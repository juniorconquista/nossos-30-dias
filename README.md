# Nossos 30 dias

Site do desafio de 30 dias: https://juniorconquista.github.io/nossos-30-dias/

## Onde os dados ficam salvos

As marcações ficam salvas no Firebase Firestore, no documento `casais/<código>`. O código do casal vai no fim do link, depois do `#`, e não está neste repositório: só quem tem o link completo consegue ler ou mudar os dados. O `localStorage` de cada aparelho fica como cópia para quando estiver sem internet.

Se o `FB_CONFIG` no `index.html` estiver `null`, o site salva só no aparelho.

## Firebase

Projeto: `nossos-30-dias-4x73r` (plano gratuito Spark, sem cartão). Console: https://console.firebase.google.com/project/nossos-30-dias-4x73r/firestore

As regras de segurança ficam em `firestore.rules`. Para publicar uma mudança nelas:

```bash
npx firebase-tools deploy --only firestore:rules
```

## Primeiro uso

Abra o site em um celular. O endereço vai ganhar um `#código` no final. Toque em **Copiar link para o outro celular** (no rodapé) e abra esse link no outro aparelho. A partir daí, os dois veem o mesmo placar e o mesmo baú.
