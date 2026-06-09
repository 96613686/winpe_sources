# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18001b36c`
- end: `0x18001b457`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800203a8`

## callees

- `0x1800015f0`
- `0x18001aba4`
- `0x18001b36c`
- `0x18001bcfc`
- `0x180026a48`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor, v10, v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor,
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
0x18001b36c  push    rbx
0x18001b36e  push    rbp
0x18001b36f  push    rsi
0x18001b370  push    rdi
0x18001b371  sub     rsp, 48h
0x18001b375  mov     rax, cs:__security_cookie
0x18001b37c  xor     rax, rsp
0x18001b37f  mov     [rsp+68h+var_38], rax
0x18001b384  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x18001b38b  mov     rdi, rdx
0x18001b38e  mov     qword ptr [rdx], 0
0x18001b395  mov     eax, [rsi]
0x18001b397  mov     [rdx], eax
0x18001b399  and     eax, 6
0x18001b39c  cmp     al, 6
0x18001b39e  jz      loc_18001B43E
0x18001b3a4  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001b3a9  lea     r8, [rsp+68h+var_40]
0x18001b3ae  mov     [rsp+68h+var_40], 0
0x18001b3b6  lea     rdx, [rsp+68h+var_48]
0x18001b3bb  mov     ebp, eax
0x18001b3bd  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(int *)
0x18001b3c2  mov     eax, [rdi]
0x18001b3c4  mov     rbx, [rsp+68h+var_48]
0x18001b3c9  cmp     [rsp+68h+var_40], 0
0x18001b3ce  mov     edx, eax
0x18001b3d0  mov     [rdi], eax
0x18001b3d2  mov     ecx, eax
0x18001b3d4  jz      short loc_18001B3EF
0x18001b3d6  test    dl, 2
0x18001b3d9  jnz     short loc_18001B3EF
0x18001b3db  and     ecx, 0FFFFF63Eh
0x18001b3e1  mov     eax, ebx
0x18001b3e3  and     eax, 9C1h
0x18001b3e8  or      ecx, eax
0x18001b3ea  or      ecx, 2
0x18001b3ed  mov     [rdi], ecx
0x18001b3ef  mov     r8d, edx
0x18001b3f2  and     r8d, 4
0x18001b3f6  jnz     short loc_18001B40A
0x18001b3f8  btr     ecx, 0Ah
0x18001b3fc  mov     eax, ebx
0x18001b3fe  and     eax, 400h
0x18001b403  or      ecx, eax
0x18001b405  or      ecx, 4
0x18001b408  mov     [rdi], ecx
0x18001b40a  mov     eax, edx
0x18001b40c  lock cmpxchg [rsi], ecx
0x18001b410  jnz     short loc_18001B3C9
0x18001b412  test    r8d, r8d
0x18001b415  jnz     short loc_18001B427
0x18001b417  mov     r8d, ebp
0x18001b41a  mov     edx, 3
0x18001b41f  mov     rcx, rsi
0x18001b422  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001b427  mov     ecx, [rdi]
0x18001b429  test    cl, 2
0x18001b42c  jnz     short loc_18001B43E
0x18001b42e  and     ecx, 0FFFFF63Eh
0x18001b434  and     ebx, 9C1h
0x18001b43a  or      ecx, ebx
0x18001b43c  mov     [rdi], ecx
0x18001b43e  mov     rax, rdi
0x18001b441  mov     rcx, [rsp+68h+var_38]
0x18001b446  xor     rcx, rsp; StackCookie
0x18001b449  call    __security_check_cookie
0x18001b44e  add     rsp, 48h
0x18001b452  pop     rdi
0x18001b453  pop     rsi
0x18001b454  pop     rbp
0x18001b455  pop     rbx
0x18001b456  retn
```
