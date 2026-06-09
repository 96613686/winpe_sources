# Microsoft::Diagnostics::Utils::Os::GetServiceProcessIdsRegex(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,int,std::unordered_multimap<ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::hash<ulong>,std::equal_to<ulong>,std::allocator<std::pair<ulong const,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>>> &,Microsoft::Diagnostics::EscalationWorkItemState *)

- ea: `0x1802f7a24`
- end: `0x1802f83bd`
- name: `?GetServiceProcessIdsRegex@Os@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@HAEAV?$unordered_multimap@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@6@PEAVEscalationWorkItemState@34@@Z`
- size: `2457`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800e4430`
- `0x180303120`

## callees

- `0x18001d5ac`
- `0x18001e638`
- `0x1800566b0`
- `0x18007fae8`
- `0x1800d0d7c`
- `0x180170014`
- `0x1801a1c9c`
- `0x1801b27a8`
- `0x1802f53e4`
- `0x1802f553c`
- `0x1802f55f0`
- `0x1802f7a24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802f7ad9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802f7b5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802f7d4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802f7dac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802f7f39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802f804a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802f8187`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802f8294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802f7ad9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802f7b5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802f7d4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802f7dac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802f7f39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802f804a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802f8187`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802f8294`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1802f7d38`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1802f7d8f`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1802f7d38`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1802f7d8f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1802f7cfb`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1802f7cfb`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1802f7a54`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1802f7a54`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x1802f7ac5`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x1802f7b48`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x1802f7ac5`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x1802f7b48`

## string_xrefs

- `0x1802f81a5`: `Failed to query services (1): 0x`
- `0x1802f82b2`: `Failed to open SC Manager: 0x`
- `0x1802f7b7a`: `Failed to query services (2): 0x`
- `0x1802f7f4e`: `Failed to query PID for service (1), `
- `0x1802f805f`: `Failed to open service, `
- `0x1802f7dc1`: `Failed to query PID for service (2), `
- `0x1802f7efa`: `Found PID matching regex, service '`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::Diagnostics::Utils::Os::GetServiceProcessIdsRegex(
        _QWORD *a1,
        DWORD a2,
        __int64 a3,
        __int64 a4)
{
  SC_HANDLE v7; // rax
  SC_HANDLE v8; // rdi
  DWORD v9; // r13d
  DWORD LastError; // ebx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  void *v14; // rax
  unsigned int v15; // ebx
  const char *v16; // r9
  __int64 result; // rax
  LPBYTE v18; // r12
  LPCWSTR *v19; // r12
  SC_HANDLE v20; // rbx
  DWORD v21; // ebx
  void *v22; // rax
  void *v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  void *v27; // rax
  unsigned int v28; // ebx
  void *v29; // rax
  void *v30; // rax
  __int64 v31; // rax
  DWORD v32; // ebx
  void *v33; // rax
  void *v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  void *v38; // rax
  DWORD v39; // ebx
  void *v40; // rax
  void *v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  void *v45; // rax
  DWORD v46; // ebx
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  void *v50; // rax
  unsigned int v51; // ebx
  DWORD v52; // ebx
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rax
  void *v56; // rax
  unsigned int v57; // ebx
  unsigned int lpServices; // [rsp+20h] [rbp-198h]
  unsigned int lpServicesa; // [rsp+20h] [rbp-198h]
  unsigned int lpServicesb; // [rsp+20h] [rbp-198h]
  char v61; // [rsp+50h] [rbp-168h] BYREF
  _BYTE v62[3]; // [rsp+51h] [rbp-167h]
  int v63; // [rsp+54h] [rbp-164h]
  __int64 v64; // [rsp+58h] [rbp-160h]
  DWORD pcbBytesNeeded; // [rsp+60h] [rbp-158h] BYREF
  DWORD ServicesReturned; // [rsp+64h] [rbp-154h] BYREF
  unsigned int v67; // [rsp+68h] [rbp-150h] BYREF
  _QWORD v68[2]; // [rsp+70h] [rbp-148h] BYREF
  char v69; // [rsp+80h] [rbp-138h] BYREF
  __int16 v70; // [rsp+81h] [rbp-137h]
  char v71; // [rsp+83h] [rbp-135h]
  int v72; // [rsp+84h] [rbp-134h]
  __int64 v73; // [rsp+88h] [rbp-130h]
  unsigned __int8 v74; // [rsp+91h] [rbp-127h]
  __int16 v75; // [rsp+92h] [rbp-126h]
  DWORD ResumeHandle; // [rsp+A0h] [rbp-118h] BYREF
  LPBYTE v77; // [rsp+A8h] [rbp-110h] BYREF
  LPBYTE lpBuffer; // [rsp+B0h] [rbp-108h] BYREF
  SC_HANDLE v79; // [rsp+B8h] [rbp-100h] BYREF
  char v80; // [rsp+C0h] [rbp-F8h] BYREF
  __int16 v81; // [rsp+C1h] [rbp-F7h]
  char v82; // [rsp+C3h] [rbp-F5h]
  int v83; // [rsp+C4h] [rbp-F4h]
  __int64 v84; // [rsp+C8h] [rbp-F0h]
  char v85; // [rsp+D0h] [rbp-E8h] BYREF
  __int16 v86; // [rsp+D1h] [rbp-E7h]
  char v87; // [rsp+D3h] [rbp-E5h]
  int v88; // [rsp+D4h] [rbp-E4h]
  __int64 v89; // [rsp+D8h] [rbp-E0h]
  char v90; // [rsp+E0h] [rbp-D8h] BYREF
  __int16 v91; // [rsp+E1h] [rbp-D7h]
  char v92; // [rsp+E3h] [rbp-D5h]
  int v93; // [rsp+E4h] [rbp-D4h]
  __int64 v94; // [rsp+E8h] [rbp-D0h]
  char v95; // [rsp+F0h] [rbp-C8h] BYREF
  __int16 v96; // [rsp+F1h] [rbp-C7h]
  char v97; // [rsp+F3h] [rbp-C5h]
  int v98; // [rsp+F4h] [rbp-C4h]
  __int64 v99; // [rsp+F8h] [rbp-C0h]
  char v100; // [rsp+100h] [rbp-B8h] BYREF
  __int16 v101; // [rsp+101h] [rbp-B7h]
  char v102; // [rsp+103h] [rbp-B5h]
  int v103; // [rsp+104h] [rbp-B4h]
  __int64 v104; // [rsp+108h] [rbp-B0h]
  LPBYTE v105; // [rsp+110h] [rbp-A8h]
  unsigned __int8 v106; // [rsp+119h] [rbp-9Fh]
  __int16 v107; // [rsp+11Ah] [rbp-9Eh]
  unsigned __int8 v108; // [rsp+129h] [rbp-8Fh]
  __int16 v109; // [rsp+12Ah] [rbp-8Eh]
  unsigned __int8 v110; // [rsp+139h] [rbp-7Fh]
  __int16 v111; // [rsp+13Ah] [rbp-7Eh]
  unsigned __int8 v112; // [rsp+149h] [rbp-6Fh]
  __int16 v113; // [rsp+14Ah] [rbp-6Eh]
  unsigned __int8 v114; // [rsp+159h] [rbp-5Fh]
  __int16 v115; // [rsp+15Ah] [rbp-5Eh]
  _BYTE v116[40]; // [rsp+168h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  v7 = OpenSCManagerW(0, 0, 4u);
  try
  {
    v8 = v7;
    v68[0] = v7;
    v9 = 0;
    if ( v7 )
    {
      pcbBytesNeeded = 0;
      ServicesReturned = 0;
      ResumeHandle = 0;
      if ( !EnumServicesStatusExW(
              v7,
              SC_ENUM_PROCESS_INFO,
              0x30u,
              a2,
              0,
              0,
              &pcbBytesNeeded,
              &ServicesReturned,
              &ResumeHandle,
              0)
        && GetLastError() == 234 )
      {
        std::make_unique<unsigned char [0],0>(&v77, pcbBytesNeeded);
        if ( !EnumServicesStatusExW(
                v8,
                SC_ENUM_PROCESS_INFO,
                0x30u,
                a2,
                v77,
                pcbBytesNeeded,
                &pcbBytesNeeded,
                &ServicesReturned,
                &ResumeHandle,
                0) )
        {
          LastError = GetLastError();
          if ( a4 )
          {
            v11 = Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a4 + 168));
            v69 = 1;
            v70 = v62[0];
            v71 = 0;
            v72 = 2097153;
            v73 = 0;
            v12 = Microsoft::Diagnostics::WideStringStream::operator<<(v11, &v69);
            v13 = Microsoft::Diagnostics::WideStringStream::operator<<(v12, LastError);
            *(_WORD *)&v62[1] = 0;
            v69 = 1;
            v70 = v62[0];
            v71 = 0;
            v72 = 0x200000;
            v73 = 0;
            v14 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v13, &v69);
            Microsoft::Diagnostics::WideStringStream::operator<<(v14);
          }
          if ( LastError )
          {
            v15 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x5A4,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
                    (const char *)LastError,
                    lpServicesb);
            std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&v77);
            wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v68);
            return v15;
          }
          else
          {
            std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&v77);
            wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v68);
            return 0;
          }
        }
        v18 = v77;
        v105 = v77;
        std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::basic_regex<wchar_t,std::regex_traits<wchar_t>>(
          v116,
          *a1,
          a1[1]);
        while ( 1 )
        {
          if ( v9 >= ServicesReturned )
          {
            std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::~basic_regex<wchar_t,std::regex_traits<wchar_t>>(v116);
            std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&v77);
            wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v68);
            return 0;
          }
          v19 = (LPCWSTR *)&v18[56 * v9];
          if ( (unsigned __int8)std::regex_search<wchar_t,std::regex_traits<wchar_t>>(*v19, v116) )
            break;
LABEL_29:
          ++v9;
          v18 = v105;
        }
        v20 = OpenServiceW(v8, *v19, 4u);
        v79 = v20;
        if ( !v20 )
        {
          if ( a4 )
          {
            v39 = GetLastError();
            v40 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a4 + 168));
            v41 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v40);
            v42 = Microsoft::Diagnostics::WideStringStream::operator<<(v41);
            v115 = 0;
            v100 = 1;
            v101 = v114;
            v102 = 0;
            v103 = 2097153;
            v104 = 0;
            v43 = Microsoft::Diagnostics::WideStringStream::operator<<(v42, &v100);
            v44 = Microsoft::Diagnostics::WideStringStream::operator<<(v43, v39);
            v75 = 0;
            v61 = 1;
            *(_WORD *)v62 = v74;
            v62[2] = 0;
            v63 = 0x200000;
            v64 = 0;
            v45 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v44, &v61);
            Microsoft::Diagnostics::WideStringStream::operator<<(v45);
          }
          goto LABEL_28;
        }
        pcbBytesNeeded = 0;
        if ( QueryServiceStatusEx(v20, SC_STATUS_PROCESS_INFO, 0, 0, &pcbBytesNeeded) || GetLastError() != 122 )
        {
          if ( a4 )
          {
            v32 = GetLastError();
            v33 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a4 + 168));
            v34 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v33);
            v35 = Microsoft::Diagnostics::WideStringStream::operator<<(v34);
            v111 = 0;
            v90 = 1;
            v91 = v110;
            v92 = 0;
            v93 = 2097153;
            v94 = 0;
            v36 = Microsoft::Diagnostics::WideStringStream::operator<<(v35, &v90);
            v37 = Microsoft::Diagnostics::WideStringStream::operator<<(v36, v32);
            v113 = 0;
            v95 = 1;
            v96 = v112;
            v97 = 0;
            v98 = 0x200000;
            v99 = 0;
            v38 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v37, &v95);
            Microsoft::Diagnostics::WideStringStream::operator<<(v38);
          }
          goto LABEL_28;
        }
        std::make_unique<unsigned char [0],0>(&lpBuffer, pcbBytesNeeded);
        if ( QueryServiceStatusEx(v20, SC_STATUS_PROCESS_INFO, lpBuffer, pcbBytesNeeded, &pcbBytesNeeded) )
        {
          v28 = *((_DWORD *)lpBuffer + 7);
          v67 = v28;
          std::_Hash<std::_Umap_traits<unsigned long,std::wstring,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::wstring>>,1>>::emplace<unsigned long &,wchar_t * &>(
            a3,
            &v69,
            &v67,
            v19);
          if ( !a4 )
            goto LABEL_21;
          v29 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a4 + 168));
          v30 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v29);
          v31 = Microsoft::Diagnostics::WideStringStream::operator<<(v30);
          v27 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v31, v28);
        }
        else
        {
          if ( !a4 )
          {
LABEL_21:
            std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpBuffer);
LABEL_28:
            wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v79);
            goto LABEL_29;
          }
          v21 = GetLastError();
          v22 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a4 + 168));
          v23 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v22);
          v24 = Microsoft::Diagnostics::WideStringStream::operator<<(v23);
          v107 = 0;
          v80 = 1;
          v81 = v106;
          v82 = 0;
          v83 = 2097153;
          v84 = 0;
          v25 = Microsoft::Diagnostics::WideStringStream::operator<<(v24, &v80);
          v26 = Microsoft::Diagnostics::WideStringStream::operator<<(v25, v21);
          v109 = 0;
          v85 = 1;
          v86 = v108;
          v87 = 0;
          v88 = 0x200000;
          v89 = 0;
          v27 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v26, &v85);
        }
        Microsoft::Diagnostics::WideStringStream::operator<<(v27);
        goto LABEL_21;
      }
      v46 = GetLastError();
      if ( a4 )
      {
        v47 = Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a4 + 168));
        v75 = 0;
        v61 = 1;
        *(_WORD *)v62 = v74;
        v62[2] = 0;
        v63 = 2097153;
        v64 = 0;
        v48 = Microsoft::Diagnostics::WideStringStream::operator<<(v47, &v61);
        v49 = Microsoft::Diagnostics::WideStringStream::operator<<(v48, v46);
        v75 = 0;
        v61 = 1;
        *(_WORD *)v62 = v74;
        v62[2] = 0;
        v63 = 0x200000;
        v64 = 0;
        v50 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v49, &v61);
        Microsoft::Diagnostics::WideStringStream::operator<<(v50);
      }
      if ( v46 )
      {
        v51 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x590,
                (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
                (const char *)v46,
                lpServicesa);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v68);
        return v51;
      }
    }
    else
    {
      v52 = GetLastError();
      if ( a4 )
      {
        v53 = Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a4 + 168));
        v75 = 0;
        v61 = 1;
        *(_WORD *)v62 = v74;
        v62[2] = 0;
        v63 = 2097153;
        v64 = 0;
        v54 = Microsoft::Diagnostics::WideStringStream::operator<<(v53, &v61);
        v55 = Microsoft::Diagnostics::WideStringStream::operator<<(v54, v52);
        v75 = 0;
        v61 = 1;
        *(_WORD *)v62 = v74;
        v62[2] = 0;
        v63 = 0x200000;
        v64 = 0;
        v56 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v55, &v61);
        Microsoft::Diagnostics::WideStringStream::operator<<(v56);
      }
      if ( v52 )
      {
        v57 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x579,
                (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
                (const char *)v52,
                lpServices);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v68);
        return v57;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v68);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x5DF,
                           (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
                           v16);
  }
  return result;
}

```

## disassembly

```asm
0x1802f7a24  mov     [rsp+arg_0], rbx
0x1802f7a29  mov     [rsp+arg_8], rsi
0x1802f7a2e  mov     [rsp+arg_10], r8
0x1802f7a33  push    rdi
0x1802f7a34  push    r12
0x1802f7a36  push    r13
0x1802f7a38  push    r14
0x1802f7a3a  push    r15
0x1802f7a3c  sub     rsp, 190h
0x1802f7a43  mov     rsi, r9
0x1802f7a46  mov     r14d, edx
0x1802f7a49  mov     rbx, rcx
0x1802f7a4c  xor     edx, edx; lpDatabaseName
0x1802f7a4e  xor     ecx, ecx; lpMachineName
0x1802f7a50  lea     r8d, [rdx+4]; dwDesiredAccess
0x1802f7a54  call    cs:__imp_OpenSCManagerW
0x1802f7a5b  nop     dword ptr [rax+rax+00h]
0x1802f7a60  mov     rdi, rax
0x1802f7a63  mov     [rsp+1B8h+var_148], rax
0x1802f7a68  xor     r13d, r13d
0x1802f7a6b  test    rax, rax
0x1802f7a6e  jz      loc_1802F8294
0x1802f7a74  mov     [rsp+1B8h+var_158], r13d
0x1802f7a79  mov     [rsp+1B8h+ServicesReturned], r13d
0x1802f7a7e  mov     [rsp+1B8h+ResumeHandle], r13d
0x1802f7a86  mov     [rsp+1B8h+pszGroupName], r13; pszGroupName
0x1802f7a8b  lea     rax, [rsp+1B8h+ResumeHandle]
0x1802f7a93  mov     [rsp+1B8h+lpResumeHandle], rax; lpResumeHandle
0x1802f7a98  lea     rax, [rsp+1B8h+ServicesReturned]
0x1802f7a9d  mov     [rsp+1B8h+lpServicesReturned], rax; lpServicesReturned
0x1802f7aa2  lea     rax, [rsp+1B8h+var_158]
0x1802f7aa7  mov     [rsp+1B8h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1802f7aac  mov     [rsp+1B8h+cbBufSize], r13d; cbBufSize
0x1802f7ab1  mov     [rsp+1B8h+lpServices], r13; unsigned int
0x1802f7ab6  mov     r9d, r14d; dwServiceState
0x1802f7ab9  lea     r15d, [r13+30h]
0x1802f7abd  mov     r8d, r15d; dwServiceType
0x1802f7ac0  xor     edx, edx; InfoLevel
0x1802f7ac2  mov     rcx, rdi; hSCManager
0x1802f7ac5  call    cs:__imp_EnumServicesStatusExW
0x1802f7acc  nop     dword ptr [rax+rax+00h]
0x1802f7ad1  test    eax, eax
0x1802f7ad3  jnz     loc_1802F8187
0x1802f7ad9  call    cs:__imp_GetLastError
0x1802f7ae0  nop     dword ptr [rax+rax+00h]
0x1802f7ae5  cmp     eax, 0EAh
0x1802f7aea  jnz     loc_1802F8187
0x1802f7af0  mov     edx, [rsp+1B8h+var_158]
0x1802f7af4  lea     rcx, [rsp+1B8h+var_110]
0x1802f7afc  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x1802f7b01  nop
0x1802f7b02  mov     eax, [rsp+1B8h+var_158]
0x1802f7b06  mov     rcx, [rsp+1B8h+var_110]
0x1802f7b0e  mov     [rsp+1B8h+pszGroupName], r13; pszGroupName
0x1802f7b13  lea     rdx, [rsp+1B8h+ResumeHandle]
0x1802f7b1b  mov     [rsp+1B8h+lpResumeHandle], rdx; lpResumeHandle
0x1802f7b20  lea     rdx, [rsp+1B8h+ServicesReturned]
0x1802f7b25  mov     [rsp+1B8h+lpServicesReturned], rdx; lpServicesReturned
0x1802f7b2a  lea     rdx, [rsp+1B8h+var_158]
0x1802f7b2f  mov     [rsp+1B8h+pcbBytesNeeded], rdx; pcbBytesNeeded
0x1802f7b34  mov     [rsp+1B8h+cbBufSize], eax; cbBufSize
0x1802f7b38  mov     [rsp+1B8h+lpServices], rcx; unsigned int
0x1802f7b3d  mov     r9d, r14d; dwServiceState
0x1802f7b40  mov     r8d, r15d; dwServiceType
0x1802f7b43  xor     edx, edx; InfoLevel
0x1802f7b45  mov     rcx, rdi; hSCManager
0x1802f7b48  call    cs:__imp_EnumServicesStatusExW
0x1802f7b4f  nop     dword ptr [rax+rax+00h]
0x1802f7b54  test    eax, eax
0x1802f7b56  jnz     loc_1802F7C95
0x1802f7b5c  call    cs:__imp_GetLastError
0x1802f7b63  nop     dword ptr [rax+rax+00h]
0x1802f7b68  mov     ebx, eax
0x1802f7b6a  test    rsi, rsi
0x1802f7b6d  jz      loc_1802F7C35
0x1802f7b73  lea     rcx, [rsi+0A8h]; Src
0x1802f7b7a  lea     rdx, aFailedToQueryS_0; "Failed to query services (2): 0x"
0x1802f7b81  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1802f7b86  mov     [rsp+1B8h+var_166], r13w
0x1802f7b8c  lea     r14d, [r13+1]
0x1802f7b90  mov     [rsp+1B8h+var_138], r14b
0x1802f7b98  movzx   ecx, word ptr [rsp+51h]
0x1802f7b9d  mov     [rsp+1B8h+var_137], cx
0x1802f7ba5  mov     cl, byte ptr [rsp+1B8h+var_166+1]
0x1802f7ba9  mov     [rsp+1B8h+var_135], cl
0x1802f7bb0  mov     [rsp+1B8h+var_134], 200001h
0x1802f7bbb  mov     [rsp+1B8h+var_130], r13
0x1802f7bc3  lea     rdx, [rsp+1B8h+var_138]
0x1802f7bcb  mov     rcx, rax
0x1802f7bce  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x1802f7bd3  mov     edx, ebx
0x1802f7bd5  mov     rcx, rax
0x1802f7bd8  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x1802f7bdd  mov     [rsp+1B8h+var_166], r13w
0x1802f7be3  mov     [rsp+1B8h+var_138], r14b
0x1802f7beb  movzx   ecx, word ptr [rsp+51h]
0x1802f7bf0  mov     [rsp+1B8h+var_137], cx
0x1802f7bf8  mov     cl, byte ptr [rsp+1B8h+var_166+1]
0x1802f7bfc  mov     [rsp+1B8h+var_135], cl
0x1802f7c03  mov     [rsp+1B8h+var_134], 200000h
0x1802f7c0e  mov     [rsp+1B8h+var_130], r13
0x1802f7c16  lea     rdx, [rsp+1B8h+var_138]
0x1802f7c1e  mov     rcx, rax
0x1802f7c21  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x1802f7c26  lea     rdx, asc_1803721B4; "\r\n"
0x1802f7c2d  mov     rcx, rax; Src
0x1802f7c30  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1802f7c35  test    ebx, ebx
0x1802f7c37  jz      short loc_1802F7C76
0x1802f7c39  mov     rcx, [rsp+1B8h]; this
0x1802f7c41  mov     r9d, ebx; char *
0x1802f7c44  lea     r8, aOnecoreBaseTel_242; "onecore\\base\\telemetry\\utc\\include"...
0x1802f7c4b  mov     edx, 5A4h; void *
0x1802f7c50  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1802f7c55  mov     ebx, eax
0x1802f7c57  lea     rcx, [rsp+1B8h+var_110]
0x1802f7c5f  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x1802f7c64  nop
0x1802f7c65  lea     rcx, [rsp+1B8h+var_148]
0x1802f7c6a  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1802f7c6f  mov     eax, ebx
0x1802f7c71  jmp     loc_1802F839F
0x1802f7c76  lea     rcx, [rsp+1B8h+var_110]
0x1802f7c7e  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x1802f7c83  nop
0x1802f7c84  lea     rcx, [rsp+1B8h+var_148]
0x1802f7c89  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1802f7c8e  xor     eax, eax
0x1802f7c90  jmp     loc_1802F839F
0x1802f7c95  mov     r12, [rsp+1B8h+var_110]
0x1802f7c9d  mov     [rsp+1B8h+var_A8], r12
0x1802f7ca5  mov     r8, [rbx+8]
0x1802f7ca9  mov     rdx, [rbx]
0x1802f7cac  lea     rcx, [rsp+1B8h+var_50]
0x1802f7cb4  call    ??0?$basic_regex@_WV?$regex_traits@_W@std@@@std@@QEAA@PEB_W_KW4syntax_option_type@regex_constants@1@@Z; std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::basic_regex<wchar_t,std::regex_traits<wchar_t>>(wchar_t const *,unsigned __int64,std::regex_constants::syntax_option_type)
0x1802f7cb9  nop
0x1802f7cba  mov     r14d, 1
0x1802f7cc0  cmp     r13d, [rsp+1B8h+ServicesReturned]
0x1802f7cc5  jnb     loc_1802F8159
0x1802f7ccb  mov     eax, r13d
0x1802f7cce  imul    rcx, rax, 38h ; '8'
0x1802f7cd2  add     r12, rcx
0x1802f7cd5  lea     rdx, [rsp+1B8h+var_50]
0x1802f7cdd  mov     rcx, [r12]
0x1802f7ce1  call    ??$regex_search@_WV?$regex_traits@_W@std@@@std@@YA_NPEB_WAEBV?$basic_regex@_WV?$regex_traits@_W@std@@@0@W4match_flag_type@regex_constants@0@@Z; std::regex_search<wchar_t,std::regex_traits<wchar_t>>(wchar_t const *,std::basic_regex<wchar_t,std::regex_traits<wchar_t>> const &,std::regex_constants::match_flag_type)
0x1802f7ce6  test    al, al
0x1802f7ce8  jz      loc_1802F8149
0x1802f7cee  mov     r8d, 4; dwDesiredAccess
0x1802f7cf4  mov     rdx, [r12]; lpServiceName
0x1802f7cf8  mov     rcx, rdi; hSCManager
0x1802f7cfb  call    cs:__imp_OpenServiceW
0x1802f7d02  nop     dword ptr [rax+rax+00h]
0x1802f7d07  mov     rbx, rax
0x1802f7d0a  mov     [rsp+1B8h+var_100], rax
0x1802f7d12  test    rax, rax
0x1802f7d15  jz      loc_1802F8041
0x1802f7d1b  mov     [rsp+1B8h+var_158], 0
0x1802f7d23  lea     rax, [rsp+1B8h+var_158]
0x1802f7d28  mov     [rsp+1B8h+lpServices], rax; pcbBytesNeeded
0x1802f7d2d  xor     r9d, r9d; cbBufSize
0x1802f7d30  xor     r8d, r8d; lpBuffer
0x1802f7d33  xor     edx, edx; InfoLevel
0x1802f7d35  mov     rcx, rbx; hService
0x1802f7d38  call    cs:__imp_QueryServiceStatusEx
0x1802f7d3f  nop     dword ptr [rax+rax+00h]
0x1802f7d44  test    eax, eax
0x1802f7d46  jnz     loc_1802F7F30
0x1802f7d4c  call    cs:__imp_GetLastError
0x1802f7d53  nop     dword ptr [rax+rax+00h]
0x1802f7d58  cmp     eax, 7Ah ; 'z'
0x1802f7d5b  jnz     loc_1802F7F30
0x1802f7d61  mov     edx, [rsp+1B8h+var_158]
0x1802f7d65  lea     rcx, [rsp+1B8h+lpBuffer]
0x1802f7d6d  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x1802f7d72  nop
0x1802f7d73  lea     rax, [rsp+1B8h+var_158]
0x1802f7d78  mov     [rsp+1B8h+lpServices], rax; pcbBytesNeeded
0x1802f7d7d  mov     r9d, [rsp+1B8h+var_158]; cbBufSize
0x1802f7d82  mov     r8, [rsp+1B8h+lpBuffer]; lpBuffer
0x1802f7d8a  xor     edx, edx; InfoLevel
0x1802f7d8c  mov     rcx, rbx; hService
0x1802f7d8f  call    cs:__imp_QueryServiceStatusEx
0x1802f7d96  nop     dword ptr [rax+rax+00h]
0x1802f7d9b  test    eax, eax
0x1802f7d9d  jnz     loc_1802F7EC2
0x1802f7da3  test    rsi, rsi
0x1802f7da6  jz      loc_1802F7EB0
0x1802f7dac  call    cs:__imp_GetLastError
0x1802f7db3  nop     dword ptr [rax+rax+00h]
0x1802f7db8  mov     ebx, eax
0x1802f7dba  lea     rcx, [rsi+0A8h]; Src
0x1802f7dc1  lea     rdx, aFailedToQueryP_0; "Failed to query PID for service (2), "
0x1802f7dc8  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1802f7dcd  mov     rdx, [r12]
0x1802f7dd1  mov     rcx, rax; Src
0x1802f7dd4  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1802f7dd9  lea     rdx, a0x; ": 0x"
0x1802f7de0  mov     rcx, rax; Src
0x1802f7de3  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1802f7de8  xor     ecx, ecx
0x1802f7dea  mov     [rsp+1B8h+var_9E], cx
0x1802f7df2  mov     [rsp+1B8h+var_F8], r14b
0x1802f7dfa  movzx   ecx, word ptr [rsp+119h]
0x1802f7e02  mov     [rsp+1B8h+var_F7], cx
0x1802f7e0a  mov     cl, byte ptr [rsp+1B8h+var_9E+1]
0x1802f7e11  mov     [rsp+1B8h+var_F5], cl
0x1802f7e18  mov     [rsp+1B8h+var_F4], 200001h
0x1802f7e23  mov     [rsp+1B8h+var_F0], 0
0x1802f7e2f  lea     rdx, [rsp+1B8h+var_F8]
0x1802f7e37  mov     rcx, rax
0x1802f7e3a  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x1802f7e3f  mov     edx, ebx
0x1802f7e41  mov     rcx, rax
0x1802f7e44  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x1802f7e49  xor     ecx, ecx
0x1802f7e4b  mov     [rsp+1B8h+var_8E], cx
0x1802f7e53  mov     [rsp+1B8h+var_E8], r14b
0x1802f7e5b  movzx   ecx, word ptr [rsp+129h]
0x1802f7e63  mov     [rsp+1B8h+var_E7], cx
0x1802f7e6b  mov     cl, byte ptr [rsp+1B8h+var_8E+1]
0x1802f7e72  mov     [rsp+1B8h+var_E5], cl
0x1802f7e79  mov     [rsp+1B8h+var_E4], 200000h
0x1802f7e84  mov     [rsp+1B8h+var_E0], 0
0x1802f7e90  lea     rdx, [rsp+1B8h+var_E8]
0x1802f7e98  mov     rcx, rax
0x1802f7e9b  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x1802f7ea0  lea     rdx, asc_1803721B4; "\r\n"
0x1802f7ea7  mov     rcx, rax; Src
0x1802f7eaa  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1802f7eaf  nop
0x1802f7eb0  lea     rcx, [rsp+1B8h+lpBuffer]
0x1802f7eb8  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x1802f7ebd  jmp     loc_1802F813C
0x1802f7ec2  mov     rax, [rsp+1B8h+lpBuffer]
0x1802f7eca  mov     ebx, [rax+1Ch]
0x1802f7ecd  mov     [rsp+1B8h+var_150], ebx
0x1802f7ed1  mov     r9, r12
0x1802f7ed4  lea     r8, [rsp+1B8h+var_150]
0x1802f7ed9  lea     rdx, [rsp+1B8h+var_138]
0x1802f7ee1  mov     rcx, [rsp+1B8h+arg_10]
0x1802f7ee9  call    ??$emplace@AEAKAEAPEA_W@?$_Hash@V?$_Umap_traits@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@2@V?$allocator@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@$00@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@@1@AEAKAEAPEA_W@Z; std::_Hash<std::_Umap_traits<ulong,std::wstring,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::wstring>>,1>>::emplace<ulong &,wchar_t * &>(ulong &,wchar_t * &)
0x1802f7eee  test    rsi, rsi
0x1802f7ef1  jz      short loc_1802F7EB0
0x1802f7ef3  lea     rcx, [rsi+0A8h]; Src
0x1802f7efa  lea     rdx, aFoundPidMatchi; "Found PID matching regex, service '"
0x1802f7f01  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1802f7f06  mov     rdx, [r12]
0x1802f7f0a  mov     rcx, rax; Src
0x1802f7f0d  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1802f7f12  lea     rdx, asc_1803B4C70; "': "
0x1802f7f19  mov     rcx, rax; Src
0x1802f7f1c  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1802f7f21  mov     edx, ebx
0x1802f7f23  mov     rcx, rax
0x1802f7f26  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x1802f7f2b  jmp     loc_1802F7EA0
0x1802f7f30  test    rsi, rsi
0x1802f7f33  jz      loc_1802F813C
0x1802f7f39  call    cs:__imp_GetLastError
0x1802f7f40  nop     dword ptr [rax+rax+00h]
0x1802f7f45  mov     ebx, eax
0x1802f7f47  lea     rcx, [rsi+0A8h]; Src
0x1802f7f4e  lea     rdx, aFailedToQueryP; "Failed to query PID for service (1), "
0x1802f7f55  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1802f7f5a  mov     rdx, [r12]
0x1802f7f5e  mov     rcx, rax; Src
0x1802f7f61  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1802f7f66  lea     rdx, a0x; ": 0x"
0x1802f7f6d  mov     rcx, rax; Src
0x1802f7f70  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1802f7f75  xor     ecx, ecx
0x1802f7f77  mov     [rsp+1B8h+var_7E], cx
0x1802f7f7f  mov     [rsp+1B8h+var_D8], r14b
0x1802f7f87  movzx   ecx, word ptr [rsp+139h]
0x1802f7f8f  mov     [rsp+1B8h+var_D7], cx
0x1802f7f97  mov     cl, byte ptr [rsp+1B8h+var_7E+1]
0x1802f7f9e  mov     [rsp+1B8h+var_D5], cl
0x1802f7fa5  mov     [rsp+1B8h+var_D4], 200001h
0x1802f7fb0  mov     [rsp+1B8h+var_D0], 0
0x1802f7fbc  lea     rdx, [rsp+1B8h+var_D8]
0x1802f7fc4  mov     rcx, rax
0x1802f7fc7  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x1802f7fcc  mov     edx, ebx
0x1802f7fce  mov     rcx, rax
0x1802f7fd1  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x1802f7fd6  xor     ecx, ecx
0x1802f7fd8  mov     [rsp+1B8h+var_6E], cx
0x1802f7fe0  mov     [rsp+1B8h+var_C8], r14b
0x1802f7fe8  movzx   ecx, word ptr [rsp+149h]
0x1802f7ff0  mov     [rsp+1B8h+var_C7], cx
0x1802f7ff8  mov     cl, byte ptr [rsp+1B8h+var_6E+1]
0x1802f7fff  mov     [rsp+1B8h+var_C5], cl
0x1802f8006  mov     [rsp+1B8h+var_C4], 200000h
0x1802f8011  mov     [rsp+1B8h+var_C0], 0
0x1802f801d  lea     rdx, [rsp+1B8h+var_C8]
0x1802f8025  mov     rcx, rax
0x1802f8028  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x1802f802d  lea     rdx, asc_1803721B4; "\r\n"
0x1802f8034  mov     rcx, rax; Src
0x1802f8037  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
  ... truncated ...
```
