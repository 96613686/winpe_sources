# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180005cf8`
- end: `0x180005db5`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006e10`
- `0x18001708c`
- `0x180017260`
- `0x1800173d4`
- `0x180017548`
- `0x1800176bc`
- `0x18001779c`
- `0x18001787c`
- `0x18001795c`

## callees

- `0x180005cf8`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005d40`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005d96`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005d40`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005d96`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005d22`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005d22`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_1800419B4;
  if ( !dword_1800419B4 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_1800419F8 )
      {
        v1 = dword_1800419B4;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_1800419F8 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_1800419F8,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_1800419F8 )
      {
        v1 = 1;
        dword_1800419B4 = 1;
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
0x180005cf8  push    rbx
0x180005cfa  sub     rsp, 20h
0x180005cfe  mov     ebx, cs:dword_1800419B4
0x180005d04  nop
0x180005d05  test    ebx, ebx
0x180005d07  jnz     loc_180005D9E
0x180005d0d  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180005d13  test    eax, eax
0x180005d15  jz      loc_180005D9C
0x180005d1b  lea     rcx, SRWLock; SRWLock
0x180005d22  call    cs:__imp_AcquireSRWLockExclusive
0x180005d28  cmp     cs:qword_1800419F8, 0
0x180005d30  jz      short loc_180005D48
0x180005d32  mov     ebx, cs:dword_1800419B4
0x180005d38  nop
0x180005d39  lea     rcx, SRWLock; SRWLock
0x180005d40  call    cs:__imp_ReleaseSRWLockExclusive
0x180005d46  jmp     short loc_180005D9E
0x180005d48  mov     cs:qword_1800419F8, 0
0x180005d53  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180005d5a  test    rax, rax
0x180005d5d  jnz     short loc_180005D6B
0x180005d5f  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180005d66  test    rax, rax
0x180005d69  jz      short loc_180005D85
0x180005d6b  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180005d72  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180005d79  lea     rcx, qword_1800419F8
0x180005d80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d85  lea     rcx, SRWLock; SRWLock
0x180005d8c  cmp     cs:qword_1800419F8, 0
0x180005d94  jnz     short loc_180005DA6
0x180005d96  call    cs:__imp_ReleaseSRWLockExclusive
0x180005d9c  xor     ebx, ebx
0x180005d9e  mov     eax, ebx
0x180005da0  add     rsp, 20h
0x180005da4  pop     rbx
0x180005da5  retn
0x180005da6  nop
0x180005da7  mov     ebx, 1
0x180005dac  mov     cs:dword_1800419B4, ebx
0x180005db2  jmp     short loc_180005D40
```
