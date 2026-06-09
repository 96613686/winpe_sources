# wil::details::FeatureImpl<__WilFeatureTraits_Feature_59697564>::GetCachedFeatureEnabledState(void)

- ea: `0x1400557a4`
- end: `0x140055885`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_59697564@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005a5e0`
- `0x14005d3a4`

## callees

- `0x14004693c`
- `0x140049d0c`
- `0x1400557a4`
- `0x1400564c8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_59697564>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  int v5; // ebp
  __int64 v6; // rcx
  signed __int32 v7; // eax
  __int16 v8; // bx
  bool v9; // zf
  signed __int32 v10; // edx
  unsigned int v11; // ecx
  wil::details *v13; // [rsp+40h] [rbp+8h] BYREF
  __int64 v14; // [rsp+48h] [rbp+10h] BYREF

  v13 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_59697564__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_59697564__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_59697564>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
    v7 = *(_DWORD *)a2;
    v8 = v14;
    do
    {
      v9 = (_DWORD)v13 == 0;
      v10 = v7;
      *(_DWORD *)a2 = v7;
      v11 = v7;
      if ( !v9 && (v7 & 2) == 0 )
      {
        v11 = v8 & 0x9C1 | v7 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v11;
      }
      if ( (v7 & 4) == 0 )
      {
        v11 = v8 & 0x400 | v11 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v11;
      }
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_59697564__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_59697564__descriptor,
        3,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x1400557a4  mov     [rsp+arg_10], rbx
0x1400557a9  mov     [rsp+arg_0], rcx
0x1400557ae  push    rbp
0x1400557af  push    rsi
0x1400557b0  push    rdi
0x1400557b1  sub     rsp, 20h
0x1400557b5  mov     rsi, cs:Feature_59697564__descriptor
0x1400557bc  mov     rdi, rdx
0x1400557bf  mov     qword ptr [rdx], 0
0x1400557c6  mov     eax, [rsi]
0x1400557c8  mov     [rdx], eax
0x1400557ca  and     eax, 6
0x1400557cd  cmp     al, 6
0x1400557cf  jz      loc_140055875
0x1400557d5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1400557da  lea     r8, [rsp+38h+arg_0]
0x1400557df  mov     dword ptr [rsp+38h+arg_0], 0
0x1400557e7  lea     rdx, [rsp+38h+arg_8]
0x1400557ec  mov     ebp, eax
0x1400557ee  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_59697564@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59697564>::GetCurrentFeatureEnabledState(int *)
0x1400557f3  mov     eax, [rdi]
0x1400557f5  mov     rbx, [rsp+38h+arg_8]
0x1400557fa  cmp     dword ptr [rsp+38h+arg_0], 0
0x1400557ff  mov     edx, eax
0x140055801  mov     [rdi], eax
0x140055803  mov     ecx, eax
0x140055805  jz      short loc_140055820
0x140055807  test    dl, 2
0x14005580a  jnz     short loc_140055820
0x14005580c  and     ecx, 0FFFFF63Eh
0x140055812  mov     eax, ebx
0x140055814  and     eax, 9C1h
0x140055819  or      ecx, eax
0x14005581b  or      ecx, 2
0x14005581e  mov     [rdi], ecx
0x140055820  mov     r8d, edx
0x140055823  and     r8d, 4
0x140055827  jnz     short loc_14005583B
0x140055829  btr     ecx, 0Ah
0x14005582d  mov     eax, ebx
0x14005582f  and     eax, 400h
0x140055834  or      ecx, eax
0x140055836  or      ecx, 4
0x140055839  mov     [rdi], ecx
0x14005583b  mov     eax, edx
0x14005583d  lock cmpxchg [rsi], ecx
0x140055841  jnz     short loc_1400557FA
0x140055843  test    r8d, r8d
0x140055846  jnz     short loc_140055860
0x140055848  mov     r9d, ebp
0x14005584b  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140055852  mov     r8d, 3
0x140055858  mov     rdx, rsi
0x14005585b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140055860  mov     eax, [rdi]
0x140055862  test    al, 2
0x140055864  jnz     short loc_140055875
0x140055866  and     eax, 0FFFFF63Eh
0x14005586b  and     ebx, 9C1h
0x140055871  or      eax, ebx
0x140055873  mov     [rdi], eax
0x140055875  mov     rbx, [rsp+38h+arg_10]
0x14005587a  mov     rax, rdi
0x14005587d  add     rsp, 20h
0x140055881  pop     rdi
0x140055882  pop     rsi
0x140055883  pop     rbp
0x140055884  retn
```
