# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180015d0c`
- end: `0x180015df8`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016a64`

## callees

- `0x180008a90`
- `0x18000cdac`
- `0x180010298`
- `0x180015d0c`
- `0x1800162d8`

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
0x180015d0c  push    rbx
0x180015d0e  push    rbp
0x180015d0f  push    rsi
0x180015d10  push    rdi
0x180015d11  sub     rsp, 48h
0x180015d15  mov     rax, cs:__security_cookie
0x180015d1c  xor     rax, rsp
0x180015d1f  mov     [rsp+68h+var_38], rax
0x180015d24  mov     rsi, cs:Feature_ValLabTest__descriptor
0x180015d2b  mov     rdi, rdx
0x180015d2e  mov     qword ptr [rdx], 0
0x180015d35  mov     eax, [rsi]
0x180015d37  mov     [rdx], eax
0x180015d39  and     eax, 6
0x180015d3c  cmp     al, 6
0x180015d3e  jz      loc_180015DDE
0x180015d44  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180015d49  lea     r8, [rsp+68h+var_40]
0x180015d4e  mov     [rsp+68h+var_40], 0
0x180015d56  lea     rdx, [rsp+68h+var_48]
0x180015d5b  mov     ebp, eax
0x180015d5d  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(int *)
0x180015d62  mov     eax, [rdi]
0x180015d64  mov     rbx, [rsp+68h+var_48]
0x180015d69  cmp     [rsp+68h+var_40], 0
0x180015d6e  mov     edx, eax
0x180015d70  mov     [rdi], eax
0x180015d72  mov     ecx, eax
0x180015d74  jz      short loc_180015D8F
0x180015d76  test    dl, 2
0x180015d79  jnz     short loc_180015D8F
0x180015d7b  and     ecx, 0FFFFF63Eh
0x180015d81  mov     eax, ebx
0x180015d83  and     eax, 9C1h
0x180015d88  or      ecx, eax
0x180015d8a  or      ecx, 2
0x180015d8d  mov     [rdi], ecx
0x180015d8f  mov     r8d, edx
0x180015d92  and     r8d, 4
0x180015d96  jnz     short loc_180015DAA
0x180015d98  btr     ecx, 0Ah
0x180015d9c  mov     eax, ebx
0x180015d9e  and     eax, 400h
0x180015da3  or      ecx, eax
0x180015da5  or      ecx, 4
0x180015da8  mov     [rdi], ecx
0x180015daa  mov     eax, edx
0x180015dac  lock cmpxchg [rsi], ecx
0x180015db0  jnz     short loc_180015D69
0x180015db2  test    r8d, r8d
0x180015db5  jnz     short loc_180015DC7
0x180015db7  mov     r8d, ebp
0x180015dba  mov     edx, 3
0x180015dbf  mov     rcx, rsi
0x180015dc2  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180015dc7  mov     ecx, [rdi]
0x180015dc9  test    cl, 2
0x180015dcc  jnz     short loc_180015DDE
0x180015dce  and     ecx, 0FFFFF63Eh
0x180015dd4  and     ebx, 9C1h
0x180015dda  or      ecx, ebx
0x180015ddc  mov     [rdi], ecx
0x180015dde  mov     rax, rdi
0x180015de1  mov     rcx, [rsp+68h+var_38]
0x180015de6  xor     rcx, rsp; StackCookie
0x180015de9  call    __security_check_cookie
0x180015dee  add     rsp, 48h
0x180015df2  pop     rdi
0x180015df3  pop     rsi
0x180015df4  pop     rbp
0x180015df5  pop     rbx
0x180015df6  retn
```
