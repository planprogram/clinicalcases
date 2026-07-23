# clinicalcases

Aplicação de avaliação de casos clínicos com persistência em rede via Firebase Realtime Database.

## Configurar Firebase Realtime Database

1. Crie um projeto Firebase e ative o Realtime Database.
2. Configure as regras de leitura/escrita.
3. No arquivo [index.html](index.html), ajuste `FB_DB_URL` se necessário.

## Autenticacao (recomendado)

Se suas regras exigem usuario autenticado (evita 401/403), habilite login anonimo:

1. No Firebase Console, abra Authentication > Sign-in method e ative Anonymous.
2. Em [index.html](index.html), configure:
	 - `FB_AUTH_MODE='anon'`
	 - `FB_CONFIG` com `apiKey`, `authDomain`, `projectId`, `appId`
3. Opcional: se preferir REST token manual, preencha `FB_DB_TOKEN`.

Exemplo:

```js
var FB_AUTH_MODE='anon';
var FB_CONFIG={
	apiKey:'SUA_API_KEY',
	authDomain:'seu-projeto.firebaseapp.com',
	projectId:'seu-projeto',
	appId:'SUA_APP_ID'
};
```

### Regras sugeridas (fase de testes)

```json
{
	"rules": {
		".read": true,
		".write": true
	}
}
```

## Observações

- O sistema salva dados apenas no Firebase (não usa localStorage).
- Dados gravados no banco:
	- `app_state/global/cases_json`
	- `participant_answers/{id_participante}`