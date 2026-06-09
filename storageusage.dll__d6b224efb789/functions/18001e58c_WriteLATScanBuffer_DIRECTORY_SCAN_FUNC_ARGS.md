# WriteLATScanBuffer(DIRECTORY_SCAN_FUNC_ARGS *)

- ea: `0x18001e58c`
- end: `0x18001ea1b`
- name: `?WriteLATScanBuffer@@YAXPEAUDIRECTORY_SCAN_FUNC_ARGS@@@Z`
- size: `1167`
- prototype: `void __fastcall(struct DIRECTORY_SCAN_FUNC_ARGS *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001ad40`

## callees

- `0x1800010b0`
- `0x180002ac8`
- `0x180005c94`
- `0x18001e58c`
- `0x180022684`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e60e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e668`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e6ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e70c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e765`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e7bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e811`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e864`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e8be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e60e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e668`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e6ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e70c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e765`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e7bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e811`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e864`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e8be`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001e9a9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001e9a9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001e5f7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001e65e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001e6b0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001e702`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001e75b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001e7b1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001e807`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001e85a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001e8b0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001e5f7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001e65e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001e6b0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001e702`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001e75b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001e7b1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001e807`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001e85a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001e8b0`

## string_xrefs

- `0x18001e5eb`: `<FilePaths>`

## pseudocode

```c
void __fastcall WriteLATScanBuffer(struct DIRECTORY_SCAN_FUNC_ARGS *a1, __int64 a2, __int64 a3)
{
  int v3; // edi
  void *v5; // rcx
  signed int LastError; // eax
  _WORD *v7; // r15
  void **v8; // r14
  signed int v9; // eax
  signed int v10; // eax
  signed int v11; // eax
  void **v12; // rsi
  DWORD v13; // edi
  signed int v14; // eax
  signed int v15; // eax
  signed int v16; // eax
  signed int v17; // eax
  signed int v18; // eax
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  void *v22; // rcx
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-89h] BYREF
  int v24; // [rsp+54h] [rbp-85h] BYREF
  char *v25; // [rsp+58h] [rbp-81h] BYREF
  __int64 v26; // [rsp+60h] [rbp-79h] BYREF
  __int64 v27; // [rsp+68h] [rbp-71h] BYREF
  __int16 v28; // [rsp+70h] [rbp-69h]
  __int64 v29; // [rsp+78h] [rbp-61h] BYREF
  __int16 v30; // [rsp+80h] [rbp-59h]
  _BYTE v31[160]; // [rsp+90h] [rbp-49h] BYREF

  v3 = *((unsigned __int16 *)a1 + 60);
  if ( (_WORD)v3 )
  {
    if ( *((_BYTE *)a1 + 700) )
    {
      memset_0(v31, 0, 0x60u);
      v5 = (void *)*((_QWORD *)a1 + 21);
      NumberOfBytesWritten = 0;
      if ( !WriteFile(v5, L"<FilePaths>", 0x18u, &NumberOfBytesWritten, 0) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        RecordDirScanFailures((struct _FILE_ID_EXTD_DIR_INFORMATION *)v31, a1, L"<WER_Failure>", LastError, 0x516u);
      }
      v7 = (_WORD *)((char *)a1 + 128);
      v8 = (void **)((char *)a1 + 136);
      if ( !WriteFile(
              *((HANDLE *)a1 + 21),
              *((LPCVOID *)a1 + 17),
              *((unsigned __int16 *)a1 + 64),
              &NumberOfBytesWritten,
              0) )
      {
        v9 = GetLastError();
        if ( v9 > 0 )
          v9 = (unsigned __int16)v9 | 0x80070000;
        RecordDirScanFailures((struct _FILE_ID_EXTD_DIR_INFORMATION *)v31, a1, L"<WER_Failure>", v9, 0x51Cu);
      }
      if ( !WriteFile(*((HANDLE *)a1 + 21), L"\n", 4u, &NumberOfBytesWritten, 0) )
      {
        v10 = GetLastError();
        if ( v10 > 0 )
          v10 = (unsigned __int16)v10 | 0x80070000;
        RecordDirScanFailures((struct _FILE_ID_EXTD_DIR_INFORMATION *)v31, a1, L"<WER_Failure>", v10, 0x522u);
      }
      if ( !WriteFile(*((HANDLE *)a1 + 21), L"<FileSizes>", 0x18u, &NumberOfBytesWritten, 0) )
      {
        v11 = GetLastError();
        if ( v11 > 0 )
          v11 = (unsigned __int16)v11 | 0x80070000;
        RecordDirScanFailures((struct _FILE_ID_EXTD_DIR_INFORMATION *)v31, a1, L"<WER_Failure>", v11, 0x52Cu);
      }
      v12 = (void **)((char *)a1 + 144);
      v13 = 8 * v3;
      if ( !WriteFile(*((HANDLE *)a1 + 21), *((LPCVOID *)a1 + 18), v13, &NumberOfBytesWritten, 0) )
      {
        v14 = GetLastError();
        if ( v14 > 0 )
          v14 = (unsigned __int16)v14 | 0x80070000;
        RecordDirScanFailures((struct _FILE_ID_EXTD_DIR_INFORMATION *)v31, a1, L"<WER_Failure>", v14, 0x532u);
      }
      if ( !WriteFile(*((HANDLE *)a1 + 21), L"\n", 4u, &NumberOfBytesWritten, 0) )
      {
        v15 = GetLastError();
        if ( v15 > 0 )
          v15 = (unsigned __int16)v15 | 0x80070000;
        RecordDirScanFailures((struct _FILE_ID_EXTD_DIR_INFORMATION *)v31, a1, L"<WER_Failure>", v15, 0x538u);
      }
      if ( !WriteFile(*((HANDLE *)a1 + 21), L"<LATS>", 0xEu, &NumberOfBytesWritten, 0) )
      {
        v16 = GetLastError();
        if ( v16 > 0 )
          v16 = (unsigned __int16)v16 | 0x80070000;
        RecordDirScanFailures((struct _FILE_ID_EXTD_DIR_INFORMATION *)v31, a1, L"<WER_Failure>", v16, 0x542u);
      }
      if ( !WriteFile(*((HANDLE *)a1 + 21), *((LPCVOID *)a1 + 19), v13, &NumberOfBytesWritten, 0) )
      {
        v17 = GetLastError();
        if ( v17 > 0 )
          v17 = (unsigned __int16)v17 | 0x80070000;
        RecordDirScanFailures((struct _FILE_ID_EXTD_DIR_INFORMATION *)v31, a1, L"<WER_Failure>", v17, 0x548u);
      }
      if ( !WriteFile(*((HANDLE *)a1 + 21), L"\n", 4u, &NumberOfBytesWritten, 0) )
      {
        v18 = GetLastError();
        if ( v18 > 0 )
          v18 = (unsigned __int16)v18 | 0x80070000;
        RecordDirScanFailures((struct _FILE_ID_EXTD_DIR_INFORMATION *)v31, a1, L"<WER_Failure>", v18, 0x54Eu);
      }
    }
    else
    {
      if ( (unsigned int)dword_180040010 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180040010, 0x400000000000LL, a3) )
      {
        LOWORD(NumberOfBytesWritten) = *((_WORD *)a1 + 40);
        v25 = (char *)a1 + 128;
        v27 = *((_QWORD *)a1 + 19);
        v29 = *((_QWORD *)a1 + 18);
        v24 = *(_DWORD *)a1;
        v28 = v3;
        v30 = v3;
        v26 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperArray<8>,_tlgWrapperArray<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<2>>(
          v19,
          (unsigned int)byte_180037A13,
          v20,
          v21,
          (__int64)&v26,
          (__int64)&v24,
          (__int64)&v29,
          (__int64)&v27,
          (__int64)&v25,
          (__int64)&NumberOfBytesWritten);
      }
      Sleep(0x28u);
      v12 = (void **)((char *)a1 + 144);
      v8 = (void **)((char *)a1 + 136);
      v7 = (_WORD *)((char *)a1 + 128);
    }
    v22 = *v12;
    *((_WORD *)a1 + 60) = 0;
    memset_0(v22, 0, 0x1F40u);
    memset_0(*((void **)a1 + 19), 0, 0x1F40u);
    memset_0(*v8, 0, *((unsigned __int16 *)a1 + 65));
    *v7 = 0;
    *((_WORD *)a1 + 40) = 0;
  }
}

```

## disassembly

```asm
0x18001e58c  push    rbp
0x18001e58e  push    rbx
0x18001e58f  push    rsi
0x18001e590  push    rdi
0x18001e591  push    r12
0x18001e593  push    r13
0x18001e595  push    r14
0x18001e597  push    r15
0x18001e599  lea     rbp, [rsp-1Fh]
0x18001e59e  sub     rsp, 0F8h
0x18001e5a5  movzx   edi, word ptr [rcx+78h]
0x18001e5a9  xor     r12d, r12d
0x18001e5ac  mov     rbx, rcx
0x18001e5af  test    di, di
0x18001e5b2  jz      loc_18001EA07
0x18001e5b8  cmp     [rcx+2BCh], r12b
0x18001e5bf  jz      loc_18001E8F1
0x18001e5c5  xor     edx, edx; Val
0x18001e5c7  lea     r8d, [r12+60h]; Size
0x18001e5cc  lea     rcx, [rbp+57h+var_A0]; void *
0x18001e5d0  call    memset_0
0x18001e5d5  mov     rcx, [rbx+0A8h]; hFile
0x18001e5dc  lea     r9, [rsp+130h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001e5e1  lea     r8d, [r12+18h]; nNumberOfBytesToWrite
0x18001e5e6  mov     [rsp+130h+NumberOfBytesWritten], r12d
0x18001e5eb  lea     rdx, aFilepaths; "<FilePaths>"
0x18001e5f2  mov     [rsp+130h+lpOverlapped], r12; lpOverlapped
0x18001e5f7  call    cs:__imp_WriteFile
0x18001e5fd  mov     r13d, 80070000h
0x18001e603  lea     rsi, aWerFailure; "<WER_Failure>"
0x18001e60a  test    eax, eax
0x18001e60c  jnz     short loc_18001E638
0x18001e60e  call    cs:__imp_GetLastError
0x18001e614  test    eax, eax
0x18001e616  jle     short loc_18001E61E
0x18001e618  movzx   eax, ax
0x18001e61b  or      eax, r13d
0x18001e61e  mov     r9d, eax; int
0x18001e621  mov     dword ptr [rsp+130h+lpOverlapped], 516h; unsigned int
0x18001e629  mov     r8, rsi; unsigned __int16 *
0x18001e62c  lea     rcx, [rbp+57h+var_A0]; struct _FILE_ID_EXTD_DIR_INFORMATION *
0x18001e630  mov     rdx, rbx; struct DIRECTORY_SCAN_FUNC_ARGS *
0x18001e633  call    ?RecordDirScanFailures@@YAJPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAUDIRECTORY_SCAN_FUNC_ARGS@@PEBGJI@Z; RecordDirScanFailures(_FILE_ID_EXTD_DIR_INFORMATION *,DIRECTORY_SCAN_FUNC_ARGS *,ushort const *,long,uint)
0x18001e638  mov     rcx, [rbx+0A8h]; hFile
0x18001e63f  lea     r15, [rbx+80h]
0x18001e646  movzx   r8d, word ptr [r15]; nNumberOfBytesToWrite
0x18001e64a  lea     r14, [rbx+88h]
0x18001e651  mov     rdx, [r14]; lpBuffer
0x18001e654  lea     r9, [rsp+130h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001e659  mov     [rsp+130h+lpOverlapped], r12; lpOverlapped
0x18001e65e  call    cs:__imp_WriteFile
0x18001e664  test    eax, eax
0x18001e666  jnz     short loc_18001E692
0x18001e668  call    cs:__imp_GetLastError
0x18001e66e  test    eax, eax
0x18001e670  jle     short loc_18001E678
0x18001e672  movzx   eax, ax
0x18001e675  or      eax, r13d
0x18001e678  mov     r9d, eax; int
0x18001e67b  mov     dword ptr [rsp+130h+lpOverlapped], 51Ch; unsigned int
0x18001e683  mov     r8, rsi; unsigned __int16 *
0x18001e686  lea     rcx, [rbp+57h+var_A0]; struct _FILE_ID_EXTD_DIR_INFORMATION *
0x18001e68a  mov     rdx, rbx; struct DIRECTORY_SCAN_FUNC_ARGS *
0x18001e68d  call    ?RecordDirScanFailures@@YAJPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAUDIRECTORY_SCAN_FUNC_ARGS@@PEBGJI@Z; RecordDirScanFailures(_FILE_ID_EXTD_DIR_INFORMATION *,DIRECTORY_SCAN_FUNC_ARGS *,ushort const *,long,uint)
0x18001e692  mov     rcx, [rbx+0A8h]; hFile
0x18001e699  lea     r9, [rsp+130h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001e69e  mov     r8d, 4; nNumberOfBytesToWrite
0x18001e6a4  mov     [rsp+130h+lpOverlapped], r12; lpOverlapped
0x18001e6a9  lea     rdx, asc_180032078; "\n"
0x18001e6b0  call    cs:__imp_WriteFile
0x18001e6b6  test    eax, eax
0x18001e6b8  jnz     short loc_18001E6E4
0x18001e6ba  call    cs:__imp_GetLastError
0x18001e6c0  test    eax, eax
0x18001e6c2  jle     short loc_18001E6CA
0x18001e6c4  movzx   eax, ax
0x18001e6c7  or      eax, r13d
0x18001e6ca  mov     r9d, eax; int
0x18001e6cd  mov     dword ptr [rsp+130h+lpOverlapped], 522h; unsigned int
0x18001e6d5  mov     r8, rsi; unsigned __int16 *
0x18001e6d8  lea     rcx, [rbp+57h+var_A0]; struct _FILE_ID_EXTD_DIR_INFORMATION *
0x18001e6dc  mov     rdx, rbx; struct DIRECTORY_SCAN_FUNC_ARGS *
0x18001e6df  call    ?RecordDirScanFailures@@YAJPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAUDIRECTORY_SCAN_FUNC_ARGS@@PEBGJI@Z; RecordDirScanFailures(_FILE_ID_EXTD_DIR_INFORMATION *,DIRECTORY_SCAN_FUNC_ARGS *,ushort const *,long,uint)
0x18001e6e4  mov     rcx, [rbx+0A8h]; hFile
0x18001e6eb  lea     r9, [rsp+130h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001e6f0  mov     r8d, 18h; nNumberOfBytesToWrite
0x18001e6f6  mov     [rsp+130h+lpOverlapped], r12; lpOverlapped
0x18001e6fb  lea     rdx, aFilesizes; "<FileSizes>"
0x18001e702  call    cs:__imp_WriteFile
0x18001e708  test    eax, eax
0x18001e70a  jnz     short loc_18001E736
0x18001e70c  call    cs:__imp_GetLastError
0x18001e712  test    eax, eax
0x18001e714  jle     short loc_18001E71C
0x18001e716  movzx   eax, ax
0x18001e719  or      eax, r13d
0x18001e71c  mov     r9d, eax; int
0x18001e71f  mov     dword ptr [rsp+130h+lpOverlapped], 52Ch; unsigned int
0x18001e727  mov     r8, rsi; unsigned __int16 *
0x18001e72a  lea     rcx, [rbp+57h+var_A0]; struct _FILE_ID_EXTD_DIR_INFORMATION *
0x18001e72e  mov     rdx, rbx; struct DIRECTORY_SCAN_FUNC_ARGS *
0x18001e731  call    ?RecordDirScanFailures@@YAJPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAUDIRECTORY_SCAN_FUNC_ARGS@@PEBGJI@Z; RecordDirScanFailures(_FILE_ID_EXTD_DIR_INFORMATION *,DIRECTORY_SCAN_FUNC_ARGS *,ushort const *,long,uint)
0x18001e736  mov     rcx, [rbx+0A8h]; hFile
0x18001e73d  lea     rsi, [rbx+90h]
0x18001e744  mov     rdx, [rsi]; lpBuffer
0x18001e747  lea     r9, [rsp+130h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001e74c  mov     eax, edi
0x18001e74e  mov     [rsp+130h+lpOverlapped], r12; lpOverlapped
0x18001e753  shl     eax, 3
0x18001e756  mov     r8d, eax; nNumberOfBytesToWrite
0x18001e759  mov     edi, eax
0x18001e75b  call    cs:__imp_WriteFile
0x18001e761  test    eax, eax
0x18001e763  jnz     short loc_18001E793
0x18001e765  call    cs:__imp_GetLastError
0x18001e76b  test    eax, eax
0x18001e76d  jle     short loc_18001E775
0x18001e76f  movzx   eax, ax
0x18001e772  or      eax, r13d
0x18001e775  mov     r9d, eax; int
0x18001e778  mov     dword ptr [rsp+130h+lpOverlapped], 532h; unsigned int
0x18001e780  lea     r8, aWerFailure; "<WER_Failure>"
0x18001e787  mov     rdx, rbx; struct DIRECTORY_SCAN_FUNC_ARGS *
0x18001e78a  lea     rcx, [rbp+57h+var_A0]; struct _FILE_ID_EXTD_DIR_INFORMATION *
0x18001e78e  call    ?RecordDirScanFailures@@YAJPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAUDIRECTORY_SCAN_FUNC_ARGS@@PEBGJI@Z; RecordDirScanFailures(_FILE_ID_EXTD_DIR_INFORMATION *,DIRECTORY_SCAN_FUNC_ARGS *,ushort const *,long,uint)
0x18001e793  mov     rcx, [rbx+0A8h]; hFile
0x18001e79a  lea     r9, [rsp+130h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001e79f  mov     r8d, 4; nNumberOfBytesToWrite
0x18001e7a5  mov     [rsp+130h+lpOverlapped], r12; lpOverlapped
0x18001e7aa  lea     rdx, asc_180032078; "\n"
0x18001e7b1  call    cs:__imp_WriteFile
0x18001e7b7  test    eax, eax
0x18001e7b9  jnz     short loc_18001E7E9
0x18001e7bb  call    cs:__imp_GetLastError
0x18001e7c1  test    eax, eax
0x18001e7c3  jle     short loc_18001E7CB
0x18001e7c5  movzx   eax, ax
0x18001e7c8  or      eax, r13d
0x18001e7cb  mov     r9d, eax; int
0x18001e7ce  mov     dword ptr [rsp+130h+lpOverlapped], 538h; unsigned int
0x18001e7d6  lea     r8, aWerFailure; "<WER_Failure>"
0x18001e7dd  mov     rdx, rbx; struct DIRECTORY_SCAN_FUNC_ARGS *
0x18001e7e0  lea     rcx, [rbp+57h+var_A0]; struct _FILE_ID_EXTD_DIR_INFORMATION *
0x18001e7e4  call    ?RecordDirScanFailures@@YAJPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAUDIRECTORY_SCAN_FUNC_ARGS@@PEBGJI@Z; RecordDirScanFailures(_FILE_ID_EXTD_DIR_INFORMATION *,DIRECTORY_SCAN_FUNC_ARGS *,ushort const *,long,uint)
0x18001e7e9  mov     rcx, [rbx+0A8h]; hFile
0x18001e7f0  lea     r9, [rsp+130h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001e7f5  mov     r8d, 0Eh; nNumberOfBytesToWrite
0x18001e7fb  mov     [rsp+130h+lpOverlapped], r12; lpOverlapped
0x18001e800  lea     rdx, aLats; "<LATS>"
0x18001e807  call    cs:__imp_WriteFile
0x18001e80d  test    eax, eax
0x18001e80f  jnz     short loc_18001E83F
0x18001e811  call    cs:__imp_GetLastError
0x18001e817  test    eax, eax
0x18001e819  jle     short loc_18001E821
0x18001e81b  movzx   eax, ax
0x18001e81e  or      eax, r13d
0x18001e821  mov     r9d, eax; int
0x18001e824  mov     dword ptr [rsp+130h+lpOverlapped], 542h; unsigned int
0x18001e82c  lea     r8, aWerFailure; "<WER_Failure>"
0x18001e833  mov     rdx, rbx; struct DIRECTORY_SCAN_FUNC_ARGS *
0x18001e836  lea     rcx, [rbp+57h+var_A0]; struct _FILE_ID_EXTD_DIR_INFORMATION *
0x18001e83a  call    ?RecordDirScanFailures@@YAJPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAUDIRECTORY_SCAN_FUNC_ARGS@@PEBGJI@Z; RecordDirScanFailures(_FILE_ID_EXTD_DIR_INFORMATION *,DIRECTORY_SCAN_FUNC_ARGS *,ushort const *,long,uint)
0x18001e83f  mov     rdx, [rbx+98h]; lpBuffer
0x18001e846  lea     r9, [rsp+130h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001e84b  mov     rcx, [rbx+0A8h]; hFile
0x18001e852  mov     r8d, edi; nNumberOfBytesToWrite
0x18001e855  mov     [rsp+130h+lpOverlapped], r12; lpOverlapped
0x18001e85a  call    cs:__imp_WriteFile
0x18001e860  test    eax, eax
0x18001e862  jnz     short loc_18001E892
0x18001e864  call    cs:__imp_GetLastError
0x18001e86a  test    eax, eax
0x18001e86c  jle     short loc_18001E874
0x18001e86e  movzx   eax, ax
0x18001e871  or      eax, r13d
0x18001e874  mov     r9d, eax; int
0x18001e877  mov     dword ptr [rsp+130h+lpOverlapped], 548h; unsigned int
0x18001e87f  lea     r8, aWerFailure; "<WER_Failure>"
0x18001e886  mov     rdx, rbx; struct DIRECTORY_SCAN_FUNC_ARGS *
0x18001e889  lea     rcx, [rbp+57h+var_A0]; struct _FILE_ID_EXTD_DIR_INFORMATION *
0x18001e88d  call    ?RecordDirScanFailures@@YAJPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAUDIRECTORY_SCAN_FUNC_ARGS@@PEBGJI@Z; RecordDirScanFailures(_FILE_ID_EXTD_DIR_INFORMATION *,DIRECTORY_SCAN_FUNC_ARGS *,ushort const *,long,uint)
0x18001e892  mov     rcx, [rbx+0A8h]; hFile
0x18001e899  lea     r9, [rsp+130h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001e89e  mov     r8d, 4; nNumberOfBytesToWrite
0x18001e8a4  mov     [rsp+130h+lpOverlapped], r12; lpOverlapped
0x18001e8a9  lea     rdx, asc_180032078; "\n"
0x18001e8b0  call    cs:__imp_WriteFile
0x18001e8b6  test    eax, eax
0x18001e8b8  jnz     loc_18001E9C4
0x18001e8be  call    cs:__imp_GetLastError
0x18001e8c4  test    eax, eax
0x18001e8c6  jle     short loc_18001E8CE
0x18001e8c8  movzx   eax, ax
0x18001e8cb  or      eax, r13d
0x18001e8ce  mov     r9d, eax; int
0x18001e8d1  mov     dword ptr [rsp+130h+lpOverlapped], 54Eh; unsigned int
0x18001e8d9  lea     r8, aWerFailure; "<WER_Failure>"
0x18001e8e0  mov     rdx, rbx; struct DIRECTORY_SCAN_FUNC_ARGS *
0x18001e8e3  lea     rcx, [rbp+57h+var_A0]; struct _FILE_ID_EXTD_DIR_INFORMATION *
0x18001e8e7  call    ?RecordDirScanFailures@@YAJPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAUDIRECTORY_SCAN_FUNC_ARGS@@PEBGJI@Z; RecordDirScanFailures(_FILE_ID_EXTD_DIR_INFORMATION *,DIRECTORY_SCAN_FUNC_ARGS *,ushort const *,long,uint)
0x18001e8ec  jmp     loc_18001E9C4
0x18001e8f1  mov     eax, cs:dword_180040010
0x18001e8f7  cmp     eax, 5
0x18001e8fa  jbe     loc_18001E9A4
0x18001e900  mov     rdx, 400000000000h
0x18001e90a  lea     rcx, dword_180040010
0x18001e911  call    _tlgKeywordOn
0x18001e916  test    al, al
0x18001e918  jz      loc_18001E9A4
0x18001e91e  movzx   eax, word ptr [rbx+50h]
0x18001e922  lea     rdx, byte_180037A13
0x18001e929  mov     word ptr [rsp+130h+NumberOfBytesWritten], ax
0x18001e92e  lea     rax, [rbx+80h]
0x18001e935  mov     [rsp+130h+var_D8], rax
0x18001e93a  mov     rax, [rbx+98h]
0x18001e941  mov     [rbp+57h+var_C8], rax
0x18001e945  mov     rax, [rbx+90h]
0x18001e94c  mov     [rbp+57h+var_B8], rax
0x18001e950  mov     eax, [rbx]
0x18001e952  mov     [rsp+130h+var_DC], eax
0x18001e956  lea     rax, [rsp+130h+NumberOfBytesWritten]
0x18001e95b  mov     [rsp+130h+var_E8], rax
0x18001e960  lea     rax, [rsp+130h+var_D8]
0x18001e965  mov     [rsp+130h+var_F0], rax
0x18001e96a  lea     rax, [rbp+57h+var_C8]
0x18001e96e  mov     [rsp+130h+var_F8], rax
0x18001e973  lea     rax, [rbp+57h+var_B8]
0x18001e977  mov     [rsp+130h+var_100], rax
0x18001e97c  lea     rax, [rsp+130h+var_DC]
0x18001e981  mov     [rsp+130h+var_108], rax
0x18001e986  lea     rax, [rbp+57h+var_D0]
0x18001e98a  mov     [rsp+130h+lpOverlapped], rax
0x18001e98f  mov     [rbp+57h+var_C0], di
0x18001e993  mov     [rbp+57h+var_B0], di
0x18001e997  mov     [rbp+57h+var_D0], 1000000h
0x18001e99f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperArray@$07@@U3@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U?$_tlgWrapperByVal@$01@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperArray@$07@@5AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@AEBU?$_tlgWrapperByVal@$01@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperArray<8>,_tlgWrapperArray<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperArray<8> const &,_tlgWrapperArray<8> const &,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapperByVal<2> const &)
0x18001e9a4  mov     ecx, 28h ; '('; dwMilliseconds
0x18001e9a9  call    cs:__imp_Sleep
0x18001e9af  lea     rsi, [rbx+90h]
0x18001e9b6  lea     r14, [rbx+88h]
0x18001e9bd  lea     r15, [rbx+80h]
0x18001e9c4  mov     rcx, [rsi]; void *
0x18001e9c7  mov     edi, 1F40h
0x18001e9cc  mov     r8d, edi; Size
0x18001e9cf  mov     [rbx+78h], r12w
0x18001e9d4  xor     edx, edx; Val
0x18001e9d6  call    memset_0
0x18001e9db  mov     rcx, [rbx+98h]; void *
0x18001e9e2  mov     r8d, edi; Size
0x18001e9e5  xor     edx, edx; Val
0x18001e9e7  call    memset_0
0x18001e9ec  movzx   r8d, word ptr [rbx+82h]; Size
0x18001e9f4  xor     edx, edx; Val
0x18001e9f6  mov     rcx, [r14]; void *
0x18001e9f9  call    memset_0
0x18001e9fe  mov     [r15], r12w
0x18001ea02  mov     [rbx+50h], r12w
0x18001ea07  add     rsp, 0F8h
0x18001ea0e  pop     r15
0x18001ea10  pop     r14
0x18001ea12  pop     r13
0x18001ea14  pop     r12
0x18001ea16  pop     rdi
0x18001ea17  pop     rsi
0x18001ea18  pop     rbx
0x18001ea19  pop     rbp
0x18001ea1a  retn
```
