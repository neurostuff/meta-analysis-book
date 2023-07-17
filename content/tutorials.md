# Tutorial

:::{note}
For this tutorial we are using a slimmed down replication of 
[Neurobiological impact of nicotinic acetylcholine receptor agonists: An ALE meta-analysis of pharmacological neuroimaging studies](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4494985/).
:::

## Learning Goals

After this tutorial, you will gain a fundamental understanding of how to use Neurosynth Compose to conduct a meta-analysis. Specifically, you will learn about:

1. Creating a {term}`Project` on Neurosynth Compose.
2. Searching for {term}`studies <study>` on pubmed.
3. Adding studies to a {term}`project`.
4. Curating studies using [PRISMA](http://prisma-statement.org/) guidelines
5. Extracting and {term}`Annotating <annotation>` analyses within studies
6. Specifying a {term}`meta-analysis`
7. Executing a {term}`meta-analysis`
8. Displaying meta-analytic images
9. Interpreting meta-analytic results
10. Considerations for follow-up analyses

We will be following Dr. Annie Lytical as she conducts a meta-analysis on the effects of nicotine administration on brain activity, but is in an enormous rush to get it done before the end of the day.

## Story

```
Dear Dr. Lytical,

We hope you have settled in to your new Post Doctoral position at the University of NeuroSyncratic.
It has now been a month since you started and we are excited to see what you have been working on.
We would like you to send us a report of your progress so far by end of day today.

Sincerely,
Your Boss: Dr. I. M. Portant

```

"Oh no!, I haven't done anything yet!" Dr. Lytical exclaimed.
"I knew binge watching [Bee and Puppy Cat](https://www.youtube.com/watch?v=dop4MTlf_zc) repeatedly was a bad idea."
(And yet, she did not regret it.)
She had to think of something fast.
Dr. Lytical scrambled to her computer and opened up the browser.
She knew some of her colleagues had been using Neurosynth Compose to conduct {term}`meta-analyses <meta-analysis>`, and thought she might be able to use it to get some results, and then she could add to her {term}`meta-analysis` once she had more time.
She navigated to [compose.neurosynth.org](https://compose.neurosynth.org) and was immediately struck by the beautiful design.
She clicked on the "Sign In" button and was greeted with a login screen.

```{figure} ./figures/login_screen.png
---
height: 550px
name: login
---
Neurosynth Compose login screen
```

She signed in with her Google account and was taken to the dashboard.
The most prominent element of the dashboard was {term}`Projects <Project>`.

```{figure} ./figures/project_page.png
---
width: 900px
name: projects
---
Neurosynth Compose projects page
```

"Perfect!" she thought, I need to create a {term}`project`.
She clicked on the "New Project" button and a popup appeared asking for a name
and description of the {term}`project`.
"Bugger!", Dr. Lytical cursed under her breath, she had not decided on a topic for her {term}`meta-analysis`.
Quickly, she rummaged through her drawer of meta-analyses she had read recently,
"Imitation is the sincerest form of flattery", she mumbled to no one in particular as she leaved through
the publications.
One stuck out to her: [`Neurobiological impact of nicotinic acetylcholine receptor agonists`](https://pubmed.ncbi.nlm.nih.gov/25662104/).
She had taken a neurobiology class in college and the class had a whole section on nicotinic acetylcholine
receptors.
Dr. Lytical was in business.

:::{important}
This tutorial is not a recommendation on how one should choose a topic for meta-analysis. One should give proper thought on the topic of their meta-analysis, and have talked to their mentors and collaborators beforehand. Please see the [PRISMA statement](https://www.bmj.com/content/372/bmj.n71) and the [10 simple rules for neuroimaging meta-analyses](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5918306/).
Consider registering your meta-analysis protocol on [PROSPERO](https://www.crd.york.ac.uk/prospero/).
:::

```{figure} ./figures/create_project.png
---
name: new project
---
Creating a new project
```

She the following information for name:
```
Replication of: Neurobiological impact of nicotinic acetylcholine receptor agonists
```

and description:
```
Nicotinic acetylcholine receptor (nAChR) agonists augment cognition among cigarette smokers and nonsmokers, yet the systems-level neurobiological mechanisms underlying such improvements are not fully understood. Aggregating neuroimaging results regarding nAChR agonists provides a means to identify common functional brain changes that may be related to procognitive drug effects.
```

After inserting the name and description, she clicked "Create"
and was redirected to the following page

```{figure} ./figures/new_project_view.png
---
name: new project view
---
View of the new project.
```

Dr. Lytical's next step is to search and curate the studies she wants to include in her meta-analysis.

## Searching for studies

Dr. Lytical clicked within the box "Curation: Get Started", and was presented with
three options: "PRISMA Workflow", "Simple Workflow", and "Custom Workflow".

```{figure} ./figures/select_prisma.png
---
name: select prisma
---
Selecting the PRISMA workflow
```

Since Dr. Lytical is replicating a manually curated meta-analysis, she selected the "PRISMA Workflow". [PRISMA](http://prisma-statement.org/), or Preferred Reporting Items for Systematic Reviews and Meta-Analyses, is a set of guidelines for conducting systematic reviews and meta-analyses.
While PRISMA encompasses the entire project workflow, Dr. Lytical has the most agency
on how strictly she will abide to the guidelines during the curation process.

```{figure} ./figures/empty_curation_board.png
---
name: empty curation board
---
View of the empty curation board.
```

She was presented with an empty curation board, with 4 sections: "Identification",
"Screening", "Eligibility", and "Included".
````{card}
{bdg-primary}`Identification`

Remove duplicate studies
````

````{card}
{bdg-primary}`Screening`

Remove irrelevant studies
````

````{card}
{bdg-primary}`Eligibility`

Remove studies that do not meet inclusion criteria
or do not have retrievable information
````


Dr. Lytical decided to use Pubmed to search for studies for this meta-analysis.

```{figure} ./figures/pubmed_main_page.png
---
name: pubmed main page
---
Pubmed landing page
```

Hopping over to Pubmed, Dr. Lytical put the following in the advanced search box:

```
("fMRI" OR "PET" OR "neuroimaging" OR "Functional magnetic resonance imaging" OR "functional MRI") AND ("nicotine" OR "cigarette" OR "smok*" OR "DMXB-A") AND ("2011/01/01"[Date - Publication] : "2011/12/31"[Date - Publication])
```

Below is what her search looked like.

```{figure} ./figures/advanced_search_query_pubmed.png
---
name: advanced search for pubmed
---
Pubmed Advanced Search
```

She got the following results from her search.

```{figure} ./figures/search_results.png
---
name: search results for pubmed
---
Pubmed search results
```

With the results in hand, she downloaded the results as a CSV file.

```{figure} ./figures/download_search_results.png
---
name: download search results
---
Download search results
```


```{figure} ./figures/pmid_file.png
---
name: example pmid file
---
Example pmid file
```

We are only searching for studies in 2011 to keep the results shorter.
140 results! Oh no, that will still take too much time.
Luckily Dr. Lytical remembered that she had previously narrowed down a list of pubmed ids.
She found the file and continued to the next step.

:::{important}
**[TUTORIAL PMID FILE](./data/tutorial_pmids.txt)**
:::

```{figure} ./figures/import_studies.png
---
name: import studies
---
Import studies into neurostore
```

```{figure} ./figures/select_search_source.png
---
name: select search source
---
Select search source
```

```{figure} ./figures/upload_pmid_file.png
---
name: upload pmid file
---
Upload the tutorial pmid file
```

```{figure} ./figures/display_imported_stubs.png
---
name: display imported studies
---
Display imported studies
```

Dr. Lytical named the search
"manually filtered nicotinic acetylcholine receptor agonists pubmed search" and clicked "Next".
There were no duplicates, so she clicked "Complete Import".

## Identification


```{figure} ./figures/identification.png
---
name: identification
---
Identification stage of curation
```

```{figure} ./figures/study_view_curation.png
---
name: study view in identification stage
---
Study view in identification stage
```

Dr. Lytical was now presented with the list of studies that she had imported.
While the import stage has handled any obvious
duplicates, the Identification stage is where she will be able to identify any duplicates that were not caught automatically.
Luckily, there were no duplicates, so each study was promoted to the next stage for screening.

## Screening

In this stage, Dr. Lytical is attempting to determine if the study has any relevancy to her meta-analysis.
For example, the study could be about cannabis
or it could be about colorectal cancer, which are topics Dr. Lytical is not interested in.
Now Dr. Lytical takes a closer look at the title and abstract of each study and identifies whether each study has relevancy to her meta-analysis.

## Eligibility

With duplicates and relevancy resolved, Dr. Lytical is now ready to determine if the study meets the eligibility criteria.
In this stage Dr. Lytical needs to read the methods
section of each study and determine if it meets the eligibility criteria.
Each paper may take several minutes to evaluate, so Dr. Lytical will need to be patient and thorough.


### Eligibility criteria

We included studies in this meta-analysis that: 1) employed fMRI or PET; 2) reported brain activity changes in stereotaxic coordinates (either Talairach or MNI space); 3) reported a set of coordinates (i.e., foci) from a within-subjects or between-subjects contrast assessing the effects of nAChR agonist administration (i.e., pharmacological administration or cigarette smoking) relative to a baseline condition (i.e., placebo administration or smoking-abstinence condition); and 4) examined brain activity using a cognitive or affective task paradigm or at rest (i.e., in the absence of explicit task demands). Studies examining functional connectivity, brain morphology, or neurochemistry were not included. Given the relatively modest but expanding corpus of literature regarding the impact of nAChR agonists on human brain function, no study exclusions were made on the basis of participant age, neuropsychiatric condition, or statistical threshold considerations.


## Ingestion

Hooray, Dr. Lytical has reached a critical milestone in her meta-analysis journey.
Once the studies are ingested, Dr. Lytical will be able to extract the data from each study.

The ingestion process includes looking up the study on Neurosynth Compose's database and asking
Dr. Lytical if she would want to use a pre-existing study or create a new one.
If Dr. Lytical chooses to use a pre-existing study, then she will inherit all the data that was already extracted from that study, which will often include coordinates and will save her a lot of time during the extraction phase.

## Extraction

```{figure} ./figures/extraction_and_annotation.png
---
name: extraction and annotation
---
Extraction and annotation stage
```

```{figure} ./figures/annotate_and_extract_study.png
---
name: annotate and extract study
---
Annotate and extract study
```

```{figure} ./figures/annotation_view.png
---
name: annotation view
---
Annotation view
```


Dr. Lytical is on a roll.
She has now reached the extraction phase.
In this phase, Dr. Lytical will extract the data from each study, which will often include
coordinates and annotations.

Within the context of a meta-analysis, Annotations can be explained as a way to categorize analyses within each study.
For example, they can be categorized by task (e.g., Stroop, N-back, etc.), by modality (e.g., fMRI, PET, etc.), or by any other category that you want to use to filter the analyses.
For this replication, Dr. Lytical is interested in the effects of nAChR agonists on the brain, which can either be excitatory or inhibitory, so she adds both an "activation" and "deactivation" column.
By default you will have an "include" column to help get you started.

In conjunction with annotating the analyses, Dr. Lytical will also need to extract and/or edit the coordinates for each analysis.
While Neurosynth Compose has many coordinates automatically extracted, Dr. Lytical will need to extract the data from some of the analyses Neurosynth Compose has not seen before.
Dr. Lytical is ecstatic that so many of the studies already have coordinates extracted from the analyses.

```{figure} ./figures/study_with_no_analyses.png
---
name: study with no analyses
---
Study with no analyses
```

For the rest, Neurosynth Compose provides an interface to add/edit coordinates.
Dr. Lytical can either directly add the coordinates on the website or she can upload a csv file with extracted coordinates.


```{figure} ./figures/add_coordinates.png
---
name: add coordinates
---
Add coordinates
```

She skillfully add the coordinates for the remaining studies and is now ready to move on to the next stage.


## Meta-analysis specification

```{figure} ./figures/proceed_meta_analysis.png
---
name: proceed meta-analysis
---
The meta-analysis stage.
```

```{figure} ./figures/create_meta_analysis.png
---
name: create meta-analysis
---
Create meta-analysis
```

```{figure} ./figures/name_meta_analysis.png
---
name: name meta-analysis
---
Name the meta-analysis
```

Dr. Lytical is now ready to select the analyses and specify the algorithm.
She clicks on the "Meta-Analysis Specification" button and is presented with a wizard that will guide her through the process.
She names this meta-analysis: "nicotinic agonist activations".

For this particular meta-analysis she chooses "activation" and goes through a wizard
to specify the algorithmic parameters for her meta-analysis.

```{figure} ./figures/select_column_activations.png
---
name: select column activations
---
Select column activations
```

Dr. Lytical is now ready to specify the algorithmic parameters for her meta-analysis.
She chooses ALE (Activation Likelihood Estimation) as the algorithm and selects
8mm as the kernel size.

```{figure} ./figures/algorithm_overview.png
---
name: algorithm overview
---
Algorithm overview
```

```{figure} ./figures/algorithm_parameters.png
---
name: algorithm parameters
---
Algorithm parameters
```

```{figure} ./figures/corrector_parameters.png
---
name: corrector parameters
---
Corrector parameters
```

```{figure} ./figures/parameter_review.png
---
name: parameter review
---
Parameter review
```

She selects the Family Wise Error rate corrector (FWE) and uses montecarlo simulation to estimate the null distribution.
She chooses 10000 iterations and 0.05 as the p-value threshold.

## Running the meta-analysis

With the analyses selected and the algorithm chosen and specified, Dr. Lytical is now ready to run the meta-analysis.
She follows the google colab link and inserts the identifier that specifies the meta-analysis.
she wants to run.


```{figure} ./figures/colab_button.png
---
name: colab button
---
Colab button
```

```{figure} ./figures/notebook_code.png
---
name: notebook code
---
Notebook code
```

She executes the analysis and waits for the results.
She is running a relatively small meta-analysis so she does not have to wait long
for the process to finish executing.

## interpreting the results

Dr. Lytical can hardly contain her excitement, but yet she must remain calm and collected,
otherwise she will not be able to interpret the results correctly.
It is important to remember what inferences you can and cannot make from a meta-analysis.

Looking at the top of the generated report Dr. Lytical checks to see how many studies
were included in the meta-analysis and checks to see if any studies were excluded.
None were excluded so she can move on to check the mask to ensure it has whole brain coverage.
Seeing the mask covers the whole brain, she moves on to check the peak coordinates reported from
all the analyses included in the meta-analysis.
In this step, she can see which coordinates are outside the mask and if there is an unusual distribution
of coordinates (e.g., they are all on the left side of the brain, or many appear to be in white matter tracts).

She confirms that the meta-analytic parameters she chose in the specification match what is inside the report.
Then she can interactively view the results to see where the significant clusters are located.
Remembering her training, Dr. Lytical recalls the Activation Likelihood Estimation creates values that can be interpreted as the probability that a voxel is activated given the studies included in the meta-analysis.
The z-values she is looking at represent the significance of that activation relative to a baseline of the voxel's expected activation if all the foci were randomly distributed across the brain.
And the z-scores have been corrected with FDR (False Discovery Rate) correction, to help control for false positives.

She finds some interesting clusters in the DMN region and ECN networks. These networks
are considered task negative and task positive networks respectively.
Since we did not differentiate between whether the coordinates included in the meta-analysis represented an increase or decrease in activation, Dr. Lytical cannot make any inferences about whether the nAChR agonists increased or decreased activation in these regions, merely that studies tended to report significant coordinates within these regions.
As a follow up analysis, Dr. Anna Lytical could label the analyses as either "activation" or "deactivation" and run a separate meta-analysis for each category.

