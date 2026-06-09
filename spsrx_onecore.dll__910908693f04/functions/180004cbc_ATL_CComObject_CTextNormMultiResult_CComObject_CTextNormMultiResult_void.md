# ATL::CComObject<CTextNormMultiResult>::~CComObject<CTextNormMultiResult>(void)

- ea: `0x180004cbc`
- end: `0x180004cf6`
- name: `??1?$CComObject@VCTextNormMultiResult@@@ATL@@UEAA@XZ`
- size: `58`
- prototype: `__int64 __fastcall(CTextNormMultiResult *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004d50`

## callees

- `0x180009218`
- `0x180010010`

## pseudocode

```c
void __fastcall ATL::CComObject<CTextNormMultiResult>::~CComObject<CTextNormMultiResult>(CTextNormMultiResult *this)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CTextNormMultiResult>::`vftable';
  (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CTextNormMultiResult::~CTextNormMultiResult(this);
}

```

## disassembly

```asm
0x180004cbc  push    rbx
0x180004cbe  sub     rsp, 20h
0x180004cc2  mov     dword ptr [rcx+8], 0C0000001h
0x180004cc9  lea     rax, ??_7?$CComObject@VCTextNormMultiResult@@@ATL@@6B@; const ATL::CComObject<CTextNormMultiResult>::`vftable'
0x180004cd0  mov     [rcx], rax
0x180004cd3  mov     rbx, rcx
0x180004cd6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004cdd  mov     rax, [rcx]
0x180004ce0  mov     rax, [rax+10h]
0x180004ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ce9  mov     rcx, rbx; this
0x180004cec  add     rsp, 20h
0x180004cf0  pop     rbx
0x180004cf1  jmp     ??1CTextNormMultiResult@@UEAA@XZ; CTextNormMultiResult::~CTextNormMultiResult(void)
```
