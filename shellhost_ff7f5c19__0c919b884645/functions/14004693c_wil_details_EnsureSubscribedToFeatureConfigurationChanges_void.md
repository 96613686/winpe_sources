# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x14004693c`
- end: `0x14004695c`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `15`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140047ac0`
- `0x140055514`
- `0x1400556bc`
- `0x1400557a4`
- `0x14005588c`
- `0x1400559f4`
- `0x140055adc`
- `0x140055bc4`
- `0x140055cac`
- `0x140055d94`
- `0x140055e7c`
- `0x140055f64`
- `0x14005604c`
- `0x1400561ac`
- `0x140056294`

## callees

- `0x14004693c`
- `0x140046964`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_1400841F4;
  if ( !dword_1400841F4 )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x14004693c  sub     rsp, 28h
0x140046940  mov     eax, cs:dword_1400841F4
0x140046946  nop
0x140046947  test    eax, eax
0x140046949  jnz     short loc_140046957
0x14004694b  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x140046952  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x140046957  add     rsp, 28h
0x14004695b  retn
```
