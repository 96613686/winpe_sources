# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(void)

- ea: `0x18000708c`
- end: `0x180007165`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d568`

## callees

- `0x180005dd0`
- `0x18000708c`
- `0x180007ad0`
- `0x18000c3f0`

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
0x18000708c  mov     [rsp+arg_10], rbx
0x180007091  mov     [rsp+arg_0], rcx
0x180007096  push    rbp
0x180007097  push    rsi
0x180007098  push    rdi
0x180007099  sub     rsp, 20h
0x18000709d  mov     rsi, cs:Feature_UexTest7__descriptor
0x1800070a4  mov     rdi, rdx
0x1800070a7  mov     qword ptr [rdx], 0
0x1800070ae  mov     eax, [rsi]
0x1800070b0  mov     [rdx], eax
0x1800070b2  and     eax, 6
0x1800070b5  cmp     al, 6
0x1800070b7  jz      loc_180007155
0x1800070bd  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800070c2  lea     r8, [rsp+38h+arg_0]
0x1800070c7  mov     dword ptr [rsp+38h+arg_0], 0
0x1800070cf  lea     rdx, [rsp+38h+arg_8]
0x1800070d4  mov     ebp, eax
0x1800070d6  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)
0x1800070db  mov     eax, [rdi]
0x1800070dd  mov     rbx, [rsp+38h+arg_8]
0x1800070e2  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800070e7  mov     edx, eax
0x1800070e9  mov     [rdi], eax
0x1800070eb  mov     ecx, eax
0x1800070ed  jz      short loc_180007108
0x1800070ef  test    dl, 2
0x1800070f2  jnz     short loc_180007108
0x1800070f4  and     ecx, 0FFFFF63Eh
0x1800070fa  mov     eax, ebx
0x1800070fc  and     eax, 9C1h
0x180007101  or      ecx, eax
0x180007103  or      ecx, 2
0x180007106  mov     [rdi], ecx
0x180007108  mov     r8d, edx
0x18000710b  and     r8d, 4
0x18000710f  jnz     short loc_180007123
0x180007111  btr     ecx, 0Ah
0x180007115  mov     eax, ebx
0x180007117  and     eax, 400h
0x18000711c  or      ecx, eax
0x18000711e  or      ecx, 4
0x180007121  mov     [rdi], ecx
0x180007123  mov     eax, edx
0x180007125  lock cmpxchg [rsi], ecx
0x180007129  jnz     short loc_1800070E2
0x18000712b  test    r8d, r8d
0x18000712e  jnz     short loc_180007140
0x180007130  mov     r8d, ebp
0x180007133  mov     edx, 3
0x180007138  mov     rcx, rsi
0x18000713b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180007140  mov     eax, [rdi]
0x180007142  test    al, 2
0x180007144  jnz     short loc_180007155
0x180007146  and     eax, 0FFFFF63Eh
0x18000714b  and     ebx, 9C1h
0x180007151  or      eax, ebx
0x180007153  mov     [rdi], eax
0x180007155  mov     rbx, [rsp+38h+arg_10]
0x18000715a  mov     rax, rdi
0x18000715d  add     rsp, 20h
0x180007161  pop     rdi
0x180007162  pop     rsi
0x180007163  pop     rbp
0x180007164  retn
```
