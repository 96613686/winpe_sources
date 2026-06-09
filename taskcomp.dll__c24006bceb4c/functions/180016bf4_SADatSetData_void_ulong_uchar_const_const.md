# SADatSetData(void *,ulong,uchar const * const)

- ea: `0x180016bf4`
- end: `0x180016c4d`
- name: `?SADatSetData@@YAJPEAXKQEBE@Z`
- size: `89`
- prototype: `int __fastcall(void *, __int64, const unsigned __int8 *const)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800168b8`
- `0x180016dd8`

## callees

- `0x180016bf4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c24`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180016c1a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180016c1a`

## pseudocode

```c
int __fastcall SADatSetData(void *a1, __int64 a2, const unsigned __int8 *const a3)
{
  int result; // eax
  DWORD v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  if ( WriteFile(a1, a3, 6u, &v4, 0) )
    return v4 != 6 ? 0x8000FFFF : 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180016bf4  mov     rax, rsp
0x180016bf7  mov     [rax+10h], edx
0x180016bfa  sub     rsp, 38h
0x180016bfe  mov     rdx, r8; lpBuffer
0x180016c01  mov     dword ptr [rax+10h], 0
0x180016c08  mov     r8d, 6; nNumberOfBytesToWrite
0x180016c0e  mov     qword ptr [rax-18h], 0
0x180016c16  lea     r9, [rax+10h]; lpNumberOfBytesWritten
0x180016c1a  call    cs:__imp_WriteFile
0x180016c20  test    eax, eax
0x180016c22  jnz     short loc_180016C38
0x180016c24  call    cs:__imp_GetLastError
0x180016c2a  test    eax, eax
0x180016c2c  jle     short loc_180016C48
0x180016c2e  movzx   eax, ax
0x180016c31  or      eax, 80070000h
0x180016c36  jmp     short loc_180016C48
0x180016c38  mov     eax, [rsp+38h+arg_8]
0x180016c3c  sub     eax, 6
0x180016c3f  neg     eax
0x180016c41  sbb     eax, eax
0x180016c43  and     eax, 8000FFFFh
0x180016c48  add     rsp, 38h
0x180016c4c  retn
```
