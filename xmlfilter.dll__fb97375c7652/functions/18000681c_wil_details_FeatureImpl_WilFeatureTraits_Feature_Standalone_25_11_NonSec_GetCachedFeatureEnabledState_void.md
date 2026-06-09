# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000681c`
- end: `0x180006989`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800077f0`

## callees

- `0x180005dd0`
- `0x18000681c`
- `0x18000c3f0`
- `0x180017010`

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
0x18000681c  mov     [rsp+arg_8], rbx
0x180006821  mov     [rsp+arg_10], rbp
0x180006826  mov     [rsp+arg_0], rcx
0x18000682b  push    rsi
0x18000682c  push    rdi
0x18000682d  push    r15
0x18000682f  sub     rsp, 20h
0x180006833  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x18000683a  mov     rbx, rdx
0x18000683d  mov     qword ptr [rdx], 0
0x180006844  mov     eax, [rsi]
0x180006846  mov     [rdx], eax
0x180006848  and     eax, 6
0x18000684b  cmp     al, 6
0x18000684d  jz      loc_180006973
0x180006853  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180006858  mov     ebp, eax
0x18000685a  mov     dword ptr [rsp+38h+arg_0], 0
0x180006862  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180006869  test    rax, rax
0x18000686c  jz      short loc_180006886
0x18000686e  lea     r8, [rsp+38h+arg_0]
0x180006873  mov     edx, 3
0x180006878  mov     ecx, 2AF34FDh
0x18000687d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006882  mov     edx, eax
0x180006884  jmp     short loc_180006894
0x180006886  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000688d  test    rax, rax
0x180006890  jnz     short loc_18000686E
0x180006892  xor     edx, edx
0x180006894  mov     r8d, edx
0x180006897  mov     eax, edx
0x180006899  and     r8d, 0FFFFFF3Fh
0x1800068a0  and     edx, 80h
0x1800068a6  mov     ecx, r8d
0x1800068a9  mov     r15d, 40h ; '@'
0x1800068af  and     ecx, 3
0x1800068b2  and     eax, r15d
0x1800068b5  shl     ecx, 2
0x1800068b8  or      ecx, eax
0x1800068ba  shl     ecx, 2
0x1800068bd  or      ecx, edx
0x1800068bf  lea     edi, ds:0[rcx*8]
0x1800068c6  test    r8d, r8d
0x1800068c9  jnz     short loc_1800068D0
0x1800068cb  mov     eax, r15d
0x1800068ce  jmp     short loc_1800068DA
0x1800068d0  xor     eax, eax
0x1800068d2  cmp     r8d, 2
0x1800068d6  cmovz   eax, r15d
0x1800068da  or      edi, eax
0x1800068dc  mov     eax, [rbx]
0x1800068de  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800068e3  mov     edx, eax
0x1800068e5  mov     [rbx], eax
0x1800068e7  jz      short loc_180006913
0x1800068e9  test    dl, 2
0x1800068ec  jnz     short loc_180006913
0x1800068ee  xor     eax, edi
0x1800068f0  and     eax, 180h
0x1800068f5  xor     eax, edx
0x1800068f7  mov     ecx, eax
0x1800068f9  xor     ecx, edi
0x1800068fb  and     ecx, r15d
0x1800068fe  xor     ecx, eax
0x180006900  or      ecx, 1
0x180006903  mov     eax, ecx
0x180006905  xor     eax, edi
0x180006907  and     eax, 800h
0x18000690c  xor     eax, ecx
0x18000690e  or      eax, 2
0x180006911  mov     [rbx], eax
0x180006913  mov     r8d, edx
0x180006916  mov     ecx, eax
0x180006918  and     r8d, 4
0x18000691c  jnz     short loc_18000692D
0x18000691e  xor     ecx, edi
0x180006920  and     ecx, 400h
0x180006926  xor     ecx, eax
0x180006928  or      ecx, 4
0x18000692b  mov     [rbx], ecx
0x18000692d  mov     eax, edx
0x18000692f  lock cmpxchg [rsi], ecx
0x180006933  jnz     short loc_1800068DE
0x180006935  test    r8d, r8d
0x180006938  jnz     short loc_18000694A
0x18000693a  mov     r8d, ebp
0x18000693d  mov     edx, 3
0x180006942  mov     rcx, rsi
0x180006945  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000694a  test    byte ptr [rbx], 2
0x18000694d  jnz     short loc_180006973
0x18000694f  mov     eax, [rbx]
0x180006951  xor     eax, edi
0x180006953  and     eax, 180h
0x180006958  xor     eax, [rbx]
0x18000695a  mov     ecx, eax
0x18000695c  xor     ecx, edi
0x18000695e  and     ecx, r15d
0x180006961  xor     ecx, eax
0x180006963  or      ecx, 1
0x180006966  mov     eax, ecx
0x180006968  xor     eax, edi
0x18000696a  and     eax, 800h
0x18000696f  xor     eax, ecx
0x180006971  mov     [rbx], eax
0x180006973  mov     rbp, [rsp+38h+arg_10]
0x180006978  mov     rax, rbx
0x18000697b  mov     rbx, [rsp+38h+arg_8]
0x180006980  add     rsp, 20h
0x180006984  pop     r15
0x180006986  pop     rdi
0x180006987  pop     rsi
0x180006988  retn
```
