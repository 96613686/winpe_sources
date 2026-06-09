# RcsServiceStatusContext::GetRcsServiceStatus(UdmRcsServiceKind,int *)

- ea: `0x18009223c`
- end: `0x18009242d`
- name: `?GetRcsServiceStatus@RcsServiceStatusContext@@QEAAJW4UdmRcsServiceKind@@PEAH@Z`
- size: `497`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801265f0`

## callees

- `0x18006db44`
- `0x180072ccc`
- `0x18009223c`
- `0x180092434`
- `0x1800924c4`
- `0x180092554`
- `0x1800925e4`
- `0x180126594`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800922d5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18009233b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800923a1`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180092404`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800922d5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18009233b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800923a1`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180092404`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800922a7`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18009230d`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180092373`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800923d6`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800922a7`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18009230d`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180092373`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800923d6`

## pseudocode

```c
__int64 __fastcall RcsServiceStatusContext::GetRcsServiceStatus(__int64 a1, int a2, _DWORD *a3)
{
  int v5; // edx
  int v6; // edx
  RcsServiceManager *v8; // rbx
  int IsCapabilitySupported; // eax
  RcsServiceManager *v10; // rbx
  RcsServiceManager *v11; // rbx
  RcsServiceManager *v12; // rbx
  WINBOOL fPending; // [rsp+68h] [rbp+38h] BYREF
  LPVOID Context; // [rsp+70h] [rbp+40h] BYREF
  __int64 v15; // [rsp+78h] [rbp+48h] BYREF

  *a3 = 0;
  if ( a2 )
  {
    v5 = a2 - 1;
    if ( v5 )
    {
      v6 = v5 - 1;
      if ( v6 )
      {
        if ( v6 != 1 )
        {
          Log_HREvent_68(2147942487LL, 0, a3, 47);
          return 2147942487LL;
        }
        fPending = 0;
        Context = 0;
        InitOnceBeginInitialize(&stru_18015DCD8, 0, &fPending, &Context);
        v8 = (RcsServiceManager *)Context;
        if ( !Context )
        {
          v8 = (RcsServiceManager *)qword_18015DCE0;
          RcsServiceManager::RcsServiceManager((RcsServiceManager *)qword_18015DCE0);
          v15 = 0;
          InitOnceComplete(&stru_18015DCD8, 0, qword_18015DCE0);
          tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&v15);
        }
        IsCapabilitySupported = RcsServiceManager::IsCapabilitySupported(v8, *(_DWORD *)(a1 + 8));
      }
      else
      {
        fPending = 0;
        Context = 0;
        InitOnceBeginInitialize(&stru_18015DCD8, 0, &fPending, &Context);
        v10 = (RcsServiceManager *)Context;
        if ( !Context )
        {
          v10 = (RcsServiceManager *)qword_18015DCE0;
          RcsServiceManager::RcsServiceManager((RcsServiceManager *)qword_18015DCE0);
          v15 = 0;
          InitOnceComplete(&stru_18015DCD8, 0, qword_18015DCE0);
          tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&v15);
        }
        IsCapabilitySupported = RcsServiceManager::IsFileTransferSupported(v10, *(_DWORD *)(a1 + 8));
      }
    }
    else
    {
      fPending = 0;
      Context = 0;
      InitOnceBeginInitialize(&stru_18015DCD8, 0, &fPending, &Context);
      v11 = (RcsServiceManager *)Context;
      if ( !Context )
      {
        v11 = (RcsServiceManager *)qword_18015DCE0;
        RcsServiceManager::RcsServiceManager((RcsServiceManager *)qword_18015DCE0);
        v15 = 0;
        InitOnceComplete(&stru_18015DCD8, 0, qword_18015DCE0);
        tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&v15);
      }
      IsCapabilitySupported = RcsServiceManager::IsGroupChatSupported(v11, *(_DWORD *)(a1 + 8));
    }
  }
  else
  {
    fPending = 0;
    Context = 0;
    InitOnceBeginInitialize(&stru_18015DCD8, 0, &fPending, &Context);
    v12 = (RcsServiceManager *)Context;
    if ( !Context )
    {
      v12 = (RcsServiceManager *)qword_18015DCE0;
      RcsServiceManager::RcsServiceManager((RcsServiceManager *)qword_18015DCE0);
      v15 = 0;
      InitOnceComplete(&stru_18015DCD8, 0, qword_18015DCE0);
      tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&v15);
    }
    IsCapabilitySupported = RcsServiceManager::IsChatSupported(v12, *(_DWORD *)(a1 + 8));
  }
  *a3 = IsCapabilitySupported;
  return 0;
}

```

## disassembly

```asm
0x18009223c  push    rbp
0x18009223e  push    rbx
0x18009223f  push    rsi
0x180092240  push    rdi
0x180092241  push    r14
0x180092243  mov     rbp, rsp
0x180092246  sub     rsp, 30h
0x18009224a  xor     r14d, r14d
0x18009224d  mov     rdi, r8
0x180092250  mov     [r8], r14d
0x180092253  mov     rsi, rcx
0x180092256  test    edx, edx
0x180092258  jz      loc_1800923BD
0x18009225e  sub     edx, 1
0x180092261  jz      loc_18009235A
0x180092267  sub     edx, 1
0x18009226a  jz      loc_1800922F4
0x180092270  cmp     edx, 1
0x180092273  jz      short loc_18009228E
0x180092275  mov     ebx, 80070057h
0x18009227a  lea     r9d, [r14+2Fh]
0x18009227e  mov     ecx, ebx
0x180092280  xor     edx, edx
0x180092282  call    Log_HREvent_68
0x180092287  mov     eax, ebx
0x180092289  jmp     loc_180092422
0x18009228e  lea     r9, [rbp+Context]; lpContext
0x180092292  mov     [rbp+fPending], r14d
0x180092296  lea     r8, [rbp+fPending]; fPending
0x18009229a  mov     [rbp+Context], r14
0x18009229e  xor     edx, edx; dwFlags
0x1800922a0  lea     rcx, stru_18015DCD8; lpInitOnce
0x1800922a7  call    cs:__imp_InitOnceBeginInitialize
0x1800922ad  mov     rbx, [rbp+Context]
0x1800922b1  test    rbx, rbx
0x1800922b4  jnz     short loc_1800922E4
0x1800922b6  lea     rbx, qword_18015DCE0
0x1800922bd  mov     rcx, rbx; this
0x1800922c0  call    ??0RcsServiceManager@@QEAA@XZ; RcsServiceManager::RcsServiceManager(void)
0x1800922c5  mov     r8, rbx; lpContext
0x1800922c8  mov     [rbp+arg_18], r14
0x1800922cc  xor     edx, edx; dwFlags
0x1800922ce  lea     rcx, stru_18015DCD8; lpInitOnce
0x1800922d5  call    cs:__imp_InitOnceComplete
0x1800922db  lea     rcx, [rbp+arg_18]
0x1800922df  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x1800922e4  mov     edx, [rsi+8]; unsigned int
0x1800922e7  mov     rcx, rbx; this
0x1800922ea  call    ?IsCapabilitySupported@RcsServiceManager@@QEAAHK@Z; RcsServiceManager::IsCapabilitySupported(ulong)
0x1800922ef  jmp     loc_18009241E
0x1800922f4  lea     r9, [rbp+Context]; lpContext
0x1800922f8  mov     [rbp+fPending], r14d
0x1800922fc  lea     r8, [rbp+fPending]; fPending
0x180092300  mov     [rbp+Context], r14
0x180092304  xor     edx, edx; dwFlags
0x180092306  lea     rcx, stru_18015DCD8; lpInitOnce
0x18009230d  call    cs:__imp_InitOnceBeginInitialize
0x180092313  mov     rbx, [rbp+Context]
0x180092317  test    rbx, rbx
0x18009231a  jnz     short loc_18009234A
0x18009231c  lea     rbx, qword_18015DCE0
0x180092323  mov     rcx, rbx; this
0x180092326  call    ??0RcsServiceManager@@QEAA@XZ; RcsServiceManager::RcsServiceManager(void)
0x18009232b  mov     r8, rbx; lpContext
0x18009232e  mov     [rbp+arg_18], r14
0x180092332  xor     edx, edx; dwFlags
0x180092334  lea     rcx, stru_18015DCD8; lpInitOnce
0x18009233b  call    cs:__imp_InitOnceComplete
0x180092341  lea     rcx, [rbp+arg_18]
0x180092345  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x18009234a  mov     edx, [rsi+8]; unsigned int
0x18009234d  mov     rcx, rbx; this
0x180092350  call    ?IsFileTransferSupported@RcsServiceManager@@QEAAHK@Z; RcsServiceManager::IsFileTransferSupported(ulong)
0x180092355  jmp     loc_18009241E
0x18009235a  lea     r9, [rbp+Context]; lpContext
0x18009235e  mov     [rbp+fPending], r14d
0x180092362  lea     r8, [rbp+fPending]; fPending
0x180092366  mov     [rbp+Context], r14
0x18009236a  xor     edx, edx; dwFlags
0x18009236c  lea     rcx, stru_18015DCD8; lpInitOnce
0x180092373  call    cs:__imp_InitOnceBeginInitialize
0x180092379  mov     rbx, [rbp+Context]
0x18009237d  test    rbx, rbx
0x180092380  jnz     short loc_1800923B0
0x180092382  lea     rbx, qword_18015DCE0
0x180092389  mov     rcx, rbx; this
0x18009238c  call    ??0RcsServiceManager@@QEAA@XZ; RcsServiceManager::RcsServiceManager(void)
0x180092391  mov     r8, rbx; lpContext
0x180092394  mov     [rbp+arg_18], r14
0x180092398  xor     edx, edx; dwFlags
0x18009239a  lea     rcx, stru_18015DCD8; lpInitOnce
0x1800923a1  call    cs:__imp_InitOnceComplete
0x1800923a7  lea     rcx, [rbp+arg_18]
0x1800923ab  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x1800923b0  mov     edx, [rsi+8]; unsigned int
0x1800923b3  mov     rcx, rbx; this
0x1800923b6  call    ?IsGroupChatSupported@RcsServiceManager@@QEAAHK@Z; RcsServiceManager::IsGroupChatSupported(ulong)
0x1800923bb  jmp     short loc_18009241E
0x1800923bd  lea     r9, [rbp+Context]; lpContext
0x1800923c1  mov     [rbp+fPending], r14d
0x1800923c5  lea     r8, [rbp+fPending]; fPending
0x1800923c9  mov     [rbp+Context], r14
0x1800923cd  xor     edx, edx; dwFlags
0x1800923cf  lea     rcx, stru_18015DCD8; lpInitOnce
0x1800923d6  call    cs:__imp_InitOnceBeginInitialize
0x1800923dc  mov     rbx, [rbp+Context]
0x1800923e0  test    rbx, rbx
0x1800923e3  jnz     short loc_180092413
0x1800923e5  lea     rbx, qword_18015DCE0
0x1800923ec  mov     rcx, rbx; this
0x1800923ef  call    ??0RcsServiceManager@@QEAA@XZ; RcsServiceManager::RcsServiceManager(void)
0x1800923f4  mov     r8, rbx; lpContext
0x1800923f7  mov     [rbp+arg_18], r14
0x1800923fb  xor     edx, edx; dwFlags
0x1800923fd  lea     rcx, stru_18015DCD8; lpInitOnce
0x180092404  call    cs:__imp_InitOnceComplete
0x18009240a  lea     rcx, [rbp+arg_18]
0x18009240e  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x180092413  mov     edx, [rsi+8]; unsigned int
0x180092416  mov     rcx, rbx; this
0x180092419  call    ?IsChatSupported@RcsServiceManager@@QEAAHK@Z; RcsServiceManager::IsChatSupported(ulong)
0x18009241e  mov     [rdi], eax
0x180092420  xor     eax, eax
0x180092422  add     rsp, 30h
0x180092426  pop     r14
0x180092428  pop     rdi
0x180092429  pop     rsi
0x18009242a  pop     rbx
0x18009242b  pop     rbp
0x18009242c  retn
```
