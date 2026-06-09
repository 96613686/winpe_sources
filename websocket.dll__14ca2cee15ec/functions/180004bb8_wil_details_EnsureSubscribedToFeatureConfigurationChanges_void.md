# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180004bb8`
- end: `0x180004c74`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `188`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005fdc`

## callees

- `0x180004bb8`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004be2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004be2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004c00`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004c56`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004c00`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004c56`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_1800122BC;
  if ( !dword_1800122BC )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_180012300 )
      {
        v1 = dword_1800122BC;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_180012300 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_180012300,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_180012300 )
      {
        v1 = 1;
        dword_1800122BC = 1;
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
0x180004bb8  push    rbx
0x180004bba  sub     rsp, 20h
0x180004bbe  mov     ebx, cs:dword_1800122BC
0x180004bc4  nop
0x180004bc5  test    ebx, ebx
0x180004bc7  jnz     loc_180004C5E
0x180004bcd  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180004bd3  test    eax, eax
0x180004bd5  jz      loc_180004C5C
0x180004bdb  lea     rcx, SRWLock; SRWLock
0x180004be2  call    cs:__imp_AcquireSRWLockExclusive
0x180004be8  cmp     cs:qword_180012300, 0
0x180004bf0  jz      short loc_180004C08
0x180004bf2  mov     ebx, cs:dword_1800122BC
0x180004bf8  lea     rcx, SRWLock; SRWLock
0x180004bff  nop
0x180004c00  call    cs:__imp_ReleaseSRWLockExclusive
0x180004c06  jmp     short loc_180004C5E
0x180004c08  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180004c0f  mov     cs:qword_180012300, 0
0x180004c1a  test    rax, rax
0x180004c1d  jnz     short loc_180004C2B
0x180004c1f  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180004c26  test    rax, rax
0x180004c29  jz      short loc_180004C45
0x180004c2b  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180004c32  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180004c39  lea     rcx, qword_180012300
0x180004c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c45  cmp     cs:qword_180012300, 0
0x180004c4d  lea     rcx, SRWLock; SRWLock
0x180004c54  jnz     short loc_180004C66
0x180004c56  call    cs:__imp_ReleaseSRWLockExclusive
0x180004c5c  xor     ebx, ebx
0x180004c5e  mov     eax, ebx
0x180004c60  add     rsp, 20h
0x180004c64  pop     rbx
0x180004c65  retn
0x180004c66  mov     ebx, 1
0x180004c6b  nop
0x180004c6c  mov     cs:dword_1800122BC, ebx
0x180004c72  jmp     short loc_180004C00
```
