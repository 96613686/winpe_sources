# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18001b2dc`
- end: `0x18001b3b5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c4a4`

## callees

- `0x18001403c`
- `0x180016068`
- `0x18001b2dc`
- `0x18001bbf0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor,
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
0x18001b2dc  mov     [rsp+arg_10], rbx
0x18001b2e1  mov     [rsp+arg_0], rcx
0x18001b2e6  push    rbp
0x18001b2e7  push    rsi
0x18001b2e8  push    rdi
0x18001b2e9  sub     rsp, 20h
0x18001b2ed  mov     rsi, cs:Feature_Standalone_26_02_NonSec__descriptor
0x18001b2f4  mov     rdi, rdx
0x18001b2f7  mov     qword ptr [rdx], 0
0x18001b2fe  mov     eax, [rsi]
0x18001b300  mov     [rdx], eax
0x18001b302  and     eax, 6
0x18001b305  cmp     al, 6
0x18001b307  jz      loc_18001B3A5
0x18001b30d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001b312  lea     r8, [rsp+38h+arg_0]
0x18001b317  mov     dword ptr [rsp+38h+arg_0], 0
0x18001b31f  lea     rdx, [rsp+38h+arg_8]
0x18001b324  mov     ebp, eax
0x18001b326  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCurrentFeatureEnabledState(int *)
0x18001b32b  mov     eax, [rdi]
0x18001b32d  mov     rbx, [rsp+38h+arg_8]
0x18001b332  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001b337  mov     edx, eax
0x18001b339  mov     [rdi], eax
0x18001b33b  mov     ecx, eax
0x18001b33d  jz      short loc_18001B358
0x18001b33f  test    dl, 2
0x18001b342  jnz     short loc_18001B358
0x18001b344  and     ecx, 0FFFFF63Eh
0x18001b34a  mov     eax, ebx
0x18001b34c  and     eax, 9C1h
0x18001b351  or      ecx, eax
0x18001b353  or      ecx, 2
0x18001b356  mov     [rdi], ecx
0x18001b358  mov     r8d, edx
0x18001b35b  and     r8d, 4
0x18001b35f  jnz     short loc_18001B373
0x18001b361  btr     ecx, 0Ah
0x18001b365  mov     eax, ebx
0x18001b367  and     eax, 400h
0x18001b36c  or      ecx, eax
0x18001b36e  or      ecx, 4
0x18001b371  mov     [rdi], ecx
0x18001b373  mov     eax, edx
0x18001b375  lock cmpxchg [rsi], ecx
0x18001b379  jnz     short loc_18001B332
0x18001b37b  test    r8d, r8d
0x18001b37e  jnz     short loc_18001B390
0x18001b380  mov     r8d, ebp
0x18001b383  mov     edx, 3
0x18001b388  mov     rcx, rsi
0x18001b38b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001b390  mov     eax, [rdi]
0x18001b392  test    al, 2
0x18001b394  jnz     short loc_18001B3A5
0x18001b396  and     eax, 0FFFFF63Eh
0x18001b39b  and     ebx, 9C1h
0x18001b3a1  or      eax, ebx
0x18001b3a3  mov     [rdi], eax
0x18001b3a5  mov     rbx, [rsp+38h+arg_10]
0x18001b3aa  mov     rax, rdi
0x18001b3ad  add     rsp, 20h
0x18001b3b1  pop     rdi
0x18001b3b2  pop     rsi
0x18001b3b3  pop     rbp
0x18001b3b4  retn
```
