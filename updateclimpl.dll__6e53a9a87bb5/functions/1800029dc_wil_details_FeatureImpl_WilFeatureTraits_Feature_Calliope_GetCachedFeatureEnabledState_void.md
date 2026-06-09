# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope>::GetCachedFeatureEnabledState(void)

- ea: `0x1800029dc`
- end: `0x180002ac6`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `234`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002acc`
- `0x180002b68`

## callees

- `0x1800028c0`
- `0x1800029dc`
- `0x180003820`
- `0x180003aa8`
- `0x180010310`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v5; // ebp
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
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope>::GetCurrentFeatureEnabledState(v6, &v13, &v14);
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(a1, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x1800029dc  mov     [rsp+arg_10], rbx
0x1800029e1  push    rbp
0x1800029e2  push    rsi
0x1800029e3  push    rdi
0x1800029e4  sub     rsp, 40h
0x1800029e8  mov     rax, cs:__security_cookie
0x1800029ef  xor     rax, rsp
0x1800029f2  mov     [rsp+58h+var_28], rax
0x1800029f7  mov     qword ptr [rdx], 0
0x1800029fe  mov     rdi, rdx
0x180002a01  mov     eax, [rcx]
0x180002a03  mov     rsi, rcx
0x180002a06  mov     [rdx], eax
0x180002a08  and     eax, 6
0x180002a0b  cmp     al, 6
0x180002a0d  jz      loc_180002AA9
0x180002a13  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180002a18  lea     r8, [rsp+58h+var_30]
0x180002a1d  mov     [rsp+58h+var_30], 0
0x180002a25  lea     rdx, [rsp+58h+var_38]
0x180002a2a  mov     ebp, eax
0x180002a2c  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope>::GetCurrentFeatureEnabledState(int *)
0x180002a31  mov     eax, [rdi]
0x180002a33  mov     rbx, [rsp+58h+var_38]
0x180002a38  cmp     [rsp+58h+var_30], 0
0x180002a3d  mov     edx, eax
0x180002a3f  mov     [rdi], eax
0x180002a41  mov     ecx, eax
0x180002a43  jz      short loc_180002A5E
0x180002a45  test    dl, 2
0x180002a48  jnz     short loc_180002A5E
0x180002a4a  and     ecx, 0FFFFF63Eh
0x180002a50  mov     eax, ebx
0x180002a52  and     eax, 9C1h
0x180002a57  or      ecx, eax
0x180002a59  or      ecx, 2
0x180002a5c  mov     [rdi], ecx
0x180002a5e  test    dl, 4
0x180002a61  jnz     short loc_180002A75
0x180002a63  btr     ecx, 0Ah
0x180002a67  mov     eax, ebx
0x180002a69  and     eax, 400h
0x180002a6e  or      ecx, eax
0x180002a70  or      ecx, 4
0x180002a73  mov     [rdi], ecx
0x180002a75  mov     eax, edx
0x180002a77  lock cmpxchg [rsi], ecx
0x180002a7b  jnz     short loc_180002A38
0x180002a7d  test    dl, 4
0x180002a80  jnz     short loc_180002A92
0x180002a82  mov     r8d, ebp
0x180002a85  mov     edx, 3
0x180002a8a  mov     rcx, rsi
0x180002a8d  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180002a92  mov     ecx, [rdi]
0x180002a94  test    cl, 2
0x180002a97  jnz     short loc_180002AA9
0x180002a99  and     ecx, 0FFFFF63Eh
0x180002a9f  and     ebx, 9C1h
0x180002aa5  or      ecx, ebx
0x180002aa7  mov     [rdi], ecx
0x180002aa9  mov     rax, rdi
0x180002aac  mov     rcx, [rsp+58h+var_28]
0x180002ab1  xor     rcx, rsp; StackCookie
0x180002ab4  call    __security_check_cookie
0x180002ab9  mov     rbx, [rsp+58h+arg_10]
0x180002abe  add     rsp, 40h
0x180002ac2  pop     rdi
0x180002ac3  pop     rsi
0x180002ac4  pop     rbp
0x180002ac5  retn
```
