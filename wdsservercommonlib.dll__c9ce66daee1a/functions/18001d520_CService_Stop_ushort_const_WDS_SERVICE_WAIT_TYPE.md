# CService::Stop(ushort const *,WDS_SERVICE_WAIT_TYPE)

- ea: `0x18001d520`
- end: `0x18001d617`
- name: `?Stop@CService@@QEAAKPEBGW4WDS_SERVICE_WAIT_TYPE@@@Z`
- size: `247`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18001d520`
- `0x18001d724`
- `0x18002f3e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001d574`
- `KERNEL32!GetLastError` at `0x18001d59c`
- `KERNEL32!GetLastError` at `0x18001d574`
- `KERNEL32!GetLastError` at `0x18001d59c`
- `ADVAPI32!ControlService` at `0x18001d5c5`
- `ADVAPI32!ControlService` at `0x18001d5c5`
- `ADVAPI32!OpenServiceW` at `0x18001d560`
- `ADVAPI32!OpenServiceW` at `0x18001d560`
- `ADVAPI32!QueryServiceStatus` at `0x18001d58c`
- `ADVAPI32!QueryServiceStatus` at `0x18001d58c`
- `ADVAPI32!CloseServiceHandle` at `0x18001d5eb`
- `ADVAPI32!CloseServiceHandle` at `0x18001d5eb`

## pseudocode

```c
__int64 __fastcall CService::Stop(SC_HANDLE **a1, const WCHAR *a2, unsigned int a3)
{
  DWORD v4; // ebx
  SC_HANDLE v5; // rcx
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rdi
  __int64 v8; // rcx
  DWORD LastError; // eax
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  v4 = 0;
  v5 = **a1;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v6 = OpenServiceW(v5, a2, 0x24u);
  v7 = v6;
  if ( v6 )
  {
    if ( !QueryServiceStatus(v6, &ServiceStatus) )
      goto LABEL_4;
    if ( ServiceStatus.dwCurrentState == 1 )
    {
LABEL_10:
      CloseServiceHandle(v7);
      return v4;
    }
    if ( ServiceStatus.dwCurrentState == 3 || ControlService(v7, 1u, &ServiceStatus) )
      LastError = CServiceControlInterface::WaitForService(
                    v8,
                    v7,
                    1,
                    a3,
                    *(_QWORD *)&ServiceStatus.dwServiceType,
                    *(_QWORD *)&ServiceStatus.dwControlsAccepted,
                    *(_QWORD *)&ServiceStatus.dwServiceSpecificExitCode,
                    ServiceStatus.dwWaitHint);
    else
LABEL_4:
      LastError = GetLastError();
    v4 = LastError;
    goto LABEL_10;
  }
  return GetLastError();
}

```

## disassembly

```asm
0x18001d520  mov     [rsp+arg_10], rbx
0x18001d525  mov     [rsp+arg_18], rsi
0x18001d52a  push    rdi
0x18001d52b  sub     rsp, 50h
0x18001d52f  mov     rax, cs:__security_cookie
0x18001d536  xor     rax, rsp
0x18001d539  mov     [rsp+58h+var_18], rax
0x18001d53e  mov     rcx, [rcx]
0x18001d541  xor     eax, eax
0x18001d543  mov     esi, r8d
0x18001d546  mov     qword ptr [rsp+58h+ServiceStatus.dwServiceSpecificExitCode], rax
0x18001d54b  xorps   xmm0, xmm0
0x18001d54e  mov     [rsp+58h+ServiceStatus.dwWaitHint], eax
0x18001d552  xor     ebx, ebx
0x18001d554  mov     rcx, [rcx]; hSCManager
0x18001d557  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x18001d55c  lea     r8d, [rbx+24h]; dwDesiredAccess
0x18001d560  call    cs:__imp_OpenServiceW
0x18001d567  nop     dword ptr [rax+rax+00h]
0x18001d56c  mov     rdi, rax
0x18001d56f  test    rax, rax
0x18001d572  jnz     short loc_18001D584
0x18001d574  call    cs:__imp_GetLastError
0x18001d57b  nop     dword ptr [rax+rax+00h]
0x18001d580  mov     ebx, eax
0x18001d582  jmp     short loc_18001D5F7
0x18001d584  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18001d589  mov     rcx, rdi; hService
0x18001d58c  call    cs:__imp_QueryServiceStatus
0x18001d593  nop     dword ptr [rax+rax+00h]
0x18001d598  test    eax, eax
0x18001d59a  jnz     short loc_18001D5AA
0x18001d59c  call    cs:__imp_GetLastError
0x18001d5a3  nop     dword ptr [rax+rax+00h]
0x18001d5a8  jmp     short loc_18001D5E6
0x18001d5aa  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 1
0x18001d5af  jz      short loc_18001D5E8
0x18001d5b1  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 3
0x18001d5b6  jz      short loc_18001D5D5
0x18001d5b8  lea     r8, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18001d5bd  mov     edx, 1; dwControl
0x18001d5c2  mov     rcx, rdi; hService
0x18001d5c5  call    cs:__imp_ControlService
0x18001d5cc  nop     dword ptr [rax+rax+00h]
0x18001d5d1  test    eax, eax
0x18001d5d3  jz      short loc_18001D59C
0x18001d5d5  mov     r9d, esi
0x18001d5d8  mov     r8d, 1
0x18001d5de  mov     rdx, rdi
0x18001d5e1  call    ?WaitForService@CServiceControlInterface@@AEAAKPEAUSC_HANDLE__@@KW4WDS_SERVICE_WAIT_TYPE@@@Z; CServiceControlInterface::WaitForService(SC_HANDLE__ *,ulong,WDS_SERVICE_WAIT_TYPE)
0x18001d5e6  mov     ebx, eax
0x18001d5e8  mov     rcx, rdi; hSCObject
0x18001d5eb  call    cs:__imp_CloseServiceHandle
0x18001d5f2  nop     dword ptr [rax+rax+00h]
0x18001d5f7  mov     eax, ebx
0x18001d5f9  mov     rcx, [rsp+58h+var_18]
0x18001d5fe  xor     rcx, rsp; StackCookie
0x18001d601  call    __security_check_cookie
0x18001d606  mov     rbx, [rsp+58h+arg_10]
0x18001d60b  mov     rsi, [rsp+58h+arg_18]
0x18001d610  add     rsp, 50h
0x18001d614  pop     rdi
0x18001d615  retn
```
