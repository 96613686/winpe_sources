# DebugData::AddComponentId(winrt::hstring const &)

- ea: `0x140054a0c`
- end: `0x140054aac`
- name: `?AddComponentId@DebugData@@QEAAXAEBUhstring@winrt@@@Z`
- size: `160`
- prototype: `void __fastcall(PSRWLOCK SRWLock, const struct winrt::hstring *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140057e34`

## callees

- `0x14000a814`
- `0x14000b420`
- `0x140046a30`
- `0x14004d3f0`
- `0x1400529a4`
- `0x140054a0c`
- `0x140059f0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140054a4e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140054a4e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall DebugData::AddComponentId(PSRWLOCK SRWLock, const struct winrt::hstring *a2)
{
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  char v6; // [rsp+40h] [rbp+18h] BYREF
  PSRWLOCK v7; // [rsp+48h] [rbp+20h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl'::`2'::impl) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x42,
      (unsigned int)"pcshell\\shell\\shellhost\\exe\\DebugData.h",
      v4);
  AcquireSRWLockExclusive(SRWLock);
  v7 = SRWLock;
  if ( SRWLock[2].Ptr == SRWLock[3].Ptr )
  {
    std::vector<winrt::hstring>::_Emplace_reallocate<winrt::hstring const &>(&SRWLock[1], SRWLock[2].Ptr, a2);
  }
  else
  {
    winrt::hstring::hstring((winrt::hstring *)SRWLock[2].Ptr, a2);
    SRWLock[2].Ptr = (char *)SRWLock[2].Ptr + 8;
  }
  DebugData::PublishShellHostProperties(SRWLock, &v6);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v7);
}

```

## disassembly

```asm
0x140054a0c  mov     [rsp+arg_0], rbx
0x140054a11  mov     [rsp+arg_8], rsi
0x140054a16  push    rdi
0x140054a17  sub     rsp, 20h
0x140054a1b  mov     rsi, rdx
0x140054a1e  mov     rdi, rcx
0x140054a21  mov     rbx, [rsp+28h]
0x140054a26  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_4@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4> `wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl(void)'::`2'::impl
0x140054a2d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(void)
0x140054a32  test    al, al
0x140054a34  jz      short loc_140054A4B
0x140054a36  lea     r8, aPcshellShellSh_0; "pcshell\\shell\\shellhost\\exe\\DebugDa"...
0x140054a3d  mov     edx, 42h ; 'B'; void *
0x140054a42  mov     rcx, rbx; this
0x140054a45  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140054a4b  mov     rcx, rdi; SRWLock
0x140054a4e  call    cs:__imp_AcquireSRWLockExclusive
0x140054a54  mov     [rsp+28h+arg_18], rdi
0x140054a59  mov     rax, [rdi+10h]
0x140054a5d  cmp     rax, [rdi+18h]
0x140054a61  jz      short loc_140054A75
0x140054a63  mov     rdx, rsi; struct winrt::hstring *
0x140054a66  mov     rcx, rax; this
0x140054a69  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x140054a6e  add     qword ptr [rdi+10h], 8
0x140054a73  jmp     short loc_140054A84
0x140054a75  mov     r8, rsi
0x140054a78  mov     rdx, rax
0x140054a7b  lea     rcx, [rdi+8]
0x140054a7f  call    ??$_Emplace_reallocate@AEBUhstring@winrt@@@?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@AEAAPEAUhstring@winrt@@QEAU23@AEBU23@@Z; std::vector<winrt::hstring>::_Emplace_reallocate<winrt::hstring const &>(winrt::hstring * const,winrt::hstring const &)
0x140054a84  lea     rdx, [rsp+28h+arg_10]
0x140054a89  mov     rcx, rdi
0x140054a8c  call    ?PublishShellHostProperties@DebugData@@AEAA?AUfire_and_forget@winrt@@XZ; DebugData::PublishShellHostProperties(void)
0x140054a91  nop
0x140054a92  lea     rcx, [rsp+28h+arg_18]
0x140054a97  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140054a9c  mov     rbx, [rsp+28h+arg_0]
0x140054aa1  mov     rsi, [rsp+28h+arg_8]
0x140054aa6  add     rsp, 20h
0x140054aaa  pop     rdi
0x140054aab  retn
```
