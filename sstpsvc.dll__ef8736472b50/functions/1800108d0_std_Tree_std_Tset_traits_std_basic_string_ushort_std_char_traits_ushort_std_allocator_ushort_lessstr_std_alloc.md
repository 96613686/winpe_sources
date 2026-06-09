# std::_Tree<std::_Tset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,_lessstr,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::~_Tree<std::_Tset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,_lessstr,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>(void)

- ea: `0x1800108d0`
- end: `0x1800108f3`
- name: `??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ`
- size: `35`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180010930`
- `0x180010d80`
- `0x180014900`
- `0x180015500`

## callees

- `0x180013498`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800108e7`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>(
        __int64 a1)
{
  std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Tidy();
  operator delete(*(void **)(a1 + 8));
}

```

## disassembly

```asm
0x1800108d0  push    rbx
0x1800108d2  sub     rsp, 20h
0x1800108d6  mov     rbx, rcx
0x1800108d9  call    ?_Tidy@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Tidy(void)
0x1800108de  mov     rcx, [rbx+8]
0x1800108e2  add     rsp, 20h
0x1800108e6  pop     rbx
0x1800108e7  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
