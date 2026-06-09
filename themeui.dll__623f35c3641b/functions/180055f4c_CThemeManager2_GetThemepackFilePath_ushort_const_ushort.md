# CThemeManager2::_GetThemepackFilePath(ushort const *,ushort * *)

- ea: `0x180055f4c`
- end: `0x1800560ec`
- name: `?_GetThemepackFilePath@CThemeManager2@@AEAAJPEBGPEAPEAG@Z`
- size: `416`
- prototype: `int(CThemeManager2 *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x1800560f4`
- `0x180056d14`

## callees

- `0x180030f64`
- `0x1800358c0`
- `0x180035d00`
- `0x180055f4c`

## import_xrefs

- `SHCORE!SHStrDupW` at `0x1800560b2`
- `SHCORE!SHStrDupW` at `0x1800560b2`
- `SHELL32!SHFileOperationW` at `0x18005604c`
- `SHELL32!SHFileOperationW` at `0x18005604c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180055fca`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180056069`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180055fca`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180056069`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180055fb5`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180056087`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180055fb5`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180056087`
- `api-ms-win-core-path-l1-1-0!PathCchAddExtension` at `0x1800560a0`
- `api-ms-win-core-path-l1-1-0!PathCchAddExtension` at `0x1800560a0`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180055f93`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180055f93`

## pseudocode

```c
HRESULT __fastcall CThemeManager2::_GetThemepackFilePath(
        CThemeManager2 *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  HRESULT result; // eax
  __int64 v6; // rax
  unsigned __int64 v7; // rcx
  bool v8; // sf
  _SHFILEOPSTRUCTW FileOp; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR pszPath[264]; // [rsp+60h] [rbp-A0h] BYREF

  *a3 = 0;
  if ( (unsigned int)GetTempPath2W(260, pszPath) - 1 > 0x103 )
    return -2147024774;
  result = PathCchAppend(pszPath, 0x104u, L"MicroThemePackDir");
  if ( result < 0 )
    return result;
  if ( CreateDirectoryW(pszPath, 0) )
    goto LABEL_14;
  result = ResultFromKnownLastError();
  if ( result != -2147024713 )
    goto LABEL_13;
  v6 = -1;
  do
    ++v6;
  while ( pszPath[v6] );
  v7 = 2 * v6 + 2;
  if ( v7 >= 0x20A )
    _report_rangecheckfailure();
  *(WCHAR *)((char *)pszPath + v7) = 0;
  FileOp.pFrom = pszPath;
  FileOp.hwnd = 0;
  *(_QWORD *)&FileOp.wFunc = 3;
  FileOp.pTo = 0;
  *(_DWORD *)&FileOp.fFlags = 1556;
  memset(&FileOp.fAnyOperationsAborted, 0, 20);
  result = SHFileOperationW(&FileOp);
  v8 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v8 = result < 0;
  }
  if ( !v8 )
  {
    if ( CreateDirectoryW(pszPath, 0) )
    {
LABEL_14:
      result = PathCchAppend(pszPath, 0x104u, a2);
      if ( result >= 0 )
      {
        result = PathCchAddExtension(pszPath, 0x104u, L".deskthemepack");
        if ( result >= 0 )
          return SHStrDupW(pszPath, a3);
      }
      return result;
    }
    result = ResultFromKnownLastError();
LABEL_13:
    if ( result < 0 )
      return result;
    goto LABEL_14;
  }
  return result;
}

```

## disassembly

```asm
0x180055f4c  mov     [rsp-8+arg_0], rbx
0x180055f51  mov     [rsp-8+arg_18], rsi
0x180055f56  push    rbp
0x180055f57  push    rdi
0x180055f58  push    r14
0x180055f5a  lea     rbp, [rsp-180h]
0x180055f62  sub     rsp, 280h
0x180055f69  mov     rax, cs:__security_cookie
0x180055f70  xor     rax, rsp
0x180055f73  mov     [rbp+190h+var_20], rax
0x180055f7a  mov     rdi, rdx
0x180055f7d  mov     r14d, 104h
0x180055f83  xor     esi, esi
0x180055f85  lea     rdx, [rsp+290h+pszPath]
0x180055f8a  mov     ecx, r14d
0x180055f8d  mov     [r8], rsi
0x180055f90  mov     rbx, r8
0x180055f93  call    cs:__imp_GetTempPath2W
0x180055f99  dec     eax
0x180055f9b  cmp     eax, 103h
0x180055fa0  ja      loc_1800560C0
0x180055fa6  lea     r8, aMicrothemepack; "MicroThemePackDir"
0x180055fad  mov     edx, r14d; cchPath
0x180055fb0  lea     rcx, [rsp+290h+pszPath]; pszPath
0x180055fb5  call    cs:__imp_PathCchAppend
0x180055fbb  test    eax, eax
0x180055fbd  js      loc_1800560C5
0x180055fc3  xor     edx, edx; lpSecurityAttributes
0x180055fc5  lea     rcx, [rsp+290h+pszPath]; lpPathName
0x180055fca  call    cs:__imp_CreateDirectoryW
0x180055fd0  test    eax, eax
0x180055fd2  jnz     loc_18005607C
0x180055fd8  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180055fdd  cmp     eax, 800700B7h
0x180055fe2  jnz     loc_180056078
0x180055fe8  lea     rcx, [rsp+290h+pszPath]
0x180055fed  or      rax, 0FFFFFFFFFFFFFFFFh
0x180055ff1  inc     rax
0x180055ff4  cmp     [rcx+rax*2], si
0x180055ff8  jnz     short loc_180055FF1
0x180055ffa  lea     rcx, ds:2[rax*2]
0x180056002  cmp     rcx, 20Ah
0x180056009  jnb     loc_1800560BA
0x18005600f  lea     rax, [rsp+290h+pszPath]
0x180056014  mov     [rsp+rcx+290h+pszPath], si
0x180056019  mov     [rsp+290h+FileOp.pFrom], rax
0x18005601e  lea     rcx, [rsp+290h+FileOp]; lpFileOp
0x180056023  xor     eax, eax
0x180056025  mov     [rsp+290h+FileOp.hwnd], rsi
0x18005602a  xorps   xmm0, xmm0
0x18005602d  mov     dword ptr [rsp+290h+FileOp.lpszProgressTitle+4], eax
0x180056031  mov     qword ptr [rsp+290h+FileOp.wFunc], 3
0x18005603a  mov     [rsp+290h+FileOp.pTo], rsi
0x18005603f  mov     dword ptr [rsp+290h+FileOp.fFlags], 614h
0x180056047  movups  xmmword ptr [rsp+290h+FileOp.fAnyOperationsAborted], xmm0
0x18005604c  call    cs:__imp_SHFileOperationW
0x180056052  test    eax, eax
0x180056054  jle     short loc_180056060
0x180056056  movzx   eax, ax
0x180056059  or      eax, 80070000h
0x18005605e  test    eax, eax
0x180056060  js      short loc_1800560C5
0x180056062  xor     edx, edx; lpSecurityAttributes
0x180056064  lea     rcx, [rsp+290h+pszPath]; lpPathName
0x180056069  call    cs:__imp_CreateDirectoryW
0x18005606f  test    eax, eax
0x180056071  jnz     short loc_18005607C
0x180056073  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180056078  test    eax, eax
0x18005607a  js      short loc_1800560C5
0x18005607c  mov     r8, rdi; pszMore
0x18005607f  lea     rcx, [rsp+290h+pszPath]; pszPath
0x180056084  mov     rdx, r14; cchPath
0x180056087  call    cs:__imp_PathCchAppend
0x18005608d  test    eax, eax
0x18005608f  js      short loc_1800560C5
0x180056091  lea     r8, pszExt; ".deskthemepack"
0x180056098  mov     rdx, r14; cchPath
0x18005609b  lea     rcx, [rsp+290h+pszPath]; pszPath
0x1800560a0  call    cs:__imp_PathCchAddExtension
0x1800560a6  test    eax, eax
0x1800560a8  js      short loc_1800560C5
0x1800560aa  mov     rdx, rbx; ppwsz
0x1800560ad  lea     rcx, [rsp+290h+pszPath]; psz
0x1800560b2  call    cs:__imp_SHStrDupW
0x1800560b8  jmp     short loc_1800560C5
0x1800560ba  call    __report_rangecheckfailure
0x1800560c0  mov     eax, 8007007Ah
0x1800560c5  mov     rcx, [rbp+190h+var_20]
0x1800560cc  xor     rcx, rsp; StackCookie
0x1800560cf  call    __security_check_cookie
0x1800560d4  lea     r11, [rsp+290h+var_10]
0x1800560dc  mov     rbx, [r11+20h]
0x1800560e0  mov     rsi, [r11+38h]
0x1800560e4  mov     rsp, r11
0x1800560e7  pop     r14
0x1800560e9  pop     rdi
0x1800560ea  pop     rbp
0x1800560eb  retn
```
