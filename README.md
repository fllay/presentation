# srsran5G

### HWs needed

1. USRP devices. Ettus B210 is used in this set up.
2. A computer to run software stacks. Intel Gen 11 CPU should be fine.
3. UEs. Since we will used 5G Stand alone (SA) mode, most COTS phones will disable SA mode and, hence, we need, somehow, enable SA. ZTE MU5002 is simple to switch to SA mode and it worrk very well. Another device is, https://www.quectel.com/product/5g-rm50xq-series. It can be used with Raspberry Pi via USB3 using this waveshare adapter, https://www.waveshare.com/wiki/USB_TO_M.2_B_KEY. 
4. SIM Card reader/writer. Any will be OK

### Softwares needed
1. Open5Gs: 5G Core network
2. srsRAN_Project: gNB SA implementation.


### SIM Card
SIM Card is sysmoISIM-SJA2 from https://www.sysmocom.de/products/sim/sysmousim/index.html. 

|IMSI	|ICCID	|ACC	|PIN1	|PUK1	|PIN2	|PUK2	|Ki	|OPC	|ADM1	|KIC1	|KID1	|KIK1	|KIC2	|KID2	|KIK2	|KIC3	|KID3	|KIK3
| ---  | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|999700000062710	|8988211000000627102	|0001	|1863	|60656842	|7188	|69439472	|0B0B97D8586F3E1DE59D0578247C448D	|958254FECC8B3062FE01BF8C054677CF	|57910110	|ACA89091EFBA1D9DDD579FF23BCF46D2	|5DB06EFC3FFC8019B919455638EFA7AB	|F9800E73708AFD6923741989581BD755	|025558C332319F627C047EB8873C2514	|FB6C8AF247047D0676CC07C41932BE2E	|A96886F051D1F9A89041D12A8337250E	|87F8B66D6CA879AAA6D90AF0729BB343	|0EAE945547BAAB8D2671341D5045BE9B	|875546A3F15622E87A2C1419A7E18D18|
|999700000062711	|8988211000000627110	|0002	|9273	|80898657	|2581	|45431615	|D2F199A52AE9D3E415AAFD6655AD3F88	|410E9BB1834729971619E4D714D29B0A	|34061030	|F16439C77BFD0DC82E3453B472E6F473	|872598184337F6184C76D9E0EF8CCAEB	|B942CCAB1326D81B584160421E87CC70	|D136DCD03C2CBB50D59DB7C8B13D83E5	|27E13714856403458C1FBA15126D8C8D	|0951027029E9B7DF31E52C32406D7EDB	|CBA5A3E57674CA7E11F39BFD7E34C854	|CF9FDBA6DA97E8A6B5E76EC35D52A895	|49E8183DA60F2EE9E7507F75F2A68E95|
|999700000062712	|8988211000000627128	|0004	|8330	|26544562	|3188	|95209499	|13C3845F6212C9AD945665C835508CC0	|B884FD8F3497D1CBA3997208A81A4AA7	|36645353	|F9B3E413EF34180FD29C4FBB7DB04188	|BAC70E5C5BEF8D6E20F8FA1EA68EE0EF	|925C4077C9F155C7AEFF417374D10E57	|D386248F970F9DB0CB816A16587F75C4	|B792130A4A18C875097C0909997BFAF0	|9B2D255ADBEDDA2F4871BC9EFEAC9BBF	|288619DB6D727097C3A3B09EEEE4EB8D	|D54819B9964C7E10B71CF7C19124652B	|73346CAD76D6882941C730553A3BFD50|
|999700000062713	|8988211000000627136	|0008	|2481	|43215893	|5679	|21192366	|96E5235D7BD18E48BEF1B85521383C4E	|B1C0A05123C419D615B71EC0F8CE13AB	|73947583	|BAEFEE018E08B0DE276DCF03900BE2AF	|B2037C9475B7C9A2D8637F8B9651B835	|AED8AB5736726DB4BF6CF1FE44E61BF6	|EF00A3344612955BC3144E4DF8C719D4	|A42E9EBDFB3768C98AFEED6154E375F7	|240A034AE19677D51B1CB19DD5F63503	|6AC9B3640FD1FD90D50B43004C72C0A4	|EEA71035E53F67E7266E2C954212E6BC	|55CADF364D70E23D7ADFA510902ABFC2|
|999700000062714	|8988211000000627144	|0010	|9353	|57390501	|9336	|63122917	|DF8CBC862DB172C13CF09C37D7077009	|0357A1719313FE31EA8112131810C98F	|76782966	|676FF8C1E63C9B5E42440BD2CAB904A9	|012F2D53A84DD2A49B5EB3DF909150D8	|AE2A7F7BBC1D90798642D14C1836A4F6	|F4D6F15DFAE71D630929FF47A6A4DEF8	|EF7184E65444042B2FC483F60F7E9A1F	|16D5AA4B7ADD2BB651E7B4AA17AFF8CA	|A40F63E77B2030BBC395F2B273706E3E	|A3AB60E7035882F0749C580E72CFF258	|C00189E62A613AEBAA3D62F503E79CF0|
|999700000062715	|8988211000000627151	|0020	|9485	|21058360	|4872	|96519362	|E27DB5641388DC88023383DF5B401EDB	|8D69C7534358D38261B6C259B80D3E98	|68964860	|286CB70291B4E834D9BA920732CDF591	|FDBC115504FCC08F0D63185695FE37E9	|132475092A918257375F1D887AFDAE4F	|757C941FBD2A28F26CF0FE5E2AC5CC0E	|15FE9B2C1A2A31CEE3CE58CEF5B0DF96	|397F4A5A0C526957E1F3318B367126D0	|AB7EEC36E89AEA1867FF156021927ADB	|2DE9C29710AB2B525557DEA1DA8C55FC	|839A9F164252E43764EBB26DC6614CD7|
|999700000062716	|8988211000000627169	|0040	|1464	|31198887	|2057	|36373760	|F359B8166EF46A372C88206B4462A324	|6DCF65673267D500311D018623921072	|41623193	|3862501C98CBBD5152A6CDBAF9BD2434	|E80CD41BBBC89490042942CF27CB297B	|3D6141749CEB1F752B31A734E1E45CBC	|F23E009CB9E7E5079C7ADB05580E979F	|E47CCF8AD44E69557FAF0EB80BF6A6B7	|D98A7BEE33BB4CDF610C124AB98D6F07	|36BC12C5136B7FD96CA3779C6BE02956	|49471E50B41842C95614D4328F192068	|B52AB6D87E61E924E155D42FE8E3C2EA|
|999700000062717	|8988211000000627177	|0080	|3284	|96140939	|9643	|93743379	|028220E005F873F1A3284F42372B2988	|43189F0995996E7E3679A066D24CEDED	|28160161	|1183A8DB6724D3E2A74A75A3A62B92ED	|4B7DD9C10DC3DFE773DB599BD727DB9E	|FAC3A5060796B04CE55AA51F4256E967	|17306A88BCDDBB2616462DF486696980	|AC816E351D5D182DDB26F90D86306017	|B5E8CE7827E40E5919A85F7C5914B1DE	|EA0EA0C3F684B22D138D6824E286DCE6	|D30D39E10FBFCF16A304AB5A15D85CB4	|170CC01E43B52D37DA4D09F2CFB5AE70|
|999700000062718	|8988211000000627185	|0100	|6127	|10427798	|6198	|23000926	|F977E20E697D40B490705AEADE114FE0	|F69529E7DED8F8E43778D009E5D489B7	|90356141	|5BC9015E4E096DAD5CB0373F96AF62A4	|8601A153D1158185113FD671BD43C58B	|66BC2351B1AA119F49C11173CBC0C6AC	|CEB29AE0E2517E66A39E6BAE3E8A7F8E	|FE59FBA49A16817FB3C66908220A7319	|762B4058A6899BD1DDF7B2D435BA39BA	|6DFAC54B3C4DADCA8F3E15692200D117	|A70216CAF2EA3EFAAF4C44A58F7C002B	|948D229E5A5F827A79D591F2F6BAE13C|
|999700000062719	|8988211000000627193	|0200	|5640	|25025736	|1752	|46086423	|BEC6CEAECF3A07451282A63FE32C3D8A	|DC30FF0D150098F8F0D3F9FB5537AD72	|96170539	|613BCEAE8CB3F8EE5BEBD7AF47E19B73	|EA046F17FCB1A4FFA54E70DB9305C849	|4602678689B82831CD7D49B6431AE55E	|AEBF0E8647F3799DA00F00CB1941FCEF	|246C031FE66C05DDE1B753FBF7199515	|65E67D61D2F122DFF88F76AE6DE08495	|C91FA25B7FFFF24CD85E69850554D6B8	|B0BACD46371DC420FA0ADAB4DEAFF583	|9C917F1A5E5CFF85FDBA12E6E59B936F|
|


In order to use the SIM card with srsrRAN Project. The SIM card will need to be modified by using the following script. 

### SIM Card script

```
# script to be used with pySim-shell.py which is part of the Osmocom pysim package,
# found at https://osmocom.org/projects/pysim/wiki
set echo true

# this script will deactivate all 5G related services and files.  This can be used
# in case you do not wish to use any 5G services, or you do not wish to configure
# the 5G specific files on the USIM card.  The card will then behave like a 3G USIM
# without any 5G capability, using the default fall-back mechanisms specified by 3GPP.

# TODO: add your card-specific ADM pin at the end of the verify_adm line below
verify_adm XXXXX
# Key Provisioning
select MF
select ADF.USIM 
select DF.5GS 
select EF.SUCI_Calc_Info 
update_binary_decoded '{ "prot_scheme_id_list": [ {"priority": 0, "identifier": 2, "key_index": 1}, {"priority": 1, "identifier": 1, "key_index": 2}, {"priority": 2, "identifier": 0, "key_index": 0}], "hnet_pubkey_list": [ {"hnet_pubkey_identifier": 27, "hnet_pubkey": "0272DA71976234CE833A6907425867B82E074D44EF907DFB4B3E21C1C2256EBCD1"}, {"hnet_pubkey_identifier": 30, "hnet_pubkey": "5A8D38864820197C3394B92613B20B91633CBD897119273BF8E4A6F4EEC0A650"}]}'


# Routing Indicator
select MF
select ADF.USIM 
select DF.5GS 
select EF.Routing_Indicator
update_binary 0071ffff

# Service Table
select MF
select ADF.USIM 
select EF.UST 
ust_service_deactivate 124
ust_service_deactivate 125
```

The script can be save as a file and then it can be executed by using pysim using the following command

`./pySim-shell.py -p0 --script ./scripts/srsran.script`

`pySim-shell` can be obtained from https://github.com/osmocom/pysim


### Open5GS Config file 
`sample.yaml` in `/home/pi/src/open5gs/build/configs` is used by `/home/pi/src/open5gs/build/tests/app/5gc`
```
db_uri: mongodb://localhost/open5gs

logger:

sbi:
    server:
      no_tls: true
      cacert: /home/pi/src/open5gs/build/configs/open5gs/tls/ca.crt
      key: /home/pi/src/open5gs/build/configs/open5gs/tls/testserver.key
      cert: /home/pi/src/open5gs/build/configs/open5gs/tls/testserver.crt
    client:
      no_tls: true
      cacert: /home/pi/src/open5gs/build/configs/open5gs/tls/ca.crt
      key: /home/pi/src/open5gs/build/configs/open5gs/tls/testclient.key
      cert: /home/pi/src/open5gs/build/configs/open5gs/tls/testclient.crt

parameter:
#    no_nrf: true
#    no_scp: true
#    no_amf: true
#    no_smf: true
#    no_upf: true
#    no_ausf: true
#    no_udm: true
#    no_pcf: true
#    no_nssf: true
#    no_bsf: true
#    no_udr: true
#    no_mme: true
#    no_sgwc: true
#    no_sgwu: true
#    no_pcrf: true
#    no_hss: true
#    use_mongodb_change_stream: true
# listen_on: 127.0.0.2
mme:
    freeDiameter:
      identity: mme.localdomain
      realm: localdomain
      listen_on: 127.0.0.2
      no_fwd: true
      load_extension:
        - module: /home/pi/src/open5gs/build/subprojects/freeDiameter/extensions/dbg_msg_dumps.fdx
          conf: 0x8888
        - module: /home/pi/src/open5gs/build/subprojects/freeDiameter/extensions/dict_rfc5777.fdx
        - module: /home/pi/src/open5gs/build/subprojects/freeDiameter/extensions/dict_mip6i.fdx
        - module: /home/pi/src/open5gs/build/subprojects/freeDiameter/extensions/dict_nasreq.fdx
        - module: /home/pi/src/open5gs/build/subprojects/freeDiameter/extensions/dict_nas_mipv6.fdx
        - module: /home/pi/src/open5gs/build/subprojects/freeDiameter/extensions/dict_dcca.fdx
        - module: /home/pi/src/open5gs/build/subprojects/freeDiameter/extensions/dict_dcca_3gpp/dict_dcca_3gpp.fdx
      connect:
        - identity: hss.localdomain
          addr: 127.0.0.8

    s1ap:
      - addr: 127.0.0.2
    gtpc:
      - addr: 127.0.0.2
    metrics:
      addr: 127.0.0.2
      port: 9090
    gummei:
      plmn_id:
        mcc: 999
        mnc: 70
      mme_gid: 2
      mme_code: 1
    tai:
      plmn_id:
        mcc: 999
        mnc: 70
      tac: 7
    security:
        integrity_order : [ EIA2, EIA1, EIA0 ]
        ciphering_order : [ EEA0, EEA1, EEA2 ]

    network_name:
        full: Open5GS

sgwc:
    gtpc:
      - addr: 127.0.0.3
    pfcp:
      - addr: 127.0.0.3

smf:
    sbi:
      - addr: 127.0.0.4
        port: 7777
    pfcp:
      - addr: 127.0.0.4
    gtpc:
      - addr: 127.0.0.4
      - addr: ::1
    gtpu:
      - addr: 127.0.0.4
      - addr: ::1
    metrics:
      addr: 127.0.0.4
      port: 9090
    subnet:
      - addr: 10.45.0.1/16
      - addr: 2001:db8:cafe::1/48
    dns:
      - 8.8.8.8
      - 8.8.4.4
      - 2001:4860:4860::8888
      - 2001:4860:4860::8844
    mtu: 1400
    freeDiameter:
      identity: smf.localdomain
      realm: localdomain
      listen_on: 127.0.0.4
      no_fwd: true
      load_extension:
        - module: /home/pi/src/open5gs/build/subprojects/freeDiameter/extensions/dbg_msg_dumps.fdx
          conf: 0x8888
        - module: /home/pi/src/open5gs/build/subprojects/freeDiameter/extensions/dict_rfc5777.fdx
        - module: /home/pi/src/open5gs/build/subprojects/freeDiameter/extensions/dict_mip6i.fdx
        - module: /home/pi/src/open5gs/build/subprojects/freeDiameter/extensions/dict_nasreq.fdx
        - module: /home/pi/src/open5gs/build/subprojects/freeDiameter/extensions/dict_nas_mipv6.fdx
        - module: /home/pi/src/open5gs/build/subprojects/freeDiameter/extensions/dict_dcca.fdx
        - module: /home/pi/src/open5gs/build/subprojects/freeDiameter/extensions/dict_dcca_3gpp/dict_dcca_3gpp.fdx
      connect:
        - identity: pcrf.localdomain
          addr: 127.0.0.9

#
#  <For Indirect Communication with Delegated Discovery>
#
#  o (Default) If you do not set Delegated Discovery as shown below,
#
#    sbi:
#      - addr: 127.0.0.5
#        port: 7777
#
#    - Use SCP if SCP avaiable. Otherwise NRF is used.
#      => App fails if both NRF and SCP are unavailable.
#
#    sbi:
#      - addr: 127.0.0.5
#        port: 7777
#    discovery:
#      delegated: auto
#
#  o To use SCP always => App fails if no SCP available.
#      delegated: yes
#
#  o Don't use SCP server => App fails if no NRF available.
#      delegated: no
#
amf:
    sbi:
      - addr: 127.0.0.5
        port: 7777
    ngap:
      - addr: 127.0.0.2
    metrics:
      addr: 127.0.0.5
      port: 9090
    guami:
      - plmn_id:
          mcc: 999
          mnc: 70
        amf_id:
          region: 2
          set: 1
    tai:
      - plmn_id:
          mcc: 999
          mnc: 70
        tac: 7
    plmn_support:
      - plmn_id:
          mcc: 999
          mnc: 70
        s_nssai:
          - sst: 1
    security:
        integrity_order : [ NIA2, NIA1, NIA0 ]
        ciphering_order : [ NEA0, NEA1, NEA2 ]
    network_name:
        full: Open5GS
    amf_name: open5gs-amf0

sgwu:
    pfcp:
      - addr: 127.0.0.6
    gtpu:
      - addr: 127.0.0.6

upf:
    pfcp:
      - addr: 127.0.0.7
    gtpu:
      - addr: 127.0.0.2
    subnet:
      - addr: 10.45.0.1/16
      - addr: 2001:db8:cafe::1/48
    metrics:
      - addr: 127.0.0.7
        port: 9090

hss:
    freeDiameter:
      identity: hss.localdomain
      realm: localdomain
      listen_on: 127.0.0.8
      no_fwd: true
      load_extension:
        - module: /home/pi/src/open5gs/build/subprojects/freeDiameter/extensions/dbg_msg_dumps.fdx
          conf: 0x8888
        - module: /home/pi/src/open5gs/build/subprojects/freeDiameter/extensions/dict_rfc5777.fdx
        - module: /home/pi/src/open5gs/build/subprojects/freeDiameter/extensions/dict_mip6i.fdx
        - module: /home/pi/src/open5gs/build/subprojects/freeDiameter/extensions/dict_nasreq.fdx
        - module: /home/pi/src/open5gs/build/subprojects/freeDiameter/extensions/dict_nas_mipv6.fdx
        - module: /home/pi/src/open5gs/build/subprojects/freeDiameter/extensions/dict_dcca.fdx
        - module: /home/pi/src/open5gs/build/subprojects/freeDiameter/extensions/dict_dcca_3gpp/dict_dcca_3gpp.fdx
      connect:
        - identity: mme.localdomain
          addr: 127.0.0.2
pcrf:
    freeDiameter:
      identity: pcrf.localdomain
      realm: localdomain
      listen_on: 127.0.0.9
      no_fwd: true
      load_extension:
        - module: /home/pi/src/open5gs/build/subprojects/freeDiameter/extensions/dbg_msg_dumps.fdx
          conf: 0x8888
        - module: /home/pi/src/open5gs/build/subprojects/freeDiameter/extensions/dict_rfc5777.fdx
        - module: /home/pi/src/open5gs/build/subprojects/freeDiameter/extensions/dict_mip6i.fdx
        - module: /home/pi/src/open5gs/build/subprojects/freeDiameter/extensions/dict_nasreq.fdx
        - module: /home/pi/src/open5gs/build/subprojects/freeDiameter/extensions/dict_nas_mipv6.fdx
        - module: /home/pi/src/open5gs/build/subprojects/freeDiameter/extensions/dict_dcca.fdx
        - module: /home/pi/src/open5gs/build/subprojects/freeDiameter/extensions/dict_dcca_3gpp/dict_dcca_3gpp.fdx
      connect:
        - identity: smf.localdomain
          addr: 127.0.0.4

nrf:
    sbi:
      - addr:
        - 127.0.0.10
        - ::1
        port: 7777

scp:
    sbi:
      - addr: 127.0.1.10
        port: 7777

ausf:
    sbi:
      - addr: 127.0.0.11
        port: 7777

udm:
    hnet:
      - id: 1
        scheme: 1
        key: /home/pi/src/open5gs/build/configs/open5gs/hnet/curve25519-1.key
      - id: 2
        scheme: 2
        key: /home/pi/src/open5gs/build/configs/open5gs/hnet/secp256r1-2.key
    sbi:
      - addr: 127.0.0.12
        port: 7777

pcf:
    sbi:
      - addr: 127.0.0.13
        port: 7777
    metrics:
      - addr: 127.0.0.13
        port: 9090

nssf:
    sbi:
      - addr: 127.0.0.14
        port: 7777
    nsi:
      - addr: 127.0.0.10
        port: 7777
        s_nssai:
          sst: 1
bsf:
    sbi:
      - addr: 127.0.0.15
        port: 7777

udr:
    sbi:
      - addr: 127.0.0.20
        port: 7777

time:
  t3512:
    value: 540     # 9 mintues * 60 = 540 seconds
```


### Monitoring Network Interfaces
The default interfaces for Open5GS look as follows:

- MongoDB = 127.0.0.1 (subscriber data) - http://localhost:3000
- MME-s1ap = 127.0.0.2 :36412 for S1-MME
- MME-gtpc = 127.0.0.2 :2123 for S11
- MME-frDi = 127.0.0.2 :3868 for S6a
- SGWC-gtpc = 127.0.0.3 :2123 for S11
- SGWC-pfcp = 127.0.0.3 :8805 for Sxa
- SMF-gtpc = 127.0.0.4 :2123 for S5c, N11
- SMF-gtpu = 127.0.0.4 :2152 for N4u (Sxu)
- SMF-pfcp = 127.0.0.4 :8805 for N4 (Sxb)
- SMF-frDi = 127.0.0.4 :3868 for Gx auth
- SMF-sbi = 127.0.0.4 :7777 for 5G SBI (N7,N10,N11)
- AMF-ngap = 127.0.0.2 :38412 for N2
- AMF-sbi = 127.0.0.5 :7777 for 5G SBI (N8,N12,N11)
- SGWU-pfcp = 127.0.0.6 :8805 for Sxa
- SGWU-gtpu = 127.0.0.6 :2152 for S1-U, S5u
- UPF-pfcp = 127.0.0.7 :8805 for N4 (Sxb)
- UPF-gtpu = 127.0.0.2 :2152 for S5u, N3, N4u (Sxu)
- HSS-frDi = 127.0.0.8 :3868 for S6a, Cx
- PCRF-frDi = 127.0.0.9 :3868 for Gx
- NRF-sbi = 127.0.0.10:7777 for 5G SBI
- AUSF-sbi = 127.0.0.11:7777 for 5G SBI
- UDM-sbi = 127.0.0.12:7777 for 5G SBI
- PCF-sbi = 127.0.0.13:7777 for 5G SBI
- NSSF-sbi = 127.0.0.14:7777 for 5G SBI
- BSF-sbi = 127.0.0.15:7777 for 5G SBI
- UDR-sbi = 127.0.0.20:7777 for 5G SBI



### gNB config file
Config file location `/home/pi/src/srsRAN_Project/configs`

`gnb_rf_b200.yml` is a configuration file for FDD band n3 with 20MHz bandwidth.  


```
amf:
  addr: 127.0.0.2                 # The address or hostname of the AMF. 127.0.1.1
  bind_addr: 127.0.0.1              # A local IP that the gNB binds to for traffic from the AMF. 127.0.0.1

rf_driver:
  device_driver: uhd                # The RF driver name.
  device_args: type=b200, num_recv_frames=64,num_send_frames=64            # Optionally pass arguments to the selected RF driver.
  clock: internal                   # Specify the clock source used by the RF.
  sync: internel                    # Specify the sync source used by the RF.
  srate: 23.04                      # 30.72 11.52 RF sample rate might need to be adjusted according to selected bandwidth.
  tx_gain: 89                       # Transmit gain of the RF might need to adjusted to the given situation.
  rx_gain: 40                       # Receive gain of the RF might need to adjusted to the given situation.
  #time_alignment_calibration:  100  # Set time stamp offset
  #device_args: num_recv_frames=64,num_send_frames=64,recv_frame_size=9232,send_frame_size=9232
cell_cfg:
  dl_arfcn: 368500                  # ARFCN of the downlink carrier (center frequency).
  band: 3                           # The NR band.
  channel_bandwidth_MHz: 20         # Bandwith in MHz. Number of PRBs will be automatically derived.
  common_scs: 15                    # Subcarrier spacing in kHz used for data.
  plmn: "99970"                     # PLMN broadcasted by the gNB.
  tac: 7                            # Tracking area code (needs to match the core configuration).
  pci: 1                            # Physical cell ID.
      
log:
  filename: /tmp/gnb.log            # Path of the log file.
  all_level: warning                # Logging level applied to all layers.

pcap:
  mac_enable: false                 # Set to true to enable MAC-layer PCAPs.
  mac_filename: /tmp/gnb_mac.pcap   # Path where the MAC PCAP is stored.
  ngap_enable: false                # Set to true to enable NGAP PCAPs.
  ngap_filename: /tmp/gnb_ngap.pcap # Path where the NGAP PCAP is stored.
```


To start gNB, say `sudo gnb -c gnb_rf_b200.yml` in config files directory

`b210tddn78.yml` is a configuration file for TDD band n78 with 20MHz bandwidth

```
amf:
  addr: 127.0.0.2                                             # The address or hostname of the AMF.
  bind_addr: 127.0.0.1                                          # A local IP that the gNB binds to for traffic from the AMF.

rf_driver:
  device_driver: uhd                                            # The RF driver name.
  device_args: type=b200,num_recv_frames=64,num_send_frames=64  # Optionally pass arguments to the selected RF driver.
  clock: internal                                                       # Specify the clock source used by the RF.
  sync: internal                                                         # Specify the sync source used by the RF.
  srate: 23.04                                                  # RF sample rate might need to be adjusted according to selected bandwidth.
  otw_format: sc12
  tx_gain: 89                                                   # Transmit gain of the RF might need to adjusted to the given situation.
  rx_gain: 60                                                   # Receive gain of the RF might need to adjusted to the given situation.

cell_cfg:
  dl_arfcn: 632628                                              # ARFCN of the downlink carrier (center frequency).
  band: 78                                                      # The NR band.
  channel_bandwidth_MHz: 20                                     # Bandwith in MHz. Number of PRBs will be automatically derived.
  common_scs: 30                                                # Subcarrier spacing in kHz used for data.
  plmn: "99970"                                                 # PLMN broadcasted by the gNB.
  tac: 7                                                        # Tracking area code (needs to match the core configuration).
  pci: 1                                                        # Physical cell ID.
      
log:
  filename: /tmp/gnb.log                                        # Path of the log file.
  all_level: warning                                            # Logging level applied to all layers.

pcap:
  mac_enable: false                                             # Set to true to enable MAC-layer PCAPs.
  mac_filename: /tmp/gnb_mac.pcap                               # Path where the MAC PCAP is stored.
  ngap_enable: false                                            # Set to true to enable NGAP PCAPs.
  ngap_filename: /tmp/gnb_ngap.pcap                             # Path where the NGAP PCAP is stored.

```


### Installation


Get depensecies

```
sudo apt-get install autoconf automake build-essential ccache cmake cpufrequtils doxygen ethtool \
g++ git inetutils-tools libboost-all-dev libncurses5 libncurses5-dev libusb-1.0-0 libusb-1.0-0-dev \
libusb-dev python3-dev python3-mako python3-numpy python3-requests python3-scipy python3-setuptools \
python3-ruamel.yaml 
```

Get images
`pi@NanoPi-R6C:~/src$ wget https://github.com/EttusResearch/uhd/releases/download/v3.15.0.0/uhd-images_3.15.0.0.tar.gz`

Get driver
`pi@NanoPi-R6C:~/src$ wget https://github.com/EttusResearch/uhd/archive/refs/tags/v3.15.0.0.zip`

`git clone -b UHD-3.15.LTS https://github.com/EttusResearch/uhd.git`

`/home/pi/src/uhd-3.15.0.0/host/build`

`cmake ..`

`make`

`sudo make install`

Install FPGA image

`sudo uhd_images_downloader`


Install srsRAN

`sudo apt-get install cmake make gcc g++ pkg-config libfftw3-dev libmbedtls-dev libsctp-dev libyaml-cpp-dev libgtest-dev`

`wget https://github.com/srsran/srsRAN_Project/archive/refs/tags/release_23_3.tar.gz`


Install open5GS

install mongoDB

https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/


Install dependencies

```
sudo apt install python3-pip python3-setuptools python3-wheel ninja-build build-essential flex bison git cmake libsctp-dev libgnutls28-dev libgcrypt-dev libssl-dev libidn11-dev libmongoc-dev libbson-dev libyaml-dev libnghttp2-dev libmicrohttpd-dev libcurl4-gnutls-dev libnghttp2-dev libtins-dev libtalloc-dev meson
```


Configuration file

`/home/pi/src/open5gs/build/configs/sample.yaml`

