# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18000cdac`
- end: `0x18000cdcd`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `33`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `10`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000dbec`
- `0x180015660`
- `0x180015754`
- `0x180015848`
- `0x18001593c`
- `0x180015a30`
- `0x180015b24`
- `0x180015c18`
- `0x180015d0c`
- `0x18001c034`

## callees

- `0x18000cdac`
- `0x18000cdd4`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_18002A3C4;
  if ( !dword_18002A3C4 )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x18000cdac  sub     rsp, 28h
0x18000cdb0  mov     eax, cs:dword_18002A3C4
0x18000cdb6  nop
0x18000cdb7  test    eax, eax
0x18000cdb9  jnz     short loc_18000CDC7
0x18000cdbb  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18000cdc2  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x18000cdc7  add     rsp, 28h
0x18000cdcb  retn
```
