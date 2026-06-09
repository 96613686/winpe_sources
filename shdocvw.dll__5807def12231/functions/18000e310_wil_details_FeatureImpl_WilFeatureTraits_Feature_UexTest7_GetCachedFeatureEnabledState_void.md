# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e310`
- end: `0x18000e3e9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fe68`
- `0x1800118fc`

## callees

- `0x18000d020`
- `0x18000e310`
- `0x18000ec38`
- `0x1800105e0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_UexTest7__descriptor,
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
0x18000e310  mov     [rsp+arg_10], rbx
0x18000e315  mov     [rsp+arg_0], rcx
0x18000e31a  push    rbp
0x18000e31b  push    rsi
0x18000e31c  push    rdi
0x18000e31d  sub     rsp, 20h
0x18000e321  mov     rsi, cs:Feature_UexTest7__descriptor
0x18000e328  mov     rdi, rdx
0x18000e32b  mov     qword ptr [rdx], 0
0x18000e332  mov     eax, [rsi]
0x18000e334  mov     [rdx], eax
0x18000e336  and     eax, 6
0x18000e339  cmp     al, 6
0x18000e33b  jz      loc_18000E3D9
0x18000e341  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e346  lea     r8, [rsp+38h+arg_0]
0x18000e34b  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e353  lea     rdx, [rsp+38h+arg_8]
0x18000e358  mov     ebp, eax
0x18000e35a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)
0x18000e35f  mov     eax, [rdi]
0x18000e361  mov     rbx, [rsp+38h+arg_8]
0x18000e366  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e36b  mov     edx, eax
0x18000e36d  mov     [rdi], eax
0x18000e36f  mov     ecx, eax
0x18000e371  jz      short loc_18000E38C
0x18000e373  test    dl, 2
0x18000e376  jnz     short loc_18000E38C
0x18000e378  and     ecx, 0FFFFF63Eh
0x18000e37e  mov     eax, ebx
0x18000e380  and     eax, 9C1h
0x18000e385  or      ecx, eax
0x18000e387  or      ecx, 2
0x18000e38a  mov     [rdi], ecx
0x18000e38c  mov     r8d, edx
0x18000e38f  and     r8d, 4
0x18000e393  jnz     short loc_18000E3A7
0x18000e395  btr     ecx, 0Ah
0x18000e399  mov     eax, ebx
0x18000e39b  and     eax, 400h
0x18000e3a0  or      ecx, eax
0x18000e3a2  or      ecx, 4
0x18000e3a5  mov     [rdi], ecx
0x18000e3a7  mov     eax, edx
0x18000e3a9  lock cmpxchg [rsi], ecx
0x18000e3ad  jnz     short loc_18000E366
0x18000e3af  test    r8d, r8d
0x18000e3b2  jnz     short loc_18000E3C4
0x18000e3b4  mov     r8d, ebp
0x18000e3b7  mov     edx, 3
0x18000e3bc  mov     rcx, rsi
0x18000e3bf  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e3c4  mov     eax, [rdi]
0x18000e3c6  test    al, 2
0x18000e3c8  jnz     short loc_18000E3D9
0x18000e3ca  and     eax, 0FFFFF63Eh
0x18000e3cf  and     ebx, 9C1h
0x18000e3d5  or      eax, ebx
0x18000e3d7  mov     [rdi], eax
0x18000e3d9  mov     rbx, [rsp+38h+arg_10]
0x18000e3de  mov     rax, rdi
0x18000e3e1  add     rsp, 20h
0x18000e3e5  pop     rdi
0x18000e3e6  pop     rsi
0x18000e3e7  pop     rbp
0x18000e3e8  retn
```
