# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x140009698`
- end: `0x140009754`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `188`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140009b0c`
- `0x140009bec`
- `0x140009eb4`
- `0x14000f780`

## callees

- `0x140009698`
- `0x140016010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x1400096c2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400096c2`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400096e0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140009736`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400096e0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140009736`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_140021474;
  if ( !dword_140021474 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_1400214B8 )
      {
        v1 = dword_140021474;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_1400214B8 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_1400214B8,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_1400214B8 )
      {
        v1 = 1;
        dword_140021474 = 1;
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
0x140009698  push    rbx
0x14000969a  sub     rsp, 20h
0x14000969e  mov     ebx, cs:dword_140021474
0x1400096a4  nop
0x1400096a5  test    ebx, ebx
0x1400096a7  jnz     loc_14000973E
0x1400096ad  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1400096b3  test    eax, eax
0x1400096b5  jz      loc_14000973C
0x1400096bb  lea     rcx, SRWLock; SRWLock
0x1400096c2  call    cs:__imp_AcquireSRWLockExclusive
0x1400096c8  cmp     cs:qword_1400214B8, 0
0x1400096d0  jz      short loc_1400096E8
0x1400096d2  mov     ebx, cs:dword_140021474
0x1400096d8  lea     rcx, SRWLock; SRWLock
0x1400096df  nop
0x1400096e0  call    cs:__imp_ReleaseSRWLockExclusive
0x1400096e6  jmp     short loc_14000973E
0x1400096e8  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1400096ef  mov     cs:qword_1400214B8, 0
0x1400096fa  test    rax, rax
0x1400096fd  jnz     short loc_14000970B
0x1400096ff  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x140009706  test    rax, rax
0x140009709  jz      short loc_140009725
0x14000970b  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140009712  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x140009719  lea     rcx, qword_1400214B8
0x140009720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009725  cmp     cs:qword_1400214B8, 0
0x14000972d  lea     rcx, SRWLock; SRWLock
0x140009734  jnz     short loc_140009746
0x140009736  call    cs:__imp_ReleaseSRWLockExclusive
0x14000973c  xor     ebx, ebx
0x14000973e  mov     eax, ebx
0x140009740  add     rsp, 20h
0x140009744  pop     rbx
0x140009745  retn
0x140009746  mov     ebx, 1
0x14000974b  nop
0x14000974c  mov     cs:dword_140021474, ebx
0x140009752  jmp     short loc_1400096E0
```
