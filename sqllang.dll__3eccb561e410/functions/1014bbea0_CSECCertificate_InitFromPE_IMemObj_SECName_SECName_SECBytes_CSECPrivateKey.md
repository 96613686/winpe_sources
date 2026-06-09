# CSECCertificate::InitFromPE(IMemObj *,SECName &,SECName &,SECBytes &,CSECPrivateKey &)

- ea: `0x1014bbea0`
- end: `0x1014bc990`
- name: `?InitFromPE@CSECCertificate@@QEAA?AVCSECCryptoError@@PEAVIMemObj@@AEAUSECName@@1AEAUSECBytes@@AEAVCSECPrivateKey@@@Z`
- size: `2800`
- prototype: `struct CSECCryptoError __high(struct IMemObj *, struct SECName *, struct SECName *, struct SECBytes *, struct CSECPrivateKey *)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1014f5320`
- `0x101519060`

## callees

- `0x100401070`
- `0x1004076a0`
- `0x100430d60`
- `0x100754350`
- `0x100755b10`
- `0x10138b140`
- `0x1014b2db0`
- `0x1014bb4f0`
- `0x1014bbea0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1014bbf45`
- `KERNEL32!GetLastError` at `0x1014bc15b`
- `KERNEL32!GetLastError` at `0x1014bc295`
- `KERNEL32!GetLastError` at `0x1014bc3f0`
- `KERNEL32!GetLastError` at `0x1014bc51f`
- `KERNEL32!GetLastError` at `0x1014bc82a`
- `KERNEL32!GetLastError` at `0x1014bc92d`
- `KERNEL32!GetLastError` at `0x1014bbf45`
- `KERNEL32!GetLastError` at `0x1014bc15b`
- `KERNEL32!GetLastError` at `0x1014bc295`
- `KERNEL32!GetLastError` at `0x1014bc3f0`
- `KERNEL32!GetLastError` at `0x1014bc51f`
- `KERNEL32!GetLastError` at `0x1014bc82a`
- `KERNEL32!GetLastError` at `0x1014bc92d`
- `secforwarder!CryptMsgClose` at `0x1014bc1ef`
- `secforwarder!CryptMsgClose` at `0x1014bc329`
- `secforwarder!CryptMsgClose` at `0x1014bc485`
- `secforwarder!CryptMsgClose` at `0x1014bc5b4`
- `secforwarder!CryptMsgClose` at `0x1014bc6da`
- `secforwarder!CryptMsgClose` at `0x1014bc7ba`
- `secforwarder!CryptMsgClose` at `0x1014bc8bf`
- `secforwarder!CryptMsgClose` at `0x1014bc1ef`
- `secforwarder!CryptMsgClose` at `0x1014bc329`
- `secforwarder!CryptMsgClose` at `0x1014bc485`
- `secforwarder!CryptMsgClose` at `0x1014bc5b4`
- `secforwarder!CryptMsgClose` at `0x1014bc6da`
- `secforwarder!CryptMsgClose` at `0x1014bc7ba`
- `secforwarder!CryptMsgClose` at `0x1014bc8bf`
- `secforwarder!CertFreeCertificateChain` at `0x1014bc1aa`
- `secforwarder!CertFreeCertificateChain` at `0x1014bc2e4`
- `secforwarder!CertFreeCertificateChain` at `0x1014bc440`
- `secforwarder!CertFreeCertificateChain` at `0x1014bc56f`
- `secforwarder!CertFreeCertificateChain` at `0x1014bc695`
- `secforwarder!CertFreeCertificateChain` at `0x1014bc775`
- `secforwarder!CertFreeCertificateChain` at `0x1014bc87a`
- `secforwarder!CertFreeCertificateChain` at `0x1014bc1aa`
- `secforwarder!CertFreeCertificateChain` at `0x1014bc2e4`
- `secforwarder!CertFreeCertificateChain` at `0x1014bc440`
- `secforwarder!CertFreeCertificateChain` at `0x1014bc56f`
- `secforwarder!CertFreeCertificateChain` at `0x1014bc695`
- `secforwarder!CertFreeCertificateChain` at `0x1014bc775`
- `secforwarder!CertFreeCertificateChain` at `0x1014bc87a`
- `secforwarder!CryptQueryObject` at `0x1014bc129`
- `secforwarder!CryptQueryObject` at `0x1014bc129`
- `secforwarder!CryptMsgGetParam` at `0x1014bc263`
- `secforwarder!CryptMsgGetParam` at `0x1014bc3c0`
- `secforwarder!CryptMsgGetParam` at `0x1014bc263`
- `secforwarder!CryptMsgGetParam` at `0x1014bc3c0`
- `secforwarder!CertGetSubjectCertificateFromStore` at `0x1014bc60d`
- `secforwarder!CertGetSubjectCertificateFromStore` at `0x1014bc60d`
- `secforwarder!CertOpenStore` at `0x1014bc4eb`
- `secforwarder!CertOpenStore` at `0x1014bc4eb`
- `secforwarder!CertFreeCertificateContext` at `0x1014bc1ba`
- `secforwarder!CertFreeCertificateContext` at `0x1014bc2f4`
- `secforwarder!CertFreeCertificateContext` at `0x1014bc450`
- `secforwarder!CertFreeCertificateContext` at `0x1014bc57f`
- `secforwarder!CertFreeCertificateContext` at `0x1014bc6a5`
- `secforwarder!CertFreeCertificateContext` at `0x1014bc785`
- `secforwarder!CertFreeCertificateContext` at `0x1014bc88a`
- `secforwarder!CertFreeCertificateContext` at `0x1014bc1ba`
- `secforwarder!CertFreeCertificateContext` at `0x1014bc2f4`
- `secforwarder!CertFreeCertificateContext` at `0x1014bc450`
- `secforwarder!CertFreeCertificateContext` at `0x1014bc57f`
- `secforwarder!CertFreeCertificateContext` at `0x1014bc6a5`
- `secforwarder!CertFreeCertificateContext` at `0x1014bc785`
- `secforwarder!CertFreeCertificateContext` at `0x1014bc88a`
- `secforwarder!CertCloseStore` at `0x1014bc1cf`
- `secforwarder!CertCloseStore` at `0x1014bc1e0`
- `secforwarder!CertCloseStore` at `0x1014bc309`
- `secforwarder!CertCloseStore` at `0x1014bc31a`
- `secforwarder!CertCloseStore` at `0x1014bc465`
- `secforwarder!CertCloseStore` at `0x1014bc476`
- `secforwarder!CertCloseStore` at `0x1014bc594`
- `secforwarder!CertCloseStore` at `0x1014bc5a5`
- `secforwarder!CertCloseStore` at `0x1014bc6ba`
- `secforwarder!CertCloseStore` at `0x1014bc6cb`
- `secforwarder!CertCloseStore` at `0x1014bc79a`
- `secforwarder!CertCloseStore` at `0x1014bc7ab`
- `secforwarder!CertCloseStore` at `0x1014bc89f`
- `secforwarder!CertCloseStore` at `0x1014bc8b0`
- `secforwarder!CertCloseStore` at `0x1014bc1cf`
- `secforwarder!CertCloseStore` at `0x1014bc1e0`
- `secforwarder!CertCloseStore` at `0x1014bc309`
- `secforwarder!CertCloseStore` at `0x1014bc31a`
- `secforwarder!CertCloseStore` at `0x1014bc465`
- `secforwarder!CertCloseStore` at `0x1014bc476`
- `secforwarder!CertCloseStore` at `0x1014bc594`
- `secforwarder!CertCloseStore` at `0x1014bc5a5`
- `secforwarder!CertCloseStore` at `0x1014bc6ba`
- `secforwarder!CertCloseStore` at `0x1014bc6cb`
- `secforwarder!CertCloseStore` at `0x1014bc79a`
- `secforwarder!CertCloseStore` at `0x1014bc7ab`
- `secforwarder!CertCloseStore` at `0x1014bc89f`
- `secforwarder!CertCloseStore` at `0x1014bc8b0`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1014bc38f`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1014bc38f`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x1014bc044`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x1014bc044`
- `sqldk!SystemThread_TlsIndex` at `0x1014bc003`
- `sqldk!SystemThread_TlsIndex` at `0x1014bc059`
- `sqldk!SystemThread_TlsOffset` at `0x1014bc00c`
- `sqldk!SystemThread_TlsOffset` at `0x1014bc062`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1014bc027`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1014bc07d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1014bc027`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1014bc07d`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bc199`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bc2d3`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bc39f`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bc42f`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bc55e`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bc67a`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bc684`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bc731`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bc764`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bc869`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bc199`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bc2d3`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bc39f`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bc42f`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bc55e`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bc67a`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bc684`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bc731`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bc764`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014bc869`

## string_xrefs

- `0x1014bc385`: `sql\ntdbms\msql\security\src\seccryptmd.cpp`

## pseudocode

```c

```
