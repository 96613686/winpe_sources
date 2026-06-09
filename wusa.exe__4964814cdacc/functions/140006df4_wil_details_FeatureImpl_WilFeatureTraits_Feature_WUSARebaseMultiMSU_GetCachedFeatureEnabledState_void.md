# wil::details::FeatureImpl<__WilFeatureTraits_Feature_WUSARebaseMultiMSU>::GetCachedFeatureEnabledState(void)

- ea: `0x140006df4`
- end: `0x140006fb0`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WUSARebaseMultiMSU@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `444`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000a24c`
- `0x14000c124`

## callees

- `0x1400068a4`
- `0x140006df4`
- `0x14000ac68`
- `0x140015010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_WUSARebaseMultiMSU>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, __int64, wil::details **); // rax
  int v6; // edx
  int v7; // eax
  int v8; // ebx
  char v9; // al
  int v10; // eax
  int v11; // ebx
  signed __int32 v12; // eax
  bool v13; // zf
  signed __int32 v14; // edx
  int v15; // r8d
  int v16; // r9d
  signed __int32 v17; // ecx
  wil::details *v19; // [rsp+40h] [rbp+8h] BYREF

  v19 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_WUSARebaseMultiMSU__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_WUSARebaseMultiMSU__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v19) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(58674884, 3, &v19);
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
  if ( (v8 & 0xC00) == 0xC00 )
  {
    v9 = 1;
  }
  else
  {
    if ( (v8 & 0x40) != 0 )
      goto LABEL_17;
    v9 = 0;
  }
  if ( (v8 & 0x40) == 0 || !v9 )
  {
    v10 = 0;
    goto LABEL_18;
  }
LABEL_17:
  v10 = 1;
LABEL_18:
  v11 = v10 | v8;
  v12 = *(_DWORD *)a2;
  do
  {
    v13 = (_DWORD)v19 == 0;
    v14 = v12;
    *(_DWORD *)a2 = v12;
    if ( v13 || (v12 & 2) != 0 )
    {
      v15 = v12;
    }
    else
    {
      v15 = v12
          ^ ((unsigned __int16)v12
           ^ (unsigned __int16)v11)
          & 0x180
          ^ (v11
           ^ v12
           ^ ((unsigned __int16)v12
            ^ (unsigned __int16)v11)
           & 0x180)
          & 0x40
          ^ ((unsigned __int8)v11
           ^ (unsigned __int8)(v12 ^ (v12 ^ v11) & 0x80 ^ (v11 ^ v12 ^ (v12 ^ v11) & 0x80) & 0x40))
          & 1
          ^ ((unsigned __int16)v11
           ^ (unsigned __int16)(v12
                              ^ (v12
                               ^ v11)
                              & 0x180
                              ^ (v11
                               ^ v12
                               ^ (v12
                                ^ v11)
                               & 0x180)
                              & 0x40
                              ^ ((unsigned __int8)v11
                               ^ (unsigned __int8)(v12 ^ (v12 ^ v11) & 0x80 ^ (v11 ^ v12 ^ (v12 ^ v11) & 0x80) & 0x40))
                              & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v15;
    }
    v16 = v12 & 4;
    if ( (v12 & 4) != 0 )
    {
      v17 = v15;
    }
    else
    {
      v17 = v15 ^ ((unsigned __int16)v15 ^ (unsigned __int16)v11) & 0x400 | 4;
      *(_DWORD *)a2 = v17;
    }
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_WUSARebaseMultiMSU__descriptor, v17, v12);
  }
  while ( v14 != v12 );
  if ( !v16 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_WUSARebaseMultiMSU__descriptor, 3, v4);
  if ( (*(_BYTE *)a2 & 2) == 0 )
    *(_DWORD *)a2 ^= ((unsigned __int16)v11
                    ^ (unsigned __int16)*(_DWORD *)a2)
                   & 0x180
                   ^ (v11
                    ^ *(_DWORD *)a2
                    ^ ((unsigned __int16)v11
                     ^ (unsigned __int16)*(_DWORD *)a2)
                    & 0x180)
                   & 0x40
                   ^ ((unsigned __int8)v11
                    ^ *(_BYTE *)a2
                    ^ ((unsigned __int8)v11
                     ^ (unsigned __int8)*(_DWORD *)a2)
                    & 0x80
                    ^ ((unsigned __int8)v11
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v11
                      ^ (unsigned __int8)*(_DWORD *)a2)
                     & 0x80)
                    & 0x40)
                   & 1
                   ^ ((unsigned __int16)v11
                    ^ *(_WORD *)a2
                    ^ ((unsigned __int16)v11
                     ^ (unsigned __int16)*(_DWORD *)a2)
                    & 0x180
                    ^ ((unsigned __int16)v11
                     ^ *(_WORD *)a2
                     ^ ((unsigned __int16)v11
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180)
                    & 0x40
                    ^ ((unsigned __int8)v11
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v11
                      ^ (unsigned __int8)*(_DWORD *)a2)
                     & 0x80
                     ^ ((unsigned __int8)v11
                      ^ *(_BYTE *)a2
                      ^ ((unsigned __int8)v11
                       ^ (unsigned __int8)*(_DWORD *)a2)
                      & 0x80)
                     & 0x40)
                    & 1)
                   & 0x800;
  return a2;
}

```

## disassembly

```asm
0x140006df4  mov     [rsp+arg_8], rbx
0x140006df9  mov     [rsp+arg_10], rbp
0x140006dfe  mov     [rsp+arg_0], rcx
0x140006e03  push    rsi
0x140006e04  push    rdi
0x140006e05  push    r15
0x140006e07  sub     rsp, 20h
0x140006e0b  mov     rsi, cs:Feature_WUSARebaseMultiMSU__descriptor
0x140006e12  mov     rdi, rdx
0x140006e15  mov     qword ptr [rdx], 0
0x140006e1c  mov     eax, [rsi]
0x140006e1e  mov     [rdx], eax
0x140006e20  and     eax, 6
0x140006e23  cmp     al, 6
0x140006e25  jz      loc_140006F9A
0x140006e2b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140006e30  mov     ebp, eax
0x140006e32  mov     dword ptr [rsp+38h+arg_0], 0
0x140006e3a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140006e41  test    rax, rax
0x140006e44  jz      short loc_140006E5E
0x140006e46  lea     r8, [rsp+38h+arg_0]
0x140006e4b  mov     edx, 3
0x140006e50  mov     ecx, 37F4EC4h
0x140006e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006e5a  mov     edx, eax
0x140006e5c  jmp     short loc_140006E6C
0x140006e5e  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140006e65  test    rax, rax
0x140006e68  jnz     short loc_140006E46
0x140006e6a  xor     edx, edx
0x140006e6c  mov     r8d, edx
0x140006e6f  mov     eax, edx
0x140006e71  and     r8d, 0FFFFFF3Fh
0x140006e78  and     edx, 80h
0x140006e7e  mov     ecx, r8d
0x140006e81  mov     r15d, 40h ; '@'
0x140006e87  and     ecx, 3
0x140006e8a  and     eax, r15d
0x140006e8d  shl     ecx, 2
0x140006e90  or      ecx, eax
0x140006e92  shl     ecx, 2
0x140006e95  or      ecx, edx
0x140006e97  lea     ebx, ds:0[rcx*8]
0x140006e9e  test    r8d, r8d
0x140006ea1  jnz     short loc_140006EA8
0x140006ea3  mov     eax, r15d
0x140006ea6  jmp     short loc_140006EB2
0x140006ea8  xor     eax, eax
0x140006eaa  cmp     r8d, 2
0x140006eae  cmovz   eax, r15d
0x140006eb2  or      ebx, eax
0x140006eb4  mov     edx, 0C00h
0x140006eb9  mov     ecx, ebx
0x140006ebb  mov     eax, ebx
0x140006ebd  and     ecx, r15d
0x140006ec0  and     eax, edx
0x140006ec2  cmp     eax, edx
0x140006ec4  jnz     short loc_140006ECA
0x140006ec6  mov     al, 1
0x140006ec8  jmp     short loc_140006ED0
0x140006eca  test    ecx, ecx
0x140006ecc  jnz     short loc_140006EDC
0x140006ece  xor     al, al
0x140006ed0  test    ecx, ecx
0x140006ed2  jz      short loc_140006ED8
0x140006ed4  test    al, al
0x140006ed6  jnz     short loc_140006EDC
0x140006ed8  xor     eax, eax
0x140006eda  jmp     short loc_140006EE1
0x140006edc  mov     eax, 1
0x140006ee1  or      ebx, eax
0x140006ee3  mov     eax, [rdi]
0x140006ee5  cmp     dword ptr [rsp+38h+arg_0], 0
0x140006eea  mov     edx, eax
0x140006eec  mov     [rdi], eax
0x140006eee  jz      short loc_140006F2B
0x140006ef0  test    dl, 2
0x140006ef3  jnz     short loc_140006F2B
0x140006ef5  mov     eax, ebx
0x140006ef7  xor     eax, edx
0x140006ef9  and     eax, 180h
0x140006efe  xor     eax, edx
0x140006f00  mov     ecx, eax
0x140006f02  xor     ecx, ebx
0x140006f04  and     ecx, r15d
0x140006f07  xor     ecx, eax
0x140006f09  mov     eax, ecx
0x140006f0b  xor     eax, ebx
0x140006f0d  and     eax, 1
0x140006f10  xor     eax, ecx
0x140006f12  mov     r8d, eax
0x140006f15  xor     r8d, ebx
0x140006f18  and     r8d, 800h
0x140006f1f  xor     r8d, eax
0x140006f22  or      r8d, 2
0x140006f26  mov     [rdi], r8d
0x140006f29  jmp     short loc_140006F2E
0x140006f2b  mov     r8d, edx
0x140006f2e  mov     r9d, edx
0x140006f31  and     r9d, 4
0x140006f35  jnz     short loc_140006F4C
0x140006f37  mov     ecx, ebx
0x140006f39  xor     ecx, r8d
0x140006f3c  and     ecx, 400h
0x140006f42  xor     ecx, r8d
0x140006f45  or      ecx, 4
0x140006f48  mov     [rdi], ecx
0x140006f4a  jmp     short loc_140006F4F
0x140006f4c  mov     ecx, r8d
0x140006f4f  mov     eax, edx
0x140006f51  lock cmpxchg [rsi], ecx
0x140006f55  jnz     short loc_140006EE5
0x140006f57  test    r9d, r9d
0x140006f5a  jnz     short loc_140006F6B
0x140006f5c  mov     r8d, ebp
0x140006f5f  lea     edx, [r9+3]
0x140006f63  mov     rcx, rsi
0x140006f66  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140006f6b  test    byte ptr [rdi], 2
0x140006f6e  jnz     short loc_140006F9A
0x140006f70  mov     eax, [rdi]
0x140006f72  xor     eax, ebx
0x140006f74  and     eax, 180h
0x140006f79  xor     eax, [rdi]
0x140006f7b  mov     ecx, eax
0x140006f7d  xor     ecx, ebx
0x140006f7f  and     ecx, r15d
0x140006f82  xor     ecx, eax
0x140006f84  mov     edx, ecx
0x140006f86  xor     edx, ebx
0x140006f88  and     edx, 1
0x140006f8b  xor     edx, ecx
0x140006f8d  mov     eax, edx
0x140006f8f  xor     eax, ebx
0x140006f91  and     eax, 800h
0x140006f96  xor     eax, edx
0x140006f98  mov     [rdi], eax
0x140006f9a  mov     rbx, [rsp+38h+arg_8]
0x140006f9f  mov     rax, rdi
0x140006fa2  mov     rbp, [rsp+38h+arg_10]
0x140006fa7  add     rsp, 20h
0x140006fab  pop     r15
0x140006fad  pop     rdi
0x140006fae  pop     rsi
0x140006faf  retn
```
