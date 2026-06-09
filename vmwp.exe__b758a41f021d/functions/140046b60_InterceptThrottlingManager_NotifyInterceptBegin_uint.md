# InterceptThrottlingManager::NotifyInterceptBegin(uint)

- ea: `0x140046b60`
- end: `0x140046dc6`
- name: `?NotifyInterceptBegin@InterceptThrottlingManager@@QEAAXI@Z`
- size: `614`
- prototype: `void __fastcall(InterceptThrottlingManager *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140046b40`

## callees

- `0x1400014a4`
- `0x140046b60`
- `0x1400579a0`
- `0x140057a8c`
- `0x14011ea40`
- `0x14011ed90`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140046d50`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140046d50`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140046bed`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140046bed`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140046c9e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140046c9e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140046baa`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140046d8a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140046baa`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140046d8a`

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
  int *v10; // [rsp+60h] [rbp+17h]
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
        qword_1403C4468 = 0;
        *(_QWORD *)&Context.Id = &qword_1403C4460;
        byte_1403C4470 = 0;
        dword_1403C4474 = 0;
        qword_1403C4460 = (__int64)&GuestStateFileTraceProvider::`vftable';
        CallbackContext = &`VmWorkerInterceptTrace::StaticHandle::StaticHandle'::`2'::__hInner;
        atexit(_lambda_c638a0893179ad876d752144997a212c_::_lambda_invoker_cdecl_);
        qword_1403C4468 = (__int64)CallbackContext;
        byte_1403C4470 = 1;
        TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
        dword_1403C4474 = 1;
        (*(void (__fastcall **)(__int64 *))(qword_1403C4460 + 8))(&qword_1403C4460);
        InitOnceComplete(&`VmWorkerInterceptTrace::Instance'::`2'::wrapper, 0, &qword_1403C4460);
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
        v10 = &dword_14036B224;
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
0x140046b60  mov     [rsp-8+arg_18], rbx
0x140046b65  push    rbp
0x140046b66  push    rdi
0x140046b67  push    r14
0x140046b69  lea     rbp, [rsp-47h]
0x140046b6e  sub     rsp, 90h
0x140046b75  mov     rax, cs:__security_cookie
0x140046b7c  xor     rax, rsp
0x140046b7f  mov     [rbp+57h+var_20], rax
0x140046b83  mov     eax, edx
0x140046b85  mov     rbx, rcx
0x140046b88  xor     r14d, r14d
0x140046b8b  mov     qword ptr [rbp+57h+PerformanceCount], r14
0x140046b8f  lea     rdi, [rax+rax*4]
0x140046b93  shl     rdi, 4
0x140046b97  add     rdi, [rcx+78h]
0x140046b9b  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x140046b9f  inc     qword ptr [rdi+18h]
0x140046ba3  mov     dword ptr [rdi+48h], 1
0x140046baa  call    cs:__imp_QueryPerformanceCounter
0x140046bb1  nop     dword ptr [rax+rax+00h]
0x140046bb6  mov     rax, qword ptr [rbp+57h+PerformanceCount]
0x140046bba  sub     rax, [rbx+60h]
0x140046bbe  cmp     rax, [rbx+58h]
0x140046bc2  jl      loc_140046DA5
0x140046bc8  lock bts dword ptr [rbx+18h], 2
0x140046bce  jb      loc_140046D5C
0x140046bd4  lea     r9, [rbp+57h+Context]; lpContext
0x140046bd8  mov     [rbp+57h+Context], r14
0x140046bdc  lea     r8, [rbp+57h+fPending]; fPending
0x140046be0  mov     [rbp+57h+fPending], r14d
0x140046be4  xor     edx, edx; dwFlags
0x140046be6  lea     rcx, ?wrapper@?1??Instance@VmWorkerInterceptTrace@@KAPEAV2@XZ@4V?$static_lazy@VVmWorkerInterceptTrace@@@details@wil@@A; lpInitOnce
0x140046bed  call    cs:__imp_InitOnceBeginInitialize
0x140046bf4  nop     dword ptr [rax+rax+00h]
0x140046bf9  test    eax, eax
0x140046bfb  jz      loc_140046CB2
0x140046c01  cmp     [rbp+57h+fPending], r14d
0x140046c05  jz      loc_140046CB2
0x140046c0b  mov     [rsp+0A0h+arg_10], rsi
0x140046c13  lea     rax, ??_7GuestStateFileTraceProvider@@6B@; const GuestStateFileTraceProvider::`vftable'
0x140046c1a  lea     rsi, qword_1403C4460
0x140046c21  mov     cs:qword_1403C4468, r14
0x140046c28  mov     [rbp+57h+Context], rsi
0x140046c2c  mov     cs:byte_1403C4470, r14b
0x140046c33  mov     cs:dword_1403C4474, r14d
0x140046c3a  mov     cs:qword_1403C4460, rax
0x140046c41  lea     rax, ?__hInner@?1???0StaticHandle@VmWorkerInterceptTrace@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `VmWorkerInterceptTrace::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x140046c48  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_c638a0893179ad876d752144997a212c_@@CA@XZ; void (__cdecl *)()
0x140046c4f  mov     cs:CallbackContext, rax
0x140046c56  call    atexit
0x140046c5b  mov     rcx, cs:CallbackContext; CallbackContext
0x140046c62  mov     cs:qword_1403C4468, rcx
0x140046c69  mov     cs:byte_1403C4470, 1
0x140046c70  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x140046c75  mov     rax, cs:qword_1403C4460
0x140046c7c  mov     rcx, rsi
0x140046c7f  mov     cs:dword_1403C4474, 1
0x140046c89  mov     rax, [rax+8]
0x140046c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046c92  mov     r8, rsi; lpContext
0x140046c95  lea     rcx, ?wrapper@?1??Instance@VmWorkerInterceptTrace@@KAPEAV2@XZ@4V?$static_lazy@VVmWorkerInterceptTrace@@@details@wil@@A; lpInitOnce
0x140046c9c  xor     edx, edx; dwFlags
0x140046c9e  call    cs:__imp_InitOnceComplete
0x140046ca5  nop     dword ptr [rax+rax+00h]
0x140046caa  mov     rsi, [rsp+0A0h+arg_10]
0x140046cb2  mov     rax, [rbp+57h+Context]
0x140046cb6  mov     rcx, [rax+8]
0x140046cba  mov     eax, [rcx]
0x140046cbc  cmp     eax, 4
0x140046cbf  jbe     loc_140046D5C
0x140046cc5  lea     rax, [rbx+0BCh]
0x140046ccc  mov     [rbp+57h+var_28], 10h
0x140046cd4  mov     [rbp+57h+var_30], rax
0x140046cd8  lea     rdx, _TraceLoggingMetadata
0x140046cdf  movzx   eax, cs:word_14036B21A
0x140046ce6  xor     r9d, r9d; RelatedActivityId
0x140046ce9  mov     dword ptr [rbp+57h+Context+4], eax
0x140046cec  xor     r8d, r8d; ActivityId
0x140046cef  mov     rax, [rcx+8]
0x140046cf3  mov     [rbp+57h+var_50.Ptr], rax
0x140046cf7  mov     dword ptr [rbp+57h+Context], 0B000000h
0x140046cfe  mov     [rbp+57h+var_58], r14
0x140046d02  movzx   eax, word ptr [rax]
0x140046d05  mov     [rbp+57h+var_50.Size], eax
0x140046d08  lea     rax, dword_14036B224
0x140046d0f  mov     [rbp+57h+var_40], rax
0x140046d13  lea     rax, _TraceLoggingMetadataEnd
0x140046d1a  sub     eax, edx
0x140046d1c  mov     dword ptr [rbp+57h+var_50.0Ch], 2
0x140046d23  mov     [rbp+57h+var_38], 1Eh
0x140046d2a  lea     rdx, [rbp+57h+Context]; EventDescriptor
0x140046d2e  mov     [rbp+57h+var_34], 1
0x140046d35  mov     [rbp+57h+fPending], eax
0x140046d38  mov     eax, [rbp+57h+fPending]
0x140046d3b  mov     rcx, [rcx+20h]; RegHandle
0x140046d3f  lea     rax, [rbp+57h+var_50]
0x140046d43  mov     [rsp+0A0h+UserData], rax; UserData
0x140046d48  mov     [rsp+0A0h+UserDataCount], 3; UserDataCount
0x140046d50  call    cs:__imp_EventWriteTransfer
0x140046d57  nop     dword ptr [rax+rax+00h]
0x140046d5c  mov     r8, qword ptr [rbp+57h+PerformanceCount]; __int64
0x140046d60  mov     rdx, rdi; struct InterceptThrottlingManager::_VP_INTERCEPT_INFO *
0x140046d63  mov     rcx, rbx; this
0x140046d66  call    ?AdjustVpBalance@InterceptThrottlingManager@@AEAAXPEAU_VP_INTERCEPT_INFO@1@_J@Z; InterceptThrottlingManager::AdjustVpBalance(InterceptThrottlingManager::_VP_INTERCEPT_INFO *,__int64)
0x140046d6b  mov     r8, [rdi+10h]
0x140046d6f  test    r8, r8
0x140046d72  jns     short loc_140046DA5
0x140046d74  mov     r9, qword ptr [rbp+57h+PerformanceCount]; __int64
0x140046d78  neg     r8; __int64
0x140046d7b  mov     rdx, rdi; struct InterceptThrottlingManager::_VP_INTERCEPT_INFO *
0x140046d7e  mov     rcx, rbx; this
0x140046d81  call    ?DelayIntercept@InterceptThrottlingManager@@AEAAXPEAU_VP_INTERCEPT_INFO@1@_J1@Z; InterceptThrottlingManager::DelayIntercept(InterceptThrottlingManager::_VP_INTERCEPT_INFO *,__int64,__int64)
0x140046d86  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x140046d8a  call    cs:__imp_QueryPerformanceCounter
0x140046d91  nop     dword ptr [rax+rax+00h]
0x140046d96  mov     r8, qword ptr [rbp+57h+PerformanceCount]; __int64
0x140046d9a  mov     rdx, rdi; struct InterceptThrottlingManager::_VP_INTERCEPT_INFO *
0x140046d9d  mov     rcx, rbx; this
0x140046da0  call    ?AdjustVpBalance@InterceptThrottlingManager@@AEAAXPEAU_VP_INTERCEPT_INFO@1@_J@Z; InterceptThrottlingManager::AdjustVpBalance(InterceptThrottlingManager::_VP_INTERCEPT_INFO *,__int64)
0x140046da5  mov     rcx, [rbp+57h+var_20]
0x140046da9  xor     rcx, rsp; StackCookie
0x140046dac  call    __security_check_cookie
0x140046db1  mov     rbx, [rsp+0A0h+arg_18]
0x140046db9  add     rsp, 90h
0x140046dc0  pop     r14
0x140046dc2  pop     rdi
0x140046dc3  pop     rbp
0x140046dc4  retn
```
