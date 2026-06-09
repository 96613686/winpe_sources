# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000f3b4`
- end: `0x18000f48d`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x1800104b0`

## callees

- `0x18000a0e0`
- `0x18000ad50`
- `0x18000ca00`
- `0x18000dc28`
- `0x18000f3b4`
- `0x18000f494`
- `0x18000f594`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f40f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f455`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f40f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f455`

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
0x18000f3b4  mov     [rsp+arg_8], rbx
0x18000f3b9  mov     [rsp+arg_10], rbp
0x18000f3be  push    rsi
0x18000f3bf  push    rdi
0x18000f3c0  push    r14
0x18000f3c2  sub     rsp, 20h
0x18000f3c6  cmp     byte ptr [rcx], 0
0x18000f3c9  mov     rbp, r9
0x18000f3cc  mov     ebx, r8d
0x18000f3cf  mov     r14d, edx
0x18000f3d2  mov     rdi, rcx
0x18000f3d5  jz      loc_18000F47A
0x18000f3db  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000f3e0  test    al, al
0x18000f3e2  jz      loc_18000F47A
0x18000f3e8  mov     rsi, [rdi+18h]
0x18000f3ec  cmp     ebx, 0FEh
0x18000f3f2  jz      short loc_18000F43D
0x18000f3f4  cmp     ebx, 0C8h
0x18000f3fa  jb      short loc_18000F40C
0x18000f3fc  cmp     ebx, 100h
0x18000f402  jl      short loc_18000F47A
0x18000f404  cmp     ebx, 200h
0x18000f40a  jnb     short loc_18000F47A
0x18000f40c  mov     rcx, rsi; SRWLock
0x18000f40f  call    cs:__imp_AcquireSRWLockExclusive
0x18000f415  mov     r9, rbp
0x18000f418  mov     [rsp+38h+arg_0], rsi
0x18000f41d  mov     r8d, ebx
0x18000f420  mov     edx, r14d
0x18000f423  mov     rcx, rsi
0x18000f426  call    ?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000f42b  lea     rcx, [rsp+38h+arg_0]
0x18000f430  mov     bl, al
0x18000f432  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000f437  test    bl, bl
0x18000f439  jz      short loc_18000F47A
0x18000f43b  jmp     short loc_18000F445
0x18000f43d  mov     rcx, rsi; this
0x18000f440  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000f445  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000f44a  test    al, al
0x18000f44c  jnz     short loc_18000F47A
0x18000f44e  lea     rbx, [rdi+20h]
0x18000f452  mov     rcx, rbx; SRWLock
0x18000f455  call    cs:__imp_AcquireSRWLockExclusive
0x18000f45b  lea     rdx, [rdi+41h]
0x18000f45f  mov     [rsp+38h+arg_0], rbx
0x18000f464  lea     rcx, [rdi+30h]
0x18000f468  mov     r8, rdi
0x18000f46b  call    ??$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)
0x18000f470  lea     rcx, [rsp+38h+arg_0]
0x18000f475  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000f47a  mov     rbx, [rsp+38h+arg_8]
0x18000f47f  mov     rbp, [rsp+38h+arg_10]
0x18000f484  add     rsp, 20h
0x18000f488  pop     r14
0x18000f48a  pop     rdi
0x18000f48b  pop     rsi
0x18000f48c  retn
```
