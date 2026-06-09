# CUtils::StopService(ushort const *,ulong)

- ea: `0x18002a4c8`
- end: `0x18002a644`
- name: `?StopService@CUtils@@SAJPEBGK@Z`
- size: `380`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18004e8e8`

## callees

- `0x180009940`
- `0x18002a4c8`
- `0x180033f60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a512`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a566`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a5d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a512`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a566`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a5d3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002a609`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002a618`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002a609`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002a618`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002a4fe`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002a4fe`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002a552`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002a552`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18002a5c3`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18002a5c3`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002a59f`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002a59f`

## string_xrefs

- `0x18002a584`: `OpenService failed: 0x%x`
- `0x18002a5f1`: `StopService failed: 0x%x`
- `0x18002a530`: `OpenSCManager failed: 0x%x`

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
0x18002a4c8  mov     [rsp+arg_8], rbx
0x18002a4cd  mov     [rsp+arg_10], rsi
0x18002a4d2  push    rdi
0x18002a4d3  sub     rsp, 50h
0x18002a4d7  mov     rax, cs:__security_cookie
0x18002a4de  xor     rax, rsp
0x18002a4e1  mov     [rsp+58h+var_18], rax
0x18002a4e6  xorps   xmm0, xmm0
0x18002a4e9  xor     edx, edx; lpDatabaseName
0x18002a4eb  mov     rbx, rcx
0x18002a4ee  xor     ecx, ecx; lpMachineName
0x18002a4f0  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x18002a4f5  lea     r8d, [rdx+1]; dwDesiredAccess
0x18002a4f9  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x18002a4fe  call    cs:__imp_OpenSCManagerW
0x18002a505  nop     dword ptr [rax+rax+00h]
0x18002a50a  mov     rsi, rax
0x18002a50d  test    rax, rax
0x18002a510  jnz     short loc_18002A546
0x18002a512  call    cs:__imp_GetLastError
0x18002a519  nop     dword ptr [rax+rax+00h]
0x18002a51e  mov     ebx, eax
0x18002a520  test    eax, eax
0x18002a522  jle     short loc_18002A52D
0x18002a524  movzx   ebx, ax
0x18002a527  or      ebx, 80070000h
0x18002a52d  mov     r8d, ebx
0x18002a530  lea     rdx, aOpenscmanagerF; "OpenSCManager failed: 0x%x"
0x18002a537  mov     ecx, 8; int
0x18002a53c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002a541  jmp     loc_18002A624
0x18002a546  mov     r8d, 24h ; '$'; dwDesiredAccess
0x18002a54c  mov     rdx, rbx; lpServiceName
0x18002a54f  mov     rcx, rsi; hSCManager
0x18002a552  call    cs:__imp_OpenServiceW
0x18002a559  nop     dword ptr [rax+rax+00h]
0x18002a55e  mov     rdi, rax
0x18002a561  test    rax, rax
0x18002a564  jnz     short loc_18002A597
0x18002a566  call    cs:__imp_GetLastError
0x18002a56d  nop     dword ptr [rax+rax+00h]
0x18002a572  mov     ebx, eax
0x18002a574  test    eax, eax
0x18002a576  jle     short loc_18002A581
0x18002a578  movzx   ebx, ax
0x18002a57b  or      ebx, 80070000h
0x18002a581  mov     r8d, ebx
0x18002a584  lea     rdx, aOpenserviceFai; "OpenService failed: 0x%x"
0x18002a58b  mov     ecx, 8; int
0x18002a590  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002a595  jmp     short loc_18002A615
0x18002a597  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18002a59c  mov     rcx, rdi; hService
0x18002a59f  call    cs:__imp_QueryServiceStatus
0x18002a5a6  nop     dword ptr [rax+rax+00h]
0x18002a5ab  test    eax, eax
0x18002a5ad  jz      short loc_18002A5B6
0x18002a5af  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 1
0x18002a5b4  jz      short loc_18002A604
0x18002a5b6  lea     r8, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18002a5bb  mov     edx, 1; dwControl
0x18002a5c0  mov     rcx, rdi; hService
0x18002a5c3  call    cs:__imp_ControlService
0x18002a5ca  nop     dword ptr [rax+rax+00h]
0x18002a5cf  test    eax, eax
0x18002a5d1  jnz     short loc_18002A604
0x18002a5d3  call    cs:__imp_GetLastError
0x18002a5da  nop     dword ptr [rax+rax+00h]
0x18002a5df  mov     ebx, eax
0x18002a5e1  test    eax, eax
0x18002a5e3  jle     short loc_18002A5EE
0x18002a5e5  movzx   ebx, ax
0x18002a5e8  or      ebx, 80070000h
0x18002a5ee  mov     r8d, ebx
0x18002a5f1  lea     rdx, aStopserviceFai; "StopService failed: 0x%x"
0x18002a5f8  mov     ecx, 8; int
0x18002a5fd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002a602  jmp     short loc_18002A606
0x18002a604  xor     ebx, ebx
0x18002a606  mov     rcx, rdi; hSCObject
0x18002a609  call    cs:__imp_CloseServiceHandle
0x18002a610  nop     dword ptr [rax+rax+00h]
0x18002a615  mov     rcx, rsi; hSCObject
0x18002a618  call    cs:__imp_CloseServiceHandle
0x18002a61f  nop     dword ptr [rax+rax+00h]
0x18002a624  mov     eax, ebx
0x18002a626  mov     rcx, [rsp+58h+var_18]
0x18002a62b  xor     rcx, rsp; StackCookie
0x18002a62e  call    __security_check_cookie
0x18002a633  mov     rbx, [rsp+58h+arg_8]
0x18002a638  mov     rsi, [rsp+58h+arg_10]
0x18002a63d  add     rsp, 50h
0x18002a641  pop     rdi
0x18002a642  retn
```
