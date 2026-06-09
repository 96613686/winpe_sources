# CFileInfoCache::_GetModulePath(ushort const *,ushort *,ulong,int,tagENTRY_TYPE)

- ea: `0x180107e4c`
- end: `0x1801080fb`
- name: `?_GetModulePath@CFileInfoCache@@AEAAJPEBGPEAGKHW4tagENTRY_TYPE@@@Z`
- size: `687`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int16 *, __int64, int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180107a3c`

## callees

- `0x1800162d4`
- `0x180024ea0`
- `0x180107e4c`
- `0x180125a58`
- `0x1801285fe`
- `0x180128660`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180107fc5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180107fc5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180107fdb`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180107fdb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801080bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801080bd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180107f2d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180107f2d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180107f98`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180108034`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180107f98`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180108034`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x18010807d`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x18010807d`

## string_xrefs

- `0x180107ed5`: `CLSID\%s\%s`
- `0x180107fd4`: `mscoree.dll`

## pseudocode

```c
__int64 __fastcall CFileInfoCache::_GetModulePath(
        __int64 a1,
        __int64 a2,
        unsigned __int16 *a3,
        __int64 a4,
        int a5,
        int a6)
{
  int v8; // ebx
  LSTATUS v9; // eax
  LSTATUS ValueW; // eax
  const WCHAR *FileNameW; // rax
  unsigned __int16 *v12; // r8
  HKEY hkey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-B8h] BYREF
  DWORD v16; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD pcchPath[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszUrl[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszPath[264]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR SubKey[264]; // [rsp+480h] [rbp+380h] BYREF
  WCHAR v21[264]; // [rsp+690h] [rbp+590h] BYREF

  if ( a2 && a3 && a6 == 2 )
  {
    *a3 = 0;
    memset_0(SubKey, 0, 0x208u);
    v8 = StringCchPrintfW(SubKey, 0x104u, L"CLSID\\%s\\%s", a2, L"InProcServer32");
    if ( v8 < 0 )
      return (unsigned int)v8;
    hkey = 0;
    v9 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, a5 != 0 ? 257 : 513, &hkey);
    v8 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        return (unsigned __int16)v9 | 0x80070000;
      return (unsigned int)v8;
    }
    memset_0(pszPath, 0, 0x208u);
    pcbData = 520;
    ValueW = RegGetValueW(hkey, 0, 0, 2u, 0, pszPath, &pcbData);
    v8 = ValueW;
    if ( ValueW )
    {
      if ( ValueW > 0 )
        v8 = (unsigned __int16)ValueW | 0x80070000;
      goto LABEL_19;
    }
    FileNameW = PathFindFileNameW(pszPath);
    if ( StrCmpICW(FileNameW, L"mscoree.dll")
      || (memset_0(pszUrl, 0, 0x208u), v16 = 520, RegGetValueW(hkey, 0, L"CodeBase", 2u, 0, pszUrl, &v16)) )
    {
      v12 = pszPath;
    }
    else if ( (unsigned int)GetUrlSchemeW(pszUrl) == 9 )
    {
      memset_0(v21, 0, 0x208u);
      pcchPath[0] = 260;
      v8 = PathCreateFromUrlW(pszUrl, v21, pcchPath, 0);
      if ( v8 < 0 )
        goto LABEL_19;
      v12 = v21;
    }
    else
    {
      v12 = pszUrl;
    }
    v8 = StringCchCopyW(a3, 0x104u, v12);
LABEL_19:
    if ( hkey )
      RegCloseKey(hkey);
    return (unsigned int)v8;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180107e4c  mov     [rsp-8+arg_0], rbx
0x180107e51  mov     [rsp-8+arg_18], rdi
0x180107e56  push    rbp
0x180107e57  push    r12
0x180107e59  push    r14
0x180107e5b  lea     rbp, [rsp-7B0h]
0x180107e63  sub     rsp, 8B0h
0x180107e6a  mov     rax, cs:__security_cookie
0x180107e71  xor     rax, rsp
0x180107e74  mov     [rbp+7C0h+var_20], rax
0x180107e7b  mov     rdi, r8
0x180107e7e  mov     rbx, rdx
0x180107e81  test    rdx, rdx
0x180107e84  jz      loc_1801080CD
0x180107e8a  test    r8, r8
0x180107e8d  jz      loc_1801080CD
0x180107e93  cmp     [rbp+7C0h+arg_28], 2
0x180107e9a  jnz     loc_1801080CD
0x180107ea0  xor     eax, eax
0x180107ea2  lea     rcx, [rbp+7C0h+SubKey]; void *
0x180107ea9  mov     [r8], ax
0x180107ead  mov     r12d, 208h
0x180107eb3  mov     r8d, r12d; Size
0x180107eb6  xor     edx, edx; Val
0x180107eb8  call    memset_0
0x180107ebd  lea     rax, aInprocserver32_2; "InProcServer32"
0x180107ec4  mov     r14d, 104h
0x180107eca  mov     edx, r14d; unsigned __int64
0x180107ecd  mov     [rsp+8C0h+phkResult], rax
0x180107ed2  mov     r9, rbx
0x180107ed5  lea     r8, aClsidSS; "CLSID\\%s\\%s"
0x180107edc  lea     rcx, [rbp+7C0h+SubKey]; unsigned __int16 *
0x180107ee3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180107ee8  mov     ebx, eax
0x180107eea  test    eax, eax
0x180107eec  js      loc_1801080C9
0x180107ef2  neg     [rbp+7C0h+arg_20]
0x180107ef8  lea     rax, [rsp+8C0h+hkey]
0x180107efd  lea     rdx, [rbp+7C0h+SubKey]; lpSubKey
0x180107f04  mov     [rsp+8C0h+hkey], 0
0x180107f0d  sbb     r9d, r9d
0x180107f10  mov     [rsp+8C0h+phkResult], rax; phkResult
0x180107f15  and     r9d, 0FFFFFF00h
0x180107f1c  xor     r8d, r8d; ulOptions
0x180107f1f  add     r9d, 201h; samDesired
0x180107f26  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180107f2d  call    cs:__imp_RegOpenKeyExW
0x180107f34  nop     dword ptr [rax+rax+00h]
0x180107f39  mov     ebx, eax
0x180107f3b  test    eax, eax
0x180107f3d  jz      short loc_180107F53
0x180107f3f  jle     loc_1801080C9
0x180107f45  movzx   ebx, ax
0x180107f48  or      ebx, 80070000h
0x180107f4e  jmp     loc_1801080C9
0x180107f53  mov     r8, r12; Size
0x180107f56  lea     rcx, [rbp+7C0h+pszPath]; void *
0x180107f5d  xor     edx, edx; Val
0x180107f5f  call    memset_0
0x180107f64  mov     rcx, [rsp+8C0h+hkey]; hkey
0x180107f69  lea     rax, [rsp+8C0h+var_878]
0x180107f6e  mov     [rsp+8C0h+pcbData], rax; pcbData
0x180107f73  mov     r9d, 2; dwFlags
0x180107f79  lea     rax, [rbp+7C0h+pszPath]
0x180107f80  mov     [rsp+8C0h+var_878], r12d
0x180107f85  mov     [rsp+8C0h+pvData], rax; pvData
0x180107f8a  xor     r8d, r8d; lpValue
0x180107f8d  xor     edx, edx; lpSubKey
0x180107f8f  mov     [rsp+8C0h+phkResult], 0; pdwType
0x180107f98  call    cs:__imp_RegGetValueW
0x180107f9f  nop     dword ptr [rax+rax+00h]
0x180107fa4  mov     ebx, eax
0x180107fa6  test    eax, eax
0x180107fa8  jz      short loc_180107FBE
0x180107faa  jle     loc_1801080B3
0x180107fb0  movzx   ebx, ax
0x180107fb3  or      ebx, 80070000h
0x180107fb9  jmp     loc_1801080B3
0x180107fbe  lea     rcx, [rbp+7C0h+pszPath]; pszPath
0x180107fc5  call    cs:__imp_PathFindFileNameW
0x180107fcc  nop     dword ptr [rax+rax+00h]
0x180107fd1  mov     rcx, rax; pszStr1
0x180107fd4  lea     rdx, aMscoreeDll_0; "mscoree.dll"
0x180107fdb  call    cs:__imp_StrCmpICW
0x180107fe2  nop     dword ptr [rax+rax+00h]
0x180107fe7  test    eax, eax
0x180107fe9  jnz     loc_18010809F
0x180107fef  mov     r8, r12; Size
0x180107ff2  lea     rcx, [rsp+8C0h+pszUrl]; void *
0x180107ff7  xor     edx, edx; Val
0x180107ff9  call    memset_0
0x180107ffe  mov     rcx, [rsp+8C0h+hkey]; hkey
0x180108003  lea     rax, [rsp+8C0h+var_874]
0x180108008  mov     [rsp+8C0h+pcbData], rax; pcbData
0x18010800d  lea     r8, aCodebase_4; "CodeBase"
0x180108014  lea     rax, [rsp+8C0h+pszUrl]
0x180108019  mov     [rsp+8C0h+var_874], r12d
0x18010801e  mov     [rsp+8C0h+pvData], rax; pvData
0x180108023  mov     r9d, 2; dwFlags
0x180108029  xor     edx, edx; lpSubKey
0x18010802b  mov     [rsp+8C0h+phkResult], 0; pdwType
0x180108034  call    cs:__imp_RegGetValueW
0x18010803b  nop     dword ptr [rax+rax+00h]
0x180108040  test    eax, eax
0x180108042  jnz     short loc_18010809F
0x180108044  lea     rcx, [rsp+8C0h+pszUrl]
0x180108049  call    GetUrlSchemeW
0x18010804e  cmp     eax, 9
0x180108051  jnz     short loc_180108098
0x180108053  mov     r8, r12; Size
0x180108056  lea     rcx, [rbp+7C0h+var_230]; void *
0x18010805d  xor     edx, edx; Val
0x18010805f  call    memset_0
0x180108064  xor     r9d, r9d; dwFlags
0x180108067  mov     [rsp+8C0h+pcchPath], r14d
0x18010806c  lea     r8, [rsp+8C0h+pcchPath]; pcchPath
0x180108071  lea     rdx, [rbp+7C0h+var_230]; pszPath
0x180108078  lea     rcx, [rsp+8C0h+pszUrl]; pszUrl
0x18010807d  call    cs:__imp_PathCreateFromUrlW
0x180108084  nop     dword ptr [rax+rax+00h]
0x180108089  mov     ebx, eax
0x18010808b  test    eax, eax
0x18010808d  js      short loc_1801080B3
0x18010808f  lea     r8, [rbp+7C0h+var_230]
0x180108096  jmp     short loc_1801080A6
0x180108098  lea     r8, [rsp+8C0h+pszUrl]
0x18010809d  jmp     short loc_1801080A6
0x18010809f  lea     r8, [rbp+7C0h+pszPath]; unsigned __int16 *
0x1801080a6  mov     rdx, r14; unsigned __int64
0x1801080a9  mov     rcx, rdi; unsigned __int16 *
0x1801080ac  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801080b1  mov     ebx, eax
0x1801080b3  mov     rcx, [rsp+8C0h+hkey]; hKey
0x1801080b8  test    rcx, rcx
0x1801080bb  jz      short loc_1801080C9
0x1801080bd  call    cs:__imp_RegCloseKey
0x1801080c4  nop     dword ptr [rax+rax+00h]
0x1801080c9  mov     eax, ebx
0x1801080cb  jmp     short loc_1801080D2
0x1801080cd  mov     eax, 80070057h
0x1801080d2  mov     rcx, [rbp+7C0h+var_20]
0x1801080d9  xor     rcx, rsp; StackCookie
0x1801080dc  call    __security_check_cookie
0x1801080e1  lea     r11, [rsp+8C0h+var_10]
0x1801080e9  mov     rbx, [r11+20h]
0x1801080ed  mov     rdi, [r11+38h]
0x1801080f1  mov     rsp, r11
0x1801080f4  pop     r14
0x1801080f6  pop     r12
0x1801080f8  pop     rbp
0x1801080f9  retn
```
