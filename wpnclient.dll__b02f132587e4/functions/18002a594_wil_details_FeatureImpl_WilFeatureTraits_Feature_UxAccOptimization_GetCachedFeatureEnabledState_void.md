# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(void)

- ea: `0x18002a594`
- end: `0x18002a675`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002b5cc`
- `0x18002c220`

## callees

- `0x180029c18`
- `0x18002a594`
- `0x18002a73c`
- `0x18002bacc`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(
      v6,
      &v14,
      &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UxAccOptimization__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_UxAccOptimization__descriptor,
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
0x18002a594  mov     [rsp+arg_10], rbx
0x18002a599  mov     [rsp+arg_0], rcx
0x18002a59e  push    rbp
0x18002a59f  push    rsi
0x18002a5a0  push    rdi
0x18002a5a1  sub     rsp, 20h
0x18002a5a5  mov     rsi, cs:Feature_UxAccOptimization__descriptor
0x18002a5ac  mov     rdi, rdx
0x18002a5af  mov     qword ptr [rdx], 0
0x18002a5b6  mov     eax, [rsi]
0x18002a5b8  mov     [rdx], eax
0x18002a5ba  and     eax, 6
0x18002a5bd  cmp     al, 6
0x18002a5bf  jz      loc_18002A665
0x18002a5c5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002a5ca  lea     r8, [rsp+38h+arg_0]
0x18002a5cf  mov     dword ptr [rsp+38h+arg_0], 0
0x18002a5d7  lea     rdx, [rsp+38h+arg_8]
0x18002a5dc  mov     ebp, eax
0x18002a5de  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)
0x18002a5e3  mov     eax, [rdi]
0x18002a5e5  mov     rbx, [rsp+38h+arg_8]
0x18002a5ea  cmp     dword ptr [rsp+38h+arg_0], 0
0x18002a5ef  mov     edx, eax
0x18002a5f1  mov     [rdi], eax
0x18002a5f3  mov     ecx, eax
0x18002a5f5  jz      short loc_18002A610
0x18002a5f7  test    dl, 2
0x18002a5fa  jnz     short loc_18002A610
0x18002a5fc  and     ecx, 0FFFFF63Eh
0x18002a602  mov     eax, ebx
0x18002a604  and     eax, 9C1h
0x18002a609  or      ecx, eax
0x18002a60b  or      ecx, 2
0x18002a60e  mov     [rdi], ecx
0x18002a610  mov     r8d, edx
0x18002a613  and     r8d, 4
0x18002a617  jnz     short loc_18002A62B
0x18002a619  btr     ecx, 0Ah
0x18002a61d  mov     eax, ebx
0x18002a61f  and     eax, 400h
0x18002a624  or      ecx, eax
0x18002a626  or      ecx, 4
0x18002a629  mov     [rdi], ecx
0x18002a62b  mov     eax, edx
0x18002a62d  lock cmpxchg [rsi], ecx
0x18002a631  jnz     short loc_18002A5EA
0x18002a633  test    r8d, r8d
0x18002a636  jnz     short loc_18002A650
0x18002a638  mov     r9d, ebp
0x18002a63b  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18002a642  mov     r8d, 3
0x18002a648  mov     rdx, rsi
0x18002a64b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18002a650  mov     eax, [rdi]
0x18002a652  test    al, 2
0x18002a654  jnz     short loc_18002A665
0x18002a656  and     eax, 0FFFFF63Eh
0x18002a65b  and     ebx, 9C1h
0x18002a661  or      eax, ebx
0x18002a663  mov     [rdi], eax
0x18002a665  mov     rbx, [rsp+38h+arg_10]
0x18002a66a  mov     rax, rdi
0x18002a66d  add     rsp, 20h
0x18002a671  pop     rdi
0x18002a672  pop     rsi
0x18002a673  pop     rbp
0x18002a674  retn
```
