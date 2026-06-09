# wil::details::FeatureImpl<__WilFeatureTraits_Feature_MIDI2>::GetCachedFeatureEnabledState(void)

- ea: `0x18001420c`
- end: `0x1800142e5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MIDI2@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800157c8`
- `0x180016540`

## callees

- `0x18001403c`
- `0x18001420c`
- `0x18001441c`
- `0x180016068`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_MIDI2>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_MIDI2__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_MIDI2__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_MIDI2>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_MIDI2__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_MIDI2__descriptor,
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
0x18001420c  mov     [rsp+arg_10], rbx
0x180014211  mov     [rsp+arg_0], rcx
0x180014216  push    rbp
0x180014217  push    rsi
0x180014218  push    rdi
0x180014219  sub     rsp, 20h
0x18001421d  mov     rsi, cs:Feature_MIDI2__descriptor
0x180014224  mov     rdi, rdx
0x180014227  mov     qword ptr [rdx], 0
0x18001422e  mov     eax, [rsi]
0x180014230  mov     [rdx], eax
0x180014232  and     eax, 6
0x180014235  cmp     al, 6
0x180014237  jz      loc_1800142D5
0x18001423d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180014242  lea     r8, [rsp+38h+arg_0]
0x180014247  mov     dword ptr [rsp+38h+arg_0], 0
0x18001424f  lea     rdx, [rsp+38h+arg_8]
0x180014254  mov     ebp, eax
0x180014256  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MIDI2@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MIDI2>::GetCurrentFeatureEnabledState(int *)
0x18001425b  mov     eax, [rdi]
0x18001425d  mov     rbx, [rsp+38h+arg_8]
0x180014262  cmp     dword ptr [rsp+38h+arg_0], 0
0x180014267  mov     edx, eax
0x180014269  mov     [rdi], eax
0x18001426b  mov     ecx, eax
0x18001426d  jz      short loc_180014288
0x18001426f  test    dl, 2
0x180014272  jnz     short loc_180014288
0x180014274  and     ecx, 0FFFFF63Eh
0x18001427a  mov     eax, ebx
0x18001427c  and     eax, 9C1h
0x180014281  or      ecx, eax
0x180014283  or      ecx, 2
0x180014286  mov     [rdi], ecx
0x180014288  mov     r8d, edx
0x18001428b  and     r8d, 4
0x18001428f  jnz     short loc_1800142A3
0x180014291  btr     ecx, 0Ah
0x180014295  mov     eax, ebx
0x180014297  and     eax, 400h
0x18001429c  or      ecx, eax
0x18001429e  or      ecx, 4
0x1800142a1  mov     [rdi], ecx
0x1800142a3  mov     eax, edx
0x1800142a5  lock cmpxchg [rsi], ecx
0x1800142a9  jnz     short loc_180014262
0x1800142ab  test    r8d, r8d
0x1800142ae  jnz     short loc_1800142C0
0x1800142b0  mov     r8d, ebp
0x1800142b3  mov     edx, 3
0x1800142b8  mov     rcx, rsi
0x1800142bb  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800142c0  mov     eax, [rdi]
0x1800142c2  test    al, 2
0x1800142c4  jnz     short loc_1800142D5
0x1800142c6  and     eax, 0FFFFF63Eh
0x1800142cb  and     ebx, 9C1h
0x1800142d1  or      eax, ebx
0x1800142d3  mov     [rdi], eax
0x1800142d5  mov     rbx, [rsp+38h+arg_10]
0x1800142da  mov     rax, rdi
0x1800142dd  add     rsp, 20h
0x1800142e1  pop     rdi
0x1800142e2  pop     rsi
0x1800142e3  pop     rbp
0x1800142e4  retn
```
