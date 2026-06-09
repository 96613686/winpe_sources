# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e150`
- end: `0x18000e229`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fd58`
- `0x180011884`

## callees

- `0x18000d020`
- `0x18000e150`
- `0x18000e990`
- `0x1800105e0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  int v5; // ebp
  __int64 v6; // rcx
  int *v7; // r9
  signed __int32 v8; // eax
  __int16 v9; // bx
  bool v10; // zf
  signed __int32 v11; // edx
  unsigned int v12; // ecx
  wil::details *v14; // [rsp+40h] [rbp+8h] BYREF
  __int64 v15; // [rsp+48h] [rbp+10h] BYREF

  v14 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(
      v6,
      &v15,
      (enum FEATURE_CHANGE_TIME)&v14,
      v7);
    v8 = *(_DWORD *)a2;
    v9 = v15;
    do
    {
      v10 = (_DWORD)v14 == 0;
      v11 = v8;
      *(_DWORD *)a2 = v8;
      v12 = v8;
      if ( !v10 && (v8 & 2) == 0 )
      {
        v12 = v9 & 0x9C1 | v8 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v12;
      }
      if ( (v8 & 4) == 0 )
      {
        v12 = v9 & 0x400 | v12 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v12;
      }
      v8 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestAccPerf__descriptor, v12, v8);
    }
    while ( v11 != v8 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_TestAccPerf__descriptor,
        3,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v9 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18000e150  mov     [rsp+arg_10], rbx
0x18000e155  mov     [rsp+arg_0], rcx
0x18000e15a  push    rbp
0x18000e15b  push    rsi
0x18000e15c  push    rdi
0x18000e15d  sub     rsp, 20h
0x18000e161  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x18000e168  mov     rdi, rdx
0x18000e16b  mov     qword ptr [rdx], 0
0x18000e172  mov     eax, [rsi]
0x18000e174  mov     [rdx], eax
0x18000e176  and     eax, 6
0x18000e179  cmp     al, 6
0x18000e17b  jz      loc_18000E219
0x18000e181  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e186  lea     r8, [rsp+38h+arg_0]
0x18000e18b  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e193  lea     rdx, [rsp+38h+arg_8]
0x18000e198  mov     ebp, eax
0x18000e19a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x18000e19f  mov     eax, [rdi]
0x18000e1a1  mov     rbx, [rsp+38h+arg_8]
0x18000e1a6  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e1ab  mov     edx, eax
0x18000e1ad  mov     [rdi], eax
0x18000e1af  mov     ecx, eax
0x18000e1b1  jz      short loc_18000E1CC
0x18000e1b3  test    dl, 2
0x18000e1b6  jnz     short loc_18000E1CC
0x18000e1b8  and     ecx, 0FFFFF63Eh
0x18000e1be  mov     eax, ebx
0x18000e1c0  and     eax, 9C1h
0x18000e1c5  or      ecx, eax
0x18000e1c7  or      ecx, 2
0x18000e1ca  mov     [rdi], ecx
0x18000e1cc  mov     r8d, edx
0x18000e1cf  and     r8d, 4
0x18000e1d3  jnz     short loc_18000E1E7
0x18000e1d5  btr     ecx, 0Ah
0x18000e1d9  mov     eax, ebx
0x18000e1db  and     eax, 400h
0x18000e1e0  or      ecx, eax
0x18000e1e2  or      ecx, 4
0x18000e1e5  mov     [rdi], ecx
0x18000e1e7  mov     eax, edx
0x18000e1e9  lock cmpxchg [rsi], ecx
0x18000e1ed  jnz     short loc_18000E1A6
0x18000e1ef  test    r8d, r8d
0x18000e1f2  jnz     short loc_18000E204
0x18000e1f4  mov     r8d, ebp
0x18000e1f7  mov     edx, 3
0x18000e1fc  mov     rcx, rsi
0x18000e1ff  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e204  mov     eax, [rdi]
0x18000e206  test    al, 2
0x18000e208  jnz     short loc_18000E219
0x18000e20a  and     eax, 0FFFFF63Eh
0x18000e20f  and     ebx, 9C1h
0x18000e215  or      eax, ebx
0x18000e217  mov     [rdi], eax
0x18000e219  mov     rbx, [rsp+38h+arg_10]
0x18000e21e  mov     rax, rdi
0x18000e221  add     rsp, 20h
0x18000e225  pop     rdi
0x18000e226  pop     rsi
0x18000e227  pop     rbp
0x18000e228  retn
```
