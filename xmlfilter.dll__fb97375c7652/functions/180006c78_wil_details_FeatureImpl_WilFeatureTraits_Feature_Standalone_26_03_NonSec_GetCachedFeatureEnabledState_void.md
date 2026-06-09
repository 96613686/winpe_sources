# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180006c78`
- end: `0x180006de5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007ad0`

## callees

- `0x180005dd0`
- `0x180006c78`
- `0x18000c3f0`
- `0x180017010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_03_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_03_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(58599553, 3, &v14);
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
            ^ ((unsigned __int16)v8
             ^ (unsigned __int16)v9)
            & 0x180
            ^ (v8
             ^ v9
             ^ ((unsigned __int16)v8
              ^ (unsigned __int16)v9)
             & 0x180)
            & 0x40
            | 1)
           ^ ((unsigned __int16)v8
            ^ ((unsigned __int16)(v9 ^ (v8 ^ v9) & 0x180 ^ (v8 ^ v9 ^ (v8 ^ v9) & 0x180) & 0x40) | 1))
           & 0x800
           | 2;
        *(_DWORD *)a2 = v9;
      }
      v12 = v9;
      if ( (v11 & 4) == 0 )
      {
        v12 = v9 ^ ((unsigned __int16)v8 ^ (unsigned __int16)v9) & 0x400 | 4;
        *(_DWORD *)a2 = v12;
      }
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_03_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_26_03_NonSec__descriptor, 3, v4);
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
0x180006c78  mov     [rsp+arg_8], rbx
0x180006c7d  mov     [rsp+arg_10], rbp
0x180006c82  mov     [rsp+arg_0], rcx
0x180006c87  push    rsi
0x180006c88  push    rdi
0x180006c89  push    r15
0x180006c8b  sub     rsp, 20h
0x180006c8f  mov     rsi, cs:Feature_Standalone_26_03_NonSec__descriptor
0x180006c96  mov     rbx, rdx
0x180006c99  mov     qword ptr [rdx], 0
0x180006ca0  mov     eax, [rsi]
0x180006ca2  mov     [rdx], eax
0x180006ca4  and     eax, 6
0x180006ca7  cmp     al, 6
0x180006ca9  jz      loc_180006DCF
0x180006caf  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180006cb4  mov     ebp, eax
0x180006cb6  mov     dword ptr [rsp+38h+arg_0], 0
0x180006cbe  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180006cc5  test    rax, rax
0x180006cc8  jz      short loc_180006CE2
0x180006cca  lea     r8, [rsp+38h+arg_0]
0x180006ccf  mov     edx, 3
0x180006cd4  mov     ecx, 37E2881h
0x180006cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cde  mov     edx, eax
0x180006ce0  jmp     short loc_180006CF0
0x180006ce2  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180006ce9  test    rax, rax
0x180006cec  jnz     short loc_180006CCA
0x180006cee  xor     edx, edx
0x180006cf0  mov     r8d, edx
0x180006cf3  mov     eax, edx
0x180006cf5  and     r8d, 0FFFFFF3Fh
0x180006cfc  and     edx, 80h
0x180006d02  mov     ecx, r8d
0x180006d05  mov     r15d, 40h ; '@'
0x180006d0b  and     ecx, 3
0x180006d0e  and     eax, r15d
0x180006d11  shl     ecx, 2
0x180006d14  or      ecx, eax
0x180006d16  shl     ecx, 2
0x180006d19  or      ecx, edx
0x180006d1b  lea     edi, ds:0[rcx*8]
0x180006d22  test    r8d, r8d
0x180006d25  jnz     short loc_180006D2C
0x180006d27  mov     eax, r15d
0x180006d2a  jmp     short loc_180006D36
0x180006d2c  xor     eax, eax
0x180006d2e  cmp     r8d, 2
0x180006d32  cmovz   eax, r15d
0x180006d36  or      edi, eax
0x180006d38  mov     eax, [rbx]
0x180006d3a  cmp     dword ptr [rsp+38h+arg_0], 0
0x180006d3f  mov     edx, eax
0x180006d41  mov     [rbx], eax
0x180006d43  jz      short loc_180006D6F
0x180006d45  test    dl, 2
0x180006d48  jnz     short loc_180006D6F
0x180006d4a  xor     eax, edi
0x180006d4c  and     eax, 180h
0x180006d51  xor     eax, edx
0x180006d53  mov     ecx, eax
0x180006d55  xor     ecx, edi
0x180006d57  and     ecx, r15d
0x180006d5a  xor     ecx, eax
0x180006d5c  or      ecx, 1
0x180006d5f  mov     eax, ecx
0x180006d61  xor     eax, edi
0x180006d63  and     eax, 800h
0x180006d68  xor     eax, ecx
0x180006d6a  or      eax, 2
0x180006d6d  mov     [rbx], eax
0x180006d6f  mov     r8d, edx
0x180006d72  mov     ecx, eax
0x180006d74  and     r8d, 4
0x180006d78  jnz     short loc_180006D89
0x180006d7a  xor     ecx, edi
0x180006d7c  and     ecx, 400h
0x180006d82  xor     ecx, eax
0x180006d84  or      ecx, 4
0x180006d87  mov     [rbx], ecx
0x180006d89  mov     eax, edx
0x180006d8b  lock cmpxchg [rsi], ecx
0x180006d8f  jnz     short loc_180006D3A
0x180006d91  test    r8d, r8d
0x180006d94  jnz     short loc_180006DA6
0x180006d96  mov     r8d, ebp
0x180006d99  mov     edx, 3
0x180006d9e  mov     rcx, rsi
0x180006da1  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180006da6  test    byte ptr [rbx], 2
0x180006da9  jnz     short loc_180006DCF
0x180006dab  mov     eax, [rbx]
0x180006dad  xor     eax, edi
0x180006daf  and     eax, 180h
0x180006db4  xor     eax, [rbx]
0x180006db6  mov     ecx, eax
0x180006db8  xor     ecx, edi
0x180006dba  and     ecx, r15d
0x180006dbd  xor     ecx, eax
0x180006dbf  or      ecx, 1
0x180006dc2  mov     eax, ecx
0x180006dc4  xor     eax, edi
0x180006dc6  and     eax, 800h
0x180006dcb  xor     eax, ecx
0x180006dcd  mov     [rbx], eax
0x180006dcf  mov     rbp, [rsp+38h+arg_10]
0x180006dd4  mov     rax, rbx
0x180006dd7  mov     rbx, [rsp+38h+arg_8]
0x180006ddc  add     rsp, 20h
0x180006de0  pop     r15
0x180006de2  pop     rdi
0x180006de3  pop     rsi
0x180006de4  retn
```
