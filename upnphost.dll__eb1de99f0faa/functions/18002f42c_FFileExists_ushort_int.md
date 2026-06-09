# FFileExists(ushort *,int)

- ea: `0x18002f42c`
- end: `0x18002f482`
- name: `?FFileExists@@YAHPEAGH@Z`
- size: `86`
- prototype: `_BOOL8 __fastcall(unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18002f384`

## callees

- `0x18002f42c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f474`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f474`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002f45a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002f45a`

## pseudocode

```c
_BOOL8 __fastcall FFileExists(unsigned __int16 *a1, int a2)
{
  char *FileW; // rax
  BOOL v3; // ebx

  FileW = (char *)CreateFileW(a1, 0x80000000, 3u, 0, 3u, a2 != 0 ? 33554448 : 128, 0);
  v3 = FileW + 1 != 0;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  return v3;
}

```

## disassembly

```asm
0x18002f42c  push    rbx
0x18002f42e  sub     rsp, 40h
0x18002f432  neg     edx
0x18002f434  mov     edx, 80000000h; dwDesiredAccess
0x18002f439  sbb     eax, eax
0x18002f43b  xor     ebx, ebx
0x18002f43d  and     eax, 1FFFF90h
0x18002f442  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x18002f447  sub     eax, 0FFFFFF80h
0x18002f44a  xor     r9d, r9d; lpSecurityAttributes
0x18002f44d  mov     [rsp+48h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x18002f451  lea     r8d, [rbx+3]; dwShareMode
0x18002f455  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x18002f45a  call    cs:__imp_CreateFileW
0x18002f460  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002f464  lea     rcx, [rax-1]
0x18002f468  setnz   bl
0x18002f46b  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002f46f  ja      short loc_18002F47A
0x18002f471  mov     rcx, rax; hObject
0x18002f474  call    cs:__imp_CloseHandle
0x18002f47a  mov     eax, ebx
0x18002f47c  add     rsp, 40h
0x18002f480  pop     rbx
0x18002f481  retn
```
