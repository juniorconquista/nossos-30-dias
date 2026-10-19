# Nossos 30 dias

Site do desafio de 30 dias: https://juniorconquista.github.io/nossos-30-dias/

## Onde os dados ficam salvos

As marcações ficam no Firebase Firestore, num cofre único do casal: o documento `casais/<COFRE>`, definido no `index.html`. Os dois celulares abrem o mesmo endereço e caem sempre no mesmo cofre. As regras do Firestore só deixam ler e gravar esse documento (não dá para listar, apagar nem criar outros). O `localStorage` de cada aparelho fica como cópia para quando estiver sem internet.

## Firebase

Projeto: `nossos-30-dias-4x73r` (plano gratuito Spark, sem cartão). Console: https://console.firebase.google.com/project/nossos-30-dias-4x73r/firestore

As regras de segurança ficam em `firestore.rules`. Para publicar uma mudança nelas:

```bash
npx firebase-tools deploy --only firestore:rules
```

## Primeiro uso

É só abrir https://juniorconquista.github.io/nossos-30-dias/ nos dois celulares. Não precisa de link especial nem de código.
