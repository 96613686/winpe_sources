# CLogonUser::get_isProfilePrivate(short *)

- ea: `0x18002e5f0`
- end: `0x18002e709`
- name: `?get_isProfilePrivate@CLogonUser@@UEAAJPEAF@Z`
- size: `281`
- prototype: `__int64 __fastcall(CLogonUser *__hidden this, __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18002d6e4`
- `0x18002d77c`
- `0x18002e5f0`
- `0x1800772c0`

## import_xrefs

- `ntshrui!IsFolderPrivateForUser` at `0x18002e6c5`
- `ntshrui!IsFolderPrivateForUser` at `0x18002e6c5`
- `SHLWAPI!PathCombineW` at `0x18002e66e`
- `SHLWAPI!PathCombineW` at `0x18002e66e`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x18002e6a3`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x18002e6a3`

## string_xrefs

- `0x18002e686`: `ProfileImagePath`

## pseudocode

```c
__int64 __fastcall CLogonUser::get_isProfilePrivate(const WCHAR **this, __int16 *a2)
{
  int IsGuestAccessMode; // ebx
  const WCHAR *v6; // r8
  const WCHAR *v7; // rdx
  int v8; // [rsp+30h] [rbp-238h] BYREF
  DWORD pcbData[3]; // [rsp+34h] [rbp-234h] BYREF
  WCHAR pszDest[264]; // [rsp+40h] [rbp-228h] BYREF

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  IsGuestAccessMode = _IsGuestAccessMode();
  if ( IsGuestAccessMode >= 0 )
  {
    IsGuestAccessMode = -2147467259;
    CLogonUser::_LookupUserSid((CLogonUser *)this);
    v6 = this[396];
    if ( v6 )
    {
      pcbData[0] = 520;
      if ( PathCombineW(pszDest, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList", v6) )
      {
        if ( !SHGetValueW(HKEY_LOCAL_MACHINE, pszDest, L"ProfileImagePath", 0, pszDest, pcbData) )
        {
          v7 = this[396];
          v8 = 0;
          if ( (unsigned int)IsFolderPrivateForUser(pszDest, v7, &v8, 0) )
          {
            if ( (v8 & 4) == 0 )
            {
              if ( (v8 & 1) != 0 )
                *a2 = -1;
              return 0;
            }
          }
        }
      }
    }
  }
  return (unsigned int)IsGuestAccessMode;
}

```

## disassembly

```asm
0x18002e5f0  mov     [rsp+arg_10], rbx
0x18002e5f5  mov     [rsp+arg_18], rsi
0x18002e5fa  push    rdi
0x18002e5fb  sub     rsp, 260h
0x18002e602  mov     rax, cs:__security_cookie
0x18002e609  xor     rax, rsp
0x18002e60c  mov     [rsp+268h+var_18], rax
0x18002e614  mov     rdi, rdx
0x18002e617  mov     rsi, rcx
0x18002e61a  test    rdx, rdx
0x18002e61d  jnz     short loc_18002E629
0x18002e61f  mov     eax, 80004003h
0x18002e624  jmp     loc_18002E6E4
0x18002e629  xor     eax, eax
0x18002e62b  mov     [rdx], ax
0x18002e62e  call    ?_IsGuestAccessMode@@YAJXZ; _IsGuestAccessMode(void)
0x18002e633  mov     ebx, eax
0x18002e635  test    eax, eax
0x18002e637  js      loc_18002E6E2
0x18002e63d  mov     rcx, rsi; this
0x18002e640  mov     ebx, 80004005h
0x18002e645  call    ?_LookupUserSid@CLogonUser@@AEAAJXZ; CLogonUser::_LookupUserSid(void)
0x18002e64a  mov     r8, [rsi+0C60h]; pszFile
0x18002e651  test    r8, r8
0x18002e654  jz      loc_18002E6E2
0x18002e65a  lea     rdx, pszDir; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002e661  mov     [rsp+268h+var_234], 208h
0x18002e669  lea     rcx, [rsp+268h+pszDest]; pszDest
0x18002e66e  call    cs:__imp_PathCombineW
0x18002e674  test    rax, rax
0x18002e677  jz      short loc_18002E6E2
0x18002e679  lea     rax, [rsp+268h+var_234]
0x18002e67e  xor     r9d, r9d; pdwType
0x18002e681  mov     [rsp+268h+pcbData], rax; pcbData
0x18002e686  lea     r8, aProfileimagepa; "ProfileImagePath"
0x18002e68d  lea     rax, [rsp+268h+pszDest]
0x18002e692  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002e699  lea     rdx, [rsp+268h+pszDest]; pszSubKey
0x18002e69e  mov     [rsp+268h+pvData], rax; pvData
0x18002e6a3  call    cs:__imp_SHGetValueW
0x18002e6a9  test    eax, eax
0x18002e6ab  jnz     short loc_18002E6E2
0x18002e6ad  mov     rdx, [rsi+0C60h]
0x18002e6b4  lea     r8, [rsp+268h+var_238]
0x18002e6b9  xor     r9d, r9d
0x18002e6bc  mov     [rsp+268h+var_238], eax
0x18002e6c0  lea     rcx, [rsp+268h+pszDest]
0x18002e6c5  call    cs:__imp_IsFolderPrivateForUser
0x18002e6cb  test    eax, eax
0x18002e6cd  jz      short loc_18002E6E2
0x18002e6cf  mov     eax, [rsp+268h+var_238]
0x18002e6d3  test    al, 4
0x18002e6d5  jnz     short loc_18002E6E2
0x18002e6d7  test    al, 1
0x18002e6d9  jz      short loc_18002E6E0
0x18002e6db  mov     word ptr [rdi], 0FFFFh
0x18002e6e0  xor     ebx, ebx
0x18002e6e2  mov     eax, ebx
0x18002e6e4  mov     rcx, [rsp+268h+var_18]
0x18002e6ec  xor     rcx, rsp; StackCookie
0x18002e6ef  call    __security_check_cookie
0x18002e6f4  lea     r11, [rsp+268h+var_8]
0x18002e6fc  mov     rbx, [r11+20h]
0x18002e700  mov     rsi, [r11+28h]
0x18002e704  mov     rsp, r11
0x18002e707  pop     rdi
0x18002e708  retn
```
