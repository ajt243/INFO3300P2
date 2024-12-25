# Project To-Do List
---

### Tasks

1. **Enhance Tooltip with Fast Food Rankings**
   - [X] Keep the current tooltip functionality for displaying the state name and top-ranked fast food chain on hover.
   - [X] Display the rankings in the following format within the tooltip:
     ```

     STATE NAME
     Top Fast Food: [Top Ranked Fast Food Chain]
     ```
   - [X] Ensure this tooltip is updated based on `mergedData` for each state.

2. **Add Legend to the Right of the Map**
   - [X ] Create a legend section to the right of the map (replacing the current McDonald's logo area).
   - [X] Display the legend in the following format:
     ```
     STATE NAME
     1. [Top Ranked Fast Food Chain Logo]
     2. [Second Ranked Fast Food Chain Logo]
     3. [Third Ranked Fast Food Chain Logo]
     ```
   - [ ] Adjust the legend styling to ensure logos are clearly visible, with the state name at the top and the rankings listed in order.

3. **Collect Logos for Fast Food Chains**
   - [X] Gather logos for the top-ranked fast food chains (e.g., McDonald’s, Starbucks, Dominos, etc.).
   - [X] Store the logos in a dedicated `logos` folder within the repo.
   - [ ] Map each fast food chain name to its respective logo URL in the code.
   - [ ] Update the legend to display the correct logo next to each ranked fast food chain for each state.

4. **Add Zoom Functionality for State Statistics**
   - [X] Implement zoom functionality to allow users to zoom in on a specific state.
   - [ ] When zoomed in, display detailed statistics related to obesity for that state, broken down by demographics (e.g., race, sex).
   - [ ] Ensure that when zoomed out, the map returns to the general view, hiding detailed statistics.

---

### Future Enhancements / Ideas

- [X] Allow users to toggle between viewing fast food rankings and obesity statistics in the legend.
- [ ] UI Changes: make the website look sleek, update color schemes, and alignment issues.
- [ ] Fill in Data Gaps or explicitly state shortcomings
- [X] Created legend for obesity gradient
- [ ] Find source for dataset
