# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180006740`
- end: `0x1800067fd`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180007020`
- `0x1800078e8`

## callees

- `0x180006740`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000676a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000676a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006788`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800067de`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006788`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800067de`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_18001584C;
  if ( !dword_18001584C )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_180015890 )
      {
        v1 = dword_18001584C;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_180015890 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_180015890,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_180015890 )
      {
        v1 = 1;
        dword_18001584C = 1;
        goto LABEL_5;
      }
      ReleaseSRWLockExclusive(&SRWLock);
    }
    return 0;
  }
  return v1;
}

```

## disassembly

```asm
0x180006740  push    rbx
0x180006742  sub     rsp, 20h
0x180006746  mov     ebx, cs:dword_18001584C
0x18000674c  nop
0x18000674d  test    ebx, ebx
0x18000674f  jnz     loc_1800067E6
0x180006755  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000675b  test    eax, eax
0x18000675d  jz      loc_1800067E4
0x180006763  lea     rcx, SRWLock; SRWLock
0x18000676a  call    cs:__imp_AcquireSRWLockExclusive
0x180006770  cmp     cs:qword_180015890, 0
0x180006778  jz      short loc_180006790
0x18000677a  mov     ebx, cs:dword_18001584C
0x180006780  nop
0x180006781  lea     rcx, SRWLock; SRWLock
0x180006788  call    cs:__imp_ReleaseSRWLockExclusive
0x18000678e  jmp     short loc_1800067E6
0x180006790  mov     cs:qword_180015890, 0
0x18000679b  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1800067a2  test    rax, rax
0x1800067a5  jnz     short loc_1800067B3
0x1800067a7  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1800067ae  test    rax, rax
0x1800067b1  jz      short loc_1800067CD
0x1800067b3  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800067ba  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x1800067c1  lea     rcx, qword_180015890
0x1800067c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067cd  lea     rcx, SRWLock; SRWLock
0x1800067d4  cmp     cs:qword_180015890, 0
0x1800067dc  jnz     short loc_1800067EE
0x1800067de  call    cs:__imp_ReleaseSRWLockExclusive
0x1800067e4  xor     ebx, ebx
0x1800067e6  mov     eax, ebx
0x1800067e8  add     rsp, 20h
0x1800067ec  pop     rbx
0x1800067ed  retn
0x1800067ee  nop
0x1800067ef  mov     ebx, 1
0x1800067f4  mov     cs:dword_18001584C, ebx
0x1800067fa  jmp     short loc_180006788
```
