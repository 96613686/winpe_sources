# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_04_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180013168`
- end: `0x1800132d5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_04_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013e54`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x180013168`
- `0x180029010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_04_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_04_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_04_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(58599559, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_04_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_26_04_NonSec__descriptor, 3, v4);
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
0x180013168  mov     [rsp+arg_8], rbx
0x18001316d  mov     [rsp+arg_10], rbp
0x180013172  mov     [rsp+arg_0], rcx
0x180013177  push    rsi
0x180013178  push    rdi
0x180013179  push    r15
0x18001317b  sub     rsp, 20h
0x18001317f  mov     rsi, cs:Feature_Standalone_26_04_NonSec__descriptor
0x180013186  mov     rbx, rdx
0x180013189  mov     qword ptr [rdx], 0
0x180013190  mov     eax, [rsi]
0x180013192  mov     [rdx], eax
0x180013194  and     eax, 6
0x180013197  cmp     al, 6
0x180013199  jz      loc_1800132BF
0x18001319f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800131a4  mov     ebp, eax
0x1800131a6  mov     dword ptr [rsp+38h+arg_0], 0
0x1800131ae  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800131b5  test    rax, rax
0x1800131b8  jz      short loc_1800131D2
0x1800131ba  lea     r8, [rsp+38h+arg_0]
0x1800131bf  mov     edx, 3
0x1800131c4  mov     ecx, 37E2887h
0x1800131c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131ce  mov     edx, eax
0x1800131d0  jmp     short loc_1800131E0
0x1800131d2  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800131d9  test    rax, rax
0x1800131dc  jnz     short loc_1800131BA
0x1800131de  xor     edx, edx
0x1800131e0  mov     r8d, edx
0x1800131e3  mov     eax, edx
0x1800131e5  and     r8d, 0FFFFFF3Fh
0x1800131ec  and     edx, 80h
0x1800131f2  mov     ecx, r8d
0x1800131f5  mov     r15d, 40h ; '@'
0x1800131fb  and     ecx, 3
0x1800131fe  and     eax, r15d
0x180013201  shl     ecx, 2
0x180013204  or      ecx, eax
0x180013206  shl     ecx, 2
0x180013209  or      ecx, edx
0x18001320b  lea     edi, ds:0[rcx*8]
0x180013212  test    r8d, r8d
0x180013215  jnz     short loc_18001321C
0x180013217  mov     eax, r15d
0x18001321a  jmp     short loc_180013226
0x18001321c  xor     eax, eax
0x18001321e  cmp     r8d, 2
0x180013222  cmovz   eax, r15d
0x180013226  or      edi, eax
0x180013228  mov     eax, [rbx]
0x18001322a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001322f  mov     edx, eax
0x180013231  mov     [rbx], eax
0x180013233  jz      short loc_18001325F
0x180013235  test    dl, 2
0x180013238  jnz     short loc_18001325F
0x18001323a  xor     eax, edi
0x18001323c  and     eax, 180h
0x180013241  xor     eax, edx
0x180013243  mov     ecx, eax
0x180013245  xor     ecx, edi
0x180013247  and     ecx, r15d
0x18001324a  xor     ecx, eax
0x18001324c  or      ecx, 1
0x18001324f  mov     eax, ecx
0x180013251  xor     eax, edi
0x180013253  and     eax, 800h
0x180013258  xor     eax, ecx
0x18001325a  or      eax, 2
0x18001325d  mov     [rbx], eax
0x18001325f  mov     r8d, edx
0x180013262  mov     ecx, eax
0x180013264  and     r8d, 4
0x180013268  jnz     short loc_180013279
0x18001326a  xor     ecx, edi
0x18001326c  and     ecx, 400h
0x180013272  xor     ecx, eax
0x180013274  or      ecx, 4
0x180013277  mov     [rbx], ecx
0x180013279  mov     eax, edx
0x18001327b  lock cmpxchg [rsi], ecx
0x18001327f  jnz     short loc_18001322A
0x180013281  test    r8d, r8d
0x180013284  jnz     short loc_180013296
0x180013286  mov     r8d, ebp
0x180013289  mov     edx, 3
0x18001328e  mov     rcx, rsi
0x180013291  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180013296  test    byte ptr [rbx], 2
0x180013299  jnz     short loc_1800132BF
0x18001329b  mov     eax, [rbx]
0x18001329d  xor     eax, edi
0x18001329f  and     eax, 180h
0x1800132a4  xor     eax, [rbx]
0x1800132a6  mov     ecx, eax
0x1800132a8  xor     ecx, edi
0x1800132aa  and     ecx, r15d
0x1800132ad  xor     ecx, eax
0x1800132af  or      ecx, 1
0x1800132b2  mov     eax, ecx
0x1800132b4  xor     eax, edi
0x1800132b6  and     eax, 800h
0x1800132bb  xor     eax, ecx
0x1800132bd  mov     [rbx], eax
0x1800132bf  mov     rbp, [rsp+38h+arg_10]
0x1800132c4  mov     rax, rbx
0x1800132c7  mov     rbx, [rsp+38h+arg_8]
0x1800132cc  add     rsp, 20h
0x1800132d0  pop     r15
0x1800132d2  pop     rdi
0x1800132d3  pop     rsi
0x1800132d4  retn
```
