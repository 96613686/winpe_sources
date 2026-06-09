# SpExecuteExternalScript(CCompExecCtxtBasic const &,CParamExchange *,int,CXVariant *)

- ea: `0x101221770`
- end: `0x101223843`
- name: `?SpExecuteExternalScript@@YAXAEBVCCompExecCtxtBasic@@PEAVCParamExchange@@HPEAVCXVariant@@@Z`
- size: `8403`
- prototype: `void __fastcall(const struct CCompExecCtxtBasic *, struct CParamExchange *, int, struct CXVariant *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1012485a0`

## callees

- `0x100401070`
- `0x100407620`
- `0x100407bd0`
- `0x10040cd80`
- `0x10043f5c0`
- `0x100440350`
- `0x1004530f0`
- `0x100454360`
- `0x100537840`
- `0x1005511a0`
- `0x1009cf2c0`
- `0x10117fcd0`
- `0x101221110`
- `0x101221770`
- `0x1012784b0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x101221859`
- `KERNEL32!QueryPerformanceCounter` at `0x10122372d`
- `KERNEL32!QueryPerformanceCounter` at `0x101221859`
- `KERNEL32!QueryPerformanceCounter` at `0x10122372d`
- `sqldk!?g_metadataFactory@@3UMetadataFactory@@A` at `0x101221bc8`
- `sqldk!?g_pAutoXactFactory@@3PEAVIAutoXactFactory@@EA` at `0x101221b7b`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10122301b`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x101223043`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10122319b`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10122362b`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10122379b`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1012223e3`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x101221941`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x10122376c`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101221846`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101223719`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101223760`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x101221948`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x101221948`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1012231f4`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101223389`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1012231f4`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101223389`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1012236f8`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1012236f8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1012218fe`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101221caf`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101221d16`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101221e7f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101221ee2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101221f21`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101221f97`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101221fd9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101222031`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101222062`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1012220f2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101222148`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1012221e2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1012222ad`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101222384`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1012223ca`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101222415`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1012224d6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10122259f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1012226ad`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101222764`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101222843`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10122287d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1012228b5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1012228fb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101222983`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1012229c9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101223343`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1012234ea`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10122352c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1012218fe`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101221caf`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101221d16`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101221e7f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101221ee2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101221f21`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101221f97`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101221fd9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101222031`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101222062`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1012220f2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101222148`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1012221e2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1012222ad`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101222384`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1012223ca`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101222415`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1012224d6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10122259f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1012226ad`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101222764`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101222843`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10122287d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1012228b5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1012228fb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101222983`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1012229c9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101223343`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1012234ea`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10122352c`
- `sqldk!SystemThread_TlsIndex` at `0x1012218a2`
- `sqldk!SystemThread_TlsIndex` at `0x101221b14`
- `sqldk!SystemThread_TlsIndex` at `0x101222afa`
- `sqldk!SystemThread_TlsIndex` at `0x1012236c0`
- `sqldk!SystemThread_TlsOffset` at `0x1012218ab`
- `sqldk!SystemThread_TlsOffset` at `0x101221b1d`
- `sqldk!SystemThread_TlsOffset` at `0x101222b03`
- `sqldk!SystemThread_TlsOffset` at `0x1012236c9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101221b38`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1012236e2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101221b38`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1012236e2`
- `sqlTsEs!?GetDefaultCollation@CDbAndSetOptsImplImport@@YAQEBVCDefaultCollation@@G@Z` at `0x101222b1b`
- `sqlTsEs!?GetDefaultCollation@CDbAndSetOptsImplImport@@YAQEBVCDefaultCollation@@G@Z` at `0x101222b1b`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x1012219c5`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x101221a6c`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x101221aae`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x101222096`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x10122217c`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x10122221e`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x1012222e9`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x101222449`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x101222512`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x1012225db`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x10122267b`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x1012226e1`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x1012227c0`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x1012219c5`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x101221a6c`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x101221aae`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x101222096`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x10122217c`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x10122221e`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x1012222e9`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x101222449`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x101222512`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x1012225db`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x10122267b`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x1012226e1`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x1012227c0`
- `sqlTsEs!?CbSize@CXVariant@@QEBAKPEBVCTypeInfo@@@Z` at `0x101222ec7`
- `sqlTsEs!?CbSize@CXVariant@@QEBAKPEBVCTypeInfo@@@Z` at `0x101222ec7`
- `sqlTsEs!??1CAutoClearXVariant@@UEAA@XZ` at `0x1012229cf`
- `sqlTsEs!??1CAutoClearXVariant@@UEAA@XZ` at `0x1012237d3`
- `sqlmin!?IncrementCounterValue@PerfmonManager@@QEAAHKK_JPEA_K@Z` at `0x10122303d`
- `sqlmin!?IncrementCounterValue@PerfmonManager@@QEAAHKK_JPEA_K@Z` at `0x101223081`
- `sqlmin!?IncrementCounterValue@PerfmonManager@@QEAAHKK_JPEA_K@Z` at `0x1012231c9`
- `sqlmin!?IncrementCounterValue@PerfmonManager@@QEAAHKK_JPEA_K@Z` at `0x101223659`
- `sqlmin!?IncrementCounterValue@PerfmonManager@@QEAAHKK_JPEA_K@Z` at `0x1012237bf`
- `sqlmin!?IncrementCounterValue@PerfmonManager@@QEAAHKK_JPEA_K@Z` at `0x10122303d`
- `sqlmin!?IncrementCounterValue@PerfmonManager@@QEAAHKK_JPEA_K@Z` at `0x101223081`
- `sqlmin!?IncrementCounterValue@PerfmonManager@@QEAAHKK_JPEA_K@Z` at `0x1012231c9`
- `sqlmin!?IncrementCounterValue@PerfmonManager@@QEAAHKK_JPEA_K@Z` at `0x101223659`
- `sqlmin!?IncrementCounterValue@PerfmonManager@@QEAAHKK_JPEA_K@Z` at `0x1012237bf`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall SpExecuteExternalScript(
        const struct CCompExecCtxtBasic *a1,
        struct CParamExchange *a2,
        int a3,
        struct CXVariant *a4)
{
  struct CXVariant *v4; // rbx
  CParamExchange *v6; // r12
  CParamExchange **v7; // rsi
  CSbTransportMgr *QuadPart; // rax
  int v9; // ecx
  CParamExchange **v10; // rsi
  CParamExchange *v11; // rcx
  __int64 v12; // rdx
  CParamExchange *v13; // rax
  unsigned __int64 v14; // r12
  const wchar_t *v15; // r15
  unsigned int v16; // esi
  __int64 v18; // rbx
  __int64 v19; // rax
  __int64 v20; // r14
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rbx
  __int64 v24; // rbx
  __int64 v25; // rbx
  unsigned int v26; // eax
  __int64 v27; // rax
  __int64 v28; // rbx
  char v29; // bl
  const wchar_t *v30; // rcx
  __int64 v31; // rax
  CParamExchange *v32; // rcx
  __int64 v33; // rdx
  char v34; // r8
  __int64 v35; // rcx
  CParamExchange *v36; // rcx
  __int64 v37; // rdx
  CParamExchange *v38; // rcx
  __int64 v39; // rdx
  char v40; // cl
  char v41; // al
  int v42; // eax
  CParamExchange *v43; // rax
  CParamExchange *v44; // rax
  int v45; // eax
  _QWORD *ThreadLocalStoragePointer; // rdx
  int v47; // ebx
  bool v48; // al
  int v49; // ecx
  bool v50; // al
  int v51; // ecx
  CParamExchange *v52; // rax
  CParamExchange *v53; // rax
  bool v54; // al
  int v55; // ecx
  CParamExchange **v56; // r14
  CParamExchange *v57; // rax
  __int128 v58; // xmm2
  __int128 v59; // xmm3
  CParamExchange *v60; // rax
  unsigned int v61; // ebx
  unsigned int v62; // esi
  CParamExchange *v63; // rax
  __int128 v64; // xmm2
  __int128 v65; // xmm3
  signed int v66; // r8d
  __int64 v67; // r9
  int v68; // edx
  _BYTE *v69; // rcx
  struct CParamExchange *v70; // r13
  struct CCompExecCtxtBasic *v71; // r15
  __int64 *v72; // rcx
  __int64 v73; // r12
  __int64 v74; // rdx
  __int64 v75; // rcx
  CParamExchange **v76; // rsi
  struct IMemObj *v77; // r14
  void *v78; // rbx
  unsigned int v79; // r15d
  _WORD *v80; // rsi
  LARGE_INTEGER v81; // r14
  int v82; // r9d
  DWORD LowPart; // r8d
  CParamExchange *v84; // rsi
  signed int v85; // r12d
  __int64 v86; // rbx
  struct Worker *v87; // rcx
  CSbTransportMgr *v88; // rcx
  unsigned __int64 v89; // rcx
  CParamExchange *v90; // rcx
  CSbTransportMgr *v91; // rcx
  CParamExchange **v92; // rcx
  unsigned __int64 v93; // rdx
  _BYTE *v94; // rax
  const struct SQLError *CurrentException; // rax
  struct ICallerParse *v96; // [rsp+20h] [rbp-CB8h]
  struct ICallerParse *v97; // [rsp+20h] [rbp-CB8h]
  struct ICallerParse *v98; // [rsp+20h] [rbp-CB8h]
  struct ICallerParse *v99; // [rsp+20h] [rbp-CB8h]
  struct ICallerParse *v100; // [rsp+20h] [rbp-CB8h]
  bool v101[8]; // [rsp+30h] [rbp-CA8h]
  unsigned int v102[2]; // [rsp+38h] [rbp-CA0h]
  int v103[2]; // [rsp+40h] [rbp-C98h]
  unsigned int v104[2]; // [rsp+48h] [rbp-C90h]
  bool v105[8]; // [rsp+50h] [rbp-C88h]
  bool v106[8]; // [rsp+58h] [rbp-C80h]
  __int64 v107; // [rsp+60h] [rbp-C78h]
  __int64 v108; // [rsp+68h] [rbp-C70h]
  __int64 v109; // [rsp+70h] [rbp-C68h]
  __int64 v110; // [rsp+78h] [rbp-C60h]
  __int64 v111; // [rsp+80h] [rbp-C58h]
  __int64 v112; // [rsp+88h] [rbp-C50h]
  __int64 v113; // [rsp+90h] [rbp-C48h]
  __int64 v114; // [rsp+98h] [rbp-C40h]
  __int64 v115; // [rsp+A0h] [rbp-C38h]
  __int64 v116; // [rsp+A8h] [rbp-C30h]
  __int64 v117; // [rsp+B0h] [rbp-C28h]
  __int64 v118; // [rsp+B8h] [rbp-C20h]
  __int64 v119; // [rsp+C0h] [rbp-C18h]
  char v120; // [rsp+C8h] [rbp-C10h]
  __int16 v121; // [rsp+D0h] [rbp-C08h]
  char v122; // [rsp+D8h] [rbp-C00h]
  int v123; // [rsp+E0h] [rbp-BF8h]
  signed int v124; // [rsp+E4h] [rbp-BF4h]
  struct CCompExecCtxtBasic *v126; // [rsp+F0h] [rbp-BE8h] BYREF
  int v127; // [rsp+F8h] [rbp-BE0h]
  int v128; // [rsp+FCh] [rbp-BDCh]
  LARGE_INTEGER v129; // [rsp+100h] [rbp-BD8h] BYREF
  CParamExchange *v130; // [rsp+108h] [rbp-BD0h] BYREF
  unsigned int v131; // [rsp+110h] [rbp-BC8h]
  __int64 v132; // [rsp+118h] [rbp-BC0h]
  LARGE_INTEGER PerformanceCount; // [rsp+120h] [rbp-BB8h] BYREF
  __int64 v134; // [rsp+128h] [rbp-BB0h]
  CParamExchange **v135; // [rsp+130h] [rbp-BA8h]
  unsigned int v136; // [rsp+138h] [rbp-BA0h]
  signed int v137; // [rsp+140h] [rbp-B98h]
  CParamExchange **v138; // [rsp+148h] [rbp-B90h]
  CParamExchange **v139; // [rsp+150h] [rbp-B88h]
  CParamExchange **v140; // [rsp+158h] [rbp-B80h]
  union _LARGE_INTEGER v141; // [rsp+160h] [rbp-B78h]
  struct CCompExecCtxtBasic **v142; // [rsp+168h] [rbp-B70h]
  CParamExchange **v143; // [rsp+170h] [rbp-B68h]
  CSbTransportMgr *v144; // [rsp+178h] [rbp-B60h] BYREF
  CParamExchange **v145; // [rsp+180h] [rbp-B58h]
  void (__fastcall ***v146)(_QWORD, __int64); // [rsp+188h] [rbp-B50h]
  void (__fastcall ***v147)(_QWORD, __int64); // [rsp+190h] [rbp-B48h]
  struct CParamExchange *v148; // [rsp+198h] [rbp-B40h]
  __int128 v149; // [rsp+1A0h] [rbp-B38h] BYREF
  __int128 v150; // [rsp+1B0h] [rbp-B28h]
  struct IMemObj *v151; // [rsp+1C0h] [rbp-B18h] BYREF
  struct IMemObj *v152; // [rsp+1C8h] [rbp-B10h] BYREF
  struct IMemObj *v153; // [rsp+1D0h] [rbp-B08h] BYREF
  struct IMemObj *v154; // [rsp+1D8h] [rbp-B00h] BYREF
  struct IMemObj *v155; // [rsp+1E0h] [rbp-AF8h] BYREF
  struct IMemObj *v156; // [rsp+1E8h] [rbp-AF0h] BYREF
  void *v157; // [rsp+1F0h] [rbp-AE8h]
  __int64 v158; // [rsp+1F8h] [rbp-AE0h]
  __int128 v159; // [rsp+200h] [rbp-AD8h] BYREF
  __int128 v160; // [rsp+210h] [rbp-AC8h]
  __int128 v161; // [rsp+220h] [rbp-AB8h] BYREF
  __int128 v162; // [rsp+230h] [rbp-AA8h]
  int v163; // [rsp+240h] [rbp-A98h]
  int v164; // [rsp+244h] [rbp-A94h]
  struct IMemObj *v165; // [rsp+248h] [rbp-A90h] BYREF
  struct IMemObj *v166; // [rsp+250h] [rbp-A88h] BYREF
  const struct CCompExecCtxtBasic *v167; // [rsp+258h] [rbp-A80h]
  struct CXVariant *v168; // [rsp+260h] [rbp-A78h]
  LARGE_INTEGER v169; // [rsp+268h] [rbp-A70h] BYREF
  __int64 v170; // [rsp+270h] [rbp-A68h]
  const wchar_t *v171; // [rsp+278h] [rbp-A60h] BYREF
  int v172; // [rsp+280h] [rbp-A58h]
  _QWORD v173[25]; // [rsp+288h] [rbp-A50h] BYREF
  _BYTE v174[32]; // [rsp+350h] [rbp-988h] BYREF
  _BYTE v175[16]; // [rsp+370h] [rbp-968h] BYREF
  __int64 v176; // [rsp+380h] [rbp-958h]
  unsigned int v177; // [rsp+388h] [rbp-950h]
  int v178; // [rsp+528h] [rbp-7B0h]
  char v179; // [rsp+52Dh] [rbp-7ABh]
  int v180; // [rsp+5B0h] [rbp-728h]
  int v181; // [rsp+5B4h] [rbp-724h]
  _OWORD v182[8]; // [rsp+8E0h] [rbp-3F8h] BYREF
  char v183[8]; // [rsp+960h] [rbp-378h] BYREF
  __m256i v184; // [rsp+968h] [rbp-370h] BYREF
  __int128 v185; // [rsp+988h] [rbp-350h]
  __int128 v186; // [rsp+998h] [rbp-340h]
  __m128i v187; // [rsp+9B0h] [rbp-328h] BYREF
  __int128 v188; // [rsp+9C0h] [rbp-318h]
  __int128 v189; // [rsp+9D0h] [rbp-308h]
  __int128 v190; // [rsp+9E0h] [rbp-2F8h]
  int v191; // [rsp+9F8h] [rbp-2E0h]
  const wchar_t *v192; // [rsp+A00h] [rbp-2D8h]
  __int64 v193; // [rsp+A08h] [rbp-2D0h]
  int v194; // [rsp+A10h] [rbp-2C8h]
  __int128 v195; // [rsp+A18h] [rbp-2C0h]
  __int128 v196; // [rsp+A28h] [rbp-2B0h]
  __m128i v197; // [rsp+A40h] [rbp-298h]
  __int128 v198; // [rsp+A50h] [rbp-288h]
  __int128 v199; // [rsp+A60h] [rbp-278h]
  __int128 v200; // [rsp+A70h] [rbp-268h]
  char v201[528]; // [rsp+A80h] [rbp-258h] BYREF

  v173[20] = -2;
  v4 = a4;
  v129.QuadPart = (LONGLONG)a4;
  v6 = a2;
  v130 = a2;
  v126 = a1;
  v167 = a1;
  v148 = a2;
  v137 = a3;
  v168 = a4;
  v141.QuadPart = 0;
  v139 = 0;
  v143 = 0;
  v7 = 0;
  v138 = 0;
  v135 = 0;
  v145 = 0;
  v142 = 0;
  v140 = 0;
  v134 = 0;
  v157 = 0;
  v158 = 0;
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
  {
    QueryPerformanceCounter(&PerformanceCount);
    QuadPart = (CSbTransportMgr *)PerformanceCount.QuadPart;
  }
  else
  {
    QuadPart = MEMORY[0x7FFE0008];
  }
  v144 = QuadPart;
  LOWORD(v119) = 0;
  v122 = 0;
  LOBYTE(v121) = 0;
  PerformanceCount.LowPart = *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                           + SystemThread_TlsIndex)
                                                                         + SystemThread_TlsOffset)
                                                             + 80LL)
                                                 + 8LL);
  if ( !v6 || *((_DWORD *)v6 + 7) - *((_DWORD *)v6 + 10) < 2 )
    ex_raise(169, 3, 16, 300, off_102ED4430);
  LODWORD(v132) = 1;
  v124 = a3;
  LOBYTE(v128) = 0;
  v123 = 0;
  v147 = 0;
  v146 = 0;
  v120 = 1;
  v131 = OsInfo::IsLinux(SOS_OS_OsInfo) + 1;
  v9 = 0;
  v127 = 0;
  if ( a3 <= 0 )
    goto LABEL_58;
  while ( 1 )
  {
    v10 = *(CParamExchange ***)(*((_QWORD *)v6 + 2) + 8LL * (v9 + *((_DWORD *)v6 + 10)));
    if ( CompareStringWEnglishNoCase(
           1u,
           0,
           *((const wchar_t **)v10[3] + 4),
           *((unsigned __int16 *)v10[3] + 20) >> 1,
           L"@LANGUAGE",
           10) == 2 )
    {
      if ( v141.QuadPart )
        goto LABEL_143;
      v141.QuadPart = (LONGLONG)v10;
      v11 = v10[3];
      v12 = *((unsigned __int8 *)&xsm_rgOrdFromXvt + *(unsigned __int8 *)v11);
      if ( !*((_BYTE *)&CTypeInfo::sxm_rgfIsUnicode + v12)
        || *((_WORD *)v11 + 8) == 0xFFFF
        || *((_BYTE *)&CTypeInfo::sxm_rgfIsLargeObject + v12)
        || (v13 = v10[1], v14 = *((int *)v13 + 4), (unsigned int)v14 > 0x100)
        || *(_BYTE *)v13 == 3 )
      {
        if ( *(_BYTE *)v10[1] == 3 )
        {
          *((_DWORD *)v4 + 2) = 11554;
          ex_raise(115, 54, 16, 17, 18, L"@language");
        }
        else
        {
          ex_raise(2, 14, 16, 176, L"@language", L"nvarchar(128)");
        }
LABEL_52:
        if ( (unsigned int)(v132 - 1) <= 1 && !byte_10308E642 )
          ex_raise(391, 11, 16, 1);
        v6 = v130;
        goto LABEL_56;
      }
      v15 = (const wchar_t *)*((_QWORD *)v13 + 1);
      if ( CompareStringWEnglishNoCase(1u, 0, v15, v14 >> 1, L"R", 2) == 2 )
      {
        LODWORD(v132) = 1;
        v16 = 1;
        v123 = 1;
      }
      else if ( CompareStringWEnglishNoCase(1u, 0, v15, v14 >> 1, L"Python", 7) == 2 )
      {
        LODWORD(v132) = 2;
        v16 = 2;
        v123 = 2;
      }
      else if ( byte_102EDCC33 && (*((_BYTE *)qword_102ECFB10 + 1342) & 4) == 0 )
      {
        LODWORD(v132) = 3;
        LOBYTE(v121) = 1;
        v18 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v19 = *(_QWORD *)(v18 + 256);
        if ( !v19 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v19 = *(_QWORD *)(v18 + 256);
        }
        v20 = *(_QWORD *)(v19 + 1000);
        v21 = *((_QWORD *)v126 + 18);
        if ( !v21 || (v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 432LL))(v21)) == 0 )
        {
          v23 = (__int64)v147;
          if ( !v147 )
          {
            v23 = (**(__int64 (__fastcall ***)(struct IAutoXactFactory *))g_pAutoXactFactory)(g_pAutoXactFactory);
            v147 = (void (__fastcall ***)(_QWORD, __int64))v23;
          }
          (*(void (__fastcall **)(__int64, const wchar_t *, __int64))(*(_QWORD *)v23 + 16LL))(
            v23,
            L"SpExecuteExternalScript",
            46);
          v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 72LL))(v23);
        }
        v24 = g_metadataFactory(v20, v22, "sql\\ntdbms\\msql\\proc\\specproc.cpp", 4110);
        if ( v146 != (void (__fastcall ***)(_QWORD, __int64))v24 && v146 )
          (**v146)(v146, 1);
        v146 = (void (__fastcall ***)(_QWORD, __int64))v24;
        v25 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(*(_QWORD *)v24 + 56LL))(
                v24,
                PerformanceCount.LowPart,
                0,
                0,
                0,
                0);
        v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64))(**(_QWORD **)(*((_QWORD *)v126 + 15) + 264LL)
                                                                          + 352LL))(
                *(_QWORD *)(*((_QWORD *)v126 + 15) + 264LL),
                PerformanceCount.LowPart,
                1,
                1);
        v27 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v25 + 232LL))(v25, v26, 0, 0);
        v171 = v15;
        v172 = v14;
        v28 = (*(__int64 (__fastcall **)(__int64, const wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v27 + 432LL))(
                v27,
                &v171,
                0,
                0);
        if ( !v28 )
        {
          LODWORD(v98) = *((_DWORD *)v10[1] + 4);
          ex_raise(390, 7, 16, 2, v98, v15);
        }
        v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
        v123 = v16;
        if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, char *, __int64))(*(_QWORD *)v28 + 48LL))(
                v28,
                v131,
                v201,
                522) )
        {
          v29 = 0;
          v120 = 0;
          goto LABEL_40;
        }
      }
      else
      {
        LODWORD(v97) = *((_DWORD *)v10[1] + 4);
        ex_raise(390, 7, 16, 1, v97, v15);
        v16 = v123;
      }
      v29 = v120;
LABEL_40:
      v118 = 0;
      v117 = 0;
      v116 = 0;
      LODWORD(v115) = 0;
      LODWORD(v114) = 0;
      LOBYTE(v113) = 0;
      LODWORD(v112) = 0;
      LODWORD(v111) = 0;
      LODWORD(v110) = 0;
      LODWORD(v109) = -1;
      LODWORD(v108) = 0;
      LODWORD(v107) = 0;
      *(_QWORD *)v106 = 0;
      *(_DWORD *)v105 = 0;
      v104[0] = 30;
      *(_QWORD *)v103 = 0;
      *(_QWORD *)v102 = 0;
      v101[0] = 1;
      if ( !(unsigned __int8)ISECManager::AccessCheckWithAuditState(
                               0,
                               PerformanceCount.LowPart,
                               PerformanceCount.LowPart,
                               0,
                               96) )
      {
        if ( *(_DWORD *)(qword_102ECFB00 + 14504) )
          goto LABEL_44;
        if ( !v16 )
          goto LABEL_44;
        v118 = 0;
        v117 = 0;
        v116 = 0;
        LODWORD(v115) = 0;
        LODWORD(v114) = 0;
        LOBYTE(v113) = 0;
        LODWORD(v112) = 0;
        LODWORD(v111) = 0;
        LODWORD(v110) = 0;
        LODWORD(v109) = -1;
        LODWORD(v108) = 0;
        LODWORD(v107) = 0;
        *(_QWORD *)v106 = 0;
        *(_DWORD *)v105 = 0;
        v104[0] = 30;
        *(_QWORD *)v103 = 0;
        *(_QWORD *)v102 = 0;
        v101[0] = 1;
        if ( !(unsigned __int8)ISECManager::AccessCheckWithAuditState(0, PerformanceCount.LowPart, v16, 23, 5) )
LABEL_44:
          ex_raise(2, 97, 16, 101);
      }
      if ( !v29 )
      {
        v30 = L"WINDOWS";
        if ( v131 == 2 )
          v30 = L"LINUX";
        v31 = -1;
        do
          ++v31;
        while ( v30[v31] );
        *(_QWORD *)v102 = v15;
        *(_DWORD *)v101 = v14;
        LODWORD(v99) = 2 * v31;
        ex_raise(391, 24, 16, 3, v99, v30);
      }
      v4 = (struct CXVariant *)v129.QuadPart;
      goto LABEL_52;
    }
    if ( CompareStringWEnglishNoCase(
           1u,
           0,
           *((const wchar_t **)v10[3] + 4),
           *((unsigned __int16 *)v10[3] + 20) >> 1,
           L"@SCRIPT",
           8) == 2 )
    {
      if ( v143 )
        goto LABEL_143;
      v143 = v10;
      if ( *(_BYTE *)v10[1] == 3 )
      {
        *((_DWORD *)v4 + 2) = 11554;
        ex_raise(115, 54, 16, 16, 14, L"@script");
      }
      if ( !*((_BYTE *)&CTypeInfo::sxm_rgfIsUnicode
            + *((unsigned __int8 *)&xsm_rgOrdFromXvt + *(unsigned __int8 *)v10[3])) )
      {
        *((_DWORD *)v4 + 2) = 214;
        ex_raise(2, 14, 16, 170, L"@script", L"nvarchar(max)");
      }
      goto LABEL_56;
    }
    if ( CompareStringWEnglishNoCase(
           1u,
           0,
           *((const wchar_t **)v10[3] + 4),
           *((unsigned __int16 *)v10[3] + 20) >> 1,
           L"@INPUT_DATA_1",
           14) == 2 )
    {
      if ( v139 )
        goto LABEL_143;
      if ( !*((_BYTE *)&CTypeInfo::sxm_rgfIsUnicode
            + *((unsigned __int8 *)&xsm_rgOrdFromXvt + *(unsigned __int8 *)v10[3])) )
      {
        *((_DWORD *)v4 + 2) = 214;
        ex_raise(2, 14, 16, 179, L"@input_data_1", L"nvarchar(max)");
      }
      v139 = v10;
      goto LABEL_56;
    }
    if ( CompareStringWEnglishNoCase(
           1u,
           0,
           *((const wchar_t **)v10[3] + 4),
           *((unsigned __int16 *)v10[3] + 20) >> 1,
           L"@RUNTIME_INPUT",
           15) == 2 )
    {
      if ( v142 )
        goto LABEL_143;
      if ( byte_102EDCC2B )
      {
        v32 = v10[3];
        v33 = *(unsigned __int8 *)v32;
        v34 = *((_BYTE *)&CTypeInfo::sxm_rgfIsBinary + *((unsigned __int8 *)&xsm_rgOrdFromXvt + v33));
        if ( (!v34 || *((_WORD *)v32 + 8) != 0xFFFF) && (_BYTE)v33 != 34 && !v34 )
        {
          *((_DWORD *)v4 + 2) = 214;
          ex_raise(2, 14, 16, 179, L"@runtime_input", L"varbinary(max)");
        }
        v142 = v10;
      }
      goto LABEL_56;
    }
    if ( CompareStringWEnglishNoCase(
           1u,
           0,
           *((const wchar_t **)v10[3] + 4),
           *((unsigned __int16 *)v10[3] + 20) >> 1,
           L"@PARALLEL",
           10) != 2 )
      break;
    if ( BYTE1(v119) )
      goto LABEL_143;
    BYTE1(v119) = 1;
    if ( !byte_102EDCC2F || (*((_BYTE *)qword_102ECFB10 + 1338) & 1) != 0 )
    {
      ex_raise(390, 14, 16, 1);
    }
    else
    {
      v35 = *(unsigned __int8 *)v10[3];
      if ( CTypeInfo::sxm_rgfIsInteger[*((unsigned __int8 *)&xsm_rgOrdFromXvt + v35)] )
      {
        if ( *((_DWORD *)v10[1] + 2) <= 1u )
        {
LABEL_96:
          if ( *((_BYTE *)v10[1] + 8) == 1 && *((_DWORD *)s_pServerConf + 2) == 2 )
            LOBYTE(v119) = 1;
          goto LABEL_56;
        }
        *((_DWORD *)v4 + 2) = 214;
        ex_raise(2, 14, 16, 172, L"@parallel", L"bit");
      }
      else
      {
        if ( (_BYTE)v35 == 104 )
          goto LABEL_96;
        *((_DWORD *)v4 + 2) = 214;
        ex_raise(2, 14, 16, 171, L"@parallel", L"bit");
      }
    }
LABEL_56:
    v9 = v127 + 1;
    v127 = v9;
    if ( v9 >= a3 )
      goto LABEL_57;
  }
  if ( CompareStringWEnglishNoCase(
         1u,
         0,
         *((const wchar_t **)v10[3] + 4),
         *((unsigned __int16 *)v10[3] + 20) >> 1,
         L"@INPUT_DATA_1_NAME",
         19) == 2 )
  {
    if ( v135 )
      goto LABEL_143;
    v36 = v10[3];
    v37 = *((unsigned __int8 *)&xsm_rgOrdFromXvt + *(unsigned __int8 *)v36);
    if ( !*((_BYTE *)&CTypeInfo::sxm_rgfIsUnicode + v37)
      || *((_WORD *)v36 + 8) == 0xFFFF
      || *((_BYTE *)&CTypeInfo::sxm_rgfIsLargeObject + v37)
      || *((_DWORD *)v10[1] + 4) > 0x100u )
    {
      *((_DWORD *)v4 + 2) = 214;
      ex_raise(2, 14, 16, 173, L"@input_data_1_name", L"nvarchar(128)");
    }
    v135 = v10;
    goto LABEL_56;
  }
  if ( CompareStringWEnglishNoCase(
         1u,
         0,
         *((const wchar_t **)v10[3] + 4),
         *((unsigned __int16 *)v10[3] + 20) >> 1,
         L"@OUTPUT_DATA_1_NAME",
         20) == 2 )
  {
    if ( v145 )
      goto LABEL_143;
    v38 = v10[3];
    v39 = *((unsigned __int8 *)&xsm_rgOrdFromXvt + *(unsigned __int8 *)v38);
    if ( !*((_BYTE *)&CTypeInfo::sxm_rgfIsUnicode + v39)
      || *((_WORD *)v38 + 8) == 0xFFFF
      || *((_BYTE *)&CTypeInfo::sxm_rgfIsLargeObject + v39)
      || *((_DWORD *)v10[1] + 4) > 0x100u )
    {
      *((_DWORD *)v4 + 2) = 214;
      ex_raise(2, 14, 16, 174, L"@output_data_1_name", L"nvarchar(128)");
    }
    v145 = v10;
    goto LABEL_56;
  }
  if ( CompareStringWEnglishNoCase(
         1u,
         0,
         *((const wchar_t **)v10[3] + 4),
         *((unsigned __int16 *)v10[3] + 20) >> 1,
         L"@PARAMS",
         8) == 2 )
  {
    if ( v138 )
      goto LABEL_143;
    v40 = *((_BYTE *)&CTypeInfo::sxm_rgfIsUnicode + *((unsigned __int8 *)&xsm_rgOrdFromXvt + *(unsigned __int8 *)v10[3]));
    v41 = v122;
    if ( v40 )
      v41 = 1;
    v122 = v41;
    if ( !v40 )
      v10 = v138;
    v138 = v10;
    v42 = v127 + 1;
    if ( !v40 )
      v42 = v124;
    v124 = v42;
    goto LABEL_56;
  }
  if ( CompareStringWEnglishNoCase(
         1u,
         0,
         *((const wchar_t **)v10[3] + 4),
         *((unsigned __int16 *)v10[3] + 20) >> 1,
         L"@INPUTDATASET",
         14) == 2 )
  {
    *((_DWORD *)v4 + 2) = 39008;
    ex_raise(390, 8, 16, 174, L"@INPUTDATASET");
    goto LABEL_56;
  }
  if ( CompareStringWEnglishNoCase(
         1u,
         0,
         *((const wchar_t **)v10[3] + 4),
         *((unsigned __int16 *)v10[3] + 20) >> 1,
         L"@INPUT_DATA_1_PARTITION_BY_COLUMNS",
         35) == 2 )
  {
    if ( v140 )
      goto LABEL_143;
    if ( byte_102EDCC29 && *((char *)qword_102ECFB10 + 1340) >= 0 )
    {
      if ( !*((_BYTE *)&CTypeInfo::sxm_rgfIsUnicode
            + *((unsigned __int8 *)&xsm_rgOrdFromXvt + *(unsigned __int8 *)v10[3])) )
      {
        *((_DWORD *)v4 + 2) = 214;
        ex_raise(2, 14, 16, 180, L"@input_data_1_partition_by_columns", L"nvarchar(max)");
      }
      v140 = v10;
    }
    else
    {
      ex_raise(
        1,
        2,
        16,
        105,
        68,
        L"@input_data_1_partition_by_columns",
        *(_QWORD *)v101,
        *(_QWORD *)v102,
        *(_QWORD *)v103,
        *(_QWORD *)v104,
        *(_QWORD *)v105,
        *(_QWORD *)v106,
        v107,
        v108,
        v109,
        v110,
        v111,
        v112,
        v113,
        v114,
        v115,
        v116,
        v117,
        v118,
        v119);
    }
    goto LABEL_56;
  }
  if ( CompareStringWEnglishNoCase(
         1u,
         0,
         *((const wchar_t **)v10[3] + 4),
         *((unsigned __int16 *)v10[3] + 20) >> 1,
         L"@INPUT_DATA_1_ORDER_BY_COLUMNS",
         31) != 2 )
  {
    if ( !v122 )
    {
      *((_DWORD *)v4 + 2) = 214;
      ex_raise(2, 14, 16, 175, L"@params", L"ntext/nchar/nvarchar");
    }
    v44 = v10[3];
    if ( *((_WORD *)v44 + 8) == 0xFFFF
      || *((_BYTE *)&CTypeInfo::sxm_rgfIsLargeObject + *((unsigned __int8 *)&xsm_rgOrdFromXvt + *(unsigned __int8 *)v44)) )
    {
      v45 = (unsigned __int8)v128;
      if ( (*(_BYTE *)v10 & 1) != 0 )
        v45 = 1;
      v128 = v45;
    }
    goto LABEL_56;
  }
  if ( !v134 )
  {
    if ( byte_102EDCC29 && *((char *)qword_102ECFB10 + 1340) >= 0 )
    {
      if ( !*((_BYTE *)&CTypeInfo::sxm_rgfIsUnicode
            + *((unsigned __int8 *)&xsm_rgOrdFromXvt + *(unsigned __int8 *)v10[3])) )
      {
        *((_DWORD *)v4 + 2) = 214;
        ex_raise(2, 14, 16, 181, L"@input_data_1_order_by_columns", L"nvarchar(max)");
      }
      v134 = (__int64)v10;
    }
    else
    {
      ex_raise(
        1,
        2,
        16,
        106,
        60,
        L"@input_data_1_order_by_columns",
        *(_QWORD *)v101,
        *(_QWORD *)v102,
        *(_QWORD *)v103,
        *(_QWORD *)v104,
        *(_QWORD *)v105,
        *(_QWORD *)v106,
        v107,
        v108,
        v109,
        v110,
        v111,
        v112,
        v113,
        v114,
        v115,
        v116,
        v117,
        v118,
        v119);
    }
    goto LABEL_56;
  }
LABEL_143:
  *((_DWORD *)v4 + 2) = 39027;
  v43 = v10[3];
  LODWORD(v96) = *((unsigned __int16 *)v43 + 20);
  ex_raise(390, 27, 16, 1, v96, *((_QWORD *)v43 + 4));
LABEL_57:
  v7 = v138;
  if ( !v141.QuadPart )
  {
LABEL_58:
    *((_DWORD *)v4 + 2) = 214;
    ex_raise(2, 14, 16, 178, L"@language", L"nvarchar(128)");
  }
  if ( !v143 )
  {
    *((_DWORD *)v4 + 2) = 214;
    ex_raise(2, 14, 16, 170, L"@script", L"nvarchar(max)");
  }
  if ( v7 )
  {
    if ( v122 )
      goto LABEL_153;
    goto LABEL_152;
  }
  if ( v122 )
  {
LABEL_152:
    *((_DWORD *)v4 + 2) = 214;
    ex_raise(2, 14, 16, 214, L"@params", L"ntext/nchar/nvarchar");
  }
LABEL_153:
  if ( (_BYTE)v128 )
    LOBYTE(v119) = 0;
  if ( !v140 && v134 )
  {
    *((_DWORD *)v4 + 2) = 39103;
    ex_raise(391, 3, 16, 1);
  }
  `eh vector constructor iterator'(
    v183,
    0x48u,
    4u,
    (void (*)(void *))CAutoClearXVariant::CAutoClearXVariant,
    CAutoClearXVariant::~CAutoClearXVariant);
  *(_WORD *)((char *)v182 + 1) = 0;
  BYTE3(v182[0]) = 0;
  LOBYTE(v182[0]) = 0;
  DWORD1(v182[0]) = 0;
  *((_QWORD *)&v182[0] + 1) = -1;
  memset(&v182[1], 0, 24);
  memset((char *)&v182[2] + 15, 0, 17);
  *((_QWORD *)&v182[2] + 1) = -1;
  LODWORD(v182[3]) = 0;
  *(_QWORD *)((char *)&v182[3] + 15) = 0;
  memset((char *)&v182[4] + 15, 0, 17);
  DWORD1(v182[4]) = 0;
  *((_QWORD *)&v182[4] + 1) = -1;
  LODWORD(v182[5]) = 0;
  *(_QWORD *)((char *)&v182[5] + 15) = 0;
  memset((char *)&v182[6] + 15, 0, 17);
  DWORD1(v182[6]) = 0;
  *((_QWORD *)&v182[6] + 1) = -1;
  LODWORD(v182[7]) = 0;
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v47 = *(_DWORD *)CDbAndSetOptsImplImport::GetDefaultCollation(
                     (CDbAndSetOptsImplImport *)*(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(ThreadLocalStoragePointer[SystemThread_TlsIndex]
                                                                                            + SystemThread_TlsOffset)
                                                                                + 80LL)
                                                                    + 8LL),
                     (unsigned __int16)ThreadLocalStoragePointer);
  CTypeInfo::InitWithMaxLen((CTypeInfo *)&v149, 0xE7u, 0);
  BYTE1(v149) |= 1u;
  if ( (_BYTE)v149 == 98 )
    LOWORD(v150) = 2;
  if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrWString + *((unsigned __int8 *)&xsm_rgOrdFromXvt + (unsigned __int8)v149))
    || (((_BYTE)v149 - 35) & 0xBF) == 0 )
  {
    v48 = CTypeInfo::FCharacterOrEncryptedCharacter((CTypeInfo *)&v149);
    v49 = DWORD1(v150);
    if ( v48 )
      v49 = v47;
    DWORD1(v150) = v49;
  }
  if ( v7 )
  {
    CTypeInfo::InitWithMaxLen((CTypeInfo *)&v159, 0xEFu, 2);
    BYTE1(v159) |= 1u;
    if ( (_BYTE)v159 == 98 )
      LOWORD(v160) = 2;
    if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrWString
         + *((unsigned __int8 *)&xsm_rgOrdFromXvt + (unsigned __int8)v159))
      || (((_BYTE)v159 - 35) & 0xBF) == 0 )
    {
      v50 = CTypeInfo::FCharacterOrEncryptedCharacter((CTypeInfo *)&v159);
      v51 = DWORD1(v160);
      if ( v50 )
        v51 = v47;
      DWORD1(v160) = v51;
    }
    v182[0] = v159;
    v182[1] = v160;
    v184.m256i_i32[0] = 61184;
    v184.m256i_i32[6] = 0;
    v184.m256i_i64[1] = (__int64)L"(";
    v184.m256i_i64[2] = 2;
    v185 = v159;
    v186 = v160;
    v52 = v7[3];
    v182[2] = *(_OWORD *)v52;
    v182[3] = *((_OWORD *)v52 + 1);
    v187.m128i_i32[0] = 3;
    v187.m128i_i64[1] = 0;
    *(_QWORD *)&v188 = 0;
    DWORD2(v188) = 0;
    v53 = v7[1];
    v187 = *(__m128i *)v53;
    v188 = *((_OWORD *)v53 + 1);
    v187.m128i_i16[1] = _mm_extract_epi16(v187, 1) & 0xFFFE;
    v189 = v182[2];
    v190 = v182[3];
    CTypeInfo::InitWithMaxLen((CTypeInfo *)&v161, 0xEFu, 2);
    BYTE1(v161) |= 1u;
    if ( (_BYTE)v161 == 98 )
      LOWORD(v162) = 2;
    if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrWString
         + *((unsigned __int8 *)&xsm_rgOrdFromXvt + (unsigned __int8)v161))
      || (((_BYTE)v161 - 35) & 0xBF) == 0 )
    {
      v54 = CTypeInfo::FCharacterOrEncryptedCharacter((CTypeInfo *)&v161);
      v55 = DWORD1(v162);
      if ( v54 )
        v55 = v47;
      DWORD1(v162) = v55;
    }
    v182[4] = v161;
    v182[5] = v162;
    v191 = 61184;
    v194 = 0;
    v192 = L")";
    v193 = 2;
    v195 = v161;
    v196 = v162;
    v56 = v139;
    if ( v139 )
    {
      v57 = v139[3];
      v58 = *(_OWORD *)v57;
      v182[6] = *(_OWORD *)v57;
      v59 = *((_OWORD *)v57 + 1);
      v182[7] = v59;
      v197.m128i_i32[0] = 3;
      v197.m128i_i64[1] = 0;
      *(_QWORD *)&v198 = 0;
      DWORD2(v198) = 0;
      v60 = v139[1];
      v197 = *(__m128i *)v60;
      v198 = *((_OWORD *)v60 + 1);
      v197.m128i_i16[1] = _mm_extract_epi16(v197, 1) & 0xFFFE;
    }
    else
    {
      v58 = v149;
      v182[6] = v149;
      v59 = v150;
      v182[7] = v150;
      v197.m128i_i32[0] = 59139;
      DWORD2(v198) = 0;
      v197.m128i_i64[1] = (__int64)&szPassword;
      *(_QWORD *)&v198 = 0;
    }
    v199 = v58;
    v200 = v59;
    v61 = (CXVariant::CbSize((CXVariant *)&v187, (const struct CTypeInfo *)&v182[2]) >> 1) + 2;
    v62 = 4;
  }
  else
  {
    v56 = v139;
    if ( v139 )
    {
      v63 = v139[3];
      v64 = *(_OWORD *)v63;
      v182[0] = *(_OWORD *)v63;
      v65 = *((_OWORD *)v63 + 1);
      v182[1] = v65;
      v184.m256i_i32[0] = 3;
      memset(&v184.m256i_u64[1], 0, 20);
      v184 = *(__m256i *)v139[1];
      v184.m256i_i16[1] = _mm_extract_epi16(*(__m128i *)v184.m256i_i8, 1) & 0xFFFE;
    }
    else
    {
      v64 = v149;
      v182[0] = v149;
      v65 = v150;
      v182[1] = v150;
      v184.m256i_i32[0] = 59139;
      v184.m256i_i32[6] = 0;
      v184.m256i_i64[1] = (__int64)&szPassword;
      v184.m256i_i64[2] = 0;
    }
    v185 = v64;
    v186 = v65;
    v61 = 0;
    v62 = 1;
  }
  if ( a3 > v124 )
  {
    *((_DWORD *)v6 + 8) |= 8u;
    v66 = v124;
    if ( v124 )
    {
      v67 = *((_QWORD *)v6 + 2);
      v68 = *((_DWORD *)v6 + 10);
      do
      {
        if ( (**(_BYTE **)(v67 + 8LL * v68) & 1) != 0 )
        {
          --*((_WORD *)v6 + 30);
          ++*((_WORD *)v6 + 46);
        }
        *((_DWORD *)v6 + 10) = ++v68;
        --v66;
      }
      while ( v66 );
    }
  }
  v69 = *(_BYTE **)&CommonGlobalState::m_PerfCountersEnabled;
  if ( CommonGlobalState::m_PerfCountersEnabled )
  {
    PerfmonManager::IncrementCounterValue((PerfmonManager *)qword_102ECFB00, 0x36u, 0, 1, 0);
    v69 = *(_BYTE **)&CommonGlobalState::m_PerfCountersEnabled;
  }
  if ( v142 && v56 && *((_DWORD *)v56[1] + 4) && *v69 )
    PerfmonManager::IncrementCounterValue((PerfmonManager *)qword_102ECFB00, 0x36u, 0x18u, 1, 0);
  try
  {
    CSQLStrings::CSQLStrings(
      (CSQLStrings *)v175,
      (const struct CAutoClearXVariant *)v183,
      (const struct CTypeInfo *)v182,
      v62,
      0,
      0,
      1,
      0,
      0,
      v61,
      1,
      0);
    v179 &= ~2u;
    v181 |= 0x10000u;
    v180 |= 0x1200000u;
    v70 = 0;
    if ( a3 > v124 )
      v70 = v6;
    v71 = v126;
    v72 = (__int64 *)*((_QWORD *)PCXCtxtGetIfExistsEXPENSIVE(v126) + 20);
    v73 = 0;
    v170 = 0;
    v74 = *v72;
    if ( *v72 )
    {
      v75 = *(_QWORD *)(v176 + 16);
      if ( v75 )
      {
        if ( (*(_DWORD *)(v75 + 32) & 2) != 0 )
        {
          v73 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v74 + 8) + 416LL) + 1808LL) + 32LL);
          v170 = v73;
        }
      }
    }
    v76 = v140;
    if ( v140 )
    {
      v77 = (struct IMemObj *)*((_QWORD *)v130 + 6);
      v173[21] = v77;
      v136 = 0;
      if ( CommonGlobalState::m_PerfCountersEnabled )
        PerfmonManager::IncrementCounterValue((PerfmonManager *)qword_102ECFB00, 0x36u, 0x38u, 1, 0);
      v163 = 4699;
      v78 = operator new(0x28u, v77, "sql\\ntdbms\\msql\\proc\\specproc.cpp", 4699, 3u);
      v173[22] = v78;
      if ( v78 )
      {
        v140 = &v151;
        v139 = &v165;
        v165 = v77;
        v138 = &v151;
        v151 = v77;
        v173[23] = &v152;
        v173[24] = &v152;
        v152 = v77;
        v173[2] = v78;
        v173[3] = &v153;
        v173[4] = &v153;
        v153 = v77;
        v173[5] = v78;
        v173[6] = v78;
        *(_QWORD *)v78 = v77;
        *((_WORD *)v78 + 4) = v121;
        *((_DWORD *)v78 + 3) = 0;
        *((_QWORD *)v78 + 2) = 0;
        *((_DWORD *)v78 + 6) = 0;
        *((_DWORD *)v78 + 7) = 0;
        *((_DWORD *)v78 + 8) = 0;
        CTHashTable<Pair<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CTMap<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *,CFnH_Pointer,CFnC_Default<CValRef *>,CFnI_Default<CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CFnD_Noop<CValRef *>,CFnD_Ptr<CTSingleColumnPredicateCombiner<CIntervalForCE>>,CMemObjAlloc<0>>::CEntryHashFn,CTMap<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *,CFnH_Pointer,CFnC_Default<CValRef *>,CFnI_Default<CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CFnD_Noop<CValRef *>,CFnD_Ptr<CTSingleColumnPredicateCombiner<CIntervalForCE>>,CMemObjAlloc<0>>::CEntryCmpFn,CTMap<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *,CFnH_Pointer,CFnC_Default<CValRef *>,CFnI_Default<CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CFnD_Noop<CValRef *>,CFnD_Ptr<CTSingleColumnPredicateCombiner<CIntervalForCE>>,CMemObjAlloc<0>>::CEntryInvalidFn,CTMap<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *,CFnH_Pointer,CFnC_Default<CValRef *>,CFnI_Default<CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CFnD_Noop<CValRef *>,CFnD_Ptr<CTSingleColumnPredicateCombiner<CIntervalForCE>>,CMemObjAlloc<0>>::CEntryDestroyFn,CMemObjAlloc<0>>::Resize(
          v78,
          40);
      }
      else
      {
        v78 = 0;
      }
      v157 = v78;
      if ( !(unsigned __int8)ParseExternalScriptColumns(v77, v71, 12, v76, v78, 0) )
      {
        *(_DWORD *)(v129.QuadPart + 8) = *(_DWORD *)(*((_QWORD *)v71 + 15) + 276LL);
        ex_raise(391, 5, 16, 1);
      }
      v79 = *((_DWORD *)v78 + 6);
      v136 = v79;
      if ( v134 )
      {
        v164 = 4715;
        v80 = operator new(0x28u, v77, "sql\\ntdbms\\msql\\proc\\specproc.cpp", 4715, 3u);
        v173[7] = v80;
        if ( v80 )
        {
          v173[8] = &v154;
          v173[9] = &v166;
          v166 = v77;
          v173[10] = &v154;
          v154 = v77;
          v173[11] = &v155;
          v173[12] = &v155;
          v155 = v77;
          v173[13] = v80;
          v173[14] = &v156;
          v173[15] = &v156;
          v156 = v77;
          v173[16] = v80;
          v173[17] = v80;
          *(_QWORD *)v80 = v77;
          v80[4] = v121;
          *((_DWORD *)v80 + 3) = 0;
          *((_QWORD *)v80 + 2) = 0;
          *((_DWORD *)v80 + 6) = 0;
          *((_DWORD *)v80 + 7) = 0;
          *((_DWORD *)v80 + 8) = 0;
          CTHashTable<Pair<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CTMap<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *,CFnH_Pointer,CFnC_Default<CValRef *>,CFnI_Default<CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CFnD_Noop<CValRef *>,CFnD_Ptr<CTSingleColumnPredicateCombiner<CIntervalForCE>>,CMemObjAlloc<0>>::CEntryHashFn,CTMap<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *,CFnH_Pointer,CFnC_Default<CValRef *>,CFnI_Default<CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CFnD_Noop<CValRef *>,CFnD_Ptr<CTSingleColumnPredicateCombiner<CIntervalForCE>>,CMemObjAlloc<0>>::CEntryCmpFn,CTMap<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *,CFnH_Pointer,CFnC_Default<CValRef *>,CFnI_Default<CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CFnD_Noop<CValRef *>,CFnD_Ptr<CTSingleColumnPredicateCombiner<CIntervalForCE>>,CMemObjAlloc<0>>::CEntryInvalidFn,CTMap<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *,CFnH_Pointer,CFnC_Default<CValRef *>,CFnI_Default<CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CFnD_Noop<CValRef *>,CFnD_Ptr<CTSingleColumnPredicateCombiner<CIntervalForCE>>,CMemObjAlloc<0>>::CEntryDestroyFn,CMemObjAlloc<0>>::Resize(
            v80,
            40);
        }
        else
        {
          v80 = 0;
        }
        v158 = (__int64)v80;
        if ( !(unsigned __int8)ParseExternalScriptColumns(v77, v126, 13, v134, v78, v80) )
        {
          *(_DWORD *)(v129.QuadPart + 8) = *(_DWORD *)(*((_QWORD *)v126 + 15) + 276LL);
          ex_raise(391, 6, 16, 1);
        }
        v79 += *((_DWORD *)v80 + 6);
        v136 = v79;
      }
      v81 = v129;
      if ( v79 > 0x20 )
      {
        *(_DWORD *)(v129.QuadPart + 8) = 39109;
        LODWORD(v100) = 32;
        ex_raise(391, 9, 16, 2, v100);
      }
      v71 = v126;
    }
    else
    {
      v78 = v157;
      v81 = v129;
    }
    v82 = v123;
    if ( !v123 )
      v82 = v132;
    LowPart = 0;
    if ( (_BYTE)v121 )
      LowPart = v141.LowPart;
    CSQLSource::SetupExternalScriptInfo(
      (unsigned int)v175,
      v132,
      LowPart,
      v82,
      v119,
      (__int64)v143,
      (__int64)v142,
      (__int64)v135,
      (__int64)v145,
      (__int64)v78,
      v158,
      (__int64)v70,
      v73,
      PerformanceCount.LowPart);
    if ( (*(_DWORD *)(v176 + 24) & 4) != 0 )
      v177 = v177 & 0xFFFFFFF3 | 4;
    CSQLSource::Execute((CSQLSource *)v175, v71, v70, 0);
    if ( v178 == 8 && CommonGlobalState::m_PerfCountersEnabled )
      PerfmonManager::IncrementCounterValue((PerfmonManager *)qword_102ECFB00, 0x36u, 0x30u, 1, 0);
    CSQLStrings::~CSQLStrings((CSQLStrings *)v175);
  }
  catch ( SQLError v174 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)v173, (const struct SQLError *)v174);
      if ( v137 > v124 )
      {
        v90 = v148;
        *((_DWORD *)v148 + 8) &= ~8u;
        _mm_lfence();
        CParamExchange::DecrParamOffset(v90, v124);
      }
      v135 = &v130;
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v129);
        v91 = (CSbTransportMgr *)v129.QuadPart;
        v130 = (CParamExchange *)v129.QuadPart;
      }
      else
      {
        v91 = MEMORY[0x7FFE0008];
        v130 = MEMORY[0x7FFE0008];
      }
      v145 = &v144;
      v143 = &v130;
      if ( v91 < v144 )
      {
        v92 = 0;
        v135 = 0;
      }
      else
      {
        v92 = (CParamExchange **)(v91 - v144);
        v135 = v92;
      }
      v126 = (struct CCompExecCtxtBasic *)v92;
      v142 = &v126;
      if ( v92 == (CParamExchange **)-1LL )
      {
        v93 = -1;
      }
      else if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        v141 = Base_PublicGlobals::sm_QueryPerformanceFrequency;
        v134 = 1;
        v131 = 3;
        v128 = 1000;
        v132 = 1000;
        v93 = (unsigned __int64)(1000LL * (_QWORD)v92) / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
      }
      else
      {
        v173[18] = &v126;
        v127 = -4;
        v93 = (unsigned __int64)v92 / 0x2710;
      }
      v173[19] = v93;
      v94 = *(_BYTE **)&CommonGlobalState::m_PerfCountersEnabled;
      if ( CommonGlobalState::m_PerfCountersEnabled )
      {
        PerfmonManager::IncrementCounterValue((PerfmonManager *)qword_102ECFB00, 0x36u, 0x28u, v93, 0);
        v94 = *(_BYTE **)&CommonGlobalState::m_PerfCountersEnabled;
      }
      if ( *v94 )
        PerfmonManager::IncrementCounterValue((PerfmonManager *)qword_102ECFB00, 0x36u, 0x30u, 1, 0);
      CurrentException = ExceptionBackout::GetCurrentException((ExceptionBackout *)v173);
      ExceptionRethrow(CurrentException);
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v173);
    }
    catch ( ShortStackException )
    {
    }
    v71 = v167;
    v84 = v148;
    v85 = v137;
    v81.QuadPart = (LONGLONG)v168;
    goto LABEL_237;
  }
  v84 = v130;
  v85 = a3;
LABEL_237:
  v86 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v87 = *(struct Worker **)(v86 + 256);
  if ( !v87 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v87 = *(struct Worker **)(v86 + 256);
  }
  if ( *((_DWORD *)v87 + 139) )
    ExceptionPostCatchActions(v87);
  if ( v85 > v124 )
  {
    _mm_lfence();
    *((_DWORD *)v84 + 8) &= ~8u;
    CParamExchange::DecrParamOffset(v84, v124);
  }
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
  {
    QueryPerformanceCounter(&v169);
    v88 = (CSbTransportMgr *)v169.QuadPart;
  }
  else
  {
    v88 = MEMORY[0x7FFE0008];
  }
  if ( v88 < v144 )
  {
    v89 = 0;
  }
  else
  {
    v89 = v88 - v144;
    if ( v89 == -1 )
      goto LABEL_253;
  }
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
    v89 = 1000 * v89 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
  else
    v89 /= 0x2710u;
LABEL_253:
  if ( CommonGlobalState::m_PerfCountersEnabled )
    PerfmonManager::IncrementCounterValue((PerfmonManager *)qword_102ECFB00, 0x36u, 0x28u, v89, 0);
  *(_DWORD *)(v81.QuadPart + 8) = *(_DWORD *)(*((_QWORD *)v71 + 15) + 276LL);
  `eh vector destructor iterator'(v183, 0x48u, 4u, CAutoClearXVariant::~CAutoClearXVariant);
  if ( v146 )
    (**v146)(v146, 1);
  if ( v147 )
    (**v147)(v147, 1);
}

```

## disassembly

```asm
0x101221770  push    rbx
0x101221772  push    rsi
0x101221773  push    rdi
0x101221774  push    r12
0x101221776  push    r13
0x101221778  push    r14
0x10122177a  push    r15
0x10122177c  sub     rsp, 0CA0h
0x101221783  mov     [rsp+0CD8h+var_9B0], 0FFFFFFFFFFFFFFFEh
0x10122178f  mov     rax, cs:__security_cookie
0x101221796  xor     rax, rsp
0x101221799  mov     [rsp+0CD8h+var_48], rax
0x1012217a1  mov     rbx, r9
0x1012217a4  mov     [rsp+0CD8h+var_BD8], rbx
0x1012217ac  mov     r14d, r8d
0x1012217af  mov     [rsp+0CD8h+var_BF0], r8d
0x1012217b7  mov     r12, rdx
0x1012217ba  mov     [rsp+0CD8h+var_BD0], rdx
0x1012217c2  mov     [rsp+0CD8h+var_BE8], rcx
0x1012217ca  mov     [rsp+0CD8h+var_A80], rcx
0x1012217d2  mov     [rsp+0CD8h+var_B40], rdx
0x1012217da  mov     [rsp+0CD8h+var_B98], r8d
0x1012217e2  mov     [rsp+0CD8h+var_A78], rbx
0x1012217ea  xor     edi, edi
0x1012217ec  mov     [rsp+0CD8h+var_B78], rdi
0x1012217f4  mov     [rsp+0CD8h+var_B88], rdi
0x1012217fc  mov     [rsp+0CD8h+var_B68], rdi
0x101221804  mov     esi, edi
0x101221806  mov     [rsp+0CD8h+var_B90], rdi
0x10122180e  mov     [rsp+0CD8h+var_BA8], rdi
0x101221816  mov     [rsp+0CD8h+var_B58], rdi
0x10122181e  mov     [rsp+0CD8h+var_B70], rdi
0x101221826  mov     [rsp+0CD8h+var_B80], rdi
0x10122182e  mov     [rsp+0CD8h+var_BB0], rdi
0x101221836  mov     [rsp+0CD8h+var_AE8], rdi
0x10122183e  mov     [rsp+0CD8h+var_AE0], rdi
0x101221846  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10122184d  cmp     [rax], edi
0x10122184f  jz      short loc_101221869
0x101221851  lea     rcx, [rsp+0CD8h+PerformanceCount]; lpPerformanceCount
0x101221859  call    cs:__imp_QueryPerformanceCounter
0x10122185f  mov     rax, qword ptr [rsp+0CD8h+PerformanceCount]
0x101221867  jmp     short loc_101221871
0x101221869  mov     rax, ds:7FFE0008h
0x101221871  mov     [rsp+0CD8h+var_B60], rax
0x101221879  mov     [rsp+0CD8h+var_C18], sil
0x101221881  mov     [rsp+0CD8h+var_C00], sil
0x101221889  mov     [rsp+0CD8h+var_C17], sil
0x101221891  mov     byte ptr [rsp+0CD8h+var_C08], sil
0x101221899  mov     rdx, gs:58h
0x1012218a2  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1012218a9  mov     ecx, [rax]
0x1012218ab  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1012218b2  mov     eax, [rax]
0x1012218b4  add     rax, [rdx+rcx*8]
0x1012218b8  mov     rax, [rax]
0x1012218bb  mov     rcx, [rax+50h]
0x1012218bf  movzx   eax, word ptr [rcx+8]
0x1012218c3  mov     dword ptr [rsp+0CD8h+PerformanceCount], eax
0x1012218ca  test    r12, r12
0x1012218cd  jz      short loc_1012218DE
0x1012218cf  mov     eax, [r12+1Ch]
0x1012218d4  sub     eax, [r12+28h]
0x1012218d9  cmp     eax, 2
0x1012218dc  jge     short loc_101221904
0x1012218de  mov     rax, cs:off_102ED4430; "sp_execute_external_script"
0x1012218e5  mov     [rsp+0CD8h+var_CB8], rax
0x1012218ea  mov     edx, 3
0x1012218ef  mov     ecx, 0A9h
0x1012218f4  mov     r9d, 12Ch
0x1012218fa  lea     r8d, [rdx+0Dh]
0x1012218fe  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x101221904  mov     r13d, 1
0x10122190a  mov     dword ptr [rsp+0CD8h+var_BC0], r13d
0x101221912  mov     [rsp+0CD8h+var_BF4], r14d
0x10122191a  mov     byte ptr [rsp+0CD8h+var_BDC], sil
0x101221922  mov     [rsp+0CD8h+var_BF8], edi
0x101221929  mov     [rsp+0CD8h+var_B48], rdi
0x101221931  mov     [rsp+0CD8h+var_B50], rdi
0x101221939  mov     [rsp+0CD8h+var_C10], r13b
0x101221941  mov     rcx, cs:__imp_?SOS_OS_OsInfo@@3VOsInfo@@A; OsInfo SOS_OS_OsInfo
0x101221948  call    cs:__imp_?IsLinux@OsInfo@@QEBA?B_NXZ; OsInfo::IsLinux(void)
0x10122194e  mov     ecx, edi
0x101221950  test    al, al
0x101221952  setnz   cl
0x101221955  inc     ecx
0x101221957  mov     [rsp+0CD8h+var_BC8], ecx
0x10122195e  mov     ecx, edi
0x101221960  mov     [rsp+0CD8h+var_BE0], ecx
0x101221967  lea     r15, ?m_szName@CXplOp_ParameterSensitivePredicate@@0QEBDEB; char const * const CXplOp_ParameterSensitivePredicate::m_szName
0x10122196e  test    r14d, r14d
0x101221971  lea     r14d, [r13+1]
0x101221975  jle     loc_101221F66
0x10122197b  lea     rdx, aLanguage_1; "@LANGUAGE"
0x101221982  nop     dword ptr [rax+00h]
0x101221986  nop     word ptr [rax+rax+00000000h]
0x101221990  mov     eax, [r12+28h]
0x101221995  add     eax, ecx
0x101221997  movsxd  rcx, eax
0x10122199a  mov     rax, [r12+10h]
0x10122199f  mov     rsi, [rax+rcx*8]
0x1012219a3  mov     rax, [rsi+18h]
0x1012219a7  movzx   r9d, word ptr [rax+28h]
0x1012219ac  shr     r9d, 1
0x1012219af  mov     dword ptr [rsp+0CD8h+var_CB0], 0Ah
0x1012219b7  mov     [rsp+0CD8h+var_CB8], rdx
0x1012219bc  mov     r8, [rax+20h]
0x1012219c0  xor     edx, edx
0x1012219c2  mov     ecx, r13d
0x1012219c5  call    cs:__imp_?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z; CompareStringWEnglishNoCase(ulong,uchar,wchar_t const *,int,wchar_t const *,int)
0x1012219cb  cmp     eax, 2
0x1012219ce  jnz     loc_10122206D
0x1012219d4  cmp     [rsp+0CD8h+var_B78], 0
0x1012219dd  jnz     loc_101222888
0x1012219e3  mov     [rsp+0CD8h+var_B78], rsi
0x1012219eb  mov     rcx, [rsi+18h]
0x1012219ef  movzx   eax, byte ptr [rcx]
0x1012219f2  movzx   edx, byte ptr [rax+r15+201B6B0h]
0x1012219fb  cmp     byte ptr [rdx+r15+2050448h], 0
0x101221a04  jz      loc_101221FFB
0x101221a0a  mov     eax, 0FFFFh
0x101221a0f  cmp     [rcx+10h], ax
0x101221a13  jz      loc_101221FFB
0x101221a19  cmp     byte ptr [rdx+r15+2AF7BF8h], 0
0x101221a22  jnz     loc_101221FFB
0x101221a28  mov     rax, [rsi+8]
0x101221a2c  movsxd  r12, dword ptr [rax+10h]
0x101221a30  cmp     r12d, 100h
0x101221a37  ja      loc_101221FFB
0x101221a3d  cmp     byte ptr [rax], 3
0x101221a40  jz      loc_101221FFB
0x101221a46  mov     r15, [rax+8]
0x101221a4a  mov     rbx, r12
0x101221a4d  shr     rbx, 1
0x101221a50  mov     dword ptr [rsp+0CD8h+var_CB0], r14d
0x101221a55  lea     rax, aR; "R"
0x101221a5c  mov     [rsp+0CD8h+var_CB8], rax
0x101221a61  mov     r9d, ebx
0x101221a64  mov     r8, r15
0x101221a67  xor     edx, edx
0x101221a69  mov     ecx, r13d
0x101221a6c  call    cs:__imp_?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z; CompareStringWEnglishNoCase(ulong,uchar,wchar_t const *,int,wchar_t const *,int)
0x101221a72  cmp     eax, 2
0x101221a75  jnz     short loc_101221A8F
0x101221a77  mov     dword ptr [rsp+0CD8h+var_BC0], r13d
0x101221a7f  mov     esi, r13d
0x101221a82  mov     [rsp+0CD8h+var_BF8], r13d
0x101221a8a  jmp     loc_101221D23
0x101221a8f  mov     dword ptr [rsp+0CD8h+var_CB0], 7
0x101221a97  lea     rax, aPython; "Python"
0x101221a9e  mov     [rsp+0CD8h+var_CB8], rax
0x101221aa3  mov     r9d, ebx
0x101221aa6  mov     r8, r15
0x101221aa9  xor     edx, edx
0x101221aab  mov     ecx, r13d
0x101221aae  call    cs:__imp_?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z; CompareStringWEnglishNoCase(ulong,uchar,wchar_t const *,int,wchar_t const *,int)
0x101221ab4  cmp     eax, 2
0x101221ab7  jnz     short loc_101221AD1
0x101221ab9  mov     dword ptr [rsp+0CD8h+var_BC0], r14d
0x101221ac1  mov     esi, r14d
0x101221ac4  mov     [rsp+0CD8h+var_BF8], r14d
0x101221acc  jmp     loc_101221D23
0x101221ad1  cmp     cs:byte_102EDCC33, 0
0x101221ad8  jz      short loc_101221AEE
0x101221ada  mov     rax, cs:qword_102ECFB10
0x101221ae1  test    byte ptr [rax+53Eh], 4
0x101221ae8  jnz     short loc_101221AEE
0x101221aea  mov     al, 1
0x101221aec  jmp     short loc_101221AF0
0x101221aee  xor     al, al
0x101221af0  test    al, al
0x101221af2  jz      loc_101221CF5
0x101221af8  mov     dword ptr [rsp+0CD8h+var_BC0], 3
0x101221b03  mov     byte ptr [rsp+0CD8h+var_C08], 1
0x101221b0b  mov     rdx, gs:58h
0x101221b14  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101221b1b  mov     ecx, [rax]
0x101221b1d  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101221b24  mov     ebx, [rax]
0x101221b26  add     rbx, [rdx+rcx*8]
0x101221b2a  mov     rax, [rbx+100h]
0x101221b31  test    rax, rax
0x101221b34  jnz     short loc_101221B45
0x101221b36  xor     ecx, ecx
0x101221b38  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101221b3e  mov     rax, [rbx+100h]
0x101221b45  mov     r14, [rax+3E8h]
0x101221b4c  mov     rcx, [rsp+0CD8h+var_BE8]
0x101221b54  mov     rcx, [rcx+90h]
0x101221b5b  test    rcx, rcx
0x101221b5e  jz      short loc_101221B6E
0x101221b60  mov     rax, [rcx]
0x101221b63  call    qword ptr [rax+1B0h]
0x101221b69  test    rax, rax
0x101221b6c  jnz     short loc_101221BB5
0x101221b6e  mov     rbx, [rsp+0CD8h+var_B48]
0x101221b76  test    rbx, rbx
0x101221b79  jnz     short loc_101221B95
0x101221b7b  mov     rax, cs:__imp_?g_pAutoXactFactory@@3PEAVIAutoXactFactory@@EA; IAutoXactFactory * g_pAutoXactFactory
0x101221b82  mov     rcx, [rax]
0x101221b85  mov     rax, [rcx]
0x101221b88  call    qword ptr [rax]
0x101221b8a  mov     rbx, rax
0x101221b8d  mov     [rsp+0CD8h+var_B48], rax
0x101221b95  mov     rax, [rbx]
0x101221b98  xor     r9d, r9d
0x101221b9b  lea     r8d, [r9+2Eh]
0x101221b9f  lea     rdx, aSpexecuteexter; "SpExecuteExternalScript"
0x101221ba6  mov     rcx, rbx
0x101221ba9  call    qword ptr [rax+10h]
0x101221bac  mov     rax, [rbx]
0x101221baf  mov     rcx, rbx
0x101221bb2  call    qword ptr [rax+48h]
0x101221bb5  mov     r9d, 100Eh
0x101221bbb  lea     r8, aSqlNtdbmsMsqlP_21; "sql\\ntdbms\\msql\\proc\\specproc.cpp"
0x101221bc2  mov     rdx, rax
0x101221bc5  mov     rcx, r14
0x101221bc8  mov     rax, cs:__imp_?g_metadataFactory@@3UMetadataFactory@@A; MetadataFactory g_metadataFactory
0x101221bcf  call    qword ptr [rax]
0x101221bd1  mov     rbx, rax
0x101221bd4  mov     rcx, [rsp+0CD8h+var_B50]
0x101221bdc  cmp     rcx, rax
0x101221bdf  jz      short loc_101221BEF
0x101221be1  test    rcx, rcx
0x101221be4  jz      short loc_101221BEF
0x101221be6  mov     r8, [rcx]
0x101221be9  mov     edx, r13d
0x101221bec  call    qword ptr [r8]
0x101221bef  mov     [rsp+0CD8h+var_B50], rbx
0x101221bf7  mov     rax, [rbx]
0x101221bfa  mov     dword ptr [rsp+0CD8h+var_CB0], edi
0x101221bfe  mov     dword ptr [rsp+0CD8h+var_CB8], edi
0x101221c02  xor     r9d, r9d
0x101221c05  xor     r8d, r8d
0x101221c08  mov     edx, dword ptr [rsp+0CD8h+PerformanceCount]
0x101221c0f  mov     rcx, rbx
0x101221c12  call    qword ptr [rax+38h]
0x101221c15  mov     rbx, rax
0x101221c18  mov     rax, [rsp+0CD8h+var_BE8]
0x101221c20  mov     rax, [rax+78h]
0x101221c24  mov     rcx, [rax+108h]
0x101221c2b  mov     r10, [rcx]
0x101221c2e  mov     r9d, r13d
0x101221c31  mov     r8d, r13d
0x101221c34  mov     edx, dword ptr [rsp+0CD8h+PerformanceCount]
0x101221c3b  call    qword ptr [r10+160h]
0x101221c42  mov     r10, [rbx]
0x101221c45  xor     r9d, r9d
0x101221c48  xor     r8d, r8d
0x101221c4b  mov     edx, eax
0x101221c4d  mov     rcx, rbx
0x101221c50  call    qword ptr [r10+0E8h]
0x101221c57  mov     [rsp+0CD8h+var_A60], r15
0x101221c5f  mov     [rsp+0CD8h+var_A58], r12d
0x101221c67  mov     r10, [rax]
0x101221c6a  xor     r9d, r9d
0x101221c6d  xor     r8d, r8d
0x101221c70  lea     rdx, [rsp+0CD8h+var_A60]
0x101221c78  mov     rcx, rax
0x101221c7b  call    qword ptr [r10+1B0h]
0x101221c82  mov     rbx, rax
0x101221c85  mov     r14d, 2
0x101221c8b  test    rax, rax
0x101221c8e  jnz     short loc_101221CB5
0x101221c90  mov     rcx, [rsi+8]
0x101221c94  mov     qword ptr [rsp+0CD8h+var_CB0], r15
0x101221c99  mov     eax, [rcx+10h]
0x101221c9c  mov     dword ptr [rsp+0CD8h+var_CB8], eax
0x101221ca0  mov     r9d, r14d
0x101221ca3  lea     edx, [rbx+7]
0x101221ca6  mov     ecx, 186h
0x101221cab  lea     r8d, [rbx+10h]
0x101221caf  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x101221cb5  mov     rax, [rbx]
0x101221cb8  mov     rcx, rbx
0x101221cbb  call    qword ptr [rax+10h]
0x101221cbe  mov     esi, eax
0x101221cc0  mov     [rsp+0CD8h+var_BF8], eax
0x101221cc7  mov     r10, [rbx]
0x101221cca  mov     r9d, 20Ah
0x101221cd0  lea     r8, [rsp+0CD8h+var_258]
0x101221cd8  mov     edx, [rsp+0CD8h+var_BC8]
0x101221cdf  mov     rcx, rbx
0x101221ce2  call    qword ptr [r10+30h]
0x101221ce6  test    eax, eax
0x101221ce8  jnz     short loc_101221D23
0x101221cea  xor     bl, bl
0x101221cec  mov     [rsp+0CD8h+var_C10], bl
0x101221cf3  jmp     short loc_101221D2B
0x101221cf5  mov     rax, [rsi+8]
0x101221cf9  mov     qword ptr [rsp+0CD8h+var_CB0], r15
0x101221cfe  mov     eax, [rax+10h]
0x101221d01  mov     dword ptr [rsp+0CD8h+var_CB8], eax
0x101221d05  mov     r9d, r13d
0x101221d08  mov     edx, 7
0x101221d0d  mov     ecx, 186h
0x101221d12  lea     r8d, [rdx+9]
0x101221d16  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x101221d1c  mov     esi, [rsp+0CD8h+var_BF8]
0x101221d23  movzx   ebx, [rsp+0CD8h+var_C10]
  ... truncated ...
```
