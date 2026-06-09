# CVaultNonTransacted::FileOperationsDeleteDirectory(ushort const *)

- ea: `0x180040730`
- end: `0x180040753`
- name: `?FileOperationsDeleteDirectory@CVaultNonTransacted@@UEAAKPEBG@Z`
- size: `35`
- prototype: `unsigned int(CVaultNonTransacted *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180040730`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040745`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180040737`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180040737`

## pseudocode

```c
DWORD __fastcall CVaultNonTransacted::FileOperationsDeleteDirectory(
        CVaultNonTransacted *this,
        const unsigned __int16 *a2)
{
  if ( RemoveDirectoryW(a2) )
    return 0;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x180040730  sub     rsp, 28h
0x180040734  mov     rcx, rdx; lpPathName
0x180040737  call    cs:__imp_RemoveDirectoryW
0x18004073d  test    eax, eax
0x18004073f  jnz     short loc_18004074C
0x180040741  add     rsp, 28h
0x180040745  jmp     cs:__imp_GetLastError
0x18004074c  xor     eax, eax
0x18004074e  add     rsp, 28h
0x180040752  retn
```
