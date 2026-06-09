# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x1800257f0`
- end: `0x180025923`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027278`

## callees

- `0x18000f89c`
- `0x180010104`
- `0x1800121f4`
- `0x1800257f0`
- `0x1800260a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800258ae`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800258ae`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v16) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(v6, &v17, &v16);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValLabTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v17 = &SRWLock;
      if ( !v5
        || v5 != dword_1800579AC
        || (Source[0] = 3,
            Source[1] = Feature_ValLabTest__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800579D0, Source, v13)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_ValLabTest__descriptor, 0xFFFFFFFB);
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
0x1800257f0  mov     [rsp+arg_10], rbx
0x1800257f5  mov     [rsp+arg_18], rbp
0x1800257fa  mov     [rsp+arg_0], rcx
0x1800257ff  push    rsi
0x180025800  push    rdi
0x180025801  push    r14
0x180025803  sub     rsp, 30h
0x180025807  mov     rsi, cs:Feature_ValLabTest__descriptor
0x18002580e  mov     rdi, rdx
0x180025811  mov     qword ptr [rdx], 0
0x180025818  mov     eax, [rsi]
0x18002581a  mov     [rdx], eax
0x18002581c  and     eax, 6
0x18002581f  cmp     al, 6
0x180025821  jz      loc_18002590D
0x180025827  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002582c  lea     r8, [rsp+48h+arg_0]
0x180025831  mov     dword ptr [rsp+48h+arg_0], 0
0x180025839  lea     rdx, [rsp+48h+arg_8]
0x18002583e  mov     ebp, eax
0x180025840  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(int *)
0x180025845  mov     eax, [rdi]
0x180025847  mov     rbx, [rsp+48h+arg_8]
0x18002584c  cmp     dword ptr [rsp+48h+arg_0], 0
0x180025851  mov     edx, eax
0x180025853  mov     [rdi], eax
0x180025855  mov     ecx, eax
0x180025857  jz      short loc_180025872
0x180025859  test    dl, 2
0x18002585c  jnz     short loc_180025872
0x18002585e  and     ecx, 0FFFFF63Eh
0x180025864  mov     eax, ebx
0x180025866  and     eax, 9C1h
0x18002586b  or      ecx, eax
0x18002586d  or      ecx, 2
0x180025870  mov     [rdi], ecx
0x180025872  mov     r8d, edx
0x180025875  and     r8d, 4
0x180025879  jnz     short loc_18002588D
0x18002587b  btr     ecx, 0Ah
0x18002587f  mov     eax, ebx
0x180025881  and     eax, 400h
0x180025886  or      ecx, eax
0x180025888  or      ecx, 4
0x18002588b  mov     [rdi], ecx
0x18002588d  mov     eax, edx
0x18002588f  lock cmpxchg [rsi], ecx
0x180025893  jnz     short loc_18002584C
0x180025895  test    r8d, r8d
0x180025898  jnz     short loc_1800258F8
0x18002589a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800258a0  test    eax, eax
0x1800258a2  jz      short loc_1800258F8
0x1800258a4  lea     r14, SRWLock
0x1800258ab  mov     rcx, r14; SRWLock
0x1800258ae  call    cs:__imp_AcquireSRWLockExclusive
0x1800258b4  mov     eax, cs:dword_1800579AC
0x1800258ba  mov     [rsp+48h+arg_8], r14
0x1800258bf  test    ebp, ebp
0x1800258c1  jz      short loc_1800258EA
0x1800258c3  cmp     ebp, eax
0x1800258c5  jnz     short loc_1800258EA
0x1800258c7  lea     rdx, [rsp+48h+Source]; Source
0x1800258cc  mov     [rsp+48h+Source], 3
0x1800258d5  lea     rcx, qword_1800579D0; this
0x1800258dc  mov     [rsp+48h+var_20], rsi
0x1800258e1  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800258e6  test    al, al
0x1800258e8  jnz     short loc_1800258EE
0x1800258ea  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800258ee  lea     rcx, [rsp+48h+arg_8]
0x1800258f3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800258f8  mov     eax, [rdi]
0x1800258fa  test    al, 2
0x1800258fc  jnz     short loc_18002590D
0x1800258fe  and     eax, 0FFFFF63Eh
0x180025903  and     ebx, 9C1h
0x180025909  or      eax, ebx
0x18002590b  mov     [rdi], eax
0x18002590d  mov     rbx, [rsp+48h+arg_10]
0x180025912  mov     rax, rdi
0x180025915  mov     rbp, [rsp+48h+arg_18]
0x18002591a  add     rsp, 30h
0x18002591e  pop     r14
0x180025920  pop     rdi
0x180025921  pop     rsi
0x180025922  retn
```
