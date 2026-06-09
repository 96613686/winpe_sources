# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e070`
- end: `0x18000e149`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fcd0`
- `0x180011848`

## callees

- `0x18000d020`
- `0x18000e070`
- `0x18000e83c`
- `0x1800105e0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(
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
      v8 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Ten2Loc__descriptor, v12, v8);
    }
    while ( v11 != v8 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Ten2Loc__descriptor,
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
0x18000e070  mov     [rsp+arg_10], rbx
0x18000e075  mov     [rsp+arg_0], rcx
0x18000e07a  push    rbp
0x18000e07b  push    rsi
0x18000e07c  push    rdi
0x18000e07d  sub     rsp, 20h
0x18000e081  mov     rsi, cs:Feature_Ten2Loc__descriptor
0x18000e088  mov     rdi, rdx
0x18000e08b  mov     qword ptr [rdx], 0
0x18000e092  mov     eax, [rsi]
0x18000e094  mov     [rdx], eax
0x18000e096  and     eax, 6
0x18000e099  cmp     al, 6
0x18000e09b  jz      loc_18000E139
0x18000e0a1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e0a6  lea     r8, [rsp+38h+arg_0]
0x18000e0ab  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e0b3  lea     rdx, [rsp+38h+arg_8]
0x18000e0b8  mov     ebp, eax
0x18000e0ba  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)
0x18000e0bf  mov     eax, [rdi]
0x18000e0c1  mov     rbx, [rsp+38h+arg_8]
0x18000e0c6  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e0cb  mov     edx, eax
0x18000e0cd  mov     [rdi], eax
0x18000e0cf  mov     ecx, eax
0x18000e0d1  jz      short loc_18000E0EC
0x18000e0d3  test    dl, 2
0x18000e0d6  jnz     short loc_18000E0EC
0x18000e0d8  and     ecx, 0FFFFF63Eh
0x18000e0de  mov     eax, ebx
0x18000e0e0  and     eax, 9C1h
0x18000e0e5  or      ecx, eax
0x18000e0e7  or      ecx, 2
0x18000e0ea  mov     [rdi], ecx
0x18000e0ec  mov     r8d, edx
0x18000e0ef  and     r8d, 4
0x18000e0f3  jnz     short loc_18000E107
0x18000e0f5  btr     ecx, 0Ah
0x18000e0f9  mov     eax, ebx
0x18000e0fb  and     eax, 400h
0x18000e100  or      ecx, eax
0x18000e102  or      ecx, 4
0x18000e105  mov     [rdi], ecx
0x18000e107  mov     eax, edx
0x18000e109  lock cmpxchg [rsi], ecx
0x18000e10d  jnz     short loc_18000E0C6
0x18000e10f  test    r8d, r8d
0x18000e112  jnz     short loc_18000E124
0x18000e114  mov     r8d, ebp
0x18000e117  mov     edx, 3
0x18000e11c  mov     rcx, rsi
0x18000e11f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e124  mov     eax, [rdi]
0x18000e126  test    al, 2
0x18000e128  jnz     short loc_18000E139
0x18000e12a  and     eax, 0FFFFF63Eh
0x18000e12f  and     ebx, 9C1h
0x18000e135  or      eax, ebx
0x18000e137  mov     [rdi], eax
0x18000e139  mov     rbx, [rsp+38h+arg_10]
0x18000e13e  mov     rax, rdi
0x18000e141  add     rsp, 20h
0x18000e145  pop     rdi
0x18000e146  pop     rsi
0x18000e147  pop     rbp
0x18000e148  retn
```
