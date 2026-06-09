# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180012b98`
- end: `0x180012d05`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013b74`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x180012b98`
- `0x180029010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(45036797, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_25_11_NonSec__descriptor, 3, v4);
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
0x180012b98  mov     [rsp+arg_8], rbx
0x180012b9d  mov     [rsp+arg_10], rbp
0x180012ba2  mov     [rsp+arg_0], rcx
0x180012ba7  push    rsi
0x180012ba8  push    rdi
0x180012ba9  push    r15
0x180012bab  sub     rsp, 20h
0x180012baf  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x180012bb6  mov     rbx, rdx
0x180012bb9  mov     qword ptr [rdx], 0
0x180012bc0  mov     eax, [rsi]
0x180012bc2  mov     [rdx], eax
0x180012bc4  and     eax, 6
0x180012bc7  cmp     al, 6
0x180012bc9  jz      loc_180012CEF
0x180012bcf  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012bd4  mov     ebp, eax
0x180012bd6  mov     dword ptr [rsp+38h+arg_0], 0
0x180012bde  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180012be5  test    rax, rax
0x180012be8  jz      short loc_180012C02
0x180012bea  lea     r8, [rsp+38h+arg_0]
0x180012bef  mov     edx, 3
0x180012bf4  mov     ecx, 2AF34FDh
0x180012bf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012bfe  mov     edx, eax
0x180012c00  jmp     short loc_180012C10
0x180012c02  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180012c09  test    rax, rax
0x180012c0c  jnz     short loc_180012BEA
0x180012c0e  xor     edx, edx
0x180012c10  mov     r8d, edx
0x180012c13  mov     eax, edx
0x180012c15  and     r8d, 0FFFFFF3Fh
0x180012c1c  and     edx, 80h
0x180012c22  mov     ecx, r8d
0x180012c25  mov     r15d, 40h ; '@'
0x180012c2b  and     ecx, 3
0x180012c2e  and     eax, r15d
0x180012c31  shl     ecx, 2
0x180012c34  or      ecx, eax
0x180012c36  shl     ecx, 2
0x180012c39  or      ecx, edx
0x180012c3b  lea     edi, ds:0[rcx*8]
0x180012c42  test    r8d, r8d
0x180012c45  jnz     short loc_180012C4C
0x180012c47  mov     eax, r15d
0x180012c4a  jmp     short loc_180012C56
0x180012c4c  xor     eax, eax
0x180012c4e  cmp     r8d, 2
0x180012c52  cmovz   eax, r15d
0x180012c56  or      edi, eax
0x180012c58  mov     eax, [rbx]
0x180012c5a  cmp     dword ptr [rsp+38h+arg_0], 0
0x180012c5f  mov     edx, eax
0x180012c61  mov     [rbx], eax
0x180012c63  jz      short loc_180012C8F
0x180012c65  test    dl, 2
0x180012c68  jnz     short loc_180012C8F
0x180012c6a  xor     eax, edi
0x180012c6c  and     eax, 180h
0x180012c71  xor     eax, edx
0x180012c73  mov     ecx, eax
0x180012c75  xor     ecx, edi
0x180012c77  and     ecx, r15d
0x180012c7a  xor     ecx, eax
0x180012c7c  or      ecx, 1
0x180012c7f  mov     eax, ecx
0x180012c81  xor     eax, edi
0x180012c83  and     eax, 800h
0x180012c88  xor     eax, ecx
0x180012c8a  or      eax, 2
0x180012c8d  mov     [rbx], eax
0x180012c8f  mov     r8d, edx
0x180012c92  mov     ecx, eax
0x180012c94  and     r8d, 4
0x180012c98  jnz     short loc_180012CA9
0x180012c9a  xor     ecx, edi
0x180012c9c  and     ecx, 400h
0x180012ca2  xor     ecx, eax
0x180012ca4  or      ecx, 4
0x180012ca7  mov     [rbx], ecx
0x180012ca9  mov     eax, edx
0x180012cab  lock cmpxchg [rsi], ecx
0x180012caf  jnz     short loc_180012C5A
0x180012cb1  test    r8d, r8d
0x180012cb4  jnz     short loc_180012CC6
0x180012cb6  mov     r8d, ebp
0x180012cb9  mov     edx, 3
0x180012cbe  mov     rcx, rsi
0x180012cc1  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180012cc6  test    byte ptr [rbx], 2
0x180012cc9  jnz     short loc_180012CEF
0x180012ccb  mov     eax, [rbx]
0x180012ccd  xor     eax, edi
0x180012ccf  and     eax, 180h
0x180012cd4  xor     eax, [rbx]
0x180012cd6  mov     ecx, eax
0x180012cd8  xor     ecx, edi
0x180012cda  and     ecx, r15d
0x180012cdd  xor     ecx, eax
0x180012cdf  or      ecx, 1
0x180012ce2  mov     eax, ecx
0x180012ce4  xor     eax, edi
0x180012ce6  and     eax, 800h
0x180012ceb  xor     eax, ecx
0x180012ced  mov     [rbx], eax
0x180012cef  mov     rbp, [rsp+38h+arg_10]
0x180012cf4  mov     rax, rbx
0x180012cf7  mov     rbx, [rsp+38h+arg_8]
0x180012cfc  add     rsp, 20h
0x180012d00  pop     r15
0x180012d02  pop     rdi
0x180012d03  pop     rsi
0x180012d04  retn
```
