package webt;
import java.util.concurrent.TimeUnit;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
public class Webtab {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		System.setProperty("webdriver.chrome.driver","E:\\drivers\\chromedriver.exe");
		WebDriver driver=new ChromeDriver();
		driver.get("http://demo.guru99.com/test/table.html");
		driver.manage().timeouts().implicitlyWait(20,TimeUnit.SECONDS);
		
		
		
		WebElement baseTable=driver.findElement(By.xpath("/html/body/table"));
		
		WebElement tRow=baseTable.findElement(By.xpath("/html/body/table/tbody/tr[2]"));
		
		baseTable.findElement(By.xpath("/html/body/table/tbody/tr[2]/td[1]"));
		
		String rowtext=tRow.getText();
		System.out.println("Second row of the table: "+rowtext);
		
		WebElement cellIneed=tRow.findElement(By.xpath("/html/body/table/tbody/tr[2]/td[2]"));
		String valueIneed=cellIneed.getText();
		System.out.println("Cell value is :" +valueIneed);
		driver.close();
	}

}
