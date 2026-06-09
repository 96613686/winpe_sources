# PfXpBuildBootLoaderFilesList

- ea: `0x180093a8c`
- end: `0x180093ee9`
- name: `PfXpBuildBootLoaderFilesList`
- size: `1117`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800197c4`

## callees

- `0x18001a400`
- `0x180049d6c`
- `0x1800784c8`
- `0x180093660`
- `0x180093a8c`
- `0x1800943e0`
- `0x180094654`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093aef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093ca1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093d87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093e66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093aef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093ca1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093d87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093e66`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180093ae5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180093ae5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180093cd4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180093daf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180093e96`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180093eb1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180093cd4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180093daf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180093e96`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180093eb1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180093cee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180093dc7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180093cee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180093dc7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180093e3c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180093e5e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180093e7b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180093e3c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180093e5e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180093e7b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180093c31`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180093c31`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180093d54`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180093d54`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180093d7d`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180093d7d`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x180093c93`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x180093c93`

## string_xrefs

- `0x180093b71`: `hal.dll`
- `0x180093baf`: `config\system`
- `0x180093bed`: `config\software`

## pseudocode

```c
__int64 __fastcall PfXpBuildBootLoaderFilesList(__int64 a1)
{
  UINT SystemDirectoryW; // eax
  DWORD LastError; // ebx
  __int64 v4; // rdi
  UINT v5; // ebx
  SC_HANDLE v6; // rbx
  BYTE *lpServices; // rsi
  struct _QUERY_SERVICE_CONFIGW *v8; // rdi
  DWORD cbBufSize; // r15d
  int v10; // r14d
  DWORD v11; // ecx
  DWORD i; // r15d
  SC_HANDLE v13; // r13
  DWORD v14; // eax
  int v15; // r14d
  __int64 v16; // r8
  DWORD v18; // [rsp+50h] [rbp-B0h] BYREF
  DWORD ResumeHandle; // [rsp+54h] [rbp-ACh] BYREF
  DWORD pcbBytesNeeded; // [rsp+58h] [rbp-A8h] BYREF
  DWORD ServicesReturned; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD v22; // [rsp+60h] [rbp-A0h]
  _DWORD v23[3]; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v24; // [rsp+70h] [rbp-90h]
  wchar_t Buffer[264]; // [rsp+80h] [rbp-80h] BYREF

  pcbBytesNeeded = 0;
  v18 = 0;
  ResumeHandle = 0;
  v23[0] = 0;
  ServicesReturned = 0;
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
  if ( !SystemDirectoryW )
    return GetLastError();
  v4 = SystemDirectoryW + 1;
  if ( (unsigned int)v4 >= 0x104 )
    return 122;
  Buffer[SystemDirectoryW] = 92;
  if ( (unsigned __int64)(2 * v4) >= 0x20A )
    _report_rangecheckfailure();
  v5 = SystemDirectoryW + 13;
  Buffer[v4] = 0;
  if ( SystemDirectoryW + 13 >= 0x104 )
    return 122;
  StringCbCatW(Buffer, 0x20Au, L"ntoskrnl.exe");
  LastError = PfXpAddBootImageAndImportsToList(a1, Buffer, v5);
  if ( LastError )
    return LastError;
  if ( (unsigned int)(v4 + 7) >= 0x104 )
    return 122;
  Buffer[v4] = 0;
  StringCbCatW(Buffer, 0x20Au, L"hal.dll");
  LastError = PfXpAddBootImageAndImportsToList(a1, Buffer, (unsigned int)(v4 + 7));
  if ( LastError )
    return LastError;
  if ( (unsigned int)(v4 + 13) >= 0x104 )
    return 122;
  Buffer[v4] = 0;
  StringCbCatW(Buffer, 0x20Au, L"config\\system");
  LastError = PfXpAddToPathList(a1);
  if ( LastError )
    return LastError;
  if ( (unsigned int)(v4 + 15) >= 0x104 )
    return 122;
  Buffer[v4] = 0;
  StringCbCatW(Buffer, 0x20Au, L"config\\software");
  LastError = PfXpAddToPathList(a1);
  if ( LastError )
    return LastError;
  PfXpGetBootLoaderNlsFileNames(a1);
  *(_QWORD *)&v23[1] = OpenSCManagerW(0, 0, 0xF003Fu);
  v6 = *(SC_HANDLE *)&v23[1];
  if ( *(_QWORD *)&v23[1] )
  {
    lpServices = 0;
    v8 = 0;
    cbBufSize = 0;
    v10 = 0;
    while ( 1 )
    {
      ResumeHandle = 0;
      if ( EnumServicesStatusExW(
             v6,
             SC_ENUM_PROCESS_INFO,
             0xBu,
             1u,
             lpServices,
             cbBufSize,
             &pcbBytesNeeded,
             &ServicesReturned,
             &ResumeHandle,
             0) )
      {
        break;
      }
      LastError = GetLastError();
      if ( LastError != 234 )
        goto LABEL_48;
      v11 = cbBufSize + pcbBytesNeeded;
      v18 = cbBufSize + pcbBytesNeeded;
      if ( lpServices )
      {
        HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, lpServices);
        v11 = v18;
      }
      lpServices = (BYTE *)HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v11);
      if ( !lpServices )
      {
        LastError = 8;
        goto LABEL_48;
      }
      if ( (unsigned int)++v10 > 0x64 )
      {
        LastError = 1;
        goto LABEL_48;
      }
      cbBufSize = v18;
      v6 = *(SC_HANDLE *)&v23[1];
    }
    v22 = 0;
    for ( i = 0; i < ServicesReturned; ++i )
    {
      v24 = 56LL * i;
      v13 = OpenServiceW(v6, *(LPCWSTR *)&lpServices[v24], 1u);
      if ( !v13 )
      {
        LastError = GetLastError();
        goto LABEL_48;
      }
      v14 = v22;
      v15 = 0;
      while ( !QueryServiceConfigW(v13, v8, v14, &v18) )
      {
        LastError = GetLastError();
        if ( LastError != 122 )
          goto LABEL_45;
        if ( v8 )
          HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v8);
        v8 = (struct _QUERY_SERVICE_CONFIGW *)HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v18);
        if ( !v8 )
        {
          LastError = 8;
LABEL_45:
          CloseServiceHandle(v13);
          goto LABEL_48;
        }
        if ( (unsigned int)++v15 > 0x64 )
          goto LABEL_44;
        v14 = v18;
        v22 = v18;
      }
      if ( !v8 )
      {
LABEL_44:
        LastError = 1;
        goto LABEL_45;
      }
      if ( (!v8->dwStartType || v8->dwServiceType == 2)
        && !(unsigned int)PfXpGetBootServiceFullPath(
                            *(STRSAFE_LPCWSTR *)&lpServices[v24],
                            v8->lpBinaryPathName,
                            Buffer,
                            (__int64)v23) )
      {
        v16 = -1;
        do
          ++v16;
        while ( Buffer[v16] );
        PfXpAddBootImageAndImportsToList(a1, Buffer, v16);
      }
      CloseServiceHandle(v13);
      v6 = *(SC_HANDLE *)&v23[1];
    }
    LastError = 0;
LABEL_48:
    CloseServiceHandle(*(SC_HANDLE *)&v23[1]);
    if ( lpServices )
      HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, lpServices);
    if ( v8 )
      HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v8);
  }
  else
  {
    return GetLastError();
  }
  return LastError;
}

```

## disassembly

```asm
0x180093a8c  push    rbp
0x180093a8e  push    rbx
0x180093a8f  push    rsi
0x180093a90  push    rdi
0x180093a91  push    r12
0x180093a93  push    r13
0x180093a95  push    r14
0x180093a97  push    r15
0x180093a99  lea     rbp, [rsp-1A8h]
0x180093aa1  sub     rsp, 2A8h
0x180093aa8  mov     rax, cs:__security_cookie
0x180093aaf  xor     rax, rsp
0x180093ab2  mov     [rbp+1E0h+var_50], rax
0x180093ab9  xor     r13d, r13d
0x180093abc  mov     r12, rcx
0x180093abf  mov     r14d, 104h
0x180093ac5  mov     [rsp+2E0h+var_288], r13d
0x180093aca  mov     edx, r14d; uSize
0x180093acd  mov     [rsp+2E0h+var_290], r13d
0x180093ad2  lea     rcx, [rbp+1E0h+Buffer]; lpBuffer
0x180093ad6  mov     [rsp+2E0h+ResumeHandle], r13d
0x180093adb  mov     dword ptr [rsp+2E0h+var_27C], r13d
0x180093ae0  mov     [rsp+2E0h+ServicesReturned], r13d
0x180093ae5  call    cs:__imp_GetSystemDirectoryW
0x180093aeb  test    eax, eax
0x180093aed  jnz     short loc_180093AFC
0x180093aef  call    cs:__imp_GetLastError
0x180093af5  mov     ebx, eax
0x180093af7  jmp     loc_180093EC4
0x180093afc  lea     edi, [rax+1]
0x180093aff  cmp     edi, r14d
0x180093b02  jnb     loc_180093EBF
0x180093b08  mov     eax, eax
0x180093b0a  lea     rsi, [rdi+rdi]
0x180093b0e  mov     r15d, 20Ah
0x180093b14  mov     ecx, 5Ch ; '\'
0x180093b19  mov     [rbp+rax*2+1E0h+Buffer], cx
0x180093b1e  cmp     rsi, r15
0x180093b21  jnb     loc_180093EB9
0x180093b27  lea     ebx, [rdi+0Ch]
0x180093b2a  mov     [rbp+rsi+1E0h+Buffer], r13w
0x180093b30  cmp     ebx, r14d
0x180093b33  jnb     loc_180093EBF
0x180093b39  lea     r8, aNtoskrnlExe; "ntoskrnl.exe"
0x180093b40  mov     edx, r15d; cbDest
0x180093b43  lea     rcx, [rbp+1E0h+Buffer]; pszDest
0x180093b47  call    StringCbCatW
0x180093b4c  mov     r8d, ebx
0x180093b4f  lea     rdx, [rbp+1E0h+Buffer]
0x180093b53  mov     rcx, r12
0x180093b56  call    PfXpAddBootImageAndImportsToList
0x180093b5b  mov     ebx, eax
0x180093b5d  test    eax, eax
0x180093b5f  jnz     loc_180093EC4
0x180093b65  lea     ebx, [rdi+7]
0x180093b68  cmp     ebx, r14d
0x180093b6b  jnb     loc_180093EBF
0x180093b71  lea     r8, aHalDll; "hal.dll"
0x180093b78  mov     [rbp+rsi+1E0h+Buffer], r13w
0x180093b7e  mov     edx, r15d; cbDest
0x180093b81  lea     rcx, [rbp+1E0h+Buffer]; pszDest
0x180093b85  call    StringCbCatW
0x180093b8a  mov     r8d, ebx
0x180093b8d  lea     rdx, [rbp+1E0h+Buffer]
0x180093b91  mov     rcx, r12
0x180093b94  call    PfXpAddBootImageAndImportsToList
0x180093b99  mov     ebx, eax
0x180093b9b  test    eax, eax
0x180093b9d  jnz     loc_180093EC4
0x180093ba3  lea     ebx, [rdi+0Dh]
0x180093ba6  cmp     ebx, r14d
0x180093ba9  jnb     loc_180093EBF
0x180093baf  lea     r8, aConfigSystem; "config\\system"
0x180093bb6  mov     [rbp+rsi+1E0h+Buffer], r13w
0x180093bbc  mov     edx, r15d; cbDest
0x180093bbf  lea     rcx, [rbp+1E0h+Buffer]; pszDest
0x180093bc3  call    StringCbCatW
0x180093bc8  mov     r8d, ebx
0x180093bcb  lea     rdx, [rbp+1E0h+Buffer]
0x180093bcf  mov     rcx, r12
0x180093bd2  call    PfXpAddToPathList
0x180093bd7  mov     ebx, eax
0x180093bd9  test    eax, eax
0x180093bdb  jnz     loc_180093EC4
0x180093be1  add     edi, 0Fh
0x180093be4  cmp     edi, r14d
0x180093be7  jnb     loc_180093EBF
0x180093bed  lea     r8, aConfigSoftware; "config\\software"
0x180093bf4  mov     [rbp+rsi+1E0h+Buffer], r13w
0x180093bfa  mov     edx, r15d; cbDest
0x180093bfd  lea     rcx, [rbp+1E0h+Buffer]; pszDest
0x180093c01  call    StringCbCatW
0x180093c06  mov     r8d, edi
0x180093c09  lea     rdx, [rbp+1E0h+Buffer]
0x180093c0d  mov     rcx, r12
0x180093c10  call    PfXpAddToPathList
0x180093c15  mov     ebx, eax
0x180093c17  test    eax, eax
0x180093c19  jnz     loc_180093EC4
0x180093c1f  mov     rcx, r12
0x180093c22  call    PfXpGetBootLoaderNlsFileNames
0x180093c27  xor     edx, edx; lpDatabaseName
0x180093c29  xor     ecx, ecx; lpMachineName
0x180093c2b  mov     r8d, 0F003Fh; dwDesiredAccess
0x180093c31  call    cs:__imp_OpenSCManagerW
0x180093c37  mov     qword ptr [rsp+2E0h+var_27C+4], rax
0x180093c3c  mov     rbx, rax
0x180093c3f  test    rax, rax
0x180093c42  jz      loc_180093AEF
0x180093c48  mov     rsi, r13
0x180093c4b  mov     rdi, r13
0x180093c4e  mov     r15d, r13d
0x180093c51  mov     r14d, r13d
0x180093c54  mov     [rsp+2E0h+pszGroupName], r13; pszGroupName
0x180093c59  lea     rax, [rsp+2E0h+ResumeHandle]
0x180093c5e  mov     [rsp+2E0h+lpResumeHandle], rax; lpResumeHandle
0x180093c63  xor     edx, edx; InfoLevel
0x180093c65  lea     rax, [rsp+2E0h+ServicesReturned]
0x180093c6a  mov     [rsp+2E0h+ResumeHandle], r13d
0x180093c6f  mov     [rsp+2E0h+lpServicesReturned], rax; lpServicesReturned
0x180093c74  mov     rcx, rbx; hSCManager
0x180093c77  lea     rax, [rsp+2E0h+var_288]
0x180093c7c  mov     [rsp+2E0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180093c81  lea     r9d, [rdx+1]; dwServiceState
0x180093c85  mov     [rsp+2E0h+cbBufSize], r15d; cbBufSize
0x180093c8a  lea     r8d, [rdx+0Bh]; dwServiceType
0x180093c8e  mov     [rsp+2E0h+lpServices], rsi; lpServices
0x180093c93  call    cs:__imp_EnumServicesStatusExW
0x180093c99  test    eax, eax
0x180093c9b  jnz     loc_180093D28
0x180093ca1  call    cs:__imp_GetLastError
0x180093ca7  mov     ebx, eax
0x180093ca9  cmp     eax, 0EAh
0x180093cae  jnz     loc_180093E76
0x180093cb4  mov     ecx, [rsp+2E0h+var_288]
0x180093cb8  add     ecx, r15d
0x180093cbb  mov     [rsp+2E0h+var_290], ecx
0x180093cbf  test    rsi, rsi
0x180093cc2  jz      short loc_180093CDE
0x180093cc4  mov     rcx, cs:PfSvcGlobals
0x180093ccb  mov     r8, rsi; lpMem
0x180093cce  xor     edx, edx; dwFlags
0x180093cd0  mov     rcx, [rcx+58h]; hHeap
0x180093cd4  call    cs:__imp_HeapFree
0x180093cda  mov     ecx, [rsp+2E0h+var_290]
0x180093cde  mov     r8d, ecx; dwBytes
0x180093ce1  xor     edx, edx; dwFlags
0x180093ce3  mov     rcx, cs:PfSvcGlobals
0x180093cea  mov     rcx, [rcx+58h]; hHeap
0x180093cee  call    cs:__imp_HeapAlloc
0x180093cf4  mov     rsi, rax
0x180093cf7  test    rax, rax
0x180093cfa  jz      short loc_180093D1E
0x180093cfc  inc     r14d
0x180093cff  cmp     r14d, 64h ; 'd'
0x180093d03  ja      short loc_180093D14
0x180093d05  mov     r15d, [rsp+2E0h+var_290]
0x180093d0a  mov     rbx, qword ptr [rsp+2E0h+var_27C+4]
0x180093d0f  jmp     loc_180093C54
0x180093d14  mov     ebx, 1
0x180093d19  jmp     loc_180093E76
0x180093d1e  mov     ebx, 8
0x180093d23  jmp     loc_180093E76
0x180093d28  mov     [rsp+2E0h+var_280], r13d
0x180093d2d  mov     r15d, r13d
0x180093d30  cmp     r15d, [rsp+2E0h+ServicesReturned]
0x180093d35  jnb     loc_180093E70
0x180093d3b  mov     eax, r15d
0x180093d3e  mov     r8d, 1; dwDesiredAccess
0x180093d44  imul    rax, 38h ; '8'
0x180093d48  mov     rcx, rbx; hSCManager
0x180093d4b  mov     [rsp+2E0h+var_270], rax
0x180093d50  mov     rdx, [rax+rsi]; lpServiceName
0x180093d54  call    cs:__imp_OpenServiceW
0x180093d5a  xor     ebx, ebx
0x180093d5c  mov     r13, rax
0x180093d5f  test    rax, rax
0x180093d62  jz      loc_180093E66
0x180093d68  mov     eax, [rsp+2E0h+var_280]
0x180093d6c  mov     r14d, ebx
0x180093d6f  lea     r9, [rsp+2E0h+var_290]; pcbBytesNeeded
0x180093d74  mov     r8d, eax; cbBufSize
0x180093d77  mov     rdx, rdi; lpServiceConfig
0x180093d7a  mov     rcx, r13; hService
0x180093d7d  call    cs:__imp_QueryServiceConfigW
0x180093d83  test    eax, eax
0x180093d85  jnz     short loc_180093DE8
0x180093d87  call    cs:__imp_GetLastError
0x180093d8d  mov     ebx, eax
0x180093d8f  cmp     eax, 7Ah ; 'z'
0x180093d92  jnz     loc_180093E5B
0x180093d98  xor     ebx, ebx
0x180093d9a  test    rdi, rdi
0x180093d9d  jz      short loc_180093DB5
0x180093d9f  mov     rcx, cs:PfSvcGlobals
0x180093da6  mov     r8, rdi; lpMem
0x180093da9  xor     edx, edx; dwFlags
0x180093dab  mov     rcx, [rcx+58h]; hHeap
0x180093daf  call    cs:__imp_HeapFree
0x180093db5  mov     rcx, cs:PfSvcGlobals
0x180093dbc  xor     edx, edx; dwFlags
0x180093dbe  mov     r8d, [rsp+2E0h+var_290]; dwBytes
0x180093dc3  mov     rcx, [rcx+58h]; hHeap
0x180093dc7  call    cs:__imp_HeapAlloc
0x180093dcd  mov     rdi, rax
0x180093dd0  test    rax, rax
0x180093dd3  jz      short loc_180093E4F
0x180093dd5  inc     r14d
0x180093dd8  cmp     r14d, 64h ; 'd'
0x180093ddc  ja      short loc_180093E56
0x180093dde  mov     eax, [rsp+2E0h+var_290]
0x180093de2  mov     [rsp+2E0h+var_280], eax
0x180093de6  jmp     short loc_180093D6F
0x180093de8  test    rdi, rdi
0x180093deb  jz      short loc_180093E56
0x180093ded  cmp     [rdi+4], ebx
0x180093df0  jz      short loc_180093DF7
0x180093df2  cmp     dword ptr [rdi], 2
0x180093df5  jnz     short loc_180093E39
0x180093df7  mov     rcx, [rsp+2E0h+var_270]
0x180093dfc  lea     rax, [rsp+2E0h+var_27C]
0x180093e01  mov     rdx, [rdi+10h]; lpFileName
0x180093e05  lea     r8, [rbp+1E0h+Buffer]; lpBuffer
0x180093e09  mov     [rsp+2E0h+lpServices], rax; __int64
0x180093e0e  mov     rcx, [rcx+rsi]; pszSrc
0x180093e12  call    PfXpGetBootServiceFullPath
0x180093e17  test    eax, eax
0x180093e19  jnz     short loc_180093E39
0x180093e1b  lea     rax, [rbp+1E0h+Buffer]
0x180093e1f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180093e23  inc     r8
0x180093e26  cmp     [rax+r8*2], bx
0x180093e2b  jnz     short loc_180093E23
0x180093e2d  lea     rdx, [rbp+1E0h+Buffer]
0x180093e31  mov     rcx, r12
0x180093e34  call    PfXpAddBootImageAndImportsToList
0x180093e39  mov     rcx, r13; hSCObject
0x180093e3c  call    cs:__imp_CloseServiceHandle
0x180093e42  mov     rbx, qword ptr [rsp+2E0h+var_27C+4]
0x180093e47  inc     r15d
0x180093e4a  jmp     loc_180093D30
0x180093e4f  mov     ebx, 8
0x180093e54  jmp     short loc_180093E5B
0x180093e56  mov     ebx, 1
0x180093e5b  mov     rcx, r13; hSCObject
0x180093e5e  call    cs:__imp_CloseServiceHandle
0x180093e64  jmp     short loc_180093E76
0x180093e66  call    cs:__imp_GetLastError
0x180093e6c  mov     ebx, eax
0x180093e6e  jmp     short loc_180093E76
0x180093e70  xor     r13d, r13d
0x180093e73  mov     ebx, r13d
0x180093e76  mov     rcx, qword ptr [rsp+2E0h+var_27C+4]; hSCObject
0x180093e7b  call    cs:__imp_CloseServiceHandle
0x180093e81  test    rsi, rsi
0x180093e84  jz      short loc_180093E9C
0x180093e86  mov     rcx, cs:PfSvcGlobals
0x180093e8d  mov     r8, rsi; lpMem
0x180093e90  xor     edx, edx; dwFlags
0x180093e92  mov     rcx, [rcx+58h]; hHeap
0x180093e96  call    cs:__imp_HeapFree
0x180093e9c  test    rdi, rdi
0x180093e9f  jz      short loc_180093EC4
0x180093ea1  mov     rcx, cs:PfSvcGlobals
0x180093ea8  mov     r8, rdi; lpMem
0x180093eab  xor     edx, edx; dwFlags
0x180093ead  mov     rcx, [rcx+58h]; hHeap
0x180093eb1  call    cs:__imp_HeapFree
0x180093eb7  jmp     short loc_180093EC4
0x180093eb9  call    __report_rangecheckfailure
0x180093ebf  mov     ebx, 7Ah ; 'z'
0x180093ec4  mov     eax, ebx
0x180093ec6  mov     rcx, [rbp+1E0h+var_50]
0x180093ecd  xor     rcx, rsp; StackCookie
0x180093ed0  call    __security_check_cookie
0x180093ed5  add     rsp, 2A8h
0x180093edc  pop     r15
0x180093ede  pop     r14
0x180093ee0  pop     r13
0x180093ee2  pop     r12
0x180093ee4  pop     rdi
0x180093ee5  pop     rsi
0x180093ee6  pop     rbx
0x180093ee7  pop     rbp
0x180093ee8  retn
```
