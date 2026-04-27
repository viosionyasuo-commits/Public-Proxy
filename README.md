# proxy-direct-rules

Direct routing rules for academic access, campus IP verification, and mainland China services.

This repository is meant to be used as a remote custom routing rule file in proxy clients that support YAML rules.

## Remote URL

Use this URL in the client:

```text
https://raw.githubusercontent.com/viosionyasuo-commits/Public-Proxy/main/rules.yaml
```

Dia browser proxy rules:

```text
https://raw.githubusercontent.com/viosionyasuo-commits/Public-Proxy/main/dia-proxy.yaml
```

## Goal

These rules force selected domains to use `DIRECT`, so services that depend on campus IP, mainland China IP, or local copyright regions are not accidentally routed through proxy nodes.

The rules focus on:

- Academic databases and publishers, such as Scopus, Web of Science, ScienceDirect, Springer Nature, Wiley, IEEE, ACM, PubMed, JSTOR, and similar services.
- Campus login, library, SSO, CAS, and IP verification flows.
- Mainland China video and streaming services, such as Tencent Video, iQIYI, Youku, Mango TV, Bilibili, Migu, and CCTV.
- Mainland China daily services, such as Tencent, Alibaba, Alipay, Baidu, JD, Meituan, Douyin, Kuaishou, Xiaohongshu, NetEase, Weibo, and Zhihu.

## Add Your School Domains

Add your own school domains near the top of `rules.yaml`, for example:

```yaml
  - DOMAIN-SUFFIX,example.edu.cn,DIRECT
  - DOMAIN-SUFFIX,lib.example.edu.cn,DIRECT
  - DOMAIN-SUFFIX,sso.example.edu.cn,DIRECT
  - DOMAIN-SUFFIX,cas.example.edu.cn,DIRECT
```

Keep these rules above broader rules when possible.

## Format

The main file uses Clash-style rule entries:

```yaml
rules:
  - DOMAIN-SUFFIX,scopus.com,DIRECT
  - DOMAIN-SUFFIX,webofscience.com,DIRECT
```

`dia-proxy.yaml` uses the same format, but routes Dia-related domains to `PROXY`.
