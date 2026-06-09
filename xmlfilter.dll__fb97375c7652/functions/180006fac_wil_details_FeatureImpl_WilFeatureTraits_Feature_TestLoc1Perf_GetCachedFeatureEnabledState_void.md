# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x180006fac`
- end: `0x180007085`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d4cc`

## callees

- `0x180005dd0`
- `0x180006fac`
- `0x180007960`
- `0x18000c3f0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestLoc1Perf__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_TestLoc1Perf__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180006fac  mov     [rsp+arg_10], rbx
0x180006fb1  mov     [rsp+arg_0], rcx
0x180006fb6  push    rbp
0x180006fb7  push    rsi
0x180006fb8  push    rdi
0x180006fb9  sub     rsp, 20h
0x180006fbd  mov     rsi, cs:Feature_TestLoc1Perf__descriptor
0x180006fc4  mov     rdi, rdx
0x180006fc7  mov     qword ptr [rdx], 0
0x180006fce  mov     eax, [rsi]
0x180006fd0  mov     [rdx], eax
0x180006fd2  and     eax, 6
0x180006fd5  cmp     al, 6
0x180006fd7  jz      loc_180007075
0x180006fdd  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180006fe2  lea     r8, [rsp+38h+arg_0]
0x180006fe7  mov     dword ptr [rsp+38h+arg_0], 0
0x180006fef  lea     rdx, [rsp+38h+arg_8]
0x180006ff4  mov     ebp, eax
0x180006ff6  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x180006ffb  mov     eax, [rdi]
0x180006ffd  mov     rbx, [rsp+38h+arg_8]
0x180007002  cmp     dword ptr [rsp+38h+arg_0], 0
0x180007007  mov     edx, eax
0x180007009  mov     [rdi], eax
0x18000700b  mov     ecx, eax
0x18000700d  jz      short loc_180007028
0x18000700f  test    dl, 2
0x180007012  jnz     short loc_180007028
0x180007014  and     ecx, 0FFFFF63Eh
0x18000701a  mov     eax, ebx
0x18000701c  and     eax, 9C1h
0x180007021  or      ecx, eax
0x180007023  or      ecx, 2
0x180007026  mov     [rdi], ecx
0x180007028  mov     r8d, edx
0x18000702b  and     r8d, 4
0x18000702f  jnz     short loc_180007043
0x180007031  btr     ecx, 0Ah
0x180007035  mov     eax, ebx
0x180007037  and     eax, 400h
0x18000703c  or      ecx, eax
0x18000703e  or      ecx, 4
0x180007041  mov     [rdi], ecx
0x180007043  mov     eax, edx
0x180007045  lock cmpxchg [rsi], ecx
0x180007049  jnz     short loc_180007002
0x18000704b  test    r8d, r8d
0x18000704e  jnz     short loc_180007060
0x180007050  mov     r8d, ebp
0x180007053  mov     edx, 3
0x180007058  mov     rcx, rsi
0x18000705b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180007060  mov     eax, [rdi]
0x180007062  test    al, 2
0x180007064  jnz     short loc_180007075
0x180007066  and     eax, 0FFFFF63Eh
0x18000706b  and     ebx, 9C1h
0x180007071  or      eax, ebx
0x180007073  mov     [rdi], eax
0x180007075  mov     rbx, [rsp+38h+arg_10]
0x18000707a  mov     rax, rdi
0x18000707d  add     rsp, 20h
0x180007081  pop     rdi
0x180007082  pop     rsi
0x180007083  pop     rbp
0x180007084  retn
```
