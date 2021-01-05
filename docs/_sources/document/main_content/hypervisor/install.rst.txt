.. jinja:: yaml_load
    
    {% import "/common_docs/jinja/macros.jinja" as macros %}

    {% set globals = {'heading_level': 1,'targets': []} %}
    {% set esx_hosts = hosts | selectattr('os._name', 'in', ['VMware vSphere ESXi']) | list %}
    {% set vc_hosts = hosts | selectattr('os._name', 'in', ['VMware vSphere vCenter']) | list %}

    {% if esx_hosts %}
        {% for host in esx_hosts %}

    {{ macros.create_heading(2,'VMware vSphere ESXi Deployment for **'+host['_name']+'**', true, ) }}

    {% include "/common_docs/jinja/intel/amt/remoteDesktop.jinja" %}
    {% include "/common_docs/jinja/vmware/vsphere/esxi/install.jinja" %}
    {% include "/common_docs/jinja/vmware/vsphere/esxi/postinstallConfig.jinja" %}

        {% endfor %}
    {% endif %}

    {% if vc_hosts %}
        {% for host in vc_hosts %}

    {{ macros.create_heading(2,'VMware vSphere vCenter Deployment for **'+host['_name']+'**', true, ) }}

    {% include "/common_docs/jinja/vmware/vsphere/vcenter/deploy_gui.jinja" %}
    {% include "/common_docs/jinja/vmware/vsphere/vcenter/configure_webgui.jinja" %}
    {% include "/common_docs/jinja/vmware/vsphere/vcenter/add_esxi_host_vcenter.jinja" %}
    {% include "/common_docs/jinja/vmware/vsphere/vcenter/license_webgui.jinja" %}

        {% endfor %}
    {% endif %}
