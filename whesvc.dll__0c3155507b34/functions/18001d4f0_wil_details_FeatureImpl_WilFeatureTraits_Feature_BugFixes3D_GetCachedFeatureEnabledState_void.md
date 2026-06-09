# wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes3D>::GetCachedFeatureEnabledState(void)

- ea: `0x18001d4f0`
- end: `0x18001d6bd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes3D@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024788`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x18001772c`
- `0x18001d4f0`
- `0x180029010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes3D>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_BugFixes3D__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_BugFixes3D__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(60757810, 3, &v20);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_BugFixes3D__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_BugFixes3D__descriptor, 3, v4);
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
0x18001d4f0  mov     [rsp+arg_0], rcx
0x18001d4f5  push    rbx
0x18001d4f6  push    rbp
0x18001d4f7  push    rsi
0x18001d4f8  push    rdi
0x18001d4f9  push    r12
0x18001d4fb  push    r14
0x18001d4fd  sub     rsp, 28h
0x18001d501  mov     r14, cs:Feature_BugFixes3D__descriptor
0x18001d508  mov     rdi, rdx
0x18001d50b  mov     qword ptr [rdx], 0
0x18001d512  mov     eax, [r14]
0x18001d515  mov     [rdx], eax
0x18001d517  and     eax, 6
0x18001d51a  cmp     al, 6
0x18001d51c  jz      loc_18001D6AD
0x18001d522  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001d527  mov     ebp, eax
0x18001d529  mov     dword ptr [rsp+58h+arg_0], 0
0x18001d531  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001d538  test    rax, rax
0x18001d53b  jz      short loc_18001D555
0x18001d53d  lea     r8, [rsp+58h+arg_0]
0x18001d542  mov     edx, 3
0x18001d547  mov     ecx, 39F1732h
0x18001d54c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d551  mov     edx, eax
0x18001d553  jmp     short loc_18001D563
0x18001d555  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001d55c  test    rax, rax
0x18001d55f  jnz     short loc_18001D53D
0x18001d561  xor     edx, edx
0x18001d563  mov     r8d, edx
0x18001d566  mov     eax, edx
0x18001d568  and     r8d, 0FFFFFF3Fh
0x18001d56f  and     edx, 80h
0x18001d575  mov     ecx, r8d
0x18001d578  mov     r12d, 40h ; '@'
0x18001d57e  and     ecx, 3
0x18001d581  and     eax, r12d
0x18001d584  shl     ecx, 2
0x18001d587  or      ecx, eax
0x18001d589  shl     ecx, 2
0x18001d58c  or      ecx, edx
0x18001d58e  lea     ebx, ds:0[rcx*8]
0x18001d595  test    r8d, r8d
0x18001d598  jnz     short loc_18001D59F
0x18001d59a  mov     eax, r12d
0x18001d59d  jmp     short loc_18001D5A9
0x18001d59f  xor     eax, eax
0x18001d5a1  cmp     r8d, 2
0x18001d5a5  cmovz   eax, r12d
0x18001d5a9  or      ebx, eax
0x18001d5ab  mov     ecx, 0C00h
0x18001d5b0  mov     eax, ebx
0x18001d5b2  and     eax, ecx
0x18001d5b4  cmp     eax, ecx
0x18001d5b6  jnz     short loc_18001D5BD
0x18001d5b8  mov     sil, 1
0x18001d5bb  jmp     short loc_18001D5C5
0x18001d5bd  xor     sil, sil
0x18001d5c0  test    r12b, bl
0x18001d5c3  jz      short loc_18001D5E0
0x18001d5c5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UexTest7@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7> `wil::Feature<__WilFeatureTraits_Feature_UexTest7>::GetImpl(void)'::`2'::impl
0x18001d5cc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(wil::ReportingKind)
0x18001d5d1  test    sil, sil
0x18001d5d4  jz      short loc_18001D5E2
0x18001d5d6  test    al, al
0x18001d5d8  jnz     short loc_18001D5E2
0x18001d5da  btr     ebx, 0Ah
0x18001d5de  jmp     short loc_18001D5E2
0x18001d5e0  xor     al, al
0x18001d5e2  test    r12b, bl
0x18001d5e5  jz      short loc_18001D5F2
0x18001d5e7  test    al, al
0x18001d5e9  jz      short loc_18001D5F2
0x18001d5eb  mov     esi, 1
0x18001d5f0  jmp     short loc_18001D5F4
0x18001d5f2  xor     esi, esi
0x18001d5f4  mov     eax, [rdi]
0x18001d5f6  or      esi, ebx
0x18001d5f8  mov     ebx, 180h
0x18001d5fd  cmp     dword ptr [rsp+58h+arg_0], 0
0x18001d602  mov     edx, eax
0x18001d604  mov     [rdi], eax
0x18001d606  jz      short loc_18001D640
0x18001d608  test    dl, 2
0x18001d60b  jnz     short loc_18001D640
0x18001d60d  mov     eax, esi
0x18001d60f  xor     eax, edx
0x18001d611  and     eax, ebx
0x18001d613  xor     eax, edx
0x18001d615  mov     ecx, eax
0x18001d617  xor     ecx, esi
0x18001d619  and     ecx, r12d
0x18001d61c  xor     ecx, eax
0x18001d61e  mov     eax, ecx
0x18001d620  xor     eax, esi
0x18001d622  and     eax, 1
0x18001d625  xor     eax, ecx
0x18001d627  mov     r8d, eax
0x18001d62a  xor     r8d, esi
0x18001d62d  and     r8d, 800h
0x18001d634  xor     r8d, eax
0x18001d637  or      r8d, 2
0x18001d63b  mov     [rdi], r8d
0x18001d63e  jmp     short loc_18001D643
0x18001d640  mov     r8d, edx
0x18001d643  mov     r9d, edx
0x18001d646  and     r9d, 4
0x18001d64a  jnz     short loc_18001D661
0x18001d64c  mov     ecx, esi
0x18001d64e  xor     ecx, r8d
0x18001d651  and     ecx, 400h
0x18001d657  xor     ecx, r8d
0x18001d65a  or      ecx, 4
0x18001d65d  mov     [rdi], ecx
0x18001d65f  jmp     short loc_18001D664
0x18001d661  mov     ecx, r8d
0x18001d664  mov     eax, edx
0x18001d666  lock cmpxchg [r14], ecx
0x18001d66b  jnz     short loc_18001D5FD
0x18001d66d  test    r9d, r9d
0x18001d670  jnz     short loc_18001D681
0x18001d672  mov     r8d, ebp
0x18001d675  lea     edx, [r9+3]
0x18001d679  mov     rcx, r14
0x18001d67c  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001d681  test    byte ptr [rdi], 2
0x18001d684  jnz     short loc_18001D6AD
0x18001d686  mov     eax, [rdi]
0x18001d688  xor     eax, esi
0x18001d68a  and     eax, ebx
0x18001d68c  xor     eax, [rdi]
0x18001d68e  mov     ecx, eax
0x18001d690  xor     ecx, esi
0x18001d692  and     ecx, r12d
0x18001d695  xor     ecx, eax
0x18001d697  mov     edx, ecx
0x18001d699  xor     edx, esi
0x18001d69b  and     edx, 1
0x18001d69e  xor     edx, ecx
0x18001d6a0  mov     eax, edx
0x18001d6a2  xor     eax, esi
0x18001d6a4  and     eax, 800h
0x18001d6a9  xor     eax, edx
0x18001d6ab  mov     [rdi], eax
0x18001d6ad  mov     rax, rdi
0x18001d6b0  add     rsp, 28h
0x18001d6b4  pop     r14
0x18001d6b6  pop     r12
0x18001d6b8  pop     rdi
0x18001d6b9  pop     rsi
0x18001d6ba  pop     rbp
0x18001d6bb  pop     rbx
0x18001d6bc  retn
```
