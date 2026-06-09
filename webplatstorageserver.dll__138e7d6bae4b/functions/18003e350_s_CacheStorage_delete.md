# s_CacheStorage_delete

- ea: `0x18003e350`
- end: `0x18003e5dd`
- name: `s_CacheStorage_delete`
- size: `653`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000e1c0`
- `0x1800273f0`
- `0x180028c50`
- `0x18002d290`
- `0x180034710`
- `0x18003e350`
- `0x18003e65c`
- `0x18003e770`
- `0x18003ed00`
- `0x18003ef90`
- `0x18003f040`
- `0x18003f18c`
- `0x18003f27c`
- `0x18003f3f4`
- `0x18003f4b4`
- `0x180063d58`
- `0x180080fb0`
- `0x1800810a4`
- `0x1800814bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18003e5c1`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18003e5c1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003e574`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003e574`

## string_xrefs

- `0x18003e38d`: `RPC CacheStorage_delete`
- `0x18003e3b6`: `CS_CacheStorage_delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall s_CacheStorage_delete(__int64 a1, __int64 *a2, unsigned int a3, std::_Ref_count_base *a4, _BYTE *a5)
{
  __int64 v6; // rbx
  struct HangDetectionWatchDog *v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r14
  __int64 *v11; // r12
  __int64 v12; // rax
  _QWORD *v13; // rbx
  char v14; // al
  volatile signed __int64 *v15; // rcx
  char *v17; // [rsp+30h] [rbp-1D8h] BYREF
  __int64 v18; // [rsp+40h] [rbp-1C8h] BYREF
  std::_Ref_count_base *v19; // [rsp+48h] [rbp-1C0h]
  _QWORD *v20; // [rsp+50h] [rbp-1B8h]
  volatile signed __int64 *v21; // [rsp+58h] [rbp-1B0h] BYREF
  __int128 v22; // [rsp+60h] [rbp-1A8h] BYREF
  _BYTE v23[8]; // [rsp+70h] [rbp-198h] BYREF
  std::_Ref_count_base *v24; // [rsp+78h] [rbp-190h]
  _QWORD v25[43]; // [rsp+80h] [rbp-188h] BYREF

  v6 = a3;
  SetThreadName((WCHAR *)L"RPC CacheStorage_delete");
  HangDetectionWatchDog::Activity::Activity((HangDetectionWatchDog::Activity *)&v21, v8);
  *a5 = 0;
  if ( !a4 && v6 )
  {
    _o_terminate(v9);
LABEL_17:
    MicrosoftTelemetryAssertTriggeredNoArgs();
    goto LABEL_12;
  }
  wil::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v25,
    "CS_CacheStorage_delete");
  v25[0] = &CacheStorageTraceLogging::CS_CacheStorage_delete::`vftable';
  v18 = v6;
  v19 = a4;
  CacheStorageTraceLogging::CS_CacheStorage_delete::StartActivity(v25, a2, &v18);
  SequentialExecutionEnforcer::Start(a2[4], &v17);
  v10 = *(_QWORD *)(*a2 + 8);
  v11 = DelayInitObject<CacheStorageTables>::Get(a2 + 6);
  *(_QWORD *)&v22 = v6;
  *((_QWORD *)&v22 + 1) = a4;
  v12 = std::enable_shared_from_this<QuotaSession>::shared_from_this(v10 + 40, v23);
  ActiveReferenceList<CacheActiveReference>::GetActiveReferenceHelper<gsl::basic_string_span<unsigned short const,-1> &,std::shared_ptr<CacheStorageActiveReference>>(
    (PCRITICAL_SECTION)(v10 + 176),
    &v18,
    1,
    &v22,
    v12);
  v13 = operator new(0x20u);
  *v13 = &ActiveReferenceHelper<QuotaOrigin>::`vftable';
  v13[1] = 0;
  v13[2] = 0;
  if ( v19 )
    _InterlockedIncrement((volatile signed __int32 *)v19 + 2);
  v13[1] = v18;
  v13[2] = v19;
  v13[3] = v10 + 176;
  *v13 = &ActiveDeletionReference<CacheActiveReference>::`vftable';
  v20 = v13;
  if ( v19 )
    std::_Ref_count_base::_Decref(v19);
  if ( v24 )
    std::_Ref_count_base::_Decref(v24);
  LOBYTE(a4) = CacheActiveReference::MarkForDeletion(v13[1], v11, a2 + 2);
  if ( v13 )
  {
    ActiveDeletionReference<CacheActiveReference>::~ActiveDeletionReference<CacheActiveReference>(v13);
    operator delete(v13);
  }
  if ( v17 )
  {
    v14 = *v17;
    *v17 = 0;
    if ( !v14 )
      goto LABEL_17;
  }
LABEL_12:
  *a5 = (_BYTE)a4;
  CacheStorageTraceLogging::CS_CacheStorage_delete::Stop(
    (CacheStorageTraceLogging::CS_CacheStorage_delete *)v25,
    (unsigned __int8)a4);
  v25[0] = &CacheStorageTraceLogging::CS_CacheStorage_delete::`vftable';
  wil::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v25);
  wil::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(v25);
  v15 = v21;
  if ( _InterlockedExchangeAdd64(v21, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
    SetThreadpoolTimer(*((PTP_TIMER *)v15 + 1), 0, 0, 0);
  SetThreadName((WCHAR *)&word_1800D6108);
  return 0;
}

```

## disassembly

```asm
0x18003e350  mov     [rsp+arg_0], rbx
0x18003e355  mov     [rsp+arg_10], rsi
0x18003e35a  push    rdi
0x18003e35b  push    r12
0x18003e35d  push    r13
0x18003e35f  push    r14
0x18003e361  push    r15
0x18003e363  sub     rsp, 1E0h
0x18003e36a  mov     rax, cs:__security_cookie
0x18003e371  xor     rax, rsp
0x18003e374  mov     [rsp+208h+var_30], rax
0x18003e37c  mov     rdi, r9
0x18003e37f  mov     ebx, r8d
0x18003e382  mov     rsi, rdx
0x18003e385  mov     r13, [rsp+208h+arg_20]
0x18003e38d  lea     rcx, aRpcCachestorag; "RPC CacheStorage_delete"
0x18003e394  call    SetThreadName
0x18003e399  nop
0x18003e39a  lea     rcx, [rsp+208h+var_1B0]; this
0x18003e39f  call    ??0Activity@HangDetectionWatchDog@@QEAA@PEAV1@@Z; HangDetectionWatchDog::Activity::Activity(HangDetectionWatchDog *)
0x18003e3a4  nop
0x18003e3a5  mov     byte ptr [r13+0], 0
0x18003e3aa  xor     r15d, r15d
0x18003e3ad  test    rdi, rdi
0x18003e3b0  jz      loc_18003E5B8
0x18003e3b6  lea     rdx, aCsCachestorage_3; "CS_CacheStorage_delete"
0x18003e3bd  lea     rcx, [rsp+208h+var_188]
0x18003e3c5  call    ??0?$ActivityBase@VStorageServerProvider@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18003e3ca  lea     rax, ??_7CS_CacheStorage_delete@CacheStorageTraceLogging@@6B@; const CacheStorageTraceLogging::CS_CacheStorage_delete::`vftable'
0x18003e3d1  mov     [rsp+208h+var_188], rax
0x18003e3d9  mov     [rsp+208h+var_1C8], rbx
0x18003e3de  mov     [rsp+208h+var_1C0], rdi
0x18003e3e3  lea     r8, [rsp+208h+var_1C8]
0x18003e3e8  mov     rdx, rsi
0x18003e3eb  lea     rcx, [rsp+208h+var_188]
0x18003e3f3  call    ?StartActivity@CS_CacheStorage_delete@CacheStorageTraceLogging@@QEAAXPEAXV?$basic_string_span@$$CBG$0?0@gsl@@@Z; CacheStorageTraceLogging::CS_CacheStorage_delete::StartActivity(void *,gsl::basic_string_span<ushort const,-1>)
0x18003e3f8  nop
0x18003e3f9  lea     rdx, [rsp+208h+var_1D8]
0x18003e3fe  mov     rcx, [rsi+20h]
0x18003e402  call    ?Start@SequentialExecutionEnforcer@@QEAA?AVInProgressExecution@1@XZ; SequentialExecutionEnforcer::Start(void)
0x18003e407  nop
0x18003e408  mov     rax, [rsi]
0x18003e40b  mov     r14, [rax+8]
0x18003e40f  lea     rcx, [rsi+30h]
0x18003e413  call    ?Get@?$DelayInitObject@UCacheStorageTables@@@@QEBAAEBUCacheStorageTables@@XZ; DelayInitObject<CacheStorageTables>::Get(void)
0x18003e418  mov     r12, rax
0x18003e41b  mov     [rsp+208h+var_1A8], rbx
0x18003e420  mov     [rsp+208h+var_1A0], rdi
0x18003e425  lea     rdi, [r14+0B0h]
0x18003e42c  lea     rcx, [r14+28h]
0x18003e430  lea     rdx, [rsp+208h+var_198]
0x18003e435  call    ?shared_from_this@?$enable_shared_from_this@VQuotaSession@@@std@@QEAA?AV?$shared_ptr@VQuotaSession@@@2@XZ; std::enable_shared_from_this<QuotaSession>::shared_from_this(void)
0x18003e43a  nop
0x18003e43b  mov     [rsp+208h+var_1E8], rax; __int64
0x18003e440  lea     r9, [rsp+208h+var_1A8]
0x18003e445  mov     r8b, 1
0x18003e448  lea     rdx, [rsp+208h+var_1C8]
0x18003e44d  mov     rcx, rdi; CriticalSection
0x18003e450  call    ??$GetActiveReferenceHelper@AEAV?$basic_string_span@$$CBG$0?0@gsl@@V?$shared_ptr@VCacheStorageActiveReference@@@std@@@?$ActiveReferenceList@VCacheActiveReference@@@@AEAA?AV?$shared_ptr@VCacheActiveReference@@@std@@_NAEAV?$basic_string_span@$$CBG$0?0@gsl@@$$QEAV?$shared_ptr@VCacheStorageActiveReference@@@2@@Z; ActiveReferenceList<CacheActiveReference>::GetActiveReferenceHelper<gsl::basic_string_span<ushort const,-1> &,std::shared_ptr<CacheStorageActiveReference>>(bool,gsl::basic_string_span<ushort const,-1> &,std::shared_ptr<CacheStorageActiveReference> &&)
0x18003e455  nop
0x18003e456  mov     r14d, 20h ; ' '
0x18003e45c  mov     ecx, r14d; Size
0x18003e45f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003e464  mov     rbx, rax
0x18003e467  lea     rax, ??_7?$ActiveReferenceHelper@VQuotaOrigin@@@@6B@; const ActiveReferenceHelper<QuotaOrigin>::`vftable'
0x18003e46e  mov     [rbx], rax
0x18003e471  mov     qword ptr [rbx+8], 0
0x18003e479  mov     qword ptr [rbx+10h], 0
0x18003e481  mov     rax, [rsp+208h+var_1C0]
0x18003e486  test    rax, rax
0x18003e489  jz      short loc_18003E48F
0x18003e48b  lock inc dword ptr [rax+8]
0x18003e48f  mov     rax, [rsp+208h+var_1C8]
0x18003e494  mov     [rbx+8], rax
0x18003e498  mov     rax, [rsp+208h+var_1C0]
0x18003e49d  mov     [rbx+10h], rax
0x18003e4a1  mov     [rbx+18h], rdi
0x18003e4a5  lea     rax, ??_7?$ActiveDeletionReference@VCacheActiveReference@@@@6B@; const ActiveDeletionReference<CacheActiveReference>::`vftable'
0x18003e4ac  mov     [rbx], rax
0x18003e4af  mov     [rsp+208h+var_1B8], rbx
0x18003e4b4  mov     rcx, [rsp+208h+var_1C0]; this
0x18003e4b9  test    rcx, rcx
0x18003e4bc  jz      short loc_18003E4C4
0x18003e4be  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003e4c3  nop
0x18003e4c4  mov     rcx, [rsp+208h+var_190]; this
0x18003e4c9  test    rcx, rcx
0x18003e4cc  jz      short loc_18003E4D3
0x18003e4ce  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003e4d3  lea     r8, [rsi+10h]
0x18003e4d7  mov     rdx, r12
0x18003e4da  mov     rcx, [rbx+8]
0x18003e4de  call    ?MarkForDeletion@CacheActiveReference@@QEAA_NAEBV?$shared_ptr@UIDatabaseTable@EseHelper@@@std@@AEBV?$shared_ptr@UIQuotaSession@@@3@@Z; CacheActiveReference::MarkForDeletion(std::shared_ptr<EseHelper::IDatabaseTable> const &,std::shared_ptr<IQuotaSession> const &)
0x18003e4e3  mov     dil, al
0x18003e4e6  test    rbx, rbx
0x18003e4e9  jz      short loc_18003E4FF
0x18003e4eb  mov     rcx, rbx
0x18003e4ee  call    ??1?$ActiveDeletionReference@VCacheActiveReference@@@@UEAA@XZ; ActiveDeletionReference<CacheActiveReference>::~ActiveDeletionReference<CacheActiveReference>(void)
0x18003e4f3  mov     rdx, r14
0x18003e4f6  mov     rcx, rbx; Block
0x18003e4f9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003e4fe  nop
0x18003e4ff  mov     rcx, [rsp+208h+var_1D8]
0x18003e504  test    rcx, rcx
0x18003e507  jz      short loc_18003E515
0x18003e509  xor     eax, eax
0x18003e50b  xchg    al, [rcx]
0x18003e50d  test    al, al
0x18003e50f  jz      loc_18003E5C8
0x18003e515  mov     [r13+0], dil
0x18003e519  mov     dl, dil; unsigned __int8
0x18003e51c  lea     rcx, [rsp+208h+var_188]; this
0x18003e524  call    ?Stop@CS_CacheStorage_delete@CacheStorageTraceLogging@@QEAAXE@Z; CacheStorageTraceLogging::CS_CacheStorage_delete::Stop(uchar)
0x18003e529  nop
0x18003e52a  lea     rax, ??_7CS_CacheStorage_delete@CacheStorageTraceLogging@@6B@; const CacheStorageTraceLogging::CS_CacheStorage_delete::`vftable'
0x18003e531  mov     [rsp+208h+var_188], rax
0x18003e539  lea     rcx, [rsp+208h+var_188]
0x18003e541  call    ?Destroy@?$ActivityBase@VStorageServerProvider@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18003e546  lea     rcx, [rsp+208h+var_188]
0x18003e54e  call    ??1?$ActivityBase@VStorageServerProvider@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<StorageServerProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18003e553  nop
0x18003e554  mov     rcx, [rsp+208h+var_1B0]
0x18003e559  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003e55d  lock xadd [rcx], rax
0x18003e562  cmp     rax, 1
0x18003e566  jnz     short loc_18003E57B
0x18003e568  xor     r9d, r9d; msWindowLength
0x18003e56b  xor     r8d, r8d; msPeriod
0x18003e56e  xor     edx, edx; pftDueTime
0x18003e570  mov     rcx, [rcx+8]; pti
0x18003e574  call    cs:__imp_SetThreadpoolTimer
0x18003e57a  nop
0x18003e57b  lea     rcx, word_1800D6108; lpWideCharStr
0x18003e582  call    SetThreadName
0x18003e587  nop
0x18003e588  mov     eax, r15d
0x18003e58b  mov     rcx, [rsp+208h+var_30]
0x18003e593  xor     rcx, rsp; StackCookie
0x18003e596  call    __security_check_cookie
0x18003e59b  lea     r11, [rsp+208h+var_28]
0x18003e5a3  mov     rbx, [r11+30h]
0x18003e5a7  mov     rsi, [r11+40h]
0x18003e5ab  mov     rsp, r11
0x18003e5ae  pop     r15
0x18003e5b0  pop     r14
0x18003e5b2  pop     r13
0x18003e5b4  pop     r12
0x18003e5b6  pop     rdi
0x18003e5b7  retn
0x18003e5b8  test    rbx, rbx
0x18003e5bb  jz      loc_18003E3B6
0x18003e5c1  call    cs:__imp__o_terminate
0x18003e5c7  nop
0x18003e5c8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003e5cd  jmp     loc_18003E515
0x18003e5d2  mov     r15d, dword ptr [rsp+208h+var_1D8]
0x18003e5d7  jmp     loc_18003E554
```
