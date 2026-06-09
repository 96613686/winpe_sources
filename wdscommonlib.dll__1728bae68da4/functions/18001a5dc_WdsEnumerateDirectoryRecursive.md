# WdsEnumerateDirectoryRecursive

- ea: `0x18001a5dc`
- end: `0x18001a876`
- name: `WdsEnumerateDirectoryRecursive`
- size: `666`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18001a5dc`
- `0x18001c660`
- `0x18001c6f0`

## callees

- `0x18001a5dc`
- `0x18001a880`
- `0x18001b0cc`
- `0x18001c610`
- `0x180030362`
- `0x180030390`
- `0x180031010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001a7af`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a830`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a844`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a7af`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a830`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a844`
- `KERNEL32!FindClose` at `0x18001a81c`
- `KERNEL32!FindClose` at `0x18001a81c`
- `KERNEL32!FindNextFileW` at `0x18001a7cc`
- `KERNEL32!FindNextFileW` at `0x18001a7cc`
- `KERNEL32!FindFirstFileW` at `0x18001a6a7`
- `KERNEL32!FindFirstFileW` at `0x18001a6a7`
- `KERNEL32!GetLastError` at `0x18001a6bc`
- `KERNEL32!GetLastError` at `0x18001a7e0`
- `KERNEL32!GetLastError` at `0x18001a6bc`
- `KERNEL32!GetLastError` at `0x18001a7e0`

## pseudocode

```c
__int64 __fastcall WdsEnumerateDirectoryRecursive(
        _WORD *a1,
        __int64 (__fastcall *a2)(unsigned __int16 *, __int64),
        unsigned int a3,
        __int64 a4)
{
  signed int v8; // ebx
  unsigned __int16 *v9; // rdi
  signed int v10; // esi
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // eax
  WCHAR *v14; // r14
  HANDLE FirstFileW; // rsi
  DWORD LastError; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  int v19; // eax
  signed int v20; // edi
  __int64 v21; // rdx
  __int64 v22; // r8
  signed int v23; // eax
  int v24; // ebx
  unsigned __int16 *v26; // [rsp+20h] [rbp-E0h] BYREF
  LPCWSTR lpFileName; // [rsp+28h] [rbp-D8h] BYREF
  _WORD *v28; // [rsp+30h] [rbp-D0h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF

  v28 = a1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v26 = 0;
  v8 = 0;
  lpFileName = 0;
  v9 = 0;
  if ( a1 && (unsigned int)WdsDirectoryExists(a1) )
  {
    v10 = ConcatenatePaths(a1, (__int64)L"*", (unsigned __int16 **)&lpFileName);
    v13 = ElValidateWin32_8(v10, v11, v12, 0x9E6u);
    v14 = (WCHAR *)lpFileName;
    if ( v13 )
    {
      if ( v10 > 0 )
        v8 = (unsigned __int16)v10 | 0x80070000;
      else
        v8 = v10;
    }
    else
    {
      FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
      if ( FirstFileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        v19 = ElValidateWin32_8(LastError, v17, v18, 0x9EFu);
        v8 = v19;
        if ( v19 > 0 )
          v8 = (unsigned __int16)v19 | 0x80070000;
        if ( v8 >= 0 )
          v8 = -2147467259;
      }
      else
      {
        while ( 1 )
        {
          v20 = ConcatenatePaths(v28, (__int64)FindFileData.cFileName, &v26);
          if ( (unsigned int)ElValidateWin32_8(v20, v21, v22, 0x9FBu) )
            break;
          v9 = v26;
          if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
            goto LABEL_23;
          if ( FindFileData.cFileName[0] != 46
            || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2]) )
          {
            if ( a3 )
            {
              v8 = a2(v26, a4);
              if ( v8 < 0 )
                goto LABEL_35;
            }
            v8 = WdsEnumerateDirectoryRecursive(v9, a2, a3, a4);
            if ( v8 < 0 )
              goto LABEL_35;
            if ( !a3 )
            {
LABEL_23:
              v8 = a2(v9, a4);
              if ( v8 < 0 )
                goto LABEL_35;
            }
          }
          if ( v9 )
          {
            operator delete(v9);
            v9 = 0;
            v26 = 0;
          }
          if ( !FindNextFileW(FirstFileW, &FindFileData) )
          {
            v23 = GetLastError();
            if ( v23 == 18 )
              goto LABEL_35;
            if ( v23 <= 0 )
            {
              v8 = v23;
              goto LABEL_35;
            }
            v24 = (unsigned __int16)v23;
            goto LABEL_34;
          }
        }
        if ( v20 <= 0 )
        {
          v8 = v20;
          v9 = v26;
          goto LABEL_35;
        }
        v24 = (unsigned __int16)v20;
        v9 = v26;
LABEL_34:
        v8 = v24 | 0x80070000;
LABEL_35:
        FindClose(FirstFileW);
      }
    }
    if ( v14 )
      operator delete(v14);
    if ( v9 )
      operator delete(v9);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001a5dc  push    rbp
0x18001a5de  push    rbx
0x18001a5df  push    rsi
0x18001a5e0  push    rdi
0x18001a5e1  push    r12
0x18001a5e3  push    r13
0x18001a5e5  push    r14
0x18001a5e7  push    r15
0x18001a5e9  lea     rbp, [rsp-1A8h]
0x18001a5f1  sub     rsp, 2A8h
0x18001a5f8  mov     rax, cs:__security_cookie
0x18001a5ff  xor     rax, rsp
0x18001a602  mov     [rbp+1E0h+var_50], rax
0x18001a609  mov     r15d, r8d
0x18001a60c  mov     [rsp+2E0h+var_2B0], rcx
0x18001a611  mov     r12, rdx
0x18001a614  mov     rsi, rcx
0x18001a617  xor     edx, edx; Val
0x18001a619  lea     rcx, [rsp+2E0h+FindFileData]; void *
0x18001a61e  mov     r8d, 250h; Size
0x18001a624  mov     r13, r9
0x18001a627  call    memset_0
0x18001a62c  xor     r14d, r14d
0x18001a62f  mov     [rsp+2E0h+var_2C0], r14
0x18001a634  mov     ebx, r14d
0x18001a637  mov     [rsp+2E0h+lpFileName], r14
0x18001a63c  mov     edi, r14d
0x18001a63f  test    rsi, rsi
0x18001a642  jnz     short loc_18001A64E
0x18001a644  mov     ebx, 80070057h
0x18001a649  jmp     loc_18001A850
0x18001a64e  mov     rcx, rsi
0x18001a651  call    WdsDirectoryExists
0x18001a656  test    eax, eax
0x18001a658  jz      short loc_18001A644
0x18001a65a  lea     r8, [rsp+2E0h+lpFileName]
0x18001a65f  mov     rcx, rsi
0x18001a662  lea     rdx, asc_180036A84; "*"
0x18001a669  call    ConcatenatePaths
0x18001a66e  mov     r9d, 9E6h
0x18001a674  mov     ecx, eax
0x18001a676  mov     esi, eax
0x18001a678  call    ElValidateWin32_8
0x18001a67d  mov     r14, [rsp+2E0h+lpFileName]
0x18001a682  test    eax, eax
0x18001a684  jz      short loc_18001A69F
0x18001a686  test    esi, esi
0x18001a688  jg      short loc_18001A691
0x18001a68a  mov     ebx, esi
0x18001a68c  jmp     loc_18001A828
0x18001a691  movzx   ebx, si
0x18001a694  or      ebx, 80070000h
0x18001a69a  jmp     loc_18001A828
0x18001a69f  lea     rdx, [rsp+2E0h+FindFileData]; lpFindFileData
0x18001a6a4  mov     rcx, r14; lpFileName
0x18001a6a7  call    cs:__imp_FindFirstFileW
0x18001a6ae  nop     dword ptr [rax+rax+00h]
0x18001a6b3  mov     rsi, rax
0x18001a6b6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001a6ba  jnz     short loc_18001A6F6
0x18001a6bc  call    cs:__imp_GetLastError
0x18001a6c3  nop     dword ptr [rax+rax+00h]
0x18001a6c8  mov     ecx, eax
0x18001a6ca  mov     r9d, 9EFh
0x18001a6d0  call    ElValidateWin32_8
0x18001a6d5  mov     ebx, eax
0x18001a6d7  test    eax, eax
0x18001a6d9  jle     short loc_18001A6E4
0x18001a6db  movzx   ebx, ax
0x18001a6de  or      ebx, 80070000h
0x18001a6e4  test    ebx, ebx
0x18001a6e6  js      loc_18001A828
0x18001a6ec  mov     ebx, 80004005h
0x18001a6f1  jmp     loc_18001A828
0x18001a6f6  mov     rcx, [rsp+2E0h+var_2B0]
0x18001a6fb  lea     r8, [rsp+2E0h+var_2C0]
0x18001a700  lea     rdx, [rsp+2E0h+FindFileData.cFileName]
0x18001a705  call    ConcatenatePaths
0x18001a70a  mov     r9d, 9FBh
0x18001a710  mov     ecx, eax
0x18001a712  mov     edi, eax
0x18001a714  call    ElValidateWin32_8
0x18001a719  xor     ecx, ecx
0x18001a71b  test    eax, eax
0x18001a71d  jnz     loc_18001A7FE
0x18001a723  test    byte ptr [rsp+2E0h+FindFileData.dwFileAttributes], 10h
0x18001a728  mov     rdi, [rsp+2E0h+var_2C0]
0x18001a72d  jz      short loc_18001A793
0x18001a72f  cmp     [rsp+2E0h+FindFileData.cFileName], 2Eh ; '.'
0x18001a735  movzx   eax, [rsp+2E0h+FindFileData.cFileName+2]
0x18001a73a  jnz     short loc_18001A756
0x18001a73c  test    ax, ax
0x18001a73f  jz      short loc_18001A7A7
0x18001a741  cmp     [rsp+2E0h+FindFileData.cFileName], 2Eh ; '.'
0x18001a747  jnz     short loc_18001A756
0x18001a749  cmp     ax, 2Eh ; '.'
0x18001a74d  jnz     short loc_18001A756
0x18001a74f  cmp     [rsp+2E0h+FindFileData.cFileName+4], cx
0x18001a754  jz      short loc_18001A7A7
0x18001a756  test    r15d, r15d
0x18001a759  jz      short loc_18001A773
0x18001a75b  mov     rdx, r13
0x18001a75e  mov     rcx, rdi
0x18001a761  mov     rax, r12
0x18001a764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a769  mov     ebx, eax
0x18001a76b  test    eax, eax
0x18001a76d  js      loc_18001A819
0x18001a773  mov     r9, r13
0x18001a776  mov     r8d, r15d
0x18001a779  mov     rdx, r12
0x18001a77c  mov     rcx, rdi
0x18001a77f  call    WdsEnumerateDirectoryRecursive
0x18001a784  mov     ebx, eax
0x18001a786  test    eax, eax
0x18001a788  js      loc_18001A819
0x18001a78e  test    r15d, r15d
0x18001a791  jnz     short loc_18001A7A7
0x18001a793  mov     rdx, r13
0x18001a796  mov     rcx, rdi
0x18001a799  mov     rax, r12
0x18001a79c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7a1  mov     ebx, eax
0x18001a7a3  test    eax, eax
0x18001a7a5  js      short loc_18001A819
0x18001a7a7  test    rdi, rdi
0x18001a7aa  jz      short loc_18001A7C4
0x18001a7ac  mov     rcx, rdi
0x18001a7af  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001a7b6  nop     dword ptr [rax+rax+00h]
0x18001a7bb  xor     eax, eax
0x18001a7bd  mov     edi, eax
0x18001a7bf  mov     [rsp+2E0h+var_2C0], rax
0x18001a7c4  lea     rdx, [rsp+2E0h+FindFileData]; lpFindFileData
0x18001a7c9  mov     rcx, rsi; hFindFile
0x18001a7cc  call    cs:__imp_FindNextFileW
0x18001a7d3  nop     dword ptr [rax+rax+00h]
0x18001a7d8  test    eax, eax
0x18001a7da  jnz     loc_18001A6F6
0x18001a7e0  call    cs:__imp_GetLastError
0x18001a7e7  nop     dword ptr [rax+rax+00h]
0x18001a7ec  cmp     eax, 12h
0x18001a7ef  jz      short loc_18001A819
0x18001a7f1  test    eax, eax
0x18001a7f3  jg      short loc_18001A7F9
0x18001a7f5  mov     ebx, eax
0x18001a7f7  jmp     short loc_18001A819
0x18001a7f9  movzx   ebx, ax
0x18001a7fc  jmp     short loc_18001A813
0x18001a7fe  test    edi, edi
0x18001a800  jg      short loc_18001A80B
0x18001a802  mov     ebx, edi
0x18001a804  mov     rdi, [rsp+2E0h+var_2C0]
0x18001a809  jmp     short loc_18001A819
0x18001a80b  movzx   ebx, di
0x18001a80e  mov     rdi, [rsp+2E0h+var_2C0]
0x18001a813  or      ebx, 80070000h
0x18001a819  mov     rcx, rsi; hFindFile
0x18001a81c  call    cs:__imp_FindClose
0x18001a823  nop     dword ptr [rax+rax+00h]
0x18001a828  test    r14, r14
0x18001a82b  jz      short loc_18001A83C
0x18001a82d  mov     rcx, r14
0x18001a830  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001a837  nop     dword ptr [rax+rax+00h]
0x18001a83c  test    rdi, rdi
0x18001a83f  jz      short loc_18001A850
0x18001a841  mov     rcx, rdi
0x18001a844  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001a84b  nop     dword ptr [rax+rax+00h]
0x18001a850  mov     eax, ebx
0x18001a852  mov     rcx, [rbp+1E0h+var_50]
0x18001a859  xor     rcx, rsp; StackCookie
0x18001a85c  call    __security_check_cookie
0x18001a861  add     rsp, 2A8h
0x18001a868  pop     r15
0x18001a86a  pop     r14
0x18001a86c  pop     r13
0x18001a86e  pop     r12
0x18001a870  pop     rdi
0x18001a871  pop     rsi
0x18001a872  pop     rbx
0x18001a873  pop     rbp
0x18001a874  retn
```
