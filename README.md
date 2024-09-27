#include <stdio.h>
// 递归函数，用于移动盘子
void hanoi(int n, char from_rod, char to_rod, char aux_rod) {
    if (n == 1) {
        printf("\n 移动盘子 1 从 %c 到 %c", from_rod, to_rod);
        return;
    }
    hanoi(n - 1, from_rod, aux_rod, to_rod);
    printf("\n 移动盘子 %d 从 %c 到 %c", n, from_rod, to_rod);
    hanoi(n - 1, aux_rod, to_rod, from_rod);
}

// 主函数
int main() {
    int n = 3; // 盘子的数量
    // 调用递归函数开始解决汉诺塔问题
    hanoi(n, 'A', 'C', 'B'); // A为起始柱子，C为目标柱子，B为辅助柱子
    return 0;
}
