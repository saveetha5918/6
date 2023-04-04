#include <stdio.h>

int main() {
    int amount, notes;
    int denominations[] = {500, 100, 50, 20, 10, 5, 2, 1};
    int notes_count[sizeof(denominations) / sizeof(denominations[0])];

    printf("Enter the amount: ");
    scanf("%d", &amount);

    // Initialize notes count for each denomination to 0
    for(int i = 0; i < sizeof(denominations) / sizeof(denominations[0]); i++) {
        notes_count[i] = 0;
    }

    // Calculate minimum number of notes for each denomination
    for(int i = 0; i < sizeof(denominations) / sizeof(denominations[0]); i++) {
        notes = amount / denominations[i];
        amount = amount % denominations[i];
        notes_count[i] = notes;
    }

    // Print minimum number of notes for each denomination
    printf("Total number of notes:\n");
    for(int i = 0; i < sizeof(denominations) / sizeof(denominations[0]); i++) {
        printf("%d: %d\n", denominations[i], notes_count[i]);
    }

    return 0;
}
