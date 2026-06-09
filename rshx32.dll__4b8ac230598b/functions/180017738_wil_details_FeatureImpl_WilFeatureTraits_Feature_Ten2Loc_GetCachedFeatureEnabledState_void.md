# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(void)

- ea: `0x180017738`
- end: `0x180017811`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018f80`

## callees

- `0x180016be8`
- `0x180017738`
- `0x180017df8`
- `0x180018da4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebp
  __int64 v6; // rcx
  signed __int32 v7; // eax
  __int16 v8; // bx
  bool v9; // zf
  signed __int32 v10; // edx
  unsigned int v11; // ecx
  wil::details *v13; // [rsp+40h] [rbp+8h] BYREF
  __int64 v14; // [rsp+48h] [rbp+10h] BYREF

  v13 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
    v7 = *(_DWORD *)a2;
    v8 = v14;
    do
    {
      v9 = (_DWORD)v13 == 0;
      v10 = v7;
      *(_DWORD *)a2 = v7;
      v11 = v7;
      if ( !v9 && (v7 & 2) == 0 )
      {
        v11 = v8 & 0x9C1 | v7 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v11;
      }
      if ( (v7 & 4) == 0 )
      {
        v11 = v8 & 0x400 | v11 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v11;
      }
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Ten2Loc__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Ten2Loc__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180017738  mov     [rsp+arg_10], rbx
0x18001773d  mov     [rsp+arg_0], rcx
0x180017742  push    rbp
0x180017743  push    rsi
0x180017744  push    rdi
0x180017745  sub     rsp, 20h
0x180017749  mov     rsi, cs:Feature_Ten2Loc__descriptor
0x180017750  mov     rdi, rdx
0x180017753  mov     qword ptr [rdx], 0
0x18001775a  mov     eax, [rsi]
0x18001775c  mov     [rdx], eax
0x18001775e  and     eax, 6
0x180017761  cmp     al, 6
0x180017763  jz      loc_180017801
0x180017769  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001776e  lea     r8, [rsp+38h+arg_0]
0x180017773  mov     dword ptr [rsp+38h+arg_0], 0
0x18001777b  lea     rdx, [rsp+38h+arg_8]
0x180017780  mov     ebp, eax
0x180017782  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)
0x180017787  mov     eax, [rdi]
0x180017789  mov     rbx, [rsp+38h+arg_8]
0x18001778e  cmp     dword ptr [rsp+38h+arg_0], 0
0x180017793  mov     edx, eax
0x180017795  mov     [rdi], eax
0x180017797  mov     ecx, eax
0x180017799  jz      short loc_1800177B4
0x18001779b  test    dl, 2
0x18001779e  jnz     short loc_1800177B4
0x1800177a0  and     ecx, 0FFFFF63Eh
0x1800177a6  mov     eax, ebx
0x1800177a8  and     eax, 9C1h
0x1800177ad  or      ecx, eax
0x1800177af  or      ecx, 2
0x1800177b2  mov     [rdi], ecx
0x1800177b4  mov     r8d, edx
0x1800177b7  and     r8d, 4
0x1800177bb  jnz     short loc_1800177CF
0x1800177bd  btr     ecx, 0Ah
0x1800177c1  mov     eax, ebx
0x1800177c3  and     eax, 400h
0x1800177c8  or      ecx, eax
0x1800177ca  or      ecx, 4
0x1800177cd  mov     [rdi], ecx
0x1800177cf  mov     eax, edx
0x1800177d1  lock cmpxchg [rsi], ecx
0x1800177d5  jnz     short loc_18001778E
0x1800177d7  test    r8d, r8d
0x1800177da  jnz     short loc_1800177EC
0x1800177dc  mov     r8d, ebp
0x1800177df  mov     edx, 3
0x1800177e4  mov     rcx, rsi
0x1800177e7  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800177ec  mov     eax, [rdi]
0x1800177ee  test    al, 2
0x1800177f0  jnz     short loc_180017801
0x1800177f2  and     eax, 0FFFFF63Eh
0x1800177f7  and     ebx, 9C1h
0x1800177fd  or      eax, ebx
0x1800177ff  mov     [rdi], eax
0x180017801  mov     rbx, [rsp+38h+arg_10]
0x180017806  mov     rax, rdi
0x180017809  add     rsp, 20h
0x18001780d  pop     rdi
0x18001780e  pop     rsi
0x18001780f  pop     rbp
0x180017810  retn
```
