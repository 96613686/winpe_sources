# _SortedCatalogInfoCreate

- ea: `0x180003510`
- end: `0x1800037c3`
- name: `_SortedCatalogInfoCreate`
- size: `691`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800037cc`

## callees

- `0x180001e58`
- `0x180003510`
- `0x180007820`
- `0x18004de52`
- `0x18004de6a`

## import_xrefs

- `msvcrt!_stricmp` at `0x1800036c2`
- `msvcrt!_stricmp` at `0x1800036c2`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800036a1`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800036a1`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800035fd`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800035fd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800035e3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800035e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003740`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000377d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800037a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003740`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000377d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800037a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800036fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000378b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800037a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800036fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000378b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800037a9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000353a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000353a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000371f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003731`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000371f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003731`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180003626`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180003626`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000370e`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000370e`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000364b`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000364b`
- `CRYPT32!CertCreateContext` at `0x180003686`
- `CRYPT32!CertCreateContext` at `0x180003686`

## pseudocode

```c
__int64 __fastcall SortedCatalogInfoCreate(_WORD *Src)
{
  __int64 v2; // rax
  bool v3; // zf
  unsigned int v4; // esi
  HLOCAL v5; // rax
  __int64 v6; // rdi
  const WCHAR *v7; // rcx
  const BYTE **v8; // r15
  int v9; // ebx
  __int64 v10; // r13
  void *v11; // rbp
  const BYTE *v12; // r14
  HANDLE FileW; // rax
  void *v14; // rsi
  DWORD FileSize; // eax
  SIZE_T v16; // r15
  HANDLE FileMappingW; // rax
  const BYTE *v18; // rax
  const void *Context; // rax
  __int64 result; // rax
  DWORD LastError; // esi
  __int64 v22; // rax

  v2 = -1;
  do
    v3 = Src[++v2] == 0;
  while ( !v3 );
  v4 = v2 + 1;
  v5 = LocalAlloc(0, (unsigned int)(2 * (v2 + 1) + 136));
  v6 = (__int64)v5;
  if ( v5 )
  {
    memset_0(v5, 0, 0x88u);
    *(_QWORD *)(v6 + 24) = v6 + 136;
    memcpy_0((void *)(v6 + 136), Src, 2LL * v4);
    v7 = *(const WCHAR **)(v6 + 24);
    v8 = (const BYTE **)(v6 + 104);
    v9 = 0;
    *(_DWORD *)(v6 + 16) = 1;
    v10 = -1;
    if ( v7 && *v7 )
    {
      v11 = 0;
      v12 = 0;
      FileW = CreateFileW(v7, 0x80000000, 5u, 0, 3u, 0x80u, 0);
      v14 = FileW;
      if ( FileW != (HANDLE)-1LL )
      {
        v10 = (__int64)FileW;
        FileSize = GetFileSize(FileW, 0);
        v16 = FileSize;
        if ( FileSize != -1 || !GetLastError() )
        {
          FileMappingW = CreateFileMappingW(v14, 0, 2u, 0, 0, 0);
          v11 = FileMappingW;
          if ( FileMappingW )
          {
            v18 = (const BYTE *)MapViewOfFile(FileMappingW, 4u, 0, 0, v16);
            v12 = v18;
            if ( v18 )
            {
              *(_QWORD *)(v6 + 96) = v11;
              *(_QWORD *)(v6 + 104) = v18;
              *(_QWORD *)(v6 + 88) = v14;
              Context = CertCreateContext(3u, 0x10001u, v18, v16, 3u, 0);
              *(_QWORD *)(v6 + 112) = Context;
              if ( Context )
              {
                if ( GetFileInformationByHandle(*(HANDLE *)(v6 + 88), (LPBY_HANDLE_FILE_INFORMATION)(v6 + 32)) )
                {
                  v3 = _stricmp(
                         *(const char **)(*(_QWORD *)(*(_QWORD *)(v6 + 112) + 24LL) + 72LL),
                         "1.3.6.1.4.1.311.12.1.3") == 0;
                  result = v6;
                  LOBYTE(v9) = v3;
                  *(_DWORD *)(v6 + 128) = v9;
                  return result;
                }
                goto LABEL_22;
              }
              v8 = (const BYTE **)(v6 + 104);
              v22 = v6 + 96;
LABEL_21:
              *(_QWORD *)(v6 + 112) = 0;
              CatUtil_Close(v22, v8, v6 + 88);
LABEL_22:
              SortedCatalogInfoFree((HLOCAL)v6);
              return 0;
            }
          }
        }
        v8 = (const BYTE **)(v6 + 104);
      }
      LastError = GetLastError();
      if ( v12 )
      {
        UnmapViewOfFile(v12);
        v12 = 0;
      }
      if ( v11 )
      {
        CloseHandle(v11);
        v11 = 0;
      }
      if ( v10 != -1 )
      {
        CloseHandle((HANDLE)v10);
        v10 = -1;
      }
    }
    else
    {
      SetLastError(0x57u);
      v12 = 0;
      v11 = 0;
      LastError = GetLastError();
    }
    SetLastError(LastError);
    *(_QWORD *)(v6 + 96) = v11;
    v22 = v6 + 96;
    *v8 = v12;
    *(_QWORD *)(v6 + 88) = v10;
    goto LABEL_21;
  }
  SetLastError(8u);
  return 0;
}

```

## disassembly

```asm
0x180003510  push    rbx
0x180003512  push    rsi
0x180003513  push    rdi
0x180003514  sub     rsp, 50h
0x180003518  mov     rbx, rcx
0x18000351b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180003522  cmp     word ptr [rcx+rax*2+2], 0
0x180003528  lea     rax, [rax+1]
0x18000352c  jnz     short loc_180003522
0x18000352e  lea     esi, [rax+1]
0x180003531  xor     ecx, ecx; uFlags
0x180003533  lea     edx, ds:88h[rsi*2]; uBytes
0x18000353a  call    cs:__imp_LocalAlloc
0x180003540  mov     rdi, rax
0x180003543  test    rax, rax
0x180003546  jz      loc_180003778
0x18000354c  mov     [rsp+68h+arg_0], rbp
0x180003551  mov     [rsp+68h+arg_8], r12
0x180003556  mov     [rsp+68h+arg_10], r13
0x18000355e  mov     [rsp+68h+var_20], r14
0x180003563  mov     [rsp+68h+var_28], r15
0x180003568  xor     edx, edx; Val
0x18000356a  mov     r8d, 88h; Size
0x180003570  mov     rcx, rax; void *
0x180003573  call    memset_0
0x180003578  lea     rcx, [rdi+88h]; void *
0x18000357f  mov     r8d, esi
0x180003582  add     r8, r8; Size
0x180003585  mov     [rdi+18h], rcx
0x180003589  mov     rdx, rbx; Src
0x18000358c  call    memcpy_0
0x180003591  mov     rcx, [rdi+18h]; lpFileName
0x180003595  lea     r15, [rdi+68h]
0x180003599  xor     ebx, ebx
0x18000359b  mov     dword ptr [rdi+10h], 1
0x1800035a2  mov     r13, 0FFFFFFFFFFFFFFFFh
0x1800035a9  test    rcx, rcx
0x1800035ac  jz      loc_18000379E
0x1800035b2  cmp     bx, [rcx]
0x1800035b5  jz      loc_18000379E
0x1800035bb  mov     [rsp+68h+hTemplateFile], rbx; hTemplateFile
0x1800035c0  xor     r9d, r9d; lpSecurityAttributes
0x1800035c3  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800035cb  mov     edx, 80000000h; dwDesiredAccess
0x1800035d0  mov     r8d, 5; dwShareMode
0x1800035d6  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x1800035de  mov     ebp, ebx
0x1800035e0  mov     r14d, ebx
0x1800035e3  call    cs:__imp_CreateFileW
0x1800035e9  mov     rsi, rax
0x1800035ec  cmp     rax, r13
0x1800035ef  jz      loc_1800036FE
0x1800035f5  xor     edx, edx; lpFileSizeHigh
0x1800035f7  mov     rcx, rax; hFile
0x1800035fa  mov     r13, rax
0x1800035fd  call    cs:__imp_GetFileSize
0x180003603  mov     r15d, eax
0x180003606  cmp     eax, 0FFFFFFFFh
0x180003609  jz      loc_18000378B
0x18000360f  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], rbx; lpName
0x180003614  xor     r9d, r9d; dwMaximumSizeHigh
0x180003617  xor     edx, edx; lpFileMappingAttributes
0x180003619  mov     [rsp+68h+dwCreationDisposition], ebx; dwMaximumSizeLow
0x18000361d  mov     r8d, 2; flProtect
0x180003623  mov     rcx, rsi; hFile
0x180003626  call    cs:__imp_CreateFileMappingW
0x18000362c  mov     rbp, rax
0x18000362f  test    rax, rax
0x180003632  jz      loc_1800036FA
0x180003638  xor     r9d, r9d; dwFileOffsetLow
0x18000363b  mov     qword ptr [rsp+68h+dwCreationDisposition], r15; dwNumberOfBytesToMap
0x180003640  xor     r8d, r8d; dwFileOffsetHigh
0x180003643  mov     edx, 4; dwDesiredAccess
0x180003648  mov     rcx, rax; hFileMappingObject
0x18000364b  call    cs:__imp_MapViewOfFile
0x180003651  mov     r14, rax
0x180003654  test    rax, rax
0x180003657  jz      loc_1800036FA
0x18000365d  mov     [rdi+60h], rbp
0x180003661  mov     [rdi+68h], rax
0x180003665  mov     [rdi+58h], rsi
0x180003669  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], rbx; pCreatePara
0x18000366e  mov     r9d, r15d; cbEncoded
0x180003671  mov     r8, rax; pbEncoded
0x180003674  mov     [rsp+68h+dwCreationDisposition], 3; dwFlags
0x18000367c  mov     edx, 10001h; dwEncodingType
0x180003681  mov     ecx, 3; dwContextType
0x180003686  call    cs:__imp_CertCreateContext
0x18000368c  mov     [rdi+70h], rax
0x180003690  test    rax, rax
0x180003693  jz      loc_1800037B9
0x180003699  mov     rcx, [rdi+58h]; hFile
0x18000369d  lea     rdx, [rdi+20h]; lpFileInformation
0x1800036a1  call    cs:__imp_GetFileInformationByHandle
0x1800036a7  test    eax, eax
0x1800036a9  jz      loc_180003768
0x1800036af  mov     rcx, [rdi+70h]
0x1800036b3  lea     rdx, a1361413111213; "1.3.6.1.4.1.311.12.1.3"
0x1800036ba  mov     rcx, [rcx+18h]
0x1800036be  mov     rcx, [rcx+48h]; String1
0x1800036c2  call    cs:__imp__stricmp
0x1800036c8  test    eax, eax
0x1800036ca  mov     rax, rdi
0x1800036cd  setz    bl
0x1800036d0  mov     [rdi+80h], ebx
0x1800036d6  mov     r14, [rsp+68h+var_20]
0x1800036db  mov     r13, [rsp+68h+arg_10]
0x1800036e3  mov     r12, [rsp+68h+arg_8]
0x1800036e8  mov     rbp, [rsp+68h+arg_0]
0x1800036ed  mov     r15, [rsp+68h+var_28]
0x1800036f2  add     rsp, 50h
0x1800036f6  pop     rdi
0x1800036f7  pop     rsi
0x1800036f8  pop     rbx
0x1800036f9  retn
0x1800036fa  lea     r15, [rdi+68h]
0x1800036fe  call    cs:__imp_GetLastError
0x180003704  mov     esi, eax
0x180003706  test    r14, r14
0x180003709  jz      short loc_180003717
0x18000370b  mov     rcx, r14; lpBaseAddress
0x18000370e  call    cs:__imp_UnmapViewOfFile
0x180003714  mov     r14, rbx
0x180003717  test    rbp, rbp
0x18000371a  jz      short loc_180003728
0x18000371c  mov     rcx, rbp; hObject
0x18000371f  call    cs:__imp_CloseHandle
0x180003725  mov     rbp, rbx
0x180003728  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x18000372c  jz      short loc_18000373E
0x18000372e  mov     rcx, r13; hObject
0x180003731  call    cs:__imp_CloseHandle
0x180003737  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18000373e  mov     ecx, esi; dwErrCode
0x180003740  call    cs:__imp_SetLastError
0x180003746  mov     [rdi+60h], rbp
0x18000374a  lea     rax, [rdi+60h]
0x18000374e  mov     [r15], r14
0x180003751  mov     [rdi+58h], r13
0x180003755  lea     r8, [rdi+58h]
0x180003759  mov     [rdi+70h], rbx
0x18000375d  mov     rdx, r15
0x180003760  mov     rcx, rax
0x180003763  call    CatUtil_Close
0x180003768  mov     rcx, rdi; hMem
0x18000376b  call    _SortedCatalogInfoFree
0x180003770  mov     rax, rbx
0x180003773  jmp     loc_1800036D6
0x180003778  mov     ecx, 8; dwErrCode
0x18000377d  call    cs:__imp_SetLastError
0x180003783  mov     rax, rdi
0x180003786  jmp     loc_1800036F2
0x18000378b  call    cs:__imp_GetLastError
0x180003791  test    eax, eax
0x180003793  jnz     loc_1800036FA
0x180003799  jmp     loc_18000360F
0x18000379e  mov     ecx, 57h ; 'W'; dwErrCode
0x1800037a3  call    cs:__imp_SetLastError
0x1800037a9  call    cs:__imp_GetLastError
0x1800037af  mov     r14, rbx
0x1800037b2  mov     rbp, rbx
0x1800037b5  mov     esi, eax
0x1800037b7  jmp     short loc_18000373E
0x1800037b9  lea     r15, [rdi+68h]
0x1800037bd  lea     rax, [rdi+60h]
0x1800037c1  jmp     short loc_180003755
```
