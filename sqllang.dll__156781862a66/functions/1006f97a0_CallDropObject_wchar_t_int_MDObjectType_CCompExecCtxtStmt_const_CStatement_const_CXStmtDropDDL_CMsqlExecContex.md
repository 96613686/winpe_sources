# CallDropObject(wchar_t *,int,MDObjectType,CCompExecCtxtStmt const *,CStatement const *,CXStmtDropDDL *,CMsqlExecContext *,IEventTargetInfo *,bool *,bool *,CSourceCollection *)

- ea: `0x1006f97a0`
- end: `0x1006fa580`
- name: `?CallDropObject@@YAXPEA_WHW4MDObjectType@@PEBVCCompExecCtxtStmt@@PEBVCStatement@@PEAVCXStmtDropDDL@@PEAVCMsqlExecContext@@PEAVIEventTargetInfo@@PEA_N7PEAVCSourceCollection@@@Z`
- size: `3552`
- prototype: ``
- caller_count: `4`
- callee_count: `54`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1006f9610`
- `0x100b638b0`
- `0x100bbfd90`
- `0x100bc2a60`

## callees

- `0x100401070`
- `0x1004012d0`
- `0x100401340`
- `0x100401433`
- `0x100407620`
- `0x100407bd0`
- `0x100409cb0`
- `0x1004131b0`
- `0x100415d70`
- `0x1004223e0`
- `0x100444d90`
- `0x1004450b0`
- `0x100446380`
- `0x10044b4c0`
- `0x10046cda0`
- `0x10046cf40`
- `0x10046cf70`
- `0x1006eea90`
- `0x1006eeda0`
- `0x1006f6580`
- `0x1006f97a0`
- `0x1006fa590`
- `0x1006fa730`
- `0x1006fad90`
- `0x10075bd10`
- `0x100760630`
- `0x100760b70`
- `0x1007a73c0`
- `0x100b4f0e0`
- `0x100b51560`
- `0x100b527f0`
- `0x100b92dc0`
- `0x100bc2a60`
- `0x100bcb3b0`
- `0x100bcb420`
- `0x100bcb6e0`
- `0x100cbdd60`
- `0x100ce0500`
- `0x100ce06f0`
- `0x100d4b530`
- `0x100dcd6e0`
- `0x100dceed0`
- `0x100dd4220`
- `0x100de4f40`
- `0x100de4fd0`
- `0x100de50b0`
- `0x100de90f0`
- `0x1010fd3e0`
- `0x1011d53b0`
- `0x1012e91e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100b54dd8`
- `KERNEL32!GetLastError` at `0x100b54dd8`
- `sqldk!?g_metadataFactory@@3UMetadataFactory@@A` at `0x100b52bf8`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x100b545d8`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x100b547a9`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x100b54b05`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x100b54bce`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x100b54bf4`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x100b54f0f`
- `sqldk!?m_ProfilerTraceEnabled@CommonGlobalState@@2_NA` at `0x1006f9d7b`
- `sqldk!?CreateExecSql@@YAPEAVIExecSql@@PEAVIMemObj@@PEAVICallerParse@@@Z` at `0x100b5393c`
- `sqldk!?CreateExecSql@@YAPEAVIExecSql@@PEAVIMemObj@@PEAVICallerParse@@@Z` at `0x100b53c96`
- `sqldk!?CreateExecSql@@YAPEAVIExecSql@@PEAVIMemObj@@PEAVICallerParse@@@Z` at `0x100b53fc6`
- `sqldk!?CreateExecSql@@YAPEAVIExecSql@@PEAVIMemObj@@PEAVICallerParse@@@Z` at `0x100b5393c`
- `sqldk!?CreateExecSql@@YAPEAVIExecSql@@PEAVIMemObj@@PEAVICallerParse@@@Z` at `0x100b53c96`
- `sqldk!?CreateExecSql@@YAPEAVIExecSql@@PEAVIMemObj@@PEAVICallerParse@@@Z` at `0x100b53fc6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100b52b86`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100b52b86`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100b533f7`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100b55005`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100b55290`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100b533f7`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100b55005`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100b55290`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100b551a9`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100b551a9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b53096`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b531d0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b53244`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b532f8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b53505`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b535ba`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b535e9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b537fd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b53869`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b538a8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b53902`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b53b5a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b53c0e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b53f33`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b54220`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b542e5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b5432f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b5443f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b54529`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b5495a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b54c92`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b54d7f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b54e1a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b53096`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b531d0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b53244`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b532f8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b53505`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b535ba`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b535e9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b537fd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b53869`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b538a8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b53902`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b53b5a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b53c0e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b53f33`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b54220`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b542e5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b5432f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b5443f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b54529`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b5495a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b54c92`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b54d7f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100b54e1a`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1006f9fef`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100b549cd`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1006f9fef`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100b549cd`
- `sqldk!SystemThread_TlsIndex` at `0x1006f9873`
- `sqldk!SystemThread_TlsIndex` at `0x1006fa394`
- `sqldk!SystemThread_TlsIndex` at `0x100b52a5c`
- `sqldk!SystemThread_TlsIndex` at `0x100b52acc`
- `sqldk!SystemThread_TlsIndex` at `0x100b52b05`
- `sqldk!SystemThread_TlsIndex` at `0x100b52f44`
- `sqldk!SystemThread_TlsIndex` at `0x100b53392`
- `sqldk!SystemThread_TlsIndex` at `0x100b535ff`
- `sqldk!SystemThread_TlsIndex` at `0x100b53708`
- `sqldk!SystemThread_TlsIndex` at `0x100b53c53`
- `sqldk!SystemThread_TlsIndex` at `0x100b53f83`
- `sqldk!SystemThread_TlsIndex` at `0x100b54e4e`
- `sqldk!SystemThread_TlsIndex` at `0x100b54ed5`
- `sqldk!SystemThread_TlsOffset` at `0x1006f987c`
- `sqldk!SystemThread_TlsOffset` at `0x1006fa39d`
- `sqldk!SystemThread_TlsOffset` at `0x100b52a65`
- `sqldk!SystemThread_TlsOffset` at `0x100b52ad5`
- `sqldk!SystemThread_TlsOffset` at `0x100b52b0e`
- `sqldk!SystemThread_TlsOffset` at `0x100b52f4d`
- `sqldk!SystemThread_TlsOffset` at `0x100b5339b`
- `sqldk!SystemThread_TlsOffset` at `0x100b53610`
- `sqldk!SystemThread_TlsOffset` at `0x100b53711`
- `sqldk!SystemThread_TlsOffset` at `0x100b53c5c`
- `sqldk!SystemThread_TlsOffset` at `0x100b53f8c`
- `sqldk!SystemThread_TlsOffset` at `0x100b54e57`
- `sqldk!SystemThread_TlsOffset` at `0x100b54ede`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100b552c6`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100b552c6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100b52a80`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100b533b6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100b55196`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100b52a80`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100b533b6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100b55196`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100b5373f`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100b5373f`
- `sqldk!??_V@YAXPEAX@Z` at `0x1006fa33c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1006fa548`
- `sqldk!??_V@YAXPEAX@Z` at `0x100b52d89`
- `sqldk!??_V@YAXPEAX@Z` at `0x100b52e1c`
- `sqldk!??_V@YAXPEAX@Z` at `0x100b52eb8`
- `sqldk!??_V@YAXPEAX@Z` at `0x100b53021`
- `sqldk!??_V@YAXPEAX@Z` at `0x100b549eb`
- `sqldk!??_V@YAXPEAX@Z` at `0x1006fa33c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1006fa548`
- `sqldk!??_V@YAXPEAX@Z` at `0x100b52d89`
- `sqldk!??_V@YAXPEAX@Z` at `0x100b52e1c`
- `sqldk!??_V@YAXPEAX@Z` at `0x100b52eb8`
- `sqldk!??_V@YAXPEAX@Z` at `0x100b53021`
- `sqldk!??_V@YAXPEAX@Z` at `0x100b549eb`
- `sqlTsEs!??1CAutoClearXVariant@@UEAA@XZ` at `0x100b5394d`
- `sqlTsEs!??1CAutoClearXVariant@@UEAA@XZ` at `0x100b53b70`
- `sqlTsEs!??1CAutoClearXVariant@@UEAA@XZ` at `0x100b53ca7`
- `sqlTsEs!??1CAutoClearXVariant@@UEAA@XZ` at `0x100b53e92`
- `sqlTsEs!??1CAutoClearXVariant@@UEAA@XZ` at `0x100b53fd7`
- `sqlTsEs!??1CAutoClearXVariant@@UEAA@XZ` at `0x100b541b3`
- `sqlmin!?IsWorkloadIsolationEnabled@DBTABLE@@QEAA_NXZ` at `0x100b54bdb`
- `sqlmin!?IsWorkloadIsolationEnabled@DBTABLE@@QEAA_NXZ` at `0x100b54c4c`
- `sqlmin!?IsWorkloadIsolationEnabled@DBTABLE@@QEAA_NXZ` at `0x100b54d0d`
- `sqlmin!?IsWorkloadIsolationEnabled@DBTABLE@@QEAA_NXZ` at `0x100b54bdb`
- `sqlmin!?IsWorkloadIsolationEnabled@DBTABLE@@QEAA_NXZ` at `0x100b54c4c`
- `sqlmin!?IsWorkloadIsolationEnabled@DBTABLE@@QEAA_NXZ` at `0x100b54d0d`
- `sqlmin!?FHasObjectAccess@@YA_NPEAVIMetadataAccess@@PEAVIMEDObject@@@Z` at `0x100b52fb4`
- `sqlmin!?FHasObjectAccess@@YA_NPEAVIMetadataAccess@@PEAVIMEDObject@@@Z` at `0x100b52fb4`
- `sqlmin!?DBDeleteFileW@@YAHPEB_WPEBUFCBFileBaseDirectives@@@Z` at `0x100b54dca`
- `sqlmin!?DBDeleteFileW@@YAHPEB_WPEBUFCBFileBaseDirectives@@@Z` at `0x100b54dca`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x100b54afc`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x100b54bbe`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x100b54c37`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x100b54cf3`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x100b54afc`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x100b54bbe`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x100b54c37`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x100b54cf3`

## string_xrefs

- `0x100b52b7a`: `rwMode == CMsqlXact::ReadOnly || ctrOption == CMsqlXact::SupportCTR || !m_pMsqlXact->FSupportsCTR ()`

## pseudocode

```c
// Hidden C++ exception states: #wind=19 #try_helpers=1
void __fastcall CallDropObject(
        wchar_t *a1,
        unsigned int a2,
        int a3,
        struct CCompExecCtxt *a4,
        struct CStatement *a5,
        CXStmtDDL *a6,
        __int64 a7,
        __int64 a8,
        char *a9,
        _BYTE *a10,
        CSourceCollection *a11)
{
  wchar_t *v12; // r15
  int v13; // eax
  int v14; // r13d
  __int64 v15; // rcx
  __int64 v16; // r8
  struct IMetadataAccess *v17; // rdi
  char v18; // al
  __int64 v19; // rax
  __int64 v20; // rbx
  struct IMEDObject *TriggerOrEvtNotifObject; // rax
  struct CCompExecCtxt *v22; // rbx
  struct IMEDObject *v23; // r15
  struct IMEDRelation *v24; // rsi
  int v25; // ebx
  unsigned int v26; // r13d
  wchar_t *v27; // rbx
  struct IMetadataAccess *v28; // rdi
  wchar_t *v29; // rbx
  DataVirtualizationResource *v30; // rdx
  unsigned __int8 (__fastcall ***v31)(_QWORD, _QWORD, _BYTE *, _QWORD); // rax
  struct IMetadataAccess *v32; // rbx
  unsigned int v33; // edi
  __int64 v34; // rax
  struct IMemObj *v35; // r10
  unsigned __int64 v36; // rax
  unsigned int v37; // eax
  __int64 v38; // rdx
  struct XDES *v39; // r8
  __int64 v40; // r9
  struct XDES *v41; // rax
  unsigned int v42; // ebx
  unsigned int v43; // ebx
  unsigned int v44; // ebx
  struct IMEDTrigger *v45; // rax
  struct IMEDTrigger *v46; // rax
  struct IMEDTrigger *v47; // rax
  struct IMetadataAccess *v48; // rdi
  struct XDES *v49; // rax
  bool v50; // bl
  CSourceCollection *v51; // rbx
  int v52; // edi
  __int64 v53; // r9
  struct IMemObj *v54; // rsi
  __int64 v55; // r15
  char *v56; // r13
  __int64 v57; // rbx
  struct Worker *v58; // rcx
  unsigned int v59; // ebx
  int v60; // ecx
  struct IMEDDatabase *v61; // rdi
  __int64 v62; // rdx
  int v63; // r8d
  __int64 v64; // r9
  char v65; // al
  void (__fastcall ***v66)(_QWORD, bool); // rcx
  __int64 v67; // rbx
  __int64 v68; // rax
  char v69; // bl
  struct IMetadataAccess *v70; // rax
  __int64 v71; // rcx
  SqlEvtUtil *v72; // rcx
  __int64 v73; // rax
  void (__fastcall ***v74)(_QWORD, __int64); // rcx
  void (__fastcall ***v75)(_QWORD, __int64); // rcx
  unsigned int v76; // ebx
  unsigned int v77; // eax
  __int64 v78; // rax
  void (__fastcall ***v79)(_QWORD, __int64); // rcx
  _QWORD *v80; // rbx
  unsigned int v81; // eax
  __int64 v82; // rdx
  _DWORD *v83; // rax
  int v84; // esi
  _QWORD *v85; // rdi
  int v86; // ebx
  unsigned int v87; // eax
  __int64 v88; // rax
  __int64 v89; // r10
  __int64 v90; // rax
  wchar_t *v91; // rax
  int v92; // edx
  __int64 v93; // r10
  bool v94; // zf
  _QWORD *v95; // rdi
  __int64 (__fastcall **v96)(_QWORD); // rbx
  unsigned int v97; // eax
  __int64 v98; // r9
  struct IMEDSchema *v99; // rbx
  __int64 v100; // rbx
  __int64 v101; // rax
  struct IMemObj *v102; // rbx
  _QWORD *v103; // rsi
  __int64 (__fastcall ***v104)(_QWORD); // rdi
  int v105; // ebx
  const wchar_t **v106; // rax
  struct IMEDSchema *v107; // rdi
  int v108; // ebx
  const wchar_t **v109; // rax
  int v110; // ebx
  const wchar_t **v111; // rax
  __int64 v112; // r11
  __int64 v113; // r8
  int v114; // ecx
  char *v115; // rbx
  __int64 v116; // rdx
  struct XDES **v117; // rax
  struct CSessionTraceFlags *v118; // rcx
  __int64 v119; // rax
  __int64 v120; // rax
  int v121; // eax
  __int64 v122; // rax
  __int64 v123; // rax
  int v124; // eax
  struct IExecSql *ExecSql; // rbx
  unsigned int v126; // eax
  int v127; // edx
  struct IExecSql *v128; // rbx
  unsigned __int8 (__fastcall ***v129)(_QWORD, _QWORD, _BYTE *, _QWORD); // rax
  unsigned int v130; // edi
  __int64 (__fastcall ***v131)(_QWORD); // rax
  __int64 v132; // rax
  __int64 v133; // rax
  __int64 v134; // rax
  __int64 v135; // r8
  struct IMEDObject *v136; // rdi
  __int64 v137; // rax
  int v138; // eax
  const wchar_t *v139; // rax
  __int64 v140; // rbx
  unsigned int v141; // eax
  __int64 v142; // rbx
  _QWORD *v143; // rdi
  unsigned int v144; // eax
  __int64 v145; // r8
  struct IMEDTrigger *v146; // rax
  struct IMEDTrigger *v147; // rax
  struct IMEDTrigger *v148; // rax
  __int64 v149; // rax
  struct IMEDIndex *i; // rbx
  unsigned int v151; // ecx
  struct BaseXact *v152; // rax
  __int64 v153; // rax
  struct XDES *v154; // rax
  int v155; // ebx
  __int64 (__fastcall ***v156)(_QWORD); // rax
  __int64 v157; // rax
  __int64 v158; // rbx
  int v159; // eax
  const wchar_t *v160; // rax
  __int64 v161; // rax
  unsigned __int64 v162; // rax
  void *v163; // rbx
  __int64 v164; // rax
  __int64 v165; // rbx
  _QWORD *v166; // rbx
  __int64 v167; // rax
  int v168; // eax
  __int64 v169; // rax
  unsigned __int16 MasterDbId; // ax
  __int64 v171; // rax
  struct XDES *v172; // rax
  __int64 v173; // rax
  __int64 v174; // rbx
  unsigned int v175; // ebx
  DBTABLE *v176; // rax
  int v177; // eax
  int v178; // ebx
  _QWORD *v179; // rbx
  void (__fastcall ***v180)(_QWORD, _BYTE *, int *, int *); // rax
  QPEvent *v181; // rax
  struct IMEDObject *v182; // r8
  _QWORD *v183; // rbx
  const wchar_t *v184; // rax
  __int64 v185; // rax
  __int64 *v186; // rdx
  __int64 v187; // rax
  __int64 v188; // rcx
  CTmpObjectList *v189; // rcx
  struct TmpObject *v190; // rax
  __int64 v191; // rdx
  __int64 v192; // rdi
  __int64 *v193; // rdi
  __int64 v194; // rax
  __int64 v195; // rbx
  __int64 v196; // rax
  __int64 v197; // rax
  __int64 v198; // rbx
  __int64 v199; // r9
  struct IMEDSchema *v200; // rax
  __int64 v201; // rax
  struct IMetadataAccess *v202; // rcx
  int v203; // ecx
  void (__fastcall ***v204)(_QWORD, __int64); // rcx
  int *v205; // rax
  int *v206; // rbx
  struct CStatement *v207; // [rsp+20h] [rbp-B98h]
  struct CStatement *v208; // [rsp+20h] [rbp-B98h]
  struct CStatement *v209; // [rsp+20h] [rbp-B98h]
  struct CStatement *v210; // [rsp+20h] [rbp-B98h]
  int v211; // [rsp+20h] [rbp-B98h]
  struct CStatement *v212; // [rsp+20h] [rbp-B98h]
  int v213; // [rsp+20h] [rbp-B98h]
  int v214; // [rsp+20h] [rbp-B98h]
  int v215; // [rsp+20h] [rbp-B98h]
  int v216; // [rsp+20h] [rbp-B98h]
  wchar_t *v217; // [rsp+28h] [rbp-B90h]
  wchar_t *v218; // [rsp+28h] [rbp-B90h]
  int v219; // [rsp+28h] [rbp-B90h]
  void *v220; // [rsp+30h] [rbp-B88h]
  bool v221[8]; // [rsp+38h] [rbp-B80h]
  bool *v222; // [rsp+40h] [rbp-B78h]
  __int64 v223; // [rsp+48h] [rbp-B70h]
  int v224; // [rsp+50h] [rbp-B68h]
  char v225[8]; // [rsp+70h] [rbp-B48h] BYREF
  int v226; // [rsp+78h] [rbp-B40h]
  unsigned int v227; // [rsp+80h] [rbp-B38h]
  int v228; // [rsp+84h] [rbp-B34h]
  unsigned int v229; // [rsp+88h] [rbp-B30h]
  struct IMetadataAccess *v230; // [rsp+90h] [rbp-B28h]
  int v231; // [rsp+98h] [rbp-B20h]
  wchar_t *v232; // [rsp+A0h] [rbp-B18h]
  struct IMetadataAccess *v233; // [rsp+A8h] [rbp-B10h]
  struct IMEDRelation *v234; // [rsp+B0h] [rbp-B08h]
  struct IMEDObject *v235; // [rsp+B8h] [rbp-B00h]
  char v236; // [rsp+C0h] [rbp-AF8h]
  char v237; // [rsp+C1h] [rbp-AF7h]
  char v238; // [rsp+C2h] [rbp-AF6h]
  struct IMEDDatabase *v239; // [rsp+C8h] [rbp-AF0h]
  int v240; // [rsp+D0h] [rbp-AE8h]
  __int16 v241; // [rsp+D4h] [rbp-AE4h] BYREF
  unsigned int v242; // [rsp+D8h] [rbp-AE0h] BYREF
  int v243; // [rsp+DCh] [rbp-ADCh]
  struct IMemObj *v244; // [rsp+E0h] [rbp-AD8h]
  struct CCompExecCtxt *v245; // [rsp+E8h] [rbp-AD0h]
  int v246; // [rsp+F0h] [rbp-AC8h]
  struct XDES *v247; // [rsp+F8h] [rbp-AC0h]
  struct IMetadataAccess *v248; // [rsp+100h] [rbp-AB8h]
  char v249; // [rsp+108h] [rbp-AB0h]
  char v250; // [rsp+109h] [rbp-AAFh]
  _BYTE v251[2]; // [rsp+10Ah] [rbp-AAEh] BYREF
  char v252; // [rsp+10Ch] [rbp-AACh]
  unsigned int v253; // [rsp+110h] [rbp-AA8h]
  int v254; // [rsp+114h] [rbp-AA4h] BYREF
  unsigned int v255; // [rsp+118h] [rbp-AA0h]
  int v256; // [rsp+11Ch] [rbp-A9Ch]
  DWORD LastError; // [rsp+120h] [rbp-A98h]
  CSourceCollection *v258; // [rsp+128h] [rbp-A90h]
  char v259; // [rsp+130h] [rbp-A88h]
  char v260; // [rsp+131h] [rbp-A87h]
  bool v261; // [rsp+132h] [rbp-A86h]
  char v262; // [rsp+133h] [rbp-A85h]
  __int64 v263; // [rsp+138h] [rbp-A80h] BYREF
  int v264; // [rsp+140h] [rbp-A78h]
  __int128 v265; // [rsp+148h] [rbp-A70h]
  struct BaseXact *v266; // [rsp+158h] [rbp-A60h]
  unsigned int v267; // [rsp+164h] [rbp-A54h]
  int v268; // [rsp+168h] [rbp-A50h]
  void *v269; // [rsp+170h] [rbp-A48h]
  _QWORD v270[2]; // [rsp+178h] [rbp-A40h] BYREF
  struct CMsqlXact *v271; // [rsp+188h] [rbp-A30h]
  __int64 v272; // [rsp+190h] [rbp-A28h]
  int v273; // [rsp+198h] [rbp-A20h] BYREF
  int v274; // [rsp+19Ch] [rbp-A1Ch]
  int v275; // [rsp+1A0h] [rbp-A18h]
  int v276; // [rsp+1A4h] [rbp-A14h]
  int v277; // [rsp+1A8h] [rbp-A10h]
  int v278; // [rsp+1ACh] [rbp-A0Ch]
  int v279; // [rsp+1B0h] [rbp-A08h]
  struct IMEDSchema *v280; // [rsp+1B8h] [rbp-A00h]
  __int64 v281; // [rsp+1C0h] [rbp-9F8h]
  void *v282; // [rsp+1C8h] [rbp-9F0h]
  struct IMemObj *v283; // [rsp+1D0h] [rbp-9E8h]
  CSourceCollection *v284; // [rsp+1D8h] [rbp-9E0h]
  int v285[2]; // [rsp+1E0h] [rbp-9D8h] BYREF
  char v286; // [rsp+1E8h] [rbp-9D0h]
  char v287; // [rsp+1E9h] [rbp-9CFh]
  int v288; // [rsp+1ECh] [rbp-9CCh]
  __int64 v289; // [rsp+1F0h] [rbp-9C8h]
  int v290; // [rsp+1F8h] [rbp-9C0h]
  _QWORD *v291; // [rsp+218h] [rbp-9A0h]
  CXStmtDDL *v292; // [rsp+220h] [rbp-998h]
  __int64 v293; // [rsp+228h] [rbp-990h]
  _QWORD v294[2]; // [rsp+230h] [rbp-988h] BYREF
  int v295; // [rsp+240h] [rbp-978h]
  __int64 v296; // [rsp+248h] [rbp-970h]
  int v297; // [rsp+250h] [rbp-968h]
  struct CStatement *v298; // [rsp+258h] [rbp-960h]
  CDistributedExecutionContext *v299; // [rsp+260h] [rbp-958h]
  __int64 v300; // [rsp+268h] [rbp-950h]
  CSourceCollection *v301; // [rsp+270h] [rbp-948h]
  __int64 v302; // [rsp+278h] [rbp-940h]
  char *v303; // [rsp+280h] [rbp-938h]
  char *v304; // [rsp+288h] [rbp-930h]
  __int64 v305; // [rsp+290h] [rbp-928h]
  int v306; // [rsp+298h] [rbp-920h]
  int v307; // [rsp+29Ch] [rbp-91Ch]
  __int64 v309; // [rsp+2A8h] [rbp-910h]
  _DWORD *v310; // [rsp+2B0h] [rbp-908h]
  __int64 (__fastcall ***v311)(_QWORD); // [rsp+2B8h] [rbp-900h]
  __int128 v312; // [rsp+2C0h] [rbp-8F8h] BYREF
  __int128 v313; // [rsp+2D0h] [rbp-8E8h]
  __int128 v314; // [rsp+2E0h] [rbp-8D8h]
  char v315[8]; // [rsp+2F0h] [rbp-8C8h] BYREF
  char v316; // [rsp+2F8h] [rbp-8C0h] BYREF
  char v317[7]; // [rsp+2F9h] [rbp-8BFh] BYREF
  _QWORD v318[2]; // [rsp+300h] [rbp-8B8h] BYREF
  int v319; // [rsp+310h] [rbp-8A8h]
  __int128 v320; // [rsp+318h] [rbp-8A0h]
  __int128 v321; // [rsp+328h] [rbp-890h]
  char v322; // [rsp+340h] [rbp-878h] BYREF
  char v323[7]; // [rsp+341h] [rbp-877h] BYREF
  _QWORD v324[2]; // [rsp+348h] [rbp-870h] BYREF
  int v325; // [rsp+358h] [rbp-860h]
  __int128 v326; // [rsp+360h] [rbp-858h]
  __int128 v327; // [rsp+370h] [rbp-848h]
  char v328[8]; // [rsp+380h] [rbp-838h] BYREF
  char v329; // [rsp+388h] [rbp-830h] BYREF
  char v330[7]; // [rsp+389h] [rbp-82Fh] BYREF
  _QWORD v331[2]; // [rsp+390h] [rbp-828h] BYREF
  int v332; // [rsp+3A0h] [rbp-818h]
  __int128 v333; // [rsp+3A8h] [rbp-810h]
  __int128 v334; // [rsp+3B8h] [rbp-800h]
  char v335; // [rsp+3D0h] [rbp-7E8h] BYREF
  char v336[7]; // [rsp+3D1h] [rbp-7E7h] BYREF
  _QWORD v337[2]; // [rsp+3D8h] [rbp-7E0h] BYREF
  int v338; // [rsp+3E8h] [rbp-7D0h]
  __int128 v339; // [rsp+3F0h] [rbp-7C8h]
  __int128 v340; // [rsp+400h] [rbp-7B8h]
  char v341[8]; // [rsp+410h] [rbp-7A8h] BYREF
  char v342; // [rsp+418h] [rbp-7A0h] BYREF
  char v343[7]; // [rsp+419h] [rbp-79Fh] BYREF
  _QWORD v344[2]; // [rsp+420h] [rbp-798h] BYREF
  int v345; // [rsp+430h] [rbp-788h]
  __int128 v346; // [rsp+438h] [rbp-780h]
  __int128 v347; // [rsp+448h] [rbp-770h]
  char v348; // [rsp+460h] [rbp-758h] BYREF
  char v349[7]; // [rsp+461h] [rbp-757h] BYREF
  _QWORD v350[2]; // [rsp+468h] [rbp-750h] BYREF
  int v351; // [rsp+478h] [rbp-740h]
  __int128 v352; // [rsp+480h] [rbp-738h]
  __int128 v353; // [rsp+490h] [rbp-728h]
  _BYTE v354[40]; // [rsp+4A0h] [rbp-718h] BYREF
  struct IExecSql *v355; // [rsp+4C8h] [rbp-6F0h]
  const wchar_t *v356; // [rsp+4D0h] [rbp-6E8h]
  struct IExecSql *v357; // [rsp+4D8h] [rbp-6E0h]
  char *v358; // [rsp+4E0h] [rbp-6D8h]
  _QWORD *v359; // [rsp+4E8h] [rbp-6D0h]
  char *v360; // [rsp+4F0h] [rbp-6C8h]
  _QWORD *v361; // [rsp+4F8h] [rbp-6C0h]
  struct IExecSql *v362; // [rsp+500h] [rbp-6B8h]
  const wchar_t *v363; // [rsp+508h] [rbp-6B0h]
  struct IExecSql *v364; // [rsp+510h] [rbp-6A8h]
  char *v365; // [rsp+518h] [rbp-6A0h]
  _QWORD *v366; // [rsp+520h] [rbp-698h]
  char *v367; // [rsp+528h] [rbp-690h]
  _QWORD *v368; // [rsp+530h] [rbp-688h]
  struct IExecSql *v369; // [rsp+538h] [rbp-680h]
  _QWORD *v370; // [rsp+540h] [rbp-678h]
  _QWORD *v371; // [rsp+548h] [rbp-670h]
  _QWORD *v372; // [rsp+550h] [rbp-668h]
  void *v373; // [rsp+558h] [rbp-660h]
  __int64 v374; // [rsp+560h] [rbp-658h]
  CTmpObjectList *v375; // [rsp+568h] [rbp-650h]
  CSourceCollection *v376; // [rsp+570h] [rbp-648h]
  __int64 v377; // [rsp+578h] [rbp-640h]
  struct IMemObj *v378; // [rsp+580h] [rbp-638h]
  _QWORD *v379; // [rsp+598h] [rbp-620h]
  _QWORD *v380; // [rsp+5A0h] [rbp-618h]
  _QWORD *v381; // [rsp+5A8h] [rbp-610h]
  const wchar_t *v382; // [rsp+5B0h] [rbp-608h]
  struct IExecSql *v383; // [rsp+5B8h] [rbp-600h]
  char *v384; // [rsp+5C0h] [rbp-5F8h]
  _QWORD *v385; // [rsp+5C8h] [rbp-5F0h]
  char *v386; // [rsp+5D0h] [rbp-5E8h]
  _QWORD *v387; // [rsp+5D8h] [rbp-5E0h]
  _OWORD v388[3]; // [rsp+5E0h] [rbp-5D8h] BYREF
  _BYTE v389[848]; // [rsp+610h] [rbp-5A8h] BYREF
  char v390[8]; // [rsp+960h] [rbp-258h] BYREF
  int v391; // [rsp+968h] [rbp-250h]
  char v392; // [rsp+96Dh] [rbp-24Bh]
  _OWORD v393[2]; // [rsp+970h] [rbp-248h] BYREF
  __int128 v394; // [rsp+990h] [rbp-228h]
  char v395[8]; // [rsp+9A0h] [rbp-218h] BYREF
  int v396; // [rsp+9A8h] [rbp-210h]
  char v397[8]; // [rsp+9B0h] [rbp-208h] BYREF
  int v398; // [rsp+9B8h] [rbp-200h]
  char v399[8]; // [rsp+9C0h] [rbp-1F8h] BYREF
  int v400; // [rsp+9C8h] [rbp-1F0h]
  _BYTE v401[16]; // [rsp+9D0h] [rbp-1E8h] BYREF
  _BYTE v402[376]; // [rsp+9E0h] [rbp-1D8h] BYREF
  int v403; // [rsp+B58h] [rbp-60h]
  char v404; // [rsp+B61h] [rbp-57h]

  v377 = -2;
  v227 = a2;
  v12 = a1;
  v232 = a1;
  v226 = a3;
  v245 = a4;
  v298 = a5;
  v292 = a6;
  v302 = a7;
  v305 = a7;
  v293 = a8;
  v303 = a9;
  v304 = a9;
  v258 = a11;
  v271 = *(struct CMsqlXact **)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                          + SystemThread_TlsOffset)
                              + 144LL);
  v278 = (*(unsigned __int8 (**)(void))(*(_QWORD *)v271 + 464LL))();
  v283 = 0;
  v263 = 0;
  v264 = 1;
  v265 = 0;
  if ( a9 )
    *a9 = 1;
  if ( a10 )
    *a10 = 0;
  WParseName::Parse((WParseName *)&v312, v12, a2);
  if ( !(2 * HIDWORD(v314)) || (v13 = 1, **((_WORD **)&v313 + 1) != 35) )
    v13 = 0;
  v240 = v13;
  v279 = v13;
  if ( a7 )
  {
    v244 = *(struct IMemObj **)(a7 + 120);
    v283 = v244;
    CXStmtDropDDL::BeginDropXact(a6, v244, v245, L"DROPOBJ", 14);
    *((_BYTE *)a6 + 241) = 0;
  }
  else
  {
    v67 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v68 = *(_QWORD *)(v67 + 256);
    if ( !v68 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v68 = *(_QWORD *)(v67 + 256);
    }
    v244 = *(struct IMemObj **)(v68 + 1000);
    v283 = v244;
  }
  v231 = 0;
  v229 = 0;
  v255 = 0;
  v272 = 0;
  v246 = 0;
  v256 = 0;
  v269 = 0;
  v239 = 0;
  v14 = 0;
  v277 = 0;
  ExcHandler::ExcHandler((ExcHandler *)v354, 0, 0, 0, hdl_DDLprntbackout, 0);
  v248 = 0;
  if ( a6 )
  {
    (*(void (__fastcall **)(CXStmtDDL *))(*(_QWORD *)a6 + 104LL))(a6);
    if ( (*((_BYTE *)a6 + 176) & 0x20) != 0 )
      v15 = *((_QWORD *)a6 + 14);
    else
      v15 = *((_QWORD *)a6 + 23);
    v266 = (struct BaseXact *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 432LL))(v15);
    v17 = (struct IMetadataAccess *)*((_QWORD *)a6 + 7);
    v230 = v17;
    v233 = v17;
  }
  else
  {
    v264 = 1;
    v247 = *(struct XDES **)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset);
    *(_QWORD *)&v265 = *((_QWORD *)v247 + 18);
    v247 = *(struct XDES **)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset);
    v69 = *((_BYTE *)v247 + 152);
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v265 + 464LL))(v265) )
    {
      if ( v69 && (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v265 + 488LL))(v265) )
        utassert_fail(
          1u,
          "rwMode == CMsqlXact::ReadOnly || ctrOption == CMsqlXact::SupportCTR || !m_pMsqlXact->FSupportsCTR ()",
          "automsqlxact.cpp",
          235,
          0);
      (*(void (__fastcall **)(_QWORD, __int64, __int64, char *))(*(_QWORD *)v265 + 232LL))(
        v265,
        2,
        1,
        (char *)&v263 + 4);
      v264 = 1;
      LODWORD(v263) = 3;
    }
    else
    {
      LODWORD(v222) = v69 != 0;
      *(_QWORD *)v221 = 0;
      LODWORD(v207) = 2;
      (*(void (__fastcall **)(_QWORD, const wchar_t *, __int64))(*(_QWORD *)v265 + 8LL))(v265, L"DROPOBJ", 14);
      LODWORD(v263) = 1;
    }
    v266 = (struct BaseXact *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v265 + 432LL))(v265);
    v70 = (struct IMetadataAccess *)g_metadataFactory(v244, v266, "Sql\\Ntdbms\\msql\\ddl\\drop.cpp", 2165);
    v17 = v70;
    v230 = v70;
    v233 = v70;
    v71 = v309;
    if ( v70 )
      v71 = 0;
    v309 = v71;
    v248 = v70;
    v14 = v277;
  }
  v294[0] = &CTriggerTarget::`vftable';
  v294[1] = v17;
  v295 = 20;
  v296 = 0;
  v291 = v294;
  v268 = 0;
  if ( a6 )
    v18 = *(_BYTE *)(*((_QWORD *)a6 + 4) + 2208LL);
  else
    v18 = 0;
  v225[0] = v18;
  v259 = v18;
  if ( v293 )
  {
    v22 = v245;
    if ( !(*(unsigned int (__fastcall **)(__int64, struct IMetadataAccess *, struct CCompExecCtxt *, _QWORD *))(*(_QWORD *)v293 + 16LL))(
            v293,
            v17,
            v245,
            v294) )
    {
      v268 = 1;
      goto LABEL_162;
    }
    (*(void (__fastcall **)(_QWORD *))(v294[0] + 32LL))(v294);
    TriggerOrEvtNotifObject = SqlEvtUtil::GetTriggerOrEvtNotifObject(
                                v72,
                                (struct IMetadataAccess *)&v312,
                                (const struct WParseName *)v294,
                                (const struct IEventTarget *)1,
                                (int)v207);
  }
  else
  {
    if ( a10 )
    {
      *a10 = 0;
      if ( *((_BYTE *)qword_102EF3550 + 342) )
      {
        v260 = *((_BYTE *)qword_102ECFB10 + 1453) >> 1;
        if ( (v260 & 1) == 0 )
        {
          v388[0] = v312;
          v388[1] = v313;
          v388[2] = v314;
          FindAndKillBlockingTupleMover(v388, L"CallDropObject", 14);
        }
      }
      LOBYTE(v16) = 5;
      v19 = (*(__int64 (__fastcall **)(struct IMetadataAccess *, __int128 *, __int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _BYTE))(*(_QWORD *)v17 + 40LL))(
              v17,
              &v312,
              v16,
              0,
              0,
              0,
              0,
              0,
              0,
              0,
              0);
      v20 = v19;
      if ( v19 )
      {
        (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v19 + 96LL))(v19, v395);
        if ( v396 == 8272 )
        {
          v73 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 296LL))(v20);
          if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73) )
          {
            v74 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)a6 + 7);
            *((_QWORD *)a6 + 7) = 0;
            if ( v74 )
              (**v74)(v74, 1);
            (*(void (__fastcall **)(CXStmtDDL *, _QWORD))(*(_QWORD *)a6 + 16LL))(a6, 0);
            *a10 = 1;
            if ( v248 )
              (**(void (__fastcall ***)(struct IMetadataAccess *, __int64))v248)(v248, 1);
            ExcHandler::~ExcHandler((ExcHandler *)v354);
            operator delete[](0);
            if ( !(_DWORD)v263 )
              return;
            goto LABEL_184;
          }
        }
      }
    }
    v14 = 1;
    LOBYTE(v224) = 0;
    LOBYTE(v16) = 2;
    TriggerOrEvtNotifObject = (struct IMEDObject *)(*(__int64 (__fastcall **)(struct IMetadataAccess *, __int128 *, __int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, int))(*(_QWORD *)v17 + 40LL))(
                                                     v17,
                                                     &v312,
                                                     v16,
                                                     0,
                                                     0,
                                                     0,
                                                     0,
                                                     0,
                                                     0,
                                                     0,
                                                     v224);
    v22 = v245;
  }
  v23 = TriggerOrEvtNotifObject;
  v235 = TriggerOrEvtNotifObject;
  if ( !TriggerOrEvtNotifObject )
  {
    v12 = v232;
LABEL_162:
    v268 = 1;
    if ( v225[0] )
    {
      if ( a6 )
      {
        v75 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)a6 + 7);
        *((_QWORD *)a6 + 7) = 0;
        if ( v75 )
          (**v75)(v75, 1);
        (*(void (__fastcall **)(CXStmtDDL *))(*(_QWORD *)a6 + 112LL))(a6);
        CXStmtDropDDL::CommitDropXact(a6, v22);
      }
      if ( v248 )
        (**(void (__fastcall ***)(struct IMetadataAccess *, __int64))v248)(v248, 1);
      ExcHandler::~ExcHandler((ExcHandler *)v354);
      operator delete[](0);
      if ( !(_DWORD)v263 )
        return;
    }
    else
    {
      LODWORD(v217) = v227;
      LODWORD(v207) = getobjtype(v226);
      ex_callprint_raiseintsqltrycatch(3701, 11, 5, 13087, v207, v217, v12);
      if ( a6 )
      {
        (*(void (__fastcall **)(CXStmtDDL *, _QWORD))(*(_QWORD *)a6 + 16LL))(a6, 0);
        CXStmtDropDDL::RollbackDropXact(a6, v22);
      }
      if ( v248 )
        (**(void (__fastcall ***)(struct IMetadataAccess *, __int64))v248)(v248, 1);
      ExcHandler::~ExcHandler((ExcHandler *)v354);
      operator delete[](0);
      if ( !(_DWORD)v263 )
        return;
    }
LABEL_184:
    CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v263, 0);
    return;
  }
  memset(v393, 0, sizeof(v393));
  v394 = 0;
  v241 = 0;
  memset_0(v402, 0, 0x188u);
  v403 = -1;
  v229 = (**(__int64 (__fastcall ***)(struct IMEDObject *))v23)(v23);
  v231 = (*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v23 + 8LL))(v23);
  v24 = (struct IMEDRelation *)(*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v23 + 120LL))(v23);
  v234 = v24;
  v281 = (*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v23 + 168LL))(v23);
  v239 = (struct IMEDDatabase *)(*(__int64 (__fastcall **)(struct IMetadataAccess *, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(*(_QWORD *)v17 + 56LL))(
                                  v17,
                                  v229,
                                  0,
                                  0,
                                  0,
                                  0);
  (*(void (__fastcall **)(struct IMEDObject *, char *))(*(_QWORD *)v23 + 96LL))(v23, v390);
  if ( v24 )
    (*(void (__fastcall **)(struct IMEDRelation *, _OWORD *))(*(_QWORD *)v24 + 16LL))(v24, v393);
  if ( v281 )
    (*(void (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v281 + 32LL))(v281, &v241);
  if ( v391 == 17985 || v391 == 21318 || v391 == 21574 || v391 == 17232 || v391 == 16724 )
    CheckSnapshotTransactionForDDL(v271);
  if ( (*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v23 + 176LL))(v23) )
  {
    v76 = (*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v23 + 16LL))(v23);
    v77 = (**(__int64 (__fastcall ***)(struct IMEDObject *))v23)(v23);
    LOBYTE(v208) = 0;
    v25 = FCheckAlterDropTriggerPermissions(v17, v77, v23, v76, (_DWORD)v208);
    v228 = v25;
    if ( v14 )
      (*(void (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v23 + 88LL))(v23);
  }
  else
  {
    if ( v240 || (v25 = 0, CDDLPermissions::FHasDropObjectPerms(v17, v23)) )
      v25 = 1;
    v228 = v25;
  }
  v261 = CommonGlobalState::m_ProfilerTraceEnabled;
  if ( CommonGlobalState::m_ProfilerTraceEnabled && (*(_DWORD *)(qword_102ECFB00 + 72) & 0x400000) != 0 )
  {
    v78 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                    + SystemThread_TlsOffset
                    + 8LL);
    if ( v78 )
    {
      v83 = *(_DWORD **)(v78 + 48);
      v310 = v83;
      if ( v83 && !*v83 )
      {
        v276 = 1;
        v23 = v235;
        v84 = *(_DWORD *)((*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v235 + 40LL))(v235) + 8);
        v85 = (_QWORD *)(*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v23 + 40LL))(v23);
        v86 = (*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v23 + 24LL))(v23);
        v87 = (**(__int64 (__fastcall ***)(struct IMEDObject *))v23)(v23);
        LOWORD(v222) = 0;
        *(_DWORD *)v221 = v391;
        v211 = v86;
        v25 = v228;
        AuditObjectEvent(118, 3, (unsigned int)v228, v87, v211, *v85, v84, *(_QWORD *)v221, (_DWORD)v222, 0);
        goto LABEL_191;
      }
    }
    else
    {
      v310 = 0;
    }
    v276 = 0;
    v23 = v235;
    v25 = v228;
LABEL_191:
    v17 = v233;
    v24 = v234;
    v230 = v233;
  }
  if ( v25 )
  {
    v26 = v226;
  }
  else
  {
    if ( v225[0] && !FHasObjectAccess(v17, v23) )
    {
      if ( a6 )
      {
        v79 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)a6 + 7);
        *((_QWORD *)a6 + 7) = 0;
        if ( v79 )
          (**v79)(v79, 1);
        (*(void (__fastcall **)(CXStmtDDL *))(*(_QWORD *)a6 + 112LL))(a6);
        CXStmtDropDDL::CommitDropXact(a6, v245);
      }
      if ( v248 )
        (**(void (__fastcall ***)(struct IMetadataAccess *, __int64))v248)(v248, 1);
      ExcHandler::~ExcHandler((ExcHandler *)v354);
      operator delete[](0);
      if ( (_DWORD)v263 )
        CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v263, 0);
      return;
    }
    v80 = (_QWORD *)(*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v23 + 40LL))(v23);
    (*(void (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v23 + 40LL))(v23);
    v26 = v226;
    v81 = getobjtype(v226);
    LODWORD(v220) = *(_DWORD *)(v82 + 8);
    LODWORD(v218) = v81;
    LODWORD(v208) = 13087;
    ex_raise(37, 1, 14, 20, v208, v218, v220, *v80);
  }
  if ( v26 == 8277 )
  {
    if ( v391 == 8275 || v391 == 21577 )
      goto LABEL_216;
  }
  else
  {
    switch ( v26 )
    {
      case 0x2050u:
        if ( v391 == 18002 || v391 == 8280 )
          goto LABEL_216;
        v94 = v391 == 17232;
        break;
      case 0x4E46u:
        if ( v391 == 18004 || v391 == 17993 || v391 == 21318 || v391 == 21574 )
          goto LABEL_216;
        v94 = v391 == 21321;
        break;
      case 0x5254u:
        v94 = v391 == 16724;
        break;
      default:
        goto LABEL_47;
    }
    if ( v94 )
    {
LABEL_216:
      v26 = v391;
      v226 = v391;
      goto LABEL_48;
    }
  }
LABEL_47:
  if ( v391 == v26 )
  {
LABEL_48:
    v27 = v232;
    goto LABEL_49;
  }
  if ( v26 == 8280 )
  {
    v88 = (*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v23 + 88LL))(v23);
    getuobjtype_dropobject(v88 != 0, v391);
    LODWORD(v222) = getobjtype(v391);
    v27 = v232;
    LODWORD(v220) = v227;
    LODWORD(v208) = v227;
    ex_raise(37, 51, 16, 1, v208, v232, v220, v232, v222, v89);
  }
  else
  {
    v27 = v232;
  }
  v90 = (*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v23 + 88LL))(v23);
  getuobjtype_dropobject(v90 != 0, v391);
  getobjtype(v391);
  v91 = getuobjtype(v26);
  LODWORD(v223) = v92;
  *(_DWORD *)v221 = v227;
  LODWORD(v218) = v227;
  ex_raise(37, 5, 16, 1, v91, v218, v27, *(_QWORD *)v221, v27, v223, v93);
LABEL_49:
  if ( v26 == 8275 )
  {
    v28 = v230;
    goto LABEL_256;
  }
  if ( v26 == 8277 )
  {
    if ( CExecLvlIntCtxt::FTableIsTriggerTarget(*((CExecLvlIntCtxt **)v245 + 16), v229, v231) )
    {
      LODWORD(v218) = v227;
      ex_raise(17, 13, 16, 3, L"DROP TABLE", v218, v27);
    }
    v95 = (_QWORD *)(*(__int64 (__fastcall **)(struct IMetadataAccess *, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(*(_QWORD *)v17 + 56LL))(
                      v17,
                      v229,
                      0,
                      0,
                      0,
                      0);
    v311 = (__int64 (__fastcall ***)(_QWORD))v95;
    v96 = (__int64 (__fastcall **)(_QWORD))*v95;
    v97 = (*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v23 + 24LL))(v23);
    LOBYTE(v98) = 1;
    v99 = (struct IMEDSchema *)((__int64 (__fastcall *)(_QWORD *, _QWORD, _QWORD, __int64))v96[27])(v95, v97, 0, v98);
    v280 = v99;
    if ( ((*(unsigned __int8 (__fastcall **)(struct IMEDRelation *))(*(_QWORD *)v24 + 728LL))(v24)
       || (*(unsigned __int8 (__fastcall **)(struct IMEDRelation *))(*(_QWORD *)v24 + 736LL))(v24))
      && !(*(unsigned __int8 (__fastcall **)(struct IMEDRelation *))(*(_QWORD *)v24 + 784LL))(v24) )
    {
      v100 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v101 = *(_QWORD *)(v100 + 256);
      if ( !v101 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v101 = *(_QWORD *)(v100 + 256);
      }
      v102 = *(struct IMemObj **)(v101 + 1000);
      v378 = v102;
      v297 = 2427;
      v103 = operator new(0x50u, v102, "Sql\\Ntdbms\\msql\\ddl\\drop.cpp", 2427, 3u);
      v379 = v103;
      if ( v103 )
      {
        *v103 = &CObjName::`vftable';
        v103[1] = 0;
        v103[2] = 0;
        v103[3] = 0;
        v103[4] = 0;
        *((_WORD *)v103 + 20) = 0;
        *((_WORD *)v103 + 21) = 0;
        *((_WORD *)v103 + 22) = 0;
        *((_WORD *)v103 + 23) = 0;
        *((_WORD *)v103 + 24) = 0;
        v103[7] = 0;
        *((_WORD *)v103 + 32) = 0;
        v103[9] = v102;
      }
      else
      {
        v103 = 0;
      }
      v380 = v103;
      v104 = v311;
      v105 = *(_DWORD *)((**v311)(v311) + 8);
      v106 = (const wchar_t **)(**v104)(v104);
      CObjName::AddPart((CObjName *)v103, *v106, v105);
      v107 = v280;
      v108 = *(_DWORD *)((**(__int64 (__fastcall ***)(struct IMEDSchema *))v280)(v280) + 8);
      v109 = (const wchar_t **)(**(__int64 (__fastcall ***)(struct IMEDSchema *))v107)(v107);
      CObjName::AddPart((CObjName *)v103, *v109, v108);
      v23 = v235;
      v110 = *(_DWORD *)((*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v235 + 40LL))(v235) + 8);
      v111 = (const wchar_t **)(*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v23 + 40LL))(v23);
      CObjName::AddPart((CObjName *)v103, *v111, v110);
      CObjName::WsFullName((CObjName *)v103);
      LODWORD(v212) = CObjName::CbFullName((CObjName *)v103);
      ex_raise(135, 52, 16, 1, v212, v112);
      v381 = v103;
      if ( v103 )
        (*(void (__fastcall **)(_QWORD *, __int64))*v103)(v103, 1);
      v28 = v233;
      v230 = v233;
      v24 = v234;
      v26 = v226;
      v99 = v280;
    }
    else
    {
      v28 = v230;
    }
    if ( v258 )
      CSourceCollection::AddTableSources(v258, v99, v23, v24);
  }
  else
  {
    v28 = v230;
    if ( v26 != 8278 )
      goto LABEL_56;
  }
  if ( (*(unsigned int (__fastcall **)(struct IMEDRelation *))(*(_QWORD *)v24 + 872LL))(v24) )
  {
    LODWORD(v208) = v227;
    ex_raise(373, 86, 16, 1, v208, v232);
  }
  if ( (BYTE10(v394) & 1) != 0 )
  {
    LODWORD(v208) = v227;
    ex_raise(374, 27, 16, 1, v208, v232);
  }
LABEL_56:
  if ( v26 != 21577 )
  {
LABEL_57:
    v29 = v232;
    goto LABEL_58;
  }
  v113 = 8LL * SystemThread_TlsIndex;
  if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(SystemThread_TlsOffset
                                          + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v113))
                              + 128LL)
                  + 76LL)
      & 0x80000) != 0
    || (v114 = *(_DWORD *)(qword_102ECFB00 + 48508), v306 = v114, (v114 & 0x20) != 0)
    && (v307 = v114, (v114 & 0x2000) == 0)
    || (v236 = 0,
        v115 = *(char **)(SystemThread_TlsOffset
                        + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v113)
                        + 136LL),
        IsHekatonEnabled(),
        v115)
    && (v236 = *v115) != 0 )
  {
    v28 = v233;
    v230 = v233;
    v23 = v235;
    v24 = v234;
    v26 = v226;
    v29 = v232;
    goto LABEL_58;
  }
  if ( *(_DWORD *)(qword_102ECFB00 + 14580) )
  {
    v262 = *((_BYTE *)qword_102ECFB10 + 1268) >> 3;
    if ( (v262 & 1) != 0 )
      goto LABEL_251;
    LODWORD(v230) = 0;
    v116 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    if ( *(_QWORD *)v116 && (v117 = *(struct XDES ***)(*(_QWORD *)v116 + 56LL), (v118 = *v117) != 0) )
    {
      v247 = *v117;
      if ( CSessionTraceFlags::CheckSessionTraceInternal(v118, 0x27A3u) )
      {
LABEL_251:
        if ( qword_103095748 )
        {
          v23 = v235;
          v28 = v233;
          v230 = v233;
          v24 = v234;
          v26 = v226;
          if ( (unsigned __int8)qword_103095748(v233, v235) )
            goto LABEL_57;
          goto LABEL_256;
        }
      }
    }
    else
    {
      v247 = 0;
    }
  }
  v28 = v233;
  v230 = v233;
  v23 = v235;
  v24 = v234;
  v26 = v226;
LABEL_256:
  LODWORD(v222) = 13029;
  v29 = v232;
  LODWORD(v220) = v227;
  LODWORD(v218) = 13029;
  LODWORD(v208) = 13087;
  ex_raise(37, 8, 16, 1, v208, v218, v220, v232, v222);
LABEL_58:
  if ( !(*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v23 + 136LL))(v23) )
    goto LABEL_59;
  v119 = (*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v23 + 136LL))(v23);
  v120 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v119 + 32LL))(v119);
  v121 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v120 + 48LL))(v120);
  if ( !v121 )
  {
    *(_DWORD *)v221 = 13039;
LABEL_260:
    LODWORD(v218) = v227;
    LODWORD(v208) = 13035;
    ex_raise(37, 16, 16, 1, v208, v218, v29, *(_QWORD *)v221);
    goto LABEL_59;
  }
  if ( v121 == 1 )
  {
    *(_DWORD *)v221 = 13040;
    goto LABEL_260;
  }
LABEL_59:
  if ( !(*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v23 + 144LL))(v23) )
    goto LABEL_60;
  if ( (*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v23 + 88LL))(v23) )
    ex_raise(37, 17, 16, 1);
  v122 = (*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v23 + 144LL))(v23);
  v123 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v122 + 24LL))(v122);
  v124 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
  if ( !v124 )
  {
    *(_DWORD *)v221 = 13039;
LABEL_267:
    LODWORD(v218) = v227;
    LODWORD(v208) = 13034;
    ex_raise(37, 16, 16, 3, v208, v218, v29, *(_QWORD *)v221);
    goto LABEL_60;
  }
  if ( v124 == 1 )
  {
    *(_DWORD *)v221 = 13040;
    goto LABEL_267;
  }
LABEL_60:
  if ( (v392 & 0x20) != 0 || v24 && (BYTE2(v394) & 0x40) != 0 || v281 && (v241 & 0x20) != 0 )
  {
    v126 = getobjtype(v26);
    v127 = 24;
    goto LABEL_279;
  }
  if ( (v392 & 0x10) != 0 )
  {
    v382 = L"(@objid int, @retcode int OUTPUT)exec @retcode = sp_MScheck_dropobject @objid = @objid";
    ExecSql = CreateExecSql(v244, 0);
    v383 = ExecSql;
    `eh vector constructor iterator'(
      v315,
      0x48u,
      2u,
      (void (*)(void *))CAutoClearXVariant::CAutoClearXVariant,
      CAutoClearXVariant::~CAutoClearXVariant);
    v384 = &v316;
    v317[2] = 0;
    strcpy(v317, "8");
    v385 = v318;
    v318[1] = 0;
    v319 = 0;
    v316 = 0;
    v320 = CTypeInfo::tiI4;
    v321 = xmmword_102EF7C30;
    v318[0] = (unsigned int)v231;
    v386 = &v322;
    v323[2] = 0;
    strcpy(v323, "8");
    v387 = v324;
    v324[1] = 0;
    v325 = 0;
    v322 = 0;
    v326 = CTypeInfo::tiI4;
    v327 = xmmword_102EF7C30;
    v324[0] = 0xFFFFFFFFLL;
    (*(void (__fastcall **)(struct IExecSql *, __int64))(*(_QWORD *)ExecSql + 192LL))(ExecSql, 2);
    *(_DWORD *)v221 = 1;
    LOWORD(v213) = 0;
    (*(void (__fastcall **)(struct IExecSql *, _QWORD, char *, _QWORD, int, _DWORD, void *, bool *))(*(_QWORD *)ExecSql + 208LL))(
      ExecSql,
      0,
      &v316,
      0,
      v213,
      0,
      &CTypeInfo::tiI4,
      *(bool **)v221);
    *(_DWORD *)v221 = 2;
    v220 = &CTypeInfo::tiI4;
    (*(void (__fastcall **)(struct IExecSql *, __int64, char *))(*(_QWORD *)ExecSql + 208LL))(ExecSql, 1, &v322);
    if ( !(*(unsigned int (__fastcall **)(struct IExecSql *, const wchar_t *, __int64))(*(_QWORD *)ExecSql + 8LL))(
            ExecSql,
            L"(@objid int, @retcode int OUTPUT)exec @retcode = sp_MScheck_dropobject @objid = @objid",
            33)
      || v322 == 3
      || LOWORD(v324[0]) )
    {
      LODWORD(v220) = v227;
      LODWORD(v218) = getobjtype(v26);
      LODWORD(v208) = 13087;
      ex_raise(37, 24, 16, 3, v208, v218, v220, v232);
    }
    `eh vector destructor iterator'(v315, 0x48u, 2u, CAutoClearXVariant::~CAutoClearXVariant);
    v355 = ExecSql;
    (*(void (__fastcall **)(struct IExecSql *, __int64))(*(_QWORD *)ExecSql + 224LL))(ExecSql, 1);
    goto LABEL_72;
  }
  v30 = qword_102EF3550;
  if ( !*((_BYTE *)qword_102EF3550 + 1486) )
  {
    v252 = *((_BYTE *)qword_102ECFB10 + 1725);
    if ( (v252 & 1) == 0 )
      goto LABEL_71;
  }
  v249 = *((_BYTE *)qword_102ECFB10 + 1725) >> 2;
  if ( (v249 & 1) != 0 )
    goto LABEL_71;
  v31 = (unsigned __int8 (__fastcall ***)(_QWORD, _QWORD, _BYTE *, _QWORD))(*(__int64 (__fastcall **)(struct IMetadataAccess *))(*(_QWORD *)v28 + 72LL))(v28);
  if ( !(**v31)(v31, v229, v402, 0) || v404 >= 0 )
  {
    v30 = qword_102EF3550;
LABEL_71:
    if ( !*((_BYTE *)v30 + 72) )
    {
      v129 = (unsigned __int8 (__fastcall ***)(_QWORD, _QWORD, _BYTE *, _QWORD))(*(__int64 (__fastcall **)(struct IMetadataAccess *))(*(_QWORD *)v28 + 72LL))(v28);
      if ( (**v129)(v129, v229, v402, 0) )
      {
        if ( (v404 & 0x40) != 0 )
        {
          if ( !*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                   + SystemThread_TlsIndex)
                                                 + SystemThread_TlsOffset)
                                     + 72LL)
                         + 4976LL) )
          {
            v363 = L"(@objid int, @retcode bit OUTPUT) set nocount on set @retcode = 0 SELECT object_id INTO #cdc_objects "
                    "FROM ( select object_id from sys.objects where schema_id = schema_id(N'cdc') and (type = 'IF' or typ"
                    "e = 'P') union select object_id from sys.tables where schema_id = schema_id(N'cdc') and name like '%"
                    "_CT' ) a select @retcode = 1 from #cdc_objects WHERE object_id = @objid if (@retcode = 1 or (@objid "
                    "in (object_id('[dbo].[systranschemas]'),\t\t\t\t\tobject_id('[cdc].[change_tables]'),\t\t\t\t\tobjec"
                    "t_id('[cdc].[captured_columns]'),\t\t\t\t\tobject_id('[cdc].[ddl_history]'),\t\t\t\t\tobject_id('[cd"
                    "c].[lsn_time_mapping]'))))\t\tset @retcode = 1 else\t\tset @retcode = 0 drop table #cdc_objects";
            v128 = CreateExecSql(v244, 0);
            v364 = v128;
            `eh vector constructor iterator'(
              v341,
              0x48u,
              2u,
              (void (*)(void *))CAutoClearXVariant::CAutoClearXVariant,
              CAutoClearXVariant::~CAutoClearXVariant);
            v365 = &v342;
            v343[2] = 0;
            strcpy(v343, "8");
            v366 = v344;
            v344[1] = 0;
            v345 = 0;
            v342 = 0;
            v346 = CTypeInfo::tiI4;
            v347 = xmmword_102EF7C30;
            v344[0] = (unsigned int)v231;
            v367 = &v348;
            v349[2] = 0;
            strcpy(v349, "h");
            v368 = v350;
            v350[1] = 0;
            v351 = 0;
            v348 = 0;
            v352 = CTypeInfo::tiBit;
            v353 = xmmword_10305AE30;
            v350[0] = 0;
            (*(void (__fastcall **)(struct IExecSql *, __int64))(*(_QWORD *)v128 + 192LL))(v128, 2);
            *(_DWORD *)v221 = 1;
            LOWORD(v215) = 0;
            (*(void (__fastcall **)(struct IExecSql *, _QWORD, char *, _QWORD, int, _DWORD, void *, bool *))(*(_QWORD *)v128 + 208LL))(
              v128,
              0,
              &v342,
              0,
              v215,
              0,
              &CTypeInfo::tiI4,
              *(bool **)v221);
            *(_DWORD *)v221 = 2;
            v220 = &CTypeInfo::tiBit;
            (*(void (__fastcall **)(struct IExecSql *, __int64, char *))(*(_QWORD *)v128 + 208LL))(v128, 1, &v348);
            if ( !(*(unsigned int (**)(struct IExecSql *, const wchar_t *, ...))(*(_QWORD *)v128 + 8LL))(
                    v128,
                    L"(@objid int, @retcode bit OUTPUT) set nocount on set @retcode = 0 SELECT object_id INTO #cdc_objects"
                     " FROM ( select object_id from sys.objects where schema_id = schema_id(N'cdc') and (type = 'IF' or t"
                     "ype = 'P') union select object_id from sys.tables where schema_id = schema_id(N'cdc') and name like"
                     " '%_CT' ) a select @retcode = 1 from #cdc_objects WHERE object_id = @objid if (@retcode = 1 or (@ob"
                     "jid in (object_id('[dbo].[systranschemas]'),\t\t\t\t\tobject_id('[cdc].[change_tables]'),\t\t\t\t\t"
                     "object_id('[cdc].[captured_columns]'),\t\t\t\t\tobject_id('[cdc].[ddl_history]'),\t\t\t\t\tobject_i"
                     "d('[cdc].[lsn_time_mapping]'))))\t\tset @retcode = 1 else\t\tset @retcode = 0 drop table #cdc_objects",
                    33)
              || LOBYTE(v350[0]) )
            {
              v26 = v226;
              LODWORD(v220) = v227;
              LODWORD(v218) = getobjtype(v226);
              LODWORD(v208) = 13087;
              ex_raise(37, 64, 16, 1, v208, v218, v220, v232);
            }
            else
            {
              v26 = v226;
            }
            `eh vector destructor iterator'(v341, 0x48u, 2u, CAutoClearXVariant::~CAutoClearXVariant);
            v369 = v128;
LABEL_287:
            (*(void (__fastcall **)(struct IExecSql *, __int64))(*(_QWORD *)v128 + 224LL))(v128, 1);
            v32 = v233;
            v230 = v233;
            v23 = v235;
            v24 = v234;
            goto LABEL_73;
          }
          goto LABEL_297;
        }
      }
    }
    goto LABEL_72;
  }
  if ( (BYTE2(v394) & 0x10) != 0 )
  {
    v126 = getobjtype(v26);
    v127 = 63;
LABEL_279:
    LODWORD(v220) = v227;
    LODWORD(v218) = v126;
    LODWORD(v208) = 13087;
    ex_raise(37, v127, 16, 2, v208, v218, v220, v29);
    goto LABEL_72;
  }
  if ( !*((_BYTE *)qword_102EF3550 + 73) )
  {
    v250 = *((_BYTE *)qword_102ECFB10 + 1726);
    if ( (v250 & 1) == 0 )
    {
      if ( !*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                               + SystemThread_TlsIndex)
                                             + SystemThread_TlsOffset)
                                 + 72LL)
                     + 4976LL) )
      {
        v356 = L"(@objid int, @retcode bit OUTPUT) if (@objid in (object_id('[dbo].[systranschemas]'),\t\t\t\t\tobject_id("
                "'[changefeed].[change_feed_tables]'),\t\t\t\t\tobject_id('[changefeed].[change_feed_table_groups]'),\t\t"
                "\t\t\tobject_id('[changefeed].[change_feed_settings]')))\t\tset @retcode = 1 else\t\tset @retcode = 0";
        v128 = CreateExecSql(v244, 0);
        v357 = v128;
        `eh vector constructor iterator'(
          v328,
          0x48u,
          2u,
          (void (*)(void *))CAutoClearXVariant::CAutoClearXVariant,
          CAutoClearXVariant::~CAutoClearXVariant);
        v358 = &v329;
        v330[2] = 0;
        strcpy(v330, "8");
        v359 = v331;
        v331[1] = 0;
        v332 = 0;
        v329 = 0;
        v333 = CTypeInfo::tiI4;
        v334 = xmmword_102EF7C30;
        v331[0] = (unsigned int)v231;
        v360 = &v335;
        v336[2] = 0;
        strcpy(v336, "h");
        v361 = v337;
        v337[1] = 0;
        v338 = 0;
        v335 = 0;
        v339 = CTypeInfo::tiBit;
        v340 = xmmword_10305AE30;
        v337[0] = 0;
        (*(void (__fastcall **)(struct IExecSql *, __int64))(*(_QWORD *)v128 + 192LL))(v128, 2);
        *(_DWORD *)v221 = 1;
        LOWORD(v214) = 0;
        (*(void (__fastcall **)(struct IExecSql *, _QWORD, char *, _QWORD, int, _DWORD, void *, bool *))(*(_QWORD *)v128 + 208LL))(
          v128,
          0,
          &v329,
          0,
          v214,
          0,
          &CTypeInfo::tiI4,
          *(bool **)v221);
        *(_DWORD *)v221 = 2;
        v220 = &CTypeInfo::tiBit;
        (*(void (__fastcall **)(struct IExecSql *, __int64, char *))(*(_QWORD *)v128 + 208LL))(v128, 1, &v335);
        if ( !(*(unsigned int (__fastcall **)(struct IExecSql *, const wchar_t *, __int64))(*(_QWORD *)v128 + 8LL))(
                v128,
                L"(@objid int, @retcode bit OUTPUT) if (@objid in (object_id('[dbo].[systranschemas]'),\t\t\t\t\tobject_id"
                 "('[changefeed].[change_feed_tables]'),\t\t\t\t\tobject_id('[changefeed].[change_feed_table_groups]'),\t"
                 "\t\t\t\tobject_id('[changefeed].[change_feed_settings]')))\t\tset @retcode = 1 else\t\tset @retcode = 0",
                33)
          || LOBYTE(v337[0]) )
        {
          v26 = v226;
          LODWORD(v220) = v227;
          LODWORD(v218) = getobjtype(v226);
          LODWORD(v208) = 13087;
          ex_raise(37, 63, 16, 3, v208, v218, v220, v232);
        }
        else
        {
          v26 = v226;
        }
        `eh vector destructor iterator'(v328, 0x48u, 2u, CAutoClearXVariant::~CAutoClearXVariant);
        v362 = v128;
        goto LABEL_287;
      }
LABEL_297:
      v32 = v233;
      v230 = v233;
      v23 = v235;
      v24 = v234;
      v26 = v226;
      goto LABEL_73;
    }
  }
LABEL_72:
  v32 = v230;
LABEL_73:
  if ( v26 == 8277 || v26 == 21573 || v26 == 8275 || v26 == 21577 )
  {
    v130 = (*(__int64 (__fastcall **)(struct IMEDRelation *))(*(_QWORD *)v24 + 432LL))(v24);
    v274 = v130;
    while ( v130 )
    {
      v131 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(struct IMEDRelation *, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v24 + 440LL))(
                                                 v24,
                                                 v130,
                                                 0,
                                                 0,
                                                 0);
      v132 = (**v131)(v131);
      v133 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v132 + 88LL))(v132);
      if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v133 + 8LL))(v133) != v231 )
      {
        LODWORD(v208) = v227;
        ex_raise(37, 26, 16, 1, v208, v232);
      }
      v274 = --v130;
    }
    if ( (*(unsigned int (__fastcall **)(struct IMEDRelation *))(*(_QWORD *)v24 + 456LL))(v24) )
    {
      LODWORD(v208) = v227;
      ex_raise(139, 34, 16, 1, v208, v232);
    }
  }
  v33 = 0;
  v253 = 0;
  v242 = 258;
  v34 = (*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v23 + 272LL))(v23);
  v35 = (struct IMemObj *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v34 + 8LL))(v34);
  v36 = 2 * ((unsigned __int64)v242 >> 1);
  if ( !is_mul_ok((unsigned __int64)v242 >> 1, 2u) )
    v36 = -1;
  v282 = operator new[](v36, v35, "Sql\\Ntdbms\\msql\\ddl\\drop.cpp", 2697, 3u);
  while ( 1 )
  {
    LOBYTE(v209) = 0;
    v37 = (*(__int64 (__fastcall **)(struct IMEDObject *, void *, unsigned int *, _QWORD, struct CStatement *))(*(_QWORD *)v23 + 256LL))(
            v23,
            v282,
            &v242,
            v33,
            v209);
    v33 = v37;
    v253 = v37;
    if ( !v37 )
      break;
    if ( (v37 & 0xE0000000) == 0xA0000000 )
      goto LABEL_311;
    v134 = (*(__int64 (__fastcall **)(struct IMetadataAccess *, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(*(_QWORD *)v32 + 56LL))(
             v32,
             v229,
             0,
             0,
             0,
             0);
    *(_DWORD *)v221 = 0;
    LODWORD(v220) = 0;
    LOBYTE(v219) = 1;
    LOBYTE(v216) = 0;
    LOBYTE(v135) = 1;
    v136 = (struct IMEDObject *)(*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, int, int, void *, bool *))(*(_QWORD *)v134 + 120LL))(
                                  v134,
                                  v33,
                                  v135,
                                  0,
                                  v216,
                                  v219,
                                  v220,
                                  *(bool **)v221);
    (*(void (__fastcall **)(struct IMEDObject *, _BYTE *))(*(_QWORD *)v136 + 96LL))(v136, v401);
    if ( (v401[13] & 8) != 0
      || (*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v136 + 120LL))(v136)
      && (v137 = (*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v136 + 120LL))(v136),
          ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v137 + 1160LL))(v137) & 2) != 0) )
    {
      v237 = 1;
      MatchingPartitionIndexViewHelper::DropMPIdxView(v239, v136);
      v242 = 258;
      v33 = v253;
    }
    else
    {
      v237 = 0;
      v33 = v253;
LABEL_311:
      v138 = ObjtypeToCmdtoken(v26);
      v139 = TokenLongName(v138);
      *(_DWORD *)v221 = v242;
      LODWORD(v218) = v227;
      ex_raise(37, 29, 16, 1, v139, v218, v232, *(_QWORD *)v221, v282);
      v242 = 258;
    }
  }
  if ( v281 )
  {
    v41 = (struct XDES *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v281 + 104LL))(v281);
    v247 = v41;
    if ( v41 )
    {
      if ( (*(unsigned int (__fastcall **)(struct XDES *))(*(_QWORD *)v41 + 24LL))(v41) )
      {
        v140 = *(_QWORD *)v239;
        v141 = (*(__int64 (__fastcall **)(struct XDES *, __int64))(*(_QWORD *)v247 + 32LL))(v247, 1);
        v142 = (*(__int64 (__fastcall **)(struct IMEDDatabase *, _QWORD, _QWORD))(v140 + 992))(v239, v141, 0);
        v143 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v142 + 16LL))(v142);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v142 + 16LL))(v142);
        v144 = getobjtype(v26);
        LODWORD(v222) = *(_DWORD *)(v145 + 8);
        LODWORD(v220) = v227;
        LODWORD(v218) = v144;
        LODWORD(v210) = 13087;
        ex_raise(105, 13, 16, 1, v210, v218, v220, v232, v222, *v143);
      }
    }
  }
  if ( v24 )
  {
    v42 = (*(__int64 (__fastcall **)(struct IMEDRelation *))(*(_QWORD *)v24 + 560LL))(v24);
    v243 = v42;
    while ( v42 )
    {
      v146 = (struct IMEDTrigger *)(*(__int64 (__fastcall **)(struct IMEDRelation *, _QWORD))(*(_QWORD *)v24 + 584LL))(
                                     v24,
                                     v42);
      CheckCanDropTrigger(v239, v146);
      v243 = --v42;
    }
    v43 = (*(__int64 (__fastcall **)(struct IMEDRelation *))(*(_QWORD *)v24 + 552LL))(v24);
    v243 = v43;
    while ( v43 )
    {
      v147 = (struct IMEDTrigger *)(*(__int64 (__fastcall **)(struct IMEDRelation *, _QWORD))(*(_QWORD *)v24 + 576LL))(
                                     v24,
                                     v43);
      CheckCanDropTrigger(v239, v147);
      v243 = --v43;
    }
    v44 = (*(__int64 (__fastcall **)(struct IMEDRelation *))(*(_QWORD *)v24 + 544LL))(v24);
    v243 = v44;
    while ( v44 )
    {
      v148 = (struct IMEDTrigger *)(*(__int64 (__fastcall **)(struct IMEDRelation *, _QWORD))(*(_QWORD *)v24 + 568LL))(
                                     v24,
                                     v44);
      CheckCanDropTrigger(v239, v148);
      v243 = --v44;
    }
    v45 = (struct IMEDTrigger *)(*(__int64 (__fastcall **)(struct IMEDRelation *))(*(_QWORD *)v24 + 608LL))(v24);
    CheckCanDropTrigger(v239, v45);
    v46 = (struct IMEDTrigger *)(*(__int64 (__fastcall **)(struct IMEDRelation *))(*(_QWORD *)v24 + 600LL))(v24);
    CheckCanDropTrigger(v239, v46);
    v47 = (struct IMEDTrigger *)(*(__int64 (__fastcall **)(struct IMEDRelation *))(*(_QWORD *)v24 + 592LL))(v24);
    CheckCanDropTrigger(v239, v47);
  }
  if ( v26 == 8278 && (*(__int64 (__fastcall **)(struct IMEDRelation *, __int64))(*(_QWORD *)v24 + 232LL))(v24, 1) )
  {
    v228 = 1;
  }
  else
  {
    v228 = 0;
    if ( v26 != 8277 && v26 != 21573 )
      goto LABEL_95;
  }
  if ( v229 != 2 )
  {
    v149 = g_dbtableFactory[4]((unsigned __int16)v229);
    v247 = (struct XDES *)(*(__int64 (__fastcall **)(struct BaseXact *, _QWORD))(*(_QWORD *)v266 + 280LL))(
                            v266,
                            *(_QWORD *)(v149 + 4624));
    for ( i = 0; ; CTableIndexUtil::CheckIndexFilegroupsForDropRowset(v239, i, v247, v232, v227, v151) )
    {
      i = (struct IMEDIndex *)(*(__int64 (__fastcall **)(struct IMEDRelation *, struct IMEDIndex *, _QWORD))(*(_QWORD *)v24 + 360LL))(
                                v24,
                                i,
                                0);
      if ( !i )
        break;
      v151 = 13029;
      if ( v228 )
        v151 = 13033;
    }
  }
LABEL_95:
  v48 = v230;
  if ( v26 == 8277 )
  {
    CIndexDDL::CIndexDDL((CIndexDDL *)v389, v230, v24, v244, v227, v232, 0, 0, 0);
    v152 = (struct BaseXact *)(*(__int64 (__fastcall **)(struct CMsqlXact *))(*(_QWORD *)v271 + 432LL))(v271);
    CIndexDDL::InvalidateTxtPtrs((CIndexDDL *)v389, v152);
    CIndexDDL::~CIndexDDL((CIndexDDL *)v389);
  }
  if ( v228 )
  {
    v370 = v270;
    v371 = v270;
    v372 = v270;
    v270[1] = v270;
    v270[0] = v270;
    v221[0] = 0;
    LOBYTE(v210) = 0;
    LOBYTE(v40) = 1;
    CBaseTableCollection::Populate(v270, v230, v23, v40, (_DWORD)v210, 0, 0, *(_DWORD *)v221);
    CBaseTableCollection::UpdateSchemas((CBaseTableCollection *)v270);
    CBaseTableCollection::~CBaseTableCollection((CBaseTableCollection *)v270);
  }
  if ( (v26 == 8277 || v26 == 21573) && (BYTE8(v394) & 1) != 0 )
  {
    v153 = g_dbtableFactory[4](v229);
    v154 = (struct XDES *)(*(__int64 (__fastcall **)(struct BaseXact *, _QWORD))(*(_QWORD *)v266 + 280LL))(
                            v266,
                            *(_QWORD *)(v153 + 4624));
    FFtDropTable(v154, v23);
  }
  if ( v24 )
  {
    v49 = (struct XDES *)(*(__int64 (__fastcall **)(struct IMEDRelation *))(*(_QWORD *)v24 + 408LL))(v24);
    v39 = v49;
    v247 = v49;
    if ( v49 )
    {
      v285[0] = 0;
      v285[1] = 0;
      v286 &= 0xE0u;
      v287 = 0;
      v288 = 0;
      v289 = 1;
      v290 = 0;
      (*(void (__fastcall **)(struct XDES *, int *))(*(_QWORD *)v49 + 32LL))(v49, v285);
      v155 = v285[0];
      HIDWORD(v218) = HIDWORD(v232);
      FTStartStopPopulation(v230, v247, 2);
      DeleteAllFragments(v239, v24);
      DeleteMapping(v266, v155, v229, v231, 1);
    }
  }
  if ( v26 - 8277 <= 1
    && (*(unsigned int (__fastcall **)(struct IMEDRelation *, __int64, struct XDES *))(*(_QWORD *)v24 + 520LL))(
         v24,
         v38,
         v39) )
  {
    _mm_lfence();
    v24 = v234;
    LOBYTE(v39) = 1;
    v156 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(struct IMEDRelation *, __int64, struct XDES *))(*(_QWORD *)v234 + 528LL))(
                                               v234,
                                               1,
                                               v39);
    v157 = (**v156)(v156);
    v158 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v157 + 40LL))(v157);
    v26 = v226;
    v159 = ObjtypeToCmdtoken(v226);
    v160 = TokenLongName(v159);
    *(_DWORD *)v221 = *(_DWORD *)(v158 + 8);
    LODWORD(v218) = v227;
    ex_raise(37, 29, 16, 3, v160, v218, v232, *(_QWORD *)v221, *(_QWORD *)v158);
    v48 = v233;
    v23 = v235;
  }
  if ( v26 != 21076 && v26 != 16724 )
  {
    if ( v26 == 20051 )
    {
      v161 = (*(__int64 (__fastcall **)(struct IMEDObject *, __int64, struct XDES *))(*(_QWORD *)v23 + 208LL))(
               v23,
               v38,
               v39);
      v228 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v161 + 8LL))(v161, 0, 0);
      v162 = 2 * ((unsigned __int64)(unsigned int)v228 >> 1);
      if ( !is_mul_ok((unsigned __int64)(unsigned int)v228 >> 1, 2u) )
        v162 = -1;
      v163 = operator new[](v162, v244, "Sql\\Ntdbms\\msql\\ddl\\drop.cpp", 2886, 3u);
      if ( v269 != v163 )
      {
        v373 = v269;
        operator delete[](v269);
      }
      v269 = v163;
      v164 = (*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v23 + 208LL))(v23);
      (*(void (__fastcall **)(__int64, void *, _QWORD))(*(_QWORD *)v164 + 8LL))(v164, v163, (unsigned int)v228);
      v246 = CbParseQuotesW((const wchar_t *)v163, v228, (wchar_t *)v163, v228);
      v272 = (__int64)v163;
    }
    goto LABEL_110;
  }
  v165 = v293;
  if ( !v293 )
  {
    v173 = (*(__int64 (__fastcall **)(struct IMEDObject *, __int64, struct XDES *))(*(_QWORD *)v23 + 88LL))(
             v23,
             v38,
             v39);
    v174 = v173;
    if ( !v173 || !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v173 + 40LL))(v173) )
      goto LABEL_110;
    v272 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v174 + 40LL))(v174);
    v246 = *(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v174 + 40LL))(v174) + 8);
    (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v174 + 96LL))(v174, v399);
    v168 = v400;
LABEL_335:
    v256 = v168;
    goto LABEL_110;
  }
  v272 = (*(__int64 (__fastcall **)(__int64, __int64, struct XDES *))(*(_QWORD *)v293 + 40LL))(v293, v38, v39);
  v246 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v165 + 48LL))(v165);
  v166 = v291;
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD *))(*v291 + 24LL))(v291) )
  {
    v167 = (*(__int64 (__fastcall **)(_QWORD *))(*v166 + 40LL))(v166);
    (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v167 + 96LL))(v167, v397);
    v168 = v398;
    goto LABEL_335;
  }
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD *))(*v291 + 8LL))(v291) )
  {
    v169 = (*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v23 + 176LL))(v23);
    if ( (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v169 + 32LL))(v169, 147) )
    {
      _mm_lfence();
      MasterDbId = GetMasterDbId();
      v171 = g_dbtableFactory[4](MasterDbId);
      v172 = (struct XDES *)(*(__int64 (__fastcall **)(struct BaseXact *, _QWORD))(*(_QWORD *)v266 + 280LL))(
                              v266,
                              *(_QWORD *)(v171 + 4624));
      CLogonTriggerCache::Flush(v172);
      v48 = v233;
      v23 = v235;
      v24 = v234;
      v26 = v226;
    }
  }
LABEL_110:
  v255 = (*(__int64 (__fastcall **)(struct IMEDObject *, __int64, struct XDES *))(*(_QWORD *)v23 + 24LL))(v23, v38, v39);
  if ( v26 == 20038 )
  {
    v175 = GetMasterDbId();
    v176 = (DBTABLE *)g_dbtableFactory[4](v229);
    if ( DBTABLE::IsWorkloadIsolationEnabled(v176) )
      v175 = v229;
    LastError = v175;
    v258 = (CSourceCollection *)g_dbtableFactory[4](v175);
    v254 = *((_DWORD *)v258 + 1169);
    v23 = v235;
    v177 = (*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v235 + 8LL))(v235);
    if ( v177 == v254 )
    {
      v178 = (**(__int64 (__fastcall ***)(struct IMEDObject *))v235)(v235);
      if ( v178 == GetMasterDbId() || DBTABLE::IsWorkloadIsolationEnabled(v258) )
      {
        v179 = (_QWORD *)(*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v235 + 40LL))(v235);
        LODWORD(v218) = *(_DWORD *)((*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v235 + 40LL))(v235) + 8);
        LODWORD(v210) = 13087;
        ex_raise(109, 20, 16, 1, v210, v218, *v179);
      }
    }
    v48 = v233;
    v180 = (void (__fastcall ***)(_QWORD, _BYTE *, int *, int *))(*(__int64 (__fastcall **)(struct IMetadataAccess *, _QWORD, _QWORD))(*(_QWORD *)v233 + 528LL))(
                                                                   v233,
                                                                   LastError,
                                                                   0);
    v273 = 0;
    (**v180)(v180, v251, &v254, &v273);
    if ( v231 == v254 )
    {
      if ( v229 != GetMasterDbId() && !DBTABLE::IsWorkloadIsolationEnabled(v258) )
      {
        v24 = v234;
        v26 = v226;
        goto LABEL_352;
      }
      v183 = (_QWORD *)(*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v235 + 40LL))(v235);
      LODWORD(v218) = *(_DWORD *)((*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v235 + 40LL))(v235) + 8);
      LODWORD(v210) = 13087;
      ex_raise(109, 20, 16, 3, v210, v218, *v183);
    }
    v24 = v234;
    v26 = v226;
    goto LABEL_352;
  }
  if ( v26 == 21318 )
  {
LABEL_352:
    v181 = (QPEvent *)(*(__int64 (__fastcall **)(struct IMetadataAccess *))(*(_QWORD *)v48 + 16LL))(v48);
    QPEvent::DropObject(v181, v23, v182);
  }
  v228 = 0;
  LODWORD(v271) = 0;
  v267 = 0;
  v50 = v26 == 8277 && (*(unsigned __int8 (__fastcall **)(struct IMEDRelation *))(*(_QWORD *)v24 + 1048LL))(v24);
  v225[0] = v50;
  v251[1] = v50;
  if ( (BYTE9(v394) & 8) != 0 && (BYTE9(v394) & 0x10) == 0 )
  {
    v184 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IMEDRelation *))(*(_QWORD *)v24 + 1088LL))(v24);
    if ( !DBDeleteFileW(v184, 0) )
    {
      LastError = GetLastError();
      if ( LastError != 2 )
      {
        v185 = (*(__int64 (__fastcall **)(struct IMEDRelation *))(*(_QWORD *)v24 + 1088LL))(v24);
        LODWORD(v218) = LastError;
        ex_raise(37, 61, 16, 1, v185, v218);
      }
    }
  }
  v238 = 0;
  if ( !v240 )
  {
    if ( !v50 )
      goto LABEL_117;
LABEL_375:
    v197 = (*(__int64 (__fastcall **)(struct IMEDRelation *, _QWORD, _QWORD))(*(_QWORD *)v24 + 360LL))(v24, 0, 0);
    v198 = v197;
    if ( v197 )
    {
      v228 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v197 + 136LL))(v197);
      v267 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v198 + 224LL))(v198);
    }
    goto LABEL_117;
  }
  if ( v50 )
    goto LABEL_375;
  if ( v26 == 8277 || v26 == 21573 )
  {
    v186 = (__int64 *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                     + SystemThread_TlsOffset);
    v187 = *v186;
    v188 = *(_QWORD *)(*v186 + 128);
    v374 = v188;
    if ( v188 )
      v189 = (CTmpObjectList *)(v188 + 168);
    else
      v189 = *(CTmpObjectList **)(*(_QWORD *)(v187 + 72) + 424LL);
    v375 = v189;
    v190 = CTmpObjectList::LookupByIdNoLock(v189, v231);
    if ( !v190 || !*((_QWORD *)v190 + 52) || (*((_DWORD *)v190 + 13) & 2) != 0 )
    {
      v48 = v233;
      v23 = v235;
      v228 = (int)v271;
      v26 = v226;
      goto LABEL_117;
    }
    v238 = 1;
LABEL_370:
    v191 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v192 = *(_QWORD *)(*(_QWORD *)v191 + 128LL);
    if ( v192 )
      v193 = (__int64 *)(v192 + 168);
    else
      v193 = *(__int64 **)(*(_QWORD *)(*(_QWORD *)v191 + 72LL) + 424LL);
    v194 = g_dbtableFactory[4](v229);
    v195 = *v193;
    v196 = (*(__int64 (__fastcall **)(struct BaseXact *, _QWORD))(*(_QWORD *)v266 + 280LL))(
             v266,
             *(_QWORD *)(v194 + 4624));
    (*(void (__fastcall **)(__int64 *, __int64, _QWORD))(v195 + 8))(v193, v196, (unsigned int)v231);
    v26 = v226;
    v52 = v240;
  }
  else
  {
LABEL_117:
    v51 = 0;
    v301 = 0;
    v258 = 0;
    if ( v225[0] )
    {
      v275 = 2988;
      v299 = (CDistributedExecutionContext *)operator new(0x38u, v244, "Sql\\Ntdbms\\msql\\ddl\\drop.cpp", 2988, 3u);
      if ( v299 )
      {
        LOBYTE(v199) = 1;
        v200 = (struct IMEDSchema *)(*(__int64 (__fastcall **)(struct IMEDDatabase *, _QWORD, _QWORD, __int64))(*(_QWORD *)v239 + 216LL))(
                                      v239,
                                      v255,
                                      0,
                                      v199);
        v51 = CDistributedExecutionContext::CDistributedExecutionContext(v299, v239, v200, v23, v298, v244);
      }
      else
      {
        v51 = 0;
      }
      v258 = v51;
      v376 = v51;
      v201 = v300;
      if ( v51 )
        v201 = 0;
      v300 = v201;
      v301 = v51;
    }
    DropObject(v48, v23, 0, a6, v51);
    v284 = v51;
    if ( v258 )
      (**(void (__fastcall ***)(CSourceCollection *, __int64))v51)(v51, 1);
    if ( v228 && v225[0] )
    {
      _mm_lfence();
      DropRangePartition(v245, v239, v233, v244, v267);
      v26 = v226;
    }
    v52 = v240;
    if ( v240 )
      goto LABEL_370;
  }
  ProduceDropObjectTrace(v26, v229, (unsigned int)v231, v232, v227);
  if ( a6 )
  {
    (*(void (__fastcall **)(CXStmtDDL *))(*(_QWORD *)a6 + 112LL))(a6);
  }
  else
  {
    v202 = v248;
    v248 = 0;
    if ( v202 )
      (**(void (__fastcall ***)(struct IMetadataAccess *, __int64))v202)(v202, 1);
    CAutoMsqlXact::CommitNestedXact((CAutoMsqlXact *)&v263, 0);
  }
  operator delete[](v282);
  if ( v248 )
    (**(void (__fastcall ***)(struct IMetadataAccess *, __int64))v248)(v248, 1);
  ExcHandler::~ExcHandler((ExcHandler *)v354);
  v54 = v244;
  v55 = v302;
  v56 = v303;
  v57 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v58 = *(struct Worker **)(v57 + 256);
  if ( !v58 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v58 = *(struct Worker **)(v57 + 256);
  }
  if ( *((_DWORD *)v58 + 139) )
    ExceptionPostCatchActions(v58);
  if ( v55
    && !v52
    && ((v59 = v226, v226 == 20051)
     || (unsigned int)(v226 - 8260) <= 0x12 && (v60 = 413697, _bittest(&v60, v226 - 8260))
     || (unsigned int)(v226 - 17993) <= 0xB && (v203 = 2561, _bittest(&v203, v226 - 17993))
     || v226 == 21076
     || v226 == 20038
     || (unsigned int)(v226 - 21573) <= 1
     || v226 == 21318
     || v226 == 17232
     || v226 == 16724
     || v226 == 21321
     || v226 == 20307
     || v226 == 20563) )
  {
    v61 = v239;
    LOBYTE(v53) = 1;
    v62 = (*(__int64 (__fastcall **)(struct IMEDDatabase *, _QWORD, _QWORD, __int64))(*(_QWORD *)v239 + 216LL))(
            v239,
            v255,
            0,
            v53);
    if ( !*((_BYTE *)a6 + 240) )
      goto LABEL_137;
    v225[0] = 1;
    v63 = 2 * HIDWORD(v314);
    v64 = *((_QWORD *)a6 + 7);
    *((_QWORD *)a6 + 7) = 0;
    PostDropEvent(v54, v59, v245, a6, v55, v64, v61, v62, *((_QWORD *)&v313 + 1), v63, v272, v246, v256, v225);
    v65 = v225[0];
    *v56 = v225[0];
    if ( v65 )
      goto LABEL_137;
    v275 = 3129;
    v205 = (int *)operator new(0x10u, v54, "Sql\\Ntdbms\\msql\\ddl\\drop.cpp", 3129, 3u);
    v206 = v205;
    v284 = (CSourceCollection *)v205;
    if ( v205 )
    {
      *v205 = v231;
      v205[1] = v229;
    }
    else
    {
      v206 = 0;
    }
    operator delete(*((void **)a6 + 28), 0);
    *((_QWORD *)a6 + 28) = v206;
  }
  else if ( a6 )
  {
    v204 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)a6 + 7);
    *((_QWORD *)a6 + 7) = 0;
    if ( v204 )
      (**v204)(v204, 1);
LABEL_137:
    CXStmtDDL::CleanupXactBHF(a6, v245, 1);
    v66 = (void (__fastcall ***)(_QWORD, bool))*((_QWORD *)a6 + 7);
    if ( v66 )
      (**v66)(v66, *((_QWORD *)a6 + 8) == 0);
    *((_QWORD *)a6 + 7) = 0;
    *((_BYTE *)a6 + 176) |= 0x10u;
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)a6 + 23) + 464LL))(*((_QWORD *)a6 + 23))
      && *((_BYTE *)a6 + 192) )
    {
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)a6 + 23) + 24LL))(*((_QWORD *)a6 + 23), 2, 0);
    }
    *((_BYTE *)a6 + 192) = 0;
    *((_BYTE *)a6 + 176) &= ~0x10u;
  }
  operator delete[](v269);
  if ( (_DWORD)v263 )
    CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v263, 0);
}

```

## disassembly

```asm
0x1006f97a0  push    rbx
0x1006f97a2  push    rsi
0x1006f97a3  push    rdi
0x1006f97a4  push    r12
0x1006f97a6  push    r13
0x1006f97a8  push    r14
0x1006f97aa  push    r15
0x1006f97ac  sub     rsp, 0B80h
0x1006f97b3  mov     [rsp+0BB8h+var_640], 0FFFFFFFFFFFFFFFEh
0x1006f97bf  mov     rax, cs:__security_cookie
0x1006f97c6  xor     rax, rsp
0x1006f97c9  mov     [rsp+0BB8h+var_48], rax
0x1006f97d1  mov     ebx, edx
0x1006f97d3  mov     [rsp+0BB8h+var_B38], edx
0x1006f97da  mov     r15, rcx
0x1006f97dd  mov     [rsp+0BB8h+var_B18], rcx
0x1006f97e5  mov     [rsp+0BB8h+var_B40], r8d
0x1006f97ea  mov     [rsp+0BB8h+var_AD0], r9
0x1006f97f2  mov     rax, [rsp+0BB8h+arg_20]
0x1006f97fa  mov     [rsp+0BB8h+var_960], rax
0x1006f9802  mov     r12, [rsp+0BB8h+arg_28]
0x1006f980a  mov     [rsp+0BB8h+var_998], r12
0x1006f9812  mov     rdi, [rsp+0BB8h+arg_30]
0x1006f981a  mov     [rsp+0BB8h+var_940], rdi
0x1006f9822  mov     [rsp+0BB8h+var_928], rdi
0x1006f982a  mov     rax, [rsp+0BB8h+arg_38]
0x1006f9832  mov     [rsp+0BB8h+var_990], rax
0x1006f983a  mov     r13, [rsp+0BB8h+arg_40]
0x1006f9842  mov     [rsp+0BB8h+var_938], r13
0x1006f984a  mov     [rsp+0BB8h+var_930], r13
0x1006f9852  mov     rsi, [rsp+0BB8h+arg_48]
0x1006f985a  mov     rax, [rsp+0BB8h+arg_50]
0x1006f9862  mov     [rsp+0BB8h+var_A90], rax
0x1006f986a  mov     rdx, gs:58h
0x1006f9873  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1006f987a  mov     ecx, [rax]
0x1006f987c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1006f9883  mov     eax, [rax]
0x1006f9885  add     rax, [rdx+rcx*8]
0x1006f9889  mov     rax, [rax]
0x1006f988c  mov     rcx, [rax+90h]
0x1006f9893  mov     [rsp+0BB8h+var_A30], rcx
0x1006f989b  mov     rax, [rcx]
0x1006f989e  call    qword ptr [rax+1D0h]
0x1006f98a4  movzx   eax, al
0x1006f98a7  mov     [rsp+0BB8h+var_A0C], eax
0x1006f98ae  xor     r14d, r14d
0x1006f98b1  mov     [rsp+0BB8h+var_9E8], r14
0x1006f98b9  mov     [rsp+0BB8h+var_A80], r14
0x1006f98c1  mov     [rsp+0BB8h+var_A78], 1
0x1006f98cc  xorps   xmm0, xmm0
0x1006f98cf  movdqu  [rsp+0BB8h+var_A70], xmm0
0x1006f98d8  test    r13, r13
0x1006f98db  jz      short loc_1006F98E2
0x1006f98dd  mov     byte ptr [r13+0], 1
0x1006f98e2  test    rsi, rsi
0x1006f98e5  jz      short loc_1006F98EA
0x1006f98e7  mov     byte ptr [rsi], 0
0x1006f98ea  mov     r8d, ebx; int
0x1006f98ed  mov     rdx, r15; wchar_t *
0x1006f98f0  lea     rcx, [rsp+0BB8h+var_8F8]; this
0x1006f98f8  call    ?Parse@WParseName@@QEAAXPEB_WH@Z; WParseName::Parse(wchar_t const *,int)
0x1006f98fd  mov     ecx, [rsp+0BB8h+var_8CC]
0x1006f9904  add     ecx, ecx
0x1006f9906  jz      short loc_1006F991B
0x1006f9908  mov     rax, [rsp+0BB8h+var_8E0]
0x1006f9910  cmp     word ptr [rax], 23h ; '#'
0x1006f9914  mov     eax, 1
0x1006f9919  jz      short loc_1006F991E
0x1006f991b  mov     eax, r14d
0x1006f991e  mov     [rsp+0BB8h+var_AE8], eax
0x1006f9925  mov     [rsp+0BB8h+var_A08], eax
0x1006f992c  test    rdi, rdi
0x1006f992f  jz      loc_100B52A53
0x1006f9935  mov     rbx, [rdi+78h]
0x1006f9939  mov     [rsp+0BB8h+var_AD8], rbx
0x1006f9941  mov     [rsp+0BB8h+var_9E8], rbx
0x1006f9949  mov     dword ptr [rsp+0BB8h+var_B98], 0Eh; int
0x1006f9951  lea     r9, aDropobj; "DROPOBJ"
0x1006f9958  mov     r8, [rsp+0BB8h+var_AD0]; struct CCompExecCtxt *
0x1006f9960  mov     rdx, rbx; struct IMemObj *
0x1006f9963  mov     rcx, r12; this
0x1006f9966  call    ?BeginDropXact@CXStmtDropDDL@@QEAAXPEAVIMemObj@@AEBVCCompExecCtxt@@PEB_WH@Z; CXStmtDropDDL::BeginDropXact(IMemObj *,CCompExecCtxt const &,wchar_t const *,int)
0x1006f996b  mov     byte ptr [r12+0F1h], 0
0x1006f9974  jmp     short loc_1006F9977
0x1006f9977  mov     [rsp+0BB8h+var_B20], r14d
0x1006f997f  mov     [rsp+0BB8h+var_B30], r14d
0x1006f9987  mov     [rsp+0BB8h+var_AA0], r14d
0x1006f998f  mov     [rsp+0BB8h+var_A28], r14
0x1006f9997  mov     [rsp+0BB8h+var_AC8], r14d
0x1006f999f  mov     [rsp+0BB8h+var_A9C], r14d
0x1006f99a7  mov     [rsp+0BB8h+var_A48], r14
0x1006f99af  mov     [rsp+0BB8h+var_AF0], r14
0x1006f99b7  mov     r13d, r14d
0x1006f99ba  mov     [rsp+0BB8h+var_A10], r14d
0x1006f99c2  xor     edx, edx; unsigned __int16
0x1006f99c4  mov     [rsp+0BB8h+var_B90], r14; struct Worker *
0x1006f99c9  lea     rax, ?hdl_DDLprntbackout@@YAHHHHHPEAD@Z; hdl_DDLprntbackout(int,int,int,int,char *)
0x1006f99d0  mov     [rsp+0BB8h+var_B98], rax; int
0x1006f99d5  xor     r9d, r9d; unsigned __int8
0x1006f99d8  xor     r8d, r8d; unsigned __int8
0x1006f99db  lea     rcx, [rsp+0BB8h+var_718]; this
0x1006f99e3  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x1006f99e8  nop
0x1006f99e9  mov     [rsp+0BB8h+var_AB8], r14
0x1006f99f1  test    r12, r12
0x1006f99f4  jz      loc_100B52AB8
0x1006f99fa  mov     rax, [r12]
0x1006f99fe  mov     rcx, r12
0x1006f9a01  call    qword ptr [rax+68h]
0x1006f9a04  test    byte ptr [r12+0B0h], 20h
0x1006f9a0d  jz      loc_100B52AAA
0x1006f9a13  mov     rcx, [r12+70h]
0x1006f9a18  jmp     short loc_1006F9A1B
0x1006f9a1b  mov     rax, [rcx]
0x1006f9a1e  call    qword ptr [rax+1B0h]
0x1006f9a24  mov     [rsp+0BB8h+var_A60], rax
0x1006f9a2c  mov     rdi, [r12+38h]
0x1006f9a31  mov     [rsp+0BB8h+var_B28], rdi
0x1006f9a39  mov     [rsp+0BB8h+var_B10], rdi
0x1006f9a41  jmp     short loc_1006F9A44
0x1006f9a44  lea     rax, ??_7IFFtStoreContext@@6B@; const IFFtStoreContext::`vftable'
0x1006f9a4b  mov     [rsp+0BB8h+var_988], rax
0x1006f9a53  lea     rax, ??_7CTriggerTarget@@6B@; const CTriggerTarget::`vftable'
0x1006f9a5a  mov     [rsp+0BB8h+var_988], rax
0x1006f9a62  mov     [rsp+0BB8h+var_980], rdi
0x1006f9a6a  mov     [rsp+0BB8h+var_978], 14h
0x1006f9a75  mov     [rsp+0BB8h+var_970], r14
0x1006f9a7d  lea     rax, [rsp+0BB8h+var_988]
0x1006f9a85  mov     [rsp+0BB8h+var_9A0], rax
0x1006f9a8d  mov     [rsp+0BB8h+var_A50], r14d
0x1006f9a95  test    r12, r12
0x1006f9a98  jz      loc_100B52C8F
0x1006f9a9e  mov     rax, [r12+20h]
0x1006f9aa3  movzx   eax, byte ptr [rax+8A0h]
0x1006f9aaa  jmp     short loc_1006F9AAD
0x1006f9aad  mov     [rsp+0BB8h+var_B48], al
0x1006f9ab1  mov     [rsp+0BB8h+var_A88], al
0x1006f9ab8  mov     rcx, [rsp+0BB8h+var_990]
0x1006f9ac0  test    rcx, rcx
0x1006f9ac3  jnz     loc_100B52C97
0x1006f9ac9  test    rsi, rsi
0x1006f9acc  jz      loc_1006F9BB1
0x1006f9ad2  mov     byte ptr [rsi], 0
0x1006f9ad5  mov     rax, cs:qword_102EF3550
0x1006f9adc  cmp     byte ptr [rax+156h], 0
0x1006f9ae3  jz      short loc_1006F9B4C
0x1006f9ae5  mov     rax, cs:qword_102ECFB10
0x1006f9aec  movzx   ecx, byte ptr [rax+5ADh]
0x1006f9af3  shr     cl, 1
0x1006f9af5  mov     [rsp+0BB8h+var_A87], cl
0x1006f9afc  test    cl, 1
0x1006f9aff  jnz     short loc_1006F9B4C
0x1006f9b01  movups  xmm0, [rsp+0BB8h+var_8F8]
0x1006f9b09  movaps  [rsp+0BB8h+var_5D8], xmm0
0x1006f9b11  movups  xmm1, xmmword ptr [rsp+2D0h]
0x1006f9b19  movaps  [rsp+0BB8h+var_5C8], xmm1
0x1006f9b21  movups  xmm0, xmmword ptr [rsp+2E0h]
0x1006f9b29  movaps  [rsp+0BB8h+var_5B8], xmm0
0x1006f9b31  xor     r9d, r9d
0x1006f9b34  lea     r8d, [r9+0Eh]
0x1006f9b38  lea     rdx, aCalldropobject; "CallDropObject"
0x1006f9b3f  lea     rcx, [rsp+0BB8h+var_5D8]
0x1006f9b47  call    ?FindAndKillBlockingTupleMover@@YAXVWParseName@@PEB_WK_N@Z; FindAndKillBlockingTupleMover(WParseName,wchar_t const *,ulong,bool)
0x1006f9b4c  mov     rax, [rdi]
0x1006f9b4f  mov     byte ptr [rsp+0BB8h+var_B68], 0
0x1006f9b54  mov     dword ptr [rsp+0BB8h+var_B70], r14d
0x1006f9b59  mov     dword ptr [rsp+0BB8h+var_B78], r14d
0x1006f9b5e  mov     qword ptr [rsp+0BB8h+var_B80], r14
0x1006f9b63  mov     qword ptr [rsp+0BB8h+var_B88], r14
0x1006f9b68  mov     [rsp+0BB8h+var_B90], r14
0x1006f9b6d  mov     [rsp+0BB8h+var_B98], r14
0x1006f9b72  xor     r9d, r9d
0x1006f9b75  mov     r8b, 5
0x1006f9b78  lea     rdx, [rsp+0BB8h+var_8F8]
0x1006f9b80  mov     rcx, rdi
0x1006f9b83  call    qword ptr [rax+28h]
0x1006f9b86  mov     rbx, rax
0x1006f9b89  test    rax, rax
0x1006f9b8c  jz      short loc_1006F9BB1
0x1006f9b8e  mov     r8, [rax]
0x1006f9b91  lea     rdx, [rsp+0BB8h+var_218]
0x1006f9b99  mov     rcx, rax
0x1006f9b9c  call    qword ptr [r8+60h]
0x1006f9ba0  cmp     [rsp+0BB8h+var_210], 2050h
0x1006f9bab  jz      loc_100B52DAF
0x1006f9bb1  mov     r13d, 1
0x1006f9bb7  mov     rax, [rdi]
0x1006f9bba  mov     byte ptr [rsp+0BB8h+var_B68], 0
0x1006f9bbf  mov     dword ptr [rsp+0BB8h+var_B70], r14d
0x1006f9bc4  mov     dword ptr [rsp+0BB8h+var_B78], r14d
0x1006f9bc9  mov     qword ptr [rsp+0BB8h+var_B80], r14
0x1006f9bce  mov     qword ptr [rsp+0BB8h+var_B88], r14
0x1006f9bd3  mov     [rsp+0BB8h+var_B90], r14
0x1006f9bd8  mov     [rsp+0BB8h+var_B98], r14
0x1006f9bdd  xor     r9d, r9d
0x1006f9be0  mov     r8b, 2
0x1006f9be3  lea     rdx, [rsp+0BB8h+var_8F8]
0x1006f9beb  mov     rcx, rdi
0x1006f9bee  call    qword ptr [rax+28h]
0x1006f9bf1  mov     rbx, [rsp+0BB8h+var_AD0]
0x1006f9bf9  mov     r15, rax
0x1006f9bfc  mov     [rsp+0BB8h+var_B00], rax
0x1006f9c04  test    rax, rax
0x1006f9c07  jz      loc_100B52E42
0x1006f9c0d  xorps   xmm0, xmm0
0x1006f9c10  movups  [rsp+0BB8h+var_248], xmm0
0x1006f9c18  movups  [rsp+0BB8h+var_238], xmm0
0x1006f9c20  movups  [rsp+0BB8h+var_228], xmm0
0x1006f9c28  mov     [rsp+0BB8h+var_AE4], r14w
0x1006f9c31  xor     edx, edx; Val
0x1006f9c33  mov     r8d, 188h; Size
0x1006f9c39  lea     rcx, [rsp+0BB8h+var_1D8]; void *
0x1006f9c41  call    memset_0
0x1006f9c46  mov     [rsp+0BB8h+var_60], 0FFFFFFFFh
0x1006f9c51  mov     rax, [r15]
0x1006f9c54  mov     rcx, r15
0x1006f9c57  call    qword ptr [rax]
0x1006f9c59  mov     ebx, eax
0x1006f9c5b  mov     [rsp+0BB8h+var_B30], eax
0x1006f9c62  mov     rdx, [r15]
0x1006f9c65  mov     rcx, r15
0x1006f9c68  call    qword ptr [rdx+8]
0x1006f9c6b  mov     [rsp+0BB8h+var_B20], eax
0x1006f9c72  mov     rdx, [r15]
0x1006f9c75  mov     rcx, r15
0x1006f9c78  call    qword ptr [rdx+78h]
0x1006f9c7b  mov     rsi, rax
0x1006f9c7e  mov     [rsp+0BB8h+var_B08], rax
0x1006f9c86  mov     rdx, [r15]
0x1006f9c89  mov     rcx, r15
0x1006f9c8c  call    qword ptr [rdx+0A8h]
0x1006f9c92  mov     [rsp+0BB8h+var_9F8], rax
0x1006f9c9a  mov     r10, [rdi]
0x1006f9c9d  mov     dword ptr [rsp+0BB8h+var_B90], r14d
0x1006f9ca2  mov     dword ptr [rsp+0BB8h+var_B98], r14d
0x1006f9ca7  xor     r9d, r9d
0x1006f9caa  xor     r8d, r8d
0x1006f9cad  mov     edx, ebx
0x1006f9caf  mov     rcx, rdi
0x1006f9cb2  call    qword ptr [r10+38h]
0x1006f9cb6  mov     [rsp+0BB8h+var_AF0], rax
0x1006f9cbe  mov     rax, [r15]
0x1006f9cc1  lea     rdx, [rsp+0BB8h+var_258]
0x1006f9cc9  mov     rcx, r15
0x1006f9ccc  call    qword ptr [rax+60h]
0x1006f9ccf  test    rsi, rsi
0x1006f9cd2  jz      short loc_1006F9CE5
0x1006f9cd4  mov     rax, [rsi]
0x1006f9cd7  lea     rdx, [rsp+0BB8h+var_248]
0x1006f9cdf  mov     rcx, rsi
0x1006f9ce2  call    qword ptr [rax+10h]
0x1006f9ce5  mov     rcx, [rsp+0BB8h+var_9F8]
0x1006f9ced  test    rcx, rcx
0x1006f9cf0  jz      short loc_1006F9D00
0x1006f9cf2  mov     rax, [rcx]
0x1006f9cf5  lea     rdx, [rsp+0BB8h+var_AE4]
0x1006f9cfd  call    qword ptr [rax+20h]
0x1006f9d00  mov     eax, [rsp+0BB8h+var_250]
0x1006f9d07  cmp     eax, 4641h
0x1006f9d0c  jz      loc_100B52EDE
0x1006f9d12  cmp     eax, 5346h
0x1006f9d17  jz      loc_100B52EDE
0x1006f9d1d  cmp     eax, 5446h
0x1006f9d22  jz      loc_100B52EDE
0x1006f9d28  cmp     eax, 4350h
0x1006f9d2d  jz      loc_100B52EDE
0x1006f9d33  cmp     eax, 4154h
0x1006f9d38  jz      loc_100B52EDE
0x1006f9d3e  mov     rax, [r15]
0x1006f9d41  mov     rcx, r15
0x1006f9d44  call    qword ptr [rax+0B0h]
0x1006f9d4a  test    rax, rax
0x1006f9d4d  jnz     loc_100B52EF2
0x1006f9d53  cmp     [rsp+0BB8h+var_AE8], 0
0x1006f9d5b  jnz     short loc_1006F9D6F
0x1006f9d5d  mov     rdx, r15; struct IMEDObject *
0x1006f9d60  mov     rcx, rdi; struct IMetadataAccess *
0x1006f9d63  call    ?FHasDropObjectPerms@CDDLPermissions@@SAEPEAVIMetadataAccess@@PEAVIMEDObject@@@Z; CDDLPermissions::FHasDropObjectPerms(IMetadataAccess *,IMEDObject *)
0x1006f9d68  test    al, al
0x1006f9d6a  mov     ebx, r14d
0x1006f9d6d  jz      short loc_1006F9D74
0x1006f9d6f  mov     ebx, 1
0x1006f9d74  mov     [rsp+0BB8h+var_B34], ebx
0x1006f9d7b  mov     rax, cs:__imp_?m_ProfilerTraceEnabled@CommonGlobalState@@2_NA; bool CommonGlobalState::m_ProfilerTraceEnabled
0x1006f9d82  movzx   ecx, byte ptr [rax]
0x1006f9d85  mov     [rsp+0BB8h+var_A86], cl
0x1006f9d8c  test    cl, cl
0x1006f9d8e  jz      short loc_1006F9DA4
0x1006f9d90  mov     rax, cs:qword_102ECFB00
0x1006f9d97  test    dword ptr [rax+48h], 400000h
0x1006f9d9e  jnz     loc_100B52F3B
0x1006f9da4  test    ebx, ebx
0x1006f9da6  jz      loc_100B52FA4
0x1006f9dac  mov     r13d, [rsp+0BB8h+var_B40]
0x1006f9db1  mov     eax, [rsp+0BB8h+var_250]
0x1006f9db8  cmp     r13d, 2055h
0x1006f9dbf  jz      loc_100B53143
0x1006f9dc5  cmp     r13d, 2050h
0x1006f9dcc  jz      loc_100B53250
  ... truncated ...
```
