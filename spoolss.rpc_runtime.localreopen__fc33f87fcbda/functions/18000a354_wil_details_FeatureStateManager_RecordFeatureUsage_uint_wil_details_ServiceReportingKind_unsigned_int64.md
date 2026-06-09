# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000a354`
- end: `0x18000a43f`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18000bee0`

## callees

- `0x1800026e4`
- `0x1800047ac`
- `0x180006970`
- `0x180007ea0`
- `0x18000a354`
- `0x18000a448`
- `0x18000a570`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a3b3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a3ff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a3b3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a3ff`

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
0x18000a354  mov     [rsp+arg_8], rbx
0x18000a359  mov     [rsp+arg_10], rbp
0x18000a35e  push    rsi
0x18000a35f  push    rdi
0x18000a360  push    r14
0x18000a362  sub     rsp, 20h
0x18000a366  mov     rbp, r9
0x18000a369  mov     ebx, r8d
0x18000a36c  mov     r14d, edx
0x18000a36f  mov     rdi, rcx
0x18000a372  cmp     byte ptr [rcx], 0
0x18000a375  jz      loc_18000A42B
0x18000a37b  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000a380  test    al, al
0x18000a382  jz      loc_18000A42B
0x18000a388  mov     rsi, [rdi+18h]
0x18000a38c  cmp     ebx, 0FEh
0x18000a392  jz      short loc_18000A3E7
0x18000a394  cmp     ebx, 0C8h
0x18000a39a  jb      short loc_18000A3B0
0x18000a39c  cmp     ebx, 100h
0x18000a3a2  jl      loc_18000A42B
0x18000a3a8  cmp     ebx, 200h
0x18000a3ae  jnb     short loc_18000A42B
0x18000a3b0  mov     rcx, rsi; SRWLock
0x18000a3b3  call    cs:__imp_AcquireSRWLockExclusive
0x18000a3ba  nop     dword ptr [rax+rax+00h]
0x18000a3bf  mov     [rsp+38h+arg_0], rsi
0x18000a3c4  mov     r9, rbp
0x18000a3c7  mov     r8d, ebx
0x18000a3ca  mov     edx, r14d
0x18000a3cd  mov     rcx, rsi
0x18000a3d0  call    ?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000a3d5  mov     bl, al
0x18000a3d7  lea     rcx, [rsp+38h+arg_0]
0x18000a3dc  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000a3e1  test    bl, bl
0x18000a3e3  jz      short loc_18000A42B
0x18000a3e5  jmp     short loc_18000A3EF
0x18000a3e7  mov     rcx, rsi; this
0x18000a3ea  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000a3ef  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000a3f4  test    al, al
0x18000a3f6  jnz     short loc_18000A42B
0x18000a3f8  lea     rbx, [rdi+20h]
0x18000a3fc  mov     rcx, rbx; SRWLock
0x18000a3ff  call    cs:__imp_AcquireSRWLockExclusive
0x18000a406  nop     dword ptr [rax+rax+00h]
0x18000a40b  mov     [rsp+38h+arg_0], rbx
0x18000a410  lea     rdx, [rdi+41h]
0x18000a414  lea     rcx, [rdi+30h]
0x18000a418  mov     r8, rdi
0x18000a41b  call    ??$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)
0x18000a420  lea     rcx, [rsp+38h+arg_0]
0x18000a425  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000a42a  nop
0x18000a42b  mov     rbx, [rsp+38h+arg_8]
0x18000a430  mov     rbp, [rsp+38h+arg_10]
0x18000a435  add     rsp, 20h
0x18000a439  pop     r14
0x18000a43b  pop     rdi
0x18000a43c  pop     rsi
0x18000a43d  retn
```
