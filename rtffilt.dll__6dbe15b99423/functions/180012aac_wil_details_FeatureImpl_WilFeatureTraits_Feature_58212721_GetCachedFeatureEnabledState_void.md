# wil::details::FeatureImpl<__WilFeatureTraits_Feature_58212721>::GetCachedFeatureEnabledState(void)

- ea: `0x180012aac`
- end: `0x180012c79`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_58212721@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015644`

## callees

- `0x180005dd8`
- `0x18000b3d8`
- `0x180012aac`
- `0x1800155c4`
- `0x18001b010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_58212721>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
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
  v3 = *(_DWORD *)Feature_58212721__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_58212721__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(58212721, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_57519991>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57519991>::GetImpl'::`2'::impl);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_58212721__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      (volatile signed __int32 *)Feature_58212721__descriptor,
      3u,
      v4);
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
0x180012aac  mov     [rsp+arg_0], rcx
0x180012ab1  push    rbx
0x180012ab2  push    rbp
0x180012ab3  push    rsi
0x180012ab4  push    rdi
0x180012ab5  push    r12
0x180012ab7  push    r14
0x180012ab9  sub     rsp, 28h
0x180012abd  mov     r14, cs:Feature_58212721__descriptor
0x180012ac4  mov     rdi, rdx
0x180012ac7  mov     qword ptr [rdx], 0
0x180012ace  mov     eax, [r14]
0x180012ad1  mov     [rdx], eax
0x180012ad3  and     eax, 6
0x180012ad6  cmp     al, 6
0x180012ad8  jz      loc_180012C69
0x180012ade  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012ae3  mov     ebp, eax
0x180012ae5  mov     dword ptr [rsp+58h+arg_0], 0
0x180012aed  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180012af4  test    rax, rax
0x180012af7  jz      short loc_180012B11
0x180012af9  lea     r8, [rsp+58h+arg_0]
0x180012afe  mov     edx, 3
0x180012b03  mov     ecx, 3784171h
0x180012b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b0d  mov     edx, eax
0x180012b0f  jmp     short loc_180012B1F
0x180012b11  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180012b18  test    rax, rax
0x180012b1b  jnz     short loc_180012AF9
0x180012b1d  xor     edx, edx
0x180012b1f  mov     r8d, edx
0x180012b22  mov     eax, edx
0x180012b24  and     r8d, 0FFFFFF3Fh
0x180012b2b  and     edx, 80h
0x180012b31  mov     ecx, r8d
0x180012b34  mov     r12d, 40h ; '@'
0x180012b3a  and     ecx, 3
0x180012b3d  and     eax, r12d
0x180012b40  shl     ecx, 2
0x180012b43  or      ecx, eax
0x180012b45  shl     ecx, 2
0x180012b48  or      ecx, edx
0x180012b4a  lea     ebx, ds:0[rcx*8]
0x180012b51  test    r8d, r8d
0x180012b54  jnz     short loc_180012B5B
0x180012b56  mov     eax, r12d
0x180012b59  jmp     short loc_180012B65
0x180012b5b  xor     eax, eax
0x180012b5d  cmp     r8d, 2
0x180012b61  cmovz   eax, r12d
0x180012b65  or      ebx, eax
0x180012b67  mov     ecx, 0C00h
0x180012b6c  mov     eax, ebx
0x180012b6e  and     eax, ecx
0x180012b70  cmp     eax, ecx
0x180012b72  jnz     short loc_180012B79
0x180012b74  mov     sil, 1
0x180012b77  jmp     short loc_180012B81
0x180012b79  xor     sil, sil
0x180012b7c  test    r12b, bl
0x180012b7f  jz      short loc_180012B9C
0x180012b81  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57519991@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57519991@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57519991> `wil::Feature<__WilFeatureTraits_Feature_57519991>::GetImpl(void)'::`2'::impl
0x180012b88  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57519991@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57519991>::__private_IsEnabled(wil::ReportingKind)
0x180012b8d  test    sil, sil
0x180012b90  jz      short loc_180012B9E
0x180012b92  test    al, al
0x180012b94  jnz     short loc_180012B9E
0x180012b96  btr     ebx, 0Ah
0x180012b9a  jmp     short loc_180012B9E
0x180012b9c  xor     al, al
0x180012b9e  test    r12b, bl
0x180012ba1  jz      short loc_180012BAE
0x180012ba3  test    al, al
0x180012ba5  jz      short loc_180012BAE
0x180012ba7  mov     esi, 1
0x180012bac  jmp     short loc_180012BB0
0x180012bae  xor     esi, esi
0x180012bb0  mov     eax, [rdi]
0x180012bb2  or      esi, ebx
0x180012bb4  mov     ebx, 180h
0x180012bb9  cmp     dword ptr [rsp+58h+arg_0], 0
0x180012bbe  mov     edx, eax
0x180012bc0  mov     [rdi], eax
0x180012bc2  jz      short loc_180012BFC
0x180012bc4  test    dl, 2
0x180012bc7  jnz     short loc_180012BFC
0x180012bc9  mov     eax, esi
0x180012bcb  xor     eax, edx
0x180012bcd  and     eax, ebx
0x180012bcf  xor     eax, edx
0x180012bd1  mov     ecx, eax
0x180012bd3  xor     ecx, esi
0x180012bd5  and     ecx, r12d
0x180012bd8  xor     ecx, eax
0x180012bda  mov     eax, ecx
0x180012bdc  xor     eax, esi
0x180012bde  and     eax, 1
0x180012be1  xor     eax, ecx
0x180012be3  mov     r8d, eax
0x180012be6  xor     r8d, esi
0x180012be9  and     r8d, 800h
0x180012bf0  xor     r8d, eax
0x180012bf3  or      r8d, 2
0x180012bf7  mov     [rdi], r8d
0x180012bfa  jmp     short loc_180012BFF
0x180012bfc  mov     r8d, edx
0x180012bff  mov     r9d, edx
0x180012c02  and     r9d, 4
0x180012c06  jnz     short loc_180012C1D
0x180012c08  mov     ecx, esi
0x180012c0a  xor     ecx, r8d
0x180012c0d  and     ecx, 400h
0x180012c13  xor     ecx, r8d
0x180012c16  or      ecx, 4
0x180012c19  mov     [rdi], ecx
0x180012c1b  jmp     short loc_180012C20
0x180012c1d  mov     ecx, r8d
0x180012c20  mov     eax, edx
0x180012c22  lock cmpxchg [r14], ecx
0x180012c27  jnz     short loc_180012BB9
0x180012c29  test    r9d, r9d
0x180012c2c  jnz     short loc_180012C3D
0x180012c2e  mov     r8d, ebp
0x180012c31  lea     edx, [r9+3]
0x180012c35  mov     rcx, r14
0x180012c38  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180012c3d  test    byte ptr [rdi], 2
0x180012c40  jnz     short loc_180012C69
0x180012c42  mov     eax, [rdi]
0x180012c44  xor     eax, esi
0x180012c46  and     eax, ebx
0x180012c48  xor     eax, [rdi]
0x180012c4a  mov     ecx, eax
0x180012c4c  xor     ecx, esi
0x180012c4e  and     ecx, r12d
0x180012c51  xor     ecx, eax
0x180012c53  mov     edx, ecx
0x180012c55  xor     edx, esi
0x180012c57  and     edx, 1
0x180012c5a  xor     edx, ecx
0x180012c5c  mov     eax, edx
0x180012c5e  xor     eax, esi
0x180012c60  and     eax, 800h
0x180012c65  xor     eax, edx
0x180012c67  mov     [rdi], eax
0x180012c69  mov     rax, rdi
0x180012c6c  add     rsp, 28h
0x180012c70  pop     r14
0x180012c72  pop     r12
0x180012c74  pop     rdi
0x180012c75  pop     rsi
0x180012c76  pop     rbp
0x180012c77  pop     rbx
0x180012c78  retn
```
