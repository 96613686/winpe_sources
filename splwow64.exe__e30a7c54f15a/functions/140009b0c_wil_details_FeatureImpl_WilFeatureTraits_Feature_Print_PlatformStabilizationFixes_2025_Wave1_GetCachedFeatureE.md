# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetCachedFeatureEnabledState(void)

- ea: `0x140009b0c`
- end: `0x140009be5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000c2b4`

## callees

- `0x140009698`
- `0x140009b0c`
- `0x140009d6c`
- `0x14000b9b0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Print_PlatformStabilizationFixes_2025_Wave1__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Print_PlatformStabilizationFixes_2025_Wave1__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetCurrentFeatureEnabledState(
      v5,
      &v11);
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
      v6 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_Print_PlatformStabilizationFixes_2025_Wave1__descriptor,
             v9,
             v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Print_PlatformStabilizationFixes_2025_Wave1__descriptor,
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
0x140009b0c  mov     [rsp+arg_10], rbx
0x140009b11  mov     [rsp+arg_0], rcx
0x140009b16  push    rbp
0x140009b17  push    rsi
0x140009b18  push    rdi
0x140009b19  sub     rsp, 20h
0x140009b1d  mov     rsi, cs:Feature_Print_PlatformStabilizationFixes_2025_Wave1__descriptor
0x140009b24  mov     rdi, rdx
0x140009b27  mov     qword ptr [rdx], 0
0x140009b2e  mov     eax, [rsi]
0x140009b30  mov     [rdx], eax
0x140009b32  and     eax, 6
0x140009b35  cmp     al, 6
0x140009b37  jz      loc_140009BD5
0x140009b3d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140009b42  lea     r8, [rsp+38h+arg_0]
0x140009b47  mov     dword ptr [rsp+38h+arg_0], 0
0x140009b4f  lea     rdx, [rsp+38h+arg_8]
0x140009b54  mov     ebp, eax
0x140009b56  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetCurrentFeatureEnabledState(int *)
0x140009b5b  mov     eax, [rdi]
0x140009b5d  mov     rbx, [rsp+38h+arg_8]
0x140009b62  cmp     dword ptr [rsp+38h+arg_0], 0
0x140009b67  mov     edx, eax
0x140009b69  mov     [rdi], eax
0x140009b6b  mov     ecx, eax
0x140009b6d  jz      short loc_140009B88
0x140009b6f  test    dl, 2
0x140009b72  jnz     short loc_140009B88
0x140009b74  and     ecx, 0FFFFF63Eh
0x140009b7a  mov     eax, ebx
0x140009b7c  and     eax, 9C1h
0x140009b81  or      ecx, eax
0x140009b83  or      ecx, 2
0x140009b86  mov     [rdi], ecx
0x140009b88  mov     r8d, edx
0x140009b8b  and     r8d, 4
0x140009b8f  jnz     short loc_140009BA3
0x140009b91  btr     ecx, 0Ah
0x140009b95  mov     eax, ebx
0x140009b97  and     eax, 400h
0x140009b9c  or      ecx, eax
0x140009b9e  or      ecx, 4
0x140009ba1  mov     [rdi], ecx
0x140009ba3  mov     eax, edx
0x140009ba5  lock cmpxchg [rsi], ecx
0x140009ba9  jnz     short loc_140009B62
0x140009bab  test    r8d, r8d
0x140009bae  jnz     short loc_140009BC0
0x140009bb0  mov     r8d, ebp
0x140009bb3  mov     edx, 3
0x140009bb8  mov     rcx, rsi
0x140009bbb  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140009bc0  mov     eax, [rdi]
0x140009bc2  test    al, 2
0x140009bc4  jnz     short loc_140009BD5
0x140009bc6  and     eax, 0FFFFF63Eh
0x140009bcb  and     ebx, 9C1h
0x140009bd1  or      eax, ebx
0x140009bd3  mov     [rdi], eax
0x140009bd5  mov     rbx, [rsp+38h+arg_10]
0x140009bda  mov     rax, rdi
0x140009bdd  add     rsp, 20h
0x140009be1  pop     rdi
0x140009be2  pop     rsi
0x140009be3  pop     rbp
0x140009be4  retn
```
