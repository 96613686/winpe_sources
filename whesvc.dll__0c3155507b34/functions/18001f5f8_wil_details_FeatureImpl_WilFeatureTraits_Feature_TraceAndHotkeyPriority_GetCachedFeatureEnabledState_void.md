# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TraceAndHotkeyPriority>::GetCachedFeatureEnabledState(void)

- ea: `0x18001f5f8`
- end: `0x18001f7c0`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TraceAndHotkeyPriority@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `456`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025224`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x18001f5f8`
- `0x180025404`
- `0x180029010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TraceAndHotkeyPriority>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TraceAndHotkeyPriority__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TraceAndHotkeyPriority__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(61299637, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl'::`2'::impl);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TraceAndHotkeyPriority__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_TraceAndHotkeyPriority__descriptor, 3, v4);
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
0x18001f5f8  mov     [rsp+arg_0], rcx
0x18001f5fd  push    rbx
0x18001f5fe  push    rbp
0x18001f5ff  push    rsi
0x18001f600  push    rdi
0x18001f601  push    r12
0x18001f603  push    r14
0x18001f605  sub     rsp, 28h
0x18001f609  mov     r14, cs:Feature_TraceAndHotkeyPriority__descriptor
0x18001f610  mov     rdi, rdx
0x18001f613  mov     qword ptr [rdx], 0
0x18001f61a  mov     eax, [r14]
0x18001f61d  mov     [rdx], eax
0x18001f61f  and     eax, 6
0x18001f622  cmp     al, 6
0x18001f624  jz      loc_18001F7B0
0x18001f62a  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001f62f  mov     ebp, eax
0x18001f631  mov     dword ptr [rsp+58h+arg_0], 0
0x18001f639  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001f640  test    rax, rax
0x18001f643  jz      short loc_18001F65D
0x18001f645  lea     r8, [rsp+58h+arg_0]
0x18001f64a  mov     edx, 3
0x18001f64f  mov     ecx, 3A75BB5h
0x18001f654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f659  mov     edx, eax
0x18001f65b  jmp     short loc_18001F66B
0x18001f65d  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001f664  test    rax, rax
0x18001f667  jnz     short loc_18001F645
0x18001f669  xor     edx, edx
0x18001f66b  mov     r8d, edx
0x18001f66e  mov     eax, edx
0x18001f670  and     r8d, 0FFFFFF3Fh
0x18001f677  and     edx, 80h
0x18001f67d  mov     ecx, r8d
0x18001f680  mov     r12d, 40h ; '@'
0x18001f686  and     ecx, 3
0x18001f689  and     eax, r12d
0x18001f68c  shl     ecx, 2
0x18001f68f  or      ecx, eax
0x18001f691  xor     eax, eax
0x18001f693  shl     ecx, 2
0x18001f696  or      ecx, edx
0x18001f698  lea     ebx, ds:0[rcx*8]
0x18001f69f  test    r8d, r8d
0x18001f6a2  jz      short loc_18001F6AC
0x18001f6a4  cmp     r8d, 2
0x18001f6a8  cmovz   eax, r12d
0x18001f6ac  or      ebx, eax
0x18001f6ae  mov     ecx, 0C00h
0x18001f6b3  mov     eax, ebx
0x18001f6b5  and     eax, ecx
0x18001f6b7  cmp     eax, ecx
0x18001f6b9  jnz     short loc_18001F6C0
0x18001f6bb  mov     sil, 1
0x18001f6be  jmp     short loc_18001F6C8
0x18001f6c0  xor     sil, sil
0x18001f6c3  test    r12b, bl
0x18001f6c6  jz      short loc_18001F6E3
0x18001f6c8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x18001f6cf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x18001f6d4  test    sil, sil
0x18001f6d7  jz      short loc_18001F6E5
0x18001f6d9  test    al, al
0x18001f6db  jnz     short loc_18001F6E5
0x18001f6dd  btr     ebx, 0Ah
0x18001f6e1  jmp     short loc_18001F6E5
0x18001f6e3  xor     al, al
0x18001f6e5  test    r12b, bl
0x18001f6e8  jz      short loc_18001F6F5
0x18001f6ea  test    al, al
0x18001f6ec  jz      short loc_18001F6F5
0x18001f6ee  mov     esi, 1
0x18001f6f3  jmp     short loc_18001F6F7
0x18001f6f5  xor     esi, esi
0x18001f6f7  mov     eax, [rdi]
0x18001f6f9  or      esi, ebx
0x18001f6fb  mov     ebx, 180h
0x18001f700  cmp     dword ptr [rsp+58h+arg_0], 0
0x18001f705  mov     edx, eax
0x18001f707  mov     [rdi], eax
0x18001f709  jz      short loc_18001F743
0x18001f70b  test    dl, 2
0x18001f70e  jnz     short loc_18001F743
0x18001f710  mov     eax, esi
0x18001f712  xor     eax, edx
0x18001f714  and     eax, ebx
0x18001f716  xor     eax, edx
0x18001f718  mov     ecx, eax
0x18001f71a  xor     ecx, esi
0x18001f71c  and     ecx, r12d
0x18001f71f  xor     ecx, eax
0x18001f721  mov     eax, ecx
0x18001f723  xor     eax, esi
0x18001f725  and     eax, 1
0x18001f728  xor     eax, ecx
0x18001f72a  mov     r8d, eax
0x18001f72d  xor     r8d, esi
0x18001f730  and     r8d, 800h
0x18001f737  xor     r8d, eax
0x18001f73a  or      r8d, 2
0x18001f73e  mov     [rdi], r8d
0x18001f741  jmp     short loc_18001F746
0x18001f743  mov     r8d, edx
0x18001f746  mov     r9d, edx
0x18001f749  and     r9d, 4
0x18001f74d  jnz     short loc_18001F764
0x18001f74f  mov     ecx, esi
0x18001f751  xor     ecx, r8d
0x18001f754  and     ecx, 400h
0x18001f75a  xor     ecx, r8d
0x18001f75d  or      ecx, 4
0x18001f760  mov     [rdi], ecx
0x18001f762  jmp     short loc_18001F767
0x18001f764  mov     ecx, r8d
0x18001f767  mov     eax, edx
0x18001f769  lock cmpxchg [r14], ecx
0x18001f76e  jnz     short loc_18001F700
0x18001f770  test    r9d, r9d
0x18001f773  jnz     short loc_18001F784
0x18001f775  mov     r8d, ebp
0x18001f778  lea     edx, [r9+3]
0x18001f77c  mov     rcx, r14
0x18001f77f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001f784  test    byte ptr [rdi], 2
0x18001f787  jnz     short loc_18001F7B0
0x18001f789  mov     eax, [rdi]
0x18001f78b  xor     eax, esi
0x18001f78d  and     eax, ebx
0x18001f78f  xor     eax, [rdi]
0x18001f791  mov     ecx, eax
0x18001f793  xor     ecx, esi
0x18001f795  and     ecx, r12d
0x18001f798  xor     ecx, eax
0x18001f79a  mov     edx, ecx
0x18001f79c  xor     edx, esi
0x18001f79e  and     edx, 1
0x18001f7a1  xor     edx, ecx
0x18001f7a3  mov     eax, edx
0x18001f7a5  xor     eax, esi
0x18001f7a7  and     eax, 800h
0x18001f7ac  xor     eax, edx
0x18001f7ae  mov     [rdi], eax
0x18001f7b0  mov     rax, rdi
0x18001f7b3  add     rsp, 28h
0x18001f7b7  pop     r14
0x18001f7b9  pop     r12
0x18001f7bb  pop     rdi
0x18001f7bc  pop     rsi
0x18001f7bd  pop     rbp
0x18001f7be  pop     rbx
0x18001f7bf  retn
```
