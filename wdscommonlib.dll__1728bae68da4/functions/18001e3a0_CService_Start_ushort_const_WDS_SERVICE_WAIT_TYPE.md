# CService::Start(ushort const *,WDS_SERVICE_WAIT_TYPE)

- ea: `0x18001e3a0`
- end: `0x18001e48b`
- name: `?Start@CService@@QEAAKPEBGW4WDS_SERVICE_WAIT_TYPE@@@Z`
- size: `235`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18001e3a0`
- `0x18001e6a4`
- `0x180030390`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001e3f4`
- `KERNEL32!GetLastError` at `0x18001e41c`
- `KERNEL32!GetLastError` at `0x18001e3f4`
- `KERNEL32!GetLastError` at `0x18001e41c`
- `ADVAPI32!CloseServiceHandle` at `0x18001e45f`
- `ADVAPI32!CloseServiceHandle` at `0x18001e45f`
- `ADVAPI32!QueryServiceStatus` at `0x18001e40c`
- `ADVAPI32!QueryServiceStatus` at `0x18001e40c`
- `ADVAPI32!OpenServiceW` at `0x18001e3e0`
- `ADVAPI32!OpenServiceW` at `0x18001e3e0`
- `ADVAPI32!StartServiceW` at `0x18001e439`
- `ADVAPI32!StartServiceW` at `0x18001e439`

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
0x18001e3a0  mov     [rsp+arg_10], rbx
0x18001e3a5  mov     [rsp+arg_18], rsi
0x18001e3aa  push    rdi
0x18001e3ab  sub     rsp, 50h
0x18001e3af  mov     rax, cs:__security_cookie
0x18001e3b6  xor     rax, rsp
0x18001e3b9  mov     [rsp+58h+var_18], rax
0x18001e3be  mov     rcx, [rcx]
0x18001e3c1  xor     eax, eax
0x18001e3c3  mov     esi, r8d
0x18001e3c6  mov     qword ptr [rsp+58h+ServiceStatus.dwServiceSpecificExitCode], rax
0x18001e3cb  xorps   xmm0, xmm0
0x18001e3ce  mov     [rsp+58h+ServiceStatus.dwWaitHint], eax
0x18001e3d2  xor     ebx, ebx
0x18001e3d4  mov     rcx, [rcx]; hSCManager
0x18001e3d7  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x18001e3dc  lea     r8d, [rbx+14h]; dwDesiredAccess
0x18001e3e0  call    cs:__imp_OpenServiceW
0x18001e3e7  nop     dword ptr [rax+rax+00h]
0x18001e3ec  mov     rdi, rax
0x18001e3ef  test    rax, rax
0x18001e3f2  jnz     short loc_18001E404
0x18001e3f4  call    cs:__imp_GetLastError
0x18001e3fb  nop     dword ptr [rax+rax+00h]
0x18001e400  mov     ebx, eax
0x18001e402  jmp     short loc_18001E46B
0x18001e404  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18001e409  mov     rcx, rdi; hService
0x18001e40c  call    cs:__imp_QueryServiceStatus
0x18001e413  nop     dword ptr [rax+rax+00h]
0x18001e418  test    eax, eax
0x18001e41a  jnz     short loc_18001E42A
0x18001e41c  call    cs:__imp_GetLastError
0x18001e423  nop     dword ptr [rax+rax+00h]
0x18001e428  jmp     short loc_18001E45A
0x18001e42a  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 4
0x18001e42f  jz      short loc_18001E45C
0x18001e431  xor     r8d, r8d; lpServiceArgVectors
0x18001e434  xor     edx, edx; dwNumServiceArgs
0x18001e436  mov     rcx, rdi; hService
0x18001e439  call    cs:__imp_StartServiceW
0x18001e440  nop     dword ptr [rax+rax+00h]
0x18001e445  test    eax, eax
0x18001e447  jz      short loc_18001E41C
0x18001e449  mov     r9d, esi
0x18001e44c  mov     r8d, 4
0x18001e452  mov     rdx, rdi
0x18001e455  call    ?WaitForService@CServiceControlInterface@@AEAAKPEAUSC_HANDLE__@@KW4WDS_SERVICE_WAIT_TYPE@@@Z; CServiceControlInterface::WaitForService(SC_HANDLE__ *,ulong,WDS_SERVICE_WAIT_TYPE)
0x18001e45a  mov     ebx, eax
0x18001e45c  mov     rcx, rdi; hSCObject
0x18001e45f  call    cs:__imp_CloseServiceHandle
0x18001e466  nop     dword ptr [rax+rax+00h]
0x18001e46b  mov     eax, ebx
0x18001e46d  mov     rcx, [rsp+58h+var_18]
0x18001e472  xor     rcx, rsp; StackCookie
0x18001e475  call    __security_check_cookie
0x18001e47a  mov     rbx, [rsp+58h+arg_10]
0x18001e47f  mov     rsi, [rsp+58h+arg_18]
0x18001e484  add     rsp, 50h
0x18001e488  pop     rdi
0x18001e489  retn
```
