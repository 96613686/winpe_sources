# RouteManagerFailoverTimer::StartFailoverDebounceTimer(RouteManagement::FailoverTrigger)

- ea: `0x1800c2b00`
- end: `0x1800c2c6f`
- name: `?StartFailoverDebounceTimer@RouteManagerFailoverTimer@@QEAAXW4FailoverTrigger@RouteManagement@@@Z`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x1800716ac`

## callees

- `0x1800137a0`
- `0x180027630`
- `0x180034584`
- `0x1800651a8`
- `0x180065258`
- `0x180084f50`
- `0x1800c2b00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c2c3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c2c3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2b6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2b6f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800c2b35`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800c2b35`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800c2bdf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800c2bdf`

## string_xrefs

- `0x1800c2c02`: `onecoreuap\net\wcm\service\base\routemanager\routemanagerfailovertimer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RouteManagerFailoverTimer::StartFailoverDebounceTimer(PTP_TIMER *a1, int a2)
{
  DWORD LastError; // eax
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  __int64 v9; // [rsp+40h] [rbp-40h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+48h] [rbp-38h] BYREF
  PTP_TIMER ThreadpoolTimer; // [rsp+50h] [rbp-30h] BYREF
  const char *v12; // [rsp+58h] [rbp-28h] BYREF
  const char *v13; // [rsp+60h] [rbp-20h] BYREF
  struct _FILETIME pftDueTime; // [rsp+68h] [rbp-18h] BYREF

  ThreadpoolTimer = CreateThreadpoolTimer(RouteManagerFailoverTimer::FailoverDebounceTimerCallback, a1, 0);
  if ( ThreadpoolTimer )
  {
    lpCriticalSection = 0;
    wil::EnterCriticalSection(&lpCriticalSection, a1 + 1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>::swap(
      a1,
      &ThreadpoolTimer);
    *((_DWORD *)a1 + 17) = a2;
    *((_BYTE *)a1 + 64) = 1;
    v9 = -2500000;
    pftDueTime = (struct _FILETIME)-2500000LL;
    SetThreadpoolTimer(*a1, &pftDueTime, 0, 0);
    if ( (unsigned int)dword_18013A120 > 5 )
    {
      LODWORD(v9) = 250;
      v12 = "FailoverDebounceTimer timer started (ms)";
      v13 = "onecoreuap\\net\\wcm\\service\\base\\routemanager\\routemanagerfailovertimer.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v5,
        (unsigned int)byte_18011D463,
        v6,
        v7,
        (__int64)&v13,
        (__int64)&v12,
        (__int64)&v9);
    }
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
  }
  else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
         && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, &WPP_7457b825ecb838ba4d8f12d605244ad5_Traceguids, LastError);
  }
  return wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(&ThreadpoolTimer);
}

```

## disassembly

```asm
0x1800c2b00  mov     [rsp-8+arg_8], rbx
0x1800c2b05  mov     [rsp-8+arg_10], rdi
0x1800c2b0a  push    rbp
0x1800c2b0b  mov     rbp, rsp
0x1800c2b0e  sub     rsp, 80h
0x1800c2b15  mov     rax, cs:__security_cookie
0x1800c2b1c  xor     rax, rsp
0x1800c2b1f  mov     [rbp+var_10], rax
0x1800c2b23  mov     edi, edx
0x1800c2b25  mov     rbx, rcx
0x1800c2b28  xor     r8d, r8d; pcbe
0x1800c2b2b  mov     rdx, rcx; pv
0x1800c2b2e  lea     rcx, ?FailoverDebounceTimerCallback@RouteManagerFailoverTimer@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800c2b35  call    cs:__imp_CreateThreadpoolTimer
0x1800c2b3b  mov     [rbp+var_30], rax
0x1800c2b3f  test    rax, rax
0x1800c2b42  jnz     short loc_1800C2B99
0x1800c2b44  lea     rcx, WPP_GLOBAL_Control
0x1800c2b4b  mov     rax, cs:WPP_GLOBAL_Control
0x1800c2b52  cmp     rax, rcx
0x1800c2b55  jz      loc_1800C2C45
0x1800c2b5b  cmp     byte ptr [rax+19h], 1
0x1800c2b5f  jb      loc_1800C2C45
0x1800c2b65  test    byte ptr [rax+1Ch], 1
0x1800c2b69  jz      loc_1800C2C45
0x1800c2b6f  call    cs:__imp_GetLastError
0x1800c2b75  mov     edx, 0Dh
0x1800c2b7a  mov     r9d, eax
0x1800c2b7d  lea     r8, WPP_7457b825ecb838ba4d8f12d605244ad5_Traceguids
0x1800c2b84  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c2b8b  mov     rcx, [rcx+10h]
0x1800c2b8f  call    WPP_SF_d
0x1800c2b94  jmp     loc_1800C2C45
0x1800c2b99  mov     [rbp+lpCriticalSection], 0
0x1800c2ba1  lea     rdx, [rbx+8]
0x1800c2ba5  lea     rcx, [rbp+lpCriticalSection]
0x1800c2ba9  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800c2bae  nop
0x1800c2baf  lea     rdx, [rbp+var_30]
0x1800c2bb3  mov     rcx, rbx
0x1800c2bb6  call    ?swap@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>::swap(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &)
0x1800c2bbb  mov     [rbx+44h], edi
0x1800c2bbe  mov     byte ptr [rbx+40h], 1
0x1800c2bc2  mov     [rbp+var_40], 0FFFFFFFFFFD9DA60h
0x1800c2bca  mov     rax, [rbp+var_40]
0x1800c2bce  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], rax
0x1800c2bd2  xor     r9d, r9d; msWindowLength
0x1800c2bd5  xor     r8d, r8d; msPeriod
0x1800c2bd8  lea     rdx, [rbp+pftDueTime]; pftDueTime
0x1800c2bdc  mov     rcx, [rbx]; pti
0x1800c2bdf  call    cs:__imp_SetThreadpoolTimer
0x1800c2be5  mov     eax, cs:dword_18013A120
0x1800c2beb  cmp     eax, 5
0x1800c2bee  jbe     short loc_1800C2C35
0x1800c2bf0  mov     dword ptr [rbp+var_40], 0FAh
0x1800c2bf7  lea     rax, aFailoverdeboun; "FailoverDebounceTimer timer started (ms"...
0x1800c2bfe  mov     [rbp+var_28], rax
0x1800c2c02  lea     rax, aOnecoreuapNetW_5; "onecoreuap\\net\\wcm\\service\\base\\ro"...
0x1800c2c09  mov     [rbp+var_20], rax
0x1800c2c0d  lea     rax, [rbp+var_40]
0x1800c2c11  mov     [rsp+80h+var_50], rax
0x1800c2c16  lea     rax, [rbp+var_28]
0x1800c2c1a  mov     [rsp+80h+var_58], rax
0x1800c2c1f  lea     rax, [rbp+var_20]
0x1800c2c23  mov     [rsp+80h+var_60], rax
0x1800c2c28  lea     rdx, byte_18011D463
0x1800c2c2f  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800c2c34  nop
0x1800c2c35  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x1800c2c39  test    rcx, rcx
0x1800c2c3c  jz      short loc_1800C2C45
0x1800c2c3e  call    cs:__imp_LeaveCriticalSection
0x1800c2c44  nop
0x1800c2c45  lea     rcx, [rbp+var_30]
0x1800c2c49  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(void)
0x1800c2c4e  mov     rcx, [rbp+var_10]
0x1800c2c52  xor     rcx, rsp; StackCookie
0x1800c2c55  call    __security_check_cookie
0x1800c2c5a  lea     r11, [rsp+80h+var_s0]
0x1800c2c62  mov     rbx, [r11+18h]
0x1800c2c66  mov     rdi, [r11+20h]
0x1800c2c6a  mov     rsp, r11
0x1800c2c6d  pop     rbp
0x1800c2c6e  retn
```
