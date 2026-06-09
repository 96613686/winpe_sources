# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180003aa8`
- end: `0x180003b63`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `187`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180002214`
- `0x1800026f8`
- `0x1800029dc`

## callees

- `0x180003aa8`
- `0x1800148e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003ad0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003ad0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003aee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003b44`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003aee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003b44`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, void (__fastcall *)(__int64), void *); // rax

  v1 = dword_18001F1EC;
  if ( !dword_18001F1EC )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_18001F1F0 )
      {
        v1 = dword_18001F1EC;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_18001F1F0 = 0;
      v2 = (void (__fastcall *)(__int64 *, void (__fastcall *)(__int64), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, void (__fastcall *)(__int64), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_18001F1F0,
          `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl'::`5'::_lambda_1_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_18001F1F0 )
      {
        v1 = 1;
        dword_18001F1EC = 1;
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
0x180003aa8  push    rbx
0x180003aaa  sub     rsp, 20h
0x180003aae  mov     ebx, cs:dword_18001F1EC
0x180003ab4  nop
0x180003ab5  test    ebx, ebx
0x180003ab7  jnz     loc_180003B4C
0x180003abd  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, bl; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180003ac3  jz      loc_180003B4A
0x180003ac9  lea     rcx, SRWLock; SRWLock
0x180003ad0  call    cs:__imp_AcquireSRWLockExclusive
0x180003ad6  cmp     cs:qword_18001F1F0, 0
0x180003ade  jz      short loc_180003AF6
0x180003ae0  mov     ebx, cs:dword_18001F1EC
0x180003ae6  nop
0x180003ae7  lea     rcx, SRWLock; SRWLock
0x180003aee  call    cs:__imp_ReleaseSRWLockExclusive
0x180003af4  jmp     short loc_180003B4C
0x180003af6  mov     cs:qword_18001F1F0, 0
0x180003b01  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180003b08  test    rax, rax
0x180003b0b  jnz     short loc_180003B19
0x180003b0d  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180003b14  test    rax, rax
0x180003b17  jz      short loc_180003B33
0x180003b19  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180003b20  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ@SA@PEAX@Z; `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x180003b27  lea     rcx, qword_18001F1F0
0x180003b2e  call    _guard_dispatch_icall
0x180003b33  lea     rcx, SRWLock; SRWLock
0x180003b3a  cmp     cs:qword_18001F1F0, 0
0x180003b42  jnz     short loc_180003B54
0x180003b44  call    cs:__imp_ReleaseSRWLockExclusive
0x180003b4a  xor     ebx, ebx
0x180003b4c  mov     eax, ebx
0x180003b4e  add     rsp, 20h
0x180003b52  pop     rbx
0x180003b53  retn
0x180003b54  nop
0x180003b55  mov     ebx, 1
0x180003b5a  mov     cs:dword_18001F1EC, ebx
0x180003b60  jmp     short loc_180003AEE
```
