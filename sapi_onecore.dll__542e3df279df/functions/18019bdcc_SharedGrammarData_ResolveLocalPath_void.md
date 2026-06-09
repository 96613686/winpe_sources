# SharedGrammarData::ResolveLocalPath(void)

- ea: `0x18019bdcc`
- end: `0x18019bf1d`
- name: `?ResolveLocalPath@SharedGrammarData@@AEAAJXZ`
- size: `337`
- prototype: `__int64 __fastcall(SharedGrammarData *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180058120`

## callees

- `0x180013ec0`
- `0x180045938`
- `0x18019bdcc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019bef6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019bf05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019bef6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019bf05`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18019be1d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18019be1d`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18019bed4`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18019bed4`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18019be82`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18019be82`

## string_xrefs

- `0x18019be9b`: `Could not create a file mapping, hr=0x%X, path=[%S]`
- `0x18019be3e`: `Could not read the grammar, hr=0x%X, path=[%S]`

## pseudocode

```c
__int64 __fastcall SharedGrammarData::ResolveLocalPath(SharedGrammarData *this)
{
  int v2; // edi
  const WCHAR *v3; // rcx
  HANDLE FileW; // rax
  const wchar_t *v6; // rsi
  unsigned int Win32Error; // eax
  const wchar_t *v8; // r9
  HANDLE FileMappingW; // rax
  unsigned int v10; // eax
  LPVOID v11; // rax
  void *v12; // rcx
  void *v13; // rcx

  v2 = 0;
  v3 = (const WCHAR *)*((_QWORD *)this + 1);
  if ( v3 )
  {
    if ( *(_QWORD *)this )
      return 2147549183LL;
    FileW = CreateFileW(v3, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    *((_QWORD *)this + 3) = FileW;
    v6 = L"<NULL>";
    if ( FileW == (HANDLE)-1LL )
    {
      Win32Error = SpHrFromLastWin32Error();
      v8 = L"<NULL>";
      if ( *((_QWORD *)this + 1) )
        v8 = (const wchar_t *)*((_QWORD *)this + 1);
      v2 = Win32Error;
      DoTraceMessage(2, "Could not read the grammar, hr=0x%X, path=[%S]", Win32Error, v8);
      if ( v2 < 0 )
        goto LABEL_14;
    }
    FileMappingW = CreateFileMappingW(*((HANDLE *)this + 3), 0, 2u, 0, 0, 0);
    *((_QWORD *)this + 4) = FileMappingW;
    if ( !FileMappingW )
    {
      v10 = SpHrFromLastWin32Error();
      if ( *((_QWORD *)this + 1) )
        v6 = (const wchar_t *)*((_QWORD *)this + 1);
      v2 = v10;
      DoTraceMessage(2, "Could not create a file mapping, hr=0x%X, path=[%S]", v10, v6);
      if ( v2 < 0 )
        goto LABEL_14;
    }
    v11 = MapViewOfFile(*((HANDLE *)this + 4), 4u, 0, 0, 0);
    *(_QWORD *)this = v11;
    if ( !v11 )
    {
      v2 = SpHrFromLastWin32Error();
      if ( v2 < 0 )
      {
LABEL_14:
        v12 = (void *)*((_QWORD *)this + 3);
        if ( v12 )
          CloseHandle(v12);
        v13 = (void *)*((_QWORD *)this + 4);
        if ( v13 )
          CloseHandle(v13);
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18019bdcc  mov     [rsp+arg_0], rbx
0x18019bdd1  mov     [rsp+arg_8], rsi
0x18019bdd6  push    rdi
0x18019bdd7  sub     rsp, 40h
0x18019bddb  mov     rbx, rcx
0x18019bdde  xor     edi, edi
0x18019bde0  mov     rcx, [rcx+8]; lpFileName
0x18019bde4  test    rcx, rcx
0x18019bde7  jz      loc_18019BF0B
0x18019bded  cmp     [rbx], rdi
0x18019bdf0  jz      short loc_18019BDFC
0x18019bdf2  mov     eax, 8000FFFFh
0x18019bdf7  jmp     loc_18019BF0D
0x18019bdfc  xor     r9d, r9d; lpSecurityAttributes
0x18019bdff  mov     [rsp+48h+hTemplateFile], rdi; hTemplateFile
0x18019be04  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18019be0c  mov     edx, 80000000h; dwDesiredAccess
0x18019be11  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18019be19  lea     r8d, [r9+1]; dwShareMode
0x18019be1d  call    cs:__imp_CreateFileW
0x18019be23  mov     [rbx+18h], rax
0x18019be27  lea     rsi, aNull_2; "<NULL>"
0x18019be2e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18019be32  jnz     short loc_18019BE64
0x18019be34  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x18019be39  cmp     qword ptr [rbx+8], 0
0x18019be3e  lea     rdx, aCouldNotReadTh; "Could not read the grammar, hr=0x%X, pa"...
0x18019be45  mov     r9, rsi
0x18019be48  mov     r8d, eax
0x18019be4b  cmovnz  r9, [rbx+8]
0x18019be50  mov     ecx, 2; int
0x18019be55  mov     edi, eax
0x18019be57  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x18019be5c  test    edi, edi
0x18019be5e  js      loc_18019BEED
0x18019be64  mov     rcx, [rbx+18h]; hFile
0x18019be68  xor     r9d, r9d; dwMaximumSizeHigh
0x18019be6b  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x18019be74  xor     edx, edx; lpFileMappingAttributes
0x18019be76  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x18019be7e  lea     r8d, [r9+2]; flProtect
0x18019be82  call    cs:__imp_CreateFileMappingW
0x18019be88  mov     [rbx+20h], rax
0x18019be8c  test    rax, rax
0x18019be8f  jnz     short loc_18019BEBD
0x18019be91  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x18019be96  cmp     qword ptr [rbx+8], 0
0x18019be9b  lea     rdx, aCouldNotCreate; "Could not create a file mapping, hr=0x%"...
0x18019bea2  mov     r8d, eax
0x18019bea5  mov     ecx, 2; int
0x18019beaa  cmovnz  rsi, [rbx+8]
0x18019beaf  mov     edi, eax
0x18019beb1  mov     r9, rsi
0x18019beb4  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x18019beb9  test    edi, edi
0x18019bebb  js      short loc_18019BEED
0x18019bebd  mov     rcx, [rbx+20h]; hFileMappingObject
0x18019bec1  xor     r9d, r9d; dwFileOffsetLow
0x18019bec4  xor     r8d, r8d; dwFileOffsetHigh
0x18019bec7  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x18019bed0  lea     edx, [r9+4]; dwDesiredAccess
0x18019bed4  call    cs:__imp_MapViewOfFile
0x18019beda  mov     [rbx], rax
0x18019bedd  test    rax, rax
0x18019bee0  jnz     short loc_18019BF0B
0x18019bee2  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x18019bee7  mov     edi, eax
0x18019bee9  test    eax, eax
0x18019beeb  jns     short loc_18019BF0B
0x18019beed  mov     rcx, [rbx+18h]; hObject
0x18019bef1  test    rcx, rcx
0x18019bef4  jz      short loc_18019BEFC
0x18019bef6  call    cs:__imp_CloseHandle
0x18019befc  mov     rcx, [rbx+20h]; hObject
0x18019bf00  test    rcx, rcx
0x18019bf03  jz      short loc_18019BF0B
0x18019bf05  call    cs:__imp_CloseHandle
0x18019bf0b  mov     eax, edi
0x18019bf0d  mov     rbx, [rsp+48h+arg_0]
0x18019bf12  mov     rsi, [rsp+48h+arg_8]
0x18019bf17  add     rsp, 40h
0x18019bf1b  pop     rdi
0x18019bf1c  retn
```
