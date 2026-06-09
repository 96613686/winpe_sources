# SAXWriter::SAXWriter(IMalloc *)

- ea: `0x10041cba0`
- end: `0x10041cc6d`
- name: `??0SAXWriter@@IEAA@PEAUIMalloc@@@Z`
- size: `205`
- prototype: `SAXWriter *__fastcall(SAXWriter *__hidden this, struct IMalloc *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x10041cae0`

## callees

- `0x10041cba0`
- `0x100439df0`

## pseudocode

```c
SAXWriter *__fastcall SAXWriter::SAXWriter(SAXWriter *this, struct IMalloc *a2)
{
  SAXWriter *result; // rax

  *((_QWORD *)this + 1) = a2;
  *(_QWORD *)this = &SAXWriter::`vftable'{for `Base'};
  *((_DWORD *)this + 16) = 1;
  *((_QWORD *)this + 2) = &SAXWriter::`vftable'{for `IMXWriter'};
  *((_QWORD *)this + 3) = &SAXWriter::`vftable'{for `ISAXLexicalHandler'};
  *((_QWORD *)this + 4) = &SAXWriter::`vftable'{for `ISAXDeclHandler'};
  *((_QWORD *)this + 5) = &SAXWriter::`vftable'{for `ISAXDTDHandler'};
  *((_QWORD *)this + 6) = &SAXWriter::`vftable'{for `ISAXErrorHandler'};
  *((_QWORD *)this + 7) = &SAXWriter::`vftable'{for `IMXAttributeWriter'};
  *((_QWORD *)this + 13) = 0;
  if ( a2 )
    ((void (__fastcall *)(struct IMalloc *))a2->lpVtbl->AddRef)(a2);
  *((_DWORD *)this + 42) = 24;
  *((_WORD *)this + 56) = 0;
  *((_QWORD *)this + 20) = (char *)this + 112;
  result = this;
  *((_WORD *)this + 86) = 0;
  *((_WORD *)this + 108) = 1;
  *((_DWORD *)this + 55) = -1;
  *((_WORD *)this + 112) = 0;
  *((_BYTE *)this + 226) = 1;
  return result;
}

```

## disassembly

```asm
0x10041cba0  mov     [rsp+arg_0], rbx
0x10041cba5  push    rdi
0x10041cba6  sub     rsp, 20h
0x10041cbaa  lea     rax, ??_7SAXWriter@@6BBase@@@; const SAXWriter::`vftable'{for `Base'}
0x10041cbb1  mov     [rcx+8], rdx
0x10041cbb5  mov     [rcx], rax
0x10041cbb8  xor     edi, edi
0x10041cbba  mov     dword ptr [rcx+40h], 1
0x10041cbc1  lea     rax, ??_7SAXWriter@@6BIMXWriter@@@; const SAXWriter::`vftable'{for `IMXWriter'}
0x10041cbc8  mov     [rcx+10h], rax
0x10041cbcc  lea     rax, ??_7SAXWriter@@6BISAXLexicalHandler@@@; const SAXWriter::`vftable'{for `ISAXLexicalHandler'}
0x10041cbd3  mov     [rcx+18h], rax
0x10041cbd7  lea     rax, ??_7SAXWriter@@6BISAXDeclHandler@@@; const SAXWriter::`vftable'{for `ISAXDeclHandler'}
0x10041cbde  mov     [rcx+20h], rax
0x10041cbe2  lea     rax, ??_7SAXWriter@@6BISAXDTDHandler@@@; const SAXWriter::`vftable'{for `ISAXDTDHandler'}
0x10041cbe9  mov     [rcx+28h], rax
0x10041cbed  lea     rax, ??_7SAXWriter@@6BISAXErrorHandler@@@; const SAXWriter::`vftable'{for `ISAXErrorHandler'}
0x10041cbf4  mov     [rcx+30h], rax
0x10041cbf8  lea     rax, ??_7SAXWriter@@6BIMXAttributeWriter@@@; const SAXWriter::`vftable'{for `IMXAttributeWriter'}
0x10041cbff  mov     [rcx+38h], rax
0x10041cc03  mov     rbx, rcx
0x10041cc06  mov     [rcx+68h], rdi
0x10041cc0a  test    rdx, rdx
0x10041cc0d  jz      short loc_10041CC1F
0x10041cc0f  mov     rax, [rdx]
0x10041cc12  mov     rcx, rdx
0x10041cc15  mov     rax, [rax+8]
0x10041cc19  call    cs:__guard_dispatch_icall_fptr
0x10041cc1f  lea     rax, [rbx+70h]
0x10041cc23  mov     dword ptr [rbx+0A8h], 18h
0x10041cc2d  mov     [rax], di
0x10041cc30  mov     [rbx+0A0h], rax
0x10041cc37  mov     rax, rbx
0x10041cc3a  mov     [rbx+0ACh], di
0x10041cc41  mov     word ptr [rbx+0D8h], 1
0x10041cc4a  mov     dword ptr [rbx+0DCh], 0FFFFFFFFh
0x10041cc54  mov     [rbx+0E0h], di
0x10041cc5b  mov     byte ptr [rbx+0E2h], 1
0x10041cc62  mov     rbx, [rsp+28h+arg_0]
0x10041cc67  add     rsp, 20h
0x10041cc6b  pop     rdi
0x10041cc6c  retn
```
