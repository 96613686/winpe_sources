# wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes5D>::GetCachedFeatureEnabledState(void)

- ea: `0x18001d898`
- end: `0x18001da65`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes5D@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800248c8`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x18001d898`
- `0x180025404`
- `0x180029010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes5D>::GetCachedFeatureEnabledState(
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
  unsigned __int8 IsEnabled; // al
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
  v3 = *(_DWORD *)Feature_BugFixes5D__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_BugFixes5D__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(61363933, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl'::`2'::impl);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_BugFixes5D__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_BugFixes5D__descriptor, 3, v4);
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
0x18001d898  mov     [rsp+arg_0], rcx
0x18001d89d  push    rbx
0x18001d89e  push    rbp
0x18001d89f  push    rsi
0x18001d8a0  push    rdi
0x18001d8a1  push    r12
0x18001d8a3  push    r14
0x18001d8a5  sub     rsp, 28h
0x18001d8a9  mov     r14, cs:Feature_BugFixes5D__descriptor
0x18001d8b0  mov     rdi, rdx
0x18001d8b3  mov     qword ptr [rdx], 0
0x18001d8ba  mov     eax, [r14]
0x18001d8bd  mov     [rdx], eax
0x18001d8bf  and     eax, 6
0x18001d8c2  cmp     al, 6
0x18001d8c4  jz      loc_18001DA55
0x18001d8ca  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001d8cf  mov     ebp, eax
0x18001d8d1  mov     dword ptr [rsp+58h+arg_0], 0
0x18001d8d9  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001d8e0  test    rax, rax
0x18001d8e3  jz      short loc_18001D8FD
0x18001d8e5  lea     r8, [rsp+58h+arg_0]
0x18001d8ea  mov     edx, 3
0x18001d8ef  mov     ecx, 3A856DDh
0x18001d8f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8f9  mov     edx, eax
0x18001d8fb  jmp     short loc_18001D90B
0x18001d8fd  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001d904  test    rax, rax
0x18001d907  jnz     short loc_18001D8E5
0x18001d909  xor     edx, edx
0x18001d90b  mov     r8d, edx
0x18001d90e  mov     eax, edx
0x18001d910  and     r8d, 0FFFFFF3Fh
0x18001d917  and     edx, 80h
0x18001d91d  mov     ecx, r8d
0x18001d920  mov     r12d, 40h ; '@'
0x18001d926  and     ecx, 3
0x18001d929  and     eax, r12d
0x18001d92c  shl     ecx, 2
0x18001d92f  or      ecx, eax
0x18001d931  shl     ecx, 2
0x18001d934  or      ecx, edx
0x18001d936  lea     ebx, ds:0[rcx*8]
0x18001d93d  test    r8d, r8d
0x18001d940  jnz     short loc_18001D947
0x18001d942  mov     eax, r12d
0x18001d945  jmp     short loc_18001D951
0x18001d947  xor     eax, eax
0x18001d949  cmp     r8d, 2
0x18001d94d  cmovz   eax, r12d
0x18001d951  or      ebx, eax
0x18001d953  mov     ecx, 0C00h
0x18001d958  mov     eax, ebx
0x18001d95a  and     eax, ecx
0x18001d95c  cmp     eax, ecx
0x18001d95e  jnz     short loc_18001D965
0x18001d960  mov     sil, 1
0x18001d963  jmp     short loc_18001D96D
0x18001d965  xor     sil, sil
0x18001d968  test    r12b, bl
0x18001d96b  jz      short loc_18001D988
0x18001d96d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x18001d974  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x18001d979  test    sil, sil
0x18001d97c  jz      short loc_18001D98A
0x18001d97e  test    al, al
0x18001d980  jnz     short loc_18001D98A
0x18001d982  btr     ebx, 0Ah
0x18001d986  jmp     short loc_18001D98A
0x18001d988  xor     al, al
0x18001d98a  test    r12b, bl
0x18001d98d  jz      short loc_18001D99A
0x18001d98f  test    al, al
0x18001d991  jz      short loc_18001D99A
0x18001d993  mov     esi, 1
0x18001d998  jmp     short loc_18001D99C
0x18001d99a  xor     esi, esi
0x18001d99c  mov     eax, [rdi]
0x18001d99e  or      esi, ebx
0x18001d9a0  mov     ebx, 180h
0x18001d9a5  cmp     dword ptr [rsp+58h+arg_0], 0
0x18001d9aa  mov     edx, eax
0x18001d9ac  mov     [rdi], eax
0x18001d9ae  jz      short loc_18001D9E8
0x18001d9b0  test    dl, 2
0x18001d9b3  jnz     short loc_18001D9E8
0x18001d9b5  mov     eax, esi
0x18001d9b7  xor     eax, edx
0x18001d9b9  and     eax, ebx
0x18001d9bb  xor     eax, edx
0x18001d9bd  mov     ecx, eax
0x18001d9bf  xor     ecx, esi
0x18001d9c1  and     ecx, r12d
0x18001d9c4  xor     ecx, eax
0x18001d9c6  mov     eax, ecx
0x18001d9c8  xor     eax, esi
0x18001d9ca  and     eax, 1
0x18001d9cd  xor     eax, ecx
0x18001d9cf  mov     r8d, eax
0x18001d9d2  xor     r8d, esi
0x18001d9d5  and     r8d, 800h
0x18001d9dc  xor     r8d, eax
0x18001d9df  or      r8d, 2
0x18001d9e3  mov     [rdi], r8d
0x18001d9e6  jmp     short loc_18001D9EB
0x18001d9e8  mov     r8d, edx
0x18001d9eb  mov     r9d, edx
0x18001d9ee  and     r9d, 4
0x18001d9f2  jnz     short loc_18001DA09
0x18001d9f4  mov     ecx, esi
0x18001d9f6  xor     ecx, r8d
0x18001d9f9  and     ecx, 400h
0x18001d9ff  xor     ecx, r8d
0x18001da02  or      ecx, 4
0x18001da05  mov     [rdi], ecx
0x18001da07  jmp     short loc_18001DA0C
0x18001da09  mov     ecx, r8d
0x18001da0c  mov     eax, edx
0x18001da0e  lock cmpxchg [r14], ecx
0x18001da13  jnz     short loc_18001D9A5
0x18001da15  test    r9d, r9d
0x18001da18  jnz     short loc_18001DA29
0x18001da1a  mov     r8d, ebp
0x18001da1d  lea     edx, [r9+3]
0x18001da21  mov     rcx, r14
0x18001da24  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001da29  test    byte ptr [rdi], 2
0x18001da2c  jnz     short loc_18001DA55
0x18001da2e  mov     eax, [rdi]
0x18001da30  xor     eax, esi
0x18001da32  and     eax, ebx
0x18001da34  xor     eax, [rdi]
0x18001da36  mov     ecx, eax
0x18001da38  xor     ecx, esi
0x18001da3a  and     ecx, r12d
0x18001da3d  xor     ecx, eax
0x18001da3f  mov     edx, ecx
0x18001da41  xor     edx, esi
0x18001da43  and     edx, 1
0x18001da46  xor     edx, ecx
0x18001da48  mov     eax, edx
0x18001da4a  xor     eax, esi
0x18001da4c  and     eax, 800h
0x18001da51  xor     eax, edx
0x18001da53  mov     [rdi], eax
0x18001da55  mov     rax, rdi
0x18001da58  add     rsp, 28h
0x18001da5c  pop     r14
0x18001da5e  pop     r12
0x18001da60  pop     rdi
0x18001da61  pop     rsi
0x18001da62  pop     rbp
0x18001da63  pop     rbx
0x18001da64  retn
```
