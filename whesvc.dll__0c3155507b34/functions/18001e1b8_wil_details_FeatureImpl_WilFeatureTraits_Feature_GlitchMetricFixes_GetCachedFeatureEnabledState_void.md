# wil::details::FeatureImpl<__WilFeatureTraits_Feature_GlitchMetricFixes>::GetCachedFeatureEnabledState(void)

- ea: `0x18001e1b8`
- end: `0x18001e385`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_GlitchMetricFixes@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024be8`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x18001e1b8`
- `0x180025188`
- `0x180029010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_GlitchMetricFixes>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_GlitchMetricFixes__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_GlitchMetricFixes__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(61843204, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc02>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestLoc02>::GetImpl'::`2'::impl);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_GlitchMetricFixes__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_GlitchMetricFixes__descriptor, 3, v4);
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
0x18001e1b8  mov     [rsp+arg_0], rcx
0x18001e1bd  push    rbx
0x18001e1be  push    rbp
0x18001e1bf  push    rsi
0x18001e1c0  push    rdi
0x18001e1c1  push    r12
0x18001e1c3  push    r14
0x18001e1c5  sub     rsp, 28h
0x18001e1c9  mov     r14, cs:Feature_GlitchMetricFixes__descriptor
0x18001e1d0  mov     rdi, rdx
0x18001e1d3  mov     qword ptr [rdx], 0
0x18001e1da  mov     eax, [r14]
0x18001e1dd  mov     [rdx], eax
0x18001e1df  and     eax, 6
0x18001e1e2  cmp     al, 6
0x18001e1e4  jz      loc_18001E375
0x18001e1ea  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001e1ef  mov     ebp, eax
0x18001e1f1  mov     dword ptr [rsp+58h+arg_0], 0
0x18001e1f9  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001e200  test    rax, rax
0x18001e203  jz      short loc_18001E21D
0x18001e205  lea     r8, [rsp+58h+arg_0]
0x18001e20a  mov     edx, 3
0x18001e20f  mov     ecx, 3AFA704h
0x18001e214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e219  mov     edx, eax
0x18001e21b  jmp     short loc_18001E22B
0x18001e21d  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001e224  test    rax, rax
0x18001e227  jnz     short loc_18001E205
0x18001e229  xor     edx, edx
0x18001e22b  mov     r8d, edx
0x18001e22e  mov     eax, edx
0x18001e230  and     r8d, 0FFFFFF3Fh
0x18001e237  and     edx, 80h
0x18001e23d  mov     ecx, r8d
0x18001e240  mov     r12d, 40h ; '@'
0x18001e246  and     ecx, 3
0x18001e249  and     eax, r12d
0x18001e24c  shl     ecx, 2
0x18001e24f  or      ecx, eax
0x18001e251  shl     ecx, 2
0x18001e254  or      ecx, edx
0x18001e256  lea     ebx, ds:0[rcx*8]
0x18001e25d  test    r8d, r8d
0x18001e260  jnz     short loc_18001E267
0x18001e262  mov     eax, r12d
0x18001e265  jmp     short loc_18001E271
0x18001e267  xor     eax, eax
0x18001e269  cmp     r8d, 2
0x18001e26d  cmovz   eax, r12d
0x18001e271  or      ebx, eax
0x18001e273  mov     ecx, 0C00h
0x18001e278  mov     eax, ebx
0x18001e27a  and     eax, ecx
0x18001e27c  cmp     eax, ecx
0x18001e27e  jnz     short loc_18001E285
0x18001e280  mov     sil, 1
0x18001e283  jmp     short loc_18001E28D
0x18001e285  xor     sil, sil
0x18001e288  test    r12b, bl
0x18001e28b  jz      short loc_18001E2A8
0x18001e28d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestLoc02@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc02@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc02> `wil::Feature<__WilFeatureTraits_Feature_TestLoc02>::GetImpl(void)'::`2'::impl
0x18001e294  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc02@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc02>::__private_IsEnabled(wil::ReportingKind)
0x18001e299  test    sil, sil
0x18001e29c  jz      short loc_18001E2AA
0x18001e29e  test    al, al
0x18001e2a0  jnz     short loc_18001E2AA
0x18001e2a2  btr     ebx, 0Ah
0x18001e2a6  jmp     short loc_18001E2AA
0x18001e2a8  xor     al, al
0x18001e2aa  test    r12b, bl
0x18001e2ad  jz      short loc_18001E2BA
0x18001e2af  test    al, al
0x18001e2b1  jz      short loc_18001E2BA
0x18001e2b3  mov     esi, 1
0x18001e2b8  jmp     short loc_18001E2BC
0x18001e2ba  xor     esi, esi
0x18001e2bc  mov     eax, [rdi]
0x18001e2be  or      esi, ebx
0x18001e2c0  mov     ebx, 180h
0x18001e2c5  cmp     dword ptr [rsp+58h+arg_0], 0
0x18001e2ca  mov     edx, eax
0x18001e2cc  mov     [rdi], eax
0x18001e2ce  jz      short loc_18001E308
0x18001e2d0  test    dl, 2
0x18001e2d3  jnz     short loc_18001E308
0x18001e2d5  mov     eax, esi
0x18001e2d7  xor     eax, edx
0x18001e2d9  and     eax, ebx
0x18001e2db  xor     eax, edx
0x18001e2dd  mov     ecx, eax
0x18001e2df  xor     ecx, esi
0x18001e2e1  and     ecx, r12d
0x18001e2e4  xor     ecx, eax
0x18001e2e6  mov     eax, ecx
0x18001e2e8  xor     eax, esi
0x18001e2ea  and     eax, 1
0x18001e2ed  xor     eax, ecx
0x18001e2ef  mov     r8d, eax
0x18001e2f2  xor     r8d, esi
0x18001e2f5  and     r8d, 800h
0x18001e2fc  xor     r8d, eax
0x18001e2ff  or      r8d, 2
0x18001e303  mov     [rdi], r8d
0x18001e306  jmp     short loc_18001E30B
0x18001e308  mov     r8d, edx
0x18001e30b  mov     r9d, edx
0x18001e30e  and     r9d, 4
0x18001e312  jnz     short loc_18001E329
0x18001e314  mov     ecx, esi
0x18001e316  xor     ecx, r8d
0x18001e319  and     ecx, 400h
0x18001e31f  xor     ecx, r8d
0x18001e322  or      ecx, 4
0x18001e325  mov     [rdi], ecx
0x18001e327  jmp     short loc_18001E32C
0x18001e329  mov     ecx, r8d
0x18001e32c  mov     eax, edx
0x18001e32e  lock cmpxchg [r14], ecx
0x18001e333  jnz     short loc_18001E2C5
0x18001e335  test    r9d, r9d
0x18001e338  jnz     short loc_18001E349
0x18001e33a  mov     r8d, ebp
0x18001e33d  lea     edx, [r9+3]
0x18001e341  mov     rcx, r14
0x18001e344  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001e349  test    byte ptr [rdi], 2
0x18001e34c  jnz     short loc_18001E375
0x18001e34e  mov     eax, [rdi]
0x18001e350  xor     eax, esi
0x18001e352  and     eax, ebx
0x18001e354  xor     eax, [rdi]
0x18001e356  mov     ecx, eax
0x18001e358  xor     ecx, esi
0x18001e35a  and     ecx, r12d
0x18001e35d  xor     ecx, eax
0x18001e35f  mov     edx, ecx
0x18001e361  xor     edx, esi
0x18001e363  and     edx, 1
0x18001e366  xor     edx, ecx
0x18001e368  mov     eax, edx
0x18001e36a  xor     eax, esi
0x18001e36c  and     eax, 800h
0x18001e371  xor     eax, edx
0x18001e373  mov     [rdi], eax
0x18001e375  mov     rax, rdi
0x18001e378  add     rsp, 28h
0x18001e37c  pop     r14
0x18001e37e  pop     r12
0x18001e380  pop     rdi
0x18001e381  pop     rsi
0x18001e382  pop     rbp
0x18001e383  pop     rbx
0x18001e384  retn
```
