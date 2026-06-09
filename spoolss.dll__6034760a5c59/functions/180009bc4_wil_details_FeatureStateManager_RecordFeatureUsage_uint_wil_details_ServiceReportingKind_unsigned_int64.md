# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180009bc4`
- end: `0x180009c9e`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18000b5b0`

## callees

- `0x180002580`
- `0x180004490`
- `0x1800065fc`
- `0x180007a68`
- `0x180009bc4`
- `0x180009ca4`
- `0x180009dbc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009c1f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009c65`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009c1f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009c65`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        _BYTE *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  _BYTE *v8; // rsi
  char v9; // bl
  wil *v10; // rcx
  _BYTE *v11; // [rsp+40h] [rbp+8h] BYREF

  if ( *a1 && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1) )
  {
    v8 = (_BYTE *)*((_QWORD *)a1 + 3);
    if ( a3 == 254 )
    {
      wil::details_abi::FeatureStateData::RecordUsage(*((wil::details_abi::FeatureStateData **)a1 + 3));
LABEL_10:
      if ( !wil::ProcessShutdownInProgress(v10) )
      {
        AcquireSRWLockExclusive((PSRWLOCK)a1 + 4);
        v11 = a1 + 32;
        wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>((_QWORD *)a1 + 6, a1 + 65, a1);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
      }
      return;
    }
    if ( a3 < 0xC8 || (int)a3 >= 256 && a3 < 0x200 )
    {
      AcquireSRWLockExclusive(*((PSRWLOCK *)a1 + 3));
      v11 = v8;
      v9 = wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(v8, a2, a3, a4);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
      if ( v9 )
        goto LABEL_10;
    }
  }
}

```

## disassembly

```asm
0x180009bc4  mov     [rsp+arg_8], rbx
0x180009bc9  mov     [rsp+arg_10], rbp
0x180009bce  push    rsi
0x180009bcf  push    rdi
0x180009bd0  push    r14
0x180009bd2  sub     rsp, 20h
0x180009bd6  mov     rbp, r9
0x180009bd9  mov     ebx, r8d
0x180009bdc  mov     r14d, edx
0x180009bdf  mov     rdi, rcx
0x180009be2  cmp     byte ptr [rcx], 0
0x180009be5  jz      loc_180009C8B
0x180009beb  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180009bf0  test    al, al
0x180009bf2  jz      loc_180009C8B
0x180009bf8  mov     rsi, [rdi+18h]
0x180009bfc  cmp     ebx, 0FEh
0x180009c02  jz      short loc_180009C4D
0x180009c04  cmp     ebx, 0C8h
0x180009c0a  jb      short loc_180009C1C
0x180009c0c  cmp     ebx, 100h
0x180009c12  jl      short loc_180009C8B
0x180009c14  cmp     ebx, 200h
0x180009c1a  jnb     short loc_180009C8B
0x180009c1c  mov     rcx, rsi; SRWLock
0x180009c1f  call    cs:__imp_AcquireSRWLockExclusive
0x180009c25  mov     [rsp+38h+arg_0], rsi
0x180009c2a  mov     r9, rbp
0x180009c2d  mov     r8d, ebx
0x180009c30  mov     edx, r14d
0x180009c33  mov     rcx, rsi
0x180009c36  call    ?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180009c3b  mov     bl, al
0x180009c3d  lea     rcx, [rsp+38h+arg_0]
0x180009c42  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180009c47  test    bl, bl
0x180009c49  jz      short loc_180009C8B
0x180009c4b  jmp     short loc_180009C55
0x180009c4d  mov     rcx, rsi; this
0x180009c50  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180009c55  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180009c5a  test    al, al
0x180009c5c  jnz     short loc_180009C8B
0x180009c5e  lea     rbx, [rdi+20h]
0x180009c62  mov     rcx, rbx; SRWLock
0x180009c65  call    cs:__imp_AcquireSRWLockExclusive
0x180009c6b  mov     [rsp+38h+arg_0], rbx
0x180009c70  lea     rdx, [rdi+41h]
0x180009c74  lea     rcx, [rdi+30h]
0x180009c78  mov     r8, rdi
0x180009c7b  call    ??$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)
0x180009c80  lea     rcx, [rsp+38h+arg_0]
0x180009c85  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180009c8a  nop
0x180009c8b  mov     rbx, [rsp+38h+arg_8]
0x180009c90  mov     rbp, [rsp+38h+arg_10]
0x180009c95  add     rsp, 20h
0x180009c99  pop     r14
0x180009c9b  pop     rdi
0x180009c9c  pop     rsi
0x180009c9d  retn
```
