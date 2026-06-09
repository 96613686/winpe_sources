# CatalogLoadFileData

- ea: `0x180001cd8`
- end: `0x180001e52`
- name: `CatalogLoadFileData`
- size: `378`
- prototype: `__int64 __fastcall(struct CRYPTCATSTORE_ *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002028`
- `0x1800079c0`

## callees

- `0x180001cd8`
- `0x1800024e0`
- `0x180002fd0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180001d29`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180001d29`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180001d11`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180001d11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001d9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001e0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001e28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001d9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001e0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001e28`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180001e03`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180001e03`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180001d92`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180001d92`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x180001d65`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x180001d65`
- `CRYPT32!CertCreateContext` at `0x180001dcd`
- `CRYPT32!CertCreateContext` at `0x180001dcd`
- `CRYPT32!CertFreeCTLContext` at `0x180001dec`
- `CRYPT32!CertFreeCTLContext` at `0x180001dec`

## pseudocode

```c
__int64 __fastcall CatalogLoadFileData(struct CRYPTCATSTORE_ *a1)
{
  HANDLE FileW; // rax
  void *v3; // rbx
  DWORD FileSize; // eax
  DWORD v5; // esi
  unsigned int v6; // edi
  char *FileMappingA; // rax
  void *v8; // r15
  BYTE *v9; // rbp
  const CTL_CONTEXT *Context; // rax
  const CTL_CONTEXT *v11; // r15

  FileW = CreateFileW(a1->pwszP7File, 0x80000000, 5u, 0, 3u, 0x8000080u, 0);
  v3 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return 0;
  FileSize = GetFileSize(FileW, 0);
  v5 = FileSize;
  v6 = 1;
  if ( FileSize != -1 )
  {
    if ( FileSize < 0xA )
    {
LABEL_12:
      CloseHandle(v3);
      return v6;
    }
    goto LABEL_4;
  }
  if ( !GetLastError() )
  {
LABEL_4:
    FileMappingA = (char *)CreateFileMappingA(v3, 0, 2u, 0, 0, 0);
    v8 = FileMappingA;
    if ( (unsigned __int64)(FileMappingA - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v9 = (BYTE *)MapViewOfFile(FileMappingA, 4u, 0, 0, 0);
      CloseHandle(v8);
      if ( v9 )
      {
        if ( v5 )
        {
          Context = (const CTL_CONTEXT *)CertCreateContext(3u, a1->dwEncodingType, v9, v5, 5u, 0);
          v11 = Context;
          if ( Context )
          {
            v6 = CatalogFillCatStore(a1, Context->pCtlInfo);
            CertFreeCTLContext(v11);
            if ( v6 )
            {
              if ( (a1->fdwStoreFlags & 0x20000000) != 0 )
                a1->hCryptMsg = CatUtil_NoContentMsgDecode(v9, v5);
            }
          }
          else
          {
            v6 = 0;
          }
        }
        UnmapViewOfFile(v9);
        goto LABEL_12;
      }
    }
  }
  CloseHandle(v3);
  return 0;
}

```

## disassembly

```asm
0x180001cd8  push    rbx
0x180001cda  push    rbp
0x180001cdb  push    rsi
0x180001cdc  push    rdi
0x180001cdd  push    r14
0x180001cdf  push    r15
0x180001ce1  sub     rsp, 48h
0x180001ce5  xor     r9d, r9d; lpSecurityAttributes
0x180001ce8  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x180001cf1  mov     r14, rcx
0x180001cf4  mov     [rsp+78h+dwFlagsAndAttributes], 8000080h; dwFlagsAndAttributes
0x180001cfc  mov     rcx, [rcx+8]; lpFileName
0x180001d00  mov     edx, 80000000h; dwDesiredAccess
0x180001d05  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x180001d0d  lea     r8d, [r9+5]; dwShareMode
0x180001d11  call    cs:__imp_CreateFileW
0x180001d17  mov     rbx, rax
0x180001d1a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180001d1e  jz      loc_180001E2E
0x180001d24  xor     edx, edx; lpFileSizeHigh
0x180001d26  mov     rcx, rax; hFile
0x180001d29  call    cs:__imp_GetFileSize
0x180001d2f  mov     esi, eax
0x180001d31  mov     edi, 1
0x180001d36  cmp     eax, 0FFFFFFFFh
0x180001d39  jz      loc_180001E32
0x180001d3f  cmp     eax, 0Ah
0x180001d42  jb      loc_180001E09
0x180001d48  xor     r9d, r9d; dwMaximumSizeHigh
0x180001d4b  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], 0; lpName
0x180001d54  xor     edx, edx; lpFileMappingAttributes
0x180001d56  mov     [rsp+78h+dwCreationDisposition], 0; dwMaximumSizeLow
0x180001d5e  mov     rcx, rbx; hFile
0x180001d61  lea     r8d, [r9+2]; flProtect
0x180001d65  call    cs:__imp_CreateFileMappingA
0x180001d6b  mov     r15, rax
0x180001d6e  lea     rcx, [rax-1]
0x180001d72  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180001d76  ja      loc_180001E25
0x180001d7c  xor     r9d, r9d; dwFileOffsetLow
0x180001d7f  mov     qword ptr [rsp+78h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x180001d88  xor     r8d, r8d; dwFileOffsetHigh
0x180001d8b  mov     rcx, rax; hFileMappingObject
0x180001d8e  lea     edx, [r9+4]; dwDesiredAccess
0x180001d92  call    cs:__imp_MapViewOfFile
0x180001d98  mov     rcx, r15; hObject
0x180001d9b  mov     rbp, rax
0x180001d9e  call    cs:__imp_CloseHandle
0x180001da4  test    rbp, rbp
0x180001da7  jz      short loc_180001E25
0x180001da9  cmp     esi, edi
0x180001dab  jb      short loc_180001E00
0x180001dad  mov     edx, [r14+18h]; dwEncodingType
0x180001db1  mov     r9d, esi; cbEncoded
0x180001db4  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], 0; pCreatePara
0x180001dbd  mov     r8, rbp; pbEncoded
0x180001dc0  mov     ecx, 3; dwContextType
0x180001dc5  mov     [rsp+78h+dwCreationDisposition], 5; dwFlags
0x180001dcd  call    cs:__imp_CertCreateContext
0x180001dd3  mov     r15, rax
0x180001dd6  test    rax, rax
0x180001dd9  jz      short loc_180001E21
0x180001ddb  mov     rdx, [rax+18h]; struct _CTL_INFO *
0x180001ddf  mov     rcx, r14; struct CRYPTCATSTORE_ *
0x180001de2  call    ?CatalogFillCatStore@@YAHPEAUCRYPTCATSTORE_@@PEAU_CTL_INFO@@@Z; CatalogFillCatStore(CRYPTCATSTORE_ *,_CTL_INFO *)
0x180001de7  mov     rcx, r15; pCtlContext
0x180001dea  mov     edi, eax
0x180001dec  call    cs:__imp_CertFreeCTLContext
0x180001df2  test    edi, edi
0x180001df4  jz      short loc_180001E00
0x180001df6  test    dword ptr [r14+1Ch], 20000000h
0x180001dfe  jnz     short loc_180001E42
0x180001e00  mov     rcx, rbp; lpBaseAddress
0x180001e03  call    cs:__imp_UnmapViewOfFile
0x180001e09  mov     rcx, rbx; hObject
0x180001e0c  call    cs:__imp_CloseHandle
0x180001e12  mov     eax, edi
0x180001e14  add     rsp, 48h
0x180001e18  pop     r15
0x180001e1a  pop     r14
0x180001e1c  pop     rdi
0x180001e1d  pop     rsi
0x180001e1e  pop     rbp
0x180001e1f  pop     rbx
0x180001e20  retn
0x180001e21  xor     edi, edi
0x180001e23  jmp     short loc_180001E00
0x180001e25  mov     rcx, rbx; hObject
0x180001e28  call    cs:__imp_CloseHandle
0x180001e2e  xor     eax, eax
0x180001e30  jmp     short loc_180001E14
0x180001e32  call    cs:__imp_GetLastError
0x180001e38  test    eax, eax
0x180001e3a  jz      loc_180001D48
0x180001e40  jmp     short loc_180001E25
0x180001e42  mov     edx, esi
0x180001e44  mov     rcx, rbp; pbData
0x180001e47  call    CatUtil_NoContentMsgDecode
0x180001e4c  mov     [r14+30h], rax
0x180001e50  jmp     short loc_180001E00
```
