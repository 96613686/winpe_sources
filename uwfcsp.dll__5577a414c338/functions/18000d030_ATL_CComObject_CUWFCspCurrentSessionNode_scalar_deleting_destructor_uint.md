# ATL::CComObject<CUWFCspCurrentSessionNode>::`scalar deleting destructor'(uint)

- ea: `0x18000d030`
- end: `0x18000d092`
- name: `??_G?$CComObject@VCUWFCspCurrentSessionNode@@@ATL@@UEAAPEAXI@Z`
- size: `98`
- prototype: `CUWFCspCurrentSessionNode *__fastcall(CUWFCspCurrentSessionNode *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000cfd8`
- `0x18000d030`
- `0x18001b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000d07e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000d07e`

## pseudocode

```c
CUWFCspCurrentSessionNode *__fastcall ATL::CComObject<CUWFCspCurrentSessionNode>::`scalar deleting destructor'(
        CUWFCspCurrentSessionNode *this,
        char a2)
{
  *((_DWORD *)this + 18) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CUWFCspCurrentSessionNode>::`vftable'{for `ICSPNode'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CUWFCspCurrentSessionNode>::`vftable'{for `ICSPNodeTransactioning'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CUWFCspCurrentSessionNode::~CUWFCspCurrentSessionNode((struct _RTL_CRITICAL_SECTION *)this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000d030  mov     [rsp+arg_0], rbx
0x18000d035  push    rdi
0x18000d036  sub     rsp, 20h
0x18000d03a  mov     dword ptr [rcx+48h], 0C0000001h
0x18000d041  lea     rax, ??_7?$CComObject@VCUWFCspCurrentSessionNode@@@ATL@@6BICSPNode@@@; const ATL::CComObject<CUWFCspCurrentSessionNode>::`vftable'{for `ICSPNode'}
0x18000d048  mov     [rcx], rax
0x18000d04b  mov     rdi, rcx
0x18000d04e  lea     rax, ??_7?$CComObject@VCUWFCspCurrentSessionNode@@@ATL@@6BICSPNodeTransactioning@@@; const ATL::CComObject<CUWFCspCurrentSessionNode>::`vftable'{for `ICSPNodeTransactioning'}
0x18000d055  mov     ebx, edx
0x18000d057  mov     [rcx+8], rax
0x18000d05b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000d062  mov     rax, [rcx]
0x18000d065  mov     rax, [rax+10h]
0x18000d069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d06e  mov     rcx, rdi; this
0x18000d071  call    ??1CUWFCspCurrentSessionNode@@MEAA@XZ; CUWFCspCurrentSessionNode::~CUWFCspCurrentSessionNode(void)
0x18000d076  test    bl, 1
0x18000d079  jz      short loc_18000D084
0x18000d07b  mov     rcx, rdi
0x18000d07e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000d084  mov     rbx, [rsp+28h+arg_0]
0x18000d089  mov     rax, rdi
0x18000d08c  add     rsp, 20h
0x18000d090  pop     rdi
0x18000d091  retn
```
