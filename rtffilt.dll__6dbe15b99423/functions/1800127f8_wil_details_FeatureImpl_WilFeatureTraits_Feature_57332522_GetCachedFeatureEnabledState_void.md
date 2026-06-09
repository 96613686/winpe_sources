# wil::details::FeatureImpl<__WilFeatureTraits_Feature_57332522>::GetCachedFeatureEnabledState(void)

- ea: `0x1800127f8`
- end: `0x1800129c5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_57332522@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015524`

## callees

- `0x180005dd8`
- `0x18000b3d8`
- `0x1800127f8`
- `0x1800152c8`
- `0x18001b010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_57332522>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_57332522__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_57332522__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(57332522, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_51365605>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_51365605>::GetImpl'::`2'::impl);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_57332522__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      (volatile signed __int32 *)Feature_57332522__descriptor,
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
0x1800127f8  mov     [rsp+arg_0], rcx
0x1800127fd  push    rbx
0x1800127fe  push    rbp
0x1800127ff  push    rsi
0x180012800  push    rdi
0x180012801  push    r12
0x180012803  push    r14
0x180012805  sub     rsp, 28h
0x180012809  mov     r14, cs:Feature_57332522__descriptor
0x180012810  mov     rdi, rdx
0x180012813  mov     qword ptr [rdx], 0
0x18001281a  mov     eax, [r14]
0x18001281d  mov     [rdx], eax
0x18001281f  and     eax, 6
0x180012822  cmp     al, 6
0x180012824  jz      loc_1800129B5
0x18001282a  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001282f  mov     ebp, eax
0x180012831  mov     dword ptr [rsp+58h+arg_0], 0
0x180012839  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180012840  test    rax, rax
0x180012843  jz      short loc_18001285D
0x180012845  lea     r8, [rsp+58h+arg_0]
0x18001284a  mov     edx, 3
0x18001284f  mov     ecx, 36AD32Ah
0x180012854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012859  mov     edx, eax
0x18001285b  jmp     short loc_18001286B
0x18001285d  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180012864  test    rax, rax
0x180012867  jnz     short loc_180012845
0x180012869  xor     edx, edx
0x18001286b  mov     r8d, edx
0x18001286e  mov     eax, edx
0x180012870  and     r8d, 0FFFFFF3Fh
0x180012877  and     edx, 80h
0x18001287d  mov     ecx, r8d
0x180012880  mov     r12d, 40h ; '@'
0x180012886  and     ecx, 3
0x180012889  and     eax, r12d
0x18001288c  shl     ecx, 2
0x18001288f  or      ecx, eax
0x180012891  shl     ecx, 2
0x180012894  or      ecx, edx
0x180012896  lea     ebx, ds:0[rcx*8]
0x18001289d  test    r8d, r8d
0x1800128a0  jnz     short loc_1800128A7
0x1800128a2  mov     eax, r12d
0x1800128a5  jmp     short loc_1800128B1
0x1800128a7  xor     eax, eax
0x1800128a9  cmp     r8d, 2
0x1800128ad  cmovz   eax, r12d
0x1800128b1  or      ebx, eax
0x1800128b3  mov     ecx, 0C00h
0x1800128b8  mov     eax, ebx
0x1800128ba  and     eax, ecx
0x1800128bc  cmp     eax, ecx
0x1800128be  jnz     short loc_1800128C5
0x1800128c0  mov     sil, 1
0x1800128c3  jmp     short loc_1800128CD
0x1800128c5  xor     sil, sil
0x1800128c8  test    r12b, bl
0x1800128cb  jz      short loc_1800128E8
0x1800128cd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_51365605@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_51365605@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_51365605> `wil::Feature<__WilFeatureTraits_Feature_51365605>::GetImpl(void)'::`2'::impl
0x1800128d4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_51365605@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_51365605>::__private_IsEnabled(wil::ReportingKind)
0x1800128d9  test    sil, sil
0x1800128dc  jz      short loc_1800128EA
0x1800128de  test    al, al
0x1800128e0  jnz     short loc_1800128EA
0x1800128e2  btr     ebx, 0Ah
0x1800128e6  jmp     short loc_1800128EA
0x1800128e8  xor     al, al
0x1800128ea  test    r12b, bl
0x1800128ed  jz      short loc_1800128FA
0x1800128ef  test    al, al
0x1800128f1  jz      short loc_1800128FA
0x1800128f3  mov     esi, 1
0x1800128f8  jmp     short loc_1800128FC
0x1800128fa  xor     esi, esi
0x1800128fc  mov     eax, [rdi]
0x1800128fe  or      esi, ebx
0x180012900  mov     ebx, 180h
0x180012905  cmp     dword ptr [rsp+58h+arg_0], 0
0x18001290a  mov     edx, eax
0x18001290c  mov     [rdi], eax
0x18001290e  jz      short loc_180012948
0x180012910  test    dl, 2
0x180012913  jnz     short loc_180012948
0x180012915  mov     eax, esi
0x180012917  xor     eax, edx
0x180012919  and     eax, ebx
0x18001291b  xor     eax, edx
0x18001291d  mov     ecx, eax
0x18001291f  xor     ecx, esi
0x180012921  and     ecx, r12d
0x180012924  xor     ecx, eax
0x180012926  mov     eax, ecx
0x180012928  xor     eax, esi
0x18001292a  and     eax, 1
0x18001292d  xor     eax, ecx
0x18001292f  mov     r8d, eax
0x180012932  xor     r8d, esi
0x180012935  and     r8d, 800h
0x18001293c  xor     r8d, eax
0x18001293f  or      r8d, 2
0x180012943  mov     [rdi], r8d
0x180012946  jmp     short loc_18001294B
0x180012948  mov     r8d, edx
0x18001294b  mov     r9d, edx
0x18001294e  and     r9d, 4
0x180012952  jnz     short loc_180012969
0x180012954  mov     ecx, esi
0x180012956  xor     ecx, r8d
0x180012959  and     ecx, 400h
0x18001295f  xor     ecx, r8d
0x180012962  or      ecx, 4
0x180012965  mov     [rdi], ecx
0x180012967  jmp     short loc_18001296C
0x180012969  mov     ecx, r8d
0x18001296c  mov     eax, edx
0x18001296e  lock cmpxchg [r14], ecx
0x180012973  jnz     short loc_180012905
0x180012975  test    r9d, r9d
0x180012978  jnz     short loc_180012989
0x18001297a  mov     r8d, ebp
0x18001297d  lea     edx, [r9+3]
0x180012981  mov     rcx, r14
0x180012984  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180012989  test    byte ptr [rdi], 2
0x18001298c  jnz     short loc_1800129B5
0x18001298e  mov     eax, [rdi]
0x180012990  xor     eax, esi
0x180012992  and     eax, ebx
0x180012994  xor     eax, [rdi]
0x180012996  mov     ecx, eax
0x180012998  xor     ecx, esi
0x18001299a  and     ecx, r12d
0x18001299d  xor     ecx, eax
0x18001299f  mov     edx, ecx
0x1800129a1  xor     edx, esi
0x1800129a3  and     edx, 1
0x1800129a6  xor     edx, ecx
0x1800129a8  mov     eax, edx
0x1800129aa  xor     eax, esi
0x1800129ac  and     eax, 800h
0x1800129b1  xor     eax, edx
0x1800129b3  mov     [rdi], eax
0x1800129b5  mov     rax, rdi
0x1800129b8  add     rsp, 28h
0x1800129bc  pop     r14
0x1800129be  pop     r12
0x1800129c0  pop     rdi
0x1800129c1  pop     rsi
0x1800129c2  pop     rbp
0x1800129c3  pop     rbx
0x1800129c4  retn
```
