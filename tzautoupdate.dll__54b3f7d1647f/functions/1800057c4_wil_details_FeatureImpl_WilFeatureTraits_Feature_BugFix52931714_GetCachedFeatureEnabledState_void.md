# wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix52931714>::GetCachedFeatureEnabledState(void)

- ea: `0x1800057c4`
- end: `0x18000589d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix52931714@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008414`
- `0x18000af24`

## callees

- `0x180005384`
- `0x1800057c4`
- `0x180005b9c`
- `0x180009148`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix52931714>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_BugFix52931714__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_BugFix52931714__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix52931714>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_BugFix52931714__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_BugFix52931714__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x1800057c4  mov     [rsp+arg_10], rbx
0x1800057c9  mov     [rsp+arg_0], rcx
0x1800057ce  push    rbp
0x1800057cf  push    rsi
0x1800057d0  push    rdi
0x1800057d1  sub     rsp, 20h
0x1800057d5  mov     rsi, cs:Feature_BugFix52931714__descriptor
0x1800057dc  mov     rdi, rdx
0x1800057df  mov     qword ptr [rdx], 0
0x1800057e6  mov     eax, [rsi]
0x1800057e8  mov     [rdx], eax
0x1800057ea  and     eax, 6
0x1800057ed  cmp     al, 6
0x1800057ef  jz      loc_18000588D
0x1800057f5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800057fa  lea     r8, [rsp+38h+arg_0]
0x1800057ff  mov     dword ptr [rsp+38h+arg_0], 0
0x180005807  lea     rdx, [rsp+38h+arg_8]
0x18000580c  mov     ebp, eax
0x18000580e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix52931714@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix52931714>::GetCurrentFeatureEnabledState(int *)
0x180005813  mov     eax, [rdi]
0x180005815  mov     rbx, [rsp+38h+arg_8]
0x18000581a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000581f  mov     edx, eax
0x180005821  mov     [rdi], eax
0x180005823  mov     ecx, eax
0x180005825  jz      short loc_180005840
0x180005827  test    dl, 2
0x18000582a  jnz     short loc_180005840
0x18000582c  and     ecx, 0FFFFF63Eh
0x180005832  mov     eax, ebx
0x180005834  and     eax, 9C1h
0x180005839  or      ecx, eax
0x18000583b  or      ecx, 2
0x18000583e  mov     [rdi], ecx
0x180005840  mov     r8d, edx
0x180005843  and     r8d, 4
0x180005847  jnz     short loc_18000585B
0x180005849  btr     ecx, 0Ah
0x18000584d  mov     eax, ebx
0x18000584f  and     eax, 400h
0x180005854  or      ecx, eax
0x180005856  or      ecx, 4
0x180005859  mov     [rdi], ecx
0x18000585b  mov     eax, edx
0x18000585d  lock cmpxchg [rsi], ecx
0x180005861  jnz     short loc_18000581A
0x180005863  test    r8d, r8d
0x180005866  jnz     short loc_180005878
0x180005868  mov     r8d, ebp
0x18000586b  mov     edx, 3
0x180005870  mov     rcx, rsi
0x180005873  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180005878  mov     eax, [rdi]
0x18000587a  test    al, 2
0x18000587c  jnz     short loc_18000588D
0x18000587e  and     eax, 0FFFFF63Eh
0x180005883  and     ebx, 9C1h
0x180005889  or      eax, ebx
0x18000588b  mov     [rdi], eax
0x18000588d  mov     rbx, [rsp+38h+arg_10]
0x180005892  mov     rax, rdi
0x180005895  add     rsp, 20h
0x180005899  pop     rdi
0x18000589a  pop     rsi
0x18000589b  pop     rbp
0x18000589c  retn
```
