# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180010910`
- end: `0x1800109cb`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `187`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180014f48`
- `0x1800150d8`
- `0x1800157ec`
- `0x180015ad4`
- `0x180015fe4`
- `0x1800162c8`
- `0x180016464`
- `0x180019924`
- `0x180019cf0`

## callees

- `0x180010910`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010938`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010938`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010956`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800109ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010956`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800109ac`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_18004DDDC;
  if ( !dword_18004DDDC )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_18004DDE0 )
      {
        v1 = dword_18004DDDC;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_18004DDE0 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_18004DDE0,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_18004DDE0 )
      {
        v1 = 1;
        dword_18004DDDC = 1;
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
0x180010910  push    rbx
0x180010912  sub     rsp, 20h
0x180010916  mov     ebx, cs:dword_18004DDDC
0x18001091c  nop
0x18001091d  test    ebx, ebx
0x18001091f  jnz     loc_1800109B4
0x180010925  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, bl; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001092b  jz      loc_1800109B2
0x180010931  lea     rcx, SRWLock; SRWLock
0x180010938  call    cs:__imp_AcquireSRWLockExclusive
0x18001093e  cmp     cs:qword_18004DDE0, 0
0x180010946  jz      short loc_18001095E
0x180010948  mov     ebx, cs:dword_18004DDDC
0x18001094e  nop
0x18001094f  lea     rcx, SRWLock; SRWLock
0x180010956  call    cs:__imp_ReleaseSRWLockExclusive
0x18001095c  jmp     short loc_1800109B4
0x18001095e  mov     cs:qword_18004DDE0, 0
0x180010969  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180010970  test    rax, rax
0x180010973  jnz     short loc_180010981
0x180010975  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18001097c  test    rax, rax
0x18001097f  jz      short loc_18001099B
0x180010981  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180010988  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18001098f  lea     rcx, qword_18004DDE0
0x180010996  call    _guard_dispatch_icall
0x18001099b  lea     rcx, SRWLock; SRWLock
0x1800109a2  cmp     cs:qword_18004DDE0, 0
0x1800109aa  jnz     short loc_1800109BC
0x1800109ac  call    cs:__imp_ReleaseSRWLockExclusive
0x1800109b2  xor     ebx, ebx
0x1800109b4  mov     eax, ebx
0x1800109b6  add     rsp, 20h
0x1800109ba  pop     rbx
0x1800109bb  retn
0x1800109bc  nop
0x1800109bd  mov     ebx, 1
0x1800109c2  mov     cs:dword_18004DDDC, ebx
0x1800109c8  jmp     short loc_180010956
```
