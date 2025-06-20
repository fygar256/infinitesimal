# infinitesimal

infinitesimal.py

A simulation program that considers infinitesimals using rock-paper-scissors

When two people play rock-paper-scissors, the outcome is either you win, the other person wins, or it's a tie.

These three cases occur with an equal probability of 1/3.

In the case of a tie, if you play rock-paper-scissors until a winner is decided,

lim n→∞ Π(i=1,n)1/3=0

and the possibility of never being able to decide is 0 in the limit formula, but such cases do exist and the probability can be said to be infinitesimal.

At the end of the Book of Revelation it says, "Behold, I am coming quickly," but there is a possibility that Christ will not come even if you wait forever.

This problem also exists when using random numbers to determine the server and client of two equivalent computers in network communication. When trying to determine with random numbers, this problem is strictly unsolvable because the computer is a black box, but if you try a sufficient number of times, it is sufficient for practical purposes.

This problem can be solved by using identities such as CPU ID and IP address.

Once you know the IP address, you can send a ping and, if you get a response, you'll know that the other party is connected. Then you can decide who will be the server and who will be the client.

Deciding who will be the server and who will be the client is the same as deciding who goes first and who goes second in a network game.

If you need the IDs of multiple players, you can use the CPU ID or the size relationship of IP addresses.

I was reading a book about the Internet and it said that a computer would roll dice, but I'm not sure if that's what it means.

## Verification program

uses truerand.py module

https://github.com/fygar256/truerandom


```infinitesimal.py
#!/usr/bin/python3
import truerand
te=[ 'Paper','Scissors','Rock' ]
def game(a,b):
    if a=='Paper':
        if b=='Paper':
            return 'draw'
        elif b=='Scissors':
            return 'lose'
        else:
            return 'win'
    elif a=='Scissors':
        if b=='Paper':
            return 'win'
        elif b=='Scissors':
            return 'draw'
        else:
            return 'lose'
    else: # a=='Rock'
        if b=='Paper':
            return 'lose'
        elif b=='Scissors':
            return 'win'
        else:
            return 'draw'

def main():
    while True:
        self=te[truerand.rand(1)%3]
        opp=te[truerand.rand(1)%3]
        result=game(self,opp)
        print(f"Self:{self} Opponent:{opp} Result:{result}")
        if result=='draw': # Tie
            continue
        break

if __name__=="__main__":
    main()
```
