# SPCart
by naritsara Maritsud
673450037-2,
Computer and Infomation Science, KKU

```
 private void Checkout_Click(object sender, EventArgs e)
        {
        
            if (chbCoffee.Checked) { }
            // ÍèÒ¹¤èÒtb  Coffee
            string strCoffeePrice = tbCoffeePrice.Text;
            string strCoffeeQuantity = tbCoffeeQuantity.Text;

            // ÍèÒ¹¤èÒtb Greentea
            string strGreenTeaPrice = tbGreenTeaPrice.Text;
            string strGreenTeaQuantity = tbGreenTeaQuantity.Text;

            // ÍèÒ¹¤èÒ Cash
            string strCash = tbCash.Text;

            int iCoffeePrice = 0;
            int iCoffeeQuantity = 0;
            int iGreenTeaPrice = 0;
            int iGreenTeaQuantity = 0;
            int iTotal = 0;
            int iCash = 0;
            int iChange = 0;

            try
            {
                // µÃÇ¨ÇèÒä´éµÔé¡ checkboxCoffee ÁÑÐéÂ
                if (chbCoffee.Checked)
                {
                    // á»Å§¤èÒ¨Ò¡ string à»¹ int
                    iCoffeePrice = int.Parse(strCoffeePrice);
                    iCoffeeQuantity = int.Parse(strCoffeeQuantity);
                }

                // µÃÇ¨ÊÍº checkboxGreen Tea
                if (chbGreenTea.Checked)
                {
                    iGreenTeaPrice = int.Parse(strGreenTeaPrice);
                    iGreenTeaQuantity = int.Parse(strGreenTeaQuantity);
                }

                //ÍèÒ¹¤èÒ Cash
                iCash = int.Parse(strCash);

            }

            catch (Exception ex)
            {
                // á»Å§¤èÒ¼Ô´¾ÅÒ´  ¨Ðà»¹0
                iCoffeePrice = 0;
                iCoffeeQuantity = 0;
                iGreenTeaPrice = 0;
                iGreenTeaQuantity = 0;
                iCash = 0;
            }

            //¤Ó¹Ç¹ ÂÍ´ÃÍÁÁ
            iTotal = (iCoffeePrice * iCoffeeQuantity) + (iGreenTeaPrice * iGreenTeaQuantity);

            //¤Ó¹Ç¹à§Ô¹·Í¹
            iChange = iCash - iTotal;

            //áÊ´§ÂÍ´ÃÇÁ  à§Ô¹·Í¹ ã¹ TextBox
            tbTotal.Text = iTotal.ToString();
            tbChange.Text = iChange.ToString();

            // á¨¡á¨§áº§¤ìáÅÐàËÃÕÂ­ thankyouChatgpt
            int[] denominations = { 1000, 500, 100, 50, 20, 10, 5, 1 };
            TextBox[] denominationTextBoxes = { tb1000, tb500, tb100, tb50, tb20, tb10, tb5, tb1 };

            for (int i = 0; i < denominations.Length; i++)
            {
                int count = iChange / denominations[i]; //¨Ó¹Ç¹áºé§ãº  àËÃÕÂ­
                iChange %= denominations[i];           //à§Ô¹·ÕèàËÅ×Í
                denominationTextBoxes[i].Text = count.ToString();
            }
        }
     ```
