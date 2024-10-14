#include <iostream>
#include <vector>

void sortColors(std::vector<int>& arr) {
    int low = 0, mid = 0, high = arr.size() - 1;

    while (mid <= high) {
        if (arr[mid] == 0) {  // Màu đỏ
            std::swap(arr[low], arr[mid]);
            low++;
            mid++;
        } else if (arr[mid] == 1) {  // Màu trắng
            mid++;
        } else {  // Màu xanh
            std::swap(arr[mid], arr[high]);
            high--;
        }
    }
}

int main() {
    std::vector<int> colors = {2, 0, 2, 0, 0, 1, 0, 2, 1};  // 0: đỏ, 1: trắng, 2: xanh
    
    sortColors(colors);
    
    std::cout << "Kết quả: { ";
    for (int color : colors) {
        std::cout << color << " ";
    }
    std::cout << "}" << std::endl;

    return 0;
}