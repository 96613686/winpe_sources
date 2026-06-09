# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x18001b924`
- end: `0x18001ba0f`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020770`

## callees

- `0x1800015f0`
- `0x18001aba4`
- `0x18001b924`
- `0x18001c164`
- `0x180026a48`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 v5; // rcx
  signed __int32 v6; // eax
  __int16 v7; // bx
  bool v8; // zf
  signed __int32 v9; // edx
  unsigned int v10; // ecx
  __int64 v12; // [rsp+20h] [rbp-48h] BYREF
  int v13; // [rsp+28h] [rbp-40h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_ValLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(v5, &v12, &v13);
    v6 = *(_DWORD *)a2;
    v7 = v12;
    do
    {
      v8 = v13 == 0;
      v9 = v6;
      *(_DWORD *)a2 = v6;
      v10 = v6;
      if ( !v8 && (v6 & 2) == 0 )
      {
        v10 = v7 & 0x9C1 | v6 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v10;
      }
      if ( (v6 & 4) == 0 )
      {
        v10 = v7 & 0x400 | v10 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v10;
      }
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValLabTest__descriptor, v10, v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_ValLabTest__descriptor,
        3,
        v4);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v7 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18001b924  push    rbx
0x18001b926  push    rbp
0x18001b927  push    rsi
0x18001b928  push    rdi
0x18001b929  sub     rsp, 48h
0x18001b92d  mov     rax, cs:__security_cookie
0x18001b934  xor     rax, rsp
0x18001b937  mov     [rsp+68h+var_38], rax
0x18001b93c  mov     rsi, cs:Feature_ValLabTest__descriptor
0x18001b943  mov     rdi, rdx
0x18001b946  mov     qword ptr [rdx], 0
0x18001b94d  mov     eax, [rsi]
0x18001b94f  mov     [rdx], eax
0x18001b951  and     eax, 6
0x18001b954  cmp     al, 6
0x18001b956  jz      loc_18001B9F6
0x18001b95c  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001b961  lea     r8, [rsp+68h+var_40]
0x18001b966  mov     [rsp+68h+var_40], 0
0x18001b96e  lea     rdx, [rsp+68h+var_48]
0x18001b973  mov     ebp, eax
0x18001b975  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(int *)
0x18001b97a  mov     eax, [rdi]
0x18001b97c  mov     rbx, [rsp+68h+var_48]
0x18001b981  cmp     [rsp+68h+var_40], 0
0x18001b986  mov     edx, eax
0x18001b988  mov     [rdi], eax
0x18001b98a  mov     ecx, eax
0x18001b98c  jz      short loc_18001B9A7
0x18001b98e  test    dl, 2
0x18001b991  jnz     short loc_18001B9A7
0x18001b993  and     ecx, 0FFFFF63Eh
0x18001b999  mov     eax, ebx
0x18001b99b  and     eax, 9C1h
0x18001b9a0  or      ecx, eax
0x18001b9a2  or      ecx, 2
0x18001b9a5  mov     [rdi], ecx
0x18001b9a7  mov     r8d, edx
0x18001b9aa  and     r8d, 4
0x18001b9ae  jnz     short loc_18001B9C2
0x18001b9b0  btr     ecx, 0Ah
0x18001b9b4  mov     eax, ebx
0x18001b9b6  and     eax, 400h
0x18001b9bb  or      ecx, eax
0x18001b9bd  or      ecx, 4
0x18001b9c0  mov     [rdi], ecx
0x18001b9c2  mov     eax, edx
0x18001b9c4  lock cmpxchg [rsi], ecx
0x18001b9c8  jnz     short loc_18001B981
0x18001b9ca  test    r8d, r8d
0x18001b9cd  jnz     short loc_18001B9DF
0x18001b9cf  mov     r8d, ebp
0x18001b9d2  mov     edx, 3
0x18001b9d7  mov     rcx, rsi
0x18001b9da  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001b9df  mov     ecx, [rdi]
0x18001b9e1  test    cl, 2
0x18001b9e4  jnz     short loc_18001B9F6
0x18001b9e6  and     ecx, 0FFFFF63Eh
0x18001b9ec  and     ebx, 9C1h
0x18001b9f2  or      ecx, ebx
0x18001b9f4  mov     [rdi], ecx
0x18001b9f6  mov     rax, rdi
0x18001b9f9  mov     rcx, [rsp+68h+var_38]
0x18001b9fe  xor     rcx, rsp; StackCookie
0x18001ba01  call    __security_check_cookie
0x18001ba06  add     rsp, 48h
0x18001ba0a  pop     rdi
0x18001ba0b  pop     rsi
0x18001ba0c  pop     rbp
0x18001ba0d  pop     rbx
0x18001ba0e  retn
```
