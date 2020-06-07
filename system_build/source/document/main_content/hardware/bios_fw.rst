.. jinja:: yaml_load
    
    {% import "/common_docs/jinja/macros.jinja" as macros %}

    {% set globals = {'heading_level': 1,'targets': []} %}
    {% set esx_hosts = hosts | selectattr('os._name', 'in', ['VMware vSphere ESXi']) | list %}
    {% set win10_hosts = hosts | selectattr('os._name', 'in', ['Microsoft Windows 10']) | list %}

    {% if hosts %}

    {{ macros.create_heading(2,'Hardware BIOS & Firmware Update/Configuration', true, ) }}

        {% for host in win10_hosts %}

    {{ macros.create_heading(3,'Hardware BIOS & Firmware Update/Configuration for **'+host['_name']+'**', true, ) }}

    {% include "/common_docs/jinja/dell/precision_3431/bios_update.jinja" %}

    {% include "/common_docs/jinja/dell/precision_3431/bios_configure.jinja" %}

        {% endfor %}

        {% for host in esx_hosts %}

    {{ macros.create_heading(3,'Hardware BIOS & Firmware Update/Configuration for **'+host['_name']+'**', true, ) }}

    {% include "/common_docs/jinja/dell/precision_3431/bios_update.jinja" %}

    {% include "/common_docs/jinja/dell/precision_3431/intel_amt_configure.jinja" %}

    {% include "/common_docs/jinja/dell/precision_3431/bios_configure.jinja" %}

        {% endfor %}
    {% endif %}

