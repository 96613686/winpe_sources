# CPolicyCache::_OpenQfePolicyKey(_GUID const &,_GUID const &)

- ea: `0x18000450c`
- end: `0x1800045d8`
- name: `?_OpenQfePolicyKey@CPolicyCache@@CAPEAUHKEY__@@AEBU_GUID@@0@Z`
- size: `204`
- prototype: `static HKEY(const struct _GUID *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005724`

## callees

- `0x18000450c`
- `0x180006ac0`
- `0x180066910`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800045b4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800045b4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180004541`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180004559`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180004541`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180004559`

## pseudocode

```c
HKEY __fastcall CPolicyCache::_OpenQfePolicyKey(const struct _GUID *a1, const struct _GUID *a2)
{
  HKEY phkResult; // [rsp+30h] [rbp-2D8h] BYREF
  OLECHAR v5[40]; // [rsp+40h] [rbp-2C8h] BYREF
  OLECHAR sz[40]; // [rsp+90h] [rbp-278h] BYREF
  WCHAR SubKey[264]; // [rsp+E0h] [rbp-228h] BYREF

  phkResult = 0;
  if ( StringFromGUID2(a1, sz, 39)
    && StringFromGUID2(a2, v5, 39)
    && (int)StringCchPrintfW(
              SubKey,
              0x104u,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\QfePolicyDefinitions\\%s\\%s",
              sz,
              v5) >= 0 )
  {
    RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &phkResult);
  }
  return phkResult;
}

```

## disassembly

```asm
0x18000450c  push    rbx
0x18000450e  sub     rsp, 300h
0x180004515  mov     rax, cs:__security_cookie
0x18000451c  xor     rax, rsp
0x18000451f  mov     [rsp+308h+var_18], rax
0x180004527  mov     rbx, rdx
0x18000452a  mov     [rsp+308h+var_2D8], 0
0x180004533  lea     rdx, [rsp+308h+sz]; lpsz
0x18000453b  mov     r8d, 27h ; '''; cchMax
0x180004541  call    cs:__imp_StringFromGUID2
0x180004547  test    eax, eax
0x180004549  jz      short loc_1800045BA
0x18000454b  mov     r8d, 27h ; '''; cchMax
0x180004551  lea     rdx, [rsp+308h+var_2C8]; lpsz
0x180004556  mov     rcx, rbx; rguid
0x180004559  call    cs:__imp_StringFromGUID2
0x18000455f  test    eax, eax
0x180004561  jz      short loc_1800045BA
0x180004563  lea     rax, [rsp+308h+var_2C8]
0x180004568  mov     edx, 104h; unsigned __int64
0x18000456d  lea     r9, [rsp+308h+sz]
0x180004575  mov     [rsp+308h+phkResult], rax
0x18000457a  lea     r8, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180004581  lea     rcx, [rsp+308h+SubKey]; unsigned __int16 *
0x180004589  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000458e  test    eax, eax
0x180004590  js      short loc_1800045BA
0x180004592  lea     rax, [rsp+308h+var_2D8]
0x180004597  mov     r9d, 20019h; samDesired
0x18000459d  xor     r8d, r8d; ulOptions
0x1800045a0  mov     [rsp+308h+phkResult], rax; phkResult
0x1800045a5  lea     rdx, [rsp+308h+SubKey]; lpSubKey
0x1800045ad  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800045b4  call    cs:__imp_RegOpenKeyExW
0x1800045ba  mov     rax, [rsp+308h+var_2D8]
0x1800045bf  mov     rcx, [rsp+308h+var_18]
0x1800045c7  xor     rcx, rsp; StackCookie
0x1800045ca  call    __security_check_cookie
0x1800045cf  add     rsp, 300h
0x1800045d6  pop     rbx
0x1800045d7  retn
```
