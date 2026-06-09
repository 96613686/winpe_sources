# WdsCompareFiles

- ea: `0x18001bbc0`
- end: `0x18001beab`
- name: `WdsCompareFiles`
- size: `747`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000214c`
- `0x18001b0cc`
- `0x18001bbc0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001be6a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001be7e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001be6a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001be7e`
- `KERNEL32!ReadFile` at `0x18001bd83`
- `KERNEL32!ReadFile` at `0x18001bda5`
- `KERNEL32!ReadFile` at `0x18001bd83`
- `KERNEL32!ReadFile` at `0x18001bda5`
- `KERNEL32!CreateFileW` at `0x18001bc1d`
- `KERNEL32!CreateFileW` at `0x18001bc77`
- `KERNEL32!CreateFileW` at `0x18001bc1d`
- `KERNEL32!CreateFileW` at `0x18001bc77`
- `KERNEL32!GetLastError` at `0x18001bc36`
- `KERNEL32!GetLastError` at `0x18001bc8c`
- `KERNEL32!GetLastError` at `0x18001bcbc`
- `KERNEL32!GetLastError` at `0x18001bcec`
- `KERNEL32!GetLastError` at `0x18001bdf5`
- `KERNEL32!GetLastError` at `0x18001be0b`
- `KERNEL32!GetLastError` at `0x18001bc36`
- `KERNEL32!GetLastError` at `0x18001bc8c`
- `KERNEL32!GetLastError` at `0x18001bcbc`
- `KERNEL32!GetLastError` at `0x18001bcec`
- `KERNEL32!GetLastError` at `0x18001bdf5`
- `KERNEL32!GetLastError` at `0x18001be0b`
- `KERNEL32!CloseHandle` at `0x18001be41`
- `KERNEL32!CloseHandle` at `0x18001be56`
- `KERNEL32!CloseHandle` at `0x18001be41`
- `KERNEL32!CloseHandle` at `0x18001be56`
- `KERNEL32!GetFileSizeEx` at `0x18001bcac`
- `KERNEL32!GetFileSizeEx` at `0x18001bcdc`
- `KERNEL32!GetFileSizeEx` at `0x18001bcac`
- `KERNEL32!GetFileSizeEx` at `0x18001bcdc`

## pseudocode

```c
__int64 __fastcall WdsCompareFiles(const WCHAR *a1, const WCHAR *a2, _DWORD *a3)
{
  unsigned int v5; // edi
  void *v6; // r14
  void *v7; // r15
  DWORD LastError; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  HANDLE FileW; // r12
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  DWORD v16; // esi
  void *v17; // rax
  union _LARGE_INTEGER v18; // rbx
  union _LARGE_INTEGER v19; // rcx
  DWORD v20; // edx
  _BYTE *v21; // rcx
  union _LARGE_INTEGER FileSize; // [rsp+40h] [rbp-20h] BYREF
  union _LARGE_INTEGER v24; // [rsp+48h] [rbp-18h]
  union _LARGE_INTEGER v25; // [rsp+50h] [rbp-10h] BYREF
  HANDLE hFile; // [rsp+58h] [rbp-8h]
  DWORD NumberOfBytesRead; // [rsp+A8h] [rbp+48h] BYREF

  FileSize.QuadPart = 0;
  v25.QuadPart = 0;
  v5 = 0;
  v24.QuadPart = 0;
  NumberOfBytesRead = 0;
  v6 = 0;
  v7 = 0;
  hFile = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0, 0);
  if ( hFile == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    return (unsigned int)ElValidateWin32_8(LastError, v9, v10, 4601);
  }
  FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    v13 = GetLastError();
    v15 = 4615;
LABEL_28:
    v5 = ElValidateWin32_8(v13, v12, v14, v15);
    goto LABEL_29;
  }
  if ( !GetFileSizeEx(hFile, &FileSize) )
  {
    v13 = GetLastError();
    v15 = 4621;
    goto LABEL_28;
  }
  if ( !GetFileSizeEx(FileW, &v25) )
  {
    v13 = GetLastError();
    v15 = 4627;
    goto LABEL_28;
  }
  if ( FileSize.QuadPart == v25.QuadPart )
  {
    v16 = 0x100000;
    v6 = operator new[](0x100000u, (const struct std::nothrow_t *)&std::nothrow);
    v17 = operator new[](0x100000u, (const struct std::nothrow_t *)&std::nothrow);
    v7 = v17;
    if ( !v6 || !v17 )
    {
      v13 = 8;
      v15 = 4641;
      goto LABEL_28;
    }
    v18 = v24;
    v19 = FileSize;
    if ( v24.QuadPart >= FileSize.QuadPart )
    {
LABEL_26:
      *a3 = 1;
      goto LABEL_29;
    }
    while ( 1 )
    {
      if ( v19.QuadPart - v18.QuadPart <= 0x100000 )
        v16 = FileSize.LowPart - v24.LowPart;
      if ( !ReadFile(hFile, v6, v16, &NumberOfBytesRead, 0) )
      {
        v13 = GetLastError();
        v15 = 4658;
        goto LABEL_28;
      }
      if ( !ReadFile(FileW, v7, v16, &NumberOfBytesRead, 0) )
      {
        v13 = GetLastError();
        v15 = 4664;
        goto LABEL_28;
      }
      v20 = 0;
      if ( v16 )
        break;
LABEL_22:
      v19 = FileSize;
      v18.QuadPart += v16;
      v24 = v18;
      if ( v18.QuadPart >= FileSize.QuadPart )
        goto LABEL_26;
      v16 = 0x100000;
    }
    v21 = v6;
    while ( *v21 == v21[(_BYTE *)v7 - (_BYTE *)v6] )
    {
      ++v20;
      ++v21;
      if ( v20 >= v16 )
        goto LABEL_22;
    }
  }
  *a3 = 0;
LABEL_29:
  CloseHandle(hFile);
  if ( FileW != (HANDLE)-1LL )
    CloseHandle(FileW);
  if ( v6 )
    operator delete(v6);
  if ( v7 )
    operator delete(v7);
  return v5;
}

```

## disassembly

```asm
0x18001bbc0  mov     rax, rsp
0x18001bbc3  mov     [rax+8], rbx
0x18001bbc7  mov     [rax+10h], rsi
0x18001bbcb  mov     [rax+18h], rdi
0x18001bbcf  push    rbp
0x18001bbd0  push    r12
0x18001bbd2  push    r13
0x18001bbd4  push    r14
0x18001bbd6  push    r15
0x18001bbd8  mov     rbp, rsp
0x18001bbdb  sub     rsp, 60h
0x18001bbdf  xor     r12d, r12d
0x18001bbe2  mov     r13, r8
0x18001bbe5  mov     [rax-58h], r12
0x18001bbe9  mov     rbx, rdx
0x18001bbec  mov     [rax-60h], r12d
0x18001bbf0  xor     r9d, r9d; lpSecurityAttributes
0x18001bbf3  mov     edx, 80000000h; dwDesiredAccess
0x18001bbf8  mov     qword ptr [rbp+FileSize], r12
0x18001bbfc  lea     r8d, [r12+1]; dwShareMode
0x18001bc01  mov     qword ptr [rbp+var_10], r12
0x18001bc05  mov     edi, r12d
0x18001bc08  mov     [rbp+var_18], r12
0x18001bc0c  mov     [rbp+NumberOfBytesRead], r12d
0x18001bc10  mov     r14d, r12d
0x18001bc13  mov     r15d, r12d
0x18001bc16  mov     dword ptr [rax-68h], 3
0x18001bc1d  call    cs:__imp_CreateFileW
0x18001bc24  nop     dword ptr [rax+rax+00h]
0x18001bc29  mov     [rbp+hFile], rax
0x18001bc2d  mov     rsi, rax
0x18001bc30  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001bc34  jnz     short loc_18001BC56
0x18001bc36  call    cs:__imp_GetLastError
0x18001bc3d  nop     dword ptr [rax+rax+00h]
0x18001bc42  mov     ecx, eax
0x18001bc44  mov     r9d, 11F9h
0x18001bc4a  call    ElValidateWin32_8
0x18001bc4f  mov     edi, eax
0x18001bc51  jmp     loc_18001BE8A
0x18001bc56  xor     r9d, r9d; lpSecurityAttributes
0x18001bc59  mov     [rsp+60h+hTemplateFile], r12; hTemplateFile
0x18001bc5e  mov     [rsp+60h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x18001bc63  mov     edx, 80000000h; dwDesiredAccess
0x18001bc68  mov     rcx, rbx; lpFileName
0x18001bc6b  mov     [rsp+60h+dwCreationDisposition], 3; lpOverlapped
0x18001bc73  lea     r8d, [r9+1]; dwShareMode
0x18001bc77  call    cs:__imp_CreateFileW
0x18001bc7e  nop     dword ptr [rax+rax+00h]
0x18001bc83  mov     r12, rax
0x18001bc86  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001bc8a  jnz     short loc_18001BCA5
0x18001bc8c  call    cs:__imp_GetLastError
0x18001bc93  nop     dword ptr [rax+rax+00h]
0x18001bc98  mov     ecx, eax
0x18001bc9a  mov     r9d, 1207h
0x18001bca0  jmp     loc_18001BE36
0x18001bca5  lea     rdx, [rbp+FileSize]; lpFileSize
0x18001bca9  mov     rcx, rsi; hFile
0x18001bcac  call    cs:__imp_GetFileSizeEx
0x18001bcb3  nop     dword ptr [rax+rax+00h]
0x18001bcb8  test    eax, eax
0x18001bcba  jnz     short loc_18001BCD5
0x18001bcbc  call    cs:__imp_GetLastError
0x18001bcc3  nop     dword ptr [rax+rax+00h]
0x18001bcc8  mov     ecx, eax
0x18001bcca  mov     r9d, 120Dh
0x18001bcd0  jmp     loc_18001BE36
0x18001bcd5  lea     rdx, [rbp+var_10]; lpFileSize
0x18001bcd9  mov     rcx, r12; hFile
0x18001bcdc  call    cs:__imp_GetFileSizeEx
0x18001bce3  nop     dword ptr [rax+rax+00h]
0x18001bce8  test    eax, eax
0x18001bcea  jnz     short loc_18001BD05
0x18001bcec  call    cs:__imp_GetLastError
0x18001bcf3  nop     dword ptr [rax+rax+00h]
0x18001bcf8  mov     ecx, eax
0x18001bcfa  mov     r9d, 1213h
0x18001bd00  jmp     loc_18001BE36
0x18001bd05  mov     rax, qword ptr [rbp+var_10]
0x18001bd09  cmp     qword ptr [rbp+FileSize], rax
0x18001bd0d  jz      short loc_18001BD18
0x18001bd0f  and     [r13+0], edi
0x18001bd13  jmp     loc_18001BE3D
0x18001bd18  mov     esi, 100000h
0x18001bd1d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001bd24  mov     ecx, esi; unsigned __int64
0x18001bd26  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001bd2b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001bd32  mov     ecx, esi; unsigned __int64
0x18001bd34  mov     r14, rax
0x18001bd37  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001bd3c  mov     r15, rax
0x18001bd3f  test    r14, r14
0x18001bd42  jz      loc_18001BE2B
0x18001bd48  test    rax, rax
0x18001bd4b  jz      loc_18001BE2B
0x18001bd51  mov     rbx, [rbp+var_18]
0x18001bd55  mov     rcx, qword ptr [rbp+FileSize]
0x18001bd59  cmp     rbx, rcx
0x18001bd5c  jge     loc_18001BE21
0x18001bd62  sub     rcx, rbx
0x18001bd65  cmp     rcx, rsi
0x18001bd68  jg      short loc_18001BD70
0x18001bd6a  mov     esi, dword ptr [rbp+FileSize]
0x18001bd6d  sub     esi, dword ptr [rbp+var_18]
0x18001bd70  mov     rcx, [rbp+hFile]; hFile
0x18001bd74  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001bd78  and     qword ptr [rsp+60h+dwCreationDisposition], rdi
0x18001bd7d  mov     r8d, esi; nNumberOfBytesToRead
0x18001bd80  mov     rdx, r14; lpBuffer
0x18001bd83  call    cs:__imp_ReadFile
0x18001bd8a  nop     dword ptr [rax+rax+00h]
0x18001bd8f  test    eax, eax
0x18001bd91  jz      short loc_18001BE0B
0x18001bd93  and     qword ptr [rsp+60h+dwCreationDisposition], rdi
0x18001bd98  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001bd9c  mov     r8d, esi; nNumberOfBytesToRead
0x18001bd9f  mov     rdx, r15; lpBuffer
0x18001bda2  mov     rcx, r12; hFile
0x18001bda5  call    cs:__imp_ReadFile
0x18001bdac  nop     dword ptr [rax+rax+00h]
0x18001bdb1  test    eax, eax
0x18001bdb3  jz      short loc_18001BDF5
0x18001bdb5  xor     edx, edx
0x18001bdb7  test    esi, esi
0x18001bdb9  jz      short loc_18001BDD9
0x18001bdbb  mov     r8, r15
0x18001bdbe  mov     rcx, r14
0x18001bdc1  sub     r8, r14
0x18001bdc4  mov     al, [r8+rcx]
0x18001bdc8  cmp     [rcx], al
0x18001bdca  jnz     loc_18001BD0F
0x18001bdd0  inc     edx
0x18001bdd2  inc     rcx
0x18001bdd5  cmp     edx, esi
0x18001bdd7  jb      short loc_18001BDC4
0x18001bdd9  mov     rcx, qword ptr [rbp+FileSize]
0x18001bddd  mov     eax, esi
0x18001bddf  add     rbx, rax
0x18001bde2  mov     [rbp+var_18], rbx
0x18001bde6  cmp     rbx, rcx
0x18001bde9  jge     short loc_18001BE21
0x18001bdeb  mov     esi, 100000h
0x18001bdf0  jmp     loc_18001BD62
0x18001bdf5  call    cs:__imp_GetLastError
0x18001bdfc  nop     dword ptr [rax+rax+00h]
0x18001be01  mov     ecx, eax
0x18001be03  mov     r9d, 1238h
0x18001be09  jmp     short loc_18001BE36
0x18001be0b  call    cs:__imp_GetLastError
0x18001be12  nop     dword ptr [rax+rax+00h]
0x18001be17  mov     ecx, eax
0x18001be19  mov     r9d, 1232h
0x18001be1f  jmp     short loc_18001BE36
0x18001be21  mov     dword ptr [r13+0], 1
0x18001be29  jmp     short loc_18001BE3D
0x18001be2b  mov     ecx, 8
0x18001be30  mov     r9d, 1221h
0x18001be36  call    ElValidateWin32_8
0x18001be3b  mov     edi, eax
0x18001be3d  mov     rcx, [rbp+hFile]; hObject
0x18001be41  call    cs:__imp_CloseHandle
0x18001be48  nop     dword ptr [rax+rax+00h]
0x18001be4d  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x18001be51  jz      short loc_18001BE62
0x18001be53  mov     rcx, r12; hObject
0x18001be56  call    cs:__imp_CloseHandle
0x18001be5d  nop     dword ptr [rax+rax+00h]
0x18001be62  test    r14, r14
0x18001be65  jz      short loc_18001BE76
0x18001be67  mov     rcx, r14
0x18001be6a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001be71  nop     dword ptr [rax+rax+00h]
0x18001be76  test    r15, r15
0x18001be79  jz      short loc_18001BE8A
0x18001be7b  mov     rcx, r15
0x18001be7e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001be85  nop     dword ptr [rax+rax+00h]
0x18001be8a  lea     r11, [rsp+60h+var_s0]
0x18001be8f  mov     eax, edi
0x18001be91  mov     rbx, [r11+30h]
0x18001be95  mov     rsi, [r11+38h]
0x18001be99  mov     rdi, [r11+40h]
0x18001be9d  mov     rsp, r11
0x18001bea0  pop     r15
0x18001bea2  pop     r14
0x18001bea4  pop     r13
0x18001bea6  pop     r12
0x18001bea8  pop     rbp
0x18001bea9  retn
```
