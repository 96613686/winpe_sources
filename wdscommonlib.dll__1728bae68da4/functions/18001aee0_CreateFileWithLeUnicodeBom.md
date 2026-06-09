# CreateFileWithLeUnicodeBom

- ea: `0x18001aee0`
- end: `0x18001afc9`
- name: `CreateFileWithLeUnicodeBom`
- size: `233`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x18001aee0`
- `0x18001b0cc`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18001af6d`
- `KERNEL32!WriteFile` at `0x18001af6d`
- `KERNEL32!CreateFileW` at `0x18001af1c`
- `KERNEL32!CreateFileW` at `0x18001af1c`
- `KERNEL32!GetLastError` at `0x18001af31`
- `KERNEL32!GetLastError` at `0x18001af7d`
- `KERNEL32!GetLastError` at `0x18001af31`
- `KERNEL32!GetLastError` at `0x18001af7d`
- `KERNEL32!CloseHandle` at `0x18001afa5`
- `KERNEL32!CloseHandle` at `0x18001afa5`

## pseudocode

```c
__int64 __fastcall CreateFileWithLeUnicodeBom(const WCHAR *a1, _QWORD *a2)
{
  unsigned int v2; // ebx
  HANDLE FileW; // rax
  void *v5; // rdi
  DWORD LastError; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  DWORD v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // eax
  __int16 Buffer; // [rsp+60h] [rbp+18h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+68h] [rbp+20h] BYREF

  v2 = 0;
  Buffer = -257;
  NumberOfBytesWritten = 0;
  FileW = CreateFileW(a1, 0x40000000u, 1u, 0, 2u, 0x80u, 0);
  v5 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v2 = ElValidateWin32_8(LastError, v7, v8, 5059);
    if ( !v2 )
      return 31;
  }
  else if ( WriteFile(FileW, &Buffer, 2u, &NumberOfBytesWritten, 0) )
  {
    *a2 = v5;
  }
  else
  {
    v9 = GetLastError();
    v12 = ElValidateWin32_8(v9, v10, v11, 5067);
    if ( !v12 )
      v12 = 31;
    v2 = v12;
    CloseHandle(v5);
  }
  return v2;
}

```

## disassembly

```asm
0x18001aee0  mov     rax, rsp
0x18001aee3  mov     [rax+8], rbx
0x18001aee7  mov     [rax+10h], rsi
0x18001aeeb  push    rdi
0x18001aeec  sub     rsp, 40h
0x18001aef0  xor     ebx, ebx
0x18001aef2  mov     word ptr [rax+18h], 0FEFFh
0x18001aef8  and     [rax-18h], rbx
0x18001aefc  mov     rsi, rdx
0x18001aeff  and     [rax+20h], ebx
0x18001af02  xor     r9d, r9d; lpSecurityAttributes
0x18001af05  mov     dword ptr [rax-20h], 80h
0x18001af0c  mov     edx, 40000000h; dwDesiredAccess
0x18001af11  lea     r8d, [rbx+1]; dwShareMode
0x18001af15  mov     dword ptr [rax-28h], 2
0x18001af1c  call    cs:__imp_CreateFileW
0x18001af23  nop     dword ptr [rax+rax+00h]
0x18001af28  mov     rdi, rax
0x18001af2b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001af2f  jnz     short loc_18001AF55
0x18001af31  call    cs:__imp_GetLastError
0x18001af38  nop     dword ptr [rax+rax+00h]
0x18001af3d  mov     ecx, eax
0x18001af3f  mov     r9d, 13C3h
0x18001af45  call    ElValidateWin32_8
0x18001af4a  mov     ebx, eax
0x18001af4c  test    eax, eax
0x18001af4e  jnz     short loc_18001AFB6
0x18001af50  lea     ebx, [rdi+20h]
0x18001af53  jmp     short loc_18001AFB6
0x18001af55  and     [rsp+48h+var_28], rbx
0x18001af5a  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001af5f  mov     r8d, 2; nNumberOfBytesToWrite
0x18001af65  lea     rdx, [rsp+48h+Buffer]; lpBuffer
0x18001af6a  mov     rcx, rdi; hFile
0x18001af6d  call    cs:__imp_WriteFile
0x18001af74  nop     dword ptr [rax+rax+00h]
0x18001af79  test    eax, eax
0x18001af7b  jnz     short loc_18001AFB3
0x18001af7d  call    cs:__imp_GetLastError
0x18001af84  nop     dword ptr [rax+rax+00h]
0x18001af89  mov     ecx, eax
0x18001af8b  mov     r9d, 13CBh
0x18001af91  call    ElValidateWin32_8
0x18001af96  test    eax, eax
0x18001af98  mov     ebx, 1Fh
0x18001af9d  mov     rcx, rdi; hObject
0x18001afa0  cmovz   eax, ebx
0x18001afa3  mov     ebx, eax
0x18001afa5  call    cs:__imp_CloseHandle
0x18001afac  nop     dword ptr [rax+rax+00h]
0x18001afb1  jmp     short loc_18001AFB6
0x18001afb3  mov     [rsi], rdi
0x18001afb6  mov     rsi, [rsp+48h+arg_8]
0x18001afbb  mov     eax, ebx
0x18001afbd  mov     rbx, [rsp+48h+arg_0]
0x18001afc2  add     rsp, 40h
0x18001afc6  pop     rdi
0x18001afc7  retn
```
