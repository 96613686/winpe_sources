# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x1800044d0`
- end: `0x1800044f0`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180004288`
- `0x1800043e4`

## callees

- `0x1800044d0`
- `0x18000458c`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  __int64 result; // rax

  result = (unsigned int)dword_1800268F4;
  if ( !dword_1800268F4 )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((RTL_SRWLOCK *)wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x1800044d0  sub     rsp, 28h
0x1800044d4  mov     eax, cs:dword_1800268F4
0x1800044da  nop
0x1800044db  test    eax, eax
0x1800044dd  jnz     short loc_1800044EB
0x1800044df  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x1800044e6  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x1800044eb  add     rsp, 28h
0x1800044ef  retn
```
