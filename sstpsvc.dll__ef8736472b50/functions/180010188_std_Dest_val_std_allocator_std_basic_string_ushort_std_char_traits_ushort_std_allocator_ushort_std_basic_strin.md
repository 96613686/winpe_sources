# std::_Dest_val<std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180010188`
- end: `0x180010195`
- name: `??$_Dest_val@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@std@@YAXAEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z`
- size: `13`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180010998`
- `0x180012c68`
- `0x180012f50`
- `0x1800130d0`
- `0x180013524`
- `0x1800137d4`
- `0x180013a24`
- `0x180014168`
- `0x18001d753`

## callees

- `0x1800134bc`

## pseudocode

```c
__int64 __fastcall std::_Dest_val<std::allocator<std::wstring>,std::wstring>(__int64 a1, void **a2)
{
  return std::wstring::_Tidy(a2, 1, 0);
}

```

## disassembly

```asm
0x180010188  mov     rcx, rdx
0x18001018b  xor     r8d, r8d
0x18001018e  mov     dl, 1
0x180010190  jmp     ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
```
