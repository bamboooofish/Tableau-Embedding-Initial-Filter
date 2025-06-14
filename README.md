# Tableau-Embedding-Initial-Filter

A simple demo showing how to embed Tableau visualizations with pre-applied filters for basic data access control.
> **Disclaimer**: This is a lightweight, client-side filtering approach - not enterprise-level security. For production environments with sensitive data, implement proper server-side access controls.

## Example Links

- **Original Tableau (All Data):**  [Tableau Public](https://public.tableau.com/app/profile/bamboooo.fish/viz/addFilter/Region_Only?publish=yes)

- **Embedded Version (Central Region Only):**  [View the demo](https://bamboooofish.github.io/Tableau-Embedding-Initial-Filter/)

> **Note:** You'll notice that even the "Region & State" Dashboard shows only the Central region data, demonstrating how the filter applies across all worksheets.

## How to do it?

**Step 1:** In Tableau, configure your filter to "Apply to Worksheets" > "Selected worksheets" and select all relevant worksheets.

**Step 2:** Use the Tableau Embedding API v3 with the `addFilter()` function, like:
```javascript
viz.addFilter('Region', 'Central');
```

## Use Cases
- **Basic Access Control**: You can detect user permissions and apply different filters accordingly.
- **Personalized Dashboards**: Show users only the data they're authorized to see.

## Use it on your dashboard
To adapt this for your own Tableau dashboard, simply modify these two parts in the code:
```javascript
// 1. Change to your Tableau URL
viz.src = 'https://public.tableau.com/views/addFilter/Region_Only?:language=zh-TW&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link';

// 2. Change the filter field and value
viz.addFilter('Region', 'Central');
```
