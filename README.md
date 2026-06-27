#include <stdio.h>
#include <string.h>

#define MAX 100 // Static array size

typedef struct {
    int id;
    char name[50];
    int quantity;
    float price;
} Item;

Item inventory[MAX];
int count = 0;

void addItem() {
    if (count < MAX) {
        printf("Enter ID, Name, Quantity, Price: ");
        scanf("%d %s %d %f", &inventory[count].id, inventory[count].name, &inventory[count].quantity, &inventory[count].price);
        count++;
        printf("Item added successfully!\n");
    } else {
        printf("Inventory Full!\n");
    }
}

void displayInventory() {
    printf("\n--- CURRENT INVENTORY ---\n");
    printf("ID\tName\t\tQty\tPrice\n");
    for (int i = 0; i < count; i++) {
        printf("%d\t%s\t\t%d\t%.2f\n", inventory[i].id, inventory[i].name, inventory[i].quantity, inventory[i].price);
    }
}

int main() {
    int choice;
    while(1) {
        printf("\n1. Add Item\n2. View Inventory\n3. Exit\nChoice: ");
        scanf("%d", &choice);
        if (choice == 1) addItem();
        else if (choice == 2) displayInventory();
        else break;
    }
    return 0;
}
