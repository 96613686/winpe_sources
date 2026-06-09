# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18001403c`
- end: `0x18001405c`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `13`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001420c`
- `0x18001ad9c`
- `0x18001ae7c`
- `0x18001af5c`
- `0x18001b03c`
- `0x18001b11c`
- `0x18001b1fc`
- `0x18001b2dc`
- `0x18001b3bc`
- `0x18001b49c`
- `0x18001b57c`
- `0x18001b65c`
- `0x18001b73c`

## callees

- `0x18001403c`
- `0x180014064`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_18002C3BC;
  if ( !dword_18002C3BC )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x18001403c  sub     rsp, 28h
0x180014040  mov     eax, cs:dword_18002C3BC
0x180014046  nop
0x180014047  test    eax, eax
0x180014049  jnz     short loc_180014057
0x18001404b  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180014052  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ
0x180014057  add     rsp, 28h
0x18001405b  retn
```
