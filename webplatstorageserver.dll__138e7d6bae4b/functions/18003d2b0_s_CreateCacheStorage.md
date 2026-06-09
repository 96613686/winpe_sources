# s_CreateCacheStorage

- ea: `0x18003d2b0`
- end: `0x18003d615`
- name: `s_CreateCacheStorage`
- size: `869`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: ``

## callees

- `0x180006e58`
- `0x180006e9c`
- `0x18000e1c0`
- `0x18001c800`
- `0x1800273f0`
- `0x18002d290`
- `0x18002ee6c`
- `0x180034710`
- `0x18003d2b0`
- `0x18003d61c`
- `0x18003d8a0`
- `0x18003ef90`
- `0x18003f040`
- `0x18003f3f4`
- `0x18005c28c`
- `0x18006233c`
- `0x180066010`
- `0x18006c7c0`
- `0x18007126c`
- `0x180071650`
- `0x180080fb0`
- `0x1800814bc`
- `0x180091c00`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18003d384`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18003d476`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18003d384`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18003d476`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003d5d6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003d5d6`

## string_xrefs

- `0x18003d2ff`: `CS_CreateCacheStorage`
- `0x18003d2dc`: `RPC CreateCacheStorage`
- `0x18003d359`: `onecoreuap\inetcore\webplatstorageserver\cachestorage\rpcapi.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall s_CreateCacheStorage(__int64 a1, __int64 a2, _QWORD *a3)
{
  struct HangDetectionWatchDog *v5; // rdx
  unsigned int v6; // r15d
  std::_Ref_count_base *v7; // rcx
  __int128 v8; // rdi
  __int64 v9; // rax
  _QWORD *Instance; // rax
  _QWORD *v11; // rax
  __int64 *v12; // rax
  __int64 v13; // rbx
  __int64 v14; // rcx
  std::_Ref_count_base *v15; // r14
  __int64 v16; // rcx
  __int64 v17; // rax
  _QWORD *v18; // rbx
  const char *v19; // r9
  volatile signed __int64 *v20; // rcx
  wil *v22; // rcx
  int v23; // [rsp+20h] [rbp-268h]
  __int64 (__fastcall ***v24)(_QWORD, __int128 *); // [rsp+30h] [rbp-258h] BYREF
  __int128 v25; // [rsp+38h] [rbp-250h] BYREF
  void *Block; // [rsp+48h] [rbp-240h] BYREF
  std::_Ref_count_base *v27; // [rsp+50h] [rbp-238h]
  __int128 v28; // [rsp+60h] [rbp-228h] BYREF
  volatile signed __int64 *v29; // [rsp+70h] [rbp-218h] BYREF
  std::_Ref_count_base *v30[2]; // [rsp+78h] [rbp-210h] BYREF
  _BYTE v31[8]; // [rsp+88h] [rbp-200h] BYREF
  std::_Ref_count_base *v32; // [rsp+90h] [rbp-1F8h]
  __int64 v33; // [rsp+98h] [rbp-1F0h]
  std::_Ref_count_base *v34; // [rsp+A0h] [rbp-1E8h]
  _BYTE v35[32]; // [rsp+B0h] [rbp-1D8h] BYREF
  _BYTE v36[48]; // [rsp+D0h] [rbp-1B8h] BYREF
  _QWORD v37[43]; // [rsp+100h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  SetThreadName((WCHAR *)L"RPC CreateCacheStorage");
  HangDetectionWatchDog::Activity::Activity((HangDetectionWatchDog::Activity *)&v29, v5);
  *a3 = 0;
  v6 = 0;
  wil::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v37,
    "CS_CreateCacheStorage");
  try
  {
    v37[0] = &CacheStorageTraceLogging::CS_CreateCacheStorage::`vftable';
    CacheStorageTraceLogging::CS_CreateCacheStorage::StartActivity(
      (CacheStorageTraceLogging::CS_CreateCacheStorage *)v37,
      (const struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0002 *)a2);
    ClientIdentity::ClientIdentity((ClientIdentity *)v35);
    v7 = retaddr;
    if ( v36[33] )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4D,
        (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\cachestorage\\rpcapi.cxx",
        (const char *)0x80004001LL,
        v23);
    *(_QWORD *)&v8 = *(unsigned int *)(a2 + 4);
    *((_QWORD *)&v8 + 1) = *(_QWORD *)(a2 + 8);
    v25 = v8;
    if ( !*((_QWORD *)&v8 + 1) && (_QWORD)v8 )
    {
      _o_terminate(retaddr);
      __debugbreak();
    }
    *(_OWORD *)v30 = 0;
    if ( (*(_BYTE *)a2 & 0x20) == 0 )
    {
      v28 = *(_OWORD *)gsl::span<unsigned char const,-1>::span<unsigned char const,-1>(v31, &v25);
      v9 = CreateQuotaSession(&Block, v35, 2, &v28);
      std::shared_ptr<EseHelper::IDatabaseSession>::operator=(v30, v9);
      v7 = v27;
      if ( v27 )
        std::_Ref_count_base::_Decref(v27);
    }
    Instance = (_QWORD *)WebPlatStorageClientManager::GetInstance(v7);
    (*(void (__fastcall **)(_QWORD, __int64 (__fastcall ****)(_QWORD, __int128 *), _BYTE *))(*(_QWORD *)*Instance + 8LL))(
      *Instance,
      &v24,
      v35);
    v11 = (_QWORD *)(**v24)(v24, &v25);
    v12 = (__int64 *)(*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v11 + 40LL))(*v11, 2);
    v13 = *v12;
    v14 = v12[1];
    if ( v14 )
      _InterlockedIncrement((volatile signed __int32 *)(v14 + 8));
    v33 = v13;
    v15 = (std::_Ref_count_base *)v12[1];
    v34 = v15;
    v16 = *((_QWORD *)&v25 + 1);
    if ( *((_QWORD *)&v25 + 1) )
      std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v25 + 1));
    if ( !*((_QWORD *)&v8 + 1) && (_QWORD)v8 )
    {
      _o_terminate(v16);
      __debugbreak();
    }
    v28 = v8;
    (*(void (__fastcall **)(_QWORD, bool))(**(_QWORD **)(v13 + 24) + 24LL))(
      *(_QWORD *)(v13 + 24),
      *(_BYTE *)(v13 + 160) != 0);
    v17 = std::enable_shared_from_this<QuotaSession>::shared_from_this(v13 + 8, v31);
    ActiveReferenceList<CacheStorageActiveReference>::GetActiveReference<std::wstring const &,gsl::span<unsigned char const,-1> &,std::shared_ptr<CacheStorageClient>>(
      (struct _RTL_CRITICAL_SECTION *)(v13 + 48),
      &Block,
      (__int64)v36,
      (__int64)&v28,
      v17);
    if ( v32 )
      std::_Ref_count_base::_Decref(v32);
    *(_QWORD *)&v25 = operator new(0x60u);
    v18 = CacheStorageSession::CacheStorageSession((_QWORD *)v25, (__int64 *)&v24, (__int64 *)&Block, v30);
    if ( Block )
      ActiveReference<CacheStorageActiveReference>::`vector deleting destructor'(Block);
    *a3 = v18;
    CacheStorageTraceLogging::CS_CreateCacheStorage::Stop((CacheStorageTraceLogging::CS_CreateCacheStorage *)v37, v18);
    if ( v15 )
      std::_Ref_count_base::_Decref(v15);
    if ( v24 )
      std::default_delete<IWebPlatStorageClientReference>::operator()();
    if ( v30[1] )
      std::_Ref_count_base::_Decref(v30[1]);
    std::wstring::~wstring(v36);
    std::wstring::~wstring(v35);
    v37[0] = &CacheStorageTraceLogging::CS_CreateCacheStorage::`vftable';
    wil::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v37);
    wil::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(v37);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\cachestorage\\rpcapi.cxx",
      v19);
    LODWORD(v24) = wil::ResultFromCaughtException(v22);
    v6 = (unsigned int)v24;
  }
  v20 = v29;
  if ( _InterlockedExchangeAdd64(v29, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
    SetThreadpoolTimer(*((PTP_TIMER *)v20 + 1), 0, 0, 0);
  SetThreadName((WCHAR *)&word_1800D6108);
  return v6;
}

```

## disassembly

```asm
0x18003d2b0  mov     [rsp+arg_0], rbx
0x18003d2b5  push    rsi
0x18003d2b6  push    rdi
0x18003d2b7  push    r12
0x18003d2b9  push    r14
0x18003d2bb  push    r15
0x18003d2bd  sub     rsp, 260h
0x18003d2c4  mov     rax, cs:__security_cookie
0x18003d2cb  xor     rax, rsp
0x18003d2ce  mov     [rsp+288h+var_30], rax
0x18003d2d6  mov     r12, r8
0x18003d2d9  mov     rbx, rdx
0x18003d2dc  lea     rcx, aRpcCreatecache; "RPC CreateCacheStorage"
0x18003d2e3  call    SetThreadName
0x18003d2e8  nop
0x18003d2e9  lea     rcx, [rsp+288h+var_218]; this
0x18003d2ee  call    ??0Activity@HangDetectionWatchDog@@QEAA@PEAV1@@Z; HangDetectionWatchDog::Activity::Activity(HangDetectionWatchDog *)
0x18003d2f3  nop
0x18003d2f4  mov     qword ptr [r12], 0
0x18003d2fc  xor     r15d, r15d
0x18003d2ff  lea     rdx, aCsCreatecaches; "CS_CreateCacheStorage"
0x18003d306  lea     rcx, [rsp+288h+var_188]
0x18003d30e  call    ??0?$ActivityBase@VStorageServerProvider@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18003d313  lea     rax, ??_7CS_CreateCacheStorage@CacheStorageTraceLogging@@6B@; const CacheStorageTraceLogging::CS_CreateCacheStorage::`vftable'
0x18003d31a  mov     [rsp+288h+var_188], rax
0x18003d322  mov     rdx, rbx; struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0002 *
0x18003d325  lea     rcx, [rsp+288h+var_188]; this
0x18003d32d  call    ?StartActivity@CS_CreateCacheStorage@CacheStorageTraceLogging@@QEAAXAEBU__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0002@@@Z; CacheStorageTraceLogging::CS_CreateCacheStorage::StartActivity(__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0002 const &)
0x18003d332  nop
0x18003d333  lea     rcx, [rsp+288h+var_1D8]; this
0x18003d33b  call    ??0ClientIdentity@@QEAA@XZ; ClientIdentity::ClientIdentity(void)
0x18003d340  nop
0x18003d341  mov     rcx, [rsp+288h]; this
0x18003d349  cmp     [rsp+288h+var_197], r15b
0x18003d351  jz      short loc_18003D369
0x18003d353  mov     r9d, 80004001h; char *
0x18003d359  lea     r8, aOnecoreuapInet_4; "onecoreuap\\inetcore\\webplatstorageser"...
0x18003d360  lea     edx, [r15+4Dh]; void *
0x18003d364  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003d369  mov     edi, [rbx+4]
0x18003d36c  mov     rsi, [rbx+8]
0x18003d370  mov     [rsp+288h+var_250], rdi
0x18003d375  mov     [rsp+288h+var_248], rsi
0x18003d37a  test    rsi, rsi
0x18003d37d  jnz     short loc_18003D38B
0x18003d37f  test    rdi, rdi
0x18003d382  jz      short loc_18003D38B
0x18003d384  call    cs:__imp__o_terminate
0x18003d38a  int     3; Trap to Debugger
0x18003d38b  xorps   xmm0, xmm0
0x18003d38e  movdqu  xmmword ptr [rsp+288h+var_210], xmm0
0x18003d394  test    byte ptr [rbx], 20h
0x18003d397  jnz     short loc_18003D3ED
0x18003d399  lea     rdx, [rsp+288h+var_250]
0x18003d39e  lea     rcx, [rsp+288h+var_200]
0x18003d3a6  call    ??$?0E$0?0$0?0$0A@@?$span@$$CBE$0?0@gsl@@QEAA@AEBV?$span@E$0?0@1@@Z; gsl::span<uchar const,-1>::span<uchar const,-1>(gsl::span<uchar,-1> const &)
0x18003d3ab  movups  xmm0, xmmword ptr [rax]
0x18003d3ae  movdqu  [rsp+288h+var_228], xmm0
0x18003d3b4  lea     r9, [rsp+288h+var_228]
0x18003d3b9  mov     r8d, 2
0x18003d3bf  lea     rdx, [rsp+288h+var_1D8]
0x18003d3c7  lea     rcx, [rsp+288h+Block]
0x18003d3cc  call    ?CreateQuotaSession@@YA?AV?$shared_ptr@UIQuotaSession@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@W4WebPlatStorageHandlerType@@V?$span@$$CBE$0?0@gsl@@@Z; CreateQuotaSession(std::wstring const &,WebPlatStorageHandlerType,gsl::span<uchar const,-1>)
0x18003d3d1  mov     rdx, rax
0x18003d3d4  lea     rcx, [rsp+288h+var_210]
0x18003d3d9  call    ??4?$shared_ptr@UIDatabaseSession@EseHelper@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<EseHelper::IDatabaseSession>::operator=(std::shared_ptr<EseHelper::IDatabaseSession> &&)
0x18003d3de  mov     rcx, [rsp+288h+var_238]; this
0x18003d3e3  test    rcx, rcx
0x18003d3e6  jz      short loc_18003D3ED
0x18003d3e8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003d3ed  call    ?GetInstance@WebPlatStorageClientManager@@SAAEAV?$unique_ptr@VWebPlatStorageClientManager@@U?$default_delete@VWebPlatStorageClientManager@@@std@@@std@@XZ; WebPlatStorageClientManager::GetInstance(void)
0x18003d3f2  mov     rcx, [rax]
0x18003d3f5  mov     rax, [rcx]
0x18003d3f8  lea     r8, [rsp+288h+var_1D8]
0x18003d400  lea     rdx, [rsp+288h+var_258]
0x18003d405  mov     rax, [rax+8]
0x18003d409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d40e  nop
0x18003d40f  mov     rcx, [rsp+288h+var_258]
0x18003d414  mov     rax, [rcx]
0x18003d417  lea     rdx, [rsp+288h+var_250]
0x18003d41c  mov     rax, [rax]
0x18003d41f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d424  nop
0x18003d425  mov     rcx, [rax]
0x18003d428  mov     rax, [rcx]
0x18003d42b  mov     edx, 2
0x18003d430  mov     rax, [rax+28h]
0x18003d434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d439  mov     rbx, [rax]
0x18003d43c  mov     rcx, [rax+8]
0x18003d440  test    rcx, rcx
0x18003d443  jz      short loc_18003D449
0x18003d445  lock inc dword ptr [rcx+8]
0x18003d449  mov     [rsp+288h+var_1F0], rbx
0x18003d451  mov     r14, [rax+8]
0x18003d455  mov     [rsp+288h+var_1E8], r14
0x18003d45d  mov     rcx, [rsp+288h+var_248]; this
0x18003d462  test    rcx, rcx
0x18003d465  jz      short loc_18003D46C
0x18003d467  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003d46c  test    rsi, rsi
0x18003d46f  jnz     short loc_18003D47D
0x18003d471  test    rdi, rdi
0x18003d474  jz      short loc_18003D47D
0x18003d476  call    cs:__imp__o_terminate
0x18003d47c  int     3; Trap to Debugger
0x18003d47d  mov     qword ptr [rsp+288h+var_228], rdi
0x18003d482  mov     qword ptr [rsp+288h+var_228+8], rsi
0x18003d487  mov     rcx, [rbx+18h]
0x18003d48b  mov     rax, [rcx]
0x18003d48e  xor     edx, edx
0x18003d490  cmp     [rbx+0A0h], dl
0x18003d496  setnz   dl
0x18003d499  mov     rax, [rax+18h]
0x18003d49d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d4a2  lea     rcx, [rbx+8]
0x18003d4a6  lea     rdx, [rsp+288h+var_200]
0x18003d4ae  call    ?shared_from_this@?$enable_shared_from_this@VQuotaSession@@@std@@QEAA?AV?$shared_ptr@VQuotaSession@@@2@XZ; std::enable_shared_from_this<QuotaSession>::shared_from_this(void)
0x18003d4b3  nop
0x18003d4b4  mov     qword ptr [rsp+288h+var_268], rax
0x18003d4b9  lea     r9, [rsp+288h+var_228]
0x18003d4be  lea     r8, [rsp+288h+var_1B8]
0x18003d4c6  lea     rdx, [rsp+288h+Block]
0x18003d4cb  lea     rcx, [rbx+30h]
0x18003d4cf  call    ??$GetActiveReference@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$span@$$CBE$0?0@gsl@@V?$shared_ptr@VCacheStorageClient@@@2@@?$ActiveReferenceList@VCacheStorageActiveReference@@@@QEAA?AV?$unique_ptr@V?$ActiveReference@VCacheStorageActiveReference@@@@U?$default_delete@V?$ActiveReference@VCacheStorageActiveReference@@@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@AEAV?$span@$$CBE$0?0@gsl@@$$QEAV?$shared_ptr@VCacheStorageClient@@@2@@Z; ActiveReferenceList<CacheStorageActiveReference>::GetActiveReference<std::wstring const &,gsl::span<uchar const,-1> &,std::shared_ptr<CacheStorageClient>>(std::wstring const &,gsl::span<uchar const,-1> &,std::shared_ptr<CacheStorageClient> &&)
0x18003d4d4  nop
0x18003d4d5  mov     rcx, [rsp+288h+var_1F8]; this
0x18003d4dd  test    rcx, rcx
0x18003d4e0  jz      short loc_18003D4E7
0x18003d4e2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003d4e7  mov     ecx, 60h ; '`'; Size
0x18003d4ec  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003d4f1  mov     [rsp+288h+var_250], rax
0x18003d4f6  lea     r9, [rsp+288h+var_210]
0x18003d4fb  lea     r8, [rsp+288h+Block]
0x18003d500  lea     rdx, [rsp+288h+var_258]
0x18003d505  mov     rcx, rax
0x18003d508  call    ??0CacheStorageSession@@QEAA@$$QEAV?$unique_ptr@UIWebPlatStorageClientReference@@U?$default_delete@UIWebPlatStorageClientReference@@@std@@@std@@$$QEAV?$unique_ptr@V?$ActiveReference@VCacheStorageActiveReference@@@@U?$default_delete@V?$ActiveReference@VCacheStorageActiveReference@@@@@std@@@2@$$QEAV?$shared_ptr@UIQuotaSession@@@2@@Z; CacheStorageSession::CacheStorageSession(std::unique_ptr<IWebPlatStorageClientReference> &&,std::unique_ptr<ActiveReference<CacheStorageActiveReference>> &&,std::shared_ptr<IQuotaSession> &&)
0x18003d50d  mov     rbx, rax
0x18003d510  mov     rcx, [rsp+288h+Block]; Block
0x18003d515  test    rcx, rcx
0x18003d518  jz      short loc_18003D524
0x18003d51a  mov     edx, 1
0x18003d51f  call    ??_E?$ActiveReference@VCacheStorageActiveReference@@@@UEAAPEAXI@Z; ActiveReference<CacheStorageActiveReference>::`vector deleting destructor'(uint)
0x18003d524  mov     [r12], rbx
0x18003d528  mov     rdx, rbx; void *
0x18003d52b  lea     rcx, [rsp+288h+var_188]; this
0x18003d533  call    ?Stop@CS_CreateCacheStorage@CacheStorageTraceLogging@@QEAAXPEAX@Z; CacheStorageTraceLogging::CS_CreateCacheStorage::Stop(void *)
0x18003d538  nop
0x18003d539  test    r14, r14
0x18003d53c  jz      short loc_18003D547
0x18003d53e  mov     rcx, r14; this
0x18003d541  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003d546  nop
0x18003d547  mov     rdx, [rsp+288h+var_258]
0x18003d54c  test    rdx, rdx
0x18003d54f  jz      short loc_18003D557
0x18003d551  call    ??R?$default_delete@UIWebPlatStorageClientReference@@@std@@QEBAXPEAUIWebPlatStorageClientReference@@@Z; std::default_delete<IWebPlatStorageClientReference>::operator()(IWebPlatStorageClientReference *)
0x18003d556  nop
0x18003d557  mov     rcx, [rsp+288h+var_210+8]; this
0x18003d55f  test    rcx, rcx
0x18003d562  jz      short loc_18003D56A
0x18003d564  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003d569  nop
0x18003d56a  lea     rcx, [rsp+288h+var_1B8]; void *
0x18003d572  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003d577  lea     rcx, [rsp+288h+var_1D8]; void *
0x18003d57f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003d584  nop
0x18003d585  lea     rax, ??_7CS_CreateCacheStorage@CacheStorageTraceLogging@@6B@; const CacheStorageTraceLogging::CS_CreateCacheStorage::`vftable'
0x18003d58c  mov     [rsp+288h+var_188], rax
0x18003d594  lea     rcx, [rsp+288h+var_188]
0x18003d59c  call    ?Destroy@?$ActivityBase@VStorageServerProvider@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18003d5a1  lea     rcx, [rsp+288h+var_188]
0x18003d5a9  call    ??1?$ActivityBase@VStorageServerProvider@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18003d5ae  nop
0x18003d5af  jmp     short loc_18003D5B6
0x18003d5b1  mov     r15d, dword ptr [rsp+288h+var_258]
0x18003d5b6  mov     rcx, [rsp+288h+var_218]
0x18003d5bb  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003d5bf  lock xadd [rcx], rax
0x18003d5c4  cmp     rax, 1
0x18003d5c8  jnz     short loc_18003D5DD
0x18003d5ca  xor     r9d, r9d; msWindowLength
0x18003d5cd  xor     r8d, r8d; msPeriod
0x18003d5d0  xor     edx, edx; pftDueTime
0x18003d5d2  mov     rcx, [rcx+8]; pti
0x18003d5d6  call    cs:__imp_SetThreadpoolTimer
0x18003d5dc  nop
0x18003d5dd  lea     rcx, word_1800D6108; lpWideCharStr
0x18003d5e4  call    SetThreadName
0x18003d5e9  nop
0x18003d5ea  mov     eax, r15d
0x18003d5ed  mov     rcx, [rsp+288h+var_30]
0x18003d5f5  xor     rcx, rsp; StackCookie
0x18003d5f8  call    __security_check_cookie
0x18003d5fd  mov     rbx, [rsp+288h+arg_0]
0x18003d605  add     rsp, 260h
0x18003d60c  pop     r15
0x18003d60e  pop     r14
0x18003d610  pop     r12
0x18003d612  pop     rdi
0x18003d613  pop     rsi
0x18003d614  retn
```
