# wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_44936384>::GetCachedFeatureEnabledState(void)

- ea: `0x1800064d4`
- end: `0x1800066a1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_44936384@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d2f4`

## callees

- `0x180005dd0`
- `0x1800064d4`
- `0x18000c3f0`
- `0x18000d568`
- `0x180017010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_44936384>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_BugFix_44936384__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_BugFix_44936384__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(44936384, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UexTest7>::GetImpl'::`2'::impl);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_BugFix_44936384__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_BugFix_44936384__descriptor, 3, v4);
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
0x1800064d4  mov     [rsp+arg_0], rcx
0x1800064d9  push    rbx
0x1800064da  push    rbp
0x1800064db  push    rsi
0x1800064dc  push    rdi
0x1800064dd  push    r12
0x1800064df  push    r14
0x1800064e1  sub     rsp, 28h
0x1800064e5  mov     r14, cs:Feature_BugFix_44936384__descriptor
0x1800064ec  mov     rdi, rdx
0x1800064ef  mov     qword ptr [rdx], 0
0x1800064f6  mov     eax, [r14]
0x1800064f9  mov     [rdx], eax
0x1800064fb  and     eax, 6
0x1800064fe  cmp     al, 6
0x180006500  jz      loc_180006691
0x180006506  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000650b  mov     ebp, eax
0x18000650d  mov     dword ptr [rsp+58h+arg_0], 0
0x180006515  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000651c  test    rax, rax
0x18000651f  jz      short loc_180006539
0x180006521  lea     r8, [rsp+58h+arg_0]
0x180006526  mov     edx, 3
0x18000652b  mov     ecx, 2ADACC0h
0x180006530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006535  mov     edx, eax
0x180006537  jmp     short loc_180006547
0x180006539  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180006540  test    rax, rax
0x180006543  jnz     short loc_180006521
0x180006545  xor     edx, edx
0x180006547  mov     r8d, edx
0x18000654a  mov     eax, edx
0x18000654c  and     r8d, 0FFFFFF3Fh
0x180006553  and     edx, 80h
0x180006559  mov     ecx, r8d
0x18000655c  mov     r12d, 40h ; '@'
0x180006562  and     ecx, 3
0x180006565  and     eax, r12d
0x180006568  shl     ecx, 2
0x18000656b  or      ecx, eax
0x18000656d  shl     ecx, 2
0x180006570  or      ecx, edx
0x180006572  lea     ebx, ds:0[rcx*8]
0x180006579  test    r8d, r8d
0x18000657c  jnz     short loc_180006583
0x18000657e  mov     eax, r12d
0x180006581  jmp     short loc_18000658D
0x180006583  xor     eax, eax
0x180006585  cmp     r8d, 2
0x180006589  cmovz   eax, r12d
0x18000658d  or      ebx, eax
0x18000658f  mov     ecx, 0C00h
0x180006594  mov     eax, ebx
0x180006596  and     eax, ecx
0x180006598  cmp     eax, ecx
0x18000659a  jnz     short loc_1800065A1
0x18000659c  mov     sil, 1
0x18000659f  jmp     short loc_1800065A9
0x1800065a1  xor     sil, sil
0x1800065a4  test    r12b, bl
0x1800065a7  jz      short loc_1800065C4
0x1800065a9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UexTest7@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7> `wil::Feature<__WilFeatureTraits_Feature_UexTest7>::GetImpl(void)'::`2'::impl
0x1800065b0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(wil::ReportingKind)
0x1800065b5  test    sil, sil
0x1800065b8  jz      short loc_1800065C6
0x1800065ba  test    al, al
0x1800065bc  jnz     short loc_1800065C6
0x1800065be  btr     ebx, 0Ah
0x1800065c2  jmp     short loc_1800065C6
0x1800065c4  xor     al, al
0x1800065c6  test    r12b, bl
0x1800065c9  jz      short loc_1800065D6
0x1800065cb  test    al, al
0x1800065cd  jz      short loc_1800065D6
0x1800065cf  mov     esi, 1
0x1800065d4  jmp     short loc_1800065D8
0x1800065d6  xor     esi, esi
0x1800065d8  mov     eax, [rdi]
0x1800065da  or      esi, ebx
0x1800065dc  mov     ebx, 180h
0x1800065e1  cmp     dword ptr [rsp+58h+arg_0], 0
0x1800065e6  mov     edx, eax
0x1800065e8  mov     [rdi], eax
0x1800065ea  jz      short loc_180006624
0x1800065ec  test    dl, 2
0x1800065ef  jnz     short loc_180006624
0x1800065f1  mov     eax, esi
0x1800065f3  xor     eax, edx
0x1800065f5  and     eax, ebx
0x1800065f7  xor     eax, edx
0x1800065f9  mov     ecx, eax
0x1800065fb  xor     ecx, esi
0x1800065fd  and     ecx, r12d
0x180006600  xor     ecx, eax
0x180006602  mov     eax, ecx
0x180006604  xor     eax, esi
0x180006606  and     eax, 1
0x180006609  xor     eax, ecx
0x18000660b  mov     r8d, eax
0x18000660e  xor     r8d, esi
0x180006611  and     r8d, 800h
0x180006618  xor     r8d, eax
0x18000661b  or      r8d, 2
0x18000661f  mov     [rdi], r8d
0x180006622  jmp     short loc_180006627
0x180006624  mov     r8d, edx
0x180006627  mov     r9d, edx
0x18000662a  and     r9d, 4
0x18000662e  jnz     short loc_180006645
0x180006630  mov     ecx, esi
0x180006632  xor     ecx, r8d
0x180006635  and     ecx, 400h
0x18000663b  xor     ecx, r8d
0x18000663e  or      ecx, 4
0x180006641  mov     [rdi], ecx
0x180006643  jmp     short loc_180006648
0x180006645  mov     ecx, r8d
0x180006648  mov     eax, edx
0x18000664a  lock cmpxchg [r14], ecx
0x18000664f  jnz     short loc_1800065E1
0x180006651  test    r9d, r9d
0x180006654  jnz     short loc_180006665
0x180006656  mov     r8d, ebp
0x180006659  lea     edx, [r9+3]
0x18000665d  mov     rcx, r14
0x180006660  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180006665  test    byte ptr [rdi], 2
0x180006668  jnz     short loc_180006691
0x18000666a  mov     eax, [rdi]
0x18000666c  xor     eax, esi
0x18000666e  and     eax, ebx
0x180006670  xor     eax, [rdi]
0x180006672  mov     ecx, eax
0x180006674  xor     ecx, esi
0x180006676  and     ecx, r12d
0x180006679  xor     ecx, eax
0x18000667b  mov     edx, ecx
0x18000667d  xor     edx, esi
0x18000667f  and     edx, 1
0x180006682  xor     edx, ecx
0x180006684  mov     eax, edx
0x180006686  xor     eax, esi
0x180006688  and     eax, 800h
0x18000668d  xor     eax, edx
0x18000668f  mov     [rdi], eax
0x180006691  mov     rax, rdi
0x180006694  add     rsp, 28h
0x180006698  pop     r14
0x18000669a  pop     r12
0x18000669c  pop     rdi
0x18000669d  pop     rsi
0x18000669e  pop     rbp
0x18000669f  pop     rbx
0x1800066a0  retn
```
