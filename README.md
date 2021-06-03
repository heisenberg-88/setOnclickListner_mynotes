# setOnclickListner_mynotes
easy explanation for setonclicklistner
# These are my notes

android:onClick in XML & onClick using interfaces in android works same

=> android:onClick is implemented as follows:
  
    <Button
    android:id="@+id/buttonTest"
    android:layout_height = "wrap_content"
    android:layout_width ="wrap_content"
    android:text = "Test Button"
    android:onClick = "Test_function"
    />
    
   here, when the "Test Button" is pressed , "Test_function" is executed from  'mainactivity.java' 
   It is implemented internally in the java code as;
     
   ...
   ...
   ...
   
    public class TestClickListener implements OnClickListener{
      @override
      public void onCLick(View view){
        Test_function();
      }
      
    }
   
