# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCachedFeatureEnabledState(void)

- ea: `0x1800179d8`
- end: `0x180017ab1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019154`

## callees

- `0x180016be8`
- `0x1800179d8`
- `0x180018248`
- `0x180018da4`

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
0x1800179d8  mov     [rsp+arg_10], rbx
0x1800179dd  mov     [rsp+arg_0], rcx
0x1800179e2  push    rbp
0x1800179e3  push    rsi
0x1800179e4  push    rdi
0x1800179e5  sub     rsp, 20h
0x1800179e9  mov     rsi, cs:Feature_TestUex12__descriptor
0x1800179f0  mov     rdi, rdx
0x1800179f3  mov     qword ptr [rdx], 0
0x1800179fa  mov     eax, [rsi]
0x1800179fc  mov     [rdx], eax
0x1800179fe  and     eax, 6
0x180017a01  cmp     al, 6
0x180017a03  jz      loc_180017AA1
0x180017a09  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180017a0e  lea     r8, [rsp+38h+arg_0]
0x180017a13  mov     dword ptr [rsp+38h+arg_0], 0
0x180017a1b  lea     rdx, [rsp+38h+arg_8]
0x180017a20  mov     ebp, eax
0x180017a22  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCurrentFeatureEnabledState(int *)
0x180017a27  mov     eax, [rdi]
0x180017a29  mov     rbx, [rsp+38h+arg_8]
0x180017a2e  cmp     dword ptr [rsp+38h+arg_0], 0
0x180017a33  mov     edx, eax
0x180017a35  mov     [rdi], eax
0x180017a37  mov     ecx, eax
0x180017a39  jz      short loc_180017A54
0x180017a3b  test    dl, 2
0x180017a3e  jnz     short loc_180017A54
0x180017a40  and     ecx, 0FFFFF63Eh
0x180017a46  mov     eax, ebx
0x180017a48  and     eax, 9C1h
0x180017a4d  or      ecx, eax
0x180017a4f  or      ecx, 2
0x180017a52  mov     [rdi], ecx
0x180017a54  mov     r8d, edx
0x180017a57  and     r8d, 4
0x180017a5b  jnz     short loc_180017A6F
0x180017a5d  btr     ecx, 0Ah
0x180017a61  mov     eax, ebx
0x180017a63  and     eax, 400h
0x180017a68  or      ecx, eax
0x180017a6a  or      ecx, 4
0x180017a6d  mov     [rdi], ecx
0x180017a6f  mov     eax, edx
0x180017a71  lock cmpxchg [rsi], ecx
0x180017a75  jnz     short loc_180017A2E
0x180017a77  test    r8d, r8d
0x180017a7a  jnz     short loc_180017A8C
0x180017a7c  mov     r8d, ebp
0x180017a7f  mov     edx, 3
0x180017a84  mov     rcx, rsi
0x180017a87  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180017a8c  mov     eax, [rdi]
0x180017a8e  test    al, 2
0x180017a90  jnz     short loc_180017AA1
0x180017a92  and     eax, 0FFFFF63Eh
0x180017a97  and     ebx, 9C1h
0x180017a9d  or      eax, ebx
0x180017a9f  mov     [rdi], eax
0x180017aa1  mov     rbx, [rsp+38h+arg_10]
0x180017aa6  mov     rax, rdi
0x180017aa9  add     rsp, 20h
0x180017aad  pop     rdi
0x180017aae  pop     rsi
0x180017aaf  pop     rbp
0x180017ab0  retn
```
