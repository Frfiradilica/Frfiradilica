
#include <stdio.h>

int main() {
    // Definisanje veličine niza
    int n;

    // Unos dimenzije niza
    printf("Unesite dimenziju niza (do 50): ");
    scanf("%d", &n);

    // Provera dimenzije niza
    if (n <= 0 || n > 50) {
        printf("Neispravna dimenzija niza.\n");
        return 1; // Prekid programa u slučaju neispravne dimenzije
    }

    // Definisanje niza x i niza b
    int x[n], b[n];
    
    // Unos elemenata niza x
    printf("Unesite elemente niza x:\n");
    for (int i = 0; i < n; i++) {
        printf("Element %d: ", i + 1);
        scanf("%d", &x[i]);
    }

    // Formiranje niza b (pozitivni elementi s parnim indeksom)
    int b_size = 0;
    for (int i = 1; i < n; i += 2) {
        if (x[i] > 0) {
            b[b_size] = x[i];
            b_size++;
        }
    }

    // Pronalaženje najmanje vrednosti u nizu b
    int min_value = b[0];
    for (int i = 1; i < b_size; i++) {
        if (b[i] < min_value) {
            min_value = b[i];
        }
    }

    // Izračunavanje proizvoda elemenata niza b isključujući najmanju vrednost
    long long int product = 1;
    for (int i = 0; i < b_size; i++) {
        if (b[i] != min_value) {
            product *= b[i];
        }
    }

    // Ispis rezultata
    printf("Proizvod elemenata niza b bez najmanje vrednosti: %lld\n", product);

    return 0;
}
 
- 👋 Hi, I’m @Frfiradilica
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
Frfiradilica/Frfiradilica is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
