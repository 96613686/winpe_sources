# PolicyUtils::Cabinet::FdiCbFileOpen(char *,int,int)

- ea: `0x180027970`
- end: `0x1800279d3`
- name: `?FdiCbFileOpen@Cabinet@PolicyUtils@@YA_JPEADHH@Z`
- size: `99`
- prototype: `INT_PTR __fastcall(const CHAR *pszFile, unsigned int oflag, int pmode)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, registry_config`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800279bd`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800279bd`

## pseudocode

```c
INT_PTR __fastcall PolicyUtils::Cabinet::FdiCbFileOpen(const CHAR *pszFile, unsigned int oflag, int pmode)
{
  char v3; // al
  DWORD dwCreationDisposition; // r9d
  DWORD v5; // edx
  INT_PTR result; // rax

  v3 = oflag;
  dwCreationDisposition = (((oflag >> 8) & 1) == 0) | 2;
  v5 = (((oflag & 1) == 0) + 1) << 30;
  if ( (v3 & 2) != 0 )
    v5 = -1073741824;
  result = (INT_PTR)CreateFileA(pszFile, v5, 1u, 0, dwCreationDisposition, 0x80u, 0);
  if ( result == -1 )
    return -1;
  return result;
}

```

## disassembly

```asm
0x180027970  sub     rsp, 48h
0x180027974  mov     r9d, edx
0x180027977  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180027980  mov     eax, edx
0x180027982  shr     r9d, 8
0x180027986  not     edx
0x180027988  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180027990  mov     r8d, 1; dwShareMode
0x180027996  not     r9d
0x180027999  and     edx, r8d
0x18002799c  and     r9d, r8d
0x18002799f  add     edx, r8d
0x1800279a2  or      r9d, 2
0x1800279a6  shl     edx, 1Eh
0x1800279a9  mov     r10d, 0C0000000h
0x1800279af  test    al, 2
0x1800279b1  mov     [rsp+48h+dwCreationDisposition], r9d; dwCreationDisposition
0x1800279b6  cmovnz  edx, r10d; dwDesiredAccess
0x1800279ba  xor     r9d, r9d; lpSecurityAttributes
0x1800279bd  call    cs:__imp_CreateFileA
0x1800279c3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800279c7  cmp     rax, rcx
0x1800279ca  cmovz   rax, rcx
0x1800279ce  add     rsp, 48h
0x1800279d2  retn
```
