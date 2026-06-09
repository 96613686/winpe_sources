# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x180010914`
- end: `0x18001091e`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `10`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18001d714`
- `0x18001d890`
- `0x18001d8a2`
- `0x18001d8d8`
- `0x18001d920`
- `0x18001da8f`
- `0x18001daa1`

## callees

- `0x1800134bc`

## pseudocode

```c
__int64 __fastcall std::wstring::~wstring(void **a1)
{
  return std::wstring::_Tidy(a1, 1, 0);
}

```

## disassembly

```asm
0x180010914  xor     r8d, r8d
0x180010917  mov     dl, 1
0x180010919  jmp     ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
```
