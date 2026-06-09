# CImageGroup::SetName(ushort const *)

- ea: `0x180006544`
- end: `0x18000670c`
- name: `?SetName@CImageGroup@@QEAAJPEBG@Z`
- size: `456`
- prototype: `__int64 __fastcall(CImageGroup *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006c60`

## callees

- `0x180006544`
- `0x180006714`
- `0x180006810`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006678`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000669a`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800066bc`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800066d6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800066f0`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006678`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000669a`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800066bc`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800066d6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800066f0`
- `KERNEL32!MoveFileW` at `0x180006637`
- `KERNEL32!MoveFileW` at `0x180006637`
- `KERNEL32!GetLastError` at `0x180006647`
- `KERNEL32!GetLastError` at `0x180006647`
- `WdsCommonLib!WdsGetParentFolderPathOfFolder` at `0x1800065ac`
- `WdsCommonLib!WdsGetParentFolderPathOfFolder` at `0x1800065ac`
- `WdsCommonLib!ConcatenatePaths` at `0x1800065fd`
- `WdsCommonLib!ConcatenatePaths` at `0x1800065fd`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x18000656f`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x18000656f`

## pseudocode

```c
__int64 __fastcall CImageGroup::SetName(CImageGroup *this, const unsigned __int16 *a2)
{
  __int64 ParentFolderPathOfFolder; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  void *v11; // rcx
  __int64 v12; // rsi
  __int64 v13; // rdx
  __int64 v14; // r8
  signed int LastError; // eax
  void *v16; // rcx
  unsigned __int16 *v17; // rax
  void *v18; // rcx
  LPCWSTR v19; // rax
  void *v21; // [rsp+20h] [rbp-10h] BYREF
  LPCWSTR lpNewFileName; // [rsp+60h] [rbp+30h] BYREF
  unsigned __int16 *v23; // [rsp+68h] [rbp+38h] BYREF

  v21 = 0;
  lpNewFileName = 0;
  v23 = 0;
  ParentFolderPathOfFolder = DuplicateStringW(a2, &v23);
  if ( (unsigned int)ElValidateWin32_0(ParentFolderPathOfFolder, v5, v6, 224) )
  {
    if ( (int)ParentFolderPathOfFolder <= 0 )
      goto LABEL_23;
    LODWORD(ParentFolderPathOfFolder) = (unsigned __int16)ParentFolderPathOfFolder;
    goto LABEL_4;
  }
  ParentFolderPathOfFolder = (unsigned int)WdsGetParentFolderPathOfFolder(*((_QWORD *)this + 4), &v21);
  if ( (int)ElValidateHr_1(ParentFolderPathOfFolder, v7, v8, 230) >= 0 )
  {
    v11 = v21;
    if ( !v21 )
    {
      LODWORD(ParentFolderPathOfFolder) = -2147024735;
      if ( (int)ElValidateHr_1(2147942561LL, v9, v10, 239) < 0 )
        goto LABEL_23;
      v11 = v21;
    }
    v12 = (unsigned int)ConcatenatePaths(v11, a2, &lpNewFileName);
    if ( (unsigned int)ElValidateWin32_0(v12, v13, v14, 243) )
    {
      if ( (int)v12 <= 0 )
      {
        LODWORD(ParentFolderPathOfFolder) = v12;
        goto LABEL_23;
      }
      LODWORD(ParentFolderPathOfFolder) = (unsigned __int16)v12;
LABEL_4:
      LODWORD(ParentFolderPathOfFolder) = ParentFolderPathOfFolder | 0x80070000;
      goto LABEL_23;
    }
    if ( MoveFileW(*((LPCWSTR *)this + 4), lpNewFileName) )
    {
      v16 = (void *)*((_QWORD *)this + 3);
      if ( v16 )
        operator delete(v16);
      v17 = v23;
      v23 = 0;
      v18 = (void *)*((_QWORD *)this + 4);
      *((_QWORD *)this + 3) = v17;
      if ( v18 )
        operator delete(v18);
      v19 = lpNewFileName;
      lpNewFileName = 0;
      *((_QWORD *)this + 4) = v19;
    }
    else
    {
      LastError = GetLastError();
      LODWORD(ParentFolderPathOfFolder) = LastError;
      if ( LastError == 183 )
      {
        LODWORD(ParentFolderPathOfFolder) = -1056833015;
      }
      else if ( LastError > 0 )
      {
        LODWORD(ParentFolderPathOfFolder) = (unsigned __int16)LastError;
        goto LABEL_4;
      }
    }
  }
LABEL_23:
  if ( v23 )
  {
    operator delete(v23);
    v23 = 0;
  }
  if ( lpNewFileName )
  {
    operator delete((void *)lpNewFileName);
    lpNewFileName = 0;
  }
  if ( v21 )
    operator delete(v21);
  return (unsigned int)ParentFolderPathOfFolder;
}

```

## disassembly

```asm
0x180006544  mov     [rsp-18h+arg_0], rbx
0x180006549  push    rbp
0x18000654a  push    rsi
0x18000654b  push    rdi
0x18000654c  mov     rbp, rsp
0x18000654f  sub     rsp, 30h
0x180006553  and     [rbp+var_10], 0
0x180006558  mov     rsi, rdx
0x18000655b  and     [rbp+lpNewFileName], 0
0x180006560  lea     rdx, [rbp+arg_18]
0x180006564  and     [rbp+arg_18], 0
0x180006569  mov     rdi, rcx
0x18000656c  mov     rcx, rsi
0x18000656f  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x180006576  nop     dword ptr [rax+rax+00h]
0x18000657b  mov     ecx, eax
0x18000657d  mov     r9d, 0E0h
0x180006583  mov     ebx, eax
0x180006585  call    ElValidateWin32_0
0x18000658a  test    eax, eax
0x18000658c  jz      short loc_1800065A4
0x18000658e  test    ebx, ebx
0x180006590  jle     loc_1800066B3
0x180006596  movzx   ebx, bx
0x180006599  or      ebx, 80070000h
0x18000659f  jmp     loc_1800066B3
0x1800065a4  mov     rcx, [rdi+20h]
0x1800065a8  lea     rdx, [rbp+var_10]
0x1800065ac  call    cs:__imp_WdsGetParentFolderPathOfFolder
0x1800065b3  nop     dword ptr [rax+rax+00h]
0x1800065b8  mov     ecx, eax
0x1800065ba  mov     r9d, 0E6h
0x1800065c0  mov     ebx, eax
0x1800065c2  call    ElValidateHr_1
0x1800065c7  test    eax, eax
0x1800065c9  js      loc_1800066B3
0x1800065cf  mov     rcx, [rbp+var_10]
0x1800065d3  test    rcx, rcx
0x1800065d6  jnz     short loc_1800065F6
0x1800065d8  mov     ebx, 800700A1h
0x1800065dd  mov     r9d, 0EFh
0x1800065e3  mov     ecx, ebx
0x1800065e5  call    ElValidateHr_1
0x1800065ea  test    eax, eax
0x1800065ec  js      loc_1800066B3
0x1800065f2  mov     rcx, [rbp+var_10]
0x1800065f6  lea     r8, [rbp+lpNewFileName]
0x1800065fa  mov     rdx, rsi
0x1800065fd  call    cs:__imp_ConcatenatePaths
0x180006604  nop     dword ptr [rax+rax+00h]
0x180006609  mov     ecx, eax
0x18000660b  mov     r9d, 0F3h
0x180006611  mov     esi, eax
0x180006613  call    ElValidateWin32_0
0x180006618  test    eax, eax
0x18000661a  jz      short loc_18000662F
0x18000661c  test    esi, esi
0x18000661e  jg      short loc_180006627
0x180006620  mov     ebx, esi
0x180006622  jmp     loc_1800066B3
0x180006627  movzx   ebx, si
0x18000662a  jmp     loc_180006599
0x18000662f  mov     rdx, [rbp+lpNewFileName]; lpNewFileName
0x180006633  mov     rcx, [rdi+20h]; lpExistingFileName
0x180006637  call    cs:__imp_MoveFileW
0x18000663e  nop     dword ptr [rax+rax+00h]
0x180006643  test    eax, eax
0x180006645  jnz     short loc_18000666F
0x180006647  call    cs:__imp_GetLastError
0x18000664e  nop     dword ptr [rax+rax+00h]
0x180006653  mov     ebx, eax
0x180006655  cmp     eax, 0B7h
0x18000665a  jnz     short loc_180006663
0x18000665c  mov     ebx, 0C1020209h
0x180006661  jmp     short loc_1800066B3
0x180006663  test    eax, eax
0x180006665  jle     short loc_1800066B3
0x180006667  movzx   ebx, ax
0x18000666a  jmp     loc_180006599
0x18000666f  mov     rcx, [rdi+18h]
0x180006673  test    rcx, rcx
0x180006676  jz      short loc_180006684
0x180006678  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000667f  nop     dword ptr [rax+rax+00h]
0x180006684  mov     rax, [rbp+arg_18]
0x180006688  and     [rbp+arg_18], 0
0x18000668d  mov     rcx, [rdi+20h]
0x180006691  mov     [rdi+18h], rax
0x180006695  test    rcx, rcx
0x180006698  jz      short loc_1800066A6
0x18000669a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800066a1  nop     dword ptr [rax+rax+00h]
0x1800066a6  mov     rax, [rbp+lpNewFileName]
0x1800066aa  and     [rbp+lpNewFileName], 0
0x1800066af  mov     [rdi+20h], rax
0x1800066b3  mov     rcx, [rbp+arg_18]
0x1800066b7  test    rcx, rcx
0x1800066ba  jz      short loc_1800066CD
0x1800066bc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800066c3  nop     dword ptr [rax+rax+00h]
0x1800066c8  and     [rbp+arg_18], 0
0x1800066cd  mov     rcx, [rbp+lpNewFileName]
0x1800066d1  test    rcx, rcx
0x1800066d4  jz      short loc_1800066E7
0x1800066d6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800066dd  nop     dword ptr [rax+rax+00h]
0x1800066e2  and     [rbp+lpNewFileName], 0
0x1800066e7  mov     rcx, [rbp+var_10]
0x1800066eb  test    rcx, rcx
0x1800066ee  jz      short loc_1800066FC
0x1800066f0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800066f7  nop     dword ptr [rax+rax+00h]
0x1800066fc  mov     eax, ebx
0x1800066fe  mov     rbx, [rsp+30h+arg_0]
0x180006703  add     rsp, 30h
0x180006707  pop     rdi
0x180006708  pop     rsi
0x180006709  pop     rbp
0x18000670a  retn
```
