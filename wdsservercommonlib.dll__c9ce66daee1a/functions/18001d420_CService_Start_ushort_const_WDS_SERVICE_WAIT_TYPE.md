# CService::Start(ushort const *,WDS_SERVICE_WAIT_TYPE)

- ea: `0x18001d420`
- end: `0x18001d50b`
- name: `?Start@CService@@QEAAKPEBGW4WDS_SERVICE_WAIT_TYPE@@@Z`
- size: `235`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18001d420`
- `0x18001d724`
- `0x18002f3e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001d474`
- `KERNEL32!GetLastError` at `0x18001d49c`
- `KERNEL32!GetLastError` at `0x18001d474`
- `KERNEL32!GetLastError` at `0x18001d49c`
- `ADVAPI32!StartServiceW` at `0x18001d4b9`
- `ADVAPI32!StartServiceW` at `0x18001d4b9`
- `ADVAPI32!OpenServiceW` at `0x18001d460`
- `ADVAPI32!OpenServiceW` at `0x18001d460`
- `ADVAPI32!QueryServiceStatus` at `0x18001d48c`
- `ADVAPI32!QueryServiceStatus` at `0x18001d48c`
- `ADVAPI32!CloseServiceHandle` at `0x18001d4df`
- `ADVAPI32!CloseServiceHandle` at `0x18001d4df`

## pseudocode

```c
__int64 __fastcall CService::Start(SC_HANDLE **a1, const WCHAR *a2, unsigned int a3)
{
  DWORD v4; // ebx
  SC_HANDLE v5; // rcx
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rdi
  DWORD LastError; // eax
  __int64 v9; // rcx
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  v4 = 0;
  v5 = **a1;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v6 = OpenServiceW(v5, a2, 0x14u);
  v7 = v6;
  if ( v6 )
  {
    if ( !QueryServiceStatus(v6, &ServiceStatus) )
      goto LABEL_4;
    if ( ServiceStatus.dwCurrentState == 4 )
    {
LABEL_9:
      CloseServiceHandle(v7);
      return v4;
    }
    if ( StartServiceW(v7, 0, 0) )
      LastError = CServiceControlInterface::WaitForService(
                    v9,
                    v7,
                    4,
                    a3,
                    *(_QWORD *)&ServiceStatus.dwServiceType,
                    *(_QWORD *)&ServiceStatus.dwControlsAccepted,
                    *(_QWORD *)&ServiceStatus.dwServiceSpecificExitCode,
                    ServiceStatus.dwWaitHint);
    else
LABEL_4:
      LastError = GetLastError();
    v4 = LastError;
    goto LABEL_9;
  }
  return GetLastError();
}

```

## disassembly

```asm
0x18001d420  mov     [rsp+arg_10], rbx
0x18001d425  mov     [rsp+arg_18], rsi
0x18001d42a  push    rdi
0x18001d42b  sub     rsp, 50h
0x18001d42f  mov     rax, cs:__security_cookie
0x18001d436  xor     rax, rsp
0x18001d439  mov     [rsp+58h+var_18], rax
0x18001d43e  mov     rcx, [rcx]
0x18001d441  xor     eax, eax
0x18001d443  mov     esi, r8d
0x18001d446  mov     qword ptr [rsp+58h+ServiceStatus.dwServiceSpecificExitCode], rax
0x18001d44b  xorps   xmm0, xmm0
0x18001d44e  mov     [rsp+58h+ServiceStatus.dwWaitHint], eax
0x18001d452  xor     ebx, ebx
0x18001d454  mov     rcx, [rcx]; hSCManager
0x18001d457  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x18001d45c  lea     r8d, [rbx+14h]; dwDesiredAccess
0x18001d460  call    cs:__imp_OpenServiceW
0x18001d467  nop     dword ptr [rax+rax+00h]
0x18001d46c  mov     rdi, rax
0x18001d46f  test    rax, rax
0x18001d472  jnz     short loc_18001D484
0x18001d474  call    cs:__imp_GetLastError
0x18001d47b  nop     dword ptr [rax+rax+00h]
0x18001d480  mov     ebx, eax
0x18001d482  jmp     short loc_18001D4EB
0x18001d484  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18001d489  mov     rcx, rdi; hService
0x18001d48c  call    cs:__imp_QueryServiceStatus
0x18001d493  nop     dword ptr [rax+rax+00h]
0x18001d498  test    eax, eax
0x18001d49a  jnz     short loc_18001D4AA
0x18001d49c  call    cs:__imp_GetLastError
0x18001d4a3  nop     dword ptr [rax+rax+00h]
0x18001d4a8  jmp     short loc_18001D4DA
0x18001d4aa  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 4
0x18001d4af  jz      short loc_18001D4DC
0x18001d4b1  xor     r8d, r8d; lpServiceArgVectors
0x18001d4b4  xor     edx, edx; dwNumServiceArgs
0x18001d4b6  mov     rcx, rdi; hService
0x18001d4b9  call    cs:__imp_StartServiceW
0x18001d4c0  nop     dword ptr [rax+rax+00h]
0x18001d4c5  test    eax, eax
0x18001d4c7  jz      short loc_18001D49C
0x18001d4c9  mov     r9d, esi
0x18001d4cc  mov     r8d, 4
0x18001d4d2  mov     rdx, rdi
0x18001d4d5  call    ?WaitForService@CServiceControlInterface@@AEAAKPEAUSC_HANDLE__@@KW4WDS_SERVICE_WAIT_TYPE@@@Z; CServiceControlInterface::WaitForService(SC_HANDLE__ *,ulong,WDS_SERVICE_WAIT_TYPE)
0x18001d4da  mov     ebx, eax
0x18001d4dc  mov     rcx, rdi; hSCObject
0x18001d4df  call    cs:__imp_CloseServiceHandle
0x18001d4e6  nop     dword ptr [rax+rax+00h]
0x18001d4eb  mov     eax, ebx
0x18001d4ed  mov     rcx, [rsp+58h+var_18]
0x18001d4f2  xor     rcx, rsp; StackCookie
0x18001d4f5  call    __security_check_cookie
0x18001d4fa  mov     rbx, [rsp+58h+arg_10]
0x18001d4ff  mov     rsi, [rsp+58h+arg_18]
0x18001d504  add     rsp, 50h
0x18001d508  pop     rdi
0x18001d509  retn
```
