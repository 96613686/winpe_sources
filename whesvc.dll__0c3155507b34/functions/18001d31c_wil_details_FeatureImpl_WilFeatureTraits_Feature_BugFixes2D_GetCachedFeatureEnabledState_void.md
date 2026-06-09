# wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes2D>::GetCachedFeatureEnabledState(void)

- ea: `0x18001d31c`
- end: `0x18001d4e9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes2D@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023660`
- `0x180024708`
- `0x180024748`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x1800174bc`
- `0x18001d31c`
- `0x180029010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes2D>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_BugFixes2D__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_BugFixes2D__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(60295199, 3, &v20);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_BugFixes2D__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_BugFixes2D__descriptor, 3, v4);
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
0x18001d31c  mov     [rsp+arg_0], rcx
0x18001d321  push    rbx
0x18001d322  push    rbp
0x18001d323  push    rsi
0x18001d324  push    rdi
0x18001d325  push    r12
0x18001d327  push    r14
0x18001d329  sub     rsp, 28h
0x18001d32d  mov     r14, cs:Feature_BugFixes2D__descriptor
0x18001d334  mov     rdi, rdx
0x18001d337  mov     qword ptr [rdx], 0
0x18001d33e  mov     eax, [r14]
0x18001d341  mov     [rdx], eax
0x18001d343  and     eax, 6
0x18001d346  cmp     al, 6
0x18001d348  jz      loc_18001D4D9
0x18001d34e  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001d353  mov     ebp, eax
0x18001d355  mov     dword ptr [rsp+58h+arg_0], 0
0x18001d35d  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001d364  test    rax, rax
0x18001d367  jz      short loc_18001D381
0x18001d369  lea     r8, [rsp+58h+arg_0]
0x18001d36e  mov     edx, 3
0x18001d373  mov     ecx, 398081Fh
0x18001d378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d37d  mov     edx, eax
0x18001d37f  jmp     short loc_18001D38F
0x18001d381  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001d388  test    rax, rax
0x18001d38b  jnz     short loc_18001D369
0x18001d38d  xor     edx, edx
0x18001d38f  mov     r8d, edx
0x18001d392  mov     eax, edx
0x18001d394  and     r8d, 0FFFFFF3Fh
0x18001d39b  and     edx, 80h
0x18001d3a1  mov     ecx, r8d
0x18001d3a4  mov     r12d, 40h ; '@'
0x18001d3aa  and     ecx, 3
0x18001d3ad  and     eax, r12d
0x18001d3b0  shl     ecx, 2
0x18001d3b3  or      ecx, eax
0x18001d3b5  shl     ecx, 2
0x18001d3b8  or      ecx, edx
0x18001d3ba  lea     ebx, ds:0[rcx*8]
0x18001d3c1  test    r8d, r8d
0x18001d3c4  jnz     short loc_18001D3CB
0x18001d3c6  mov     eax, r12d
0x18001d3c9  jmp     short loc_18001D3D5
0x18001d3cb  xor     eax, eax
0x18001d3cd  cmp     r8d, 2
0x18001d3d1  cmovz   eax, r12d
0x18001d3d5  or      ebx, eax
0x18001d3d7  mov     ecx, 0C00h
0x18001d3dc  mov     eax, ebx
0x18001d3de  and     eax, ecx
0x18001d3e0  cmp     eax, ecx
0x18001d3e2  jnz     short loc_18001D3E9
0x18001d3e4  mov     sil, 1
0x18001d3e7  jmp     short loc_18001D3F1
0x18001d3e9  xor     sil, sil
0x18001d3ec  test    r12b, bl
0x18001d3ef  jz      short loc_18001D40C
0x18001d3f1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ten2Loc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc> `wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl(void)'::`2'::impl
0x18001d3f8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(wil::ReportingKind)
0x18001d3fd  test    sil, sil
0x18001d400  jz      short loc_18001D40E
0x18001d402  test    al, al
0x18001d404  jnz     short loc_18001D40E
0x18001d406  btr     ebx, 0Ah
0x18001d40a  jmp     short loc_18001D40E
0x18001d40c  xor     al, al
0x18001d40e  test    r12b, bl
0x18001d411  jz      short loc_18001D41E
0x18001d413  test    al, al
0x18001d415  jz      short loc_18001D41E
0x18001d417  mov     esi, 1
0x18001d41c  jmp     short loc_18001D420
0x18001d41e  xor     esi, esi
0x18001d420  mov     eax, [rdi]
0x18001d422  or      esi, ebx
0x18001d424  mov     ebx, 180h
0x18001d429  cmp     dword ptr [rsp+58h+arg_0], 0
0x18001d42e  mov     edx, eax
0x18001d430  mov     [rdi], eax
0x18001d432  jz      short loc_18001D46C
0x18001d434  test    dl, 2
0x18001d437  jnz     short loc_18001D46C
0x18001d439  mov     eax, esi
0x18001d43b  xor     eax, edx
0x18001d43d  and     eax, ebx
0x18001d43f  xor     eax, edx
0x18001d441  mov     ecx, eax
0x18001d443  xor     ecx, esi
0x18001d445  and     ecx, r12d
0x18001d448  xor     ecx, eax
0x18001d44a  mov     eax, ecx
0x18001d44c  xor     eax, esi
0x18001d44e  and     eax, 1
0x18001d451  xor     eax, ecx
0x18001d453  mov     r8d, eax
0x18001d456  xor     r8d, esi
0x18001d459  and     r8d, 800h
0x18001d460  xor     r8d, eax
0x18001d463  or      r8d, 2
0x18001d467  mov     [rdi], r8d
0x18001d46a  jmp     short loc_18001D46F
0x18001d46c  mov     r8d, edx
0x18001d46f  mov     r9d, edx
0x18001d472  and     r9d, 4
0x18001d476  jnz     short loc_18001D48D
0x18001d478  mov     ecx, esi
0x18001d47a  xor     ecx, r8d
0x18001d47d  and     ecx, 400h
0x18001d483  xor     ecx, r8d
0x18001d486  or      ecx, 4
0x18001d489  mov     [rdi], ecx
0x18001d48b  jmp     short loc_18001D490
0x18001d48d  mov     ecx, r8d
0x18001d490  mov     eax, edx
0x18001d492  lock cmpxchg [r14], ecx
0x18001d497  jnz     short loc_18001D429
0x18001d499  test    r9d, r9d
0x18001d49c  jnz     short loc_18001D4AD
0x18001d49e  mov     r8d, ebp
0x18001d4a1  lea     edx, [r9+3]
0x18001d4a5  mov     rcx, r14
0x18001d4a8  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001d4ad  test    byte ptr [rdi], 2
0x18001d4b0  jnz     short loc_18001D4D9
0x18001d4b2  mov     eax, [rdi]
0x18001d4b4  xor     eax, esi
0x18001d4b6  and     eax, ebx
0x18001d4b8  xor     eax, [rdi]
0x18001d4ba  mov     ecx, eax
0x18001d4bc  xor     ecx, esi
0x18001d4be  and     ecx, r12d
0x18001d4c1  xor     ecx, eax
0x18001d4c3  mov     edx, ecx
0x18001d4c5  xor     edx, esi
0x18001d4c7  and     edx, 1
0x18001d4ca  xor     edx, ecx
0x18001d4cc  mov     eax, edx
0x18001d4ce  xor     eax, esi
0x18001d4d0  and     eax, 800h
0x18001d4d5  xor     eax, edx
0x18001d4d7  mov     [rdi], eax
0x18001d4d9  mov     rax, rdi
0x18001d4dc  add     rsp, 28h
0x18001d4e0  pop     r14
0x18001d4e2  pop     r12
0x18001d4e4  pop     rdi
0x18001d4e5  pop     rsi
0x18001d4e6  pop     rbp
0x18001d4e7  pop     rbx
0x18001d4e8  retn
```
