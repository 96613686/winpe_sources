# PathCompactPathW

- ea: `0x18000ee00`
- end: `0x18000f1b3`
- name: `PathCompactPathW`
- size: `947`
- prototype: `BOOL __stdcall(HDC hDC, LPWSTR pszPath, UINT dx)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180020bd0`

## callees

- `0x180003400`
- `0x18000ee00`
- `0x180012550`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18000ef0f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18000ef0f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000ee7e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000ef2f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000efb7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000ee7e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000ef2f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000efb7`
- `GDI32!GetGlyphIndicesW` at `0x18000eefd`
- `GDI32!GetGlyphIndicesW` at `0x18000eefd`
- `GDI32!GetTextExtentPointW` at `0x18000ee95`
- `GDI32!GetTextExtentPointW` at `0x18000eec6`
- `GDI32!GetTextExtentPointW` at `0x18000ef47`
- `GDI32!GetTextExtentPointW` at `0x18000ef8a`
- `GDI32!GetTextExtentPointW` at `0x18000ee95`
- `GDI32!GetTextExtentPointW` at `0x18000eec6`
- `GDI32!GetTextExtentPointW` at `0x18000ef47`
- `GDI32!GetTextExtentPointW` at `0x18000ef8a`
- `GDI32!GetTextExtentExPointI` at `0x18000f022`
- `GDI32!GetTextExtentExPointI` at `0x18000f119`
- `GDI32!GetTextExtentExPointI` at `0x18000f022`
- `GDI32!GetTextExtentExPointI` at `0x18000f119`
- `USER32!GetDC` at `0x18000ee6f`
- `USER32!GetDC` at `0x18000ee6f`
- `USER32!ReleaseDC` at `0x18000f180`
- `USER32!ReleaseDC` at `0x18000f180`

## pseudocode

```c
BOOL __stdcall PathCompactPathW(HDC hDC, LPWSTR pszPath, UINT dx)
{
  BOOL v4; // r15d
  HDC v6; // rdi
  HDC DC; // r13
  int v8; // r14d
  int v9; // ecx
  LONG v10; // eax
  int v11; // r11d
  int v12; // eax
  int v13; // r8d
  int v14; // ecx
  WCHAR *v15; // r8
  int v16; // r14d
  unsigned __int16 *v17; // rcx
  int v18; // r8d
  int v19; // r9d
  LONG v21; // [rsp+40h] [rbp-C0h]
  LONG v22; // [rsp+44h] [rbp-BCh]
  LONG cx; // [rsp+48h] [rbp-B8h]
  unsigned __int16 *FileNameW; // [rsp+50h] [rbp-B0h]
  int nFit; // [rsp+60h] [rbp-A0h] BYREF
  int v26; // [rsp+64h] [rbp-9Ch] BYREF
  tagSIZE sz; // [rsp+68h] [rbp-98h] BYREF
  WCHAR String[256]; // [rsp+70h] [rbp-90h] BYREF
  WORD pgi[264]; // [rsp+270h] [rbp+170h] BYREF

  v4 = 1;
  v6 = hDC;
  if ( !pszPath )
    return v4;
  v4 = 0;
  v26 = 0;
  DC = 0;
  nFit = 0;
  sz = 0;
  if ( !hDC )
  {
    DC = GetDC(0);
    v6 = DC;
  }
  v8 = lstrlenW(pszPath);
  if ( GetTextExtentPointW(v6, pszPath, v8, &sz) )
  {
    if ( sz.cx <= dx )
    {
      v4 = 1;
      goto LABEL_34;
    }
    if ( !GetTextExtentPointW(v6, L"...", 3, &sz) )
      goto LABEL_34;
    cx = sz.cx;
    if ( v8 > 259 )
      v8 = 259;
    if ( GetGlyphIndicesW(v6, pszPath, v8, pgi, 0) == -1 )
      goto LABEL_34;
    FileNameW = PathFindFileNameW(pszPath);
    nFit = FileNameW - pszPath;
    v26 = lstrlenW(FileNameW);
    if ( !GetTextExtentPointW(v6, FileNameW, v26, &sz) )
      goto LABEL_34;
    v9 = nFit;
    v10 = sz.cx;
    v11 = 0;
    v22 = sz.cx;
    if ( nFit )
    {
      if ( !GetTextExtentPointW(v6, L"...\\", 4, &sz) )
        goto LABEL_34;
      v21 = sz.cx;
      StringCchCopyW(String, 0x100u, FileNameW);
      v12 = lstrlenW(String);
      v13 = nFit;
      v26 = v12;
      if ( nFit > 255 - v12 )
      {
        v13 = 255 - v12;
        nFit = 255 - v12;
      }
      if ( v13 > 0 && dx > v21 + v22 )
      {
        if ( !GetTextExtentExPointI(v6, pgi, v13, dx - v21 - v22, &nFit, 0, &sz) )
          goto LABEL_34;
        v14 = nFit;
        if ( nFit > 1 && (unsigned __int16)(pszPath[nFit] + 9216) <= 0x3FFu )
          v14 = --nFit;
        StringCchCopyW(&pszPath[v14], 260 - v14, L"...\\");
        v15 = String;
        v16 = 260 - (nFit + 4);
        nFit += 4;
        v17 = &pszPath[nFit];
        goto LABEL_32;
      }
      StringCchCopyW(pszPath, 0x104u, L"...\\");
      nFit = 4;
      StringCchCopyW(pszPath + 4, 0x100u, String);
      v9 = 4;
      v10 = v22;
    }
    if ( dx >= v11 + v10 )
    {
LABEL_33:
      v4 = 1;
      goto LABEL_34;
    }
    v18 = v26;
    if ( v26 > 256 - v9 )
    {
      v18 = 256 - v9;
      v26 = 256 - v9;
    }
    if ( !GetTextExtentExPointI(v6, &pgi[FileNameW - pszPath], v18, dx - cx - v11, &v26, 0, &sz) )
      goto LABEL_34;
    v19 = v26;
    if ( v26 > 1 && (unsigned __int16)(pszPath[v26] + 9216) <= 0x3FFu )
      v19 = --v26;
    v15 = (WCHAR *)L"...";
    v16 = 260 - nFit - v19;
    v17 = &pszPath[v19 + (__int64)nFit];
LABEL_32:
    StringCchCopyW(v17, v16, v15);
    goto LABEL_33;
  }
LABEL_34:
  if ( DC )
    ReleaseDC(0, DC);
  return v4;
}

```

## disassembly

```asm
0x18000ee00  mov     [rsp-8+arg_18], rbx
0x18000ee05  push    rbp
0x18000ee06  push    rsi
0x18000ee07  push    rdi
0x18000ee08  push    r12
0x18000ee0a  push    r13
0x18000ee0c  push    r14
0x18000ee0e  push    r15
0x18000ee10  lea     rbp, [rsp-390h]
0x18000ee18  sub     rsp, 490h
0x18000ee1f  mov     rax, cs:__security_cookie
0x18000ee26  xor     rax, rsp
0x18000ee29  mov     [rbp+3C0h+var_40], rax
0x18000ee30  mov     r12d, 1
0x18000ee36  mov     esi, r8d
0x18000ee39  mov     r15d, r12d
0x18000ee3c  mov     rbx, rdx
0x18000ee3f  mov     rdi, rcx
0x18000ee42  test    rdx, rdx
0x18000ee45  jz      loc_18000F186
0x18000ee4b  xor     r15d, r15d
0x18000ee4e  mov     [rsp+4C0h+var_45C], 0
0x18000ee56  xor     r13d, r13d
0x18000ee59  mov     [rsp+4C0h+nFit], 0
0x18000ee61  mov     qword ptr [rsp+4C0h+sz.cx], 0
0x18000ee6a  test    rcx, rcx
0x18000ee6d  jnz     short loc_18000EE7B
0x18000ee6f  call    cs:__imp_GetDC
0x18000ee75  mov     r13, rax
0x18000ee78  mov     rdi, rax
0x18000ee7b  mov     rcx, rbx; lpString
0x18000ee7e  call    cs:__imp_lstrlenW
0x18000ee84  lea     r9, [rsp+4C0h+sz]; lpsz
0x18000ee89  mov     rdx, rbx; lpString
0x18000ee8c  mov     r8d, eax; c
0x18000ee8f  mov     rcx, rdi; hdc
0x18000ee92  mov     r14d, eax
0x18000ee95  call    cs:__imp_GetTextExtentPointW
0x18000ee9b  test    eax, eax
0x18000ee9d  jz      loc_18000F176
0x18000eea3  cmp     [rsp+4C0h+sz.cx], esi
0x18000eea7  ja      short loc_18000EEB1
0x18000eea9  mov     r15d, r12d
0x18000eeac  jmp     loc_18000F176
0x18000eeb1  lea     r9, [rsp+4C0h+sz]; lpsz
0x18000eeb6  mov     r8d, 3; c
0x18000eebc  lea     rdx, asc_18003E418; "..."
0x18000eec3  mov     rcx, rdi; hdc
0x18000eec6  call    cs:__imp_GetTextExtentPointW
0x18000eecc  test    eax, eax
0x18000eece  jz      loc_18000F176
0x18000eed4  mov     eax, [rsp+4C0h+sz.cx]
0x18000eed8  lea     r9, [rbp+3C0h+pgi]; pgi
0x18000eedf  mov     [rsp+4C0h+var_478], eax
0x18000eee3  mov     rdx, rbx; lpstr
0x18000eee6  mov     eax, 103h
0x18000eeeb  mov     [rsp+4C0h+fl], r15d; fl
0x18000eef0  cmp     r14d, eax
0x18000eef3  mov     rcx, rdi; hdc
0x18000eef6  cmovg   r14d, eax
0x18000eefa  mov     r8d, r14d; c
0x18000eefd  call    cs:__imp_GetGlyphIndicesW
0x18000ef03  cmp     eax, 0FFFFFFFFh
0x18000ef06  jz      loc_18000F176
0x18000ef0c  mov     rcx, rbx; pszPath
0x18000ef0f  call    cs:__imp_PathFindFileNameW
0x18000ef15  mov     r14, rax
0x18000ef18  mov     [rsp+4C0h+var_470], rax
0x18000ef1d  sub     rax, rbx
0x18000ef20  mov     rcx, r14; lpString
0x18000ef23  sar     rax, 1
0x18000ef26  mov     [rsp+4C0h+var_468], rax
0x18000ef2b  mov     [rsp+4C0h+nFit], eax
0x18000ef2f  call    cs:__imp_lstrlenW
0x18000ef35  lea     r9, [rsp+4C0h+sz]; lpsz
0x18000ef3a  mov     rdx, r14; lpString
0x18000ef3d  mov     r8d, eax; c
0x18000ef40  mov     [rsp+4C0h+var_45C], eax
0x18000ef44  mov     rcx, rdi; hdc
0x18000ef47  call    cs:__imp_GetTextExtentPointW
0x18000ef4d  test    eax, eax
0x18000ef4f  jz      loc_18000F176
0x18000ef55  mov     ecx, [rsp+4C0h+nFit]
0x18000ef59  mov     r12d, 100h
0x18000ef5f  mov     eax, [rsp+4C0h+sz.cx]
0x18000ef63  xor     r11d, r11d
0x18000ef66  mov     [rsp+4C0h+var_47C], eax
0x18000ef6a  lea     r14d, [r12+4]
0x18000ef6f  test    ecx, ecx
0x18000ef71  jz      loc_18000F0C3
0x18000ef77  lea     r9, [rsp+4C0h+sz]; lpsz
0x18000ef7c  mov     rcx, rdi; hdc
0x18000ef7f  lea     r8d, [r11+4]; c
0x18000ef83  lea     rdx, asc_18003E408; "...\\"
0x18000ef8a  call    cs:__imp_GetTextExtentPointW
0x18000ef90  test    eax, eax
0x18000ef92  jz      loc_18000F176
0x18000ef98  mov     eax, [rsp+4C0h+sz.cx]
0x18000ef9c  lea     rcx, [rsp+4C0h+String]; unsigned __int16 *
0x18000efa1  mov     r8, [rsp+4C0h+var_470]; unsigned __int16 *
0x18000efa6  mov     edx, r12d; unsigned __int64
0x18000efa9  mov     [rsp+4C0h+var_480], eax
0x18000efad  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000efb2  lea     rcx, [rsp+4C0h+String]; lpString
0x18000efb7  call    cs:__imp_lstrlenW
0x18000efbd  mov     r8d, [rsp+4C0h+nFit]
0x18000efc2  lea     ecx, [r12-1]
0x18000efc7  sub     ecx, eax
0x18000efc9  mov     [rsp+4C0h+var_45C], eax
0x18000efcd  cmp     r8d, ecx
0x18000efd0  jle     short loc_18000EFD9
0x18000efd2  mov     r8d, ecx; cwchString
0x18000efd5  mov     [rsp+4C0h+nFit], ecx
0x18000efd9  mov     r11d, [rsp+4C0h+var_480]
0x18000efde  test    r8d, r8d
0x18000efe1  jle     loc_18000F090
0x18000efe7  mov     ecx, [rsp+4C0h+var_47C]
0x18000efeb  lea     eax, [r11+rcx]
0x18000efef  cmp     esi, eax
0x18000eff1  jbe     loc_18000F090
0x18000eff7  sub     esi, r11d
0x18000effa  lea     rax, [rsp+4C0h+sz]
0x18000efff  mov     [rsp+4C0h+lpSize], rax; lpSize
0x18000f004  lea     rdx, [rbp+3C0h+pgi]; lpwszString
0x18000f00b  sub     esi, ecx
0x18000f00d  mov     [rsp+4C0h+lpnDx], r15; lpnDx
0x18000f012  lea     rax, [rsp+4C0h+nFit]
0x18000f017  mov     r9d, esi; nMaxExtent
0x18000f01a  mov     rcx, rdi; hdc
0x18000f01d  mov     qword ptr [rsp+4C0h+fl], rax; lpnFit
0x18000f022  call    cs:__imp_GetTextExtentExPointI
0x18000f028  test    eax, eax
0x18000f02a  jz      loc_18000F176
0x18000f030  movsxd  rcx, [rsp+4C0h+nFit]
0x18000f035  cmp     ecx, 1
0x18000f038  jle     short loc_18000F053
0x18000f03a  mov     edx, 2400h
0x18000f03f  mov     eax, 3FFh
0x18000f044  add     dx, [rbx+rcx*2]
0x18000f048  cmp     dx, ax
0x18000f04b  ja      short loc_18000F053
0x18000f04d  dec     ecx
0x18000f04f  mov     [rsp+4C0h+nFit], ecx
0x18000f053  mov     eax, r14d
0x18000f056  lea     r8, asc_18003E408; "...\\"
0x18000f05d  sub     eax, ecx
0x18000f05f  movsxd  rdx, eax; unsigned __int64
0x18000f062  movsxd  rax, ecx
0x18000f065  lea     rcx, [rbx+rax*2]; unsigned __int16 *
0x18000f069  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f06e  mov     r11d, [rsp+4C0h+nFit]
0x18000f073  lea     r8, [rsp+4C0h+String]
0x18000f078  add     r11d, 4
0x18000f07c  movsxd  rax, r11d
0x18000f07f  sub     r14d, r11d
0x18000f082  mov     [rsp+4C0h+nFit], r11d
0x18000f087  lea     rcx, [rbx+rax*2]
0x18000f08b  jmp     loc_18000F168
0x18000f090  lea     r8, asc_18003E408; "...\\"
0x18000f097  mov     rdx, r14; unsigned __int64
0x18000f09a  mov     rcx, rbx; unsigned __int16 *
0x18000f09d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f0a2  lea     rcx, [rbx+8]; unsigned __int16 *
0x18000f0a6  mov     [rsp+4C0h+nFit], 4
0x18000f0ae  lea     r8, [rsp+4C0h+String]; unsigned __int16 *
0x18000f0b3  mov     rdx, r12; unsigned __int64
0x18000f0b6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f0bb  mov     ecx, [rsp+4C0h+nFit]
0x18000f0bf  mov     eax, [rsp+4C0h+var_47C]
0x18000f0c3  add     eax, r11d
0x18000f0c6  cmp     esi, eax
0x18000f0c8  jnb     loc_18000F170
0x18000f0ce  mov     r8d, [rsp+4C0h+var_45C]
0x18000f0d3  sub     r12d, ecx
0x18000f0d6  cmp     r8d, r12d
0x18000f0d9  jle     short loc_18000F0E3
0x18000f0db  mov     r8d, r12d; cwchString
0x18000f0de  mov     [rsp+4C0h+var_45C], r12d
0x18000f0e3  mov     rax, [rsp+4C0h+var_468]
0x18000f0e8  lea     rdx, [rbp+3C0h+pgi]
0x18000f0ef  sub     esi, [rsp+4C0h+var_478]
0x18000f0f3  mov     rcx, rdi; hdc
0x18000f0f6  sub     esi, r11d
0x18000f0f9  mov     r9d, esi; nMaxExtent
0x18000f0fc  lea     rdx, [rdx+rax*2]; lpwszString
0x18000f100  lea     rax, [rsp+4C0h+sz]
0x18000f105  mov     [rsp+4C0h+lpSize], rax; lpSize
0x18000f10a  lea     rax, [rsp+4C0h+var_45C]
0x18000f10f  mov     [rsp+4C0h+lpnDx], r15; lpnDx
0x18000f114  mov     qword ptr [rsp+4C0h+fl], rax; lpnFit
0x18000f119  call    cs:__imp_GetTextExtentExPointI
0x18000f11f  test    eax, eax
0x18000f121  jz      short loc_18000F176
0x18000f123  movsxd  r9, [rsp+4C0h+var_45C]
0x18000f128  cmp     r9d, 1
0x18000f12c  jle     short loc_18000F14A
0x18000f12e  mov     edx, 2400h
0x18000f133  mov     eax, 3FFh
0x18000f138  add     dx, [rbx+r9*2]
0x18000f13d  cmp     dx, ax
0x18000f140  ja      short loc_18000F14A
0x18000f142  dec     r9d
0x18000f145  mov     [rsp+4C0h+var_45C], r9d
0x18000f14a  sub     r14d, [rsp+4C0h+nFit]
0x18000f14f  lea     r8, asc_18003E418; "..."
0x18000f156  movsxd  rcx, [rsp+4C0h+nFit]
0x18000f15b  sub     r14d, r9d
0x18000f15e  movsxd  rax, r9d
0x18000f161  add     rcx, rax
0x18000f164  lea     rcx, [rbx+rcx*2]; unsigned __int16 *
0x18000f168  movsxd  rdx, r14d; unsigned __int64
0x18000f16b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f170  mov     r15d, 1
0x18000f176  test    r13, r13
0x18000f179  jz      short loc_18000F186
0x18000f17b  mov     rdx, r13; hDC
0x18000f17e  xor     ecx, ecx; hWnd
0x18000f180  call    cs:__imp_ReleaseDC
0x18000f186  mov     eax, r15d
0x18000f189  mov     rcx, [rbp+3C0h+var_40]
0x18000f190  xor     rcx, rsp; StackCookie
0x18000f193  call    __security_check_cookie
0x18000f198  mov     rbx, [rsp+4C0h+arg_18]
0x18000f1a0  add     rsp, 490h
0x18000f1a7  pop     r15
0x18000f1a9  pop     r14
0x18000f1ab  pop     r13
0x18000f1ad  pop     r12
0x18000f1af  pop     rdi
0x18000f1b0  pop     rsi
0x18000f1b1  pop     rbp
0x18000f1b2  retn
```
