# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCachedFeatureEnabledState(void)

- ea: `0x18001357c`
- end: `0x180013655`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017690`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x18001357c`
- `0x180013e54`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestUex12__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestUex12__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestUex12__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_TestUex12__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18001357c  mov     [rsp+arg_10], rbx
0x180013581  mov     [rsp+arg_0], rcx
0x180013586  push    rbp
0x180013587  push    rsi
0x180013588  push    rdi
0x180013589  sub     rsp, 20h
0x18001358d  mov     rsi, cs:Feature_TestUex12__descriptor
0x180013594  mov     rdi, rdx
0x180013597  mov     qword ptr [rdx], 0
0x18001359e  mov     eax, [rsi]
0x1800135a0  mov     [rdx], eax
0x1800135a2  and     eax, 6
0x1800135a5  cmp     al, 6
0x1800135a7  jz      loc_180013645
0x1800135ad  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800135b2  lea     r8, [rsp+38h+arg_0]
0x1800135b7  mov     dword ptr [rsp+38h+arg_0], 0
0x1800135bf  lea     rdx, [rsp+38h+arg_8]
0x1800135c4  mov     ebp, eax
0x1800135c6  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCurrentFeatureEnabledState(int *)
0x1800135cb  mov     eax, [rdi]
0x1800135cd  mov     rbx, [rsp+38h+arg_8]
0x1800135d2  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800135d7  mov     edx, eax
0x1800135d9  mov     [rdi], eax
0x1800135db  mov     ecx, eax
0x1800135dd  jz      short loc_1800135F8
0x1800135df  test    dl, 2
0x1800135e2  jnz     short loc_1800135F8
0x1800135e4  and     ecx, 0FFFFF63Eh
0x1800135ea  mov     eax, ebx
0x1800135ec  and     eax, 9C1h
0x1800135f1  or      ecx, eax
0x1800135f3  or      ecx, 2
0x1800135f6  mov     [rdi], ecx
0x1800135f8  mov     r8d, edx
0x1800135fb  and     r8d, 4
0x1800135ff  jnz     short loc_180013613
0x180013601  btr     ecx, 0Ah
0x180013605  mov     eax, ebx
0x180013607  and     eax, 400h
0x18001360c  or      ecx, eax
0x18001360e  or      ecx, 4
0x180013611  mov     [rdi], ecx
0x180013613  mov     eax, edx
0x180013615  lock cmpxchg [rsi], ecx
0x180013619  jnz     short loc_1800135D2
0x18001361b  test    r8d, r8d
0x18001361e  jnz     short loc_180013630
0x180013620  mov     r8d, ebp
0x180013623  mov     edx, 3
0x180013628  mov     rcx, rsi
0x18001362b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180013630  mov     eax, [rdi]
0x180013632  test    al, 2
0x180013634  jnz     short loc_180013645
0x180013636  and     eax, 0FFFFF63Eh
0x18001363b  and     ebx, 9C1h
0x180013641  or      eax, ebx
0x180013643  mov     [rdi], eax
0x180013645  mov     rbx, [rsp+38h+arg_10]
0x18001364a  mov     rax, rdi
0x18001364d  add     rsp, 20h
0x180013651  pop     rdi
0x180013652  pop     rsi
0x180013653  pop     rbp
0x180013654  retn
```
