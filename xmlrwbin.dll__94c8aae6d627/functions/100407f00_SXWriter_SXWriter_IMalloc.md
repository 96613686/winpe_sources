# SXWriter::SXWriter(IMalloc *)

- ea: `0x100407f00`
- end: `0x10040806a`
- name: `??0SXWriter@@IEAA@PEAUIMalloc@@@Z`
- size: `362`
- prototype: `SXWriter *__fastcall(SXWriter *__hidden this, struct IMalloc *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x100407e10`

## callees

- `0x100407f00`
- `0x100424580`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x100407fbd`
- `KERNEL32!EnterCriticalSection` at `0x100407fbd`
- `KERNEL32!LeaveCriticalSection` at `0x100407fd0`
- `KERNEL32!LeaveCriticalSection` at `0x100407fd0`

## pseudocode

```c
SXWriter *__fastcall SXWriter::SXWriter(SXWriter *this, struct IMalloc *a2)
{
  __int64 v3; // rdx
  _WORD *v4; // rax
  __int16 v5; // cx
  _WORD *v6; // rcx
  SXWriter *result; // rax

  *((_QWORD *)this + 1) = a2;
  *((_QWORD *)this + 12) = a2;
  *(_QWORD *)this = &SXWriter::`vftable'{for `Base'};
  *((_QWORD *)this + 2) = &SXWriter::`vftable'{for `ISXFormatWriter'};
  *((_QWORD *)this + 3) = &SXWriter::`vftable'{for `ISXFormatContentHandler'};
  *((_QWORD *)this + 4) = &SXWriter::`vftable'{for `ISAXLexicalHandler'};
  *((_QWORD *)this + 5) = &SXWriter::`vftable'{for `ISAXDeclHandler'};
  *((_QWORD *)this + 6) = &SXWriter::`vftable'{for `ISAXDTDHandler'};
  *((_QWORD *)this + 7) = &SXWriter::`vftable'{for `ISAXErrorHandler'};
  *((_QWORD *)this + 8) = &SXWriter::`vftable'{for `IMXSXAttributeWriter'};
  *((_QWORD *)this + 9) = &SXWriter::`vftable'{for `ISXNametable'};
  *((_QWORD *)this + 11) = &_xarray<WriterHandleEntry,_xarray_item<WriterHandleEntry>>::`vftable';
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  if ( a2 )
    ((void (__fastcall *)(struct IMalloc *))a2->lpVtbl->AddRef)(a2);
  *((_DWORD *)this + 63) = 1;
  *((_BYTE *)this + 336) = 0;
  EnterCriticalSection(&s_cs);
  ++s_cComponents;
  LeaveCriticalSection(&s_cs);
  v3 = 24;
  v4 = (_WORD *)((char *)this + 144);
  do
  {
    if ( v3 == -2147483622 )
      break;
    v5 = *(_WORD *)((char *)v4 + (char *)L"UTF-16" - ((char *)this + 144));
    if ( !v5 )
      break;
    *v4++ = v5;
    --v3;
  }
  while ( v3 );
  v6 = v4 - 1;
  if ( v3 )
    v6 = v4;
  *v6 = 0;
  *((_QWORD *)this + 39) = (char *)this + 2401;
  result = this;
  *((_QWORD *)this + 24) = (char *)this + 144;
  *((_DWORD *)this + 50) = 24;
  *((_WORD *)this + 102) = 0;
  *((_BYTE *)this + 248) = 0;
  *((_DWORD *)this + 32) = -1;
  *((_QWORD *)this + 10) = 0;
  return result;
}

```

## disassembly

```asm
0x100407f00  mov     [rsp+arg_0], rbx
0x100407f05  push    rdi
0x100407f06  sub     rsp, 20h
0x100407f0a  xor     edi, edi
0x100407f0c  mov     [rcx+8], rdx
0x100407f10  mov     [rcx+60h], rdx
0x100407f14  lea     rax, ??_7SXWriter@@6BBase@@@; const SXWriter::`vftable'{for `Base'}
0x100407f1b  mov     [rcx], rax
0x100407f1e  lea     rax, ??_7SXWriter@@6BISXFormatWriter@@@; const SXWriter::`vftable'{for `ISXFormatWriter'}
0x100407f25  mov     [rcx+10h], rax
0x100407f29  lea     rax, ??_7SXWriter@@6BISXFormatContentHandler@@@; const SXWriter::`vftable'{for `ISXFormatContentHandler'}
0x100407f30  mov     [rcx+18h], rax
0x100407f34  lea     rax, ??_7SXWriter@@6BISAXLexicalHandler@@@; const SXWriter::`vftable'{for `ISAXLexicalHandler'}
0x100407f3b  mov     [rcx+20h], rax
0x100407f3f  lea     rax, ??_7SXWriter@@6BISAXDeclHandler@@@; const SXWriter::`vftable'{for `ISAXDeclHandler'}
0x100407f46  mov     [rcx+28h], rax
0x100407f4a  lea     rax, ??_7SXWriter@@6BISAXDTDHandler@@@; const SXWriter::`vftable'{for `ISAXDTDHandler'}
0x100407f51  mov     [rcx+30h], rax
0x100407f55  lea     rax, ??_7SXWriter@@6BISAXErrorHandler@@@; const SXWriter::`vftable'{for `ISAXErrorHandler'}
0x100407f5c  mov     [rcx+38h], rax
0x100407f60  lea     rax, ??_7SXWriter@@6BIMXSXAttributeWriter@@@; const SXWriter::`vftable'{for `IMXSXAttributeWriter'}
0x100407f67  mov     [rcx+40h], rax
0x100407f6b  lea     rax, ??_7SXWriter@@6BISXNametable@@@; const SXWriter::`vftable'{for `ISXNametable'}
0x100407f72  mov     [rcx+48h], rax
0x100407f76  lea     rax, ??_7?$_xarray@UWriterHandleEntry@@V?$_xarray_item@UWriterHandleEntry@@@@@@6B@; const _xarray<WriterHandleEntry,_xarray_item<WriterHandleEntry>>::`vftable'
0x100407f7d  mov     [rcx+58h], rax
0x100407f81  mov     rbx, rcx
0x100407f84  mov     [rcx+68h], rdi
0x100407f88  mov     [rcx+70h], rdi
0x100407f8c  mov     [rcx+78h], rdi
0x100407f90  test    rdx, rdx
0x100407f93  jz      short loc_100407FA5
0x100407f95  mov     rax, [rdx]
0x100407f98  mov     rcx, rdx
0x100407f9b  mov     rax, [rax+8]
0x100407f9f  call    cs:__guard_dispatch_icall_fptr
0x100407fa5  lea     rcx, ?s_cs@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x100407fac  mov     dword ptr [rbx+0FCh], 1
0x100407fb6  mov     [rbx+150h], dil
0x100407fbd  call    cs:__imp_EnterCriticalSection
0x100407fc3  inc     cs:?s_cComponents@@3JA; long s_cComponents
0x100407fc9  lea     rcx, ?s_cs@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x100407fd0  call    cs:__imp_LeaveCriticalSection
0x100407fd6  lea     r9, [rbx+90h]
0x100407fdd  mov     edx, 18h
0x100407fe2  lea     r8, aUtf16; "UTF-16"
0x100407fe9  mov     rax, r9
0x100407fec  sub     r8, r9
0x100407fef  nop
0x100407ff0  lea     rcx, [rdx+7FFFFFE6h]
0x100407ff7  test    rcx, rcx
0x100407ffa  jz      short loc_100408013
0x100407ffc  movzx   ecx, word ptr [r8+rax]
0x100408001  test    cx, cx
0x100408004  jz      short loc_100408013
0x100408006  mov     [rax], cx
0x100408009  add     rax, 2
0x10040800d  sub     rdx, 1
0x100408011  jnz     short loc_100407FF0
0x100408013  lea     rcx, [rax-2]
0x100408017  test    rdx, rdx
0x10040801a  cmovnz  rcx, rax
0x10040801e  lea     rax, [rbx+961h]
0x100408025  mov     [rcx], di
0x100408028  mov     [rbx+138h], rax
0x10040802f  mov     rax, rbx
0x100408032  mov     [rbx+0C0h], r9
0x100408039  mov     dword ptr [rbx+0C8h], 18h
0x100408043  mov     [rbx+0CCh], di
0x10040804a  mov     [rbx+0F8h], dil
0x100408051  mov     dword ptr [rbx+80h], 0FFFFFFFFh
0x10040805b  mov     [rbx+50h], rdi
0x10040805f  mov     rbx, [rsp+28h+arg_0]
0x100408064  add     rsp, 20h
0x100408068  pop     rdi
0x100408069  retn
```
