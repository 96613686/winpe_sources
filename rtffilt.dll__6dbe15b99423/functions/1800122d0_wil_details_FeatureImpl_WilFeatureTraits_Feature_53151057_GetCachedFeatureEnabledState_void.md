# wil::details::FeatureImpl<__WilFeatureTraits_Feature_53151057>::GetCachedFeatureEnabledState(void)

- ea: `0x1800122d0`
- end: `0x18001249c`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_53151057@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `460`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800153e4`

## callees

- `0x180005dd8`
- `0x18000b3d8`
- `0x1800122d0`
- `0x180015190`
- `0x18001b010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_53151057>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 (__fastcall *v5)(__int64, _QWORD, wil::details **); // rax
  int v6; // edx
  int v7; // eax
  int v8; // ebx
  char v9; // si
  char IsEnabled; // al
  BOOL v11; // esi
  int v12; // esi
  signed __int32 v13; // eax
  bool v14; // zf
  signed __int32 v15; // edx
  int v16; // r8d
  int v17; // r9d
  signed __int32 v18; // ecx
  wil::details *v20; // [rsp+60h] [rbp+8h] BYREF

  v20 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_53151057__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_53151057__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  v6 = 0;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(53151057, 0, &v20);
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
LABEL_12:
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl'::`2'::impl);
    if ( v9 && !IsEnabled )
      v8 &= ~0x400u;
    goto LABEL_16;
  }
  v9 = 0;
  if ( (v8 & 0x40) != 0 )
    goto LABEL_12;
  IsEnabled = 0;
LABEL_16:
  v11 = (v8 & 0x40) != 0 && IsEnabled;
  v12 = v8 | v11;
  if ( !v4 )
    LODWORD(v20) = 0;
  v13 = *(_DWORD *)a2;
  do
  {
    v14 = (_DWORD)v20 == 0;
    v15 = v13;
    *(_DWORD *)a2 = v13;
    if ( v14 || (v13 & 2) != 0 )
    {
      v16 = v13;
    }
    else
    {
      v16 = v13
          ^ (v13
           ^ v12)
          & 0x180
          ^ (v12
           ^ v13
           ^ (v13
            ^ v12)
           & 0x180)
          & 0x40
          ^ ((unsigned __int8)v12
           ^ (unsigned __int8)(v13 ^ (v13 ^ v12) & 0x80 ^ (v12 ^ v13 ^ (v13 ^ v12) & 0x80) & 0x40))
          & 1
          ^ ((unsigned __int16)v12
           ^ (unsigned __int16)(v13
                              ^ (v13
                               ^ v12)
                              & 0x180
                              ^ (v12
                               ^ v13
                               ^ (v13
                                ^ v12)
                               & 0x180)
                              & 0x40
                              ^ ((unsigned __int8)v12
                               ^ (unsigned __int8)(v13 ^ (v13 ^ v12) & 0x80 ^ (v12 ^ v13 ^ (v13 ^ v12) & 0x80) & 0x40))
                              & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v16;
    }
    v17 = v13 & 4;
    if ( (v13 & 4) != 0 )
    {
      v18 = v16;
    }
    else
    {
      v18 = v16 ^ ((unsigned __int16)v16 ^ (unsigned __int16)v12) & 0x400 | 4;
      *(_DWORD *)a2 = v18;
    }
    v13 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_53151057__descriptor, v18, v13);
  }
  while ( v15 != v13 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      (volatile signed __int32 *)Feature_53151057__descriptor,
      0,
      v4);
  if ( (*(_BYTE *)a2 & 2) == 0 )
    *(_DWORD *)a2 ^= (v12
                    ^ *(_DWORD *)a2)
                   & 0x180
                   ^ (v12
                    ^ *(_DWORD *)a2
                    ^ (v12
                     ^ *(_DWORD *)a2)
                    & 0x180)
                   & 0x40
                   ^ ((unsigned __int8)v12
                    ^ *(_BYTE *)a2
                    ^ ((unsigned __int8)v12
                     ^ *(_BYTE *)a2)
                    & 0x80
                    ^ ((unsigned __int8)v12
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v12
                      ^ *(_BYTE *)a2)
                     & 0x80)
                    & 0x40)
                   & 1
                   ^ ((unsigned __int16)v12
                    ^ *(_WORD *)a2
                    ^ ((unsigned __int16)v12
                     ^ *(_WORD *)a2)
                    & 0x180
                    ^ ((unsigned __int16)v12
                     ^ *(_WORD *)a2
                     ^ ((unsigned __int16)v12
                      ^ *(_WORD *)a2)
                     & 0x180)
                    & 0x40
                    ^ ((unsigned __int8)v12
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v12
                      ^ *(_BYTE *)a2)
                     & 0x80
                     ^ ((unsigned __int8)v12
                      ^ *(_BYTE *)a2
                      ^ ((unsigned __int8)v12
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
0x1800122d0  mov     [rsp+arg_0], rcx
0x1800122d5  push    rbx
0x1800122d6  push    rbp
0x1800122d7  push    rsi
0x1800122d8  push    rdi
0x1800122d9  push    r12
0x1800122db  push    r14
0x1800122dd  sub     rsp, 28h
0x1800122e1  mov     r14, cs:Feature_53151057__descriptor
0x1800122e8  mov     rdi, rdx
0x1800122eb  mov     qword ptr [rdx], 0
0x1800122f2  mov     eax, [r14]
0x1800122f5  mov     [rdx], eax
0x1800122f7  and     eax, 6
0x1800122fa  cmp     al, 6
0x1800122fc  jz      loc_18001248C
0x180012302  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012307  mov     ebp, eax
0x180012309  mov     dword ptr [rsp+58h+arg_0], 0
0x180012311  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180012318  xor     edx, edx
0x18001231a  test    rax, rax
0x18001231d  jnz     short loc_18001232B
0x18001231f  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180012326  test    rax, rax
0x180012329  jz      short loc_18001233C
0x18001232b  lea     r8, [rsp+58h+arg_0]
0x180012330  mov     ecx, 32B0551h
0x180012335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001233a  mov     edx, eax
0x18001233c  mov     r8d, edx
0x18001233f  mov     eax, edx
0x180012341  and     r8d, 0FFFFFF3Fh
0x180012348  and     edx, 80h
0x18001234e  mov     ecx, r8d
0x180012351  mov     r12d, 40h ; '@'
0x180012357  and     ecx, 3
0x18001235a  and     eax, r12d
0x18001235d  shl     ecx, 2
0x180012360  or      ecx, eax
0x180012362  shl     ecx, 2
0x180012365  or      ecx, edx
0x180012367  lea     ebx, ds:0[rcx*8]
0x18001236e  test    r8d, r8d
0x180012371  jnz     short loc_180012378
0x180012373  mov     eax, r12d
0x180012376  jmp     short loc_180012382
0x180012378  xor     eax, eax
0x18001237a  cmp     r8d, 2
0x18001237e  cmovz   eax, r12d
0x180012382  or      ebx, eax
0x180012384  mov     ecx, 0C00h
0x180012389  mov     eax, ebx
0x18001238b  and     eax, ecx
0x18001238d  cmp     eax, ecx
0x18001238f  jnz     short loc_180012396
0x180012391  mov     sil, 1
0x180012394  jmp     short loc_18001239E
0x180012396  xor     sil, sil
0x180012399  test    r12b, bl
0x18001239c  jz      short loc_1800123B9
0x18001239e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_47942714@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714> `wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl(void)'::`2'::impl
0x1800123a5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(wil::ReportingKind)
0x1800123aa  test    sil, sil
0x1800123ad  jz      short loc_1800123BB
0x1800123af  test    al, al
0x1800123b1  jnz     short loc_1800123BB
0x1800123b3  btr     ebx, 0Ah
0x1800123b7  jmp     short loc_1800123BB
0x1800123b9  xor     al, al
0x1800123bb  test    r12b, bl
0x1800123be  jz      short loc_1800123CB
0x1800123c0  test    al, al
0x1800123c2  jz      short loc_1800123CB
0x1800123c4  mov     esi, 1
0x1800123c9  jmp     short loc_1800123CD
0x1800123cb  xor     esi, esi
0x1800123cd  or      esi, ebx
0x1800123cf  test    ebp, ebp
0x1800123d1  jnz     short loc_1800123D7
0x1800123d3  mov     dword ptr [rsp+58h+arg_0], ebp
0x1800123d7  mov     eax, [rdi]
0x1800123d9  mov     ebx, 180h
0x1800123de  cmp     dword ptr [rsp+58h+arg_0], 0
0x1800123e3  mov     edx, eax
0x1800123e5  mov     [rdi], eax
0x1800123e7  jz      short loc_180012421
0x1800123e9  test    dl, 2
0x1800123ec  jnz     short loc_180012421
0x1800123ee  mov     eax, esi
0x1800123f0  xor     eax, edx
0x1800123f2  and     eax, ebx
0x1800123f4  xor     eax, edx
0x1800123f6  mov     ecx, eax
0x1800123f8  xor     ecx, esi
0x1800123fa  and     ecx, r12d
0x1800123fd  xor     ecx, eax
0x1800123ff  mov     eax, ecx
0x180012401  xor     eax, esi
0x180012403  and     eax, 1
0x180012406  xor     eax, ecx
0x180012408  mov     r8d, eax
0x18001240b  xor     r8d, esi
0x18001240e  and     r8d, 800h
0x180012415  xor     r8d, eax
0x180012418  or      r8d, 2
0x18001241c  mov     [rdi], r8d
0x18001241f  jmp     short loc_180012424
0x180012421  mov     r8d, edx
0x180012424  mov     r9d, edx
0x180012427  and     r9d, 4
0x18001242b  jnz     short loc_180012442
0x18001242d  mov     ecx, esi
0x18001242f  xor     ecx, r8d
0x180012432  and     ecx, 400h
0x180012438  xor     ecx, r8d
0x18001243b  or      ecx, 4
0x18001243e  mov     [rdi], ecx
0x180012440  jmp     short loc_180012445
0x180012442  mov     ecx, r8d
0x180012445  mov     eax, edx
0x180012447  lock cmpxchg [r14], ecx
0x18001244c  jnz     short loc_1800123DE
0x18001244e  test    r9d, r9d
0x180012451  jnz     short loc_180012460
0x180012453  mov     r8d, ebp
0x180012456  xor     edx, edx
0x180012458  mov     rcx, r14
0x18001245b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180012460  test    byte ptr [rdi], 2
0x180012463  jnz     short loc_18001248C
0x180012465  mov     eax, [rdi]
0x180012467  xor     eax, esi
0x180012469  and     eax, ebx
0x18001246b  xor     eax, [rdi]
0x18001246d  mov     ecx, eax
0x18001246f  xor     ecx, esi
0x180012471  and     ecx, r12d
0x180012474  xor     ecx, eax
0x180012476  mov     edx, ecx
0x180012478  xor     edx, esi
0x18001247a  and     edx, 1
0x18001247d  xor     edx, ecx
0x18001247f  mov     eax, edx
0x180012481  xor     eax, esi
0x180012483  and     eax, 800h
0x180012488  xor     eax, edx
0x18001248a  mov     [rdi], eax
0x18001248c  mov     rax, rdi
0x18001248f  add     rsp, 28h
0x180012493  pop     r14
0x180012495  pop     r12
0x180012497  pop     rdi
0x180012498  pop     rsi
0x180012499  pop     rbp
0x18001249a  pop     rbx
0x18001249b  retn
```
