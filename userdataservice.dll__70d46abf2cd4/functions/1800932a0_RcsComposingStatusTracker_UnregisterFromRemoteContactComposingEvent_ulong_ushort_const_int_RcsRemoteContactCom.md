# RcsComposingStatusTracker::UnregisterFromRemoteContactComposingEvent(ulong,ushort const *,int,RcsRemoteContactComposingNotification *)

- ea: `0x1800932a0`
- end: `0x18009348c`
- name: `?UnregisterFromRemoteContactComposingEvent@RcsComposingStatusTracker@@QEAAJKPEBGHPEAURcsRemoteContactComposingNotification@@@Z`
- size: `492`
- prototype: `__int64 __usercall@<rax>(RcsComposingStatusTracker *__hidden this@<rcx>, unsigned int@<edx>, const unsigned __int16 *@<r8>, int@<r9d>, struct RcsRemoteContactComposingNotification *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800f5e70`

## callees

- `0x180008f0c`
- `0x180018c20`
- `0x18001b340`
- `0x18006db44`
- `0x180072ccc`
- `0x18007d240`
- `0x180093230`
- `0x1800932a0`
- `0x180094d50`
- `0x1800a847c`
- `0x1800efd60`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180093369`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180093369`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180093337`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180093337`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800933d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800933d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180093415`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180093464`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180093415`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180093464`

## string_xrefs

- `0x1800932cc`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\rcscomposingstatustracker.cpp`
- `0x18009339e`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\rcscomposingstatustracker.cpp`
- `0x1800933ff`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\rcscomposingstatustracker.cpp`

## pseudocode

```c
__int64 __fastcall RcsComposingStatusTracker::UnregisterFromRemoteContactComposingEvent(
        RcsComposingStatusTracker *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        struct RcsRemoteContactComposingNotification *a5)
{
  unsigned int v9; // ebx
  __int64 v10; // rcx
  int ProcessedChatId; // eax
  __int64 v12; // r9
  RcsServiceManager *v13; // rbx
  struct RcsChatAdapter *ExistingChatAdapter; // rbx
  int v15; // eax
  unsigned int v16; // r14d
  LPVOID Context; // [rsp+30h] [rbp-40h] BYREF
  __int64 v19; // [rsp+38h] [rbp-38h] BYREF
  struct _GUID v20; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int16 *v21[4]; // [rsp+50h] [rbp-20h] BYREF
  void **fPending; // [rsp+90h] [rbp+20h] BYREF

  if ( !*((_DWORD *)this + 4) )
  {
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v21);
    v20 = 0;
    ProcessedChatId = RcsComposingStatusTracker::_GetProcessedChatId(v10, a3, a4, v21);
    v9 = ProcessedChatId;
    if ( ProcessedChatId < 0 )
    {
      v12 = 131;
LABEL_10:
      Log_HREvent(
        (unsigned int)ProcessedChatId,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\rcscomposingstatustracker.cpp",
        v12);
LABEL_19:
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v21);
      return v9;
    }
    LODWORD(fPending) = 0;
    Context = 0;
    InitOnceBeginInitialize(&stru_18015DCD8, 0, (PBOOL)&fPending, &Context);
    v13 = (RcsServiceManager *)Context;
    if ( !Context )
    {
      v13 = (RcsServiceManager *)qword_18015DCE0;
      RcsServiceManager::RcsServiceManager((RcsServiceManager *)qword_18015DCE0);
      v19 = 0;
      InitOnceComplete(&stru_18015DCD8, 0, qword_18015DCE0);
      tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&v19);
    }
    ProcessedChatId = RcsServiceManager::GetImsClientIdForProviderId(v13, a2, &v20);
    v9 = ProcessedChatId;
    if ( ProcessedChatId != -2147023728 )
    {
      if ( ProcessedChatId < 0 )
      {
        v12 = 140;
        goto LABEL_10;
      }
      ExistingChatAdapter = RcsComposingStatusTracker::_GetExistingChatAdapter(this, &v20, v21[0]);
      if ( ExistingChatAdapter )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
        v15 = (*(__int64 (__fastcall **)(struct RcsChatAdapter *, struct RcsRemoteContactComposingNotification *))(*(_QWORD *)ExistingChatAdapter + 56LL))(
                ExistingChatAdapter,
                a5);
        v16 = v15;
        if ( v15 < 0 )
        {
          Log_HREvent(
            (unsigned int)v15,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\rcscomposingstatustracker.cpp",
            154);
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
          v9 = v16;
          goto LABEL_19;
        }
        if ( !(*(unsigned int (__fastcall **)(struct RcsChatAdapter *))(*(_QWORD *)ExistingChatAdapter + 80LL))(ExistingChatAdapter) )
        {
          utl::_Tree<_GUID,utl::pair<_GUID const,utl::unique_ptr<RcsEndUserMessageTracker::RcsEndUserMessageInfo,utl::default_delete<RcsEndUserMessageTracker::RcsEndUserMessageInfo>>>,GuidComparator,utl::allocator<utl::pair<_GUID const,utl::unique_ptr<RcsEndUserMessageTracker::RcsEndUserMessageInfo,utl::default_delete<RcsEndUserMessageTracker::RcsEndUserMessageInfo>>>>,0>::find<void>(
            (__int64)this + 72,
            &fPending,
            &v20);
          if ( (void **)((char *)this + 72) != fPending )
            RcsShutdownableMap<RcsChatAdapter>::erase((char *)fPending[5] + 8, v21[0]);
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
      }
    }
    v9 = 0;
    goto LABEL_19;
  }
  v9 = -2147418113;
  Log_HREvent(
    2147549183LL,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\rcscomposingstatustracker.cpp",
    123);
  return v9;
}

```

## disassembly

```asm
0x1800932a0  mov     [rsp-18h+arg_8], rbx
0x1800932a5  mov     [rsp-18h+arg_10], rsi
0x1800932aa  push    rbp
0x1800932ab  push    rdi
0x1800932ac  push    r14
0x1800932ae  mov     rbp, rsp
0x1800932b1  sub     rsp, 70h
0x1800932b5  cmp     dword ptr [rcx+10h], 0
0x1800932b9  mov     ebx, r9d
0x1800932bc  mov     rsi, r8
0x1800932bf  mov     r14d, edx
0x1800932c2  mov     rdi, rcx
0x1800932c5  jz      short loc_1800932E7
0x1800932c7  mov     ebx, 8000FFFFh
0x1800932cc  lea     r8, aOnecoreuapBase_113; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800932d3  mov     ecx, ebx
0x1800932d5  mov     r9d, 7Bh ; '{'
0x1800932db  xor     edx, edx
0x1800932dd  call    Log_HREvent
0x1800932e2  jmp     loc_180093475
0x1800932e7  lea     rcx, [rbp+var_20]; void *
0x1800932eb  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800932f0  xorps   xmm0, xmm0
0x1800932f3  lea     r9, [rbp+var_20]
0x1800932f7  mov     r8d, ebx
0x1800932fa  mov     rdx, rsi
0x1800932fd  movups  xmmword ptr [rbp+var_30.Data1], xmm0
0x180093301  call    ?_GetProcessedChatId@RcsComposingStatusTracker@@AEAAJPEBGHPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; RcsComposingStatusTracker::_GetProcessedChatId(ushort const *,int,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180093306  mov     ebx, eax
0x180093308  test    eax, eax
0x18009330a  jns     short loc_180093317
0x18009330c  mov     r9d, 83h
0x180093312  jmp     loc_18009339E
0x180093317  lea     r9, [rbp+Context]; lpContext
0x18009331b  mov     dword ptr [rbp+fPending], 0
0x180093322  lea     r8, [rbp+fPending]; fPending
0x180093326  mov     [rbp+Context], 0
0x18009332e  xor     edx, edx; dwFlags
0x180093330  lea     rcx, stru_18015DCD8; lpInitOnce
0x180093337  call    cs:__imp_InitOnceBeginInitialize
0x18009333d  mov     rbx, [rbp+Context]
0x180093341  test    rbx, rbx
0x180093344  jnz     short loc_180093378
0x180093346  lea     rbx, qword_18015DCE0
0x18009334d  mov     rcx, rbx; this
0x180093350  call    ??0RcsServiceManager@@QEAA@XZ; RcsServiceManager::RcsServiceManager(void)
0x180093355  mov     r8, rbx; lpContext
0x180093358  mov     [rbp+var_38], 0
0x180093360  xor     edx, edx; dwFlags
0x180093362  lea     rcx, stru_18015DCD8; lpInitOnce
0x180093369  call    cs:__imp_InitOnceComplete
0x18009336f  lea     rcx, [rbp+var_38]
0x180093373  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x180093378  lea     r8, [rbp+var_30]; struct _GUID *
0x18009337c  mov     edx, r14d; unsigned int
0x18009337f  mov     rcx, rbx; this
0x180093382  call    ?GetImsClientIdForProviderId@RcsServiceManager@@QEAAJKAEAU_GUID@@@Z; RcsServiceManager::GetImsClientIdForProviderId(ulong,_GUID &)
0x180093387  mov     ebx, eax
0x180093389  cmp     eax, 80070490h
0x18009338e  jz      loc_18009346A
0x180093394  test    eax, eax
0x180093396  jns     short loc_1800933B6
0x180093398  mov     r9d, 8Ch
0x18009339e  lea     r8, aOnecoreuapBase_113; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800933a5  mov     edx, 1
0x1800933aa  mov     ecx, eax
0x1800933ac  call    Log_HREvent
0x1800933b1  jmp     loc_18009346C
0x1800933b6  mov     r8, [rbp+var_20]; unsigned __int16 *
0x1800933ba  lea     rdx, [rbp+var_30]; struct _GUID *
0x1800933be  mov     rcx, rdi; this
0x1800933c1  call    ?_GetExistingChatAdapter@RcsComposingStatusTracker@@AEAAPEAVRcsChatAdapter@@AEBU_GUID@@PEBG@Z; RcsComposingStatusTracker::_GetExistingChatAdapter(_GUID const &,ushort const *)
0x1800933c6  mov     rbx, rax
0x1800933c9  test    rax, rax
0x1800933cc  jz      loc_18009346A
0x1800933d2  lea     rsi, [rdi+18h]
0x1800933d6  mov     rcx, rsi; lpCriticalSection
0x1800933d9  call    cs:__imp_EnterCriticalSection
0x1800933df  mov     rcx, [rbx]
0x1800933e2  mov     rdx, [rbp+arg_20]
0x1800933e6  mov     rax, [rcx+38h]
0x1800933ea  mov     rcx, rbx
0x1800933ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800933f2  mov     r14d, eax
0x1800933f5  test    eax, eax
0x1800933f7  jns     short loc_180093420
0x1800933f9  mov     r9d, 9Ah
0x1800933ff  lea     r8, aOnecoreuapBase_113; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180093406  mov     edx, 1
0x18009340b  mov     ecx, eax
0x18009340d  call    Log_HREvent
0x180093412  mov     rcx, rsi; lpCriticalSection
0x180093415  call    cs:__imp_LeaveCriticalSection
0x18009341b  mov     ebx, r14d
0x18009341e  jmp     short loc_18009346C
0x180093420  mov     rax, [rbx]
0x180093423  mov     rcx, rbx
0x180093426  mov     rax, [rax+50h]
0x18009342a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009342f  test    eax, eax
0x180093431  jnz     short loc_180093461
0x180093433  lea     rbx, [rdi+48h]
0x180093437  mov     rcx, rbx
0x18009343a  lea     r8, [rbp+var_30]
0x18009343e  lea     rdx, [rbp+fPending]
0x180093442  call    ??$find@X@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@V?$unique_ptr@URcsEndUserMessageInfo@RcsEndUserMessageTracker@@U?$default_delete@URcsEndUserMessageInfo@RcsEndUserMessageTracker@@@utl@@@utl@@@utl@@UGuidComparator@@V?$allocator@U?$pair@$$CBU_GUID@@V?$unique_ptr@URcsEndUserMessageInfo@RcsEndUserMessageTracker@@U?$default_delete@URcsEndUserMessageInfo@RcsEndUserMessageTracker@@@utl@@@utl@@@utl@@@3@$0A@@utl@@QEAA?AV?$_TreeIt@U?$pair@$$CBU_GUID@@V?$unique_ptr@URcsEndUserMessageInfo@RcsEndUserMessageTracker@@U?$default_delete@URcsEndUserMessageInfo@RcsEndUserMessageTracker@@@utl@@@utl@@@utl@@@1@AEBU_GUID@@@Z; utl::_Tree<_GUID,utl::pair<_GUID const,utl::unique_ptr<RcsEndUserMessageTracker::RcsEndUserMessageInfo,utl::default_delete<RcsEndUserMessageTracker::RcsEndUserMessageInfo>>>,GuidComparator,utl::allocator<utl::pair<_GUID const,utl::unique_ptr<RcsEndUserMessageTracker::RcsEndUserMessageInfo,utl::default_delete<RcsEndUserMessageTracker::RcsEndUserMessageInfo>>>>,0>::find<void>(_GUID const &)
0x180093447  mov     rax, [rbp+fPending]
0x18009344b  cmp     rbx, rax
0x18009344e  jz      short loc_180093461
0x180093450  mov     rcx, [rax+28h]
0x180093454  mov     rdx, [rbp+var_20]
0x180093458  add     rcx, 8
0x18009345c  call    ?erase@?$RcsShutdownableMap@VRcsChatAdapter@@@@QEAAHPEBG@Z; RcsShutdownableMap<RcsChatAdapter>::erase(ushort const *)
0x180093461  mov     rcx, rsi; lpCriticalSection
0x180093464  call    cs:__imp_LeaveCriticalSection
0x18009346a  xor     ebx, ebx
0x18009346c  lea     rcx, [rbp+var_20]; void *
0x180093470  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180093475  lea     r11, [rsp+70h+var_s0]
0x18009347a  mov     eax, ebx
0x18009347c  mov     rbx, [r11+28h]
0x180093480  mov     rsi, [r11+30h]
0x180093484  mov     rsp, r11
0x180093487  pop     r14
0x180093489  pop     rdi
0x18009348a  pop     rbp
0x18009348b  retn
```
