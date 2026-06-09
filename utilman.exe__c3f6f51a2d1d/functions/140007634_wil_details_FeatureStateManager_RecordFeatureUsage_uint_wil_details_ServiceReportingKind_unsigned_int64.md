# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x140007634`
- end: `0x14000771f`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x140009150`

## callees

- `0x1400036b0`
- `0x14000483c`
- `0x1400053a0`
- `0x140007274`
- `0x140007634`
- `0x140007728`
- `0x140007850`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x140007693`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400076df`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140007693`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400076df`

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
0x140007634  mov     [rsp+arg_8], rbx
0x140007639  mov     [rsp+arg_10], rbp
0x14000763e  push    rsi
0x14000763f  push    rdi
0x140007640  push    r14
0x140007642  sub     rsp, 20h
0x140007646  mov     rbp, r9
0x140007649  mov     ebx, r8d
0x14000764c  mov     r14d, edx
0x14000764f  mov     rdi, rcx
0x140007652  cmp     byte ptr [rcx], 0
0x140007655  jz      loc_14000770B
0x14000765b  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x140007660  test    al, al
0x140007662  jz      loc_14000770B
0x140007668  mov     rsi, [rdi+18h]
0x14000766c  cmp     ebx, 0FEh
0x140007672  jz      short loc_1400076C7
0x140007674  cmp     ebx, 0C8h
0x14000767a  jb      short loc_140007690
0x14000767c  cmp     ebx, 100h
0x140007682  jl      loc_14000770B
0x140007688  cmp     ebx, 200h
0x14000768e  jnb     short loc_14000770B
0x140007690  mov     rcx, rsi; SRWLock
0x140007693  call    cs:__imp_AcquireSRWLockExclusive
0x14000769a  nop     dword ptr [rax+rax+00h]
0x14000769f  mov     [rsp+38h+arg_0], rsi
0x1400076a4  mov     r9, rbp
0x1400076a7  mov     r8d, ebx
0x1400076aa  mov     edx, r14d
0x1400076ad  mov     rcx, rsi
0x1400076b0  call    ?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1400076b5  mov     bl, al
0x1400076b7  lea     rcx, [rsp+38h+arg_0]
0x1400076bc  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1400076c1  test    bl, bl
0x1400076c3  jz      short loc_14000770B
0x1400076c5  jmp     short loc_1400076CF
0x1400076c7  mov     rcx, rsi; this
0x1400076ca  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1400076cf  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1400076d4  test    al, al
0x1400076d6  jnz     short loc_14000770B
0x1400076d8  lea     rbx, [rdi+20h]
0x1400076dc  mov     rcx, rbx; SRWLock
0x1400076df  call    cs:__imp_AcquireSRWLockExclusive
0x1400076e6  nop     dword ptr [rax+rax+00h]
0x1400076eb  mov     [rsp+38h+arg_0], rbx
0x1400076f0  lea     rdx, [rdi+41h]
0x1400076f4  lea     rcx, [rdi+30h]
0x1400076f8  mov     r8, rdi
0x1400076fb  call    ??$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)
0x140007700  lea     rcx, [rsp+38h+arg_0]
0x140007705  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000770a  nop
0x14000770b  mov     rbx, [rsp+38h+arg_8]
0x140007710  mov     rbp, [rsp+38h+arg_10]
0x140007715  add     rsp, 20h
0x140007719  pop     r14
0x14000771b  pop     rdi
0x14000771c  pop     rsi
0x14000771d  retn
```
