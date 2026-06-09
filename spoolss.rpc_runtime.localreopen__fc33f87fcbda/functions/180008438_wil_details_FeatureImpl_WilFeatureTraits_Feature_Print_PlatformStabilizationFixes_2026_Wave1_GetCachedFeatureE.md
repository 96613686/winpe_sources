# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetCachedFeatureEnabledState(void)

- ea: `0x180008438`
- end: `0x180008578`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a7c4`
- `0x18000c480`

## callees

- `0x1800047ac`
- `0x180007f30`
- `0x180008438`
- `0x180008a20`
- `0x18000c63c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800084f6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800084f6`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Print_PlatformStabilizationFixes_2026_Wave1__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Print_PlatformStabilizationFixes_2026_Wave1__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetCurrentFeatureEnabledState(
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
             (volatile signed __int32 *)Feature_Print_PlatformStabilizationFixes_2026_Wave1__descriptor,
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
            v14[1] = Feature_Print_PlatformStabilizationFixes_2026_Wave1__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180022338, v14, 0x10u)) )
      {
        _InterlockedAnd(
          (volatile signed __int32 *)Feature_Print_PlatformStabilizationFixes_2026_Wave1__descriptor,
          0xFFFFFFFB);
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
0x180008438  mov     [rsp+arg_10], rbx
0x18000843d  mov     [rsp+arg_18], rbp
0x180008442  mov     [rsp+arg_0], rcx
0x180008447  push    rsi
0x180008448  push    rdi
0x180008449  push    r14
0x18000844b  sub     rsp, 30h
0x18000844f  mov     rsi, cs:Feature_Print_PlatformStabilizationFixes_2026_Wave1__descriptor
0x180008456  mov     rdi, rdx
0x180008459  mov     qword ptr [rdx], 0
0x180008460  mov     eax, [rsi]
0x180008462  mov     [rdx], eax
0x180008464  and     eax, 6
0x180008467  cmp     al, 6
0x180008469  jz      loc_180008561
0x18000846f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180008474  lea     r8, [rsp+48h+arg_0]
0x180008479  mov     dword ptr [rsp+48h+arg_0], 0
0x180008481  lea     rdx, [rsp+48h+arg_8]
0x180008486  mov     ebp, eax
0x180008488  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetCurrentFeatureEnabledState(int *)
0x18000848d  mov     eax, [rdi]
0x18000848f  mov     rbx, [rsp+48h+arg_8]
0x180008494  cmp     dword ptr [rsp+48h+arg_0], 0
0x180008499  mov     edx, eax
0x18000849b  mov     [rdi], eax
0x18000849d  mov     ecx, eax
0x18000849f  jz      short loc_1800084BA
0x1800084a1  test    dl, 2
0x1800084a4  jnz     short loc_1800084BA
0x1800084a6  and     ecx, 0FFFFF63Eh
0x1800084ac  mov     eax, ebx
0x1800084ae  and     eax, 9C1h
0x1800084b3  or      ecx, eax
0x1800084b5  or      ecx, 2
0x1800084b8  mov     [rdi], ecx
0x1800084ba  mov     r8d, edx
0x1800084bd  and     r8d, 4
0x1800084c1  jnz     short loc_1800084D5
0x1800084c3  btr     ecx, 0Ah
0x1800084c7  mov     eax, ebx
0x1800084c9  and     eax, 400h
0x1800084ce  or      ecx, eax
0x1800084d0  or      ecx, 4
0x1800084d3  mov     [rdi], ecx
0x1800084d5  mov     eax, edx
0x1800084d7  lock cmpxchg [rsi], ecx
0x1800084db  jnz     short loc_180008494
0x1800084dd  test    r8d, r8d
0x1800084e0  jnz     short loc_18000854C
0x1800084e2  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800084e8  test    eax, eax
0x1800084ea  jz      short loc_18000854C
0x1800084ec  lea     r14, SRWLock
0x1800084f3  mov     rcx, r14; SRWLock
0x1800084f6  call    cs:__imp_AcquireSRWLockExclusive
0x1800084fd  nop     dword ptr [rax+rax+00h]
0x180008502  mov     eax, cs:dword_180022304
0x180008508  mov     [rsp+48h+arg_8], r14
0x18000850d  test    ebp, ebp
0x18000850f  jz      short loc_18000853E
0x180008511  cmp     ebp, eax
0x180008513  jnz     short loc_18000853E
0x180008515  mov     r8d, 10h; unsigned __int64
0x18000851b  mov     [rsp+48h+var_28], 3
0x180008524  lea     rdx, [rsp+48h+var_28]; void *
0x180008529  mov     [rsp+48h+var_20], rsi
0x18000852e  lea     rcx, qword_180022338; this
0x180008535  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000853a  test    al, al
0x18000853c  jnz     short loc_180008542
0x18000853e  lock and dword ptr [rsi], 0FFFFFFFBh
0x180008542  lea     rcx, [rsp+48h+arg_8]
0x180008547  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000854c  mov     eax, [rdi]
0x18000854e  test    al, 2
0x180008550  jnz     short loc_180008561
0x180008552  and     eax, 0FFFFF63Eh
0x180008557  and     ebx, 9C1h
0x18000855d  or      eax, ebx
0x18000855f  mov     [rdi], eax
0x180008561  mov     rbx, [rsp+48h+arg_10]
0x180008566  mov     rax, rdi
0x180008569  mov     rbp, [rsp+48h+arg_18]
0x18000856e  add     rsp, 30h
0x180008572  pop     r14
0x180008574  pop     rdi
0x180008575  pop     rsi
0x180008576  retn
```
