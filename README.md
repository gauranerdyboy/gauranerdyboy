import turtle
from time import sleep

screen = turtle.Screen()
screen.setup(600, 600)
screen.bgcolor("black")
turtle.speed(0)
turtle.ht()
turtle.penup()

def create_food():
    food = turtle.Turtle()
    food.shape("circle")
    food.color("red")
    food.penup()
    food.goto(0, 100)
    return food

def move():
    turtle.direction = "stop"

    def go_up():
        turtle.direction = "up"

    def go_down():
        turtle.direction = "down"
    
    def go_left():
        turtle.direction = "left"

    def go_right():
        turtle.direction = "right"

    screen.onkey(go_up, "w")
    screen.onkey(go_down, "s")
    screen.onkey(go_left, "a")
    screen.onkey(go_right, "d")

    while True:
        screen.update()

        if turtle.direction == "up":
            y = turtle.ycor()
            turtle.sety(y + 20)

        if turtle.direction == "down":
            y = turtle.ycor()
            turtle.sety(y - 20)

        if turtle.direction == "left":
            x = turtle.xcor()
            turtle.setx(x - 20)

        if turtle.direction == "right":
            x = turtle.xcor()
            turtle.setx(x + 20)

        sleep(0.1)

def main():
    turtle.goto(0, 0)
    turtle.st()
    screen.listen()
    move()
    screen.mainloop()

if __name__ == "__main__":
    main()
