# SAXWriter::QueryInterface(_GUID const &,void * *)

- ea: `0x10041cea0`
- end: `0x10041cff0`
- name: `?QueryInterface@SAXWriter@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `336`
- prototype: `__int64 __fastcall(SAXWriter *__hidden this, const struct _GUID *, void **)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x100420290`
- `0x1004202b0`
- `0x1004202e0`
- `0x100420310`
- `0x100420350`

## callees

- `0x10041cea0`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall SAXWriter::QueryInterface(SAXWriter *this, const struct _GUID *a2, void **a3)
{
  SAXWriter *v3; // r9
  __int64 result; // rax
  char *v5; // rax

  v3 = this;
  if ( !a3 )
    return 2147500035LL;
  if ( (*(_QWORD *)&a2->Data1 != *(_QWORD *)&IID_IUnknown.Data1 || *(_QWORD *)a2->Data4 != *(_QWORD *)IID_IUnknown.Data4)
    && (*(_QWORD *)&a2->Data1 != *(_QWORD *)&IID_IMXWriter.Data1
     || *(_QWORD *)a2->Data4 != *(_QWORD *)IID_IMXWriter.Data4) )
  {
    if ( *(_QWORD *)&a2->Data1 != *(_QWORD *)&IID_ISAXContentHandler.Data1
      || *(_QWORD *)a2->Data4 != *(_QWORD *)IID_ISAXContentHandler.Data4 )
    {
      if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISAXDeclHandler.Data1
        && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_ISAXDeclHandler.Data4 )
      {
        v5 = (char *)this - 16;
        this = (SAXWriter *)((char *)this + 16);
        goto LABEL_25;
      }
      if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISAXDTDHandler.Data1
        && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_ISAXDTDHandler.Data4 )
      {
        v5 = (char *)this - 16;
        this = (SAXWriter *)((char *)this + 24);
        goto LABEL_25;
      }
      if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISAXErrorHandler.Data1
        && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_ISAXErrorHandler.Data4 )
      {
        v5 = (char *)this - 16;
        this = (SAXWriter *)((char *)this + 32);
        goto LABEL_25;
      }
      if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISAXLexicalHandler.Data1
        && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_ISAXLexicalHandler.Data4 )
      {
        v5 = (char *)this - 16;
        this = (SAXWriter *)((char *)this + 8);
        goto LABEL_25;
      }
      if ( *(_QWORD *)&a2->Data1 != *(_QWORD *)&IID_IMXAttributeWriter.Data1
        || *(_QWORD *)a2->Data4 != *(_QWORD *)IID_IMXAttributeWriter.Data4 )
      {
        result = 2147500034LL;
        *a3 = 0;
        return result;
      }
    }
    v5 = (char *)this - 16;
    this = (SAXWriter *)((char *)this + 40);
    goto LABEL_25;
  }
  v5 = (char *)this - 16;
LABEL_25:
  if ( !v5 )
    this = 0;
  *a3 = this;
  (*(void (__fastcall **)(SAXWriter *))(*(_QWORD *)v3 + 8LL))(v3);
  return 0;
}

```

## disassembly

```asm
0x10041cea0  sub     rsp, 28h
0x10041cea4  mov     r9, rcx
0x10041cea7  test    r8, r8
0x10041ceaa  jnz     short loc_10041CEB6
0x10041ceac  mov     eax, 80004003h
0x10041ceb1  add     rsp, 28h
0x10041ceb5  retn
0x10041ceb6  mov     rax, [rdx]
0x10041ceb9  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x10041cec0  jnz     short loc_10041CECF
0x10041cec2  mov     rax, [rdx+8]
0x10041cec6  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x10041cecd  jz      short loc_10041CEE8
0x10041cecf  mov     rax, [rdx]
0x10041ced2  cmp     rax, qword ptr cs:IID_IMXWriter.Data1
0x10041ced9  jnz     short loc_10041CEF1
0x10041cedb  mov     rax, [rdx+8]
0x10041cedf  cmp     rax, qword ptr cs:IID_IMXWriter.Data4
0x10041cee6  jnz     short loc_10041CEF1
0x10041cee8  lea     rax, [rcx-10h]
0x10041ceec  jmp     loc_10041CFBE
0x10041cef1  mov     rax, [rdx]
0x10041cef4  cmp     rax, qword ptr cs:IID_ISAXContentHandler.Data1
0x10041cefb  jnz     short loc_10041CF0E
0x10041cefd  mov     rax, [rdx+8]
0x10041cf01  cmp     rax, qword ptr cs:IID_ISAXContentHandler.Data4
0x10041cf08  jz      loc_10041CFB6
0x10041cf0e  mov     rax, [rdx]
0x10041cf11  cmp     rax, qword ptr cs:IID_ISAXDeclHandler.Data1
0x10041cf18  jnz     short loc_10041CF34
0x10041cf1a  mov     rax, [rdx+8]
0x10041cf1e  cmp     rax, qword ptr cs:IID_ISAXDeclHandler.Data4
0x10041cf25  jnz     short loc_10041CF34
0x10041cf27  lea     rax, [rcx-10h]
0x10041cf2b  add     rcx, 10h
0x10041cf2f  jmp     loc_10041CFBE
0x10041cf34  mov     rax, [rdx]
0x10041cf37  cmp     rax, qword ptr cs:IID_ISAXDTDHandler.Data1
0x10041cf3e  jnz     short loc_10041CF57
0x10041cf40  mov     rax, [rdx+8]
0x10041cf44  cmp     rax, qword ptr cs:IID_ISAXDTDHandler.Data4
0x10041cf4b  jnz     short loc_10041CF57
0x10041cf4d  lea     rax, [rcx-10h]
0x10041cf51  add     rcx, 18h
0x10041cf55  jmp     short loc_10041CFBE
0x10041cf57  mov     rax, [rdx]
0x10041cf5a  cmp     rax, qword ptr cs:IID_ISAXErrorHandler.Data1
0x10041cf61  jnz     short loc_10041CF7A
0x10041cf63  mov     rax, [rdx+8]
0x10041cf67  cmp     rax, qword ptr cs:IID_ISAXErrorHandler.Data4
0x10041cf6e  jnz     short loc_10041CF7A
0x10041cf70  lea     rax, [rcx-10h]
0x10041cf74  add     rcx, 20h ; ' '
0x10041cf78  jmp     short loc_10041CFBE
0x10041cf7a  mov     rax, [rdx]
0x10041cf7d  cmp     rax, qword ptr cs:IID_ISAXLexicalHandler.Data1
0x10041cf84  jnz     short loc_10041CF9D
0x10041cf86  mov     rax, [rdx+8]
0x10041cf8a  cmp     rax, qword ptr cs:IID_ISAXLexicalHandler.Data4
0x10041cf91  jnz     short loc_10041CF9D
0x10041cf93  lea     rax, [rcx-10h]
0x10041cf97  add     rcx, 8
0x10041cf9b  jmp     short loc_10041CFBE
0x10041cf9d  mov     rax, [rdx]
0x10041cfa0  cmp     rax, qword ptr cs:IID_IMXAttributeWriter.Data1
0x10041cfa7  jnz     short loc_10041CFE1
0x10041cfa9  mov     rax, [rdx+8]
0x10041cfad  cmp     rax, qword ptr cs:IID_IMXAttributeWriter.Data4
0x10041cfb4  jnz     short loc_10041CFE1
0x10041cfb6  lea     rax, [rcx-10h]
0x10041cfba  add     rcx, 28h ; '('
0x10041cfbe  xor     edx, edx
0x10041cfc0  test    rax, rax
0x10041cfc3  cmovz   rcx, rdx
0x10041cfc7  mov     [r8], rcx
0x10041cfca  mov     rcx, r9
0x10041cfcd  mov     rax, [r9]
0x10041cfd0  mov     rax, [rax+8]
0x10041cfd4  call    cs:__guard_dispatch_icall_fptr
0x10041cfda  xor     eax, eax
0x10041cfdc  add     rsp, 28h
0x10041cfe0  retn
0x10041cfe1  xor     edx, edx
0x10041cfe3  mov     eax, 80004002h
0x10041cfe8  mov     [r8], rdx
0x10041cfeb  add     rsp, 28h
0x10041cfef  retn
```
