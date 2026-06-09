# GenericTable<HTTP2ServerCookie,0,&DefaultCompareKeys<HTTP2Cookie>(HTTP2Cookie const &,HTTP2Cookie const &)>::Allocate(_RTL_AVL_TABLE *,ulong)

- ea: `0x180004470`
- end: `0x18000447d`
- name: `?Allocate@?$GenericTable@VHTTP2ServerCookie@@$0A@$1??$DefaultCompareKeys@VHTTP2Cookie@@@@YAHAEBVHTTP2Cookie@@0@Z@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z`
- size: `13`
- prototype: `RTL_AVL_ALLOCATE_ROUTINE`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
struct _RTL_BALANCED_LINKS *__fastcall GenericTable<HTTP2ServerCookie,0,&int DefaultCompareKeys<HTTP2Cookie>(HTTP2Cookie const &,HTTP2Cookie const &)>::Allocate(
        struct _RTL_AVL_TABLE *Table,
        CLONG ByteSize)
{
  struct _RTL_BALANCED_LINKS *result; // rax

  result = Table[1].BalancedRoot.Parent;
  Table[1].BalancedRoot.Parent = 0;
  return result;
}

```

## disassembly

```asm
0x180004470  mov     rax, [rcx+68h]
0x180004474  mov     qword ptr [rcx+68h], 0
0x18000447c  retn
```
