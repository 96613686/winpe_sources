# InternetTime_GetW32TimeServer(ushort *,ulong)

- ea: `0x180016a44`
- end: `0x180016bb4`
- name: `?InternetTime_GetW32TimeServer@@YAJPEAGK@Z`
- size: `368`
- prototype: `__int64 __fastcall(PCWSTR pszFirst, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c300`

## callees

- `0x180016a44`
- `0x180028f2e`
- `0x180028f60`

## import_xrefs

- `SHLWAPI!StrStrW` at `0x180016b70`
- `SHLWAPI!StrStrW` at `0x180016b70`
- `SHLWAPI!SHGetValueW` at `0x180016ac5`
- `SHLWAPI!SHGetValueW` at `0x180016b4d`
- `SHLWAPI!SHGetValueW` at `0x180016ac5`
- `SHLWAPI!SHGetValueW` at `0x180016b4d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016b0c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016b0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016b88`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016b88`

## pseudocode

```c
__int64 __fastcall InternetTime_GetW32TimeServer(WCHAR *pszFirst)
{
  LSTATUS v2; // eax
  signed int v3; // ebx
  LSTATUS v4; // eax
  LSTATUS v5; // eax
  PWSTR v6; // rcx
  DWORD pcbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pdwType; // [rsp+34h] [rbp-CCh] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR pszValue; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v12[526]; // [rsp+42h] [rbp-BEh] BYREF

  pdwType = 0;
  pszValue = 0;
  memset_0(v12, 0, 0x206u);
  pcbData = 520;
  v2 = SHGetValueW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\DateTime\\Servers",
         0,
         &pdwType,
         &pszValue,
         &pcbData);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 >= 0 )
  {
    phkResult = 0;
    v4 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\DateTime\\Servers",
           0,
           0x20019u,
           &phkResult);
    v3 = v4;
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    if ( v3 >= 0 )
    {
      pcbData = 512;
      v5 = SHGetValueW(phkResult, 0, &pszValue, &pdwType, pszFirst, &pcbData);
      v3 = v5;
      if ( v5 > 0 )
        v3 = (unsigned __int16)v5 | 0x80070000;
      if ( v3 >= 0 )
      {
        v6 = StrStrW(pszFirst, L",0x");
        if ( v6 )
          *v6 = 0;
        RegCloseKey(phkResult);
      }
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180016a44  mov     [rsp-8+arg_8], rbx
0x180016a49  mov     [rsp-8+arg_10], rdi
0x180016a4e  push    rbp
0x180016a4f  lea     rbp, [rsp-160h]
0x180016a57  sub     rsp, 260h
0x180016a5e  mov     rax, cs:__security_cookie
0x180016a65  xor     rax, rsp
0x180016a68  mov     [rbp+160h+var_10], rax
0x180016a6f  mov     rdi, rcx
0x180016a72  mov     [rsp+260h+pdwType], 0
0x180016a7a  xor     eax, eax
0x180016a7c  lea     rcx, [rsp+260h+var_21E]; void *
0x180016a81  xor     edx, edx; Val
0x180016a83  mov     [rsp+260h+pszValue], ax
0x180016a88  mov     r8d, 206h; Size
0x180016a8e  call    memset_0
0x180016a93  lea     rax, [rsp+260h+var_230]
0x180016a98  mov     [rsp+260h+var_230], 208h
0x180016aa0  mov     [rsp+260h+pcbData], rax; pcbData
0x180016aa5  lea     r9, [rsp+260h+pdwType]; pdwType
0x180016aaa  lea     rax, [rsp+260h+pszValue]
0x180016aaf  xor     r8d, r8d; pszValue
0x180016ab2  lea     rdx, pszSubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180016ab9  mov     [rsp+260h+pvData], rax; pvData
0x180016abe  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180016ac5  call    cs:__imp_SHGetValueW
0x180016acb  mov     ebx, eax
0x180016acd  test    eax, eax
0x180016acf  jle     short loc_180016ADA
0x180016ad1  movzx   ebx, ax
0x180016ad4  or      ebx, 80070000h
0x180016ada  test    ebx, ebx
0x180016adc  js      loc_180016B8E
0x180016ae2  lea     rax, [rsp+260h+phkResult]
0x180016ae7  mov     [rsp+260h+phkResult], 0
0x180016af0  mov     r9d, 20019h; samDesired
0x180016af6  mov     [rsp+260h+pvData], rax; phkResult
0x180016afb  xor     r8d, r8d; ulOptions
0x180016afe  lea     rdx, pszSubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180016b05  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016b0c  call    cs:__imp_RegOpenKeyExW
0x180016b12  mov     ebx, eax
0x180016b14  test    eax, eax
0x180016b16  jle     short loc_180016B21
0x180016b18  movzx   ebx, ax
0x180016b1b  or      ebx, 80070000h
0x180016b21  test    ebx, ebx
0x180016b23  js      short loc_180016B8E
0x180016b25  mov     rcx, [rsp+260h+phkResult]; hkey
0x180016b2a  lea     rax, [rsp+260h+var_230]
0x180016b2f  mov     [rsp+260h+pcbData], rax; pcbData
0x180016b34  lea     r9, [rsp+260h+pdwType]; pdwType
0x180016b39  lea     r8, [rsp+260h+pszValue]; pszValue
0x180016b3e  mov     [rsp+260h+pvData], rdi; pvData
0x180016b43  xor     edx, edx; pszSubKey
0x180016b45  mov     [rsp+260h+var_230], 200h
0x180016b4d  call    cs:__imp_SHGetValueW
0x180016b53  mov     ebx, eax
0x180016b55  test    eax, eax
0x180016b57  jle     short loc_180016B62
0x180016b59  movzx   ebx, ax
0x180016b5c  or      ebx, 80070000h
0x180016b62  test    ebx, ebx
0x180016b64  js      short loc_180016B8E
0x180016b66  lea     rdx, pszSrch; ",0x"
0x180016b6d  mov     rcx, rdi; pszFirst
0x180016b70  call    cs:__imp_StrStrW
0x180016b76  mov     rcx, rax
0x180016b79  test    rax, rax
0x180016b7c  jz      short loc_180016B83
0x180016b7e  xor     eax, eax
0x180016b80  mov     [rcx], ax
0x180016b83  mov     rcx, [rsp+260h+phkResult]; hKey
0x180016b88  call    cs:__imp_RegCloseKey
0x180016b8e  mov     eax, ebx
0x180016b90  mov     rcx, [rbp+160h+var_10]
0x180016b97  xor     rcx, rsp; StackCookie
0x180016b9a  call    __security_check_cookie
0x180016b9f  lea     r11, [rsp+260h+var_s0]
0x180016ba7  mov     rbx, [r11+18h]
0x180016bab  mov     rdi, [r11+20h]
0x180016baf  mov     rsp, r11
0x180016bb2  pop     rbp
0x180016bb3  retn
```
