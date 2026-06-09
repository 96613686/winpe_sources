# CLogonUser::makeProfilePrivate(short)

- ea: `0x18002e980`
- end: `0x18002ea73`
- name: `?makeProfilePrivate@CLogonUser@@UEAAJF@Z`
- size: `243`
- prototype: `__int64 __fastcall(CLogonUser *__hidden this, __int16)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18002d6e4`
- `0x18002d77c`
- `0x18002e980`
- `0x1800772c0`

## import_xrefs

- `ntshrui!SetFolderPermissionsForSharing` at `0x18002ea3f`
- `ntshrui!SetFolderPermissionsForSharing` at `0x18002ea3f`
- `SHLWAPI!PathCombineW` at `0x18002e9e6`
- `SHLWAPI!PathCombineW` at `0x18002e9e6`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x18002ea1b`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x18002ea1b`

## string_xrefs

- `0x18002e9fe`: `ProfileImagePath`

## pseudocode

```c
__int64 __fastcall CLogonUser::makeProfilePrivate(const WCHAR **this, __int16 a2)
{
  int IsGuestAccessMode; // ebx
  const WCHAR *v5; // r8
  DWORD pcbData[4]; // [rsp+30h] [rbp-238h] BYREF
  WCHAR pszDest[264]; // [rsp+40h] [rbp-228h] BYREF

  IsGuestAccessMode = _IsGuestAccessMode();
  if ( IsGuestAccessMode >= 0 )
  {
    IsGuestAccessMode = -2147467259;
    CLogonUser::_LookupUserSid((CLogonUser *)this);
    v5 = this[396];
    if ( v5 )
    {
      pcbData[0] = 520;
      if ( PathCombineW(pszDest, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList", v5) )
      {
        if ( !SHGetValueW(HKEY_LOCAL_MACHINE, pszDest, L"ProfileImagePath", 0, pszDest, pcbData)
          && (unsigned int)SetFolderPermissionsForSharing(pszDest, this[396], a2 != -1, 0) )
        {
          return 0;
        }
      }
    }
  }
  return (unsigned int)IsGuestAccessMode;
}

```

## disassembly

```asm
0x18002e980  mov     [rsp+arg_8], rbx
0x18002e985  mov     [rsp+arg_10], rsi
0x18002e98a  push    rdi
0x18002e98b  sub     rsp, 260h
0x18002e992  mov     rax, cs:__security_cookie
0x18002e999  xor     rax, rsp
0x18002e99c  mov     [rsp+268h+var_18], rax
0x18002e9a4  movzx   esi, dx
0x18002e9a7  mov     rdi, rcx
0x18002e9aa  call    ?_IsGuestAccessMode@@YAJXZ; _IsGuestAccessMode(void)
0x18002e9af  mov     ebx, eax
0x18002e9b1  test    eax, eax
0x18002e9b3  js      loc_18002EA4C
0x18002e9b9  mov     rcx, rdi; this
0x18002e9bc  mov     ebx, 80004005h
0x18002e9c1  call    ?_LookupUserSid@CLogonUser@@AEAAJXZ; CLogonUser::_LookupUserSid(void)
0x18002e9c6  mov     r8, [rdi+0C60h]; pszFile
0x18002e9cd  test    r8, r8
0x18002e9d0  jz      short loc_18002EA4C
0x18002e9d2  lea     rdx, pszDir; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002e9d9  mov     [rsp+268h+var_238], 208h
0x18002e9e1  lea     rcx, [rsp+268h+pszDest]; pszDest
0x18002e9e6  call    cs:__imp_PathCombineW
0x18002e9ec  test    rax, rax
0x18002e9ef  jz      short loc_18002EA4C
0x18002e9f1  lea     rax, [rsp+268h+var_238]
0x18002e9f6  xor     r9d, r9d; pdwType
0x18002e9f9  mov     [rsp+268h+pcbData], rax; pcbData
0x18002e9fe  lea     r8, aProfileimagepa; "ProfileImagePath"
0x18002ea05  lea     rax, [rsp+268h+pszDest]
0x18002ea0a  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002ea11  lea     rdx, [rsp+268h+pszDest]; pszSubKey
0x18002ea16  mov     [rsp+268h+pvData], rax; pvData
0x18002ea1b  call    cs:__imp_SHGetValueW
0x18002ea21  test    eax, eax
0x18002ea23  jnz     short loc_18002EA4C
0x18002ea25  mov     rdx, [rdi+0C60h]
0x18002ea2c  lea     rcx, [rsp+268h+pszDest]
0x18002ea31  xor     r8d, r8d
0x18002ea34  cmp     si, 0FFFFh
0x18002ea38  setnz   r8b
0x18002ea3c  xor     r9d, r9d
0x18002ea3f  call    cs:__imp_SetFolderPermissionsForSharing
0x18002ea45  xor     ecx, ecx
0x18002ea47  test    eax, eax
0x18002ea49  cmovnz  ebx, ecx
0x18002ea4c  mov     eax, ebx
0x18002ea4e  mov     rcx, [rsp+268h+var_18]
0x18002ea56  xor     rcx, rsp; StackCookie
0x18002ea59  call    __security_check_cookie
0x18002ea5e  lea     r11, [rsp+268h+var_8]
0x18002ea66  mov     rbx, [r11+18h]
0x18002ea6a  mov     rsi, [r11+20h]
0x18002ea6e  mov     rsp, r11
0x18002ea71  pop     rdi
0x18002ea72  retn
```
