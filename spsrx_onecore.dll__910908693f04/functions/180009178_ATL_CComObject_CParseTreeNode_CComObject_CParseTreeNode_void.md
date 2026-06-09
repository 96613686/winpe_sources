# ATL::CComObject<CParseTreeNode>::~CComObject<CParseTreeNode>(void)

- ea: `0x180009178`
- end: `0x1800091b2`
- name: `??1?$CComObject@VCParseTreeNode@@@ATL@@UEAA@XZ`
- size: `58`
- prototype: `__int64 __fastcall(CParseTreeNode *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009520`

## callees

- `0x18000ee14`
- `0x180010010`

## pseudocode

```c
void __fastcall ATL::CComObject<CParseTreeNode>::~CComObject<CParseTreeNode>(CParseTreeNode *this)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CParseTreeNode>::`vftable';
  (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CParseTreeNode::~CParseTreeNode(this);
}

```

## disassembly

```asm
0x180009178  push    rbx
0x18000917a  sub     rsp, 20h
0x18000917e  mov     dword ptr [rcx+8], 0C0000001h
0x180009185  lea     rax, ??_7?$CComObject@VCParseTreeNode@@@ATL@@6B@; const ATL::CComObject<CParseTreeNode>::`vftable'
0x18000918c  mov     [rcx], rax
0x18000918f  mov     rbx, rcx
0x180009192  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009199  mov     rax, [rcx]
0x18000919c  mov     rax, [rax+10h]
0x1800091a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091a5  mov     rcx, rbx; this
0x1800091a8  add     rsp, 20h
0x1800091ac  pop     rbx
0x1800091ad  jmp     ??1CParseTreeNode@@UEAA@XZ; CParseTreeNode::~CParseTreeNode(void)
```
