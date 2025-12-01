# Virus Spread Simulator Construction Kit  
*A hands-on SEIR modeling sandbox for epidemic learning, teaching, and rapid experimentation*

[![Python](https://img.shields.io/badge/python-3.8%2B-blue)]()
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)]()
[![License: GPL v3](https://img.shields.io/badge/license-GPLv3-green.svg)]()

[Luca Amore](https://www.lucaamore.com)  
[Blog post about this project](https://www.lucaamore.com/?p=1023)

![COVID-19](https://github.com/lookee/seir-model/blob/master/img/seir-simulation-luke.png?raw=true)

---

## 🎯 Overview

This project provides a set of interactive **SEIR-based epidemic models** implemented in Python notebooks.  
It allows exploration of infectious disease dynamics under different scenarios and assumptions:

- Basic SEIR transmission  
- COVID-19 extended dynamics  
- Malaria progression (vector-borne)

It is ideal for students, educators, and researchers wanting a practical sandbox to simulate, visualize, and modify infectious disease models.

---

## 📌 Table of Contents
- [SEIR Models](#seir-models)
- [COVID-19 (Metropolitan Milan)](#covid-19-metropolitan-milan)
- [Malaria](#malaria)
- [How to Use](#-how-to-use)
- [License](#-license)
- [References](#references)

---

## **SEIR MODELS**

The SEIR model can be schematically represented by:

![SEIR](https://github.com/lookee/seir-model/blob/master/img/SEIR_block_model.png?raw=true)

A standard SEIR compartmental model divides the population into:

| Compartment | Meaning                                      |
|------------|----------------------------------------------|
| S          | Susceptible                                  |
| E          | Exposed (infected but not yet infectious)    |
| I          | Infectious                                   |
| R          | Removed / Recovered                          |

---

## TOY VIRUS

Think of the Toy Virus example as the minimal working virus used to illustrate every modeling concept before layering in real-world complications.

![Block Model of a Simple Virus](https://github.com/lookee/seir-model/blob/master/img/SEIR_example_block_model.png?raw=true)

$$
\begin{cases}
\dfrac{\partial s(t)}{\partial t} = -\lambda s(t)i(t) \\
\dfrac{\partial e(t)}{\partial t} = \lambda s(t)i(t) - \dfrac{e(t)}{\xi} \\
\dfrac{\partial i(t)}{\partial t} = \dfrac{h}{\xi} e(t) - \dfrac{i(t)}{\mu} \\
\dfrac{\partial r(t)}{\partial t} = \dfrac{h}{\mu} i(t)
\end{cases}
$$

You can run and modify the simulation here:

👉 **[SEIR NOTEBOOK - TOY VIRUS](https://github.com/lookee/seir-model/blob/master/SEIR_model.ipynb)**

![COVID-19](https://github.com/lookee/seir-model/blob/master/img/toy-virus.png?raw=true)

---

## **COVID-19 (Metropolitan Milan)**

Extended SEIR model with asymptomatic and symptomatic branches, hospitalizations, deaths, NPIs, and vaccinations calibrated on the Metropolitan City of Milan (~3.2M inhabitants).

👉 **[COVID-19 NOTEBOOK](https://github.com/lookee/seir-model/blob/master/covid19_model.ipynb)**

![COVID-19 MODEL](https://github.com/lookee/seir-model/blob/master/img/covid19-model.png?raw=true)

This extended model includes:

- Symptomatic vs asymptomatic infectious classes  
- Hospitalization dynamics  
- Deaths and outcome tracking  
- Time-varying transmission (e.g. NPIs, lockdowns, vaccination effects)

---

## **MALARIA**

Vector-borne disease modeling inspired by malaria epidemiology, using an SEIR-style framework adapted to the specific characteristics of malaria transmission.

👉 **[MALARIA NOTEBOOK](https://github.com/lookee/seir-model/blob/master/malaria_model.ipynb)**

> This notebook demonstrates how the same compartmental modeling approach can be adapted to different infectious diseases by tuning parameters and model structure.

---

## 🧪 How to Use
Clone the repository and open the notebooks in Jupyter or Google Colab to explore and modify the models as you wish:

```bash
git clone https://github.com/lookee/seir-model.git
cd seir-model
pip install -r requirements.txt
jupyter notebook
```

Alternatively, you can open the notebooks directly in Google Colab for a more interactive experience. Enjoy experimenting with the models!

![Laboratory](https://github.com/lookee/seir-model/raw/master/img/model_secret_laboratory.png?raw=true)

---
## 📚 References

[Jennifer Ciarochi, 2020. "Modeling How Infectious Diseases like Coronavirus Spread"](https://triplebyte.com/blog/modeling-infectious-diseases)

[Blackwood, Julie C., and Lauren M. Childs. 2018. “An Introduction to Compartmental Modeling for the Budding Infectious Disease Modeler.”](https://www.tandfonline.com/doi/full/10.1080/23737867.2018.1509026)

[Desai, Rishi. n.d. “Understanding R Nought.” Khan Academy](https://www.khanacademy.org/science/health-and-medicine/current-issues-in-health-and-medicine/ebola-outbreak/v/understanding-r-nought?modal=1)

[Simulate HIV Infection](https://apmonitor.com/pdc/index.php/Main/SimulateHIV)

[Simulate Coupled Differential Equations in Python](https://youtu.be/zRMmiBMjP9o)

[Differential Equation in Action. Udacity Course](https://www.udacity.com/course/differential-equations-in-action--cs222)

