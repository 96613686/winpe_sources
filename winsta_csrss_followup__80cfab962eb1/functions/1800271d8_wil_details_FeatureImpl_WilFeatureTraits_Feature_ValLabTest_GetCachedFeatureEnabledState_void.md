# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x1800271d8`
- end: `0x180027312`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028d14`

## callees

- `0x1800103cc`
- `0x180010d08`
- `0x180012a70`
- `0x1800271d8`
- `0x180027ab4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027296`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027296`

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
        || v5 != dword_18005A9E4
        || (Source[0] = 3,
            Source[1] = Feature_ValLabTest__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18005AA18, Source, v13)) )
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
0x1800271d8  mov     [rsp+arg_10], rbx
0x1800271dd  mov     [rsp+arg_18], rbp
0x1800271e2  mov     [rsp+arg_0], rcx
0x1800271e7  push    rsi
0x1800271e8  push    rdi
0x1800271e9  push    r14
0x1800271eb  sub     rsp, 30h
0x1800271ef  mov     rsi, cs:Feature_ValLabTest__descriptor
0x1800271f6  mov     rdi, rdx
0x1800271f9  mov     qword ptr [rdx], 0
0x180027200  mov     eax, [rsi]
0x180027202  mov     [rdx], eax
0x180027204  and     eax, 6
0x180027207  cmp     al, 6
0x180027209  jz      loc_1800272FB
0x18002720f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180027214  lea     r8, [rsp+48h+arg_0]
0x180027219  mov     dword ptr [rsp+48h+arg_0], 0
0x180027221  lea     rdx, [rsp+48h+arg_8]
0x180027226  mov     ebp, eax
0x180027228  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(int *)
0x18002722d  mov     eax, [rdi]
0x18002722f  mov     rbx, [rsp+48h+arg_8]
0x180027234  cmp     dword ptr [rsp+48h+arg_0], 0
0x180027239  mov     edx, eax
0x18002723b  mov     [rdi], eax
0x18002723d  mov     ecx, eax
0x18002723f  jz      short loc_18002725A
0x180027241  test    dl, 2
0x180027244  jnz     short loc_18002725A
0x180027246  and     ecx, 0FFFFF63Eh
0x18002724c  mov     eax, ebx
0x18002724e  and     eax, 9C1h
0x180027253  or      ecx, eax
0x180027255  or      ecx, 2
0x180027258  mov     [rdi], ecx
0x18002725a  mov     r8d, edx
0x18002725d  and     r8d, 4
0x180027261  jnz     short loc_180027275
0x180027263  btr     ecx, 0Ah
0x180027267  mov     eax, ebx
0x180027269  and     eax, 400h
0x18002726e  or      ecx, eax
0x180027270  or      ecx, 4
0x180027273  mov     [rdi], ecx
0x180027275  mov     eax, edx
0x180027277  lock cmpxchg [rsi], ecx
0x18002727b  jnz     short loc_180027234
0x18002727d  test    r8d, r8d
0x180027280  jnz     short loc_1800272E6
0x180027282  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180027288  test    eax, eax
0x18002728a  jz      short loc_1800272E6
0x18002728c  lea     r14, SRWLock
0x180027293  mov     rcx, r14; SRWLock
0x180027296  call    cs:__imp_AcquireSRWLockExclusive
0x18002729d  nop     dword ptr [rax+rax+00h]
0x1800272a2  mov     eax, cs:dword_18005A9E4
0x1800272a8  mov     [rsp+48h+arg_8], r14
0x1800272ad  test    ebp, ebp
0x1800272af  jz      short loc_1800272D8
0x1800272b1  cmp     ebp, eax
0x1800272b3  jnz     short loc_1800272D8
0x1800272b5  lea     rdx, [rsp+48h+Source]; Source
0x1800272ba  mov     [rsp+48h+Source], 3
0x1800272c3  lea     rcx, qword_18005AA18; this
0x1800272ca  mov     [rsp+48h+var_20], rsi
0x1800272cf  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800272d4  test    al, al
0x1800272d6  jnz     short loc_1800272DC
0x1800272d8  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800272dc  lea     rcx, [rsp+48h+arg_8]
0x1800272e1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800272e6  mov     eax, [rdi]
0x1800272e8  test    al, 2
0x1800272ea  jnz     short loc_1800272FB
0x1800272ec  and     eax, 0FFFFF63Eh
0x1800272f1  and     ebx, 9C1h
0x1800272f7  or      eax, ebx
0x1800272f9  mov     [rdi], eax
0x1800272fb  mov     rbx, [rsp+48h+arg_10]
0x180027300  mov     rax, rdi
0x180027303  mov     rbp, [rsp+48h+arg_18]
0x180027308  add     rsp, 30h
0x18002730c  pop     r14
0x18002730e  pop     rdi
0x18002730f  pop     rsi
0x180027310  retn
```
