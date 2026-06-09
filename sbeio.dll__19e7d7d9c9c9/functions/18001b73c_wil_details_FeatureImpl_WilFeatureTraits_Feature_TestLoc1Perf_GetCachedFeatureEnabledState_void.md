# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x18001b73c`
- end: `0x18001b827`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020628`
- `0x18002705c`

## callees

- `0x1800015f0`
- `0x18001aba4`
- `0x18001b73c`
- `0x18001bfac`
- `0x180026a48`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(v5, &v12, &v13);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestLoc1Perf__descriptor, v10, v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_TestLoc1Perf__descriptor,
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
0x18001b73c  push    rbx
0x18001b73e  push    rbp
0x18001b73f  push    rsi
0x18001b740  push    rdi
0x18001b741  sub     rsp, 48h
0x18001b745  mov     rax, cs:__security_cookie
0x18001b74c  xor     rax, rsp
0x18001b74f  mov     [rsp+68h+var_38], rax
0x18001b754  mov     rsi, cs:Feature_TestLoc1Perf__descriptor
0x18001b75b  mov     rdi, rdx
0x18001b75e  mov     qword ptr [rdx], 0
0x18001b765  mov     eax, [rsi]
0x18001b767  mov     [rdx], eax
0x18001b769  and     eax, 6
0x18001b76c  cmp     al, 6
0x18001b76e  jz      loc_18001B80E
0x18001b774  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001b779  lea     r8, [rsp+68h+var_40]
0x18001b77e  mov     [rsp+68h+var_40], 0
0x18001b786  lea     rdx, [rsp+68h+var_48]
0x18001b78b  mov     ebp, eax
0x18001b78d  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x18001b792  mov     eax, [rdi]
0x18001b794  mov     rbx, [rsp+68h+var_48]
0x18001b799  cmp     [rsp+68h+var_40], 0
0x18001b79e  mov     edx, eax
0x18001b7a0  mov     [rdi], eax
0x18001b7a2  mov     ecx, eax
0x18001b7a4  jz      short loc_18001B7BF
0x18001b7a6  test    dl, 2
0x18001b7a9  jnz     short loc_18001B7BF
0x18001b7ab  and     ecx, 0FFFFF63Eh
0x18001b7b1  mov     eax, ebx
0x18001b7b3  and     eax, 9C1h
0x18001b7b8  or      ecx, eax
0x18001b7ba  or      ecx, 2
0x18001b7bd  mov     [rdi], ecx
0x18001b7bf  mov     r8d, edx
0x18001b7c2  and     r8d, 4
0x18001b7c6  jnz     short loc_18001B7DA
0x18001b7c8  btr     ecx, 0Ah
0x18001b7cc  mov     eax, ebx
0x18001b7ce  and     eax, 400h
0x18001b7d3  or      ecx, eax
0x18001b7d5  or      ecx, 4
0x18001b7d8  mov     [rdi], ecx
0x18001b7da  mov     eax, edx
0x18001b7dc  lock cmpxchg [rsi], ecx
0x18001b7e0  jnz     short loc_18001B799
0x18001b7e2  test    r8d, r8d
0x18001b7e5  jnz     short loc_18001B7F7
0x18001b7e7  mov     r8d, ebp
0x18001b7ea  mov     edx, 3
0x18001b7ef  mov     rcx, rsi
0x18001b7f2  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001b7f7  mov     ecx, [rdi]
0x18001b7f9  test    cl, 2
0x18001b7fc  jnz     short loc_18001B80E
0x18001b7fe  and     ecx, 0FFFFF63Eh
0x18001b804  and     ebx, 9C1h
0x18001b80a  or      ecx, ebx
0x18001b80c  mov     [rdi], ecx
0x18001b80e  mov     rax, rdi
0x18001b811  mov     rcx, [rsp+68h+var_38]
0x18001b816  xor     rcx, rsp; StackCookie
0x18001b819  call    __security_check_cookie
0x18001b81e  add     rsp, 48h
0x18001b822  pop     rdi
0x18001b823  pop     rsi
0x18001b824  pop     rbp
0x18001b825  pop     rbx
0x18001b826  retn
```
