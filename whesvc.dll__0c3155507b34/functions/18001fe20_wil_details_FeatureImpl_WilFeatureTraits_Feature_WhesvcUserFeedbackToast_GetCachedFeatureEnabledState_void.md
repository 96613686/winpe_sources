# wil::details::FeatureImpl<__WilFeatureTraits_Feature_WhesvcUserFeedbackToast>::GetCachedFeatureEnabledState(void)

- ea: `0x18001fe20`
- end: `0x18001ffe8`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WhesvcUserFeedbackToast@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `456`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025540`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x18001fe20`
- `0x180025404`
- `0x180029010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_WhesvcUserFeedbackToast>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_WhesvcUserFeedbackToast__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_WhesvcUserFeedbackToast__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(60824047, 3, &v20);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_WhesvcUserFeedbackToast__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_WhesvcUserFeedbackToast__descriptor, 3, v4);
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
0x18001fe20  mov     [rsp+arg_0], rcx
0x18001fe25  push    rbx
0x18001fe26  push    rbp
0x18001fe27  push    rsi
0x18001fe28  push    rdi
0x18001fe29  push    r12
0x18001fe2b  push    r14
0x18001fe2d  sub     rsp, 28h
0x18001fe31  mov     r14, cs:Feature_WhesvcUserFeedbackToast__descriptor
0x18001fe38  mov     rdi, rdx
0x18001fe3b  mov     qword ptr [rdx], 0
0x18001fe42  mov     eax, [r14]
0x18001fe45  mov     [rdx], eax
0x18001fe47  and     eax, 6
0x18001fe4a  cmp     al, 6
0x18001fe4c  jz      loc_18001FFD8
0x18001fe52  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001fe57  mov     ebp, eax
0x18001fe59  mov     dword ptr [rsp+58h+arg_0], 0
0x18001fe61  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001fe68  test    rax, rax
0x18001fe6b  jz      short loc_18001FE85
0x18001fe6d  lea     r8, [rsp+58h+arg_0]
0x18001fe72  mov     edx, 3
0x18001fe77  mov     ecx, 3A019EFh
0x18001fe7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe81  mov     edx, eax
0x18001fe83  jmp     short loc_18001FE93
0x18001fe85  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001fe8c  test    rax, rax
0x18001fe8f  jnz     short loc_18001FE6D
0x18001fe91  xor     edx, edx
0x18001fe93  mov     r8d, edx
0x18001fe96  mov     eax, edx
0x18001fe98  and     r8d, 0FFFFFF3Fh
0x18001fe9f  and     edx, 80h
0x18001fea5  mov     ecx, r8d
0x18001fea8  mov     r12d, 40h ; '@'
0x18001feae  and     ecx, 3
0x18001feb1  and     eax, r12d
0x18001feb4  shl     ecx, 2
0x18001feb7  or      ecx, eax
0x18001feb9  xor     eax, eax
0x18001febb  shl     ecx, 2
0x18001febe  or      ecx, edx
0x18001fec0  lea     ebx, ds:0[rcx*8]
0x18001fec7  test    r8d, r8d
0x18001feca  jz      short loc_18001FED4
0x18001fecc  cmp     r8d, 2
0x18001fed0  cmovz   eax, r12d
0x18001fed4  or      ebx, eax
0x18001fed6  mov     ecx, 0C00h
0x18001fedb  mov     eax, ebx
0x18001fedd  and     eax, ecx
0x18001fedf  cmp     eax, ecx
0x18001fee1  jnz     short loc_18001FEE8
0x18001fee3  mov     sil, 1
0x18001fee6  jmp     short loc_18001FEF0
0x18001fee8  xor     sil, sil
0x18001feeb  test    r12b, bl
0x18001feee  jz      short loc_18001FF0B
0x18001fef0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x18001fef7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x18001fefc  test    sil, sil
0x18001feff  jz      short loc_18001FF0D
0x18001ff01  test    al, al
0x18001ff03  jnz     short loc_18001FF0D
0x18001ff05  btr     ebx, 0Ah
0x18001ff09  jmp     short loc_18001FF0D
0x18001ff0b  xor     al, al
0x18001ff0d  test    r12b, bl
0x18001ff10  jz      short loc_18001FF1D
0x18001ff12  test    al, al
0x18001ff14  jz      short loc_18001FF1D
0x18001ff16  mov     esi, 1
0x18001ff1b  jmp     short loc_18001FF1F
0x18001ff1d  xor     esi, esi
0x18001ff1f  mov     eax, [rdi]
0x18001ff21  or      esi, ebx
0x18001ff23  mov     ebx, 180h
0x18001ff28  cmp     dword ptr [rsp+58h+arg_0], 0
0x18001ff2d  mov     edx, eax
0x18001ff2f  mov     [rdi], eax
0x18001ff31  jz      short loc_18001FF6B
0x18001ff33  test    dl, 2
0x18001ff36  jnz     short loc_18001FF6B
0x18001ff38  mov     eax, esi
0x18001ff3a  xor     eax, edx
0x18001ff3c  and     eax, ebx
0x18001ff3e  xor     eax, edx
0x18001ff40  mov     ecx, eax
0x18001ff42  xor     ecx, esi
0x18001ff44  and     ecx, r12d
0x18001ff47  xor     ecx, eax
0x18001ff49  mov     eax, ecx
0x18001ff4b  xor     eax, esi
0x18001ff4d  and     eax, 1
0x18001ff50  xor     eax, ecx
0x18001ff52  mov     r8d, eax
0x18001ff55  xor     r8d, esi
0x18001ff58  and     r8d, 800h
0x18001ff5f  xor     r8d, eax
0x18001ff62  or      r8d, 2
0x18001ff66  mov     [rdi], r8d
0x18001ff69  jmp     short loc_18001FF6E
0x18001ff6b  mov     r8d, edx
0x18001ff6e  mov     r9d, edx
0x18001ff71  and     r9d, 4
0x18001ff75  jnz     short loc_18001FF8C
0x18001ff77  mov     ecx, esi
0x18001ff79  xor     ecx, r8d
0x18001ff7c  and     ecx, 400h
0x18001ff82  xor     ecx, r8d
0x18001ff85  or      ecx, 4
0x18001ff88  mov     [rdi], ecx
0x18001ff8a  jmp     short loc_18001FF8F
0x18001ff8c  mov     ecx, r8d
0x18001ff8f  mov     eax, edx
0x18001ff91  lock cmpxchg [r14], ecx
0x18001ff96  jnz     short loc_18001FF28
0x18001ff98  test    r9d, r9d
0x18001ff9b  jnz     short loc_18001FFAC
0x18001ff9d  mov     r8d, ebp
0x18001ffa0  lea     edx, [r9+3]
0x18001ffa4  mov     rcx, r14
0x18001ffa7  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001ffac  test    byte ptr [rdi], 2
0x18001ffaf  jnz     short loc_18001FFD8
0x18001ffb1  mov     eax, [rdi]
0x18001ffb3  xor     eax, esi
0x18001ffb5  and     eax, ebx
0x18001ffb7  xor     eax, [rdi]
0x18001ffb9  mov     ecx, eax
0x18001ffbb  xor     ecx, esi
0x18001ffbd  and     ecx, r12d
0x18001ffc0  xor     ecx, eax
0x18001ffc2  mov     edx, ecx
0x18001ffc4  xor     edx, esi
0x18001ffc6  and     edx, 1
0x18001ffc9  xor     edx, ecx
0x18001ffcb  mov     eax, edx
0x18001ffcd  xor     eax, esi
0x18001ffcf  and     eax, 800h
0x18001ffd4  xor     eax, edx
0x18001ffd6  mov     [rdi], eax
0x18001ffd8  mov     rax, rdi
0x18001ffdb  add     rsp, 28h
0x18001ffdf  pop     r14
0x18001ffe1  pop     r12
0x18001ffe3  pop     rdi
0x18001ffe4  pop     rsi
0x18001ffe5  pop     rbp
0x18001ffe6  pop     rbx
0x18001ffe7  retn
```
