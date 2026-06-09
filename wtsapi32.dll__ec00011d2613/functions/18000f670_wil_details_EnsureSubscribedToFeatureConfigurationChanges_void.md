# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18000f670`
- end: `0x18000f690`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000f7b8`
- `0x18000f8a0`
- `0x18000f9fc`
- `0x1800128d0`

## callees

- `0x18000f670`
- `0x18000f698`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_18001FB9C;
  if ( !dword_18001FB9C )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x18000f670  sub     rsp, 28h
0x18000f674  mov     eax, cs:dword_18001FB9C
0x18000f67a  nop
0x18000f67b  test    eax, eax
0x18000f67d  jnz     short loc_18000F68B
0x18000f67f  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18000f686  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ
0x18000f68b  add     rsp, 28h
0x18000f68f  retn
```
