# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x180009ddc`
- end: `0x180009de1`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c21c`
- `0x18000c22e`
- `0x18000c240`
- `0x18000c252`
- `0x18000c264`
- `0x18000c276`
- `0x18000c288`
- `0x18000c29a`
- `0x18000c2ac`
- `0x18000c318`

## callees

- `0x18000a4d4`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall std::wstring::~wstring(__int64 a1)
{
  return std::wstring::_Tidy_deallocate(a1);
}

```

## disassembly

```asm
0x180009ddc  jmp     ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
```
