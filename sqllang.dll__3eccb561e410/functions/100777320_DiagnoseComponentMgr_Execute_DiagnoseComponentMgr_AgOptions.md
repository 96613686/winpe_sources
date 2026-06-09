# DiagnoseComponentMgr::Execute(DiagnoseComponentMgr::AgOptions)

- ea: `0x100777320`
- end: `0x10077804d`
- name: `?Execute@DiagnoseComponentMgr@@QEAAXW4AgOptions@1@@Z`
- size: `3373`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x10121f460`
- `0x101753cb0`

## callees

- `0x100401070`
- `0x100401450`
- `0x100402150`
- `0x100402410`
- `0x100430d60`
- `0x100430e10`
- `0x1007767b0`
- `0x100776800`
- `0x1007772c0`
- `0x100777320`
- `0x100778060`
- `0x100778240`
- `0x100a24c60`
- `0x10174b930`
- `0x10174bac0`
- `0x10174ec30`
- `0x10174f070`
- `0x10179daa0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1007778bf`
- `KERNEL32!QueryPerformanceCounter` at `0x10077792c`
- `KERNEL32!QueryPerformanceCounter` at `0x1007779bf`
- `KERNEL32!QueryPerformanceCounter` at `0x100777f08`
- `KERNEL32!QueryPerformanceCounter` at `0x10174f7eb`
- `KERNEL32!QueryPerformanceCounter` at `0x10174f99f`
- `KERNEL32!QueryPerformanceCounter` at `0x1007778bf`
- `KERNEL32!QueryPerformanceCounter` at `0x10077792c`
- `KERNEL32!QueryPerformanceCounter` at `0x1007779bf`
- `KERNEL32!QueryPerformanceCounter` at `0x100777f08`
- `KERNEL32!QueryPerformanceCounter` at `0x10174f7eb`
- `KERNEL32!QueryPerformanceCounter` at `0x10174f99f`
- `KERNEL32!GetCurrentThread` at `0x1007774f3`
- `KERNEL32!GetCurrentThread` at `0x1007774f3`
- `sqldk!?sm_AffinityMask@SOS_PublicGlobals@@2VSystemAffinity@@A` at `0x100777447`
- `sqldk!?sm_AffinityMask@SOS_PublicGlobals@@2VSystemAffinity@@A` at `0x100777476`
- `sqldk!?sm_AffinityMask@SOS_PublicGlobals@@2VSystemAffinity@@A` at `0x1007774c5`
- `sqldk!?SafeCopy@SystemAffinity@@QEBA?AV1@XZ` at `0x10077744e`
- `sqldk!?SafeCopy@SystemAffinity@@QEBA?AV1@XZ` at `0x10077747d`
- `sqldk!?SafeCopy@SystemAffinity@@QEBA?AV1@XZ` at `0x1007774cc`
- `sqldk!?SafeCopy@SystemAffinity@@QEBA?AV1@XZ` at `0x10077744e`
- `sqldk!?SafeCopy@SystemAffinity@@QEBA?AV1@XZ` at `0x10077747d`
- `sqldk!?SafeCopy@SystemAffinity@@QEBA?AV1@XZ` at `0x1007774cc`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x100777f9a`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10077789f`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10077790c`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10077799f`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100777ee8`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100777f82`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10174f7cb`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10174f983`
- `sqldk!?Instance@OsNumaConfig@@SAPEAV1@XZ` at `0x10077750f`
- `sqldk!?Instance@OsNumaConfig@@SAPEAV1@XZ` at `0x10174fcb7`
- `sqldk!?Instance@OsNumaConfig@@SAPEAV1@XZ` at `0x10077750f`
- `sqldk!?Instance@OsNumaConfig@@SAPEAV1@XZ` at `0x10174fcb7`
- `sqldk!?GetGroup@NodeAffinity@@QEBAGXZ` at `0x10077748b`
- `sqldk!?GetGroup@NodeAffinity@@QEBAGXZ` at `0x10077748b`
- `sqldk!?GetNodeAffinity@SystemAffinity@@QEBA?AVNodeAffinity@@G@Z` at `0x100777468`
- `sqldk!?GetNodeAffinity@SystemAffinity@@QEBA?AVNodeAffinity@@G@Z` at `0x100777468`
- `sqldk!?GetFirstGroupSet@SystemAffinity@@QEBA?BVGroupAffinity@@XZ` at `0x1007774e2`
- `sqldk!?GetFirstGroupSet@SystemAffinity@@QEBA?BVGroupAffinity@@XZ` at `0x1007774e2`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10077770d`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10077770d`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10174fbcd`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10174fbcd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1007773c8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1007773c8`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1007775b2`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1007775da`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1007775b2`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1007775da`
- `sqldk!SystemThread_TlsIndex` at `0x10077737b`
- `sqldk!SystemThread_TlsIndex` at `0x1007773f3`
- `sqldk!SystemThread_TlsIndex` at `0x100777638`
- `sqldk!SystemThread_TlsIndex` at `0x1007777fc`
- `sqldk!SystemThread_TlsIndex` at `0x100777e79`
- `sqldk!SystemThread_TlsIndex` at `0x10174f8df`
- `sqldk!SystemThread_TlsIndex` at `0x10174f947`
- `sqldk!SystemThread_TlsIndex` at `0x10174fb95`
- `sqldk!SystemThread_TlsOffset` at `0x100777384`
- `sqldk!SystemThread_TlsOffset` at `0x1007773fc`
- `sqldk!SystemThread_TlsOffset` at `0x100777641`
- `sqldk!SystemThread_TlsOffset` at `0x100777805`
- `sqldk!SystemThread_TlsOffset` at `0x100777e82`
- `sqldk!SystemThread_TlsOffset` at `0x10174f8e8`
- `sqldk!SystemThread_TlsOffset` at `0x10174f950`
- `sqldk!SystemThread_TlsOffset` at `0x10174fb9e`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10174fc19`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10174fc19`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100777417`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10174faf5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10174fbb7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100777417`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10174faf5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10174fbb7`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100777667`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10077782b`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100777667`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10077782b`
- `sqldk!??_V@YAXPEAX@Z` at `0x10174fcb0`
- `sqldk!??_V@YAXPEAX@Z` at `0x10174fcb0`
- `sqldk!?GetCPUCount@GroupAffinity@@QEBAIXZ` at `0x1007774b3`
- `sqldk!?GetCPUCount@GroupAffinity@@QEBAIXZ` at `0x1007774b3`
- `sqldk!?GetGroupAffinity@SystemAffinity@@QEBA?BVGroupAffinity@@G@Z` at `0x1007774a5`
- `sqldk!?GetGroupAffinity@SystemAffinity@@QEBA?BVGroupAffinity@@G@Z` at `0x1007774a5`
- `sqldk!??0GroupAffinity@@QEAA@XZ` at `0x100777509`
- `sqldk!??0GroupAffinity@@QEAA@XZ` at `0x100777509`
- `sqlTsEs!??1CBufferedStream@@UEAA@XZ` at `0x100777d8c`
- `sqlTsEs!??1CBufferedStream@@UEAA@XZ` at `0x100777d8c`
- `sqlmin!?AddNewColumn@BackupResultSet@@IEAAXPEB_WW4ColumnType@BackupColumn@@I@Z` at `0x100777756`
- `sqlmin!?AddNewColumn@BackupResultSet@@IEAAXPEB_WW4ColumnType@BackupColumn@@I@Z` at `0x10077776d`
- `sqlmin!?AddNewColumn@BackupResultSet@@IEAAXPEB_WW4ColumnType@BackupColumn@@I@Z` at `0x100777784`
- `sqlmin!?AddNewColumn@BackupResultSet@@IEAAXPEB_WW4ColumnType@BackupColumn@@I@Z` at `0x10077779b`
- `sqlmin!?AddNewColumn@BackupResultSet@@IEAAXPEB_WW4ColumnType@BackupColumn@@I@Z` at `0x1007777b2`
- `sqlmin!?AddNewColumn@BackupResultSet@@IEAAXPEB_WW4ColumnType@BackupColumn@@I@Z` at `0x1007777ce`
- `sqlmin!?AddNewColumn@BackupResultSet@@IEAAXPEB_WW4ColumnType@BackupColumn@@I@Z` at `0x100777756`
- `sqlmin!?AddNewColumn@BackupResultSet@@IEAAXPEB_WW4ColumnType@BackupColumn@@I@Z` at `0x10077776d`
- `sqlmin!?AddNewColumn@BackupResultSet@@IEAAXPEB_WW4ColumnType@BackupColumn@@I@Z` at `0x100777784`
- `sqlmin!?AddNewColumn@BackupResultSet@@IEAAXPEB_WW4ColumnType@BackupColumn@@I@Z` at `0x10077779b`
- `sqlmin!?AddNewColumn@BackupResultSet@@IEAAXPEB_WW4ColumnType@BackupColumn@@I@Z` at `0x1007777b2`
- `sqlmin!?AddNewColumn@BackupResultSet@@IEAAXPEB_WW4ColumnType@BackupColumn@@I@Z` at `0x1007777ce`
- `sqlmin!??0BackupResultSet@@QEAA@PEAVBackupOperation@@KPEAVIMemObj@@@Z` at `0x100777731`
- `sqlmin!??0BackupResultSet@@QEAA@PEAVBackupOperation@@KPEAVIMemObj@@@Z` at `0x100777731`
- `sqlmin!??1BackupResultSet@@QEAA@XZ` at `0x10174fc0b`
- `sqlmin!??1BackupResultSet@@QEAA@XZ` at `0x10174fc0b`
- `sqlmin!?SetLongColumn@BackupResultSetRow@@QEAAXJ@Z` at `0x10174f71f`
- `sqlmin!?SetLongColumn@BackupResultSetRow@@QEAAXJ@Z` at `0x10174f71f`
- `sqlmin!?EndResultSet@BackupResultSet@@QEAAXH@Z` at `0x10174f8d0`
- `sqlmin!?EndResultSet@BackupResultSet@@QEAAXH@Z` at `0x10174f8d0`
- `sqlmin!?SetDateColumn@BackupResultSetRow@@QEAAXUSQLDATE@@@Z` at `0x10174f6e9`
- `sqlmin!?SetDateColumn@BackupResultSetRow@@QEAAXUSQLDATE@@@Z` at `0x10174f6e9`
- `sqlmin!?SetNullColumn@BackupResultSetRow@@QEAAXK@Z` at `0x10174f765`
- `sqlmin!?SetNullColumn@BackupResultSetRow@@QEAAXK@Z` at `0x10174f765`
- `sqlmin!?SetNameColumn@BackupResultSetRow@@QEAAXPEB_W@Z` at `0x10174f6fe`
- `sqlmin!?SetNameColumn@BackupResultSetRow@@QEAAXPEB_W@Z` at `0x10174f712`
- `sqlmin!?SetNameColumn@BackupResultSetRow@@QEAAXPEB_W@Z` at `0x10174f738`
- `sqlmin!?SetNameColumn@BackupResultSetRow@@QEAAXPEB_W@Z` at `0x10174f6fe`
- `sqlmin!?SetNameColumn@BackupResultSetRow@@QEAAXPEB_W@Z` at `0x10174f712`
- `sqlmin!?SetNameColumn@BackupResultSetRow@@QEAAXPEB_W@Z` at `0x10174f738`
- `sqlmin!?SetStringColumn@BackupResultSetRow@@QEAAXPEAUIBlobHandle@@H@Z` at `0x10174f879`
- `sqlmin!?SetStringColumn@BackupResultSetRow@@QEAAXPEAUIBlobHandle@@H@Z` at `0x10174f879`
- `sqlmin!?utgettime@@YAXPEAUSQLDATEBASE@@HPEA_N@Z` at `0x100777a1a`
- `sqlmin!?utgettime@@YAXPEAUSQLDATEBASE@@HPEA_N@Z` at `0x100777a1a`

## string_xrefs

- `0x10077777a`: `component_name`
- `0x10077774c`: `create_time`
- `0x100777763`: `component_type`
- `0x1007775cb`: `sql\ntdbms\msql\xmldb\common\xmlwriter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall DiagnoseComponentMgr::Execute(__int64 a1)
{
  __int64 v1; // r13
  int v2; // ebx
  __int64 v3; // rbx
  __int64 v4; // rax
  __int64 v5; // rcx
  unsigned __int16 v6; // bx
  unsigned __int16 Group; // ax
  __int64 v8; // rax
  int v9; // ebx
  __int64 v10; // rdi
  bool v11; // zf
  void *v12; // rax
  __int64 v13; // rdx
  int v14; // ebx
  DiagEventSessionMgr *v15; // rax
  __int64 v16; // rax
  struct CSessionTraceFlags *v17; // rcx
  struct DiagEventSessionMgr *v18; // rax
  unsigned int v19; // edi
  __int64 *v20; // rsi
  __int64 v21; // rbx
  __int64 v22; // rcx
  BackupResultSet *v23; // rax
  BackupResultSet *v24; // rbx
  __int64 v25; // rax
  struct CSessionTraceFlags *v26; // rcx
  CSbTransportMgr *QuadPart; // rax
  CSbTransportMgr *v28; // rax
  CSbTransportMgr *v29; // rax
  __int64 v30; // rax
  void *v31; // rbx
  CSsXmlWriter *v32; // rdi
  BackupResultSet *v33; // rsi
  struct DiagnoseComponent *v34; // r15
  int v35; // r12d
  __int64 v36; // rcx
  void *v37; // rax
  int v38; // eax
  __int64 v39; // rbx
  __int64 v40; // rax
  int v41; // eax
  CSbTransportMgr *v42; // rcx
  unsigned __int64 v43; // rcx
  unsigned __int64 v44; // rax
  unsigned __int64 v45; // rdx
  __int64 v46; // rcx
  const wchar_t *v47; // rax
  const wchar_t *v48; // rax
  CSbTransportMgr *v49; // rax
  __int64 v50; // rcx
  __int64 v51; // rcx
  CSbTransportMgr *v52; // rax
  __int64 v53; // rbx
  struct Worker *v54; // rcx
  int v55; // ebx
  void ***v56; // rdi
  struct DiagEventSessionMgr *v57; // rax
  __int64 v58; // rax
  __int64 result; // rax
  const struct SQLError *CurrentException; // rax
  int v61; // [rsp+40h] [rbp-DE8h]
  int v62; // [rsp+50h] [rbp-DD8h]
  int v63; // [rsp+70h] [rbp-DB8h]
  BOOL v64; // [rsp+78h] [rbp-DB0h]
  unsigned int v65; // [rsp+78h] [rbp-DB0h]
  int v66; // [rsp+80h] [rbp-DA8h]
  BackupResultSet *v67; // [rsp+88h] [rbp-DA0h]
  unsigned int v68; // [rsp+90h] [rbp-D98h]
  void *v69; // [rsp+98h] [rbp-D90h]
  BackupResultSetRow *v70; // [rsp+A0h] [rbp-D88h]
  struct CSsXmlWriter *SSXmlWriterInPlace; // [rsp+C0h] [rbp-D68h]
  CSbTransportMgr *v72; // [rsp+E8h] [rbp-D40h] BYREF
  unsigned __int64 v73; // [rsp+F0h] [rbp-D38h]
  __int64 v74; // [rsp+F8h] [rbp-D30h]
  void *v75; // [rsp+100h] [rbp-D28h]
  unsigned __int64 v76; // [rsp+108h] [rbp-D20h] BYREF
  CSbTransportMgr *v77; // [rsp+110h] [rbp-D18h] BYREF
  CSbTransportMgr *v78; // [rsp+118h] [rbp-D10h] BYREF
  CSbTransportMgr *v79; // [rsp+120h] [rbp-D08h] BYREF
  __int64 v80; // [rsp+128h] [rbp-D00h] BYREF
  CSbTransportMgr *v81; // [rsp+130h] [rbp-CF8h] BYREF
  CSbTransportMgr *v82; // [rsp+138h] [rbp-CF0h] BYREF
  __int64 v83; // [rsp+140h] [rbp-CE8h] BYREF
  CSbTransportMgr *v84; // [rsp+148h] [rbp-CE0h] BYREF
  CSbTransportMgr *v85; // [rsp+150h] [rbp-CD8h] BYREF
  __int64 v86; // [rsp+158h] [rbp-CD0h] BYREF
  unsigned __int64 v87; // [rsp+160h] [rbp-CC8h] BYREF
  CSbTransportMgr *v88; // [rsp+168h] [rbp-CC0h] BYREF
  CSbTransportMgr *v89; // [rsp+170h] [rbp-CB8h] BYREF
  BackupResultSet *v90; // [rsp+178h] [rbp-CB0h]
  __int64 v91; // [rsp+180h] [rbp-CA8h] BYREF
  int v92; // [rsp+188h] [rbp-CA0h]
  void ***v93; // [rsp+190h] [rbp-C98h] BYREF
  int v94; // [rsp+198h] [rbp-C90h]
  void **v95; // [rsp+1A0h] [rbp-C88h] BYREF
  void *v96; // [rsp+1A8h] [rbp-C80h]
  int v97; // [rsp+1B0h] [rbp-C78h]
  void *v98; // [rsp+1B8h] [rbp-C70h]
  int v99; // [rsp+1C0h] [rbp-C68h]
  int v100; // [rsp+1C4h] [rbp-C64h]
  int v101; // [rsp+1C8h] [rbp-C60h]
  int v102; // [rsp+1CCh] [rbp-C5Ch]
  int v103; // [rsp+1D0h] [rbp-C58h]
  int v104; // [rsp+1D4h] [rbp-C54h]
  int v105; // [rsp+1D8h] [rbp-C50h]
  int v106; // [rsp+1DCh] [rbp-C4Ch]
  int v107; // [rsp+1E0h] [rbp-C48h]
  int v108; // [rsp+1E4h] [rbp-C44h]
  int v109; // [rsp+1E8h] [rbp-C40h]
  int v110; // [rsp+1ECh] [rbp-C3Ch]
  int v111; // [rsp+1F0h] [rbp-C38h]
  int v112; // [rsp+1F4h] [rbp-C34h]
  int v113; // [rsp+1F8h] [rbp-C30h]
  LARGE_INTEGER PerformanceCount; // [rsp+200h] [rbp-C28h] BYREF
  LARGE_INTEGER v115; // [rsp+208h] [rbp-C20h] BYREF
  LARGE_INTEGER v116; // [rsp+210h] [rbp-C18h] BYREF
  __int64 v117; // [rsp+218h] [rbp-C10h] BYREF
  LARGE_INTEGER v118; // [rsp+220h] [rbp-C08h] BYREF
  CSbTransportMgr *v119; // [rsp+228h] [rbp-C00h]
  struct DiagnoseComponent *v120; // [rsp+230h] [rbp-BF8h]
  LARGE_INTEGER v121; // [rsp+238h] [rbp-BF0h] BYREF
  CSbTransportMgr *v122; // [rsp+240h] [rbp-BE8h]
  LARGE_INTEGER v123; // [rsp+248h] [rbp-BE0h] BYREF
  __int64 v124; // [rsp+250h] [rbp-BD8h]
  __int64 v125; // [rsp+258h] [rbp-BD0h]
  int v126; // [rsp+260h] [rbp-BC8h]
  unsigned __int64 v127; // [rsp+268h] [rbp-BC0h]
  int v128; // [rsp+270h] [rbp-BB8h]
  int v129; // [rsp+274h] [rbp-BB4h]
  void **v130; // [rsp+278h] [rbp-BB0h] BYREF
  int v131; // [rsp+280h] [rbp-BA8h]
  void *v132; // [rsp+288h] [rbp-BA0h]
  int v133; // [rsp+290h] [rbp-B98h]
  int v134; // [rsp+298h] [rbp-B90h]
  _QWORD v135[2]; // [rsp+2A0h] [rbp-B88h] BYREF
  int v136; // [rsp+2B0h] [rbp-B78h]
  _BYTE v137[16]; // [rsp+2B8h] [rbp-B70h] BYREF
  int v138; // [rsp+2C8h] [rbp-B60h] BYREF
  __int64 v139; // [rsp+2D0h] [rbp-B58h]
  __int64 v140; // [rsp+2D8h] [rbp-B50h]
  __int64 v141; // [rsp+2E0h] [rbp-B48h]
  __int64 v142; // [rsp+2E8h] [rbp-B40h]
  int v143; // [rsp+2F0h] [rbp-B38h] BYREF
  __int64 v144; // [rsp+2F8h] [rbp-B30h]
  __int64 v145; // [rsp+300h] [rbp-B28h]
  __int64 v146; // [rsp+308h] [rbp-B20h]
  __int64 v147; // [rsp+310h] [rbp-B18h]
  CSbTransportMgr **v148; // [rsp+318h] [rbp-B10h]
  void *v149; // [rsp+320h] [rbp-B08h]
  void *v150; // [rsp+328h] [rbp-B00h]
  _WORD *v151; // [rsp+330h] [rbp-AF8h]
  _BYTE **v152; // [rsp+338h] [rbp-AF0h]
  void **v153; // [rsp+340h] [rbp-AE8h]
  void **v154; // [rsp+348h] [rbp-AE0h]
  __int64 v155; // [rsp+350h] [rbp-AD8h]
  __int64 *v156; // [rsp+358h] [rbp-AD0h]
  CSbTransportMgr **v157; // [rsp+360h] [rbp-AC8h]
  CSbTransportMgr **v158; // [rsp+368h] [rbp-AC0h]
  __int64 v159; // [rsp+370h] [rbp-AB8h]
  __int64 *v160; // [rsp+378h] [rbp-AB0h]
  CSbTransportMgr **v161; // [rsp+380h] [rbp-AA8h]
  CSbTransportMgr **v162; // [rsp+388h] [rbp-AA0h]
  _WORD *v163; // [rsp+390h] [rbp-A98h]
  int **v164; // [rsp+398h] [rbp-A90h]
  __int64 v165; // [rsp+3A0h] [rbp-A88h]
  __int64 v166; // [rsp+3A8h] [rbp-A80h]
  __int64 v167; // [rsp+3B0h] [rbp-A78h]
  __int64 *v168; // [rsp+3B8h] [rbp-A70h]
  __int64 v169; // [rsp+3C0h] [rbp-A68h]
  CSbTransportMgr **v170; // [rsp+3C8h] [rbp-A60h]
  unsigned __int64 *v171; // [rsp+3D0h] [rbp-A58h]
  CSbTransportMgr **v172; // [rsp+3D8h] [rbp-A50h]
  unsigned __int64 *v173; // [rsp+3E0h] [rbp-A48h]
  __int64 v174; // [rsp+3E8h] [rbp-A40h]
  __int64 v175; // [rsp+3F0h] [rbp-A38h]
  unsigned __int64 *v176; // [rsp+3F8h] [rbp-A30h]
  __int64 v177; // [rsp+400h] [rbp-A28h]
  CSbTransportMgr **v178; // [rsp+408h] [rbp-A20h]
  CSbTransportMgr **v179; // [rsp+410h] [rbp-A18h]
  _WORD *v180; // [rsp+418h] [rbp-A10h]
  _BYTE v181[16]; // [rsp+420h] [rbp-A08h] BYREF
  int **v182; // [rsp+430h] [rbp-9F8h]
  CSbTransportMgr **v183; // [rsp+438h] [rbp-9F0h]
  CSbTransportMgr **v184; // [rsp+440h] [rbp-9E8h]
  __int64 v185; // [rsp+448h] [rbp-9E0h]
  __int64 v186; // [rsp+450h] [rbp-9D8h]
  int v187; // [rsp+460h] [rbp-9C8h] BYREF
  __int64 v188; // [rsp+468h] [rbp-9C0h]
  _DWORD v189[2]; // [rsp+470h] [rbp-9B8h] BYREF
  __int64 v190; // [rsp+478h] [rbp-9B0h]
  char v191[64]; // [rsp+480h] [rbp-9A8h] BYREF
  _BYTE v192[32]; // [rsp+4C0h] [rbp-968h] BYREF
  char v193[8]; // [rsp+4E0h] [rbp-948h] BYREF
  _WORD v194[4]; // [rsp+4E8h] [rbp-940h] BYREF
  int v195; // [rsp+4F0h] [rbp-938h]
  _BYTE **v196; // [rsp+4F8h] [rbp-930h]
  char *v197; // [rsp+500h] [rbp-928h]
  __int64 v198; // [rsp+508h] [rbp-920h]
  _BYTE *v199; // [rsp+510h] [rbp-918h] BYREF
  int v200; // [rsp+518h] [rbp-910h]
  __int16 v201; // [rsp+51Ch] [rbp-90Ch]
  __int16 v202; // [rsp+51Eh] [rbp-90Ah]
  void *v203; // [rsp+520h] [rbp-908h] BYREF
  unsigned int v204; // [rsp+528h] [rbp-900h]
  __int16 v205; // [rsp+52Ch] [rbp-8FCh]
  __int16 v206; // [rsp+52Eh] [rbp-8FAh]
  char v207; // [rsp+530h] [rbp-8F8h] BYREF
  int v208; // [rsp+730h] [rbp-6F8h]
  int v209; // [rsp+734h] [rbp-6F4h]
  __int64 v210; // [rsp+738h] [rbp-6F0h]
  _BYTE v211[16]; // [rsp+740h] [rbp-6E8h] BYREF
  char v212[8]; // [rsp+750h] [rbp-6D8h] BYREF
  _WORD v213[4]; // [rsp+758h] [rbp-6D0h] BYREF
  int v214; // [rsp+760h] [rbp-6C8h]
  int **v215; // [rsp+768h] [rbp-6C0h]
  char *v216; // [rsp+770h] [rbp-6B8h]
  __int64 v217; // [rsp+778h] [rbp-6B0h]
  int *v218; // [rsp+780h] [rbp-6A8h] BYREF
  int v219; // [rsp+788h] [rbp-6A0h]
  __int16 v220; // [rsp+78Ch] [rbp-69Ch]
  __int16 v221; // [rsp+78Eh] [rbp-69Ah]
  char v222; // [rsp+790h] [rbp-698h] BYREF
  int v223; // [rsp+9A0h] [rbp-488h]
  int v224; // [rsp+9A4h] [rbp-484h]
  __int64 v225; // [rsp+9A8h] [rbp-480h]
  int v226; // [rsp+9B0h] [rbp-478h] BYREF
  __int64 v227; // [rsp+9B4h] [rbp-474h]
  char v228[8]; // [rsp+9C0h] [rbp-468h] BYREF
  _WORD v229[4]; // [rsp+9C8h] [rbp-460h] BYREF
  int v230; // [rsp+9D0h] [rbp-458h]
  int **v231; // [rsp+9D8h] [rbp-450h]
  char *v232; // [rsp+9E0h] [rbp-448h]
  __int64 v233; // [rsp+9E8h] [rbp-440h]
  int *v234; // [rsp+9F0h] [rbp-438h] BYREF
  int v235; // [rsp+9F8h] [rbp-430h]
  __int16 v236; // [rsp+9FCh] [rbp-42Ch]
  __int16 v237; // [rsp+9FEh] [rbp-42Ah]
  char v238; // [rsp+A00h] [rbp-428h] BYREF
  int v239; // [rsp+C10h] [rbp-218h]
  int v240; // [rsp+C14h] [rbp-214h]
  __int64 v241; // [rsp+C18h] [rbp-210h]
  int v242; // [rsp+C20h] [rbp-208h] BYREF
  __int64 v243; // [rsp+C24h] [rbp-204h]
  __int128 v244; // [rsp+C30h] [rbp-1F8h] BYREF
  HANDLE CurrentThread; // [rsp+C40h] [rbp-1E8h]
  _BYTE v246[16]; // [rsp+C48h] [rbp-1E0h] BYREF
  char v247[24]; // [rsp+C58h] [rbp-1D0h] BYREF
  _BYTE v248[128]; // [rsp+C70h] [rbp-1B8h] BYREF
  _BYTE v249[128]; // [rsp+CF0h] [rbp-138h] BYREF
  _BYTE v250[136]; // [rsp+D70h] [rbp-B8h] BYREF

  v177 = -2;
  v1 = a1;
  v124 = a1;
  v2 = 0;
  if ( *(_DWORD *)(a1 + 120) )
  {
    v2 = (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                              + SystemThread_TlsIndex)
                                            + SystemThread_TlsOffset)
                                + 128LL)
                    + 76LL) >> 9)
       & 1;
    if ( v2 )
    {
      if ( *(_DWORD *)(a1 + 48) )
        ex_raise(170, 73, 16, 1);
    }
  }
  SOS_Task::AutoSwitchPreemptive::AutoSwitchPreemptive(&v187, 536871721, v2 ^ 1u);
  v3 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v4 = *(_QWORD *)(v3 + 256);
  if ( !v4 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v4 = *(_QWORD *)(v3 + 256);
  }
  v5 = *(_QWORD *)(v4 + 992);
  v6 = 0;
  if ( (*(_BYTE *)(v5 + 1568) & 4) == 0 )
    v6 = *(_WORD *)(v5 + 160);
  SystemAffinity::SafeCopy(SOS_PublicGlobals::sm_AffinityMask, v248);
  SystemAffinity::GetNodeAffinity(v248, v181, v6);
  SystemAffinity::SafeCopy(SOS_PublicGlobals::sm_AffinityMask, v249);
  Group = NodeAffinity::GetGroup((NodeAffinity *)v181);
  SystemAffinity::GetGroupAffinity(v249, &v244, Group);
  if ( !GroupAffinity::GetCPUCount((GroupAffinity *)&v244) )
  {
    SystemAffinity::SafeCopy(SOS_PublicGlobals::sm_AffinityMask, v250);
    v244 = *(_OWORD *)SystemAffinity::GetFirstGroupSet(v250, v247);
  }
  CurrentThread = GetCurrentThread();
  GroupAffinity::GroupAffinity((GroupAffinity *)v246);
  v8 = OsNumaConfig::Instance();
  (*(void (__fastcall **)(__int64, HANDLE, __int128 *, _BYTE *))(*(_QWORD *)v8 + 48LL))(v8, CurrentThread, &v244, v246);
  v91 = v1 + 128;
  v92 = 0;
  TAutoMutex<UnfairRecursiveMutexInternal<SuspendQueueExpSLock,0>,4294967295>::GetAccess(&v91, 4195085);
  DiagEventSessionMgr::Instance();
  v9 = v92;
  if ( v92 )
  {
    v10 = v91;
    do
    {
      UnfairRecursiveMutexInternal<SuspendQueueExpSLock,0>::Release(v10);
      v11 = v9-- == 1;
      v92 = v9;
    }
    while ( !v11 );
  }
  v75 = operator new[](0x40000u, *(struct IMemObj **)(v1 + 112), "sql\\ntdbms\\msql\\utils\\diagnose.cpp", 2290, 3u);
  v12 = operator new[](0x60u, *(struct IMemObj **)(v1 + 112), "sql\\ntdbms\\msql\\xmldb\\common\\xmlwriter.cpp", 93, 3u);
  SSXmlWriterInPlace = (struct CSsXmlWriter *)CreateSSXmlWriterInPlace(v12, v13, 3, 1, 0);
  v14 = *(_DWORD *)(v1 + 120);
  v15 = DiagEventSessionMgr::Instance();
  DiagEventSessionMgr::Init(v15, v14);
  DeadlockMonitorDiagnostics::Init((DeadlockMonitorDiagnostics *)DeadlockMonitorDiagnostics::sm_instance);
  if ( (*((_BYTE *)qword_102ECFB10 + 321) & 0x10) != 0
    || (v16 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset)) != 0
    && (v17 = **(struct CSessionTraceFlags ***)(v16 + 56)) != 0
    && CSessionTraceFlags::CheckSessionTraceInternal(v17, 0xA0Cu) )
  {
    v18 = DiagEventSessionMgr::Instance();
    DiagEventSessionMgr::Stats::Reset(*((DiagEventSessionMgr::Stats **)v18 + 28));
  }
  v19 = 0;
  v20 = (__int64 *)(v1 + 56);
  do
  {
    v21 = DiagnoseComponent::Create(v19, *(unsigned int *)(v1 + 48), *(_QWORD *)(v1 + 112));
    v22 = *v20;
    if ( *v20 != v21 && v22 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 16LL))(v22, 1);
    *v20 = v21;
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v21 + 24LL))(v21, *(_QWORD *)(v1 + 112));
    ++v19;
    ++v20;
  }
  while ( v19 < 6 );
  v67 = 0;
  if ( *(_DWORD *)(v1 + 120) )
  {
    v23 = (BackupResultSet *)operator new(
                               0x90u,
                               *(struct IMemObj **)(v1 + 112),
                               "sql\\ntdbms\\msql\\utils\\diagnose.cpp",
                               2320,
                               3u);
    v90 = v23;
    if ( v23 )
      v24 = BackupResultSet::BackupResultSet(v23, 0, 6u, *(struct IMemObj **)(v1 + 112));
    else
      v24 = 0;
    v67 = v24;
    BackupResultSet::AddNewColumn(v24, L"create_time", 3, 0);
    BackupResultSet::AddNewColumn(v24, L"component_type", 10, 0);
    BackupResultSet::AddNewColumn(v24, L"component_name", 10, 0);
    BackupResultSet::AddNewColumn(v24, L"state", 7, 0);
    BackupResultSet::AddNewColumn(v24, L"state_desc", 10, 0);
    BackupResultSet::AddNewColumn(v24, L"data", 13, 0xFFFF);
  }
  if ( !*(_DWORD *)(v1 + 48) && *((char *)qword_102ECFB10 + 324) >= 0 )
  {
    v25 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                    + SystemThread_TlsOffset);
    if ( !v25
      || (v26 = **(struct CSessionTraceFlags ***)(v25 + 56)) == 0
      || !CSessionTraceFlags::CheckSessionTraceInternal(v26, 0xA27u) )
    {
      v138 = 4194400;
      v139 = 0;
      v141 = 0;
      v140 = 0;
      v142 = 0;
      SOS_Task::Sleep(5000, &v138);
    }
  }
  try
  {
LABEL_34:
    if ( !(unsigned int)DiagnoseComponentMgr::ShouldExitSession() )
    {
      v178 = &v88;
      v126 = Base_PublicGlobals::sm_invariantTscAvailable;
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&PerformanceCount);
        QuadPart = (CSbTransportMgr *)PerformanceCount.QuadPart;
      }
      else
      {
        QuadPart = MEMORY[0x7FFE0008];
      }
      v88 = QuadPart;
      v89 = QuadPart;
      v179 = &v89;
      *(_QWORD *)(v1 + 32) = QuadPart;
      v183 = &v77;
      v128 = Base_PublicGlobals::sm_invariantTscAvailable;
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v115);
        v28 = (CSbTransportMgr *)v115.QuadPart;
      }
      else
      {
        v28 = MEMORY[0x7FFE0008];
      }
      v77 = v28;
      v78 = v28;
      v184 = &v78;
      *(_QWORD *)(v1 + 40) = v28;
      if ( (HIDWORD(qword_102EDC9FC) & 0x8000000) != 0 )
      {
        v180 = v229;
        v229[0] = 0;
        v229[1] = 1;
        v230 = 0;
        v231 = &v234;
        v232 = &v238;
        v239 = 0;
        v240 = 0;
        v233 = 0;
        v241 = 0;
        v182 = &v234;
        v234 = &v242;
        v235 = 12;
        v236 = 0;
        v237 = 0;
        v242 = 0;
        v185 = *(unsigned int *)(v1 + 48);
        v129 = 3;
        v134 = 1000;
        v186 = 1000 * v185;
        v243 = 1000 * v185;
        XeSqlPkg::sp_server_diagnostics_result_set::Publish((XeSqlPkg::sp_server_diagnostics_result_set *)v228);
      }
      v148 = &v79;
      v101 = Base_PublicGlobals::sm_invariantTscAvailable;
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v116);
        v29 = (CSbTransportMgr *)v116.QuadPart;
      }
      else
      {
        v29 = MEMORY[0x7FFE0008];
      }
      v79 = v29;
      v122 = v29;
      if ( *(_DWORD *)(v1 + 120) || (HIDWORD(qword_102EDC9FC) & 0x10000000) != 0 )
      {
        utgettime((struct SQLDATEBASE *)&v117, 0, 0);
        v66 = 0;
        v30 = 0;
        v31 = v75;
        v32 = SSXmlWriterInPlace;
        v33 = v67;
        while ( 1 )
        {
LABEL_46:
          if ( (unsigned int)v30 >= 6 )
          {
            if ( *(_DWORD *)(v1 + 120) )
            {
              v159 = 0;
              v83 = 0;
              v160 = &v83;
              *(_QWORD *)(v1 + 40) = 0;
              BackupResultSet::EndResultSet(v67, 0);
              v50 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                        + SystemThread_TlsIndex)
                                                      + SystemThread_TlsOffset)
                                          + 112LL)
                              + 24LL);
              LOWORD(v62) = 0;
              LOWORD(v61) = 0;
              (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD, _DWORD, int, _QWORD, int, _QWORD, _QWORD))(*(_QWORD *)v50 + 96LL))(
                v50,
                1,
                0,
                0,
                0,
                0,
                0,
                0,
                v61,
                0,
                v62,
                0,
                0);
              v51 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                        + SystemThread_TlsIndex)
                                                      + SystemThread_TlsOffset)
                                          + 112LL)
                              + 24LL);
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v51 + 16LL))(v51, 2);
              v161 = &v84;
              v113 = Base_PublicGlobals::sm_invariantTscAvailable;
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v121);
                v52 = (CSbTransportMgr *)v121.QuadPart;
              }
              else
              {
                v52 = MEMORY[0x7FFE0008];
                v74 = (__int64)MEMORY[0x7FFE0008];
              }
              v84 = v52;
              v85 = v52;
              v162 = &v85;
              *(_QWORD *)(v1 + 40) = v52;
            }
            goto LABEL_62;
          }
          v34 = *(struct DiagnoseComponent **)(v1 + 8 * v30 + 56);
          v120 = v34;
          if ( !(*(unsigned int (__fastcall **)(struct DiagnoseComponent *))(*(_QWORD *)v34 + 48LL))(v34)
            || (*(unsigned int (__fastcall **)(struct DiagnoseComponent *))(*(_QWORD *)v34 + 56LL))(v34) )
          {
            break;
          }
          v30 = (unsigned int)++v66;
        }
        while ( 1 )
        {
          (*(void (__fastcall **)(struct DiagnoseComponent *))(*(_QWORD *)v34 + 32LL))(v34);
          v63 = *((_DWORD *)v34 + 3);
          v102 = v63;
          v70 = 0;
          if ( *(_DWORD *)(v1 + 120) )
          {
            v70 = (BackupResultSetRow *)(**(__int64 (__fastcall ***)(BackupResultSet *))v33)(v33);
            BackupResultSetRow::SetDateColumn(v70, v117);
            v47 = (const wchar_t *)(*(__int64 (__fastcall **)(struct DiagnoseComponent *))(*(_QWORD *)v34 + 8LL))(v34);
            BackupResultSetRow::SetNameColumn(v70, v47);
            v48 = (const wchar_t *)(**(__int64 (__fastcall ***)(struct DiagnoseComponent *))v34)(v34);
            BackupResultSetRow::SetNameColumn(v70, v48);
            BackupResultSetRow::SetLongColumn(v70, v63);
            BackupResultSetRow::SetNameColumn(v70, (const wchar_t *)(&DiagnoseComponent::sm_stateNames)[v63]);
          }
          v149 = v31;
          v100 = 0;
          v96 = v31;
          v97 = 0x40000;
          v98 = v31;
          v99 = 0x40000;
          v95 = &CBufferedStreamWithRaise::`vftable';
          CSsXmlWriter::Init(v32, (struct CBufferedStream *)&v95, 0, 0, 0);
          v131 = 1;
          v132 = 0;
          v133 = 0;
          v130 = &BufLockBytesReadOnlySS::`vftable';
          v135[0] = &CBlobHandleIlb::`vftable';
          v135[1] = &v130;
          v136 = 0;
          v69 = 0;
          v35 = 0;
          v36 = off_102F56BB8[2];
          v64 = v36 != 0;
          if ( !*(_DWORD *)(v1 + 120) && !v36 )
            break;
          if ( !(unsigned int)DiagnoseComponentMgr::GetDataSafe(v34, v32) )
            break;
          v37 = v96;
          v69 = v96;
          v35 = v97 - v99;
          if ( *(_DWORD *)(v1 + 120) )
          {
            v150 = v96;
            v132 = v96;
            v133 = v97 - v99;
            BackupResultSetRow::SetStringColumn(v70, (struct IBlobHandle *)v135, v35);
LABEL_92:
            v37 = v69;
          }
          if ( (HIDWORD(qword_102EDC9FC) & 0x10000000) != 0 )
          {
            v151 = v194;
            v194[0] = 0;
            v194[1] = 2;
            v195 = 0;
            v196 = &v199;
            v197 = &v207;
            v208 = 0;
            v209 = 0;
            v198 = 0;
            v210 = 0;
            v152 = &v199;
            v199 = v211;
            v200 = 10;
            v201 = 1;
            v202 = 0;
            v153 = &v203;
            v203 = 0;
            v204 = 0;
            v205 = 2;
            v206 = 0;
            v211[0] = v66;
            v211[1] = v63;
            if ( v64 )
            {
              v154 = &v203;
              v203 = v37;
              v204 = v35 & 0xFFFFFFFE;
              v205 = 2;
              v206 = 0;
            }
            XeSqlPkg::sp_server_diagnostics_component_result::Publish((XeSqlPkg::sp_server_diagnostics_component_result *)v193);
          }
          if ( *(_DWORD *)(v1 + 120) )
          {
            v155 = 0;
            v80 = 0;
            v156 = &v80;
            *(_QWORD *)(v1 + 40) = 0;
            (*(void (__fastcall **)(BackupResultSet *, BackupResultSetRow *))(*(_QWORD *)v67 + 8LL))(v67, v70);
            v157 = &v81;
            v103 = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v118);
              v49 = (CSbTransportMgr *)v118.QuadPart;
            }
            else
            {
              v49 = MEMORY[0x7FFE0008];
              v119 = MEMORY[0x7FFE0008];
            }
            v81 = v49;
            v82 = v49;
            v158 = &v82;
            *(_QWORD *)(v1 + 40) = v49;
            v31 = v75;
            v32 = SSXmlWriterInPlace;
            v33 = v67;
            v34 = v120;
          }
          CBufferedStream::~CBufferedStream((CBufferedStream *)&v95);
          if ( !(*(unsigned int (__fastcall **)(struct DiagnoseComponent *))(*(_QWORD *)v34 + 56LL))(v34) )
          {
            v30 = (unsigned int)++v66;
            goto LABEL_46;
          }
        }
        if ( *(_DWORD *)(v1 + 120) )
          BackupResultSetRow::SetNullColumn(v70, 1u);
        goto LABEL_92;
      }
LABEL_62:
      v74 = 0x800000000000008LL;
      if ( (HIDWORD(qword_102EDC9FC) & 0x8000000) != 0 )
      {
        v163 = v213;
        v213[0] = 0;
        v213[1] = 1;
        v214 = 0;
        v215 = &v218;
        v216 = &v222;
        v223 = 0;
        v224 = 0;
        v217 = 0;
        v225 = 0;
        v164 = &v218;
        v218 = &v226;
        v219 = 12;
        v220 = 0;
        v221 = 0;
        v226 = 1;
        v165 = *(unsigned int *)(v1 + 48);
        v104 = 3;
        v105 = 1000;
        v166 = 1000 * v165;
        v227 = 1000 * v165;
        XeSqlPkg::sp_server_diagnostics_result_set::Publish((XeSqlPkg::sp_server_diagnostics_result_set *)v212);
      }
      if ( *(_DWORD *)(v1 + 48) )
      {
        v167 = 0;
        v86 = 0;
        v168 = &v86;
        *(_QWORD *)(v1 + 40) = 0;
        v65 = *(_DWORD *)(v1 + 48);
        v87 = (unsigned __int64)v122;
        v38 = -1;
        if ( *(_DWORD *)(v1 + 120) )
          v38 = 1000;
        v68 = v38;
        while ( 1 )
        {
          v39 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v40 = *(_QWORD *)(v39 + 256);
          if ( !v40 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v40 = *(_QWORD *)(v39 + 256);
          }
          v169 = *(_QWORD *)(v40 + 600);
          if ( (*(_DWORD *)(v169 + 188) & 4) != 0 || (v41 = 0, (*(_BYTE *)(qword_102ECFB00 + 48) & 0x20) != 0) )
            v41 = 1;
          if ( v41 )
            goto LABEL_34;
          v170 = &v72;
          v106 = Base_PublicGlobals::sm_invariantTscAvailable;
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v123);
            v42 = (CSbTransportMgr *)v123.QuadPart;
          }
          else
          {
            v42 = MEMORY[0x7FFE0008];
          }
          v72 = v42;
          v171 = &v87;
          v172 = &v72;
          if ( (unsigned __int64)v42 < v87 )
            v43 = 0;
          else
            v43 = (unsigned __int64)v42 - v87;
          v76 = v43;
          v173 = &v76;
          if ( v43 == -1 )
          {
            v45 = -1;
            LODWORD(v44) = -1;
          }
          else
          {
            v107 = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              v174 = 1;
              v108 = 3;
              v109 = 1000;
              v175 = 1000;
              v44 = 1000 * v43 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
              LODWORD(v45) = v44;
              v73 = v44;
              goto LABEL_80;
            }
            v176 = &v76;
            v110 = -4;
            v111 = 10000;
            v45 = v43 / 0x2710;
            v127 = v43 / 0x2710;
            LODWORD(v44) = v43 / 0x2710;
          }
          v73 = v45;
LABEL_80:
          v112 = v45;
          if ( (unsigned int)v44 > v65 )
            goto LABEL_34;
          _mm_lfence();
          v46 = v65 - (unsigned int)v73;
          if ( v68 < (unsigned int)v46 )
            v46 = v68;
          v143 = 4195114;
          v144 = 1;
          v146 = 0;
          v145 = 0;
          v147 = 0;
          SOS_Task::Sleep(v46, &v143);
        }
      }
    }
  }
  catch ( SQLError v192 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)v137, (const struct SQLError *)v192);
      CurrentException = ExceptionBackout::GetCurrentException((ExceptionBackout *)v137);
      ExceptionRethrow(CurrentException);
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v137);
    }
    catch ( ShortStackException )
    {
    }
    v1 = v124;
  }
  v53 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v54 = *(struct Worker **)(v53 + 256);
  if ( !v54 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v54 = *(struct Worker **)(v53 + 256);
  }
  if ( *((_DWORD *)v54 + 139) )
    ExceptionPostCatchActions(v54);
  v125 = 0;
  *(_QWORD *)(v1 + 32) = 0;
  v90 = 0;
  *(_QWORD *)(v1 + 40) = 0;
  if ( v67 )
  {
    BackupResultSet::~BackupResultSet(v67);
    operator delete(v67, 0x90u);
  }
  v93 = &off_102F56D28;
  v94 = 0;
  TAutoMutex<UnfairRecursiveMutexInternal<SuspendQueueExpSLock,0>,4294967295>::GetAccess(&v93, 4195085);
  LODWORD(qword_102F56DA0) = qword_102F56DA0 - 1;
  v55 = v94;
  if ( v94 )
  {
    v56 = v93;
    do
    {
      UnfairRecursiveMutexInternal<SuspendQueueExpSLock,0>::Release(v56);
      v11 = v55-- == 1;
      v94 = v55;
    }
    while ( !v11 );
  }
  v57 = DiagEventSessionMgr::Instance();
  (**(void (__fastcall ***)(struct DiagEventSessionMgr *))v57)(v57);
  if ( SSXmlWriterInPlace )
    (**(void (__fastcall ***)(struct CSsXmlWriter *, __int64))SSXmlWriterInPlace)(SSXmlWriterInPlace, 1);
  operator delete[](v75);
  v58 = OsNumaConfig::Instance();
  (*(void (__fastcall **)(__int64, HANDLE, _BYTE *, _QWORD))(*(_QWORD *)v58 + 48LL))(v58, CurrentThread, v246, 0);
  v127 = (unsigned __int64)v189;
  if ( v189[0] )
  {
    if ( v189[1] )
      *(_DWORD *)(v190 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v190 + 608) + 16LL))(
        *(_QWORD *)(v190 + 608),
        v190,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)v191);
  result = (unsigned int)~v187;
  *(_DWORD *)(v188 + 616) &= result;
  return result;
}

```

## disassembly

```asm
0x100777320  mov     r11, rsp
0x100777323  push    rdi
0x100777324  push    r12
0x100777326  push    r13
0x100777328  push    r14
0x10077732a  push    r15
0x10077732c  sub     rsp, 0E00h
0x100777333  mov     qword ptr [r11-0A28h], 0FFFFFFFFFFFFFFFEh
0x10077733e  mov     [r11+10h], rbx
0x100777342  mov     [r11+18h], rsi
0x100777346  mov     rax, cs:__security_cookie
0x10077734d  xor     rax, rsp
0x100777350  mov     [rsp+0E28h+var_30], rax
0x100777358  mov     r13, rcx
0x10077735b  mov     [r11-0BD8h], rcx
0x100777362  xor     r14d, r14d
0x100777365  mov     ebx, r14d
0x100777368  cmp     [rcx+78h], r14d
0x10077736c  jz      loc_10174F573
0x100777372  mov     r8, gs:58h
0x10077737b  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100777382  mov     edx, [rax]
0x100777384  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10077738b  mov     eax, [rax]
0x10077738d  add     rax, [r8+rdx*8]
0x100777391  mov     rax, [rax]
0x100777394  mov     rcx, [rax+80h]
0x10077739b  mov     ebx, [rcx+4Ch]
0x10077739e  shr     ebx, 9
0x1007773a1  and     ebx, 1
0x1007773a4  jz      loc_10174F573
0x1007773aa  cmp     [r13+30h], r14d
0x1007773ae  jbe     loc_10174F573
0x1007773b4  mov     r12d, 1
0x1007773ba  mov     r9d, r12d
0x1007773bd  lea     edx, [r14+49h]
0x1007773c1  lea     ecx, [rdx+61h]
0x1007773c4  lea     r8d, [r14+10h]
0x1007773c8  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x1007773ce  jmp     short loc_1007773D1
0x1007773d1  xor     ebx, 1
0x1007773d4  mov     r8d, ebx
0x1007773d7  mov     edx, 20000329h
0x1007773dc  lea     rcx, [rsp+0E28h+var_9C8]
0x1007773e4  call    ??0AutoSwitchPreemptive@SOS_Task@@QEAA@W4PWAIT_enum@@H@Z; SOS_Task::AutoSwitchPreemptive::AutoSwitchPreemptive(PWAIT_enum,int)
0x1007773e9  nop
0x1007773ea  mov     rdx, gs:58h
0x1007773f3  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1007773fa  mov     ecx, [rax]
0x1007773fc  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100777403  mov     ebx, [rax]
0x100777405  add     rbx, [rdx+rcx*8]
0x100777409  mov     rax, [rbx+100h]
0x100777410  test    rax, rax
0x100777413  jnz     short loc_100777424
0x100777415  xor     ecx, ecx
0x100777417  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10077741d  mov     rax, [rbx+100h]
0x100777424  mov     rcx, [rax+3E0h]
0x10077742b  test    byte ptr [rcx+620h], 4
0x100777432  movzx   ebx, r14w
0x100777436  jnz     short loc_10077743F
0x100777438  movzx   ebx, word ptr [rcx+0A0h]
0x10077743f  lea     rdx, [rsp+0E28h+var_1B8]
0x100777447  mov     rcx, cs:__imp_?sm_AffinityMask@SOS_PublicGlobals@@2VSystemAffinity@@A; SystemAffinity SOS_PublicGlobals::sm_AffinityMask
0x10077744e  call    cs:__imp_?SafeCopy@SystemAffinity@@QEBA?AV1@XZ; SystemAffinity::SafeCopy(void)
0x100777454  movzx   r8d, bx
0x100777458  lea     rdx, [rsp+0E28h+var_A08]
0x100777460  lea     rcx, [rsp+0E28h+var_1B8]
0x100777468  call    cs:__imp_?GetNodeAffinity@SystemAffinity@@QEBA?AVNodeAffinity@@G@Z; SystemAffinity::GetNodeAffinity(ushort)
0x10077746e  lea     rdx, [rsp+0E28h+var_138]
0x100777476  mov     rcx, cs:__imp_?sm_AffinityMask@SOS_PublicGlobals@@2VSystemAffinity@@A; SystemAffinity SOS_PublicGlobals::sm_AffinityMask
0x10077747d  call    cs:__imp_?SafeCopy@SystemAffinity@@QEBA?AV1@XZ; SystemAffinity::SafeCopy(void)
0x100777483  lea     rcx, [rsp+0E28h+var_A08]
0x10077748b  call    cs:__imp_?GetGroup@NodeAffinity@@QEBAGXZ; NodeAffinity::GetGroup(void)
0x100777491  movzx   r8d, ax
0x100777495  lea     rdx, [rsp+0E28h+var_1F8]
0x10077749d  lea     rcx, [rsp+0E28h+var_138]
0x1007774a5  call    cs:__imp_?GetGroupAffinity@SystemAffinity@@QEBA?BVGroupAffinity@@G@Z; SystemAffinity::GetGroupAffinity(ushort)
0x1007774ab  lea     rcx, [rsp+0E28h+var_1F8]
0x1007774b3  call    cs:__imp_?GetCPUCount@GroupAffinity@@QEBAIXZ; GroupAffinity::GetCPUCount(void)
0x1007774b9  test    eax, eax
0x1007774bb  jnz     short loc_1007774F3
0x1007774bd  lea     rdx, [rsp+0E28h+var_B8]
0x1007774c5  mov     rcx, cs:__imp_?sm_AffinityMask@SOS_PublicGlobals@@2VSystemAffinity@@A; SystemAffinity SOS_PublicGlobals::sm_AffinityMask
0x1007774cc  call    cs:__imp_?SafeCopy@SystemAffinity@@QEBA?AV1@XZ; SystemAffinity::SafeCopy(void)
0x1007774d2  lea     rdx, [rsp+0E28h+var_1D0]
0x1007774da  lea     rcx, [rsp+0E28h+var_B8]
0x1007774e2  call    cs:__imp_?GetFirstGroupSet@SystemAffinity@@QEBA?BVGroupAffinity@@XZ; SystemAffinity::GetFirstGroupSet(void)
0x1007774e8  movups  xmm0, xmmword ptr [rax]
0x1007774eb  movups  [rsp+0E28h+var_1F8], xmm0
0x1007774f3  call    cs:__imp_GetCurrentThread
0x1007774f9  mov     [rsp+0E28h+var_1E8], rax
0x100777501  lea     rcx, [rsp+0E28h+var_1E0]
0x100777509  call    cs:__imp_??0GroupAffinity@@QEAA@XZ; GroupAffinity::GroupAffinity(void)
0x10077750f  call    cs:__imp_?Instance@OsNumaConfig@@SAPEAV1@XZ; OsNumaConfig::Instance(void)
0x100777515  mov     r10, [rax]
0x100777518  lea     r9, [rsp+0E28h+var_1E0]
0x100777520  lea     r8, [rsp+0E28h+var_1F8]
0x100777528  mov     rdx, [rsp+0E28h+var_1E8]
0x100777530  mov     rcx, rax
0x100777533  call    qword ptr [r10+30h]
0x100777537  nop
0x100777538  lea     rax, [r13+80h]
0x10077753f  mov     [rsp+0E28h+var_CA8], rax
0x100777547  mov     [rsp+0E28h+var_CA0], r14d
0x10077754f  mov     edx, 40030Dh
0x100777554  lea     rcx, [rsp+0E28h+var_CA8]
0x10077755c  call    ?GetAccess@?$TAutoMutex@V?$UnfairRecursiveMutexInternal@USuspendQueueExpSLock@@$0A@@@$0PPPPPPPP@@@QEAAXI@Z; TAutoMutex<UnfairRecursiveMutexInternal<SuspendQueueExpSLock,0>,4294967295>::GetAccess(uint)
0x100777561  call    ?Instance@DiagEventSessionMgr@@SAPEAV1@XZ; DiagEventSessionMgr::Instance(void)
0x100777566  nop
0x100777567  nop     word ptr [rax+rax+00000000h]
0x100777570  mov     ebx, [rsp+0E28h+var_CA0]
0x100777577  test    ebx, ebx
0x100777579  jz      short loc_100777597
0x10077757b  mov     rdi, [rsp+0E28h+var_CA8]
0x100777583  mov     rcx, rdi
0x100777586  call    ?Release@?$UnfairRecursiveMutexInternal@USuspendQueueExpSLock@@$0A@@@QEAAXXZ; UnfairRecursiveMutexInternal<SuspendQueueExpSLock,0>::Release(void)
0x10077758b  add     ebx, 0FFFFFFFFh
0x10077758e  mov     [rsp+0E28h+var_CA0], ebx
0x100777595  jnz     short loc_100777583
0x100777597  mov     byte ptr [rsp+0E28h+var_E08], 3
0x10077759c  mov     r9d, 8F2h
0x1007775a2  lea     r8, aSqlNtdbmsMsqlU_33; "sql\\ntdbms\\msql\\utils\\diagnose.cpp"
0x1007775a9  mov     rdx, [r13+70h]
0x1007775ad  mov     ecx, 40000h
0x1007775b2  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1007775b8  mov     [rsp+0E28h+var_D28], rax
0x1007775c0  mov     byte ptr [rsp+0E28h+var_E08], 3
0x1007775c5  mov     r9d, 5Dh ; ']'
0x1007775cb  lea     r8, aSqlNtdbmsMsqlX_41; "sql\\ntdbms\\msql\\xmldb\\common\\xmlwr"...
0x1007775d2  mov     rdx, [r13+70h]
0x1007775d6  lea     ecx, [r9+3]
0x1007775da  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1007775e0  mov     dword ptr [rsp+0E28h+var_E08], r14d
0x1007775e5  mov     r9d, r12d
0x1007775e8  mov     r8d, 3
0x1007775ee  mov     rcx, rax
0x1007775f1  call    ?CreateSSXmlWriterInPlace@@YAPEAVCSsXmlWriter@@PEAXHW4XmlWriterType@@W4XmlBldrType@@K@Z; CreateSSXmlWriterInPlace(void *,int,XmlWriterType,XmlBldrType,ulong)
0x1007775f6  mov     [rsp+0E28h+var_D68], rax
0x1007775fe  mov     ebx, [r13+78h]
0x100777602  call    ?Instance@DiagEventSessionMgr@@SAPEAV1@XZ; DiagEventSessionMgr::Instance(void)
0x100777607  mov     rcx, rax; this
0x10077760a  mov     edx, ebx; int
0x10077760c  call    ?Init@DiagEventSessionMgr@@QEAAXH@Z; DiagEventSessionMgr::Init(int)
0x100777611  nop
0x100777612  lea     rcx, ?sm_instance@DeadlockMonitorDiagnostics@@0V1@A; this
0x100777619  call    ?Init@DeadlockMonitorDiagnostics@@QEAAXXZ; DeadlockMonitorDiagnostics::Init(void)
0x10077761e  nop
0x10077761f  mov     rax, cs:qword_102ECFB10
0x100777626  test    byte ptr [rax+141h], 10h
0x10077762d  jnz     short loc_100777671
0x10077762f  mov     r8, gs:58h
0x100777638  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10077763f  mov     ecx, [rax]
0x100777641  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100777648  mov     edx, [rax]
0x10077764a  add     rdx, [r8+rcx*8]
0x10077764e  mov     rax, [rdx]
0x100777651  test    rax, rax
0x100777654  jz      short loc_100777682
0x100777656  mov     rax, [rax+38h]
0x10077765a  mov     rcx, [rax]
0x10077765d  test    rcx, rcx
0x100777660  jz      short loc_100777682
0x100777662  mov     edx, 0A0Ch
0x100777667  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x10077766d  test    eax, eax
0x10077766f  jz      short loc_100777682
0x100777671  call    ?Instance@DiagEventSessionMgr@@SAPEAV1@XZ; DiagEventSessionMgr::Instance(void)
0x100777676  mov     rcx, [rax+0E0h]; this
0x10077767d  call    ?Reset@Stats@DiagEventSessionMgr@@QEAAXXZ; DiagEventSessionMgr::Stats::Reset(void)
0x100777682  mov     edi, r14d
0x100777685  lea     rsi, [r13+38h]
0x100777689  nop     dword ptr [rax+00000000h]
0x100777690  mov     r8, [r13+70h]
0x100777694  mov     edx, [r13+30h]
0x100777698  mov     ecx, edi
0x10077769a  call    ?Create@DiagnoseComponent@@SAPEAV1@W4ComponentId@1@IPEAVIMemObj@@@Z; DiagnoseComponent::Create(DiagnoseComponent::ComponentId,uint,IMemObj *)
0x10077769f  mov     rbx, rax
0x1007776a2  mov     rcx, [rsi]
0x1007776a5  cmp     rcx, rax
0x1007776a8  jz      short loc_1007776B9
0x1007776aa  test    rcx, rcx
0x1007776ad  jz      short loc_1007776B9
0x1007776af  mov     r8, [rcx]
0x1007776b2  mov     edx, r12d
0x1007776b5  call    qword ptr [r8+10h]
0x1007776b9  mov     [rsi], rbx
0x1007776bc  mov     rax, [rbx]
0x1007776bf  mov     rdx, [r13+70h]
0x1007776c3  mov     rcx, rbx
0x1007776c6  call    qword ptr [rax+18h]
0x1007776c9  inc     edi
0x1007776cb  add     rsi, 8
0x1007776cf  cmp     edi, 6
0x1007776d2  jb      short loc_100777690
0x1007776d4  mov     [rsp+0E28h+var_DA0], r14
0x1007776dc  cmp     dword ptr [r13+78h], 0
0x1007776e1  jz      loc_1007777D4
0x1007776e7  mov     [rsp+0E28h+var_D98], 910h
0x1007776f2  mov     byte ptr [rsp+0E28h+var_E08], 3
0x1007776f7  mov     r9d, 910h
0x1007776fd  lea     r8, aSqlNtdbmsMsqlU_33; "sql\\ntdbms\\msql\\utils\\diagnose.cpp"
0x100777704  mov     rdx, [r13+70h]
0x100777708  mov     ecx, 90h
0x10077770d  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x100777713  mov     [rsp+0E28h+var_CB0], rax
0x10077771b  test    rax, rax
0x10077771e  jz      loc_10174F57F
0x100777724  mov     r9, [r13+70h]
0x100777728  xor     edx, edx
0x10077772a  lea     r8d, [rdx+6]
0x10077772e  mov     rcx, rax
0x100777731  call    cs:__imp_??0BackupResultSet@@QEAA@PEAVBackupOperation@@KPEAVIMemObj@@@Z; BackupResultSet::BackupResultSet(BackupOperation *,ulong,IMemObj *)
0x100777737  mov     rbx, rax
0x10077773a  jmp     short loc_10077773D
0x10077773d  mov     [rsp+0E28h+var_DA0], rbx
0x100777745  xor     r9d, r9d
0x100777748  lea     r8d, [r9+3]
0x10077774c  lea     rdx, aCreateTime; "create_time"
0x100777753  mov     rcx, rbx
0x100777756  call    cs:__imp_?AddNewColumn@BackupResultSet@@IEAAXPEB_WW4ColumnType@BackupColumn@@I@Z; BackupResultSet::AddNewColumn(wchar_t const *,BackupColumn::ColumnType,uint)
0x10077775c  xor     r9d, r9d
0x10077775f  lea     r8d, [r9+0Ah]
0x100777763  lea     rdx, aComponentType; "component_type"
0x10077776a  mov     rcx, rbx
0x10077776d  call    cs:__imp_?AddNewColumn@BackupResultSet@@IEAAXPEB_WW4ColumnType@BackupColumn@@I@Z; BackupResultSet::AddNewColumn(wchar_t const *,BackupColumn::ColumnType,uint)
0x100777773  xor     r9d, r9d
0x100777776  lea     r8d, [r9+0Ah]
0x10077777a  lea     rdx, aComponentName; "component_name"
0x100777781  mov     rcx, rbx
0x100777784  call    cs:__imp_?AddNewColumn@BackupResultSet@@IEAAXPEB_WW4ColumnType@BackupColumn@@I@Z; BackupResultSet::AddNewColumn(wchar_t const *,BackupColumn::ColumnType,uint)
0x10077778a  xor     r9d, r9d
0x10077778d  lea     r8d, [r9+7]
0x100777791  lea     rdx, aState_6; "state"
0x100777798  mov     rcx, rbx
0x10077779b  call    cs:__imp_?AddNewColumn@BackupResultSet@@IEAAXPEB_WW4ColumnType@BackupColumn@@I@Z; BackupResultSet::AddNewColumn(wchar_t const *,BackupColumn::ColumnType,uint)
0x1007777a1  xor     r9d, r9d
0x1007777a4  lea     r8d, [r9+0Ah]
0x1007777a8  lea     rdx, aStateDesc; "state_desc"
0x1007777af  mov     rcx, rbx
0x1007777b2  call    cs:__imp_?AddNewColumn@BackupResultSet@@IEAAXPEB_WW4ColumnType@BackupColumn@@I@Z; BackupResultSet::AddNewColumn(wchar_t const *,BackupColumn::ColumnType,uint)
0x1007777b8  mov     r9d, 0FFFFh
0x1007777be  mov     r8d, 0Dh
0x1007777c4  lea     rdx, aData_1; "data"
0x1007777cb  mov     rcx, rbx
0x1007777ce  call    cs:__imp_?AddNewColumn@BackupResultSet@@IEAAXPEB_WW4ColumnType@BackupColumn@@I@Z; BackupResultSet::AddNewColumn(wchar_t const *,BackupColumn::ColumnType,uint)
0x1007777d4  cmp     dword ptr [r13+30h], 0
0x1007777d9  jnz     loc_100777873
0x1007777df  mov     rax, cs:qword_102ECFB10
0x1007777e6  cmp     byte ptr [rax+144h], 0
0x1007777ed  jl      loc_100777873
0x1007777f3  mov     r8, gs:58h
0x1007777fc  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100777803  mov     ecx, [rax]
0x100777805  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10077780c  mov     edx, [rax]
0x10077780e  add     rdx, [r8+rcx*8]
0x100777812  mov     rax, [rdx]
0x100777815  test    rax, rax
0x100777818  jz      short loc_100777835
0x10077781a  mov     rax, [rax+38h]
0x10077781e  mov     rcx, [rax]
0x100777821  test    rcx, rcx
0x100777824  jz      short loc_100777835
0x100777826  mov     edx, 0A27h
0x10077782b  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100777831  test    eax, eax
0x100777833  jnz     short loc_100777873
0x100777835  mov     [rsp+0E28h+var_B60], 400060h
0x100777840  mov     [rsp+0E28h+var_B58], r14
0x100777848  mov     [rsp+0E28h+var_B48], r14
0x100777850  mov     [rsp+0E28h+var_B50], r14
0x100777858  mov     [rsp+0E28h+var_B40], r14
0x100777860  lea     rdx, [rsp+0E28h+var_B60]
0x100777868  mov     ecx, 1388h
0x10077786d  call    ?Sleep@SOS_Task@@SA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@@Z; SOS_Task::Sleep(ulong,SOS_WaitInfo const *)
0x100777872  nop
0x100777873  mov     edi, 3E8h
0x100777878  mov     rsi, 346DC5D63886594Bh
0x100777882  call    ?ShouldExitSession@DiagnoseComponentMgr@@SAHXZ; DiagnoseComponentMgr::ShouldExitSession(void)
0x100777887  test    eax, eax
0x100777889  jnz     loc_10174FB89
0x10077788f  lea     rax, [rsp+0E28h+var_CC0]
0x100777897  mov     [rsp+0E28h+var_A20], rax
0x10077789f  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x1007778a6  mov     ecx, [rax]
0x1007778a8  mov     [rsp+0E28h+var_BC8], ecx
0x1007778af  test    ecx, ecx
0x1007778b1  jz      loc_10174F588
0x1007778b7  lea     rcx, [rsp+0E28h+PerformanceCount]; lpPerformanceCount
0x1007778bf  call    cs:__imp_QueryPerformanceCounter
0x1007778c5  mov     rax, qword ptr [rsp+0E28h+PerformanceCount]
0x1007778cd  jmp     short loc_1007778D0
0x1007778d0  mov     [rsp+0E28h+var_CC0], rax
0x1007778d8  mov     [rsp+0E28h+var_CB8], rax
0x1007778e0  lea     rax, [rsp+0E28h+var_CB8]
0x1007778e8  mov     [rsp+0E28h+var_A18], rax
0x1007778f0  mov     rax, [rsp+0E28h+var_CB8]
  ... truncated ...
```
