# CodeStudy

Platforma do nauki programowania (HTML i SQL) oparta na własnych pytaniach.
Bez AI w aplikacji: pytania przygotowujesz wcześniej i wgrywasz jako pliki JSON.

## Jak to działa

- Wpisujesz odpowiedzi samodzielnie, bez opcji ABCD.
- Aplikacja porównuje je z poprawnymi wariantami i pokazuje wyjaśnienie.
- Postępy, historia i błędne pytania zapisują się w przeglądarce.

## Struktura repozytorium

```
codestudy/
├── index.html
└── materials/
    └── PRZEDMIOT/        HTML albo SQL
        └── DZIAL/        folder działu
            └── temat.json
```

Prawdziwe nazwy działu i tematu aplikacja czyta z pól `section` i `topic` w pliku JSON.

## Uruchomienie

1. Załóż publiczne repozytorium na GitHubie i wgraj `index.html` oraz folder `materials`.
2. Włącz Pages: Settings → Pages → Branch `main`, folder `/ (root)`.
3. Otwórz `https://TWOJ-LOGIN.github.io/NAZWA-REPO/`.
4. Naciśnij **Synchronizuj** na stronie głównej.

## Dodawanie tematu

1. Wygeneruj plik JSON zewnętrznym AI.
2. Dodaj go w `materials/PRZEDMIOT/DZIAL/temat.json`.
3. Naciśnij **Synchronizuj** w aplikacji.

## Format pliku

```json
{
  "subject": "HTML",
  "section": "JavaScript",
  "topic": "Obiekty wbudowane",
  "questions": [
    {
      "id": "q1",
      "type": "short_answer",
      "question": "Jaką komendą wyświetlisz adres URL strony?",
      "correct_answer": "document.location",
      "accepted_answers": ["document.location"],
      "explanation": "document.location zwraca adres URL aktualnej strony."
    }
  ]
}
```

## Sprawdzanie odpowiedzi

- Pomijane są zbędne spacje, końcowy średnik i różnice w cudzysłowach.
- W HTML wielkość liter ma znaczenie, w SQL nie.
- Pole `"case_sensitive": true` lub `false` w pytaniu nadpisuje to ustawienie.
