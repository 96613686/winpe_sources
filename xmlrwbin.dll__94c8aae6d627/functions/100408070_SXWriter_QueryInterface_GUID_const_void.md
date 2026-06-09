# SXWriter::QueryInterface(_GUID const &,void * *)

- ea: `0x100408070`
- end: `0x100408232`
- name: `?QueryInterface@SXWriter@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `450`
- prototype: `__int64 __fastcall(SXWriter *__hidden this, const struct _GUID *, void **)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x100407c30`
- `0x100407c40`
- `0x100407c80`
- `0x100407cd0`
- `0x100407ce0`
- `0x100407d20`
- `0x100407d30`

## callees

- `0x100408070`
- `0x100424580`

## pseudocode

```c
__int64 __fastcall SXWriter::QueryInterface(SXWriter *this, const struct _GUID *a2, void **a3)
{
  SXWriter *v3; // r9
  char *v4; // rax
  __int64 result; // rax

  v3 = this;
  if ( *(_OWORD *)a2 == *(_OWORD *)&IID_IUnknown
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISXFormatWriter.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_ISXFormatWriter.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IMXWriter.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IMXWriter.Data4 )
  {
    v4 = (char *)this - 16;
  }
  else
  {
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISAXContentHandler.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_ISAXContentHandler.Data4 )
    {
      goto LABEL_9;
    }
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISXFormatContentHandler.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_ISXFormatContentHandler.Data4 )
    {
      v4 = (char *)this - 16;
      this = (SXWriter *)((char *)this + 8);
      goto LABEL_32;
    }
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IMXAttributeWriter.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IMXAttributeWriter.Data4 )
    {
      goto LABEL_9;
    }
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISAXDeclHandler.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_ISAXDeclHandler.Data4 )
    {
      v4 = (char *)this - 16;
      this = (SXWriter *)((char *)this + 24);
      goto LABEL_32;
    }
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISAXDTDHandler.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_ISAXDTDHandler.Data4 )
    {
      v4 = (char *)this - 16;
      this = (SXWriter *)((char *)this + 32);
      goto LABEL_32;
    }
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISAXErrorHandler.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_ISAXErrorHandler.Data4 )
    {
      v4 = (char *)this - 16;
      this = (SXWriter *)((char *)this + 40);
      goto LABEL_32;
    }
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISAXLexicalHandler.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_ISAXLexicalHandler.Data4 )
    {
      v4 = (char *)this - 16;
      this = (SXWriter *)((char *)this + 16);
      goto LABEL_32;
    }
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IMXSXAttributeWriter.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IMXSXAttributeWriter.Data4 )
    {
LABEL_9:
      v4 = (char *)this - 16;
      this = (SXWriter *)((char *)this + 48);
    }
    else
    {
      if ( *(_QWORD *)&a2->Data1 != *(_QWORD *)&IID_ISXNametable.Data1
        || *(_QWORD *)a2->Data4 != *(_QWORD *)IID_ISXNametable.Data4 )
      {
        result = 2147500034LL;
        *a3 = 0;
        return result;
      }
      v4 = (char *)this - 16;
      this = (SXWriter *)((char *)this + 56);
    }
  }
LABEL_32:
  if ( !v4 )
    this = 0;
  *a3 = this;
  (*(void (__fastcall **)(SXWriter *))(*(_QWORD *)v3 + 8LL))(v3);
  return 0;
}

```

## disassembly

```asm
0x100408070  sub     rsp, 28h
0x100408074  mov     rax, [rdx]
0x100408077  mov     r9, rcx
0x10040807a  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x100408081  jnz     short loc_100408090
0x100408083  mov     rax, [rdx+8]
0x100408087  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x10040808e  jz      short loc_1004080A9
0x100408090  mov     rax, [rdx]
0x100408093  cmp     rax, qword ptr cs:IID_ISXFormatWriter.Data1
0x10040809a  jnz     short loc_1004080B2
0x10040809c  mov     rax, [rdx+8]
0x1004080a0  cmp     rax, qword ptr cs:IID_ISXFormatWriter.Data4
0x1004080a7  jnz     short loc_1004080B2
0x1004080a9  lea     rax, [rcx-10h]
0x1004080ad  jmp     loc_100408200
0x1004080b2  mov     rax, [rdx]
0x1004080b5  cmp     rax, qword ptr cs:IID_IMXWriter.Data1
0x1004080bc  jnz     short loc_1004080CB
0x1004080be  mov     rax, [rdx+8]
0x1004080c2  cmp     rax, qword ptr cs:IID_IMXWriter.Data4
0x1004080c9  jz      short loc_1004080A9
0x1004080cb  mov     rax, [rdx]
0x1004080ce  cmp     rax, qword ptr cs:IID_ISAXContentHandler.Data1
0x1004080d5  jnz     short loc_1004080F1
0x1004080d7  mov     rax, [rdx+8]
0x1004080db  cmp     rax, qword ptr cs:IID_ISAXContentHandler.Data4
0x1004080e2  jnz     short loc_1004080F1
0x1004080e4  lea     rax, [rcx-10h]
0x1004080e8  add     rcx, 30h ; '0'
0x1004080ec  jmp     loc_100408200
0x1004080f1  mov     rax, [rdx]
0x1004080f4  cmp     rax, qword ptr cs:IID_ISXFormatContentHandler.Data1
0x1004080fb  jnz     short loc_100408117
0x1004080fd  mov     rax, [rdx+8]
0x100408101  cmp     rax, qword ptr cs:IID_ISXFormatContentHandler.Data4
0x100408108  jnz     short loc_100408117
0x10040810a  lea     rax, [rcx-10h]
0x10040810e  add     rcx, 8
0x100408112  jmp     loc_100408200
0x100408117  mov     rax, [rdx]
0x10040811a  cmp     rax, qword ptr cs:IID_IMXAttributeWriter.Data1
0x100408121  jnz     short loc_100408130
0x100408123  mov     rax, [rdx+8]
0x100408127  cmp     rax, qword ptr cs:IID_IMXAttributeWriter.Data4
0x10040812e  jz      short loc_1004080E4
0x100408130  mov     rax, [rdx]
0x100408133  cmp     rax, qword ptr cs:IID_ISAXDeclHandler.Data1
0x10040813a  jnz     short loc_100408156
0x10040813c  mov     rax, [rdx+8]
0x100408140  cmp     rax, qword ptr cs:IID_ISAXDeclHandler.Data4
0x100408147  jnz     short loc_100408156
0x100408149  lea     rax, [rcx-10h]
0x10040814d  add     rcx, 18h
0x100408151  jmp     loc_100408200
0x100408156  mov     rax, [rdx]
0x100408159  cmp     rax, qword ptr cs:IID_ISAXDTDHandler.Data1
0x100408160  jnz     short loc_10040817C
0x100408162  mov     rax, [rdx+8]
0x100408166  cmp     rax, qword ptr cs:IID_ISAXDTDHandler.Data4
0x10040816d  jnz     short loc_10040817C
0x10040816f  lea     rax, [rcx-10h]
0x100408173  add     rcx, 20h ; ' '
0x100408177  jmp     loc_100408200
0x10040817c  mov     rax, [rdx]
0x10040817f  cmp     rax, qword ptr cs:IID_ISAXErrorHandler.Data1
0x100408186  jnz     short loc_10040819F
0x100408188  mov     rax, [rdx+8]
0x10040818c  cmp     rax, qword ptr cs:IID_ISAXErrorHandler.Data4
0x100408193  jnz     short loc_10040819F
0x100408195  lea     rax, [rcx-10h]
0x100408199  add     rcx, 28h ; '('
0x10040819d  jmp     short loc_100408200
0x10040819f  mov     rax, [rdx]
0x1004081a2  cmp     rax, qword ptr cs:IID_ISAXLexicalHandler.Data1
0x1004081a9  jnz     short loc_1004081C2
0x1004081ab  mov     rax, [rdx+8]
0x1004081af  cmp     rax, qword ptr cs:IID_ISAXLexicalHandler.Data4
0x1004081b6  jnz     short loc_1004081C2
0x1004081b8  lea     rax, [rcx-10h]
0x1004081bc  add     rcx, 10h
0x1004081c0  jmp     short loc_100408200
0x1004081c2  mov     rax, [rdx]
0x1004081c5  cmp     rax, qword ptr cs:IID_IMXSXAttributeWriter.Data1
0x1004081cc  jnz     short loc_1004081DF
0x1004081ce  mov     rax, [rdx+8]
0x1004081d2  cmp     rax, qword ptr cs:IID_IMXSXAttributeWriter.Data4
0x1004081d9  jz      loc_1004080E4
0x1004081df  mov     rax, [rdx]
0x1004081e2  cmp     rax, qword ptr cs:IID_ISXNametable.Data1
0x1004081e9  jnz     short loc_100408223
0x1004081eb  mov     rax, [rdx+8]
0x1004081ef  cmp     rax, qword ptr cs:IID_ISXNametable.Data4
0x1004081f6  jnz     short loc_100408223
0x1004081f8  lea     rax, [rcx-10h]
0x1004081fc  add     rcx, 38h ; '8'
0x100408200  xor     edx, edx
0x100408202  test    rax, rax
0x100408205  cmovz   rcx, rdx
0x100408209  mov     [r8], rcx
0x10040820c  mov     rcx, r9
0x10040820f  mov     rax, [r9]
0x100408212  mov     rax, [rax+8]
0x100408216  call    cs:__guard_dispatch_icall_fptr
0x10040821c  xor     eax, eax
0x10040821e  add     rsp, 28h
0x100408222  retn
0x100408223  xor     edx, edx
0x100408225  mov     eax, 80004002h
0x10040822a  mov     [r8], rdx
0x10040822d  add     rsp, 28h
0x100408231  retn
```
