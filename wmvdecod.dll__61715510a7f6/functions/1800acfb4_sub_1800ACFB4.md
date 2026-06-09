# sub_1800ACFB4

- ea: `0x1800acfb4`
- end: `0x1800acfc0`
- name: `sub_1800ACFB4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800acf11`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegSetValueA` at `0x1800acfb4`

## pseudocode

```c
__int64 sub_1800ACFB4()
{
  return sub_1800ACF11();
}

```

## disassembly

```asm
0x1800acfb4  lea     rax, RegSetValueA
0x1800acfbb  jmp     sub_1800ACF11
```
