# SafeCreateTempFile

- ea: `0x180008178`
- end: `0x1800084ca`
- name: `SafeCreateTempFile`
- size: `850`
- prototype: `__int64 __usercall@<rax>(LPCWCH lpWideCharStr@<rcx>, LPCVOID lpBuffer@<rdx>, LPCSTR lpPathName)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800084d0`
- `0x180008af0`

## callees

- `0x1800031f4`
- `0x180003200`
- `0x180008178`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800081f0`
- `KERNEL32!GetLastError` at `0x18000824f`
- `KERNEL32!GetLastError` at `0x1800082af`
- `KERNEL32!GetLastError` at `0x180008355`
- `KERNEL32!GetLastError` at `0x18000845b`
- `KERNEL32!GetLastError` at `0x1800081f0`
- `KERNEL32!GetLastError` at `0x18000824f`
- `KERNEL32!GetLastError` at `0x1800082af`
- `KERNEL32!GetLastError` at `0x180008355`
- `KERNEL32!GetLastError` at `0x18000845b`
- `KERNEL32!MultiByteToWideChar` at `0x180008413`
- `KERNEL32!MultiByteToWideChar` at `0x180008451`
- `KERNEL32!MultiByteToWideChar` at `0x180008413`
- `KERNEL32!MultiByteToWideChar` at `0x180008451`
- `KERNEL32!GetTempFileNameA` at `0x1800082a3`
- `KERNEL32!GetTempFileNameA` at `0x1800082a3`
- `KERNEL32!WideCharToMultiByte` at `0x1800081e4`
- `KERNEL32!WideCharToMultiByte` at `0x180008315`
- `KERNEL32!WideCharToMultiByte` at `0x1800081e4`
- `KERNEL32!WideCharToMultiByte` at `0x180008315`
- `KERNEL32!WriteFile` at `0x1800083a1`
- `KERNEL32!WriteFile` at `0x1800083c7`
- `KERNEL32!WriteFile` at `0x1800083a1`
- `KERNEL32!WriteFile` at `0x1800083c7`
- `KERNEL32!GetTempPath2A` at `0x180008212`
- `KERNEL32!GetTempPath2A` at `0x180008245`
- `KERNEL32!GetTempPath2A` at `0x180008212`
- `KERNEL32!GetTempPath2A` at `0x180008245`
- `KERNEL32!CreateFileA` at `0x180008343`
- `KERNEL32!CreateFileA` at `0x180008343`
- `KERNEL32!CloseHandle` at `0x1800084aa`
- `KERNEL32!CloseHandle` at `0x1800084aa`
- `KERNEL32!FlushFileBuffers` at `0x1800083d8`
- `KERNEL32!FlushFileBuffers` at `0x1800083d8`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180008428`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180008428`
- `OLEAUT32!__imp_SysFreeString` at `0x180008473`
- `OLEAUT32!__imp_SysFreeString` at `0x180008473`

## pseudocode

```c
__int64 __fastcall SafeCreateTempFile(LPCWCH lpWideCharStr, _WORD *lpBuffer, int a3, _QWORD *a4, CHAR *lpPathName)
{
  CHAR *v5; // r15
  void *v6; // rdi
  int v10; // ebp
  __int64 v11; // rbx
  signed int LastError; // eax
  unsigned int v13; // ebx
  int TempPath2A; // eax
  unsigned int v15; // r14d
  const CHAR *v16; // rax
  int v17; // eax
  signed int v18; // eax
  unsigned int v19; // r14d
  CHAR *v20; // rax
  CHAR *v21; // rbp
  signed int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rax
  HANDLE FileA; // rax
  signed int v26; // eax
  UINT v27; // eax
  int v28; // r14d
  WCHAR *v29; // rax
  OLECHAR *v30; // rsi
  signed int v31; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-48h] BYREF
  __int16 Buffer; // [rsp+90h] [rbp+8h] BYREF
  _QWORD *v35; // [rsp+A8h] [rbp+20h]

  v35 = a4;
  v5 = lpPathName;
  v6 = 0;
  NumberOfBytesWritten = 0;
  *a4 = 0;
  Buffer = -257;
  v10 = 0;
  if ( v5 )
    *(_QWORD *)v5 = 0;
  v11 = -1;
  if ( lpWideCharStr && (v10 = WideCharToMultiByte(0, 0, lpWideCharStr, -1, 0, 0, 0, 0)) == 0
    || (TempPath2A = GetTempPath2A(0, 0)) == 0 )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return v13;
  }
  v15 = TempPath2A + 1;
  v16 = (const CHAR *)operator new((unsigned int)(TempPath2A + 1));
  lpPathName = (CHAR *)v16;
  if ( !v16 )
    return (unsigned int)-2147024882;
  v17 = GetTempPath2A(v15, v16);
  if ( !v17 )
  {
    v18 = GetLastError();
    v13 = v18;
    if ( v18 > 0 )
      v13 = (unsigned __int16)v18 | 0x80070000;
    goto LABEL_47;
  }
  v19 = v10 + v17 + 16;
  v20 = (CHAR *)operator new(v19);
  v21 = v20;
  if ( !v20 )
  {
    v13 = -2147024882;
    goto LABEL_47;
  }
  if ( !GetTempFileNameA(lpPathName, "wsh", 0, v20) )
    goto LABEL_16;
  if ( lpWideCharStr )
  {
    v23 = -1;
    do
      ++v23;
    while ( v21[v23] );
    if ( *lpWideCharStr != 46 )
    {
      v24 = (unsigned int)v23;
      LODWORD(v23) = v23 + 1;
      v21[v24] = 46;
    }
    if ( !WideCharToMultiByte(0, 0, lpWideCharStr, -1, &v21[(unsigned int)v23], v19 - v23, 0, 0) )
      goto LABEL_16;
  }
  FileA = CreateFileA(v21, 0xC0000000, 0, 0, 2u, 0x4002100u, 0);
  if ( FileA != (HANDLE)-1LL )
    v6 = FileA;
  if ( !v6 )
  {
    v26 = GetLastError();
    v13 = v26;
    if ( v26 > 0 )
      v13 = (unsigned __int16)v26 | 0x80070000;
    v6 = 0;
    goto LABEL_46;
  }
  if ( a3 > 0
    && (*lpBuffer != Buffer && !WriteFile(v6, &Buffer, 2u, &NumberOfBytesWritten, 0)
     || !WriteFile(v6, lpBuffer, 2 * a3, &NumberOfBytesWritten, 0)
     || !FlushFileBuffers(v6)) )
  {
    goto LABEL_16;
  }
  if ( !v5 )
  {
LABEL_45:
    *v35 = v6;
    v6 = 0;
    v13 = 0;
    goto LABEL_46;
  }
  do
    ++v11;
  while ( v21[v11] );
  v27 = MultiByteToWideChar(0, 0, v21, v11, 0, 0);
  v28 = v27;
  if ( !v27 )
  {
LABEL_16:
    v22 = GetLastError();
    v13 = v22;
    if ( v22 > 0 )
      v13 = (unsigned __int16)v22 | 0x80070000;
    goto LABEL_46;
  }
  v29 = SysAllocStringLen(0, v27);
  v30 = v29;
  if ( v29 )
  {
    if ( !MultiByteToWideChar(0, 0, v21, v11, v29, v28) )
    {
      v31 = GetLastError();
      v13 = v31;
      if ( v31 > 0 )
        v13 = (unsigned __int16)v31 | 0x80070000;
      SysFreeString(v30);
      goto LABEL_46;
    }
    *(_QWORD *)v5 = v30;
    goto LABEL_45;
  }
  v13 = -2147024882;
LABEL_46:
  operator delete(v21);
LABEL_47:
  operator delete(lpPathName);
  if ( v6 )
    CloseHandle(v6);
  return v13;
}

```

## disassembly

```asm
0x180008178  mov     rax, rsp
0x18000817b  mov     [rax+10h], rbx
0x18000817f  mov     [rax+20h], r9
0x180008183  push    rbp
0x180008184  push    rsi
0x180008185  push    rdi
0x180008186  push    r12
0x180008188  push    r13
0x18000818a  push    r14
0x18000818c  push    r15
0x18000818e  sub     rsp, 50h
0x180008192  mov     r15, [rsp+88h+lpPathName]
0x18000819a  xor     edi, edi
0x18000819c  mov     [rax-48h], edi
0x18000819f  mov     rsi, rcx
0x1800081a2  mov     [r9], rdi
0x1800081a5  mov     ecx, 0FEFFh
0x1800081aa  mov     [rax+8], cx
0x1800081ae  mov     r12d, r8d
0x1800081b1  mov     r13, rdx
0x1800081b4  mov     ebp, edi
0x1800081b6  test    r15, r15
0x1800081b9  jz      short loc_1800081BE
0x1800081bb  mov     [r15], rdi
0x1800081be  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800081c2  test    rsi, rsi
0x1800081c5  jz      short loc_18000820E
0x1800081c7  mov     [rsp+88h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x1800081cc  mov     r9d, ebx; cchWideChar
0x1800081cf  mov     [rsp+88h+lpDefaultChar], rdi; lpDefaultChar
0x1800081d4  mov     r8, rsi; lpWideCharStr
0x1800081d7  mov     [rsp+88h+cbMultiByte], edi; cbMultiByte
0x1800081db  xor     edx, edx; dwFlags
0x1800081dd  xor     ecx, ecx; CodePage
0x1800081df  mov     [rsp+88h+lpMultiByteStr], rdi; lpMultiByteStr
0x1800081e4  call    cs:__imp_WideCharToMultiByte
0x1800081ea  mov     ebp, eax
0x1800081ec  test    eax, eax
0x1800081ee  jnz     short loc_18000820E
0x1800081f0  call    cs:__imp_GetLastError
0x1800081f6  mov     ebx, eax
0x1800081f8  test    eax, eax
0x1800081fa  jle     loc_1800084B0
0x180008200  movzx   ebx, ax
0x180008203  or      ebx, 80070000h
0x180008209  jmp     loc_1800084B0
0x18000820e  xor     edx, edx
0x180008210  xor     ecx, ecx
0x180008212  call    cs:__imp_GetTempPath2A
0x180008218  test    eax, eax
0x18000821a  jz      short loc_1800081F0
0x18000821c  lea     r14d, [rax+1]
0x180008220  mov     ecx, r14d; Size
0x180008223  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008228  mov     [rsp+88h+lpPathName], rax
0x180008230  test    rax, rax
0x180008233  jnz     short loc_18000823F
0x180008235  mov     ebx, 8007000Eh
0x18000823a  jmp     loc_1800084B0
0x18000823f  mov     rdx, rax
0x180008242  mov     ecx, r14d
0x180008245  call    cs:__imp_GetTempPath2A
0x18000824b  test    eax, eax
0x18000824d  jnz     short loc_18000826D
0x18000824f  call    cs:__imp_GetLastError
0x180008255  mov     ebx, eax
0x180008257  test    eax, eax
0x180008259  jle     loc_180008495
0x18000825f  movzx   ebx, ax
0x180008262  or      ebx, 80070000h
0x180008268  jmp     loc_180008495
0x18000826d  lea     r14d, [rax+10h]
0x180008271  add     r14d, ebp
0x180008274  mov     ecx, r14d; Size
0x180008277  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000827c  mov     rbp, rax
0x18000827f  test    rax, rax
0x180008282  jnz     short loc_18000828E
0x180008284  mov     ebx, 8007000Eh
0x180008289  jmp     loc_180008495
0x18000828e  mov     rcx, [rsp+88h+lpPathName]; lpPathName
0x180008296  lea     rdx, PrefixString; "wsh"
0x18000829d  mov     r9, rbp; lpTempFileName
0x1800082a0  xor     r8d, r8d; uUnique
0x1800082a3  call    cs:__imp_GetTempFileNameA
0x1800082a9  xor     edx, edx; dwFlags
0x1800082ab  test    eax, eax
0x1800082ad  jnz     short loc_1800082CD
0x1800082af  call    cs:__imp_GetLastError
0x1800082b5  mov     ebx, eax
0x1800082b7  test    eax, eax
0x1800082b9  jle     loc_18000848D
0x1800082bf  movzx   ebx, ax
0x1800082c2  or      ebx, 80070000h
0x1800082c8  jmp     loc_18000848D
0x1800082cd  test    rsi, rsi
0x1800082d0  jz      short loc_18000831F
0x1800082d2  mov     rcx, rbx
0x1800082d5  inc     rcx
0x1800082d8  cmp     [rcx+rbp], dl
0x1800082db  jnz     short loc_1800082D5
0x1800082dd  mov     r8d, 2Eh ; '.'
0x1800082e3  cmp     r8w, [rsi]
0x1800082e7  jz      short loc_1800082F1
0x1800082e9  mov     eax, ecx
0x1800082eb  inc     ecx
0x1800082ed  mov     [rax+rbp], r8b
0x1800082f1  mov     [rsp+88h+lpUsedDefaultChar], rdx; lpUsedDefaultChar
0x1800082f6  sub     r14d, ecx
0x1800082f9  mov     eax, ecx
0x1800082fb  mov     r9d, ebx; cchWideChar
0x1800082fe  mov     [rsp+88h+lpDefaultChar], rdx; lpDefaultChar
0x180008303  add     rax, rbp
0x180008306  mov     [rsp+88h+cbMultiByte], r14d; cbMultiByte
0x18000830b  mov     r8, rsi; lpWideCharStr
0x18000830e  xor     ecx, ecx; CodePage
0x180008310  mov     [rsp+88h+lpMultiByteStr], rax; lpMultiByteStr
0x180008315  call    cs:__imp_WideCharToMultiByte
0x18000831b  test    eax, eax
0x18000831d  jz      short loc_1800082AF
0x18000831f  mov     [rsp+88h+lpDefaultChar], rdi; hTemplateFile
0x180008324  mov     esi, 2
0x180008329  mov     [rsp+88h+cbMultiByte], 4002100h; dwFlagsAndAttributes
0x180008331  xor     r9d, r9d; lpSecurityAttributes
0x180008334  xor     r8d, r8d; dwShareMode
0x180008337  mov     dword ptr [rsp+88h+lpMultiByteStr], esi; dwCreationDisposition
0x18000833b  mov     edx, 0C0000000h; dwDesiredAccess
0x180008340  mov     rcx, rbp; lpFileName
0x180008343  call    cs:__imp_CreateFileA
0x180008349  cmp     rax, rbx
0x18000834c  cmovnz  rdi, rax
0x180008350  test    rdi, rdi
0x180008353  jnz     short loc_180008371
0x180008355  call    cs:__imp_GetLastError
0x18000835b  mov     ebx, eax
0x18000835d  test    eax, eax
0x18000835f  jle     short loc_18000836A
0x180008361  movzx   ebx, ax
0x180008364  or      ebx, 80070000h
0x18000836a  xor     edi, edi
0x18000836c  jmp     loc_18000848D
0x180008371  test    r12d, r12d
0x180008374  jle     short loc_1800083E6
0x180008376  movzx   eax, [rsp+88h+Buffer]
0x18000837e  cmp     [r13+0], ax
0x180008383  jz      short loc_1800083AF
0x180008385  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000838a  mov     [rsp+88h+lpMultiByteStr], 0; lpOverlapped
0x180008393  mov     r8d, esi; nNumberOfBytesToWrite
0x180008396  lea     rdx, [rsp+88h+Buffer]; lpBuffer
0x18000839e  mov     rcx, rdi; hFile
0x1800083a1  call    cs:__imp_WriteFile
0x1800083a7  test    eax, eax
0x1800083a9  jz      loc_1800082AF
0x1800083af  lea     r8d, [r12+r12]; nNumberOfBytesToWrite
0x1800083b3  mov     [rsp+88h+lpMultiByteStr], 0; lpOverlapped
0x1800083bc  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800083c1  mov     rdx, r13; lpBuffer
0x1800083c4  mov     rcx, rdi; hFile
0x1800083c7  call    cs:__imp_WriteFile
0x1800083cd  test    eax, eax
0x1800083cf  jz      loc_1800082AF
0x1800083d5  mov     rcx, rdi; hFile
0x1800083d8  call    cs:__imp_FlushFileBuffers
0x1800083de  test    eax, eax
0x1800083e0  jz      loc_1800082AF
0x1800083e6  test    r15, r15
0x1800083e9  jz      loc_18000847E
0x1800083ef  inc     rbx
0x1800083f2  cmp     byte ptr [rbx+rbp], 0
0x1800083f6  jnz     short loc_1800083EF
0x1800083f8  mov     [rsp+88h+cbMultiByte], 0; cchWideChar
0x180008400  mov     r9d, ebx; cbMultiByte
0x180008403  mov     r8, rbp; lpMultiByteStr
0x180008406  mov     [rsp+88h+lpMultiByteStr], 0; lpWideCharStr
0x18000840f  xor     edx, edx; dwFlags
0x180008411  xor     ecx, ecx; CodePage
0x180008413  call    cs:__imp_MultiByteToWideChar
0x180008419  mov     r14d, eax
0x18000841c  test    eax, eax
0x18000841e  jz      loc_1800082AF
0x180008424  mov     edx, eax; ui
0x180008426  xor     ecx, ecx; strIn
0x180008428  call    cs:__imp_SysAllocStringLen
0x18000842e  mov     rsi, rax
0x180008431  test    rax, rax
0x180008434  jnz     short loc_18000843D
0x180008436  mov     ebx, 8007000Eh
0x18000843b  jmp     short loc_18000848D
0x18000843d  mov     [rsp+88h+cbMultiByte], r14d; cchWideChar
0x180008442  mov     r9d, ebx; cbMultiByte
0x180008445  mov     r8, rbp; lpMultiByteStr
0x180008448  mov     [rsp+88h+lpMultiByteStr], rsi; lpWideCharStr
0x18000844d  xor     edx, edx; dwFlags
0x18000844f  xor     ecx, ecx; CodePage
0x180008451  call    cs:__imp_MultiByteToWideChar
0x180008457  test    eax, eax
0x180008459  jnz     short loc_18000847B
0x18000845b  call    cs:__imp_GetLastError
0x180008461  mov     ebx, eax
0x180008463  test    eax, eax
0x180008465  jle     short loc_180008470
0x180008467  movzx   ebx, ax
0x18000846a  or      ebx, 80070000h
0x180008470  mov     rcx, rsi; bstrString
0x180008473  call    cs:__imp_SysFreeString
0x180008479  jmp     short loc_18000848D
0x18000847b  mov     [r15], rsi
0x18000847e  mov     rax, [rsp+88h+arg_18]
0x180008486  mov     [rax], rdi
0x180008489  xor     edi, edi
0x18000848b  xor     ebx, ebx
0x18000848d  mov     rcx, rbp; Block
0x180008490  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008495  mov     rcx, [rsp+88h+lpPathName]; Block
0x18000849d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800084a2  test    rdi, rdi
0x1800084a5  jz      short loc_1800084B0
0x1800084a7  mov     rcx, rdi; hObject
0x1800084aa  call    cs:__imp_CloseHandle
0x1800084b0  mov     eax, ebx
0x1800084b2  mov     rbx, [rsp+88h+arg_8]
0x1800084ba  add     rsp, 50h
0x1800084be  pop     r15
0x1800084c0  pop     r14
0x1800084c2  pop     r13
0x1800084c4  pop     r12
0x1800084c6  pop     rdi
0x1800084c7  pop     rsi
0x1800084c8  pop     rbp
0x1800084c9  retn
```
