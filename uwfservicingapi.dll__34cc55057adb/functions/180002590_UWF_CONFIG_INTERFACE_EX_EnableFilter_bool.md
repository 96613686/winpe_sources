# UWF_CONFIG_INTERFACE_EX::EnableFilter(bool)

- ea: `0x180002590`
- end: `0x180002599`
- name: `?EnableFilter@UWF_CONFIG_INTERFACE_EX@@UEAAJ_N@Z`
- size: `9`
- prototype: `int __fastcall(UWF_CONFIG_INTERFACE_EX *this, bool)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `uwfcfgmgmt!UwfCfgSetFilterEnabled` at `0x180002592`

## pseudocode

```c
int __fastcall UWF_CONFIG_INTERFACE_EX::EnableFilter(UWF_CONFIG_INTERFACE_EX *this, bool a2)
{
  return UwfCfgSetFilterEnabled(a2);
}

```

## disassembly

```asm
0x180002590  mov     cl, dl
0x180002592  jmp     cs:__imp_?UwfCfgSetFilterEnabled@@YAJ_N@Z; UwfCfgSetFilterEnabled(bool)
```
