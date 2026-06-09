# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CA_Fix_NetStackSafety>::GetCachedFeatureEnabledState(void)

- ea: `0x180015660`
- end: `0x18001574c`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CA_Fix_NetStackSafety@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `236`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800165fc`
- `0x180016d00`

## callees

- `0x180008a90`
- `0x18000cdac`
- `0x180010298`
- `0x180015660`
- `0x180015e00`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CA_Fix_NetStackSafety>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_CA_Fix_NetStackSafety__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_CA_Fix_NetStackSafety__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CA_Fix_NetStackSafety>::GetCurrentFeatureEnabledState(
      v5,
      &v12,
      &v13);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_CA_Fix_NetStackSafety__descriptor, v10, v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_CA_Fix_NetStackSafety__descriptor,
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
0x180015660  push    rbx
0x180015662  push    rbp
0x180015663  push    rsi
0x180015664  push    rdi
0x180015665  sub     rsp, 48h
0x180015669  mov     rax, cs:__security_cookie
0x180015670  xor     rax, rsp
0x180015673  mov     [rsp+68h+var_38], rax
0x180015678  mov     rsi, cs:Feature_CA_Fix_NetStackSafety__descriptor
0x18001567f  mov     rdi, rdx
0x180015682  mov     qword ptr [rdx], 0
0x180015689  mov     eax, [rsi]
0x18001568b  mov     [rdx], eax
0x18001568d  and     eax, 6
0x180015690  cmp     al, 6
0x180015692  jz      loc_180015732
0x180015698  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001569d  lea     r8, [rsp+68h+var_40]
0x1800156a2  mov     [rsp+68h+var_40], 0
0x1800156aa  lea     rdx, [rsp+68h+var_48]
0x1800156af  mov     ebp, eax
0x1800156b1  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CA_Fix_NetStackSafety@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CA_Fix_NetStackSafety>::GetCurrentFeatureEnabledState(int *)
0x1800156b6  mov     eax, [rdi]
0x1800156b8  mov     rbx, [rsp+68h+var_48]
0x1800156bd  cmp     [rsp+68h+var_40], 0
0x1800156c2  mov     edx, eax
0x1800156c4  mov     [rdi], eax
0x1800156c6  mov     ecx, eax
0x1800156c8  jz      short loc_1800156E3
0x1800156ca  test    dl, 2
0x1800156cd  jnz     short loc_1800156E3
0x1800156cf  and     ecx, 0FFFFF63Eh
0x1800156d5  mov     eax, ebx
0x1800156d7  and     eax, 9C1h
0x1800156dc  or      ecx, eax
0x1800156de  or      ecx, 2
0x1800156e1  mov     [rdi], ecx
0x1800156e3  mov     r8d, edx
0x1800156e6  and     r8d, 4
0x1800156ea  jnz     short loc_1800156FE
0x1800156ec  btr     ecx, 0Ah
0x1800156f0  mov     eax, ebx
0x1800156f2  and     eax, 400h
0x1800156f7  or      ecx, eax
0x1800156f9  or      ecx, 4
0x1800156fc  mov     [rdi], ecx
0x1800156fe  mov     eax, edx
0x180015700  lock cmpxchg [rsi], ecx
0x180015704  jnz     short loc_1800156BD
0x180015706  test    r8d, r8d
0x180015709  jnz     short loc_18001571B
0x18001570b  mov     r8d, ebp
0x18001570e  mov     edx, 3
0x180015713  mov     rcx, rsi
0x180015716  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001571b  mov     ecx, [rdi]
0x18001571d  test    cl, 2
0x180015720  jnz     short loc_180015732
0x180015722  and     ecx, 0FFFFF63Eh
0x180015728  and     ebx, 9C1h
0x18001572e  or      ecx, ebx
0x180015730  mov     [rdi], ecx
0x180015732  mov     rax, rdi
0x180015735  mov     rcx, [rsp+68h+var_38]
0x18001573a  xor     rcx, rsp; StackCookie
0x18001573d  call    __security_check_cookie
0x180015742  add     rsp, 48h
0x180015746  pop     rdi
0x180015747  pop     rsi
0x180015748  pop     rbp
0x180015749  pop     rbx
0x18001574a  retn
```
