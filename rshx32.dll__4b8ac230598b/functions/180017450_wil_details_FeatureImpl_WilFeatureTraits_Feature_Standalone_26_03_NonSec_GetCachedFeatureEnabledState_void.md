# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180017450`
- end: `0x1800175bd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800183b8`

## callees

- `0x180016be8`
- `0x180017450`
- `0x180018da4`
- `0x18001e010`

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
0x180017450  mov     [rsp+arg_8], rbx
0x180017455  mov     [rsp+arg_10], rbp
0x18001745a  mov     [rsp+arg_0], rcx
0x18001745f  push    rsi
0x180017460  push    rdi
0x180017461  push    r15
0x180017463  sub     rsp, 20h
0x180017467  mov     rsi, cs:Feature_Standalone_26_03_NonSec__descriptor
0x18001746e  mov     rbx, rdx
0x180017471  mov     qword ptr [rdx], 0
0x180017478  mov     eax, [rsi]
0x18001747a  mov     [rdx], eax
0x18001747c  and     eax, 6
0x18001747f  cmp     al, 6
0x180017481  jz      loc_1800175A7
0x180017487  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001748c  mov     ebp, eax
0x18001748e  mov     dword ptr [rsp+38h+arg_0], 0
0x180017496  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001749d  test    rax, rax
0x1800174a0  jz      short loc_1800174BA
0x1800174a2  lea     r8, [rsp+38h+arg_0]
0x1800174a7  mov     edx, 3
0x1800174ac  mov     ecx, 37E2881h
0x1800174b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174b6  mov     edx, eax
0x1800174b8  jmp     short loc_1800174C8
0x1800174ba  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800174c1  test    rax, rax
0x1800174c4  jnz     short loc_1800174A2
0x1800174c6  xor     edx, edx
0x1800174c8  mov     r8d, edx
0x1800174cb  mov     eax, edx
0x1800174cd  and     r8d, 0FFFFFF3Fh
0x1800174d4  and     edx, 80h
0x1800174da  mov     ecx, r8d
0x1800174dd  mov     r15d, 40h ; '@'
0x1800174e3  and     ecx, 3
0x1800174e6  and     eax, r15d
0x1800174e9  shl     ecx, 2
0x1800174ec  or      ecx, eax
0x1800174ee  shl     ecx, 2
0x1800174f1  or      ecx, edx
0x1800174f3  lea     edi, ds:0[rcx*8]
0x1800174fa  test    r8d, r8d
0x1800174fd  jnz     short loc_180017504
0x1800174ff  mov     eax, r15d
0x180017502  jmp     short loc_18001750E
0x180017504  xor     eax, eax
0x180017506  cmp     r8d, 2
0x18001750a  cmovz   eax, r15d
0x18001750e  or      edi, eax
0x180017510  mov     eax, [rbx]
0x180017512  cmp     dword ptr [rsp+38h+arg_0], 0
0x180017517  mov     edx, eax
0x180017519  mov     [rbx], eax
0x18001751b  jz      short loc_180017547
0x18001751d  test    dl, 2
0x180017520  jnz     short loc_180017547
0x180017522  xor     eax, edi
0x180017524  and     eax, 180h
0x180017529  xor     eax, edx
0x18001752b  mov     ecx, eax
0x18001752d  xor     ecx, edi
0x18001752f  and     ecx, r15d
0x180017532  xor     ecx, eax
0x180017534  or      ecx, 1
0x180017537  mov     eax, ecx
0x180017539  xor     eax, edi
0x18001753b  and     eax, 800h
0x180017540  xor     eax, ecx
0x180017542  or      eax, 2
0x180017545  mov     [rbx], eax
0x180017547  mov     r8d, edx
0x18001754a  mov     ecx, eax
0x18001754c  and     r8d, 4
0x180017550  jnz     short loc_180017561
0x180017552  xor     ecx, edi
0x180017554  and     ecx, 400h
0x18001755a  xor     ecx, eax
0x18001755c  or      ecx, 4
0x18001755f  mov     [rbx], ecx
0x180017561  mov     eax, edx
0x180017563  lock cmpxchg [rsi], ecx
0x180017567  jnz     short loc_180017512
0x180017569  test    r8d, r8d
0x18001756c  jnz     short loc_18001757E
0x18001756e  mov     r8d, ebp
0x180017571  mov     edx, 3
0x180017576  mov     rcx, rsi
0x180017579  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001757e  test    byte ptr [rbx], 2
0x180017581  jnz     short loc_1800175A7
0x180017583  mov     eax, [rbx]
0x180017585  xor     eax, edi
0x180017587  and     eax, 180h
0x18001758c  xor     eax, [rbx]
0x18001758e  mov     ecx, eax
0x180017590  xor     ecx, edi
0x180017592  and     ecx, r15d
0x180017595  xor     ecx, eax
0x180017597  or      ecx, 1
0x18001759a  mov     eax, ecx
0x18001759c  xor     eax, edi
0x18001759e  and     eax, 800h
0x1800175a3  xor     eax, ecx
0x1800175a5  mov     [rbx], eax
0x1800175a7  mov     rbp, [rsp+38h+arg_10]
0x1800175ac  mov     rax, rbx
0x1800175af  mov     rbx, [rsp+38h+arg_8]
0x1800175b4  add     rsp, 20h
0x1800175b8  pop     r15
0x1800175ba  pop     rdi
0x1800175bb  pop     rsi
0x1800175bc  retn
```
