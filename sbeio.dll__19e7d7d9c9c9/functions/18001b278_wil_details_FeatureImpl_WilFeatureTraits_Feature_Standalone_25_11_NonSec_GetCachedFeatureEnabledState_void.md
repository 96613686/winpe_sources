# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18001b278`
- end: `0x18001b363`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002030c`

## callees

- `0x1800015f0`
- `0x18001aba4`
- `0x18001b278`
- `0x18001bc88`
- `0x180026a48`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(
      v5,
      &v12,
      &v13);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor, v10, v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor,
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
0x18001b278  push    rbx
0x18001b27a  push    rbp
0x18001b27b  push    rsi
0x18001b27c  push    rdi
0x18001b27d  sub     rsp, 48h
0x18001b281  mov     rax, cs:__security_cookie
0x18001b288  xor     rax, rsp
0x18001b28b  mov     [rsp+68h+var_38], rax
0x18001b290  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x18001b297  mov     rdi, rdx
0x18001b29a  mov     qword ptr [rdx], 0
0x18001b2a1  mov     eax, [rsi]
0x18001b2a3  mov     [rdx], eax
0x18001b2a5  and     eax, 6
0x18001b2a8  cmp     al, 6
0x18001b2aa  jz      loc_18001B34A
0x18001b2b0  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001b2b5  lea     r8, [rsp+68h+var_40]
0x18001b2ba  mov     [rsp+68h+var_40], 0
0x18001b2c2  lea     rdx, [rsp+68h+var_48]
0x18001b2c7  mov     ebp, eax
0x18001b2c9  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(int *)
0x18001b2ce  mov     eax, [rdi]
0x18001b2d0  mov     rbx, [rsp+68h+var_48]
0x18001b2d5  cmp     [rsp+68h+var_40], 0
0x18001b2da  mov     edx, eax
0x18001b2dc  mov     [rdi], eax
0x18001b2de  mov     ecx, eax
0x18001b2e0  jz      short loc_18001B2FB
0x18001b2e2  test    dl, 2
0x18001b2e5  jnz     short loc_18001B2FB
0x18001b2e7  and     ecx, 0FFFFF63Eh
0x18001b2ed  mov     eax, ebx
0x18001b2ef  and     eax, 9C1h
0x18001b2f4  or      ecx, eax
0x18001b2f6  or      ecx, 2
0x18001b2f9  mov     [rdi], ecx
0x18001b2fb  mov     r8d, edx
0x18001b2fe  and     r8d, 4
0x18001b302  jnz     short loc_18001B316
0x18001b304  btr     ecx, 0Ah
0x18001b308  mov     eax, ebx
0x18001b30a  and     eax, 400h
0x18001b30f  or      ecx, eax
0x18001b311  or      ecx, 4
0x18001b314  mov     [rdi], ecx
0x18001b316  mov     eax, edx
0x18001b318  lock cmpxchg [rsi], ecx
0x18001b31c  jnz     short loc_18001B2D5
0x18001b31e  test    r8d, r8d
0x18001b321  jnz     short loc_18001B333
0x18001b323  mov     r8d, ebp
0x18001b326  mov     edx, 3
0x18001b32b  mov     rcx, rsi
0x18001b32e  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001b333  mov     ecx, [rdi]
0x18001b335  test    cl, 2
0x18001b338  jnz     short loc_18001B34A
0x18001b33a  and     ecx, 0FFFFF63Eh
0x18001b340  and     ebx, 9C1h
0x18001b346  or      ecx, ebx
0x18001b348  mov     [rdi], ecx
0x18001b34a  mov     rax, rdi
0x18001b34d  mov     rcx, [rsp+68h+var_38]
0x18001b352  xor     rcx, rsp; StackCookie
0x18001b355  call    __security_check_cookie
0x18001b35a  add     rsp, 48h
0x18001b35e  pop     rdi
0x18001b35f  pop     rsi
0x18001b360  pop     rbp
0x18001b361  pop     rbx
0x18001b362  retn
```
