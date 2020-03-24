# Sock-Merchant-Problem
John works at a clothing store. He has a large pile of socks that he must pair by color for sale. Given an array of integers representing the color of each sock, determine how many pairs of socks with matching colors there are.  For example, there are n=7 socks with colors ar=[1,2,1,2,1,3,2] . There is one pair of color 1  and one of color 2 . There are three odd socks left, one of each color. The number of pairs is 2.


# Function explained:
There are two counters used mainly, count and temp; After we apply the command Arrays.sort(), the values in array look something like [1,1,1,2,2,2,3]. Now temp keeps a count of how many times colors of a kind come together. 
Since we need a total of how many pairs of socks are present, we do- count=count+(temp/2)

static int sockMerchant(int n, int[] arr) {
        int count=0;
        Arrays.sort(arr);
        for(int i=0;i<n;i++){
            int temp=1;
            while((i<n-1)&&(arr[i]==arr[i+1])){
                temp=temp+1; 
                i++;             
            }
            count=count+(temp/2);
        }
        return count;
    }
