# Minutes of Meetings

Maintained by: Amir Nurmukhambetov (1930907)

## Fifth Meeting [30 Apr 2024]

Today we discussed the privoted idea with Georgi and it was approved with some slight modifications (renaming things etc).

Balint got the motor and servo working with PWM and continuous motion. After which he started writing documentation on his work. It can be found on this [repo](https://github.com/2IO75-group-34/friendly-guacamole)

Eusebiu and Alexia completed the backlog.

I (Amir) and Joep worked on redesigning the robot so that it was more realistic in scale and used less parts. This allowed us to have a better understanding of what parts we need.

![Redesigned Idea](./images/redesigned-idea.png)

Joep, Balint, Amir, and Eusebiu started working on making a prototype design for the conveyer belt.

![Conveyer belt in progress](./images/conveyer-belt-in-progress.jpeg)

After which Eusebiu recorded a pitch video demonstration of our idea.

- [Youtube link](https://www.youtube.com/watch?v=dQw4w9WgXcQ)

## Fourth Meeting [29 Apr 2024]

Georgi has notified us that the idea **Hangman** doesn't represent a airport baggage system. We have pivoted the idea towards **baggage screening control system**.

![](./images/baggage-screening-control-sytem.png)

The basic premise of this idea is that the baggages are checked for their content. If the system detects a malliscious item then it gets flagged and is sent to the other team (or placed into flagged box). If the baggage is good, it get sorted into to classes: business and economy. If the bag is special it is considered to be personale baggage.

Balint got the LED to work with the raspberry pi and arduino board. Motors and servos are in process, the current issue that we are facing is that the power for them are not compatible with the arduino board and raspberry pi.

Joep, Eusebiu and Alexia worked on filling out the backlog.

## Third Meeting [26 Apr 2024]

- Everyone has done scrum quiz.

- Eusebiu and Alexia started to document scrum planning. While everyone suggests their thought.

- We have decided on tackle these challanges:
  - Simulation-in-the-loop testing and digital twinning
  - Communication protocols

- Everyone worked on filling out the rubric (based on the challanges mentioned above).

- Mentor agreed on idea **Hangman**

We brought the parts from the locker to play with it. Balint decided to start to configure arduino board to work with the raspberry pi so that the motors work. The rest watched a video showcasing how to connect and assemble FischerTechnik pieces.

Video(s):

- [How to Use FischerTechnik Systems](https://www.youtube.com/watch?v=OtKxWEv9YuA)

At the end, Balint took raspberry pi and arduino board home to work on it in more. I (Amir) took all pieces to see whats possible and how viable our idea. Eusebiu and Alexia decided to start learning how to 3D model.

## Second Meeting [24 Apr 2024]

Went through ideas:

### Binary Addition

**Init idea:**

two sequences of baggages representing each number are added and the result is displayed as a sequence of baggages. Then its get sorted.

**Possible issues:**

- How do we determine when the sequence is stopped for a certain number?
  - **Solution(s):**
  - A set sequence of 8bit would be inputted.
  - If no baggage is received for after a certain threshold then it is considered as black = 0.
  - We won't limit ourselves to two numbers, any amount can be possible.

- A situation may occur where the number of white or black baggages are not enough to represent the summed result.
  - **Solution(s):**
  - Display the result using an LED screen display.

- How do we resolve if the baggages arrive too quickly? More specifically they are clustered and the space in between each baggage is different.
  - **Solution(s):**
  - Don't disturb the sequence make sure the **color reader** is fast enough to determine bit.

- Since the reviewer doesn't control the input the sequence is random. And so the result of addition can't be controlled.
  - **Solution(s):**
  - Before adding the sequence display the number that the 8bit chunk represents.

**Revised edition:**

Robot that reads a sequence of baggages in white/black. Each bag represents a bit either 1 or 0 depending on its color. A sequence is split in 8bit chunks and all are summed. The result is displayed on a LED screen display, and latest number added is shown. After processing the bagges are sorted by color.

### Alphabet Sorter

**Init idea:**

A sequence of baggages with english letters on each are inputted. The robot determines which letter is on each baggage after which stores is in a basket for a specific letter. The user would input the word they would like to display, after which the robot would output baggages with letters in a specific order such that the sequence shows the text user inputted.

**Possible issues:**

- The english alphabet contains 26 letters, this would involve 26 containers for storage, this would take too much space.
- The robot must be autonamous, but this has a user prompt in the middle of the task, which is not allowed.
- What happens if the baggage doesn't contain a letter, or contains a symbol that the storage can't be place.

### HangMan

![hangman image demo](./images/hangman.jpeg)

**Init idea:**

A sequence of baggages with english letters on each. A robot determines the letter on a bag. A screen display of the hangman game. The determined letter is checked if its contained in the word choosen, if true then the baggages are sorted by color, else if the letter is not in the word, the robot ignores them.

**Possible issues:**

- How do we determine the word for the hangman game? What happens if the word is guessed correctly?
  - **Solution(s):**
  - The robot contains a word pool from which it selects randomly.
- How to handle letters that can't be recognized?
  - **Solution(s):**
  - The baggage is set as not in word.
  - Perhaps the robot could display a recognition percentage. Showing how likely it thinks that the letter on the bag is a certain letter.

### Connect Random 4

![connect random 4 demo](./images/connect-random-4.jpeg)

**Init idea:**

A sequence of baggages colored black and white is inputted. The robot sorts them by color (white / black). A robot and a player play connect 4 game against each other using sortted pieces.

**Possible issues:**

- For the robot to be autonamous no user be present. Therefore user player cannot exist.
  - **Solution(s):**
  - Instead of user against robot. Its gonna be robot against robot.

- How we determine where the robot places its piece?
  - **Solution(s):**
  - For simplicity sakes, the robot randomly plays using a peg board.

- How do we determine the game has ended?.
  - **Solution(s):**
  - A camera looking at the board determines what game state we are in currently.

- What happens when the game is over.
  - **Solution(s):**
  - A convayer belt below picks all baggages after the lever (to drop all pieces) is pushed.

**Revised idea:**

A sequence of baggages colored white and black are inputted. A basic sorter sorts them by white and black. Player 1 (user) uses white baggage as pieces. Player 2 (robot) uses black baggages as pieces. Both play a connect 4 game using a peg board. This makes the input to the game random.

**Alternatively:**

Instead of having user play with white baggages. Have both random robots play against each other.

### Other ideas

Other ideas were discussed but weren't relevant enough to be written here.

## First Meeting [23 Apr 2024]

We chatted with neigbouiring group 33. We decided to work with for now but the whole group hasn't yet decided.

We created a github repository for managing all documents, like decision list, minutes, and logbooks. And added all team members.

We started to brainstorm ideas:

**ideas:**

- [ ] **NFC tagged baggage**. Where NFC indicates where the baggage should go. Similar to how baggage is transported do different planes.
- [x] **Weight sorting**. Customized baggage with different weight distrubtion, based on it sort them.
- [x] **Main brain system**. A system which dictates other sub-subsystems adjacent to it.
- [x] **Morse code ouput**. A robot that outputs baggage in a way to display morse code.
- [ ] **Rotating table of baskets**.
- [x] **Water convayerbelt**. Have boats that transport baggages.
- [x] **Binary Addition**. Inputting in a black/white baggages in coresponding way outputs a result of addition in binary.
- [x] **Lost & Found Storage**. Sort baggages in some way and using vertical space as storage (done via elevator)
- [x] **Carwash**. A robot sorts baggage into clean and dirty. Then all dirty baggages are getting cleaned like a carwash.
- [x] **Platics warpper**. From NFC those baggages that are type wrap are wrapped and then sorted somewhere else.
- [x] **Alphabet sorter**. Each baggage has a letter assigned the robot sorts by letter then from user input outputs the correct text. This idea can be extended to work with the other group that manages storage related functionality.

**Possible cool features that can be implemented:**

- Screen display feature, to show users any addition
- Using NFC we can store more detailed information about the baggage.
- Elevator, Catapult, Zipline.

- Scrum Masters were decided:
  - Eusebiu Puşcă
  - Alexia Miliganu
