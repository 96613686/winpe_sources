# s_IDBIndex_openCursor

- ea: `0x18002dbd0`
- end: `0x18002e030`
- name: `s_IDBIndex_openCursor`
- size: `1120`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: ``

## callees

- `0x180022a30`
- `0x1800233b0`
- `0x180024720`
- `0x180024870`
- `0x180024998`
- `0x1800273f0`
- `0x180029e74`
- `0x18002a060`
- `0x18002b480`
- `0x18002c9e0`
- `0x18002d290`
- `0x18002dbd0`
- `0x18002e038`
- `0x18004d894`
- `0x18004d938`
- `0x18004db98`
- `0x180056814`
- `0x180057168`
- `0x18005ff10`
- `0x180080fb0`
- `0x180081b40`
- `0x1800b0bcc`
- `0x1800b2088`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002de66`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002de66`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002deb3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002deb3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002ddca`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002ddca`

## string_xrefs

- `0x18002dc26`: `RPC IDBIdx_openCursor`
- `0x18002dc4f`: `IDB_IDBIndex_openCursor`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall s_IDBIndex_openCursor(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        char a5,
        void **a6,
        const struct __MIDL_RPCIndexedDB_0009 **a7)
{
  const struct __MIDL_RPCIndexedDB_0009 **v10; // rsi
  struct HangDetectionWatchDog *v11; // rdx
  int CurrentPositionValues; // ebx
  struct __MIDL_RPCIndexedDB_0009 *v13; // r12
  volatile signed __int64 *v14; // rcx
  char v16; // bl
  volatile signed __int32 *v17; // r15
  __int64 v18; // rax
  volatile signed __int32 *v19; // r14
  _QWORD *SmartRpc; // rbx
  struct __MIDL_RPCIndexedDB_0009 *v21; // rbx
  char v22; // [rsp+50h] [rbp-B0h] BYREF
  bool v23; // [rsp+51h] [rbp-AFh]
  unsigned int v24; // [rsp+54h] [rbp-ACh] BYREF
  struct __MIDL_RPCIndexedDB_0009 *v25; // [rsp+58h] [rbp-A8h] BYREF
  CIndexedDBServerCursor *v26; // [rsp+60h] [rbp-A0h] BYREF
  CIndexedDBServerCursor **v27; // [rsp+68h] [rbp-98h]
  unsigned int v28; // [rsp+70h] [rbp-90h]
  __int64 v29; // [rsp+78h] [rbp-88h] BYREF
  volatile signed __int64 *v30; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v31[8]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v32; // [rsp+90h] [rbp-70h]
  void **v33; // [rsp+A0h] [rbp-60h] BYREF
  int v34; // [rsp+A8h] [rbp-58h] BYREF
  char v35; // [rsp+ACh] [rbp-54h]
  int v36; // [rsp+D0h] [rbp-30h] BYREF
  const char *v37; // [rsp+D8h] [rbp-28h]
  __int64 v38; // [rsp+E0h] [rbp-20h]
  char v39; // [rsp+E8h] [rbp-18h]
  int v40; // [rsp+F0h] [rbp-10h]
  _BYTE v41[152]; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v42; // [rsp+190h] [rbp+90h]
  int v43; // [rsp+1A0h] [rbp+A0h]
  __int64 v44; // [rsp+1A8h] [rbp+A8h]
  int *v45; // [rsp+1B0h] [rbp+B0h]
  __int64 v46; // [rsp+1B8h] [rbp+B8h]
  __int64 v47; // [rsp+1C0h] [rbp+C0h]
  void ***v48; // [rsp+1C8h] [rbp+C8h]
  __int64 v49; // [rsp+1D0h] [rbp+D0h]
  int v50; // [rsp+1D8h] [rbp+D8h]
  int *v51; // [rsp+1E0h] [rbp+E0h]
  char v52; // [rsp+1E8h] [rbp+E8h]

  v28 = a4;
  v29 = a3;
  v10 = a7;
  v27 = a7;
  SetThreadName((WCHAR *)L"RPC IDBIdx_openCursor");
  HangDetectionWatchDog::Activity::Activity((HangDetectionWatchDog::Activity *)&v30, v11);
  v34 = 0;
  v35 = 0;
  v39 = 0;
  v36 = 0;
  v37 = "IDB_IDBIndex_openCursor";
  v38 = 0;
  v40 = 0;
  v42 = 0;
  memset_0(v41, 0, sizeof(v41));
  v43 = 1;
  v44 = 0;
  v45 = &v34;
  v46 = 0;
  v47 = 0;
  v48 = &v33;
  v49 = 0;
  v50 = 0;
  v51 = &v36;
  v52 = 0;
  v33 = &IndexedDbTraceLogging::IDB_IDBIndex_openCursor::`vftable';
  IndexedDbTraceLogging::IDB_IDBIndex_openCursor::StartActivity(&v33, a2, a3, a4, a5);
  if ( a6 )
    *a6 = 0;
  *a7 = 0;
  CurrentPositionValues = -2147024809;
  if ( !a2 || !a6 )
    goto LABEL_14;
  v25 = 0;
  if ( (int)CIndexedDBServerConnectionsMgr::GetCallerId(&v25) < 0 )
  {
    CurrentPositionValues = -2147024891;
    goto LABEL_14;
  }
  v13 = v25;
  if ( !*(_BYTE *)(a2 + 56)
    || (*(unsigned int (__fastcall **)(_QWORD, struct __MIDL_RPCIndexedDB_0009 *))(**(_QWORD **)(a2 + 8) + 16LL))(
         *(_QWORD *)(a2 + 8),
         v25)
    || (v16 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 8) + 40LL))(*(_QWORD *)(a2 + 8)),
        v16 != (*(unsigned __int8 (__fastcall **)(struct __MIDL_RPCIndexedDB_0009 *))(*(_QWORD *)v13 + 40LL))(v13)) )
  {
    CurrentPositionValues = -2147024891;
    goto LABEL_9;
  }
  v23 = a5 != 0;
  v17 = 0;
  *a7 = 0;
  v24 = 0;
  if ( a2 != -16 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 16));
    v24 = 1;
  }
  if ( *(_BYTE *)(a2 + 56) )
  {
    v18 = *(_QWORD *)(a2 + 104);
    v31[0] = 0;
    v32 = v18;
    _InterlockedIncrement((volatile signed __int32 *)(v18 + 88));
    CurrentPositionValues = CIndexedDBServerTransaction::CTransactionThreadScope::Attach((CIndexedDBServerTransaction::CTransactionThreadScope *)v31);
    if ( CurrentPositionValues < 0 )
      goto LABEL_20;
    v26 = 0;
    CurrentPositionValues = CIndexedDBServerCursor::CreateInstance(&v26);
    if ( CurrentPositionValues < 0 )
      goto LABEL_20;
    v25 = 0;
    v22 = 0;
    v19 = (volatile signed __int32 *)v26;
    CurrentPositionValues = CIndexedDBServerCursor::Init(
                              v26,
                              *(_QWORD *)(a2 + 8),
                              a2 + 64,
                              *(_QWORD *)(a2 + 104),
                              **(_QWORD **)(a2 + 112),
                              *(_QWORD *)(*(_QWORD *)(a2 + 112) + 8LL),
                              v29,
                              v28,
                              &v22);
    if ( CurrentPositionValues >= 0 )
    {
      if ( v22 )
      {
        SmartRpc = MakeSmartRpcPointer<IndexedDbCursorPositionValues,>(&v29);
        SmartRpcPointer<IndexedDbCursorPositionValues>::ResetHelper(&v25, *SmartRpc);
        *SmartRpc = 0;
        SmartRpcPointer<IndexedDbCursorPositionValues>::ResetHelper(&v29, 0);
        v21 = v25;
        v26 = v25;
        IndexedDbRpcHelpers::IndexedDbCursorPositionValuesTrait::Free(v25);
        CurrentPositionValues = CIndexedDBServerCursor::GetCurrentPositionValues(
                                  (CIndexedDBServerCursor *)v19,
                                  v23,
                                  v21);
        if ( CurrentPositionValues < 0 )
          goto LABEL_35;
      }
      else
      {
        v26 = 0;
      }
      CThreadSafeLinkedList<CIndexedDBServerCursor,CDoubleLink<CIndexedDBServerCursor,&public: static int CIndexedDBServerCursor::CIndexedDBServerCursor_GetCLink_lnkOffset(void)>>::AddToList(
        a2 + 128,
        v19);
      v17 = v19;
      _InterlockedIncrement(v19 + 16);
      v25 = 0;
      *v27 = v26;
    }
LABEL_35:
    CIndexedDBServerCursor::Release((CIndexedDBServerCursor *)v19);
    SmartRpcPointer<IndexedDbCursorPositionValues>::ResetHelper(&v25, 0);
LABEL_20:
    CIndexedDBServerTransaction::CTransactionThreadScope::~CTransactionThreadScope((CIndexedDBServerTransaction::CTransactionThreadScope *)v31);
    goto LABEL_21;
  }
  CurrentPositionValues = -2147024891;
LABEL_21:
  if ( v24 && a2 != -16 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(a2 + 16));
  v24 = 0;
  if ( CurrentPositionValues < 0 )
  {
    if ( (int)CIndexedDBServerIndex::GetClientContextFlags((CIndexedDBServerIndex *)a2, &v24) >= 0 )
      CIndexedDBServerPhysicalDBManager::HandleCorruptionIfDetected(v24, CurrentPositionValues, 0);
  }
  else
  {
    *a6 = (void *)v17;
  }
  v10 = v27;
LABEL_9:
  (*(void (__fastcall **)(struct __MIDL_RPCIndexedDB_0009 *))(*(_QWORD *)v13 + 8LL))(v13);
  if ( CurrentPositionValues >= 0 )
  {
    IndexedDbTraceLogging::IDB_IDBIndex_openCursor::Stop(
      (IndexedDbTraceLogging::IDB_IDBIndex_openCursor *)&v33,
      *a6,
      *v10);
    goto LABEL_11;
  }
LABEL_14:
  wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    &v33,
    (unsigned int)CurrentPositionValues);
LABEL_11:
  v33 = &IndexedDbTraceLogging::IDB_IDBIndex_openCursor::`vftable';
  wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v33);
  wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(&v33);
  v14 = v30;
  if ( _InterlockedExchangeAdd64(v30, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
    SetThreadpoolTimer(*((PTP_TIMER *)v14 + 1), 0, 0, 0);
  SetThreadName((WCHAR *)&word_1800D6108);
  return (unsigned int)CurrentPositionValues;
}

```

## disassembly

```asm
0x18002dbd0  mov     [rsp-8+arg_0], rbx
0x18002dbd5  push    rbp
0x18002dbd6  push    rsi
0x18002dbd7  push    rdi
0x18002dbd8  push    r12
0x18002dbda  push    r13
0x18002dbdc  push    r14
0x18002dbde  push    r15
0x18002dbe0  lea     rbp, [rsp-100h]
0x18002dbe8  sub     rsp, 200h
0x18002dbef  mov     rax, cs:__security_cookie
0x18002dbf6  xor     rax, rsp
0x18002dbf9  mov     [rbp+130h+var_40], rax
0x18002dc00  mov     r15d, r9d
0x18002dc03  mov     [rsp+230h+var_1C0], r9d
0x18002dc08  mov     rbx, r8
0x18002dc0b  mov     [rsp+230h+var_1B8], rbx
0x18002dc10  mov     rdi, rdx
0x18002dc13  mov     r13, [rbp+130h+arg_28]
0x18002dc1a  mov     rsi, [rbp+130h+arg_30]
0x18002dc21  mov     [rsp+230h+var_1C8], rsi
0x18002dc26  lea     rcx, aRpcIdbidxOpenc; "RPC IDBIdx_openCursor"
0x18002dc2d  call    SetThreadName
0x18002dc32  lea     rcx, [rbp+130h+var_1B0]; this
0x18002dc36  call    ??0Activity@HangDetectionWatchDog@@QEAA@PEAV1@@Z; HangDetectionWatchDog::Activity::Activity(HangDetectionWatchDog *)
0x18002dc3b  nop
0x18002dc3c  xor     r12d, r12d
0x18002dc3f  mov     [rbp+130h+var_188], r12d
0x18002dc43  mov     [rbp+130h+var_184], r12b
0x18002dc47  mov     [rbp+130h+var_148], r12b
0x18002dc4b  mov     [rbp+130h+var_160], r12d
0x18002dc4f  lea     rax, aIdbIdbindexOpe; "IDB_IDBIndex_openCursor"
0x18002dc56  mov     [rbp+130h+var_158], rax
0x18002dc5a  mov     [rbp+130h+var_150], r12
0x18002dc5e  mov     [rbp+130h+var_140], r12d
0x18002dc62  xorps   xmm0, xmm0
0x18002dc65  movdqa  [rbp+130h+var_A0], xmm0
0x18002dc6d  xor     edx, edx; Val
0x18002dc6f  mov     r8d, 98h; Size
0x18002dc75  lea     rcx, [rbp+130h+var_138]; void *
0x18002dc79  call    memset_0
0x18002dc7e  mov     [rbp+130h+var_90], 1
0x18002dc88  xor     eax, eax
0x18002dc8a  mov     [rbp+130h+var_88], rax
0x18002dc91  lea     rax, [rbp+130h+var_188]
0x18002dc95  mov     [rbp+130h+var_80], rax
0x18002dc9c  mov     [rbp+130h+var_78], r12
0x18002dca3  mov     [rbp+130h+var_70], r12
0x18002dcaa  lea     rax, [rbp+130h+var_190]
0x18002dcae  mov     [rbp+130h+var_68], rax
0x18002dcb5  mov     [rbp+130h+var_60], r12
0x18002dcbc  mov     [rbp+130h+var_58], r12d
0x18002dcc3  lea     rax, [rbp+130h+var_160]
0x18002dcc7  mov     [rbp+130h+var_50], rax
0x18002dcce  mov     [rbp+130h+var_48], r12b
0x18002dcd5  lea     rax, ??_7IDB_IDBIndex_openCursor@IndexedDbTraceLogging@@6B@; const IndexedDbTraceLogging::IDB_IDBIndex_openCursor::`vftable'
0x18002dcdc  mov     [rbp+130h+var_190], rax
0x18002dce0  mov     r14b, [rbp+130h+arg_20]
0x18002dce7  mov     byte ptr [rsp+230h+var_210], r14b
0x18002dcec  mov     r9d, r15d
0x18002dcef  mov     r8, rbx
0x18002dcf2  mov     rdx, rdi
0x18002dcf5  lea     rcx, [rbp+130h+var_190]
0x18002dcf9  call    ?StartActivity@IDB_IDBIndex_openCursor@IndexedDbTraceLogging@@QEAAXPEAXPEBU__MIDL_RPCIndexedDB_0003@@W4INDEXED_DB_CURSOR_DIRECTION@@E@Z; IndexedDbTraceLogging::IDB_IDBIndex_openCursor::StartActivity(void *,__MIDL_RPCIndexedDB_0003 const *,INDEXED_DB_CURSOR_DIRECTION,uchar)
0x18002dcfe  nop
0x18002dcff  test    r13, r13
0x18002dd02  jnz     loc_18002DEDB
0x18002dd08  mov     [rsi], r12
0x18002dd0b  mov     ebx, 80070057h
0x18002dd10  test    rdi, rdi
0x18002dd13  jz      loc_18002DE0A
0x18002dd19  test    r13, r13
0x18002dd1c  jz      loc_18002DE0A
0x18002dd22  mov     [rsp+230h+var_1D8], r12
0x18002dd27  lea     rcx, [rsp+230h+var_1D8]; struct ICallerIdentity **
0x18002dd2c  call    ?GetCallerId@CIndexedDBServerConnectionsMgr@@SAJPEAPEAUICallerIdentity@@@Z; CIndexedDBServerConnectionsMgr::GetCallerId(ICallerIdentity * *)
0x18002dd31  test    eax, eax
0x18002dd33  js      loc_18002E026
0x18002dd39  mov     al, [rdi+38h]
0x18002dd3c  nop
0x18002dd3d  mov     r12, [rsp+230h+var_1D8]
0x18002dd42  test    al, al
0x18002dd44  jz      short loc_18002DD61
0x18002dd46  mov     rcx, [rdi+8]
0x18002dd4a  mov     rax, [rcx]
0x18002dd4d  mov     rdx, r12
0x18002dd50  mov     rax, [rax+10h]
0x18002dd54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd59  test    eax, eax
0x18002dd5b  jz      loc_18002DE1A
0x18002dd61  mov     ebx, 80070005h
0x18002dd66  mov     rax, [r12]
0x18002dd6a  mov     rcx, r12
0x18002dd6d  mov     rax, [rax+8]
0x18002dd71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd76  test    ebx, ebx
0x18002dd78  js      loc_18002DE0A
0x18002dd7e  mov     r8, [rsi]; struct __MIDL_RPCIndexedDB_0009 *
0x18002dd81  mov     rdx, [r13+0]; void *
0x18002dd85  lea     rcx, [rbp+130h+var_190]; this
0x18002dd89  call    ?Stop@IDB_IDBIndex_openCursor@IndexedDbTraceLogging@@QEAAXPEAXPEBU__MIDL_RPCIndexedDB_0009@@@Z; IndexedDbTraceLogging::IDB_IDBIndex_openCursor::Stop(void *,__MIDL_RPCIndexedDB_0009 const *)
0x18002dd8e  lea     rax, ??_7IDB_IDBIndex_openCursor@IndexedDbTraceLogging@@6B@; const IndexedDbTraceLogging::IDB_IDBIndex_openCursor::`vftable'
0x18002dd95  mov     [rbp+130h+var_190], rax
0x18002dd99  lea     rcx, [rbp+130h+var_190]
0x18002dd9d  call    ?Destroy@?$ActivityBase@VStorageServerProvider@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18002dda2  lea     rcx, [rbp+130h+var_190]
0x18002dda6  call    ??1?$ActivityBase@VStorageServerProvider@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18002ddab  mov     rcx, [rbp+130h+var_1B0]
0x18002ddaf  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002ddb3  lock xadd [rcx], rax
0x18002ddb8  cmp     rax, 1
0x18002ddbc  jnz     short loc_18002DDD1
0x18002ddbe  xor     r9d, r9d; msWindowLength
0x18002ddc1  xor     r8d, r8d; msPeriod
0x18002ddc4  xor     edx, edx; pftDueTime
0x18002ddc6  mov     rcx, [rcx+8]; pti
0x18002ddca  call    cs:__imp_SetThreadpoolTimer
0x18002ddd0  nop
0x18002ddd1  lea     rcx, word_1800D6108; lpWideCharStr
0x18002ddd8  call    SetThreadName
0x18002dddd  nop
0x18002ddde  mov     eax, ebx
0x18002dde0  mov     rcx, [rbp+130h+var_40]
0x18002dde7  xor     rcx, rsp; StackCookie
0x18002ddea  call    __security_check_cookie
0x18002ddef  mov     rbx, [rsp+230h+arg_0]
0x18002ddf7  add     rsp, 200h
0x18002ddfe  pop     r15
0x18002de00  pop     r14
0x18002de02  pop     r13
0x18002de04  pop     r12
0x18002de06  pop     rdi
0x18002de07  pop     rsi
0x18002de08  pop     rbp
0x18002de09  retn
0x18002de0a  mov     edx, ebx
0x18002de0c  lea     rcx, [rbp+130h+var_190]
0x18002de10  call    ?Stop@?$ActivityBase@VStorageServerProvider@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002de15  jmp     loc_18002DD8E
0x18002de1a  mov     rcx, [rdi+8]
0x18002de1e  mov     rax, [rcx]
0x18002de21  mov     rax, [rax+28h]
0x18002de25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de2a  mov     bl, al
0x18002de2c  mov     rcx, [r12]
0x18002de30  mov     rax, [rcx+28h]
0x18002de34  mov     rcx, r12
0x18002de37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de3c  cmp     bl, al
0x18002de3e  jnz     loc_18002DD61
0x18002de44  test    r14b, r14b
0x18002de47  setnz   [rsp+230h+var_1DF]
0x18002de4c  xor     r14d, r14d
0x18002de4f  mov     r15d, r14d
0x18002de52  mov     [rsi], r14
0x18002de55  lea     rsi, [rdi+10h]
0x18002de59  mov     [rsp+230h+var_1DC], r14d
0x18002de5e  test    rsi, rsi
0x18002de61  jz      short loc_18002DE74
0x18002de63  mov     rcx, rsi; lpCriticalSection
0x18002de66  call    cs:__imp_EnterCriticalSection
0x18002de6c  mov     [rsp+230h+var_1DC], 1
0x18002de74  mov     al, [rdi+38h]
0x18002de77  nop
0x18002de78  test    al, al
0x18002de7a  jz      short loc_18002DED4
0x18002de7c  mov     rax, [rdi+68h]
0x18002de80  mov     [rbp+130h+var_1A8], r14b
0x18002de84  mov     [rbp+130h+var_1A0], rax
0x18002de88  lock inc dword ptr [rax+58h]
0x18002de8c  lea     rcx, [rbp+130h+var_1A8]; this
0x18002de90  call    ?Attach@CTransactionThreadScope@CIndexedDBServerTransaction@@QEAAJXZ; CIndexedDBServerTransaction::CTransactionThreadScope::Attach(void)
0x18002de95  mov     ebx, eax
0x18002de97  test    eax, eax
0x18002de99  jns     short loc_18002DEE4
0x18002de9b  lea     rcx, [rbp+130h+var_1A8]; this
0x18002de9f  call    ??1CTransactionThreadScope@CIndexedDBServerTransaction@@QEAA@XZ; CIndexedDBServerTransaction::CTransactionThreadScope::~CTransactionThreadScope(void)
0x18002dea4  cmp     [rsp+230h+var_1DC], r14d
0x18002dea9  jz      short loc_18002DEB9
0x18002deab  test    rsi, rsi
0x18002deae  jz      short loc_18002DEB9
0x18002deb0  mov     rcx, rsi; lpCriticalSection
0x18002deb3  call    cs:__imp_LeaveCriticalSection
0x18002deb9  mov     [rsp+230h+var_1DC], r14d
0x18002debe  test    ebx, ebx
0x18002dec0  js      loc_18002DFFE
0x18002dec6  mov     [r13+0], r15
0x18002deca  mov     rsi, [rsp+230h+var_1C8]
0x18002decf  jmp     loc_18002DD66
0x18002ded4  mov     ebx, 80070005h
0x18002ded9  jmp     short loc_18002DEA4
0x18002dedb  mov     [r13+0], r12
0x18002dedf  jmp     loc_18002DD08
0x18002dee4  mov     [rsp+230h+var_1D0], r14
0x18002dee9  lea     rcx, [rsp+230h+var_1D0]; struct CIndexedDBServerCursor **
0x18002deee  call    ?CreateInstance@CIndexedDBServerCursor@@SAJPEAPEAV1@@Z; CIndexedDBServerCursor::CreateInstance(CIndexedDBServerCursor * *)
0x18002def3  mov     ebx, eax
0x18002def5  test    eax, eax
0x18002def7  js      short loc_18002DE9B
0x18002def9  mov     [rsp+230h+var_1D8], r14
0x18002defe  mov     [rsp+230h+var_1E0], r14b
0x18002df03  mov     rcx, [rdi+70h]
0x18002df07  lea     r8, [rdi+40h]
0x18002df0b  lea     rax, [rsp+230h+var_1E0]
0x18002df10  mov     [rsp+230h+var_1F0], rax
0x18002df15  mov     eax, [rsp+230h+var_1C0]
0x18002df19  mov     [rsp+230h+var_1F8], eax
0x18002df1d  mov     rax, [rsp+230h+var_1B8]
0x18002df22  mov     [rsp+230h+var_200], rax
0x18002df27  mov     rax, [rcx+8]
0x18002df2b  mov     [rsp+230h+var_208], rax
0x18002df30  mov     rax, [rcx]
0x18002df33  mov     [rsp+230h+var_210], rax
0x18002df38  mov     r9, [rdi+68h]
0x18002df3c  mov     rdx, [rdi+8]
0x18002df40  mov     r14, [rsp+230h+var_1D0]
0x18002df45  mov     rcx, r14
0x18002df48  call    ?Init@CIndexedDBServerCursor@@QEAAJPEAUICallerIdentity@@PEAUIIndexedDBServerCursorOwner@@PEAVCIndexedDBServerTransaction@@PEAVCEseLayerObjectStore@@PEAVCEseLayerIndexSchema@@PEBU__MIDL_RPCIndexedDB_0003@@W4INDEXED_DB_CURSOR_DIRECTION@@PEA_N@Z; CIndexedDBServerCursor::Init(ICallerIdentity *,IIndexedDBServerCursorOwner *,CIndexedDBServerTransaction *,CEseLayerObjectStore *,CEseLayerIndexSchema *,__MIDL_RPCIndexedDB_0003 const *,INDEXED_DB_CURSOR_DIRECTION,bool *)
0x18002df4d  mov     ebx, eax
0x18002df4f  test    eax, eax
0x18002df51  js      loc_18002DFE2
0x18002df57  cmp     [rsp+230h+var_1E0], r15b
0x18002df5c  jz      short loc_18002DFB0
0x18002df5e  lea     rcx, [rsp+230h+var_1B8]
0x18002df63  call    ??$MakeSmartRpcPointer@VIndexedDbCursorPositionValues@@$$V@@YA?AV?$SmartRpcPointer@VIndexedDbCursorPositionValues@@@@XZ; MakeSmartRpcPointer<IndexedDbCursorPositionValues,>(void)
0x18002df68  mov     rbx, rax
0x18002df6b  mov     rdx, [rax]
0x18002df6e  lea     rcx, [rsp+230h+var_1D8]
0x18002df73  call    ?ResetHelper@?$SmartRpcPointer@VIndexedDbCursorPositionValues@@@@AEAAXPEAU__MIDL_RPCIndexedDB_0009@@@Z; SmartRpcPointer<IndexedDbCursorPositionValues>::ResetHelper(__MIDL_RPCIndexedDB_0009 *)
0x18002df78  mov     [rbx], r15
0x18002df7b  xor     edx, edx
0x18002df7d  lea     rcx, [rsp+230h+var_1B8]
0x18002df82  call    ?ResetHelper@?$SmartRpcPointer@VIndexedDbCursorPositionValues@@@@AEAAXPEAU__MIDL_RPCIndexedDB_0009@@@Z; SmartRpcPointer<IndexedDbCursorPositionValues>::ResetHelper(__MIDL_RPCIndexedDB_0009 *)
0x18002df87  mov     rbx, [rsp+230h+var_1D8]
0x18002df8c  mov     [rsp+230h+var_1D0], rbx
0x18002df91  mov     rcx, rbx; struct __MIDL_RPCIndexedDB_0009 *
0x18002df94  call    ?Free@IndexedDbCursorPositionValuesTrait@IndexedDbRpcHelpers@@SAXAEAU__MIDL_RPCIndexedDB_0009@@@Z; IndexedDbRpcHelpers::IndexedDbCursorPositionValuesTrait::Free(__MIDL_RPCIndexedDB_0009 &)
0x18002df99  mov     r8, rbx; struct __MIDL_RPCIndexedDB_0009 *
0x18002df9c  mov     dl, [rsp+230h+var_1DF]; bool
0x18002dfa0  mov     rcx, r14; this
0x18002dfa3  call    ?GetCurrentPositionValues@CIndexedDBServerCursor@@QEAAJ_NPEAU__MIDL_RPCIndexedDB_0009@@@Z; CIndexedDBServerCursor::GetCurrentPositionValues(bool,__MIDL_RPCIndexedDB_0009 *)
0x18002dfa8  mov     ebx, eax
0x18002dfaa  test    eax, eax
0x18002dfac  jns     short loc_18002DFB5
0x18002dfae  jmp     short loc_18002DFE2
0x18002dfb0  mov     [rsp+230h+var_1D0], r15
0x18002dfb5  lea     rcx, [rdi+80h]
0x18002dfbc  mov     rdx, r14
0x18002dfbf  call    ?AddToList@?$CThreadSafeLinkedList@VCIndexedDBServerCursor@@V?$CDoubleLink@VCIndexedDBServerCursor@@$1?CIndexedDBServerCursor_GetCLink_lnkOffset@1@SAHXZ@@@@QEAAXPEAVCIndexedDBServerCursor@@@Z; CThreadSafeLinkedList<CIndexedDBServerCursor,CDoubleLink<CIndexedDBServerCursor,&CIndexedDBServerCursor::CIndexedDBServerCursor_GetCLink_lnkOffset(void)>>::AddToList(CIndexedDBServerCursor *)
0x18002dfc4  mov     r15, r14
0x18002dfc7  lock inc dword ptr [r14+40h]
0x18002dfcc  mov     [rsp+230h+var_1D8], 0
0x18002dfd5  mov     rax, [rsp+230h+var_1D0]
0x18002dfda  mov     rcx, [rsp+230h+var_1C8]
0x18002dfdf  mov     [rcx], rax
0x18002dfe2  mov     rcx, r14; this
0x18002dfe5  call    ?Release@CIndexedDBServerCursor@@QEAAKXZ; CIndexedDBServerCursor::Release(void)
0x18002dfea  xor     edx, edx
0x18002dfec  lea     rcx, [rsp+230h+var_1D8]
0x18002dff1  call    ?ResetHelper@?$SmartRpcPointer@VIndexedDbCursorPositionValues@@@@AEAAXPEAU__MIDL_RPCIndexedDB_0009@@@Z; SmartRpcPointer<IndexedDbCursorPositionValues>::ResetHelper(__MIDL_RPCIndexedDB_0009 *)
0x18002dff6  xor     r14d, r14d
0x18002dff9  jmp     loc_18002DE9B
0x18002dffe  lea     rdx, [rsp+230h+var_1DC]; unsigned int *
0x18002e003  mov     rcx, rdi; this
0x18002e006  call    ?GetClientContextFlags@CIndexedDBServerIndex@@QEAAJPEAK@Z; CIndexedDBServerIndex::GetClientContextFlags(ulong *)
0x18002e00b  test    eax, eax
0x18002e00d  js      loc_18002DECA
0x18002e013  xor     r8d, r8d; struct CWxString *
0x18002e016  mov     edx, ebx; int
0x18002e018  mov     ecx, [rsp+230h+var_1DC]; unsigned int
0x18002e01c  call    ?HandleCorruptionIfDetected@CIndexedDBServerPhysicalDBManager@@SAXKJPEAVCWxString@@@Z; CIndexedDBServerPhysicalDBManager::HandleCorruptionIfDetected(ulong,long,CWxString *)
0x18002e021  jmp     loc_18002DECA
0x18002e026  mov     ebx, 80070005h
0x18002e02b  jmp     loc_18002DE0A
```
