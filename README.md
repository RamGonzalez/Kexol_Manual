# Kexol: Our Lab Server and Most Precious Resource!

## Management:
- **Jacob Cervantes** ([jacob.cervantes@cinvestav.mx](mailto:jacob.cervantes@cinvestav.mx)): High-level IT support
- **Santiago Medina** ([santiago.medina@cinvestav.mx](mailto:santiago.medina@cinvestav.mx)): General server admin, resource allocation, and usage monitoring.
- **Jose Antonio Corona** ([jose.corona@cinvestav.mx](mailto:jose.corona@cinvestav.mx)): Software administration and installation support

> **Note**: If you notice any issues with Kexol (e.g., performance concerns, unusual noises), contact the management team immediately.

---

## Organization
Everyone has access to certain directories on Kexol. Feel free to add programs and datasets, but avoid deleting shared resources. Key directories include:

- `/data/programs`
- `/data/programs/bin`
- `/data/projects`
- `/data/reference_panels`
- `/data/scratch/` – Temporary file storage
- `/data/data_vault/` – One directory per user (more on this later)

> **Important**: If you add reference panels, you are **obliged** to include a `README` with details about the data's origin, type, and any quality control/post-processing performed.

For sudo privileges to install new programs or update versions, contact the management team.

---

## Kexol Capabilities
- **Storage**: 51 TB
- **Processing Power**: 36 cores, 72 threads

### Backup (NAS System)
- **Storage**: 32 TB
- **Backup Schedule**: Performed every 15 days by Jacob

---

## Running Jobs on Kexol
- **No Job Scheduler (yet)**: Jobs can be submitted via the command line using `parallel` and/or `screen`.
- **Job Coordination**: Fill out the **[designated form](https://docs.google.com/spreadsheets/d/1CH23JU266zqPQu-ZciToqBL6L75N_9c6RlR6U2DE38o/edit?usp=sharing)** to avoid overlapping with others’ tasks.

> Remember, all lab members use Kexol and may need to run analyses simultaneously.

---

## `data_vault` - Backup for Users
The `data_vault` is the centralized storage and backup system for data and results generated by lab members. It ensures that all critical data is securely stored and easily accessible with a structured, collaborative organization and periodic backup.

> **Note**: Avoid duplicating data between home directories and other directories. To maintain storage integrity, use symbolic links (soft links) instead. To create a soft link, use the `ln -s` command:

```bash
ln -s /data/projects/projectx /users/userX/projectx
```

**Directory Structure**

The data_vault is organized by user, with each user having data and results folders. Below is the typical organization:

```
data_vault/
│
├── user1/
│   ├── data/
│   │   ├── dataset_A/
│   │   │   ├── raw_data/           # Raw data files
│   │   │   ├── processed_data/     # Preprocessed data files
│   │   │   ├── metadata/           # Metadata and documentation
│   │   │   └── README.md           # Documentation for dataset_A
│   │   └── dataset_B/
│   │       ├── raw_data/
│   │       ├── processed_data/
│   │       ├── metadata/
│   │       └── README.md           # Documentation for dataset_B
│   ├── results/
│   │   ├── project_A/
│   │   │   ├── result1/            # Results from first analysis
│   │   │   ├── result2/            # Results from second analysis
│   │   │   └── figures/            # Generated figures and charts
│   │   └── project_B/
│   │       ├── result1/
│   │       ├── result2/
│   │       └── figures/
├── user2/
│   └── ...
```

Each user has two main folders within data_vault:

- `data`: For storing important datasets. Each dataset must include a README file detailing its contents for others, including collaborators and future lab members, to understand the data.
- `results`: For storing important results requiring backup. Organize it in a way that suits your project structure.

### Scratch

-	Do not duplicate kexol!
-	Temporary Storage: Use this directory for intermediate data files that can be regenerated if needed. We will periodically clear this folder to free up space.

Note: If you are no longer going to use your temporary or intermediate data in a bioinformatics step it is advisable to delete them once you are done using them. Many intermediate data are easily re-generated, so they do not need to take up storage space.

### Home Directory Guidelines `data/users/you`

-	Primary Workspace: This is your main directory for running your analyses.
-	Code and Scripts: Store all personal code and scripts here.
-	Program Installation: You can install your own programs using [conda/mamba](https://github.com/conda-forge/miniforge) within this directory.
-	Backup Responsibility: This directory is not backed up; please manage your own backups.
-	Storage Limit: The maximum quota for this directory is *1 Tb*.

**It is suggested to each user to have good data management**

-	Establish a standard directory structure (e.g., raw_data/, processed_data/, results/, scripts/) and use it consistently.
-	Implements processes for data cleaning and deletion of temporary files, keeping storage under control.
-	Document in detail the workflow, tools, software versions and parameters used.
-	Use clear file and directory names with specific conventions (e.g., project_date_description).


### Confidentiality Clause for Members of the MorenoLab
All members of the MorenoLab, including fellows, students, interns, postdocs, administrative staff, and any other individuals with access to information generated or handled in the laboratory, commit to maintaining absolute confidentiality regarding the lab's internal data. 
This commitment includes, but is not limited to:

- Genomic data, confidential information, and any personal data of participants in research projects.
- Information about projects, analyses, methodologies, preliminary results, and any other internal data of the lab.
  
Under no circumstances, and without exception, may this information be transferred to third parties, nor shared partially or entirely through digital means or other formats. The confidentiality obligation extends to any circumstance outside the laboratory and remains in effect even after the individual's relationship with the laboratory has ended.
Failure to comply with this clause will result in corresponding observations and/or sanctions according to the conditions of the material transfer agreements and data protection agreements governing each data set obtained or generated by MorenoLab.


