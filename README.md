
    def __init__(self, name, money):
        self.name = name
        self.money = money
        self.level = 1

    def spin(self):
        result = random.randint(1, 100)
        multiplier = self.level * 2
        final_result = result * multiplier
        self.money += final_result
        print(f"{self.name} spun and won ${final_result}!")
        return final_result

    def increase_level(self):
        self.level += 1
        print(f"{self.name}'s level is now {self.level}.")

# Main game loop
def coin_master_game():
    player = Player("John", 1000000)

    while True:
        player.spin()
        print(f"{player.name}'s total money: ${player.money}")

        if player.money > 10000000:
            player.increase_level()
            print("\n\nLEVEL UP! You've reached a new level. Let's see how much more you can earn.\n\n")

        input("Press Enter to spin again. ")

coin_master_game()
