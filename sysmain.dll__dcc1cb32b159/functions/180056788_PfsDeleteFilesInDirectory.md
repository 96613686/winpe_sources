# PfsDeleteFilesInDirectory

- ea: `0x180056788`
- end: `0x1800568d0`
- name: `PfsDeleteFilesInDirectory`
- size: `328`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800564d0`
- `0x180083f1c`

## callees

- `0x180039f94`
- `0x180049d6c`
- `0x180056788`
- `0x1800784c8`
- `0x1800b645a`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056818`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056818`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005687d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005687d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18005689b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18005689b`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18005688b`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18005688b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180056806`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180056806`

## pseudocode

```c
__int64 __fastcall PfsDeleteFilesInDirectory(__int64 a1, __int64 a2)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rbx
  HANDLE FirstFileW; // rsi
  __int64 v8; // rdi
  __int64 v9; // rax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-498h] BYREF
  wchar_t pszDest[264]; // [rsp+280h] [rbp-248h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v4 = StringCbPrintfW(pszDest, 0x208u, L"%s\\%s", a1, a2);
  if ( v4 >= 0 )
  {
    v6 = -1;
    FirstFileW = FindFirstFileW(pszDest, &FindFileData);
    if ( FirstFileW == (HANDLE)-1LL )
    {
      return GetLastError();
    }
    else
    {
      v8 = -1;
      do
        ++v8;
      while ( *(_WORD *)(a2 + 2 * v8) );
      do
        ++v6;
      while ( pszDest[v6] );
      do
      {
        v9 = (unsigned int)(v6 - v8);
        if ( (unsigned __int64)(2 * v9) >= 0x208 )
          _report_rangecheckfailure();
        pszDest[v9] = 0;
        if ( StringCbCatW(pszDest, 0x208u, FindFileData.cFileName) >= 0 )
          DeleteFileW(pszDest);
      }
      while ( FindNextFileW(FirstFileW, &FindFileData) );
      v5 = 0;
      FindClose(FirstFileW);
    }
  }
  else
  {
    return (unsigned __int16)v4;
  }
  return v5;
}

```

## disassembly

```asm
0x180056788  mov     [rsp+arg_10], rbx
0x18005678d  push    rbp
0x18005678e  push    rsi
0x18005678f  push    rdi
0x180056790  push    r14
0x180056792  push    r15
0x180056794  sub     rsp, 4A0h
0x18005679b  mov     rax, cs:__security_cookie
0x1800567a2  xor     rax, rsp
0x1800567a5  mov     [rsp+4C8h+var_38], rax
0x1800567ad  mov     rbp, rdx
0x1800567b0  mov     rbx, rcx
0x1800567b3  xor     edx, edx; Val
0x1800567b5  lea     rcx, [rsp+4C8h+FindFileData]; void *
0x1800567ba  mov     r8d, 250h; Size
0x1800567c0  call    memset_0
0x1800567c5  mov     r15d, 208h
0x1800567cb  mov     [rsp+4C8h+var_4A8], rbp
0x1800567d0  mov     edx, r15d; cbDest
0x1800567d3  lea     r8, aSS; "%s\\%s"
0x1800567da  mov     r9, rbx
0x1800567dd  lea     rcx, [rsp+4C8h+pszDest]; pszDest
0x1800567e5  call    StringCbPrintfW
0x1800567ea  xor     r14d, r14d
0x1800567ed  test    eax, eax
0x1800567ef  jns     short loc_1800567F9
0x1800567f1  movzx   ebx, ax
0x1800567f4  jmp     loc_1800568A1
0x1800567f9  lea     rdx, [rsp+4C8h+FindFileData]; lpFindFileData
0x1800567fe  lea     rcx, [rsp+4C8h+pszDest]; lpFileName
0x180056806  call    cs:__imp_FindFirstFileW
0x18005680c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180056810  mov     rsi, rax
0x180056813  cmp     rax, rbx
0x180056816  jnz     short loc_180056822
0x180056818  call    cs:__imp_GetLastError
0x18005681e  mov     ebx, eax
0x180056820  jmp     short loc_1800568A1
0x180056822  mov     rdi, rbx
0x180056825  inc     rdi
0x180056828  cmp     [rbp+rdi*2+0], r14w
0x18005682e  jnz     short loc_180056825
0x180056830  lea     rax, [rsp+4C8h+pszDest]
0x180056838  inc     rbx
0x18005683b  cmp     [rax+rbx*2], r14w
0x180056840  jnz     short loc_180056838
0x180056842  mov     rax, rbx
0x180056845  sub     rax, rdi
0x180056848  mov     eax, eax
0x18005684a  lea     rcx, [rax+rax]
0x18005684e  cmp     rcx, r15
0x180056851  jnb     short loc_1800568CA
0x180056853  mov     [rsp+rcx+4C8h+pszDest], r14w
0x18005685c  lea     r8, [rsp+4C8h+FindFileData.cFileName]; pszSrc
0x180056861  lea     rcx, [rsp+4C8h+pszDest]; pszDest
0x180056869  mov     rdx, r15; cbDest
0x18005686c  call    StringCbCatW
0x180056871  test    eax, eax
0x180056873  js      short loc_180056883
0x180056875  lea     rcx, [rsp+4C8h+pszDest]; lpFileName
0x18005687d  call    cs:__imp_DeleteFileW
0x180056883  lea     rdx, [rsp+4C8h+FindFileData]; lpFindFileData
0x180056888  mov     rcx, rsi; hFindFile
0x18005688b  call    cs:__imp_FindNextFileW
0x180056891  test    eax, eax
0x180056893  jnz     short loc_180056842
0x180056895  mov     ebx, r14d
0x180056898  mov     rcx, rsi; hFindFile
0x18005689b  call    cs:__imp_FindClose
0x1800568a1  mov     eax, ebx
0x1800568a3  mov     rcx, [rsp+4C8h+var_38]
0x1800568ab  xor     rcx, rsp; StackCookie
0x1800568ae  call    __security_check_cookie
0x1800568b3  mov     rbx, [rsp+4C8h+arg_10]
0x1800568bb  add     rsp, 4A0h
0x1800568c2  pop     r15
0x1800568c4  pop     r14
0x1800568c6  pop     rdi
0x1800568c7  pop     rsi
0x1800568c8  pop     rbp
0x1800568c9  retn
0x1800568ca  call    __report_rangecheckfailure
```
