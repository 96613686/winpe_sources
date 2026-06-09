# CService::Suspend(ushort const *,WDS_SERVICE_WAIT_TYPE)

- ea: `0x18001d620`
- end: `0x18001d71e`
- name: `?Suspend@CService@@QEAAKPEBGW4WDS_SERVICE_WAIT_TYPE@@@Z`
- size: `254`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18001d620`
- `0x18001d724`
- `0x18002f3e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001d674`
- `KERNEL32!GetLastError` at `0x18001d69c`
- `KERNEL32!GetLastError` at `0x18001d674`
- `KERNEL32!GetLastError` at `0x18001d69c`
- `ADVAPI32!ControlService` at `0x18001d6cc`
- `ADVAPI32!ControlService` at `0x18001d6cc`
- `ADVAPI32!OpenServiceW` at `0x18001d660`
- `ADVAPI32!OpenServiceW` at `0x18001d660`
- `ADVAPI32!QueryServiceStatus` at `0x18001d68c`
- `ADVAPI32!QueryServiceStatus` at `0x18001d68c`
- `ADVAPI32!CloseServiceHandle` at `0x18001d6f2`
- `ADVAPI32!CloseServiceHandle` at `0x18001d6f2`

## pseudocode

```c
__int64 __fastcall CService::Suspend(SC_HANDLE **a1, const WCHAR *a2, unsigned int a3)
{
  unsigned int v4; // ebx
  SC_HANDLE v5; // rcx
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rdi
  DWORD LastError; // eax
  __int64 v9; // rcx
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  v4 = 0;
  v5 = **a1;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v6 = OpenServiceW(v5, a2, 0x44u);
  v7 = v6;
  if ( v6 )
  {
    if ( !QueryServiceStatus(v6, &ServiceStatus) )
      goto LABEL_4;
    if ( ServiceStatus.dwCurrentState != 7 )
    {
      if ( ServiceStatus.dwCurrentState == 4 )
      {
        if ( ControlService(v7, 2u, &ServiceStatus) )
        {
          LastError = CServiceControlInterface::WaitForService(
                        v9,
                        v7,
                        7,
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
0x18001d620  mov     [rsp+arg_10], rbx
0x18001d625  mov     [rsp+arg_18], rsi
0x18001d62a  push    rdi
0x18001d62b  sub     rsp, 50h
0x18001d62f  mov     rax, cs:__security_cookie
0x18001d636  xor     rax, rsp
0x18001d639  mov     [rsp+58h+var_18], rax
0x18001d63e  mov     rcx, [rcx]
0x18001d641  xor     eax, eax
0x18001d643  mov     esi, r8d
0x18001d646  mov     qword ptr [rsp+58h+ServiceStatus.dwServiceSpecificExitCode], rax
0x18001d64b  xorps   xmm0, xmm0
0x18001d64e  mov     [rsp+58h+ServiceStatus.dwWaitHint], eax
0x18001d652  xor     ebx, ebx
0x18001d654  mov     rcx, [rcx]; hSCManager
0x18001d657  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x18001d65c  lea     r8d, [rbx+44h]; dwDesiredAccess
0x18001d660  call    cs:__imp_OpenServiceW
0x18001d667  nop     dword ptr [rax+rax+00h]
0x18001d66c  mov     rdi, rax
0x18001d66f  test    rax, rax
0x18001d672  jnz     short loc_18001D684
0x18001d674  call    cs:__imp_GetLastError
0x18001d67b  nop     dword ptr [rax+rax+00h]
0x18001d680  mov     ebx, eax
0x18001d682  jmp     short loc_18001D6FE
0x18001d684  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18001d689  mov     rcx, rdi; hService
0x18001d68c  call    cs:__imp_QueryServiceStatus
0x18001d693  nop     dword ptr [rax+rax+00h]
0x18001d698  test    eax, eax
0x18001d69a  jnz     short loc_18001D6AA
0x18001d69c  call    cs:__imp_GetLastError
0x18001d6a3  nop     dword ptr [rax+rax+00h]
0x18001d6a8  jmp     short loc_18001D6ED
0x18001d6aa  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 7
0x18001d6af  jz      short loc_18001D6EF
0x18001d6b1  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 4
0x18001d6b6  jz      short loc_18001D6BF
0x18001d6b8  mov     ebx, 426h
0x18001d6bd  jmp     short loc_18001D6EF
0x18001d6bf  lea     r8, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18001d6c4  mov     edx, 2; dwControl
0x18001d6c9  mov     rcx, rdi; hService
0x18001d6cc  call    cs:__imp_ControlService
0x18001d6d3  nop     dword ptr [rax+rax+00h]
0x18001d6d8  test    eax, eax
0x18001d6da  jz      short loc_18001D69C
0x18001d6dc  mov     r9d, esi
0x18001d6df  mov     r8d, 7
0x18001d6e5  mov     rdx, rdi
0x18001d6e8  call    ?WaitForService@CServiceControlInterface@@AEAAKPEAUSC_HANDLE__@@KW4WDS_SERVICE_WAIT_TYPE@@@Z; CServiceControlInterface::WaitForService(SC_HANDLE__ *,ulong,WDS_SERVICE_WAIT_TYPE)
0x18001d6ed  mov     ebx, eax
0x18001d6ef  mov     rcx, rdi; hSCObject
0x18001d6f2  call    cs:__imp_CloseServiceHandle
0x18001d6f9  nop     dword ptr [rax+rax+00h]
0x18001d6fe  mov     eax, ebx
0x18001d700  mov     rcx, [rsp+58h+var_18]
0x18001d705  xor     rcx, rsp; StackCookie
0x18001d708  call    __security_check_cookie
0x18001d70d  mov     rbx, [rsp+58h+arg_10]
0x18001d712  mov     rsi, [rsp+58h+arg_18]
0x18001d717  add     rsp, 50h
0x18001d71b  pop     rdi
0x18001d71c  retn
```
