# CreateFileWithLeUnicodeBom

- ea: `0x18001a0a0`
- end: `0x18001a189`
- name: `CreateFileWithLeUnicodeBom`
- size: `233`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x18001a0a0`
- `0x18001a28c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001a0f1`
- `KERNEL32!GetLastError` at `0x18001a13d`
- `KERNEL32!GetLastError` at `0x18001a0f1`
- `KERNEL32!GetLastError` at `0x18001a13d`
- `KERNEL32!CloseHandle` at `0x18001a165`
- `KERNEL32!CloseHandle` at `0x18001a165`
- `KERNEL32!CreateFileW` at `0x18001a0dc`
- `KERNEL32!CreateFileW` at `0x18001a0dc`
- `KERNEL32!WriteFile` at `0x18001a12d`
- `KERNEL32!WriteFile` at `0x18001a12d`

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
0x18001a0a0  mov     rax, rsp
0x18001a0a3  mov     [rax+8], rbx
0x18001a0a7  mov     [rax+10h], rsi
0x18001a0ab  push    rdi
0x18001a0ac  sub     rsp, 40h
0x18001a0b0  xor     ebx, ebx
0x18001a0b2  mov     word ptr [rax+18h], 0FEFFh
0x18001a0b8  and     [rax-18h], rbx
0x18001a0bc  mov     rsi, rdx
0x18001a0bf  and     [rax+20h], ebx
0x18001a0c2  xor     r9d, r9d; lpSecurityAttributes
0x18001a0c5  mov     dword ptr [rax-20h], 80h
0x18001a0cc  mov     edx, 40000000h; dwDesiredAccess
0x18001a0d1  lea     r8d, [rbx+1]; dwShareMode
0x18001a0d5  mov     dword ptr [rax-28h], 2
0x18001a0dc  call    cs:__imp_CreateFileW
0x18001a0e3  nop     dword ptr [rax+rax+00h]
0x18001a0e8  mov     rdi, rax
0x18001a0eb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001a0ef  jnz     short loc_18001A115
0x18001a0f1  call    cs:__imp_GetLastError
0x18001a0f8  nop     dword ptr [rax+rax+00h]
0x18001a0fd  mov     ecx, eax
0x18001a0ff  mov     r9d, 13C3h
0x18001a105  call    ElValidateWin32_8
0x18001a10a  mov     ebx, eax
0x18001a10c  test    eax, eax
0x18001a10e  jnz     short loc_18001A176
0x18001a110  lea     ebx, [rdi+20h]
0x18001a113  jmp     short loc_18001A176
0x18001a115  and     [rsp+48h+var_28], rbx
0x18001a11a  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001a11f  mov     r8d, 2; nNumberOfBytesToWrite
0x18001a125  lea     rdx, [rsp+48h+Buffer]; lpBuffer
0x18001a12a  mov     rcx, rdi; hFile
0x18001a12d  call    cs:__imp_WriteFile
0x18001a134  nop     dword ptr [rax+rax+00h]
0x18001a139  test    eax, eax
0x18001a13b  jnz     short loc_18001A173
0x18001a13d  call    cs:__imp_GetLastError
0x18001a144  nop     dword ptr [rax+rax+00h]
0x18001a149  mov     ecx, eax
0x18001a14b  mov     r9d, 13CBh
0x18001a151  call    ElValidateWin32_8
0x18001a156  test    eax, eax
0x18001a158  mov     ebx, 1Fh
0x18001a15d  mov     rcx, rdi; hObject
0x18001a160  cmovz   eax, ebx
0x18001a163  mov     ebx, eax
0x18001a165  call    cs:__imp_CloseHandle
0x18001a16c  nop     dword ptr [rax+rax+00h]
0x18001a171  jmp     short loc_18001A176
0x18001a173  mov     [rsi], rdi
0x18001a176  mov     rsi, [rsp+48h+arg_8]
0x18001a17b  mov     eax, ebx
0x18001a17d  mov     rbx, [rsp+48h+arg_0]
0x18001a182  add     rsp, 40h
0x18001a186  pop     rdi
0x18001a187  retn
```
