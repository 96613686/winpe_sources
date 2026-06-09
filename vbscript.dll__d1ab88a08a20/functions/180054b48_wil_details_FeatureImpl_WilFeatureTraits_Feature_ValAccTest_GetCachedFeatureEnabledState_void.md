# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180054b48`
- end: `0x180054c88`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800574b4`
- `0x180057e60`

## callees

- `0x180032698`
- `0x180033f2c`
- `0x18003b8cc`
- `0x180054b48`
- `0x1800550c0`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180054c06`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180054c06`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(
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
  _QWORD Source[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details *v15; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v16; // [rsp+58h] [rbp+10h] BYREF

  v15 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_ValAccTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValAccTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValAccTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_18009386C
        || (Source[0] = 3,
            Source[1] = Feature_ValAccTest__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800938A0, Source, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_ValAccTest__descriptor, 0xFFFFFFFB);
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
0x180054b48  mov     [rsp+arg_10], rbx
0x180054b4d  mov     [rsp+arg_18], rbp
0x180054b52  mov     [rsp+arg_0], rcx
0x180054b57  push    rsi
0x180054b58  push    rdi
0x180054b59  push    r14
0x180054b5b  sub     rsp, 30h
0x180054b5f  mov     rsi, cs:Feature_ValAccTest__descriptor
0x180054b66  mov     rdi, rdx
0x180054b69  mov     qword ptr [rdx], 0
0x180054b70  mov     eax, [rsi]
0x180054b72  mov     [rdx], eax
0x180054b74  and     eax, 6
0x180054b77  cmp     al, 6
0x180054b79  jz      loc_180054C71
0x180054b7f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180054b84  lea     r8, [rsp+48h+arg_0]
0x180054b89  mov     dword ptr [rsp+48h+arg_0], 0
0x180054b91  lea     rdx, [rsp+48h+arg_8]
0x180054b96  mov     ebp, eax
0x180054b98  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x180054b9d  mov     eax, [rdi]
0x180054b9f  mov     rbx, [rsp+48h+arg_8]
0x180054ba4  cmp     dword ptr [rsp+48h+arg_0], 0
0x180054ba9  mov     edx, eax
0x180054bab  mov     [rdi], eax
0x180054bad  mov     ecx, eax
0x180054baf  jz      short loc_180054BCA
0x180054bb1  test    dl, 2
0x180054bb4  jnz     short loc_180054BCA
0x180054bb6  and     ecx, 0FFFFF63Eh
0x180054bbc  mov     eax, ebx
0x180054bbe  and     eax, 9C1h
0x180054bc3  or      ecx, eax
0x180054bc5  or      ecx, 2
0x180054bc8  mov     [rdi], ecx
0x180054bca  mov     r8d, edx
0x180054bcd  and     r8d, 4
0x180054bd1  jnz     short loc_180054BE5
0x180054bd3  btr     ecx, 0Ah
0x180054bd7  mov     eax, ebx
0x180054bd9  and     eax, 400h
0x180054bde  or      ecx, eax
0x180054be0  or      ecx, 4
0x180054be3  mov     [rdi], ecx
0x180054be5  mov     eax, edx
0x180054be7  lock cmpxchg [rsi], ecx
0x180054beb  jnz     short loc_180054BA4
0x180054bed  test    r8d, r8d
0x180054bf0  jnz     short loc_180054C5C
0x180054bf2  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180054bf8  test    eax, eax
0x180054bfa  jz      short loc_180054C5C
0x180054bfc  lea     r14, SRWLock
0x180054c03  mov     rcx, r14; SRWLock
0x180054c06  call    cs:__imp_AcquireSRWLockExclusive
0x180054c0d  nop     dword ptr [rax+rax+00h]
0x180054c12  mov     eax, cs:dword_18009386C
0x180054c18  mov     [rsp+48h+arg_8], r14
0x180054c1d  test    ebp, ebp
0x180054c1f  jz      short loc_180054C4E
0x180054c21  cmp     ebp, eax
0x180054c23  jnz     short loc_180054C4E
0x180054c25  mov     r8d, 10h; SourceSize
0x180054c2b  mov     [rsp+48h+Source], 3
0x180054c34  lea     rdx, [rsp+48h+Source]; Source
0x180054c39  mov     [rsp+48h+var_20], rsi
0x180054c3e  lea     rcx, qword_1800938A0; this
0x180054c45  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180054c4a  test    al, al
0x180054c4c  jnz     short loc_180054C52
0x180054c4e  lock and dword ptr [rsi], 0FFFFFFFBh
0x180054c52  lea     rcx, [rsp+48h+arg_8]
0x180054c57  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180054c5c  mov     eax, [rdi]
0x180054c5e  test    al, 2
0x180054c60  jnz     short loc_180054C71
0x180054c62  and     eax, 0FFFFF63Eh
0x180054c67  and     ebx, 9C1h
0x180054c6d  or      eax, ebx
0x180054c6f  mov     [rdi], eax
0x180054c71  mov     rbx, [rsp+48h+arg_10]
0x180054c76  mov     rax, rdi
0x180054c79  mov     rbp, [rsp+48h+arg_18]
0x180054c7e  add     rsp, 30h
0x180054c82  pop     r14
0x180054c84  pop     rdi
0x180054c85  pop     rsi
0x180054c86  retn
```
