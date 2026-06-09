# SADatSetData(void *,ulong,uchar const * const)

- ea: `0x180017b60`
- end: `0x180017bc6`
- name: `?SADatSetData@@YAJPEAXKQEBE@Z`
- size: `102`
- prototype: `int(void *, unsigned int, const unsigned __int8 *const)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800177d4`
- `0x180017d84`

## callees

- `0x180017b60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b96`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180017b86`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180017b86`

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
0x180017b60  mov     rax, rsp
0x180017b63  mov     [rax+10h], edx
0x180017b66  sub     rsp, 38h
0x180017b6a  mov     rdx, r8; lpBuffer
0x180017b6d  mov     dword ptr [rax+10h], 0
0x180017b74  mov     r8d, 6; nNumberOfBytesToWrite
0x180017b7a  mov     qword ptr [rax-18h], 0
0x180017b82  lea     r9, [rax+10h]; lpNumberOfBytesWritten
0x180017b86  call    cs:__imp_WriteFile
0x180017b8d  nop     dword ptr [rax+rax+00h]
0x180017b92  test    eax, eax
0x180017b94  jnz     short loc_180017BB0
0x180017b96  call    cs:__imp_GetLastError
0x180017b9d  nop     dword ptr [rax+rax+00h]
0x180017ba2  test    eax, eax
0x180017ba4  jle     short loc_180017BC0
0x180017ba6  movzx   eax, ax
0x180017ba9  or      eax, 80070000h
0x180017bae  jmp     short loc_180017BC0
0x180017bb0  mov     eax, [rsp+38h+arg_8]
0x180017bb4  sub     eax, 6
0x180017bb7  neg     eax
0x180017bb9  sbb     eax, eax
0x180017bbb  and     eax, 8000FFFFh
0x180017bc0  add     rsp, 38h
0x180017bc4  retn
```
