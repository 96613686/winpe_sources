# CVaultTransacted::FileOperationsCreateDirectory(ushort const *)

- ea: `0x1800401d0`
- end: `0x1800401f9`
- name: `?FileOperationsCreateDirectory@CVaultTransacted@@UEAAKPEBG@Z`
- size: `41`
- prototype: `unsigned int __fastcall(CVaultTransacted *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800401d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800401eb`
- `api-ms-win-core-kernel32-legacy-l1-1-3!CreateDirectoryTransactedW` at `0x1800401dd`
- `api-ms-win-core-kernel32-legacy-l1-1-3!CreateDirectoryTransactedW` at `0x1800401dd`

## pseudocode

```c
DWORD __fastcall CVaultTransacted::FileOperationsCreateDirectory(HANDLE *this, const unsigned __int16 *a2)
{
  if ( CreateDirectoryTransactedW(0, a2, 0, this[1]) )
    return 0;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x1800401d0  sub     rsp, 28h
0x1800401d4  mov     r9, [rcx+8]; hTransaction
0x1800401d8  xor     r8d, r8d; lpSecurityAttributes
0x1800401db  xor     ecx, ecx; lpTemplateDirectory
0x1800401dd  call    cs:__imp_CreateDirectoryTransactedW
0x1800401e3  test    eax, eax
0x1800401e5  jnz     short loc_1800401F2
0x1800401e7  add     rsp, 28h
0x1800401eb  jmp     cs:__imp_GetLastError
0x1800401f2  xor     eax, eax
0x1800401f4  add     rsp, 28h
0x1800401f8  retn
```
