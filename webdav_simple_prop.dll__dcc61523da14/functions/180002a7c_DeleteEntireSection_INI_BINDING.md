# DeleteEntireSection(INI_BINDING *)

- ea: `0x180002a7c`
- end: `0x180002b2e`
- name: `?DeleteEntireSection@@YAJPEAUINI_BINDING@@@Z`
- size: `178`
- prototype: `signed int __fastcall(LPCWSTR *)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180001c30`
- `0x180002080`
- `0x180002520`

## callees

- `0x180002a7c`
- `0x180003490`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002aab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ae9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002aab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ae9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180002adf`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180002adf`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180002b0f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180002b0f`
- `KERNEL32!WritePrivateProfileStringW` at `0x180002aa1`
- `KERNEL32!WritePrivateProfileStringW` at `0x180002aa1`

## pseudocode

```c
signed int __fastcall DeleteEntireSection(LPCWSTR *a1)
{
  signed int result; // eax
  bool v3; // sf
  const WCHAR *v4; // rcx
  __int128 FileInformation; // [rsp+20h] [rbp-38h] BYREF
  __int128 v6; // [rsp+30h] [rbp-28h]
  unsigned int v7; // [rsp+40h] [rbp-18h]

  if ( WritePrivateProfileStringW(a1[11], 0, 0, a1[4]) )
    goto LABEL_5;
  result = GetLastError();
  v3 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v3 = result < 0;
  }
  if ( !v3 )
  {
LABEL_5:
    v4 = a1[4];
    v7 = 0;
    FileInformation = 0;
    v6 = 0;
    if ( GetFileAttributesExW(v4, GetFileExInfoStandard, &FileInformation)
      && (HIDWORD(v6) || v7 > 8 || DeleteFileW(a1[4])) )
    {
      return 0;
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002a7c  push    rbx
0x180002a7e  sub     rsp, 50h
0x180002a82  mov     rax, cs:__security_cookie
0x180002a89  xor     rax, rsp
0x180002a8c  mov     [rsp+58h+var_10], rax
0x180002a91  mov     r9, [rcx+20h]; lpFileName
0x180002a95  mov     rbx, rcx
0x180002a98  mov     rcx, [rcx+58h]; lpAppName
0x180002a9c  xor     r8d, r8d; lpString
0x180002a9f  xor     edx, edx; lpKeyName
0x180002aa1  call    cs:__imp_WritePrivateProfileStringW
0x180002aa7  test    eax, eax
0x180002aa9  jnz     short loc_180002AC1
0x180002aab  call    cs:__imp_GetLastError
0x180002ab1  test    eax, eax
0x180002ab3  jle     short loc_180002ABF
0x180002ab5  movzx   eax, ax
0x180002ab8  or      eax, 80070000h
0x180002abd  test    eax, eax
0x180002abf  js      short loc_180002B1B
0x180002ac1  mov     rcx, [rbx+20h]; lpFileName
0x180002ac5  lea     r8, [rsp+58h+FileInformation]; lpFileInformation
0x180002aca  xorps   xmm0, xmm0
0x180002acd  xor     eax, eax
0x180002acf  xor     edx, edx; fInfoLevelId
0x180002ad1  mov     [rsp+58h+var_18], eax
0x180002ad5  movups  [rsp+58h+FileInformation], xmm0
0x180002ada  movups  [rsp+58h+var_28], xmm0
0x180002adf  call    cs:__imp_GetFileAttributesExW
0x180002ae5  test    eax, eax
0x180002ae7  jnz     short loc_180002AFD
0x180002ae9  call    cs:__imp_GetLastError
0x180002aef  test    eax, eax
0x180002af1  jle     short loc_180002B1B
0x180002af3  movzx   eax, ax
0x180002af6  or      eax, 80070000h
0x180002afb  jmp     short loc_180002B1B
0x180002afd  cmp     dword ptr [rsp+58h+var_28+0Ch], 0
0x180002b02  jnz     short loc_180002B19
0x180002b04  cmp     [rsp+58h+var_18], 8
0x180002b09  ja      short loc_180002B19
0x180002b0b  mov     rcx, [rbx+20h]; lpFileName
0x180002b0f  call    cs:__imp_DeleteFileW
0x180002b15  test    eax, eax
0x180002b17  jz      short loc_180002AE9
0x180002b19  xor     eax, eax
0x180002b1b  mov     rcx, [rsp+58h+var_10]
0x180002b20  xor     rcx, rsp; StackCookie
0x180002b23  call    __security_check_cookie
0x180002b28  add     rsp, 50h
0x180002b2c  pop     rbx
0x180002b2d  retn
```
