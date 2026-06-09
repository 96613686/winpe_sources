# WcmCommon::Xml::Node::Node(WcmCommon::Xml::Details::Node const &)

- ea: `0x180028be8`
- end: `0x180028c83`
- name: `??0Node@Xml@WcmCommon@@AEAA@AEBU0Details@12@@Z`
- size: `155`
- prototype: `WcmCommon::Xml::Node *__fastcall(WcmCommon::Xml::Node *this, const struct Node *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028998`
- `0x180029740`

## callees

- `0x1800029c0`
- `0x180028be8`
- `0x180033010`

## pseudocode

```c
WcmCommon::Xml::Node *__fastcall WcmCommon::Xml::Node::Node(WcmCommon::Xml::Node *this, const struct Node *a2)
{
  struct Node *v4; // rsi
  struct NodeVtbl *lpVtbl; // rcx
  _DWORD *v7; // [rsp+30h] [rbp+8h]

  v4 = (struct Node *)operator new(8u);
  lpVtbl = a2->lpVtbl;
  v4->lpVtbl = a2->lpVtbl;
  if ( lpVtbl )
    (*((void (__fastcall **)(struct NodeVtbl *))lpVtbl->QueryInterface + 1))(lpVtbl);
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  v7 = operator new(0x18u);
  *(_OWORD *)v7 = 0;
  v7[2] = 1;
  v7[3] = 1;
  *(_QWORD *)v7 = &std::_Ref_count<WcmCommon::Xml::Details::Node>::`vftable';
  *((_QWORD *)v7 + 2) = v4;
  *(_QWORD *)this = v4;
  *((_QWORD *)this + 1) = v7;
  return this;
}

```

## disassembly

```asm
0x180028be8  mov     [rsp+arg_8], rbx
0x180028bed  mov     [rsp+arg_10], rsi
0x180028bf2  mov     [rsp+arg_0], rcx
0x180028bf7  push    rdi
0x180028bf8  sub     rsp, 20h
0x180028bfc  mov     rbx, rdx
0x180028bff  mov     rdi, rcx
0x180028c02  mov     ecx, 8; Size
0x180028c07  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180028c0c  mov     rsi, rax
0x180028c0f  mov     rcx, [rbx]
0x180028c12  mov     [rax], rcx
0x180028c15  test    rcx, rcx
0x180028c18  jz      short loc_180028C27
0x180028c1a  mov     rdx, [rcx]
0x180028c1d  mov     rax, [rdx+8]
0x180028c21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c26  nop
0x180028c27  mov     qword ptr [rdi], 0
0x180028c2e  mov     qword ptr [rdi+8], 0
0x180028c36  mov     [rsp+28h+arg_0], rsi
0x180028c3b  mov     ecx, 18h; Size
0x180028c40  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180028c45  mov     [rsp+28h+arg_0], rax
0x180028c4a  xorps   xmm0, xmm0
0x180028c4d  movups  xmmword ptr [rax], xmm0
0x180028c50  mov     ecx, 1
0x180028c55  mov     [rax+8], ecx
0x180028c58  mov     [rax+0Ch], ecx
0x180028c5b  lea     rcx, ??_7?$_Ref_count@UNode@Details@Xml@WcmCommon@@@std@@6B@; const std::_Ref_count<WcmCommon::Xml::Details::Node>::`vftable'
0x180028c62  mov     [rax], rcx
0x180028c65  mov     [rax+10h], rsi
0x180028c69  mov     [rdi], rsi
0x180028c6c  mov     [rdi+8], rax
0x180028c70  mov     rax, rdi
0x180028c73  mov     rbx, [rsp+28h+arg_8]
0x180028c78  mov     rsi, [rsp+28h+arg_10]
0x180028c7d  add     rsp, 20h
0x180028c81  pop     rdi
0x180028c82  retn
```
