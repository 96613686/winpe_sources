# CService::Continue(ushort const *,WDS_SERVICE_WAIT_TYPE)

- ea: `0x18001dd60`
- end: `0x18001de5e`
- name: `?Continue@CService@@QEAAKPEBGW4WDS_SERVICE_WAIT_TYPE@@@Z`
- size: `254`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18001dd60`
- `0x18001e6a4`
- `0x180030390`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001ddb4`
- `KERNEL32!GetLastError` at `0x18001dddc`
- `KERNEL32!GetLastError` at `0x18001ddb4`
- `KERNEL32!GetLastError` at `0x18001dddc`
- `ADVAPI32!CloseServiceHandle` at `0x18001de32`
- `ADVAPI32!CloseServiceHandle` at `0x18001de32`
- `ADVAPI32!QueryServiceStatus` at `0x18001ddcc`
- `ADVAPI32!QueryServiceStatus` at `0x18001ddcc`
- `ADVAPI32!OpenServiceW` at `0x18001dda0`
- `ADVAPI32!OpenServiceW` at `0x18001dda0`
- `ADVAPI32!ControlService` at `0x18001de0c`
- `ADVAPI32!ControlService` at `0x18001de0c`

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
0x18001dd60  mov     [rsp+arg_10], rbx
0x18001dd65  mov     [rsp+arg_18], rsi
0x18001dd6a  push    rdi
0x18001dd6b  sub     rsp, 50h
0x18001dd6f  mov     rax, cs:__security_cookie
0x18001dd76  xor     rax, rsp
0x18001dd79  mov     [rsp+58h+var_18], rax
0x18001dd7e  mov     rcx, [rcx]
0x18001dd81  xor     eax, eax
0x18001dd83  mov     esi, r8d
0x18001dd86  mov     qword ptr [rsp+58h+ServiceStatus.dwServiceSpecificExitCode], rax
0x18001dd8b  xorps   xmm0, xmm0
0x18001dd8e  mov     [rsp+58h+ServiceStatus.dwWaitHint], eax
0x18001dd92  xor     ebx, ebx
0x18001dd94  mov     rcx, [rcx]; hSCManager
0x18001dd97  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x18001dd9c  lea     r8d, [rbx+44h]; dwDesiredAccess
0x18001dda0  call    cs:__imp_OpenServiceW
0x18001dda7  nop     dword ptr [rax+rax+00h]
0x18001ddac  mov     rdi, rax
0x18001ddaf  test    rax, rax
0x18001ddb2  jnz     short loc_18001DDC4
0x18001ddb4  call    cs:__imp_GetLastError
0x18001ddbb  nop     dword ptr [rax+rax+00h]
0x18001ddc0  mov     ebx, eax
0x18001ddc2  jmp     short loc_18001DE3E
0x18001ddc4  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18001ddc9  mov     rcx, rdi; hService
0x18001ddcc  call    cs:__imp_QueryServiceStatus
0x18001ddd3  nop     dword ptr [rax+rax+00h]
0x18001ddd8  test    eax, eax
0x18001ddda  jnz     short loc_18001DDEA
0x18001dddc  call    cs:__imp_GetLastError
0x18001dde3  nop     dword ptr [rax+rax+00h]
0x18001dde8  jmp     short loc_18001DE2D
0x18001ddea  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 4
0x18001ddef  jz      short loc_18001DE2F
0x18001ddf1  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 7
0x18001ddf6  jz      short loc_18001DDFF
0x18001ddf8  mov     ebx, 426h
0x18001ddfd  jmp     short loc_18001DE2F
0x18001ddff  lea     r8, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18001de04  mov     edx, 3; dwControl
0x18001de09  mov     rcx, rdi; hService
0x18001de0c  call    cs:__imp_ControlService
0x18001de13  nop     dword ptr [rax+rax+00h]
0x18001de18  test    eax, eax
0x18001de1a  jz      short loc_18001DDDC
0x18001de1c  mov     r9d, esi
0x18001de1f  mov     r8d, 4
0x18001de25  mov     rdx, rdi
0x18001de28  call    ?WaitForService@CServiceControlInterface@@AEAAKPEAUSC_HANDLE__@@KW4WDS_SERVICE_WAIT_TYPE@@@Z; CServiceControlInterface::WaitForService(SC_HANDLE__ *,ulong,WDS_SERVICE_WAIT_TYPE)
0x18001de2d  mov     ebx, eax
0x18001de2f  mov     rcx, rdi; hSCObject
0x18001de32  call    cs:__imp_CloseServiceHandle
0x18001de39  nop     dword ptr [rax+rax+00h]
0x18001de3e  mov     eax, ebx
0x18001de40  mov     rcx, [rsp+58h+var_18]
0x18001de45  xor     rcx, rsp; StackCookie
0x18001de48  call    __security_check_cookie
0x18001de4d  mov     rbx, [rsp+58h+arg_10]
0x18001de52  mov     rsi, [rsp+58h+arg_18]
0x18001de57  add     rsp, 50h
0x18001de5b  pop     rdi
0x18001de5c  retn
```
