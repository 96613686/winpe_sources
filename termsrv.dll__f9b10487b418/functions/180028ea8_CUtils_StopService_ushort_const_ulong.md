# CUtils::StopService(ushort const *,ulong)

- ea: `0x180028ea8`
- end: `0x180028fed`
- name: `?StopService@CUtils@@SAJPEBGK@Z`
- size: `325`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18004c2b8`

## callees

- `0x18000a210`
- `0x180028ea8`
- `0x1800321f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028eec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028eec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f8f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180028fbf`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180028fc8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180028fbf`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180028fc8`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180028ede`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180028ede`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180028f26`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180028f26`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180028f85`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180028f85`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180028f67`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180028f67`

## string_xrefs

- `0x180028f4c`: `OpenService failed: 0x%x`
- `0x180028fa7`: `StopService failed: 0x%x`
- `0x180028f04`: `OpenSCManager failed: 0x%x`

## pseudocode

```c
__int64 __fastcall CUtils::StopService(LPCWSTR lpServiceName)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rsi
  signed int v4; // eax
  unsigned int v5; // ebx
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rdi
  signed int v8; // eax
  signed int LastError; // eax
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v2 = OpenSCManagerW(0, 0, 1u);
  v3 = v2;
  if ( v2 )
  {
    v6 = OpenServiceW(v2, lpServiceName, 0x24u);
    v7 = v6;
    if ( v6 )
    {
      if ( QueryServiceStatus(v6, &ServiceStatus) && ServiceStatus.dwCurrentState == 1
        || ControlService(v7, 1u, &ServiceStatus) )
      {
        v5 = 0;
      }
      else
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        _DbgPrintMessage(8, "StopService failed: 0x%x", v5);
      }
      CloseServiceHandle(v7);
    }
    else
    {
      v8 = GetLastError();
      v5 = v8;
      if ( v8 > 0 )
        v5 = (unsigned __int16)v8 | 0x80070000;
      _DbgPrintMessage(8, "OpenService failed: 0x%x", v5);
    }
    CloseServiceHandle(v3);
  }
  else
  {
    v4 = GetLastError();
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    _DbgPrintMessage(8, "OpenSCManager failed: 0x%x", v5);
  }
  return v5;
}

```

## disassembly

```asm
0x180028ea8  mov     [rsp+arg_8], rbx
0x180028ead  mov     [rsp+arg_10], rsi
0x180028eb2  push    rdi
0x180028eb3  sub     rsp, 50h
0x180028eb7  mov     rax, cs:__security_cookie
0x180028ebe  xor     rax, rsp
0x180028ec1  mov     [rsp+58h+var_18], rax
0x180028ec6  xorps   xmm0, xmm0
0x180028ec9  xor     edx, edx; lpDatabaseName
0x180028ecb  mov     rbx, rcx
0x180028ece  xor     ecx, ecx; lpMachineName
0x180028ed0  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x180028ed5  lea     r8d, [rdx+1]; dwDesiredAccess
0x180028ed9  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x180028ede  call    cs:__imp_OpenSCManagerW
0x180028ee4  mov     rsi, rax
0x180028ee7  test    rax, rax
0x180028eea  jnz     short loc_180028F1A
0x180028eec  call    cs:__imp_GetLastError
0x180028ef2  mov     ebx, eax
0x180028ef4  test    eax, eax
0x180028ef6  jle     short loc_180028F01
0x180028ef8  movzx   ebx, ax
0x180028efb  or      ebx, 80070000h
0x180028f01  mov     r8d, ebx
0x180028f04  lea     rdx, aOpenscmanagerF; "OpenSCManager failed: 0x%x"
0x180028f0b  mov     ecx, 8; int
0x180028f10  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180028f15  jmp     loc_180028FCE
0x180028f1a  mov     r8d, 24h ; '$'; dwDesiredAccess
0x180028f20  mov     rdx, rbx; lpServiceName
0x180028f23  mov     rcx, rsi; hSCManager
0x180028f26  call    cs:__imp_OpenServiceW
0x180028f2c  mov     rdi, rax
0x180028f2f  test    rax, rax
0x180028f32  jnz     short loc_180028F5F
0x180028f34  call    cs:__imp_GetLastError
0x180028f3a  mov     ebx, eax
0x180028f3c  test    eax, eax
0x180028f3e  jle     short loc_180028F49
0x180028f40  movzx   ebx, ax
0x180028f43  or      ebx, 80070000h
0x180028f49  mov     r8d, ebx
0x180028f4c  lea     rdx, aOpenserviceFai; "OpenService failed: 0x%x"
0x180028f53  mov     ecx, 8; int
0x180028f58  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180028f5d  jmp     short loc_180028FC5
0x180028f5f  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x180028f64  mov     rcx, rdi; hService
0x180028f67  call    cs:__imp_QueryServiceStatus
0x180028f6d  test    eax, eax
0x180028f6f  jz      short loc_180028F78
0x180028f71  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 1
0x180028f76  jz      short loc_180028FBA
0x180028f78  lea     r8, [rsp+58h+ServiceStatus]; lpServiceStatus
0x180028f7d  mov     edx, 1; dwControl
0x180028f82  mov     rcx, rdi; hService
0x180028f85  call    cs:__imp_ControlService
0x180028f8b  test    eax, eax
0x180028f8d  jnz     short loc_180028FBA
0x180028f8f  call    cs:__imp_GetLastError
0x180028f95  mov     ebx, eax
0x180028f97  test    eax, eax
0x180028f99  jle     short loc_180028FA4
0x180028f9b  movzx   ebx, ax
0x180028f9e  or      ebx, 80070000h
0x180028fa4  mov     r8d, ebx
0x180028fa7  lea     rdx, aStopserviceFai; "StopService failed: 0x%x"
0x180028fae  mov     ecx, 8; int
0x180028fb3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180028fb8  jmp     short loc_180028FBC
0x180028fba  xor     ebx, ebx
0x180028fbc  mov     rcx, rdi; hSCObject
0x180028fbf  call    cs:__imp_CloseServiceHandle
0x180028fc5  mov     rcx, rsi; hSCObject
0x180028fc8  call    cs:__imp_CloseServiceHandle
0x180028fce  mov     eax, ebx
0x180028fd0  mov     rcx, [rsp+58h+var_18]
0x180028fd5  xor     rcx, rsp; StackCookie
0x180028fd8  call    __security_check_cookie
0x180028fdd  mov     rbx, [rsp+58h+arg_8]
0x180028fe2  mov     rsi, [rsp+58h+arg_10]
0x180028fe7  add     rsp, 50h
0x180028feb  pop     rdi
0x180028fec  retn
```
