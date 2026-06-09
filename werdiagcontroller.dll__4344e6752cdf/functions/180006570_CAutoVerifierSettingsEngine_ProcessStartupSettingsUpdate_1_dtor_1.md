# _CAutoVerifierSettingsEngine::ProcessStartupSettingsUpdate_::_1_::dtor$1

- ea: `0x180006570`
- end: `0x18000657c`
- name: `_CAutoVerifierSettingsEngine::ProcessStartupSettingsUpdate_::_1_::dtor$1`
- size: `12`
- prototype: `NTSTATUS __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x1800021d8`

## pseudocode

```c
NTSTATUS __fastcall CAutoVerifierSettingsEngine::ProcessStartupSettingsUpdate_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&long NtClose(void *),0>>::~unique_any<tlx::handle_traits<void *,long (*)(void *),&long NtClose(void *),0>>((void **)(a2 + 728));
}

```

## disassembly

```asm
0x180006570  lea     rcx, [rdx+2D8h]
0x180006577  jmp     ??1?$unique_any@U?$handle_traits@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&NtClose(void *),0>>::~unique_any<tlx::handle_traits<void *,long (*)(void *),&NtClose(void *),0>>(void)
```
