# std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ActionPlugin,std::default_delete<ActionPlugin>>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ActionPlugin,std::default_delete<ActionPlugin>>>,void *>>>(void)

- ea: `0x1800188d8`
- end: `0x1800188f4`
- name: `??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x18002761a`
- `0x18002793d`

## callees

- `0x180003304`
- `0x1800188d8`

## pseudocode

```c
void __fastcall std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>,void *>>>(
        __int64 a1)
{
  void *v1; // rcx

  v1 = *(void **)(a1 + 8);
  if ( v1 )
    operator delete(v1, 0x38u);
}

```

## disassembly

```asm
0x1800188d8  sub     rsp, 28h
0x1800188dc  mov     rcx, [rcx+8]; void *
0x1800188e0  test    rcx, rcx
0x1800188e3  jz      short loc_1800188EF
0x1800188e5  mov     edx, 38h ; '8'; unsigned __int64
0x1800188ea  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800188ef  add     rsp, 28h
0x1800188f3  retn
```
