
.. image:: https://github.com/Valires/er-evaluation/actions/workflows/python-package.yaml/badge.svg
        :target: https://github.com/Valires/er-evaluation/actions/workflows/python-package.yaml

.. image:: https://badge.fury.io/py/er-evaluation.svg
        :target: https://badge.fury.io/py/er-evaluation

.. image:: https://readthedocs.org/projects/er-evaluation/badge/?version=latest
        :target: https://er-evaluation.readthedocs.io/en/latest/?version=latest
        :alt: Documentation Status


🔍 ER-Evaluation: An End-to-End Evaluation Framework for Entity Resolution Systems
==================================================================================

**ER-Evaluation** is a Python package for the evaluation of entity resolution (ER) systems. It provides data structure definitions, summary statistics, visualizations, error analysis tools, and statistically principled performance estimators.

💻 Installation
---------------

Install the released version from PyPI using:

.. code:: bash

    pip install er-evaluation

Or install the development version using:

.. code:: bash

    pip install git+https://github.com/Valires/er-evaluation.git


📖 Documentation
----------------

Please refer to the documentation website `er-evaluation.readthedocs.io <https://er-evaluation.readthedocs.io/en/latest>`_.

🖼️ Usage Examples
-----------------

Please refer to the `User Guide <https://er-evaluation.readthedocs.io/en/latest/userguide.html>`_ or our `Visualization Examples <https://er-evaluation.readthedocs.io/en/latest/visualizations.html>`_ for a complete usage guide.

In summary, here's how you might use the package.

1. Import your predicted disambiguations and reference benchmark dataset.

.. code::

        import er_evaluation as ee

        predictions, reference = ee.load_pv_disambiguations()

2. Plot `summary statistics <https://er-evaluation.readthedocs.io/en/latest/02-summary_statistics.html>`_ and compare disambiguations.

.. code::

        ee.plot_summaries(predictions)

.. image:: plot_summaries.png
   :width: 400

.. code::

        ee.plot_comparison(predictions)

.. image:: plot_comparison.png
   :width: 400

3. Define sampling weights and `estimate performance metrics <https://er-evaluation.readthedocs.io/en/latest/03-estimating_performance.html>`_.

.. code::

        ee.plot_estimates(predictions, {"sample":reference, "weights":"cluster_size"})

.. image:: plot_estimates.png
   :width: 400

4. Perform `error analysis <https://er-evaluation.readthedocs.io/en/latest/04-error_analysis.html>`_ using cluster-level explanatory features and cluster error metrics.

.. code::


        ee.make_dt_regressor_plot(
                y,
                weights,
                features_df,
                numerical_features,
                categorical_features,
                max_depth=3,
                type="sunburst"
        )

.. image:: plot_decisiontree.png
   :width: 400

💭 Development Philosophy
-------------------------

**ER-Evaluation** is designed to be a unified source of evaluation tools for entity resolution systems, adhering to the Unix philosophy of simplicity, modularity, and composability. The package contains Python functions that take standard data structures such as pandas Series and DataFrames as input, making it easy to integrate into existing workflows. By importing the necessary functions and calling them on your data, you can easily use ER-Evaluation to evaluate your entity resolution system without worrying about custom data structures or complex architectures.

📜 Citation
-----------

Please acknowledge the publications below if you use ER-Evaluation:

- Binette, Olivier. (2022). ER-Evaluation: An End-to-End Evaluation Framework for Entity Resolution Systems. Available online at `github.com/Valires/ER-Evaluation <https://github.com/Valires/ER-Evaluation>`_
- Binette, Olivier, Sokhna A York, Emma Hickerson, Youngsoo Baek, Sarvo Madhavan, Christina Jones. (2022). Estimating the Performance of Entity Resolution Algorithms: Lessons Learned Through PatentsView.org. arXiv e-prints: `arxiv:2210.01230 <https://arxiv.org/abs/2210.01230>`_
- Upcoming: "A Statistical Evaluation Framework for Black-Box Entity Resolution Systems With Application to Inventor Name Disambiguation"

📝 Public License
-----------------

* `GNU Affero General Public License v3 <https://www.gnu.org/licenses/agpl-3.0.en.html>`_
