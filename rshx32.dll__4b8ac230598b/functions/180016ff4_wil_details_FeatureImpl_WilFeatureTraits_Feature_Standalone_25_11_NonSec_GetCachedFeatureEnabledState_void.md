# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180016ff4`
- end: `0x180017161`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017f68`

## callees

- `0x180016be8`
- `0x180016ff4`
- `0x180018da4`
- `0x18001e010`

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
0x180016ff4  mov     [rsp+arg_8], rbx
0x180016ff9  mov     [rsp+arg_10], rbp
0x180016ffe  mov     [rsp+arg_0], rcx
0x180017003  push    rsi
0x180017004  push    rdi
0x180017005  push    r15
0x180017007  sub     rsp, 20h
0x18001700b  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x180017012  mov     rbx, rdx
0x180017015  mov     qword ptr [rdx], 0
0x18001701c  mov     eax, [rsi]
0x18001701e  mov     [rdx], eax
0x180017020  and     eax, 6
0x180017023  cmp     al, 6
0x180017025  jz      loc_18001714B
0x18001702b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180017030  mov     ebp, eax
0x180017032  mov     dword ptr [rsp+38h+arg_0], 0
0x18001703a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180017041  test    rax, rax
0x180017044  jz      short loc_18001705E
0x180017046  lea     r8, [rsp+38h+arg_0]
0x18001704b  mov     edx, 3
0x180017050  mov     ecx, 2AF34FDh
0x180017055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001705a  mov     edx, eax
0x18001705c  jmp     short loc_18001706C
0x18001705e  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180017065  test    rax, rax
0x180017068  jnz     short loc_180017046
0x18001706a  xor     edx, edx
0x18001706c  mov     r8d, edx
0x18001706f  mov     eax, edx
0x180017071  and     r8d, 0FFFFFF3Fh
0x180017078  and     edx, 80h
0x18001707e  mov     ecx, r8d
0x180017081  mov     r15d, 40h ; '@'
0x180017087  and     ecx, 3
0x18001708a  and     eax, r15d
0x18001708d  shl     ecx, 2
0x180017090  or      ecx, eax
0x180017092  shl     ecx, 2
0x180017095  or      ecx, edx
0x180017097  lea     edi, ds:0[rcx*8]
0x18001709e  test    r8d, r8d
0x1800170a1  jnz     short loc_1800170A8
0x1800170a3  mov     eax, r15d
0x1800170a6  jmp     short loc_1800170B2
0x1800170a8  xor     eax, eax
0x1800170aa  cmp     r8d, 2
0x1800170ae  cmovz   eax, r15d
0x1800170b2  or      edi, eax
0x1800170b4  mov     eax, [rbx]
0x1800170b6  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800170bb  mov     edx, eax
0x1800170bd  mov     [rbx], eax
0x1800170bf  jz      short loc_1800170EB
0x1800170c1  test    dl, 2
0x1800170c4  jnz     short loc_1800170EB
0x1800170c6  xor     eax, edi
0x1800170c8  and     eax, 180h
0x1800170cd  xor     eax, edx
0x1800170cf  mov     ecx, eax
0x1800170d1  xor     ecx, edi
0x1800170d3  and     ecx, r15d
0x1800170d6  xor     ecx, eax
0x1800170d8  or      ecx, 1
0x1800170db  mov     eax, ecx
0x1800170dd  xor     eax, edi
0x1800170df  and     eax, 800h
0x1800170e4  xor     eax, ecx
0x1800170e6  or      eax, 2
0x1800170e9  mov     [rbx], eax
0x1800170eb  mov     r8d, edx
0x1800170ee  mov     ecx, eax
0x1800170f0  and     r8d, 4
0x1800170f4  jnz     short loc_180017105
0x1800170f6  xor     ecx, edi
0x1800170f8  and     ecx, 400h
0x1800170fe  xor     ecx, eax
0x180017100  or      ecx, 4
0x180017103  mov     [rbx], ecx
0x180017105  mov     eax, edx
0x180017107  lock cmpxchg [rsi], ecx
0x18001710b  jnz     short loc_1800170B6
0x18001710d  test    r8d, r8d
0x180017110  jnz     short loc_180017122
0x180017112  mov     r8d, ebp
0x180017115  mov     edx, 3
0x18001711a  mov     rcx, rsi
0x18001711d  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180017122  test    byte ptr [rbx], 2
0x180017125  jnz     short loc_18001714B
0x180017127  mov     eax, [rbx]
0x180017129  xor     eax, edi
0x18001712b  and     eax, 180h
0x180017130  xor     eax, [rbx]
0x180017132  mov     ecx, eax
0x180017134  xor     ecx, edi
0x180017136  and     ecx, r15d
0x180017139  xor     ecx, eax
0x18001713b  or      ecx, 1
0x18001713e  mov     eax, ecx
0x180017140  xor     eax, edi
0x180017142  and     eax, 800h
0x180017147  xor     eax, ecx
0x180017149  mov     [rbx], eax
0x18001714b  mov     rbp, [rsp+38h+arg_10]
0x180017150  mov     rax, rbx
0x180017153  mov     rbx, [rsp+38h+arg_8]
0x180017158  add     rsp, 20h
0x18001715c  pop     r15
0x18001715e  pop     rdi
0x18001715f  pop     rsi
0x180017160  retn
```
