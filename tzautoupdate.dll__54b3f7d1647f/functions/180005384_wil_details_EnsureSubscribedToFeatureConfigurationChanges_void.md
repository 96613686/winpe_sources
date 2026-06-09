# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180005384`
- end: `0x1800053a4`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800057c4`
- `0x1800058a4`
- `0x180005984`
- `0x180006870`
- `0x180010e04`
- `0x180010ee4`

## callees

- `0x180005384`
- `0x1800053ac`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_180030A94;
  if ( !dword_180030A94 )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x180005384  sub     rsp, 28h
0x180005388  mov     eax, cs:dword_180030A94
0x18000538e  nop
0x18000538f  test    eax, eax
0x180005391  jnz     short loc_18000539F
0x180005393  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18000539a  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x18000539f  add     rsp, 28h
0x1800053a3  retn
```
