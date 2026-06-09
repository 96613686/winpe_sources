# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(void)

- ea: `0x180005984`
- end: `0x180005a5d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008524`
- `0x18000af60`

## callees

- `0x180005384`
- `0x180005984`
- `0x180005cd0`
- `0x180009148`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(
      v6,
      &v14,
      &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UxAccOptimization__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_UxAccOptimization__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180005984  mov     [rsp+arg_10], rbx
0x180005989  mov     [rsp+arg_0], rcx
0x18000598e  push    rbp
0x18000598f  push    rsi
0x180005990  push    rdi
0x180005991  sub     rsp, 20h
0x180005995  mov     rsi, cs:Feature_UxAccOptimization__descriptor
0x18000599c  mov     rdi, rdx
0x18000599f  mov     qword ptr [rdx], 0
0x1800059a6  mov     eax, [rsi]
0x1800059a8  mov     [rdx], eax
0x1800059aa  and     eax, 6
0x1800059ad  cmp     al, 6
0x1800059af  jz      loc_180005A4D
0x1800059b5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800059ba  lea     r8, [rsp+38h+arg_0]
0x1800059bf  mov     dword ptr [rsp+38h+arg_0], 0
0x1800059c7  lea     rdx, [rsp+38h+arg_8]
0x1800059cc  mov     ebp, eax
0x1800059ce  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)
0x1800059d3  mov     eax, [rdi]
0x1800059d5  mov     rbx, [rsp+38h+arg_8]
0x1800059da  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800059df  mov     edx, eax
0x1800059e1  mov     [rdi], eax
0x1800059e3  mov     ecx, eax
0x1800059e5  jz      short loc_180005A00
0x1800059e7  test    dl, 2
0x1800059ea  jnz     short loc_180005A00
0x1800059ec  and     ecx, 0FFFFF63Eh
0x1800059f2  mov     eax, ebx
0x1800059f4  and     eax, 9C1h
0x1800059f9  or      ecx, eax
0x1800059fb  or      ecx, 2
0x1800059fe  mov     [rdi], ecx
0x180005a00  mov     r8d, edx
0x180005a03  and     r8d, 4
0x180005a07  jnz     short loc_180005A1B
0x180005a09  btr     ecx, 0Ah
0x180005a0d  mov     eax, ebx
0x180005a0f  and     eax, 400h
0x180005a14  or      ecx, eax
0x180005a16  or      ecx, 4
0x180005a19  mov     [rdi], ecx
0x180005a1b  mov     eax, edx
0x180005a1d  lock cmpxchg [rsi], ecx
0x180005a21  jnz     short loc_1800059DA
0x180005a23  test    r8d, r8d
0x180005a26  jnz     short loc_180005A38
0x180005a28  mov     r8d, ebp
0x180005a2b  mov     edx, 3
0x180005a30  mov     rcx, rsi
0x180005a33  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180005a38  mov     eax, [rdi]
0x180005a3a  test    al, 2
0x180005a3c  jnz     short loc_180005A4D
0x180005a3e  and     eax, 0FFFFF63Eh
0x180005a43  and     ebx, 9C1h
0x180005a49  or      eax, ebx
0x180005a4b  mov     [rdi], eax
0x180005a4d  mov     rbx, [rsp+38h+arg_10]
0x180005a52  mov     rax, rdi
0x180005a55  add     rsp, 20h
0x180005a59  pop     rdi
0x180005a5a  pop     rsi
0x180005a5b  pop     rbp
0x180005a5c  retn
```
