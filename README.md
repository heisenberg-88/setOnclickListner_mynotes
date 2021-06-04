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
   It is implemented internally in the java code as,
     
   ...
   ...
   ...
   
    public class TestClickListener implements OnClickListener{
      @override
      public void onCLick(View view){
        Test_function();
      }
      
    }
    
   internally the onClick() method is as above.
    
   we can use setonclicklistener by defining own function onClick() , by using interfaces
   # public static interface View.OnClickListener
   abstract void is onClick();
   interfaces are the classes which are not implemented
   -No state 
   -All methods are abstract(not implemented
   
   
   without using XML with android:onClick="Test_function()"
   we can use setOnClickListener,
   Create a java class file exampleClickListener.java in android project java folder
    
    ...
    ...
    ...
    
    public class exampleClickListener implements View.onClickListener {
      
      @override
      public void onClick(View view){
        ....
        ... ///// write the code you want to execute after pressing the button/View/onclick .
        ....
      }
    
    }
   
   
   Now use this in 'mainactivity.java' file
  because, we want to listen the onclick immediately after the app startup 
  in mainactivity.java file ,
  
    ...
    ...
    ...
    
    /// inside the main class of mainactivity
    
      @Override
      protected void onCreate(Bundle savedInstanceState) {
          super.onCreate(savedInstanceState);
          setContentView(R.layout.activity_main);
          
          /// Create a new object for exampleClickListener
          
          exampleClickListener objectForClickListener = new exampleClickListener();
          
          // Create the Object for the View on which we have to implement this clicklistener , here i'm taking TexView as an example
          
          TextView objforView = (TextView) findViewById(R.id.textview_id);
          
          // set clicklistener on that view (i.e. objforView in this example)
          // pass objectForClcikListener inside the setOnClickListener method
          
          objforView.setOnClickListener(objectForClcikListener);
          
          
      }
      
      
 ----------------------------------------------------------------------------
 ############################################################################
 
 Without typing these many lines, we can directly use onClickListener in the "mainactivity.java" file.
 
 => first change :
  without creating object, we can directly use it
  
  remove following line from above code
    
    exampleClickListener objectForClickListener = new exampleClickListener();
    
  use it directly inside setOnClickListener -
   
    objforView.setOnClickListener(new exampleClickListener());
    
    
  we can also directly define the onClick method in "mainactivity.java" file.
  first delete the "exampleClickListener.java" class file.
  
    ///// Inside the onCreate method ;
            
          ///// create the object for TextView.
          
          TextView objforView = (TextView) findViewById(R.id.textview_id);
          
          /// Set a clicklistener on that view
          
          objforView.setOnClickListener( new View.OnCLickListener {
          
              // The code in this method will be executed when the  View is clicked on.
              
              @override
              public void onClick(View view){
                  ...
                  ..  ///// write the code you want to execute after pressing the button/View/onclick .
                  .....
              }
          
          });
          
          
          
          
          
  
    
    
   
    
  
     
    
    
  
   
    
    
  
   
