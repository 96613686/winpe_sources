# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x180015b24`
- end: `0x180015c10`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `236`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001691c`
- `0x180016d78`

## callees

- `0x180008a90`
- `0x18000cdac`
- `0x180010298`
- `0x180015b24`
- `0x180016118`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 v5; // rcx
  signed __int32 v6; // eax
  __int16 v7; // bx
  bool v8; // zf
  signed __int32 v9; // edx
  unsigned int v10; // ecx
  __int64 v12; // [rsp+20h] [rbp-48h] BYREF
  int v13; // [rsp+28h] [rbp-40h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(v5, &v12, &v13);
    v6 = *(_DWORD *)a2;
    v7 = v12;
    do
    {
      v8 = v13 == 0;
      v9 = v6;
      *(_DWORD *)a2 = v6;
      v10 = v6;
      if ( !v8 && (v6 & 2) == 0 )
      {
        v10 = v7 & 0x9C1 | v6 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v10;
      }
      if ( (v6 & 4) == 0 )
      {
        v10 = v7 & 0x400 | v10 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v10;
      }
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestLoc1Perf__descriptor, v10, v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_TestLoc1Perf__descriptor,
        3,
        v4);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v7 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180015b24  push    rbx
0x180015b26  push    rbp
0x180015b27  push    rsi
0x180015b28  push    rdi
0x180015b29  sub     rsp, 48h
0x180015b2d  mov     rax, cs:__security_cookie
0x180015b34  xor     rax, rsp
0x180015b37  mov     [rsp+68h+var_38], rax
0x180015b3c  mov     rsi, cs:Feature_TestLoc1Perf__descriptor
0x180015b43  mov     rdi, rdx
0x180015b46  mov     qword ptr [rdx], 0
0x180015b4d  mov     eax, [rsi]
0x180015b4f  mov     [rdx], eax
0x180015b51  and     eax, 6
0x180015b54  cmp     al, 6
0x180015b56  jz      loc_180015BF6
0x180015b5c  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180015b61  lea     r8, [rsp+68h+var_40]
0x180015b66  mov     [rsp+68h+var_40], 0
0x180015b6e  lea     rdx, [rsp+68h+var_48]
0x180015b73  mov     ebp, eax
0x180015b75  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x180015b7a  mov     eax, [rdi]
0x180015b7c  mov     rbx, [rsp+68h+var_48]
0x180015b81  cmp     [rsp+68h+var_40], 0
0x180015b86  mov     edx, eax
0x180015b88  mov     [rdi], eax
0x180015b8a  mov     ecx, eax
0x180015b8c  jz      short loc_180015BA7
0x180015b8e  test    dl, 2
0x180015b91  jnz     short loc_180015BA7
0x180015b93  and     ecx, 0FFFFF63Eh
0x180015b99  mov     eax, ebx
0x180015b9b  and     eax, 9C1h
0x180015ba0  or      ecx, eax
0x180015ba2  or      ecx, 2
0x180015ba5  mov     [rdi], ecx
0x180015ba7  mov     r8d, edx
0x180015baa  and     r8d, 4
0x180015bae  jnz     short loc_180015BC2
0x180015bb0  btr     ecx, 0Ah
0x180015bb4  mov     eax, ebx
0x180015bb6  and     eax, 400h
0x180015bbb  or      ecx, eax
0x180015bbd  or      ecx, 4
0x180015bc0  mov     [rdi], ecx
0x180015bc2  mov     eax, edx
0x180015bc4  lock cmpxchg [rsi], ecx
0x180015bc8  jnz     short loc_180015B81
0x180015bca  test    r8d, r8d
0x180015bcd  jnz     short loc_180015BDF
0x180015bcf  mov     r8d, ebp
0x180015bd2  mov     edx, 3
0x180015bd7  mov     rcx, rsi
0x180015bda  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180015bdf  mov     ecx, [rdi]
0x180015be1  test    cl, 2
0x180015be4  jnz     short loc_180015BF6
0x180015be6  and     ecx, 0FFFFF63Eh
0x180015bec  and     ebx, 9C1h
0x180015bf2  or      ecx, ebx
0x180015bf4  mov     [rdi], ecx
0x180015bf6  mov     rax, rdi
0x180015bf9  mov     rcx, [rsp+68h+var_38]
0x180015bfe  xor     rcx, rsp; StackCookie
0x180015c01  call    __security_check_cookie
0x180015c06  add     rsp, 48h
0x180015c0a  pop     rdi
0x180015c0b  pop     rsi
0x180015c0c  pop     rbp
0x180015c0d  pop     rbx
0x180015c0e  retn
```
