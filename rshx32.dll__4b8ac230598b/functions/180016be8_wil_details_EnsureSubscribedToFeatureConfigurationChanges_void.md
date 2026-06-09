# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180016be8`
- end: `0x180016ca4`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `188`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `15`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180016cac`
- `0x180016e80`
- `0x180016ff4`
- `0x180017168`
- `0x1800172dc`
- `0x180017450`
- `0x1800175c4`
- `0x180017738`
- `0x180017818`
- `0x1800178f8`
- `0x1800179d8`
- `0x180017ab8`
- `0x180017b98`
- `0x180017c78`
- `0x18001af30`

## callees

- `0x180016be8`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016c30`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016c86`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016c30`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016c86`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016c12`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016c12`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_180028C54;
  if ( !dword_180028C54 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_180028C98 )
      {
        v1 = dword_180028C54;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_180028C98 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_180028C98,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_180028C98 )
      {
        v1 = 1;
        dword_180028C54 = 1;
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
0x180016be8  push    rbx
0x180016bea  sub     rsp, 20h
0x180016bee  mov     ebx, cs:dword_180028C54
0x180016bf4  nop
0x180016bf5  test    ebx, ebx
0x180016bf7  jnz     loc_180016C8E
0x180016bfd  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180016c03  test    eax, eax
0x180016c05  jz      loc_180016C8C
0x180016c0b  lea     rcx, SRWLock; SRWLock
0x180016c12  call    cs:__imp_AcquireSRWLockExclusive
0x180016c18  cmp     cs:qword_180028C98, 0
0x180016c20  jz      short loc_180016C38
0x180016c22  mov     ebx, cs:dword_180028C54
0x180016c28  lea     rcx, SRWLock; SRWLock
0x180016c2f  nop
0x180016c30  call    cs:__imp_ReleaseSRWLockExclusive
0x180016c36  jmp     short loc_180016C8E
0x180016c38  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180016c3f  mov     cs:qword_180028C98, 0
0x180016c4a  test    rax, rax
0x180016c4d  jnz     short loc_180016C5B
0x180016c4f  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180016c56  test    rax, rax
0x180016c59  jz      short loc_180016C75
0x180016c5b  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180016c62  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180016c69  lea     rcx, qword_180028C98
0x180016c70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c75  cmp     cs:qword_180028C98, 0
0x180016c7d  lea     rcx, SRWLock; SRWLock
0x180016c84  jnz     short loc_180016C96
0x180016c86  call    cs:__imp_ReleaseSRWLockExclusive
0x180016c8c  xor     ebx, ebx
0x180016c8e  mov     eax, ebx
0x180016c90  add     rsp, 20h
0x180016c94  pop     rbx
0x180016c95  retn
0x180016c96  mov     ebx, 1
0x180016c9b  nop
0x180016c9c  mov     cs:dword_180028C54, ebx
0x180016ca2  jmp     short loc_180016C30
```
