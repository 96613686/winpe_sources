# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x140009bec`
- end: `0x140009d63`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140009d6c`

## callees

- `0x140009698`
- `0x140009bec`
- `0x14000b9b0`
- `0x140016010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
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
  v3 = *(_DWORD *)Feature_UxLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UxLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(57048218, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UxLabTest__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_UxLabTest__descriptor,
        3u,
        v4);
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
0x140009bec  mov     [rsp+arg_8], rbx
0x140009bf1  mov     [rsp+arg_10], rbp
0x140009bf6  mov     [rsp+arg_0], rcx
0x140009bfb  push    rsi
0x140009bfc  push    rdi
0x140009bfd  push    r15
0x140009bff  sub     rsp, 20h
0x140009c03  mov     rsi, cs:Feature_UxLabTest__descriptor
0x140009c0a  mov     rbx, rdx
0x140009c0d  mov     qword ptr [rdx], 0
0x140009c14  mov     eax, [rsi]
0x140009c16  mov     [rdx], eax
0x140009c18  and     eax, 6
0x140009c1b  cmp     al, 6
0x140009c1d  jz      loc_140009D4D
0x140009c23  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140009c28  mov     ebp, eax
0x140009c2a  mov     dword ptr [rsp+38h+arg_0], 0
0x140009c32  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140009c39  test    rax, rax
0x140009c3c  jz      short loc_140009C56
0x140009c3e  lea     r8, [rsp+38h+arg_0]
0x140009c43  mov     edx, 3
0x140009c48  mov     ecx, 3667C9Ah
0x140009c4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009c52  mov     edx, eax
0x140009c54  jmp     short loc_140009C64
0x140009c56  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140009c5d  test    rax, rax
0x140009c60  jnz     short loc_140009C3E
0x140009c62  xor     edx, edx
0x140009c64  mov     r8d, edx
0x140009c67  mov     eax, edx
0x140009c69  and     r8d, 0FFFFFF3Fh
0x140009c70  and     edx, 80h
0x140009c76  mov     ecx, r8d
0x140009c79  mov     r15d, 40h ; '@'
0x140009c7f  and     ecx, 3
0x140009c82  and     eax, r15d
0x140009c85  shl     ecx, 2
0x140009c88  or      ecx, eax
0x140009c8a  shl     ecx, 2
0x140009c8d  or      ecx, edx
0x140009c8f  lea     edi, ds:0[rcx*8]
0x140009c96  test    r8d, r8d
0x140009c99  jnz     short loc_140009CA0
0x140009c9b  mov     eax, r15d
0x140009c9e  jmp     short loc_140009CAA
0x140009ca0  xor     eax, eax
0x140009ca2  cmp     r8d, 2
0x140009ca6  cmovz   eax, r15d
0x140009caa  or      edi, eax
0x140009cac  mov     eax, [rbx]
0x140009cae  cmp     dword ptr [rsp+38h+arg_0], 0
0x140009cb3  mov     edx, eax
0x140009cb5  mov     [rbx], eax
0x140009cb7  jz      short loc_140009CE7
0x140009cb9  test    dl, 2
0x140009cbc  jnz     short loc_140009CE7
0x140009cbe  mov     eax, edi
0x140009cc0  xor     eax, edx
0x140009cc2  and     eax, 180h
0x140009cc7  xor     eax, edx
0x140009cc9  mov     ecx, eax
0x140009ccb  xor     ecx, edi
0x140009ccd  and     ecx, r15d
0x140009cd0  xor     ecx, eax
0x140009cd2  or      ecx, 1
0x140009cd5  mov     eax, ecx
0x140009cd7  xor     eax, edi
0x140009cd9  and     eax, 800h
0x140009cde  xor     eax, ecx
0x140009ce0  or      eax, 2
0x140009ce3  mov     [rbx], eax
0x140009ce5  jmp     short loc_140009CE9
0x140009ce7  mov     eax, edx
0x140009ce9  mov     r8d, edx
0x140009cec  and     r8d, 4
0x140009cf0  jnz     short loc_140009D05
0x140009cf2  mov     ecx, edi
0x140009cf4  xor     ecx, eax
0x140009cf6  and     ecx, 400h
0x140009cfc  xor     ecx, eax
0x140009cfe  or      ecx, 4
0x140009d01  mov     [rbx], ecx
0x140009d03  jmp     short loc_140009D07
0x140009d05  mov     ecx, eax
0x140009d07  mov     eax, edx
0x140009d09  lock cmpxchg [rsi], ecx
0x140009d0d  jnz     short loc_140009CAE
0x140009d0f  test    r8d, r8d
0x140009d12  jnz     short loc_140009D24
0x140009d14  mov     r8d, ebp
0x140009d17  mov     edx, 3
0x140009d1c  mov     rcx, rsi
0x140009d1f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140009d24  test    byte ptr [rbx], 2
0x140009d27  jnz     short loc_140009D4D
0x140009d29  mov     eax, [rbx]
0x140009d2b  xor     eax, edi
0x140009d2d  and     eax, 180h
0x140009d32  xor     eax, [rbx]
0x140009d34  mov     ecx, eax
0x140009d36  xor     ecx, edi
0x140009d38  and     ecx, r15d
0x140009d3b  xor     ecx, eax
0x140009d3d  or      ecx, 1
0x140009d40  mov     eax, ecx
0x140009d42  xor     eax, edi
0x140009d44  and     eax, 800h
0x140009d49  xor     eax, ecx
0x140009d4b  mov     [rbx], eax
0x140009d4d  mov     rbp, [rsp+38h+arg_10]
0x140009d52  mov     rax, rbx
0x140009d55  mov     rbx, [rsp+38h+arg_8]
0x140009d5a  add     rsp, 20h
0x140009d5e  pop     r15
0x140009d60  pop     rdi
0x140009d61  pop     rsi
0x140009d62  retn
```
