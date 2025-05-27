# Decimal-to-Binary

#include <stdio.h>
#include <math.h>

int binarySizeCalculator(int input)
{
    int binarySize = 0;
    do 
    {   
        input /= 2;
        binarySize++;

    } while(input > 0);
    return binarySize;
}

void tavan(int *arraybinary, int input, int binarySize)
{
    do 
    {
        for(int i = 0; i < binarySize; i++)
        {
            arraybinary[i] = input % 2;
            input /= 2;
        }

    } while(input > 0);
}

int main(void)
{
    int input;
    int binarySize;

    printf("Enter a number: ");
    scanf("%d", &input);

    if(input < 0)
    {
        printf("Please enter only positive integers!\n");
    }

    // printf("Input: %d\n", input);

    binarySize = binarySizeCalculator(input);

    // printf("Binary size: %d\n",  binarySize);

    int arraybinary[binarySize];

    tavan(arraybinary, input, binarySize); 
    
    // printf("1s & 0s:\n");
    // for(int i = 0; i < binarySize; i++)
    // {
    //     printf("%d ", arraybinary[i]);
    // }
    // printf("\n");

    printf("Binary:\n");
    for(int i = binarySize - 1; i >= 0; i--)
    {
        printf("%d", arraybinary[i]);
    }
    printf("\n");

    return 0;
}
