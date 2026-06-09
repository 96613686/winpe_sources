# std::_Tree_alloc<0,std::_Tree_base_types<std::pair<ATL::CComBSTR const,CWbemDispID>,CWbemAllocator<CWbemDispID>>>::_Buyheadnode(void)

- ea: `0x180019d94`
- end: `0x180019dce`
- name: `?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBVCComBSTR@ATL@@VCWbemDispID@@@std@@V?$CWbemAllocator@VCWbemDispID@@@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@VCWbemDispID@@@std@@PEAX@2@XZ`
- size: `58`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006850`
- `0x180009320`
- `0x180013950`

## callees

- `0x180019d94`
- `0x18001a848`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180019da2`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180019da2`

## pseudocode

```c
_QWORD *std::_Tree_alloc<0,std::_Tree_base_types<std::pair<ATL::CComBSTR const,CWbemDispID>,CWbemAllocator<CWbemDispID>>>::_Buyheadnode()
{
  _QWORD *result; // rax

  result = CWin32DefaultArena::WbemMemAlloc(0x38u);
  if ( !result )
    std::_Xbad_alloc();
  *result = result;
  result[1] = result;
  result[2] = result;
  *((_WORD *)result + 12) = 257;
  return result;
}

```

## disassembly

```asm
0x180019d94  mov     [rsp+arg_0], rcx
0x180019d99  sub     rsp, 28h
0x180019d9d  mov     ecx, 38h ; '8'
0x180019da2  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180019da8  mov     [rsp+28h+arg_0], rax
0x180019dad  test    rax, rax
0x180019db0  jnz     short loc_180019DB8
0x180019db2  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180019db8  mov     [rax], rax
0x180019dbb  mov     [rax+8], rax
0x180019dbf  mov     [rax+10h], rax
0x180019dc3  mov     word ptr [rax+18h], 101h
0x180019dc9  add     rsp, 28h
0x180019dcd  retn
```
