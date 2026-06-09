# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x1400068a4`
- end: `0x140006960`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `188`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140006df4`
- `0x1400086fc`

## callees

- `0x1400068a4`
- `0x140015010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x1400068ce`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400068ce`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400068ec`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140006942`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400068ec`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140006942`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_1400203EC;
  if ( !dword_1400203EC )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_140020430 )
      {
        v1 = dword_1400203EC;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_140020430 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_140020430,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_140020430 )
      {
        v1 = 1;
        dword_1400203EC = 1;
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
0x1400068a4  push    rbx
0x1400068a6  sub     rsp, 20h
0x1400068aa  mov     ebx, cs:dword_1400203EC
0x1400068b0  nop
0x1400068b1  test    ebx, ebx
0x1400068b3  jnz     loc_14000694A
0x1400068b9  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1400068bf  test    eax, eax
0x1400068c1  jz      loc_140006948
0x1400068c7  lea     rcx, SRWLock; SRWLock
0x1400068ce  call    cs:__imp_AcquireSRWLockExclusive
0x1400068d4  cmp     cs:qword_140020430, 0
0x1400068dc  jz      short loc_1400068F4
0x1400068de  mov     ebx, cs:dword_1400203EC
0x1400068e4  lea     rcx, SRWLock; SRWLock
0x1400068eb  nop
0x1400068ec  call    cs:__imp_ReleaseSRWLockExclusive
0x1400068f2  jmp     short loc_14000694A
0x1400068f4  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1400068fb  mov     cs:qword_140020430, 0
0x140006906  test    rax, rax
0x140006909  jnz     short loc_140006917
0x14000690b  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x140006912  test    rax, rax
0x140006915  jz      short loc_140006931
0x140006917  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000691e  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x140006925  lea     rcx, qword_140020430
0x14000692c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006931  cmp     cs:qword_140020430, 0
0x140006939  lea     rcx, SRWLock; SRWLock
0x140006940  jnz     short loc_140006952
0x140006942  call    cs:__imp_ReleaseSRWLockExclusive
0x140006948  xor     ebx, ebx
0x14000694a  mov     eax, ebx
0x14000694c  add     rsp, 20h
0x140006950  pop     rbx
0x140006951  retn
0x140006952  mov     ebx, 1
0x140006957  nop
0x140006958  mov     cs:dword_1400203EC, ebx
0x14000695e  jmp     short loc_1400068EC
```
