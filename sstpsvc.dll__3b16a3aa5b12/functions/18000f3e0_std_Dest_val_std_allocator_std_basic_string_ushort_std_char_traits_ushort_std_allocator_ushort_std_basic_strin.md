# std::_Dest_val<std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x18000f3e0`
- end: `0x18000f3ed`
- name: `??$_Dest_val@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@std@@YAXAEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z`
- size: `13`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x18000fbb0`
- `0x180011ccc`
- `0x180011fa4`
- `0x18001211c`
- `0x180012560`
- `0x180012808`
- `0x180012a54`
- `0x18001317c`
- `0x18001c217`

## callees

- `0x1800124fc`

## pseudocode

```c
__int64 __fastcall std::_Dest_val<std::allocator<std::wstring>,std::wstring>(__int64 a1, void **a2)
{
  return std::wstring::_Tidy(a2, 1, 0);
}

```

## disassembly

```asm
0x18000f3e0  mov     rcx, rdx
0x18000f3e3  xor     r8d, r8d
0x18000f3e6  mov     dl, 1
0x18000f3e8  jmp     ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
```
