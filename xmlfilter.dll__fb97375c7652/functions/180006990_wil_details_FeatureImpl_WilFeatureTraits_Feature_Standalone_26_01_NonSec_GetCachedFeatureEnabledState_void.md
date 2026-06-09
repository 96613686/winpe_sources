# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180006990`
- end: `0x180006afd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007960`

## callees

- `0x180005dd0`
- `0x180006990`
- `0x18000c3f0`
- `0x180017010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(58599532, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_26_01_NonSec__descriptor, 3, v4);
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
0x180006990  mov     [rsp+arg_8], rbx
0x180006995  mov     [rsp+arg_10], rbp
0x18000699a  mov     [rsp+arg_0], rcx
0x18000699f  push    rsi
0x1800069a0  push    rdi
0x1800069a1  push    r15
0x1800069a3  sub     rsp, 20h
0x1800069a7  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x1800069ae  mov     rbx, rdx
0x1800069b1  mov     qword ptr [rdx], 0
0x1800069b8  mov     eax, [rsi]
0x1800069ba  mov     [rdx], eax
0x1800069bc  and     eax, 6
0x1800069bf  cmp     al, 6
0x1800069c1  jz      loc_180006AE7
0x1800069c7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800069cc  mov     ebp, eax
0x1800069ce  mov     dword ptr [rsp+38h+arg_0], 0
0x1800069d6  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800069dd  test    rax, rax
0x1800069e0  jz      short loc_1800069FA
0x1800069e2  lea     r8, [rsp+38h+arg_0]
0x1800069e7  mov     edx, 3
0x1800069ec  mov     ecx, 37E286Ch
0x1800069f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069f6  mov     edx, eax
0x1800069f8  jmp     short loc_180006A08
0x1800069fa  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180006a01  test    rax, rax
0x180006a04  jnz     short loc_1800069E2
0x180006a06  xor     edx, edx
0x180006a08  mov     r8d, edx
0x180006a0b  mov     eax, edx
0x180006a0d  and     r8d, 0FFFFFF3Fh
0x180006a14  and     edx, 80h
0x180006a1a  mov     ecx, r8d
0x180006a1d  mov     r15d, 40h ; '@'
0x180006a23  and     ecx, 3
0x180006a26  and     eax, r15d
0x180006a29  shl     ecx, 2
0x180006a2c  or      ecx, eax
0x180006a2e  shl     ecx, 2
0x180006a31  or      ecx, edx
0x180006a33  lea     edi, ds:0[rcx*8]
0x180006a3a  test    r8d, r8d
0x180006a3d  jnz     short loc_180006A44
0x180006a3f  mov     eax, r15d
0x180006a42  jmp     short loc_180006A4E
0x180006a44  xor     eax, eax
0x180006a46  cmp     r8d, 2
0x180006a4a  cmovz   eax, r15d
0x180006a4e  or      edi, eax
0x180006a50  mov     eax, [rbx]
0x180006a52  cmp     dword ptr [rsp+38h+arg_0], 0
0x180006a57  mov     edx, eax
0x180006a59  mov     [rbx], eax
0x180006a5b  jz      short loc_180006A87
0x180006a5d  test    dl, 2
0x180006a60  jnz     short loc_180006A87
0x180006a62  xor     eax, edi
0x180006a64  and     eax, 180h
0x180006a69  xor     eax, edx
0x180006a6b  mov     ecx, eax
0x180006a6d  xor     ecx, edi
0x180006a6f  and     ecx, r15d
0x180006a72  xor     ecx, eax
0x180006a74  or      ecx, 1
0x180006a77  mov     eax, ecx
0x180006a79  xor     eax, edi
0x180006a7b  and     eax, 800h
0x180006a80  xor     eax, ecx
0x180006a82  or      eax, 2
0x180006a85  mov     [rbx], eax
0x180006a87  mov     r8d, edx
0x180006a8a  mov     ecx, eax
0x180006a8c  and     r8d, 4
0x180006a90  jnz     short loc_180006AA1
0x180006a92  xor     ecx, edi
0x180006a94  and     ecx, 400h
0x180006a9a  xor     ecx, eax
0x180006a9c  or      ecx, 4
0x180006a9f  mov     [rbx], ecx
0x180006aa1  mov     eax, edx
0x180006aa3  lock cmpxchg [rsi], ecx
0x180006aa7  jnz     short loc_180006A52
0x180006aa9  test    r8d, r8d
0x180006aac  jnz     short loc_180006ABE
0x180006aae  mov     r8d, ebp
0x180006ab1  mov     edx, 3
0x180006ab6  mov     rcx, rsi
0x180006ab9  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180006abe  test    byte ptr [rbx], 2
0x180006ac1  jnz     short loc_180006AE7
0x180006ac3  mov     eax, [rbx]
0x180006ac5  xor     eax, edi
0x180006ac7  and     eax, 180h
0x180006acc  xor     eax, [rbx]
0x180006ace  mov     ecx, eax
0x180006ad0  xor     ecx, edi
0x180006ad2  and     ecx, r15d
0x180006ad5  xor     ecx, eax
0x180006ad7  or      ecx, 1
0x180006ada  mov     eax, ecx
0x180006adc  xor     eax, edi
0x180006ade  and     eax, 800h
0x180006ae3  xor     eax, ecx
0x180006ae5  mov     [rbx], eax
0x180006ae7  mov     rbp, [rsp+38h+arg_10]
0x180006aec  mov     rax, rbx
0x180006aef  mov     rbx, [rsp+38h+arg_8]
0x180006af4  add     rsp, 20h
0x180006af8  pop     r15
0x180006afa  pop     rdi
0x180006afb  pop     rsi
0x180006afc  retn
```
