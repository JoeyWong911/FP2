# Final Project Assignment 2: Explore One More! (FP2) 
DUE March 30, 2015 Monday (2015-03-30)

### My Library: racket/draw

I chose the draw library from racket because it makes sense to extend from gui to here, I can combine them for the final project.

I follwed a tutorial of how to use basic tools to creat lines, rectangles, pen and brush, colors, text and such. Used only procedure to create a picture of a little face and a sun, with caption "OPL is fun!"

I learned basic techniques of making pictures out of codes. 

```
#lang racket

(require racket/draw)
(require racket/math)


(define target (make-bitmap 150 150))
(define dc (new bitmap-dc% [bitmap target]))

(send dc set-brush "Lightblue" 'solid)
(send dc draw-rectangle 0 0 150 150)

(send dc set-smoothing 'aligned)
(send dc set-pen "yellow" 1 'solid)
(send dc set-brush "yellow" 'solid)
(send dc draw-ellipse 99 1 50 50)



(define no-pen (new pen% [style 'transparent]))
(define no-brush (new brush% [style 'transparent]))
(define skin-brush (new brush% [color "NavajoWhite"]))
(define yellow-brush (new brush% [color "yellow"]))
(define red-brush (new brush% [color "red"]))
(define red-pen (new pen% [color "red"] [width 2]))
(define yellow-pen (new pen% [color "yellow"] [width 2]))


(define draw-face dc)
(send dc set-smoothing 'aligned)

(send dc set-pen no-pen)
(send dc set-brush skin-brush)
(send dc draw-ellipse 1 49 100 100)


(send dc set-pen "black" 2 'solid)
(send dc draw-arc 25 80 20 20 (* 2 pi) (* 1 pi))
(send dc draw-arc 58 80 20 20 (* 2 pi) (* 1 pi))

(send dc set-pen no-pen)
(send dc set-brush red-brush)
(send dc draw-arc 26 85 50 50 pi (* 2 pi))


(define dc2 (new bitmap-dc% [bitmap target]))

(send dc2 set-text-foreground "Brown")
(send dc2 set-font (make-font #:size 12 
                              #:weight 'bold))
(send dc2 draw-text "OPL is fun! JK." 8 30)

;;run here
target
```

Output:

It outputs a picture of a little happy guy saying OPL is fun under the sun.

