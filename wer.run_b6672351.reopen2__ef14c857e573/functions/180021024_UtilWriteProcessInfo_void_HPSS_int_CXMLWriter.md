# UtilWriteProcessInfo(void *,HPSS__ *,int,CXMLWriter *)

- ea: `0x180021024`
- end: `0x180022194`
- name: `?UtilWriteProcessInfo@@YAJPEAXPEAUHPSS__@@HPEAVCXMLWriter@@@Z`
- size: `4464`
- prototype: `__int64 __fastcall(void *, struct HPSS__ *, int, struct CXMLWriter *)`
- caller_count: `2`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180021024`
- `0x180094e8c`

## callees

- `0x180007fd8`
- `0x18000cf50`
- `0x18000da00`
- `0x18000e31c`
- `0x180020680`
- `0x180021024`
- `0x18002219c`
- `0x18002f99c`
- `0x18003bab0`
- `0x18003de9c`
- `0x180042f00`
- `0x180042f20`
- `0x180043324`
- `0x180043468`
- `0x180045438`
- `0x18004b78c`
- `0x18004c134`
- `0x18004e7dc`
- `0x180053300`
- `0x180053d3c`
- `0x18007b530`
- `0x180082ecc`
- `0x18009c274`
- `0x1800aa924`
- `0x1800aab38`
- `0x1800aaca0`
- `0x1800aaea8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021fb3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021fd6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021ffc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022025`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022048`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022071`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022094`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800220bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800220e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022109`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022132`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002215b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021fb3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021fd6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021ffc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022025`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022048`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022071`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022094`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800220bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800220e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022109`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022132`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002215b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x1800216a6`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x1800216a6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800219f5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800219f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800216ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800216ba`
- `ntdll!NtQueryInformationProcess` at `0x180021212`
- `ntdll!NtQueryInformationProcess` at `0x180021dbc`
- `ntdll!NtQueryInformationProcess` at `0x180021212`
- `ntdll!NtQueryInformationProcess` at `0x180021dbc`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180021ee2`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180021ee2`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180021279`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x1800212ce`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180021a6a`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180021279`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x1800212ce`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180021a6a`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800214f3`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800214f3`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180021468`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180021468`

## string_xrefs

- `0x180021ce6`: `ComponentId`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall UtilWriteProcessInfo(void *a1, struct HPSS__ *a2, int a3, struct CXMLWriter *a4)
{
  __int64 v7; // rdx
  __int64 v8; // r8
  _BOOL8 v9; // rcx
  unsigned int *v10; // rax
  _OWORD *v11; // rcx
  __int64 v12; // rdx
  NTSTATUS v13; // ebx
  unsigned int v14; // ebx
  wchar_t *v15; // rcx
  __int64 v16; // rdx
  void *v17; // rbx
  int v18; // eax
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  int v23; // eax
  wchar_t *v24; // rcx
  int ProcessPathFromHandle; // eax
  wchar_t *v26; // rax
  int ProcessCommandLine; // r14d
  unsigned int v28; // r14d
  PWSTR *v29; // rax
  __int64 v30; // rcx
  __int64 v31; // r8
  struct _FILETIME v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rax
  int ProcessPackageFullName; // eax
  int ProcessApplicationId; // eax
  wchar_t *v39; // rcx
  __int64 v40; // rdx
  int ProcessHostComponentIds; // eax
  signed int LastError; // eax
  int v43; // r9d
  int v44; // r9d
  int v45; // r9d
  int v46; // r9d
  int v47; // r9d
  char v48; // dl
  const wchar_t *v49; // rcx
  __int64 v50; // rax
  BOOL v51; // ebx
  int v52; // r9d
  int v53; // r9d
  int v54; // r9d
  int v55; // r9d
  int v56; // r9d
  int v57; // r9d
  NTSTATUS v58; // eax
  char *v59; // rbx
  __int128 v61; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v62; // [rsp+40h] [rbp-C0h] BYREF
  struct _FILETIME SystemTimeAsFileTime[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v64[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v65; // [rsp+64h] [rbp-9Ch] BYREF
  struct _FILETIME CreationTime; // [rsp+68h] [rbp-98h] BYREF
  char *v67; // [rsp+70h] [rbp-90h] BYREF
  void *v68; // [rsp+78h] [rbp-88h] BYREF
  struct _FILETIME ExitTime; // [rsp+80h] [rbp-80h] BYREF
  struct _FILETIME KernelTime; // [rsp+88h] [rbp-78h] BYREF
  struct _FILETIME UserTime; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v72; // [rsp+98h] [rbp-68h] BYREF
  __int128 ProcessInformation; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v74; // [rsp+B0h] [rbp-50h]
  DWORD dwProcessId[4]; // [rsp+C0h] [rbp-40h]
  LPVOID lpMem; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v77; // [rsp+D8h] [rbp-28h]
  char v78; // [rsp+E0h] [rbp-20h] BYREF
  LPVOID v79; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE *v80; // [rsp+F8h] [rbp-8h]
  char v81; // [rsp+100h] [rbp+0h] BYREF
  LPVOID v82; // [rsp+110h] [rbp+10h] BYREF
  __int64 v83; // [rsp+118h] [rbp+18h]
  char v84; // [rsp+120h] [rbp+20h] BYREF
  LPVOID v85[2]; // [rsp+130h] [rbp+30h] BYREF
  char v86; // [rsp+140h] [rbp+40h] BYREF
  LPVOID v87[2]; // [rsp+150h] [rbp+50h] BYREF
  char v88; // [rsp+160h] [rbp+60h] BYREF
  LPVOID v89[2]; // [rsp+170h] [rbp+70h] BYREF
  char v90; // [rsp+180h] [rbp+80h] BYREF
  LPVOID v91[2]; // [rsp+190h] [rbp+90h] BYREF
  char v92; // [rsp+1A0h] [rbp+A0h] BYREF
  LPVOID v93[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  char v94; // [rsp+1C0h] [rbp+C0h] BYREF
  LPVOID v95[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  char v96; // [rsp+1E0h] [rbp+E0h] BYREF
  LPVOID v97[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  char v98; // [rsp+200h] [rbp+100h] BYREF
  LPVOID v99[2]; // [rsp+210h] [rbp+110h] BYREF
  char v100; // [rsp+220h] [rbp+120h] BYREF
  wchar_t *v101; // [rsp+230h] [rbp+130h] BYREF
  char v102; // [rsp+240h] [rbp+140h] BYREF
  _QWORD v103[6]; // [rsp+250h] [rbp+150h] BYREF
  _VM_COUNTERS_EX v104; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v105[704]; // [rsp+2E0h] [rbp+1E0h] BYREF
  unsigned int v106; // [rsp+5A0h] [rbp+4A0h] BYREF
  __int64 v107; // [rsp+5A8h] [rbp+4A8h]
  __int64 v108; // [rsp+5B0h] [rbp+4B0h]
  unsigned int v109; // [rsp+5B8h] [rbp+4B8h]
  unsigned int v110; // [rsp+5BCh] [rbp+4BCh]
  unsigned int v111; // [rsp+5C0h] [rbp+4C0h]
  struct _FILETIME v112; // [rsp+5C8h] [rbp+4C8h]
  struct _FILETIME v113; // [rsp+5D0h] [rbp+4D0h]
  struct _FILETIME v114; // [rsp+5D8h] [rbp+4D8h]
  struct _FILETIME v115; // [rsp+5E0h] [rbp+4E0h]
  SIZE_T v116; // [rsp+5F0h] [rbp+4F0h]
  SIZE_T v117; // [rsp+5F8h] [rbp+4F8h]
  ULONG v118; // [rsp+600h] [rbp+500h]
  SIZE_T v119; // [rsp+608h] [rbp+508h]
  SIZE_T v120; // [rsp+610h] [rbp+510h]
  SIZE_T v121; // [rsp+618h] [rbp+518h]
  SIZE_T v122; // [rsp+620h] [rbp+520h]
  SIZE_T v123; // [rsp+628h] [rbp+528h]
  SIZE_T v124; // [rsp+630h] [rbp+530h]
  SIZE_T v125; // [rsp+638h] [rbp+538h]
  SIZE_T v126; // [rsp+640h] [rbp+540h]
  SIZE_T v127; // [rsp+648h] [rbp+548h]
  char v128; // [rsp+654h] [rbp+554h] BYREF
  _VM_COUNTERS_EX v129; // [rsp+860h] [rbp+760h] BYREF
  struct _GUID v130; // [rsp+8C0h] [rbp+7C0h] BYREF
  _WORD v131[264]; // [rsp+8D0h] [rbp+7D0h] BYREF

  LODWORD(v67) = a3;
  memset_0(&v106, 0, 0x2C0u);
  v68 = 0;
  ProcessInformation = 0;
  v74 = 0;
  *(_OWORD *)dwProcessId = 0;
  CreationTime = 0;
  ExitTime = 0;
  KernelTime = 0;
  UserTime = 0;
  memset_0(&v129, 0, sizeof(v129));
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v97);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v101);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v95);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v82);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v93);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v85);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v91);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v79);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v99);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v89);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v87);
  v72 = 0;
  v130 = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&lpMem);
  v9 = a2 != 0;
  if ( v9 == (a1 != 0) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v7, v8);
  memset_0(v105, 0, sizeof(v105));
  v10 = &v106;
  v11 = v105;
  v12 = 5;
  do
  {
    *(_OWORD *)v10 = *v11;
    *((_OWORD *)v10 + 1) = v11[1];
    *((_OWORD *)v10 + 2) = v11[2];
    *((_OWORD *)v10 + 3) = v11[3];
    *((_OWORD *)v10 + 4) = v11[4];
    *((_OWORD *)v10 + 5) = v11[5];
    *((_OWORD *)v10 + 6) = v11[6];
    *((_OWORD *)v10 + 7) = v11[7];
    v10 += 32;
    v11 += 8;
    --v12;
  }
  while ( v12 );
  *(_OWORD *)v10 = *v11;
  *((_OWORD *)v10 + 1) = v11[1];
  *((_OWORD *)v10 + 2) = v11[2];
  *((_OWORD *)v10 + 3) = v11[3];
  CreationTime = 0;
  if ( a1 )
  {
    v13 = NtQueryInformationProcess(a1, ProcessBasicInformation, &ProcessInformation, 0x30u, 0);
    if ( v13 < 0 )
    {
      v14 = v13 | 0x10000000;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v16 = 14;
LABEL_10:
        WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_683aa959ceed38e99a300365342989fb_Traceguids, v14);
        goto LABEL_111;
      }
      goto LABEL_111;
    }
    v17 = a1;
LABEL_26:
    v23 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v97, L"%d", dwProcessId[0]);
    if ( v23 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_683aa959ceed38e99a300365342989fb_Traceguids,
        (unsigned int)v23);
    if ( a2 )
    {
      v24 = (wchar_t *)&v128;
    }
    else
    {
      ProcessPathFromHandle = UtilGetProcessPathFromHandle(v17);
      if ( ProcessPathFromHandle < 0 )
      {
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            WPP_683aa959ceed38e99a300365342989fb_Traceguids,
            (unsigned int)ProcessPathFromHandle);
        v26 = L"(unable to retrieve)";
LABEL_39:
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v95, v26);
        ProcessCommandLine = UtilGetProcessCommandLine(v17);
        if ( ProcessCommandLine < 0 )
        {
          v28 = ProcessCommandLine | 0x80000000;
        }
        else
        {
          v28 = 0;
          SystemTimeAsFileTime[0] = 0;
          v29 = (PWSTR *)___replace___BY0A__WU__generic_delete___BY0A__WU__generic_deallocate__MP6AXPEAX_Z1_CoTaskMemFree__YAX0_ZPEAX_tlx___tlx___utl__YAPEAPEA_WAEAV__unique_ptr___BY0A__WU__generic_delete___BY0A__WU__generic_deallocate__MP6AXPEAX_Z1_CoTaskMemFree__YAX0_ZPEAX_tlx___tlx___0__Z(SystemTimeAsFileTime);
          if ( SHGetKnownFolderPath(&FOLDERID_InternetCache, 0x4000u, 0, v29) >= 0 )
          {
            v32 = SystemTimeAsFileTime[0];
            if ( !*(_QWORD *)SystemTimeAsFileTime )
            {
              MicrosoftTelemetryAssertTriggeredNoArgs(v30, 0, v31);
              v32 = SystemTimeAsFileTime[0];
            }
            v33 = -1;
            do
              ++v33;
            while ( *(_WORD *)(*(_QWORD *)&v32 + 2 * v33) );
            *(struct _FILETIME *)&v62 = v32;
            *((_QWORD *)&v62 + 1) = v33;
            *(_QWORD *)&v61 = v82;
            *((_QWORD *)&v61 + 1) = (v83 - (__int64)v82) >> 1;
            v28 = (unsigned __int8)StringContainsOrdinalIgnoreCase(&v61, &v62);
            __ResetImpl___unique_ptr___BY0A__WU__generic_delete___BY0A__WU__generic_deallocate__MP6AXPEAX_Z1_CoTaskMemFree__YAX0_ZPEAX_tlx___tlx___utl__AEAAXPEA_W_Z(
              SystemTimeAsFileTime,
              0);
          }
          v131[0] = 0;
          if ( (unsigned int)GetTempPath2W(260, v131) - 1 <= 0x102 )
          {
            if ( !v131[0] )
              MicrosoftTelemetryAssertTriggeredNoArgs(0, v34, v35);
            v36 = -1;
            do
              ++v36;
            while ( v131[v36] );
            *(_QWORD *)&v61 = v131;
            *((_QWORD *)&v61 + 1) = v36;
            *(_QWORD *)&v62 = v82;
            *((_QWORD *)&v62 + 1) = (v83 - (__int64)v82) >> 1;
            if ( (unsigned __int8)StringContainsOrdinalIgnoreCase(&v62, &v61) )
              v28 |= 2u;
          }
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(SystemTimeAsFileTime);
        }
        tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v93, L"%08X", v28);
        if ( !(unsigned int)PackageUtility::IsPackagedApplication(v17) )
        {
LABEL_73:
          if ( a1 )
          {
            if ( !GetProcessTimes(a1, &CreationTime, &ExitTime, &KernelTime, &UserTime) )
            {
LABEL_75:
              LastError = GetLastError();
              if ( LastError > 0 )
                LastError = (unsigned __int16)LastError | 0x80070000;
              tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                v85,
                L"Error %08X",
                (unsigned int)LastError);
LABEL_78:
              v62 = 0;
              *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime = 0;
              *(_QWORD *)&v61 = L"ProcessInformation";
              *((_QWORD *)&v61 + 1) = 18;
              CXMLWriter::BeginElement(
                (_DWORD)a4,
                (unsigned int)&v61,
                (unsigned int)SystemTimeAsFileTime,
                0,
                (__int64)&v62);
              *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime = 0;
              *(LPVOID *)&v61 = v97[0];
              *((_QWORD *)&v61 + 1) = ((char *)v97[1] - (char *)v97[0]) >> 1;
              *(_QWORD *)&v62 = L"Pid";
              *((_QWORD *)&v62 + 1) = 3;
              LOBYTE(v43) = 1;
              CXMLWriter::BeginElement(
                (_DWORD)a4,
                (unsigned int)&v62,
                (unsigned int)&v61,
                v43,
                (__int64)SystemTimeAsFileTime);
              *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime = 0;
              *(LPVOID *)&v61 = v95[0];
              *((_QWORD *)&v61 + 1) = ((char *)v95[1] - (char *)v95[0]) >> 1;
              *(_QWORD *)&v62 = L"ImageName";
              *((_QWORD *)&v62 + 1) = 9;
              LOBYTE(v44) = 1;
              CXMLWriter::BeginElement(
                (_DWORD)a4,
                (unsigned int)&v62,
                (unsigned int)&v61,
                v44,
                (__int64)SystemTimeAsFileTime);
              *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime = 0;
              *(LPVOID *)&v61 = v93[0];
              *((_QWORD *)&v61 + 1) = ((char *)v93[1] - (char *)v93[0]) >> 1;
              *(_QWORD *)&v62 = L"CmdLineSignature";
              *((_QWORD *)&v62 + 1) = 16;
              LOBYTE(v45) = 1;
              CXMLWriter::BeginElement(
                (_DWORD)a4,
                (unsigned int)&v62,
                (unsigned int)&v61,
                v45,
                (__int64)SystemTimeAsFileTime);
              *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime = 0;
              *(LPVOID *)&v61 = v85[0];
              *((_QWORD *)&v61 + 1) = ((char *)v85[1] - (char *)v85[0]) >> 1;
              *(_QWORD *)&v62 = L"Uptime";
              *((_QWORD *)&v62 + 1) = 6;
              LOBYTE(v46) = 1;
              CXMLWriter::BeginElement(
                (_DWORD)a4,
                (unsigned int)&v62,
                (unsigned int)&v61,
                v46,
                (__int64)SystemTimeAsFileTime);
              v64[0] = 0;
              v65 = 0;
              UtilGetProcessArchitecture(v17, v64, &v65);
              if ( v64[0] == v65 || !v64[0] || (v48 = 1, !v65) )
                v48 = 0;
              v103[0] = L"guest";
              v103[1] = 0;
              v103[2] = v64[0];
              v103[3] = L"host";
              v103[4] = 0;
              v103[5] = v65;
              v49 = L"1";
              if ( !v48 )
                v49 = L"0";
              v50 = -1;
              do
                ++v50;
              while ( v49[v50] );
              *(_QWORD *)&v61 = v103;
              *((_QWORD *)&v61 + 1) = 2;
              *(_QWORD *)&v62 = v49;
              *((_QWORD *)&v62 + 1) = v50;
              SystemTimeAsFileTime[0] = (struct _FILETIME)L"Wow64";
              SystemTimeAsFileTime[1] = (struct _FILETIME)5LL;
              LOBYTE(v47) = 1;
              CXMLWriter::BeginElement(
                (_DWORD)a4,
                (unsigned int)SystemTimeAsFileTime,
                (unsigned int)&v62,
                v47,
                (__int64)&v61);
              v51 = 0;
              if ( a1 )
              {
                SystemTimeAsFileTime[0].dwLowDateTime = 0;
                if ( (int)GetProcessIptTraceSize(a1, SystemTimeAsFileTime) >= 0 )
                  v51 = SystemTimeAsFileTime[0].dwLowDateTime != 0;
              }
              else if ( a2 )
              {
                v61 = 0;
                if ( !(unsigned int)PssQuerySnapshot(a2, 10, &v61) )
                  v51 = DWORD2(v61) != 0;
              }
              tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v91, L"%u", v51);
              *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime = 0;
              *(LPVOID *)&v61 = v91[0];
              *((_QWORD *)&v61 + 1) = ((char *)v91[1] - (char *)v91[0]) >> 1;
              *(_QWORD *)&v62 = L"IptEnabled";
              *((_QWORD *)&v62 + 1) = 10;
              LOBYTE(v52) = 1;
              CXMLWriter::BeginElement(
                (_DWORD)a4,
                (unsigned int)&v62,
                (unsigned int)&v61,
                v52,
                (__int64)SystemTimeAsFileTime);
              if ( v79 != v80 )
              {
                v62 = 0;
                *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime = 0;
                *(_QWORD *)&v61 = L"Package";
                *((_QWORD *)&v61 + 1) = 7;
                CXMLWriter::BeginElement(
                  (_DWORD)a4,
                  (unsigned int)&v61,
                  (unsigned int)SystemTimeAsFileTime,
                  0,
                  (__int64)&v62);
                *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime = 0;
                *(_QWORD *)&v61 = v79;
                *((_QWORD *)&v61 + 1) = (v80 - (_BYTE *)v79) >> 1;
                *(_QWORD *)&v62 = L"FullName";
                *((_QWORD *)&v62 + 1) = 8;
                LOBYTE(v53) = 1;
                CXMLWriter::BeginElement(
                  (_DWORD)a4,
                  (unsigned int)&v62,
                  (unsigned int)&v61,
                  v53,
                  (__int64)SystemTimeAsFileTime);
                *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime = 0;
                *(LPVOID *)&v61 = v89[0];
                *((_QWORD *)&v61 + 1) = ((char *)v89[1] - (char *)v89[0]) >> 1;
                *(_QWORD *)&v62 = L"FamilyName";
                *((_QWORD *)&v62 + 1) = 10;
                LOBYTE(v54) = 1;
                CXMLWriter::BeginElement(
                  (_DWORD)a4,
                  (unsigned int)&v62,
                  (unsigned int)&v61,
                  v54,
                  (__int64)SystemTimeAsFileTime);
                *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime = 0;
                *(LPVOID *)&v61 = v87[0];
                *((_QWORD *)&v61 + 1) = ((char *)v87[1] - (char *)v87[0]) >> 1;
                *(_QWORD *)&v62 = L"PackageRelativeApplicationId";
                *((_QWORD *)&v62 + 1) = 28;
                LOBYTE(v55) = 1;
                CXMLWriter::BeginElement(
                  (_DWORD)a4,
                  (unsigned int)&v62,
                  (unsigned int)&v61,
                  v55,
                  (__int64)SystemTimeAsFileTime);
                tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&lpMem, L"%I64u", v72);
                *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime = 0;
                *(_QWORD *)&v61 = lpMem;
                *((_QWORD *)&v61 + 1) = (v77 - (__int64)lpMem) >> 1;
                *(_QWORD *)&v62 = L"HostId";
                *((_QWORD *)&v62 + 1) = 6;
                LOBYTE(v56) = 1;
                CXMLWriter::BeginElement(
                  (_DWORD)a4,
                  (unsigned int)&v62,
                  (unsigned int)&v61,
                  v56,
                  (__int64)SystemTimeAsFileTime);
                UtilGetStringFromGUID(&v130, &lpMem);
                *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime = 0;
                *(_QWORD *)&v61 = lpMem;
                *((_QWORD *)&v61 + 1) = (v77 - (__int64)lpMem) >> 1;
                *(_QWORD *)&v62 = L"ComponentId";
                *((_QWORD *)&v62 + 1) = 11;
                LOBYTE(v57) = 1;
                CXMLWriter::BeginElement(
                  (_DWORD)a4,
                  (unsigned int)&v62,
                  (unsigned int)&v61,
                  v57,
                  (__int64)SystemTimeAsFileTime);
                *(_QWORD *)&v61 = L"Package";
                *((_QWORD *)&v61 + 1) = 7;
                CXMLWriter::EndElement(a4, &v61);
              }
              if ( a1 )
              {
                memset_0(&v104, 0, sizeof(v104));
                v129 = v104;
                v58 = NtQueryInformationProcess(a1, ProcessVmCounters, &v129, 0x60u, 0);
                if ( v58 < 0 )
                {
                  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      23,
                      WPP_683aa959ceed38e99a300365342989fb_Traceguids,
                      v58 | 0x10000000u);
                  goto LABEL_105;
                }
              }
              else
              {
                if ( !a2 )
                  goto LABEL_105;
                v129.PeakVirtualSize = v116;
                v129.VirtualSize = v117;
                v129.PageFaultCount = v118;
                v129.PeakWorkingSetSize = v119;
                v129.WorkingSetSize = v120;
                v129.QuotaPeakPagedPoolUsage = v121;
                v129.QuotaPagedPoolUsage = v122;
                v129.QuotaPeakNonPagedPoolUsage = v123;
                v129.QuotaNonPagedPoolUsage = v124;
                v129.PagefileUsage = v125;
                v129.PeakPagefileUsage = v126;
                v129.PrivateUsage = v127;
              }
              UtilWriteProcessVmInfo(&v129, a4);
LABEL_105:
              if ( (_DWORD)v67 && a1 )
              {
                v59 = (char *)OpenProcess(0x410u, 0, dwProcessId[2]);
                v67 = v59;
                if ( v59 != (char *)-1LL && v59 + 1 != (char *)1 )
                {
                  v62 = 0;
                  *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime = 0;
                  *(_QWORD *)&v61 = L"ParentProcess";
                  *((_QWORD *)&v61 + 1) = 13;
                  CXMLWriter::BeginElement(
                    (_DWORD)a4,
                    (unsigned int)&v61,
                    (unsigned int)SystemTimeAsFileTime,
                    0,
                    (__int64)&v62);
                  UtilWriteProcessInfo(v59, 0, 0, a4);
                  *(_QWORD *)&v61 = L"ParentProcess";
                  *((_QWORD *)&v61 + 1) = 13;
                  CXMLWriter::EndElement(a4, &v61);
                }
                tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v67);
              }
              *(_QWORD *)&v61 = L"ProcessInformation";
              *((_QWORD *)&v61 + 1) = 18;
              CXMLWriter::EndElement(a4, &v61);
              v14 = 0;
              goto LABEL_111;
            }
          }
          else
          {
            if ( !a2 )
              goto LABEL_75;
            CreationTime = v112;
            ExitTime = v113;
            KernelTime = v114;
            UserTime = v115;
          }
          SystemTimeAsFileTime[0] = 0;
          GetSystemTimeAsFileTime(SystemTimeAsFileTime);
          tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            v85,
            L"%I64u",
            (*(_QWORD *)SystemTimeAsFileTime - *(_QWORD *)&CreationTime) / 0x2710uLL);
          goto LABEL_78;
        }
        ProcessPackageFullName = PackageUtility::GetProcessPackageFullName(v17);
        if ( ProcessPackageFullName < 0
          && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[14] & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            19,
            WPP_683aa959ceed38e99a300365342989fb_Traceguids,
            (unsigned int)ProcessPackageFullName);
        }
        ProcessApplicationId = PackageUtility::GetProcessApplicationId(v17);
        if ( ProcessApplicationId < 0 )
        {
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
          {
            v40 = 21;
            goto LABEL_68;
          }
        }
        else
        {
          ProcessApplicationId = PackageUtility::ParseApplicationId(v99[0], v89, v87);
          if ( ProcessApplicationId < 0 )
          {
            v39 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
            {
              v40 = 20;
LABEL_68:
              WPP_SF_d(
                *((_QWORD *)v39 + 2),
                v40,
                WPP_683aa959ceed38e99a300365342989fb_Traceguids,
                (unsigned int)ProcessApplicationId);
            }
          }
        }
        ProcessHostComponentIds = PackageUtility::GetProcessHostComponentIds(v17, &v72, &v130);
        if ( ProcessHostComponentIds < 0
          && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[14] & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            WPP_683aa959ceed38e99a300365342989fb_Traceguids,
            (unsigned int)ProcessHostComponentIds);
        }
        goto LABEL_73;
      }
      v24 = v101;
    }
    v26 = (wchar_t *)UtilPathTail(v24);
    goto LABEL_39;
  }
  v18 = PssQuerySnapshot(a2, 0, &v106);
  v14 = v18;
  if ( !v18 )
  {
    v19 = PssQuerySnapshot(a2, 1, &v68);
    v14 = v19;
    if ( v19 )
    {
      if ( v19 > 0 )
        v14 = (unsigned __int16)v19 | 0x80070000;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v16 = 16;
        goto LABEL_10;
      }
      goto LABEL_111;
    }
    *(_QWORD *)&ProcessInformation = v106;
    *((_QWORD *)&ProcessInformation + 1) = v107;
    *(_QWORD *)&v74 = v108;
    *((_QWORD *)&v74 + 1) = v109;
    *(_QWORD *)dwProcessId = v110;
    *(_QWORD *)&dwProcessId[2] = v111;
    v17 = v68;
    if ( !v68 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v21, v20, v22);
    goto LABEL_26;
  }
  if ( v18 > 0 )
    v14 = (unsigned __int16)v18 | 0x80070000;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v16 = 15;
    goto LABEL_10;
  }
LABEL_111:
  if ( lpMem != &v78 )
    HeapFree(g_hWerheap, 0, lpMem);
  if ( v87[0] != &v88 )
    HeapFree(g_hWerheap, 0, v87[0]);
  if ( v89[0] != &v90 )
    HeapFree(g_hWerheap, 0, v89[0]);
  if ( v99[0] != &v100 )
    HeapFree(g_hWerheap, 0, v99[0]);
  if ( v79 != &v81 )
    HeapFree(g_hWerheap, 0, v79);
  if ( v91[0] != &v92 )
    HeapFree(g_hWerheap, 0, v91[0]);
  if ( v85[0] != &v86 )
    HeapFree(g_hWerheap, 0, v85[0]);
  if ( v93[0] != &v94 )
    HeapFree(g_hWerheap, 0, v93[0]);
  if ( v82 != &v84 )
    HeapFree(g_hWerheap, 0, v82);
  if ( v95[0] != &v96 )
    HeapFree(g_hWerheap, 0, v95[0]);
  if ( v101 != (wchar_t *)&v102 )
    HeapFree(g_hWerheap, 0, v101);
  if ( v97[0] != &v98 )
    HeapFree(g_hWerheap, 0, v97[0]);
  return v14;
}

```

## disassembly

```asm
0x180021024  mov     [rsp-8+arg_10], rbx
0x180021029  push    rbp
0x18002102a  push    rsi
0x18002102b  push    rdi
0x18002102c  push    r12
0x18002102e  push    r13
0x180021030  push    r14
0x180021032  push    r15
0x180021034  lea     rbp, [rsp-9F0h]
0x18002103c  sub     rsp, 0AF0h
0x180021043  mov     rax, cs:__security_cookie
0x18002104a  xor     rax, rsp
0x18002104d  mov     [rbp+0A20h+var_40], rax
0x180021054  mov     r12, r9
0x180021057  mov     dword ptr [rsp+0B20h+var_AB0], r8d
0x18002105c  mov     r13, rdx
0x18002105f  mov     r15, rcx
0x180021062  mov     ebx, 2C0h
0x180021067  mov     r8d, ebx; Size
0x18002106a  xor     edx, edx; Val
0x18002106c  lea     rcx, [rbp+0A20h+var_580]; void *
0x180021073  call    memset_0
0x180021078  xor     r14d, r14d
0x18002107b  mov     [rsp+0B20h+var_AA8], r14
0x180021080  xorps   xmm0, xmm0
0x180021083  movups  [rbp+0A20h+ProcessInformation], xmm0
0x180021087  movups  [rbp+0A20h+var_A70], xmm0
0x18002108b  movups  xmmword ptr [rbp+0A20h+dwProcessId], xmm0
0x18002108f  mov     qword ptr [rsp+0B20h+CreationTime.dwLowDateTime], r14
0x180021094  mov     qword ptr [rbp+0A20h+ExitTime.dwLowDateTime], r14
0x180021098  mov     qword ptr [rbp+0A20h+KernelTime.dwLowDateTime], r14
0x18002109c  mov     qword ptr [rbp+0A20h+UserTime.dwLowDateTime], r14
0x1800210a0  xor     edx, edx; Val
0x1800210a2  lea     r8d, [r14+60h]; Size
0x1800210a6  lea     rcx, [rbp+0A20h+var_2C0]; void *
0x1800210ad  call    memset_0
0x1800210b2  lea     rcx, [rbp+0A20h+var_930]; void *
0x1800210b9  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800210be  nop
0x1800210bf  lea     rcx, [rbp+0A20h+var_8F0]; void *
0x1800210c6  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800210cb  nop
0x1800210cc  lea     rcx, [rbp+0A20h+var_950]; void *
0x1800210d3  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800210d8  nop
0x1800210d9  lea     rcx, [rbp+0A20h+var_A10]; void *
0x1800210dd  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800210e2  nop
0x1800210e3  lea     rcx, [rbp+0A20h+var_970]; void *
0x1800210ea  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800210ef  nop
0x1800210f0  lea     rcx, [rbp+0A20h+var_9F0]; void *
0x1800210f4  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800210f9  nop
0x1800210fa  lea     rcx, [rbp+0A20h+var_990]; void *
0x180021101  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180021106  nop
0x180021107  lea     rcx, [rbp+0A20h+var_A30]; void *
0x18002110b  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180021110  nop
0x180021111  lea     rcx, [rbp+0A20h+var_910]; void *
0x180021118  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18002111d  nop
0x18002111e  lea     rcx, [rbp+0A20h+var_9B0]; void *
0x180021122  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180021127  nop
0x180021128  lea     rcx, [rbp+0A20h+var_9D0]; void *
0x18002112c  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180021131  nop
0x180021132  mov     [rbp+0A20h+var_A88], r14
0x180021136  xorps   xmm0, xmm0
0x180021139  movups  xmmword ptr [rbp+0A20h+var_260.Data1], xmm0
0x180021140  lea     rcx, [rbp+0A20h+lpMem]; void *
0x180021144  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180021149  nop
0x18002114a  mov     ecx, r14d
0x18002114d  test    r13, r13
0x180021150  setnz   cl
0x180021153  mov     eax, r14d
0x180021156  test    r15, r15
0x180021159  setnz   al
0x18002115c  cmp     ecx, eax
0x18002115e  jnz     short loc_180021165
0x180021160  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180021165  mov     r8, rbx; Size
0x180021168  xor     edx, edx; Val
0x18002116a  lea     rcx, [rbp+0A20h+var_840]; void *
0x180021171  call    memset_0
0x180021176  lea     rax, [rbp+0A20h+var_580]
0x18002117d  lea     rcx, [rbp+0A20h+var_840]
0x180021184  mov     edx, 5
0x180021189  lea     r8d, [rdx+7Bh]
0x18002118d  movups  xmm0, xmmword ptr [rcx]
0x180021190  movups  xmmword ptr [rax], xmm0
0x180021193  movups  xmm1, xmmword ptr [rcx+10h]
0x180021197  movups  xmmword ptr [rax+10h], xmm1
0x18002119b  movups  xmm0, xmmword ptr [rcx+20h]
0x18002119f  movups  xmmword ptr [rax+20h], xmm0
0x1800211a3  movups  xmm1, xmmword ptr [rcx+30h]
0x1800211a7  movups  xmmword ptr [rax+30h], xmm1
0x1800211ab  movups  xmm0, xmmword ptr [rcx+40h]
0x1800211af  movups  xmmword ptr [rax+40h], xmm0
0x1800211b3  movups  xmm1, xmmword ptr [rcx+50h]
0x1800211b7  movups  xmmword ptr [rax+50h], xmm1
0x1800211bb  movups  xmm0, xmmword ptr [rcx+60h]
0x1800211bf  movups  xmmword ptr [rax+60h], xmm0
0x1800211c3  movups  xmm1, xmmword ptr [rcx+70h]
0x1800211c7  movups  xmmword ptr [rax+70h], xmm1
0x1800211cb  add     rax, r8
0x1800211ce  add     rcx, r8
0x1800211d1  sub     rdx, 1; ProcessInformationClass
0x1800211d5  jnz     short loc_18002118D
0x1800211d7  movups  xmm0, xmmword ptr [rcx]
0x1800211da  movups  xmmword ptr [rax], xmm0
0x1800211dd  movups  xmm1, xmmword ptr [rcx+10h]
0x1800211e1  movups  xmmword ptr [rax+10h], xmm1
0x1800211e5  movups  xmm0, xmmword ptr [rcx+20h]
0x1800211e9  movups  xmmword ptr [rax+20h], xmm0
0x1800211ed  movups  xmm1, xmmword ptr [rcx+30h]
0x1800211f1  movups  xmmword ptr [rax+30h], xmm1
0x1800211f5  mov     qword ptr [rsp+0B20h+CreationTime.dwLowDateTime], r14
0x1800211fa  lea     esi, [rdx+1]
0x1800211fd  test    r15, r15
0x180021200  jz      short loc_18002126C
0x180021202  mov     [rsp+0B20h+ReturnLength], r14; ReturnLength
0x180021207  lea     r9d, [rdx+30h]; ProcessInformationLength
0x18002120b  lea     r8, [rbp+0A20h+ProcessInformation]; ProcessInformation
0x18002120f  mov     rcx, r15; ProcessHandle
0x180021212  call    cs:__imp_NtQueryInformationProcess
0x180021219  nop     dword ptr [rax+rax+00h]
0x18002121e  mov     ebx, eax
0x180021220  test    eax, eax
0x180021222  jns     short loc_180021264
0x180021224  bts     ebx, 1Ch
0x180021228  lea     rdi, WPP_GLOBAL_Control
0x18002122f  mov     rcx, cs:WPP_GLOBAL_Control
0x180021236  cmp     rcx, rdi
0x180021239  jz      loc_180021F9D
0x18002123f  test    [rcx+1Ch], sil
0x180021243  jz      loc_180021F9D
0x180021249  lea     edx, [rsi+0Dh]
0x18002124c  mov     r9d, ebx
0x18002124f  lea     r8, WPP_683aa959ceed38e99a300365342989fb_Traceguids
0x180021256  mov     rcx, [rcx+10h]
0x18002125a  call    WPP_SF_d
0x18002125f  jmp     loc_180021F9D
0x180021264  mov     rbx, r15
0x180021267  jmp     loc_180021370
0x18002126c  mov     r9d, ebx
0x18002126f  lea     r8, [rbp+0A20h+var_580]
0x180021276  mov     rcx, r13
0x180021279  call    cs:__imp_PssQuerySnapshot
0x180021280  nop     dword ptr [rax+rax+00h]
0x180021285  mov     ebx, eax
0x180021287  test    eax, eax
0x180021289  jz      short loc_1800212BE
0x18002128b  jle     short loc_180021296
0x18002128d  movzx   ebx, ax
0x180021290  or      ebx, 80070000h
0x180021296  lea     rdi, WPP_GLOBAL_Control
0x18002129d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800212a4  cmp     rcx, rdi
0x1800212a7  jz      loc_180021F9D
0x1800212ad  test    [rcx+1Ch], sil
0x1800212b1  jz      loc_180021F9D
0x1800212b7  mov     edx, 0Fh
0x1800212bc  jmp     short loc_18002124C
0x1800212be  mov     r9d, 8
0x1800212c4  lea     r8, [rsp+0B20h+var_AA8]
0x1800212c9  mov     edx, esi
0x1800212cb  mov     rcx, r13
0x1800212ce  call    cs:__imp_PssQuerySnapshot
0x1800212d5  nop     dword ptr [rax+rax+00h]
0x1800212da  mov     ebx, eax
0x1800212dc  test    eax, eax
0x1800212de  jz      short loc_180021316
0x1800212e0  jle     short loc_1800212EB
0x1800212e2  movzx   ebx, ax
0x1800212e5  or      ebx, 80070000h
0x1800212eb  lea     rdi, WPP_GLOBAL_Control
0x1800212f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800212f9  cmp     rcx, rdi
0x1800212fc  jz      loc_180021F9D
0x180021302  test    [rcx+1Ch], sil
0x180021306  jz      loc_180021F9D
0x18002130c  mov     edx, 10h
0x180021311  jmp     loc_18002124C
0x180021316  xorps   xmm0, xmm0
0x180021319  movups  [rbp+0A20h+ProcessInformation], xmm0
0x18002131d  movups  [rbp+0A20h+var_A70], xmm0
0x180021321  movups  xmmword ptr [rbp+0A20h+dwProcessId], xmm0
0x180021325  mov     eax, [rbp+0A20h+var_580]
0x18002132b  mov     dword ptr [rbp+0A20h+ProcessInformation], eax
0x18002132e  mov     rax, [rbp+0A20h+var_578]
0x180021335  mov     qword ptr [rbp+0A20h+ProcessInformation+8], rax
0x180021339  mov     rax, [rbp+0A20h+var_570]
0x180021340  mov     qword ptr [rbp+0A20h+var_A70], rax
0x180021344  mov     eax, [rbp+0A20h+var_568]
0x18002134a  mov     dword ptr [rbp+0A20h+var_A70+8], eax
0x18002134d  mov     eax, [rbp+0A20h+var_564]
0x180021353  mov     qword ptr [rbp+0A20h+dwProcessId], rax
0x180021357  mov     eax, [rbp+0A20h+var_560]
0x18002135d  mov     qword ptr [rbp+0A20h+dwProcessId+8], rax
0x180021361  mov     rbx, [rsp+0B20h+var_AA8]
0x180021366  test    rbx, rbx
0x180021369  jnz     short loc_180021370
0x18002136b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180021370  mov     r8d, [rbp+0A20h+dwProcessId]
0x180021374  lea     rdx, aD; "%d"
0x18002137b  lea     rcx, [rbp+0A20h+var_930]
0x180021382  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180021387  lea     rsi, WPP_683aa959ceed38e99a300365342989fb_Traceguids
0x18002138e  lea     rdi, WPP_GLOBAL_Control
0x180021395  test    eax, eax
0x180021397  jns     short loc_1800213BF
0x180021399  mov     rcx, cs:WPP_GLOBAL_Control
0x1800213a0  cmp     rcx, rdi
0x1800213a3  jz      short loc_1800213BF
0x1800213a5  test    byte ptr [rcx+1Ch], 2
0x1800213a9  jz      short loc_1800213BF
0x1800213ab  mov     edx, 11h
0x1800213b0  mov     r9d, eax
0x1800213b3  mov     r8, rsi
0x1800213b6  mov     rcx, [rcx+10h]
0x1800213ba  call    WPP_SF_d
0x1800213bf  test    r13, r13
0x1800213c2  jz      short loc_1800213CD
0x1800213c4  lea     rcx, [rbp+0A20h+var_4CC]
0x1800213cb  jmp     short loc_180021416
0x1800213cd  lea     rdx, [rbp+0A20h+var_8F0]
0x1800213d4  mov     rcx, rbx; hProcess
0x1800213d7  call    ?UtilGetProcessPathFromHandle@@YAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetProcessPathFromHandle(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1800213dc  test    eax, eax
0x1800213de  jns     short loc_18002140F
0x1800213e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800213e7  cmp     rcx, rdi
0x1800213ea  jz      short loc_180021406
0x1800213ec  test    byte ptr [rcx+1Ch], 2
0x1800213f0  jz      short loc_180021406
0x1800213f2  mov     edx, 12h
0x1800213f7  mov     r9d, eax
0x1800213fa  mov     r8, rsi
0x1800213fd  mov     rcx, [rcx+10h]
0x180021401  call    WPP_SF_d
0x180021406  lea     rax, aUnableToRetrie; "(unable to retrieve)"
0x18002140d  jmp     short loc_18002141B
0x18002140f  mov     rcx, [rbp+0A20h+var_8F0]; wchar_t *
0x180021416  call    ?UtilPathTail@@YAPEB_WPEB_W@Z; UtilPathTail(wchar_t const *)
0x18002141b  mov     rdx, rax
0x18002141e  lea     rcx, [rbp+0A20h+var_950]
0x180021425  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18002142a  lea     rdx, [rbp+0A20h+var_A10]
0x18002142e  mov     rcx, rbx; hProcess
0x180021431  call    ?UtilGetProcessCommandLine@@YAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetProcessCommandLine(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180021436  mov     r14d, eax
0x180021439  xor     eax, eax
0x18002143b  test    r14d, r14d
0x18002143e  js      loc_18002157A
0x180021444  mov     r14d, eax
0x180021447  mov     qword ptr [rsp+0B20h+SystemTimeAsFileTime.dwLowDateTime], rax
0x18002144c  lea     rcx, [rsp+0B20h+SystemTimeAsFileTime]
0x180021451  call    ??$replace@$$BY0A@_WU?$generic_delete@$$BY0A@_WU?$generic_deallocate@$MP6AXPEAX@Z1?CoTaskMemFree@@YAX0@ZPEAX@tlx@@@tlx@@@utl@@YAPEAPEA_WAEAV?$unique_ptr@$$BY0A@_WU?$generic_delete@$$BY0A@_WU?$generic_deallocate@$MP6AXPEAX@Z1?CoTaskMemFree@@YAX0@ZPEAX@tlx@@@tlx@@@0@@Z
0x180021456  mov     r9, rax; ppszPath
0x180021459  xor     r8d, r8d; hToken
0x18002145c  mov     edx, 4000h; dwFlags
0x180021461  lea     rcx, FOLDERID_InternetCache; rfid
0x180021468  call    cs:__imp_SHGetKnownFolderPath
0x18002146f  nop     dword ptr [rax+rax+00h]
0x180021474  xor     edx, edx
0x180021476  test    eax, eax
0x180021478  js      short loc_1800214E0
0x18002147a  mov     rax, qword ptr [rsp+0B20h+SystemTimeAsFileTime.dwLowDateTime]
0x18002147f  test    rax, rax
0x180021482  jnz     short loc_180021490
0x180021484  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180021489  mov     rax, qword ptr [rsp+0B20h+SystemTimeAsFileTime.dwLowDateTime]
0x18002148e  xor     edx, edx
0x180021490  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180021494  inc     rcx
0x180021497  cmp     [rax+rcx*2], dx
0x18002149b  jnz     short loc_180021494
0x18002149d  mov     qword ptr [rsp+0B20h+var_AE0], rax
0x1800214a2  mov     qword ptr [rsp+0B20h+var_AE0+8], rcx
0x1800214a7  mov     rax, [rbp+0A20h+var_A10]
0x1800214ab  mov     qword ptr [rsp+0B20h+var_AF0], rax
0x1800214b0  mov     rcx, [rbp+0A20h+var_A08]
0x1800214b4  sub     rcx, rax
0x1800214b7  sar     rcx, 1
0x1800214ba  mov     qword ptr [rsp+0B20h+var_AF0+8], rcx
0x1800214bf  lea     rdx, [rsp+0B20h+var_AE0]
0x1800214c4  lea     rcx, [rsp+0B20h+var_AF0]
0x1800214c9  call    ?StringContainsOrdinalIgnoreCase@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0@Z; StringContainsOrdinalIgnoreCase(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x1800214ce  movzx   r14d, al
0x1800214d2  xor     edx, edx
0x1800214d4  lea     rcx, [rsp+0B20h+SystemTimeAsFileTime]
0x1800214d9  call    ?_ResetImpl@?$unique_ptr@$$BY0A@_WU?$generic_delete@$$BY0A@_WU?$generic_deallocate@$MP6AXPEAX@Z1?CoTaskMemFree@@YAX0@ZPEAX@tlx@@@tlx@@@utl@@AEAAXPEA_W@Z
0x1800214de  xor     edx, edx
0x1800214e0  mov     [rbp+0A20h+var_250], dx
0x1800214e7  lea     rdx, [rbp+0A20h+var_250]
0x1800214ee  mov     ecx, 104h
  ... truncated ...
```
