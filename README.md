# PlacesQA
Main Repository for Muralidharan et al., "PlacesQA: Towards Automatic Answering of Questions on the Web"

## [PlacesQA: Towards Automatic Answering of Questions on the Web. Srikanth Muralidharan, Akash Abdu Jyothi, Nelson Nauata, Fred Tung, Greg Mori. Arxiv Version](https://www.arxiv.org/)

## Contents
1. [Abstract](abstract)
1. [Task](#task)
1. [Dataset](#dataset)
1. [Model](#model)
1. [Experiments](#experiments)
1. [License and Citation](#license-and-citation)

## Abstract

Web users often post questions: "Does hotel X have a pool?", "Is museum Y wheelchair accessible?". The potential to automate the answering process presents an exciting challenge for AI systems, with many practical applications. However, to the best of our knowledge, there are not yet any public datasets for general question answering on the web. In this paper, we introduce the PlacesQA dataset, which contains 9,750 questions and answers about 750 unique places, including hotels, museums and nightlife venues, derived from questions asked by real users of travel websites.  This dataset serves as a testbed for general question answering.  For concreteness, we also provide sets of 73,148 and 181,266 images from these 750 places, obtained via web searches.  We show that images of these places on the web provide a rich source of information that can be potentially leveraged by an automatic question answering agent.

## Task

<img src="https://github.com/sri3705/placesQA/blob/master/images/qa_pull.jpg" alt="Our Task" height="400" >

**Figure 1.** This paper takes a first step towards general question answering on the web (middle), in which an AI agent is given a user question and is tasked
with acquiring relevant images (and other complementary modes of information) from the web to produce an accurate answer. Our PlacesQA dataset consists of
"canonical" questions and answers covering 750 unique places, including hotels, museums, and nightlife venues. The visual QA example is from
[AntolICCV'15](https://arxiv.org/pdf/1505.00468v6.pdf).

<img src="https://github.com/sri3705/placesQA/blob/master/images/QAexample.jpg" alt="PlacesQA example" height="400" >

**Figure 2.** A demonstrative example of real world questions and answers, where Google image search results provide evidence for the answers.

## Dataset

#### You could download the Google Search Images [here](https://arxiv.org).
#### You could download the Facebook Images [here](https://arxiv.org).

Dataset Statistics

|Category|Number of Places|No. of Categorical Questions|
|:---:|:---:|:---:|
|Hotels|250|18|
|Museums|250|15|
|Nightlife|250|6|

**Table 1.** Statistics of the PlacesQA dataset.



## Model

<img src="https://github.com/sri3705/placesQA/blob/master/images/qa_model.png" alt="Generalized Set pooling model" height="400" >

**Figure 3.** Left:  We  propose a new permutation-invariant fusion operator for sets that generalizes common pooling approaches, such as max, mean, and
“max-min” pooling,and that can be learned end-to-end. Right: Late fusion model with generalized setpooling.

## Experiments

<table>
  <tr>
    <td><b>Method</b></td>
    <td><b>Accuracy</b></td>
    <td><b>Wins vs. Losses</b></td>
    <td><b>Accuracy</b></td>
    <td><b>Wins vs. Losses</b></td>
  </tr>
  <tr>
  	<td></td>
    <td colspan="2"><center><b>Hotels</b></center></td>
    <td colspan="2"><center><b>Museums</b></center></td>
  </tr>
  <tr>
    <td>Majority</td>
    <td>72.1</td>
    <td>n/a</td>
    <td>70.2</td>
    <td>n/a</td>
  </tr>
  <tr>
    <td>Max Pooling</td>
    <td>72.2</td>
    <td>3 vs. 2</td>
    <td>69.1</td>
    <td>0 vs. 5</td>
  </tr>
  <tr>
    <td>Mean Pooling</td>
    <td>73.5</td>
    <td>5 vs. 1</td>
    <td>69.4</td>
    <td>1 vs. 2</td>
  </tr>
  <tr>
    <td>Generalized(Ours)</td>
    <td>74.9</td>
    <td>7 vs. 1</td>
    <td>69.5</td>
    <td>1 vs. 3</td>
  </tr>
  <tr>
  	<td></td>
    <td colspan="2"><center><b>Nightlife</b></center></td>
    <td colspan="2"><center><b>Overall</b></center></td>
  </tr>
  <tr>
    <td>Majority</td>
    <td>64.0</td>
    <td>n/a</td>
    <td>70.1</td>
    <td>n/a</td>
  </tr>
  <tr>
    <td>Max Pooling</td>
    <td>63.7</td>
    <td>0 vs. 1</td>
    <td>69.7</td>
    <td>3 vs. 8</td>
  </tr>
  <tr>
    <td>Mean Pooling</td>
    <td>64.0</td>
    <td>1 vs. 2</td>
    <td>70.4</td>
    <td>7 vs. 5</td>
  </tr>
  <tr>
    <td>Generalized(Ours)</td>
    <td>66.0</td>
    <td>3 vs. 0</td>
    <td><b>71.4</b></td>
    <td><b>11 vs. 4</b></td>
  </tr>
</table>

**Table 2.** Summary of the results obtained using traditional set fusion methods and ourlearned generalized set fusion using Google search images. Wins (or losses) indicates the number of questions for which the method performs better (or worse) than answeringthe majority answer (yes/no) for a particular question.

<table>
  <tr>
    <td><b>Method</b></td>
    <td><b>Accuracy</b></td>
    <td><b>Wins vs. Losses</b></td>
    <td><b>Accuracy</b></td>
    <td><b>Wins vs. Losses</b></td>
  </tr>
  <tr>
  	<td></td>
    <td colspan="2"><center><b>Hotels</b></center></td>
    <td colspan="2"><center><b>Museums</b></center></td>
  </tr>
  <tr>
    <td>Majority</td>
    <td>72.1</td>
    <td>n/a</td>
    <td>70.2</td>
    <td>n/a</td>
  </tr>
  <tr>
    <td>Max Pooling</td>
    <td>72.7</td>
    <td>3 vs. 2</td>
    <td>69.9</td>
    <td>0 vs. 1</td>
  </tr>
  <tr>
    <td>Mean Pooling</td>
    <td>72.5</td>
    <td>4 vs. 2</td>
    <td>69.8</td>
    <td>0 vs. 2</td>
  </tr>
  <tr>
    <td>Generalized(Ours)</td>
    <td>74.3</td>
    <td>8 vs. 3</td>
    <td>70.0</td>
    <td>2 vs. 3</td>
  </tr>
  <tr>
  	<td></td>
    <td colspan="2"><center><b>Nightlife</b></center></td>
    <td colspan="2"><center><b>Overall</b></center></td>
  </tr>
  <tr>
    <td>Majority</td>
    <td>64.0</td>
    <td>n/a</td>
    <td>70.1</td>
    <td>n/a</td>
  </tr>
  <tr>
    <td>Max Pooling</td>
    <td>63.7</td>
    <td>1 vs. 1</td>
    <td>70.3</td>
    <td>4 vs. 4</td>
  </tr>
  <tr>
    <td>Mean Pooling</td>
    <td>64.0</td>
    <td>1 vs. 1</td>
    <td>70.1</td>
    <td>5 vs. 5</td>
  </tr>
  <tr>
    <td>Generalized(Ours)</td>
    <td>63.7</td>
    <td>1 vs. 1</td>
    <td><b>71.1</b></td>
    <td><b>11 vs. 7</b></td>
  </tr>
</table>

**Table 3.** Summary of the results obtained using traditional set fusion methods and ourlearned generalized set fusion using Facebook images. Wins (or losses) indicates the number of questions for which the method performs better (or worse) than answeringthe majority answer (yes/no) for a particular question.

## License and Citation

Source code is released under the **BSD 2-Clause license**

If you are using our dataset, please cite:

###### Webpage inspired from [Ibrahim et al. CVPR2016](https://github.com/mostafa-saad/deep-activity-rec).
