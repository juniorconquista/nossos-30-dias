# Nossos 30 dias

Site do desafio de 30 dias: https://juniorconquista.github.io/nossos-30-dias/

## Onde os dados ficam salvos

As marcações ficam salvas no Firebase Firestore, no documento `casais/<código>`. O código do casal vai no fim do link, depois do `#`, e não está neste repositório: só quem tem o link completo consegue ler ou mudar os dados. O `localStorage` de cada aparelho fica como cópia para quando estiver sem internet.

Se o `FB_CONFIG` no `index.html` estiver `null`, o site salva só no aparelho.

## Como configurar o Firebase

1. Acesse https://console.firebase.google.com e crie um projeto (o Google Analytics pode ficar desligado).
2. Vá em **Criação > Firestore Database > Criar banco de dados**, escolha a região `southamerica-east1` e o **modo de produção**.
3. Na aba **Regras**, cole as regras abaixo e clique em **Publicar**:

   ```
   rules_version = '2';
   service cloud.firestore {
     match /databases/{database}/documents {
       match /casais/{id} {
         allow get, create, update: if id.size() >= 20;
         allow list, delete: if false;
       }
     }
   }
   ```

4. Clique na engrenagem e vá em **Configurações do projeto > Seus apps > ícone `</>` (Web)**. Registre o app sem ativar o Hosting e copie o objeto `firebaseConfig`.
5. No `index.html`, troque `var FB_CONFIG=null;` por esse objeto. Os dados do `firebaseConfig` podem ficar no repositório público: eles só identificam o projeto, e quem protege os dados são as regras e o código do casal.

## Primeiro uso

Abra o site em um celular. O endereço vai ganhar um `#código` no final. Toque em **Copiar link para o outro celular** (no rodapé) e abra esse link no outro aparelho. A partir daí, os dois veem o mesmo placar e o mesmo baú.
