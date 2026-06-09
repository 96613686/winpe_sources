# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18000ca74`
- end: `0x18000cb31`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `44`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000cee8`
- `0x18001267c`
- `0x180012850`
- `0x180012a24`
- `0x180012b98`
- `0x180012d0c`
- `0x180012e80`
- `0x180012ff4`
- `0x180013168`
- `0x1800132dc`
- `0x1800133bc`
- `0x18001349c`
- `0x18001357c`
- `0x18001365c`
- `0x18001373c`
- `0x18001381c`
- `0x18001cf78`
- `0x18001d148`
- `0x18001d31c`
- `0x18001d4f0`
- `0x18001d6c4`
- `0x18001d898`
- `0x18001da6c`
- `0x18001dc40`
- `0x18001de14`
- `0x18001dfe8`
- `0x18001e1b8`
- `0x18001e38c`
- `0x18001e560`
- `0x18001e734`
- `0x18001e904`
- `0x18001ead4`
- `0x18001eca8`
- `0x18001ee7c`
- `0x18001f050`
- `0x18001f1c4`
- `0x18001f344`
- `0x18001f518`
- `0x18001f5f8`
- `0x18001f7c8`
- `0x18001f99c`
- `0x18001fb70`
- `0x18001fc50`
- `0x18001fe20`

## callees

- `0x18000ca74`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ca9e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ca9e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cabc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cb12`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cabc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cb12`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_1800346C4;
  if ( !dword_1800346C4 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_180034708 )
      {
        v1 = dword_1800346C4;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_180034708 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_180034708,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_180034708 )
      {
        v1 = 1;
        dword_1800346C4 = 1;
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
0x18000ca74  push    rbx
0x18000ca76  sub     rsp, 20h
0x18000ca7a  mov     ebx, cs:dword_1800346C4
0x18000ca80  nop
0x18000ca81  test    ebx, ebx
0x18000ca83  jnz     loc_18000CB1A
0x18000ca89  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000ca8f  test    eax, eax
0x18000ca91  jz      loc_18000CB18
0x18000ca97  lea     rcx, SRWLock; SRWLock
0x18000ca9e  call    cs:__imp_AcquireSRWLockExclusive
0x18000caa4  cmp     cs:qword_180034708, 0
0x18000caac  jz      short loc_18000CAC4
0x18000caae  mov     ebx, cs:dword_1800346C4
0x18000cab4  nop
0x18000cab5  lea     rcx, SRWLock; SRWLock
0x18000cabc  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cac2  jmp     short loc_18000CB1A
0x18000cac4  mov     cs:qword_180034708, 0
0x18000cacf  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000cad6  test    rax, rax
0x18000cad9  jnz     short loc_18000CAE7
0x18000cadb  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000cae2  test    rax, rax
0x18000cae5  jz      short loc_18000CB01
0x18000cae7  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000caee  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18000caf5  lea     rcx, qword_180034708
0x18000cafc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb01  lea     rcx, SRWLock; SRWLock
0x18000cb08  cmp     cs:qword_180034708, 0
0x18000cb10  jnz     short loc_18000CB22
0x18000cb12  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cb18  xor     ebx, ebx
0x18000cb1a  mov     eax, ebx
0x18000cb1c  add     rsp, 20h
0x18000cb20  pop     rbx
0x18000cb21  retn
0x18000cb22  nop
0x18000cb23  mov     ebx, 1
0x18000cb28  mov     cs:dword_1800346C4, ebx
0x18000cb2e  jmp     short loc_18000CABC
```
