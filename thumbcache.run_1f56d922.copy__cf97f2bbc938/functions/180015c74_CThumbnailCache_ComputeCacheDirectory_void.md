# CThumbnailCache::_ComputeCacheDirectory(void)

- ea: `0x180015c74`
- end: `0x180015d2f`
- name: `?_ComputeCacheDirectory@CThumbnailCache@@AEAAJXZ`
- size: `187`
- prototype: `__int64 __fastcall(CThumbnailCache *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015868`
- `0x18002d7b0`
- `0x180040c80`
- `0x1800416d0`

## callees

- `0x180015c74`
- `0x180035830`
- `0x1800375fc`

## import_xrefs

- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x180015cd3`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x180015cd3`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetFolderPathAndSubDirW` at `0x180015d0d`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetFolderPathAndSubDirW` at `0x180015d0d`

## string_xrefs

- `0x180015cbd`: `SOFTWARE\Microsoft\Windows\CurrentVersion\ThumbnailCache`
- `0x180015ce2`: `Microsoft\Windows\ThumbnailCache`

## pseudocode

```c
HRESULT __fastcall CThumbnailCache::_ComputeCacheDirectory(CThumbnailCache *this)
{
  char *pszPath; // rbx
  char DIBSectionPresent; // al
  const WCHAR *pszSubDir; // rcx
  DWORD v5; // [rsp+30h] [rbp-18h] BYREF
  DWORD v6; // [rsp+34h] [rbp-14h] BYREF

  pszPath = (char *)this + 72;
  if ( *((_WORD *)this + 36) )
    return 0;
  v5 = 520;
  v6 = 2;
  if ( !SHGetValueW(
          HKEY_CURRENT_USER,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ThumbnailCache",
          L"Location",
          &v6,
          pszPath,
          &v5) )
    return 0;
  DIBSectionPresent = IsCreateDIBSectionPresent();
  pszSubDir = L"Microsoft\\Windows\\Explorer";
  if ( !DIBSectionPresent )
    pszSubDir = L"Microsoft\\Windows\\ThumbnailCache";
  return SHGetFolderPathAndSubDirW(0, 32796, 0, 0, pszSubDir, (LPWSTR)pszPath);
}

```

## disassembly

```asm
0x180015c74  mov     r11, rsp
0x180015c77  mov     [r11+10h], rbx
0x180015c7b  push    rdi
0x180015c7c  sub     rsp, 40h
0x180015c80  mov     rax, cs:__security_cookie
0x180015c87  xor     rax, rsp
0x180015c8a  mov     [rsp+48h+var_10], rax
0x180015c8f  lea     rbx, [rcx+48h]
0x180015c93  xor     edi, edi
0x180015c95  cmp     [rbx], di
0x180015c98  jnz     loc_180015D2B
0x180015c9e  lea     rax, [r11-18h]
0x180015ca2  mov     [rsp+48h+var_18], 208h
0x180015caa  mov     [r11-20h], rax
0x180015cae  lea     r9, [r11-14h]; pdwType
0x180015cb2  lea     r8, pszValue; "Location"
0x180015cb9  mov     [r11-28h], rbx
0x180015cbd  lea     rdx, pszSubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180015cc4  mov     [rsp+48h+var_14], 2
0x180015ccc  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180015cd3  call    cs:__imp_SHGetValueW
0x180015cd9  test    eax, eax
0x180015cdb  jz      short loc_180015D2B
0x180015cdd  call    IsCreateDIBSectionPresent
0x180015ce2  lea     rdx, pszSubDir; "Microsoft\\Windows\\ThumbnailCache"
0x180015ce9  mov     [rsp+48h+pszPath], rbx; pszPath
0x180015cee  test    al, al
0x180015cf0  lea     rcx, aMicrosoftWindo_1; "Microsoft\\Windows\\Explorer"
0x180015cf7  cmovz   rcx, rdx
0x180015cfb  xor     r9d, r9d; dwFlags
0x180015cfe  mov     [rsp+48h+pszSubDir], rcx; pszSubDir
0x180015d03  xor     r8d, r8d; hToken
0x180015d06  xor     ecx, ecx; hwnd
0x180015d08  mov     edx, 801Ch; csidl
0x180015d0d  call    cs:__imp_SHGetFolderPathAndSubDirW
0x180015d13  mov     rcx, [rsp+48h+var_10]
0x180015d18  xor     rcx, rsp; StackCookie
0x180015d1b  call    __security_check_cookie
0x180015d20  mov     rbx, [rsp+48h+arg_8]
0x180015d25  add     rsp, 40h
0x180015d29  pop     rdi
0x180015d2a  retn
0x180015d2b  mov     eax, edi
0x180015d2d  jmp     short loc_180015D13
```
