# s_Cache_matchAll

- ea: `0x180091660`
- end: `0x1800917f5`
- name: `s_Cache_matchAll`
- size: `405`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x18001f470`
- `0x1800245f0`
- `0x180024c2c`
- `0x180025b20`
- `0x1800273f0`
- `0x18002d290`
- `0x18003f3f4`
- `0x1800537e0`
- `0x180080fb0`
- `0x18008dbd0`
- `0x18008e43c`
- `0x18008ef50`
- `0x180091660`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18009178e`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180091795`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18009178e`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180091795`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800917c0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800917c0`

## string_xrefs

- `0x180091692`: `RPC Cache_matchAll`
- `0x1800916b9`: `CS_Cache_matchAll`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall s_Cache_matchAll(
        __int64 a1,
        void *a2,
        const struct __MIDL_RPCCacheStorage_0002 *a3,
        _DWORD *a4,
        char **a5)
{
  struct HangDetectionWatchDog *v8; // rdx
  unsigned int v9; // esi
  __int64 v10; // r9
  char *v11; // rbx
  __int64 v12; // rcx
  __int64 *v13; // rax
  __int64 v14; // rcx
  volatile signed __int64 *v15; // rcx
  _QWORD v17[2]; // [rsp+20h] [rbp-1C8h] BYREF
  volatile signed __int64 *v18; // [rsp+30h] [rbp-1B8h] BYREF
  _QWORD v19[4]; // [rsp+38h] [rbp-1B0h] BYREF
  unsigned __int64 v20; // [rsp+58h] [rbp-190h]
  _QWORD v21[43]; // [rsp+60h] [rbp-188h] BYREF

  SetThreadName((WCHAR *)L"RPC Cache_matchAll");
  HangDetectionWatchDog::Activity::Activity((HangDetectionWatchDog::Activity *)&v18, v8);
  *a4 = 0;
  *a5 = 0;
  v9 = 0;
  wil::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v21,
    "CS_Cache_matchAll");
  v21[0] = &CacheStorageTraceLogging::CS_Cache_matchAll::`vftable';
  CacheStorageTraceLogging::CS_Cache_matchAll::StartActivity((CacheStorageTraceLogging::CS_Cache_matchAll *)v21, a2, a3);
  LOBYTE(v10) = 1;
  CacheSession::Match(a2, v19, a3, v10);
  if ( v20 )
  {
    *a5 = ResponseMatch::s_AllocateResponseInfosForRpc(v19);
    *a4 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v20);
  }
  v11 = *a5;
  gsl::details::extent_type<-1>::extent_type<-1>(v17, (unsigned int)*a4);
  if ( v17[0] == -1 || !v11 && v17[0] )
  {
    _o_terminate(v12);
    v9 = v17[0];
  }
  else
  {
    v13 = (__int64 *)gsl::details::extent_type<-1>::extent_type<-1>(v17, v17[0]);
    v14 = *v13;
    if ( *v13 == -1 || !v11 && v14 )
    {
      _o_terminate(v14);
      __debugbreak();
    }
    v17[0] = *v13;
    v17[1] = v11;
    CacheStorageTraceLogging::CS_Cache_matchAll::Stop(v21, v17);
    std::deque<ResponseMatch>::~deque<ResponseMatch>(v19);
    CacheStorageTraceLogging::CS_Cache_matchAll::~CS_Cache_matchAll((CacheStorageTraceLogging::CS_Cache_matchAll *)v21);
  }
  v15 = v18;
  if ( _InterlockedExchangeAdd64(v18, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
    SetThreadpoolTimer(*((PTP_TIMER *)v15 + 1), 0, 0, 0);
  SetThreadName((WCHAR *)&word_1800D6108);
  return v9;
}

```

## disassembly

```asm
0x180091660  push    rbx
0x180091662  push    rsi
0x180091663  push    rdi
0x180091664  push    r14
0x180091666  push    r15
0x180091668  sub     rsp, 1C0h
0x18009166f  mov     rax, cs:__security_cookie
0x180091676  xor     rax, rsp
0x180091679  mov     [rsp+1E8h+var_30], rax
0x180091681  mov     rdi, r9
0x180091684  mov     r15, r8
0x180091687  mov     r14, rdx
0x18009168a  mov     rbx, [rsp+1E8h+arg_20]
0x180091692  lea     rcx, aRpcCacheMatcha; "RPC Cache_matchAll"
0x180091699  call    SetThreadName
0x18009169e  nop
0x18009169f  lea     rcx, [rsp+1E8h+var_1B8]; this
0x1800916a4  call    ??0Activity@HangDetectionWatchDog@@QEAA@PEAV1@@Z; HangDetectionWatchDog::Activity::Activity(HangDetectionWatchDog *)
0x1800916a9  nop
0x1800916aa  mov     dword ptr [rdi], 0
0x1800916b0  mov     qword ptr [rbx], 0
0x1800916b7  xor     esi, esi
0x1800916b9  lea     rdx, aCsCacheMatchal; "CS_Cache_matchAll"
0x1800916c0  lea     rcx, [rsp+1E8h+var_188]
0x1800916c5  call    ??0?$ActivityBase@VStorageServerProvider@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800916ca  lea     rax, ??_7CS_Cache_matchAll@CacheStorageTraceLogging@@6B@; const CacheStorageTraceLogging::CS_Cache_matchAll::`vftable'
0x1800916d1  mov     [rsp+1E8h+var_188], rax
0x1800916d6  mov     r8, r15; struct __MIDL_RPCCacheStorage_0002 *
0x1800916d9  mov     rdx, r14; void *
0x1800916dc  lea     rcx, [rsp+1E8h+var_188]; this
0x1800916e1  call    ?StartActivity@CS_Cache_matchAll@CacheStorageTraceLogging@@QEAAXPEAXPEBU__MIDL_RPCCacheStorage_0002@@@Z; CacheStorageTraceLogging::CS_Cache_matchAll::StartActivity(void *,__MIDL_RPCCacheStorage_0002 const *)
0x1800916e6  nop
0x1800916e7  mov     r9b, 1
0x1800916ea  mov     r8, r15
0x1800916ed  lea     rdx, [rsp+1E8h+var_1B0]
0x1800916f2  mov     rcx, r14
0x1800916f5  call    ?Match@CacheSession@@QEAA?AV?$deque@VResponseMatch@@V?$allocator@VResponseMatch@@@std@@@std@@PEBU__MIDL_RPCCacheStorage_0002@@_N@Z; CacheSession::Match(__MIDL_RPCCacheStorage_0002 const *,bool)
0x1800916fa  nop
0x1800916fb  cmp     [rsp+1E8h+var_190], rsi
0x180091700  jbe     short loc_18009171B
0x180091702  lea     rcx, [rsp+1E8h+var_1B0]
0x180091707  call    ?s_AllocateResponseInfosForRpc@ResponseMatch@@SAPEAU__MIDL_RPCCacheStorage_0003@@AEAV?$deque@VResponseMatch@@V?$allocator@VResponseMatch@@@std@@@std@@@Z; ResponseMatch::s_AllocateResponseInfosForRpc(std::deque<ResponseMatch> &)
0x18009170c  mov     [rbx], rax
0x18009170f  mov     rcx, [rsp+1E8h+var_190]
0x180091714  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180091719  mov     [rdi], eax
0x18009171b  mov     rbx, [rbx]
0x18009171e  mov     edx, [rdi]
0x180091720  lea     rcx, [rsp+1E8h+var_1C8]
0x180091725  call    ??0?$extent_type@$0?0@details@gsl@@QEAA@_K@Z; gsl::details::extent_type<-1>::extent_type<-1>(unsigned __int64)
0x18009172a  mov     rdx, [rsp+1E8h+var_1C8]
0x18009172f  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180091733  jz      short loc_180091795
0x180091735  test    rbx, rbx
0x180091738  jnz     short loc_18009173F
0x18009173a  test    rdx, rdx
0x18009173d  jnz     short loc_180091795
0x18009173f  lea     rcx, [rsp+1E8h+var_1C8]
0x180091744  call    ??0?$extent_type@$0?0@details@gsl@@QEAA@_K@Z; gsl::details::extent_type<-1>::extent_type<-1>(unsigned __int64)
0x180091749  mov     rcx, [rax]
0x18009174c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180091750  jz      short loc_18009178E
0x180091752  test    rbx, rbx
0x180091755  jnz     short loc_18009175C
0x180091757  test    rcx, rcx
0x18009175a  jnz     short loc_18009178E
0x18009175c  mov     [rsp+1E8h+var_1C8], rcx
0x180091761  mov     [rsp+1E8h+var_1C0], rbx
0x180091766  lea     rdx, [rsp+1E8h+var_1C8]
0x18009176b  lea     rcx, [rsp+1E8h+var_188]
0x180091770  call    ?Stop@CS_Cache_matchAll@CacheStorageTraceLogging@@QEAAXV?$span@$$CBU__MIDL_RPCCacheStorage_0003@@$0?0@gsl@@@Z; CacheStorageTraceLogging::CS_Cache_matchAll::Stop(gsl::span<__MIDL_RPCCacheStorage_0003 const,-1>)
0x180091775  nop
0x180091776  lea     rcx, [rsp+1E8h+var_1B0]
0x18009177b  call    ??1?$deque@VResponseMatch@@V?$allocator@VResponseMatch@@@std@@@std@@QEAA@XZ; std::deque<ResponseMatch>::~deque<ResponseMatch>(void)
0x180091780  nop
0x180091781  lea     rcx, [rsp+1E8h+var_188]; this
0x180091786  call    ??1CS_Cache_matchAll@CacheStorageTraceLogging@@QEAA@XZ; CacheStorageTraceLogging::CS_Cache_matchAll::~CS_Cache_matchAll(void)
0x18009178b  nop
0x18009178c  jmp     short loc_1800917A0
0x18009178e  call    cs:__imp__o_terminate
0x180091794  int     3; Trap to Debugger
0x180091795  call    cs:__imp__o_terminate
0x18009179b  nop
0x18009179c  mov     esi, dword ptr [rsp+1E8h+var_1C8]
0x1800917a0  mov     rcx, [rsp+1E8h+var_1B8]
0x1800917a5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800917a9  lock xadd [rcx], rax
0x1800917ae  cmp     rax, 1
0x1800917b2  jnz     short loc_1800917C7
0x1800917b4  xor     r9d, r9d; msWindowLength
0x1800917b7  xor     r8d, r8d; msPeriod
0x1800917ba  xor     edx, edx; pftDueTime
0x1800917bc  mov     rcx, [rcx+8]; pti
0x1800917c0  call    cs:__imp_SetThreadpoolTimer
0x1800917c6  nop
0x1800917c7  lea     rcx, word_1800D6108; lpWideCharStr
0x1800917ce  call    SetThreadName
0x1800917d3  nop
0x1800917d4  mov     eax, esi
0x1800917d6  mov     rcx, [rsp+1E8h+var_30]
0x1800917de  xor     rcx, rsp; StackCookie
0x1800917e1  call    __security_check_cookie
0x1800917e6  add     rsp, 1C0h
0x1800917ed  pop     r15
0x1800917ef  pop     r14
0x1800917f1  pop     rdi
0x1800917f2  pop     rsi
0x1800917f3  pop     rbx
0x1800917f4  retn
```
