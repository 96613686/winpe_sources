# ATL::CComObject<CUWFCspNextSessionNode>::`scalar deleting destructor'(uint)

- ea: `0x18000e560`
- end: `0x18000e5c2`
- name: `??_G?$CComObject@VCUWFCspNextSessionNode@@@ATL@@UEAAPEAXI@Z`
- size: `98`
- prototype: `CUWFCspNextSessionNode *__fastcall(CUWFCspNextSessionNode *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000e510`
- `0x18000e560`
- `0x18001b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000e5ae`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000e5ae`

## pseudocode

```c
CUWFCspNextSessionNode *__fastcall ATL::CComObject<CUWFCspNextSessionNode>::`scalar deleting destructor'(
        CUWFCspNextSessionNode *this,
        char a2)
{
  *((_DWORD *)this + 18) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CUWFCspNextSessionNode>::`vftable'{for `ICSPNode'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CUWFCspNextSessionNode>::`vftable'{for `ICSPNodeTransactioning'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CUWFCspNextSessionNode::~CUWFCspNextSessionNode((struct _RTL_CRITICAL_SECTION *)this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000e560  mov     [rsp+arg_0], rbx
0x18000e565  push    rdi
0x18000e566  sub     rsp, 20h
0x18000e56a  mov     dword ptr [rcx+48h], 0C0000001h
0x18000e571  lea     rax, ??_7?$CComObject@VCUWFCspNextSessionNode@@@ATL@@6BICSPNode@@@; const ATL::CComObject<CUWFCspNextSessionNode>::`vftable'{for `ICSPNode'}
0x18000e578  mov     [rcx], rax
0x18000e57b  mov     rdi, rcx
0x18000e57e  lea     rax, ??_7?$CComObject@VCUWFCspNextSessionNode@@@ATL@@6BICSPNodeTransactioning@@@; const ATL::CComObject<CUWFCspNextSessionNode>::`vftable'{for `ICSPNodeTransactioning'}
0x18000e585  mov     ebx, edx
0x18000e587  mov     [rcx+8], rax
0x18000e58b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000e592  mov     rax, [rcx]
0x18000e595  mov     rax, [rax+10h]
0x18000e599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e59e  mov     rcx, rdi; this
0x18000e5a1  call    ??1CUWFCspNextSessionNode@@MEAA@XZ; CUWFCspNextSessionNode::~CUWFCspNextSessionNode(void)
0x18000e5a6  test    bl, 1
0x18000e5a9  jz      short loc_18000E5B4
0x18000e5ab  mov     rcx, rdi
0x18000e5ae  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000e5b4  mov     rbx, [rsp+28h+arg_0]
0x18000e5b9  mov     rax, rdi
0x18000e5bc  add     rsp, 20h
0x18000e5c0  pop     rdi
0x18000e5c1  retn
```
