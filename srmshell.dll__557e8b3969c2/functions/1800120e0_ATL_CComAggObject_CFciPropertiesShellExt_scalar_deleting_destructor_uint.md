# ATL::CComAggObject<CFciPropertiesShellExt>::`scalar deleting destructor'(uint)

- ea: `0x1800120e0`
- end: `0x180012143`
- name: `??_G?$CComAggObject@VCFciPropertiesShellExt@@@ATL@@UEAAPEAXI@Z`
- size: `99`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000505c`
- `0x1800120e0`
- `0x180020010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001212f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001212f`

## pseudocode

```c
_DWORD *__fastcall ATL::CComAggObject<CFciPropertiesShellExt>::`scalar deleting destructor'(_DWORD *a1, char a2)
{
  *(_QWORD *)a1 = &ATL::CComAggObject<CFciPropertiesShellExt>::`vftable';
  a1[2] = -1073741823;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CFciPropertiesShellExt::~CFciPropertiesShellExt((CFciPropertiesShellExt *)(a1 + 4));
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1800120e0  mov     [rsp+arg_8], rbx
0x1800120e5  mov     [rsp+arg_0], rcx
0x1800120ea  push    rdi
0x1800120eb  sub     rsp, 20h
0x1800120ef  mov     ebx, edx
0x1800120f1  mov     rdi, rcx
0x1800120f4  lea     rax, ??_7?$CComAggObject@VCFciPropertiesShellExt@@@ATL@@6B@; const ATL::CComAggObject<CFciPropertiesShellExt>::`vftable'
0x1800120fb  mov     [rcx], rax
0x1800120fe  mov     dword ptr [rcx+8], 0C0000001h
0x180012105  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001210c  mov     rax, [rcx]
0x18001210f  mov     rax, [rax+10h]
0x180012113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012118  nop
0x180012119  lea     rcx, [rdi+10h]; this
0x18001211d  mov     [rsp+28h+arg_10], rcx
0x180012122  call    ??1CFciPropertiesShellExt@@QEAA@XZ; CFciPropertiesShellExt::~CFciPropertiesShellExt(void)
0x180012127  test    bl, 1
0x18001212a  jz      short loc_180012135
0x18001212c  mov     rcx, rdi
0x18001212f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180012135  mov     rax, rdi
0x180012138  mov     rbx, [rsp+28h+arg_8]
0x18001213d  add     rsp, 20h
0x180012141  pop     rdi
0x180012142  retn
```
