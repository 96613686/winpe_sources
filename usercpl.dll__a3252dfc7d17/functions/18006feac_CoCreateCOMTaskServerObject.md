# CoCreateCOMTaskServerObject

- ea: `0x18006feac`
- end: `0x1800702c2`
- name: `CoCreateCOMTaskServerObject`
- size: `1046`
- prototype: `__int64 __fastcall(int, int, int, int, int, LPVOID *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800702c8`

## callees

- `0x180002ac4`
- `0x18000328d`
- `0x180003299`
- `0x1800032a5`
- `0x180003529`
- `0x180005714`
- `0x180005ca8`
- `0x180006a74`
- `0x180007458`
- `0x18000788c`
- `0x180008f00`
- `0x18006f474`
- `0x18006f534`
- `0x18006feac`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18006ffcc`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18006ffcc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180070042`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180070201`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180070042`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180070201`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180070034`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800701f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180070034`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800701f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800700ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800700ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007007d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070124`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800701bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800701d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007024a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007007d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070124`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800701bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800701d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007024a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800700a4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007018b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800700a4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007018b`

## string_xrefs

- `0x18006ffbe`: `Global\ShellCreateObjectTaskReadyEvent`
- `0x1800700d3`: `Global\ShellCreateObjectTaskReadyEvent`
- `0x18006fff5`: `shell\lib\comtaskserverutil.cpp`
- `0x180070012`: `shell\lib\comtaskserverutil.cpp`
- `0x180070104`: `shell\lib\comtaskserverutil.cpp`
- `0x18007019b`: `shell\lib\comtaskserverutil.cpp`
- `0x180070225`: `shell\lib\comtaskserverutil.cpp`
- `0x18006ff7e`: `CoCreateCOMTaskServerObject`

## pseudocode

```c
__int64 __fastcall CoCreateCOMTaskServerObject(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, LPVOID *a6)
{
  LPVOID *v6; // rsi
  wil::details *v7; // rcx
  HANDLE v8; // rbx
  int v9; // edi
  int LastErrorFailHr; // eax
  __int64 v11; // rdx
  void *v12; // rbx
  HANDLE ProcessHeap; // rax
  DWORD v15; // eax
  unsigned int v16; // r8d
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  HRESULT Instance; // eax
  wil::details *v21; // rcx
  HANDLE Event; // rbx
  const unsigned __int16 *v23; // rcx
  int v24; // eax
  __int64 v25; // r8
  const char *v26; // r9
  DWORD v27; // eax
  unsigned int v28; // r8d
  const char *v29; // r9
  HRESULT v30; // eax
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  void *v35; // rbx
  HANDLE v36; // rax
  __int64 v37; // r8
  const char *v38; // r9
  int ppv; // [rsp+20h] [rbp-60h]
  int ppva; // [rsp+20h] [rbp-60h]
  int ppvb; // [rsp+20h] [rbp-60h]
  int v42; // [rsp+30h] [rbp-50h] BYREF
  const char *v43; // [rsp+38h] [rbp-48h]
  LPVOID lpMem; // [rsp+40h] [rbp-40h]
  char v45; // [rsp+48h] [rbp-38h]
  _QWORD v46[3]; // [rsp+50h] [rbp-30h] BYREF
  int v47; // [rsp+68h] [rbp-18h]
  int *v48; // [rsp+70h] [rbp-10h]
  char v49; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  LPVOID Context; // [rsp+B0h] [rbp+30h] BYREF
  WINBOOL fPending; // [rsp+B8h] [rbp+38h] BYREF

  v6 = a6;
  Context = 0;
  fPending = 0;
  *a6 = 0;
  if ( InitOnceBeginInitialize_0(&`CoCreateInstanceAsSystemTelemetry::Instance'::`2'::wrapper, 0, &fPending, &Context)
    && fPending )
  {
    qword_1800A34E8 = 0;
    qword_1800A34E0 = (__int64)&TaskFlowTelemetry::`vftable';
    Context = &qword_1800A34E0;
    byte_1800A34F0 = 0;
    dword_1800A34F4 = 0;
    atexit(_lambda_1ed552633946a27b818d04b3bf9896b5_::_lambda_invoker_cdecl_);
    qword_1800A34E8 = (__int64)CoCreateInstanceAsSystemLogging::Provider();
    byte_1800A34F0 = 0;
    dword_1800A34F4 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_1800A34E0 + 8))(&qword_1800A34E0);
    InitOnceComplete_0(&`CoCreateInstanceAsSystemTelemetry::Instance'::`2'::wrapper, 0, &qword_1800A34E0);
  }
  v45 = 0;
  v43 = "CoCreateCOMTaskServerObject";
  v46[1] = Context;
  v48 = &v42;
  v42 = 0;
  lpMem = 0;
  v46[0] = 0;
  v46[2] = 0;
  v47 = 0;
  v49 = 0;
  wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)v46);
  v8 = OpenEventW(0x100002u, 0, L"Global\\ShellCreateObjectTaskReadyEvent");
  if ( v8 )
  {
    v9 = 0;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v7);
    v9 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 && LastErrorFailHr != -2147024894 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x47,
        (unsigned int)"shell\\lib\\comtaskserverutil.cpp",
        (const char *)(unsigned int)LastErrorFailHr,
        ppv);
      v11 = 96;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"shell\\lib\\comtaskserverutil.cpp",
        (const char *)(unsigned int)v9,
        ppva);
LABEL_10:
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v46);
      if ( v45 )
      {
        v12 = lpMem;
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v12);
      }
      return (unsigned int)v9;
    }
    v8 = 0;
  }
  if ( v9 >= 0 )
  {
    v15 = WaitForSingleObjectEx_0(v8, 0x7530u, 0);
    if ( v15 != 258 )
    {
      if ( v15 )
        wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB0F, v16, v17);
    }
  }
  if ( v8 && !CloseHandle(v8) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
  Instance = CoCreateInstance(&CLSID_CreateObjectAsSystem, 0, 4u, &GUID_75121952_e0d0_43e5_9380_1d80483acf72, v6);
  v9 = Instance;
  if ( Instance < 0 )
  {
    if ( Instance != -2147221164 )
    {
      v11 = 100;
      goto LABEL_9;
    }
    Event = CreateEventExW_0(0, L"Global\\ShellCreateObjectTaskReadyEvent", 1u, 0x1F0003u);
    if ( Event )
    {
      GetLastError();
    }
    else
    {
      v9 = wil::details::GetLastErrorFailHr(v21);
      Event = 0;
      if ( v9 < 0 )
      {
        v11 = 107;
        goto LABEL_9;
      }
    }
    v24 = RunTaskSchedulerTask(v23);
    v9 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6E,
        (unsigned int)"shell\\lib\\comtaskserverutil.cpp",
        (const char *)(unsigned int)v24,
        ppva);
      if ( Event && !CloseHandle(Event) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
      goto LABEL_10;
    }
    v27 = WaitForSingleObjectEx_0(Event, 0x7530u, 0);
    if ( v27 == 258 )
    {
      v9 = -2147023436;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6F,
        (unsigned int)"shell\\lib\\comtaskserverutil.cpp",
        (const char *)0x800705B4LL,
        ppva);
      if ( Event && !CloseHandle(Event) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
      goto LABEL_10;
    }
    if ( v27 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB0F, v28, v29);
    v30 = CoCreateInstance(&CLSID_CreateObjectAsSystem, 0, 4u, &GUID_75121952_e0d0_43e5_9380_1d80483acf72, v6);
    v9 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x71,
        (unsigned int)"shell\\lib\\comtaskserverutil.cpp",
        (const char *)(unsigned int)v30,
        ppvb);
      if ( Event && !CloseHandle(Event) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
      goto LABEL_10;
    }
    if ( Event && !CloseHandle(Event) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
  }
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v46);
  if ( v45 )
  {
    v35 = lpMem;
    v36 = GetProcessHeap();
    HeapFree(v36, 0, v35);
  }
  return 0;
}

```

## disassembly

```asm
0x18006feac  mov     rax, rsp
0x18006feaf  mov     [rax+8], rbx
0x18006feb3  mov     [rax+10h], rsi
0x18006feb7  mov     [rax+20h], r9d
0x18006febb  mov     [rax+18h], r8
0x18006febf  push    rbp
0x18006fec0  push    rdi
0x18006fec1  push    r14
0x18006fec3  mov     rbp, rsp
0x18006fec6  sub     rsp, 80h
0x18006fecd  mov     rsi, [rbp+arg_28]
0x18006fed1  lea     r9, [rbp+Context]; lpContext
0x18006fed5  xor     r14d, r14d
0x18006fed8  lea     r8, [rbp+fPending]; fPending
0x18006fedc  xor     edx, edx; dwFlags
0x18006fede  mov     [rbp+Context], r14
0x18006fee2  lea     rcx, ?wrapper@?1??Instance@CoCreateInstanceAsSystemTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VCoCreateInstanceAsSystemTelemetry@@@details@wil@@A; lpInitOnce
0x18006fee9  mov     [rbp+fPending], r14d
0x18006feed  mov     [rsi], r14
0x18006fef0  call    InitOnceBeginInitialize_0
0x18006fef5  test    eax, eax
0x18006fef7  jz      loc_18006FF7E
0x18006fefd  cmp     [rbp+fPending], r14d
0x18006ff01  jz      short loc_18006FF7E
0x18006ff03  lea     rax, ??_7TaskFlowTelemetry@@6B@; const TaskFlowTelemetry::`vftable'
0x18006ff0a  mov     cs:qword_1800A34E8, r14
0x18006ff11  lea     rbx, qword_1800A34E0
0x18006ff18  mov     cs:qword_1800A34E0, rax
0x18006ff1f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ed552633946a27b818d04b3bf9896b5_@@CA@XZ; void (__cdecl *)()
0x18006ff26  mov     [rbp+Context], rbx
0x18006ff2a  mov     cs:byte_1800A34F0, r14b
0x18006ff31  mov     cs:dword_1800A34F4, r14d
0x18006ff38  call    atexit
0x18006ff3d  call    ?Provider@CoCreateInstanceAsSystemLogging@@SAPEBU_tlgProvider_t@@XZ; CoCreateInstanceAsSystemLogging::Provider(void)
0x18006ff42  mov     cs:qword_1800A34E8, rax
0x18006ff49  mov     rcx, rbx
0x18006ff4c  mov     rax, cs:qword_1800A34E0
0x18006ff53  mov     cs:byte_1800A34F0, r14b
0x18006ff5a  mov     cs:dword_1800A34F4, 1
0x18006ff64  mov     rax, [rax+8]
0x18006ff68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ff6d  mov     r8, rbx; lpContext
0x18006ff70  lea     rcx, ?wrapper@?1??Instance@CoCreateInstanceAsSystemTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VCoCreateInstanceAsSystemTelemetry@@@details@wil@@A; lpInitOnce
0x18006ff77  xor     edx, edx; dwFlags
0x18006ff79  call    InitOnceComplete_0
0x18006ff7e  lea     rax, aCocreatecomtas; "CoCreateCOMTaskServerObject"
0x18006ff85  mov     [rbp+var_38], r14b
0x18006ff89  mov     [rbp+var_48], rax
0x18006ff8d  lea     rcx, [rbp+var_30]; this
0x18006ff91  mov     rax, [rbp+Context]
0x18006ff95  mov     [rbp+var_28], rax
0x18006ff99  lea     rax, [rbp+var_50]
0x18006ff9d  mov     [rbp+var_10], rax
0x18006ffa1  mov     [rbp+var_50], r14d
0x18006ffa5  mov     [rbp+lpMem], r14
0x18006ffa9  mov     [rbp+var_30], r14
0x18006ffad  mov     [rbp+var_20], r14
0x18006ffb1  mov     [rbp+var_18], r14d
0x18006ffb5  mov     [rbp+var_8], r14b
0x18006ffb9  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18006ffbe  lea     r8, Name; "Global\\ShellCreateObjectTaskReadyEvent"
0x18006ffc5  xor     edx, edx; bInheritHandle
0x18006ffc7  mov     ecx, 100002h; dwDesiredAccess
0x18006ffcc  call    cs:__imp_OpenEventW
0x18006ffd2  mov     rbx, rax
0x18006ffd5  test    rax, rax
0x18006ffd8  jz      short loc_18006FFDF
0x18006ffda  mov     edi, r14d
0x18006ffdd  jmp     short loc_180070052
0x18006ffdf  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18006ffe4  mov     edi, eax
0x18006ffe6  test    eax, eax
0x18006ffe8  jns     short loc_18007004F
0x18006ffea  cmp     eax, 80070002h
0x18006ffef  jz      short loc_18007004F
0x18006fff1  mov     rcx, [rbp+18h]; this
0x18006fff5  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x18006fffc  mov     r9d, eax; char *
0x18006ffff  mov     edx, 47h ; 'G'; void *
0x180070004  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180070009  mov     edx, 60h ; '`'; void *
0x18007000e  mov     rcx, [rbp+18h]; this
0x180070012  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x180070019  mov     r9d, edi; char *
0x18007001c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180070021  lea     rcx, [rbp+var_30]; this
0x180070025  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18007002a  cmp     [rbp+var_38], r14b
0x18007002e  jz      short loc_180070048
0x180070030  mov     rbx, [rbp+lpMem]
0x180070034  call    cs:__imp_GetProcessHeap
0x18007003a  mov     r8, rbx; lpMem
0x18007003d  xor     edx, edx; dwFlags
0x18007003f  mov     rcx, rax; hHeap
0x180070042  call    cs:__imp_HeapFree
0x180070048  mov     eax, edi
0x18007004a  jmp     loc_180070209
0x18007004f  mov     rbx, r14
0x180070052  test    edi, edi
0x180070054  js      short loc_180070075
0x180070056  xor     r8d, r8d; bAlertable
0x180070059  mov     edx, 7530h; dwMilliseconds
0x18007005e  mov     rcx, rbx; hHandle
0x180070061  call    WaitForSingleObjectEx_0
0x180070066  cmp     eax, 102h
0x18007006b  jz      short loc_180070075
0x18007006d  test    eax, eax
0x18007006f  jnz     loc_180070295
0x180070075  test    rbx, rbx
0x180070078  jz      short loc_18007008B
0x18007007a  mov     rcx, rbx; hObject
0x18007007d  call    cs:__imp_CloseHandle
0x180070083  test    eax, eax
0x180070085  jz      loc_1800702A4
0x18007008b  xor     edx, edx; pUnkOuter
0x18007008d  mov     qword ptr [rsp+80h+ppv], rsi; int
0x180070092  lea     r9, _GUID_75121952_e0d0_43e5_9380_1d80483acf72; riid
0x180070099  lea     rcx, CLSID_CreateObjectAsSystem; rclsid
0x1800700a0  lea     r8d, [rdx+4]; dwClsContext
0x1800700a4  call    cs:__imp_CoCreateInstance
0x1800700aa  mov     edi, eax
0x1800700ac  test    eax, eax
0x1800700ae  jns     short loc_1800700C1
0x1800700b0  cmp     eax, 80040154h
0x1800700b5  jz      short loc_1800700CD
0x1800700b7  mov     edx, 64h ; 'd'
0x1800700bc  jmp     loc_18007000E
0x1800700c1  cmp     edi, 80040154h
0x1800700c7  jnz     loc_1800701E0
0x1800700cd  mov     r9d, 1F0003h; dwDesiredAccess
0x1800700d3  lea     rdx, Name; "Global\\ShellCreateObjectTaskReadyEvent"
0x1800700da  mov     r8d, 1; dwFlags
0x1800700e0  xor     ecx, ecx; lpEventAttributes
0x1800700e2  call    CreateEventExW_0
0x1800700e7  mov     rbx, rax
0x1800700ea  test    rax, rax
0x1800700ed  jz      short loc_180070137
0x1800700ef  call    cs:__imp_GetLastError
0x1800700f5  call    ?RunTaskSchedulerTask@@YAJPEBG@Z; RunTaskSchedulerTask(ushort const *)
0x1800700fa  mov     edi, eax
0x1800700fc  test    eax, eax
0x1800700fe  jns     short loc_18007014F
0x180070100  mov     rcx, [rbp+18h]; this
0x180070104  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x18007010b  mov     r9d, eax; char *
0x18007010e  mov     edx, 6Eh ; 'n'; void *
0x180070113  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180070118  test    rbx, rbx
0x18007011b  jz      loc_180070021
0x180070121  mov     rcx, rbx; hObject
0x180070124  call    cs:__imp_CloseHandle
0x18007012a  test    eax, eax
0x18007012c  jz      loc_180070268
0x180070132  jmp     loc_180070021
0x180070137  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18007013c  mov     edi, eax
0x18007013e  mov     rbx, r14
0x180070141  test    eax, eax
0x180070143  jns     short loc_1800700F5
0x180070145  mov     edx, 6Bh ; 'k'
0x18007014a  jmp     loc_18007000E
0x18007014f  xor     r8d, r8d; bAlertable
0x180070152  mov     edx, 7530h; dwMilliseconds
0x180070157  mov     rcx, rbx; hHandle
0x18007015a  call    WaitForSingleObjectEx_0
0x18007015f  cmp     eax, 102h
0x180070164  jz      loc_180070221
0x18007016a  test    eax, eax
0x18007016c  jnz     loc_1800702B3
0x180070172  lea     r9, _GUID_75121952_e0d0_43e5_9380_1d80483acf72; riid
0x180070179  mov     qword ptr [rsp+80h+ppv], rsi; int
0x18007017e  xor     edx, edx; pUnkOuter
0x180070180  lea     r8d, [rax+4]; dwClsContext
0x180070184  lea     rcx, CLSID_CreateObjectAsSystem; rclsid
0x18007018b  call    cs:__imp_CoCreateInstance
0x180070191  mov     edi, eax
0x180070193  test    eax, eax
0x180070195  jns     short loc_1800701CE
0x180070197  mov     rcx, [rbp+18h]; this
0x18007019b  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x1800701a2  mov     r9d, eax; char *
0x1800701a5  mov     edx, 71h ; 'q'; void *
0x1800701aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800701af  test    rbx, rbx
0x1800701b2  jz      loc_180070021
0x1800701b8  mov     rcx, rbx; hObject
0x1800701bb  call    cs:__imp_CloseHandle
0x1800701c1  test    eax, eax
0x1800701c3  jz      loc_180070277
0x1800701c9  jmp     loc_180070021
0x1800701ce  test    rbx, rbx
0x1800701d1  jz      short loc_1800701E0
0x1800701d3  mov     rcx, rbx; hObject
0x1800701d6  call    cs:__imp_CloseHandle
0x1800701dc  test    eax, eax
0x1800701de  jz      short loc_180070259
0x1800701e0  lea     rcx, [rbp+var_30]; this
0x1800701e4  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800701e9  cmp     [rbp+var_38], r14b
0x1800701ed  jz      short loc_180070207
0x1800701ef  mov     rbx, [rbp+lpMem]
0x1800701f3  call    cs:__imp_GetProcessHeap
0x1800701f9  mov     r8, rbx; lpMem
0x1800701fc  xor     edx, edx; dwFlags
0x1800701fe  mov     rcx, rax; hHeap
0x180070201  call    cs:__imp_HeapFree
0x180070207  xor     eax, eax
0x180070209  lea     r11, [rsp+80h+var_s0]
0x180070211  mov     rbx, [r11+20h]
0x180070215  mov     rsi, [r11+28h]
0x180070219  mov     rsp, r11
0x18007021c  pop     r14
0x18007021e  pop     rdi
0x18007021f  pop     rbp
0x180070220  retn
0x180070221  mov     rcx, [rbp+18h]; this
0x180070225  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x18007022c  mov     edi, 800705B4h
0x180070231  mov     edx, 6Fh ; 'o'; void *
0x180070236  mov     r9d, edi; char *
0x180070239  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007023e  test    rbx, rbx
0x180070241  jz      loc_180070021
0x180070247  mov     rcx, rbx; hObject
0x18007024a  call    cs:__imp_CloseHandle
0x180070250  test    eax, eax
0x180070252  jz      short loc_180070286
0x180070254  jmp     loc_180070021
0x180070259  mov     rcx, [rbp+18h]; this
0x18007025d  mov     edx, 0A0Bh; void *
0x180070262  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180070268  mov     rcx, [rbp+18h]; this
0x18007026c  mov     edx, 0A0Bh; void *
0x180070271  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180070277  mov     rcx, [rbp+18h]; this
0x18007027b  mov     edx, 0A0Bh; void *
0x180070280  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180070286  mov     rcx, [rbp+18h]; this
0x18007028a  mov     edx, 0A0Bh; void *
0x18007028f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180070295  mov     rcx, [rbp+18h]; this
0x180070299  mov     edx, 0B0Fh; void *
0x18007029e  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800702a4  mov     rcx, [rbp+18h]; this
0x1800702a8  mov     edx, 0A0Bh; void *
0x1800702ad  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800702b3  mov     rcx, [rbp+18h]; this
0x1800702b7  mov     edx, 0B0Fh; void *
0x1800702bc  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```
