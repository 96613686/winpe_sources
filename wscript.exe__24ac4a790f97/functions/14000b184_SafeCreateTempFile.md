# SafeCreateTempFile

- ea: `0x14000b184`
- end: `0x14000b4c2`
- name: `SafeCreateTempFile`
- size: `830`
- prototype: `__int64 __usercall@<rax>(LPCWCH lpWideCharStr@<rcx>, LPCVOID lpBuffer@<rdx>, LPCSTR lpPathName)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14000b5d0`
- `0x14000b8c8`

## callees

- `0x140001008`
- `0x140001048`
- `0x14000b184`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x14000b420`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x14000b420`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b46b`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b46b`
- `KERNEL32!GetLastError` at `0x14000b1fc`
- `KERNEL32!GetLastError` at `0x14000b25b`
- `KERNEL32!GetLastError` at `0x14000b2bb`
- `KERNEL32!GetLastError` at `0x14000b34d`
- `KERNEL32!GetLastError` at `0x14000b453`
- `KERNEL32!GetLastError` at `0x14000b1fc`
- `KERNEL32!GetLastError` at `0x14000b25b`
- `KERNEL32!GetLastError` at `0x14000b2bb`
- `KERNEL32!GetLastError` at `0x14000b34d`
- `KERNEL32!GetLastError` at `0x14000b453`
- `KERNEL32!CloseHandle` at `0x14000b4a2`
- `KERNEL32!CloseHandle` at `0x14000b4a2`
- `KERNEL32!MultiByteToWideChar` at `0x14000b40b`
- `KERNEL32!MultiByteToWideChar` at `0x14000b449`
- `KERNEL32!MultiByteToWideChar` at `0x14000b40b`
- `KERNEL32!MultiByteToWideChar` at `0x14000b449`
- `KERNEL32!FlushFileBuffers` at `0x14000b3d0`
- `KERNEL32!FlushFileBuffers` at `0x14000b3d0`
- `KERNEL32!GetTempFileNameA` at `0x14000b2af`
- `KERNEL32!GetTempFileNameA` at `0x14000b2af`
- `KERNEL32!WideCharToMultiByte` at `0x14000b1f0`
- `KERNEL32!WideCharToMultiByte` at `0x14000b30d`
- `KERNEL32!WideCharToMultiByte` at `0x14000b1f0`
- `KERNEL32!WideCharToMultiByte` at `0x14000b30d`
- `KERNEL32!CreateFileA` at `0x14000b33b`
- `KERNEL32!CreateFileA` at `0x14000b33b`
- `KERNEL32!GetTempPath2A` at `0x14000b21e`
- `KERNEL32!GetTempPath2A` at `0x14000b251`
- `KERNEL32!GetTempPath2A` at `0x14000b21e`
- `KERNEL32!GetTempPath2A` at `0x14000b251`
- `KERNEL32!WriteFile` at `0x14000b399`
- `KERNEL32!WriteFile` at `0x14000b3bf`
- `KERNEL32!WriteFile` at `0x14000b399`
- `KERNEL32!WriteFile` at `0x14000b3bf`

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
  __int64 v23; // rax
  HANDLE FileA; // rax
  signed int v25; // eax
  UINT v26; // eax
  int v27; // r14d
  WCHAR *v28; // rax
  OLECHAR *v29; // rsi
  signed int v30; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-48h] BYREF
  __int16 Buffer; // [rsp+90h] [rbp+8h] BYREF
  _QWORD *v34; // [rsp+A8h] [rbp+20h]

  v34 = a4;
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
    goto LABEL_45;
  }
  v19 = v10 + v17 + 15;
  v20 = (CHAR *)operator new(v19);
  v21 = v20;
  if ( !v20 )
  {
    v13 = -2147024882;
    goto LABEL_45;
  }
  if ( !GetTempFileNameA(lpPathName, "wsh", 0, v20) )
    goto LABEL_16;
  if ( lpWideCharStr )
  {
    v23 = -1;
    do
      ++v23;
    while ( v21[v23] );
    if ( !WideCharToMultiByte(0, 0, lpWideCharStr, -1, &v21[(unsigned int)v23], v19 - v23, 0, 0) )
      goto LABEL_16;
  }
  FileA = CreateFileA(v21, 0xC0000000, 0, 0, 2u, 0x4002100u, 0);
  if ( FileA != (HANDLE)-1LL )
    v6 = FileA;
  if ( !v6 )
  {
    v25 = GetLastError();
    v13 = v25;
    if ( v25 > 0 )
      v13 = (unsigned __int16)v25 | 0x80070000;
    v6 = 0;
    goto LABEL_44;
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
LABEL_43:
    *v34 = v6;
    v6 = 0;
    v13 = 0;
    goto LABEL_44;
  }
  do
    ++v11;
  while ( v21[v11] );
  v26 = MultiByteToWideChar(0, 0, v21, v11, 0, 0);
  v27 = v26;
  if ( !v26 )
  {
LABEL_16:
    v22 = GetLastError();
    v13 = v22;
    if ( v22 > 0 )
      v13 = (unsigned __int16)v22 | 0x80070000;
    goto LABEL_44;
  }
  v28 = SysAllocStringLen(0, v26);
  v29 = v28;
  if ( v28 )
  {
    if ( !MultiByteToWideChar(0, 0, v21, v11, v28, v27) )
    {
      v30 = GetLastError();
      v13 = v30;
      if ( v30 > 0 )
        v13 = (unsigned __int16)v30 | 0x80070000;
      SysFreeString(v29);
      goto LABEL_44;
    }
    *(_QWORD *)v5 = v29;
    goto LABEL_43;
  }
  v13 = -2147024882;
LABEL_44:
  operator delete(v21);
LABEL_45:
  operator delete(lpPathName);
  if ( v6 )
    CloseHandle(v6);
  return v13;
}

```

## disassembly

```asm
0x14000b184  mov     rax, rsp
0x14000b187  mov     [rax+10h], rbx
0x14000b18b  mov     [rax+20h], r9
0x14000b18f  push    rbp
0x14000b190  push    rsi
0x14000b191  push    rdi
0x14000b192  push    r12
0x14000b194  push    r13
0x14000b196  push    r14
0x14000b198  push    r15
0x14000b19a  sub     rsp, 50h
0x14000b19e  mov     r15, [rsp+88h+lpPathName]
0x14000b1a6  xor     edi, edi
0x14000b1a8  mov     [rax-48h], edi
0x14000b1ab  mov     rsi, rcx
0x14000b1ae  mov     [r9], rdi
0x14000b1b1  mov     ecx, 0FEFFh
0x14000b1b6  mov     [rax+8], cx
0x14000b1ba  mov     r12d, r8d
0x14000b1bd  mov     r13, rdx
0x14000b1c0  mov     ebp, edi
0x14000b1c2  test    r15, r15
0x14000b1c5  jz      short loc_14000B1CA
0x14000b1c7  mov     [r15], rdi
0x14000b1ca  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000b1ce  test    rsi, rsi
0x14000b1d1  jz      short loc_14000B21A
0x14000b1d3  mov     [rsp+88h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x14000b1d8  mov     r9d, ebx; cchWideChar
0x14000b1db  mov     [rsp+88h+lpDefaultChar], rdi; lpDefaultChar
0x14000b1e0  mov     r8, rsi; lpWideCharStr
0x14000b1e3  mov     [rsp+88h+cbMultiByte], edi; cbMultiByte
0x14000b1e7  xor     edx, edx; dwFlags
0x14000b1e9  xor     ecx, ecx; CodePage
0x14000b1eb  mov     [rsp+88h+lpMultiByteStr], rdi; lpMultiByteStr
0x14000b1f0  call    cs:__imp_WideCharToMultiByte
0x14000b1f6  mov     ebp, eax
0x14000b1f8  test    eax, eax
0x14000b1fa  jnz     short loc_14000B21A
0x14000b1fc  call    cs:__imp_GetLastError
0x14000b202  mov     ebx, eax
0x14000b204  test    eax, eax
0x14000b206  jle     loc_14000B4A8
0x14000b20c  movzx   ebx, ax
0x14000b20f  or      ebx, 80070000h
0x14000b215  jmp     loc_14000B4A8
0x14000b21a  xor     edx, edx
0x14000b21c  xor     ecx, ecx
0x14000b21e  call    cs:__imp_GetTempPath2A
0x14000b224  test    eax, eax
0x14000b226  jz      short loc_14000B1FC
0x14000b228  lea     r14d, [rax+1]
0x14000b22c  mov     ecx, r14d; Size
0x14000b22f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000b234  mov     [rsp+88h+lpPathName], rax
0x14000b23c  test    rax, rax
0x14000b23f  jnz     short loc_14000B24B
0x14000b241  mov     ebx, 8007000Eh
0x14000b246  jmp     loc_14000B4A8
0x14000b24b  mov     rdx, rax
0x14000b24e  mov     ecx, r14d
0x14000b251  call    cs:__imp_GetTempPath2A
0x14000b257  test    eax, eax
0x14000b259  jnz     short loc_14000B279
0x14000b25b  call    cs:__imp_GetLastError
0x14000b261  mov     ebx, eax
0x14000b263  test    eax, eax
0x14000b265  jle     loc_14000B48D
0x14000b26b  movzx   ebx, ax
0x14000b26e  or      ebx, 80070000h
0x14000b274  jmp     loc_14000B48D
0x14000b279  lea     r14d, [rax+0Fh]
0x14000b27d  add     r14d, ebp
0x14000b280  mov     ecx, r14d; Size
0x14000b283  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000b288  mov     rbp, rax
0x14000b28b  test    rax, rax
0x14000b28e  jnz     short loc_14000B29A
0x14000b290  mov     ebx, 8007000Eh
0x14000b295  jmp     loc_14000B48D
0x14000b29a  mov     rcx, [rsp+88h+lpPathName]; lpPathName
0x14000b2a2  lea     rdx, PrefixString; "wsh"
0x14000b2a9  mov     r9, rbp; lpTempFileName
0x14000b2ac  xor     r8d, r8d; uUnique
0x14000b2af  call    cs:__imp_GetTempFileNameA
0x14000b2b5  xor     ecx, ecx; CodePage
0x14000b2b7  test    eax, eax
0x14000b2b9  jnz     short loc_14000B2D9
0x14000b2bb  call    cs:__imp_GetLastError
0x14000b2c1  mov     ebx, eax
0x14000b2c3  test    eax, eax
0x14000b2c5  jle     loc_14000B485
0x14000b2cb  movzx   ebx, ax
0x14000b2ce  or      ebx, 80070000h
0x14000b2d4  jmp     loc_14000B485
0x14000b2d9  test    rsi, rsi
0x14000b2dc  jz      short loc_14000B317
0x14000b2de  mov     rax, rbx
0x14000b2e1  inc     rax
0x14000b2e4  cmp     [rax+rbp], cl
0x14000b2e7  jnz     short loc_14000B2E1
0x14000b2e9  sub     r14d, eax
0x14000b2ec  mov     [rsp+88h+lpUsedDefaultChar], rcx; lpUsedDefaultChar
0x14000b2f1  mov     [rsp+88h+lpDefaultChar], rcx; lpDefaultChar
0x14000b2f6  mov     r9d, ebx; cchWideChar
0x14000b2f9  mov     eax, eax
0x14000b2fb  mov     r8, rsi; lpWideCharStr
0x14000b2fe  add     rax, rbp
0x14000b301  mov     [rsp+88h+cbMultiByte], r14d; cbMultiByte
0x14000b306  xor     edx, edx; dwFlags
0x14000b308  mov     [rsp+88h+lpMultiByteStr], rax; lpMultiByteStr
0x14000b30d  call    cs:__imp_WideCharToMultiByte
0x14000b313  test    eax, eax
0x14000b315  jz      short loc_14000B2BB
0x14000b317  mov     [rsp+88h+lpDefaultChar], rdi; hTemplateFile
0x14000b31c  mov     esi, 2
0x14000b321  mov     [rsp+88h+cbMultiByte], 4002100h; dwFlagsAndAttributes
0x14000b329  xor     r9d, r9d; lpSecurityAttributes
0x14000b32c  xor     r8d, r8d; dwShareMode
0x14000b32f  mov     dword ptr [rsp+88h+lpMultiByteStr], esi; dwCreationDisposition
0x14000b333  mov     edx, 0C0000000h; dwDesiredAccess
0x14000b338  mov     rcx, rbp; lpFileName
0x14000b33b  call    cs:__imp_CreateFileA
0x14000b341  cmp     rax, rbx
0x14000b344  cmovnz  rdi, rax
0x14000b348  test    rdi, rdi
0x14000b34b  jnz     short loc_14000B369
0x14000b34d  call    cs:__imp_GetLastError
0x14000b353  mov     ebx, eax
0x14000b355  test    eax, eax
0x14000b357  jle     short loc_14000B362
0x14000b359  movzx   ebx, ax
0x14000b35c  or      ebx, 80070000h
0x14000b362  xor     edi, edi
0x14000b364  jmp     loc_14000B485
0x14000b369  test    r12d, r12d
0x14000b36c  jle     short loc_14000B3DE
0x14000b36e  movzx   eax, [rsp+88h+Buffer]
0x14000b376  cmp     [r13+0], ax
0x14000b37b  jz      short loc_14000B3A7
0x14000b37d  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14000b382  mov     [rsp+88h+lpMultiByteStr], 0; lpOverlapped
0x14000b38b  mov     r8d, esi; nNumberOfBytesToWrite
0x14000b38e  lea     rdx, [rsp+88h+Buffer]; lpBuffer
0x14000b396  mov     rcx, rdi; hFile
0x14000b399  call    cs:__imp_WriteFile
0x14000b39f  test    eax, eax
0x14000b3a1  jz      loc_14000B2BB
0x14000b3a7  lea     r8d, [r12+r12]; nNumberOfBytesToWrite
0x14000b3ab  mov     [rsp+88h+lpMultiByteStr], 0; lpOverlapped
0x14000b3b4  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14000b3b9  mov     rdx, r13; lpBuffer
0x14000b3bc  mov     rcx, rdi; hFile
0x14000b3bf  call    cs:__imp_WriteFile
0x14000b3c5  test    eax, eax
0x14000b3c7  jz      loc_14000B2BB
0x14000b3cd  mov     rcx, rdi; hFile
0x14000b3d0  call    cs:__imp_FlushFileBuffers
0x14000b3d6  test    eax, eax
0x14000b3d8  jz      loc_14000B2BB
0x14000b3de  test    r15, r15
0x14000b3e1  jz      loc_14000B476
0x14000b3e7  inc     rbx
0x14000b3ea  cmp     byte ptr [rbx+rbp], 0
0x14000b3ee  jnz     short loc_14000B3E7
0x14000b3f0  mov     [rsp+88h+cbMultiByte], 0; cchWideChar
0x14000b3f8  mov     r9d, ebx; cbMultiByte
0x14000b3fb  mov     r8, rbp; lpMultiByteStr
0x14000b3fe  mov     [rsp+88h+lpMultiByteStr], 0; lpWideCharStr
0x14000b407  xor     edx, edx; dwFlags
0x14000b409  xor     ecx, ecx; CodePage
0x14000b40b  call    cs:__imp_MultiByteToWideChar
0x14000b411  mov     r14d, eax
0x14000b414  test    eax, eax
0x14000b416  jz      loc_14000B2BB
0x14000b41c  mov     edx, eax; ui
0x14000b41e  xor     ecx, ecx; strIn
0x14000b420  call    cs:__imp_SysAllocStringLen
0x14000b426  mov     rsi, rax
0x14000b429  test    rax, rax
0x14000b42c  jnz     short loc_14000B435
0x14000b42e  mov     ebx, 8007000Eh
0x14000b433  jmp     short loc_14000B485
0x14000b435  mov     [rsp+88h+cbMultiByte], r14d; cchWideChar
0x14000b43a  mov     r9d, ebx; cbMultiByte
0x14000b43d  mov     r8, rbp; lpMultiByteStr
0x14000b440  mov     [rsp+88h+lpMultiByteStr], rsi; lpWideCharStr
0x14000b445  xor     edx, edx; dwFlags
0x14000b447  xor     ecx, ecx; CodePage
0x14000b449  call    cs:__imp_MultiByteToWideChar
0x14000b44f  test    eax, eax
0x14000b451  jnz     short loc_14000B473
0x14000b453  call    cs:__imp_GetLastError
0x14000b459  mov     ebx, eax
0x14000b45b  test    eax, eax
0x14000b45d  jle     short loc_14000B468
0x14000b45f  movzx   ebx, ax
0x14000b462  or      ebx, 80070000h
0x14000b468  mov     rcx, rsi; bstrString
0x14000b46b  call    cs:__imp_SysFreeString
0x14000b471  jmp     short loc_14000B485
0x14000b473  mov     [r15], rsi
0x14000b476  mov     rax, [rsp+88h+arg_18]
0x14000b47e  mov     [rax], rdi
0x14000b481  xor     edi, edi
0x14000b483  xor     ebx, ebx
0x14000b485  mov     rcx, rbp; Block
0x14000b488  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000b48d  mov     rcx, [rsp+88h+lpPathName]; Block
0x14000b495  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000b49a  test    rdi, rdi
0x14000b49d  jz      short loc_14000B4A8
0x14000b49f  mov     rcx, rdi; hObject
0x14000b4a2  call    cs:__imp_CloseHandle
0x14000b4a8  mov     eax, ebx
0x14000b4aa  mov     rbx, [rsp+88h+arg_8]
0x14000b4b2  add     rsp, 50h
0x14000b4b6  pop     r15
0x14000b4b8  pop     r14
0x14000b4ba  pop     r13
0x14000b4bc  pop     r12
0x14000b4be  pop     rdi
0x14000b4bf  pop     rsi
0x14000b4c0  pop     rbp
0x14000b4c1  retn
```
