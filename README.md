# PRACTIKA
#include <iostream>
#include <vector>

using namespace std;

void linearApprox(const vector<double>& x, const vector<double>& y, double& a, double& b) {
    int n = x.size();
    double sumX = 0, sumY = 0, sumXY = 0, sumXX = 0;

    for (int i = 0; i < n; i++) {
        sumX += x[i];
        sumY += y[i];
        sumXY += x[i] * y[i];
        sumXX += x[i] * x[i];
    }

    a = (n * sumXY - sumX * sumY) / (n * sumXX - sumX * sumX);
    b = (sumY - a * sumX) / n;
}

int main() {
    vector<double> x = {1.0, 2.0, 3.0, 4.0, 5.0};
    vector<double> y = {2.1, 4.3, 6.2, 8.0, 10.1};

    double a, b;
    linearApprox(x, y, a, b);

    cout << "Линейная аппроксимация: y = " << a << "x + " << b << endl;

    return 0;
}
