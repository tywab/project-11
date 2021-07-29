var road,runningPath;
var runner,boy
var edges;
function preload(){
  //pre-load images
  road=loadImage("path.png")
  runner=loadAnimation("Runner-1.png","Runner-2.png");
}

function setup(){
  createCanvas(600,600);
  //create sprites here
  runningPath=createSprite(300,300,600,600);
  runningPath.addImage(road);
  runningPath.velocityY=-6
  runningPath.scale=1.2
  boy=createSprite(300,500,50,100);
  boy.addAnimation("running",runner)
  boy.scale=0.1
  
  edges=createEdgeSprites()




}

function draw() {
  background(0);
  if(runningPath.y<0){
    runningPath.y=300
  }
  boy.x= World.mouseX;
  boy.collide(edges[0]);
  boy.collide(edges[2]);
  drawSprites();

}
