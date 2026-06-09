# UtilWriteProcessInfo(void *,HPSS__ *,int,CXMLWriter *)

- ea: `0x18002054c`
- end: `0x18002162c`
- name: `?UtilWriteProcessInfo@@YAJPEAXPEAUHPSS__@@HPEAVCXMLWriter@@@Z`
- size: `4320`
- prototype: `__int64 __fastcall(void *, struct HPSS__ *, int, struct CXMLWriter *)`
- caller_count: `2`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002054c`
- `0x180090dac`

## callees

- `0x180007e10`
- `0x18000bc10`
- `0x18000c390`
- `0x18000cc74`
- `0x18001fe24`
- `0x18002054c`
- `0x180021634`
- `0x18002de18`
- `0x180039874`
- `0x18003bf14`
- `0x180040f08`
- `0x18004144c`
- `0x180041588`
- `0x180041830`
- `0x180049458`
- `0x180049ee4`
- `0x18004c520`
- `0x180050db0`
- `0x1800517cc`
- `0x180077f8c`
- `0x18007f408`
- `0x180097e84`
- `0x1800a5aa8`
- `0x1800a5cb4`
- `0x1800a5e04`
- `0x1800a5ffc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021494`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800214b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800214d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800214f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021511`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021534`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021551`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021574`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021591`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800215b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800215d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800215fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021494`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800214b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800214d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800214f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021511`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021534`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021551`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021574`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021591`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800215b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800215d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800215fa`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x180020bb0`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x180020bb0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180020eee`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180020eee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020bbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020bbe`
- `ntdll!NtQueryInformationProcess` at `0x180020737`
- `ntdll!NtQueryInformationProcess` at `0x1800212a9`
- `ntdll!NtQueryInformationProcess` at `0x180020737`
- `ntdll!NtQueryInformationProcess` at `0x1800212a9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800213c9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800213c9`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180020798`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x1800207e7`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180020f5d`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180020798`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x1800207e7`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180020f5d`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180020a07`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180020a07`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180020978`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180020978`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800209ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800209ec`

## string_xrefs

- `0x1800211d3`: `ComponentId`

## pseudocode

```c
__int64 __fastcall UtilWriteProcessInfo(void *a1, struct HPSS__ *a2, int a3, struct CXMLWriter *a4)
{
  unsigned int *v7; // rax
  _OWORD *v8; // rcx
  __int64 v9; // rdx
  NTSTATUS v10; // ebx
  unsigned int v11; // ebx
  wchar_t *v12; // rcx
  __int64 v13; // rdx
  void *v14; // r14
  int v15; // eax
  int v16; // eax
  int v17; // eax
  wchar_t *v18; // rcx
  int ProcessPathFromHandle; // eax
  const wchar_t *v20; // rax
  int ProcessCommandLine; // ebx
  unsigned int v22; // ebx
  PWSTR *v23; // rax
  _WORD *v24; // rax
  __int64 v25; // rcx
  void *v26; // rcx
  __int64 v27; // rax
  unsigned int v28; // ebx
  int ProcessPackageFullName; // eax
  int ProcessApplicationId; // eax
  wchar_t *v31; // rcx
  __int64 v32; // rdx
  int ProcessHostComponentIds; // eax
  signed int LastError; // eax
  char v35; // dl
  const wchar_t *v36; // rcx
  __int64 v37; // rax
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 v40; // r8
  __int64 v41; // r9
  NTSTATUS v42; // eax
  char *v43; // rbx
  __int64 v44; // r8
  __int64 v45; // r9
  __int128 v47; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v48; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v50[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v51; // [rsp+64h] [rbp-9Ch] BYREF
  struct _FILETIME CreationTime; // [rsp+68h] [rbp-98h] BYREF
  char *v53; // [rsp+70h] [rbp-90h] BYREF
  void *v54; // [rsp+78h] [rbp-88h] BYREF
  struct _FILETIME ExitTime; // [rsp+80h] [rbp-80h] BYREF
  struct _FILETIME KernelTime; // [rsp+88h] [rbp-78h] BYREF
  struct _FILETIME UserTime; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v58; // [rsp+98h] [rbp-68h] BYREF
  __int128 ProcessInformation; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v60; // [rsp+B0h] [rbp-50h]
  DWORD dwProcessId[4]; // [rsp+C0h] [rbp-40h]
  LPVOID lpMem; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v63; // [rsp+D8h] [rbp-28h]
  char v64; // [rsp+E0h] [rbp-20h] BYREF
  LPVOID v65; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE *v66; // [rsp+F8h] [rbp-8h]
  char v67; // [rsp+100h] [rbp+0h] BYREF
  LPVOID v68; // [rsp+110h] [rbp+10h] BYREF
  __int64 v69; // [rsp+118h] [rbp+18h]
  char v70; // [rsp+120h] [rbp+20h] BYREF
  LPVOID v71[2]; // [rsp+130h] [rbp+30h] BYREF
  char v72; // [rsp+140h] [rbp+40h] BYREF
  LPVOID v73[2]; // [rsp+150h] [rbp+50h] BYREF
  char v74; // [rsp+160h] [rbp+60h] BYREF
  LPVOID v75[2]; // [rsp+170h] [rbp+70h] BYREF
  char v76; // [rsp+180h] [rbp+80h] BYREF
  LPVOID v77[2]; // [rsp+190h] [rbp+90h] BYREF
  char v78; // [rsp+1A0h] [rbp+A0h] BYREF
  LPVOID v79[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  char v80; // [rsp+1C0h] [rbp+C0h] BYREF
  LPVOID v81[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  char v82; // [rsp+1E0h] [rbp+E0h] BYREF
  LPVOID v83[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  char v84; // [rsp+200h] [rbp+100h] BYREF
  LPVOID v85[2]; // [rsp+210h] [rbp+110h] BYREF
  char v86; // [rsp+220h] [rbp+120h] BYREF
  wchar_t *v87; // [rsp+230h] [rbp+130h] BYREF
  char v88; // [rsp+240h] [rbp+140h] BYREF
  _QWORD v89[6]; // [rsp+250h] [rbp+150h] BYREF
  _VM_COUNTERS_EX v90; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v91[704]; // [rsp+2E0h] [rbp+1E0h] BYREF
  unsigned int v92; // [rsp+5A0h] [rbp+4A0h] BYREF
  __int64 v93; // [rsp+5A8h] [rbp+4A8h]
  __int64 v94; // [rsp+5B0h] [rbp+4B0h]
  unsigned int v95; // [rsp+5B8h] [rbp+4B8h]
  unsigned int v96; // [rsp+5BCh] [rbp+4BCh]
  unsigned int v97; // [rsp+5C0h] [rbp+4C0h]
  struct _FILETIME v98; // [rsp+5C8h] [rbp+4C8h]
  struct _FILETIME v99; // [rsp+5D0h] [rbp+4D0h]
  struct _FILETIME v100; // [rsp+5D8h] [rbp+4D8h]
  struct _FILETIME v101; // [rsp+5E0h] [rbp+4E0h]
  SIZE_T v102; // [rsp+5F0h] [rbp+4F0h]
  SIZE_T v103; // [rsp+5F8h] [rbp+4F8h]
  ULONG v104; // [rsp+600h] [rbp+500h]
  SIZE_T v105; // [rsp+608h] [rbp+508h]
  SIZE_T v106; // [rsp+610h] [rbp+510h]
  SIZE_T v107; // [rsp+618h] [rbp+518h]
  SIZE_T v108; // [rsp+620h] [rbp+520h]
  SIZE_T v109; // [rsp+628h] [rbp+528h]
  SIZE_T v110; // [rsp+630h] [rbp+530h]
  SIZE_T v111; // [rsp+638h] [rbp+538h]
  SIZE_T v112; // [rsp+640h] [rbp+540h]
  SIZE_T v113; // [rsp+648h] [rbp+548h]
  char v114; // [rsp+654h] [rbp+554h] BYREF
  _VM_COUNTERS_EX v115; // [rsp+860h] [rbp+760h] BYREF
  struct _GUID v116; // [rsp+8C0h] [rbp+7C0h] BYREF
  _WORD v117[264]; // [rsp+8D0h] [rbp+7D0h] BYREF

  LODWORD(v53) = a3;
  memset_0(&v92, 0, 0x2C0u);
  v54 = 0;
  ProcessInformation = 0;
  v60 = 0;
  *(_OWORD *)dwProcessId = 0;
  CreationTime = 0;
  ExitTime = 0;
  KernelTime = 0;
  UserTime = 0;
  memset_0(&v115, 0, sizeof(v115));
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v83);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v87);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v81);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v68);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v79);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v71);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v77);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v65);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v85);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v75);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v73);
  v58 = 0;
  v116 = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&lpMem);
  if ( (a2 != 0) == (a1 != 0) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  memset_0(v91, 0, sizeof(v91));
  v7 = &v92;
  v8 = v91;
  v9 = 5;
  do
  {
    *(_OWORD *)v7 = *v8;
    *((_OWORD *)v7 + 1) = v8[1];
    *((_OWORD *)v7 + 2) = v8[2];
    *((_OWORD *)v7 + 3) = v8[3];
    *((_OWORD *)v7 + 4) = v8[4];
    *((_OWORD *)v7 + 5) = v8[5];
    *((_OWORD *)v7 + 6) = v8[6];
    *((_OWORD *)v7 + 7) = v8[7];
    v7 += 32;
    v8 += 8;
    --v9;
  }
  while ( v9 );
  *(_OWORD *)v7 = *v8;
  *((_OWORD *)v7 + 1) = v8[1];
  *((_OWORD *)v7 + 2) = v8[2];
  *((_OWORD *)v7 + 3) = v8[3];
  CreationTime = 0;
  if ( a1 )
  {
    v10 = NtQueryInformationProcess(a1, ProcessBasicInformation, &ProcessInformation, 0x30u, 0);
    if ( v10 < 0 )
    {
      v11 = v10 | 0x10000000;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v13 = 14;
LABEL_10:
        WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_683aa959ceed38e99a300365342989fb_Traceguids, v11);
        goto LABEL_114;
      }
      goto LABEL_114;
    }
    v14 = a1;
LABEL_26:
    v17 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v83, L"%d", dwProcessId[0]);
    if ( v17 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_683aa959ceed38e99a300365342989fb_Traceguids,
        (unsigned int)v17);
    if ( a2 )
    {
      v18 = (wchar_t *)&v114;
    }
    else
    {
      ProcessPathFromHandle = UtilGetProcessPathFromHandle(v14);
      if ( ProcessPathFromHandle < 0 )
      {
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            WPP_683aa959ceed38e99a300365342989fb_Traceguids,
            (unsigned int)ProcessPathFromHandle);
        v20 = L"(unable to retrieve)";
LABEL_39:
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v81, v20);
        ProcessCommandLine = UtilGetProcessCommandLine(v14, (__int64)&v68);
        if ( ProcessCommandLine < 0 )
        {
          v22 = ProcessCommandLine | 0x80000000;
        }
        else
        {
          v22 = 0;
          pv[0] = 0;
          v23 = (PWSTR *)___replace___BY0A__WU__generic_delete___BY0A__WU__generic_deallocate__MP6AXPEAX_Z1_CoTaskMemFree__YAX0_ZPEAX_tlx___tlx___utl__YAPEAPEA_WAEAV__unique_ptr___BY0A__WU__generic_delete___BY0A__WU__generic_deallocate__MP6AXPEAX_Z1_CoTaskMemFree__YAX0_ZPEAX_tlx___tlx___0__Z(pv);
          if ( SHGetKnownFolderPath(&FOLDERID_InternetCache, 0x4000u, 0, v23) >= 0 )
          {
            v24 = pv[0];
            if ( !pv[0] )
            {
              MicrosoftTelemetryAssertTriggeredNoArgs();
              v24 = pv[0];
            }
            v25 = -1;
            do
              ++v25;
            while ( v24[v25] );
            *(_QWORD *)&v48 = v24;
            *((_QWORD *)&v48 + 1) = v25;
            *(_QWORD *)&v47 = v68;
            *((_QWORD *)&v47 + 1) = (v69 - (__int64)v68) >> 1;
            v22 = (unsigned __int8)StringContainsOrdinalIgnoreCase(&v47, &v48);
            v26 = pv[0];
            pv[0] = 0;
            if ( v26 )
              CoTaskMemFree(v26);
          }
          v117[0] = 0;
          if ( (unsigned int)GetTempPath2W(260, v117) - 1 <= 0x102 )
          {
            if ( !v117[0] )
              MicrosoftTelemetryAssertTriggeredNoArgs();
            v27 = -1;
            do
              ++v27;
            while ( v117[v27] );
            *(_QWORD *)&v47 = v117;
            *((_QWORD *)&v47 + 1) = v27;
            *(_QWORD *)&v48 = v68;
            *((_QWORD *)&v48 + 1) = (v69 - (__int64)v68) >> 1;
            if ( (unsigned __int8)StringContainsOrdinalIgnoreCase(&v48, &v47) )
              v22 |= 2u;
          }
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(pv);
        }
        tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v79, L"%08X", v22);
        v28 = 0;
        if ( !(unsigned int)PackageUtility::IsPackagedApplication(v14) )
        {
LABEL_74:
          if ( a1 )
          {
            if ( !GetProcessTimes(a1, &CreationTime, &ExitTime, &KernelTime, &UserTime) )
            {
LABEL_76:
              LastError = GetLastError();
              if ( LastError > 0 )
                LastError = (unsigned __int16)LastError | 0x80070000;
              tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                v71,
                L"Error %08X",
                (unsigned int)LastError);
LABEL_79:
              v48 = 0;
              *(_OWORD *)pv = 0;
              *(_QWORD *)&v47 = L"ProcessInformation";
              *((_QWORD *)&v47 + 1) = 18;
              CXMLWriter::BeginElement((__int64)a4, &v47, (__int128 *)pv, 0, &v48);
              *(_OWORD *)pv = 0;
              *(LPVOID *)&v47 = v83[0];
              *((_QWORD *)&v47 + 1) = ((char *)v83[1] - (char *)v83[0]) >> 1;
              *(_QWORD *)&v48 = L"Pid";
              *((_QWORD *)&v48 + 1) = 3;
              CXMLWriter::BeginElement((__int64)a4, &v48, &v47, 1, (__int128 *)pv);
              *(_OWORD *)pv = 0;
              *(LPVOID *)&v47 = v81[0];
              *((_QWORD *)&v47 + 1) = ((char *)v81[1] - (char *)v81[0]) >> 1;
              *(_QWORD *)&v48 = L"ImageName";
              *((_QWORD *)&v48 + 1) = 9;
              CXMLWriter::BeginElement((__int64)a4, &v48, &v47, 1, (__int128 *)pv);
              *(_OWORD *)pv = 0;
              *(LPVOID *)&v47 = v79[0];
              *((_QWORD *)&v47 + 1) = ((char *)v79[1] - (char *)v79[0]) >> 1;
              *(_QWORD *)&v48 = L"CmdLineSignature";
              *((_QWORD *)&v48 + 1) = 16;
              CXMLWriter::BeginElement((__int64)a4, &v48, &v47, 1, (__int128 *)pv);
              *(_OWORD *)pv = 0;
              *(LPVOID *)&v47 = v71[0];
              *((_QWORD *)&v47 + 1) = ((char *)v71[1] - (char *)v71[0]) >> 1;
              *(_QWORD *)&v48 = L"Uptime";
              *((_QWORD *)&v48 + 1) = 6;
              CXMLWriter::BeginElement((__int64)a4, &v48, &v47, 1, (__int128 *)pv);
              v50[0] = 0;
              v51 = 0;
              UtilGetProcessArchitecture(v14, v50, &v51);
              if ( v50[0] == v51 || !v50[0] || (v35 = 1, !v51) )
                v35 = 0;
              v89[0] = L"guest";
              v89[1] = 0;
              v89[2] = v50[0];
              v89[3] = L"host";
              v89[4] = 0;
              v89[5] = v51;
              v36 = L"1";
              if ( !v35 )
                v36 = L"0";
              v37 = -1;
              do
                ++v37;
              while ( v36[v37] );
              *(_QWORD *)&v47 = v89;
              *((_QWORD *)&v47 + 1) = 2;
              *(_QWORD *)&v48 = v36;
              *((_QWORD *)&v48 + 1) = v37;
              pv[0] = L"Wow64";
              pv[1] = (LPVOID)5;
              CXMLWriter::BeginElement((__int64)a4, (__int128 *)pv, &v48, 1, &v47);
              if ( a1 )
              {
                LODWORD(pv[0]) = 0;
                if ( (int)GetProcessIptTraceSize(a1, pv) >= 0 && LODWORD(pv[0]) )
                  v28 = 1;
              }
              else if ( a2 )
              {
                v47 = 0;
                if ( !(unsigned int)PssQuerySnapshot(a2, 10, &v47, 16) )
                {
                  if ( DWORD2(v47) )
                    v28 = 1;
                }
              }
              tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v77, L"%u", v28);
              *(_OWORD *)pv = 0;
              *(LPVOID *)&v47 = v77[0];
              *((_QWORD *)&v47 + 1) = ((char *)v77[1] - (char *)v77[0]) >> 1;
              *(_QWORD *)&v48 = L"IptEnabled";
              *((_QWORD *)&v48 + 1) = 10;
              CXMLWriter::BeginElement((__int64)a4, &v48, &v47, 1, (__int128 *)pv);
              if ( v65 != v66 )
              {
                v48 = 0;
                *(_OWORD *)pv = 0;
                *(_QWORD *)&v47 = L"Package";
                *((_QWORD *)&v47 + 1) = 7;
                CXMLWriter::BeginElement((__int64)a4, &v47, (__int128 *)pv, 0, &v48);
                *(_OWORD *)pv = 0;
                *(_QWORD *)&v47 = v65;
                *((_QWORD *)&v47 + 1) = (v66 - (_BYTE *)v65) >> 1;
                *(_QWORD *)&v48 = L"FullName";
                *((_QWORD *)&v48 + 1) = 8;
                CXMLWriter::BeginElement((__int64)a4, &v48, &v47, 1, (__int128 *)pv);
                *(_OWORD *)pv = 0;
                *(LPVOID *)&v47 = v75[0];
                *((_QWORD *)&v47 + 1) = ((char *)v75[1] - (char *)v75[0]) >> 1;
                *(_QWORD *)&v48 = L"FamilyName";
                *((_QWORD *)&v48 + 1) = 10;
                CXMLWriter::BeginElement((__int64)a4, &v48, &v47, 1, (__int128 *)pv);
                *(_OWORD *)pv = 0;
                *(LPVOID *)&v47 = v73[0];
                *((_QWORD *)&v47 + 1) = ((char *)v73[1] - (char *)v73[0]) >> 1;
                *(_QWORD *)&v48 = L"PackageRelativeApplicationId";
                *((_QWORD *)&v48 + 1) = 28;
                CXMLWriter::BeginElement((__int64)a4, &v48, &v47, 1, (__int128 *)pv);
                tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&lpMem, L"%I64u", v58);
                *(_OWORD *)pv = 0;
                *(_QWORD *)&v47 = lpMem;
                *((_QWORD *)&v47 + 1) = (v63 - (__int64)lpMem) >> 1;
                *(_QWORD *)&v48 = L"HostId";
                *((_QWORD *)&v48 + 1) = 6;
                CXMLWriter::BeginElement((__int64)a4, &v48, &v47, 1, (__int128 *)pv);
                UtilGetStringFromGUID(&v116, &lpMem);
                *(_OWORD *)pv = 0;
                *(_QWORD *)&v47 = lpMem;
                *((_QWORD *)&v47 + 1) = (v63 - (__int64)lpMem) >> 1;
                *(_QWORD *)&v48 = L"ComponentId";
                *((_QWORD *)&v48 + 1) = 11;
                CXMLWriter::BeginElement((__int64)a4, &v48, &v47, 1, (__int128 *)pv);
                *(_QWORD *)&v47 = L"Package";
                *((_QWORD *)&v47 + 1) = 7;
                CXMLWriter::EndElement(a4, &v47, v40, v41);
              }
              if ( a1 )
              {
                memset_0(&v90, 0, sizeof(v90));
                v115 = v90;
                v42 = NtQueryInformationProcess(a1, ProcessVmCounters, &v115, 0x60u, 0);
                if ( v42 < 0 )
                {
                  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      23,
                      WPP_683aa959ceed38e99a300365342989fb_Traceguids,
                      v42 | 0x10000000u);
                  goto LABEL_108;
                }
              }
              else
              {
                if ( !a2 )
                  goto LABEL_108;
                v115.PeakVirtualSize = v102;
                v115.VirtualSize = v103;
                v115.PageFaultCount = v104;
                v115.PeakWorkingSetSize = v105;
                v115.WorkingSetSize = v106;
                v115.QuotaPeakPagedPoolUsage = v107;
                v115.QuotaPagedPoolUsage = v108;
                v115.QuotaPeakNonPagedPoolUsage = v109;
                v115.QuotaNonPagedPoolUsage = v110;
                v115.PagefileUsage = v111;
                v115.PeakPagefileUsage = v112;
                v115.PrivateUsage = v113;
              }
              UtilWriteProcessVmInfo(&v115, a4);
LABEL_108:
              if ( (_DWORD)v53 && a1 )
              {
                v43 = (char *)OpenProcess(0x410u, 0, dwProcessId[2]);
                v53 = v43;
                if ( v43 != (char *)-1LL && v43 + 1 != (char *)1 )
                {
                  v48 = 0;
                  *(_OWORD *)pv = 0;
                  *(_QWORD *)&v47 = L"ParentProcess";
                  *((_QWORD *)&v47 + 1) = 13;
                  CXMLWriter::BeginElement((__int64)a4, &v47, (__int128 *)pv, 0, &v48);
                  UtilWriteProcessInfo(v43, 0, 0, a4);
                  *(_QWORD *)&v47 = L"ParentProcess";
                  *((_QWORD *)&v47 + 1) = 13;
                  CXMLWriter::EndElement(a4, &v47, v44, v45);
                }
                tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v53);
              }
              *(_QWORD *)&v47 = L"ProcessInformation";
              *((_QWORD *)&v47 + 1) = 18;
              CXMLWriter::EndElement(a4, &v47, v38, v39);
              v11 = 0;
              goto LABEL_114;
            }
          }
          else
          {
            if ( !a2 )
              goto LABEL_76;
            CreationTime = v98;
            ExitTime = v99;
            KernelTime = v100;
            UserTime = v101;
          }
          pv[0] = 0;
          GetSystemTimeAsFileTime((LPFILETIME)pv);
          tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            v71,
            L"%I64u",
            ((unsigned __int64)pv[0] - *(_QWORD *)&CreationTime) / 0x2710);
          goto LABEL_79;
        }
        ProcessPackageFullName = PackageUtility::GetProcessPackageFullName(v14, (__int64)&v65);
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
        ProcessApplicationId = PackageUtility::GetProcessApplicationId(v14, (__int64)v85);
        if ( ProcessApplicationId < 0 )
        {
          v31 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
          {
            v32 = 21;
            goto LABEL_69;
          }
        }
        else
        {
          ProcessApplicationId = PackageUtility::ParseApplicationId((const wchar_t *)v85[0], (__int64)v75, (__int64)v73);
          if ( ProcessApplicationId < 0 )
          {
            v31 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
            {
              v32 = 20;
LABEL_69:
              WPP_SF_d(
                *((_QWORD *)v31 + 2),
                v32,
                WPP_683aa959ceed38e99a300365342989fb_Traceguids,
                (unsigned int)ProcessApplicationId);
            }
          }
        }
        ProcessHostComponentIds = PackageUtility::GetProcessHostComponentIds(v14, &v58, &v116);
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
        goto LABEL_74;
      }
      v18 = v87;
    }
    v20 = UtilPathTail(v18);
    goto LABEL_39;
  }
  v15 = PssQuerySnapshot(a2, 0, &v92, 704);
  v11 = v15;
  if ( !v15 )
  {
    v16 = PssQuerySnapshot(a2, 1, &v54, 8);
    v11 = v16;
    if ( v16 )
    {
      if ( v16 > 0 )
        v11 = (unsigned __int16)v16 | 0x80070000;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v13 = 16;
        goto LABEL_10;
      }
      goto LABEL_114;
    }
    *(_QWORD *)&ProcessInformation = v92;
    *((_QWORD *)&ProcessInformation + 1) = v93;
    *(_QWORD *)&v60 = v94;
    *((_QWORD *)&v60 + 1) = v95;
    *(_QWORD *)dwProcessId = v96;
    *(_QWORD *)&dwProcessId[2] = v97;
    v14 = v54;
    if ( !v54 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    goto LABEL_26;
  }
  if ( v15 > 0 )
    v11 = (unsigned __int16)v15 | 0x80070000;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v13 = 15;
    goto LABEL_10;
  }
LABEL_114:
  if ( lpMem != &v64 )
    HeapFree(g_hWerheap, 0, lpMem);
  if ( v73[0] != &v74 )
    HeapFree(g_hWerheap, 0, v73[0]);
  if ( v75[0] != &v76 )
    HeapFree(g_hWerheap, 0, v75[0]);
  if ( v85[0] != &v86 )
    HeapFree(g_hWerheap, 0, v85[0]);
  if ( v65 != &v67 )
    HeapFree(g_hWerheap, 0, v65);
  if ( v77[0] != &v78 )
    HeapFree(g_hWerheap, 0, v77[0]);
  if ( v71[0] != &v72 )
    HeapFree(g_hWerheap, 0, v71[0]);
  if ( v79[0] != &v80 )
    HeapFree(g_hWerheap, 0, v79[0]);
  if ( v68 != &v70 )
    HeapFree(g_hWerheap, 0, v68);
  if ( v81[0] != &v82 )
    HeapFree(g_hWerheap, 0, v81[0]);
  if ( v87 != (wchar_t *)&v88 )
    HeapFree(g_hWerheap, 0, v87);
  if ( v83[0] != &v84 )
    HeapFree(g_hWerheap, 0, v83[0]);
  return v11;
}

```

## disassembly

```asm
0x18002054c  mov     [rsp-8+arg_10], rbx
0x180020551  push    rbp
0x180020552  push    rsi
0x180020553  push    rdi
0x180020554  push    r12
0x180020556  push    r13
0x180020558  push    r14
0x18002055a  push    r15
0x18002055c  lea     rbp, [rsp-9F0h]
0x180020564  sub     rsp, 0AF0h
0x18002056b  mov     rax, cs:__security_cookie
0x180020572  xor     rax, rsp
0x180020575  mov     [rbp+0A20h+var_40], rax
0x18002057c  mov     r12, r9
0x18002057f  mov     dword ptr [rsp+0B20h+var_AB0], r8d
0x180020584  mov     r13, rdx
0x180020587  mov     r15, rcx
0x18002058a  mov     ebx, 2C0h
0x18002058f  mov     r8d, ebx; Size
0x180020592  xor     edx, edx; Val
0x180020594  lea     rcx, [rbp+0A20h+var_580]; void *
0x18002059b  call    memset_0
0x1800205a0  xor     edi, edi
0x1800205a2  mov     [rsp+0B20h+var_AA8], rdi
0x1800205a7  xorps   xmm0, xmm0
0x1800205aa  movups  [rbp+0A20h+ProcessInformation], xmm0
0x1800205ae  movups  [rbp+0A20h+var_A70], xmm0
0x1800205b2  movups  xmmword ptr [rbp+0A20h+dwProcessId], xmm0
0x1800205b6  mov     qword ptr [rsp+0B20h+CreationTime.dwLowDateTime], rdi
0x1800205bb  mov     qword ptr [rbp+0A20h+ExitTime.dwLowDateTime], rdi
0x1800205bf  mov     qword ptr [rbp+0A20h+KernelTime.dwLowDateTime], rdi
0x1800205c3  mov     qword ptr [rbp+0A20h+UserTime.dwLowDateTime], rdi
0x1800205c7  xor     edx, edx; Val
0x1800205c9  lea     r8d, [rdi+60h]; Size
0x1800205cd  lea     rcx, [rbp+0A20h+var_2C0]; void *
0x1800205d4  call    memset_0
0x1800205d9  lea     rcx, [rbp+0A20h+var_930]; void *
0x1800205e0  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800205e5  nop
0x1800205e6  lea     rcx, [rbp+0A20h+var_8F0]; void *
0x1800205ed  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800205f2  nop
0x1800205f3  lea     rcx, [rbp+0A20h+var_950]; void *
0x1800205fa  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800205ff  nop
0x180020600  lea     rcx, [rbp+0A20h+var_A10]; void *
0x180020604  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180020609  nop
0x18002060a  lea     rcx, [rbp+0A20h+var_970]; void *
0x180020611  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180020616  nop
0x180020617  lea     rcx, [rbp+0A20h+var_9F0]; void *
0x18002061b  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180020620  nop
0x180020621  lea     rcx, [rbp+0A20h+var_990]; void *
0x180020628  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18002062d  nop
0x18002062e  lea     rcx, [rbp+0A20h+var_A30]; void *
0x180020632  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180020637  nop
0x180020638  lea     rcx, [rbp+0A20h+var_910]; void *
0x18002063f  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180020644  nop
0x180020645  lea     rcx, [rbp+0A20h+var_9B0]; void *
0x180020649  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18002064e  nop
0x18002064f  lea     rcx, [rbp+0A20h+var_9D0]; void *
0x180020653  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180020658  nop
0x180020659  mov     [rbp+0A20h+var_A88], rdi
0x18002065d  xorps   xmm0, xmm0
0x180020660  movups  xmmword ptr [rbp+0A20h+var_260.Data1], xmm0
0x180020667  lea     rcx, [rbp+0A20h+lpMem]; void *
0x18002066b  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180020670  nop
0x180020671  mov     ecx, edi
0x180020673  test    r13, r13
0x180020676  setnz   cl
0x180020679  mov     eax, edi
0x18002067b  test    r15, r15
0x18002067e  setnz   al
0x180020681  cmp     ecx, eax
0x180020683  jnz     short loc_18002068A
0x180020685  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002068a  mov     r8, rbx; Size
0x18002068d  xor     edx, edx; Val
0x18002068f  lea     rcx, [rbp+0A20h+var_840]; void *
0x180020696  call    memset_0
0x18002069b  lea     rax, [rbp+0A20h+var_580]
0x1800206a2  lea     rcx, [rbp+0A20h+var_840]
0x1800206a9  mov     edx, 5
0x1800206ae  lea     r8d, [rdx+7Bh]
0x1800206b2  movups  xmm0, xmmword ptr [rcx]
0x1800206b5  movups  xmmword ptr [rax], xmm0
0x1800206b8  movups  xmm1, xmmword ptr [rcx+10h]
0x1800206bc  movups  xmmword ptr [rax+10h], xmm1
0x1800206c0  movups  xmm0, xmmword ptr [rcx+20h]
0x1800206c4  movups  xmmword ptr [rax+20h], xmm0
0x1800206c8  movups  xmm1, xmmword ptr [rcx+30h]
0x1800206cc  movups  xmmword ptr [rax+30h], xmm1
0x1800206d0  movups  xmm0, xmmword ptr [rcx+40h]
0x1800206d4  movups  xmmword ptr [rax+40h], xmm0
0x1800206d8  movups  xmm1, xmmword ptr [rcx+50h]
0x1800206dc  movups  xmmword ptr [rax+50h], xmm1
0x1800206e0  movups  xmm0, xmmword ptr [rcx+60h]
0x1800206e4  movups  xmmword ptr [rax+60h], xmm0
0x1800206e8  movups  xmm1, xmmword ptr [rcx+70h]
0x1800206ec  movups  xmmword ptr [rax+70h], xmm1
0x1800206f0  add     rax, r8
0x1800206f3  add     rcx, r8
0x1800206f6  sub     rdx, 1; ProcessInformationClass
0x1800206fa  jnz     short loc_1800206B2
0x1800206fc  movups  xmm0, xmmword ptr [rcx]
0x1800206ff  movups  xmmword ptr [rax], xmm0
0x180020702  movups  xmm1, xmmword ptr [rcx+10h]
0x180020706  movups  xmmword ptr [rax+10h], xmm1
0x18002070a  movups  xmm0, xmmword ptr [rcx+20h]
0x18002070e  movups  xmmword ptr [rax+20h], xmm0
0x180020712  movups  xmm1, xmmword ptr [rcx+30h]
0x180020716  movups  xmmword ptr [rax+30h], xmm1
0x18002071a  mov     qword ptr [rsp+0B20h+CreationTime.dwLowDateTime], rdi
0x18002071f  lea     esi, [rdx+1]
0x180020722  test    r15, r15
0x180020725  jz      short loc_18002078B
0x180020727  mov     [rsp+0B20h+ReturnLength], rdi; ReturnLength
0x18002072c  lea     r9d, [rdx+30h]; ProcessInformationLength
0x180020730  lea     r8, [rbp+0A20h+ProcessInformation]; ProcessInformation
0x180020734  mov     rcx, r15; ProcessHandle
0x180020737  call    cs:__imp_NtQueryInformationProcess
0x18002073d  mov     ebx, eax
0x18002073f  test    eax, eax
0x180020741  jns     short loc_180020783
0x180020743  bts     ebx, 1Ch
0x180020747  lea     rdi, WPP_GLOBAL_Control
0x18002074e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020755  cmp     rcx, rdi
0x180020758  jz      loc_18002147E
0x18002075e  test    [rcx+1Ch], sil
0x180020762  jz      loc_18002147E
0x180020768  lea     edx, [rsi+0Dh]
0x18002076b  mov     r9d, ebx
0x18002076e  lea     r8, WPP_683aa959ceed38e99a300365342989fb_Traceguids
0x180020775  mov     rcx, [rcx+10h]
0x180020779  call    WPP_SF_d
0x18002077e  jmp     loc_18002147E
0x180020783  mov     r14, r15
0x180020786  jmp     loc_180020883
0x18002078b  mov     r9d, ebx
0x18002078e  lea     r8, [rbp+0A20h+var_580]
0x180020795  mov     rcx, r13
0x180020798  call    cs:__imp_PssQuerySnapshot
0x18002079e  mov     ebx, eax
0x1800207a0  test    eax, eax
0x1800207a2  jz      short loc_1800207D7
0x1800207a4  jle     short loc_1800207AF
0x1800207a6  movzx   ebx, ax
0x1800207a9  or      ebx, 80070000h
0x1800207af  lea     rdi, WPP_GLOBAL_Control
0x1800207b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800207bd  cmp     rcx, rdi
0x1800207c0  jz      loc_18002147E
0x1800207c6  test    [rcx+1Ch], sil
0x1800207ca  jz      loc_18002147E
0x1800207d0  mov     edx, 0Fh
0x1800207d5  jmp     short loc_18002076B
0x1800207d7  mov     r9d, 8
0x1800207dd  lea     r8, [rsp+0B20h+var_AA8]
0x1800207e2  mov     edx, esi
0x1800207e4  mov     rcx, r13
0x1800207e7  call    cs:__imp_PssQuerySnapshot
0x1800207ed  mov     ebx, eax
0x1800207ef  test    eax, eax
0x1800207f1  jz      short loc_180020829
0x1800207f3  jle     short loc_1800207FE
0x1800207f5  movzx   ebx, ax
0x1800207f8  or      ebx, 80070000h
0x1800207fe  lea     rdi, WPP_GLOBAL_Control
0x180020805  mov     rcx, cs:WPP_GLOBAL_Control
0x18002080c  cmp     rcx, rdi
0x18002080f  jz      loc_18002147E
0x180020815  test    [rcx+1Ch], sil
0x180020819  jz      loc_18002147E
0x18002081f  mov     edx, 10h
0x180020824  jmp     loc_18002076B
0x180020829  xorps   xmm0, xmm0
0x18002082c  movups  [rbp+0A20h+ProcessInformation], xmm0
0x180020830  movups  [rbp+0A20h+var_A70], xmm0
0x180020834  movups  xmmword ptr [rbp+0A20h+dwProcessId], xmm0
0x180020838  mov     eax, [rbp+0A20h+var_580]
0x18002083e  mov     dword ptr [rbp+0A20h+ProcessInformation], eax
0x180020841  mov     rax, [rbp+0A20h+var_578]
0x180020848  mov     qword ptr [rbp+0A20h+ProcessInformation+8], rax
0x18002084c  mov     rax, [rbp+0A20h+var_570]
0x180020853  mov     qword ptr [rbp+0A20h+var_A70], rax
0x180020857  mov     eax, [rbp+0A20h+var_568]
0x18002085d  mov     dword ptr [rbp+0A20h+var_A70+8], eax
0x180020860  mov     eax, [rbp+0A20h+var_564]
0x180020866  mov     qword ptr [rbp+0A20h+dwProcessId], rax
0x18002086a  mov     eax, [rbp+0A20h+var_560]
0x180020870  mov     qword ptr [rbp+0A20h+dwProcessId+8], rax
0x180020874  mov     r14, [rsp+0B20h+var_AA8]
0x180020879  test    r14, r14
0x18002087c  jnz     short loc_180020883
0x18002087e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180020883  mov     r8d, [rbp+0A20h+dwProcessId]
0x180020887  lea     rdx, aD; "%d"
0x18002088e  lea     rcx, [rbp+0A20h+var_930]
0x180020895  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18002089a  lea     rsi, WPP_683aa959ceed38e99a300365342989fb_Traceguids
0x1800208a1  lea     rdi, WPP_GLOBAL_Control
0x1800208a8  test    eax, eax
0x1800208aa  jns     short loc_1800208D2
0x1800208ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800208b3  cmp     rcx, rdi
0x1800208b6  jz      short loc_1800208D2
0x1800208b8  test    byte ptr [rcx+1Ch], 2
0x1800208bc  jz      short loc_1800208D2
0x1800208be  mov     edx, 11h
0x1800208c3  mov     r9d, eax
0x1800208c6  mov     r8, rsi
0x1800208c9  mov     rcx, [rcx+10h]
0x1800208cd  call    WPP_SF_d
0x1800208d2  test    r13, r13
0x1800208d5  jz      short loc_1800208E0
0x1800208d7  lea     rcx, [rbp+0A20h+var_4CC]
0x1800208de  jmp     short loc_180020929
0x1800208e0  lea     rdx, [rbp+0A20h+var_8F0]
0x1800208e7  mov     rcx, r14; hProcess
0x1800208ea  call    ?UtilGetProcessPathFromHandle@@YAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetProcessPathFromHandle(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1800208ef  test    eax, eax
0x1800208f1  jns     short loc_180020922
0x1800208f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800208fa  cmp     rcx, rdi
0x1800208fd  jz      short loc_180020919
0x1800208ff  test    byte ptr [rcx+1Ch], 2
0x180020903  jz      short loc_180020919
0x180020905  mov     edx, 12h
0x18002090a  mov     r9d, eax
0x18002090d  mov     r8, rsi
0x180020910  mov     rcx, [rcx+10h]
0x180020914  call    WPP_SF_d
0x180020919  lea     rax, aUnableToRetrie; "(unable to retrieve)"
0x180020920  jmp     short loc_18002092E
0x180020922  mov     rcx, [rbp+0A20h+var_8F0]; wchar_t *
0x180020929  call    ?UtilPathTail@@YAPEB_WPEB_W@Z; UtilPathTail(wchar_t const *)
0x18002092e  mov     rdx, rax
0x180020931  lea     rcx, [rbp+0A20h+var_950]
0x180020938  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18002093d  lea     rdx, [rbp+0A20h+var_A10]
0x180020941  mov     rcx, r14; hProcess
0x180020944  call    ?UtilGetProcessCommandLine@@YAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetProcessCommandLine(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180020949  mov     ebx, eax
0x18002094b  xor     eax, eax
0x18002094d  test    ebx, ebx
0x18002094f  js      loc_180020A87
0x180020955  mov     ebx, eax
0x180020957  mov     [rsp+0B20h+pv], rax
0x18002095c  lea     rcx, [rsp+0B20h+pv]
0x180020961  call    ??$replace@$$BY0A@_WU?$generic_delete@$$BY0A@_WU?$generic_deallocate@$MP6AXPEAX@Z1?CoTaskMemFree@@YAX0@ZPEAX@tlx@@@tlx@@@utl@@YAPEAPEA_WAEAV?$unique_ptr@$$BY0A@_WU?$generic_delete@$$BY0A@_WU?$generic_deallocate@$MP6AXPEAX@Z1?CoTaskMemFree@@YAX0@ZPEAX@tlx@@@tlx@@@0@@Z
0x180020966  mov     r9, rax; ppszPath
0x180020969  xor     r8d, r8d; hToken
0x18002096c  mov     edx, 4000h; dwFlags
0x180020971  lea     rcx, FOLDERID_InternetCache; rfid
0x180020978  call    cs:__imp_SHGetKnownFolderPath
0x18002097e  xor     edx, edx
0x180020980  test    eax, eax
0x180020982  js      short loc_1800209F4
0x180020984  mov     rax, [rsp+0B20h+pv]
0x180020989  test    rax, rax
0x18002098c  jnz     short loc_18002099A
0x18002098e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180020993  mov     rax, [rsp+0B20h+pv]
0x180020998  xor     edx, edx
0x18002099a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002099e  inc     rcx
0x1800209a1  cmp     [rax+rcx*2], dx
0x1800209a5  jnz     short loc_18002099E
0x1800209a7  mov     qword ptr [rsp+0B20h+var_AE0], rax
0x1800209ac  mov     qword ptr [rsp+0B20h+var_AE0+8], rcx
0x1800209b1  mov     rax, [rbp+0A20h+var_A10]
0x1800209b5  mov     qword ptr [rsp+0B20h+var_AF0], rax
0x1800209ba  mov     rcx, [rbp+0A20h+var_A08]
0x1800209be  sub     rcx, rax
0x1800209c1  sar     rcx, 1
0x1800209c4  mov     qword ptr [rsp+0B20h+var_AF0+8], rcx
0x1800209c9  lea     rdx, [rsp+0B20h+var_AE0]
0x1800209ce  lea     rcx, [rsp+0B20h+var_AF0]
0x1800209d3  call    ?StringContainsOrdinalIgnoreCase@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0@Z; StringContainsOrdinalIgnoreCase(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x1800209d8  movzx   ebx, al
0x1800209db  mov     rcx, [rsp+0B20h+pv]; pv
0x1800209e0  xor     edx, edx
0x1800209e2  mov     [rsp+0B20h+pv], rdx
0x1800209e7  test    rcx, rcx
0x1800209ea  jz      short loc_1800209F4
0x1800209ec  call    cs:__imp_CoTaskMemFree
0x1800209f2  xor     edx, edx
0x1800209f4  mov     [rbp+0A20h+var_250], dx
0x1800209fb  lea     rdx, [rbp+0A20h+var_250]
0x180020a02  mov     ecx, 104h
0x180020a07  call    cs:__imp_GetTempPath2W
  ... truncated ...
```
