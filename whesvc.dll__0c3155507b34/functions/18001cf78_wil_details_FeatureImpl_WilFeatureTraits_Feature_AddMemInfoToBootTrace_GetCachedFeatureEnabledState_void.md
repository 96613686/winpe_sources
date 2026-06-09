# wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::GetCachedFeatureEnabledState(void)

- ea: `0x18001cf78`
- end: `0x18001d140`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_AddMemInfoToBootTrace@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `456`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800245cc`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x18001cf78`
- `0x180025404`
- `0x180029010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_AddMemInfoToBootTrace__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_AddMemInfoToBootTrace__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(57608148, 3, &v20);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_AddMemInfoToBootTrace__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_AddMemInfoToBootTrace__descriptor, 3, v4);
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
0x18001cf78  mov     [rsp+arg_0], rcx
0x18001cf7d  push    rbx
0x18001cf7e  push    rbp
0x18001cf7f  push    rsi
0x18001cf80  push    rdi
0x18001cf81  push    r12
0x18001cf83  push    r14
0x18001cf85  sub     rsp, 28h
0x18001cf89  mov     r14, cs:Feature_AddMemInfoToBootTrace__descriptor
0x18001cf90  mov     rdi, rdx
0x18001cf93  mov     qword ptr [rdx], 0
0x18001cf9a  mov     eax, [r14]
0x18001cf9d  mov     [rdx], eax
0x18001cf9f  and     eax, 6
0x18001cfa2  cmp     al, 6
0x18001cfa4  jz      loc_18001D130
0x18001cfaa  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001cfaf  mov     ebp, eax
0x18001cfb1  mov     dword ptr [rsp+58h+arg_0], 0
0x18001cfb9  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001cfc0  test    rax, rax
0x18001cfc3  jz      short loc_18001CFDD
0x18001cfc5  lea     r8, [rsp+58h+arg_0]
0x18001cfca  mov     edx, 3
0x18001cfcf  mov     ecx, 36F07D4h
0x18001cfd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cfd9  mov     edx, eax
0x18001cfdb  jmp     short loc_18001CFEB
0x18001cfdd  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001cfe4  test    rax, rax
0x18001cfe7  jnz     short loc_18001CFC5
0x18001cfe9  xor     edx, edx
0x18001cfeb  mov     r8d, edx
0x18001cfee  mov     eax, edx
0x18001cff0  and     r8d, 0FFFFFF3Fh
0x18001cff7  and     edx, 80h
0x18001cffd  mov     ecx, r8d
0x18001d000  mov     r12d, 40h ; '@'
0x18001d006  and     ecx, 3
0x18001d009  and     eax, r12d
0x18001d00c  shl     ecx, 2
0x18001d00f  or      ecx, eax
0x18001d011  xor     eax, eax
0x18001d013  shl     ecx, 2
0x18001d016  or      ecx, edx
0x18001d018  lea     ebx, ds:0[rcx*8]
0x18001d01f  test    r8d, r8d
0x18001d022  jz      short loc_18001D02C
0x18001d024  cmp     r8d, 2
0x18001d028  cmovz   eax, r12d
0x18001d02c  or      ebx, eax
0x18001d02e  mov     ecx, 0C00h
0x18001d033  mov     eax, ebx
0x18001d035  and     eax, ecx
0x18001d037  cmp     eax, ecx
0x18001d039  jnz     short loc_18001D040
0x18001d03b  mov     sil, 1
0x18001d03e  jmp     short loc_18001D048
0x18001d040  xor     sil, sil
0x18001d043  test    r12b, bl
0x18001d046  jz      short loc_18001D063
0x18001d048  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x18001d04f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x18001d054  test    sil, sil
0x18001d057  jz      short loc_18001D065
0x18001d059  test    al, al
0x18001d05b  jnz     short loc_18001D065
0x18001d05d  btr     ebx, 0Ah
0x18001d061  jmp     short loc_18001D065
0x18001d063  xor     al, al
0x18001d065  test    r12b, bl
0x18001d068  jz      short loc_18001D075
0x18001d06a  test    al, al
0x18001d06c  jz      short loc_18001D075
0x18001d06e  mov     esi, 1
0x18001d073  jmp     short loc_18001D077
0x18001d075  xor     esi, esi
0x18001d077  mov     eax, [rdi]
0x18001d079  or      esi, ebx
0x18001d07b  mov     ebx, 180h
0x18001d080  cmp     dword ptr [rsp+58h+arg_0], 0
0x18001d085  mov     edx, eax
0x18001d087  mov     [rdi], eax
0x18001d089  jz      short loc_18001D0C3
0x18001d08b  test    dl, 2
0x18001d08e  jnz     short loc_18001D0C3
0x18001d090  mov     eax, esi
0x18001d092  xor     eax, edx
0x18001d094  and     eax, ebx
0x18001d096  xor     eax, edx
0x18001d098  mov     ecx, eax
0x18001d09a  xor     ecx, esi
0x18001d09c  and     ecx, r12d
0x18001d09f  xor     ecx, eax
0x18001d0a1  mov     eax, ecx
0x18001d0a3  xor     eax, esi
0x18001d0a5  and     eax, 1
0x18001d0a8  xor     eax, ecx
0x18001d0aa  mov     r8d, eax
0x18001d0ad  xor     r8d, esi
0x18001d0b0  and     r8d, 800h
0x18001d0b7  xor     r8d, eax
0x18001d0ba  or      r8d, 2
0x18001d0be  mov     [rdi], r8d
0x18001d0c1  jmp     short loc_18001D0C6
0x18001d0c3  mov     r8d, edx
0x18001d0c6  mov     r9d, edx
0x18001d0c9  and     r9d, 4
0x18001d0cd  jnz     short loc_18001D0E4
0x18001d0cf  mov     ecx, esi
0x18001d0d1  xor     ecx, r8d
0x18001d0d4  and     ecx, 400h
0x18001d0da  xor     ecx, r8d
0x18001d0dd  or      ecx, 4
0x18001d0e0  mov     [rdi], ecx
0x18001d0e2  jmp     short loc_18001D0E7
0x18001d0e4  mov     ecx, r8d
0x18001d0e7  mov     eax, edx
0x18001d0e9  lock cmpxchg [r14], ecx
0x18001d0ee  jnz     short loc_18001D080
0x18001d0f0  test    r9d, r9d
0x18001d0f3  jnz     short loc_18001D104
0x18001d0f5  mov     r8d, ebp
0x18001d0f8  lea     edx, [r9+3]
0x18001d0fc  mov     rcx, r14
0x18001d0ff  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001d104  test    byte ptr [rdi], 2
0x18001d107  jnz     short loc_18001D130
0x18001d109  mov     eax, [rdi]
0x18001d10b  xor     eax, esi
0x18001d10d  and     eax, ebx
0x18001d10f  xor     eax, [rdi]
0x18001d111  mov     ecx, eax
0x18001d113  xor     ecx, esi
0x18001d115  and     ecx, r12d
0x18001d118  xor     ecx, eax
0x18001d11a  mov     edx, ecx
0x18001d11c  xor     edx, esi
0x18001d11e  and     edx, 1
0x18001d121  xor     edx, ecx
0x18001d123  mov     eax, edx
0x18001d125  xor     eax, esi
0x18001d127  and     eax, 800h
0x18001d12c  xor     eax, edx
0x18001d12e  mov     [rdi], eax
0x18001d130  mov     rax, rdi
0x18001d133  add     rsp, 28h
0x18001d137  pop     r14
0x18001d139  pop     r12
0x18001d13b  pop     rdi
0x18001d13c  pop     rsi
0x18001d13d  pop     rbp
0x18001d13e  pop     rbx
0x18001d13f  retn
```
