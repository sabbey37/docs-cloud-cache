# How to run/test/etc the pizza app

## Long-running env *tehran*

- OpsMan creds

    ```
    User: pivotalcf
    Password: d8k2ug5j61djnnyi
    ```
- output from running `loaddry ~/Downloads/tehran.json`

    ```
    "bosh_commandline_credentials",
    {
      "credential": "BOSH_CLIENT=ops_manager BOSH_CLIENT_SECRET=fmRaZlHC5J0pI-bxptCCW-bHlRPyK-hT BOSH_CA_CERT=/var/tempest/workspaces/default/root_ca_certificate BOSH_ENVIRONMENT=10.0.0.5 bosh "
    }
    ```

- after showenv tehran:

```
% showenv tehran
{
  "name": "tehran",
  "date-created": "1546627281",
  "services-tls-cert": "TheServicesTLSCertPlaceholder",
  "bosh": {
    "client": "director",
    "client-secret": "Z6V4VPZgEKJzCMhaG_qW7qDujZeonGo5",
    "uaa-url": "https://10.0.0.5:8443",
    "address": "https://10.0.0.5:25555",
    "ca-cert": "-----BEGIN CERTIFICATE-----\nMIIDUTCCAjmgAwIBAgIVANobtnHfFhDxZUOkWxH3YPe/taQiMA0GCSqGSIb3DQEB\nCwUAMB8xCzAJBgNVBAYTAlVTMRAwDgYDVQQKDAdQaXZvdGFsMB4XDTE5MDEwMjIy\nNDgxMFoXDTIzMDEwMzIyNDgxMFowHzELMAkGA1UEBhMCVVMxEDAOBgNVBAoMB1Bp\ndm90YWwwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQC8UsWo3sLkh2xc\nOF0sYSyL6TyFjFEYqn25/wJAw031kgHCQIuzH5xf03iVmwI7wrUdmjtAjaY6f8Ol\nvP6ldvbsTALtBy8aFbBnLZ0b0ngDrzD9I6ddWK315ak8e/9h9SNKq8oIWsvYWxI1\nsNKlsrRq5fCGbHmxnuRjE1recEBc3S9JimlN5KLkNKIEvkSPDvO+W9tR1kXp7sLt\nersKRMq3SFXPPOXnS+P0rDiGHfBQ2QiAjLA44EdBZD6bA4Q6OeD/rQnvUHCnr94S\nKlqqK9bVJL0jzXwH7SgMl2hEEiC9KyMxg9LsgeQTzWy4MvVAKROiZi0Ndd2CL0aY\nf2kGPbNjAgMBAAGjgYMwgYAwHQYDVR0OBBYEFN8u8wF33f2Oe4LxdIiox+/ulz6o\nMB8GA1UdIwQYMBaAFN8u8wF33f2Oe4LxdIiox+/ulz6oMB0GA1UdJQQWMBQGCCsG\nAQUFBwMCBggrBgEFBQcDATAPBgNVHRMBAf8EBTADAQH/MA4GA1UdDwEB/wQEAwIB\nBjANBgkqhkiG9w0BAQsFAAOCAQEATQUu5nv+J93RqCXoScKxBgu6tP6PdL7GGH2v\nAMgO227e8SRKSJvHkkPCLlQ/2zDKvzqXZQsQVC1PctbXCfxcCRpPzv0FJ6F0kWpv\nko48RrruH8818MOLfhvxeTud4zr5/bp46962mwr4ubYaY5JCrqxADXXFoUM0ISAZ\nZKeVtEVrcsu91UbAfSDkdPEUCX330SApjOJ3qaxPrcdPuSoin3Zqv9d074nP35mT\nTNBEx395MN37XwqYKyEsG4oPLqbdR1YVPoFbfJGMjDKFLIMu/1zPnxDtOL91escq\nTeHIaOtYMU7qshWy9Pj1qhPQCvFXPbLbIHU8/e4i9o1jS0GVVg==\n-----END CERTIFICATE-----\n"
  },
  "cf": {
    "system-domain": "sys.tehran.cf-app.com",
    "apps-domain": "apps.tehran.cf-app.com",
    "username": "admin",
    "password": "LElfDWsiw_1ClRFYt7nQZsBS7bu63Db_",
    "cloudcache-broker-client-id": "cloudcache_broker",
    "cloudcache-broker-client-secret": "ohi6GcR7ycwydgdFKF3NCwQ-BsirXJbk",
    "loggregator-ca-cert": "-----BEGIN CERTIFICATE-----\nMIIDUTCCAjmgAwIBAgIVANobtnHfFhDxZUOkWxH3YPe/taQiMA0GCSqGSIb3DQEB\nCwUAMB8xCzAJBgNVBAYTAlVTMRAwDgYDVQQKDAdQaXZvdGFsMB4XDTE5MDEwMjIy\nNDgxMFoXDTIzMDEwMzIyNDgxMFowHzELMAkGA1UEBhMCVVMxEDAOBgNVBAoMB1Bp\ndm90YWwwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQC8UsWo3sLkh2xc\nOF0sYSyL6TyFjFEYqn25/wJAw031kgHCQIuzH5xf03iVmwI7wrUdmjtAjaY6f8Ol\nvP6ldvbsTALtBy8aFbBnLZ0b0ngDrzD9I6ddWK315ak8e/9h9SNKq8oIWsvYWxI1\nsNKlsrRq5fCGbHmxnuRjE1recEBc3S9JimlN5KLkNKIEvkSPDvO+W9tR1kXp7sLt\nersKRMq3SFXPPOXnS+P0rDiGHfBQ2QiAjLA44EdBZD6bA4Q6OeD/rQnvUHCnr94S\nKlqqK9bVJL0jzXwH7SgMl2hEEiC9KyMxg9LsgeQTzWy4MvVAKROiZi0Ndd2CL0aY\nf2kGPbNjAgMBAAGjgYMwgYAwHQYDVR0OBBYEFN8u8wF33f2Oe4LxdIiox+/ulz6o\nMB8GA1UdIwQYMBaAFN8u8wF33f2Oe4LxdIiox+/ulz6oMB0GA1UdJQQWMBQGCCsG\nAQUFBwMCBggrBgEFBQcDATAPBgNVHRMBAf8EBTADAQH/MA4GA1UdDwEB/wQEAwIB\nBjANBgkqhkiG9w0BAQsFAAOCAQEATQUu5nv+J93RqCXoScKxBgu6tP6PdL7GGH2v\nAMgO227e8SRKSJvHkkPCLlQ/2zDKvzqXZQsQVC1PctbXCfxcCRpPzv0FJ6F0kWpv\nko48RrruH8818MOLfhvxeTud4zr5/bp46962mwr4ubYaY5JCrqxADXXFoUM0ISAZ\nZKeVtEVrcsu91UbAfSDkdPEUCX330SApjOJ3qaxPrcdPuSoin3Zqv9d074nP35mT\nTNBEx395MN37XwqYKyEsG4oPLqbdR1YVPoFbfJGMjDKFLIMu/1zPnxDtOL91escq\nTeHIaOtYMU7qshWy9Pj1qhPQCvFXPbLbIHU8/e4i9o1jS0GVVg==\n-----END CERTIFICATE-----\n",
    "metron-agent-key": "-----BEGIN RSA PRIVATE KEY-----\nMIIEowIBAAKCAQEAzYBDYgOFPyYnMVb0E0rPR4UzXTgqH/4AC81u/oRb9ai3FGLt\n8K24pOO88EDwrUV/6wYMCqoZCKKuTI8RPsHCpg05bmvnNaP85rzZWyQcKY7kG+o5\nZS8KTNYiX9+4iS/hvOgrCczy7F8BnGzkJ2s6zExLItTlqgrDRa9/cyrxAbcyBf+y\nLO62+n0bo54Oiu64e1asmgbrB3tX2kgt9FHvUOlJ4Qri/l6rsvDkFHnaJwqrdJFE\n4PCO5QxYAs+CDhMFdrwjE/Xn7QCgIIA46HOWs+tlySYmAaKYCfHcx9E2eJxWOJZJ\ns2c/P70JGIkIVL4brwOMtVnilfPfRw7LSt0gsQIDAQABAoIBAFGcjaYgNcu1cD01\nBiufOyBxMsvjoT8hVY1aYakskYTHIyYyf8Jki37YftF/SNXXUwzYUvHtSZHXYZc/\n/h5JPu9JMzS6H5F69dYAy+VZOuH6QHchlverLdED/ZTLuXKqFGE8ZtM2lIbw2Cfy\nSs2o1SoLZo+Hs0nLim9jWh83v4zpKP5buHgXbmhk3sg9NAD12rYLDVo8ji9MR9QO\nwseixmyiYeTev2tBNUFYKoc9CzjK5rJiviuf6Ybt+RKFOXk/m9iXDvleNLf2V5sr\nrlJs6tR5LdIjOQSa/nCIPJHeg3rSigGCR0KJs8WRL7YHbktlpC0PdaOYt0jUbp3H\n7nvqUc0CgYEA6MsMEjwNKQDJ4bU5fRoM9GBKlWPfU1ZhsTLveZeJ19IEnQ3mmPqZ\nzt4/cXb0EE6liPejKqVPXCbHg1dWxh9KqCprwy6cgYTCW7eaMD5/STVn4KrhawJf\ntTPmZBp0xpGr4/9DxG1GAJGs2B6g5cxV/vSU/A5n8ulDAi9Gkl1Gmv8CgYEA4fy2\nb+Tr6rDQJGi7fusTPnm//vaObtg2kUHX+S47hBSWnKRlInbh9k9xCIzncenh1Hdt\nbt4ZUrOmpi4oqOfHVzAiixxepEiPomWe0RmAWCSGT31VGI7qQQUX4iMYsY2/K3k5\nQRzZSrnvhf72B6clBoWJrQS3qNIopC4YL5rotE8CgYATdGyk1XnwFE3K3B9a0iOF\nBMsW4wrV5yEw8uXKjpyJedbC3VeJL2BNRoucyukot7nj0XZEaR5RwDfqRRFOa20M\n0sbAwBN6S4MGsThkkcSHdLwirYU7MS6YcSbu9LsPoTrxSfL65nr0Lzh3s0+VBNem\n//+3dOjBBzd/Zj4Km1r8NwKBgQCzI6++7VnyFa05X2hZyKDdooeG5g2sYmqHJQm+\nNl7paaSmkU62TkT7CqhQndmOHFdvJCi0fQzX2R9eljKXCfyj6b1IRvnjAr4Rfrqx\niKSLupBZjMGbERcy6YWwNiAKB5ImNRckvWimatQrhRukn2OjUtH7PEUWZ1neI8f6\nXLLg0wKBgF3xXMAsI7knUA5b1NO/Q6fFEMU+ghhugQfcMhbDX3vcZindVpXle9tp\nlXt/+vYa6b8Pwo9qnHGogAMo2bC5okv0VK43ZT97dfDF/kvv3GPHC+8T4mRfqfI9\nKH8/Qcdy3QjI3/oKLdUsgSmwgcDKvWTjllj8st/kL76wH68HBsiE\n-----END RSA PRIVATE KEY-----\n",
    "metron-agent-cert": "-----BEGIN CERTIFICATE-----\nMIIDZDCCAkygAwIBAgIVAPcW1cFgiVJ1SiehK7LUdGziVsSBMA0GCSqGSIb3DQEB\nCwUAMB8xCzAJBgNVBAYTAlVTMRAwDgYDVQQKDAdQaXZvdGFsMB4XDTE5MDEwMjIz\nMDU0NloXDTIxMDEwMjIzMDU0NlowMDELMAkGA1UEBhMCVVMxEDAOBgNVBAoMB1Bp\ndm90YWwxDzANBgNVBAMMBm1ldHJvbjCCASIwDQYJKoZIhvcNAQEBBQADggEPADCC\nAQoCggEBAM2AQ2IDhT8mJzFW9BNKz0eFM104Kh/+AAvNbv6EW/WotxRi7fCtuKTj\nvPBA8K1Ff+sGDAqqGQiirkyPET7BwqYNOW5r5zWj/Oa82VskHCmO5BvqOWUvCkzW\nIl/fuIkv4bzoKwnM8uxfAZxs5CdrOsxMSyLU5aoKw0Wvf3Mq8QG3MgX/sizutvp9\nG6OeDoruuHtWrJoG6wd7V9pILfRR71DpSeEK4v5eq7Lw5BR52icKq3SRRODwjuUM\nWALPgg4TBXa8IxP15+0AoCCAOOhzlrPrZckmJgGimAnx3MfRNnicVjiWSbNnPz+9\nCRiJCFS+G68DjLVZ4pXz30cOy0rdILECAwEAAaOBhTCBgjAdBgNVHQ4EFgQUCWku\nxTkYWWZGLQefbzs6IFLbUxUwHwYDVR0jBBgwFoAU3y7zAXfd/Y57gvF0iKjH7+6X\nPqgwHQYDVR0lBBYwFAYIKwYBBQUHAwIGCCsGAQUFBwMBMA4GA1UdDwEB/wQEAwIH\ngDARBgNVHREECjAIggZtZXRyb24wDQYJKoZIhvcNAQELBQADggEBAGU/R9eKdDyO\nYFjcBqNqf1LgL6zkMwqNP865x5J/kw2AQXH5oFoUGaXKMEn8oaBk3cah0p+kWmBo\nTxBd8/kDpL8y2OPhwzIku9I1FQmcOujDsb0ghn5FWnT51JzcHBQ6aHKjYZSiUdlp\nYXDiZlJ9ZaVab3Edo7tmG04vJyyui+iJ01uW121MftLvPJZX4PMJkcAS7R+HoUIj\nBixAmLpjVpcHTg5YfDqVK547uTxchmnx7amfWhugLL+mTyl5CnSqx0p7IXFC0Xp9\nrd5FtyDCVTR4suU8jeljclti8nkQ4UxQE58NUNnOM/O5QxXxnqoRn2T7VDv5u84E\nr5ArxiiH434=\n-----END CERTIFICATE-----\n"
  },
  "opsman": {
    "username": "pivotalcf",
    "password": "d8k2ug5j61djnnyi",
    "address": "https://pcf.tehran.cf-app.com",
    "client": "ops_manager",
    "client-secret": "fmRaZlHC5J0pI-bxptCCW-bHlRPyK-hT"
```

- for tehran: plan 1 is called extra-small. Also have dev-plan and
small-footprint plan.  Each with defaults.

## Time to Run the Pizza app (without TLS on the cluster)

1. Create the PCC cluster:

    ```
    % cf login --skip-ssl-validation -a https://api.sys.tehran.cf-app.com
    ```

    Login creds are `admin` and `LElfDWsiw_1ClRFYt7nQZsBS7bu63Db_`

    ```
      cf create-service p-cloudcache PLAN_NAME SERVICE_INSTANCE
    % cf create-service p-cloudcache extra-small PCC-no-TLS
    ```

1. With CWD of PCC-Sample-App-PizzaStore,
Build, push, and then bind the app:

    ```
    % ./gradlew build
    % cf push --no-start
    % cf bind-service cloudcache-pizza-store PCC-no-TLS
    ```

    `APP_NAME` is `cloudcache-pizza-store`

1. Get GemFire 9.6, to have gfsh.  From pivnet, download. Then, unzip.

1. Create service key, and then Connect with gfsh and create the 2 regions:

    ```
      cf create-service-key SERVICE-INSTANCE-NAME KEY-NAME
    % cf create-service-key PCC-no-TLS            noTLSkey
    ```

    Print the service key:

    ```
    % cf service-key PCC-no-TLS noTLSkey
    ```

    Here's the service key:

    ```
    Getting key noTLSkey for service instance PCC-no-TLS as admin...
    
    {
     "distributed_system_id": "0",
     "locators": [
      "10.0.8.6[55221]",
      "10.0.8.7[55221]",
      "10.0.8.5[55221]"
     ],
     "urls": {
      "gfsh": "https://cloudcache-6ba31341-25ab-474d-8c33-0be17482ccfd.sys.tehran.cf-app.com/gemfire/v1",
      "pulse": "https://cloudcache-6ba31341-25ab-474d-8c33-0be17482ccfd.sys.tehran.cf-app.com/pulse"
     },
     "users": [
      {
       "password": "57A8hgjNkVZMmtOxuHmycw",
       "roles": [
        "developer"
       ],
       "username": "developer_5VTEVRHdeq1D5yLUmSGdqw"
      },
      {
       "password": "0Pw3D5dgl3IjAprCPd4cA",
       "roles": [
        "cluster_operator"
       ],
       "username": "cluster_operator_ebmzuyGVp6fDKET4VJGAsg"
      }
     ],
     "wan": {
      "sender_credentials": {
       "active": {
        "password": "Wd6j1SnsPBCFotDWiQXpA",
        "username": "gateway_sender_hlo7amzueHHAxPqJLBMtlQ"
       }
      }
     }
    }
    ```

    Run gfsh and connect (hit return for all the prompts):

    ```
    % ~/Downloads/pivotal-gemfire-9.6.0/bin/gfsh
    gfsh>connect --use-http=true --use-ssl --skip-ssl-validation=true --url=https://cloudcache-6ba31341-25ab-474d-8c33-0be17482ccfd.sys.tehran.cf-app.com/gemfire/v1 --user=cluster_operator_ebmzuyGVp6fDKET4VJGAsg --password=0Pw3D5dgl3IjAprCPd4cA
    ```

    ```
    gfsh>create region --name=Pizza --type=REPLICATE
    gfsh>create region --name=Name --type=REPLICATE
    ```

1. Start the app (with CF login, but outside gfsh):

    ```
    % cf start cloudcache-pizza-store
    ```

1. Acquire the app's URL:

    ```
    % cf apps
    Getting apps in org system / space test-space as admin...
    OK
    
    name                     requested state   instances   memory   disk   urls
    cloudcache-pizza-store   started           1/1         1G       1G     cloudcache-pizza-store.apps.tehran.cf-app.com
    ```

## Run some commands.

URL `http://cloudcache-pizza-store.apps.tehran.cf-app.com/pizzas` returns `No Pizzas Found`

Put in a pizza order (browser based) with:

Here's a great query to use from gfsh:

```
query --query='SELECT e.key, e.value.toppings.toString() FROM /Pizza.entrySet() e'
```

## Setting up Plan for TLS-enabled cluster creation

(Taylor is writing up the steps for this.)

BoshDirector IP: 10.0.0.5
Director Creds: director Z6V4VPZgEKJzCMhaG_qW7qDujZeonGo5

Run custom script to authenticate me to the credhub of the tehran env,
and conveniently creates the right CA if it isn't already existing:

```
% target-credhub tehran
```

```
% uaac target 10.0.0.5:8443
```

