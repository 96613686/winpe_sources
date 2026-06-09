# TraceServiceStatus(void)

- ea: `0x180043240`
- end: `0x1800433be`
- name: `?TraceServiceStatus@@YAJXZ`
- size: `382`
- prototype: `__int64(void)`
- caller_count: `41`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180006c70`
- `0x18000ceb0`
- `0x180010cc4`
- `0x180014db0`
- `0x180043478`
- `0x180043944`
- `0x180043d7c`
- `0x1800441f8`
- `0x180044544`
- `0x180044874`
- `0x180044c08`
- `0x180044fbc`
- `0x1800452f4`
- `0x180045648`
- `0x1800459bc`
- `0x180045ccc`
- `0x180046034`
- `0x1800463a0`
- `0x18004670c`
- `0x180046a58`
- `0x180046d90`
- `0x180047148`
- `0x1800474f8`
- `0x18004789c`
- `0x180047c00`
- `0x180047f6c`
- `0x1800482b8`
- `0x180048624`
- `0x18004895c`
- `0x180048c8c`
- `0x180048ff8`
- `0x180049340`
- `0x180049698`
- `0x180049a00`
- `0x180049d94`
- `0x18004a0c4`
- `0x18004a404`
- `0x18004a748`
- `0x18004aa80`
- `0x18004adb0`
- `0x18004b100`

## callees

- `0x1800090c0`
- `0x180009630`
- `0x18000a400`
- `0x18001a0d0`
- `0x180043240`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800432ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043302`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800432ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043302`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800432f4`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800432f4`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800432bc`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800432bc`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004337b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180043389`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004337b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180043389`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180043320`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180043320`

## string_xrefs

- `0x18004327a`: `TraceServiceStatus`
- `0x1800432b3`: `ServicesActive`
- `0x18004332d`: `Service status: dwCheckPoint=0x%x, dwControlsAccepted=0x%x, dwCurrentState=0x%x, dwServiceSpecificExitCode=0x%x, dwServiceType=0x%x, dwWaitHint=0x%x, dwWin32ExitCode=0x%x.`

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
  CTraceFuncW<long>::~CTraceFuncW<long>(v11);
  return v6;
}

```

## disassembly

```asm
0x180043240  mov     [rsp-8+arg_0], rbx
0x180043245  mov     [rsp-8+arg_8], rdi
0x18004324a  push    rbp
0x18004324b  lea     rbp, [rsp-57h]
0x180043250  sub     rsp, 0B0h
0x180043257  mov     rax, cs:__security_cookie
0x18004325e  xor     rax, rsp
0x180043261  mov     [rbp+57h+var_8], rax
0x180043265  xorps   xmm0, xmm0
0x180043268  mov     [rbp+57h+var_50], 0
0x18004326f  xor     r9d, r9d; unsigned int
0x180043272  mov     [rbp+57h+var_38], 0
0x18004327a  lea     rdx, aTraceservicest; "TraceServiceStatus"
0x180043281  mov     [rbp+57h+var_30], 0
0x180043289  lea     rax, [rbp+57h+var_50]
0x18004328d  mov     [rbp+57h+var_48], rdx
0x180043291  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x180043295  lea     r8d, [r9+23h]; char *
0x180043299  mov     [rbp+57h+var_40], rax
0x18004329d  lea     rcx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800432a4  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800432a8  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800432ad  mov     r8d, 80000000h; dwDesiredAccess
0x1800432b3  lea     rdx, DatabaseName; "ServicesActive"
0x1800432ba  xor     ecx, ecx; lpMachineName
0x1800432bc  call    cs:__imp_OpenSCManagerW
0x1800432c2  mov     rdi, rax
0x1800432c5  test    rax, rax
0x1800432c8  jnz     short loc_1800432E4
0x1800432ca  call    cs:__imp_GetLastError
0x1800432d0  test    eax, eax
0x1800432d2  jle     short loc_1800432DC
0x1800432d4  movzx   eax, ax
0x1800432d7  or      eax, 80070000h
0x1800432dc  mov     [rbp+57h+var_50], eax
0x1800432df  jmp     loc_18004338F
0x1800432e4  mov     r8d, 4; dwDesiredAccess
0x1800432ea  lea     rdx, aWlidsvc_0; "WlidSvc"
0x1800432f1  mov     rcx, rdi; hSCManager
0x1800432f4  call    cs:__imp_OpenServiceW
0x1800432fa  mov     rbx, rax
0x1800432fd  test    rax, rax
0x180043300  jnz     short loc_180043319
0x180043302  call    cs:__imp_GetLastError
0x180043308  test    eax, eax
0x18004330a  jle     short loc_180043314
0x18004330c  movzx   eax, ax
0x18004330f  or      eax, 80070000h
0x180043314  mov     [rbp+57h+var_50], eax
0x180043317  jmp     short loc_180043378
0x180043319  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x18004331d  mov     rcx, rbx; hService
0x180043320  call    cs:__imp_QueryServiceStatus
0x180043326  test    eax, eax
0x180043328  jz      short loc_180043302
0x18004332a  mov     eax, [rbp+57h+ServiceStatus.dwWin32ExitCode]
0x18004332d  lea     r9, aServiceStatusD; "Service status: dwCheckPoint=0x%x, dwCo"...
0x180043334  mov     [rsp+0B0h+var_60], eax
0x180043338  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004333f  mov     eax, [rbp+57h+ServiceStatus.dwWaitHint]
0x180043342  mov     r8d, 3Ch ; '<'; unsigned int
0x180043348  mov     [rsp+0B0h+var_68], eax
0x18004334c  mov     eax, [rbp+57h+ServiceStatus.dwServiceType]
0x18004334f  mov     [rsp+0B0h+var_70], eax
0x180043353  mov     eax, [rbp+57h+ServiceStatus.dwServiceSpecificExitCode]
0x180043356  lea     ecx, [r8-37h]; unsigned __int8
0x18004335a  mov     [rsp+0B0h+var_78], eax
0x18004335e  mov     eax, [rbp+57h+ServiceStatus.dwCurrentState]
0x180043361  mov     [rsp+0B0h+var_80], eax
0x180043365  mov     eax, [rbp+57h+ServiceStatus.dwControlsAccepted]
0x180043368  mov     [rsp+0B0h+var_88], eax
0x18004336c  mov     eax, [rbp+57h+ServiceStatus.dwCheckPoint]
0x18004336f  mov     dword ptr [rsp+0B0h+var_90], eax
0x180043373  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180043378  mov     rcx, rdi; hSCObject
0x18004337b  call    cs:__imp_CloseServiceHandle
0x180043381  test    rbx, rbx
0x180043384  jz      short loc_18004338F
0x180043386  mov     rcx, rbx; hSCObject
0x180043389  call    cs:__imp_CloseServiceHandle
0x18004338f  mov     ebx, [rbp+57h+var_50]
0x180043392  lea     rcx, [rbp+57h+var_48]
0x180043396  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18004339b  mov     eax, ebx
0x18004339d  mov     rcx, [rbp+57h+var_8]
0x1800433a1  xor     rcx, rsp; StackCookie
0x1800433a4  call    __security_check_cookie
0x1800433a9  lea     r11, [rsp+0B0h+var_s0]
0x1800433b1  mov     rbx, [r11+10h]
0x1800433b5  mov     rdi, [r11+18h]
0x1800433b9  mov     rsp, r11
0x1800433bc  pop     rbp
0x1800433bd  retn
```
