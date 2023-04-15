openssl_pki
=========

Generate certificate (root && sub CA && certificate)

Requirements
------------

community.crypto

Role Variables
--------------

```
root_ca:
  - name: root
    delete: true
    key_pass: a_password_for_key_
    intermediate_ca:
      - name: intermediate_ca_name
        certificate:
          - name: certificate_name
            type: serv_auth
          - name: certificate_name
            type: serv_auth
      - name: intermediate_ca_name
        intermediate_ca:
          - name: sub_intermediate_ca
    certificates:
intermediate_ca:
  - name:
    ca_key_path:
    ca_key_pass:
    ca_cert_path:
certificate:
  - name:
    type:
    ca_key_path:
    ca_key_pass:
    ca_cert_path:
self_signed:
  - name: 
    type:

base_path:
subca_default_signatory:
  type: ca subca
  name: root
  type: custom
  key_path: ...key.pem
  key_pass: ....
  cert_path: ...cert.pem
certificates:
  - type: ca
    cert_name: root
  - type: subca
    delete: false
    cert_name: elastic

    signatory:
      type: ca
      name: root
    type: custom
    key_path: ...key.pem
    key_pass: ....
    cert_path: ...cert.pem

    cert_country_code:
    cert_country:
    cert_locality:
    cert_organisation:
    cert_organisational_unit:
    cert_subj:
    cert_subj_alt:
    cert_email:
    cert_digest:
    cert_ocsp_staple:
    cert_ocsp_staple_crt:

    key_usage:
    key_usage_crt:
    key_ext_usage:
    key_ext_crt:
    key_cipher:
    key_curve:
    key_pass:
    key_size:
    key_type:
```

Dependencies
------------

Example Playbook
----------------

roles:
    - openssl_pki-subpki_role
  vars:
    self_signed:
      - name: self.signed.com
        type: serv_auth
        cert_subj_alt:
          - DNS:self.signed.com
          - DNS:www.self.signed.com

License
-------

BSD

amaelFr
------------------
