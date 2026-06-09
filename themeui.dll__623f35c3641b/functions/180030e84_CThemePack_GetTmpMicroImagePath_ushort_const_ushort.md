# CThemePack::_GetTmpMicroImagePath(ushort const *,ushort * *)

- ea: `0x180030e84`
- end: `0x180030f5e`
- name: `?_GetTmpMicroImagePath@CThemePack@@AEAAJPEBGPEAPEAG@Z`
- size: `218`
- prototype: `int(CThemePack *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18006760c`

## callees

- `0x180030e84`
- `0x180030f64`
- `0x1800358c0`

## import_xrefs

- `SHCORE!SHStrDupW` at `0x180030f30`
- `SHCORE!SHStrDupW` at `0x180030f30`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180030eeb`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180030eeb`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180030eda`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180030f1e`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180030eda`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180030f1e`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180030eba`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180030eba`

## pseudocode

```c
HRESULT __fastcall CThemePack::_GetTmpMicroImagePath(
        CThemePack *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  HRESULT result; // eax
  bool v6; // sf
  WCHAR pszPath[264]; // [rsp+20h] [rbp-228h] BYREF

  *a3 = 0;
  if ( (unsigned int)GetTempPath2W(260, pszPath) - 1 > 0x103 )
    return -2147024774;
  result = PathCchAppend(pszPath, 0x104u, L"MicroImageDir");
  if ( result >= 0 )
  {
    if ( CreateDirectoryW(pszPath, 0) )
      goto LABEL_8;
    result = ResultFromKnownLastError();
    v6 = result < 0;
    if ( result > 0 )
    {
      result = (unsigned __int16)result | 0x80070000;
      v6 = result < 0;
    }
    if ( !v6 || result == -2147024713 )
    {
LABEL_8:
      result = PathCchAppend(pszPath, 0x104u, a2);
      if ( result >= 0 )
        return SHStrDupW(pszPath, a3);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180030e84  mov     [rsp+arg_0], rbx
0x180030e89  push    rdi
0x180030e8a  sub     rsp, 240h
0x180030e91  mov     rax, cs:__security_cookie
0x180030e98  xor     rax, rsp
0x180030e9b  mov     [rsp+248h+var_18], rax
0x180030ea3  mov     rdi, rdx
0x180030ea6  mov     qword ptr [r8], 0
0x180030ead  lea     rdx, [rsp+248h+pszPath]
0x180030eb2  mov     ecx, 104h
0x180030eb7  mov     rbx, r8
0x180030eba  call    cs:__imp_GetTempPath2W
0x180030ec0  dec     eax
0x180030ec2  cmp     eax, 103h
0x180030ec7  ja      short loc_180030F38
0x180030ec9  lea     r8, pszMore; "MicroImageDir"
0x180030ed0  mov     edx, 104h; cchPath
0x180030ed5  lea     rcx, [rsp+248h+pszPath]; pszPath
0x180030eda  call    cs:__imp_PathCchAppend
0x180030ee0  test    eax, eax
0x180030ee2  js      short loc_180030F3D
0x180030ee4  xor     edx, edx; lpSecurityAttributes
0x180030ee6  lea     rcx, [rsp+248h+pszPath]; lpPathName
0x180030eeb  call    cs:__imp_CreateDirectoryW
0x180030ef1  test    eax, eax
0x180030ef3  jnz     short loc_180030F11
0x180030ef5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180030efa  test    eax, eax
0x180030efc  jle     short loc_180030F08
0x180030efe  movzx   eax, ax
0x180030f01  or      eax, 80070000h
0x180030f06  test    eax, eax
0x180030f08  jns     short loc_180030F11
0x180030f0a  cmp     eax, 800700B7h
0x180030f0f  jnz     short loc_180030F3D
0x180030f11  mov     r8, rdi; pszMore
0x180030f14  lea     rcx, [rsp+248h+pszPath]; pszPath
0x180030f19  mov     edx, 104h; cchPath
0x180030f1e  call    cs:__imp_PathCchAppend
0x180030f24  test    eax, eax
0x180030f26  js      short loc_180030F3D
0x180030f28  mov     rdx, rbx; ppwsz
0x180030f2b  lea     rcx, [rsp+248h+pszPath]; psz
0x180030f30  call    cs:__imp_SHStrDupW
0x180030f36  jmp     short loc_180030F3D
0x180030f38  mov     eax, 8007007Ah
0x180030f3d  mov     rcx, [rsp+248h+var_18]
0x180030f45  xor     rcx, rsp; StackCookie
0x180030f48  call    __security_check_cookie
0x180030f4d  mov     rbx, [rsp+248h+arg_0]
0x180030f55  add     rsp, 240h
0x180030f5c  pop     rdi
0x180030f5d  retn
```
