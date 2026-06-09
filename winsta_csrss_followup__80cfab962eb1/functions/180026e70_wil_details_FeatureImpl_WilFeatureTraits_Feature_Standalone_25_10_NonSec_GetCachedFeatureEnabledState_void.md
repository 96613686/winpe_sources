# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180026e70`
- end: `0x180026faa`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028b80`

## callees

- `0x1800103cc`
- `0x180010d08`
- `0x180012a70`
- `0x180026e70`
- `0x1800278ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026f2e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026f2e`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v16) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(
      v6,
      &v17,
      &v16);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v17 = &SRWLock;
      if ( !v5
        || v5 != dword_18005A9E4
        || (Source[0] = 3,
            Source[1] = Feature_Standalone_25_10_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18005AA18, Source, v13)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor, 0xFFFFFFFB);
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
0x180026e70  mov     [rsp+arg_10], rbx
0x180026e75  mov     [rsp+arg_18], rbp
0x180026e7a  mov     [rsp+arg_0], rcx
0x180026e7f  push    rsi
0x180026e80  push    rdi
0x180026e81  push    r14
0x180026e83  sub     rsp, 30h
0x180026e87  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x180026e8e  mov     rdi, rdx
0x180026e91  mov     qword ptr [rdx], 0
0x180026e98  mov     eax, [rsi]
0x180026e9a  mov     [rdx], eax
0x180026e9c  and     eax, 6
0x180026e9f  cmp     al, 6
0x180026ea1  jz      loc_180026F93
0x180026ea7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180026eac  lea     r8, [rsp+48h+arg_0]
0x180026eb1  mov     dword ptr [rsp+48h+arg_0], 0
0x180026eb9  lea     rdx, [rsp+48h+arg_8]
0x180026ebe  mov     ebp, eax
0x180026ec0  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(int *)
0x180026ec5  mov     eax, [rdi]
0x180026ec7  mov     rbx, [rsp+48h+arg_8]
0x180026ecc  cmp     dword ptr [rsp+48h+arg_0], 0
0x180026ed1  mov     edx, eax
0x180026ed3  mov     [rdi], eax
0x180026ed5  mov     ecx, eax
0x180026ed7  jz      short loc_180026EF2
0x180026ed9  test    dl, 2
0x180026edc  jnz     short loc_180026EF2
0x180026ede  and     ecx, 0FFFFF63Eh
0x180026ee4  mov     eax, ebx
0x180026ee6  and     eax, 9C1h
0x180026eeb  or      ecx, eax
0x180026eed  or      ecx, 2
0x180026ef0  mov     [rdi], ecx
0x180026ef2  mov     r8d, edx
0x180026ef5  and     r8d, 4
0x180026ef9  jnz     short loc_180026F0D
0x180026efb  btr     ecx, 0Ah
0x180026eff  mov     eax, ebx
0x180026f01  and     eax, 400h
0x180026f06  or      ecx, eax
0x180026f08  or      ecx, 4
0x180026f0b  mov     [rdi], ecx
0x180026f0d  mov     eax, edx
0x180026f0f  lock cmpxchg [rsi], ecx
0x180026f13  jnz     short loc_180026ECC
0x180026f15  test    r8d, r8d
0x180026f18  jnz     short loc_180026F7E
0x180026f1a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180026f20  test    eax, eax
0x180026f22  jz      short loc_180026F7E
0x180026f24  lea     r14, SRWLock
0x180026f2b  mov     rcx, r14; SRWLock
0x180026f2e  call    cs:__imp_AcquireSRWLockExclusive
0x180026f35  nop     dword ptr [rax+rax+00h]
0x180026f3a  mov     eax, cs:dword_18005A9E4
0x180026f40  mov     [rsp+48h+arg_8], r14
0x180026f45  test    ebp, ebp
0x180026f47  jz      short loc_180026F70
0x180026f49  cmp     ebp, eax
0x180026f4b  jnz     short loc_180026F70
0x180026f4d  lea     rdx, [rsp+48h+Source]; Source
0x180026f52  mov     [rsp+48h+Source], 3
0x180026f5b  lea     rcx, qword_18005AA18; this
0x180026f62  mov     [rsp+48h+var_20], rsi
0x180026f67  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180026f6c  test    al, al
0x180026f6e  jnz     short loc_180026F74
0x180026f70  lock and dword ptr [rsi], 0FFFFFFFBh
0x180026f74  lea     rcx, [rsp+48h+arg_8]
0x180026f79  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180026f7e  mov     eax, [rdi]
0x180026f80  test    al, 2
0x180026f82  jnz     short loc_180026F93
0x180026f84  and     eax, 0FFFFF63Eh
0x180026f89  and     ebx, 9C1h
0x180026f8f  or      eax, ebx
0x180026f91  mov     [rdi], eax
0x180026f93  mov     rbx, [rsp+48h+arg_10]
0x180026f98  mov     rax, rdi
0x180026f9b  mov     rbp, [rsp+48h+arg_18]
0x180026fa0  add     rsp, 30h
0x180026fa4  pop     r14
0x180026fa6  pop     rdi
0x180026fa7  pop     rsi
0x180026fa8  retn
```
