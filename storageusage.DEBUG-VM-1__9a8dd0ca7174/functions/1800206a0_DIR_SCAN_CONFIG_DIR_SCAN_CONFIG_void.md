# DIR_SCAN_CONFIG::~DIR_SCAN_CONFIG(void)

- ea: `0x1800206a0`
- end: `0x1800206a9`
- name: `??1DIR_SCAN_CONFIG@@QEAA@XZ`
- size: `9`
- prototype: `void __fastcall(DIR_SCAN_CONFIG *__hidden this)`
- caller_count: `20`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002b976`
- `0x18002b9be`
- `0x18002b9d0`
- `0x18002b9e2`
- `0x18002b9f4`
- `0x18002ba06`
- `0x18002ba18`
- `0x18002ba2a`
- `0x18002ba3c`
- `0x18002ba4e`
- `0x18002ba60`
- `0x18002ba72`
- `0x18002ba84`
- `0x18002ba96`
- `0x18002baa8`
- `0x18002baba`
- `0x18002bacc`
- `0x18002bade`
- `0x18002baf0`
- `0x18002bb02`

## callees

- `0x1800240d8`

## pseudocode

```c
void __fastcall DIR_SCAN_CONFIG::~DIR_SCAN_CONFIG(DIR_SCAN_CONFIG *this)
{
  std::vector<unsigned short const *>::_Tidy((char *)this + 48);
}

```

## disassembly

```asm
0x1800206a0  add     rcx, 30h ; '0'
0x1800206a4  jmp     ?_Tidy@?$vector@PEBGV?$allocator@PEBG@std@@@std@@AEAAXXZ; std::vector<ushort const *>::_Tidy(void)
```
