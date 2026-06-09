# ATL::CComObject<CUWFCspNode>::`vector deleting destructor'(uint)

- ea: `0x1800081d0`
- end: `0x180008232`
- name: `??_E?$CComObject@VCUWFCspNode@@@ATL@@UEAAPEAXI@Z`
- size: `98`
- prototype: `CUWFCspNode *__fastcall(CUWFCspNode *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180007e9c`
- `0x1800081d0`
- `0x18001b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000821e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000821e`

## pseudocode

```c
CUWFCspNode *__fastcall ATL::CComObject<CUWFCspNode>::`vector deleting destructor'(CUWFCspNode *this, char a2)
{
  *((_DWORD *)this + 18) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CUWFCspNode>::`vftable'{for `ICSPNode'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CUWFCspNode>::`vftable'{for `ICSPNodeTransactioning'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CUWFCspNode::~CUWFCspNode((struct _RTL_CRITICAL_SECTION *)this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800081d0  mov     [rsp+arg_0], rbx
0x1800081d5  push    rdi
0x1800081d6  sub     rsp, 20h
0x1800081da  mov     dword ptr [rcx+48h], 0C0000001h
0x1800081e1  lea     rax, ??_7?$CComObject@VCUWFCspNode@@@ATL@@6BICSPNode@@@; const ATL::CComObject<CUWFCspNode>::`vftable'{for `ICSPNode'}
0x1800081e8  mov     [rcx], rax
0x1800081eb  mov     rdi, rcx
0x1800081ee  lea     rax, ??_7?$CComObject@VCUWFCspNode@@@ATL@@6BICSPNodeTransactioning@@@; const ATL::CComObject<CUWFCspNode>::`vftable'{for `ICSPNodeTransactioning'}
0x1800081f5  mov     ebx, edx
0x1800081f7  mov     [rcx+8], rax
0x1800081fb  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008202  mov     rax, [rcx]
0x180008205  mov     rax, [rax+10h]
0x180008209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000820e  mov     rcx, rdi; this
0x180008211  call    ??1CUWFCspNode@@MEAA@XZ; CUWFCspNode::~CUWFCspNode(void)
0x180008216  test    bl, 1
0x180008219  jz      short loc_180008224
0x18000821b  mov     rcx, rdi
0x18000821e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008224  mov     rbx, [rsp+28h+arg_0]
0x180008229  mov     rax, rdi
0x18000822c  add     rsp, 20h
0x180008230  pop     rdi
0x180008231  retn
```
