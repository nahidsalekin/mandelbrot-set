# mandelbrot-set

gcc -Wall -g -c  mandel.c -o mandel.o

gcc -Wall -g -c  bitmap.c -o bitmap.o

gcc mandel.o bitmap.o -o mandel -lpthread

./mandel

Create Video:
ffmpeg -i mandel%d.bmp mandel.mpg

For better quality:
ffmpeg -framerate 25 -i mandel%d.bmp -c:v libx264 -profile:v high -crf 20 -pix_fmt yuv420p mandel.mpg


ffplay mandel.mpg
