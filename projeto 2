function setup() {
  createCanvas (600,400);
  trilha.loop();
}
//posiçao da Bolinha
let xBolinha = 300;
let yBolinha = 200;
let diametro = 15;

//movimento da Bolinha
let velocidadeXBolinha = 5;
let velocidadeYBolinha = 5;

//variaveis da Minha Raquete
let xRaquete = 5;
let yRaquete = 150;
let comprimentoRaquete = 10;
let alturaRaquete = 90;

//variaveis Oponente
let xRaqueteOponente = 585;
let yRaqueteOponente = 150;
let velocidadeYOponente;
 
//pontos
let meusPontos = 0;
let pontosOponente = 0;

//soons do jogo
let trilha;
let raquetada;
let ponto;

function draw() {
  background(0);
  mostraBolinha();
  movimentaBolinha ();
  verificaColisaoBorda();
  mostraRaquete(xRaquete,yRaquete);
  movimentaMinhaRaquete();
  verificaColisaoRaquete();
  mostraRaquete(xRaqueteOponente,yRaqueteOponente);
  movimentaRaqueteOponente();
  verificaColisaoRaqueteOponente();
  mostraPlacar();
  marcaPonto();
}

//funções especificas

function preload (){
trilha = loadSound ("trilha.mp3");
raquetada = loadSound ("raquetada.mp3");
ponto = loadSound ("ponto.mp3");
}

function mostraBolinha(){circle (xBolinha,yBolinha,diametro)
}

function movimentaBolinha(){xBolinha+=velocidadeXBolinha; yBolinha += velocidadeYBolinha;
}

function verificaColisaoBorda(){
  if (xBolinha + diametro/2 > width || xBolinha - diametro/2 < 0) velocidadeXBolinha *= -1;
  
  if (yBolinha + diametro/2 > height || yBolinha - diametro/2 < 0) velocidadeYBolinha *= -1;
}

function mostraRaquete(x,y){rect (x, y, comprimentoRaquete,alturaRaquete);
} 

function movimentaMinhaRaquete(){
if (keyIsDown(UP_ARROW)) {yRaquete -= 10;}

if (keyIsDown(DOWN_ARROW)) {yRaquete += 10;}               
}
   
function movimentaRaqueteOponente(){
   velocidadeYOponente = yBolinha - yRaqueteOponente - comprimentoRaquete / 2 - 30;
  yRaqueteOponente += velocidadeYOponente;
}

function verificaColisaoRaquete() {if (xBolinha - diametro/2 < xRaquete + comprimentoRaquete && yBolinha - diametro/2 < yRaquete + alturaRaquete && yBolinha + diametro/2 > yRaquete) { velocidadeXBolinha *= -1; raquetada.play();
}
}

function verificaColisaoRaqueteOponente() 
{if (xBolinha + diametro/2 > xRaqueteOponente && yBolinha - diametro/2 < yRaqueteOponente + alturaRaquete && yBolinha + diametro/2 > yRaqueteOponente) {velocidadeXBolinha *= -1; raquetada.play();
}
}

function mostraPlacar (){
stroke (225)
textAlign (CENTER);
textSize (16);
fill (color (255,150,0));
rect (150,10,40,20);
fill (255);
text (meusPontos,170,26);
fill (color(255,150,0));  
rect(450,10,40,20);
fill (255);
text (pontosOponente,470,26);
}

function marcaPonto(){
if (xBolinha >590){meusPontos += 1;
ponto.play();}
if (xBolinha < 10){pontosOponente += 1;
ponto.play();}
}
