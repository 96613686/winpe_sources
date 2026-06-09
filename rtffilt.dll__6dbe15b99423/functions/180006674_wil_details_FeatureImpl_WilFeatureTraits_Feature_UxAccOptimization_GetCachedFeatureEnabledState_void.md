# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(void)

- ea: `0x180006674`
- end: `0x18000674d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c6b4`

## callees

- `0x180005dd8`
- `0x180006674`
- `0x180006970`
- `0x18000b3d8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 v5; // rcx
  signed __int32 v6; // eax
  __int16 v7; // bx
  signed __int32 v8; // edx
  unsigned int v9; // ecx
  __int64 v11; // [rsp+48h] [rbp+10h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(v5, &v11);
    v6 = *(_DWORD *)a2;
    v7 = v11;
    do
    {
      v8 = v6;
      *(_DWORD *)a2 = v6;
      v9 = v6;
      if ( (v6 & 4) == 0 )
      {
        v9 = v7 & 0x400 | v6 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v9;
      }
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UxAccOptimization__descriptor, v9, v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_UxAccOptimization__descriptor,
        3u,
        v4);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v7 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180006674  mov     [rsp+arg_10], rbx
0x180006679  mov     [rsp+arg_0], rcx
0x18000667e  push    rbp
0x18000667f  push    rsi
0x180006680  push    rdi
0x180006681  sub     rsp, 20h
0x180006685  mov     rsi, cs:Feature_UxAccOptimization__descriptor
0x18000668c  mov     rdi, rdx
0x18000668f  mov     qword ptr [rdx], 0
0x180006696  mov     eax, [rsi]
0x180006698  mov     [rdx], eax
0x18000669a  and     eax, 6
0x18000669d  cmp     al, 6
0x18000669f  jz      loc_18000673D
0x1800066a5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800066aa  lea     r8, [rsp+38h+arg_0]
0x1800066af  mov     dword ptr [rsp+38h+arg_0], 0
0x1800066b7  lea     rdx, [rsp+38h+arg_8]
0x1800066bc  mov     ebp, eax
0x1800066be  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)
0x1800066c3  mov     eax, [rdi]
0x1800066c5  mov     rbx, [rsp+38h+arg_8]
0x1800066ca  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800066cf  mov     edx, eax
0x1800066d1  mov     [rdi], eax
0x1800066d3  mov     ecx, eax
0x1800066d5  jz      short loc_1800066F0
0x1800066d7  test    dl, 2
0x1800066da  jnz     short loc_1800066F0
0x1800066dc  and     ecx, 0FFFFF63Eh
0x1800066e2  mov     eax, ebx
0x1800066e4  and     eax, 9C1h
0x1800066e9  or      ecx, eax
0x1800066eb  or      ecx, 2
0x1800066ee  mov     [rdi], ecx
0x1800066f0  mov     r8d, edx
0x1800066f3  and     r8d, 4
0x1800066f7  jnz     short loc_18000670B
0x1800066f9  btr     ecx, 0Ah
0x1800066fd  mov     eax, ebx
0x1800066ff  and     eax, 400h
0x180006704  or      ecx, eax
0x180006706  or      ecx, 4
0x180006709  mov     [rdi], ecx
0x18000670b  mov     eax, edx
0x18000670d  lock cmpxchg [rsi], ecx
0x180006711  jnz     short loc_1800066CA
0x180006713  test    r8d, r8d
0x180006716  jnz     short loc_180006728
0x180006718  mov     r8d, ebp
0x18000671b  mov     edx, 3
0x180006720  mov     rcx, rsi
0x180006723  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180006728  mov     eax, [rdi]
0x18000672a  test    al, 2
0x18000672c  jnz     short loc_18000673D
0x18000672e  and     eax, 0FFFFF63Eh
0x180006733  and     ebx, 9C1h
0x180006739  or      eax, ebx
0x18000673b  mov     [rdi], eax
0x18000673d  mov     rbx, [rsp+38h+arg_10]
0x180006742  mov     rax, rdi
0x180006745  add     rsp, 20h
0x180006749  pop     rdi
0x18000674a  pop     rsi
0x18000674b  pop     rbp
0x18000674c  retn
```
