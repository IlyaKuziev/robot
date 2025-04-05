class RobotAthlete_01012025
event RewardAssigned(address indexed user, uint256 amount);
event RewardClaimed(address indexed user, uint256 amount);

constructor(address _rewardToken) {
    rewardToken = IERC20(_rewardToken);
}

function assignReward(address user, uint256 amount) external onlyOwner {
    rewards[user] += amount;
    emit RewardAssigned(user, amount);
}

function claimReward() external {
    uint256 amount = rewards[msg.sender];
    require(amount > 0, "No rewards available");
    require(rewardToken.balanceOf(address(this)) >= amount, "Not enough rewards in contract");
    
    rewards[msg.sender] = 0;
    rewardToken.transfer(msg.sender, amount);
    
    emit RewardClaimed(msg.sender, amount);
}

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
