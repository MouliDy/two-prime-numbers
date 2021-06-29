#include <iostream>
using namespace std;

int Prime(int n);

int main() {
    int n, i;
    int flag = 0;

    cout << "Enter a positive  integer: ";
    cin >> n;

    for(i = 2; i <= n/2; ++i) {
        if (Prime(i)) {
            if (Prime(n - i)) {
                cout << n << " = " << i << " + " << n-i << endl;
                flag = 1;
            }
        }
    }

    if (!flag)
      cout << n << " not a sum of two prime numbers.";

    return 0;
}
int Prime(int n)
{
    int i;
    int isPrime = 1;

    if (n == 0 || n == 1) {
        isPrime = 0;
    }
    else {
        for(i = 2; i <= n/2; ++i) {
            if(n % i == 0) {
                isPrime = 0;
                break;
            }
        }
    }

    return isPrime;
}
