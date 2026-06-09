# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000da10`
- end: `0x18000db68`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ed24`

## callees

- `0x18000d020`
- `0x18000da10`
- `0x1800105e0`
- `0x1800109c4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v17) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x2AF34F8,
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
      v12 = _InterlockedCompareExchange(
              (volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor,
              v15,
              v14);
    }
    while ( v14 != v12 );
    if ( (v14 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor,
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
0x18000da10  mov     [rsp+arg_8], rbx
0x18000da15  mov     [rsp+arg_10], rbp
0x18000da1a  mov     [rsp+arg_0], rcx
0x18000da1f  push    rsi
0x18000da20  push    rdi
0x18000da21  push    r15
0x18000da23  sub     rsp, 20h
0x18000da27  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x18000da2e  mov     rbx, rdx
0x18000da31  mov     qword ptr [rdx], 0
0x18000da38  mov     eax, [rsi]
0x18000da3a  mov     [rdx], eax
0x18000da3c  and     eax, 6
0x18000da3f  cmp     al, 6
0x18000da41  jz      loc_18000DB52
0x18000da47  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000da4c  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x18000da51  mov     dword ptr [rsp+38h+arg_0], 0
0x18000da59  mov     edx, 3; unsigned int
0x18000da5e  mov     ecx, 2AF34F8h; this
0x18000da63  mov     ebp, eax
0x18000da65  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18000da6a  mov     r8d, eax
0x18000da6d  mov     ecx, eax
0x18000da6f  and     r8d, 0FFFFFF3Fh
0x18000da76  and     eax, 80h
0x18000da7b  mov     edx, r8d
0x18000da7e  mov     r15d, 40h ; '@'
0x18000da84  and     edx, 3
0x18000da87  and     ecx, r15d
0x18000da8a  shl     edx, 2
0x18000da8d  or      edx, ecx
0x18000da8f  shl     edx, 2
0x18000da92  or      edx, eax
0x18000da94  lea     edi, ds:0[rdx*8]
0x18000da9b  test    r8d, r8d
0x18000da9e  jnz     short loc_18000DAA5
0x18000daa0  mov     eax, r15d
0x18000daa3  jmp     short loc_18000DAAF
0x18000daa5  xor     eax, eax
0x18000daa7  cmp     r8d, 2
0x18000daab  cmovz   eax, r15d
0x18000daaf  or      edi, eax
0x18000dab1  mov     eax, [rbx]
0x18000dab3  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000dab8  mov     edx, eax
0x18000daba  mov     [rbx], eax
0x18000dabc  jz      short loc_18000DAEC
0x18000dabe  test    dl, 2
0x18000dac1  jnz     short loc_18000DAEC
0x18000dac3  mov     eax, edi
0x18000dac5  xor     eax, edx
0x18000dac7  and     eax, 180h
0x18000dacc  xor     eax, edx
0x18000dace  mov     ecx, eax
0x18000dad0  xor     ecx, edi
0x18000dad2  and     ecx, r15d
0x18000dad5  xor     ecx, eax
0x18000dad7  or      ecx, 1
0x18000dada  mov     eax, ecx
0x18000dadc  xor     eax, edi
0x18000dade  and     eax, 800h
0x18000dae3  xor     eax, ecx
0x18000dae5  or      eax, 2
0x18000dae8  mov     [rbx], eax
0x18000daea  jmp     short loc_18000DAEE
0x18000daec  mov     eax, edx
0x18000daee  mov     r8d, edx
0x18000daf1  and     r8d, 4
0x18000daf5  jnz     short loc_18000DB0A
0x18000daf7  mov     ecx, edi
0x18000daf9  xor     ecx, eax
0x18000dafb  and     ecx, 400h
0x18000db01  xor     ecx, eax
0x18000db03  or      ecx, 4
0x18000db06  mov     [rbx], ecx
0x18000db08  jmp     short loc_18000DB0C
0x18000db0a  mov     ecx, eax
0x18000db0c  mov     eax, edx
0x18000db0e  lock cmpxchg [rsi], ecx
0x18000db12  jnz     short loc_18000DAB3
0x18000db14  test    r8d, r8d
0x18000db17  jnz     short loc_18000DB29
0x18000db19  mov     r8d, ebp
0x18000db1c  mov     edx, 3
0x18000db21  mov     rcx, rsi
0x18000db24  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000db29  test    byte ptr [rbx], 2
0x18000db2c  jnz     short loc_18000DB52
0x18000db2e  mov     eax, [rbx]
0x18000db30  xor     eax, edi
0x18000db32  and     eax, 180h
0x18000db37  xor     eax, [rbx]
0x18000db39  mov     ecx, eax
0x18000db3b  xor     ecx, edi
0x18000db3d  and     ecx, r15d
0x18000db40  xor     ecx, eax
0x18000db42  or      ecx, 1
0x18000db45  mov     eax, ecx
0x18000db47  xor     eax, edi
0x18000db49  and     eax, 800h
0x18000db4e  xor     eax, ecx
0x18000db50  mov     [rbx], eax
0x18000db52  mov     rbp, [rsp+38h+arg_10]
0x18000db57  mov     rax, rbx
0x18000db5a  mov     rbx, [rsp+38h+arg_8]
0x18000db5f  add     rsp, 20h
0x18000db63  pop     r15
0x18000db65  pop     rdi
0x18000db66  pop     rsi
0x18000db67  retn
```
