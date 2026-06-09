# wil::details::FeatureImpl<__WilFeatureTraits_Feature_FTW>::GetCachedFeatureEnabledState(void)

- ea: `0x14001ff88`
- end: `0x1400200c8`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_FTW@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140021ec8`
- `0x140022e6c`

## callees

- `0x14000483c`
- `0x140005430`
- `0x140009b7c`
- `0x14001ff88`
- `0x140020290`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x140020046`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140020046`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_FTW>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_FTW__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_FTW__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_FTW>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_FTW__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_1400473C8);
      v16 = &stru_1400473C8;
      if ( !v5
        || v5 != dword_1400473DC
        || (v14[0] = 1,
            v14[1] = Feature_FTW__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_140047410, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_FTW__descriptor, 0xFFFFFFFB);
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
0x14001ff88  mov     [rsp+arg_10], rbx
0x14001ff8d  mov     [rsp+arg_18], rbp
0x14001ff92  mov     [rsp+arg_0], rcx
0x14001ff97  push    rsi
0x14001ff98  push    rdi
0x14001ff99  push    r14
0x14001ff9b  sub     rsp, 30h
0x14001ff9f  mov     rsi, cs:Feature_FTW__descriptor
0x14001ffa6  mov     rdi, rdx
0x14001ffa9  mov     qword ptr [rdx], 0
0x14001ffb0  mov     eax, [rsi]
0x14001ffb2  mov     [rdx], eax
0x14001ffb4  and     eax, 6
0x14001ffb7  cmp     al, 6
0x14001ffb9  jz      loc_1400200B1
0x14001ffbf  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14001ffc4  lea     r8, [rsp+48h+arg_0]
0x14001ffc9  mov     dword ptr [rsp+48h+arg_0], 0
0x14001ffd1  lea     rdx, [rsp+48h+arg_8]
0x14001ffd6  mov     ebp, eax
0x14001ffd8  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_FTW@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FTW>::GetCurrentFeatureEnabledState(int *)
0x14001ffdd  mov     eax, [rdi]
0x14001ffdf  mov     rbx, [rsp+48h+arg_8]
0x14001ffe4  cmp     dword ptr [rsp+48h+arg_0], 0
0x14001ffe9  mov     edx, eax
0x14001ffeb  mov     [rdi], eax
0x14001ffed  mov     ecx, eax
0x14001ffef  jz      short loc_14002000A
0x14001fff1  test    dl, 2
0x14001fff4  jnz     short loc_14002000A
0x14001fff6  and     ecx, 0FFFFF63Eh
0x14001fffc  mov     eax, ebx
0x14001fffe  and     eax, 9C1h
0x140020003  or      ecx, eax
0x140020005  or      ecx, 2
0x140020008  mov     [rdi], ecx
0x14002000a  mov     r8d, edx
0x14002000d  and     r8d, 4
0x140020011  jnz     short loc_140020025
0x140020013  btr     ecx, 0Ah
0x140020017  mov     eax, ebx
0x140020019  and     eax, 400h
0x14002001e  or      ecx, eax
0x140020020  or      ecx, 4
0x140020023  mov     [rdi], ecx
0x140020025  mov     eax, edx
0x140020027  lock cmpxchg [rsi], ecx
0x14002002b  jnz     short loc_14001FFE4
0x14002002d  test    r8d, r8d
0x140020030  jnz     short loc_14002009C
0x140020032  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140020038  test    eax, eax
0x14002003a  jz      short loc_14002009C
0x14002003c  lea     r14, stru_1400473C8
0x140020043  mov     rcx, r14; SRWLock
0x140020046  call    cs:__imp_AcquireSRWLockExclusive
0x14002004d  nop     dword ptr [rax+rax+00h]
0x140020052  mov     eax, cs:dword_1400473DC
0x140020058  mov     [rsp+48h+arg_8], r14
0x14002005d  test    ebp, ebp
0x14002005f  jz      short loc_14002008E
0x140020061  cmp     ebp, eax
0x140020063  jnz     short loc_14002008E
0x140020065  mov     r8d, 10h; unsigned __int64
0x14002006b  mov     [rsp+48h+var_28], 1
0x140020074  lea     rdx, [rsp+48h+var_28]; void *
0x140020079  mov     [rsp+48h+var_20], rsi
0x14002007e  lea     rcx, qword_140047410; this
0x140020085  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14002008a  test    al, al
0x14002008c  jnz     short loc_140020092
0x14002008e  lock and dword ptr [rsi], 0FFFFFFFBh
0x140020092  lea     rcx, [rsp+48h+arg_8]
0x140020097  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14002009c  mov     eax, [rdi]
0x14002009e  test    al, 2
0x1400200a0  jnz     short loc_1400200B1
0x1400200a2  and     eax, 0FFFFF63Eh
0x1400200a7  and     ebx, 9C1h
0x1400200ad  or      eax, ebx
0x1400200af  mov     [rdi], eax
0x1400200b1  mov     rbx, [rsp+48h+arg_10]
0x1400200b6  mov     rax, rdi
0x1400200b9  mov     rbp, [rsp+48h+arg_18]
0x1400200be  add     rsp, 30h
0x1400200c2  pop     r14
0x1400200c4  pop     rdi
0x1400200c5  pop     rsi
0x1400200c6  retn
```
