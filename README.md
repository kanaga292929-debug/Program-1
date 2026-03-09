#include<stdio.h>
#include<string.h>

struct item{
    char name[20];
    int qty;
    float price;
}cart[50];

int n=0;

int main(){
    int ch,i;
    float total=0;

    while(1){
        printf("\n1.Add 2.Remove 3.Update 4.Bill 5.Exit\n");
        scanf("%d",&ch);

        if(ch==1){
            scanf("%s%d%f",cart[n].name,&cart[n].qty,&cart[n].price);
            n++;
        }

        else if(ch==2){
            char name[20];
            scanf("%s",name);
            for(i=0;i<n;i++)
            if(strcmp(cart[i].name,name)==0)
                cart[i]=cart[n-1],n--;
        }

        else if(ch==3){
            char name[20];
            scanf("%s",name);
            for(i=0;i<n;i++)
            if(strcmp(cart[i].name,name)==0)
                scanf("%d",&cart[i].qty);
        }

        else if(ch==4){
            total=0;
            for(i=0;i<n;i++)
                total+=cart[i].qty*cart[i].price;
            printf("Total=%.2f",total);
        }

        else break;
    }
}
# Program-1
