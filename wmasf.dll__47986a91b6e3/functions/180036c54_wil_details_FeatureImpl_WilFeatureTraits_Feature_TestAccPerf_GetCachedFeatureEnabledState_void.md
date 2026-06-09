# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x180036c54`
- end: `0x180036d3f`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003a0a0`
- `0x18003bf00`

## callees

- `0x1800015d0`
- `0x180036170`
- `0x180036c54`
- `0x1800373c8`
- `0x18003b548`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(v5, &v12, &v13);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestAccPerf__descriptor, v10, v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_TestAccPerf__descriptor,
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
0x180036c54  push    rbx
0x180036c56  push    rbp
0x180036c57  push    rsi
0x180036c58  push    rdi
0x180036c59  sub     rsp, 48h
0x180036c5d  mov     rax, cs:__security_cookie
0x180036c64  xor     rax, rsp
0x180036c67  mov     [rsp+68h+var_38], rax
0x180036c6c  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x180036c73  mov     rdi, rdx
0x180036c76  mov     qword ptr [rdx], 0
0x180036c7d  mov     eax, [rsi]
0x180036c7f  mov     [rdx], eax
0x180036c81  and     eax, 6
0x180036c84  cmp     al, 6
0x180036c86  jz      loc_180036D26
0x180036c8c  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180036c91  lea     r8, [rsp+68h+var_40]
0x180036c96  mov     [rsp+68h+var_40], 0
0x180036c9e  lea     rdx, [rsp+68h+var_48]
0x180036ca3  mov     ebp, eax
0x180036ca5  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x180036caa  mov     eax, [rdi]
0x180036cac  mov     rbx, [rsp+68h+var_48]
0x180036cb1  cmp     [rsp+68h+var_40], 0
0x180036cb6  mov     edx, eax
0x180036cb8  mov     [rdi], eax
0x180036cba  mov     ecx, eax
0x180036cbc  jz      short loc_180036CD7
0x180036cbe  test    dl, 2
0x180036cc1  jnz     short loc_180036CD7
0x180036cc3  and     ecx, 0FFFFF63Eh
0x180036cc9  mov     eax, ebx
0x180036ccb  and     eax, 9C1h
0x180036cd0  or      ecx, eax
0x180036cd2  or      ecx, 2
0x180036cd5  mov     [rdi], ecx
0x180036cd7  mov     r8d, edx
0x180036cda  and     r8d, 4
0x180036cde  jnz     short loc_180036CF2
0x180036ce0  btr     ecx, 0Ah
0x180036ce4  mov     eax, ebx
0x180036ce6  and     eax, 400h
0x180036ceb  or      ecx, eax
0x180036ced  or      ecx, 4
0x180036cf0  mov     [rdi], ecx
0x180036cf2  mov     eax, edx
0x180036cf4  lock cmpxchg [rsi], ecx
0x180036cf8  jnz     short loc_180036CB1
0x180036cfa  test    r8d, r8d
0x180036cfd  jnz     short loc_180036D0F
0x180036cff  mov     r8d, ebp
0x180036d02  mov     edx, 3
0x180036d07  mov     rcx, rsi
0x180036d0a  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180036d0f  mov     ecx, [rdi]
0x180036d11  test    cl, 2
0x180036d14  jnz     short loc_180036D26
0x180036d16  and     ecx, 0FFFFF63Eh
0x180036d1c  and     ebx, 9C1h
0x180036d22  or      ecx, ebx
0x180036d24  mov     [rdi], ecx
0x180036d26  mov     rax, rdi
0x180036d29  mov     rcx, [rsp+68h+var_38]
0x180036d2e  xor     rcx, rsp; StackCookie
0x180036d31  call    __security_check_cookie
0x180036d36  add     rsp, 48h
0x180036d3a  pop     rdi
0x180036d3b  pop     rsi
0x180036d3c  pop     rbp
0x180036d3d  pop     rbx
0x180036d3e  retn
```
