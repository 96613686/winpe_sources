# __imp_load_CMP_WaitNoPendingInstallEvents

- ea: `0x18001badb`
- end: `0x18001bae7`
- name: `__imp_load_CMP_WaitNoPendingInstallEvents`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x18001ba38`

## import_xrefs

- `CFGMGR32!CMP_WaitNoPendingInstallEvents` at `0x18001badb`

## pseudocode

```c
__int64 load_CMP_WaitNoPendingInstallEvents()
{
  return _tailMerge_cfgmgr32_dll();
}

```

## disassembly

```asm
0x18001badb  lea     rax, __imp_CMP_WaitNoPendingInstallEvents
0x18001bae2  jmp     __tailMerge_cfgmgr32_dll
```
