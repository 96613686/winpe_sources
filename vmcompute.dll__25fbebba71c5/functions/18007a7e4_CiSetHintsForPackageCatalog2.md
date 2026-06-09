# CiSetHintsForPackageCatalog2

- ea: `0x18007a7e4`
- end: `0x18007aa11`
- name: `CiSetHintsForPackageCatalog2`
- size: `557`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x1800582a8`

## callees

- `0x18007a7e4`
- `0x18007aa18`
- `0x18007ae6c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18007a8e1`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18007a8e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a984`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a984`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a9dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a9f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a9dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a9f1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007a82f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007a82f`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18007a853`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18007a853`
- `ntdll!RtlFreeHeap` at `0x18007a976`
- `ntdll!RtlFreeHeap` at `0x18007a976`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18007a8c3`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18007a8c3`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18007a899`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18007a899`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18007a9c8`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18007a9c8`
- `CRYPT32!CertCreateContext` at `0x18007a91b`
- `CRYPT32!CertCreateContext` at `0x18007a91b`
- `CRYPT32!CertFreeCTLContext` at `0x18007a9b4`
- `CRYPT32!CertFreeCTLContext` at `0x18007a9b4`

## pseudocode

```c
__int64 __fastcall CiSetHintsForPackageCatalog2(PCWSTR SourceString, __int64 a2)
{
  const CTL_CONTEXT *Context; // rsi
  const BYTE *v5; // r14
  void *v6; // r15
  HANDLE FileW; // rax
  void *v8; // rbp
  DWORD LowPart; // ebx
  HANDLE FileMappingW; // rax
  wchar_t *v11; // rax
  const WCHAR *v12; // rdi
  signed int CatalogHint; // ebx
  signed int LastError; // eax
  unsigned int v15; // ebx
  union _LARGE_INTEGER FileSize; // [rsp+B8h] [rbp+20h] BYREF

  FileSize.QuadPart = 0;
  Context = 0;
  v5 = 0;
  v6 = 0;
  FileW = CreateFileW(SourceString, 0x80000000, 5u, 0, 3u, 0x8000080u, 0);
  v8 = FileW;
  if ( FileW == (HANDLE)-1LL || !GetFileSizeEx(FileW, &FileSize) )
    goto LABEL_15;
  if ( FileSize.HighPart || (LowPart = FileSize.LowPart) == 0 )
  {
    CatalogHint = -1073741538;
    goto LABEL_19;
  }
  if ( (FileMappingW = CreateFileMappingW(v8, 0, 2u, 0, 0, 0), (v6 = FileMappingW) != 0)
    && (v5 = (const BYTE *)MapViewOfFile(FileMappingW, 4u, 0, 0, 0)) != 0
    && ((v11 = wcsrchr(SourceString, 0x5Cu)) != 0 ? (v12 = v11 + 1) : (v12 = SourceString),
        (Context = (const CTL_CONTEXT *)CertCreateContext(3u, 0x10001u, v5, LowPart, 5u, 0)) != 0) )
  {
    CatalogHint = CiCreateCatalogHint(v12);
    if ( CatalogHint >= 0 )
      CatalogHint = CipSetEasForEachHint(Context->pCtlInfo, a2, 0);
  }
  else
  {
LABEL_15:
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
    CatalogHint = v15 & 0xEFFFFFFF;
    if ( CatalogHint >= 0 )
      CatalogHint = -1073741823;
  }
LABEL_19:
  if ( Context )
    CertFreeCTLContext(Context);
  if ( v5 )
    UnmapViewOfFile(v5);
  if ( v6 )
    CloseHandle(v6);
  if ( v8 != (void *)-1LL )
    CloseHandle(v8);
  return (unsigned int)CatalogHint;
}

```

## disassembly

```asm
0x18007a7e4  mov     rax, rsp
0x18007a7e7  push    rbx
0x18007a7e8  push    rbp
0x18007a7e9  push    rsi
0x18007a7ea  push    rdi
0x18007a7eb  push    r12
0x18007a7ed  push    r13
0x18007a7ef  push    r14
0x18007a7f1  push    r15
0x18007a7f3  sub     rsp, 58h
0x18007a7f7  xor     ebx, ebx
0x18007a7f9  mov     r13, rdx
0x18007a7fc  mov     [rax-68h], rbx
0x18007a800  xor     r9d, r9d; lpSecurityAttributes
0x18007a803  mov     dword ptr [rax-70h], 8000080h
0x18007a80a  mov     edx, 80000000h; dwDesiredAccess
0x18007a80f  mov     r12, rcx
0x18007a812  mov     [rax+20h], rbx
0x18007a816  lea     r8d, [rbx+5]; dwShareMode
0x18007a81a  mov     [rax-58h], rbx
0x18007a81e  mov     esi, ebx
0x18007a820  mov     dword ptr [rax-78h], 3
0x18007a827  mov     edi, ebx
0x18007a829  mov     r14d, ebx
0x18007a82c  mov     r15d, ebx
0x18007a82f  call    cs:__imp_CreateFileW
0x18007a836  nop     dword ptr [rax+rax+00h]
0x18007a83b  mov     rbp, rax
0x18007a83e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007a842  jz      loc_18007A984
0x18007a848  lea     rdx, [rsp+98h+FileSize]; lpFileSize
0x18007a850  mov     rcx, rax; hFile
0x18007a853  call    cs:__imp_GetFileSizeEx
0x18007a85a  nop     dword ptr [rax+rax+00h]
0x18007a85f  test    eax, eax
0x18007a861  jz      loc_18007A984
0x18007a867  cmp     dword ptr [rsp+98h+FileSize+4], ebx
0x18007a86e  jnz     loc_18007A95A
0x18007a874  mov     rbx, qword ptr [rsp+98h+FileSize]
0x18007a87c  test    ebx, ebx
0x18007a87e  jz      loc_18007A95A
0x18007a884  mov     [rsp+98h+lpName], r15; lpName
0x18007a889  lea     r8d, [r15+2]; flProtect
0x18007a88d  xor     r9d, r9d; dwMaximumSizeHigh
0x18007a890  mov     [rsp+98h+dwMaximumSizeLow], esi; dwMaximumSizeLow
0x18007a894  xor     edx, edx; lpFileMappingAttributes
0x18007a896  mov     rcx, rbp; hFile
0x18007a899  call    cs:__imp_CreateFileMappingW
0x18007a8a0  nop     dword ptr [rax+rax+00h]
0x18007a8a5  mov     r15, rax
0x18007a8a8  test    rax, rax
0x18007a8ab  jz      loc_18007A984
0x18007a8b1  xor     r9d, r9d; dwFileOffsetLow
0x18007a8b4  mov     qword ptr [rsp+98h+dwMaximumSizeLow], r14; dwNumberOfBytesToMap
0x18007a8b9  xor     r8d, r8d; dwFileOffsetHigh
0x18007a8bc  lea     edx, [r14+4]; dwDesiredAccess
0x18007a8c0  mov     rcx, rax; hFileMappingObject
0x18007a8c3  call    cs:__imp_MapViewOfFile
0x18007a8ca  nop     dword ptr [rax+rax+00h]
0x18007a8cf  mov     r14, rax
0x18007a8d2  test    rax, rax
0x18007a8d5  jz      loc_18007A984
0x18007a8db  lea     edx, [rdi+5Ch]; Ch
0x18007a8de  mov     rcx, r12; Str
0x18007a8e1  call    cs:__imp_wcsrchr
0x18007a8e8  nop     dword ptr [rax+rax+00h]
0x18007a8ed  mov     rdi, rax
0x18007a8f0  test    rax, rax
0x18007a8f3  jnz     short loc_18007A8FA
0x18007a8f5  mov     rdi, r12
0x18007a8f8  jmp     short loc_18007A8FE
0x18007a8fa  add     rdi, 2
0x18007a8fe  mov     [rsp+98h+lpName], rsi; pCreatePara
0x18007a903  mov     r9d, ebx; cbEncoded
0x18007a906  mov     r8, r14; pbEncoded
0x18007a909  mov     [rsp+98h+dwMaximumSizeLow], 5; dwFlags
0x18007a911  mov     edx, 10001h; dwEncodingType
0x18007a916  mov     ecx, 3; dwContextType
0x18007a91b  call    cs:__imp_CertCreateContext
0x18007a922  nop     dword ptr [rax+rax+00h]
0x18007a927  mov     rsi, rax
0x18007a92a  test    rax, rax
0x18007a92d  jz      short loc_18007A984
0x18007a92f  lea     rdx, [rsp+98h+P]
0x18007a934  mov     rcx, rdi; SourceString
0x18007a937  call    CiCreateCatalogHint
0x18007a93c  mov     rdi, [rsp+98h+P]
0x18007a941  mov     ebx, eax
0x18007a943  test    eax, eax
0x18007a945  js      short loc_18007A95F
0x18007a947  mov     rcx, [rsi+18h]
0x18007a94b  mov     r8, rdi
0x18007a94e  mov     rdx, r13
0x18007a951  call    CipSetEasForEachHint
0x18007a956  mov     ebx, eax
0x18007a958  jmp     short loc_18007A95F
0x18007a95a  mov     ebx, 0C000011Eh
0x18007a95f  test    rdi, rdi
0x18007a962  jz      short loc_18007A9AC
0x18007a964  mov     rcx, gs:60h
0x18007a96d  mov     r8, rdi; P
0x18007a970  xor     edx, edx; Flags
0x18007a972  mov     rcx, [rcx+30h]; HeapHandle
0x18007a976  call    cs:__imp_RtlFreeHeap
0x18007a97d  nop     dword ptr [rax+rax+00h]
0x18007a982  jmp     short loc_18007A9AC
0x18007a984  call    cs:__imp_GetLastError
0x18007a98b  nop     dword ptr [rax+rax+00h]
0x18007a990  mov     ebx, eax
0x18007a992  test    eax, eax
0x18007a994  jle     short loc_18007A99F
0x18007a996  movzx   ebx, ax
0x18007a999  or      ebx, 80070000h
0x18007a99f  and     ebx, 0EFFFFFFFh
0x18007a9a5  jl      short loc_18007A9AC
0x18007a9a7  mov     ebx, 0C0000001h
0x18007a9ac  test    rsi, rsi
0x18007a9af  jz      short loc_18007A9C0
0x18007a9b1  mov     rcx, rsi; pCtlContext
0x18007a9b4  call    cs:__imp_CertFreeCTLContext
0x18007a9bb  nop     dword ptr [rax+rax+00h]
0x18007a9c0  test    r14, r14
0x18007a9c3  jz      short loc_18007A9D4
0x18007a9c5  mov     rcx, r14; lpBaseAddress
0x18007a9c8  call    cs:__imp_UnmapViewOfFile
0x18007a9cf  nop     dword ptr [rax+rax+00h]
0x18007a9d4  test    r15, r15
0x18007a9d7  jz      short loc_18007A9E8
0x18007a9d9  mov     rcx, r15; hObject
0x18007a9dc  call    cs:__imp_CloseHandle
0x18007a9e3  nop     dword ptr [rax+rax+00h]
0x18007a9e8  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18007a9ec  jz      short loc_18007A9FD
0x18007a9ee  mov     rcx, rbp; hObject
0x18007a9f1  call    cs:__imp_CloseHandle
0x18007a9f8  nop     dword ptr [rax+rax+00h]
0x18007a9fd  mov     eax, ebx
0x18007a9ff  add     rsp, 58h
0x18007aa03  pop     r15
0x18007aa05  pop     r14
0x18007aa07  pop     r13
0x18007aa09  pop     r12
0x18007aa0b  pop     rdi
0x18007aa0c  pop     rsi
0x18007aa0d  pop     rbp
0x18007aa0e  pop     rbx
0x18007aa0f  retn
```
