# wil::details::FeatureImpl<__WilFeatureTraits_Feature_4055748921>::GetCachedFeatureEnabledState(void)

- ea: `0x180008e78`
- end: `0x180009011`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_4055748921@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `409`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c83c`
- `0x18000ebe4`

## callees

- `0x180008724`
- `0x180008e78`
- `0x18000da58`
- `0x18001d010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_4055748921>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v5; // eax
  unsigned int v6; // ebp
  __int64 (__fastcall *v7)(__int64, __int64, int *); // rax
  int v8; // edx
  int v9; // ebx
  int v10; // ebx
  int v11; // eax
  char v12; // cl
  int v13; // eax
  signed __int32 v14; // edx
  int v15; // ebx
  bool v16; // zf
  signed __int32 v17; // ecx
  signed __int32 v18; // eax
  int v19; // eax
  int v21; // [rsp+40h] [rbp+8h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)a1;
  *(_DWORD *)a2 = *(_DWORD *)a1;
  if ( (v3 & 6) == 6 )
    return a2;
  v5 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  v21 = 0;
  v6 = v5;
  v7 = (__int64 (__fastcall *)(__int64, __int64, int *))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v7 = (__int64 (__fastcall *)(__int64, __int64, int *))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v8 = v7(52965666, 3, &v21);
  }
  else
  {
    v8 = 0;
  }
  v9 = 8 * (v8 & 0x80 | (4 * (v8 & 0x40 | (4 * (v8 & 3)))));
  if ( (v8 & 0xFFFFFF3F) != 0 )
  {
    v11 = 0;
    if ( (v8 & 0xFFFFFF3F) == 2 )
      v11 = 64;
    v10 = v11 | v9;
  }
  else
  {
    v10 = v9 | 0x40;
  }
  v12 = 0;
  if ( (v10 & 0xC00) == 0xC00 )
  {
    v12 = 1;
  }
  else if ( (v10 & 0x40) != 0 )
  {
    goto LABEL_17;
  }
  if ( (v10 & 0x40) == 0 || !v12 )
  {
    v13 = 0;
    goto LABEL_18;
  }
LABEL_17:
  v13 = 1;
LABEL_18:
  v14 = *(_DWORD *)a2;
  v15 = v13 | v10;
  while ( 1 )
  {
    v16 = v21 == 0;
    v17 = v14;
    *(_DWORD *)a2 = v14;
    if ( !v16 && (v14 & 2) == 0 )
    {
      v17 = v14
          ^ ((unsigned __int16)v14
           ^ (unsigned __int16)v15)
          & 0x180
          ^ (v15
           ^ v14
           ^ ((unsigned __int16)v14
            ^ (unsigned __int16)v15)
           & 0x180)
          & 0x40
          ^ ((unsigned __int8)v15
           ^ (unsigned __int8)(v14 ^ (v14 ^ v15) & 0x80 ^ (v15 ^ v14 ^ (v14 ^ v15) & 0x80) & 0x40))
          & 1
          ^ ((unsigned __int16)v15
           ^ (unsigned __int16)(v14
                              ^ (v14
                               ^ v15)
                              & 0x180
                              ^ (v15
                               ^ v14
                               ^ (v14
                                ^ v15)
                               & 0x180)
                              & 0x40
                              ^ ((unsigned __int8)v15
                               ^ (unsigned __int8)(v14 ^ (v14 ^ v15) & 0x80 ^ (v15 ^ v14 ^ (v14 ^ v15) & 0x80) & 0x40))
                              & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v17;
    }
    if ( (v14 & 4) == 0 )
    {
      v17 = ((unsigned __int16)v17 ^ (unsigned __int16)v15) & 0x400 ^ v17 | 4;
      *(_DWORD *)a2 = v17;
    }
    v18 = _InterlockedCompareExchange((volatile signed __int32 *)a1, v17, v14);
    if ( v14 == v18 )
      break;
    v14 = v18;
  }
  if ( (v14 & 4) == 0 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(a1, 3, v6);
  if ( (*(_BYTE *)a2 & 2) == 0 )
  {
    v19 = *(_DWORD *)a2 ^ (*(_DWORD *)a2 ^ v15) & 0x180;
    *(_DWORD *)a2 = v19
                  ^ (v19
                   ^ v15)
                  & 0x40
                  ^ ((unsigned __int8)v15
                   ^ (unsigned __int8)(v19 ^ (v19 ^ v15) & 0x40))
                  & 1
                  ^ ((unsigned __int16)v15
                   ^ (unsigned __int16)(v19
                                      ^ (v19
                                       ^ v15)
                                      & 0x40
                                      ^ ((unsigned __int8)v15
                                       ^ (unsigned __int8)(v19 ^ (v19 ^ v15) & 0x40))
                                      & 1))
                  & 0x800;
  }
  return a2;
}

```

## disassembly

```asm
0x180008e78  mov     [rsp+arg_8], rbx
0x180008e7d  mov     [rsp+arg_10], rbp
0x180008e82  push    rsi
0x180008e83  push    rdi
0x180008e84  push    r15
0x180008e86  sub     rsp, 20h
0x180008e8a  and     qword ptr [rdx], 0
0x180008e8e  mov     rdi, rdx
0x180008e91  mov     eax, [rcx]
0x180008e93  mov     rsi, rcx
0x180008e96  mov     [rdx], eax
0x180008e98  and     eax, 6
0x180008e9b  cmp     al, 6
0x180008e9d  jz      loc_180008FFA
0x180008ea3  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180008ea8  and     [rsp+38h+arg_0], 0
0x180008ead  mov     ebp, eax
0x180008eaf  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180008eb6  test    rax, rax
0x180008eb9  jz      short loc_180008ED3
0x180008ebb  lea     r8, [rsp+38h+arg_0]
0x180008ec0  mov     edx, 3
0x180008ec5  mov     ecx, 3283122h
0x180008eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ecf  mov     edx, eax
0x180008ed1  jmp     short loc_180008EE1
0x180008ed3  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180008eda  test    rax, rax
0x180008edd  jnz     short loc_180008EBB
0x180008edf  xor     edx, edx
0x180008ee1  mov     r8d, edx
0x180008ee4  mov     eax, edx
0x180008ee6  and     r8d, 0FFFFFF3Fh
0x180008eed  and     edx, 80h
0x180008ef3  mov     ecx, r8d
0x180008ef6  mov     r15d, 40h ; '@'
0x180008efc  and     ecx, 3
0x180008eff  and     eax, r15d
0x180008f02  shl     ecx, 2
0x180008f05  or      ecx, eax
0x180008f07  shl     ecx, 2
0x180008f0a  or      ecx, edx
0x180008f0c  lea     ebx, ds:0[rcx*8]
0x180008f13  test    r8d, r8d
0x180008f16  jnz     short loc_180008F1D
0x180008f18  or      ebx, r15d
0x180008f1b  jmp     short loc_180008F29
0x180008f1d  xor     eax, eax
0x180008f1f  cmp     r8d, 2
0x180008f23  cmovz   eax, r15d
0x180008f27  or      ebx, eax
0x180008f29  mov     edx, 0C00h
0x180008f2e  mov     eax, ebx
0x180008f30  and     eax, edx
0x180008f32  xor     cl, cl
0x180008f34  cmp     eax, edx
0x180008f36  jnz     short loc_180008F3C
0x180008f38  mov     cl, 1
0x180008f3a  jmp     short loc_180008F41
0x180008f3c  test    r15b, bl
0x180008f3f  jnz     short loc_180008F4E
0x180008f41  test    r15b, bl
0x180008f44  jz      short loc_180008F4A
0x180008f46  test    cl, cl
0x180008f48  jnz     short loc_180008F4E
0x180008f4a  xor     eax, eax
0x180008f4c  jmp     short loc_180008F53
0x180008f4e  mov     eax, 1
0x180008f53  mov     edx, [rdi]
0x180008f55  or      ebx, eax
0x180008f57  cmp     [rsp+38h+arg_0], 0
0x180008f5c  mov     ecx, edx
0x180008f5e  mov     [rdi], edx
0x180008f60  jz      short loc_180008F95
0x180008f62  test    dl, 2
0x180008f65  jnz     short loc_180008F95
0x180008f67  mov     eax, ebx
0x180008f69  xor     eax, edx
0x180008f6b  and     eax, 180h
0x180008f70  xor     eax, edx
0x180008f72  mov     ecx, eax
0x180008f74  xor     ecx, ebx
0x180008f76  and     ecx, r15d
0x180008f79  xor     ecx, eax
0x180008f7b  mov     eax, ecx
0x180008f7d  xor     eax, ebx
0x180008f7f  and     eax, 1
0x180008f82  xor     eax, ecx
0x180008f84  mov     ecx, eax
0x180008f86  xor     ecx, ebx
0x180008f88  and     ecx, 800h
0x180008f8e  xor     ecx, eax
0x180008f90  or      ecx, 2
0x180008f93  mov     [rdi], ecx
0x180008f95  test    dl, 4
0x180008f98  jnz     short loc_180008FAA
0x180008f9a  mov     eax, ebx
0x180008f9c  xor     eax, ecx
0x180008f9e  and     eax, 400h
0x180008fa3  xor     ecx, eax
0x180008fa5  or      ecx, 4
0x180008fa8  mov     [rdi], ecx
0x180008faa  mov     eax, edx
0x180008fac  lock cmpxchg [rsi], ecx
0x180008fb0  jz      short loc_180008FB6
0x180008fb2  mov     edx, eax
0x180008fb4  jmp     short loc_180008F57
0x180008fb6  test    dl, 4
0x180008fb9  jnz     short loc_180008FCB
0x180008fbb  mov     r8d, ebp
0x180008fbe  mov     edx, 3
0x180008fc3  mov     rcx, rsi
0x180008fc6  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180008fcb  test    byte ptr [rdi], 2
0x180008fce  jnz     short loc_180008FFA
0x180008fd0  mov     eax, ebx
0x180008fd2  mov     ecx, ebx
0x180008fd4  xor     eax, [rdi]
0x180008fd6  and     eax, 180h
0x180008fdb  xor     eax, [rdi]
0x180008fdd  xor     ecx, eax
0x180008fdf  and     ecx, r15d
0x180008fe2  xor     ecx, eax
0x180008fe4  mov     edx, ecx
0x180008fe6  xor     edx, ebx
0x180008fe8  and     edx, 1
0x180008feb  xor     edx, ecx
0x180008fed  mov     eax, edx
0x180008fef  xor     eax, ebx
0x180008ff1  and     eax, 800h
0x180008ff6  xor     eax, edx
0x180008ff8  mov     [rdi], eax
0x180008ffa  mov     rbx, [rsp+38h+arg_8]
0x180008fff  mov     rax, rdi
0x180009002  mov     rbp, [rsp+38h+arg_10]
0x180009007  add     rsp, 20h
0x18000900b  pop     r15
0x18000900d  pop     rdi
0x18000900e  pop     rsi
0x18000900f  retn
```
