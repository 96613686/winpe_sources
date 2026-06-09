# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(void)

- ea: `0x1800132dc`
- end: `0x1800133b5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800174bc`

## callees

- `0x18000ca74`
- `0x18000e564`
- `0x1800132dc`
- `0x180013a04`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Ten2Loc__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Ten2Loc__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x1800132dc  mov     [rsp+arg_10], rbx
0x1800132e1  mov     [rsp+arg_0], rcx
0x1800132e6  push    rbp
0x1800132e7  push    rsi
0x1800132e8  push    rdi
0x1800132e9  sub     rsp, 20h
0x1800132ed  mov     rsi, cs:Feature_Ten2Loc__descriptor
0x1800132f4  mov     rdi, rdx
0x1800132f7  mov     qword ptr [rdx], 0
0x1800132fe  mov     eax, [rsi]
0x180013300  mov     [rdx], eax
0x180013302  and     eax, 6
0x180013305  cmp     al, 6
0x180013307  jz      loc_1800133A5
0x18001330d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013312  lea     r8, [rsp+38h+arg_0]
0x180013317  mov     dword ptr [rsp+38h+arg_0], 0
0x18001331f  lea     rdx, [rsp+38h+arg_8]
0x180013324  mov     ebp, eax
0x180013326  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)
0x18001332b  mov     eax, [rdi]
0x18001332d  mov     rbx, [rsp+38h+arg_8]
0x180013332  cmp     dword ptr [rsp+38h+arg_0], 0
0x180013337  mov     edx, eax
0x180013339  mov     [rdi], eax
0x18001333b  mov     ecx, eax
0x18001333d  jz      short loc_180013358
0x18001333f  test    dl, 2
0x180013342  jnz     short loc_180013358
0x180013344  and     ecx, 0FFFFF63Eh
0x18001334a  mov     eax, ebx
0x18001334c  and     eax, 9C1h
0x180013351  or      ecx, eax
0x180013353  or      ecx, 2
0x180013356  mov     [rdi], ecx
0x180013358  mov     r8d, edx
0x18001335b  and     r8d, 4
0x18001335f  jnz     short loc_180013373
0x180013361  btr     ecx, 0Ah
0x180013365  mov     eax, ebx
0x180013367  and     eax, 400h
0x18001336c  or      ecx, eax
0x18001336e  or      ecx, 4
0x180013371  mov     [rdi], ecx
0x180013373  mov     eax, edx
0x180013375  lock cmpxchg [rsi], ecx
0x180013379  jnz     short loc_180013332
0x18001337b  test    r8d, r8d
0x18001337e  jnz     short loc_180013390
0x180013380  mov     r8d, ebp
0x180013383  mov     edx, 3
0x180013388  mov     rcx, rsi
0x18001338b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180013390  mov     eax, [rdi]
0x180013392  test    al, 2
0x180013394  jnz     short loc_1800133A5
0x180013396  and     eax, 0FFFFF63Eh
0x18001339b  and     ebx, 9C1h
0x1800133a1  or      eax, ebx
0x1800133a3  mov     [rdi], eax
0x1800133a5  mov     rbx, [rsp+38h+arg_10]
0x1800133aa  mov     rax, rdi
0x1800133ad  add     rsp, 20h
0x1800133b1  pop     rdi
0x1800133b2  pop     rsi
0x1800133b3  pop     rbp
0x1800133b4  retn
```
