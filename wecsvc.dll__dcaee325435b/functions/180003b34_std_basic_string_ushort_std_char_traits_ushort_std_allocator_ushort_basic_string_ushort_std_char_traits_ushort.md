# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x180003b34`
- end: `0x180003b3e`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `10`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `60`
- callee_count: `1`
- tags: ``

## callers

- `0x1800205f0`
- `0x180020680`
- `0x180020758`
- `0x1800209b1`
- `0x1800209f9`
- `0x180020d6b`
- `0x180020d81`
- `0x180020d97`
- `0x180020db0`
- `0x180020dc9`
- `0x180020de2`
- `0x180020dfb`
- `0x180020e38`
- `0x180020e79`
- `0x180020f8d`
- `0x18002103b`
- `0x18002104d`
- `0x180021071`
- `0x180021095`
- `0x1800210a7`
- `0x1800210b9`
- `0x1800210ef`
- `0x180021137`
- `0x180021293`
- `0x1800212b7`
- `0x1800212c9`
- `0x1800212db`
- `0x1800212ed`
- `0x1800212ff`
- `0x180021311`
- `0x180021323`
- `0x180021335`
- `0x180021347`
- `0x180021359`
- `0x18002136b`
- `0x18002145a`
- `0x180021562`
- `0x180021574`
- `0x18002168e`
- `0x1800216cc`
- `0x180021714`
- `0x18002180e`
- `0x1800219ec`
- `0x1800219fe`
- `0x180021e85`
- `0x180022077`
- `0x180022210`
- `0x1800222c0`
- `0x180022334`
- `0x1800223b6`

## callees

- `0x1800062d4`

## pseudocode

```c
__int64 __fastcall std::wstring::~wstring(__int64 a1, __int64 a2)
{
  LOBYTE(a2) = 1;
  return std::wstring::_Tidy(a1, a2, 0);
}

```

## disassembly

```asm
0x180003b34  xor     r8d, r8d
0x180003b37  mov     dl, 1
0x180003b39  jmp     ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
```
