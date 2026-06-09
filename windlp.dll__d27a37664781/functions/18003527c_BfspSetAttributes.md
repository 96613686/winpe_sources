# BfspSetAttributes

- ea: `0x18003527c`
- end: `0x180035386`
- name: `BfspSetAttributes`
- size: `266`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180032518`
- `0x18003379c`

## callees

- `0x180031b50`
- `0x18003527c`
- `0x1800366b8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18003532c`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18003532c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800352c0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800352c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003536e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003536e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800352cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035338`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800352cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035338`

## string_xrefs

- `0x180035358`: `SetFileAttributes(%s) failed! Last Error = %#x.`

## pseudocode

```c
__int64 __fastcall BfspSetAttributes(LPCWSTR lpFileName, unsigned int a2)
{
  unsigned int v4; // esi
  DWORD v5; // ecx
  DWORD FileAttributesW; // eax
  DWORD LastError; // eax
  DWORD v8; // edi
  DWORD v9; // edx
  DWORD v10; // eax

  if ( a2 != 128 && (a2 & 0xFFFFFF78) != 0 )
  {
    v4 = 0;
    BfspLogMessage(4, L"Invalid attributes (%#x) specified for %s file!", a2, lpFileName);
    v5 = 87;
LABEL_19:
    SetLastError(v5);
    return v4;
  }
  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW == -1 )
  {
    v4 = 0;
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError == 5 || LastError - 32 <= 1 )
      BfspPrintFileOwnerProcess(lpFileName);
    if ( v8 == 2 )
      BfspLogMessage(2, L"GetFileAttributes(%s) failed: File not found.", lpFileName);
    else
      BfspLogMessage(3, L"GetFileAttributes(%s) failed! Last Error = %#x.", lpFileName, v8);
LABEL_18:
    v5 = v8;
    goto LABEL_19;
  }
  v9 = a2 & 0xFFFFFF7F | FileAttributesW & 0x3120;
  if ( (a2 | FileAttributesW & 0x3120 | 0x80) == 0x80 )
    v9 = 128;
  v4 = SetFileAttributesW(lpFileName, v9);
  if ( !v4 )
  {
    v10 = GetLastError();
    v8 = v10;
    if ( v10 == 5 || v10 - 32 <= 1 )
      BfspPrintFileOwnerProcess(lpFileName);
    BfspLogMessage(4, L"SetFileAttributes(%s) failed! Last Error = %#x.", lpFileName, v8);
    goto LABEL_18;
  }
  return v4;
}

```

## disassembly

```asm
0x18003527c  mov     [rsp+arg_0], rbx
0x180035281  mov     [rsp+arg_8], rsi
0x180035286  push    rdi
0x180035287  sub     rsp, 20h
0x18003528b  mov     esi, 80h
0x180035290  mov     edi, edx
0x180035292  mov     rbx, rcx
0x180035295  cmp     edx, esi
0x180035297  jz      short loc_1800352C0
0x180035299  test    edx, 0FFFFFF78h
0x18003529f  jz      short loc_1800352C0
0x1800352a1  xor     esi, esi
0x1800352a3  mov     r9, rcx
0x1800352a6  mov     r8d, edx
0x1800352a9  lea     rdx, aInvalidAttribu; "Invalid attributes (%#x) specified for "...
0x1800352b0  lea     ecx, [rsi+4]
0x1800352b3  call    BfspLogMessage
0x1800352b8  lea     ecx, [rsi+57h]; lpFileName
0x1800352bb  jmp     loc_18003536E
0x1800352c0  call    cs:__imp_GetFileAttributesW
0x1800352c6  mov     edx, eax
0x1800352c8  cmp     eax, 0FFFFFFFFh
0x1800352cb  jnz     short loc_180035314
0x1800352cd  xor     esi, esi
0x1800352cf  call    cs:__imp_GetLastError
0x1800352d5  mov     edi, eax
0x1800352d7  cmp     eax, 5
0x1800352da  jz      short loc_1800352E4
0x1800352dc  add     eax, 0FFFFFFE0h
0x1800352df  cmp     eax, 1
0x1800352e2  ja      short loc_1800352EC
0x1800352e4  mov     rcx, rbx; lpFileName
0x1800352e7  call    BfspPrintFileOwnerProcess
0x1800352ec  mov     ecx, 2
0x1800352f1  mov     r8, rbx
0x1800352f4  cmp     edi, ecx
0x1800352f6  jz      short loc_180035306
0x1800352f8  lea     rdx, aGetfileattribu_0; "GetFileAttributes(%s) failed! Last Erro"...
0x1800352ff  mov     ecx, 3
0x180035304  jmp     short loc_180035364
0x180035306  lea     rdx, aGetfileattribu; "GetFileAttributes(%s) failed: File not "...
0x18003530d  call    BfspLogMessage
0x180035312  jmp     short loc_18003536C
0x180035314  and     edx, 3120h
0x18003531a  mov     rcx, rbx; lpFileName
0x18003531d  or      edx, edi
0x18003531f  mov     eax, edx
0x180035321  btr     edx, 7
0x180035325  or      eax, esi
0x180035327  cmp     eax, esi
0x180035329  cmovz   edx, eax; dwFileAttributes
0x18003532c  call    cs:__imp_SetFileAttributesW
0x180035332  mov     esi, eax
0x180035334  test    eax, eax
0x180035336  jnz     short loc_180035374
0x180035338  call    cs:__imp_GetLastError
0x18003533e  mov     edi, eax
0x180035340  cmp     eax, 5
0x180035343  jz      short loc_18003534D
0x180035345  lea     ecx, [rax-20h]
0x180035348  cmp     ecx, 1
0x18003534b  ja      short loc_180035355
0x18003534d  mov     rcx, rbx; lpFileName
0x180035350  call    BfspPrintFileOwnerProcess
0x180035355  mov     r8, rbx
0x180035358  lea     rdx, aSetfileattribu; "SetFileAttributes(%s) failed! Last Erro"...
0x18003535f  mov     ecx, 4
0x180035364  mov     r9d, edi
0x180035367  call    BfspLogMessage
0x18003536c  mov     ecx, edi; dwErrCode
0x18003536e  call    cs:__imp_SetLastError
0x180035374  mov     rbx, [rsp+28h+arg_0]
0x180035379  mov     eax, esi
0x18003537b  mov     rsi, [rsp+28h+arg_8]
0x180035380  add     rsp, 20h
0x180035384  pop     rdi
0x180035385  retn
```
