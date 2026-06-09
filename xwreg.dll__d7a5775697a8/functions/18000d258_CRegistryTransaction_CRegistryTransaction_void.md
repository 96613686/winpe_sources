# CRegistryTransaction::~CRegistryTransaction(void)

- ea: `0x18000d258`
- end: `0x18000d263`
- name: `??1CRegistryTransaction@@QEAA@XZ`
- size: `11`
- prototype: `void __fastcall(CRegistryTransaction *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops, registry_config`

## callers

- `0x180012e66`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000d25c`

## pseudocode

```c
void __fastcall CRegistryTransaction::~CRegistryTransaction(const WCHAR *this)
{
  DeleteFileW(this + 4);
}

```

## disassembly

```asm
0x18000d258  add     rcx, 8
0x18000d25c  jmp     cs:__imp_DeleteFileW
```
