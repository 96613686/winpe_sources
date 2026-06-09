# lafe_readpassphrase

- ea: `0x1400074d0`
- end: `0x14000761a`
- name: `lafe_readpassphrase`
- size: `330`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1400050a0`

## callees

- `0x1400071a4`
- `0x1400074d0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x1400075d3`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x1400075d3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400075e2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007600`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400075e2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007600`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14000756f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400075bb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14000756f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400075bb`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x140007593`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x140007593`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x1400074fe`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x140007519`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x1400074fe`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x140007519`
- `api-ms-win-core-console-l1-1-0!GetConsoleMode` at `0x140007530`
- `api-ms-win-core-console-l1-1-0!GetConsoleMode` at `0x140007530`
- `api-ms-win-core-console-l1-1-0!SetConsoleMode` at `0x14000754b`
- `api-ms-win-core-console-l1-1-0!SetConsoleMode` at `0x14000754b`

## string_xrefs

- `0x140007606`: `Couldn't read passphrase`

## pseudocode

```c
char *__fastcall lafe_readpassphrase(__int64 a1, char *a2, __int64 a3)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  HANDLE StdHandle; // rdi
  __int64 v7; // r8
  HANDLE v8; // rsi
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp+8h] BYREF
  int v14; // [rsp+44h] [rbp+Ch]
  DWORD Mode; // [rsp+50h] [rbp+18h] BYREF
  int v16; // [rsp+54h] [rbp+1Ch]

  v16 = HIDWORD(a3);
  v14 = HIDWORD(a1);
  Mode = 0;
  NumberOfBytesRead = 0;
  StdHandle = GetStdHandle(0xFFFFFFF6);
  if ( StdHandle != (HANDLE)-1LL
    && (v8 = GetStdHandle(0xFFFFFFF5), v8 != (HANDLE)-1LL)
    && GetConsoleMode(StdHandle, &Mode)
    && (Mode = Mode & 0xFFFFFFF8 | 3, SetConsoleMode(StdHandle, Mode))
    && WriteFile(v8, "Enter passphrase:", 0x11u, 0, 0)
    && ReadFile(StdHandle, a2, 0x3FFu, &NumberOfBytesRead, 0) )
  {
    WriteFile(v8, "\r\n", 2u, 0, 0);
    a2[NumberOfBytesRead] = 0;
    a2[strcspn(a2, "\r\n")] = 0;
    if ( a2 )
      return a2;
  }
  else
  {
    a2 = 0;
  }
  if ( *(_DWORD *)_o__errno(v5, v4, v7) != 4 )
  {
    _o__errno(v10, v9, v11);
    lafe_errc(1);
  }
  return a2;
}

```

## disassembly

```asm
0x1400074d0  mov     rax, rsp
0x1400074d3  mov     [rax+10h], rbx
0x1400074d7  mov     [rax+20h], rsi
0x1400074db  mov     [rax+18h], r8
0x1400074df  mov     [rax+8], rcx
0x1400074e3  push    rdi
0x1400074e4  sub     rsp, 30h
0x1400074e8  mov     ecx, 0FFFFFFF6h; nStdHandle
0x1400074ed  mov     dword ptr [rax+18h], 0
0x1400074f4  mov     rbx, rdx
0x1400074f7  mov     dword ptr [rax+8], 0
0x1400074fe  call    cs:__imp_GetStdHandle
0x140007504  mov     rdi, rax
0x140007507  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000750b  jnz     short loc_140007514
0x14000750d  xor     ebx, ebx
0x14000750f  jmp     loc_1400075E2
0x140007514  mov     ecx, 0FFFFFFF5h; nStdHandle
0x140007519  call    cs:__imp_GetStdHandle
0x14000751f  mov     rsi, rax
0x140007522  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140007526  jz      short loc_14000750D
0x140007528  lea     rdx, [rsp+38h+Mode]; lpMode
0x14000752d  mov     rcx, rdi; hConsoleHandle
0x140007530  call    cs:__imp_GetConsoleMode
0x140007536  test    eax, eax
0x140007538  jz      short loc_14000750D
0x14000753a  mov     edx, [rsp+38h+Mode]
0x14000753e  mov     rcx, rdi; hConsoleHandle
0x140007541  and     edx, 0FFFFFFFBh
0x140007544  or      edx, 3; dwMode
0x140007547  mov     [rsp+38h+Mode], edx
0x14000754b  call    cs:__imp_SetConsoleMode
0x140007551  test    eax, eax
0x140007553  jz      short loc_14000750D
0x140007555  xor     r9d, r9d; lpNumberOfBytesWritten
0x140007558  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x140007561  lea     rdx, aEnterPassphras; "Enter passphrase:"
0x140007568  mov     rcx, rsi; hFile
0x14000756b  lea     r8d, [r9+11h]; nNumberOfBytesToWrite
0x14000756f  call    cs:__imp_WriteFile
0x140007575  test    eax, eax
0x140007577  jz      short loc_14000750D
0x140007579  lea     r9, [rsp+38h+NumberOfBytesRead]; lpNumberOfBytesRead
0x14000757e  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x140007587  mov     r8d, 3FFh; nNumberOfBytesToRead
0x14000758d  mov     rdx, rbx; lpBuffer
0x140007590  mov     rcx, rdi; hFile
0x140007593  call    cs:__imp_ReadFile
0x140007599  test    eax, eax
0x14000759b  jz      loc_14000750D
0x1400075a1  xor     r9d, r9d; lpNumberOfBytesWritten
0x1400075a4  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x1400075ad  lea     rdx, Control; "\r\n"
0x1400075b4  mov     rcx, rsi; hFile
0x1400075b7  lea     r8d, [r9+2]; nNumberOfBytesToWrite
0x1400075bb  call    cs:__imp_WriteFile
0x1400075c1  mov     eax, [rsp+38h+NumberOfBytesRead]
0x1400075c5  lea     rdx, Control; "\r\n"
0x1400075cc  mov     rcx, rbx; Str
0x1400075cf  mov     byte ptr [rax+rbx], 0
0x1400075d3  call    cs:__imp_strcspn
0x1400075d9  mov     byte ptr [rax+rbx], 0
0x1400075dd  test    rbx, rbx
0x1400075e0  jnz     short loc_1400075ED
0x1400075e2  call    cs:__imp__o__errno
0x1400075e8  cmp     dword ptr [rax], 4
0x1400075eb  jnz     short loc_140007600
0x1400075ed  mov     rsi, [rsp+38h+arg_18]
0x1400075f2  mov     rax, rbx
0x1400075f5  mov     rbx, [rsp+38h+arg_8]
0x1400075fa  add     rsp, 30h
0x1400075fe  pop     rdi
0x1400075ff  retn
0x140007600  call    cs:__imp__o__errno
0x140007606  lea     r8, aCouldnTReadPas; "Couldn't read passphrase"
0x14000760d  mov     ecx, 1; Code
0x140007612  mov     edx, [rax]
0x140007614  call    lafe_errc
```
