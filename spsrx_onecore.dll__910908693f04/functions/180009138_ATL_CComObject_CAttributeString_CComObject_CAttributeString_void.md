# ATL::CComObject<CAttributeString>::~CComObject<CAttributeString>(void)

- ea: `0x180009138`
- end: `0x180009172`
- name: `??1?$CComObject@VCAttributeString@@@ATL@@UEAA@XZ`
- size: `58`
- prototype: `__int64 __fastcall(CAttributeString *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800094e0`

## callees

- `0x18000e53c`
- `0x180010010`

## pseudocode

```c
void __fastcall ATL::CComObject<CAttributeString>::~CComObject<CAttributeString>(CAttributeString *this)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CAttributeString>::`vftable';
  (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CAttributeString::~CAttributeString(this);
}

```

## disassembly

```asm
0x180009138  push    rbx
0x18000913a  sub     rsp, 20h
0x18000913e  mov     dword ptr [rcx+8], 0C0000001h
0x180009145  lea     rax, ??_7?$CComObject@VCAttributeString@@@ATL@@6B@; const ATL::CComObject<CAttributeString>::`vftable'
0x18000914c  mov     [rcx], rax
0x18000914f  mov     rbx, rcx
0x180009152  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009159  mov     rax, [rcx]
0x18000915c  mov     rax, [rax+10h]
0x180009160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009165  mov     rcx, rbx; this
0x180009168  add     rsp, 20h
0x18000916c  pop     rbx
0x18000916d  jmp     ??1CAttributeString@@UEAA@XZ; CAttributeString::~CAttributeString(void)
```
