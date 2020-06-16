.. jinja:: yaml_load
    
    {% import "/common_docs/jinja/macros.jinja" as macros %}

    {% set globals = {'heading_level': 1,'targets': []} %}
    {% set esx_hosts = hosts | selectattr('os._name', 'in', ['VMware vSphere ESXi']) | list %}

    {% if esx_hosts %}

        {% for host in esx_hosts %}

    {{ macros.create_heading(2,'VMware vSphere ESXi Deployment for **'+host['_name']+'**', true, ) }}

    {% include "/common_docs/jinja/dell/precision_3431/intel_amt_remoteDesktop.jinja" %}
    {% include "/common_docs/jinja/vmware/vsphere/esxi/install.jinja" %}
    {% include "/common_docs/jinja/vmware/vsphere/esxi/postinstallConfig.jinja" %}

        {% endfor %}
    {% endif %}
