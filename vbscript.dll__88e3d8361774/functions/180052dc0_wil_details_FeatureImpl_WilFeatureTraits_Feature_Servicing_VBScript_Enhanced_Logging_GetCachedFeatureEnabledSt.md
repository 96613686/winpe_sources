# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::GetCachedFeatureEnabledState(void)

- ea: `0x180052dc0`
- end: `0x180052ef9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180055930`
- `0x180056438`

## callees

- `0x18002d704`
- `0x18002dbe4`
- `0x180039f1c`
- `0x180052dc0`
- `0x18005357c`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180052e7e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180052e7e`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Servicing_VBScript_Enhanced_Logging__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_VBScript_Enhanced_Logging__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::GetCurrentFeatureEnabledState(
      v6,
      &v16,
      &v15);
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
      v7 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_Servicing_VBScript_Enhanced_Logging__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_18009086C
        || (Source[0] = 3,
            Source[1] = Feature_Servicing_VBScript_Enhanced_Logging__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180090890, Source, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Servicing_VBScript_Enhanced_Logging__descriptor, 0xFFFFFFFB);
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
0x180052dc0  mov     [rsp+arg_10], rbx
0x180052dc5  mov     [rsp+arg_18], rbp
0x180052dca  mov     [rsp+arg_0], rcx
0x180052dcf  push    rsi
0x180052dd0  push    rdi
0x180052dd1  push    r14
0x180052dd3  sub     rsp, 30h
0x180052dd7  mov     rsi, cs:Feature_Servicing_VBScript_Enhanced_Logging__descriptor
0x180052dde  mov     rdi, rdx
0x180052de1  mov     qword ptr [rdx], 0
0x180052de8  mov     eax, [rsi]
0x180052dea  mov     [rdx], eax
0x180052dec  and     eax, 6
0x180052def  cmp     al, 6
0x180052df1  jz      loc_180052EE3
0x180052df7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180052dfc  lea     r8, [rsp+48h+arg_0]
0x180052e01  mov     dword ptr [rsp+48h+arg_0], 0
0x180052e09  lea     rdx, [rsp+48h+arg_8]
0x180052e0e  mov     ebp, eax
0x180052e10  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::GetCurrentFeatureEnabledState(int *)
0x180052e15  mov     eax, [rdi]
0x180052e17  mov     rbx, [rsp+48h+arg_8]
0x180052e1c  cmp     dword ptr [rsp+48h+arg_0], 0
0x180052e21  mov     edx, eax
0x180052e23  mov     [rdi], eax
0x180052e25  mov     ecx, eax
0x180052e27  jz      short loc_180052E42
0x180052e29  test    dl, 2
0x180052e2c  jnz     short loc_180052E42
0x180052e2e  and     ecx, 0FFFFF63Eh
0x180052e34  mov     eax, ebx
0x180052e36  and     eax, 9C1h
0x180052e3b  or      ecx, eax
0x180052e3d  or      ecx, 2
0x180052e40  mov     [rdi], ecx
0x180052e42  mov     r8d, edx
0x180052e45  and     r8d, 4
0x180052e49  jnz     short loc_180052E5D
0x180052e4b  btr     ecx, 0Ah
0x180052e4f  mov     eax, ebx
0x180052e51  and     eax, 400h
0x180052e56  or      ecx, eax
0x180052e58  or      ecx, 4
0x180052e5b  mov     [rdi], ecx
0x180052e5d  mov     eax, edx
0x180052e5f  lock cmpxchg [rsi], ecx
0x180052e63  jnz     short loc_180052E1C
0x180052e65  test    r8d, r8d
0x180052e68  jnz     short loc_180052ECE
0x180052e6a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180052e70  test    eax, eax
0x180052e72  jz      short loc_180052ECE
0x180052e74  lea     r14, SRWLock
0x180052e7b  mov     rcx, r14; SRWLock
0x180052e7e  call    cs:__imp_AcquireSRWLockExclusive
0x180052e84  mov     eax, cs:dword_18009086C
0x180052e8a  mov     [rsp+48h+arg_8], r14
0x180052e8f  test    ebp, ebp
0x180052e91  jz      short loc_180052EC0
0x180052e93  cmp     ebp, eax
0x180052e95  jnz     short loc_180052EC0
0x180052e97  mov     r8d, 10h; SourceSize
0x180052e9d  mov     [rsp+48h+Source], 3
0x180052ea6  lea     rdx, [rsp+48h+Source]; Source
0x180052eab  mov     [rsp+48h+var_20], rsi
0x180052eb0  lea     rcx, qword_180090890; this
0x180052eb7  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180052ebc  test    al, al
0x180052ebe  jnz     short loc_180052EC4
0x180052ec0  lock and dword ptr [rsi], 0FFFFFFFBh
0x180052ec4  lea     rcx, [rsp+48h+arg_8]
0x180052ec9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180052ece  mov     eax, [rdi]
0x180052ed0  test    al, 2
0x180052ed2  jnz     short loc_180052EE3
0x180052ed4  and     eax, 0FFFFF63Eh
0x180052ed9  and     ebx, 9C1h
0x180052edf  or      eax, ebx
0x180052ee1  mov     [rdi], eax
0x180052ee3  mov     rbx, [rsp+48h+arg_10]
0x180052ee8  mov     rax, rdi
0x180052eeb  mov     rbp, [rsp+48h+arg_18]
0x180052ef0  add     rsp, 30h
0x180052ef4  pop     r14
0x180052ef6  pop     rdi
0x180052ef7  pop     rsi
0x180052ef8  retn
```
