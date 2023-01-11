# Bank-Interface
#include "stdio.h"
#include "stdlib.h"
#include "util.h"

void welcome(){
    int selection,money=7000, amount, previousBalance;
    printf("Please select a transaction\n");
    for (int i = 0; i <2 ; ++i) {
        printf(" \n <1 BALANCE_INQUIRY\n <2 TRANSFER\n <3 CASH_WITHDRAWAL\n <4 BILL_PAYMENTS\n <5 EXIT\n\n");
        scanf("\n%d", &selection);
        printf("Your selection: %d\n", selection);
        switch (selection) {

            case 1:
                printf("Balance = %d\n\n", money);
                i = 0;
                break;
            case 2:
                printf("Enter amount\n");
                scanf("%d", &amount);
                previousBalance = money;
                money += amount;
                printf("------------------INFORMATION--------------------\n");
                printf("Previous Balance =%d\n", previousBalance);
                printf("The Amount of Transfer = %d\n", amount);

                printf("Recent Balance = %d\n", money);
                if(money<0){ printf("YOU ARE IN DEBT!\n");}
                printf("-------------------------------------------------\n");
                i = 0;
                break;
            case 3:
                printf("Enter amount\n");
                scanf("%d", &amount);
                previousBalance = money;
                money -= amount;
                printf("------------------INFORMATION--------------------\n");
                printf("Previous Balance = %d\n", previousBalance);
                printf("The Amount of Withdrawal = %d\n", amount);
                printf("Recent Balance = %d\n", money);
                if(money<0){ printf("YOU ARE IN DEBT!");}
                printf("-------------------------------------------------\n");
                i = 0;
                break;
            case 4:
                for (int j = 0; j < 2; ++j) {
                    printf("\nSelect payment bill\n");
                    printf(" <1 Water\n <2 Electricity\n <3 Internet\n <4 Natural_gas\n <5 Return Home");
                    typedef enum paymentType {Water = 1, Electricity = 2, Internet = 3, Natural_gas = 4} PaymentType;
                    PaymentType payment;
                    scanf("%d", &payment);
                    printf("Your Selection: %d\n", payment);
                        {  if (payment == 1) {
                            money -= 150;
                            printf("\nYour bill has been paid.\nCurrent Balance = %d\n", money);
                            j = 0;

                        } else if (payment == 2) {
                            money -= 300;
                            printf("\nYour bill has been paid.\nCurrent Balance = %d\n", money);
                            j = 0;

                        } else if (payment == 3) {
                            money -= 100;
                            printf("\nYour bill has been paid.\nCurrent Balance = %d\n", money);
                            j = 0;

                        } else if (payment == 4) {
                            money -= 120;
                            printf("\nYour bill has been paid.\nCurrent Balance = %d\n", money);
                            j = 0;

                        } else if (payment == 5) {j = 5;}else
                        { printf("Wrong Selection"); j = 0;}
                        }
                }
                i=0;
                break;
            default:
                printf("\n-------------------------------------------------\n");
                printf("\n\n Wrong Selection \n\n");
                printf("\n-------------------------------------------------\n");
                break;
        }
    }
}
int main(){
    welcome();
}
