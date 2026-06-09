# wil::details::FeatureImpl<__WilFeatureTraits_Feature_51718004>::GetCachedFeatureEnabledState(void)

- ea: `0x1800121f0`
- end: `0x1800122c9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_51718004@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015348`

## callees

- `0x180005dd8`
- `0x18000b3d8`
- `0x1800121f0`
- `0x18001359c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_51718004>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_51718004__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_51718004__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_51718004>::GetCurrentFeatureEnabledState(v5, &v11);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_51718004__descriptor, v9, v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_51718004__descriptor,
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
0x1800121f0  mov     [rsp+arg_10], rbx
0x1800121f5  mov     [rsp+arg_0], rcx
0x1800121fa  push    rbp
0x1800121fb  push    rsi
0x1800121fc  push    rdi
0x1800121fd  sub     rsp, 20h
0x180012201  mov     rsi, cs:Feature_51718004__descriptor
0x180012208  mov     rdi, rdx
0x18001220b  mov     qword ptr [rdx], 0
0x180012212  mov     eax, [rsi]
0x180012214  mov     [rdx], eax
0x180012216  and     eax, 6
0x180012219  cmp     al, 6
0x18001221b  jz      loc_1800122B9
0x180012221  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012226  lea     r8, [rsp+38h+arg_0]
0x18001222b  mov     dword ptr [rsp+38h+arg_0], 0
0x180012233  lea     rdx, [rsp+38h+arg_8]
0x180012238  mov     ebp, eax
0x18001223a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_51718004@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_51718004>::GetCurrentFeatureEnabledState(int *)
0x18001223f  mov     eax, [rdi]
0x180012241  mov     rbx, [rsp+38h+arg_8]
0x180012246  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001224b  mov     edx, eax
0x18001224d  mov     [rdi], eax
0x18001224f  mov     ecx, eax
0x180012251  jz      short loc_18001226C
0x180012253  test    dl, 2
0x180012256  jnz     short loc_18001226C
0x180012258  and     ecx, 0FFFFF63Eh
0x18001225e  mov     eax, ebx
0x180012260  and     eax, 9C1h
0x180012265  or      ecx, eax
0x180012267  or      ecx, 2
0x18001226a  mov     [rdi], ecx
0x18001226c  mov     r8d, edx
0x18001226f  and     r8d, 4
0x180012273  jnz     short loc_180012287
0x180012275  btr     ecx, 0Ah
0x180012279  mov     eax, ebx
0x18001227b  and     eax, 400h
0x180012280  or      ecx, eax
0x180012282  or      ecx, 4
0x180012285  mov     [rdi], ecx
0x180012287  mov     eax, edx
0x180012289  lock cmpxchg [rsi], ecx
0x18001228d  jnz     short loc_180012246
0x18001228f  test    r8d, r8d
0x180012292  jnz     short loc_1800122A4
0x180012294  mov     r8d, ebp
0x180012297  mov     edx, 3
0x18001229c  mov     rcx, rsi
0x18001229f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800122a4  mov     eax, [rdi]
0x1800122a6  test    al, 2
0x1800122a8  jnz     short loc_1800122B9
0x1800122aa  and     eax, 0FFFFF63Eh
0x1800122af  and     ebx, 9C1h
0x1800122b5  or      eax, ebx
0x1800122b7  mov     [rdi], eax
0x1800122b9  mov     rbx, [rsp+38h+arg_10]
0x1800122be  mov     rax, rdi
0x1800122c1  add     rsp, 20h
0x1800122c5  pop     rdi
0x1800122c6  pop     rsi
0x1800122c7  pop     rbp
0x1800122c8  retn
```
