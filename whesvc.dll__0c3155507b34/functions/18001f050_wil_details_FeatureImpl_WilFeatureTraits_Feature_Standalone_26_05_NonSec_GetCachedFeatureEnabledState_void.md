# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_05_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18001f050`
- end: `0x18001f1bd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_05_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001fff0`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x18001f050`
- `0x180029010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_05_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_05_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_05_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(58599563, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_05_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_26_05_NonSec__descriptor, 3, v4);
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
0x18001f050  mov     [rsp+arg_8], rbx
0x18001f055  mov     [rsp+arg_10], rbp
0x18001f05a  mov     [rsp+arg_0], rcx
0x18001f05f  push    rsi
0x18001f060  push    rdi
0x18001f061  push    r15
0x18001f063  sub     rsp, 20h
0x18001f067  mov     rsi, cs:Feature_Standalone_26_05_NonSec__descriptor
0x18001f06e  mov     rbx, rdx
0x18001f071  mov     qword ptr [rdx], 0
0x18001f078  mov     eax, [rsi]
0x18001f07a  mov     [rdx], eax
0x18001f07c  and     eax, 6
0x18001f07f  cmp     al, 6
0x18001f081  jz      loc_18001F1A7
0x18001f087  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001f08c  mov     ebp, eax
0x18001f08e  mov     dword ptr [rsp+38h+arg_0], 0
0x18001f096  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001f09d  test    rax, rax
0x18001f0a0  jz      short loc_18001F0BA
0x18001f0a2  lea     r8, [rsp+38h+arg_0]
0x18001f0a7  mov     edx, 3
0x18001f0ac  mov     ecx, 37E288Bh
0x18001f0b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0b6  mov     edx, eax
0x18001f0b8  jmp     short loc_18001F0C8
0x18001f0ba  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001f0c1  test    rax, rax
0x18001f0c4  jnz     short loc_18001F0A2
0x18001f0c6  xor     edx, edx
0x18001f0c8  mov     r8d, edx
0x18001f0cb  mov     eax, edx
0x18001f0cd  and     r8d, 0FFFFFF3Fh
0x18001f0d4  and     edx, 80h
0x18001f0da  mov     ecx, r8d
0x18001f0dd  mov     r15d, 40h ; '@'
0x18001f0e3  and     ecx, 3
0x18001f0e6  and     eax, r15d
0x18001f0e9  shl     ecx, 2
0x18001f0ec  or      ecx, eax
0x18001f0ee  shl     ecx, 2
0x18001f0f1  or      ecx, edx
0x18001f0f3  lea     edi, ds:0[rcx*8]
0x18001f0fa  test    r8d, r8d
0x18001f0fd  jnz     short loc_18001F104
0x18001f0ff  mov     eax, r15d
0x18001f102  jmp     short loc_18001F10E
0x18001f104  xor     eax, eax
0x18001f106  cmp     r8d, 2
0x18001f10a  cmovz   eax, r15d
0x18001f10e  or      edi, eax
0x18001f110  mov     eax, [rbx]
0x18001f112  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001f117  mov     edx, eax
0x18001f119  mov     [rbx], eax
0x18001f11b  jz      short loc_18001F147
0x18001f11d  test    dl, 2
0x18001f120  jnz     short loc_18001F147
0x18001f122  xor     eax, edi
0x18001f124  and     eax, 180h
0x18001f129  xor     eax, edx
0x18001f12b  mov     ecx, eax
0x18001f12d  xor     ecx, edi
0x18001f12f  and     ecx, r15d
0x18001f132  xor     ecx, eax
0x18001f134  or      ecx, 1
0x18001f137  mov     eax, ecx
0x18001f139  xor     eax, edi
0x18001f13b  and     eax, 800h
0x18001f140  xor     eax, ecx
0x18001f142  or      eax, 2
0x18001f145  mov     [rbx], eax
0x18001f147  mov     r8d, edx
0x18001f14a  mov     ecx, eax
0x18001f14c  and     r8d, 4
0x18001f150  jnz     short loc_18001F161
0x18001f152  xor     ecx, edi
0x18001f154  and     ecx, 400h
0x18001f15a  xor     ecx, eax
0x18001f15c  or      ecx, 4
0x18001f15f  mov     [rbx], ecx
0x18001f161  mov     eax, edx
0x18001f163  lock cmpxchg [rsi], ecx
0x18001f167  jnz     short loc_18001F112
0x18001f169  test    r8d, r8d
0x18001f16c  jnz     short loc_18001F17E
0x18001f16e  mov     r8d, ebp
0x18001f171  mov     edx, 3
0x18001f176  mov     rcx, rsi
0x18001f179  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001f17e  test    byte ptr [rbx], 2
0x18001f181  jnz     short loc_18001F1A7
0x18001f183  mov     eax, [rbx]
0x18001f185  xor     eax, edi
0x18001f187  and     eax, 180h
0x18001f18c  xor     eax, [rbx]
0x18001f18e  mov     ecx, eax
0x18001f190  xor     ecx, edi
0x18001f192  and     ecx, r15d
0x18001f195  xor     ecx, eax
0x18001f197  or      ecx, 1
0x18001f19a  mov     eax, ecx
0x18001f19c  xor     eax, edi
0x18001f19e  and     eax, 800h
0x18001f1a3  xor     eax, ecx
0x18001f1a5  mov     [rbx], eax
0x18001f1a7  mov     rbp, [rsp+38h+arg_10]
0x18001f1ac  mov     rax, rbx
0x18001f1af  mov     rbx, [rsp+38h+arg_8]
0x18001f1b4  add     rsp, 20h
0x18001f1b8  pop     r15
0x18001f1ba  pop     rdi
0x18001f1bb  pop     rsi
0x18001f1bc  retn
```
