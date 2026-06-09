# XmlFindLanguageTag(IXmlReader *,STRU *,int *)

- ea: `0x18001e898`
- end: `0x18001e992`
- name: `?XmlFindLanguageTag@@YAJPEAUIXmlReader@@PEAVSTRU@@PEAH@Z`
- size: `250`
- prototype: `__int64 __fastcall(struct IXmlReader *, struct STRU *, int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180012774`
- `0x180012c54`
- `0x1800134f0`

## callees

- `0x18001e898`
- `0x1800224e6`
- `0x180023010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001e961`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001e961`

## string_xrefs

- `0x18001e919`: `xml:lang`

## pseudocode

```c
__int64 __fastcall XmlFindLanguageTag(struct IXmlReader *a1, struct STRU *a2, int *a3)
{
  struct IXmlReaderVtbl *lpVtbl; // rax
  int v7; // eax
  bool v8; // zf
  struct IXmlReaderVtbl *v9; // rax
  int v10; // eax
  struct IXmlReaderVtbl *v11; // r9
  unsigned int v12; // ebx
  int v14; // [rsp+40h] [rbp+8h] BYREF
  wchar_t *String1; // [rsp+50h] [rbp+18h] BYREF
  const unsigned __int16 *v16; // [rsp+58h] [rbp+20h] BYREF

  lpVtbl = a1->lpVtbl;
  v14 = 0;
  *a3 = 0;
  v7 = ((__int64 (__fastcall *)(struct IXmlReader *, int *))lpVtbl->GetNodeType)(a1, &v14);
  v8 = v7 == 0;
  if ( v7 >= 0 )
  {
    if ( v14 != 1 )
    {
      v7 = -2147024809;
      goto LABEL_14;
    }
    v7 = ((__int64 (__fastcall *)(struct IXmlReader *))a1->lpVtbl->MoveToFirstAttribute)(a1);
LABEL_8:
    v8 = v7 == 0;
    goto LABEL_9;
  }
  do
  {
LABEL_9:
    if ( !v8 )
      goto LABEL_14;
    v9 = a1->lpVtbl;
    String1 = 0;
    v16 = 0;
    v7 = ((__int64 (__fastcall *)(struct IXmlReader *, wchar_t **, _QWORD))v9->GetQualifiedName)(a1, &String1, 0);
    v8 = v7 == 0;
  }
  while ( v7 < 0 );
  v10 = wcscmp_0(String1, L"xml:lang");
  v11 = a1->lpVtbl;
  if ( v10 )
  {
    v7 = ((__int64 (__fastcall *)(struct IXmlReader *))v11->MoveToNextAttribute)(a1);
    goto LABEL_8;
  }
  v7 = ((__int64 (__fastcall *)(struct IXmlReader *, const unsigned __int16 **, _QWORD))v11->GetValue)(a1, &v16, 0);
  if ( v7 >= 0 )
  {
    v7 = STRU::Copy(a2, v16);
    if ( v7 >= 0 )
      *a3 = 1;
  }
LABEL_14:
  v12 = 0;
  if ( v7 != 1 )
    v12 = v7;
  ((void (__fastcall *)(struct IXmlReader *))a1->lpVtbl->MoveToElement)(a1);
  return v12;
}

```

## disassembly

```asm
0x18001e898  push    rbx
0x18001e89a  push    rsi
0x18001e89b  push    rdi
0x18001e89c  sub     rsp, 20h
0x18001e8a0  mov     rax, [rcx]
0x18001e8a3  mov     rsi, rdx
0x18001e8a6  lea     rdx, [rsp+38h+arg_0]
0x18001e8ab  mov     [rsp+38h+arg_0], 0
0x18001e8b3  mov     rbx, r8
0x18001e8b6  mov     dword ptr [r8], 0
0x18001e8bd  mov     rdi, rcx
0x18001e8c0  mov     rax, [rax+38h]
0x18001e8c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8c9  test    eax, eax
0x18001e8cb  js      short loc_18001E93A
0x18001e8cd  cmp     [rsp+38h+arg_0], 1
0x18001e8d2  jz      short loc_18001E8DE
0x18001e8d4  mov     eax, 80070057h
0x18001e8d9  jmp     loc_18001E971
0x18001e8de  mov     rax, [rdi]
0x18001e8e1  mov     rax, [rax+40h]
0x18001e8e5  jmp     short loc_18001E930
0x18001e8e7  mov     rax, [rdi]
0x18001e8ea  lea     rdx, [rsp+38h+String1]
0x18001e8ef  xor     r8d, r8d
0x18001e8f2  mov     [rsp+38h+String1], 0
0x18001e8fb  mov     rcx, rdi
0x18001e8fe  mov     [rsp+38h+arg_18], 0
0x18001e907  mov     rax, [rax+60h]
0x18001e90b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e910  test    eax, eax
0x18001e912  js      short loc_18001E93A
0x18001e914  mov     rcx, [rsp+38h+String1]; String1
0x18001e919  lea     rdx, aXmlLang; "xml:lang"
0x18001e920  call    wcscmp_0
0x18001e925  mov     r9, [rdi]
0x18001e928  test    eax, eax
0x18001e92a  jz      short loc_18001E93E
0x18001e92c  mov     rax, [r9+48h]
0x18001e930  mov     rcx, rdi
0x18001e933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e938  test    eax, eax
0x18001e93a  jz      short loc_18001E8E7
0x18001e93c  jmp     short loc_18001E971
0x18001e93e  mov     rax, [r9+80h]
0x18001e945  lea     rdx, [rsp+38h+arg_18]
0x18001e94a  xor     r8d, r8d
0x18001e94d  mov     rcx, rdi
0x18001e950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e955  test    eax, eax
0x18001e957  js      short loc_18001E971
0x18001e959  mov     rdx, [rsp+38h+arg_18]
0x18001e95e  mov     rcx, rsi
0x18001e961  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001e967  test    eax, eax
0x18001e969  js      short loc_18001E971
0x18001e96b  mov     dword ptr [rbx], 1
0x18001e971  mov     rcx, [rdi]
0x18001e974  xor     ebx, ebx
0x18001e976  cmp     eax, 1
0x18001e979  cmovnz  ebx, eax
0x18001e97c  mov     rax, [rcx+58h]
0x18001e980  mov     rcx, rdi
0x18001e983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e988  mov     eax, ebx
0x18001e98a  add     rsp, 20h
0x18001e98e  pop     rdi
0x18001e98f  pop     rsi
0x18001e990  pop     rbx
0x18001e991  retn
```
