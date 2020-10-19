# ProtectiveUI
package Tes1;
import java.util.Iterator;
import java.util.Set;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class PIC {

	public static void main(String[] args) throws InterruptedException {
		
		System.setProperty("webdriver.chrome.driver", "C:\\Users\\proy\\Desktop\\Chro\\chromedriver.exe");
		WebDriver driver = new ChromeDriver();
		driver.manage().window().maximize();
        driver.get("https://www.protectiveinsurance.com/");
        System.out.println(driver.getTitle());
        
        //Thread.sleep(4000);
        driver.findElement(By.linkText("MY ACCOUNT")).click();
        Thread.sleep(4000);
        //creating new object:  newWindow
        Set<String> newWindow = driver.getWindowHandles();
       //Iterate using Iterator 
        Iterator<String> tab =  newWindow.iterator();
        //create object on main window1
        String parent=tab.next();
        String child= tab.next();
        driver.switchTo().window(child);
        System.out.println("Current URL " + driver.getCurrentUrl());
        Thread.sleep(4000);
        
        driver.findElement(By.linkText("Claims")).click();
        Thread.sleep(4000);
       
        driver.findElement(By.id("ctl00_PlaceHolderMain_signInControl_UserName")).sendKeys("proy@protectiveinsurance.com");
        driver.findElement(By.id("ctl00_PlaceHolderMain_signInControl_password")).sendKeys("3XpkZd54rK");
        driver.findElement(By.id("ctl00_PlaceHolderMain_signInControl_login")).click();
        
