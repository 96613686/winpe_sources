# SdpVerifyDirectoryTrust(ushort const *,ushort const *)

- ea: `0x180007bc0`
- end: `0x180007f04`
- name: `?SdpVerifyDirectoryTrust@@YAJPEBG0@Z`
- size: `836`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180011ba4`

## callees

- `0x1800012a4`
- `0x1800012b0`
- `0x180002978`
- `0x1800066f8`
- `0x18000787c`
- `0x180007bc0`
- `0x180007f0c`
- `0x180008184`
- `0x180026fa0`
- `0x18002708c`
- `0x180029882`
- `0x1800298c0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180007d47`
- `msvcrt!_wcsicmp` at `0x180007d61`
- `msvcrt!_wcsicmp` at `0x180007d7f`
- `msvcrt!_wcsicmp` at `0x180007d47`
- `msvcrt!_wcsicmp` at `0x180007d61`
- `msvcrt!_wcsicmp` at `0x180007d7f`
- `KERNEL32!FindFirstFileW` at `0x180007d24`
- `KERNEL32!FindFirstFileW` at `0x180007d24`
- `KERNEL32!FindClose` at `0x180007e57`
- `KERNEL32!FindClose` at `0x180007e57`
- `KERNEL32!FindNextFileW` at `0x180007df2`
- `KERNEL32!FindNextFileW` at `0x180007df2`
- `KERNEL32!GetProcessHeap` at `0x180007ea4`
- `KERNEL32!GetProcessHeap` at `0x180007ea4`
- `KERNEL32!HeapFree` at `0x180007eb2`
- `KERNEL32!HeapFree` at `0x180007eb2`

## string_xrefs

- `0x180007c2b`: `SdpVerifyDirectoryTrust`
- `0x180007c85`: `SdpVerifyDirectoryTrust`
- `0x180007cd7`: `SdpVerifyDirectoryTrust`
- `0x180007e24`: `SdpVerifyDirectoryTrust`

## pseudocode

```c
__int64 __fastcall SdpVerifyDirectoryTrust(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  unsigned __int16 *v4; // rdi
  unsigned __int16 *v5; // r14
  unsigned int v6; // ebx
  char *FirstFileW; // r15
  int FullPath; // eax
  int v9; // r8d
  unsigned __int16 *v10; // rax
  WCHAR *v11; // rsi
  int v12; // eax
  int v13; // r8d
  _QWORD *v14; // rdi
  __int64 v15; // rax
  void *v16; // rcx
  HANDLE ProcessHeap; // rax
  LPVOID lpMem[2]; // [rsp+30h] [rbp-D0h] BYREF
  void *Block; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v21; // [rsp+48h] [rbp-B8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF

  v4 = 0;
  v5 = 0;
  Block = 0;
  v21 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  *(_OWORD *)lpMem = 0;
  if ( !a1 )
  {
    v6 = -2147024809;
    SdpDebugTrace(1u, L"SdpVerifyDirectoryTrust", 279, -2147024809);
    goto LABEL_35;
  }
  FirstFileW = 0;
  lpMem[1] = lpMem;
  lpMem[0] = lpMem;
  if ( !a2 )
    goto LABEL_10;
  FullPath = SdpGetFullPath(a2, (unsigned __int16 **)&Block, &v21);
  v6 = FullPath;
  if ( FullPath >= 0 )
  {
    FullPath = SdpVerifyTrust(a2);
    v6 = FullPath;
    if ( FullPath < 0 )
    {
      v9 = 291;
      goto LABEL_6;
    }
    v4 = (unsigned __int16 *)Block;
    v5 = v21;
LABEL_10:
    v10 = (unsigned __int16 *)operator new[](0x208u);
    v11 = v10;
    if ( v10 )
    {
      v12 = StringCchPrintfW(v10, 0x104u, L"%s\\*", a1);
      v6 = v12;
      if ( v12 >= 0 )
      {
        FirstFileW = (char *)FindFirstFileW(v11, &FindFileData);
        if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          do
          {
            if ( _wcsicmp(FindFileData.cFileName, L".")
              && _wcsicmp(FindFileData.cFileName, L"..")
              && (FindFileData.dwFileAttributes & 0x10) == 0
              && (!v5 || _wcsicmp(FindFileData.cFileName, v5)) )
            {
              if ( v4 )
              {
                v12 = SdpAddFileToList((struct _LIST_ENTRY *)lpMem, FindFileData.cFileName);
                v6 = v12;
                if ( v12 < 0 )
                {
                  v13 = 346;
                  goto LABEL_29;
                }
              }
              else
              {
                v12 = StringCchPrintfW(v11, 0x104u, L"%s\\%s", a1, FindFileData.cFileName);
                v6 = v12;
                if ( v12 < 0 )
                {
                  v13 = 339;
                  goto LABEL_29;
                }
                v12 = SdpVerifyTrust(v11, 0);
                v6 = v12;
                if ( v12 < 0 )
                {
                  v13 = 342;
                  goto LABEL_29;
                }
              }
            }
          }
          while ( FindNextFileW(FirstFileW, &FindFileData) );
          if ( v4 )
          {
            v12 = SdpVerifyDirectoryIntegrity(a1, v4, (struct _LIST_ENTRY *)lpMem);
            v6 = v12;
            if ( v12 < 0 )
            {
              v13 = 357;
              goto LABEL_29;
            }
          }
        }
      }
      else
      {
        v13 = 298;
LABEL_29:
        SdpDebugTrace(1u, L"SdpVerifyDirectoryTrust", v13, v12);
      }
      operator delete(v11);
    }
    else
    {
      v6 = -2147024882;
      SdpDebugTrace(1u, L"SdpVerifyDirectoryTrust", 295, -2147024882);
    }
    goto LABEL_31;
  }
  v9 = 285;
LABEL_6:
  SdpDebugTrace(1u, L"SdpVerifyDirectoryTrust", v9, FullPath);
  v4 = (unsigned __int16 *)Block;
LABEL_31:
  if ( v4 )
    operator delete(v4);
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    FindClose(FirstFileW);
LABEL_35:
  while ( 1 )
  {
    v14 = lpMem[0];
    if ( lpMem[0] == lpMem )
      break;
    if ( *((LPVOID **)lpMem[0] + 1) != lpMem
      || (v15 = *(_QWORD *)lpMem[0], *(LPVOID *)(*(_QWORD *)lpMem[0] + 8LL) != lpMem[0]) )
    {
      __fastfail(3u);
    }
    lpMem[0] = *(LPVOID *)lpMem[0];
    *(_QWORD *)(v15 + 8) = lpMem;
    v16 = (void *)v14[2];
    if ( v16 )
    {
      operator delete(v16);
      v14[2] = 0;
    }
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v14);
  }
  return v6;
}

```

## disassembly

```asm
0x180007bc0  mov     [rsp-8+arg_10], rbx
0x180007bc5  mov     [rsp-8+arg_18], rsi
0x180007bca  push    rbp
0x180007bcb  push    rdi
0x180007bcc  push    r12
0x180007bce  push    r14
0x180007bd0  push    r15
0x180007bd2  lea     rbp, [rsp-1B0h]
0x180007bda  sub     rsp, 2B0h
0x180007be1  mov     rax, cs:__security_cookie
0x180007be8  xor     rax, rsp
0x180007beb  mov     [rbp+1D0h+var_30], rax
0x180007bf2  mov     rsi, rdx
0x180007bf5  mov     r12, rcx
0x180007bf8  xor     edi, edi
0x180007bfa  lea     rcx, [rsp+2D0h+FindFileData]; void *
0x180007bff  xor     r14d, r14d
0x180007c02  mov     [rsp+2D0h+Block], rdi
0x180007c07  xor     edx, edx; Val
0x180007c09  mov     [rsp+2D0h+var_288], r14
0x180007c0e  mov     r8d, 250h; Size
0x180007c14  call    memset_0
0x180007c19  xorps   xmm0, xmm0
0x180007c1c  movups  xmmword ptr [rsp+2D0h+lpMem], xmm0
0x180007c21  test    r12, r12
0x180007c24  jnz     short loc_180007C48
0x180007c26  mov     ebx, 80070057h
0x180007c2b  lea     rdx, aSdpverifydirec; "SdpVerifyDirectoryTrust"
0x180007c32  mov     r9d, ebx; int
0x180007c35  lea     ecx, [rdi+1]; Level
0x180007c38  mov     r8d, 117h; int
0x180007c3e  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180007c43  jmp     loc_180007E5D
0x180007c48  lea     rax, [rsp+2D0h+lpMem]
0x180007c4d  xor     r15d, r15d
0x180007c50  mov     [rsp+2D0h+lpMem+8], rax
0x180007c55  lea     rax, [rsp+2D0h+lpMem]
0x180007c5a  mov     [rsp+2D0h+lpMem], rax
0x180007c5f  test    rsi, rsi
0x180007c62  jz      short loc_180007CC0
0x180007c64  lea     r8, [rsp+2D0h+var_288]; unsigned __int16 **
0x180007c69  mov     rcx, rsi; unsigned __int16 *
0x180007c6c  lea     rdx, [rsp+2D0h+Block]; unsigned __int16 **
0x180007c71  call    ?SdpGetFullPath@@YAJPEBGPEAPEAG1@Z; SdpGetFullPath(ushort const *,ushort * *,ushort * *)
0x180007c76  mov     ebx, eax
0x180007c78  test    eax, eax
0x180007c7a  jns     short loc_180007CA0
0x180007c7c  mov     r8d, 11Dh; int
0x180007c82  mov     r9d, eax; int
0x180007c85  lea     rdx, aSdpverifydirec; "SdpVerifyDirectoryTrust"
0x180007c8c  mov     ecx, 1; Level
0x180007c91  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180007c96  mov     rdi, [rsp+2D0h+Block]
0x180007c9b  jmp     loc_180007E3D
0x180007ca0  mov     rcx, rsi; unsigned __int16 *
0x180007ca3  call    ?SdpVerifyTrust@@YAJPEBG@Z; SdpVerifyTrust(ushort const *)
0x180007ca8  mov     ebx, eax
0x180007caa  test    eax, eax
0x180007cac  jns     short loc_180007CB6
0x180007cae  mov     r8d, 123h
0x180007cb4  jmp     short loc_180007C82
0x180007cb6  mov     rdi, [rsp+2D0h+Block]
0x180007cbb  mov     r14, [rsp+2D0h+var_288]
0x180007cc0  mov     ecx, 208h; unsigned __int64
0x180007cc5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180007cca  mov     rsi, rax
0x180007ccd  test    rax, rax
0x180007cd0  jnz     short loc_180007CF4
0x180007cd2  mov     ebx, 8007000Eh
0x180007cd7  lea     rdx, aSdpverifydirec; "SdpVerifyDirectoryTrust"
0x180007cde  mov     r9d, ebx; int
0x180007ce1  lea     ecx, [rax+1]; Level
0x180007ce4  mov     r8d, 127h; int
0x180007cea  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180007cef  jmp     loc_180007E3D
0x180007cf4  mov     r9, r12
0x180007cf7  lea     r8, aS; "%s\\*"
0x180007cfe  mov     edx, 104h; unsigned __int64
0x180007d03  mov     rcx, rsi; unsigned __int16 *
0x180007d06  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007d0b  mov     ebx, eax
0x180007d0d  test    eax, eax
0x180007d0f  jns     short loc_180007D1C
0x180007d11  mov     r8d, 12Ah
0x180007d17  jmp     loc_180007E21
0x180007d1c  lea     rdx, [rsp+2D0h+FindFileData]; lpFindFileData
0x180007d21  mov     rcx, rsi; lpFileName
0x180007d24  call    cs:__imp_FindFirstFileW
0x180007d2a  mov     r15, rax
0x180007d2d  lea     rcx, [rax-1]
0x180007d31  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180007d35  ja      loc_180007E35
0x180007d3b  lea     rdx, String2; "."
0x180007d42  lea     rcx, [rsp+2D0h+FindFileData.cFileName]; String1
0x180007d47  call    cs:__imp__wcsicmp
0x180007d4d  test    eax, eax
0x180007d4f  jz      loc_180007DEA
0x180007d55  lea     rdx, asc_18002D4A0; ".."
0x180007d5c  lea     rcx, [rsp+2D0h+FindFileData.cFileName]; String1
0x180007d61  call    cs:__imp__wcsicmp
0x180007d67  test    eax, eax
0x180007d69  jz      short loc_180007DEA
0x180007d6b  test    byte ptr [rsp+2D0h+FindFileData.dwFileAttributes], 10h
0x180007d70  jnz     short loc_180007DEA
0x180007d72  test    r14, r14
0x180007d75  jz      short loc_180007D89
0x180007d77  mov     rdx, r14; String2
0x180007d7a  lea     rcx, [rsp+2D0h+FindFileData.cFileName]; String1
0x180007d7f  call    cs:__imp__wcsicmp
0x180007d85  test    eax, eax
0x180007d87  jz      short loc_180007DEA
0x180007d89  test    rdi, rdi
0x180007d8c  jnz     short loc_180007DD1
0x180007d8e  lea     rax, [rsp+2D0h+FindFileData.cFileName]
0x180007d93  mov     r9, r12
0x180007d96  lea     r8, aSS; "%s\\%s"
0x180007d9d  mov     [rsp+2D0h+var_2B0], rax
0x180007da2  mov     edx, 104h; unsigned __int64
0x180007da7  mov     rcx, rsi; unsigned __int16 *
0x180007daa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007daf  mov     ebx, eax
0x180007db1  test    eax, eax
0x180007db3  js      loc_180007EBA
0x180007db9  xor     edx, edx; unsigned __int16 *
0x180007dbb  mov     rcx, rsi; unsigned __int16 *
0x180007dbe  call    ?SdpVerifyTrust@@YAJPEBG0@Z; SdpVerifyTrust(ushort const *,ushort const *)
0x180007dc3  mov     ebx, eax
0x180007dc5  test    eax, eax
0x180007dc7  jns     short loc_180007DEA
0x180007dc9  mov     r8d, 156h
0x180007dcf  jmp     short loc_180007E21
0x180007dd1  lea     rdx, [rsp+2D0h+FindFileData.cFileName]; unsigned __int16 *
0x180007dd6  lea     rcx, [rsp+2D0h+lpMem]; struct _LIST_ENTRY *
0x180007ddb  call    ?SdpAddFileToList@@YAJPEAU_LIST_ENTRY@@PEBG@Z; SdpAddFileToList(_LIST_ENTRY *,ushort const *)
0x180007de0  mov     ebx, eax
0x180007de2  test    eax, eax
0x180007de4  js      loc_180007EC5
0x180007dea  lea     rdx, [rsp+2D0h+FindFileData]; lpFindFileData
0x180007def  mov     rcx, r15; hFindFile
0x180007df2  call    cs:__imp_FindNextFileW
0x180007df8  test    eax, eax
0x180007dfa  jnz     loc_180007D3B
0x180007e00  test    rdi, rdi
0x180007e03  jz      short loc_180007E35
0x180007e05  lea     r8, [rsp+2D0h+lpMem]; struct _LIST_ENTRY *
0x180007e0a  mov     rdx, rdi; unsigned __int16 *
0x180007e0d  mov     rcx, r12; unsigned __int16 *
0x180007e10  call    ?SdpVerifyDirectoryIntegrity@@YAJPEBG0PEAU_LIST_ENTRY@@@Z; SdpVerifyDirectoryIntegrity(ushort const *,ushort const *,_LIST_ENTRY *)
0x180007e15  mov     ebx, eax
0x180007e17  test    eax, eax
0x180007e19  jns     short loc_180007E35
0x180007e1b  mov     r8d, 165h; int
0x180007e21  mov     r9d, eax; int
0x180007e24  lea     rdx, aSdpverifydirec; "SdpVerifyDirectoryTrust"
0x180007e2b  mov     ecx, 1; Level
0x180007e30  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180007e35  mov     rcx, rsi; Block
0x180007e38  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007e3d  test    rdi, rdi
0x180007e40  jz      short loc_180007E4A
0x180007e42  mov     rcx, rdi; Block
0x180007e45  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007e4a  lea     rax, [r15-1]
0x180007e4e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007e52  ja      short loc_180007E5D
0x180007e54  mov     rcx, r15; hFindFile
0x180007e57  call    cs:__imp_FindClose
0x180007e5d  mov     rdi, [rsp+2D0h+lpMem]
0x180007e62  lea     rax, [rsp+2D0h+lpMem]
0x180007e67  cmp     rdi, rax
0x180007e6a  jz      short loc_180007ED7
0x180007e6c  lea     rax, [rsp+2D0h+lpMem]
0x180007e71  cmp     [rdi+8], rax
0x180007e75  jnz     short loc_180007ED0
0x180007e77  mov     rax, [rdi]
0x180007e7a  cmp     [rax+8], rdi
0x180007e7e  jnz     short loc_180007ED0
0x180007e80  lea     rcx, [rsp+2D0h+lpMem]
0x180007e85  mov     [rsp+2D0h+lpMem], rax
0x180007e8a  mov     [rax+8], rcx
0x180007e8e  mov     rcx, [rdi+10h]; Block
0x180007e92  test    rcx, rcx
0x180007e95  jz      short loc_180007EA4
0x180007e97  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007e9c  mov     qword ptr [rdi+10h], 0
0x180007ea4  call    cs:__imp_GetProcessHeap
0x180007eaa  mov     r8, rdi; lpMem
0x180007ead  xor     edx, edx; dwFlags
0x180007eaf  mov     rcx, rax; hHeap
0x180007eb2  call    cs:__imp_HeapFree
0x180007eb8  jmp     short loc_180007E5D
0x180007eba  mov     r8d, 153h
0x180007ec0  jmp     loc_180007E21
0x180007ec5  mov     r8d, 15Ah
0x180007ecb  jmp     loc_180007E21
0x180007ed0  mov     ecx, 3
0x180007ed5  int     29h; Win8: RtlFailFast(ecx)
0x180007ed7  mov     eax, ebx
0x180007ed9  mov     rcx, [rbp+1D0h+var_30]
0x180007ee0  xor     rcx, rsp; StackCookie
0x180007ee3  call    __security_check_cookie
0x180007ee8  lea     r11, [rsp+2D0h+var_20]
0x180007ef0  mov     rbx, [r11+40h]
0x180007ef4  mov     rsi, [r11+48h]
0x180007ef8  mov     rsp, r11
0x180007efb  pop     r15
0x180007efd  pop     r14
0x180007eff  pop     r12
0x180007f01  pop     rdi
0x180007f02  pop     rbp
0x180007f03  retn
```
