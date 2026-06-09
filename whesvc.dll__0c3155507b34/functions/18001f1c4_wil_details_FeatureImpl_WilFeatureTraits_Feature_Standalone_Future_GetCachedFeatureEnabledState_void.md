# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)

- ea: `0x18001f1c4`
- end: `0x18001f33b`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020160`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x18001f1c4`
- `0x180029010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_Future__descriptor, 3, v4);
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
0x18001f1c4  mov     [rsp+arg_8], rbx
0x18001f1c9  mov     [rsp+arg_10], rbp
0x18001f1ce  mov     [rsp+arg_0], rcx
0x18001f1d3  push    rsi
0x18001f1d4  push    rdi
0x18001f1d5  push    r15
0x18001f1d7  sub     rsp, 20h
0x18001f1db  mov     rsi, cs:Feature_Standalone_Future__descriptor
0x18001f1e2  mov     rbx, rdx
0x18001f1e5  mov     qword ptr [rdx], 0
0x18001f1ec  mov     eax, [rsi]
0x18001f1ee  mov     [rdx], eax
0x18001f1f0  and     eax, 6
0x18001f1f3  cmp     al, 6
0x18001f1f5  jz      loc_18001F325
0x18001f1fb  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001f200  mov     ebp, eax
0x18001f202  mov     dword ptr [rsp+38h+arg_0], 0
0x18001f20a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001f211  test    rax, rax
0x18001f214  jz      short loc_18001F22E
0x18001f216  lea     r8, [rsp+38h+arg_0]
0x18001f21b  mov     edx, 3
0x18001f220  mov     ecx, 2F29A04h
0x18001f225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f22a  mov     edx, eax
0x18001f22c  jmp     short loc_18001F23C
0x18001f22e  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001f235  test    rax, rax
0x18001f238  jnz     short loc_18001F216
0x18001f23a  xor     edx, edx
0x18001f23c  mov     r8d, edx
0x18001f23f  mov     eax, edx
0x18001f241  and     r8d, 0FFFFFF3Fh
0x18001f248  and     edx, 80h
0x18001f24e  mov     ecx, r8d
0x18001f251  mov     r15d, 40h ; '@'
0x18001f257  and     ecx, 3
0x18001f25a  and     eax, r15d
0x18001f25d  shl     ecx, 2
0x18001f260  or      ecx, eax
0x18001f262  shl     ecx, 2
0x18001f265  or      ecx, edx
0x18001f267  lea     edi, ds:0[rcx*8]
0x18001f26e  test    r8d, r8d
0x18001f271  jnz     short loc_18001F278
0x18001f273  mov     eax, r15d
0x18001f276  jmp     short loc_18001F282
0x18001f278  xor     eax, eax
0x18001f27a  cmp     r8d, 2
0x18001f27e  cmovz   eax, r15d
0x18001f282  or      edi, eax
0x18001f284  mov     eax, [rbx]
0x18001f286  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001f28b  mov     edx, eax
0x18001f28d  mov     [rbx], eax
0x18001f28f  jz      short loc_18001F2BF
0x18001f291  test    dl, 2
0x18001f294  jnz     short loc_18001F2BF
0x18001f296  mov     eax, edi
0x18001f298  xor     eax, edx
0x18001f29a  and     eax, 180h
0x18001f29f  xor     eax, edx
0x18001f2a1  mov     ecx, eax
0x18001f2a3  xor     ecx, edi
0x18001f2a5  and     ecx, r15d
0x18001f2a8  xor     ecx, eax
0x18001f2aa  or      ecx, 1
0x18001f2ad  mov     eax, ecx
0x18001f2af  xor     eax, edi
0x18001f2b1  and     eax, 800h
0x18001f2b6  xor     eax, ecx
0x18001f2b8  or      eax, 2
0x18001f2bb  mov     [rbx], eax
0x18001f2bd  jmp     short loc_18001F2C1
0x18001f2bf  mov     eax, edx
0x18001f2c1  mov     r8d, edx
0x18001f2c4  and     r8d, 4
0x18001f2c8  jnz     short loc_18001F2DD
0x18001f2ca  mov     ecx, edi
0x18001f2cc  xor     ecx, eax
0x18001f2ce  and     ecx, 400h
0x18001f2d4  xor     ecx, eax
0x18001f2d6  or      ecx, 4
0x18001f2d9  mov     [rbx], ecx
0x18001f2db  jmp     short loc_18001F2DF
0x18001f2dd  mov     ecx, eax
0x18001f2df  mov     eax, edx
0x18001f2e1  lock cmpxchg [rsi], ecx
0x18001f2e5  jnz     short loc_18001F286
0x18001f2e7  test    r8d, r8d
0x18001f2ea  jnz     short loc_18001F2FC
0x18001f2ec  mov     r8d, ebp
0x18001f2ef  mov     edx, 3
0x18001f2f4  mov     rcx, rsi
0x18001f2f7  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001f2fc  test    byte ptr [rbx], 2
0x18001f2ff  jnz     short loc_18001F325
0x18001f301  mov     eax, [rbx]
0x18001f303  xor     eax, edi
0x18001f305  and     eax, 180h
0x18001f30a  xor     eax, [rbx]
0x18001f30c  mov     ecx, eax
0x18001f30e  xor     ecx, edi
0x18001f310  and     ecx, r15d
0x18001f313  xor     ecx, eax
0x18001f315  or      ecx, 1
0x18001f318  mov     eax, ecx
0x18001f31a  xor     eax, edi
0x18001f31c  and     eax, 800h
0x18001f321  xor     eax, ecx
0x18001f323  mov     [rbx], eax
0x18001f325  mov     rbp, [rsp+38h+arg_10]
0x18001f32a  mov     rax, rbx
0x18001f32d  mov     rbx, [rsp+38h+arg_8]
0x18001f332  add     rsp, 20h
0x18001f336  pop     r15
0x18001f338  pop     rdi
0x18001f339  pop     rsi
0x18001f33a  retn
```
