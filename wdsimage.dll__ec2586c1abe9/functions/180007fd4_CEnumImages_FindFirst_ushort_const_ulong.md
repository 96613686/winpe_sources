# CEnumImages::FindFirst(ushort const *,ulong)

- ea: `0x180007fd4`
- end: `0x1800081b2`
- name: `?FindFirst@CEnumImages@@QEAAJPEBGK@Z`
- size: `478`
- prototype: `__int64 __fastcall(CEnumImages *__hidden this, LPCWSTR lpFileName, unsigned int)`
- caller_count: `7`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180007d60`
- `0x180007ec8`
- `0x180008820`
- `0x180008a10`
- `0x1800096c0`
- `0x18000a570`
- `0x18000b8b0`

## callees

- `0x180007934`
- `0x180007fd4`
- `0x1800081b8`
- `0x18000844c`
- `0x1800086e4`
- `0x180008748`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000818e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000818e`
- `KERNEL32!GetFileAttributesW` at `0x18000802a`
- `KERNEL32!GetFileAttributesW` at `0x18000802a`
- `KERNEL32!GetLastError` at `0x18000803b`
- `KERNEL32!GetLastError` at `0x18000803b`
- `WdsCommonLib!WdsGetParentFolderPathOfFile` at `0x1800080f7`
- `WdsCommonLib!WdsGetParentFolderPathOfFile` at `0x1800080f7`
- `WdsCommonLib!GetFileNameFromPath` at `0x1800080bd`
- `WdsCommonLib!GetFileNameFromPath` at `0x1800080bd`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x18000807b`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x1800080d0`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x18000807b`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x1800080d0`

## pseudocode

```c
__int64 __fastcall CEnumImages::FindFirst(CEnumImages *this, unsigned __int16 *lpFileName, int a3)
{
  int v5; // eax
  DWORD FileAttributesW; // eax
  signed int LastError; // eax
  unsigned int ParentFolderPathOfFile; // ebx
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned __int16 *v11; // rdx
  const unsigned __int16 *FileNameFromPath; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // r8
  int Next; // eax
  unsigned __int16 *v21; // [rsp+48h] [rbp+10h] BYREF

  v21 = 0;
  if ( !lpFileName || !*lpFileName || (a3 & 0xFFFFF800) != 0 )
  {
    ParentFolderPathOfFile = -2147024809;
    goto LABEL_24;
  }
  v5 = a3 | 0x206;
  if ( (a3 & 0x206) != 0 )
    v5 = a3;
  *((_DWORD *)this + 12) = v5;
  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW != -1 )
  {
    if ( (FileAttributesW & 0x10) != 0 )
    {
      ParentFolderPathOfFile = DuplicateStringW(L"*", (unsigned __int16 **)this + 7);
      if ( (unsigned int)ElValidateWin32_3(ParentFolderPathOfFile, v9, v10, 98) )
        goto LABEL_13;
      v11 = lpFileName;
      v21 = lpFileName;
    }
    else
    {
      FileNameFromPath = (const unsigned __int16 *)GetFileNameFromPath(lpFileName);
      ParentFolderPathOfFile = DuplicateStringW(FileNameFromPath, (unsigned __int16 **)this + 7);
      if ( (unsigned int)ElValidateWin32_3(ParentFolderPathOfFile, v13, v14, 106)
        || (ParentFolderPathOfFile = WdsGetParentFolderPathOfFile(lpFileName, &v21),
            (unsigned int)ElValidateWin32_3(ParentFolderPathOfFile, v15, v16, 109)) )
      {
LABEL_13:
        if ( (int)ParentFolderPathOfFile > 0 )
          ParentFolderPathOfFile = (unsigned __int16)ParentFolderPathOfFile | 0x80070000;
        goto LABEL_24;
      }
      v11 = v21;
    }
    ParentFolderPathOfFile = CEnumImages::Search(this, v11);
    if ( (int)ElValidateHr_4(ParentFolderPathOfFile, v17, v18, 116) < 0 )
      goto LABEL_24;
    if ( !*((_DWORD *)this + 9) )
      goto LABEL_10;
    Next = CEnumImages::FindNext(this);
    ParentFolderPathOfFile = Next;
    if ( Next < 0 )
      ElValidateHrWithExceptions(
        Next,
        (unsigned int)&word_180013F66,
        (unsigned int)"base\\eco\\wds\\wdsimage\\src\\enumimages.cpp",
        133,
        1,
        3);
    goto LABEL_24;
  }
  LastError = GetLastError();
  ParentFolderPathOfFile = LastError;
  if ( LastError > 0 )
    ParentFolderPathOfFile = (unsigned __int16)LastError | 0x80070000;
  if ( ParentFolderPathOfFile == -2147024894 )
LABEL_10:
    ParentFolderPathOfFile = -1056833013;
LABEL_24:
  if ( lpFileName != v21 && v21 )
    operator delete(v21);
  return ParentFolderPathOfFile;
}

```

## disassembly

```asm
0x180007fd4  mov     rax, rsp
0x180007fd7  mov     [rax+8], rbx
0x180007fdb  mov     [rax+18h], rbp
0x180007fdf  mov     [rax+20h], rsi
0x180007fe3  push    rdi
0x180007fe4  sub     rsp, 30h
0x180007fe8  xor     ebp, ebp
0x180007fea  mov     rdi, rdx
0x180007fed  mov     [rax+10h], rbp
0x180007ff1  mov     rsi, rcx
0x180007ff4  test    rdx, rdx
0x180007ff7  jz      loc_18000817A
0x180007ffd  cmp     [rdx], bp
0x180008000  jz      loc_18000817A
0x180008006  test    r8d, 0FFFFF800h
0x18000800d  jnz     loc_18000817A
0x180008013  mov     edx, 206h
0x180008018  mov     eax, r8d
0x18000801b  or      eax, edx
0x18000801d  test    edx, r8d
0x180008020  cmovnz  eax, r8d
0x180008024  mov     [rcx+30h], eax
0x180008027  mov     rcx, rdi; lpFileName
0x18000802a  call    cs:__imp_GetFileAttributesW
0x180008031  nop     dword ptr [rax+rax+00h]
0x180008036  cmp     eax, 0FFFFFFFFh
0x180008039  jnz     short loc_18000806C
0x18000803b  call    cs:__imp_GetLastError
0x180008042  nop     dword ptr [rax+rax+00h]
0x180008047  mov     ebx, eax
0x180008049  test    eax, eax
0x18000804b  jle     short loc_180008056
0x18000804d  movzx   ebx, ax
0x180008050  or      ebx, 80070000h
0x180008056  cmp     ebx, 80070002h
0x18000805c  jnz     loc_18000817F
0x180008062  mov     ebx, 0C102020Bh
0x180008067  jmp     loc_18000817F
0x18000806c  test    al, 10h
0x18000806e  jz      short loc_1800080BA
0x180008070  lea     rdx, [rsi+38h]
0x180008074  lea     rcx, asc_1800140D4; "*"
0x18000807b  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x180008082  nop     dword ptr [rax+rax+00h]
0x180008087  mov     ecx, eax
0x180008089  mov     r9d, 62h ; 'b'
0x18000808f  mov     ebx, eax
0x180008091  call    ElValidateWin32_3
0x180008096  test    eax, eax
0x180008098  jz      short loc_1800080B0
0x18000809a  test    ebx, ebx
0x18000809c  jle     loc_18000817F
0x1800080a2  movzx   ebx, bx
0x1800080a5  or      ebx, 80070000h
0x1800080ab  jmp     loc_18000817F
0x1800080b0  mov     rdx, rdi
0x1800080b3  mov     [rsp+38h+arg_8], rdx
0x1800080b8  jmp     short loc_18000811B
0x1800080ba  mov     rcx, rdi
0x1800080bd  call    cs:__imp_GetFileNameFromPath
0x1800080c4  nop     dword ptr [rax+rax+00h]
0x1800080c9  mov     rcx, rax
0x1800080cc  lea     rdx, [rsi+38h]
0x1800080d0  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x1800080d7  nop     dword ptr [rax+rax+00h]
0x1800080dc  mov     ecx, eax
0x1800080de  mov     r9d, 6Ah ; 'j'
0x1800080e4  mov     ebx, eax
0x1800080e6  call    ElValidateWin32_3
0x1800080eb  test    eax, eax
0x1800080ed  jnz     short loc_18000809A
0x1800080ef  lea     rdx, [rsp+38h+arg_8]
0x1800080f4  mov     rcx, rdi
0x1800080f7  call    cs:__imp_WdsGetParentFolderPathOfFile
0x1800080fe  nop     dword ptr [rax+rax+00h]
0x180008103  mov     ecx, eax
0x180008105  mov     r9d, 6Dh ; 'm'
0x18000810b  mov     ebx, eax
0x18000810d  call    ElValidateWin32_3
0x180008112  test    eax, eax
0x180008114  jnz     short loc_18000809A
0x180008116  mov     rdx, [rsp+38h+arg_8]; unsigned __int16 *
0x18000811b  mov     rcx, rsi; this
0x18000811e  call    ?Search@CEnumImages@@AEAAJPEBG@Z; CEnumImages::Search(ushort const *)
0x180008123  mov     r9d, 74h ; 't'
0x180008129  mov     ecx, eax
0x18000812b  mov     ebx, eax
0x18000812d  call    ElValidateHr_4
0x180008132  test    eax, eax
0x180008134  js      short loc_18000817F
0x180008136  cmp     [rsi+24h], ebp
0x180008139  jz      loc_180008062
0x18000813f  mov     rcx, rsi; this
0x180008142  call    ?FindNext@CEnumImages@@QEAAJXZ; CEnumImages::FindNext(void)
0x180008147  mov     ebx, eax
0x180008149  test    eax, eax
0x18000814b  jns     short loc_18000817F
0x18000814d  mov     [rsp+38h+var_10], 0C1020203h
0x180008155  lea     r8, aBaseEcoWdsWdsi_6; "base\\eco\\wds\\wdsimage\\src\\enumimag"...
0x18000815c  mov     r9d, 85h
0x180008162  mov     [rsp+38h+var_18], 1
0x18000816a  lea     rdx, word_180013F66
0x180008171  mov     ecx, eax
0x180008173  call    ElValidateHrWithExceptions
0x180008178  jmp     short loc_18000817F
0x18000817a  mov     ebx, 80070057h
0x18000817f  mov     rcx, [rsp+38h+arg_8]
0x180008184  cmp     rdi, rcx
0x180008187  jz      short loc_18000819A
0x180008189  test    rcx, rcx
0x18000818c  jz      short loc_18000819A
0x18000818e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008195  nop     dword ptr [rax+rax+00h]
0x18000819a  mov     rbp, [rsp+38h+arg_10]
0x18000819f  mov     eax, ebx
0x1800081a1  mov     rbx, [rsp+38h+arg_0]
0x1800081a6  mov     rsi, [rsp+38h+arg_18]
0x1800081ab  add     rsp, 30h
0x1800081af  pop     rdi
0x1800081b0  retn
```
