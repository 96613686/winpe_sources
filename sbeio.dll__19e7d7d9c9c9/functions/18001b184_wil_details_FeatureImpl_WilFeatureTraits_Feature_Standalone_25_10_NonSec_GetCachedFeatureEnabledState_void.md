# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18001b184`
- end: `0x18001b26f`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020270`

## callees

- `0x1800015f0`
- `0x18001aba4`
- `0x18001b184`
- `0x18001bc14`
- `0x180026a48`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor, v10, v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor,
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
0x18001b184  push    rbx
0x18001b186  push    rbp
0x18001b187  push    rsi
0x18001b188  push    rdi
0x18001b189  sub     rsp, 48h
0x18001b18d  mov     rax, cs:__security_cookie
0x18001b194  xor     rax, rsp
0x18001b197  mov     [rsp+68h+var_38], rax
0x18001b19c  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x18001b1a3  mov     rdi, rdx
0x18001b1a6  mov     qword ptr [rdx], 0
0x18001b1ad  mov     eax, [rsi]
0x18001b1af  mov     [rdx], eax
0x18001b1b1  and     eax, 6
0x18001b1b4  cmp     al, 6
0x18001b1b6  jz      loc_18001B256
0x18001b1bc  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001b1c1  lea     r8, [rsp+68h+var_40]
0x18001b1c6  mov     [rsp+68h+var_40], 0
0x18001b1ce  lea     rdx, [rsp+68h+var_48]
0x18001b1d3  mov     ebp, eax
0x18001b1d5  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(int *)
0x18001b1da  mov     eax, [rdi]
0x18001b1dc  mov     rbx, [rsp+68h+var_48]
0x18001b1e1  cmp     [rsp+68h+var_40], 0
0x18001b1e6  mov     edx, eax
0x18001b1e8  mov     [rdi], eax
0x18001b1ea  mov     ecx, eax
0x18001b1ec  jz      short loc_18001B207
0x18001b1ee  test    dl, 2
0x18001b1f1  jnz     short loc_18001B207
0x18001b1f3  and     ecx, 0FFFFF63Eh
0x18001b1f9  mov     eax, ebx
0x18001b1fb  and     eax, 9C1h
0x18001b200  or      ecx, eax
0x18001b202  or      ecx, 2
0x18001b205  mov     [rdi], ecx
0x18001b207  mov     r8d, edx
0x18001b20a  and     r8d, 4
0x18001b20e  jnz     short loc_18001B222
0x18001b210  btr     ecx, 0Ah
0x18001b214  mov     eax, ebx
0x18001b216  and     eax, 400h
0x18001b21b  or      ecx, eax
0x18001b21d  or      ecx, 4
0x18001b220  mov     [rdi], ecx
0x18001b222  mov     eax, edx
0x18001b224  lock cmpxchg [rsi], ecx
0x18001b228  jnz     short loc_18001B1E1
0x18001b22a  test    r8d, r8d
0x18001b22d  jnz     short loc_18001B23F
0x18001b22f  mov     r8d, ebp
0x18001b232  mov     edx, 3
0x18001b237  mov     rcx, rsi
0x18001b23a  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001b23f  mov     ecx, [rdi]
0x18001b241  test    cl, 2
0x18001b244  jnz     short loc_18001B256
0x18001b246  and     ecx, 0FFFFF63Eh
0x18001b24c  and     ebx, 9C1h
0x18001b252  or      ecx, ebx
0x18001b254  mov     [rdi], ecx
0x18001b256  mov     rax, rdi
0x18001b259  mov     rcx, [rsp+68h+var_38]
0x18001b25e  xor     rcx, rsp; StackCookie
0x18001b261  call    __security_check_cookie
0x18001b266  add     rsp, 48h
0x18001b26a  pop     rdi
0x18001b26b  pop     rsi
0x18001b26c  pop     rbp
0x18001b26d  pop     rbx
0x18001b26e  retn
```
