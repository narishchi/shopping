# SPCart
 by นริศรา มาตย์สุด
673450037-2,
Computer and Infomation Science, KKU

```
 private void Checkout_Click(object sender, EventArgs e)
        {
        
            if (chbCoffee.Checked) { }
            // อ่านค่าtb  Coffee
            string strCoffeePrice = tbCoffeePrice.Text;
            string strCoffeeQuantity = tbCoffeeQuantity.Text;

            // อ่านค่าtb Greentea
            string strGreenTeaPrice = tbGreenTeaPrice.Text;
            string strGreenTeaQuantity = tbGreenTeaQuantity.Text;

            // อ่านค่า Cash
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
                // ตรวจว่าได้ติ้ก checkboxCoffee มัะ้ย
                if (chbCoffee.Checked)
                {
                    // แปลงค่าจาก string เปน int
                    iCoffeePrice = int.Parse(strCoffeePrice);
                    iCoffeeQuantity = int.Parse(strCoffeeQuantity);
                }

                // ตรวจสอบ checkboxGreen Tea
                if (chbGreenTea.Checked)
                {
                    iGreenTeaPrice = int.Parse(strGreenTeaPrice);
                    iGreenTeaQuantity = int.Parse(strGreenTeaQuantity);
                }

                //อ่านค่า Cash
                iCash = int.Parse(strCash);

            }

            catch (Exception ex)
            {
                // แปลงค่าผิดพลาด  จะเปน0
                iCoffeePrice = 0;
                iCoffeeQuantity = 0;
                iGreenTeaPrice = 0;
                iGreenTeaQuantity = 0;
                iCash = 0;
            }

            //คำนวน ยอดรอมม
            iTotal = (iCoffeePrice * iCoffeeQuantity) + (iGreenTeaPrice * iGreenTeaQuantity);

            //คำนวนเงินทอน
            iChange = iCash - iTotal;

            //แสดงยอดรวม  เงินทอน ใน TextBox
            tbTotal.Text = iTotal.ToString();
            tbChange.Text = iChange.ToString();

            // แจกแจงแบงค์และเหรียญ thankyouChatgpt
            int[] denominations = { 1000, 500, 100, 50, 20, 10, 5, 1 };
            TextBox[] denominationTextBoxes = { tb1000, tb500, tb100, tb50, tb20, tb10, tb5, tb1 };

            for (int i = 0; i < denominations.Length; i++)
            {
                int count = iChange / denominations[i]; //จำนวนแบ้งใบ  เหรียญ
                iChange %= denominations[i];           //เงินที่เหลือ
                denominationTextBoxes[i].Text = count.ToString();
            }
        }

private void Clear_Click(object sender, EventArgs e)
{
    tbCoffeePrice.Text = "";
    tbCoffeeQuantity.Text = "";
    tbGreenTeaQuantity.Text = "";
    tbGreenTeaPrice.Text = "";
    tbTotal.Text = "";
    tbCash.Text = "";
    tbChange.Text = "";
    tb1000.Text = "";
    tb500.Text = "";
    tb100.Text = "";
    tb50.Text = "";
    tb20.Text = "";
    tb10.Text = "";
    tb5.Text = "";
    tb1.Text = "";
    chbCoffee.Checked = false;
    chbGreenTea.Checked = false;
}
     ```
