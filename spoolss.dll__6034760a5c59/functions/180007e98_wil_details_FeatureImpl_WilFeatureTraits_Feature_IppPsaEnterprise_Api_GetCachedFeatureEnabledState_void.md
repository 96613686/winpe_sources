# wil::details::FeatureImpl<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::GetCachedFeatureEnabledState(void)

- ea: `0x180007e98`
- end: `0x180007fd1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_IppPsaEnterprise_Api@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009f60`

## callees

- `0x180004490`
- `0x180007af4`
- `0x180007e98`
- `0x18000838c`
- `0x18000bcac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007f56`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007f56`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_IppPsaEnterprise_Api__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_IppPsaEnterprise_Api__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_IppPsaEnterprise_Api__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_180021304
        || (v14[0] = 3,
            v14[1] = Feature_IppPsaEnterprise_Api__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180021328, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_IppPsaEnterprise_Api__descriptor, 0xFFFFFFFB);
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
0x180007e98  mov     [rsp+arg_10], rbx
0x180007e9d  mov     [rsp+arg_18], rbp
0x180007ea2  mov     [rsp+arg_0], rcx
0x180007ea7  push    rsi
0x180007ea8  push    rdi
0x180007ea9  push    r14
0x180007eab  sub     rsp, 30h
0x180007eaf  mov     rsi, cs:Feature_IppPsaEnterprise_Api__descriptor
0x180007eb6  mov     rdi, rdx
0x180007eb9  mov     qword ptr [rdx], 0
0x180007ec0  mov     eax, [rsi]
0x180007ec2  mov     [rdx], eax
0x180007ec4  and     eax, 6
0x180007ec7  cmp     al, 6
0x180007ec9  jz      loc_180007FBB
0x180007ecf  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180007ed4  lea     r8, [rsp+48h+arg_0]
0x180007ed9  mov     dword ptr [rsp+48h+arg_0], 0
0x180007ee1  lea     rdx, [rsp+48h+arg_8]
0x180007ee6  mov     ebp, eax
0x180007ee8  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_IppPsaEnterprise_Api@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::GetCurrentFeatureEnabledState(int *)
0x180007eed  mov     eax, [rdi]
0x180007eef  mov     rbx, [rsp+48h+arg_8]
0x180007ef4  cmp     dword ptr [rsp+48h+arg_0], 0
0x180007ef9  mov     edx, eax
0x180007efb  mov     [rdi], eax
0x180007efd  mov     ecx, eax
0x180007eff  jz      short loc_180007F1A
0x180007f01  test    dl, 2
0x180007f04  jnz     short loc_180007F1A
0x180007f06  and     ecx, 0FFFFF63Eh
0x180007f0c  mov     eax, ebx
0x180007f0e  and     eax, 9C1h
0x180007f13  or      ecx, eax
0x180007f15  or      ecx, 2
0x180007f18  mov     [rdi], ecx
0x180007f1a  mov     r8d, edx
0x180007f1d  and     r8d, 4
0x180007f21  jnz     short loc_180007F35
0x180007f23  btr     ecx, 0Ah
0x180007f27  mov     eax, ebx
0x180007f29  and     eax, 400h
0x180007f2e  or      ecx, eax
0x180007f30  or      ecx, 4
0x180007f33  mov     [rdi], ecx
0x180007f35  mov     eax, edx
0x180007f37  lock cmpxchg [rsi], ecx
0x180007f3b  jnz     short loc_180007EF4
0x180007f3d  test    r8d, r8d
0x180007f40  jnz     short loc_180007FA6
0x180007f42  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180007f48  test    eax, eax
0x180007f4a  jz      short loc_180007FA6
0x180007f4c  lea     r14, SRWLock
0x180007f53  mov     rcx, r14; SRWLock
0x180007f56  call    cs:__imp_AcquireSRWLockExclusive
0x180007f5c  mov     eax, cs:dword_180021304
0x180007f62  mov     [rsp+48h+arg_8], r14
0x180007f67  test    ebp, ebp
0x180007f69  jz      short loc_180007F98
0x180007f6b  cmp     ebp, eax
0x180007f6d  jnz     short loc_180007F98
0x180007f6f  mov     r8d, 10h; unsigned __int64
0x180007f75  mov     [rsp+48h+var_28], 3
0x180007f7e  lea     rdx, [rsp+48h+var_28]; void *
0x180007f83  mov     [rsp+48h+var_20], rsi
0x180007f88  lea     rcx, qword_180021328; this
0x180007f8f  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180007f94  test    al, al
0x180007f96  jnz     short loc_180007F9C
0x180007f98  lock and dword ptr [rsi], 0FFFFFFFBh
0x180007f9c  lea     rcx, [rsp+48h+arg_8]
0x180007fa1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180007fa6  mov     eax, [rdi]
0x180007fa8  test    al, 2
0x180007faa  jnz     short loc_180007FBB
0x180007fac  and     eax, 0FFFFF63Eh
0x180007fb1  and     ebx, 9C1h
0x180007fb7  or      eax, ebx
0x180007fb9  mov     [rdi], eax
0x180007fbb  mov     rbx, [rsp+48h+arg_10]
0x180007fc0  mov     rax, rdi
0x180007fc3  mov     rbp, [rsp+48h+arg_18]
0x180007fc8  add     rsp, 30h
0x180007fcc  pop     r14
0x180007fce  pop     rdi
0x180007fcf  pop     rsi
0x180007fd0  retn
```
