#include <stdio.h>
#include <stdlib.h>

// Structure pour un noeud de la liste circulaire
typedef struct NoeudCirculaire {
    int val;
    struct NoeudCirculaire* suiv;
} NoeudCirculaire;

// Fonction pour créer un nouveau noeud
NoeudCirculaire* creerNoeud(int val) {
    NoeudCirculaire* nouveau = (NoeudCirculaire*)malloc(sizeof(NoeudCirculaire));
    nouveau->val = val;
    return nouveau;
}

// Fonction pour insérer un élément en tête de la liste circulaire
void insererEnTeteCirculaire(NoeudCirculaire** tete, int val) {
    NoeudCirculaire* nouveau = creerNoeud(val);
    if (*tete == NULL) {
        *tete = nouveau;
        nouveau->suiv = *tete;
    } else {
        NoeudCirculaire* last = (*tete)->suiv;
        while (last->suiv != *tete) {
            last = last->suiv;
        }
        last->suiv = nouveau;
        nouveau->suiv = *tete;
        *tete = nouveau;
    }
}

// Fonction pour insérer un élément en queue de la liste circulaire
void insererEnQueueCirculaire(NoeudCirculaire** tete, int val) {
    NoeudCirculaire* nouveau = creerNoeud(val);
    if (*tete == NULL) {
        *tete = nouveau;
        nouveau->suiv = *tete;
    } else {
        NoeudCirculaire* last = *tete;
        while (last->suiv != *tete) {
            last = last->suiv;
        }
        last->suiv = nouveau;
        nouveau->suiv = *tete;
    }
}

// Fonction pour afficher la liste circulaire
void afficherListe(NoeudCirculaire* tete) {
    if (tete == NULL) return;

    NoeudCirculaire* temp = tete;
    do {
        printf("%d ", temp->val);
        temp = temp->suiv;
    } while (temp != tete);
    printf("\n");
}

int main() {
    NoeudCirculaire* tete = NULL;
    int choix, val, n;

    printf("Combien de nombres voulez-vous insérer en queue ? ");
    scanf("%d", &n);

    for (int i = 0; i < n; i++) {
        printf("Entrez le nombre %d : ", i + 1);
        scanf("%d", &val);
        insererEnQueueCirculaire(&tete, val);
    }

    printf("Liste après insertion en queue : ");
    afficherListe(tete);

    printf("Combien de nombres voulez-vous insérer en tête ? ");
    scanf("%d", &n);

    for (int i = 0; i < n; i++) {
        printf("Entrez le nombre %d : ", i + 1);
        scanf("%d", &val);
        insererEnTeteCirculaire(&tete, val);
    }

    printf("Liste après insertion en tête : ");
    afficherListe(tete);

    return 0;
}
