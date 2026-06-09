# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_BufferOverflowFix>::GetCachedFeatureEnabledState(void)

- ea: `0x18001b090`
- end: `0x18001b17b`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_BufferOverflowFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800201c8`
- `0x180026fa8`

## callees

- `0x1800015f0`
- `0x18001aba4`
- `0x18001b090`
- `0x18001bb4c`
- `0x180026a48`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_BufferOverflowFix>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Servicing_BufferOverflowFix__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_BufferOverflowFix__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_BufferOverflowFix>::GetCurrentFeatureEnabledState(
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
      v6 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_Servicing_BufferOverflowFix__descriptor,
             v10,
             v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Servicing_BufferOverflowFix__descriptor,
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
0x18001b090  push    rbx
0x18001b092  push    rbp
0x18001b093  push    rsi
0x18001b094  push    rdi
0x18001b095  sub     rsp, 48h
0x18001b099  mov     rax, cs:__security_cookie
0x18001b0a0  xor     rax, rsp
0x18001b0a3  mov     [rsp+68h+var_38], rax
0x18001b0a8  mov     rsi, cs:Feature_Servicing_BufferOverflowFix__descriptor
0x18001b0af  mov     rdi, rdx
0x18001b0b2  mov     qword ptr [rdx], 0
0x18001b0b9  mov     eax, [rsi]
0x18001b0bb  mov     [rdx], eax
0x18001b0bd  and     eax, 6
0x18001b0c0  cmp     al, 6
0x18001b0c2  jz      loc_18001B162
0x18001b0c8  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001b0cd  lea     r8, [rsp+68h+var_40]
0x18001b0d2  mov     [rsp+68h+var_40], 0
0x18001b0da  lea     rdx, [rsp+68h+var_48]
0x18001b0df  mov     ebp, eax
0x18001b0e1  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_BufferOverflowFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_BufferOverflowFix>::GetCurrentFeatureEnabledState(int *)
0x18001b0e6  mov     eax, [rdi]
0x18001b0e8  mov     rbx, [rsp+68h+var_48]
0x18001b0ed  cmp     [rsp+68h+var_40], 0
0x18001b0f2  mov     edx, eax
0x18001b0f4  mov     [rdi], eax
0x18001b0f6  mov     ecx, eax
0x18001b0f8  jz      short loc_18001B113
0x18001b0fa  test    dl, 2
0x18001b0fd  jnz     short loc_18001B113
0x18001b0ff  and     ecx, 0FFFFF63Eh
0x18001b105  mov     eax, ebx
0x18001b107  and     eax, 9C1h
0x18001b10c  or      ecx, eax
0x18001b10e  or      ecx, 2
0x18001b111  mov     [rdi], ecx
0x18001b113  mov     r8d, edx
0x18001b116  and     r8d, 4
0x18001b11a  jnz     short loc_18001B12E
0x18001b11c  btr     ecx, 0Ah
0x18001b120  mov     eax, ebx
0x18001b122  and     eax, 400h
0x18001b127  or      ecx, eax
0x18001b129  or      ecx, 4
0x18001b12c  mov     [rdi], ecx
0x18001b12e  mov     eax, edx
0x18001b130  lock cmpxchg [rsi], ecx
0x18001b134  jnz     short loc_18001B0ED
0x18001b136  test    r8d, r8d
0x18001b139  jnz     short loc_18001B14B
0x18001b13b  mov     r8d, ebp
0x18001b13e  mov     edx, 3
0x18001b143  mov     rcx, rsi
0x18001b146  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001b14b  mov     ecx, [rdi]
0x18001b14d  test    cl, 2
0x18001b150  jnz     short loc_18001B162
0x18001b152  and     ecx, 0FFFFF63Eh
0x18001b158  and     ebx, 9C1h
0x18001b15e  or      ecx, ebx
0x18001b160  mov     [rdi], ecx
0x18001b162  mov     rax, rdi
0x18001b165  mov     rcx, [rsp+68h+var_38]
0x18001b16a  xor     rcx, rsp; StackCookie
0x18001b16d  call    __security_check_cookie
0x18001b172  add     rsp, 48h
0x18001b176  pop     rdi
0x18001b177  pop     rsi
0x18001b178  pop     rbp
0x18001b179  pop     rbx
0x18001b17a  retn
```
