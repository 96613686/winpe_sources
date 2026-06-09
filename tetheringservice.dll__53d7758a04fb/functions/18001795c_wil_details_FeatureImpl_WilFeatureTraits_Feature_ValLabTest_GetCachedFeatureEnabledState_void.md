# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x18001795c`
- end: `0x180017ad3`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018138`

## callees

- `0x180005cf8`
- `0x180009548`
- `0x18001795c`
- `0x180033010`

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
0x18001795c  mov     [rsp+arg_8], rbx
0x180017961  mov     [rsp+arg_10], rbp
0x180017966  mov     [rsp+arg_0], rcx
0x18001796b  push    rsi
0x18001796c  push    rdi
0x18001796d  push    r15
0x18001796f  sub     rsp, 20h
0x180017973  mov     rsi, cs:Feature_ValLabTest__descriptor
0x18001797a  mov     rbx, rdx
0x18001797d  mov     qword ptr [rdx], 0
0x180017984  mov     eax, [rsi]
0x180017986  mov     [rdx], eax
0x180017988  and     eax, 6
0x18001798b  cmp     al, 6
0x18001798d  jz      loc_180017ABD
0x180017993  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180017998  mov     ebp, eax
0x18001799a  mov     dword ptr [rsp+38h+arg_0], 0
0x1800179a2  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800179a9  test    rax, rax
0x1800179ac  jz      short loc_1800179C6
0x1800179ae  lea     r8, [rsp+38h+arg_0]
0x1800179b3  mov     edx, 3
0x1800179b8  mov     ecx, 3667CA2h
0x1800179bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179c2  mov     edx, eax
0x1800179c4  jmp     short loc_1800179D4
0x1800179c6  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800179cd  test    rax, rax
0x1800179d0  jnz     short loc_1800179AE
0x1800179d2  xor     edx, edx
0x1800179d4  mov     r8d, edx
0x1800179d7  mov     eax, edx
0x1800179d9  and     r8d, 0FFFFFF3Fh
0x1800179e0  and     edx, 80h
0x1800179e6  mov     ecx, r8d
0x1800179e9  mov     r15d, 40h ; '@'
0x1800179ef  and     ecx, 3
0x1800179f2  and     eax, r15d
0x1800179f5  shl     ecx, 2
0x1800179f8  or      ecx, eax
0x1800179fa  shl     ecx, 2
0x1800179fd  or      ecx, edx
0x1800179ff  lea     edi, ds:0[rcx*8]
0x180017a06  test    r8d, r8d
0x180017a09  jnz     short loc_180017A10
0x180017a0b  mov     eax, r15d
0x180017a0e  jmp     short loc_180017A1A
0x180017a10  xor     eax, eax
0x180017a12  cmp     r8d, 2
0x180017a16  cmovz   eax, r15d
0x180017a1a  or      edi, eax
0x180017a1c  mov     eax, [rbx]
0x180017a1e  cmp     dword ptr [rsp+38h+arg_0], 0
0x180017a23  mov     edx, eax
0x180017a25  mov     [rbx], eax
0x180017a27  jz      short loc_180017A57
0x180017a29  test    dl, 2
0x180017a2c  jnz     short loc_180017A57
0x180017a2e  mov     eax, edi
0x180017a30  xor     eax, edx
0x180017a32  and     eax, 180h
0x180017a37  xor     eax, edx
0x180017a39  mov     ecx, eax
0x180017a3b  xor     ecx, edi
0x180017a3d  and     ecx, r15d
0x180017a40  xor     ecx, eax
0x180017a42  or      ecx, 1
0x180017a45  mov     eax, ecx
0x180017a47  xor     eax, edi
0x180017a49  and     eax, 800h
0x180017a4e  xor     eax, ecx
0x180017a50  or      eax, 2
0x180017a53  mov     [rbx], eax
0x180017a55  jmp     short loc_180017A59
0x180017a57  mov     eax, edx
0x180017a59  mov     r8d, edx
0x180017a5c  and     r8d, 4
0x180017a60  jnz     short loc_180017A75
0x180017a62  mov     ecx, edi
0x180017a64  xor     ecx, eax
0x180017a66  and     ecx, 400h
0x180017a6c  xor     ecx, eax
0x180017a6e  or      ecx, 4
0x180017a71  mov     [rbx], ecx
0x180017a73  jmp     short loc_180017A77
0x180017a75  mov     ecx, eax
0x180017a77  mov     eax, edx
0x180017a79  lock cmpxchg [rsi], ecx
0x180017a7d  jnz     short loc_180017A1E
0x180017a7f  test    r8d, r8d
0x180017a82  jnz     short loc_180017A94
0x180017a84  mov     r8d, ebp
0x180017a87  mov     edx, 3
0x180017a8c  mov     rcx, rsi
0x180017a8f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180017a94  test    byte ptr [rbx], 2
0x180017a97  jnz     short loc_180017ABD
0x180017a99  mov     eax, [rbx]
0x180017a9b  xor     eax, edi
0x180017a9d  and     eax, 180h
0x180017aa2  xor     eax, [rbx]
0x180017aa4  mov     ecx, eax
0x180017aa6  xor     ecx, edi
0x180017aa8  and     ecx, r15d
0x180017aab  xor     ecx, eax
0x180017aad  or      ecx, 1
0x180017ab0  mov     eax, ecx
0x180017ab2  xor     eax, edi
0x180017ab4  and     eax, 800h
0x180017ab9  xor     eax, ecx
0x180017abb  mov     [rbx], eax
0x180017abd  mov     rbp, [rsp+38h+arg_10]
0x180017ac2  mov     rax, rbx
0x180017ac5  mov     rbx, [rsp+38h+arg_8]
0x180017aca  add     rsp, 20h
0x180017ace  pop     r15
0x180017ad0  pop     rdi
0x180017ad1  pop     rsi
0x180017ad2  retn
```
