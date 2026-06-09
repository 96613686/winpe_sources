# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_03_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180012dfc`
- end: `0x180012f69`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800131e0`

## callees

- `0x180005dd8`
- `0x18000b3d8`
- `0x180012dfc`
- `0x18001b010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_03_NonSec>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
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
  v3 = *(_DWORD *)Feature_Standalone_25_03_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_03_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(45036774, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_03_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_25_03_NonSec__descriptor,
        3u,
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
0x180012dfc  mov     [rsp+arg_8], rbx
0x180012e01  mov     [rsp+arg_10], rbp
0x180012e06  mov     [rsp+arg_0], rcx
0x180012e0b  push    rsi
0x180012e0c  push    rdi
0x180012e0d  push    r15
0x180012e0f  sub     rsp, 20h
0x180012e13  mov     rsi, cs:Feature_Standalone_25_03_NonSec__descriptor
0x180012e1a  mov     rbx, rdx
0x180012e1d  mov     qword ptr [rdx], 0
0x180012e24  mov     eax, [rsi]
0x180012e26  mov     [rdx], eax
0x180012e28  and     eax, 6
0x180012e2b  cmp     al, 6
0x180012e2d  jz      loc_180012F53
0x180012e33  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012e38  mov     ebp, eax
0x180012e3a  mov     dword ptr [rsp+38h+arg_0], 0
0x180012e42  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180012e49  test    rax, rax
0x180012e4c  jz      short loc_180012E66
0x180012e4e  lea     r8, [rsp+38h+arg_0]
0x180012e53  mov     edx, 3
0x180012e58  mov     ecx, 2AF34E6h
0x180012e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e62  mov     edx, eax
0x180012e64  jmp     short loc_180012E74
0x180012e66  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180012e6d  test    rax, rax
0x180012e70  jnz     short loc_180012E4E
0x180012e72  xor     edx, edx
0x180012e74  mov     r8d, edx
0x180012e77  mov     eax, edx
0x180012e79  and     r8d, 0FFFFFF3Fh
0x180012e80  and     edx, 80h
0x180012e86  mov     ecx, r8d
0x180012e89  mov     r15d, 40h ; '@'
0x180012e8f  and     ecx, 3
0x180012e92  and     eax, r15d
0x180012e95  shl     ecx, 2
0x180012e98  or      ecx, eax
0x180012e9a  shl     ecx, 2
0x180012e9d  or      ecx, edx
0x180012e9f  lea     edi, ds:0[rcx*8]
0x180012ea6  test    r8d, r8d
0x180012ea9  jnz     short loc_180012EB0
0x180012eab  mov     eax, r15d
0x180012eae  jmp     short loc_180012EBA
0x180012eb0  xor     eax, eax
0x180012eb2  cmp     r8d, 2
0x180012eb6  cmovz   eax, r15d
0x180012eba  or      edi, eax
0x180012ebc  mov     eax, [rbx]
0x180012ebe  cmp     dword ptr [rsp+38h+arg_0], 0
0x180012ec3  mov     edx, eax
0x180012ec5  mov     [rbx], eax
0x180012ec7  jz      short loc_180012EF3
0x180012ec9  test    dl, 2
0x180012ecc  jnz     short loc_180012EF3
0x180012ece  xor     eax, edi
0x180012ed0  and     eax, 180h
0x180012ed5  xor     eax, edx
0x180012ed7  mov     ecx, eax
0x180012ed9  xor     ecx, edi
0x180012edb  and     ecx, r15d
0x180012ede  xor     ecx, eax
0x180012ee0  or      ecx, 1
0x180012ee3  mov     eax, ecx
0x180012ee5  xor     eax, edi
0x180012ee7  and     eax, 800h
0x180012eec  xor     eax, ecx
0x180012eee  or      eax, 2
0x180012ef1  mov     [rbx], eax
0x180012ef3  mov     r8d, edx
0x180012ef6  mov     ecx, eax
0x180012ef8  and     r8d, 4
0x180012efc  jnz     short loc_180012F0D
0x180012efe  xor     ecx, edi
0x180012f00  and     ecx, 400h
0x180012f06  xor     ecx, eax
0x180012f08  or      ecx, 4
0x180012f0b  mov     [rbx], ecx
0x180012f0d  mov     eax, edx
0x180012f0f  lock cmpxchg [rsi], ecx
0x180012f13  jnz     short loc_180012EBE
0x180012f15  test    r8d, r8d
0x180012f18  jnz     short loc_180012F2A
0x180012f1a  mov     r8d, ebp
0x180012f1d  mov     edx, 3
0x180012f22  mov     rcx, rsi
0x180012f25  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180012f2a  test    byte ptr [rbx], 2
0x180012f2d  jnz     short loc_180012F53
0x180012f2f  mov     eax, [rbx]
0x180012f31  xor     eax, edi
0x180012f33  and     eax, 180h
0x180012f38  xor     eax, [rbx]
0x180012f3a  mov     ecx, eax
0x180012f3c  xor     ecx, edi
0x180012f3e  and     ecx, r15d
0x180012f41  xor     ecx, eax
0x180012f43  or      ecx, 1
0x180012f46  mov     eax, ecx
0x180012f48  xor     eax, edi
0x180012f4a  and     eax, 800h
0x180012f4f  xor     eax, ecx
0x180012f51  mov     [rbx], eax
0x180012f53  mov     rbp, [rsp+38h+arg_10]
0x180012f58  mov     rax, rbx
0x180012f5b  mov     rbx, [rsp+38h+arg_8]
0x180012f60  add     rsp, 20h
0x180012f64  pop     r15
0x180012f66  pop     rdi
0x180012f67  pop     rsi
0x180012f68  retn
```
