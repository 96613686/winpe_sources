# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180005dd0`
- end: `0x180005e8d`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `13`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800064d4`
- `0x1800066a8`
- `0x18000681c`
- `0x180006990`
- `0x180006b04`
- `0x180006c78`
- `0x180006dec`
- `0x180006ecc`
- `0x180006fac`
- `0x18000708c`
- `0x18000716c`
- `0x18000724c`
- `0x180008e50`

## callees

- `0x180005dd0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005e18`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005e6e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005e18`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005e6e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005dfa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005dfa`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_180021734;
  if ( !dword_180021734 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_180021778 )
      {
        v1 = dword_180021734;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_180021778 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_180021778,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_180021778 )
      {
        v1 = 1;
        dword_180021734 = 1;
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
0x180005dd0  push    rbx
0x180005dd2  sub     rsp, 20h
0x180005dd6  mov     ebx, cs:dword_180021734
0x180005ddc  nop
0x180005ddd  test    ebx, ebx
0x180005ddf  jnz     loc_180005E76
0x180005de5  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180005deb  test    eax, eax
0x180005ded  jz      loc_180005E74
0x180005df3  lea     rcx, SRWLock; SRWLock
0x180005dfa  call    cs:__imp_AcquireSRWLockExclusive
0x180005e00  cmp     cs:qword_180021778, 0
0x180005e08  jz      short loc_180005E20
0x180005e0a  mov     ebx, cs:dword_180021734
0x180005e10  nop
0x180005e11  lea     rcx, SRWLock; SRWLock
0x180005e18  call    cs:__imp_ReleaseSRWLockExclusive
0x180005e1e  jmp     short loc_180005E76
0x180005e20  mov     cs:qword_180021778, 0
0x180005e2b  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180005e32  test    rax, rax
0x180005e35  jnz     short loc_180005E43
0x180005e37  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180005e3e  test    rax, rax
0x180005e41  jz      short loc_180005E5D
0x180005e43  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180005e4a  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180005e51  lea     rcx, qword_180021778
0x180005e58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e5d  lea     rcx, SRWLock; SRWLock
0x180005e64  cmp     cs:qword_180021778, 0
0x180005e6c  jnz     short loc_180005E7E
0x180005e6e  call    cs:__imp_ReleaseSRWLockExclusive
0x180005e74  xor     ebx, ebx
0x180005e76  mov     eax, ebx
0x180005e78  add     rsp, 20h
0x180005e7c  pop     rbx
0x180005e7d  retn
0x180005e7e  nop
0x180005e7f  mov     ebx, 1
0x180005e84  mov     cs:dword_180021734, ebx
0x180005e8a  jmp     short loc_180005E18
```
