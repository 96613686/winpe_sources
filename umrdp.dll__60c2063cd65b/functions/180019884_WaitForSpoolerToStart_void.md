# WaitForSpoolerToStart(void)

- ea: `0x180019884`
- end: `0x1800199f0`
- name: `?WaitForSpoolerToStart@@YAKXZ`
- size: `364`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x1800199f8`

## callees

- `0x180019884`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800198cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800198f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001992f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019959`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019979`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001999e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800199a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800198cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800198f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001992f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019959`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019979`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001999e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800199a4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001996b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001996b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800199b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800199b6`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800198e4`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800198e4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800198fd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800199cb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800198fd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800199cb`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800198bb`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800198bb`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180019925`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180019925`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18001994f`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180019994`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18001994f`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180019994`

## string_xrefs

- `0x1800198b2`: `ServicesActive`

## pseudocode

```c
__int64 WaitForSpoolerToStart(void)
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rsi
  SC_HANDLE v2; // rdi
  DWORD LastError; // ebx
  struct _QUERY_SERVICE_CONFIGW *v4; // rax
  struct _QUERY_SERVICE_CONFIGW *v5; // rsi
  DWORD pcbBytesNeeded; // [rsp+20h] [rbp-38h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+28h] [rbp-30h] BYREF

  pcbBytesNeeded = 0;
  v0 = OpenSCManagerW(0, L"ServicesActive", 0x80000000);
  v1 = v0;
  if ( v0 )
  {
    LastError = 0;
    v2 = OpenServiceW(v0, L"Spooler", 0x80000000);
    if ( !v2 )
      LastError = GetLastError();
    CloseServiceHandle(v1);
  }
  else
  {
    v2 = 0;
    LastError = GetLastError();
  }
  if ( !LastError )
  {
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( v2 )
    {
      if ( QueryServiceStatus(v2, &ServiceStatus) )
      {
        if ( ServiceStatus.dwCurrentState == 4 )
        {
LABEL_21:
          CloseServiceHandle(v2);
          return LastError;
        }
      }
      else
      {
        GetLastError();
      }
    }
    if ( QueryServiceConfigW(v2, 0, 0, &pcbBytesNeeded) || GetLastError() != 122 )
    {
      LastError = -2147418113;
    }
    else
    {
      v4 = (struct _QUERY_SERVICE_CONFIGW *)LocalAlloc(0x40u, pcbBytesNeeded);
      v5 = v4;
      if ( v4 )
      {
        if ( QueryServiceConfigW(v2, v4, pcbBytesNeeded, &pcbBytesNeeded) )
        {
          LastError = -2147467259;
        }
        else
        {
          GetLastError();
          LastError = GetLastError();
        }
        LocalFree(v5);
      }
      else
      {
        GetLastError();
        LastError = 14;
      }
    }
  }
  if ( v2 )
    goto LABEL_21;
  return LastError;
}

```

## disassembly

```asm
0x180019884  mov     [rsp+arg_0], rbx
0x180019889  mov     [rsp+arg_8], rsi
0x18001988e  push    rdi
0x18001988f  sub     rsp, 50h
0x180019893  mov     rax, cs:__security_cookie
0x18001989a  xor     rax, rsp
0x18001989d  mov     [rsp+58h+var_10], rax
0x1800198a2  mov     edi, 80000000h
0x1800198a7  mov     [rsp+58h+pcbBytesNeeded], 0
0x1800198af  mov     r8d, edi; dwDesiredAccess
0x1800198b2  lea     rdx, DatabaseName; "ServicesActive"
0x1800198b9  xor     ecx, ecx; lpMachineName
0x1800198bb  call    cs:__imp_OpenSCManagerW
0x1800198c1  mov     rsi, rax
0x1800198c4  test    rax, rax
0x1800198c7  jnz     short loc_1800198D5
0x1800198c9  xor     edi, edi
0x1800198cb  call    cs:__imp_GetLastError
0x1800198d1  mov     ebx, eax
0x1800198d3  jmp     short loc_180019903
0x1800198d5  mov     r8d, edi; dwDesiredAccess
0x1800198d8  lea     rdx, aSpooler; "Spooler"
0x1800198df  mov     rcx, rsi; hSCManager
0x1800198e2  xor     ebx, ebx
0x1800198e4  call    cs:__imp_OpenServiceW
0x1800198ea  mov     rdi, rax
0x1800198ed  test    rax, rax
0x1800198f0  jnz     short loc_1800198FA
0x1800198f2  call    cs:__imp_GetLastError
0x1800198f8  mov     ebx, eax
0x1800198fa  mov     rcx, rsi; hSCObject
0x1800198fd  call    cs:__imp_CloseServiceHandle
0x180019903  test    ebx, ebx
0x180019905  jnz     loc_1800199C3
0x18001990b  xorps   xmm0, xmm0
0x18001990e  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x180019913  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x180019918  test    rdi, rdi
0x18001991b  jz      short loc_180019942
0x18001991d  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x180019922  mov     rcx, rdi; hService
0x180019925  call    cs:__imp_QueryServiceStatus
0x18001992b  test    eax, eax
0x18001992d  jnz     short loc_180019937
0x18001992f  call    cs:__imp_GetLastError
0x180019935  jmp     short loc_180019942
0x180019937  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 4
0x18001993c  jz      loc_1800199C8
0x180019942  lea     r9, [rsp+58h+pcbBytesNeeded]; pcbBytesNeeded
0x180019947  xor     r8d, r8d; cbBufSize
0x18001994a  xor     edx, edx; lpServiceConfig
0x18001994c  mov     rcx, rdi; hService
0x18001994f  call    cs:__imp_QueryServiceConfigW
0x180019955  test    eax, eax
0x180019957  jnz     short loc_1800199BE
0x180019959  call    cs:__imp_GetLastError
0x18001995f  cmp     eax, 7Ah ; 'z'
0x180019962  jnz     short loc_1800199BE
0x180019964  mov     edx, [rsp+58h+pcbBytesNeeded]; uBytes
0x180019968  lea     ecx, [rax-3Ah]; uFlags
0x18001996b  call    cs:__imp_LocalAlloc
0x180019971  mov     rsi, rax
0x180019974  test    rax, rax
0x180019977  jnz     short loc_180019984
0x180019979  call    cs:__imp_GetLastError
0x18001997f  lea     ebx, [rsi+0Eh]
0x180019982  jmp     short loc_1800199C3
0x180019984  mov     r8d, [rsp+58h+pcbBytesNeeded]; cbBufSize
0x180019989  lea     r9, [rsp+58h+pcbBytesNeeded]; pcbBytesNeeded
0x18001998e  mov     rdx, rsi; lpServiceConfig
0x180019991  mov     rcx, rdi; hService
0x180019994  call    cs:__imp_QueryServiceConfigW
0x18001999a  test    eax, eax
0x18001999c  jnz     short loc_1800199AE
0x18001999e  call    cs:__imp_GetLastError
0x1800199a4  call    cs:__imp_GetLastError
0x1800199aa  mov     ebx, eax
0x1800199ac  jmp     short loc_1800199B3
0x1800199ae  mov     ebx, 80004005h
0x1800199b3  mov     rcx, rsi; hMem
0x1800199b6  call    cs:__imp_LocalFree
0x1800199bc  jmp     short loc_1800199C3
0x1800199be  mov     ebx, 8000FFFFh
0x1800199c3  test    rdi, rdi
0x1800199c6  jz      short loc_1800199D1
0x1800199c8  mov     rcx, rdi; hSCObject
0x1800199cb  call    cs:__imp_CloseServiceHandle
0x1800199d1  mov     eax, ebx
0x1800199d3  mov     rcx, [rsp+58h+var_10]
0x1800199d8  xor     rcx, rsp; StackCookie
0x1800199db  call    __security_check_cookie
0x1800199e0  mov     rbx, [rsp+58h+arg_0]
0x1800199e5  mov     rsi, [rsp+58h+arg_8]
0x1800199ea  add     rsp, 50h
0x1800199ee  pop     rdi
0x1800199ef  retn
```
