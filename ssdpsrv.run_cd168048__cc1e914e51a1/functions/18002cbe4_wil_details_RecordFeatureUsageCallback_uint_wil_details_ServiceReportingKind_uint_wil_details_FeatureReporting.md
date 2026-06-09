# wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)

- ea: `0x18002cbe4`
- end: `0x18002ccd5`
- name: `?RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18002d204`

## callees

- `0x1800246b8`
- `0x180024d20`
- `0x18002cbe4`
- `0x18002e004`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002cc65`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002cc65`

## pseudocode

```c
void __fastcall wil::details::RecordFeatureUsageCallback(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        struct wil_details_FeatureReportingCache *a4,
        RTL_SRWLOCK *a5)
{
  unsigned int v6; // edi
  RTL_SRWLOCK *v7; // rbx
  unsigned int Ptr_high; // r8d
  void (__fastcall *v9)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  const char *v10; // [rsp+20h] [rbp-8h]

  v6 = a1;
  if ( g_wil_details_RecordSRUMFeatureUsage && (!(_DWORD)a2 || (unsigned int)(a2 - 100) <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(a1, a2, 1);
  v7 = a5;
  if ( LODWORD(a5->Ptr) )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
      v6,
      a4);
  Ptr_high = HIDWORD(v7->Ptr);
  if ( Ptr_high )
    wil::details::WilApi_RecordFeatureUsage(
      (wil::details *)v6,
      (unsigned int)v7[1].Ptr,
      Ptr_high,
      (unsigned int)a4,
      v10);
  if ( !LODWORD(v7[2].Ptr) && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    a5 = &SRWLock;
    if ( !qword_1800443B0 )
    {
      v9 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_1800443B0 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v9 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v9(&qword_1800443B0, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&a5);
  }
}

```

## disassembly

```asm
0x18002cbe4  mov     [rsp+arg_0], rbx
0x18002cbe9  mov     [rsp+arg_8], rsi
0x18002cbee  push    rdi; char *
0x18002cbef  sub     rsp, 20h
0x18002cbf3  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18002cbfa  mov     rsi, r9
0x18002cbfd  mov     edi, ecx
0x18002cbff  test    rax, rax
0x18002cc02  jz      short loc_18002CC1D
0x18002cc04  test    edx, edx
0x18002cc06  jz      short loc_18002CC12
0x18002cc08  lea     r8d, [rdx-64h]
0x18002cc0c  cmp     r8d, 31h ; '1'
0x18002cc10  ja      short loc_18002CC1D
0x18002cc12  mov     r8d, 1
0x18002cc18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc1d  mov     rbx, [rsp+28h+arg_20]
0x18002cc22  cmp     dword ptr [rbx], 0
0x18002cc25  jz      short loc_18002CC38
0x18002cc27  mov     r8, rsi; struct wil_details_FeatureReportingCache *
0x18002cc2a  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18002cc31  mov     edx, edi; unsigned int
0x18002cc33  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18002cc38  mov     r8d, [rbx+4]; unsigned int
0x18002cc3c  test    r8d, r8d
0x18002cc3f  jz      short loc_18002CC4B
0x18002cc41  mov     edx, [rbx+8]; unsigned int
0x18002cc44  mov     ecx, edi; this
0x18002cc46  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18002cc4b  cmp     dword ptr [rbx+10h], 0
0x18002cc4f  jnz     short loc_18002CCC4
0x18002cc51  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18002cc57  test    eax, eax
0x18002cc59  jz      short loc_18002CCC4
0x18002cc5b  lea     rbx, SRWLock
0x18002cc62  mov     rcx, rbx; SRWLock
0x18002cc65  call    cs:__imp_AcquireSRWLockExclusive
0x18002cc6c  nop     dword ptr [rax+rax+00h]
0x18002cc71  cmp     cs:qword_1800443B0, 0
0x18002cc79  mov     [rsp+28h+arg_20], rbx
0x18002cc7e  jnz     short loc_18002CCBA
0x18002cc80  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18002cc87  mov     cs:qword_1800443B0, 0
0x18002cc92  test    rax, rax
0x18002cc95  jnz     short loc_18002CCA3
0x18002cc97  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18002cc9e  test    rax, rax
0x18002cca1  jz      short loc_18002CCBA
0x18002cca3  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002cca7  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18002ccae  lea     rcx, qword_1800443B0
0x18002ccb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ccba  lea     rcx, [rsp+28h+arg_20]
0x18002ccbf  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002ccc4  mov     rbx, [rsp+28h+arg_0]
0x18002ccc9  mov     rsi, [rsp+28h+arg_8]
0x18002ccce  add     rsp, 20h
0x18002ccd2  pop     rdi
0x18002ccd3  retn
```
