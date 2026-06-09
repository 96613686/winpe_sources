# FFileExists(ushort *,int)

- ea: `0x180030d94`
- end: `0x180030df7`
- name: `?FFileExists@@YAHPEAGH@Z`
- size: `99`
- prototype: `__int64 __fastcall(unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180030cdc`

## callees

- `0x180030d94`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030de2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030de2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180030dc2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180030dc2`

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
0x180030d94  push    rbx
0x180030d96  sub     rsp, 40h
0x180030d9a  neg     edx
0x180030d9c  mov     edx, 80000000h; dwDesiredAccess
0x180030da1  sbb     eax, eax
0x180030da3  xor     ebx, ebx
0x180030da5  and     eax, 1FFFF90h
0x180030daa  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x180030daf  sub     eax, 0FFFFFF80h
0x180030db2  xor     r9d, r9d; lpSecurityAttributes
0x180030db5  mov     [rsp+48h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180030db9  lea     r8d, [rbx+3]; dwShareMode
0x180030dbd  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x180030dc2  call    cs:__imp_CreateFileW
0x180030dc9  nop     dword ptr [rax+rax+00h]
0x180030dce  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180030dd2  lea     rcx, [rax-1]
0x180030dd6  setnz   bl
0x180030dd9  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180030ddd  ja      short loc_180030DEE
0x180030ddf  mov     rcx, rax; hObject
0x180030de2  call    cs:__imp_CloseHandle
0x180030de9  nop     dword ptr [rax+rax+00h]
0x180030dee  mov     eax, ebx
0x180030df0  add     rsp, 40h
0x180030df4  pop     rbx
0x180030df5  retn
```
