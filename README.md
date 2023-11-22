ggg
#include <stdio.h>

int main() {
    // Deklaracija nizova
    char originalniNiz[] = "Ovo je neki tekst sa razmacima.";
    char noviNiz[1000]; // Pretpostavljena maksimalna dužina novog niza

    // Inicijalizacija indeksa za novi niz
    int j = 0;

    // For petlja za kopiranje karaktera bez razmaka u novi niz
    for (int i = 0; originalniNiz[i] != '\0'; i++) {
        if (originalniNiz[i] != ' ' && originalniNiz[i] != '\t' && originalniNiz[i] != '\n') {
            noviNiz[j++] = originalniNiz[i];
        }
    }
    noviNiz[j] = '\0'; // Postavljanje kraja niza

    // Ispis rezultata
    printf("Originalni niz: %s\n", originalniNiz);
    printf("Novi niz bez razmaka: %s\n", noviNiz);

    return 0;
}
