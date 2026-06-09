# EtlFileQueryResult::EtlFileQueryResult(OperationControl *,void *,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::map<ulong,QueryNode,utl::less<ulong>,utl::allocator<utl::pair<ulong const,QueryNode>>> const &,ulong,wchar_t const *,_GUID *,void *,__int64 &,ulong)

- ea: `0x180060194`
- end: `0x180061006`
- name: `??0EtlFileQueryResult@@AEAA@PEAVOperationControl@@PEAXV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@AEBV?$map@KUQueryNode@@U?$less@K@utl@@V?$allocator@U?$pair@$$CBKUQueryNode@@@utl@@@3@@5@KPEB_WPEAU_GUID@@1AEA_JK@Z`
- size: `3698`
- prototype: `__int64 __usercall@<rax>(LPVOID lpParameter@<rcx>, __int64, __int64, int, __int64, __int64, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005ffc0`

## callees

- `0x18000347c`
- `0x180008d30`
- `0x180014bd0`
- `0x180016ef0`
- `0x180017b60`
- `0x180019d28`
- `0x18001c320`
- `0x18002b310`
- `0x18002d6dc`
- `0x18002dcc0`
- `0x18002de70`
- `0x18002fa38`
- `0x18003d394`
- `0x18003ed4c`
- `0x18003ee1c`
- `0x1800441ec`
- `0x1800498d8`
- `0x18005ea74`
- `0x18005ff90`
- `0x180060194`
- `0x1800613d8`
- `0x180062484`
- `0x18008aeb4`
- `0x18008c17c`
- `0x18008c1f8`
- `0x180091c20`
- `0x180091edc`
- `0x180092008`
- `0x18009aee0`
- `0x18009bb88`
- `0x18009cd4c`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1800606b2`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1800606b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800605b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800609de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060cdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060ddc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800605b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800609de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060cdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060ddc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180060d8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180060d8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180060c5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180060c5b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180060c99`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180060c99`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180060c71`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180060c71`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180060ccf`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180060ccf`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180060d75`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180060d75`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x180060587`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18006097d`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x180060587`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18006097d`

## pseudocode

```c
// Hidden C++ exception states: #wind=18 #try_helpers=1
char *__fastcall EtlFileQueryResult::EtlFileQueryResult(
        char *lpParameter,
        __int64 a2,
        void *a3,
        __int64 *a4,
        __int128 *a5,
        wmi::RefBase *a6,
        int a7,
        const WCHAR *a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        unsigned int a12)
{
  __int64 v15; // r15
  __int64 *v16; // rdi
  unsigned int v17; // ebx
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rax
  unsigned int v21; // r13d
  _QWORD *FilterQuery; // rdi
  __int64 v23; // rax
  const WCHAR *v24; // r12
  TRACEHANDLE v25; // rax
  __int64 v26; // r8
  DWORD LastError; // ebx
  int v28; // esi
  unsigned int v29; // ebx
  __int64 v30; // r8
  TRACEHANDLE v31; // rax
  DWORD v32; // ebx
  __int64 v33; // rbx
  _WORD *v34; // rsi
  wmi::RefBase *v35; // r10
  wmi::RefBase *v36; // rax
  HANDLE CurrentThread; // rax
  HANDLE *v38; // rbx
  HANDLE v39; // rax
  DWORD v40; // ebx
  DWORD v42; // ebx
  wmi::RefBase *v43[2]; // [rsp+50h] [rbp-528h] BYREF
  __int64 v44; // [rsp+60h] [rbp-518h] BYREF
  __int64 v45; // [rsp+68h] [rbp-510h]
  void *TokenHandle[2]; // [rsp+70h] [rbp-508h] BYREF
  wchar_t *v47[2]; // [rsp+80h] [rbp-4F8h] BYREF
  __int64 v48[2]; // [rsp+A0h] [rbp-4D8h] BYREF
  __int128 v49; // [rsp+B0h] [rbp-4C8h]
  __int64 v50; // [rsp+C0h] [rbp-4B8h]
  void *Thread[3]; // [rsp+C8h] [rbp-4B0h] BYREF
  __int64 v52[2]; // [rsp+E0h] [rbp-498h] BYREF
  __int64 v53[4]; // [rsp+F0h] [rbp-488h] BYREF
  void *v54[2]; // [rsp+110h] [rbp-468h] BYREF
  char v55; // [rsp+120h] [rbp-458h] BYREF
  __int128 pExceptionObject; // [rsp+130h] [rbp-448h] BYREF
  __int64 v57; // [rsp+140h] [rbp-438h]
  unsigned int v58; // [rsp+148h] [rbp-430h]
  int v59; // [rsp+14Ch] [rbp-42Ch]
  int v60; // [rsp+150h] [rbp-428h]
  __int128 v61; // [rsp+158h] [rbp-420h] BYREF
  __int64 v62; // [rsp+168h] [rbp-410h]
  DWORD v63; // [rsp+170h] [rbp-408h]
  int v64; // [rsp+174h] [rbp-404h]
  int v65; // [rsp+178h] [rbp-400h]
  __int128 v66; // [rsp+180h] [rbp-3F8h] BYREF
  __int64 v67; // [rsp+190h] [rbp-3E8h]
  unsigned int v68; // [rsp+198h] [rbp-3E0h]
  int v69; // [rsp+19Ch] [rbp-3DCh]
  int v70; // [rsp+1A0h] [rbp-3D8h]
  __int128 v71; // [rsp+1A8h] [rbp-3D0h] BYREF
  __int64 v72; // [rsp+1B8h] [rbp-3C0h]
  int v73; // [rsp+1C0h] [rbp-3B8h]
  int v74; // [rsp+1C4h] [rbp-3B4h]
  int v75; // [rsp+1C8h] [rbp-3B0h]
  __int128 v76; // [rsp+1D0h] [rbp-3A8h] BYREF
  __int64 v77; // [rsp+1E0h] [rbp-398h]
  int v78; // [rsp+1E8h] [rbp-390h]
  int v79; // [rsp+1ECh] [rbp-38Ch]
  int v80; // [rsp+1F0h] [rbp-388h]
  __int128 v81; // [rsp+1F8h] [rbp-380h] BYREF
  __int64 v82; // [rsp+208h] [rbp-370h]
  int v83; // [rsp+210h] [rbp-368h]
  int v84; // [rsp+214h] [rbp-364h]
  int v85; // [rsp+218h] [rbp-360h]
  __int128 v86; // [rsp+220h] [rbp-358h] BYREF
  __int64 v87; // [rsp+230h] [rbp-348h]
  DWORD v88; // [rsp+238h] [rbp-340h]
  int v89; // [rsp+23Ch] [rbp-33Ch]
  int v90; // [rsp+240h] [rbp-338h]
  __int128 v91; // [rsp+248h] [rbp-330h] BYREF
  __int64 v92; // [rsp+258h] [rbp-320h]
  DWORD v93; // [rsp+260h] [rbp-318h]
  int v94; // [rsp+264h] [rbp-314h]
  int v95; // [rsp+268h] [rbp-310h]
  __int128 v96; // [rsp+270h] [rbp-308h] BYREF
  __int64 v97; // [rsp+280h] [rbp-2F8h]
  DWORD v98; // [rsp+288h] [rbp-2F0h]
  int v99; // [rsp+28Ch] [rbp-2ECh]
  int v100; // [rsp+290h] [rbp-2E8h]
  __int128 v101; // [rsp+298h] [rbp-2E0h] BYREF
  __int64 v102; // [rsp+2A8h] [rbp-2D0h]
  int v103; // [rsp+2B0h] [rbp-2C8h]
  int v104; // [rsp+2B4h] [rbp-2C4h]
  int v105; // [rsp+2B8h] [rbp-2C0h]
  __int128 v106; // [rsp+2C0h] [rbp-2B8h] BYREF
  __int64 v107; // [rsp+2D0h] [rbp-2A8h]
  int v108; // [rsp+2D8h] [rbp-2A0h]
  int v109; // [rsp+2DCh] [rbp-29Ch]
  int v110; // [rsp+2E0h] [rbp-298h]
  __int128 v111; // [rsp+2E8h] [rbp-290h] BYREF
  __int64 v112; // [rsp+2F8h] [rbp-280h]
  int v113; // [rsp+300h] [rbp-278h]
  int v114; // [rsp+304h] [rbp-274h]
  int v115; // [rsp+308h] [rbp-270h]
  __int128 v116; // [rsp+310h] [rbp-268h]
  _EVENT_TRACE_LOGFILEW Logfile; // [rsp+320h] [rbp-258h] BYREF
  _WORD v118[8]; // [rsp+4E0h] [rbp-98h] BYREF
  _WORD v119[40]; // [rsp+4F0h] [rbp-88h] BYREF

  Thread[1] = lpParameter;
  v48[0] = (__int64)a5;
  v43[0] = a6;
  v50 = a10;
  LogQueryResult::LogQueryResult((LogQueryResult *)lpParameter);
  *(_QWORD *)lpParameter = &EtlFileQueryResult::`vftable';
  *((_QWORD *)lpParameter + 9) = 0;
  *((_QWORD *)lpParameter + 10) = 0;
  *((_QWORD *)lpParameter + 11) = 0;
  *((_QWORD *)lpParameter + 12) = 0;
  *((_QWORD *)lpParameter + 13) = 0;
  *((_QWORD *)lpParameter + 14) = 0;
  *((_DWORD *)lpParameter + 30) = 0;
  v15 = -1;
  *((_DWORD *)lpParameter + 31) = -1;
  *((_QWORD *)lpParameter + 16) = 0;
  *((_QWORD *)lpParameter + 17) = 0;
  *((_QWORD *)lpParameter + 18) = 0;
  `eh vector constructor iterator'(
    lpParameter + 152,
    8u,
    0x10u,
    tlx::unique_any<tlx::handle_traits<unsigned __int64,unsigned long (*)(unsigned __int64),&unsigned long CloseTrace(unsigned __int64),-1>>::unique_any<tlx::handle_traits<unsigned __int64,unsigned long (*)(unsigned __int64),&unsigned long CloseTrace(unsigned __int64),-1>>,
    tlx::unique_any<tlx::handle_traits<unsigned __int64,unsigned long (*)(unsigned __int64),&unsigned long CloseTrace(unsigned __int64),-1>>::~unique_any<tlx::handle_traits<unsigned __int64,unsigned long (*)(unsigned __int64),&unsigned long CloseTrace(unsigned __int64),-1>>);
  *((_QWORD *)lpParameter + 35) = 0;
  *((_QWORD *)lpParameter + 36) = 0;
  *((_QWORD *)lpParameter + 37) = 0;
  *((_QWORD *)lpParameter + 38) = 0;
  *((_QWORD *)lpParameter + 39) = 0;
  v44 = *a4;
  v45 = a4[1];
  v16 = (__int64 *)(lpParameter + 320);
  MakeOrThrowOOM(lpParameter + 320);
  *((_QWORD *)lpParameter + 44) = a12;
  v49 = *a5;
  MakeOrThrowOOM(lpParameter + 360);
  utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>(lpParameter + 392);
  utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>(lpParameter + 424);
  *((_QWORD *)lpParameter + 57) = a11;
  *((_DWORD *)lpParameter + 116) = 0;
  lpParameter[468] = 0;
  v17 = CopySelfRelativeSD(a3);
  if ( v17 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_df2db0e57fcf329b720e46088dc10b5a_Traceguids, v17);
    }
    pExceptionObject = 0;
    v57 = 0;
    v58 = v17;
    v59 = -1;
    v60 = 353;
    throw (EvtException *)&pExceptionObject;
  }
  v18 = *((_QWORD *)lpParameter + 41);
  v19 = *v16;
  if ( *v16 == v18 )
  {
    v44 = *((_QWORD *)lpParameter + 45);
    v45 = (*((_QWORD *)lpParameter + 46) - v44) >> 1;
  }
  else
  {
    v44 = *v16;
    v45 = (v18 - v19) >> 1;
  }
  AssignOrThrowOOM(lpParameter + 16, &v44);
  if ( *v16 != *((_QWORD *)lpParameter + 41) )
  {
    TokenHandle[0] = MIDL_user_allocate(0x10008u);
    utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>::operator=(lpParameter + 96, TokenHandle);
    if ( TokenHandle[0] )
      operator delete(TokenHandle[0]);
    v20 = *((_QWORD *)lpParameter + 12);
    v21 = 0;
    if ( !v20 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_df2db0e57fcf329b720e46088dc10b5a_Traceguids, 14);
      }
      v111 = 0;
      v112 = 0;
      v113 = 14;
      v114 = -1;
      v115 = 385;
      throw (EvtException *)&v111;
    }
    *((_QWORD *)lpParameter + 13) = v20;
    *((_DWORD *)lpParameter + 28) = 0;
    *((_DWORD *)lpParameter + 29) = 65544;
    *((_QWORD *)lpParameter + 16) = v20;
    *((_DWORD *)lpParameter + 34) = 0;
    *((_DWORD *)lpParameter + 35) = 65544;
    lpParameter[69] = IsQueryNodeListStarQuery(v43[0]);
    FilterQuery = (_QWORD *)CreateFilterQuery(v43, v43[0]);
    wmi::AutoRef<TermType>::Release(lpParameter + 288);
    *((_QWORD *)lpParameter + 36) = *FilterQuery;
    *FilterQuery = 0;
    if ( v43[0] )
      wmi::RefBase::Release(v43[0]);
    v23 = utl::make_unique<SimpleFilter,wmi::AutoRef<FilterQuery> &,__int64 &,0>(
            v43,
            lpParameter + 288,
            *((_QWORD *)lpParameter + 57));
    utl::unique_ptr<SimpleFilter,utl::default_delete<SimpleFilter>>::operator=(lpParameter + 296, v23);
    if ( v43[0] )
      utl::default_delete<SimpleFilter>::operator()();
    if ( !*((_QWORD *)lpParameter + 37) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_df2db0e57fcf329b720e46088dc10b5a_Traceguids, 14);
      }
      v106 = 0;
      v107 = 0;
      v108 = 14;
      v109 = -1;
      v110 = 403;
      throw (EvtException *)&v106;
    }
    v24 = a8;
    memset_0(&Logfile, 0, sizeof(Logfile));
    Logfile.LogFileMode = 0x10000000;
    Logfile.EventCallback = (PEVENT_CALLBACK)EtlFileQueryResult::_ProcessTraceEvent;
    Logfile.Context = lpParameter;
    if ( *((_DWORD *)lpParameter + 88) < 2u )
    {
      if ( !FileExists(*((const wchar_t **)lpParameter + 40)) )
        return lpParameter;
      Logfile.LogFileName = (LPWSTR)*((_QWORD *)lpParameter + 40);
      v25 = OpenTraceW(&Logfile);
      tlx::unique_any<tlx::handle_traits<unsigned __int64,unsigned long (*)(unsigned __int64),&unsigned long CloseTrace(unsigned __int64),-1>>::reset(
        lpParameter + 152,
        v25);
      if ( *((_QWORD *)lpParameter + 19) == -1 )
      {
        LastError = GetLastError();
        if ( !LastError )
          LastError = 1287;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_df2db0e57fcf329b720e46088dc10b5a_Traceguids, LastError);
        }
        v61 = 0;
        v62 = 0;
        v63 = LastError;
        v64 = -1;
        v65 = 432;
        throw (EvtException *)&v61;
      }
      *((_DWORD *)lpParameter + 89) = 1;
      goto LABEL_70;
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v47);
    v28 = 0;
    while ( v21 < *((_DWORD *)lpParameter + 88) )
    {
      v44 = *((_QWORD *)lpParameter + 40);
      v45 = (*((_QWORD *)lpParameter + 41) - v44) >> 1;
      AssignOrThrowOOM(v47, &v44);
      v29 = _o__itow_s(++v21, v118, 3);
      if ( v29 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_df2db0e57fcf329b720e46088dc10b5a_Traceguids, v29);
        }
        v66 = 0;
        v67 = 0;
        v68 = v29;
        v69 = -1;
        v70 = 451;
        throw (EvtException *)&v66;
      }
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v47) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_df2db0e57fcf329b720e46088dc10b5a_Traceguids, 14);
        }
        v71 = 0;
        v72 = 0;
        v73 = 14;
        v74 = -1;
        v75 = 456;
        throw (EvtException *)&v71;
      }
      if ( v21 < 0xA
        && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v47) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_df2db0e57fcf329b720e46088dc10b5a_Traceguids, 14);
        }
        v76 = 0;
        v77 = 0;
        v78 = 14;
        v79 = -1;
        v80 = 463;
        throw (EvtException *)&v76;
      }
      v30 = -1;
      do
        ++v30;
      while ( v118[v30] );
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v47) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_df2db0e57fcf329b720e46088dc10b5a_Traceguids, 14);
        }
        v81 = 0;
        v82 = 0;
        v83 = 14;
        v84 = -1;
        v85 = 469;
        throw (EvtException *)&v81;
      }
      if ( FileExists(v47[0]) )
      {
        Logfile.LogFileName = v47[0];
        v31 = OpenTraceW(&Logfile);
        tlx::unique_any<tlx::handle_traits<unsigned __int64,unsigned long (*)(unsigned __int64),&unsigned long CloseTrace(unsigned __int64),-1>>::reset(
          &lpParameter[8 * v28 + 152],
          v31);
        if ( *(_QWORD *)&lpParameter[8 * v28 + 152] == -1 )
        {
          v32 = GetLastError();
          if ( !v32 )
            v32 = 1287;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_df2db0e57fcf329b720e46088dc10b5a_Traceguids, v32);
          }
          v86 = 0;
          v87 = 0;
          v88 = v32;
          v89 = -1;
          v90 = 479;
          throw (EvtException *)&v86;
        }
        ++v28;
        memset_0(&Logfile, 0, sizeof(Logfile));
        Logfile.LogFileMode = 0x10000000;
        Logfile.EventCallback = (PEVENT_CALLBACK)EtlFileQueryResult::_ProcessTraceEvent;
        Logfile.Context = lpParameter;
      }
    }
    *((_DWORD *)lpParameter + 89) = v28;
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v47);
    if ( v28 )
    {
LABEL_70:
      if ( a9 )
      {
        LOBYTE(v26) = 1;
        tlx::guid_to_string_lower<wchar_t>(v119, a9, v26);
        v33 = -1;
        do
          ++v33;
        while ( v119[v33] );
        v34 = v119;
      }
      else
      {
        v34 = 0;
        v33 = 0;
      }
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v54);
      GetLocalComputerDnsName(v54);
      if ( !a8 )
        v24 = &pszFormat;
      do
        ++v15;
      while ( v24[v15] );
      v116 = 0;
      v35 = (wmi::RefBase *)MIDL_user_allocate(0x260u);
      v43[0] = v35;
      if ( v35 )
      {
        v49 = 0;
        v116 = 0;
        v44 = 0;
        v45 = 0;
        v52[0] = 0;
        v52[1] = 0;
        v53[0] = (__int64)v54[0];
        v53[1] = ((char *)v54[1] - (char *)v54[0]) >> 1;
        *(_OWORD *)v47 = *(_OWORD *)v48[0];
        v48[0] = (__int64)v34;
        v48[1] = v33;
        v53[2] = (__int64)v24;
        v53[3] = v15;
        v36 = (wmi::RefBase *)PublishedEventRecordToBinXmlConverter::PublishedEventRecordToBinXmlConverter(
                                v35,
                                (__int64)v48,
                                (__int64)v47,
                                (__int64)v53,
                                (__int64)v52,
                                (__int64)&v44,
                                v50);
      }
      else
      {
        v36 = 0;
      }
      v43[0] = v36;
      utl::unique_ptr<PublishedEventRecordToBinXmlConverter,utl::default_delete<PublishedEventRecordToBinXmlConverter>>::operator=(
        lpParameter + 312,
        v43);
      if ( v43[0] )
        PublishedEventRecordToBinXmlConverter::`scalar deleting destructor'(v43[0], 1u);
      if ( !*((_QWORD *)lpParameter + 39) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_df2db0e57fcf329b720e46088dc10b5a_Traceguids, 14);
        }
        v101 = 0;
        v102 = 0;
        v103 = 14;
        v104 = -1;
        v105 = 527;
        throw (EvtException *)&v101;
      }
      TokenHandle[0] = 0;
      CurrentThread = GetCurrentThread();
      OpenThreadToken(CurrentThread, 0xCu, 1, TokenHandle);
      v38 = (HANDLE *)(lpParameter + 280);
      v39 = CreateThread(0, 0, EtlFileQueryResult::ProcessTraceThreadProc, lpParameter, 4u, 0);
      tlx::unique_any<tlx::file_handle_traits>::reset(lpParameter + 280, v39);
      if ( (unsigned __int64)(*((_QWORD *)lpParameter + 35) + 1LL) <= 1 )
      {
        v42 = GetLastError();
        if ( !v42 )
          v42 = 1287;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_df2db0e57fcf329b720e46088dc10b5a_Traceguids, v42);
        }
        v96 = 0;
        v97 = 0;
        v98 = v42;
        v99 = -1;
        v100 = 553;
        throw (EvtException *)&v96;
      }
      Thread[0] = *v38;
      if ( !SetThreadToken(Thread, TokenHandle[0]) )
      {
        v40 = GetLastError();
        if ( !v40 )
          v40 = 1287;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_df2db0e57fcf329b720e46088dc10b5a_Traceguids, v40);
        }
        v91 = 0;
        v92 = 0;
        v93 = v40;
        v94 = -1;
        v95 = 559;
        throw (EvtException *)&v91;
      }
      ResumeThread(*v38);
      if ( (unsigned __int64)TokenHandle[0] + 1 > 1 )
        CloseHandle(TokenHandle[0]);
      if ( v54[0] != &v55 )
        operator delete(v54[0]);
    }
  }
  return lpParameter;
}

```

## disassembly

```asm
0x180060194  mov     [rsp+arg_8], rbx
0x180060199  mov     [rsp+arg_18], rsi
0x18006019e  push    rdi
0x18006019f  push    r12
0x1800601a1  push    r13
0x1800601a3  push    r14
0x1800601a5  push    r15
0x1800601a7  sub     rsp, 550h
0x1800601ae  mov     rax, cs:__security_cookie
0x1800601b5  xor     rax, rsp
0x1800601b8  mov     [rsp+578h+var_38], rax
0x1800601c0  mov     rdi, r9
0x1800601c3  mov     rsi, r8
0x1800601c6  mov     r14, rcx
0x1800601c9  mov     [rsp+578h+var_4A8], rcx
0x1800601d1  mov     r12, [rsp+578h+arg_20]
0x1800601d9  mov     [rsp+578h+var_4D8], r12
0x1800601e1  mov     rax, [rsp+578h+arg_28]
0x1800601e9  mov     [rsp+578h+var_528], rax
0x1800601ee  mov     rax, [rsp+578h+arg_48]
0x1800601f6  mov     [rsp+578h+var_4B8], rax
0x1800601fe  xor     ebx, ebx
0x180060200  call    ??0LogQueryResult@@QEAA@XZ; LogQueryResult::LogQueryResult(void)
0x180060205  nop
0x180060206  lea     rax, ??_7EtlFileQueryResult@@6B@; const EtlFileQueryResult::`vftable'
0x18006020d  mov     [r14], rax
0x180060210  mov     [r14+48h], rbx
0x180060214  mov     [r14+50h], rbx
0x180060218  mov     [r14+58h], rbx
0x18006021c  lea     r13, [r14+60h]
0x180060220  mov     [r13+0], rbx
0x180060224  mov     [r14+68h], rbx
0x180060228  mov     [r14+70h], rbx
0x18006022c  mov     [r14+78h], ebx
0x180060230  or      r15, 0FFFFFFFFFFFFFFFFh
0x180060234  mov     [r14+7Ch], r15d
0x180060238  mov     [r14+80h], rbx
0x18006023f  mov     [r14+88h], rbx
0x180060246  mov     [r14+90h], rbx
0x18006024d  lea     rcx, ??1?$unique_any@U?$handle_traits@_KP6AK_K@Z$1?CloseTrace@@YAK0@Z$0?0@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<unsigned __int64,ulong (*)(unsigned __int64),&CloseTrace(unsigned __int64),-1>>::~unique_any<tlx::handle_traits<unsigned __int64,ulong (*)(unsigned __int64),&CloseTrace(unsigned __int64),-1>>(void)
0x180060254  mov     qword ptr [rsp+578h+dwCreationFlags], rcx; void (*)(void *)
0x180060259  lea     r9, ??0?$unique_any@U?$handle_traits@_KP6AK_K@Z$1?CloseTrace@@YAK0@Z$0?0@tlx@@@tlx@@QEAA@XZ; void (*)(void *)
0x180060260  lea     edx, [rbx+8]; unsigned __int64
0x180060263  lea     r8d, [rbx+10h]; unsigned __int64
0x180060267  lea     rcx, [r14+98h]; void *
0x18006026e  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180060273  nop
0x180060274  mov     [r14+118h], rbx
0x18006027b  mov     [r14+120h], rbx
0x180060282  mov     [r14+128h], rbx
0x180060289  lea     rbx, [r14+130h]
0x180060290  mov     qword ptr [rbx], 0
0x180060297  mov     qword ptr [r14+138h], 0
0x1800602a2  mov     rax, [rdi]
0x1800602a5  mov     [rsp+578h+var_518], rax
0x1800602aa  mov     rax, [rdi+8]
0x1800602ae  mov     [rsp+578h+var_510], rax
0x1800602b3  lea     rdi, [r14+140h]
0x1800602ba  lea     rdx, [rsp+578h+var_518]
0x1800602bf  mov     rcx, rdi
0x1800602c2  call    ?MakeOrThrowOOM@@YA?AV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@2@@Z; MakeOrThrowOOM(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x1800602c7  nop
0x1800602c8  mov     eax, [rsp+578h+arg_58]
0x1800602cf  mov     [r14+160h], eax
0x1800602d6  mov     dword ptr [r14+164h], 0
0x1800602e1  movaps  xmm0, xmmword ptr [r12]
0x1800602e6  movdqa  [rsp+578h+var_4C8], xmm0
0x1800602ef  lea     r12, [r14+168h]
0x1800602f6  lea     rdx, [rsp+578h+var_4C8]
0x1800602fe  mov     rcx, r12
0x180060301  call    ?MakeOrThrowOOM@@YA?AV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@2@@Z; MakeOrThrowOOM(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x180060306  nop
0x180060307  lea     rcx, [r14+188h]
0x18006030e  call    ??0?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@2@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@2@$0A@@utl@@IEAA@XZ; utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>(void)
0x180060313  nop
0x180060314  lea     rcx, [r14+1A8h]
0x18006031b  call    ??0?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@2@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@2@$0A@@utl@@IEAA@XZ; utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>(void)
0x180060320  nop
0x180060321  mov     rax, [rsp+578h+arg_50]
0x180060329  mov     [r14+1C8h], rax
0x180060330  mov     dword ptr [r14+1D0h], 0
0x18006033b  mov     byte ptr [r14+1D4h], 0
0x180060343  mov     rdx, rbx
0x180060346  mov     rcx, rsi; Src
0x180060349  call    ?CopySelfRelativeSD@@YAKPEAXAEAV?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@@Z; CopySelfRelativeSD(void *,tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>> &)
0x18006034e  mov     ebx, eax
0x180060350  xor     esi, esi
0x180060352  test    eax, eax
0x180060354  jz      short loc_1800603D4
0x180060356  lea     rax, WPP_GLOBAL_Control
0x18006035d  mov     rcx, cs:WPP_GLOBAL_Control
0x180060364  cmp     rcx, rax
0x180060367  jz      short loc_18006038E
0x180060369  test    dword ptr [rcx+1Ch], 200h
0x180060370  jz      short loc_18006038E
0x180060372  cmp     byte ptr [rcx+19h], 2
0x180060376  jb      short loc_18006038E
0x180060378  lea     edx, [rsi+1Ah]
0x18006037b  mov     r9d, ebx
0x18006037e  lea     r8, WPP_df2db0e57fcf329b720e46088dc10b5a_Traceguids
0x180060385  mov     rcx, [rcx+10h]
0x180060389  call    WPP_SF_d
0x18006038e  xorps   xmm0, xmm0
0x180060391  movdqu  [rsp+578h+pExceptionObject], xmm0
0x18006039a  mov     [rsp+578h+var_438], rsi
0x1800603a2  mov     [rsp+578h+var_430], ebx
0x1800603a9  mov     [rsp+578h+var_42C], 0FFFFFFFFh
0x1800603b4  mov     [rsp+578h+var_428], 161h
0x1800603bf  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800603c6  lea     rcx, [rsp+578h+pExceptionObject]; pExceptionObject
0x1800603ce  call    _CxxThrowException_0
0x1800603d4  mov     rax, [rdi+8]
0x1800603d8  mov     rcx, [rdi]
0x1800603db  lea     rdx, [rsp+578h+var_518]
0x1800603e0  cmp     rcx, rax
0x1800603e3  jnz     short loc_180060400
0x1800603e5  mov     rax, [r12]
0x1800603e9  mov     [rsp+578h+var_518], rax
0x1800603ee  mov     rcx, [r12+8]
0x1800603f3  sub     rcx, rax
0x1800603f6  sar     rcx, 1
0x1800603f9  mov     [rsp+578h+var_510], rcx
0x1800603fe  jmp     short loc_180060410
0x180060400  mov     [rsp+578h+var_518], rcx
0x180060405  sub     rax, rcx
0x180060408  sar     rax, 1
0x18006040b  mov     [rsp+578h+var_510], rax
0x180060410  lea     rcx, [r14+10h]
0x180060414  call    ?AssignOrThrowOOM@@YAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@2@@Z; AssignOrThrowOOM(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x180060419  mov     rax, [rdi+8]
0x18006041d  cmp     [rdi], rax
0x180060420  jz      loc_180060DAC
0x180060426  mov     ebx, 10008h
0x18006042b  mov     ecx, ebx; size
0x18006042d  call    MIDL_user_allocate
0x180060432  mov     [rsp+578h+TokenHandle], rax
0x180060437  lea     rdx, [rsp+578h+TokenHandle]
0x18006043c  mov     rcx, r13
0x18006043f  call    ??4?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>::operator=(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &&)
0x180060444  mov     rcx, [rsp+578h+TokenHandle]; void *
0x180060449  test    rcx, rcx
0x18006044c  jz      short loc_180060453
0x18006044e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180060453  mov     rax, [r13+0]
0x180060457  xor     r13d, r13d
0x18006045a  test    rax, rax
0x18006045d  jz      loc_180060F81
0x180060463  mov     [r14+68h], rax
0x180060467  mov     [r14+70h], r13d
0x18006046b  mov     [r14+74h], ebx
0x18006046f  mov     [r14+80h], rax
0x180060476  mov     [r14+88h], r13d
0x18006047d  mov     [r14+8Ch], ebx
0x180060484  mov     rcx, [rsp+578h+var_528]
0x180060489  call    ?IsQueryNodeListStarQuery@@YA_NAEBV?$map@KUQueryNode@@U?$less@K@utl@@V?$allocator@U?$pair@$$CBKUQueryNode@@@utl@@@3@@utl@@@Z; IsQueryNodeListStarQuery(utl::map<ulong,QueryNode,utl::less<ulong>,utl::allocator<utl::pair<ulong const,QueryNode>>> const &)
0x18006048e  mov     [r14+45h], al
0x180060492  mov     rdx, [rsp+578h+var_528]
0x180060497  lea     rcx, [rsp+578h+var_528]
0x18006049c  call    ?CreateFilterQuery@@YA?AV?$AutoRef@VFilterQuery@@@wmi@@AEBV?$map@KUQueryNode@@U?$less@K@utl@@V?$allocator@U?$pair@$$CBKUQueryNode@@@utl@@@3@@utl@@@Z; CreateFilterQuery(utl::map<ulong,QueryNode,utl::less<ulong>,utl::allocator<utl::pair<ulong const,QueryNode>>> const &)
0x1800604a1  mov     rdi, rax
0x1800604a4  lea     rbx, [r14+120h]
0x1800604ab  mov     rcx, rbx
0x1800604ae  call    ?Release@?$AutoRef@VTermType@@@wmi@@QEAAXXZ; wmi::AutoRef<TermType>::Release(void)
0x1800604b3  mov     rax, [rdi]
0x1800604b6  mov     [rbx], rax
0x1800604b9  mov     [rdi], r13
0x1800604bc  mov     rcx, [rsp+578h+var_528]; this
0x1800604c1  test    rcx, rcx
0x1800604c4  jz      short loc_1800604CB
0x1800604c6  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x1800604cb  mov     r8, [r14+1C8h]
0x1800604d2  lea     rdx, [r14+120h]
0x1800604d9  lea     rcx, [rsp+578h+var_528]
0x1800604de  call    ??$make_unique@VSimpleFilter@@AEAV?$AutoRef@VFilterQuery@@@wmi@@AEA_J$0A@@utl@@YA?AV?$unique_ptr@VSimpleFilter@@U?$default_delete@VSimpleFilter@@@utl@@@0@AEAV?$AutoRef@VFilterQuery@@@wmi@@AEA_J@Z; utl::make_unique<SimpleFilter,wmi::AutoRef<FilterQuery> &,__int64 &,0>(wmi::AutoRef<FilterQuery> &,__int64 &)
0x1800604e3  mov     rdx, rax
0x1800604e6  lea     rcx, [r14+128h]
0x1800604ed  call    ??4?$unique_ptr@VSimpleFilter@@U?$default_delete@VSimpleFilter@@@utl@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<SimpleFilter,utl::default_delete<SimpleFilter>>::operator=(utl::unique_ptr<SimpleFilter,utl::default_delete<SimpleFilter>> &&)
0x1800604f2  mov     rdx, [rsp+578h+var_528]
0x1800604f7  test    rdx, rdx
0x1800604fa  jz      short loc_180060501
0x1800604fc  call    ??R?$default_delete@VSimpleFilter@@@utl@@QEBAXPEAVSimpleFilter@@@Z; utl::default_delete<SimpleFilter>::operator()(SimpleFilter *)
0x180060501  cmp     [r14+128h], r13
0x180060508  jz      loc_180060EFC
0x18006050e  mov     r12, [rsp+578h+arg_38]
0x180060516  xor     edx, edx; Val
0x180060518  mov     r8d, 1C0h; Size
0x18006051e  lea     rcx, [rsp+578h+Logfile]; void *
0x180060526  call    memset_0
0x18006052b  mov     dword ptr [rsp+578h+Logfile.1Ch], 10000000h
0x180060536  lea     rax, ?_ProcessTraceEvent@EtlFileQueryResult@@CAXPEAU_EVENT_RECORD@@@Z; EtlFileQueryResult::_ProcessTraceEvent(_EVENT_RECORD *)
0x18006053d  mov     qword ptr [rsp+578h+Logfile.1A8h], rax
0x180060545  mov     [rsp+578h+Logfile.Context], r14
0x18006054d  cmp     dword ptr [r14+160h], 2
0x180060555  jnb     loc_180060647
0x18006055b  mov     rcx, [r14+140h]; wchar_t *
0x180060562  call    ?FileExists@@YA_NPEB_W@Z; FileExists(wchar_t const *)
0x180060567  test    al, al
0x180060569  jnz     short loc_180060570
0x18006056b  jmp     loc_180060DAC
0x180060570  mov     rax, [r14+140h]
0x180060577  mov     [rsp+578h+Logfile.LogFileName], rax
0x18006057f  lea     rcx, [rsp+578h+Logfile]; Logfile
0x180060587  call    cs:__imp_OpenTraceW
0x18006058d  mov     rdx, rax
0x180060590  lea     rcx, [r14+98h]
0x180060597  call    ?reset@?$unique_any@U?$handle_traits@_KP6AK_K@Z$1?CloseTrace@@YAK0@Z$0?0@tlx@@@tlx@@QEAAX_K@Z; tlx::unique_any<tlx::handle_traits<unsigned __int64,ulong (*)(unsigned __int64),&CloseTrace(unsigned __int64),-1>>::reset(unsigned __int64)
0x18006059c  cmp     [r14+98h], r15
0x1800605a3  jz      short loc_1800605B6
0x1800605a5  mov     edi, 1
0x1800605aa  mov     [r14+164h], edi
0x1800605b1  jmp     loc_180060A8F
0x1800605b6  call    cs:__imp_GetLastError
0x1800605bc  mov     ebx, eax
0x1800605be  mov     eax, 507h
0x1800605c3  test    ebx, ebx
0x1800605c5  cmovz   ebx, eax
0x1800605c8  lea     rax, WPP_GLOBAL_Control
0x1800605cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800605d6  cmp     rcx, rax
0x1800605d9  jz      short loc_180060602
0x1800605db  test    dword ptr [rcx+1Ch], 200h
0x1800605e2  jz      short loc_180060602
0x1800605e4  cmp     byte ptr [rcx+19h], 2
0x1800605e8  jb      short loc_180060602
0x1800605ea  mov     edx, 1Eh
0x1800605ef  mov     r9d, ebx
0x1800605f2  lea     r8, WPP_df2db0e57fcf329b720e46088dc10b5a_Traceguids
0x1800605f9  mov     rcx, [rcx+10h]
0x1800605fd  call    WPP_SF_d
0x180060602  xorps   xmm0, xmm0
0x180060605  movdqu  [rsp+578h+var_420], xmm0
0x18006060e  mov     [rsp+578h+var_410], r13
0x180060616  mov     [rsp+578h+var_408], ebx
0x18006061d  mov     [rsp+578h+var_404], 0FFFFFFFFh
0x180060628  mov     [rsp+578h+var_400], 1B0h
0x180060633  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18006063a  lea     rcx, [rsp+578h+var_420]; pExceptionObject
0x180060642  call    _CxxThrowException_0
0x180060647  lea     rcx, [rsp+578h+var_4F8]; void *
0x18006064f  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180060654  nop
0x180060655  mov     esi, r13d
0x180060658  mov     edi, 1
0x18006065d  cmp     r13d, [r14+160h]
0x180060664  jnb     loc_180060A6F
0x18006066a  mov     rax, [r14+140h]
0x180060671  mov     [rsp+578h+var_518], rax
0x180060676  mov     rcx, [r14+148h]
0x18006067d  sub     rcx, rax
0x180060680  sar     rcx, 1
0x180060683  mov     [rsp+578h+var_510], rcx
0x180060688  lea     rdx, [rsp+578h+var_518]
0x18006068d  lea     rcx, [rsp+578h+var_4F8]
0x180060695  call    ?AssignOrThrowOOM@@YAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@2@@Z; AssignOrThrowOOM(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18006069a  inc     r13d
0x18006069d  mov     r9d, 0Ah
0x1800606a3  lea     r8d, [r9-7]
0x1800606a7  lea     rdx, [rsp+578h+var_98]
0x1800606af  mov     ecx, r13d
0x1800606b2  call    cs:__imp__o__itow_s
0x1800606b8  mov     ebx, eax
0x1800606ba  test    eax, eax
0x1800606bc  jz      loc_180060745
0x1800606c2  lea     rax, WPP_GLOBAL_Control
0x1800606c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800606d0  cmp     rcx, rax
0x1800606d3  jz      short loc_1800606FC
0x1800606d5  test    dword ptr [rcx+1Ch], 200h
0x1800606dc  jz      short loc_1800606FC
0x1800606de  cmp     byte ptr [rcx+19h], 2
0x1800606e2  jb      short loc_1800606FC
0x1800606e4  mov     edx, 1Fh
0x1800606e9  mov     r9d, ebx
0x1800606ec  lea     r8, WPP_df2db0e57fcf329b720e46088dc10b5a_Traceguids
0x1800606f3  mov     rcx, [rcx+10h]
0x1800606f7  call    WPP_SF_d
0x1800606fc  xorps   xmm0, xmm0
0x1800606ff  movdqu  [rsp+578h+var_3F8], xmm0
0x180060708  mov     [rsp+578h+var_3E8], 0
0x180060714  mov     [rsp+578h+var_3E0], ebx
0x18006071b  mov     [rsp+578h+var_3DC], 0FFFFFFFFh
0x180060726  mov     [rsp+578h+var_3D8], 1C3h
0x180060731  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180060738  lea     rcx, [rsp+578h+var_3F8]; pExceptionObject
0x180060740  call    _CxxThrowException_0
0x180060745  mov     r8d, 2
0x18006074b  lea     rdx, a0; ".0"
0x180060752  lea     rcx, [rsp+578h+var_4F8]
0x18006075a  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18006075f  xor     ebx, ebx
0x180060761  test    al, al
0x180060763  jnz     loc_1800607EB
0x180060769  lea     rax, WPP_GLOBAL_Control
0x180060770  mov     rcx, cs:WPP_GLOBAL_Control
0x180060777  cmp     rcx, rax
0x18006077a  jz      short loc_1800607A2
0x18006077c  test    dword ptr [rcx+1Ch], 200h
0x180060783  jz      short loc_1800607A2
0x180060785  cmp     byte ptr [rcx+19h], 2
0x180060789  jb      short loc_1800607A2
  ... truncated ...
```
