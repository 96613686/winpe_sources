# DeleteSystemDataRegistryKeyForUser(void *)

- ea: `0x180008828`
- end: `0x1800088f0`
- name: `?DeleteSystemDataRegistryKeyForUser@@YAJPEAX@Z`
- size: `200`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180006890`

## callees

- `0x180002230`
- `0x180005968`
- `0x180008828`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000885b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000885b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800088cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800088cf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800088b5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800088b5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180008851`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180008851`

## string_xrefs

- `0x180008881`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SystemProtectedUserData`

## pseudocode

```c
__int64 __fastcall DeleteSystemDataRegistryKeyForUser(void *a1)
{
  signed int LastError; // eax
  signed int v2; // ebx
  LSTATUS v3; // eax
  LPWSTR StringSid; // [rsp+30h] [rbp-238h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-228h] BYREF

  StringSid = 0;
  if ( ConvertSidToStringSidW(a1, &StringSid) )
  {
    v2 = StringCchPrintfW(
           SubKey,
           0x104u,
           L"%s\\%s",
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SystemProtectedUserData",
           StringSid);
    if ( v2 >= 0 )
    {
      v3 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, SubKey);
      v2 = v3;
      if ( v3 > 0 )
        v2 = (unsigned __int16)v3 | 0x80070000;
    }
    LocalFree(StringSid);
  }
  else
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( v2 >= 0 )
      return (unsigned int)-2147467259;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180008828  push    rbx
0x18000882a  sub     rsp, 260h
0x180008831  mov     rax, cs:__security_cookie
0x180008838  xor     rax, rsp
0x18000883b  mov     [rsp+268h+var_18], rax
0x180008843  lea     rdx, [rsp+268h+StringSid]; StringSid
0x180008848  mov     [rsp+268h+StringSid], 0
0x180008851  call    cs:__imp_ConvertSidToStringSidW
0x180008857  test    eax, eax
0x180008859  jnz     short loc_18000887C
0x18000885b  call    cs:__imp_GetLastError
0x180008861  mov     ebx, eax
0x180008863  test    eax, eax
0x180008865  jle     short loc_180008870
0x180008867  movzx   ebx, ax
0x18000886a  or      ebx, 80070000h
0x180008870  test    ebx, ebx
0x180008872  mov     eax, 80004005h
0x180008877  cmovns  ebx, eax
0x18000887a  jmp     short loc_1800088D5
0x18000887c  mov     rax, [rsp+268h+StringSid]
0x180008881  lea     r9, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180008888  lea     r8, aSS; "%s\\%s"
0x18000888f  mov     [rsp+268h+var_248], rax
0x180008894  mov     edx, 104h; unsigned __int64
0x180008899  lea     rcx, [rsp+268h+SubKey]; unsigned __int16 *
0x18000889e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800088a3  mov     ebx, eax
0x1800088a5  test    eax, eax
0x1800088a7  js      short loc_1800088CA
0x1800088a9  lea     rdx, [rsp+268h+SubKey]; lpSubKey
0x1800088ae  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800088b5  call    cs:__imp_RegDeleteTreeW
0x1800088bb  mov     ebx, eax
0x1800088bd  test    eax, eax
0x1800088bf  jle     short loc_1800088CA
0x1800088c1  movzx   ebx, ax
0x1800088c4  or      ebx, 80070000h
0x1800088ca  mov     rcx, [rsp+268h+StringSid]; hMem
0x1800088cf  call    cs:__imp_LocalFree
0x1800088d5  mov     eax, ebx
0x1800088d7  mov     rcx, [rsp+268h+var_18]
0x1800088df  xor     rcx, rsp; StackCookie
0x1800088e2  call    __security_check_cookie
0x1800088e7  add     rsp, 260h
0x1800088ee  pop     rbx
0x1800088ef  retn
```
