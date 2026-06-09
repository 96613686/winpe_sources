# CService::Continue(ushort const *,WDS_SERVICE_WAIT_TYPE)

- ea: `0x18001ce00`
- end: `0x18001cefe`
- name: `?Continue@CService@@QEAAKPEBGW4WDS_SERVICE_WAIT_TYPE@@@Z`
- size: `254`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18001ce00`
- `0x18001d724`
- `0x18002f3e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001ce54`
- `KERNEL32!GetLastError` at `0x18001ce7c`
- `KERNEL32!GetLastError` at `0x18001ce54`
- `KERNEL32!GetLastError` at `0x18001ce7c`
- `ADVAPI32!ControlService` at `0x18001ceac`
- `ADVAPI32!ControlService` at `0x18001ceac`
- `ADVAPI32!OpenServiceW` at `0x18001ce40`
- `ADVAPI32!OpenServiceW` at `0x18001ce40`
- `ADVAPI32!QueryServiceStatus` at `0x18001ce6c`
- `ADVAPI32!QueryServiceStatus` at `0x18001ce6c`
- `ADVAPI32!CloseServiceHandle` at `0x18001ced2`
- `ADVAPI32!CloseServiceHandle` at `0x18001ced2`

## pseudocode

```c
__int64 __fastcall CService::Continue(SC_HANDLE **a1, const WCHAR *a2, unsigned int a3)
{
  unsigned int v4; // ebx
  SC_HANDLE v5; // rcx
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rdi
  DWORD LastError; // eax
  __int64 v9; // rcx
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  v4 = 0;
  v5 = **a1;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v6 = OpenServiceW(v5, a2, 0x44u);
  v7 = v6;
  if ( v6 )
  {
    if ( !QueryServiceStatus(v6, &ServiceStatus) )
      goto LABEL_4;
    if ( ServiceStatus.dwCurrentState != 4 )
    {
      if ( ServiceStatus.dwCurrentState == 7 )
      {
        if ( ControlService(v7, 3u, &ServiceStatus) )
        {
          LastError = CServiceControlInterface::WaitForService(
                        v9,
                        v7,
                        4,
                        a3,
                        *(_QWORD *)&ServiceStatus.dwServiceType,
                        *(_QWORD *)&ServiceStatus.dwControlsAccepted,
                        *(_QWORD *)&ServiceStatus.dwServiceSpecificExitCode,
                        ServiceStatus.dwWaitHint);
          goto LABEL_10;
        }
LABEL_4:
        LastError = GetLastError();
LABEL_10:
        v4 = LastError;
        goto LABEL_11;
      }
      v4 = 1062;
    }
LABEL_11:
    CloseServiceHandle(v7);
    return v4;
  }
  return GetLastError();
}

```

## disassembly

```asm
0x18001ce00  mov     [rsp+arg_10], rbx
0x18001ce05  mov     [rsp+arg_18], rsi
0x18001ce0a  push    rdi
0x18001ce0b  sub     rsp, 50h
0x18001ce0f  mov     rax, cs:__security_cookie
0x18001ce16  xor     rax, rsp
0x18001ce19  mov     [rsp+58h+var_18], rax
0x18001ce1e  mov     rcx, [rcx]
0x18001ce21  xor     eax, eax
0x18001ce23  mov     esi, r8d
0x18001ce26  mov     qword ptr [rsp+58h+ServiceStatus.dwServiceSpecificExitCode], rax
0x18001ce2b  xorps   xmm0, xmm0
0x18001ce2e  mov     [rsp+58h+ServiceStatus.dwWaitHint], eax
0x18001ce32  xor     ebx, ebx
0x18001ce34  mov     rcx, [rcx]; hSCManager
0x18001ce37  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x18001ce3c  lea     r8d, [rbx+44h]; dwDesiredAccess
0x18001ce40  call    cs:__imp_OpenServiceW
0x18001ce47  nop     dword ptr [rax+rax+00h]
0x18001ce4c  mov     rdi, rax
0x18001ce4f  test    rax, rax
0x18001ce52  jnz     short loc_18001CE64
0x18001ce54  call    cs:__imp_GetLastError
0x18001ce5b  nop     dword ptr [rax+rax+00h]
0x18001ce60  mov     ebx, eax
0x18001ce62  jmp     short loc_18001CEDE
0x18001ce64  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18001ce69  mov     rcx, rdi; hService
0x18001ce6c  call    cs:__imp_QueryServiceStatus
0x18001ce73  nop     dword ptr [rax+rax+00h]
0x18001ce78  test    eax, eax
0x18001ce7a  jnz     short loc_18001CE8A
0x18001ce7c  call    cs:__imp_GetLastError
0x18001ce83  nop     dword ptr [rax+rax+00h]
0x18001ce88  jmp     short loc_18001CECD
0x18001ce8a  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 4
0x18001ce8f  jz      short loc_18001CECF
0x18001ce91  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 7
0x18001ce96  jz      short loc_18001CE9F
0x18001ce98  mov     ebx, 426h
0x18001ce9d  jmp     short loc_18001CECF
0x18001ce9f  lea     r8, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18001cea4  mov     edx, 3; dwControl
0x18001cea9  mov     rcx, rdi; hService
0x18001ceac  call    cs:__imp_ControlService
0x18001ceb3  nop     dword ptr [rax+rax+00h]
0x18001ceb8  test    eax, eax
0x18001ceba  jz      short loc_18001CE7C
0x18001cebc  mov     r9d, esi
0x18001cebf  mov     r8d, 4
0x18001cec5  mov     rdx, rdi
0x18001cec8  call    ?WaitForService@CServiceControlInterface@@AEAAKPEAUSC_HANDLE__@@KW4WDS_SERVICE_WAIT_TYPE@@@Z; CServiceControlInterface::WaitForService(SC_HANDLE__ *,ulong,WDS_SERVICE_WAIT_TYPE)
0x18001cecd  mov     ebx, eax
0x18001cecf  mov     rcx, rdi; hSCObject
0x18001ced2  call    cs:__imp_CloseServiceHandle
0x18001ced9  nop     dword ptr [rax+rax+00h]
0x18001cede  mov     eax, ebx
0x18001cee0  mov     rcx, [rsp+58h+var_18]
0x18001cee5  xor     rcx, rsp; StackCookie
0x18001cee8  call    __security_check_cookie
0x18001ceed  mov     rbx, [rsp+58h+arg_10]
0x18001cef2  mov     rsi, [rsp+58h+arg_18]
0x18001cef7  add     rsp, 50h
0x18001cefb  pop     rdi
0x18001cefc  retn
```
