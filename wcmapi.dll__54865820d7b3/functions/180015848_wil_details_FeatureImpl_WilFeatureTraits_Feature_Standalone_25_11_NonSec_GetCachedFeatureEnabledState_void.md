# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180015848`
- end: `0x180015934`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016740`

## callees

- `0x180008a90`
- `0x18000cdac`
- `0x180010298`
- `0x180015848`
- `0x180015f40`

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
0x180015848  push    rbx
0x18001584a  push    rbp
0x18001584b  push    rsi
0x18001584c  push    rdi
0x18001584d  sub     rsp, 48h
0x180015851  mov     rax, cs:__security_cookie
0x180015858  xor     rax, rsp
0x18001585b  mov     [rsp+68h+var_38], rax
0x180015860  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x180015867  mov     rdi, rdx
0x18001586a  mov     qword ptr [rdx], 0
0x180015871  mov     eax, [rsi]
0x180015873  mov     [rdx], eax
0x180015875  and     eax, 6
0x180015878  cmp     al, 6
0x18001587a  jz      loc_18001591A
0x180015880  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180015885  lea     r8, [rsp+68h+var_40]
0x18001588a  mov     [rsp+68h+var_40], 0
0x180015892  lea     rdx, [rsp+68h+var_48]
0x180015897  mov     ebp, eax
0x180015899  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(int *)
0x18001589e  mov     eax, [rdi]
0x1800158a0  mov     rbx, [rsp+68h+var_48]
0x1800158a5  cmp     [rsp+68h+var_40], 0
0x1800158aa  mov     edx, eax
0x1800158ac  mov     [rdi], eax
0x1800158ae  mov     ecx, eax
0x1800158b0  jz      short loc_1800158CB
0x1800158b2  test    dl, 2
0x1800158b5  jnz     short loc_1800158CB
0x1800158b7  and     ecx, 0FFFFF63Eh
0x1800158bd  mov     eax, ebx
0x1800158bf  and     eax, 9C1h
0x1800158c4  or      ecx, eax
0x1800158c6  or      ecx, 2
0x1800158c9  mov     [rdi], ecx
0x1800158cb  mov     r8d, edx
0x1800158ce  and     r8d, 4
0x1800158d2  jnz     short loc_1800158E6
0x1800158d4  btr     ecx, 0Ah
0x1800158d8  mov     eax, ebx
0x1800158da  and     eax, 400h
0x1800158df  or      ecx, eax
0x1800158e1  or      ecx, 4
0x1800158e4  mov     [rdi], ecx
0x1800158e6  mov     eax, edx
0x1800158e8  lock cmpxchg [rsi], ecx
0x1800158ec  jnz     short loc_1800158A5
0x1800158ee  test    r8d, r8d
0x1800158f1  jnz     short loc_180015903
0x1800158f3  mov     r8d, ebp
0x1800158f6  mov     edx, 3
0x1800158fb  mov     rcx, rsi
0x1800158fe  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180015903  mov     ecx, [rdi]
0x180015905  test    cl, 2
0x180015908  jnz     short loc_18001591A
0x18001590a  and     ecx, 0FFFFF63Eh
0x180015910  and     ebx, 9C1h
0x180015916  or      ecx, ebx
0x180015918  mov     [rdi], ecx
0x18001591a  mov     rax, rdi
0x18001591d  mov     rcx, [rsp+68h+var_38]
0x180015922  xor     rcx, rsp; StackCookie
0x180015925  call    __security_check_cookie
0x18001592a  add     rsp, 48h
0x18001592e  pop     rdi
0x18001592f  pop     rsi
0x180015930  pop     rbp
0x180015931  pop     rbx
0x180015932  retn
```
