# CCompAttribLex::MapFileToMemory(ushort const *)

- ea: `0x1800fd7c4`
- end: `0x1800fd887`
- name: `?MapFileToMemory@CCompAttribLex@@AEAAJPEBG@Z`
- size: `195`
- prototype: `int(CCompAttribLex *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800fd5c4`

## callees

- `0x18005b268`
- `0x1800fd7c4`
- `0x1800fdf04`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800fd7fa`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800fd7fa`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800fd81b`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800fd81b`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800fd864`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800fd864`

## pseudocode

```c
__int64 __fastcall CCompAttribLex::MapFileToMemory(CCompAttribLex *this, const unsigned __int16 *a2)
{
  int Win32Error; // ebx
  HANDLE FileW; // rax
  DWORD FileSize; // eax
  HANDLE FileMapping; // rax
  LPVOID v7; // rax

  Win32Error = 0;
  FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x10000080u, 0);
  *((_QWORD *)this + 10) = FileW;
  if ( FileW != (HANDLE)-1LL || (Win32Error = SpHrFromLastWin32Error(), Win32Error >= 0) )
  {
    FileSize = GetFileSize(*((HANDLE *)this + 10), 0);
    *((_DWORD *)this + 28) = FileSize;
    if ( FileSize == -1 )
    {
      return (unsigned int)-2147024809;
    }
    else
    {
      FileMapping = SpCreateFileMapping(*((HANDLE *)this + 10));
      *((_QWORD *)this + 11) = FileMapping;
      if ( FileMapping || (Win32Error = SpHrFromLastWin32Error(), Win32Error >= 0) )
      {
        v7 = MapViewOfFile(*((HANDLE *)this + 11), 4u, 0, 0, 0);
        *((_QWORD *)this + 13) = v7;
        if ( !v7 )
          return (unsigned int)SpHrFromLastWin32Error();
      }
    }
  }
  return (unsigned int)Win32Error;
}

```

## disassembly

```asm
0x1800fd7c4  mov     [rsp+arg_0], rbx
0x1800fd7c9  push    rdi
0x1800fd7ca  sub     rsp, 40h
0x1800fd7ce  mov     rax, rdx
0x1800fd7d1  xor     ebx, ebx
0x1800fd7d3  mov     rdi, rcx
0x1800fd7d6  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x1800fd7db  mov     [rsp+48h+dwFlagsAndAttributes], 10000080h; unsigned int
0x1800fd7e3  xor     r9d, r9d; lpSecurityAttributes
0x1800fd7e6  mov     edx, 80000000h; dwDesiredAccess
0x1800fd7eb  mov     [rsp+48h+dwCreationDisposition], 3; unsigned __int16 *
0x1800fd7f3  lea     r8d, [rbx+1]; dwShareMode
0x1800fd7f7  mov     rcx, rax; lpFileName
0x1800fd7fa  call    cs:__imp_CreateFileW
0x1800fd800  mov     [rdi+50h], rax
0x1800fd804  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800fd808  jnz     short loc_1800FD815
0x1800fd80a  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800fd80f  mov     ebx, eax
0x1800fd811  test    eax, eax
0x1800fd813  js      short loc_1800FD87A
0x1800fd815  mov     rcx, [rdi+50h]; hFile
0x1800fd819  xor     edx, edx; lpFileSizeHigh
0x1800fd81b  call    cs:__imp_GetFileSize
0x1800fd821  mov     [rdi+70h], eax
0x1800fd824  cmp     eax, 0FFFFFFFFh
0x1800fd827  jnz     short loc_1800FD830
0x1800fd829  mov     ebx, 80070057h
0x1800fd82e  jmp     short loc_1800FD87A
0x1800fd830  mov     rcx, [rdi+50h]; hFile
0x1800fd834  call    ?SpCreateFileMapping@@YAPEAXPEAXKKKPEBGK@Z; SpCreateFileMapping(void *,ulong,ulong,ulong,ushort const *,ulong)
0x1800fd839  mov     [rdi+58h], rax
0x1800fd83d  test    rax, rax
0x1800fd840  jnz     short loc_1800FD84D
0x1800fd842  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800fd847  mov     ebx, eax
0x1800fd849  test    eax, eax
0x1800fd84b  js      short loc_1800FD87A
0x1800fd84d  mov     rcx, [rdi+58h]; hFileMappingObject
0x1800fd851  xor     r9d, r9d; dwFileOffsetLow
0x1800fd854  xor     r8d, r8d; dwFileOffsetHigh
0x1800fd857  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x1800fd860  lea     edx, [r9+4]; dwDesiredAccess
0x1800fd864  call    cs:__imp_MapViewOfFile
0x1800fd86a  mov     [rdi+68h], rax
0x1800fd86e  test    rax, rax
0x1800fd871  jnz     short loc_1800FD87A
0x1800fd873  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800fd878  mov     ebx, eax
0x1800fd87a  mov     eax, ebx
0x1800fd87c  mov     rbx, [rsp+48h+arg_0]
0x1800fd881  add     rsp, 40h
0x1800fd885  pop     rdi
0x1800fd886  retn
```
