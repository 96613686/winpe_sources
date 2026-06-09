# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs>::GetCachedFeatureEnabledState(void)

- ea: `0x14001a220`
- end: `0x14001a30a`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `234`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001a0dc`
- `0x14001a310`

## callees

- `0x140005090`
- `0x140005154`
- `0x14001a220`
- `0x14001a3b0`
- `0x14001aa60`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v5; // ebp
  __int64 v6; // rcx
  signed __int32 v7; // eax
  __int16 v8; // bx
  bool v9; // zf
  signed __int32 v10; // edx
  unsigned int v11; // ecx
  __int64 v13; // [rsp+20h] [rbp-38h] BYREF
  int v14; // [rsp+28h] [rbp-30h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)a1;
  *(_DWORD *)a2 = *(_DWORD *)a1;
  if ( (v3 & 6) != 6 )
  {
    v14 = 0;
    v5 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs>::GetCurrentFeatureEnabledState(
      v6,
      &v13,
      &v14);
    v7 = *(_DWORD *)a2;
    v8 = v13;
    do
    {
      v9 = v14 == 0;
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)a1, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges((volatile signed __int32 *)a1, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x14001a220  mov     [rsp+arg_10], rbx
0x14001a225  push    rbp
0x14001a226  push    rsi
0x14001a227  push    rdi
0x14001a228  sub     rsp, 40h
0x14001a22c  mov     rax, cs:__security_cookie
0x14001a233  xor     rax, rsp
0x14001a236  mov     [rsp+58h+var_28], rax
0x14001a23b  mov     qword ptr [rdx], 0
0x14001a242  mov     rdi, rdx
0x14001a245  mov     eax, [rcx]
0x14001a247  mov     rsi, rcx
0x14001a24a  mov     [rdx], eax
0x14001a24c  and     eax, 6
0x14001a24f  cmp     al, 6
0x14001a251  jz      loc_14001A2ED
0x14001a257  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14001a25c  lea     r8, [rsp+58h+var_30]
0x14001a261  mov     [rsp+58h+var_30], 0
0x14001a269  lea     rdx, [rsp+58h+var_38]
0x14001a26e  mov     ebp, eax
0x14001a270  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs>::GetCurrentFeatureEnabledState(int *)
0x14001a275  mov     eax, [rdi]
0x14001a277  mov     rbx, [rsp+58h+var_38]
0x14001a27c  cmp     [rsp+58h+var_30], 0
0x14001a281  mov     edx, eax
0x14001a283  mov     [rdi], eax
0x14001a285  mov     ecx, eax
0x14001a287  jz      short loc_14001A2A2
0x14001a289  test    dl, 2
0x14001a28c  jnz     short loc_14001A2A2
0x14001a28e  and     ecx, 0FFFFF63Eh
0x14001a294  mov     eax, ebx
0x14001a296  and     eax, 9C1h
0x14001a29b  or      ecx, eax
0x14001a29d  or      ecx, 2
0x14001a2a0  mov     [rdi], ecx
0x14001a2a2  test    dl, 4
0x14001a2a5  jnz     short loc_14001A2B9
0x14001a2a7  btr     ecx, 0Ah
0x14001a2ab  mov     eax, ebx
0x14001a2ad  and     eax, 400h
0x14001a2b2  or      ecx, eax
0x14001a2b4  or      ecx, 4
0x14001a2b7  mov     [rdi], ecx
0x14001a2b9  mov     eax, edx
0x14001a2bb  lock cmpxchg [rsi], ecx
0x14001a2bf  jnz     short loc_14001A27C
0x14001a2c1  test    dl, 4
0x14001a2c4  jnz     short loc_14001A2D6
0x14001a2c6  mov     r8d, ebp
0x14001a2c9  mov     edx, 3
0x14001a2ce  mov     rcx, rsi
0x14001a2d1  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14001a2d6  mov     ecx, [rdi]
0x14001a2d8  test    cl, 2
0x14001a2db  jnz     short loc_14001A2ED
0x14001a2dd  and     ecx, 0FFFFF63Eh
0x14001a2e3  and     ebx, 9C1h
0x14001a2e9  or      ecx, ebx
0x14001a2eb  mov     [rdi], ecx
0x14001a2ed  mov     rax, rdi
0x14001a2f0  mov     rcx, [rsp+58h+var_28]
0x14001a2f5  xor     rcx, rsp; StackCookie
0x14001a2f8  call    __security_check_cookie
0x14001a2fd  mov     rbx, [rsp+58h+arg_10]
0x14001a302  add     rsp, 40h
0x14001a306  pop     rdi
0x14001a307  pop     rsi
0x14001a308  pop     rbp
0x14001a309  retn
```
