# PfSvUnattendCallback

- ea: `0x180084020`
- end: `0x18008425c`
- name: `PfSvUnattendCallback`
- size: `572`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180039f94`
- `0x180084020`
- `0x180084264`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084235`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084235`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800840ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800840ae`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800841de`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800841de`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800840f6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800840f6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180084191`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180084191`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084129`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008414f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084129`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008414f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18008421c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180084225`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18008421c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180084225`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18008411b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18008411b`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180084213`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180084213`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180084141`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180084141`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800841a5`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800841a5`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18008416a`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18008416a`

## string_xrefs

- `0x18008404c`: `CacheList`
- `0x180084060`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\UnattendSettings\Microsoft-Windows-SystemMaintenanceService`

## pseudocode

```c
__int64 PfSvUnattendCallback()
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rsi
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rbx
  int v4; // r14d
  unsigned int v5; // edi
  DWORD i; // edi
  LSTATUS v7; // eax
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+70h] [rbp-90h] BYREF
  wchar_t pszDest[264]; // [rsp+90h] [rbp-70h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  cchName = 0;
  cSubKeys = 0;
  hKey = 0;
  StringCbPrintfW(
    pszDest,
    0x208u,
    L"%s\\%s",
    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\UnattendSettings\\Microsoft-Windows-SystemMaintenanceService",
    L"CacheList");
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszDest, 0, 0x20019u, &hKey)
    && !RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0)
    && cSubKeys )
  {
    v0 = OpenSCManagerW(0, 0, 0xF003Fu);
    v1 = v0;
    if ( v0 )
    {
      v2 = OpenServiceW(v0, L"Sysmain", 0xF003Fu);
      v3 = v2;
      if ( v2 )
      {
        v4 = 0;
        if ( ControlService(v2, 1u, &ServiceStatus) )
        {
          v4 = 1;
          v5 = 0;
          do
          {
            if ( ServiceStatus.dwCurrentState != 3 )
              break;
            if ( v5 >= 0x3A98 )
              break;
            Sleep(0x3E8u);
            v5 += 1000;
          }
          while ( QueryServiceStatus(v3, &ServiceStatus) );
        }
        for ( i = 0; i < 0x10; ++i )
        {
          cchName = 260;
          v7 = RegEnumKeyExW(hKey, i, pszDest, &cchName, 0, 0, 0, 0);
          if ( v7 )
          {
            if ( v7 != 234 )
              break;
          }
          else
          {
            PfSvUnattendProcessSubKey(hKey, pszDest);
          }
        }
        if ( v4 )
          StartServiceW(v3, 0, 0);
        CloseServiceHandle(v3);
      }
      else
      {
        GetLastError();
      }
      CloseServiceHandle(v1);
    }
    else
    {
      GetLastError();
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180084020  push    rbp
0x180084022  push    rbx
0x180084023  push    rsi
0x180084024  push    rdi
0x180084025  push    r14
0x180084027  push    r15
0x180084029  lea     rbp, [rsp-1B8h]
0x180084031  sub     rsp, 2B8h
0x180084038  mov     rax, cs:__security_cookie
0x18008403f  xor     rax, rsp
0x180084042  mov     [rbp+1E0h+var_40], rax
0x180084049  xorps   xmm0, xmm0
0x18008404c  lea     rax, aCachelist; "CacheList"
0x180084053  xor     r15d, r15d
0x180084056  mov     [rsp+2E0h+phkResult], rax
0x18008405b  movups  xmmword ptr [rsp+2E0h+ServiceStatus.dwServiceType], xmm0
0x180084060  lea     r9, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180084067  mov     [rsp+2E0h+cchName], r15d
0x18008406c  lea     r8, aSS; "%s\\%s"
0x180084073  mov     [rsp+2E0h+cSubKeys], r15d
0x180084078  mov     edx, 208h; cbDest
0x18008407d  mov     [rsp+2E0h+hKey], r15
0x180084082  lea     rcx, [rbp+1E0h+pszDest]; pszDest
0x180084086  movups  xmmword ptr [rsp+2E0h+ServiceStatus.dwWin32ExitCode], xmm0
0x18008408b  call    StringCbPrintfW
0x180084090  lea     rax, [rsp+2E0h+hKey]
0x180084095  mov     r9d, 20019h; samDesired
0x18008409b  xor     r8d, r8d; ulOptions
0x18008409e  mov     [rsp+2E0h+phkResult], rax; phkResult
0x1800840a3  lea     rdx, [rbp+1E0h+pszDest]; lpSubKey
0x1800840a7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800840ae  call    cs:__imp_RegOpenKeyExW
0x1800840b4  test    eax, eax
0x1800840b6  jnz     loc_18008422B
0x1800840bc  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1800840c1  lea     rax, [rsp+2E0h+cSubKeys]
0x1800840c6  mov     [rsp+2E0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800840cb  xor     r9d, r9d; lpReserved
0x1800840ce  mov     [rsp+2E0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800840d3  xor     r8d, r8d; lpcchClass
0x1800840d6  mov     [rsp+2E0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800840db  xor     edx, edx; lpClass
0x1800840dd  mov     [rsp+2E0h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800840e2  mov     [rsp+2E0h+lpcValues], r15; lpcValues
0x1800840e7  mov     [rsp+2E0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800840ec  mov     [rsp+2E0h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800840f1  mov     [rsp+2E0h+phkResult], rax; lpcSubKeys
0x1800840f6  call    cs:__imp_RegQueryInfoKeyW
0x1800840fc  test    eax, eax
0x1800840fe  jnz     loc_18008422B
0x180084104  cmp     [rsp+2E0h+cSubKeys], r15d
0x180084109  jz      loc_18008422B
0x18008410f  mov     ebx, 0F003Fh
0x180084114  xor     edx, edx; lpDatabaseName
0x180084116  mov     r8d, ebx; dwDesiredAccess
0x180084119  xor     ecx, ecx; lpMachineName
0x18008411b  call    cs:__imp_OpenSCManagerW
0x180084121  mov     rsi, rax
0x180084124  test    rax, rax
0x180084127  jnz     short loc_180084134
0x180084129  call    cs:__imp_GetLastError
0x18008412f  jmp     loc_18008422B
0x180084134  mov     r8d, ebx; dwDesiredAccess
0x180084137  lea     rdx, ServiceName; "Sysmain"
0x18008413e  mov     rcx, rsi; hSCManager
0x180084141  call    cs:__imp_OpenServiceW
0x180084147  mov     rbx, rax
0x18008414a  test    rax, rax
0x18008414d  jnz     short loc_18008415A
0x18008414f  call    cs:__imp_GetLastError
0x180084155  jmp     loc_180084222
0x18008415a  lea     r8, [rsp+2E0h+ServiceStatus]; lpServiceStatus
0x18008415f  mov     edx, 1; dwControl
0x180084164  mov     rcx, rbx; hService
0x180084167  mov     r14d, r15d
0x18008416a  call    cs:__imp_ControlService
0x180084170  test    eax, eax
0x180084172  jz      short loc_1800841AF
0x180084174  mov     r14d, 1
0x18008417a  mov     edi, r15d
0x18008417d  cmp     [rsp+2E0h+ServiceStatus.dwCurrentState], 3
0x180084182  jnz     short loc_1800841AF
0x180084184  cmp     edi, 3A98h
0x18008418a  jnb     short loc_1800841AF
0x18008418c  mov     ecx, 3E8h; dwMilliseconds
0x180084191  call    cs:__imp_Sleep
0x180084197  lea     rdx, [rsp+2E0h+ServiceStatus]; lpServiceStatus
0x18008419c  mov     rcx, rbx; hService
0x18008419f  add     edi, 3E8h
0x1800841a5  call    cs:__imp_QueryServiceStatus
0x1800841ab  test    eax, eax
0x1800841ad  jnz     short loc_18008417D
0x1800841af  mov     edi, r15d
0x1800841b2  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1800841b7  lea     r9, [rsp+2E0h+cchName]; lpcchName
0x1800841bc  mov     [rsp+2E0h+lpcValues], r15; lpftLastWriteTime
0x1800841c1  lea     r8, [rbp+1E0h+pszDest]; lpName
0x1800841c5  mov     [rsp+2E0h+lpcbMaxClassLen], r15; lpcchClass
0x1800841ca  mov     edx, edi; dwIndex
0x1800841cc  mov     [rsp+2E0h+lpcbMaxSubKeyLen], r15; lpClass
0x1800841d1  mov     [rsp+2E0h+phkResult], r15; lpReserved
0x1800841d6  mov     [rsp+2E0h+cchName], 104h
0x1800841de  call    cs:__imp_RegEnumKeyExW
0x1800841e4  test    eax, eax
0x1800841e6  jz      short loc_1800841F1
0x1800841e8  cmp     eax, 0EAh
0x1800841ed  jnz     short loc_180084206
0x1800841ef  jmp     short loc_1800841FF
0x1800841f1  mov     rcx, [rsp+2E0h+hKey]
0x1800841f6  lea     rdx, [rbp+1E0h+pszDest]
0x1800841fa  call    PfSvUnattendProcessSubKey
0x1800841ff  inc     edi
0x180084201  cmp     edi, 10h
0x180084204  jb      short loc_1800841B2
0x180084206  test    r14d, r14d
0x180084209  jz      short loc_180084219
0x18008420b  xor     r8d, r8d; lpServiceArgVectors
0x18008420e  xor     edx, edx; dwNumServiceArgs
0x180084210  mov     rcx, rbx; hService
0x180084213  call    cs:__imp_StartServiceW
0x180084219  mov     rcx, rbx; hSCObject
0x18008421c  call    cs:__imp_CloseServiceHandle
0x180084222  mov     rcx, rsi; hSCObject
0x180084225  call    cs:__imp_CloseServiceHandle
0x18008422b  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180084230  test    rcx, rcx
0x180084233  jz      short loc_18008423B
0x180084235  call    cs:__imp_RegCloseKey
0x18008423b  xor     eax, eax
0x18008423d  mov     rcx, [rbp+1E0h+var_40]
0x180084244  xor     rcx, rsp; StackCookie
0x180084247  call    __security_check_cookie
0x18008424c  add     rsp, 2B8h
0x180084253  pop     r15
0x180084255  pop     r14
0x180084257  pop     rdi
0x180084258  pop     rsi
0x180084259  pop     rbx
0x18008425a  pop     rbp
0x18008425b  retn
```
