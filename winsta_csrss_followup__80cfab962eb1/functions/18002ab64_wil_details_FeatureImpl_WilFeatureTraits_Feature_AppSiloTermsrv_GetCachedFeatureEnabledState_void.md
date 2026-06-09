# wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloTermsrv>::GetCachedFeatureEnabledState(void)

- ea: `0x18002ab64`
- end: `0x18002ac9e`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloTermsrv@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `314`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002af18`
- `0x18002b034`

## callees

- `0x1800103cc`
- `0x180010d08`
- `0x180012a70`
- `0x18002ab64`
- `0x18002ad8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ac22`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ac22`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloTermsrv>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_AppSiloTermsrv__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_AppSiloTermsrv__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v16) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloTermsrv>::GetCurrentFeatureEnabledState(v6, &v17, &v16);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_AppSiloTermsrv__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v17 = &SRWLock;
      if ( !v5
        || v5 != dword_18005A9E4
        || (Source[0] = 3,
            Source[1] = Feature_AppSiloTermsrv__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18005AA18, Source, v13)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_AppSiloTermsrv__descriptor, 0xFFFFFFFB);
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
0x18002ab64  mov     [rsp+arg_10], rbx
0x18002ab69  mov     [rsp+arg_18], rbp
0x18002ab6e  mov     [rsp+arg_0], rcx
0x18002ab73  push    rsi
0x18002ab74  push    rdi
0x18002ab75  push    r14
0x18002ab77  sub     rsp, 30h
0x18002ab7b  mov     rsi, cs:Feature_AppSiloTermsrv__descriptor
0x18002ab82  mov     rdi, rdx
0x18002ab85  mov     qword ptr [rdx], 0
0x18002ab8c  mov     eax, [rsi]
0x18002ab8e  mov     [rdx], eax
0x18002ab90  and     eax, 6
0x18002ab93  cmp     al, 6
0x18002ab95  jz      loc_18002AC87
0x18002ab9b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002aba0  lea     r8, [rsp+48h+arg_0]
0x18002aba5  mov     dword ptr [rsp+48h+arg_0], 0
0x18002abad  lea     rdx, [rsp+48h+arg_8]
0x18002abb2  mov     ebp, eax
0x18002abb4  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloTermsrv@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloTermsrv>::GetCurrentFeatureEnabledState(int *)
0x18002abb9  mov     eax, [rdi]
0x18002abbb  mov     rbx, [rsp+48h+arg_8]
0x18002abc0  cmp     dword ptr [rsp+48h+arg_0], 0
0x18002abc5  mov     edx, eax
0x18002abc7  mov     [rdi], eax
0x18002abc9  mov     ecx, eax
0x18002abcb  jz      short loc_18002ABE6
0x18002abcd  test    dl, 2
0x18002abd0  jnz     short loc_18002ABE6
0x18002abd2  and     ecx, 0FFFFF63Eh
0x18002abd8  mov     eax, ebx
0x18002abda  and     eax, 9C1h
0x18002abdf  or      ecx, eax
0x18002abe1  or      ecx, 2
0x18002abe4  mov     [rdi], ecx
0x18002abe6  mov     r8d, edx
0x18002abe9  and     r8d, 4
0x18002abed  jnz     short loc_18002AC01
0x18002abef  btr     ecx, 0Ah
0x18002abf3  mov     eax, ebx
0x18002abf5  and     eax, 400h
0x18002abfa  or      ecx, eax
0x18002abfc  or      ecx, 4
0x18002abff  mov     [rdi], ecx
0x18002ac01  mov     eax, edx
0x18002ac03  lock cmpxchg [rsi], ecx
0x18002ac07  jnz     short loc_18002ABC0
0x18002ac09  test    r8d, r8d
0x18002ac0c  jnz     short loc_18002AC72
0x18002ac0e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18002ac14  test    eax, eax
0x18002ac16  jz      short loc_18002AC72
0x18002ac18  lea     r14, SRWLock
0x18002ac1f  mov     rcx, r14; SRWLock
0x18002ac22  call    cs:__imp_AcquireSRWLockExclusive
0x18002ac29  nop     dword ptr [rax+rax+00h]
0x18002ac2e  mov     eax, cs:dword_18005A9E4
0x18002ac34  mov     [rsp+48h+arg_8], r14
0x18002ac39  test    ebp, ebp
0x18002ac3b  jz      short loc_18002AC64
0x18002ac3d  cmp     ebp, eax
0x18002ac3f  jnz     short loc_18002AC64
0x18002ac41  lea     rdx, [rsp+48h+Source]; Source
0x18002ac46  mov     [rsp+48h+Source], 3
0x18002ac4f  lea     rcx, qword_18005AA18; this
0x18002ac56  mov     [rsp+48h+var_20], rsi
0x18002ac5b  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18002ac60  test    al, al
0x18002ac62  jnz     short loc_18002AC68
0x18002ac64  lock and dword ptr [rsi], 0FFFFFFFBh
0x18002ac68  lea     rcx, [rsp+48h+arg_8]
0x18002ac6d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002ac72  mov     eax, [rdi]
0x18002ac74  test    al, 2
0x18002ac76  jnz     short loc_18002AC87
0x18002ac78  and     eax, 0FFFFF63Eh
0x18002ac7d  and     ebx, 9C1h
0x18002ac83  or      eax, ebx
0x18002ac85  mov     [rdi], eax
0x18002ac87  mov     rbx, [rsp+48h+arg_10]
0x18002ac8c  mov     rax, rdi
0x18002ac8f  mov     rbp, [rsp+48h+arg_18]
0x18002ac94  add     rsp, 30h
0x18002ac98  pop     r14
0x18002ac9a  pop     rdi
0x18002ac9b  pop     rsi
0x18002ac9c  retn
```
