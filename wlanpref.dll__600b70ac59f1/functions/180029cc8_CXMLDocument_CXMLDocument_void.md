# CXMLDocument::~CXMLDocument(void)

- ea: `0x180029cc8`
- end: `0x180029cec`
- name: `??1CXMLDocument@@QEAA@XZ`
- size: `36`
- prototype: `void __fastcall(CXMLDocument *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c8a8`
- `0x18002efd7`

## callees

- `0x180003458`
- `0x180029cf4`
- `0x18002a510`

## pseudocode

```c
void __fastcall CXMLDocument::~CXMLDocument(CXMLDocument *this, struct IXMLDOMNode **a2)
{
  CXMLDocumentNode::Detach(this, a2);
  CXMLDocumentNode::~CXMLDocumentNode((CXMLDocument *)((char *)this + 8));
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this);
}

```

## disassembly

```asm
0x180029cc8  push    rbx
0x180029cca  sub     rsp, 20h
0x180029cce  mov     rbx, rcx
0x180029cd1  call    ?Detach@CXMLDocumentNode@@QEAAJPEAPEAUIXMLDOMNode@@@Z; CXMLDocumentNode::Detach(IXMLDOMNode * *)
0x180029cd6  lea     rcx, [rbx+8]; this
0x180029cda  call    ??1CXMLDocumentNode@@QEAA@XZ; CXMLDocumentNode::~CXMLDocumentNode(void)
0x180029cdf  mov     rcx, rbx
0x180029ce2  add     rsp, 20h
0x180029ce6  pop     rbx
0x180029ce7  jmp     ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
```
