// Daniel Shiffman & Conor O'Neill
// http://codingtra.in
// http://patreon.com/codingtrain

// Sandpiles
// https://youtu.be/diGjw5tghYU

int[][] sandpiles;

void setup() {
  size(800, 800);
  sandpiles = new int[width][height];
  sandpiles[width/2][height/2] = 1000000;
}

void topple() {
  int[][] nextpiles = new int[width][height];  
  for (int x = 1; x < width-1; x++) {
    for (int y = 1; y < height-1; y++) {
      int num=sandpiles[x][y];
      int over=floor(sandpiles[x+1][y]/4)+floor(sandpiles[x-1][y]/4)+floor(sandpiles[x][y+1]/4)+floor(sandpiles[x][y-1]/4);
      nextpiles[x][y]=num%4+over;
    }
  }

  sandpiles = nextpiles;
}

void render() {
  loadPixels();
  for (int x = 0; x < width; x++) {
    for (int y = 0; y < height; y++) {
      int num = sandpiles[x][y];
      color col = color(255, 0, 0);
      if (num == 0) {
        col = color(255, 255, 0);
      } else if (num == 1) {
        col = color(0, 185, 63);
      } else if (num == 2) {
        col = color(0, 104, 255);
      } else if (num == 3) {
        col = color(122, 0, 229);
      }

      pixels[x+y*width] = col;
    }
  }

  updatePixels();
}


void draw() {
  render(); 
  topple();
  }
