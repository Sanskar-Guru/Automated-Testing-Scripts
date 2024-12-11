# Automated-Testing-Scripts
Selenium and API testing scripts for beginners.
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class LoginTest {
    public static void main(String[] args) {
        System.setProperty("webdriver.chrome.driver", "path-to-chromedriver");
        WebDriver driver = new ChromeDriver();

        // Open the login page
        driver.get("https://example.com/login");

        // Find and interact with elements
        WebElement username = driver.findElement(By.id("username"));
        WebElement password = driver.findElement(By.id("password"));
        WebElement loginButton = driver.findElement(By.id("loginButton"));

        username.sendKeys("testuser");
        password.sendKeys("password123");
        loginButton.click();

        // Verify the result
        String expectedUrl = "https://example.com/dashboard";
        if (driver.getCurrentUrl().equals(expectedUrl)) {
            System.out.println("Login test passed!");
        } else {
            System.out.println("Login test failed.");
        }

        driver.quit();
    }
}
