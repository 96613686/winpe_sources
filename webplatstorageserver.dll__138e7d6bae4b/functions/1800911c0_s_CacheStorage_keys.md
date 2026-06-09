# s_CacheStorage_keys

- ea: `0x1800911c0`
- end: `0x1800913b6`
- name: `s_CacheStorage_keys`
- size: `502`
- prototype: `__int64 __fastcall(__int64, void *, unsigned int *, __int64 *)`
- caller_count: `0`
- callee_count: `15`
- tags: ``

## callees

- `0x18001f470`
- `0x1800245f0`
- `0x1800273f0`
- `0x18002d290`
- `0x18003f3f4`
- `0x18007e900`
- `0x180080fb0`
- `0x18008d860`
- `0x18008d8b8`
- `0x18008daec`
- `0x18008db4c`
- `0x18008e1d4`
- `0x18008e514`
- `0x1800911c0`
- `0x1800a6df8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180091351`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180091351`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18009137c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18009137c`

## string_xrefs

- `0x1800911eb`: `RPC CacheStorage_keys`
- `0x180091212`: `CS_CacheStorage_keys`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall s_CacheStorage_keys(__int64 a1, void *a2, unsigned int *a3, __int64 *a4)
{
  struct HangDetectionWatchDog *v7; // rdx
  unsigned int v8; // edi
  unsigned int v9; // eax
  __int64 v10; // rbx
  __int64 v11; // rcx
  volatile signed __int64 *v12; // rcx
  _BYTE *v14; // [rsp+20h] [rbp-208h] BYREF
  __int64 v15; // [rsp+28h] [rbp-200h]
  volatile signed __int64 *v16; // [rsp+30h] [rbp-1F8h] BYREF
  __int128 v17; // [rsp+40h] [rbp-1E8h] BYREF
  _BYTE v18[24]; // [rsp+50h] [rbp-1D8h] BYREF
  __int64 v19; // [rsp+68h] [rbp-1C0h]
  __int64 v20; // [rsp+70h] [rbp-1B8h]
  __int128 v21; // [rsp+78h] [rbp-1B0h] BYREF
  __int64 v22; // [rsp+88h] [rbp-1A0h]
  __int64 v23; // [rsp+90h] [rbp-198h]
  __int64 v24; // [rsp+98h] [rbp-190h]
  _BYTE v25[16]; // [rsp+A0h] [rbp-188h] BYREF
  _QWORD v26[43]; // [rsp+B0h] [rbp-178h] BYREF

  SetThreadName(L"RPC CacheStorage_keys");
  HangDetectionWatchDog::Activity::Activity((HangDetectionWatchDog::Activity *)&v16, v7);
  *a3 = 0;
  *a4 = 0;
  v8 = 0;
  wil::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v26,
    "CS_CacheStorage_keys");
  v26[0] = &CacheStorageTraceLogging::CS_CacheStorage_keys::`vftable';
  CacheStorageTraceLogging::CS_CacheStorage_keys::StartActivity(
    (CacheStorageTraceLogging::CS_CacheStorage_keys *)v26,
    a2);
  CacheStorageSession::Keys(a2, v18);
  v9 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v20);
  *a3 = v9;
  if ( v20 )
  {
    v21 = 0;
    v22 = 0;
    v23 = 0;
    v24 = 0;
    v14 = v18;
    v15 = v20 + v19;
    *(_QWORD *)&v17 = v18;
    *((_QWORD *)&v17 + 1) = v19;
    std::deque<std::wstring>::_Construct<std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<std::wstring>>>,std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<std::wstring>>>>(
      &v21,
      &v17,
      &v14);
    *a4 = AllocateStringBuffersForRpc(&v21);
    v9 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v20);
    *a3 = v9;
  }
  v10 = *a4;
  gsl::details::extent_type<-1>::extent_type<-1>(&v14, v9);
  v15 = v10;
  if ( v14 == (_BYTE *)-1LL || !v10 && v14 )
  {
    _o_terminate(v11);
    v8 = (unsigned int)v14;
  }
  else
  {
    v17 = *(_OWORD *)gsl::span<__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 const,-1>::span<__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 const,-1>(
                       v25,
                       &v14);
    CacheStorageTraceLogging::CS_CacheStorage_keys::Stop(v26, &v17);
    std::deque<std::wstring>::~deque<std::wstring>(v18);
    CacheStorageTraceLogging::CS_CacheStorage_keys::~CS_CacheStorage_keys((CacheStorageTraceLogging::CS_CacheStorage_keys *)v26);
  }
  v12 = v16;
  if ( _InterlockedExchangeAdd64(v16, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
    SetThreadpoolTimer(*((PTP_TIMER *)v12 + 1), 0, 0, 0);
  SetThreadName(&word_1800D6108);
  return v8;
}

```

## disassembly

```asm
0x1800911c0  mov     [rsp+arg_0], rbx
0x1800911c5  push    rsi
0x1800911c6  push    rdi
0x1800911c7  push    r14
0x1800911c9  sub     rsp, 210h
0x1800911d0  mov     rax, cs:__security_cookie
0x1800911d7  xor     rax, rsp
0x1800911da  mov     [rsp+228h+var_20], rax
0x1800911e2  mov     rsi, r9
0x1800911e5  mov     rbx, r8
0x1800911e8  mov     r14, rdx
0x1800911eb  lea     rcx, aRpcCachestorag_0; "RPC CacheStorage_keys"
0x1800911f2  call    SetThreadName
0x1800911f7  nop
0x1800911f8  lea     rcx, [rsp+228h+var_1F8]; this
0x1800911fd  call    ??0Activity@HangDetectionWatchDog@@QEAA@PEAV1@@Z; HangDetectionWatchDog::Activity::Activity(HangDetectionWatchDog *)
0x180091202  nop
0x180091203  mov     dword ptr [rbx], 0
0x180091209  mov     qword ptr [rsi], 0
0x180091210  xor     edi, edi
0x180091212  lea     rdx, aCsCachestorage_2; "CS_CacheStorage_keys"
0x180091219  lea     rcx, [rsp+228h+var_178]
0x180091221  call    ??0?$ActivityBase@VStorageServerProvider@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180091226  lea     rax, ??_7CS_CacheStorage_keys@CacheStorageTraceLogging@@6B@; const CacheStorageTraceLogging::CS_CacheStorage_keys::`vftable'
0x18009122d  mov     [rsp+228h+var_178], rax
0x180091235  mov     rdx, r14; void *
0x180091238  lea     rcx, [rsp+228h+var_178]; this
0x180091240  call    ?StartActivity@CS_CacheStorage_keys@CacheStorageTraceLogging@@QEAAXPEAX@Z; CacheStorageTraceLogging::CS_CacheStorage_keys::StartActivity(void *)
0x180091245  nop
0x180091246  lea     rdx, [rsp+228h+var_1D8]
0x18009124b  mov     rcx, r14
0x18009124e  call    ?Keys@CacheStorageSession@@QEAA?AV?$deque@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ; CacheStorageSession::Keys(void)
0x180091253  nop
0x180091254  mov     rcx, [rsp+228h+var_1B8]
0x180091259  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18009125e  mov     [rbx], eax
0x180091260  mov     rdx, [rsp+228h+var_1B8]
0x180091265  test    rdx, rdx
0x180091268  jz      short loc_1800912DF
0x18009126a  xorps   xmm0, xmm0
0x18009126d  movdqu  [rsp+228h+var_1B0], xmm0
0x180091273  mov     [rsp+228h+var_1A0], rdi
0x18009127b  mov     [rsp+228h+var_198], rdi
0x180091283  mov     [rsp+228h+var_190], rdi
0x18009128b  mov     rcx, [rsp+228h+var_1C0]
0x180091290  lea     rax, [rsp+228h+var_1D8]
0x180091295  mov     [rsp+228h+var_208], rax
0x18009129a  lea     rax, [rdx+rcx]
0x18009129e  mov     [rsp+228h+var_200], rax
0x1800912a3  lea     rax, [rsp+228h+var_1D8]
0x1800912a8  mov     qword ptr [rsp+228h+var_1E8], rax
0x1800912ad  mov     qword ptr [rsp+228h+var_1E8+8], rcx
0x1800912b2  lea     r8, [rsp+228h+var_208]
0x1800912b7  lea     rdx, [rsp+228h+var_1E8]
0x1800912bc  lea     rcx, [rsp+228h+var_1B0]
0x1800912c1  call    ??$_Construct@V?$_Deque_unchecked_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@V12@@?$deque@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXV?$_Deque_unchecked_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@V21@@Z; std::deque<std::wstring>::_Construct<std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<std::wstring>>>,std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<std::wstring>>>>(std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<std::wstring>>>,std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<std::wstring>>>)
0x1800912c6  lea     rcx, [rsp+228h+var_1B0]
0x1800912cb  call    ?AllocateStringBuffersForRpc@@YAPEAU__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001@@V?$deque@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; AllocateStringBuffersForRpc(std::deque<std::wstring>)
0x1800912d0  mov     [rsi], rax
0x1800912d3  mov     rcx, [rsp+228h+var_1B8]
0x1800912d8  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x1800912dd  mov     [rbx], eax
0x1800912df  mov     rbx, [rsi]
0x1800912e2  mov     edx, eax
0x1800912e4  lea     rcx, [rsp+228h+var_208]
0x1800912e9  call    ??0?$extent_type@$0?0@details@gsl@@QEAA@_K@Z; gsl::details::extent_type<-1>::extent_type<-1>(unsigned __int64)
0x1800912ee  mov     [rsp+228h+var_200], rbx
0x1800912f3  mov     rax, [rsp+228h+var_208]
0x1800912f8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800912fc  jz      short loc_180091351
0x1800912fe  test    rbx, rbx
0x180091301  jnz     short loc_180091308
0x180091303  test    rax, rax
0x180091306  jnz     short loc_180091351
0x180091308  lea     rdx, [rsp+228h+var_208]
0x18009130d  lea     rcx, [rsp+228h+var_188]
0x180091315  call    ??$?0U__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001@@$0?0$0?0$0A@@?$span@$$CBU__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001@@$0?0@gsl@@QEAA@AEBV?$span@U__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001@@$0?0@1@@Z; gsl::span<__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 const,-1>::span<__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 const,-1>(gsl::span<__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001,-1> const &)
0x18009131a  movups  xmm0, xmmword ptr [rax]
0x18009131d  movdqu  [rsp+228h+var_1E8], xmm0
0x180091323  lea     rdx, [rsp+228h+var_1E8]
0x180091328  lea     rcx, [rsp+228h+var_178]
0x180091330  call    ?Stop@CS_CacheStorage_keys@CacheStorageTraceLogging@@QEAAXV?$span@$$CBU__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001@@$0?0@gsl@@@Z; CacheStorageTraceLogging::CS_CacheStorage_keys::Stop(gsl::span<__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 const,-1>)
0x180091335  nop
0x180091336  lea     rcx, [rsp+228h+var_1D8]
0x18009133b  call    ??1?$deque@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::deque<std::wstring>::~deque<std::wstring>(void)
0x180091340  nop
0x180091341  lea     rcx, [rsp+228h+var_178]; this
0x180091349  call    ??1CS_CacheStorage_keys@CacheStorageTraceLogging@@QEAA@XZ; CacheStorageTraceLogging::CS_CacheStorage_keys::~CS_CacheStorage_keys(void)
0x18009134e  nop
0x18009134f  jmp     short loc_18009135C
0x180091351  call    cs:__imp__o_terminate
0x180091357  nop
0x180091358  mov     edi, dword ptr [rsp+228h+var_208]
0x18009135c  mov     rcx, [rsp+228h+var_1F8]
0x180091361  or      rax, 0FFFFFFFFFFFFFFFFh
0x180091365  lock xadd [rcx], rax
0x18009136a  cmp     rax, 1
0x18009136e  jnz     short loc_180091383
0x180091370  xor     r9d, r9d; msWindowLength
0x180091373  xor     r8d, r8d; msPeriod
0x180091376  xor     edx, edx; pftDueTime
0x180091378  mov     rcx, [rcx+8]; pti
0x18009137c  call    cs:__imp_SetThreadpoolTimer
0x180091382  nop
0x180091383  lea     rcx, word_1800D6108; lpWideCharStr
0x18009138a  call    SetThreadName
0x18009138f  nop
0x180091390  mov     eax, edi
0x180091392  mov     rcx, [rsp+228h+var_20]
0x18009139a  xor     rcx, rsp; StackCookie
0x18009139d  call    __security_check_cookie
0x1800913a2  mov     rbx, [rsp+228h+arg_0]
0x1800913aa  add     rsp, 210h
0x1800913b1  pop     r14
0x1800913b3  pop     rdi
0x1800913b4  pop     rsi
0x1800913b5  retn
```
