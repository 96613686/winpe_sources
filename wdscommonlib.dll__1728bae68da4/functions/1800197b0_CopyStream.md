# CopyStream

- ea: `0x1800197b0`
- end: `0x180019ae5`
- name: `CopyStream`
- size: `821`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180019aec`

## callees

- `0x18000214c`
- `0x180006310`
- `0x1800197b0`
- `0x18001afd0`
- `0x18001b0cc`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180019aa4`
- `msvcrt!??3@YAXPEAX@Z` at `0x180019ab8`
- `msvcrt!??3@YAXPEAX@Z` at `0x180019aa4`
- `msvcrt!??3@YAXPEAX@Z` at `0x180019ab8`
- `KERNEL32!WriteFile` at `0x1800199fc`
- `KERNEL32!WriteFile` at `0x1800199fc`
- `KERNEL32!ReadFile` at `0x1800199c8`
- `KERNEL32!ReadFile` at `0x1800199c8`
- `KERNEL32!CreateFileW` at `0x1800198ad`
- `KERNEL32!CreateFileW` at `0x18001993c`
- `KERNEL32!CreateFileW` at `0x1800198ad`
- `KERNEL32!CreateFileW` at `0x18001993c`
- `KERNEL32!GetLastError` at `0x1800198c2`
- `KERNEL32!GetLastError` at `0x180019951`
- `KERNEL32!GetLastError` at `0x180019a1f`
- `KERNEL32!GetLastError` at `0x180019a52`
- `KERNEL32!GetLastError` at `0x1800198c2`
- `KERNEL32!GetLastError` at `0x180019951`
- `KERNEL32!GetLastError` at `0x180019a1f`
- `KERNEL32!GetLastError` at `0x180019a52`
- `KERNEL32!CloseHandle` at `0x180019a86`
- `KERNEL32!CloseHandle` at `0x180019a95`
- `KERNEL32!CloseHandle` at `0x180019a86`
- `KERNEL32!CloseHandle` at `0x180019a95`

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
0x1800197b0  mov     rax, rsp
0x1800197b3  mov     [rax+8], rbx
0x1800197b7  mov     [rax+10h], rbp
0x1800197bb  mov     [rax+18h], rsi
0x1800197bf  push    rdi
0x1800197c0  push    r12
0x1800197c2  push    r13
0x1800197c4  push    r14
0x1800197c6  push    r15
0x1800197c8  sub     rsp, 50h
0x1800197cc  xor     r13d, r13d
0x1800197cf  mov     r12, r8
0x1800197d2  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800197d6  mov     [rax+20h], r13d
0x1800197da  mov     r9, r8
0x1800197dd  mov     [rax-38h], r13d
0x1800197e1  mov     r14, rdx
0x1800197e4  mov     rbx, rcx
0x1800197e7  mov     esi, r13d
0x1800197ea  inc     r9
0x1800197ed  cmp     [rcx+r9*2], r13w
0x1800197f2  jnz     short loc_1800197EA
0x1800197f4  mov     rax, r8
0x1800197f7  inc     rax
0x1800197fa  cmp     [rdx+rax*2], r13w
0x1800197ff  jnz     short loc_1800197F7
0x180019801  cmp     r9, rax
0x180019804  mov     rax, r8
0x180019807  cmovbe  rcx, r14
0x18001980b  inc     rax
0x18001980e  cmp     [rcx+rax*2], r13w
0x180019813  jnz     short loc_18001980B
0x180019815  lea     rdi, [rax+106h]
0x18001981c  cmp     rdi, rax
0x18001981f  jnb     short loc_18001982B
0x180019821  mov     ebx, 80070216h
0x180019826  jmp     loc_180019AC4
0x18001982b  mov     eax, 2
0x180019830  mul     rdi
0x180019833  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001983a  cmovo   rax, r8
0x18001983e  mov     rcx, rax; unsigned __int64
0x180019841  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180019846  mov     rbp, rax
0x180019849  test    rax, rax
0x18001984c  jnz     short loc_180019858
0x18001984e  mov     ebx, 8007000Eh
0x180019853  jmp     loc_180019AC4
0x180019858  mov     r9, rbx
0x18001985b  mov     qword ptr [rsp+78h+dwCreationDisposition], r12
0x180019860  lea     r8, aSS_0; "%s%s"
0x180019867  mov     rdx, rdi; unsigned __int64
0x18001986a  mov     rcx, rbp; unsigned __int16 *
0x18001986d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019872  mov     r9d, 1BDh
0x180019878  mov     ecx, eax
0x18001987a  mov     ebx, eax
0x18001987c  call    ElValidateHr_5
0x180019881  test    eax, eax
0x180019883  js      loc_180019AA1
0x180019889  mov     eax, 3
0x18001988e  mov     [rsp+78h+hTemplateFile], r13; hTemplateFile
0x180019893  mov     r8d, eax; dwShareMode
0x180019896  mov     [rsp+78h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x18001989e  xor     r9d, r9d; lpSecurityAttributes
0x1800198a1  mov     [rsp+78h+dwCreationDisposition], eax; dwCreationDisposition
0x1800198a5  mov     edx, 80000000h; dwDesiredAccess
0x1800198aa  mov     rcx, rbp; lpFileName
0x1800198ad  call    cs:__imp_CreateFileW
0x1800198b4  nop     dword ptr [rax+rax+00h]
0x1800198b9  mov     r15, rax
0x1800198bc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800198c0  jnz     short loc_1800198FC
0x1800198c2  call    cs:__imp_GetLastError
0x1800198c9  nop     dword ptr [rax+rax+00h]
0x1800198ce  mov     ecx, eax
0x1800198d0  mov     r9d, 1CCh
0x1800198d6  call    ElValidateWin32_8
0x1800198db  mov     ebx, eax
0x1800198dd  test    eax, eax
0x1800198df  jle     short loc_1800198EA
0x1800198e1  movzx   ebx, ax
0x1800198e4  or      ebx, 80070000h
0x1800198ea  test    ebx, ebx
0x1800198ec  js      loc_180019AA1
0x1800198f2  mov     ebx, 80004005h
0x1800198f7  jmp     loc_180019AA1
0x1800198fc  mov     r9, r14
0x1800198ff  mov     qword ptr [rsp+78h+dwCreationDisposition], r12
0x180019904  lea     r8, aSS_0; "%s%s"
0x18001990b  mov     rdx, rdi; unsigned __int64
0x18001990e  mov     rcx, rbp; unsigned __int16 *
0x180019911  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019916  xor     r9d, r9d; lpSecurityAttributes
0x180019919  mov     [rsp+78h+hTemplateFile], r13; hTemplateFile
0x18001991e  mov     [rsp+78h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x180019926  mov     edx, 0C0000000h; dwDesiredAccess
0x18001992b  mov     rcx, rbp; lpFileName
0x18001992e  mov     [rsp+78h+dwCreationDisposition], 2; dwCreationDisposition
0x180019936  mov     ebx, eax
0x180019938  lea     r8d, [r9+3]; dwShareMode
0x18001993c  call    cs:__imp_CreateFileW
0x180019943  nop     dword ptr [rax+rax+00h]
0x180019948  mov     r14, rax
0x18001994b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001994f  jnz     short loc_18001998B
0x180019951  call    cs:__imp_GetLastError
0x180019958  nop     dword ptr [rax+rax+00h]
0x18001995d  mov     ecx, eax
0x18001995f  mov     r9d, 1E6h
0x180019965  call    ElValidateWin32_8
0x18001996a  mov     ebx, eax
0x18001996c  test    eax, eax
0x18001996e  jle     short loc_180019979
0x180019970  movzx   ebx, ax
0x180019973  or      ebx, 80070000h
0x180019979  test    ebx, ebx
0x18001997b  js      loc_180019A92
0x180019981  mov     ebx, 80004005h
0x180019986  jmp     loc_180019A92
0x18001998b  mov     r12d, 8000h
0x180019991  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180019998  mov     ecx, r12d; unsigned __int64
0x18001999b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800199a0  mov     rsi, rax
0x1800199a3  test    rax, rax
0x1800199a6  jnz     short loc_1800199B2
0x1800199a8  mov     ebx, 8007000Eh
0x1800199ad  jmp     loc_180019A83
0x1800199b2  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800199ba  mov     qword ptr [rsp+78h+dwCreationDisposition], r13; lpOverlapped
0x1800199bf  mov     r8d, r12d; nNumberOfBytesToRead
0x1800199c2  mov     rdx, rsi; lpBuffer
0x1800199c5  mov     rcx, r15; hFile
0x1800199c8  call    cs:__imp_ReadFile
0x1800199cf  nop     dword ptr [rax+rax+00h]
0x1800199d4  test    eax, eax
0x1800199d6  jz      short loc_180019A52
0x1800199d8  mov     eax, [rsp+78h+NumberOfBytesRead]
0x1800199df  mov     edi, eax
0x1800199e1  test    edi, edi
0x1800199e3  jz      short loc_180019A19
0x1800199e5  sub     eax, edi
0x1800199e7  mov     qword ptr [rsp+78h+dwCreationDisposition], r13; lpOverlapped
0x1800199ec  mov     edx, eax
0x1800199ee  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800199f3  add     rdx, rsi; lpBuffer
0x1800199f6  mov     r8d, edi; nNumberOfBytesToWrite
0x1800199f9  mov     rcx, r14; hFile
0x1800199fc  call    cs:__imp_WriteFile
0x180019a03  nop     dword ptr [rax+rax+00h]
0x180019a08  sub     edi, [rsp+78h+NumberOfBytesWritten]
0x180019a0c  test    eax, eax
0x180019a0e  jz      short loc_180019A1F
0x180019a10  mov     eax, [rsp+78h+NumberOfBytesRead]
0x180019a17  jmp     short loc_1800199E1
0x180019a19  test    eax, eax
0x180019a1b  jnz     short loc_1800199B2
0x180019a1d  jmp     short loc_180019A83
0x180019a1f  call    cs:__imp_GetLastError
0x180019a26  nop     dword ptr [rax+rax+00h]
0x180019a2b  mov     ecx, eax
0x180019a2d  mov     r9d, 214h
0x180019a33  call    ElValidateWin32_8
0x180019a38  mov     ebx, eax
0x180019a3a  test    eax, eax
0x180019a3c  jle     short loc_180019A47
0x180019a3e  movzx   ebx, ax
0x180019a41  or      ebx, 80070000h
0x180019a47  test    ebx, ebx
0x180019a49  js      short loc_180019A83
0x180019a4b  mov     ebx, 80004005h
0x180019a50  jmp     short loc_180019A83
0x180019a52  call    cs:__imp_GetLastError
0x180019a59  nop     dword ptr [rax+rax+00h]
0x180019a5e  mov     ecx, eax
0x180019a60  mov     r9d, 1FEh
0x180019a66  call    ElValidateWin32_8
0x180019a6b  test    eax, eax
0x180019a6d  jle     short loc_180019A77
0x180019a6f  movzx   eax, ax
0x180019a72  or      eax, 80070000h
0x180019a77  mov     ebx, 80004005h
0x180019a7c  test    eax, eax
0x180019a7e  cmovns  eax, ebx
0x180019a81  mov     ebx, eax
0x180019a83  mov     rcx, r14; hObject
0x180019a86  call    cs:__imp_CloseHandle
0x180019a8d  nop     dword ptr [rax+rax+00h]
0x180019a92  mov     rcx, r15; hObject
0x180019a95  call    cs:__imp_CloseHandle
0x180019a9c  nop     dword ptr [rax+rax+00h]
0x180019aa1  mov     rcx, rbp
0x180019aa4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180019aab  nop     dword ptr [rax+rax+00h]
0x180019ab0  test    rsi, rsi
0x180019ab3  jz      short loc_180019AC4
0x180019ab5  mov     rcx, rsi
0x180019ab8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180019abf  nop     dword ptr [rax+rax+00h]
0x180019ac4  lea     r11, [rsp+78h+var_28]
0x180019ac9  mov     eax, ebx
0x180019acb  mov     rbx, [r11+30h]
0x180019acf  mov     rbp, [r11+38h]
0x180019ad3  mov     rsi, [r11+40h]
0x180019ad7  mov     rsp, r11
0x180019ada  pop     r15
0x180019adc  pop     r14
0x180019ade  pop     r13
0x180019ae0  pop     r12
0x180019ae2  pop     rdi
0x180019ae3  retn
```
