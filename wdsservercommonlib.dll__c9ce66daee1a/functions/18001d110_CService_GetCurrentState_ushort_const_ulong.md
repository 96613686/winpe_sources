# CService::GetCurrentState(ushort const *,ulong *)

- ea: `0x18001d110`
- end: `0x18001d1c2`
- name: `?GetCurrentState@CService@@QEAAKPEBGPEAK@Z`
- size: `178`
- prototype: `unsigned int __fastcall(CService *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18001d110`
- `0x18002f3e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001d15d`
- `KERNEL32!GetLastError` at `0x18001d185`
- `KERNEL32!GetLastError` at `0x18001d15d`
- `KERNEL32!GetLastError` at `0x18001d185`
- `ADVAPI32!OpenServiceW` at `0x18001d149`
- `ADVAPI32!OpenServiceW` at `0x18001d149`
- `ADVAPI32!QueryServiceStatus` at `0x18001d175`
- `ADVAPI32!QueryServiceStatus` at `0x18001d175`
- `ADVAPI32!CloseServiceHandle` at `0x18001d19e`
- `ADVAPI32!CloseServiceHandle` at `0x18001d19e`

## pseudocode

```c
__int64 __fastcall CService::GetCurrentState(SC_HANDLE **this, const unsigned __int16 *a2, unsigned int *a3)
{
  DWORD LastError; // ebx
  SC_HANDLE v5; // rcx
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rdi
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-48h] BYREF

  LastError = 0;
  v5 = **this;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v6 = OpenServiceW(v5, a2, 4u);
  v7 = v6;
  if ( v6 )
  {
    if ( QueryServiceStatus(v6, &ServiceStatus) )
      *a3 = ServiceStatus.dwCurrentState;
    else
      LastError = GetLastError();
    CloseServiceHandle(v7);
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
0x18001d110  push    rbx
0x18001d112  push    rsi
0x18001d113  push    rdi
0x18001d114  sub     rsp, 50h
0x18001d118  mov     rax, cs:__security_cookie
0x18001d11f  xor     rax, rsp
0x18001d122  mov     [rsp+68h+var_28], rax
0x18001d127  mov     rcx, [rcx]
0x18001d12a  xor     eax, eax
0x18001d12c  mov     rsi, r8
0x18001d12f  mov     qword ptr [rsp+68h+ServiceStatus.dwServiceSpecificExitCode], rax
0x18001d134  xorps   xmm0, xmm0
0x18001d137  mov     [rsp+68h+ServiceStatus.dwWaitHint], eax
0x18001d13b  xor     ebx, ebx
0x18001d13d  mov     rcx, [rcx]; hSCManager
0x18001d140  movups  xmmword ptr [rsp+68h+ServiceStatus.dwServiceType], xmm0
0x18001d145  lea     r8d, [rbx+4]; dwDesiredAccess
0x18001d149  call    cs:__imp_OpenServiceW
0x18001d150  nop     dword ptr [rax+rax+00h]
0x18001d155  mov     rdi, rax
0x18001d158  test    rax, rax
0x18001d15b  jnz     short loc_18001D16D
0x18001d15d  call    cs:__imp_GetLastError
0x18001d164  nop     dword ptr [rax+rax+00h]
0x18001d169  mov     ebx, eax
0x18001d16b  jmp     short loc_18001D1AA
0x18001d16d  lea     rdx, [rsp+68h+ServiceStatus]; lpServiceStatus
0x18001d172  mov     rcx, rdi; hService
0x18001d175  call    cs:__imp_QueryServiceStatus
0x18001d17c  nop     dword ptr [rax+rax+00h]
0x18001d181  test    eax, eax
0x18001d183  jnz     short loc_18001D195
0x18001d185  call    cs:__imp_GetLastError
0x18001d18c  nop     dword ptr [rax+rax+00h]
0x18001d191  mov     ebx, eax
0x18001d193  jmp     short loc_18001D19B
0x18001d195  mov     eax, [rsp+68h+ServiceStatus.dwCurrentState]
0x18001d199  mov     [rsi], eax
0x18001d19b  mov     rcx, rdi; hSCObject
0x18001d19e  call    cs:__imp_CloseServiceHandle
0x18001d1a5  nop     dword ptr [rax+rax+00h]
0x18001d1aa  mov     eax, ebx
0x18001d1ac  mov     rcx, [rsp+68h+var_28]
0x18001d1b1  xor     rcx, rsp; StackCookie
0x18001d1b4  call    __security_check_cookie
0x18001d1b9  add     rsp, 50h
0x18001d1bd  pop     rdi
0x18001d1be  pop     rsi
0x18001d1bf  pop     rbx
0x18001d1c0  retn
```
