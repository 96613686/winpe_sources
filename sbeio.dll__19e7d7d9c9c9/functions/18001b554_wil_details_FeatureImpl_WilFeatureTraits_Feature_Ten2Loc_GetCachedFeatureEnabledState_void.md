# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(void)

- ea: `0x18001b554`
- end: `0x18001b63f`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800204e0`
- `0x180026fe4`

## callees

- `0x1800015f0`
- `0x18001aba4`
- `0x18001b554`
- `0x18001bde4`
- `0x180026a48`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(v5, &v12, &v13);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Ten2Loc__descriptor, v10, v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Ten2Loc__descriptor,
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
0x18001b554  push    rbx
0x18001b556  push    rbp
0x18001b557  push    rsi
0x18001b558  push    rdi
0x18001b559  sub     rsp, 48h
0x18001b55d  mov     rax, cs:__security_cookie
0x18001b564  xor     rax, rsp
0x18001b567  mov     [rsp+68h+var_38], rax
0x18001b56c  mov     rsi, cs:Feature_Ten2Loc__descriptor
0x18001b573  mov     rdi, rdx
0x18001b576  mov     qword ptr [rdx], 0
0x18001b57d  mov     eax, [rsi]
0x18001b57f  mov     [rdx], eax
0x18001b581  and     eax, 6
0x18001b584  cmp     al, 6
0x18001b586  jz      loc_18001B626
0x18001b58c  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001b591  lea     r8, [rsp+68h+var_40]
0x18001b596  mov     [rsp+68h+var_40], 0
0x18001b59e  lea     rdx, [rsp+68h+var_48]
0x18001b5a3  mov     ebp, eax
0x18001b5a5  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)
0x18001b5aa  mov     eax, [rdi]
0x18001b5ac  mov     rbx, [rsp+68h+var_48]
0x18001b5b1  cmp     [rsp+68h+var_40], 0
0x18001b5b6  mov     edx, eax
0x18001b5b8  mov     [rdi], eax
0x18001b5ba  mov     ecx, eax
0x18001b5bc  jz      short loc_18001B5D7
0x18001b5be  test    dl, 2
0x18001b5c1  jnz     short loc_18001B5D7
0x18001b5c3  and     ecx, 0FFFFF63Eh
0x18001b5c9  mov     eax, ebx
0x18001b5cb  and     eax, 9C1h
0x18001b5d0  or      ecx, eax
0x18001b5d2  or      ecx, 2
0x18001b5d5  mov     [rdi], ecx
0x18001b5d7  mov     r8d, edx
0x18001b5da  and     r8d, 4
0x18001b5de  jnz     short loc_18001B5F2
0x18001b5e0  btr     ecx, 0Ah
0x18001b5e4  mov     eax, ebx
0x18001b5e6  and     eax, 400h
0x18001b5eb  or      ecx, eax
0x18001b5ed  or      ecx, 4
0x18001b5f0  mov     [rdi], ecx
0x18001b5f2  mov     eax, edx
0x18001b5f4  lock cmpxchg [rsi], ecx
0x18001b5f8  jnz     short loc_18001B5B1
0x18001b5fa  test    r8d, r8d
0x18001b5fd  jnz     short loc_18001B60F
0x18001b5ff  mov     r8d, ebp
0x18001b602  mov     edx, 3
0x18001b607  mov     rcx, rsi
0x18001b60a  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001b60f  mov     ecx, [rdi]
0x18001b611  test    cl, 2
0x18001b614  jnz     short loc_18001B626
0x18001b616  and     ecx, 0FFFFF63Eh
0x18001b61c  and     ebx, 9C1h
0x18001b622  or      ecx, ebx
0x18001b624  mov     [rdi], ecx
0x18001b626  mov     rax, rdi
0x18001b629  mov     rcx, [rsp+68h+var_38]
0x18001b62e  xor     rcx, rsp; StackCookie
0x18001b631  call    __security_check_cookie
0x18001b636  add     rsp, 48h
0x18001b63a  pop     rdi
0x18001b63b  pop     rsi
0x18001b63c  pop     rbp
0x18001b63d  pop     rbx
0x18001b63e  retn
```
