![Example](Images/GeneExpression.png "Example")

GeneExpressionPCA [![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=EFQXNQ7UYXYKW&source=url)
=======

<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#project-description">Project description</a>
    </li>
    <li>
      <a href="#files-and-data-description">Files and data description</a>
    </li>
    <li>
      <a href="#biochemical-foundations">Biochemical Foundations</a>
      <ul>
        <li><a href="#mTOR-pathway">mTOR pathway</a></li>
        <li><a href="#conditions">Conditions</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting started</a>
      <ul>
        <li><a href="#running">Running</a></li>
        <li><a href="#principal-component-analysis">Principal Component Analysis</a></li>
      </ul>
    </li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
    <li><a href="#issues">Issues</a></li>
    <li><a href="#license">License</a></li>
  </ol>
</details>

## Project description

The goal of this project in quantitative genomics was to identify core pathways that underlie myopathy and
evaluate differences in gene expressions of mTORC1 in different treatment conditions and in the different subjects.

The signaling pathway regulating the activity of the mammalian target of rapamycin complex 1 (mTORC1)
controls skeletal muscle homeostasis, which is determined by the difference in the rates of protein synthesis and
degradation. 

:star2: Highlights:

1. An effect on gene expression levels from the treatment of Rapamycin was found
2. Key genes in the molecular
   pathway of mTOR could be identified
3. Dimensionality reduction by PCA made the data easier to process
4. The K-means
   algorithm allowed to cluster the subjects and conditions by similarity

## Files and data description

**File structure:**

```
.
├── Gene Expression PCA.ipynb     # Jupyter Notebook with Data Analysis                                         
├── GeneExpressionTable.tsv       # Gene expression data
├── Images                        # Images
│   ├── ConditionPCA.png            # Plot of 3 first principal components by condition
│   ├── GeneExpression.png          # Header image
│   └── mTOR.jpg                    # mTOR pathway
└── * README.md                   # Project overview and instructions                    
```

## Biochemical Foundations

### mTOR pathway

The signaling pathway regulating the activity of the mammalian ```target of rapamycin complex 1 (mTORC1)``` controls
skeletal muscle homeostasis, which is determined by the difference in the rates of protein synthesis and degradation.
In the skeletal muscle, mTORC1 activation occurs in response to a variety of signals, including growth factors,
nutrients, energy state and mechanical load.

To study the function of mTORC1 in the skeletal muscle, the laboratory of Dr. Markus Rüegg (Biozentrum) has developed
a ```mouse model called TSCmKO```, in which the ```TORC1 inhibitor Tsc1 was selectively deleted``` in skeletal muscles.
It was found that these mice develop precocious sarcopenia, characterized by fragmentation of the neuromuscular
junction, progressive loss of muscle mass and loss of muscle force.

<p align="center"><img src="Images/mTOR.jpg" width="200"></p>


Treatment of TSCmKO mice with ```rapamycin```, an mTORC1 inhibitor, ameliorated the myopathy.
To identify core pathways that underlie myopathy in TSCmKO mice, ```mRNA-seq samples``` from EDL muscle of TSCmKO mice
and wild-type mice of the age of 3 months (young phase in both TSCmKO and wild-type mice) and 9 months (adult phase in
wild-type mice and sarcopenic phase in TSCmKO mice) in combination with rapamycin treatment were generated and sequenced
at the Quantitative Genomics facility of the Biozentrum.

### Conditions

The table called “GeneExpressionTable.tsv” contains the information about the expression of 117 genes in log2[TPM] units
measured in the Musculus extensor digitorum longus of the following mice:

* Condition 1: 5 replicates of 3 months old wild-type mice
* Condition 2: 5 replicates of 3 months old wild-type mice treated with rapamycin
* Condition 3: 5 replicates of 3 months old TSCmKO mice
* Condition 4: 5 replicates of 3 months old TSCmKO mice treated with rapamycin
* Condition 5: 5 replicates of 9 months old wild-type mice
* Condition 6: 5 replicates of 9 months old wild-type mice treated with rapamycin
* Condition 7: 5 replicates of 9 months old TSCmKO mice
* Condition 8: 5 replicates of 9 months old TSCmKO mice treated with rapamycin

## Getting Started


### Running

To run or interact with the code, run the following command from the command line (CLI):

~~~
jupyter lab
~~~

In case you still have installed the old version of Jupyter you might still use:

~~~
jupyter notebook
~~~

From your browser you can then access the ```notebook```.

A ```notebook``` is a shareable document that combines computer code, plain language descriptions, data, rich
visualizations like 3D models, charts, graphs and figures, and interactive controls.

### Principal Component Analysis

![Principal Component Analysis](Images/ConditionPCA.png)

The PCA was performed in both directions (conditions and genes). The first three Principal Components were examined and
the variance explained by it was calculated.
The replicates were clustered with a k-means algorithm according to their expression levels.


## Acknowledgments

* The data was provided by the Quantitative Genomics facility of the Biozentrum at the University of Basel.

## Issues

Found a bug? Want more features? Find something missing in the documentation? Let us know! Please don't hesitate
to [file an issue](https://github.com/thierrygrimm/GeneExpressionPCA/issues/new) and make a recommendation.

## License

```
GeneExpressionPCA - Principal Component Analysis of Gene Expression data

The MIT License (MIT)

Copyright (c) 2019 Thierry Grimm

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software ("GeneExpressionPCA") and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
```
