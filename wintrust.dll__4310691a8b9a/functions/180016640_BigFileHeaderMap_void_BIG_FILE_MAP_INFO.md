# BigFileHeaderMap(void *,_BIG_FILE_MAP_INFO *)

- ea: `0x180016640`
- end: `0x18001682c`
- name: `?BigFileHeaderMap@@YAHPEAXPEAU_BIG_FILE_MAP_INFO@@@Z`
- size: `492`
- prototype: `__int64 __fastcall(HANDLE hFile, struct _BIG_FILE_MAP_INFO *)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180015b70`
- `0x180015e90`
- `0x180015f30`
- `0x18003da40`
- `0x18003e01c`

## callees

- `0x180016314`
- `0x180016640`
- `0x180016834`
- `0x1800168c8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180016691`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180016691`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180016735`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18001674f`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18001678d`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180016735`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18001674f`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18001678d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180016775`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180016775`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800166fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800166fe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001670c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001670c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800167d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800167d7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180016800`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180016800`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800167ae`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800167ae`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x1800166d5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x1800166d5`

## pseudocode

```c
__int64 __fastcall BigFileHeaderMap(HANDLE hFile, struct _BIG_FILE_MAP_INFO *a2)
{
  union _LARGE_INTEGER v4; // rbx
  HANDLE FileMappingA; // rax
  unsigned int v6; // eax
  unsigned int v7; // ebx
  HANDLE ProcessHeap; // rax
  LPVOID v9; // rax
  LARGE_INTEGER v10; // rbx
  LPVOID v11; // rax
  DWORD v13; // ecx
  union _LARGE_INTEGER NewFilePointer; // [rsp+30h] [rbp-58h] BYREF
  LARGE_INTEGER liDistanceToMove; // [rsp+38h] [rbp-50h]
  _SYSTEM_INFO SystemInfo; // [rsp+40h] [rbp-48h] BYREF
  DWORD NumberOfBytesRead; // [rsp+A0h] [rbp+18h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+A8h] [rbp+20h] BYREF

  liDistanceToMove.QuadPart = 0;
  NewFilePointer.QuadPart = 0;
  FileSize.QuadPart = 0;
  NumberOfBytesRead = 0;
  if ( !dword_180069ED8 )
  {
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetSystemInfo(&SystemInfo);
    if ( !SystemInfo.dwAllocationGranularity )
    {
      v13 = -2147418113;
LABEL_17:
      SetLastError(v13);
      goto LABEL_18;
    }
    dword_180069ED8 = SystemInfo.dwAllocationGranularity;
  }
  if ( dword_180069ED8 >= (unsigned int)I_CryptGetMaxHashBytesToMapRegValue() )
  {
    v13 = -2147024809;
    goto LABEL_17;
  }
  *(_DWORD *)a2 = dword_180069ED8;
  if ( GetFileSizeEx(hFile, &FileSize) )
  {
    v4 = FileSize;
    *((union _LARGE_INTEGER *)a2 + 2) = FileSize;
    if ( v4.QuadPart >= (unsigned int)I_CryptGetMaxHeaderBytesToMapRegValue() )
      v4.LowPart = I_CryptGetMaxHeaderBytesToMapRegValue();
    *((_DWORD *)a2 + 8) = v4.LowPart;
    FileMappingA = CreateFileMappingA(hFile, 0, 2u, 0, 0, 0);
    *((_QWORD *)a2 + 1) = FileMappingA;
    if ( FileMappingA )
    {
      v6 = *((_DWORD *)a2 + 8);
      *((_QWORD *)a2 + 8) = hFile;
      if ( v6 > 0x80000 )
        v6 = 0x80000;
      v7 = v6;
      *((_DWORD *)a2 + 20) = v6;
      ProcessHeap = GetProcessHeap();
      v9 = HeapAlloc(ProcessHeap, 0, v7);
      *((_QWORD *)a2 + 9) = v9;
      if ( v9 )
      {
        v10 = liDistanceToMove;
        if ( SetFilePointerEx(hFile, liDistanceToMove, &NewFilePointer, 1u) )
        {
          if ( SetFilePointerEx(hFile, v10, 0, 0) )
          {
            if ( ReadFile(hFile, *((LPVOID *)a2 + 9), *((_DWORD *)a2 + 20), &NumberOfBytesRead, 0) )
            {
              if ( SetFilePointerEx(hFile, NewFilePointer, 0, 0) )
              {
                v11 = MapViewOfFile(*((HANDLE *)a2 + 1), 4u, 0, 0, *((unsigned int *)a2 + 8));
                *((_QWORD *)a2 + 3) = v11;
                if ( v11 )
                  return 1;
              }
            }
          }
        }
      }
    }
  }
LABEL_18:
  BigFileUnmap(a2);
  return 0;
}

```

## disassembly

```asm
0x180016640  mov     rax, rsp
0x180016643  mov     [rax+8], rbx
0x180016647  push    rbp
0x180016648  push    rsi
0x180016649  push    rdi
0x18001664a  sub     rsp, 70h
0x18001664e  xor     ebp, ebp
0x180016650  mov     rdi, rdx
0x180016653  cmp     cs:dword_180069ED8, ebp
0x180016659  mov     rsi, rcx
0x18001665c  mov     [rax-50h], rbp
0x180016660  mov     [rax-58h], rbp
0x180016664  mov     [rax+20h], rbp
0x180016668  mov     [rax+18h], ebp
0x18001666b  jz      loc_1800167E9
0x180016671  call    I_CryptGetMaxHashBytesToMapRegValue
0x180016676  mov     ecx, cs:dword_180069ED8
0x18001667c  cmp     ecx, eax
0x18001667e  jnb     loc_180016825
0x180016684  mov     [rdi], ecx
0x180016686  lea     rdx, [rsp+88h+FileSize]; lpFileSize
0x18001668e  mov     rcx, rsi; hFile
0x180016691  call    cs:__imp_GetFileSizeEx
0x180016697  test    eax, eax
0x180016699  jz      loc_1800167DD
0x18001669f  mov     rbx, qword ptr [rsp+88h+FileSize]
0x1800166a7  mov     [rdi+10h], rbx
0x1800166ab  call    I_CryptGetMaxHeaderBytesToMapRegValue
0x1800166b0  mov     eax, eax
0x1800166b2  cmp     rbx, rax
0x1800166b5  jge     loc_180016819
0x1800166bb  mov     [rsp+88h+lpName], rbp; lpName
0x1800166c0  xor     r9d, r9d; dwMaximumSizeHigh
0x1800166c3  xor     edx, edx; lpFileMappingAttributes
0x1800166c5  mov     [rsp+88h+dwMaximumSizeLow], ebp; dwMaximumSizeLow
0x1800166c9  mov     r8d, 2; flProtect
0x1800166cf  mov     [rdi+20h], ebx
0x1800166d2  mov     rcx, rsi; hFile
0x1800166d5  call    cs:__imp_CreateFileMappingA
0x1800166db  mov     [rdi+8], rax
0x1800166df  test    rax, rax
0x1800166e2  jz      loc_1800167DD
0x1800166e8  mov     eax, [rdi+20h]
0x1800166eb  mov     ecx, 80000h
0x1800166f0  cmp     eax, ecx
0x1800166f2  mov     [rdi+40h], rsi
0x1800166f6  cmova   eax, ecx
0x1800166f9  mov     ebx, eax
0x1800166fb  mov     [rdi+50h], ebx
0x1800166fe  call    cs:__imp_GetProcessHeap
0x180016704  mov     r8d, ebx; dwBytes
0x180016707  xor     edx, edx; dwFlags
0x180016709  mov     rcx, rax; hHeap
0x18001670c  call    cs:__imp_HeapAlloc
0x180016712  mov     [rdi+48h], rax
0x180016716  test    rax, rax
0x180016719  jz      loc_1800167DD
0x18001671f  mov     rbx, qword ptr [rsp+88h+liDistanceToMove]
0x180016724  lea     r8, [rsp+88h+NewFilePointer]; lpNewFilePointer
0x180016729  mov     rdx, rbx; liDistanceToMove
0x18001672c  mov     r9d, 1; dwMoveMethod
0x180016732  mov     rcx, rsi; hFile
0x180016735  call    cs:__imp_SetFilePointerEx
0x18001673b  test    eax, eax
0x18001673d  jz      loc_1800167DD
0x180016743  xor     r9d, r9d; dwMoveMethod
0x180016746  xor     r8d, r8d; lpNewFilePointer
0x180016749  mov     rdx, rbx; liDistanceToMove
0x18001674c  mov     rcx, rsi; hFile
0x18001674f  call    cs:__imp_SetFilePointerEx
0x180016755  test    eax, eax
0x180016757  jz      loc_1800167DD
0x18001675d  mov     r8d, [rdi+50h]; nNumberOfBytesToRead
0x180016761  lea     r9, [rsp+88h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180016769  mov     rdx, [rdi+48h]; lpBuffer
0x18001676d  mov     rcx, rsi; hFile
0x180016770  mov     qword ptr [rsp+88h+dwMaximumSizeLow], rbp; lpOverlapped
0x180016775  call    cs:__imp_ReadFile
0x18001677b  test    eax, eax
0x18001677d  jz      short loc_1800167DD
0x18001677f  mov     rdx, qword ptr [rsp+88h+NewFilePointer]; liDistanceToMove
0x180016784  xor     r9d, r9d; dwMoveMethod
0x180016787  xor     r8d, r8d; lpNewFilePointer
0x18001678a  mov     rcx, rsi; hFile
0x18001678d  call    cs:__imp_SetFilePointerEx
0x180016793  test    eax, eax
0x180016795  jz      short loc_1800167DD
0x180016797  mov     ecx, [rdi+20h]
0x18001679a  xor     r9d, r9d; dwFileOffsetLow
0x18001679d  mov     qword ptr [rsp+88h+dwMaximumSizeLow], rcx; dwNumberOfBytesToMap
0x1800167a2  xor     r8d, r8d; dwFileOffsetHigh
0x1800167a5  mov     rcx, [rdi+8]; hFileMappingObject
0x1800167a9  mov     edx, 4; dwDesiredAccess
0x1800167ae  call    cs:__imp_MapViewOfFile
0x1800167b4  mov     [rdi+18h], rax
0x1800167b8  test    rax, rax
0x1800167bb  jz      short loc_1800167DD
0x1800167bd  mov     eax, 1
0x1800167c2  mov     rbx, [rsp+88h+arg_0]
0x1800167ca  add     rsp, 70h
0x1800167ce  pop     rdi
0x1800167cf  pop     rsi
0x1800167d0  pop     rbp
0x1800167d1  retn
0x1800167d2  mov     ecx, 8000FFFFh; dwErrCode
0x1800167d7  call    cs:__imp_SetLastError
0x1800167dd  mov     rcx, rdi; struct _BIG_FILE_MAP_INFO *
0x1800167e0  call    ?BigFileUnmap@@YAXPEAU_BIG_FILE_MAP_INFO@@@Z; BigFileUnmap(_BIG_FILE_MAP_INFO *)
0x1800167e5  mov     eax, ebp
0x1800167e7  jmp     short loc_1800167C2
0x1800167e9  xorps   xmm0, xmm0
0x1800167ec  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x1800167f1  movups  xmmword ptr [rsp+88h+SystemInfo], xmm0
0x1800167f6  movups  xmmword ptr [rsp+88h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x1800167fb  movups  xmmword ptr [rsp+88h+SystemInfo.dwNumberOfProcessors], xmm0
0x180016800  call    cs:__imp_GetSystemInfo
0x180016806  mov     eax, [rsp+88h+SystemInfo.dwAllocationGranularity]
0x18001680a  test    eax, eax
0x18001680c  jz      short loc_1800167D2
0x18001680e  mov     cs:dword_180069ED8, eax
0x180016814  jmp     loc_180016671
0x180016819  call    I_CryptGetMaxHeaderBytesToMapRegValue
0x18001681e  mov     ebx, eax
0x180016820  jmp     loc_1800166BB
0x180016825  mov     ecx, 80070057h
0x18001682a  jmp     short loc_1800167D7
```
