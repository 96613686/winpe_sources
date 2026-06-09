# utl::vector<utl::unique_ptr<BinXmlExtractor::AttributePathNode,utl::default_delete<BinXmlExtractor::AttributePathNode>>,utl::allocator<utl::unique_ptr<BinXmlExtractor::AttributePathNode,utl::default_delete<BinXmlExtractor::AttributePathNode>>>>::_Uninit(void)

- ea: `0x1800201fc`
- end: `0x180020230`
- name: `?_Uninit@?$vector@V?$unique_ptr@UAttributePathNode@BinXmlExtractor@@U?$default_delete@UAttributePathNode@BinXmlExtractor@@@utl@@@utl@@V?$allocator@V?$unique_ptr@UAttributePathNode@BinXmlExtractor@@U?$default_delete@UAttributePathNode@BinXmlExtractor@@@utl@@@utl@@@2@@utl@@AEAAXXZ`
- size: `52`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x18000cee0`
- `0x18000cf20`
- `0x18001a4dc`
- `0x180020154`

## callees

- `0x18000a100`
- `0x1800201fc`
- `0x180020238`

## pseudocode

```c
void __fastcall utl::vector<utl::unique_ptr<BinXmlExtractor::AttributePathNode,utl::default_delete<BinXmlExtractor::AttributePathNode>>,utl::allocator<utl::unique_ptr<BinXmlExtractor::AttributePathNode,utl::default_delete<BinXmlExtractor::AttributePathNode>>>>::_Uninit(
        __int64 a1)
{
  void *v1; // rdx
  __int64 v3; // r8

  v1 = *(void **)a1;
  if ( *(_QWORD *)a1 != -1 )
  {
    v3 = *(_QWORD *)(a1 + 8) - (_QWORD)v1;
    *(_QWORD *)(a1 + 8) = v1;
    utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<BinXmlExtractor::AttributePathNode,utl::default_delete<BinXmlExtractor::AttributePathNode>>>>(
      a1,
      v1,
      v3 >> 3);
    operator delete(*(void **)a1);
  }
}

```

## disassembly

```asm
0x1800201fc  push    rbx
0x1800201fe  sub     rsp, 20h
0x180020202  mov     rdx, [rcx]
0x180020205  mov     rbx, rcx
0x180020208  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18002020c  jz      short loc_18002022A
0x18002020e  mov     r8, [rcx+8]
0x180020212  sub     r8, rdx
0x180020215  mov     [rcx+8], rdx
0x180020219  sar     r8, 3
0x18002021d  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@UAttributePathNode@BinXmlExtractor@@U?$default_delete@UAttributePathNode@BinXmlExtractor@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@UAttributePathNode@BinXmlExtractor@@U?$default_delete@UAttributePathNode@BinXmlExtractor@@@utl@@@utl@@@0@PEAV?$unique_ptr@UAttributePathNode@BinXmlExtractor@@U?$default_delete@UAttributePathNode@BinXmlExtractor@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<BinXmlExtractor::AttributePathNode,utl::default_delete<BinXmlExtractor::AttributePathNode>>>>(utl::allocator<utl::unique_ptr<BinXmlExtractor::AttributePathNode,utl::default_delete<BinXmlExtractor::AttributePathNode>>> &,utl::unique_ptr<BinXmlExtractor::AttributePathNode,utl::default_delete<BinXmlExtractor::AttributePathNode>> *,unsigned __int64)
0x180020222  mov     rcx, [rbx]; void *
0x180020225  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002022a  add     rsp, 20h
0x18002022e  pop     rbx
0x18002022f  retn
```
