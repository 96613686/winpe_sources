# wil::details::FeatureImpl<__WilFeatureTraits_Feature_AMPPLValidationInWsc>::GetCachedVariantState(void)

- ea: `0x1800316c8`
- end: `0x18003182a`
- name: `?GetCachedVariantState@?$FeatureImpl@U__WilFeatureTraits_Feature_AMPPLValidationInWsc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `354`
- prototype: `__int64 *__fastcall(wil::details *, signed __int64 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180031af4`
- `0x1800326a8`

## callees

- `0x180022240`
- `0x180027404`
- `0x180028b1c`
- `0x1800316c8`
- `0x18003192c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800317c9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800317c9`

## pseudocode

```c
__int64 *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_AMPPLValidationInWsc>::GetCachedVariantState(
        wil::details *a1,
        signed __int64 *a2)
{
  __int64 v3; // rax
  unsigned int v4; // esi
  __int64 v5; // rcx
  __int64 v6; // r9
  int v7; // ecx
  signed __int64 v8; // rax
  int v9; // r11d
  signed __int64 v10; // r10
  int v11; // r8d
  bool v12; // zf
  _QWORD Source[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details *v15; // [rsp+50h] [rbp+20h] BYREF
  RTL_SRWLOCK *v16; // [rsp+58h] [rbp+28h] BYREF

  v15 = a1;
  v3 = *Feature_AMPPLValidationInWsc__descriptor;
  *a2 = *Feature_AMPPLValidationInWsc__descriptor;
  if ( (v3 & 0xC) != 0xC )
  {
    LODWORD(v15) = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AMPPLValidationInWsc>::GetCurrentVariantState(v5, &v16, &v15);
    v6 = *a2;
    v7 = (int)v16;
    v8 = *a2;
    v9 = HIDWORD(v16);
    v10 = *a2;
    while ( 1 )
    {
      *(_DWORD *)a2 = v6;
      *((_DWORD *)a2 + 1) = HIDWORD(v8);
      if ( (v6 & 8) != 0 )
      {
        v11 = v6;
      }
      else
      {
        *((_DWORD *)a2 + 1) = v9;
        v11 = v7 & 0x800 | ((_DWORD)v15 != 0 ? 8 : 0) | v6 & 0xFFFC07F7 | v7 & 0x3F000;
        *(_DWORD *)a2 = v11;
      }
      if ( (v6 & 4) == 0 )
        *(_DWORD *)a2 = v7 & 0x400 | v11 & 0xFFFFFBFF | 4;
      v8 = _InterlockedCompareExchange64(Feature_AMPPLValidationInWsc__descriptor, *a2, v10);
      v12 = v10 == v8;
      v10 = v8;
      if ( v12 )
        break;
      LODWORD(v6) = v8;
    }
    if ( (v6 & 4) == 0 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v4
        || v4 != dword_1800544EC
        || (Source[0] = 3,
            Source[1] = Feature_AMPPLValidationInWsc__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180054510, Source, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_AMPPLValidationInWsc__descriptor, 0xFFFFFFFB);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1800316c8  mov     [rsp-18h+arg_10], rbx
0x1800316cd  mov     [rsp-18h+arg_18], rsi
0x1800316d2  mov     [rsp-18h+arg_0], rcx
0x1800316d7  push    rbp
0x1800316d8  push    rdi
0x1800316d9  push    r14
0x1800316db  mov     rbp, rsp
0x1800316de  sub     rsp, 30h
0x1800316e2  mov     rbx, cs:Feature_AMPPLValidationInWsc__descriptor
0x1800316e9  mov     rdi, rdx
0x1800316ec  mov     rax, [rbx]
0x1800316ef  mov     [rdx], rax
0x1800316f2  and     eax, 0Ch
0x1800316f5  cmp     al, 0Ch
0x1800316f7  jz      loc_180031814
0x1800316fd  mov     dword ptr [rbp+arg_0], 0
0x180031704  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180031709  lea     r8, [rbp+arg_0]
0x18003170d  mov     esi, eax
0x18003170f  lea     rdx, [rbp+arg_8]
0x180031713  call    ?GetCurrentVariantState@?$FeatureImpl@U__WilFeatureTraits_Feature_AMPPLValidationInWsc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AMPPLValidationInWsc>::GetCurrentVariantState(int *)
0x180031718  mov     r9, [rdi]
0x18003171b  mov     rcx, [rbp+arg_8]
0x18003171f  mov     rax, r9
0x180031722  mov     r11d, dword ptr [rbp+arg_8+4]
0x180031726  mov     r10, r9
0x180031729  shr     rax, 20h
0x18003172d  mov     [rdi], r9d
0x180031730  mov     [rdi+4], eax
0x180031733  test    r9b, 8
0x180031737  jnz     short loc_180031777
0x180031739  mov     r8d, ecx
0x18003173c  mov     [rdi+4], r11d
0x180031740  and     r8d, 3F000h
0x180031747  mov     eax, r9d
0x18003174a  and     eax, 0FFFC0FFFh
0x18003174f  or      r8d, eax
0x180031752  mov     eax, dword ptr [rbp+arg_0]
0x180031755  neg     eax
0x180031757  mov     eax, ecx
0x180031759  sbb     edx, edx
0x18003175b  and     r8d, 0FFFFFFF7h
0x18003175f  and     edx, 8
0x180031762  and     eax, 800h
0x180031767  or      r8d, edx
0x18003176a  btr     r8d, 0Bh
0x18003176f  or      r8d, eax
0x180031772  mov     [rdi], r8d
0x180031775  jmp     short loc_18003177A
0x180031777  mov     r8d, r9d
0x18003177a  test    r9b, 4
0x18003177e  jnz     short loc_180031797
0x180031780  btr     r8d, 0Ah
0x180031785  mov     edx, ecx
0x180031787  and     edx, 400h
0x18003178d  or      r8d, edx
0x180031790  or      r8d, 4
0x180031794  mov     [rdi], r8d
0x180031797  mov     rdx, [rdi]
0x18003179a  mov     rax, r10
0x18003179d  lock cmpxchg [rbx], rdx
0x1800317a2  mov     r10, rax
0x1800317a5  jz      short loc_1800317AF
0x1800317a7  mov     r9d, eax
0x1800317aa  jmp     loc_180031729
0x1800317af  test    r9b, 4
0x1800317b3  jnz     short loc_180031814
0x1800317b5  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800317bb  test    eax, eax
0x1800317bd  jz      short loc_180031814
0x1800317bf  lea     r14, SRWLock
0x1800317c6  mov     rcx, r14; SRWLock
0x1800317c9  call    cs:__imp_AcquireSRWLockExclusive
0x1800317cf  mov     eax, cs:dword_1800544EC
0x1800317d5  mov     [rbp+arg_8], r14
0x1800317d9  test    esi, esi
0x1800317db  jz      short loc_180031807
0x1800317dd  cmp     esi, eax
0x1800317df  jnz     short loc_180031807
0x1800317e1  mov     r8d, 10h; SourceSize
0x1800317e7  mov     [rbp+Source], 3
0x1800317ef  lea     rdx, [rbp+Source]; Source
0x1800317f3  mov     [rbp+var_8], rbx
0x1800317f7  lea     rcx, qword_180054510; this
0x1800317fe  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180031803  test    al, al
0x180031805  jnz     short loc_18003180B
0x180031807  lock and dword ptr [rbx], 0FFFFFFFBh
0x18003180b  lea     rcx, [rbp+arg_8]
0x18003180f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180031814  mov     rbx, [rsp+30h+arg_10]
0x180031819  mov     rax, rdi
0x18003181c  mov     rsi, [rsp+30h+arg_18]
0x180031821  add     rsp, 30h
0x180031825  pop     r14
0x180031827  pop     rdi
0x180031828  pop     rbp
0x180031829  retn
```
