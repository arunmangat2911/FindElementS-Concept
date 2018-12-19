# FindElementS-Concept

package SeleniumSession;

import java.util.List;
import java.util.concurrent.TimeUnit;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class FindElementSConcept {

	public static void main(String[] args) {
		System.setProperty("webdriver.chrome.driver", "C:\\Users\\Arun\\eclipse-workspace\\Selenium\\lib\\chromedrivers\\chromedriver.exe");
		WebDriver driver = new ChromeDriver();
		
		driver.manage().window().maximize();
		
		
		
		driver.manage().timeouts().pageLoadTimeout(40, TimeUnit.SECONDS);
		driver.manage().timeouts().implicitlyWait(30, TimeUnit.SECONDS);
		
		driver.get("https://www.ebay.com/");
		
		//1.Get the total count of links on the page
		//2.get the text of each link on the page
		
		List <WebElement> linkList = driver.findElements(By.tagName("a"));
		
		//Size of linklist
		System.out.println(linkList.size());
		
		for(int i=0;i<linkList.size();i++) {
			String linkText = linkList.get(i).getText();
			System.out.println(linkText);
		
		}
		
		
		
		

	}

}
