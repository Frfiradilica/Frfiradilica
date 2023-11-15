#include <stdio.h>

int main() {
    int n;

    // Unos dužine niza x
    printf("Unesite duzinu niza x (do 50): ");
    scanf("%d", &n);

    if (n <= 0 || n > 50) {
        printf("Neispravna duzina niza.\n");
        return 1;
    }

    // Unos elemenata niza x
    int x[50];
    printf("Unesite elemente niza x:\n");
    for (int i = 0; i < n; i++) {
        printf("x[%d]: ", i);
        scanf("%d", &x[i]);
    }

    // Formiranje niza b
    int b[25];  // Kako b ima samo pozitivne elemente sa parnim indeksima, dužina će biti najviše n/2
    int brojacB = 0;
    for (int i = 0; i < n; i += 2) {
        if (x[i] > 0) {
            b[brojacB] = x[i];
            brojacB++;
        }
    }

    // Računanje proizvoda elemenata niza b, isključujući elemente sa najmanjom vrednošću
    int najmanjiElement = b[0];
    for (int i = 1; i < brojacB; i++) {
        if (b[i] < najmanjiElement) {
            najmanjiElement = b[i];
        }
    }

    long long proizvod = 1;
    for (int i = 0; i < brojacB; i++) {
        if (b[i] != najmanjiElement) {
            proizvod *= b[i];
        }
    }

    // Ispis rezultata
    printf("Proizvod elemenata niza b bez najmanjeg elementa: %lld\n", proizvod);

    return 0;
}
