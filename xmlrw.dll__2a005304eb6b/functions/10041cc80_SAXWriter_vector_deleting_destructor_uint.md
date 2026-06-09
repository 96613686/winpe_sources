# SAXWriter::`vector deleting destructor'(uint)

- ea: `0x10041cc80`
- end: `0x10041cde0`
- name: `??_ESAXWriter@@MEAAPEAXI@Z`
- size: `352`
- prototype: `void *__fastcall(SAXWriter *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x100401310`
- `0x10041cc80`
- `0x10041d870`
- `0x100439df0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x10041cd42`
- `KERNEL32!HeapFree` at `0x10041cdb1`
- `KERNEL32!HeapFree` at `0x10041cd42`
- `KERNEL32!HeapFree` at `0x10041cdb1`

## pseudocode

```c
SAXWriter *__fastcall SAXWriter::`vector deleting destructor'(SAXWriter *this, char a2)
{
  SAXWriter *v4; // rcx
  void (__fastcall ***v5)(_QWORD, __int64); // rcx
  char *v6; // r8
  struct IMalloc *v7; // rcx
  __int64 v8; // rcx
  struct IMalloc *v9; // rcx

  *(_QWORD *)this = &SAXWriter::`vftable'{for `Base'};
  v4 = (SAXWriter *)((char *)this + 16);
  *(_QWORD *)v4 = &SAXWriter::`vftable'{for `IMXWriter'};
  *((_QWORD *)this + 3) = &SAXWriter::`vftable'{for `ISAXLexicalHandler'};
  *((_QWORD *)this + 4) = &SAXWriter::`vftable'{for `ISAXDeclHandler'};
  *((_QWORD *)this + 5) = &SAXWriter::`vftable'{for `ISAXDTDHandler'};
  *((_QWORD *)this + 6) = &SAXWriter::`vftable'{for `ISAXErrorHandler'};
  *((_QWORD *)this + 7) = &SAXWriter::`vftable'{for `IMXAttributeWriter'};
  SAXWriter::flush(v4);
  v5 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 13);
  if ( v5 )
    (**v5)(v5, 1);
  v6 = (char *)*((_QWORD *)this + 20);
  if ( v6 != (char *)this + 112 && v6 )
  {
    v7 = (struct IMalloc *)*((_QWORD *)this + 1);
    if ( v7 || (v7 = g_pMalloc) != 0 )
      ((void (__fastcall *)(struct IMalloc *, _QWORD))v7->lpVtbl->Free)(v7, *((_QWORD *)this + 20));
    else
      HeapFree(g_hHeap, 0, v6);
  }
  v8 = *((_QWORD *)this + 12);
  if ( v8 )
  {
    *((_QWORD *)this + 12) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  if ( (a2 & 1) == 0 )
    return this;
  if ( (a2 & 4) != 0 )
  {
    __global_delete(this);
    return this;
  }
  v9 = (struct IMalloc *)*((_QWORD *)this + 1);
  if ( v9 || (v9 = g_pMalloc) != 0 )
  {
    ((void (__fastcall *)(struct IMalloc *, SAXWriter *))v9->lpVtbl->Free)(v9, this);
    return this;
  }
  else
  {
    HeapFree(g_hHeap, 0, this);
    return this;
  }
}

```

## disassembly

```asm
0x10041cc80  mov     [rsp+arg_0], rbx
0x10041cc85  push    rdi
0x10041cc86  sub     rsp, 20h
0x10041cc8a  mov     rbx, rcx
0x10041cc8d  lea     rax, ??_7SAXWriter@@6BBase@@@; const SAXWriter::`vftable'{for `Base'}
0x10041cc94  mov     [rcx], rax
0x10041cc97  mov     edi, edx
0x10041cc99  add     rcx, 10h; this
0x10041cc9d  lea     rax, ??_7SAXWriter@@6BIMXWriter@@@; const SAXWriter::`vftable'{for `IMXWriter'}
0x10041cca4  mov     [rcx], rax
0x10041cca7  lea     rax, ??_7SAXWriter@@6BISAXLexicalHandler@@@; const SAXWriter::`vftable'{for `ISAXLexicalHandler'}
0x10041ccae  mov     [rbx+18h], rax
0x10041ccb2  lea     rax, ??_7SAXWriter@@6BISAXDeclHandler@@@; const SAXWriter::`vftable'{for `ISAXDeclHandler'}
0x10041ccb9  mov     [rbx+20h], rax
0x10041ccbd  lea     rax, ??_7SAXWriter@@6BISAXDTDHandler@@@; const SAXWriter::`vftable'{for `ISAXDTDHandler'}
0x10041ccc4  mov     [rbx+28h], rax
0x10041ccc8  lea     rax, ??_7SAXWriter@@6BISAXErrorHandler@@@; const SAXWriter::`vftable'{for `ISAXErrorHandler'}
0x10041cccf  mov     [rbx+30h], rax
0x10041ccd3  lea     rax, ??_7SAXWriter@@6BIMXAttributeWriter@@@; const SAXWriter::`vftable'{for `IMXAttributeWriter'}
0x10041ccda  mov     [rbx+38h], rax
0x10041ccde  call    ?flush@SAXWriter@@UEAAJXZ; SAXWriter::flush(void)
0x10041cce3  mov     rcx, [rbx+68h]
0x10041cce7  test    rcx, rcx
0x10041ccea  jz      short loc_10041CCFD
0x10041ccec  mov     rax, [rcx]
0x10041ccef  mov     edx, 1
0x10041ccf4  mov     rax, [rax]
0x10041ccf7  call    cs:__guard_dispatch_icall_fptr
0x10041ccfd  mov     r8, [rbx+0A0h]; lpMem
0x10041cd04  lea     rax, [rbx+70h]
0x10041cd08  cmp     r8, rax
0x10041cd0b  jz      short loc_10041CD48
0x10041cd0d  test    r8, r8
0x10041cd10  jz      short loc_10041CD48
0x10041cd12  mov     rcx, [rbx+8]
0x10041cd16  test    rcx, rcx
0x10041cd19  jnz     short loc_10041CD27
0x10041cd1b  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10041cd22  test    rcx, rcx
0x10041cd25  jz      short loc_10041CD39
0x10041cd27  mov     rax, [rcx]
0x10041cd2a  mov     rdx, r8
0x10041cd2d  mov     rax, [rax+28h]
0x10041cd31  call    cs:__guard_dispatch_icall_fptr
0x10041cd37  jmp     short loc_10041CD48
0x10041cd39  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10041cd40  xor     edx, edx; dwFlags
0x10041cd42  call    cs:__imp_HeapFree
0x10041cd48  mov     rcx, [rbx+60h]
0x10041cd4c  test    rcx, rcx
0x10041cd4f  jz      short loc_10041CD66
0x10041cd51  mov     qword ptr [rbx+60h], 0
0x10041cd59  mov     rax, [rcx]
0x10041cd5c  mov     rax, [rax+10h]
0x10041cd60  call    cs:__guard_dispatch_icall_fptr
0x10041cd66  test    dil, 1
0x10041cd6a  jz      short loc_10041CDD2
0x10041cd6c  test    dil, 4
0x10041cd70  jnz     short loc_10041CDC5
0x10041cd72  mov     rcx, [rbx+8]
0x10041cd76  test    rcx, rcx
0x10041cd79  jz      short loc_10041CD99
0x10041cd7b  mov     rax, [rcx]
0x10041cd7e  mov     rdx, rbx
0x10041cd81  mov     rax, [rax+28h]
0x10041cd85  call    cs:__guard_dispatch_icall_fptr
0x10041cd8b  mov     rax, rbx
0x10041cd8e  mov     rbx, [rsp+28h+arg_0]
0x10041cd93  add     rsp, 20h
0x10041cd97  pop     rdi
0x10041cd98  retn
0x10041cd99  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10041cda0  test    rcx, rcx
0x10041cda3  jnz     short loc_10041CD7B
0x10041cda5  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10041cdac  mov     r8, rbx; lpMem
0x10041cdaf  xor     edx, edx; dwFlags
0x10041cdb1  call    cs:__imp_HeapFree
0x10041cdb7  mov     rax, rbx
0x10041cdba  mov     rbx, [rsp+28h+arg_0]
0x10041cdbf  add     rsp, 20h
0x10041cdc3  pop     rdi
0x10041cdc4  retn
0x10041cdc5  mov     edx, 1E8h; unsigned __int64
0x10041cdca  mov     rcx, rbx; void *
0x10041cdcd  call    ?__global_delete@@YAXPEAX_K@Z; __global_delete(void *,unsigned __int64)
0x10041cdd2  mov     rax, rbx
0x10041cdd5  mov     rbx, [rsp+28h+arg_0]
0x10041cdda  add     rsp, 20h
0x10041cdde  pop     rdi
0x10041cddf  retn
```
