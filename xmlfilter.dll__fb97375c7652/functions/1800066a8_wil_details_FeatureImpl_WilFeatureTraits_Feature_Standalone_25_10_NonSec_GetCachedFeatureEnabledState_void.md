# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x1800066a8`
- end: `0x180006815`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007c40`

## callees

- `0x180005dd0`
- `0x1800066a8`
- `0x18000c3f0`
- `0x180017010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
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
  v3 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(45036792, 3, &v14);
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
            ^ ((unsigned __int16)v8
             ^ (unsigned __int16)v9)
            & 0x180
            ^ (v8
             ^ v9
             ^ ((unsigned __int16)v8
              ^ (unsigned __int16)v9)
             & 0x180)
            & 0x40
            | 1)
           ^ ((unsigned __int16)v8
            ^ ((unsigned __int16)(v9 ^ (v8 ^ v9) & 0x180 ^ (v8 ^ v9 ^ (v8 ^ v9) & 0x180) & 0x40) | 1))
           & 0x800
           | 2;
        *(_DWORD *)a2 = v9;
      }
      v12 = v9;
      if ( (v11 & 4) == 0 )
      {
        v12 = v9 ^ ((unsigned __int16)v8 ^ (unsigned __int16)v9) & 0x400 | 4;
        *(_DWORD *)a2 = v12;
      }
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_25_10_NonSec__descriptor, 3, v4);
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
0x1800066a8  mov     [rsp+arg_8], rbx
0x1800066ad  mov     [rsp+arg_10], rbp
0x1800066b2  mov     [rsp+arg_0], rcx
0x1800066b7  push    rsi
0x1800066b8  push    rdi
0x1800066b9  push    r15
0x1800066bb  sub     rsp, 20h
0x1800066bf  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x1800066c6  mov     rbx, rdx
0x1800066c9  mov     qword ptr [rdx], 0
0x1800066d0  mov     eax, [rsi]
0x1800066d2  mov     [rdx], eax
0x1800066d4  and     eax, 6
0x1800066d7  cmp     al, 6
0x1800066d9  jz      loc_1800067FF
0x1800066df  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800066e4  mov     ebp, eax
0x1800066e6  mov     dword ptr [rsp+38h+arg_0], 0
0x1800066ee  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800066f5  test    rax, rax
0x1800066f8  jz      short loc_180006712
0x1800066fa  lea     r8, [rsp+38h+arg_0]
0x1800066ff  mov     edx, 3
0x180006704  mov     ecx, 2AF34F8h
0x180006709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000670e  mov     edx, eax
0x180006710  jmp     short loc_180006720
0x180006712  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180006719  test    rax, rax
0x18000671c  jnz     short loc_1800066FA
0x18000671e  xor     edx, edx
0x180006720  mov     r8d, edx
0x180006723  mov     eax, edx
0x180006725  and     r8d, 0FFFFFF3Fh
0x18000672c  and     edx, 80h
0x180006732  mov     ecx, r8d
0x180006735  mov     r15d, 40h ; '@'
0x18000673b  and     ecx, 3
0x18000673e  and     eax, r15d
0x180006741  shl     ecx, 2
0x180006744  or      ecx, eax
0x180006746  shl     ecx, 2
0x180006749  or      ecx, edx
0x18000674b  lea     edi, ds:0[rcx*8]
0x180006752  test    r8d, r8d
0x180006755  jnz     short loc_18000675C
0x180006757  mov     eax, r15d
0x18000675a  jmp     short loc_180006766
0x18000675c  xor     eax, eax
0x18000675e  cmp     r8d, 2
0x180006762  cmovz   eax, r15d
0x180006766  or      edi, eax
0x180006768  mov     eax, [rbx]
0x18000676a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000676f  mov     edx, eax
0x180006771  mov     [rbx], eax
0x180006773  jz      short loc_18000679F
0x180006775  test    dl, 2
0x180006778  jnz     short loc_18000679F
0x18000677a  xor     eax, edi
0x18000677c  and     eax, 180h
0x180006781  xor     eax, edx
0x180006783  mov     ecx, eax
0x180006785  xor     ecx, edi
0x180006787  and     ecx, r15d
0x18000678a  xor     ecx, eax
0x18000678c  or      ecx, 1
0x18000678f  mov     eax, ecx
0x180006791  xor     eax, edi
0x180006793  and     eax, 800h
0x180006798  xor     eax, ecx
0x18000679a  or      eax, 2
0x18000679d  mov     [rbx], eax
0x18000679f  mov     r8d, edx
0x1800067a2  mov     ecx, eax
0x1800067a4  and     r8d, 4
0x1800067a8  jnz     short loc_1800067B9
0x1800067aa  xor     ecx, edi
0x1800067ac  and     ecx, 400h
0x1800067b2  xor     ecx, eax
0x1800067b4  or      ecx, 4
0x1800067b7  mov     [rbx], ecx
0x1800067b9  mov     eax, edx
0x1800067bb  lock cmpxchg [rsi], ecx
0x1800067bf  jnz     short loc_18000676A
0x1800067c1  test    r8d, r8d
0x1800067c4  jnz     short loc_1800067D6
0x1800067c6  mov     r8d, ebp
0x1800067c9  mov     edx, 3
0x1800067ce  mov     rcx, rsi
0x1800067d1  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800067d6  test    byte ptr [rbx], 2
0x1800067d9  jnz     short loc_1800067FF
0x1800067db  mov     eax, [rbx]
0x1800067dd  xor     eax, edi
0x1800067df  and     eax, 180h
0x1800067e4  xor     eax, [rbx]
0x1800067e6  mov     ecx, eax
0x1800067e8  xor     ecx, edi
0x1800067ea  and     ecx, r15d
0x1800067ed  xor     ecx, eax
0x1800067ef  or      ecx, 1
0x1800067f2  mov     eax, ecx
0x1800067f4  xor     eax, edi
0x1800067f6  and     eax, 800h
0x1800067fb  xor     eax, ecx
0x1800067fd  mov     [rbx], eax
0x1800067ff  mov     rbp, [rsp+38h+arg_10]
0x180006804  mov     rax, rbx
0x180006807  mov     rbx, [rsp+38h+arg_8]
0x18000680c  add     rsp, 20h
0x180006810  pop     r15
0x180006812  pop     rdi
0x180006813  pop     rsi
0x180006814  retn
```
