# ArgPrintEx(ulong *,ushort const *)

- ea: `0x14003d254`
- end: `0x14003d4e9`
- name: `?ArgPrintEx@@YAJPEAKPEBG@Z`
- size: `661`
- prototype: `__int64 __fastcall(unsigned int *, const unsigned __int16 *)`
- caller_count: `10`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14002ec00`
- `0x14003c420`
- `0x14003c54c`
- `0x14003c780`
- `0x14003c974`
- `0x14003cb00`
- `0x14003d124`
- `0x14003d574`
- `0x14003d930`
- `0x14003e014`

## callees

- `0x14003d254`
- `0x14003d828`
- `0x14003e334`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003d4af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003d4af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003d39c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003d4a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003d39c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003d4a1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14003d3aa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14003d3aa`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x14003d3ef`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x14003d3ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d30a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d33b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d3f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d47c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d4be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d30a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d33b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d3f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d47c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d4be`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14003d46e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14003d46e`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x14003d281`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x14003d281`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x14003d2fc`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x14003d2fc`

## pseudocode

```c
__int64 __fastcall ArgPrintEx(unsigned int *a1, const unsigned __int16 *a2)
{
  char *StdHandle; // rbp
  signed int v5; // ebx
  DWORD v6; // ebx
  DWORD v7; // r8d
  signed int v8; // eax
  bool v9; // sf
  signed int LastError; // eax
  bool v11; // cc
  unsigned __int64 v12; // rcx
  __int64 cbMultiByte; // rdi
  HANDLE ProcessHeap; // rax
  CHAR *v15; // rax
  CHAR *v16; // r14
  signed int v17; // eax
  __int64 v18; // rcx
  CHAR *i; // rax
  unsigned __int64 v20; // rdi
  signed int v21; // eax
  HANDLE v22; // rax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-28h] BYREF
  __int64 nNumberOfCharsToWrite; // [rsp+80h] [rbp+18h] BYREF
  DWORD NumberOfCharsWritten; // [rsp+88h] [rbp+20h] BYREF

  LODWORD(nNumberOfCharsToWrite) = 0;
  NumberOfBytesWritten = 0;
  StdHandle = (char *)GetStdHandle(0xFFFFFFF5);
  if ( (unsigned __int64)(StdHandle - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    v5 = LastError;
    v11 = LastError <= 0;
LABEL_45:
    if ( !v11 )
      return (unsigned __int16)LastError | 0x80070000;
    return (unsigned int)v5;
  }
  v5 = ArgStringLength(a2, a1, (unsigned int *)&nNumberOfCharsToWrite);
  if ( v5 < 0 )
    return (unsigned int)v5;
  if ( !(unsigned int)ArgIsConsole(StdHandle) )
  {
    v12 = (unsigned int)nNumberOfCharsToWrite + 1LL;
    if ( v12 < (unsigned int)nNumberOfCharsToWrite )
      return (unsigned int)-2147024362;
    nNumberOfCharsToWrite = 0;
    cbMultiByte = 2 * v12;
    if ( !is_mul_ok(v12, 2u) || 2 * v12 > 0x7FFFFFFF )
      return (unsigned int)-2147024362;
    ProcessHeap = GetProcessHeap();
    v15 = (CHAR *)HeapAlloc(ProcessHeap, 0, cbMultiByte);
    v16 = v15;
    if ( !v15 )
      return (unsigned int)-2147024882;
    *v15 = 0;
    if ( WideCharToMultiByte(1u, 0, a2, -1, v15, cbMultiByte, "_", 0) <= 0 )
    {
      v17 = GetLastError();
      v5 = v17;
      if ( !v17 )
        goto LABEL_40;
      if ( v17 > 0 )
        v5 = (unsigned __int16)v17 | 0x80070000;
      if ( v5 < 0 )
        goto LABEL_42;
    }
    v18 = cbMultiByte;
    for ( i = v16; v18; --v18 )
    {
      if ( !*i )
        break;
      ++i;
    }
    v5 = v18 == 0 ? 0x80070057 : 0;
    if ( !v18 )
      goto LABEL_42;
    v20 = cbMultiByte - v18;
    if ( v20 > 0xFFFFFFFF )
    {
      v5 = -2147024362;
      goto LABEL_42;
    }
    if ( WriteFile(StdHandle, v16, v20, &NumberOfBytesWritten, 0) )
    {
      v5 = 0;
LABEL_42:
      v22 = GetProcessHeap();
      HeapFree(v22, 0, v16);
      return (unsigned int)v5;
    }
    v21 = GetLastError();
    v5 = v21;
    if ( v21 )
    {
      if ( v21 > 0 )
        v5 = (unsigned __int16)v21 | 0x80070000;
      goto LABEL_42;
    }
LABEL_40:
    v5 = -2147467259;
    goto LABEL_42;
  }
  v6 = nNumberOfCharsToWrite;
  for ( NumberOfCharsWritten = 0; ; a2 += NumberOfCharsWritten )
  {
    v7 = 0x2000;
    if ( v6 < 0x2000 )
      v7 = v6;
    if ( WriteConsoleW(StdHandle, a2, v7, &NumberOfCharsWritten, 0) )
    {
      v8 = 0;
    }
    else
    {
      v8 = GetLastError();
      v9 = v8 < 0;
      if ( !v8 )
        return 0;
      if ( v8 > 0 )
      {
        v8 = (unsigned __int16)v8 | 0x80070000;
        v9 = v8 < 0;
      }
      if ( v9 )
        return 0;
    }
    if ( NumberOfCharsWritten > v6 )
      break;
    v6 -= NumberOfCharsWritten;
    if ( !v6 )
      break;
  }
  if ( v8 )
    return 0;
  LastError = GetLastError();
  v5 = LastError;
  v11 = LastError <= 0;
  if ( LastError )
    goto LABEL_45;
  return (unsigned int)-2147467259;
}

```

## disassembly

```asm
0x14003d254  mov     rax, rsp
0x14003d257  mov     [rax+8], rbx
0x14003d25b  mov     [rax+10h], rbp
0x14003d25f  push    rdi
0x14003d260  push    r14
0x14003d262  push    r15
0x14003d264  sub     rsp, 50h
0x14003d268  mov     rbx, rcx
0x14003d26b  mov     dword ptr [rax+18h], 0
0x14003d272  mov     ecx, 0FFFFFFF5h; nStdHandle
0x14003d277  mov     dword ptr [rax-28h], 0
0x14003d27e  mov     r15, rdx
0x14003d281  call    cs:__imp_GetStdHandle
0x14003d287  mov     rbp, rax
0x14003d28a  lea     r8, [rax-1]
0x14003d28e  cmp     r8, 0FFFFFFFFFFFFFFFDh
0x14003d292  ja      loc_14003D4BE
0x14003d298  lea     r8, [rsp+68h+nNumberOfCharsToWrite]; unsigned int *
0x14003d2a0  mov     rdx, rbx; unsigned int *
0x14003d2a3  mov     rcx, r15; unsigned __int16 *
0x14003d2a6  call    ?ArgStringLength@@YAJPEBGPEAK1@Z; ArgStringLength(ushort const *,ulong *,ulong *)
0x14003d2ab  mov     ebx, eax
0x14003d2ad  test    eax, eax
0x14003d2af  js      loc_14003D4D3
0x14003d2b5  mov     rcx, rbp; hConsoleHandle
0x14003d2b8  call    ?ArgIsConsole@@YAHPEAX@Z; ArgIsConsole(void *)
0x14003d2bd  test    eax, eax
0x14003d2bf  jz      loc_14003D35C
0x14003d2c5  mov     ebx, dword ptr [rsp+68h+nNumberOfCharsToWrite]
0x14003d2cc  mov     edi, 2000h
0x14003d2d1  mov     [rsp+68h+NumberOfCharsWritten], 0
0x14003d2dc  mov     r8d, edi
0x14003d2df  mov     [rsp+68h+lpReserved], 0; lpReserved
0x14003d2e8  cmp     ebx, edi
0x14003d2ea  lea     r9, [rsp+68h+NumberOfCharsWritten]; lpNumberOfCharsWritten
0x14003d2f2  mov     rdx, r15; lpBuffer
0x14003d2f5  mov     rcx, rbp; hConsoleOutput
0x14003d2f8  cmovb   r8d, ebx; nNumberOfCharsToWrite
0x14003d2fc  call    cs:__imp_WriteConsoleW
0x14003d302  test    eax, eax
0x14003d304  jz      short loc_14003D30A
0x14003d306  xor     eax, eax
0x14003d308  jmp     short loc_14003D322
0x14003d30a  call    cs:__imp_GetLastError
0x14003d310  test    eax, eax
0x14003d312  jz      short loc_14003D355
0x14003d314  jle     short loc_14003D320
0x14003d316  movzx   eax, ax
0x14003d319  or      eax, 80070000h
0x14003d31e  test    eax, eax
0x14003d320  js      short loc_14003D355
0x14003d322  mov     ecx, [rsp+68h+NumberOfCharsWritten]
0x14003d329  cmp     ecx, ebx
0x14003d32b  ja      short loc_14003D337
0x14003d32d  sub     ebx, ecx
0x14003d32f  jz      short loc_14003D337
0x14003d331  lea     r15, [r15+rcx*2]
0x14003d335  jmp     short loc_14003D2DC
0x14003d337  test    eax, eax
0x14003d339  jnz     short loc_14003D355
0x14003d33b  call    cs:__imp_GetLastError
0x14003d341  mov     ebx, eax
0x14003d343  test    eax, eax
0x14003d345  jnz     loc_14003D4C8
0x14003d34b  mov     ebx, 80004005h
0x14003d350  jmp     loc_14003D4D3
0x14003d355  xor     ebx, ebx
0x14003d357  jmp     loc_14003D4D3
0x14003d35c  mov     eax, dword ptr [rsp+68h+nNumberOfCharsToWrite]
0x14003d363  lea     rcx, [rax+1]
0x14003d367  cmp     rcx, rax
0x14003d36a  jb      loc_14003D4B7
0x14003d370  mov     eax, 2
0x14003d375  mov     [rsp+68h+nNumberOfCharsToWrite], 0
0x14003d381  mul     rcx
0x14003d384  mov     rdi, rax
0x14003d387  test    rdx, rdx
0x14003d38a  jnz     loc_14003D4B7
0x14003d390  cmp     rax, 7FFFFFFFh
0x14003d396  ja      loc_14003D4B7
0x14003d39c  call    cs:__imp_GetProcessHeap
0x14003d3a2  mov     r8, rdi; dwBytes
0x14003d3a5  xor     edx, edx; dwFlags
0x14003d3a7  mov     rcx, rax; hHeap
0x14003d3aa  call    cs:__imp_HeapAlloc
0x14003d3b0  mov     r14, rax
0x14003d3b3  test    rax, rax
0x14003d3b6  jnz     short loc_14003D3C2
0x14003d3b8  mov     ebx, 8007000Eh
0x14003d3bd  jmp     loc_14003D4D3
0x14003d3c2  mov     [rsp+68h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x14003d3cb  xor     edx, edx; dwFlags
0x14003d3cd  mov     byte ptr [rax], 0
0x14003d3d0  or      r9d, 0FFFFFFFFh; cchWideChar
0x14003d3d4  lea     rax, DefaultChar; "_"
0x14003d3db  mov     r8, r15; lpWideCharStr
0x14003d3de  mov     [rsp+68h+lpDefaultChar], rax; lpDefaultChar
0x14003d3e3  lea     ecx, [rdx+1]; CodePage
0x14003d3e6  mov     [rsp+68h+cbMultiByte], edi; cbMultiByte
0x14003d3ea  mov     [rsp+68h+lpReserved], r14; lpMultiByteStr
0x14003d3ef  call    cs:__imp_WideCharToMultiByte
0x14003d3f5  test    eax, eax
0x14003d3f7  jg      short loc_14003D41C
0x14003d3f9  call    cs:__imp_GetLastError
0x14003d3ff  mov     ebx, eax
0x14003d401  test    eax, eax
0x14003d403  jz      loc_14003D495
0x14003d409  jle     short loc_14003D414
0x14003d40b  movzx   ebx, ax
0x14003d40e  or      ebx, 80070000h
0x14003d414  test    ebx, ebx
0x14003d416  js      loc_14003D4A1
0x14003d41c  mov     rcx, rdi
0x14003d41f  mov     rax, r14
0x14003d422  test    rdi, rdi
0x14003d425  jz      short loc_14003D435
0x14003d427  cmp     byte ptr [rax], 0
0x14003d42a  jz      short loc_14003D435
0x14003d42c  inc     rax
0x14003d42f  sub     rcx, 1
0x14003d433  jnz     short loc_14003D427
0x14003d435  mov     rax, rcx
0x14003d438  neg     rax
0x14003d43b  sbb     ebx, ebx
0x14003d43d  not     ebx
0x14003d43f  and     ebx, 80070057h
0x14003d445  test    rcx, rcx
0x14003d448  jz      short loc_14003D4A1
0x14003d44a  sub     rdi, rcx
0x14003d44d  mov     eax, 0FFFFFFFFh
0x14003d452  cmp     rdi, rax
0x14003d455  ja      short loc_14003D49C
0x14003d457  mov     r8d, edi; nNumberOfBytesToWrite
0x14003d45a  mov     [rsp+68h+lpReserved], 0; lpOverlapped
0x14003d463  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14003d468  mov     rdx, r14; lpBuffer
0x14003d46b  mov     rcx, rbp; hFile
0x14003d46e  call    cs:__imp_WriteFile
0x14003d474  test    eax, eax
0x14003d476  jz      short loc_14003D47C
0x14003d478  xor     ebx, ebx
0x14003d47a  jmp     short loc_14003D4A1
0x14003d47c  call    cs:__imp_GetLastError
0x14003d482  mov     ebx, eax
0x14003d484  test    eax, eax
0x14003d486  jz      short loc_14003D495
0x14003d488  jle     short loc_14003D4A1
0x14003d48a  movzx   ebx, ax
0x14003d48d  or      ebx, 80070000h
0x14003d493  jmp     short loc_14003D4A1
0x14003d495  mov     ebx, 80004005h
0x14003d49a  jmp     short loc_14003D4A1
0x14003d49c  mov     ebx, 80070216h
0x14003d4a1  call    cs:__imp_GetProcessHeap
0x14003d4a7  mov     r8, r14; lpMem
0x14003d4aa  xor     edx, edx; dwFlags
0x14003d4ac  mov     rcx, rax; hHeap
0x14003d4af  call    cs:__imp_HeapFree
0x14003d4b5  jmp     short loc_14003D4D3
0x14003d4b7  mov     ebx, 80070216h
0x14003d4bc  jmp     short loc_14003D4D3
0x14003d4be  call    cs:__imp_GetLastError
0x14003d4c4  mov     ebx, eax
0x14003d4c6  test    eax, eax
0x14003d4c8  jle     short loc_14003D4D3
0x14003d4ca  movzx   ebx, ax
0x14003d4cd  or      ebx, 80070000h
0x14003d4d3  mov     rbp, [rsp+68h+arg_8]
0x14003d4d8  mov     eax, ebx
0x14003d4da  mov     rbx, [rsp+68h+arg_0]
0x14003d4df  add     rsp, 50h
0x14003d4e3  pop     r15
0x14003d4e5  pop     r14
0x14003d4e7  pop     rdi
0x14003d4e8  retn
```
