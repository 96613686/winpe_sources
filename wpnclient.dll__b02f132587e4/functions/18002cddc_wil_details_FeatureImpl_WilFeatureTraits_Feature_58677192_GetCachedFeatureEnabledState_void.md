# wil::details::FeatureImpl<__WilFeatureTraits_Feature_58677192>::GetCachedFeatureEnabledState(void)

- ea: `0x18002cddc`
- end: `0x18002cf15`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_58677192@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002de7c`

## callees

- `0x18001f5f0`
- `0x180029c18`
- `0x18002c34c`
- `0x18002cddc`
- `0x18002d05c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ce9a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ce9a`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_58677192>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_58677192__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_58677192__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_58677192>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_58677192__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_180044A54
        || (v14[0] = 3,
            v14[1] = Feature_58677192__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180044A78, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_58677192__descriptor, 0xFFFFFFFB);
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
0x18002cddc  mov     [rsp+arg_10], rbx
0x18002cde1  mov     [rsp+arg_18], rbp
0x18002cde6  mov     [rsp+arg_0], rcx
0x18002cdeb  push    rsi
0x18002cdec  push    rdi
0x18002cded  push    r14
0x18002cdef  sub     rsp, 30h
0x18002cdf3  mov     rsi, cs:Feature_58677192__descriptor
0x18002cdfa  mov     rdi, rdx
0x18002cdfd  mov     qword ptr [rdx], 0
0x18002ce04  mov     eax, [rsi]
0x18002ce06  mov     [rdx], eax
0x18002ce08  and     eax, 6
0x18002ce0b  cmp     al, 6
0x18002ce0d  jz      loc_18002CEFF
0x18002ce13  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002ce18  lea     r8, [rsp+48h+arg_0]
0x18002ce1d  mov     dword ptr [rsp+48h+arg_0], 0
0x18002ce25  lea     rdx, [rsp+48h+arg_8]
0x18002ce2a  mov     ebp, eax
0x18002ce2c  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_58677192@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58677192>::GetCurrentFeatureEnabledState(int *)
0x18002ce31  mov     eax, [rdi]
0x18002ce33  mov     rbx, [rsp+48h+arg_8]
0x18002ce38  cmp     dword ptr [rsp+48h+arg_0], 0
0x18002ce3d  mov     edx, eax
0x18002ce3f  mov     [rdi], eax
0x18002ce41  mov     ecx, eax
0x18002ce43  jz      short loc_18002CE5E
0x18002ce45  test    dl, 2
0x18002ce48  jnz     short loc_18002CE5E
0x18002ce4a  and     ecx, 0FFFFF63Eh
0x18002ce50  mov     eax, ebx
0x18002ce52  and     eax, 9C1h
0x18002ce57  or      ecx, eax
0x18002ce59  or      ecx, 2
0x18002ce5c  mov     [rdi], ecx
0x18002ce5e  mov     r8d, edx
0x18002ce61  and     r8d, 4
0x18002ce65  jnz     short loc_18002CE79
0x18002ce67  btr     ecx, 0Ah
0x18002ce6b  mov     eax, ebx
0x18002ce6d  and     eax, 400h
0x18002ce72  or      ecx, eax
0x18002ce74  or      ecx, 4
0x18002ce77  mov     [rdi], ecx
0x18002ce79  mov     eax, edx
0x18002ce7b  lock cmpxchg [rsi], ecx
0x18002ce7f  jnz     short loc_18002CE38
0x18002ce81  test    r8d, r8d
0x18002ce84  jnz     short loc_18002CEEA
0x18002ce86  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18002ce8c  test    eax, eax
0x18002ce8e  jz      short loc_18002CEEA
0x18002ce90  lea     r14, SRWLock
0x18002ce97  mov     rcx, r14; SRWLock
0x18002ce9a  call    cs:__imp_AcquireSRWLockExclusive
0x18002cea0  mov     eax, cs:dword_180044A54
0x18002cea6  mov     [rsp+48h+arg_8], r14
0x18002ceab  test    ebp, ebp
0x18002cead  jz      short loc_18002CEDC
0x18002ceaf  cmp     ebp, eax
0x18002ceb1  jnz     short loc_18002CEDC
0x18002ceb3  mov     r8d, 10h; unsigned __int64
0x18002ceb9  mov     [rsp+48h+var_28], 3
0x18002cec2  lea     rdx, [rsp+48h+var_28]; void *
0x18002cec7  mov     [rsp+48h+var_20], rsi
0x18002cecc  lea     rcx, qword_180044A78; this
0x18002ced3  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18002ced8  test    al, al
0x18002ceda  jnz     short loc_18002CEE0
0x18002cedc  lock and dword ptr [rsi], 0FFFFFFFBh
0x18002cee0  lea     rcx, [rsp+48h+arg_8]
0x18002cee5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002ceea  mov     eax, [rdi]
0x18002ceec  test    al, 2
0x18002ceee  jnz     short loc_18002CEFF
0x18002cef0  and     eax, 0FFFFF63Eh
0x18002cef5  and     ebx, 9C1h
0x18002cefb  or      eax, ebx
0x18002cefd  mov     [rdi], eax
0x18002ceff  mov     rbx, [rsp+48h+arg_10]
0x18002cf04  mov     rax, rdi
0x18002cf07  mov     rbp, [rsp+48h+arg_18]
0x18002cf0c  add     rsp, 30h
0x18002cf10  pop     r14
0x18002cf12  pop     rdi
0x18002cf13  pop     rsi
0x18002cf14  retn
```
