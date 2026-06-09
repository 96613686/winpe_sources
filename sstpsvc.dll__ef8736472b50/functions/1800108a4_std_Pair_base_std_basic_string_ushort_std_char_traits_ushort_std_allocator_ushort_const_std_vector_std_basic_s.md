# std::_Pair_base<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>::~_Pair_base<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>(void)

- ea: `0x1800108a4`
- end: `0x1800108c8`
- name: `??1?$_Pair_base@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@QEAA@XZ`
- size: `36`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800085a4`
- `0x180010924`
- `0x180010b08`
- `0x180013da0`

## callees

- `0x1800134bc`
- `0x180013524`

## pseudocode

```c
__int64 __fastcall std::_Pair_base<std::wstring const,std::vector<std::wstring>>::~_Pair_base<std::wstring const,std::vector<std::wstring>>(
        void **a1)
{
  std::vector<std::wstring>::_Tidy(a1 + 5);
  return std::wstring::_Tidy(a1, 1, 0);
}

```

## disassembly

```asm
0x1800108a4  push    rbx
0x1800108a6  sub     rsp, 20h
0x1800108aa  mov     rbx, rcx
0x1800108ad  add     rcx, 28h ; '('
0x1800108b1  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800108b6  xor     r8d, r8d
0x1800108b9  mov     dl, 1
0x1800108bb  mov     rcx, rbx
0x1800108be  add     rsp, 20h
0x1800108c2  pop     rbx
0x1800108c3  jmp     ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
```
