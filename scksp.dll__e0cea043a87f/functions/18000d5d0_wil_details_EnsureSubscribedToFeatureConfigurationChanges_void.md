# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18000d5d0`
- end: `0x18000d5f0`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000da28`
- `0x18000db08`
- `0x18000dbe8`
- `0x18000ec7c`

## callees

- `0x18000d5d0`
- `0x18000d5f8`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_18004B59C;
  if ( !dword_18004B59C )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x18000d5d0  sub     rsp, 28h
0x18000d5d4  mov     eax, cs:dword_18004B59C
0x18000d5da  nop
0x18000d5db  test    eax, eax
0x18000d5dd  jnz     short loc_18000D5EB
0x18000d5df  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18000d5e6  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x18000d5eb  add     rsp, 28h
0x18000d5ef  retn
```
