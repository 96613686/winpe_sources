# _CFciPropertiesShellExt::UpdateInformationControls_::_1_::dtor$0

- ea: `0x18001e152`
- end: `0x18001e15e`
- name: `_CFciPropertiesShellExt::UpdateInformationControls_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800022b8`

## pseudocode

```c
void __fastcall CFciPropertiesShellExt::UpdateInformationControls_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CSrmComBSTR::~CSrmComBSTR((BSTR *)(a2 + 112));
}

```

## disassembly

```asm
0x18001e152  lea     rcx, [rdx+70h]; this
0x18001e159  jmp     ??1CSrmComBSTR@@QEAA@XZ; CSrmComBSTR::~CSrmComBSTR(void)
```
