# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::GetCachedFeatureEnabledState(void)

- ea: `0x18000d790`
- end: `0x18000d928`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `408`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fb34`
- `0x1800117d0`

## callees

- `0x18000d020`
- `0x18000d790`
- `0x1800105e0`
- `0x1800109c4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  int v5; // ebp
  int *v6; // r9
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v8; // r8d
  int v9; // edx
  int v10; // eax
  int v11; // edi
  char v12; // al
  int v13; // eax
  int v14; // edi
  signed __int32 v15; // eax
  bool v16; // zf
  signed __int32 v17; // edx
  int v18; // r8d
  int v19; // r9d
  signed __int32 v20; // ecx
  wil::details *v22; // [rsp+40h] [rbp+8h] BYREF

  v22 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_ModernizeSecMgrCreationInShell__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ModernizeSecMgrCreationInShell__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v22) = 0;
  v5 = v4;
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                          (wil::details *)0x344DED5,
                          3u,
                          (enum FEATURE_CHANGE_TIME)&v22,
                          v6);
  v8 = FeatureEnabledState & 0xFFFFFF3F;
  v9 = FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3))));
  v10 = 0;
  if ( v8 == 2 )
    v10 = 64;
  v11 = v10 | (8 * v9);
  if ( (v11 & 0xC00) == 0xC00 )
  {
    v12 = 1;
  }
  else
  {
    if ( (v11 & 0x40) != 0 )
      goto LABEL_11;
    v12 = 0;
  }
  if ( (v11 & 0x40) == 0 || !v12 )
  {
    v13 = 0;
    goto LABEL_12;
  }
LABEL_11:
  v13 = 1;
LABEL_12:
  v14 = v13 | v11;
  v15 = *(_DWORD *)a2;
  do
  {
    v16 = (_DWORD)v22 == 0;
    v17 = v15;
    *(_DWORD *)a2 = v15;
    if ( v16 || (v15 & 2) != 0 )
    {
      v18 = v15;
    }
    else
    {
      v18 = v15
          ^ ((unsigned __int16)v15
           ^ (unsigned __int16)v14)
          & 0x180
          ^ (v14
           ^ v15
           ^ ((unsigned __int16)v15
            ^ (unsigned __int16)v14)
           & 0x180)
          & 0x40
          ^ ((unsigned __int8)v14
           ^ (unsigned __int8)(v15 ^ (v15 ^ v14) & 0x80 ^ (v14 ^ v15 ^ (v15 ^ v14) & 0x80) & 0x40))
          & 1
          ^ ((unsigned __int16)v14
           ^ (unsigned __int16)(v15
                              ^ (v15
                               ^ v14)
                              & 0x180
                              ^ (v14
                               ^ v15
                               ^ (v15
                                ^ v14)
                               & 0x180)
                              & 0x40
                              ^ ((unsigned __int8)v14
                               ^ (unsigned __int8)(v15 ^ (v15 ^ v14) & 0x80 ^ (v14 ^ v15 ^ (v15 ^ v14) & 0x80) & 0x40))
                              & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v18;
    }
    v19 = v15 & 4;
    if ( (v15 & 4) != 0 )
    {
      v20 = v18;
    }
    else
    {
      v20 = v18 ^ ((unsigned __int16)v18 ^ (unsigned __int16)v14) & 0x400 | 4;
      *(_DWORD *)a2 = v20;
    }
    v15 = _InterlockedCompareExchange(
            (volatile signed __int32 *)Feature_ModernizeSecMgrCreationInShell__descriptor,
            v20,
            v15);
  }
  while ( v17 != v15 );
  if ( !v19 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      (volatile signed __int32 *)Feature_ModernizeSecMgrCreationInShell__descriptor,
      3,
      v5);
  if ( (*(_BYTE *)a2 & 2) == 0 )
    *(_DWORD *)a2 ^= ((unsigned __int16)v14
                    ^ (unsigned __int16)*(_DWORD *)a2)
                   & 0x180
                   ^ (v14
                    ^ *(_DWORD *)a2
                    ^ ((unsigned __int16)v14
                     ^ (unsigned __int16)*(_DWORD *)a2)
                    & 0x180)
                   & 0x40
                   ^ ((unsigned __int8)v14
                    ^ *(_BYTE *)a2
                    ^ ((unsigned __int8)v14
                     ^ (unsigned __int8)*(_DWORD *)a2)
                    & 0x80
                    ^ ((unsigned __int8)v14
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v14
                      ^ (unsigned __int8)*(_DWORD *)a2)
                     & 0x80)
                    & 0x40)
                   & 1
                   ^ ((unsigned __int16)v14
                    ^ *(_WORD *)a2
                    ^ ((unsigned __int16)v14
                     ^ (unsigned __int16)*(_DWORD *)a2)
                    & 0x180
                    ^ ((unsigned __int16)v14
                     ^ *(_WORD *)a2
                     ^ ((unsigned __int16)v14
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180)
                    & 0x40
                    ^ ((unsigned __int8)v14
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v14
                      ^ (unsigned __int8)*(_DWORD *)a2)
                     & 0x80
                     ^ ((unsigned __int8)v14
                      ^ *(_BYTE *)a2
                      ^ ((unsigned __int8)v14
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
0x18000d790  mov     [rsp+arg_8], rbx
0x18000d795  mov     [rsp+arg_10], rbp
0x18000d79a  mov     [rsp+arg_0], rcx
0x18000d79f  push    rsi
0x18000d7a0  push    rdi
0x18000d7a1  push    r15
0x18000d7a3  sub     rsp, 20h
0x18000d7a7  mov     rsi, cs:Feature_ModernizeSecMgrCreationInShell__descriptor
0x18000d7ae  mov     rbx, rdx
0x18000d7b1  mov     qword ptr [rdx], 0
0x18000d7b8  mov     eax, [rsi]
0x18000d7ba  mov     [rdx], eax
0x18000d7bc  and     eax, 6
0x18000d7bf  cmp     al, 6
0x18000d7c1  jz      loc_18000D912
0x18000d7c7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000d7cc  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x18000d7d1  mov     dword ptr [rsp+38h+arg_0], 0
0x18000d7d9  mov     edx, 3; unsigned int
0x18000d7de  mov     ecx, 344DED5h; this
0x18000d7e3  mov     ebp, eax
0x18000d7e5  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18000d7ea  mov     r8d, eax
0x18000d7ed  mov     ecx, eax
0x18000d7ef  and     eax, 80h
0x18000d7f4  and     r8d, 0FFFFFF3Fh
0x18000d7fb  mov     edx, r8d
0x18000d7fe  mov     r15d, 40h ; '@'
0x18000d804  and     edx, 3
0x18000d807  and     ecx, r15d
0x18000d80a  shl     edx, 2
0x18000d80d  or      edx, ecx
0x18000d80f  shl     edx, 2
0x18000d812  or      edx, eax
0x18000d814  xor     eax, eax
0x18000d816  lea     edi, ds:0[rdx*8]
0x18000d81d  test    r8d, r8d
0x18000d820  jz      short loc_18000D82A
0x18000d822  cmp     r8d, 2
0x18000d826  cmovz   eax, r15d
0x18000d82a  or      edi, eax
0x18000d82c  mov     edx, 0C00h
0x18000d831  mov     ecx, edi
0x18000d833  mov     eax, edi
0x18000d835  and     ecx, r15d
0x18000d838  and     eax, edx
0x18000d83a  cmp     eax, edx
0x18000d83c  jnz     short loc_18000D842
0x18000d83e  mov     al, 1
0x18000d840  jmp     short loc_18000D848
0x18000d842  test    ecx, ecx
0x18000d844  jnz     short loc_18000D854
0x18000d846  xor     al, al
0x18000d848  test    ecx, ecx
0x18000d84a  jz      short loc_18000D850
0x18000d84c  test    al, al
0x18000d84e  jnz     short loc_18000D854
0x18000d850  xor     eax, eax
0x18000d852  jmp     short loc_18000D859
0x18000d854  mov     eax, 1
0x18000d859  or      edi, eax
0x18000d85b  mov     eax, [rbx]
0x18000d85d  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000d862  mov     edx, eax
0x18000d864  mov     [rbx], eax
0x18000d866  jz      short loc_18000D8A3
0x18000d868  test    dl, 2
0x18000d86b  jnz     short loc_18000D8A3
0x18000d86d  mov     eax, edi
0x18000d86f  xor     eax, edx
0x18000d871  and     eax, 180h
0x18000d876  xor     eax, edx
0x18000d878  mov     ecx, eax
0x18000d87a  xor     ecx, edi
0x18000d87c  and     ecx, r15d
0x18000d87f  xor     ecx, eax
0x18000d881  mov     eax, ecx
0x18000d883  xor     eax, edi
0x18000d885  and     eax, 1
0x18000d888  xor     eax, ecx
0x18000d88a  mov     r8d, eax
0x18000d88d  xor     r8d, edi
0x18000d890  and     r8d, 800h
0x18000d897  xor     r8d, eax
0x18000d89a  or      r8d, 2
0x18000d89e  mov     [rbx], r8d
0x18000d8a1  jmp     short loc_18000D8A6
0x18000d8a3  mov     r8d, edx
0x18000d8a6  mov     r9d, edx
0x18000d8a9  and     r9d, 4
0x18000d8ad  jnz     short loc_18000D8C4
0x18000d8af  mov     ecx, edi
0x18000d8b1  xor     ecx, r8d
0x18000d8b4  and     ecx, 400h
0x18000d8ba  xor     ecx, r8d
0x18000d8bd  or      ecx, 4
0x18000d8c0  mov     [rbx], ecx
0x18000d8c2  jmp     short loc_18000D8C7
0x18000d8c4  mov     ecx, r8d
0x18000d8c7  mov     eax, edx
0x18000d8c9  lock cmpxchg [rsi], ecx
0x18000d8cd  jnz     short loc_18000D85D
0x18000d8cf  test    r9d, r9d
0x18000d8d2  jnz     short loc_18000D8E3
0x18000d8d4  mov     r8d, ebp
0x18000d8d7  lea     edx, [r9+3]
0x18000d8db  mov     rcx, rsi
0x18000d8de  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000d8e3  test    byte ptr [rbx], 2
0x18000d8e6  jnz     short loc_18000D912
0x18000d8e8  mov     eax, [rbx]
0x18000d8ea  xor     eax, edi
0x18000d8ec  and     eax, 180h
0x18000d8f1  xor     eax, [rbx]
0x18000d8f3  mov     ecx, eax
0x18000d8f5  xor     ecx, edi
0x18000d8f7  and     ecx, r15d
0x18000d8fa  xor     ecx, eax
0x18000d8fc  mov     edx, ecx
0x18000d8fe  xor     edx, edi
0x18000d900  and     edx, 1
0x18000d903  xor     edx, ecx
0x18000d905  mov     eax, edx
0x18000d907  xor     eax, edi
0x18000d909  and     eax, 800h
0x18000d90e  xor     eax, edx
0x18000d910  mov     [rbx], eax
0x18000d912  mov     rbp, [rsp+38h+arg_10]
0x18000d917  mov     rax, rbx
0x18000d91a  mov     rbx, [rsp+38h+arg_8]
0x18000d91f  add     rsp, 20h
0x18000d923  pop     r15
0x18000d925  pop     rdi
0x18000d926  pop     rsi
0x18000d927  retn
```
