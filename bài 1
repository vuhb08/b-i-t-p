#include <iostream>
using namespace std;

// Định nghĩa một Node của đa thức
struct Node {
    int coefficient;  // hệ số
    int exponent;     // số mũ
    Node* next;       // con trỏ đến Node tiếp theo
};

// Hàm thêm một Node mới vào danh sách
void insertTerm(Node*& head, int coefficient, int exponent) {
    if (coefficient == 0) return;  // Bỏ qua nếu hệ số là 0

    Node* newNode = new Node;
    newNode->coefficient = coefficient;
    newNode->exponent = exponent;
    newNode->next = nullptr;

    if (head == nullptr) {  // Danh sách rỗng, thêm phần tử đầu tiên
        head = newNode;
    } else {  // Thêm phần tử vào cuối danh sách
        Node* temp = head;
        while (temp->next != nullptr) {
            temp = temp->next;
        }
        temp->next = newNode;
    }
}

// Hàm in đa thức
void printPolynomial(Node* head) {
    Node* temp = head;
    while (temp != nullptr) {
        cout << temp->coefficient << "x^" << temp->exponent;
        temp = temp->next;
        if (temp != nullptr) cout << " + ";
    }
    cout << endl;
}

// Hàm giải phóng bộ nhớ cho danh sách móc nối
void freeList(Node*& head) {
    Node* temp;
    while (head != nullptr) {
        temp = head;
        head = head->next;
        delete temp;
    }
}

int main() {
    Node* polynomial = nullptr;

    int coefficient, exponent;
    char choice;

    // Nhập đa thức
    do {
        cout << "Nhập hệ số: ";
        cin >> coefficient;
        cout << "Nhập số mũ: ";
        cin >> exponent;

        // Thêm vào danh sách nếu hệ số không phải là 0
        insertTerm(polynomial, coefficient, exponent);

        cout << "Tiếp tục nhập? (y/n): ";
        cin >> choice;
    } while (choice == 'y' || choice == 'Y');

    // In đa thức
    cout << "Đa thức đã nhập: ";
    printPolynomial(polynomial);

    // Giải phóng bộ nhớ
    freeList(polynomial);

    return 0;
}
