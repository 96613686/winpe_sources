# __dcrt_lowio_ensure_console_output_initialized

- ea: `0x10043816c`
- end: `0x1004381be`
- name: `__dcrt_lowio_ensure_console_output_initialized`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x100437270`

## callees

- `0x10043816c`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1004381a2`
- `KERNEL32!CreateFileW` at `0x1004381a2`

## pseudocode

```c
__int64 _dcrt_lowio_ensure_console_output_initialized()
{
  char *FileW; // rax
  unsigned int v1; // ebx

  FileW = (char *)hObject;
  v1 = 0;
  if ( hObject == (HANDLE)-2LL )
  {
    FileW = (char *)CreateFileW(L"CONOUT$", 0x40000000u, 3u, 0, 3u, 0, 0);
    hObject = FileW;
  }
  LOBYTE(v1) = FileW + 1 != 0;
  return v1;
}

```

## disassembly

```asm
0x10043816c  push    rbx
0x10043816e  sub     rsp, 40h
0x100438172  mov     rax, cs:hObject
0x100438179  xor     ebx, ebx
0x10043817b  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x10043817f  jnz     short loc_1004381AF
0x100438181  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x100438186  lea     r8d, [rbx+3]; dwShareMode
0x10043818a  mov     [rsp+48h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x10043818e  lea     rcx, FileName; "CONOUT$"
0x100438195  xor     r9d, r9d; lpSecurityAttributes
0x100438198  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x10043819d  mov     edx, 40000000h; dwDesiredAccess
0x1004381a2  call    cs:__imp_CreateFileW
0x1004381a8  mov     cs:hObject, rax
0x1004381af  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1004381b3  setnz   bl
0x1004381b6  mov     eax, ebx
0x1004381b8  add     rsp, 40h
0x1004381bc  pop     rbx
0x1004381bd  retn
```
