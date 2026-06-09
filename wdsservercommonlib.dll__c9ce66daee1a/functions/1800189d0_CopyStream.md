# CopyStream

- ea: `0x1800189d0`
- end: `0x180018cf7`
- name: `CopyStream`
- size: `807`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180018d00`

## callees

- `0x18000179c`
- `0x180005830`
- `0x1800189d0`
- `0x18001a190`
- `0x18001a28c`
- `0x18002e468`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180018ae2`
- `KERNEL32!GetLastError` at `0x180018b71`
- `KERNEL32!GetLastError` at `0x180018c3f`
- `KERNEL32!GetLastError` at `0x180018c72`
- `KERNEL32!GetLastError` at `0x180018ae2`
- `KERNEL32!GetLastError` at `0x180018b71`
- `KERNEL32!GetLastError` at `0x180018c3f`
- `KERNEL32!GetLastError` at `0x180018c72`
- `KERNEL32!CloseHandle` at `0x180018ca6`
- `KERNEL32!CloseHandle` at `0x180018cb5`
- `KERNEL32!CloseHandle` at `0x180018ca6`
- `KERNEL32!CloseHandle` at `0x180018cb5`
- `KERNEL32!CreateFileW` at `0x180018acd`
- `KERNEL32!CreateFileW` at `0x180018b5c`
- `KERNEL32!CreateFileW` at `0x180018acd`
- `KERNEL32!CreateFileW` at `0x180018b5c`
- `KERNEL32!ReadFile` at `0x180018be8`
- `KERNEL32!ReadFile` at `0x180018be8`
- `KERNEL32!WriteFile` at `0x180018c1c`
- `KERNEL32!WriteFile` at `0x180018c1c`

## pseudocode

```c
__int64 __fastcall CopyStream(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned __int64 v4; // r9
  __int64 v6; // rbx
  char *v7; // rsi
  unsigned __int64 v8; // rax
  bool v9; // cc
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rdi
  __int64 v12; // rbx
  unsigned __int64 v13; // rax
  unsigned __int16 *v14; // rax
  WCHAR *v15; // rbp
  __int64 v16; // rdx
  __int64 v17; // r8
  HANDLE FileW; // r15
  DWORD LastError; // eax
  __int64 v20; // rdx
  __int64 v21; // r8
  int v22; // eax
  HANDLE v23; // r14
  DWORD v24; // eax
  __int64 v25; // rdx
  __int64 v26; // r8
  int v27; // eax
  DWORD v28; // eax
  DWORD v29; // edi
  BOOL v30; // eax
  DWORD v31; // eax
  __int64 v32; // rdx
  __int64 v33; // r8
  int v34; // eax
  DWORD v35; // eax
  __int64 v36; // rdx
  __int64 v37; // r8
  signed int v38; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-38h] BYREF
  DWORD NumberOfBytesRead; // [rsp+98h] [rbp+20h] BYREF

  NumberOfBytesRead = 0;
  v4 = -1;
  NumberOfBytesWritten = 0;
  v6 = a1;
  v7 = 0;
  do
    ++v4;
  while ( *(_WORD *)(a1 + 2 * v4) );
  v8 = -1;
  do
    ++v8;
  while ( *(_WORD *)(a2 + 2 * v8) );
  v9 = v4 <= v8;
  v10 = -1;
  if ( v9 )
    a1 = a2;
  do
    ++v10;
  while ( *(_WORD *)(a1 + 2 * v10) );
  v11 = v10 + 262;
  if ( v10 + 262 >= v10 )
  {
    v13 = 2 * v11;
    if ( !is_mul_ok(v11, 2u) )
      v13 = -1;
    v14 = (unsigned __int16 *)operator new[](v13, (const struct std::nothrow_t *)&std::nothrow);
    v15 = v14;
    if ( v14 )
    {
      v12 = (unsigned int)StringCchPrintfW(v14, v11, L"%s%s", v6, a3);
      if ( (int)ElValidateHr_5(v12, v16, v17, 445) >= 0 )
      {
        FileW = CreateFileW(v15, 0x80000000, 3u, 0, 3u, 0x8000000u, 0);
        if ( FileW == (HANDLE)-1LL )
        {
          LastError = GetLastError();
          v22 = ElValidateWin32_8(LastError, v20, v21, 460);
          LODWORD(v12) = v22;
          if ( v22 > 0 )
            LODWORD(v12) = (unsigned __int16)v22 | 0x80070000;
          if ( (int)v12 >= 0 )
            LODWORD(v12) = -2147467259;
        }
        else
        {
          LODWORD(v12) = StringCchPrintfW(v15, v11, L"%s%s", a2, a3);
          v23 = CreateFileW(v15, 0xC0000000, 3u, 0, 2u, 0x8000000u, 0);
          if ( v23 == (HANDLE)-1LL )
          {
            v24 = GetLastError();
            v27 = ElValidateWin32_8(v24, v25, v26, 486);
            LODWORD(v12) = v27;
            if ( v27 > 0 )
              LODWORD(v12) = (unsigned __int16)v27 | 0x80070000;
            if ( (int)v12 >= 0 )
              LODWORD(v12) = -2147467259;
          }
          else
          {
            v7 = (char *)operator new[](0x8000u, (const struct std::nothrow_t *)&std::nothrow);
            if ( v7 )
            {
              while ( 2 )
              {
                if ( ReadFile(FileW, v7, 0x8000u, &NumberOfBytesRead, 0) )
                {
                  v28 = NumberOfBytesRead;
                  v29 = NumberOfBytesRead;
                  while ( v29 )
                  {
                    v30 = WriteFile(v23, &v7[v28 - v29], v29, &NumberOfBytesWritten, 0);
                    v29 -= NumberOfBytesWritten;
                    if ( !v30 )
                    {
                      v31 = GetLastError();
                      v34 = ElValidateWin32_8(v31, v32, v33, 532);
                      LODWORD(v12) = v34;
                      if ( v34 > 0 )
                        LODWORD(v12) = (unsigned __int16)v34 | 0x80070000;
                      if ( (int)v12 >= 0 )
                        LODWORD(v12) = -2147467259;
                      goto LABEL_43;
                    }
                    v28 = NumberOfBytesRead;
                  }
                  if ( v28 )
                    continue;
                }
                else
                {
                  v35 = GetLastError();
                  v38 = ElValidateWin32_8(v35, v36, v37, 510);
                  if ( v38 > 0 )
                    v38 = (unsigned __int16)v38 | 0x80070000;
                  if ( v38 >= 0 )
                    v38 = -2147467259;
                  LODWORD(v12) = v38;
                }
                break;
              }
            }
            else
            {
              LODWORD(v12) = -2147024882;
            }
LABEL_43:
            CloseHandle(v23);
          }
          CloseHandle(FileW);
        }
      }
      operator delete(v15);
      if ( v7 )
        operator delete(v7);
    }
    else
    {
      LODWORD(v12) = -2147024882;
    }
  }
  else
  {
    LODWORD(v12) = -2147024362;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800189d0  mov     rax, rsp
0x1800189d3  mov     [rax+8], rbx
0x1800189d7  mov     [rax+10h], rbp
0x1800189db  mov     [rax+18h], rsi
0x1800189df  push    rdi
0x1800189e0  push    r12
0x1800189e2  push    r13
0x1800189e4  push    r14
0x1800189e6  push    r15
0x1800189e8  sub     rsp, 50h
0x1800189ec  xor     r13d, r13d
0x1800189ef  mov     r12, r8
0x1800189f2  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800189f6  mov     [rax+20h], r13d
0x1800189fa  mov     r9, r8
0x1800189fd  mov     [rax-38h], r13d
0x180018a01  mov     r14, rdx
0x180018a04  mov     rbx, rcx
0x180018a07  mov     esi, r13d
0x180018a0a  inc     r9
0x180018a0d  cmp     [rcx+r9*2], r13w
0x180018a12  jnz     short loc_180018A0A
0x180018a14  mov     rax, r8
0x180018a17  inc     rax
0x180018a1a  cmp     [rdx+rax*2], r13w
0x180018a1f  jnz     short loc_180018A17
0x180018a21  cmp     r9, rax
0x180018a24  mov     rax, r8
0x180018a27  cmovbe  rcx, r14
0x180018a2b  inc     rax
0x180018a2e  cmp     [rcx+rax*2], r13w
0x180018a33  jnz     short loc_180018A2B
0x180018a35  lea     rdi, [rax+106h]
0x180018a3c  cmp     rdi, rax
0x180018a3f  jnb     short loc_180018A4B
0x180018a41  mov     ebx, 80070216h
0x180018a46  jmp     loc_180018CD6
0x180018a4b  mov     eax, 2
0x180018a50  mul     rdi
0x180018a53  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180018a5a  cmovo   rax, r8
0x180018a5e  mov     rcx, rax; unsigned __int64
0x180018a61  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180018a66  mov     rbp, rax
0x180018a69  test    rax, rax
0x180018a6c  jnz     short loc_180018A78
0x180018a6e  mov     ebx, 8007000Eh
0x180018a73  jmp     loc_180018CD6
0x180018a78  mov     r9, rbx
0x180018a7b  mov     qword ptr [rsp+78h+dwCreationDisposition], r12
0x180018a80  lea     r8, aSS_0; "%s%s"
0x180018a87  mov     rdx, rdi; unsigned __int64
0x180018a8a  mov     rcx, rbp; unsigned __int16 *
0x180018a8d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018a92  mov     r9d, 1BDh
0x180018a98  mov     ecx, eax
0x180018a9a  mov     ebx, eax
0x180018a9c  call    ElValidateHr_5
0x180018aa1  test    eax, eax
0x180018aa3  js      loc_180018CC1
0x180018aa9  mov     eax, 3
0x180018aae  mov     [rsp+78h+hTemplateFile], r13; hTemplateFile
0x180018ab3  mov     r8d, eax; dwShareMode
0x180018ab6  mov     [rsp+78h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x180018abe  xor     r9d, r9d; lpSecurityAttributes
0x180018ac1  mov     [rsp+78h+dwCreationDisposition], eax; dwCreationDisposition
0x180018ac5  mov     edx, 80000000h; dwDesiredAccess
0x180018aca  mov     rcx, rbp; lpFileName
0x180018acd  call    cs:__imp_CreateFileW
0x180018ad4  nop     dword ptr [rax+rax+00h]
0x180018ad9  mov     r15, rax
0x180018adc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180018ae0  jnz     short loc_180018B1C
0x180018ae2  call    cs:__imp_GetLastError
0x180018ae9  nop     dword ptr [rax+rax+00h]
0x180018aee  mov     ecx, eax
0x180018af0  mov     r9d, 1CCh
0x180018af6  call    ElValidateWin32_8
0x180018afb  mov     ebx, eax
0x180018afd  test    eax, eax
0x180018aff  jle     short loc_180018B0A
0x180018b01  movzx   ebx, ax
0x180018b04  or      ebx, 80070000h
0x180018b0a  test    ebx, ebx
0x180018b0c  js      loc_180018CC1
0x180018b12  mov     ebx, 80004005h
0x180018b17  jmp     loc_180018CC1
0x180018b1c  mov     r9, r14
0x180018b1f  mov     qword ptr [rsp+78h+dwCreationDisposition], r12
0x180018b24  lea     r8, aSS_0; "%s%s"
0x180018b2b  mov     rdx, rdi; unsigned __int64
0x180018b2e  mov     rcx, rbp; unsigned __int16 *
0x180018b31  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018b36  xor     r9d, r9d; lpSecurityAttributes
0x180018b39  mov     [rsp+78h+hTemplateFile], r13; hTemplateFile
0x180018b3e  mov     [rsp+78h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x180018b46  mov     edx, 0C0000000h; dwDesiredAccess
0x180018b4b  mov     rcx, rbp; lpFileName
0x180018b4e  mov     [rsp+78h+dwCreationDisposition], 2; dwCreationDisposition
0x180018b56  mov     ebx, eax
0x180018b58  lea     r8d, [r9+3]; dwShareMode
0x180018b5c  call    cs:__imp_CreateFileW
0x180018b63  nop     dword ptr [rax+rax+00h]
0x180018b68  mov     r14, rax
0x180018b6b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180018b6f  jnz     short loc_180018BAB
0x180018b71  call    cs:__imp_GetLastError
0x180018b78  nop     dword ptr [rax+rax+00h]
0x180018b7d  mov     ecx, eax
0x180018b7f  mov     r9d, 1E6h
0x180018b85  call    ElValidateWin32_8
0x180018b8a  mov     ebx, eax
0x180018b8c  test    eax, eax
0x180018b8e  jle     short loc_180018B99
0x180018b90  movzx   ebx, ax
0x180018b93  or      ebx, 80070000h
0x180018b99  test    ebx, ebx
0x180018b9b  js      loc_180018CB2
0x180018ba1  mov     ebx, 80004005h
0x180018ba6  jmp     loc_180018CB2
0x180018bab  mov     r12d, 8000h
0x180018bb1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180018bb8  mov     ecx, r12d; unsigned __int64
0x180018bbb  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180018bc0  mov     rsi, rax
0x180018bc3  test    rax, rax
0x180018bc6  jnz     short loc_180018BD2
0x180018bc8  mov     ebx, 8007000Eh
0x180018bcd  jmp     loc_180018CA3
0x180018bd2  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180018bda  mov     qword ptr [rsp+78h+dwCreationDisposition], r13; lpOverlapped
0x180018bdf  mov     r8d, r12d; nNumberOfBytesToRead
0x180018be2  mov     rdx, rsi; lpBuffer
0x180018be5  mov     rcx, r15; hFile
0x180018be8  call    cs:__imp_ReadFile
0x180018bef  nop     dword ptr [rax+rax+00h]
0x180018bf4  test    eax, eax
0x180018bf6  jz      short loc_180018C72
0x180018bf8  mov     eax, [rsp+78h+NumberOfBytesRead]
0x180018bff  mov     edi, eax
0x180018c01  test    edi, edi
0x180018c03  jz      short loc_180018C39
0x180018c05  sub     eax, edi
0x180018c07  mov     qword ptr [rsp+78h+dwCreationDisposition], r13; lpOverlapped
0x180018c0c  mov     edx, eax
0x180018c0e  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180018c13  add     rdx, rsi; lpBuffer
0x180018c16  mov     r8d, edi; nNumberOfBytesToWrite
0x180018c19  mov     rcx, r14; hFile
0x180018c1c  call    cs:__imp_WriteFile
0x180018c23  nop     dword ptr [rax+rax+00h]
0x180018c28  sub     edi, [rsp+78h+NumberOfBytesWritten]
0x180018c2c  test    eax, eax
0x180018c2e  jz      short loc_180018C3F
0x180018c30  mov     eax, [rsp+78h+NumberOfBytesRead]
0x180018c37  jmp     short loc_180018C01
0x180018c39  test    eax, eax
0x180018c3b  jnz     short loc_180018BD2
0x180018c3d  jmp     short loc_180018CA3
0x180018c3f  call    cs:__imp_GetLastError
0x180018c46  nop     dword ptr [rax+rax+00h]
0x180018c4b  mov     ecx, eax
0x180018c4d  mov     r9d, 214h
0x180018c53  call    ElValidateWin32_8
0x180018c58  mov     ebx, eax
0x180018c5a  test    eax, eax
0x180018c5c  jle     short loc_180018C67
0x180018c5e  movzx   ebx, ax
0x180018c61  or      ebx, 80070000h
0x180018c67  test    ebx, ebx
0x180018c69  js      short loc_180018CA3
0x180018c6b  mov     ebx, 80004005h
0x180018c70  jmp     short loc_180018CA3
0x180018c72  call    cs:__imp_GetLastError
0x180018c79  nop     dword ptr [rax+rax+00h]
0x180018c7e  mov     ecx, eax
0x180018c80  mov     r9d, 1FEh
0x180018c86  call    ElValidateWin32_8
0x180018c8b  test    eax, eax
0x180018c8d  jle     short loc_180018C97
0x180018c8f  movzx   eax, ax
0x180018c92  or      eax, 80070000h
0x180018c97  mov     ebx, 80004005h
0x180018c9c  test    eax, eax
0x180018c9e  cmovns  eax, ebx
0x180018ca1  mov     ebx, eax
0x180018ca3  mov     rcx, r14; hObject
0x180018ca6  call    cs:__imp_CloseHandle
0x180018cad  nop     dword ptr [rax+rax+00h]
0x180018cb2  mov     rcx, r15; hObject
0x180018cb5  call    cs:__imp_CloseHandle
0x180018cbc  nop     dword ptr [rax+rax+00h]
0x180018cc1  mov     rcx, rbp; lpMem
0x180018cc4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018cc9  test    rsi, rsi
0x180018ccc  jz      short loc_180018CD6
0x180018cce  mov     rcx, rsi; lpMem
0x180018cd1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018cd6  lea     r11, [rsp+78h+var_28]
0x180018cdb  mov     eax, ebx
0x180018cdd  mov     rbx, [r11+30h]
0x180018ce1  mov     rbp, [r11+38h]
0x180018ce5  mov     rsi, [r11+40h]
0x180018ce9  mov     rsp, r11
0x180018cec  pop     r15
0x180018cee  pop     r14
0x180018cf0  pop     r13
0x180018cf2  pop     r12
0x180018cf4  pop     rdi
0x180018cf5  retn
```
