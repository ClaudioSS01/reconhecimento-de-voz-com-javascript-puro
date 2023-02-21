# reconhecimento-de-voz-com-javascript-puro
#reconhecimento de voz com javascript puro

var recognition = new (window.SpeechRecognition || window.webkitSpeechRecognition || window.mozSpeechRecognition || window.msSpeechRecognition)();
recognition.lang = 'pt';
recognition.interimResults = false;
recognition.maxAlternatives = 5;


setInterval(()=>{
recognition.start();
console.log('escutando')
},3000)

recognition.onresult = function(event) {
    console.log('você disse ', event.results[0][0].transcript);
};
