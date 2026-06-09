# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x18001b830`
- end: `0x18001b91b`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800206cc`
- `0x180027098`

## callees

- `0x1800015f0`
- `0x18001aba4`
- `0x18001b830`
- `0x18001c090`
- `0x180026a48`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValAccTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValAccTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(v5, &v12, &v13);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValAccTest__descriptor, v10, v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_ValAccTest__descriptor,
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
0x18001b830  push    rbx
0x18001b832  push    rbp
0x18001b833  push    rsi
0x18001b834  push    rdi
0x18001b835  sub     rsp, 48h
0x18001b839  mov     rax, cs:__security_cookie
0x18001b840  xor     rax, rsp
0x18001b843  mov     [rsp+68h+var_38], rax
0x18001b848  mov     rsi, cs:Feature_ValAccTest__descriptor
0x18001b84f  mov     rdi, rdx
0x18001b852  mov     qword ptr [rdx], 0
0x18001b859  mov     eax, [rsi]
0x18001b85b  mov     [rdx], eax
0x18001b85d  and     eax, 6
0x18001b860  cmp     al, 6
0x18001b862  jz      loc_18001B902
0x18001b868  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001b86d  lea     r8, [rsp+68h+var_40]
0x18001b872  mov     [rsp+68h+var_40], 0
0x18001b87a  lea     rdx, [rsp+68h+var_48]
0x18001b87f  mov     ebp, eax
0x18001b881  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x18001b886  mov     eax, [rdi]
0x18001b888  mov     rbx, [rsp+68h+var_48]
0x18001b88d  cmp     [rsp+68h+var_40], 0
0x18001b892  mov     edx, eax
0x18001b894  mov     [rdi], eax
0x18001b896  mov     ecx, eax
0x18001b898  jz      short loc_18001B8B3
0x18001b89a  test    dl, 2
0x18001b89d  jnz     short loc_18001B8B3
0x18001b89f  and     ecx, 0FFFFF63Eh
0x18001b8a5  mov     eax, ebx
0x18001b8a7  and     eax, 9C1h
0x18001b8ac  or      ecx, eax
0x18001b8ae  or      ecx, 2
0x18001b8b1  mov     [rdi], ecx
0x18001b8b3  mov     r8d, edx
0x18001b8b6  and     r8d, 4
0x18001b8ba  jnz     short loc_18001B8CE
0x18001b8bc  btr     ecx, 0Ah
0x18001b8c0  mov     eax, ebx
0x18001b8c2  and     eax, 400h
0x18001b8c7  or      ecx, eax
0x18001b8c9  or      ecx, 4
0x18001b8cc  mov     [rdi], ecx
0x18001b8ce  mov     eax, edx
0x18001b8d0  lock cmpxchg [rsi], ecx
0x18001b8d4  jnz     short loc_18001B88D
0x18001b8d6  test    r8d, r8d
0x18001b8d9  jnz     short loc_18001B8EB
0x18001b8db  mov     r8d, ebp
0x18001b8de  mov     edx, 3
0x18001b8e3  mov     rcx, rsi
0x18001b8e6  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001b8eb  mov     ecx, [rdi]
0x18001b8ed  test    cl, 2
0x18001b8f0  jnz     short loc_18001B902
0x18001b8f2  and     ecx, 0FFFFF63Eh
0x18001b8f8  and     ebx, 9C1h
0x18001b8fe  or      ecx, ebx
0x18001b900  mov     [rdi], ecx
0x18001b902  mov     rax, rdi
0x18001b905  mov     rcx, [rsp+68h+var_38]
0x18001b90a  xor     rcx, rsp; StackCookie
0x18001b90d  call    __security_check_cookie
0x18001b912  add     rsp, 48h
0x18001b916  pop     rdi
0x18001b917  pop     rsi
0x18001b918  pop     rbp
0x18001b919  pop     rbx
0x18001b91a  retn
```
