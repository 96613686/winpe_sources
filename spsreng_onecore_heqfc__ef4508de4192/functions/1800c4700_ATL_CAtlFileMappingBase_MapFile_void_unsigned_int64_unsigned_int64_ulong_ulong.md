# ATL::CAtlFileMappingBase::MapFile(void *,unsigned __int64,unsigned __int64,ulong,ulong)

- ea: `0x1800c4700`
- end: `0x1800c47cc`
- name: `?MapFile@CAtlFileMappingBase@ATL@@QEAAJPEAX_K1KK@Z`
- size: `204`
- prototype: `int(ATL::CAtlFileMappingBase *__hidden this, void *, unsigned __int64, unsigned __int64, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800c45c0`
- `0x1800d2e40`

## callees

- `0x180016f48`
- `0x1800c4700`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800c4725`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800c4725`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c47ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c47ad`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x1800c4794`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x1800c4794`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800c474e`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800c474e`

## pseudocode

```c
__int64 __fastcall ATL::CAtlFileMappingBase::MapFile(ATL::CAtlFileMappingBase *this, void *a2)
{
  HANDLE FileMappingW; // rax
  void *v5; // rcx
  __int64 result; // rax
  SIZE_T v7; // rax
  LPVOID v8; // rax
  unsigned int Error; // ebx
  SIZE_T dwNumberOfBytesToMap; // [rsp+58h] [rbp+20h] BYREF

  HIDWORD(dwNumberOfBytesToMap) = 0;
  LODWORD(dwNumberOfBytesToMap) = GetFileSize(a2, (LPDWORD)&dwNumberOfBytesToMap + 1);
  FileMappingW = CreateFileMappingW(a2, 0, 2u, HIDWORD(dwNumberOfBytesToMap), dwNumberOfBytesToMap, 0);
  *((_QWORD *)this + 2) = FileMappingW;
  v5 = FileMappingW;
  if ( !FileMappingW )
    return ATL::AtlHresultFromLastError();
  v7 = dwNumberOfBytesToMap;
  *((_QWORD *)this + 1) = dwNumberOfBytesToMap;
  *((_DWORD *)this + 8) = 4;
  *((_QWORD *)this + 3) = 0;
  v8 = MapViewOfFileEx(v5, 4u, 0, 0, v7, 0);
  *(_QWORD *)this = v8;
  if ( v8 )
    return 0;
  Error = ATL::AtlHresultFromLastError();
  CloseHandle(*((HANDLE *)this + 2));
  result = Error;
  *((_QWORD *)this + 2) = 0;
  return result;
}

```

## disassembly

```asm
0x1800c4700  mov     rax, rsp
0x1800c4703  mov     [rax+8], rbx
0x1800c4707  mov     [rax+20h], r9
0x1800c470b  push    rdi
0x1800c470c  sub     rsp, 30h
0x1800c4710  mov     rbx, rdx
0x1800c4713  mov     qword ptr [rax+20h], 0
0x1800c471b  mov     rdi, rcx
0x1800c471e  lea     rdx, [rax+24h]; lpFileSizeHigh
0x1800c4722  mov     rcx, rbx; hFile
0x1800c4725  call    cs:__imp_GetFileSize
0x1800c472b  xor     edx, edx; lpFileMappingAttributes
0x1800c472d  mov     [rsp+38h+lpName], 0; lpName
0x1800c4736  mov     dword ptr [rsp+38h+dwNumberOfBytesToMap], eax
0x1800c473a  mov     rcx, rbx; hFile
0x1800c473d  mov     r9, [rsp+38h+dwNumberOfBytesToMap]
0x1800c4742  shr     r9, 20h; dwMaximumSizeHigh
0x1800c4746  lea     r8d, [rdx+2]; flProtect
0x1800c474a  mov     [rsp+38h+dwMaximumSizeLow], eax; dwMaximumSizeLow
0x1800c474e  call    cs:__imp_CreateFileMappingW
0x1800c4754  mov     [rdi+10h], rax
0x1800c4758  mov     rcx, rax; hFileMappingObject
0x1800c475b  test    rax, rax
0x1800c475e  jnz     short loc_1800C4767
0x1800c4760  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800c4765  jmp     short loc_1800C47C1
0x1800c4767  mov     rax, [rsp+38h+dwNumberOfBytesToMap]
0x1800c476c  mov     edx, 4; dwDesiredAccess
0x1800c4771  mov     [rdi+8], rax
0x1800c4775  xor     r9d, r9d; dwFileOffsetLow
0x1800c4778  mov     [rsp+38h+lpName], 0; lpBaseAddress
0x1800c4781  xor     r8d, r8d; dwFileOffsetHigh
0x1800c4784  mov     [rdi+20h], edx
0x1800c4787  mov     qword ptr [rdi+18h], 0
0x1800c478f  mov     qword ptr [rsp+38h+dwMaximumSizeLow], rax; dwNumberOfBytesToMap
0x1800c4794  call    cs:__imp_MapViewOfFileEx
0x1800c479a  mov     [rdi], rax
0x1800c479d  test    rax, rax
0x1800c47a0  jnz     short loc_1800C47BF
0x1800c47a2  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800c47a7  mov     rcx, [rdi+10h]; hObject
0x1800c47ab  mov     ebx, eax
0x1800c47ad  call    cs:__imp_CloseHandle
0x1800c47b3  mov     eax, ebx
0x1800c47b5  mov     qword ptr [rdi+10h], 0
0x1800c47bd  jmp     short loc_1800C47C1
0x1800c47bf  xor     eax, eax
0x1800c47c1  mov     rbx, [rsp+38h+arg_0]
0x1800c47c6  add     rsp, 30h
0x1800c47ca  pop     rdi
0x1800c47cb  retn
```
