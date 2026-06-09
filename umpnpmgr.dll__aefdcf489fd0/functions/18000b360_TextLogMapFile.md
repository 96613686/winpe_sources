# TextLogMapFile

- ea: `0x18000b360`
- end: `0x18000b5e0`
- name: `TextLogMapFile`
- size: `640`
- prototype: `__int64 __fastcall(__int64, __int64, int, char)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800027a0`
- `0x1800056d0`
- `0x18000b160`
- `0x1800177e0`

## callees

- `0x18000b360`
- `0x18000b890`
- `0x18000f82c`
- `0x1800101e8`
- `0x180017058`
- `0x1800175cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18000b40f`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18000b40f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b3ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b44e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b523`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b53f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b3ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b44e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b523`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b53f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b459`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b52f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b459`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b52f`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000b430`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000b47f`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000b430`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000b47f`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000b443`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000b443`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000b3df`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000b3df`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000b514`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000b514`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000b4f0`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000b4f0`

## pseudocode

```c
__int64 __fastcall TextLogMapFile(__int64 a1, __int64 a2, int a3, char a4)
{
  const WCHAR *v5; // rsi
  DWORD v6; // edi
  unsigned int v10; // r13d
  HANDLE FileW; // rax
  DWORD LastError; // eax
  DWORD v13; // ebp
  unsigned int FileSize; // edi
  DWORD v15; // eax
  int LogStatus; // eax
  HANDLE FileMappingW; // rax
  LPVOID v18; // rax
  unsigned int i; // edi
  __int64 result; // rax
  unsigned int v21; // edx
  _BYTE v22[32]; // [rsp+40h] [rbp-48h] BYREF

  *(_QWORD *)a2 = -1;
  *(_QWORD *)(a2 + 8) = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_DWORD *)(a2 + 44) = a4 & 1;
  *(_DWORD *)(a2 + 48) = 0;
  v5 = *(const WCHAR **)(a1 + 16);
  v6 = -1073676288;
  if ( (a4 & 6) == 0 )
    v6 = -1073741824;
  v10 = 0;
  while ( 1 )
  {
    FileW = CreateFileW(v5, v6, 1u, 0, 4u, 0, 0);
    *(_QWORD *)a2 = FileW;
    if ( FileW == (HANDLE)-1LL )
      break;
LABEL_8:
    if ( *(_QWORD *)a2 != -1 )
      goto LABEL_11;
  }
  LastError = GetLastError();
  v13 = LastError;
  if ( LastError == 32 )
  {
    if ( v10 >= 0x7530 )
      goto LABEL_29;
    SleepEx(0x32u, 0);
    v10 += 50;
    goto LABEL_8;
  }
  if ( !LastError )
  {
LABEL_11:
    FileSize = GetFileSize(*(HANDLE *)a2, 0);
    if ( SetFilePointer(*(HANDLE *)a2, FileSize, 0, 0) != -1
      || (v13 = GetLastError(), CloseHandle(*(HANDLE *)a2), *(_QWORD *)a2 = -1, !v13) )
    {
      if ( FileSize )
      {
        if ( (a4 & 2) != 0
          && FileSize >= *(_DWORD *)(a1 + 8)
          && *(_DWORD *)(a1 + 24) < 4u
          && (*(_DWORD *)(a1 + 12) & 0x2000) == 0 )
        {
          *(_DWORD *)(a2 + 48) = 1;
        }
      }
      else
      {
        WriteTextLogFileHeader(*(HANDLE *)a2);
        v15 = GetFileSize(*(HANDLE *)a2, 0);
        *(_DWORD *)(a1 + 12) &= ~0x1000u;
        FileSize = v15;
        LogStatus = TextLogGetLogStatus(a1);
        if ( (LogStatus & 0x1000) != 0 )
          TextLogSetLogStatus(a1, LogStatus & 0xFFFFEFFF);
      }
      FileMappingW = CreateFileMappingW(*(HANDLE *)a2, 0, 4u, 0, FileSize + a3, 0);
      *(_QWORD *)(a2 + 8) = FileMappingW;
      if ( FileMappingW )
      {
        v18 = MapViewOfFile(FileMappingW, 0xF001Fu, 0, 0, FileSize + a3);
        *(_QWORD *)(a2 + 16) = v18;
        if ( !v18 )
        {
          v13 = GetLastError();
          CloseHandle(*(HANDLE *)(a2 + 8));
          *(_QWORD *)(a2 + 8) = 0;
          goto LABEL_25;
        }
        goto LABEL_26;
      }
      v13 = GetLastError();
LABEL_25:
      if ( !v13 )
      {
LABEL_26:
        *(_QWORD *)(a2 + 24) = *(_QWORD *)(a2 + 16) + FileSize;
        *(_QWORD *)(a2 + 32) = a1;
        for ( i = 0; (unsigned int)TextLogEnumerateOpenSections(a2, i, (__int64)v22); ++i )
          ;
        *(_DWORD *)(a2 + 40) = *(_DWORD *)(a2 + 24) - 20 * i - *(_DWORD *)(a2 + 16);
        return 0;
      }
    }
  }
LABEL_29:
  TextLogUnmapFile(a2);
  result = v13;
  v21 = TextLogMapErrors++;
  if ( v21 > 5 )
    *(_DWORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x18000b360  mov     [rsp+arg_8], rbx
0x18000b365  mov     [rsp+arg_10], rsi
0x18000b36a  push    rdi
0x18000b36b  push    r12
0x18000b36d  push    r13
0x18000b36f  push    r14
0x18000b371  push    r15
0x18000b373  sub     rsp, 60h
0x18000b377  mov     r15, rcx
0x18000b37a  mov     qword ptr [rdx], 0FFFFFFFFFFFFFFFFh
0x18000b381  xor     ecx, ecx
0x18000b383  mov     [rsp+88h+arg_0], rbp
0x18000b38b  mov     eax, r9d
0x18000b38e  mov     [rdx+8], rcx
0x18000b392  and     eax, 1
0x18000b395  mov     [rdx+10h], rcx
0x18000b399  mov     [rdx+2Ch], eax
0x18000b39c  test    r9b, 6
0x18000b3a0  mov     eax, 0C0000000h
0x18000b3a5  mov     [rdx+30h], ecx
0x18000b3a8  mov     rsi, [r15+10h]
0x18000b3ac  mov     edi, 0C0010000h
0x18000b3b1  cmovz   edi, eax
0x18000b3b4  mov     r14d, r9d
0x18000b3b7  mov     r12d, r8d
0x18000b3ba  mov     rbx, rdx
0x18000b3bd  mov     r13d, ecx
0x18000b3c0  mov     [rsp+88h+hTemplateFile], rcx; hTemplateFile
0x18000b3c5  xor     r9d, r9d; lpSecurityAttributes
0x18000b3c8  mov     [rsp+88h+dwFlagsAndAttributes], ecx; dwFlagsAndAttributes
0x18000b3cc  mov     r8d, 1; dwShareMode
0x18000b3d2  mov     rcx, rsi; lpFileName
0x18000b3d5  mov     [rsp+88h+dwCreationDisposition], 4; dwCreationDisposition
0x18000b3dd  mov     edx, edi; dwDesiredAccess
0x18000b3df  call    cs:__imp_CreateFileW
0x18000b3e5  mov     [rbx], rax
0x18000b3e8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000b3ec  jnz     short loc_18000B419
0x18000b3ee  call    cs:__imp_GetLastError
0x18000b3f4  mov     ebp, eax
0x18000b3f6  cmp     eax, 20h ; ' '
0x18000b3f9  jnz     short loc_18000B423
0x18000b3fb  cmp     r13d, 7530h
0x18000b402  jnb     loc_18000B598
0x18000b408  xor     edx, edx; bAlertable
0x18000b40a  mov     ecx, 32h ; '2'; dwMilliseconds
0x18000b40f  call    cs:__imp_SleepEx
0x18000b415  add     r13d, 32h ; '2'
0x18000b419  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x18000b41d  jnz     short loc_18000B42B
0x18000b41f  xor     ecx, ecx
0x18000b421  jmp     short loc_18000B3C0
0x18000b423  test    eax, eax
0x18000b425  jnz     loc_18000B598
0x18000b42b  mov     rcx, [rbx]; hFile
0x18000b42e  xor     edx, edx; lpFileSizeHigh
0x18000b430  call    cs:__imp_GetFileSize
0x18000b436  mov     rcx, [rbx]; hFile
0x18000b439  xor     r9d, r9d; dwMoveMethod
0x18000b43c  mov     edx, eax; lDistanceToMove
0x18000b43e  xor     r8d, r8d; lpDistanceToMoveHigh
0x18000b441  mov     edi, eax
0x18000b443  call    cs:__imp_SetFilePointer
0x18000b449  cmp     eax, 0FFFFFFFFh
0x18000b44c  jnz     short loc_18000B46E
0x18000b44e  call    cs:__imp_GetLastError
0x18000b454  mov     rcx, [rbx]; hObject
0x18000b457  mov     ebp, eax
0x18000b459  call    cs:__imp_CloseHandle
0x18000b45f  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x18000b466  test    ebp, ebp
0x18000b468  jnz     loc_18000B598
0x18000b46e  test    edi, edi
0x18000b470  jnz     short loc_18000B4AD
0x18000b472  mov     rcx, [rbx]; hFile
0x18000b475  call    WriteTextLogFileHeader
0x18000b47a  mov     rcx, [rbx]; hFile
0x18000b47d  xor     edx, edx; lpFileSizeHigh
0x18000b47f  call    cs:__imp_GetFileSize
0x18000b485  and     dword ptr [r15+0Ch], 0FFFFEFFFh
0x18000b48d  mov     rcx, r15
0x18000b490  mov     edi, eax
0x18000b492  call    TextLogGetLogStatus
0x18000b497  bt      eax, 0Ch
0x18000b49b  jnb     short loc_18000B4D1
0x18000b49d  btr     eax, 0Ch
0x18000b4a1  mov     rcx, r15
0x18000b4a4  mov     edx, eax
0x18000b4a6  call    TextLogSetLogStatus
0x18000b4ab  jmp     short loc_18000B4D1
0x18000b4ad  test    r14b, 2
0x18000b4b1  jz      short loc_18000B4D1
0x18000b4b3  cmp     edi, [r15+8]
0x18000b4b7  jb      short loc_18000B4D1
0x18000b4b9  cmp     dword ptr [r15+18h], 4
0x18000b4be  jnb     short loc_18000B4D1
0x18000b4c0  test    dword ptr [r15+0Ch], 2000h
0x18000b4c8  jnz     short loc_18000B4D1
0x18000b4ca  mov     dword ptr [rbx+30h], 1
0x18000b4d1  mov     rcx, [rbx]; hFile
0x18000b4d4  lea     esi, [rdi+r12]
0x18000b4d8  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], 0; lpName
0x18000b4e1  xor     r9d, r9d; dwMaximumSizeHigh
0x18000b4e4  xor     edx, edx; lpFileMappingAttributes
0x18000b4e6  mov     [rsp+88h+dwCreationDisposition], esi; dwMaximumSizeLow
0x18000b4ea  mov     r8d, 4; flProtect
0x18000b4f0  call    cs:__imp_CreateFileMappingW
0x18000b4f6  mov     [rbx+8], rax
0x18000b4fa  test    rax, rax
0x18000b4fd  jz      short loc_18000B53F
0x18000b4ff  mov     ecx, esi
0x18000b501  xor     r9d, r9d; dwFileOffsetLow
0x18000b504  mov     qword ptr [rsp+88h+dwCreationDisposition], rcx; dwNumberOfBytesToMap
0x18000b509  xor     r8d, r8d; dwFileOffsetHigh
0x18000b50c  mov     rcx, rax; hFileMappingObject
0x18000b50f  mov     edx, 0F001Fh; dwDesiredAccess
0x18000b514  call    cs:__imp_MapViewOfFile
0x18000b51a  mov     [rbx+10h], rax
0x18000b51e  test    rax, rax
0x18000b521  jnz     short loc_18000B54B
0x18000b523  call    cs:__imp_GetLastError
0x18000b529  mov     rcx, [rbx+8]; hObject
0x18000b52d  mov     ebp, eax
0x18000b52f  call    cs:__imp_CloseHandle
0x18000b535  mov     qword ptr [rbx+8], 0
0x18000b53d  jmp     short loc_18000B547
0x18000b53f  call    cs:__imp_GetLastError
0x18000b545  mov     ebp, eax
0x18000b547  test    ebp, ebp
0x18000b549  jnz     short loc_18000B598
0x18000b54b  mov     eax, edi
0x18000b54d  lea     r8, [rsp+88h+var_48]
0x18000b552  add     rax, [rbx+10h]
0x18000b556  xor     edx, edx
0x18000b558  mov     rcx, rbx
0x18000b55b  mov     [rbx+18h], rax
0x18000b55f  mov     [rbx+20h], r15
0x18000b563  xor     edi, edi
0x18000b565  call    TextLogEnumerateOpenSections
0x18000b56a  test    eax, eax
0x18000b56c  jz      short loc_18000B583
0x18000b56e  inc     edi
0x18000b570  lea     r8, [rsp+88h+var_48]
0x18000b575  mov     edx, edi
0x18000b577  mov     rcx, rbx
0x18000b57a  call    TextLogEnumerateOpenSections
0x18000b57f  test    eax, eax
0x18000b581  jnz     short loc_18000B56E
0x18000b583  mov     ecx, [rbx+18h]
0x18000b586  lea     eax, [rdi+rdi*4]
0x18000b589  shl     eax, 2
0x18000b58c  sub     ecx, eax
0x18000b58e  sub     ecx, [rbx+10h]
0x18000b591  mov     [rbx+28h], ecx
0x18000b594  xor     eax, eax
0x18000b596  jmp     short loc_18000B5BE
0x18000b598  mov     rcx, rbx
0x18000b59b  call    TextLogUnmapFile
0x18000b5a0  mov     ecx, cs:TextLogMapErrors
0x18000b5a6  mov     eax, ebp
0x18000b5a8  mov     edx, ecx
0x18000b5aa  inc     ecx
0x18000b5ac  mov     cs:TextLogMapErrors, ecx
0x18000b5b2  cmp     edx, 5
0x18000b5b5  jbe     short loc_18000B5BE
0x18000b5b7  mov     dword ptr [r15], 0
0x18000b5be  mov     rbp, [rsp+88h+arg_0]
0x18000b5c6  lea     r11, [rsp+88h+var_28]
0x18000b5cb  mov     rbx, [r11+38h]
0x18000b5cf  mov     rsi, [r11+40h]
0x18000b5d3  mov     rsp, r11
0x18000b5d6  pop     r15
0x18000b5d8  pop     r14
0x18000b5da  pop     r13
0x18000b5dc  pop     r12
0x18000b5de  pop     rdi
0x18000b5df  retn
```
