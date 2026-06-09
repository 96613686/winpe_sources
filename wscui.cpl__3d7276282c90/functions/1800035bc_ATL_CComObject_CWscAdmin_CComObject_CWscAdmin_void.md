# ATL::CComObject<CWscAdmin>::~CComObject<CWscAdmin>(void)

- ea: `0x1800035bc`
- end: `0x1800035f6`
- name: `??1?$CComObject@VCWscAdmin@@@ATL@@UEAA@XZ`
- size: `58`
- prototype: `__int64 __fastcall(CWscAdmin *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003690`

## callees

- `0x180003658`
- `0x18000c010`

## pseudocode

```c
void __fastcall ATL::CComObject<CWscAdmin>::~CComObject<CWscAdmin>(CWscAdmin *this)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CWscAdmin>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CWscAdmin::~CWscAdmin(this);
}

```

## disassembly

```asm
0x1800035bc  push    rbx
0x1800035be  sub     rsp, 20h
0x1800035c2  mov     dword ptr [rcx+8], 0C0000001h
0x1800035c9  lea     rax, ??_7?$CComObject@VCWscAdmin@@@ATL@@6B@; const ATL::CComObject<CWscAdmin>::`vftable'
0x1800035d0  mov     [rcx], rax
0x1800035d3  mov     rbx, rcx
0x1800035d6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800035dd  mov     rax, [rcx]
0x1800035e0  mov     rax, [rax+10h]
0x1800035e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035e9  mov     rcx, rbx; this
0x1800035ec  add     rsp, 20h
0x1800035f0  pop     rbx
0x1800035f1  jmp     ??1CWscAdmin@@QEAA@XZ; CWscAdmin::~CWscAdmin(void)
```
