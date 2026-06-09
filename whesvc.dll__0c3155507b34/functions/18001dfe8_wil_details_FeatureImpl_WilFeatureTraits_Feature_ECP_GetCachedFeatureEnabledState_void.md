# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ECP>::GetCachedFeatureEnabledState(void)

- ea: `0x18001dfe8`
- end: `0x18001e1b0`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ECP@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `456`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024b48`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x18001dfe8`
- `0x180025404`
- `0x180029010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ECP>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ECP__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ECP__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(56401475, 3, &v20);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ECP__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_ECP__descriptor, 3, v4);
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
0x18001dfe8  mov     [rsp+arg_0], rcx
0x18001dfed  push    rbx
0x18001dfee  push    rbp
0x18001dfef  push    rsi
0x18001dff0  push    rdi
0x18001dff1  push    r12
0x18001dff3  push    r14
0x18001dff5  sub     rsp, 28h
0x18001dff9  mov     r14, cs:Feature_ECP__descriptor
0x18001e000  mov     rdi, rdx
0x18001e003  mov     qword ptr [rdx], 0
0x18001e00a  mov     eax, [r14]
0x18001e00d  mov     [rdx], eax
0x18001e00f  and     eax, 6
0x18001e012  cmp     al, 6
0x18001e014  jz      loc_18001E1A0
0x18001e01a  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001e01f  mov     ebp, eax
0x18001e021  mov     dword ptr [rsp+58h+arg_0], 0
0x18001e029  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001e030  test    rax, rax
0x18001e033  jz      short loc_18001E04D
0x18001e035  lea     r8, [rsp+58h+arg_0]
0x18001e03a  mov     edx, 3
0x18001e03f  mov     ecx, 35C9E43h
0x18001e044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e049  mov     edx, eax
0x18001e04b  jmp     short loc_18001E05B
0x18001e04d  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001e054  test    rax, rax
0x18001e057  jnz     short loc_18001E035
0x18001e059  xor     edx, edx
0x18001e05b  mov     r8d, edx
0x18001e05e  mov     eax, edx
0x18001e060  and     r8d, 0FFFFFF3Fh
0x18001e067  and     edx, 80h
0x18001e06d  mov     ecx, r8d
0x18001e070  mov     r12d, 40h ; '@'
0x18001e076  and     ecx, 3
0x18001e079  and     eax, r12d
0x18001e07c  shl     ecx, 2
0x18001e07f  or      ecx, eax
0x18001e081  xor     eax, eax
0x18001e083  shl     ecx, 2
0x18001e086  or      ecx, edx
0x18001e088  lea     ebx, ds:0[rcx*8]
0x18001e08f  test    r8d, r8d
0x18001e092  jz      short loc_18001E09C
0x18001e094  cmp     r8d, 2
0x18001e098  cmovz   eax, r12d
0x18001e09c  or      ebx, eax
0x18001e09e  mov     ecx, 0C00h
0x18001e0a3  mov     eax, ebx
0x18001e0a5  and     eax, ecx
0x18001e0a7  cmp     eax, ecx
0x18001e0a9  jnz     short loc_18001E0B0
0x18001e0ab  mov     sil, 1
0x18001e0ae  jmp     short loc_18001E0B8
0x18001e0b0  xor     sil, sil
0x18001e0b3  test    r12b, bl
0x18001e0b6  jz      short loc_18001E0D3
0x18001e0b8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x18001e0bf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x18001e0c4  test    sil, sil
0x18001e0c7  jz      short loc_18001E0D5
0x18001e0c9  test    al, al
0x18001e0cb  jnz     short loc_18001E0D5
0x18001e0cd  btr     ebx, 0Ah
0x18001e0d1  jmp     short loc_18001E0D5
0x18001e0d3  xor     al, al
0x18001e0d5  test    r12b, bl
0x18001e0d8  jz      short loc_18001E0E5
0x18001e0da  test    al, al
0x18001e0dc  jz      short loc_18001E0E5
0x18001e0de  mov     esi, 1
0x18001e0e3  jmp     short loc_18001E0E7
0x18001e0e5  xor     esi, esi
0x18001e0e7  mov     eax, [rdi]
0x18001e0e9  or      esi, ebx
0x18001e0eb  mov     ebx, 180h
0x18001e0f0  cmp     dword ptr [rsp+58h+arg_0], 0
0x18001e0f5  mov     edx, eax
0x18001e0f7  mov     [rdi], eax
0x18001e0f9  jz      short loc_18001E133
0x18001e0fb  test    dl, 2
0x18001e0fe  jnz     short loc_18001E133
0x18001e100  mov     eax, esi
0x18001e102  xor     eax, edx
0x18001e104  and     eax, ebx
0x18001e106  xor     eax, edx
0x18001e108  mov     ecx, eax
0x18001e10a  xor     ecx, esi
0x18001e10c  and     ecx, r12d
0x18001e10f  xor     ecx, eax
0x18001e111  mov     eax, ecx
0x18001e113  xor     eax, esi
0x18001e115  and     eax, 1
0x18001e118  xor     eax, ecx
0x18001e11a  mov     r8d, eax
0x18001e11d  xor     r8d, esi
0x18001e120  and     r8d, 800h
0x18001e127  xor     r8d, eax
0x18001e12a  or      r8d, 2
0x18001e12e  mov     [rdi], r8d
0x18001e131  jmp     short loc_18001E136
0x18001e133  mov     r8d, edx
0x18001e136  mov     r9d, edx
0x18001e139  and     r9d, 4
0x18001e13d  jnz     short loc_18001E154
0x18001e13f  mov     ecx, esi
0x18001e141  xor     ecx, r8d
0x18001e144  and     ecx, 400h
0x18001e14a  xor     ecx, r8d
0x18001e14d  or      ecx, 4
0x18001e150  mov     [rdi], ecx
0x18001e152  jmp     short loc_18001E157
0x18001e154  mov     ecx, r8d
0x18001e157  mov     eax, edx
0x18001e159  lock cmpxchg [r14], ecx
0x18001e15e  jnz     short loc_18001E0F0
0x18001e160  test    r9d, r9d
0x18001e163  jnz     short loc_18001E174
0x18001e165  mov     r8d, ebp
0x18001e168  lea     edx, [r9+3]
0x18001e16c  mov     rcx, r14
0x18001e16f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001e174  test    byte ptr [rdi], 2
0x18001e177  jnz     short loc_18001E1A0
0x18001e179  mov     eax, [rdi]
0x18001e17b  xor     eax, esi
0x18001e17d  and     eax, ebx
0x18001e17f  xor     eax, [rdi]
0x18001e181  mov     ecx, eax
0x18001e183  xor     ecx, esi
0x18001e185  and     ecx, r12d
0x18001e188  xor     ecx, eax
0x18001e18a  mov     edx, ecx
0x18001e18c  xor     edx, esi
0x18001e18e  and     edx, 1
0x18001e191  xor     edx, ecx
0x18001e193  mov     eax, edx
0x18001e195  xor     eax, esi
0x18001e197  and     eax, 800h
0x18001e19c  xor     eax, edx
0x18001e19e  mov     [rdi], eax
0x18001e1a0  mov     rax, rdi
0x18001e1a3  add     rsp, 28h
0x18001e1a7  pop     r14
0x18001e1a9  pop     r12
0x18001e1ab  pop     rdi
0x18001e1ac  pop     rsi
0x18001e1ad  pop     rbp
0x18001e1ae  pop     rbx
0x18001e1af  retn
```
