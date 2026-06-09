# CService::GetCurrentState(ushort const *,ulong *)

- ea: `0x18001e080`
- end: `0x18001e132`
- name: `?GetCurrentState@CService@@QEAAKPEBGPEAK@Z`
- size: `178`
- prototype: `unsigned int __fastcall(CService *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18001e080`
- `0x180030390`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001e0cd`
- `KERNEL32!GetLastError` at `0x18001e0f5`
- `KERNEL32!GetLastError` at `0x18001e0cd`
- `KERNEL32!GetLastError` at `0x18001e0f5`
- `ADVAPI32!CloseServiceHandle` at `0x18001e10e`
- `ADVAPI32!CloseServiceHandle` at `0x18001e10e`
- `ADVAPI32!QueryServiceStatus` at `0x18001e0e5`
- `ADVAPI32!QueryServiceStatus` at `0x18001e0e5`
- `ADVAPI32!OpenServiceW` at `0x18001e0b9`
- `ADVAPI32!OpenServiceW` at `0x18001e0b9`

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
0x18001e080  push    rbx
0x18001e082  push    rsi
0x18001e083  push    rdi
0x18001e084  sub     rsp, 50h
0x18001e088  mov     rax, cs:__security_cookie
0x18001e08f  xor     rax, rsp
0x18001e092  mov     [rsp+68h+var_28], rax
0x18001e097  mov     rcx, [rcx]
0x18001e09a  xor     eax, eax
0x18001e09c  mov     rsi, r8
0x18001e09f  mov     qword ptr [rsp+68h+ServiceStatus.dwServiceSpecificExitCode], rax
0x18001e0a4  xorps   xmm0, xmm0
0x18001e0a7  mov     [rsp+68h+ServiceStatus.dwWaitHint], eax
0x18001e0ab  xor     ebx, ebx
0x18001e0ad  mov     rcx, [rcx]; hSCManager
0x18001e0b0  movups  xmmword ptr [rsp+68h+ServiceStatus.dwServiceType], xmm0
0x18001e0b5  lea     r8d, [rbx+4]; dwDesiredAccess
0x18001e0b9  call    cs:__imp_OpenServiceW
0x18001e0c0  nop     dword ptr [rax+rax+00h]
0x18001e0c5  mov     rdi, rax
0x18001e0c8  test    rax, rax
0x18001e0cb  jnz     short loc_18001E0DD
0x18001e0cd  call    cs:__imp_GetLastError
0x18001e0d4  nop     dword ptr [rax+rax+00h]
0x18001e0d9  mov     ebx, eax
0x18001e0db  jmp     short loc_18001E11A
0x18001e0dd  lea     rdx, [rsp+68h+ServiceStatus]; lpServiceStatus
0x18001e0e2  mov     rcx, rdi; hService
0x18001e0e5  call    cs:__imp_QueryServiceStatus
0x18001e0ec  nop     dword ptr [rax+rax+00h]
0x18001e0f1  test    eax, eax
0x18001e0f3  jnz     short loc_18001E105
0x18001e0f5  call    cs:__imp_GetLastError
0x18001e0fc  nop     dword ptr [rax+rax+00h]
0x18001e101  mov     ebx, eax
0x18001e103  jmp     short loc_18001E10B
0x18001e105  mov     eax, [rsp+68h+ServiceStatus.dwCurrentState]
0x18001e109  mov     [rsi], eax
0x18001e10b  mov     rcx, rdi; hSCObject
0x18001e10e  call    cs:__imp_CloseServiceHandle
0x18001e115  nop     dword ptr [rax+rax+00h]
0x18001e11a  mov     eax, ebx
0x18001e11c  mov     rcx, [rsp+68h+var_28]
0x18001e121  xor     rcx, rsp; StackCookie
0x18001e124  call    __security_check_cookie
0x18001e129  add     rsp, 50h
0x18001e12d  pop     rdi
0x18001e12e  pop     rsi
0x18001e12f  pop     rbx
0x18001e130  retn
```
