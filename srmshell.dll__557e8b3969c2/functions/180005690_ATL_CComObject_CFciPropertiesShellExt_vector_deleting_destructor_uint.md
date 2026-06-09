# ATL::CComObject<CFciPropertiesShellExt>::`vector deleting destructor'(uint)

- ea: `0x180005690`
- end: `0x1800056f8`
- name: `??_E?$CComObject@VCFciPropertiesShellExt@@@ATL@@UEAAPEAXI@Z`
- size: `104`
- prototype: `CFciPropertiesShellExt *__fastcall(CFciPropertiesShellExt *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000505c`
- `0x180005690`
- `0x180020010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800056e4`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800056e4`

## pseudocode

```c
CFciPropertiesShellExt *__fastcall ATL::CComObject<CFciPropertiesShellExt>::`vector deleting destructor'(
        CFciPropertiesShellExt *this,
        char a2)
{
  *(_QWORD *)this = &ATL::CComObject<CFciPropertiesShellExt>::`vftable'{for `IShellExtInit'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CFciPropertiesShellExt>::`vftable'{for `IShellPropSheetExt'};
  *((_DWORD *)this + 4) = -1073741823;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CFciPropertiesShellExt::~CFciPropertiesShellExt(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180005690  mov     [rsp+arg_8], rbx
0x180005695  mov     [rsp+arg_0], rcx
0x18000569a  push    rdi
0x18000569b  sub     rsp, 20h
0x18000569f  mov     ebx, edx
0x1800056a1  mov     rdi, rcx
0x1800056a4  lea     rax, ??_7?$CComObject@VCFciPropertiesShellExt@@@ATL@@6BIShellExtInit@@@; const ATL::CComObject<CFciPropertiesShellExt>::`vftable'{for `IShellExtInit'}
0x1800056ab  mov     [rcx], rax
0x1800056ae  lea     rax, ??_7?$CComObject@VCFciPropertiesShellExt@@@ATL@@6BIShellPropSheetExt@@@; const ATL::CComObject<CFciPropertiesShellExt>::`vftable'{for `IShellPropSheetExt'}
0x1800056b5  mov     [rcx+8], rax
0x1800056b9  mov     dword ptr [rcx+10h], 0C0000001h
0x1800056c0  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800056c7  mov     rax, [rcx]
0x1800056ca  mov     rax, [rax+10h]
0x1800056ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056d3  nop
0x1800056d4  mov     rcx, rdi; this
0x1800056d7  call    ??1CFciPropertiesShellExt@@QEAA@XZ; CFciPropertiesShellExt::~CFciPropertiesShellExt(void)
0x1800056dc  test    bl, 1
0x1800056df  jz      short loc_1800056EA
0x1800056e1  mov     rcx, rdi
0x1800056e4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800056ea  mov     rax, rdi
0x1800056ed  mov     rbx, [rsp+28h+arg_8]
0x1800056f2  add     rsp, 20h
0x1800056f6  pop     rdi
0x1800056f7  retn
```
