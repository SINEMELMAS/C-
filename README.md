# C++
#include <iostream>
#include <vector>
#include <cmath>

class CalcuClass {
public:
    int Summation(std::vector<int> nums) {
        int sum = 0;
        for (int num : nums) {
            sum += num;
        }
        return sum;
    }

    int Multiply(std::vector<int> nums) {
        int result = 1;
        for (int num : nums) {
            result *= num;
        }
        return result;
    }

    double Deviations(std::vector<int> nums) {
        if (nums.empty()) return 0.0;
        double mean = static_cast<double>(Summation(nums)) / static_cast<double>(nums.size());
        double deviations = 0.0;
        for (int num : nums) {
            deviations += pow(num - mean, 2);
        }
        return sqrt(deviations / static_cast<double>(nums.size()));
    }

    int Subtract(std::vector<int> nums) {
        if (nums.empty()) return 0;
        int result = nums[0];
        for (int i = 1; i < nums.size(); ++i) {
            result -= nums[i];
        }
        return result;
    }
};

int main() {
    CalcuClass calculator;
    std::vector<int> nums;
    int choice;
    int num;

    do {
        std::cout << "=========================================================\n\n";
        std::cout << "====================by Sinem Elmas=======================\n\n";
        std::cout << "    ~~ WELCOME to Data Structure Algorithms program ~~\n\n";
        std::cout << "Select and Enter Your Choice from the Menu :\n";
        std::cout << "  1. + Summation\n";
        std::cout << "  2. * Multiply\n";
        std::cout << "  3. / Deviations\n";
        std::cout << "  4. - Subtract\n";
        std::cout << "  5. Exit\n";
        std::cout << "=========================================================\n";
        std::cin >> choice;

        switch (choice) {
            case 1:
            case 2:
            case 4:
                std::cout << "Enter the size of the array: ";
                std::cin >> num;
                nums.clear();
                std::cout << "Enter " << num << " elements:\n";
                for (int i = 0; i < num; ++i) {
                    int element;
                    std::cin >> element;
                    nums.push_back(element);
                }
                break;
            case 3:
                std::cout << "Enter the size of the array: ";
                std::cin >> num;
                nums.clear();
                std::cout << "Enter " << num << " elements:\n";
                for (int i = 0; i < num; ++i) {
                    int element;
                    std::cin >> element;
                    nums.push_back(element);
                }
                break;
            case 5:
                std::cout << "Exiting the program. Thank you for using the program.\n";
                return 0;
            default:
                std::cout << "Invalid choice! Please try again.\n";
                continue;
        }

        switch (choice) {
            case 1:
                std::cout << "Summation result: " << calculator.Summation(nums) << std::endl;
                break;
            case 2:
                std::cout << "Multiplication result: " << calculator.Multiply(nums) << std::endl;
                break;
            case 3:
                std::cout << "Standard Deviation: " << calculator.Deviations(nums) << std::endl;
                break;
            case 4:
                std::cout << "Subtraction result: " << calculator.Subtract(nums) << std::endl;
                break;
        }

    } while (true);

    return 0;
}
