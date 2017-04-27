# Travel List Component

### Component Use

```javascript
<t-list items=[[data]] settings=[[settings]] resources=[[resources]]>
  <template>
    <img src="" />  
    <t-hotel-item class="item" data=[[item]]></t-hotel-item
  </template>
  <template class="no-results">
    <div>{{resources.noResultsFound}}</div>
    <div>Try a new search</div>
    <t-search></t-search>    
  </template>
</t-list>
```


### Settings
```javascript
{
    "pageSize": 10,
    //Scrolls  to this page
    "showPage": 3,
    "enableScrollTop":true,
    "views": [
        {
            "title": "List",
            "code": "lst",
            "iconName": "list",
            "selected": true
        },
        {
            "title": "Map",
            "iconName": "map",
            "code": "map"
        }
    ],
    "sorting": [
        {
            "title": "Hotel Name",
            "property": "name",
            "sortBy": "asc"
        },
        {
            "title": "Star rating", "property": "rating",                   
            "options": [
                {
                    "title": "Rating low to high",
                    "sortBy": "asc"
                },
                {
                    "title": "Rating high to low",
                    "sortBy": "dsc",
                    "selected":true
                }
            ]
        },
        {
            "title": "Recommended",
            "property": "relevance",
            "sortBy": "dsc",
            //in this case the sort will not allow multiple clicks for toggle
            "singleState":true
        },
        {
            "title": "Review",
            "property": "user.rating",
            "sortBy": "dsc"
        }
    ],
    "currentSortIndex": 2,
    "filter": [
        {
            "title": "Price",
            "code": "price"
        },
        {
            "title": "Rating",
            "code": "rating"
        },
        {
            "title": "Distance",
            "code": "dist"
        }
    ]
}
```
### Resources
```javascript
{
    "title": "We found {{total} hotels for your search",
    "filteredTitle": "We found {{current}/{{total} hotels for your search",
    "loadMoreResultsText": "SHOW MORE RESULTS",
    "loadingMoreResultsText": "LOADING ...",
    "noResultsFound":"Oops! no results found for your search. Pelase try again",
    "noFilteredResults":"Sorry no results found for your applied filters.",
    "listUpdateText":"Updating results",
    "icons": {
        "list": "list-icon",
        "map": "map"        
    }
}
```

### Data
```javascript

[
    {
        "id": 1
    },
    {
        "id": 2
    }
]
```

### Events

```javascript
Listens
t-list-set-filter
t-list-view-tap{
    "code": "map"
}

Raise
t-list-filter-reset  - {"code":"dst"}
t-list-more-results-tap 

```

### Styles
```javascript
Need variable for defining header text colour
Need mixin for defining border details
Classes for overriding default icons
Loader mixin to set class or image details for all icons
```
## Important Information
- 

## Test Cases
- Verify all exposed public properties are working independently and with complex combination.
- Verify all exposed methods and events are working.

## Steps to Start
- Set Github repository at your end for this project, we will merge them later
- You can use Google/Vaadin's elements (like calender element and textboxes etc.)
- You can use some Tavisca's elements like auto-suggest if required from https://github.com/atomelements/t-autosuggest but all the features and properties mentioned in scope should be added. (Fork the existing element and create V2)

## Performance standard
- Any component if opened via [web page tester](https://www.webpagetest.org/), it should load under 500ms (milli seconds).

## Documents
- Visual designs for List component - https://projects.invisionapp.com/share/6E9PJ7R4Q#/screens/219768213
- API access : Url - http://demo.travelnxt.com/dev
- Tavisca Elements - https://github.com/atomelements and https://github.com/travelnxtelements
- Vaadin elements - https://vaadin.com/docs/-/part/elements/elements-getting-started.html
- Google - https://elements.polymer-project.org/browse?package=google-web-components
- Tavisca Web component style Guide - https://drive.google.com/open?id=0B7BT_2nBFNYVR2tscE9pRnVJYmc
