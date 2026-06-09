# COledbConnect::GatherConnectionProperties(IUnknown *,OLEDB_PROPCONN *)

- ea: `0x1016e0a40`
- end: `0x1016e66a9`
- name: `?GatherConnectionProperties@COledbConnect@@IEAAXPEAUIUnknown@@PEAUOLEDB_PROPCONN@@@Z`
- size: `23657`
- prototype: `void __fastcall(COledbConnect *__hidden this, struct IUnknown *, struct OLEDB_PROPCONN *)`
- caller_count: `4`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1012d1900`
- `0x1012d3fb0`
- `0x1016f1cc0`
- `0x101701080`

## callees

- `0x100401070`
- `0x100401090`
- `0x1004132a0`
- `0x100422f40`
- `0x100430d60`
- `0x100430e10`
- `0x1004c8670`
- `0x1005509c0`
- `0x1016d8890`
- `0x1016e0a40`
- `0x1016e69f0`
- `0x1016ec360`
- `0x101e5a890`
- `0x101e5a920`
- `0x101e5c8d0`
- `0x101e5c980`
- `0x101e5ca20`
- `0x101e5edc0`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1016e5053`
- `OLEAUT32!__imp_VariantClear` at `0x1016e5b56`
- `OLEAUT32!__imp_VariantClear` at `0x1016e5053`
- `OLEAUT32!__imp_VariantClear` at `0x1016e5b56`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1016e1aec`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1016e1fa6`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1016e1aec`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1016e1fa6`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1016e5017`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1016e5b21`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1016e5017`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1016e5b21`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016e0c2d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016e0c69`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016e1071`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016e10ae`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016e52e9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016e5326`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016e0c2d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016e0c69`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016e1071`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016e10ae`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016e52e9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016e5326`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1016e5d8d`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1016e5ea3`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1016e5fc5`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1016e60da`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1016e61e6`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1016e62fa`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1016e5d8d`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1016e5ea3`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1016e5fc5`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1016e60da`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1016e61e6`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1016e62fa`
- `sqldk!SystemThread_TlsIndex` at `0x1016e4b5e`
- `sqldk!SystemThread_TlsIndex` at `0x1016e4db6`
- `sqldk!SystemThread_TlsIndex` at `0x1016e4e2a`
- `sqldk!SystemThread_TlsIndex` at `0x1016e4fdf`
- `sqldk!SystemThread_TlsIndex` at `0x1016e5a16`
- `sqldk!SystemThread_TlsIndex` at `0x1016e5ae9`
- `sqldk!SystemThread_TlsOffset` at `0x1016e4b67`
- `sqldk!SystemThread_TlsOffset` at `0x1016e4dbf`
- `sqldk!SystemThread_TlsOffset` at `0x1016e4e33`
- `sqldk!SystemThread_TlsOffset` at `0x1016e4fe8`
- `sqldk!SystemThread_TlsOffset` at `0x1016e5a1f`
- `sqldk!SystemThread_TlsOffset` at `0x1016e5af2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016e5001`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016e5b0b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016e5001`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016e5b0b`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016e4df2`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016e4e61`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016e5a50`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016e4df2`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016e4e61`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016e5a50`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e0c78`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e10bd`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e118c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e125b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e1363`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e1435`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e1531`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e1603`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e16ff`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e17d1`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e19bd`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e1add`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e1c6c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e1f79`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e20e9`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e21ee`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e22f1`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e2414`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e2517`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e263a`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e273d`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e285b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e2984`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e2acb`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e2be3`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e2d37`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e2e42`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e2f45`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e304e`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e3183`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e329f`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e33bc`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e349a`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e3572`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e377b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e38e6`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e3a19`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e3b24`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e3c2f`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e3d3a`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e3e45`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e3f50`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e405b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e4166`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e4271`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e437c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e454b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e4650`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e474c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e4863`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e4973`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e4a86`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e4d4e`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e5335`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e53f6`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e54c2`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e5593`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e5650`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e5792`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e587c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e5956`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e5de0`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e5eef`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e6018`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e611f`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e6239`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e633f`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e0c78`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e10bd`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e118c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e125b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e1363`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e1435`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e1531`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e1603`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e16ff`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e17d1`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e19bd`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e1add`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e1c6c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e1f79`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e20e9`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e21ee`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e22f1`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e2414`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e2517`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e263a`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e273d`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e285b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e2984`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e2acb`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e2be3`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e2d37`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e2e42`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e2f45`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e304e`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e3183`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e329f`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e33bc`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e349a`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e3572`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e377b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e38e6`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e3a19`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e3b24`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e3c2f`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e3d3a`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e3e45`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e3f50`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e405b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e4166`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e4271`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e437c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e454b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e4650`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e474c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e4863`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e4973`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e4a86`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e4d4e`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e5335`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e53f6`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e54c2`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e5593`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e5650`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e5792`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e587c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e5956`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e5de0`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e5eef`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e6018`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e611f`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e6239`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016e633f`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x1016e19ec`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x1016e1c97`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x1016e1ccf`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x1016e1d06`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x1016e1d3d`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x1016e1d74`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x1016e1dab`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x1016e1de3`

## string_xrefs

- `0x1016e1d22`: `sqlnclirda11.dll`
- `0x1016e1ceb`: `msoledbsql.dll`
- `0x1016e2aa6`: `DBPROP_BYREFACCESSORS`
- `0x1016e1cb4`: `sqlncli11.dll`
- `0x1016e1d59`: `MSDASQL.DLL`
- `0x1016e1d90`: `MSJETOLEDB40.DLL`
- `0x1016e1dc8`: `MSDAORA.DLL`
- `0x1016e1dff`: `OraOLEDB.DLL`
- `0x1016e1e37`: `OraOLEDB10.DLL`
- `0x1016e1e6f`: `AccessServices.OLEDB`
- `0x1016e3f2b`: `SQLPROP_SIMPLEUPDATES`
- `0x1016e462b`: `SSPROP_UNICODECOMPARISONSTYLE`

## pseudocode

```c
// Hidden C++ exception states: #wind=91 #try_helpers=2
void __fastcall COledbConnect::GatherConnectionProperties(
        COledbConnect *this,
        struct IUnknown *a2,
        struct OLEDB_PROPCONN *a3)
{
  struct IUnknown *Interface; // rsi
  bool v6; // al
  int v7; // r12d
  __int64 v8; // rdi
  __int64 v9; // rax
  struct IUnknown *v10; // r12
  bool v11; // al
  int v12; // esi
  __int64 v13; // rdi
  __int64 v14; // rax
  __int64 v15; // rdi
  __int64 v16; // rax
  __int64 v17; // rdi
  __int64 v18; // rax
  __int64 v19; // rdi
  __int64 v20; // rax
  __int64 v21; // rdi
  __int64 v22; // rax
  __int64 v23; // rdi
  __int64 v24; // rax
  __int64 v25; // rdi
  __int64 v26; // rax
  __int64 v27; // rdi
  __int64 v28; // rax
  __int64 v29; // rdi
  __int64 v30; // rax
  int v31; // edi
  __int64 v32; // rdx
  __int64 v33; // r9
  unsigned int v34; // r12d
  __int64 v35; // rax
  SID *v36; // r8
  int *v37; // rsi
  unsigned int v38; // eax
  __int64 v39; // rdi
  __int64 v40; // rax
  __int64 v41; // rdi
  __int64 v42; // rax
  __crt_locale_pointers *DefaultLocale; // rax
  int v44; // eax
  int v45; // r10d
  int v46; // r10d
  int v47; // r10d
  __int64 v48; // rdi
  __int64 v49; // rax
  __int64 v50; // rdi
  __int64 v51; // rax
  __crt_locale_pointers *v52; // rax
  __int64 v53; // rdi
  __int64 v54; // rax
  int v55; // eax
  __int64 v56; // rdi
  __int64 v57; // rax
  __int64 v58; // rdi
  __int64 v59; // rax
  int v60; // eax
  __int64 v61; // rdi
  __int64 v62; // rax
  __int64 v63; // rdi
  __int64 v64; // rax
  int v65; // eax
  __int64 v66; // rdi
  __int64 v67; // rax
  __int64 v68; // rdi
  __int64 v69; // rax
  __int64 v70; // rdi
  __int64 v71; // rax
  int v72; // eax
  __int64 v73; // rdi
  __int64 v74; // rax
  int v75; // ecx
  __int64 v76; // rdi
  __int64 v77; // rax
  __int64 v78; // rdi
  __int64 v79; // rax
  int v80; // ecx
  char v81; // al
  __int64 v82; // rdi
  __int64 v83; // rax
  int v84; // eax
  __int64 v85; // rdi
  __int64 v86; // rax
  __int64 v87; // rdi
  __int64 v88; // rax
  int v89; // ecx
  __int64 v90; // rdi
  __int64 v91; // rax
  __int64 v92; // rdi
  __int64 v93; // rax
  __int64 v94; // rdi
  __int64 v95; // rax
  char v96; // al
  __int64 v97; // rdi
  __int64 v98; // rax
  __int64 v99; // rdi
  __int64 v100; // rax
  __int64 v101; // rdi
  __int64 v102; // rax
  unsigned int v103; // r13d
  __int64 v104; // rdx
  unsigned int v105; // r12d
  __int64 i; // rax
  __int64 v107; // rsi
  __int64 v108; // rdi
  __int64 v109; // rax
  char v110; // al
  char v111; // al
  char v112; // al
  __int64 v113; // rdi
  __int64 v114; // rax
  char v115; // al
  char v116; // al
  __int64 v117; // rdi
  __int64 v118; // rax
  __int64 v119; // rdi
  __int64 v120; // rax
  __int64 v121; // rdi
  __int64 v122; // rax
  __int64 v123; // rdi
  __int64 v124; // rax
  __int64 v125; // rdi
  __int64 v126; // rax
  __int64 v127; // rdi
  __int64 v128; // rax
  __int64 v129; // rdi
  __int64 v130; // rax
  __int64 v131; // rdi
  __int64 v132; // rax
  __int64 v133; // rdi
  __int64 v134; // rax
  __int64 v135; // rdi
  __int64 v136; // rax
  __int64 v137; // rax
  char *v138; // r8
  __int64 v139; // rdx
  unsigned int v140; // r13d
  __int64 v141; // rdi
  unsigned int v142; // r12d
  __int64 v143; // rax
  __int64 v144; // rsi
  __int16 v145; // ax
  __int64 v146; // rdi
  __int64 v147; // rax
  __int16 v148; // ax
  __int64 v149; // rdi
  __int64 v150; // rax
  __int64 v151; // rdi
  __int64 v152; // rax
  __int16 v153; // ax
  __int64 v154; // rdi
  __int64 v155; // rax
  __int16 v156; // ax
  __int64 v157; // rdi
  __int64 v158; // rax
  __int16 v159; // ax
  __int64 v160; // rdi
  __int64 v161; // rax
  bool v162; // zf
  __int64 v163; // rax
  __int64 v164; // rcx
  unsigned __int8 (__fastcall ***SQLFEModeInspector)(_QWORD); // rax
  const wchar_t *v166; // rcx
  __int64 v167; // rax
  int v168; // ecx
  char v169; // al
  __int64 v170; // rax
  char *v171; // r8
  __int64 v172; // rdx
  unsigned int v173; // r12d
  __int64 v174; // rdx
  unsigned int j; // r13d
  __int64 v176; // rsi
  __int64 v177; // rdi
  __int64 v178; // rax
  __int64 v179; // rdx
  struct CSessionTraceFlags **v180; // rax
  __int64 v181; // rdx
  struct CSessionTraceFlags **v182; // rax
  struct CSessionTraceFlags *v183; // rcx
  int v184; // eax
  char v185; // al
  bool v186; // al
  char v187; // cl
  char v188; // al
  char v189; // al
  char v190; // cl
  __int64 v191; // rdi
  struct Worker *v192; // rcx
  unsigned int k; // r12d
  __int64 v194; // rcx
  unsigned int v195; // edx
  VARIANTARG *v196; // r13
  VARIANTARG *v197; // rdi
  __int64 v198; // rsi
  bool v199; // al
  int v200; // esi
  __int64 v201; // rdi
  __int64 v202; // rax
  __int64 v203; // rdi
  __int64 v204; // rax
  void **v205; // rcx
  __int64 v206; // rdi
  __int64 v207; // rax
  __int64 v208; // rdi
  __int64 v209; // rax
  __int64 v210; // rdi
  __int64 v211; // rax
  char *v212; // r12
  unsigned int v213; // esi
  __int64 v214; // rax
  char *v215; // rdx
  int v216; // eax
  __int64 v217; // rdi
  __int64 v218; // rax
  __int64 v219; // rdi
  __int64 v220; // rax
  __int64 v221; // rdi
  __int64 v222; // rax
  __int64 v223; // rax
  struct CSessionTraceFlags *v224; // rcx
  int v225; // eax
  __int64 v226; // rdi
  struct Worker *v227; // rcx
  unsigned int v228; // r12d
  unsigned int v229; // edi
  _DWORD *v230; // r13
  _DWORD *v231; // rsi
  struct IUnknown *v232; // rcx
  bool v233; // al
  int v234; // edi
  _WORD **v235; // rdx
  __int64 v236; // rsi
  __int64 v237; // rdi
  IErrorReportingManager *ErrorReportingManager; // rax
  __int64 v239; // rax
  __int64 v240; // rsi
  __int64 v241; // rdi
  IErrorReportingManager *v242; // rax
  __int64 v243; // rsi
  __int64 v244; // rdi
  IErrorReportingManager *v245; // rax
  _WORD *v246; // rcx
  __int64 v247; // rax
  __int64 v248; // rsi
  __int64 v249; // rdi
  IErrorReportingManager *v250; // rax
  __int16 v251; // cx
  __int64 v252; // rsi
  __int64 v253; // rdi
  IErrorReportingManager *v254; // rax
  _WORD *v255; // rcx
  __int64 v256; // rax
  __int64 v257; // rsi
  __int64 v258; // rdi
  IErrorReportingManager *v259; // rax
  void *v260; // rcx
  __int64 v261; // rcx
  struct IUnknown *v262; // rcx
  __int64 v263; // [rsp+40h] [rbp-D908h]
  __int64 v264; // [rsp+40h] [rbp-D908h]
  __int64 v265; // [rsp+40h] [rbp-D908h]
  __int64 v266; // [rsp+40h] [rbp-D908h]
  int v267; // [rsp+48h] [rbp-D900h]
  unsigned int v268; // [rsp+50h] [rbp-D8F8h]
  __int64 v269; // [rsp+50h] [rbp-D8F8h]
  unsigned int v270; // [rsp+58h] [rbp-D8F0h] BYREF
  unsigned int v271; // [rsp+5Ch] [rbp-D8ECh]
  unsigned int v272; // [rsp+60h] [rbp-D8E8h]
  char v273; // [rsp+64h] [rbp-D8E4h]
  char v274; // [rsp+65h] [rbp-D8E3h]
  char v275; // [rsp+66h] [rbp-D8E2h]
  int v276; // [rsp+68h] [rbp-D8E0h]
  char *v277; // [rsp+70h] [rbp-D8D8h] BYREF
  char v278; // [rsp+78h] [rbp-D8D0h]
  char v279; // [rsp+79h] [rbp-D8CFh]
  char v280; // [rsp+7Ah] [rbp-D8CEh]
  char v281; // [rsp+7Bh] [rbp-D8CDh]
  char v282; // [rsp+7Ch] [rbp-D8CCh]
  int v283; // [rsp+80h] [rbp-D8C8h]
  _DWORD *v284; // [rsp+88h] [rbp-D8C0h] BYREF
  int v285; // [rsp+90h] [rbp-D8B8h]
  void **v286; // [rsp+98h] [rbp-D8B0h] BYREF
  char v287; // [rsp+A0h] [rbp-D8A8h]
  struct IUnknown *v289; // [rsp+A8h] [rbp-D8A0h] BYREF
  int v290; // [rsp+B0h] [rbp-D898h]
  int v291; // [rsp+B4h] [rbp-D894h]
  int v292; // [rsp+B8h] [rbp-D890h]
  _DWORD *v293; // [rsp+C0h] [rbp-D888h]
  __int64 v294; // [rsp+C8h] [rbp-D880h] BYREF
  struct IUnknown *v295; // [rsp+D0h] [rbp-D878h]
  void *v296; // [rsp+D8h] [rbp-D870h] BYREF
  int v297; // [rsp+E4h] [rbp-D864h] BYREF
  int v298; // [rsp+E8h] [rbp-D860h]
  int v299; // [rsp+ECh] [rbp-D85Ch]
  int v300; // [rsp+F0h] [rbp-D858h]
  int v301; // [rsp+F4h] [rbp-D854h]
  int v302; // [rsp+F8h] [rbp-D850h] BYREF
  int v303; // [rsp+FCh] [rbp-D84Ch] BYREF
  unsigned int v304; // [rsp+100h] [rbp-D848h] BYREF
  struct CSessionTraceFlags *v305; // [rsp+108h] [rbp-D840h]
  COledbConnect *v306; // [rsp+110h] [rbp-D838h]
  struct OLEDB_PROPCONN *v307; // [rsp+118h] [rbp-D830h]
  void *v308; // [rsp+120h] [rbp-D828h] BYREF
  struct IUnknown *v309; // [rsp+128h] [rbp-D820h]
  _DWORD *v310; // [rsp+130h] [rbp-D818h]
  char v311[4]; // [rsp+138h] [rbp-D810h] BYREF
  char v312[4]; // [rsp+13Ch] [rbp-D80Ch] BYREF
  struct OLEDB_PROPCONN *v313; // [rsp+140h] [rbp-D808h]
  _QWORD v314[2]; // [rsp+150h] [rbp-D7F8h] BYREF
  int v315; // [rsp+160h] [rbp-D7E8h]
  __int64 v316; // [rsp+168h] [rbp-D7E0h]
  __int64 v317; // [rsp+170h] [rbp-D7D8h]
  void *v318; // [rsp+178h] [rbp-D7D0h]
  __int64 v319; // [rsp+180h] [rbp-D7C8h]
  int v320; // [rsp+188h] [rbp-D7C0h]
  int v321; // [rsp+18Ch] [rbp-D7BCh]
  __int64 v322; // [rsp+190h] [rbp-D7B8h]
  int v323; // [rsp+198h] [rbp-D7B0h]
  char v324; // [rsp+19Ch] [rbp-D7ACh]
  __int64 v325; // [rsp+1A0h] [rbp-D7A8h]
  __int64 v326; // [rsp+1A8h] [rbp-D7A0h]
  _QWORD v327[2]; // [rsp+1B0h] [rbp-D798h] BYREF
  int v328; // [rsp+1C0h] [rbp-D788h]
  __int64 v329; // [rsp+1C8h] [rbp-D780h]
  __int64 v330; // [rsp+1D0h] [rbp-D778h]
  void *v331; // [rsp+1D8h] [rbp-D770h]
  __int64 v332; // [rsp+1E0h] [rbp-D768h]
  int v333; // [rsp+1E8h] [rbp-D760h]
  int v334; // [rsp+1ECh] [rbp-D75Ch]
  __int64 v335; // [rsp+1F0h] [rbp-D758h]
  int v336; // [rsp+1F8h] [rbp-D750h]
  char v337; // [rsp+1FCh] [rbp-D74Ch]
  _QWORD v338[2]; // [rsp+200h] [rbp-D748h] BYREF
  int v339; // [rsp+210h] [rbp-D738h]
  __int64 v340; // [rsp+218h] [rbp-D730h]
  __int64 v341; // [rsp+220h] [rbp-D728h]
  void *v342; // [rsp+228h] [rbp-D720h]
  __int64 v343; // [rsp+230h] [rbp-D718h]
  int v344; // [rsp+238h] [rbp-D710h]
  int v345; // [rsp+23Ch] [rbp-D70Ch]
  __int64 v346; // [rsp+240h] [rbp-D708h]
  int v347; // [rsp+248h] [rbp-D700h]
  char v348; // [rsp+24Ch] [rbp-D6FCh]
  _QWORD v349[2]; // [rsp+250h] [rbp-D6F8h] BYREF
  int v350; // [rsp+260h] [rbp-D6E8h]
  __int64 v351; // [rsp+268h] [rbp-D6E0h]
  __int64 v352; // [rsp+270h] [rbp-D6D8h]
  void *v353; // [rsp+278h] [rbp-D6D0h]
  int v354; // [rsp+280h] [rbp-D6C8h]
  _DWORD v355[6]; // [rsp+284h] [rbp-D6C4h] BYREF
  char v356; // [rsp+29Ch] [rbp-D6ACh]
  _QWORD v357[2]; // [rsp+2A0h] [rbp-D6A8h] BYREF
  int v358; // [rsp+2B0h] [rbp-D698h]
  __int64 v359; // [rsp+2B8h] [rbp-D690h]
  __int64 v360; // [rsp+2C0h] [rbp-D688h]
  void *v361; // [rsp+2C8h] [rbp-D680h]
  int v362; // [rsp+2D0h] [rbp-D678h]
  _DWORD v363[6]; // [rsp+2D4h] [rbp-D674h] BYREF
  char v364; // [rsp+2ECh] [rbp-D65Ch]
  _QWORD v365[2]; // [rsp+2F0h] [rbp-D658h] BYREF
  int v366; // [rsp+300h] [rbp-D648h]
  __int64 v367; // [rsp+308h] [rbp-D640h]
  __int64 v368; // [rsp+310h] [rbp-D638h]
  void *v369; // [rsp+318h] [rbp-D630h]
  int v370; // [rsp+320h] [rbp-D628h]
  _DWORD v371[6]; // [rsp+324h] [rbp-D624h] BYREF
  char v372; // [rsp+33Ch] [rbp-D60Ch]
  _QWORD v373[2]; // [rsp+340h] [rbp-D608h] BYREF
  int v374; // [rsp+350h] [rbp-D5F8h]
  __int64 v375; // [rsp+358h] [rbp-D5F0h]
  __int64 v376; // [rsp+360h] [rbp-D5E8h]
  void *v377; // [rsp+368h] [rbp-D5E0h]
  int v378; // [rsp+370h] [rbp-D5D8h]
  _DWORD v379[6]; // [rsp+374h] [rbp-D5D4h] BYREF
  char v380; // [rsp+38Ch] [rbp-D5BCh]
  _QWORD v381[2]; // [rsp+390h] [rbp-D5B8h] BYREF
  int v382; // [rsp+3A0h] [rbp-D5A8h]
  __int64 v383; // [rsp+3A8h] [rbp-D5A0h]
  __int64 v384; // [rsp+3B0h] [rbp-D598h]
  void *v385; // [rsp+3B8h] [rbp-D590h]
  int v386; // [rsp+3C0h] [rbp-D588h]
  _DWORD v387[6]; // [rsp+3C4h] [rbp-D584h] BYREF
  char v388; // [rsp+3DCh] [rbp-D56Ch]
  _QWORD v389[2]; // [rsp+3E0h] [rbp-D568h] BYREF
  int v390; // [rsp+3F0h] [rbp-D558h]
  __int64 v391; // [rsp+3F8h] [rbp-D550h]
  __int64 v392; // [rsp+400h] [rbp-D548h]
  void *v393; // [rsp+408h] [rbp-D540h]
  int v394; // [rsp+410h] [rbp-D538h]
  _DWORD v395[6]; // [rsp+414h] [rbp-D534h] BYREF
  char v396; // [rsp+42Ch] [rbp-D51Ch]
  _QWORD v397[2]; // [rsp+430h] [rbp-D518h] BYREF
  int v398; // [rsp+440h] [rbp-D508h]
  __int64 v399; // [rsp+448h] [rbp-D500h]
  __int64 v400; // [rsp+450h] [rbp-D4F8h]
  void *v401; // [rsp+458h] [rbp-D4F0h]
  int v402; // [rsp+460h] [rbp-D4E8h]
  _DWORD v403[6]; // [rsp+464h] [rbp-D4E4h] BYREF
  char v404; // [rsp+47Ch] [rbp-D4CCh]
  _QWORD v405[2]; // [rsp+480h] [rbp-D4C8h] BYREF
  int v406; // [rsp+490h] [rbp-D4B8h]
  __int64 v407; // [rsp+498h] [rbp-D4B0h]
  __int64 v408; // [rsp+4A0h] [rbp-D4A8h]
  void *v409; // [rsp+4A8h] [rbp-D4A0h]
  int v410; // [rsp+4B0h] [rbp-D498h]
  _DWORD v411[6]; // [rsp+4B4h] [rbp-D494h] BYREF
  char v412; // [rsp+4CCh] [rbp-D47Ch]
  _QWORD v413[2]; // [rsp+4D0h] [rbp-D478h] BYREF
  int v414; // [rsp+4E0h] [rbp-D468h]
  __int64 v415; // [rsp+4E8h] [rbp-D460h]
  __int64 v416; // [rsp+4F0h] [rbp-D458h]
  void *v417; // [rsp+4F8h] [rbp-D450h]
  int v418; // [rsp+500h] [rbp-D448h]
  _DWORD v419[6]; // [rsp+504h] [rbp-D444h] BYREF
  char v420; // [rsp+51Ch] [rbp-D42Ch]
  _QWORD v421[2]; // [rsp+520h] [rbp-D428h] BYREF
  int v422; // [rsp+530h] [rbp-D418h]
  __int64 v423; // [rsp+538h] [rbp-D410h]
  __int64 v424; // [rsp+540h] [rbp-D408h]
  void *v425; // [rsp+548h] [rbp-D400h]
  int v426; // [rsp+550h] [rbp-D3F8h]
  _DWORD v427[6]; // [rsp+554h] [rbp-D3F4h] BYREF
  char v428; // [rsp+56Ch] [rbp-D3DCh]
  _QWORD v429[2]; // [rsp+570h] [rbp-D3D8h] BYREF
  int v430; // [rsp+580h] [rbp-D3C8h]
  __int64 v431; // [rsp+588h] [rbp-D3C0h]
  __int64 v432; // [rsp+590h] [rbp-D3B8h]
  void *v433; // [rsp+598h] [rbp-D3B0h]
  int v434; // [rsp+5A0h] [rbp-D3A8h]
  _DWORD v435[6]; // [rsp+5A4h] [rbp-D3A4h] BYREF
  char v436; // [rsp+5BCh] [rbp-D38Ch]
  _QWORD v437[2]; // [rsp+5C0h] [rbp-D388h] BYREF
  int v438; // [rsp+5D0h] [rbp-D378h]
  __int64 v439; // [rsp+5D8h] [rbp-D370h]
  __int64 v440; // [rsp+5E0h] [rbp-D368h]
  void *v441; // [rsp+5E8h] [rbp-D360h]
  int v442; // [rsp+5F0h] [rbp-D358h]
  _DWORD v443[6]; // [rsp+5F4h] [rbp-D354h] BYREF
  char v444; // [rsp+60Ch] [rbp-D33Ch]
  _QWORD v445[2]; // [rsp+610h] [rbp-D338h] BYREF
  int v446; // [rsp+620h] [rbp-D328h]
  __int64 v447; // [rsp+628h] [rbp-D320h]
  __int64 v448; // [rsp+630h] [rbp-D318h]
  void *v449; // [rsp+638h] [rbp-D310h]
  int v450; // [rsp+640h] [rbp-D308h]
  _DWORD v451[6]; // [rsp+644h] [rbp-D304h] BYREF
  char v452; // [rsp+65Ch] [rbp-D2ECh]
  _QWORD v453[2]; // [rsp+660h] [rbp-D2E8h] BYREF
  int v454; // [rsp+670h] [rbp-D2D8h]
  __int64 v455; // [rsp+678h] [rbp-D2D0h]
  __int64 v456; // [rsp+680h] [rbp-D2C8h]
  void *v457; // [rsp+688h] [rbp-D2C0h]
  int v458; // [rsp+690h] [rbp-D2B8h]
  _DWORD v459[6]; // [rsp+694h] [rbp-D2B4h] BYREF
  char v460; // [rsp+6ACh] [rbp-D29Ch]
  _QWORD v461[2]; // [rsp+6B0h] [rbp-D298h] BYREF
  int v462; // [rsp+6C0h] [rbp-D288h]
  __int64 v463; // [rsp+6C8h] [rbp-D280h]
  __int64 v464; // [rsp+6D0h] [rbp-D278h]
  void *v465; // [rsp+6D8h] [rbp-D270h]
  int v466; // [rsp+6E0h] [rbp-D268h]
  _DWORD v467[6]; // [rsp+6E4h] [rbp-D264h] BYREF
  char v468; // [rsp+6FCh] [rbp-D24Ch]
  _QWORD v469[2]; // [rsp+700h] [rbp-D248h] BYREF
  int v470; // [rsp+710h] [rbp-D238h]
  __int64 v471; // [rsp+718h] [rbp-D230h]
  __int64 v472; // [rsp+720h] [rbp-D228h]
  void *v473; // [rsp+728h] [rbp-D220h]
  int v474; // [rsp+730h] [rbp-D218h]
  _DWORD v475[6]; // [rsp+734h] [rbp-D214h] BYREF
  char v476; // [rsp+74Ch] [rbp-D1FCh]
  _QWORD v477[2]; // [rsp+750h] [rbp-D1F8h] BYREF
  int v478; // [rsp+760h] [rbp-D1E8h]
  __int64 v479; // [rsp+768h] [rbp-D1E0h]
  __int64 v480; // [rsp+770h] [rbp-D1D8h]
  void *v481; // [rsp+778h] [rbp-D1D0h]
  int v482; // [rsp+780h] [rbp-D1C8h]
  _DWORD v483[6]; // [rsp+784h] [rbp-D1C4h] BYREF
  char v484; // [rsp+79Ch] [rbp-D1ACh]
  _QWORD v485[2]; // [rsp+7A0h] [rbp-D1A8h] BYREF
  int v486; // [rsp+7B0h] [rbp-D198h]
  __int64 v487; // [rsp+7B8h] [rbp-D190h]
  __int64 v488; // [rsp+7C0h] [rbp-D188h]
  void *v489; // [rsp+7C8h] [rbp-D180h]
  int v490; // [rsp+7D0h] [rbp-D178h]
  _DWORD v491[6]; // [rsp+7D4h] [rbp-D174h] BYREF
  char v492; // [rsp+7ECh] [rbp-D15Ch]
  _QWORD v493[2]; // [rsp+7F0h] [rbp-D158h] BYREF
  int v494; // [rsp+800h] [rbp-D148h]
  __int64 v495; // [rsp+808h] [rbp-D140h]
  __int64 v496; // [rsp+810h] [rbp-D138h]
  _DWORD *v497; // [rsp+818h] [rbp-D130h]
  int v498; // [rsp+820h] [rbp-D128h]
  _DWORD v499[6]; // [rsp+824h] [rbp-D124h] BYREF
  char v500; // [rsp+83Ch] [rbp-D10Ch]
  _QWORD v501[2]; // [rsp+840h] [rbp-D108h] BYREF
  int v502; // [rsp+850h] [rbp-D0F8h]
  __int64 v503; // [rsp+858h] [rbp-D0F0h]
  __int64 v504; // [rsp+860h] [rbp-D0E8h]
  void *v505; // [rsp+868h] [rbp-D0E0h]
  int v506; // [rsp+870h] [rbp-D0D8h]
  _DWORD v507[6]; // [rsp+874h] [rbp-D0D4h] BYREF
  char v508; // [rsp+88Ch] [rbp-D0BCh]
  _QWORD v509[2]; // [rsp+890h] [rbp-D0B8h] BYREF
  int v510; // [rsp+8A0h] [rbp-D0A8h]
  __int64 v511; // [rsp+8A8h] [rbp-D0A0h]
  __int64 v512; // [rsp+8B0h] [rbp-D098h]
  void *v513; // [rsp+8B8h] [rbp-D090h]
  int v514; // [rsp+8C0h] [rbp-D088h]
  _DWORD v515[6]; // [rsp+8C4h] [rbp-D084h] BYREF
  char v516; // [rsp+8DCh] [rbp-D06Ch]
  _QWORD v517[2]; // [rsp+8E0h] [rbp-D068h] BYREF
  int v518; // [rsp+8F0h] [rbp-D058h]
  __int64 v519; // [rsp+8F8h] [rbp-D050h]
  __int64 v520; // [rsp+900h] [rbp-D048h]
  void *v521; // [rsp+908h] [rbp-D040h]
  int v522; // [rsp+910h] [rbp-D038h]
  _DWORD v523[6]; // [rsp+914h] [rbp-D034h] BYREF
  char v524; // [rsp+92Ch] [rbp-D01Ch]
  _QWORD v525[2]; // [rsp+930h] [rbp-D018h] BYREF
  int v526; // [rsp+940h] [rbp-D008h]
  __int64 v527; // [rsp+948h] [rbp-D000h]
  __int64 v528; // [rsp+950h] [rbp-CFF8h]
  void *v529; // [rsp+958h] [rbp-CFF0h]
  int v530; // [rsp+960h] [rbp-CFE8h]
  _DWORD v531[6]; // [rsp+964h] [rbp-CFE4h] BYREF
  char v532; // [rsp+97Ch] [rbp-CFCCh]
  _QWORD v533[2]; // [rsp+980h] [rbp-CFC8h] BYREF
  int v534; // [rsp+990h] [rbp-CFB8h]
  __int64 v535; // [rsp+998h] [rbp-CFB0h]
  __int64 v536; // [rsp+9A0h] [rbp-CFA8h]
  void *v537; // [rsp+9A8h] [rbp-CFA0h]
  int v538; // [rsp+9B0h] [rbp-CF98h]
  _DWORD v539[6]; // [rsp+9B4h] [rbp-CF94h] BYREF
  char v540; // [rsp+9CCh] [rbp-CF7Ch]
  _QWORD v541[2]; // [rsp+9D0h] [rbp-CF78h] BYREF
  int v542; // [rsp+9E0h] [rbp-CF68h]
  __int64 v543; // [rsp+9E8h] [rbp-CF60h]
  __int64 v544; // [rsp+9F0h] [rbp-CF58h]
  void *v545; // [rsp+9F8h] [rbp-CF50h]
  int v546; // [rsp+A00h] [rbp-CF48h]
  _DWORD v547[6]; // [rsp+A04h] [rbp-CF44h] BYREF
  char v548; // [rsp+A1Ch] [rbp-CF2Ch]
  _QWORD v549[2]; // [rsp+A20h] [rbp-CF28h] BYREF
  int v550; // [rsp+A30h] [rbp-CF18h]
  __int64 v551; // [rsp+A38h] [rbp-CF10h]
  __int64 v552; // [rsp+A40h] [rbp-CF08h]
  void *v553; // [rsp+A48h] [rbp-CF00h]
  int v554; // [rsp+A50h] [rbp-CEF8h]
  _DWORD v555[6]; // [rsp+A54h] [rbp-CEF4h] BYREF
  char v556; // [rsp+A6Ch] [rbp-CEDCh]
  _QWORD v557[2]; // [rsp+A70h] [rbp-CED8h] BYREF
  int v558; // [rsp+A80h] [rbp-CEC8h]
  __int64 v559; // [rsp+A88h] [rbp-CEC0h]
  __int64 v560; // [rsp+A90h] [rbp-CEB8h]
  void *v561; // [rsp+A98h] [rbp-CEB0h]
  int v562; // [rsp+AA0h] [rbp-CEA8h]
  _DWORD v563[6]; // [rsp+AA4h] [rbp-CEA4h] BYREF
  char v564; // [rsp+ABCh] [rbp-CE8Ch]
  _QWORD v565[2]; // [rsp+AC0h] [rbp-CE88h] BYREF
  int v566; // [rsp+AD0h] [rbp-CE78h]
  __int64 v567; // [rsp+AD8h] [rbp-CE70h]
  __int64 v568; // [rsp+AE0h] [rbp-CE68h]
  void *v569; // [rsp+AE8h] [rbp-CE60h]
  int v570; // [rsp+AF0h] [rbp-CE58h]
  _DWORD v571[6]; // [rsp+AF4h] [rbp-CE54h] BYREF
  char v572; // [rsp+B0Ch] [rbp-CE3Ch]
  _QWORD v573[2]; // [rsp+B10h] [rbp-CE38h] BYREF
  int v574; // [rsp+B20h] [rbp-CE28h]
  __int64 v575; // [rsp+B28h] [rbp-CE20h]
  __int64 v576; // [rsp+B30h] [rbp-CE18h]
  void *v577; // [rsp+B38h] [rbp-CE10h]
  int v578; // [rsp+B40h] [rbp-CE08h]
  _DWORD v579[6]; // [rsp+B44h] [rbp-CE04h] BYREF
  char v580; // [rsp+B5Ch] [rbp-CDECh]
  _QWORD v581[2]; // [rsp+B60h] [rbp-CDE8h] BYREF
  int v582; // [rsp+B70h] [rbp-CDD8h]
  __int64 v583; // [rsp+B78h] [rbp-CDD0h]
  __int64 v584; // [rsp+B80h] [rbp-CDC8h]
  void *v585; // [rsp+B88h] [rbp-CDC0h]
  int v586; // [rsp+B90h] [rbp-CDB8h]
  _DWORD v587[6]; // [rsp+B94h] [rbp-CDB4h] BYREF
  char v588; // [rsp+BACh] [rbp-CD9Ch]
  _QWORD v589[2]; // [rsp+BB0h] [rbp-CD98h] BYREF
  int v590; // [rsp+BC0h] [rbp-CD88h]
  __int64 v591; // [rsp+BC8h] [rbp-CD80h]
  __int64 v592; // [rsp+BD0h] [rbp-CD78h]
  void *v593; // [rsp+BD8h] [rbp-CD70h]
  int v594; // [rsp+BE0h] [rbp-CD68h]
  _DWORD v595[6]; // [rsp+BE4h] [rbp-CD64h] BYREF
  char v596; // [rsp+BFCh] [rbp-CD4Ch]
  _QWORD v597[2]; // [rsp+C00h] [rbp-CD48h] BYREF
  int v598; // [rsp+C10h] [rbp-CD38h]
  __int64 v599; // [rsp+C18h] [rbp-CD30h]
  __int64 v600; // [rsp+C20h] [rbp-CD28h]
  void *v601; // [rsp+C28h] [rbp-CD20h]
  int v602; // [rsp+C30h] [rbp-CD18h]
  _DWORD v603[6]; // [rsp+C34h] [rbp-CD14h] BYREF
  char v604; // [rsp+C4Ch] [rbp-CCFCh]
  _QWORD v605[2]; // [rsp+C50h] [rbp-CCF8h] BYREF
  int v606; // [rsp+C60h] [rbp-CCE8h]
  __int64 v607; // [rsp+C68h] [rbp-CCE0h]
  __int64 v608; // [rsp+C70h] [rbp-CCD8h]
  void *v609; // [rsp+C78h] [rbp-CCD0h]
  int v610; // [rsp+C80h] [rbp-CCC8h]
  _DWORD v611[6]; // [rsp+C84h] [rbp-CCC4h] BYREF
  char v612; // [rsp+C9Ch] [rbp-CCACh]
  _QWORD v613[2]; // [rsp+CA0h] [rbp-CCA8h] BYREF
  int v614; // [rsp+CB0h] [rbp-CC98h]
  __int64 v615; // [rsp+CB8h] [rbp-CC90h]
  __int64 v616; // [rsp+CC0h] [rbp-CC88h]
  void *v617; // [rsp+CC8h] [rbp-CC80h]
  int v618; // [rsp+CD0h] [rbp-CC78h]
  _DWORD v619[6]; // [rsp+CD4h] [rbp-CC74h] BYREF
  char v620; // [rsp+CECh] [rbp-CC5Ch]
  _QWORD v621[2]; // [rsp+CF0h] [rbp-CC58h] BYREF
  int v622; // [rsp+D00h] [rbp-CC48h]
  __int64 v623; // [rsp+D08h] [rbp-CC40h]
  __int64 v624; // [rsp+D10h] [rbp-CC38h]
  void *v625; // [rsp+D18h] [rbp-CC30h]
  int v626; // [rsp+D20h] [rbp-CC28h]
  _DWORD v627[6]; // [rsp+D24h] [rbp-CC24h] BYREF
  char v628; // [rsp+D3Ch] [rbp-CC0Ch]
  _QWORD v629[2]; // [rsp+D40h] [rbp-CC08h] BYREF
  int v630; // [rsp+D50h] [rbp-CBF8h]
  __int64 v631; // [rsp+D58h] [rbp-CBF0h]
  __int64 v632; // [rsp+D60h] [rbp-CBE8h]
  void *v633; // [rsp+D68h] [rbp-CBE0h]
  int v634; // [rsp+D70h] [rbp-CBD8h]
  _DWORD v635[6]; // [rsp+D74h] [rbp-CBD4h] BYREF
  char v636; // [rsp+D8Ch] [rbp-CBBCh]
  _QWORD v637[2]; // [rsp+D90h] [rbp-CBB8h] BYREF
  int v638; // [rsp+DA0h] [rbp-CBA8h]
  __int64 v639; // [rsp+DA8h] [rbp-CBA0h]
  __int64 v640; // [rsp+DB0h] [rbp-CB98h]
  void *v641; // [rsp+DB8h] [rbp-CB90h]
  int v642; // [rsp+DC0h] [rbp-CB88h]
  _DWORD v643[6]; // [rsp+DC4h] [rbp-CB84h] BYREF
  char v644; // [rsp+DDCh] [rbp-CB6Ch]
  _QWORD v645[2]; // [rsp+DE0h] [rbp-CB68h] BYREF
  int v646; // [rsp+DF0h] [rbp-CB58h]
  __int64 v647; // [rsp+DF8h] [rbp-CB50h]
  __int64 v648; // [rsp+E00h] [rbp-CB48h]
  void *v649; // [rsp+E08h] [rbp-CB40h]
  int v650; // [rsp+E10h] [rbp-CB38h]
  _DWORD v651[6]; // [rsp+E14h] [rbp-CB34h] BYREF
  char v652; // [rsp+E2Ch] [rbp-CB1Ch]
  _QWORD v653[2]; // [rsp+E30h] [rbp-CB18h] BYREF
  int v654; // [rsp+E40h] [rbp-CB08h]
  __int64 v655; // [rsp+E48h] [rbp-CB00h]
  __int64 v656; // [rsp+E50h] [rbp-CAF8h]
  void *v657; // [rsp+E58h] [rbp-CAF0h]
  int v658; // [rsp+E60h] [rbp-CAE8h]
  _DWORD v659[6]; // [rsp+E64h] [rbp-CAE4h] BYREF
  char v660; // [rsp+E7Ch] [rbp-CACCh]
  _QWORD v661[2]; // [rsp+E80h] [rbp-CAC8h] BYREF
  int v662; // [rsp+E90h] [rbp-CAB8h]
  __int64 v663; // [rsp+E98h] [rbp-CAB0h]
  __int64 v664; // [rsp+EA0h] [rbp-CAA8h]
  void *v665; // [rsp+EA8h] [rbp-CAA0h]
  int v666; // [rsp+EB0h] [rbp-CA98h]
  _DWORD v667[6]; // [rsp+EB4h] [rbp-CA94h] BYREF
  char v668; // [rsp+ECCh] [rbp-CA7Ch]
  _QWORD v669[2]; // [rsp+ED0h] [rbp-CA78h] BYREF
  int v670; // [rsp+EE0h] [rbp-CA68h]
  __int64 v671; // [rsp+EE8h] [rbp-CA60h]
  __int64 v672; // [rsp+EF0h] [rbp-CA58h]
  void *v673; // [rsp+EF8h] [rbp-CA50h]
  int v674; // [rsp+F00h] [rbp-CA48h]
  _DWORD v675[6]; // [rsp+F04h] [rbp-CA44h] BYREF
  char v676; // [rsp+F1Ch] [rbp-CA2Ch]
  _QWORD v677[2]; // [rsp+F20h] [rbp-CA28h] BYREF
  int v678; // [rsp+F30h] [rbp-CA18h]
  __int64 v679; // [rsp+F38h] [rbp-CA10h]
  __int64 v680; // [rsp+F40h] [rbp-CA08h]
  void *v681; // [rsp+F48h] [rbp-CA00h]
  int v682; // [rsp+F50h] [rbp-C9F8h]
  _DWORD v683[6]; // [rsp+F54h] [rbp-C9F4h] BYREF
  char v684; // [rsp+F6Ch] [rbp-C9DCh]
  _QWORD v685[2]; // [rsp+F70h] [rbp-C9D8h] BYREF
  int v686; // [rsp+F80h] [rbp-C9C8h]
  __int64 v687; // [rsp+F88h] [rbp-C9C0h]
  __int64 v688; // [rsp+F90h] [rbp-C9B8h]
  void *v689; // [rsp+F98h] [rbp-C9B0h]
  int v690; // [rsp+FA0h] [rbp-C9A8h]
  _DWORD v691[6]; // [rsp+FA4h] [rbp-C9A4h] BYREF
  char v692; // [rsp+FBCh] [rbp-C98Ch]
  _QWORD v693[2]; // [rsp+FC0h] [rbp-C988h] BYREF
  int v694; // [rsp+FD0h] [rbp-C978h]
  __int64 v695; // [rsp+FD8h] [rbp-C970h]
  __int64 v696; // [rsp+FE0h] [rbp-C968h]
  void *v697; // [rsp+FE8h] [rbp-C960h]
  int v698; // [rsp+FF0h] [rbp-C958h]
  _DWORD v699[6]; // [rsp+FF4h] [rbp-C954h] BYREF
  char v700; // [rsp+100Ch] [rbp-C93Ch]
  _QWORD v701[2]; // [rsp+1010h] [rbp-C938h] BYREF
  int v702; // [rsp+1020h] [rbp-C928h]
  __int64 v703; // [rsp+1028h] [rbp-C920h]
  __int64 v704; // [rsp+1030h] [rbp-C918h]
  void *v705; // [rsp+1038h] [rbp-C910h]
  int v706; // [rsp+1040h] [rbp-C908h]
  _DWORD v707[6]; // [rsp+1044h] [rbp-C904h] BYREF
  char v708; // [rsp+105Ch] [rbp-C8ECh]
  _QWORD v709[2]; // [rsp+1060h] [rbp-C8E8h] BYREF
  int v710; // [rsp+1070h] [rbp-C8D8h]
  __int64 v711; // [rsp+1078h] [rbp-C8D0h]
  __int64 v712; // [rsp+1080h] [rbp-C8C8h]
  void *v713; // [rsp+1088h] [rbp-C8C0h]
  int v714; // [rsp+1090h] [rbp-C8B8h]
  _DWORD v715[6]; // [rsp+1094h] [rbp-C8B4h] BYREF
  char v716; // [rsp+10ACh] [rbp-C89Ch]
  _QWORD v717[2]; // [rsp+10B0h] [rbp-C898h] BYREF
  int v718; // [rsp+10C0h] [rbp-C888h]
  __int64 v719; // [rsp+10C8h] [rbp-C880h]
  __int64 v720; // [rsp+10D0h] [rbp-C878h]
  void *v721; // [rsp+10D8h] [rbp-C870h]
  int v722; // [rsp+10E0h] [rbp-C868h]
  _DWORD v723[6]; // [rsp+10E4h] [rbp-C864h] BYREF
  char v724; // [rsp+10FCh] [rbp-C84Ch]
  _QWORD v725[2]; // [rsp+1100h] [rbp-C848h] BYREF
  int v726; // [rsp+1110h] [rbp-C838h]
  __int64 v727; // [rsp+1118h] [rbp-C830h]
  __int64 v728; // [rsp+1120h] [rbp-C828h]
  void *v729; // [rsp+1128h] [rbp-C820h]
  int v730; // [rsp+1130h] [rbp-C818h]
  _DWORD v731[6]; // [rsp+1134h] [rbp-C814h] BYREF
  char v732; // [rsp+114Ch] [rbp-C7FCh]
  _QWORD v733[2]; // [rsp+1150h] [rbp-C7F8h] BYREF
  int v734; // [rsp+1160h] [rbp-C7E8h]
  __int64 v735; // [rsp+1168h] [rbp-C7E0h]
  __int64 v736; // [rsp+1170h] [rbp-C7D8h]
  void *v737; // [rsp+1178h] [rbp-C7D0h]
  int v738; // [rsp+1180h] [rbp-C7C8h]
  _DWORD v739[6]; // [rsp+1184h] [rbp-C7C4h] BYREF
  char v740; // [rsp+119Ch] [rbp-C7ACh]
  _QWORD v741[2]; // [rsp+11A0h] [rbp-C7A8h] BYREF
  int v742; // [rsp+11B0h] [rbp-C798h]
  __int64 v743; // [rsp+11B8h] [rbp-C790h]
  __int64 v744; // [rsp+11C0h] [rbp-C788h]
  void *v745; // [rsp+11C8h] [rbp-C780h]
  int v746; // [rsp+11D0h] [rbp-C778h]
  _DWORD v747[6]; // [rsp+11D4h] [rbp-C774h] BYREF
  char v748; // [rsp+11ECh] [rbp-C75Ch]
  _QWORD v749[2]; // [rsp+11F0h] [rbp-C758h] BYREF
  int v750; // [rsp+1200h] [rbp-C748h]
  __int64 v751; // [rsp+1208h] [rbp-C740h]
  __int64 v752; // [rsp+1210h] [rbp-C738h]
  void *v753; // [rsp+1218h] [rbp-C730h]
  int v754; // [rsp+1220h] [rbp-C728h]
  _DWORD v755[6]; // [rsp+1224h] [rbp-C724h] BYREF
  char v756; // [rsp+123Ch] [rbp-C70Ch]
  _QWORD v757[2]; // [rsp+1240h] [rbp-C708h] BYREF
  int v758; // [rsp+1250h] [rbp-C6F8h]
  __int64 v759; // [rsp+1258h] [rbp-C6F0h]
  __int64 v760; // [rsp+1260h] [rbp-C6E8h]
  void *v761; // [rsp+1268h] [rbp-C6E0h]
  int v762; // [rsp+1270h] [rbp-C6D8h]
  int v763; // [rsp+1274h] [rbp-C6D4h]
  int v764; // [rsp+1278h] [rbp-C6D0h]
  int v765; // [rsp+127Ch] [rbp-C6CCh]
  int v766; // [rsp+1280h] [rbp-C6C8h]
  int v767; // [rsp+1284h] [rbp-C6C4h]
  int v768; // [rsp+1288h] [rbp-C6C0h]
  char v769; // [rsp+128Ch] [rbp-C6BCh]
  _QWORD v770[2]; // [rsp+1290h] [rbp-C6B8h] BYREF
  int v771; // [rsp+12A0h] [rbp-C6A8h]
  __int64 v772; // [rsp+12A8h] [rbp-C6A0h]
  __int64 v773; // [rsp+12B0h] [rbp-C698h]
  void *v774; // [rsp+12B8h] [rbp-C690h]
  int v775; // [rsp+12C0h] [rbp-C688h]
  int v776; // [rsp+12C4h] [rbp-C684h]
  int v777; // [rsp+12C8h] [rbp-C680h]
  int v778; // [rsp+12CCh] [rbp-C67Ch]
  int v779; // [rsp+12D0h] [rbp-C678h]
  int v780; // [rsp+12D4h] [rbp-C674h]
  int v781; // [rsp+12D8h] [rbp-C670h]
  char v782; // [rsp+12DCh] [rbp-C66Ch]
  _QWORD v783[2]; // [rsp+12E0h] [rbp-C668h] BYREF
  int v784; // [rsp+12F0h] [rbp-C658h]
  __int64 v785; // [rsp+12F8h] [rbp-C650h]
  __int64 v786; // [rsp+1300h] [rbp-C648h]
  void *v787; // [rsp+1308h] [rbp-C640h]
  int v788; // [rsp+1310h] [rbp-C638h]
  int v789; // [rsp+1314h] [rbp-C634h]
  int v790; // [rsp+1318h] [rbp-C630h]
  int v791; // [rsp+131Ch] [rbp-C62Ch]
  int v792; // [rsp+1320h] [rbp-C628h]
  int v793; // [rsp+1324h] [rbp-C624h]
  int v794; // [rsp+1328h] [rbp-C620h]
  char v795; // [rsp+132Ch] [rbp-C61Ch]
  _QWORD v796[2]; // [rsp+1330h] [rbp-C618h] BYREF
  int v797; // [rsp+1340h] [rbp-C608h]
  __int64 v798; // [rsp+1348h] [rbp-C600h]
  __int64 v799; // [rsp+1350h] [rbp-C5F8h]
  void *v800; // [rsp+1358h] [rbp-C5F0h]
  int v801; // [rsp+1360h] [rbp-C5E8h]
  int v802; // [rsp+1364h] [rbp-C5E4h]
  int v803; // [rsp+1368h] [rbp-C5E0h]
  int v804; // [rsp+136Ch] [rbp-C5DCh]
  int v805; // [rsp+1370h] [rbp-C5D8h]
  int v806; // [rsp+1374h] [rbp-C5D4h]
  int v807; // [rsp+1378h] [rbp-C5D0h]
  char v808; // [rsp+137Ch] [rbp-C5CCh]
  _QWORD v809[2]; // [rsp+1380h] [rbp-C5C8h] BYREF
  int v810; // [rsp+1390h] [rbp-C5B8h]
  __int64 v811; // [rsp+1398h] [rbp-C5B0h]
  __int64 v812; // [rsp+13A0h] [rbp-C5A8h]
  void *v813; // [rsp+13A8h] [rbp-C5A0h]
  int v814; // [rsp+13B0h] [rbp-C598h]
  int v815; // [rsp+13B4h] [rbp-C594h]
  int v816; // [rsp+13B8h] [rbp-C590h]
  int v817; // [rsp+13BCh] [rbp-C58Ch]
  int v818; // [rsp+13C0h] [rbp-C588h]
  int v819; // [rsp+13C4h] [rbp-C584h]
  int v820; // [rsp+13C8h] [rbp-C580h]
  char v821; // [rsp+13CCh] [rbp-C57Ch]
  _QWORD v822[2]; // [rsp+13D0h] [rbp-C578h] BYREF
  int v823; // [rsp+13E0h] [rbp-C568h]
  __int64 v824; // [rsp+13E8h] [rbp-C560h]
  __int64 v825; // [rsp+13F0h] [rbp-C558h]
  void *v826; // [rsp+13F8h] [rbp-C550h]
  int v827; // [rsp+1400h] [rbp-C548h]
  int v828; // [rsp+1404h] [rbp-C544h]
  int v829; // [rsp+1408h] [rbp-C540h]
  int v830; // [rsp+140Ch] [rbp-C53Ch]
  int v831; // [rsp+1410h] [rbp-C538h]
  int v832; // [rsp+1414h] [rbp-C534h]
  int v833; // [rsp+1418h] [rbp-C530h]
  char v834; // [rsp+141Ch] [rbp-C52Ch]
  _QWORD v835[2]; // [rsp+1420h] [rbp-C528h] BYREF
  int v836; // [rsp+1430h] [rbp-C518h]
  __int64 v837; // [rsp+1438h] [rbp-C510h]
  __int64 v838; // [rsp+1440h] [rbp-C508h]
  void *v839; // [rsp+1448h] [rbp-C500h]
  int v840; // [rsp+1450h] [rbp-C4F8h]
  int v841; // [rsp+1454h] [rbp-C4F4h]
  int v842; // [rsp+1458h] [rbp-C4F0h]
  int v843; // [rsp+145Ch] [rbp-C4ECh]
  int v844; // [rsp+1460h] [rbp-C4E8h]
  int v845; // [rsp+1464h] [rbp-C4E4h]
  int v846; // [rsp+1468h] [rbp-C4E0h]
  char v847; // [rsp+146Ch] [rbp-C4DCh]
  __int64 v848; // [rsp+1470h] [rbp-C4D8h]
  GUID *v849; // [rsp+1478h] [rbp-C4D0h]
  int v850; // [rsp+1480h] [rbp-C4C8h]
  __int64 v851; // [rsp+1488h] [rbp-C4C0h]
  __int64 v852; // [rsp+1490h] [rbp-C4B8h]
  __int64 v853; // [rsp+1498h] [rbp-C4B0h]
  __int64 v854; // [rsp+14A0h] [rbp-C4A8h]
  int v855; // [rsp+14A8h] [rbp-C4A0h]
  int v856; // [rsp+14ACh] [rbp-C49Ch]
  __int64 v857; // [rsp+14B0h] [rbp-C498h]
  int v858; // [rsp+14B8h] [rbp-C490h]
  char v859; // [rsp+14BCh] [rbp-C48Ch]
  __int64 v860; // [rsp+14C0h] [rbp-C488h]
  GUID *v861; // [rsp+14C8h] [rbp-C480h]
  int v862; // [rsp+14D0h] [rbp-C478h]
  __int64 v863; // [rsp+14D8h] [rbp-C470h]
  __int64 v864; // [rsp+14E0h] [rbp-C468h]
  __int64 v865; // [rsp+14E8h] [rbp-C460h]
  __int64 v866; // [rsp+14F0h] [rbp-C458h]
  int v867; // [rsp+14F8h] [rbp-C450h]
  int v868; // [rsp+14FCh] [rbp-C44Ch]
  __int64 v869; // [rsp+1500h] [rbp-C448h]
  int v870; // [rsp+1508h] [rbp-C440h]
  char v871; // [rsp+150Ch] [rbp-C43Ch]
  __int64 v872; // [rsp+1510h] [rbp-C438h]
  GUID *v873; // [rsp+1518h] [rbp-C430h]
  int v874; // [rsp+1520h] [rbp-C428h]
  __int64 v875; // [rsp+1528h] [rbp-C420h]
  __int64 v876; // [rsp+1530h] [rbp-C418h]
  __int64 v877; // [rsp+1538h] [rbp-C410h]
  __int64 v878; // [rsp+1540h] [rbp-C408h]
  int v879; // [rsp+1548h] [rbp-C400h]
  int v880; // [rsp+154Ch] [rbp-C3FCh]
  __int64 v881; // [rsp+1550h] [rbp-C3F8h]
  int v882; // [rsp+1558h] [rbp-C3F0h]
  char v883; // [rsp+155Ch] [rbp-C3ECh]
  __int64 v884; // [rsp+1560h] [rbp-C3E8h]
  GUID *v885; // [rsp+1568h] [rbp-C3E0h]
  int v886; // [rsp+1570h] [rbp-C3D8h]
  __int64 v887; // [rsp+1578h] [rbp-C3D0h]
  __int64 v888; // [rsp+1580h] [rbp-C3C8h]
  __int64 v889; // [rsp+1588h] [rbp-C3C0h]
  __int64 v890; // [rsp+1590h] [rbp-C3B8h]
  int v891; // [rsp+1598h] [rbp-C3B0h]
  int v892; // [rsp+159Ch] [rbp-C3ACh]
  __int64 v893; // [rsp+15A0h] [rbp-C3A8h]
  int v894; // [rsp+15A8h] [rbp-C3A0h]
  char v895; // [rsp+15ACh] [rbp-C39Ch]
  __int64 v896; // [rsp+15B0h] [rbp-C398h]
  GUID *v897; // [rsp+15B8h] [rbp-C390h]
  int v898; // [rsp+15C0h] [rbp-C388h]
  __int64 v899; // [rsp+15C8h] [rbp-C380h]
  __int64 v900; // [rsp+15D0h] [rbp-C378h]
  __int64 v901; // [rsp+15D8h] [rbp-C370h]
  __int64 v902; // [rsp+15E0h] [rbp-C368h]
  int v903; // [rsp+15E8h] [rbp-C360h]
  int v904; // [rsp+15ECh] [rbp-C35Ch]
  __int64 v905; // [rsp+15F0h] [rbp-C358h]
  int v906; // [rsp+15F8h] [rbp-C350h]
  char v907; // [rsp+15FCh] [rbp-C34Ch]
  __int64 v908; // [rsp+1600h] [rbp-C348h]
  GUID *v909; // [rsp+1608h] [rbp-C340h]
  int v910; // [rsp+1610h] [rbp-C338h]
  __int64 v911; // [rsp+1618h] [rbp-C330h]
  __int64 v912; // [rsp+1620h] [rbp-C328h]
  __int64 v913; // [rsp+1628h] [rbp-C320h]
  __int64 v914; // [rsp+1630h] [rbp-C318h]
  int v915; // [rsp+1638h] [rbp-C310h]
  int v916; // [rsp+163Ch] [rbp-C30Ch]
  __int64 v917; // [rsp+1640h] [rbp-C308h]
  int v918; // [rsp+1648h] [rbp-C300h]
  char v919; // [rsp+164Ch] [rbp-C2FCh]
  _DWORD *v920; // [rsp+1650h] [rbp-C2F8h]
  void *v921; // [rsp+1658h] [rbp-C2F0h]
  char *v922; // [rsp+1660h] [rbp-C2E8h]
  _DWORD *v923; // [rsp+1668h] [rbp-C2E0h]
  void *v924; // [rsp+1670h] [rbp-C2D8h]
  _DWORD *v925; // [rsp+1678h] [rbp-C2D0h]
  void *v926; // [rsp+1680h] [rbp-C2C8h]
  char *v927; // [rsp+1688h] [rbp-C2C0h]
  _DWORD *v928; // [rsp+1690h] [rbp-C2B8h]
  void *v929; // [rsp+1698h] [rbp-C2B0h]
  _DWORD *v930; // [rsp+16A0h] [rbp-C2A8h]
  void *v931; // [rsp+16A8h] [rbp-C2A0h]
  _DWORD *v932; // [rsp+16B0h] [rbp-C298h]
  void *v933; // [rsp+16B8h] [rbp-C290h]
  _DWORD *v934; // [rsp+16C0h] [rbp-C288h]
  void *v935; // [rsp+16C8h] [rbp-C280h]
  _DWORD *v936; // [rsp+16D0h] [rbp-C278h]
  void *v937; // [rsp+16D8h] [rbp-C270h]
  _DWORD *v938; // [rsp+16E0h] [rbp-C268h]
  void *v939; // [rsp+16E8h] [rbp-C260h]
  _DWORD *v940; // [rsp+16F0h] [rbp-C258h]
  void *v941; // [rsp+16F8h] [rbp-C250h]
  _DWORD *v942; // [rsp+1700h] [rbp-C248h]
  void *v943; // [rsp+1708h] [rbp-C240h]
  _DWORD *v944; // [rsp+1710h] [rbp-C238h]
  void *v945; // [rsp+1718h] [rbp-C230h]
  _DWORD *v946; // [rsp+1720h] [rbp-C228h]
  void *v947; // [rsp+1728h] [rbp-C220h]
  _DWORD *v948; // [rsp+1730h] [rbp-C218h]
  void *v949; // [rsp+1738h] [rbp-C210h]
  _DWORD *v950; // [rsp+1740h] [rbp-C208h]
  void *v951; // [rsp+1748h] [rbp-C200h]
  _DWORD *v952; // [rsp+1750h] [rbp-C1F8h]
  void *v953; // [rsp+1758h] [rbp-C1F0h]
  _DWORD *v954; // [rsp+1760h] [rbp-C1E8h]
  void *v955; // [rsp+1768h] [rbp-C1E0h]
  _DWORD *v956; // [rsp+1770h] [rbp-C1D8h]
  void *v957; // [rsp+1778h] [rbp-C1D0h]
  _DWORD *v958; // [rsp+1780h] [rbp-C1C8h]
  void *v959; // [rsp+1788h] [rbp-C1C0h]
  _DWORD *v960; // [rsp+1790h] [rbp-C1B8h]
  void *v961; // [rsp+1798h] [rbp-C1B0h]
  _DWORD *v962; // [rsp+17A0h] [rbp-C1A8h]
  void *v963; // [rsp+17A8h] [rbp-C1A0h]
  _DWORD *v964; // [rsp+17B0h] [rbp-C198h]
  void *v965; // [rsp+17B8h] [rbp-C190h]
  _DWORD *v966; // [rsp+17C0h] [rbp-C188h]
  void *v967; // [rsp+17C8h] [rbp-C180h]
  _DWORD *v968; // [rsp+17D0h] [rbp-C178h]
  void *v969; // [rsp+17D8h] [rbp-C170h]
  _DWORD *v970; // [rsp+17E0h] [rbp-C168h]
  void *v971; // [rsp+17E8h] [rbp-C160h]
  _DWORD *v972; // [rsp+17F0h] [rbp-C158h]
  void *v973; // [rsp+17F8h] [rbp-C150h]
  _DWORD *v974; // [rsp+1800h] [rbp-C148h]
  void *v975; // [rsp+1808h] [rbp-C140h]
  char *v976; // [rsp+1810h] [rbp-C138h]
  void *v977; // [rsp+1818h] [rbp-C130h]
  _DWORD *v978; // [rsp+1820h] [rbp-C128h]
  void *v979; // [rsp+1828h] [rbp-C120h]
  _DWORD *v980; // [rsp+1830h] [rbp-C118h]
  void *v981; // [rsp+1838h] [rbp-C110h]
  _DWORD *v982; // [rsp+1840h] [rbp-C108h]
  void *v983; // [rsp+1848h] [rbp-C100h]
  _DWORD *v984; // [rsp+1850h] [rbp-C0F8h]
  void *v985; // [rsp+1858h] [rbp-C0F0h]
  _DWORD *v986; // [rsp+1860h] [rbp-C0E8h]
  void *v987; // [rsp+1868h] [rbp-C0E0h]
  _DWORD *v988; // [rsp+1870h] [rbp-C0D8h]
  void *v989; // [rsp+1878h] [rbp-C0D0h]
  _DWORD *v990; // [rsp+1880h] [rbp-C0C8h]
  void *v991; // [rsp+1888h] [rbp-C0C0h]
  _DWORD *v992; // [rsp+1890h] [rbp-C0B8h]
  void *v993; // [rsp+1898h] [rbp-C0B0h]
  char *v994; // [rsp+18A0h] [rbp-C0A8h]
  _DWORD *v995; // [rsp+18A8h] [rbp-C0A0h]
  void *v996; // [rsp+18B0h] [rbp-C098h]
  _DWORD *v997; // [rsp+18B8h] [rbp-C090h]
  void *v998; // [rsp+18C0h] [rbp-C088h]
  _DWORD *v999; // [rsp+18C8h] [rbp-C080h]
  void *v1000; // [rsp+18D0h] [rbp-C078h]
  _DWORD *v1001; // [rsp+18D8h] [rbp-C070h]
  void *v1002; // [rsp+18E0h] [rbp-C068h]
  _DWORD *v1003; // [rsp+18E8h] [rbp-C060h]
  void *v1004; // [rsp+18F0h] [rbp-C058h]
  _DWORD *v1005; // [rsp+18F8h] [rbp-C050h]
  void *v1006; // [rsp+1900h] [rbp-C048h]
  __int64 v1007; // [rsp+1908h] [rbp-C040h]
  const wchar_t *v1008; // [rsp+1910h] [rbp-C038h]
  void *v1009; // [rsp+1918h] [rbp-C030h]
  _DWORD *v1010; // [rsp+1920h] [rbp-C028h]
  char *v1011; // [rsp+1928h] [rbp-C020h]
  _DWORD *v1012; // [rsp+1930h] [rbp-C018h]
  void *v1013; // [rsp+1938h] [rbp-C010h]
  __int64 v1014; // [rsp+1940h] [rbp-C008h]
  _DWORD *v1015; // [rsp+1958h] [rbp-BFF0h]
  _DWORD *v1016; // [rsp+1960h] [rbp-BFE8h]
  void *v1017; // [rsp+1968h] [rbp-BFE0h]
  _DWORD *v1018; // [rsp+1970h] [rbp-BFD8h]
  _DWORD *v1019; // [rsp+1978h] [rbp-BFD0h]
  void *v1020; // [rsp+1980h] [rbp-BFC8h]
  _DWORD *v1021; // [rsp+1988h] [rbp-BFC0h]
  void *v1022; // [rsp+1990h] [rbp-BFB8h]
  char *v1023; // [rsp+1998h] [rbp-BFB0h]
  _DWORD *v1024; // [rsp+19B0h] [rbp-BF98h]
  void *v1025; // [rsp+19B8h] [rbp-BF90h]
  _DWORD *v1026; // [rsp+19C0h] [rbp-BF88h]
  void *v1027; // [rsp+19C8h] [rbp-BF80h]
  char *v1028; // [rsp+19D0h] [rbp-BF78h]
  _DWORD *v1029; // [rsp+19D8h] [rbp-BF70h]
  void *v1030; // [rsp+19E0h] [rbp-BF68h]
  int v1031; // [rsp+1A20h] [rbp-BF28h] BYREF
  __int64 v1032; // [rsp+1A28h] [rbp-BF20h]
  _DWORD v1033[2]; // [rsp+1A30h] [rbp-BF18h] BYREF
  __int64 v1034; // [rsp+1A38h] [rbp-BF10h]
  char v1035[64]; // [rsp+1A40h] [rbp-BF08h] BYREF
  int v1036; // [rsp+1A80h] [rbp-BEC8h] BYREF
  __int64 v1037; // [rsp+1A88h] [rbp-BEC0h]
  _DWORD v1038[2]; // [rsp+1A90h] [rbp-BEB8h] BYREF
  __int64 v1039; // [rsp+1A98h] [rbp-BEB0h]
  char v1040[64]; // [rsp+1AA0h] [rbp-BEA8h] BYREF
  int v1041; // [rsp+1AE0h] [rbp-BE68h] BYREF
  __int64 v1042; // [rsp+1AE8h] [rbp-BE60h]
  _DWORD v1043[2]; // [rsp+1AF0h] [rbp-BE58h] BYREF
  __int64 v1044; // [rsp+1AF8h] [rbp-BE50h]
  char v1045[64]; // [rsp+1B00h] [rbp-BE48h] BYREF
  int v1046; // [rsp+1B40h] [rbp-BE08h] BYREF
  __int64 v1047; // [rsp+1B48h] [rbp-BE00h]
  _DWORD v1048[2]; // [rsp+1B50h] [rbp-BDF8h] BYREF
  __int64 v1049; // [rsp+1B58h] [rbp-BDF0h]
  char v1050[64]; // [rsp+1B60h] [rbp-BDE8h] BYREF
  _DWORD *v1051; // [rsp+1BA0h] [rbp-BDA8h] BYREF
  int v1052; // [rsp+1BA8h] [rbp-BDA0h]
  GUID v1053; // [rsp+1BACh] [rbp-BD9Ch]
  _DWORD v1054[4]; // [rsp+1BC0h] [rbp-BD88h] BYREF
  _DWORD v1055[6]; // [rsp+1BD0h] [rbp-BD78h] BYREF
  _DWORD v1056[12]; // [rsp+1BE8h] [rbp-BD60h] BYREF
  _DWORD v1057[14]; // [rsp+1C18h] [rbp-BD30h] BYREF
  _DWORD v1058[20]; // [rsp+1C50h] [rbp-BCF8h] BYREF
  _DWORD *v1059; // [rsp+1CA0h] [rbp-BCA8h] BYREF
  int v1060; // [rsp+1CA8h] [rbp-BCA0h]
  GUID v1061; // [rsp+1CACh] [rbp-BC9Ch]
  _DWORD *v1062; // [rsp+1CC0h] [rbp-BC88h]
  int v1063; // [rsp+1CC8h] [rbp-BC80h]
  GUID v1064; // [rsp+1CCCh] [rbp-BC7Ch]
  _DWORD *v1065; // [rsp+1CE0h] [rbp-BC68h]
  int v1066; // [rsp+1CE8h] [rbp-BC60h]
  GUID v1067; // [rsp+1CECh] [rbp-BC5Ch]
  int *v1068; // [rsp+1D00h] [rbp-BC48h]
  int v1069; // [rsp+1D08h] [rbp-BC40h]
  GUID v1070; // [rsp+1D0Ch] [rbp-BC3Ch]
  wchar_t v1071[4008]; // [rsp+1D20h] [rbp-BC28h] BYREF
  wchar_t v1072[4008]; // [rsp+3C70h] [rbp-9CD8h] BYREF
  wchar_t v1073[4008]; // [rsp+5BC0h] [rbp-7D88h] BYREF
  wchar_t v1074[4008]; // [rsp+7B10h] [rbp-5E38h] BYREF
  wchar_t v1075[4008]; // [rsp+9A60h] [rbp-3EE8h] BYREF
  wchar_t v1076[4008]; // [rsp+B9B0h] [rbp-1F98h] BYREF

  v1014 = -2;
  v313 = a3;
  v306 = this;
  v307 = a3;
  v273 = 0;
  v274 = 0;
  v275 = 0;
  Interface = COledbConnect::GetInterface(this, &IID_IGetDataSource, a2, &IID_IUnknown, 1);
  v309 = Interface;
  v289 = 0;
  v6 = COledbConnect::FSupportsUms(this);
  SOS_Task::AutoSwitchPreemptive::AutoSwitchPreemptive(&v1031, 536871509, !v6);
  v7 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))Interface->lpVtbl[1].QueryInterface)(
         Interface,
         &IID_IUnknown,
         &v289);
  v305 = (struct CSessionTraceFlags *)v1033;
  if ( v1033[0] )
  {
    if ( v1033[1] )
      *(_DWORD *)(v1034 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v1034 + 608) + 16LL))(
        *(_QWORD *)(v1034 + 608),
        v1034,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)v1035);
  *(_DWORD *)(v1032 + 616) &= ~v1031;
  if ( v7 < 0 )
  {
    _mm_lfence();
    v8 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
    v9 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
    v314[0] = Interface;
    v314[1] = &IID_IGetDataSource;
    v315 = v7;
    v316 = v9;
    v317 = v8;
    v318 = 0;
    v319 = 0;
    v320 = 0;
    v321 = -1;
    v322 = 0;
    v323 = 0;
    v324 &= ~1u;
    if ( COledbError::FPrintSQLServerError((COledbError *)v314) )
      ex_raise(73, 7, 25, 1);
    COledbError::PrintMsgUsingHRESULT((COledbError *)v314);
    ex_raise(73, 7, 16, 1, v316, v317);
    operator delete[](v318);
  }
  v309 = 0;
  ((void (__fastcall *)(struct IUnknown *))Interface->lpVtbl->Release)(Interface);
  v1058[0] = 40;
  v1058[1] = 41;
  v1058[2] = 96;
  v1058[3] = 97;
  v1058[4] = 22;
  v1058[5] = 46;
  v1058[6] = 100;
  v1058[7] = 80;
  v1058[8] = 84;
  v1058[9] = 111;
  v1058[10] = 120;
  v1058[11] = 109;
  v1058[12] = 36;
  v1058[13] = 83;
  v1058[14] = 288;
  v1058[15] = 237;
  v1058[16] = 196;
  v1056[0] = 4;
  v1056[1] = 5;
  v1056[2] = 6;
  v1056[3] = 7;
  v1056[4] = 8;
  v1056[5] = 9;
  v1056[6] = 16;
  v1056[7] = 20;
  v1056[8] = 21;
  v1056[9] = 22;
  v1056[10] = 23;
  v1056[11] = 24;
  v1055[0] = 2;
  v1055[1] = 3;
  v1055[2] = 4;
  v1055[3] = 5;
  v1055[4] = 6;
  v1055[5] = 7;
  v297 = 16;
  v270 = 0;
  v277 = 0;
  v1059 = v1058;
  v1060 = 17;
  v1061 = DBPROPSET_DATASOURCEINFO;
  v1062 = v1056;
  v1063 = 12;
  v1064 = SQLPROPSET_OPTHINTS;
  v1065 = v1055;
  v1066 = 6;
  v1067 = DBPROPSET_SQLSERVERDATASOURCEINFO;
  v276 = 3;
  v1068 = &v297;
  v1069 = 1;
  v1070 = DBPROPSET_SQLSERVERDBINIT;
  v10 = COledbConnect::GetInterface(this, &IID_IDBProperties, v289, &IID_IUnknown, 1);
  v295 = v10;
  v11 = COledbConnect::FSupportsUms(this);
  SOS_Task::AutoSwitchPreemptive::AutoSwitchPreemptive(&v1036, 536871511, !v11);
  v12 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, _DWORD **, unsigned int *, char **))v10->lpVtbl[1].QueryInterface)(
          v10,
          4,
          &v1059,
          &v270,
          &v277);
  v305 = (struct CSessionTraceFlags *)v1038;
  if ( v1038[0] )
  {
    if ( v1038[1] )
      *(_DWORD *)(v1039 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v1039 + 608) + 16LL))(
        *(_QWORD *)(v1039 + 608),
        v1039,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)v1040);
  *(_DWORD *)(v1037 + 616) &= ~v1036;
  if ( (int)(v12 + 0x80000000) >= 0 && v12 != -2147217887 )
  {
    _mm_lfence();
    v13 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
    v14 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
    v338[0] = v10;
    v338[1] = &IID_IDBProperties;
    v339 = v12;
    v340 = v14;
    v341 = v13;
    v342 = 0;
    v343 = 0;
    v344 = 0;
    v345 = -1;
    v346 = 0;
    v347 = 0;
    v348 &= ~1u;
    if ( COledbError::FPrintSQLServerError((COledbError *)v338) )
      ex_raise(73, 72, 25, 1);
    COledbError::PrintMsgUsingHRESULT((COledbError *)v338);
    ex_raise(73, 72, 16, 2, v340, v341);
    operator delete[](v342);
  }
  if ( v270 != 4 )
  {
    v15 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
    v16 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
    v509[0] = 0;
    v509[1] = &IID_IUnknown;
    v510 = 0;
    v511 = v16;
    v512 = v15;
    v513 = 0;
    v514 = 0;
    v1019 = v515;
    v515[0] = 0;
    v515[1] = 0;
    v515[2] = -1;
    v515[3] = 0;
    v515[4] = 0;
    v515[5] = 0;
    v516 &= ~1u;
    COledbError::RaiseDataWarning((COledbError *)v509, L"number of property sets", L"4");
    v1020 = v513;
    operator delete[](v513);
  }
  if ( v277 )
    goto LABEL_22;
  v17 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
  v18 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
  v517[0] = 0;
  v517[1] = &IID_IUnknown;
  v518 = 0;
  v519 = v18;
  v520 = v17;
  v521 = 0;
  v522 = 0;
  v1021 = v523;
  v523[0] = 0;
  v523[1] = 0;
  v523[2] = -1;
  v523[3] = 0;
  v523[4] = 0;
  v523[5] = 0;
  v524 &= ~1u;
  COledbError::RaiseDataWarning((COledbError *)v517, L"property sets", L"not NULL");
  v1022 = v521;
  operator delete[](v521);
  if ( v277 )
  {
LABEL_22:
    if ( v270 )
    {
      v1023 = v277 + 12;
      if ( *(_QWORD *)(v277 + 12) != *(_QWORD *)&DBPROPSET_DATASOURCEINFO.Data1
        || *(_QWORD *)(v277 + 20) != *(_QWORD *)DBPROPSET_DATASOURCEINFO.Data4 )
      {
        v19 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
        v20 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
        v525[0] = 0;
        v525[1] = &IID_IUnknown;
        v526 = 0;
        v527 = v20;
        v528 = v19;
        v529 = 0;
        v530 = 0;
        v1024 = v531;
        v531[0] = 0;
        v531[1] = 0;
        v531[2] = -1;
        v531[3] = 0;
        v531[4] = 0;
        v531[5] = 0;
        v532 &= ~1u;
        COledbError::RaiseDataWarning((COledbError *)v525, L"guidPropertySet", L"DBPROPSET_DATASOURCEINFO");
        v1025 = v529;
        operator delete[](v529);
      }
      if ( !*((_DWORD *)v277 + 2) )
      {
        v21 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
        v22 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
        v533[0] = 0;
        v533[1] = &IID_IUnknown;
        v534 = 0;
        v535 = v22;
        v536 = v21;
        v537 = 0;
        v538 = 0;
        v1026 = v539;
        v539[0] = 0;
        v539[1] = 0;
        v539[2] = -1;
        v539[3] = 0;
        v539[4] = 0;
        v539[5] = 0;
        v540 &= ~1u;
        COledbError::RaiseDataWarning((COledbError *)v533, L"number of DATASOURCEINFO properties", L"greater than 0");
        v1027 = v537;
        operator delete[](v537);
      }
    }
    if ( v270 > 1 )
    {
      v1028 = v277 + 44;
      if ( *(_QWORD *)(v277 + 44) != *(_QWORD *)&SQLPROPSET_OPTHINTS.Data1
        || *(_QWORD *)(v277 + 52) != *(_QWORD *)SQLPROPSET_OPTHINTS.Data4 )
      {
        v23 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
        v24 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
        v541[0] = 0;
        v541[1] = &IID_IUnknown;
        v542 = 0;
        v543 = v24;
        v544 = v23;
        v545 = 0;
        v546 = 0;
        v1029 = v547;
        v547[0] = 0;
        v547[1] = 0;
        v547[2] = -1;
        v547[3] = 0;
        v547[4] = 0;
        v547[5] = 0;
        v548 &= ~1u;
        COledbError::RaiseDataWarning((COledbError *)v541, L"guidPropertySet", L"SQLPROPSET_OPTHINTS");
        v1030 = v545;
        operator delete[](v545);
      }
      if ( !*((_DWORD *)v277 + 10) )
      {
        v25 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
        v26 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
        v549[0] = 0;
        v549[1] = &IID_IUnknown;
        v550 = 0;
        v551 = v26;
        v552 = v25;
        v553 = 0;
        v554 = 0;
        v920 = v555;
        v555[0] = 0;
        v555[1] = 0;
        v555[2] = -1;
        v555[3] = 0;
        v555[4] = 0;
        v555[5] = 0;
        v556 &= ~1u;
        COledbError::RaiseDataWarning(
          (COledbError *)v549,
          L"number of SQLPROPSET_OPTHINTS properties",
          L"greater than 0");
        v921 = v553;
        operator delete[](v553);
      }
    }
    if ( v270 > 2 )
    {
      v922 = v277 + 76;
      if ( *(_QWORD *)(v277 + 76) != *(_QWORD *)&DBPROPSET_SQLSERVERDATASOURCEINFO.Data1
        || *(_QWORD *)(v277 + 84) != *(_QWORD *)DBPROPSET_SQLSERVERDATASOURCEINFO.Data4 )
      {
        v27 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
        v28 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
        v557[0] = 0;
        v557[1] = &IID_IUnknown;
        v558 = 0;
        v559 = v28;
        v560 = v27;
        v561 = 0;
        v562 = 0;
        v923 = v563;
        v563[0] = 0;
        v563[1] = 0;
        v563[2] = -1;
        v563[3] = 0;
        v563[4] = 0;
        v563[5] = 0;
        v564 &= ~1u;
        COledbError::RaiseDataWarning((COledbError *)v557, L"guidPropertySet", L"DBPROPSET_SQLSERVERDATASOURCEINFO");
        v924 = v561;
        operator delete[](v561);
      }
      if ( !*((_DWORD *)v277 + 18) )
      {
        v29 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
        v30 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
        v565[0] = 0;
        v565[1] = &IID_IUnknown;
        v566 = 0;
        v567 = v30;
        v568 = v29;
        v569 = 0;
        v570 = 0;
        v925 = v571;
        v571[0] = 0;
        v571[1] = 0;
        v571[2] = -1;
        v571[3] = 0;
        v571[4] = 0;
        v571[5] = 0;
        v572 &= ~1u;
        COledbError::RaiseDataWarning(
          (COledbError *)v565,
          L"number of SQLSERVERDATASOURCEINFO properties",
          L"greater than 0");
        v926 = v569;
        operator delete[](v569);
      }
    }
  }
  v290 = 0;
  v291 = 0;
  v31 = 0;
  v267 = 0;
  v298 = 0;
  v285 = 0;
  v299 = 0;
  v283 = 0;
  v300 = 0;
  v276 = 0;
  v301 = 0;
  v292 = 0;
  if ( v277
    && v270
    && (v927 = v277 + 12, *(_QWORD *)(v277 + 12) == *(_QWORD *)&DBPROPSET_DATASOURCEINFO.Data1)
    && *(_QWORD *)(v277 + 20) == *(_QWORD *)DBPROPSET_DATASOURCEINFO.Data4 )
  {
    v32 = *((unsigned int *)v277 + 2);
    v268 = *((_DWORD *)v277 + 2);
    v272 = v268;
    v33 = *(_QWORD *)v277;
    v263 = *(_QWORD *)v277;
  }
  else
  {
    v32 = 0;
    v268 = 0;
    v272 = 0;
    v33 = 0;
    v263 = 0;
  }
  v34 = 0;
  v271 = 0;
  v35 = 0;
  v36 = &CXplOp_ParameterSensitivePredicate::m_szName;
  while ( (unsigned int)v35 < (unsigned int)v32 )
  {
    v37 = (int *)(v33 + 72 * v35);
    v38 = *v37;
    if ( (unsigned int)*v37 > 0x120 )
      goto LABEL_197;
    if ( v38 == 288 )
    {
      if ( !v37[2] )
      {
        if ( *((_WORD *)v37 + 24) == 3 )
        {
          if ( (v37[14] & 2) != 0 )
            *((_BYTE *)a3 + 3) |= 8u;
        }
        else
        {
          v94 = (*(__int64 (__fastcall **)(COledbConnect *, __int64, SID *))(*(_QWORD *)this + 40LL))(
                  this,
                  v32,
                  &CXplOp_ParameterSensitivePredicate::m_szName);
          v95 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
          v733[0] = 0;
          v733[1] = &IID_IUnknown;
          v734 = 0;
          v735 = v95;
          v736 = v94;
          v737 = 0;
          v738 = 0;
          v968 = v739;
          v739[0] = 0;
          v739[1] = 0;
          v739[2] = -1;
          v739[3] = 0;
          v739[4] = 0;
          v739[5] = 0;
          v740 &= ~1u;
          COledbError::RaiseTypeWarning((COledbError *)v733, L"DBPROP_TABLESTATISTICS", *((_WORD *)v37 + 24), 3u);
          v969 = v737;
          operator delete[](v737);
          v32 = v268;
          v36 = &CXplOp_ParameterSensitivePredicate::m_szName;
          v33 = v263;
          v31 = v267;
        }
      }
    }
    else
    {
      switch ( v38 )
      {
        case 0x16u:
          if ( !v37[2] )
          {
            if ( *((_WORD *)v37 + 24) == 3 )
            {
              v55 = v37[14];
              if ( v55 == 2 )
              {
                *((_DWORD *)a3 + 2) |= 1u;
              }
              else if ( v55 != 1 )
              {
                v56 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
                v57 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
                v613[0] = 0;
                v613[1] = &IID_IUnknown;
                v614 = 0;
                v615 = v57;
                v616 = v56;
                v617 = 0;
                v618 = 0;
                v938 = v619;
                v619[0] = 0;
                v619[1] = 0;
                v619[2] = -1;
                v619[3] = 0;
                v619[4] = 0;
                v619[5] = 0;
                v620 &= ~1u;
                COledbError::RaiseDataWarning(
                  (COledbError *)v613,
                  L"DBPROP_CATALOGLOCATION",
                  L"either DBPROPVAL_CL_END or DBPROPVAL_CL_START");
                v939 = v617;
                operator delete[](v617);
                v32 = v268;
                v36 = &CXplOp_ParameterSensitivePredicate::m_szName;
                v33 = v263;
                v31 = v267;
              }
            }
            else
            {
              v53 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
              v54 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
              v605[0] = 0;
              v605[1] = &IID_IUnknown;
              v606 = 0;
              v607 = v54;
              v608 = v53;
              v609 = 0;
              v610 = 0;
              v936 = v611;
              v611[0] = 0;
              v611[1] = 0;
              v611[2] = -1;
              v611[3] = 0;
              v611[4] = 0;
              v611[5] = 0;
              v612 &= ~1u;
              COledbError::RaiseTypeWarning((COledbError *)v605, L"DBPROP_CATALOGLOCATION", *((_WORD *)v37 + 24), 3u);
              v937 = v609;
              operator delete[](v609);
              v32 = v268;
              v36 = &CXplOp_ParameterSensitivePredicate::m_szName;
              v33 = v263;
              v31 = v267;
            }
          }
          break;
        case 0x24u:
          if ( !v37[2] )
          {
            if ( *((_WORD *)v37 + 24) == 3 )
            {
              v84 = v37[14];
              if ( v84 == 1 )
              {
                *((_BYTE *)a3 + 4) |= 8u;
              }
              else if ( v84 == 2 )
              {
                *((_BYTE *)a3 + 4) &= ~8u;
              }
              else
              {
                v85 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
                v86 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
                v701[0] = 0;
                v701[1] = &IID_IUnknown;
                v702 = 0;
                v703 = v86;
                v704 = v85;
                v705 = 0;
                v706 = 0;
                v960 = v707;
                v707[0] = 0;
                v707[1] = 0;
                v707[2] = -1;
                v707[3] = 0;
                v707[4] = 0;
                v707[5] = 0;
                v708 &= ~1u;
                COledbError::RaiseDataWarning(
                  (COledbError *)v701,
                  L"DBPROP_CONCATNULLBEHAVIOR",
                  L"either DBPROPVAL_CB_NULL or DBPROPVAL_CB_NON_NULL");
                v961 = v705;
                operator delete[](v705);
                v32 = v268;
                v36 = &CXplOp_ParameterSensitivePredicate::m_szName;
                v33 = v263;
                v31 = v267;
              }
            }
            else
            {
              v82 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
              v83 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
              v693[0] = 0;
              v693[1] = &IID_IUnknown;
              v694 = 0;
              v695 = v83;
              v696 = v82;
              v697 = 0;
              v698 = 0;
              v958 = v699;
              v699[0] = 0;
              v699[1] = 0;
              v699[2] = -1;
              v699[3] = 0;
              v699[4] = 0;
              v699[5] = 0;
              v700 &= ~1u;
              COledbError::RaiseTypeWarning((COledbError *)v693, L"DBPROP_CONCATNULLBEHAVIOR", *((_WORD *)v37 + 24), 3u);
              v959 = v697;
              operator delete[](v697);
              v32 = v268;
              v36 = &CXplOp_ParameterSensitivePredicate::m_szName;
              v33 = v263;
              v31 = v267;
            }
          }
          break;
        case 0x28u:
          if ( !v37[2] )
          {
            if ( *((_WORD *)v37 + 24) == 8 )
            {
              if ( CompareStringWEnglishNoCase(1u, 0, *((const wchar_t **)v37 + 7), -1, L"Microsoft SQL Server", -1) == 2 )
                v290 = 1;
            }
            else
            {
              v39 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
              v40 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
              v573[0] = 0;
              v573[1] = &IID_IUnknown;
              v574 = 0;
              v575 = v40;
              v576 = v39;
              v577 = 0;
              v578 = 0;
              v928 = v579;
              v579[0] = 0;
              v579[1] = 0;
              v579[2] = -1;
              v579[3] = 0;
              v579[4] = 0;
              v579[5] = 0;
              v580 &= ~1u;
              COledbError::RaiseTypeWarning((COledbError *)v573, L"DBPROP_DBMSNAME", *((_WORD *)v37 + 24), 8u);
              v929 = v577;
              operator delete[](v577);
              v31 = v267;
            }
            goto LABEL_99;
          }
          break;
        case 0x29u:
          if ( !v37[2] )
          {
            if ( *((_WORD *)v37 + 24) == 8 )
            {
              DefaultLocale = GetDefaultLocale();
              v44 = _wtoi_l(*((const wchar_t **)v37 + 7), DefaultLocale);
              if ( v44 == 7 )
              {
                v291 = 1;
              }
              else
              {
                if ( v44 >= 8 )
                  v31 = 1;
                v267 = v31;
                v298 = v31;
                v45 = v285;
                if ( v44 >= 9 )
                  v45 = 1;
                v285 = v45;
                v299 = v45;
                v46 = v283;
                if ( v44 >= 10 )
                  v46 = 1;
                v283 = v46;
                v300 = v46;
                v47 = v276;
                if ( v44 >= 11 )
                  v47 = 1;
                v276 = v47;
                v301 = v47;
                if ( v44 >= 16 )
                  v292 = 1;
              }
            }
            else
            {
              v41 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
              v42 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
              v581[0] = 0;
              v581[1] = &IID_IUnknown;
              v582 = 0;
              v583 = v42;
              v584 = v41;
              v585 = 0;
              v586 = 0;
              v930 = v587;
              v587[0] = 0;
              v587[1] = 0;
              v587[2] = -1;
              v587[3] = 0;
              v587[4] = 0;
              v587[5] = 0;
              v588 &= ~1u;
              COledbError::RaiseTypeWarning((COledbError *)v581, L"DBPROP_DBMSVER", *((_WORD *)v37 + 24), 8u);
              v931 = v585;
              operator delete[](v585);
              v31 = v267;
            }
            goto LABEL_99;
          }
          break;
        case 0x2Eu:
          if ( !v37[2] )
          {
            if ( *((_WORD *)v37 + 24) == 3 )
            {
              v60 = v37[14];
              switch ( v60 )
              {
                case 2:
                  *((_DWORD *)a3 + 2) |= 4u;
                  break;
                case 8:
                  *((_DWORD *)a3 + 2) |= 6u;
                  break;
                case 4:
                  *((_DWORD *)a3 + 2) |= 8u;
                  break;
                default:
                  if ( v60 != 1 )
                  {
                    v61 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
                    v62 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
                    v629[0] = 0;
                    v629[1] = &IID_IUnknown;
                    v630 = 0;
                    v631 = v62;
                    v632 = v61;
                    v633 = 0;
                    v634 = 0;
                    v942 = v635;
                    v635[0] = 0;
                    v635[1] = 0;
                    v635[2] = -1;
                    v635[3] = 0;
                    v635[4] = 0;
                    v635[5] = 0;
                    v636 &= ~1u;
                    COledbError::RaiseDataWarning(
                      (COledbError *)v629,
                      L"DBPROP_IDENTIFIERCASE",
                      L"one of DBPROPVAL_IC_LOWER,DBPROPVAL_IC_MIXED,DBPROPVAL_IC_SENSITIVE, and DBPROPVAL_IC_UPPER");
                    v943 = v633;
                    operator delete[](v633);
                    v32 = v268;
                    v36 = &CXplOp_ParameterSensitivePredicate::m_szName;
                    v33 = v263;
                    v31 = v267;
                  }
                  break;
              }
            }
            else
            {
              v58 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
              v59 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
              v621[0] = 0;
              v621[1] = &IID_IUnknown;
              v622 = 0;
              v623 = v59;
              v624 = v58;
              v625 = 0;
              v626 = 0;
              v940 = v627;
              v627[0] = 0;
              v627[1] = 0;
              v627[2] = -1;
              v627[3] = 0;
              v627[4] = 0;
              v627[5] = 0;
              v628 &= ~1u;
              COledbError::RaiseTypeWarning((COledbError *)v621, L"DBPROP_IDENTIFIERCASE", *((_WORD *)v37 + 24), 3u);
              v941 = v625;
              operator delete[](v625);
              v32 = v268;
              v36 = &CXplOp_ParameterSensitivePredicate::m_szName;
              v33 = v263;
              v31 = v267;
            }
          }
          break;
        case 0x50u:
          if ( !v37[2] )
          {
            if ( *((_WORD *)v37 + 24) == 11 )
            {
              if ( *((_WORD *)v37 + 28) )
                *((_BYTE *)a3 + 3) |= 2u;
              else
                *((_BYTE *)a3 + 3) &= ~2u;
            }
            else
            {
              v68 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
              v69 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
              v653[0] = 0;
              v653[1] = &IID_IUnknown;
              v654 = 0;
              v655 = v69;
              v656 = v68;
              v657 = 0;
              v658 = 0;
              v948 = v659;
              v659[0] = 0;
              v659[1] = 0;
              v659[2] = -1;
              v659[3] = 0;
              v659[4] = 0;
              v659[5] = 0;
              v660 &= ~1u;
              COledbError::RaiseTypeWarning(
                (COledbError *)v653,
                L"DBPROP_MULTIPLESTORAGEOBJECTS",
                *((_WORD *)v37 + 24),
                0xBu);
              v949 = v657;
              operator delete[](v657);
              v32 = v268;
              v36 = &CXplOp_ParameterSensitivePredicate::m_szName;
              v33 = v263;
              v31 = v267;
            }
          }
          break;
        case 0x53u:
          if ( !v37[2] )
          {
            if ( *((_WORD *)v37 + 24) == 3 )
            {
              v89 = v37[14];
              if ( (((v89 - 1) & 0xFFFFFFFC) != 0 || v89 == 3) && v89 != 8 )
              {
                v90 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
                v91 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
                v717[0] = 0;
                v717[1] = &IID_IUnknown;
                v718 = 0;
                v719 = v91;
                v720 = v90;
                v721 = 0;
                v722 = 0;
                v964 = v723;
                v723[0] = 0;
                v723[1] = 0;
                v723[2] = -1;
                v723[3] = 0;
                v723[4] = 0;
                v723[5] = 0;
                v724 &= ~1u;
                COledbError::RaiseDataWarning(
                  (COledbError *)v717,
                  L"DBPROP_NULLCOLLATION",
                  L"one of DBPROPVAL_NC_END,DBPROPVAL_NC_HIGH,DBPROPVAL_NC_LOW,DBPROPVAL_NC_LOW");
                v965 = v721;
                operator delete[](v721);
                v32 = v268;
                v36 = &CXplOp_ParameterSensitivePredicate::m_szName;
                v33 = v263;
                v31 = v267;
              }
              else
              {
                *((_DWORD *)a3 + 138) = v89;
              }
            }
            else
            {
              v87 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
              v88 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
              v709[0] = 0;
              v709[1] = &IID_IUnknown;
              v710 = 0;
              v711 = v88;
              v712 = v87;
              v713 = 0;
              v714 = 0;
              v962 = v715;
              v715[0] = 0;
              v715[1] = 0;
              v715[2] = -1;
              v715[3] = 0;
              v715[4] = 0;
              v715[5] = 0;
              v716 &= ~1u;
              COledbError::RaiseTypeWarning((COledbError *)v709, L"DBPROP_NULLCOLLATION", *((_WORD *)v37 + 24), 3u);
              v963 = v713;
              operator delete[](v713);
              v32 = v268;
              v36 = &CXplOp_ParameterSensitivePredicate::m_szName;
              v33 = v263;
              v31 = v267;
            }
          }
          break;
        case 0x54u:
          if ( !v37[2] )
          {
            if ( *((_WORD *)v37 + 24) == 3 )
            {
              if ( (v37[14] & 1) != 0 )
                *((_BYTE *)a3 + 3) |= 1u;
              else
                *((_BYTE *)a3 + 3) &= ~1u;
            }
            else
            {
              v70 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
              v71 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
              v661[0] = 0;
              v661[1] = &IID_IUnknown;
              v662 = 0;
              v663 = v71;
              v664 = v70;
              v665 = 0;
              v666 = 0;
              v950 = v667;
              v667[0] = 0;
              v667[1] = 0;
              v667[2] = -1;
              v667[3] = 0;
              v667[4] = 0;
              v667[5] = 0;
              v668 &= ~1u;
              COledbError::RaiseTypeWarning((COledbError *)v661, L"DBPROP_OLEOBJECTS", *((_WORD *)v37 + 24), 3u);
              v951 = v665;
              operator delete[](v665);
              v32 = v268;
              v36 = &CXplOp_ParameterSensitivePredicate::m_szName;
              v33 = v263;
              v31 = v267;
            }
          }
          break;
        case 0x60u:
          if ( !v37[2] )
          {
            if ( *((_WORD *)v37 + 24) == 8 )
            {
              if ( CompareStringWEnglishNoCase(1u, 0, *((const wchar_t **)v37 + 7), -1, L"Microsoft BCP Provider", -1) == 2 )
              {
                *((_BYTE *)a3 + 3) |= 1u;
              }
              else if ( CompareStringWEnglishNoCase(1u, 0, *((const wchar_t **)v37 + 7), -1, L"sqlncli11.dll", -1) == 2 )
              {
                *(_BYTE *)a3 |= 0x40u;
              }
              else if ( CompareStringWEnglishNoCase(1u, 0, *((const wchar_t **)v37 + 7), -1, L"msoledbsql.dll", -1) == 2 )
              {
                *(_BYTE *)a3 |= 0x40u;
              }
              else if ( CompareStringWEnglishNoCase(1u, 0, *((const wchar_t **)v37 + 7), -1, L"sqlnclirda11.dll", -1) == 2 )
              {
                *(_BYTE *)a3 |= 0x40u;
              }
              else if ( CompareStringWEnglishNoCase(1u, 0, *((const wchar_t **)v37 + 7), -1, L"MSDASQL.DLL", -1) == 2 )
              {
                *(_BYTE *)a3 |= 0x80u;
              }
              else if ( CompareStringWEnglishNoCase(1u, 0, *((const wchar_t **)v37 + 7), -1, L"MSJETOLEDB40.DLL", -1) == 2 )
              {
                *((_BYTE *)a3 + 1) |= 1u;
              }
              else if ( CompareStringWEnglishNoCase(1u, 0, *((const wchar_t **)v37 + 7), -1, L"MSDAORA.DLL", -1) == 2 )
              {
                *((_BYTE *)a3 + 1) |= 2u;
              }
              else if ( CompareStringWEnglishNoCase(1u, 0, *((const wchar_t **)v37 + 7), -1, L"OraOLEDB.DLL", -1) == 2 )
              {
                *((_BYTE *)a3 + 1) |= 4u;
              }
              else if ( CompareStringWEnglishNoCase(1u, 0, *((const wchar_t **)v37 + 7), -1, L"OraOLEDB10.DLL", -1) == 2 )
              {
                *((_BYTE *)a3 + 1) |= 4u;
              }
              else if ( CompareStringWEnglishNoCase(
                          1u,
                          0,
                          *((const wchar_t **)v37 + 7),
                          -1,
                          L"AccessServices.OLEDB",
                          -1) == 2 )
              {
                *((_BYTE *)a3 + 1) |= 8u;
              }
            }
            else
            {
              v48 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
              v49 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
              v589[0] = 0;
              v589[1] = &IID_IUnknown;
              v590 = 0;
              v591 = v49;
              v592 = v48;
              v593 = 0;
              v594 = 0;
              v932 = v595;
              v595[0] = 0;
              v595[1] = 0;
              v595[2] = -1;
              v595[3] = 0;
              v595[4] = 0;
              v595[5] = 0;
              v596 &= ~1u;
              COledbError::RaiseTypeWarning((COledbError *)v589, L"DBPROP_PROVIDERNAME", *((_WORD *)v37 + 24), 8u);
              v933 = v593;
              operator delete[](v593);
              v31 = v267;
            }
            goto LABEL_99;
          }
          break;
        case 0x61u:
          if ( !v37[2] )
          {
            if ( *((_WORD *)v37 + 24) == 8 )
            {
              v52 = GetDefaultLocale();
              if ( swscanf_l(*((const wchar_t *const *)v37 + 7), L"%u.%u", v52, &v302, &v303) )
                *((_DWORD *)a3 + 140) = v303 | (v302 << 16);
LABEL_99:
              v33 = v263;
              v36 = &CXplOp_ParameterSensitivePredicate::m_szName;
              v32 = v268;
            }
            else
            {
              v50 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
              v51 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
              v597[0] = 0;
              v597[1] = &IID_IUnknown;
              v598 = 0;
              v599 = v51;
              v600 = v50;
              v601 = 0;
              v602 = 0;
              v934 = v603;
              v603[0] = 0;
              v603[1] = 0;
              v603[2] = -1;
              v603[3] = 0;
              v603[4] = 0;
              v603[5] = 0;
              v604 &= ~1u;
              COledbError::RaiseTypeWarning((COledbError *)v597, L"DBPROP_PROVIDEROLEDBVER", *((_WORD *)v37 + 24), 8u);
              v935 = v601;
              operator delete[](v601);
              v32 = v268;
              v36 = &CXplOp_ParameterSensitivePredicate::m_szName;
              v33 = v263;
              v31 = v267;
            }
          }
          break;
        case 0x64u:
          if ( !v37[2] )
          {
            if ( *((_WORD *)v37 + 24) == 3 )
            {
              v65 = v37[14];
              switch ( v65 )
              {
                case 2:
                  *((_DWORD *)a3 + 2) |= 0x20u;
                  break;
                case 8:
                  *((_DWORD *)a3 + 2) |= 0x30u;
                  break;
                case 4:
                  *((_DWORD *)a3 + 2) |= 0x40u;
                  break;
                default:
                  if ( v65 != 1 )
                  {
                    v66 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
                    v67 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
                    v645[0] = 0;
                    v645[1] = &IID_IUnknown;
                    v646 = 0;
                    v647 = v67;
                    v648 = v66;
                    v649 = 0;
                    v650 = 0;
                    v946 = v651;
                    v651[0] = 0;
                    v651[1] = 0;
                    v651[2] = -1;
                    v651[3] = 0;
                    v651[4] = 0;
                    v651[5] = 0;
                    v652 &= ~1u;
                    COledbError::RaiseDataWarning(
                      (COledbError *)v645,
                      L"DBPROP_QUOTEDIDENTIFIERCASE",
                      L"one of DBPROPVAL_IC_LOWER,DBPROPVAL_IC_MIXED,DBPROPVAL_IC_SENSITIVE, and DBPROPVAL_IC_UPPER");
                    v947 = v649;
                    operator delete[](v649);
                    v32 = v268;
                    v36 = &CXplOp_ParameterSensitivePredicate::m_szName;
                    v33 = v263;
                    v31 = v267;
                  }
                  break;
              }
            }
            else
            {
              v63 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
              v64 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
              v637[0] = 0;
              v637[1] = &IID_IUnknown;
              v638 = 0;
              v639 = v64;
              v640 = v63;
              v641 = 0;
              v642 = 0;
              v944 = v643;
              v643[0] = 0;
              v643[1] = 0;
              v643[2] = -1;
              v643[3] = 0;
              v643[4] = 0;
              v643[5] = 0;
              v644 &= ~1u;
              COledbError::RaiseTypeWarning(
                (COledbError *)v637,
                L"DBPROP_QUOTEDIDENTIFIERCASE",
                *((_WORD *)v37 + 24),
                3u);
              v945 = v641;
              operator delete[](v641);
              v32 = v268;
              v36 = &CXplOp_ParameterSensitivePredicate::m_szName;
              v33 = v263;
              v31 = v267;
            }
          }
          break;
        case 0x6Du:
          if ( v37[2] )
            break;
          if ( *((_WORD *)v37 + 24) != 3 )
          {
            v78 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
            v79 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
            v685[0] = 0;
            v685[1] = &IID_IUnknown;
            v686 = 0;
            v687 = v79;
            v688 = v78;
            v689 = 0;
            v690 = 0;
            v956 = v691;
            v691[0] = 0;
            v691[1] = 0;
            v691[2] = -1;
            v691[3] = 0;
            v691[4] = 0;
            v691[5] = 0;
            v692 &= ~1u;
            COledbError::RaiseTypeWarning((COledbError *)v685, L"DBPROP_SQLSUPPORT", *((_WORD *)v37 + 24), 3u);
            v957 = v689;
            operator delete[](v689);
            v32 = v268;
            v36 = &CXplOp_ParameterSensitivePredicate::m_szName;
            v33 = v263;
            v31 = v267;
            break;
          }
          v80 = v37[14];
          if ( (v80 & 0x10) != 0 )
          {
            *((_BYTE *)a3 + 1) |= 0x20u;
            v81 = *((_BYTE *)a3 + 1) | 0x80;
            *((_BYTE *)a3 + 1) = v81;
            v80 = v37[14];
          }
          else
          {
            v81 = *((_BYTE *)a3 + 1);
          }
          if ( (v80 & 2) != 0 )
          {
            v81 |= 0x40u;
            *((_BYTE *)a3 + 1) = v81;
          }
          else if ( (v80 & 1) == 0 )
          {
            goto LABEL_165;
          }
          *((_BYTE *)a3 + 1) = v81 | 0x80;
LABEL_165:
          if ( (v37[14] & 0x200) != 0 )
            *((_BYTE *)a3 + 2) |= 1u;
          break;
        case 0x6Fu:
          v72 = 8;
          *((_DWORD *)a3 + 139) = 8;
          if ( !v37[2] )
          {
            if ( *((_WORD *)v37 + 24) == 3 )
            {
              v75 = v37[14];
              if ( (v75 & 8) != 0 )
              {
                *((_DWORD *)a3 + 139) = 9;
                v72 = 9;
                v75 = v37[14];
              }
              if ( (v75 & 2) != 0 )
              {
                v72 |= 2u;
                *((_DWORD *)a3 + 139) = v72;
                v75 = v37[14];
              }
              if ( (v75 & 1) != 0 )
                *((_DWORD *)a3 + 139) = v72 | 4;
            }
            else
            {
              v73 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
              v74 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
              v669[0] = 0;
              v669[1] = &IID_IUnknown;
              v670 = 0;
              v671 = v74;
              v672 = v73;
              v673 = 0;
              v674 = 0;
              v952 = v675;
              v675[0] = 0;
              v675[1] = 0;
              v675[2] = -1;
              v675[3] = 0;
              v675[4] = 0;
              v675[5] = 0;
              v676 &= ~1u;
              COledbError::RaiseTypeWarning((COledbError *)v669, L"DBPROP_STRUCTUREDSTORAGE", *((_WORD *)v37 + 24), 3u);
              v953 = v673;
              operator delete[](v673);
              v32 = v268;
              v36 = &CXplOp_ParameterSensitivePredicate::m_szName;
              v33 = v263;
              v31 = v267;
            }
          }
          break;
        case 0x78u:
          if ( !v37[2] )
          {
            if ( *((_WORD *)v37 + 24) == 11 )
            {
              if ( !*((_WORD *)v37 + 28) )
                *((_BYTE *)a3 + 4) &= ~4u;
            }
            else
            {
              v76 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
              v77 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
              v677[0] = 0;
              v677[1] = &IID_IUnknown;
              v678 = 0;
              v679 = v77;
              v680 = v76;
              v681 = 0;
              v682 = 0;
              v954 = v683;
              v683[0] = 0;
              v683[1] = 0;
              v683[2] = -1;
              v683[3] = 0;
              v683[4] = 0;
              v683[5] = 0;
              v684 &= ~1u;
              COledbError::RaiseTypeWarning((COledbError *)v677, L"DBPROP_BYREFACCESSORS", *((_WORD *)v37 + 24), 0xBu);
              v955 = v681;
              operator delete[](v681);
              v32 = v268;
              v36 = &CXplOp_ParameterSensitivePredicate::m_szName;
              v33 = v263;
              v31 = v267;
            }
          }
          break;
        case 0xC4u:
          if ( !v37[2] )
          {
            if ( *((_WORD *)v37 + 24) == 3 )
            {
              *((_BYTE *)a3 + 3) = *((_BYTE *)a3 + 3) & 0x7F | (*((_BYTE *)v37 + 56) << 7);
            }
            else
            {
              v92 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
              v93 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
              v725[0] = 0;
              v725[1] = &IID_IUnknown;
              v726 = 0;
              v727 = v93;
              v728 = v92;
              v729 = 0;
              v730 = 0;
              v966 = v731;
              v731[0] = 0;
              v731[1] = 0;
              v731[2] = -1;
              v731[3] = 0;
              v731[4] = 0;
              v731[5] = 0;
              v732 &= ~1u;
              COledbError::RaiseTypeWarning((COledbError *)v725, L"DBPROP_MULTIPLERESULTS", *((_WORD *)v37 + 24), 3u);
              v967 = v729;
              operator delete[](v729);
              v32 = v268;
              v36 = &CXplOp_ParameterSensitivePredicate::m_szName;
              v33 = v263;
              v31 = v267;
            }
          }
          break;
        case 0xEDu:
          if ( v37[2] != 1 || (*(_BYTE *)a3 & 0x40) != 0 || *(char *)a3 < 0 )
            *((_BYTE *)a3 + 3) &= ~0x40u;
          else
            *((_BYTE *)a3 + 3) |= 0x40u;
          break;
        default:
          break;
      }
    }
LABEL_197:
    v271 = ++v34;
    v35 = v34;
  }
  v96 = *((_BYTE *)a3 + 3);
  if ( (v96 & 1) == 0 )
    goto LABEL_201;
  if ( *((_DWORD *)a3 + 139) )
    goto LABEL_202;
  v97 = (*(__int64 (__fastcall **)(COledbConnect *, __int64, SID *))(*(_QWORD *)this + 40LL))(
          this,
          v32,
          &CXplOp_ParameterSensitivePredicate::m_szName);
  v98 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
  v741[0] = 0;
  v741[1] = &IID_IUnknown;
  v742 = 0;
  v743 = v98;
  v744 = v97;
  v745 = 0;
  v746 = 0;
  v970 = v747;
  v747[0] = 0;
  v747[1] = 0;
  v747[2] = -1;
  v747[3] = 0;
  v747[4] = 0;
  v747[5] = 0;
  v748 &= ~1u;
  COledbError::RaiseConsistencyWarning((COledbError *)v741, L"DBPROPVAL_OO_BLOB", L"DBPROP_STRUCTUREDSTORAGE");
  v971 = v745;
  operator delete[](v745);
  v96 = *((_BYTE *)a3 + 3);
LABEL_201:
  if ( *((_DWORD *)a3 + 139) )
  {
LABEL_202:
    if ( (v96 & 1) == 0 )
    {
      v99 = (*(__int64 (__fastcall **)(COledbConnect *, __int64, SID *))(*(_QWORD *)this + 40LL))(this, v32, v36);
      v100 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
      v749[0] = 0;
      v749[1] = &IID_IUnknown;
      v750 = 0;
      v751 = v100;
      v752 = v99;
      v753 = 0;
      v754 = 0;
      v972 = v755;
      v755[0] = 0;
      v755[1] = 0;
      v755[2] = -1;
      v755[3] = 0;
      v755[4] = 0;
      v755[5] = 0;
      v756 &= ~1u;
      COledbError::RaiseConsistencyWarning((COledbError *)v749, L"DBPROP_STRUCTUREDSTORAGE", L"DBPROPVAL_OO_BLOB");
      v973 = v753;
      operator delete[](v753);
      v96 = *((_BYTE *)a3 + 3);
    }
  }
  if ( (v96 & 2) != 0 && (v96 & 1) == 0 )
  {
    v101 = (*(__int64 (__fastcall **)(COledbConnect *, __int64, SID *))(*(_QWORD *)this + 40LL))(this, v32, v36);
    v102 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
    v349[0] = 0;
    v349[1] = &IID_IUnknown;
    v350 = 0;
    v351 = v102;
    v352 = v101;
    v353 = 0;
    v354 = 0;
    v974 = v355;
    v355[0] = 0;
    v355[1] = 0;
    v355[2] = -1;
    v355[3] = 0;
    v355[4] = 0;
    v355[5] = 0;
    v356 &= ~1u;
    COledbError::RaiseConsistencyWarning((COledbError *)v349, L"DBPROP_MULTIPLESTORAGEOBJECTS", L"DBPROPVAL_OO_BLOB");
    v975 = v353;
    operator delete[](v353);
  }
  if ( v290 )
  {
    if ( v291 )
      *(_BYTE *)a3 |= 1u;
    if ( v267 )
      *(_BYTE *)a3 |= 2u;
    if ( v285 )
      *(_BYTE *)a3 |= 4u;
    if ( v283 )
      *(_BYTE *)a3 |= 8u;
    if ( v276 )
      *(_BYTE *)a3 |= 0x10u;
    if ( v292 )
    {
      *(_BYTE *)a3 |= 0x20u;
      *((_BYTE *)a3 + 6) |= 2u;
    }
  }
  v276 = 1;
  if ( v277
    && v270 > 1
    && (v976 = v277 + 44, *(_QWORD *)(v277 + 44) == *(_QWORD *)&SQLPROPSET_OPTHINTS.Data1)
    && *(_QWORD *)(v277 + 52) == *(_QWORD *)SQLPROPSET_OPTHINTS.Data4 )
  {
    v103 = *((_DWORD *)v277 + 10);
    v272 = v103;
    v104 = *((_QWORD *)v277 + 4);
    v264 = v104;
  }
  else
  {
    v103 = 0;
    v272 = 0;
    v104 = 0;
    v264 = 0;
  }
  v105 = 0;
  v271 = 0;
  for ( i = 0; (unsigned int)i < v103; i = v105 )
  {
    v107 = v104 + 72 * i;
    switch ( *(_DWORD *)v107 )
    {
      case 4:
        if ( (*((_BYTE *)this + 144) & 2) != 0 )
        {
          v111 = (*((_BYTE *)this + 148) & 2) != 0;
          v278 = 1;
          *((_BYTE *)a3 + 4) &= ~0x40u;
          *((_BYTE *)a3 + 4) |= v111 << 6;
        }
        else
        {
          v278 = 0;
          if ( *(_DWORD *)(v107 + 8) )
          {
            *((_BYTE *)a3 + 4) |= 0x40u;
          }
          else if ( *(_WORD *)(v107 + 48) == 11 )
          {
            v110 = *((_BYTE *)a3 + 4);
            if ( *(_WORD *)(v107 + 56) )
              *((_BYTE *)a3 + 4) = v110 | 0x40;
            else
              *((_BYTE *)a3 + 4) = v110 & 0xBF;
          }
          else
          {
            v108 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
            v109 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
            v357[0] = 0;
            v357[1] = &IID_IUnknown;
            v358 = 0;
            v359 = v109;
            v360 = v108;
            v361 = 0;
            v362 = 0;
            v1018 = v363;
            v363[0] = 0;
            v363[1] = 0;
            v363[2] = -1;
            v363[3] = 0;
            v363[4] = 0;
            v363[5] = 0;
            v364 &= ~1u;
            COledbError::RaiseTypeWarning((COledbError *)v357, L"SQLPROP_NESTEDQUERIES", *(_WORD *)(v107 + 48), 0xBu);
            v1017 = v361;
            operator delete[](v361);
            v104 = v264;
          }
        }
        break;
      case 5:
        if ( (*((_BYTE *)this + 144) & 1) != 0 )
        {
          v116 = *((_BYTE *)this + 148) & 1;
          v279 = 1;
          *((_BYTE *)a3 + 4) &= ~0x20u;
          *((_BYTE *)a3 + 4) |= 32 * v116;
        }
        else
        {
          v279 = 0;
          if ( *(_DWORD *)(v107 + 8) )
          {
            if ( (*(_BYTE *)a3 & 3) != 0 || (v112 = *((_BYTE *)a3 + 1), (v112 & 1) != 0) || v112 < 0 )
              *((_BYTE *)a3 + 4) |= 0x20u;
            else
              *((_BYTE *)a3 + 4) &= ~0x20u;
          }
          else if ( *(_WORD *)(v107 + 48) == 11 )
          {
            v115 = *((_BYTE *)a3 + 4);
            if ( *(_WORD *)(v107 + 56) )
              *((_BYTE *)a3 + 4) = v115 | 0x20;
            else
              *((_BYTE *)a3 + 4) = v115 & 0xDF;
          }
          else
          {
            v113 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
            v114 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
            v365[0] = 0;
            v365[1] = &IID_IUnknown;
            v366 = 0;
            v367 = v114;
            v368 = v113;
            v369 = 0;
            v370 = 0;
            v1016 = v371;
            v371[0] = 0;
            v371[1] = 0;
            v371[2] = -1;
            v371[3] = 0;
            v371[4] = 0;
            v371[5] = 0;
            v372 &= ~1u;
            COledbError::RaiseTypeWarning((COledbError *)v365, L"SQLPROP_DYNAMICSQL", *(_WORD *)(v107 + 48), 0xBu);
            v1013 = v369;
            operator delete[](v369);
            v104 = v264;
          }
        }
        break;
      case 6:
        if ( !*(_DWORD *)(v107 + 8) )
        {
          if ( *(_WORD *)(v107 + 48) == 11 )
          {
            *((_BYTE *)a3 + 2) = *((_BYTE *)a3 + 2) & 0xEF | (*(_WORD *)(v107 + 56) != 0 ? 0x10 : 0);
          }
          else
          {
            v117 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
            v118 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
            v373[0] = 0;
            v373[1] = &IID_IUnknown;
            v374 = 0;
            v375 = v118;
            v376 = v117;
            v377 = 0;
            v378 = 0;
            v1010 = v379;
            v379[0] = 0;
            v379[1] = 0;
            v379[2] = -1;
            v379[3] = 0;
            v379[4] = 0;
            v379[5] = 0;
            v380 &= ~1u;
            COledbError::RaiseTypeWarning((COledbError *)v373, L"SQLPROP_GROUPBY", *(_WORD *)(v107 + 48), 0xBu);
            v1009 = v377;
            operator delete[](v377);
            v104 = v264;
          }
        }
        break;
      case 7:
        if ( !*(_DWORD *)(v107 + 8) )
        {
          if ( *(_WORD *)(v107 + 48) == 11 )
          {
            *((_BYTE *)a3 + 2) = *((_BYTE *)a3 + 2) & 0xF7 | (*(_WORD *)(v107 + 56) != 0 ? 8 : 0);
          }
          else
          {
            v119 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
            v120 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
            v381[0] = 0;
            v381[1] = &IID_IUnknown;
            v382 = 0;
            v383 = v120;
            v384 = v119;
            v385 = 0;
            v386 = 0;
            v1015 = v387;
            v387[0] = 0;
            v387[1] = 0;
            v387[2] = -1;
            v387[3] = 0;
            v387[4] = 0;
            v387[5] = 0;
            v388 &= ~1u;
            COledbError::RaiseTypeWarning((COledbError *)v381, L"SQLPROP_DATELITERALS", *(_WORD *)(v107 + 48), 0xBu);
            v977 = v385;
            operator delete[](v385);
            v104 = v264;
          }
        }
        break;
      case 8:
        if ( !*(_DWORD *)(v107 + 8) )
        {
          if ( *(_WORD *)(v107 + 48) == 11 )
          {
            *((_BYTE *)a3 + 2) = *((_BYTE *)a3 + 2) & 0xFD | (*(_WORD *)(v107 + 56) != 0 ? 2 : 0);
          }
          else
          {
            v121 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
            v122 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
            v389[0] = 0;
            v389[1] = &IID_IUnknown;
            v390 = 0;
            v391 = v122;
            v392 = v121;
            v393 = 0;
            v394 = 0;
            v978 = v395;
            v395[0] = 0;
            v395[1] = 0;
            v395[2] = -1;
            v395[3] = 0;
            v395[4] = 0;
            v395[5] = 0;
            v396 &= ~1u;
            COledbError::RaiseTypeWarning((COledbError *)v389, L"SQLPROP_ANSILIKE", *(_WORD *)(v107 + 48), 0xBu);
            v979 = v393;
            operator delete[](v393);
            v104 = v264;
          }
        }
        break;
      case 9:
        if ( !*(_DWORD *)(v107 + 8) )
        {
          if ( *(_WORD *)(v107 + 48) == 11 )
          {
            *((_BYTE *)a3 + 2) = *((_BYTE *)a3 + 2) & 0xDF | (*(_WORD *)(v107 + 56) != 0 ? 0x20 : 0);
          }
          else
          {
            v123 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
            v124 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
            v397[0] = 0;
            v397[1] = &IID_IUnknown;
            v398 = 0;
            v399 = v124;
            v400 = v123;
            v401 = 0;
            v402 = 0;
            v980 = v403;
            v403[0] = 0;
            v403[1] = 0;
            v403[2] = -1;
            v403[3] = 0;
            v403[4] = 0;
            v403[5] = 0;
            v404 &= ~1u;
            COledbError::RaiseTypeWarning((COledbError *)v397, L"SQLPROP_INNERJOIN", *(_WORD *)(v107 + 48), 0xBu);
            v981 = v401;
            operator delete[](v401);
            v104 = v264;
          }
        }
        break;
      case 0x10:
        if ( !*(_DWORD *)(v107 + 8) )
        {
          if ( *(_WORD *)(v107 + 48) == 11 )
          {
            *((_BYTE *)a3 + 2) = *((_BYTE *)a3 + 2) & 0xBF | (*(_WORD *)(v107 + 56) != 0 ? 0x40 : 0);
          }
          else
          {
            v125 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
            v126 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
            v405[0] = 0;
            v405[1] = &IID_IUnknown;
            v406 = 0;
            v407 = v126;
            v408 = v125;
            v409 = 0;
            v410 = 0;
            v982 = v411;
            v411[0] = 0;
            v411[1] = 0;
            v411[2] = -1;
            v411[3] = 0;
            v411[4] = 0;
            v411[5] = 0;
            v412 &= ~1u;
            COledbError::RaiseTypeWarning((COledbError *)v405, L"SQLPROP_SUBQUERIES", *(_WORD *)(v107 + 48), 0xBu);
            v983 = v409;
            operator delete[](v409);
            v104 = v264;
          }
        }
        break;
      case 0x14:
        if ( !*(_DWORD *)(v107 + 8) )
        {
          if ( *(_WORD *)(v107 + 48) == 11 )
          {
            *((_BYTE *)a3 + 2) = *((_BYTE *)a3 + 2) & 0x7F | (*(_WORD *)(v107 + 56) != 0 ? 0x80 : 0);
          }
          else
          {
            v127 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
            v128 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
            v413[0] = 0;
            v413[1] = &IID_IUnknown;
            v414 = 0;
            v415 = v128;
            v416 = v127;
            v417 = 0;
            v418 = 0;
            v984 = v419;
            v419[0] = 0;
            v419[1] = 0;
            v419[2] = -1;
            v419[3] = 0;
            v419[4] = 0;
            v419[5] = 0;
            v420 &= ~1u;
            COledbError::RaiseTypeWarning((COledbError *)v413, L"SQLPROP_SIMPLEUPDATES", *(_WORD *)(v107 + 48), 0xBu);
            v985 = v417;
            operator delete[](v417);
            v104 = v264;
          }
        }
        break;
      case 0x15:
        if ( !*(_DWORD *)(v107 + 8) )
        {
          if ( *(_WORD *)(v107 + 48) == 11 )
          {
            *((_BYTE *)a3 + 2) = *((_BYTE *)a3 + 2) & 0xFB | (*(_WORD *)(v107 + 56) != 0 ? 4 : 0);
          }
          else
          {
            v129 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
            v130 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
            v421[0] = 0;
            v421[1] = &IID_IUnknown;
            v422 = 0;
            v423 = v130;
            v424 = v129;
            v425 = 0;
            v426 = 0;
            v986 = v427;
            v427[0] = 0;
            v427[1] = 0;
            v427[2] = -1;
            v427[3] = 0;
            v427[4] = 0;
            v427[5] = 0;
            v428 &= ~1u;
            COledbError::RaiseTypeWarning((COledbError *)v421, L"SQLPROP_SQLLIKE", *(_WORD *)(v107 + 48), 0xBu);
            v987 = v425;
            operator delete[](v425);
            v104 = v264;
          }
        }
        break;
      case 0x16:
        if ( !*(_DWORD *)(v107 + 8) )
        {
          if ( *(_WORD *)(v107 + 48) == 11 )
          {
            *((_BYTE *)a3 + 5) = *((_BYTE *)a3 + 5) & 0x7F | (*(_WORD *)(v107 + 56) != 0 ? 0x80 : 0);
          }
          else
          {
            v131 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
            v132 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
            v429[0] = 0;
            v429[1] = &IID_IUnknown;
            v430 = 0;
            v431 = v132;
            v432 = v131;
            v433 = 0;
            v434 = 0;
            v988 = v435;
            v435[0] = 0;
            v435[1] = 0;
            v435[2] = -1;
            v435[3] = 0;
            v435[4] = 0;
            v435[5] = 0;
            v436 &= ~1u;
            COledbError::RaiseTypeWarning((COledbError *)v429, L"SQLPROP_SQLBITREMOTING", *(_WORD *)(v107 + 48), 0xBu);
            v989 = v433;
            operator delete[](v433);
            v104 = v264;
          }
        }
        break;
      case 0x17:
        if ( !*(_DWORD *)(v107 + 8) )
        {
          if ( *(_WORD *)(v107 + 48) == 11 )
          {
            *((_BYTE *)a3 + 5) = *((_BYTE *)a3 + 5) & 0xDF | (*(_WORD *)(v107 + 56) != 0 ? 0x20 : 0);
          }
          else
          {
            v133 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
            v134 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
            v437[0] = 0;
            v437[1] = &IID_IUnknown;
            v438 = 0;
            v439 = v134;
            v440 = v133;
            v441 = 0;
            v442 = 0;
            v990 = v443;
            v443[0] = 0;
            v443[1] = 0;
            v443[2] = -1;
            v443[3] = 0;
            v443[4] = 0;
            v443[5] = 0;
            v444 &= ~1u;
            COledbError::RaiseTypeWarning(
              (COledbError *)v437,
              L"SQLPROP_SQLUNICODELITERALS",
              *(_WORD *)(v107 + 48),
              0xBu);
            v991 = v441;
            operator delete[](v441);
            v104 = v264;
          }
        }
        break;
      case 0x18:
        if ( !*(_DWORD *)(v107 + 8) )
        {
          if ( *(_WORD *)(v107 + 48) == 11 )
          {
            *((_BYTE *)a3 + 6) = *((_BYTE *)a3 + 6) & 0xFE | (*(_WORD *)(v107 + 56) != 0);
          }
          else
          {
            v135 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
            v136 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
            v501[0] = 0;
            v501[1] = &IID_IUnknown;
            v502 = 0;
            v503 = v136;
            v504 = v135;
            v505 = 0;
            v506 = 0;
            v992 = v507;
            v507[0] = 0;
            v507[1] = 0;
            v507[2] = -1;
            v507[3] = 0;
            v507[4] = 0;
            v507[5] = 0;
            v508 &= ~1u;
            COledbError::RaiseTypeWarning(
              (COledbError *)v501,
              L"SQLPROP_USELATESTCOLLATIONVERSION",
              *(_WORD *)(v107 + 48),
              0xBu);
            v993 = v505;
            operator delete[](v505);
            v104 = v264;
          }
        }
        break;
      default:
        break;
    }
    v271 = ++v105;
  }
  v137 = (unsigned int)++v276;
  if ( v277
    && v270 > 2
    && (v138 = &v277[32 * v137 + 12], v994 = v138,
                                      *(_QWORD *)v138 == *(_QWORD *)&DBPROPSET_SQLSERVERDATASOURCEINFO.Data1)
    && *((_QWORD *)v138 + 1) == *(_QWORD *)DBPROPSET_SQLSERVERDATASOURCEINFO.Data4 )
  {
    v139 = 32LL * (unsigned int)v137;
    v140 = *(_DWORD *)&v277[v139 + 8];
    v272 = v140;
    v141 = *(_QWORD *)&v277[v139];
    v265 = v141;
  }
  else
  {
    v140 = 0;
    v272 = 0;
    v141 = 0;
    v265 = 0;
  }
  v269 = v141;
  v142 = 0;
  v271 = 0;
  v143 = 0;
  while ( 2 )
  {
    if ( (unsigned int)v143 < v140 )
    {
      v144 = v141 + 72 * v143;
      switch ( *(_DWORD *)v144 )
      {
        case 2:
          if ( !*(_DWORD *)(v144 + 8) )
          {
            v145 = *(_WORD *)(v144 + 48);
            if ( v145 )
            {
              if ( v145 == 3 )
              {
                *((_DWORD *)a3 + 6) = *(_DWORD *)(v144 + 56);
              }
              else
              {
                v146 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
                v147 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
                v445[0] = 0;
                v445[1] = &IID_IUnknown;
                v446 = 0;
                v447 = v147;
                v448 = v146;
                v449 = 0;
                v450 = 0;
                v995 = v451;
                v451[0] = 0;
                v451[1] = 0;
                v451[2] = -1;
                v451[3] = 0;
                v451[4] = 0;
                v451[5] = 0;
                v452 &= ~1u;
                COledbError::RaiseTypeWarning((COledbError *)v445, L"SSPROP_UNICODELCID", *(_WORD *)(v144 + 48), 3u);
                v996 = v449;
                operator delete[](v449);
                v141 = v265;
              }
            }
          }
          goto LABEL_344;
        case 3:
          if ( !*(_DWORD *)(v144 + 8) )
          {
            v148 = *(_WORD *)(v144 + 48);
            if ( v148 )
            {
              if ( v148 == 3 )
              {
                *((_DWORD *)a3 + 137) = *(_DWORD *)(v144 + 56);
              }
              else
              {
                v149 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
                v150 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
                v453[0] = 0;
                v453[1] = &IID_IUnknown;
                v454 = 0;
                v455 = v150;
                v456 = v149;
                v457 = 0;
                v458 = 0;
                v997 = v459;
                v459[0] = 0;
                v459[1] = 0;
                v459[2] = -1;
                v459[3] = 0;
                v459[4] = 0;
                v459[5] = 0;
                v460 &= ~1u;
                COledbError::RaiseTypeWarning(
                  (COledbError *)v453,
                  L"SSPROP_UNICODECOMPARISONSTYLE",
                  *(_WORD *)(v144 + 48),
                  3u);
                v998 = v457;
                operator delete[](v457);
                v141 = v265;
              }
            }
          }
          goto LABEL_344;
        case 4:
          if ( !*(_DWORD *)(v144 + 8) )
          {
            if ( *(_WORD *)(v144 + 48) == 11 )
            {
              *((_BYTE *)a3 + 3) = *((_BYTE *)a3 + 3) & 0xEF | (*(_WORD *)(v144 + 56) != 0 ? 0x10 : 0);
            }
            else
            {
              v151 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
              v152 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
              v461[0] = 0;
              v461[1] = &IID_IUnknown;
              v462 = 0;
              v463 = v152;
              v464 = v151;
              v465 = 0;
              v466 = 0;
              v999 = v467;
              v467[0] = 0;
              v467[1] = 0;
              v467[2] = -1;
              v467[3] = 0;
              v467[4] = 0;
              v467[5] = 0;
              v468 &= ~1u;
              COledbError::RaiseTypeWarning(
                (COledbError *)v461,
                L"SSPROP_COLUMNLEVELCOLLATION",
                *(_WORD *)(v144 + 48),
                0xBu);
              v1000 = v465;
              operator delete[](v465);
              v141 = v265;
            }
          }
          goto LABEL_344;
        case 5:
          if ( !*(_DWORD *)(v144 + 8) )
          {
            v153 = *(_WORD *)(v144 + 48);
            if ( v153 )
            {
              if ( v153 == 8 )
              {
                StringCchCopyW((wchar_t *)a3 + 16, 0x81u, *(const wchar_t **)(v144 + 56));
              }
              else
              {
                v154 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
                v155 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
                v469[0] = 0;
                v469[1] = &IID_IUnknown;
                v470 = 0;
                v471 = v155;
                v472 = v154;
                v473 = 0;
                v474 = 0;
                v1001 = v475;
                v475[0] = 0;
                v475[1] = 0;
                v475[2] = -1;
                v475[3] = 0;
                v475[4] = 0;
                v475[5] = 0;
                v476 &= ~1u;
                COledbError::RaiseTypeWarning((COledbError *)v469, L"SSPROP_CHARACTERSET", *(_WORD *)(v144 + 48), 8u);
                v1002 = v473;
                operator delete[](v473);
                v141 = v265;
              }
            }
          }
          goto LABEL_344;
        case 6:
          if ( !*(_DWORD *)(v144 + 8) )
          {
            v156 = *(_WORD *)(v144 + 48);
            if ( v156 )
            {
              if ( v156 == 8 )
              {
                StringCchCopyW((wchar_t *)a3 + 145, 0x81u, *(const wchar_t **)(v144 + 56));
              }
              else
              {
                v157 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
                v158 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
                v477[0] = 0;
                v477[1] = &IID_IUnknown;
                v478 = 0;
                v479 = v158;
                v480 = v157;
                v481 = 0;
                v482 = 0;
                v1003 = v483;
                v483[0] = 0;
                v483[1] = 0;
                v483[2] = -1;
                v483[3] = 0;
                v483[4] = 0;
                v483[5] = 0;
                v484 &= ~1u;
                COledbError::RaiseTypeWarning((COledbError *)v477, L"SSPROP_SORTORDER", *(_WORD *)(v144 + 48), 8u);
                v1004 = v481;
                operator delete[](v481);
                v141 = v265;
              }
            }
          }
          goto LABEL_344;
        case 7:
          if ( *(_DWORD *)(v144 + 8) )
            goto LABEL_344;
          v159 = *(_WORD *)(v144 + 48);
          if ( !v159 )
            goto LABEL_344;
          if ( v159 != 8 )
          {
            v160 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
            v161 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
            v485[0] = 0;
            v485[1] = &IID_IUnknown;
            v486 = 0;
            v487 = v161;
            v488 = v160;
            v489 = 0;
            v490 = 0;
            v1005 = v491;
            v491[0] = 0;
            v491[1] = 0;
            v491[2] = -1;
            v491[3] = 0;
            v491[4] = 0;
            v491[5] = 0;
            v492 &= ~1u;
            COledbError::RaiseTypeWarning((COledbError *)v485, L"SSPROP_CURRENTCOLLATION", *(_WORD *)(v144 + 48), 8u);
            v1006 = v489;
            operator delete[](v489);
            v141 = v265;
LABEL_344:
            v271 = ++v142;
            v143 = v142;
            continue;
          }
          if ( CPolybaseFeatureManager::IsPolybaseProvisioned((CPolybaseFeatureManager *)&g_PolybaseFeatureManager, 1) )
          {
            v162 = !FUseReplicatedServerContext();
            v163 = qword_102ECFB00;
            v164 = qword_102ECFB00 + 14864;
            if ( !v162 )
              v164 = qword_102ECFB00 + 28520;
            v1007 = v164;
            if ( *(_BYTE *)(v164 + 13645) )
            {
LABEL_337:
              if ( *((_BYTE *)this + 141) )
              {
                *((_BYTE *)a3 + 5) |= 8u;
                goto LABEL_344;
              }
LABEL_339:
              v166 = *(const wchar_t **)(v141 + 72LL * v142 + 56);
              v1008 = v166;
              v167 = -1;
              do
                ++v167;
              while ( v166[v167] );
              v326 = 2 * v167;
              FResolveCollation(v166, 2 * v167, &v304);
              v326 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset);
              v325 = v326;
              v168 = *(_DWORD *)CRelOp_Query::DBDataCollation(SystemThread_TlsIndex, v311);
              *((_BYTE *)a3 + 5) &= ~8u;
              v169 = 0;
              if ( v168 == v304 )
                v169 = 8;
              *((_BYTE *)a3 + 5) |= v169;
              v140 = v272;
              v141 = v269;
              v265 = v269;
              v142 = v271;
              goto LABEL_344;
            }
          }
          else
          {
            v163 = qword_102ECFB00;
          }
          if ( !*(_DWORD *)(v163 + 14504) )
            goto LABEL_339;
          SQLFEModeInspector = (unsigned __int8 (__fastcall ***)(_QWORD))GetSQLFEModeInspector();
          if ( !(**SQLFEModeInspector)(SQLFEModeInspector) )
            goto LABEL_339;
          goto LABEL_337;
        default:
          goto LABEL_344;
      }
    }
    break;
  }
  v170 = (unsigned int)++v276;
  if ( v277
    && v270 > 3
    && (v171 = &v277[32 * v170 + 12], v1011 = v171, *(_QWORD *)v171 == *(_QWORD *)&DBPROPSET_SQLSERVERDBINIT.Data1)
    && *((_QWORD *)v171 + 1) == *(_QWORD *)DBPROPSET_SQLSERVERDBINIT.Data4 )
  {
    v172 = 32LL * (unsigned int)v170;
    v173 = *(_DWORD *)&v277[v172 + 8];
    v272 = v173;
    v174 = *(_QWORD *)&v277[v172];
    v266 = v174;
  }
  else
  {
    v173 = 0;
    v272 = 0;
    v174 = 0;
    v266 = 0;
  }
  v271 = 0;
  for ( j = 0; j < v173; v271 = j )
  {
    v176 = v174 + 72LL * j;
    if ( *(_DWORD *)v176 == 16 && !*(_DWORD *)(v176 + 8) )
    {
      if ( *(_WORD *)(v176 + 48) == 11 )
      {
        *((_BYTE *)a3 + 3) = *((_BYTE *)a3 + 3) & 0xBF | (*(_WORD *)(v176 + 56) != 0 ? 0x40 : 0);
      }
      else
      {
        v177 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
        v178 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
        v493[0] = 0;
        v493[1] = &IID_IUnknown;
        v494 = 0;
        v495 = v178;
        v496 = v177;
        v497 = 0;
        v498 = 0;
        v1012 = v499;
        v499[0] = 0;
        v499[1] = 0;
        v499[2] = -1;
        v499[3] = 0;
        v499[4] = 0;
        v499[5] = 0;
        v500 &= ~1u;
        COledbError::RaiseTypeWarning((COledbError *)v493, L"SSPROP_SESS_MARS_ENABLED", *(_WORD *)(v176 + 48), 0xBu);
        v310 = v497;
        operator delete[](v497);
        v174 = v266;
      }
    }
    ++j;
  }
  if ( (*(_BYTE *)a3 & 0x40) != 0 )
    *((_BYTE *)a3 + 3) |= 0x20u;
  v287 = *((_BYTE *)qword_102ECFB10 + 915);
  if ( (v287 & 1) != 0
    || (v285 = 0,
        v179 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset,
        *(_QWORD *)v179)
    && (v180 = *(struct CSessionTraceFlags ***)(*(_QWORD *)v179 + 56LL), *v180)
    && CSessionTraceFlags::CheckSessionTraceInternal(*v180, 0x1C98u) )
  {
    *((_BYTE *)a3 + 3) &= ~0x40u;
  }
  if ( !(*((_BYTE *)qword_102ECFB10 + 1158) >> 7) )
  {
    v181 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    if ( *(_QWORD *)v181 && (v182 = *(struct CSessionTraceFlags ***)(*(_QWORD *)v181 + 56LL), (v183 = *v182) != 0) )
    {
      v305 = *v182;
      if ( !CSessionTraceFlags::CheckSessionTraceInternal(v183, 0x2437u) )
        goto LABEL_372;
    }
    else
    {
      v305 = 0;
LABEL_372:
      if ( (*(_BYTE *)a3 & 0x40) != 0 )
        *((_BYTE *)this + 149) |= 8u;
    }
  }
  v184 = *((_DWORD *)this + 36);
  if ( (v184 & 0x80u) != 0 )
  {
    v185 = *((_BYTE *)this + 149) & 1;
    v282 = 1;
    *((_BYTE *)a3 + 2) &= ~4u;
    *((_BYTE *)a3 + 2) |= 4 * v185;
    v184 = *((_DWORD *)this + 36);
  }
  else
  {
    v282 = 0;
  }
  if ( (v184 & 0x20) != 0 )
  {
    v186 = (*((_BYTE *)this + 148) & 0x20) != 0;
    v280 = 1;
    *((_BYTE *)a3 + 5) &= ~1u;
    *((_BYTE *)a3 + 5) |= v186;
    v184 = *((_DWORD *)this + 36);
  }
  else
  {
    v280 = 0;
  }
  if ( (v184 & 0x10) != 0 )
  {
    v187 = (*((_BYTE *)this + 148) & 0x10) != 0;
    v281 = 1;
    *((_BYTE *)a3 + 4) &= ~0x80u;
    *((_BYTE *)a3 + 4) |= v187 << 7;
    if ( v187 )
    {
      *(_BYTE *)a3 &= ~1u;
      v188 = *(_BYTE *)a3 & 0xFD;
      *(_BYTE *)a3 = v188;
      v188 &= ~4u;
      *(_BYTE *)a3 = v188;
      v188 &= ~8u;
      *(_BYTE *)a3 = v188;
      v188 &= ~0x10u;
      *(_BYTE *)a3 = v188;
      v188 &= ~0x20u;
      *(_BYTE *)a3 = v188;
      v188 &= ~0x40u;
      *(_BYTE *)a3 = v188;
      *(_BYTE *)a3 = v188 & 0x7F;
      *((_BYTE *)a3 + 1) &= ~1u;
      v189 = *((_BYTE *)a3 + 1) & 0xFD;
      *((_BYTE *)a3 + 1) = v189;
      v189 &= ~8u;
      *((_BYTE *)a3 + 1) = v189;
      *((_BYTE *)a3 + 2) &= ~1u;
      v190 = *((_BYTE *)a3 + 2);
      v189 &= ~0x40u;
      *((_BYTE *)a3 + 1) = v189;
      v189 &= ~0x80u;
      *((_BYTE *)a3 + 1) = v189;
      *((_BYTE *)a3 + 1) = v189 & 0xDF;
      v190 &= ~2u;
      *((_BYTE *)a3 + 2) = v190;
      v190 &= ~4u;
      *((_BYTE *)a3 + 2) = v190;
      *((_BYTE *)a3 + 6) &= ~2u;
      v190 &= ~8u;
      *((_BYTE *)a3 + 2) = v190;
      v190 &= ~0x10u;
      *((_BYTE *)a3 + 2) = v190;
      v190 &= ~0x20u;
      *((_BYTE *)a3 + 2) = v190;
      v190 &= ~0x40u;
      *((_BYTE *)a3 + 2) = v190;
      *((_BYTE *)a3 + 2) = v190 & 0x7F;
    }
  }
  else
  {
    v281 = 0;
  }
  v191 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v192 = *(struct Worker **)(v191 + 256);
  if ( !v192 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v192 = *(struct Worker **)(v191 + 256);
  }
  if ( *((_DWORD *)v192 + 139) )
    ExceptionPostCatchActions(v192);
  for ( k = 0; k < v270; ++k )
  {
    v194 = 32LL * k;
    v195 = *(_DWORD *)&v277[v194 + 8];
    v196 = *(VARIANTARG **)&v277[v194];
    if ( v195 )
    {
      v197 = v196 + 2;
      v198 = v195;
      do
      {
        VariantClear(v197);
        v197 += 3;
        --v198;
      }
      while ( v198 );
    }
    TaskFree(v196);
  }
  TaskFree(v277);
  v1057[0] = 130;
  v1057[1] = 127;
  v1057[2] = 14;
  v1057[3] = 34;
  v1057[4] = 117;
  v1057[5] = 137;
  v1057[6] = 139;
  v1057[7] = 136;
  v1057[8] = 73;
  v1057[9] = 89;
  v1057[10] = 90;
  v1057[11] = 102;
  v1057[12] = 187;
  v1057[13] = 201;
  v293 = 0;
  v1051 = v1057;
  v1052 = 14;
  v1053 = DBPROPSET_ROWSET;
  v199 = COledbConnect::FSupportsUms(this);
  SOS_Task::AutoSwitchPreemptive::AutoSwitchPreemptive(&v1041, 536871512, !v199);
  v200 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, _DWORD **, unsigned int *, void ***, void **))v295->lpVtbl[1].AddRef)(
           v295,
           1,
           &v1051,
           &v270,
           &v286,
           &v308);
  v310 = v1043;
  if ( v1043[0] )
  {
    if ( v1043[1] )
      *(_DWORD *)(v1044 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v1044 + 608) + 16LL))(
        *(_QWORD *)(v1044 + 608),
        v1044,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)v1045);
  *(_DWORD *)(v1042 + 616) &= ~v1041;
  if ( (int)(v200 + 0x80000000) >= 0 && v200 != -2147217887 )
  {
    _mm_lfence();
    v201 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
    v202 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
    v327[0] = v295;
    v327[1] = &IID_IDBProperties;
    v328 = v200;
    v329 = v202;
    v330 = v201;
    v331 = 0;
    v332 = 0;
    v333 = 0;
    v334 = -1;
    v335 = 0;
    v336 = 0;
    v337 &= ~1u;
    if ( COledbError::FPrintSQLServerError((COledbError *)v327) )
      ex_raise(73, 72, 25, 3);
    COledbError::PrintMsgUsingHRESULT((COledbError *)v327);
    ex_raise(73, 72, 16, 4, v329, v330);
    operator delete[](v331);
  }
  if ( v270 != 1 )
  {
    v203 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
    v204 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
    v770[0] = 0;
    v770[1] = &IID_IUnknown;
    v771 = 0;
    v772 = v204;
    v773 = v203;
    v774 = 0;
    v775 = 0;
    v776 = 0;
    v777 = 0;
    v778 = -1;
    v779 = 0;
    v780 = 0;
    v781 = 0;
    v782 &= ~1u;
    COledbError::RaiseDataWarning((COledbError *)v770, L"number of property info set", L"1");
    operator delete[](v774);
  }
  v205 = v286;
  if ( !v286 )
  {
    v206 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
    v207 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
    v783[0] = 0;
    v783[1] = &IID_IUnknown;
    v784 = 0;
    v785 = v207;
    v786 = v206;
    v787 = 0;
    v788 = 0;
    v789 = 0;
    v790 = 0;
    v791 = -1;
    v792 = 0;
    v793 = 0;
    v794 = 0;
    v795 &= ~1u;
    COledbError::RaiseDataWarning((COledbError *)v783, L"property info sets", L"not NULL");
    operator delete[](v787);
    v205 = v286;
  }
  if ( *(void **)((char *)v205 + 12) != *(void **)&DBPROPSET_ROWSET.Data1
    || *(void **)((char *)v205 + 20) != *(void **)DBPROPSET_ROWSET.Data4 )
  {
    v208 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
    v209 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
    v796[0] = 0;
    v796[1] = &IID_IUnknown;
    v797 = 0;
    v798 = v209;
    v799 = v208;
    v800 = 0;
    v801 = 0;
    v802 = 0;
    v803 = 0;
    v804 = -1;
    v805 = 0;
    v806 = 0;
    v807 = 0;
    v808 &= ~1u;
    COledbError::RaiseDataWarning((COledbError *)v796, L"guidPropertySet", L"DBPROPSET_ROWSET");
    operator delete[](v800);
    v205 = v286;
  }
  if ( !*((_DWORD *)v205 + 2) )
  {
    v210 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
    v211 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
    v809[0] = 0;
    v809[1] = &IID_IUnknown;
    v810 = 0;
    v811 = v211;
    v812 = v210;
    v813 = 0;
    v814 = 0;
    v815 = 0;
    v816 = 0;
    v817 = -1;
    v818 = 0;
    v819 = 0;
    v820 = 0;
    v821 &= ~1u;
    COledbError::RaiseDataWarning((COledbError *)v809, L"number of DBPROPSET_ROWSET properties", L"greater than 0");
    operator delete[](v813);
    v205 = v286;
  }
  v272 = *((_DWORD *)v205 + 2);
  v212 = (char *)*v205;
  v293 = *v205;
  v213 = 0;
  v271 = 0;
  v214 = 0;
  while ( 2 )
  {
    if ( (unsigned int)v214 < v272 )
    {
      v215 = &v212[48 * v214];
      switch ( *((_DWORD *)v215 + 2) )
      {
        case 0x49:
          if ( (*((_DWORD *)v215 + 3) & 0x440) == 0x440 )
            *((_BYTE *)a3 + 4) |= 1u;
          goto LABEL_450;
        case 0x59:
          if ( (*((_DWORD *)v215 + 3) & 0x440) == 0x440 )
            v273 = 1;
          goto LABEL_450;
        case 0x5A:
          if ( (*((_DWORD *)v215 + 3) & 0x440) == 0x440 )
            v274 = 1;
          goto LABEL_450;
        case 0x66:
          if ( (*((_DWORD *)v215 + 3) & 0x440) == 0x440 )
            v275 = 1;
          goto LABEL_450;
        case 0x75:
          if ( (*((_DWORD *)v215 + 3) & 0x400) == 0 )
            *((_BYTE *)a3 + 5) &= ~2u;
          goto LABEL_450;
        case 0x88:
          v216 = *((_DWORD *)v215 + 3);
          if ( v216 && (v216 & 0x400) != 0 )
          {
            if ( (*((_BYTE *)a3 + 556) & 1) != 0 )
              goto LABEL_418;
            v221 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
            v222 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
            v835[0] = 0;
            v835[1] = &IID_IUnknown;
            v836 = 0;
            v837 = v222;
            v838 = v221;
            v839 = 0;
            v840 = 0;
            v841 = 0;
            v842 = 0;
            v843 = -1;
            v844 = 0;
            v845 = 0;
            v846 = 0;
            v847 &= ~1u;
            COledbError::RaiseConsistencyWarning((COledbError *)v835, L"DBPROP_ILockBytes", L"DBPROPVAL_SS_ILOCKBYTES");
            operator delete[](v839);
          }
          goto LABEL_450;
        case 0x89:
          v216 = *((_DWORD *)v215 + 3);
          if ( v216 && (v216 & 0x400) != 0 )
          {
            if ( (*((_BYTE *)a3 + 556) & 4) != 0 )
              goto LABEL_418;
            v217 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
            v218 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
            v822[0] = 0;
            v822[1] = &IID_IUnknown;
            v823 = 0;
            v824 = v218;
            v825 = v217;
            v826 = 0;
            v827 = 0;
            v828 = 0;
            v829 = 0;
            v830 = -1;
            v831 = 0;
            v832 = 0;
            v833 = 0;
            v834 &= ~1u;
            COledbError::RaiseConsistencyWarning(
              (COledbError *)v822,
              L"DBPROP_ISequentialStream",
              L"DBPROPVAL_SS_ISEQUENTIALSTREAM");
            operator delete[](v826);
          }
          goto LABEL_450;
        case 0x8B:
          v216 = *((_DWORD *)v215 + 3);
          if ( v216 && (v216 & 0x400) != 0 )
          {
            if ( (*((_BYTE *)a3 + 556) & 2) != 0 )
            {
LABEL_418:
              if ( (v216 & 0x100) != 0 )
                *((_BYTE *)a3 + 3) |= 4u;
            }
            else
            {
              v219 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
              v220 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
              v757[0] = 0;
              v757[1] = &IID_IUnknown;
              v758 = 0;
              v759 = v220;
              v760 = v219;
              v761 = 0;
              v762 = 0;
              v763 = 0;
              v764 = 0;
              v765 = -1;
              v766 = 0;
              v767 = 0;
              v768 = 0;
              v769 &= ~1u;
              COledbError::RaiseConsistencyWarning((COledbError *)v757, L"DBPROP_IStream", L"DBPROPVAL_SS_ISTREAM");
              operator delete[](v761);
            }
          }
          goto LABEL_450;
        case 0xBB:
          if ( (*((_DWORD *)v215 + 3) & 0x440) == 0x440 )
            *((_BYTE *)a3 + 4) |= 0x10u;
          goto LABEL_450;
        case 0xC9:
          if ( (*((_BYTE *)qword_102ECFB10 + 915) & 2) != 0 )
            goto LABEL_447;
          v283 = 0;
          v223 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset);
          if ( v223 && (v224 = **(struct CSessionTraceFlags ***)(v223 + 56)) != 0 )
            v225 = CSessionTraceFlags::CheckSessionTraceInternal(v224, 0x1C99u);
          else
            v225 = v283;
          v212 = (char *)v293;
          if ( v225 )
          {
            v213 = v271;
LABEL_447:
            *((_BYTE *)a3 + 5) &= ~0x40u;
          }
          else
          {
            v213 = v271;
            if ( (v293[12 * v271 + 3] & 0x440) == 0x440 )
              *((_BYTE *)a3 + 5) |= 0x40u;
          }
LABEL_450:
          v271 = ++v213;
          v214 = v213;
          continue;
        default:
          goto LABEL_450;
      }
    }
    break;
  }
  if ( v273 == 1 && v274 == 1 && v275 == 1 )
    *((_BYTE *)a3 + 4) |= 2u;
  v226 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v227 = *(struct Worker **)(v226 + 256);
  if ( !v227 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v227 = *(struct Worker **)(v226 + 256);
  }
  if ( *((_DWORD *)v227 + 139) )
    ExceptionPostCatchActions(v227);
  v228 = v272;
  if ( v272 )
  {
    v229 = 0;
    v230 = v293;
    v231 = v293 + 3;
    do
    {
      if ( *v231 )
        VariantClear((VARIANTARG *)&v230[12 * v229 + 6]);
      ++v229;
      v231 += 12;
    }
    while ( v229 < v228 );
  }
  TaskFree(*v286);
  TaskFree(v286);
  TaskFree(v308);
  v232 = v295;
  v295 = 0;
  ((void (__fastcall *)(struct IUnknown *))v232->lpVtbl->Release)(v232);
  v294 = 0;
  if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v289->lpVtbl->QueryInterface)(
         v289,
         &IID_IDBInfo,
         &v294) >= 0 )
  {
    v1054[0] = 3;
    v1054[1] = 27;
    v1054[2] = 15;
    v284 = 0;
    v296 = 0;
    v233 = COledbConnect::FSupportsUms(this);
    SOS_Task::AutoSwitchPreemptive::AutoSwitchPreemptive(&v1046, 536871510, !v233);
    v234 = (*(__int64 (__fastcall **)(__int64, __int64, _DWORD *, char *, _DWORD **, void **))(*(_QWORD *)v294 + 32LL))(
             v294,
             3,
             v1054,
             v312,
             &v284,
             &v296);
    v310 = v1048;
    if ( v1048[0] )
    {
      if ( v1048[1] )
        *(_DWORD *)(v1049 + 800) |= 0x800u;
      else
        (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v1049 + 608) + 16LL))(
          *(_QWORD *)(v1049 + 608),
          v1049,
          1);
    }
    SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)v1050);
    *(_DWORD *)(v1047 + 616) &= ~v1046;
    if ( v234 >= 0 )
    {
      v235 = (_WORD **)v284;
      if ( v284[7] )
      {
        if ( v284[6] != 3 )
        {
          v236 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
          v237 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
          v848 = 0;
          v849 = &IID_IUnknown;
          v850 = 0;
          v851 = v237;
          v852 = v236;
          v853 = 0;
          v854 = 0;
          v855 = 0;
          v856 = -1;
          v857 = 0;
          v858 = 0;
          v859 &= ~1u;
          ErrorReportingManager = GetErrorReportingManager();
          IErrorReportingManager::CwchCallFormatToBuffer(
            ErrorReportingManager,
            7425,
            v1071,
            4001,
            v237,
            v236,
            L"the first literal",
            L"DBLITERAL_CATALOG_SEPARATOR");
          SendErrorEventToTrace(v1071);
          operator delete[](0);
          v235 = (_WORD **)v284;
        }
        if ( *v235 )
        {
          v239 = -1;
          do
            ++v239;
          while ( (*v235)[v239] );
          if ( (_DWORD)v239 == 1 )
          {
            *((_WORD *)a3 + 8) = **v235;
          }
          else
          {
            v240 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
            v241 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
            v860 = 0;
            v861 = &IID_IUnknown;
            v862 = 0;
            v863 = v241;
            v864 = v240;
            v865 = 0;
            v866 = 0;
            v867 = 0;
            v868 = -1;
            v869 = 0;
            v870 = 0;
            v871 &= ~1u;
            v242 = GetErrorReportingManager();
            IErrorReportingManager::CwchCallFormatToBuffer(v242, 7425, v1072, 4001, v241, v240, L"literal length", L"1");
            SendErrorEventToTrace(v1072);
            operator delete[](0);
            v235 = (_WORD **)v284;
            *((_WORD *)a3 + 8) = **(_WORD **)v284;
          }
        }
        else
        {
          *((_WORD *)a3 + 8) = 0;
        }
      }
      if ( *((_DWORD *)v235 + 17) )
      {
        if ( *((_DWORD *)v235 + 16) != 27 )
        {
          v243 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
          v244 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
          v872 = 0;
          v873 = &IID_IUnknown;
          v874 = 0;
          v875 = v244;
          v876 = v243;
          v877 = 0;
          v878 = 0;
          v879 = 0;
          v880 = -1;
          v881 = 0;
          v882 = 0;
          v883 &= ~1u;
          v245 = GetErrorReportingManager();
          IErrorReportingManager::CwchCallFormatToBuffer(
            v245,
            7425,
            v1073,
            4001,
            v244,
            v243,
            L"the second literal",
            L"DBLITERAL_SCHEMA_SEPARATOR");
          SendErrorEventToTrace(v1073);
          operator delete[](0);
          v235 = (_WORD **)v284;
        }
        v246 = v235[5];
        if ( v246 )
        {
          v247 = -1;
          do
            ++v247;
          while ( v246[v247] );
          if ( (_DWORD)v247 != 1 )
          {
            v248 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
            v249 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
            v884 = 0;
            v885 = &IID_IUnknown;
            v886 = 0;
            v887 = v249;
            v888 = v248;
            v889 = 0;
            v890 = 0;
            v891 = 0;
            v892 = -1;
            v893 = 0;
            v894 = 0;
            v895 &= ~1u;
            v250 = GetErrorReportingManager();
            IErrorReportingManager::CwchCallFormatToBuffer(v250, 7425, v1074, 4001, v249, v248, L"literal length", L"1");
            SendErrorEventToTrace(v1074);
            operator delete[](0);
            v235 = (_WORD **)v284;
          }
          v251 = *v235[5];
        }
        else
        {
          v251 = 0;
        }
      }
      else
      {
        v251 = *((_WORD *)a3 + 8);
      }
      *((_WORD *)v313 + 6) = v251;
      if ( *((_DWORD *)v235 + 27) )
      {
        if ( *((_DWORD *)v235 + 26) != 15 )
        {
          v252 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
          v253 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
          v896 = 0;
          v897 = &IID_IUnknown;
          v898 = 0;
          v899 = v253;
          v900 = v252;
          v901 = 0;
          v902 = 0;
          v903 = 0;
          v904 = -1;
          v905 = 0;
          v906 = 0;
          v907 &= ~1u;
          v254 = GetErrorReportingManager();
          IErrorReportingManager::CwchCallFormatToBuffer(
            v254,
            7425,
            v1075,
            4001,
            v253,
            v252,
            L"the third literal",
            L"DBLITERAL_QUOTE");
          SendErrorEventToTrace(v1075);
          operator delete[](0);
          v235 = (_WORD **)v284;
        }
        v255 = v235[10];
        if ( v255 )
        {
          v256 = -1;
          do
            ++v256;
          while ( v255[v256] );
          if ( (_DWORD)v256 != 1 )
          {
            v257 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 40LL))(this);
            v258 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)this + 24LL))(this);
            v908 = 0;
            v909 = &IID_IUnknown;
            v910 = 0;
            v911 = v258;
            v912 = v257;
            v913 = 0;
            v914 = 0;
            v915 = 0;
            v916 = -1;
            v917 = 0;
            v918 = 0;
            v919 &= ~1u;
            v259 = GetErrorReportingManager();
            IErrorReportingManager::CwchCallFormatToBuffer(v259, 7425, v1076, 4001, v258, v257, L"literal length", L"1");
            SendErrorEventToTrace(v1076);
            operator delete[](0);
            v235 = (_WORD **)v284;
          }
          *((_WORD *)a3 + 10) = *v235[10];
        }
        else
        {
          *((_WORD *)a3 + 10) = 0;
        }
      }
      v284 = 0;
      TaskFree(v235);
      v260 = v296;
      v296 = 0;
      TaskFree(v260);
    }
    v261 = v294;
    v294 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v261 + 16LL))(v261);
    TaskFree(v296);
    TaskFree(v284);
  }
  v262 = v289;
  v289 = 0;
  ((void (__fastcall *)(struct IUnknown *))v262->lpVtbl->Release)(v262);
  *((_BYTE *)this + 149) ^= (*((_BYTE *)this + 149) ^ (*((_BYTE *)a3 + 3) >> 2)) & 0x10;
  *((_BYTE *)this + 149) ^= (*((_BYTE *)this + 149) ^ (8 * *((_BYTE *)a3 + 1))) & 0x20;
  if ( v294 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v294 + 16LL))(v294);
  if ( v289 )
    ((void (__fastcall *)(struct IUnknown *))v289->lpVtbl->Release)(v289);
  if ( v309 )
    ((void (__fastcall *)(struct IUnknown *))v309->lpVtbl->Release)(v309);
}

```

## disassembly

```asm
0x1016e0a40  push    rbx
0x1016e0a42  push    rsi
0x1016e0a43  push    rdi
0x1016e0a44  push    r12
0x1016e0a46  push    r13
0x1016e0a48  push    r14
0x1016e0a4a  push    r15
0x1016e0a4c  mov     eax, 0D910h
0x1016e0a51  call    _alloca_probe
0x1016e0a56  sub     rsp, rax
0x1016e0a59  mov     [rsp+0D948h+var_C008], 0FFFFFFFFFFFFFFFEh
0x1016e0a65  mov     rax, cs:__security_cookie
0x1016e0a6c  xor     rax, rsp
0x1016e0a6f  mov     [rsp+0D948h+var_48], rax
0x1016e0a77  mov     r15, r8
0x1016e0a7a  mov     r14, rcx
0x1016e0a7d  mov     [rsp+0D948h+var_D808], r8
0x1016e0a85  mov     [rsp+0D948h+var_D838], rcx
0x1016e0a8d  mov     [rsp+0D948h+var_D830], r8
0x1016e0a95  mov     [rsp+0D948h+var_D8E4], 0
0x1016e0a9a  mov     [rsp+0D948h+var_D8E3], 0
0x1016e0a9f  mov     [rsp+0D948h+var_D8E2], 0
0x1016e0aa4  mov     [rsp+0D948h+var_D928], 1; bool
0x1016e0aa9  lea     r13, IID_IUnknown
0x1016e0ab0  mov     r9, r13; struct _GUID *
0x1016e0ab3  mov     r8, rdx; struct IUnknown *
0x1016e0ab6  lea     rdx, IID_IGetDataSource; struct _GUID *
0x1016e0abd  call    ?GetInterface@COledbConnect@@QEBAPEAUIUnknown@@AEBU_GUID@@PEAU2@0_N@Z; COledbConnect::GetInterface(_GUID const &,IUnknown *,_GUID const &,bool)
0x1016e0ac2  mov     rsi, rax
0x1016e0ac5  mov     [rsp+0D948h+var_D820], rax
0x1016e0acd  xor     ebx, ebx
0x1016e0acf  mov     [rsp+0D948h+var_D8A0], rbx
0x1016e0ad7  mov     rcx, r14; this
0x1016e0ada  call    ?FSupportsUms@COledbConnect@@IEBA_NXZ; COledbConnect::FSupportsUms(void)
0x1016e0adf  mov     r8d, ebx
0x1016e0ae2  test    al, al
0x1016e0ae4  setz    r8b
0x1016e0ae8  mov     edx, 20000255h
0x1016e0aed  lea     rcx, [rsp+0D948h+var_BF28]
0x1016e0af5  call    ??0AutoSwitchPreemptive@SOS_Task@@QEAA@W4PWAIT_enum@@H@Z; SOS_Task::AutoSwitchPreemptive::AutoSwitchPreemptive(PWAIT_enum,int)
0x1016e0afa  nop
0x1016e0afb  mov     rax, [rsi]
0x1016e0afe  lea     r8, [rsp+0D948h+var_D8A0]
0x1016e0b06  mov     rdx, r13
0x1016e0b09  mov     rcx, rsi
0x1016e0b0c  call    qword ptr [rax+18h]
0x1016e0b0f  mov     r12d, eax
0x1016e0b12  lea     rax, [rsp+0D948h+var_BF18]
0x1016e0b1a  mov     [rsp+0D948h+var_D840], rax
0x1016e0b22  lea     edi, [rbx+1]
0x1016e0b25  cmp     [rsp+0D948h+var_BF18], ebx
0x1016e0b2c  jz      short loc_1016E0B5C
0x1016e0b2e  mov     rdx, [rsp+0D948h+var_BF10]
0x1016e0b36  mov     rcx, [rdx+260h]
0x1016e0b3d  cmp     [rsp+0D948h+var_BF14], ebx
0x1016e0b44  jz      short loc_1016E0B52
0x1016e0b46  or      dword ptr [rdx+320h], 800h
0x1016e0b50  jmp     short loc_1016E0B5C
0x1016e0b52  mov     rax, [rcx]
0x1016e0b55  mov     r8d, edi
0x1016e0b58  call    qword ptr [rax+10h]
0x1016e0b5b  nop
0x1016e0b5c  lea     rcx, [rsp+0D948h+var_BF08]; this
0x1016e0b64  call    ??1SOS_ExternalAutoWait@@QEAA@XZ; SOS_ExternalAutoWait::~SOS_ExternalAutoWait(void)
0x1016e0b69  nop
0x1016e0b6a  mov     ecx, [rsp+0D948h+var_BF28]
0x1016e0b71  not     ecx
0x1016e0b73  mov     rax, [rsp+0D948h+var_BF20]
0x1016e0b7b  and     [rax+268h], ecx
0x1016e0b81  test    r12d, r12d
0x1016e0b84  jns     loc_1016E0C7E
0x1016e0b8a  lfence
0x1016e0b8d  mov     rax, [r14]
0x1016e0b90  mov     rcx, r14
0x1016e0b93  call    qword ptr [rax+28h]
0x1016e0b96  mov     rdi, rax
0x1016e0b99  mov     rdx, [r14]
0x1016e0b9c  mov     rcx, r14
0x1016e0b9f  call    qword ptr [rdx+18h]
0x1016e0ba2  mov     [rsp+0D948h+var_D7F8], rsi
0x1016e0baa  lea     rcx, IID_IGetDataSource
0x1016e0bb1  mov     [rsp+0D948h+var_D7F0], rcx
0x1016e0bb9  mov     [rsp+0D948h+var_D7E8], r12d
0x1016e0bc1  mov     [rsp+0D948h+var_D7E0], rax
0x1016e0bc9  mov     [rsp+0D948h+var_D7D8], rdi
0x1016e0bd1  mov     [rsp+0D948h+var_D7D0], rbx
0x1016e0bd9  mov     [rsp+0D948h+var_D7C8], rbx
0x1016e0be1  mov     [rsp+0D948h+var_D7C0], ebx
0x1016e0be8  mov     [rsp+0D948h+var_D7BC], 0FFFFFFFFh
0x1016e0bf3  mov     [rsp+0D948h+var_D7B8], rbx
0x1016e0bfb  mov     [rsp+0D948h+var_D7B0], ebx
0x1016e0c02  and     [rsp+0D948h+var_D7AC], 0FEh
0x1016e0c0a  lea     rcx, [rsp+0D948h+var_D7F8]; this
0x1016e0c12  call    ?FPrintSQLServerError@COledbError@@AEAA_NXZ; COledbError::FPrintSQLServerError(void)
0x1016e0c17  mov     edi, 1
0x1016e0c1c  test    al, al
0x1016e0c1e  jz      short loc_1016E0C33
0x1016e0c20  mov     r9d, edi
0x1016e0c23  lea     edx, [rdi+6]
0x1016e0c26  lea     ecx, [rdi+48h]
0x1016e0c29  lea     r8d, [rdi+18h]
0x1016e0c2d  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x1016e0c33  lea     rcx, [rsp+0D948h+var_D7F8]; this
0x1016e0c3b  call    ?PrintMsgUsingHRESULT@COledbError@@AEAAXXZ; COledbError::PrintMsgUsingHRESULT(void)
0x1016e0c40  mov     rax, [rsp+0D948h+var_D7D8]
0x1016e0c48  mov     [rsp+0D948h+var_D920], rax
0x1016e0c4d  mov     rax, [rsp+0D948h+var_D7E0]
0x1016e0c55  mov     qword ptr [rsp+0D948h+var_D928], rax
0x1016e0c5a  mov     r9d, edi
0x1016e0c5d  mov     edx, 7
0x1016e0c62  lea     ecx, [rdx+42h]
0x1016e0c65  lea     r8d, [rdx+9]
0x1016e0c69  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x1016e0c6f  nop
0x1016e0c70  mov     rcx, [rsp+0D948h+var_D7D0]
0x1016e0c78  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1016e0c7e  mov     [rsp+0D948h+var_D820], rbx
0x1016e0c86  mov     rax, [rsi]
0x1016e0c89  mov     rcx, rsi
0x1016e0c8c  call    qword ptr [rax+10h]
0x1016e0c8f  mov     [rsp+0D948h+var_BCF8], 28h ; '('
0x1016e0c9a  mov     [rsp+0D948h+var_BCF4], 29h ; ')'
0x1016e0ca5  mov     [rsp+0D948h+var_BCF0], 60h ; '`'
0x1016e0cb0  mov     [rsp+0D948h+var_BCEC], 61h ; 'a'
0x1016e0cbb  mov     [rsp+0D948h+var_BCE8], 16h
0x1016e0cc6  mov     [rsp+0D948h+var_BCE4], 2Eh ; '.'
0x1016e0cd1  mov     [rsp+0D948h+var_BCE0], 64h ; 'd'
0x1016e0cdc  mov     [rsp+0D948h+var_BCDC], 50h ; 'P'
0x1016e0ce7  mov     [rsp+0D948h+var_BCD8], 54h ; 'T'
0x1016e0cf2  mov     [rsp+0D948h+var_BCD4], 6Fh ; 'o'
0x1016e0cfd  mov     [rsp+0D948h+var_BCD0], 78h ; 'x'
0x1016e0d08  mov     [rsp+0D948h+var_BCCC], 6Dh ; 'm'
0x1016e0d13  mov     [rsp+0D948h+var_BCC8], 24h ; '$'
0x1016e0d1e  mov     [rsp+0D948h+var_BCC4], 53h ; 'S'
0x1016e0d29  mov     [rsp+0D948h+var_BCC0], 120h
0x1016e0d34  mov     [rsp+0D948h+var_BCBC], 0EDh
0x1016e0d3f  mov     [rsp+0D948h+var_BCB8], 0C4h
0x1016e0d4a  mov     [rsp+0D948h+var_BD60], 4
0x1016e0d55  mov     [rsp+0D948h+var_BD5C], 5
0x1016e0d60  mov     [rsp+0D948h+var_BD58], 6
0x1016e0d6b  mov     [rsp+0D948h+var_BD54], 7
0x1016e0d76  mov     eax, 8
0x1016e0d7b  mov     [rsp+0D948h+var_BD50], eax
0x1016e0d82  mov     [rsp+0D948h+var_BD4C], 9
0x1016e0d8d  mov     [rsp+0D948h+var_BD48], 10h
0x1016e0d98  mov     [rsp+0D948h+var_BD44], 14h
0x1016e0da3  mov     [rsp+0D948h+var_BD40], 15h
0x1016e0dae  mov     [rsp+0D948h+var_BD3C], 16h
0x1016e0db9  mov     [rsp+0D948h+var_BD38], 17h
0x1016e0dc4  mov     [rsp+0D948h+var_BD34], 18h
0x1016e0dcf  mov     [rsp+0D948h+var_BD78], 2
0x1016e0dda  mov     [rsp+0D948h+var_BD74], 3
0x1016e0de5  mov     [rsp+0D948h+var_BD70], 4
0x1016e0df0  mov     [rsp+0D948h+var_BD6C], 5
0x1016e0dfb  mov     [rsp+0D948h+var_BD68], 6
0x1016e0e06  mov     [rsp+0D948h+var_BD64], 7
0x1016e0e11  mov     [rsp+0D948h+var_D864], 10h
0x1016e0e1c  mov     [rsp+0D948h+var_D8F0], ebx
0x1016e0e20  mov     [rsp+0D948h+var_D8D8], rbx
0x1016e0e25  lea     rax, [rsp+0D948h+var_BCF8]
0x1016e0e2d  mov     [rsp+0D948h+var_BCA8], rax
0x1016e0e35  mov     [rsp+0D948h+var_BCA0], 11h
0x1016e0e40  movups  xmm0, xmmword ptr cs:DBPROPSET_DATASOURCEINFO.Data1
0x1016e0e47  movups  [rsp+0D948h+var_BC9C], xmm0
0x1016e0e4f  lea     rax, [rsp+0D948h+var_BD60]
0x1016e0e57  mov     [rsp+0D948h+var_BC88], rax
0x1016e0e5f  mov     [rsp+0D948h+var_BC80], 0Ch
0x1016e0e6a  movups  xmm0, xmmword ptr cs:?SQLPROPSET_OPTHINTS@@3U_GUID@@B.Data1; _GUID const SQLPROPSET_OPTHINTS ...
0x1016e0e71  movups  [rsp+0D948h+var_BC7C], xmm0
0x1016e0e79  lea     rax, [rsp+0D948h+var_BD78]
0x1016e0e81  mov     [rsp+0D948h+var_BC68], rax
0x1016e0e89  mov     [rsp+0D948h+var_BC60], 6
0x1016e0e94  movups  xmm0, xmmword ptr cs:DBPROPSET_SQLSERVERDATASOURCEINFO.Data1
0x1016e0e9b  movups  [rsp+0D948h+var_BC5C], xmm0
0x1016e0ea3  mov     [rsp+0D948h+var_D8E0], 3
0x1016e0eab  lea     rax, [rsp+0D948h+var_D864]
0x1016e0eb3  mov     [rsp+0D948h+var_BC48], rax
0x1016e0ebb  mov     [rsp+0D948h+var_BC40], edi
0x1016e0ec2  movups  xmm0, xmmword ptr cs:DBPROPSET_SQLSERVERDBINIT.Data1
0x1016e0ec9  movups  [rsp+0D948h+var_BC3C], xmm0
0x1016e0ed1  mov     [rsp+0D948h+var_D928], 1; bool
0x1016e0ed6  mov     r9, r13; struct _GUID *
0x1016e0ed9  mov     r8, [rsp+0D948h+var_D8A0]; struct IUnknown *
0x1016e0ee1  lea     rdx, IID_IDBProperties; struct _GUID *
0x1016e0ee8  mov     rcx, r14; this
0x1016e0eeb  call    ?GetInterface@COledbConnect@@QEBAPEAUIUnknown@@AEBU_GUID@@PEAU2@0_N@Z; COledbConnect::GetInterface(_GUID const &,IUnknown *,_GUID const &,bool)
0x1016e0ef0  mov     r12, rax
0x1016e0ef3  mov     [rsp+0D948h+var_D878], rax
0x1016e0efb  mov     rcx, r14; this
0x1016e0efe  call    ?FSupportsUms@COledbConnect@@IEBA_NXZ; COledbConnect::FSupportsUms(void)
0x1016e0f03  mov     r8d, ebx
0x1016e0f06  test    al, al
0x1016e0f08  setz    r8b
0x1016e0f0c  mov     edx, 20000257h
0x1016e0f11  lea     rcx, [rsp+0D948h+var_BEC8]
0x1016e0f19  call    ??0AutoSwitchPreemptive@SOS_Task@@QEAA@W4PWAIT_enum@@H@Z; SOS_Task::AutoSwitchPreemptive::AutoSwitchPreemptive(PWAIT_enum,int)
0x1016e0f1e  nop
0x1016e0f1f  mov     rax, [r12]
0x1016e0f23  lea     rcx, [rsp+0D948h+var_D8D8]
0x1016e0f28  mov     qword ptr [rsp+0D948h+var_D928], rcx
0x1016e0f2d  lea     r9, [rsp+0D948h+var_D8F0]
0x1016e0f32  lea     r8, [rsp+0D948h+var_BCA8]
0x1016e0f3a  mov     edx, 4
0x1016e0f3f  mov     rcx, r12
0x1016e0f42  call    qword ptr [rax+18h]
0x1016e0f45  mov     esi, eax
0x1016e0f47  lea     rax, [rsp+0D948h+var_BEB8]
0x1016e0f4f  mov     [rsp+0D948h+var_D840], rax
0x1016e0f57  cmp     [rsp+0D948h+var_BEB8], 0
0x1016e0f5f  jz      short loc_1016E0F90
0x1016e0f61  mov     rdx, [rsp+0D948h+var_BEB0]
0x1016e0f69  mov     rcx, [rdx+260h]
0x1016e0f70  cmp     [rsp+0D948h+var_BEB4], 0
0x1016e0f78  jz      short loc_1016E0F86
0x1016e0f7a  or      dword ptr [rdx+320h], 800h
0x1016e0f84  jmp     short loc_1016E0F90
0x1016e0f86  mov     rax, [rcx]
0x1016e0f89  mov     r8d, edi
0x1016e0f8c  call    qword ptr [rax+10h]
0x1016e0f8f  nop
0x1016e0f90  lea     rcx, [rsp+0D948h+var_BEA8]; this
0x1016e0f98  call    ??1SOS_ExternalAutoWait@@QEAA@XZ; SOS_ExternalAutoWait::~SOS_ExternalAutoWait(void)
0x1016e0f9d  nop
0x1016e0f9e  mov     ecx, [rsp+0D948h+var_BEC8]
0x1016e0fa5  not     ecx
0x1016e0fa7  mov     rax, [rsp+0D948h+var_BEC0]
0x1016e0faf  and     [rax+268h], ecx
0x1016e0fb5  mov     ecx, 80000000h
0x1016e0fba  lea     eax, [rcx+rsi]
0x1016e0fbd  test    ecx, eax
0x1016e0fbf  jnz     loc_1016E10C4
0x1016e0fc5  cmp     esi, 80040E21h
0x1016e0fcb  jz      loc_1016E10C4
0x1016e0fd1  lfence
0x1016e0fd4  mov     rax, [r14]
0x1016e0fd7  mov     rcx, r14
0x1016e0fda  call    qword ptr [rax+28h]
0x1016e0fdd  mov     rdi, rax
0x1016e0fe0  mov     rdx, [r14]
0x1016e0fe3  mov     rcx, r14
0x1016e0fe6  call    qword ptr [rdx+18h]
0x1016e0fe9  mov     [rsp+0D948h+var_D748], r12
0x1016e0ff1  lea     rcx, IID_IDBProperties
0x1016e0ff8  mov     [rsp+0D948h+var_D740], rcx
0x1016e1000  mov     [rsp+0D948h+var_D738], esi
0x1016e1007  mov     [rsp+0D948h+var_D730], rax
0x1016e100f  mov     [rsp+0D948h+var_D728], rdi
0x1016e1017  mov     [rsp+0D948h+var_D720], rbx
0x1016e101f  mov     [rsp+0D948h+var_D718], rbx
0x1016e1027  mov     [rsp+0D948h+var_D710], ebx
0x1016e102e  mov     [rsp+0D948h+var_D70C], 0FFFFFFFFh
0x1016e1039  mov     [rsp+0D948h+var_D708], rbx
0x1016e1041  mov     [rsp+0D948h+var_D700], ebx
0x1016e1048  and     [rsp+0D948h+var_D6FC], 0FEh
0x1016e1050  lea     rcx, [rsp+0D948h+var_D748]; this
0x1016e1058  call    ?FPrintSQLServerError@COledbError@@AEAA_NXZ; COledbError::FPrintSQLServerError(void)
0x1016e105d  test    al, al
0x1016e105f  jz      short loc_1016E1077
0x1016e1061  mov     edx, 48h ; 'H'
0x1016e1066  lea     ecx, [rdx+1]
0x1016e1069  lea     r9d, [rdx-47h]
0x1016e106d  lea     r8d, [rdx-2Fh]
0x1016e1071  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x1016e1077  lea     rcx, [rsp+0D948h+var_D748]; this
0x1016e107f  call    ?PrintMsgUsingHRESULT@COledbError@@AEAAXXZ; COledbError::PrintMsgUsingHRESULT(void)
0x1016e1084  mov     rax, [rsp+0D948h+var_D728]
0x1016e108c  mov     [rsp+0D948h+var_D920], rax
0x1016e1091  mov     rax, [rsp+0D948h+var_D730]
0x1016e1099  mov     qword ptr [rsp+0D948h+var_D928], rax
0x1016e109e  mov     edx, 48h ; 'H'
0x1016e10a3  lea     ecx, [rdx+1]
0x1016e10a6  lea     r9d, [rdx-46h]
0x1016e10aa  lea     r8d, [rdx-38h]
0x1016e10ae  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x1016e10b4  nop
0x1016e10b5  mov     rcx, [rsp+0D948h+var_D720]
0x1016e10bd  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1016e10c3  nop
0x1016e10c4  cmp     [rsp+0D948h+var_D8F0], 4
0x1016e10c9  jz      loc_1016E1192
0x1016e10cf  mov     rax, [r14]
0x1016e10d2  mov     rcx, r14
0x1016e10d5  call    qword ptr [rax+28h]
0x1016e10d8  mov     rdi, rax
0x1016e10db  mov     rdx, [r14]
0x1016e10de  mov     rcx, r14
0x1016e10e1  call    qword ptr [rdx+18h]
0x1016e10e4  mov     [rsp+0D948h+var_D0B8], rbx
0x1016e10ec  mov     [rsp+0D948h+var_D0B0], r13
0x1016e10f4  mov     [rsp+0D948h+var_D0A8], ebx
0x1016e10fb  mov     [rsp+0D948h+var_D0A0], rax
0x1016e1103  mov     [rsp+0D948h+var_D098], rdi
0x1016e110b  mov     [rsp+0D948h+var_D090], rbx
0x1016e1113  mov     [rsp+0D948h+var_D088], ebx
0x1016e111a  lea     rax, [rsp+0D948h+var_D084]
0x1016e1122  mov     [rsp+0D948h+var_BFD0], rax
0x1016e112a  mov     [rsp+0D948h+var_D084], ebx
0x1016e1131  mov     [rsp+0D948h+var_D080], ebx
0x1016e1138  mov     [rsp+0D948h+var_D07C], 0FFFFFFFFh
0x1016e1143  mov     [rsp+0D948h+var_D078], ebx
  ... truncated ...
```
