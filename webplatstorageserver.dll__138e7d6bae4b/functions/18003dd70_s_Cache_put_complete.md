# s_Cache_put_complete

- ea: `0x18003dd70`
- end: `0x18003dfb4`
- name: `s_Cache_put_complete`
- size: `580`
- prototype: `__int64 __fastcall(__int64, CachePutSession **, char, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180018700`
- `0x1800273f0`
- `0x18002d290`
- `0x18003d0e4`
- `0x18003dd70`
- `0x18003dfbc`
- `0x18003ef90`
- `0x18003f040`
- `0x18003f6c0`
- `0x180080fb0`
- `0x1800810a4`
- `0x180081b40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18003dddb`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18003dddb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003df70`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003df70`

## string_xrefs

- `0x18003ddaf`: `RPC Cache_put_complete`
- `0x18003ddf8`: `CS_Cache_put_complete`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall s_Cache_put_complete(__int64 a1, CachePutSession **a2, char a3, unsigned int a4, __int64 a5)
{
  __int64 v5; // r15
  CachePutSession **v7; // rsi
  struct HangDetectionWatchDog *v8; // rdx
  __int64 v9; // r8
  unsigned int v10; // r14d
  CachePutSession *v11; // rdi
  const char *v12; // r9
  volatile signed __int64 *v13; // rcx
  wil *v15; // rcx
  volatile signed __int64 *v17; // [rsp+28h] [rbp-1C0h] BYREF
  _QWORD v18[2]; // [rsp+30h] [rbp-1B8h] BYREF
  CachePutSession **v19; // [rsp+40h] [rbp-1A8h]
  _QWORD v20[2]; // [rsp+50h] [rbp-198h] BYREF
  void **v21; // [rsp+60h] [rbp-188h] BYREF
  int v22; // [rsp+68h] [rbp-180h] BYREF
  char v23; // [rsp+6Ch] [rbp-17Ch]
  int v24; // [rsp+90h] [rbp-158h] BYREF
  const char *v25; // [rsp+98h] [rbp-150h]
  __int64 v26; // [rsp+A0h] [rbp-148h]
  char v27; // [rsp+A8h] [rbp-140h]
  int v28; // [rsp+B0h] [rbp-138h]
  char v29[152]; // [rsp+B8h] [rbp-130h] BYREF
  __int128 v30; // [rsp+150h] [rbp-98h]
  int v31; // [rsp+160h] [rbp-88h]
  __int64 v32; // [rsp+168h] [rbp-80h]
  int *v33; // [rsp+170h] [rbp-78h]
  __int64 v34; // [rsp+178h] [rbp-70h]
  __int64 v35; // [rsp+180h] [rbp-68h]
  void ***v36; // [rsp+188h] [rbp-60h]
  __int64 v37; // [rsp+190h] [rbp-58h]
  int v38; // [rsp+198h] [rbp-50h]
  int *v39; // [rsp+1A0h] [rbp-48h]
  char v40; // [rsp+1A8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]

  v5 = a4;
  v7 = a2;
  v19 = a2;
  SetThreadName(L"RPC Cache_put_complete");
  HangDetectionWatchDog::Activity::Activity((HangDetectionWatchDog::Activity *)&v17, v8);
  if ( !a5 && v5 )
    _o_terminate();
  v22 = 0;
  v23 = 0;
  v27 = 0;
  v24 = 0;
  v25 = "CS_Cache_put_complete";
  v26 = 0;
  v28 = 0;
  v30 = 0;
  memset_0(v29, 0, sizeof(v29));
  v31 = 1;
  v32 = 0;
  v33 = &v22;
  v34 = 0;
  v35 = 0;
  v36 = &v21;
  v37 = 0;
  v38 = 0;
  v39 = &v24;
  v40 = 0;
  v21 = &CacheStorageTraceLogging::CS_Cache_put_complete::`vftable';
  v18[0] = v5;
  v18[1] = a5;
  LOBYTE(v9) = a3;
  CacheStorageTraceLogging::CS_Cache_put_complete::StartActivity(&v21, *v7, v9, v18);
  v10 = 0;
  v11 = *v7;
  v18[0] = *v7;
  if ( a3 )
  {
    try
    {
      v20[0] = v5;
      v20[1] = a5;
      CachePutSession::Commit(v11, v20);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x165,
        (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\cachestorage\\rpcapi.cxx",
        v12);
      v10 = wil::ResultFromCaughtException(v15);
      v11 = (CachePutSession *)v18[0];
      v7 = v19;
    }
  }
  *v7 = 0;
  if ( v11 )
  {
    CachePutSession::~CachePutSession(v11);
    operator delete(v11);
  }
  wil::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v21, v10);
  v21 = &CacheStorageTraceLogging::CS_Cache_put_complete::`vftable';
  wil::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v21);
  wil::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(&v21);
  v13 = v17;
  if ( _InterlockedExchangeAdd64(v17, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
    SetThreadpoolTimer(*((PTP_TIMER *)v13 + 1), 0, 0, 0);
  SetThreadName(&word_1800D6108);
  return v10;
}

```

## disassembly

```asm
0x18003dd70  mov     [rsp+arg_0], rbx
0x18003dd75  mov     [rsp+arg_18], rsi
0x18003dd7a  push    rdi
0x18003dd7b  push    r12
0x18003dd7d  push    r13
0x18003dd7f  push    r14
0x18003dd81  push    r15
0x18003dd83  sub     rsp, 1C0h
0x18003dd8a  mov     rax, cs:__security_cookie
0x18003dd91  xor     rax, rsp
0x18003dd94  mov     [rsp+1E8h+var_30], rax
0x18003dd9c  mov     r15d, r9d
0x18003dd9f  mov     dil, r8b
0x18003dda2  mov     [rsp+1E8h+var_1C8], r8b
0x18003dda7  mov     rsi, rdx
0x18003ddaa  mov     [rsp+1E8h+var_1A8], rdx
0x18003ddaf  lea     rcx, aRpcCachePutCom; "RPC Cache_put_complete"
0x18003ddb6  call    SetThreadName
0x18003ddbb  nop
0x18003ddbc  lea     rcx, [rsp+1E8h+var_1C0]; this
0x18003ddc1  call    ??0Activity@HangDetectionWatchDog@@QEAA@PEAV1@@Z; HangDetectionWatchDog::Activity::Activity(HangDetectionWatchDog *)
0x18003ddc6  nop
0x18003ddc7  mov     r12, [rsp+1E8h+arg_20]
0x18003ddcf  xor     ebx, ebx
0x18003ddd1  test    r12, r12
0x18003ddd4  jnz     short loc_18003DDE2
0x18003ddd6  test    r15, r15
0x18003ddd9  jz      short loc_18003DDE2
0x18003dddb  call    cs:__imp__o_terminate
0x18003dde1  nop
0x18003dde2  mov     [rsp+1E8h+var_180], ebx
0x18003dde6  mov     [rsp+1E8h+var_17C], bl
0x18003ddea  mov     [rsp+1E8h+var_140], bl
0x18003ddf1  mov     [rsp+1E8h+var_158], ebx
0x18003ddf8  lea     rax, aCsCachePutComp; "CS_Cache_put_complete"
0x18003ddff  mov     [rsp+1E8h+var_150], rax
0x18003de07  mov     [rsp+1E8h+var_148], rbx
0x18003de0f  mov     [rsp+1E8h+var_138], ebx
0x18003de16  xorps   xmm0, xmm0
0x18003de19  movdqa  [rsp+1E8h+var_98], xmm0
0x18003de22  xor     edx, edx; Val
0x18003de24  mov     r8d, 98h; Size
0x18003de2a  lea     rcx, [rsp+1E8h+var_130]; void *
0x18003de32  call    memset_0
0x18003de37  mov     [rsp+1E8h+var_88], 1
0x18003de42  xor     eax, eax
0x18003de44  mov     [rsp+1E8h+var_80], rax
0x18003de4c  lea     rax, [rsp+1E8h+var_180]
0x18003de51  mov     [rsp+1E8h+var_78], rax
0x18003de59  mov     [rsp+1E8h+var_70], rbx
0x18003de61  mov     [rsp+1E8h+var_68], rbx
0x18003de69  lea     rax, [rsp+1E8h+var_188]
0x18003de6e  mov     [rsp+1E8h+var_60], rax
0x18003de76  mov     [rsp+1E8h+var_58], rbx
0x18003de7e  mov     [rsp+1E8h+var_50], ebx
0x18003de85  lea     rax, [rsp+1E8h+var_158]
0x18003de8d  mov     [rsp+1E8h+var_48], rax
0x18003de95  mov     [rsp+1E8h+var_40], bl
0x18003de9c  lea     r13, ??_7CS_Cache_put_complete@CacheStorageTraceLogging@@6B@; const CacheStorageTraceLogging::CS_Cache_put_complete::`vftable'
0x18003dea3  mov     [rsp+1E8h+var_188], r13
0x18003dea8  mov     [rsp+1E8h+var_1B8], r15
0x18003dead  mov     [rsp+1E8h+var_1B0], r12
0x18003deb2  lea     r9, [rsp+1E8h+var_1B8]
0x18003deb7  mov     r8b, dil
0x18003deba  mov     rdx, [rsi]
0x18003debd  lea     rcx, [rsp+1E8h+var_188]
0x18003dec2  call    ?StartActivity@CS_Cache_put_complete@CacheStorageTraceLogging@@QEAAXPEAXEV?$span@$$CBU__MIDL_RPCCacheStorage_0003@@$0?0@gsl@@@Z; CacheStorageTraceLogging::CS_Cache_put_complete::StartActivity(void *,uchar,gsl::span<__MIDL_RPCCacheStorage_0003 const,-1>)
0x18003dec7  nop
0x18003dec8  mov     r14d, ebx
0x18003decb  mov     rdi, [rsi]
0x18003dece  mov     [rsp+1E8h+var_1B8], rdi
0x18003ded3  cmp     [rsp+1E8h+var_1C8], bl
0x18003ded7  jz      short loc_18003DF0B
0x18003ded9  mov     [rsp+1E8h+var_198], r15
0x18003dede  mov     [rsp+1E8h+var_190], r12
0x18003dee3  lea     rdx, [rsp+1E8h+var_198]
0x18003dee8  mov     rcx, rdi
0x18003deeb  call    ?Commit@CachePutSession@@QEAAXV?$span@$$CBU__MIDL_RPCCacheStorage_0003@@$0?0@gsl@@@Z; CachePutSession::Commit(gsl::span<__MIDL_RPCCacheStorage_0003 const,-1>)
0x18003def0  nop
0x18003def1  jmp     short loc_18003DF0B
0x18003def3  xor     ebx, ebx
0x18003def5  lea     r13, ??_7CS_Cache_put_complete@CacheStorageTraceLogging@@6B@; const CacheStorageTraceLogging::CS_Cache_put_complete::`vftable'
0x18003defc  mov     r14d, [rsp+1E8h+var_1C4]
0x18003df01  mov     rdi, [rsp+1E8h+var_1B8]
0x18003df06  mov     rsi, [rsp+1E8h+var_1A8]
0x18003df0b  mov     [rsi], rbx
0x18003df0e  test    rdi, rdi
0x18003df11  jz      short loc_18003DF28
0x18003df13  mov     rcx, rdi; this
0x18003df16  call    ??1CachePutSession@@QEAA@XZ; CachePutSession::~CachePutSession(void)
0x18003df1b  mov     edx, 88h
0x18003df20  mov     rcx, rdi; Block
0x18003df23  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003df28  mov     edx, r14d
0x18003df2b  lea     rcx, [rsp+1E8h+var_188]
0x18003df30  call    ?Stop@?$ActivityBase@VStorageServerProvider@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18003df35  nop
0x18003df36  mov     [rsp+1E8h+var_188], r13
0x18003df3b  lea     rcx, [rsp+1E8h+var_188]
0x18003df40  call    ?Destroy@?$ActivityBase@VStorageServerProvider@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18003df45  lea     rcx, [rsp+1E8h+var_188]
0x18003df4a  call    ??1?$ActivityBase@VStorageServerProvider@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18003df4f  nop
0x18003df50  mov     rcx, [rsp+1E8h+var_1C0]
0x18003df55  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003df59  lock xadd [rcx], rax
0x18003df5e  cmp     rax, 1
0x18003df62  jnz     short loc_18003DF77
0x18003df64  xor     r9d, r9d; msWindowLength
0x18003df67  xor     r8d, r8d; msPeriod
0x18003df6a  xor     edx, edx; pftDueTime
0x18003df6c  mov     rcx, [rcx+8]; pti
0x18003df70  call    cs:__imp_SetThreadpoolTimer
0x18003df76  nop
0x18003df77  lea     rcx, word_1800D6108; lpWideCharStr
0x18003df7e  call    SetThreadName
0x18003df83  nop
0x18003df84  mov     eax, r14d
0x18003df87  mov     rcx, [rsp+1E8h+var_30]
0x18003df8f  xor     rcx, rsp; StackCookie
0x18003df92  call    __security_check_cookie
0x18003df97  lea     r11, [rsp+1E8h+var_28]
0x18003df9f  mov     rbx, [r11+30h]
0x18003dfa3  mov     rsi, [r11+48h]
0x18003dfa7  mov     rsp, r11
0x18003dfaa  pop     r15
0x18003dfac  pop     r14
0x18003dfae  pop     r13
0x18003dfb0  pop     r12
0x18003dfb2  pop     rdi
0x18003dfb3  retn
```
