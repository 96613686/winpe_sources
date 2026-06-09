# WlanSendServiceControlMessage(ulong,ushort const *)

- ea: `0x1800261d8`
- end: `0x18002629b`
- name: `?WlanSendServiceControlMessage@@YAKKPEBG@Z`
- size: `195`
- prototype: `unsigned int __fastcall(unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800285d0`

## callees

- `0x180019a20`
- `0x1800261d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002621b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026241`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026262`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002621b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026241`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026262`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002626d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180026276`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002626d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180026276`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002620d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002620d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180026233`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180026233`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180026258`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180026258`

## string_xrefs

- `0x180026229`: `Dnscache`

## pseudocode

```c
DWORD __fastcall WlanSendServiceControlMessage(__int64 a1, const unsigned __int16 *a2)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rsi
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rdi
  DWORD LastError; // ebx
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v2 = OpenSCManagerW(0, 0, 0x80000000);
  v3 = v2;
  if ( !v2 )
    return GetLastError();
  v5 = OpenServiceW(v2, L"Dnscache", 0x40u);
  v6 = v5;
  if ( v5 )
  {
    LastError = 0;
    if ( !ControlService(v5, 6u, &ServiceStatus) )
      LastError = GetLastError();
    CloseServiceHandle(v6);
  }
  else
  {
    LastError = GetLastError();
  }
  CloseServiceHandle(v3);
  return LastError;
}

```

## disassembly

```asm
0x1800261d8  mov     [rsp+arg_0], rbx
0x1800261dd  mov     [rsp+arg_8], rsi
0x1800261e2  push    rdi
0x1800261e3  sub     rsp, 50h
0x1800261e7  mov     rax, cs:__security_cookie
0x1800261ee  xor     rax, rsp
0x1800261f1  mov     [rsp+58h+var_18], rax
0x1800261f6  xorps   xmm0, xmm0
0x1800261f9  xor     edx, edx; lpDatabaseName
0x1800261fb  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x180026200  xor     ecx, ecx; lpMachineName
0x180026202  mov     r8d, 80000000h; dwDesiredAccess
0x180026208  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x18002620d  call    cs:__imp_OpenSCManagerW
0x180026213  mov     rsi, rax
0x180026216  test    rax, rax
0x180026219  jnz     short loc_180026223
0x18002621b  call    cs:__imp_GetLastError
0x180026221  jmp     short loc_18002627E
0x180026223  mov     r8d, 40h ; '@'; dwDesiredAccess
0x180026229  lea     rdx, ServiceName; "Dnscache"
0x180026230  mov     rcx, rsi; hSCManager
0x180026233  call    cs:__imp_OpenServiceW
0x180026239  mov     rdi, rax
0x18002623c  test    rax, rax
0x18002623f  jnz     short loc_18002624B
0x180026241  call    cs:__imp_GetLastError
0x180026247  mov     ebx, eax
0x180026249  jmp     short loc_180026273
0x18002624b  xor     ebx, ebx
0x18002624d  lea     r8, [rsp+58h+ServiceStatus]; lpServiceStatus
0x180026252  mov     rcx, rdi; hService
0x180026255  lea     edx, [rbx+6]; dwControl
0x180026258  call    cs:__imp_ControlService
0x18002625e  test    eax, eax
0x180026260  jnz     short loc_18002626A
0x180026262  call    cs:__imp_GetLastError
0x180026268  mov     ebx, eax
0x18002626a  mov     rcx, rdi; hSCObject
0x18002626d  call    cs:__imp_CloseServiceHandle
0x180026273  mov     rcx, rsi; hSCObject
0x180026276  call    cs:__imp_CloseServiceHandle
0x18002627c  mov     eax, ebx
0x18002627e  mov     rcx, [rsp+58h+var_18]
0x180026283  xor     rcx, rsp; StackCookie
0x180026286  call    __security_check_cookie
0x18002628b  mov     rbx, [rsp+58h+arg_0]
0x180026290  mov     rsi, [rsp+58h+arg_8]
0x180026295  add     rsp, 50h
0x180026299  pop     rdi
0x18002629a  retn
```
