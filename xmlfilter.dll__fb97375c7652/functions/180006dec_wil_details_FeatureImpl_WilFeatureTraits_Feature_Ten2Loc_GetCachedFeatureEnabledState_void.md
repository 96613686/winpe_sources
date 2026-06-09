# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(void)

- ea: `0x180006dec`
- end: `0x180006ec5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d394`

## callees

- `0x180005dd0`
- `0x180006dec`
- `0x180007680`
- `0x18000c3f0`

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
0x180006dec  mov     [rsp+arg_10], rbx
0x180006df1  mov     [rsp+arg_0], rcx
0x180006df6  push    rbp
0x180006df7  push    rsi
0x180006df8  push    rdi
0x180006df9  sub     rsp, 20h
0x180006dfd  mov     rsi, cs:Feature_Ten2Loc__descriptor
0x180006e04  mov     rdi, rdx
0x180006e07  mov     qword ptr [rdx], 0
0x180006e0e  mov     eax, [rsi]
0x180006e10  mov     [rdx], eax
0x180006e12  and     eax, 6
0x180006e15  cmp     al, 6
0x180006e17  jz      loc_180006EB5
0x180006e1d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180006e22  lea     r8, [rsp+38h+arg_0]
0x180006e27  mov     dword ptr [rsp+38h+arg_0], 0
0x180006e2f  lea     rdx, [rsp+38h+arg_8]
0x180006e34  mov     ebp, eax
0x180006e36  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)
0x180006e3b  mov     eax, [rdi]
0x180006e3d  mov     rbx, [rsp+38h+arg_8]
0x180006e42  cmp     dword ptr [rsp+38h+arg_0], 0
0x180006e47  mov     edx, eax
0x180006e49  mov     [rdi], eax
0x180006e4b  mov     ecx, eax
0x180006e4d  jz      short loc_180006E68
0x180006e4f  test    dl, 2
0x180006e52  jnz     short loc_180006E68
0x180006e54  and     ecx, 0FFFFF63Eh
0x180006e5a  mov     eax, ebx
0x180006e5c  and     eax, 9C1h
0x180006e61  or      ecx, eax
0x180006e63  or      ecx, 2
0x180006e66  mov     [rdi], ecx
0x180006e68  mov     r8d, edx
0x180006e6b  and     r8d, 4
0x180006e6f  jnz     short loc_180006E83
0x180006e71  btr     ecx, 0Ah
0x180006e75  mov     eax, ebx
0x180006e77  and     eax, 400h
0x180006e7c  or      ecx, eax
0x180006e7e  or      ecx, 4
0x180006e81  mov     [rdi], ecx
0x180006e83  mov     eax, edx
0x180006e85  lock cmpxchg [rsi], ecx
0x180006e89  jnz     short loc_180006E42
0x180006e8b  test    r8d, r8d
0x180006e8e  jnz     short loc_180006EA0
0x180006e90  mov     r8d, ebp
0x180006e93  mov     edx, 3
0x180006e98  mov     rcx, rsi
0x180006e9b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180006ea0  mov     eax, [rdi]
0x180006ea2  test    al, 2
0x180006ea4  jnz     short loc_180006EB5
0x180006ea6  and     eax, 0FFFFF63Eh
0x180006eab  and     ebx, 9C1h
0x180006eb1  or      eax, ebx
0x180006eb3  mov     [rdi], eax
0x180006eb5  mov     rbx, [rsp+38h+arg_10]
0x180006eba  mov     rax, rdi
0x180006ebd  add     rsp, 20h
0x180006ec1  pop     rdi
0x180006ec2  pop     rsi
0x180006ec3  pop     rbp
0x180006ec4  retn
```
