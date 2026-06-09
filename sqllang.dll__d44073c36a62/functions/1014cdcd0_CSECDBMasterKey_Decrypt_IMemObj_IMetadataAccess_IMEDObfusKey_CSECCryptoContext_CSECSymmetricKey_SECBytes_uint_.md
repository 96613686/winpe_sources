# CSECDBMasterKey::Decrypt(IMemObj *,IMetadataAccess *,IMEDObfusKey *,CSECCryptoContext &,CSECSymmetricKey &,SECBytes &,uint,ulong)

- ea: `0x1014cdcd0`
- end: `0x1014cef83`
- name: `?Decrypt@CSECDBMasterKey@@SA?AVCSECCryptoError@@PEAVIMemObj@@PEAVIMetadataAccess@@PEAVIMEDObfusKey@@AEAVCSECCryptoContext@@AEAVCSECSymmetricKey@@AEAUSECBytes@@IK@Z`
- size: `4787`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `service_task`

## callers

- `0x1014ca0f0`

## callees

- `0x100401070`
- `0x100401090`
- `0x100401433`
- `0x1004076a0`
- `0x100430d60`
- `0x100439ca0`
- `0x100754350`
- `0x100755960`
- `0x100755b10`
- `0x10121d660`
- `0x101496df0`
- `0x101497ad0`
- `0x1014ac300`
- `0x1014be0c0`
- `0x1014be930`
- `0x1014bf6a0`
- `0x1014c0790`
- `0x1014cdcd0`
- `0x101e88fe0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1014ce343`
- `KERNEL32!GetLastError` at `0x1014ce343`
- `secforwarder!CertFreeCertificateContext` at `0x1014ce7d0`
- `secforwarder!CertFreeCertificateContext` at `0x1014ce935`
- `secforwarder!CertFreeCertificateContext` at `0x1014cea3d`
- `secforwarder!CertFreeCertificateContext` at `0x1014ceaf0`
- `secforwarder!CertFreeCertificateContext` at `0x1014cec00`
- `secforwarder!CertFreeCertificateContext` at `0x1014ced95`
- `secforwarder!CertFreeCertificateContext` at `0x1014ce7d0`
- `secforwarder!CertFreeCertificateContext` at `0x1014ce935`
- `secforwarder!CertFreeCertificateContext` at `0x1014cea3d`
- `secforwarder!CertFreeCertificateContext` at `0x1014ceaf0`
- `secforwarder!CertFreeCertificateContext` at `0x1014cec00`
- `secforwarder!CertFreeCertificateContext` at `0x1014ced95`
- `secforwarder!CertCloseStore` at `0x1014ce7e5`
- `secforwarder!CertCloseStore` at `0x1014ce94a`
- `secforwarder!CertCloseStore` at `0x1014cea52`
- `secforwarder!CertCloseStore` at `0x1014ceb05`
- `secforwarder!CertCloseStore` at `0x1014cec1c`
- `secforwarder!CertCloseStore` at `0x1014cedb1`
- `secforwarder!CertCloseStore` at `0x1014ce7e5`
- `secforwarder!CertCloseStore` at `0x1014ce94a`
- `secforwarder!CertCloseStore` at `0x1014cea52`
- `secforwarder!CertCloseStore` at `0x1014ceb05`
- `secforwarder!CertCloseStore` at `0x1014cec1c`
- `secforwarder!CertCloseStore` at `0x1014cedb1`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x1014ce5c6`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x1014ce697`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x1014ce697`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1014ce0e3`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1014ce256`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1014ce49c`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1014ce0e3`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1014ce256`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1014ce49c`
- `sqldk!SystemThread_TlsIndex` at `0x1014ce653`
- `sqldk!SystemThread_TlsIndex` at `0x1014ce6af`
- `sqldk!SystemThread_TlsOffset` at `0x1014ce65c`
- `sqldk!SystemThread_TlsOffset` at `0x1014ce6b8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1014ce677`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1014ce6d3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1014ce677`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1014ce6d3`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014cde35`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014cde4c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014cdeec`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014cdf35`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014cdf81`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014cdfb0`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014ce470`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014ce487`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014ce58e`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014ce5a5`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014ce7c0`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014ce866`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014ce918`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014ce9cb`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014cea20`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014cead3`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014cebed`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014cec37`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014cecf7`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014ced1b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014ced75`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014cee6a`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014ceea0`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014ceeec`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014cef22`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014cde35`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014cde4c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014cdeec`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014cdf35`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014cdf81`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014cdfb0`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014ce470`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014ce487`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014ce58e`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014ce5a5`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014ce7c0`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014ce866`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014ce918`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014ce9cb`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014cea20`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014cead3`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014cebed`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014cec37`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014cecf7`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014ced1b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014ced75`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014cee6a`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014ceea0`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014ceeec`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014cef22`
- `sqlmin!?GetOnDiskVersion@RecoveryUnit@@QEBAGXZ` at `0x1014ce5d7`
- `sqlmin!?GetOnDiskVersion@RecoveryUnit@@QEBAGXZ` at `0x1014ce5d7`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x1014cde52`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x1014cedc9`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x1014cde52`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x1014cedc9`
- `sqlmin!GetXdbServerGlobals` at `0x1014cdd4e`
- `sqlmin!GetXdbServerGlobals` at `0x1014cdd6d`
- `sqlmin!GetXdbServerGlobals` at `0x1014cdd4e`
- `sqlmin!GetXdbServerGlobals` at `0x1014cdd6d`

## pseudocode

```c

```
