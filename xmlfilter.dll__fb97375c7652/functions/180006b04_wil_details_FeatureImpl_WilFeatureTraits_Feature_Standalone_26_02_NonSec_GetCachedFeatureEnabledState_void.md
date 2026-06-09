# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180006b04`
- end: `0x180006c71`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007680`

## callees

- `0x180005dd0`
- `0x180006b04`
- `0x18000c3f0`
- `0x180017010`

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
0x180006b04  mov     [rsp+arg_8], rbx
0x180006b09  mov     [rsp+arg_10], rbp
0x180006b0e  mov     [rsp+arg_0], rcx
0x180006b13  push    rsi
0x180006b14  push    rdi
0x180006b15  push    r15
0x180006b17  sub     rsp, 20h
0x180006b1b  mov     rsi, cs:Feature_Standalone_26_02_NonSec__descriptor
0x180006b22  mov     rbx, rdx
0x180006b25  mov     qword ptr [rdx], 0
0x180006b2c  mov     eax, [rsi]
0x180006b2e  mov     [rdx], eax
0x180006b30  and     eax, 6
0x180006b33  cmp     al, 6
0x180006b35  jz      loc_180006C5B
0x180006b3b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180006b40  mov     ebp, eax
0x180006b42  mov     dword ptr [rsp+38h+arg_0], 0
0x180006b4a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180006b51  test    rax, rax
0x180006b54  jz      short loc_180006B6E
0x180006b56  lea     r8, [rsp+38h+arg_0]
0x180006b5b  mov     edx, 3
0x180006b60  mov     ecx, 37E287Eh
0x180006b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b6a  mov     edx, eax
0x180006b6c  jmp     short loc_180006B7C
0x180006b6e  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180006b75  test    rax, rax
0x180006b78  jnz     short loc_180006B56
0x180006b7a  xor     edx, edx
0x180006b7c  mov     r8d, edx
0x180006b7f  mov     eax, edx
0x180006b81  and     r8d, 0FFFFFF3Fh
0x180006b88  and     edx, 80h
0x180006b8e  mov     ecx, r8d
0x180006b91  mov     r15d, 40h ; '@'
0x180006b97  and     ecx, 3
0x180006b9a  and     eax, r15d
0x180006b9d  shl     ecx, 2
0x180006ba0  or      ecx, eax
0x180006ba2  shl     ecx, 2
0x180006ba5  or      ecx, edx
0x180006ba7  lea     edi, ds:0[rcx*8]
0x180006bae  test    r8d, r8d
0x180006bb1  jnz     short loc_180006BB8
0x180006bb3  mov     eax, r15d
0x180006bb6  jmp     short loc_180006BC2
0x180006bb8  xor     eax, eax
0x180006bba  cmp     r8d, 2
0x180006bbe  cmovz   eax, r15d
0x180006bc2  or      edi, eax
0x180006bc4  mov     eax, [rbx]
0x180006bc6  cmp     dword ptr [rsp+38h+arg_0], 0
0x180006bcb  mov     edx, eax
0x180006bcd  mov     [rbx], eax
0x180006bcf  jz      short loc_180006BFB
0x180006bd1  test    dl, 2
0x180006bd4  jnz     short loc_180006BFB
0x180006bd6  xor     eax, edi
0x180006bd8  and     eax, 180h
0x180006bdd  xor     eax, edx
0x180006bdf  mov     ecx, eax
0x180006be1  xor     ecx, edi
0x180006be3  and     ecx, r15d
0x180006be6  xor     ecx, eax
0x180006be8  or      ecx, 1
0x180006beb  mov     eax, ecx
0x180006bed  xor     eax, edi
0x180006bef  and     eax, 800h
0x180006bf4  xor     eax, ecx
0x180006bf6  or      eax, 2
0x180006bf9  mov     [rbx], eax
0x180006bfb  mov     r8d, edx
0x180006bfe  mov     ecx, eax
0x180006c00  and     r8d, 4
0x180006c04  jnz     short loc_180006C15
0x180006c06  xor     ecx, edi
0x180006c08  and     ecx, 400h
0x180006c0e  xor     ecx, eax
0x180006c10  or      ecx, 4
0x180006c13  mov     [rbx], ecx
0x180006c15  mov     eax, edx
0x180006c17  lock cmpxchg [rsi], ecx
0x180006c1b  jnz     short loc_180006BC6
0x180006c1d  test    r8d, r8d
0x180006c20  jnz     short loc_180006C32
0x180006c22  mov     r8d, ebp
0x180006c25  mov     edx, 3
0x180006c2a  mov     rcx, rsi
0x180006c2d  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180006c32  test    byte ptr [rbx], 2
0x180006c35  jnz     short loc_180006C5B
0x180006c37  mov     eax, [rbx]
0x180006c39  xor     eax, edi
0x180006c3b  and     eax, 180h
0x180006c40  xor     eax, [rbx]
0x180006c42  mov     ecx, eax
0x180006c44  xor     ecx, edi
0x180006c46  and     ecx, r15d
0x180006c49  xor     ecx, eax
0x180006c4b  or      ecx, 1
0x180006c4e  mov     eax, ecx
0x180006c50  xor     eax, edi
0x180006c52  and     eax, 800h
0x180006c57  xor     eax, ecx
0x180006c59  mov     [rbx], eax
0x180006c5b  mov     rbp, [rsp+38h+arg_10]
0x180006c60  mov     rax, rbx
0x180006c63  mov     rbx, [rsp+38h+arg_8]
0x180006c68  add     rsp, 20h
0x180006c6c  pop     r15
0x180006c6e  pop     rdi
0x180006c6f  pop     rsi
0x180006c70  retn
```
