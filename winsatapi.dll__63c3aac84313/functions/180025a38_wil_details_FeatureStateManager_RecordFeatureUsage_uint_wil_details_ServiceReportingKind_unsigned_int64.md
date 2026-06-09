# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180025a38`
- end: `0x180025ab7`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `127`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180026c90`

## callees

- `0x18000f37c`
- `0x1800126f0`
- `0x180021be4`
- `0x180023d58`
- `0x180025984`
- `0x180025a38`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025a88`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025a88`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        _BYTE *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  wil *v8; // rcx
  RTL_SRWLOCK *v9; // [rsp+60h] [rbp+8h] BYREF

  if ( *a1
    && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1)
    && wil::details_abi::FeatureStateData::RecordFeatureUsage(
         *((wil::details_abi::FeatureStateData **)a1 + 3),
         a2,
         a3,
         a4)
    && !wil::ProcessShutdownInProgress(v8) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)a1 + 4);
    v9 = (RTL_SRWLOCK *)(a1 + 32);
    wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>((_QWORD *)a1 + 6, a1 + 65, a1);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  }
}

```

## disassembly

```asm
0x180025a38  push    rbx
0x180025a3a  push    rbp
0x180025a3b  push    rsi
0x180025a3c  push    rdi
0x180025a3d  sub     rsp, 38h
0x180025a41  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x180025a4a  mov     rbx, r9
0x180025a4d  mov     esi, r8d
0x180025a50  mov     ebp, edx
0x180025a52  mov     rdi, rcx
0x180025a55  cmp     byte ptr [rcx], 0
0x180025a58  jz      short loc_180025AAE
0x180025a5a  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180025a5f  test    al, al
0x180025a61  jz      short loc_180025AAE
0x180025a63  mov     r9, rbx
0x180025a66  mov     r8d, esi
0x180025a69  mov     edx, ebp
0x180025a6b  mov     rcx, [rdi+18h]
0x180025a6f  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180025a74  test    al, al
0x180025a76  jz      short loc_180025AAE
0x180025a78  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180025a7d  test    al, al
0x180025a7f  jnz     short loc_180025AAE
0x180025a81  lea     rbx, [rdi+20h]
0x180025a85  mov     rcx, rbx; SRWLock
0x180025a88  call    cs:__imp_AcquireSRWLockExclusive
0x180025a8e  mov     [rsp+58h+arg_0], rbx
0x180025a93  lea     rdx, [rdi+41h]
0x180025a97  lea     rcx, [rdi+30h]
0x180025a9b  mov     r8, rdi
0x180025a9e  call    ??$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)
0x180025aa3  lea     rcx, [rsp+58h+arg_0]
0x180025aa8  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180025aad  nop
0x180025aae  add     rsp, 38h
0x180025ab2  pop     rdi
0x180025ab3  pop     rsi
0x180025ab4  pop     rbp
0x180025ab5  pop     rbx
0x180025ab6  retn
```
