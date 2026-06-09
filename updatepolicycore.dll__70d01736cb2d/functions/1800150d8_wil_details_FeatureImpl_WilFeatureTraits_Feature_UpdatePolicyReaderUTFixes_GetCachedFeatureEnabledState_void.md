# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UpdatePolicyReaderUTFixes>::GetCachedFeatureEnabledState(void)

- ea: `0x1800150d8`
- end: `0x1800151c2`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UpdatePolicyReaderUTFixes@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `234`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180014ea8`
- `0x1800151c8`

## callees

- `0x180010910`
- `0x1800109d4`
- `0x1800150d8`
- `0x1800155b0`
- `0x18002ffd0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UpdatePolicyReaderUTFixes>::GetCachedFeatureEnabledState(
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
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UpdatePolicyReaderUTFixes>::GetCurrentFeatureEnabledState(
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(a1, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x1800150d8  mov     [rsp+arg_10], rbx
0x1800150dd  push    rbp
0x1800150de  push    rsi
0x1800150df  push    rdi
0x1800150e0  sub     rsp, 40h
0x1800150e4  mov     rax, cs:__security_cookie
0x1800150eb  xor     rax, rsp
0x1800150ee  mov     [rsp+58h+var_28], rax
0x1800150f3  mov     qword ptr [rdx], 0
0x1800150fa  mov     rdi, rdx
0x1800150fd  mov     eax, [rcx]
0x1800150ff  mov     rsi, rcx
0x180015102  mov     [rdx], eax
0x180015104  and     eax, 6
0x180015107  cmp     al, 6
0x180015109  jz      loc_1800151A5
0x18001510f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180015114  lea     r8, [rsp+58h+var_30]
0x180015119  mov     [rsp+58h+var_30], 0
0x180015121  lea     rdx, [rsp+58h+var_38]
0x180015126  mov     ebp, eax
0x180015128  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UpdatePolicyReaderUTFixes@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UpdatePolicyReaderUTFixes>::GetCurrentFeatureEnabledState(int *)
0x18001512d  mov     eax, [rdi]
0x18001512f  mov     rbx, [rsp+58h+var_38]
0x180015134  cmp     [rsp+58h+var_30], 0
0x180015139  mov     edx, eax
0x18001513b  mov     [rdi], eax
0x18001513d  mov     ecx, eax
0x18001513f  jz      short loc_18001515A
0x180015141  test    dl, 2
0x180015144  jnz     short loc_18001515A
0x180015146  and     ecx, 0FFFFF63Eh
0x18001514c  mov     eax, ebx
0x18001514e  and     eax, 9C1h
0x180015153  or      ecx, eax
0x180015155  or      ecx, 2
0x180015158  mov     [rdi], ecx
0x18001515a  test    dl, 4
0x18001515d  jnz     short loc_180015171
0x18001515f  btr     ecx, 0Ah
0x180015163  mov     eax, ebx
0x180015165  and     eax, 400h
0x18001516a  or      ecx, eax
0x18001516c  or      ecx, 4
0x18001516f  mov     [rdi], ecx
0x180015171  mov     eax, edx
0x180015173  lock cmpxchg [rsi], ecx
0x180015177  jnz     short loc_180015134
0x180015179  test    dl, 4
0x18001517c  jnz     short loc_18001518E
0x18001517e  mov     r8d, ebp
0x180015181  mov     edx, 3
0x180015186  mov     rcx, rsi
0x180015189  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001518e  mov     ecx, [rdi]
0x180015190  test    cl, 2
0x180015193  jnz     short loc_1800151A5
0x180015195  and     ecx, 0FFFFF63Eh
0x18001519b  and     ebx, 9C1h
0x1800151a1  or      ecx, ebx
0x1800151a3  mov     [rdi], ecx
0x1800151a5  mov     rax, rdi
0x1800151a8  mov     rcx, [rsp+58h+var_28]
0x1800151ad  xor     rcx, rsp; StackCookie
0x1800151b0  call    __security_check_cookie
0x1800151b5  mov     rbx, [rsp+58h+arg_10]
0x1800151ba  add     rsp, 40h
0x1800151be  pop     rdi
0x1800151bf  pop     rsi
0x1800151c0  pop     rbp
0x1800151c1  retn
```
