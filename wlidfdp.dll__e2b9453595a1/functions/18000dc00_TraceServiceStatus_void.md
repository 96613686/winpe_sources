# TraceServiceStatus(void)

- ea: `0x18000dc00`
- end: `0x18000dd7d`
- name: `?TraceServiceStatus@@YAJXZ`
- size: `381`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000de3c`
- `0x18000e1c0`
- `0x18000e500`
- `0x18000e8b8`

## callees

- `0x1800027f0`
- `0x1800054dc`
- `0x180008edc`
- `0x18000dc00`
- `0x18000f4cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dcc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dcc1`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000dc7b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000dc7b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000dd3a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000dd48`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000dd3a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000dd48`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000dcb3`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000dcb3`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18000dcdf`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18000dcdf`

## string_xrefs

- `0x18000dc2f`: `TraceServiceStatus`
- `0x18000dc72`: `ServicesActive`
- `0x18000dcec`: `Service status: dwCheckPoint=0x%x, dwControlsAccepted=0x%x, dwCurrentState=0x%x, dwServiceSpecificExitCode=0x%x, dwServiceType=0x%x, dwWaitHint=0x%x, dwWin32ExitCode=0x%x.`

## pseudocode

```c
__int64 TraceServiceStatus(void)
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rdi
  signed int v2; // eax
  __int64 v3; // rdx
  int v4; // r8d
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rbx
  signed int LastError; // eax
  unsigned int v8; // ebx
  signed int v10; // [rsp+60h] [rbp+7h] BYREF
  _QWORD v11[4]; // [rsp+68h] [rbp+Fh] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+88h] [rbp+2Fh] BYREF

  v10 = 0;
  v11[2] = 0;
  v11[0] = "TraceServiceStatus";
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v11[1] = &v10;
  v11[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
    "TraceServiceStatus",
    (const char *)0x23);
  v0 = OpenSCManagerW(0, L"ServicesActive", 0x80000000);
  v1 = v0;
  if ( v0 )
  {
    v5 = OpenServiceW(v0, L"WlidSvc", 4u);
    v6 = v5;
    if ( v5 && QueryServiceStatus(v5, &ServiceStatus) )
    {
      TracePrintW(
        (PPTraceStatus *)5,
        (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
        0x3Cu,
        L"Service status: dwCheckPoint=0x%x, dwControlsAccepted=0x%x, dwCurrentState=0x%x, dwServiceSpecificExitCode=0x%x,"
         " dwServiceType=0x%x, dwWaitHint=0x%x, dwWin32ExitCode=0x%x.",
        ServiceStatus.dwCheckPoint,
        ServiceStatus.dwControlsAccepted,
        ServiceStatus.dwCurrentState,
        ServiceStatus.dwServiceSpecificExitCode,
        ServiceStatus.dwServiceType,
        ServiceStatus.dwWaitHint,
        ServiceStatus.dwWin32ExitCode);
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v10 = LastError;
    }
    CloseServiceHandle(v1);
    if ( v6 )
      CloseServiceHandle(v6);
  }
  else
  {
    v2 = GetLastError();
    if ( v2 > 0 )
      v2 = (unsigned __int16)v2 | 0x80070000;
    v10 = v2;
  }
  v8 = v10;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v11, v3, v4);
  return v8;
}

```

## disassembly

```asm
0x18000dc00  mov     [rsp-8+arg_0], rbx
0x18000dc05  mov     [rsp-8+arg_8], rdi
0x18000dc0a  push    rbp
0x18000dc0b  lea     rbp, [rsp-57h]
0x18000dc10  sub     rsp, 0B0h
0x18000dc17  mov     rax, cs:__security_cookie
0x18000dc1e  xor     rax, rsp
0x18000dc21  mov     [rbp+57h+var_8], rax
0x18000dc25  xorps   xmm0, xmm0
0x18000dc28  mov     [rbp+57h+var_50], 0
0x18000dc2f  lea     rdx, aTraceservicest; "TraceServiceStatus"
0x18000dc36  mov     [rbp+57h+var_38], 0
0x18000dc3e  lea     rax, [rbp+57h+var_50]
0x18000dc42  mov     [rbp+57h+var_48], rdx
0x18000dc46  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x18000dc4a  mov     r8d, 23h ; '#'; char *
0x18000dc50  mov     [rbp+57h+var_40], rax
0x18000dc54  lea     rcx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18000dc5b  mov     [rbp+57h+var_30], 0
0x18000dc63  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x18000dc67  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18000dc6c  mov     r8d, 80000000h; dwDesiredAccess
0x18000dc72  lea     rdx, DatabaseName; "ServicesActive"
0x18000dc79  xor     ecx, ecx; lpMachineName
0x18000dc7b  call    cs:__imp_OpenSCManagerW
0x18000dc81  mov     rdi, rax
0x18000dc84  test    rax, rax
0x18000dc87  jnz     short loc_18000DCA3
0x18000dc89  call    cs:__imp_GetLastError
0x18000dc8f  test    eax, eax
0x18000dc91  jle     short loc_18000DC9B
0x18000dc93  movzx   eax, ax
0x18000dc96  or      eax, 80070000h
0x18000dc9b  mov     [rbp+57h+var_50], eax
0x18000dc9e  jmp     loc_18000DD4E
0x18000dca3  mov     r8d, 4; dwDesiredAccess
0x18000dca9  lea     rdx, aWlidsvc_0; "WlidSvc"
0x18000dcb0  mov     rcx, rdi; hSCManager
0x18000dcb3  call    cs:__imp_OpenServiceW
0x18000dcb9  mov     rbx, rax
0x18000dcbc  test    rax, rax
0x18000dcbf  jnz     short loc_18000DCD8
0x18000dcc1  call    cs:__imp_GetLastError
0x18000dcc7  test    eax, eax
0x18000dcc9  jle     short loc_18000DCD3
0x18000dccb  movzx   eax, ax
0x18000dcce  or      eax, 80070000h
0x18000dcd3  mov     [rbp+57h+var_50], eax
0x18000dcd6  jmp     short loc_18000DD37
0x18000dcd8  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x18000dcdc  mov     rcx, rbx; hService
0x18000dcdf  call    cs:__imp_QueryServiceStatus
0x18000dce5  test    eax, eax
0x18000dce7  jz      short loc_18000DCC1
0x18000dce9  mov     eax, [rbp+57h+ServiceStatus.dwWin32ExitCode]
0x18000dcec  lea     r9, aServiceStatusD; "Service status: dwCheckPoint=0x%x, dwCo"...
0x18000dcf3  mov     [rsp+0B0h+var_60], eax
0x18000dcf7  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18000dcfe  mov     eax, [rbp+57h+ServiceStatus.dwWaitHint]
0x18000dd01  mov     r8d, 3Ch ; '<'; unsigned int
0x18000dd07  mov     [rsp+0B0h+var_68], eax
0x18000dd0b  mov     eax, [rbp+57h+ServiceStatus.dwServiceType]
0x18000dd0e  mov     [rsp+0B0h+var_70], eax
0x18000dd12  mov     eax, [rbp+57h+ServiceStatus.dwServiceSpecificExitCode]
0x18000dd15  lea     ecx, [r8-37h]; unsigned __int8
0x18000dd19  mov     [rsp+0B0h+var_78], eax
0x18000dd1d  mov     eax, [rbp+57h+ServiceStatus.dwCurrentState]
0x18000dd20  mov     [rsp+0B0h+var_80], eax
0x18000dd24  mov     eax, [rbp+57h+ServiceStatus.dwControlsAccepted]
0x18000dd27  mov     [rsp+0B0h+var_88], eax
0x18000dd2b  mov     eax, [rbp+57h+ServiceStatus.dwCheckPoint]
0x18000dd2e  mov     [rsp+0B0h+var_90], eax
0x18000dd32  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000dd37  mov     rcx, rdi; hSCObject
0x18000dd3a  call    cs:__imp_CloseServiceHandle
0x18000dd40  test    rbx, rbx
0x18000dd43  jz      short loc_18000DD4E
0x18000dd45  mov     rcx, rbx; hSCObject
0x18000dd48  call    cs:__imp_CloseServiceHandle
0x18000dd4e  mov     ebx, [rbp+57h+var_50]
0x18000dd51  lea     rcx, [rbp+57h+var_48]
0x18000dd55  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18000dd5a  mov     eax, ebx
0x18000dd5c  mov     rcx, [rbp+57h+var_8]
0x18000dd60  xor     rcx, rsp; StackCookie
0x18000dd63  call    __security_check_cookie
0x18000dd68  lea     r11, [rsp+0B0h+var_s0]
0x18000dd70  mov     rbx, [r11+10h]
0x18000dd74  mov     rdi, [r11+18h]
0x18000dd78  mov     rsp, r11
0x18000dd7b  pop     rbp
0x18000dd7c  retn
```
