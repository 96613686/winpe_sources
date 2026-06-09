# wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)

- ea: `0x18002abfc`
- end: `0x18002ace6`
- name: `?RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z`
- size: `234`
- prototype: `void __fastcall(__int64, __int64, __int64, struct wil_details_FeatureReportingCache *, RTL_SRWLOCK *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18002b280`

## callees

- `0x180022c9c`
- `0x1800232a8`
- `0x18002abfc`
- `0x18002c080`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ac7d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ac7d`

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
      (char *)&wil::details::g_enabledStateManager,
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
    if ( !qword_1800412F8 )
    {
      v9 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_1800412F8 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v9 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v9(&qword_1800412F8, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&a5);
  }
}

```

## disassembly

```asm
0x18002abfc  mov     [rsp+arg_0], rbx
0x18002ac01  mov     [rsp+arg_8], rsi
0x18002ac06  push    rdi; char *
0x18002ac07  sub     rsp, 20h
0x18002ac0b  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18002ac12  mov     rsi, r9
0x18002ac15  mov     edi, ecx
0x18002ac17  test    rax, rax
0x18002ac1a  jz      short loc_18002AC35
0x18002ac1c  test    edx, edx
0x18002ac1e  jz      short loc_18002AC2A
0x18002ac20  lea     r8d, [rdx-64h]
0x18002ac24  cmp     r8d, 31h ; '1'
0x18002ac28  ja      short loc_18002AC35
0x18002ac2a  mov     r8d, 1
0x18002ac30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac35  mov     rbx, [rsp+28h+arg_20]
0x18002ac3a  cmp     dword ptr [rbx], 0
0x18002ac3d  jz      short loc_18002AC50
0x18002ac3f  mov     r8, rsi; struct wil_details_FeatureReportingCache *
0x18002ac42  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18002ac49  mov     edx, edi; unsigned int
0x18002ac4b  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18002ac50  mov     r8d, [rbx+4]; unsigned int
0x18002ac54  test    r8d, r8d
0x18002ac57  jz      short loc_18002AC63
0x18002ac59  mov     edx, [rbx+8]; unsigned int
0x18002ac5c  mov     ecx, edi; this
0x18002ac5e  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18002ac63  cmp     dword ptr [rbx+10h], 0
0x18002ac67  jnz     short loc_18002ACD6
0x18002ac69  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18002ac6f  test    eax, eax
0x18002ac71  jz      short loc_18002ACD6
0x18002ac73  lea     rbx, SRWLock
0x18002ac7a  mov     rcx, rbx; SRWLock
0x18002ac7d  call    cs:__imp_AcquireSRWLockExclusive
0x18002ac83  cmp     cs:qword_1800412F8, 0
0x18002ac8b  mov     [rsp+28h+arg_20], rbx
0x18002ac90  jnz     short loc_18002ACCC
0x18002ac92  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18002ac99  mov     cs:qword_1800412F8, 0
0x18002aca4  test    rax, rax
0x18002aca7  jnz     short loc_18002ACB5
0x18002aca9  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18002acb0  test    rax, rax
0x18002acb3  jz      short loc_18002ACCC
0x18002acb5  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002acb9  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18002acc0  lea     rcx, qword_1800412F8
0x18002acc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002accc  lea     rcx, [rsp+28h+arg_20]
0x18002acd1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002acd6  mov     rbx, [rsp+28h+arg_0]
0x18002acdb  mov     rsi, [rsp+28h+arg_8]
0x18002ace0  add     rsp, 20h
0x18002ace4  pop     rdi
0x18002ace5  retn
```
