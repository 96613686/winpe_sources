# wil::details::FeatureImpl<__WilFeatureTraits_Feature_HighDrainSleepStudy>::GetCachedFeatureEnabledState(void)

- ea: `0x18001e560`
- end: `0x18001e72d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_HighDrainSleepStudy@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024d28`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x1800174bc`
- `0x18001e560`
- `0x180029010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_HighDrainSleepStudy>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_HighDrainSleepStudy__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_HighDrainSleepStudy__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(59719389, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl'::`2'::impl);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_HighDrainSleepStudy__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_HighDrainSleepStudy__descriptor, 3, v4);
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
0x18001e560  mov     [rsp+arg_0], rcx
0x18001e565  push    rbx
0x18001e566  push    rbp
0x18001e567  push    rsi
0x18001e568  push    rdi
0x18001e569  push    r12
0x18001e56b  push    r14
0x18001e56d  sub     rsp, 28h
0x18001e571  mov     r14, cs:Feature_HighDrainSleepStudy__descriptor
0x18001e578  mov     rdi, rdx
0x18001e57b  mov     qword ptr [rdx], 0
0x18001e582  mov     eax, [r14]
0x18001e585  mov     [rdx], eax
0x18001e587  and     eax, 6
0x18001e58a  cmp     al, 6
0x18001e58c  jz      loc_18001E71D
0x18001e592  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001e597  mov     ebp, eax
0x18001e599  mov     dword ptr [rsp+58h+arg_0], 0
0x18001e5a1  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001e5a8  test    rax, rax
0x18001e5ab  jz      short loc_18001E5C5
0x18001e5ad  lea     r8, [rsp+58h+arg_0]
0x18001e5b2  mov     edx, 3
0x18001e5b7  mov     ecx, 38F3EDDh
0x18001e5bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5c1  mov     edx, eax
0x18001e5c3  jmp     short loc_18001E5D3
0x18001e5c5  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001e5cc  test    rax, rax
0x18001e5cf  jnz     short loc_18001E5AD
0x18001e5d1  xor     edx, edx
0x18001e5d3  mov     r8d, edx
0x18001e5d6  mov     eax, edx
0x18001e5d8  and     r8d, 0FFFFFF3Fh
0x18001e5df  and     edx, 80h
0x18001e5e5  mov     ecx, r8d
0x18001e5e8  mov     r12d, 40h ; '@'
0x18001e5ee  and     ecx, 3
0x18001e5f1  and     eax, r12d
0x18001e5f4  shl     ecx, 2
0x18001e5f7  or      ecx, eax
0x18001e5f9  shl     ecx, 2
0x18001e5fc  or      ecx, edx
0x18001e5fe  lea     ebx, ds:0[rcx*8]
0x18001e605  test    r8d, r8d
0x18001e608  jnz     short loc_18001E60F
0x18001e60a  mov     eax, r12d
0x18001e60d  jmp     short loc_18001E619
0x18001e60f  xor     eax, eax
0x18001e611  cmp     r8d, 2
0x18001e615  cmovz   eax, r12d
0x18001e619  or      ebx, eax
0x18001e61b  mov     ecx, 0C00h
0x18001e620  mov     eax, ebx
0x18001e622  and     eax, ecx
0x18001e624  cmp     eax, ecx
0x18001e626  jnz     short loc_18001E62D
0x18001e628  mov     sil, 1
0x18001e62b  jmp     short loc_18001E635
0x18001e62d  xor     sil, sil
0x18001e630  test    r12b, bl
0x18001e633  jz      short loc_18001E650
0x18001e635  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ten2Loc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc> `wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl(void)'::`2'::impl
0x18001e63c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(wil::ReportingKind)
0x18001e641  test    sil, sil
0x18001e644  jz      short loc_18001E652
0x18001e646  test    al, al
0x18001e648  jnz     short loc_18001E652
0x18001e64a  btr     ebx, 0Ah
0x18001e64e  jmp     short loc_18001E652
0x18001e650  xor     al, al
0x18001e652  test    r12b, bl
0x18001e655  jz      short loc_18001E662
0x18001e657  test    al, al
0x18001e659  jz      short loc_18001E662
0x18001e65b  mov     esi, 1
0x18001e660  jmp     short loc_18001E664
0x18001e662  xor     esi, esi
0x18001e664  mov     eax, [rdi]
0x18001e666  or      esi, ebx
0x18001e668  mov     ebx, 180h
0x18001e66d  cmp     dword ptr [rsp+58h+arg_0], 0
0x18001e672  mov     edx, eax
0x18001e674  mov     [rdi], eax
0x18001e676  jz      short loc_18001E6B0
0x18001e678  test    dl, 2
0x18001e67b  jnz     short loc_18001E6B0
0x18001e67d  mov     eax, esi
0x18001e67f  xor     eax, edx
0x18001e681  and     eax, ebx
0x18001e683  xor     eax, edx
0x18001e685  mov     ecx, eax
0x18001e687  xor     ecx, esi
0x18001e689  and     ecx, r12d
0x18001e68c  xor     ecx, eax
0x18001e68e  mov     eax, ecx
0x18001e690  xor     eax, esi
0x18001e692  and     eax, 1
0x18001e695  xor     eax, ecx
0x18001e697  mov     r8d, eax
0x18001e69a  xor     r8d, esi
0x18001e69d  and     r8d, 800h
0x18001e6a4  xor     r8d, eax
0x18001e6a7  or      r8d, 2
0x18001e6ab  mov     [rdi], r8d
0x18001e6ae  jmp     short loc_18001E6B3
0x18001e6b0  mov     r8d, edx
0x18001e6b3  mov     r9d, edx
0x18001e6b6  and     r9d, 4
0x18001e6ba  jnz     short loc_18001E6D1
0x18001e6bc  mov     ecx, esi
0x18001e6be  xor     ecx, r8d
0x18001e6c1  and     ecx, 400h
0x18001e6c7  xor     ecx, r8d
0x18001e6ca  or      ecx, 4
0x18001e6cd  mov     [rdi], ecx
0x18001e6cf  jmp     short loc_18001E6D4
0x18001e6d1  mov     ecx, r8d
0x18001e6d4  mov     eax, edx
0x18001e6d6  lock cmpxchg [r14], ecx
0x18001e6db  jnz     short loc_18001E66D
0x18001e6dd  test    r9d, r9d
0x18001e6e0  jnz     short loc_18001E6F1
0x18001e6e2  mov     r8d, ebp
0x18001e6e5  lea     edx, [r9+3]
0x18001e6e9  mov     rcx, r14
0x18001e6ec  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001e6f1  test    byte ptr [rdi], 2
0x18001e6f4  jnz     short loc_18001E71D
0x18001e6f6  mov     eax, [rdi]
0x18001e6f8  xor     eax, esi
0x18001e6fa  and     eax, ebx
0x18001e6fc  xor     eax, [rdi]
0x18001e6fe  mov     ecx, eax
0x18001e700  xor     ecx, esi
0x18001e702  and     ecx, r12d
0x18001e705  xor     ecx, eax
0x18001e707  mov     edx, ecx
0x18001e709  xor     edx, esi
0x18001e70b  and     edx, 1
0x18001e70e  xor     edx, ecx
0x18001e710  mov     eax, edx
0x18001e712  xor     eax, esi
0x18001e714  and     eax, 800h
0x18001e719  xor     eax, edx
0x18001e71b  mov     [rdi], eax
0x18001e71d  mov     rax, rdi
0x18001e720  add     rsp, 28h
0x18001e724  pop     r14
0x18001e726  pop     r12
0x18001e728  pop     rdi
0x18001e729  pop     rsi
0x18001e72a  pop     rbp
0x18001e72b  pop     rbx
0x18001e72c  retn
```
