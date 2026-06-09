# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetCachedFeatureEnabledState(void)

- ea: `0x14000f780`
- end: `0x14000f937`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `439`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000f940`
- `0x14000faa4`

## callees

- `0x140009698`
- `0x14000b9b0`
- `0x14000f780`
- `0x140016010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 (__fastcall *v5)(__int64, __int64, wil::details **); // rax
  int v6; // edx
  int v7; // eax
  int v8; // ebx
  char v9; // al
  int v10; // eax
  int v11; // ebx
  signed __int32 v12; // eax
  bool v13; // zf
  signed __int32 v14; // edx
  int v15; // r8d
  int v16; // r9d
  signed __int32 v17; // ecx
  wil::details *v19; // [rsp+40h] [rbp+8h] BYREF

  v19 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Print_PlatformStabilizationFixes_2026_Wave1__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Print_PlatformStabilizationFixes_2026_Wave1__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v19) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(57741219, 3, &v19);
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
  }
  else
  {
    if ( (v8 & 0x40) != 0 )
      goto LABEL_15;
    v9 = 0;
  }
  if ( (v8 & 0x40) == 0 || !v9 )
  {
    v10 = 0;
    goto LABEL_16;
  }
LABEL_15:
  v10 = 1;
LABEL_16:
  v11 = v10 | v8;
  v12 = *(_DWORD *)a2;
  do
  {
    v13 = (_DWORD)v19 == 0;
    v14 = v12;
    *(_DWORD *)a2 = v12;
    if ( v13 || (v12 & 2) != 0 )
    {
      v15 = v12;
    }
    else
    {
      v15 = v12
          ^ ((unsigned __int16)v12
           ^ (unsigned __int16)v11)
          & 0x180
          ^ (v11
           ^ v12
           ^ ((unsigned __int16)v12
            ^ (unsigned __int16)v11)
           & 0x180)
          & 0x40
          ^ ((unsigned __int8)v11
           ^ (unsigned __int8)(v12 ^ (v12 ^ v11) & 0x80 ^ (v11 ^ v12 ^ (v12 ^ v11) & 0x80) & 0x40))
          & 1
          ^ ((unsigned __int16)v11
           ^ (unsigned __int16)(v12
                              ^ (v12
                               ^ v11)
                              & 0x180
                              ^ (v11
                               ^ v12
                               ^ (v12
                                ^ v11)
                               & 0x180)
                              & 0x40
                              ^ ((unsigned __int8)v11
                               ^ (unsigned __int8)(v12 ^ (v12 ^ v11) & 0x80 ^ (v11 ^ v12 ^ (v12 ^ v11) & 0x80) & 0x40))
                              & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v15;
    }
    v16 = v12 & 4;
    if ( (v12 & 4) != 0 )
    {
      v17 = v15;
    }
    else
    {
      v17 = v15 ^ ((unsigned __int16)v15 ^ (unsigned __int16)v11) & 0x400 | 4;
      *(_DWORD *)a2 = v17;
    }
    v12 = _InterlockedCompareExchange(
            (volatile signed __int32 *)Feature_Print_PlatformStabilizationFixes_2026_Wave1__descriptor,
            v17,
            v12);
  }
  while ( v14 != v12 );
  if ( !v16 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      (volatile signed __int32 *)Feature_Print_PlatformStabilizationFixes_2026_Wave1__descriptor,
      3u,
      v4);
  if ( (*(_BYTE *)a2 & 2) == 0 )
    *(_DWORD *)a2 ^= ((unsigned __int16)v11
                    ^ (unsigned __int16)*(_DWORD *)a2)
                   & 0x180
                   ^ (v11
                    ^ *(_DWORD *)a2
                    ^ ((unsigned __int16)v11
                     ^ (unsigned __int16)*(_DWORD *)a2)
                    & 0x180)
                   & 0x40
                   ^ ((unsigned __int8)v11
                    ^ *(_BYTE *)a2
                    ^ ((unsigned __int8)v11
                     ^ (unsigned __int8)*(_DWORD *)a2)
                    & 0x80
                    ^ ((unsigned __int8)v11
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v11
                      ^ (unsigned __int8)*(_DWORD *)a2)
                     & 0x80)
                    & 0x40)
                   & 1
                   ^ ((unsigned __int16)v11
                    ^ *(_WORD *)a2
                    ^ ((unsigned __int16)v11
                     ^ (unsigned __int16)*(_DWORD *)a2)
                    & 0x180
                    ^ ((unsigned __int16)v11
                     ^ *(_WORD *)a2
                     ^ ((unsigned __int16)v11
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180)
                    & 0x40
                    ^ ((unsigned __int8)v11
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v11
                      ^ (unsigned __int8)*(_DWORD *)a2)
                     & 0x80
                     ^ ((unsigned __int8)v11
                      ^ *(_BYTE *)a2
                      ^ ((unsigned __int8)v11
                       ^ (unsigned __int8)*(_DWORD *)a2)
                      & 0x80)
                     & 0x40)
                    & 1)
                   & 0x800;
  return a2;
}

```

## disassembly

```asm
0x14000f780  mov     [rsp+arg_8], rbx
0x14000f785  mov     [rsp+arg_10], rbp
0x14000f78a  mov     [rsp+arg_0], rcx
0x14000f78f  push    rsi
0x14000f790  push    rdi
0x14000f791  push    r12
0x14000f793  sub     rsp, 20h
0x14000f797  mov     rsi, cs:Feature_Print_PlatformStabilizationFixes_2026_Wave1__descriptor
0x14000f79e  mov     rdi, rdx
0x14000f7a1  mov     qword ptr [rdx], 0
0x14000f7a8  mov     eax, [rsi]
0x14000f7aa  mov     [rdx], eax
0x14000f7ac  and     eax, 6
0x14000f7af  cmp     al, 6
0x14000f7b1  jz      loc_14000F921
0x14000f7b7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000f7bc  mov     ebp, eax
0x14000f7be  mov     dword ptr [rsp+38h+arg_0], 0
0x14000f7c6  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x14000f7cd  test    rax, rax
0x14000f7d0  jz      short loc_14000F7EA
0x14000f7d2  lea     r8, [rsp+38h+arg_0]
0x14000f7d7  mov     edx, 3
0x14000f7dc  mov     ecx, 3710FA3h
0x14000f7e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f7e6  mov     edx, eax
0x14000f7e8  jmp     short loc_14000F7F8
0x14000f7ea  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x14000f7f1  test    rax, rax
0x14000f7f4  jnz     short loc_14000F7D2
0x14000f7f6  xor     edx, edx
0x14000f7f8  mov     r8d, edx
0x14000f7fb  mov     eax, edx
0x14000f7fd  and     r8d, 0FFFFFF3Fh
0x14000f804  and     edx, 80h
0x14000f80a  mov     ecx, r8d
0x14000f80d  mov     r12d, 40h ; '@'
0x14000f813  and     ecx, 3
0x14000f816  and     eax, r12d
0x14000f819  shl     ecx, 2
0x14000f81c  or      ecx, eax
0x14000f81e  xor     eax, eax
0x14000f820  shl     ecx, 2
0x14000f823  or      ecx, edx
0x14000f825  lea     ebx, ds:0[rcx*8]
0x14000f82c  test    r8d, r8d
0x14000f82f  jz      short loc_14000F839
0x14000f831  cmp     r8d, 2
0x14000f835  cmovz   eax, r12d
0x14000f839  or      ebx, eax
0x14000f83b  mov     edx, 0C00h
0x14000f840  mov     ecx, ebx
0x14000f842  mov     eax, ebx
0x14000f844  and     ecx, r12d
0x14000f847  and     eax, edx
0x14000f849  cmp     eax, edx
0x14000f84b  jnz     short loc_14000F851
0x14000f84d  mov     al, 1
0x14000f84f  jmp     short loc_14000F857
0x14000f851  test    ecx, ecx
0x14000f853  jnz     short loc_14000F863
0x14000f855  xor     al, al
0x14000f857  test    ecx, ecx
0x14000f859  jz      short loc_14000F85F
0x14000f85b  test    al, al
0x14000f85d  jnz     short loc_14000F863
0x14000f85f  xor     eax, eax
0x14000f861  jmp     short loc_14000F868
0x14000f863  mov     eax, 1
0x14000f868  or      ebx, eax
0x14000f86a  mov     eax, [rdi]
0x14000f86c  cmp     dword ptr [rsp+38h+arg_0], 0
0x14000f871  mov     edx, eax
0x14000f873  mov     [rdi], eax
0x14000f875  jz      short loc_14000F8B2
0x14000f877  test    dl, 2
0x14000f87a  jnz     short loc_14000F8B2
0x14000f87c  mov     eax, ebx
0x14000f87e  xor     eax, edx
0x14000f880  and     eax, 180h
0x14000f885  xor     eax, edx
0x14000f887  mov     ecx, eax
0x14000f889  xor     ecx, ebx
0x14000f88b  and     ecx, r12d
0x14000f88e  xor     ecx, eax
0x14000f890  mov     eax, ecx
0x14000f892  xor     eax, ebx
0x14000f894  and     eax, 1
0x14000f897  xor     eax, ecx
0x14000f899  mov     r8d, eax
0x14000f89c  xor     r8d, ebx
0x14000f89f  and     r8d, 800h
0x14000f8a6  xor     r8d, eax
0x14000f8a9  or      r8d, 2
0x14000f8ad  mov     [rdi], r8d
0x14000f8b0  jmp     short loc_14000F8B5
0x14000f8b2  mov     r8d, edx
0x14000f8b5  mov     r9d, edx
0x14000f8b8  and     r9d, 4
0x14000f8bc  jnz     short loc_14000F8D3
0x14000f8be  mov     ecx, ebx
0x14000f8c0  xor     ecx, r8d
0x14000f8c3  and     ecx, 400h
0x14000f8c9  xor     ecx, r8d
0x14000f8cc  or      ecx, 4
0x14000f8cf  mov     [rdi], ecx
0x14000f8d1  jmp     short loc_14000F8D6
0x14000f8d3  mov     ecx, r8d
0x14000f8d6  mov     eax, edx
0x14000f8d8  lock cmpxchg [rsi], ecx
0x14000f8dc  jnz     short loc_14000F86C
0x14000f8de  test    r9d, r9d
0x14000f8e1  jnz     short loc_14000F8F2
0x14000f8e3  mov     r8d, ebp
0x14000f8e6  lea     edx, [r9+3]
0x14000f8ea  mov     rcx, rsi
0x14000f8ed  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000f8f2  test    byte ptr [rdi], 2
0x14000f8f5  jnz     short loc_14000F921
0x14000f8f7  mov     eax, [rdi]
0x14000f8f9  xor     eax, ebx
0x14000f8fb  and     eax, 180h
0x14000f900  xor     eax, [rdi]
0x14000f902  mov     ecx, eax
0x14000f904  xor     ecx, ebx
0x14000f906  and     ecx, r12d
0x14000f909  xor     ecx, eax
0x14000f90b  mov     edx, ecx
0x14000f90d  xor     edx, ebx
0x14000f90f  and     edx, 1
0x14000f912  xor     edx, ecx
0x14000f914  mov     eax, edx
0x14000f916  xor     eax, ebx
0x14000f918  and     eax, 800h
0x14000f91d  xor     eax, edx
0x14000f91f  mov     [rdi], eax
0x14000f921  mov     rbx, [rsp+38h+arg_8]
0x14000f926  mov     rax, rdi
0x14000f929  mov     rbp, [rsp+38h+arg_10]
0x14000f92e  add     rsp, 20h
0x14000f932  pop     r12
0x14000f934  pop     rdi
0x14000f935  pop     rsi
0x14000f936  retn
```
