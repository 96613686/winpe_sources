# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180017260`
- end: `0x1800173cd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018138`

## callees

- `0x180005cf8`
- `0x180009548`
- `0x180017260`
- `0x180033010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(45036792, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_25_10_NonSec__descriptor, 3, v4);
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
0x180017260  mov     [rsp+arg_8], rbx
0x180017265  mov     [rsp+arg_10], rbp
0x18001726a  mov     [rsp+arg_0], rcx
0x18001726f  push    rsi
0x180017270  push    rdi
0x180017271  push    r15
0x180017273  sub     rsp, 20h
0x180017277  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x18001727e  mov     rbx, rdx
0x180017281  mov     qword ptr [rdx], 0
0x180017288  mov     eax, [rsi]
0x18001728a  mov     [rdx], eax
0x18001728c  and     eax, 6
0x18001728f  cmp     al, 6
0x180017291  jz      loc_1800173B7
0x180017297  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001729c  mov     ebp, eax
0x18001729e  mov     dword ptr [rsp+38h+arg_0], 0
0x1800172a6  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800172ad  test    rax, rax
0x1800172b0  jz      short loc_1800172CA
0x1800172b2  lea     r8, [rsp+38h+arg_0]
0x1800172b7  mov     edx, 3
0x1800172bc  mov     ecx, 2AF34F8h
0x1800172c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172c6  mov     edx, eax
0x1800172c8  jmp     short loc_1800172D8
0x1800172ca  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800172d1  test    rax, rax
0x1800172d4  jnz     short loc_1800172B2
0x1800172d6  xor     edx, edx
0x1800172d8  mov     r8d, edx
0x1800172db  mov     eax, edx
0x1800172dd  and     r8d, 0FFFFFF3Fh
0x1800172e4  and     edx, 80h
0x1800172ea  mov     ecx, r8d
0x1800172ed  mov     r15d, 40h ; '@'
0x1800172f3  and     ecx, 3
0x1800172f6  and     eax, r15d
0x1800172f9  shl     ecx, 2
0x1800172fc  or      ecx, eax
0x1800172fe  shl     ecx, 2
0x180017301  or      ecx, edx
0x180017303  lea     edi, ds:0[rcx*8]
0x18001730a  test    r8d, r8d
0x18001730d  jnz     short loc_180017314
0x18001730f  mov     eax, r15d
0x180017312  jmp     short loc_18001731E
0x180017314  xor     eax, eax
0x180017316  cmp     r8d, 2
0x18001731a  cmovz   eax, r15d
0x18001731e  or      edi, eax
0x180017320  mov     eax, [rbx]
0x180017322  cmp     dword ptr [rsp+38h+arg_0], 0
0x180017327  mov     edx, eax
0x180017329  mov     [rbx], eax
0x18001732b  jz      short loc_180017357
0x18001732d  test    dl, 2
0x180017330  jnz     short loc_180017357
0x180017332  xor     eax, edi
0x180017334  and     eax, 180h
0x180017339  xor     eax, edx
0x18001733b  mov     ecx, eax
0x18001733d  xor     ecx, edi
0x18001733f  and     ecx, r15d
0x180017342  xor     ecx, eax
0x180017344  or      ecx, 1
0x180017347  mov     eax, ecx
0x180017349  xor     eax, edi
0x18001734b  and     eax, 800h
0x180017350  xor     eax, ecx
0x180017352  or      eax, 2
0x180017355  mov     [rbx], eax
0x180017357  mov     r8d, edx
0x18001735a  mov     ecx, eax
0x18001735c  and     r8d, 4
0x180017360  jnz     short loc_180017371
0x180017362  xor     ecx, edi
0x180017364  and     ecx, 400h
0x18001736a  xor     ecx, eax
0x18001736c  or      ecx, 4
0x18001736f  mov     [rbx], ecx
0x180017371  mov     eax, edx
0x180017373  lock cmpxchg [rsi], ecx
0x180017377  jnz     short loc_180017322
0x180017379  test    r8d, r8d
0x18001737c  jnz     short loc_18001738E
0x18001737e  mov     r8d, ebp
0x180017381  mov     edx, 3
0x180017386  mov     rcx, rsi
0x180017389  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001738e  test    byte ptr [rbx], 2
0x180017391  jnz     short loc_1800173B7
0x180017393  mov     eax, [rbx]
0x180017395  xor     eax, edi
0x180017397  and     eax, 180h
0x18001739c  xor     eax, [rbx]
0x18001739e  mov     ecx, eax
0x1800173a0  xor     ecx, edi
0x1800173a2  and     ecx, r15d
0x1800173a5  xor     ecx, eax
0x1800173a7  or      ecx, 1
0x1800173aa  mov     eax, ecx
0x1800173ac  xor     eax, edi
0x1800173ae  and     eax, 800h
0x1800173b3  xor     eax, ecx
0x1800173b5  mov     [rbx], eax
0x1800173b7  mov     rbp, [rsp+38h+arg_10]
0x1800173bc  mov     rax, rbx
0x1800173bf  mov     rbx, [rsp+38h+arg_8]
0x1800173c4  add     rsp, 20h
0x1800173c8  pop     r15
0x1800173ca  pop     rdi
0x1800173cb  pop     rsi
0x1800173cc  retn
```
