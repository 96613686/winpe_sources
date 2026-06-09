# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetCachedFeatureEnabledState(void)

- ea: `0x18000da28`
- end: `0x18000db01`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800106fc`
- `0x1800122b4`

## callees

- `0x18000d5d0`
- `0x18000da28`
- `0x18000ddfc`
- `0x180011590`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  int v5; // ebp
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
  v3 = *(_DWORD *)Feature_Servicing_SmartCardKspPqcSupport__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_SmartCardKspPqcSupport__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_Servicing_SmartCardKspPqcSupport__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Servicing_SmartCardKspPqcSupport__descriptor,
        1,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18000da28  mov     [rsp+arg_10], rbx
0x18000da2d  mov     [rsp+arg_0], rcx
0x18000da32  push    rbp
0x18000da33  push    rsi
0x18000da34  push    rdi
0x18000da35  sub     rsp, 20h
0x18000da39  mov     rsi, cs:Feature_Servicing_SmartCardKspPqcSupport__descriptor
0x18000da40  mov     rdi, rdx
0x18000da43  mov     qword ptr [rdx], 0
0x18000da4a  mov     eax, [rsi]
0x18000da4c  mov     [rdx], eax
0x18000da4e  and     eax, 6
0x18000da51  cmp     al, 6
0x18000da53  jz      loc_18000DAF1
0x18000da59  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000da5e  lea     r8, [rsp+38h+arg_0]
0x18000da63  mov     dword ptr [rsp+38h+arg_0], 0
0x18000da6b  lea     rdx, [rsp+38h+arg_8]
0x18000da70  mov     ebp, eax
0x18000da72  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetCurrentFeatureEnabledState(int *)
0x18000da77  mov     eax, [rdi]
0x18000da79  mov     rbx, [rsp+38h+arg_8]
0x18000da7e  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000da83  mov     edx, eax
0x18000da85  mov     [rdi], eax
0x18000da87  mov     ecx, eax
0x18000da89  jz      short loc_18000DAA4
0x18000da8b  test    dl, 2
0x18000da8e  jnz     short loc_18000DAA4
0x18000da90  and     ecx, 0FFFFF63Eh
0x18000da96  mov     eax, ebx
0x18000da98  and     eax, 9C1h
0x18000da9d  or      ecx, eax
0x18000da9f  or      ecx, 2
0x18000daa2  mov     [rdi], ecx
0x18000daa4  mov     r8d, edx
0x18000daa7  and     r8d, 4
0x18000daab  jnz     short loc_18000DABF
0x18000daad  btr     ecx, 0Ah
0x18000dab1  mov     eax, ebx
0x18000dab3  and     eax, 400h
0x18000dab8  or      ecx, eax
0x18000daba  or      ecx, 4
0x18000dabd  mov     [rdi], ecx
0x18000dabf  mov     eax, edx
0x18000dac1  lock cmpxchg [rsi], ecx
0x18000dac5  jnz     short loc_18000DA7E
0x18000dac7  test    r8d, r8d
0x18000daca  jnz     short loc_18000DADC
0x18000dacc  mov     r8d, ebp
0x18000dacf  mov     edx, 1
0x18000dad4  mov     rcx, rsi
0x18000dad7  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000dadc  mov     eax, [rdi]
0x18000dade  test    al, 2
0x18000dae0  jnz     short loc_18000DAF1
0x18000dae2  and     eax, 0FFFFF63Eh
0x18000dae7  and     ebx, 9C1h
0x18000daed  or      eax, ebx
0x18000daef  mov     [rdi], eax
0x18000daf1  mov     rbx, [rsp+38h+arg_10]
0x18000daf6  mov     rax, rdi
0x18000daf9  add     rsp, 20h
0x18000dafd  pop     rdi
0x18000dafe  pop     rsi
0x18000daff  pop     rbp
0x18000db00  retn
```
