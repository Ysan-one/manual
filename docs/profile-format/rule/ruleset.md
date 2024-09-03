---
sidebar_position: 3
---

# Rule Set

Rule Set is a remote url configuration, whose content is a collection of Rule, but without target definition in it.

Use Rule Set can greatly simplify the content complexity of profile which has a lot of rules in it, 
and also can reuse rules encapsulated by other contributors.

:::tip
Define a large number of rules in a rule set will significantly reduce the efficiency of rule matching.
In this scenario, we strongly recommend you switch to the [Domain Set](./domainset) standard.
:::

## Sample

### Rule Set definition

```ini
RULE-SET,https://ruleset.com/cn,ProxyVMess
```

### Remote Rule Set content sample

```ini
DOMAIN,www.apple.com
DOMAIN,www.google.com
DOMAIN-SUFFIX,apple.com
DOMAIN-SUFFIX,appsto.re,SelectGroup
DOMAIN-SUFFIX,s.mzstatic.com,SelectGroup
DOMAIN,gspe1-ssl.ls.apple.com,SelectGroup
DOMAIN,news-events.apple.com,SelectGroup
DOMAIN,news-client.apple.com,SelectGroup
DOMAIN-SUFFIX,itunes.apple.com,SelectGroup
DOMAIN-SUFFIX,lookup-api.apple.com,SelectGroup
DOMAIN-SUFFIX,lcdn-registration.apple.com,DIRECT
DOMAIN-SUFFIX,mzstatic.com,DIRECT
DOMAIN,mtalk.google.com,DIRECT
DOMAIN,mtalk4.google.com,DIRECT
DOMAIN,mtalk-staging.google.com,DIRECT
DOMAIN,mtalk-dev.google.com,DIRECT
DOMAIN,alt1-mtalk.google.com,DIRECT
DOMAIN,alt1-mtalk.google.com,DIRECT
DOMAIN,alt2-mtalk.google.com,DIRECT
DOMAIN,alt3-mtalk.google.com,DIRECT
DOMAIN,alt4-mtalk.google.com,DIRECT
DOMAIN,alt5-mtalk.google.com,DIRECT
DOMAIN,alt6-mtalk.google.com,DIRECT
DOMAIN,alt7-mtalk.google.com,DIRECT
DOMAIN,alt8-mtalk.google.com,DIRECT
DOMAIN-SUFFIX,short.weixin.qq.com,SelectGroup
DOMAIN-SUFFIX,dns.weixin.qq.com.cn,SelectGroup
PROCESS-NAME,com.samsung.android.sskds (1000),SelectGroup 
DOMAIN-KEYWORD,google
IP-CIDR,192.168.0.0/16
GEOIP,US
```

You can see that there is no target definition in it, all matching traffic will use proxy 'ProxyVMess' as target

## Format

```ini
RULE-SET, {rule set url}, {target}
```

## Param

| Name         | Value | Mandatory | Note                                                   |
|--------------|-------|-----------|--------------------------------------------------------|
| rule set url | -     | true      |                                                        |
| target       | -     | true      | Specified proxy or proxy group must existed in profile |
