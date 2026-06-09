# wil::details::FeatureImpl<__WilFeatureTraits_Feature_60163883>::GetCachedFeatureEnabledState(void)

- ea: `0x180016cac`
- end: `0x180016e79`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_60163883@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018ee0`

## callees

- `0x180016be8`
- `0x180016cac`
- `0x180018da4`
- `0x180019154`
- `0x18001e010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_60163883>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, __int64, wil::details **); // rax
  int v6; // edx
  int v7; // eax
  int v8; // ebx
  char v9; // si
  char IsEnabled; // al
  BOOL v11; // esi
  signed __int32 v12; // eax
  int v13; // esi
  bool v14; // zf
  signed __int32 v15; // edx
  int v16; // r8d
  int v17; // r9d
  signed __int32 v18; // ecx
  wil::details *v20; // [rsp+60h] [rbp+8h] BYREF

  v20 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_60163883__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_60163883__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(60163883, 3, &v20);
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
  if ( (v8 & 0xC00) == 0xC00 )
  {
    v9 = 1;
LABEL_13:
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestUex12>::GetImpl'::`2'::impl);
    if ( v9 && !IsEnabled )
      v8 &= ~0x400u;
    goto LABEL_17;
  }
  v9 = 0;
  if ( (v8 & 0x40) != 0 )
    goto LABEL_13;
  IsEnabled = 0;
LABEL_17:
  v11 = (v8 & 0x40) != 0 && IsEnabled;
  v12 = *(_DWORD *)a2;
  v13 = v8 | v11;
  do
  {
    v14 = (_DWORD)v20 == 0;
    v15 = v12;
    *(_DWORD *)a2 = v12;
    if ( v14 || (v12 & 2) != 0 )
    {
      v16 = v12;
    }
    else
    {
      v16 = v12
          ^ (v12
           ^ v13)
          & 0x180
          ^ (v13
           ^ v12
           ^ (v12
            ^ v13)
           & 0x180)
          & 0x40
          ^ ((unsigned __int8)v13
           ^ (unsigned __int8)(v12 ^ (v12 ^ v13) & 0x80 ^ (v13 ^ v12 ^ (v12 ^ v13) & 0x80) & 0x40))
          & 1
          ^ ((unsigned __int16)v13
           ^ (unsigned __int16)(v12
                              ^ (v12
                               ^ v13)
                              & 0x180
                              ^ (v13
                               ^ v12
                               ^ (v12
                                ^ v13)
                               & 0x180)
                              & 0x40
                              ^ ((unsigned __int8)v13
                               ^ (unsigned __int8)(v12 ^ (v12 ^ v13) & 0x80 ^ (v13 ^ v12 ^ (v12 ^ v13) & 0x80) & 0x40))
                              & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v16;
    }
    v17 = v12 & 4;
    if ( (v12 & 4) != 0 )
    {
      v18 = v16;
    }
    else
    {
      v18 = v16 ^ ((unsigned __int16)v16 ^ (unsigned __int16)v13) & 0x400 | 4;
      *(_DWORD *)a2 = v18;
    }
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_60163883__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_60163883__descriptor, 3, v4);
  if ( (*(_BYTE *)a2 & 2) == 0 )
    *(_DWORD *)a2 ^= (v13
                    ^ *(_DWORD *)a2)
                   & 0x180
                   ^ (v13
                    ^ *(_DWORD *)a2
                    ^ (v13
                     ^ *(_DWORD *)a2)
                    & 0x180)
                   & 0x40
                   ^ ((unsigned __int8)v13
                    ^ *(_BYTE *)a2
                    ^ ((unsigned __int8)v13
                     ^ *(_BYTE *)a2)
                    & 0x80
                    ^ ((unsigned __int8)v13
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v13
                      ^ *(_BYTE *)a2)
                     & 0x80)
                    & 0x40)
                   & 1
                   ^ ((unsigned __int16)v13
                    ^ *(_WORD *)a2
                    ^ ((unsigned __int16)v13
                     ^ *(_WORD *)a2)
                    & 0x180
                    ^ ((unsigned __int16)v13
                     ^ *(_WORD *)a2
                     ^ ((unsigned __int16)v13
                      ^ *(_WORD *)a2)
                     & 0x180)
                    & 0x40
                    ^ ((unsigned __int8)v13
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v13
                      ^ *(_BYTE *)a2)
                     & 0x80
                     ^ ((unsigned __int8)v13
                      ^ *(_BYTE *)a2
                      ^ ((unsigned __int8)v13
                       ^ *(_BYTE *)a2)
                      & 0x80)
                     & 0x40)
                    & 1)
                   & 0x800;
  return a2;
}

```

## disassembly

```asm
0x180016cac  mov     [rsp+arg_0], rcx
0x180016cb1  push    rbx
0x180016cb2  push    rbp
0x180016cb3  push    rsi
0x180016cb4  push    rdi
0x180016cb5  push    r12
0x180016cb7  push    r14
0x180016cb9  sub     rsp, 28h
0x180016cbd  mov     r14, cs:Feature_60163883__descriptor
0x180016cc4  mov     rdi, rdx
0x180016cc7  mov     qword ptr [rdx], 0
0x180016cce  mov     eax, [r14]
0x180016cd1  mov     [rdx], eax
0x180016cd3  and     eax, 6
0x180016cd6  cmp     al, 6
0x180016cd8  jz      loc_180016E69
0x180016cde  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180016ce3  mov     ebp, eax
0x180016ce5  mov     dword ptr [rsp+58h+arg_0], 0
0x180016ced  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180016cf4  test    rax, rax
0x180016cf7  jz      short loc_180016D11
0x180016cf9  lea     r8, [rsp+58h+arg_0]
0x180016cfe  mov     edx, 3
0x180016d03  mov     ecx, 396072Bh
0x180016d08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d0d  mov     edx, eax
0x180016d0f  jmp     short loc_180016D1F
0x180016d11  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180016d18  test    rax, rax
0x180016d1b  jnz     short loc_180016CF9
0x180016d1d  xor     edx, edx
0x180016d1f  mov     r8d, edx
0x180016d22  mov     eax, edx
0x180016d24  and     r8d, 0FFFFFF3Fh
0x180016d2b  and     edx, 80h
0x180016d31  mov     ecx, r8d
0x180016d34  mov     r12d, 40h ; '@'
0x180016d3a  and     ecx, 3
0x180016d3d  and     eax, r12d
0x180016d40  shl     ecx, 2
0x180016d43  or      ecx, eax
0x180016d45  shl     ecx, 2
0x180016d48  or      ecx, edx
0x180016d4a  lea     ebx, ds:0[rcx*8]
0x180016d51  test    r8d, r8d
0x180016d54  jnz     short loc_180016D5B
0x180016d56  mov     eax, r12d
0x180016d59  jmp     short loc_180016D65
0x180016d5b  xor     eax, eax
0x180016d5d  cmp     r8d, 2
0x180016d61  cmovz   eax, r12d
0x180016d65  or      ebx, eax
0x180016d67  mov     ecx, 0C00h
0x180016d6c  mov     eax, ebx
0x180016d6e  and     eax, ecx
0x180016d70  cmp     eax, ecx
0x180016d72  jnz     short loc_180016D79
0x180016d74  mov     sil, 1
0x180016d77  jmp     short loc_180016D81
0x180016d79  xor     sil, sil
0x180016d7c  test    r12b, bl
0x180016d7f  jz      short loc_180016D9C
0x180016d81  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestUex12@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12> `wil::Feature<__WilFeatureTraits_Feature_TestUex12>::GetImpl(void)'::`2'::impl
0x180016d88  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::__private_IsEnabled(wil::ReportingKind)
0x180016d8d  test    sil, sil
0x180016d90  jz      short loc_180016D9E
0x180016d92  test    al, al
0x180016d94  jnz     short loc_180016D9E
0x180016d96  btr     ebx, 0Ah
0x180016d9a  jmp     short loc_180016D9E
0x180016d9c  xor     al, al
0x180016d9e  test    r12b, bl
0x180016da1  jz      short loc_180016DAE
0x180016da3  test    al, al
0x180016da5  jz      short loc_180016DAE
0x180016da7  mov     esi, 1
0x180016dac  jmp     short loc_180016DB0
0x180016dae  xor     esi, esi
0x180016db0  mov     eax, [rdi]
0x180016db2  or      esi, ebx
0x180016db4  mov     ebx, 180h
0x180016db9  cmp     dword ptr [rsp+58h+arg_0], 0
0x180016dbe  mov     edx, eax
0x180016dc0  mov     [rdi], eax
0x180016dc2  jz      short loc_180016DFC
0x180016dc4  test    dl, 2
0x180016dc7  jnz     short loc_180016DFC
0x180016dc9  mov     eax, esi
0x180016dcb  xor     eax, edx
0x180016dcd  and     eax, ebx
0x180016dcf  xor     eax, edx
0x180016dd1  mov     ecx, eax
0x180016dd3  xor     ecx, esi
0x180016dd5  and     ecx, r12d
0x180016dd8  xor     ecx, eax
0x180016dda  mov     eax, ecx
0x180016ddc  xor     eax, esi
0x180016dde  and     eax, 1
0x180016de1  xor     eax, ecx
0x180016de3  mov     r8d, eax
0x180016de6  xor     r8d, esi
0x180016de9  and     r8d, 800h
0x180016df0  xor     r8d, eax
0x180016df3  or      r8d, 2
0x180016df7  mov     [rdi], r8d
0x180016dfa  jmp     short loc_180016DFF
0x180016dfc  mov     r8d, edx
0x180016dff  mov     r9d, edx
0x180016e02  and     r9d, 4
0x180016e06  jnz     short loc_180016E1D
0x180016e08  mov     ecx, esi
0x180016e0a  xor     ecx, r8d
0x180016e0d  and     ecx, 400h
0x180016e13  xor     ecx, r8d
0x180016e16  or      ecx, 4
0x180016e19  mov     [rdi], ecx
0x180016e1b  jmp     short loc_180016E20
0x180016e1d  mov     ecx, r8d
0x180016e20  mov     eax, edx
0x180016e22  lock cmpxchg [r14], ecx
0x180016e27  jnz     short loc_180016DB9
0x180016e29  test    r9d, r9d
0x180016e2c  jnz     short loc_180016E3D
0x180016e2e  mov     r8d, ebp
0x180016e31  lea     edx, [r9+3]
0x180016e35  mov     rcx, r14
0x180016e38  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180016e3d  test    byte ptr [rdi], 2
0x180016e40  jnz     short loc_180016E69
0x180016e42  mov     eax, [rdi]
0x180016e44  xor     eax, esi
0x180016e46  and     eax, ebx
0x180016e48  xor     eax, [rdi]
0x180016e4a  mov     ecx, eax
0x180016e4c  xor     ecx, esi
0x180016e4e  and     ecx, r12d
0x180016e51  xor     ecx, eax
0x180016e53  mov     edx, ecx
0x180016e55  xor     edx, esi
0x180016e57  and     edx, 1
0x180016e5a  xor     edx, ecx
0x180016e5c  mov     eax, edx
0x180016e5e  xor     eax, esi
0x180016e60  and     eax, 800h
0x180016e65  xor     eax, edx
0x180016e67  mov     [rdi], eax
0x180016e69  mov     rax, rdi
0x180016e6c  add     rsp, 28h
0x180016e70  pop     r14
0x180016e72  pop     r12
0x180016e74  pop     rdi
0x180016e75  pop     rsi
0x180016e76  pop     rbp
0x180016e77  pop     rbx
0x180016e78  retn
```
