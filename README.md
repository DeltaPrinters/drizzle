# Drizzle
_The simplest jQuery filtering and sorting library ever!_

## Live Demo
Check the live demo <a href="https://anishnair02.github.io/drizzle/" target="_blank">here</a>

## Vision
<p align="center">
<img src="https://github.com/anishnair02/drizzle/blob/master/graphics/logo/drizzle.png?raw=true" width="100px" height="100px"/>
</p>

The main idea behind drizzle is to keep things simple and avoid complex conditions, thus evading confusion. The name **drizzle** here refers to **filtering** (which reduces the result, just like heavy rains to drizzle) and **sorting** (changes in the climatic conditions which affect rains). Too much of linking, right? Let's move into the coding/technical aspect. ;-)

## Including drizzle
The first thing to do is to include the plugin file to your html.

To include the plugin file, you can either download it include it locally or use CDN path

### Download
```html
<script src="https://github.com/anishnair02/drizzle/blob/master/dist/drizzle.min.js"></script>
```

### CDN
```html
<script src="https://cdn.jsdelivr.net/gh/anishnair02/drizzle/dist/drizzle.min.js"></script>
```
> - Downloading and using the plugin file locally in your project is faster. 
> - But using CDN path has a great advantage - you get the latest copy of the JS file.
> - Also note, browser caching or server side caching may affect fetching the latest version of drizzle.min.js since the filename remains the same and at times maybe cached.

## Initializing drizzle
Once you have included the plugin file, you need initialize it once (for a particluar parent-child element relationship) to be able to filter and sort elements.

Go to your custom js file or create a new one - say "main.js" and include it to your html file just like you did above.

To initialize, please refer to the code below
```javascript
var grid = $(container).drizzle({child: child-elements});
```            
Here, we are defining the **container (the parent)** element and the **child (all the children)** elements so that drizzle understands it.

**Container** and **child** elements can be any HTML/jQuery element (i.e a [jQuery selector]([https://api.jquery.com/category/selectors/](https://api.jquery.com/category/selectors/))) and you can define it using an `id`, `classname` or by using any `attribute-value` pair
> #id ```#person```<br/>
> .classname ```.people``` <br/>
> attribute=value ```type="people"```

#### Example
```javascript
var grid = $('.cards').drizzle({child: '.card'});
```
Here `.cards` is the container and `.card` is the child.

Hi! I'm your first Markdown file in **StackEdit**. If you want to learn about StackEdit, you can read me. If you want to play with Markdown, you can edit me. Once you have finished with me, you can create new files by opening the **file explorer** on the left corner of the navigation bar.

## Filtering
To filter the children, use the **filter** method
```javascript
grid.filter(element);     
```
`element` refers to any HTML/jQuery element

#### Example
```javascript
grid.filter('.members.new');
/* OR */
grid.filter('#customer-21');
/* OR */
grid.filter('[data-role="captain"]');
```

## Sorting
To sort the children, use the **sort** method
```javascript
grid.sort(element, [options]);    
```
`element` refers to any HTML/jQuery element
`options` are optional. Refers to the options you need to pass, the `order` of sort in this case.

```javascript
options = {
	order: 'asc' // asc, desc. By default it's always asc (ascending)
	isNumber: true // true, false. By default it's false and will sort it by alphabets. True will sort it based on the number(value) rather than alphabets.
}
```
#### Example
```javascript
grid.sort('.content .members.new', {order: 'desc'});
```

## Unfilter or Reset
To reset or unfilter, use any of the below methods

```javascript
grid.unfilter();
/* OR */
grid.rain();
/* OR */
grid.filter('*')
```

#### Resources
- Used <a href="https://semantic-ui.com/" target="_blank">Semantic UI</a> for demo/docs