# InterceptThrottlingManager::NotifyInterceptBegin(uint)

- ea: `0x140047f80`
- end: `0x1400481e6`
- name: `?NotifyInterceptBegin@InterceptThrottlingManager@@QEAAXI@Z`
- size: `614`
- prototype: `void __fastcall(InterceptThrottlingManager *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140047f60`

## callees

- `0x1400014a4`
- `0x140047f80`
- `0x140057030`
- `0x14005711c`
- `0x140132960`
- `0x140132cb0`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140048170`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140048170`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1400480be`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1400480be`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14004800d`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14004800d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140047fca`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400481aa`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140047fca`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400481aa`

## pseudocode

```c
void __fastcall InterceptThrottlingManager::NotifyInterceptBegin(InterceptThrottlingManager *this, unsigned int a2)
{
  __int64 v3; // rdi
  __int64 v4; // rcx
  __int64 v5; // r8
  WINBOOL fPending; // [rsp+30h] [rbp-19h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp-11h] BYREF
  EVENT_DESCRIPTOR Context; // [rsp+40h] [rbp-9h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp+7h] BYREF
  char *v10; // [rsp+60h] [rbp+17h]
  int v11; // [rsp+68h] [rbp+1Fh]
  int v12; // [rsp+6Ch] [rbp+23h]
  char *v13; // [rsp+70h] [rbp+27h]
  __int64 v14; // [rsp+78h] [rbp+2Fh]

  PerformanceCount.QuadPart = 0;
  v3 = *((_QWORD *)this + 15) + 80LL * a2;
  ++*(_QWORD *)(v3 + 24);
  *(_DWORD *)(v3 + 72) = 1;
  QueryPerformanceCounter(&PerformanceCount);
  if ( PerformanceCount.QuadPart - *((_QWORD *)this + 12) >= *((_QWORD *)this + 11) )
  {
    if ( !_interlockedbittestandset((volatile signed __int32 *)this + 6, 2u) )
    {
      *(_QWORD *)&Context.Id = 0;
      fPending = 0;
      if ( InitOnceBeginInitialize(&`VmWorkerInterceptTrace::Instance'::`2'::wrapper, 0, &fPending, (LPVOID *)&Context)
        && fPending )
      {
        qword_1403B7ED8 = 0;
        *(_QWORD *)&Context.Id = &qword_1403B7ED0;
        byte_1403B7EE0 = 0;
        dword_1403B7EE4 = 0;
        qword_1403B7ED0 = (__int64)&GuestStateFileTraceProvider::`vftable';
        CallbackContext = &`VmWorkerInterceptTrace::StaticHandle::StaticHandle'::`2'::__hInner;
        atexit(_lambda_c638a0893179ad876d752144997a212c_::_lambda_invoker_cdecl_);
        qword_1403B7ED8 = (__int64)CallbackContext;
        byte_1403B7EE0 = 1;
        TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
        dword_1403B7EE4 = 1;
        (*(void (__fastcall **)(__int64 *))(qword_1403B7ED0 + 8))(&qword_1403B7ED0);
        InitOnceComplete(&`VmWorkerInterceptTrace::Instance'::`2'::wrapper, 0, &qword_1403B7ED0);
      }
      v4 = *(_QWORD *)(*(_QWORD *)&Context.Id + 8LL);
      if ( *(_DWORD *)v4 > 4u )
      {
        v14 = 16;
        v13 = (char *)this + 188;
        UserData.Ptr = *(_QWORD *)(v4 + 8);
        *(_QWORD *)&Context.Id = 0x40B000000LL;
        Context.Keyword = 0;
        UserData.Size = *(unsigned __int16 *)UserData.Ptr;
        v10 = byte_1403601C9;
        UserData.Reserved = 2;
        v11 = 30;
        v12 = 1;
        fPending = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(*(_QWORD *)(v4 + 32), &Context, 0, 0, 3u, &UserData);
      }
    }
    InterceptThrottlingManager::AdjustVpBalance(
      this,
      (struct InterceptThrottlingManager::_VP_INTERCEPT_INFO *)v3,
      PerformanceCount.QuadPart);
    v5 = *(_QWORD *)(v3 + 16);
    if ( v5 < 0 )
    {
      InterceptThrottlingManager::DelayIntercept(
        this,
        (struct InterceptThrottlingManager::_VP_INTERCEPT_INFO *)v3,
        -v5,
        PerformanceCount.QuadPart);
      QueryPerformanceCounter(&PerformanceCount);
      InterceptThrottlingManager::AdjustVpBalance(
        this,
        (struct InterceptThrottlingManager::_VP_INTERCEPT_INFO *)v3,
        PerformanceCount.QuadPart);
    }
  }
}

```

## disassembly

```asm
0x140047f80  mov     [rsp-8+arg_18], rbx
0x140047f85  push    rbp
0x140047f86  push    rdi
0x140047f87  push    r14
0x140047f89  lea     rbp, [rsp-47h]
0x140047f8e  sub     rsp, 90h
0x140047f95  mov     rax, cs:__security_cookie
0x140047f9c  xor     rax, rsp
0x140047f9f  mov     [rbp+57h+var_20], rax
0x140047fa3  mov     eax, edx
0x140047fa5  mov     rbx, rcx
0x140047fa8  xor     r14d, r14d
0x140047fab  mov     qword ptr [rbp+57h+PerformanceCount], r14
0x140047faf  lea     rdi, [rax+rax*4]
0x140047fb3  shl     rdi, 4
0x140047fb7  add     rdi, [rcx+78h]
0x140047fbb  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x140047fbf  inc     qword ptr [rdi+18h]
0x140047fc3  mov     dword ptr [rdi+48h], 1
0x140047fca  call    cs:__imp_QueryPerformanceCounter
0x140047fd1  nop     dword ptr [rax+rax+00h]
0x140047fd6  mov     rax, qword ptr [rbp+57h+PerformanceCount]
0x140047fda  sub     rax, [rbx+60h]
0x140047fde  cmp     rax, [rbx+58h]
0x140047fe2  jl      loc_1400481C5
0x140047fe8  lock bts dword ptr [rbx+18h], 2
0x140047fee  jb      loc_14004817C
0x140047ff4  lea     r9, [rbp+57h+Context]; lpContext
0x140047ff8  mov     [rbp+57h+Context], r14
0x140047ffc  lea     r8, [rbp+57h+fPending]; fPending
0x140048000  mov     [rbp+57h+fPending], r14d
0x140048004  xor     edx, edx; dwFlags
0x140048006  lea     rcx, ?wrapper@?1??Instance@VmWorkerInterceptTrace@@KAPEAV2@XZ@4V?$static_lazy@VVmWorkerInterceptTrace@@@details@wil@@A; lpInitOnce
0x14004800d  call    cs:__imp_InitOnceBeginInitialize
0x140048014  nop     dword ptr [rax+rax+00h]
0x140048019  test    eax, eax
0x14004801b  jz      loc_1400480D2
0x140048021  cmp     [rbp+57h+fPending], r14d
0x140048025  jz      loc_1400480D2
0x14004802b  mov     [rsp+0A0h+arg_10], rsi
0x140048033  lea     rax, ??_7GuestStateFileTraceProvider@@6B@; const GuestStateFileTraceProvider::`vftable'
0x14004803a  lea     rsi, qword_1403B7ED0
0x140048041  mov     cs:qword_1403B7ED8, r14
0x140048048  mov     [rbp+57h+Context], rsi
0x14004804c  mov     cs:byte_1403B7EE0, r14b
0x140048053  mov     cs:dword_1403B7EE4, r14d
0x14004805a  mov     cs:qword_1403B7ED0, rax
0x140048061  lea     rax, ?__hInner@?1???0StaticHandle@VmWorkerInterceptTrace@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `VmWorkerInterceptTrace::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x140048068  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_c638a0893179ad876d752144997a212c_@@CA@XZ; void (__cdecl *)()
0x14004806f  mov     cs:CallbackContext, rax
0x140048076  call    atexit
0x14004807b  mov     rcx, cs:CallbackContext; CallbackContext
0x140048082  mov     cs:qword_1403B7ED8, rcx
0x140048089  mov     cs:byte_1403B7EE0, 1
0x140048090  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x140048095  mov     rax, cs:qword_1403B7ED0
0x14004809c  mov     rcx, rsi
0x14004809f  mov     cs:dword_1403B7EE4, 1
0x1400480a9  mov     rax, [rax+8]
0x1400480ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400480b2  mov     r8, rsi; lpContext
0x1400480b5  lea     rcx, ?wrapper@?1??Instance@VmWorkerInterceptTrace@@KAPEAV2@XZ@4V?$static_lazy@VVmWorkerInterceptTrace@@@details@wil@@A; lpInitOnce
0x1400480bc  xor     edx, edx; dwFlags
0x1400480be  call    cs:__imp_InitOnceComplete
0x1400480c5  nop     dword ptr [rax+rax+00h]
0x1400480ca  mov     rsi, [rsp+0A0h+arg_10]
0x1400480d2  mov     rax, [rbp+57h+Context]
0x1400480d6  mov     rcx, [rax+8]
0x1400480da  mov     eax, [rcx]
0x1400480dc  cmp     eax, 4
0x1400480df  jbe     loc_14004817C
0x1400480e5  lea     rax, [rbx+0BCh]
0x1400480ec  mov     [rbp+57h+var_28], 10h
0x1400480f4  mov     [rbp+57h+var_30], rax
0x1400480f8  lea     rdx, _TraceLoggingMetadata
0x1400480ff  movzx   eax, cs:word_1403601BF
0x140048106  xor     r9d, r9d; RelatedActivityId
0x140048109  mov     dword ptr [rbp+57h+Context+4], eax
0x14004810c  xor     r8d, r8d; ActivityId
0x14004810f  mov     rax, [rcx+8]
0x140048113  mov     [rbp+57h+var_50.Ptr], rax
0x140048117  mov     dword ptr [rbp+57h+Context], 0B000000h
0x14004811e  mov     [rbp+57h+var_58], r14
0x140048122  movzx   eax, word ptr [rax]
0x140048125  mov     [rbp+57h+var_50.Size], eax
0x140048128  lea     rax, byte_1403601C9
0x14004812f  mov     [rbp+57h+var_40], rax
0x140048133  lea     rax, _TraceLoggingMetadataEnd
0x14004813a  sub     eax, edx
0x14004813c  mov     dword ptr [rbp+57h+var_50.0Ch], 2
0x140048143  mov     [rbp+57h+var_38], 1Eh
0x14004814a  lea     rdx, [rbp+57h+Context]; EventDescriptor
0x14004814e  mov     [rbp+57h+var_34], 1
0x140048155  mov     [rbp+57h+fPending], eax
0x140048158  mov     eax, [rbp+57h+fPending]
0x14004815b  mov     rcx, [rcx+20h]; RegHandle
0x14004815f  lea     rax, [rbp+57h+var_50]
0x140048163  mov     [rsp+0A0h+UserData], rax; UserData
0x140048168  mov     [rsp+0A0h+UserDataCount], 3; UserDataCount
0x140048170  call    cs:__imp_EventWriteTransfer
0x140048177  nop     dword ptr [rax+rax+00h]
0x14004817c  mov     r8, qword ptr [rbp+57h+PerformanceCount]; __int64
0x140048180  mov     rdx, rdi; struct InterceptThrottlingManager::_VP_INTERCEPT_INFO *
0x140048183  mov     rcx, rbx; this
0x140048186  call    ?AdjustVpBalance@InterceptThrottlingManager@@AEAAXPEAU_VP_INTERCEPT_INFO@1@_J@Z; InterceptThrottlingManager::AdjustVpBalance(InterceptThrottlingManager::_VP_INTERCEPT_INFO *,__int64)
0x14004818b  mov     r8, [rdi+10h]
0x14004818f  test    r8, r8
0x140048192  jns     short loc_1400481C5
0x140048194  mov     r9, qword ptr [rbp+57h+PerformanceCount]; __int64
0x140048198  neg     r8; __int64
0x14004819b  mov     rdx, rdi; struct InterceptThrottlingManager::_VP_INTERCEPT_INFO *
0x14004819e  mov     rcx, rbx; this
0x1400481a1  call    ?DelayIntercept@InterceptThrottlingManager@@AEAAXPEAU_VP_INTERCEPT_INFO@1@_J1@Z; InterceptThrottlingManager::DelayIntercept(InterceptThrottlingManager::_VP_INTERCEPT_INFO *,__int64,__int64)
0x1400481a6  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x1400481aa  call    cs:__imp_QueryPerformanceCounter
0x1400481b1  nop     dword ptr [rax+rax+00h]
0x1400481b6  mov     r8, qword ptr [rbp+57h+PerformanceCount]; __int64
0x1400481ba  mov     rdx, rdi; struct InterceptThrottlingManager::_VP_INTERCEPT_INFO *
0x1400481bd  mov     rcx, rbx; this
0x1400481c0  call    ?AdjustVpBalance@InterceptThrottlingManager@@AEAAXPEAU_VP_INTERCEPT_INFO@1@_J@Z; InterceptThrottlingManager::AdjustVpBalance(InterceptThrottlingManager::_VP_INTERCEPT_INFO *,__int64)
0x1400481c5  mov     rcx, [rbp+57h+var_20]
0x1400481c9  xor     rcx, rsp; StackCookie
0x1400481cc  call    __security_check_cookie
0x1400481d1  mov     rbx, [rsp+0A0h+arg_18]
0x1400481d9  add     rsp, 90h
0x1400481e0  pop     r14
0x1400481e2  pop     rdi
0x1400481e3  pop     rbp
0x1400481e4  retn
```
