# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Scenario58454712>::GetCachedFeatureEnabledState(void)

- ea: `0x180010e04`
- end: `0x180010edd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Scenario58454712@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011d1c`
- `0x180012df8`

## callees

- `0x180005384`
- `0x180009148`
- `0x180010e04`
- `0x180010fc4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Scenario58454712>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Scenario58454712__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Scenario58454712__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Scenario58454712>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Scenario58454712__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Scenario58454712__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180010e04  mov     [rsp+arg_10], rbx
0x180010e09  mov     [rsp+arg_0], rcx
0x180010e0e  push    rbp
0x180010e0f  push    rsi
0x180010e10  push    rdi
0x180010e11  sub     rsp, 20h
0x180010e15  mov     rsi, cs:Feature_Scenario58454712__descriptor
0x180010e1c  mov     rdi, rdx
0x180010e1f  mov     qword ptr [rdx], 0
0x180010e26  mov     eax, [rsi]
0x180010e28  mov     [rdx], eax
0x180010e2a  and     eax, 6
0x180010e2d  cmp     al, 6
0x180010e2f  jz      loc_180010ECD
0x180010e35  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180010e3a  lea     r8, [rsp+38h+arg_0]
0x180010e3f  mov     dword ptr [rsp+38h+arg_0], 0
0x180010e47  lea     rdx, [rsp+38h+arg_8]
0x180010e4c  mov     ebp, eax
0x180010e4e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Scenario58454712@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Scenario58454712>::GetCurrentFeatureEnabledState(int *)
0x180010e53  mov     eax, [rdi]
0x180010e55  mov     rbx, [rsp+38h+arg_8]
0x180010e5a  cmp     dword ptr [rsp+38h+arg_0], 0
0x180010e5f  mov     edx, eax
0x180010e61  mov     [rdi], eax
0x180010e63  mov     ecx, eax
0x180010e65  jz      short loc_180010E80
0x180010e67  test    dl, 2
0x180010e6a  jnz     short loc_180010E80
0x180010e6c  and     ecx, 0FFFFF63Eh
0x180010e72  mov     eax, ebx
0x180010e74  and     eax, 9C1h
0x180010e79  or      ecx, eax
0x180010e7b  or      ecx, 2
0x180010e7e  mov     [rdi], ecx
0x180010e80  mov     r8d, edx
0x180010e83  and     r8d, 4
0x180010e87  jnz     short loc_180010E9B
0x180010e89  btr     ecx, 0Ah
0x180010e8d  mov     eax, ebx
0x180010e8f  and     eax, 400h
0x180010e94  or      ecx, eax
0x180010e96  or      ecx, 4
0x180010e99  mov     [rdi], ecx
0x180010e9b  mov     eax, edx
0x180010e9d  lock cmpxchg [rsi], ecx
0x180010ea1  jnz     short loc_180010E5A
0x180010ea3  test    r8d, r8d
0x180010ea6  jnz     short loc_180010EB8
0x180010ea8  mov     r8d, ebp
0x180010eab  mov     edx, 3
0x180010eb0  mov     rcx, rsi
0x180010eb3  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180010eb8  mov     eax, [rdi]
0x180010eba  test    al, 2
0x180010ebc  jnz     short loc_180010ECD
0x180010ebe  and     eax, 0FFFFF63Eh
0x180010ec3  and     ebx, 9C1h
0x180010ec9  or      eax, ebx
0x180010ecb  mov     [rdi], eax
0x180010ecd  mov     rbx, [rsp+38h+arg_10]
0x180010ed2  mov     rax, rdi
0x180010ed5  add     rsp, 20h
0x180010ed9  pop     rdi
0x180010eda  pop     rsi
0x180010edb  pop     rbp
0x180010edc  retn
```
