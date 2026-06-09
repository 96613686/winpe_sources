# InternetTime_StartServiceAndRefresh

- ea: `0x18001718c`
- end: `0x180017405`
- name: `InternetTime_StartServiceAndRefresh`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18001d600`

## callees

- `0x180001df0`
- `0x180001e3c`
- `0x180006dd8`
- `0x1800092c4`
- `0x180014db0`
- `0x180016e28`
- `0x18001718c`
- `0x180028f60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001720a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017235`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001720a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017235`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800171d9`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800171d9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001738c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800173ba`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001738c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800173ba`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800171b7`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800171b7`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180017309`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180017309`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180017347`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180017347`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180017200`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18001726b`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180017200`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18001726b`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1800172c9`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1800172c9`

## string_xrefs

- `0x1800172e0`: `shell\cpls\utc\inettimecommon.cpp`
- `0x180017370`: `shell\cpls\utc\inettimecommon.cpp`
- `0x1800173a1`: `shell\cpls\utc\inettimecommon.cpp`
- `0x1800173cf`: `shell\cpls\utc\inettimecommon.cpp`

## pseudocode

```c
__int64 __fastcall InternetTime_StartServiceAndRefresh(int a1)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rbp
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rsi
  struct _QUERY_SERVICE_CONFIGW *v6; // rdi
  unsigned int Error; // ebx
  signed int LastError; // eax
  unsigned __int64 v9; // r9
  __int64 v10; // rdx
  unsigned int v11; // eax
  int v12; // eax
  int lpBinaryPathName; // [rsp+20h] [rbp-98h]
  DWORD pcbBytesNeeded; // [rsp+60h] [rbp-58h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+68h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v2 = OpenSCManagerW(0, 0, 0x15u);
  v3 = v2;
  if ( !v2 )
  {
    Error = ResultFromLastError();
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x1C8,
      (unsigned int)"shell\\cpls\\utc\\inettimecommon.cpp",
      (const char *)Error,
      lpBinaryPathName);
    return Error;
  }
  v4 = OpenServiceW(v2, L"w32time", 0x53u);
  v5 = v4;
  if ( v4 )
  {
    pcbBytesNeeded = 0;
    if ( QueryServiceConfigW(v4, 0, 0, &pcbBytesNeeded) || GetLastError() != 122 )
    {
      v6 = 0;
      LastError = GetLastError();
      Error = LastError;
      if ( LastError > 0 )
        Error = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v6 = (struct _QUERY_SERVICE_CONFIGW *)operator new[](pcbBytesNeeded);
      Error = v6 == 0 ? 0x8007000E : 0;
    }
    if ( (Error & 0x80000000) != 0 )
    {
      v9 = Error;
      v10 = 399;
LABEL_26:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"shell\\cpls\\utc\\inettimecommon.cpp",
        (const char *)v9,
        lpBinaryPathName);
      goto LABEL_27;
    }
    if ( QueryServiceConfigW(v5, v6, pcbBytesNeeded, &pcbBytesNeeded)
      && v6->dwStartType == 4
      && !ChangeServiceConfigW(v5, 0xFFFFFFFF, 3u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
    {
      v11 = ResultFromKnownLastError();
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x19A,
        (unsigned int)"shell\\cpls\\utc\\inettimecommon.cpp",
        (const char *)v11,
        lpBinaryPathName);
    }
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( StartServiceW(v5, 0, 0) || (v12 = ResultFromLastError(), Error = v12, v12 == -2147023840) || v12 == -2147023835 )
    {
      Error = 0;
    }
    else if ( v12 < 0 )
    {
      v10 = 429;
LABEL_25:
      v9 = (unsigned int)v12;
      goto LABEL_26;
    }
    if ( a1 )
    {
      if ( ControlService(v5, 6u, &ServiceStatus) )
      {
        Error = 0;
      }
      else
      {
        v12 = ResultFromLastError();
        Error = v12;
        if ( v12 < 0 )
        {
          v10 = 434;
          goto LABEL_25;
        }
      }
    }
LABEL_27:
    if ( v6 )
      operator delete[](v6);
    CloseServiceHandle(v5);
    goto LABEL_31;
  }
  Error = ResultFromLastError();
  wil::details::in1diag3::Log_Hr(
    retaddr,
    (void *)0x1C0,
    (unsigned int)"shell\\cpls\\utc\\inettimecommon.cpp",
    (const char *)Error,
    lpBinaryPathName);
LABEL_31:
  CloseServiceHandle(v3);
  return Error;
}

```

## disassembly

```asm
0x18001718c  push    rbx
0x18001718e  push    rbp
0x18001718f  push    rsi
0x180017190  push    rdi
0x180017191  push    r14
0x180017193  sub     rsp, 90h
0x18001719a  mov     rax, cs:__security_cookie
0x1800171a1  xor     rax, rsp
0x1800171a4  mov     [rsp+0B8h+var_30], rax
0x1800171ac  xor     edx, edx; lpDatabaseName
0x1800171ae  mov     r14d, ecx
0x1800171b1  xor     ecx, ecx; lpMachineName
0x1800171b3  lea     r8d, [rdx+15h]; dwDesiredAccess
0x1800171b7  call    cs:__imp_OpenSCManagerW
0x1800171bd  mov     rbp, rax
0x1800171c0  test    rax, rax
0x1800171c3  jz      loc_1800173C2
0x1800171c9  mov     r8d, 53h ; 'S'; dwDesiredAccess
0x1800171cf  lea     rdx, ServiceName; "w32time"
0x1800171d6  mov     rcx, rax; hSCManager
0x1800171d9  call    cs:__imp_OpenServiceW
0x1800171df  mov     rsi, rax
0x1800171e2  test    rax, rax
0x1800171e5  jz      loc_180017394
0x1800171eb  lea     r9, [rsp+0B8h+pcbBytesNeeded]; pcbBytesNeeded
0x1800171f0  mov     [rsp+0B8h+pcbBytesNeeded], 0
0x1800171f8  xor     r8d, r8d; cbBufSize
0x1800171fb  xor     edx, edx; lpServiceConfig
0x1800171fd  mov     rcx, rax; hService
0x180017200  call    cs:__imp_QueryServiceConfigW
0x180017206  test    eax, eax
0x180017208  jnz     short loc_180017233
0x18001720a  call    cs:__imp_GetLastError
0x180017210  cmp     eax, 7Ah ; 'z'
0x180017213  jnz     short loc_180017233
0x180017215  mov     ecx, [rsp+0B8h+pcbBytesNeeded]; unsigned __int64
0x180017219  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001721e  mov     rcx, rax
0x180017221  mov     rdi, rax
0x180017224  neg     rcx
0x180017227  sbb     ebx, ebx
0x180017229  not     ebx
0x18001722b  and     ebx, 8007000Eh
0x180017231  jmp     short loc_18001724A
0x180017233  xor     edi, edi
0x180017235  call    cs:__imp_GetLastError
0x18001723b  mov     ebx, eax
0x18001723d  test    eax, eax
0x18001723f  jle     short loc_18001724A
0x180017241  movzx   ebx, ax
0x180017244  or      ebx, 80070000h
0x18001724a  test    ebx, ebx
0x18001724c  jns     short loc_18001725B
0x18001724e  mov     r9d, ebx
0x180017251  mov     edx, 18Fh
0x180017256  jmp     loc_180017368
0x18001725b  mov     r8d, [rsp+0B8h+pcbBytesNeeded]; cbBufSize
0x180017260  lea     r9, [rsp+0B8h+pcbBytesNeeded]; pcbBytesNeeded
0x180017265  mov     rdx, rdi; lpServiceConfig
0x180017268  mov     rcx, rsi; hService
0x18001726b  call    cs:__imp_QueryServiceConfigW
0x180017271  test    eax, eax
0x180017273  jz      short loc_1800172F4
0x180017275  cmp     dword ptr [rdi+4], 4
0x180017279  jnz     short loc_1800172F4
0x18001727b  mov     [rsp+0B8h+lpDisplayName], 0; lpDisplayName
0x180017284  or      edx, 0FFFFFFFFh; dwServiceType
0x180017287  mov     [rsp+0B8h+lpPassword], 0; lpPassword
0x180017290  mov     r9d, edx; dwErrorControl
0x180017293  mov     [rsp+0B8h+lpServiceStartName], 0; lpServiceStartName
0x18001729c  mov     r8d, 3; dwStartType
0x1800172a2  mov     [rsp+0B8h+lpDependencies], 0; lpDependencies
0x1800172ab  mov     rcx, rsi; hService
0x1800172ae  mov     [rsp+0B8h+lpdwTagId], 0; lpdwTagId
0x1800172b7  mov     [rsp+0B8h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x1800172c0  mov     [rsp+0B8h+lpBinaryPathName], 0; int
0x1800172c9  call    cs:__imp_ChangeServiceConfigW
0x1800172cf  test    eax, eax
0x1800172d1  jnz     short loc_1800172F4
0x1800172d3  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800172d8  mov     rcx, [rsp+0B8h]; this
0x1800172e0  lea     r8, aShellCplsUtcIn; "shell\\cpls\\utc\\inettimecommon.cpp"
0x1800172e7  mov     r9d, eax; char *
0x1800172ea  mov     edx, 19Ah; void *
0x1800172ef  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800172f4  xorps   xmm0, xmm0
0x1800172f7  xor     r8d, r8d; lpServiceArgVectors
0x1800172fa  movups  xmmword ptr [rsp+0B8h+ServiceStatus.dwServiceType], xmm0
0x1800172ff  xor     edx, edx; dwNumServiceArgs
0x180017301  mov     rcx, rsi; hService
0x180017304  movups  xmmword ptr [rsp+0B8h+ServiceStatus.dwWin32ExitCode], xmm0
0x180017309  call    cs:__imp_StartServiceW
0x18001730f  test    eax, eax
0x180017311  jnz     short loc_180017333
0x180017313  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180017318  mov     ebx, eax
0x18001731a  cmp     eax, 80070420h
0x18001731f  jz      short loc_180017333
0x180017321  cmp     eax, 80070425h
0x180017326  jz      short loc_180017333
0x180017328  test    eax, eax
0x18001732a  jns     short loc_180017335
0x18001732c  mov     edx, 1ADh
0x180017331  jmp     short loc_180017365
0x180017333  xor     ebx, ebx
0x180017335  test    r14d, r14d
0x180017338  jz      short loc_18001737C
0x18001733a  lea     r8, [rsp+0B8h+ServiceStatus]; lpServiceStatus
0x18001733f  mov     edx, 6; dwControl
0x180017344  mov     rcx, rsi; hService
0x180017347  call    cs:__imp_ControlService
0x18001734d  test    eax, eax
0x18001734f  jz      short loc_180017355
0x180017351  xor     ebx, ebx
0x180017353  jmp     short loc_18001737C
0x180017355  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001735a  mov     ebx, eax
0x18001735c  test    eax, eax
0x18001735e  jns     short loc_18001737C
0x180017360  mov     edx, 1B2h; void *
0x180017365  mov     r9d, eax; char *
0x180017368  mov     rcx, [rsp+0B8h]; this
0x180017370  lea     r8, aShellCplsUtcIn; "shell\\cpls\\utc\\inettimecommon.cpp"
0x180017377  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001737c  test    rdi, rdi
0x18001737f  jz      short loc_180017389
0x180017381  mov     rcx, rdi; Block
0x180017384  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180017389  mov     rcx, rsi; hSCObject
0x18001738c  call    cs:__imp_CloseServiceHandle
0x180017392  jmp     short loc_1800173B7
0x180017394  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180017399  mov     rcx, [rsp+0B8h]; this
0x1800173a1  lea     r8, aShellCplsUtcIn; "shell\\cpls\\utc\\inettimecommon.cpp"
0x1800173a8  mov     r9d, eax; char *
0x1800173ab  mov     edx, 1C0h; void *
0x1800173b0  mov     ebx, eax
0x1800173b2  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800173b7  mov     rcx, rbp; hSCObject
0x1800173ba  call    cs:__imp_CloseServiceHandle
0x1800173c0  jmp     short loc_1800173E5
0x1800173c2  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800173c7  mov     rcx, [rsp+0B8h]; this
0x1800173cf  lea     r8, aShellCplsUtcIn; "shell\\cpls\\utc\\inettimecommon.cpp"
0x1800173d6  mov     r9d, eax; char *
0x1800173d9  mov     edx, 1C8h; void *
0x1800173de  mov     ebx, eax
0x1800173e0  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800173e5  mov     eax, ebx
0x1800173e7  mov     rcx, [rsp+0B8h+var_30]
0x1800173ef  xor     rcx, rsp; StackCookie
0x1800173f2  call    __security_check_cookie
0x1800173f7  add     rsp, 90h
0x1800173fe  pop     r14
0x180017400  pop     rdi
0x180017401  pop     rsi
0x180017402  pop     rbp
0x180017403  pop     rbx
0x180017404  retn
```
