# utl::vector<utl::unique_ptr<BinXmlExtractor::ElementPathNode,utl::default_delete<BinXmlExtractor::ElementPathNode>>,utl::allocator<utl::unique_ptr<BinXmlExtractor::ElementPathNode,utl::default_delete<BinXmlExtractor::ElementPathNode>>>>::_Uninit(void)

- ea: `0x18002003c`
- end: `0x180020070`
- name: `?_Uninit@?$vector@V?$unique_ptr@UElementPathNode@BinXmlExtractor@@U?$default_delete@UElementPathNode@BinXmlExtractor@@@utl@@@utl@@V?$allocator@V?$unique_ptr@UElementPathNode@BinXmlExtractor@@U?$default_delete@UElementPathNode@BinXmlExtractor@@@utl@@@utl@@@2@@utl@@AEAAXXZ`
- size: `52`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x18000cee0`
- `0x18000cf20`
- `0x18001a4dc`
- `0x18001ff94`

## callees

- `0x18000a100`
- `0x18002003c`
- `0x180020078`

## pseudocode

```c
void __fastcall utl::vector<utl::unique_ptr<BinXmlExtractor::ElementPathNode,utl::default_delete<BinXmlExtractor::ElementPathNode>>,utl::allocator<utl::unique_ptr<BinXmlExtractor::ElementPathNode,utl::default_delete<BinXmlExtractor::ElementPathNode>>>>::_Uninit(
        __int64 a1)
{
  void *v1; // rdx
  __int64 v3; // r8

  v1 = *(void **)a1;
  if ( *(_QWORD *)a1 != -1 )
  {
    v3 = *(_QWORD *)(a1 + 8) - (_QWORD)v1;
    *(_QWORD *)(a1 + 8) = v1;
    utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<BinXmlExtractor::ElementPathNode,utl::default_delete<BinXmlExtractor::ElementPathNode>>>>(
      a1,
      v1,
      v3 >> 3);
    operator delete(*(void **)a1);
  }
}

```

## disassembly

```asm
0x18002003c  push    rbx
0x18002003e  sub     rsp, 20h
0x180020042  mov     rdx, [rcx]
0x180020045  mov     rbx, rcx
0x180020048  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18002004c  jz      short loc_18002006A
0x18002004e  mov     r8, [rcx+8]
0x180020052  sub     r8, rdx
0x180020055  mov     [rcx+8], rdx
0x180020059  sar     r8, 3
0x18002005d  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@UElementPathNode@BinXmlExtractor@@U?$default_delete@UElementPathNode@BinXmlExtractor@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@UElementPathNode@BinXmlExtractor@@U?$default_delete@UElementPathNode@BinXmlExtractor@@@utl@@@utl@@@0@PEAV?$unique_ptr@UElementPathNode@BinXmlExtractor@@U?$default_delete@UElementPathNode@BinXmlExtractor@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<BinXmlExtractor::ElementPathNode,utl::default_delete<BinXmlExtractor::ElementPathNode>>>>(utl::allocator<utl::unique_ptr<BinXmlExtractor::ElementPathNode,utl::default_delete<BinXmlExtractor::ElementPathNode>>> &,utl::unique_ptr<BinXmlExtractor::ElementPathNode,utl::default_delete<BinXmlExtractor::ElementPathNode>> *,unsigned __int64)
0x180020062  mov     rcx, [rbx]; void *
0x180020065  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002006a  add     rsp, 20h
0x18002006e  pop     rbx
0x18002006f  retn
```
