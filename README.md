#OAI_IBX

Once bootstrapped, deploy the MySQL charm then the oai-hss charm:

EPC charms
juju deploy mysql
juju deploy --repository=/home/mozart/charms  local:trusty/oai-hss
juju deploy --repository=/home/mozart/charms  local:trusty/oai-epc
juju deploy --repository=/home/mozart/charms  local:trusty/oai-IBX

Add a relation between oai-epc and oai-hss:

juju add-relation mysql oai-hss
juju add-relation oai-epc oai-hss
juju add-relation oai-epc oai-IBX


To have a look at the hss output:

juju ssh oai-hss/0
cat /srv/.out
