# WdsEnumerateDirectoryRecursive

- ea: `0x1800197a8`
- end: `0x180019a2d`
- name: `WdsEnumerateDirectoryRecursive`
- size: `645`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1800197a8`
- `0x18001b7a0`
- `0x18001b830`

## callees

- `0x1800197a8`
- `0x180019a40`
- `0x18001a28c`
- `0x18001b750`
- `0x18002e468`
- `0x18002f3ba`
- `0x18002f3e0`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180019888`
- `KERNEL32!GetLastError` at `0x1800199a5`
- `KERNEL32!GetLastError` at `0x180019888`
- `KERNEL32!GetLastError` at `0x1800199a5`
- `KERNEL32!FindFirstFileW` at `0x180019873`
- `KERNEL32!FindFirstFileW` at `0x180019873`
- `KERNEL32!FindNextFileW` at `0x180019991`
- `KERNEL32!FindNextFileW` at `0x180019991`
- `KERNEL32!FindClose` at `0x1800199e1`
- `KERNEL32!FindClose` at `0x1800199e1`

## pseudocode

```c
__int64 __fastcall WdsEnumerateDirectoryRecursive(
        _WORD *a1,
        __int64 (__fastcall *a2)(void *, __int64),
        unsigned int a3,
        __int64 a4)
{
  signed int v8; // ebx
  void *v9; // rdi
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
  void *lpMem; // [rsp+20h] [rbp-E0h] BYREF
  LPCWSTR lpFileName; // [rsp+28h] [rbp-D8h] BYREF
  _WORD *v28; // [rsp+30h] [rbp-D0h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF

  v28 = a1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  lpMem = 0;
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
          v20 = ConcatenatePaths(v28, (__int64)FindFileData.cFileName, (unsigned __int16 **)&lpMem);
          if ( (unsigned int)ElValidateWin32_8(v20, v21, v22, 0x9FBu) )
            break;
          v9 = lpMem;
          if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
            goto LABEL_23;
          if ( FindFileData.cFileName[0] != 46
            || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2]) )
          {
            if ( a3 )
            {
              v8 = a2(lpMem, a4);
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
            lpMem = 0;
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
          v9 = lpMem;
          goto LABEL_35;
        }
        v24 = (unsigned __int16)v20;
        v9 = lpMem;
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
0x1800197a8  push    rbp
0x1800197aa  push    rbx
0x1800197ab  push    rsi
0x1800197ac  push    rdi
0x1800197ad  push    r12
0x1800197af  push    r13
0x1800197b1  push    r14
0x1800197b3  push    r15
0x1800197b5  lea     rbp, [rsp-1A8h]
0x1800197bd  sub     rsp, 2A8h
0x1800197c4  mov     rax, cs:__security_cookie
0x1800197cb  xor     rax, rsp
0x1800197ce  mov     [rbp+1E0h+var_50], rax
0x1800197d5  mov     r15d, r8d
0x1800197d8  mov     [rsp+2E0h+var_2B0], rcx
0x1800197dd  mov     r12, rdx
0x1800197e0  mov     rsi, rcx
0x1800197e3  xor     edx, edx; Val
0x1800197e5  lea     rcx, [rsp+2E0h+FindFileData]; void *
0x1800197ea  mov     r8d, 250h; Size
0x1800197f0  mov     r13, r9
0x1800197f3  call    memset_0
0x1800197f8  xor     r14d, r14d
0x1800197fb  mov     [rsp+2E0h+lpMem], r14
0x180019800  mov     ebx, r14d
0x180019803  mov     [rsp+2E0h+lpFileName], r14
0x180019808  mov     edi, r14d
0x18001980b  test    rsi, rsi
0x18001980e  jnz     short loc_18001981A
0x180019810  mov     ebx, 80070057h
0x180019815  jmp     loc_180019A07
0x18001981a  mov     rcx, rsi
0x18001981d  call    WdsDirectoryExists
0x180019822  test    eax, eax
0x180019824  jz      short loc_180019810
0x180019826  lea     r8, [rsp+2E0h+lpFileName]
0x18001982b  mov     rcx, rsi
0x18001982e  lea     rdx, asc_180034514; "*"
0x180019835  call    ConcatenatePaths
0x18001983a  mov     r9d, 9E6h
0x180019840  mov     ecx, eax
0x180019842  mov     esi, eax
0x180019844  call    ElValidateWin32_8
0x180019849  mov     r14, [rsp+2E0h+lpFileName]
0x18001984e  test    eax, eax
0x180019850  jz      short loc_18001986B
0x180019852  test    esi, esi
0x180019854  jg      short loc_18001985D
0x180019856  mov     ebx, esi
0x180019858  jmp     loc_1800199ED
0x18001985d  movzx   ebx, si
0x180019860  or      ebx, 80070000h
0x180019866  jmp     loc_1800199ED
0x18001986b  lea     rdx, [rsp+2E0h+FindFileData]; lpFindFileData
0x180019870  mov     rcx, r14; lpFileName
0x180019873  call    cs:__imp_FindFirstFileW
0x18001987a  nop     dword ptr [rax+rax+00h]
0x18001987f  mov     rsi, rax
0x180019882  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180019886  jnz     short loc_1800198C2
0x180019888  call    cs:__imp_GetLastError
0x18001988f  nop     dword ptr [rax+rax+00h]
0x180019894  mov     ecx, eax
0x180019896  mov     r9d, 9EFh
0x18001989c  call    ElValidateWin32_8
0x1800198a1  mov     ebx, eax
0x1800198a3  test    eax, eax
0x1800198a5  jle     short loc_1800198B0
0x1800198a7  movzx   ebx, ax
0x1800198aa  or      ebx, 80070000h
0x1800198b0  test    ebx, ebx
0x1800198b2  js      loc_1800199ED
0x1800198b8  mov     ebx, 80004005h
0x1800198bd  jmp     loc_1800199ED
0x1800198c2  mov     rcx, [rsp+2E0h+var_2B0]
0x1800198c7  lea     r8, [rsp+2E0h+lpMem]
0x1800198cc  lea     rdx, [rsp+2E0h+FindFileData.cFileName]
0x1800198d1  call    ConcatenatePaths
0x1800198d6  mov     r9d, 9FBh
0x1800198dc  mov     ecx, eax
0x1800198de  mov     edi, eax
0x1800198e0  call    ElValidateWin32_8
0x1800198e5  xor     ecx, ecx
0x1800198e7  test    eax, eax
0x1800198e9  jnz     loc_1800199C3
0x1800198ef  test    byte ptr [rsp+2E0h+FindFileData.dwFileAttributes], 10h
0x1800198f4  mov     rdi, [rsp+2E0h+lpMem]
0x1800198f9  jz      short loc_18001995F
0x1800198fb  cmp     [rsp+2E0h+FindFileData.cFileName], 2Eh ; '.'
0x180019901  movzx   eax, [rsp+2E0h+FindFileData.cFileName+2]
0x180019906  jnz     short loc_180019922
0x180019908  test    ax, ax
0x18001990b  jz      short loc_180019973
0x18001990d  cmp     [rsp+2E0h+FindFileData.cFileName], 2Eh ; '.'
0x180019913  jnz     short loc_180019922
0x180019915  cmp     ax, 2Eh ; '.'
0x180019919  jnz     short loc_180019922
0x18001991b  cmp     [rsp+2E0h+FindFileData.cFileName+4], cx
0x180019920  jz      short loc_180019973
0x180019922  test    r15d, r15d
0x180019925  jz      short loc_18001993F
0x180019927  mov     rdx, r13
0x18001992a  mov     rcx, rdi
0x18001992d  mov     rax, r12
0x180019930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019935  mov     ebx, eax
0x180019937  test    eax, eax
0x180019939  js      loc_1800199DE
0x18001993f  mov     r9, r13
0x180019942  mov     r8d, r15d
0x180019945  mov     rdx, r12
0x180019948  mov     rcx, rdi
0x18001994b  call    WdsEnumerateDirectoryRecursive
0x180019950  mov     ebx, eax
0x180019952  test    eax, eax
0x180019954  js      loc_1800199DE
0x18001995a  test    r15d, r15d
0x18001995d  jnz     short loc_180019973
0x18001995f  mov     rdx, r13
0x180019962  mov     rcx, rdi
0x180019965  mov     rax, r12
0x180019968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001996d  mov     ebx, eax
0x18001996f  test    eax, eax
0x180019971  js      short loc_1800199DE
0x180019973  test    rdi, rdi
0x180019976  jz      short loc_180019989
0x180019978  mov     rcx, rdi; lpMem
0x18001997b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019980  xor     eax, eax
0x180019982  mov     edi, eax
0x180019984  mov     [rsp+2E0h+lpMem], rax
0x180019989  lea     rdx, [rsp+2E0h+FindFileData]; lpFindFileData
0x18001998e  mov     rcx, rsi; hFindFile
0x180019991  call    cs:__imp_FindNextFileW
0x180019998  nop     dword ptr [rax+rax+00h]
0x18001999d  test    eax, eax
0x18001999f  jnz     loc_1800198C2
0x1800199a5  call    cs:__imp_GetLastError
0x1800199ac  nop     dword ptr [rax+rax+00h]
0x1800199b1  cmp     eax, 12h
0x1800199b4  jz      short loc_1800199DE
0x1800199b6  test    eax, eax
0x1800199b8  jg      short loc_1800199BE
0x1800199ba  mov     ebx, eax
0x1800199bc  jmp     short loc_1800199DE
0x1800199be  movzx   ebx, ax
0x1800199c1  jmp     short loc_1800199D8
0x1800199c3  test    edi, edi
0x1800199c5  jg      short loc_1800199D0
0x1800199c7  mov     ebx, edi
0x1800199c9  mov     rdi, [rsp+2E0h+lpMem]
0x1800199ce  jmp     short loc_1800199DE
0x1800199d0  movzx   ebx, di
0x1800199d3  mov     rdi, [rsp+2E0h+lpMem]
0x1800199d8  or      ebx, 80070000h
0x1800199de  mov     rcx, rsi; hFindFile
0x1800199e1  call    cs:__imp_FindClose
0x1800199e8  nop     dword ptr [rax+rax+00h]
0x1800199ed  test    r14, r14
0x1800199f0  jz      short loc_1800199FA
0x1800199f2  mov     rcx, r14; lpMem
0x1800199f5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800199fa  test    rdi, rdi
0x1800199fd  jz      short loc_180019A07
0x1800199ff  mov     rcx, rdi; lpMem
0x180019a02  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019a07  mov     eax, ebx
0x180019a09  mov     rcx, [rbp+1E0h+var_50]
0x180019a10  xor     rcx, rsp; StackCookie
0x180019a13  call    __security_check_cookie
0x180019a18  add     rsp, 2A8h
0x180019a1f  pop     r15
0x180019a21  pop     r14
0x180019a23  pop     r13
0x180019a25  pop     r12
0x180019a27  pop     rdi
0x180019a28  pop     rsi
0x180019a29  pop     rbx
0x180019a2a  pop     rbp
0x180019a2b  retn
```
