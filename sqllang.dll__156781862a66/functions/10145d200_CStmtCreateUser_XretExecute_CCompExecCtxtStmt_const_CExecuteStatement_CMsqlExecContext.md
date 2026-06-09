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
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // eax
  __int64 result; // rax
  __int64 v16; // rax
  wchar_t *v17; // r13
  unsigned __int64 v18; // rcx
  signed __int64 v19; // rdx
  __int64 v20; // rax
  int v21; // edi
  char v22; // si
  __int64 v23; // rax
  char v24; // bl
  unsigned int v25; // eax
  __int64 v26; // r8
  __int64 v27; // rax
  __int64 v28; // r14
  bool v29; // r12
  const wchar_t *v30; // rdi
  __int64 v31; // rax
  int v32; // ebx
  __int64 v33; // rcx
  unsigned __int64 v34; // rbx
  const void *v35; // rdi
  __int64 v36; // rcx
  int v37; // r8d
  int v38; // edx
  __int64 v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rdx
  __int64 v42; // rbx
  bool v43; // r15
  int v44; // eax
  int v45; // ebx
  int v46; // edi
  __int64 v47; // rcx
  __int64 v48; // rdi
  __int64 v49; // rax
  unsigned int v50; // ebx
  int v51; // edx
  __int64 v52; // rdi
  unsigned int v53; // r15d
  __int64 v54; // r14
  int v55; // esi
  struct __crt_locale_pointers *DefaultLocale; // rax
  unsigned __int64 v57; // rbx
  struct __crt_locale_pointers *v58; // rax
  unsigned __int16 v59; // dx
  CDefaultCollation *DefaultCollation; // rbx
  char v61; // cl
  char v62; // bl
  __int64 v63; // rax
  DBTABLE *v64; // rax
  DBTABLE *v65; // rbx
  unsigned int v66; // edi
  const wchar_t *v67; // rbx
  __int64 v68; // rcx
  CDefaultCollation *v69; // rax
  struct CGatewayServerPrincipal *ServerPrincipal; // rdi
  __int64 v71; // rbx
  unsigned int v72; // r14d
  __int64 v73; // r14
  int v74; // eax
  RPC_WSTR v75; // rbx
  __int64 v76; // rbx
  __int64 v77; // rax
  void *v78; // rbx
  int v79; // edi
  struct CGatewayServerPrincipal *v80; // rax
  BOOL LoginSidFromLogicalMaster; // ebx
  const wchar_t *v82; // rax
  unsigned int v83; // eax
  unsigned int v84; // r14d
  unsigned __int8 *v85; // rcx
  CDefaultCollation *v86; // rbx
  bool v87; // al
  signed __int64 v88; // rdx
  unsigned __int64 v89; // rcx
  unsigned int v90; // ebx
  _WORD *v91; // rdi
  const struct CSECCertParams::_SECCertParams near *const *v92; // rdx
  __int64 v93; // rbx
  __int64 v94; // rbx
  wchar_t *v95; // rdi
  __int64 v96; // r12
  __int64 v97; // rax
  int v98; // ecx
  __int64 v99; // rcx
  __int64 v100; // rax
  UUID v101; // xmm6
  wchar_t *v102; // rsi
  int v103; // ecx
  __int64 v104; // rax
  bool v105; // bl
  unsigned int *p_Size; // rdx
  bool v107; // r8
  __int64 v108; // r9
  __int64 v109; // rax
  __int64 v110; // rbx
  int v111; // ebx
  int v112; // r13d
  __int64 v113; // r12
  __int64 v114; // rax
  const wchar_t *v115; // r15
  unsigned int v116; // r12d
  char v117; // bl
  unsigned __int64 v118; // rdi
  struct CLangInfo *LangInfoByLCID; // rbx
  int v120; // edx
  int v121; // ecx
  unsigned int v122; // edi
  __int64 v123; // rax
  unsigned int *v124; // rbx
  int v125; // ecx
  __int64 v126; // rax
  int v127; // eax
  bool v128; // bl
  bool v129; // al
  __int16 v130; // ax
  struct __crt_locale_pointers *v131; // rax
  const void *v132; // rdx
  char v133; // r15
  __int64 v134; // rbx
  __int64 v135; // rax
  __int64 v136; // rax
  __int64 (__fastcall ***v137)(_QWORD); // rbx
  __int64 v138; // rdi
  __int64 v139; // r9
  int v140; // ecx
  __int64 v141; // rax
  GUID *v142; // rcx
  __int64 *v143; // rdx
  __int64 (__fastcall ***v144)(_QWORD); // rax
  __int64 v145; // r14
  int UserDbAccessEPS; // eax
  __int64 v147; // rax
  const wchar_t *v148; // r8
  __int64 v149; // rax
  __int64 v150; // r14
  __int64 v151; // rax
  int v152; // ebx
  _QWORD *ThreadLocalStoragePointer; // rdx
  __int64 v154; // rcx
  __int64 v155; // rbx
  bool v156; // al
  int v157; // eax
  unsigned int v158; // esi
  __int64 v159; // rbx
  __int64 v160; // rax
  __int64 v161; // rbx
  __int64 v162; // rax
  SQLLEN v163; // [rsp+20h] [rbp-E0h]
  unsigned int v164; // [rsp+20h] [rbp-E0h]
  int v165; // [rsp+20h] [rbp-E0h]
  int v166; // [rsp+20h] [rbp-E0h]
  SQLLEN v167; // [rsp+20h] [rbp-E0h]
  int v168; // [rsp+20h] [rbp-E0h]
  wchar_t *v169; // [rsp+20h] [rbp-E0h]
  int v170; // [rsp+20h] [rbp-E0h]
  wchar_t *v171; // [rsp+28h] [rbp-D8h]
  unsigned int *v172; // [rsp+30h] [rbp-D0h]
  char v173; // [rsp+70h] [rbp-90h]
  bool v174; // [rsp+71h] [rbp-8Fh]
  char v175; // [rsp+72h] [rbp-8Eh] BYREF
  char v176; // [rsp+73h] [rbp-8Dh]
  char v177[4]; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int DestinationSize; // [rsp+78h] [rbp-88h] BYREF
  bool DestinationSize_4; // [rsp+7Ch] [rbp-84h] BYREF
  __int64 v180; // [rsp+80h] [rbp-80h]
  unsigned int Size; // [rsp+88h] [rbp-78h] BYREF
  unsigned int Size_4; // [rsp+8Ch] [rbp-74h]
  bool v183[8]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v184; // [rsp+98h] [rbp-68h]
  bool v185; // [rsp+A0h] [rbp-60h] BYREF
  bool v186; // [rsp+A1h] [rbp-5Fh] BYREF
  char v187; // [rsp+A2h] [rbp-5Eh] BYREF
  unsigned __int8 v188; // [rsp+A3h] [rbp-5Dh]
  unsigned int SourceSize[3]; // [rsp+A4h] [rbp-5Ch] BYREF
  unsigned __int16 v190[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int16 v191; // [rsp+B4h] [rbp-4Ch]
  unsigned int v192; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v193; // [rsp+C0h] [rbp-40h]
  __int64 v194; // [rsp+C8h] [rbp-38h]
  int v195; // [rsp+D0h] [rbp-30h]
  int v196; // [rsp+D4h] [rbp-2Ch]
  struct CGatewayServerPrincipal *v197; // [rsp+D8h] [rbp-28h]
  struct IMemObj *v198; // [rsp+E0h] [rbp-20h]
  __int64 v199; // [rsp+E8h] [rbp-18h]
  int v200; // [rsp+F0h] [rbp-10h]
  __int64 v201; // [rsp+F8h] [rbp-8h]
  int v202; // [rsp+100h] [rbp+0h] BYREF
  int v203; // [rsp+104h] [rbp+4h] BYREF
  int v204; // [rsp+108h] [rbp+8h] BYREF
  int v205; // [rsp+10Ch] [rbp+Ch]
  int v206; // [rsp+110h] [rbp+10h]
  unsigned int v207; // [rsp+114h] [rbp+14h]
  void *Source; // [rsp+118h] [rbp+18h] BYREF
  CDefaultCollation *v209; // [rsp+120h] [rbp+20h]
  __int64 v210; // [rsp+128h] [rbp+28h] BYREF
  _DWORD v211[2]; // [rsp+130h] [rbp+30h] BYREF
  char v212; // [rsp+138h] [rbp+38h]
  unsigned __int8 v213; // [rsp+139h] [rbp+39h]
  char v214; // [rsp+13Ah] [rbp+3Ah]
  int v215; // [rsp+13Ch] [rbp+3Ch]
  __int64 v216; // [rsp+140h] [rbp+40h]
  int v217; // [rsp+148h] [rbp+48h] BYREF
  int v218; // [rsp+14Ch] [rbp+4Ch]
  RPC_WSTR StringUuid[2]; // [rsp+150h] [rbp+50h] BYREF
  __int128 v220; // [rsp+160h] [rbp+60h] BYREF
  RPC_WSTR v221; // [rsp+170h] [rbp+70h] BYREF
  __int16 *v222; // [rsp+178h] [rbp+78h]
  unsigned int *v223; // [rsp+180h] [rbp+80h]
  __int64 v224; // [rsp+188h] [rbp+88h]
  __int64 v225; // [rsp+190h] [rbp+90h]
  void *v226[2]; // [rsp+198h] [rbp+98h] BYREF
  HCERTSTORE hCertStore[2]; // [rsp+1A8h] [rbp+A8h] BYREF
  int v228; // [rsp+1B8h] [rbp+B8h]
  __int64 v229; // [rsp+1C0h] [rbp+C0h]
  PCCERT_CONTEXT pCertContext; // [rsp+1C8h] [rbp+C8h]
  char v231; // [rsp+1D0h] [rbp+D0h]
  const wchar_t *v232; // [rsp+1D8h] [rbp+D8h] BYREF
  int v233; // [rsp+1E0h] [rbp+E0h]
  _BYTE *v234; // [rsp+1E8h] [rbp+E8h] BYREF
  int v235; // [rsp+1F0h] [rbp+F0h]
  wchar_t *v236; // [rsp+1F8h] [rbp+F8h] BYREF
  unsigned int v237; // [rsp+200h] [rbp+100h]
  wchar_t *v238; // [rsp+208h] [rbp+108h] BYREF
  unsigned int v239; // [rsp+210h] [rbp+110h]
  wchar_t *v240; // [rsp+218h] [rbp+118h] BYREF
  unsigned int v241; // [rsp+220h] [rbp+120h]
  wchar_t *v242; // [rsp+228h] [rbp+128h] BYREF
  unsigned int v243; // [rsp+230h] [rbp+130h]
  wchar_t *v244; // [rsp+238h] [rbp+138h] BYREF
  unsigned int v245; // [rsp+240h] [rbp+140h]
  wchar_t *v246; // [rsp+248h] [rbp+148h] BYREF
  unsigned int v247; // [rsp+250h] [rbp+150h]
  __int64 v248; // [rsp+258h] [rbp+158h] BYREF
  int v249; // [rsp+260h] [rbp+160h]
  __int64 v250; // [rsp+268h] [rbp+168h] BYREF
  int v251; // [rsp+270h] [rbp+170h]
  __int64 v252; // [rsp+278h] [rbp+178h] BYREF
  int v253; // [rsp+280h] [rbp+180h]
  GUID v254; // [rsp+290h] [rbp+190h] BYREF
  __int64 v255; // [rsp+2A0h] [rbp+1A0h]
  __int128 v256; // [rsp+2B0h] [rbp+1B0h] BYREF
  GUID v257; // [rsp+2C0h] [rbp+1C0h] BYREF
  UUID v258; // [rsp+2D0h] [rbp+1D0h] BYREF
  GUID v259; // [rsp+2E0h] [rbp+1E0h] BYREF
  UUID v260; // [rsp+2F0h] [rbp+1F0h] BYREF
  GUID v261; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v262[24]; // [rsp+310h] [rbp+210h] BYREF
  __int64 v263; // [rsp+328h] [rbp+228h]
  _BYTE v264[24]; // [rsp+338h] [rbp+238h] BYREF
  __int64 v265; // [rsp+350h] [rbp+250h]
  _DWORD v266[6]; // [rsp+360h] [rbp+260h] BYREF
  void *v267; // [rsp+378h] [rbp+278h]
  _BYTE v268[24]; // [rsp+388h] [rbp+288h] BYREF
  __int64 v269; // [rsp+3A0h] [rbp+2A0h]
  _DWORD v270[6]; // [rsp+3B0h] [rbp+2B0h] BYREF
  void *v271; // [rsp+3C8h] [rbp+2C8h]
  _BYTE v272[24]; // [rsp+3D8h] [rbp+2D8h] BYREF
  __int64 v273; // [rsp+3F0h] [rbp+2F0h]
  _DWORD v274[6]; // [rsp+400h] [rbp+300h] BYREF
  void *v275; // [rsp+418h] [rbp+318h]
  _BYTE v276[24]; // [rsp+428h] [rbp+328h] BYREF
  __int64 v277; // [rsp+440h] [rbp+340h]
  _DWORD v278[6]; // [rsp+450h] [rbp+350h] BYREF
  void *v279; // [rsp+468h] [rbp+368h]
  _BYTE v280[24]; // [rsp+478h] [rbp+378h] BYREF
  __int64 v281; // [rsp+490h] [rbp+390h]
  _DWORD v282[6]; // [rsp+4A0h] [rbp+3A0h] BYREF
  void *v283; // [rsp+4B8h] [rbp+3B8h]
  _DWORD v284[6]; // [rsp+4C8h] [rbp+3C8h] BYREF
  void *v285; // [rsp+4E0h] [rbp+3E0h]
  char v286[8]; // [rsp+4F0h] [rbp+3F0h] BYREF
  int v287; // [rsp+4F8h] [rbp+3F8h]
  int v288; // [rsp+500h] [rbp+400h]
  char **v289; // [rsp+508h] [rbp+408h]
  char *v290; // [rsp+510h] [rbp+410h]
  __int64 v291; // [rsp+518h] [rbp+418h]
  char *v292; // [rsp+520h] [rbp+420h] BYREF
  int v293; // [rsp+528h] [rbp+428h]
  int v294; // [rsp+52Ch] [rbp+42Ch]
  const wchar_t *v295; // [rsp+530h] [rbp+430h]
  __int64 v296; // [rsp+538h] [rbp+438h]
  const wchar_t *v297; // [rsp+540h] [rbp+440h]
  int v298; // [rsp+548h] [rbp+448h]
  int v299; // [rsp+54Ch] [rbp+44Ch]
  __int64 v300; // [rsp+550h] [rbp+450h]
  int v301; // [rsp+558h] [rbp+458h]
  int v302; // [rsp+55Ch] [rbp+45Ch]
  __int64 v303; // [rsp+560h] [rbp+460h]
  int v304; // [rsp+568h] [rbp+468h]
  int v305; // [rsp+56Ch] [rbp+46Ch]
  char v306; // [rsp+570h] [rbp+470h] BYREF
  __int64 v307; // [rsp+740h] [rbp+640h]
  __int64 v308; // [rsp+748h] [rbp+648h]
  char v309; // [rsp+750h] [rbp+650h] BYREF
  char v310[8]; // [rsp+770h] [rbp+670h] BYREF
  int v311; // [rsp+778h] [rbp+678h]
  int v312; // [rsp+780h] [rbp+680h]
  char **v313; // [rsp+788h] [rbp+688h]
  char *v314; // [rsp+790h] [rbp+690h]
  __int64 v315; // [rsp+798h] [rbp+698h]
  char *v316; // [rsp+7A0h] [rbp+6A0h] BYREF
  int v317; // [rsp+7A8h] [rbp+6A8h]
  int v318; // [rsp+7ACh] [rbp+6ACh]
  const wchar_t *v319; // [rsp+7B0h] [rbp+6B0h]
  __int64 v320; // [rsp+7B8h] [rbp+6B8h]
  const wchar_t *v321; // [rsp+7C0h] [rbp+6C0h]
  int v322; // [rsp+7C8h] [rbp+6C8h]
  int v323; // [rsp+7CCh] [rbp+6CCh]
  __int64 v324; // [rsp+7D0h] [rbp+6D0h]
  int v325; // [rsp+7D8h] [rbp+6D8h]
  int v326; // [rsp+7DCh] [rbp+6DCh]
  __int64 v327; // [rsp+7E0h] [rbp+6E0h]
  int v328; // [rsp+7E8h] [rbp+6E8h]
  int v329; // [rsp+7ECh] [rbp+6ECh]
  char v330; // [rsp+7F0h] [rbp+6F0h] BYREF
  __int64 v331; // [rsp+9C0h] [rbp+8C0h]
  __int64 v332; // [rsp+9C8h] [rbp+8C8h]
  char v333; // [rsp+9D0h] [rbp+8D0h] BYREF
  char v334[8]; // [rsp+9F0h] [rbp+8F0h] BYREF
  int v335; // [rsp+9F8h] [rbp+8F8h]
  int v336; // [rsp+A00h] [rbp+900h]
  char **v337; // [rsp+A08h] [rbp+908h]
  char *v338; // [rsp+A10h] [rbp+910h]
  __int64 v339; // [rsp+A18h] [rbp+918h]
  char *v340; // [rsp+A20h] [rbp+920h] BYREF
  int v341; // [rsp+A28h] [rbp+928h]
  int v342; // [rsp+A2Ch] [rbp+92Ch]
  const wchar_t *v343; // [rsp+A30h] [rbp+930h]
  __int64 v344; // [rsp+A38h] [rbp+938h]
  const wchar_t *v345; // [rsp+A40h] [rbp+940h]
  int v346; // [rsp+A48h] [rbp+948h]
  int v347; // [rsp+A4Ch] [rbp+94Ch]
  __int64 v348; // [rsp+A50h] [rbp+950h]
  int v349; // [rsp+A58h] [rbp+958h]
  int v350; // [rsp+A5Ch] [rbp+95Ch]
  __int64 v351; // [rsp+A60h] [rbp+960h]
  int v352; // [rsp+A68h] [rbp+968h]
  int v353; // [rsp+A6Ch] [rbp+96Ch]
  char v354; // [rsp+A70h] [rbp+970h] BYREF
  __int64 v355; // [rsp+C40h] [rbp+B40h]
  __int64 v356; // [rsp+C48h] [rbp+B48h]
  char v357; // [rsp+C50h] [rbp+B50h] BYREF
  char v358[8]; // [rsp+C70h] [rbp+B70h] BYREF
  int v359; // [rsp+C78h] [rbp+B78h]
  int v360; // [rsp+C80h] [rbp+B80h]
  char **v361; // [rsp+C88h] [rbp+B88h]
  char *v362; // [rsp+C90h] [rbp+B90h]
  __int64 v363; // [rsp+C98h] [rbp+B98h]
  char *v364; // [rsp+CA0h] [rbp+BA0h] BYREF
  int v365; // [rsp+CA8h] [rbp+BA8h]
  int v366; // [rsp+CACh] [rbp+BACh]
  const wchar_t *v367; // [rsp+CB0h] [rbp+BB0h]
  __int64 v368; // [rsp+CB8h] [rbp+BB8h]
  const wchar_t *v369; // [rsp+CC0h] [rbp+BC0h]
  int v370; // [rsp+CC8h] [rbp+BC8h]
  int v371; // [rsp+CCCh] [rbp+BCCh]
  __int64 v372; // [rsp+CD0h] [rbp+BD0h]
  int v373; // [rsp+CD8h] [rbp+BD8h]
  int v374; // [rsp+CDCh] [rbp+BDCh]
  __int64 v375; // [rsp+CE0h] [rbp+BE0h]
  int v376; // [rsp+CE8h] [rbp+BE8h]
  int v377; // [rsp+CECh] [rbp+BECh]
  char v378; // [rsp+CF0h] [rbp+BF0h] BYREF
  __int64 v379; // [rsp+EC0h] [rbp+DC0h]
  __int64 v380; // [rsp+EC8h] [rbp+DC8h]
  char v381; // [rsp+ED0h] [rbp+DD0h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+EF0h] [rbp+DF0h] BYREF
  UUID Uuid; // [rsp+F00h] [rbp+E00h] BYREF
  __int128 v384; // [rsp+F10h] [rbp+E10h] BYREF
  __int64 v385; // [rsp+F20h] [rbp+E20h]
  GUID pguid; // [rsp+F28h] [rbp+E28h] BYREF
  GUID v387; // [rsp+F38h] [rbp+E38h] BYREF
  char v388[24]; // [rsp+F48h] [rbp+E48h] BYREF
  _BYTE v389[6992]; // [rsp+F60h] [rbp+E60h] BYREF
  unsigned __int8 Destination[8]; // [rsp+2AB0h] [rbp+29B0h] BYREF
  int v391; // [rsp+2AB8h] [rbp+29B8h]
  char v392[84]; // [rsp+2ABCh] [rbp+29BCh] BYREF
  wchar_t v393[136]; // [rsp+2B10h] [rbp+2A10h] BYREF
  wchar_t v394[136]; // [rsp+2C20h] [rbp+2B20h] BYREF
  _BYTE v395[272]; // [rsp+2D30h] [rbp+2C30h] BYREF
  wchar_t v396[136]; // [rsp+2E40h] [rbp+2D40h] BYREF

  v255 = -2;
  v225 = a4;
  v224 = a3;
  *(_QWORD *)&SourceSize[1] = a2;
  v180 = a1;
  v198 = *(struct IMemObj **)(a4 + 120);
  v8 = *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                     + SystemThread_TlsIndex)
                                                   + SystemThread_TlsOffset)
                                       + 80LL)
                           + 8LL);
  Size_4 = v8;
  v9 = *(_QWORD *)(a3 + 56);
  v199 = v9;
  pguid = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
  CoCreateGuid(&pguid);
  if ( FIsDwFidoDatabaseType(v8) )
  {
    if ( *(_BYTE *)(GetXdbServerGlobals(v11, v10) + 12004)
      && *(_BYTE *)(GetXdbServerGlobals(v13, v12) + 12009)
      && (*(_BYTE *)(CFeatureSwitchesFido::GetCurrentInstance() + 77) || (*((_BYTE *)qword_102ECFB10 + 1512) & 0x10) != 0) )
    {
      v14 = *(_DWORD *)(a1 + 2432);
      if ( v14 == 7 )
      {
        if ( !byte_102EDCED4 )
          ex_raise(331, 68, 16, 2);
      }
      else if ( v14 != 1 && !byte_102EDCED4 )
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
  v16 = *(_QWORD *)(a2 + 72);
  v207 = 4;
  if ( (*(_BYTE *)(v16 + 270) & 4) != 0 && (qword_102F21DB4 & 1) != 0 )
  {
    v311 = 327680;
    v312 = 0;
    v313 = &v316;
    v314 = &v330;
    v331 = 0;
    v315 = 0;
    v332 = 0;
    v316 = &v333;
    v317 = 32;
    v318 = 4;
    v324 = 0;
    v325 = 0;
    v326 = 2;
    v327 = 0;
    v328 = 0;
    v329 = 3;
    v319 = L"CREATE";
    v320 = 12;
    v321 = L"START";
    v322 = 10;
    v323 = 1;
    XeCloudPkg::azuresqldb_user_ddl::Publish((XeCloudPkg::azuresqldb_user_ddl *)v310);
  }
  v194 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(*(_QWORD *)v9 + 56LL))(
           v9,
           v8,
           0,
           0,
           0,
           0);
  v17 = 0;
  v18 = *(_QWORD *)(a1 + 2240);
  if ( v18 )
  {
    v17 = *(wchar_t **)(v18 + 8);
    v19 = *(unsigned int *)(v18 + 16);
  }
  else
  {
    v19 = 0;
  }
  Size = v19;
  DestinationSize = 85;
  v222 = 0;
  v20 = *(_QWORD *)(a1 + 2400);
  v201 = v20;
  if ( v20 )
  {
    v18 = *(_QWORD *)(v20 + 8);
    v222 = (__int16 *)v18;
    v205 = *(_DWORD *)(v20 + 16);
  }
  else
  {
    v205 = 0;
  }
  Uuid = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
  v21 = *(_DWORD *)(a1 + 2432);
  v195 = v21;
  if ( v21 == 1 && (_DWORD)v19 )
  {
    v22 = 1;
    v175 = 1;
    v173 = 0;
    goto LABEL_27;
  }
  v22 = 0;
  v175 = 0;
  if ( v21 == 2 && (_DWORD)v19 )
  {
    v173 = 1;
    goto LABEL_27;
  }
  v173 = 0;
  v175 = 0;
  if ( v21 != 3 || (v175 = 0, !(_DWORD)v19) )
  {
LABEL_27:
    v176 = 0;
    if ( !(_DWORD)v19 )
      goto LABEL_33;
    goto LABEL_28;
  }
  v176 = 1;
  v175 = 0;
LABEL_28:
  if ( v17 )
  {
    v18 = 0;
    if ( (unsigned __int64)(unsigned int)v19 >> 1 )
    {
      v23 = 0;
      while ( v17[v23] != 92 )
      {
        v18 = (unsigned int)(v18 + 1);
        if ( ++v23 >= (__int64)((unsigned __int64)(unsigned int)v19 >> 1) )
          goto LABEL_33;
      }
      v18 = (unsigned __int64)&v17[(int)v18];
      if ( v18 )
      {
        v24 = 1;
        goto LABEL_34;
      }
    }
  }
LABEL_33:
  v24 = 0;
LABEL_34:
  v174 = ((v21 - 4) & 0xFFFFFFFD) == 0;
  v25 = *(_DWORD *)(a1 + 2216);
  v26 = *(_QWORD *)(a1 + 2208);
  if ( v26 && v25 && (v18 = 0, (v19 = (unsigned __int64)v25 >> 1) != 0) )
  {
    v27 = 0;
    while ( *(_WORD *)(v26 + 2 * v27) != 92 )
    {
      v18 = (unsigned int)(v18 + 1);
      if ( ++v27 >= v19 )
        goto LABEL_40;
    }
    v184 = v26 + 2LL * (int)v18;
  }
  else
  {
LABEL_40:
    v184 = 0;
  }
  v193 = *(_QWORD *)(a1 + 2256);
  v28 = *(_QWORD *)(a1 + 2304);
  v210 = v28;
  v29 = v28 != 0;
  DestinationSize_4 = v28 != 0;
  v177[0] = 0;
  if ( (*(_DWORD *)(GetXdbServerGlobals(v18, v19) + 11976) || (unsigned int)IsVDWFrontendInstance())
    && (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)&SourceSize[1] + 72LL) + 270LL) & 2) == 0
    && (v24 || v184) )
  {
    ex_raise(419, 6, 16, 18, 48, L"CREATE USER FROM WINDOWS");
  }
  if ( v21 == 7 && !*(_DWORD *)(qword_102ECFB00 + 14504) && !IsBoxAADEnabled(0) )
    ex_raise(375, 25, 16, 1, 68, L"CREATE USER FROM EXTERNAL PROVIDER");
  v30 = 0;
  v31 = *(_QWORD *)(a1 + 2408);
  if ( v31 )
  {
    v30 = *(const wchar_t **)(v31 + 8);
    v32 = *(_DWORD *)(v31 + 16);
  }
  else
  {
    v32 = 0;
  }
  v206 = v32;
  LOBYTE(v196) = 0;
  v33 = *(unsigned int *)(a1 + 2216);
  *(_QWORD *)&v220 = *(_QWORD *)(a1 + 2208);
  DWORD2(v220) = v33;
  v256 = v220;
  LOWORD(v163) = Size_4;
  CStmtOwnerMgmt::ErrorOutIfCloudLifterUnchangeablePrincipal(v33, &v256, 13105);
  if ( !v32 )
    goto LABEL_66;
  v34 = (unsigned __int64)v32 >> 1;
  if ( CompareStringWEnglishNoCase(1u, 0, v30, v34, L"ON", 3) == 2 )
  {
    LOBYTE(v196) = 1;
LABEL_66:
    v35 = 0;
    goto LABEL_67;
  }
  v44 = CompareStringWEnglishNoCase(1u, 0, v30, v34, L"OFF", 4);
  v45 = (unsigned __int8)v196;
  v35 = 0;
  if ( v44 == 2 )
    v45 = 0;
  v196 = v45;
LABEL_67:
  v36 = v201;
  if ( v201 )
  {
    v37 = 0;
    v38 = 0;
    if ( OptSecDDLDBPrincipalOptions )
    {
      v39 = 0;
      v40 = 0;
      while ( *(_DWORD *)((char *)&OptSecDDLDBPrincipalOptions + v40 + 12) != 22 )
      {
        ++v38;
        ++v39;
        v40 = 24 * v39;
        if ( !*((_QWORD *)&OptSecDDLDBPrincipalOptions + 3 * v39) )
          goto LABEL_72;
      }
      v37 = *((_DWORD *)&OptSecDDLDBPrincipalOptions + 6 * v38 + 2);
      v41 = *((_QWORD *)&OptSecDDLDBPrincipalOptions + 3 * v38);
    }
    else
    {
LABEL_72:
      v41 = 0;
    }
    if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)&SourceSize[1] + 72LL) + 270LL) & 4) == 0 )
    {
      LODWORD(v163) = v37;
      ex_raise(1, 2, 16, 30, v163, v41);
    }
    if ( v22 || v176 || v173 || v195 == 7 || v193 || v174 )
      ex_raise(331, 68, 16, 1, v163);
    v42 = v184;
    if ( v184 )
      ex_raise(331, 69, 16, 1);
    if ( !v28 )
    {
      ex_raise(331, 62, 16, 2);
      v43 = v174;
      goto LABEL_93;
    }
    v36 = v201;
LABEL_103:
    v49 = *(_QWORD *)(a1 + 2304);
    if ( v49 )
    {
      v35 = *(const void **)(v49 + 8);
      v50 = *(_DWORD *)(v49 + 16);
    }
    else
    {
      v50 = 0;
    }
    if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)&SourceSize[1] + 72LL) + 270LL) & 4) == 0 )
    {
      if ( v184 )
        ex_raise(332, 37, 16, 1, L"SID");
      if ( v50 > 0x55 )
        ex_raise(154, 19, 16, 1);
      memcpy_s(Destination, 0x55u, v35, v50);
      DestinationSize = v50;
      v43 = v174;
      if ( !v174 )
        ex_raise(332, 42, 16, 1);
      if ( v50 != 28 )
        ex_raise(330, 60, 16, 1);
      if ( !FIsOrphanedUserSid(Destination, v50) )
        ex_raise(330, 60, 16, 1);
      goto LABEL_92;
    }
    v43 = v174;
    if ( v195 == 7 || v22 || v174 || v176 || v173 || v193 )
    {
      v51 = 70;
    }
    else
    {
      if ( v36 )
      {
LABEL_127:
        if ( v50 != 16 )
          ex_raise(154, 19, 16, 1);
        memcpy_s(Destination, 0x55u, v35, v50);
        DestinationSize = v50;
        if ( v174
          || !v201 && !(unsigned int)FIsGatewaySID(Destination, v50)
          || (unsigned int)FIsGatewaySID(Destination, v50) && Destination[6] == 1
          || (unsigned int)FIsGatewaySID(Destination, v50) && Destination[5] == 1 )
        {
          ex_raise(405, 6, 16, 1, v163);
        }
        goto LABEL_92;
      }
      v51 = 62;
    }
    ex_raise(331, v51, 16, 1, v163);
    goto LABEL_127;
  }
  if ( v28 )
    goto LABEL_103;
  v43 = v174;
LABEL_92:
  v42 = v184;
LABEL_93:
  v46 = *(_DWORD *)(g_dbtableFactory[4](Size_4) + 3888);
  v218 = v46;
  v47 = v193;
  if ( v193 )
  {
    if ( FSystemDBId(Size_4) || v46 != 1 && (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)&SourceSize[1] + 72LL) + 270LL) & 4) == 0 )
      ex_raise(332, 33, 16, 1, v163);
    v48 = *(_QWORD *)&SourceSize[1];
    if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)&SourceSize[1] + 72LL) + 270LL) & 4) != 0 && !byte_102EDCB78 )
      ex_raise(406, 99, 16, 1);
    v47 = v193;
  }
  else
  {
    v48 = *(_QWORD *)&SourceSize[1];
  }
  if ( v22 || v173 || v176 )
  {
    if ( !v43 )
    {
LABEL_149:
      v53 = Size;
      goto LABEL_150;
    }
  }
  else if ( !v43 )
  {
    if ( !v28 )
    {
LABEL_143:
      v52 = v180;
      v17 = *(wchar_t **)(v180 + 2208);
      v53 = *(_DWORD *)(v180 + 2216);
      Size = v53;
      goto LABEL_151;
    }
    goto LABEL_149;
  }
  if ( v42 || (*(_BYTE *)(*(_QWORD *)(v48 + 72) + 270LL) & 4) != 0 && v47 )
    goto LABEL_143;
  v17 = L"public";
  v53 = 12;
  Size = 12;
LABEL_150:
  v52 = v180;
LABEL_151:
  v54 = -1;
  v211[1] = Size_4;
  v212 = 0;
  v216 = 0;
  v188 = ISECManager::CheckPermRule(1380144472, v198, v199, Size_4, Size_4, 0, -1, 21333, 1, 1, 0, 0);
  v213 = v188;
  v211[0] = 1380144472;
  v215 = 21333;
  v214 = 1;
  if ( v188 )
  {
    v55 = 0;
  }
  else
  {
    v257 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
    ISECManager::CheckPermRuleAuditOnly(1380144472, 0, v199, Size_4, 0, 0, 21333, 0, 0, &v257, 0, 0, 0, -1);
    v212 = 1;
    v55 = 0;
    AuditSecurityEvent(109, 3, 0, v17, v53, *(wchar_t **)(v52 + 2208), *(_DWORD *)(v52 + 2216), 0, 0);
    ex_raise(152, 47, 16, 1);
  }
  AuditSecurityEvent(109, 3, 1, v17, v53, *(wchar_t **)(v52 + 2208), *(_DWORD *)(v52 + 2216), 0, 0);
  DefaultLocale = GetDefaultLocale();
  StringCchPrintf_lW(v394, 0x81u, L"%.*s", DefaultLocale, (unsigned __int64)v53 >> 1, v17);
  v57 = (unsigned __int64)*(unsigned int *)(v52 + 2216) >> 1;
  v58 = GetDefaultLocale();
  *(_DWORD *)v190 = StringCchPrintf_lW(v393, 0x81u, L"%.*s", v58, v57, *(_QWORD *)(v52 + 2208));
  DefaultCollation = CDbAndSetOptsImplImport::GetDefaultCollation(
                       (CDbAndSetOptsImplImport *)(unsigned __int16)Size_4,
                       v59);
  v209 = DefaultCollation;
  if ( CDefaultCollation::FEqW(DefaultCollation, *(const wchar_t **)(v52 + 2208), *(_DWORD *)(v52 + 2216), L"dbo", 6u)
    || CDefaultCollation::FEqW(DefaultCollation, *(const wchar_t **)(v52 + 2208), *(_DWORD *)(v52 + 2216), L"sys", 6u)
    || CDefaultCollation::FEqW(
         DefaultCollation,
         *(const wchar_t **)(v52 + 2208),
         *(_DWORD *)(v52 + 2216),
         L"INFORMATION_SCHEMA",
         0x24u) )
  {
    ex_raise(150, 23, 16, 1, v393);
  }
  v61 = *(_BYTE *)(*(_QWORD *)(*(_QWORD *)&SourceSize[1] + 72LL) + 270LL) & 4;
  if ( v61 && v193 )
  {
    v236 = v17;
    v237 = v53;
    CheckContainedUserNameConflict(&v236, v198, v194, 2, v393);
LABEL_161:
    v62 = v173;
LABEL_162:
    v63 = v184;
    if ( v175 && v184 )
    {
      if ( !CDefaultCollation::FEqW(v209, *(const wchar_t **)(v52 + 2208), *(_DWORD *)(v52 + 2216), v17, v53) )
        ex_raise(150, 6, 16, 1, v393);
      v63 = v184;
    }
    if ( (v62 || v176) && v63 )
      ex_raise(150, 6, 16, 1, v393);
    v72 = DestinationSize;
    goto LABEL_242;
  }
  v29 = DestinationSize_4;
  if ( !v61 )
    goto LABEL_161;
  v62 = v173;
  if ( v174 || !v53 || v195 == 7 || v173 || v176 || v210 )
    goto LABEL_162;
  v64 = (DBTABLE *)g_dbtableFactory[4](Size_4);
  v65 = v64;
  do
    ++v54;
  while ( aMaster_0[v54] );
  v66 = DBTABLE::CbLogicalDbNameInternal(v64);
  v67 = DBTABLE::LogicalDbNameInternal(v65);
  v69 = (CDefaultCollation *)CDefaultCollation::PDCServer(v68);
  if ( CDefaultCollation::FEqIgnoreCaseW(v69, v67, v66, L"master", 2 * v54) )
  {
    v53 = Size;
    ServerPrincipal = CGatewayServerPrincipals::GetServerPrincipal(
                        *(const struct CCompExecCtxtBasic **)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                              + SystemThread_TlsIndex)
                                                            + SystemThread_TlsOffset),
                        v17,
                        Size);
    v197 = ServerPrincipal;
    v71 = 0;
    if ( !ServerPrincipal )
    {
      v238 = v17;
      v164 = Size_4;
      v239 = Size;
      v71 = (*(__int64 (__fastcall **)(__int64, wchar_t **, __int64))(*(_QWORD *)v199 + 328LL))(v199, &v238, 1);
    }
    if ( (qword_102F21DB4 & 1) != 0 )
    {
      v335 = 327680;
      v336 = 0;
      v337 = &v340;
      v338 = &v354;
      v355 = 0;
      v339 = 0;
      v356 = 0;
      v340 = &v357;
      v341 = 32;
      v342 = 4;
      v348 = 0;
      v349 = 0;
      v350 = 2;
      v351 = 0;
      v352 = 0;
      v353 = 3;
      v343 = L"CREATE";
      v344 = 12;
      v345 = L"GETLOGINSID";
      v346 = 22;
      v347 = 1;
      XeCloudPkg::azuresqldb_user_ddl::Publish((XeCloudPkg::azuresqldb_user_ddl *)v334);
    }
    if ( v71 )
    {
      v73 = (*(unsigned int (__fastcall **)(__int64, unsigned __int8 *, __int64))(*(_QWORD *)v71 + 8LL))(
              v71,
              Destination,
              85);
      v74 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v71 + 24LL))(v71);
      if ( v74 == 7 )
      {
        v55 = 7;
      }
      else if ( v74 == 8 )
      {
        v55 = 8;
      }
      else
      {
        ex_raise(150, 7, 16, 8, v393);
      }
      LOBYTE(v164) = 1;
      if ( (*(__int64 (__fastcall **)(__int64, unsigned __int8 *, _QWORD, _QWORD, unsigned int))(*(_QWORD *)v194 + 240LL))(
             v194,
             Destination,
             (unsigned int)v73,
             0,
             v164) )
      {
        ex_raise(150, 23, 16, 2, v393);
      }
      LOWORD(v200) = -8534;
      if ( &Destination[v73] )
      {
        *(_WORD *)&Destination[v73] = v200;
      }
      else
      {
        *_errno() = 22;
        _invalid_parameter_noinfo();
      }
      v72 = v73 + 2;
      DestinationSize = v72;
      if ( byte_102EDCA55 )
      {
        Uuid = *(UUID *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v71 + 80LL))(v71, &v384);
        if ( *(_QWORD *)&Uuid.Data1 == *(_QWORD *)&Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val.Data1
          && *(_QWORD *)Uuid.Data4 == *(_QWORD *)Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val.Data4 )
        {
          StringUuid[0] = 0;
          AzureActiveDirectoryService::GetTenantId(v198, StringUuid);
          v75 = StringUuid[0];
          if ( StringUuid[0] && UuidFromStringW(StringUuid[0], &Uuid) && *(int *)v190 >= 0 )
          {
            _mm_lfence();
            scierrlog(0x9280u, *(unsigned int *)v190, L"CStmtCreateUser::XretExecute", 2063);
            v53 = Size;
            v72 = DestinationSize;
            v75 = StringUuid[0];
          }
          operator delete[](v75);
        }
      }
    }
    else
    {
      if ( !ServerPrincipal )
        ex_raise(150, 7, 16, 2, v17);
      memcpy_s(Destination, DestinationSize, (char *)ServerPrincipal + 268, *((unsigned int *)ServerPrincipal + 89));
      v72 = *((_DWORD *)ServerPrincipal + 89);
      DestinationSize = v72;
    }
    v197 = ServerPrincipal;
    if ( ServerPrincipal )
    {
      operator delete[](*((void **)ServerPrincipal + 147));
      operator delete(ServerPrincipal, 0x4A8u);
      v29 = 1;
      v177[0] = 1;
      v52 = v180;
      goto LABEL_242;
    }
  }
  else
  {
    Source = 0;
    SourceSize[0] = 0;
    v186 = 0;
    v185 = 0;
    v192 = 7;
    v240 = v17;
    v241 = v53;
    v76 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v77 = *(_QWORD *)(v76 + 256);
    if ( !v77 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v77 = *(_QWORD *)(v76 + 256);
    }
    v78 = *(void **)(v77 + 1000);
    v203 = 0;
    v202 = 0;
    v204 = 0;
    LOBYTE(v164) = 0;
    (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, int *, unsigned int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
      s_pServerConf,
      L"Security",
      L"RetryUserDDLXOdbcInitialBackoff",
      &v203,
      v164,
      0);
    LOBYTE(v165) = 0;
    (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, int *, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
      s_pServerConf,
      L"Security",
      L"RetryUserDDLXOdbcMaxDuration",
      &v202,
      v165,
      0);
    LOBYTE(v166) = 0;
    (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, int *, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
      s_pServerConf,
      L"Security",
      L"RetryUserDDLXOdbcMaxNoofRetries",
      &v204,
      v166,
      0);
    v79 = v203;
    LODWORD(v384) = v203;
    *((_QWORD *)&v384 + 1) = v202;
    LOWORD(v385) = v204;
    v226[1] = v78;
    v200 = 91;
    v80 = (struct CGatewayServerPrincipal *)operator new(
                                              0x28u,
                                              (struct IMemObj *)v78,
                                              "sql\\ntdbms\\include\\xodbcwrapper.h",
                                              91,
                                              3u);
    v197 = v80;
    if ( v80 )
    {
      *(_OWORD *)v80 = v384;
      *((_QWORD *)v80 + 2) = v385;
      *((_DWORD *)v80 + 6) = v79;
      *((_WORD *)v80 + 14) = 0;
    }
    else
    {
      v80 = 0;
    }
    v226[0] = v80;
    LODWORD(v167) = 0;
    LoginSidFromLogicalMaster = CAutoOdbcConnectionWrapper::GetLoginSidFromLogicalMaster(
                                  (CAutoOdbcConnectionWrapper *)v226,
                                  (const struct MDName *)&v240,
                                  0,
                                  0,
                                  v167,
                                  (unsigned __int8 **)&Source,
                                  SourceSize,
                                  &v186,
                                  &v185,
                                  &v192,
                                  1,
                                  &Uuid);
    operator delete(v226[0], 0x28u);
    if ( (qword_102F21DB4 & 1) != 0 )
    {
      v287 = 327680;
      v288 = 0;
      v289 = &v292;
      v290 = &v306;
      v307 = 0;
      v291 = 0;
      v308 = 0;
      v292 = &v309;
      v293 = 32;
      v294 = 4;
      v300 = 0;
      v301 = 0;
      v302 = 2;
      v303 = 0;
      v304 = 0;
      v305 = 3;
      v295 = L"CREATE";
      v296 = 12;
      v299 = 1;
      if ( LoginSidFromLogicalMaster )
      {
        v82 = L"GETLOGINSID";
        v298 = 22;
      }
      else
      {
        v82 = L"GETLOGINSIDFAILURE";
        v298 = 36;
      }
      v297 = v82;
      XeCloudPkg::azuresqldb_user_ddl::Publish((XeCloudPkg::azuresqldb_user_ddl *)v286);
    }
    if ( !LoginSidFromLogicalMaster || (v83 = SourceSize[0]) == 0 || !Source )
    {
      ex_raise(150, 7, 16, 6, v17);
      v83 = SourceSize[0];
    }
    if ( v83 > 0x55 )
    {
      ex_raise(154, 19, 16, 6);
      v83 = SourceSize[0];
    }
    memcpy_s(Destination, DestinationSize, Source, v83);
    v72 = SourceSize[0];
    if ( SourceSize[0] == 16 || byte_102EDCC3D && SourceSize[0] == 18 && *((_WORD *)Source + 8) == 0xDEAA )
    {
      if ( v192 == 7 )
      {
        v55 = 7;
      }
      else if ( v192 == 8 )
      {
        v55 = 8;
      }
      LOBYTE(v168) = 1;
      if ( (*(__int64 (__fastcall **)(__int64, unsigned __int8 *, _QWORD, _QWORD, int))(*(_QWORD *)v194 + 240LL))(
             v194,
             Destination,
             SourceSize[0],
             0,
             v168) )
      {
        ex_raise(150, 23, 16, 3, v393);
      }
      v84 = SourceSize[0];
      v191 = -8534;
      v85 = &Destination[SourceSize[0]];
      if ( v85 )
      {
        *(_WORD *)v85 = v191;
      }
      else
      {
        *_errno() = 22;
        _invalid_parameter_noinfo();
      }
      v72 = v84 + 2;
    }
    DestinationSize = v72;
    operator delete[](Source);
    v53 = Size;
  }
  v29 = 1;
  v177[0] = 1;
  v52 = v180;
LABEL_242:
  v86 = v209;
  v87 = CDefaultCollation::FEqW(v209, *(const wchar_t **)(v52 + 2208), *(_DWORD *)(v52 + 2216), L"guest", 0xAu);
  v192 = v87;
  if ( v87 )
  {
    if ( !CDefaultCollation::FEqW(v86, v17, v53, L"guest", 0xAu) )
      ex_raise(150, 62, 16, 1);
    if ( v174 )
      ex_raise(150, 6, 16, 1, v393);
  }
  if ( (unsigned int)CSECCertParams::GetCertType(*(_QWORD *)(v52 + 2208), *(unsigned int *)(v52 + 2216), Size_4) != 11 )
  {
    v90 = *(_DWORD *)(v52 + 2216);
    v91 = *(_WORD **)(v52 + 2208);
    v92 = &CSECCertParams::m_rgCertParams + 6 * (int)CSECCertParams::GetCertType(v91, v90, Size_4);
    if ( *(_DWORD *)v92 == 11 && v90 && *v91 == 35
      || !CSECCertParams::FCanDoActionInMode(
            (int)(*((_DWORD *)v92 + 10) << 31) >> 31,
            (const struct CSECCertParams::_SECCertParams *)v92,
            Size_4) )
    {
      ex_raise(152, 47, 16, 1);
    }
    v52 = v180;
  }
  if ( v192 )
  {
    v55 = 0;
    goto LABEL_360;
  }
  if ( v173 )
  {
    v242 = v17;
    v243 = v53;
    v93 = (*(__int64 (__fastcall **)(__int64, wchar_t **, _QWORD))(*(_QWORD *)v194 + 800LL))(v194, &v242, 0);
    if ( !v93 )
    {
      LODWORD(v172) = v53;
      LODWORD(v171) = 13116;
      LODWORD(v169) = 13118;
      ex_raise(151, 51, 16, 1, v169, v171, v172, v17);
    }
    *(_QWORD *)&v220 = 0;
    CSECSessionCryptoContext::GetCryptoContext(
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                      + SystemThread_TlsIndex)
                                                    + SystemThread_TlsOffset)
                                        + 72LL)
                            + 104LL)
                + 264LL)
    + 216LL,
      v266,
      3,
      &v220);
    if ( v266[0] )
    {
      v197 = (struct CGatewayServerPrincipal *)v264;
      v265 = 0;
      CSECCryptoError::DeepCopyCSECCryptoError((CSECCryptoError *)v264, (const struct CSECCryptoError *)v266);
      RaiseCryptoError(v264, 0);
    }
    if ( v267 )
      operator delete[](v267);
    *(_OWORD *)hCertStore = 0;
    v228 = 0;
    v229 = v220;
    pCertContext = 0;
    v231 = 0;
    CSECCertificate::InitFromMD(hCertStore, v270, v198, v93);
    if ( v270[0] )
    {
      v197 = (struct CGatewayServerPrincipal *)v268;
      v269 = 0;
      CSECCryptoError::DeepCopyCSECCryptoError((CSECCryptoError *)v268, (const struct CSECCryptoError *)v270);
      RaiseCryptoError(v268, 0);
    }
    if ( v271 )
      operator delete[](v271);
    CSECCertificate::GetSid(hCertStore, v274, &DestinationSize, Destination);
    if ( v274[0] )
    {
      v197 = (struct CGatewayServerPrincipal *)v272;
      v273 = 0;
      CSECCryptoError::DeepCopyCSECCryptoError((CSECCryptoError *)v272, (const struct CSECCryptoError *)v274);
      RaiseCryptoError(v272, 0);
    }
    if ( v275 )
      operator delete[](v275);
    v55 = 5;
    if ( pCertContext )
    {
      CertFreeCertificateContext(pCertContext);
      pCertContext = 0;
    }
    v89 = (unsigned __int64)hCertStore[0];
    if ( hCertStore[0] )
    {
      CertCloseStore(hCertStore[0], 0);
      hCertStore[0] = 0;
    }
    v72 = DestinationSize;
    goto LABEL_360;
  }
  if ( v176 )
  {
    v244 = v17;
    v245 = v53;
    v94 = (*(__int64 (__fastcall **)(__int64, wchar_t **, _QWORD))(*(_QWORD *)v194 + 960LL))(v194, &v244, 0);
    if ( !v94 )
    {
      LODWORD(v172) = v53;
      LODWORD(v171) = 13141;
      LODWORD(v169) = 13118;
      ex_raise(151, 51, 16, 1, v169, v171, v172, v17);
    }
    v210 = 0;
    CSECSessionCryptoContext::GetCryptoContext(
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                      + SystemThread_TlsIndex)
                                                    + SystemThread_TlsOffset)
                                        + 72LL)
                            + 104LL)
                + 264LL)
    + 216LL,
      v278,
      3,
      &v210);
    if ( v278[0] )
    {
      v197 = (struct CGatewayServerPrincipal *)v276;
      v277 = 0;
      CSECCryptoError::DeepCopyCSECCryptoError((CSECCryptoError *)v276, (const struct CSECCryptoError *)v278);
      RaiseCryptoError(v276, 0);
    }
    if ( v279 )
      operator delete[](v279);
    CSECAsymmetricKey::CSECAsymmetricKey(v389, v210, 0, 0);
    CSECAsymmetricKey::InitFromMD(v389, v282, v198, v94);
    if ( v282[0] )
    {
      v197 = (struct CGatewayServerPrincipal *)v280;
      v281 = 0;
      CSECCryptoError::DeepCopyCSECCryptoError((CSECCryptoError *)v280, (const struct CSECCryptoError *)v282);
      RaiseCryptoError(v280, 0);
    }
    if ( v283 )
      operator delete[](v283);
    CSECAsymmetricKey::GetSid(v389, v284, &DestinationSize, Destination);
    if ( v284[0] )
    {
      v197 = (struct CGatewayServerPrincipal *)v262;
      v263 = 0;
      CSECCryptoError::DeepCopyCSECCryptoError((CSECCryptoError *)v262, (const struct CSECCryptoError *)v284);
      RaiseCryptoError(v262, 0);
    }
    if ( v285 )
      operator delete[](v285);
    v55 = 6;
    CSECAsymmetricKey::~CSECAsymmetricKey((CSECAsymmetricKey *)v389);
    v72 = DestinationSize;
    goto LABEL_360;
  }
  if ( v195 == 7 )
  {
    v175 = 0;
    v187 = 0;
    v95 = 0;
    v96 = v180;
    if ( byte_102EDCA59 )
    {
      v97 = *(_QWORD *)(v180 + 2424);
      if ( v97 )
      {
        v95 = *(wchar_t **)(v97 + 8);
        v98 = *(_DWORD *)(v97 + 16);
      }
      else
      {
        v98 = 0;
      }
      v217 = v98;
    }
    if ( byte_102EDCA55
      && (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)&SourceSize[1] + 72LL) + 270LL) & 4) != 0
      && *(_DWORD *)(qword_102ECFB00 + 14504) )
    {
      v99 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                + SystemThread_TlsIndex)
                                              + SystemThread_TlsOffset)
                                  + 120LL)
                      + 264LL);
      v100 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v99 + 568LL))(v99, v194, 1, 0);
      if ( v100 )
        Uuid = *(UUID *)(*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v100 + 608LL))(v100, v388);
      if ( *(_QWORD *)&Uuid.Data1 == *(_QWORD *)&Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val.Data1
        && _mm_srli_si128((__m128i)Uuid, 8).m128i_u64[0] == *(_QWORD *)Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val.Data4 )
      {
        v221 = 0;
        AzureActiveDirectoryService::GetTenantId(v198, &v221);
        UuidFromStringW(v221, &Uuid);
        operator delete[](v221);
        v53 = Size;
      }
      else
      {
        v53 = Size;
      }
    }
    v101 = Uuid;
    v102 = v394;
    if ( v95 )
      v102 = v95;
    if ( !v17 )
      goto LABEL_315;
    if ( !v53 )
      goto LABEL_315;
    v103 = 0;
    if ( !((unsigned __int64)v53 >> 1) )
      goto LABEL_315;
    v104 = 0;
    while ( v17[v104] != 92 )
    {
      ++v103;
      if ( ++v104 >= (__int64)((unsigned __int64)v53 >> 1) )
        goto LABEL_315;
    }
    if ( v103 >= 0 && v53 - 1 != v103 )
    {
      v105 = v95 != 0;
    }
    else
    {
LABEL_315:
      v105 = v95 != 0;
      if ( !*(_DWORD *)(qword_102ECFB00 + 14504) && !IsBoxAADEnabled(0) )
        ex_raise(154, 7, 16, 1, v102);
    }
    p_Size = (unsigned int *)&v217;
    if ( !v95 )
      p_Size = &Size;
    v258 = v101;
    if ( v95 )
      v17 = v95;
    LOBYTE(v171) = v105;
    LookupFederatedPrincipal(
      v17,
      p_Size,
      v102,
      2,
      &pguid,
      (_DWORD)v171,
      Destination,
      &DestinationSize,
      &v175,
      &v187,
      &v258);
    v55 = 8 - (v175 != 0);
    v72 = DestinationSize;
LABEL_361:
    if ( !v193 )
      goto LABEL_365;
    goto LABEL_362;
  }
  if ( v177[0] )
  {
LABEL_360:
    v96 = v180;
    goto LABEL_361;
  }
  v107 = v174;
  v108 = v201;
  if ( !v174 && !v201 )
  {
    v246 = v17;
    v247 = v53;
    v109 = (*(__int64 (__fastcall **)(__int64, wchar_t **, _QWORD, __int64, _DWORD))(*(_QWORD *)v199 + 328LL))(
             v199,
             &v246,
             0,
             1,
             0);
    v110 = v109;
    if ( v109 )
    {
      v72 = (*(__int64 (__fastcall **)(__int64, unsigned __int8 *, __int64))(*(_QWORD *)v109 + 8LL))(
              v109,
              Destination,
              85);
      v111 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v110 + 24LL))(v110);
      if ( v72 == 1 && Destination[0] == 1 )
        ex_raise(154, 5, 16, 1, v394);
      if ( v111 )
      {
        switch ( v111 )
        {
          case 1:
            v55 = 1;
            break;
          case 2:
            v55 = 2;
            break;
          case 4:
            v55 = 5;
            break;
          case 5:
            v55 = 6;
            break;
          case 7:
            v55 = 7;
            break;
          case 8:
            v55 = 8;
            break;
          case 6:
            LODWORD(v172) = v53;
            LODWORD(v171) = 13115;
            LODWORD(v169) = 13118;
            ex_raise(151, 51, 16, 1, v169, v171, v172, v17);
            break;
          default:
            ex_raise(154, 5, 16, 1, v393);
            break;
        }
      }
      else
      {
        v55 = 0;
      }
      if ( *(_DWORD *)(qword_102ECFB00 + 14504)
        && (unsigned int)(v55 - 7) <= 1
        && !*(_DWORD *)(GetXdbServerGlobals(v89, v88) + 11976)
        && !(unsigned int)IsVDWFrontendInstance()
        && !CDefaultCollation::FEqW(v209, *(const wchar_t **)(v52 + 2208), *(_DWORD *)(v52 + 2216), v17, v53) )
      {
        ex_raise(331, 48, 16, 1);
      }
      if ( v184 && (!v55 || (unsigned int)(v55 - 5) <= 1) )
        ex_raise(150, 6, 16, 1, v393);
      goto LABEL_360;
    }
    v107 = 0;
    v108 = v201;
  }
  v122 = 0;
  if ( !v17 )
    goto LABEL_387;
  if ( !v53 )
    goto LABEL_387;
  v89 = 0;
  v88 = (unsigned __int64)v53 >> 1;
  if ( !v88 )
    goto LABEL_387;
  v123 = 0;
  while ( v17[v123] != 92 )
  {
    v89 = (unsigned int)(v89 + 1);
    if ( ++v123 >= v88 )
      goto LABEL_387;
  }
  v89 = (unsigned __int64)&v17[(int)v89];
  if ( !v89 )
  {
LABEL_387:
    if ( !v108 )
    {
      if ( !v107 )
        ex_raise(150, 7, 16, 1, v394);
      if ( !v29 )
      {
        if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)&SourceSize[1] + 72LL) + 270LL) & 4) != 0 && v193 )
        {
          v124 = 0;
          v223 = 0;
          if ( *(_DWORD *)(qword_102ECFB00 + 14504) )
          {
            v122 = 2;
            v124 = (unsigned int *)operator new[](8u, v198, "sql\\ntdbms\\msql\\security\\src\\secddl.cpp", 2528, 3u);
            if ( v124 )
              operator delete[](0);
            v223 = v124;
            *(_QWORD *)v124 = 0;
          }
          if ( !(unsigned int)GenerateSidForGatewayLogin(v124, v122, 0, Destination, &DestinationSize, 1) )
            ex_raise(151, 67, 16, 1);
          operator delete[](v124);
          v72 = DestinationSize;
          v55 = 0;
          goto LABEL_360;
        }
        if ( CoCreateGuid(&v387) )
          ex_raise(151, 67, 16, 1);
        if ( v72 - 1 > 0x1A )
        {
          v72 = 28;
          *(_DWORD *)pIdentifierAuthority.Value = 0;
          pIdentifierAuthority.Value[4] = 0;
          pIdentifierAuthority.Value[5] = 9;
          if ( InitializeSid(Destination, &pIdentifierAuthority, 5u) )
          {
            v391 = 3;
            memcpy_s(v392, 0x10u, &v387, 0x10u);
            v55 = 0;
            goto LABEL_360;
          }
        }
        ex_raise(151, 67, 16, 1);
      }
      v55 = 0;
      goto LABEL_360;
    }
LABEL_428:
    if ( v205 != 2 )
      ex_raise(331, 63, 16, 1);
    if ( v222 )
    {
      v130 = *v222;
      if ( *v222 == 69 )
        goto LABEL_436;
      switch ( v130 )
      {
        case 'X':
LABEL_435:
          v55 = 8;
          goto LABEL_360;
        case 'e':
LABEL_436:
          v55 = 7;
          goto LABEL_360;
        case 'x':
          goto LABEL_435;
      }
    }
    v55 = 0;
    ex_raise(331, 63, 16, 2);
    goto LABEL_360;
  }
  if ( v108 )
    goto LABEL_428;
  v183[0] = 0;
  v177[0] = 0;
  v125 = 0;
  v126 = 0;
  while ( v17[v126] != 92 )
  {
    ++v125;
    if ( ++v126 >= v88 )
      goto LABEL_405;
  }
  if ( v125 < 0 || v53 - 1 == v125 )
  {
LABEL_405:
    if ( !*(_DWORD *)(qword_102ECFB00 + 14504) && !IsBoxAADEnabled(0) )
      ex_raise(154, 7, 16, 1, v394);
    goto LABEL_418;
  }
  if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                         + SystemThread_TlsOffset)
                             + 72LL)
                 + 270LL)
      & 4) != 0 )
  {
LABEL_418:
    v259 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
    LOBYTE(v171) = 0;
    LookupFederatedPrincipal(
      v17,
      &Size,
      v394,
      2,
      &pguid,
      (_DWORD)v171,
      Destination,
      &DestinationSize,
      v183,
      v177,
      &v259);
    v72 = DestinationSize;
    v128 = v183[0];
    goto LABEL_419;
  }
  v190[0] = 85;
  v127 = FGetSidFromNt(v17, Size, Destination, v190, 85, 1);
  v128 = v127 != 0;
  if ( v127 )
    v129 = v177[0];
  else
    v129 = (unsigned int)FGetSidFromNt(v17, Size, Destination, v190, 71, 1) != 0;
  if ( !v128 && !v129 )
    ex_raise(154, 1, 16, 1, v394);
  v72 = v190[0];
LABEL_419:
  v55 = 2 - v128;
  if ( v193 )
  {
    ex_raise(332, 37, 16, 1, L"PASSWORD");
    v96 = v180;
LABEL_362:
    if ( v55 || *(_DWORD *)(v96 + 2432) != 6 )
      ex_raise(332, 34, 16, 1, L"PASSWORD");
  }
LABEL_365:
  v112 = 0;
  v113 = v180;
  v114 = *(_QWORD *)(v180 + 2320);
  if ( !v114 )
    goto LABEL_448;
  v115 = *(const wchar_t **)(v114 + 8);
  v116 = *(_DWORD *)(v114 + 20);
  v117 = *(_BYTE *)(v114 + 24);
  v118 = *(unsigned int *)(v114 + 16);
  if ( !(_DWORD)v118 && !v117 )
    goto LABEL_447;
  if ( (!v218 || (unsigned int)(v55 - 1) > 1 && *(_DWORD *)(v180 + 2432) != 6)
    && (!*(_DWORD *)(GetXdbServerGlobals(v89, v88) + 11976)
     && !(unsigned int)IsVDWFrontendInstance()
     && !IsBoxAADEnabled(0)
     || (unsigned int)(v55 - 7) > 1) )
  {
    ex_raise(332, 34, 16, 1, L"DEFAULT_LANGUAGE");
  }
  if ( v117 )
  {
    LangInfoByLCID = GetLangInfoByLCID(v116);
    if ( !LangInfoByLCID )
    {
      LODWORD(v169) = v116;
      v120 = 2;
      v121 = 98;
LABEL_379:
      ex_raise(v121, v120, 16, 1, v169);
      v113 = v180;
      goto LABEL_448;
    }
LABEL_442:
    v132 = (const void *)*((_QWORD *)LangInfoByLCID + 1);
    if ( *((_BYTE *)LangInfoByLCID + 16) )
    {
      if ( v132 )
      {
        memmove(v395, v132, *((unsigned __int8 *)LangInfoByLCID + 16));
      }
      else
      {
        memset_0(v395, 0, 0x102u);
        *_errno() = 22;
        _invalid_parameter_noinfo();
      }
    }
    v112 = *((unsigned __int8 *)LangInfoByLCID + 16);
    goto LABEL_447;
  }
  if ( CompareStringWEnglishNoCase(1u, 0, v115, (unsigned __int64)(int)v118 >> 1, L"none", 4) != 2 )
  {
    LangInfoByLCID = GetLangInfoByName(v115, v118);
    if ( !LangInfoByLCID )
    {
      LangInfoByLCID = GetLangInfoByAlias(v115, v118);
      if ( !LangInfoByLCID )
      {
        v131 = GetDefaultLocale();
        StringCchPrintf_lW(v396, 0x81u, L"%.*s", v131, v118 >> 1, v115);
        v169 = v396;
        v120 = 33;
        v121 = 150;
        goto LABEL_379;
      }
    }
    goto LABEL_442;
  }
LABEL_447:
  v113 = v180;
LABEL_448:
  v133 = 0;
  v134 = v194;
  v135 = *(_QWORD *)v194;
  if ( v192 )
  {
    v136 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(v135 + 232))(v194, 2, 1);
    v137 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v136 + 72LL))(v136);
    v138 = (**v137)(v137);
    if ( (((unsigned int)GetUserDbAccessEPS(v199, v194, v138, 1) - 1) & 0xFFFFFFFD) == 0 )
      ex_raise(150, 23, 16, 4, v393);
  }
  else
  {
    LOBYTE(v169) = 1;
    if ( (*(__int64 (__fastcall **)(__int64, unsigned __int8 *, _QWORD, _QWORD, _DWORD))(v135 + 328))(
           v194,
           Destination,
           v72,
           0,
           (_DWORD)v169) )
    {
      ex_raise(150, 22, 16, 1);
    }
    else
    {
      LOBYTE(v170) = 1;
      LOBYTE(v139) = 1;
      v144 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(__int64, unsigned __int8 *, _QWORD, __int64, int))(*(_QWORD *)v134 + 240LL))(
                                                 v134,
                                                 Destination,
                                                 v72,
                                                 v139,
                                                 v170);
      v138 = (__int64)v144;
      if ( v144 )
      {
        v145 = (**v144)(v144);
        v137 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v138 + 72LL))(v138);
        v133 = 1;
        UserDbAccessEPS = GetUserDbAccessEPS(v199, v194, v138, 1);
        if ( !v55 || ((UserDbAccessEPS - 1) & 0xFFFFFFFD) == 0 )
        {
          if ( v145
            && CDefaultCollation::FEqW(
                 v209,
                 *(const wchar_t **)(v113 + 2208),
                 *(_DWORD *)(v113 + 2216),
                 *(const wchar_t **)v145,
                 *(_DWORD *)(v145 + 8)) )
          {
            ex_raise(150, 23, 16, 5, v393);
          }
          else
          {
            ex_raise(150, 63, 16, 1);
          }
        }
        goto LABEL_471;
      }
    }
    v140 = *(_DWORD *)(v113 + 2216);
    v141 = *(_QWORD *)(v113 + 2208);
    if ( byte_102EDCA55 )
    {
      v260 = Uuid;
      v248 = v141;
      v249 = v140;
      v142 = &v260;
      v143 = &v248;
    }
    else
    {
      v261 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
      v250 = v141;
      v251 = v140;
      v142 = &v261;
      v143 = &v250;
    }
    v138 = (*(__int64 (__fastcall **)(__int64, __int64 *, unsigned __int8 *, _QWORD, int, GUID *))(*(_QWORD *)v134
                                                                                                 + 248LL))(
             v134,
             v143,
             Destination,
             v72,
             v55,
             v142);
    if ( !v138 )
      ex_raise(150, 23, 16, 6, v393);
    if ( *(_DWORD *)(v113 + 2432) == 6 )
    {
      v147 = *(_QWORD *)(v113 + 2256);
      if ( !v147 || (v148 = *(const wchar_t **)(v147 + 8), !*(_DWORD *)(v147 + 16)) )
        v148 = &szPassword;
      CheckSetUserPwd(4, v138, v148);
    }
    v137 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v138 + 72LL))(v138);
  }
LABEL_471:
  v149 = (**v137)(v137);
  SetDbConnectPermission(v199, v149, 1);
  v150 = 0;
  v151 = *(_QWORD *)(v113 + 2224);
  if ( v151 )
  {
    v150 = *(_QWORD *)(v151 + 8);
    v152 = *(_DWORD *)(v151 + 16);
  }
  else
  {
    v152 = 0;
  }
  if ( (unsigned int)(v55 - 5) <= 1 )
  {
    if ( v152 )
      ex_raise(152, 59, 16, 1);
  }
  else if ( !v152 || v133 && (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v138 + 48LL))(v138) )
  {
    if ( v55 != 2 && v55 != 8 && (!v133 || !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v138 + 48LL))(v138)) )
    {
      v232 = L"dbo";
      v233 = 6;
      (*(void (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v138 + 456LL))(v138, &v232);
    }
  }
  else
  {
    v252 = v150;
    v253 = v152;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v138 + 456LL))(v138, &v252);
  }
  if ( v112 && ((unsigned int)(v55 - 1) <= 1 || (unsigned int)(v55 - 7) <= 1 || *(_DWORD *)(v113 + 2432) == 6) )
  {
    v234 = v395;
    v235 = v112;
    (*(void (__fastcall **)(__int64, _BYTE **))(*(_QWORD *)v138 + 520LL))(v138, &v234);
  }
  if ( v206 )
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v138 + 600LL))(v138, (unsigned __int8)v196);
  if ( *(_DWORD *)(qword_102ECFB00 + 14504) )
  {
    if ( byte_102EDCA50 )
    {
      if ( byte_102EF429C )
      {
        ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
        v154 = *(_QWORD *)(*(_QWORD *)(ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset) + 72LL);
        v155 = *(_QWORD *)(v154 + 96);
        if ( v155 )
        {
          LOBYTE(ThreadLocalStoragePointer) = 2;
          v156 = CPhysicalConnection::GetFeatureExtension(*(_QWORD *)(v154 + 96), ThreadLocalStoragePointer)
              && *(_DWORD *)(v155 + 988) != 2;
          if ( !v55 && (v193 || *(_DWORD *)(v113 + 2432) == 1 && Size) && v156 )
            ex_raise(374, 57, 16, 2);
        }
      }
    }
  }
  v157 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v138 + 8LL))(v138);
  v158 = Size_4;
  if ( !v212 )
  {
    v254 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
    ISECManager::CheckPermRuleAuditOnly(1380144472, v198, v199, Size_4, v157, v188, 21333, 0, 0, &v254, 0, 0, 0, -1);
    v212 = 1;
  }
  v159 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v199 + 16LL))(v199);
  v160 = g_dbtableFactory[4](v158);
  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v159 + 280LL))(v159, *(_QWORD *)(v160 + 4624));
  InvalidateSecurityCaches(v158, 0, v158);
  v161 = v224;
  if ( !*(_BYTE *)(v224 + 240)
    || (DestinationSize_4 = 1,
        v162 = *(_QWORD *)(v224 + 56),
        *(_QWORD *)(v224 + 56) = 0,
        PostOwnerMgmtEvent(34, *(_QWORD *)&SourceSize[1], v161, v225, v162, v194, v138, &DestinationSize_4, 0, 0, 0, 0),
        DestinationSize_4) )
  {
    if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)&SourceSize[1] + 72LL) + 270LL) & 4) != 0 && (qword_102F21DB4 & 1) != 0 )
    {
      v359 = 327680;
      v360 = 0;
      v361 = &v364;
      v362 = &v378;
      v379 = 0;
      v363 = 0;
      v380 = 0;
      v364 = &v381;
      v365 = 32;
      v366 = 4;
      v372 = 0;
      v373 = 0;
      v374 = 2;
      v375 = 0;
      v376 = 0;
      v377 = 3;
      v367 = L"CREATE";
      v368 = 12;
      v369 = L"FINISH";
      v370 = 12;
      v371 = 1;
      XeCloudPkg::azuresqldb_user_ddl::Publish((XeCloudPkg::azuresqldb_user_ddl *)v358);
    }
    *(_BYTE *)(v161 + 176) |= 0x10u;
    v207 = 0;
  }
  CAutoHandleCreateAudit::~CAutoHandleCreateAudit((CAutoHandleCreateAudit *)v211);
  return v207;
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
