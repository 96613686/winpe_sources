# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180010ee4`
- end: `0x180010fbd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011da8`

## callees

- `0x180005384`
- `0x180009148`
- `0x180010ee4`
- `0x18001108c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValLabTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_ValLabTest__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180010ee4  mov     [rsp+arg_10], rbx
0x180010ee9  mov     [rsp+arg_0], rcx
0x180010eee  push    rbp
0x180010eef  push    rsi
0x180010ef0  push    rdi
0x180010ef1  sub     rsp, 20h
0x180010ef5  mov     rsi, cs:Feature_ValLabTest__descriptor
0x180010efc  mov     rdi, rdx
0x180010eff  mov     qword ptr [rdx], 0
0x180010f06  mov     eax, [rsi]
0x180010f08  mov     [rdx], eax
0x180010f0a  and     eax, 6
0x180010f0d  cmp     al, 6
0x180010f0f  jz      loc_180010FAD
0x180010f15  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180010f1a  lea     r8, [rsp+38h+arg_0]
0x180010f1f  mov     dword ptr [rsp+38h+arg_0], 0
0x180010f27  lea     rdx, [rsp+38h+arg_8]
0x180010f2c  mov     ebp, eax
0x180010f2e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(int *)
0x180010f33  mov     eax, [rdi]
0x180010f35  mov     rbx, [rsp+38h+arg_8]
0x180010f3a  cmp     dword ptr [rsp+38h+arg_0], 0
0x180010f3f  mov     edx, eax
0x180010f41  mov     [rdi], eax
0x180010f43  mov     ecx, eax
0x180010f45  jz      short loc_180010F60
0x180010f47  test    dl, 2
0x180010f4a  jnz     short loc_180010F60
0x180010f4c  and     ecx, 0FFFFF63Eh
0x180010f52  mov     eax, ebx
0x180010f54  and     eax, 9C1h
0x180010f59  or      ecx, eax
0x180010f5b  or      ecx, 2
0x180010f5e  mov     [rdi], ecx
0x180010f60  mov     r8d, edx
0x180010f63  and     r8d, 4
0x180010f67  jnz     short loc_180010F7B
0x180010f69  btr     ecx, 0Ah
0x180010f6d  mov     eax, ebx
0x180010f6f  and     eax, 400h
0x180010f74  or      ecx, eax
0x180010f76  or      ecx, 4
0x180010f79  mov     [rdi], ecx
0x180010f7b  mov     eax, edx
0x180010f7d  lock cmpxchg [rsi], ecx
0x180010f81  jnz     short loc_180010F3A
0x180010f83  test    r8d, r8d
0x180010f86  jnz     short loc_180010F98
0x180010f88  mov     r8d, ebp
0x180010f8b  mov     edx, 3
0x180010f90  mov     rcx, rsi
0x180010f93  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180010f98  mov     eax, [rdi]
0x180010f9a  test    al, 2
0x180010f9c  jnz     short loc_180010FAD
0x180010f9e  and     eax, 0FFFFF63Eh
0x180010fa3  and     ebx, 9C1h
0x180010fa9  or      eax, ebx
0x180010fab  mov     [rdi], eax
0x180010fad  mov     rbx, [rsp+38h+arg_10]
0x180010fb2  mov     rax, rdi
0x180010fb5  add     rsp, 20h
0x180010fb9  pop     rdi
0x180010fba  pop     rsi
0x180010fbb  pop     rbp
0x180010fbc  retn
```
