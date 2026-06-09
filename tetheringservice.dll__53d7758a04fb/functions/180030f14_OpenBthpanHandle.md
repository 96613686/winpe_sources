# OpenBthpanHandle

- ea: `0x180030f14`
- end: `0x180030f72`
- name: `OpenBthpanHandle`
- size: `94`
- prototype: `DWORD __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180030204`
- `0x180030f78`

## callees

- `0x180030f14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030f60`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180030f4f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180030f4f`

## pseudocode

```c
DWORD __fastcall OpenBthpanHandle(_QWORD *a1)
{
  HANDLE FileW; // rax

  *a1 = -1;
  FileW = CreateFileW(L"\\\\.\\\\BthPan", 0xC0000000, 0, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
    return GetLastError();
  *a1 = FileW;
  return 0;
}

```

## disassembly

```asm
0x180030f14  push    rbx
0x180030f16  sub     rsp, 40h
0x180030f1a  mov     rbx, rcx
0x180030f1d  mov     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x180030f24  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180030f2d  lea     rcx, FileName; "\\\\.\\\\BthPan"
0x180030f34  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180030f3c  xor     r9d, r9d; lpSecurityAttributes
0x180030f3f  xor     r8d, r8d; dwShareMode
0x180030f42  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180030f4a  mov     edx, 0C0000000h; dwDesiredAccess
0x180030f4f  call    cs:__imp_CreateFileW
0x180030f55  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180030f59  jnz     short loc_180030F67
0x180030f5b  add     rsp, 40h
0x180030f5f  pop     rbx
0x180030f60  jmp     cs:__imp_GetLastError
0x180030f67  mov     [rbx], rax
0x180030f6a  xor     eax, eax
0x180030f6c  add     rsp, 40h
0x180030f70  pop     rbx
0x180030f71  retn
```
