# FinalGroup3
Scott Neale's C# Group 3 project App
We can start coding here so that we can all add comments and see each others work. This took me a while, but click on the little computer to the right of the read me file. then it will open a box and start coding. If you want to just make a new snippet of code and show everyone, but not necessarily have it displayed in the main code, then gist it. make it public so we can all see. 
Below is the code from the begginning of thursday. This is just the ToDO class


  public partial class ToDoLists : Form
    {
       
      //Instanciate ShoppingCart.cs class as an Object of the Form.
        ShoppingCart cart = new ShoppingCart();

      //Default Constructor with no Conditions (Does Nothing).
        public ToDoLists()
        {
            InitializeComponent();
        }



   //****************************************************************************************************************************************************************************************************************//
   //*********************************************   Button_Click Events that Control Navigation (Enabling the Corresponding Panel and Disabling ALL Others)   ******************************************************//
   //****************************************************************************************************************************************************************************************************************//

       //Changes Panel Visibility (All = false, except for Food Categories panel)
        private void btnCreateShoppingList_Click(object sender, EventArgs e)
        {
            plShoppingCatgs.Visible = true;
            plFirstScreen.Visible = false;
            plSumbitPage.Visible = false;
            plDairyMain.Visible = false;
            plProteinMain.Visible = false;
        }

       //Changes Panel Visibility (All = false, except for Dairy panel)
        private void btnDairyMain_Click(object sender, EventArgs e)
        {
            plDairyMain.Visible = true;
            plShoppingCatgs.Visible = false;
            plSumbitPage.Visible = false;
            plFirstScreen.Visible = false;
            plProteinMain.Visible = false;
        }

       //Changes Panel Visibility (All = false, except for Protein Panel)
        private void btnProteinMain_Click(object sender, EventArgs e)
        {
            plProteinMain.Visible = true;
            plShoppingCatgs.Visible = false;
            plFirstScreen.Visible = false;
            plSumbitPage.Visible = false;
            plDairyMain.Visible = false;
        }

       //Changes Panel Visibility (All = false, except for Food Categories panel)
        private void btnBackToCatgs_Click(object sender, EventArgs e)
        {
            plShoppingCatgs.Visible = true;
            plFirstScreen.Visible = false;
            plSumbitPage.Visible = false;
            plDairyMain.Visible = false;
            plProteinMain.Visible = false;
        }

       //Changes Panel Visibility (All = false, except for Food Categories panel)
        private void btnBackToCatgs2_Click(object sender, EventArgs e)
        {
            plShoppingCatgs.Visible = true;
            plFirstScreen.Visible = false;
            plSumbitPage.Visible = false;
            plDairyMain.Visible = false;
            plProteinMain.Visible = false;
        }




   //****************************************************************************************************************************************************************************************************************//
   //**********************   Button_Click Events that Control Navigation AND HAVE ADDITIONAL FEATURES (Enabling the Corresponding Panel and Disabling ALL Others + ADDITIONAL FEATURES)   **************************//
   //****************************************************************************************************************************************************************************************************************//

       //Changes Panel Visibility (All = false, except for First Screen panel) + RUNS RESULTS() METHODS FOR EACH FOOD CATEGORY      
        private void btnSubmitMain_Click(object sender, EventArgs e)
        {
            plSumbitPage.Visible = true;
            plShoppingCatgs.Visible = false;
            plFirstScreen.Visible = false;
            plDairyMain.Visible = false;
            plProteinMain.Visible = false;

           //Calls the FigureResults() method for each food category, receiving a string back and then Formatting it and adding it the the Submit Panel's lblResults.Text label.
            lblResults.Text += string.Format(cart.FigureDairyResults());
            lblResults.Text += string.Format(cart.FigureProteinResults());
        }

       //Changes Panel Visibility (All = false, except for Edit Items panel) + ALLOWS FOR REMOVING/UPDATING ALREADY-SELECTED SHOPPING ITEMS                       *****
        private void btnEditItems_Click(object sender, EventArgs e)
        {

        }

       //Changes Panel Visibility (All = false) + RESETS THE PROGRAM ENTIRELY TO ENSURE THAT IS RUNS SMOOTHLY EVERYTIME                                           *****
        private void btnBackToListSelect_Click(object sender, EventArgs e)
        {
            plFirstScreen.Visible = true;
            plShoppingCatgs.Visible = false;
            plSumbitPage.Visible = false;
            plDairyMain.Visible = false;
            plProteinMain.Visible = false;

           //ReLaunches Program entirely.
             //this.Restart();
        }




   //**************************************************************************************************************************************************************************************************************//
   //**************************************************   Button_Click Events that Increase their Accessor in ShoppingCart.cs (Storing Item Quantities)   *********************************************************//
   //**************************************************************************************************************************************************************************************************************//

       //Increases Quantity of 'Cheese' in ShoppingCart.cs
        private void btnCheeseItem_Click(object sender, EventArgs e)
        {
            cart.Cheese++;
        }

       //Increases Quantity of 'Milk' in ShoppingCart.cs
        private void btnMilkItem_Click(object sender, EventArgs e)
        {
            cart.Milk++;
        }

       //Increases Quantity of 'Butter' in ShoppingCart.cs
        private void btnButterItem_Click(object sender, EventArgs e)
        {
            cart.Butter++;
        }

       //Increases Quantity of 'Yogurt' in ShoppingCart.cs
        private void btnYogurtItem_Click(object sender, EventArgs e)
        {
            cart.Yogurt++;
        }

       //Increases Quantity of 'Steak' in ShoppingCart.cs
        private void bttnSteak_Click(object sender, EventArgs e)
        {
            cart.Steak++;
            lblTotalMeatTally.Text = Convert.ToString(cart.UpdateProteinRunningTotal());
            lblSteak.Text = Convert.ToString(cart.Steak);
        }

       //Increases Quantity of 'Pork' in ShoppingCart.cs
        private void bttnPork_Click(object sender, EventArgs e)
        {
            cart.Pork++;
            lblTotalMeatTally.Text = Convert.ToString(cart.UpdateProteinRunningTotal());
            lblPork.Text = Convert.ToString(cart.Pork);
        }

       //Increases Quantity of 'Chicken' in ShoppingCart.cs
        private void bttnChicken_Click(object sender, EventArgs e)
        {
            cart.Chicken++;
            lblTotalMeatTally.Text = Convert.ToString(cart.UpdateProteinRunningTotal());
            lblChicken.Text = Convert.ToString(cart.Chicken);
        }

       //Increases Quantity of 'Beef' in ShoppingCart.cs
        private void bttnBeef_Click(object sender, EventArgs e)
        {
            cart.Beef++;
            lblTotalMeatTally.Text = Convert.ToString(cart.UpdateProteinRunningTotal());
            lblBeef.Text = Convert.ToString(cart.Beef);
        }

       //Increases Quantity of 'Tilapia' in ShoppingCart.cs
        private void bttnTilapia_Click(object sender, EventArgs e)
        {
            cart.Tilapia++;
            lblTotalMeatTally.Text = Convert.ToString(cart.UpdateProteinRunningTotal());
            lblTilapia.Text = Convert.ToString(cart.Tilapia);
        }
       
       //Increases Quantity of 'Trout' in ShoppingCart.cs
        private void bttnTrout_Click(object sender, EventArgs e)
        {
            cart.Trout++;
            lblTotalMeatTally.Text = Convert.ToString(cart.UpdateProteinRunningTotal());
            lblTrout.Text = Convert.ToString(cart.Trout);
        }
       
       //Increases Quantity of 'Salmon' in ShoppingCart.cs
        private void bttnSalmon_Click(object sender, EventArgs e)
        {
            cart.Salmon++;
            lblTotalMeatTally.Text = Convert.ToString(cart.UpdateProteinRunningTotal());
            lblSalmon.Text = Convert.ToString(cart.Salmon);
        }
       
       //Increases Quantity of 'Shrimp' in ShoppingCart.cs
        private void bttnShrimp_Click(object sender, EventArgs e)
        {
            cart.Shrimp++;
            lblTotalMeatTally.Text = Convert.ToString(cart.UpdateProteinRunningTotal());
            lblShrimp.Text = Convert.ToString(cart.Shrimp);
        }
       
       //Increases Quantity of 'Lobster' in ShoppingCart.cs
        private void bttnLobster_Click(object sender, EventArgs e)
        {
            cart.Lobster++;
            lblTotalMeatTally.Text = Convert.ToString(cart.UpdateProteinRunningTotal());
            lblLobster.Text = Convert.ToString(cart.Lobster);
        }
       
       //Increases Quantity of 'Crab' in ShoppingCart.cs
        private void bttnCrab_Click(object sender, EventArgs e)
        {
            cart.Crab++;
            lblTotalMeatTally.Text = Convert.ToString(cart.UpdateProteinRunningTotal());
            lblCrab.Text = Convert.ToString(cart.Crab);
        }
       
       //Increases Quantity of 'DriedPinto' in ShoppingCart.cs
        private void bttnPinto_Click(object sender, EventArgs e)
        {
            cart.DriedPinto++;
            lblTotalMeatTally.Text = Convert.ToString(cart.UpdateProteinRunningTotal());
            lblPinto.Text = Convert.ToString(cart.DriedPinto);
        }
      
       //Increases Quantity of 'DriedBlack' in ShoppingCart.cs
        private void bttnBlackBeans_Click(object sender, EventArgs e)
        {
            cart.DriedBlack++;
            lblTotalMeatTally.Text = Convert.ToString(cart.UpdateProteinRunningTotal());
            lblBlack.Text = Convert.ToString(cart.DriedBlack);
        }
       
       //Increases Quantity of 'DriedKidney' in ShoppingCart.cs
        private void bttnKidney_Click(object sender, EventArgs e)
        {
            cart.DriedKidney++;
            lblTotalMeatTally.Text = Convert.ToString(cart.UpdateProteinRunningTotal());
            lblKidney.Text = Convert.ToString(cart.DriedKidney);
        }
       
       //Increases Quantity of 'Eggs' in ShoppingCart.cs
        private void bttnEggs_Click(object sender, EventArgs e)
        {
            cart.Eggs++;
            lblTotalMeatTally.Text = Convert.ToString(cart.UpdateProteinRunningTotal());
            lblEggs.Text = Convert.ToString(cart.Eggs);
        }
       
       //Increases Quantity of 'Nuts' in ShoppingCart.cs
        private void bttnNuts_Click(object sender, EventArgs e)
        {
            cart.Nuts++;
            lblTotalMeatTally.Text = Convert.ToString(cart.UpdateProteinRunningTotal());
            lblNuts.Text = Convert.ToString(cart.Nuts);
        }

    }
}
