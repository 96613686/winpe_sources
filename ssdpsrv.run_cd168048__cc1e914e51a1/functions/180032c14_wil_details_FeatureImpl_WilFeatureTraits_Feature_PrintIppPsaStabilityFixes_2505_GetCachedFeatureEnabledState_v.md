# wil::details::FeatureImpl<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::GetCachedFeatureEnabledState(void)

- ea: `0x180032c14`
- end: `0x180032d54`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003396c`
- `0x180033be4`

## callees

- `0x180024d20`
- `0x18002b074`
- `0x18002e454`
- `0x180032c14`
- `0x180033054`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180032cd2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180032cd2`

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
        || v5 != dword_1800443A4
        || (v14[0] = 3,
            v14[1] = Feature_PrintIppPsaStabilityFixes_2505__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800443D8, v14, 0x10u)) )
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
0x180032c14  mov     [rsp+arg_10], rbx
0x180032c19  mov     [rsp+arg_18], rbp
0x180032c1e  mov     [rsp+arg_0], rcx
0x180032c23  push    rsi
0x180032c24  push    rdi
0x180032c25  push    r14
0x180032c27  sub     rsp, 30h
0x180032c2b  mov     rsi, cs:Feature_PrintIppPsaStabilityFixes_2505__descriptor
0x180032c32  mov     rdi, rdx
0x180032c35  mov     qword ptr [rdx], 0
0x180032c3c  mov     eax, [rsi]
0x180032c3e  mov     [rdx], eax
0x180032c40  and     eax, 6
0x180032c43  cmp     al, 6
0x180032c45  jz      loc_180032D3D
0x180032c4b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180032c50  lea     r8, [rsp+48h+arg_0]
0x180032c55  mov     dword ptr [rsp+48h+arg_0], 0
0x180032c5d  lea     rdx, [rsp+48h+arg_8]
0x180032c62  mov     ebp, eax
0x180032c64  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::GetCurrentFeatureEnabledState(int *)
0x180032c69  mov     eax, [rdi]
0x180032c6b  mov     rbx, [rsp+48h+arg_8]
0x180032c70  cmp     dword ptr [rsp+48h+arg_0], 0
0x180032c75  mov     edx, eax
0x180032c77  mov     [rdi], eax
0x180032c79  mov     ecx, eax
0x180032c7b  jz      short loc_180032C96
0x180032c7d  test    dl, 2
0x180032c80  jnz     short loc_180032C96
0x180032c82  and     ecx, 0FFFFF63Eh
0x180032c88  mov     eax, ebx
0x180032c8a  and     eax, 9C1h
0x180032c8f  or      ecx, eax
0x180032c91  or      ecx, 2
0x180032c94  mov     [rdi], ecx
0x180032c96  mov     r8d, edx
0x180032c99  and     r8d, 4
0x180032c9d  jnz     short loc_180032CB1
0x180032c9f  btr     ecx, 0Ah
0x180032ca3  mov     eax, ebx
0x180032ca5  and     eax, 400h
0x180032caa  or      ecx, eax
0x180032cac  or      ecx, 4
0x180032caf  mov     [rdi], ecx
0x180032cb1  mov     eax, edx
0x180032cb3  lock cmpxchg [rsi], ecx
0x180032cb7  jnz     short loc_180032C70
0x180032cb9  test    r8d, r8d
0x180032cbc  jnz     short loc_180032D28
0x180032cbe  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180032cc4  test    eax, eax
0x180032cc6  jz      short loc_180032D28
0x180032cc8  lea     r14, SRWLock
0x180032ccf  mov     rcx, r14; SRWLock
0x180032cd2  call    cs:__imp_AcquireSRWLockExclusive
0x180032cd9  nop     dword ptr [rax+rax+00h]
0x180032cde  mov     eax, cs:dword_1800443A4
0x180032ce4  mov     [rsp+48h+arg_8], r14
0x180032ce9  test    ebp, ebp
0x180032ceb  jz      short loc_180032D1A
0x180032ced  cmp     ebp, eax
0x180032cef  jnz     short loc_180032D1A
0x180032cf1  mov     r8d, 10h; unsigned __int64
0x180032cf7  mov     [rsp+48h+var_28], 3
0x180032d00  lea     rdx, [rsp+48h+var_28]; void *
0x180032d05  mov     [rsp+48h+var_20], rsi
0x180032d0a  lea     rcx, qword_1800443D8; this
0x180032d11  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180032d16  test    al, al
0x180032d18  jnz     short loc_180032D1E
0x180032d1a  lock and dword ptr [rsi], 0FFFFFFFBh
0x180032d1e  lea     rcx, [rsp+48h+arg_8]
0x180032d23  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180032d28  mov     eax, [rdi]
0x180032d2a  test    al, 2
0x180032d2c  jnz     short loc_180032D3D
0x180032d2e  and     eax, 0FFFFF63Eh
0x180032d33  and     ebx, 9C1h
0x180032d39  or      eax, ebx
0x180032d3b  mov     [rdi], eax
0x180032d3d  mov     rbx, [rsp+48h+arg_10]
0x180032d42  mov     rax, rdi
0x180032d45  mov     rbp, [rsp+48h+arg_18]
0x180032d4a  add     rsp, 30h
0x180032d4e  pop     r14
0x180032d50  pop     rdi
0x180032d51  pop     rsi
0x180032d52  retn
```
