# CService::Notify(ushort const *,ulong,WDS_SERVICE_WAIT_TYPE)

- ea: `0x18001d290`
- end: `0x18001d34e`
- name: `?Notify@CService@@QEAAKPEBGKW4WDS_SERVICE_WAIT_TYPE@@@Z`
- size: `190`
- prototype: `unsigned int __high(const unsigned __int16 *, unsigned int, enum WDS_SERVICE_WAIT_TYPE)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18001d290`
- `0x18002f3e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001d2e8`
- `KERNEL32!GetLastError` at `0x18001d312`
- `KERNEL32!GetLastError` at `0x18001d2e8`
- `KERNEL32!GetLastError` at `0x18001d312`
- `ADVAPI32!ControlService` at `0x18001d302`
- `ADVAPI32!ControlService` at `0x18001d302`
- `ADVAPI32!OpenServiceW` at `0x18001d2d4`
- `ADVAPI32!OpenServiceW` at `0x18001d2d4`
- `ADVAPI32!CloseServiceHandle` at `0x18001d323`
- `ADVAPI32!CloseServiceHandle` at `0x18001d323`

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
0x18001d290  push    rbx
0x18001d292  push    rsi
0x18001d293  push    rdi
0x18001d294  sub     rsp, 50h
0x18001d298  mov     rax, cs:__security_cookie
0x18001d29f  xor     rax, rsp
0x18001d2a2  mov     [rsp+68h+var_28], rax
0x18001d2a7  mov     rcx, [rcx]
0x18001d2aa  xor     eax, eax
0x18001d2ac  mov     qword ptr [rsp+68h+ServiceStatus.dwServiceSpecificExitCode], rax
0x18001d2b1  xor     ebx, ebx
0x18001d2b3  mov     [rsp+68h+ServiceStatus.dwWaitHint], eax
0x18001d2b7  xorps   xmm0, xmm0
0x18001d2ba  lea     eax, [r8-80h]
0x18001d2be  mov     esi, r8d
0x18001d2c1  movups  xmmword ptr [rsp+68h+ServiceStatus.dwServiceType], xmm0
0x18001d2c6  cmp     eax, 7Fh
0x18001d2c9  ja      short loc_18001D331
0x18001d2cb  mov     rcx, [rcx]; hSCManager
0x18001d2ce  mov     r8d, 100h; dwDesiredAccess
0x18001d2d4  call    cs:__imp_OpenServiceW
0x18001d2db  nop     dword ptr [rax+rax+00h]
0x18001d2e0  mov     rdi, rax
0x18001d2e3  test    rax, rax
0x18001d2e6  jnz     short loc_18001D2F8
0x18001d2e8  call    cs:__imp_GetLastError
0x18001d2ef  nop     dword ptr [rax+rax+00h]
0x18001d2f4  mov     ebx, eax
0x18001d2f6  jmp     short loc_18001D336
0x18001d2f8  lea     r8, [rsp+68h+ServiceStatus]; lpServiceStatus
0x18001d2fd  mov     edx, esi; dwControl
0x18001d2ff  mov     rcx, rdi; hService
0x18001d302  call    cs:__imp_ControlService
0x18001d309  nop     dword ptr [rax+rax+00h]
0x18001d30e  test    eax, eax
0x18001d310  jnz     short loc_18001D320
0x18001d312  call    cs:__imp_GetLastError
0x18001d319  nop     dword ptr [rax+rax+00h]
0x18001d31e  mov     ebx, eax
0x18001d320  mov     rcx, rdi; hSCObject
0x18001d323  call    cs:__imp_CloseServiceHandle
0x18001d32a  nop     dword ptr [rax+rax+00h]
0x18001d32f  jmp     short loc_18001D336
0x18001d331  mov     ebx, 57h ; 'W'
0x18001d336  mov     eax, ebx
0x18001d338  mov     rcx, [rsp+68h+var_28]
0x18001d33d  xor     rcx, rsp; StackCookie
0x18001d340  call    __security_check_cookie
0x18001d345  add     rsp, 50h
0x18001d349  pop     rdi
0x18001d34a  pop     rsi
0x18001d34b  pop     rbx
0x18001d34c  retn
```
