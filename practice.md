- 快排(时间复杂度nlog(n))

  ```java
  /**
  *  
  *
  **/
  public class Sort{
  public static void quickSort(int[] arr,int low,int high) {
    int left = low;
    int right = high;
    //temp就是基准位
    int temp = arr[low];
    if(low>high){
      return;
    }
    while (left<right) {
      //先看右边，依次往左递减
      while (temp<=arr[right]&&left<right) {
        right--;
      }
      //再看左边，依次往右递增
      while (temp>=arr[left]&&left<right) {
        left++;
      }
      //如果满足条件则交换
      if (left<right) {
        int t = arr[right];
        arr[right] = arr[left];
        arr[left] = t;
      }
    }
    //最后将基准为与left和right相等位置的数字交换
    arr[low] = arr[left];
    arr[left] = temp;
    //递归调用左半数组
    quickSort(arr, low, right-1);
    //递归调用右半数组
    quickSort(arr, right+1, high);
  }
  
    
  public static void quickSort(int[] arr, int high, int low){
    int left = low;
    int right = high;
    int temp = arr[low];
    if(low>high){
      return;
    }
    while(left < right){
      while(left < right && arr[right] >= temp){
        right--;
      }
      while(left < right && arr[left] <= temp){
        left++;
      }
      if(left < right){
        swap(arr[left],arr[right]);
      }
    }
    swap(arr[low],arr[right]);
    quickSort(arr,low,right-1);
    quickSort(arr,right+1,high);
  }
  
  public static void swap(int a, int b){
    int temp = a;
    a = b;
    b = temp;
  }
  ```

- 冒泡排序

  ```java
  public static void bubble(int[] arr){
    for(int i=0;i<arr.length-1;i++ ){
      for(int j=0;j<arr.length-1-i;j++){
        if(arr[j]>arr[j+1]){
          swap(arr[j],arr[j+1]);
        }
    	}
    }
    
    
  }
  ```

  ```java
  public class Test{
    public static void heapSort(arr,low,high){
      int[] heapArray = createHeap(arr);
      for(int i=heapArray.length-1;i>=0;i--){
        swap(heapArray[0],heapArray[i]);
        ajust(heapArray,0,i);
      }
    }
    public static int[] createHeap(int a[], int k) {
      int[] heapArray = new int[k];
      for (int i = 0; i < k; i++) {
        heapArray[i] = a[i];
      }
      //完全二叉树的数组表示中，下标小于等于result.length / 2 - 1才有子节点
      for (int i = heapArray.length / 2 - 1;i >= 0;i--){
        heapify(i,heapArray);
      }
      return heapArray;
    }
    public static void ajustHeap(int[] arr, int node, int length)
      int left = 2*node + 1;
      int right = 2*node + 2;
      int smallest = node;
      if(arr[left] < arr[smallest] && left < length){
        smallest = left;
      }
      if(arr[right] < arr[smallest] && right < length){
        smallest = right;
      }
      if(smallest == node){
        return;
      }else{
        swap(arr[node],arr[smallest]);
        ajustHeap(arr,smallest)
      }
  }
  ```
  
  ```java
  public class Test{
    public static void pre(TreeNode root){
      if(root == null){
        return;
      }
      System.out.println(root.val)
      pre(root.left);
      pre(root.right);
    }
    
  }
  class TreeNode{
      int val;
      TreeNode left;
      TreeNode right;
    }
  ```
  
  ```java
  public class Test{
    public static void layer(TreeNode root){
      if(root == null){
        return;
      }
      System.out.println(root.val)
  
    }
    
  }
  class TreeNode{
      int val;
      TreeNode left;
      TreeNode right;
    }
  ```
  
  

