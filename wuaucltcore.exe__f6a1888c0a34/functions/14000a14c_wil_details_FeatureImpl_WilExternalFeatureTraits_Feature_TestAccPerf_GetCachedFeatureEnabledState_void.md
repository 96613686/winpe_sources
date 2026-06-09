# wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x14000a14c`
- end: `0x14000a236`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilExternalFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `234`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000a23c`
- `0x14000a2d8`

## callees

- `0x140005090`
- `0x140005154`
- `0x14000a02c`
- `0x14000a14c`
- `0x14001aa60`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v5; // ebp
  __int64 v6; // rcx
  signed __int32 v7; // eax
  __int16 v8; // bx
  bool v9; // zf
  signed __int32 v10; // edx
  unsigned int v11; // ecx
  __int64 v13; // [rsp+20h] [rbp-38h] BYREF
  int v14; // [rsp+28h] [rbp-30h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)a1;
  *(_DWORD *)a2 = *(_DWORD *)a1;
  if ( (v3 & 6) != 6 )
  {
    v14 = 0;
    v5 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(
      v6,
      &v13,
      &v14);
    v7 = *(_DWORD *)a2;
    v8 = v13;
    do
    {
      v9 = v14 == 0;
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)a1, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges((volatile signed __int32 *)a1, 64, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x14000a14c  mov     [rsp+arg_10], rbx
0x14000a151  push    rbp
0x14000a152  push    rsi
0x14000a153  push    rdi
0x14000a154  sub     rsp, 40h
0x14000a158  mov     rax, cs:__security_cookie
0x14000a15f  xor     rax, rsp
0x14000a162  mov     [rsp+58h+var_28], rax
0x14000a167  mov     qword ptr [rdx], 0
0x14000a16e  mov     rdi, rdx
0x14000a171  mov     eax, [rcx]
0x14000a173  mov     rsi, rcx
0x14000a176  mov     [rdx], eax
0x14000a178  and     eax, 6
0x14000a17b  cmp     al, 6
0x14000a17d  jz      loc_14000A219
0x14000a183  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000a188  lea     r8, [rsp+58h+var_30]
0x14000a18d  mov     [rsp+58h+var_30], 0
0x14000a195  lea     rdx, [rsp+58h+var_38]
0x14000a19a  mov     ebp, eax
0x14000a19c  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilExternalFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x14000a1a1  mov     eax, [rdi]
0x14000a1a3  mov     rbx, [rsp+58h+var_38]
0x14000a1a8  cmp     [rsp+58h+var_30], 0
0x14000a1ad  mov     edx, eax
0x14000a1af  mov     [rdi], eax
0x14000a1b1  mov     ecx, eax
0x14000a1b3  jz      short loc_14000A1CE
0x14000a1b5  test    dl, 2
0x14000a1b8  jnz     short loc_14000A1CE
0x14000a1ba  and     ecx, 0FFFFF63Eh
0x14000a1c0  mov     eax, ebx
0x14000a1c2  and     eax, 9C1h
0x14000a1c7  or      ecx, eax
0x14000a1c9  or      ecx, 2
0x14000a1cc  mov     [rdi], ecx
0x14000a1ce  test    dl, 4
0x14000a1d1  jnz     short loc_14000A1E5
0x14000a1d3  btr     ecx, 0Ah
0x14000a1d7  mov     eax, ebx
0x14000a1d9  and     eax, 400h
0x14000a1de  or      ecx, eax
0x14000a1e0  or      ecx, 4
0x14000a1e3  mov     [rdi], ecx
0x14000a1e5  mov     eax, edx
0x14000a1e7  lock cmpxchg [rsi], ecx
0x14000a1eb  jnz     short loc_14000A1A8
0x14000a1ed  test    dl, 4
0x14000a1f0  jnz     short loc_14000A202
0x14000a1f2  mov     r8d, ebp
0x14000a1f5  mov     edx, 40h ; '@'
0x14000a1fa  mov     rcx, rsi
0x14000a1fd  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000a202  mov     ecx, [rdi]
0x14000a204  test    cl, 2
0x14000a207  jnz     short loc_14000A219
0x14000a209  and     ecx, 0FFFFF63Eh
0x14000a20f  and     ebx, 9C1h
0x14000a215  or      ecx, ebx
0x14000a217  mov     [rdi], ecx
0x14000a219  mov     rax, rdi
0x14000a21c  mov     rcx, [rsp+58h+var_28]
0x14000a221  xor     rcx, rsp; StackCookie
0x14000a224  call    __security_check_cookie
0x14000a229  mov     rbx, [rsp+58h+arg_10]
0x14000a22e  add     rsp, 40h
0x14000a232  pop     rdi
0x14000a233  pop     rsi
0x14000a234  pop     rbp
0x14000a235  retn
```
