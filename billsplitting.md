# lHacks2018-1
int main(){
    char str1[20];
    int no;
    int arr[no];
    printf ("Enter number of roommates:");
    scanf ("%d", &no);
    printf ("Number of roommates: %d\n", no);
    for (int i=0; i<no-1; i++){
                arr[i]=0;
            }
    while (1){
        char question[5];
        printf ("Do you want to reset the code? ");
        scanf ("%s", question);
        printf ("%s\n", question);
        if (strcmp(question, "yes") == 0){
            printf ("Enter number of roommates:");
            scanf ("%d", &no);
            printf ("Number of roommates: %d\n", no);
            for (int i=0; i<no-1; i++){
                arr[i]=0;
            }
    }
        else{
            int person;
            printf ("Enter person that has paid the bill: ");
            scanf ("%d", &person);
            printf ("Person that paid the bill: %d\n", person);
            if (person>no && person<0)
                printf("This person does not exist");
            else {
                int price;
                printf ("Enter bill of the person: ");
                scanf ("%d", &price);
                printf ("%d\n", price);
                arr[person-1]+=price;
                printf("Amount of money the person paid: %d\n", arr[person-1]);
                int total=0;
                for (int i=0; i<no-1; i++){
                    total+=arr[i];
                }
                printf ("Total amount of money: %d\n", total);
                float avg = total/(float)no;
                printf ("Average: %.2f\n", avg);
                printf ("Enter person to read their status: ");
                int status;
                scanf ("%d", &status);
                printf ("%d\n", status);
                if (status>no && status < 0)
                    printf ("This person does not exist\n");
                else{
                    float tobepaid = arr[status-1]-avg;
                    printf ("%.f\n", tobepaid);
                }
            }
        }
    }
}
