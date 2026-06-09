# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x1800084c4`
- end: `0x1800084e4`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180009434`

## callees

- `0x1800084c4`
- `0x1800084ec`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_18001619C;
  if ( !dword_18001619C )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x1800084c4  sub     rsp, 28h
0x1800084c8  mov     eax, cs:dword_18001619C
0x1800084ce  nop
0x1800084cf  test    eax, eax
0x1800084d1  jnz     short loc_1800084DF
0x1800084d3  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x1800084da  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x1800084df  add     rsp, 28h
0x1800084e3  retn
```
