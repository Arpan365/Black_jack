import random

legend=['Jack','King','Queen']
cards = [11,2,3,4,5,6,7,8,9,10,10,10]
# cards=[10,11]
Ace=[1,11]

#Function for summation of list
def replacement_to_int(cards1):
    replacement_int = 10
    converted_list=[]
    for items in cards1:
        if items in legend:
            index_to_replace = cards1.index(items)
            cards1[index_to_replace] = replacement_int
            converted_list.append(replacement_int)
        else:
            converted_list.append(items)
    return converted_list

#Function for taking taking legend in list
my_cards_fn=[]
def legend_inclusion(input_cards,my_cards_fn):
    my_card_fn=random.choice(input_cards)
    if my_card_fn==10:
        my_cards_fn.append(random.choice(legend))
    else:
        my_cards_fn.append(my_card_fn)


game_over=False
I_have=1000
while not game_over:
    deal=int(input("Enter the value to start a deal:  "))
    dollar_I_have=I_have-deal
    I_have=dollar_I_have
    print(dollar_I_have, end="\n ")
    if dollar_I_have!=0:
        print("Start Playing")
# making random choices of cards 
        my_cards=[]
        dealer_cards=[]
        for i in range(0,2):
            legend_inclusion(input_cards=cards,my_cards_fn=my_cards)
            legend_inclusion(input_cards=cards,my_cards_fn=dealer_cards)
        print(f"My modified cards are {my_cards} \n ")
        print([dealer_cards[0]], end="\n ")
        
#For Hit and Stand state for player
    condition=False
    while not condition:
        if sum(replacement_to_int(my_cards))==21 and len(my_cards)==2:
            print("B L A C K J A C K \n " )
            break
        player_choice=False
        while not player_choice:
            button=input("Write 'hit' to pick a card and 'stand' to terminate the picking :")
            print(f"your cards are {my_cards} and the summation of the cards is {sum(replacement_to_int(my_cards))} \n ")
            if button=="hit":
                print("Pick a card \n ")
                legend_inclusion(input_cards=cards,my_cards_fn=my_cards)
                item=11
                for item in my_cards:
                    if 11 in my_cards and sum(replacement_to_int(my_cards))>21:
                        my_cards.remove(11)
                        my_cards.append(1) 
                
                
                print(f"your cards are {my_cards} and the summation of the cards is {sum(replacement_to_int(my_cards))}\n ")
                
            if sum(replacement_to_int(my_cards))>21:
                print("Bust that means you lost \n ")
                break

            if button=="stand":
                print("You are standby now \n ")
                print(f"The dealer's cards are {dealer_cards} and the summation is {sum(replacement_to_int(dealer_cards))} \n ")
                player_choice=True
                dealer_choice=False
                while not dealer_choice:
                    infinite=False
                    while sum(replacement_to_int(dealer_cards))<17:
                        print("Dealer must pick a card \n ")
                        legend_inclusion(input_cards=cards,my_cards_fn=dealer_cards)
                        print(f"Dealer's card are {dealer_cards} \n ")

                    if sum(replacement_to_int(dealer_cards))>17:
                        infinite=True
                        if (sum(replacement_to_int(dealer_cards))>21):
                            print("Dealer Bust that means you win \n ")
                            dealer_choice==True
                        break
                        
                    

                    print(f"your cards are {my_cards} and the summation of the cards is {sum(replacement_to_int(my_cards))} \n ")
                    print(f"The dealer's cards are {dealer_cards} and the summation is {sum(replacement_to_int(dealer_cards))} \n ")


        if sum(replacement_to_int(my_cards)) >21:
            I_have+=0
            print(I_have , end="\n ")
            condition=True
            break

        if sum(replacement_to_int(dealer_cards)) >21:
            I_have+=2*deal
            print(I_have ,end="\n ")
            condition=True
            break  

        if sum(replacement_to_int(dealer_cards))<sum(replacement_to_int(my_cards)):
            I_have+=2*deal
            print(I_have,end="\n ")
            print("You win \n ")
            condition=True
            break
             
        if sum(replacement_to_int(dealer_cards))==sum(replacement_to_int(my_cards)):
            I_have+=deal
            print(I_have,end="\n ")
            print("Draw \n ")
            condition=True
            break
        if sum(replacement_to_int(dealer_cards))>sum(replacement_to_int(my_cards)):
            I_have+=0
            print(I_have,end="\n ")
            print("Dealer win \n ")
            condition=True
            break

            
            # print(f"your cards are {my_cards} and the summation of the cards is {sum(replacement_to_int(my_cards))}")
            # print(f"The dealer's cards are {dealer_cards} and the summation is {sum(replacement_to_int(dealer_cards))}")     
    
#Summation of List
    # my_cards1=replacement_to_int(my_cards)
    # dealer_cards1=replacement_to_int(dealer_cards)
    # print(sum(my_cards1))
    # print(sum(dealer_cards1))

    if dollar_I_have==0:
        print("Game Over \n  ")
        game_over==True