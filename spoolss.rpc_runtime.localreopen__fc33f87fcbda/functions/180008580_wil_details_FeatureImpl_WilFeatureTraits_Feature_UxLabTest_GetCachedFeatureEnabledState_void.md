# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180008580`
- end: `0x1800086c0`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a860`

## callees

- `0x1800047ac`
- `0x180007f30`
- `0x180008580`
- `0x180008ae0`
- `0x18000c63c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000863e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000863e`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebp
  __int64 v6; // rcx
  signed __int32 v7; // eax
  __int16 v8; // bx
  bool v9; // zf
  signed __int32 v10; // edx
  unsigned int v11; // ecx
  int v12; // r8d
  _QWORD v14[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details *v15; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v16; // [rsp+58h] [rbp+10h] BYREF

  v15 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_UxLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UxLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
    v7 = *(_DWORD *)a2;
    v8 = (__int16)v16;
    do
    {
      v9 = (_DWORD)v15 == 0;
      v10 = v7;
      *(_DWORD *)a2 = v7;
      v11 = v7;
      if ( !v9 && (v7 & 2) == 0 )
      {
        v11 = v8 & 0x9C1 | v7 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v11;
      }
      v12 = v7 & 4;
      if ( (v7 & 4) == 0 )
      {
        v11 = v8 & 0x400 | v11 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v11;
      }
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UxLabTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_180022304
        || (v14[0] = 3,
            v14[1] = Feature_UxLabTest__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180022338, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_UxLabTest__descriptor, 0xFFFFFFFB);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
    }
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180008580  mov     [rsp+arg_10], rbx
0x180008585  mov     [rsp+arg_18], rbp
0x18000858a  mov     [rsp+arg_0], rcx
0x18000858f  push    rsi
0x180008590  push    rdi
0x180008591  push    r14
0x180008593  sub     rsp, 30h
0x180008597  mov     rsi, cs:Feature_UxLabTest__descriptor
0x18000859e  mov     rdi, rdx
0x1800085a1  mov     qword ptr [rdx], 0
0x1800085a8  mov     eax, [rsi]
0x1800085aa  mov     [rdx], eax
0x1800085ac  and     eax, 6
0x1800085af  cmp     al, 6
0x1800085b1  jz      loc_1800086A9
0x1800085b7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800085bc  lea     r8, [rsp+48h+arg_0]
0x1800085c1  mov     dword ptr [rsp+48h+arg_0], 0
0x1800085c9  lea     rdx, [rsp+48h+arg_8]
0x1800085ce  mov     ebp, eax
0x1800085d0  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest>::GetCurrentFeatureEnabledState(int *)
0x1800085d5  mov     eax, [rdi]
0x1800085d7  mov     rbx, [rsp+48h+arg_8]
0x1800085dc  cmp     dword ptr [rsp+48h+arg_0], 0
0x1800085e1  mov     edx, eax
0x1800085e3  mov     [rdi], eax
0x1800085e5  mov     ecx, eax
0x1800085e7  jz      short loc_180008602
0x1800085e9  test    dl, 2
0x1800085ec  jnz     short loc_180008602
0x1800085ee  and     ecx, 0FFFFF63Eh
0x1800085f4  mov     eax, ebx
0x1800085f6  and     eax, 9C1h
0x1800085fb  or      ecx, eax
0x1800085fd  or      ecx, 2
0x180008600  mov     [rdi], ecx
0x180008602  mov     r8d, edx
0x180008605  and     r8d, 4
0x180008609  jnz     short loc_18000861D
0x18000860b  btr     ecx, 0Ah
0x18000860f  mov     eax, ebx
0x180008611  and     eax, 400h
0x180008616  or      ecx, eax
0x180008618  or      ecx, 4
0x18000861b  mov     [rdi], ecx
0x18000861d  mov     eax, edx
0x18000861f  lock cmpxchg [rsi], ecx
0x180008623  jnz     short loc_1800085DC
0x180008625  test    r8d, r8d
0x180008628  jnz     short loc_180008694
0x18000862a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180008630  test    eax, eax
0x180008632  jz      short loc_180008694
0x180008634  lea     r14, SRWLock
0x18000863b  mov     rcx, r14; SRWLock
0x18000863e  call    cs:__imp_AcquireSRWLockExclusive
0x180008645  nop     dword ptr [rax+rax+00h]
0x18000864a  mov     eax, cs:dword_180022304
0x180008650  mov     [rsp+48h+arg_8], r14
0x180008655  test    ebp, ebp
0x180008657  jz      short loc_180008686
0x180008659  cmp     ebp, eax
0x18000865b  jnz     short loc_180008686
0x18000865d  mov     r8d, 10h; unsigned __int64
0x180008663  mov     [rsp+48h+var_28], 3
0x18000866c  lea     rdx, [rsp+48h+var_28]; void *
0x180008671  mov     [rsp+48h+var_20], rsi
0x180008676  lea     rcx, qword_180022338; this
0x18000867d  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180008682  test    al, al
0x180008684  jnz     short loc_18000868A
0x180008686  lock and dword ptr [rsi], 0FFFFFFFBh
0x18000868a  lea     rcx, [rsp+48h+arg_8]
0x18000868f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180008694  mov     eax, [rdi]
0x180008696  test    al, 2
0x180008698  jnz     short loc_1800086A9
0x18000869a  and     eax, 0FFFFF63Eh
0x18000869f  and     ebx, 9C1h
0x1800086a5  or      eax, ebx
0x1800086a7  mov     [rdi], eax
0x1800086a9  mov     rbx, [rsp+48h+arg_10]
0x1800086ae  mov     rax, rdi
0x1800086b1  mov     rbp, [rsp+48h+arg_18]
0x1800086b6  add     rsp, 30h
0x1800086ba  pop     r14
0x1800086bc  pop     rdi
0x1800086bd  pop     rsi
0x1800086be  retn
```
