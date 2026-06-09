# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180012ff4`
- end: `0x180013161`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013fc4`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x180012ff4`
- `0x180029010`

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
0x180012ff4  mov     [rsp+arg_8], rbx
0x180012ff9  mov     [rsp+arg_10], rbp
0x180012ffe  mov     [rsp+arg_0], rcx
0x180013003  push    rsi
0x180013004  push    rdi
0x180013005  push    r15
0x180013007  sub     rsp, 20h
0x18001300b  mov     rsi, cs:Feature_Standalone_26_03_NonSec__descriptor
0x180013012  mov     rbx, rdx
0x180013015  mov     qword ptr [rdx], 0
0x18001301c  mov     eax, [rsi]
0x18001301e  mov     [rdx], eax
0x180013020  and     eax, 6
0x180013023  cmp     al, 6
0x180013025  jz      loc_18001314B
0x18001302b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013030  mov     ebp, eax
0x180013032  mov     dword ptr [rsp+38h+arg_0], 0
0x18001303a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180013041  test    rax, rax
0x180013044  jz      short loc_18001305E
0x180013046  lea     r8, [rsp+38h+arg_0]
0x18001304b  mov     edx, 3
0x180013050  mov     ecx, 37E2881h
0x180013055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001305a  mov     edx, eax
0x18001305c  jmp     short loc_18001306C
0x18001305e  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180013065  test    rax, rax
0x180013068  jnz     short loc_180013046
0x18001306a  xor     edx, edx
0x18001306c  mov     r8d, edx
0x18001306f  mov     eax, edx
0x180013071  and     r8d, 0FFFFFF3Fh
0x180013078  and     edx, 80h
0x18001307e  mov     ecx, r8d
0x180013081  mov     r15d, 40h ; '@'
0x180013087  and     ecx, 3
0x18001308a  and     eax, r15d
0x18001308d  shl     ecx, 2
0x180013090  or      ecx, eax
0x180013092  shl     ecx, 2
0x180013095  or      ecx, edx
0x180013097  lea     edi, ds:0[rcx*8]
0x18001309e  test    r8d, r8d
0x1800130a1  jnz     short loc_1800130A8
0x1800130a3  mov     eax, r15d
0x1800130a6  jmp     short loc_1800130B2
0x1800130a8  xor     eax, eax
0x1800130aa  cmp     r8d, 2
0x1800130ae  cmovz   eax, r15d
0x1800130b2  or      edi, eax
0x1800130b4  mov     eax, [rbx]
0x1800130b6  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800130bb  mov     edx, eax
0x1800130bd  mov     [rbx], eax
0x1800130bf  jz      short loc_1800130EB
0x1800130c1  test    dl, 2
0x1800130c4  jnz     short loc_1800130EB
0x1800130c6  xor     eax, edi
0x1800130c8  and     eax, 180h
0x1800130cd  xor     eax, edx
0x1800130cf  mov     ecx, eax
0x1800130d1  xor     ecx, edi
0x1800130d3  and     ecx, r15d
0x1800130d6  xor     ecx, eax
0x1800130d8  or      ecx, 1
0x1800130db  mov     eax, ecx
0x1800130dd  xor     eax, edi
0x1800130df  and     eax, 800h
0x1800130e4  xor     eax, ecx
0x1800130e6  or      eax, 2
0x1800130e9  mov     [rbx], eax
0x1800130eb  mov     r8d, edx
0x1800130ee  mov     ecx, eax
0x1800130f0  and     r8d, 4
0x1800130f4  jnz     short loc_180013105
0x1800130f6  xor     ecx, edi
0x1800130f8  and     ecx, 400h
0x1800130fe  xor     ecx, eax
0x180013100  or      ecx, 4
0x180013103  mov     [rbx], ecx
0x180013105  mov     eax, edx
0x180013107  lock cmpxchg [rsi], ecx
0x18001310b  jnz     short loc_1800130B6
0x18001310d  test    r8d, r8d
0x180013110  jnz     short loc_180013122
0x180013112  mov     r8d, ebp
0x180013115  mov     edx, 3
0x18001311a  mov     rcx, rsi
0x18001311d  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180013122  test    byte ptr [rbx], 2
0x180013125  jnz     short loc_18001314B
0x180013127  mov     eax, [rbx]
0x180013129  xor     eax, edi
0x18001312b  and     eax, 180h
0x180013130  xor     eax, [rbx]
0x180013132  mov     ecx, eax
0x180013134  xor     ecx, edi
0x180013136  and     ecx, r15d
0x180013139  xor     ecx, eax
0x18001313b  or      ecx, 1
0x18001313e  mov     eax, ecx
0x180013140  xor     eax, edi
0x180013142  and     eax, 800h
0x180013147  xor     eax, ecx
0x180013149  mov     [rbx], eax
0x18001314b  mov     rbp, [rsp+38h+arg_10]
0x180013150  mov     rax, rbx
0x180013153  mov     rbx, [rsp+38h+arg_8]
0x180013158  add     rsp, 20h
0x18001315c  pop     r15
0x18001315e  pop     rdi
0x18001315f  pop     rsi
0x180013160  retn
```
