# ATL::CComObject<CWLIDFDProv>::~CComObject<CWLIDFDProv>(void)

- ea: `0x18000544c`
- end: `0x180005486`
- name: `??1?$CComObject@VCWLIDFDProv@@@ATL@@UEAA@XZ`
- size: `58`
- prototype: `void __fastcall(CWLIDFDProv *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800058f0`

## callees

- `0x18000579c`
- `0x180012010`

## pseudocode

```c
void __fastcall ATL::CComObject<CWLIDFDProv>::~CComObject<CWLIDFDProv>(CWLIDFDProv *this)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CWLIDFDProv>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CWLIDFDProv::~CWLIDFDProv(this);
}

```

## disassembly

```asm
0x18000544c  push    rbx
0x18000544e  sub     rsp, 20h
0x180005452  mov     dword ptr [rcx+8], 0C0000001h
0x180005459  lea     rax, ??_7?$CComObject@VCWLIDFDProv@@@ATL@@6B@; const ATL::CComObject<CWLIDFDProv>::`vftable'
0x180005460  mov     [rcx], rax
0x180005463  mov     rbx, rcx
0x180005466  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000546d  mov     rax, [rcx]
0x180005470  mov     rax, [rax+10h]
0x180005474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005479  mov     rcx, rbx; this
0x18000547c  add     rsp, 20h
0x180005480  pop     rbx
0x180005481  jmp     ??1CWLIDFDProv@@UEAA@XZ; CWLIDFDProv::~CWLIDFDProv(void)
```
