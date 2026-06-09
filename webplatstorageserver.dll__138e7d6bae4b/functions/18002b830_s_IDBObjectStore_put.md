# s_IDBObjectStore_put

- ea: `0x18002b830`
- end: `0x18002bb75`
- name: `s_IDBObjectStore_put`
- size: `837`
- prototype: `__int64 __fastcall(__int64, __int64, const struct __MIDL_RPCIndexedDB_0004 *, RTL_SRWLOCK *, struct __MIDL_RPCIndexedDB_0001 *)`
- caller_count: `0`
- callee_count: `18`
- tags: ``

## callees

- `0x18002170c`
- `0x1800273f0`
- `0x180029e74`
- `0x18002a060`
- `0x18002b480`
- `0x18002b830`
- `0x18002bb80`
- `0x18002bbf4`
- `0x18002bd04`
- `0x18004ca40`
- `0x180051bb4`
- `0x180052a4c`
- `0x18005e07c`
- `0x180080fb0`
- `0x180081b40`
- `0x1800b0bcc`
- `0x1800b1e1c`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bafc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bafc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002b8a5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002ba19`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002b8a5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002ba19`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall s_IDBObjectStore_put(
        __int64 a1,
        __int64 a2,
        const struct __MIDL_RPCIndexedDB_0004 *a3,
        RTL_SRWLOCK *a4,
        struct __MIDL_RPCIndexedDB_0001 *a5)
{
  struct HangDetectionWatchDog *v8; // rbx
  char v9; // si
  int v10; // edi
  struct _FILETIME v11; // r15
  unsigned __int8 (__fastcall *v13)(struct _FILETIME); // rsi
  char v14; // di
  signed int v15; // eax
  __int64 v16; // rdx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-E0h] BYREF
  PSRWLOCK SRWLock; // [rsp+28h] [rbp-D8h] BYREF
  void **v19; // [rsp+30h] [rbp-D0h] BYREF
  int v20; // [rsp+38h] [rbp-C8h] BYREF
  char v21; // [rsp+3Ch] [rbp-C4h]
  int v22; // [rsp+60h] [rbp-A0h] BYREF
  const char *v23; // [rsp+68h] [rbp-98h]
  __int64 v24; // [rsp+70h] [rbp-90h]
  char v25; // [rsp+78h] [rbp-88h]
  int v26; // [rsp+80h] [rbp-80h]
  _BYTE v27[152]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v28; // [rsp+120h] [rbp+20h]
  int v29; // [rsp+130h] [rbp+30h]
  __int64 v30; // [rsp+138h] [rbp+38h]
  int *v31; // [rsp+140h] [rbp+40h]
  _QWORD v32[4]; // [rsp+148h] [rbp+48h] BYREF
  int v33; // [rsp+168h] [rbp+68h]
  int *v34; // [rsp+170h] [rbp+70h]
  char v35; // [rsp+178h] [rbp+78h]

  SRWLock = a4;
  SetThreadName(L"RPC IDBStor_put");
  v8 = HangDetectionWatchDog::s_DefaultInstance();
  _InterlockedIncrement64((volatile signed __int64 *)v8);
  pftDueTime = (struct _FILETIME)*((_QWORD *)v8 + 2);
  SetThreadpoolTimer(*((PTP_TIMER *)v8 + 1), &pftDueTime, 0, 0);
  v9 = 0;
  v20 = 0;
  v21 = 0;
  v25 = 0;
  v22 = 0;
  v23 = "IDB_IDBObjectStore_put";
  v24 = 0;
  v26 = 0;
  v28 = 0;
  memset_0(v27, 0, sizeof(v27));
  v29 = 1;
  v30 = 0;
  v31 = &v20;
  v32[0] = 0;
  v32[1] = 0;
  v32[2] = &v19;
  v32[3] = 0;
  v33 = 0;
  v34 = &v22;
  v35 = 0;
  v19 = &IndexedDbTraceLogging::IDB_IDBObjectStore_put::`vftable';
  IndexedDbTraceLogging::IDB_IDBObjectStore_put::StartActivity(
    (IndexedDbTraceLogging::IDB_IDBObjectStore_put *)&v19,
    (void *)a2,
    a3,
    (const struct __MIDL_RPCIndexedDB_0001 *)a4);
  if ( a5 )
  {
    *(_OWORD *)a5 = 0;
    *((_QWORD *)a5 + 2) = 0;
  }
  v10 = -2147024809;
  if ( !a2 || !a3 )
    goto LABEL_17;
  pftDueTime = 0;
  if ( (int)CIndexedDBServerConnectionsMgr::GetCallerId((struct ICallerIdentity **)&pftDueTime) < 0 )
  {
    v10 = -2147024891;
    goto LABEL_17;
  }
  v11 = pftDueTime;
  if ( !*(_BYTE *)(a2 + 56)
    || (*(unsigned int (__fastcall **)(_QWORD, struct _FILETIME))(**(_QWORD **)(a2 + 8) + 16LL))(
         *(_QWORD *)(a2 + 8),
         pftDueTime) )
  {
    goto LABEL_8;
  }
  v13 = *(unsigned __int8 (__fastcall **)(struct _FILETIME))(**(_QWORD **)&v11 + 40LL);
  v14 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 8) + 40LL))(*(_QWORD *)(a2 + 8));
  if ( v14 != ((__int64 (__fastcall *)(_QWORD))v13)(v11) )
  {
    v9 = 0;
LABEL_8:
    v10 = -2147024891;
    goto LABEL_9;
  }
  v10 = CIndexedDBServerObjectStore::Put(
          (CIndexedDBServerObjectStore *)a2,
          a3,
          (const struct __MIDL_RPCIndexedDB_0001 *)SRWLock,
          a5);
  v9 = 0;
  pftDueTime.dwLowDateTime = 0;
  if ( v10 < 0
    && (int)CIndexedDBServerObjectStore::GetClientContextFlags(
              (CIndexedDBServerObjectStore *)a2,
              (unsigned int *)&pftDueTime) >= 0 )
  {
    CIndexedDBServerPhysicalDBManager::HandleCorruptionIfDetected(pftDueTime.dwLowDateTime, v10, 0);
  }
LABEL_9:
  (*(void (__fastcall **)(struct _FILETIME))(**(_QWORD **)&v11 + 8LL))(v11);
  if ( v10 < 0 )
  {
LABEL_17:
    wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
      &v19,
      (unsigned int)v10);
    goto LABEL_11;
  }
  IndexedDbTraceLogging::IDB_IDBObjectStore_put::Stop((IndexedDbTraceLogging::IDB_IDBObjectStore_put *)&v19, a5);
LABEL_11:
  v19 = &IndexedDbTraceLogging::IDB_IDBObjectStore_put::`vftable';
  if ( !v32[0] )
    goto LABEL_12;
  wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(&v19, &SRWLock);
  if ( v32[0] && *(_DWORD *)v32[0] == 1 )
    v9 = 1;
  else
    wil::details::shared_object<wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(v32);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v9 )
  {
LABEL_12:
    if ( *v31 == 1 )
    {
      v15 = v31[22];
      pftDueTime.dwLowDateTime = v15;
      v16 = 2147942974LL;
      if ( v15 < 0 )
        v16 = (unsigned int)v15;
      wil::ActivityBase<StorageServerProvider,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        v31,
        v16,
        &pftDueTime);
      wil::ActivityBase<StorageServerProvider,1,70368744177666,4,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(&v19);
    }
  }
  wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(&v19);
  if ( _InterlockedExchangeAdd64((volatile signed __int64 *)v8, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
    SetThreadpoolTimer(*((PTP_TIMER *)v8 + 1), 0, 0, 0);
  SetThreadName(&word_1800D6108);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002b830  mov     [rsp-8+arg_0], rbx
0x18002b835  push    rbp
0x18002b836  push    rsi
0x18002b837  push    rdi
0x18002b838  push    r12
0x18002b83a  push    r13
0x18002b83c  push    r14
0x18002b83e  push    r15
0x18002b840  lea     rbp, [rsp-90h]
0x18002b848  sub     rsp, 190h
0x18002b84f  mov     rax, cs:__security_cookie
0x18002b856  xor     rax, rsp
0x18002b859  mov     [rbp+0C0h+var_40], rax
0x18002b860  mov     rdi, r9
0x18002b863  mov     [rsp+1C0h+SRWLock], r9
0x18002b868  mov     r12, r8
0x18002b86b  mov     r14, rdx
0x18002b86e  mov     r13, [rbp+0C0h+arg_20]
0x18002b875  lea     rcx, aRpcIdbstorPut; "RPC IDBStor_put"
0x18002b87c  call    SetThreadName
0x18002b881  call    ?s_DefaultInstance@HangDetectionWatchDog@@SAAEAV1@XZ; HangDetectionWatchDog::s_DefaultInstance(void)
0x18002b886  mov     rbx, rax
0x18002b889  lock inc qword ptr [rax]
0x18002b88d  mov     rax, [rax+10h]
0x18002b891  mov     qword ptr [rsp+1C0h+pftDueTime.dwLowDateTime], rax
0x18002b896  xor     r9d, r9d; msWindowLength
0x18002b899  xor     r8d, r8d; msPeriod
0x18002b89c  lea     rdx, [rsp+1C0h+pftDueTime]; pftDueTime
0x18002b8a1  mov     rcx, [rbx+8]; pti
0x18002b8a5  call    cs:__imp_SetThreadpoolTimer
0x18002b8ab  nop
0x18002b8ac  xor     esi, esi
0x18002b8ae  mov     [rsp+1C0h+var_188], esi
0x18002b8b2  mov     [rsp+1C0h+var_184], sil
0x18002b8b7  mov     [rsp+1C0h+var_148], sil
0x18002b8bc  mov     [rsp+1C0h+var_160], esi
0x18002b8c0  lea     rax, aIdbIdbobjectst_9; "IDB_IDBObjectStore_put"
0x18002b8c7  mov     [rsp+1C0h+var_158], rax
0x18002b8cc  mov     [rsp+1C0h+var_150], rsi
0x18002b8d1  mov     [rbp+0C0h+var_140], esi
0x18002b8d4  xorps   xmm0, xmm0
0x18002b8d7  movdqa  [rbp+0C0h+var_A0], xmm0
0x18002b8dc  xor     edx, edx; Val
0x18002b8de  mov     r8d, 98h; Size
0x18002b8e4  lea     rcx, [rbp+0C0h+var_138]; void *
0x18002b8e8  call    memset_0
0x18002b8ed  mov     [rbp+0C0h+var_90], 1
0x18002b8f4  xor     eax, eax
0x18002b8f6  mov     [rbp+0C0h+var_88], rax
0x18002b8fa  lea     rax, [rsp+1C0h+var_188]
0x18002b8ff  mov     [rbp+0C0h+var_80], rax
0x18002b903  mov     [rbp+0C0h+var_78], rsi
0x18002b907  mov     [rbp+0C0h+var_70], rsi
0x18002b90b  lea     rax, [rsp+1C0h+var_190]
0x18002b910  mov     [rbp+0C0h+var_68], rax
0x18002b914  mov     [rbp+0C0h+var_60], rsi
0x18002b918  mov     [rbp+0C0h+var_58], esi
0x18002b91b  lea     rax, [rsp+1C0h+var_160]
0x18002b920  mov     [rbp+0C0h+var_50], rax
0x18002b924  mov     [rbp+0C0h+var_48], sil
0x18002b928  lea     rax, ??_7IDB_IDBObjectStore_put@IndexedDbTraceLogging@@6B@; const IndexedDbTraceLogging::IDB_IDBObjectStore_put::`vftable'
0x18002b92f  mov     [rsp+1C0h+var_190], rax
0x18002b934  mov     r9, rdi; struct __MIDL_RPCIndexedDB_0001 *
0x18002b937  mov     r8, r12; struct __MIDL_RPCIndexedDB_0004 *
0x18002b93a  mov     rdx, r14; void *
0x18002b93d  lea     rcx, [rsp+1C0h+var_190]; this
0x18002b942  call    ?StartActivity@IDB_IDBObjectStore_put@IndexedDbTraceLogging@@QEAAXPEAXAEBU__MIDL_RPCIndexedDB_0004@@PEBU__MIDL_RPCIndexedDB_0001@@@Z; IndexedDbTraceLogging::IDB_IDBObjectStore_put::StartActivity(void *,__MIDL_RPCIndexedDB_0004 const &,__MIDL_RPCIndexedDB_0001 const *)
0x18002b947  nop
0x18002b948  test    r13, r13
0x18002b94b  jnz     loc_18002BB04
0x18002b951  mov     edi, 80070057h
0x18002b956  test    r14, r14
0x18002b959  jz      loc_18002BA5E
0x18002b95f  test    r12, r12
0x18002b962  jz      loc_18002BA5E
0x18002b968  mov     qword ptr [rsp+1C0h+pftDueTime.dwLowDateTime], rsi
0x18002b96d  lea     rcx, [rsp+1C0h+pftDueTime]; struct ICallerIdentity **
0x18002b972  call    ?GetCallerId@CIndexedDBServerConnectionsMgr@@SAJPEAPEAUICallerIdentity@@@Z; CIndexedDBServerConnectionsMgr::GetCallerId(ICallerIdentity * *)
0x18002b977  test    eax, eax
0x18002b979  js      loc_18002BA59
0x18002b97f  mov     al, [r14+38h]
0x18002b983  nop
0x18002b984  mov     r15, qword ptr [rsp+1C0h+pftDueTime.dwLowDateTime]
0x18002b989  test    al, al
0x18002b98b  jz      short loc_18002B9A8
0x18002b98d  mov     rcx, [r14+8]
0x18002b991  mov     rax, [rcx]
0x18002b994  mov     rdx, r15
0x18002b997  mov     rax, [rax+10h]
0x18002b99b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b9a0  test    eax, eax
0x18002b9a2  jz      loc_18002BA6F
0x18002b9a8  mov     edi, 80070005h
0x18002b9ad  mov     rax, [r15]
0x18002b9b0  mov     rcx, r15
0x18002b9b3  mov     rax, [rax+8]
0x18002b9b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b9bc  test    edi, edi
0x18002b9be  js      loc_18002BA5E
0x18002b9c4  mov     rdx, r13; struct __MIDL_RPCIndexedDB_0001 *
0x18002b9c7  lea     rcx, [rsp+1C0h+var_190]; this
0x18002b9cc  call    ?Stop@IDB_IDBObjectStore_put@IndexedDbTraceLogging@@QEAAXAEBU__MIDL_RPCIndexedDB_0001@@@Z; IndexedDbTraceLogging::IDB_IDBObjectStore_put::Stop(__MIDL_RPCIndexedDB_0001 const &)
0x18002b9d1  lea     rax, ??_7IDB_IDBObjectStore_put@IndexedDbTraceLogging@@6B@; const IndexedDbTraceLogging::IDB_IDBObjectStore_put::`vftable'
0x18002b9d8  mov     [rsp+1C0h+var_190], rax
0x18002b9dd  cmp     [rbp+0C0h+var_78], rsi
0x18002b9e1  jnz     loc_18002BB1E
0x18002b9e7  mov     rcx, [rbp+0C0h+var_80]
0x18002b9eb  cmp     dword ptr [rcx], 1
0x18002b9ee  jz      loc_18002BB4B
0x18002b9f4  lea     rcx, [rsp+1C0h+var_190]
0x18002b9f9  call    ??1?$ActivityBase@VStorageServerProvider@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18002b9fe  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002ba02  lock xadd [rbx], rax
0x18002ba07  cmp     rax, 1
0x18002ba0b  jnz     short loc_18002BA20
0x18002ba0d  xor     r9d, r9d; msWindowLength
0x18002ba10  xor     r8d, r8d; msPeriod
0x18002ba13  xor     edx, edx; pftDueTime
0x18002ba15  mov     rcx, [rbx+8]; pti
0x18002ba19  call    cs:__imp_SetThreadpoolTimer
0x18002ba1f  nop
0x18002ba20  lea     rcx, word_1800D6108; lpWideCharStr
0x18002ba27  call    SetThreadName
0x18002ba2c  nop
0x18002ba2d  mov     eax, edi
0x18002ba2f  mov     rcx, [rbp+0C0h+var_40]
0x18002ba36  xor     rcx, rsp; StackCookie
0x18002ba39  call    __security_check_cookie
0x18002ba3e  mov     rbx, [rsp+1C0h+arg_0]
0x18002ba46  add     rsp, 190h
0x18002ba4d  pop     r15
0x18002ba4f  pop     r14
0x18002ba51  pop     r13
0x18002ba53  pop     r12
0x18002ba55  pop     rdi
0x18002ba56  pop     rsi
0x18002ba57  pop     rbp
0x18002ba58  retn
0x18002ba59  mov     edi, 80070005h
0x18002ba5e  mov     edx, edi
0x18002ba60  lea     rcx, [rsp+1C0h+var_190]
0x18002ba65  call    ?Stop@?$ActivityBase@VStorageServerProvider@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002ba6a  jmp     loc_18002B9D1
0x18002ba6f  mov     rcx, [r14+8]
0x18002ba73  mov     rax, [r15]
0x18002ba76  mov     rsi, [rax+28h]
0x18002ba7a  mov     rdx, [rcx]
0x18002ba7d  mov     rax, [rdx+28h]
0x18002ba81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba86  mov     dil, al
0x18002ba89  mov     rcx, r15
0x18002ba8c  mov     rax, rsi
0x18002ba8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba94  cmp     dil, al
0x18002ba97  jnz     short loc_18002BB17
0x18002ba99  mov     r9, r13; struct __MIDL_RPCIndexedDB_0001 *
0x18002ba9c  mov     r8, [rsp+1C0h+SRWLock]; struct __MIDL_RPCIndexedDB_0001 *
0x18002baa1  mov     rdx, r12; struct __MIDL_RPCIndexedDB_0004 *
0x18002baa4  mov     rcx, r14; this
0x18002baa7  call    ?Put@CIndexedDBServerObjectStore@@QEAAJPEBU__MIDL_RPCIndexedDB_0004@@PEBU__MIDL_RPCIndexedDB_0001@@PEAU3@@Z; CIndexedDBServerObjectStore::Put(__MIDL_RPCIndexedDB_0004 const *,__MIDL_RPCIndexedDB_0001 const *,__MIDL_RPCIndexedDB_0001 *)
0x18002baac  mov     edi, eax
0x18002baae  xor     esi, esi
0x18002bab0  mov     [rsp+1C0h+pftDueTime.dwLowDateTime], esi
0x18002bab4  test    eax, eax
0x18002bab6  jns     loc_18002B9AD
0x18002babc  lea     rdx, [rsp+1C0h+pftDueTime]; unsigned int *
0x18002bac1  mov     rcx, r14; this
0x18002bac4  call    ?GetClientContextFlags@CIndexedDBServerObjectStore@@QEAAJPEAK@Z; CIndexedDBServerObjectStore::GetClientContextFlags(ulong *)
0x18002bac9  test    eax, eax
0x18002bacb  js      loc_18002B9AD
0x18002bad1  xor     r8d, r8d; struct CWxString *
0x18002bad4  mov     edx, edi; int
0x18002bad6  mov     ecx, [rsp+1C0h+pftDueTime.dwLowDateTime]; unsigned int
0x18002bada  call    ?HandleCorruptionIfDetected@CIndexedDBServerPhysicalDBManager@@SAXKJPEAVCWxString@@@Z; CIndexedDBServerPhysicalDBManager::HandleCorruptionIfDetected(ulong,long,CWxString *)
0x18002badf  jmp     loc_18002B9AD
0x18002bae4  test    sil, sil
0x18002bae7  jz      loc_18002B9F4
0x18002baed  jmp     loc_18002B9E7
0x18002baf2  mov     rcx, [rsp+1C0h+SRWLock]; SRWLock
0x18002baf7  test    rcx, rcx
0x18002bafa  jz      short loc_18002BAE4
0x18002bafc  call    cs:__imp_ReleaseSRWLockExclusive
0x18002bb02  jmp     short loc_18002BAE4
0x18002bb04  xorps   xmm0, xmm0
0x18002bb07  xor     eax, eax
0x18002bb09  movups  xmmword ptr [r13+0], xmm0
0x18002bb0e  mov     [r13+10h], rax
0x18002bb12  jmp     loc_18002B951
0x18002bb17  xor     esi, esi
0x18002bb19  jmp     loc_18002B9A8
0x18002bb1e  lea     rdx, [rsp+1C0h+SRWLock]
0x18002bb23  lea     rcx, [rsp+1C0h+var_190]
0x18002bb28  call    ?LockExclusive@?$ActivityBase@VStorageServerProvider@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002bb2d  mov     rax, [rbp+0C0h+var_78]
0x18002bb31  test    rax, rax
0x18002bb34  jz      short loc_18002BB40
0x18002bb36  cmp     dword ptr [rax], 1
0x18002bb39  jnz     short loc_18002BB40
0x18002bb3b  mov     sil, 1
0x18002bb3e  jmp     short loc_18002BAF2
0x18002bb40  lea     rcx, [rbp+0C0h+var_78]
0x18002bb44  call    ?reset@?$shared_object@V?$ActivityData@VStorageServerProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VStorageServerProvider@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18002bb49  jmp     short loc_18002BAF2
0x18002bb4b  mov     eax, [rcx+58h]
0x18002bb4e  mov     [rsp+1C0h+pftDueTime.dwLowDateTime], eax
0x18002bb52  mov     edx, 8007023Eh
0x18002bb57  test    eax, eax
0x18002bb59  cmovs   edx, eax
0x18002bb5c  lea     r8, [rsp+1C0h+pftDueTime]
0x18002bb61  call    ?SetStopResult@?$ActivityData@VStorageServerProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VStorageServerProvider@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<StorageServerProvider,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18002bb66  lea     rcx, [rsp+1C0h+var_190]
0x18002bb6b  call    ?ReportStopActivity@?$ActivityBase@VStorageServerProvider@@$00$0EAAAAAAAAAAC@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<StorageServerProvider,1,70368744177666,4,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x18002bb70  jmp     loc_18002B9F4
```
