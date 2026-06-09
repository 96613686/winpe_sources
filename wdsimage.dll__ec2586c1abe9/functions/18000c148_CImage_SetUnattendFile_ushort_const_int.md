# CImage::SetUnattendFile(ushort const *,int)

- ea: `0x18000c148`
- end: `0x18000c2d2`
- name: `?SetUnattendFile@CImage@@QEAAJPEBGH@Z`
- size: `394`
- prototype: `int(CImage *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005fe0`

## callees

- `0x18000c148`
- `0x18000d5b0`
- `0x18000d6b0`
- `0x18000eb44`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000c2ae`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c2ae`
- `KERNEL32!CopyFileW` at `0x18000c263`
- `KERNEL32!CopyFileW` at `0x18000c263`
- `KERNEL32!GetFileAttributesW` at `0x18000c197`
- `KERNEL32!GetFileAttributesW` at `0x18000c201`
- `KERNEL32!GetFileAttributesW` at `0x18000c197`
- `KERNEL32!GetFileAttributesW` at `0x18000c201`
- `KERNEL32!GetLastError` at `0x18000c220`
- `KERNEL32!GetLastError` at `0x18000c273`
- `KERNEL32!GetLastError` at `0x18000c220`
- `KERNEL32!GetLastError` at `0x18000c273`
- `WdsCommonLib!WdsGetParentFolderPathOfFile` at `0x18000c1d2`
- `WdsCommonLib!WdsGetParentFolderPathOfFile` at `0x18000c1d2`

## pseudocode

```c
__int64 __fastcall CImage::SetUnattendFile(CImage *this, const unsigned __int16 *a2, int a3)
{
  unsigned int ParentFolderPathOfFile; // ebx
  __int64 v7; // rdx
  __int64 v8; // rdx
  DWORD v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // eax
  DWORD LastError; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  signed int v16; // eax
  LPCWSTR lpFileName; // [rsp+30h] [rbp+8h] BYREF

  lpFileName = 0;
  if ( *((_DWORD *)this + 80) > 5u
    || (ParentFolderPathOfFile = -1056833006,
        (int)ElValidateHr_5(3238134290LL, a2, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 1493) >= 0) )
  {
    if ( GetFileAttributesW(a2) != -1
      || (ParentFolderPathOfFile = -2147024894,
          (int)ElValidateHr_5(2147942402LL, v7, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 1502) >= 0) )
    {
      ParentFolderPathOfFile = WdsGetParentFolderPathOfFile(*((_QWORD *)this + 13), &lpFileName);
      if ( (int)ElValidateHr_5(ParentFolderPathOfFile, v8, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 1509) >= 0 )
      {
        if ( GetFileAttributesW(lpFileName) != -1 || (unsigned int)CreatePath(lpFileName) )
        {
          if ( !CopyFileW(a2, *((LPCWSTR *)this + 13), a3 == 0) )
          {
            LastError = GetLastError();
            v16 = ElValidateWin32_4(LastError, v14, v15, 1526);
            if ( v16 > 0 )
              v16 = (unsigned __int16)v16 | 0x80070000;
            if ( v16 >= 0 )
              v16 = -2147467259;
            ParentFolderPathOfFile = v16;
          }
        }
        else
        {
          v9 = GetLastError();
          v12 = ElValidateWin32_4(v9, v10, v11, 1515);
          ParentFolderPathOfFile = v12;
          if ( v12 > 0 )
            ParentFolderPathOfFile = (unsigned __int16)v12 | 0x80070000;
          if ( (ParentFolderPathOfFile & 0x80000000) == 0 )
            ParentFolderPathOfFile = -2147467259;
        }
      }
    }
  }
  if ( lpFileName )
    operator delete((void *)lpFileName);
  return ParentFolderPathOfFile;
}

```

## disassembly

```asm
0x18000c148  mov     rax, rsp
0x18000c14b  mov     [rax+10h], rbx
0x18000c14f  mov     [rax+18h], rbp
0x18000c153  mov     [rax+20h], rsi
0x18000c157  push    rdi
0x18000c158  sub     rsp, 20h
0x18000c15c  and     qword ptr [rax+8], 0
0x18000c161  mov     ebp, r8d
0x18000c164  cmp     dword ptr [rcx+140h], 5
0x18000c16b  mov     rsi, rdx
0x18000c16e  mov     rdi, rcx
0x18000c171  ja      short loc_18000C194
0x18000c173  mov     ebx, 0C1020212h
0x18000c178  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000c17f  mov     ecx, ebx
0x18000c181  mov     r9d, 5D5h
0x18000c187  call    ElValidateHr_5
0x18000c18c  test    eax, eax
0x18000c18e  js      loc_18000C2A4
0x18000c194  mov     rcx, rsi; lpFileName
0x18000c197  call    cs:__imp_GetFileAttributesW
0x18000c19e  nop     dword ptr [rax+rax+00h]
0x18000c1a3  cmp     eax, 0FFFFFFFFh
0x18000c1a6  jnz     short loc_18000C1C9
0x18000c1a8  mov     ebx, 80070002h
0x18000c1ad  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000c1b4  mov     ecx, ebx
0x18000c1b6  mov     r9d, 5DEh
0x18000c1bc  call    ElValidateHr_5
0x18000c1c1  test    eax, eax
0x18000c1c3  js      loc_18000C2A4
0x18000c1c9  mov     rcx, [rdi+68h]
0x18000c1cd  lea     rdx, [rsp+28h+lpFileName]
0x18000c1d2  call    cs:__imp_WdsGetParentFolderPathOfFile
0x18000c1d9  nop     dword ptr [rax+rax+00h]
0x18000c1de  mov     r9d, 5E5h
0x18000c1e4  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000c1eb  mov     ecx, eax
0x18000c1ed  mov     ebx, eax
0x18000c1ef  call    ElValidateHr_5
0x18000c1f4  test    eax, eax
0x18000c1f6  js      loc_18000C2A4
0x18000c1fc  mov     rcx, [rsp+28h+lpFileName]; lpFileName
0x18000c201  call    cs:__imp_GetFileAttributesW
0x18000c208  nop     dword ptr [rax+rax+00h]
0x18000c20d  cmp     eax, 0FFFFFFFFh
0x18000c210  jnz     short loc_18000C253
0x18000c212  mov     rcx, [rsp+28h+lpFileName]
0x18000c217  call    CreatePath
0x18000c21c  test    eax, eax
0x18000c21e  jnz     short loc_18000C253
0x18000c220  call    cs:__imp_GetLastError
0x18000c227  nop     dword ptr [rax+rax+00h]
0x18000c22c  mov     ecx, eax
0x18000c22e  mov     r9d, 5EBh
0x18000c234  call    ElValidateWin32_4
0x18000c239  mov     ebx, eax
0x18000c23b  test    eax, eax
0x18000c23d  jle     short loc_18000C248
0x18000c23f  movzx   ebx, ax
0x18000c242  or      ebx, 80070000h
0x18000c248  test    ebx, ebx
0x18000c24a  js      short loc_18000C2A4
0x18000c24c  mov     ebx, 80004005h
0x18000c251  jmp     short loc_18000C2A4
0x18000c253  mov     rdx, [rdi+68h]; lpNewFileName
0x18000c257  xor     r8d, r8d
0x18000c25a  test    ebp, ebp
0x18000c25c  mov     rcx, rsi; lpExistingFileName
0x18000c25f  setz    r8b; bFailIfExists
0x18000c263  call    cs:__imp_CopyFileW
0x18000c26a  nop     dword ptr [rax+rax+00h]
0x18000c26f  test    eax, eax
0x18000c271  jnz     short loc_18000C2A4
0x18000c273  call    cs:__imp_GetLastError
0x18000c27a  nop     dword ptr [rax+rax+00h]
0x18000c27f  mov     ecx, eax
0x18000c281  mov     r9d, 5F6h
0x18000c287  call    ElValidateWin32_4
0x18000c28c  test    eax, eax
0x18000c28e  jle     short loc_18000C298
0x18000c290  movzx   eax, ax
0x18000c293  or      eax, 80070000h
0x18000c298  mov     ebx, 80004005h
0x18000c29d  test    eax, eax
0x18000c29f  cmovns  eax, ebx
0x18000c2a2  mov     ebx, eax
0x18000c2a4  mov     rcx, [rsp+28h+lpFileName]
0x18000c2a9  test    rcx, rcx
0x18000c2ac  jz      short loc_18000C2BA
0x18000c2ae  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c2b5  nop     dword ptr [rax+rax+00h]
0x18000c2ba  mov     rbp, [rsp+28h+arg_10]
0x18000c2bf  mov     eax, ebx
0x18000c2c1  mov     rbx, [rsp+28h+arg_8]
0x18000c2c6  mov     rsi, [rsp+28h+arg_18]
0x18000c2cb  add     rsp, 20h
0x18000c2cf  pop     rdi
0x18000c2d0  retn
```
