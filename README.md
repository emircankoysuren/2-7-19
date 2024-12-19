#include <stdio.h>
#include <string.h>
int main(void)
{
     FILE * kalori = fopen("C:\\project\\txtdosyalari\\kalori.txt", "r");
    FILE * siparis= fopen("C:\\project\\txtdosyalari\\siparis.txt", "r");
    if(kalori == NULL)
    {
       
   printf("Dosya acilikren hata aldi");
        return -31;
    }
    if(siparis == NULL)
    {
      
  }
  

   char kalori_string[100][20];
    float kalori_float[100];
    char siparis_string[100][20];
    float siparis_float[100];
    float toplam =0;
    int i=0;
    do
    {
        fscanf(kalori, "%s", kalori_string[i]);
        fscanf(kalori, "%f", &kalori_float[i]);
        i++; // kalori dosyasındaki öğelerin sayacını tutar.

  } while(!feof(kalori)); 

   int j=0; 
    do
    {

       

  fscanf(siparis, "%s", siparis_string[j]);
       fscanf(siparis, "%f", &siparis_float[j]);
     j++;
    }while(!feof(siparis));

   for(int k=0;k<j;k++)
    {
        for(int l=0;l<i;l++)
        {
           

           

  if(stricmp(siparis_string[k],kalori_string[l])==0)
            {
                
   toplam=toplam+siparis_float[k]*kalori_float[l];
            }

        }
    }
   

   printf("Siparisiniz Toplam %0.3f kaloridir.",toplam);

   
   fclose(siparis);
    fclose(kalori);
    return 0;
}
