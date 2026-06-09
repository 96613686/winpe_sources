# _CAutoVerifierSettingsEngine::ProcessStartupSettingsUpdate_::_1_::dtor$3

- ea: `0x180006594`
- end: `0x1800065a0`
- name: `_CAutoVerifierSettingsEngine::ProcessStartupSettingsUpdate_::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x180002218`

## pseudocode

```c
void __fastcall CAutoVerifierSettingsEngine::ProcessStartupSettingsUpdate_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>::~unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>((void **)(a2 + 88));
}

```

## disassembly

```asm
0x180006594  lea     rcx, [rdx+58h]
0x18000659b  jmp     ??1?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@QEAA@XZ; utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>::~unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>(void)
```
