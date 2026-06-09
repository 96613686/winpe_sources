# wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::GetCachedFeatureEnabledState(void)

- ea: `0x180011e5c`
- end: `0x180011f35`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015190`

## callees

- `0x180005dd8`
- `0x18000b3d8`
- `0x180011e5c`
- `0x1800131e0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_47942714__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_47942714__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::GetCurrentFeatureEnabledState(v5, &v11);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_47942714__descriptor, v9, v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_47942714__descriptor,
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
0x180011e5c  mov     [rsp+arg_10], rbx
0x180011e61  mov     [rsp+arg_0], rcx
0x180011e66  push    rbp
0x180011e67  push    rsi
0x180011e68  push    rdi
0x180011e69  sub     rsp, 20h
0x180011e6d  mov     rsi, cs:Feature_47942714__descriptor
0x180011e74  mov     rdi, rdx
0x180011e77  mov     qword ptr [rdx], 0
0x180011e7e  mov     eax, [rsi]
0x180011e80  mov     [rdx], eax
0x180011e82  and     eax, 6
0x180011e85  cmp     al, 6
0x180011e87  jz      loc_180011F25
0x180011e8d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180011e92  lea     r8, [rsp+38h+arg_0]
0x180011e97  mov     dword ptr [rsp+38h+arg_0], 0
0x180011e9f  lea     rdx, [rsp+38h+arg_8]
0x180011ea4  mov     ebp, eax
0x180011ea6  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::GetCurrentFeatureEnabledState(int *)
0x180011eab  mov     eax, [rdi]
0x180011ead  mov     rbx, [rsp+38h+arg_8]
0x180011eb2  cmp     dword ptr [rsp+38h+arg_0], 0
0x180011eb7  mov     edx, eax
0x180011eb9  mov     [rdi], eax
0x180011ebb  mov     ecx, eax
0x180011ebd  jz      short loc_180011ED8
0x180011ebf  test    dl, 2
0x180011ec2  jnz     short loc_180011ED8
0x180011ec4  and     ecx, 0FFFFF63Eh
0x180011eca  mov     eax, ebx
0x180011ecc  and     eax, 9C1h
0x180011ed1  or      ecx, eax
0x180011ed3  or      ecx, 2
0x180011ed6  mov     [rdi], ecx
0x180011ed8  mov     r8d, edx
0x180011edb  and     r8d, 4
0x180011edf  jnz     short loc_180011EF3
0x180011ee1  btr     ecx, 0Ah
0x180011ee5  mov     eax, ebx
0x180011ee7  and     eax, 400h
0x180011eec  or      ecx, eax
0x180011eee  or      ecx, 4
0x180011ef1  mov     [rdi], ecx
0x180011ef3  mov     eax, edx
0x180011ef5  lock cmpxchg [rsi], ecx
0x180011ef9  jnz     short loc_180011EB2
0x180011efb  test    r8d, r8d
0x180011efe  jnz     short loc_180011F10
0x180011f00  mov     r8d, ebp
0x180011f03  mov     edx, 3
0x180011f08  mov     rcx, rsi
0x180011f0b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180011f10  mov     eax, [rdi]
0x180011f12  test    al, 2
0x180011f14  jnz     short loc_180011F25
0x180011f16  and     eax, 0FFFFF63Eh
0x180011f1b  and     ebx, 9C1h
0x180011f21  or      eax, ebx
0x180011f23  mov     [rdi], eax
0x180011f25  mov     rbx, [rsp+38h+arg_10]
0x180011f2a  mov     rax, rdi
0x180011f2d  add     rsp, 20h
0x180011f31  pop     rdi
0x180011f32  pop     rsi
0x180011f33  pop     rbp
0x180011f34  retn
```
