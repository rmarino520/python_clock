import sys
import time as t

'''
This is a simple clock
User selects standard or 24 hour clock 
User sets the hours and minutes

Clock is displayed and acts... like a clock
'''

# boolean values to increment the time
incrementMinutes = False
incrementHours = False

# boolean values to select the clock
twentyFour = False
standardClock = False

# boolean values for input checking
validHours = True
validMinutes = True
validClock = True

# max values
hoursMaxStd = 12
hoursMaxTf = 23
minutesMax = 59

# CLOCK CHOICE
clockChoice = input("Choose a clock \n1) Standard 2) 24 Hour: ")

# Keep asking for correct input
while validClock:

    # Check if string input is a digit
    if str.isdigit(clockChoice):

        # Cast the string to an int
        clockChoice = int(clockChoice)

        # Determine clock choice
        if 1 == clockChoice:
            standardClock = True
            validClock = False
        elif 2 == clockChoice:
            twentyFour = True
            validClock = False
    else:
        clockChoice = input("Choose a valid choice (1 or 2): ")

# SET HOURS
hours = input("Enter hours: ")

# Same concept as above: keep asking until valid input
while validHours:

    if str.isdigit(hours):
        hours = int(hours)

        if standardClock:
            if -1 >= hours or hoursMaxStd < hours:
                hours = input("Input valid hours (1-12): ")

            elif 10 > hours:
                # Cast minutes back to a string and add a zero to the front
                hours = str(hours)
                hours = '0' + hours
                validHours = False

        else:
            if -1 >= hours or hoursMaxTf < hours:
                hours = input("Input valid hours (1-23): ")

                if str.isdigit(hours):
                    hours = int(hours)

            elif 10 > hours:
                # Cast minutes back to a string and add a zero to the front
                hours = str(hours)
                hours = '0' + hours
                validHours = False

    else:
        hours = input("Input valid hours (1-12): ")

# SET MINUTES
minutes = input("Enter minutes: ")

# Same concept as above: keep asking until valid input
while validMinutes:

    if str.isdigit(minutes):
        minutes = int(minutes)

        if -1 >= minutes or 59 < minutes:
            minutes = input("Input valid minutes (0-59): ")

        elif 10 > minutes:
            minutes = str(minutes)
            minutes = '0' + minutes
            validMinutes = False

        else:
            validMinutes = False

    else:
        minutes = input("Input valid minutes (0-59): ")

# Add space in output
print()

# Clock processing
while True:
    for seconds in range(1, 61):
        if standardClock:
            if incrementHours:
                hours = int(hours)
                hours += 1
                incrementHours = False
                if hoursMaxStd < hours:
                    hours = 1
                    hours = str(hours)
                    hours = '0' + hours
                elif 10 > hours:
                    hours = str(hours)
                    hours = '0' + hours
        else:
            if 0 == hours:
                hours = str(hours)
                hours = '0' + hours
            if incrementHours and 23 != hours:
                hours = int(hours)
                hours += 1
                incrementHours = False
                if hoursMaxTf < hours:
                    hours = 0
                    hours = str(hours)
                    hours = '0' + hours
                elif 10 > hours:
                    hours = str(hours)
                    hours = '0' + hours
            elif incrementHours and 23 == hours:
                hours = 0
                hours = str(hours)
                hours = '0' + hours
                incrementHours = False

        if incrementMinutes:
            minutes = int(minutes)
            minutes += 1
            incrementMinutes = False
            if minutesMax <= minutes:
                minutes = '00'
            elif 10 > minutes:
                minutes = str(minutes)
                minutes = '0' + minutes

        if 60 == seconds:
            sys.stdout.write("\r" + str(hours) + ':' + str(minutes) + ':' + '00')
            sys.stdout.flush()
            t.sleep(1)
        elif 10 > seconds:
            sys.stdout.write("\r" + str(hours) + ':' + str(minutes) + ':' + '0' + str(seconds))
            sys.stdout.flush()
            t.sleep(1)
        elif 59 > seconds:
            sys.stdout.write("\r" + str(hours) + ':' + str(minutes) + ':' + str(seconds))
            sys.stdout.flush()
            t.sleep(1)
        elif 59 == seconds:
            if 59 == minutes:
                sys.stdout.write("\r" + str(hours) + ':' + str(minutes) + ':' + str(seconds))
                sys.stdout.flush()
                t.sleep(1)
                incrementMinutes = True
                incrementHours = True
            else:
                sys.stdout.write("\r" + str(hours) + ':' + str(minutes) + ':' + str(seconds))
                sys.stdout.flush()
                t.sleep(1)
                incrementMinutes = True
