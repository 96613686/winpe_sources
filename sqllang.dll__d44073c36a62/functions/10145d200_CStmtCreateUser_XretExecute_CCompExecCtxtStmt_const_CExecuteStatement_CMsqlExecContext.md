# CStmtCreateUser::XretExecute(CCompExecCtxtStmt const &,CExecuteStatement *,CMsqlExecContext *)

- ea: `0x10145d200`
- end: `0x10145fff1`
- name: `?XretExecute@CStmtCreateUser@@UEBA?AW4EXRetType@@AEBVCCompExecCtxtStmt@@PEAVCExecuteStatement@@PEAVCMsqlExecContext@@@Z`
- size: `11761`
- prototype: ``
- caller_count: `1`
- callee_count: `44`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1014750b0`

## callees

- `0x100401070`
- `0x100401090`
- `0x100401400`
- `0x100401433`
- `0x100403080`
- `0x10040be50`
- `0x10041a970`
- `0x100430960`
- `0x100439ca0`
- `0x100440d70`
- `0x100445500`
- `0x10054bd60`
- `0x1006f7e90`
- `0x1006fa910`
- `0x100755b10`
- `0x100984060`
- `0x100a516f0`
- `0x100ddd9c0`
- `0x101174c30`
- `0x10121d760`
- `0x10121d890`
- `0x10138dab0`
- `0x10138e380`
- `0x10138e6e0`
- `0x101394e70`
- `0x1013b5000`
- `0x101453210`
- `0x10145b010`
- `0x10145b130`
- `0x10145b520`
- `0x10145bd10`
- `0x10145c9b0`
- `0x10145cd10`
- `0x10145d200`
- `0x10149cf70`
- `0x10149e850`
- `0x1014b9c60`
- `0x1014be930`
- `0x1014c1950`
- `0x1014c5210`
- `0x1014c6a30`
- `0x10154c680`
- `0x101e88ac0`
- `0x101eb0560`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x10145e320`
- `RPCRT4!UuidFromStringW` at `0x10145eedb`
- `RPCRT4!UuidFromStringW` at `0x10145e320`
- `RPCRT4!UuidFromStringW` at `0x10145eedb`
- `ADVAPI32!InitializeSid` at `0x10145f707`
- `ADVAPI32!InitializeSid` at `0x10145f707`
- `ole32!CoCreateGuid` at `0x10145d2ba`
- `ole32!CoCreateGuid` at `0x10145f6b4`
- `ole32!CoCreateGuid` at `0x10145d2ba`
- `ole32!CoCreateGuid` at `0x10145f6b4`
- `secforwarder!CertFreeCertificateContext` at `0x10145eb78`
- `secforwarder!CertFreeCertificateContext` at `0x10145eb78`
- `secforwarder!CertCloseStore` at `0x10145eb93`
- `secforwarder!CertCloseStore` at `0x10145eb93`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x10145d90a`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x10145dfc4`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x10145fe10`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x10145e41e`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x10145e44d`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x10145e47c`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10145dd91`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10145ddc5`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10145f82d`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10145dd91`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10145ddc5`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10145f82d`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10145e4f1`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10145e4f1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145d34b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145d62c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145d677`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145d814`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145d852`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145d873`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145d893`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145d95e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145d990`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145d9fa`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145da16`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145da56`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145da72`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145da9f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145daf3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145db10`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145db9f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145dd49`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145dea5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145df65`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145e1aa`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145e231`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145e277`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145e6c5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145e6e5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145e791`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145e81f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145e892`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145e8bc`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145e942`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145e9bb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145ec0a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145ef7a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f0e0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f15d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f17b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f1e6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f21c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f261`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f2fe`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f338`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f3b4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f470`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f517`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f5ea`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f69e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f6cd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f74e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f773`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f7c5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f938`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f971`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145fa80`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145fa9a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145fb05`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145fc67`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145fd7c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145d34b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145d62c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145d677`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145d814`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145d852`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145d873`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145d893`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145d95e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145d990`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145d9fa`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145da16`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145da56`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145da72`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145da9f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145daf3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145db10`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145db9f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145dd49`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145dea5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145df65`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145e1aa`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145e231`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145e277`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145e6c5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145e6e5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145e791`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145e81f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145e892`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145e8bc`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145e942`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145e9bb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145ec0a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145ef7a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f0e0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f15d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f17b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f1e6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f21c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f261`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f2fe`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f338`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f3b4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f470`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f517`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f5ea`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f69e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f6cd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f74e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f773`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f7c5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f938`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145f971`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145fa80`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145fa9a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145fb05`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145fc67`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10145fd7c`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10145f41b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10145f41b`
- `sqldk!SystemThread_TlsIndex` at `0x10145d279`
- `sqldk!SystemThread_TlsIndex` at `0x10145e033`
- `sqldk!SystemThread_TlsIndex` at `0x10145e3da`
- `sqldk!SystemThread_TlsIndex` at `0x10145e9d0`
- `sqldk!SystemThread_TlsIndex` at `0x10145ec1f`
- `sqldk!SystemThread_TlsIndex` at `0x10145ee3d`
- `sqldk!SystemThread_TlsIndex` at `0x10145f537`
- `sqldk!SystemThread_TlsIndex` at `0x10145fd02`
- `sqldk!SystemThread_TlsOffset` at `0x10145d282`
- `sqldk!SystemThread_TlsOffset` at `0x10145e03c`
- `sqldk!SystemThread_TlsOffset` at `0x10145e3e3`
- `sqldk!SystemThread_TlsOffset` at `0x10145e9d9`
- `sqldk!SystemThread_TlsOffset` at `0x10145ec28`
- `sqldk!SystemThread_TlsOffset` at `0x10145ee46`
- `sqldk!SystemThread_TlsOffset` at `0x10145f540`
- `sqldk!SystemThread_TlsOffset` at `0x10145fd0b`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10145e392`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10145e596`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10145e392`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10145e596`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10145e3fe`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10145e3fe`
- `sqldk!??_V@YAXPEAX@Z` at `0x10145e35d`
- `sqldk!??_V@YAXPEAX@Z` at `0x10145e384`
- `sqldk!??_V@YAXPEAX@Z` at `0x10145e7d5`
- `sqldk!??_V@YAXPEAX@Z` at `0x10145ea5d`
- `sqldk!??_V@YAXPEAX@Z` at `0x10145eaf2`
- `sqldk!??_V@YAXPEAX@Z` at `0x10145eb61`
- `sqldk!??_V@YAXPEAX@Z` at `0x10145ecab`
- `sqldk!??_V@YAXPEAX@Z` at `0x10145ed2c`
- `sqldk!??_V@YAXPEAX@Z` at `0x10145ed9b`
- `sqldk!??_V@YAXPEAX@Z` at `0x10145eee6`
- `sqldk!??_V@YAXPEAX@Z` at `0x10145f42b`
- `sqldk!??_V@YAXPEAX@Z` at `0x10145f47a`
- `sqldk!??_V@YAXPEAX@Z` at `0x10145e35d`
- `sqldk!??_V@YAXPEAX@Z` at `0x10145e384`
- `sqldk!??_V@YAXPEAX@Z` at `0x10145e7d5`
- `sqldk!??_V@YAXPEAX@Z` at `0x10145ea5d`
- `sqldk!??_V@YAXPEAX@Z` at `0x10145eaf2`
- `sqldk!??_V@YAXPEAX@Z` at `0x10145eb61`
- `sqldk!??_V@YAXPEAX@Z` at `0x10145ecab`
- `sqldk!??_V@YAXPEAX@Z` at `0x10145ed2c`
- `sqldk!??_V@YAXPEAX@Z` at `0x10145ed9b`
- `sqldk!??_V@YAXPEAX@Z` at `0x10145eee6`
- `sqldk!??_V@YAXPEAX@Z` at `0x10145f42b`
- `sqldk!??_V@YAXPEAX@Z` at `0x10145f47a`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x10145e005`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x10145e005`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x10145e01c`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x10145e01c`
- `sqlTsEs!?GetDefaultCollation@CDbAndSetOptsImplImport@@YAQEBVCDefaultCollation@@G@Z` at `0x10145ddfe`
- `sqlTsEs!?GetDefaultCollation@CDbAndSetOptsImplImport@@YAQEBVCDefaultCollation@@G@Z` at `0x10145ddfe`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x10145d77c`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x10145d8c0`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x10145f7f2`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x10145d77c`

## string_xrefs

- `0x10145e440`: `Security`
- `0x10145e46f`: `Security`
- `0x10145e49e`: `Security`
- `0x10145d392`: `CREATE`
- `0x10145e145`: `CREATE`
- `0x10145e63e`: `CREATE`
- `0x10145ff68`: `CREATE`
- `0x10145e678`: `GETLOGINSIDFAILURE`
- `0x10145e33a`: `CStmtCreateUser::XretExecute`
- `0x10145e15e`: `GETLOGINSID`
- `0x10145e665`: `GETLOGINSID`
- `0x10145d652`: `CREATE USER FROM EXTERNAL PROVIDER`
- `0x10145d605`: `CREATE USER FROM WINDOWS`
- `0x10145f40d`: `sql\ntdbms\msql\security\src\secddl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall CStmtCreateUser::XretExecute(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v8; // ebx
  __int64 v9; // r14
  __int64 v10; // rcx
  __int64 v11; // rcx
  int v12; // eax
  __int64 result; // rax
  __int64 v14; // rax
  wchar_t *v15; // r13
  unsigned __int64 v16; // rcx
  unsigned int v17; // edx
  __int64 v18; // rax
  int v19; // edi
  char v20; // si
  __int64 v21; // rax
  char v22; // bl
  unsigned int v23; // eax
  __int64 v24; // r8
  signed __int64 v25; // rdx
  __int64 v26; // rax
  __int64 v27; // r14
  bool v28; // r12
  const wchar_t *v29; // rdi
  __int64 v30; // rax
  int v31; // ebx
  __int64 v32; // rcx
  unsigned __int64 v33; // rbx
  const void *v34; // rdi
  __int64 v35; // rcx
  int v36; // r8d
  int v37; // edx
  __int64 v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rbx
  bool v42; // r15
  int v43; // eax
  int v44; // ebx
  int v45; // edi
  __int64 v46; // rcx
  __int64 v47; // rdi
  __int64 v48; // rax
  unsigned int v49; // ebx
  int v50; // edx
  __int64 v51; // rdi
  unsigned int v52; // r15d
  __int64 v53; // r14
  int v54; // esi
  struct __crt_locale_pointers *DefaultLocale; // rax
  unsigned __int64 v56; // rbx
  struct __crt_locale_pointers *v57; // rax
  unsigned __int16 v58; // dx
  CDefaultCollation *DefaultCollation; // rbx
  char v60; // cl
  char v61; // bl
  __int64 v62; // rax
  DBTABLE *v63; // rax
  DBTABLE *v64; // rbx
  unsigned int v65; // edi
  const wchar_t *v66; // rbx
  CDefaultCollation *v67; // rax
  struct CGatewayServerPrincipal *ServerPrincipal; // rdi
  __int64 v69; // rbx
  unsigned int v70; // r14d
  __int64 v71; // r14
  int v72; // eax
  RPC_WSTR v73; // rbx
  __int64 v74; // rbx
  __int64 v75; // rax
  void *v76; // rbx
  int v77; // edi
  struct CGatewayServerPrincipal *v78; // rax
  BOOL LoginSidFromLogicalMaster; // ebx
  const wchar_t *v80; // rax
  unsigned int v81; // eax
  unsigned int v82; // r14d
  unsigned __int8 *v83; // rcx
  CDefaultCollation *v84; // rbx
  bool v85; // al
  unsigned __int64 v86; // rcx
  unsigned int v87; // ebx
  _WORD *v88; // rdi
  const struct CSECCertParams::_SECCertParams near *const *v89; // rdx
  __int64 v90; // rbx
  __int64 v91; // rbx
  wchar_t *v92; // rdi
  __int64 v93; // r12
  __int64 v94; // rax
  int v95; // ecx
  __int64 v96; // rcx
  __int64 v97; // rax
  UUID v98; // xmm6
  wchar_t *v99; // rsi
  int v100; // ecx
  __int64 v101; // rax
  bool v102; // bl
  unsigned int *p_Size; // rdx
  bool v104; // r8
  __int64 v105; // r9
  __int64 v106; // rax
  __int64 v107; // rbx
  int v108; // ebx
  int v109; // r13d
  __int64 v110; // r12
  __int64 v111; // rax
  const wchar_t *v112; // r15
  unsigned int v113; // r12d
  char v114; // bl
  unsigned __int64 v115; // rdi
  struct CLangInfo *LangInfoByLCID; // rbx
  int v117; // edx
  int v118; // ecx
  unsigned int v119; // edi
  signed __int64 v120; // rdx
  __int64 v121; // rax
  unsigned int *v122; // rbx
  int v123; // ecx
  __int64 v124; // rax
  int v125; // eax
  bool v126; // bl
  bool v127; // al
  __int16 v128; // ax
  struct __crt_locale_pointers *v129; // rax
  const void *v130; // rdx
  char v131; // r15
  __int64 v132; // rbx
  __int64 v133; // rax
  __int64 v134; // rax
  __int64 (__fastcall ***v135)(_QWORD); // rbx
  __int64 v136; // rdi
  __int64 v137; // r9
  int v138; // ecx
  __int64 v139; // rax
  GUID *v140; // rcx
  __int64 *v141; // rdx
  __int64 (__fastcall ***v142)(_QWORD); // rax
  __int64 v143; // r14
  int UserDbAccessEPS; // eax
  __int64 v145; // rax
  const wchar_t *v146; // r8
  __int64 v147; // rax
  __int64 v148; // r14
  __int64 v149; // rax
  int v150; // ebx
  _QWORD *ThreadLocalStoragePointer; // rdx
  __int64 v152; // rcx
  __int64 v153; // rbx
  bool v154; // al
  int v155; // eax
  unsigned int v156; // esi
  __int64 v157; // rbx
  __int64 v158; // rax
  __int64 v159; // rbx
  __int64 v160; // rax
  SQLLEN v161; // [rsp+20h] [rbp-E0h]
  unsigned int v162; // [rsp+20h] [rbp-E0h]
  int v163; // [rsp+20h] [rbp-E0h]
  int v164; // [rsp+20h] [rbp-E0h]
  SQLLEN v165; // [rsp+20h] [rbp-E0h]
  int v166; // [rsp+20h] [rbp-E0h]
  wchar_t *v167; // [rsp+20h] [rbp-E0h]
  int v168; // [rsp+20h] [rbp-E0h]
  wchar_t *v169; // [rsp+28h] [rbp-D8h]
  unsigned int *v170; // [rsp+30h] [rbp-D0h]
  char v171; // [rsp+70h] [rbp-90h]
  bool v172; // [rsp+71h] [rbp-8Fh]
  char v173; // [rsp+72h] [rbp-8Eh] BYREF
  char v174; // [rsp+73h] [rbp-8Dh]
  char v175[4]; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int DestinationSize; // [rsp+78h] [rbp-88h] BYREF
  bool DestinationSize_4; // [rsp+7Ch] [rbp-84h] BYREF
  __int64 v178; // [rsp+80h] [rbp-80h]
  unsigned int Size; // [rsp+88h] [rbp-78h] BYREF
  unsigned int Size_4; // [rsp+8Ch] [rbp-74h]
  bool v181[8]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v182; // [rsp+98h] [rbp-68h]
  bool v183; // [rsp+A0h] [rbp-60h] BYREF
  bool v184; // [rsp+A1h] [rbp-5Fh] BYREF
  char v185; // [rsp+A2h] [rbp-5Eh] BYREF
  unsigned __int8 v186; // [rsp+A3h] [rbp-5Dh]
  unsigned int SourceSize[3]; // [rsp+A4h] [rbp-5Ch] BYREF
  unsigned __int16 v188[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int16 v189; // [rsp+B4h] [rbp-4Ch]
  unsigned int v190; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v191; // [rsp+C0h] [rbp-40h]
  __int64 v192; // [rsp+C8h] [rbp-38h]
  int v193; // [rsp+D0h] [rbp-30h]
  int v194; // [rsp+D4h] [rbp-2Ch]
  struct CGatewayServerPrincipal *v195; // [rsp+D8h] [rbp-28h]
  struct IMemObj *v196; // [rsp+E0h] [rbp-20h]
  __int64 v197; // [rsp+E8h] [rbp-18h]
  int v198; // [rsp+F0h] [rbp-10h]
  __int64 v199; // [rsp+F8h] [rbp-8h]
  int v200; // [rsp+100h] [rbp+0h] BYREF
  int v201; // [rsp+104h] [rbp+4h] BYREF
  int v202; // [rsp+108h] [rbp+8h] BYREF
  int v203; // [rsp+10Ch] [rbp+Ch]
  int v204; // [rsp+110h] [rbp+10h]
  unsigned int v205; // [rsp+114h] [rbp+14h]
  void *Source; // [rsp+118h] [rbp+18h] BYREF
  CDefaultCollation *v207; // [rsp+120h] [rbp+20h]
  __int64 v208; // [rsp+128h] [rbp+28h] BYREF
  _DWORD v209[2]; // [rsp+130h] [rbp+30h] BYREF
  char v210; // [rsp+138h] [rbp+38h]
  unsigned __int8 v211; // [rsp+139h] [rbp+39h]
  char v212; // [rsp+13Ah] [rbp+3Ah]
  int v213; // [rsp+13Ch] [rbp+3Ch]
  __int64 v214; // [rsp+140h] [rbp+40h]
  int v215; // [rsp+148h] [rbp+48h] BYREF
  int v216; // [rsp+14Ch] [rbp+4Ch]
  RPC_WSTR StringUuid[2]; // [rsp+150h] [rbp+50h] BYREF
  __int128 v218; // [rsp+160h] [rbp+60h] BYREF
  RPC_WSTR v219; // [rsp+170h] [rbp+70h] BYREF
  __int16 *v220; // [rsp+178h] [rbp+78h]
  unsigned int *v221; // [rsp+180h] [rbp+80h]
  __int64 v222; // [rsp+188h] [rbp+88h]
  __int64 v223; // [rsp+190h] [rbp+90h]
  void *v224[2]; // [rsp+198h] [rbp+98h] BYREF
  HCERTSTORE hCertStore[2]; // [rsp+1A8h] [rbp+A8h] BYREF
  int v226; // [rsp+1B8h] [rbp+B8h]
  __int64 v227; // [rsp+1C0h] [rbp+C0h]
  PCCERT_CONTEXT pCertContext; // [rsp+1C8h] [rbp+C8h]
  char v229; // [rsp+1D0h] [rbp+D0h]
  const wchar_t *v230; // [rsp+1D8h] [rbp+D8h] BYREF
  int v231; // [rsp+1E0h] [rbp+E0h]
  _BYTE *v232; // [rsp+1E8h] [rbp+E8h] BYREF
  int v233; // [rsp+1F0h] [rbp+F0h]
  wchar_t *v234; // [rsp+1F8h] [rbp+F8h] BYREF
  unsigned int v235; // [rsp+200h] [rbp+100h]
  wchar_t *v236; // [rsp+208h] [rbp+108h] BYREF
  unsigned int v237; // [rsp+210h] [rbp+110h]
  wchar_t *v238; // [rsp+218h] [rbp+118h] BYREF
  unsigned int v239; // [rsp+220h] [rbp+120h]
  wchar_t *v240; // [rsp+228h] [rbp+128h] BYREF
  unsigned int v241; // [rsp+230h] [rbp+130h]
  wchar_t *v242; // [rsp+238h] [rbp+138h] BYREF
  unsigned int v243; // [rsp+240h] [rbp+140h]
  wchar_t *v244; // [rsp+248h] [rbp+148h] BYREF
  unsigned int v245; // [rsp+250h] [rbp+150h]
  __int64 v246; // [rsp+258h] [rbp+158h] BYREF
  int v247; // [rsp+260h] [rbp+160h]
  __int64 v248; // [rsp+268h] [rbp+168h] BYREF
  int v249; // [rsp+270h] [rbp+170h]
  __int64 v250; // [rsp+278h] [rbp+178h] BYREF
  int v251; // [rsp+280h] [rbp+180h]
  GUID v252; // [rsp+290h] [rbp+190h] BYREF
  __int64 v253; // [rsp+2A0h] [rbp+1A0h]
  __int128 v254; // [rsp+2B0h] [rbp+1B0h] BYREF
  GUID v255; // [rsp+2C0h] [rbp+1C0h] BYREF
  UUID v256; // [rsp+2D0h] [rbp+1D0h] BYREF
  GUID v257; // [rsp+2E0h] [rbp+1E0h] BYREF
  UUID v258; // [rsp+2F0h] [rbp+1F0h] BYREF
  GUID v259; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v260[24]; // [rsp+310h] [rbp+210h] BYREF
  __int64 v261; // [rsp+328h] [rbp+228h]
  _BYTE v262[24]; // [rsp+338h] [rbp+238h] BYREF
  __int64 v263; // [rsp+350h] [rbp+250h]
  _DWORD v264[6]; // [rsp+360h] [rbp+260h] BYREF
  void *v265; // [rsp+378h] [rbp+278h]
  _BYTE v266[24]; // [rsp+388h] [rbp+288h] BYREF
  __int64 v267; // [rsp+3A0h] [rbp+2A0h]
  _DWORD v268[6]; // [rsp+3B0h] [rbp+2B0h] BYREF
  void *v269; // [rsp+3C8h] [rbp+2C8h]
  _BYTE v270[24]; // [rsp+3D8h] [rbp+2D8h] BYREF
  __int64 v271; // [rsp+3F0h] [rbp+2F0h]
  _DWORD v272[6]; // [rsp+400h] [rbp+300h] BYREF
  void *v273; // [rsp+418h] [rbp+318h]
  _BYTE v274[24]; // [rsp+428h] [rbp+328h] BYREF
  __int64 v275; // [rsp+440h] [rbp+340h]
  _DWORD v276[6]; // [rsp+450h] [rbp+350h] BYREF
  void *v277; // [rsp+468h] [rbp+368h]
  _BYTE v278[24]; // [rsp+478h] [rbp+378h] BYREF
  __int64 v279; // [rsp+490h] [rbp+390h]
  _DWORD v280[6]; // [rsp+4A0h] [rbp+3A0h] BYREF
  void *v281; // [rsp+4B8h] [rbp+3B8h]
  _DWORD v282[6]; // [rsp+4C8h] [rbp+3C8h] BYREF
  void *v283; // [rsp+4E0h] [rbp+3E0h]
  char v284[8]; // [rsp+4F0h] [rbp+3F0h] BYREF
  int v285; // [rsp+4F8h] [rbp+3F8h]
  int v286; // [rsp+500h] [rbp+400h]
  char **v287; // [rsp+508h] [rbp+408h]
  char *v288; // [rsp+510h] [rbp+410h]
  __int64 v289; // [rsp+518h] [rbp+418h]
  char *v290; // [rsp+520h] [rbp+420h] BYREF
  int v291; // [rsp+528h] [rbp+428h]
  int v292; // [rsp+52Ch] [rbp+42Ch]
  const wchar_t *v293; // [rsp+530h] [rbp+430h]
  __int64 v294; // [rsp+538h] [rbp+438h]
  const wchar_t *v295; // [rsp+540h] [rbp+440h]
  int v296; // [rsp+548h] [rbp+448h]
  int v297; // [rsp+54Ch] [rbp+44Ch]
  __int64 v298; // [rsp+550h] [rbp+450h]
  int v299; // [rsp+558h] [rbp+458h]
  int v300; // [rsp+55Ch] [rbp+45Ch]
  __int64 v301; // [rsp+560h] [rbp+460h]
  int v302; // [rsp+568h] [rbp+468h]
  int v303; // [rsp+56Ch] [rbp+46Ch]
  char v304; // [rsp+570h] [rbp+470h] BYREF
  __int64 v305; // [rsp+740h] [rbp+640h]
  __int64 v306; // [rsp+748h] [rbp+648h]
  char v307; // [rsp+750h] [rbp+650h] BYREF
  char v308[8]; // [rsp+770h] [rbp+670h] BYREF
  int v309; // [rsp+778h] [rbp+678h]
  int v310; // [rsp+780h] [rbp+680h]
  char **v311; // [rsp+788h] [rbp+688h]
  char *v312; // [rsp+790h] [rbp+690h]
  __int64 v313; // [rsp+798h] [rbp+698h]
  char *v314; // [rsp+7A0h] [rbp+6A0h] BYREF
  int v315; // [rsp+7A8h] [rbp+6A8h]
  int v316; // [rsp+7ACh] [rbp+6ACh]
  const wchar_t *v317; // [rsp+7B0h] [rbp+6B0h]
  __int64 v318; // [rsp+7B8h] [rbp+6B8h]
  const wchar_t *v319; // [rsp+7C0h] [rbp+6C0h]
  int v320; // [rsp+7C8h] [rbp+6C8h]
  int v321; // [rsp+7CCh] [rbp+6CCh]
  __int64 v322; // [rsp+7D0h] [rbp+6D0h]
  int v323; // [rsp+7D8h] [rbp+6D8h]
  int v324; // [rsp+7DCh] [rbp+6DCh]
  __int64 v325; // [rsp+7E0h] [rbp+6E0h]
  int v326; // [rsp+7E8h] [rbp+6E8h]
  int v327; // [rsp+7ECh] [rbp+6ECh]
  char v328; // [rsp+7F0h] [rbp+6F0h] BYREF
  __int64 v329; // [rsp+9C0h] [rbp+8C0h]
  __int64 v330; // [rsp+9C8h] [rbp+8C8h]
  char v331; // [rsp+9D0h] [rbp+8D0h] BYREF
  char v332[8]; // [rsp+9F0h] [rbp+8F0h] BYREF
  int v333; // [rsp+9F8h] [rbp+8F8h]
  int v334; // [rsp+A00h] [rbp+900h]
  char **v335; // [rsp+A08h] [rbp+908h]
  char *v336; // [rsp+A10h] [rbp+910h]
  __int64 v337; // [rsp+A18h] [rbp+918h]
  char *v338; // [rsp+A20h] [rbp+920h] BYREF
  int v339; // [rsp+A28h] [rbp+928h]
  int v340; // [rsp+A2Ch] [rbp+92Ch]
  const wchar_t *v341; // [rsp+A30h] [rbp+930h]
  __int64 v342; // [rsp+A38h] [rbp+938h]
  const wchar_t *v343; // [rsp+A40h] [rbp+940h]
  int v344; // [rsp+A48h] [rbp+948h]
  int v345; // [rsp+A4Ch] [rbp+94Ch]
  __int64 v346; // [rsp+A50h] [rbp+950h]
  int v347; // [rsp+A58h] [rbp+958h]
  int v348; // [rsp+A5Ch] [rbp+95Ch]
  __int64 v349; // [rsp+A60h] [rbp+960h]
  int v350; // [rsp+A68h] [rbp+968h]
  int v351; // [rsp+A6Ch] [rbp+96Ch]
  char v352; // [rsp+A70h] [rbp+970h] BYREF
  __int64 v353; // [rsp+C40h] [rbp+B40h]
  __int64 v354; // [rsp+C48h] [rbp+B48h]
  char v355; // [rsp+C50h] [rbp+B50h] BYREF
  char v356[8]; // [rsp+C70h] [rbp+B70h] BYREF
  int v357; // [rsp+C78h] [rbp+B78h]
  int v358; // [rsp+C80h] [rbp+B80h]
  char **v359; // [rsp+C88h] [rbp+B88h]
  char *v360; // [rsp+C90h] [rbp+B90h]
  __int64 v361; // [rsp+C98h] [rbp+B98h]
  char *v362; // [rsp+CA0h] [rbp+BA0h] BYREF
  int v363; // [rsp+CA8h] [rbp+BA8h]
  int v364; // [rsp+CACh] [rbp+BACh]
  const wchar_t *v365; // [rsp+CB0h] [rbp+BB0h]
  __int64 v366; // [rsp+CB8h] [rbp+BB8h]
  const wchar_t *v367; // [rsp+CC0h] [rbp+BC0h]
  int v368; // [rsp+CC8h] [rbp+BC8h]
  int v369; // [rsp+CCCh] [rbp+BCCh]
  __int64 v370; // [rsp+CD0h] [rbp+BD0h]
  int v371; // [rsp+CD8h] [rbp+BD8h]
  int v372; // [rsp+CDCh] [rbp+BDCh]
  __int64 v373; // [rsp+CE0h] [rbp+BE0h]
  int v374; // [rsp+CE8h] [rbp+BE8h]
  int v375; // [rsp+CECh] [rbp+BECh]
  char v376; // [rsp+CF0h] [rbp+BF0h] BYREF
  __int64 v377; // [rsp+EC0h] [rbp+DC0h]
  __int64 v378; // [rsp+EC8h] [rbp+DC8h]
  char v379; // [rsp+ED0h] [rbp+DD0h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+EF0h] [rbp+DF0h] BYREF
  UUID Uuid; // [rsp+F00h] [rbp+E00h] BYREF
  __int128 v382; // [rsp+F10h] [rbp+E10h] BYREF
  __int64 v383; // [rsp+F20h] [rbp+E20h]
  GUID pguid; // [rsp+F28h] [rbp+E28h] BYREF
  GUID v385; // [rsp+F38h] [rbp+E38h] BYREF
  char v386[24]; // [rsp+F48h] [rbp+E48h] BYREF
  _BYTE v387[6992]; // [rsp+F60h] [rbp+E60h] BYREF
  unsigned __int8 Destination[8]; // [rsp+2AB0h] [rbp+29B0h] BYREF
  int v389; // [rsp+2AB8h] [rbp+29B8h]
  char v390[84]; // [rsp+2ABCh] [rbp+29BCh] BYREF
  wchar_t v391[136]; // [rsp+2B10h] [rbp+2A10h] BYREF
  wchar_t v392[136]; // [rsp+2C20h] [rbp+2B20h] BYREF
  _BYTE v393[272]; // [rsp+2D30h] [rbp+2C30h] BYREF
  wchar_t v394[136]; // [rsp+2E40h] [rbp+2D40h] BYREF

  v253 = -2;
  v223 = a4;
  v222 = a3;
  *(_QWORD *)&SourceSize[1] = a2;
  v178 = a1;
  v196 = *(struct IMemObj **)(a4 + 120);
  v8 = *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                     + SystemThread_TlsIndex)
                                                   + SystemThread_TlsOffset)
                                       + 80LL)
                           + 8LL);
  Size_4 = v8;
  v9 = *(_QWORD *)(a3 + 56);
  v197 = v9;
  pguid = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
  CoCreateGuid(&pguid);
  if ( FIsDwFidoDatabaseType(v8) )
  {
    if ( *(_BYTE *)(GetXdbServerGlobals(v10) + 12004)
      && *(_BYTE *)(GetXdbServerGlobals(v11) + 12009)
      && (*(_BYTE *)(CFeatureSwitchesFido::GetCurrentInstance() + 77) || (*((_BYTE *)qword_102ECFB10 + 1512) & 0x10) != 0) )
    {
      v12 = *(_DWORD *)(a1 + 2432);
      if ( v12 == 7 )
      {
        if ( !byte_102EDCED4 )
          ex_raise(331, 68, 16, 2);
      }
      else if ( v12 != 1 && !byte_102EDCED4 )
      {
        ex_raise(331, 68, 16, 3);
      }
    }
    result = CStatement::XretDwFidoExecuteOnGLMS(a1, a4, v8, 0);
    if ( (_DWORD)result != 27 )
    {
      if ( !(_DWORD)result )
        *(_BYTE *)(a3 + 176) |= 0x10u;
      return result;
    }
  }
  v14 = *(_QWORD *)(a2 + 72);
  v205 = 4;
  if ( (*(_BYTE *)(v14 + 270) & 4) != 0 && (qword_102F21DB4 & 1) != 0 )
  {
    v309 = 327680;
    v310 = 0;
    v311 = &v314;
    v312 = &v328;
    v329 = 0;
    v313 = 0;
    v330 = 0;
    v314 = &v331;
    v315 = 32;
    v316 = 4;
    v322 = 0;
    v323 = 0;
    v324 = 2;
    v325 = 0;
    v326 = 0;
    v327 = 3;
    v317 = L"CREATE";
    v318 = 12;
    v319 = L"START";
    v320 = 10;
    v321 = 1;
    XeCloudPkg::azuresqldb_user_ddl::Publish((XeCloudPkg::azuresqldb_user_ddl *)v308);
  }
  v192 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(*(_QWORD *)v9 + 56LL))(
           v9,
           v8,
           0,
           0,
           0,
           0);
  v15 = 0;
  v16 = *(_QWORD *)(a1 + 2240);
  if ( v16 )
  {
    v15 = *(wchar_t **)(v16 + 8);
    v17 = *(_DWORD *)(v16 + 16);
  }
  else
  {
    v17 = 0;
  }
  Size = v17;
  DestinationSize = 85;
  v220 = 0;
  v18 = *(_QWORD *)(a1 + 2400);
  v199 = v18;
  if ( v18 )
  {
    v16 = *(_QWORD *)(v18 + 8);
    v220 = (__int16 *)v16;
    v203 = *(_DWORD *)(v18 + 16);
  }
  else
  {
    v203 = 0;
  }
  Uuid = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
  v19 = *(_DWORD *)(a1 + 2432);
  v193 = v19;
  if ( v19 == 1 && v17 )
  {
    v20 = 1;
    v173 = 1;
    v171 = 0;
    goto LABEL_27;
  }
  v20 = 0;
  v173 = 0;
  if ( v19 == 2 && v17 )
  {
    v171 = 1;
    goto LABEL_27;
  }
  v171 = 0;
  v173 = 0;
  if ( v19 != 3 || (v173 = 0, !v17) )
  {
LABEL_27:
    v174 = 0;
    if ( !v17 )
      goto LABEL_33;
    goto LABEL_28;
  }
  v174 = 1;
  v173 = 0;
LABEL_28:
  if ( v15 )
  {
    v16 = 0;
    if ( (unsigned __int64)v17 >> 1 )
    {
      v21 = 0;
      while ( v15[v21] != 92 )
      {
        v16 = (unsigned int)(v16 + 1);
        if ( ++v21 >= (__int64)((unsigned __int64)v17 >> 1) )
          goto LABEL_33;
      }
      v16 = (unsigned __int64)&v15[(int)v16];
      if ( v16 )
      {
        v22 = 1;
        goto LABEL_34;
      }
    }
  }
LABEL_33:
  v22 = 0;
LABEL_34:
  v172 = ((v19 - 4) & 0xFFFFFFFD) == 0;
  v23 = *(_DWORD *)(a1 + 2216);
  v24 = *(_QWORD *)(a1 + 2208);
  if ( v24 && v23 && (v16 = 0, (v25 = (unsigned __int64)v23 >> 1) != 0) )
  {
    v26 = 0;
    while ( *(_WORD *)(v24 + 2 * v26) != 92 )
    {
      v16 = (unsigned int)(v16 + 1);
      if ( ++v26 >= v25 )
        goto LABEL_40;
    }
    v182 = v24 + 2LL * (int)v16;
  }
  else
  {
LABEL_40:
    v182 = 0;
  }
  v191 = *(_QWORD *)(a1 + 2256);
  v27 = *(_QWORD *)(a1 + 2304);
  v208 = v27;
  v28 = v27 != 0;
  DestinationSize_4 = v27 != 0;
  v175[0] = 0;
  if ( (*(_DWORD *)(GetXdbServerGlobals(v16) + 11976) || (unsigned int)IsVDWFrontendInstance())
    && (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)&SourceSize[1] + 72LL) + 270LL) & 2) == 0
    && (v22 || v182) )
  {
    ex_raise(419, 6, 16, 18, 48, L"CREATE USER FROM WINDOWS");
  }
  if ( v19 == 7 && !*(_DWORD *)(qword_102ECFB00 + 14504) && !IsBoxAADEnabled(0) )
    ex_raise(375, 25, 16, 1, 68, L"CREATE USER FROM EXTERNAL PROVIDER");
  v29 = 0;
  v30 = *(_QWORD *)(a1 + 2408);
  if ( v30 )
  {
    v29 = *(const wchar_t **)(v30 + 8);
    v31 = *(_DWORD *)(v30 + 16);
  }
  else
  {
    v31 = 0;
  }
  v204 = v31;
  LOBYTE(v194) = 0;
  v32 = *(unsigned int *)(a1 + 2216);
  *(_QWORD *)&v218 = *(_QWORD *)(a1 + 2208);
  DWORD2(v218) = v32;
  v254 = v218;
  LOWORD(v161) = Size_4;
  CStmtOwnerMgmt::ErrorOutIfCloudLifterUnchangeablePrincipal(v32, &v254, 13105);
  if ( !v31 )
    goto LABEL_66;
  v33 = (unsigned __int64)v31 >> 1;
  if ( CompareStringWEnglishNoCase(1u, 0, v29, v33, L"ON", 3) == 2 )
  {
    LOBYTE(v194) = 1;
LABEL_66:
    v34 = 0;
    goto LABEL_67;
  }
  v43 = CompareStringWEnglishNoCase(1u, 0, v29, v33, L"OFF", 4);
  v44 = (unsigned __int8)v194;
  v34 = 0;
  if ( v43 == 2 )
    v44 = 0;
  v194 = v44;
LABEL_67:
  v35 = v199;
  if ( v199 )
  {
    v36 = 0;
    v37 = 0;
    if ( OptSecDDLDBPrincipalOptions )
    {
      v38 = 0;
      v39 = 0;
      while ( *(_DWORD *)((char *)&OptSecDDLDBPrincipalOptions + v39 + 12) != 22 )
      {
        ++v37;
        ++v38;
        v39 = 24 * v38;
        if ( !*((_QWORD *)&OptSecDDLDBPrincipalOptions + 3 * v38) )
          goto LABEL_72;
      }
      v36 = *((_DWORD *)&OptSecDDLDBPrincipalOptions + 6 * v37 + 2);
      v40 = *((_QWORD *)&OptSecDDLDBPrincipalOptions + 3 * v37);
    }
    else
    {
LABEL_72:
      v40 = 0;
    }
    if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)&SourceSize[1] + 72LL) + 270LL) & 4) == 0 )
    {
      LODWORD(v161) = v36;
      ex_raise(1, 2, 16, 30, v161, v40);
    }
    if ( v20 || v174 || v171 || v193 == 7 || v191 || v172 )
      ex_raise(331, 68, 16, 1, v161);
    v41 = v182;
    if ( v182 )
      ex_raise(331, 69, 16, 1);
    if ( !v27 )
    {
      ex_raise(331, 62, 16, 2);
      v42 = v172;
      goto LABEL_93;
    }
    v35 = v199;
LABEL_103:
    v48 = *(_QWORD *)(a1 + 2304);
    if ( v48 )
    {
      v34 = *(const void **)(v48 + 8);
      v49 = *(_DWORD *)(v48 + 16);
    }
    else
    {
      v49 = 0;
    }
    if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)&SourceSize[1] + 72LL) + 270LL) & 4) == 0 )
    {
      if ( v182 )
        ex_raise(332, 37, 16, 1, L"SID");
      if ( v49 > 0x55 )
        ex_raise(154, 19, 16, 1);
      memcpy_s(Destination, 0x55u, v34, v49);
      DestinationSize = v49;
      v42 = v172;
      if ( !v172 )
        ex_raise(332, 42, 16, 1);
      if ( v49 != 28 )
        ex_raise(330, 60, 16, 1);
      if ( !FIsOrphanedUserSid(Destination, v49) )
        ex_raise(330, 60, 16, 1);
      goto LABEL_92;
    }
    v42 = v172;
    if ( v193 == 7 || v20 || v172 || v174 || v171 || v191 )
    {
      v50 = 70;
    }
    else
    {
      if ( v35 )
      {
LABEL_127:
        if ( v49 != 16 )
          ex_raise(154, 19, 16, 1);
        memcpy_s(Destination, 0x55u, v34, v49);
        DestinationSize = v49;
        if ( v172
          || !v199 && !(unsigned int)FIsGatewaySID(Destination, v49)
          || (unsigned int)FIsGatewaySID(Destination, v49) && Destination[6] == 1
          || (unsigned int)FIsGatewaySID(Destination, v49) && Destination[5] == 1 )
        {
          ex_raise(405, 6, 16, 1, v161);
        }
        goto LABEL_92;
      }
      v50 = 62;
    }
    ex_raise(331, v50, 16, 1, v161);
    goto LABEL_127;
  }
  if ( v27 )
    goto LABEL_103;
  v42 = v172;
LABEL_92:
  v41 = v182;
LABEL_93:
  v45 = *(_DWORD *)(((__int64 (__fastcall *)(_QWORD))g_dbtableFactory[4])(Size_4) + 3888);
  v216 = v45;
  v46 = v191;
  if ( v191 )
  {
    if ( FSystemDBId(Size_4) || v45 != 1 && (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)&SourceSize[1] + 72LL) + 270LL) & 4) == 0 )
      ex_raise(332, 33, 16, 1, v161);
    v47 = *(_QWORD *)&SourceSize[1];
    if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)&SourceSize[1] + 72LL) + 270LL) & 4) != 0 && !byte_102EDCB78 )
      ex_raise(406, 99, 16, 1);
    v46 = v191;
  }
  else
  {
    v47 = *(_QWORD *)&SourceSize[1];
  }
  if ( v20 || v171 || v174 )
  {
    if ( !v42 )
    {
LABEL_149:
      v52 = Size;
      goto LABEL_150;
    }
  }
  else if ( !v42 )
  {
    if ( !v27 )
    {
LABEL_143:
      v51 = v178;
      v15 = *(wchar_t **)(v178 + 2208);
      v52 = *(_DWORD *)(v178 + 2216);
      Size = v52;
      goto LABEL_151;
    }
    goto LABEL_149;
  }
  if ( v41 || (*(_BYTE *)(*(_QWORD *)(v47 + 72) + 270LL) & 4) != 0 && v46 )
    goto LABEL_143;
  v15 = L"public";
  v52 = 12;
  Size = 12;
LABEL_150:
  v51 = v178;
LABEL_151:
  v53 = -1;
  v209[1] = Size_4;
  v210 = 0;
  v214 = 0;
  v186 = ISECManager::CheckPermRule(1380144472, v196, v197, Size_4, Size_4, 0, -1, 21333, 1, 1, 0, 0);
  v211 = v186;
  v209[0] = 1380144472;
  v213 = 21333;
  v212 = 1;
  if ( v186 )
  {
    v54 = 0;
  }
  else
  {
    v255 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
    ISECManager::CheckPermRuleAuditOnly(1380144472, 0, v197, Size_4, 0, 0, 21333, 0, 0, &v255, 0, 0, 0, -1);
    v210 = 1;
    v54 = 0;
    AuditSecurityEvent(109, 3, 0, v15, v52, *(wchar_t **)(v51 + 2208), *(_DWORD *)(v51 + 2216), 0, 0);
    ex_raise(152, 47, 16, 1);
  }
  AuditSecurityEvent(109, 3, 1, v15, v52, *(wchar_t **)(v51 + 2208), *(_DWORD *)(v51 + 2216), 0, 0);
  DefaultLocale = GetDefaultLocale();
  StringCchPrintf_lW(v392, 0x81u, L"%.*s", DefaultLocale, (unsigned __int64)v52 >> 1, v15);
  v56 = (unsigned __int64)*(unsigned int *)(v51 + 2216) >> 1;
  v57 = GetDefaultLocale();
  *(_DWORD *)v188 = StringCchPrintf_lW(v391, 0x81u, L"%.*s", v57, v56, *(_QWORD *)(v51 + 2208));
  DefaultCollation = CDbAndSetOptsImplImport::GetDefaultCollation(
                       (CDbAndSetOptsImplImport *)(unsigned __int16)Size_4,
                       v58);
  v207 = DefaultCollation;
  if ( CDefaultCollation::FEqW(DefaultCollation, *(const wchar_t **)(v51 + 2208), *(_DWORD *)(v51 + 2216), L"dbo", 6u)
    || CDefaultCollation::FEqW(DefaultCollation, *(const wchar_t **)(v51 + 2208), *(_DWORD *)(v51 + 2216), L"sys", 6u)
    || CDefaultCollation::FEqW(
         DefaultCollation,
         *(const wchar_t **)(v51 + 2208),
         *(_DWORD *)(v51 + 2216),
         L"INFORMATION_SCHEMA",
         0x24u) )
  {
    ex_raise(150, 23, 16, 1, v391);
  }
  v60 = *(_BYTE *)(*(_QWORD *)(*(_QWORD *)&SourceSize[1] + 72LL) + 270LL) & 4;
  if ( v60 && v191 )
  {
    v234 = v15;
    v235 = v52;
    CheckContainedUserNameConflict(&v234, v196, v192, 2, v391);
LABEL_161:
    v61 = v171;
LABEL_162:
    v62 = v182;
    if ( v173 && v182 )
    {
      if ( !CDefaultCollation::FEqW(v207, *(const wchar_t **)(v51 + 2208), *(_DWORD *)(v51 + 2216), v15, v52) )
        ex_raise(150, 6, 16, 1, v391);
      v62 = v182;
    }
    if ( (v61 || v174) && v62 )
      ex_raise(150, 6, 16, 1, v391);
    v70 = DestinationSize;
    goto LABEL_242;
  }
  v28 = DestinationSize_4;
  if ( !v60 )
    goto LABEL_161;
  v61 = v171;
  if ( v172 || !v52 || v193 == 7 || v171 || v174 || v208 )
    goto LABEL_162;
  v63 = (DBTABLE *)((__int64 (__fastcall *)(_QWORD))g_dbtableFactory[4])(Size_4);
  v64 = v63;
  do
    ++v53;
  while ( aMaster_0[v53] );
  v65 = DBTABLE::CbLogicalDbNameInternal(v63);
  v66 = DBTABLE::LogicalDbNameInternal(v64);
  v67 = (CDefaultCollation *)CDefaultCollation::PDCServer();
  if ( CDefaultCollation::FEqIgnoreCaseW(v67, v66, v65, L"master", 2 * v53) )
  {
    v52 = Size;
    ServerPrincipal = CGatewayServerPrincipals::GetServerPrincipal(
                        *(const struct CCompExecCtxtBasic **)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                              + SystemThread_TlsIndex)
                                                            + SystemThread_TlsOffset),
                        v15,
                        Size);
    v195 = ServerPrincipal;
    v69 = 0;
    if ( !ServerPrincipal )
    {
      v236 = v15;
      v162 = Size_4;
      v237 = Size;
      v69 = (*(__int64 (__fastcall **)(__int64, wchar_t **, __int64))(*(_QWORD *)v197 + 328LL))(v197, &v236, 1);
    }
    if ( (qword_102F21DB4 & 1) != 0 )
    {
      v333 = 327680;
      v334 = 0;
      v335 = &v338;
      v336 = &v352;
      v353 = 0;
      v337 = 0;
      v354 = 0;
      v338 = &v355;
      v339 = 32;
      v340 = 4;
      v346 = 0;
      v347 = 0;
      v348 = 2;
      v349 = 0;
      v350 = 0;
      v351 = 3;
      v341 = L"CREATE";
      v342 = 12;
      v343 = L"GETLOGINSID";
      v344 = 22;
      v345 = 1;
      XeCloudPkg::azuresqldb_user_ddl::Publish((XeCloudPkg::azuresqldb_user_ddl *)v332);
    }
    if ( v69 )
    {
      v71 = (*(unsigned int (__fastcall **)(__int64, unsigned __int8 *, __int64))(*(_QWORD *)v69 + 8LL))(
              v69,
              Destination,
              85);
      v72 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v69 + 24LL))(v69);
      if ( v72 == 7 )
      {
        v54 = 7;
      }
      else if ( v72 == 8 )
      {
        v54 = 8;
      }
      else
      {
        ex_raise(150, 7, 16, 8, v391);
      }
      LOBYTE(v162) = 1;
      if ( (*(__int64 (__fastcall **)(__int64, unsigned __int8 *, _QWORD, _QWORD, unsigned int))(*(_QWORD *)v192 + 240LL))(
             v192,
             Destination,
             (unsigned int)v71,
             0,
             v162) )
      {
        ex_raise(150, 23, 16, 2, v391);
      }
      LOWORD(v198) = -8534;
      if ( &Destination[v71] )
      {
        *(_WORD *)&Destination[v71] = v198;
      }
      else
      {
        *_errno() = 22;
        _invalid_parameter_noinfo();
      }
      v70 = v71 + 2;
      DestinationSize = v70;
      if ( byte_102EDCA55 )
      {
        Uuid = *(UUID *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v69 + 80LL))(v69, &v382);
        if ( *(_QWORD *)&Uuid.Data1 == *(_QWORD *)&Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val.Data1
          && *(_QWORD *)Uuid.Data4 == *(_QWORD *)Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val.Data4 )
        {
          StringUuid[0] = 0;
          AzureActiveDirectoryService::GetTenantId(v196, StringUuid);
          v73 = StringUuid[0];
          if ( StringUuid[0] && UuidFromStringW(StringUuid[0], &Uuid) && *(int *)v188 >= 0 )
          {
            _mm_lfence();
            scierrlog(0x9280u, *(unsigned int *)v188, L"CStmtCreateUser::XretExecute", 2063);
            v52 = Size;
            v70 = DestinationSize;
            v73 = StringUuid[0];
          }
          operator delete[](v73);
        }
      }
    }
    else
    {
      if ( !ServerPrincipal )
        ex_raise(150, 7, 16, 2, v15);
      memcpy_s(Destination, DestinationSize, (char *)ServerPrincipal + 268, *((unsigned int *)ServerPrincipal + 89));
      v70 = *((_DWORD *)ServerPrincipal + 89);
      DestinationSize = v70;
    }
    v195 = ServerPrincipal;
    if ( ServerPrincipal )
    {
      operator delete[](*((void **)ServerPrincipal + 147));
      operator delete(ServerPrincipal, 0x4A8u);
      v28 = 1;
      v175[0] = 1;
      v51 = v178;
      goto LABEL_242;
    }
  }
  else
  {
    Source = 0;
    SourceSize[0] = 0;
    v184 = 0;
    v183 = 0;
    v190 = 7;
    v238 = v15;
    v239 = v52;
    v74 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v75 = *(_QWORD *)(v74 + 256);
    if ( !v75 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v75 = *(_QWORD *)(v74 + 256);
    }
    v76 = *(void **)(v75 + 1000);
    v201 = 0;
    v200 = 0;
    v202 = 0;
    LOBYTE(v162) = 0;
    (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, int *, unsigned int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
      s_pServerConf,
      L"Security",
      L"RetryUserDDLXOdbcInitialBackoff",
      &v201,
      v162,
      0);
    LOBYTE(v163) = 0;
    (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, int *, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
      s_pServerConf,
      L"Security",
      L"RetryUserDDLXOdbcMaxDuration",
      &v200,
      v163,
      0);
    LOBYTE(v164) = 0;
    (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, int *, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
      s_pServerConf,
      L"Security",
      L"RetryUserDDLXOdbcMaxNoofRetries",
      &v202,
      v164,
      0);
    v77 = v201;
    LODWORD(v382) = v201;
    *((_QWORD *)&v382 + 1) = v200;
    LOWORD(v383) = v202;
    v224[1] = v76;
    v198 = 91;
    v78 = (struct CGatewayServerPrincipal *)operator new(
                                              0x28u,
                                              (struct IMemObj *)v76,
                                              "sql\\ntdbms\\include\\xodbcwrapper.h",
                                              91,
                                              3u);
    v195 = v78;
    if ( v78 )
    {
      *(_OWORD *)v78 = v382;
      *((_QWORD *)v78 + 2) = v383;
      *((_DWORD *)v78 + 6) = v77;
      *((_WORD *)v78 + 14) = 0;
    }
    else
    {
      v78 = 0;
    }
    v224[0] = v78;
    LODWORD(v165) = 0;
    LoginSidFromLogicalMaster = CAutoOdbcConnectionWrapper::GetLoginSidFromLogicalMaster(
                                  (CAutoOdbcConnectionWrapper *)v224,
                                  (const struct MDName *)&v238,
                                  0,
                                  0,
                                  v165,
                                  (unsigned __int8 **)&Source,
                                  SourceSize,
                                  &v184,
                                  &v183,
                                  &v190,
                                  1,
                                  &Uuid);
    operator delete(v224[0], 0x28u);
    if ( (qword_102F21DB4 & 1) != 0 )
    {
      v285 = 327680;
      v286 = 0;
      v287 = &v290;
      v288 = &v304;
      v305 = 0;
      v289 = 0;
      v306 = 0;
      v290 = &v307;
      v291 = 32;
      v292 = 4;
      v298 = 0;
      v299 = 0;
      v300 = 2;
      v301 = 0;
      v302 = 0;
      v303 = 3;
      v293 = L"CREATE";
      v294 = 12;
      v297 = 1;
      if ( LoginSidFromLogicalMaster )
      {
        v80 = L"GETLOGINSID";
        v296 = 22;
      }
      else
      {
        v80 = L"GETLOGINSIDFAILURE";
        v296 = 36;
      }
      v295 = v80;
      XeCloudPkg::azuresqldb_user_ddl::Publish((XeCloudPkg::azuresqldb_user_ddl *)v284);
    }
    if ( !LoginSidFromLogicalMaster || (v81 = SourceSize[0]) == 0 || !Source )
    {
      ex_raise(150, 7, 16, 6, v15);
      v81 = SourceSize[0];
    }
    if ( v81 > 0x55 )
    {
      ex_raise(154, 19, 16, 6);
      v81 = SourceSize[0];
    }
    memcpy_s(Destination, DestinationSize, Source, v81);
    v70 = SourceSize[0];
    if ( SourceSize[0] == 16 || byte_102EDCC3D && SourceSize[0] == 18 && *((_WORD *)Source + 8) == 0xDEAA )
    {
      if ( v190 == 7 )
      {
        v54 = 7;
      }
      else if ( v190 == 8 )
      {
        v54 = 8;
      }
      LOBYTE(v166) = 1;
      if ( (*(__int64 (__fastcall **)(__int64, unsigned __int8 *, _QWORD, _QWORD, int))(*(_QWORD *)v192 + 240LL))(
             v192,
             Destination,
             SourceSize[0],
             0,
             v166) )
      {
        ex_raise(150, 23, 16, 3, v391);
      }
      v82 = SourceSize[0];
      v189 = -8534;
      v83 = &Destination[SourceSize[0]];
      if ( v83 )
      {
        *(_WORD *)v83 = v189;
      }
      else
      {
        *_errno() = 22;
        _invalid_parameter_noinfo();
      }
      v70 = v82 + 2;
    }
    DestinationSize = v70;
    operator delete[](Source);
    v52 = Size;
  }
  v28 = 1;
  v175[0] = 1;
  v51 = v178;
LABEL_242:
  v84 = v207;
  v85 = CDefaultCollation::FEqW(v207, *(const wchar_t **)(v51 + 2208), *(_DWORD *)(v51 + 2216), L"guest", 0xAu);
  v190 = v85;
  if ( v85 )
  {
    if ( !CDefaultCollation::FEqW(v84, v15, v52, L"guest", 0xAu) )
      ex_raise(150, 62, 16, 1);
    if ( v172 )
      ex_raise(150, 6, 16, 1, v391);
  }
  if ( (unsigned int)CSECCertParams::GetCertType(*(_QWORD *)(v51 + 2208), *(unsigned int *)(v51 + 2216), Size_4) != 11 )
  {
    v87 = *(_DWORD *)(v51 + 2216);
    v88 = *(_WORD **)(v51 + 2208);
    v89 = &CSECCertParams::m_rgCertParams + 6 * (int)CSECCertParams::GetCertType(v88, v87, Size_4);
    if ( *(_DWORD *)v89 == 11 && v87 && *v88 == 35
      || !CSECCertParams::FCanDoActionInMode(
            (int)(*((_DWORD *)v89 + 10) << 31) >> 31,
            (const struct CSECCertParams::_SECCertParams *)v89,
            Size_4) )
    {
      ex_raise(152, 47, 16, 1);
    }
    v51 = v178;
  }
  if ( v190 )
  {
    v54 = 0;
    goto LABEL_360;
  }
  if ( v171 )
  {
    v240 = v15;
    v241 = v52;
    v90 = (*(__int64 (__fastcall **)(__int64, wchar_t **, _QWORD))(*(_QWORD *)v192 + 800LL))(v192, &v240, 0);
    if ( !v90 )
    {
      LODWORD(v170) = v52;
      LODWORD(v169) = 13116;
      LODWORD(v167) = 13118;
      ex_raise(151, 51, 16, 1, v167, v169, v170, v15);
    }
    *(_QWORD *)&v218 = 0;
    CSECSessionCryptoContext::GetCryptoContext(
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                      + SystemThread_TlsIndex)
                                                    + SystemThread_TlsOffset)
                                        + 72LL)
                            + 104LL)
                + 264LL)
    + 216LL,
      v264,
      3,
      &v218);
    if ( v264[0] )
    {
      v195 = (struct CGatewayServerPrincipal *)v262;
      v263 = 0;
      CSECCryptoError::DeepCopyCSECCryptoError((CSECCryptoError *)v262, (const struct CSECCryptoError *)v264);
      RaiseCryptoError(v262, 0);
    }
    if ( v265 )
      operator delete[](v265);
    *(_OWORD *)hCertStore = 0;
    v226 = 0;
    v227 = v218;
    pCertContext = 0;
    v229 = 0;
    CSECCertificate::InitFromMD(hCertStore, v268, v196, v90);
    if ( v268[0] )
    {
      v195 = (struct CGatewayServerPrincipal *)v266;
      v267 = 0;
      CSECCryptoError::DeepCopyCSECCryptoError((CSECCryptoError *)v266, (const struct CSECCryptoError *)v268);
      RaiseCryptoError(v266, 0);
    }
    if ( v269 )
      operator delete[](v269);
    CSECCertificate::GetSid(hCertStore, v272, &DestinationSize, Destination);
    if ( v272[0] )
    {
      v195 = (struct CGatewayServerPrincipal *)v270;
      v271 = 0;
      CSECCryptoError::DeepCopyCSECCryptoError((CSECCryptoError *)v270, (const struct CSECCryptoError *)v272);
      RaiseCryptoError(v270, 0);
    }
    if ( v273 )
      operator delete[](v273);
    v54 = 5;
    if ( pCertContext )
    {
      CertFreeCertificateContext(pCertContext);
      pCertContext = 0;
    }
    v86 = (unsigned __int64)hCertStore[0];
    if ( hCertStore[0] )
    {
      CertCloseStore(hCertStore[0], 0);
      hCertStore[0] = 0;
    }
    v70 = DestinationSize;
    goto LABEL_360;
  }
  if ( v174 )
  {
    v242 = v15;
    v243 = v52;
    v91 = (*(__int64 (__fastcall **)(__int64, wchar_t **, _QWORD))(*(_QWORD *)v192 + 960LL))(v192, &v242, 0);
    if ( !v91 )
    {
      LODWORD(v170) = v52;
      LODWORD(v169) = 13141;
      LODWORD(v167) = 13118;
      ex_raise(151, 51, 16, 1, v167, v169, v170, v15);
    }
    v208 = 0;
    CSECSessionCryptoContext::GetCryptoContext(
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                      + SystemThread_TlsIndex)
                                                    + SystemThread_TlsOffset)
                                        + 72LL)
                            + 104LL)
                + 264LL)
    + 216LL,
      v276,
      3,
      &v208);
    if ( v276[0] )
    {
      v195 = (struct CGatewayServerPrincipal *)v274;
      v275 = 0;
      CSECCryptoError::DeepCopyCSECCryptoError((CSECCryptoError *)v274, (const struct CSECCryptoError *)v276);
      RaiseCryptoError(v274, 0);
    }
    if ( v277 )
      operator delete[](v277);
    CSECAsymmetricKey::CSECAsymmetricKey(v387, v208, 0, 0);
    CSECAsymmetricKey::InitFromMD(v387, v280, v196, v91);
    if ( v280[0] )
    {
      v195 = (struct CGatewayServerPrincipal *)v278;
      v279 = 0;
      CSECCryptoError::DeepCopyCSECCryptoError((CSECCryptoError *)v278, (const struct CSECCryptoError *)v280);
      RaiseCryptoError(v278, 0);
    }
    if ( v281 )
      operator delete[](v281);
    CSECAsymmetricKey::GetSid(v387, v282, &DestinationSize, Destination);
    if ( v282[0] )
    {
      v195 = (struct CGatewayServerPrincipal *)v260;
      v261 = 0;
      CSECCryptoError::DeepCopyCSECCryptoError((CSECCryptoError *)v260, (const struct CSECCryptoError *)v282);
      RaiseCryptoError(v260, 0);
    }
    if ( v283 )
      operator delete[](v283);
    v54 = 6;
    CSECAsymmetricKey::~CSECAsymmetricKey((CSECAsymmetricKey *)v387);
    v70 = DestinationSize;
    goto LABEL_360;
  }
  if ( v193 == 7 )
  {
    v173 = 0;
    v185 = 0;
    v92 = 0;
    v93 = v178;
    if ( byte_102EDCA59 )
    {
      v94 = *(_QWORD *)(v178 + 2424);
      if ( v94 )
      {
        v92 = *(wchar_t **)(v94 + 8);
        v95 = *(_DWORD *)(v94 + 16);
      }
      else
      {
        v95 = 0;
      }
      v215 = v95;
    }
    if ( byte_102EDCA55
      && (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)&SourceSize[1] + 72LL) + 270LL) & 4) != 0
      && *(_DWORD *)(qword_102ECFB00 + 14504) )
    {
      v96 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                + SystemThread_TlsIndex)
                                              + SystemThread_TlsOffset)
                                  + 120LL)
                      + 264LL);
      v97 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v96 + 568LL))(v96, v192, 1, 0);
      if ( v97 )
        Uuid = *(UUID *)(*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v97 + 608LL))(v97, v386);
      if ( *(_QWORD *)&Uuid.Data1 == *(_QWORD *)&Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val.Data1
        && _mm_srli_si128((__m128i)Uuid, 8).m128i_u64[0] == *(_QWORD *)Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val.Data4 )
      {
        v219 = 0;
        AzureActiveDirectoryService::GetTenantId(v196, &v219);
        UuidFromStringW(v219, &Uuid);
        operator delete[](v219);
        v52 = Size;
      }
      else
      {
        v52 = Size;
      }
    }
    v98 = Uuid;
    v99 = v392;
    if ( v92 )
      v99 = v92;
    if ( !v15 )
      goto LABEL_315;
    if ( !v52 )
      goto LABEL_315;
    v100 = 0;
    if ( !((unsigned __int64)v52 >> 1) )
      goto LABEL_315;
    v101 = 0;
    while ( v15[v101] != 92 )
    {
      ++v100;
      if ( ++v101 >= (__int64)((unsigned __int64)v52 >> 1) )
        goto LABEL_315;
    }
    if ( v100 >= 0 && v52 - 1 != v100 )
    {
      v102 = v92 != 0;
    }
    else
    {
LABEL_315:
      v102 = v92 != 0;
      if ( !*(_DWORD *)(qword_102ECFB00 + 14504) && !IsBoxAADEnabled(0) )
        ex_raise(154, 7, 16, 1, v99);
    }
    p_Size = (unsigned int *)&v215;
    if ( !v92 )
      p_Size = &Size;
    v256 = v98;
    if ( v92 )
      v15 = v92;
    LOBYTE(v169) = v102;
    LookupFederatedPrincipal(
      v15,
      p_Size,
      v99,
      2,
      &pguid,
      (_DWORD)v169,
      Destination,
      &DestinationSize,
      &v173,
      &v185,
      &v256);
    v54 = 8 - (v173 != 0);
    v70 = DestinationSize;
LABEL_361:
    if ( !v191 )
      goto LABEL_365;
    goto LABEL_362;
  }
  if ( v175[0] )
  {
LABEL_360:
    v93 = v178;
    goto LABEL_361;
  }
  v104 = v172;
  v105 = v199;
  if ( !v172 && !v199 )
  {
    v244 = v15;
    v245 = v52;
    v106 = (*(__int64 (__fastcall **)(__int64, wchar_t **, _QWORD, __int64, _DWORD))(*(_QWORD *)v197 + 328LL))(
             v197,
             &v244,
             0,
             1,
             0);
    v107 = v106;
    if ( v106 )
    {
      v70 = (*(__int64 (__fastcall **)(__int64, unsigned __int8 *, __int64))(*(_QWORD *)v106 + 8LL))(
              v106,
              Destination,
              85);
      v108 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v107 + 24LL))(v107);
      if ( v70 == 1 && Destination[0] == 1 )
        ex_raise(154, 5, 16, 1, v392);
      if ( v108 )
      {
        switch ( v108 )
        {
          case 1:
            v54 = 1;
            break;
          case 2:
            v54 = 2;
            break;
          case 4:
            v54 = 5;
            break;
          case 5:
            v54 = 6;
            break;
          case 7:
            v54 = 7;
            break;
          case 8:
            v54 = 8;
            break;
          case 6:
            LODWORD(v170) = v52;
            LODWORD(v169) = 13115;
            LODWORD(v167) = 13118;
            ex_raise(151, 51, 16, 1, v167, v169, v170, v15);
            break;
          default:
            ex_raise(154, 5, 16, 1, v391);
            break;
        }
      }
      else
      {
        v54 = 0;
      }
      if ( *(_DWORD *)(qword_102ECFB00 + 14504)
        && (unsigned int)(v54 - 7) <= 1
        && !*(_DWORD *)(GetXdbServerGlobals(v86) + 11976)
        && !(unsigned int)IsVDWFrontendInstance()
        && !CDefaultCollation::FEqW(v207, *(const wchar_t **)(v51 + 2208), *(_DWORD *)(v51 + 2216), v15, v52) )
      {
        ex_raise(331, 48, 16, 1);
      }
      if ( v182 && (!v54 || (unsigned int)(v54 - 5) <= 1) )
        ex_raise(150, 6, 16, 1, v391);
      goto LABEL_360;
    }
    v104 = 0;
    v105 = v199;
  }
  v119 = 0;
  if ( !v15 )
    goto LABEL_387;
  if ( !v52 )
    goto LABEL_387;
  v86 = 0;
  v120 = (unsigned __int64)v52 >> 1;
  if ( !v120 )
    goto LABEL_387;
  v121 = 0;
  while ( v15[v121] != 92 )
  {
    v86 = (unsigned int)(v86 + 1);
    if ( ++v121 >= v120 )
      goto LABEL_387;
  }
  v86 = (unsigned __int64)&v15[(int)v86];
  if ( !v86 )
  {
LABEL_387:
    if ( !v105 )
    {
      if ( !v104 )
        ex_raise(150, 7, 16, 1, v392);
      if ( !v28 )
      {
        if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)&SourceSize[1] + 72LL) + 270LL) & 4) != 0 && v191 )
        {
          v122 = 0;
          v221 = 0;
          if ( *(_DWORD *)(qword_102ECFB00 + 14504) )
          {
            v119 = 2;
            v122 = (unsigned int *)operator new[](8u, v196, "sql\\ntdbms\\msql\\security\\src\\secddl.cpp", 2528, 3u);
            if ( v122 )
              operator delete[](0);
            v221 = v122;
            *(_QWORD *)v122 = 0;
          }
          if ( !(unsigned int)GenerateSidForGatewayLogin(v122, v119, 0, Destination, &DestinationSize, 1) )
            ex_raise(151, 67, 16, 1);
          operator delete[](v122);
          v70 = DestinationSize;
          v54 = 0;
          goto LABEL_360;
        }
        if ( CoCreateGuid(&v385) )
          ex_raise(151, 67, 16, 1);
        if ( v70 - 1 > 0x1A )
        {
          v70 = 28;
          *(_DWORD *)pIdentifierAuthority.Value = 0;
          pIdentifierAuthority.Value[4] = 0;
          pIdentifierAuthority.Value[5] = 9;
          if ( InitializeSid(Destination, &pIdentifierAuthority, 5u) )
          {
            v389 = 3;
            memcpy_s(v390, 0x10u, &v385, 0x10u);
            v54 = 0;
            goto LABEL_360;
          }
        }
        ex_raise(151, 67, 16, 1);
      }
      v54 = 0;
      goto LABEL_360;
    }
LABEL_428:
    if ( v203 != 2 )
      ex_raise(331, 63, 16, 1);
    if ( v220 )
    {
      v128 = *v220;
      if ( *v220 == 69 )
        goto LABEL_436;
      switch ( v128 )
      {
        case 'X':
LABEL_435:
          v54 = 8;
          goto LABEL_360;
        case 'e':
LABEL_436:
          v54 = 7;
          goto LABEL_360;
        case 'x':
          goto LABEL_435;
      }
    }
    v54 = 0;
    ex_raise(331, 63, 16, 2);
    goto LABEL_360;
  }
  if ( v105 )
    goto LABEL_428;
  v181[0] = 0;
  v175[0] = 0;
  v123 = 0;
  v124 = 0;
  while ( v15[v124] != 92 )
  {
    ++v123;
    if ( ++v124 >= v120 )
      goto LABEL_405;
  }
  if ( v123 < 0 || v52 - 1 == v123 )
  {
LABEL_405:
    if ( !*(_DWORD *)(qword_102ECFB00 + 14504) && !IsBoxAADEnabled(0) )
      ex_raise(154, 7, 16, 1, v392);
    goto LABEL_418;
  }
  if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                         + SystemThread_TlsOffset)
                             + 72LL)
                 + 270LL)
      & 4) != 0 )
  {
LABEL_418:
    v257 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
    LOBYTE(v169) = 0;
    LookupFederatedPrincipal(
      v15,
      &Size,
      v392,
      2,
      &pguid,
      (_DWORD)v169,
      Destination,
      &DestinationSize,
      v181,
      v175,
      &v257);
    v70 = DestinationSize;
    v126 = v181[0];
    goto LABEL_419;
  }
  v188[0] = 85;
  v125 = FGetSidFromNt(v15, Size, Destination, v188, 85, 1);
  v126 = v125 != 0;
  if ( v125 )
    v127 = v175[0];
  else
    v127 = (unsigned int)FGetSidFromNt(v15, Size, Destination, v188, 71, 1) != 0;
  if ( !v126 && !v127 )
    ex_raise(154, 1, 16, 1, v392);
  v70 = v188[0];
LABEL_419:
  v54 = 2 - v126;
  if ( v191 )
  {
    ex_raise(332, 37, 16, 1, L"PASSWORD");
    v93 = v178;
LABEL_362:
    if ( v54 || *(_DWORD *)(v93 + 2432) != 6 )
      ex_raise(332, 34, 16, 1, L"PASSWORD");
  }
LABEL_365:
  v109 = 0;
  v110 = v178;
  v111 = *(_QWORD *)(v178 + 2320);
  if ( !v111 )
    goto LABEL_448;
  v112 = *(const wchar_t **)(v111 + 8);
  v113 = *(_DWORD *)(v111 + 20);
  v114 = *(_BYTE *)(v111 + 24);
  v115 = *(unsigned int *)(v111 + 16);
  if ( !(_DWORD)v115 && !v114 )
    goto LABEL_447;
  if ( (!v216 || (unsigned int)(v54 - 1) > 1 && *(_DWORD *)(v178 + 2432) != 6)
    && (!*(_DWORD *)(GetXdbServerGlobals(v86) + 11976) && !(unsigned int)IsVDWFrontendInstance() && !IsBoxAADEnabled(0)
     || (unsigned int)(v54 - 7) > 1) )
  {
    ex_raise(332, 34, 16, 1, L"DEFAULT_LANGUAGE");
  }
  if ( v114 )
  {
    LangInfoByLCID = GetLangInfoByLCID(v113);
    if ( !LangInfoByLCID )
    {
      LODWORD(v167) = v113;
      v117 = 2;
      v118 = 98;
LABEL_379:
      ex_raise(v118, v117, 16, 1, v167);
      v110 = v178;
      goto LABEL_448;
    }
LABEL_442:
    v130 = (const void *)*((_QWORD *)LangInfoByLCID + 1);
    if ( *((_BYTE *)LangInfoByLCID + 16) )
    {
      if ( v130 )
      {
        memmove(v393, v130, *((unsigned __int8 *)LangInfoByLCID + 16));
      }
      else
      {
        memset_0(v393, 0, 0x102u);
        *_errno() = 22;
        _invalid_parameter_noinfo();
      }
    }
    v109 = *((unsigned __int8 *)LangInfoByLCID + 16);
    goto LABEL_447;
  }
  if ( CompareStringWEnglishNoCase(1u, 0, v112, (unsigned __int64)(int)v115 >> 1, L"none", 4) != 2 )
  {
    LangInfoByLCID = GetLangInfoByName(v112, v115);
    if ( !LangInfoByLCID )
    {
      LangInfoByLCID = GetLangInfoByAlias(v112, v115);
      if ( !LangInfoByLCID )
      {
        v129 = GetDefaultLocale();
        StringCchPrintf_lW(v394, 0x81u, L"%.*s", v129, v115 >> 1, v112);
        v167 = v394;
        v117 = 33;
        v118 = 150;
        goto LABEL_379;
      }
    }
    goto LABEL_442;
  }
LABEL_447:
  v110 = v178;
LABEL_448:
  v131 = 0;
  v132 = v192;
  v133 = *(_QWORD *)v192;
  if ( v190 )
  {
    v134 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(v133 + 232))(v192, 2, 1);
    v135 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v134 + 72LL))(v134);
    v136 = (**v135)(v135);
    if ( (((unsigned int)GetUserDbAccessEPS(v197, v192, v136, 1) - 1) & 0xFFFFFFFD) == 0 )
      ex_raise(150, 23, 16, 4, v391);
  }
  else
  {
    LOBYTE(v167) = 1;
    if ( (*(__int64 (__fastcall **)(__int64, unsigned __int8 *, _QWORD, _QWORD, _DWORD))(v133 + 328))(
           v192,
           Destination,
           v70,
           0,
           (_DWORD)v167) )
    {
      ex_raise(150, 22, 16, 1);
    }
    else
    {
      LOBYTE(v168) = 1;
      LOBYTE(v137) = 1;
      v142 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(__int64, unsigned __int8 *, _QWORD, __int64, int))(*(_QWORD *)v132 + 240LL))(
                                                 v132,
                                                 Destination,
                                                 v70,
                                                 v137,
                                                 v168);
      v136 = (__int64)v142;
      if ( v142 )
      {
        v143 = (**v142)(v142);
        v135 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v136 + 72LL))(v136);
        v131 = 1;
        UserDbAccessEPS = GetUserDbAccessEPS(v197, v192, v136, 1);
        if ( !v54 || ((UserDbAccessEPS - 1) & 0xFFFFFFFD) == 0 )
        {
          if ( v143
            && CDefaultCollation::FEqW(
                 v207,
                 *(const wchar_t **)(v110 + 2208),
                 *(_DWORD *)(v110 + 2216),
                 *(const wchar_t **)v143,
                 *(_DWORD *)(v143 + 8)) )
          {
            ex_raise(150, 23, 16, 5, v391);
          }
          else
          {
            ex_raise(150, 63, 16, 1);
          }
        }
        goto LABEL_471;
      }
    }
    v138 = *(_DWORD *)(v110 + 2216);
    v139 = *(_QWORD *)(v110 + 2208);
    if ( byte_102EDCA55 )
    {
      v258 = Uuid;
      v246 = v139;
      v247 = v138;
      v140 = &v258;
      v141 = &v246;
    }
    else
    {
      v259 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
      v248 = v139;
      v249 = v138;
      v140 = &v259;
      v141 = &v248;
    }
    v136 = (*(__int64 (__fastcall **)(__int64, __int64 *, unsigned __int8 *, _QWORD, int, GUID *))(*(_QWORD *)v132
                                                                                                 + 248LL))(
             v132,
             v141,
             Destination,
             v70,
             v54,
             v140);
    if ( !v136 )
      ex_raise(150, 23, 16, 6, v391);
    if ( *(_DWORD *)(v110 + 2432) == 6 )
    {
      v145 = *(_QWORD *)(v110 + 2256);
      if ( !v145 || (v146 = *(const wchar_t **)(v145 + 8), !*(_DWORD *)(v145 + 16)) )
        v146 = &szPassword;
      CheckSetUserPwd(4, v136, v146);
    }
    v135 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v136 + 72LL))(v136);
  }
LABEL_471:
  v147 = (**v135)(v135);
  SetDbConnectPermission(v197, v147, 1);
  v148 = 0;
  v149 = *(_QWORD *)(v110 + 2224);
  if ( v149 )
  {
    v148 = *(_QWORD *)(v149 + 8);
    v150 = *(_DWORD *)(v149 + 16);
  }
  else
  {
    v150 = 0;
  }
  if ( (unsigned int)(v54 - 5) <= 1 )
  {
    if ( v150 )
      ex_raise(152, 59, 16, 1);
  }
  else if ( !v150 || v131 && (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v136 + 48LL))(v136) )
  {
    if ( v54 != 2 && v54 != 8 && (!v131 || !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v136 + 48LL))(v136)) )
    {
      v230 = L"dbo";
      v231 = 6;
      (*(void (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v136 + 456LL))(v136, &v230);
    }
  }
  else
  {
    v250 = v148;
    v251 = v150;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v136 + 456LL))(v136, &v250);
  }
  if ( v109 && ((unsigned int)(v54 - 1) <= 1 || (unsigned int)(v54 - 7) <= 1 || *(_DWORD *)(v110 + 2432) == 6) )
  {
    v232 = v393;
    v233 = v109;
    (*(void (__fastcall **)(__int64, _BYTE **))(*(_QWORD *)v136 + 520LL))(v136, &v232);
  }
  if ( v204 )
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v136 + 600LL))(v136, (unsigned __int8)v194);
  if ( *(_DWORD *)(qword_102ECFB00 + 14504) )
  {
    if ( byte_102EDCA50 )
    {
      if ( byte_102EF429C )
      {
        ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
        v152 = *(_QWORD *)(*(_QWORD *)(ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset) + 72LL);
        v153 = *(_QWORD *)(v152 + 96);
        if ( v153 )
        {
          LOBYTE(ThreadLocalStoragePointer) = 2;
          v154 = CPhysicalConnection::GetFeatureExtension(*(_QWORD *)(v152 + 96), ThreadLocalStoragePointer)
              && *(_DWORD *)(v153 + 988) != 2;
          if ( !v54 && (v191 || *(_DWORD *)(v110 + 2432) == 1 && Size) && v154 )
            ex_raise(374, 57, 16, 2);
        }
      }
    }
  }
  v155 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v136 + 8LL))(v136);
  v156 = Size_4;
  if ( !v210 )
  {
    v252 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
    ISECManager::CheckPermRuleAuditOnly(1380144472, v196, v197, Size_4, v155, v186, 21333, 0, 0, &v252, 0, 0, 0, -1);
    v210 = 1;
  }
  v157 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v197 + 16LL))(v197);
  v158 = ((__int64 (__fastcall *)(_QWORD))g_dbtableFactory[4])(v156);
  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v157 + 280LL))(v157, *(_QWORD *)(v158 + 4624));
  InvalidateSecurityCaches(v156, 0, v156);
  v159 = v222;
  if ( !*(_BYTE *)(v222 + 240)
    || (DestinationSize_4 = 1,
        v160 = *(_QWORD *)(v222 + 56),
        *(_QWORD *)(v222 + 56) = 0,
        PostOwnerMgmtEvent(34, *(_QWORD *)&SourceSize[1], v159, v223, v160, v192, v136, &DestinationSize_4, 0, 0, 0, 0),
        DestinationSize_4) )
  {
    if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)&SourceSize[1] + 72LL) + 270LL) & 4) != 0 && (qword_102F21DB4 & 1) != 0 )
    {
      v357 = 327680;
      v358 = 0;
      v359 = &v362;
      v360 = &v376;
      v377 = 0;
      v361 = 0;
      v378 = 0;
      v362 = &v379;
      v363 = 32;
      v364 = 4;
      v370 = 0;
      v371 = 0;
      v372 = 2;
      v373 = 0;
      v374 = 0;
      v375 = 3;
      v365 = L"CREATE";
      v366 = 12;
      v367 = L"FINISH";
      v368 = 12;
      v369 = 1;
      XeCloudPkg::azuresqldb_user_ddl::Publish((XeCloudPkg::azuresqldb_user_ddl *)v356);
    }
    *(_BYTE *)(v159 + 176) |= 0x10u;
    v205 = 0;
  }
  CAutoHandleCreateAudit::~CAutoHandleCreateAudit((CAutoHandleCreateAudit *)v209);
  return v205;
}

```

## disassembly

```asm
0x10145d200  push    rbp
0x10145d202  push    rbx
0x10145d203  push    rsi
0x10145d204  push    rdi
0x10145d205  push    r12
0x10145d207  push    r13
0x10145d209  push    r14
0x10145d20b  push    r15
0x10145d20d  lea     rbp, [rsp-2E78h]
0x10145d215  mov     eax, 2F78h
0x10145d21a  call    _alloca_probe
0x10145d21f  sub     rsp, rax
0x10145d222  mov     [rbp+2EB0h+var_2D10], 0FFFFFFFFFFFFFFFEh
0x10145d22d  movaps  [rsp+2FB0h+var_50], xmm6
0x10145d235  mov     rax, cs:__security_cookie
0x10145d23c  xor     rax, rsp
0x10145d23f  mov     [rbp+2EB0h+var_60], rax
0x10145d246  mov     r13, r9
0x10145d249  mov     [rbp+2EB0h+var_2E20], r9
0x10145d250  mov     rsi, r8
0x10145d253  mov     [rbp+2EB0h+var_2E28], r8
0x10145d25a  mov     rdi, rdx
0x10145d25d  mov     qword ptr [rbp+2EB0h+SourceSize+4], rdx
0x10145d261  mov     r15, rcx
0x10145d264  mov     [rbp+2EB0h+var_2F30], rcx
0x10145d268  mov     rax, [r9+78h]
0x10145d26c  mov     [rbp+2EB0h+var_2ED0], rax
0x10145d270  mov     r9, gs:58h
0x10145d279  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10145d280  mov     edx, [rax]
0x10145d282  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10145d289  mov     eax, [rax]
0x10145d28b  add     rax, [r9+rdx*8]
0x10145d28f  mov     rax, [rax]
0x10145d292  mov     rcx, [rax+50h]
0x10145d296  movzx   ebx, word ptr [rcx+8]
0x10145d29a  mov     dword ptr [rbp+2EB0h+Size+4], ebx
0x10145d29d  mov     r14, [r8+38h]
0x10145d2a1  mov     [rbp+2EB0h+var_2EC8], r14
0x10145d2a5  movups  xmm0, xmmword ptr cs:?sm_val@?$Zero@ULocaleEntry@?$XE_StaticPackage@$0L@@@@@2ULocaleEntry@?$XE_StaticPackage@$0L@@@B.Data1; XE_StaticPackage<11>::LocaleEntry const Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val ...
0x10145d2ac  movups  xmmword ptr [rbp+2EB0h+pguid.Data1], xmm0
0x10145d2b3  lea     rcx, [rbp+2EB0h+pguid]; pguid
0x10145d2ba  call    cs:__imp_CoCreateGuid
0x10145d2c0  mov     ecx, ebx
0x10145d2c2  call    cs:__imp_?FIsDwFidoDatabaseType@@YA_NK@Z; FIsDwFidoDatabaseType(ulong)
0x10145d2c8  xor     r12d, r12d
0x10145d2cb  test    al, al
0x10145d2cd  jz      loc_10145D386
0x10145d2d3  call    cs:__imp_GetXdbServerGlobals
0x10145d2d9  cmp     [rax+2EE4h], r12b
0x10145d2e0  jz      short loc_10145D351
0x10145d2e2  call    cs:__imp_GetXdbServerGlobals
0x10145d2e8  cmp     [rax+2EE9h], r12b
0x10145d2ef  jz      short loc_10145D351
0x10145d2f1  call    cs:__imp_?GetCurrentInstance@CFeatureSwitchesFido@@SAPEBV1@XZ; CFeatureSwitchesFido::GetCurrentInstance(void)
0x10145d2f7  cmp     [rax+4Dh], r12b
0x10145d2fb  jnz     short loc_10145D30D
0x10145d2fd  mov     rax, cs:qword_102ECFB10
0x10145d304  test    byte ptr [rax+5E8h], 10h
0x10145d30b  jz      short loc_10145D351
0x10145d30d  mov     eax, [r15+980h]
0x10145d314  cmp     eax, 7
0x10145d317  jnz     short loc_10145D328
0x10145d319  cmp     cs:byte_102EDCED4, r12b
0x10145d320  jnz     short loc_10145D351
0x10145d322  lea     r9d, [rax-5]
0x10145d326  jmp     short loc_10145D33C
0x10145d328  cmp     eax, 1
0x10145d32b  jz      short loc_10145D351
0x10145d32d  cmp     cs:byte_102EDCED4, r12b
0x10145d334  jnz     short loc_10145D351
0x10145d336  mov     r9d, 3
0x10145d33c  mov     r8d, 10h
0x10145d342  lea     edx, [r8+34h]
0x10145d346  mov     ecx, 14Bh
0x10145d34b  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10145d351  mov     byte ptr [rsp+2FB0h+var_2F88], r12b
0x10145d356  mov     word ptr [rsp+2FB0h+var_2F90], r12w
0x10145d35c  xor     r9d, r9d
0x10145d35f  mov     r8d, ebx
0x10145d362  mov     rdx, r13
0x10145d365  mov     rcx, r15
0x10145d368  call    ?XretDwFidoExecuteOnGLMS@CStatement@@QEBA?AW4EXRetType@@PEBVCMsqlExecContext@@KPEAVIFidoGLMController@@G_N@Z; CStatement::XretDwFidoExecuteOnGLMS(CMsqlExecContext const *,ulong,IFidoGLMController *,ushort,bool)
0x10145d36d  cmp     eax, 1Bh
0x10145d370  jz      short loc_10145D386
0x10145d372  test    eax, eax
0x10145d374  jnz     loc_10145FFC6
0x10145d37a  or      byte ptr [rsi+0B0h], 10h
0x10145d381  jmp     loc_10145FFC6
0x10145d386  mov     rax, [rdi+48h]
0x10145d38a  mov     ecx, 4
0x10145d38f  mov     [rbp+2EB0h+var_2E9C], ecx
0x10145d392  lea     r11, aCreate; "CREATE"
0x10145d399  test    [rax+10Eh], cl
0x10145d39f  jz      loc_10145D482
0x10145d3a5  test    byte ptr cs:qword_102F21DB4, 1
0x10145d3ac  jz      loc_10145D482
0x10145d3b2  mov     [rbp+2EB0h+var_2838], 50000h
0x10145d3bc  mov     [rbp+2EB0h+var_2830], r12d
0x10145d3c3  lea     rax, [rbp+2EB0h+var_2810]
0x10145d3ca  mov     [rbp+2EB0h+var_2828], rax
0x10145d3d1  lea     rax, [rbp+2EB0h+var_27C0]
0x10145d3d8  mov     [rbp+2EB0h+var_2820], rax
0x10145d3df  mov     [rbp+2EB0h+var_25F0], r12
0x10145d3e6  mov     [rbp+2EB0h+var_2818], r12
0x10145d3ed  mov     [rbp+2EB0h+var_25E8], r12
0x10145d3f4  lea     rax, [rbp+2EB0h+var_25E0]
0x10145d3fb  mov     [rbp+2EB0h+var_2810], rax
0x10145d402  mov     [rbp+2EB0h+var_2808], 20h ; ' '
0x10145d40c  mov     [rbp+2EB0h+var_2804], ecx
0x10145d412  mov     [rbp+2EB0h+var_27E0], r12
0x10145d419  mov     [rbp+2EB0h+var_27D8], r12d
0x10145d420  mov     [rbp+2EB0h+var_27D4], 2
0x10145d42a  mov     [rbp+2EB0h+var_27D0], r12
0x10145d431  mov     [rbp+2EB0h+var_27C8], r12d
0x10145d438  mov     [rbp+2EB0h+var_27C4], 3
0x10145d442  mov     [rbp+2EB0h+var_2800], r11
0x10145d449  mov     [rbp+2EB0h+var_27F8], 0Ch
0x10145d454  lea     rax, aStart_2; "START"
0x10145d45b  mov     [rbp+2EB0h+var_27F0], rax
0x10145d462  mov     [rbp+2EB0h+var_27E8], 0Ah
0x10145d46c  mov     [rbp+2EB0h+var_27E4], 1
0x10145d476  lea     rcx, [rbp+2EB0h+var_2840]; this
0x10145d47d  call    ?Publish@azuresqldb_user_ddl@XeCloudPkg@@QEAAXXZ; XeCloudPkg::azuresqldb_user_ddl::Publish(void)
0x10145d482  mov     rax, [r14]
0x10145d485  mov     dword ptr [rsp+2FB0h+var_2F88], r12d
0x10145d48a  mov     dword ptr [rsp+2FB0h+var_2F90], r12d
0x10145d48f  xor     r9d, r9d
0x10145d492  xor     r8d, r8d
0x10145d495  mov     edx, ebx
0x10145d497  mov     rcx, r14
0x10145d49a  call    qword ptr [rax+38h]
0x10145d49d  mov     [rbp+2EB0h+var_2EE8], rax
0x10145d4a1  mov     r13, r12
0x10145d4a4  mov     rcx, [r15+8C0h]
0x10145d4ab  test    rcx, rcx
0x10145d4ae  jz      short loc_10145D4B9
0x10145d4b0  mov     r13, [rcx+8]
0x10145d4b4  mov     edx, [rcx+10h]
0x10145d4b7  jmp     short loc_10145D4BC
0x10145d4b9  mov     edx, r12d
0x10145d4bc  mov     dword ptr [rbp+2EB0h+Size], edx
0x10145d4bf  mov     eax, 55h ; 'U'
0x10145d4c4  mov     dword ptr [rsp+2FB0h+DestinationSize], eax
0x10145d4c8  mov     [rbp+2EB0h+var_2E38], r12
0x10145d4cc  mov     rax, [r15+960h]
0x10145d4d3  mov     [rbp+2EB0h+var_2EB8], rax
0x10145d4d7  test    rax, rax
0x10145d4da  jz      short loc_10145D4EC
0x10145d4dc  mov     rcx, [rax+8]
0x10145d4e0  mov     [rbp+2EB0h+var_2E38], rcx
0x10145d4e4  mov     eax, [rax+10h]
0x10145d4e7  mov     [rbp+2EB0h+var_2EA4], eax
0x10145d4ea  jmp     short loc_10145D4F0
0x10145d4ec  mov     [rbp+2EB0h+var_2EA4], r12d
0x10145d4f0  movups  xmm0, xmmword ptr cs:?sm_val@?$Zero@ULocaleEntry@?$XE_StaticPackage@$0L@@@@@2ULocaleEntry@?$XE_StaticPackage@$0L@@@B.Data1; XE_StaticPackage<11>::LocaleEntry const Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val ...
0x10145d4f7  movaps  xmmword ptr [rbp+2EB0h+Uuid.Data1], xmm0
0x10145d4fe  mov     edi, [r15+980h]
0x10145d505  mov     [rbp+2EB0h+var_2EE0], edi
0x10145d508  cmp     edi, 1
0x10145d50b  jnz     loc_10145D696
0x10145d511  test    edx, edx
0x10145d513  jz      loc_10145D696
0x10145d519  movzx   esi, dil
0x10145d51d  mov     [rsp+2FB0h+var_2F3E], dil
0x10145d522  mov     [rsp+2FB0h+var_2F40], r12b
0x10145d527  mov     [rsp+2FB0h+var_2F3D], r12b
0x10145d52c  test    edx, edx
0x10145d52e  jz      short loc_10145D55A
0x10145d530  test    r13, r13
0x10145d533  jz      short loc_10145D55A
0x10145d535  mov     ecx, r12d
0x10145d538  mov     r8d, edx
0x10145d53b  shr     r8, 1
0x10145d53e  jz      short loc_10145D55A
0x10145d540  mov     rax, r12
0x10145d543  cmp     word ptr [r13+rax*2+0], 5Ch ; '\'
0x10145d54a  jz      loc_10145D6E0
0x10145d550  inc     ecx
0x10145d552  inc     rax
0x10145d555  cmp     rax, r8
0x10145d558  jl      short loc_10145D543
0x10145d55a  xor     bl, bl
0x10145d55c  lea     eax, [rdi-4]
0x10145d55f  test    eax, 0FFFFFFFDh
0x10145d564  setz    [rsp+2FB0h+var_2F3F]
0x10145d569  mov     eax, [r15+8A8h]
0x10145d570  mov     r8, [r15+8A0h]
0x10145d577  test    r8, r8
0x10145d57a  jz      short loc_10145D5A6
0x10145d57c  test    eax, eax
0x10145d57e  jz      short loc_10145D5A6
0x10145d580  mov     ecx, r12d
0x10145d583  mov     edx, eax
0x10145d585  shr     rdx, 1
0x10145d588  jz      short loc_10145D5A6
0x10145d58a  mov     rax, r12
0x10145d58d  nop     dword ptr [rax]
0x10145d590  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x10145d596  jz      loc_10145D6FB
0x10145d59c  inc     ecx
0x10145d59e  inc     rax
0x10145d5a1  cmp     rax, rdx
0x10145d5a4  jl      short loc_10145D590
0x10145d5a6  mov     [rbp+2EB0h+var_2F18], r12
0x10145d5aa  mov     rax, [r15+8D0h]
0x10145d5b1  mov     [rbp+2EB0h+var_2EF0], rax
0x10145d5b5  mov     r14, [r15+900h]
0x10145d5bc  mov     [rbp+2EB0h+var_2E88], r14
0x10145d5c0  test    r14, r14
0x10145d5c3  setnz   r12b
0x10145d5c7  mov     byte ptr [rsp+2FB0h+DestinationSize+4], r12b
0x10145d5cc  mov     [rsp+2FB0h+var_2F3C], 0
0x10145d5d1  call    cs:__imp_GetXdbServerGlobals
0x10145d5d7  cmp     dword ptr [rax+2EC8h], 0
0x10145d5de  jnz     short loc_10145D5E9
0x10145d5e0  call    ?IsVDWFrontendInstance@@YAHXZ; IsVDWFrontendInstance(void)
0x10145d5e5  test    eax, eax
0x10145d5e7  jz      short loc_10145D632
0x10145d5e9  mov     rax, qword ptr [rbp+2EB0h+SourceSize+4]
0x10145d5ed  mov     rax, [rax+48h]
0x10145d5f1  test    byte ptr [rax+10Eh], 2
0x10145d5f8  jnz     short loc_10145D632
0x10145d5fa  test    bl, bl
0x10145d5fc  jnz     short loc_10145D605
0x10145d5fe  cmp     [rbp+2EB0h+var_2F18], 0
0x10145d603  jz      short loc_10145D632
0x10145d605  lea     rax, aCreateUserFrom_0; "CREATE USER FROM WINDOWS"
0x10145d60c  mov     [rsp+2FB0h+var_2F88], rax
0x10145d611  mov     [rsp+2FB0h+var_2F90], 30h ; '0'
0x10145d61a  mov     edx, 6
0x10145d61f  mov     ecx, 1A3h
0x10145d624  lea     r9d, [rdx+0Ch]
0x10145d628  lea     r8d, [rdx+0Ah]
0x10145d62c  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10145d632  cmp     edi, 7
0x10145d635  jnz     short loc_10145D67D
0x10145d637  mov     rax, cs:qword_102ECFB00
0x10145d63e  cmp     dword ptr [rax+38A8h], 0
0x10145d645  jnz     short loc_10145D67D
0x10145d647  xor     ecx, ecx; bool
0x10145d649  call    ?IsBoxAADEnabled@@YA_N_N@Z; IsBoxAADEnabled(bool)
0x10145d64e  test    al, al
0x10145d650  jnz     short loc_10145D67D
0x10145d652  lea     rax, aCreateUserFrom; "CREATE USER FROM EXTERNAL PROVIDER"
0x10145d659  mov     [rsp+2FB0h+var_2F88], rax
0x10145d65e  mov     [rsp+2FB0h+var_2F90], 44h ; 'D'
0x10145d667  lea     edx, [rdi+12h]
0x10145d66a  mov     ecx, 177h
0x10145d66f  lea     r9d, [rdi-6]
0x10145d673  lea     r8d, [rdi+9]
0x10145d677  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10145d67d  xor     ecx, ecx
0x10145d67f  mov     edi, ecx
0x10145d681  mov     rax, [r15+968h]
0x10145d688  test    rax, rax
0x10145d68b  jz      short loc_10145D70B
0x10145d68d  mov     rdi, [rax+8]
0x10145d691  mov     ebx, [rax+10h]
0x10145d694  jmp     short loc_10145D70D
0x10145d696  xor     sil, sil
0x10145d699  mov     [rsp+2FB0h+var_2F3E], sil
0x10145d69e  cmp     edi, 2
0x10145d6a1  jnz     short loc_10145D6B1
0x10145d6a3  test    edx, edx
0x10145d6a5  jz      short loc_10145D6B1
0x10145d6a7  mov     [rsp+2FB0h+var_2F40], 1
0x10145d6ac  jmp     loc_10145D527
0x10145d6b1  mov     [rsp+2FB0h+var_2F40], sil
0x10145d6b6  mov     [rsp+2FB0h+var_2F3E], sil
0x10145d6bb  cmp     edi, 3
0x10145d6be  jnz     loc_10145D527
0x10145d6c4  mov     [rsp+2FB0h+var_2F3E], sil
0x10145d6c9  test    edx, edx
0x10145d6cb  jz      loc_10145D527
0x10145d6d1  mov     [rsp+2FB0h+var_2F3D], 1
0x10145d6d6  mov     [rsp+2FB0h+var_2F3E], sil
0x10145d6db  jmp     loc_10145D530
0x10145d6e0  movsxd  rax, ecx
0x10145d6e3  lea     rcx, ds:0[rax*2]
0x10145d6eb  add     rcx, r13
0x10145d6ee  jz      loc_10145D55A
0x10145d6f4  mov     bl, 1
0x10145d6f6  jmp     loc_10145D55C
0x10145d6fb  movsxd  rax, ecx
0x10145d6fe  lea     rax, [r8+rax*2]
0x10145d702  mov     [rbp+2EB0h+var_2F18], rax
0x10145d706  jmp     loc_10145D5AA
0x10145d70b  mov     ebx, ecx
0x10145d70d  mov     [rbp+2EB0h+var_2EA0], ebx
0x10145d710  mov     byte ptr [rbp+2EB0h+var_2EDC], cl
0x10145d713  mov     ecx, [r15+8A8h]
0x10145d71a  mov     rax, [r15+8A0h]
0x10145d721  mov     qword ptr [rbp+2EB0h+var_2E50], rax
0x10145d725  mov     dword ptr [rbp+2EB0h+var_2E50+8], ecx
0x10145d728  movaps  xmm0, [rbp+2EB0h+var_2E50]
0x10145d72c  movdqa  [rbp+2EB0h+var_2D00], xmm0
0x10145d734  mov     eax, dword ptr [rbp+2EB0h+Size+4]
0x10145d737  mov     word ptr [rsp+2FB0h+var_2F90], ax
0x10145d73c  mov     r9d, 333Ah
  ... truncated ...
```
