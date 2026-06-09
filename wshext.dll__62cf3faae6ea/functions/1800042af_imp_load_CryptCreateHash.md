# __imp_load_CryptCreateHash

- ea: `0x1800042af`
- end: `0x1800042bb`
- name: `__imp_load_CryptCreateHash`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003d4b`

## import_xrefs

- `ADVAPI32!CryptCreateHash` at `0x1800042af`

## pseudocode

```c
__int64 load_CryptCreateHash()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x1800042af  lea     rax, __imp_CryptCreateHash
0x1800042b6  jmp     __tailMerge_advapi32_dll
```
