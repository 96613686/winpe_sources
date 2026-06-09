# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180004548`
- end: `0x180004604`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `188`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005640`

## callees

- `0x180004548`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004572`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004572`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004590`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800045e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004590`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800045e6`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_18002D87C;
  if ( !dword_18002D87C )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_18002D8C0 )
      {
        v1 = dword_18002D87C;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_18002D8C0 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_18002D8C0,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_18002D8C0 )
      {
        v1 = 1;
        dword_18002D87C = 1;
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
0x180004548  push    rbx
0x18000454a  sub     rsp, 20h
0x18000454e  mov     ebx, cs:dword_18002D87C
0x180004554  nop
0x180004555  test    ebx, ebx
0x180004557  jnz     loc_1800045EE
0x18000455d  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180004563  test    eax, eax
0x180004565  jz      loc_1800045EC
0x18000456b  lea     rcx, SRWLock; SRWLock
0x180004572  call    cs:__imp_AcquireSRWLockExclusive
0x180004578  cmp     cs:qword_18002D8C0, 0
0x180004580  jz      short loc_180004598
0x180004582  mov     ebx, cs:dword_18002D87C
0x180004588  lea     rcx, SRWLock; SRWLock
0x18000458f  nop
0x180004590  call    cs:__imp_ReleaseSRWLockExclusive
0x180004596  jmp     short loc_1800045EE
0x180004598  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000459f  mov     cs:qword_18002D8C0, 0
0x1800045aa  test    rax, rax
0x1800045ad  jnz     short loc_1800045BB
0x1800045af  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1800045b6  test    rax, rax
0x1800045b9  jz      short loc_1800045D5
0x1800045bb  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800045c2  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x1800045c9  lea     rcx, qword_18002D8C0
0x1800045d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045d5  cmp     cs:qword_18002D8C0, 0
0x1800045dd  lea     rcx, SRWLock; SRWLock
0x1800045e4  jnz     short loc_1800045F6
0x1800045e6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800045ec  xor     ebx, ebx
0x1800045ee  mov     eax, ebx
0x1800045f0  add     rsp, 20h
0x1800045f4  pop     rbx
0x1800045f5  retn
0x1800045f6  mov     ebx, 1
0x1800045fb  nop
0x1800045fc  mov     cs:dword_18002D87C, ebx
0x180004602  jmp     short loc_180004590
```
