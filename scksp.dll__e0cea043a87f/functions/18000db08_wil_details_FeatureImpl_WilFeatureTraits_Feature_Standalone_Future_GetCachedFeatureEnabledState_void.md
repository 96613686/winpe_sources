# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)

- ea: `0x18000db08`
- end: `0x18000dbe1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010788`

## callees

- `0x18000d5d0`
- `0x18000db08`
- `0x18000dedc`
- `0x180011590`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  int v5; // ebp
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
  v3 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCurrentFeatureEnabledState(
      v6,
      &v14,
      &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_Future__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_Future__descriptor,
        3,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18000db08  mov     [rsp+arg_10], rbx
0x18000db0d  mov     [rsp+arg_0], rcx
0x18000db12  push    rbp
0x18000db13  push    rsi
0x18000db14  push    rdi
0x18000db15  sub     rsp, 20h
0x18000db19  mov     rsi, cs:Feature_Standalone_Future__descriptor
0x18000db20  mov     rdi, rdx
0x18000db23  mov     qword ptr [rdx], 0
0x18000db2a  mov     eax, [rsi]
0x18000db2c  mov     [rdx], eax
0x18000db2e  and     eax, 6
0x18000db31  cmp     al, 6
0x18000db33  jz      loc_18000DBD1
0x18000db39  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000db3e  lea     r8, [rsp+38h+arg_0]
0x18000db43  mov     dword ptr [rsp+38h+arg_0], 0
0x18000db4b  lea     rdx, [rsp+38h+arg_8]
0x18000db50  mov     ebp, eax
0x18000db52  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCurrentFeatureEnabledState(int *)
0x18000db57  mov     eax, [rdi]
0x18000db59  mov     rbx, [rsp+38h+arg_8]
0x18000db5e  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000db63  mov     edx, eax
0x18000db65  mov     [rdi], eax
0x18000db67  mov     ecx, eax
0x18000db69  jz      short loc_18000DB84
0x18000db6b  test    dl, 2
0x18000db6e  jnz     short loc_18000DB84
0x18000db70  and     ecx, 0FFFFF63Eh
0x18000db76  mov     eax, ebx
0x18000db78  and     eax, 9C1h
0x18000db7d  or      ecx, eax
0x18000db7f  or      ecx, 2
0x18000db82  mov     [rdi], ecx
0x18000db84  mov     r8d, edx
0x18000db87  and     r8d, 4
0x18000db8b  jnz     short loc_18000DB9F
0x18000db8d  btr     ecx, 0Ah
0x18000db91  mov     eax, ebx
0x18000db93  and     eax, 400h
0x18000db98  or      ecx, eax
0x18000db9a  or      ecx, 4
0x18000db9d  mov     [rdi], ecx
0x18000db9f  mov     eax, edx
0x18000dba1  lock cmpxchg [rsi], ecx
0x18000dba5  jnz     short loc_18000DB5E
0x18000dba7  test    r8d, r8d
0x18000dbaa  jnz     short loc_18000DBBC
0x18000dbac  mov     r8d, ebp
0x18000dbaf  mov     edx, 3
0x18000dbb4  mov     rcx, rsi
0x18000dbb7  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000dbbc  mov     eax, [rdi]
0x18000dbbe  test    al, 2
0x18000dbc0  jnz     short loc_18000DBD1
0x18000dbc2  and     eax, 0FFFFF63Eh
0x18000dbc7  and     ebx, 9C1h
0x18000dbcd  or      eax, ebx
0x18000dbcf  mov     [rdi], eax
0x18000dbd1  mov     rbx, [rsp+38h+arg_10]
0x18000dbd6  mov     rax, rdi
0x18000dbd9  add     rsp, 20h
0x18000dbdd  pop     rdi
0x18000dbde  pop     rsi
0x18000dbdf  pop     rbp
0x18000dbe0  retn
```
