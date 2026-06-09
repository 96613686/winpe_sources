# RemoveDirectoryRecursive(ushort const *,RemoveDirectoryRecursiveFlags)

- ea: `0x18007deb0`
- end: `0x18007e069`
- name: `?RemoveDirectoryRecursive@@YAJPEBGW4RemoveDirectoryRecursiveFlags@@@Z`
- size: `441`
- prototype: `__int64 __fastcall(const WCHAR *, int)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18007de70`
- `0x18007de90`
- `0x18007deb0`

## callees

- `0x18007deb0`
- `0x180080fb0`
- `0x180081b40`
- `0x180081d9d`
- `0x180081f3d`
- `0x1800b79c4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007df9d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007df9d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18007dfd5`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18007dfd5`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18007df25`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18007df25`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18007dff9`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18007dff9`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18007def9`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18007df77`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18007def9`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18007df77`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RemoveDirectoryRecursive(const WCHAR *a1, int a2)
{
  HRESULT ErrorError; // ebx
  HANDLE FirstFileW; // rsi
  PCWSTR pszPathIn; // [rsp+20h] [rbp-E0h] BYREF
  PWSTR ppszPathOut; // [rsp+28h] [rbp-D8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF

  ppszPathOut = 0;
  ErrorError = PathAllocCombine(a1, L"*", 1u, &ppszPathOut);
  if ( ErrorError >= 0 )
  {
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    FirstFileW = FindFirstFileW(ppszPathOut, &FindFileData);
    if ( FirstFileW != (HANDLE)-1LL )
    {
      while ( 1 )
      {
        if ( (FindFileData.dwFileAttributes & 0x10) == 0
          || FindFileData.cFileName[0] != 46
          || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2]) )
        {
          pszPathIn = 0;
          ErrorError = PathAllocCombine(a1, FindFileData.cFileName, 1u, (PWSTR *)&pszPathIn);
          if ( ErrorError < 0 )
            break;
          if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
          {
            ErrorError = RemoveDirectoryRecursive(pszPathIn, a2 & 0xFFFFFFFD);
          }
          else if ( DeleteFileW(pszPathIn) )
          {
            ErrorError = 0;
          }
          else
          {
            ErrorError = HRESULTFromLastErrorError();
            if ( ErrorError < 0 && (a2 & 1) != 0 )
              ErrorError = 0;
          }
          LocalFree_0((HLOCAL)pszPathIn);
        }
        if ( ErrorError < 0 )
          break;
        if ( FindNextFileW(FirstFileW, &FindFileData) )
        {
          ErrorError = 0;
        }
        else
        {
          ErrorError = HRESULTFromLastErrorError();
          if ( ErrorError < 0 )
            break;
        }
      }
      FindClose(FirstFileW);
      if ( ErrorError == -2147024878 )
        ErrorError = 0;
    }
    LocalFree_0(ppszPathOut);
    if ( ErrorError >= 0 && (a2 & 2) == 0 )
    {
      if ( RemoveDirectoryW_0(a1) )
      {
        return 0;
      }
      else
      {
        ErrorError = HRESULTFromLastErrorError();
        if ( ErrorError < 0 && (a2 & 1) != 0 )
          return 0;
      }
    }
  }
  return (unsigned int)ErrorError;
}

```

## disassembly

```asm
0x18007deb0  mov     [rsp-8+arg_10], rbx
0x18007deb5  push    rbp
0x18007deb6  push    rsi
0x18007deb7  push    rdi
0x18007deb8  push    r14
0x18007deba  push    r15
0x18007debc  lea     rbp, [rsp-190h]
0x18007dec4  sub     rsp, 290h
0x18007decb  mov     rax, cs:__security_cookie
0x18007ded2  xor     rax, rsp
0x18007ded5  mov     [rbp+1B0h+var_30], rax
0x18007dedc  xor     r15d, r15d
0x18007dedf  lea     r9, [rsp+2B0h+ppszPathOut]; ppszPathOut
0x18007dee4  mov     edi, edx
0x18007dee6  mov     [rsp+2B0h+ppszPathOut], r15
0x18007deeb  lea     rdx, pszMore; "*"
0x18007def2  mov     r14, rcx
0x18007def5  lea     r8d, [r15+1]; dwFlags
0x18007def9  call    cs:__imp_PathAllocCombine
0x18007deff  mov     ebx, eax
0x18007df01  test    eax, eax
0x18007df03  js      loc_18007E041
0x18007df09  xor     edx, edx; Val
0x18007df0b  lea     rcx, [rsp+2B0h+FindFileData]; void *
0x18007df10  mov     r8d, 250h; Size
0x18007df16  call    memset_0
0x18007df1b  mov     rcx, [rsp+2B0h+ppszPathOut]; lpFileName
0x18007df20  lea     rdx, [rsp+2B0h+FindFileData]; lpFindFileData
0x18007df25  call    cs:__imp_FindFirstFileW
0x18007df2b  mov     rsi, rax
0x18007df2e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007df32  jz      loc_18007E009
0x18007df38  test    byte ptr [rsp+2B0h+FindFileData.dwFileAttributes], 10h
0x18007df3d  jz      short loc_18007DF5F
0x18007df3f  cmp     [rsp+2B0h+FindFileData.cFileName], 2Eh ; '.'
0x18007df45  jnz     short loc_18007DF5F
0x18007df47  movzx   eax, [rsp+2B0h+FindFileData.cFileName+2]
0x18007df4c  test    ax, ax
0x18007df4f  jz      short loc_18007DFC9
0x18007df51  cmp     ax, 2Eh ; '.'
0x18007df55  jnz     short loc_18007DF5F
0x18007df57  cmp     [rsp+2B0h+FindFileData.cFileName+4], r15w
0x18007df5d  jz      short loc_18007DFC9
0x18007df5f  lea     r9, [rsp+2B0h+pszPathIn]; ppszPathOut
0x18007df64  mov     [rsp+2B0h+pszPathIn], r15
0x18007df69  mov     r8d, 1; dwFlags
0x18007df6f  lea     rdx, [rsp+2B0h+FindFileData.cFileName]; pszMore
0x18007df74  mov     rcx, r14; pszPathIn
0x18007df77  call    cs:__imp_PathAllocCombine
0x18007df7d  mov     ebx, eax
0x18007df7f  test    eax, eax
0x18007df81  js      short loc_18007DFF6
0x18007df83  test    byte ptr [rsp+2B0h+FindFileData.dwFileAttributes], 10h
0x18007df88  mov     rcx, [rsp+2B0h+pszPathIn]; lpFileName
0x18007df8d  jz      short loc_18007DF9D
0x18007df8f  mov     edx, edi
0x18007df91  and     edx, 0FFFFFFFDh
0x18007df94  call    ?RemoveDirectoryRecursive@@YAJPEBGW4RemoveDirectoryRecursiveFlags@@@Z; RemoveDirectoryRecursive(ushort const *,RemoveDirectoryRecursiveFlags)
0x18007df99  mov     ebx, eax
0x18007df9b  jmp     short loc_18007DFBF
0x18007df9d  call    cs:__imp_DeleteFileW
0x18007dfa3  test    eax, eax
0x18007dfa5  jz      short loc_18007DFAC
0x18007dfa7  mov     ebx, r15d
0x18007dfaa  jmp     short loc_18007DFBF
0x18007dfac  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x18007dfb1  mov     ebx, eax
0x18007dfb3  test    eax, eax
0x18007dfb5  jns     short loc_18007DFBF
0x18007dfb7  test    dil, 1
0x18007dfbb  cmovnz  ebx, r15d
0x18007dfbf  mov     rcx, [rsp+2B0h+pszPathIn]; hMem
0x18007dfc4  call    LocalFree_0
0x18007dfc9  test    ebx, ebx
0x18007dfcb  js      short loc_18007DFF6
0x18007dfcd  lea     rdx, [rsp+2B0h+FindFileData]; lpFindFileData
0x18007dfd2  mov     rcx, rsi; hFindFile
0x18007dfd5  call    cs:__imp_FindNextFileW
0x18007dfdb  test    eax, eax
0x18007dfdd  jz      short loc_18007DFE7
0x18007dfdf  mov     ebx, r15d
0x18007dfe2  jmp     loc_18007DF38
0x18007dfe7  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x18007dfec  mov     ebx, eax
0x18007dfee  test    eax, eax
0x18007dff0  jns     loc_18007DF38
0x18007dff6  mov     rcx, rsi; hFindFile
0x18007dff9  call    cs:__imp_FindClose
0x18007dfff  cmp     ebx, 80070012h
0x18007e005  cmovz   ebx, r15d
0x18007e009  mov     rcx, [rsp+2B0h+ppszPathOut]; hMem
0x18007e00e  call    LocalFree_0
0x18007e013  test    ebx, ebx
0x18007e015  js      short loc_18007E041
0x18007e017  test    dil, 2
0x18007e01b  jnz     short loc_18007E041
0x18007e01d  mov     rcx, r14; lpPathName
0x18007e020  call    RemoveDirectoryW_0
0x18007e025  test    eax, eax
0x18007e027  jz      short loc_18007E02E
0x18007e029  mov     ebx, r15d
0x18007e02c  jmp     short loc_18007E041
0x18007e02e  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x18007e033  mov     ebx, eax
0x18007e035  test    eax, eax
0x18007e037  jns     short loc_18007E041
0x18007e039  test    dil, 1
0x18007e03d  cmovnz  ebx, r15d
0x18007e041  mov     eax, ebx
0x18007e043  mov     rcx, [rbp+1B0h+var_30]
0x18007e04a  xor     rcx, rsp; StackCookie
0x18007e04d  call    __security_check_cookie
0x18007e052  mov     rbx, [rsp+2B0h+arg_10]
0x18007e05a  add     rsp, 290h
0x18007e061  pop     r15
0x18007e063  pop     r14
0x18007e065  pop     rdi
0x18007e066  pop     rsi
0x18007e067  pop     rbp
0x18007e068  retn
```
