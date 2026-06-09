# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381>::GetCachedFeatureEnabledState(void)

- ea: `0x140009c30`
- end: `0x140009d1a`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `234`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140009b74`
- `0x140009d20`

## callees

- `0x140005090`
- `0x140005154`
- `0x140009c30`
- `0x140009df4`
- `0x14001aa60`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381>::GetCachedFeatureEnabledState(
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
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381>::GetCurrentFeatureEnabledState(
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges((volatile signed __int32 *)a1, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x140009c30  mov     [rsp+arg_10], rbx
0x140009c35  push    rbp
0x140009c36  push    rsi
0x140009c37  push    rdi
0x140009c38  sub     rsp, 40h
0x140009c3c  mov     rax, cs:__security_cookie
0x140009c43  xor     rax, rsp
0x140009c46  mov     [rsp+58h+var_28], rax
0x140009c4b  mov     qword ptr [rdx], 0
0x140009c52  mov     rdi, rdx
0x140009c55  mov     eax, [rcx]
0x140009c57  mov     rsi, rcx
0x140009c5a  mov     [rdx], eax
0x140009c5c  and     eax, 6
0x140009c5f  cmp     al, 6
0x140009c61  jz      loc_140009CFD
0x140009c67  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140009c6c  lea     r8, [rsp+58h+var_30]
0x140009c71  mov     [rsp+58h+var_30], 0
0x140009c79  lea     rdx, [rsp+58h+var_38]
0x140009c7e  mov     ebp, eax
0x140009c80  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381>::GetCurrentFeatureEnabledState(int *)
0x140009c85  mov     eax, [rdi]
0x140009c87  mov     rbx, [rsp+58h+var_38]
0x140009c8c  cmp     [rsp+58h+var_30], 0
0x140009c91  mov     edx, eax
0x140009c93  mov     [rdi], eax
0x140009c95  mov     ecx, eax
0x140009c97  jz      short loc_140009CB2
0x140009c99  test    dl, 2
0x140009c9c  jnz     short loc_140009CB2
0x140009c9e  and     ecx, 0FFFFF63Eh
0x140009ca4  mov     eax, ebx
0x140009ca6  and     eax, 9C1h
0x140009cab  or      ecx, eax
0x140009cad  or      ecx, 2
0x140009cb0  mov     [rdi], ecx
0x140009cb2  test    dl, 4
0x140009cb5  jnz     short loc_140009CC9
0x140009cb7  btr     ecx, 0Ah
0x140009cbb  mov     eax, ebx
0x140009cbd  and     eax, 400h
0x140009cc2  or      ecx, eax
0x140009cc4  or      ecx, 4
0x140009cc7  mov     [rdi], ecx
0x140009cc9  mov     eax, edx
0x140009ccb  lock cmpxchg [rsi], ecx
0x140009ccf  jnz     short loc_140009C8C
0x140009cd1  test    dl, 4
0x140009cd4  jnz     short loc_140009CE6
0x140009cd6  mov     r8d, ebp
0x140009cd9  mov     edx, 3
0x140009cde  mov     rcx, rsi
0x140009ce1  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140009ce6  mov     ecx, [rdi]
0x140009ce8  test    cl, 2
0x140009ceb  jnz     short loc_140009CFD
0x140009ced  and     ecx, 0FFFFF63Eh
0x140009cf3  and     ebx, 9C1h
0x140009cf9  or      ecx, ebx
0x140009cfb  mov     [rdi], ecx
0x140009cfd  mov     rax, rdi
0x140009d00  mov     rcx, [rsp+58h+var_28]
0x140009d05  xor     rcx, rsp; StackCookie
0x140009d08  call    __security_check_cookie
0x140009d0d  mov     rbx, [rsp+58h+arg_10]
0x140009d12  add     rsp, 40h
0x140009d16  pop     rdi
0x140009d17  pop     rsi
0x140009d18  pop     rbp
0x140009d19  retn
```
