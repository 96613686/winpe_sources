# _anonymous_namespace_::cab_file::fci_open

- ea: `0x180040b50`
- end: `0x180040bbe`
- name: `_anonymous_namespace_::cab_file::fci_open`
- size: `110`
- prototype: `INT_PTR __cdecl(LPSTR pszFile, int oflag, int pmode, int *err, void *pv)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180040b50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040bac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040bac`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180040ba0`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180040ba0`

## pseudocode

```c
INT_PTR __fastcall anonymous_namespace_::cab_file::fci_open(const CHAR *pszFile, __int16 oflag, int pmode, DWORD *err)
{
  DWORD v5; // eax
  INT_PTR result; // rax

  if ( (oflag & 2) != 0 )
  {
    v5 = -1073741824;
  }
  else
  {
    v5 = 0x80000000;
    if ( (oflag & 1) != 0 )
      v5 = 0x40000000;
  }
  result = (INT_PTR)CreateFileA(pszFile, v5, 7u, 0, ((oflag & 0x100) == 0) | 2u, 0x80u, 0);
  if ( result == -1 )
  {
    *err = GetLastError();
    return -1;
  }
  return result;
}

```

## disassembly

```asm
0x180040b50  push    rbx
0x180040b52  sub     rsp, 40h
0x180040b56  mov     rbx, r9
0x180040b59  test    dl, 2
0x180040b5c  jz      short loc_180040B65
0x180040b5e  mov     eax, 0C0000000h
0x180040b63  jmp     short loc_180040B77
0x180040b65  test    dl, 1
0x180040b68  mov     eax, 80000000h
0x180040b6d  mov     r8d, 40000000h
0x180040b73  cmovnz  eax, r8d
0x180040b77  shr     edx, 8
0x180040b7a  xor     r9d, r9d; lpSecurityAttributes
0x180040b7d  not     edx
0x180040b7f  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180040b88  and     edx, 1
0x180040b8b  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180040b93  or      edx, 2
0x180040b96  mov     [rsp+48h+dwCreationDisposition], edx; dwCreationDisposition
0x180040b9a  lea     r8d, [r9+7]; dwShareMode
0x180040b9e  mov     edx, eax; dwDesiredAccess
0x180040ba0  call    cs:__imp_CreateFileA
0x180040ba6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180040baa  jnz     short loc_180040BB8
0x180040bac  call    cs:__imp_GetLastError
0x180040bb2  mov     [rbx], eax
0x180040bb4  or      rax, 0FFFFFFFFFFFFFFFFh
0x180040bb8  add     rsp, 40h
0x180040bbc  pop     rbx
0x180040bbd  retn
```
