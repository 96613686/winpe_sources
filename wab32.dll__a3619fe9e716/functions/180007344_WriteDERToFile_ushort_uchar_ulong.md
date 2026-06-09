# WriteDERToFile(ushort *,uchar *,ulong)

- ea: `0x180007344`
- end: `0x1800073ee`
- name: `?WriteDERToFile@@YAJPEAGPEAEK@Z`
- size: `170`
- prototype: `int(unsigned __int16 *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000597c`

## callees

- `0x180007344`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180007382`
- `KERNEL32!CreateFileW` at `0x180007382`
- `KERNEL32!WriteFile` at `0x1800073af`
- `KERNEL32!WriteFile` at `0x1800073af`
- `KERNEL32!CloseHandle` at `0x1800073d6`
- `KERNEL32!CloseHandle` at `0x1800073d6`

## pseudocode

```c
__int64 __fastcall WriteDERToFile(unsigned __int16 *a1, unsigned __int8 *a2, DWORD a3)
{
  HANDLE FileW; // rax
  void *v6; // rdi
  unsigned int v7; // ebx
  DWORD NumberOfBytesWritten; // [rsp+68h] [rbp+20h] BYREF

  NumberOfBytesWritten = 0;
  FileW = CreateFileW(a1, 0xC0000000, 0, 0, 2u, 0, 0);
  v6 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v7 = -2147221226;
LABEL_8:
    CloseHandle(v6);
    return v7;
  }
  if ( WriteFile(FileW, a2, a3, &NumberOfBytesWritten, 0) )
  {
    v7 = 0;
    if ( a3 != NumberOfBytesWritten )
      v7 = -2147467259;
  }
  else
  {
    v7 = -2147221226;
  }
  if ( v6 )
    goto LABEL_8;
  return v7;
}

```

## disassembly

```asm
0x180007344  mov     rax, rsp
0x180007347  mov     [rax+8], rbx
0x18000734b  mov     [rax+10h], rsi
0x18000734f  push    rdi
0x180007350  sub     rsp, 40h
0x180007354  mov     qword ptr [rax-18h], 0
0x18000735c  mov     esi, r8d
0x18000735f  mov     rbx, rdx
0x180007362  mov     dword ptr [rax-20h], 0
0x180007369  xor     r8d, r8d; dwShareMode
0x18000736c  mov     dword ptr [rax-28h], 2
0x180007373  mov     edx, 0C0000000h; dwDesiredAccess
0x180007378  mov     dword ptr [rax+20h], 0
0x18000737f  xor     r9d, r9d; lpSecurityAttributes
0x180007382  call    cs:__imp_CreateFileW
0x180007388  mov     rdi, rax
0x18000738b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000738f  jnz     short loc_180007398
0x180007391  mov     ebx, 80040116h
0x180007396  jmp     short loc_1800073D3
0x180007398  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000739d  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x1800073a6  mov     r8d, esi; nNumberOfBytesToWrite
0x1800073a9  mov     rdx, rbx; lpBuffer
0x1800073ac  mov     rcx, rdi; hFile
0x1800073af  call    cs:__imp_WriteFile
0x1800073b5  test    eax, eax
0x1800073b7  jnz     short loc_1800073C0
0x1800073b9  mov     ebx, 80040116h
0x1800073be  jmp     short loc_1800073CE
0x1800073c0  xor     ebx, ebx
0x1800073c2  mov     eax, 80004005h
0x1800073c7  cmp     esi, [rsp+48h+NumberOfBytesWritten]
0x1800073cb  cmovnz  ebx, eax
0x1800073ce  test    rdi, rdi
0x1800073d1  jz      short loc_1800073DC
0x1800073d3  mov     rcx, rdi; hObject
0x1800073d6  call    cs:__imp_CloseHandle
0x1800073dc  mov     rsi, [rsp+48h+arg_8]
0x1800073e1  mov     eax, ebx
0x1800073e3  mov     rbx, [rsp+48h+arg_0]
0x1800073e8  add     rsp, 40h
0x1800073ec  pop     rdi
0x1800073ed  retn
```
