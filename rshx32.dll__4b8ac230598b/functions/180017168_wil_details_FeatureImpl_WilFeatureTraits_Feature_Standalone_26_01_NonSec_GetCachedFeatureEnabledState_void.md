# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180017168`
- end: `0x1800172d5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800180d8`

## callees

- `0x180016be8`
- `0x180017168`
- `0x180018da4`
- `0x18001e010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(58599532, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_26_01_NonSec__descriptor, 3, v4);
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
0x180017168  mov     [rsp+arg_8], rbx
0x18001716d  mov     [rsp+arg_10], rbp
0x180017172  mov     [rsp+arg_0], rcx
0x180017177  push    rsi
0x180017178  push    rdi
0x180017179  push    r15
0x18001717b  sub     rsp, 20h
0x18001717f  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x180017186  mov     rbx, rdx
0x180017189  mov     qword ptr [rdx], 0
0x180017190  mov     eax, [rsi]
0x180017192  mov     [rdx], eax
0x180017194  and     eax, 6
0x180017197  cmp     al, 6
0x180017199  jz      loc_1800172BF
0x18001719f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800171a4  mov     ebp, eax
0x1800171a6  mov     dword ptr [rsp+38h+arg_0], 0
0x1800171ae  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800171b5  test    rax, rax
0x1800171b8  jz      short loc_1800171D2
0x1800171ba  lea     r8, [rsp+38h+arg_0]
0x1800171bf  mov     edx, 3
0x1800171c4  mov     ecx, 37E286Ch
0x1800171c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171ce  mov     edx, eax
0x1800171d0  jmp     short loc_1800171E0
0x1800171d2  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800171d9  test    rax, rax
0x1800171dc  jnz     short loc_1800171BA
0x1800171de  xor     edx, edx
0x1800171e0  mov     r8d, edx
0x1800171e3  mov     eax, edx
0x1800171e5  and     r8d, 0FFFFFF3Fh
0x1800171ec  and     edx, 80h
0x1800171f2  mov     ecx, r8d
0x1800171f5  mov     r15d, 40h ; '@'
0x1800171fb  and     ecx, 3
0x1800171fe  and     eax, r15d
0x180017201  shl     ecx, 2
0x180017204  or      ecx, eax
0x180017206  shl     ecx, 2
0x180017209  or      ecx, edx
0x18001720b  lea     edi, ds:0[rcx*8]
0x180017212  test    r8d, r8d
0x180017215  jnz     short loc_18001721C
0x180017217  mov     eax, r15d
0x18001721a  jmp     short loc_180017226
0x18001721c  xor     eax, eax
0x18001721e  cmp     r8d, 2
0x180017222  cmovz   eax, r15d
0x180017226  or      edi, eax
0x180017228  mov     eax, [rbx]
0x18001722a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001722f  mov     edx, eax
0x180017231  mov     [rbx], eax
0x180017233  jz      short loc_18001725F
0x180017235  test    dl, 2
0x180017238  jnz     short loc_18001725F
0x18001723a  xor     eax, edi
0x18001723c  and     eax, 180h
0x180017241  xor     eax, edx
0x180017243  mov     ecx, eax
0x180017245  xor     ecx, edi
0x180017247  and     ecx, r15d
0x18001724a  xor     ecx, eax
0x18001724c  or      ecx, 1
0x18001724f  mov     eax, ecx
0x180017251  xor     eax, edi
0x180017253  and     eax, 800h
0x180017258  xor     eax, ecx
0x18001725a  or      eax, 2
0x18001725d  mov     [rbx], eax
0x18001725f  mov     r8d, edx
0x180017262  mov     ecx, eax
0x180017264  and     r8d, 4
0x180017268  jnz     short loc_180017279
0x18001726a  xor     ecx, edi
0x18001726c  and     ecx, 400h
0x180017272  xor     ecx, eax
0x180017274  or      ecx, 4
0x180017277  mov     [rbx], ecx
0x180017279  mov     eax, edx
0x18001727b  lock cmpxchg [rsi], ecx
0x18001727f  jnz     short loc_18001722A
0x180017281  test    r8d, r8d
0x180017284  jnz     short loc_180017296
0x180017286  mov     r8d, ebp
0x180017289  mov     edx, 3
0x18001728e  mov     rcx, rsi
0x180017291  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180017296  test    byte ptr [rbx], 2
0x180017299  jnz     short loc_1800172BF
0x18001729b  mov     eax, [rbx]
0x18001729d  xor     eax, edi
0x18001729f  and     eax, 180h
0x1800172a4  xor     eax, [rbx]
0x1800172a6  mov     ecx, eax
0x1800172a8  xor     ecx, edi
0x1800172aa  and     ecx, r15d
0x1800172ad  xor     ecx, eax
0x1800172af  or      ecx, 1
0x1800172b2  mov     eax, ecx
0x1800172b4  xor     eax, edi
0x1800172b6  and     eax, 800h
0x1800172bb  xor     eax, ecx
0x1800172bd  mov     [rbx], eax
0x1800172bf  mov     rbp, [rsp+38h+arg_10]
0x1800172c4  mov     rax, rbx
0x1800172c7  mov     rbx, [rsp+38h+arg_8]
0x1800172cc  add     rsp, 20h
0x1800172d0  pop     r15
0x1800172d2  pop     rdi
0x1800172d3  pop     rsi
0x1800172d4  retn
```
