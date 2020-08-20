.. jinja:: yaml_load
    
    {% import "/common_docs/jinja/macros.jinja" as macros %}

    {% set globals = {'heading_level': 1,'targets': []} %}
    {% set esx_hosts = hosts | selectattr('os._name', 'in', ['VMware vSphere ESXi']) | list %}
    {% set win10_hosts = hosts | selectattr('os._name', 'in', ['Microsoft Windows 10']) | list %}

    {% if esx_hosts %}

    {{ macros.create_heading(2,"Hardware Assembly", true, ) }}

        {% for host in esx_hosts if host['hardware']['model'] in ['3431 SFF Workstation'] %}

    {% include "/common_docs/jinja/dell/precision_3431/phys_assy.jinja" %}

        {% endfor %}

        {% for host in esx_hosts if host['hardware']['model'] in ['NUC NUC9VXQNX'] %}

    {% include "/common_docs/jinja/intel/nuc9vxqnx/phys_assy.jinja" %}

        {% endfor %}

    {% endif %}
