# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180017c78`
- end: `0x180017def`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018528`

## callees

- `0x180016be8`
- `0x180017c78`
- `0x180018da4`
- `0x18001e010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, __int64, wil::details **); // rax
  int v6; // edx
  int v7; // eax
  int v8; // edi
  int v9; // eax
  bool v10; // zf
  signed __int32 v11; // edx
  signed __int32 v12; // ecx
  wil::details *v14; // [rsp+40h] [rbp+8h] BYREF

  v14 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_ValLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(57048226, 3, &v14);
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
    v9 = *(_DWORD *)a2;
    do
    {
      v10 = (_DWORD)v14 == 0;
      v11 = v9;
      *(_DWORD *)a2 = v9;
      if ( !v10 && (v9 & 2) == 0 )
      {
        v9 = (v9
            ^ ((unsigned __int16)v9
             ^ (unsigned __int16)v8)
            & 0x180
            ^ (v8
             ^ v9
             ^ ((unsigned __int16)v9
              ^ (unsigned __int16)v8)
             & 0x180)
            & 0x40
            | 1)
           ^ ((unsigned __int16)v8
            ^ ((unsigned __int16)(v9 ^ (v9 ^ v8) & 0x180 ^ (v8 ^ v9 ^ (v9 ^ v8) & 0x180) & 0x40) | 1))
           & 0x800
           | 2;
        *(_DWORD *)a2 = v9;
      }
      if ( (v11 & 4) != 0 )
      {
        v12 = v9;
      }
      else
      {
        v12 = v9 ^ ((unsigned __int16)v9 ^ (unsigned __int16)v8) & 0x400 | 4;
        *(_DWORD *)a2 = v12;
      }
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValLabTest__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_ValLabTest__descriptor, 3, v4);
    if ( (*(_BYTE *)a2 & 2) == 0 )
      *(_DWORD *)a2 = (*(_DWORD *)a2
                     ^ ((unsigned __int16)v8
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180
                     ^ (v8
                      ^ *(_DWORD *)a2
                      ^ ((unsigned __int16)v8
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180)
                     & 0x40
                     | 1)
                    ^ ((unsigned __int16)v8
                     ^ (*(_WORD *)a2
                      ^ ((unsigned __int16)v8
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180
                      ^ ((unsigned __int16)v8
                       ^ *(_WORD *)a2
                       ^ ((unsigned __int16)v8
                        ^ (unsigned __int16)*(_DWORD *)a2)
                       & 0x180)
                      & 0x40
                      | 1))
                    & 0x800;
  }
  return a2;
}

```

## disassembly

```asm
0x180017c78  mov     [rsp+arg_8], rbx
0x180017c7d  mov     [rsp+arg_10], rbp
0x180017c82  mov     [rsp+arg_0], rcx
0x180017c87  push    rsi
0x180017c88  push    rdi
0x180017c89  push    r15
0x180017c8b  sub     rsp, 20h
0x180017c8f  mov     rsi, cs:Feature_ValLabTest__descriptor
0x180017c96  mov     rbx, rdx
0x180017c99  mov     qword ptr [rdx], 0
0x180017ca0  mov     eax, [rsi]
0x180017ca2  mov     [rdx], eax
0x180017ca4  and     eax, 6
0x180017ca7  cmp     al, 6
0x180017ca9  jz      loc_180017DD9
0x180017caf  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180017cb4  mov     ebp, eax
0x180017cb6  mov     dword ptr [rsp+38h+arg_0], 0
0x180017cbe  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180017cc5  test    rax, rax
0x180017cc8  jz      short loc_180017CE2
0x180017cca  lea     r8, [rsp+38h+arg_0]
0x180017ccf  mov     edx, 3
0x180017cd4  mov     ecx, 3667CA2h
0x180017cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017cde  mov     edx, eax
0x180017ce0  jmp     short loc_180017CF0
0x180017ce2  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180017ce9  test    rax, rax
0x180017cec  jnz     short loc_180017CCA
0x180017cee  xor     edx, edx
0x180017cf0  mov     r8d, edx
0x180017cf3  mov     eax, edx
0x180017cf5  and     r8d, 0FFFFFF3Fh
0x180017cfc  and     edx, 80h
0x180017d02  mov     ecx, r8d
0x180017d05  mov     r15d, 40h ; '@'
0x180017d0b  and     ecx, 3
0x180017d0e  and     eax, r15d
0x180017d11  shl     ecx, 2
0x180017d14  or      ecx, eax
0x180017d16  shl     ecx, 2
0x180017d19  or      ecx, edx
0x180017d1b  lea     edi, ds:0[rcx*8]
0x180017d22  test    r8d, r8d
0x180017d25  jnz     short loc_180017D2C
0x180017d27  mov     eax, r15d
0x180017d2a  jmp     short loc_180017D36
0x180017d2c  xor     eax, eax
0x180017d2e  cmp     r8d, 2
0x180017d32  cmovz   eax, r15d
0x180017d36  or      edi, eax
0x180017d38  mov     eax, [rbx]
0x180017d3a  cmp     dword ptr [rsp+38h+arg_0], 0
0x180017d3f  mov     edx, eax
0x180017d41  mov     [rbx], eax
0x180017d43  jz      short loc_180017D73
0x180017d45  test    dl, 2
0x180017d48  jnz     short loc_180017D73
0x180017d4a  mov     eax, edi
0x180017d4c  xor     eax, edx
0x180017d4e  and     eax, 180h
0x180017d53  xor     eax, edx
0x180017d55  mov     ecx, eax
0x180017d57  xor     ecx, edi
0x180017d59  and     ecx, r15d
0x180017d5c  xor     ecx, eax
0x180017d5e  or      ecx, 1
0x180017d61  mov     eax, ecx
0x180017d63  xor     eax, edi
0x180017d65  and     eax, 800h
0x180017d6a  xor     eax, ecx
0x180017d6c  or      eax, 2
0x180017d6f  mov     [rbx], eax
0x180017d71  jmp     short loc_180017D75
0x180017d73  mov     eax, edx
0x180017d75  mov     r8d, edx
0x180017d78  and     r8d, 4
0x180017d7c  jnz     short loc_180017D91
0x180017d7e  mov     ecx, edi
0x180017d80  xor     ecx, eax
0x180017d82  and     ecx, 400h
0x180017d88  xor     ecx, eax
0x180017d8a  or      ecx, 4
0x180017d8d  mov     [rbx], ecx
0x180017d8f  jmp     short loc_180017D93
0x180017d91  mov     ecx, eax
0x180017d93  mov     eax, edx
0x180017d95  lock cmpxchg [rsi], ecx
0x180017d99  jnz     short loc_180017D3A
0x180017d9b  test    r8d, r8d
0x180017d9e  jnz     short loc_180017DB0
0x180017da0  mov     r8d, ebp
0x180017da3  mov     edx, 3
0x180017da8  mov     rcx, rsi
0x180017dab  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180017db0  test    byte ptr [rbx], 2
0x180017db3  jnz     short loc_180017DD9
0x180017db5  mov     eax, [rbx]
0x180017db7  xor     eax, edi
0x180017db9  and     eax, 180h
0x180017dbe  xor     eax, [rbx]
0x180017dc0  mov     ecx, eax
0x180017dc2  xor     ecx, edi
0x180017dc4  and     ecx, r15d
0x180017dc7  xor     ecx, eax
0x180017dc9  or      ecx, 1
0x180017dcc  mov     eax, ecx
0x180017dce  xor     eax, edi
0x180017dd0  and     eax, 800h
0x180017dd5  xor     eax, ecx
0x180017dd7  mov     [rbx], eax
0x180017dd9  mov     rbp, [rsp+38h+arg_10]
0x180017dde  mov     rax, rbx
0x180017de1  mov     rbx, [rsp+38h+arg_8]
0x180017de6  add     rsp, 20h
0x180017dea  pop     r15
0x180017dec  pop     rdi
0x180017ded  pop     rsi
0x180017dee  retn
```
