# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x180017818`
- end: `0x1800178f1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001901c`

## callees

- `0x180016be8`
- `0x180017818`
- `0x180017f68`
- `0x180018da4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestAccPerf__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_TestAccPerf__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180017818  mov     [rsp+arg_10], rbx
0x18001781d  mov     [rsp+arg_0], rcx
0x180017822  push    rbp
0x180017823  push    rsi
0x180017824  push    rdi
0x180017825  sub     rsp, 20h
0x180017829  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x180017830  mov     rdi, rdx
0x180017833  mov     qword ptr [rdx], 0
0x18001783a  mov     eax, [rsi]
0x18001783c  mov     [rdx], eax
0x18001783e  and     eax, 6
0x180017841  cmp     al, 6
0x180017843  jz      loc_1800178E1
0x180017849  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001784e  lea     r8, [rsp+38h+arg_0]
0x180017853  mov     dword ptr [rsp+38h+arg_0], 0
0x18001785b  lea     rdx, [rsp+38h+arg_8]
0x180017860  mov     ebp, eax
0x180017862  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x180017867  mov     eax, [rdi]
0x180017869  mov     rbx, [rsp+38h+arg_8]
0x18001786e  cmp     dword ptr [rsp+38h+arg_0], 0
0x180017873  mov     edx, eax
0x180017875  mov     [rdi], eax
0x180017877  mov     ecx, eax
0x180017879  jz      short loc_180017894
0x18001787b  test    dl, 2
0x18001787e  jnz     short loc_180017894
0x180017880  and     ecx, 0FFFFF63Eh
0x180017886  mov     eax, ebx
0x180017888  and     eax, 9C1h
0x18001788d  or      ecx, eax
0x18001788f  or      ecx, 2
0x180017892  mov     [rdi], ecx
0x180017894  mov     r8d, edx
0x180017897  and     r8d, 4
0x18001789b  jnz     short loc_1800178AF
0x18001789d  btr     ecx, 0Ah
0x1800178a1  mov     eax, ebx
0x1800178a3  and     eax, 400h
0x1800178a8  or      ecx, eax
0x1800178aa  or      ecx, 4
0x1800178ad  mov     [rdi], ecx
0x1800178af  mov     eax, edx
0x1800178b1  lock cmpxchg [rsi], ecx
0x1800178b5  jnz     short loc_18001786E
0x1800178b7  test    r8d, r8d
0x1800178ba  jnz     short loc_1800178CC
0x1800178bc  mov     r8d, ebp
0x1800178bf  mov     edx, 3
0x1800178c4  mov     rcx, rsi
0x1800178c7  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800178cc  mov     eax, [rdi]
0x1800178ce  test    al, 2
0x1800178d0  jnz     short loc_1800178E1
0x1800178d2  and     eax, 0FFFFF63Eh
0x1800178d7  and     ebx, 9C1h
0x1800178dd  or      eax, ebx
0x1800178df  mov     [rdi], eax
0x1800178e1  mov     rbx, [rsp+38h+arg_10]
0x1800178e6  mov     rax, rdi
0x1800178e9  add     rsp, 20h
0x1800178ed  pop     rdi
0x1800178ee  pop     rsi
0x1800178ef  pop     rbp
0x1800178f0  retn
```
