# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UTMSeverity>::GetCachedFeatureEnabledState(void)

- ea: `0x18001f7c8`
- end: `0x18001f995`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UTMSeverity@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800252c4`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x18001f7c8`
- `0x180025404`
- `0x180029010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UTMSeverity>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_UTMSeverity__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UTMSeverity__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(60698700, 3, &v20);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UTMSeverity__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_UTMSeverity__descriptor, 3, v4);
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
0x18001f7c8  mov     [rsp+arg_0], rcx
0x18001f7cd  push    rbx
0x18001f7ce  push    rbp
0x18001f7cf  push    rsi
0x18001f7d0  push    rdi
0x18001f7d1  push    r12
0x18001f7d3  push    r14
0x18001f7d5  sub     rsp, 28h
0x18001f7d9  mov     r14, cs:Feature_UTMSeverity__descriptor
0x18001f7e0  mov     rdi, rdx
0x18001f7e3  mov     qword ptr [rdx], 0
0x18001f7ea  mov     eax, [r14]
0x18001f7ed  mov     [rdx], eax
0x18001f7ef  and     eax, 6
0x18001f7f2  cmp     al, 6
0x18001f7f4  jz      loc_18001F985
0x18001f7fa  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001f7ff  mov     ebp, eax
0x18001f801  mov     dword ptr [rsp+58h+arg_0], 0
0x18001f809  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001f810  test    rax, rax
0x18001f813  jz      short loc_18001F82D
0x18001f815  lea     r8, [rsp+58h+arg_0]
0x18001f81a  mov     edx, 3
0x18001f81f  mov     ecx, 39E304Ch
0x18001f824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f829  mov     edx, eax
0x18001f82b  jmp     short loc_18001F83B
0x18001f82d  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001f834  test    rax, rax
0x18001f837  jnz     short loc_18001F815
0x18001f839  xor     edx, edx
0x18001f83b  mov     r8d, edx
0x18001f83e  mov     eax, edx
0x18001f840  and     r8d, 0FFFFFF3Fh
0x18001f847  and     edx, 80h
0x18001f84d  mov     ecx, r8d
0x18001f850  mov     r12d, 40h ; '@'
0x18001f856  and     ecx, 3
0x18001f859  and     eax, r12d
0x18001f85c  shl     ecx, 2
0x18001f85f  or      ecx, eax
0x18001f861  shl     ecx, 2
0x18001f864  or      ecx, edx
0x18001f866  lea     ebx, ds:0[rcx*8]
0x18001f86d  test    r8d, r8d
0x18001f870  jnz     short loc_18001F877
0x18001f872  mov     eax, r12d
0x18001f875  jmp     short loc_18001F881
0x18001f877  xor     eax, eax
0x18001f879  cmp     r8d, 2
0x18001f87d  cmovz   eax, r12d
0x18001f881  or      ebx, eax
0x18001f883  mov     ecx, 0C00h
0x18001f888  mov     eax, ebx
0x18001f88a  and     eax, ecx
0x18001f88c  cmp     eax, ecx
0x18001f88e  jnz     short loc_18001F895
0x18001f890  mov     sil, 1
0x18001f893  jmp     short loc_18001F89D
0x18001f895  xor     sil, sil
0x18001f898  test    r12b, bl
0x18001f89b  jz      short loc_18001F8B8
0x18001f89d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x18001f8a4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x18001f8a9  test    sil, sil
0x18001f8ac  jz      short loc_18001F8BA
0x18001f8ae  test    al, al
0x18001f8b0  jnz     short loc_18001F8BA
0x18001f8b2  btr     ebx, 0Ah
0x18001f8b6  jmp     short loc_18001F8BA
0x18001f8b8  xor     al, al
0x18001f8ba  test    r12b, bl
0x18001f8bd  jz      short loc_18001F8CA
0x18001f8bf  test    al, al
0x18001f8c1  jz      short loc_18001F8CA
0x18001f8c3  mov     esi, 1
0x18001f8c8  jmp     short loc_18001F8CC
0x18001f8ca  xor     esi, esi
0x18001f8cc  mov     eax, [rdi]
0x18001f8ce  or      esi, ebx
0x18001f8d0  mov     ebx, 180h
0x18001f8d5  cmp     dword ptr [rsp+58h+arg_0], 0
0x18001f8da  mov     edx, eax
0x18001f8dc  mov     [rdi], eax
0x18001f8de  jz      short loc_18001F918
0x18001f8e0  test    dl, 2
0x18001f8e3  jnz     short loc_18001F918
0x18001f8e5  mov     eax, esi
0x18001f8e7  xor     eax, edx
0x18001f8e9  and     eax, ebx
0x18001f8eb  xor     eax, edx
0x18001f8ed  mov     ecx, eax
0x18001f8ef  xor     ecx, esi
0x18001f8f1  and     ecx, r12d
0x18001f8f4  xor     ecx, eax
0x18001f8f6  mov     eax, ecx
0x18001f8f8  xor     eax, esi
0x18001f8fa  and     eax, 1
0x18001f8fd  xor     eax, ecx
0x18001f8ff  mov     r8d, eax
0x18001f902  xor     r8d, esi
0x18001f905  and     r8d, 800h
0x18001f90c  xor     r8d, eax
0x18001f90f  or      r8d, 2
0x18001f913  mov     [rdi], r8d
0x18001f916  jmp     short loc_18001F91B
0x18001f918  mov     r8d, edx
0x18001f91b  mov     r9d, edx
0x18001f91e  and     r9d, 4
0x18001f922  jnz     short loc_18001F939
0x18001f924  mov     ecx, esi
0x18001f926  xor     ecx, r8d
0x18001f929  and     ecx, 400h
0x18001f92f  xor     ecx, r8d
0x18001f932  or      ecx, 4
0x18001f935  mov     [rdi], ecx
0x18001f937  jmp     short loc_18001F93C
0x18001f939  mov     ecx, r8d
0x18001f93c  mov     eax, edx
0x18001f93e  lock cmpxchg [r14], ecx
0x18001f943  jnz     short loc_18001F8D5
0x18001f945  test    r9d, r9d
0x18001f948  jnz     short loc_18001F959
0x18001f94a  mov     r8d, ebp
0x18001f94d  lea     edx, [r9+3]
0x18001f951  mov     rcx, r14
0x18001f954  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001f959  test    byte ptr [rdi], 2
0x18001f95c  jnz     short loc_18001F985
0x18001f95e  mov     eax, [rdi]
0x18001f960  xor     eax, esi
0x18001f962  and     eax, ebx
0x18001f964  xor     eax, [rdi]
0x18001f966  mov     ecx, eax
0x18001f968  xor     ecx, esi
0x18001f96a  and     ecx, r12d
0x18001f96d  xor     ecx, eax
0x18001f96f  mov     edx, ecx
0x18001f971  xor     edx, esi
0x18001f973  and     edx, 1
0x18001f976  xor     edx, ecx
0x18001f978  mov     eax, edx
0x18001f97a  xor     eax, esi
0x18001f97c  and     eax, 800h
0x18001f981  xor     eax, edx
0x18001f983  mov     [rdi], eax
0x18001f985  mov     rax, rdi
0x18001f988  add     rsp, 28h
0x18001f98c  pop     r14
0x18001f98e  pop     r12
0x18001f990  pop     rdi
0x18001f991  pop     rsi
0x18001f992  pop     rbp
0x18001f993  pop     rbx
0x18001f994  retn
```
