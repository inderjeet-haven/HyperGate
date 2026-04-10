**Guide For Formatting The Master\_Inventory Excel As Per Your Proxmox Infra:**

---

* To ensure the "Infrastructure Map" builds correctly in HyperGate, the Excel file must follow a strict 5-column structure. Do not change the column order.



* Example Scenarios:



1. One country one cluster at one site (with 2 nodes).



|Country|Site|Cluster|Node\_Name|IP|
|-|-|-|-|-|
|UK|London|LDN-PRD-01|pve-lon-01|10.0.0.10|
|UK	<br />|London|LDN-PRD-01|pve-lon-02|10.0.0.20|



2\. One country with multiple clusters at one site (with 2 nodes each).



|Country|Site|Cluster|Node\_Name|IP|
|-|-|-|-|-|
|UK|London|LDN-PRD-01|pve-lon-01|10.0.0.10|
|UK	<br />|London|LDN-PRD-01|pve-lon-02|10.0.0.20|
|UK|London|LDN-PRD-02|pve-lon-03|10.0.0.30|
|UK|London|LDN-Prd-02|pve-lon-04|10.0.0.40|



3\. One country with multiple clusters at multiple sites (with 2 nodes each).



|Country|Site|Cluster|Node\_Name|IP|
|-|-|-|-|-|
|UK|London|LDN-PRD-01|pve-lon-01|10.0.0.10|
|UK	<br />|London|LDN-PRD-01|pve-lon-02|10.0.0.20|
|UK|London|LDN-PRD-02|pve-lon-03|10.0.0.30|
|UK|London|LDN-Prd-02|pve-lon-04|10.0.0.40|
|UK|Belfast|BEL-PRD-01|pve-bel-01|10.0.0.50|
|UK	<br />|Belfast|BEL-PRD-01|pve-bel-02|10.0.0.60|
|UK|Cardiff|CAR-PRD-01|pve-car-01|10.0.0.70|
|UK|Cardiff|CAR-Prd-01|pve-car-02|10.0.0.80|



3\. Standalone Nodes (you still need to define a cluster name for them in the excel even if they are standalone).



|Country|Site|Cluster|Node\_Name|IP|
|-|-|-|-|-|
|India|Mumbai|Standalone|pve-mum-01|10.0.0.10|
|India	<br />|Mumbai|Standalone|pve-mum-02|10.0.0.20|
|Canada|Montreal|Standalone|pve-mtl-01|10.0.0.30|
|Canada|Montreal|Standalone|pve-mtl-02|10.0.0.40|



* HyperGate builds your infrastructure map based on the logic of your Excel sheet. If you have a standalone machine, treat the machine's purpose as the 'Cluster Name' (As shown in above example) to keep your tree view organized and easy to navigate.



⚠️ **Data Discipline: The "Do's and Don'ts".**



To keep the Infrastructure Map clean, follow these rules strictly. The engine is powerful, but it's also precise:



1\. Case Sensitivity (The "Montreal" vs "montreal" Rule): The engine treats text exactly as it's written.



The Problem: If Row 1 says Canada and Row 2 says canada, you will see two separate country branches in the tree.

The Fix: Pick a standard (e.g., Title Case) and stick to it for all rows.



2\. Hidden Spaces (The "Invisible Bug"):


This was a big one for me.



The Problem: A cell containing "London " (with a space at the end) is not the same as "London". This causes "Ghost Branches" where clusters appear to be split for no reason.

The Fix: Ensure there are no leading or trailing spaces in your cells. The tool tries to trim them, but clean data is always better.



3\. Duplicate Node Names:



The Problem: If you name two different physical nodes pve-01 in the same cluster, the inventory logic might get confused when generating reports.



The Fix: Every Node Name within a cluster must be unique.



⚠️ Pro-Tip: I recommend using Hyphens (-) instead of spaces for Cluster and Node names (e.g., MTL-PROD instead of MTL PROD) to ensure maximum compatibility with the backend API calls.



