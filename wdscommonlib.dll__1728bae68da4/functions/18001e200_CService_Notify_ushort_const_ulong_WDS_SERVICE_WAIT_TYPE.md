# CService::Notify(ushort const *,ulong,WDS_SERVICE_WAIT_TYPE)

- ea: `0x18001e200`
- end: `0x18001e2be`
- name: `?Notify@CService@@QEAAKPEBGKW4WDS_SERVICE_WAIT_TYPE@@@Z`
- size: `190`
- prototype: `unsigned int __high(const unsigned __int16 *, unsigned int, enum WDS_SERVICE_WAIT_TYPE)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18001e200`
- `0x180030390`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001e258`
- `KERNEL32!GetLastError` at `0x18001e282`
- `KERNEL32!GetLastError` at `0x18001e258`
- `KERNEL32!GetLastError` at `0x18001e282`
- `ADVAPI32!CloseServiceHandle` at `0x18001e293`
- `ADVAPI32!CloseServiceHandle` at `0x18001e293`
- `ADVAPI32!OpenServiceW` at `0x18001e244`
- `ADVAPI32!OpenServiceW` at `0x18001e244`
- `ADVAPI32!ControlService` at `0x18001e272`
- `ADVAPI32!ControlService` at `0x18001e272`

## pseudocode

```c
__int64 __fastcall CService::Notify(SC_HANDLE **a1, const WCHAR *a2, DWORD a3)
{
  SC_HANDLE *v3; // rcx
  DWORD LastError; // ebx
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rdi
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-48h] BYREF

  v3 = *a1;
  LastError = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( a3 - 128 > 0x7F )
  {
    return 87;
  }
  else
  {
    v6 = OpenServiceW(*v3, a2, 0x100u);
    v7 = v6;
    if ( v6 )
    {
      if ( !ControlService(v6, a3, &ServiceStatus) )
        LastError = GetLastError();
      CloseServiceHandle(v7);
    }
    else
    {
      return GetLastError();
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18001e200  push    rbx
0x18001e202  push    rsi
0x18001e203  push    rdi
0x18001e204  sub     rsp, 50h
0x18001e208  mov     rax, cs:__security_cookie
0x18001e20f  xor     rax, rsp
0x18001e212  mov     [rsp+68h+var_28], rax
0x18001e217  mov     rcx, [rcx]
0x18001e21a  xor     eax, eax
0x18001e21c  mov     qword ptr [rsp+68h+ServiceStatus.dwServiceSpecificExitCode], rax
0x18001e221  xor     ebx, ebx
0x18001e223  mov     [rsp+68h+ServiceStatus.dwWaitHint], eax
0x18001e227  xorps   xmm0, xmm0
0x18001e22a  lea     eax, [r8-80h]
0x18001e22e  mov     esi, r8d
0x18001e231  movups  xmmword ptr [rsp+68h+ServiceStatus.dwServiceType], xmm0
0x18001e236  cmp     eax, 7Fh
0x18001e239  ja      short loc_18001E2A1
0x18001e23b  mov     rcx, [rcx]; hSCManager
0x18001e23e  mov     r8d, 100h; dwDesiredAccess
0x18001e244  call    cs:__imp_OpenServiceW
0x18001e24b  nop     dword ptr [rax+rax+00h]
0x18001e250  mov     rdi, rax
0x18001e253  test    rax, rax
0x18001e256  jnz     short loc_18001E268
0x18001e258  call    cs:__imp_GetLastError
0x18001e25f  nop     dword ptr [rax+rax+00h]
0x18001e264  mov     ebx, eax
0x18001e266  jmp     short loc_18001E2A6
0x18001e268  lea     r8, [rsp+68h+ServiceStatus]; lpServiceStatus
0x18001e26d  mov     edx, esi; dwControl
0x18001e26f  mov     rcx, rdi; hService
0x18001e272  call    cs:__imp_ControlService
0x18001e279  nop     dword ptr [rax+rax+00h]
0x18001e27e  test    eax, eax
0x18001e280  jnz     short loc_18001E290
0x18001e282  call    cs:__imp_GetLastError
0x18001e289  nop     dword ptr [rax+rax+00h]
0x18001e28e  mov     ebx, eax
0x18001e290  mov     rcx, rdi; hSCObject
0x18001e293  call    cs:__imp_CloseServiceHandle
0x18001e29a  nop     dword ptr [rax+rax+00h]
0x18001e29f  jmp     short loc_18001E2A6
0x18001e2a1  mov     ebx, 57h ; 'W'
0x18001e2a6  mov     eax, ebx
0x18001e2a8  mov     rcx, [rsp+68h+var_28]
0x18001e2ad  xor     rcx, rsp; StackCookie
0x18001e2b0  call    __security_check_cookie
0x18001e2b5  add     rsp, 50h
0x18001e2b9  pop     rdi
0x18001e2ba  pop     rsi
0x18001e2bb  pop     rbx
0x18001e2bc  retn
```
