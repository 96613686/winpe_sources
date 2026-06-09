# s_IDBObjectStore_openIndex

- ea: `0x18002b000`
- end: `0x18002b3a1`
- name: `s_IDBObjectStore_openIndex`
- size: `929`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `broker_com_uri`

## callees

- `0x1800273f0`
- `0x180029e74`
- `0x18002a060`
- `0x18002b000`
- `0x18002b3a8`
- `0x18002b480`
- `0x18002b5a8`
- `0x180045034`
- `0x18004ca40`
- `0x180051bb4`
- `0x180052a4c`
- `0x18005e07c`
- `0x180070e88`
- `0x180080fb0`
- `0x18008149c`
- `0x180081b40`
- `0x180083fcc`
- `0x180084034`
- `0x1800b0bcc`
- `0x1800b1e1c`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b32a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b32a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002b092`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002b210`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002b092`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002b210`

## string_xrefs

- `0x18002b0b0`: `IDB_IDBObjectStore_openIndex`
- `0x18002b039`: `RPC IDBStor_openIndex`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall s_IDBObjectStore_openIndex(__int64 a1, __int64 a2, __int64 a3, void **a4)
{
  int v7; // ebx
  struct ICallerIdentity *v8; // r15
  unsigned __int8 (__fastcall *v10)(struct ICallerIdentity *); // rdi
  char v11; // bl
  __int64 v12; // rcx
  char v13; // di
  int v14; // eax
  __int64 v15; // rdx
  struct ICallerIdentity *v16; // [rsp+20h] [rbp-E0h] BYREF
  struct _FILETIME pftDueTime; // [rsp+28h] [rbp-D8h] BYREF
  void **v18; // [rsp+30h] [rbp-D0h] BYREF
  int v19; // [rsp+38h] [rbp-C8h] BYREF
  char v20; // [rsp+3Ch] [rbp-C4h]
  int v21; // [rsp+60h] [rbp-A0h] BYREF
  const char *v22; // [rsp+68h] [rbp-98h]
  __int64 v23; // [rsp+70h] [rbp-90h]
  char v24; // [rsp+78h] [rbp-88h]
  int v25; // [rsp+80h] [rbp-80h]
  _BYTE v26[152]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v27; // [rsp+120h] [rbp+20h]
  int v28; // [rsp+130h] [rbp+30h]
  __int64 v29; // [rsp+138h] [rbp+38h]
  int *v30; // [rsp+140h] [rbp+40h]
  _QWORD v31[4]; // [rsp+148h] [rbp+48h] BYREF
  int v32; // [rsp+168h] [rbp+68h]
  int *v33; // [rsp+170h] [rbp+70h]
  char v34; // [rsp+178h] [rbp+78h]

  SetThreadName(L"RPC IDBStor_openIndex");
  if ( dword_180114128 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 5060LL) )
  {
    Init_thread_header(&dword_180114128);
    if ( dword_180114128 == -1 )
    {
      HangDetectionWatchDog::HangDetectionWatchDog(v12, 300000);
      atexit(HangDetectionWatchDog::s_DefaultInstance_::_2_::_dynamic_atexit_destructor_for__s_instance__);
      Init_thread_footer(&dword_180114128);
    }
  }
  _InterlockedIncrement64(&qword_180114130);
  pftDueTime = (struct _FILETIME)qword_180114140;
  SetThreadpoolTimer(pti, &pftDueTime, 0, 0);
  v19 = 0;
  v20 = 0;
  v24 = 0;
  v21 = 0;
  v22 = "IDB_IDBObjectStore_openIndex";
  v23 = 0;
  v25 = 0;
  v27 = 0;
  memset_0(v26, 0, sizeof(v26));
  v28 = 1;
  v29 = 0;
  v30 = &v19;
  v31[0] = 0;
  v31[1] = 0;
  v31[2] = &v18;
  v31[3] = 0;
  v32 = 0;
  v33 = &v21;
  v34 = 0;
  v18 = &IndexedDbTraceLogging::IDB_IDBObjectStore_openIndex::`vftable';
  IndexedDbTraceLogging::IDB_IDBObjectStore_openIndex::StartActivity(
    (IndexedDbTraceLogging::IDB_IDBObjectStore_openIndex *)&v18,
    (void *)a2,
    a3);
  if ( a4 )
    *a4 = 0;
  v7 = -2147024809;
  if ( a2 && a4 )
  {
    v16 = 0;
    if ( (int)CIndexedDBServerConnectionsMgr::GetCallerId(&v16) < 0 )
    {
      v7 = -2147024891;
    }
    else
    {
      v8 = v16;
      if ( *(_BYTE *)(a2 + 56)
        && !(*(unsigned int (__fastcall **)(_QWORD, struct ICallerIdentity *))(**(_QWORD **)(a2 + 8) + 16LL))(
              *(_QWORD *)(a2 + 8),
              v16)
        && (v10 = *(unsigned __int8 (__fastcall **)(struct ICallerIdentity *))(*(_QWORD *)v8 + 40LL),
            v11 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 8) + 40LL))(*(_QWORD *)(a2 + 8)),
            v11 == v10(v8)) )
      {
        pftDueTime = 0;
        v7 = CIndexedDBServerObjectStore::OpenIndex(
               (CIndexedDBServerObjectStore *)a2,
               a3,
               (struct CIndexedDBServerIndex **)&pftDueTime);
        LODWORD(v16) = 0;
        if ( v7 >= 0 )
        {
          *a4 = (void *)pftDueTime;
        }
        else if ( (int)CIndexedDBServerObjectStore::GetClientContextFlags(
                         (CIndexedDBServerObjectStore *)a2,
                         (unsigned int *)&v16) >= 0 )
        {
          CIndexedDBServerPhysicalDBManager::HandleCorruptionIfDetected((unsigned int)v16, v7, 0);
        }
      }
      else
      {
        v7 = -2147024891;
      }
      (*(void (__fastcall **)(struct ICallerIdentity *))(*(_QWORD *)v8 + 8LL))(v8);
      if ( v7 >= 0 )
      {
        IndexedDbTraceLogging::IDB_IDBObjectStore_openIndex::Stop(
          (IndexedDbTraceLogging::IDB_IDBObjectStore_openIndex *)&v18,
          *a4);
        goto LABEL_13;
      }
    }
  }
  wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v18, (unsigned int)v7);
LABEL_13:
  v18 = &IndexedDbTraceLogging::IDB_IDBObjectStore_openIndex::`vftable';
  if ( !v31[0] )
    goto LABEL_14;
  wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    &v18,
    &pftDueTime);
  if ( v31[0] && *(_DWORD *)v31[0] == 1 )
  {
    v13 = 1;
  }
  else
  {
    v13 = 0;
    wil::details::shared_object<wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(v31);
  }
  if ( pftDueTime )
    ReleaseSRWLockExclusive(*(PSRWLOCK *)&pftDueTime);
  if ( v13 )
  {
LABEL_14:
    if ( *v30 == 1 )
    {
      v14 = v30[22];
      LODWORD(v16) = v14;
      v15 = 2147942974LL;
      if ( v14 < 0 )
        v15 = (unsigned int)v14;
      wil::ActivityBase<StorageServerProvider,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        v30,
        v15,
        &v16);
      wil::ActivityBase<StorageServerProvider,1,70368744177666,4,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(&v18);
    }
  }
  wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(&v18);
  if ( _InterlockedExchangeAdd64(&qword_180114130, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
    SetThreadpoolTimer(pti, 0, 0, 0);
  SetThreadName(&word_1800D6108);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002b000  mov     [rsp-8+arg_0], rbx
0x18002b005  push    rbp
0x18002b006  push    rsi
0x18002b007  push    rdi
0x18002b008  push    r12
0x18002b00a  push    r13
0x18002b00c  push    r14
0x18002b00e  push    r15
0x18002b010  lea     rbp, [rsp-90h]
0x18002b018  sub     rsp, 190h
0x18002b01f  mov     rax, cs:__security_cookie
0x18002b026  xor     rax, rsp
0x18002b029  mov     [rbp+0C0h+var_40], rax
0x18002b030  mov     r14, r9
0x18002b033  mov     r12, r8
0x18002b036  mov     rsi, rdx
0x18002b039  lea     rcx, aRpcIdbstorOpen_0; "RPC IDBStor_openIndex"
0x18002b040  call    SetThreadName
0x18002b045  mov     ecx, cs:_tls_index
0x18002b04b  mov     rax, gs:58h
0x18002b054  mov     edx, 13C4h
0x18002b059  mov     rax, [rax+rcx*8]
0x18002b05d  mov     eax, [rdx+rax]
0x18002b060  cmp     cs:dword_180114128, eax
0x18002b066  jg      loc_18002B2C8
0x18002b06c  lock inc cs:qword_180114130
0x18002b074  mov     rax, cs:qword_180114140
0x18002b07b  mov     qword ptr [rsp+1C0h+pftDueTime.dwLowDateTime], rax
0x18002b080  xor     r9d, r9d; msWindowLength
0x18002b083  xor     r8d, r8d; msPeriod
0x18002b086  lea     rdx, [rsp+1C0h+pftDueTime]; pftDueTime
0x18002b08b  mov     rcx, cs:pti; pti
0x18002b092  call    cs:__imp_SetThreadpoolTimer
0x18002b098  nop
0x18002b099  xor     r13d, r13d
0x18002b09c  mov     [rsp+1C0h+var_188], r13d
0x18002b0a1  mov     [rsp+1C0h+var_184], r13b
0x18002b0a6  mov     [rsp+1C0h+var_148], r13b
0x18002b0ab  mov     [rsp+1C0h+var_160], r13d
0x18002b0b0  lea     rax, aIdbIdbobjectst; "IDB_IDBObjectStore_openIndex"
0x18002b0b7  mov     [rsp+1C0h+var_158], rax
0x18002b0bc  mov     [rsp+1C0h+var_150], r13
0x18002b0c1  mov     [rbp+0C0h+var_140], r13d
0x18002b0c5  xorps   xmm0, xmm0
0x18002b0c8  movdqa  [rbp+0C0h+var_A0], xmm0
0x18002b0cd  xor     edx, edx; Val
0x18002b0cf  mov     r8d, 98h; Size
0x18002b0d5  lea     rcx, [rbp+0C0h+var_138]; void *
0x18002b0d9  call    memset_0
0x18002b0de  mov     [rbp+0C0h+var_90], 1
0x18002b0e5  xor     eax, eax
0x18002b0e7  mov     [rbp+0C0h+var_88], rax
0x18002b0eb  lea     rax, [rsp+1C0h+var_188]
0x18002b0f0  mov     [rbp+0C0h+var_80], rax
0x18002b0f4  mov     [rbp+0C0h+var_78], r13
0x18002b0f8  mov     [rbp+0C0h+var_70], r13
0x18002b0fc  lea     rax, [rsp+1C0h+var_190]
0x18002b101  mov     [rbp+0C0h+var_68], rax
0x18002b105  mov     [rbp+0C0h+var_60], r13
0x18002b109  mov     [rbp+0C0h+var_58], r13d
0x18002b10d  lea     rax, [rsp+1C0h+var_160]
0x18002b112  mov     [rbp+0C0h+var_50], rax
0x18002b116  mov     [rbp+0C0h+var_48], r13b
0x18002b11a  lea     rax, ??_7IDB_IDBObjectStore_openIndex@IndexedDbTraceLogging@@6B@; const IndexedDbTraceLogging::IDB_IDBObjectStore_openIndex::`vftable'
0x18002b121  mov     [rsp+1C0h+var_190], rax
0x18002b126  mov     r8, r12; __int64
0x18002b129  mov     rdx, rsi; void *
0x18002b12c  lea     rcx, [rsp+1C0h+var_190]; this
0x18002b131  call    ?StartActivity@IDB_IDBObjectStore_openIndex@IndexedDbTraceLogging@@QEAAXPEAX_J@Z; IndexedDbTraceLogging::IDB_IDBObjectStore_openIndex::StartActivity(void *,__int64)
0x18002b136  nop
0x18002b137  test    r14, r14
0x18002b13a  jnz     loc_18002B332
0x18002b140  mov     ebx, 80070057h
0x18002b145  test    rsi, rsi
0x18002b148  jnz     short loc_18002B158
0x18002b14a  mov     edx, ebx
0x18002b14c  lea     rcx, [rsp+1C0h+var_190]
0x18002b151  call    ?Stop@?$ActivityBase@VStorageServerProvider@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002b156  jmp     short loc_18002B1C1
0x18002b158  test    r14, r14
0x18002b15b  jz      short loc_18002B14A
0x18002b15d  mov     [rsp+1C0h+var_1A0], r13
0x18002b162  lea     rcx, [rsp+1C0h+var_1A0]; struct ICallerIdentity **
0x18002b167  call    ?GetCallerId@CIndexedDBServerConnectionsMgr@@SAJPEAPEAUICallerIdentity@@@Z; CIndexedDBServerConnectionsMgr::GetCallerId(ICallerIdentity * *)
0x18002b16c  test    eax, eax
0x18002b16e  js      loc_18002B308
0x18002b174  mov     al, [rsi+38h]
0x18002b177  nop
0x18002b178  mov     r15, [rsp+1C0h+var_1A0]
0x18002b17d  test    al, al
0x18002b17f  jz      short loc_18002B19C
0x18002b181  mov     rcx, [rsi+8]
0x18002b185  mov     rax, [rcx]
0x18002b188  mov     rdx, r15
0x18002b18b  mov     rax, [rax+10h]
0x18002b18f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b194  test    eax, eax
0x18002b196  jz      loc_18002B250
0x18002b19c  mov     ebx, 80070005h
0x18002b1a1  mov     rax, [r15]
0x18002b1a4  mov     rcx, r15
0x18002b1a7  mov     rax, [rax+8]
0x18002b1ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b1b0  test    ebx, ebx
0x18002b1b2  js      short loc_18002B14A
0x18002b1b4  mov     rdx, [r14]; void *
0x18002b1b7  lea     rcx, [rsp+1C0h+var_190]; this
0x18002b1bc  call    ?Stop@IDB_IDBObjectStore_openIndex@IndexedDbTraceLogging@@QEAAXPEAX@Z; IndexedDbTraceLogging::IDB_IDBObjectStore_openIndex::Stop(void *)
0x18002b1c1  lea     rax, ??_7IDB_IDBObjectStore_openIndex@IndexedDbTraceLogging@@6B@; const IndexedDbTraceLogging::IDB_IDBObjectStore_openIndex::`vftable'
0x18002b1c8  mov     [rsp+1C0h+var_190], rax
0x18002b1cd  cmp     [rbp+0C0h+var_78], r13
0x18002b1d1  jnz     loc_18002B347
0x18002b1d7  mov     rcx, [rbp+0C0h+var_80]
0x18002b1db  cmp     dword ptr [rcx], 1
0x18002b1de  jz      loc_18002B377
0x18002b1e4  lea     rcx, [rsp+1C0h+var_190]
0x18002b1e9  call    ??1?$ActivityBase@VStorageServerProvider@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18002b1ee  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b1f2  lock xadd cs:qword_180114130, rax
0x18002b1fb  cmp     rax, 1
0x18002b1ff  jnz     short loc_18002B217
0x18002b201  xor     r9d, r9d; msWindowLength
0x18002b204  xor     r8d, r8d; msPeriod
0x18002b207  xor     edx, edx; pftDueTime
0x18002b209  mov     rcx, cs:pti; pti
0x18002b210  call    cs:__imp_SetThreadpoolTimer
0x18002b216  nop
0x18002b217  lea     rcx, word_1800D6108; lpWideCharStr
0x18002b21e  call    SetThreadName
0x18002b223  nop
0x18002b224  mov     eax, ebx
0x18002b226  mov     rcx, [rbp+0C0h+var_40]
0x18002b22d  xor     rcx, rsp; StackCookie
0x18002b230  call    __security_check_cookie
0x18002b235  mov     rbx, [rsp+1C0h+arg_0]
0x18002b23d  add     rsp, 190h
0x18002b244  pop     r15
0x18002b246  pop     r14
0x18002b248  pop     r13
0x18002b24a  pop     r12
0x18002b24c  pop     rdi
0x18002b24d  pop     rsi
0x18002b24e  pop     rbp
0x18002b24f  retn
0x18002b250  mov     rcx, [rsi+8]
0x18002b254  mov     rax, [r15]
0x18002b257  mov     rdi, [rax+28h]
0x18002b25b  mov     rax, [rcx]
0x18002b25e  mov     rax, [rax+28h]
0x18002b262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b267  mov     bl, al
0x18002b269  mov     rcx, r15
0x18002b26c  mov     rax, rdi
0x18002b26f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b274  cmp     bl, al
0x18002b276  jnz     loc_18002B19C
0x18002b27c  mov     qword ptr [rsp+1C0h+pftDueTime.dwLowDateTime], r13
0x18002b281  lea     r8, [rsp+1C0h+pftDueTime]; struct CIndexedDBServerIndex **
0x18002b286  mov     rdx, r12; __int64
0x18002b289  mov     rcx, rsi; this
0x18002b28c  call    ?OpenIndex@CIndexedDBServerObjectStore@@QEAAJ_JPEAPEAVCIndexedDBServerIndex@@@Z; CIndexedDBServerObjectStore::OpenIndex(__int64,CIndexedDBServerIndex * *)
0x18002b291  mov     ebx, eax
0x18002b293  mov     dword ptr [rsp+1C0h+var_1A0], r13d
0x18002b298  test    eax, eax
0x18002b29a  jns     loc_18002B33A
0x18002b2a0  lea     rdx, [rsp+1C0h+var_1A0]; unsigned int *
0x18002b2a5  mov     rcx, rsi; this
0x18002b2a8  call    ?GetClientContextFlags@CIndexedDBServerObjectStore@@QEAAJPEAK@Z; CIndexedDBServerObjectStore::GetClientContextFlags(ulong *)
0x18002b2ad  test    eax, eax
0x18002b2af  js      loc_18002B1A1
0x18002b2b5  xor     r8d, r8d; struct CWxString *
0x18002b2b8  mov     edx, ebx; int
0x18002b2ba  mov     ecx, dword ptr [rsp+1C0h+var_1A0]; unsigned int
0x18002b2be  call    ?HandleCorruptionIfDetected@CIndexedDBServerPhysicalDBManager@@SAXKJPEAVCWxString@@@Z; CIndexedDBServerPhysicalDBManager::HandleCorruptionIfDetected(ulong,long,CWxString *)
0x18002b2c3  jmp     loc_18002B1A1
0x18002b2c8  lea     rcx, dword_180114128
0x18002b2cf  call    _Init_thread_header
0x18002b2d4  cmp     cs:dword_180114128, 0FFFFFFFFh
0x18002b2db  jnz     loc_18002B06C
0x18002b2e1  mov     edx, 493E0h
0x18002b2e6  call    ??0HangDetectionWatchDog@@QEAA@V?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@@Z; HangDetectionWatchDog::HangDetectionWatchDog(std::chrono::duration<__int64,std::ratio<1,1000>>)
0x18002b2eb  lea     rcx, _HangDetectionWatchDog__s_DefaultInstance____2____dynamic_atexit_destructor_for__s_instance__; void (__cdecl *)()
0x18002b2f2  call    atexit
0x18002b2f7  lea     rcx, dword_180114128
0x18002b2fe  call    _Init_thread_footer
0x18002b303  jmp     loc_18002B06C
0x18002b308  mov     ebx, 80070005h
0x18002b30d  jmp     loc_18002B14A
0x18002b312  test    dil, dil
0x18002b315  jz      loc_18002B1E4
0x18002b31b  jmp     loc_18002B1D7
0x18002b320  mov     rcx, qword ptr [rsp+1C0h+pftDueTime.dwLowDateTime]; SRWLock
0x18002b325  test    rcx, rcx
0x18002b328  jz      short loc_18002B312
0x18002b32a  call    cs:__imp_ReleaseSRWLockExclusive
0x18002b330  jmp     short loc_18002B312
0x18002b332  mov     [r14], r13
0x18002b335  jmp     loc_18002B140
0x18002b33a  mov     rax, qword ptr [rsp+1C0h+pftDueTime.dwLowDateTime]
0x18002b33f  mov     [r14], rax
0x18002b342  jmp     loc_18002B1A1
0x18002b347  lea     rdx, [rsp+1C0h+pftDueTime]
0x18002b34c  lea     rcx, [rsp+1C0h+var_190]
0x18002b351  call    ?LockExclusive@?$ActivityBase@VStorageServerProvider@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002b356  mov     rax, [rbp+0C0h+var_78]
0x18002b35a  test    rax, rax
0x18002b35d  jz      short loc_18002B369
0x18002b35f  cmp     dword ptr [rax], 1
0x18002b362  jnz     short loc_18002B369
0x18002b364  mov     dil, 1
0x18002b367  jmp     short loc_18002B320
0x18002b369  mov     dil, r13b
0x18002b36c  lea     rcx, [rbp+0C0h+var_78]
0x18002b370  call    ?reset@?$shared_object@V?$ActivityData@VStorageServerProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VStorageServerProvider@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18002b375  jmp     short loc_18002B320
0x18002b377  mov     eax, [rcx+58h]
0x18002b37a  mov     dword ptr [rsp+1C0h+var_1A0], eax
0x18002b37e  mov     edx, 8007023Eh
0x18002b383  test    eax, eax
0x18002b385  cmovs   edx, eax
0x18002b388  lea     r8, [rsp+1C0h+var_1A0]
0x18002b38d  call    ?SetStopResult@?$ActivityData@VStorageServerProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VStorageServerProvider@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<StorageServerProvider,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18002b392  lea     rcx, [rsp+1C0h+var_190]
0x18002b397  call    ?ReportStopActivity@?$ActivityBase@VStorageServerProvider@@$00$0EAAAAAAAAAAC@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<StorageServerProvider,1,70368744177666,4,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x18002b39c  jmp     loc_18002B1E4
```
