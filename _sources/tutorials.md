# Tutorial

:::{note}
For this tutorial we are using a slimmed down replication of 
[Neurobiological impact of nicotinic acetylcholine receptor agonists: An ALE meta-analysis of pharmacological neuroimaging studies](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4494985/).
:::

## Learning Goals

After this tutorial, you will gain a fundamental understanding of how to use Neurosynth Compose to conduct a meta-analysis. Specifically, you will learn about:

1. Creating a {term}`Project` on Neurosynth Compose.
2. Searching for {term}`studies <study>` on PubMed.
3. Adding {term}`studies <study>` to a {term}`project`.
4. Curating {term}`studies <study>` using [PRISMA](http://prisma-statement.org/) guidelines
5. Extracting and {term}`Annotating <annotation>` {term}`analyses <analysis>` within studies
6. Specifying a {term}`meta-analysis`
7. Executing a {term}`meta-analysis`
8. Displaying meta-analytic images
9. Interpreting meta-analytic results
10. Considerations for follow-up analyses.

We will be following Dr. Annie Lytical as she conducts a {term}`meta-analysis` on the effects of nicotine administration on brain activity, but is in an enormous rush to get it done before the end of the day.

## Story

```{epigraph}
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
align: center
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
This tutorial is not a recommendation on how one should choose a topic for {term}`meta-analysis`. One should give proper thought on the topic of their {term}`meta-analysis`, and have talked to their mentors and collaborators beforehand. Please see the [PRISMA statement](https://www.bmj.com/content/372/bmj.n71) and the [10 simple rules for neuroimaging meta-analyses](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5918306/).
Consider registering your {term}`meta-analysis` protocol on [PROSPERO](https://www.crd.york.ac.uk/prospero/).
:::

```{figure} ./figures/create_project.png
---
name: new project
---
Creating a new project
```

She typed the following information for name:
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

Dr. Lytical's next step is to search and curate the {term}`studies <study>` she wants to include in her {term}`meta-analysis`.

## Searching for studies

Dr. Lytical clicked within the box "Curation: Get Started", and was presented with
three options: "PRISMA Workflow", "Simple Workflow", and "Custom Workflow".

```{figure} ./figures/select_prisma.png
---
name: select prisma
---
Selecting the PRISMA workflow
```

Since Dr. Lytical is replicating a manually curated {term}`meta-analysis`, she selected the "PRISMA Workflow". [PRISMA](http://prisma-statement.org/), or Preferred Reporting Items for Systematic Reviews and Meta-Analyses, is a set of guidelines for conducting systematic reviews and meta-analyses.
While PRISMA encompasses the entire {term}`project` workflow, Dr. Lytical has the most agency
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

Remove duplicate {term}`studies <study>`
````

````{card}
{bdg-primary}`Screening`

Remove irrelevant {term}`studies <study>`
````

````{card}
{bdg-primary}`Eligibility`

Remove {term}`studies <study>` that do not meet inclusion criteria
or do not have retrievable information
````

````{card}
{bdg-primary}`Inclusion`

Double check the {term}`studies <study>` and view which {term}`studies <study>` will be included in the {term}`meta-analysis`
````

Dr. Lytical decided to use PubMed to search for {term}`studies <study>` for this {term}`meta-analysis`.

```{figure} ./figures/pubmed_main_page.png
---
name: pubmed main page
---
Pubmed landing page
```

Hopping over to PubMed, Dr. Lytical clicked on the advanced text below the main search box,
and put the following text in the advanced search box:

```
("fMRI" OR "PET" OR "neuroimaging" OR "Functional magnetic resonance imaging" OR "functional MRI") AND ("nicotine" OR "cigarette" OR "smok*" OR "DMXB-A") AND ("2011/01/01"[Date - Publication] : "2011/12/31"[Date - Publication])
```

Below is what her search looked like.

```{figure} ./figures/advanced_search_query_pubmed.png
---
name: advanced search for pubmed
---
Pubmed advanced search
```

She got the following results from her search.

```{figure} ./figures/search_results.png
---
name: search results for pubmed
---
Pubmed search results
```

She downloaded the results as a PMID file, by clicking on the save button.
She changed the selection to be "All Results", and selecting the PMID format.
This will download a text file with a PMID on each row.

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

We are only searching for {term}`studies <study>` in 2011 to keep the results shorter.
140 results! Oh no, that will still take too much time.
Luckily Dr. Lytical remembered that she had previously narrowed down a list of PubMed ids.
She found the file (linked below) and continued to the next step.

:::{important}
**[TUTORIAL PMID FILE](./data/tutorial_pmids.txt)**
:::

With the pmid file in hand, Dr. Lytical went back to neurostore and clicked on the "Import Studies" button
on the top right of the curation board page.

```{figure} ./figures/import_studies.png
---
name: import studies
---
Import studies into neurostore
```

When importing {term}`studies <study>`, Dr. Lytical needs to select a search source, which could be from
the Neurosynth Compose database, PubMed, a citation manager, or a manually inserted {term}`study`.
Since she searched on PubMed, she selected "Import Via PubMed ID List".


```{figure} ./figures/select_search_source.png
---
name: select search source
---
Select search source
```

Dr. Lytical uploaded the pmid file that she had downloaded from PubMed.
She could also copy and paste the pmids into the text box.

```{figure} ./figures/upload_pmid_file.png
---
name: upload pmid file
---
Upload the tutorial pmid file
```

She can now view all the {term}`studies <study>` she imported as a quick visual confirmation
the {term}`studies <study>` look correct.

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

All the imported {term}`studies <study>` are visible in the first column
of our PRISMA board: Identification.
The purpose of identification is to find duplicated {term}`studies <study>`,
which is more of a concern when multiple searches are included.
Since Dr. Lytical's only source was PubMed, it is unlikely there
are any duplicates.

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

Dr. Lytical was now presented with the list of {term}`studies <study>` that she had imported.
While the import stage has handled any obvious
duplicates, the Identification stage is where she will be able to identify any duplicates that were not caught automatically.
Luckily, there were no duplicates, so each {term}`study` was promoted to the next stage for screening.

## Screening

In this stage, Dr. Lytical is attempting to determine if the {term}`study` has any relevancy to her {term}`meta-analysis`.
For example, the {term}`study` could be about cannabis
or it could be about colorectal cancer, which are topics, outside the topic
of Dr. Lytical's {term}`meta-analysis`.
Please read the title and abstracts along with Dr. Lytical and determine whether each {term}`study` has relevancy to her {term}`meta-analysis`.

## Eligibility

With duplicates and relevancy resolved, Dr. Lytical is now ready to determine if the {term}`study` meets the eligibility criteria.
In this stage Dr. Lytical likely needs to read the methods
section of each {term}`study` and determine if it meets the eligibility criteria.
Each paper may take several minutes to evaluate, so Dr. Lytical will need to be patient and thorough.
"Wait!", Dr. Anna Lytical exclaims, what are my eligibility criteria!
Thankfully, the eligibility criteria are printed below.


### Eligibility criteria

We included {term}`studies <study>` in this {term}`meta-analysis` that: 1) employed fMRI or PET; 2) reported brain activity changes in stereotaxic coordinates (either Talairach or MNI space); 3) reported a set of coordinates (i.e., foci) from a within-subjects or between-subjects contrast assessing the effects of nAChR agonist administration (i.e., pharmacological administration or cigarette smoking) relative to a baseline condition (i.e., placebo administration or smoking-abstinence condition); and 4) examined brain activity using a cognitive or affective task paradigm or at rest (i.e., in the absence of explicit task demands). {term}`Studies <study>` examining functional connectivity, brain morphology, or neurochemistry were not included. Given the relatively modest but expanding corpus of literature regarding the impact of nAChR agonists on human brain function, no {term}`study` exclusions were made on the basis of participant age, neuropsychiatric condition, or statistical threshold considerations.


### Eligibility determination

While the eligibility criteria provide guidelines for inclusion and exclusion,
this does not mean the answer will be obvious for each paper. Indeed, there
are often disagreements between individuals reviewing the papers.
In this tutorial, however, Dr. Lytical only has you, and that is enough.

## Inclusion/Ingestion

Hooray, Dr. Lytical has reached a critical milestone in her {term}`meta-analysis` journey.
The {term}`studies <study>` that survived your critical eye are happily waiting in the inclusion column.
Dr. Lytical takes a quick look at the inclusion column to ensure no paper snuck through
that was not supposed to survive curation.
These {term}`studies <study>` are now ready to be ingested into a {term}`studyset` for use in Dr. Lytical's
{term}`meta-analysis`.

The ingestion process includes looking up the {term}`study` on Neurosynth Compose's database and asking
Dr. Lytical if she would want to use a pre-existing {term}`study` or create a new one.
If Dr. Lytical chooses to use a pre-existing {term}`study`, then she will inherit all the data that was already extracted from that {term}`study`, which will often include coordinates and will save her a lot of time during the extraction phase.
So if there is an option to select an existing {term}`study`, Dr. Lytical is highly motivated
to select it.

Once the {term}`studies <study>` are ingested, Dr. Lytical will be able to extract/edit coordinate data from each {term}`study` and label {term}`analyses <analysis>` for inclusion for her particular {term}`meta-analysis`.
These collective labels are called annotations.

Within the context of a {term}`meta-analysis`, Annotations can be explained as a way to categorize {term}`analyses <analysis>` within each {term}`study`.
For example, they can be categorized by task (e.g., Stroop, N-back, etc.), by modality (e.g., fMRI, PET, etc.), or by any other category that you want to use to filter the {term}`analyses <analysis>`.
For this replication, Dr. Lytical is interested in the effects of nAChR agonists on the brain, which can either be excitatory or inhibitory, so she adds both an "activation" and "deactivation" annotation column.
By default you will have an "include" column to help get you started.

## Extraction and Annotation

Extraction and annotation are integral to a {term}`meta-analysis`,
and, thankfully, the Neurosynth Compose database reduces the effort
for this process.

```{figure} ./figures/extraction_and_annotation.png
---
name: extraction and annotation
---
View of the extraction and annotation page on Neurosynth Compose
```

```{figure} ./figures/annotate_and_extract_study.png
---
name: annotate and extract study
---
View of a particular study for annotation and extraction.
```

```{figure} ./figures/annotation_view.png
---
name: annotation view
---
View of the annotations for a particular study
```

Dr. Lytical is on a roll.
She has now reached the extraction phase.
In this phase, Dr. Lytical will extract the data from each {term}`study`, specifically
coordinates and annotations.

In conjunction with annotating the {term}`analyses <analysis>`, Dr. Lytical will also need to extract and/or edit the coordinates for each analysis.
While Neurosynth Compose has many coordinates automatically extracted, Dr. Lytical will need to extract the data from some of the {term}`analyses <analysis>` Neurosynth Compose has not seen before.
Dr. Lytical is ecstatic that so many of the {term}`studies <study>` already have coordinates extracted from the {term}`analyses <analysis>`.

```{figure} ./figures/study_with_no_analyses.png
---
name: study with no analyses
---
Study with no analyses
```

For the rest, Neurosynth Compose provides an interface to add/edit coordinates.
Dr. Lytical can directly add the coordinates on the website, by copy/pasting the
coordinates into the platform.
It's often easiest to copy/paste the table into google sheets first,
and then select the coordinates to paste into Neurosynth Compose.


```{figure} ./figures/add_coordinates.png
---
name: add coordinates
---
Add coordinates
```

She skillfully add the coordinates for the remaining {term}`studies <study>` and is now ready to move on to the next stage.


## Meta-analysis specification

The {term}`meta-analysis` specification is the stage where many may
scratch their heads and look with confusion.
But not Dr. Anna Lytical, she came armed with the knowledge of
learning about the different algorithms and their nuances.

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

Dr. Lytical is now ready to select the {term}`analyses <analysis>` and specify the algorithm.
She clicks on the "Meta-Analysis Specification" button and is presented with a wizard that will guide her through the process.
She names this {term}`meta-analysis`: "nicotinic agonist activations".

For this particular {term}`meta-analysis` she chooses "included" and goes through a wizard
to specify the algorithmic parameters for her {term}`meta-analysis`.

```{figure} ./figures/select_column_activations.png
---
name: select column activations
---
Select column activations
```

Dr. Lytical is now ready to specify the algorithmic parameters for her {term}`meta-analysis`.
She chooses ALE (Activation Likelihood Estimation; {numref}`algorithm overview`) as the algorithm and selects
8mm as the kernel size {numref}`algorithm parameters`.

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

She selects the False Discovery Rate corrector (FDR) and selects "independent",
and 0.05 as the p-value threshold.

## Running the meta-analysis

With the {term}`analyses <analysis>` selected and the algorithm chosen and specified, Dr. Lytical is now ready to run the {term}`meta-analysis`.
She follows the google colab link and inserts the identifier that specifies the {term}`meta-analysis`.
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
She is running a relatively small {term}`meta-analysis` so she does not have to wait long
for the process to finish executing.

## interpreting the results

Dr. Lytical can hardly contain her excitement, but yet she must remain calm and collected,
otherwise she will not be able to interpret the results correctly.
It is important to remember what inferences you can and cannot make from a {term}`meta-analysis`.

Looking at the top of the generated report Dr. Lytical checks to see how many {term}`studies <study>`
were included in the {term}`meta-analysis` and checks to see if any {term}`studies <study>` were excluded.
None were excluded so she can move on to check the mask to ensure it has whole brain coverage.
Seeing the mask covers the whole brain, she moves on to check the peak coordinates reported from
all the {term}`analyses <analysis>` included in the {term}`meta-analysis`.
In this step, she can see which coordinates are outside the mask and if there is an unusual distribution
of coordinates (e.g., are they are all on the left side of the brain? are there many coordinates in white matter tracts?).

She confirms that the meta-analytic parameters she chose in the specification match what is in the report.
Then she can interactively view the results to see where the significant clusters are located.
Remembering her training, Dr. Lytical recalls the Activation Likelihood Estimation creates values that can be interpreted as the probability that a voxel is activated given the {term}`studies <study>` included in the {term}`meta-analysis`.
The Z-values she is looking at represent the significance of that activation relative to a baseline of the voxel's expected activation if all the foci were randomly distributed across the brain.
And the Z-scores have been corrected with FDR (False Discovery Rate) correction, to help control for false positives.

She identifies clusters in the Default Mode Network (DMN) and Executive Cognition Network (ECN). In the literature, these networks
are considered task negative and task positive networks, respectively.
Since we did not differentiate between whether the coordinates included in the {term}`meta-analysis` represented an increase or decrease in activation, Dr. Lytical cannot make any inferences about whether the nAChR agonists increased or decreased activation in these regions, merely that {term}`studies <study>` tended to report significant coordinates within these regions.
As a follow up analysis, Dr. Anna Lytical could label the {term}`analyses <analysis>` as either "activation" or "deactivation" and run a separate {term}`meta-analysis` for each category.

## Conclusion

Congratulations! You've ran your first meta-analysis and helped Dr. Lytical
keep her job.

You've accomplished a lot in this tutorial:
1. Created a {term}`Project` on Neurosynth Compose.
2. Searched for {term}`studies <study>` about nicotine on pubmed.
3. Added {term}`studies <study>` to a {term}`project` by importing them.
4. Curated {term}`studies <study>` using [PRISMA](http://prisma-statement.org/) guidelines within the four sections: Identification, Screening, Eligibility, and Inclusion.
5. Extracted and {term}`Annotated <annotation>` {term}`analyses <analysis>` within studies
6. Specified an ALE {term}`meta-analysis`.
7. Executed a {term}`meta-analysis` using google colab.
8. Displayed meta-analytic statistical images.
9. Interpreted meta-analytic results to validate and understand the meta-analysis.
10. Considerations for follow-up analyses to split up the analyses in different ways.


Dr. Lytical is planning on jumping right back in to create another Project
with her own ideas, maybe something about naturalistic data while watching Bee and
PuppyCat, she would gladly volunteer for that study...
