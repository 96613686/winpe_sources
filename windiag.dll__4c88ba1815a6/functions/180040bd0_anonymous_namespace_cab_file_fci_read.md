# _anonymous_namespace_::cab_file::fci_read

- ea: `0x180040bd0`
- end: `0x180040c10`
- name: `_anonymous_namespace_::cab_file::fci_read`
- size: `64`
- prototype: `UINT __cdecl(INT_PTR hf, void *memory, UINT cb, int *err, void *pv)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180040bd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040bff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040bff`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180040bef`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180040bef`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::cab_file::fci_read(INT_PTR hf, void *memory, UINT cb, DWORD *err)
{
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-18h] BYREF

  NumberOfBytesRead = 0;
  if ( ReadFile((HANDLE)hf, memory, cb, &NumberOfBytesRead, 0) )
    return NumberOfBytesRead;
  *err = GetLastError();
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x180040bd0  push    rbx
0x180040bd2  sub     rsp, 40h
0x180040bd6  mov     rbx, r9
0x180040bd9  mov     [rsp+48h+NumberOfBytesRead], 0
0x180040be1  lea     r9, [rsp+48h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180040be6  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x180040bef  call    cs:__imp_ReadFile
0x180040bf5  test    eax, eax
0x180040bf7  jz      short loc_180040BFF
0x180040bf9  mov     eax, [rsp+48h+NumberOfBytesRead]
0x180040bfd  jmp     short loc_180040C0A
0x180040bff  call    cs:__imp_GetLastError
0x180040c05  mov     [rbx], eax
0x180040c07  or      eax, 0FFFFFFFFh
0x180040c0a  add     rsp, 40h
0x180040c0e  pop     rbx
0x180040c0f  retn
```
