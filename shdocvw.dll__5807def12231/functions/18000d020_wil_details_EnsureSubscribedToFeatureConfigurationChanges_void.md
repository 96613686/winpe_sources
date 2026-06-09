# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18000d020`
- end: `0x18000d040`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `24`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800027a0`
- `0x18000d3f0`
- `0x18000d4d0`
- `0x18000d630`
- `0x18000d790`
- `0x18000d930`
- `0x18000da10`
- `0x18000db70`
- `0x18000dcd0`
- `0x18000de30`
- `0x18000df90`
- `0x18000e070`
- `0x18000e150`
- `0x18000e230`
- `0x18000e310`
- `0x18000e3f0`
- `0x18000e4d0`
- `0x180015fc4`
- `0x180016164`
- `0x180016244`
- `0x1800163a0`
- `0x180016480`
- `0x180016560`
- `0x180022bf8`

## callees

- `0x18000d020`
- `0x18000d048`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_18003855C;
  if ( !dword_18003855C )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x18000d020  sub     rsp, 28h
0x18000d024  mov     eax, cs:dword_18003855C
0x18000d02a  nop
0x18000d02b  test    eax, eax
0x18000d02d  jnz     short loc_18000D03B
0x18000d02f  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18000d036  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x18000d03b  add     rsp, 28h
0x18000d03f  retn
```
