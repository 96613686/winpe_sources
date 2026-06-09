# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x18001373c`
- end: `0x180013815`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800177c8`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x18001373c`
- `0x180014134`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValAccTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValAccTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValAccTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_ValAccTest__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18001373c  mov     [rsp+arg_10], rbx
0x180013741  mov     [rsp+arg_0], rcx
0x180013746  push    rbp
0x180013747  push    rsi
0x180013748  push    rdi
0x180013749  sub     rsp, 20h
0x18001374d  mov     rsi, cs:Feature_ValAccTest__descriptor
0x180013754  mov     rdi, rdx
0x180013757  mov     qword ptr [rdx], 0
0x18001375e  mov     eax, [rsi]
0x180013760  mov     [rdx], eax
0x180013762  and     eax, 6
0x180013765  cmp     al, 6
0x180013767  jz      loc_180013805
0x18001376d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013772  lea     r8, [rsp+38h+arg_0]
0x180013777  mov     dword ptr [rsp+38h+arg_0], 0
0x18001377f  lea     rdx, [rsp+38h+arg_8]
0x180013784  mov     ebp, eax
0x180013786  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x18001378b  mov     eax, [rdi]
0x18001378d  mov     rbx, [rsp+38h+arg_8]
0x180013792  cmp     dword ptr [rsp+38h+arg_0], 0
0x180013797  mov     edx, eax
0x180013799  mov     [rdi], eax
0x18001379b  mov     ecx, eax
0x18001379d  jz      short loc_1800137B8
0x18001379f  test    dl, 2
0x1800137a2  jnz     short loc_1800137B8
0x1800137a4  and     ecx, 0FFFFF63Eh
0x1800137aa  mov     eax, ebx
0x1800137ac  and     eax, 9C1h
0x1800137b1  or      ecx, eax
0x1800137b3  or      ecx, 2
0x1800137b6  mov     [rdi], ecx
0x1800137b8  mov     r8d, edx
0x1800137bb  and     r8d, 4
0x1800137bf  jnz     short loc_1800137D3
0x1800137c1  btr     ecx, 0Ah
0x1800137c5  mov     eax, ebx
0x1800137c7  and     eax, 400h
0x1800137cc  or      ecx, eax
0x1800137ce  or      ecx, 4
0x1800137d1  mov     [rdi], ecx
0x1800137d3  mov     eax, edx
0x1800137d5  lock cmpxchg [rsi], ecx
0x1800137d9  jnz     short loc_180013792
0x1800137db  test    r8d, r8d
0x1800137de  jnz     short loc_1800137F0
0x1800137e0  mov     r8d, ebp
0x1800137e3  mov     edx, 3
0x1800137e8  mov     rcx, rsi
0x1800137eb  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800137f0  mov     eax, [rdi]
0x1800137f2  test    al, 2
0x1800137f4  jnz     short loc_180013805
0x1800137f6  and     eax, 0FFFFF63Eh
0x1800137fb  and     ebx, 9C1h
0x180013801  or      eax, ebx
0x180013803  mov     [rdi], eax
0x180013805  mov     rbx, [rsp+38h+arg_10]
0x18001380a  mov     rax, rdi
0x18001380d  add     rsp, 20h
0x180013811  pop     rdi
0x180013812  pop     rsi
0x180013813  pop     rbp
0x180013814  retn
```
