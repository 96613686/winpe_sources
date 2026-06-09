# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(void)

- ea: `0x18000f9fc`
- end: `0x18000fadd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010fc4`
- `0x180011f84`

## callees

- `0x18000f670`
- `0x18000f9fc`
- `0x18000fba4`
- `0x180011240`

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
        (RTL_SRWLOCK *)wil::details::g_enabledStateManager,
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
0x18000f9fc  mov     [rsp+arg_10], rbx
0x18000fa01  mov     [rsp+arg_0], rcx
0x18000fa06  push    rbp
0x18000fa07  push    rsi
0x18000fa08  push    rdi
0x18000fa09  sub     rsp, 20h
0x18000fa0d  mov     rsi, cs:Feature_UxAccOptimization__descriptor
0x18000fa14  mov     rdi, rdx
0x18000fa17  mov     qword ptr [rdx], 0
0x18000fa1e  mov     eax, [rsi]
0x18000fa20  mov     [rdx], eax
0x18000fa22  and     eax, 6
0x18000fa25  cmp     al, 6
0x18000fa27  jz      loc_18000FACD
0x18000fa2d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000fa32  lea     r8, [rsp+38h+arg_0]
0x18000fa37  mov     dword ptr [rsp+38h+arg_0], 0
0x18000fa3f  lea     rdx, [rsp+38h+arg_8]
0x18000fa44  mov     ebp, eax
0x18000fa46  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)
0x18000fa4b  mov     eax, [rdi]
0x18000fa4d  mov     rbx, [rsp+38h+arg_8]
0x18000fa52  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000fa57  mov     edx, eax
0x18000fa59  mov     [rdi], eax
0x18000fa5b  mov     ecx, eax
0x18000fa5d  jz      short loc_18000FA78
0x18000fa5f  test    dl, 2
0x18000fa62  jnz     short loc_18000FA78
0x18000fa64  and     ecx, 0FFFFF63Eh
0x18000fa6a  mov     eax, ebx
0x18000fa6c  and     eax, 9C1h
0x18000fa71  or      ecx, eax
0x18000fa73  or      ecx, 2
0x18000fa76  mov     [rdi], ecx
0x18000fa78  mov     r8d, edx
0x18000fa7b  and     r8d, 4
0x18000fa7f  jnz     short loc_18000FA93
0x18000fa81  btr     ecx, 0Ah
0x18000fa85  mov     eax, ebx
0x18000fa87  and     eax, 400h
0x18000fa8c  or      ecx, eax
0x18000fa8e  or      ecx, 4
0x18000fa91  mov     [rdi], ecx
0x18000fa93  mov     eax, edx
0x18000fa95  lock cmpxchg [rsi], ecx
0x18000fa99  jnz     short loc_18000FA52
0x18000fa9b  test    r8d, r8d
0x18000fa9e  jnz     short loc_18000FAB8
0x18000faa0  mov     r9d, ebp
0x18000faa3  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000faaa  mov     r8d, 3
0x18000fab0  mov     rdx, rsi
0x18000fab3  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000fab8  mov     eax, [rdi]
0x18000faba  test    al, 2
0x18000fabc  jnz     short loc_18000FACD
0x18000fabe  and     eax, 0FFFFF63Eh
0x18000fac3  and     ebx, 9C1h
0x18000fac9  or      eax, ebx
0x18000facb  mov     [rdi], eax
0x18000facd  mov     rbx, [rsp+38h+arg_10]
0x18000fad2  mov     rax, rdi
0x18000fad5  add     rsp, 20h
0x18000fad9  pop     rdi
0x18000fada  pop     rsi
0x18000fadb  pop     rbp
0x18000fadc  retn
```
