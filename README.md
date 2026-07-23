# clinicalcases

Aplicação de avaliação de casos clínicos com persistência em rede via Firebase Realtime Database.

## Configurar Firebase Realtime Database

1. Crie um projeto Firebase e ative o Realtime Database.
2. Configure as regras de leitura/escrita.
3. No arquivo [index.html](index.html), ajuste `FB_DB_URL` se necessário.

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