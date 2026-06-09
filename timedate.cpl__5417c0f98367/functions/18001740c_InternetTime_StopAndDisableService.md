# InternetTime_StopAndDisableService

- ea: `0x18001740c`
- end: `0x180017541`
- name: `InternetTime_StopAndDisableService`
- size: `309`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001d840`

## callees

- `0x180006dd8`
- `0x180016e28`
- `0x18001740c`
- `0x180028f60`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001745a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001745a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800174c1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800174ef`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800174c1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800174ef`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180017438`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180017438`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800174b8`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800174b8`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18001749a`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18001749a`

## string_xrefs

- `0x1800174d6`: `shell\cpls\utc\inettimecommon.cpp`
- `0x180017504`: `shell\cpls\utc\inettimecommon.cpp`

## pseudocode

```c
__int64 InternetTime_StopAndDisableService()
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rdi
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rsi
  unsigned int Error; // ebx
  int lpBinaryPathName; // [rsp+20h] [rbp-78h]
  struct _SERVICE_STATUS ServiceStatus; // [rsp+60h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v0 = OpenSCManagerW(0, 0, 0x15u);
  v1 = v0;
  if ( v0 )
  {
    v2 = OpenServiceW(v0, L"w32time", 0x63u);
    v3 = v2;
    if ( v2 )
    {
      Error = 0;
      ChangeServiceConfigW(v2, 0xFFFFFFFF, 4u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0);
      memset(&ServiceStatus, 0, sizeof(ServiceStatus));
      ControlService(v3, 1u, &ServiceStatus);
      CloseServiceHandle(v3);
    }
    else
    {
      Error = ResultFromKnownLastError();
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x1E8,
        (unsigned int)"shell\\cpls\\utc\\inettimecommon.cpp",
        (const char *)Error,
        lpBinaryPathName);
    }
    CloseServiceHandle(v1);
  }
  else
  {
    Error = ResultFromKnownLastError();
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x1F0,
      (unsigned int)"shell\\cpls\\utc\\inettimecommon.cpp",
      (const char *)Error,
      lpBinaryPathName);
  }
  return Error;
}

```

## disassembly

```asm
0x18001740c  mov     [rsp+arg_0], rbx
0x180017411  mov     [rsp+arg_8], rsi
0x180017416  push    rdi
0x180017417  sub     rsp, 90h
0x18001741e  mov     rax, cs:__security_cookie
0x180017425  xor     rax, rsp
0x180017428  mov     [rsp+98h+var_18], rax
0x180017430  xor     edx, edx; lpDatabaseName
0x180017432  xor     ecx, ecx; lpMachineName
0x180017434  lea     r8d, [rdx+15h]; dwDesiredAccess
0x180017438  call    cs:__imp_OpenSCManagerW
0x18001743e  mov     rdi, rax
0x180017441  test    rax, rax
0x180017444  jz      loc_1800174F7
0x18001744a  mov     r8d, 63h ; 'c'; dwDesiredAccess
0x180017450  lea     rdx, ServiceName; "w32time"
0x180017457  mov     rcx, rax; hSCManager
0x18001745a  call    cs:__imp_OpenServiceW
0x180017460  mov     rsi, rax
0x180017463  test    rax, rax
0x180017466  jz      short loc_1800174C9
0x180017468  xor     ebx, ebx
0x18001746a  or      edx, 0FFFFFFFFh; dwServiceType
0x18001746d  mov     [rsp+98h+lpDisplayName], rbx; lpDisplayName
0x180017472  mov     r9d, edx; dwErrorControl
0x180017475  mov     [rsp+98h+lpPassword], rbx; lpPassword
0x18001747a  mov     rcx, rax; hService
0x18001747d  mov     [rsp+98h+lpServiceStartName], rbx; lpServiceStartName
0x180017482  mov     [rsp+98h+lpDependencies], rbx; lpDependencies
0x180017487  lea     r8d, [rbx+4]; dwStartType
0x18001748b  mov     [rsp+98h+lpdwTagId], rbx; lpdwTagId
0x180017490  mov     [rsp+98h+lpLoadOrderGroup], rbx; lpLoadOrderGroup
0x180017495  mov     [rsp+98h+lpBinaryPathName], rbx; lpBinaryPathName
0x18001749a  call    cs:__imp_ChangeServiceConfigW
0x1800174a0  xorps   xmm0, xmm0
0x1800174a3  lea     r8, [rsp+98h+ServiceStatus]; lpServiceStatus
0x1800174a8  movups  xmmword ptr [rsp+98h+ServiceStatus.dwServiceType], xmm0
0x1800174ad  lea     edx, [rbx+1]; dwControl
0x1800174b0  mov     rcx, rsi; hService
0x1800174b3  movups  xmmword ptr [rsp+98h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800174b8  call    cs:__imp_ControlService
0x1800174be  mov     rcx, rsi; hSCObject
0x1800174c1  call    cs:__imp_CloseServiceHandle
0x1800174c7  jmp     short loc_1800174EC
0x1800174c9  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800174ce  mov     rcx, [rsp+98h]; this
0x1800174d6  lea     r8, aShellCplsUtcIn; "shell\\cpls\\utc\\inettimecommon.cpp"
0x1800174dd  mov     r9d, eax; char *
0x1800174e0  mov     edx, 1E8h; void *
0x1800174e5  mov     ebx, eax
0x1800174e7  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800174ec  mov     rcx, rdi; hSCObject
0x1800174ef  call    cs:__imp_CloseServiceHandle
0x1800174f5  jmp     short loc_18001751A
0x1800174f7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800174fc  mov     rcx, [rsp+98h]; this
0x180017504  lea     r8, aShellCplsUtcIn; "shell\\cpls\\utc\\inettimecommon.cpp"
0x18001750b  mov     r9d, eax; char *
0x18001750e  mov     edx, 1F0h; void *
0x180017513  mov     ebx, eax
0x180017515  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001751a  mov     eax, ebx
0x18001751c  mov     rcx, [rsp+98h+var_18]
0x180017524  xor     rcx, rsp; StackCookie
0x180017527  call    __security_check_cookie
0x18001752c  lea     r11, [rsp+98h+var_8]
0x180017534  mov     rbx, [r11+10h]
0x180017538  mov     rsi, [r11+18h]
0x18001753c  mov     rsp, r11
0x18001753f  pop     rdi
0x180017540  retn
```
