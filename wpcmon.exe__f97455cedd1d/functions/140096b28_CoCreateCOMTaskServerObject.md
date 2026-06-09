# CoCreateCOMTaskServerObject

- ea: `0x140096b28`
- end: `0x140096f25`
- name: `CoCreateCOMTaskServerObject`
- size: `1021`
- prototype: `__int64 __fastcall(int, int, int, int, int, LPVOID *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140096f2c`

## callees

- `0x140004833`
- `0x140004863`
- `0x14000486f`
- `0x14000487b`
- `0x140005a84`
- `0x140006536`
- `0x140007565`
- `0x140007571`
- `0x14000bd20`
- `0x14000dbbc`
- `0x140010a98`
- `0x140011fec`
- `0x140016854`
- `0x14001b510`
- `0x140096174`
- `0x140096264`
- `0x140096b28`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x140096c9a`
- `KERNEL32!GetProcessHeap` at `0x140096e5a`
- `KERNEL32!GetProcessHeap` at `0x140096c9a`
- `KERNEL32!GetProcessHeap` at `0x140096e5a`
- `KERNEL32!CloseHandle` at `0x140096ce3`
- `KERNEL32!CloseHandle` at `0x140096d8c`
- `KERNEL32!CloseHandle` at `0x140096e22`
- `KERNEL32!CloseHandle` at `0x140096e3d`
- `KERNEL32!CloseHandle` at `0x140096eb1`
- `KERNEL32!CloseHandle` at `0x140096ce3`
- `KERNEL32!CloseHandle` at `0x140096d8c`
- `KERNEL32!CloseHandle` at `0x140096e22`
- `KERNEL32!CloseHandle` at `0x140096e3d`
- `KERNEL32!CloseHandle` at `0x140096eb1`
- `KERNEL32!HeapFree` at `0x140096ca8`
- `KERNEL32!HeapFree` at `0x140096e68`
- `KERNEL32!HeapFree` at `0x140096ca8`
- `KERNEL32!HeapFree` at `0x140096e68`

## string_xrefs

- `0x140096c5e`: `shell\lib\comtaskserverutil.cpp`
- `0x140096c7b`: `shell\lib\comtaskserverutil.cpp`
- `0x140096d6f`: `shell\lib\comtaskserverutil.cpp`
- `0x140096e05`: `shell\lib\comtaskserverutil.cpp`
- `0x140096e94`: `shell\lib\comtaskserverutil.cpp`
- `0x140096c25`: `Global\ShellCreateObjectTaskReadyEvent`
- `0x140096d42`: `Global\ShellCreateObjectTaskReadyEvent`
- `0x140096c02`: `CoCreateCOMTaskServerObject`

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
  unsigned int v18; // r8d
  const char *v19; // r9
  HRESULT Instance_0; // eax
  wil::details *v21; // rcx
  HANDLE Event; // rbx
  const unsigned __int16 *v23; // rcx
  int v24; // eax
  unsigned int v25; // r8d
  const char *v26; // r9
  DWORD v27; // eax
  unsigned int v28; // r8d
  const char *v29; // r9
  HRESULT v30; // eax
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  void *v35; // rbx
  HANDLE v36; // rax
  unsigned int v37; // r8d
  const char *v38; // r9
  int ppv; // [rsp+20h] [rbp-60h]
  int ppva; // [rsp+20h] [rbp-60h]
  int ppvb; // [rsp+20h] [rbp-60h]
  int v42; // [rsp+30h] [rbp-50h] BYREF
  const char *v43; // [rsp+38h] [rbp-48h]
  LPVOID lpMem; // [rsp+40h] [rbp-40h]
  char v45; // [rsp+48h] [rbp-38h]
  _BYTE v46[48]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  LPVOID Context; // [rsp+B0h] [rbp+30h] BYREF
  WINBOOL fPending; // [rsp+B8h] [rbp+38h] BYREF

  v6 = a6;
  *a6 = 0;
  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize_0(&`CoCreateInstanceAsSystemTelemetry::Instance'::`2'::wrapper, 0, &fPending, &Context)
    && fPending )
  {
    Context = &qword_1401111E8;
    qword_1401111F0 = 0;
    byte_1401111F8 = 0;
    dword_1401111FC = 0;
    qword_1401111E8 = (__int64)&wil::details::FeatureLogging::`vftable';
    atexit(_lambda_1ed552633946a27b818d04b3bf9896b5_::_lambda_invoker_cdecl_);
    qword_1401111F0 = (__int64)CoCreateInstanceAsSystemLogging::Provider();
    byte_1401111F8 = 0;
    dword_1401111FC = 1;
    (*(void (__fastcall **)(__int64 *))(qword_1401111E8 + 8))(&qword_1401111E8);
    InitOnceComplete_0(&`CoCreateInstanceAsSystemTelemetry::Instance'::`2'::wrapper, 0, &qword_1401111E8);
  }
  v45 = 0;
  v42 = 0;
  v43 = "CoCreateCOMTaskServerObject";
  lpMem = 0;
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)v46,
    (struct wil::details::IFailureCallback *)Context,
    (struct wil::CallContextInfo *)&v42,
    1);
  v8 = OpenEventW_0(0x100002u, 0, L"Global\\ShellCreateObjectTaskReadyEvent");
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
  Instance_0 = CoCreateInstance_0(&CLSID_CreateObjectAsSystem, 0, 4u, &GUID_75121952_e0d0_43e5_9380_1d80483acf72, v6);
  v9 = Instance_0;
  if ( Instance_0 < 0 )
  {
    if ( Instance_0 != -2147221164 )
    {
      v11 = 100;
      goto LABEL_9;
    }
    Event = CreateEventExW_0(0, L"Global\\ShellCreateObjectTaskReadyEvent", 1u, 0x1F0003u);
    if ( Event )
    {
      GetLastError_0();
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
    v30 = CoCreateInstance_0(&CLSID_CreateObjectAsSystem, 0, 4u, &GUID_75121952_e0d0_43e5_9380_1d80483acf72, v6);
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
0x140096b28  mov     rax, rsp
0x140096b2b  mov     [rax+8], rbx
0x140096b2f  mov     [rax+10h], rsi
0x140096b33  mov     [rax+20h], r9d
0x140096b37  mov     [rax+18h], r8
0x140096b3b  push    rbp
0x140096b3c  push    rdi
0x140096b3d  push    r14
0x140096b3f  mov     rbp, rsp
0x140096b42  sub     rsp, 80h
0x140096b49  xor     r14d, r14d
0x140096b4c  mov     rsi, [rbp+arg_28]
0x140096b50  mov     [rsi], r14
0x140096b53  mov     [rbp+Context], r14
0x140096b57  mov     [rbp+fPending], r14d
0x140096b5b  lea     r9, [rbp+Context]; lpContext
0x140096b5f  lea     r8, [rbp+fPending]; fPending
0x140096b63  xor     edx, edx; dwFlags
0x140096b65  lea     rcx, ?wrapper@?1??Instance@CoCreateInstanceAsSystemTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VCoCreateInstanceAsSystemTelemetry@@@details@wil@@A; lpInitOnce
0x140096b6c  call    InitOnceBeginInitialize_0
0x140096b71  test    eax, eax
0x140096b73  jz      loc_140096BFA
0x140096b79  cmp     [rbp+fPending], r14d
0x140096b7d  jz      short loc_140096BFA
0x140096b7f  lea     rbx, qword_1401111E8
0x140096b86  mov     [rbp+Context], rbx
0x140096b8a  mov     cs:qword_1401111F0, r14
0x140096b91  mov     cs:byte_1401111F8, r14b
0x140096b98  mov     cs:dword_1401111FC, r14d
0x140096b9f  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x140096ba6  mov     cs:qword_1401111E8, rax
0x140096bad  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ed552633946a27b818d04b3bf9896b5_@@CA@XZ; void (__cdecl *)()
0x140096bb4  call    atexit
0x140096bb9  call    ?Provider@CoCreateInstanceAsSystemLogging@@SAPEBU_tlgProvider_t@@XZ; CoCreateInstanceAsSystemLogging::Provider(void)
0x140096bbe  mov     cs:qword_1401111F0, rax
0x140096bc5  mov     cs:byte_1401111F8, r14b
0x140096bcc  mov     cs:dword_1401111FC, 1
0x140096bd6  mov     rax, cs:qword_1401111E8
0x140096bdd  mov     rcx, rbx
0x140096be0  mov     rax, [rax+8]
0x140096be4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096be9  mov     r8, rbx; lpContext
0x140096bec  xor     edx, edx; dwFlags
0x140096bee  lea     rcx, ?wrapper@?1??Instance@CoCreateInstanceAsSystemTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VCoCreateInstanceAsSystemTelemetry@@@details@wil@@A; lpInitOnce
0x140096bf5  call    InitOnceComplete_0
0x140096bfa  mov     [rbp+var_38], r14b
0x140096bfe  mov     [rbp+var_50], r14d
0x140096c02  lea     rax, aCocreatecomtas; "CoCreateCOMTaskServerObject"
0x140096c09  mov     [rbp+var_48], rax
0x140096c0d  mov     [rbp+lpMem], r14
0x140096c11  mov     r9b, 1; bool
0x140096c14  lea     r8, [rbp+var_50]; struct wil::CallContextInfo *
0x140096c18  mov     rdx, [rbp+Context]; struct wil::details::IFailureCallback *
0x140096c1c  lea     rcx, [rbp+var_30]; this
0x140096c20  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x140096c25  lea     r8, Name; "Global\\ShellCreateObjectTaskReadyEvent"
0x140096c2c  xor     edx, edx; bInheritHandle
0x140096c2e  mov     ecx, 100002h; dwDesiredAccess
0x140096c33  call    OpenEventW_0
0x140096c38  mov     rbx, rax
0x140096c3b  test    rax, rax
0x140096c3e  jz      short loc_140096C45
0x140096c40  mov     edi, r14d
0x140096c43  jmp     short loc_140096CB8
0x140096c45  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140096c4a  mov     edi, eax
0x140096c4c  test    eax, eax
0x140096c4e  jns     short loc_140096CB5
0x140096c50  cmp     eax, 80070002h
0x140096c55  jz      short loc_140096CB5
0x140096c57  mov     rcx, [rbp+18h]; this
0x140096c5b  mov     r9d, eax; char *
0x140096c5e  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x140096c65  mov     edx, 47h ; 'G'; void *
0x140096c6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140096c6f  mov     edx, 60h ; '`'; void *
0x140096c74  mov     rcx, [rbp+18h]; this
0x140096c78  mov     r9d, edi; char *
0x140096c7b  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x140096c82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140096c87  lea     rcx, [rbp+var_30]; this
0x140096c8b  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x140096c90  cmp     [rbp+var_38], r14b
0x140096c94  jz      short loc_140096CAE
0x140096c96  mov     rbx, [rbp+lpMem]
0x140096c9a  call    cs:__imp_GetProcessHeap
0x140096ca0  mov     r8, rbx; lpMem
0x140096ca3  xor     edx, edx; dwFlags
0x140096ca5  mov     rcx, rax; hHeap
0x140096ca8  call    cs:__imp_HeapFree
0x140096cae  mov     eax, edi
0x140096cb0  jmp     loc_140096E70
0x140096cb5  mov     rbx, r14
0x140096cb8  test    edi, edi
0x140096cba  js      short loc_140096CDB
0x140096cbc  xor     r8d, r8d; bAlertable
0x140096cbf  mov     edx, 7530h; dwMilliseconds
0x140096cc4  mov     rcx, rbx; hHandle
0x140096cc7  call    WaitForSingleObjectEx_0
0x140096ccc  cmp     eax, 102h
0x140096cd1  jz      short loc_140096CDB
0x140096cd3  test    eax, eax
0x140096cd5  jnz     loc_140096EFC
0x140096cdb  test    rbx, rbx
0x140096cde  jz      short loc_140096CF5
0x140096ce0  mov     rcx, rbx; hObject
0x140096ce3  call    cs:__imp_CloseHandle
0x140096ce9  mov     rcx, [rbp+18h]; this
0x140096ced  test    eax, eax
0x140096cef  jz      loc_140096F0B
0x140096cf5  mov     qword ptr [rsp+80h+ppv], rsi; int
0x140096cfa  lea     r9, _GUID_75121952_e0d0_43e5_9380_1d80483acf72; riid
0x140096d01  xor     edx, edx; pUnkOuter
0x140096d03  lea     r8d, [rdx+4]; dwClsContext
0x140096d07  lea     rcx, CLSID_CreateObjectAsSystem; rclsid
0x140096d0e  call    CoCreateInstance_0
0x140096d13  mov     edi, eax
0x140096d15  test    eax, eax
0x140096d17  jns     short loc_140096D2A
0x140096d19  cmp     eax, 80040154h
0x140096d1e  jz      short loc_140096D36
0x140096d20  mov     edx, 64h ; 'd'
0x140096d25  jmp     loc_140096C74
0x140096d2a  cmp     edi, 80040154h
0x140096d30  jnz     loc_140096E47
0x140096d36  mov     r9d, 1F0003h; dwDesiredAccess
0x140096d3c  mov     r8d, 1; dwFlags
0x140096d42  lea     rdx, Name; "Global\\ShellCreateObjectTaskReadyEvent"
0x140096d49  xor     ecx, ecx; lpEventAttributes
0x140096d4b  call    CreateEventExW_0
0x140096d50  mov     rbx, rax
0x140096d53  test    rax, rax
0x140096d56  jz      short loc_140096D9F
0x140096d58  call    GetLastError_0
0x140096d5d  call    ?RunTaskSchedulerTask@@YAJPEBG@Z; RunTaskSchedulerTask(ushort const *)
0x140096d62  mov     edi, eax
0x140096d64  test    eax, eax
0x140096d66  jns     short loc_140096DB7
0x140096d68  mov     rcx, [rbp+18h]; this
0x140096d6c  mov     r9d, eax; char *
0x140096d6f  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x140096d76  mov     edx, 6Eh ; 'n'; void *
0x140096d7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140096d80  test    rbx, rbx
0x140096d83  jz      loc_140096C87
0x140096d89  mov     rcx, rbx; hObject
0x140096d8c  call    cs:__imp_CloseHandle
0x140096d92  test    eax, eax
0x140096d94  jz      loc_140096ECF
0x140096d9a  jmp     loc_140096C87
0x140096d9f  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140096da4  mov     edi, eax
0x140096da6  mov     rbx, r14
0x140096da9  test    eax, eax
0x140096dab  jns     short loc_140096D5D
0x140096dad  mov     edx, 6Bh ; 'k'
0x140096db2  jmp     loc_140096C74
0x140096db7  xor     r8d, r8d; bAlertable
0x140096dba  mov     edx, 7530h; dwMilliseconds
0x140096dbf  mov     rcx, rbx; hHandle
0x140096dc2  call    WaitForSingleObjectEx_0
0x140096dc7  cmp     eax, 102h
0x140096dcc  jz      loc_140096E88
0x140096dd2  test    eax, eax
0x140096dd4  jnz     loc_140096F16
0x140096dda  mov     qword ptr [rsp+80h+ppv], rsi; int
0x140096ddf  lea     r9, _GUID_75121952_e0d0_43e5_9380_1d80483acf72; riid
0x140096de6  xor     edx, edx; pUnkOuter
0x140096de8  lea     r8d, [rax+4]; dwClsContext
0x140096dec  lea     rcx, CLSID_CreateObjectAsSystem; rclsid
0x140096df3  call    CoCreateInstance_0
0x140096df8  mov     edi, eax
0x140096dfa  test    eax, eax
0x140096dfc  jns     short loc_140096E35
0x140096dfe  mov     rcx, [rbp+18h]; this
0x140096e02  mov     r9d, eax; char *
0x140096e05  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x140096e0c  mov     edx, 71h ; 'q'; void *
0x140096e11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140096e16  test    rbx, rbx
0x140096e19  jz      loc_140096C87
0x140096e1f  mov     rcx, rbx; hObject
0x140096e22  call    cs:__imp_CloseHandle
0x140096e28  test    eax, eax
0x140096e2a  jz      loc_140096EDE
0x140096e30  jmp     loc_140096C87
0x140096e35  test    rbx, rbx
0x140096e38  jz      short loc_140096E47
0x140096e3a  mov     rcx, rbx; hObject
0x140096e3d  call    cs:__imp_CloseHandle
0x140096e43  test    eax, eax
0x140096e45  jz      short loc_140096EC0
0x140096e47  lea     rcx, [rbp+var_30]; this
0x140096e4b  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x140096e50  cmp     [rbp+var_38], r14b
0x140096e54  jz      short loc_140096E6E
0x140096e56  mov     rbx, [rbp+lpMem]
0x140096e5a  call    cs:__imp_GetProcessHeap
0x140096e60  mov     r8, rbx; lpMem
0x140096e63  xor     edx, edx; dwFlags
0x140096e65  mov     rcx, rax; hHeap
0x140096e68  call    cs:__imp_HeapFree
0x140096e6e  xor     eax, eax
0x140096e70  lea     r11, [rsp+80h+var_s0]
0x140096e78  mov     rbx, [r11+20h]
0x140096e7c  mov     rsi, [r11+28h]
0x140096e80  mov     rsp, r11
0x140096e83  pop     r14
0x140096e85  pop     rdi
0x140096e86  pop     rbp
0x140096e87  retn
0x140096e88  mov     rcx, [rbp+18h]; this
0x140096e8c  mov     edi, 800705B4h
0x140096e91  mov     r9d, edi; char *
0x140096e94  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x140096e9b  mov     edx, 6Fh ; 'o'; void *
0x140096ea0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140096ea5  test    rbx, rbx
0x140096ea8  jz      loc_140096C87
0x140096eae  mov     rcx, rbx; hObject
0x140096eb1  call    cs:__imp_CloseHandle
0x140096eb7  test    eax, eax
0x140096eb9  jz      short loc_140096EED
0x140096ebb  jmp     loc_140096C87
0x140096ec0  mov     rcx, [rbp+18h]; this
0x140096ec4  mov     edx, 0A0Bh; void *
0x140096ec9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140096ecf  mov     rcx, [rbp+18h]; this
0x140096ed3  mov     edx, 0A0Bh; void *
0x140096ed8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140096ede  mov     rcx, [rbp+18h]; this
0x140096ee2  mov     edx, 0A0Bh; void *
0x140096ee7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140096eed  mov     rcx, [rbp+18h]; this
0x140096ef1  mov     edx, 0A0Bh; void *
0x140096ef6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140096efc  mov     rcx, [rbp+18h]; this
0x140096f00  mov     edx, 0B0Fh; void *
0x140096f05  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140096f0b  mov     edx, 0A0Bh; void *
0x140096f10  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140096f16  mov     rcx, [rbp+18h]; this
0x140096f1a  mov     edx, 0B0Fh; void *
0x140096f1f  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```
