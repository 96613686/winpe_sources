# s_Cache_keys

- ea: `0x1800914c0`
- end: `0x180091652`
- name: `s_Cache_keys`
- size: `402`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x18001f470`
- `0x1800245f0`
- `0x1800273f0`
- `0x18002d290`
- `0x18003f3f4`
- `0x18007ade0`
- `0x180080fb0`
- `0x18008db1c`
- `0x18008dba4`
- `0x18008e364`
- `0x18008ea54`
- `0x1800914c0`
- `0x180093254`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800915eb`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800915f2`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800915eb`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800915f2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18009161d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18009161d`

## string_xrefs

- `0x1800914f2`: `RPC Cache_keys`
- `0x180091519`: `CS_Cache_keys`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall s_Cache_keys(
        __int64 a1,
        void *a2,
        const struct __MIDL_RPCCacheStorage_0002 *a3,
        _DWORD *a4,
        __int64 *a5)
{
  struct HangDetectionWatchDog *v8; // rdx
  unsigned int v9; // esi
  __int64 v10; // rbx
  __int64 v11; // rcx
  __int64 *v12; // rax
  __int64 v13; // rcx
  volatile signed __int64 *v14; // rcx
  _QWORD v16[2]; // [rsp+20h] [rbp-1C8h] BYREF
  volatile signed __int64 *v17; // [rsp+30h] [rbp-1B8h] BYREF
  _BYTE v18[32]; // [rsp+38h] [rbp-1B0h] BYREF
  unsigned __int64 v19; // [rsp+58h] [rbp-190h]
  _QWORD v20[43]; // [rsp+60h] [rbp-188h] BYREF

  SetThreadName((WCHAR *)L"RPC Cache_keys");
  HangDetectionWatchDog::Activity::Activity((HangDetectionWatchDog::Activity *)&v17, v8);
  *a4 = 0;
  *a5 = 0;
  v9 = 0;
  wil::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v20,
    "CS_Cache_keys");
  v20[0] = &CacheStorageTraceLogging::CS_Cache_keys::`vftable';
  CacheStorageTraceLogging::CS_Cache_keys::StartActivity((CacheStorageTraceLogging::CS_Cache_keys *)v20, a2, a3);
  CacheSession::Keys(a2, v18, a3);
  if ( v19 )
  {
    *a5 = RequestMatch::s_AllocateRequestInfosForRpc(v18);
    *a4 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v19);
  }
  v10 = *a5;
  gsl::details::extent_type<-1>::extent_type<-1>(v16, (unsigned int)*a4);
  if ( v16[0] == -1 || !v10 && v16[0] )
  {
    _o_terminate(v11);
    v9 = v16[0];
  }
  else
  {
    v12 = (__int64 *)gsl::details::extent_type<-1>::extent_type<-1>(v16, v16[0]);
    v13 = *v12;
    if ( *v12 == -1 || !v10 && v13 )
    {
      _o_terminate(v13);
      __debugbreak();
    }
    v16[0] = *v12;
    v16[1] = v10;
    CacheStorageTraceLogging::CS_Cache_keys::Stop(v20, v16);
    std::deque<RequestMatch>::~deque<RequestMatch>(v18);
    CacheStorageTraceLogging::CS_Cache_keys::~CS_Cache_keys((CacheStorageTraceLogging::CS_Cache_keys *)v20);
  }
  v14 = v17;
  if ( _InterlockedExchangeAdd64(v17, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
    SetThreadpoolTimer(*((PTP_TIMER *)v14 + 1), 0, 0, 0);
  SetThreadName((WCHAR *)&word_1800D6108);
  return v9;
}

```

## disassembly

```asm
0x1800914c0  push    rbx
0x1800914c2  push    rsi
0x1800914c3  push    rdi
0x1800914c4  push    r14
0x1800914c6  push    r15
0x1800914c8  sub     rsp, 1C0h
0x1800914cf  mov     rax, cs:__security_cookie
0x1800914d6  xor     rax, rsp
0x1800914d9  mov     [rsp+1E8h+var_30], rax
0x1800914e1  mov     rdi, r9
0x1800914e4  mov     r15, r8
0x1800914e7  mov     r14, rdx
0x1800914ea  mov     rbx, [rsp+1E8h+arg_20]
0x1800914f2  lea     rcx, aRpcCacheKeys; "RPC Cache_keys"
0x1800914f9  call    SetThreadName
0x1800914fe  nop
0x1800914ff  lea     rcx, [rsp+1E8h+var_1B8]; this
0x180091504  call    ??0Activity@HangDetectionWatchDog@@QEAA@PEAV1@@Z; HangDetectionWatchDog::Activity::Activity(HangDetectionWatchDog *)
0x180091509  nop
0x18009150a  mov     dword ptr [rdi], 0
0x180091510  mov     qword ptr [rbx], 0
0x180091517  xor     esi, esi
0x180091519  lea     rdx, aCsCacheKeys; "CS_Cache_keys"
0x180091520  lea     rcx, [rsp+1E8h+var_188]
0x180091525  call    ??0?$ActivityBase@VStorageServerProvider@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18009152a  lea     rax, ??_7CS_Cache_keys@CacheStorageTraceLogging@@6B@; const CacheStorageTraceLogging::CS_Cache_keys::`vftable'
0x180091531  mov     [rsp+1E8h+var_188], rax
0x180091536  mov     r8, r15; struct __MIDL_RPCCacheStorage_0002 *
0x180091539  mov     rdx, r14; void *
0x18009153c  lea     rcx, [rsp+1E8h+var_188]; this
0x180091541  call    ?StartActivity@CS_Cache_keys@CacheStorageTraceLogging@@QEAAXPEAXPEBU__MIDL_RPCCacheStorage_0002@@@Z; CacheStorageTraceLogging::CS_Cache_keys::StartActivity(void *,__MIDL_RPCCacheStorage_0002 const *)
0x180091546  nop
0x180091547  mov     r8, r15
0x18009154a  lea     rdx, [rsp+1E8h+var_1B0]
0x18009154f  mov     rcx, r14
0x180091552  call    ?Keys@CacheSession@@QEAA?AV?$deque@VRequestMatch@@V?$allocator@VRequestMatch@@@std@@@std@@PEBU__MIDL_RPCCacheStorage_0002@@@Z; CacheSession::Keys(__MIDL_RPCCacheStorage_0002 const *)
0x180091557  nop
0x180091558  cmp     [rsp+1E8h+var_190], rsi
0x18009155d  jbe     short loc_180091578
0x18009155f  lea     rcx, [rsp+1E8h+var_1B0]
0x180091564  call    ?s_AllocateRequestInfosForRpc@RequestMatch@@SAPEAU__MIDL_RPCCacheStorage_0001@@AEBV?$deque@VRequestMatch@@V?$allocator@VRequestMatch@@@std@@@std@@@Z; RequestMatch::s_AllocateRequestInfosForRpc(std::deque<RequestMatch> const &)
0x180091569  mov     [rbx], rax
0x18009156c  mov     rcx, [rsp+1E8h+var_190]
0x180091571  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180091576  mov     [rdi], eax
0x180091578  mov     rbx, [rbx]
0x18009157b  mov     edx, [rdi]
0x18009157d  lea     rcx, [rsp+1E8h+var_1C8]
0x180091582  call    ??0?$extent_type@$0?0@details@gsl@@QEAA@_K@Z; gsl::details::extent_type<-1>::extent_type<-1>(unsigned __int64)
0x180091587  mov     rdx, [rsp+1E8h+var_1C8]
0x18009158c  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180091590  jz      short loc_1800915F2
0x180091592  test    rbx, rbx
0x180091595  jnz     short loc_18009159C
0x180091597  test    rdx, rdx
0x18009159a  jnz     short loc_1800915F2
0x18009159c  lea     rcx, [rsp+1E8h+var_1C8]
0x1800915a1  call    ??0?$extent_type@$0?0@details@gsl@@QEAA@_K@Z; gsl::details::extent_type<-1>::extent_type<-1>(unsigned __int64)
0x1800915a6  mov     rcx, [rax]
0x1800915a9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800915ad  jz      short loc_1800915EB
0x1800915af  test    rbx, rbx
0x1800915b2  jnz     short loc_1800915B9
0x1800915b4  test    rcx, rcx
0x1800915b7  jnz     short loc_1800915EB
0x1800915b9  mov     [rsp+1E8h+var_1C8], rcx
0x1800915be  mov     [rsp+1E8h+var_1C0], rbx
0x1800915c3  lea     rdx, [rsp+1E8h+var_1C8]
0x1800915c8  lea     rcx, [rsp+1E8h+var_188]
0x1800915cd  call    ?Stop@CS_Cache_keys@CacheStorageTraceLogging@@QEAAXV?$span@$$CBU__MIDL_RPCCacheStorage_0001@@$0?0@gsl@@@Z; CacheStorageTraceLogging::CS_Cache_keys::Stop(gsl::span<__MIDL_RPCCacheStorage_0001 const,-1>)
0x1800915d2  nop
0x1800915d3  lea     rcx, [rsp+1E8h+var_1B0]
0x1800915d8  call    ??1?$deque@VRequestMatch@@V?$allocator@VRequestMatch@@@std@@@std@@QEAA@XZ; std::deque<RequestMatch>::~deque<RequestMatch>(void)
0x1800915dd  nop
0x1800915de  lea     rcx, [rsp+1E8h+var_188]; this
0x1800915e3  call    ??1CS_Cache_keys@CacheStorageTraceLogging@@QEAA@XZ; CacheStorageTraceLogging::CS_Cache_keys::~CS_Cache_keys(void)
0x1800915e8  nop
0x1800915e9  jmp     short loc_1800915FD
0x1800915eb  call    cs:__imp__o_terminate
0x1800915f1  int     3; Trap to Debugger
0x1800915f2  call    cs:__imp__o_terminate
0x1800915f8  nop
0x1800915f9  mov     esi, dword ptr [rsp+1E8h+var_1C8]
0x1800915fd  mov     rcx, [rsp+1E8h+var_1B8]
0x180091602  or      rax, 0FFFFFFFFFFFFFFFFh
0x180091606  lock xadd [rcx], rax
0x18009160b  cmp     rax, 1
0x18009160f  jnz     short loc_180091624
0x180091611  xor     r9d, r9d; msWindowLength
0x180091614  xor     r8d, r8d; msPeriod
0x180091617  xor     edx, edx; pftDueTime
0x180091619  mov     rcx, [rcx+8]; pti
0x18009161d  call    cs:__imp_SetThreadpoolTimer
0x180091623  nop
0x180091624  lea     rcx, word_1800D6108; lpWideCharStr
0x18009162b  call    SetThreadName
0x180091630  nop
0x180091631  mov     eax, esi
0x180091633  mov     rcx, [rsp+1E8h+var_30]
0x18009163b  xor     rcx, rsp; StackCookie
0x18009163e  call    __security_check_cookie
0x180091643  add     rsp, 1C0h
0x18009164a  pop     r15
0x18009164c  pop     r14
0x18009164e  pop     rdi
0x18009164f  pop     rsi
0x180091650  pop     rbx
0x180091651  retn
```
