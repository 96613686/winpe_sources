# PdcTimerHelper::ActivatePdcTimer(ulong)

- ea: `0x180051058`
- end: `0x180051156`
- name: `?ActivatePdcTimer@PdcTimerHelper@@QEAAXK@Z`
- size: `254`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, int)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18005115c`
- `0x18005385c`
- `0x18005b06c`
- `0x18005b560`

## callees

- `0x18002f044`
- `0x18003145c`
- `0x180031dec`
- `0x180050950`
- `0x180050dd4`
- `0x180051058`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180051145`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180051145`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051065`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051065`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800510fa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800510fa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800510db`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800510db`

## pseudocode

```c
void __fastcall PdcTimerHelper::ActivatePdcTimer(LPCRITICAL_SECTION lpCriticalSection, int a2)
{
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // rdx
  PTP_TIMER ThreadpoolTimer; // rax
  int v8; // ecx
  const char *v9; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPCRITICAL_SECTION v11; // [rsp+50h] [rbp+8h] BYREF
  __int64 v12; // [rsp+60h] [rbp+18h] BYREF
  struct _FILETIME pftDueTime; // [rsp+68h] [rbp+20h] BYREF

  EnterCriticalSection(lpCriticalSection);
  v11 = lpCriticalSection;
  HIDWORD(lpCriticalSection[1].OwningThread) = a2;
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    &lpCriticalSection[1].LockCount,
    0);
  LOBYTE(v6) = 1;
  try
  {
    v12 = PdcActivateNetwork(LODWORD(lpCriticalSection[1].OwningThread), v6, v4, v5);
    v11 = 0;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long Pdcv2ActivationClientDeactivate(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator=(
      &v11,
      &lpCriticalSection[1]);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long Pdcv2ActivationClientDeactivate(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator=(
      &lpCriticalSection[1],
      &v12);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long Pdcv2ActivationClientDeactivate(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long Pdcv2ActivationClientDeactivate(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v12);
    pftDueTime = (struct _FILETIME)-(__int64)(unsigned int)(10000 * HIDWORD(lpCriticalSection[1].OwningThread));
    ThreadpoolTimer = CreateThreadpoolTimer(PdcTimerHelper::TimerCallback, lpCriticalSection, 0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      &lpCriticalSection[1].LockCount,
      ThreadpoolTimer);
    SetThreadpoolTimer(*(PTP_TIMER *)&lpCriticalSection[1].LockCount, &pftDueTime, 0, 0);
    if ( v11 && (byte_1800AFD82 & 0x10) != 0 )
      McTemplateU0diiq_EventWriteTransfer(
        v8,
        (unsigned int)WPNPRV_PDC_DEACTIVATE,
        0,
        1,
        (char)lpCriticalSection[1].OwningThread,
        1);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long Pdcv2ActivationClientDeactivate(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long Pdcv2ActivationClientDeactivate(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v11);
    LeaveCriticalSection(lpCriticalSection);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x111C,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpconnector.cpp",
      v9);
  }
}

```

## disassembly

```asm
0x180051058  push    rbx
0x18005105a  push    rsi
0x18005105b  push    rdi
0x18005105c  sub     rsp, 30h
0x180051060  mov     ebx, edx
0x180051062  mov     rdi, rcx
0x180051065  call    cs:__imp_EnterCriticalSection
0x18005106b  mov     [rsp+48h+arg_0], rdi
0x180051070  mov     [rdi+3Ch], ebx
0x180051073  lea     rsi, [rdi+30h]
0x180051077  xor     edx, edx
0x180051079  mov     rcx, rsi
0x18005107c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180051081  mov     dl, 1
0x180051083  mov     ecx, [rdi+38h]
0x180051086  call    ?PdcActivateNetwork@@YAPEAXW4_PDC_REAOSN@@_N@Z; PdcActivateNetwork(_PDC_REAOSN,bool)
0x18005108b  mov     [rsp+48h+arg_10], rax
0x180051090  mov     [rsp+48h+arg_0], 0
0x180051099  lea     rdx, [rdi+28h]
0x18005109d  lea     rcx, [rsp+48h+arg_0]
0x1800510a2  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?Pdcv2ActivationClientDeactivate@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&Pdcv2ActivationClientDeactivate(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&Pdcv2ActivationClientDeactivate(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&)
0x1800510a7  lea     rdx, [rsp+48h+arg_10]
0x1800510ac  lea     rcx, [rdi+28h]
0x1800510b0  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?Pdcv2ActivationClientDeactivate@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&Pdcv2ActivationClientDeactivate(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&Pdcv2ActivationClientDeactivate(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&)
0x1800510b5  lea     rcx, [rsp+48h+arg_10]
0x1800510ba  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?Pdcv2ActivationClientDeactivate@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&Pdcv2ActivationClientDeactivate(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&Pdcv2ActivationClientDeactivate(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800510bf  imul    edx, [rdi+3Ch], 2710h
0x1800510c6  neg     rdx
0x1800510c9  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rdx
0x1800510ce  xor     r8d, r8d; pcbe
0x1800510d1  mov     rdx, rdi; pv
0x1800510d4  lea     rcx, ?TimerCallback@PdcTimerHelper@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800510db  call    cs:__imp_CreateThreadpoolTimer
0x1800510e1  mov     rdx, rax
0x1800510e4  mov     rcx, rsi
0x1800510e7  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800510ec  xor     r9d, r9d; msWindowLength
0x1800510ef  xor     r8d, r8d; msPeriod
0x1800510f2  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x1800510f7  mov     rcx, [rsi]; pti
0x1800510fa  call    cs:__imp_SetThreadpoolTimer
0x180051100  cmp     [rsp+48h+arg_0], 0
0x180051106  jz      short loc_180051137
0x180051108  test    cs:byte_1800AFD82, 10h
0x18005110f  jz      short loc_180051137
0x180051111  movsxd  rax, dword ptr [rdi+38h]
0x180051115  mov     [rsp+48h+var_20], 1
0x18005111d  mov     [rsp+48h+var_28], rax
0x180051122  mov     r9d, 1
0x180051128  xor     r8d, r8d
0x18005112b  lea     rdx, WPNPRV_PDC_DEACTIVATE
0x180051132  call    McTemplateU0diiq_EventWriteTransfer
0x180051137  lea     rcx, [rsp+48h+arg_0]
0x18005113c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?Pdcv2ActivationClientDeactivate@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&Pdcv2ActivationClientDeactivate(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&Pdcv2ActivationClientDeactivate(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180051141  nop
0x180051142  mov     rcx, rdi; lpCriticalSection
0x180051145  call    cs:__imp_LeaveCriticalSection
0x18005114b  nop
0x18005114c  jmp     short $+2
0x18005114e  add     rsp, 30h
0x180051152  pop     rdi
0x180051153  pop     rsi
0x180051154  pop     rbx
0x180051155  retn
```
