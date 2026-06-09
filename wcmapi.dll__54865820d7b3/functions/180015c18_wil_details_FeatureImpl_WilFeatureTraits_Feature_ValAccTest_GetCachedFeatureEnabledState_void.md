# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180015c18`
- end: `0x180015d04`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `236`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800169c0`
- `0x180016db4`

## callees

- `0x180008a90`
- `0x18000cdac`
- `0x180010298`
- `0x180015c18`
- `0x180016200`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValAccTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValAccTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(v5, &v12, &v13);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValAccTest__descriptor, v10, v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_ValAccTest__descriptor,
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
0x180015c18  push    rbx
0x180015c1a  push    rbp
0x180015c1b  push    rsi
0x180015c1c  push    rdi
0x180015c1d  sub     rsp, 48h
0x180015c21  mov     rax, cs:__security_cookie
0x180015c28  xor     rax, rsp
0x180015c2b  mov     [rsp+68h+var_38], rax
0x180015c30  mov     rsi, cs:Feature_ValAccTest__descriptor
0x180015c37  mov     rdi, rdx
0x180015c3a  mov     qword ptr [rdx], 0
0x180015c41  mov     eax, [rsi]
0x180015c43  mov     [rdx], eax
0x180015c45  and     eax, 6
0x180015c48  cmp     al, 6
0x180015c4a  jz      loc_180015CEA
0x180015c50  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180015c55  lea     r8, [rsp+68h+var_40]
0x180015c5a  mov     [rsp+68h+var_40], 0
0x180015c62  lea     rdx, [rsp+68h+var_48]
0x180015c67  mov     ebp, eax
0x180015c69  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x180015c6e  mov     eax, [rdi]
0x180015c70  mov     rbx, [rsp+68h+var_48]
0x180015c75  cmp     [rsp+68h+var_40], 0
0x180015c7a  mov     edx, eax
0x180015c7c  mov     [rdi], eax
0x180015c7e  mov     ecx, eax
0x180015c80  jz      short loc_180015C9B
0x180015c82  test    dl, 2
0x180015c85  jnz     short loc_180015C9B
0x180015c87  and     ecx, 0FFFFF63Eh
0x180015c8d  mov     eax, ebx
0x180015c8f  and     eax, 9C1h
0x180015c94  or      ecx, eax
0x180015c96  or      ecx, 2
0x180015c99  mov     [rdi], ecx
0x180015c9b  mov     r8d, edx
0x180015c9e  and     r8d, 4
0x180015ca2  jnz     short loc_180015CB6
0x180015ca4  btr     ecx, 0Ah
0x180015ca8  mov     eax, ebx
0x180015caa  and     eax, 400h
0x180015caf  or      ecx, eax
0x180015cb1  or      ecx, 4
0x180015cb4  mov     [rdi], ecx
0x180015cb6  mov     eax, edx
0x180015cb8  lock cmpxchg [rsi], ecx
0x180015cbc  jnz     short loc_180015C75
0x180015cbe  test    r8d, r8d
0x180015cc1  jnz     short loc_180015CD3
0x180015cc3  mov     r8d, ebp
0x180015cc6  mov     edx, 3
0x180015ccb  mov     rcx, rsi
0x180015cce  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180015cd3  mov     ecx, [rdi]
0x180015cd5  test    cl, 2
0x180015cd8  jnz     short loc_180015CEA
0x180015cda  and     ecx, 0FFFFF63Eh
0x180015ce0  and     ebx, 9C1h
0x180015ce6  or      ecx, ebx
0x180015ce8  mov     [rdi], ecx
0x180015cea  mov     rax, rdi
0x180015ced  mov     rcx, [rsp+68h+var_38]
0x180015cf2  xor     rcx, rsp; StackCookie
0x180015cf5  call    __security_check_cookie
0x180015cfa  add     rsp, 48h
0x180015cfe  pop     rdi
0x180015cff  pop     rsi
0x180015d00  pop     rbp
0x180015d01  pop     rbx
0x180015d02  retn
```
