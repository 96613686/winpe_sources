# wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2602>::GetCachedFeatureEnabledState(void)

- ea: `0x18001ae7c`
- end: `0x18001af55`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2602@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c204`
- `0x18001c834`

## callees

- `0x18001403c`
- `0x180016068`
- `0x18001ae7c`
- `0x18001b8e4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2602>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_MediaQI2602__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_MediaQI2602__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2602>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_MediaQI2602__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_MediaQI2602__descriptor,
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
0x18001ae7c  mov     [rsp+arg_10], rbx
0x18001ae81  mov     [rsp+arg_0], rcx
0x18001ae86  push    rbp
0x18001ae87  push    rsi
0x18001ae88  push    rdi
0x18001ae89  sub     rsp, 20h
0x18001ae8d  mov     rsi, cs:Feature_MediaQI2602__descriptor
0x18001ae94  mov     rdi, rdx
0x18001ae97  mov     qword ptr [rdx], 0
0x18001ae9e  mov     eax, [rsi]
0x18001aea0  mov     [rdx], eax
0x18001aea2  and     eax, 6
0x18001aea5  cmp     al, 6
0x18001aea7  jz      loc_18001AF45
0x18001aead  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001aeb2  lea     r8, [rsp+38h+arg_0]
0x18001aeb7  mov     dword ptr [rsp+38h+arg_0], 0
0x18001aebf  lea     rdx, [rsp+38h+arg_8]
0x18001aec4  mov     ebp, eax
0x18001aec6  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2602@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2602>::GetCurrentFeatureEnabledState(int *)
0x18001aecb  mov     eax, [rdi]
0x18001aecd  mov     rbx, [rsp+38h+arg_8]
0x18001aed2  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001aed7  mov     edx, eax
0x18001aed9  mov     [rdi], eax
0x18001aedb  mov     ecx, eax
0x18001aedd  jz      short loc_18001AEF8
0x18001aedf  test    dl, 2
0x18001aee2  jnz     short loc_18001AEF8
0x18001aee4  and     ecx, 0FFFFF63Eh
0x18001aeea  mov     eax, ebx
0x18001aeec  and     eax, 9C1h
0x18001aef1  or      ecx, eax
0x18001aef3  or      ecx, 2
0x18001aef6  mov     [rdi], ecx
0x18001aef8  mov     r8d, edx
0x18001aefb  and     r8d, 4
0x18001aeff  jnz     short loc_18001AF13
0x18001af01  btr     ecx, 0Ah
0x18001af05  mov     eax, ebx
0x18001af07  and     eax, 400h
0x18001af0c  or      ecx, eax
0x18001af0e  or      ecx, 4
0x18001af11  mov     [rdi], ecx
0x18001af13  mov     eax, edx
0x18001af15  lock cmpxchg [rsi], ecx
0x18001af19  jnz     short loc_18001AED2
0x18001af1b  test    r8d, r8d
0x18001af1e  jnz     short loc_18001AF30
0x18001af20  mov     r8d, ebp
0x18001af23  mov     edx, 3
0x18001af28  mov     rcx, rsi
0x18001af2b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001af30  mov     eax, [rdi]
0x18001af32  test    al, 2
0x18001af34  jnz     short loc_18001AF45
0x18001af36  and     eax, 0FFFFF63Eh
0x18001af3b  and     ebx, 9C1h
0x18001af41  or      eax, ebx
0x18001af43  mov     [rdi], eax
0x18001af45  mov     rbx, [rsp+38h+arg_10]
0x18001af4a  mov     rax, rdi
0x18001af4d  add     rsp, 20h
0x18001af51  pop     rdi
0x18001af52  pop     rsi
0x18001af53  pop     rbp
0x18001af54  retn
```
