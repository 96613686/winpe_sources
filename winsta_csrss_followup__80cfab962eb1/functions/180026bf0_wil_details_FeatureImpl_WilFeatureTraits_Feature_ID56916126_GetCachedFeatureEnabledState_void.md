# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::GetCachedFeatureEnabledState(void)

- ea: `0x180026bf0`
- end: `0x180026d2a`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `314`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028a54`
- `0x180029358`
- `0x18002b36c`

## callees

- `0x1800103cc`
- `0x180010d08`
- `0x180012a70`
- `0x180026bf0`
- `0x18002774c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026cae`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026cae`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::GetCachedFeatureEnabledState(
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
  unsigned __int64 v13; // r8
  _QWORD Source[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details *v16; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v17; // [rsp+58h] [rbp+10h] BYREF

  v16 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_ID56916126__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ID56916126__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v16) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::GetCurrentFeatureEnabledState(v6, &v17, &v16);
    v7 = *(_DWORD *)a2;
    v8 = (__int16)v17;
    do
    {
      v9 = (_DWORD)v16 == 0;
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ID56916126__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v17 = &SRWLock;
      if ( !v5
        || v5 != dword_18005A9E4
        || (Source[0] = 3,
            Source[1] = Feature_ID56916126__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18005AA18, Source, v13)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_ID56916126__descriptor, 0xFFFFFFFB);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v17);
    }
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180026bf0  mov     [rsp+arg_10], rbx
0x180026bf5  mov     [rsp+arg_18], rbp
0x180026bfa  mov     [rsp+arg_0], rcx
0x180026bff  push    rsi
0x180026c00  push    rdi
0x180026c01  push    r14
0x180026c03  sub     rsp, 30h
0x180026c07  mov     rsi, cs:Feature_ID56916126__descriptor
0x180026c0e  mov     rdi, rdx
0x180026c11  mov     qword ptr [rdx], 0
0x180026c18  mov     eax, [rsi]
0x180026c1a  mov     [rdx], eax
0x180026c1c  and     eax, 6
0x180026c1f  cmp     al, 6
0x180026c21  jz      loc_180026D13
0x180026c27  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180026c2c  lea     r8, [rsp+48h+arg_0]
0x180026c31  mov     dword ptr [rsp+48h+arg_0], 0
0x180026c39  lea     rdx, [rsp+48h+arg_8]
0x180026c3e  mov     ebp, eax
0x180026c40  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::GetCurrentFeatureEnabledState(int *)
0x180026c45  mov     eax, [rdi]
0x180026c47  mov     rbx, [rsp+48h+arg_8]
0x180026c4c  cmp     dword ptr [rsp+48h+arg_0], 0
0x180026c51  mov     edx, eax
0x180026c53  mov     [rdi], eax
0x180026c55  mov     ecx, eax
0x180026c57  jz      short loc_180026C72
0x180026c59  test    dl, 2
0x180026c5c  jnz     short loc_180026C72
0x180026c5e  and     ecx, 0FFFFF63Eh
0x180026c64  mov     eax, ebx
0x180026c66  and     eax, 9C1h
0x180026c6b  or      ecx, eax
0x180026c6d  or      ecx, 2
0x180026c70  mov     [rdi], ecx
0x180026c72  mov     r8d, edx
0x180026c75  and     r8d, 4
0x180026c79  jnz     short loc_180026C8D
0x180026c7b  btr     ecx, 0Ah
0x180026c7f  mov     eax, ebx
0x180026c81  and     eax, 400h
0x180026c86  or      ecx, eax
0x180026c88  or      ecx, 4
0x180026c8b  mov     [rdi], ecx
0x180026c8d  mov     eax, edx
0x180026c8f  lock cmpxchg [rsi], ecx
0x180026c93  jnz     short loc_180026C4C
0x180026c95  test    r8d, r8d
0x180026c98  jnz     short loc_180026CFE
0x180026c9a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180026ca0  test    eax, eax
0x180026ca2  jz      short loc_180026CFE
0x180026ca4  lea     r14, SRWLock
0x180026cab  mov     rcx, r14; SRWLock
0x180026cae  call    cs:__imp_AcquireSRWLockExclusive
0x180026cb5  nop     dword ptr [rax+rax+00h]
0x180026cba  mov     eax, cs:dword_18005A9E4
0x180026cc0  mov     [rsp+48h+arg_8], r14
0x180026cc5  test    ebp, ebp
0x180026cc7  jz      short loc_180026CF0
0x180026cc9  cmp     ebp, eax
0x180026ccb  jnz     short loc_180026CF0
0x180026ccd  lea     rdx, [rsp+48h+Source]; Source
0x180026cd2  mov     [rsp+48h+Source], 3
0x180026cdb  lea     rcx, qword_18005AA18; this
0x180026ce2  mov     [rsp+48h+var_20], rsi
0x180026ce7  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180026cec  test    al, al
0x180026cee  jnz     short loc_180026CF4
0x180026cf0  lock and dword ptr [rsi], 0FFFFFFFBh
0x180026cf4  lea     rcx, [rsp+48h+arg_8]
0x180026cf9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180026cfe  mov     eax, [rdi]
0x180026d00  test    al, 2
0x180026d02  jnz     short loc_180026D13
0x180026d04  and     eax, 0FFFFF63Eh
0x180026d09  and     ebx, 9C1h
0x180026d0f  or      eax, ebx
0x180026d11  mov     [rdi], eax
0x180026d13  mov     rbx, [rsp+48h+arg_10]
0x180026d18  mov     rax, rdi
0x180026d1b  mov     rbp, [rsp+48h+arg_18]
0x180026d20  add     rsp, 30h
0x180026d24  pop     r14
0x180026d26  pop     rdi
0x180026d27  pop     rsi
0x180026d28  retn
```
