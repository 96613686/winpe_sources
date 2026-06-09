# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::GetCachedFeatureEnabledState(void)

- ea: `0x180054628`
- end: `0x180054768`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180057290`
- `0x180057de8`

## callees

- `0x180032698`
- `0x180033f2c`
- `0x18003b8cc`
- `0x180054628`
- `0x180054e20`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x1800546e6`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800546e6`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::GetCachedFeatureEnabledState(
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
  _QWORD Source[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details *v15; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v16; // [rsp+58h] [rbp+10h] BYREF

  v15 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Servicing_VBScript_Enhanced_Logging__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_VBScript_Enhanced_Logging__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::GetCurrentFeatureEnabledState(
      v6,
      &v16,
      &v15);
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
      v7 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_Servicing_VBScript_Enhanced_Logging__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_18009386C
        || (Source[0] = 3,
            Source[1] = Feature_Servicing_VBScript_Enhanced_Logging__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800938A0, Source, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Servicing_VBScript_Enhanced_Logging__descriptor, 0xFFFFFFFB);
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
0x180054628  mov     [rsp+arg_10], rbx
0x18005462d  mov     [rsp+arg_18], rbp
0x180054632  mov     [rsp+arg_0], rcx
0x180054637  push    rsi
0x180054638  push    rdi
0x180054639  push    r14
0x18005463b  sub     rsp, 30h
0x18005463f  mov     rsi, cs:Feature_Servicing_VBScript_Enhanced_Logging__descriptor
0x180054646  mov     rdi, rdx
0x180054649  mov     qword ptr [rdx], 0
0x180054650  mov     eax, [rsi]
0x180054652  mov     [rdx], eax
0x180054654  and     eax, 6
0x180054657  cmp     al, 6
0x180054659  jz      loc_180054751
0x18005465f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180054664  lea     r8, [rsp+48h+arg_0]
0x180054669  mov     dword ptr [rsp+48h+arg_0], 0
0x180054671  lea     rdx, [rsp+48h+arg_8]
0x180054676  mov     ebp, eax
0x180054678  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::GetCurrentFeatureEnabledState(int *)
0x18005467d  mov     eax, [rdi]
0x18005467f  mov     rbx, [rsp+48h+arg_8]
0x180054684  cmp     dword ptr [rsp+48h+arg_0], 0
0x180054689  mov     edx, eax
0x18005468b  mov     [rdi], eax
0x18005468d  mov     ecx, eax
0x18005468f  jz      short loc_1800546AA
0x180054691  test    dl, 2
0x180054694  jnz     short loc_1800546AA
0x180054696  and     ecx, 0FFFFF63Eh
0x18005469c  mov     eax, ebx
0x18005469e  and     eax, 9C1h
0x1800546a3  or      ecx, eax
0x1800546a5  or      ecx, 2
0x1800546a8  mov     [rdi], ecx
0x1800546aa  mov     r8d, edx
0x1800546ad  and     r8d, 4
0x1800546b1  jnz     short loc_1800546C5
0x1800546b3  btr     ecx, 0Ah
0x1800546b7  mov     eax, ebx
0x1800546b9  and     eax, 400h
0x1800546be  or      ecx, eax
0x1800546c0  or      ecx, 4
0x1800546c3  mov     [rdi], ecx
0x1800546c5  mov     eax, edx
0x1800546c7  lock cmpxchg [rsi], ecx
0x1800546cb  jnz     short loc_180054684
0x1800546cd  test    r8d, r8d
0x1800546d0  jnz     short loc_18005473C
0x1800546d2  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800546d8  test    eax, eax
0x1800546da  jz      short loc_18005473C
0x1800546dc  lea     r14, SRWLock
0x1800546e3  mov     rcx, r14; SRWLock
0x1800546e6  call    cs:__imp_AcquireSRWLockExclusive
0x1800546ed  nop     dword ptr [rax+rax+00h]
0x1800546f2  mov     eax, cs:dword_18009386C
0x1800546f8  mov     [rsp+48h+arg_8], r14
0x1800546fd  test    ebp, ebp
0x1800546ff  jz      short loc_18005472E
0x180054701  cmp     ebp, eax
0x180054703  jnz     short loc_18005472E
0x180054705  mov     r8d, 10h; SourceSize
0x18005470b  mov     [rsp+48h+Source], 3
0x180054714  lea     rdx, [rsp+48h+Source]; Source
0x180054719  mov     [rsp+48h+var_20], rsi
0x18005471e  lea     rcx, qword_1800938A0; this
0x180054725  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18005472a  test    al, al
0x18005472c  jnz     short loc_180054732
0x18005472e  lock and dword ptr [rsi], 0FFFFFFFBh
0x180054732  lea     rcx, [rsp+48h+arg_8]
0x180054737  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18005473c  mov     eax, [rdi]
0x18005473e  test    al, 2
0x180054740  jnz     short loc_180054751
0x180054742  and     eax, 0FFFFF63Eh
0x180054747  and     ebx, 9C1h
0x18005474d  or      eax, ebx
0x18005474f  mov     [rdi], eax
0x180054751  mov     rbx, [rsp+48h+arg_10]
0x180054756  mov     rax, rdi
0x180054759  mov     rbp, [rsp+48h+arg_18]
0x18005475e  add     rsp, 30h
0x180054762  pop     r14
0x180054764  pop     rdi
0x180054765  pop     rsi
0x180054766  retn
```
