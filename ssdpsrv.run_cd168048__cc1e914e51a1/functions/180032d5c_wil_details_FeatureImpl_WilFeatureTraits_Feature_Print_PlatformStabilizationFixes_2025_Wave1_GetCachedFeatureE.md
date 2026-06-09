# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetCachedFeatureEnabledState(void)

- ea: `0x180032d5c`
- end: `0x180032e9c`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800339f8`
- `0x180033c20`

## callees

- `0x180024d20`
- `0x18002b074`
- `0x18002e454`
- `0x180032d5c`
- `0x18003317c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180032e1a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180032e1a`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetCachedFeatureEnabledState(
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
  int v12; // r8d
  _QWORD v14[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details *v15; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v16; // [rsp+58h] [rbp+10h] BYREF

  v15 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Print_PlatformStabilizationFixes_2025_Wave1__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Print_PlatformStabilizationFixes_2025_Wave1__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetCurrentFeatureEnabledState(
      v6,
      &v16,
      &v15);
    v7 = *(_DWORD *)a2;
    v8 = (__int16)v16;
    do
    {
      v9 = (_DWORD)v15 == 0;
      v10 = v7;
      *(_DWORD *)a2 = v7;
      v11 = v7;
      if ( !v9 && (v7 & 2) == 0 )
      {
        v11 = v8 & 0x9C1 | v7 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v11;
      }
      v12 = v7 & 4;
      if ( (v7 & 4) == 0 )
      {
        v11 = v8 & 0x400 | v11 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v11;
      }
      v7 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_Print_PlatformStabilizationFixes_2025_Wave1__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800443A4
        || (v14[0] = 3,
            v14[1] = Feature_Print_PlatformStabilizationFixes_2025_Wave1__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800443D8, v14, 0x10u)) )
      {
        _InterlockedAnd(
          (volatile signed __int32 *)Feature_Print_PlatformStabilizationFixes_2025_Wave1__descriptor,
          0xFFFFFFFB);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
    }
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180032d5c  mov     [rsp+arg_10], rbx
0x180032d61  mov     [rsp+arg_18], rbp
0x180032d66  mov     [rsp+arg_0], rcx
0x180032d6b  push    rsi
0x180032d6c  push    rdi
0x180032d6d  push    r14
0x180032d6f  sub     rsp, 30h
0x180032d73  mov     rsi, cs:Feature_Print_PlatformStabilizationFixes_2025_Wave1__descriptor
0x180032d7a  mov     rdi, rdx
0x180032d7d  mov     qword ptr [rdx], 0
0x180032d84  mov     eax, [rsi]
0x180032d86  mov     [rdx], eax
0x180032d88  and     eax, 6
0x180032d8b  cmp     al, 6
0x180032d8d  jz      loc_180032E85
0x180032d93  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180032d98  lea     r8, [rsp+48h+arg_0]
0x180032d9d  mov     dword ptr [rsp+48h+arg_0], 0
0x180032da5  lea     rdx, [rsp+48h+arg_8]
0x180032daa  mov     ebp, eax
0x180032dac  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetCurrentFeatureEnabledState(int *)
0x180032db1  mov     eax, [rdi]
0x180032db3  mov     rbx, [rsp+48h+arg_8]
0x180032db8  cmp     dword ptr [rsp+48h+arg_0], 0
0x180032dbd  mov     edx, eax
0x180032dbf  mov     [rdi], eax
0x180032dc1  mov     ecx, eax
0x180032dc3  jz      short loc_180032DDE
0x180032dc5  test    dl, 2
0x180032dc8  jnz     short loc_180032DDE
0x180032dca  and     ecx, 0FFFFF63Eh
0x180032dd0  mov     eax, ebx
0x180032dd2  and     eax, 9C1h
0x180032dd7  or      ecx, eax
0x180032dd9  or      ecx, 2
0x180032ddc  mov     [rdi], ecx
0x180032dde  mov     r8d, edx
0x180032de1  and     r8d, 4
0x180032de5  jnz     short loc_180032DF9
0x180032de7  btr     ecx, 0Ah
0x180032deb  mov     eax, ebx
0x180032ded  and     eax, 400h
0x180032df2  or      ecx, eax
0x180032df4  or      ecx, 4
0x180032df7  mov     [rdi], ecx
0x180032df9  mov     eax, edx
0x180032dfb  lock cmpxchg [rsi], ecx
0x180032dff  jnz     short loc_180032DB8
0x180032e01  test    r8d, r8d
0x180032e04  jnz     short loc_180032E70
0x180032e06  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180032e0c  test    eax, eax
0x180032e0e  jz      short loc_180032E70
0x180032e10  lea     r14, SRWLock
0x180032e17  mov     rcx, r14; SRWLock
0x180032e1a  call    cs:__imp_AcquireSRWLockExclusive
0x180032e21  nop     dword ptr [rax+rax+00h]
0x180032e26  mov     eax, cs:dword_1800443A4
0x180032e2c  mov     [rsp+48h+arg_8], r14
0x180032e31  test    ebp, ebp
0x180032e33  jz      short loc_180032E62
0x180032e35  cmp     ebp, eax
0x180032e37  jnz     short loc_180032E62
0x180032e39  mov     r8d, 10h; unsigned __int64
0x180032e3f  mov     [rsp+48h+var_28], 3
0x180032e48  lea     rdx, [rsp+48h+var_28]; void *
0x180032e4d  mov     [rsp+48h+var_20], rsi
0x180032e52  lea     rcx, qword_1800443D8; this
0x180032e59  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180032e5e  test    al, al
0x180032e60  jnz     short loc_180032E66
0x180032e62  lock and dword ptr [rsi], 0FFFFFFFBh
0x180032e66  lea     rcx, [rsp+48h+arg_8]
0x180032e6b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180032e70  mov     eax, [rdi]
0x180032e72  test    al, 2
0x180032e74  jnz     short loc_180032E85
0x180032e76  and     eax, 0FFFFF63Eh
0x180032e7b  and     ebx, 9C1h
0x180032e81  or      eax, ebx
0x180032e83  mov     [rdi], eax
0x180032e85  mov     rbx, [rsp+48h+arg_10]
0x180032e8a  mov     rax, rdi
0x180032e8d  mov     rbp, [rsp+48h+arg_18]
0x180032e92  add     rsp, 30h
0x180032e96  pop     r14
0x180032e98  pop     rdi
0x180032e99  pop     rsi
0x180032e9a  retn
```
