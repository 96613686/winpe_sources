# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(void)

- ea: `0x18000dbe8`
- end: `0x18000dcc1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001080c`
- `0x1800122f0`

## callees

- `0x18000d5d0`
- `0x18000dbe8`
- `0x18000df70`
- `0x180011590`

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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
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
0x18000dbe8  mov     [rsp+arg_10], rbx
0x18000dbed  mov     [rsp+arg_0], rcx
0x18000dbf2  push    rbp
0x18000dbf3  push    rsi
0x18000dbf4  push    rdi
0x18000dbf5  sub     rsp, 20h
0x18000dbf9  mov     rsi, cs:Feature_UxAccOptimization__descriptor
0x18000dc00  mov     rdi, rdx
0x18000dc03  mov     qword ptr [rdx], 0
0x18000dc0a  mov     eax, [rsi]
0x18000dc0c  mov     [rdx], eax
0x18000dc0e  and     eax, 6
0x18000dc11  cmp     al, 6
0x18000dc13  jz      loc_18000DCB1
0x18000dc19  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000dc1e  lea     r8, [rsp+38h+arg_0]
0x18000dc23  mov     dword ptr [rsp+38h+arg_0], 0
0x18000dc2b  lea     rdx, [rsp+38h+arg_8]
0x18000dc30  mov     ebp, eax
0x18000dc32  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)
0x18000dc37  mov     eax, [rdi]
0x18000dc39  mov     rbx, [rsp+38h+arg_8]
0x18000dc3e  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000dc43  mov     edx, eax
0x18000dc45  mov     [rdi], eax
0x18000dc47  mov     ecx, eax
0x18000dc49  jz      short loc_18000DC64
0x18000dc4b  test    dl, 2
0x18000dc4e  jnz     short loc_18000DC64
0x18000dc50  and     ecx, 0FFFFF63Eh
0x18000dc56  mov     eax, ebx
0x18000dc58  and     eax, 9C1h
0x18000dc5d  or      ecx, eax
0x18000dc5f  or      ecx, 2
0x18000dc62  mov     [rdi], ecx
0x18000dc64  mov     r8d, edx
0x18000dc67  and     r8d, 4
0x18000dc6b  jnz     short loc_18000DC7F
0x18000dc6d  btr     ecx, 0Ah
0x18000dc71  mov     eax, ebx
0x18000dc73  and     eax, 400h
0x18000dc78  or      ecx, eax
0x18000dc7a  or      ecx, 4
0x18000dc7d  mov     [rdi], ecx
0x18000dc7f  mov     eax, edx
0x18000dc81  lock cmpxchg [rsi], ecx
0x18000dc85  jnz     short loc_18000DC3E
0x18000dc87  test    r8d, r8d
0x18000dc8a  jnz     short loc_18000DC9C
0x18000dc8c  mov     r8d, ebp
0x18000dc8f  mov     edx, 3
0x18000dc94  mov     rcx, rsi
0x18000dc97  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000dc9c  mov     eax, [rdi]
0x18000dc9e  test    al, 2
0x18000dca0  jnz     short loc_18000DCB1
0x18000dca2  and     eax, 0FFFFF63Eh
0x18000dca7  and     ebx, 9C1h
0x18000dcad  or      eax, ebx
0x18000dcaf  mov     [rdi], eax
0x18000dcb1  mov     rbx, [rsp+38h+arg_10]
0x18000dcb6  mov     rax, rdi
0x18000dcb9  add     rsp, 20h
0x18000dcbd  pop     rdi
0x18000dcbe  pop     rsi
0x18000dcbf  pop     rbp
0x18000dcc0  retn
```
