# wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangSnapshotTrace>::GetCachedFeatureEnabledState(void)

- ea: `0x18001e38c`
- end: `0x18001e559`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_HangSnapshotTrace@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024c88`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x1800175f4`
- `0x18001e38c`
- `0x180029010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangSnapshotTrace>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_HangSnapshotTrace__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_HangSnapshotTrace__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(58301681, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl'::`2'::impl);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_HangSnapshotTrace__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_HangSnapshotTrace__descriptor, 3, v4);
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
0x18001e38c  mov     [rsp+arg_0], rcx
0x18001e391  push    rbx
0x18001e392  push    rbp
0x18001e393  push    rsi
0x18001e394  push    rdi
0x18001e395  push    r12
0x18001e397  push    r14
0x18001e399  sub     rsp, 28h
0x18001e39d  mov     r14, cs:Feature_HangSnapshotTrace__descriptor
0x18001e3a4  mov     rdi, rdx
0x18001e3a7  mov     qword ptr [rdx], 0
0x18001e3ae  mov     eax, [r14]
0x18001e3b1  mov     [rdx], eax
0x18001e3b3  and     eax, 6
0x18001e3b6  cmp     al, 6
0x18001e3b8  jz      loc_18001E549
0x18001e3be  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001e3c3  mov     ebp, eax
0x18001e3c5  mov     dword ptr [rsp+58h+arg_0], 0
0x18001e3cd  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001e3d4  test    rax, rax
0x18001e3d7  jz      short loc_18001E3F1
0x18001e3d9  lea     r8, [rsp+58h+arg_0]
0x18001e3de  mov     edx, 3
0x18001e3e3  mov     ecx, 3799CF1h
0x18001e3e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3ed  mov     edx, eax
0x18001e3ef  jmp     short loc_18001E3FF
0x18001e3f1  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001e3f8  test    rax, rax
0x18001e3fb  jnz     short loc_18001E3D9
0x18001e3fd  xor     edx, edx
0x18001e3ff  mov     r8d, edx
0x18001e402  mov     eax, edx
0x18001e404  and     r8d, 0FFFFFF3Fh
0x18001e40b  and     edx, 80h
0x18001e411  mov     ecx, r8d
0x18001e414  mov     r12d, 40h ; '@'
0x18001e41a  and     ecx, 3
0x18001e41d  and     eax, r12d
0x18001e420  shl     ecx, 2
0x18001e423  or      ecx, eax
0x18001e425  shl     ecx, 2
0x18001e428  or      ecx, edx
0x18001e42a  lea     ebx, ds:0[rcx*8]
0x18001e431  test    r8d, r8d
0x18001e434  jnz     short loc_18001E43B
0x18001e436  mov     eax, r12d
0x18001e439  jmp     short loc_18001E445
0x18001e43b  xor     eax, eax
0x18001e43d  cmp     r8d, 2
0x18001e441  cmovz   eax, r12d
0x18001e445  or      ebx, eax
0x18001e447  mov     ecx, 0C00h
0x18001e44c  mov     eax, ebx
0x18001e44e  and     eax, ecx
0x18001e450  cmp     eax, ecx
0x18001e452  jnz     short loc_18001E459
0x18001e454  mov     sil, 1
0x18001e457  jmp     short loc_18001E461
0x18001e459  xor     sil, sil
0x18001e45c  test    r12b, bl
0x18001e45f  jz      short loc_18001E47C
0x18001e461  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestLoc1Perf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf> `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl(void)'::`2'::impl
0x18001e468  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x18001e46d  test    sil, sil
0x18001e470  jz      short loc_18001E47E
0x18001e472  test    al, al
0x18001e474  jnz     short loc_18001E47E
0x18001e476  btr     ebx, 0Ah
0x18001e47a  jmp     short loc_18001E47E
0x18001e47c  xor     al, al
0x18001e47e  test    r12b, bl
0x18001e481  jz      short loc_18001E48E
0x18001e483  test    al, al
0x18001e485  jz      short loc_18001E48E
0x18001e487  mov     esi, 1
0x18001e48c  jmp     short loc_18001E490
0x18001e48e  xor     esi, esi
0x18001e490  mov     eax, [rdi]
0x18001e492  or      esi, ebx
0x18001e494  mov     ebx, 180h
0x18001e499  cmp     dword ptr [rsp+58h+arg_0], 0
0x18001e49e  mov     edx, eax
0x18001e4a0  mov     [rdi], eax
0x18001e4a2  jz      short loc_18001E4DC
0x18001e4a4  test    dl, 2
0x18001e4a7  jnz     short loc_18001E4DC
0x18001e4a9  mov     eax, esi
0x18001e4ab  xor     eax, edx
0x18001e4ad  and     eax, ebx
0x18001e4af  xor     eax, edx
0x18001e4b1  mov     ecx, eax
0x18001e4b3  xor     ecx, esi
0x18001e4b5  and     ecx, r12d
0x18001e4b8  xor     ecx, eax
0x18001e4ba  mov     eax, ecx
0x18001e4bc  xor     eax, esi
0x18001e4be  and     eax, 1
0x18001e4c1  xor     eax, ecx
0x18001e4c3  mov     r8d, eax
0x18001e4c6  xor     r8d, esi
0x18001e4c9  and     r8d, 800h
0x18001e4d0  xor     r8d, eax
0x18001e4d3  or      r8d, 2
0x18001e4d7  mov     [rdi], r8d
0x18001e4da  jmp     short loc_18001E4DF
0x18001e4dc  mov     r8d, edx
0x18001e4df  mov     r9d, edx
0x18001e4e2  and     r9d, 4
0x18001e4e6  jnz     short loc_18001E4FD
0x18001e4e8  mov     ecx, esi
0x18001e4ea  xor     ecx, r8d
0x18001e4ed  and     ecx, 400h
0x18001e4f3  xor     ecx, r8d
0x18001e4f6  or      ecx, 4
0x18001e4f9  mov     [rdi], ecx
0x18001e4fb  jmp     short loc_18001E500
0x18001e4fd  mov     ecx, r8d
0x18001e500  mov     eax, edx
0x18001e502  lock cmpxchg [r14], ecx
0x18001e507  jnz     short loc_18001E499
0x18001e509  test    r9d, r9d
0x18001e50c  jnz     short loc_18001E51D
0x18001e50e  mov     r8d, ebp
0x18001e511  lea     edx, [r9+3]
0x18001e515  mov     rcx, r14
0x18001e518  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001e51d  test    byte ptr [rdi], 2
0x18001e520  jnz     short loc_18001E549
0x18001e522  mov     eax, [rdi]
0x18001e524  xor     eax, esi
0x18001e526  and     eax, ebx
0x18001e528  xor     eax, [rdi]
0x18001e52a  mov     ecx, eax
0x18001e52c  xor     ecx, esi
0x18001e52e  and     ecx, r12d
0x18001e531  xor     ecx, eax
0x18001e533  mov     edx, ecx
0x18001e535  xor     edx, esi
0x18001e537  and     edx, 1
0x18001e53a  xor     edx, ecx
0x18001e53c  mov     eax, edx
0x18001e53e  xor     eax, esi
0x18001e540  and     eax, 800h
0x18001e545  xor     eax, edx
0x18001e547  mov     [rdi], eax
0x18001e549  mov     rax, rdi
0x18001e54c  add     rsp, 28h
0x18001e550  pop     r14
0x18001e552  pop     r12
0x18001e554  pop     rdi
0x18001e555  pop     rsi
0x18001e556  pop     rbp
0x18001e557  pop     rbx
0x18001e558  retn
```
