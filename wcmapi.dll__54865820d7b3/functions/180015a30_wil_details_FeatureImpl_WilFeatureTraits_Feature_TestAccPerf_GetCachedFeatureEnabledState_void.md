# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x180015a30`
- end: `0x180015b1c`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `236`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016878`
- `0x180016d3c`

## callees

- `0x180008a90`
- `0x18000cdac`
- `0x180010298`
- `0x180015a30`
- `0x180016030`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 v5; // rcx
  signed __int32 v6; // eax
  __int16 v7; // bx
  bool v8; // zf
  signed __int32 v9; // edx
  unsigned int v10; // ecx
  __int64 v12; // [rsp+20h] [rbp-48h] BYREF
  int v13; // [rsp+28h] [rbp-40h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(v5, &v12, &v13);
    v6 = *(_DWORD *)a2;
    v7 = v12;
    do
    {
      v8 = v13 == 0;
      v9 = v6;
      *(_DWORD *)a2 = v6;
      v10 = v6;
      if ( !v8 && (v6 & 2) == 0 )
      {
        v10 = v7 & 0x9C1 | v6 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v10;
      }
      if ( (v6 & 4) == 0 )
      {
        v10 = v7 & 0x400 | v10 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v10;
      }
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestAccPerf__descriptor, v10, v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_TestAccPerf__descriptor,
        3,
        v4);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v7 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180015a30  push    rbx
0x180015a32  push    rbp
0x180015a33  push    rsi
0x180015a34  push    rdi
0x180015a35  sub     rsp, 48h
0x180015a39  mov     rax, cs:__security_cookie
0x180015a40  xor     rax, rsp
0x180015a43  mov     [rsp+68h+var_38], rax
0x180015a48  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x180015a4f  mov     rdi, rdx
0x180015a52  mov     qword ptr [rdx], 0
0x180015a59  mov     eax, [rsi]
0x180015a5b  mov     [rdx], eax
0x180015a5d  and     eax, 6
0x180015a60  cmp     al, 6
0x180015a62  jz      loc_180015B02
0x180015a68  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180015a6d  lea     r8, [rsp+68h+var_40]
0x180015a72  mov     [rsp+68h+var_40], 0
0x180015a7a  lea     rdx, [rsp+68h+var_48]
0x180015a7f  mov     ebp, eax
0x180015a81  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x180015a86  mov     eax, [rdi]
0x180015a88  mov     rbx, [rsp+68h+var_48]
0x180015a8d  cmp     [rsp+68h+var_40], 0
0x180015a92  mov     edx, eax
0x180015a94  mov     [rdi], eax
0x180015a96  mov     ecx, eax
0x180015a98  jz      short loc_180015AB3
0x180015a9a  test    dl, 2
0x180015a9d  jnz     short loc_180015AB3
0x180015a9f  and     ecx, 0FFFFF63Eh
0x180015aa5  mov     eax, ebx
0x180015aa7  and     eax, 9C1h
0x180015aac  or      ecx, eax
0x180015aae  or      ecx, 2
0x180015ab1  mov     [rdi], ecx
0x180015ab3  mov     r8d, edx
0x180015ab6  and     r8d, 4
0x180015aba  jnz     short loc_180015ACE
0x180015abc  btr     ecx, 0Ah
0x180015ac0  mov     eax, ebx
0x180015ac2  and     eax, 400h
0x180015ac7  or      ecx, eax
0x180015ac9  or      ecx, 4
0x180015acc  mov     [rdi], ecx
0x180015ace  mov     eax, edx
0x180015ad0  lock cmpxchg [rsi], ecx
0x180015ad4  jnz     short loc_180015A8D
0x180015ad6  test    r8d, r8d
0x180015ad9  jnz     short loc_180015AEB
0x180015adb  mov     r8d, ebp
0x180015ade  mov     edx, 3
0x180015ae3  mov     rcx, rsi
0x180015ae6  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180015aeb  mov     ecx, [rdi]
0x180015aed  test    cl, 2
0x180015af0  jnz     short loc_180015B02
0x180015af2  and     ecx, 0FFFFF63Eh
0x180015af8  and     ebx, 9C1h
0x180015afe  or      ecx, ebx
0x180015b00  mov     [rdi], ecx
0x180015b02  mov     rax, rdi
0x180015b05  mov     rcx, [rsp+68h+var_38]
0x180015b0a  xor     rcx, rsp; StackCookie
0x180015b0d  call    __security_check_cookie
0x180015b12  add     rsp, 48h
0x180015b16  pop     rdi
0x180015b17  pop     rsi
0x180015b18  pop     rbp
0x180015b19  pop     rbx
0x180015b1a  retn
```
