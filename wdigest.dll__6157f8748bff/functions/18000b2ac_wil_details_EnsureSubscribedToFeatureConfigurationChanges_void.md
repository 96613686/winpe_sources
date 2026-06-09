# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18000b2ac`
- end: `0x18000b2cc`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000ad50`
- `0x18000d700`

## callees

- `0x18000b2ac`
- `0x1800149e4`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_18004673C;
  if ( !dword_18004673C )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x18000b2ac  sub     rsp, 28h
0x18000b2b0  mov     eax, cs:dword_18004673C
0x18000b2b6  nop
0x18000b2b7  test    eax, eax
0x18000b2b9  jnz     short loc_18000B2C7
0x18000b2bb  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18000b2c2  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x18000b2c7  add     rsp, 28h
0x18000b2cb  retn
```
