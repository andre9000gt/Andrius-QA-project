# Andrius-QA-project
Test automation project
import org.junit.Assert;
import org.junit.Test;
import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.interactions.Actions;
import org.openqa.selenium.support.ui.Select;
import java.util.concurrent.TimeUnit;

public class FirstTestSuite {
    
    //1) Add/Remove elements test cases
    
    @Test
    public void addRemoveElements() {
        System.setProperty("webdriver.chrome.driver", "drivers\\chromedriver_v94.exe");
        WebDriver driver = new ChromeDriver();
        String url = "http://the-internet.herokuapp.com";


        driver.get(url);
        WebElement addDeleteElements = driver.findElement(By.cssSelector("#content > ul > li:nth-child(2) > a"));
        addDeleteElements.click();

        WebElement addButton = driver.findElement(By.cssSelector("#content > div > button"));
        addButton.click();


        WebElement deleteButton = driver.findElement(By.cssSelector("#elements > button"));
        deleteButton.click();

        driver.close();
    }

    //2) Checkboxes clicking test cases
    
    @Test
    public void checkboxes() {
        System.setProperty("webdriver.chrome.driver", "drivers\\chromedriver_v94.exe");
        WebDriver driver = new ChromeDriver();
        String url = "http://the-internet.herokuapp.com";

        driver.get(url);
        WebElement checkboxes = driver.findElement(By.cssSelector("#content > ul > li:nth-child(6) > a"));
        checkboxes.click();

        WebElement checkboxOne = driver.findElement(By.cssSelector("#checkboxes > input[type=checkbox]:nth-child(1)"));
        checkboxOne.click();

        WebElement checkboxOneUndo = driver.findElement(By.cssSelector("#checkboxes > input[type=checkbox]:nth-child(1)"));
        checkboxOneUndo.click();

        WebElement checkboxTwo = driver.findElement(By.cssSelector("#checkboxes > input[type=checkbox]:nth-child(3)"));
        checkboxTwo.click();

        WebElement checkboxTwoUndo = driver.findElement(By.cssSelector("#checkboxes > input[type=checkbox]:nth-child(3)"));
        checkboxTwoUndo.click();

        driver.close();
    }
    
    //3) Context menu right click and alert acception test cases
   
    @Test
    public void contextMenu() {
        System.setProperty("webdriver.chrome.driver", "drivers\\chromedriver_v94.exe");
        WebDriver driver = new ChromeDriver();
        String url = "http://the-internet.herokuapp.com";

        driver.get(url);
        WebElement contextMenu = driver.findElement(By.cssSelector("#content > ul > li:nth-child(7) > a"));
        contextMenu.click();

        Actions action = new Actions(driver);
        action.contextClick(driver.findElement(By.xpath("//*[@id=\"hot-spot\"]"))).build().perform();

        driver.switchTo().alert().accept();

        driver.close();
    }

    //4) Dropdown list and options selection test cases
    
    @Test
    public void dropDownList() {
        System.setProperty("webdriver.chrome.driver", "drivers\\chromedriver_v94.exe");
        WebDriver driver = new ChromeDriver();
        String url = "http://the-internet.herokuapp.com";

        driver.get(url);
        WebElement dropDown = driver.findElement(By.cssSelector("#content > ul > li:nth-child(11) > a"));
        dropDown.click();

        WebElement clickDropDown = driver.findElement(By.cssSelector("#dropdown"));
        clickDropDown.click();

        Select dropdown = new Select(driver.findElement(By.id("dropdown")));
        dropdown.selectByIndex(1);

        WebElement clickDropDown2 = driver.findElement(By.cssSelector("#dropdown"));
        clickDropDown2.click();

        Select dropdown2 = new Select(driver.findElement(By.id("dropdown")));
        dropdown2.selectByIndex(2);

        driver.close();
    }

    //5) Dynamic loading IN PROGRESS
    
    @Test
    public void dynLoading() {
        System.setProperty("webdriver.chrome.driver", "drivers\\chromedriver_v94.exe");
        WebDriver driver = new ChromeDriver();
        String url = "http://the-internet.herokuapp.com";

        driver.get(url);
        WebElement dynLoad = driver.findElement(By.cssSelector("#content > ul > li:nth-child(14) > a"));
        dynLoad.click();

        driver.close();
    }

    //6) Hover action test cases
    
    @Test
    public void hoverMouse() {
        System.setProperty("webdriver.chrome.driver", "drivers\\chromedriver_v94.exe");
        WebDriver driver = new ChromeDriver();
        String url = "http://the-internet.herokuapp.com";

        driver.get(url);
        WebElement hover = driver.findElement(By.cssSelector("#content > ul > li:nth-child(25) > a"));
        hover.click();

        Actions actions = new Actions(driver);
        WebElement hover1 = driver.findElement(By.cssSelector("#content > div > div:nth-child(3) > img"));
        actions.moveToElement(hover1);

        WebElement subMenu1 = driver.findElement(By.cssSelector("#content > div > div:nth-child(3) > div > a"));
        actions.moveToElement(subMenu1);
        actions.build().perform();

        WebElement hover2 = driver.findElement(By.cssSelector("#content > div > div:nth-child(4) > img"));
        actions.moveToElement(hover2);

        WebElement subMenu2 = driver.findElement(By.cssSelector("#content > div > div:nth-child(4) > div > a"));
        actions.moveToElement(subMenu2);
        actions.build().perform();

        WebElement hover3 = driver.findElement(By.cssSelector("#content > div > div:nth-child(5) > img"));
        actions.moveToElement(hover3);

        WebElement subMenu3 = driver.findElement(By.cssSelector("#content > div > div:nth-child(5) > div > a"));
        actions.moveToElement(subMenu3);
        actions.build().perform();

        driver.close();
    }

    //7) Input test case
    
    @Test
    public void inputText() {

        System.setProperty("webdriver.chrome.driver", "drivers\\chromedriver_v94.exe");
        WebDriver driver = new ChromeDriver();
        String url = "http://the-internet.herokuapp.com";

        driver.get(url);
        WebElement input = driver.findElement(By.cssSelector("#content > ul > li:nth-child(27) > a"));
        input.click();
        int count = 10;
        WebElement number = driver.findElement(By.cssSelector("#content > div > div > div > input[type=number]"));
        number.sendKeys("" + count);

        driver.close();
    }

    //8) Slow resources test cases IN PROGRESS
    
    @Test
    public void slowResources() {

        System.setProperty("webdriver.chrome.driver", "drivers\\chromedriver_v94.exe");
        WebDriver driver = new ChromeDriver();
        String url = "http://the-internet.herokuapp.com";

        driver.get(url);
        WebElement slowRes = driver.findElement(By.cssSelector("#content > ul > li:nth-child(40) > a"));
        slowRes.click();

        driver.close();
    }
    
    //9) Sortable data tables test cases IN PROGRESS
    
    @Test
    public void dataTables() {

        System.setProperty("webdriver.chrome.driver", "drivers\\chromedriver_v94.exe");
        WebDriver driver = new ChromeDriver();
        String url = "http://the-internet.herokuapp.com";

        driver.get(url);
        WebElement datTable = driver.findElement(By.cssSelector("#content > ul > li:nth-child(41) > a"));
        datTable.click();

        driver.close();
    }
}
