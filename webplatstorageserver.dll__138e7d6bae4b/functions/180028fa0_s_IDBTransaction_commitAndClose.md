# s_IDBTransaction_commitAndClose

- ea: `0x180028fa0`
- end: `0x18002940e`
- name: `s_IDBTransaction_commitAndClose`
- size: `1134`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `broker_com_uri`

## callees

- `0x180020ea0`
- `0x1800247ac`
- `0x1800273f0`
- `0x180028fa0`
- `0x180029414`
- `0x180029e74`
- `0x18002a060`
- `0x18002b480`
- `0x180030c04`
- `0x18004ca40`
- `0x180051bb4`
- `0x180052a4c`
- `0x180055cac`
- `0x18005e07c`
- `0x180060450`
- `0x180070e88`
- `0x180071590`
- `0x180080fb0`
- `0x18008149c`
- `0x180083fcc`
- `0x180084034`
- `0x1800b0bcc`
- `0x1800b1370`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029328`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029328`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002902f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002927a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002902f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002927a`

## string_xrefs

- `0x180028fd6`: `RPC IDBTran_commitAndClose`
- `0x180029048`: `IDB_IDBTransaction_commitAndClose`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall s_IDBTransaction_commitAndClose(__int64 a1, void **a2, struct __MIDL_RPCIndexedDB_0008 **a3)
{
  int v5; // ebx
  CIndexedDBServerTransaction *v6; // r15
  struct _FILETIME v7; // r14
  __int64 v8; // rsi
  unsigned __int8 (__fastcall *v9)(__int64); // rdi
  char v10; // bl
  __int64 v12; // rcx
  struct __MIDL_RPCIndexedDB_0008 **SmartRpc; // rax
  struct __MIDL_RPCIndexedDB_0008 *v14; // rcx
  struct __MIDL_RPCIndexedDB_0008 *v15; // rdi
  char v16; // di
  signed int v17; // eax
  __int64 v18; // rdx
  bool v19; // [rsp+20h] [rbp-E0h] BYREF
  struct _FILETIME pftDueTime; // [rsp+28h] [rbp-D8h] BYREF
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD v22[3]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+68h] [rbp-98h]
  void **v24; // [rsp+70h] [rbp-90h] BYREF
  int v25; // [rsp+78h] [rbp-88h] BYREF
  char v26; // [rsp+7Ch] [rbp-84h]
  int v27; // [rsp+A0h] [rbp-60h] BYREF
  const char *v28; // [rsp+A8h] [rbp-58h]
  __int64 v29; // [rsp+B0h] [rbp-50h]
  char v30; // [rsp+B8h] [rbp-48h]
  int v31; // [rsp+C0h] [rbp-40h]
  __int128 v32; // [rsp+C8h] [rbp-38h]
  __int128 v33; // [rsp+D8h] [rbp-28h]
  __int128 v34; // [rsp+E8h] [rbp-18h]
  __int128 v35; // [rsp+F8h] [rbp-8h]
  __int128 v36; // [rsp+108h] [rbp+8h]
  __int128 v37; // [rsp+118h] [rbp+18h]
  __int128 v38; // [rsp+128h] [rbp+28h]
  __int128 v39; // [rsp+138h] [rbp+38h]
  __int128 v40; // [rsp+148h] [rbp+48h]
  __int64 v41; // [rsp+158h] [rbp+58h]
  __int128 v42; // [rsp+160h] [rbp+60h]
  int v43; // [rsp+170h] [rbp+70h]
  __int64 v44; // [rsp+178h] [rbp+78h]
  int *v45; // [rsp+180h] [rbp+80h]
  _QWORD v46[4]; // [rsp+188h] [rbp+88h] BYREF
  int v47; // [rsp+1A8h] [rbp+A8h]
  int *v48; // [rsp+1B0h] [rbp+B0h]
  char v49; // [rsp+1B8h] [rbp+B8h]

  SetThreadName(L"RPC IDBTran_commitAndClose");
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
  v25 = 0;
  v26 = 0;
  v30 = 0;
  v27 = 0;
  v28 = "IDB_IDBTransaction_commitAndClose";
  v29 = 0;
  v31 = 0;
  v42 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v43 = 1;
  v44 = 0;
  v45 = &v25;
  v46[0] = 0;
  v46[1] = 0;
  v46[2] = &v24;
  v46[3] = 0;
  v47 = 0;
  v48 = &v27;
  v49 = 0;
  v24 = &IndexedDbTraceLogging::IDB_IDBTransaction_commitAndClose::`vftable';
  IndexedDbTraceLogging::IDB_IDBTransaction_commitAndClose::StartActivity(
    (IndexedDbTraceLogging::IDB_IDBTransaction_commitAndClose *)&v24,
    *a2);
  *a3 = 0;
  v5 = -2147024809;
  v6 = (CIndexedDBServerTransaction *)*a2;
  if ( !*a2 )
    goto LABEL_21;
  pftDueTime = 0;
  if ( (int)CIndexedDBServerConnectionsMgr::GetCallerId((struct ICallerIdentity **)&pftDueTime) < 0 )
  {
    v5 = -2147024891;
LABEL_21:
    wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v24, (unsigned int)v5);
    goto LABEL_15;
  }
  v7 = pftDueTime;
  if ( *((_BYTE *)v6 + 56)
    && !(*(unsigned int (__fastcall **)(_QWORD, struct _FILETIME))(**((_QWORD **)v6 + 1) + 16LL))(
          *((_QWORD *)v6 + 1),
          pftDueTime)
    && (v8 = *((_QWORD *)v6 + 1),
        v9 = *(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v8 + 40LL),
        v10 = (*(__int64 (__fastcall **)(struct _FILETIME))(**(_QWORD **)&v7 + 40LL))(v7),
        v9(v8) == v10) )
  {
    v19 = 0;
    memset(v22, 0, sizeof(v22));
    v23 = 0;
    IndexedDbRpcHelpers::IndexedDbDatabaseValuesTrait::Free((struct __MIDL_RPCIndexedDB_0008 *)v22);
    v5 = CIndexedDBServerTransaction::Commit(v6, &v19, (struct __MIDL_RPCIndexedDB_0008 *)v22);
    if ( v19 )
    {
      SmartRpc = (struct __MIDL_RPCIndexedDB_0008 **)MakeSmartRpcPointer<IndexedDbDatabaseValues,IndexedDbDatabaseValues>(
                                                       &pftDueTime,
                                                       v22);
      v14 = *SmartRpc;
      *SmartRpc = 0;
      *a3 = v14;
      v15 = (struct __MIDL_RPCIndexedDB_0008 *)pftDueTime;
      pftDueTime = 0;
      if ( v15 )
      {
        IndexedDbRpcHelpers::IndexedDbDatabaseValuesTrait::Free(v15);
        SRWLock = (PSRWLOCK)v15;
        WxFreeHeapEx((void **)&SRWLock);
      }
    }
    pftDueTime.dwLowDateTime = 0;
    if ( v5 < 0 && (int)CIndexedDBServerTransaction::GetClientContextFlags(v6, (unsigned int *)&pftDueTime) >= 0 )
      CIndexedDBServerPhysicalDBManager::HandleCorruptionIfDetected(pftDueTime.dwLowDateTime, v5, 0);
    if ( v5 != -2140082176 )
    {
      CIndexedDBServerTransaction::Release(v6);
      *a2 = 0;
    }
    IndexedDbRpcHelpers::IndexedDbDatabaseValuesTrait::Free((struct __MIDL_RPCIndexedDB_0008 *)v22);
  }
  else
  {
    v5 = -2147024891;
  }
  (*(void (__fastcall **)(struct _FILETIME))(**(_QWORD **)&v7 + 8LL))(v7);
  if ( v5 < 0 )
    goto LABEL_21;
  IndexedDbTraceLogging::IDB_IDBTransaction_commitAndClose::Stop(
    (IndexedDbTraceLogging::IDB_IDBTransaction_commitAndClose *)&v24,
    *a3);
LABEL_15:
  v24 = &IndexedDbTraceLogging::IDB_IDBTransaction_commitAndClose::`vftable';
  if ( !v46[0] )
    goto LABEL_16;
  wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(&v24, &SRWLock);
  if ( v46[0] && *(_DWORD *)v46[0] == 1 )
  {
    v16 = 1;
  }
  else
  {
    v16 = 0;
    wil::details::shared_object<wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(v46);
  }
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v16 )
  {
LABEL_16:
    if ( *v45 == 1 )
    {
      v17 = v45[22];
      pftDueTime.dwLowDateTime = v17;
      v18 = 2147942974LL;
      if ( v17 < 0 )
        v18 = (unsigned int)v17;
      wil::ActivityBase<StorageServerProvider,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        v45,
        v18,
        &pftDueTime);
      wil::ActivityBase<StorageServerProvider,1,70368744177666,4,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(&v24);
    }
  }
  wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(&v24);
  if ( _InterlockedExchangeAdd64(&qword_180114130, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
    SetThreadpoolTimer(pti, 0, 0, 0);
  SetThreadName(&word_1800D6108);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180028fa0  mov     [rsp-8+arg_0], rbx
0x180028fa5  push    rbp
0x180028fa6  push    rsi
0x180028fa7  push    rdi
0x180028fa8  push    r12
0x180028faa  push    r13
0x180028fac  push    r14
0x180028fae  push    r15
0x180028fb0  lea     rbp, [rsp-0D0h]
0x180028fb8  sub     rsp, 1D0h
0x180028fbf  mov     rax, cs:__security_cookie
0x180028fc6  xor     rax, rsp
0x180028fc9  mov     [rbp+100h+var_40], rax
0x180028fd0  mov     r12, r8
0x180028fd3  mov     r13, rdx
0x180028fd6  lea     rcx, aRpcIdbtranComm; "RPC IDBTran_commitAndClose"
0x180028fdd  call    SetThreadName
0x180028fe2  mov     ecx, cs:_tls_index
0x180028fe8  mov     rax, gs:58h
0x180028ff1  mov     edx, 13C4h
0x180028ff6  mov     rax, [rax+rcx*8]
0x180028ffa  mov     ecx, [rdx+rax]
0x180028ffd  cmp     cs:dword_180114128, ecx
0x180029003  jg      loc_1800292D0
0x180029009  lock inc cs:qword_180114130
0x180029011  mov     rax, cs:qword_180114140
0x180029018  mov     qword ptr [rsp+200h+pftDueTime.dwLowDateTime], rax
0x18002901d  xor     r9d, r9d; msWindowLength
0x180029020  xor     r8d, r8d; msPeriod
0x180029023  lea     rdx, [rsp+200h+pftDueTime]; pftDueTime
0x180029028  mov     rcx, cs:pti; pti
0x18002902f  call    cs:__imp_SetThreadpoolTimer
0x180029035  nop
0x180029036  xor     edi, edi
0x180029038  mov     [rsp+200h+var_188], edi
0x18002903c  mov     [rsp+200h+var_184], dil
0x180029041  mov     [rbp+100h+var_148], dil
0x180029045  mov     [rbp+100h+var_160], edi
0x180029048  lea     rax, aIdbIdbtransact; "IDB_IDBTransaction_commitAndClose"
0x18002904f  mov     [rbp+100h+var_158], rax
0x180029053  mov     [rbp+100h+var_150], rdi
0x180029057  mov     [rbp+100h+var_140], edi
0x18002905a  xorps   xmm0, xmm0
0x18002905d  movdqa  [rbp+100h+var_A0], xmm0
0x180029062  xorps   xmm1, xmm1
0x180029065  xor     eax, eax
0x180029067  movups  [rbp+100h+var_138], xmm1
0x18002906b  movups  [rbp+100h+var_128], xmm1
0x18002906f  movups  [rbp+100h+var_118], xmm1
0x180029073  movups  [rbp+100h+var_108], xmm1
0x180029077  movups  [rbp+100h+var_F8], xmm1
0x18002907b  movups  [rbp+100h+var_E8], xmm1
0x18002907f  movups  [rbp+100h+var_D8], xmm1
0x180029083  movups  [rbp+100h+var_C8], xmm1
0x180029087  movups  [rbp+100h+var_B8], xmm1
0x18002908b  mov     [rbp+100h+var_A8], rax
0x18002908f  mov     [rbp+100h+var_90], 1
0x180029096  mov     [rbp+100h+var_88], rax
0x18002909a  lea     rax, [rsp+200h+var_188]
0x18002909f  mov     [rbp+100h+var_80], rax
0x1800290a6  mov     [rbp+100h+var_78], rdi
0x1800290ad  mov     [rbp+100h+var_70], rdi
0x1800290b4  lea     rax, [rsp+200h+var_190]
0x1800290b9  mov     [rbp+100h+var_68], rax
0x1800290c0  mov     [rbp+100h+var_60], rdi
0x1800290c7  mov     [rbp+100h+var_58], edi
0x1800290cd  lea     rax, [rbp+100h+var_160]
0x1800290d1  mov     [rbp+100h+var_50], rax
0x1800290d8  mov     [rbp+100h+var_48], dil
0x1800290df  lea     rax, ??_7IDB_IDBTransaction_commitAndClose@IndexedDbTraceLogging@@6B@; const IndexedDbTraceLogging::IDB_IDBTransaction_commitAndClose::`vftable'
0x1800290e6  mov     [rsp+200h+var_190], rax
0x1800290eb  mov     rdx, [r13+0]; void *
0x1800290ef  lea     rcx, [rsp+200h+var_190]; this
0x1800290f4  call    ?StartActivity@IDB_IDBTransaction_commitAndClose@IndexedDbTraceLogging@@QEAAXPEAX@Z; IndexedDbTraceLogging::IDB_IDBTransaction_commitAndClose::StartActivity(void *)
0x1800290f9  nop
0x1800290fa  mov     [r12], rdi
0x1800290fe  mov     ebx, 80070057h
0x180029103  mov     r15, [r13+0]
0x180029107  test    r15, r15
0x18002910a  jz      loc_1800292BF
0x180029110  mov     qword ptr [rsp+200h+pftDueTime.dwLowDateTime], rdi
0x180029115  lea     rcx, [rsp+200h+pftDueTime]; struct ICallerIdentity **
0x18002911a  call    ?GetCallerId@CIndexedDBServerConnectionsMgr@@SAJPEAPEAUICallerIdentity@@@Z; CIndexedDBServerConnectionsMgr::GetCallerId(ICallerIdentity * *)
0x18002911f  test    eax, eax
0x180029121  js      loc_1800292BA
0x180029127  movzx   eax, byte ptr [r15+38h]
0x18002912c  nop
0x18002912d  mov     r14, qword ptr [rsp+200h+pftDueTime.dwLowDateTime]
0x180029132  test    al, al
0x180029134  jz      short loc_18002914D
0x180029136  mov     rcx, [r15+8]
0x18002913a  mov     rax, [rcx]
0x18002913d  mov     rdx, r14
0x180029140  mov     rax, [rax+10h]
0x180029144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029149  test    eax, eax
0x18002914b  jz      short loc_180029157
0x18002914d  mov     ebx, 80070005h
0x180029152  jmp     loc_1800291FC
0x180029157  mov     rsi, [r15+8]
0x18002915b  mov     rax, [r14]
0x18002915e  mov     rdx, [rsi]
0x180029161  mov     rdi, [rdx+28h]
0x180029165  mov     rcx, r14
0x180029168  mov     rax, [rax+28h]
0x18002916c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029171  movzx   ebx, al
0x180029174  mov     rcx, rsi
0x180029177  mov     rax, rdi
0x18002917a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002917f  cmp     al, bl
0x180029181  jnz     short loc_18002914D
0x180029183  mov     [rsp+200h+var_1E0], 0
0x180029188  xorps   xmm0, xmm0
0x18002918b  xor     eax, eax
0x18002918d  movups  [rsp+200h+var_1C8], xmm0
0x180029192  movups  [rsp+200h+var_1B8], xmm0
0x180029197  movups  [rsp+200h+var_1A8], xmm0
0x18002919c  mov     [rsp+200h+var_198], rax
0x1800291a1  lea     rcx, [rsp+200h+var_1C8]; struct __MIDL_RPCIndexedDB_0008 *
0x1800291a6  call    ?Free@IndexedDbDatabaseValuesTrait@IndexedDbRpcHelpers@@SAXAEAU__MIDL_RPCIndexedDB_0008@@@Z; IndexedDbRpcHelpers::IndexedDbDatabaseValuesTrait::Free(__MIDL_RPCIndexedDB_0008 &)
0x1800291ab  lea     r8, [rsp+200h+var_1C8]; struct __MIDL_RPCIndexedDB_0008 *
0x1800291b0  lea     rdx, [rsp+200h+var_1E0]; bool *
0x1800291b5  mov     rcx, r15; this
0x1800291b8  call    ?Commit@CIndexedDBServerTransaction@@QEAAJPEA_NPEAU__MIDL_RPCIndexedDB_0008@@@Z; CIndexedDBServerTransaction::Commit(bool *,__MIDL_RPCIndexedDB_0008 *)
0x1800291bd  mov     ebx, eax
0x1800291bf  cmp     [rsp+200h+var_1E0], 0
0x1800291c4  jnz     loc_180029330
0x1800291ca  mov     [rsp+200h+pftDueTime.dwLowDateTime], 0
0x1800291d2  test    ebx, ebx
0x1800291d4  js      loc_180029380
0x1800291da  cmp     ebx, 8070F000h
0x1800291e0  jz      short loc_1800291F2
0x1800291e2  mov     rcx, r15; this
0x1800291e5  call    ?Release@CIndexedDBServerTransaction@@QEAAKXZ; CIndexedDBServerTransaction::Release(void)
0x1800291ea  mov     qword ptr [r13+0], 0
0x1800291f2  lea     rcx, [rsp+200h+var_1C8]; struct __MIDL_RPCIndexedDB_0008 *
0x1800291f7  call    ?Free@IndexedDbDatabaseValuesTrait@IndexedDbRpcHelpers@@SAXAEAU__MIDL_RPCIndexedDB_0008@@@Z; IndexedDbRpcHelpers::IndexedDbDatabaseValuesTrait::Free(__MIDL_RPCIndexedDB_0008 &)
0x1800291fc  mov     rax, [r14]
0x1800291ff  mov     rcx, r14
0x180029202  mov     rax, [rax+8]
0x180029206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002920b  test    ebx, ebx
0x18002920d  js      loc_1800292BF
0x180029213  mov     rdx, [r12]; struct __MIDL_RPCIndexedDB_0008 *
0x180029217  lea     rcx, [rsp+200h+var_190]; this
0x18002921c  call    ?Stop@IDB_IDBTransaction_commitAndClose@IndexedDbTraceLogging@@QEAAXPEAU__MIDL_RPCIndexedDB_0008@@@Z; IndexedDbTraceLogging::IDB_IDBTransaction_commitAndClose::Stop(__MIDL_RPCIndexedDB_0008 *)
0x180029221  lea     rax, ??_7IDB_IDBTransaction_commitAndClose@IndexedDbTraceLogging@@6B@; const IndexedDbTraceLogging::IDB_IDBTransaction_commitAndClose::`vftable'
0x180029228  mov     [rsp+200h+var_190], rax
0x18002922d  cmp     [rbp+100h+var_78], 0
0x180029235  jnz     loc_1800293A8
0x18002923b  mov     rcx, [rbp+100h+var_80]
0x180029242  cmp     dword ptr [rcx], 1
0x180029245  jz      loc_1800293E4
0x18002924b  lea     rcx, [rsp+200h+var_190]
0x180029250  call    ??1?$ActivityBase@VStorageServerProvider@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180029255  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002925c  lock xadd cs:qword_180114130, rax
0x180029265  cmp     rax, 1
0x180029269  jnz     short loc_180029281
0x18002926b  xor     r9d, r9d; msWindowLength
0x18002926e  xor     r8d, r8d; msPeriod
0x180029271  xor     edx, edx; pftDueTime
0x180029273  mov     rcx, cs:pti; pti
0x18002927a  call    cs:__imp_SetThreadpoolTimer
0x180029280  nop
0x180029281  lea     rcx, word_1800D6108; lpWideCharStr
0x180029288  call    SetThreadName
0x18002928d  nop
0x18002928e  mov     eax, ebx
0x180029290  mov     rcx, [rbp+100h+var_40]
0x180029297  xor     rcx, rsp; StackCookie
0x18002929a  call    __security_check_cookie
0x18002929f  mov     rbx, [rsp+200h+arg_0]
0x1800292a7  add     rsp, 1D0h
0x1800292ae  pop     r15
0x1800292b0  pop     r14
0x1800292b2  pop     r13
0x1800292b4  pop     r12
0x1800292b6  pop     rdi
0x1800292b7  pop     rsi
0x1800292b8  pop     rbp
0x1800292b9  retn
0x1800292ba  mov     ebx, 80070005h
0x1800292bf  mov     edx, ebx
0x1800292c1  lea     rcx, [rsp+200h+var_190]
0x1800292c6  call    ?Stop@?$ActivityBase@VStorageServerProvider@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800292cb  jmp     loc_180029221
0x1800292d0  lea     rcx, dword_180114128
0x1800292d7  call    _Init_thread_header
0x1800292dc  cmp     cs:dword_180114128, 0FFFFFFFFh
0x1800292e3  jnz     loc_180029009
0x1800292e9  mov     edx, 493E0h
0x1800292ee  call    ??0HangDetectionWatchDog@@QEAA@V?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@@Z; HangDetectionWatchDog::HangDetectionWatchDog(std::chrono::duration<__int64,std::ratio<1,1000>>)
0x1800292f3  lea     rcx, _HangDetectionWatchDog__s_DefaultInstance____2____dynamic_atexit_destructor_for__s_instance__; void (__cdecl *)()
0x1800292fa  call    atexit
0x1800292ff  lea     rcx, dword_180114128
0x180029306  call    _Init_thread_footer
0x18002930b  jmp     loc_180029009
0x180029310  test    dil, dil
0x180029313  jnz     loc_18002923B
0x180029319  jmp     loc_18002924B
0x18002931e  mov     rcx, [rsp+200h+SRWLock]; SRWLock
0x180029323  test    rcx, rcx
0x180029326  jz      short loc_180029310
0x180029328  call    cs:__imp_ReleaseSRWLockExclusive
0x18002932e  jmp     short loc_180029310
0x180029330  lea     rdx, [rsp+200h+var_1C8]
0x180029335  lea     rcx, [rsp+200h+pftDueTime]
0x18002933a  call    ??$MakeSmartRpcPointer@VIndexedDbDatabaseValues@@V1@@@YA?AV?$SmartRpcPointer@VIndexedDbDatabaseValues@@@@$$QEAVIndexedDbDatabaseValues@@@Z; MakeSmartRpcPointer<IndexedDbDatabaseValues,IndexedDbDatabaseValues>(IndexedDbDatabaseValues &&)
0x18002933f  mov     rcx, [rax]
0x180029342  mov     qword ptr [rax], 0
0x180029349  mov     [r12], rcx
0x18002934d  mov     rdi, qword ptr [rsp+200h+pftDueTime.dwLowDateTime]
0x180029352  mov     qword ptr [rsp+200h+pftDueTime.dwLowDateTime], 0
0x18002935b  test    rdi, rdi
0x18002935e  jz      loc_1800291CA
0x180029364  mov     rcx, rdi; struct __MIDL_RPCIndexedDB_0008 *
0x180029367  call    ?Free@IndexedDbDatabaseValuesTrait@IndexedDbRpcHelpers@@SAXAEAU__MIDL_RPCIndexedDB_0008@@@Z; IndexedDbRpcHelpers::IndexedDbDatabaseValuesTrait::Free(__MIDL_RPCIndexedDB_0008 &)
0x18002936c  mov     [rsp+200h+SRWLock], rdi
0x180029371  lea     rcx, [rsp+200h+SRWLock]
0x180029376  call    WxFreeHeapEx
0x18002937b  jmp     loc_1800291CA
0x180029380  lea     rdx, [rsp+200h+pftDueTime]; unsigned int *
0x180029385  mov     rcx, r15; this
0x180029388  call    ?GetClientContextFlags@CIndexedDBServerTransaction@@QEAAJPEAK@Z; CIndexedDBServerTransaction::GetClientContextFlags(ulong *)
0x18002938d  test    eax, eax
0x18002938f  js      loc_1800291DA
0x180029395  xor     r8d, r8d; struct CWxString *
0x180029398  mov     edx, ebx; int
0x18002939a  mov     ecx, [rsp+200h+pftDueTime.dwLowDateTime]; unsigned int
0x18002939e  call    ?HandleCorruptionIfDetected@CIndexedDBServerPhysicalDBManager@@SAXKJPEAVCWxString@@@Z; CIndexedDBServerPhysicalDBManager::HandleCorruptionIfDetected(ulong,long,CWxString *)
0x1800293a3  jmp     loc_1800291DA
0x1800293a8  lea     rdx, [rsp+200h+SRWLock]
0x1800293ad  lea     rcx, [rsp+200h+var_190]
0x1800293b2  call    ?LockExclusive@?$ActivityBase@VStorageServerProvider@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800293b7  mov     rax, [rbp+100h+var_78]
0x1800293be  test    rax, rax
0x1800293c1  jz      short loc_1800293D0
0x1800293c3  cmp     dword ptr [rax], 1
0x1800293c6  jnz     short loc_1800293D0
0x1800293c8  mov     dil, 1
0x1800293cb  jmp     loc_18002931E
0x1800293d0  xor     dil, dil
0x1800293d3  lea     rcx, [rbp+100h+var_78]
0x1800293da  call    ?reset@?$shared_object@V?$ActivityData@VStorageServerProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VStorageServerProvider@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x1800293df  jmp     loc_18002931E
0x1800293e4  mov     eax, [rcx+58h]
0x1800293e7  mov     [rsp+200h+pftDueTime.dwLowDateTime], eax
0x1800293eb  mov     edx, 8007023Eh
0x1800293f0  test    eax, eax
0x1800293f2  cmovs   edx, eax
0x1800293f5  lea     r8, [rsp+200h+pftDueTime]
0x1800293fa  call    ?SetStopResult@?$ActivityData@VStorageServerProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VStorageServerProvider@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<StorageServerProvider,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x1800293ff  lea     rcx, [rsp+200h+var_190]
0x180029404  call    ?ReportStopActivity@?$ActivityBase@VStorageServerProvider@@$00$0EAAAAAAAAAAC@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<StorageServerProvider,1,70368744177666,4,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x180029409  jmp     loc_18002924B
```
