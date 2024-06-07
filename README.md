#include<stdio.h>

#define SHAREHOLDER_COUNT

#define SHAREHOLDER1 "KRISH" 
#define SHAREHOLDER2 "AARYAN"
#define SHAREHOLDER3 "JACKSON"
#define SHAREHOLDER4 "KRIESTIAN" 
#define SHAREHOLDER5 "ARIANA" 
#define SHAREHOLDER6 "GWEN T HOLSON" 

int votesCount1=0, votesCount2=0, votesCount3=0, votesCount4=0, votesCount5=0, votesCount6=0, spoiledtvotes=0;

void castVote()
{
int choice;    
printf("\n\n ### Please choose your SHAREHOLDER Candidate ####\n\n");
printf("\n 1. %s", SHAREHOLDER1);
printf("\n 2. %s", SHAREHOLDER2);
printf("\n 3. %s", SHAREHOLDER3);
printf("\n 4. %s", SHAREHOLDER4);
printf("\n 5. %s", SHAREHOLDER5);
printf("\n 6. %s", SHAREHOLDER6);
printf("\n 7. %s", "None of These");

printf("\n\n Input your choice (1 - 6) : ");
scanf("%d",&choice);

switch(choice){
    case 1: votesCount1++; break;
    case 2: votesCount2++; break;
    case 3: votesCount3++; break;
    case 4: votesCount4++; break;
    case 5: votesCount5++; break;
    case 6: votesCount6++; break;
    case 7: spoiledtvotes++; break;
    default: printf("\n Error: Wrong Choice !! Please retry");
             //hold the screen
             getchar();
}
printf("\n YOU VOTED YOUR CANDIDATE SUCCESSFULLY !!");
}

void votesCount(){
printf("\n\n ##### Voting Statics ####");
printf("\n %s - %d ", SHAREHOLDER1, votesCount1);
printf("\n %s - %d ", SHAREHOLDER1, votesCount2);
printf("\n %s - %d ", SHAREHOLDER1, votesCount3);
printf("\n %s - %d ", SHAREHOLDER1, votesCount4);
printf("\n %s - %d ", "Spoiled Votes", spoiledtvotes); 
}

void getLeadingSHAREHOLDER(){
    printf("\n\n  #### Leading SHAREHOLDER ####\n\n");
    if(votesCount1>votesCount2 && votesCount1>votesCount3 && votesCount1 >votesCount4 && votesCount1>votesCount5 && votesCount1>votesCount6 )
    printf("[%s]",SHAREHOLDER1);
    else if (votesCount2>votesCount3 && votesCount2>votesCount4 && votesCount2>votesCount5 && votesCount2>votesCount6 && votesCount2 >votesCount1)
    printf("[%s]",SHAREHOLDER2);
    else if(votesCount3>votesCount4 && votesCount3>votesCount5 && votesCount3>votesCount6 && votesCount3>votesCount1 && votesCount3 >votesCount2) 
    printf("[%s]",SHAREHOLDER3);
    else if(votesCount4>votesCount5 && votesCount4>votesCount6 && votesCount4>votesCount1 && votesCount4>votesCount2 && votesCount4 >votesCount3)
    printf("[%s]",SHAREHOLDER4);
    else if(votesCount5>votesCount6 && votesCount5>votesCount1 && votesCount5>votesCount2 && votesCount5>votesCount3 && votesCount5 >votesCount4)
    printf("[%s]",SHAREHOLDER5);
    else if(votesCount6>votesCount1 && votesCount6>votesCount2 && votesCount6>votesCount3 && votesCount6>votesCount4 && votesCount6 >votesCount5)
    printf("[%s]",SHAREHOLDER6);
    else
    printf("----- Warning !!! No-win situation----");   
}

int main()
{
int i;
int choice;

do{
printf("\n\n ###### Welcome to GENERAL MANAGER SELECTION #####");
printf("\n\n 1. Cast your Vote");
printf("\n 2. Find Vote Count");
printf("\n 3. Find leading Candidate");
printf("\n 0. Exit");

printf("\n\n Please enter your Shareholder choice : ");
scanf("%d", &choice);

switch(choice)
{
case 1: castVote();break;
case 2: votesCount();break;
case 3: getLeadingSHAREHOLDER();break;
default: printf("\n Error: Invalid Choice");
}
}while(choice!=0);

//hold the screen
getchar();

return 0;
}
