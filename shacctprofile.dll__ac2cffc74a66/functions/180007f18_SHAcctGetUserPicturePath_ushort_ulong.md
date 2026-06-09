# SHAcctGetUserPicturePath(ushort *,ulong)

- ea: `0x180007f18`
- end: `0x180007fbc`
- name: `?SHAcctGetUserPicturePath@@YAJPEAGK@Z`
- size: `164`
- prototype: `signed int __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000834c`
- `0x18000855c`

## callees

- `0x180002230`
- `0x180005968`
- `0x180007f18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f52`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180007f48`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180007f48`

## string_xrefs

- `0x180007f3b`: `%ProgramData%`

## pseudocode

```c
signed int __fastcall SHAcctGetUserPicturePath(unsigned __int16 *a1)
{
  DWORD v2; // eax
  signed int result; // eax
  WCHAR Dst[264]; // [rsp+30h] [rbp-228h] BYREF

  v2 = ExpandEnvironmentStringsW(L"%ProgramData%", Dst, 0x104u);
  if ( v2 )
  {
    if ( v2 <= 0x104 )
      return StringCchPrintfW(a1, 0x104u, L"%s\\%s", Dst, L"Microsoft\\User Account Pictures");
    else
      return -2147024774;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    if ( result >= 0 )
      return -2147467259;
  }
  return result;
}

```

## disassembly

```asm
0x180007f18  push    rbx
0x180007f1a  sub     rsp, 250h
0x180007f21  mov     rax, cs:__security_cookie
0x180007f28  xor     rax, rsp
0x180007f2b  mov     [rsp+258h+var_18], rax
0x180007f33  mov     rbx, rcx
0x180007f36  lea     rdx, [rsp+258h+Dst]; lpDst
0x180007f3b  lea     rcx, Src; "%ProgramData%"
0x180007f42  mov     r8d, 104h; nSize
0x180007f48  call    cs:__imp_ExpandEnvironmentStringsW
0x180007f4e  test    eax, eax
0x180007f50  jnz     short loc_180007F70
0x180007f52  call    cs:__imp_GetLastError
0x180007f58  test    eax, eax
0x180007f5a  jle     short loc_180007F64
0x180007f5c  movzx   eax, ax
0x180007f5f  or      eax, 80070000h
0x180007f64  test    eax, eax
0x180007f66  mov     ecx, 80004005h
0x180007f6b  cmovns  eax, ecx
0x180007f6e  jmp     short loc_180007FA3
0x180007f70  cmp     eax, 104h
0x180007f75  jbe     short loc_180007F7E
0x180007f77  mov     eax, 8007007Ah
0x180007f7c  jmp     short loc_180007FA3
0x180007f7e  lea     rax, aMicrosoftUserA; "Microsoft\\User Account Pictures"
0x180007f85  mov     edx, 104h; unsigned __int64
0x180007f8a  lea     r9, [rsp+258h+Dst]
0x180007f8f  mov     [rsp+258h+var_238], rax
0x180007f94  lea     r8, aSS; "%s\\%s"
0x180007f9b  mov     rcx, rbx; unsigned __int16 *
0x180007f9e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007fa3  mov     rcx, [rsp+258h+var_18]
0x180007fab  xor     rcx, rsp; StackCookie
0x180007fae  call    __security_check_cookie
0x180007fb3  add     rsp, 250h
0x180007fba  pop     rbx
0x180007fbb  retn
```
