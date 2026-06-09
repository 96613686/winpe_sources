# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc02>::GetCachedFeatureEnabledState(void)

- ea: `0x18001f518`
- end: `0x18001f5f1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc02@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025188`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x18001f518`
- `0x18001fff0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc02>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestLoc02__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestLoc02__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc02>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestLoc02__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_TestLoc02__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18001f518  mov     [rsp+arg_10], rbx
0x18001f51d  mov     [rsp+arg_0], rcx
0x18001f522  push    rbp
0x18001f523  push    rsi
0x18001f524  push    rdi
0x18001f525  sub     rsp, 20h
0x18001f529  mov     rsi, cs:Feature_TestLoc02__descriptor
0x18001f530  mov     rdi, rdx
0x18001f533  mov     qword ptr [rdx], 0
0x18001f53a  mov     eax, [rsi]
0x18001f53c  mov     [rdx], eax
0x18001f53e  and     eax, 6
0x18001f541  cmp     al, 6
0x18001f543  jz      loc_18001F5E1
0x18001f549  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001f54e  lea     r8, [rsp+38h+arg_0]
0x18001f553  mov     dword ptr [rsp+38h+arg_0], 0
0x18001f55b  lea     rdx, [rsp+38h+arg_8]
0x18001f560  mov     ebp, eax
0x18001f562  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc02@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc02>::GetCurrentFeatureEnabledState(int *)
0x18001f567  mov     eax, [rdi]
0x18001f569  mov     rbx, [rsp+38h+arg_8]
0x18001f56e  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001f573  mov     edx, eax
0x18001f575  mov     [rdi], eax
0x18001f577  mov     ecx, eax
0x18001f579  jz      short loc_18001F594
0x18001f57b  test    dl, 2
0x18001f57e  jnz     short loc_18001F594
0x18001f580  and     ecx, 0FFFFF63Eh
0x18001f586  mov     eax, ebx
0x18001f588  and     eax, 9C1h
0x18001f58d  or      ecx, eax
0x18001f58f  or      ecx, 2
0x18001f592  mov     [rdi], ecx
0x18001f594  mov     r8d, edx
0x18001f597  and     r8d, 4
0x18001f59b  jnz     short loc_18001F5AF
0x18001f59d  btr     ecx, 0Ah
0x18001f5a1  mov     eax, ebx
0x18001f5a3  and     eax, 400h
0x18001f5a8  or      ecx, eax
0x18001f5aa  or      ecx, 4
0x18001f5ad  mov     [rdi], ecx
0x18001f5af  mov     eax, edx
0x18001f5b1  lock cmpxchg [rsi], ecx
0x18001f5b5  jnz     short loc_18001F56E
0x18001f5b7  test    r8d, r8d
0x18001f5ba  jnz     short loc_18001F5CC
0x18001f5bc  mov     r8d, ebp
0x18001f5bf  mov     edx, 3
0x18001f5c4  mov     rcx, rsi
0x18001f5c7  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001f5cc  mov     eax, [rdi]
0x18001f5ce  test    al, 2
0x18001f5d0  jnz     short loc_18001F5E1
0x18001f5d2  and     eax, 0FFFFF63Eh
0x18001f5d7  and     ebx, 9C1h
0x18001f5dd  or      eax, ebx
0x18001f5df  mov     [rdi], eax
0x18001f5e1  mov     rbx, [rsp+38h+arg_10]
0x18001f5e6  mov     rax, rdi
0x18001f5e9  add     rsp, 20h
0x18001f5ed  pop     rdi
0x18001f5ee  pop     rsi
0x18001f5ef  pop     rbp
0x18001f5f0  retn
```
