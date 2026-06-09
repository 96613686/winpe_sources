# s_IDBFactory_getDatabaseNames

- ea: `0x18007eac0`
- end: `0x18007ec13`
- name: `s_IDBFactory_getDatabaseNames`
- size: `339`
- prototype: `__int64 __fastcall(__int64, CIndexedDBServerFactoryWithSecurityContext **, unsigned int *, struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 **)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x18001f470`
- `0x1800273f0`
- `0x180029e74`
- `0x18002d290`
- `0x18002e8f4`
- `0x18007eac0`
- `0x18007ec1c`
- `0x180080fb0`
- `0x18008d860`
- `0x1800a7f98`
- `0x1800a9078`
- `0x1800b2dbc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18007eba3`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18007eba3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007ebe0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007ebe0`

## pseudocode

```c
__int64 __fastcall s_IDBFactory_getDatabaseNames(
        __int64 a1,
        CIndexedDBServerFactoryWithSecurityContext **a2,
        unsigned int *a3,
        struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 **a4)
{
  struct HangDetectionWatchDog *v7; // rdx
  int DatabaseNames; // ebx
  struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 *v9; // rdi
  __int64 v10; // rcx
  volatile signed __int64 *v11; // rcx
  volatile signed __int64 *v13; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v14; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v15[16]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v16[42]; // [rsp+50h] [rbp-B0h] BYREF

  SetThreadName(L"RPC IDBFact_getDatabaseNames");
  HangDetectionWatchDog::Activity::Activity((HangDetectionWatchDog::Activity *)&v13, v7);
  wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v16,
    "IDB_IDBFactory_getDatabaseNames");
  v16[0] = &IndexedDbTraceLogging::IDB_IDBFactory_getDatabaseNames::`vftable';
  IndexedDbTraceLogging::IDB_IDBFactory_getDatabaseNames::StartActivity(
    (IndexedDbTraceLogging::IDB_IDBFactory_getDatabaseNames *)v16,
    a2);
  DatabaseNames = -2147024809;
  if ( a2
    && (DatabaseNames = CIndexedDBServerFactoryWithSecurityContext::GetDatabaseNames(a2[2], a3, a4), DatabaseNames >= 0) )
  {
    v9 = *a4;
    gsl::details::extent_type<-1>::extent_type<-1>(&v14, *a3);
    *((_QWORD *)&v14 + 1) = v9;
    if ( (_QWORD)v14 == -1 || !v9 && (_QWORD)v14 )
    {
      _o_terminate(v10);
      __debugbreak();
    }
    v14 = *(_OWORD *)gsl::span<__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 const,-1>::span<__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 const,-1>(
                       v15,
                       &v14);
    IndexedDbTraceLogging::IDB_IDBFactory_getDatabaseNames::Stop(v16, &v14);
  }
  else
  {
    wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
      v16,
      (unsigned int)DatabaseNames);
  }
  IndexedDbTraceLogging::IDB_IDBFactory_getDatabaseNames::~IDB_IDBFactory_getDatabaseNames((IndexedDbTraceLogging::IDB_IDBFactory_getDatabaseNames *)v16);
  v11 = v13;
  if ( _InterlockedExchangeAdd64(v13, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
    SetThreadpoolTimer(*((PTP_TIMER *)v11 + 1), 0, 0, 0);
  SetThreadName(&word_1800D6108);
  return (unsigned int)DatabaseNames;
}

```

## disassembly

```asm
0x18007eac0  push    rbp
0x18007eac2  push    rbx
0x18007eac3  push    rsi
0x18007eac4  push    rdi
0x18007eac5  push    r14
0x18007eac7  lea     rbp, [rsp-0B0h]
0x18007eacf  sub     rsp, 1B0h
0x18007ead6  mov     rax, cs:__security_cookie
0x18007eadd  xor     rax, rsp
0x18007eae0  mov     [rbp+0D0h+var_30], rax
0x18007eae7  mov     rdi, r9
0x18007eaea  mov     rsi, r8
0x18007eaed  mov     r14, rdx
0x18007eaf0  lea     rcx, aRpcIdbfactGetd; "RPC IDBFact_getDatabaseNames"
0x18007eaf7  call    SetThreadName
0x18007eafc  lea     rcx, [rsp+1D0h+var_1B0]; this
0x18007eb01  call    ??0Activity@HangDetectionWatchDog@@QEAA@PEAV1@@Z; HangDetectionWatchDog::Activity::Activity(HangDetectionWatchDog *)
0x18007eb06  nop
0x18007eb07  lea     rdx, aIdbIdbfactoryG; "IDB_IDBFactory_getDatabaseNames"
0x18007eb0e  lea     rcx, [rsp+1D0h+var_180]
0x18007eb13  call    ??0?$ActivityBase@VStorageServerProvider@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18007eb18  lea     rax, ??_7IDB_IDBFactory_getDatabaseNames@IndexedDbTraceLogging@@6B@; const IndexedDbTraceLogging::IDB_IDBFactory_getDatabaseNames::`vftable'
0x18007eb1f  mov     [rsp+1D0h+var_180], rax
0x18007eb24  mov     rdx, r14; void *
0x18007eb27  lea     rcx, [rsp+1D0h+var_180]; this
0x18007eb2c  call    ?StartActivity@IDB_IDBFactory_getDatabaseNames@IndexedDbTraceLogging@@QEAAXPEAX@Z; IndexedDbTraceLogging::IDB_IDBFactory_getDatabaseNames::StartActivity(void *)
0x18007eb31  nop
0x18007eb32  mov     ebx, 80070057h
0x18007eb37  test    r14, r14
0x18007eb3a  jz      short loc_18007EBAA
0x18007eb3c  mov     r8, rdi; struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 **
0x18007eb3f  mov     rdx, rsi; unsigned int *
0x18007eb42  mov     rcx, [r14+10h]; this
0x18007eb46  call    ?GetDatabaseNames@CIndexedDBServerFactoryWithSecurityContext@@QEAAJPEAKPEAPEAU__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001@@@Z; CIndexedDBServerFactoryWithSecurityContext::GetDatabaseNames(ulong *,__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 * *)
0x18007eb4b  mov     ebx, eax
0x18007eb4d  test    eax, eax
0x18007eb4f  js      short loc_18007EBAA
0x18007eb51  mov     rdi, [rdi]
0x18007eb54  mov     edx, [rsi]
0x18007eb56  lea     rcx, [rsp+1D0h+var_1A0]
0x18007eb5b  call    ??0?$extent_type@$0?0@details@gsl@@QEAA@_K@Z; gsl::details::extent_type<-1>::extent_type<-1>(unsigned __int64)
0x18007eb60  mov     qword ptr [rsp+1D0h+var_1A0+8], rdi
0x18007eb65  mov     rax, qword ptr [rsp+1D0h+var_1A0]
0x18007eb6a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007eb6e  jz      short loc_18007EBA3
0x18007eb70  test    rdi, rdi
0x18007eb73  jnz     short loc_18007EB7A
0x18007eb75  test    rax, rax
0x18007eb78  jnz     short loc_18007EBA3
0x18007eb7a  lea     rdx, [rsp+1D0h+var_1A0]
0x18007eb7f  lea     rcx, [rsp+1D0h+var_190]
0x18007eb84  call    ??$?0U__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001@@$0?0$0?0$0A@@?$span@$$CBU__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001@@$0?0@gsl@@QEAA@AEBV?$span@U__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001@@$0?0@1@@Z; gsl::span<__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 const,-1>::span<__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 const,-1>(gsl::span<__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001,-1> const &)
0x18007eb89  movups  xmm0, xmmword ptr [rax]
0x18007eb8c  movdqu  [rsp+1D0h+var_1A0], xmm0
0x18007eb92  lea     rdx, [rsp+1D0h+var_1A0]
0x18007eb97  lea     rcx, [rsp+1D0h+var_180]
0x18007eb9c  call    ?Stop@IDB_IDBFactory_getDatabaseNames@IndexedDbTraceLogging@@QEAAXV?$span@$$CBU__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001@@$0?0@gsl@@@Z; IndexedDbTraceLogging::IDB_IDBFactory_getDatabaseNames::Stop(gsl::span<__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 const,-1>)
0x18007eba1  jmp     short loc_18007EBB6
0x18007eba3  call    cs:__imp__o_terminate
0x18007eba9  int     3; Trap to Debugger
0x18007ebaa  mov     edx, ebx
0x18007ebac  lea     rcx, [rsp+1D0h+var_180]
0x18007ebb1  call    ?Stop@?$ActivityBase@VStorageServerProvider@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18007ebb6  lea     rcx, [rsp+1D0h+var_180]; this
0x18007ebbb  call    ??1IDB_IDBFactory_getDatabaseNames@IndexedDbTraceLogging@@QEAA@XZ; IndexedDbTraceLogging::IDB_IDBFactory_getDatabaseNames::~IDB_IDBFactory_getDatabaseNames(void)
0x18007ebc0  mov     rcx, [rsp+1D0h+var_1B0]
0x18007ebc5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007ebc9  lock xadd [rcx], rax
0x18007ebce  cmp     rax, 1
0x18007ebd2  jnz     short loc_18007EBE7
0x18007ebd4  xor     r9d, r9d; msWindowLength
0x18007ebd7  xor     r8d, r8d; msPeriod
0x18007ebda  xor     edx, edx; pftDueTime
0x18007ebdc  mov     rcx, [rcx+8]; pti
0x18007ebe0  call    cs:__imp_SetThreadpoolTimer
0x18007ebe6  nop
0x18007ebe7  lea     rcx, word_1800D6108; lpWideCharStr
0x18007ebee  call    SetThreadName
0x18007ebf3  nop
0x18007ebf4  mov     eax, ebx
0x18007ebf6  mov     rcx, [rbp+0D0h+var_30]
0x18007ebfd  xor     rcx, rsp; StackCookie
0x18007ec00  call    __security_check_cookie
0x18007ec05  add     rsp, 1B0h
0x18007ec0c  pop     r14
0x18007ec0e  pop     rdi
0x18007ec0f  pop     rsi
0x18007ec10  pop     rbx
0x18007ec11  pop     rbp
0x18007ec12  retn
```
