# CVaultTransacted::FileOperationsDeleteDirectory(ushort const *)

- ea: `0x180040760`
- end: `0x18004078a`
- name: `?FileOperationsDeleteDirectory@CVaultTransacted@@UEAAKPEBG@Z`
- size: `42`
- prototype: `unsigned int(CVaultTransacted *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180040760`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004077c`
- `api-ms-win-core-kernel32-legacy-l1-1-3!RemoveDirectoryTransactedW` at `0x18004076e`
- `api-ms-win-core-kernel32-legacy-l1-1-3!RemoveDirectoryTransactedW` at `0x18004076e`

## pseudocode

```c
DWORD __fastcall CVaultTransacted::FileOperationsDeleteDirectory(HANDLE *this, const unsigned __int16 *a2)
{
  if ( RemoveDirectoryTransactedW(a2, this[1]) )
    return 0;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x180040760  sub     rsp, 28h
0x180040764  mov     rax, rdx
0x180040767  mov     rdx, [rcx+8]; hTransaction
0x18004076b  mov     rcx, rax; lpPathName
0x18004076e  call    cs:__imp_RemoveDirectoryTransactedW
0x180040774  test    eax, eax
0x180040776  jnz     short loc_180040783
0x180040778  add     rsp, 28h
0x18004077c  jmp     cs:__imp_GetLastError
0x180040783  xor     eax, eax
0x180040785  add     rsp, 28h
0x180040789  retn
```
