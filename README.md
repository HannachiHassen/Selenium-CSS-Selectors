# Selenium-CSS-Selectors
Locating elements by CSS selectors is the preferred way as it is faster and more readable than XPath.

This tutorial provides examples of how to locate web elements in Selenium using CSS selectors.

## CSS Selectors by Attribute

Let’s imagine we have a tag with the following attributes [id, class, name, value]

```html
<input type="text" id="fistname" name="first_name" class="myForm">
```
The generic way to locate elements by attribute is:

```html
css = element_name[<attribute_name>='<value>']
```

Example:
```java
WebElement firstName = driver.findElement(By.cssSelector("input[name='first_name']"));
```
## Id Attribute
In CSS, we can use # notation to select the id attribute of an element:

Example:
```java
driver.findElement(By.cssSelector("input#firstname"));

//or

driver.findElement(By.cssSelector("#firstname"));
```
## Class Attribute

The same principle can be used to locate elements by their class attribute.

We use the . notation.
```java
driver.findElement(By.cssSelector("input.myForm"));

//or

driver.findElement(By.cssSelector(".myForm"));
```
> **Note**: **Take extra care when using the . notation as there could be many web elements on the HTML source with the same class attribute.** 

## Multiple Attributes

Sometimes there is a need to be more specific with the selection criteria in order to locate the correct element.
```html
<div class="ajax_enabled" style="display:block">
```
The value of the display could either be “none” or “block” depending on the ajax call. In this situation, we have to locate the element by both class and style.

Example:
```java
driver.findElement(By.cssSelector("div[class='ajax_enabled'] [style='display:block']"))
```
