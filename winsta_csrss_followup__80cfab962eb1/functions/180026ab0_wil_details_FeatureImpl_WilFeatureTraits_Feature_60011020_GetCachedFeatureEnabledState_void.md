# wil::details::FeatureImpl<__WilFeatureTraits_Feature_60011020>::GetCachedFeatureEnabledState(void)

- ea: `0x180026ab0`
- end: `0x180026bea`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_60011020@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800289d0`

## callees

- `0x1800103cc`
- `0x180010d08`
- `0x180012a70`
- `0x180026ab0`
- `0x1800276d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026b6e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026b6e`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_60011020>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_60011020__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_60011020__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v16) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_60011020>::GetCurrentFeatureEnabledState(v6, &v17, &v16);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_60011020__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v17 = &SRWLock;
      if ( !v5
        || v5 != dword_18005A9E4
        || (Source[0] = 3,
            Source[1] = Feature_60011020__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18005AA18, Source, v13)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_60011020__descriptor, 0xFFFFFFFB);
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
0x180026ab0  mov     [rsp+arg_10], rbx
0x180026ab5  mov     [rsp+arg_18], rbp
0x180026aba  mov     [rsp+arg_0], rcx
0x180026abf  push    rsi
0x180026ac0  push    rdi
0x180026ac1  push    r14
0x180026ac3  sub     rsp, 30h
0x180026ac7  mov     rsi, cs:Feature_60011020__descriptor
0x180026ace  mov     rdi, rdx
0x180026ad1  mov     qword ptr [rdx], 0
0x180026ad8  mov     eax, [rsi]
0x180026ada  mov     [rdx], eax
0x180026adc  and     eax, 6
0x180026adf  cmp     al, 6
0x180026ae1  jz      loc_180026BD3
0x180026ae7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180026aec  lea     r8, [rsp+48h+arg_0]
0x180026af1  mov     dword ptr [rsp+48h+arg_0], 0
0x180026af9  lea     rdx, [rsp+48h+arg_8]
0x180026afe  mov     ebp, eax
0x180026b00  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_60011020@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60011020>::GetCurrentFeatureEnabledState(int *)
0x180026b05  mov     eax, [rdi]
0x180026b07  mov     rbx, [rsp+48h+arg_8]
0x180026b0c  cmp     dword ptr [rsp+48h+arg_0], 0
0x180026b11  mov     edx, eax
0x180026b13  mov     [rdi], eax
0x180026b15  mov     ecx, eax
0x180026b17  jz      short loc_180026B32
0x180026b19  test    dl, 2
0x180026b1c  jnz     short loc_180026B32
0x180026b1e  and     ecx, 0FFFFF63Eh
0x180026b24  mov     eax, ebx
0x180026b26  and     eax, 9C1h
0x180026b2b  or      ecx, eax
0x180026b2d  or      ecx, 2
0x180026b30  mov     [rdi], ecx
0x180026b32  mov     r8d, edx
0x180026b35  and     r8d, 4
0x180026b39  jnz     short loc_180026B4D
0x180026b3b  btr     ecx, 0Ah
0x180026b3f  mov     eax, ebx
0x180026b41  and     eax, 400h
0x180026b46  or      ecx, eax
0x180026b48  or      ecx, 4
0x180026b4b  mov     [rdi], ecx
0x180026b4d  mov     eax, edx
0x180026b4f  lock cmpxchg [rsi], ecx
0x180026b53  jnz     short loc_180026B0C
0x180026b55  test    r8d, r8d
0x180026b58  jnz     short loc_180026BBE
0x180026b5a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180026b60  test    eax, eax
0x180026b62  jz      short loc_180026BBE
0x180026b64  lea     r14, SRWLock
0x180026b6b  mov     rcx, r14; SRWLock
0x180026b6e  call    cs:__imp_AcquireSRWLockExclusive
0x180026b75  nop     dword ptr [rax+rax+00h]
0x180026b7a  mov     eax, cs:dword_18005A9E4
0x180026b80  mov     [rsp+48h+arg_8], r14
0x180026b85  test    ebp, ebp
0x180026b87  jz      short loc_180026BB0
0x180026b89  cmp     ebp, eax
0x180026b8b  jnz     short loc_180026BB0
0x180026b8d  lea     rdx, [rsp+48h+Source]; Source
0x180026b92  mov     [rsp+48h+Source], 3
0x180026b9b  lea     rcx, qword_18005AA18; this
0x180026ba2  mov     [rsp+48h+var_20], rsi
0x180026ba7  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180026bac  test    al, al
0x180026bae  jnz     short loc_180026BB4
0x180026bb0  lock and dword ptr [rsi], 0FFFFFFFBh
0x180026bb4  lea     rcx, [rsp+48h+arg_8]
0x180026bb9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180026bbe  mov     eax, [rdi]
0x180026bc0  test    al, 2
0x180026bc2  jnz     short loc_180026BD3
0x180026bc4  and     eax, 0FFFFF63Eh
0x180026bc9  and     ebx, 9C1h
0x180026bcf  or      eax, ebx
0x180026bd1  mov     [rdi], eax
0x180026bd3  mov     rbx, [rsp+48h+arg_10]
0x180026bd8  mov     rax, rdi
0x180026bdb  mov     rbp, [rsp+48h+arg_18]
0x180026be0  add     rsp, 30h
0x180026be4  pop     r14
0x180026be6  pop     rdi
0x180026be7  pop     rsi
0x180026be8  retn
```
