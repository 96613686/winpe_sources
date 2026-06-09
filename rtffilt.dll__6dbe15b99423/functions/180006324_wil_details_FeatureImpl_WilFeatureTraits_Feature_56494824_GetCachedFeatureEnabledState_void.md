# wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::GetCachedFeatureEnabledState(void)

- ea: `0x180006324`
- end: `0x1800064ec`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `456`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c614`

## callees

- `0x180005dd8`
- `0x180006324`
- `0x18000b3d8`
- `0x18000c6b4`
- `0x18001b010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
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
  v3 = *(_DWORD *)Feature_56494824__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_56494824__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(56494824, 3, &v20);
  }
  else
  {
    v6 = 0;
  }
  v7 = 0;
  if ( (v6 & 0xFFFFFF3F) == 2 )
    v7 = 64;
  v8 = v7 | (8 * (v6 & 0x80 | (4 * (v6 & 0x40 | (4 * (v6 & 3))))));
  if ( (v8 & 0xC00) == 0xC00 )
  {
    v9 = 1;
LABEL_11:
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl'::`2'::impl);
    if ( v9 && !IsEnabled )
      v8 &= ~0x400u;
    goto LABEL_15;
  }
  v9 = 0;
  if ( (v8 & 0x40) != 0 )
    goto LABEL_11;
  IsEnabled = 0;
LABEL_15:
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_56494824__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      (volatile signed __int32 *)Feature_56494824__descriptor,
      3u,
      v4);
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
0x180006324  mov     [rsp+arg_0], rcx
0x180006329  push    rbx
0x18000632a  push    rbp
0x18000632b  push    rsi
0x18000632c  push    rdi
0x18000632d  push    r12
0x18000632f  push    r14
0x180006331  sub     rsp, 28h
0x180006335  mov     r14, cs:Feature_56494824__descriptor
0x18000633c  mov     rdi, rdx
0x18000633f  mov     qword ptr [rdx], 0
0x180006346  mov     eax, [r14]
0x180006349  mov     [rdx], eax
0x18000634b  and     eax, 6
0x18000634e  cmp     al, 6
0x180006350  jz      loc_1800064DC
0x180006356  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000635b  mov     ebp, eax
0x18000635d  mov     dword ptr [rsp+58h+arg_0], 0
0x180006365  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000636c  test    rax, rax
0x18000636f  jz      short loc_180006389
0x180006371  lea     r8, [rsp+58h+arg_0]
0x180006376  mov     edx, 3
0x18000637b  mov     ecx, 35E0AE8h
0x180006380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006385  mov     edx, eax
0x180006387  jmp     short loc_180006397
0x180006389  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180006390  test    rax, rax
0x180006393  jnz     short loc_180006371
0x180006395  xor     edx, edx
0x180006397  mov     r8d, edx
0x18000639a  mov     eax, edx
0x18000639c  and     r8d, 0FFFFFF3Fh
0x1800063a3  and     edx, 80h
0x1800063a9  mov     ecx, r8d
0x1800063ac  mov     r12d, 40h ; '@'
0x1800063b2  and     ecx, 3
0x1800063b5  and     eax, r12d
0x1800063b8  shl     ecx, 2
0x1800063bb  or      ecx, eax
0x1800063bd  xor     eax, eax
0x1800063bf  shl     ecx, 2
0x1800063c2  or      ecx, edx
0x1800063c4  lea     ebx, ds:0[rcx*8]
0x1800063cb  test    r8d, r8d
0x1800063ce  jz      short loc_1800063D8
0x1800063d0  cmp     r8d, 2
0x1800063d4  cmovz   eax, r12d
0x1800063d8  or      ebx, eax
0x1800063da  mov     ecx, 0C00h
0x1800063df  mov     eax, ebx
0x1800063e1  and     eax, ecx
0x1800063e3  cmp     eax, ecx
0x1800063e5  jnz     short loc_1800063EC
0x1800063e7  mov     sil, 1
0x1800063ea  jmp     short loc_1800063F4
0x1800063ec  xor     sil, sil
0x1800063ef  test    r12b, bl
0x1800063f2  jz      short loc_18000640F
0x1800063f4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x1800063fb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x180006400  test    sil, sil
0x180006403  jz      short loc_180006411
0x180006405  test    al, al
0x180006407  jnz     short loc_180006411
0x180006409  btr     ebx, 0Ah
0x18000640d  jmp     short loc_180006411
0x18000640f  xor     al, al
0x180006411  test    r12b, bl
0x180006414  jz      short loc_180006421
0x180006416  test    al, al
0x180006418  jz      short loc_180006421
0x18000641a  mov     esi, 1
0x18000641f  jmp     short loc_180006423
0x180006421  xor     esi, esi
0x180006423  mov     eax, [rdi]
0x180006425  or      esi, ebx
0x180006427  mov     ebx, 180h
0x18000642c  cmp     dword ptr [rsp+58h+arg_0], 0
0x180006431  mov     edx, eax
0x180006433  mov     [rdi], eax
0x180006435  jz      short loc_18000646F
0x180006437  test    dl, 2
0x18000643a  jnz     short loc_18000646F
0x18000643c  mov     eax, esi
0x18000643e  xor     eax, edx
0x180006440  and     eax, ebx
0x180006442  xor     eax, edx
0x180006444  mov     ecx, eax
0x180006446  xor     ecx, esi
0x180006448  and     ecx, r12d
0x18000644b  xor     ecx, eax
0x18000644d  mov     eax, ecx
0x18000644f  xor     eax, esi
0x180006451  and     eax, 1
0x180006454  xor     eax, ecx
0x180006456  mov     r8d, eax
0x180006459  xor     r8d, esi
0x18000645c  and     r8d, 800h
0x180006463  xor     r8d, eax
0x180006466  or      r8d, 2
0x18000646a  mov     [rdi], r8d
0x18000646d  jmp     short loc_180006472
0x18000646f  mov     r8d, edx
0x180006472  mov     r9d, edx
0x180006475  and     r9d, 4
0x180006479  jnz     short loc_180006490
0x18000647b  mov     ecx, esi
0x18000647d  xor     ecx, r8d
0x180006480  and     ecx, 400h
0x180006486  xor     ecx, r8d
0x180006489  or      ecx, 4
0x18000648c  mov     [rdi], ecx
0x18000648e  jmp     short loc_180006493
0x180006490  mov     ecx, r8d
0x180006493  mov     eax, edx
0x180006495  lock cmpxchg [r14], ecx
0x18000649a  jnz     short loc_18000642C
0x18000649c  test    r9d, r9d
0x18000649f  jnz     short loc_1800064B0
0x1800064a1  mov     r8d, ebp
0x1800064a4  lea     edx, [r9+3]
0x1800064a8  mov     rcx, r14
0x1800064ab  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800064b0  test    byte ptr [rdi], 2
0x1800064b3  jnz     short loc_1800064DC
0x1800064b5  mov     eax, [rdi]
0x1800064b7  xor     eax, esi
0x1800064b9  and     eax, ebx
0x1800064bb  xor     eax, [rdi]
0x1800064bd  mov     ecx, eax
0x1800064bf  xor     ecx, esi
0x1800064c1  and     ecx, r12d
0x1800064c4  xor     ecx, eax
0x1800064c6  mov     edx, ecx
0x1800064c8  xor     edx, esi
0x1800064ca  and     edx, 1
0x1800064cd  xor     edx, ecx
0x1800064cf  mov     eax, edx
0x1800064d1  xor     eax, esi
0x1800064d3  and     eax, 800h
0x1800064d8  xor     eax, edx
0x1800064da  mov     [rdi], eax
0x1800064dc  mov     rax, rdi
0x1800064df  add     rsp, 28h
0x1800064e3  pop     r14
0x1800064e5  pop     r12
0x1800064e7  pop     rdi
0x1800064e8  pop     rsi
0x1800064e9  pop     rbp
0x1800064ea  pop     rbx
0x1800064eb  retn
```
