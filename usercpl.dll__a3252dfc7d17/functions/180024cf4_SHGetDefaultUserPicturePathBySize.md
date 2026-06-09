# SHGetDefaultUserPicturePathBySize

- ea: `0x180024cf4`
- end: `0x180024e2d`
- name: `SHGetDefaultUserPicturePathBySize`
- size: `313`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180060bc4`
- `0x180061f48`

## callees

- `0x180006f2c`
- `0x180024cf4`
- `0x1800772c0`

## import_xrefs

- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180024db9`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180024db9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024d34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024d34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024e04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024e04`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180024d2a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180024d2a`

## string_xrefs

- `0x180024d16`: `%ProgramData%`

## pseudocode

```c
__int64 __fastcall SHGetDefaultUserPicturePathBySize(__int64 a1, int a2, unsigned __int16 *a3)
{
  DWORD v5; // eax
  signed int LastError; // eax
  int v7; // ebx
  const WCHAR *v8; // rcx
  LPWSTR v9; // rcx
  LPWSTR ppwsz; // [rsp+30h] [rbp-238h] BYREF
  WCHAR Dst[264]; // [rsp+40h] [rbp-228h] BYREF

  v5 = ExpandEnvironmentStringsW(L"%ProgramData%", Dst, 0x104u);
  if ( v5 )
  {
    if ( v5 <= 0x104 )
    {
      ppwsz = 0;
      switch ( a2 )
      {
        case 32:
          v8 = L"user-32.png";
          break;
        case 40:
          v8 = L"user-40.png";
          break;
        case 48:
          v8 = L"user-48.png";
          break;
        case 192:
          v8 = L"user-192.png";
          break;
        default:
          v8 = L"user.png";
          break;
      }
      v7 = SHStrDupW(v8, &ppwsz);
      if ( v7 >= 0 )
        v7 = StringCchPrintfW(a3, 0x104u, L"%s\\%s\\%s", Dst, L"Microsoft\\User Account Pictures", ppwsz);
      v9 = ppwsz;
      ppwsz = 0;
      CoTaskMemFree(v9);
    }
    else
    {
      return (unsigned int)-2147024774;
    }
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 >= 0 )
      return (unsigned int)-2147467259;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180024cf4  mov     [rsp+arg_0], rbx
0x180024cf9  push    rdi
0x180024cfa  sub     rsp, 260h
0x180024d01  mov     rax, cs:__security_cookie
0x180024d08  xor     rax, rsp
0x180024d0b  mov     [rsp+268h+var_18], rax
0x180024d13  mov     rdi, r8
0x180024d16  lea     rcx, aProgramdata; "%ProgramData%"
0x180024d1d  mov     ebx, edx
0x180024d1f  mov     r8d, 104h; nSize
0x180024d25  lea     rdx, [rsp+268h+Dst]; lpDst
0x180024d2a  call    cs:__imp_ExpandEnvironmentStringsW
0x180024d30  test    eax, eax
0x180024d32  jnz     short loc_180024D58
0x180024d34  call    cs:__imp_GetLastError
0x180024d3a  mov     ebx, eax
0x180024d3c  test    eax, eax
0x180024d3e  jle     short loc_180024D49
0x180024d40  movzx   ebx, ax
0x180024d43  or      ebx, 80070000h
0x180024d49  test    ebx, ebx
0x180024d4b  mov     eax, 80004005h
0x180024d50  cmovns  ebx, eax
0x180024d53  jmp     loc_180024E0A
0x180024d58  cmp     eax, 104h
0x180024d5d  jbe     short loc_180024D69
0x180024d5f  mov     ebx, 8007007Ah
0x180024d64  jmp     loc_180024E0A
0x180024d69  mov     [rsp+268h+ppwsz], 0
0x180024d72  lea     rdx, [rsp+268h+ppwsz]; ppwsz
0x180024d77  cmp     ebx, 20h ; ' '
0x180024d7a  jz      short loc_180024DB2
0x180024d7c  cmp     ebx, 28h ; '('
0x180024d7f  jz      short loc_180024DA9
0x180024d81  cmp     ebx, 30h ; '0'
0x180024d84  jz      short loc_180024DA0
0x180024d86  cmp     ebx, 0C0h
0x180024d8c  jz      short loc_180024D97
0x180024d8e  lea     rcx, aUserPng; "user.png"
0x180024d95  jmp     short loc_180024DB9
0x180024d97  lea     rcx, aUser192Png; "user-192.png"
0x180024d9e  jmp     short loc_180024DB9
0x180024da0  lea     rcx, aUser48Png; "user-48.png"
0x180024da7  jmp     short loc_180024DB9
0x180024da9  lea     rcx, aUser40Png; "user-40.png"
0x180024db0  jmp     short loc_180024DB9
0x180024db2  lea     rcx, aUser32Png; "user-32.png"
0x180024db9  call    cs:__imp_SHStrDupW
0x180024dbf  mov     ebx, eax
0x180024dc1  test    eax, eax
0x180024dc3  js      short loc_180024DF6
0x180024dc5  mov     rax, [rsp+268h+ppwsz]
0x180024dca  lea     r9, [rsp+268h+Dst]
0x180024dcf  mov     [rsp+268h+var_240], rax
0x180024dd4  lea     r8, aSSS; "%s\\%s\\%s"
0x180024ddb  lea     rax, aMicrosoftUserA; "Microsoft\\User Account Pictures"
0x180024de2  mov     edx, 104h; unsigned __int64
0x180024de7  mov     rcx, rdi; unsigned __int16 *
0x180024dea  mov     [rsp+268h+var_248], rax
0x180024def  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180024df4  mov     ebx, eax
0x180024df6  mov     rcx, [rsp+268h+ppwsz]; pv
0x180024dfb  mov     [rsp+268h+ppwsz], 0
0x180024e04  call    cs:__imp_CoTaskMemFree
0x180024e0a  mov     eax, ebx
0x180024e0c  mov     rcx, [rsp+268h+var_18]
0x180024e14  xor     rcx, rsp; StackCookie
0x180024e17  call    __security_check_cookie
0x180024e1c  mov     rbx, [rsp+268h+arg_0]
0x180024e24  add     rsp, 260h
0x180024e2b  pop     rdi
0x180024e2c  retn
```
