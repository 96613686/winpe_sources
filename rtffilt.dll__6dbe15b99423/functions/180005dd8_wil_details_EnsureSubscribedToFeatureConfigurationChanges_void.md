# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180005dd8`
- end: `0x180005e95`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `18`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006324`
- `0x1800064f4`
- `0x180006674`
- `0x180007684`
- `0x180011e5c`
- `0x180011f3c`
- `0x18001201c`
- `0x1800121f0`
- `0x1800122d0`
- `0x1800124a4`
- `0x180012624`
- `0x1800127f8`
- `0x1800129cc`
- `0x180012aac`
- `0x180012c80`
- `0x180012dfc`
- `0x180012f70`
- `0x180013d4c`

## callees

- `0x180005dd8`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005e02`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005e02`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005e20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005e76`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005e20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005e76`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_1800234A4;
  if ( !dword_1800234A4 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_1800234E8 )
      {
        v1 = dword_1800234A4;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_1800234E8 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_1800234E8,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_1800234E8 )
      {
        v1 = 1;
        dword_1800234A4 = 1;
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
0x180005dd8  push    rbx
0x180005dda  sub     rsp, 20h
0x180005dde  mov     ebx, cs:dword_1800234A4
0x180005de4  nop
0x180005de5  test    ebx, ebx
0x180005de7  jnz     loc_180005E7E
0x180005ded  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180005df3  test    eax, eax
0x180005df5  jz      loc_180005E7C
0x180005dfb  lea     rcx, SRWLock; SRWLock
0x180005e02  call    cs:__imp_AcquireSRWLockExclusive
0x180005e08  cmp     cs:qword_1800234E8, 0
0x180005e10  jz      short loc_180005E28
0x180005e12  mov     ebx, cs:dword_1800234A4
0x180005e18  nop
0x180005e19  lea     rcx, SRWLock; SRWLock
0x180005e20  call    cs:__imp_ReleaseSRWLockExclusive
0x180005e26  jmp     short loc_180005E7E
0x180005e28  mov     cs:qword_1800234E8, 0
0x180005e33  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180005e3a  test    rax, rax
0x180005e3d  jnz     short loc_180005E4B
0x180005e3f  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180005e46  test    rax, rax
0x180005e49  jz      short loc_180005E65
0x180005e4b  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180005e52  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180005e59  lea     rcx, qword_1800234E8
0x180005e60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e65  lea     rcx, SRWLock; SRWLock
0x180005e6c  cmp     cs:qword_1800234E8, 0
0x180005e74  jnz     short loc_180005E86
0x180005e76  call    cs:__imp_ReleaseSRWLockExclusive
0x180005e7c  xor     ebx, ebx
0x180005e7e  mov     eax, ebx
0x180005e80  add     rsp, 20h
0x180005e84  pop     rbx
0x180005e85  retn
0x180005e86  nop
0x180005e87  mov     ebx, 1
0x180005e8c  mov     cs:dword_1800234A4, ebx
0x180005e92  jmp     short loc_180005E20
```
