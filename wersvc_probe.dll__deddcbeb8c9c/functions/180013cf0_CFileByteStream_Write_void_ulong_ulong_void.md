# CFileByteStream::Write(void *,ulong,ulong *,void *)

- ea: `0x180013cf0`
- end: `0x180013d30`
- name: `?Write@CFileByteStream@@UEAAJPEAXKPEAK0@Z`
- size: `64`
- prototype: `__int64 __fastcall(CFileByteStream *__hidden this, void *, unsigned int, unsigned int *, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180013cf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d0f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180013d01`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180013d01`

## pseudocode

```c
signed int __fastcall CFileByteStream::Write(HANDLE *this, void *a2, DWORD a3, unsigned int *a4)
{
  signed int result; // eax

  if ( WriteFile(this[1], a2, a3, a4, 0) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( result >= 0 )
    return -2147467259;
  return result;
}

```

## disassembly

```asm
0x180013cf0  sub     rsp, 38h
0x180013cf4  mov     rcx, [rcx+8]; hFile
0x180013cf8  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x180013d01  call    cs:__imp_WriteFile
0x180013d07  test    eax, eax
0x180013d09  jz      short loc_180013D0F
0x180013d0b  xor     eax, eax
0x180013d0d  jmp     short loc_180013D2B
0x180013d0f  call    cs:__imp_GetLastError
0x180013d15  test    eax, eax
0x180013d17  jle     short loc_180013D21
0x180013d19  movzx   eax, ax
0x180013d1c  or      eax, 80070000h
0x180013d21  test    eax, eax
0x180013d23  mov     ecx, 80004005h
0x180013d28  cmovns  eax, ecx
0x180013d2b  add     rsp, 38h
0x180013d2f  retn
```
