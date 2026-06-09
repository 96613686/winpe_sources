# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x18001b648`
- end: `0x18001b733`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020584`
- `0x180027020`

## callees

- `0x1800015f0`
- `0x18001aba4`
- `0x18001b648`
- `0x18001bec8`
- `0x180026a48`

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
0x18001b648  push    rbx
0x18001b64a  push    rbp
0x18001b64b  push    rsi
0x18001b64c  push    rdi
0x18001b64d  sub     rsp, 48h
0x18001b651  mov     rax, cs:__security_cookie
0x18001b658  xor     rax, rsp
0x18001b65b  mov     [rsp+68h+var_38], rax
0x18001b660  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x18001b667  mov     rdi, rdx
0x18001b66a  mov     qword ptr [rdx], 0
0x18001b671  mov     eax, [rsi]
0x18001b673  mov     [rdx], eax
0x18001b675  and     eax, 6
0x18001b678  cmp     al, 6
0x18001b67a  jz      loc_18001B71A
0x18001b680  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001b685  lea     r8, [rsp+68h+var_40]
0x18001b68a  mov     [rsp+68h+var_40], 0
0x18001b692  lea     rdx, [rsp+68h+var_48]
0x18001b697  mov     ebp, eax
0x18001b699  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x18001b69e  mov     eax, [rdi]
0x18001b6a0  mov     rbx, [rsp+68h+var_48]
0x18001b6a5  cmp     [rsp+68h+var_40], 0
0x18001b6aa  mov     edx, eax
0x18001b6ac  mov     [rdi], eax
0x18001b6ae  mov     ecx, eax
0x18001b6b0  jz      short loc_18001B6CB
0x18001b6b2  test    dl, 2
0x18001b6b5  jnz     short loc_18001B6CB
0x18001b6b7  and     ecx, 0FFFFF63Eh
0x18001b6bd  mov     eax, ebx
0x18001b6bf  and     eax, 9C1h
0x18001b6c4  or      ecx, eax
0x18001b6c6  or      ecx, 2
0x18001b6c9  mov     [rdi], ecx
0x18001b6cb  mov     r8d, edx
0x18001b6ce  and     r8d, 4
0x18001b6d2  jnz     short loc_18001B6E6
0x18001b6d4  btr     ecx, 0Ah
0x18001b6d8  mov     eax, ebx
0x18001b6da  and     eax, 400h
0x18001b6df  or      ecx, eax
0x18001b6e1  or      ecx, 4
0x18001b6e4  mov     [rdi], ecx
0x18001b6e6  mov     eax, edx
0x18001b6e8  lock cmpxchg [rsi], ecx
0x18001b6ec  jnz     short loc_18001B6A5
0x18001b6ee  test    r8d, r8d
0x18001b6f1  jnz     short loc_18001B703
0x18001b6f3  mov     r8d, ebp
0x18001b6f6  mov     edx, 3
0x18001b6fb  mov     rcx, rsi
0x18001b6fe  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001b703  mov     ecx, [rdi]
0x18001b705  test    cl, 2
0x18001b708  jnz     short loc_18001B71A
0x18001b70a  and     ecx, 0FFFFF63Eh
0x18001b710  and     ebx, 9C1h
0x18001b716  or      ecx, ebx
0x18001b718  mov     [rdi], ecx
0x18001b71a  mov     rax, rdi
0x18001b71d  mov     rcx, [rsp+68h+var_38]
0x18001b722  xor     rcx, rsp; StackCookie
0x18001b725  call    __security_check_cookie
0x18001b72a  add     rsp, 48h
0x18001b72e  pop     rdi
0x18001b72f  pop     rsi
0x18001b730  pop     rbp
0x18001b731  pop     rbx
0x18001b732  retn
```
