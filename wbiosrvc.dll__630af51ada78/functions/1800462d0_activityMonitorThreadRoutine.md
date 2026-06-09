# _activityMonitorThreadRoutine

- ea: `0x1800462d0`
- end: `0x180046475`
- name: `_activityMonitorThreadRoutine`
- size: `421`
- prototype: `static int(struct thread_inside_functions *, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18002d3b4`
- `0x1800462d0`
- `0x18005388c`
- `0x180058138`
- `0x180075a24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800463a7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800463a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046301`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800463b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046301`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800463b2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180046359`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180046410`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180046359`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180046410`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004641e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004641e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800462ee`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800462ee`

## string_xrefs

- `0x180046326`: `onecore\ds\security\biometrics\service\server\activitymonitor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall activityMonitorThreadRoutine(struct thread_inside_functions *a1, void *a2)
{
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v4; // rbx
  signed int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // r9
  signed int LastError; // eax
  __int64 v9; // r9
  unsigned int v10; // ecx
  __int64 v11; // r9
  int v13; // [rsp+20h] [rbp-28h]
  struct _TP_TIMER *v14; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned int v16; // [rsp+60h] [rbp+18h] BYREF
  struct _FILETIME pftDueTime; // [rsp+68h] [rbp+20h] BYREF

  ThreadpoolTimer = CreateThreadpoolTimer(timerCompletionCallback, 0, 0);
  v4 = ThreadpoolTimer;
  v14 = ThreadpoolTimer;
  if ( ThreadpoolTimer )
  {
    pftDueTime = (struct _FILETIME)-180000000LL;
    SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0x4650u, 0x1388u);
    if ( (unsigned int)dword_18010F170 > 4 )
    {
      v16 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18010F170,
        (unsigned __int8 *)word_1800ED492,
        0,
        v7,
        (__int64)&v16);
    }
    if ( _InterlockedCompareExchange((volatile signed __int32 *)a1 + 26, 2, 2) == 2
      && WaitForSingleObject(*((HANDLE *)a1 + 14), 0xFFFFFFFF) == -1 )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)dword_18010F170 > 2 )
      {
        v16 = v10;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_18010F170,
          (unsigned __int8 *)byte_1800ED44F,
          0,
          v9,
          (__int64)&v16);
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixActivityMonitorShutdownRace>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_FixActivityMonitorShutdownRace>::GetImpl'::`2'::impl) )
    {
      SetThreadpoolTimer(v4, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(v4, 1);
    }
    if ( (unsigned int)dword_18010F170 > 4 )
    {
      v16 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18010F170,
        (unsigned __int8 *)&dword_1800ED414,
        0,
        v11,
        (__int64)&v16);
    }
    v6 = 0;
  }
  else
  {
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    if ( (v6 & 0x80000000) != 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x156,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\activitymonitor.cpp",
        (const char *)v6,
        v13);
  }
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(&v14);
  return v6;
}

```

## disassembly

```asm
0x1800462d0  mov     [rsp+arg_0], rbx
0x1800462d5  mov     [rsp+arg_8], rsi
0x1800462da  push    rdi
0x1800462db  sub     rsp, 40h
0x1800462df  mov     rdi, rcx
0x1800462e2  xor     r8d, r8d; pcbe
0x1800462e5  xor     edx, edx; pv
0x1800462e7  lea     rcx, _timerCompletionCallback; pfnti
0x1800462ee  call    cs:__imp_CreateThreadpoolTimer
0x1800462f4  mov     rbx, rax
0x1800462f7  mov     [rsp+48h+var_18], rax
0x1800462fc  test    rax, rax
0x1800462ff  jnz     short loc_18004633C
0x180046301  call    cs:__imp_GetLastError
0x180046307  mov     ebx, eax
0x180046309  test    eax, eax
0x18004630b  jle     short loc_180046316
0x18004630d  movzx   ebx, ax
0x180046310  or      ebx, 80070000h
0x180046316  test    ebx, ebx
0x180046318  jns     loc_180046459
0x18004631e  mov     rcx, [rsp+48h]; this
0x180046323  mov     r9d, ebx; char *
0x180046326  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\biometrics\\serv"...
0x18004632d  mov     edx, 156h; void *
0x180046332  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046337  jmp     loc_180046459
0x18004633c  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFF5456B00h
0x180046345  mov     r9d, 1388h; msWindowLength
0x18004634b  mov     r8d, 4650h; msPeriod
0x180046351  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180046356  mov     rcx, rbx; pti
0x180046359  call    cs:__imp_SetThreadpoolTimer
0x18004635f  mov     eax, cs:dword_18010F170
0x180046365  cmp     eax, 4
0x180046368  jbe     short loc_180046392
0x18004636a  mov     [rsp+48h+arg_10], 0
0x180046372  lea     rax, [rsp+48h+arg_10]
0x180046377  mov     qword ptr [rsp+48h+var_28], rax
0x18004637c  xor     r8d, r8d
0x18004637f  lea     rdx, word_1800ED492
0x180046386  lea     rcx, dword_18010F170
0x18004638d  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180046392  mov     esi, 2
0x180046397  mov     eax, esi
0x180046399  lock cmpxchg [rdi+68h], esi
0x18004639e  jnz     short loc_1800463F5
0x1800463a0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800463a3  mov     rcx, [rdi+70h]; hHandle
0x1800463a7  call    cs:__imp_WaitForSingleObject
0x1800463ad  cmp     eax, 0FFFFFFFFh
0x1800463b0  jnz     short loc_1800463F5
0x1800463b2  call    cs:__imp_GetLastError
0x1800463b8  mov     ecx, eax
0x1800463ba  test    eax, eax
0x1800463bc  jle     short loc_1800463C7
0x1800463be  movzx   ecx, ax
0x1800463c1  or      ecx, 80070000h
0x1800463c7  mov     eax, cs:dword_18010F170
0x1800463cd  cmp     eax, esi
0x1800463cf  jbe     short loc_1800463F5
0x1800463d1  mov     [rsp+48h+arg_10], ecx
0x1800463d5  lea     rax, [rsp+48h+arg_10]
0x1800463da  mov     qword ptr [rsp+48h+var_28], rax
0x1800463df  xor     r8d, r8d
0x1800463e2  lea     rdx, byte_1800ED44F
0x1800463e9  lea     rcx, dword_18010F170
0x1800463f0  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800463f5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixActivityMonitorShutdownRace@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixActivityMonitorShutdownRace@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixActivityMonitorShutdownRace> `wil::Feature<__WilFeatureTraits_Feature_FixActivityMonitorShutdownRace>::GetImpl(void)'::`2'::impl
0x1800463fc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixActivityMonitorShutdownRace@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixActivityMonitorShutdownRace>::__private_IsEnabled(void)
0x180046401  test    al, al
0x180046403  jz      short loc_180046424
0x180046405  xor     r9d, r9d; msWindowLength
0x180046408  xor     r8d, r8d; msPeriod
0x18004640b  xor     edx, edx; pftDueTime
0x18004640d  mov     rcx, rbx; pti
0x180046410  call    cs:__imp_SetThreadpoolTimer
0x180046416  mov     edx, 1; fCancelPendingCallbacks
0x18004641b  mov     rcx, rbx; pti
0x18004641e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180046424  mov     eax, cs:dword_18010F170
0x18004642a  cmp     eax, 4
0x18004642d  jbe     short loc_180046457
0x18004642f  mov     [rsp+48h+arg_10], 0
0x180046437  lea     rax, [rsp+48h+arg_10]
0x18004643c  mov     qword ptr [rsp+48h+var_28], rax
0x180046441  xor     r8d, r8d
0x180046444  lea     rdx, dword_1800ED414
0x18004644b  lea     rcx, dword_18010F170
0x180046452  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180046457  xor     ebx, ebx
0x180046459  lea     rcx, [rsp+48h+var_18]
0x18004645e  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(void)
0x180046463  mov     eax, ebx
0x180046465  mov     rbx, [rsp+48h+arg_0]
0x18004646a  mov     rsi, [rsp+48h+arg_8]
0x18004646f  add     rsp, 40h
0x180046473  pop     rdi
0x180046474  retn
```
