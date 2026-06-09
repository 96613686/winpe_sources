# sub_1800ACFA2

- ea: `0x1800acfa2`
- end: `0x1800acfae`
- name: `sub_1800ACFA2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800acf11`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x1800acfa2`

## pseudocode

```c
__int64 sub_1800ACFA2()
{
  return sub_1800ACF11();
}

```

## disassembly

```asm
0x1800acfa2  lea     rax, RegCreateKeyW
0x1800acfa9  jmp     sub_1800ACF11
```
