# WSHCreateFile

- ea: `0x180008ea4`
- end: `0x180008f75`
- name: `WSHCreateFile`
- size: `209`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180008950`
- `0x180008bc0`

## callees

- `0x1800031f4`
- `0x180008a04`
- `0x180008ea4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180008f3d`
- `KERNEL32!GetLastError` at `0x180008f3d`
- `KERNEL32!CreateFileW` at `0x180008ee3`
- `KERNEL32!CreateFileW` at `0x180008ee3`
- `KERNEL32!CreateFileA` at `0x180008f20`
- `KERNEL32!CreateFileA` at `0x180008f20`

## pseudocode

```c
__int64 __fastcall WSHCreateFile(const WCHAR *a1, DWORD a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  bool v5; // zf
  HANDLE FileA; // rax
  int v8; // ebx
  signed int LastError; // eax

  v5 = !Global::g_fWindowsNT;
  *a5 = 0;
  if ( v5 )
  {
    v8 = UnicodeToMB(a1);
    if ( v8 < 0 )
      return (unsigned int)v8;
    FileA = CreateFileA(0, a2, 0, 0, 3u, 0x80u, 0);
  }
  else
  {
    FileA = CreateFileW(a1, a2, 0, 0, 3u, 0x80u, 0);
  }
  *a5 = FileA;
  if ( FileA == (HANDLE)-1LL )
  {
    *a5 = 0;
  }
  else if ( FileA )
  {
    return 0;
  }
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180008ea4  mov     rax, rsp
0x180008ea7  push    rbx
0x180008ea8  push    rbp
0x180008ea9  push    rsi
0x180008eaa  push    rdi
0x180008eab  sub     rsp, 58h
0x180008eaf  mov     rsi, [rsp+78h+arg_20]
0x180008eb7  xor     edi, edi
0x180008eb9  cmp     cs:?g_fWindowsNT@Global@@2_NA, dil; bool Global::g_fWindowsNT
0x180008ec0  mov     ebp, edx
0x180008ec2  mov     [rax-38h], rdi
0x180008ec6  mov     [rsi], rdi
0x180008ec9  jz      short loc_180008EEB
0x180008ecb  mov     [rax-48h], rdi
0x180008ecf  xor     r9d, r9d; lpSecurityAttributes
0x180008ed2  mov     dword ptr [rax-50h], 80h
0x180008ed9  xor     r8d, r8d; dwShareMode
0x180008edc  mov     dword ptr [rax-58h], 3
0x180008ee3  call    cs:__imp_CreateFileW
0x180008ee9  jmp     short loc_180008F26
0x180008eeb  lea     rdx, [rsp+78h+lpFileName]
0x180008ef0  call    UnicodeToMB
0x180008ef5  mov     ebx, eax
0x180008ef7  test    eax, eax
0x180008ef9  js      short loc_180008F58
0x180008efb  mov     [rsp+78h+hTemplateFile], rdi; hTemplateFile
0x180008f00  xor     r9d, r9d; lpSecurityAttributes
0x180008f03  mov     rdi, [rsp+78h+lpFileName]
0x180008f08  xor     r8d, r8d; dwShareMode
0x180008f0b  mov     rcx, rdi; lpFileName
0x180008f0e  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180008f16  mov     edx, ebp; dwDesiredAccess
0x180008f18  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x180008f20  call    cs:__imp_CreateFileA
0x180008f26  mov     [rsi], rax
0x180008f29  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008f2d  jnz     short loc_180008F38
0x180008f2f  mov     qword ptr [rsi], 0
0x180008f36  jmp     short loc_180008F3D
0x180008f38  test    rax, rax
0x180008f3b  jnz     short loc_180008F54
0x180008f3d  call    cs:__imp_GetLastError
0x180008f43  mov     ebx, eax
0x180008f45  test    eax, eax
0x180008f47  jle     short loc_180008F5D
0x180008f49  movzx   ebx, ax
0x180008f4c  or      ebx, 80070000h
0x180008f52  jmp     short loc_180008F5D
0x180008f54  xor     ebx, ebx
0x180008f56  jmp     short loc_180008F5D
0x180008f58  mov     rdi, [rsp+78h+lpFileName]
0x180008f5d  test    rdi, rdi
0x180008f60  jz      short loc_180008F6A
0x180008f62  mov     rcx, rdi; Block
0x180008f65  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008f6a  mov     eax, ebx
0x180008f6c  add     rsp, 58h
0x180008f70  pop     rdi
0x180008f71  pop     rsi
0x180008f72  pop     rbp
0x180008f73  pop     rbx
0x180008f74  retn
```
