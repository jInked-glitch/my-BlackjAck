import random

def blackjack():
    deal_card = {
        "A":[1,11],
        "2":2,
        "3":3,
        "4":4,
        "5":5,
        "6":6,
        "7":7,
        "8":8,
        "9":9,
        "10":10,
        "J":10,
        "Q":10,
        "K":10,
    }

    player_hand = random.choices(list(deal_card), k=2)
    dealer_hand = random.choices(list(deal_card), k=2)


    def calculate_score(hand): 
        score = 0
        ace_count = 0

        for card_player in hand:
            if card_player == "A":
                ace_count += 1
            else:
                score += deal_card[card_player]

        for _ in range(ace_count):
            if score + 11 <= 21:
                score += 11

            else:
                score += 1
        return score
    

    player_score = calculate_score(player_hand)
    dealer_score = calculate_score(dealer_hand)

    print(f"Player's hand: {player_hand}, Score: {player_score}")
    print(f"Dealer's first card: {dealer_hand[0]}")

    should_play = True
    if dealer_score == 21:
        if player_score == 21:
            print(f"Your cards:{player_hand}, current score: {player_score},"
                  f"Dealer cards:{dealer_hand}, current score: {dealer_score},Draw!")
        elif player_score != 21:
            print(f"Your cards:{player_hand}, current score: {player_score},"
                  f"Dealer cards:{dealer_hand}, current score: {dealer_score},you lose...")
        should_play = False

    elif dealer_score != 21:
        if player_score == 21:
            print("You hit 21! Moving to dealer's turn...")
            should_play = False

    while player_score < 21:
        continue_answer = input("Type 'y' to get another card, type 'n' to pass")
        if continue_answer == "y":
            new_card_player = random.choice(list(deal_card))
            player_hand.append(new_card_player)
            player_score = calculate_score(player_hand)
            print(f"Your cards:{player_hand}, current score: {player_score}")
            if player_score > 21:  
                print("You busted! You lose!")
                return
        elif continue_answer.lower() == "n":  
            break
        else:
            print("Invalid input. Please enter 'y' or 'n'.")  

    while dealer_score <= 16:
        new_card_dealer = random.choice(list(deal_card))
        dealer_hand.append(new_card_dealer)
        dealer_score = calculate_score(dealer_hand)
        if dealer_score > 21:  
            print(f"Dealer cards: {dealer_hand}, current score: {dealer_score}, Dealer busted! You win!")
            return
        elif dealer_score == 21:
            print(f"Dealer cards: {dealer_hand}, current score: {dealer_score}, Dealer got Black Jack, You lose...")
            return
        else:
            print(f"Dealer cards: {dealer_hand}, current score: {dealer_score}, getting another card")

    print(f"Dealer's final hand: {dealer_hand}, final score: {dealer_score}")

    if player_score > dealer_score:
        if player_score == 21:
            print("You got Black Jack, You win!")
        else:
            print("You win!")

    elif player_score < dealer_score:
        if dealer_score == 21:
            print("You got Black Jack, You lose...")
        else:
            print("You lose...")
    else:
        if dealer_score == 21 and player_score == 21:
            print("Both got Black Jack, it's draw!")
        else:
            print("It's a draw!")


while True:
    play_game = input("Do you want to play a game of Black Jack? Type 'y' or 'n': ")
    if play_game.lower() == "n":
        print("Thanks for playing! Goodbye!")
        break  
    elif play_game.lower() == "y":
        blackjack()  
    else:
        print("Invalid input. Please enter 'y' or 'n'.")  
