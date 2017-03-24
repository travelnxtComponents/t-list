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
