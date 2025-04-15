## 🔑 Manage REDCap API Keys Using an R Script

To simplify and centralize access to REDCap databases across team projects, save your personal REDCap API tokens in a script on your **OneDrive**, and use that script in all your shared R programs. This process is specific to the Northwestern IT ecosystem, in which all emplyees have a personal OneDrive file, and by saving an R file with all individual API tokens, that file can be used to input tokens into shared scripts rather than sharing tokens or consistantly deleting API keys from scripts. 

---

### 📁 Step 1: Create `redcap_api_info.R` on Your Person OneDrive

Save the following code in a file called `redcap_api_info.R` located in your personal OneDrive folder:

> Remove any tokens that do not apply to you.

```r
# Define variables needed for REDCap API pulls:
url <- "https://redcap.nubic.northwestern.edu/redcap/api/"

example1_token <- "***"  # Example 1 Database API Token
example2_token <- "***"  # Example 2 Database API Token
example3_token <- "***"  # Example 3 Database API Token
example4_token <- "***"  # Example 4 Database API Token
```

---

### 🧠 Step 2: Load the API Keys in Your R Programs

At the top of each R program, **source** your token file using the path to your OneDrive. The `od_loc` variable should be defined as shown in the [Write R Program Connecting to OneDrive](#) section.

```r
# Load API token variables from personal OneDrive
source(paste(od_loc, "redcap_api_info.R", sep = ""))
```

This ensures that your REDCap API keys are securely separated from the shared codebase, and lets team members independently manage their access credentials.

---

### ✅ Benefits

- 🔒 Keeps credentials private but accessible
- 🔄 Reusable across multiple R projects
- ⚙️ Works cross-platform using the shared `od_loc` logic

---

📄 **Note**: Make sure your OneDrive is synced locally for this to work. For more info, see the [OneDrive Setup Guide](#).
