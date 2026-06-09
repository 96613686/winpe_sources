# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x140005090`
- end: `0x14000514b`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `187`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140009c30`
- `0x14000a14c`
- `0x140013764`
- `0x140014094`
- `0x140014378`
- `0x140014674`
- `0x14001a220`

## callees

- `0x140005090`
- `0x1400206e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400050d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000512c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400050d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000512c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400050b8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400050b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_14002E5AC;
  if ( !dword_14002E5AC )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_14002E5B0 )
      {
        v1 = dword_14002E5AC;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_14002E5B0 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_14002E5B0,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_14002E5B0 )
      {
        v1 = 1;
        dword_14002E5AC = 1;
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
0x140005090  push    rbx
0x140005092  sub     rsp, 20h
0x140005096  mov     ebx, cs:dword_14002E5AC
0x14000509c  nop
0x14000509d  test    ebx, ebx
0x14000509f  jnz     loc_140005134
0x1400050a5  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, bl; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1400050ab  jz      loc_140005132
0x1400050b1  lea     rcx, SRWLock; SRWLock
0x1400050b8  call    cs:__imp_AcquireSRWLockExclusive
0x1400050be  cmp     cs:qword_14002E5B0, 0
0x1400050c6  jz      short loc_1400050DE
0x1400050c8  mov     ebx, cs:dword_14002E5AC
0x1400050ce  nop
0x1400050cf  lea     rcx, SRWLock; SRWLock
0x1400050d6  call    cs:__imp_ReleaseSRWLockExclusive
0x1400050dc  jmp     short loc_140005134
0x1400050de  mov     cs:qword_14002E5B0, 0
0x1400050e9  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1400050f0  test    rax, rax
0x1400050f3  jnz     short loc_140005101
0x1400050f5  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1400050fc  test    rax, rax
0x1400050ff  jz      short loc_14000511B
0x140005101  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140005108  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x14000510f  lea     rcx, qword_14002E5B0
0x140005116  call    _guard_dispatch_icall
0x14000511b  lea     rcx, SRWLock; SRWLock
0x140005122  cmp     cs:qword_14002E5B0, 0
0x14000512a  jnz     short loc_14000513C
0x14000512c  call    cs:__imp_ReleaseSRWLockExclusive
0x140005132  xor     ebx, ebx
0x140005134  mov     eax, ebx
0x140005136  add     rsp, 20h
0x14000513a  pop     rbx
0x14000513b  retn
0x14000513c  nop
0x14000513d  mov     ebx, 1
0x140005142  mov     cs:dword_14002E5AC, ebx
0x140005148  jmp     short loc_1400050D6
```
