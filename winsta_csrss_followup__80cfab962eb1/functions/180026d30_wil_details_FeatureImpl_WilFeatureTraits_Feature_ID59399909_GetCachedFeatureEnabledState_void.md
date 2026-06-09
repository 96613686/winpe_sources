# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59399909>::GetCachedFeatureEnabledState(void)

- ea: `0x180026d30`
- end: `0x180026e6a`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59399909@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `314`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028af0`
- `0x180029398`

## callees

- `0x1800103cc`
- `0x180010d08`
- `0x180012a70`
- `0x180026d30`
- `0x180027824`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026dee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026dee`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59399909>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ID59399909__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ID59399909__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v16) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59399909>::GetCurrentFeatureEnabledState(v6, &v17, &v16);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ID59399909__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v17 = &SRWLock;
      if ( !v5
        || v5 != dword_18005A9E4
        || (Source[0] = 3,
            Source[1] = Feature_ID59399909__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18005AA18, Source, v13)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_ID59399909__descriptor, 0xFFFFFFFB);
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
0x180026d30  mov     [rsp+arg_10], rbx
0x180026d35  mov     [rsp+arg_18], rbp
0x180026d3a  mov     [rsp+arg_0], rcx
0x180026d3f  push    rsi
0x180026d40  push    rdi
0x180026d41  push    r14
0x180026d43  sub     rsp, 30h
0x180026d47  mov     rsi, cs:Feature_ID59399909__descriptor
0x180026d4e  mov     rdi, rdx
0x180026d51  mov     qword ptr [rdx], 0
0x180026d58  mov     eax, [rsi]
0x180026d5a  mov     [rdx], eax
0x180026d5c  and     eax, 6
0x180026d5f  cmp     al, 6
0x180026d61  jz      loc_180026E53
0x180026d67  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180026d6c  lea     r8, [rsp+48h+arg_0]
0x180026d71  mov     dword ptr [rsp+48h+arg_0], 0
0x180026d79  lea     rdx, [rsp+48h+arg_8]
0x180026d7e  mov     ebp, eax
0x180026d80  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59399909@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59399909>::GetCurrentFeatureEnabledState(int *)
0x180026d85  mov     eax, [rdi]
0x180026d87  mov     rbx, [rsp+48h+arg_8]
0x180026d8c  cmp     dword ptr [rsp+48h+arg_0], 0
0x180026d91  mov     edx, eax
0x180026d93  mov     [rdi], eax
0x180026d95  mov     ecx, eax
0x180026d97  jz      short loc_180026DB2
0x180026d99  test    dl, 2
0x180026d9c  jnz     short loc_180026DB2
0x180026d9e  and     ecx, 0FFFFF63Eh
0x180026da4  mov     eax, ebx
0x180026da6  and     eax, 9C1h
0x180026dab  or      ecx, eax
0x180026dad  or      ecx, 2
0x180026db0  mov     [rdi], ecx
0x180026db2  mov     r8d, edx
0x180026db5  and     r8d, 4
0x180026db9  jnz     short loc_180026DCD
0x180026dbb  btr     ecx, 0Ah
0x180026dbf  mov     eax, ebx
0x180026dc1  and     eax, 400h
0x180026dc6  or      ecx, eax
0x180026dc8  or      ecx, 4
0x180026dcb  mov     [rdi], ecx
0x180026dcd  mov     eax, edx
0x180026dcf  lock cmpxchg [rsi], ecx
0x180026dd3  jnz     short loc_180026D8C
0x180026dd5  test    r8d, r8d
0x180026dd8  jnz     short loc_180026E3E
0x180026dda  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180026de0  test    eax, eax
0x180026de2  jz      short loc_180026E3E
0x180026de4  lea     r14, SRWLock
0x180026deb  mov     rcx, r14; SRWLock
0x180026dee  call    cs:__imp_AcquireSRWLockExclusive
0x180026df5  nop     dword ptr [rax+rax+00h]
0x180026dfa  mov     eax, cs:dword_18005A9E4
0x180026e00  mov     [rsp+48h+arg_8], r14
0x180026e05  test    ebp, ebp
0x180026e07  jz      short loc_180026E30
0x180026e09  cmp     ebp, eax
0x180026e0b  jnz     short loc_180026E30
0x180026e0d  lea     rdx, [rsp+48h+Source]; Source
0x180026e12  mov     [rsp+48h+Source], 3
0x180026e1b  lea     rcx, qword_18005AA18; this
0x180026e22  mov     [rsp+48h+var_20], rsi
0x180026e27  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180026e2c  test    al, al
0x180026e2e  jnz     short loc_180026E34
0x180026e30  lock and dword ptr [rsi], 0FFFFFFFBh
0x180026e34  lea     rcx, [rsp+48h+arg_8]
0x180026e39  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180026e3e  mov     eax, [rdi]
0x180026e40  test    al, 2
0x180026e42  jnz     short loc_180026E53
0x180026e44  and     eax, 0FFFFF63Eh
0x180026e49  and     ebx, 9C1h
0x180026e4f  or      eax, ebx
0x180026e51  mov     [rdi], eax
0x180026e53  mov     rbx, [rsp+48h+arg_10]
0x180026e58  mov     rax, rdi
0x180026e5b  mov     rbp, [rsp+48h+arg_18]
0x180026e60  add     rsp, 30h
0x180026e64  pop     r14
0x180026e66  pop     rdi
0x180026e67  pop     rsi
0x180026e68  retn
```
