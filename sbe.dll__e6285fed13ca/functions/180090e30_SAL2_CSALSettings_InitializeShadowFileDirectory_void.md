# SAL2::CSALSettings::InitializeShadowFileDirectory(void)

- ea: `0x180090e30`
- end: `0x180090f1f`
- name: `?InitializeShadowFileDirectory@CSALSettings@SAL2@@AEAAJXZ`
- size: `239`
- prototype: `__int64 __fastcall(SAL2::CSALSettings *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x180090d6c`

## callees

- `0x180090e30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180090ee4`
- `KERNEL32!GetLastError` at `0x180090ee4`
- `KERNEL32!GetTempPath2W` at `0x180090eda`
- `KERNEL32!GetTempPath2W` at `0x180090eda`
- `ole32!CoTaskMemFree` at `0x180090f0e`
- `ole32!CoTaskMemFree` at `0x180090f0e`
- `SHELL32!SHGetKnownFolderPath` at `0x180090e6f`
- `SHELL32!SHGetKnownFolderPath` at `0x180090e6f`
- `SHLWAPI!PathFileExistsW` at `0x180090ecb`
- `SHLWAPI!PathFileExistsW` at `0x180090ecb`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180090e8c`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180090e8c`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180090ea4`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180090ebc`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180090ea4`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180090ebc`

## pseudocode

```c
__int64 __fastcall SAL2::CSALSettings::InitializeShadowFileDirectory(SAL2::CSALSettings *this)
{
  int v1; // ebx
  signed int LastError; // eax
  PWSTR ppszPath; // [rsp+50h] [rbp+8h] BYREF

  v1 = 0;
  ppszPath = 0;
  if ( pszPath )
    goto LABEL_7;
  v1 = SHGetKnownFolderPath(&FOLDERID_ProgramData, 0x400u, 0, &ppszPath);
  if ( !v1 )
  {
    v1 = PathCchCombine(&pszPath, 0x104u, ppszPath, L"Microsoft");
    if ( v1 < 0 )
      goto LABEL_12;
    v1 = PathCchAppend(&pszPath, 0x104u, L"eHome");
    if ( v1 < 0 )
      goto LABEL_12;
    v1 = PathCchAppend(&pszPath, 0x104u, L"SharedSBE");
  }
  if ( v1 < 0 )
  {
LABEL_12:
    pszPath = 0;
    goto LABEL_13;
  }
LABEL_7:
  if ( !PathFileExistsW(&pszPath) )
  {
    if ( !(unsigned int)GetTempPath2W(260, &pszPath) )
    {
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( v1 < 0 )
      goto LABEL_12;
  }
LABEL_13:
  if ( ppszPath )
    CoTaskMemFree(ppszPath);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180090e30  mov     [rsp+ppszPath], rcx
0x180090e35  push    rbx
0x180090e36  push    rbp
0x180090e37  push    rsi
0x180090e38  push    rdi
0x180090e39  sub     rsp, 28h
0x180090e3d  xor     edi, edi
0x180090e3f  lea     rsi, pszPath
0x180090e46  cmp     cs:pszPath, di
0x180090e4d  mov     ebx, edi
0x180090e4f  mov     [rsp+48h+ppszPath], rdi
0x180090e54  mov     ebp, 104h
0x180090e59  jnz     short loc_180090EC8
0x180090e5b  lea     r9, [rsp+48h+ppszPath]; ppszPath
0x180090e60  xor     r8d, r8d; hToken
0x180090e63  mov     edx, 400h; dwFlags
0x180090e68  lea     rcx, FOLDERID_ProgramData; rfid
0x180090e6f  call    cs:__imp_SHGetKnownFolderPath
0x180090e75  mov     ebx, eax
0x180090e77  test    eax, eax
0x180090e79  jnz     short loc_180090EC4
0x180090e7b  mov     r8, [rsp+48h+ppszPath]; pszPathIn
0x180090e80  lea     r9, pszMore; "Microsoft"
0x180090e87  mov     edx, ebp; cchPathOut
0x180090e89  mov     rcx, rsi; pszPathOut
0x180090e8c  call    cs:__imp_PathCchCombine
0x180090e92  mov     ebx, eax
0x180090e94  test    eax, eax
0x180090e96  js      short loc_180090EFD
0x180090e98  lea     r8, aEhome; "eHome"
0x180090e9f  mov     edx, ebp; cchPath
0x180090ea1  mov     rcx, rsi; pszPath
0x180090ea4  call    cs:__imp_PathCchAppend
0x180090eaa  mov     ebx, eax
0x180090eac  test    eax, eax
0x180090eae  js      short loc_180090EFD
0x180090eb0  lea     r8, aSharedsbe; "SharedSBE"
0x180090eb7  mov     edx, ebp; cchPath
0x180090eb9  mov     rcx, rsi; pszPath
0x180090ebc  call    cs:__imp_PathCchAppend
0x180090ec2  mov     ebx, eax
0x180090ec4  test    ebx, ebx
0x180090ec6  js      short loc_180090EFD
0x180090ec8  mov     rcx, rsi; pszPath
0x180090ecb  call    cs:__imp_PathFileExistsW
0x180090ed1  test    eax, eax
0x180090ed3  jnz     short loc_180090F04
0x180090ed5  mov     rdx, rsi
0x180090ed8  mov     ecx, ebp
0x180090eda  call    cs:__imp_GetTempPath2W
0x180090ee0  test    eax, eax
0x180090ee2  jnz     short loc_180090EF9
0x180090ee4  call    cs:__imp_GetLastError
0x180090eea  mov     ebx, eax
0x180090eec  test    eax, eax
0x180090eee  jle     short loc_180090EF9
0x180090ef0  movzx   ebx, ax
0x180090ef3  or      ebx, 80070000h
0x180090ef9  test    ebx, ebx
0x180090efb  jns     short loc_180090F04
0x180090efd  mov     cs:pszPath, di
0x180090f04  mov     rcx, [rsp+48h+ppszPath]; pv
0x180090f09  test    rcx, rcx
0x180090f0c  jz      short loc_180090F14
0x180090f0e  call    cs:__imp_CoTaskMemFree
0x180090f14  mov     eax, ebx
0x180090f16  add     rsp, 28h
0x180090f1a  pop     rdi
0x180090f1b  pop     rsi
0x180090f1c  pop     rbp
0x180090f1d  pop     rbx
0x180090f1e  retn
```
