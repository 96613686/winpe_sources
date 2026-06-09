# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56699092>::GetCachedFeatureEnabledState(void)

- ea: `0x180012c80`
- end: `0x180012df5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56699092@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `373`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001359c`

## callees

- `0x180005dd8`
- `0x18000b3d8`
- `0x180012c80`
- `0x18001b010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56699092>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
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
  v3 = *(_DWORD *)Feature_ID56699092__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ID56699092__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    v6 = 0;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(56699092, 0, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ID56699092__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_ID56699092__descriptor,
        0,
        v4);
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
0x180012c80  mov     [rsp+arg_8], rbx
0x180012c85  mov     [rsp+arg_10], rbp
0x180012c8a  mov     [rsp+arg_0], rcx
0x180012c8f  push    rsi
0x180012c90  push    rdi
0x180012c91  push    r15
0x180012c93  sub     rsp, 20h
0x180012c97  mov     rsi, cs:Feature_ID56699092__descriptor
0x180012c9e  mov     rbx, rdx
0x180012ca1  mov     qword ptr [rdx], 0
0x180012ca8  mov     eax, [rsi]
0x180012caa  mov     [rdx], eax
0x180012cac  and     eax, 6
0x180012caf  cmp     al, 6
0x180012cb1  jz      loc_180012DDF
0x180012cb7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012cbc  mov     ebp, eax
0x180012cbe  mov     dword ptr [rsp+38h+arg_0], 0
0x180012cc6  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180012ccd  xor     edx, edx
0x180012ccf  test    rax, rax
0x180012cd2  jnz     short loc_180012CE0
0x180012cd4  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180012cdb  test    rax, rax
0x180012cde  jz      short loc_180012CF1
0x180012ce0  lea     r8, [rsp+38h+arg_0]
0x180012ce5  mov     ecx, 36128D4h
0x180012cea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012cef  mov     edx, eax
0x180012cf1  mov     r8d, edx
0x180012cf4  mov     eax, edx
0x180012cf6  and     r8d, 0FFFFFF3Fh
0x180012cfd  and     edx, 80h
0x180012d03  mov     ecx, r8d
0x180012d06  mov     r15d, 40h ; '@'
0x180012d0c  and     ecx, 3
0x180012d0f  and     eax, r15d
0x180012d12  shl     ecx, 2
0x180012d15  or      ecx, eax
0x180012d17  shl     ecx, 2
0x180012d1a  or      ecx, edx
0x180012d1c  lea     edi, ds:0[rcx*8]
0x180012d23  test    r8d, r8d
0x180012d26  jnz     short loc_180012D2D
0x180012d28  mov     eax, r15d
0x180012d2b  jmp     short loc_180012D37
0x180012d2d  xor     eax, eax
0x180012d2f  cmp     r8d, 2
0x180012d33  cmovz   eax, r15d
0x180012d37  or      edi, eax
0x180012d39  test    ebp, ebp
0x180012d3b  jnz     short loc_180012D41
0x180012d3d  mov     dword ptr [rsp+38h+arg_0], ebp
0x180012d41  mov     eax, [rbx]
0x180012d43  cmp     dword ptr [rsp+38h+arg_0], 0
0x180012d48  mov     edx, eax
0x180012d4a  mov     [rbx], eax
0x180012d4c  jz      short loc_180012D7C
0x180012d4e  test    dl, 2
0x180012d51  jnz     short loc_180012D7C
0x180012d53  mov     eax, edi
0x180012d55  xor     eax, edx
0x180012d57  and     eax, 180h
0x180012d5c  xor     eax, edx
0x180012d5e  mov     ecx, eax
0x180012d60  xor     ecx, edi
0x180012d62  and     ecx, r15d
0x180012d65  xor     ecx, eax
0x180012d67  or      ecx, 1
0x180012d6a  mov     eax, ecx
0x180012d6c  xor     eax, edi
0x180012d6e  and     eax, 800h
0x180012d73  xor     eax, ecx
0x180012d75  or      eax, 2
0x180012d78  mov     [rbx], eax
0x180012d7a  jmp     short loc_180012D7E
0x180012d7c  mov     eax, edx
0x180012d7e  mov     r8d, edx
0x180012d81  and     r8d, 4
0x180012d85  jnz     short loc_180012D9A
0x180012d87  mov     ecx, edi
0x180012d89  xor     ecx, eax
0x180012d8b  and     ecx, 400h
0x180012d91  xor     ecx, eax
0x180012d93  or      ecx, 4
0x180012d96  mov     [rbx], ecx
0x180012d98  jmp     short loc_180012D9C
0x180012d9a  mov     ecx, eax
0x180012d9c  mov     eax, edx
0x180012d9e  lock cmpxchg [rsi], ecx
0x180012da2  jnz     short loc_180012D43
0x180012da4  test    r8d, r8d
0x180012da7  jnz     short loc_180012DB6
0x180012da9  mov     r8d, ebp
0x180012dac  xor     edx, edx
0x180012dae  mov     rcx, rsi
0x180012db1  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180012db6  test    byte ptr [rbx], 2
0x180012db9  jnz     short loc_180012DDF
0x180012dbb  mov     eax, [rbx]
0x180012dbd  xor     eax, edi
0x180012dbf  and     eax, 180h
0x180012dc4  xor     eax, [rbx]
0x180012dc6  mov     ecx, eax
0x180012dc8  xor     ecx, edi
0x180012dca  and     ecx, r15d
0x180012dcd  xor     ecx, eax
0x180012dcf  or      ecx, 1
0x180012dd2  mov     eax, ecx
0x180012dd4  xor     eax, edi
0x180012dd6  and     eax, 800h
0x180012ddb  xor     eax, ecx
0x180012ddd  mov     [rbx], eax
0x180012ddf  mov     rbp, [rsp+38h+arg_10]
0x180012de4  mov     rax, rbx
0x180012de7  mov     rbx, [rsp+38h+arg_8]
0x180012dec  add     rsp, 20h
0x180012df0  pop     r15
0x180012df2  pop     rdi
0x180012df3  pop     rsi
0x180012df4  retn
```
