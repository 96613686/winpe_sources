# UWF_CONFIG_INTERFACE_EX::CommitHklmValueByName(ushort const *,ushort const *)

- ea: `0x180002580`
- end: `0x180002589`
- name: `?CommitHklmValueByName@UWF_CONFIG_INTERFACE_EX@@UEAAJPEBG0@Z`
- size: `9`
- prototype: `int __fastcall(UWF_CONFIG_INTERFACE_EX *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `uwfcfgmgmt!UwfCfgCommitRegistry` at `0x180002582`

## pseudocode

```c
int __fastcall UWF_CONFIG_INTERFACE_EX::CommitHklmValueByName(
        UWF_CONFIG_INTERFACE_EX *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  return UwfCfgCommitRegistry(1, a2, a3);
}

```

## disassembly

```asm
0x180002580  mov     cl, 1
0x180002582  jmp     cs:__imp_?UwfCfgCommitRegistry@@YAJ_NPEBG1@Z; UwfCfgCommitRegistry(bool,ushort const *,ushort const *)
```
