# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(void)

- ea: `0x18001365c`
- end: `0x180013735`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001772c`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x18001365c`
- `0x180013fc4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_UexTest7__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UexTest7__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UexTest7__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_UexTest7__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18001365c  mov     [rsp+arg_10], rbx
0x180013661  mov     [rsp+arg_0], rcx
0x180013666  push    rbp
0x180013667  push    rsi
0x180013668  push    rdi
0x180013669  sub     rsp, 20h
0x18001366d  mov     rsi, cs:Feature_UexTest7__descriptor
0x180013674  mov     rdi, rdx
0x180013677  mov     qword ptr [rdx], 0
0x18001367e  mov     eax, [rsi]
0x180013680  mov     [rdx], eax
0x180013682  and     eax, 6
0x180013685  cmp     al, 6
0x180013687  jz      loc_180013725
0x18001368d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013692  lea     r8, [rsp+38h+arg_0]
0x180013697  mov     dword ptr [rsp+38h+arg_0], 0
0x18001369f  lea     rdx, [rsp+38h+arg_8]
0x1800136a4  mov     ebp, eax
0x1800136a6  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)
0x1800136ab  mov     eax, [rdi]
0x1800136ad  mov     rbx, [rsp+38h+arg_8]
0x1800136b2  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800136b7  mov     edx, eax
0x1800136b9  mov     [rdi], eax
0x1800136bb  mov     ecx, eax
0x1800136bd  jz      short loc_1800136D8
0x1800136bf  test    dl, 2
0x1800136c2  jnz     short loc_1800136D8
0x1800136c4  and     ecx, 0FFFFF63Eh
0x1800136ca  mov     eax, ebx
0x1800136cc  and     eax, 9C1h
0x1800136d1  or      ecx, eax
0x1800136d3  or      ecx, 2
0x1800136d6  mov     [rdi], ecx
0x1800136d8  mov     r8d, edx
0x1800136db  and     r8d, 4
0x1800136df  jnz     short loc_1800136F3
0x1800136e1  btr     ecx, 0Ah
0x1800136e5  mov     eax, ebx
0x1800136e7  and     eax, 400h
0x1800136ec  or      ecx, eax
0x1800136ee  or      ecx, 4
0x1800136f1  mov     [rdi], ecx
0x1800136f3  mov     eax, edx
0x1800136f5  lock cmpxchg [rsi], ecx
0x1800136f9  jnz     short loc_1800136B2
0x1800136fb  test    r8d, r8d
0x1800136fe  jnz     short loc_180013710
0x180013700  mov     r8d, ebp
0x180013703  mov     edx, 3
0x180013708  mov     rcx, rsi
0x18001370b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180013710  mov     eax, [rdi]
0x180013712  test    al, 2
0x180013714  jnz     short loc_180013725
0x180013716  and     eax, 0FFFFF63Eh
0x18001371b  and     ebx, 9C1h
0x180013721  or      eax, ebx
0x180013723  mov     [rdi], eax
0x180013725  mov     rbx, [rsp+38h+arg_10]
0x18001372a  mov     rax, rdi
0x18001372d  add     rsp, 20h
0x180013731  pop     rdi
0x180013732  pop     rsi
0x180013733  pop     rbp
0x180013734  retn
```
