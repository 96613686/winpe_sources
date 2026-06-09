# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x1800172dc`
- end: `0x180017449`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017df8`

## callees

- `0x180016be8`
- `0x1800172dc`
- `0x180018da4`
- `0x18001e010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(58599550, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_26_02_NonSec__descriptor, 3, v4);
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
0x1800172dc  mov     [rsp+arg_8], rbx
0x1800172e1  mov     [rsp+arg_10], rbp
0x1800172e6  mov     [rsp+arg_0], rcx
0x1800172eb  push    rsi
0x1800172ec  push    rdi
0x1800172ed  push    r15
0x1800172ef  sub     rsp, 20h
0x1800172f3  mov     rsi, cs:Feature_Standalone_26_02_NonSec__descriptor
0x1800172fa  mov     rbx, rdx
0x1800172fd  mov     qword ptr [rdx], 0
0x180017304  mov     eax, [rsi]
0x180017306  mov     [rdx], eax
0x180017308  and     eax, 6
0x18001730b  cmp     al, 6
0x18001730d  jz      loc_180017433
0x180017313  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180017318  mov     ebp, eax
0x18001731a  mov     dword ptr [rsp+38h+arg_0], 0
0x180017322  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180017329  test    rax, rax
0x18001732c  jz      short loc_180017346
0x18001732e  lea     r8, [rsp+38h+arg_0]
0x180017333  mov     edx, 3
0x180017338  mov     ecx, 37E287Eh
0x18001733d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017342  mov     edx, eax
0x180017344  jmp     short loc_180017354
0x180017346  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001734d  test    rax, rax
0x180017350  jnz     short loc_18001732E
0x180017352  xor     edx, edx
0x180017354  mov     r8d, edx
0x180017357  mov     eax, edx
0x180017359  and     r8d, 0FFFFFF3Fh
0x180017360  and     edx, 80h
0x180017366  mov     ecx, r8d
0x180017369  mov     r15d, 40h ; '@'
0x18001736f  and     ecx, 3
0x180017372  and     eax, r15d
0x180017375  shl     ecx, 2
0x180017378  or      ecx, eax
0x18001737a  shl     ecx, 2
0x18001737d  or      ecx, edx
0x18001737f  lea     edi, ds:0[rcx*8]
0x180017386  test    r8d, r8d
0x180017389  jnz     short loc_180017390
0x18001738b  mov     eax, r15d
0x18001738e  jmp     short loc_18001739A
0x180017390  xor     eax, eax
0x180017392  cmp     r8d, 2
0x180017396  cmovz   eax, r15d
0x18001739a  or      edi, eax
0x18001739c  mov     eax, [rbx]
0x18001739e  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800173a3  mov     edx, eax
0x1800173a5  mov     [rbx], eax
0x1800173a7  jz      short loc_1800173D3
0x1800173a9  test    dl, 2
0x1800173ac  jnz     short loc_1800173D3
0x1800173ae  xor     eax, edi
0x1800173b0  and     eax, 180h
0x1800173b5  xor     eax, edx
0x1800173b7  mov     ecx, eax
0x1800173b9  xor     ecx, edi
0x1800173bb  and     ecx, r15d
0x1800173be  xor     ecx, eax
0x1800173c0  or      ecx, 1
0x1800173c3  mov     eax, ecx
0x1800173c5  xor     eax, edi
0x1800173c7  and     eax, 800h
0x1800173cc  xor     eax, ecx
0x1800173ce  or      eax, 2
0x1800173d1  mov     [rbx], eax
0x1800173d3  mov     r8d, edx
0x1800173d6  mov     ecx, eax
0x1800173d8  and     r8d, 4
0x1800173dc  jnz     short loc_1800173ED
0x1800173de  xor     ecx, edi
0x1800173e0  and     ecx, 400h
0x1800173e6  xor     ecx, eax
0x1800173e8  or      ecx, 4
0x1800173eb  mov     [rbx], ecx
0x1800173ed  mov     eax, edx
0x1800173ef  lock cmpxchg [rsi], ecx
0x1800173f3  jnz     short loc_18001739E
0x1800173f5  test    r8d, r8d
0x1800173f8  jnz     short loc_18001740A
0x1800173fa  mov     r8d, ebp
0x1800173fd  mov     edx, 3
0x180017402  mov     rcx, rsi
0x180017405  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001740a  test    byte ptr [rbx], 2
0x18001740d  jnz     short loc_180017433
0x18001740f  mov     eax, [rbx]
0x180017411  xor     eax, edi
0x180017413  and     eax, 180h
0x180017418  xor     eax, [rbx]
0x18001741a  mov     ecx, eax
0x18001741c  xor     ecx, edi
0x18001741e  and     ecx, r15d
0x180017421  xor     ecx, eax
0x180017423  or      ecx, 1
0x180017426  mov     eax, ecx
0x180017428  xor     eax, edi
0x18001742a  and     eax, 800h
0x18001742f  xor     eax, ecx
0x180017431  mov     [rbx], eax
0x180017433  mov     rbp, [rsp+38h+arg_10]
0x180017438  mov     rax, rbx
0x18001743b  mov     rbx, [rsp+38h+arg_8]
0x180017440  add     rsp, 20h
0x180017444  pop     r15
0x180017446  pop     rdi
0x180017447  pop     rsi
0x180017448  retn
```
