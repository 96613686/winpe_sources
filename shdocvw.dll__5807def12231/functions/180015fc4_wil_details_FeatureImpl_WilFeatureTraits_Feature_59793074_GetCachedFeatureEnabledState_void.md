# wil::details::FeatureImpl<__WilFeatureTraits_Feature_59793074>::GetCachedFeatureEnabledState(void)

- ea: `0x180015fc4`
- end: `0x18001615c`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_59793074@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `408`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018cd4`
- `0x18001a630`

## callees

- `0x18000d020`
- `0x1800105e0`
- `0x1800109c4`
- `0x180015fc4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_59793074>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_59793074__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_59793074__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v22) = 0;
  v5 = v4;
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                          (wil::details *)0x3905EB2,
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
    v15 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_59793074__descriptor, v20, v15);
  }
  while ( v17 != v15 );
  if ( !v19 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      (volatile signed __int32 *)Feature_59793074__descriptor,
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
0x180015fc4  mov     [rsp+arg_8], rbx
0x180015fc9  mov     [rsp+arg_10], rbp
0x180015fce  mov     [rsp+arg_0], rcx
0x180015fd3  push    rsi
0x180015fd4  push    rdi
0x180015fd5  push    r15
0x180015fd7  sub     rsp, 20h
0x180015fdb  mov     rsi, cs:Feature_59793074__descriptor
0x180015fe2  mov     rbx, rdx
0x180015fe5  mov     qword ptr [rdx], 0
0x180015fec  mov     eax, [rsi]
0x180015fee  mov     [rdx], eax
0x180015ff0  and     eax, 6
0x180015ff3  cmp     al, 6
0x180015ff5  jz      loc_180016146
0x180015ffb  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180016000  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x180016005  mov     dword ptr [rsp+38h+arg_0], 0
0x18001600d  mov     edx, 3; unsigned int
0x180016012  mov     ecx, 3905EB2h; this
0x180016017  mov     ebp, eax
0x180016019  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001601e  mov     r8d, eax
0x180016021  mov     ecx, eax
0x180016023  and     eax, 80h
0x180016028  and     r8d, 0FFFFFF3Fh
0x18001602f  mov     edx, r8d
0x180016032  mov     r15d, 40h ; '@'
0x180016038  and     edx, 3
0x18001603b  and     ecx, r15d
0x18001603e  shl     edx, 2
0x180016041  or      edx, ecx
0x180016043  shl     edx, 2
0x180016046  or      edx, eax
0x180016048  xor     eax, eax
0x18001604a  lea     edi, ds:0[rdx*8]
0x180016051  test    r8d, r8d
0x180016054  jz      short loc_18001605E
0x180016056  cmp     r8d, 2
0x18001605a  cmovz   eax, r15d
0x18001605e  or      edi, eax
0x180016060  mov     edx, 0C00h
0x180016065  mov     ecx, edi
0x180016067  mov     eax, edi
0x180016069  and     ecx, r15d
0x18001606c  and     eax, edx
0x18001606e  cmp     eax, edx
0x180016070  jnz     short loc_180016076
0x180016072  mov     al, 1
0x180016074  jmp     short loc_18001607C
0x180016076  test    ecx, ecx
0x180016078  jnz     short loc_180016088
0x18001607a  xor     al, al
0x18001607c  test    ecx, ecx
0x18001607e  jz      short loc_180016084
0x180016080  test    al, al
0x180016082  jnz     short loc_180016088
0x180016084  xor     eax, eax
0x180016086  jmp     short loc_18001608D
0x180016088  mov     eax, 1
0x18001608d  or      edi, eax
0x18001608f  mov     eax, [rbx]
0x180016091  cmp     dword ptr [rsp+38h+arg_0], 0
0x180016096  mov     edx, eax
0x180016098  mov     [rbx], eax
0x18001609a  jz      short loc_1800160D7
0x18001609c  test    dl, 2
0x18001609f  jnz     short loc_1800160D7
0x1800160a1  mov     eax, edi
0x1800160a3  xor     eax, edx
0x1800160a5  and     eax, 180h
0x1800160aa  xor     eax, edx
0x1800160ac  mov     ecx, eax
0x1800160ae  xor     ecx, edi
0x1800160b0  and     ecx, r15d
0x1800160b3  xor     ecx, eax
0x1800160b5  mov     eax, ecx
0x1800160b7  xor     eax, edi
0x1800160b9  and     eax, 1
0x1800160bc  xor     eax, ecx
0x1800160be  mov     r8d, eax
0x1800160c1  xor     r8d, edi
0x1800160c4  and     r8d, 800h
0x1800160cb  xor     r8d, eax
0x1800160ce  or      r8d, 2
0x1800160d2  mov     [rbx], r8d
0x1800160d5  jmp     short loc_1800160DA
0x1800160d7  mov     r8d, edx
0x1800160da  mov     r9d, edx
0x1800160dd  and     r9d, 4
0x1800160e1  jnz     short loc_1800160F8
0x1800160e3  mov     ecx, edi
0x1800160e5  xor     ecx, r8d
0x1800160e8  and     ecx, 400h
0x1800160ee  xor     ecx, r8d
0x1800160f1  or      ecx, 4
0x1800160f4  mov     [rbx], ecx
0x1800160f6  jmp     short loc_1800160FB
0x1800160f8  mov     ecx, r8d
0x1800160fb  mov     eax, edx
0x1800160fd  lock cmpxchg [rsi], ecx
0x180016101  jnz     short loc_180016091
0x180016103  test    r9d, r9d
0x180016106  jnz     short loc_180016117
0x180016108  mov     r8d, ebp
0x18001610b  lea     edx, [r9+3]
0x18001610f  mov     rcx, rsi
0x180016112  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180016117  test    byte ptr [rbx], 2
0x18001611a  jnz     short loc_180016146
0x18001611c  mov     eax, [rbx]
0x18001611e  xor     eax, edi
0x180016120  and     eax, 180h
0x180016125  xor     eax, [rbx]
0x180016127  mov     ecx, eax
0x180016129  xor     ecx, edi
0x18001612b  and     ecx, r15d
0x18001612e  xor     ecx, eax
0x180016130  mov     edx, ecx
0x180016132  xor     edx, edi
0x180016134  and     edx, 1
0x180016137  xor     edx, ecx
0x180016139  mov     eax, edx
0x18001613b  xor     eax, edi
0x18001613d  and     eax, 800h
0x180016142  xor     eax, edx
0x180016144  mov     [rbx], eax
0x180016146  mov     rbp, [rsp+38h+arg_10]
0x18001614b  mov     rax, rbx
0x18001614e  mov     rbx, [rsp+38h+arg_8]
0x180016153  add     rsp, 20h
0x180016157  pop     r15
0x180016159  pop     rdi
0x18001615a  pop     rsi
0x18001615b  retn
```
