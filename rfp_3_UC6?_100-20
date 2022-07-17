#!/bin/bash

IS_PART_TIME=1;
IS_FULL_TIME=2;
MAX_HRS_IN_MONTH=4;
EMP_RATE_PER_HR=20;
NUM_WORKING_DAYS=20;

totalEmpHours=0;
totalWorkingDays=0;

function getWorkHrs() {
   local $empCheck=$1
   case $empCheck in
      $IS_FULL_TIME)
         empHrs=8
               ;;
      $IS_PART_TIME)
         empHrs=4
               ;;
      *)
         empHrs=0
               ;;
   esac
echo $empHrs
}

function getEmpWage() {
	local empHr=$1
	echo $(($empHr*$EMP_RATE_PER_HR))
}

while [[ $totalEmpHours -lt $MAX_HRS_IN_MONTH && $totalWorkingDays -lt $NUM_WORKING_DAYS ]]
do
   ((totalWorkingDays++))
   empCheck=$((RANDOM%3));
   empHrs="$( getWorkHrs  $empCheck )"
   totalEmpHours=$(($totalEmpHours+$empHrs))
	dailyWage[$totalWorkingDays]="$( getEmpWage $empHrs )"
done

totalSalary=$(($totalEmpHours*$EMP_RATE_PER_HR));
echo "TOTAL EMPLOYEE HOURS=$totalEmpHours"
echo "TOTAL SALARY=$totalSalary"
echo "${dailyWage[@]}"
