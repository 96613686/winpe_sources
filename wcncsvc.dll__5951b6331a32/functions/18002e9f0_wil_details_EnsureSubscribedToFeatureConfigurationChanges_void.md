# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18002e9f0`
- end: `0x18002eaad`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002f1cc`
- `0x18002f3a0`
- `0x18002f514`
- `0x18002f688`
- `0x18002f768`
- `0x18002f848`
- `0x1800307e4`

## callees

- `0x18002e9f0`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002ea38`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002ea8e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002ea38`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002ea8e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ea1a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ea1a`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_180074E94;
  if ( !dword_180074E94 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_180074E80);
      if ( qword_180074ED8 )
      {
        v1 = dword_180074E94;
LABEL_5:
        ReleaseSRWLockExclusive(&stru_180074E80);
        return v1;
      }
      qword_180074ED8 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_180074ED8,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_180074ED8 )
      {
        v1 = 1;
        dword_180074E94 = 1;
        goto LABEL_5;
      }
      ReleaseSRWLockExclusive(&stru_180074E80);
    }
    return 0;
  }
  return v1;
}

```

## disassembly

```asm
0x18002e9f0  push    rbx
0x18002e9f2  sub     rsp, 20h
0x18002e9f6  mov     ebx, cs:dword_180074E94
0x18002e9fc  nop
0x18002e9fd  test    ebx, ebx
0x18002e9ff  jnz     loc_18002EA96
0x18002ea05  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18002ea0b  test    eax, eax
0x18002ea0d  jz      loc_18002EA94
0x18002ea13  lea     rcx, stru_180074E80; SRWLock
0x18002ea1a  call    cs:__imp_AcquireSRWLockExclusive
0x18002ea20  cmp     cs:qword_180074ED8, 0
0x18002ea28  jz      short loc_18002EA40
0x18002ea2a  mov     ebx, cs:dword_180074E94
0x18002ea30  nop
0x18002ea31  lea     rcx, stru_180074E80; SRWLock
0x18002ea38  call    cs:__imp_ReleaseSRWLockExclusive
0x18002ea3e  jmp     short loc_18002EA96
0x18002ea40  mov     cs:qword_180074ED8, 0
0x18002ea4b  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18002ea52  test    rax, rax
0x18002ea55  jnz     short loc_18002EA63
0x18002ea57  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18002ea5e  test    rax, rax
0x18002ea61  jz      short loc_18002EA7D
0x18002ea63  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18002ea6a  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18002ea71  lea     rcx, qword_180074ED8
0x18002ea78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea7d  lea     rcx, stru_180074E80; SRWLock
0x18002ea84  cmp     cs:qword_180074ED8, 0
0x18002ea8c  jnz     short loc_18002EA9E
0x18002ea8e  call    cs:__imp_ReleaseSRWLockExclusive
0x18002ea94  xor     ebx, ebx
0x18002ea96  mov     eax, ebx
0x18002ea98  add     rsp, 20h
0x18002ea9c  pop     rbx
0x18002ea9d  retn
0x18002ea9e  nop
0x18002ea9f  mov     ebx, 1
0x18002eaa4  mov     cs:dword_180074E94, ebx
0x18002eaaa  jmp     short loc_18002EA38
```
