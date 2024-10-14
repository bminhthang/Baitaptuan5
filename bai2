#include <iostream>
#include <vector>
#include <cmath>

using namespace std;

// Hàm kiểm tra một số có phải số nguyên tố hay không
bool isPrime(int n) {
    if (n < 2) return false;
    for (int i = 2; i <= sqrt(n); i++) {
        if (n % i == 0) return false;
    }
    return true;
}

// Hàm kiểm tra xem một số có phải là số Blum hay không
bool isBlumNumber(int n) {
    for (int p = 2; p * p <= n; p++) {
        if (isPrime(p) && p % 4 == 3) {
            int q = n / p;
            if (n % p == 0 && isPrime(q) && q % 4 == 3) {
                return true;
            }
        }
    }
    return false;
}

// Hàm tạo danh sách các số Blum nhỏ hơn N
vector<int> generateBlumNumbers(int N) {
    vector<int> blumNumbers;
    for (int i = 2; i < N; i++) {
        if (isBlumNumber(i)) {
            blumNumbers.push_back(i);
        }
    }
    return blumNumbers;
}

// Hàm tìm các cặp số Blum có tổng cũng là một số Blum
void findBlumPairs(const vector<int>& blumNumbers, int N) {
    cout << "Các cặp số Blum có tổng cũng là số Blum: \n";
    for (int i = 0; i < blumNumbers.size(); i++) {
        for (int j = i; j < blumNumbers.size(); j++) {
            int sum = blumNumbers[i] + blumNumbers[j];
            if (sum < N && isBlumNumber(sum)) {
                cout << blumNumbers[i] << " + " << blumNumbers[j] << " = " << sum << "\n";
            }
        }
    }
}

// Hàm kiểm tra xem số M có trong dãy số Blum hay không
bool checkBlumExist(const vector<int>& blumNumbers, int M) {
    for (int num : blumNumbers) {
        if (num == M) return true;
    }
    return false;
}

int main() {
    int N;
    cout << "Nhập số N: ";
    cin >> N;

    // Bước 1: Tạo danh sách các số Blum nhỏ hơn N
    vector<int> blumNumbers = generateBlumNumbers(N);

    // Bước 2: In ra danh sách các số Blum
    cout << "Các số Blum nhỏ hơn " << N << ": ";
    for (int num : blumNumbers) {
        cout << num << " ";
    }
    cout << endl;

    // Bước 3: Tìm các cặp số Blum có tổng cũng là số Blum
    findBlumPairs(blumNumbers, N);

    // Bước 4: Kiểm tra số Blum M
    int M;
    cout << "Nhập số M để kiểm tra: ";
    cin >> M;
    if (checkBlumExist(blumNumbers, M)) {
        cout << M << " là một số Blum trong dãy.\n";
    } else {
        cout << M << " không phải là số Blum trong dãy.\n";
    }

    return 0;
}