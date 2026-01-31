package com.qa.tests;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

import io.github.bonigarcia.wdm.WebDriverManager;

/**
 * @author Admin
 *
 */
public class LoginTest {

	public static void main(String[] args) throws InterruptedException {
		
		WebDriverManager.chromedriver().setup();
		
		WebDriver driver = new ChromeDriver();
		driver.manage().window().maximize();
		
		driver.get("https://rahulshettyacademy.com/locatorspractice/");
		driver.findElement(By.id("inputUsername")).sendKeys("ashwini");
		driver.findElement(By.name("inputPassword")).sendKeys("test");
		driver.findElement(By.className("signInBtn")).click();
		
		Thread.sleep(2000);
		
		String message = driver.findElement(By.className("error")).getText();
		System.out.println(message);
		
		driver.findElement(By.linkText("Forgot your password?")).click();
		Thread.sleep(2000);
		
		driver.findElement(By.cssSelector("input[placeholder='Name']")).sendKeys("ashwini");

		driver.findElement(By.cssSelector("input[placeholder='Email']")).sendKeys("ashwini@gmail.com");
		driver.findElement(By.cssSelector(".reset-pwd-btn")).click();
		
		String passwordReset = driver.findElement(By.className("infoMsg")).getText();
		System.out.println(passwordReset);
		
		String arrayPassowrd[] = passwordReset.split("'");
		
		System.out.println(arrayPassowrd[1]); // has password

		driver.findElement(By.cssSelector(".go-to-login-btn")).click();
		Thread.sleep(2000);
		
		driver.findElement(By.id("inputUsername")).sendKeys("ashwini");
		driver.findElement(By.name("inputPassword")).sendKeys(arrayPassowrd[1]);
		driver.findElement(By.className("signInBtn")).click();
		
		Thread.sleep(2000);
		
		String dashboardMsg = driver.findElement(By.cssSelector("div[class='login-container'] h2")).getText();
		System.out.println(dashboardMsg);
		
		driver.quit();
		
	}
}
