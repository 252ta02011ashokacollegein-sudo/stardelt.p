# stardelt.p
star and delt in culcution c programing code..✨
Sure. If you mean Star and Delta connection calculations in C programming, here is a simple program.
Star (Y) and Delta (Δ) Conversion
Formulas:
Delta → Star
RA = (R1 × R2) / (R1 + R2 + R3)
RB = (R2 × R3) / (R1 + R2 + R3)
RC = (R3 × R1) / (R1 + R2 + R3)
Star → Delta
R1 = (RA×RB + RB×RC + RC×RA) / RC
R2 = (RA×RB + RB×RC + RC×RA) / RA
R3 = (RA×RB + RB×RC + RC×RA) / RB
#include <stdio.h>

int main()
{
    int choice;
    float R1, R2, R3, RA, RB, RC, sum;

    printf("1. Delta to Star\n");
    printf("2. Star to Delta\n");
    printf("Enter your choice: ");
    scanf("%d", &choice);

    if (choice == 1)
    {
        printf("Enter Delta resistances R1, R2, R3: ");
        scanf("%f %f %f", &R1, &R2, &R3);

        sum = R1 + R2 + R3;

        RA = (R1 * R2) / sum;
        RB = (R2 * R3) / sum;
        RC = (R3 * R1) / sum;

        printf("\nStar resistances:\n");
        printf("RA = %.2f ohms\n", RA);
        printf("RB = %.2f ohms\n", RB);
        printf("RC = %.2f ohms\n", RC);
    }
    else if (choice == 2)
    {
        printf("Enter Star resistances RA, RB, RC: ");
        scanf("%f %f %f", &RA, &RB, &RC);

        R1 = (RA*RB + RB*RC + RC*RA) / RC;
        R2 = (RA*RB + RB*RC + RC*RA) / RA;
        R3 = (RA*RB + RB*RC + RC*RA) / RB;

        printf("\nDelta resistances:\n");
        printf("R1 = %.2f ohms\n", R1);
        printf("R2 = %.2f ohms\n", R2);
        printf("R3 = %.2f ohms\n", R3);
    }
    else
    {
        printf("Invalid choice");
    }

    return 0;
}
