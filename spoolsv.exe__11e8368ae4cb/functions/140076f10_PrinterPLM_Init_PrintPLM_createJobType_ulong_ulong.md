# PrinterPLM::Init(PrintPLM::createJobType,ulong,ulong)

- ea: `0x140076f10`
- end: `0x140077082`
- name: `?Init@PrinterPLM@@AEAAJW4createJobType@PrintPLM@@KK@Z`
- size: `370`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140076d5c`

## callees

- `0x14001488c`
- `0x140076f10`
- `0x140077220`
- `0x140077560`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140077006`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140077006`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140076ff7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140076ff7`
- `KERNEL32!GetTickCount64` at `0x140077031`
- `KERNEL32!GetTickCount64` at `0x140077031`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140076f85`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140076f85`

## string_xrefs

- `0x140076fb5`: `BeginTask failed. HResult: 0x%x`
- `0x140076f55`: `Creating a PLM Task Completion Object Ids. ProcessId: 0x%04x SessionId: 0x%04x`
- `0x14007701e`: `CreateThreadpoolTimer() failed 0x%x!!`
- `0x14007704b`: `CoCreate of OSTaskCompletion Object failed. HResult: 0x%x`

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
0x140076f10  push    rbx
0x140076f12  push    rbp
0x140076f13  push    rsi
0x140076f14  push    rdi
0x140076f15  push    r14
0x140076f17  push    r15
0x140076f19  sub     rsp, 38h
0x140076f1d  mov     ebp, edx
0x140076f1f  lea     rsi, aPrinterplmInit; "PrinterPLM::Init"
0x140076f26  mov     rdi, rcx
0x140076f29  lea     rdx, aInitPlmObject; "Init PLM object"
0x140076f30  mov     rcx, rsi; char *
0x140076f33  mov     r15d, r9d
0x140076f36  mov     r14d, r8d
0x140076f39  call    ?WriteDbgTraceInfo@PrintPLMTelemetry@@SAXPEADPEAGZZ; PrintPLMTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140076f3e  mov     ebx, [rdi+58h]
0x140076f41  mov     [rsp+68h+arg_0], 0
0x140076f4a  test    ebx, ebx
0x140076f4c  js      loc_14007704B
0x140076f52  mov     r9d, r15d
0x140076f55  lea     rdx, aCreatingAPlmTa; "Creating a PLM Task Completion Object I"...
0x140076f5c  mov     r8d, r14d
0x140076f5f  mov     rcx, rsi; char *
0x140076f62  call    ?WriteDbgTraceInfo@PrintPLMTelemetry@@SAXPEADPEAGZZ; PrintPLMTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140076f67  xor     edx, edx; pUnkOuter
0x140076f69  lea     rax, [rsp+68h+arg_0]
0x140076f6e  lea     r9, IID_IOSTaskCompletion; riid
0x140076f75  mov     [rsp+68h+ppv], rax; ppv
0x140076f7a  lea     rcx, CLSID_OSTaskCompletion; rclsid
0x140076f81  lea     r8d, [rdx+1]; dwClsContext
0x140076f85  call    cs:__imp_CoCreateInstance
0x140076f8b  mov     ebx, eax
0x140076f8d  test    eax, eax
0x140076f8f  js      loc_14007704B
0x140076f95  mov     rcx, [rsp+68h+arg_0]
0x140076f9a  mov     r8d, 8
0x140076fa0  mov     edx, r14d
0x140076fa3  mov     rax, [rcx]
0x140076fa6  mov     rax, [rax+18h]
0x140076faa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140076faf  mov     ebx, eax
0x140076fb1  test    eax, eax
0x140076fb3  jns     short loc_140076FC1
0x140076fb5  lea     rdx, aBegintaskFaile; "BeginTask failed. HResult: 0x%x"
0x140076fbc  jmp     loc_140077052
0x140076fc1  mov     rax, [rsp+68h+arg_0]
0x140076fc6  xor     ecx, ecx
0x140076fc8  test    rax, rax
0x140076fcb  jz      short loc_140076FD9
0x140076fcd  mov     rcx, rax
0x140076fd0  mov     [rsp+68h+arg_0], 0
0x140076fd9  mov     [rdi+20h], rcx
0x140076fdd  lea     rax, ?StartDocTimerCallback@PrinterPLM@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; PrinterPLM::StartDocTimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)
0x140076fe4  test    ebp, ebp
0x140076fe6  lea     rcx, ?AddJobTimerCallback@PrinterPLM@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; PrinterPLM::AddJobTimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)
0x140076fed  mov     rdx, rdi; pv
0x140076ff0  cmovnz  rcx, rax; pfnti
0x140076ff4  xor     r8d, r8d; pcbe
0x140076ff7  call    cs:__imp_CreateThreadpoolTimer
0x140076ffd  mov     [rdi+60h], rax
0x140077001  test    rax, rax
0x140077004  jnz     short loc_140077031
0x140077006  call    cs:__imp_GetLastError
0x14007700c  mov     ebx, eax
0x14007700e  test    eax, eax
0x140077010  jle     short loc_14007701B
0x140077012  movzx   ebx, ax
0x140077015  or      ebx, 80070000h
0x14007701b  mov     r8d, ebx
0x14007701e  lea     rdx, aCreatethreadpo; "CreateThreadpoolTimer() failed 0x%x!!"
0x140077025  mov     rcx, rsi; char *
0x140077028  call    ?WriteDbgTraceError@PrintPLMTelemetry@@SAXPEADPEAGZZ; PrintPLMTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14007702d  test    ebx, ebx
0x14007702f  js      short loc_14007705D
0x140077031  call    cs:__imp_GetTickCount64
0x140077037  mov     edx, ebp
0x140077039  mov     rcx, rdi
0x14007703c  mov     [rdi+18h], rax
0x140077040  mov     [rdi+10h], rax
0x140077044  call    ?SetFirstRun@PrinterPLM@@AEAAXW4createJobType@PrintPLM@@@Z; PrinterPLM::SetFirstRun(PrintPLM::createJobType)
0x140077049  jmp     short loc_14007705D
0x14007704b  lea     rdx, aCocreateOfOsta; "CoCreate of OSTaskCompletion Object fai"...
0x140077052  mov     r8d, ebx
0x140077055  mov     rcx, rsi; char *
0x140077058  call    ?WriteDbgTraceError@PrintPLMTelemetry@@SAXPEADPEAGZZ; PrintPLMTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14007705d  mov     rcx, [rsp+68h+arg_0]
0x140077062  test    rcx, rcx
0x140077065  jz      short loc_140077073
0x140077067  mov     rax, [rcx]
0x14007706a  mov     rax, [rax+10h]
0x14007706e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140077073  mov     eax, ebx
0x140077075  add     rsp, 38h
0x140077079  pop     r15
0x14007707b  pop     r14
0x14007707d  pop     rdi
0x14007707e  pop     rsi
0x14007707f  pop     rbp
0x140077080  pop     rbx
0x140077081  retn
```
