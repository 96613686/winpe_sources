# PathIsContentTypeW

- ea: `0x180020b20`
- end: `0x180020bca`
- name: `PathIsContentTypeW`
- size: `170`
- prototype: `BOOL __stdcall(LPCWSTR pszPath, LPCWSTR pszContentType)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800085b0`
- `0x180012550`
- `0x180020b20`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180020b50`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180020b50`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180020b98`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180020b98`

## pseudocode

```c
BOOL __stdcall PathIsContentTypeW(LPCWSTR pszPath, LPCWSTR pszContentType)
{
  BOOL v3; // ebx
  const WCHAR *ExtensionW; // rax
  DWORD pcchOut[4]; // [rsp+30h] [rbp-238h] BYREF
  WCHAR String1[264]; // [rsp+40h] [rbp-228h] BYREF

  v3 = 0;
  if ( pszPath )
  {
    ExtensionW = PathFindExtensionW(pszPath);
    if ( ExtensionW )
    {
      if ( *ExtensionW )
      {
        pcchOut[0] = 260;
        if ( AssocQueryStringW(0, ASSOCSTR_CONTENTTYPE, ExtensionW, 0, String1, pcchOut) >= 0 )
          LOBYTE(v3) = lstrcmpiW(String1, pszContentType) == 0;
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180020b20  mov     [rsp+arg_10], rbx
0x180020b25  mov     [rsp+arg_18], rsi
0x180020b2a  push    rdi
0x180020b2b  sub     rsp, 260h
0x180020b32  mov     rax, cs:__security_cookie
0x180020b39  xor     rax, rsp
0x180020b3c  mov     [rsp+268h+var_18], rax
0x180020b44  xor     esi, esi
0x180020b46  mov     rdi, rdx
0x180020b49  mov     ebx, esi
0x180020b4b  test    rcx, rcx
0x180020b4e  jz      short loc_180020BA3
0x180020b50  call    cs:__imp_PathFindExtensionW
0x180020b56  test    rax, rax
0x180020b59  jz      short loc_180020BA3
0x180020b5b  cmp     [rax], si
0x180020b5e  jz      short loc_180020BA3
0x180020b60  lea     rcx, [rsp+268h+var_238]
0x180020b65  mov     [rsp+268h+var_238], 104h
0x180020b6d  mov     [rsp+268h+pcchOut], rcx; pcchOut
0x180020b72  lea     edx, [rsi+0Eh]; str
0x180020b75  lea     rcx, [rsp+268h+String1]
0x180020b7a  xor     r9d, r9d; pszExtra
0x180020b7d  mov     [rsp+268h+pszOut], rcx; pszOut
0x180020b82  mov     r8, rax; pszAssoc
0x180020b85  xor     ecx, ecx; flags
0x180020b87  call    AssocQueryStringW
0x180020b8c  test    eax, eax
0x180020b8e  js      short loc_180020BA3
0x180020b90  mov     rdx, rdi; lpString2
0x180020b93  lea     rcx, [rsp+268h+String1]; lpString1
0x180020b98  call    cs:__imp_lstrcmpiW
0x180020b9e  test    eax, eax
0x180020ba0  setz    bl
0x180020ba3  mov     eax, ebx
0x180020ba5  mov     rcx, [rsp+268h+var_18]
0x180020bad  xor     rcx, rsp; StackCookie
0x180020bb0  call    __security_check_cookie
0x180020bb5  lea     r11, [rsp+268h+var_8]
0x180020bbd  mov     rbx, [r11+20h]
0x180020bc1  mov     rsi, [r11+28h]
0x180020bc5  mov     rsp, r11
0x180020bc8  pop     rdi
0x180020bc9  retn
```
