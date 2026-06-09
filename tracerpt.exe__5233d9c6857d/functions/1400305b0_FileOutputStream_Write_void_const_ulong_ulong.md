# FileOutputStream::Write(void const *,ulong,ulong *)

- ea: `0x1400305b0`
- end: `0x1400305e8`
- name: `?Write@FileOutputStream@@UEAAJPEBXKPEAK@Z`
- size: `56`
- prototype: `__int64 __fastcall(FileOutputStream *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1400305b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400305cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400305cb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400305c1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400305c1`

## pseudocode

```c
__int64 __fastcall FileOutputStream::Write(HANDLE *this, const void *a2, DWORD a3, unsigned int *a4)
{
  unsigned int v4; // ebx
  signed int LastError; // eax

  v4 = 0;
  if ( !WriteFile(this[1], a2, a3, a4, 0) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v4;
}

```

## disassembly

```asm
0x1400305b0  push    rbx
0x1400305b2  sub     rsp, 30h
0x1400305b6  mov     rcx, [rcx+8]; hFile
0x1400305ba  xor     ebx, ebx
0x1400305bc  mov     [rsp+38h+lpOverlapped], rbx; lpOverlapped
0x1400305c1  call    cs:__imp_WriteFile
0x1400305c7  test    eax, eax
0x1400305c9  jnz     short loc_1400305E0
0x1400305cb  call    cs:__imp_GetLastError
0x1400305d1  mov     ebx, eax
0x1400305d3  test    eax, eax
0x1400305d5  jle     short loc_1400305E0
0x1400305d7  movzx   ebx, ax
0x1400305da  or      ebx, 80070000h
0x1400305e0  mov     eax, ebx
0x1400305e2  add     rsp, 30h
0x1400305e6  pop     rbx
0x1400305e7  retn
```
