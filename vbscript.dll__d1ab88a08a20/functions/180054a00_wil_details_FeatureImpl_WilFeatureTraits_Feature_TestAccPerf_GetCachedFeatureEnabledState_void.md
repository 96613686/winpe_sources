# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x180054a00`
- end: `0x180054b40`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180057428`
- `0x180057e24`

## callees

- `0x180032698`
- `0x180033f2c`
- `0x18003b8cc`
- `0x180054a00`
- `0x180054fd8`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180054abe`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180054abe`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestAccPerf__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_18009386C
        || (Source[0] = 3,
            Source[1] = Feature_TestAccPerf__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800938A0, Source, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_TestAccPerf__descriptor, 0xFFFFFFFB);
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
0x180054a00  mov     [rsp+arg_10], rbx
0x180054a05  mov     [rsp+arg_18], rbp
0x180054a0a  mov     [rsp+arg_0], rcx
0x180054a0f  push    rsi
0x180054a10  push    rdi
0x180054a11  push    r14
0x180054a13  sub     rsp, 30h
0x180054a17  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x180054a1e  mov     rdi, rdx
0x180054a21  mov     qword ptr [rdx], 0
0x180054a28  mov     eax, [rsi]
0x180054a2a  mov     [rdx], eax
0x180054a2c  and     eax, 6
0x180054a2f  cmp     al, 6
0x180054a31  jz      loc_180054B29
0x180054a37  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180054a3c  lea     r8, [rsp+48h+arg_0]
0x180054a41  mov     dword ptr [rsp+48h+arg_0], 0
0x180054a49  lea     rdx, [rsp+48h+arg_8]
0x180054a4e  mov     ebp, eax
0x180054a50  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x180054a55  mov     eax, [rdi]
0x180054a57  mov     rbx, [rsp+48h+arg_8]
0x180054a5c  cmp     dword ptr [rsp+48h+arg_0], 0
0x180054a61  mov     edx, eax
0x180054a63  mov     [rdi], eax
0x180054a65  mov     ecx, eax
0x180054a67  jz      short loc_180054A82
0x180054a69  test    dl, 2
0x180054a6c  jnz     short loc_180054A82
0x180054a6e  and     ecx, 0FFFFF63Eh
0x180054a74  mov     eax, ebx
0x180054a76  and     eax, 9C1h
0x180054a7b  or      ecx, eax
0x180054a7d  or      ecx, 2
0x180054a80  mov     [rdi], ecx
0x180054a82  mov     r8d, edx
0x180054a85  and     r8d, 4
0x180054a89  jnz     short loc_180054A9D
0x180054a8b  btr     ecx, 0Ah
0x180054a8f  mov     eax, ebx
0x180054a91  and     eax, 400h
0x180054a96  or      ecx, eax
0x180054a98  or      ecx, 4
0x180054a9b  mov     [rdi], ecx
0x180054a9d  mov     eax, edx
0x180054a9f  lock cmpxchg [rsi], ecx
0x180054aa3  jnz     short loc_180054A5C
0x180054aa5  test    r8d, r8d
0x180054aa8  jnz     short loc_180054B14
0x180054aaa  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180054ab0  test    eax, eax
0x180054ab2  jz      short loc_180054B14
0x180054ab4  lea     r14, SRWLock
0x180054abb  mov     rcx, r14; SRWLock
0x180054abe  call    cs:__imp_AcquireSRWLockExclusive
0x180054ac5  nop     dword ptr [rax+rax+00h]
0x180054aca  mov     eax, cs:dword_18009386C
0x180054ad0  mov     [rsp+48h+arg_8], r14
0x180054ad5  test    ebp, ebp
0x180054ad7  jz      short loc_180054B06
0x180054ad9  cmp     ebp, eax
0x180054adb  jnz     short loc_180054B06
0x180054add  mov     r8d, 10h; SourceSize
0x180054ae3  mov     [rsp+48h+Source], 3
0x180054aec  lea     rdx, [rsp+48h+Source]; Source
0x180054af1  mov     [rsp+48h+var_20], rsi
0x180054af6  lea     rcx, qword_1800938A0; this
0x180054afd  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180054b02  test    al, al
0x180054b04  jnz     short loc_180054B0A
0x180054b06  lock and dword ptr [rsi], 0FFFFFFFBh
0x180054b0a  lea     rcx, [rsp+48h+arg_8]
0x180054b0f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180054b14  mov     eax, [rdi]
0x180054b16  test    al, 2
0x180054b18  jnz     short loc_180054B29
0x180054b1a  and     eax, 0FFFFF63Eh
0x180054b1f  and     ebx, 9C1h
0x180054b25  or      eax, ebx
0x180054b27  mov     [rdi], eax
0x180054b29  mov     rbx, [rsp+48h+arg_10]
0x180054b2e  mov     rax, rdi
0x180054b31  mov     rbp, [rsp+48h+arg_18]
0x180054b36  add     rsp, 30h
0x180054b3a  pop     r14
0x180054b3c  pop     rdi
0x180054b3d  pop     rsi
0x180054b3e  retn
```
