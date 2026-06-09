# SacHandleOpen

- ea: `0x18002735c`
- end: `0x1800273d7`
- name: `SacHandleOpen`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180026e8c`

## callees

- `0x18002735c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800273a2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800273a2`

## pseudocode

```c
_BOOL8 __fastcall SacHandleOpen(_QWORD *a1)
{
  HANDLE FileW; // rax

  if ( a1 )
  {
    FileW = CreateFileW(L"\\\\.\\SAC", 0xC0000000, 0, 0, 3u, 0, 0);
    *a1 = FileW;
    return FileW != (HANDLE)-1LL;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x18002735c  mov     [rsp+arg_0], rbx
0x180027361  push    rdi
0x180027362  sub     rsp, 50h
0x180027366  mov     rdi, rcx
0x180027369  mov     ebx, 1
0x18002736e  test    rcx, rcx
0x180027371  jnz     short loc_180027377
0x180027373  xor     ebx, ebx
0x180027375  jmp     short loc_1800273BD
0x180027377  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x180027380  mov     [rsp+58h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180027388  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x180027390  xor     r9d, r9d; lpSecurityAttributes
0x180027393  xor     r8d, r8d; dwShareMode
0x180027396  mov     edx, 0C0000000h; dwDesiredAccess
0x18002739b  lea     rcx, FileName; "\\\\.\\SAC"
0x1800273a2  call    cs:__imp_CreateFileW
0x1800273a9  nop     dword ptr [rax+rax+00h]
0x1800273ae  mov     rcx, rax
0x1800273b1  mov     [rdi], rax
0x1800273b4  xor     eax, eax
0x1800273b6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800273ba  cmovz   ebx, eax
0x1800273bd  mov     [rsp+58h+var_18], ebx
0x1800273c1  jmp     short loc_1800273C9
0x1800273c3  xor     ebx, ebx
0x1800273c5  mov     [rsp+58h+var_18], ebx
0x1800273c9  mov     eax, ebx
0x1800273cb  mov     rbx, [rsp+58h+arg_0]
0x1800273d0  add     rsp, 50h
0x1800273d4  pop     rdi
0x1800273d5  retn
```
