# Dynamin-memory-allocation-
```
#include <stdio.h>
#include <stdlib.h>
struct student
{
    char name[100];
    int id;
    int mark;
};
int main()
{
    struct student *s=NULL;
    int choice,count=0;
    while(1)
    {
        printf("=====STUDENT MANAGEMENT=====\n");
        printf("1) ADD STUDENT\n");
        printf("2) VIEW ALL STUDENT\n");
        printf("0) EXIT\n");
        scanf("%d",&choice);
        if (choice==1)
        {
            count++;
            s=(struct student*)realloc(s,count*sizeof(struct student));
            if (s == NULL)
            {
                printf("Memory allocation failed!\n");
                return 1;
            }
            printf("ENTER STUDENT NAME : \n");
            scanf(" %[^\n]", s[count-1].name);
            printf("ENTER STUDNET ID : \n");
            scanf("%d",&s[count-1].id);
            printf("ENTER STUDENT MARK : \n");
            scanf("%d",&s[count-1].mark);
            printf("Student added successfully!\n");
        }    
        else if (choice==2)
        {
            if (count==0)
                printf("NO STUDENT RECORD\n");
            else 
            {
                for (int i=0;i<count;i++)
              {
                printf("\nStudent %d\n", i+1);
                printf("Name  : %s\n", s[i].name);
                printf("ID    : %d\n", s[i].id);
                printf("Marks : %d\n", s[i].mark);
              }
            }
        }  
        else if (choice==0)
        {
            free(s);
            printf("=====PROGRAM END=====\n");
            exit(0);
        }
    }
}
```
## OUTPUT
<img width="1872" height="856" alt="1" src="https://github.com/user-attachments/assets/71bcd809-5e69-4cc1-84c4-4bf737f8029e" />
