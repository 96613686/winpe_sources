# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(void)

- ea: `0x180017ab8`
- end: `0x180017b91`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800191f0`

## callees

- `0x180016be8`
- `0x180017ab8`
- `0x1800183b8`
- `0x180018da4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(
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
  wil::details *v13; // [rsp+40h] [rbp+8h] BYREF
  __int64 v14; // [rsp+48h] [rbp+10h] BYREF

  v13 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_UexTest7__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UexTest7__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UexTest7__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_UexTest7__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180017ab8  mov     [rsp+arg_10], rbx
0x180017abd  mov     [rsp+arg_0], rcx
0x180017ac2  push    rbp
0x180017ac3  push    rsi
0x180017ac4  push    rdi
0x180017ac5  sub     rsp, 20h
0x180017ac9  mov     rsi, cs:Feature_UexTest7__descriptor
0x180017ad0  mov     rdi, rdx
0x180017ad3  mov     qword ptr [rdx], 0
0x180017ada  mov     eax, [rsi]
0x180017adc  mov     [rdx], eax
0x180017ade  and     eax, 6
0x180017ae1  cmp     al, 6
0x180017ae3  jz      loc_180017B81
0x180017ae9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180017aee  lea     r8, [rsp+38h+arg_0]
0x180017af3  mov     dword ptr [rsp+38h+arg_0], 0
0x180017afb  lea     rdx, [rsp+38h+arg_8]
0x180017b00  mov     ebp, eax
0x180017b02  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)
0x180017b07  mov     eax, [rdi]
0x180017b09  mov     rbx, [rsp+38h+arg_8]
0x180017b0e  cmp     dword ptr [rsp+38h+arg_0], 0
0x180017b13  mov     edx, eax
0x180017b15  mov     [rdi], eax
0x180017b17  mov     ecx, eax
0x180017b19  jz      short loc_180017B34
0x180017b1b  test    dl, 2
0x180017b1e  jnz     short loc_180017B34
0x180017b20  and     ecx, 0FFFFF63Eh
0x180017b26  mov     eax, ebx
0x180017b28  and     eax, 9C1h
0x180017b2d  or      ecx, eax
0x180017b2f  or      ecx, 2
0x180017b32  mov     [rdi], ecx
0x180017b34  mov     r8d, edx
0x180017b37  and     r8d, 4
0x180017b3b  jnz     short loc_180017B4F
0x180017b3d  btr     ecx, 0Ah
0x180017b41  mov     eax, ebx
0x180017b43  and     eax, 400h
0x180017b48  or      ecx, eax
0x180017b4a  or      ecx, 4
0x180017b4d  mov     [rdi], ecx
0x180017b4f  mov     eax, edx
0x180017b51  lock cmpxchg [rsi], ecx
0x180017b55  jnz     short loc_180017B0E
0x180017b57  test    r8d, r8d
0x180017b5a  jnz     short loc_180017B6C
0x180017b5c  mov     r8d, ebp
0x180017b5f  mov     edx, 3
0x180017b64  mov     rcx, rsi
0x180017b67  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180017b6c  mov     eax, [rdi]
0x180017b6e  test    al, 2
0x180017b70  jnz     short loc_180017B81
0x180017b72  and     eax, 0FFFFF63Eh
0x180017b77  and     ebx, 9C1h
0x180017b7d  or      eax, ebx
0x180017b7f  mov     [rdi], eax
0x180017b81  mov     rbx, [rsp+38h+arg_10]
0x180017b86  mov     rax, rdi
0x180017b89  add     rsp, 20h
0x180017b8d  pop     rdi
0x180017b8e  pop     rsi
0x180017b8f  pop     rbp
0x180017b90  retn
```
