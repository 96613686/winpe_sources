# wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_TestConfNum>::GetCachedFeatureEnabledState(void)

- ea: `0x140014094`
- end: `0x14001417e`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilExternalFeatureTraits_Feature_TestConfNum@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `234`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140014184`
- `0x140014220`

## callees

- `0x140005090`
- `0x140005154`
- `0x140013f74`
- `0x140014094`
- `0x14001aa60`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_TestConfNum>::GetCachedFeatureEnabledState(
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
    wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_TestConfNum>::GetCurrentFeatureEnabledState(
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges((volatile signed __int32 *)a1, 64, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x140014094  mov     [rsp+arg_10], rbx
0x140014099  push    rbp
0x14001409a  push    rsi
0x14001409b  push    rdi
0x14001409c  sub     rsp, 40h
0x1400140a0  mov     rax, cs:__security_cookie
0x1400140a7  xor     rax, rsp
0x1400140aa  mov     [rsp+58h+var_28], rax
0x1400140af  mov     qword ptr [rdx], 0
0x1400140b6  mov     rdi, rdx
0x1400140b9  mov     eax, [rcx]
0x1400140bb  mov     rsi, rcx
0x1400140be  mov     [rdx], eax
0x1400140c0  and     eax, 6
0x1400140c3  cmp     al, 6
0x1400140c5  jz      loc_140014161
0x1400140cb  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1400140d0  lea     r8, [rsp+58h+var_30]
0x1400140d5  mov     [rsp+58h+var_30], 0
0x1400140dd  lea     rdx, [rsp+58h+var_38]
0x1400140e2  mov     ebp, eax
0x1400140e4  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilExternalFeatureTraits_Feature_TestConfNum@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_TestConfNum>::GetCurrentFeatureEnabledState(int *)
0x1400140e9  mov     eax, [rdi]
0x1400140eb  mov     rbx, [rsp+58h+var_38]
0x1400140f0  cmp     [rsp+58h+var_30], 0
0x1400140f5  mov     edx, eax
0x1400140f7  mov     [rdi], eax
0x1400140f9  mov     ecx, eax
0x1400140fb  jz      short loc_140014116
0x1400140fd  test    dl, 2
0x140014100  jnz     short loc_140014116
0x140014102  and     ecx, 0FFFFF63Eh
0x140014108  mov     eax, ebx
0x14001410a  and     eax, 9C1h
0x14001410f  or      ecx, eax
0x140014111  or      ecx, 2
0x140014114  mov     [rdi], ecx
0x140014116  test    dl, 4
0x140014119  jnz     short loc_14001412D
0x14001411b  btr     ecx, 0Ah
0x14001411f  mov     eax, ebx
0x140014121  and     eax, 400h
0x140014126  or      ecx, eax
0x140014128  or      ecx, 4
0x14001412b  mov     [rdi], ecx
0x14001412d  mov     eax, edx
0x14001412f  lock cmpxchg [rsi], ecx
0x140014133  jnz     short loc_1400140F0
0x140014135  test    dl, 4
0x140014138  jnz     short loc_14001414A
0x14001413a  mov     r8d, ebp
0x14001413d  mov     edx, 40h ; '@'
0x140014142  mov     rcx, rsi
0x140014145  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14001414a  mov     ecx, [rdi]
0x14001414c  test    cl, 2
0x14001414f  jnz     short loc_140014161
0x140014151  and     ecx, 0FFFFF63Eh
0x140014157  and     ebx, 9C1h
0x14001415d  or      ecx, ebx
0x14001415f  mov     [rdi], ecx
0x140014161  mov     rax, rdi
0x140014164  mov     rcx, [rsp+58h+var_28]
0x140014169  xor     rcx, rsp; StackCookie
0x14001416c  call    __security_check_cookie
0x140014171  mov     rbx, [rsp+58h+arg_10]
0x140014176  add     rsp, 40h
0x14001417a  pop     rdi
0x14001417b  pop     rsi
0x14001417c  pop     rbp
0x14001417d  retn
```
