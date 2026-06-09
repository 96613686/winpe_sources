# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x18001381c`
- end: `0x180013993`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014134`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x18001381c`
- `0x180029010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(57048226, 3, &v14);
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
            ^ ((unsigned __int16)v9
             ^ (unsigned __int16)v8)
            & 0x180
            ^ (v8
             ^ v9
             ^ ((unsigned __int16)v9
              ^ (unsigned __int16)v8)
             & 0x180)
            & 0x40
            | 1)
           ^ ((unsigned __int16)v8
            ^ ((unsigned __int16)(v9 ^ (v9 ^ v8) & 0x180 ^ (v8 ^ v9 ^ (v9 ^ v8) & 0x180) & 0x40) | 1))
           & 0x800
           | 2;
        *(_DWORD *)a2 = v9;
      }
      if ( (v11 & 4) != 0 )
      {
        v12 = v9;
      }
      else
      {
        v12 = v9 ^ ((unsigned __int16)v9 ^ (unsigned __int16)v8) & 0x400 | 4;
        *(_DWORD *)a2 = v12;
      }
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValLabTest__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_ValLabTest__descriptor, 3, v4);
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
0x18001381c  mov     [rsp+arg_8], rbx
0x180013821  mov     [rsp+arg_10], rbp
0x180013826  mov     [rsp+arg_0], rcx
0x18001382b  push    rsi
0x18001382c  push    rdi
0x18001382d  push    r15
0x18001382f  sub     rsp, 20h
0x180013833  mov     rsi, cs:Feature_ValLabTest__descriptor
0x18001383a  mov     rbx, rdx
0x18001383d  mov     qword ptr [rdx], 0
0x180013844  mov     eax, [rsi]
0x180013846  mov     [rdx], eax
0x180013848  and     eax, 6
0x18001384b  cmp     al, 6
0x18001384d  jz      loc_18001397D
0x180013853  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013858  mov     ebp, eax
0x18001385a  mov     dword ptr [rsp+38h+arg_0], 0
0x180013862  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180013869  test    rax, rax
0x18001386c  jz      short loc_180013886
0x18001386e  lea     r8, [rsp+38h+arg_0]
0x180013873  mov     edx, 3
0x180013878  mov     ecx, 3667CA2h
0x18001387d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013882  mov     edx, eax
0x180013884  jmp     short loc_180013894
0x180013886  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001388d  test    rax, rax
0x180013890  jnz     short loc_18001386E
0x180013892  xor     edx, edx
0x180013894  mov     r8d, edx
0x180013897  mov     eax, edx
0x180013899  and     r8d, 0FFFFFF3Fh
0x1800138a0  and     edx, 80h
0x1800138a6  mov     ecx, r8d
0x1800138a9  mov     r15d, 40h ; '@'
0x1800138af  and     ecx, 3
0x1800138b2  and     eax, r15d
0x1800138b5  shl     ecx, 2
0x1800138b8  or      ecx, eax
0x1800138ba  shl     ecx, 2
0x1800138bd  or      ecx, edx
0x1800138bf  lea     edi, ds:0[rcx*8]
0x1800138c6  test    r8d, r8d
0x1800138c9  jnz     short loc_1800138D0
0x1800138cb  mov     eax, r15d
0x1800138ce  jmp     short loc_1800138DA
0x1800138d0  xor     eax, eax
0x1800138d2  cmp     r8d, 2
0x1800138d6  cmovz   eax, r15d
0x1800138da  or      edi, eax
0x1800138dc  mov     eax, [rbx]
0x1800138de  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800138e3  mov     edx, eax
0x1800138e5  mov     [rbx], eax
0x1800138e7  jz      short loc_180013917
0x1800138e9  test    dl, 2
0x1800138ec  jnz     short loc_180013917
0x1800138ee  mov     eax, edi
0x1800138f0  xor     eax, edx
0x1800138f2  and     eax, 180h
0x1800138f7  xor     eax, edx
0x1800138f9  mov     ecx, eax
0x1800138fb  xor     ecx, edi
0x1800138fd  and     ecx, r15d
0x180013900  xor     ecx, eax
0x180013902  or      ecx, 1
0x180013905  mov     eax, ecx
0x180013907  xor     eax, edi
0x180013909  and     eax, 800h
0x18001390e  xor     eax, ecx
0x180013910  or      eax, 2
0x180013913  mov     [rbx], eax
0x180013915  jmp     short loc_180013919
0x180013917  mov     eax, edx
0x180013919  mov     r8d, edx
0x18001391c  and     r8d, 4
0x180013920  jnz     short loc_180013935
0x180013922  mov     ecx, edi
0x180013924  xor     ecx, eax
0x180013926  and     ecx, 400h
0x18001392c  xor     ecx, eax
0x18001392e  or      ecx, 4
0x180013931  mov     [rbx], ecx
0x180013933  jmp     short loc_180013937
0x180013935  mov     ecx, eax
0x180013937  mov     eax, edx
0x180013939  lock cmpxchg [rsi], ecx
0x18001393d  jnz     short loc_1800138DE
0x18001393f  test    r8d, r8d
0x180013942  jnz     short loc_180013954
0x180013944  mov     r8d, ebp
0x180013947  mov     edx, 3
0x18001394c  mov     rcx, rsi
0x18001394f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180013954  test    byte ptr [rbx], 2
0x180013957  jnz     short loc_18001397D
0x180013959  mov     eax, [rbx]
0x18001395b  xor     eax, edi
0x18001395d  and     eax, 180h
0x180013962  xor     eax, [rbx]
0x180013964  mov     ecx, eax
0x180013966  xor     ecx, edi
0x180013968  and     ecx, r15d
0x18001396b  xor     ecx, eax
0x18001396d  or      ecx, 1
0x180013970  mov     eax, ecx
0x180013972  xor     eax, edi
0x180013974  and     eax, 800h
0x180013979  xor     eax, ecx
0x18001397b  mov     [rbx], eax
0x18001397d  mov     rbp, [rsp+38h+arg_10]
0x180013982  mov     rax, rbx
0x180013985  mov     rbx, [rsp+38h+arg_8]
0x18001398a  add     rsp, 20h
0x18001398e  pop     r15
0x180013990  pop     rdi
0x180013991  pop     rsi
0x180013992  retn
```
