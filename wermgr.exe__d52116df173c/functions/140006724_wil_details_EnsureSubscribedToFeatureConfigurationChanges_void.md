# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x140006724`
- end: `0x1400067e1`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140006814`
- `0x14000698c`
- `0x140006b0c`
- `0x140011ec0`

## callees

- `0x140006724`
- `0x14001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000676c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400067c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000676c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400067c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000674e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000674e`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_14002C444;
  if ( !dword_14002C444 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_14002C488 )
      {
        v1 = dword_14002C444;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_14002C488 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_14002C488,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_14002C488 )
      {
        v1 = 1;
        dword_14002C444 = 1;
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
0x140006724  push    rbx
0x140006726  sub     rsp, 20h
0x14000672a  mov     ebx, cs:dword_14002C444
0x140006730  nop
0x140006731  test    ebx, ebx
0x140006733  jnz     loc_1400067CA
0x140006739  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000673f  test    eax, eax
0x140006741  jz      loc_1400067C8
0x140006747  lea     rcx, SRWLock; SRWLock
0x14000674e  call    cs:__imp_AcquireSRWLockExclusive
0x140006754  cmp     cs:qword_14002C488, 0
0x14000675c  jz      short loc_140006774
0x14000675e  mov     ebx, cs:dword_14002C444
0x140006764  nop
0x140006765  lea     rcx, SRWLock; SRWLock
0x14000676c  call    cs:__imp_ReleaseSRWLockExclusive
0x140006772  jmp     short loc_1400067CA
0x140006774  mov     cs:qword_14002C488, 0
0x14000677f  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x140006786  test    rax, rax
0x140006789  jnz     short loc_140006797
0x14000678b  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x140006792  test    rax, rax
0x140006795  jz      short loc_1400067B1
0x140006797  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000679e  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x1400067a5  lea     rcx, qword_14002C488
0x1400067ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400067b1  lea     rcx, SRWLock; SRWLock
0x1400067b8  cmp     cs:qword_14002C488, 0
0x1400067c0  jnz     short loc_1400067D2
0x1400067c2  call    cs:__imp_ReleaseSRWLockExclusive
0x1400067c8  xor     ebx, ebx
0x1400067ca  mov     eax, ebx
0x1400067cc  add     rsp, 20h
0x1400067d0  pop     rbx
0x1400067d1  retn
0x1400067d2  nop
0x1400067d3  mov     ebx, 1
0x1400067d8  mov     cs:dword_14002C444, ebx
0x1400067de  jmp     short loc_14000676C
```
