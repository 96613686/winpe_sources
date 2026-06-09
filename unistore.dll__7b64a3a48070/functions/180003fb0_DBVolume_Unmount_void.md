# DBVolume::Unmount(void)

- ea: `0x180003fb0`
- end: `0x180004129`
- name: `?Unmount@DBVolume@@EEAAJXZ`
- size: `377`
- prototype: `__int64 __fastcall(DBVolume *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003a38`

## callees

- `0x180003fb0`
- `0x180004130`
- `0x1800041b0`
- `0x1800041e4`
- `0x18000424c`
- `0x180004290`
- `0x1800068f0`
- `0x18000f530`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004003`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004003`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004054`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004054`
- `ESENT!JetStopServiceInstance` at `0x1800040b6`
- `ESENT!JetStopServiceInstance` at `0x1800040b6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004099`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004099`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800040ab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800040ab`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18000407c`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18000407c`

## string_xrefs

- `0x1800040cd`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180004110`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`

## pseudocode

```c
__int64 __fastcall DBVolume::Unmount(DBVolume *this)
{
  struct _TP_TIMER *v2; // rcx
  __int64 v3; // rcx
  JET_INSTANCE v4; // rcx
  __int64 v5; // rcx
  __int64 result; // rax
  JET_ERR v7; // eax
  unsigned int v8; // eax
  unsigned __int64 v9; // rax
  int v10; // eax
  unsigned int HresultFromJetError; // eax

  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 24);
  if ( v2 && IsThreadpoolTimerSet(v2) )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 24), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 24), 1);
  }
  if ( (unsigned int)IsServiceShuttingDown() )
  {
    v3 = *((_QWORD *)this + 30);
    if ( v3 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 24LL))(v3);
      v10 = CommsESE_JetCommitTransaction(v9, 8u);
      if ( v10 < 0 )
      {
        HresultFromJetError = MakeHresultFromJetError(v10);
        Log_UnistoreHREvent_0(
          HresultFromJetError,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
          4616);
      }
    }
    v4 = *((_QWORD *)this + 10);
    if ( v4 != -1 )
    {
      v7 = JetStopServiceInstance(v4);
      if ( v7 < 0 )
      {
        v8 = MakeHresultFromJetError(v7);
        Log_UnistoreHREvent_0(
          v8,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
          4622);
      }
    }
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  utl::_HashTable<CallerId,utl::pair<CallerId const,ATL::CComPtr<IDBSession>>,utl::hash<CallerId>,utl::equal_to<CallerId>,utl::allocator<utl::pair<CallerId const,ATL::CComPtr<IDBSession>>>,0>::_ClearList((char *)this + 88);
  if ( *((_QWORD *)this + 13) )
    utl::_HashTable<unsigned long,utl::pair<unsigned long const,ATL::CComPtr<ISyncKnowledge>>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,ATL::CComPtr<ISyncKnowledge>>>,0>::_InitBuckets((char *)this + 88);
  utl::list<utl::pair<CallerId,ATL::CComPtr<IDBSession>>,utl::allocator<utl::pair<CallerId,ATL::CComPtr<IDBSession>>>>::clear((char *)this + 128);
  v5 = *((_QWORD *)this + 30);
  if ( v5 )
  {
    *((_QWORD *)this + 30) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  result = 0;
  *((_QWORD *)this + 10) = -1;
  *((_QWORD *)this + 2) = 0;
  return result;
}

```

## disassembly

```asm
0x180003fb0  mov     [rsp+arg_0], rbx
0x180003fb5  mov     [rsp+arg_8], rsi
0x180003fba  push    rdi
0x180003fbb  sub     rsp, 30h
0x180003fbf  mov     rbx, rcx
0x180003fc2  mov     rcx, [rcx+0C0h]; pti
0x180003fc9  test    rcx, rcx
0x180003fcc  jnz     loc_18000407C
0x180003fd2  call    ?IsServiceShuttingDown@@YAHXZ; IsServiceShuttingDown(void)
0x180003fd7  test    eax, eax
0x180003fd9  jz      short loc_180003FF9
0x180003fdb  mov     rcx, [rbx+0F0h]
0x180003fe2  test    rcx, rcx
0x180003fe5  jnz     loc_1800040E6
0x180003feb  mov     rcx, [rbx+50h]; instance
0x180003fef  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180003ff3  jnz     loc_1800040B6
0x180003ff9  lea     rsi, [rbx+98h]
0x180004000  mov     rcx, rsi; lpCriticalSection
0x180004003  call    cs:__imp_EnterCriticalSection
0x180004009  lea     rcx, [rbx+58h]
0x18000400d  call    ?_ClearList@?$_HashTable@UCallerId@@U?$pair@$$CBUCallerId@@V?$CComPtr@VIDBSession@@@ATL@@@utl@@U?$hash@UCallerId@@@3@U?$equal_to@UCallerId@@@3@V?$allocator@U?$pair@$$CBUCallerId@@V?$CComPtr@VIDBSession@@@ATL@@@utl@@@3@$0A@@utl@@AEAAXXZ; utl::_HashTable<CallerId,utl::pair<CallerId const,ATL::CComPtr<IDBSession>>,utl::hash<CallerId>,utl::equal_to<CallerId>,utl::allocator<utl::pair<CallerId const,ATL::CComPtr<IDBSession>>>,0>::_ClearList(void)
0x180004012  cmp     qword ptr [rbx+68h], 0
0x180004017  jz      short loc_180004022
0x180004019  lea     rcx, [rbx+58h]
0x18000401d  call    ?_InitBuckets@?$_HashTable@KU?$pair@$$CBKV?$CComPtr@UISyncKnowledge@@@ATL@@@utl@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBKV?$CComPtr@UISyncKnowledge@@@ATL@@@utl@@@2@$0A@@utl@@AEAAXXZ; utl::_HashTable<ulong,utl::pair<ulong const,ATL::CComPtr<ISyncKnowledge>>,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,ATL::CComPtr<ISyncKnowledge>>>,0>::_InitBuckets(void)
0x180004022  lea     rcx, [rbx+80h]
0x180004029  call    ?clear@?$list@U?$pair@UCallerId@@V?$CComPtr@VIDBSession@@@ATL@@@utl@@V?$allocator@U?$pair@UCallerId@@V?$CComPtr@VIDBSession@@@ATL@@@utl@@@2@@utl@@QEAAXXZ; utl::list<utl::pair<CallerId,ATL::CComPtr<IDBSession>>,utl::allocator<utl::pair<CallerId,ATL::CComPtr<IDBSession>>>>::clear(void)
0x18000402e  mov     rcx, [rbx+0F0h]
0x180004035  test    rcx, rcx
0x180004038  jz      short loc_180004051
0x18000403a  mov     qword ptr [rbx+0F0h], 0
0x180004045  mov     rax, [rcx]
0x180004048  mov     rax, [rax+10h]
0x18000404c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004051  mov     rcx, rsi; lpCriticalSection
0x180004054  call    cs:__imp_LeaveCriticalSection
0x18000405a  mov     rsi, [rsp+38h+arg_8]
0x18000405f  xor     eax, eax
0x180004061  mov     qword ptr [rbx+50h], 0FFFFFFFFFFFFFFFFh
0x180004069  mov     qword ptr [rbx+10h], 0
0x180004071  mov     rbx, [rsp+38h+arg_0]
0x180004076  add     rsp, 30h
0x18000407a  pop     rdi
0x18000407b  retn
0x18000407c  call    cs:__imp_IsThreadpoolTimerSet
0x180004082  test    eax, eax
0x180004084  jz      loc_180003FD2
0x18000408a  mov     rcx, [rbx+0C0h]; pti
0x180004091  xor     r9d, r9d; msWindowLength
0x180004094  xor     r8d, r8d; msPeriod
0x180004097  xor     edx, edx; pftDueTime
0x180004099  call    cs:__imp_SetThreadpoolTimer
0x18000409f  mov     rcx, [rbx+0C0h]; pti
0x1800040a6  mov     edx, 1; fCancelPendingCallbacks
0x1800040ab  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800040b1  jmp     loc_180003FD2
0x1800040b6  call    cs:__imp_JetStopServiceInstance
0x1800040bc  test    eax, eax
0x1800040be  jns     loc_180003FF9
0x1800040c4  mov     ecx, eax; int
0x1800040c6  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800040cb  mov     ecx, eax
0x1800040cd  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800040d4  mov     r9d, 120Eh
0x1800040da  xor     edx, edx
0x1800040dc  call    Log_UnistoreHREvent_0
0x1800040e1  jmp     loc_180003FF9
0x1800040e6  mov     rax, [rcx]
0x1800040e9  mov     rax, [rax+18h]
0x1800040ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040f2  mov     rcx, rax; unsigned __int64
0x1800040f5  mov     edx, 8; unsigned int
0x1800040fa  call    ?CommsESE_JetCommitTransaction@@YAJ_KK@Z; CommsESE_JetCommitTransaction(unsigned __int64,ulong)
0x1800040ff  test    eax, eax
0x180004101  jns     loc_180003FEB
0x180004107  mov     ecx, eax; int
0x180004109  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18000410e  mov     ecx, eax
0x180004110  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180004117  mov     r9d, 1208h
0x18000411d  xor     edx, edx
0x18000411f  call    Log_UnistoreHREvent_0
0x180004124  jmp     loc_180003FEB
```
