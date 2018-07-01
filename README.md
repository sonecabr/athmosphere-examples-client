# Just a simple event using atmosphere samples

To test:
- Edit js/main.js and change request endpoint to your atmosphere server
- Just access the file in your browser
- Use curl or another http client to send example msg, like:
```
curl -XPOST 'https://88535ecd.ngrok.io/api/chat/6c171b3e-a3f8-465f-9d39-255660a90acf/GRUPO/SOLICITADA/b5c514a2-7e6e-4b5a-b716-617736185632' -d 'the_msg'
```
Edit the onMessage method to correspond to your msg pattern:
```
var me = json.event.usuarioOrigem.nome == author;
var date =  typeof(json.event.dtInclusao) == 'string' ? parseInt(json.event.dtInclusao) : json.event.dtInclusao;
addMessage(json.event.usuarioOrigem.nome, json.event.msg, me ? 'blue' : 'black', new Date(date));
```
