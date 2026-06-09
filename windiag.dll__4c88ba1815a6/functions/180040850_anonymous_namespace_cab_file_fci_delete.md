# _anonymous_namespace_::cab_file::fci_delete

- ea: `0x180040850`
- end: `0x180040878`
- name: `_anonymous_namespace_::cab_file::fci_delete`
- size: `40`
- prototype: `int __cdecl(LPSTR pszFile, int *err, void *pv)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180040850`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040867`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040867`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x180040859`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x180040859`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::cab_file::fci_delete(const CHAR *pszFile, DWORD *err, void *pv)
{
  if ( DeleteFileA(pszFile) )
    return 0;
  *err = GetLastError();
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x180040850  push    rbx
0x180040852  sub     rsp, 20h
0x180040856  mov     rbx, rdx
0x180040859  call    cs:__imp_DeleteFileA
0x18004085f  test    eax, eax
0x180040861  jz      short loc_180040867
0x180040863  xor     eax, eax
0x180040865  jmp     short loc_180040872
0x180040867  call    cs:__imp_GetLastError
0x18004086d  mov     [rbx], eax
0x18004086f  or      eax, 0FFFFFFFFh
0x180040872  add     rsp, 20h
0x180040876  pop     rbx
0x180040877  retn
```
