# CVaultNonTransacted::FileOperationsMoveFile(ushort *,ushort *)

- ea: `0x1800407f0`
- end: `0x18004081f`
- name: `?FileOperationsMoveFile@CVaultNonTransacted@@UEAAKPEAG0@Z`
- size: `47`
- prototype: `unsigned int(CVaultNonTransacted *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800407f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040811`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180040803`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180040803`

## pseudocode

```c
DWORD __fastcall CVaultNonTransacted::FileOperationsMoveFile(
        CVaultNonTransacted *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  if ( MoveFileExW(a2, a3, 2u) )
    return 0;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x1800407f0  sub     rsp, 28h
0x1800407f4  mov     rax, r8
0x1800407f7  mov     rcx, rdx; lpExistingFileName
0x1800407fa  mov     rdx, rax; lpNewFileName
0x1800407fd  mov     r8d, 2; dwFlags
0x180040803  call    cs:__imp_MoveFileExW
0x180040809  test    eax, eax
0x18004080b  jnz     short loc_180040818
0x18004080d  add     rsp, 28h
0x180040811  jmp     cs:__imp_GetLastError
0x180040818  xor     eax, eax
0x18004081a  add     rsp, 28h
0x18004081e  retn
```
