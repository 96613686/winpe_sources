# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImplVal>::GetCachedFeatureEnabledState(void)

- ea: `0x18000d630`
- end: `0x18000d788`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ImplVal@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016850`

## callees

- `0x18000d020`
- `0x18000d630`
- `0x1800105e0`
- `0x1800109c4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImplVal>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  int v5; // ebp
  int *v6; // r9
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v8; // r8d
  int v9; // edi
  int v10; // eax
  int v11; // edi
  int v12; // eax
  bool v13; // zf
  signed __int32 v14; // edx
  signed __int32 v15; // ecx
  wil::details *v17; // [rsp+40h] [rbp+8h] BYREF

  v17 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_ImplVal__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ImplVal__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v17) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x33B9B29,
                            3u,
                            (enum FEATURE_CHANGE_TIME)&v17,
                            v6);
    v8 = FeatureEnabledState & 0xFFFFFF3F;
    v9 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
    if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
    {
      v10 = 0;
      if ( v8 == 2 )
        v10 = 64;
    }
    else
    {
      v10 = 64;
    }
    v11 = v10 | v9;
    v12 = *(_DWORD *)a2;
    do
    {
      v13 = (_DWORD)v17 == 0;
      v14 = v12;
      *(_DWORD *)a2 = v12;
      if ( !v13 && (v12 & 2) == 0 )
      {
        v12 = (v12
             ^ ((unsigned __int16)v12
              ^ (unsigned __int16)v11)
             & 0x180
             ^ (v11
              ^ v12
              ^ ((unsigned __int16)v12
               ^ (unsigned __int16)v11)
              & 0x180)
             & 0x40
             | 1)
            ^ ((unsigned __int16)v11
             ^ ((unsigned __int16)(v12 ^ (v12 ^ v11) & 0x180 ^ (v11 ^ v12 ^ (v12 ^ v11) & 0x180) & 0x40) | 1))
            & 0x800
            | 2;
        *(_DWORD *)a2 = v12;
      }
      if ( (v14 & 4) != 0 )
      {
        v15 = v12;
      }
      else
      {
        v15 = v12 ^ ((unsigned __int16)v12 ^ (unsigned __int16)v11) & 0x400 | 4;
        *(_DWORD *)a2 = v15;
      }
      v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ImplVal__descriptor, v15, v14);
    }
    while ( v14 != v12 );
    if ( (v14 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_ImplVal__descriptor,
        3,
        v5);
    if ( (*(_BYTE *)a2 & 2) == 0 )
      *(_DWORD *)a2 = (*(_DWORD *)a2
                     ^ ((unsigned __int16)v11
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180
                     ^ (v11
                      ^ *(_DWORD *)a2
                      ^ ((unsigned __int16)v11
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180)
                     & 0x40
                     | 1)
                    ^ ((unsigned __int16)v11
                     ^ (*(_WORD *)a2
                      ^ ((unsigned __int16)v11
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180
                      ^ ((unsigned __int16)v11
                       ^ *(_WORD *)a2
                       ^ ((unsigned __int16)v11
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
0x18000d630  mov     [rsp+arg_8], rbx
0x18000d635  mov     [rsp+arg_10], rbp
0x18000d63a  mov     [rsp+arg_0], rcx
0x18000d63f  push    rsi
0x18000d640  push    rdi
0x18000d641  push    r15
0x18000d643  sub     rsp, 20h
0x18000d647  mov     rsi, cs:Feature_ImplVal__descriptor
0x18000d64e  mov     rbx, rdx
0x18000d651  mov     qword ptr [rdx], 0
0x18000d658  mov     eax, [rsi]
0x18000d65a  mov     [rdx], eax
0x18000d65c  and     eax, 6
0x18000d65f  cmp     al, 6
0x18000d661  jz      loc_18000D772
0x18000d667  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000d66c  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x18000d671  mov     dword ptr [rsp+38h+arg_0], 0
0x18000d679  mov     edx, 3; unsigned int
0x18000d67e  mov     ecx, 33B9B29h; this
0x18000d683  mov     ebp, eax
0x18000d685  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18000d68a  mov     r8d, eax
0x18000d68d  mov     ecx, eax
0x18000d68f  and     r8d, 0FFFFFF3Fh
0x18000d696  and     eax, 80h
0x18000d69b  mov     edx, r8d
0x18000d69e  mov     r15d, 40h ; '@'
0x18000d6a4  and     edx, 3
0x18000d6a7  and     ecx, r15d
0x18000d6aa  shl     edx, 2
0x18000d6ad  or      edx, ecx
0x18000d6af  shl     edx, 2
0x18000d6b2  or      edx, eax
0x18000d6b4  lea     edi, ds:0[rdx*8]
0x18000d6bb  test    r8d, r8d
0x18000d6be  jnz     short loc_18000D6C5
0x18000d6c0  mov     eax, r15d
0x18000d6c3  jmp     short loc_18000D6CF
0x18000d6c5  xor     eax, eax
0x18000d6c7  cmp     r8d, 2
0x18000d6cb  cmovz   eax, r15d
0x18000d6cf  or      edi, eax
0x18000d6d1  mov     eax, [rbx]
0x18000d6d3  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000d6d8  mov     edx, eax
0x18000d6da  mov     [rbx], eax
0x18000d6dc  jz      short loc_18000D70C
0x18000d6de  test    dl, 2
0x18000d6e1  jnz     short loc_18000D70C
0x18000d6e3  mov     eax, edi
0x18000d6e5  xor     eax, edx
0x18000d6e7  and     eax, 180h
0x18000d6ec  xor     eax, edx
0x18000d6ee  mov     ecx, eax
0x18000d6f0  xor     ecx, edi
0x18000d6f2  and     ecx, r15d
0x18000d6f5  xor     ecx, eax
0x18000d6f7  or      ecx, 1
0x18000d6fa  mov     eax, ecx
0x18000d6fc  xor     eax, edi
0x18000d6fe  and     eax, 800h
0x18000d703  xor     eax, ecx
0x18000d705  or      eax, 2
0x18000d708  mov     [rbx], eax
0x18000d70a  jmp     short loc_18000D70E
0x18000d70c  mov     eax, edx
0x18000d70e  mov     r8d, edx
0x18000d711  and     r8d, 4
0x18000d715  jnz     short loc_18000D72A
0x18000d717  mov     ecx, edi
0x18000d719  xor     ecx, eax
0x18000d71b  and     ecx, 400h
0x18000d721  xor     ecx, eax
0x18000d723  or      ecx, 4
0x18000d726  mov     [rbx], ecx
0x18000d728  jmp     short loc_18000D72C
0x18000d72a  mov     ecx, eax
0x18000d72c  mov     eax, edx
0x18000d72e  lock cmpxchg [rsi], ecx
0x18000d732  jnz     short loc_18000D6D3
0x18000d734  test    r8d, r8d
0x18000d737  jnz     short loc_18000D749
0x18000d739  mov     r8d, ebp
0x18000d73c  mov     edx, 3
0x18000d741  mov     rcx, rsi
0x18000d744  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000d749  test    byte ptr [rbx], 2
0x18000d74c  jnz     short loc_18000D772
0x18000d74e  mov     eax, [rbx]
0x18000d750  xor     eax, edi
0x18000d752  and     eax, 180h
0x18000d757  xor     eax, [rbx]
0x18000d759  mov     ecx, eax
0x18000d75b  xor     ecx, edi
0x18000d75d  and     ecx, r15d
0x18000d760  xor     ecx, eax
0x18000d762  or      ecx, 1
0x18000d765  mov     eax, ecx
0x18000d767  xor     eax, edi
0x18000d769  and     eax, 800h
0x18000d76e  xor     eax, ecx
0x18000d770  mov     [rbx], eax
0x18000d772  mov     rbp, [rsp+38h+arg_10]
0x18000d777  mov     rax, rbx
0x18000d77a  mov     rbx, [rsp+38h+arg_8]
0x18000d77f  add     rsp, 20h
0x18000d783  pop     r15
0x18000d785  pop     rdi
0x18000d786  pop     rsi
0x18000d787  retn
```
