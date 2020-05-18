.. jinja::

    {% import "/common_docs/jinja/macros.jinja" as macros %}

    {{ macros.create_heading(2,"Parts Lists and Specifications", true, ) }}

    {% include "/common_docs/jinja/dell/precision_3431/specs.jinja" %}

    {% include "/common_docs/jinja/dell/precision_3431/parts.jinja" %}

