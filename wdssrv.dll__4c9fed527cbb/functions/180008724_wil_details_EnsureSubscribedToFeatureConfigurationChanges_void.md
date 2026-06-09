# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180008724`
- end: `0x1800087fc`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `216`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008e78`
- `0x18000a338`

## callees

- `0x180008724`
- `0x18001d010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180008750`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180008750`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180008776`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800087cf`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180008776`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800087cf`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_180028344;
  if ( !dword_180028344 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_180028348 )
      {
        v1 = dword_180028344;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_180028348 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_180028348,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_180028348 )
      {
        v1 = 1;
        dword_180028344 = 1;
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
0x180008724  mov     [rsp+arg_0], rbx
0x180008729  push    rdi
0x18000872a  sub     rsp, 20h
0x18000872e  mov     ebx, cs:dword_180028344
0x180008734  nop
0x180008735  test    ebx, ebx
0x180008737  jnz     loc_1800087DD
0x18000873d  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, bl; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180008743  jz      loc_1800087DB
0x180008749  lea     rcx, SRWLock; SRWLock
0x180008750  call    cs:__imp_AcquireSRWLockExclusive
0x180008757  nop     dword ptr [rax+rax+00h]
0x18000875c  mov     rbx, cs:qword_180028348
0x180008763  test    rbx, rbx
0x180008766  jz      short loc_180008784
0x180008768  mov     ebx, cs:dword_180028344
0x18000876e  lea     rcx, SRWLock; SRWLock
0x180008775  nop
0x180008776  call    cs:__imp_ReleaseSRWLockExclusive
0x18000877d  nop     dword ptr [rax+rax+00h]
0x180008782  jmp     short loc_1800087DD
0x180008784  and     cs:qword_180028348, 0
0x18000878c  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180008793  test    rax, rax
0x180008796  jnz     short loc_1800087A4
0x180008798  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000879f  test    rax, rax
0x1800087a2  jz      short loc_1800087BE
0x1800087a4  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800087ab  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x1800087b2  lea     rcx, qword_180028348
0x1800087b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087be  cmp     cs:qword_180028348, 0
0x1800087c6  lea     rcx, SRWLock; SRWLock
0x1800087cd  jnz     short loc_1800087EB
0x1800087cf  call    cs:__imp_ReleaseSRWLockExclusive
0x1800087d6  nop     dword ptr [rax+rax+00h]
0x1800087db  xor     ebx, ebx
0x1800087dd  mov     eax, ebx
0x1800087df  mov     rbx, [rsp+28h+arg_0]
0x1800087e4  add     rsp, 20h
0x1800087e8  pop     rdi
0x1800087e9  retn
0x1800087eb  mov     ebx, 1
0x1800087f0  nop
0x1800087f1  mov     cs:dword_180028344, ebx
0x1800087f7  jmp     loc_180008776
```
