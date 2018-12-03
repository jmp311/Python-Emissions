# Python-Emissions
Emission Calculation using pythong
# This code uses python to calculates the emissions of a car over a year dependent on variables likes MPG, CO2 emissions and more.


# initialize global variables
POUNDS_CO2_PER_GALLON = 19.4

def yearly_miles_driven(work_distance,days_per_week):
    # declare variables
    miles_per_day = 0.0
    miles_per_year = 0.0
    # compute miles/year
    weeks_per_year = 52
    miles_per_day = work_distance * 2
    miles_per_year = miles_per_day * days_per_week * weeks_per_year
    # return miles/year
    return miles_per_year

def gallons_per_year(mpy,mpg):
    # declare variables
    gallons_per_year = 0.0
    
    # compute gallons/year
    gallons_per_year = mpy / mpg
    # return gallons/year
    return gallons_per_year

def emissions_per_year(gpy):
    #declare variables
    CO2_per_year = 0.0
    #compute CO2 emissions/year
    CO2_per_year = gpy * POUNDS_CO2_PER_GALLON
    #return CO2 emissions/year
    return CO2_per_year
    
# define main function
def main():
    # declare variables
    work_distance = 0.0
    mpg = 0.0
    days_per_week = 0.0
    miles_per_year = 0.0
    # get input
    work_distance = float(input('What is the distance to your job?'))
    if work_distance == 0:
        print('Distance to work must be greater than 0!')
        work_distance = float(input('What is the distance to your job?'))
    mpg = float(input('How many miles per gallon does your car get?'))
    if mpg == 0:
        print('Miles per gallon must be greater than 0!')
        mpg = float(input('How many miles per gallon does your car get?'))        
    days_per_week = int(input('How many days a week do you work?'))
    if days_per_week == 0:
        print('You must input a value greater than 0!')
        days_per_week = int(input('How many days a week do you work?')) 
    # call functions
    mpy = yearly_miles_driven(work_distance,days_per_week)
    gpy = gallons_per_year(mpy,mpg)
    epy = emissions_per_year(gpy)
    
    # output
    print()
    print('Carbon Dioxide Emissions per Year','\n',\
          '-------------------------------','\n',\
          '    ',format(epy,'.1f'),'lbs/gallon')
main()



