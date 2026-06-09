# CSharedAccessFile::SetFilePosition(__int64,ulong)

- ea: `0x180023494`
- end: `0x180023547`
- name: `?SetFilePosition@CSharedAccessFile@@QEAAH_JK@Z`
- size: `179`
- prototype: `__int64 __fastcall(CSharedAccessFile *__hidden this, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180023038`
- `0x180023aa0`

## callees

- `0x180023494`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002352b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002352b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800234d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800234e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023515`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800234d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800234e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023515`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180023504`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180023504`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800234be`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800234be`

## pseudocode

```c
__int64 __fastcall CSharedAccessFile::SetFilePosition(HANDLE *this, __int64 a2, DWORD a3)
{
  HANDLE v4; // rcx
  LONG v6; // [rsp+3Ch] [rbp+14h] BYREF
  DWORD FileSizeHigh; // [rsp+40h] [rbp+18h] BYREF

  FileSizeHigh = a3;
  v6 = 0;
  if ( SetFilePointer(*this, 0, &v6, 2u) == -1 && GetLastError() )
  {
    if ( GetLastError() != 1 )
      return 0;
    v4 = *this;
    FileSizeHigh = 0;
    if ( GetFileSize(v4, &FileSizeHigh) != -1 || GetLastError() != 1 )
    {
      SetLastError(1u);
      return 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180023494  mov     rax, rsp
0x180023497  mov     [rax+18h], r8d
0x18002349b  mov     [rax+10h], rdx
0x18002349f  push    rbx
0x1800234a0  sub     rsp, 20h
0x1800234a4  mov     rbx, rcx
0x1800234a7  mov     qword ptr [rax+10h], 0
0x1800234af  mov     rcx, [rcx]; hFile
0x1800234b2  lea     r8, [rax+14h]; lpDistanceToMoveHigh
0x1800234b6  mov     r9d, 2; dwMoveMethod
0x1800234bc  xor     edx, edx; lDistanceToMove
0x1800234be  call    cs:__imp_SetFilePointer
0x1800234c5  nop     dword ptr [rax+rax+00h]
0x1800234ca  mov     [rsp+28h+arg_8], eax
0x1800234ce  cmp     eax, 0FFFFFFFFh
0x1800234d1  jnz     short loc_18002353B
0x1800234d3  call    cs:__imp_GetLastError
0x1800234da  nop     dword ptr [rax+rax+00h]
0x1800234df  test    eax, eax
0x1800234e1  jz      short loc_18002353B
0x1800234e3  call    cs:__imp_GetLastError
0x1800234ea  nop     dword ptr [rax+rax+00h]
0x1800234ef  cmp     eax, 1
0x1800234f2  jnz     short loc_180023537
0x1800234f4  mov     rcx, [rbx]; hFile
0x1800234f7  lea     rdx, [rsp+28h+FileSizeHigh]; lpFileSizeHigh
0x1800234fc  mov     [rsp+28h+FileSizeHigh], 0
0x180023504  call    cs:__imp_GetFileSize
0x18002350b  nop     dword ptr [rax+rax+00h]
0x180023510  cmp     eax, 0FFFFFFFFh
0x180023513  jnz     short loc_180023526
0x180023515  call    cs:__imp_GetLastError
0x18002351c  nop     dword ptr [rax+rax+00h]
0x180023521  cmp     eax, 1
0x180023524  jz      short loc_18002353B
0x180023526  mov     ecx, 1; dwErrCode
0x18002352b  call    cs:__imp_SetLastError
0x180023532  nop     dword ptr [rax+rax+00h]
0x180023537  xor     eax, eax
0x180023539  jmp     short loc_180023540
0x18002353b  mov     eax, 1
0x180023540  add     rsp, 20h
0x180023544  pop     rbx
0x180023545  retn
```
