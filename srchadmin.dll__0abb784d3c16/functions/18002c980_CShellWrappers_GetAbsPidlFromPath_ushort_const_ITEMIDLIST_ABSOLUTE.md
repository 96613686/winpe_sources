# CShellWrappers::GetAbsPidlFromPath(ushort const *,_ITEMIDLIST_ABSOLUTE * *)

- ea: `0x18002c980`
- end: `0x18002cb85`
- name: `?GetAbsPidlFromPath@CShellWrappers@@QEAAJPEBGPEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `517`
- prototype: `int(CShellWrappers *__hidden this, const unsigned __int16 *, struct _ITEMIDLIST_ABSOLUTE **)`
- caller_count: `5`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014880`
- `0x180014ab0`
- `0x18001681c`
- `0x180024260`
- `0x180024360`

## callees

- `0x180004fdc`
- `0x180005cc0`
- `0x18000d4dc`
- `0x180024714`
- `0x18002c980`
- `0x1800303a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18002c9d4`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18002c9d4`
- `SHELL32!SHParseDisplayName` at `0x18002cb4c`
- `SHELL32!SHParseDisplayName` at `0x18002cb4c`
- `SHLWAPI!UrlIsW` at `0x18002c9bc`
- `SHLWAPI!UrlIsW` at `0x18002c9bc`
- `SHLWAPI!PathCreateFromUrlW` at `0x18002ca8c`
- `SHLWAPI!PathCreateFromUrlW` at `0x18002ca8c`
- `SHLWAPI!UrlEscapeW` at `0x18002ca02`
- `SHLWAPI!UrlEscapeW` at `0x18002ca5c`
- `SHLWAPI!UrlEscapeW` at `0x18002ca02`
- `SHLWAPI!UrlEscapeW` at `0x18002ca5c`
- `SHLWAPI!PathIsRootW` at `0x18002cab9`
- `SHLWAPI!PathIsRootW` at `0x18002cab9`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18002cafb`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18002cafb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cb5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cb5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ca40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ca40`

## pseudocode

```c
__int64 __fastcall CShellWrappers::GetAbsPidlFromPath(IBindCtx **this, const unsigned __int16 *a2, LPITEMIDLIST *a3)
{
  WCHAR *v5; // rdi
  HRESULT v7; // eax
  HRESULT Error; // ebx
  WCHAR *v9; // rax
  const WCHAR *v10; // rsi
  int lpMaximumComponentLength; // [rsp+20h] [rbp-E0h]
  WCHAR pszEscaped[2]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcchEscaped; // [rsp+44h] [rbp-BCh] BYREF
  DWORD pcchPath; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR pszPath[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR FileSystemNameBuffer[264]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR VolumeNameBuffer[264]; // [rsp+470h] [rbp+370h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6C8h] [rbp+5C8h]

  v5 = 0;
  if ( !UrlIsW(a2, URLIS_FILEURL) )
    goto LABEL_20;
  if ( !wcsstr(a2, L"\\") )
    goto LABEL_9;
  pcchEscaped = 1;
  pszEscaped[0] = 0;
  v7 = UrlEscapeW(a2, pszEscaped, &pcchEscaped, 0);
  Error = v7;
  if ( v7 == -2147467261 )
  {
    v9 = (WCHAR *)CoTaskMemAlloc(2LL * pcchEscaped);
    v5 = v9;
    if ( v9 )
    {
      Error = UrlEscapeW(a2, v9, &pcchEscaped, 0);
      if ( Error < 0 )
        goto LABEL_23;
      v10 = v5;
LABEL_10:
      pcchPath = 260;
      Error = PathCreateFromUrlW(v10, pszPath, &pcchPath, 0);
      if ( Error < 0 )
        goto LABEL_22;
      if ( !(unsigned int)IsIndexerSupportedDriveType(pszPath) )
      {
        Error = -2147024809;
        goto LABEL_22;
      }
      if ( PathIsRootW(pszPath) )
      {
        if ( GetVolumeInformationW(pszPath, VolumeNameBuffer, 0x105u, 0, 0, 0, FileSystemNameBuffer, 0x105u) )
        {
          if ( wcscmp_0(FileSystemNameBuffer, L"RAW") )
            goto LABEL_19;
          Error = -2147024809;
        }
        else
        {
          Error = ResultFromKnownLastError();
        }
        if ( Error < 0 )
          goto LABEL_22;
      }
LABEL_19:
      if ( v10 )
      {
LABEL_21:
        Error = SHParseDisplayName(v10, this[1], a3, 0, 0);
LABEL_22:
        if ( !v5 )
          return (unsigned int)Error;
LABEL_23:
        CoTaskMemFree(v5);
        return (unsigned int)Error;
      }
LABEL_20:
      v10 = a2;
      goto LABEL_21;
    }
LABEL_9:
    v10 = a2;
    goto LABEL_10;
  }
  if ( v7 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBA,
      (unsigned int)"shell\\cpls\\srchadmin\\cpl\\shellwrappers.cpp",
      (const char *)(unsigned int)v7,
      lpMaximumComponentLength);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18002c980  push    rbp
0x18002c982  push    rbx
0x18002c983  push    rsi
0x18002c984  push    rdi
0x18002c985  push    r12
0x18002c987  push    r14
0x18002c989  push    r15
0x18002c98b  lea     rbp, [rsp-590h]
0x18002c993  sub     rsp, 690h
0x18002c99a  mov     rax, cs:__security_cookie
0x18002c9a1  xor     rax, rsp
0x18002c9a4  mov     [rbp+5C0h+var_40], rax
0x18002c9ab  mov     r14, rdx
0x18002c9ae  mov     r15, rcx
0x18002c9b1  xor     edi, edi
0x18002c9b3  mov     rcx, r14; pszUrl
0x18002c9b6  mov     r12, r8
0x18002c9b9  lea     edx, [rdi+3]; UrlIs
0x18002c9bc  call    cs:__imp_UrlIsW
0x18002c9c2  test    eax, eax
0x18002c9c4  jz      loc_18002CB33
0x18002c9ca  lea     rdx, SubStr; "\\"
0x18002c9d1  mov     rcx, r14; Str
0x18002c9d4  call    cs:__imp_wcsstr
0x18002c9da  test    rax, rax
0x18002c9dd  jz      loc_18002CA71
0x18002c9e3  xor     eax, eax
0x18002c9e5  mov     [rsp+6C0h+pcchEscaped], 1
0x18002c9ed  xor     r9d, r9d; dwFlags
0x18002c9f0  mov     [rsp+6C0h+pszEscaped], ax
0x18002c9f5  lea     r8, [rsp+6C0h+pcchEscaped]; pcchEscaped
0x18002c9fa  mov     rcx, r14; pszUrl
0x18002c9fd  lea     rdx, [rsp+6C0h+pszEscaped]; pszEscaped
0x18002ca02  call    cs:__imp_UrlEscapeW
0x18002ca08  mov     ebx, eax
0x18002ca0a  cmp     eax, 80004003h
0x18002ca0f  jz      short loc_18002CA39
0x18002ca11  test    eax, eax
0x18002ca13  jns     loc_18002CB62
0x18002ca19  mov     rcx, [rbp+5C8h]; this
0x18002ca20  lea     r8, aShellCplsSrcha; "shell\\cpls\\srchadmin\\cpl\\shellwrapp"...
0x18002ca27  mov     r9d, eax; char *
0x18002ca2a  mov     edx, 0BAh; void *
0x18002ca2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ca34  jmp     loc_18002CB62
0x18002ca39  mov     ecx, [rsp+6C0h+pcchEscaped]
0x18002ca3d  add     rcx, rcx; cb
0x18002ca40  call    cs:__imp_CoTaskMemAlloc
0x18002ca46  mov     rdi, rax
0x18002ca49  test    rax, rax
0x18002ca4c  jz      short loc_18002CA71
0x18002ca4e  xor     r9d, r9d; dwFlags
0x18002ca51  lea     r8, [rsp+6C0h+pcchEscaped]; pcchEscaped
0x18002ca56  mov     rdx, rax; pszEscaped
0x18002ca59  mov     rcx, r14; pszUrl
0x18002ca5c  call    cs:__imp_UrlEscapeW
0x18002ca62  mov     ebx, eax
0x18002ca64  test    eax, eax
0x18002ca66  js      loc_18002CB59
0x18002ca6c  mov     rsi, rdi
0x18002ca6f  jmp     short loc_18002CA74
0x18002ca71  mov     rsi, r14
0x18002ca74  xor     r9d, r9d; dwFlags
0x18002ca77  mov     [rsp+6C0h+pcchPath], 104h
0x18002ca7f  lea     r8, [rsp+6C0h+pcchPath]; pcchPath
0x18002ca84  mov     rcx, rsi; pszUrl
0x18002ca87  lea     rdx, [rsp+6C0h+pszPath]; pszPath
0x18002ca8c  call    cs:__imp_PathCreateFromUrlW
0x18002ca92  mov     ebx, eax
0x18002ca94  test    eax, eax
0x18002ca96  js      loc_18002CB54
0x18002ca9c  lea     rcx, [rsp+6C0h+pszPath]; unsigned __int16 *
0x18002caa1  call    ?IsIndexerSupportedDriveType@@YAHPEBG@Z; IsIndexerSupportedDriveType(ushort const *)
0x18002caa6  test    eax, eax
0x18002caa8  jnz     short loc_18002CAB4
0x18002caaa  mov     ebx, 80070057h
0x18002caaf  jmp     loc_18002CB54
0x18002cab4  lea     rcx, [rsp+6C0h+pszPath]; pszPath
0x18002cab9  call    cs:__imp_PathIsRootW
0x18002cabf  test    eax, eax
0x18002cac1  jz      short loc_18002CB2E
0x18002cac3  mov     r8d, 105h; nVolumeNameSize
0x18002cac9  lea     rax, [rbp+5C0h+FileSystemNameBuffer]
0x18002cad0  mov     [rsp+6C0h+nFileSystemNameSize], r8d; nFileSystemNameSize
0x18002cad5  lea     rdx, [rbp+5C0h+VolumeNameBuffer]; lpVolumeNameBuffer
0x18002cadc  mov     [rsp+6C0h+lpFileSystemNameBuffer], rax; lpFileSystemNameBuffer
0x18002cae1  lea     rcx, [rsp+6C0h+pszPath]; lpRootPathName
0x18002cae6  mov     [rsp+6C0h+lpFileSystemFlags], 0; lpFileSystemFlags
0x18002caef  xor     r9d, r9d; lpVolumeSerialNumber
0x18002caf2  mov     [rsp+6C0h+lpMaximumComponentLength], 0; lpMaximumComponentLength
0x18002cafb  call    cs:__imp_GetVolumeInformationW
0x18002cb01  test    eax, eax
0x18002cb03  jz      short loc_18002CB23
0x18002cb05  lea     rdx, aRaw; "RAW"
0x18002cb0c  lea     rcx, [rbp+5C0h+FileSystemNameBuffer]; String1
0x18002cb13  call    wcscmp_0
0x18002cb18  test    eax, eax
0x18002cb1a  jnz     short loc_18002CB2E
0x18002cb1c  mov     ebx, 80070057h
0x18002cb21  jmp     short loc_18002CB2A
0x18002cb23  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002cb28  mov     ebx, eax
0x18002cb2a  test    ebx, ebx
0x18002cb2c  js      short loc_18002CB54
0x18002cb2e  test    rsi, rsi
0x18002cb31  jnz     short loc_18002CB36
0x18002cb33  mov     rsi, r14
0x18002cb36  mov     rdx, [r15+8]; pbc
0x18002cb3a  xor     r9d, r9d; sfgaoIn
0x18002cb3d  mov     r8, r12; ppidl
0x18002cb40  mov     [rsp+6C0h+lpMaximumComponentLength], 0; psfgaoOut
0x18002cb49  mov     rcx, rsi; pszName
0x18002cb4c  call    cs:__imp_SHParseDisplayName
0x18002cb52  mov     ebx, eax
0x18002cb54  test    rdi, rdi
0x18002cb57  jz      short loc_18002CB62
0x18002cb59  mov     rcx, rdi; pv
0x18002cb5c  call    cs:__imp_CoTaskMemFree
0x18002cb62  mov     eax, ebx
0x18002cb64  mov     rcx, [rbp+5C0h+var_40]
0x18002cb6b  xor     rcx, rsp; StackCookie
0x18002cb6e  call    __security_check_cookie
0x18002cb73  add     rsp, 690h
0x18002cb7a  pop     r15
0x18002cb7c  pop     r14
0x18002cb7e  pop     r12
0x18002cb80  pop     rdi
0x18002cb81  pop     rsi
0x18002cb82  pop     rbx
0x18002cb83  pop     rbp
0x18002cb84  retn
```
