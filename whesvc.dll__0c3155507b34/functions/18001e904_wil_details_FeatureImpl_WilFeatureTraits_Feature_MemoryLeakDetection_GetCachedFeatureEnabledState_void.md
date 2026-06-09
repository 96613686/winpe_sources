# wil::details::FeatureImpl<__WilFeatureTraits_Feature_MemoryLeakDetection>::GetCachedFeatureEnabledState(void)

- ea: `0x18001e904`
- end: `0x18001eacc`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MemoryLeakDetection@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `456`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024e68`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x18001e904`
- `0x180025404`
- `0x180029010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_MemoryLeakDetection>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_MemoryLeakDetection__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_MemoryLeakDetection__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(56429527, 3, &v20);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_MemoryLeakDetection__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_MemoryLeakDetection__descriptor, 3, v4);
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
0x18001e904  mov     [rsp+arg_0], rcx
0x18001e909  push    rbx
0x18001e90a  push    rbp
0x18001e90b  push    rsi
0x18001e90c  push    rdi
0x18001e90d  push    r12
0x18001e90f  push    r14
0x18001e911  sub     rsp, 28h
0x18001e915  mov     r14, cs:Feature_MemoryLeakDetection__descriptor
0x18001e91c  mov     rdi, rdx
0x18001e91f  mov     qword ptr [rdx], 0
0x18001e926  mov     eax, [r14]
0x18001e929  mov     [rdx], eax
0x18001e92b  and     eax, 6
0x18001e92e  cmp     al, 6
0x18001e930  jz      loc_18001EABC
0x18001e936  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001e93b  mov     ebp, eax
0x18001e93d  mov     dword ptr [rsp+58h+arg_0], 0
0x18001e945  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001e94c  test    rax, rax
0x18001e94f  jz      short loc_18001E969
0x18001e951  lea     r8, [rsp+58h+arg_0]
0x18001e956  mov     edx, 3
0x18001e95b  mov     ecx, 35D0BD7h
0x18001e960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e965  mov     edx, eax
0x18001e967  jmp     short loc_18001E977
0x18001e969  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001e970  test    rax, rax
0x18001e973  jnz     short loc_18001E951
0x18001e975  xor     edx, edx
0x18001e977  mov     r8d, edx
0x18001e97a  mov     eax, edx
0x18001e97c  and     r8d, 0FFFFFF3Fh
0x18001e983  and     edx, 80h
0x18001e989  mov     ecx, r8d
0x18001e98c  mov     r12d, 40h ; '@'
0x18001e992  and     ecx, 3
0x18001e995  and     eax, r12d
0x18001e998  shl     ecx, 2
0x18001e99b  or      ecx, eax
0x18001e99d  xor     eax, eax
0x18001e99f  shl     ecx, 2
0x18001e9a2  or      ecx, edx
0x18001e9a4  lea     ebx, ds:0[rcx*8]
0x18001e9ab  test    r8d, r8d
0x18001e9ae  jz      short loc_18001E9B8
0x18001e9b0  cmp     r8d, 2
0x18001e9b4  cmovz   eax, r12d
0x18001e9b8  or      ebx, eax
0x18001e9ba  mov     ecx, 0C00h
0x18001e9bf  mov     eax, ebx
0x18001e9c1  and     eax, ecx
0x18001e9c3  cmp     eax, ecx
0x18001e9c5  jnz     short loc_18001E9CC
0x18001e9c7  mov     sil, 1
0x18001e9ca  jmp     short loc_18001E9D4
0x18001e9cc  xor     sil, sil
0x18001e9cf  test    r12b, bl
0x18001e9d2  jz      short loc_18001E9EF
0x18001e9d4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x18001e9db  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x18001e9e0  test    sil, sil
0x18001e9e3  jz      short loc_18001E9F1
0x18001e9e5  test    al, al
0x18001e9e7  jnz     short loc_18001E9F1
0x18001e9e9  btr     ebx, 0Ah
0x18001e9ed  jmp     short loc_18001E9F1
0x18001e9ef  xor     al, al
0x18001e9f1  test    r12b, bl
0x18001e9f4  jz      short loc_18001EA01
0x18001e9f6  test    al, al
0x18001e9f8  jz      short loc_18001EA01
0x18001e9fa  mov     esi, 1
0x18001e9ff  jmp     short loc_18001EA03
0x18001ea01  xor     esi, esi
0x18001ea03  mov     eax, [rdi]
0x18001ea05  or      esi, ebx
0x18001ea07  mov     ebx, 180h
0x18001ea0c  cmp     dword ptr [rsp+58h+arg_0], 0
0x18001ea11  mov     edx, eax
0x18001ea13  mov     [rdi], eax
0x18001ea15  jz      short loc_18001EA4F
0x18001ea17  test    dl, 2
0x18001ea1a  jnz     short loc_18001EA4F
0x18001ea1c  mov     eax, esi
0x18001ea1e  xor     eax, edx
0x18001ea20  and     eax, ebx
0x18001ea22  xor     eax, edx
0x18001ea24  mov     ecx, eax
0x18001ea26  xor     ecx, esi
0x18001ea28  and     ecx, r12d
0x18001ea2b  xor     ecx, eax
0x18001ea2d  mov     eax, ecx
0x18001ea2f  xor     eax, esi
0x18001ea31  and     eax, 1
0x18001ea34  xor     eax, ecx
0x18001ea36  mov     r8d, eax
0x18001ea39  xor     r8d, esi
0x18001ea3c  and     r8d, 800h
0x18001ea43  xor     r8d, eax
0x18001ea46  or      r8d, 2
0x18001ea4a  mov     [rdi], r8d
0x18001ea4d  jmp     short loc_18001EA52
0x18001ea4f  mov     r8d, edx
0x18001ea52  mov     r9d, edx
0x18001ea55  and     r9d, 4
0x18001ea59  jnz     short loc_18001EA70
0x18001ea5b  mov     ecx, esi
0x18001ea5d  xor     ecx, r8d
0x18001ea60  and     ecx, 400h
0x18001ea66  xor     ecx, r8d
0x18001ea69  or      ecx, 4
0x18001ea6c  mov     [rdi], ecx
0x18001ea6e  jmp     short loc_18001EA73
0x18001ea70  mov     ecx, r8d
0x18001ea73  mov     eax, edx
0x18001ea75  lock cmpxchg [r14], ecx
0x18001ea7a  jnz     short loc_18001EA0C
0x18001ea7c  test    r9d, r9d
0x18001ea7f  jnz     short loc_18001EA90
0x18001ea81  mov     r8d, ebp
0x18001ea84  lea     edx, [r9+3]
0x18001ea88  mov     rcx, r14
0x18001ea8b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001ea90  test    byte ptr [rdi], 2
0x18001ea93  jnz     short loc_18001EABC
0x18001ea95  mov     eax, [rdi]
0x18001ea97  xor     eax, esi
0x18001ea99  and     eax, ebx
0x18001ea9b  xor     eax, [rdi]
0x18001ea9d  mov     ecx, eax
0x18001ea9f  xor     ecx, esi
0x18001eaa1  and     ecx, r12d
0x18001eaa4  xor     ecx, eax
0x18001eaa6  mov     edx, ecx
0x18001eaa8  xor     edx, esi
0x18001eaaa  and     edx, 1
0x18001eaad  xor     edx, ecx
0x18001eaaf  mov     eax, edx
0x18001eab1  xor     eax, esi
0x18001eab3  and     eax, 800h
0x18001eab8  xor     eax, edx
0x18001eaba  mov     [rdi], eax
0x18001eabc  mov     rax, rdi
0x18001eabf  add     rsp, 28h
0x18001eac3  pop     r14
0x18001eac5  pop     r12
0x18001eac7  pop     rdi
0x18001eac8  pop     rsi
0x18001eac9  pop     rbp
0x18001eaca  pop     rbx
0x18001eacb  retn
```
