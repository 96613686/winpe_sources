# CFileInfoCache::_GetModulePath(ushort const *,ushort *,ulong,int,tagENTRY_TYPE)

- ea: `0x1800fcfe8`
- end: `0x1800fd26c`
- name: `?_GetModulePath@CFileInfoCache@@AEAAJPEBGPEAGKHW4tagENTRY_TYPE@@@Z`
- size: `644`
- prototype: `int __high(const unsigned __int16 *, unsigned __int16 *, unsigned int, int, enum tagENTRY_TYPE)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800fcc7c`

## callees

- `0x18001054c`
- `0x18001e340`
- `0x1800fcfe8`
- `0x18011905c`
- `0x18011ba3e`
- `0x18011baa0`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800fd155`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800fd155`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800fd165`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800fd165`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fd235`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fd235`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fd0c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fd0c9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800fd12e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800fd1b8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800fd12e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800fd1b8`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x1800fd1fb`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x1800fd1fb`

## string_xrefs

- `0x1800fd071`: `CLSID\%s\%s`
- `0x1800fd15e`: `mscoree.dll`

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
  WCHAR *v12; // r8
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
0x1800fcfe8  mov     [rsp-8+arg_0], rbx
0x1800fcfed  mov     [rsp-8+arg_18], rdi
0x1800fcff2  push    rbp
0x1800fcff3  push    r12
0x1800fcff5  push    r14
0x1800fcff7  lea     rbp, [rsp-7B0h]
0x1800fcfff  sub     rsp, 8B0h
0x1800fd006  mov     rax, cs:__security_cookie
0x1800fd00d  xor     rax, rsp
0x1800fd010  mov     [rbp+7C0h+var_20], rax
0x1800fd017  mov     rdi, r8
0x1800fd01a  mov     rbx, rdx
0x1800fd01d  test    rdx, rdx
0x1800fd020  jz      loc_1800FD23F
0x1800fd026  test    r8, r8
0x1800fd029  jz      loc_1800FD23F
0x1800fd02f  cmp     [rbp+7C0h+arg_28], 2
0x1800fd036  jnz     loc_1800FD23F
0x1800fd03c  xor     eax, eax
0x1800fd03e  lea     rcx, [rbp+7C0h+SubKey]; void *
0x1800fd045  mov     [r8], ax
0x1800fd049  mov     r12d, 208h
0x1800fd04f  mov     r8d, r12d; Size
0x1800fd052  xor     edx, edx; Val
0x1800fd054  call    memset_0
0x1800fd059  lea     rax, aInprocserver32_2; "InProcServer32"
0x1800fd060  mov     r14d, 104h
0x1800fd066  mov     edx, r14d; unsigned __int64
0x1800fd069  mov     [rsp+8C0h+phkResult], rax
0x1800fd06e  mov     r9, rbx
0x1800fd071  lea     r8, aClsidSS; "CLSID\\%s\\%s"
0x1800fd078  lea     rcx, [rbp+7C0h+SubKey]; unsigned __int16 *
0x1800fd07f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800fd084  mov     ebx, eax
0x1800fd086  test    eax, eax
0x1800fd088  js      loc_1800FD23B
0x1800fd08e  neg     [rbp+7C0h+arg_20]
0x1800fd094  lea     rax, [rsp+8C0h+hkey]
0x1800fd099  lea     rdx, [rbp+7C0h+SubKey]; lpSubKey
0x1800fd0a0  mov     [rsp+8C0h+hkey], 0
0x1800fd0a9  sbb     r9d, r9d
0x1800fd0ac  mov     [rsp+8C0h+phkResult], rax; phkResult
0x1800fd0b1  and     r9d, 0FFFFFF00h
0x1800fd0b8  xor     r8d, r8d; ulOptions
0x1800fd0bb  add     r9d, 201h; samDesired
0x1800fd0c2  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800fd0c9  call    cs:__imp_RegOpenKeyExW
0x1800fd0cf  mov     ebx, eax
0x1800fd0d1  test    eax, eax
0x1800fd0d3  jz      short loc_1800FD0E9
0x1800fd0d5  jle     loc_1800FD23B
0x1800fd0db  movzx   ebx, ax
0x1800fd0de  or      ebx, 80070000h
0x1800fd0e4  jmp     loc_1800FD23B
0x1800fd0e9  mov     r8, r12; Size
0x1800fd0ec  lea     rcx, [rbp+7C0h+pszPath]; void *
0x1800fd0f3  xor     edx, edx; Val
0x1800fd0f5  call    memset_0
0x1800fd0fa  mov     rcx, [rsp+8C0h+hkey]; hkey
0x1800fd0ff  lea     rax, [rsp+8C0h+var_878]
0x1800fd104  mov     [rsp+8C0h+pcbData], rax; pcbData
0x1800fd109  mov     r9d, 2; dwFlags
0x1800fd10f  lea     rax, [rbp+7C0h+pszPath]
0x1800fd116  mov     [rsp+8C0h+var_878], r12d
0x1800fd11b  mov     [rsp+8C0h+pvData], rax; pvData
0x1800fd120  xor     r8d, r8d; lpValue
0x1800fd123  xor     edx, edx; lpSubKey
0x1800fd125  mov     [rsp+8C0h+phkResult], 0; pdwType
0x1800fd12e  call    cs:__imp_RegGetValueW
0x1800fd134  mov     ebx, eax
0x1800fd136  test    eax, eax
0x1800fd138  jz      short loc_1800FD14E
0x1800fd13a  jle     loc_1800FD22B
0x1800fd140  movzx   ebx, ax
0x1800fd143  or      ebx, 80070000h
0x1800fd149  jmp     loc_1800FD22B
0x1800fd14e  lea     rcx, [rbp+7C0h+pszPath]; pszPath
0x1800fd155  call    cs:__imp_PathFindFileNameW
0x1800fd15b  mov     rcx, rax; pszStr1
0x1800fd15e  lea     rdx, aMscoreeDll_0; "mscoree.dll"
0x1800fd165  call    cs:__imp_StrCmpICW
0x1800fd16b  test    eax, eax
0x1800fd16d  jnz     loc_1800FD217
0x1800fd173  mov     r8, r12; Size
0x1800fd176  lea     rcx, [rsp+8C0h+pszUrl]; void *
0x1800fd17b  xor     edx, edx; Val
0x1800fd17d  call    memset_0
0x1800fd182  mov     rcx, [rsp+8C0h+hkey]; hkey
0x1800fd187  lea     rax, [rsp+8C0h+var_874]
0x1800fd18c  mov     [rsp+8C0h+pcbData], rax; pcbData
0x1800fd191  lea     r8, aCodebase_4; "CodeBase"
0x1800fd198  lea     rax, [rsp+8C0h+pszUrl]
0x1800fd19d  mov     [rsp+8C0h+var_874], r12d
0x1800fd1a2  mov     [rsp+8C0h+pvData], rax; pvData
0x1800fd1a7  mov     r9d, 2; dwFlags
0x1800fd1ad  xor     edx, edx; lpSubKey
0x1800fd1af  mov     [rsp+8C0h+phkResult], 0; pdwType
0x1800fd1b8  call    cs:__imp_RegGetValueW
0x1800fd1be  test    eax, eax
0x1800fd1c0  jnz     short loc_1800FD217
0x1800fd1c2  lea     rcx, [rsp+8C0h+pszUrl]
0x1800fd1c7  call    GetUrlSchemeW
0x1800fd1cc  cmp     eax, 9
0x1800fd1cf  jnz     short loc_1800FD210
0x1800fd1d1  mov     r8, r12; Size
0x1800fd1d4  lea     rcx, [rbp+7C0h+var_230]; void *
0x1800fd1db  xor     edx, edx; Val
0x1800fd1dd  call    memset_0
0x1800fd1e2  xor     r9d, r9d; dwFlags
0x1800fd1e5  mov     [rsp+8C0h+pcchPath], r14d
0x1800fd1ea  lea     r8, [rsp+8C0h+pcchPath]; pcchPath
0x1800fd1ef  lea     rdx, [rbp+7C0h+var_230]; pszPath
0x1800fd1f6  lea     rcx, [rsp+8C0h+pszUrl]; pszUrl
0x1800fd1fb  call    cs:__imp_PathCreateFromUrlW
0x1800fd201  mov     ebx, eax
0x1800fd203  test    eax, eax
0x1800fd205  js      short loc_1800FD22B
0x1800fd207  lea     r8, [rbp+7C0h+var_230]
0x1800fd20e  jmp     short loc_1800FD21E
0x1800fd210  lea     r8, [rsp+8C0h+pszUrl]
0x1800fd215  jmp     short loc_1800FD21E
0x1800fd217  lea     r8, [rbp+7C0h+pszPath]; unsigned __int16 *
0x1800fd21e  mov     rdx, r14; unsigned __int64
0x1800fd221  mov     rcx, rdi; unsigned __int16 *
0x1800fd224  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800fd229  mov     ebx, eax
0x1800fd22b  mov     rcx, [rsp+8C0h+hkey]; hKey
0x1800fd230  test    rcx, rcx
0x1800fd233  jz      short loc_1800FD23B
0x1800fd235  call    cs:__imp_RegCloseKey
0x1800fd23b  mov     eax, ebx
0x1800fd23d  jmp     short loc_1800FD244
0x1800fd23f  mov     eax, 80070057h
0x1800fd244  mov     rcx, [rbp+7C0h+var_20]
0x1800fd24b  xor     rcx, rsp; StackCookie
0x1800fd24e  call    __security_check_cookie
0x1800fd253  lea     r11, [rsp+8C0h+var_10]
0x1800fd25b  mov     rbx, [r11+20h]
0x1800fd25f  mov     rdi, [r11+38h]
0x1800fd263  mov     rsp, r11
0x1800fd266  pop     r14
0x1800fd268  pop     r12
0x1800fd26a  pop     rbp
0x1800fd26b  retn
```
