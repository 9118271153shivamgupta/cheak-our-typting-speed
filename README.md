# cheak-our-typting-speed


from  time import time     # to record the time


# now to calculate the accuracy of input prompt
def tperror(prompt):
    global inwords

    words=prompt.split()
    errors=0
    for i in range(len(inwords)):
        if i in (0,len(inwords)-1):
            if inwords[i]==words[i]:
                continue
            else:
                errors+=1
        else:
            if inwords[i]==words[i]:
                if (inwords[i+1]==words[i+1]) and (inwords[i-1]==words[i-1]):
                    continue
                else:
                    errors+=1
            else:
                errors+=1
    return errors

    # now to calculate the speed of typing words per minits
def speed (inprompt, stime, etime):
    global time
    global inwords

    inwords =inprompt.split()
    twords=len(inwords)
    speed=twords/time
    
    return speed

#calculate the total elapsed time

def elapsedtime(stime,etime):
    time =etime-stime  # etime is the end time and stime is the start time


    return time


if __name__=='__main__':
    prompt = "polymorphism is one of the core concepts of object-oriented programming (OOP) and describes situations in which something occurs in several different forms. In computer science, it describes the concept that you can access objects of different types through the same interface."
# this was paragraph wich you can have to type to cheak your speed 
    print(" type this :-", prompt )

# cheaking  to input Entre basically it wil see
    input("press Enter when you are reeady to cheak your speed:  ")

    # recording the time
    stime =time()
    inprompt=input()
    etime=time()

    time=round(elapsedtime(stime,etime),2) #round of the time
    speed = speed(inprompt,stime ,etime)
    errors=tperror(prompt)

    #print all requried data 

    print("====================================================")
    print("total time elapsed: ", time , "second")
    print("Your average typing speed was  " ,speed , "word per minute(w/n)")
    print("with the total of ", errors , "error")
    print("====================================================")

                

