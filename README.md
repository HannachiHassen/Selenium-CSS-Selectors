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

##Attribute NOT contain a specific value

In WebDriver, how do you find elements whose attribute contain values which you don’t want to select? This CSS selector example shows how NOT to select by specific attribute value

Suppose you have many elements which share the same attribute and attribute value, but some of those elements have other variables appended to the value. e.g:
```html
<div class="day past calendar-day-2017-02-13 calendar-dow-1 unavailable">
<div class="day today calendar-day-2017-02-14 calendar-dow-2 unavailable">
<div class="day calendar-day-2017-02-15 calendar-dow-3">
<div class="day calendar-day-2017-02-16 calendar-dow-4">
```
In the above snippet, we want to select an available day (i.e. the two last `div` elements)

As can be seen, all four divs contain “calendar-day-“ but the first two also contain “unavailable” which we don’t want.

The CSS selector for Not selecting the first two divs is
```java
driver.findElement(By.cssSelector("div[class*=calendar-day-]:not([class*='unavailable'])"));"
```
## Locating Child Element

## Multiple Child Elements

## Dynamically Generated Ids

## Attribute Starts with

## Attribute Ends with

## Attribute Contains
