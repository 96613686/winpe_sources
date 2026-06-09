# wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixesQ3>::GetCachedFeatureEnabledState(void)

- ea: `0x180012850`
- end: `0x180012a1d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixesQ3@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001741c`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x180012850`
- `0x1800175f4`
- `0x180029010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixesQ3>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_BugFixesQ3__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_BugFixesQ3__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(59125405, 3, &v20);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_BugFixesQ3__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_BugFixesQ3__descriptor, 3, v4);
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
0x180012850  mov     [rsp+arg_0], rcx
0x180012855  push    rbx
0x180012856  push    rbp
0x180012857  push    rsi
0x180012858  push    rdi
0x180012859  push    r12
0x18001285b  push    r14
0x18001285d  sub     rsp, 28h
0x180012861  mov     r14, cs:Feature_BugFixesQ3__descriptor
0x180012868  mov     rdi, rdx
0x18001286b  mov     qword ptr [rdx], 0
0x180012872  mov     eax, [r14]
0x180012875  mov     [rdx], eax
0x180012877  and     eax, 6
0x18001287a  cmp     al, 6
0x18001287c  jz      loc_180012A0D
0x180012882  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012887  mov     ebp, eax
0x180012889  mov     dword ptr [rsp+58h+arg_0], 0
0x180012891  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180012898  test    rax, rax
0x18001289b  jz      short loc_1800128B5
0x18001289d  lea     r8, [rsp+58h+arg_0]
0x1800128a2  mov     edx, 3
0x1800128a7  mov     ecx, 3862E9Dh
0x1800128ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128b1  mov     edx, eax
0x1800128b3  jmp     short loc_1800128C3
0x1800128b5  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800128bc  test    rax, rax
0x1800128bf  jnz     short loc_18001289D
0x1800128c1  xor     edx, edx
0x1800128c3  mov     r8d, edx
0x1800128c6  mov     eax, edx
0x1800128c8  and     r8d, 0FFFFFF3Fh
0x1800128cf  and     edx, 80h
0x1800128d5  mov     ecx, r8d
0x1800128d8  mov     r12d, 40h ; '@'
0x1800128de  and     ecx, 3
0x1800128e1  and     eax, r12d
0x1800128e4  shl     ecx, 2
0x1800128e7  or      ecx, eax
0x1800128e9  shl     ecx, 2
0x1800128ec  or      ecx, edx
0x1800128ee  lea     ebx, ds:0[rcx*8]
0x1800128f5  test    r8d, r8d
0x1800128f8  jnz     short loc_1800128FF
0x1800128fa  mov     eax, r12d
0x1800128fd  jmp     short loc_180012909
0x1800128ff  xor     eax, eax
0x180012901  cmp     r8d, 2
0x180012905  cmovz   eax, r12d
0x180012909  or      ebx, eax
0x18001290b  mov     ecx, 0C00h
0x180012910  mov     eax, ebx
0x180012912  and     eax, ecx
0x180012914  cmp     eax, ecx
0x180012916  jnz     short loc_18001291D
0x180012918  mov     sil, 1
0x18001291b  jmp     short loc_180012925
0x18001291d  xor     sil, sil
0x180012920  test    r12b, bl
0x180012923  jz      short loc_180012940
0x180012925  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestLoc1Perf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf> `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl(void)'::`2'::impl
0x18001292c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x180012931  test    sil, sil
0x180012934  jz      short loc_180012942
0x180012936  test    al, al
0x180012938  jnz     short loc_180012942
0x18001293a  btr     ebx, 0Ah
0x18001293e  jmp     short loc_180012942
0x180012940  xor     al, al
0x180012942  test    r12b, bl
0x180012945  jz      short loc_180012952
0x180012947  test    al, al
0x180012949  jz      short loc_180012952
0x18001294b  mov     esi, 1
0x180012950  jmp     short loc_180012954
0x180012952  xor     esi, esi
0x180012954  mov     eax, [rdi]
0x180012956  or      esi, ebx
0x180012958  mov     ebx, 180h
0x18001295d  cmp     dword ptr [rsp+58h+arg_0], 0
0x180012962  mov     edx, eax
0x180012964  mov     [rdi], eax
0x180012966  jz      short loc_1800129A0
0x180012968  test    dl, 2
0x18001296b  jnz     short loc_1800129A0
0x18001296d  mov     eax, esi
0x18001296f  xor     eax, edx
0x180012971  and     eax, ebx
0x180012973  xor     eax, edx
0x180012975  mov     ecx, eax
0x180012977  xor     ecx, esi
0x180012979  and     ecx, r12d
0x18001297c  xor     ecx, eax
0x18001297e  mov     eax, ecx
0x180012980  xor     eax, esi
0x180012982  and     eax, 1
0x180012985  xor     eax, ecx
0x180012987  mov     r8d, eax
0x18001298a  xor     r8d, esi
0x18001298d  and     r8d, 800h
0x180012994  xor     r8d, eax
0x180012997  or      r8d, 2
0x18001299b  mov     [rdi], r8d
0x18001299e  jmp     short loc_1800129A3
0x1800129a0  mov     r8d, edx
0x1800129a3  mov     r9d, edx
0x1800129a6  and     r9d, 4
0x1800129aa  jnz     short loc_1800129C1
0x1800129ac  mov     ecx, esi
0x1800129ae  xor     ecx, r8d
0x1800129b1  and     ecx, 400h
0x1800129b7  xor     ecx, r8d
0x1800129ba  or      ecx, 4
0x1800129bd  mov     [rdi], ecx
0x1800129bf  jmp     short loc_1800129C4
0x1800129c1  mov     ecx, r8d
0x1800129c4  mov     eax, edx
0x1800129c6  lock cmpxchg [r14], ecx
0x1800129cb  jnz     short loc_18001295D
0x1800129cd  test    r9d, r9d
0x1800129d0  jnz     short loc_1800129E1
0x1800129d2  mov     r8d, ebp
0x1800129d5  lea     edx, [r9+3]
0x1800129d9  mov     rcx, r14
0x1800129dc  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800129e1  test    byte ptr [rdi], 2
0x1800129e4  jnz     short loc_180012A0D
0x1800129e6  mov     eax, [rdi]
0x1800129e8  xor     eax, esi
0x1800129ea  and     eax, ebx
0x1800129ec  xor     eax, [rdi]
0x1800129ee  mov     ecx, eax
0x1800129f0  xor     ecx, esi
0x1800129f2  and     ecx, r12d
0x1800129f5  xor     ecx, eax
0x1800129f7  mov     edx, ecx
0x1800129f9  xor     edx, esi
0x1800129fb  and     edx, 1
0x1800129fe  xor     edx, ecx
0x180012a00  mov     eax, edx
0x180012a02  xor     eax, esi
0x180012a04  and     eax, 800h
0x180012a09  xor     eax, edx
0x180012a0b  mov     [rdi], eax
0x180012a0d  mov     rax, rdi
0x180012a10  add     rsp, 28h
0x180012a14  pop     r14
0x180012a16  pop     r12
0x180012a18  pop     rdi
0x180012a19  pop     rsi
0x180012a1a  pop     rbp
0x180012a1b  pop     rbx
0x180012a1c  retn
```
