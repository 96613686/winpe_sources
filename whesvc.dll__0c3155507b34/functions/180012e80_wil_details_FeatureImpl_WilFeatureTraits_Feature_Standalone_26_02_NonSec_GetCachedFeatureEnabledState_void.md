# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180012e80`
- end: `0x180012fed`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013a04`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x180012e80`
- `0x180029010`

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
0x180012e80  mov     [rsp+arg_8], rbx
0x180012e85  mov     [rsp+arg_10], rbp
0x180012e8a  mov     [rsp+arg_0], rcx
0x180012e8f  push    rsi
0x180012e90  push    rdi
0x180012e91  push    r15
0x180012e93  sub     rsp, 20h
0x180012e97  mov     rsi, cs:Feature_Standalone_26_02_NonSec__descriptor
0x180012e9e  mov     rbx, rdx
0x180012ea1  mov     qword ptr [rdx], 0
0x180012ea8  mov     eax, [rsi]
0x180012eaa  mov     [rdx], eax
0x180012eac  and     eax, 6
0x180012eaf  cmp     al, 6
0x180012eb1  jz      loc_180012FD7
0x180012eb7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012ebc  mov     ebp, eax
0x180012ebe  mov     dword ptr [rsp+38h+arg_0], 0
0x180012ec6  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180012ecd  test    rax, rax
0x180012ed0  jz      short loc_180012EEA
0x180012ed2  lea     r8, [rsp+38h+arg_0]
0x180012ed7  mov     edx, 3
0x180012edc  mov     ecx, 37E287Eh
0x180012ee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ee6  mov     edx, eax
0x180012ee8  jmp     short loc_180012EF8
0x180012eea  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180012ef1  test    rax, rax
0x180012ef4  jnz     short loc_180012ED2
0x180012ef6  xor     edx, edx
0x180012ef8  mov     r8d, edx
0x180012efb  mov     eax, edx
0x180012efd  and     r8d, 0FFFFFF3Fh
0x180012f04  and     edx, 80h
0x180012f0a  mov     ecx, r8d
0x180012f0d  mov     r15d, 40h ; '@'
0x180012f13  and     ecx, 3
0x180012f16  and     eax, r15d
0x180012f19  shl     ecx, 2
0x180012f1c  or      ecx, eax
0x180012f1e  shl     ecx, 2
0x180012f21  or      ecx, edx
0x180012f23  lea     edi, ds:0[rcx*8]
0x180012f2a  test    r8d, r8d
0x180012f2d  jnz     short loc_180012F34
0x180012f2f  mov     eax, r15d
0x180012f32  jmp     short loc_180012F3E
0x180012f34  xor     eax, eax
0x180012f36  cmp     r8d, 2
0x180012f3a  cmovz   eax, r15d
0x180012f3e  or      edi, eax
0x180012f40  mov     eax, [rbx]
0x180012f42  cmp     dword ptr [rsp+38h+arg_0], 0
0x180012f47  mov     edx, eax
0x180012f49  mov     [rbx], eax
0x180012f4b  jz      short loc_180012F77
0x180012f4d  test    dl, 2
0x180012f50  jnz     short loc_180012F77
0x180012f52  xor     eax, edi
0x180012f54  and     eax, 180h
0x180012f59  xor     eax, edx
0x180012f5b  mov     ecx, eax
0x180012f5d  xor     ecx, edi
0x180012f5f  and     ecx, r15d
0x180012f62  xor     ecx, eax
0x180012f64  or      ecx, 1
0x180012f67  mov     eax, ecx
0x180012f69  xor     eax, edi
0x180012f6b  and     eax, 800h
0x180012f70  xor     eax, ecx
0x180012f72  or      eax, 2
0x180012f75  mov     [rbx], eax
0x180012f77  mov     r8d, edx
0x180012f7a  mov     ecx, eax
0x180012f7c  and     r8d, 4
0x180012f80  jnz     short loc_180012F91
0x180012f82  xor     ecx, edi
0x180012f84  and     ecx, 400h
0x180012f8a  xor     ecx, eax
0x180012f8c  or      ecx, 4
0x180012f8f  mov     [rbx], ecx
0x180012f91  mov     eax, edx
0x180012f93  lock cmpxchg [rsi], ecx
0x180012f97  jnz     short loc_180012F42
0x180012f99  test    r8d, r8d
0x180012f9c  jnz     short loc_180012FAE
0x180012f9e  mov     r8d, ebp
0x180012fa1  mov     edx, 3
0x180012fa6  mov     rcx, rsi
0x180012fa9  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180012fae  test    byte ptr [rbx], 2
0x180012fb1  jnz     short loc_180012FD7
0x180012fb3  mov     eax, [rbx]
0x180012fb5  xor     eax, edi
0x180012fb7  and     eax, 180h
0x180012fbc  xor     eax, [rbx]
0x180012fbe  mov     ecx, eax
0x180012fc0  xor     ecx, edi
0x180012fc2  and     ecx, r15d
0x180012fc5  xor     ecx, eax
0x180012fc7  or      ecx, 1
0x180012fca  mov     eax, ecx
0x180012fcc  xor     eax, edi
0x180012fce  and     eax, 800h
0x180012fd3  xor     eax, ecx
0x180012fd5  mov     [rbx], eax
0x180012fd7  mov     rbp, [rsp+38h+arg_10]
0x180012fdc  mov     rax, rbx
0x180012fdf  mov     rbx, [rsp+38h+arg_8]
0x180012fe4  add     rsp, 20h
0x180012fe8  pop     r15
0x180012fea  pop     rdi
0x180012feb  pop     rsi
0x180012fec  retn
```
