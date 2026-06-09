# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18000bccc`
- end: `0x18000bcec`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800148a8`
- `0x180014a0c`

## callees

- `0x18000bccc`
- `0x18000bcf4`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_18001F79C;
  if ( !dword_18001F79C )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x18000bccc  sub     rsp, 28h
0x18000bcd0  mov     eax, cs:dword_18001F79C
0x18000bcd6  nop
0x18000bcd7  test    eax, eax
0x18000bcd9  jnz     short loc_18000BCE7
0x18000bcdb  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18000bce2  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ
0x18000bce7  add     rsp, 28h
0x18000bceb  retn
```
