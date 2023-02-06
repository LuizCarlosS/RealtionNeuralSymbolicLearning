# Neural Symbolic Learning

## Setup

To properly run the code inside this repository, please run

`pip install -r requirements.txt`

## Description

This repository aims to give answer to two propositions, both based on the following example of the Michalski train:

![Figure 1 - Example fo Michalski Train](/Contextualization/description-1.png)

Besides this, it's stated that the number of attributes is:
1. Number of cars per train (range of values is 3 to 5)
2. Amount of different loads it can carry (valor entre 1 a 4)
3. For each car of a train:
    1. the quantity of axle with wheels (range of values is 2 to 3)
    2. the length of a car (short or long)
    3. the shape of the car body, and can be
       1. Closed-rectangle,
       2. open-rectangle
       3. Double open-rectangle
       4. Ellipse,
       5. Engine or locomotive
       6. Hexagon
       7. Jagged top,
       8. Open trap,
       9. Sloped top
    4. The number of loads (range of values is 0 to 3)
    5. Shape of the load (circle, hexagon, rectangle, or triangle).

Alongsides 10 boolean attributes which describe wether or not a pair of cargo types are in adjacent train cars (since each car carries a single type of cargo)
We have the following relations with respect to the carriages of a train, whose logical value
varies between -1 (False) and 1 (True).
1. There is a rectangle next to a rectangle (-1 or 1)
2. There is a rectangle next to a triangle (-1 or 1)
3. There is a rectangle next to a hexagon (-1 or 1)
4. There is a rectangle next to a circle (-1 or 1)
5. There is a triangle next to a triangle (-1 or 1)
6. There is a triangle next to a hexagon (-1 or 1)
7. There is a triangle next to a circle (-1 or 1)
8. There is a circle next to a circle (-1 or 1)

Finally, a single class attribute defines the direction of the train, be it east or west.
Attributes with multiple values have integers assined to them, in the order which they are presented above. I.E. in the shape of the load, circle would be assigned value 1, hexagon would be 2, and so on.
Corresponding neurons must use linear activation function, i.e. h(x) = x.

## Question 1

The first question asks the following:
> Implement a solution based on the relational learning model containing meta-networks to connect premise concepts. This models must contain 11 networks, one for each of the following concepts as defined on pages 136 and 137 (of book Neural Symbolic Cognitive Reasoning):
   1. num_cars(t, nc), in which t ∊ [1..10] and nc ∊ [3..5].
   2. num_loads(t, nl) in which t ∊ [1..10] an nl ∊ [1..4].
   3. num_wheels(t, c, w) in which t ∊ [1..10] and c ∊ [1..4] e w ∊ [2..3].
   4. length(t, c, l) in which t ∊ [1..10] and c ∊ [1..4] and l ∊ [-1..1] (-1 denotes short and 1
   long)
   5. shape(t, c, s) in which t ∊ [1..10] and c ∊ [1..4] and s ∊ [1..10] (one number for each
   shape).
   6. num_cars_loads(t, c, ncl) in which t ∊ [1..10] and c ∊ [1..4] e ncl ∊ [0..3].
   7. load_shape(t, c, ls) in which t ∊ [1..10] e c ∊ [1..4] and ls ∊ [1..4].
   8. next_crc(t, c, x) in which t ∊ [1..10] and c ∊ [1..4] and x ∊ [-1..1], in which car c of
   train t has an adjacent car with loads in circle form.
   9. next_hex(t, c, x) in which t ∊ [1..10] and c ∊ [1..4] and x ∊ [-1..1], in which car c of
   train t has an adjacent car with loads in a hexagon shape.
   10. next_rec(t, c, x) in which t ∊ [1..10] e c ∊ [1..4] e x ∊ [-1..1], in which car c of train t
   has an adjacent car with rectangle loads.
   11. next_tri(t, c, x) in which t ∊ [1..10] e c ∊ [1..4] e x ∊ [-1..1], in which car c of train t
   has an adjacent car with triangle loads.

### Answer/How to run the code to solve this question.
Run the entire notebook (train_question1.ipynb) in the scripts folder, in sequence. All 11 concept models and the final meta network will be trained

## Question 2
Now the second question asks us to extend the first model in the following way:
> Extend your model to other types of cases as shown in Figure 2.,
describing the new predicates as in the previous question and train your model
as in the book example.
![question2-image](/Contextualization/question2.png)

### Answer/How to run the code to solve this question.
Run the entire notebook (train_question2.ipynb) in the scripts folder, in sequence. All 11 concept models and the final meta network will be trained

## Report
In the following link you can find the report containing some further theoretical background, explanation on the solution and code, besides some further exploration of the problem and solution proposed.
