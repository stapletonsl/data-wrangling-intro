### Using clustering to detect possible typing errors

Another very useful feature of OpenRefine is Clustering.  In OpenRefine, clustering means 'finding groups of different values that might be alternative representations of the same thing'. For example, the text strings 'New York', 'new york'  or 'New Yrok' (write on board) very likely refer to the same concept.

Clustering is a very powerful tool for identifying and fixing datasets which contain misspelled or mistyped entries.

OpenRefine has several clustering algorithms built in. Let's experiment with them.

#### Activity 10 – Fixing errors via Clustering

Create a Text Facet for `Crash_Nature`, scroll through the list.  You will notice a number of values  that are likely mis-typed entries due to various factors.  (Ask for examples and reward with prizes).

Click the `Cluster` button, on the top right of the facet.

In the resulting pop-up window, different edit options and algorithms are available via drop down boxes.

Select the `key collision` method and `fingerprint` keying function. It should identify one cluster with 3 value options.

Click the `Merge?` box beside the cluster, then click `Merge Selected and Re-cluster` to apply the corrections to the dataset.

Try selecting different Methods and Keying Functions combinations, to see if new merges are suggested.

There may be a few more clusters, to fix misspellings, typos, capitalisation, hyphens, etc.

How many choices are now shown in the facet?  13 (prize).

Close the facet.

*Important: Some merges are not necessary. Nearest neighbour with a radius of 2.0 with find Struck by external load with Struck by internal load.  These are valid variables, do not merge these.*

### Different clustering algorithms

Detailed information on the different clustering algorithms and combinations is available here: [https://github.com/OpenRefine/OpenRefine/wiki/Clustering-In-Depth](https://github.com/OpenRefine/OpenRefine/wiki/Clustering-In-Depth).
