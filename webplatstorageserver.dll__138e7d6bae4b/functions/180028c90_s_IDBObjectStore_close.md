# s_IDBObjectStore_close

- ea: `0x180028c90`
- end: `0x180028f92`
- name: `s_IDBObjectStore_close`
- size: `770`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800273f0`
- `0x180028c90`
- `0x180029718`
- `0x180029e74`
- `0x180031890`
- `0x18004ca40`
- `0x180051bb4`
- `0x1800520ec`
- `0x180052a4c`
- `0x18005e07c`
- `0x180070e88`
- `0x1800750fc`
- `0x180080fb0`
- `0x1800810a4`
- `0x18008149c`
- `0x180081b40`
- `0x180083fcc`
- `0x180084034`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028efd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028efd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180028d15`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180028e4d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180028d15`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180028e4d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall s_IDBObjectStore_close(__int64 a1, void **a2)
{
  unsigned int v3; // esi
  volatile signed __int32 *v4; // rbx
  __int64 v6; // rcx
  char v7; // bl
  signed int v8; // eax
  __int64 v9; // rdx
  void *v10; // rbx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-E0h] BYREF
  void **v12; // [rsp+30h] [rbp-D0h] BYREF
  int v13; // [rsp+38h] [rbp-C8h] BYREF
  char v14; // [rsp+3Ch] [rbp-C4h]
  int v15; // [rsp+60h] [rbp-A0h] BYREF
  const char *v16; // [rsp+68h] [rbp-98h]
  __int64 v17; // [rsp+70h] [rbp-90h]
  char v18; // [rsp+78h] [rbp-88h]
  int v19; // [rsp+80h] [rbp-80h]
  _BYTE v20[152]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v21; // [rsp+120h] [rbp+20h]
  int v22; // [rsp+130h] [rbp+30h]
  __int64 v23; // [rsp+138h] [rbp+38h]
  int *v24; // [rsp+140h] [rbp+40h]
  void *Block; // [rsp+148h] [rbp+48h] BYREF
  _QWORD v26[3]; // [rsp+150h] [rbp+50h] BYREF
  int v27; // [rsp+168h] [rbp+68h]
  int *v28; // [rsp+170h] [rbp+70h]
  char v29; // [rsp+178h] [rbp+78h]

  SetThreadName((WCHAR *)L"RPC IDBStor_close");
  if ( dword_180114128 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 5060LL) )
  {
    Init_thread_header(&dword_180114128);
    if ( dword_180114128 == -1 )
    {
      HangDetectionWatchDog::HangDetectionWatchDog(v6, 300000);
      atexit(HangDetectionWatchDog::s_DefaultInstance_::_2_::_dynamic_atexit_destructor_for__s_instance__);
      Init_thread_footer(&dword_180114128);
    }
  }
  _InterlockedIncrement64(&qword_180114130);
  pftDueTime = (struct _FILETIME)qword_180114140;
  SetThreadpoolTimer(pti, &pftDueTime, 0, 0);
  v13 = 0;
  v14 = 0;
  v18 = 0;
  v15 = 0;
  v16 = "IDB_IDBObjectStore_close";
  v17 = 0;
  v19 = 0;
  v21 = 0;
  memset_0(v20, 0, sizeof(v20));
  v22 = 1;
  v23 = 0;
  v24 = &v13;
  Block = 0;
  v26[0] = 0;
  v26[1] = &v12;
  v26[2] = 0;
  v27 = 0;
  v28 = &v15;
  v29 = 0;
  v12 = &IndexedDbTraceLogging::IDB_IDBObjectStore_close::`vftable';
  IndexedDbTraceLogging::IDB_IDBObjectStore_close::StartActivity(
    (IndexedDbTraceLogging::IDB_IDBObjectStore_close *)&v12,
    *a2);
  v3 = -2147024809;
  v4 = (volatile signed __int32 *)*a2;
  if ( *a2 )
  {
    v3 = CIndexedDBServerObjectStore::Close((CIndexedDBServerObjectStore *)*a2);
    if ( _InterlockedExchangeAdd(v4 + 20, 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(void *, __int64))v4)((void *)v4, 1);
    *a2 = 0;
  }
  wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v12, v3);
  v12 = &IndexedDbTraceLogging::IDB_IDBObjectStore_close::`vftable';
  if ( !Block )
    goto LABEL_7;
  wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    &v12,
    &pftDueTime);
  if ( Block && *(_DWORD *)Block == 1 )
  {
    v7 = 1;
  }
  else
  {
    v7 = 0;
    wil::details::shared_object<wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(&Block);
  }
  if ( pftDueTime )
    ReleaseSRWLockExclusive(*(PSRWLOCK *)&pftDueTime);
  if ( v7 )
  {
LABEL_7:
    if ( *v24 == 1 )
    {
      v8 = v24[22];
      pftDueTime.dwLowDateTime = v8;
      v9 = 2147942974LL;
      if ( v8 < 0 )
        v9 = (unsigned int)v8;
      wil::ActivityBase<StorageServerProvider,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        v24,
        v9,
        &pftDueTime);
      wil::ActivityBase<StorageServerProvider,1,70368744177666,4,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(&v12);
    }
  }
  if ( v27 )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v26);
  if ( Block )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block, 0xFFFFFFFF) == 1 )
    {
      v10 = Block;
      if ( Block )
      {
        wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>((char *)Block + 8);
        operator delete(v10);
      }
    }
    Block = 0;
  }
  wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>(&v13);
  if ( _InterlockedExchangeAdd64(&qword_180114130, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
    SetThreadpoolTimer(pti, 0, 0, 0);
  return SetThreadName((WCHAR *)&word_1800D6108);
}

```

## disassembly

```asm
0x180028c90  push    rbp
0x180028c92  push    rbx
0x180028c93  push    rsi
0x180028c94  push    rdi
0x180028c95  push    r12
0x180028c97  push    r14
0x180028c99  lea     rbp, [rsp-98h]
0x180028ca1  sub     rsp, 198h
0x180028ca8  mov     rax, cs:__security_cookie
0x180028caf  xor     rax, rsp
0x180028cb2  mov     [rbp+0C0h+var_40], rax
0x180028cb9  mov     rdi, rdx
0x180028cbc  lea     rcx, aRpcIdbstorClos; "RPC IDBStor_close"
0x180028cc3  call    SetThreadName
0x180028cc8  mov     ecx, cs:_tls_index
0x180028cce  mov     rax, gs:58h
0x180028cd7  mov     edx, 13C4h
0x180028cdc  mov     rax, [rax+rcx*8]
0x180028ce0  mov     eax, [rdx+rax]
0x180028ce3  cmp     cs:dword_180114128, eax
0x180028ce9  jg      loc_180028E98
0x180028cef  lock inc cs:qword_180114130
0x180028cf7  mov     rax, cs:qword_180114140
0x180028cfe  mov     qword ptr [rsp+1C0h+pftDueTime.dwLowDateTime], rax
0x180028d03  xor     r9d, r9d; msWindowLength
0x180028d06  xor     r8d, r8d; msPeriod
0x180028d09  lea     rdx, [rsp+1C0h+pftDueTime]; pftDueTime
0x180028d0e  mov     rcx, cs:pti; pti
0x180028d15  call    cs:__imp_SetThreadpoolTimer
0x180028d1b  nop
0x180028d1c  xor     r14d, r14d
0x180028d1f  mov     [rsp+1C0h+var_188], r14d
0x180028d24  mov     [rsp+1C0h+var_184], r14b
0x180028d29  mov     [rsp+1C0h+var_148], r14b
0x180028d2e  mov     [rsp+1C0h+var_160], r14d
0x180028d33  lea     rax, aIdbIdbobjectst_3; "IDB_IDBObjectStore_close"
0x180028d3a  mov     [rsp+1C0h+var_158], rax
0x180028d3f  mov     [rsp+1C0h+var_150], r14
0x180028d44  mov     [rbp+0C0h+var_140], r14d
0x180028d48  xorps   xmm0, xmm0
0x180028d4b  movdqa  [rbp+0C0h+var_A0], xmm0
0x180028d50  xor     edx, edx; Val
0x180028d52  mov     r8d, 98h; Size
0x180028d58  lea     rcx, [rbp+0C0h+var_138]; void *
0x180028d5c  call    memset_0
0x180028d61  mov     [rbp+0C0h+var_90], 1
0x180028d68  xor     eax, eax
0x180028d6a  mov     [rbp+0C0h+var_88], rax
0x180028d6e  lea     rax, [rsp+1C0h+var_188]
0x180028d73  mov     [rbp+0C0h+var_80], rax
0x180028d77  mov     [rbp+0C0h+Block], r14
0x180028d7b  mov     [rbp+0C0h+var_70], r14
0x180028d7f  lea     rax, [rsp+1C0h+var_190]
0x180028d84  mov     [rbp+0C0h+var_68], rax
0x180028d88  mov     [rbp+0C0h+var_60], r14
0x180028d8c  mov     [rbp+0C0h+var_58], r14d
0x180028d90  lea     rax, [rsp+1C0h+var_160]
0x180028d95  mov     [rbp+0C0h+var_50], rax
0x180028d99  mov     [rbp+0C0h+var_48], r14b
0x180028d9d  lea     r12, ??_7IDB_IDBObjectStore_close@IndexedDbTraceLogging@@6B@; const IndexedDbTraceLogging::IDB_IDBObjectStore_close::`vftable'
0x180028da4  mov     [rsp+1C0h+var_190], r12
0x180028da9  mov     rdx, [rdi]; void *
0x180028dac  lea     rcx, [rsp+1C0h+var_190]; this
0x180028db1  call    ?StartActivity@IDB_IDBObjectStore_close@IndexedDbTraceLogging@@QEAAXPEAX@Z; IndexedDbTraceLogging::IDB_IDBObjectStore_close::StartActivity(void *)
0x180028db6  nop
0x180028db7  mov     esi, 80070057h
0x180028dbc  mov     rbx, [rdi]
0x180028dbf  test    rbx, rbx
0x180028dc2  jz      short loc_180028DE2
0x180028dc4  mov     rcx, rbx; this
0x180028dc7  call    ?Close@CIndexedDBServerObjectStore@@QEAAJXZ; CIndexedDBServerObjectStore::Close(void)
0x180028dcc  mov     esi, eax
0x180028dce  or      eax, 0FFFFFFFFh
0x180028dd1  lock xadd [rbx+50h], eax
0x180028dd6  cmp     eax, 1
0x180028dd9  jz      loc_180028E80
0x180028ddf  mov     [rdi], r14
0x180028de2  mov     edx, esi
0x180028de4  lea     rcx, [rsp+1C0h+var_190]
0x180028de9  call    ?Stop@?$ActivityBase@VStorageServerProvider@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180028dee  mov     [rsp+1C0h+var_190], r12
0x180028df3  cmp     [rbp+0C0h+Block], r14
0x180028df7  jnz     loc_180028F05
0x180028dfd  mov     rcx, [rbp+0C0h+var_80]
0x180028e01  cmp     dword ptr [rcx], 1
0x180028e04  jz      loc_180028F34
0x180028e0a  cmp     [rbp+0C0h+var_58], r14d
0x180028e0e  jnz     loc_180028ED8
0x180028e14  mov     rcx, [rbp+0C0h+Block]
0x180028e18  test    rcx, rcx
0x180028e1b  jnz     loc_180028F5E
0x180028e21  lea     rcx, [rsp+1C0h+var_188]
0x180028e26  call    ??1?$ActivityData@VStorageServerProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VStorageServerProvider@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>(void)
0x180028e2b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180028e2f  lock xadd cs:qword_180114130, rax
0x180028e38  cmp     rax, 1
0x180028e3c  jnz     short loc_180028E54
0x180028e3e  xor     r9d, r9d; msWindowLength
0x180028e41  xor     r8d, r8d; msPeriod
0x180028e44  xor     edx, edx; pftDueTime
0x180028e46  mov     rcx, cs:pti; pti
0x180028e4d  call    cs:__imp_SetThreadpoolTimer
0x180028e53  nop
0x180028e54  lea     rcx, word_1800D6108; lpWideCharStr
0x180028e5b  call    SetThreadName
0x180028e60  nop
0x180028e61  mov     rcx, [rbp+0C0h+var_40]
0x180028e68  xor     rcx, rsp; StackCookie
0x180028e6b  call    __security_check_cookie
0x180028e70  add     rsp, 198h
0x180028e77  pop     r14
0x180028e79  pop     r12
0x180028e7b  pop     rdi
0x180028e7c  pop     rsi
0x180028e7d  pop     rbx
0x180028e7e  pop     rbp
0x180028e7f  retn
0x180028e80  mov     rax, [rbx]
0x180028e83  mov     edx, 1
0x180028e88  mov     rcx, rbx
0x180028e8b  mov     rax, [rax]
0x180028e8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e93  jmp     loc_180028DDF
0x180028e98  lea     rcx, dword_180114128
0x180028e9f  call    _Init_thread_header
0x180028ea4  cmp     cs:dword_180114128, 0FFFFFFFFh
0x180028eab  jnz     loc_180028CEF
0x180028eb1  mov     edx, 493E0h
0x180028eb6  call    ??0HangDetectionWatchDog@@QEAA@V?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@@Z; HangDetectionWatchDog::HangDetectionWatchDog(std::chrono::duration<__int64,std::ratio<1,1000>>)
0x180028ebb  lea     rcx, _HangDetectionWatchDog__s_DefaultInstance____2____dynamic_atexit_destructor_for__s_instance__; void (__cdecl *)()
0x180028ec2  call    atexit
0x180028ec7  lea     rcx, dword_180114128
0x180028ece  call    _Init_thread_footer
0x180028ed3  jmp     loc_180028CEF
0x180028ed8  lea     rcx, [rbp+0C0h+var_70]; this
0x180028edc  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180028ee1  jmp     loc_180028E14
0x180028ee6  test    bl, bl
0x180028ee8  jz      loc_180028E0A
0x180028eee  jmp     loc_180028DFD
0x180028ef3  mov     rcx, qword ptr [rsp+1C0h+pftDueTime.dwLowDateTime]; SRWLock
0x180028ef8  test    rcx, rcx
0x180028efb  jz      short loc_180028EE6
0x180028efd  call    cs:__imp_ReleaseSRWLockExclusive
0x180028f03  jmp     short loc_180028EE6
0x180028f05  lea     rdx, [rsp+1C0h+pftDueTime]
0x180028f0a  lea     rcx, [rsp+1C0h+var_190]
0x180028f0f  call    ?LockExclusive@?$ActivityBase@VStorageServerProvider@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180028f14  mov     rax, [rbp+0C0h+Block]
0x180028f18  test    rax, rax
0x180028f1b  jz      short loc_180028F26
0x180028f1d  cmp     dword ptr [rax], 1
0x180028f20  jnz     short loc_180028F26
0x180028f22  mov     bl, 1
0x180028f24  jmp     short loc_180028EF3
0x180028f26  mov     bl, r14b
0x180028f29  lea     rcx, [rbp+0C0h+Block]
0x180028f2d  call    ?reset@?$shared_object@V?$ActivityData@VStorageServerProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VStorageServerProvider@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180028f32  jmp     short loc_180028EF3
0x180028f34  mov     eax, [rcx+58h]
0x180028f37  mov     [rsp+1C0h+pftDueTime.dwLowDateTime], eax
0x180028f3b  mov     edx, 8007023Eh
0x180028f40  test    eax, eax
0x180028f42  cmovs   edx, eax
0x180028f45  lea     r8, [rsp+1C0h+pftDueTime]
0x180028f4a  call    ?SetStopResult@?$ActivityData@VStorageServerProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VStorageServerProvider@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<StorageServerProvider,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x180028f4f  lea     rcx, [rsp+1C0h+var_190]
0x180028f54  call    ?ReportStopActivity@?$ActivityBase@VStorageServerProvider@@$00$0EAAAAAAAAAAC@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<StorageServerProvider,1,70368744177666,4,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x180028f59  jmp     loc_180028E0A
0x180028f5e  or      eax, 0FFFFFFFFh
0x180028f61  lock xadd [rcx], eax
0x180028f65  cmp     eax, 1
0x180028f68  jnz     short loc_180028F89
0x180028f6a  mov     rbx, [rbp+0C0h+Block]
0x180028f6e  test    rbx, rbx
0x180028f71  jz      short loc_180028F89
0x180028f73  lea     rcx, [rbx+8]
0x180028f77  call    ??1?$ActivityData@VStorageServerProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VStorageServerProvider@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>(void)
0x180028f7c  mov     edx, 110h
0x180028f81  mov     rcx, rbx; Block
0x180028f84  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180028f89  mov     [rbp+0C0h+Block], r14
0x180028f8d  jmp     loc_180028E21
```
