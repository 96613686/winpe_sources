# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180007f30`
- end: `0x180007f51`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `33`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800082f0`
- `0x180008438`
- `0x180008580`
- `0x1800086c8`
- `0x180009458`

## callees

- `0x180007f30`
- `0x180007f58`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_180022304;
  if ( !dword_180022304 )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x180007f30  sub     rsp, 28h
0x180007f34  mov     eax, cs:dword_180022304
0x180007f3a  nop
0x180007f3b  test    eax, eax
0x180007f3d  jnz     short loc_180007F4B
0x180007f3f  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180007f46  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x180007f4b  add     rsp, 28h
0x180007f4f  retn
```
