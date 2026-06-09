# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180012a24`
- end: `0x180012b91`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014134`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x180012a24`
- `0x180029010`

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
0x180012a24  mov     [rsp+arg_8], rbx
0x180012a29  mov     [rsp+arg_10], rbp
0x180012a2e  mov     [rsp+arg_0], rcx
0x180012a33  push    rsi
0x180012a34  push    rdi
0x180012a35  push    r15
0x180012a37  sub     rsp, 20h
0x180012a3b  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x180012a42  mov     rbx, rdx
0x180012a45  mov     qword ptr [rdx], 0
0x180012a4c  mov     eax, [rsi]
0x180012a4e  mov     [rdx], eax
0x180012a50  and     eax, 6
0x180012a53  cmp     al, 6
0x180012a55  jz      loc_180012B7B
0x180012a5b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012a60  mov     ebp, eax
0x180012a62  mov     dword ptr [rsp+38h+arg_0], 0
0x180012a6a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180012a71  test    rax, rax
0x180012a74  jz      short loc_180012A8E
0x180012a76  lea     r8, [rsp+38h+arg_0]
0x180012a7b  mov     edx, 3
0x180012a80  mov     ecx, 2AF34F8h
0x180012a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a8a  mov     edx, eax
0x180012a8c  jmp     short loc_180012A9C
0x180012a8e  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180012a95  test    rax, rax
0x180012a98  jnz     short loc_180012A76
0x180012a9a  xor     edx, edx
0x180012a9c  mov     r8d, edx
0x180012a9f  mov     eax, edx
0x180012aa1  and     r8d, 0FFFFFF3Fh
0x180012aa8  and     edx, 80h
0x180012aae  mov     ecx, r8d
0x180012ab1  mov     r15d, 40h ; '@'
0x180012ab7  and     ecx, 3
0x180012aba  and     eax, r15d
0x180012abd  shl     ecx, 2
0x180012ac0  or      ecx, eax
0x180012ac2  shl     ecx, 2
0x180012ac5  or      ecx, edx
0x180012ac7  lea     edi, ds:0[rcx*8]
0x180012ace  test    r8d, r8d
0x180012ad1  jnz     short loc_180012AD8
0x180012ad3  mov     eax, r15d
0x180012ad6  jmp     short loc_180012AE2
0x180012ad8  xor     eax, eax
0x180012ada  cmp     r8d, 2
0x180012ade  cmovz   eax, r15d
0x180012ae2  or      edi, eax
0x180012ae4  mov     eax, [rbx]
0x180012ae6  cmp     dword ptr [rsp+38h+arg_0], 0
0x180012aeb  mov     edx, eax
0x180012aed  mov     [rbx], eax
0x180012aef  jz      short loc_180012B1B
0x180012af1  test    dl, 2
0x180012af4  jnz     short loc_180012B1B
0x180012af6  xor     eax, edi
0x180012af8  and     eax, 180h
0x180012afd  xor     eax, edx
0x180012aff  mov     ecx, eax
0x180012b01  xor     ecx, edi
0x180012b03  and     ecx, r15d
0x180012b06  xor     ecx, eax
0x180012b08  or      ecx, 1
0x180012b0b  mov     eax, ecx
0x180012b0d  xor     eax, edi
0x180012b0f  and     eax, 800h
0x180012b14  xor     eax, ecx
0x180012b16  or      eax, 2
0x180012b19  mov     [rbx], eax
0x180012b1b  mov     r8d, edx
0x180012b1e  mov     ecx, eax
0x180012b20  and     r8d, 4
0x180012b24  jnz     short loc_180012B35
0x180012b26  xor     ecx, edi
0x180012b28  and     ecx, 400h
0x180012b2e  xor     ecx, eax
0x180012b30  or      ecx, 4
0x180012b33  mov     [rbx], ecx
0x180012b35  mov     eax, edx
0x180012b37  lock cmpxchg [rsi], ecx
0x180012b3b  jnz     short loc_180012AE6
0x180012b3d  test    r8d, r8d
0x180012b40  jnz     short loc_180012B52
0x180012b42  mov     r8d, ebp
0x180012b45  mov     edx, 3
0x180012b4a  mov     rcx, rsi
0x180012b4d  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180012b52  test    byte ptr [rbx], 2
0x180012b55  jnz     short loc_180012B7B
0x180012b57  mov     eax, [rbx]
0x180012b59  xor     eax, edi
0x180012b5b  and     eax, 180h
0x180012b60  xor     eax, [rbx]
0x180012b62  mov     ecx, eax
0x180012b64  xor     ecx, edi
0x180012b66  and     ecx, r15d
0x180012b69  xor     ecx, eax
0x180012b6b  or      ecx, 1
0x180012b6e  mov     eax, ecx
0x180012b70  xor     eax, edi
0x180012b72  and     eax, 800h
0x180012b77  xor     eax, ecx
0x180012b79  mov     [rbx], eax
0x180012b7b  mov     rbp, [rsp+38h+arg_10]
0x180012b80  mov     rax, rbx
0x180012b83  mov     rbx, [rsp+38h+arg_8]
0x180012b88  add     rsp, 20h
0x180012b8c  pop     r15
0x180012b8e  pop     rdi
0x180012b8f  pop     rsi
0x180012b90  retn
```
