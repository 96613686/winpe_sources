# TraceServiceStatus(void)

- ea: `0x180046ce0`
- end: `0x180046e5e`
- name: `?TraceServiceStatus@@YAJXZ`
- size: `382`
- prototype: `__int64(void)`
- caller_count: `45`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180046f0c`
- `0x1800473e0`
- `0x180047748`
- `0x180047a84`
- `0x180047e20`
- `0x180048158`
- `0x1800484c4`
- `0x180048818`
- `0x180048b44`
- `0x180048ecc`
- `0x180049268`
- `0x1800495d4`
- `0x18004990c`
- `0x180049c6c`
- `0x180049fd8`
- `0x18004a344`
- `0x18004a6b0`
- `0x18004aa84`
- `0x18004ae78`
- `0x18004b1c0`
- `0x18004b594`
- `0x18004b8cc`
- `0x18004bbf4`
- `0x18004bf2c`
- `0x18004c300`
- `0x18004c66c`
- `0x18004c9b8`
- `0x18004cd60`
- `0x18004d0cc`
- `0x18004d454`
- `0x18004d78c`
- `0x18004daf8`
- `0x18004de44`
- `0x18004e198`
- `0x18004e504`
- `0x18004e838`
- `0x18004eba0`
- `0x18004ef0c`
- `0x18004f24c`
- `0x18004f590`
- `0x18004f8d4`
- `0x18004fc38`
- `0x18004ffa4`
- `0x180050304`
- `0x180050724`

## callees

- `0x180002da0`
- `0x18000cc9c`
- `0x18000e870`
- `0x180046ce0`
- `0x1800530e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046d6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046da2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046d6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046da2`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180046d5c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180046d5c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180046d94`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180046d94`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180046e1b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180046e29`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180046e1b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180046e29`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180046dc0`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180046dc0`

## string_xrefs

- `0x180046d1a`: `TraceServiceStatus`
- `0x180046d53`: `ServicesActive`
- `0x180046dcd`: `Service status: dwCheckPoint=0x%x, dwControlsAccepted=0x%x, dwCurrentState=0x%x, dwServiceSpecificExitCode=0x%x, dwServiceType=0x%x, dwWaitHint=0x%x, dwWin32ExitCode=0x%x.`

## pseudocode

```c
__int64 TraceServiceStatus(void)
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rdi
  signed int v2; // eax
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rbx
  signed int LastError; // eax
  unsigned int v6; // ebx
  const unsigned __int16 *v8; // [rsp+20h] [rbp-39h]
  __int64 v9; // [rsp+20h] [rbp-39h]
  signed int v10; // [rsp+60h] [rbp+7h] BYREF
  _QWORD v11[4]; // [rsp+68h] [rbp+Fh] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+88h] [rbp+2Fh] BYREF

  v10 = 0;
  v11[2] = 0;
  v11[3] = 0;
  v11[0] = "TraceServiceStatus";
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v11[1] = &v10;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
    "TraceServiceStatus",
    (const char *)0x23,
    0,
    v8);
  v0 = OpenSCManagerW(0, L"ServicesActive", 0x80000000);
  v1 = v0;
  if ( v0 )
  {
    v3 = OpenServiceW(v0, L"WlidSvc", 4u);
    v4 = v3;
    if ( v3 && QueryServiceStatus(v3, &ServiceStatus) )
    {
      LODWORD(v9) = ServiceStatus.dwCheckPoint;
      TracePrintW(
        5u,
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
        0x3Cu,
        L"Service status: dwCheckPoint=0x%x, dwControlsAccepted=0x%x, dwCurrentState=0x%x, dwServiceSpecificExitCode=0x%x,"
         " dwServiceType=0x%x, dwWaitHint=0x%x, dwWin32ExitCode=0x%x.",
        v9,
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
    if ( v4 )
      CloseServiceHandle(v4);
  }
  else
  {
    v2 = GetLastError();
    if ( v2 > 0 )
      v2 = (unsigned __int16)v2 | 0x80070000;
    v10 = v2;
  }
  v6 = v10;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v11);
  return v6;
}

```

## disassembly

```asm
0x180046ce0  mov     [rsp-8+arg_0], rbx
0x180046ce5  mov     [rsp-8+arg_8], rdi
0x180046cea  push    rbp
0x180046ceb  lea     rbp, [rsp-57h]
0x180046cf0  sub     rsp, 0B0h
0x180046cf7  mov     rax, cs:__security_cookie
0x180046cfe  xor     rax, rsp
0x180046d01  mov     [rbp+57h+var_8], rax
0x180046d05  xorps   xmm0, xmm0
0x180046d08  mov     [rbp+57h+var_50], 0
0x180046d0f  xor     r9d, r9d; unsigned int
0x180046d12  mov     [rbp+57h+var_38], 0
0x180046d1a  lea     rdx, aTraceservicest; "TraceServiceStatus"
0x180046d21  mov     [rbp+57h+var_30], 0
0x180046d29  lea     rax, [rbp+57h+var_50]
0x180046d2d  mov     [rbp+57h+var_48], rdx
0x180046d31  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x180046d35  lea     r8d, [r9+23h]; char *
0x180046d39  mov     [rbp+57h+var_40], rax
0x180046d3d  lea     rcx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180046d44  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x180046d48  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180046d4d  mov     r8d, 80000000h; dwDesiredAccess
0x180046d53  lea     rdx, DatabaseName; "ServicesActive"
0x180046d5a  xor     ecx, ecx; lpMachineName
0x180046d5c  call    cs:__imp_OpenSCManagerW
0x180046d62  mov     rdi, rax
0x180046d65  test    rax, rax
0x180046d68  jnz     short loc_180046D84
0x180046d6a  call    cs:__imp_GetLastError
0x180046d70  test    eax, eax
0x180046d72  jle     short loc_180046D7C
0x180046d74  movzx   eax, ax
0x180046d77  or      eax, 80070000h
0x180046d7c  mov     [rbp+57h+var_50], eax
0x180046d7f  jmp     loc_180046E2F
0x180046d84  mov     r8d, 4; dwDesiredAccess
0x180046d8a  lea     rdx, aWlidsvc_0; "WlidSvc"
0x180046d91  mov     rcx, rdi; hSCManager
0x180046d94  call    cs:__imp_OpenServiceW
0x180046d9a  mov     rbx, rax
0x180046d9d  test    rax, rax
0x180046da0  jnz     short loc_180046DB9
0x180046da2  call    cs:__imp_GetLastError
0x180046da8  test    eax, eax
0x180046daa  jle     short loc_180046DB4
0x180046dac  movzx   eax, ax
0x180046daf  or      eax, 80070000h
0x180046db4  mov     [rbp+57h+var_50], eax
0x180046db7  jmp     short loc_180046E18
0x180046db9  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x180046dbd  mov     rcx, rbx; hService
0x180046dc0  call    cs:__imp_QueryServiceStatus
0x180046dc6  test    eax, eax
0x180046dc8  jz      short loc_180046DA2
0x180046dca  mov     eax, [rbp+57h+ServiceStatus.dwWin32ExitCode]
0x180046dcd  lea     r9, aServiceStatusD; "Service status: dwCheckPoint=0x%x, dwCo"...
0x180046dd4  mov     [rsp+0B0h+var_60], eax
0x180046dd8  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180046ddf  mov     eax, [rbp+57h+ServiceStatus.dwWaitHint]
0x180046de2  mov     r8d, 3Ch ; '<'; unsigned int
0x180046de8  mov     [rsp+0B0h+var_68], eax
0x180046dec  mov     eax, [rbp+57h+ServiceStatus.dwServiceType]
0x180046def  mov     [rsp+0B0h+var_70], eax
0x180046df3  mov     eax, [rbp+57h+ServiceStatus.dwServiceSpecificExitCode]
0x180046df6  lea     ecx, [r8-37h]; unsigned __int8
0x180046dfa  mov     [rsp+0B0h+var_78], eax
0x180046dfe  mov     eax, [rbp+57h+ServiceStatus.dwCurrentState]
0x180046e01  mov     [rsp+0B0h+var_80], eax
0x180046e05  mov     eax, [rbp+57h+ServiceStatus.dwControlsAccepted]
0x180046e08  mov     [rsp+0B0h+var_88], eax
0x180046e0c  mov     eax, [rbp+57h+ServiceStatus.dwCheckPoint]
0x180046e0f  mov     dword ptr [rsp+0B0h+var_90], eax
0x180046e13  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180046e18  mov     rcx, rdi; hSCObject
0x180046e1b  call    cs:__imp_CloseServiceHandle
0x180046e21  test    rbx, rbx
0x180046e24  jz      short loc_180046E2F
0x180046e26  mov     rcx, rbx; hSCObject
0x180046e29  call    cs:__imp_CloseServiceHandle
0x180046e2f  mov     ebx, [rbp+57h+var_50]
0x180046e32  lea     rcx, [rbp+57h+var_48]
0x180046e36  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180046e3b  mov     eax, ebx
0x180046e3d  mov     rcx, [rbp+57h+var_8]
0x180046e41  xor     rcx, rsp; StackCookie
0x180046e44  call    __security_check_cookie
0x180046e49  lea     r11, [rsp+0B0h+var_s0]
0x180046e51  mov     rbx, [r11+10h]
0x180046e55  mov     rdi, [r11+18h]
0x180046e59  mov     rsp, r11
0x180046e5c  pop     rbp
0x180046e5d  retn
```
