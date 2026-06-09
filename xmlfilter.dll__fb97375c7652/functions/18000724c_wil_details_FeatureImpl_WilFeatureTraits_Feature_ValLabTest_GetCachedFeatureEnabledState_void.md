# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x18000724c`
- end: `0x1800073c3`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007c40`

## callees

- `0x180005dd0`
- `0x18000724c`
- `0x18000c3f0`
- `0x180017010`

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
0x18000724c  mov     [rsp+arg_8], rbx
0x180007251  mov     [rsp+arg_10], rbp
0x180007256  mov     [rsp+arg_0], rcx
0x18000725b  push    rsi
0x18000725c  push    rdi
0x18000725d  push    r15
0x18000725f  sub     rsp, 20h
0x180007263  mov     rsi, cs:Feature_ValLabTest__descriptor
0x18000726a  mov     rbx, rdx
0x18000726d  mov     qword ptr [rdx], 0
0x180007274  mov     eax, [rsi]
0x180007276  mov     [rdx], eax
0x180007278  and     eax, 6
0x18000727b  cmp     al, 6
0x18000727d  jz      loc_1800073AD
0x180007283  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180007288  mov     ebp, eax
0x18000728a  mov     dword ptr [rsp+38h+arg_0], 0
0x180007292  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180007299  test    rax, rax
0x18000729c  jz      short loc_1800072B6
0x18000729e  lea     r8, [rsp+38h+arg_0]
0x1800072a3  mov     edx, 3
0x1800072a8  mov     ecx, 3667CA2h
0x1800072ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072b2  mov     edx, eax
0x1800072b4  jmp     short loc_1800072C4
0x1800072b6  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800072bd  test    rax, rax
0x1800072c0  jnz     short loc_18000729E
0x1800072c2  xor     edx, edx
0x1800072c4  mov     r8d, edx
0x1800072c7  mov     eax, edx
0x1800072c9  and     r8d, 0FFFFFF3Fh
0x1800072d0  and     edx, 80h
0x1800072d6  mov     ecx, r8d
0x1800072d9  mov     r15d, 40h ; '@'
0x1800072df  and     ecx, 3
0x1800072e2  and     eax, r15d
0x1800072e5  shl     ecx, 2
0x1800072e8  or      ecx, eax
0x1800072ea  shl     ecx, 2
0x1800072ed  or      ecx, edx
0x1800072ef  lea     edi, ds:0[rcx*8]
0x1800072f6  test    r8d, r8d
0x1800072f9  jnz     short loc_180007300
0x1800072fb  mov     eax, r15d
0x1800072fe  jmp     short loc_18000730A
0x180007300  xor     eax, eax
0x180007302  cmp     r8d, 2
0x180007306  cmovz   eax, r15d
0x18000730a  or      edi, eax
0x18000730c  mov     eax, [rbx]
0x18000730e  cmp     dword ptr [rsp+38h+arg_0], 0
0x180007313  mov     edx, eax
0x180007315  mov     [rbx], eax
0x180007317  jz      short loc_180007347
0x180007319  test    dl, 2
0x18000731c  jnz     short loc_180007347
0x18000731e  mov     eax, edi
0x180007320  xor     eax, edx
0x180007322  and     eax, 180h
0x180007327  xor     eax, edx
0x180007329  mov     ecx, eax
0x18000732b  xor     ecx, edi
0x18000732d  and     ecx, r15d
0x180007330  xor     ecx, eax
0x180007332  or      ecx, 1
0x180007335  mov     eax, ecx
0x180007337  xor     eax, edi
0x180007339  and     eax, 800h
0x18000733e  xor     eax, ecx
0x180007340  or      eax, 2
0x180007343  mov     [rbx], eax
0x180007345  jmp     short loc_180007349
0x180007347  mov     eax, edx
0x180007349  mov     r8d, edx
0x18000734c  and     r8d, 4
0x180007350  jnz     short loc_180007365
0x180007352  mov     ecx, edi
0x180007354  xor     ecx, eax
0x180007356  and     ecx, 400h
0x18000735c  xor     ecx, eax
0x18000735e  or      ecx, 4
0x180007361  mov     [rbx], ecx
0x180007363  jmp     short loc_180007367
0x180007365  mov     ecx, eax
0x180007367  mov     eax, edx
0x180007369  lock cmpxchg [rsi], ecx
0x18000736d  jnz     short loc_18000730E
0x18000736f  test    r8d, r8d
0x180007372  jnz     short loc_180007384
0x180007374  mov     r8d, ebp
0x180007377  mov     edx, 3
0x18000737c  mov     rcx, rsi
0x18000737f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180007384  test    byte ptr [rbx], 2
0x180007387  jnz     short loc_1800073AD
0x180007389  mov     eax, [rbx]
0x18000738b  xor     eax, edi
0x18000738d  and     eax, 180h
0x180007392  xor     eax, [rbx]
0x180007394  mov     ecx, eax
0x180007396  xor     ecx, edi
0x180007398  and     ecx, r15d
0x18000739b  xor     ecx, eax
0x18000739d  or      ecx, 1
0x1800073a0  mov     eax, ecx
0x1800073a2  xor     eax, edi
0x1800073a4  and     eax, 800h
0x1800073a9  xor     eax, ecx
0x1800073ab  mov     [rbx], eax
0x1800073ad  mov     rbp, [rsp+38h+arg_10]
0x1800073b2  mov     rax, rbx
0x1800073b5  mov     rbx, [rsp+38h+arg_8]
0x1800073ba  add     rsp, 20h
0x1800073be  pop     r15
0x1800073c0  pop     rdi
0x1800073c1  pop     rsi
0x1800073c2  retn
```
