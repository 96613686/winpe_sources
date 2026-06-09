# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180005a90`
- end: `0x180005b05`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `117`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000a330`

## callees

- `0x180005a90`
- `0x180005e6c`
- `0x180006470`
- `0x18000af78`
- `0x18000b380`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005ad7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005ad7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005af5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005af5`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        _BYTE *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  wil *v8; // rcx

  if ( *a1
    && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1)
    && wil::details_abi::FeatureStateData::RecordFeatureUsage(*((_QWORD *)a1 + 3), a2, a3, a4)
    && !wil::ProcessShutdownInProgress(v8) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)a1 + 4);
    wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>((_QWORD *)a1 + 6, a1 + 65, a1);
    if ( a1 != (_BYTE *)-32LL )
      ReleaseSRWLockExclusive((PSRWLOCK)a1 + 4);
  }
}

```

## disassembly

```asm
0x180005a90  push    rbx
0x180005a92  push    rbp
0x180005a93  push    rsi
0x180005a94  push    rdi
0x180005a95  sub     rsp, 28h
0x180005a99  mov     rdi, r9
0x180005a9c  mov     esi, r8d
0x180005a9f  mov     ebp, edx
0x180005aa1  mov     rbx, rcx
0x180005aa4  cmp     byte ptr [rcx], 0
0x180005aa7  jz      short loc_180005AFC
0x180005aa9  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180005aae  test    al, al
0x180005ab0  jz      short loc_180005AFC
0x180005ab2  mov     r9, rdi
0x180005ab5  mov     r8d, esi
0x180005ab8  mov     edx, ebp
0x180005aba  mov     rcx, [rbx+18h]
0x180005abe  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180005ac3  test    al, al
0x180005ac5  jz      short loc_180005AFC
0x180005ac7  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180005acc  test    al, al
0x180005ace  jnz     short loc_180005AFC
0x180005ad0  lea     rdi, [rbx+20h]
0x180005ad4  mov     rcx, rdi; SRWLock
0x180005ad7  call    cs:__imp_AcquireSRWLockExclusive
0x180005add  lea     rdx, [rbx+41h]
0x180005ae1  lea     rcx, [rbx+30h]
0x180005ae5  mov     r8, rbx
0x180005ae8  call    ??$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)
0x180005aed  test    rdi, rdi
0x180005af0  jz      short loc_180005AFC
0x180005af2  mov     rcx, rdi; SRWLock
0x180005af5  call    cs:__imp_ReleaseSRWLockExclusive
0x180005afb  nop
0x180005afc  add     rsp, 28h
0x180005b00  pop     rdi
0x180005b01  pop     rsi
0x180005b02  pop     rbp
0x180005b03  pop     rbx
0x180005b04  retn
```
