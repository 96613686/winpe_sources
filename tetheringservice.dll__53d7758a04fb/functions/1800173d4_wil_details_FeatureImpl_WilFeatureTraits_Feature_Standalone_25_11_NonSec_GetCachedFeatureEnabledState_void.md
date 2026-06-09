# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x1800173d4`
- end: `0x180017541`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017e58`

## callees

- `0x180005cf8`
- `0x180009548`
- `0x1800173d4`
- `0x180033010`

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
0x1800173d4  mov     [rsp+arg_8], rbx
0x1800173d9  mov     [rsp+arg_10], rbp
0x1800173de  mov     [rsp+arg_0], rcx
0x1800173e3  push    rsi
0x1800173e4  push    rdi
0x1800173e5  push    r15
0x1800173e7  sub     rsp, 20h
0x1800173eb  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x1800173f2  mov     rbx, rdx
0x1800173f5  mov     qword ptr [rdx], 0
0x1800173fc  mov     eax, [rsi]
0x1800173fe  mov     [rdx], eax
0x180017400  and     eax, 6
0x180017403  cmp     al, 6
0x180017405  jz      loc_18001752B
0x18001740b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180017410  mov     ebp, eax
0x180017412  mov     dword ptr [rsp+38h+arg_0], 0
0x18001741a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180017421  test    rax, rax
0x180017424  jz      short loc_18001743E
0x180017426  lea     r8, [rsp+38h+arg_0]
0x18001742b  mov     edx, 3
0x180017430  mov     ecx, 2AF34FDh
0x180017435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001743a  mov     edx, eax
0x18001743c  jmp     short loc_18001744C
0x18001743e  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180017445  test    rax, rax
0x180017448  jnz     short loc_180017426
0x18001744a  xor     edx, edx
0x18001744c  mov     r8d, edx
0x18001744f  mov     eax, edx
0x180017451  and     r8d, 0FFFFFF3Fh
0x180017458  and     edx, 80h
0x18001745e  mov     ecx, r8d
0x180017461  mov     r15d, 40h ; '@'
0x180017467  and     ecx, 3
0x18001746a  and     eax, r15d
0x18001746d  shl     ecx, 2
0x180017470  or      ecx, eax
0x180017472  shl     ecx, 2
0x180017475  or      ecx, edx
0x180017477  lea     edi, ds:0[rcx*8]
0x18001747e  test    r8d, r8d
0x180017481  jnz     short loc_180017488
0x180017483  mov     eax, r15d
0x180017486  jmp     short loc_180017492
0x180017488  xor     eax, eax
0x18001748a  cmp     r8d, 2
0x18001748e  cmovz   eax, r15d
0x180017492  or      edi, eax
0x180017494  mov     eax, [rbx]
0x180017496  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001749b  mov     edx, eax
0x18001749d  mov     [rbx], eax
0x18001749f  jz      short loc_1800174CB
0x1800174a1  test    dl, 2
0x1800174a4  jnz     short loc_1800174CB
0x1800174a6  xor     eax, edi
0x1800174a8  and     eax, 180h
0x1800174ad  xor     eax, edx
0x1800174af  mov     ecx, eax
0x1800174b1  xor     ecx, edi
0x1800174b3  and     ecx, r15d
0x1800174b6  xor     ecx, eax
0x1800174b8  or      ecx, 1
0x1800174bb  mov     eax, ecx
0x1800174bd  xor     eax, edi
0x1800174bf  and     eax, 800h
0x1800174c4  xor     eax, ecx
0x1800174c6  or      eax, 2
0x1800174c9  mov     [rbx], eax
0x1800174cb  mov     r8d, edx
0x1800174ce  mov     ecx, eax
0x1800174d0  and     r8d, 4
0x1800174d4  jnz     short loc_1800174E5
0x1800174d6  xor     ecx, edi
0x1800174d8  and     ecx, 400h
0x1800174de  xor     ecx, eax
0x1800174e0  or      ecx, 4
0x1800174e3  mov     [rbx], ecx
0x1800174e5  mov     eax, edx
0x1800174e7  lock cmpxchg [rsi], ecx
0x1800174eb  jnz     short loc_180017496
0x1800174ed  test    r8d, r8d
0x1800174f0  jnz     short loc_180017502
0x1800174f2  mov     r8d, ebp
0x1800174f5  mov     edx, 3
0x1800174fa  mov     rcx, rsi
0x1800174fd  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180017502  test    byte ptr [rbx], 2
0x180017505  jnz     short loc_18001752B
0x180017507  mov     eax, [rbx]
0x180017509  xor     eax, edi
0x18001750b  and     eax, 180h
0x180017510  xor     eax, [rbx]
0x180017512  mov     ecx, eax
0x180017514  xor     ecx, edi
0x180017516  and     ecx, r15d
0x180017519  xor     ecx, eax
0x18001751b  or      ecx, 1
0x18001751e  mov     eax, ecx
0x180017520  xor     eax, edi
0x180017522  and     eax, 800h
0x180017527  xor     eax, ecx
0x180017529  mov     [rbx], eax
0x18001752b  mov     rbp, [rsp+38h+arg_10]
0x180017530  mov     rax, rbx
0x180017533  mov     rbx, [rsp+38h+arg_8]
0x180017538  add     rsp, 20h
0x18001753c  pop     r15
0x18001753e  pop     rdi
0x18001753f  pop     rsi
0x180017540  retn
```
