# SdpGetFullPath(ushort const *,ushort * *,ushort * *)

- ea: `0x18002708c`
- end: `0x1800271e4`
- name: `?SdpGetFullPath@@YAJPEBGPEAPEAG1@Z`
- size: `344`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `8`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800034c4`
- `0x180007bc0`
- `0x180007f0c`
- `0x180008184`
- `0x18000c3fc`
- `0x1800101cc`
- `0x18001d544`
- `0x18002758c`

## callees

- `0x1800012a4`
- `0x1800012b0`
- `0x180026fa0`
- `0x18002708c`
- `0x180027b7c`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x180027150`
- `KERNEL32!GetFullPathNameW` at `0x180027150`
- `KERNEL32!GetLastError` at `0x18002715a`
- `KERNEL32!GetLastError` at `0x18002715a`

## string_xrefs

- `0x1800270c2`: `SdpGetFullPath`
- `0x180027106`: `SdpGetFullPath`

## pseudocode

```c
__int64 __fastcall SdpGetFullPath(const unsigned __int16 *a1, unsigned __int16 **a2, unsigned __int16 **a3)
{
  int v5; // r8d
  unsigned int v6; // ebx
  int v7; // eax
  unsigned __int16 *v8; // rdi
  int v9; // r9d
  int v10; // r8d
  WCHAR *v11; // rax
  DWORD FullPathNameW; // eax
  signed int LastError; // eax
  LPCWSTR lpFileName; // [rsp+40h] [rbp+8h] BYREF
  LPWSTR FilePart; // [rsp+58h] [rbp+20h] BYREF

  lpFileName = 0;
  FilePart = 0;
  if ( !a1 )
  {
    v5 = 1887;
LABEL_3:
    v6 = -2147024809;
    SdpDebugTrace(1u, L"SdpGetFullPath", v5, -2147024809);
    return v6;
  }
  if ( !a2 )
  {
    v5 = 1888;
    goto LABEL_3;
  }
  v7 = SdpStrExpand((unsigned __int16 **)&lpFileName, a1);
  v6 = v7;
  if ( v7 >= 0 )
  {
    v11 = (WCHAR *)operator new[](0x208u);
    v8 = v11;
    if ( v11 )
    {
      FullPathNameW = GetFullPathNameW(lpFileName, 0x104u, v11, &FilePart);
      if ( FullPathNameW )
      {
        if ( FullPathNameW <= 0x104 )
        {
          *a2 = v8;
          v8 = 0;
          if ( a3 )
          {
            *a3 = FilePart;
            FilePart = 0;
          }
          goto LABEL_21;
        }
        v6 = -2147024785;
        v10 = 1901;
        v9 = -2147024785;
      }
      else
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        v10 = 1897;
        if ( (v6 & 0x80000000) == 0 )
          v6 = -2147467259;
        v9 = v6;
      }
    }
    else
    {
      v6 = -2147024882;
      v10 = 1894;
      v9 = -2147024882;
    }
  }
  else
  {
    v8 = 0;
    v9 = v7;
    v10 = 1891;
  }
  SdpDebugTrace(1u, L"SdpGetFullPath", v10, v9);
LABEL_21:
  if ( lpFileName )
    operator delete((void *)lpFileName);
  if ( v8 )
    operator delete(v8);
  return v6;
}

```

## disassembly

```asm
0x18002708c  mov     [rsp+arg_8], rbx
0x180027091  push    rsi
0x180027092  push    rdi
0x180027093  push    r14
0x180027095  sub     rsp, 20h
0x180027099  mov     [rsp+38h+lpFileName], 0
0x1800270a2  mov     r14, r8
0x1800270a5  mov     [rsp+38h+FilePart], 0
0x1800270ae  mov     rsi, rdx
0x1800270b1  test    rcx, rcx
0x1800270b4  jnz     short loc_1800270DB
0x1800270b6  mov     r8d, 75Fh; int
0x1800270bc  mov     r9d, 80070057h; int
0x1800270c2  lea     rdx, aSdpgetfullpath; "SdpGetFullPath"
0x1800270c9  mov     ecx, 1; Level
0x1800270ce  mov     ebx, r9d
0x1800270d1  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800270d6  jmp     loc_1800271D4
0x1800270db  test    rsi, rsi
0x1800270de  jnz     short loc_1800270E8
0x1800270e0  mov     r8d, 760h
0x1800270e6  jmp     short loc_1800270BC
0x1800270e8  mov     rdx, rcx; unsigned __int16 *
0x1800270eb  lea     rcx, [rsp+38h+lpFileName]; unsigned __int16 **
0x1800270f0  call    ?SdpStrExpand@@YAJPEAPEAGPEBG@Z; SdpStrExpand(ushort * *,ushort const *)
0x1800270f5  mov     ebx, eax
0x1800270f7  test    eax, eax
0x1800270f9  jns     short loc_18002711C
0x1800270fb  xor     edi, edi
0x1800270fd  mov     r9d, eax; int
0x180027100  mov     r8d, 763h; int
0x180027106  lea     rdx, aSdpgetfullpath; "SdpGetFullPath"
0x18002710d  mov     ecx, 1; Level
0x180027112  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180027117  jmp     loc_1800271B5
0x18002711c  mov     ecx, 208h; unsigned __int64
0x180027121  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180027126  mov     rdi, rax
0x180027129  test    rax, rax
0x18002712c  jnz     short loc_18002713E
0x18002712e  mov     ebx, 8007000Eh
0x180027133  mov     r8d, 766h
0x180027139  mov     r9d, ebx
0x18002713c  jmp     short loc_180027106
0x18002713e  mov     rcx, [rsp+38h+lpFileName]; lpFileName
0x180027143  lea     r9, [rsp+38h+FilePart]; lpFilePart
0x180027148  mov     r8, rdi; lpBuffer
0x18002714b  mov     edx, 104h; nBufferLength
0x180027150  call    cs:__imp_GetFullPathNameW
0x180027156  test    eax, eax
0x180027158  jnz     short loc_180027184
0x18002715a  call    cs:__imp_GetLastError
0x180027160  mov     ebx, eax
0x180027162  test    eax, eax
0x180027164  jle     short loc_18002716F
0x180027166  movzx   ebx, ax
0x180027169  or      ebx, 80070000h
0x18002716f  test    ebx, ebx
0x180027171  mov     eax, 80004005h
0x180027176  mov     r8d, 769h
0x18002717c  cmovns  ebx, eax
0x18002717f  mov     r9d, ebx
0x180027182  jmp     short loc_180027106
0x180027184  cmp     eax, 104h
0x180027189  jbe     short loc_18002719E
0x18002718b  mov     ebx, 8007006Fh
0x180027190  mov     r8d, 76Dh
0x180027196  mov     r9d, ebx
0x180027199  jmp     loc_180027106
0x18002719e  mov     [rsi], rdi
0x1800271a1  xor     edi, edi
0x1800271a3  test    r14, r14
0x1800271a6  jz      short loc_1800271B5
0x1800271a8  mov     rax, [rsp+38h+FilePart]
0x1800271ad  mov     [r14], rax
0x1800271b0  mov     [rsp+38h+FilePart], rdi
0x1800271b5  cmp     [rsp+38h+lpFileName], 0
0x1800271bb  jz      short loc_1800271C7
0x1800271bd  mov     rcx, [rsp+38h+lpFileName]; Block
0x1800271c2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800271c7  test    rdi, rdi
0x1800271ca  jz      short loc_1800271D4
0x1800271cc  mov     rcx, rdi; Block
0x1800271cf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800271d4  mov     eax, ebx
0x1800271d6  mov     rbx, [rsp+38h+arg_8]
0x1800271db  add     rsp, 20h
0x1800271df  pop     r14
0x1800271e1  pop     rdi
0x1800271e2  pop     rsi
0x1800271e3  retn
```
