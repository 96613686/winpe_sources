# wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoEscalationSupport>::GetCachedFeatureEnabledState(void)

- ea: `0x18001d148`
- end: `0x18001d315`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoEscalationSupport@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024668`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x180017558`
- `0x18001d148`
- `0x180029010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoEscalationSupport>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_AutoEscalationSupport__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_AutoEscalationSupport__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(59872159, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl'::`2'::impl);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_AutoEscalationSupport__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_AutoEscalationSupport__descriptor, 3, v4);
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
0x18001d148  mov     [rsp+arg_0], rcx
0x18001d14d  push    rbx
0x18001d14e  push    rbp
0x18001d14f  push    rsi
0x18001d150  push    rdi
0x18001d151  push    r12
0x18001d153  push    r14
0x18001d155  sub     rsp, 28h
0x18001d159  mov     r14, cs:Feature_AutoEscalationSupport__descriptor
0x18001d160  mov     rdi, rdx
0x18001d163  mov     qword ptr [rdx], 0
0x18001d16a  mov     eax, [r14]
0x18001d16d  mov     [rdx], eax
0x18001d16f  and     eax, 6
0x18001d172  cmp     al, 6
0x18001d174  jz      loc_18001D305
0x18001d17a  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001d17f  mov     ebp, eax
0x18001d181  mov     dword ptr [rsp+58h+arg_0], 0
0x18001d189  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001d190  test    rax, rax
0x18001d193  jz      short loc_18001D1AD
0x18001d195  lea     r8, [rsp+58h+arg_0]
0x18001d19a  mov     edx, 3
0x18001d19f  mov     ecx, 391939Fh
0x18001d1a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1a9  mov     edx, eax
0x18001d1ab  jmp     short loc_18001D1BB
0x18001d1ad  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001d1b4  test    rax, rax
0x18001d1b7  jnz     short loc_18001D195
0x18001d1b9  xor     edx, edx
0x18001d1bb  mov     r8d, edx
0x18001d1be  mov     eax, edx
0x18001d1c0  and     r8d, 0FFFFFF3Fh
0x18001d1c7  and     edx, 80h
0x18001d1cd  mov     ecx, r8d
0x18001d1d0  mov     r12d, 40h ; '@'
0x18001d1d6  and     ecx, 3
0x18001d1d9  and     eax, r12d
0x18001d1dc  shl     ecx, 2
0x18001d1df  or      ecx, eax
0x18001d1e1  shl     ecx, 2
0x18001d1e4  or      ecx, edx
0x18001d1e6  lea     ebx, ds:0[rcx*8]
0x18001d1ed  test    r8d, r8d
0x18001d1f0  jnz     short loc_18001D1F7
0x18001d1f2  mov     eax, r12d
0x18001d1f5  jmp     short loc_18001D201
0x18001d1f7  xor     eax, eax
0x18001d1f9  cmp     r8d, 2
0x18001d1fd  cmovz   eax, r12d
0x18001d201  or      ebx, eax
0x18001d203  mov     ecx, 0C00h
0x18001d208  mov     eax, ebx
0x18001d20a  and     eax, ecx
0x18001d20c  cmp     eax, ecx
0x18001d20e  jnz     short loc_18001D215
0x18001d210  mov     sil, 1
0x18001d213  jmp     short loc_18001D21D
0x18001d215  xor     sil, sil
0x18001d218  test    r12b, bl
0x18001d21b  jz      short loc_18001D238
0x18001d21d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestAccPerf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf> `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl(void)'::`2'::impl
0x18001d224  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x18001d229  test    sil, sil
0x18001d22c  jz      short loc_18001D23A
0x18001d22e  test    al, al
0x18001d230  jnz     short loc_18001D23A
0x18001d232  btr     ebx, 0Ah
0x18001d236  jmp     short loc_18001D23A
0x18001d238  xor     al, al
0x18001d23a  test    r12b, bl
0x18001d23d  jz      short loc_18001D24A
0x18001d23f  test    al, al
0x18001d241  jz      short loc_18001D24A
0x18001d243  mov     esi, 1
0x18001d248  jmp     short loc_18001D24C
0x18001d24a  xor     esi, esi
0x18001d24c  mov     eax, [rdi]
0x18001d24e  or      esi, ebx
0x18001d250  mov     ebx, 180h
0x18001d255  cmp     dword ptr [rsp+58h+arg_0], 0
0x18001d25a  mov     edx, eax
0x18001d25c  mov     [rdi], eax
0x18001d25e  jz      short loc_18001D298
0x18001d260  test    dl, 2
0x18001d263  jnz     short loc_18001D298
0x18001d265  mov     eax, esi
0x18001d267  xor     eax, edx
0x18001d269  and     eax, ebx
0x18001d26b  xor     eax, edx
0x18001d26d  mov     ecx, eax
0x18001d26f  xor     ecx, esi
0x18001d271  and     ecx, r12d
0x18001d274  xor     ecx, eax
0x18001d276  mov     eax, ecx
0x18001d278  xor     eax, esi
0x18001d27a  and     eax, 1
0x18001d27d  xor     eax, ecx
0x18001d27f  mov     r8d, eax
0x18001d282  xor     r8d, esi
0x18001d285  and     r8d, 800h
0x18001d28c  xor     r8d, eax
0x18001d28f  or      r8d, 2
0x18001d293  mov     [rdi], r8d
0x18001d296  jmp     short loc_18001D29B
0x18001d298  mov     r8d, edx
0x18001d29b  mov     r9d, edx
0x18001d29e  and     r9d, 4
0x18001d2a2  jnz     short loc_18001D2B9
0x18001d2a4  mov     ecx, esi
0x18001d2a6  xor     ecx, r8d
0x18001d2a9  and     ecx, 400h
0x18001d2af  xor     ecx, r8d
0x18001d2b2  or      ecx, 4
0x18001d2b5  mov     [rdi], ecx
0x18001d2b7  jmp     short loc_18001D2BC
0x18001d2b9  mov     ecx, r8d
0x18001d2bc  mov     eax, edx
0x18001d2be  lock cmpxchg [r14], ecx
0x18001d2c3  jnz     short loc_18001D255
0x18001d2c5  test    r9d, r9d
0x18001d2c8  jnz     short loc_18001D2D9
0x18001d2ca  mov     r8d, ebp
0x18001d2cd  lea     edx, [r9+3]
0x18001d2d1  mov     rcx, r14
0x18001d2d4  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001d2d9  test    byte ptr [rdi], 2
0x18001d2dc  jnz     short loc_18001D305
0x18001d2de  mov     eax, [rdi]
0x18001d2e0  xor     eax, esi
0x18001d2e2  and     eax, ebx
0x18001d2e4  xor     eax, [rdi]
0x18001d2e6  mov     ecx, eax
0x18001d2e8  xor     ecx, esi
0x18001d2ea  and     ecx, r12d
0x18001d2ed  xor     ecx, eax
0x18001d2ef  mov     edx, ecx
0x18001d2f1  xor     edx, esi
0x18001d2f3  and     edx, 1
0x18001d2f6  xor     edx, ecx
0x18001d2f8  mov     eax, edx
0x18001d2fa  xor     eax, esi
0x18001d2fc  and     eax, 800h
0x18001d301  xor     eax, edx
0x18001d303  mov     [rdi], eax
0x18001d305  mov     rax, rdi
0x18001d308  add     rsp, 28h
0x18001d30c  pop     r14
0x18001d30e  pop     r12
0x18001d310  pop     rdi
0x18001d311  pop     rsi
0x18001d312  pop     rbp
0x18001d313  pop     rbx
0x18001d314  retn
```
