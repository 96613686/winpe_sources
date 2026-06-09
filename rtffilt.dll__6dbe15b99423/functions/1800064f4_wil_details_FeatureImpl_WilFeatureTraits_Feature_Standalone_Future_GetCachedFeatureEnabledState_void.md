# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)

- ea: `0x1800064f4`
- end: `0x18000666b`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006970`
- `0x1800133b4`

## callees

- `0x180005dd8`
- `0x1800064f4`
- `0x18000b3d8`
- `0x18001b010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 (__fastcall *v5)(__int64, __int64, wil::details **); // rax
  int v6; // edx
  int v7; // eax
  int v8; // edi
  int v9; // eax
  bool v10; // zf
  signed __int32 v11; // edx
  signed __int32 v12; // ecx
  wil::details *v14; // [rsp+40h] [rbp+8h] BYREF

  v14 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(49453572, 3, &v14);
    }
    else
    {
      v6 = 0;
    }
    if ( (v6 & 0xFFFFFF3F) != 0 )
    {
      v7 = 0;
      if ( (v6 & 0xFFFFFF3F) == 2 )
        v7 = 64;
    }
    else
    {
      v7 = 64;
    }
    v8 = v7 | (8 * (v6 & 0x80 | (4 * (v6 & 0x40 | (4 * (v6 & 3))))));
    v9 = *(_DWORD *)a2;
    do
    {
      v10 = (_DWORD)v14 == 0;
      v11 = v9;
      *(_DWORD *)a2 = v9;
      if ( !v10 && (v9 & 2) == 0 )
      {
        v9 = (v9
            ^ ((unsigned __int16)v9
             ^ (unsigned __int16)v8)
            & 0x180
            ^ (v8
             ^ v9
             ^ ((unsigned __int16)v9
              ^ (unsigned __int16)v8)
             & 0x180)
            & 0x40
            | 1)
           ^ ((unsigned __int16)v8
            ^ ((unsigned __int16)(v9 ^ (v9 ^ v8) & 0x180 ^ (v8 ^ v9 ^ (v9 ^ v8) & 0x180) & 0x40) | 1))
           & 0x800
           | 2;
        *(_DWORD *)a2 = v9;
      }
      if ( (v11 & 4) != 0 )
      {
        v12 = v9;
      }
      else
      {
        v12 = v9 ^ ((unsigned __int16)v9 ^ (unsigned __int16)v8) & 0x400 | 4;
        *(_DWORD *)a2 = v12;
      }
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_Future__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_Future__descriptor,
        3u,
        v4);
    if ( (*(_BYTE *)a2 & 2) == 0 )
      *(_DWORD *)a2 = (*(_DWORD *)a2
                     ^ ((unsigned __int16)v8
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180
                     ^ (v8
                      ^ *(_DWORD *)a2
                      ^ ((unsigned __int16)v8
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180)
                     & 0x40
                     | 1)
                    ^ ((unsigned __int16)v8
                     ^ (*(_WORD *)a2
                      ^ ((unsigned __int16)v8
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180
                      ^ ((unsigned __int16)v8
                       ^ *(_WORD *)a2
                       ^ ((unsigned __int16)v8
                        ^ (unsigned __int16)*(_DWORD *)a2)
                       & 0x180)
                      & 0x40
                      | 1))
                    & 0x800;
  }
  return a2;
}

```

## disassembly

```asm
0x1800064f4  mov     [rsp+arg_8], rbx
0x1800064f9  mov     [rsp+arg_10], rbp
0x1800064fe  mov     [rsp+arg_0], rcx
0x180006503  push    rsi
0x180006504  push    rdi
0x180006505  push    r15
0x180006507  sub     rsp, 20h
0x18000650b  mov     rsi, cs:Feature_Standalone_Future__descriptor
0x180006512  mov     rbx, rdx
0x180006515  mov     qword ptr [rdx], 0
0x18000651c  mov     eax, [rsi]
0x18000651e  mov     [rdx], eax
0x180006520  and     eax, 6
0x180006523  cmp     al, 6
0x180006525  jz      loc_180006655
0x18000652b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180006530  mov     ebp, eax
0x180006532  mov     dword ptr [rsp+38h+arg_0], 0
0x18000653a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180006541  test    rax, rax
0x180006544  jz      short loc_18000655E
0x180006546  lea     r8, [rsp+38h+arg_0]
0x18000654b  mov     edx, 3
0x180006550  mov     ecx, 2F29A04h
0x180006555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000655a  mov     edx, eax
0x18000655c  jmp     short loc_18000656C
0x18000655e  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180006565  test    rax, rax
0x180006568  jnz     short loc_180006546
0x18000656a  xor     edx, edx
0x18000656c  mov     r8d, edx
0x18000656f  mov     eax, edx
0x180006571  and     r8d, 0FFFFFF3Fh
0x180006578  and     edx, 80h
0x18000657e  mov     ecx, r8d
0x180006581  mov     r15d, 40h ; '@'
0x180006587  and     ecx, 3
0x18000658a  and     eax, r15d
0x18000658d  shl     ecx, 2
0x180006590  or      ecx, eax
0x180006592  shl     ecx, 2
0x180006595  or      ecx, edx
0x180006597  lea     edi, ds:0[rcx*8]
0x18000659e  test    r8d, r8d
0x1800065a1  jnz     short loc_1800065A8
0x1800065a3  mov     eax, r15d
0x1800065a6  jmp     short loc_1800065B2
0x1800065a8  xor     eax, eax
0x1800065aa  cmp     r8d, 2
0x1800065ae  cmovz   eax, r15d
0x1800065b2  or      edi, eax
0x1800065b4  mov     eax, [rbx]
0x1800065b6  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800065bb  mov     edx, eax
0x1800065bd  mov     [rbx], eax
0x1800065bf  jz      short loc_1800065EF
0x1800065c1  test    dl, 2
0x1800065c4  jnz     short loc_1800065EF
0x1800065c6  mov     eax, edi
0x1800065c8  xor     eax, edx
0x1800065ca  and     eax, 180h
0x1800065cf  xor     eax, edx
0x1800065d1  mov     ecx, eax
0x1800065d3  xor     ecx, edi
0x1800065d5  and     ecx, r15d
0x1800065d8  xor     ecx, eax
0x1800065da  or      ecx, 1
0x1800065dd  mov     eax, ecx
0x1800065df  xor     eax, edi
0x1800065e1  and     eax, 800h
0x1800065e6  xor     eax, ecx
0x1800065e8  or      eax, 2
0x1800065eb  mov     [rbx], eax
0x1800065ed  jmp     short loc_1800065F1
0x1800065ef  mov     eax, edx
0x1800065f1  mov     r8d, edx
0x1800065f4  and     r8d, 4
0x1800065f8  jnz     short loc_18000660D
0x1800065fa  mov     ecx, edi
0x1800065fc  xor     ecx, eax
0x1800065fe  and     ecx, 400h
0x180006604  xor     ecx, eax
0x180006606  or      ecx, 4
0x180006609  mov     [rbx], ecx
0x18000660b  jmp     short loc_18000660F
0x18000660d  mov     ecx, eax
0x18000660f  mov     eax, edx
0x180006611  lock cmpxchg [rsi], ecx
0x180006615  jnz     short loc_1800065B6
0x180006617  test    r8d, r8d
0x18000661a  jnz     short loc_18000662C
0x18000661c  mov     r8d, ebp
0x18000661f  mov     edx, 3
0x180006624  mov     rcx, rsi
0x180006627  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000662c  test    byte ptr [rbx], 2
0x18000662f  jnz     short loc_180006655
0x180006631  mov     eax, [rbx]
0x180006633  xor     eax, edi
0x180006635  and     eax, 180h
0x18000663a  xor     eax, [rbx]
0x18000663c  mov     ecx, eax
0x18000663e  xor     ecx, edi
0x180006640  and     ecx, r15d
0x180006643  xor     ecx, eax
0x180006645  or      ecx, 1
0x180006648  mov     eax, ecx
0x18000664a  xor     eax, edi
0x18000664c  and     eax, 800h
0x180006651  xor     eax, ecx
0x180006653  mov     [rbx], eax
0x180006655  mov     rbp, [rsp+38h+arg_10]
0x18000665a  mov     rax, rbx
0x18000665d  mov     rbx, [rsp+38h+arg_8]
0x180006662  add     rsp, 20h
0x180006666  pop     r15
0x180006668  pop     rdi
0x180006669  pop     rsi
0x18000666a  retn
```
