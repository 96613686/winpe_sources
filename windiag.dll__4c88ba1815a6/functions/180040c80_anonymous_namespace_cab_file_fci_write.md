# _anonymous_namespace_::cab_file::fci_write

- ea: `0x180040c80`
- end: `0x180040cc0`
- name: `_anonymous_namespace_::cab_file::fci_write`
- size: `64`
- prototype: `UINT __cdecl(INT_PTR hf, void *memory, UINT cb, int *err, void *pv)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180040c80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040caf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040caf`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180040c9f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180040c9f`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::cab_file::fci_write(INT_PTR hf, void *memory, UINT cb, DWORD *err)
{
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-18h] BYREF

  NumberOfBytesWritten = 0;
  if ( WriteFile((HANDLE)hf, memory, cb, &NumberOfBytesWritten, 0) )
    return NumberOfBytesWritten;
  *err = GetLastError();
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x180040c80  push    rbx
0x180040c82  sub     rsp, 40h
0x180040c86  mov     rbx, r9
0x180040c89  mov     [rsp+48h+NumberOfBytesWritten], 0
0x180040c91  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180040c96  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x180040c9f  call    cs:__imp_WriteFile
0x180040ca5  test    eax, eax
0x180040ca7  jz      short loc_180040CAF
0x180040ca9  mov     eax, [rsp+48h+NumberOfBytesWritten]
0x180040cad  jmp     short loc_180040CBA
0x180040caf  call    cs:__imp_GetLastError
0x180040cb5  mov     [rbx], eax
0x180040cb7  or      eax, 0FFFFFFFFh
0x180040cba  add     rsp, 40h
0x180040cbe  pop     rbx
0x180040cbf  retn
```
