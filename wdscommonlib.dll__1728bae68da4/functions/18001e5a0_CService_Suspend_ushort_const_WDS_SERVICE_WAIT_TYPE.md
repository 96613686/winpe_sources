# CService::Suspend(ushort const *,WDS_SERVICE_WAIT_TYPE)

- ea: `0x18001e5a0`
- end: `0x18001e69e`
- name: `?Suspend@CService@@QEAAKPEBGW4WDS_SERVICE_WAIT_TYPE@@@Z`
- size: `254`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18001e5a0`
- `0x18001e6a4`
- `0x180030390`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001e5f4`
- `KERNEL32!GetLastError` at `0x18001e61c`
- `KERNEL32!GetLastError` at `0x18001e5f4`
- `KERNEL32!GetLastError` at `0x18001e61c`
- `ADVAPI32!CloseServiceHandle` at `0x18001e672`
- `ADVAPI32!CloseServiceHandle` at `0x18001e672`
- `ADVAPI32!QueryServiceStatus` at `0x18001e60c`
- `ADVAPI32!QueryServiceStatus` at `0x18001e60c`
- `ADVAPI32!OpenServiceW` at `0x18001e5e0`
- `ADVAPI32!OpenServiceW` at `0x18001e5e0`
- `ADVAPI32!ControlService` at `0x18001e64c`
- `ADVAPI32!ControlService` at `0x18001e64c`

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
0x18001e5a0  mov     [rsp+arg_10], rbx
0x18001e5a5  mov     [rsp+arg_18], rsi
0x18001e5aa  push    rdi
0x18001e5ab  sub     rsp, 50h
0x18001e5af  mov     rax, cs:__security_cookie
0x18001e5b6  xor     rax, rsp
0x18001e5b9  mov     [rsp+58h+var_18], rax
0x18001e5be  mov     rcx, [rcx]
0x18001e5c1  xor     eax, eax
0x18001e5c3  mov     esi, r8d
0x18001e5c6  mov     qword ptr [rsp+58h+ServiceStatus.dwServiceSpecificExitCode], rax
0x18001e5cb  xorps   xmm0, xmm0
0x18001e5ce  mov     [rsp+58h+ServiceStatus.dwWaitHint], eax
0x18001e5d2  xor     ebx, ebx
0x18001e5d4  mov     rcx, [rcx]; hSCManager
0x18001e5d7  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x18001e5dc  lea     r8d, [rbx+44h]; dwDesiredAccess
0x18001e5e0  call    cs:__imp_OpenServiceW
0x18001e5e7  nop     dword ptr [rax+rax+00h]
0x18001e5ec  mov     rdi, rax
0x18001e5ef  test    rax, rax
0x18001e5f2  jnz     short loc_18001E604
0x18001e5f4  call    cs:__imp_GetLastError
0x18001e5fb  nop     dword ptr [rax+rax+00h]
0x18001e600  mov     ebx, eax
0x18001e602  jmp     short loc_18001E67E
0x18001e604  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18001e609  mov     rcx, rdi; hService
0x18001e60c  call    cs:__imp_QueryServiceStatus
0x18001e613  nop     dword ptr [rax+rax+00h]
0x18001e618  test    eax, eax
0x18001e61a  jnz     short loc_18001E62A
0x18001e61c  call    cs:__imp_GetLastError
0x18001e623  nop     dword ptr [rax+rax+00h]
0x18001e628  jmp     short loc_18001E66D
0x18001e62a  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 7
0x18001e62f  jz      short loc_18001E66F
0x18001e631  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 4
0x18001e636  jz      short loc_18001E63F
0x18001e638  mov     ebx, 426h
0x18001e63d  jmp     short loc_18001E66F
0x18001e63f  lea     r8, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18001e644  mov     edx, 2; dwControl
0x18001e649  mov     rcx, rdi; hService
0x18001e64c  call    cs:__imp_ControlService
0x18001e653  nop     dword ptr [rax+rax+00h]
0x18001e658  test    eax, eax
0x18001e65a  jz      short loc_18001E61C
0x18001e65c  mov     r9d, esi
0x18001e65f  mov     r8d, 7
0x18001e665  mov     rdx, rdi
0x18001e668  call    ?WaitForService@CServiceControlInterface@@AEAAKPEAUSC_HANDLE__@@KW4WDS_SERVICE_WAIT_TYPE@@@Z; CServiceControlInterface::WaitForService(SC_HANDLE__ *,ulong,WDS_SERVICE_WAIT_TYPE)
0x18001e66d  mov     ebx, eax
0x18001e66f  mov     rcx, rdi; hSCObject
0x18001e672  call    cs:__imp_CloseServiceHandle
0x18001e679  nop     dword ptr [rax+rax+00h]
0x18001e67e  mov     eax, ebx
0x18001e680  mov     rcx, [rsp+58h+var_18]
0x18001e685  xor     rcx, rsp; StackCookie
0x18001e688  call    __security_check_cookie
0x18001e68d  mov     rbx, [rsp+58h+arg_10]
0x18001e692  mov     rsi, [rsp+58h+arg_18]
0x18001e697  add     rsp, 50h
0x18001e69b  pop     rdi
0x18001e69c  retn
```
