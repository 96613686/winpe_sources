# CSpUnCompressedLexicon::OpenLexFile(bool,void * *)

- ea: `0x1800f8110`
- end: `0x1800f8241`
- name: `?OpenLexFile@CSpUnCompressedLexicon@@AEAAJ_NPEAPEAX@Z`
- size: `305`
- prototype: `__int64 __fastcall(CSpUnCompressedLexicon *__hidden this, bool, void **)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800f6208`
- `0x1800f7574`
- `0x1800f82ac`

## callees

- `0x180013ec0`
- `0x180045938`
- `0x1800f8110`
- `0x1800f854c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f81e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f8227`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f81e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f8227`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f81f6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f81f6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800f814f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800f814f`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800f81be`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800f81be`

## string_xrefs

- `0x1800f8198`: `Cannot find lexicon file. Recreate lexicon`
- `0x1800f81d0`: `Lexicon file size is not obtainable or invalid. Recreate lexicon`

## pseudocode

```c
__int64 __fastcall CSpUnCompressedLexicon::OpenLexFile(WCHAR *this, char a2, void **a3)
{
  char *FileW; // rax
  char *v7; // rdi
  __int64 result; // rax
  int v9; // ebx
  int v10; // eax
  void *v11; // [rsp+98h] [rbp+20h] BYREF

  FileW = (char *)CreateFileW(this + 48, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v11 = FileW;
  v7 = FileW;
  if ( FileW == (char *)-1LL )
  {
    result = SpHrFromLastWin32Error();
    v9 = result;
    if ( !a2 )
    {
      *a3 = 0;
      return result;
    }
    if ( (unsigned int)(result + 2147024894) > 1 || *((_DWORD *)this + 21) != 1 && *((_DWORD *)this + 21) != 64 )
      goto LABEL_13;
    DoTraceMessage(4, "Cannot find lexicon file. Recreate lexicon");
LABEL_12:
    v10 = CSpUnCompressedLexicon::RecreateEmptyDict((CSpUnCompressedLexicon *)this, &v11);
    v7 = (char *)v11;
    v9 = v10;
LABEL_13:
    if ( v9 < 0 )
    {
      if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v7);
      v7 = 0;
    }
    goto LABEL_17;
  }
  v9 = 0;
  if ( (*((_DWORD *)this + 21) == 1 || *((_DWORD *)this + 21) == 64) && GetFileSize(FileW, 0) - 940 > 0xFFFFFC52 )
  {
    DoTraceMessage(4, "Lexicon file size is not obtainable or invalid. Recreate lexicon");
    CloseHandle(v7);
    v11 = 0;
    DeleteFileW(this + 48);
    goto LABEL_12;
  }
LABEL_17:
  *a3 = v7;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800f8110  push    rbx
0x1800f8112  push    rbp
0x1800f8113  push    rsi
0x1800f8114  push    rdi
0x1800f8115  push    r14
0x1800f8117  push    r15
0x1800f8119  sub     rsp, 48h
0x1800f811d  xor     r9d, r9d; lpSecurityAttributes
0x1800f8120  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x1800f8129  mov     r14, r8
0x1800f812c  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800f8134  mov     bpl, dl
0x1800f8137  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x1800f813f  mov     rsi, rcx
0x1800f8142  mov     edx, 80000000h; dwDesiredAccess
0x1800f8147  lea     r8d, [r9+1]; dwShareMode
0x1800f814b  add     rcx, 60h ; '`'; lpFileName
0x1800f814f  call    cs:__imp_CreateFileW
0x1800f8155  mov     [rsp+78h+arg_18], rax
0x1800f815d  mov     rdi, rax
0x1800f8160  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800f8164  jnz     short loc_1800F81AB
0x1800f8166  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800f816b  mov     ebx, eax
0x1800f816d  test    bpl, bpl
0x1800f8170  jnz     short loc_1800F817E
0x1800f8172  mov     qword ptr [r14], 0
0x1800f8179  jmp     loc_1800F8234
0x1800f817e  add     eax, 7FF8FFFEh
0x1800f8183  cmp     eax, 1
0x1800f8186  ja      loc_1800F8216
0x1800f818c  cmp     dword ptr [rsi+54h], 1
0x1800f8190  jz      short loc_1800F8198
0x1800f8192  cmp     dword ptr [rsi+54h], 40h ; '@'
0x1800f8196  jnz     short loc_1800F8216
0x1800f8198  lea     rdx, aCannotFindLexi; "Cannot find lexicon file. Recreate lexi"...
0x1800f819f  mov     ecx, 4; int
0x1800f81a4  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800f81a9  jmp     short loc_1800F81FC
0x1800f81ab  xor     ebx, ebx
0x1800f81ad  cmp     dword ptr [rsi+54h], 1
0x1800f81b1  jz      short loc_1800F81B9
0x1800f81b3  cmp     dword ptr [rsi+54h], 40h ; '@'
0x1800f81b7  jnz     short loc_1800F822F
0x1800f81b9  xor     edx, edx; lpFileSizeHigh
0x1800f81bb  mov     rcx, rdi; hFile
0x1800f81be  call    cs:__imp_GetFileSize
0x1800f81c4  add     eax, 0FFFFFC54h
0x1800f81c9  cmp     eax, 0FFFFFC52h
0x1800f81ce  jbe     short loc_1800F822F
0x1800f81d0  lea     rdx, aLexiconFileSiz; "Lexicon file size is not obtainable or "...
0x1800f81d7  mov     ecx, 4; int
0x1800f81dc  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800f81e1  mov     rcx, rdi; hObject
0x1800f81e4  call    cs:__imp_CloseHandle
0x1800f81ea  lea     rcx, [rsi+60h]; lpFileName
0x1800f81ee  mov     [rsp+78h+arg_18], rbx
0x1800f81f6  call    cs:__imp_DeleteFileW
0x1800f81fc  lea     rdx, [rsp+78h+arg_18]; void **
0x1800f8204  mov     rcx, rsi; this
0x1800f8207  call    ?RecreateEmptyDict@CSpUnCompressedLexicon@@AEAAJPEAPEAX@Z; CSpUnCompressedLexicon::RecreateEmptyDict(void * *)
0x1800f820c  mov     rdi, [rsp+78h+arg_18]
0x1800f8214  mov     ebx, eax
0x1800f8216  test    ebx, ebx
0x1800f8218  jns     short loc_1800F822F
0x1800f821a  lea     rax, [rdi-1]
0x1800f821e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800f8222  ja      short loc_1800F822D
0x1800f8224  mov     rcx, rdi; hObject
0x1800f8227  call    cs:__imp_CloseHandle
0x1800f822d  xor     edi, edi
0x1800f822f  mov     [r14], rdi
0x1800f8232  mov     eax, ebx
0x1800f8234  add     rsp, 48h
0x1800f8238  pop     r15
0x1800f823a  pop     r14
0x1800f823c  pop     rdi
0x1800f823d  pop     rsi
0x1800f823e  pop     rbp
0x1800f823f  pop     rbx
0x1800f8240  retn
```
