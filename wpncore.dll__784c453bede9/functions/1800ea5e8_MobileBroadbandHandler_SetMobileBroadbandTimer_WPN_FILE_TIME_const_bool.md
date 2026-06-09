# MobileBroadbandHandler::SetMobileBroadbandTimer(_WPN_FILE_TIME * const,bool)

- ea: `0x1800ea5e8`
- end: `0x1800ea6fd`
- name: `?SetMobileBroadbandTimer@MobileBroadbandHandler@@QEAAXQEAU_WPN_FILE_TIME@@_N@Z`
- size: `277`
- prototype: `void __fastcall(PVOID pv, struct _WPN_FILE_TIME *const, bool)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005d068`
- `0x18005d300`
- `0x180080b58`
- `0x1800ea294`

## callees

- `0x18001bf50`
- `0x18003b534`
- `0x180049644`
- `0x18009b278`
- `0x1800a0b2c`
- `0x1800ea5e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ea666`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ea6a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ea666`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ea6a3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800ea633`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800ea633`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800ea659`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800ea6cb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800ea659`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800ea6cb`

## pseudocode

```c
void __fastcall MobileBroadbandHandler::SetMobileBroadbandTimer(char *pv, struct _WPN_FILE_TIME *const a2, char a3)
{
  PTP_TIMER ThreadpoolTimer; // rax
  const char *v7; // r9
  _QWORD v8[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  PTP_TIMER pti; // [rsp+48h] [rbp+10h] BYREF
  struct _FILETIME pftDueTime; // [rsp+58h] [rbp+20h] BYREF

  try
  {
    if ( !a2 )
      MicrosoftTelemetryAssertTriggeredNoArgs(pv);
    pti = 0;
    pftDueTime = *(struct _FILETIME *)((char *)a2 + 4);
    if ( a3 )
    {
      ThreadpoolTimer = CreateThreadpoolTimer(MobileBroadbandHandler::TimerProcessing, pv, 0);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        &pti,
        ThreadpoolTimer);
      SetThreadpoolTimer(pti, &pftDueTime, 0, 0xEA60u);
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(pv + 64));
    v8[0] = pv + 64;
    if ( !pv[104] && a3 )
      std::swap<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>,0>(
        &pti,
        pv + 56);
    Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)v8);
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      &pti,
      0);
    EnterCriticalSection((LPCRITICAL_SECTION)(pv + 64));
    v8[0] = pv + 64;
    if ( !pv[104] && !a3 )
      SetThreadpoolTimer(*((PTP_TIMER *)pv + 7), &pftDueTime, 0, 0xEA60u);
    Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)v8);
    if ( pti )
      wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(pti);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xA2,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\conn\\mobilebroadbandhandler.cpp",
      v7);
  }
}

```

## disassembly

```asm
0x1800ea5e8  mov     [rsp+arg_0], rbx
0x1800ea5ed  mov     [rsp+arg_10], rsi
0x1800ea5f2  push    rdi
0x1800ea5f3  sub     rsp, 30h
0x1800ea5f7  mov     sil, r8b
0x1800ea5fa  mov     rdi, rdx
0x1800ea5fd  mov     rbx, rcx
0x1800ea600  test    rdx, rdx
0x1800ea603  jnz     short loc_1800EA60A
0x1800ea605  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "nullptr != NextResetDate")
0x1800ea60a  mov     [rsp+38h+pti], 0
0x1800ea613  mov     eax, [rdi+8]
0x1800ea616  mov     [rsp+38h+pftDueTime.dwHighDateTime], eax
0x1800ea61a  mov     eax, [rdi+4]
0x1800ea61d  mov     [rsp+38h+pftDueTime.dwLowDateTime], eax
0x1800ea621  test    sil, sil
0x1800ea624  jz      short loc_1800EA65F
0x1800ea626  xor     r8d, r8d; pcbe
0x1800ea629  mov     rdx, rbx; pv
0x1800ea62c  lea     rcx, ?TimerProcessing@MobileBroadbandHandler@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800ea633  call    cs:__imp_CreateThreadpoolTimer
0x1800ea639  mov     rdx, rax
0x1800ea63c  lea     rcx, [rsp+38h+pti]
0x1800ea641  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800ea646  mov     r9d, 0EA60h; msWindowLength
0x1800ea64c  xor     r8d, r8d; msPeriod
0x1800ea64f  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1800ea654  mov     rcx, [rsp+38h+pti]; pti
0x1800ea659  call    cs:__imp_SetThreadpoolTimer
0x1800ea65f  lea     rdi, [rbx+40h]
0x1800ea663  mov     rcx, rdi; lpCriticalSection
0x1800ea666  call    cs:__imp_EnterCriticalSection
0x1800ea66c  mov     [rsp+38h+var_18], rdi
0x1800ea671  cmp     byte ptr [rbx+68h], 0
0x1800ea675  jnz     short loc_1800EA68A
0x1800ea677  test    sil, sil
0x1800ea67a  jz      short loc_1800EA68A
0x1800ea67c  lea     rdx, [rbx+38h]
0x1800ea680  lea     rcx, [rsp+38h+pti]
0x1800ea685  call    ??$swap@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$0A@@std@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@0@Z; std::swap<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>,0>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &)
0x1800ea68a  lea     rcx, [rsp+38h+var_18]; this
0x1800ea68f  call    ??1SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection(void)
0x1800ea694  xor     edx, edx
0x1800ea696  lea     rcx, [rsp+38h+pti]
0x1800ea69b  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800ea6a0  mov     rcx, rdi; lpCriticalSection
0x1800ea6a3  call    cs:__imp_EnterCriticalSection
0x1800ea6a9  mov     [rsp+38h+var_18], rdi
0x1800ea6ae  cmp     byte ptr [rbx+68h], 0
0x1800ea6b2  jnz     short loc_1800EA6D1
0x1800ea6b4  test    sil, sil
0x1800ea6b7  jnz     short loc_1800EA6D1
0x1800ea6b9  mov     r9d, 0EA60h; msWindowLength
0x1800ea6bf  xor     r8d, r8d; msPeriod
0x1800ea6c2  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1800ea6c7  mov     rcx, [rbx+38h]; pti
0x1800ea6cb  call    cs:__imp_SetThreadpoolTimer
0x1800ea6d1  lea     rcx, [rsp+38h+var_18]; this
0x1800ea6d6  call    ??1SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection(void)
0x1800ea6db  mov     rcx, [rsp+38h+pti]; pti
0x1800ea6e0  test    rcx, rcx
0x1800ea6e3  jz      short loc_1800EA6EB
0x1800ea6e5  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1800ea6ea  nop
0x1800ea6eb  jmp     short $+2
0x1800ea6ed  mov     rbx, [rsp+38h+arg_0]
0x1800ea6f2  mov     rsi, [rsp+38h+arg_10]
0x1800ea6f7  add     rsp, 30h
0x1800ea6fb  pop     rdi
0x1800ea6fc  retn
```
