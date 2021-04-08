import queue
def createMaze():
    maze = []
    maze.append([" "," ","S"])
    maze.append([" ", "#", " "])
    maze.append(["E", " ", " "])
    return maze

def createMaze2():
    maze = []
    maze.append(["#", "#", "#", "#", "#", "S", "#", "#", "#"])
    maze.append(["#", " ", " ", " ", " ", " ", " ", " ", "#"])
    maze.append(["#", " ", "#", "#", " ", "#", "#", "#", "#"])
    maze.append(["#", " ", "#", " ", " ", " ", "#", " ", "#"])
    maze.append(["#", " ", "#", " ", "#", " ", "#", " ", "#"])
    maze.append(["#", " ", "#", " ", "#", " ", "#", " ", "#"])
    maze.append(["#", " ", "#", " ", "#", " ", "#", " ", "#"])
    maze.append(["#", " ", " ", " ", " ", " ", " ", " ", "#"])
    maze.append(["#", "#", "#", "#", "#", "#", "#", "E", "#"])

    return maze


def findExit(maze,s,moves):
    c = s[1]
    r = s[0]
    for move in moves:
        if move == "L":
            c -= 1
        elif move == "R":
            c += 1
        elif move == "U":
            r -= 1
        elif move == "D":
            r += 1
    if maze[r][c]=="E":
        print("Found: " + moves)
        printMaze(maze,s,moves)
        return True
    return False

def valid(maze,s,moves):
    c = s[1]
    r = s[0]
    for move in moves:
        if move=="L":
            c -=1
        elif move=="R":
            c+=1
        elif move=="U":
            r-=1
        elif move=="D":
            r+=1
        if not(0<=c<len(maze) and 0<=r<len(maze)):
            return False
        elif (maze[r][c]=="#"):
            return False
    return True

def printMaze(maze,s,path=""):
    c = s[1]
    r = s[0]
    pos = set()
    for move in path:
        if move == "L":
            c -= 1
        elif move == "R":
            c += 1
        elif move == "U":
            r -= 1
        elif move == "D":
            r += 1
        pos.add((r,c))
    for r,row in enumerate(maze):
        for c,col in enumerate(row):
            if(r,c) in pos:
                print("+ ",end="")
            else:
                print(col + " ",end="")
        print()
#Main application
maze = createMaze2()
q = queue.Queue()
q.put("")
path = ""
s= [0,5]
while not findExit(maze,s,path):
    path= q.get()
    for m in ["L","R","U","D"]:
        add = path + m
        if valid(maze,s,add):
            q.put(add)


