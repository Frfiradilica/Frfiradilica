#include <stdio.h>

// Funkcija za zamenu elemenata u nizu
void zamena(float *a, float *b) {
    float temp = *a;
    *a = *b;
    *b = temp;
}

// Funkcija za sortiranje niza u rastućem redosledu
void sortirajRastuce(float niz[], int duzina) {
    for (int i = 0; i < duzina - 1; i++) {
        for (int j = 0; j < duzina - i - 1; j++) {
            if (niz[j] > niz[j + 1]) {
                zamena(&niz[j], &niz[j + 1]);
            }
        }
    }
}

// Funkcija za sortiranje niza u opadajućem redosledu
void sortirajOpadajuce(float niz[], int duzina) {
    for (int i = 0; i < duzina - 1; i++) {
        for (int j = 0; j < duzina - i - 1; j++) {
            if (niz[j] < niz[j + 1]) {
                zamena(&niz[j], &niz[j + 1]);
            }
        }
    }
}

int main() {
    int n;
    printf("Unesite broj elemenata niza: ");
    scanf("%d", &n);

    float niz[n];

    // Unos elemenata niza
    printf("Unesite decimalne brojeve u niz:\n");
    for (int i = 0; i < n; i++) {
        printf("niz[%d]: ", i);
        scanf("%f", &niz[i]);
    }

    // Sortiranje u rastućem redosledu
    sortirajRastuce(niz, n);
    printf("Niz sortiran u rastucem redosledu:\n");
    for (int i = 0; i < n; i++) {
        printf("%.2f ", niz[i]);
    }
    printf("\n");

    // Sortiranje u opadajućem redosledu
    sortirajOpadajuce(niz, n);
    printf("Niz sortiran u opadajucem redosledu:\n");
    for (int i = 0; i < n; i++) {
        printf("%.2f ", niz[i]);
    }
    printf("\n");

    return 0;
}
