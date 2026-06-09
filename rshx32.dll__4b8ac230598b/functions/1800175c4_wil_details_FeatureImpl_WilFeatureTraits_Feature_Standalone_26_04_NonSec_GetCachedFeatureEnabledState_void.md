# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_04_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x1800175c4`
- end: `0x180017731`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_04_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018248`

## callees

- `0x180016be8`
- `0x1800175c4`
- `0x180018da4`
- `0x18001e010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_04_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_04_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_04_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(58599559, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_04_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_26_04_NonSec__descriptor, 3, v4);
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
0x1800175c4  mov     [rsp+arg_8], rbx
0x1800175c9  mov     [rsp+arg_10], rbp
0x1800175ce  mov     [rsp+arg_0], rcx
0x1800175d3  push    rsi
0x1800175d4  push    rdi
0x1800175d5  push    r15
0x1800175d7  sub     rsp, 20h
0x1800175db  mov     rsi, cs:Feature_Standalone_26_04_NonSec__descriptor
0x1800175e2  mov     rbx, rdx
0x1800175e5  mov     qword ptr [rdx], 0
0x1800175ec  mov     eax, [rsi]
0x1800175ee  mov     [rdx], eax
0x1800175f0  and     eax, 6
0x1800175f3  cmp     al, 6
0x1800175f5  jz      loc_18001771B
0x1800175fb  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180017600  mov     ebp, eax
0x180017602  mov     dword ptr [rsp+38h+arg_0], 0
0x18001760a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180017611  test    rax, rax
0x180017614  jz      short loc_18001762E
0x180017616  lea     r8, [rsp+38h+arg_0]
0x18001761b  mov     edx, 3
0x180017620  mov     ecx, 37E2887h
0x180017625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001762a  mov     edx, eax
0x18001762c  jmp     short loc_18001763C
0x18001762e  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180017635  test    rax, rax
0x180017638  jnz     short loc_180017616
0x18001763a  xor     edx, edx
0x18001763c  mov     r8d, edx
0x18001763f  mov     eax, edx
0x180017641  and     r8d, 0FFFFFF3Fh
0x180017648  and     edx, 80h
0x18001764e  mov     ecx, r8d
0x180017651  mov     r15d, 40h ; '@'
0x180017657  and     ecx, 3
0x18001765a  and     eax, r15d
0x18001765d  shl     ecx, 2
0x180017660  or      ecx, eax
0x180017662  shl     ecx, 2
0x180017665  or      ecx, edx
0x180017667  lea     edi, ds:0[rcx*8]
0x18001766e  test    r8d, r8d
0x180017671  jnz     short loc_180017678
0x180017673  mov     eax, r15d
0x180017676  jmp     short loc_180017682
0x180017678  xor     eax, eax
0x18001767a  cmp     r8d, 2
0x18001767e  cmovz   eax, r15d
0x180017682  or      edi, eax
0x180017684  mov     eax, [rbx]
0x180017686  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001768b  mov     edx, eax
0x18001768d  mov     [rbx], eax
0x18001768f  jz      short loc_1800176BB
0x180017691  test    dl, 2
0x180017694  jnz     short loc_1800176BB
0x180017696  xor     eax, edi
0x180017698  and     eax, 180h
0x18001769d  xor     eax, edx
0x18001769f  mov     ecx, eax
0x1800176a1  xor     ecx, edi
0x1800176a3  and     ecx, r15d
0x1800176a6  xor     ecx, eax
0x1800176a8  or      ecx, 1
0x1800176ab  mov     eax, ecx
0x1800176ad  xor     eax, edi
0x1800176af  and     eax, 800h
0x1800176b4  xor     eax, ecx
0x1800176b6  or      eax, 2
0x1800176b9  mov     [rbx], eax
0x1800176bb  mov     r8d, edx
0x1800176be  mov     ecx, eax
0x1800176c0  and     r8d, 4
0x1800176c4  jnz     short loc_1800176D5
0x1800176c6  xor     ecx, edi
0x1800176c8  and     ecx, 400h
0x1800176ce  xor     ecx, eax
0x1800176d0  or      ecx, 4
0x1800176d3  mov     [rbx], ecx
0x1800176d5  mov     eax, edx
0x1800176d7  lock cmpxchg [rsi], ecx
0x1800176db  jnz     short loc_180017686
0x1800176dd  test    r8d, r8d
0x1800176e0  jnz     short loc_1800176F2
0x1800176e2  mov     r8d, ebp
0x1800176e5  mov     edx, 3
0x1800176ea  mov     rcx, rsi
0x1800176ed  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800176f2  test    byte ptr [rbx], 2
0x1800176f5  jnz     short loc_18001771B
0x1800176f7  mov     eax, [rbx]
0x1800176f9  xor     eax, edi
0x1800176fb  and     eax, 180h
0x180017700  xor     eax, [rbx]
0x180017702  mov     ecx, eax
0x180017704  xor     ecx, edi
0x180017706  and     ecx, r15d
0x180017709  xor     ecx, eax
0x18001770b  or      ecx, 1
0x18001770e  mov     eax, ecx
0x180017710  xor     eax, edi
0x180017712  and     eax, 800h
0x180017717  xor     eax, ecx
0x180017719  mov     [rbx], eax
0x18001771b  mov     rbp, [rsp+38h+arg_10]
0x180017720  mov     rax, rbx
0x180017723  mov     rbx, [rsp+38h+arg_8]
0x180017728  add     rsp, 20h
0x18001772c  pop     r15
0x18001772e  pop     rdi
0x18001772f  pop     rsi
0x180017730  retn
```
