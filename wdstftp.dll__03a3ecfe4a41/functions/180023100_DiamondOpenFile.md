# DiamondOpenFile

- ea: `0x180023100`
- end: `0x1800231ea`
- name: `DiamondOpenFile`
- size: `234`
- prototype: `INT_PTR __cdecl(LPSTR pszFile, int oflag, int pmode)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180022e24`
- `0x180023100`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800231b8`
- `KERNEL32!HeapFree` at `0x1800231b8`
- `KERNEL32!GetLastError` at `0x180023129`
- `KERNEL32!GetLastError` at `0x180023196`
- `KERNEL32!GetLastError` at `0x180023129`
- `KERNEL32!GetLastError` at `0x180023196`
- `KERNEL32!CreateFileW` at `0x180023181`
- `KERNEL32!CreateFileW` at `0x180023181`
- `KERNEL32!SetLastError` at `0x1800231c6`
- `KERNEL32!SetLastError` at `0x1800231c6`
- `KERNEL32!GetProcessHeap` at `0x1800231a4`
- `KERNEL32!GetProcessHeap` at `0x1800231a4`

## pseudocode

```c
INT_PTR __fastcall DiamondOpenFile(const CHAR *pszFile, unsigned int oflag, int pmode)
{
  DWORD LastError; // ebx
  __int64 FileW; // rsi
  WCHAR *v6; // rbp
  DWORD v7; // edx
  HANDLE ProcessHeap; // rax

  LastError = 0;
  FileW = -1;
  v6 = (WCHAR *)WimStrUnicode(pszFile);
  if ( v6 )
  {
    v7 = -1073741824;
    if ( (oflag & 2) == 0 )
      v7 = (oflag & 1) != 0 ? 0x40000000 : 0x80000000;
    FileW = (__int64)CreateFileW(v6, v7, 1u, 0, (((oflag >> 8) & 1) == 0) | 2u, 0x80u, 0);
    if ( FileW == -1 )
      LastError = GetLastError();
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
  }
  else
  {
    LastError = GetLastError();
  }
  SetLastError(LastError);
  return FileW;
}

```

## disassembly

```asm
0x180023100  mov     [rsp+arg_0], rbx
0x180023105  mov     [rsp+arg_8], rbp
0x18002310a  mov     [rsp+arg_10], rsi
0x18002310f  push    rdi
0x180023110  sub     rsp, 40h
0x180023114  mov     edi, edx
0x180023116  xor     ebx, ebx
0x180023118  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002311c  call    WimStrUnicode
0x180023121  mov     rbp, rax
0x180023124  test    rax, rax
0x180023127  jnz     short loc_18002313C
0x180023129  call    cs:__imp_GetLastError
0x180023130  nop     dword ptr [rax+rax+00h]
0x180023135  mov     ebx, eax
0x180023137  jmp     loc_1800231C4
0x18002313c  mov     r8d, 1; dwShareMode
0x180023142  mov     edx, 0C0000000h
0x180023147  test    dil, 2
0x18002314b  jnz     short loc_18002315F
0x18002314d  mov     al, dil
0x180023150  and     al, r8b
0x180023153  neg     al
0x180023155  sbb     ecx, ecx
0x180023157  and     edx, ecx
0x180023159  add     edx, 80000000h; dwDesiredAccess
0x18002315f  shr     edi, 8
0x180023162  xor     r9d, r9d; lpSecurityAttributes
0x180023165  not     edi
0x180023167  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x18002316c  and     edi, r8d
0x18002316f  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180023177  or      edi, 2
0x18002317a  mov     rcx, rbp; lpFileName
0x18002317d  mov     [rsp+48h+dwCreationDisposition], edi; dwCreationDisposition
0x180023181  call    cs:__imp_CreateFileW
0x180023188  nop     dword ptr [rax+rax+00h]
0x18002318d  mov     rsi, rax
0x180023190  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180023194  jnz     short loc_1800231A4
0x180023196  call    cs:__imp_GetLastError
0x18002319d  nop     dword ptr [rax+rax+00h]
0x1800231a2  mov     ebx, eax
0x1800231a4  call    cs:__imp_GetProcessHeap
0x1800231ab  nop     dword ptr [rax+rax+00h]
0x1800231b0  mov     r8, rbp; lpMem
0x1800231b3  xor     edx, edx; dwFlags
0x1800231b5  mov     rcx, rax; hHeap
0x1800231b8  call    cs:__imp_HeapFree
0x1800231bf  nop     dword ptr [rax+rax+00h]
0x1800231c4  mov     ecx, ebx; dwErrCode
0x1800231c6  call    cs:__imp_SetLastError
0x1800231cd  nop     dword ptr [rax+rax+00h]
0x1800231d2  mov     rbx, [rsp+48h+arg_0]
0x1800231d7  mov     rax, rsi
0x1800231da  mov     rsi, [rsp+48h+arg_10]
0x1800231df  mov     rbp, [rsp+48h+arg_8]
0x1800231e4  add     rsp, 40h
0x1800231e8  pop     rdi
0x1800231e9  retn
```
