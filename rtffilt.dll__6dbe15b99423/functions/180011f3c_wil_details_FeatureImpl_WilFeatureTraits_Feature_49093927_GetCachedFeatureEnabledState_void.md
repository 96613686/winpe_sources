# wil::details::FeatureImpl<__WilFeatureTraits_Feature_49093927>::GetCachedFeatureEnabledState(void)

- ea: `0x180011f3c`
- end: `0x180012015`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_49093927@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001522c`

## callees

- `0x180005dd8`
- `0x18000b3d8`
- `0x180011f3c`
- `0x1800133b4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_49093927>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 v5; // rcx
  signed __int32 v6; // eax
  __int16 v7; // bx
  signed __int32 v8; // edx
  unsigned int v9; // ecx
  __int64 v11; // [rsp+48h] [rbp+10h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_49093927__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_49093927__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_49093927>::GetCurrentFeatureEnabledState(v5, &v11);
    v6 = *(_DWORD *)a2;
    v7 = v11;
    do
    {
      v8 = v6;
      *(_DWORD *)a2 = v6;
      v9 = v6;
      if ( (v6 & 4) == 0 )
      {
        v9 = v7 & 0x400 | v6 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v9;
      }
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_49093927__descriptor, v9, v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_49093927__descriptor,
        3u,
        v4);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v7 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180011f3c  mov     [rsp+arg_10], rbx
0x180011f41  mov     [rsp+arg_0], rcx
0x180011f46  push    rbp
0x180011f47  push    rsi
0x180011f48  push    rdi
0x180011f49  sub     rsp, 20h
0x180011f4d  mov     rsi, cs:Feature_49093927__descriptor
0x180011f54  mov     rdi, rdx
0x180011f57  mov     qword ptr [rdx], 0
0x180011f5e  mov     eax, [rsi]
0x180011f60  mov     [rdx], eax
0x180011f62  and     eax, 6
0x180011f65  cmp     al, 6
0x180011f67  jz      loc_180012005
0x180011f6d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180011f72  lea     r8, [rsp+38h+arg_0]
0x180011f77  mov     dword ptr [rsp+38h+arg_0], 0
0x180011f7f  lea     rdx, [rsp+38h+arg_8]
0x180011f84  mov     ebp, eax
0x180011f86  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_49093927@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_49093927>::GetCurrentFeatureEnabledState(int *)
0x180011f8b  mov     eax, [rdi]
0x180011f8d  mov     rbx, [rsp+38h+arg_8]
0x180011f92  cmp     dword ptr [rsp+38h+arg_0], 0
0x180011f97  mov     edx, eax
0x180011f99  mov     [rdi], eax
0x180011f9b  mov     ecx, eax
0x180011f9d  jz      short loc_180011FB8
0x180011f9f  test    dl, 2
0x180011fa2  jnz     short loc_180011FB8
0x180011fa4  and     ecx, 0FFFFF63Eh
0x180011faa  mov     eax, ebx
0x180011fac  and     eax, 9C1h
0x180011fb1  or      ecx, eax
0x180011fb3  or      ecx, 2
0x180011fb6  mov     [rdi], ecx
0x180011fb8  mov     r8d, edx
0x180011fbb  and     r8d, 4
0x180011fbf  jnz     short loc_180011FD3
0x180011fc1  btr     ecx, 0Ah
0x180011fc5  mov     eax, ebx
0x180011fc7  and     eax, 400h
0x180011fcc  or      ecx, eax
0x180011fce  or      ecx, 4
0x180011fd1  mov     [rdi], ecx
0x180011fd3  mov     eax, edx
0x180011fd5  lock cmpxchg [rsi], ecx
0x180011fd9  jnz     short loc_180011F92
0x180011fdb  test    r8d, r8d
0x180011fde  jnz     short loc_180011FF0
0x180011fe0  mov     r8d, ebp
0x180011fe3  mov     edx, 3
0x180011fe8  mov     rcx, rsi
0x180011feb  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180011ff0  mov     eax, [rdi]
0x180011ff2  test    al, 2
0x180011ff4  jnz     short loc_180012005
0x180011ff6  and     eax, 0FFFFF63Eh
0x180011ffb  and     ebx, 9C1h
0x180012001  or      eax, ebx
0x180012003  mov     [rdi], eax
0x180012005  mov     rbx, [rsp+38h+arg_10]
0x18001200a  mov     rax, rdi
0x18001200d  add     rsp, 20h
0x180012011  pop     rdi
0x180012012  pop     rsi
0x180012013  pop     rbp
0x180012014  retn
```
