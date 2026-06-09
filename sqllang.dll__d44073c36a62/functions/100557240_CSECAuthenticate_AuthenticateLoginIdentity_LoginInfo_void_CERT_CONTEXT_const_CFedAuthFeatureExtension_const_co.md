# CSECAuthenticate::AuthenticateLoginIdentity(LoginInfo *,void *,_CERT_CONTEXT const *,CFedAuthFeatureExtension const * const,CSECValArray<ulong> &,CSECValArray<ulong> &,CConnectionChecker const *,CAutoRefc<ILoginToken> &,CAutoP<CFedAuthFeatureExtensionAckOption> &,CAutoRg<uchar> &,ulong &,bool &,ExternalRBACAdminType &,bool &,bool &,bool,ulong)

- ea: `0x100557240`
- end: `0x100557416`
- name: `?AuthenticateLoginIdentity@CSECAuthenticate@@QEAAKPEAULoginInfo@@PEAXPEBU_CERT_CONTEXT@@QEBVCFedAuthFeatureExtension@@AEAV?$CSECValArray@K@@4PEBVCConnectionChecker@@AEAV?$CAutoRefc@VILoginToken@@@@AEAV?$CAutoP@VCFedAuthFeatureExtensionAckOption@@@@AEAV?$CAutoRg@E@@AEAKAEA_NAEAW4ExternalRBACAdminType@@AEA_NAEA_N_NK@Z`
- size: `470`
- prototype: ``
- caller_count: `1`
- callee_count: `33`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x10054c610`

## callees

- `0x100401070`
- `0x100401090`
- `0x100401433`
- `0x100403080`
- `0x10040be50`
- `0x10040bf50`
- `0x100435510`
- `0x10045c260`
- `0x100557240`
- `0x100558eb0`
- `0x10058cb20`
- `0x100712be0`
- `0x100755b10`
- `0x100a16470`
- `0x1011e3aa0`
- `0x101423f20`
- `0x101424460`
- `0x10143cba0`
- `0x10143ced0`
- `0x10149cf70`
- `0x1014bb3b0`
- `0x1014c14d0`
- `0x1014c1830`
- `0x1014c1950`
- `0x1014c1eb0`
- `0x10154ee80`
- `0x10155be70`
- `0x101dd6580`
- `0x101e88ac0`
- `0x101e88db0`
- `0x101eac1b0`
- `0x101eac3c0`
- `0x101eb40a0`

## import_xrefs

- `ADVAPI32!CryptReleaseContext` at `0x101439e5f`
- `ADVAPI32!CryptReleaseContext` at `0x101439ec5`
- `ADVAPI32!CryptReleaseContext` at `0x101439e5f`
- `ADVAPI32!CryptReleaseContext` at `0x101439ec5`
- `secforwarder!CertFreeCertificateContext` at `0x101439e29`
- `secforwarder!CertFreeCertificateContext` at `0x101439e8f`
- `secforwarder!CertFreeCertificateContext` at `0x101439e29`
- `secforwarder!CertFreeCertificateContext` at `0x101439e8f`
- `secforwarder!CertCloseStore` at `0x101439e3e`
- `secforwarder!CertCloseStore` at `0x101439ea4`
- `secforwarder!CertCloseStore` at `0x101439e3e`
- `secforwarder!CertCloseStore` at `0x101439ea4`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x10143a2b2`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x10143a338`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x101439d5e`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x101439d65`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x101439d65`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10143a3f7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10143a5e4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10143a3f7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10143a5e4`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10143a4fc`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10143a4fc`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10143a60d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10143a60d`
- `sqldk!SystemThread_TlsIndex` at `0x100557313`
- `sqldk!SystemThread_TlsIndex` at `0x10058c883`
- `sqldk!SystemThread_TlsIndex` at `0x10058ca66`
- `sqldk!SystemThread_TlsIndex` at `0x1014397c8`
- `sqldk!SystemThread_TlsIndex` at `0x101439d22`
- `sqldk!SystemThread_TlsIndex` at `0x101439ee8`
- `sqldk!SystemThread_TlsIndex` at `0x10143a021`
- `sqldk!SystemThread_TlsIndex` at `0x10143a0f1`
- `sqldk!SystemThread_TlsIndex` at `0x10143a284`
- `sqldk!SystemThread_TlsOffset` at `0x10055731c`
- `sqldk!SystemThread_TlsOffset` at `0x10058c88c`
- `sqldk!SystemThread_TlsOffset` at `0x10058ca6f`
- `sqldk!SystemThread_TlsOffset` at `0x1014397d9`
- `sqldk!SystemThread_TlsOffset` at `0x101439d33`
- `sqldk!SystemThread_TlsOffset` at `0x101439ef1`
- `sqldk!SystemThread_TlsOffset` at `0x10143a02a`
- `sqldk!SystemThread_TlsOffset` at `0x10143a0fa`
- `sqldk!SystemThread_TlsOffset` at `0x10143a28d`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10143a591`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10143a591`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101439811`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101439fed`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10143a043`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101439811`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101439fed`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10143a043`
- `sqldk!??_V@YAXPEAX@Z` at `0x10143994d`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014399b9`
- `sqldk!??_V@YAXPEAX@Z` at `0x101439abd`
- `sqldk!??_V@YAXPEAX@Z` at `0x101439b4c`
- `sqldk!??_V@YAXPEAX@Z` at `0x101439cf8`
- `sqldk!??_V@YAXPEAX@Z` at `0x10143994d`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014399b9`
- `sqldk!??_V@YAXPEAX@Z` at `0x101439abd`
- `sqldk!??_V@YAXPEAX@Z` at `0x101439b4c`
- `sqldk!??_V@YAXPEAX@Z` at `0x101439cf8`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x10143a3ad`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x10143a3ad`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x10143a3cb`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x10143a3cb`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10143a15a`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10143a15a`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10143a166`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10143a166`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesFido@@SAPEBV1@XZ` at `0x10058cab7`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesFido@@SAPEBV1@XZ` at `0x10058cab7`
- `sqlmin!?FControlNodeDwShellDb@@YA_NXZ` at `0x10143a1ce`
- `sqlmin!?FControlNodeDwShellDb@@YA_NXZ` at `0x10143a1ce`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x10143a371`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x10143a371`
- `sqlmin!GetXdbServerGlobals` at `0x10058c9af`
- `sqlmin!GetXdbServerGlobals` at `0x10058ca91`
- `sqlmin!GetXdbServerGlobals` at `0x10058caa4`
- `sqlmin!GetXdbServerGlobals` at `0x101439890`
- `sqlmin!GetXdbServerGlobals` at `0x10143a08f`
- `sqlmin!GetXdbServerGlobals` at `0x10143a0af`
- `sqlmin!GetXdbServerGlobals` at `0x10143a18f`
- `sqlmin!GetXdbServerGlobals` at `0x10143a204`
- `sqlmin!GetXdbServerGlobals` at `0x10143a25d`
- `sqlmin!GetXdbServerGlobals` at `0x10143a411`
- `sqlmin!GetXdbServerGlobals` at `0x10143a554`
- `sqlmin!GetXdbServerGlobals` at `0x10143a564`
- `sqlmin!GetXdbServerGlobals` at `0x10143a660`
- `sqlmin!GetXdbServerGlobals` at `0x10058c9af`
- `sqlmin!GetXdbServerGlobals` at `0x10058ca91`
- `sqlmin!GetXdbServerGlobals` at `0x10058caa4`
- `sqlmin!GetXdbServerGlobals` at `0x101439890`
- `sqlmin!GetXdbServerGlobals` at `0x10143a08f`
- `sqlmin!GetXdbServerGlobals` at `0x10143a0af`
- `sqlmin!GetXdbServerGlobals` at `0x10143a18f`
- `sqlmin!GetXdbServerGlobals` at `0x10143a204`
- `sqlmin!GetXdbServerGlobals` at `0x10143a25d`
- `sqlmin!GetXdbServerGlobals` at `0x10143a411`
- `sqlmin!GetXdbServerGlobals` at `0x10143a554`
- `sqlmin!GetXdbServerGlobals` at `0x10143a564`
- `sqlmin!GetXdbServerGlobals` at `0x10143a660`

## string_xrefs

- `0x10143a5ff`: `sql\ntdbms\msql\security\src\seccontext.cpp`
- `0x101439a05`: `Getting sid from Cert SubjectName`
- `0x10143a5d8`: `!pLgnInfo->m_pbSID`

## pseudocode

```c

```
