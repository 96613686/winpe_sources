# ServiceMain(uint,ushort * *)

- ea: `0x180038de0`
- end: `0x18003925b`
- name: `?ServiceMain@@YAXIPEAPEAG@Z`
- size: `1147`
- prototype: `void __fastcall(__int64, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `28`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000a974`
- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000f4fc`
- `0x180011a94`
- `0x1800138a8`
- `0x1800174c4`
- `0x18002de18`
- `0x18002def8`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180033884`
- `0x180033cc0`
- `0x1800353b4`
- `0x180036334`
- `0x180038de0`
- `0x18003ae34`
- `0x18003ae6c`
- `0x18003ae9c`
- `0x1800459d8`
- `0x180045cd4`
- `0x1800465fc`
- `0x180076654`
- `0x1800768ac`
- `0x180076adc`
- `0x180078010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800391b9`
- `KERNEL32!EnterCriticalSection` at `0x1800391b9`
- `KERNEL32!LeaveCriticalSection` at `0x1800391f3`
- `KERNEL32!LeaveCriticalSection` at `0x1800391f3`
- `KERNEL32!CreateEventW` at `0x180038e24`
- `KERNEL32!CreateEventW` at `0x180038e86`
- `KERNEL32!CreateEventW` at `0x180038e24`
- `KERNEL32!CreateEventW` at `0x180038e86`
- `KERNEL32!GetLastError` at `0x180038e3d`
- `KERNEL32!GetLastError` at `0x180038e98`
- `KERNEL32!GetLastError` at `0x180038e3d`
- `KERNEL32!GetLastError` at `0x180038e98`
- `KERNEL32!CloseHandle` at `0x1800390bc`
- `KERNEL32!CloseHandle` at `0x1800390d9`
- `KERNEL32!CloseHandle` at `0x1800390bc`
- `KERNEL32!CloseHandle` at `0x1800390d9`
- `ole32!CoInitializeEx` at `0x180038efc`
- `ole32!CoInitializeEx` at `0x180038efc`
- `ole32!CoUninitialize` at `0x180039218`
- `ole32!CoUninitialize` at `0x180039218`

## string_xrefs

- `0x180038e45`: `Fatal error: failed to create shutdown event, error code 0x%08X`
- `0x180038e69`: `Fatal error: failed to create shutdown event, error code 0x%08X`
- `0x180038e31`: `ServiceMain`
- `0x180038ea0`: `Fatal error: failed to create event for push-scanning, error code 0x%08X`
- `0x180038ec4`: `Fatal error: failed to create event for push-scanning, error code 0x%08X`
- `0x180039067`: `Fatal error: failed to create the global service component holder - we appear to be out of memory`
- `0x180039089`: `Fatal error: failed to create the global service component holder - we appear to be out of memory`
- `0x180038f0a`: `Fatal error: failed to Initialize COM (hr = 0x%08X)`
- `0x180038f2c`: `Fatal error: failed to Initialize COM (hr = 0x%08X)`
- `0x180038ff0`: `Fatal error: failed to Initialize the WiaService object (hr = 0x%08X)`
- `0x180039012`: `Fatal error: failed to Initialize the WiaService object (hr = 0x%08X)`
- `0x18003901e`: `Fatal error: failed to create the WiaService object - we appear to be out of memory`
- `0x180039040`: `Fatal error: failed to create the WiaService object - we appear to be out of memory`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, unsigned __int16 **a2)
{
  int v2; // ebp
  WiaService *v3; // rsi
  DWORD LastError; // edi
  char *v5; // rbx
  void *v6; // rdx
  void *v7; // rax
  int v8; // edx
  int v9; // ecx
  DWORD v10; // edi
  char *v11; // rbx
  void *v12; // rdx
  void *v13; // rax
  HRESULT v14; // edi
  char *v15; // rbx
  void *v16; // rdx
  WiaService *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // rcx
  int v21; // edi
  __int64 v22; // r8
  char *v23; // rbx
  void *v24; // rdx
  char *v25; // rbx
  void *v26; // rdx
  void *lpMem; // rax
  int v28; // edx
  int v29; // ecx
  char *v30; // rbx
  void *v31; // rdx
  HANDLE v32; // rcx
  HANDLE v33; // rcx
  Dispatcher *v34; // rbx
  char *v35; // rcx
  char *v36; // rbx
  void *v37; // rdx
  void *v38; // rax
  int v39; // edx
  int v40; // ecx
  __int64 v41; // r8
  __int64 v42; // rax
  char *v43; // rcx
  _QWORD v44[38]; // [rsp+40h] [rbp-188h] BYREF
  _BYTE v45[16]; // [rsp+170h] [rbp-58h] BYREF

  v2 = 0;
  v3 = 0;
  EnableMitigations();
  McGenEventRegister_EventRegister();
  InitializeWIATracingLibrary();
  g_hShutdownEvent = CreateEventW(0, 1, 0, 0);
  if ( !g_hShutdownEvent )
  {
    LastError = GetLastError();
    v5 = (char *)WiaTrace_TraceLog("Fatal error: failed to create shutdown event, error code 0x%08X");
    WriteDbgTraceErrorWI("ServiceMain", v5);
    WiaTrcLib::Free((WiaTrcLib *)v5, v6);
    v7 = (void *)WiaTrace_Trace("Fatal error: failed to create shutdown event, error code 0x%08X", LastError);
    goto LABEL_21;
  }
  g_hWiaRpcAsyncCallEvent = CreateEventW(0, 0, 0, 0);
  if ( !g_hWiaRpcAsyncCallEvent )
  {
    v10 = GetLastError();
    v11 = (char *)WiaTrace_TraceLog("Fatal error: failed to create event for push-scanning, error code 0x%08X");
    WriteDbgTraceErrorWI("ServiceMain", v11);
    WiaTrcLib::Free((WiaTrcLib *)v11, v12);
    v7 = (void *)WiaTrace_Trace("Fatal error: failed to create event for push-scanning, error code 0x%08X", v10);
    goto LABEL_21;
  }
  v13 = operator new(0x68u);
  if ( !v13 )
  {
    g_pServiceComponentHolder = 0;
    goto LABEL_20;
  }
  g_pServiceComponentHolder = CSimpleRefMap<CSimpleStringBase<unsigned short>>::CSimpleRefMap<CSimpleStringBase<unsigned short>>(v13);
  if ( !g_pServiceComponentHolder )
  {
LABEL_20:
    v30 = (char *)WiaTrace_TraceLog("Fatal error: failed to create the global service component holder - we appear to be out of memory");
    WriteDbgTraceErrorWI("ServiceMain", v30);
    WiaTrcLib::Free((WiaTrcLib *)v30, v31);
    v7 = (void *)WiaTrace_Trace("Fatal error: failed to create the global service component holder - we appear to be out of memory");
    goto LABEL_21;
  }
  v14 = CoInitializeEx(0, 0);
  if ( v14 >= 0 )
  {
    v2 = 1;
    v17 = (WiaService *)operator new(0x38u);
    v3 = v17;
    if ( !v17 )
    {
      v25 = (char *)WiaTrace_TraceLog("Fatal error: failed to create the WiaService object - we appear to be out of memory");
      WriteDbgTraceErrorWI("ServiceMain", v25);
      WiaTrcLib::Free((WiaTrcLib *)v25, v26);
      lpMem = (void *)WiaTrace_Trace("Fatal error: failed to create the WiaService object - we appear to be out of memory");
      WiaTrace_ProcessTrace_Ex(v29, v28, (int)"ServiceMain", 1, lpMem);
      v3 = 0;
      goto LABEL_22;
    }
    *((_DWORD *)v17 + 12) = 1;
    *(_QWORD *)v17 = &WiaService::`vbtable';
    *((_QWORD *)v17 + 5) = &WiaService::`vftable';
    *((_QWORD *)v17 + 1) = 1432580947;
    *((_QWORD *)v17 + 2) = 0;
    *((_DWORD *)v17 + 6) = 0;
    *((_QWORD *)v17 + 4) = 0;
    if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
      McGenEventWrite_EventWriteTransfer(v18, DocPerf_Wia_ServiceInit_Start, v19, 1, v45);
    v21 = WiaService::Initialize(v3);
    if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
      McGenEventWrite_EventWriteTransfer(v20, DocPerf_Wia_ServiceInit_Stop, v22, 1, v45);
    if ( v21 >= 0 )
    {
      WiaService::Run(v3);
      goto LABEL_22;
    }
    v23 = (char *)WiaTrace_TraceLog("Fatal error: failed to Initialize the WiaService object (hr = 0x%08X)");
    WriteDbgTraceErrorWI("ServiceMain", v23);
    WiaTrcLib::Free((WiaTrcLib *)v23, v24);
    v7 = (void *)WiaTrace_Trace(
                   "Fatal error: failed to Initialize the WiaService object (hr = 0x%08X)",
                   (unsigned int)v21);
  }
  else
  {
    v15 = (char *)WiaTrace_TraceLog("Fatal error: failed to Initialize COM (hr = 0x%08X)");
    WriteDbgTraceErrorWI("ServiceMain", v15);
    WiaTrcLib::Free((WiaTrcLib *)v15, v16);
    v7 = (void *)WiaTrace_Trace("Fatal error: failed to Initialize COM (hr = 0x%08X)", (unsigned int)v14);
  }
LABEL_21:
  WiaTrace_ProcessTrace_Ex(v9, v8, (int)"ServiceMain", 1, v7);
LABEL_22:
  v32 = g_hWiaRpcAsyncCallEvent;
  if ( g_hWiaRpcAsyncCallEvent )
  {
    g_hWiaRpcAsyncCallEvent = 0;
    CloseHandle(v32);
  }
  v33 = g_hShutdownEvent;
  if ( g_hShutdownEvent )
  {
    g_hShutdownEvent = 0;
    CloseHandle(v33);
  }
  ServiceComponentHolder::ServiceComponentHolder((ServiceComponentHolder *)v45);
  CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v44, L"Dispatcher");
  v34 = (Dispatcher *)ServiceComponentHolder::Get<Dispatcher>(v45, v44);
  v44[0] = &CSimpleStringBase<unsigned short>::`vftable';
  CSimpleStringBase<unsigned short>::DeleteStorage(v44);
  v44[34] = 0;
  if ( v34 )
  {
    Dispatcher::UnInitialize(v34);
    v35 = (char *)v34 + *(int *)(*((_QWORD *)v34 + 1) + 4LL) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v35 + 16LL))(v35);
  }
  else
  {
    v36 = (char *)WiaTrace_TraceLogWithSubComp(1, "The Image Device Class enumerator failed to find the Dispatcher");
    WriteDbgTraceWarningWI("ServiceMain", v36);
    WiaTrcLib::Free((WiaTrcLib *)v36, v37);
    v38 = (void *)WiaTrace_TraceWithSubComp(1, "The Image Device Class enumerator failed to find the Dispatcher");
    WiaTrace_ProcessTrace_Ex(v40, v39, (int)"ServiceMain", 2, v38);
  }
  ServiceComponentHolder::~ServiceComponentHolder((ServiceComponentHolder *)v45);
  EnterCriticalSection(&g_csServiceComponentHolder);
  v41 = g_pServiceComponentHolder;
  if ( g_pServiceComponentHolder )
  {
    v42 = *(_QWORD *)g_pServiceComponentHolder;
    g_pServiceComponentHolder = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v41 + *(int *)(v42 + 4)) + 16LL))(v41 + *(int *)(v42 + 4));
  }
  LeaveCriticalSection(&g_csServiceComponentHolder);
  if ( v3 )
  {
    v43 = (char *)v3 + *(int *)(*(_QWORD *)v3 + 4LL);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v43 + 16LL))(v43);
  }
  if ( v2 )
    CoUninitialize();
  if ( _InterlockedCompareExchange(&WiaTrcLib::g_WiaTrc_bInited, 1, 1) == 1 )
  {
    CWiaObjectTracking::Term();
    WiaTrace_Term_Trace();
  }
  McGenEventUnregister_EventUnregister();
}

```

## disassembly

```asm
0x180038de0  push    rbx
0x180038de2  push    rbp
0x180038de3  push    rsi
0x180038de4  push    rdi
0x180038de5  push    r12
0x180038de7  push    r15
0x180038de9  sub     rsp, 198h
0x180038df0  mov     rax, cs:__security_cookie
0x180038df7  xor     rax, rsp
0x180038dfa  mov     [rsp+1C8h+var_48], rax
0x180038e02  xor     ebp, ebp
0x180038e04  xor     esi, esi
0x180038e06  call    ?EnableMitigations@@YAXXZ; EnableMitigations(void)
0x180038e0b  call    McGenEventRegister_EventRegister
0x180038e10  call    InitializeWIATracingLibrary
0x180038e15  lea     r15d, [rbp+1]
0x180038e19  xor     r9d, r9d; lpName
0x180038e1c  mov     edx, r15d; bManualReset
0x180038e1f  xor     r8d, r8d; bInitialState
0x180038e22  xor     ecx, ecx; lpEventAttributes
0x180038e24  call    cs:__imp_CreateEventW
0x180038e2a  mov     cs:?g_hShutdownEvent@@3PEAXEA, rax; void * g_hShutdownEvent
0x180038e31  lea     r12, aServicemain_0; "ServiceMain"
0x180038e38  test    rax, rax
0x180038e3b  jnz     short loc_180038E7C
0x180038e3d  call    cs:__imp_GetLastError
0x180038e43  mov     edx, eax
0x180038e45  lea     rcx, aFatalErrorFail_4; "Fatal error: failed to create shutdown "...
0x180038e4c  mov     edi, eax
0x180038e4e  call    WiaTrace_TraceLog
0x180038e53  mov     rdx, rax; char *
0x180038e56  mov     rcx, r12; char *
0x180038e59  mov     rbx, rax
0x180038e5c  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180038e61  mov     rcx, rbx; this
0x180038e64  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180038e69  lea     rcx, aFatalErrorFail_4; "Fatal error: failed to create shutdown "...
0x180038e70  mov     edx, edi
0x180038e72  call    WiaTrace_Trace
0x180038e77  jmp     loc_180039095
0x180038e7c  xor     r9d, r9d; lpName
0x180038e7f  xor     r8d, r8d; bInitialState
0x180038e82  xor     edx, edx; bManualReset
0x180038e84  xor     ecx, ecx; lpEventAttributes
0x180038e86  call    cs:__imp_CreateEventW
0x180038e8c  mov     cs:?g_hWiaRpcAsyncCallEvent@@3PEAXEA, rax; void * g_hWiaRpcAsyncCallEvent
0x180038e93  test    rax, rax
0x180038e96  jnz     short loc_180038ECD
0x180038e98  call    cs:__imp_GetLastError
0x180038e9e  mov     edx, eax
0x180038ea0  lea     rcx, aFatalErrorFail_0; "Fatal error: failed to create event for"...
0x180038ea7  mov     edi, eax
0x180038ea9  call    WiaTrace_TraceLog
0x180038eae  mov     rdx, rax; char *
0x180038eb1  mov     rcx, r12; char *
0x180038eb4  mov     rbx, rax
0x180038eb7  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180038ebc  mov     rcx, rbx; this
0x180038ebf  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180038ec4  lea     rcx, aFatalErrorFail_0; "Fatal error: failed to create event for"...
0x180038ecb  jmp     short loc_180038E70
0x180038ecd  mov     ecx, 68h ; 'h'; Size
0x180038ed2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180038ed7  test    rax, rax
0x180038eda  jz      loc_180039060
0x180038ee0  mov     rcx, rax
0x180038ee3  call    ??0?$CSimpleRefMap@V?$CSimpleStringBase@G@@@@QEAA@XZ; CSimpleRefMap<CSimpleStringBase<ushort>>::CSimpleRefMap<CSimpleStringBase<ushort>>(void)
0x180038ee8  mov     cs:?g_pServiceComponentHolder@@3PEAV?$CSimpleRefMap@V?$CSimpleStringBase@G@@@@EA, rax; CSimpleRefMap<CSimpleStringBase<ushort>> * g_pServiceComponentHolder
0x180038eef  test    rax, rax
0x180038ef2  jz      loc_180039067
0x180038ef8  xor     edx, edx; dwCoInit
0x180038efa  xor     ecx, ecx; pvReserved
0x180038efc  call    cs:__imp_CoInitializeEx
0x180038f02  mov     edi, eax
0x180038f04  test    eax, eax
0x180038f06  jns     short loc_180038F38
0x180038f08  mov     edx, eax
0x180038f0a  lea     rcx, aFatalErrorFail_1; "Fatal error: failed to Initialize COM ("...
0x180038f11  call    WiaTrace_TraceLog
0x180038f16  mov     rdx, rax; char *
0x180038f19  mov     rcx, r12; char *
0x180038f1c  mov     rbx, rax
0x180038f1f  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180038f24  mov     rcx, rbx; this
0x180038f27  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180038f2c  lea     rcx, aFatalErrorFail_1; "Fatal error: failed to Initialize COM ("...
0x180038f33  jmp     loc_180038E70
0x180038f38  mov     ecx, 38h ; '8'; Size
0x180038f3d  mov     ebp, r15d
0x180038f40  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180038f45  mov     rsi, rax
0x180038f48  test    rax, rax
0x180038f4b  jz      loc_18003901E
0x180038f51  lea     rax, ??_8WiaService@@7B@; const WiaService::`vbtable'
0x180038f58  mov     [rsi+30h], r15d
0x180038f5c  mov     [rsi], rax
0x180038f5f  lea     rax, ??_7WiaService@@6B@; const WiaService::`vftable'
0x180038f66  mov     [rsi+28h], rax
0x180038f6a  mov     qword ptr [rsi+8], 55637353h
0x180038f72  mov     qword ptr [rsi+10h], 0
0x180038f7a  mov     dword ptr [rsi+18h], 0
0x180038f81  mov     qword ptr [rsi+20h], 0
0x180038f89  test    cs:Microsoft_Windows_DocumentsEnableBits, 2
0x180038f90  jz      short loc_180038FAE
0x180038f92  lea     rax, [rsp+1C8h+var_58]
0x180038f9a  mov     r9d, r15d
0x180038f9d  lea     rdx, DocPerf_Wia_ServiceInit_Start
0x180038fa4  mov     [rsp+1C8h+lpMem], rax
0x180038fa9  call    McGenEventWrite_EventWriteTransfer
0x180038fae  mov     rcx, rsi; this
0x180038fb1  call    ?Initialize@WiaService@@QEAAJJ@Z; WiaService::Initialize(long)
0x180038fb6  test    cs:Microsoft_Windows_DocumentsEnableBits, 2
0x180038fbd  mov     edi, eax
0x180038fbf  jz      short loc_180038FDD
0x180038fc1  lea     rax, [rsp+1C8h+var_58]
0x180038fc9  mov     r9d, r15d
0x180038fcc  lea     rdx, DocPerf_Wia_ServiceInit_Stop
0x180038fd3  mov     [rsp+1C8h+lpMem], rax
0x180038fd8  call    McGenEventWrite_EventWriteTransfer
0x180038fdd  test    edi, edi
0x180038fdf  js      short loc_180038FEE
0x180038fe1  mov     rcx, rsi; this
0x180038fe4  call    ?Run@WiaService@@QEAAJXZ; WiaService::Run(void)
0x180038fe9  jmp     loc_1800390A5
0x180038fee  mov     edx, edi
0x180038ff0  lea     rcx, aFatalErrorFail_2; "Fatal error: failed to Initialize the W"...
0x180038ff7  call    WiaTrace_TraceLog
0x180038ffc  mov     rdx, rax; char *
0x180038fff  mov     rcx, r12; char *
0x180039002  mov     rbx, rax
0x180039005  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18003900a  mov     rcx, rbx; this
0x18003900d  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180039012  lea     rcx, aFatalErrorFail_2; "Fatal error: failed to Initialize the W"...
0x180039019  jmp     loc_180038E70
0x18003901e  lea     rcx, aFatalErrorFail_3; "Fatal error: failed to create the WiaSe"...
0x180039025  call    WiaTrace_TraceLog
0x18003902a  mov     rdx, rax; char *
0x18003902d  mov     rcx, r12; char *
0x180039030  mov     rbx, rax
0x180039033  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180039038  mov     rcx, rbx; this
0x18003903b  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180039040  lea     rcx, aFatalErrorFail_3; "Fatal error: failed to create the WiaSe"...
0x180039047  call    WiaTrace_Trace
0x18003904c  mov     r9d, r15d; int
0x18003904f  mov     [rsp+1C8h+lpMem], rax; lpMem
0x180039054  mov     r8, r12; int
0x180039057  call    WiaTrace_ProcessTrace_Ex
0x18003905c  xor     esi, esi
0x18003905e  jmp     short loc_1800390A5
0x180039060  mov     cs:?g_pServiceComponentHolder@@3PEAV?$CSimpleRefMap@V?$CSimpleStringBase@G@@@@EA, rsi; CSimpleRefMap<CSimpleStringBase<ushort>> * g_pServiceComponentHolder
0x180039067  lea     rcx, aFatalErrorFail; "Fatal error: failed to create the globa"...
0x18003906e  call    WiaTrace_TraceLog
0x180039073  mov     rdx, rax; char *
0x180039076  mov     rcx, r12; char *
0x180039079  mov     rbx, rax
0x18003907c  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180039081  mov     rcx, rbx; this
0x180039084  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180039089  lea     rcx, aFatalErrorFail; "Fatal error: failed to create the globa"...
0x180039090  call    WiaTrace_Trace
0x180039095  mov     r9d, r15d; int
0x180039098  mov     [rsp+1C8h+lpMem], rax; lpMem
0x18003909d  mov     r8, r12; int
0x1800390a0  call    WiaTrace_ProcessTrace_Ex
0x1800390a5  mov     rcx, cs:?g_hWiaRpcAsyncCallEvent@@3PEAXEA; hObject
0x1800390ac  test    rcx, rcx
0x1800390af  jz      short loc_1800390C2
0x1800390b1  mov     cs:?g_hWiaRpcAsyncCallEvent@@3PEAXEA, 0; void * g_hWiaRpcAsyncCallEvent
0x1800390bc  call    cs:__imp_CloseHandle
0x1800390c2  mov     rcx, cs:?g_hShutdownEvent@@3PEAXEA; hObject
0x1800390c9  test    rcx, rcx
0x1800390cc  jz      short loc_1800390DF
0x1800390ce  mov     cs:?g_hShutdownEvent@@3PEAXEA, 0; void * g_hShutdownEvent
0x1800390d9  call    cs:__imp_CloseHandle
0x1800390df  lea     rcx, [rsp+1C8h+var_58]; this
0x1800390e7  call    ??0ServiceComponentHolder@@QEAA@XZ; ServiceComponentHolder::ServiceComponentHolder(void)
0x1800390ec  lea     rdx, aDispatcher; "Dispatcher"
0x1800390f3  lea     rcx, [rsp+1C8h+var_188]
0x1800390f8  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x1800390fd  lea     rdx, [rsp+1C8h+var_188]
0x180039102  lea     rcx, [rsp+1C8h+var_58]
0x18003910a  call    ??$Get@VDispatcher@@@ServiceComponentHolder@@QEAAPEAVDispatcher@@AEBV?$CSimpleStringBase@G@@@Z; ServiceComponentHolder::Get<Dispatcher>(CSimpleStringBase<ushort> const &)
0x18003910f  mov     rbx, rax
0x180039112  lea     rcx, [rsp+1C8h+var_188]
0x180039117  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x18003911e  mov     [rsp+1C8h+var_188], rax
0x180039123  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180039128  mov     [rsp+1C8h+var_78], 0
0x180039134  test    rbx, rbx
0x180039137  jz      short loc_18003915E
0x180039139  mov     rcx, rbx; this
0x18003913c  call    ?UnInitialize@Dispatcher@@QEAAJXZ; Dispatcher::UnInitialize(void)
0x180039141  mov     rcx, [rbx+8]
0x180039145  movsxd  rcx, dword ptr [rcx+4]
0x180039149  add     rcx, 8
0x18003914d  add     rcx, rbx
0x180039150  mov     rax, [rcx]
0x180039153  mov     rax, [rax+10h]
0x180039157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003915c  jmp     short loc_1800391A5
0x18003915e  lea     rdx, aTheImageDevice_5; "The Image Device Class enumerator faile"...
0x180039165  mov     ecx, r15d
0x180039168  call    WiaTrace_TraceLogWithSubComp
0x18003916d  mov     rdx, rax; char *
0x180039170  mov     rcx, r12; char *
0x180039173  mov     rbx, rax
0x180039176  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18003917b  mov     rcx, rbx; this
0x18003917e  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180039183  lea     rdx, aTheImageDevice_5; "The Image Device Class enumerator faile"...
0x18003918a  mov     ecx, r15d
0x18003918d  call    WiaTrace_TraceWithSubComp
0x180039192  mov     r9d, 2; int
0x180039198  mov     [rsp+1C8h+lpMem], rax; lpMem
0x18003919d  mov     r8, r12; int
0x1800391a0  call    WiaTrace_ProcessTrace_Ex
0x1800391a5  lea     rcx, [rsp+1C8h+var_58]; this
0x1800391ad  call    ??1ServiceComponentHolder@@UEAA@XZ; ServiceComponentHolder::~ServiceComponentHolder(void)
0x1800391b2  lea     rcx, ?g_csServiceComponentHolder@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800391b9  call    cs:__imp_EnterCriticalSection
0x1800391bf  mov     r8, cs:?g_pServiceComponentHolder@@3PEAV?$CSimpleRefMap@V?$CSimpleStringBase@G@@@@EA; CSimpleRefMap<CSimpleStringBase<ushort>> * g_pServiceComponentHolder
0x1800391c6  test    r8, r8
0x1800391c9  jz      short loc_1800391EC
0x1800391cb  mov     rax, [r8]
0x1800391ce  mov     cs:?g_pServiceComponentHolder@@3PEAV?$CSimpleRefMap@V?$CSimpleStringBase@G@@@@EA, 0; CSimpleRefMap<CSimpleStringBase<ushort>> * g_pServiceComponentHolder
0x1800391d9  movsxd  rcx, dword ptr [rax+4]
0x1800391dd  add     rcx, r8
0x1800391e0  mov     rax, [rcx]
0x1800391e3  mov     rax, [rax+10h]
0x1800391e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800391ec  lea     rcx, ?g_csServiceComponentHolder@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800391f3  call    cs:__imp_LeaveCriticalSection
0x1800391f9  test    rsi, rsi
0x1800391fc  jz      short loc_180039214
0x1800391fe  mov     rax, [rsi]
0x180039201  movsxd  rcx, dword ptr [rax+4]
0x180039205  add     rcx, rsi
0x180039208  mov     rax, [rcx]
0x18003920b  mov     rax, [rax+10h]
0x18003920f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039214  test    ebp, ebp
0x180039216  jz      short loc_18003921E
0x180039218  call    cs:__imp_CoUninitialize
0x18003921e  mov     eax, r15d
0x180039221  lock cmpxchg cs:?g_WiaTrc_bInited@WiaTrcLib@@3HA, r15d; int WiaTrcLib::g_WiaTrc_bInited
0x18003922a  jnz     short loc_180039236
0x18003922c  call    ?Term@CWiaObjectTracking@@SAXXZ; CWiaObjectTracking::Term(void)
0x180039231  call    WiaTrace_Term_Trace
0x180039236  call    McGenEventUnregister_EventUnregister
0x18003923b  mov     rcx, [rsp+1C8h+var_48]
0x180039243  xor     rcx, rsp; StackCookie
0x180039246  call    __security_check_cookie
0x18003924b  add     rsp, 198h
0x180039252  pop     r15
0x180039254  pop     r12
0x180039256  pop     rdi
0x180039257  pop     rsi
0x180039258  pop     rbp
0x180039259  pop     rbx
0x18003925a  retn
```
