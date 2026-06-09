# CShellWrappers::GetOfflineDisplayProperties(ushort const *,ushort *,int *)

- ea: `0x180003ac8`
- end: `0x180003e0e`
- name: `?GetOfflineDisplayProperties@CShellWrappers@@QEBAJPEBGPEAGPEAH@Z`
- size: `838`
- prototype: `int(CShellWrappers *__hidden this, const unsigned __int16 *, unsigned __int16 *, int *)`
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180014ab0`
- `0x18001681c`
- `0x180024260`
- `0x180024360`
- `0x180025270`

## callees

- `0x180003ac8`
- `0x180005cc0`
- `0x18000687c`
- `0x1800094f0`
- `0x18000957c`
- `0x18000eaac`
- `0x18002cf30`

## import_xrefs

- `SHELL32!__imp_Shell_GetCachedImageIndex` at `0x180003dc5`
- `SHELL32!__imp_Shell_GetCachedImageIndex` at `0x180003dc5`
- `SHLWAPI!PathParseIconLocationW` at `0x180003db2`
- `SHLWAPI!PathParseIconLocationW` at `0x180003db2`
- `SHLWAPI!PathStripPathW` at `0x180003b67`
- `SHLWAPI!PathStripPathW` at `0x180003b67`
- `SHLWAPI!UrlIsW` at `0x180003b1a`
- `SHLWAPI!UrlIsW` at `0x180003b1a`
- `SHLWAPI!PathCreateFromUrlW` at `0x180003b39`
- `SHLWAPI!PathCreateFromUrlW` at `0x180003b39`
- `SHLWAPI!__imp_ParseURLW` at `0x180003c92`
- `SHLWAPI!__imp_ParseURLW` at `0x180003c92`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x180003d31`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x180003d31`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003ced`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003ced`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003ddb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003ddb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180003d8e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180003d8e`

## string_xrefs

- `0x180003d1a`: `ProtocolHandlerDisplayName`
- `0x180003d69`: `ProtocolHandlerIconPath`

## pseudocode

```c
__int64 __fastcall CShellWrappers::GetOfflineDisplayProperties(
        CShellWrappers *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        int *a4)
{
  HRESULT v8; // eax
  signed int v9; // ebx
  WCHAR *v10; // rax
  int v11; // edx
  int v12; // ecx
  unsigned __int16 v13; // cx
  DWORD v14; // ecx
  __int64 v15; // rax
  const unsigned __int16 *p_pvData; // r8
  LSTATUS v17; // eax
  bool v18; // sf
  char v19; // si
  LSTATUS MUIStringW; // eax
  bool v21; // sf
  LSTATUS ValueW; // eax
  int v23; // eax
  DWORD pcchPath; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  _BYTE hKey[10]; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t v28; // [rsp+52h] [rbp-AEh]
  PARSEDURLW ppu; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 pvData; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v31[526]; // [rsp+82h] [rbp-7Eh] BYREF
  WCHAR pszPath[264]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR SubKey[264]; // [rsp+4A0h] [rbp+3A0h] BYREF
  WCHAR pszOutBuf[264]; // [rsp+6B0h] [rbp+5B0h] BYREF

  *a4 = *((_DWORD *)this + 5);
  pcchPath = 260;
  if ( UrlIsW(a2, URLIS_FILEURL) )
  {
    v8 = PathCreateFromUrlW(a2, a3, &pcchPath, 0);
    pcchPath = 260;
    v9 = v8;
    if ( v8 < 0 )
    {
      StringCchCopyW(a3, 0x104u, a2);
    }
    else
    {
      StringCchCopyW(pszPath, 0x104u, a3);
      PathStripPathW(pszPath);
      v10 = pszPath;
      do
      {
        v11 = *(WCHAR *)((char *)v10 + (char *)a3 - (char *)pszPath);
        v12 = *v10 - v11;
        if ( v12 )
          break;
        ++v10;
      }
      while ( v11 );
      if ( !v12 )
      {
        pvData = 0;
        memset_0(v31, 0, 0x206u);
        v13 = *a3;
        pcbData = 0;
        GetDriveInfo(v13, &pvData, &pcbData);
        v14 = pcbData;
        v15 = 28;
        if ( pcbData == 3 )
          v15 = 24;
        *a4 = *(_DWORD *)((char *)this + v15);
        *(_DWORD *)&hKey[6] = *(_DWORD *)L":)";
        v28 = asc_1800385C8[5];
        *(_WORD *)&hKey[4] = *a3;
        *(_DWORD *)hKey = 2621472;
        if ( pvData )
        {
          p_pvData = &pvData;
        }
        else
        {
          p_pvData = (const unsigned __int16 *)((char *)this + 544);
          if ( v14 != 3 )
            p_pvData = (const unsigned __int16 *)((char *)this + 1056);
        }
        StringCchCopyW(a3, pcchPath, p_pvData);
        StringCchCatW(a3, pcchPath, (const unsigned __int16 *)hKey);
      }
    }
    StringCchCatW(a3, pcchPath, (const unsigned __int16 *)this + 16);
  }
  else
  {
    StringCchCopyW(a3, pcchPath, a2);
    memset(&ppu, 0, sizeof(ppu));
    ppu.cbSize = 40;
    if ( ParseURLW(a2, &ppu) < 0 || (int)StringCchCopyNW(SubKey, 0x104u, ppu.pszProtocol, ppu.cchProtocol) < 0 )
      return 1;
    *(_QWORD *)hKey = 0;
    v17 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, (PHKEY)hKey);
    v18 = v17 < 0;
    if ( v17 > 0 )
      v18 = 1;
    if ( v18 )
      return 1;
    v19 = 0;
    MUIStringW = RegLoadMUIStringW(*(HKEY *)hKey, L"ProtocolHandlerDisplayName", pszOutBuf, 0x104u, 0, 1u, 0);
    v21 = MUIStringW < 0;
    if ( MUIStringW > 0 )
      v21 = 1;
    if ( !v21 )
    {
      StringCchCopyW(a3, pcchPath, pszOutBuf);
      v19 = 1;
    }
    pcbData = 520;
    ValueW = RegGetValueW(*(HKEY *)hKey, 0, L"ProtocolHandlerIconPath", 2u, 0, &pvData, &pcbData);
    v9 = ValueW;
    if ( ValueW )
    {
      pvData = 0;
      if ( ValueW > 0 )
        v9 = (unsigned __int16)ValueW | 0x80070000;
    }
    if ( v9 < 0 )
    {
      v9 = 0;
    }
    else
    {
      v23 = PathParseIconLocationW(&pvData);
      if ( v23 )
      {
        *a4 = Shell_GetCachedImageIndex(&pvData, v23, 0);
        v19 = 1;
      }
    }
    RegCloseKey(*(HKEY *)hKey);
    if ( !v19 )
      return 1;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180003ac8  push    rbp
0x180003aca  push    rbx
0x180003acb  push    rsi
0x180003acc  push    rdi
0x180003acd  push    r12
0x180003acf  push    r13
0x180003ad1  push    r14
0x180003ad3  push    r15
0x180003ad5  lea     rbp, [rsp-7D8h]
0x180003add  sub     rsp, 8D8h
0x180003ae4  mov     rax, cs:__security_cookie
0x180003aeb  xor     rax, rsp
0x180003aee  mov     [rbp+810h+var_50], rax
0x180003af5  mov     eax, [rcx+14h]
0x180003af8  mov     r14, rdx
0x180003afb  mov     rsi, rcx
0x180003afe  mov     [r9], eax
0x180003b01  mov     r13d, 104h
0x180003b07  mov     rcx, r14; pszUrl
0x180003b0a  mov     edx, 3; UrlIs
0x180003b0f  mov     [rsp+910h+pcchPath], r13d
0x180003b14  mov     r15, r9
0x180003b17  mov     rdi, r8
0x180003b1a  call    cs:__imp_UrlIsW
0x180003b20  xor     r12d, r12d
0x180003b23  test    eax, eax
0x180003b25  jz      loc_180003C5F
0x180003b2b  xor     r9d, r9d; dwFlags
0x180003b2e  lea     r8, [rsp+910h+pcchPath]; pcchPath
0x180003b33  mov     rdx, rdi; pszPath
0x180003b36  mov     rcx, r14; pszUrl
0x180003b39  call    cs:__imp_PathCreateFromUrlW
0x180003b3f  mov     [rsp+910h+pcchPath], r13d
0x180003b44  mov     edx, r13d; unsigned __int64
0x180003b47  mov     ebx, eax
0x180003b49  test    eax, eax
0x180003b4b  js      loc_180003C3F
0x180003b51  mov     r8, rdi; unsigned __int16 *
0x180003b54  lea     rcx, [rbp+810h+pszPath]; unsigned __int16 *
0x180003b5b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003b60  lea     rcx, [rbp+810h+pszPath]; pszPath
0x180003b67  call    cs:__imp_PathStripPathW
0x180003b6d  lea     rax, [rbp+810h+pszPath]
0x180003b74  mov     r8, rdi
0x180003b77  sub     r8, rax
0x180003b7a  movzx   ecx, word ptr [rax]
0x180003b7d  movzx   edx, word ptr [rax+r8]
0x180003b82  sub     ecx, edx
0x180003b84  jnz     short loc_180003B8E
0x180003b86  add     rax, 2
0x180003b8a  test    edx, edx
0x180003b8c  jnz     short loc_180003B7A
0x180003b8e  test    ecx, ecx
0x180003b90  jnz     loc_180003C4A
0x180003b96  xor     edx, edx; Val
0x180003b98  mov     [rbp+810h+pvData], r12w
0x180003b9d  mov     r8d, 206h; Size
0x180003ba3  lea     rcx, [rbp+810h+var_88E]; void *
0x180003ba7  call    memset_0
0x180003bac  movzx   ecx, word ptr [rdi]; unsigned __int16
0x180003baf  lea     r8, [rsp+910h+pcbData]; unsigned int *
0x180003bb4  lea     rdx, [rbp+810h+pvData]; unsigned __int16 *
0x180003bb8  mov     [rsp+910h+pcbData], r12d
0x180003bbd  call    ?GetDriveInfo@@YAXGPEAGPEAK@Z; GetDriveInfo(ushort,ushort *,ulong *)
0x180003bc2  mov     ecx, [rsp+910h+pcbData]
0x180003bc6  mov     eax, 1Ch
0x180003bcb  cmp     ecx, 3
0x180003bce  lea     edx, [rax-4]
0x180003bd1  cmovz   eax, edx
0x180003bd4  mov     eax, [rsi+rax]
0x180003bd7  mov     [r15], eax
0x180003bda  mov     eax, dword ptr cs:asc_1800385C8+6; ":)"
0x180003be0  mov     dword ptr [rsp+910h+hKey+6], eax
0x180003be4  movzx   eax, word ptr cs:asc_1800385C8+0Ah; ""
0x180003beb  mov     [rsp+910h+var_8BE], ax
0x180003bf0  movzx   eax, word ptr [rdi]
0x180003bf3  mov     word ptr [rsp+910h+hKey+4], ax
0x180003bf8  mov     dword ptr [rsp+910h+hKey], 280020h
0x180003c00  cmp     [rbp+810h+pvData], r12w
0x180003c05  jz      short loc_180003C0D
0x180003c07  lea     r8, [rbp+810h+pvData]
0x180003c0b  jmp     short loc_180003C20
0x180003c0d  lea     r8, [rsi+220h]
0x180003c14  cmp     ecx, 3
0x180003c17  jz      short loc_180003C20
0x180003c19  lea     r8, [rsi+420h]; unsigned __int16 *
0x180003c20  mov     edx, [rsp+910h+pcchPath]; unsigned __int64
0x180003c24  mov     rcx, rdi; unsigned __int16 *
0x180003c27  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003c2c  mov     edx, [rsp+910h+pcchPath]; unsigned __int64
0x180003c30  lea     r8, [rsp+910h+hKey]; unsigned __int16 *
0x180003c35  mov     rcx, rdi; unsigned __int16 *
0x180003c38  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003c3d  jmp     short loc_180003C4A
0x180003c3f  mov     r8, r14; unsigned __int16 *
0x180003c42  mov     rcx, rdi; unsigned __int16 *
0x180003c45  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003c4a  mov     edx, [rsp+910h+pcchPath]; unsigned __int64
0x180003c4e  lea     r8, [rsi+20h]; unsigned __int16 *
0x180003c52  mov     rcx, rdi; unsigned __int16 *
0x180003c55  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003c5a  jmp     loc_180003DE9
0x180003c5f  mov     edx, [rsp+910h+pcchPath]; unsigned __int64
0x180003c63  mov     r8, r14; unsigned __int16 *
0x180003c66  mov     rcx, rdi; unsigned __int16 *
0x180003c69  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003c6e  xorps   xmm0, xmm0
0x180003c71  lea     rdx, [rsp+910h+ppu]; ppu
0x180003c76  xor     eax, eax
0x180003c78  mov     rcx, r14; pcszURL
0x180003c7b  movups  xmmword ptr [rsp+910h+ppu.cbSize], xmm0
0x180003c80  mov     qword ptr [rsp+910h+ppu.cchSuffix], rax
0x180003c85  mov     [rsp+910h+ppu.cbSize], 28h ; '('
0x180003c8d  movups  xmmword ptr [rsp+910h+ppu.cchProtocol], xmm0
0x180003c92  call    cs:__imp_ParseURLW
0x180003c98  mov     r14d, 1
0x180003c9e  test    eax, eax
0x180003ca0  js      loc_180003DE6
0x180003ca6  mov     r9d, [rsp+910h+ppu.cchProtocol]; unsigned __int64
0x180003cab  lea     rcx, [rbp+810h+SubKey]; unsigned __int16 *
0x180003cb2  mov     r8, [rsp+910h+ppu.pszProtocol]; unsigned __int16 *
0x180003cb7  mov     rdx, r13; unsigned __int64
0x180003cba  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180003cbf  test    eax, eax
0x180003cc1  js      loc_180003DE6
0x180003cc7  lea     rax, [rsp+910h+hKey]
0x180003ccc  mov     qword ptr [rsp+910h+hKey], r12
0x180003cd1  mov     r9d, 20019h; samDesired
0x180003cd7  mov     [rsp+910h+phkResult], rax; phkResult
0x180003cdc  xor     r8d, r8d; ulOptions
0x180003cdf  lea     rdx, [rbp+810h+SubKey]; lpSubKey
0x180003ce6  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180003ced  call    cs:__imp_RegOpenKeyExW
0x180003cf3  mov     ebx, 80070000h
0x180003cf8  test    eax, eax
0x180003cfa  jle     short loc_180003D03
0x180003cfc  movzx   eax, ax
0x180003cff  or      eax, ebx
0x180003d01  test    eax, eax
0x180003d03  js      loc_180003DE6
0x180003d09  mov     rcx, qword ptr [rsp+910h+hKey]; hKey
0x180003d0e  lea     r8, [rbp+810h+pszOutBuf]; pszOutBuf
0x180003d15  mov     [rsp+910h+pszDirectory], r12; pszDirectory
0x180003d1a  lea     rdx, pszValue; "ProtocolHandlerDisplayName"
0x180003d21  mov     [rsp+910h+Flags], r14d; Flags
0x180003d26  mov     r9d, r13d; cbOutBuf
0x180003d29  mov     [rsp+910h+phkResult], r12; pcbData
0x180003d2e  mov     sil, r12b
0x180003d31  call    cs:__imp_RegLoadMUIStringW
0x180003d37  test    eax, eax
0x180003d39  jle     short loc_180003D42
0x180003d3b  movzx   eax, ax
0x180003d3e  or      eax, ebx
0x180003d40  test    eax, eax
0x180003d42  js      short loc_180003D5A
0x180003d44  mov     edx, [rsp+910h+pcchPath]; unsigned __int64
0x180003d48  lea     r8, [rbp+810h+pszOutBuf]; unsigned __int16 *
0x180003d4f  mov     rcx, rdi; unsigned __int16 *
0x180003d52  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003d57  mov     sil, r14b
0x180003d5a  mov     rcx, qword ptr [rsp+910h+hKey]; hkey
0x180003d5f  lea     rax, [rsp+910h+pcbData]
0x180003d64  mov     [rsp+910h+pszDirectory], rax; pcbData
0x180003d69  lea     r8, aProtocolhandle; "ProtocolHandlerIconPath"
0x180003d70  lea     rax, [rbp+810h+pvData]
0x180003d74  mov     [rsp+910h+pcbData], 208h
0x180003d7c  mov     qword ptr [rsp+910h+Flags], rax; pvData
0x180003d81  mov     r9d, 2; dwFlags
0x180003d87  xor     edx, edx; lpSubKey
0x180003d89  mov     [rsp+910h+phkResult], r12; pdwType
0x180003d8e  call    cs:__imp_RegGetValueW
0x180003d94  mov     ebx, eax
0x180003d96  test    eax, eax
0x180003d98  jz      short loc_180003DAA
0x180003d9a  mov     [rbp+810h+pvData], r12w
0x180003d9f  jle     short loc_180003DAA
0x180003da1  movzx   ebx, ax
0x180003da4  or      ebx, 80070000h
0x180003daa  test    ebx, ebx
0x180003dac  js      short loc_180003DD3
0x180003dae  lea     rcx, [rbp+810h+pvData]; pszIconFile
0x180003db2  call    cs:__imp_PathParseIconLocationW
0x180003db8  test    eax, eax
0x180003dba  jz      short loc_180003DD6
0x180003dbc  xor     r8d, r8d; uIconFlags
0x180003dbf  lea     rcx, [rbp+810h+pvData]; pwszIconPath
0x180003dc3  mov     edx, eax; iIconIndex
0x180003dc5  call    cs:__imp_Shell_GetCachedImageIndex
0x180003dcb  mov     [r15], eax
0x180003dce  mov     sil, r14b
0x180003dd1  jmp     short loc_180003DD6
0x180003dd3  mov     ebx, r12d
0x180003dd6  mov     rcx, qword ptr [rsp+910h+hKey]; hKey
0x180003ddb  call    cs:__imp_RegCloseKey
0x180003de1  test    sil, sil
0x180003de4  jnz     short loc_180003DE9
0x180003de6  mov     ebx, r14d
0x180003de9  mov     eax, ebx
0x180003deb  mov     rcx, [rbp+810h+var_50]
0x180003df2  xor     rcx, rsp; StackCookie
0x180003df5  call    __security_check_cookie
0x180003dfa  add     rsp, 8D8h
0x180003e01  pop     r15
0x180003e03  pop     r14
0x180003e05  pop     r13
0x180003e07  pop     r12
0x180003e09  pop     rdi
0x180003e0a  pop     rsi
0x180003e0b  pop     rbx
0x180003e0c  pop     rbp
0x180003e0d  retn
```
