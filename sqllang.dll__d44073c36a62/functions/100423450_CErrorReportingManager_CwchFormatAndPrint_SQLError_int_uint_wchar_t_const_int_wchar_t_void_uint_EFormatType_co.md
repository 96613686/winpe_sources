# CErrorReportingManager::CwchFormatAndPrint(SQLError *,int,uint,wchar_t const *,int,wchar_t *,void *,uint,EFormatType const *,char *)

- ea: `0x100423450`
- end: `0x100423ca9`
- name: `?CwchFormatAndPrint@CErrorReportingManager@@UEAAHPEAVSQLError@@HIPEB_WHPEA_WPEAXIPEBW4EFormatType@@PEAD@Z`
- size: `2137`
- prototype: `int(CErrorReportingManager *__hidden this, struct SQLError *, int, unsigned int, const wchar_t *, int, wchar_t *, void *, unsigned int, const enum EFormatType *, char *)`
- caller_count: `3`
- callee_count: `18`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x10167ba50`
- `0x10167bf80`
- `0x10167c090`

## callees

- `0x1004012d0`
- `0x100401340`
- `0x100422850`
- `0x100422fb0`
- `0x100423170`
- `0x100423450`
- `0x100423cb0`
- `0x100424480`
- `0x100424770`
- `0x100424890`
- `0x100425090`
- `0x1008d40b0`
- `0x1016755e0`
- `0x101675fd0`
- `0x101676f60`
- `0x101677670`
- `0x101677f80`
- `0x101678370`

## import_xrefs

- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x100423789`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10054f063`
- `sqldk!?hdl_backout@@YAHHHHHPEAD@Z` at `0x1004236a6`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10042382b`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101678c07`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10042382b`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101678c07`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1016795c5`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1016795c5`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1004238fe`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10167908d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10167915f`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1004238fe`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10167908d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10167915f`
- `sqldk!SystemThread_TlsIndex` at `0x10042349a`
- `sqldk!SystemThread_TlsIndex` at `0x1004234ec`
- `sqldk!SystemThread_TlsIndex` at `0x1004237da`
- `sqldk!SystemThread_TlsIndex` at `0x1004238b5`
- `sqldk!SystemThread_TlsIndex` at `0x100423c03`
- `sqldk!SystemThread_TlsIndex` at `0x101678bab`
- `sqldk!SystemThread_TlsIndex` at `0x101679039`
- `sqldk!SystemThread_TlsIndex` at `0x10167910b`
- `sqldk!SystemThread_TlsOffset` at `0x1004234a4`
- `sqldk!SystemThread_TlsOffset` at `0x1004234f5`
- `sqldk!SystemThread_TlsOffset` at `0x1004237e3`
- `sqldk!SystemThread_TlsOffset` at `0x1004238be`
- `sqldk!SystemThread_TlsOffset` at `0x100423c0c`
- `sqldk!SystemThread_TlsOffset` at `0x101678bb4`
- `sqldk!SystemThread_TlsOffset` at `0x101679042`
- `sqldk!SystemThread_TlsOffset` at `0x101679114`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100423890`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100423c51`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100423c62`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101678c6c`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101678d73`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101678d84`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101678e80`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101678e91`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101678fd3`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101678fe4`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101679311`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101679322`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1016795ed`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1016795fe`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100423890`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100423c51`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100423c62`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101678c6c`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101678d73`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101678d84`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101678e80`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101678e91`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101678fd3`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101678fe4`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101679311`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101679322`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1016795ed`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1016795fe`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101678b07`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101678b3e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101678b84`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101678bcf`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101678c82`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10167905d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10167912f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016795b2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101678b07`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101678b3e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101678b84`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101678bcf`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101678c82`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10167905d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10167912f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016795b2`
- `sqldk!??_V@YAXPEAX@Z` at `0x100423914`
- `sqldk!??_V@YAXPEAX@Z` at `0x100423bdb`
- `sqldk!??_V@YAXPEAX@Z` at `0x100423be5`
- `sqldk!??_V@YAXPEAX@Z` at `0x100423c71`
- `sqldk!??_V@YAXPEAX@Z` at `0x101678d37`
- `sqldk!??_V@YAXPEAX@Z` at `0x101678d43`
- `sqldk!??_V@YAXPEAX@Z` at `0x101678d8e`
- `sqldk!??_V@YAXPEAX@Z` at `0x101678e46`
- `sqldk!??_V@YAXPEAX@Z` at `0x101678e50`
- `sqldk!??_V@YAXPEAX@Z` at `0x101678e9b`
- `sqldk!??_V@YAXPEAX@Z` at `0x101678f99`
- `sqldk!??_V@YAXPEAX@Z` at `0x101678fa3`
- `sqldk!??_V@YAXPEAX@Z` at `0x101678fee`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016790a3`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016790fc`
- `sqldk!??_V@YAXPEAX@Z` at `0x101679175`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016792d7`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016792e1`
- `sqldk!??_V@YAXPEAX@Z` at `0x10167932c`
- `sqldk!??_V@YAXPEAX@Z` at `0x10167960d`
- `sqldk!??_V@YAXPEAX@Z` at `0x100423914`
- `sqldk!??_V@YAXPEAX@Z` at `0x100423bdb`
- `sqldk!??_V@YAXPEAX@Z` at `0x100423be5`
- `sqldk!??_V@YAXPEAX@Z` at `0x100423c71`
- `sqldk!??_V@YAXPEAX@Z` at `0x101678d37`
- `sqldk!??_V@YAXPEAX@Z` at `0x101678d43`
- `sqldk!??_V@YAXPEAX@Z` at `0x101678d8e`
- `sqldk!??_V@YAXPEAX@Z` at `0x101678e46`
- `sqldk!??_V@YAXPEAX@Z` at `0x101678e50`
- `sqldk!??_V@YAXPEAX@Z` at `0x101678e9b`
- `sqldk!??_V@YAXPEAX@Z` at `0x101678f99`
- `sqldk!??_V@YAXPEAX@Z` at `0x101678fa3`
- `sqldk!??_V@YAXPEAX@Z` at `0x101678fee`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016790a3`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016790fc`
- `sqldk!??_V@YAXPEAX@Z` at `0x101679175`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016792d7`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016792e1`
- `sqldk!??_V@YAXPEAX@Z` at `0x10167932c`
- `sqldk!??_V@YAXPEAX@Z` at `0x10167960d`
- `sqldk!?ex_dump_trigger@@YAHKHPEAHH@Z` at `0x1004239ef`
- `sqldk!?ex_dump_trigger@@YAHKHPEAHH@Z` at `0x1004239ef`
- `sqlmin!?IncrementCounterInstanceValue@PerfmonManager@@QEAAHKK_JKPEA_K@Z` at `0x1004237b7`
- `sqlmin!?IncrementCounterInstanceValue@PerfmonManager@@QEAAHKK_JKPEA_K@Z` at `0x1004237b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
__int64 __fastcall CErrorReportingManager::CwchFormatAndPrint(
        CErrorReportingManager *this,
        struct SQLError *a2,
        unsigned int a3,
        unsigned int a4,
        wchar_t *a5,
        int a6,
        wchar_t *a7,
        void *a8,
        unsigned int a9,
        const enum EFormatType *a10,
        char *a11)
{
  __int64 v14; // rbx
  __int64 v15; // rdx
  int v16; // ecx
  __int64 v17; // rbx
  __int64 v18; // rcx
  BOOL v19; // r12d
  void *v20; // rbx
  __int16 v21; // ax
  unsigned int v22; // r14d
  wchar_t *v23; // rsi
  __int64 v24; // rcx
  void *v25; // rdi
  int v26; // eax
  __int64 v27; // rbx
  __int64 v28; // rdx
  struct CFormattedParams *v29; // rax
  struct CFormattedParams *v30; // rbx
  int i; // ecx
  __int64 v32; // rbx
  __int64 v33; // rdx
  unsigned int v34; // ecx
  const enum EFormatType *v35; // r13
  bool v36; // cl
  struct CFormattedParams *v37; // rax
  int v38; // ecx
  CErrorReportingManager *v39; // rcx
  CErrorReportingManager *v40; // r12
  __int64 v41; // rbx
  struct Worker *v42; // rcx
  int v44; // ecx
  __int64 v45; // rbx
  __int64 v46; // rdx
  struct CFormattedParams *v47; // rax
  struct CFormattedParams *v48; // rbx
  int j; // ecx
  int v50; // ecx
  int v51; // ecx
  __int64 v52; // rbx
  __int64 v53; // rdx
  wchar_t *v54; // rbx
  __int64 v55; // rbx
  __int64 v56; // rdx
  const wchar_t *v57; // rcx
  int v58; // edx
  char *v59; // r14
  const wchar_t *v60; // rcx
  char v61; // cl
  struct CFormattedParams *v62; // rax
  int v63; // ecx
  struct CFormattedParams *v64; // [rsp+70h] [rbp-468h]
  bool v65; // [rsp+78h] [rbp-460h] BYREF
  int v66; // [rsp+7Ch] [rbp-45Ch]
  struct CFormattedParams *v67; // [rsp+80h] [rbp-458h]
  unsigned __int16 v68; // [rsp+88h] [rbp-450h]
  int v69; // [rsp+8Ch] [rbp-44Ch]
  int v70; // [rsp+90h] [rbp-448h] BYREF
  int v71; // [rsp+94h] [rbp-444h] BYREF
  int v72; // [rsp+98h] [rbp-440h]
  int v73; // [rsp+9Ch] [rbp-43Ch]
  int v74; // [rsp+A0h] [rbp-438h]
  unsigned int v75; // [rsp+A4h] [rbp-434h]
  unsigned int v76; // [rsp+A8h] [rbp-430h]
  int v77; // [rsp+ACh] [rbp-42Ch] BYREF
  int v78; // [rsp+B0h] [rbp-428h] BYREF
  wchar_t *v79; // [rsp+B8h] [rbp-420h]
  int v80; // [rsp+C0h] [rbp-418h]
  __int64 v81; // [rsp+C8h] [rbp-410h]
  void *v82; // [rsp+D0h] [rbp-408h]
  int v83; // [rsp+D8h] [rbp-400h]
  int v84; // [rsp+DCh] [rbp-3FCh]
  void *v85; // [rsp+E0h] [rbp-3F8h]
  int v86; // [rsp+E8h] [rbp-3F0h]
  int v87; // [rsp+ECh] [rbp-3ECh]
  int v88; // [rsp+F0h] [rbp-3E8h] BYREF
  int v89; // [rsp+F4h] [rbp-3E4h]
  __int64 v90; // [rsp+F8h] [rbp-3E0h] BYREF
  char v91; // [rsp+100h] [rbp-3D8h]
  int v92; // [rsp+108h] [rbp-3D0h]
  int v93; // [rsp+110h] [rbp-3C8h]
  __m128i si128; // [rsp+118h] [rbp-3C0h] BYREF
  int v95; // [rsp+128h] [rbp-3B0h]
  __m128i v96; // [rsp+130h] [rbp-3A8h] BYREF
  int v97; // [rsp+140h] [rbp-398h]
  _BYTE v98[40]; // [rsp+148h] [rbp-390h] BYREF
  struct CFormattedParams *v99; // [rsp+170h] [rbp-368h]
  struct IMemObj *v100; // [rsp+178h] [rbp-360h]
  struct CFormattedParams *v101; // [rsp+180h] [rbp-358h]
  __int64 v102; // [rsp+188h] [rbp-350h]
  struct IMemObj *v103; // [rsp+190h] [rbp-348h]
  char v104[8]; // [rsp+1B0h] [rbp-328h] BYREF
  int v105; // [rsp+1B8h] [rbp-320h]
  int v106; // [rsp+1C0h] [rbp-318h]
  char **v107; // [rsp+1C8h] [rbp-310h]
  char *v108; // [rsp+1D0h] [rbp-308h]
  __int64 v109; // [rsp+1D8h] [rbp-300h]
  char *v110; // [rsp+1E0h] [rbp-2F8h] BYREF
  int v111; // [rsp+1E8h] [rbp-2F0h]
  int v112; // [rsp+1ECh] [rbp-2ECh]
  __int64 v113; // [rsp+1F0h] [rbp-2E8h]
  int v114; // [rsp+1F8h] [rbp-2E0h]
  int v115; // [rsp+1FCh] [rbp-2DCh]
  char v116; // [rsp+200h] [rbp-2D8h] BYREF
  __int64 v117; // [rsp+400h] [rbp-D8h]
  __int64 v118; // [rsp+408h] [rbp-D0h]
  char v119; // [rsp+410h] [rbp-C8h] BYREF
  struct SQLError *v120; // [rsp+430h] [rbp-A8h]
  unsigned int v121; // [rsp+438h] [rbp-A0h]
  unsigned int v122; // [rsp+43Ch] [rbp-9Ch]
  bool v123; // [rsp+440h] [rbp-98h]
  void *v124; // [rsp+448h] [rbp-90h]
  int v125; // [rsp+450h] [rbp-88h]
  char v126; // [rsp+454h] [rbp-84h]
  struct CFormattedParams *v127; // [rsp+458h] [rbp-80h]
  BOOL v128; // [rsp+460h] [rbp-78h]
  char *v129; // [rsp+468h] [rbp-70h]
  char *v130; // [rsp+470h] [rbp-68h]
  __int16 v131; // [rsp+478h] [rbp-60h]
  char v133; // [rsp+4E8h] [rbp+10h]

  v102 = -2;
  v80 = 0;
  v14 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v15 = *(_QWORD *)(v14 + 256);
  if ( !v15 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v15 = *(_QWORD *)(v14 + 256);
  }
  v81 = v15;
  v16 = *(_DWORD *)a2;
  if ( *((_DWORD *)a2 + 4) != 1 )
    v16 = (unsigned __int16)*(_DWORD *)a2;
  if ( v16 == 701 )
  {
    v44 = *(_DWORD *)(v15 + 616);
    v80 = v44 & 0x20 ^ 0x20;
    *(_DWORD *)(v15 + 616) = v44 | 0x20;
  }
  v17 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v18 = *(_QWORD *)(v17 + 256);
  if ( !v18 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v18 = *(_QWORD *)(v17 + 256);
  }
  v19 = (*(_BYTE *)(v18 + 616) & 0x40) != 0 || !*((_DWORD *)this + 10) || (*(_DWORD *)(v18 + 616) & 0x4000) != 0;
  v20 = 0;
  v82 = 0;
  v64 = 0;
  v67 = 0;
  v21 = (*(__int64 (__fastcall **)(CErrorReportingManager *, _QWORD))(*(_QWORD *)this + 120LL))(this, 0);
  v105 = 0x20000;
  v106 = 0;
  v107 = &v110;
  v108 = &v116;
  v117 = 0;
  v109 = 0;
  v118 = 0;
  v110 = &v119;
  v111 = 27;
  v112 = 1;
  v113 = 0;
  v114 = 0;
  v115 = 7;
  v120 = a2;
  v121 = a3;
  v22 = a4;
  v122 = a4;
  v123 = 0;
  v23 = 0;
  v124 = 0;
  v125 = 0;
  v126 = 0;
  v127 = 0;
  v128 = v19;
  v129 = (char *)this + 1024;
  v130 = (char *)this + 1040;
  v131 = v21;
  v24 = *(unsigned int *)a2;
  if ( *((_DWORD *)a2 + 4) != 1 )
    v24 = (unsigned __int16)v24;
  v83 = anonymous_namespace_::FHideUserDataParameters(v24);
  if ( !v83 || (v133 = 1, (*((_BYTE *)qword_102ECFB10 + 1294) & 4) == 0) )
    v133 = 0;
  v76 = 0;
  ExcHandler::ExcHandler((ExcHandler *)v98, 0, 0, 0, (int (*)(int, int, int, int, char *))hdl_backout, 0);
  v69 = a9 & 1;
  v74 = v69;
  v75 = (a9 >> 1) & 1;
  v66 = v75;
  v84 = (a9 >> 2) & 1;
  v89 = (a9 >> 4) & 1;
  v71 = 0;
  v78 = 0;
  v88 = 0;
  v25 = 0;
  v85 = 0;
  v70 = 0;
  v79 = 0;
  v77 = 0;
  v68 = (*(__int64 (__fastcall **)(CErrorReportingManager *, _QWORD))(*(_QWORD *)this + 120LL))(this, 0);
  v72 = v69;
  v73 = v69;
  v26 = *((_DWORD *)a2 + 1);
  if ( v26 == 10 )
  {
    if ( CommonGlobalState::m_PerfCountersEnabled )
      PerfmonManager::IncrementCounterInstanceValue((PerfmonManager *)qword_102ECFB00, 0xEu, 0, 1, 1u, 0);
  }
  else if ( v26 <= 18 && CommonGlobalState::m_PerfCountersEnabled )
  {
    PerfmonManager::IncrementCounterInstanceValue((PerfmonManager *)qword_102ECFB00, 0xEu, 0, 1, 2u, 0);
  }
  if ( !v19 )
  {
    v93 = 4864;
    v27 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v28 = *(_QWORD *)(v27 + 256);
    if ( !v28 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v28 = *(_QWORD *)(v27 + 256);
    }
    v103 = *(struct IMemObj **)(v28 + 1000);
    v29 = (struct CFormattedParams *)operator new(
                                       0x1248u,
                                       v103,
                                       1,
                                       "sql\\ntdbms\\msql\\utils\\errorreport.cpp",
                                       4864,
                                       3u);
    v30 = v29;
    v99 = v29;
    if ( v29 )
    {
      *((_QWORD *)v29 + 525) = v29;
      *((_DWORD *)v29 + 1052) = 0;
      *((_DWORD *)v29 + 1154) = 0;
      *((_DWORD *)v29 + 1155) = 0;
      for ( i = 0; ; ++i )
      {
        v86 = i;
        if ( i >= 50 )
          break;
        *((_BYTE *)v29 + i + 4624) = 0;
      }
    }
    else
    {
      v30 = 0;
    }
    if ( v30 )
      operator delete(0, 0x1248u);
    v64 = v30;
    if ( v133 )
    {
      v92 = 4869;
      v45 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v46 = *(_QWORD *)(v45 + 256);
      if ( !v46 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v46 = *(_QWORD *)(v45 + 256);
      }
      v100 = *(struct IMemObj **)(v46 + 1000);
      v47 = (struct CFormattedParams *)operator new(
                                         0x1248u,
                                         v100,
                                         1,
                                         "sql\\ntdbms\\msql\\utils\\errorreport.cpp",
                                         4869,
                                         3u);
      v48 = v47;
      v101 = v47;
      if ( v47 )
      {
        *((_QWORD *)v47 + 525) = v47;
        *((_DWORD *)v47 + 1052) = 0;
        *((_DWORD *)v47 + 1154) = 0;
        *((_DWORD *)v47 + 1155) = 0;
        for ( j = 0; ; ++j )
        {
          v87 = j;
          if ( j >= 50 )
            break;
          *((_BYTE *)v47 + j + 4624) = 0;
        }
      }
      else
      {
        v48 = 0;
      }
      if ( v67 != v48 )
        operator delete(v67, 0x1248u);
      v67 = v48;
    }
    v32 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v33 = *(_QWORD *)(v32 + 256);
    if ( !v33 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v33 = *(_QWORD *)(v32 + 256);
    }
    v25 = operator new[](
            0x1000u,
            *(struct IMemObj **)(v33 + 1000),
            1,
            "sql\\ntdbms\\msql\\utils\\errorreport.cpp",
            4874,
            3u);
    if ( v85 != v25 )
      operator delete[](v85);
    v85 = v25;
    if ( !v64 || v133 && !v67 || (v19 = 0, !v25) )
      v19 = 1;
    v69 = v74;
    v72 = v73;
    v23 = v79;
    v20 = v82;
    v22 = a4;
  }
  if ( *((_DWORD *)a2 + 4) != 1 )
  {
    if ( !(unsigned int)FGetMsgFormatSpecs(a2, &v71, &v78, &v88, (wchar_t *)v25, v25 != 0 ? 0x800 : 0, &v70) )
    {
      if ( !v75 )
      {
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        v95 = 0;
        v50 = *(_DWORD *)a2;
        if ( *((_DWORD *)a2 + 4) != 1 )
          v50 = (unsigned __int16)*(_DWORD *)a2;
        IErrorReportingManager::CwchCallFormatAndPrint(
          this,
          (struct SQLError *)&si128,
          2,
          1u,
          0,
          0,
          0,
          (void *)0xFFFFFFFFFFFFFFFFLL,
          3u,
          0,
          v50,
          *((_DWORD *)a2 + 1),
          *((_DWORD *)a2 + 3));
      }
      goto LABEL_135;
    }
    if ( (a9 & 8) == 0 )
    {
      v34 = *(_DWORD *)a2;
      if ( *((_DWORD *)a2 + 4) != 1 )
        v34 = (unsigned __int16)*(_DWORD *)a2;
      if ( ex_dump_trigger(v34, *((_DWORD *)a2 + 1), 0, -1) )
        CErrorReportingManager::GenerateErrorDump(a2);
    }
  }
  if ( v19 )
    goto LABEL_142;
  if ( *((_DWORD *)a2 + 4) != 1 )
  {
    v35 = a10;
    v19 = FFormatParams((const wchar_t *)v25, v70, 0, 0, 0, 0, v69, v66, v72, v83, v64, a10, a11) == 0;
    v36 = v133 && (unsigned int)FFormatParams((const wchar_t *)v25, v70, 0, 0, 0, 0, v69, v66, v72, 0, v67, a10, a11);
    if ( !v19 )
    {
      v37 = v64;
      if ( v36 )
        v37 = v67;
      v127 = v37;
      goto LABEL_55;
    }
    if ( !v75 )
    {
LABEL_135:
      operator delete[](v23);
      operator delete[](v25);
      ExcHandler::~ExcHandler((ExcHandler *)v98);
      ErrorReportedAutoPublish::Publish((ErrorReportedAutoPublish *)v104);
      operator delete(v67, 0x1248u);
      operator delete(v64, 0x1248u);
      operator delete[](v20);
      *(_DWORD *)(v81 + 616) &= ~v80;
      return 0xFFFFFFFFLL;
    }
    goto LABEL_55;
  }
  if ( !a5 )
  {
    if ( !(unsigned int)CErrorReportingManager::FGetUserMsg(a2, &v71, (wchar_t *)v25, 2048, &v70, 0x409u) )
    {
      if ( !v75 )
      {
        v96 = _mm_load_si128((const __m128i *)&_xmm);
        v97 = 0;
        v51 = *(_DWORD *)a2;
        if ( *((_DWORD *)a2 + 4) != 1 )
          v51 = (unsigned __int16)*(_DWORD *)a2;
        IErrorReportingManager::CwchCallFormatAndPrint(
          this,
          (struct SQLError *)&v96,
          2,
          1u,
          0,
          0,
          0,
          (void *)0xFFFFFFFFFFFFFFFFLL,
          3u,
          0,
          v51,
          *((_DWORD *)a2 + 1),
          *((_DWORD *)a2 + 3));
      }
      goto LABEL_135;
    }
    if ( v68 != 1033 )
    {
      v52 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v53 = *(_QWORD *)(v52 + 256);
      if ( !v53 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v53 = *(_QWORD *)(v52 + 256);
      }
      v54 = (wchar_t *)operator new[](
                         0x1000u,
                         *(struct IMemObj **)(v53 + 1000),
                         1,
                         "sql\\ntdbms\\msql\\utils\\errorreport.cpp",
                         4998,
                         3u);
      if ( v79 != v54 )
        operator delete[](v79);
      v79 = v54;
      if ( v54 && !(unsigned int)CErrorReportingManager::FGetUserMsg(a2, &v71, v54, 2048, &v77, v68) )
      {
        v79 = 0;
        operator delete[](v54);
      }
    }
  }
  v55 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v56 = *(_QWORD *)(v55 + 256);
  if ( !v56 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v56 = *(_QWORD *)(v55 + 256);
  }
  v20 = operator new[](
          0x1002u,
          *(struct IMemObj **)(v56 + 1000),
          1,
          "sql\\ntdbms\\msql\\utils\\errorreport.cpp",
          5013,
          3u);
  if ( v82 != v20 )
    operator delete[](v82);
  v82 = v20;
  v25 = v85;
  v23 = v79;
  if ( !v20 )
  {
    v19 = 1;
    v22 = a4;
LABEL_142:
    v35 = a10;
    goto LABEL_55;
  }
  v57 = (const wchar_t *)v85;
  if ( a5 )
    v57 = a5;
  v58 = v70;
  if ( a5 )
    v58 = a6;
  v78 = v58;
  v59 = a11;
  v35 = a10;
  v19 = FFormatParams(v57, v58, v79, v77, (wchar_t *)v20, 2049, v74, v66, v73, v83, v64, a10, a11) == 0;
  if ( !v133 )
    goto LABEL_136;
  v60 = (const wchar_t *)v25;
  if ( a5 )
    v60 = a5;
  if ( (unsigned int)FFormatParams(v60, v78, v23, v77, (wchar_t *)v20, 2049, v74, v66, v73, 0, v67, a10, v59) )
    v61 = 1;
  else
LABEL_136:
    v61 = 0;
  if ( v19 )
  {
    if ( !v75 )
      goto LABEL_135;
  }
  else
  {
    v124 = v20;
    v125 = 2049;
    v62 = v64;
    if ( v61 )
      v62 = v67;
    v127 = v62;
  }
  v22 = a4;
LABEL_55:
  if ( (v22 & 0x81) != 0 )
  {
    if ( v64 )
      v38 = *((_DWORD *)v64 + 1052);
    else
      v38 = 0;
    v22 |= CErrorReportingManager::EGetDestination(this, a2, v71, v66, v35, &a11, v38);
    if ( (v22 & 0x80u) != 0 )
      v22 &= ~2u;
    v122 = v22;
  }
  else if ( (v22 & 0x40) != 0 )
  {
    v22 &= ~0x40u;
    v63 = v64 ? *((_DWORD *)v64 + 1052) : 0;
    if ( (CErrorReportingManager::EGetDestination(this, a2, v71, v66, v35, &a11, v63) & 2) != 0 )
      v22 |= 2u;
  }
  v90 = 0;
  v91 = 0;
  CAutoInterceptErrorForTsqlCatch::Initialize((CAutoInterceptErrorForTsqlCatch *)&v90, a2, &v65);
  v123 = v65;
  if ( (v22 & 2) != 0 )
    CErrorReportingManager::SetError(v39, a2);
  if ( v19 )
  {
    v76 = CErrorReportingManager::TersePrintError(this, a2, v22, v84, a3, a8, a7, 0x800u, a11);
  }
  else
  {
    if ( (v22 & 0x10) == 0 || (v76 = CErrorReportingManager::SendErrorToBuffer(this, a2, a7, (wchar_t *)v20, v64)) != 0 )
    {
      v40 = this;
    }
    else
    {
      v40 = this;
      v76 = CErrorReportingManager::TersePrintError(
              this,
              a2,
              0x10u,
              1,
              0,
              (void *)0xFFFFFFFFFFFFFFFFLL,
              a7,
              0x800u,
              a11);
    }
    if ( (v22 & 2) != 0 )
      CErrorReportingManager::SendErrorToUser(v40, a2, v64, (wchar_t *)v20);
    if ( (v22 & 0x24) != 0 )
      CErrorReportingManager::SendErrorToErrLog(v40, a2, v22 & 0x24, v84, v89, 0, a3, v64, (wchar_t *)v20, a8);
    if ( (v22 & 8) != 0 )
      CErrorReportingManager::SendErrorToEventLog(v40, a2, a3, v64, (wchar_t *)v20);
  }
  if ( v90 )
    *(_BYTE *)(v90 + 296) = v91;
  operator delete[](v23);
  operator delete[](v25);
  ExcHandler::~ExcHandler((ExcHandler *)v98);
  v41 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v42 = *(struct Worker **)(v41 + 256);
  if ( !v42 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v42 = *(struct Worker **)(v41 + 256);
  }
  if ( *((_DWORD *)v42 + 139) )
    ExceptionPostCatchActions(v42);
  ErrorReportedAutoPublish::Publish((ErrorReportedAutoPublish *)v104);
  operator delete(v67, 0x1248u);
  operator delete(v64, 0x1248u);
  operator delete[](v82);
  *(_DWORD *)(v81 + 616) &= ~v80;
  return v76;
}

```

## disassembly

```asm
0x100423450  mov     [rsp+arg_18], r9d
0x100423455  mov     [rsp+arg_10], r8d
0x10042345a  mov     [rsp+arg_0], rcx
0x10042345f  push    rbx
0x100423460  push    rsi
0x100423461  push    rdi
0x100423462  push    r12
0x100423464  push    r13
0x100423466  push    r14
0x100423468  push    r15
0x10042346a  sub     rsp, 4A0h
0x100423471  mov     [rsp+4D8h+var_350], 0FFFFFFFFFFFFFFFEh
0x10042347d  mov     esi, r8d
0x100423480  mov     r15, rdx
0x100423483  mov     rdi, rcx
0x100423486  xor     r14d, r14d
0x100423489  mov     [rsp+4D8h+var_418], r14d
0x100423491  mov     r10, gs:58h
0x10042349a  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004234a1  mov     r9d, [rax]
0x1004234a4  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004234ab  mov     ebx, [rax]
0x1004234ad  add     rbx, [r10+r9*8]
0x1004234b1  mov     rdx, [rbx+100h]
0x1004234b8  test    rdx, rdx
0x1004234bb  jz      loc_101678B05
0x1004234c1  mov     [rsp+4D8h+var_410], rdx
0x1004234c9  mov     ecx, [r15]
0x1004234cc  movzx   eax, cx
0x1004234cf  cmp     dword ptr [r15+10h], 1
0x1004234d4  cmovnz  ecx, eax
0x1004234d7  cmp     ecx, 2BDh
0x1004234dd  jz      loc_101678B1A
0x1004234e3  mov     rdx, gs:58h
0x1004234ec  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004234f3  mov     ecx, [rax]
0x1004234f5  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004234fc  mov     ebx, [rax]
0x1004234fe  add     rbx, [rdx+rcx*8]
0x100423502  mov     rcx, [rbx+100h]
0x100423509  test    rcx, rcx
0x10042350c  jz      loc_101678B3E
0x100423512  test    byte ptr [rcx+268h], 40h
0x100423519  jnz     loc_101678B51
0x10042351f  mov     eax, [rdi+28h]
0x100423522  test    eax, eax
0x100423524  jz      loc_101678B51
0x10042352a  test    dword ptr [rcx+268h], 4000h
0x100423534  jnz     loc_101678B51
0x10042353a  mov     r12d, r14d
0x10042353d  mov     r13d, 1
0x100423543  jmp     short loc_100423546
0x100423546  mov     rbx, r14
0x100423549  mov     [rsp+4D8h+var_408], rbx
0x100423551  mov     [rsp+4D8h+var_468], r14
0x100423556  mov     [rsp+4D8h+var_458], r14
0x10042355e  mov     rax, [rdi]
0x100423561  xor     edx, edx
0x100423563  mov     rcx, rdi
0x100423566  call    qword ptr [rax+78h]
0x100423569  movzx   ecx, ax
0x10042356c  mov     [rsp+4D8h+var_320], 20000h
0x100423577  mov     [rsp+4D8h+var_318], r14d
0x10042357f  lea     rax, [rsp+4D8h+var_2F8]
0x100423587  mov     [rsp+4D8h+var_310], rax
0x10042358f  lea     rax, [rsp+4D8h+var_2D8]
0x100423597  mov     [rsp+4D8h+var_308], rax
0x10042359f  mov     [rsp+4D8h+var_D8], r14
0x1004235a7  mov     [rsp+4D8h+var_300], r14
0x1004235af  mov     [rsp+4D8h+var_D0], r14
0x1004235b7  lea     rax, [rsp+4D8h+var_C8]
0x1004235bf  mov     [rsp+4D8h+var_2F8], rax
0x1004235c7  mov     [rsp+4D8h+var_2F0], 1Bh
0x1004235d2  mov     [rsp+4D8h+var_2EC], 1
0x1004235dd  mov     [rsp+4D8h+var_2E8], r14
0x1004235e5  mov     [rsp+4D8h+var_2E0], r14d
0x1004235ed  mov     [rsp+4D8h+var_2DC], 7
0x1004235f8  mov     [rsp+4D8h+var_A8], r15
0x100423600  mov     [rsp+4D8h+var_A0], esi
0x100423607  mov     r14d, [rsp+4D8h+arg_18]
0x10042360f  mov     [rsp+4D8h+var_9C], r14d
0x100423617  mov     [rsp+4D8h+var_98], 0
0x10042361f  xor     esi, esi
0x100423621  mov     [rsp+4D8h+var_90], rsi
0x100423629  mov     [rsp+4D8h+var_88], esi
0x100423630  mov     [rsp+4D8h+var_84], sil
0x100423638  mov     [rsp+4D8h+var_80], rsi
0x100423640  mov     [rsp+4D8h+var_78], r12d
0x100423648  lea     rax, [rdi+400h]
0x10042364f  mov     [rsp+4D8h+var_70], rax
0x100423657  lea     rax, [rdi+410h]
0x10042365e  mov     [rsp+4D8h+var_68], rax
0x100423666  mov     [rsp+4D8h+var_60], cx
0x10042366e  mov     ecx, [r15]
0x100423671  movzx   eax, cx
0x100423674  cmp     dword ptr [r15+10h], 1
0x100423679  cmovnz  ecx, eax
0x10042367c  call    _anonymous_namespace___FHideUserDataParameters
0x100423681  mov     [rsp+4D8h+var_400], eax
0x100423688  test    eax, eax
0x10042368a  jnz     loc_101678B60
0x100423690  mov     [rsp+4D8h+arg_8], 0
0x100423698  mov     [rsp+4D8h+var_430], esi
0x10042369f  xor     edx, edx; unsigned __int16
0x1004236a1  mov     [rsp+4D8h+var_4B0], rsi; struct Worker *
0x1004236a6  mov     rax, cs:__imp_?hdl_backout@@YAHHHHHPEAD@Z; hdl_backout(int,int,int,int,char *)
0x1004236ad  mov     [rsp+4D8h+var_4B8], rax; int (*)(int, int, int, int, char *)
0x1004236b2  xor     r9d, r9d; unsigned __int8
0x1004236b5  xor     r8d, r8d; unsigned __int8
0x1004236b8  lea     rcx, [rsp+4D8h+var_390]; this
0x1004236c0  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x1004236c5  nop
0x1004236c6  mov     ecx, [rsp+4D8h+arg_40]
0x1004236cd  mov     eax, ecx
0x1004236cf  and     eax, 1
0x1004236d2  mov     [rsp+4D8h+var_44C], eax
0x1004236d9  mov     [rsp+4D8h+var_438], eax
0x1004236e0  mov     eax, ecx
0x1004236e2  shr     eax, 1
0x1004236e4  and     eax, 1
0x1004236e7  mov     [rsp+4D8h+var_434], eax
0x1004236ee  mov     [rsp+4D8h+var_45C], eax
0x1004236f2  mov     eax, ecx
0x1004236f4  shr     eax, 2
0x1004236f7  and     eax, 1
0x1004236fa  mov     [rsp+4D8h+var_3FC], eax
0x100423701  mov     eax, ecx
0x100423703  shr     eax, 4
0x100423706  and     eax, 1
0x100423709  mov     [rsp+4D8h+var_3E4], eax
0x100423710  mov     [rsp+4D8h+var_444], esi
0x100423717  mov     [rsp+4D8h+var_428], esi
0x10042371e  mov     [rsp+4D8h+var_3E8], esi
0x100423725  mov     rdi, rsi
0x100423728  mov     [rsp+4D8h+var_3F8], rsi
0x100423730  mov     [rsp+4D8h+var_448], esi
0x100423737  mov     [rsp+4D8h+var_420], rsi
0x10042373f  mov     [rsp+4D8h+var_42C], 0
0x10042374a  mov     rcx, [rsp+4D8h+arg_0]
0x100423752  mov     rax, [rcx]
0x100423755  xor     edx, edx
0x100423757  call    qword ptr [rax+78h]
0x10042375a  mov     [rsp+4D8h+var_450], ax
0x100423762  mov     eax, [rsp+4D8h+var_44C]
0x100423769  mov     [rsp+4D8h+var_440], eax
0x100423770  mov     [rsp+4D8h+var_43C], eax
0x100423777  mov     eax, [r15+4]
0x10042377b  cmp     eax, 0Ah
0x10042377e  jz      loc_10054F063
0x100423784  cmp     eax, 12h
0x100423787  jg      short loc_1004237BD
0x100423789  mov     rax, cs:__imp_?m_PerfCountersEnabled@CommonGlobalState@@2_NA; bool CommonGlobalState::m_PerfCountersEnabled
0x100423790  cmp     byte ptr [rax], 0
0x100423793  jz      short loc_1004237BD
0x100423795  mov     [rsp+4D8h+var_4B0], 0
0x10042379e  mov     dword ptr [rsp+4D8h+var_4B8], 2
0x1004237a6  mov     r9, r13
0x1004237a9  xor     r8d, r8d
0x1004237ac  lea     edx, [r8+0Eh]
0x1004237b0  mov     rcx, cs:qword_102ECFB00
0x1004237b7  call    cs:__imp_?IncrementCounterInstanceValue@PerfmonManager@@QEAAHKK_JKPEA_K@Z; PerfmonManager::IncrementCounterInstanceValue(ulong,ulong,__int64,ulong,unsigned __int64 *)
0x1004237bd  test    r12d, r12d
0x1004237c0  jnz     loc_100423977
0x1004237c6  mov     [rsp+4D8h+var_3C8], 1300h
0x1004237d1  mov     rdx, gs:58h
0x1004237da  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004237e1  mov     ecx, [rax]
0x1004237e3  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004237ea  mov     ebx, [rax]
0x1004237ec  add     rbx, [rdx+rcx*8]
0x1004237f0  mov     rdx, [rbx+100h]
0x1004237f7  test    rdx, rdx
0x1004237fa  jz      loc_101678B82
0x100423800  mov     rdx, [rdx+3E8h]
0x100423807  mov     [rsp+4D8h+var_348], rdx
0x10042380f  mov     byte ptr [rsp+4D8h+var_4B0], 3
0x100423814  mov     dword ptr [rsp+4D8h+var_4B8], 1300h
0x10042381c  lea     r9, aSqlNtdbmsMsqlU_15; "sql\\ntdbms\\msql\\utils\\errorreport.c"...
0x100423823  mov     r8d, r13d
0x100423826  mov     ecx, 1248h
0x10042382b  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100423831  mov     rbx, rax
0x100423834  mov     [rsp+4D8h+var_368], rax
0x10042383c  xor     r14d, r14d
0x10042383f  test    rax, rax
0x100423842  jz      short loc_10042387E
0x100423844  mov     [rax+1068h], rax
0x10042384b  mov     [rax+1070h], r14d
0x100423852  mov     [rax+1208h], r14d
0x100423859  mov     [rax+120Ch], r14d
0x100423860  mov     ecx, r14d
0x100423863  mov     [rsp+4D8h+var_3F0], ecx
0x10042386a  cmp     ecx, 32h ; '2'
0x10042386d  jge     short loc_100423881
0x10042386f  movsxd  rax, ecx
0x100423872  mov     [rax+rbx+1210h], r14b
0x10042387a  inc     ecx
0x10042387c  jmp     short loc_100423863
0x10042387e  mov     rbx, r14
0x100423881  mov     rcx, [rsp+4D8h+var_468]
0x100423886  cmp     rcx, rbx
0x100423889  jz      short loc_100423896
0x10042388b  mov     edx, 1248h
0x100423890  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x100423896  mov     [rsp+4D8h+var_468], rbx
0x10042389b  movzx   esi, [rsp+4D8h+arg_8]
0x1004238a3  test    sil, sil
0x1004238a6  jnz     loc_101678B97
0x1004238ac  mov     rdx, gs:58h
0x1004238b5  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004238bc  mov     ecx, [rax]
0x1004238be  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004238c5  mov     ebx, [rax]
0x1004238c7  add     rbx, [rdx+rcx*8]
0x1004238cb  mov     rdx, [rbx+100h]
0x1004238d2  test    rdx, rdx
0x1004238d5  jz      loc_101678C80
0x1004238db  mov     byte ptr [rsp+4D8h+var_4B0], 3
0x1004238e0  mov     dword ptr [rsp+4D8h+var_4B8], 130Ah
0x1004238e8  lea     r9, aSqlNtdbmsMsqlU_15; "sql\\ntdbms\\msql\\utils\\errorreport.c"...
0x1004238ef  mov     r8d, r13d
0x1004238f2  mov     rdx, [rdx+3E8h]
0x1004238f9  mov     ecx, 1000h
0x1004238fe  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100423904  mov     rdi, rax
0x100423907  mov     rcx, [rsp+4D8h+var_3F8]
0x10042390f  cmp     rcx, rax
0x100423912  jz      short loc_10042391A
0x100423914  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10042391a  mov     [rsp+4D8h+var_3F8], rdi
0x100423922  cmp     [rsp+4D8h+var_468], 0
0x100423928  jz      loc_101678CA4
0x10042392e  test    sil, sil
0x100423931  jnz     loc_101678C95
0x100423937  test    rdi, rdi
0x10042393a  mov     r12d, r14d
0x10042393d  jz      loc_101678CA4
0x100423943  mov     eax, [rsp+4D8h+var_438]
0x10042394a  mov     [rsp+4D8h+var_44C], eax
0x100423951  mov     eax, [rsp+4D8h+var_43C]
0x100423958  mov     [rsp+4D8h+var_440], eax
0x10042395f  mov     rsi, [rsp+4D8h+var_420]
0x100423967  mov     rbx, [rsp+4D8h+var_408]
0x10042396f  mov     r14d, [rsp+4D8h+arg_18]
0x100423977  cmp     dword ptr [r15+10h], 1
0x10042397c  jz      short loc_1004239FD
0x10042397e  mov     rax, rdi
0x100423981  neg     rax
0x100423984  sbb     ecx, ecx
0x100423986  and     ecx, 800h
0x10042398c  lea     rax, [rsp+4D8h+var_448]
0x100423994  mov     [rsp+4D8h+var_4A8], rax; int *
0x100423999  mov     dword ptr [rsp+4D8h+var_4B0], ecx; int
0x10042399d  mov     [rsp+4D8h+var_4B8], rdi; wchar_t *
0x1004239a2  lea     r9, [rsp+4D8h+var_3E8]; int *
0x1004239aa  lea     r8, [rsp+4D8h+var_428]; int *
0x1004239b2  lea     rdx, [rsp+4D8h+var_444]; int *
0x1004239ba  mov     rcx, r15; struct SQLError *
0x1004239bd  call    ?FGetMsgFormatSpecs@@YAHPEAVSQLError@@PEAH11PEA_WH1@Z; FGetMsgFormatSpecs(SQLError *,int *,int *,int *,wchar_t *,int,int *)
0x1004239c2  test    eax, eax
0x1004239c4  jz      loc_101678CAD
0x1004239ca  test    byte ptr [rsp+4D8h+arg_40], 8
0x1004239d2  jnz     short loc_1004239FD
0x1004239d4  mov     ecx, [r15]
0x1004239d7  movzx   eax, cx
0x1004239da  cmp     dword ptr [r15+10h], 1
0x1004239df  cmovnz  ecx, eax
0x1004239e2  mov     r9d, 0FFFFFFFFh
0x1004239e8  xor     r8d, r8d
0x1004239eb  mov     edx, [r15+4]
0x1004239ef  call    cs:__imp_?ex_dump_trigger@@YAHKHPEAHH@Z; ex_dump_trigger(ulong,int,int *,int)
0x1004239f5  test    eax, eax
0x1004239f7  jnz     loc_101678DB7
0x1004239fd  test    r12d, r12d
0x100423a00  jnz     loc_1016793A0
0x100423a06  cmp     dword ptr [r15+10h], 1
0x100423a0b  jz      loc_101678EC4
0x100423a11  mov     rax, [rsp+4D8h+arg_50]
0x100423a19  mov     [rsp+4D8h+var_478], rax; char *
0x100423a1e  mov     r13, [rsp+4D8h+arg_48]
0x100423a26  mov     [rsp+4D8h+var_480], r13; enum EFormatType *
0x100423a2b  mov     rax, [rsp+4D8h+var_468]
0x100423a30  mov     [rsp+4D8h+var_488], rax; struct CFormattedParams *
0x100423a35  mov     eax, [rsp+4D8h+var_400]
0x100423a3c  mov     dword ptr [rsp+4D8h+var_490], eax; int
0x100423a40  mov     eax, [rsp+4D8h+var_440]
0x100423a47  mov     dword ptr [rsp+4D8h+var_498], eax; int
0x100423a4b  mov     eax, [rsp+4D8h+var_45C]
0x100423a4f  mov     dword ptr [rsp+4D8h+var_4A0], eax; int
0x100423a53  mov     eax, [rsp+4D8h+var_44C]
0x100423a5a  mov     dword ptr [rsp+4D8h+var_4A8], eax; int
0x100423a5e  xor     eax, eax
0x100423a60  mov     dword ptr [rsp+4D8h+var_4B0], eax; int
0x100423a64  mov     [rsp+4D8h+var_4B8], rax; wchar_t *
0x100423a69  xor     r9d, r9d; int
0x100423a6c  xor     r8d, r8d; wchar_t *
0x100423a6f  mov     edx, [rsp+4D8h+var_448]; int
0x100423a76  mov     rcx, rdi; wchar_t *
0x100423a79  call    ?FFormatParams@@YAHPEB_WHPEA_WH1HHHHHPEAVCFormattedParams@@PEBW4EFormatType@@PEAD@Z; FFormatParams(wchar_t const *,int,wchar_t *,int,wchar_t *,int,int,int,int,int,CFormattedParams *,EFormatType const *,char *)
0x100423a7e  xor     ecx, ecx
  ... truncated ...
```
