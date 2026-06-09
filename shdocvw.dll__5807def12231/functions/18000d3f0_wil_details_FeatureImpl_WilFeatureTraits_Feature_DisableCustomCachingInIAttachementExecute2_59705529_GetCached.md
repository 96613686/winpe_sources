# wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableCustomCachingInIAttachementExecute2_59705529>::GetCachedFeatureEnabledState(void)

- ea: `0x18000d3f0`
- end: `0x18000d4c9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_DisableCustomCachingInIAttachementExecute2_59705529@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000faa8`
- `0x180011794`

## callees

- `0x18000d020`
- `0x18000d3f0`
- `0x18000e630`
- `0x1800105e0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableCustomCachingInIAttachementExecute2_59705529>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_DisableCustomCachingInIAttachementExecute2_59705529__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_DisableCustomCachingInIAttachementExecute2_59705529__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableCustomCachingInIAttachementExecute2_59705529>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_DisableCustomCachingInIAttachementExecute2_59705529__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_DisableCustomCachingInIAttachementExecute2_59705529__descriptor,
        1,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18000d3f0  mov     [rsp+arg_10], rbx
0x18000d3f5  mov     [rsp+arg_0], rcx
0x18000d3fa  push    rbp
0x18000d3fb  push    rsi
0x18000d3fc  push    rdi
0x18000d3fd  sub     rsp, 20h
0x18000d401  mov     rsi, cs:Feature_DisableCustomCachingInIAttachementExecute2_59705529__descriptor
0x18000d408  mov     rdi, rdx
0x18000d40b  mov     qword ptr [rdx], 0
0x18000d412  mov     eax, [rsi]
0x18000d414  mov     [rdx], eax
0x18000d416  and     eax, 6
0x18000d419  cmp     al, 6
0x18000d41b  jz      loc_18000D4B9
0x18000d421  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000d426  lea     r8, [rsp+38h+arg_0]
0x18000d42b  mov     dword ptr [rsp+38h+arg_0], 0
0x18000d433  lea     rdx, [rsp+38h+arg_8]
0x18000d438  mov     ebp, eax
0x18000d43a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_DisableCustomCachingInIAttachementExecute2_59705529@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableCustomCachingInIAttachementExecute2_59705529>::GetCurrentFeatureEnabledState(int *)
0x18000d43f  mov     eax, [rdi]
0x18000d441  mov     rbx, [rsp+38h+arg_8]
0x18000d446  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000d44b  mov     edx, eax
0x18000d44d  mov     [rdi], eax
0x18000d44f  mov     ecx, eax
0x18000d451  jz      short loc_18000D46C
0x18000d453  test    dl, 2
0x18000d456  jnz     short loc_18000D46C
0x18000d458  and     ecx, 0FFFFF63Eh
0x18000d45e  mov     eax, ebx
0x18000d460  and     eax, 9C1h
0x18000d465  or      ecx, eax
0x18000d467  or      ecx, 2
0x18000d46a  mov     [rdi], ecx
0x18000d46c  mov     r8d, edx
0x18000d46f  and     r8d, 4
0x18000d473  jnz     short loc_18000D487
0x18000d475  btr     ecx, 0Ah
0x18000d479  mov     eax, ebx
0x18000d47b  and     eax, 400h
0x18000d480  or      ecx, eax
0x18000d482  or      ecx, 4
0x18000d485  mov     [rdi], ecx
0x18000d487  mov     eax, edx
0x18000d489  lock cmpxchg [rsi], ecx
0x18000d48d  jnz     short loc_18000D446
0x18000d48f  test    r8d, r8d
0x18000d492  jnz     short loc_18000D4A4
0x18000d494  mov     r8d, ebp
0x18000d497  mov     edx, 1
0x18000d49c  mov     rcx, rsi
0x18000d49f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000d4a4  mov     eax, [rdi]
0x18000d4a6  test    al, 2
0x18000d4a8  jnz     short loc_18000D4B9
0x18000d4aa  and     eax, 0FFFFF63Eh
0x18000d4af  and     ebx, 9C1h
0x18000d4b5  or      eax, ebx
0x18000d4b7  mov     [rdi], eax
0x18000d4b9  mov     rbx, [rsp+38h+arg_10]
0x18000d4be  mov     rax, rdi
0x18000d4c1  add     rsp, 20h
0x18000d4c5  pop     rdi
0x18000d4c6  pop     rsi
0x18000d4c7  pop     rbp
0x18000d4c8  retn
```
