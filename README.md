# Project 3 - Yelp

Yelp is a Yelp search app using the [Yelp API](http://www.yelp.com/developers/documentation/v2/search_api).

Time spent: 6 hours spent in total

## User Stories

The following **required** functionality is completed:

- [x] Table rows for search results should be dynamic height according to the content height. (3pt)
- [x] Custom cells should have the proper Auto Layout constraints. (+5pt)
- [x] Search bar should be in the navigation bar (doesn't have to expand to show location like the real Yelp app does). (+2pt)

The following **stretch** features are implemented:

- [ ] Infinite scroll for restaurant results. (+3pt)
- [ ] Implement map view of restaurant results. (+3pt)
- [ ] Implement the restaurant detail page. (+2pt)

The following **additional** features are implemented:

- [ ] List anything else that you can get done to improve the app functionality!

Please list two areas of the assignment you'd like to **discuss further with your peers** during the next class (examples include better ways to implement something, how to extend your app in certain ways, etc):

1. Are there other ways (read: "easier") to set layouts for different devices? 
2. Should Auto Layout be automatically applied to items you place in the storyboard, and then be maanually changed around if necessary, rather than the other way around.

## Video Walkthrough

Here's a walkthrough of implemented user stories:

<img src=' https://i.imgur.com/DXL8GaO.gifv ' title='Video Walkthrough' width='' alt='Video Walkthrough' />



GIF created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

- Auto Layout is my worst enemy. I definitely will have to go back and rewatch the tutorial videos on it, because I'm constantly having issues trying to get things to look the way I want.

## License

Copyright [2018] [Cory Dashiell]

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.


### Basic Yelp client

This is a headless example of how to implement an OAuth 1.0a Yelp API client. The Yelp API provides an application token that allows applications to make unauthenticated requests to their search API.

### Next steps

- Check out `BusinessesViewController.swift` to see how to use the `Business` model.

### Sample request

**Basic search with query**

```
Business.searchWithTerm("Thai", completion: { (businesses: [Business]!, error: Error!) -> Void in
    self.businesses = businesses
    
    for business in businesses {
        print(business.name!)
        print(business.address!)
    }
})
```

**Advanced search with categories, sort, and deal filters**

```
Business.searchWithTerm("Restaurants", sort: .distance, categories: ["asianfusion", "burgers"], deals: true) { (businesses: [Business]!, error: Error!) -> Void in

    for business in businesses {
        print(business.name!)
        print(business.address!)
    }
}
```
