# wil::details::FeatureImpl<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::GetCachedFeatureEnabledState(void)

- ea: `0x1800082f0`
- end: `0x180008430`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a738`
- `0x18000c444`

## callees

- `0x1800047ac`
- `0x180007f30`
- `0x1800082f0`
- `0x180008954`
- `0x18000c63c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800083ae`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800083ae`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_PrintIppPsaStabilityFixes_2505__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_PrintIppPsaStabilityFixes_2505__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::GetCurrentFeatureEnabledState(
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
             (volatile signed __int32 *)Feature_PrintIppPsaStabilityFixes_2505__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_180022304
        || (v14[0] = 3,
            v14[1] = Feature_PrintIppPsaStabilityFixes_2505__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180022338, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_PrintIppPsaStabilityFixes_2505__descriptor, 0xFFFFFFFB);
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
0x1800082f0  mov     [rsp+arg_10], rbx
0x1800082f5  mov     [rsp+arg_18], rbp
0x1800082fa  mov     [rsp+arg_0], rcx
0x1800082ff  push    rsi
0x180008300  push    rdi
0x180008301  push    r14
0x180008303  sub     rsp, 30h
0x180008307  mov     rsi, cs:Feature_PrintIppPsaStabilityFixes_2505__descriptor
0x18000830e  mov     rdi, rdx
0x180008311  mov     qword ptr [rdx], 0
0x180008318  mov     eax, [rsi]
0x18000831a  mov     [rdx], eax
0x18000831c  and     eax, 6
0x18000831f  cmp     al, 6
0x180008321  jz      loc_180008419
0x180008327  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000832c  lea     r8, [rsp+48h+arg_0]
0x180008331  mov     dword ptr [rsp+48h+arg_0], 0
0x180008339  lea     rdx, [rsp+48h+arg_8]
0x18000833e  mov     ebp, eax
0x180008340  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::GetCurrentFeatureEnabledState(int *)
0x180008345  mov     eax, [rdi]
0x180008347  mov     rbx, [rsp+48h+arg_8]
0x18000834c  cmp     dword ptr [rsp+48h+arg_0], 0
0x180008351  mov     edx, eax
0x180008353  mov     [rdi], eax
0x180008355  mov     ecx, eax
0x180008357  jz      short loc_180008372
0x180008359  test    dl, 2
0x18000835c  jnz     short loc_180008372
0x18000835e  and     ecx, 0FFFFF63Eh
0x180008364  mov     eax, ebx
0x180008366  and     eax, 9C1h
0x18000836b  or      ecx, eax
0x18000836d  or      ecx, 2
0x180008370  mov     [rdi], ecx
0x180008372  mov     r8d, edx
0x180008375  and     r8d, 4
0x180008379  jnz     short loc_18000838D
0x18000837b  btr     ecx, 0Ah
0x18000837f  mov     eax, ebx
0x180008381  and     eax, 400h
0x180008386  or      ecx, eax
0x180008388  or      ecx, 4
0x18000838b  mov     [rdi], ecx
0x18000838d  mov     eax, edx
0x18000838f  lock cmpxchg [rsi], ecx
0x180008393  jnz     short loc_18000834C
0x180008395  test    r8d, r8d
0x180008398  jnz     short loc_180008404
0x18000839a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800083a0  test    eax, eax
0x1800083a2  jz      short loc_180008404
0x1800083a4  lea     r14, SRWLock
0x1800083ab  mov     rcx, r14; SRWLock
0x1800083ae  call    cs:__imp_AcquireSRWLockExclusive
0x1800083b5  nop     dword ptr [rax+rax+00h]
0x1800083ba  mov     eax, cs:dword_180022304
0x1800083c0  mov     [rsp+48h+arg_8], r14
0x1800083c5  test    ebp, ebp
0x1800083c7  jz      short loc_1800083F6
0x1800083c9  cmp     ebp, eax
0x1800083cb  jnz     short loc_1800083F6
0x1800083cd  mov     r8d, 10h; unsigned __int64
0x1800083d3  mov     [rsp+48h+var_28], 3
0x1800083dc  lea     rdx, [rsp+48h+var_28]; void *
0x1800083e1  mov     [rsp+48h+var_20], rsi
0x1800083e6  lea     rcx, qword_180022338; this
0x1800083ed  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800083f2  test    al, al
0x1800083f4  jnz     short loc_1800083FA
0x1800083f6  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800083fa  lea     rcx, [rsp+48h+arg_8]
0x1800083ff  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180008404  mov     eax, [rdi]
0x180008406  test    al, 2
0x180008408  jnz     short loc_180008419
0x18000840a  and     eax, 0FFFFF63Eh
0x18000840f  and     ebx, 9C1h
0x180008415  or      eax, ebx
0x180008417  mov     [rdi], eax
0x180008419  mov     rbx, [rsp+48h+arg_10]
0x18000841e  mov     rax, rdi
0x180008421  mov     rbp, [rsp+48h+arg_18]
0x180008426  add     rsp, 30h
0x18000842a  pop     r14
0x18000842c  pop     rdi
0x18000842d  pop     rsi
0x18000842e  retn
```
