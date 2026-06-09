# PrinterPLM::Init(PrintPLM::createJobType,ulong,ulong)

- ea: `0x14007e1c4`
- end: `0x14007e34f`
- name: `?Init@PrinterPLM@@AEAAJW4createJobType@PrintPLM@@KK@Z`
- size: `395`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14007e00c`

## callees

- `0x140015b60`
- `0x14007e1c4`
- `0x14007e4fc`
- `0x14007e884`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007e2c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007e2c6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14007e2b1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14007e2b1`
- `KERNEL32!GetTickCount64` at `0x14007e2f7`
- `KERNEL32!GetTickCount64` at `0x14007e2f7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14007e239`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14007e239`

## string_xrefs

- `0x14007e317`: `CoCreate of OSTaskCompletion Object failed. HResult: 0x%x`
- `0x14007e26f`: `BeginTask failed. HResult: 0x%x`
- `0x14007e209`: `Creating a PLM Task Completion Object Ids. ProcessId: 0x%04x SessionId: 0x%04x`
- `0x14007e2e4`: `CreateThreadpoolTimer() failed 0x%x!!`

## pseudocode

```c
__int64 __fastcall PrinterPLM::Init(__int64 a1, unsigned int a2, unsigned int a3, unsigned int a4)
{
  int v8; // ebx
  LPVOID v9; // rcx
  void (__stdcall *v10)(PTP_CALLBACK_INSTANCE, PVOID, PTP_TIMER); // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  signed int LastError; // eax
  ULONGLONG TickCount64; // rax
  LPVOID ppv; // [rsp+70h] [rbp+8h] BYREF

  PrintPLMTelemetry::WriteDbgTraceInfo("PrinterPLM::Init", L"Init PLM object");
  v8 = *(_DWORD *)(a1 + 88);
  ppv = 0;
  if ( v8 < 0
    || (PrintPLMTelemetry::WriteDbgTraceInfo(
          "PrinterPLM::Init",
          L"Creating a PLM Task Completion Object Ids. ProcessId: 0x%04x SessionId: 0x%04x",
          a3,
          a4),
        v8 = CoCreateInstance(&CLSID_OSTaskCompletion, 0, 1u, &IID_IOSTaskCompletion, &ppv),
        v8 < 0) )
  {
    PrintPLMTelemetry::WriteDbgTraceError(
      "PrinterPLM::Init",
      L"CoCreate of OSTaskCompletion Object failed. HResult: 0x%x",
      (unsigned int)v8);
  }
  else
  {
    v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64))(*(_QWORD *)ppv + 24LL))(ppv, a3, 8);
    if ( v8 >= 0 )
    {
      v9 = 0;
      if ( ppv )
      {
        v9 = ppv;
        ppv = 0;
      }
      *(_QWORD *)(a1 + 32) = v9;
      v10 = (void (__stdcall *)(PTP_CALLBACK_INSTANCE, PVOID, PTP_TIMER))PrinterPLM::AddJobTimerCallback;
      if ( a2 )
        v10 = PrinterPLM::StartDocTimerCallback;
      ThreadpoolTimer = CreateThreadpoolTimer(v10, (PVOID)a1, 0);
      *(_QWORD *)(a1 + 96) = ThreadpoolTimer;
      if ( ThreadpoolTimer )
        goto LABEL_13;
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      PrintPLMTelemetry::WriteDbgTraceError(
        "PrinterPLM::Init",
        L"CreateThreadpoolTimer() failed 0x%x!!",
        (unsigned int)v8);
      if ( v8 >= 0 )
      {
LABEL_13:
        TickCount64 = GetTickCount64();
        *(_QWORD *)(a1 + 24) = TickCount64;
        *(_QWORD *)(a1 + 16) = TickCount64;
        PrinterPLM::SetFirstRun(a1, a2);
      }
    }
    else
    {
      PrintPLMTelemetry::WriteDbgTraceError("PrinterPLM::Init", L"BeginTask failed. HResult: 0x%x", (unsigned int)v8);
    }
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14007e1c4  push    rbx
0x14007e1c6  push    rbp
0x14007e1c7  push    rsi
0x14007e1c8  push    rdi
0x14007e1c9  push    r14
0x14007e1cb  push    r15
0x14007e1cd  sub     rsp, 38h
0x14007e1d1  mov     ebp, edx
0x14007e1d3  lea     rsi, aPrinterplmInit; "PrinterPLM::Init"
0x14007e1da  mov     rdi, rcx
0x14007e1dd  lea     rdx, aInitPlmObject; "Init PLM object"
0x14007e1e4  mov     rcx, rsi; char *
0x14007e1e7  mov     r15d, r9d
0x14007e1ea  mov     r14d, r8d
0x14007e1ed  call    ?WriteDbgTraceInfo@PrintPLMTelemetry@@SAXPEADPEAGZZ; PrintPLMTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14007e1f2  mov     ebx, [rdi+58h]
0x14007e1f5  mov     [rsp+68h+arg_0], 0
0x14007e1fe  test    ebx, ebx
0x14007e200  js      loc_14007E317
0x14007e206  mov     r9d, r15d
0x14007e209  lea     rdx, aCreatingAPlmTa; "Creating a PLM Task Completion Object I"...
0x14007e210  mov     r8d, r14d
0x14007e213  mov     rcx, rsi; char *
0x14007e216  call    ?WriteDbgTraceInfo@PrintPLMTelemetry@@SAXPEADPEAGZZ; PrintPLMTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14007e21b  xor     edx, edx; pUnkOuter
0x14007e21d  lea     rax, [rsp+68h+arg_0]
0x14007e222  lea     r9, IID_IOSTaskCompletion; riid
0x14007e229  mov     [rsp+68h+ppv], rax; ppv
0x14007e22e  lea     rcx, CLSID_OSTaskCompletion; rclsid
0x14007e235  lea     r8d, [rdx+1]; dwClsContext
0x14007e239  call    cs:__imp_CoCreateInstance
0x14007e240  nop     dword ptr [rax+rax+00h]
0x14007e245  mov     ebx, eax
0x14007e247  test    eax, eax
0x14007e249  js      loc_14007E317
0x14007e24f  mov     rcx, [rsp+68h+arg_0]
0x14007e254  mov     r8d, 8
0x14007e25a  mov     edx, r14d
0x14007e25d  mov     rax, [rcx]
0x14007e260  mov     rax, [rax+18h]
0x14007e264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007e269  mov     ebx, eax
0x14007e26b  test    eax, eax
0x14007e26d  jns     short loc_14007E27B
0x14007e26f  lea     rdx, aBegintaskFaile; "BeginTask failed. HResult: 0x%x"
0x14007e276  jmp     loc_14007E31E
0x14007e27b  mov     rax, [rsp+68h+arg_0]
0x14007e280  xor     ecx, ecx
0x14007e282  test    rax, rax
0x14007e285  jz      short loc_14007E293
0x14007e287  mov     rcx, rax
0x14007e28a  mov     [rsp+68h+arg_0], 0
0x14007e293  mov     [rdi+20h], rcx
0x14007e297  lea     rax, ?StartDocTimerCallback@PrinterPLM@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; PrinterPLM::StartDocTimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)
0x14007e29e  test    ebp, ebp
0x14007e2a0  lea     rcx, ?AddJobTimerCallback@PrinterPLM@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; PrinterPLM::AddJobTimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)
0x14007e2a7  mov     rdx, rdi; pv
0x14007e2aa  cmovnz  rcx, rax; pfnti
0x14007e2ae  xor     r8d, r8d; pcbe
0x14007e2b1  call    cs:__imp_CreateThreadpoolTimer
0x14007e2b8  nop     dword ptr [rax+rax+00h]
0x14007e2bd  mov     [rdi+60h], rax
0x14007e2c1  test    rax, rax
0x14007e2c4  jnz     short loc_14007E2F7
0x14007e2c6  call    cs:__imp_GetLastError
0x14007e2cd  nop     dword ptr [rax+rax+00h]
0x14007e2d2  mov     ebx, eax
0x14007e2d4  test    eax, eax
0x14007e2d6  jle     short loc_14007E2E1
0x14007e2d8  movzx   ebx, ax
0x14007e2db  or      ebx, 80070000h
0x14007e2e1  mov     r8d, ebx
0x14007e2e4  lea     rdx, aCreatethreadpo; "CreateThreadpoolTimer() failed 0x%x!!"
0x14007e2eb  mov     rcx, rsi; char *
0x14007e2ee  call    ?WriteDbgTraceError@PrintPLMTelemetry@@SAXPEADPEAGZZ; PrintPLMTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14007e2f3  test    ebx, ebx
0x14007e2f5  js      short loc_14007E329
0x14007e2f7  call    cs:__imp_GetTickCount64
0x14007e2fe  nop     dword ptr [rax+rax+00h]
0x14007e303  mov     edx, ebp
0x14007e305  mov     rcx, rdi
0x14007e308  mov     [rdi+18h], rax
0x14007e30c  mov     [rdi+10h], rax
0x14007e310  call    ?SetFirstRun@PrinterPLM@@AEAAXW4createJobType@PrintPLM@@@Z; PrinterPLM::SetFirstRun(PrintPLM::createJobType)
0x14007e315  jmp     short loc_14007E329
0x14007e317  lea     rdx, aCocreateOfOsta; "CoCreate of OSTaskCompletion Object fai"...
0x14007e31e  mov     r8d, ebx
0x14007e321  mov     rcx, rsi; char *
0x14007e324  call    ?WriteDbgTraceError@PrintPLMTelemetry@@SAXPEADPEAGZZ; PrintPLMTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14007e329  mov     rcx, [rsp+68h+arg_0]
0x14007e32e  test    rcx, rcx
0x14007e331  jz      short loc_14007E33F
0x14007e333  mov     rax, [rcx]
0x14007e336  mov     rax, [rax+10h]
0x14007e33a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007e33f  mov     eax, ebx
0x14007e341  add     rsp, 38h
0x14007e345  pop     r15
0x14007e347  pop     r14
0x14007e349  pop     rdi
0x14007e34a  pop     rsi
0x14007e34b  pop     rbp
0x14007e34c  pop     rbx
0x14007e34d  retn
```
