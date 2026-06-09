# wil::details::FeatureImpl<__WilFeatureTraits_Feature_58788260>::GetCachedFeatureEnabledState(void)

- ea: `0x18002cf1c`
- end: `0x18002d055`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_58788260@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002df00`
- `0x18002e0ac`

## callees

- `0x18001f5f0`
- `0x180029c18`
- `0x18002c34c`
- `0x18002cf1c`
- `0x18002d0d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002cfda`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002cfda`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_58788260>::GetCachedFeatureEnabledState(
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
  _QWORD v14[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details *v15; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v16; // [rsp+58h] [rbp+10h] BYREF

  v15 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_58788260__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_58788260__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_58788260>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_58788260__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_180044A54
        || (v14[0] = 3,
            v14[1] = Feature_58788260__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180044A78, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_58788260__descriptor, 0xFFFFFFFB);
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
0x18002cf1c  mov     [rsp+arg_10], rbx
0x18002cf21  mov     [rsp+arg_18], rbp
0x18002cf26  mov     [rsp+arg_0], rcx
0x18002cf2b  push    rsi
0x18002cf2c  push    rdi
0x18002cf2d  push    r14
0x18002cf2f  sub     rsp, 30h
0x18002cf33  mov     rsi, cs:Feature_58788260__descriptor
0x18002cf3a  mov     rdi, rdx
0x18002cf3d  mov     qword ptr [rdx], 0
0x18002cf44  mov     eax, [rsi]
0x18002cf46  mov     [rdx], eax
0x18002cf48  and     eax, 6
0x18002cf4b  cmp     al, 6
0x18002cf4d  jz      loc_18002D03F
0x18002cf53  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002cf58  lea     r8, [rsp+48h+arg_0]
0x18002cf5d  mov     dword ptr [rsp+48h+arg_0], 0
0x18002cf65  lea     rdx, [rsp+48h+arg_8]
0x18002cf6a  mov     ebp, eax
0x18002cf6c  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_58788260@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58788260>::GetCurrentFeatureEnabledState(int *)
0x18002cf71  mov     eax, [rdi]
0x18002cf73  mov     rbx, [rsp+48h+arg_8]
0x18002cf78  cmp     dword ptr [rsp+48h+arg_0], 0
0x18002cf7d  mov     edx, eax
0x18002cf7f  mov     [rdi], eax
0x18002cf81  mov     ecx, eax
0x18002cf83  jz      short loc_18002CF9E
0x18002cf85  test    dl, 2
0x18002cf88  jnz     short loc_18002CF9E
0x18002cf8a  and     ecx, 0FFFFF63Eh
0x18002cf90  mov     eax, ebx
0x18002cf92  and     eax, 9C1h
0x18002cf97  or      ecx, eax
0x18002cf99  or      ecx, 2
0x18002cf9c  mov     [rdi], ecx
0x18002cf9e  mov     r8d, edx
0x18002cfa1  and     r8d, 4
0x18002cfa5  jnz     short loc_18002CFB9
0x18002cfa7  btr     ecx, 0Ah
0x18002cfab  mov     eax, ebx
0x18002cfad  and     eax, 400h
0x18002cfb2  or      ecx, eax
0x18002cfb4  or      ecx, 4
0x18002cfb7  mov     [rdi], ecx
0x18002cfb9  mov     eax, edx
0x18002cfbb  lock cmpxchg [rsi], ecx
0x18002cfbf  jnz     short loc_18002CF78
0x18002cfc1  test    r8d, r8d
0x18002cfc4  jnz     short loc_18002D02A
0x18002cfc6  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18002cfcc  test    eax, eax
0x18002cfce  jz      short loc_18002D02A
0x18002cfd0  lea     r14, SRWLock
0x18002cfd7  mov     rcx, r14; SRWLock
0x18002cfda  call    cs:__imp_AcquireSRWLockExclusive
0x18002cfe0  mov     eax, cs:dword_180044A54
0x18002cfe6  mov     [rsp+48h+arg_8], r14
0x18002cfeb  test    ebp, ebp
0x18002cfed  jz      short loc_18002D01C
0x18002cfef  cmp     ebp, eax
0x18002cff1  jnz     short loc_18002D01C
0x18002cff3  mov     r8d, 10h; unsigned __int64
0x18002cff9  mov     [rsp+48h+var_28], 3
0x18002d002  lea     rdx, [rsp+48h+var_28]; void *
0x18002d007  mov     [rsp+48h+var_20], rsi
0x18002d00c  lea     rcx, qword_180044A78; this
0x18002d013  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18002d018  test    al, al
0x18002d01a  jnz     short loc_18002D020
0x18002d01c  lock and dword ptr [rsi], 0FFFFFFFBh
0x18002d020  lea     rcx, [rsp+48h+arg_8]
0x18002d025  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002d02a  mov     eax, [rdi]
0x18002d02c  test    al, 2
0x18002d02e  jnz     short loc_18002D03F
0x18002d030  and     eax, 0FFFFF63Eh
0x18002d035  and     ebx, 9C1h
0x18002d03b  or      eax, ebx
0x18002d03d  mov     [rdi], eax
0x18002d03f  mov     rbx, [rsp+48h+arg_10]
0x18002d044  mov     rax, rdi
0x18002d047  mov     rbp, [rsp+48h+arg_18]
0x18002d04c  add     rsp, 30h
0x18002d050  pop     r14
0x18002d052  pop     rdi
0x18002d053  pop     rsi
0x18002d054  retn
```
