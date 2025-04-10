he World Trade Center towers stand tall against a clear, bright blue morning sky. Streets bustle with pedestrians in suits, and yellow taxis move slowly through heavy traffic. Sunlight reflects sharply from glass windows of nearby buildings. Tom, the blue-gray cat, walks briskly along the wide gray sidewalk with a single black briefcase in his hand.<end_scene>
<start_scene>Inside the World Trade Center lobby, expansive marble floors reflect warm golden recessed lighting. Gray marble pillars and brass fixtures highlight the elegant entryway, along with a brass elevator door. A uniformed doorman wearing a dark navy-blue suit stands behind a polished wooden counter. Tom, the blue-gray cat, with a single black briefcase in his hand calmly walks in from the right and approaches the elevator doors. Tom's left hand is empty.
Inside the World Trade Center lobby, expansive marble floors reflect warm golden recessed lighting. Gray marble pillars and brass fixtures highlight the elegant entryway, along with a brass elevator door. A uniformed doorman wearing a dark navy-blue suit stands behind a polished wooden counter. Tom, the blue-gray cat, has a single black briefcase in his hand slowly presses the elevator button on the left side of the elevator and waits. Tom's left hand is empty.<end_scene>

31vmarch:
    def __init__(self, name):
        self.name = name
        self.energy = 100
    def run(self, distance):
        if self.energy >= distance * 2:
            self.energy -= distance * 2
            print(f"{self.name} пробежал {distance} метров. Осталось энергии: {self.energy}")
        else:
            print(f"{self.name} устал и не может бежать.")

    def jump(self, height):
        if self.energy >= height * 5:
            self.energy -= height * 5
            print(f"{self.name} прыгнул на {height} метров. Осталось энергии: {self.energy}")
        else:
            print(f"{self.name} устал и не может прыгать.")

    def throw_ball(self, distance):
        if self.energy >= distance:
            self.energy -= distance
            print(f"{self.name} бросил мяч на {distance} метров. Осталось энергии: {self.energy}")
        else:
            print(f"{self.name} устал и не может бросать мяч.")

    def recharge(self):
        self.energy = 100
        print(f"{self.name} восстановил энергию!")

# Пример использования
robot = RobotAthlete("Спортбот")
robot.run(10)
robot.jump(3)
robot.throw_ball(15)
robot.recharge()
robot.run(20)
