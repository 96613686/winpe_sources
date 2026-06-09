# CService::Stop(ushort const *,WDS_SERVICE_WAIT_TYPE)

- ea: `0x18001e4a0`
- end: `0x18001e597`
- name: `?Stop@CService@@QEAAKPEBGW4WDS_SERVICE_WAIT_TYPE@@@Z`
- size: `247`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18001e4a0`
- `0x18001e6a4`
- `0x180030390`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001e4f4`
- `KERNEL32!GetLastError` at `0x18001e51c`
- `KERNEL32!GetLastError` at `0x18001e4f4`
- `KERNEL32!GetLastError` at `0x18001e51c`
- `ADVAPI32!CloseServiceHandle` at `0x18001e56b`
- `ADVAPI32!CloseServiceHandle` at `0x18001e56b`
- `ADVAPI32!QueryServiceStatus` at `0x18001e50c`
- `ADVAPI32!QueryServiceStatus` at `0x18001e50c`
- `ADVAPI32!OpenServiceW` at `0x18001e4e0`
- `ADVAPI32!OpenServiceW` at `0x18001e4e0`
- `ADVAPI32!ControlService` at `0x18001e545`
- `ADVAPI32!ControlService` at `0x18001e545`

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
0x18001e4a0  mov     [rsp+arg_10], rbx
0x18001e4a5  mov     [rsp+arg_18], rsi
0x18001e4aa  push    rdi
0x18001e4ab  sub     rsp, 50h
0x18001e4af  mov     rax, cs:__security_cookie
0x18001e4b6  xor     rax, rsp
0x18001e4b9  mov     [rsp+58h+var_18], rax
0x18001e4be  mov     rcx, [rcx]
0x18001e4c1  xor     eax, eax
0x18001e4c3  mov     esi, r8d
0x18001e4c6  mov     qword ptr [rsp+58h+ServiceStatus.dwServiceSpecificExitCode], rax
0x18001e4cb  xorps   xmm0, xmm0
0x18001e4ce  mov     [rsp+58h+ServiceStatus.dwWaitHint], eax
0x18001e4d2  xor     ebx, ebx
0x18001e4d4  mov     rcx, [rcx]; hSCManager
0x18001e4d7  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x18001e4dc  lea     r8d, [rbx+24h]; dwDesiredAccess
0x18001e4e0  call    cs:__imp_OpenServiceW
0x18001e4e7  nop     dword ptr [rax+rax+00h]
0x18001e4ec  mov     rdi, rax
0x18001e4ef  test    rax, rax
0x18001e4f2  jnz     short loc_18001E504
0x18001e4f4  call    cs:__imp_GetLastError
0x18001e4fb  nop     dword ptr [rax+rax+00h]
0x18001e500  mov     ebx, eax
0x18001e502  jmp     short loc_18001E577
0x18001e504  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18001e509  mov     rcx, rdi; hService
0x18001e50c  call    cs:__imp_QueryServiceStatus
0x18001e513  nop     dword ptr [rax+rax+00h]
0x18001e518  test    eax, eax
0x18001e51a  jnz     short loc_18001E52A
0x18001e51c  call    cs:__imp_GetLastError
0x18001e523  nop     dword ptr [rax+rax+00h]
0x18001e528  jmp     short loc_18001E566
0x18001e52a  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 1
0x18001e52f  jz      short loc_18001E568
0x18001e531  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 3
0x18001e536  jz      short loc_18001E555
0x18001e538  lea     r8, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18001e53d  mov     edx, 1; dwControl
0x18001e542  mov     rcx, rdi; hService
0x18001e545  call    cs:__imp_ControlService
0x18001e54c  nop     dword ptr [rax+rax+00h]
0x18001e551  test    eax, eax
0x18001e553  jz      short loc_18001E51C
0x18001e555  mov     r9d, esi
0x18001e558  mov     r8d, 1
0x18001e55e  mov     rdx, rdi
0x18001e561  call    ?WaitForService@CServiceControlInterface@@AEAAKPEAUSC_HANDLE__@@KW4WDS_SERVICE_WAIT_TYPE@@@Z; CServiceControlInterface::WaitForService(SC_HANDLE__ *,ulong,WDS_SERVICE_WAIT_TYPE)
0x18001e566  mov     ebx, eax
0x18001e568  mov     rcx, rdi; hSCObject
0x18001e56b  call    cs:__imp_CloseServiceHandle
0x18001e572  nop     dword ptr [rax+rax+00h]
0x18001e577  mov     eax, ebx
0x18001e579  mov     rcx, [rsp+58h+var_18]
0x18001e57e  xor     rcx, rsp; StackCookie
0x18001e581  call    __security_check_cookie
0x18001e586  mov     rbx, [rsp+58h+arg_10]
0x18001e58b  mov     rsi, [rsp+58h+arg_18]
0x18001e590  add     rsp, 50h
0x18001e594  pop     rdi
0x18001e595  retn
```
