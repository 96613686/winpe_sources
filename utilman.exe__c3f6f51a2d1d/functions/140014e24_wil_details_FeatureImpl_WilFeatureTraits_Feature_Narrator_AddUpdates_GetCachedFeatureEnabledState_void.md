# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetCachedFeatureEnabledState(void)

- ea: `0x140014e24`
- end: `0x140014f64`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140016b74`
- `0x140018010`

## callees

- `0x14000483c`
- `0x140005430`
- `0x140009b7c`
- `0x140014e24`
- `0x140014f6c`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x140014ee2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140014ee2`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Narrator_AddUpdates__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Narrator_AddUpdates__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Narrator_AddUpdates__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_1400473C8);
      v16 = &stru_1400473C8;
      if ( !v5
        || v5 != dword_1400473DC
        || (v14[0] = 1,
            v14[1] = Feature_Narrator_AddUpdates__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_140047410, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Narrator_AddUpdates__descriptor, 0xFFFFFFFB);
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
0x140014e24  mov     [rsp+arg_10], rbx
0x140014e29  mov     [rsp+arg_18], rbp
0x140014e2e  mov     [rsp+arg_0], rcx
0x140014e33  push    rsi
0x140014e34  push    rdi
0x140014e35  push    r14
0x140014e37  sub     rsp, 30h
0x140014e3b  mov     rsi, cs:Feature_Narrator_AddUpdates__descriptor
0x140014e42  mov     rdi, rdx
0x140014e45  mov     qword ptr [rdx], 0
0x140014e4c  mov     eax, [rsi]
0x140014e4e  mov     [rdx], eax
0x140014e50  and     eax, 6
0x140014e53  cmp     al, 6
0x140014e55  jz      loc_140014F4D
0x140014e5b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140014e60  lea     r8, [rsp+48h+arg_0]
0x140014e65  mov     dword ptr [rsp+48h+arg_0], 0
0x140014e6d  lea     rdx, [rsp+48h+arg_8]
0x140014e72  mov     ebp, eax
0x140014e74  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetCurrentFeatureEnabledState(int *)
0x140014e79  mov     eax, [rdi]
0x140014e7b  mov     rbx, [rsp+48h+arg_8]
0x140014e80  cmp     dword ptr [rsp+48h+arg_0], 0
0x140014e85  mov     edx, eax
0x140014e87  mov     [rdi], eax
0x140014e89  mov     ecx, eax
0x140014e8b  jz      short loc_140014EA6
0x140014e8d  test    dl, 2
0x140014e90  jnz     short loc_140014EA6
0x140014e92  and     ecx, 0FFFFF63Eh
0x140014e98  mov     eax, ebx
0x140014e9a  and     eax, 9C1h
0x140014e9f  or      ecx, eax
0x140014ea1  or      ecx, 2
0x140014ea4  mov     [rdi], ecx
0x140014ea6  mov     r8d, edx
0x140014ea9  and     r8d, 4
0x140014ead  jnz     short loc_140014EC1
0x140014eaf  btr     ecx, 0Ah
0x140014eb3  mov     eax, ebx
0x140014eb5  and     eax, 400h
0x140014eba  or      ecx, eax
0x140014ebc  or      ecx, 4
0x140014ebf  mov     [rdi], ecx
0x140014ec1  mov     eax, edx
0x140014ec3  lock cmpxchg [rsi], ecx
0x140014ec7  jnz     short loc_140014E80
0x140014ec9  test    r8d, r8d
0x140014ecc  jnz     short loc_140014F38
0x140014ece  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140014ed4  test    eax, eax
0x140014ed6  jz      short loc_140014F38
0x140014ed8  lea     r14, stru_1400473C8
0x140014edf  mov     rcx, r14; SRWLock
0x140014ee2  call    cs:__imp_AcquireSRWLockExclusive
0x140014ee9  nop     dword ptr [rax+rax+00h]
0x140014eee  mov     eax, cs:dword_1400473DC
0x140014ef4  mov     [rsp+48h+arg_8], r14
0x140014ef9  test    ebp, ebp
0x140014efb  jz      short loc_140014F2A
0x140014efd  cmp     ebp, eax
0x140014eff  jnz     short loc_140014F2A
0x140014f01  mov     r8d, 10h; unsigned __int64
0x140014f07  mov     [rsp+48h+var_28], 1
0x140014f10  lea     rdx, [rsp+48h+var_28]; void *
0x140014f15  mov     [rsp+48h+var_20], rsi
0x140014f1a  lea     rcx, qword_140047410; this
0x140014f21  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x140014f26  test    al, al
0x140014f28  jnz     short loc_140014F2E
0x140014f2a  lock and dword ptr [rsi], 0FFFFFFFBh
0x140014f2e  lea     rcx, [rsp+48h+arg_8]
0x140014f33  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140014f38  mov     eax, [rdi]
0x140014f3a  test    al, 2
0x140014f3c  jnz     short loc_140014F4D
0x140014f3e  and     eax, 0FFFFF63Eh
0x140014f43  and     ebx, 9C1h
0x140014f49  or      eax, ebx
0x140014f4b  mov     [rdi], eax
0x140014f4d  mov     rbx, [rsp+48h+arg_10]
0x140014f52  mov     rax, rdi
0x140014f55  mov     rbp, [rsp+48h+arg_18]
0x140014f5a  add     rsp, 30h
0x140014f5e  pop     r14
0x140014f60  pop     rdi
0x140014f61  pop     rsi
0x140014f62  retn
```
