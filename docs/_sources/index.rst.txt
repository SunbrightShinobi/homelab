.. jinja:: yaml_load

    ================================================================================
    |project| - (|git_repo|, |release|)
    ================================================================================

    .. only:: html

        .. image:: /images/FullColor_1280x1024_lightBG.png
            :scale: 10
            :alt: Binarylandscapes Consulting
            :align: center

    ---------------------
    Contents
    ---------------------

    .. toctree::
        :maxdepth: 5
        :numbered:
        :name: mastertoc
        :glob:

        document/main_content/contents

    ------------------
    Revision History
    ------------------

    .. tabularcolumns:: |>{\RaggedRight}p{\dimexpr 0.2\linewidth-2\tabcolsep}
                        |>{\RaggedRight}p{\dimexpr 0.2\linewidth-2\tabcolsep}
                        |>{\RaggedRight}p{\dimexpr 0.6\linewidth-2\tabcolsep}|

    .. list-table:: Revision History
        :header-rows: 1
        :class: longtable
        :name: revision_history
        :align: center

        * - **Date**
            - **Rev**
            - **Description**

        {% for revision in _document['revisionHistory'] %}

        * - {{ revision['date'] }}
            - {{ revision['rev'] }}
            - {% for change in revision['changes'] %}
            {{ change }}
            {% endfor %}

        {% endfor %}

    --------------
    To Do List
    --------------

    .. todolist::

    ---------------------
    Appendices
    ---------------------

    .. toctree::
        :maxdepth: 2
        :numbered:
        :name: appendices
        :glob:

        common_docs/appendices/acronym_list

    .. only:: html

        ---------
        Indexes
        ---------

        * :ref:`genindex`
        * :ref:`modindex`
        * :ref:`search`
