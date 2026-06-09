# __dcrt_lowio_ensure_console_output_initialized

- ea: `0x100422cc0`
- end: `0x100422d12`
- name: `__dcrt_lowio_ensure_console_output_initialized`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1004222e8`

## callees

- `0x100422cc0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x100422cf6`
- `KERNEL32!CreateFileW` at `0x100422cf6`

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
0x100422cc0  push    rbx
0x100422cc2  sub     rsp, 40h
0x100422cc6  mov     rax, cs:hObject
0x100422ccd  xor     ebx, ebx
0x100422ccf  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x100422cd3  jnz     short loc_100422D03
0x100422cd5  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x100422cda  lea     r8d, [rbx+3]; dwShareMode
0x100422cde  mov     [rsp+48h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x100422ce2  lea     rcx, FileName; "CONOUT$"
0x100422ce9  xor     r9d, r9d; lpSecurityAttributes
0x100422cec  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x100422cf1  mov     edx, 40000000h; dwDesiredAccess
0x100422cf6  call    cs:__imp_CreateFileW
0x100422cfc  mov     cs:hObject, rax
0x100422d03  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x100422d07  setnz   bl
0x100422d0a  mov     eax, ebx
0x100422d0c  add     rsp, 40h
0x100422d10  pop     rbx
0x100422d11  retn
```
