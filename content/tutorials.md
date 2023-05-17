# Tutorials

For this tutorial we are using a slimmed down replication of the Nicotine Administration Meta-Analysis.
In this tutorial you will gain experience with the following:

1. Creating a project
2. searching for studies on pubmed
3. adding studies to a project
4. curating studies using PRISMA guidelines
5. extracting data from analyses within studies
6. specifying a meta-analysis
7. running a meta-analysis
8. viewing meta-analysis results
9. interpreting meta-analysis results
10. deciding on follow-up analyses

We will be following Dr. Annie Litical as she conducts a meta-analysis on the effects of nicotine administration on brain activity, but is in an enourmous rush to get it done before the end of the day.

## Story

```
Dear Dr. Litical,

We hope you have settled in to your new Post Doctoral position at the University of NeuroSynth.
It has now been a month since you started and we are excited to see what you have been working on.
We would like you to send us a report of your progress so far by end of day today.

Sincerely,
Your Boss: Dr. I. M. Portant

```

"Oh no!, I haven't done anything yet!" Dr. Litical exclaimed.
"I knew binge watching [Bee and Puppy Cat](https://www.youtube.com/watch?v=dop4MTlf_zc) repeatedly was a bad idea."
(And yet, she did not regret it.)
She had to think of something fast.
Dr. Litical scrambled to her computer and opened up the browser.
She knew some of her colleagues had been using NeuroSynth-Compose to conduct meta-analyses, and thought she might be able to use it to get some results, and then she could add to them once she had more time.
She navigated to [compose.neurosynth.org](https://compose.neurosynth.org) and was immediately struck by the beautiful design.
"Wow, this is so much better than the old NeuroSynth!" she thought.
"Whoever designed this must be have put a lot of thought and care into the interface."
She clicked on the "Sign In" button and was greeted with a login screen.
She signed in with her Google account and was taken to the dashboard.
The most prominant element of the dashboard was "Projects".
"perfect!" she thought, I need to create a project.
She clicked on the "New Project" button and a popup appeared asking for a name
and description of the project.
"Bugger!", Dr. Litical cursed under her breath, she had not decided on a topic for her meta-analysis.
Quickly, she rummaged through her drawer of meta-analyses she had read recently,
"Imitation is the sincerest form of flattery", she mumbled to no one in particular as she leaved through
the publications.
One stuck out to her: `Neurobiological impact of nicotinic acetylcholine receptor agonists`.
She had taken a neurobiology class in college and the class had a whole section on nicotinic acetylcholine
receptors.
Dr. Litical was back in business.
NOTE: One should have given proper thought on what their meta-analysis is about, and have talked to their mentors and collaborators beforehand.
She the following information for name:
```
Replication of: Neurobiological impact of nicotinic acetylcholine receptor agonists
```
and description:
```
Nicotinic acetylcholine receptor (nAChR) agonists augment cognition among cigarette smokers and nonsmokers, yet the systems-level neurobiological mechanisms underlying such improvements are not fully understood. Aggregating neuroimaging results regarding nAChR agonists provides a means to identify common functional brain changes that may be related to procognitive drug effects.
```
## Searching for studies

Hopping over to Pubmed, Dr. Litical put the following in the advanced search box:
```
("fMRI" OR "PET" OR "neuroimaging" OR "Functional magnetic resonance imaging" OR "functional MRI") AND ("nicotine" OR "cigarette" OR "smok*" OR "DMXB-A") AND ("2011/01/01"[Date - Publication] : "2011/12/31"[Date - Publication])
```

We are only searching for studies in 2011 to keep the results shorter.
140 results! Oh no, that will still take too much time.
Luckily Dr. Litical remembered that she had previously narrowed down a list of pubmed ids.
She found the file and continued to the next step.

** Here is the FILE **

Dr. Litical named the search
"manually filtered nicotinic acetylcholine receptor agonists pubmed search" and clicked "Next".
There were no duplicates, so she clicked "Complete Import".

## Identification

Dr. Litical was now presented with the list of studies that she had imported.
While the import stage has handled any obvious
duplicates, the Identification stage is where she will be able to identify any duplicates that were not caught automatically.
Luckily, there were no duplicates, so each study was promoted to the next stage for screening.

## Screening

In this stage, Dr. Litical is attempting to determine if the study has any relevancy to her meta-analysis.
For example, the study could be about cannibas
or it could be about corectal cancer, which are topics Dr. Litical is not interested in.
Now Dr. Litical takes a closer look at the title and abstract of each study and identifies whether each study has relevancy to her meta-analysis.

## Eligibility

With duplicates and relevancy resolved, Dr. Litical is now ready to determine if the study meets the eligibility criteria.
In this stage Dr. Litical needs to read the methods
section of each study and determine if it meets the eligibility criteria.
Each paper may take several minutes to evaluate, so Dr. Litical will need to be patient and thorough.


### Eligibility criteria

We included studies in this meta-analysis that: 1) employed fMRI or PET; 2) reported brain activity changes in stereotaxic coordinates (either Talairach or MNI space); 3) reported a set of coordinates (i.e., foci) from a within-subjects or between-subjects contrast assessing the effects of nAChR agonist administration (i.e., pharmacological administration or cigarette smoking) relative to a baseline condition (i.e., placebo administration or smoking-abstinence condition); and 4) examined brain activity using a cognitive or affective task paradigm or at rest (i.e., in the absence of explicit task demands). Studies examining functional connectivity, brain morphology, or neurochemistry were not included. Given the relatively modest but expanding corpus of literature regarding the impact of nAChR agonists on human brain function, no study exclusions were made on the basis of participant age, neuropsychiatric condition, or statistical threshold considerations.


## Ingestion

Horray, Dr. Litical has reached a critical milestone in her meta-analysis journey.
Once the studies are ingested, Dr. Litical will be able to extract the data from each study.

The ingestion process includes looking up the study on NeuroSynth-Compose's database and asking
Dr. Litical if she would want to use a pre-existing study or create a new one.
If Dr. Litical chooses to use a pre-existing study, then she will inherit all the data that was already extracted from that study, which will often include coordinates and will save her a lot of time during the extraction phase.

## Extraction

Dr. Litical is on a roll.
She has now reached the extraction phase.
In this phase, Dr. Litical will extract the data from each study, which will often include
coordinates and annotations.

Annotations are the method you will filter
the analyses you include in your meta-analysis.
By default you will have an "include" column,
but you are free to add as many columns as you want for different categories of annotations.
For example, in this meta-analysis, Dr. Litical is interested in the effects of nAChR agonists on the brain, which can either be excitatory or inhibitory, so she adds both an "activation" and "deactivation" column.

While NeuroSynth-Compose has many studies already extracted, Dr. Litical will need to extract the data from some of the studies herself.

NeuroSynth-Compose provides an interface to add the coordinates yourself.

## Selection

Dr. Litical is now ready to select the studies she wants to include in her meta-analysis.
Since she already annotated all the studies in her meta-analysis, she can now filter the studies by the annotations she created.

## Meta-analysis specification

Dr. Litical is now ready to specify the algorithmic parameters for her meta-analysis.
Dr. Litical is not trying to rock the boat so she specifies a run of the mill 
ALE meta-analysis.

## Running the meta-analysis

She follows the google colab link and inserts the code that specifies the meta-analysis
she wants to run.
