# wil::details::FeatureImpl<__WilFeatureTraits_Feature_DefaultOptionalToMini>::GetCachedFeatureEnabledState(void)

- ea: `0x140006814`
- end: `0x140006983`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_DefaultOptionalToMini@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `367`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140004e18`

## callees

- `0x140006724`
- `0x140006814`
- `0x14000a768`
- `0x14001e010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_DefaultOptionalToMini>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, _QWORD, wil::details **); // rax
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
  v3 = *(_DWORD *)Feature_DefaultOptionalToMini__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_DefaultOptionalToMini__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    v6 = 0;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(43997187, 0, &v14);
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
    if ( !v4 )
      LODWORD(v14) = 0;
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
      if ( (v11 & 4) != 0 )
      {
        v12 = v9;
      }
      else
      {
        v12 = v9 ^ ((unsigned __int16)v9 ^ (unsigned __int16)v8) & 0x400 | 4;
        *(_DWORD *)a2 = v12;
      }
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_DefaultOptionalToMini__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_DefaultOptionalToMini__descriptor, 0, v4);
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
0x140006814  mov     [rsp+arg_8], rbx
0x140006819  mov     [rsp+arg_10], rbp
0x14000681e  mov     [rsp+arg_0], rcx
0x140006823  push    rsi
0x140006824  push    rdi
0x140006825  push    r15
0x140006827  sub     rsp, 20h
0x14000682b  mov     rsi, cs:Feature_DefaultOptionalToMini__descriptor
0x140006832  mov     rbx, rdx
0x140006835  mov     qword ptr [rdx], 0
0x14000683c  mov     eax, [rsi]
0x14000683e  mov     [rdx], eax
0x140006840  and     eax, 6
0x140006843  cmp     al, 6
0x140006845  jz      loc_14000696D
0x14000684b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140006850  mov     ebp, eax
0x140006852  mov     dword ptr [rsp+38h+arg_0], 0
0x14000685a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140006861  xor     edx, edx
0x140006863  test    rax, rax
0x140006866  jnz     short loc_140006874
0x140006868  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x14000686f  test    rax, rax
0x140006872  jz      short loc_140006885
0x140006874  lea     r8, [rsp+38h+arg_0]
0x140006879  mov     ecx, 29F5803h
0x14000687e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006883  mov     edx, eax
0x140006885  mov     r8d, edx
0x140006888  mov     eax, edx
0x14000688a  and     r8d, 0FFFFFF3Fh
0x140006891  and     edx, 80h
0x140006897  mov     ecx, r8d
0x14000689a  mov     r15d, 40h ; '@'
0x1400068a0  and     ecx, 3
0x1400068a3  and     eax, r15d
0x1400068a6  shl     ecx, 2
0x1400068a9  or      ecx, eax
0x1400068ab  shl     ecx, 2
0x1400068ae  or      ecx, edx
0x1400068b0  lea     edi, ds:0[rcx*8]
0x1400068b7  test    r8d, r8d
0x1400068ba  jnz     short loc_1400068C1
0x1400068bc  mov     eax, r15d
0x1400068bf  jmp     short loc_1400068CB
0x1400068c1  xor     eax, eax
0x1400068c3  cmp     r8d, 2
0x1400068c7  cmovz   eax, r15d
0x1400068cb  or      edi, eax
0x1400068cd  test    ebp, ebp
0x1400068cf  jnz     short loc_1400068D5
0x1400068d1  mov     dword ptr [rsp+38h+arg_0], ebp
0x1400068d5  mov     eax, [rbx]
0x1400068d7  cmp     dword ptr [rsp+38h+arg_0], 0
0x1400068dc  mov     edx, eax
0x1400068de  mov     [rbx], eax
0x1400068e0  jz      short loc_14000690C
0x1400068e2  test    dl, 2
0x1400068e5  jnz     short loc_14000690C
0x1400068e7  xor     eax, edi
0x1400068e9  and     eax, 180h
0x1400068ee  xor     eax, edx
0x1400068f0  mov     ecx, eax
0x1400068f2  xor     ecx, edi
0x1400068f4  and     ecx, r15d
0x1400068f7  xor     ecx, eax
0x1400068f9  or      ecx, 1
0x1400068fc  mov     eax, ecx
0x1400068fe  xor     eax, edi
0x140006900  and     eax, 800h
0x140006905  xor     eax, ecx
0x140006907  or      eax, 2
0x14000690a  mov     [rbx], eax
0x14000690c  mov     r8d, edx
0x14000690f  and     r8d, 4
0x140006913  jnz     short loc_140006928
0x140006915  mov     ecx, edi
0x140006917  xor     ecx, eax
0x140006919  and     ecx, 400h
0x14000691f  xor     ecx, eax
0x140006921  or      ecx, 4
0x140006924  mov     [rbx], ecx
0x140006926  jmp     short loc_14000692A
0x140006928  mov     ecx, eax
0x14000692a  mov     eax, edx
0x14000692c  lock cmpxchg [rsi], ecx
0x140006930  jnz     short loc_1400068D7
0x140006932  test    r8d, r8d
0x140006935  jnz     short loc_140006944
0x140006937  mov     r8d, ebp
0x14000693a  xor     edx, edx
0x14000693c  mov     rcx, rsi
0x14000693f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140006944  test    byte ptr [rbx], 2
0x140006947  jnz     short loc_14000696D
0x140006949  mov     eax, [rbx]
0x14000694b  xor     eax, edi
0x14000694d  and     eax, 180h
0x140006952  xor     eax, [rbx]
0x140006954  mov     ecx, eax
0x140006956  xor     ecx, edi
0x140006958  and     ecx, r15d
0x14000695b  xor     ecx, eax
0x14000695d  or      ecx, 1
0x140006960  mov     eax, ecx
0x140006962  xor     eax, edi
0x140006964  and     eax, 800h
0x140006969  xor     eax, ecx
0x14000696b  mov     [rbx], eax
0x14000696d  mov     rbp, [rsp+38h+arg_10]
0x140006972  mov     rax, rbx
0x140006975  mov     rbx, [rsp+38h+arg_8]
0x14000697a  add     rsp, 20h
0x14000697e  pop     r15
0x140006980  pop     rdi
0x140006981  pop     rsi
0x140006982  retn
```
