# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180007af4`
- end: `0x180007b14`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180007e98`
- `0x180007fd8`
- `0x180008118`
- `0x180008d48`

## callees

- `0x180007af4`
- `0x180007b1c`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_180021304;
  if ( !dword_180021304 )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x180007af4  sub     rsp, 28h
0x180007af8  mov     eax, cs:dword_180021304
0x180007afe  nop
0x180007aff  test    eax, eax
0x180007b01  jnz     short loc_180007B0F
0x180007b03  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180007b0a  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x180007b0f  add     rsp, 28h
0x180007b13  retn
```
