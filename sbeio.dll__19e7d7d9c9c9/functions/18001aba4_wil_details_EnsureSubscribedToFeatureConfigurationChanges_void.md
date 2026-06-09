# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18001aba4`
- end: `0x18001abc4`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `10`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001b090`
- `0x18001b184`
- `0x18001b278`
- `0x18001b36c`
- `0x18001b460`
- `0x18001b554`
- `0x18001b648`
- `0x18001b73c`
- `0x18001b830`
- `0x18001b924`

## callees

- `0x18001aba4`
- `0x18001abcc`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_180032214;
  if ( !dword_180032214 )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x18001aba4  sub     rsp, 28h
0x18001aba8  mov     eax, cs:dword_180032214
0x18001abae  nop
0x18001abaf  test    eax, eax
0x18001abb1  jnz     short loc_18001ABBF
0x18001abb3  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18001abba  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x18001abbf  add     rsp, 28h
0x18001abc3  retn
```
