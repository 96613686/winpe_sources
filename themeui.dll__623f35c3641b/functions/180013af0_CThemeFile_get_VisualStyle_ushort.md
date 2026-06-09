# CThemeFile::get_VisualStyle(ushort * *)

- ea: `0x180013af0`
- end: `0x180013e49`
- name: `?get_VisualStyle@CThemeFile@@UEAAJPEAPEAG@Z`
- size: `857`
- prototype: `int(CThemeFile *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800089c0`
- `0x18000d490`
- `0x18000dd60`
- `0x18000e780`
- `0x180013af0`
- `0x180015190`
- `0x180015660`
- `0x1800358c0`
- `0x18003633c`
- `0x180052974`
- `0x180060fac`
- `0x18006d010`

## import_xrefs

- `SHLWAPI!PathIsRelativeW` at `0x180013d95`
- `SHLWAPI!PathIsRelativeW` at `0x180013d95`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x180013e25`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x180013e25`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x180013d5d`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x180013d5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013c79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013de9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013c79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013de9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013b7a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013b7a`
- `OLEAUT32!__imp_SysAllocString` at `0x180013c5c`
- `OLEAUT32!__imp_SysAllocString` at `0x180013c5c`

## pseudocode

```c
__int64 __fastcall CThemeFile::get_VisualStyle(CThemeFile *this, unsigned __int16 **a2)
{
  OLECHAR *v2; // rdi
  unsigned int v5; // esi
  __int64 *v6; // r14
  HRESULT v7; // r15d
  __int64 v8; // rcx
  bool v9; // zf
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rax
  unsigned __int16 *v14; // rax
  unsigned int v15; // edx
  struct IUnknown *v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  HRESULT v19; // eax
  unsigned int v20[2]; // [rsp+48h] [rbp-C0h] BYREF
  PCWSTR pszSource; // [rsp+50h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-B0h] BYREF
  OLECHAR *v23; // [rsp+60h] [rbp-A8h] BYREF
  WCHAR pszOutBuf[264]; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int16 v25[264]; // [rsp+278h] [rbp+170h] BYREF

  v2 = 0;
  *a2 = 0;
  v23 = 0;
  v5 = -2147467259;
  if ( !*((_QWORD *)this + 4) )
  {
    v7 = -2147467259;
    goto LABEL_13;
  }
  v6 = (__int64 *)*((_QWORD *)this + 5);
  if ( v6 )
  {
    v9 = *((_BYTE *)this + 48) == 0;
    v10 = *((_QWORD *)this + 5);
    v11 = *v6;
    if ( v9 )
    {
      (*(void (__fastcall **)(__int64))(v11 + 8))(v10);
      goto LABEL_21;
    }
    (*(void (__fastcall **)(__int64))(v11 + 96))(v10);
  }
  ppv = 0;
  v7 = CoCreateInstance(&CLSID_PrivateProfile, 0, 1u, &GUID_b57046bc_32e5_428a_9887_19f712b907bf, &ppv);
  if ( v7 < 0 )
    goto LABEL_13;
  v7 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64))(*(_QWORD *)ppv + 24LL))(
         ppv,
         *((_QWORD *)this + 4),
         0x400000);
  if ( v7 >= 0 )
  {
    v8 = *((_QWORD *)this + 5);
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    v6 = (__int64 *)ppv;
    *((_QWORD *)this + 5) = ppv;
    (*(void (__fastcall **)(__int64 *))(*v6 + 8))(v6);
    *((_BYTE *)this + 48) = 0;
LABEL_21:
    pszSource = 0;
    if ( (int)StringCchPrintfW(v25, 0x104u, L"%s.MUI", L"Path") < 0
      || (*(int (__fastcall **)(__int64 *, const WCHAR *, unsigned __int16 *, _QWORD, int, PCWSTR *))(*v6 + 48))(
           v6,
           L"VisualStyles",
           v25,
           0,
           1,
           &pszSource) < 0 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64 *, const WCHAR *, const WCHAR *, _QWORD, int, PCWSTR *))(*v6 + 48))(
             v6,
             L"VisualStyles",
             L"Path",
             0,
             1,
             &pszSource);
      if ( v7 < 0 )
        goto LABEL_34;
    }
    memset_0(pszOutBuf, 0, 0x208u);
    v7 = SHLoadIndirectString(pszSource, pszOutBuf, 0x104u, 0);
    if ( v7 >= 0 )
    {
      v7 = ExpandResourceDir(pszOutBuf, v15);
      if ( v7 >= 0 )
      {
        v7 = ExpandThemeTokens(*((const unsigned __int16 **)this + 4), pszOutBuf);
        if ( v7 >= 0 )
        {
          if ( !PathIsRelativeW(pszOutBuf) )
          {
            v20[0] = 0;
            SHMapUrlToZoneEx(pszOutBuf, v16, v18, v20);
            if ( pszOutBuf[0] && v20[0] && !CFileSource::s_IsUncPathAllowedForThumbnailImage() )
            {
              pszOutBuf[0] = 0;
            }
            else if ( (unsigned int)ConfirmFile(pszOutBuf) == 3 )
            {
              v7 = -2147024894;
              goto LABEL_33;
            }
          }
          v19 = _AllocString<CTCoAllocPolicy>(v17, v16, pszOutBuf, &v23);
          v2 = v23;
          v7 = v19;
        }
      }
    }
LABEL_33:
    CoTaskMemFree((LPVOID)pszSource);
LABEL_34:
    v12 = *v6;
    goto LABEL_12;
  }
  v12 = *(_QWORD *)ppv;
LABEL_12:
  (*(void (**)(void))(v12 + 16))();
LABEL_13:
  if ( v7 < 0 )
    return (unsigned int)v7;
  if ( *v2 )
  {
    v5 = 0;
    v14 = SysAllocString(v2);
    *a2 = v14;
    if ( v2 )
    {
      if ( !v14 )
        v5 = -2147024882;
    }
  }
  else if ( (unsigned int)SHExpandEnvironmentStringsW(
                            L"%SystemRoot%\\resources\\themes\\Aero\\AeroLite.msstyles",
                            v25,
                            260) )
  {
    v5 = HrSysAllocString(v25, a2);
  }
  CoTaskMemFree(v2);
  return v5;
}

```

## disassembly

```asm
0x180013af0  mov     r11, rsp
0x180013af3  push    rbp
0x180013af4  push    rsi
0x180013af5  push    rdi
0x180013af6  push    r12
0x180013af8  push    r15
0x180013afa  lea     rbp, [r11-3C8h]
0x180013b01  sub     rsp, 4A0h
0x180013b08  mov     rax, cs:__security_cookie
0x180013b0f  xor     rax, rsp
0x180013b12  mov     [rbp+3C0h+var_40], rax
0x180013b19  xor     edi, edi
0x180013b1b  mov     qword ptr [rdx], 0
0x180013b22  mov     r12, rdx
0x180013b25  mov     [r11+18h], rbx
0x180013b29  mov     rbx, rcx
0x180013b2c  mov     [rsp+4C0h+var_468], rdi
0x180013b31  mov     esi, 80004005h
0x180013b36  cmp     [rcx+20h], rdi
0x180013b3a  jz      loc_180013BF9
0x180013b40  mov     [r11-30h], r13
0x180013b44  mov     [r11-38h], r14
0x180013b48  mov     r14, [rcx+28h]
0x180013b4c  test    r14, r14
0x180013b4f  jnz     loc_180013BDB
0x180013b55  lea     rax, [rsp+4C0h+var_470]
0x180013b5a  mov     [rsp+4C0h+var_470], rdi
0x180013b5f  lea     r9, _GUID_b57046bc_32e5_428a_9887_19f712b907bf; riid
0x180013b66  mov     [rsp+4C0h+ppv], rax; ppv
0x180013b6b  xor     edx, edx; pUnkOuter
0x180013b6d  lea     rcx, CLSID_PrivateProfile; rclsid
0x180013b74  mov     r8d, 1; dwClsContext
0x180013b7a  call    cs:__imp_CoCreateInstance
0x180013b80  mov     r15d, eax
0x180013b83  test    eax, eax
0x180013b85  js      loc_180013C0F
0x180013b8b  mov     rcx, [rsp+4C0h+var_470]
0x180013b90  mov     r8d, 400000h
0x180013b96  mov     rdx, [rbx+20h]
0x180013b9a  mov     rax, [rcx]
0x180013b9d  mov     rax, [rax+18h]
0x180013ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ba6  mov     r15d, eax
0x180013ba9  test    eax, eax
0x180013bab  js      short loc_180013BFE
0x180013bad  mov     rcx, [rbx+28h]
0x180013bb1  test    rcx, rcx
0x180013bb4  jnz     loc_180013C83
0x180013bba  mov     r14, [rsp+4C0h+var_470]
0x180013bbf  mov     [rbx+28h], r14
0x180013bc3  mov     rcx, r14
0x180013bc6  mov     rax, [r14]
0x180013bc9  mov     rax, [rax+8]
0x180013bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013bd2  mov     [rbx+30h], dil
0x180013bd6  jmp     loc_180013C9D
0x180013bdb  cmp     [rcx+30h], dil
0x180013bdf  mov     rcx, r14
0x180013be2  mov     rax, [r14]
0x180013be5  jz      loc_180013C94
0x180013beb  mov     rax, [rax+60h]
0x180013bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013bf4  jmp     loc_180013B55
0x180013bf9  mov     r15d, esi
0x180013bfc  jmp     short loc_180013C1F
0x180013bfe  mov     rcx, [rsp+4C0h+var_470]
0x180013c03  mov     rax, [rcx]
0x180013c06  mov     rax, [rax+10h]
0x180013c0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c0f  mov     r13, [rsp+498h]
0x180013c17  mov     r14, [rsp+4C0h+var_30]
0x180013c1f  mov     rbx, [rsp+4C0h+arg_10]
0x180013c27  test    r15d, r15d
0x180013c2a  jns     short loc_180013C4D
0x180013c2c  mov     eax, r15d
0x180013c2f  mov     rcx, [rbp+3C0h+var_40]
0x180013c36  xor     rcx, rsp; StackCookie
0x180013c39  call    __security_check_cookie
0x180013c3e  add     rsp, 4A0h
0x180013c45  pop     r15
0x180013c47  pop     r12
0x180013c49  pop     rdi
0x180013c4a  pop     rsi
0x180013c4b  pop     rbp
0x180013c4c  retn
0x180013c4d  cmp     word ptr [rdi], 0
0x180013c51  jz      loc_180013E11
0x180013c57  mov     rcx, rdi; psz
0x180013c5a  xor     esi, esi
0x180013c5c  call    cs:__imp_SysAllocString
0x180013c62  mov     [r12], rax
0x180013c66  test    rdi, rdi
0x180013c69  jz      short loc_180013C76
0x180013c6b  test    rax, rax
0x180013c6e  mov     ecx, 8007000Eh
0x180013c73  cmovz   esi, ecx
0x180013c76  mov     rcx, rdi; pv
0x180013c79  call    cs:__imp_CoTaskMemFree
0x180013c7f  mov     eax, esi
0x180013c81  jmp     short loc_180013C2F
0x180013c83  mov     rax, [rcx]
0x180013c86  mov     rax, [rax+10h]
0x180013c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c8f  jmp     loc_180013BBA
0x180013c94  mov     rax, [rax+8]
0x180013c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c9d  lea     r9, aPath; "Path"
0x180013ca4  mov     [rsp+4C0h+pszSource], rdi
0x180013ca9  lea     r8, aSMui; "%s.MUI"
0x180013cb0  mov     edx, 104h; unsigned __int64
0x180013cb5  lea     rcx, [rbp+3C0h+var_250]; unsigned __int16 *
0x180013cbc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013cc1  test    eax, eax
0x180013cc3  js      short loc_180013CFB
0x180013cc5  mov     rax, [r14]
0x180013cc8  lea     rcx, [rsp+4C0h+pszSource]
0x180013ccd  mov     [rsp+28h], rcx
0x180013cd2  lea     r8, [rbp+3C0h+var_250]
0x180013cd9  xor     r9d, r9d
0x180013cdc  mov     dword ptr [rsp+4C0h+ppv], 1
0x180013ce4  lea     rdx, aVisualstyles; "VisualStyles"
0x180013ceb  mov     rcx, r14
0x180013cee  mov     rax, [rax+30h]
0x180013cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cf7  test    eax, eax
0x180013cf9  jns     short loc_180013D38
0x180013cfb  mov     rax, [r14]
0x180013cfe  lea     rcx, [rsp+4C0h+pszSource]
0x180013d03  mov     [rsp+28h], rcx
0x180013d08  lea     r8, aPath; "Path"
0x180013d0f  xor     r9d, r9d
0x180013d12  mov     dword ptr [rsp+4C0h+ppv], 1
0x180013d1a  lea     rdx, aVisualstyles; "VisualStyles"
0x180013d21  mov     rcx, r14
0x180013d24  mov     rax, [rax+30h]
0x180013d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d2d  mov     r15d, eax
0x180013d30  test    eax, eax
0x180013d32  js      loc_180013DEF
0x180013d38  xor     edx, edx; Val
0x180013d3a  lea     rcx, [rsp+4C0h+pszOutBuf]; void *
0x180013d3f  mov     r8d, 208h; Size
0x180013d45  call    memset_0
0x180013d4a  mov     rcx, [rsp+4C0h+pszSource]; pszSource
0x180013d4f  lea     rdx, [rsp+4C0h+pszOutBuf]; pszOutBuf
0x180013d54  xor     r9d, r9d; ppvReserved
0x180013d57  mov     r8d, 104h; cchOutBuf
0x180013d5d  call    cs:__imp_SHLoadIndirectString
0x180013d63  mov     r15d, eax
0x180013d66  test    eax, eax
0x180013d68  js      short loc_180013DE4
0x180013d6a  lea     rcx, [rsp+4C0h+pszOutBuf]; unsigned __int16 *
0x180013d6f  call    ?ExpandResourceDir@@YAJPEAGK@Z; ExpandResourceDir(ushort *,ulong)
0x180013d74  mov     r15d, eax
0x180013d77  test    eax, eax
0x180013d79  js      short loc_180013DE4
0x180013d7b  mov     rcx, [rbx+20h]; unsigned __int16 *
0x180013d7f  lea     rdx, [rsp+4C0h+pszOutBuf]; unsigned __int16 *
0x180013d84  call    ?ExpandThemeTokens@@YAJPEBGPEAGH@Z; ExpandThemeTokens(ushort const *,ushort *,int)
0x180013d89  mov     r15d, eax
0x180013d8c  test    eax, eax
0x180013d8e  js      short loc_180013DE4
0x180013d90  lea     rcx, [rsp+4C0h+pszOutBuf]; pszPath
0x180013d95  call    cs:__imp_PathIsRelativeW
0x180013d9b  test    eax, eax
0x180013d9d  jnz     short loc_180013DCD
0x180013d9f  lea     r9, [rsp+4C0h+var_480]; unsigned int *
0x180013da4  mov     [rsp+4C0h+var_480], edi
0x180013da8  lea     rcx, [rsp+4C0h+pszOutBuf]; unsigned __int16 *
0x180013dad  call    ?SHMapUrlToZoneEx@@YAJPEBGPEAUIUnknown@@KPEAK@Z; SHMapUrlToZoneEx(ushort const *,IUnknown *,ulong,ulong *)
0x180013db2  cmp     [rsp+4C0h+pszOutBuf], di
0x180013db7  jz      short loc_180013DFA
0x180013db9  cmp     [rsp+4C0h+var_480], edi
0x180013dbd  jz      short loc_180013DFA
0x180013dbf  call    ?s_IsUncPathAllowedForThumbnailImage@CFileSource@@SAHXZ; CFileSource::s_IsUncPathAllowedForThumbnailImage(void)
0x180013dc4  test    eax, eax
0x180013dc6  jnz     short loc_180013DFA
0x180013dc8  mov     [rsp+4C0h+pszOutBuf], ax
0x180013dcd  lea     r9, [rsp+4C0h+var_468]
0x180013dd2  lea     r8, [rsp+4C0h+pszOutBuf]
0x180013dd7  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180013ddc  mov     rdi, [rsp+4C0h+var_468]
0x180013de1  mov     r15d, eax
0x180013de4  mov     rcx, [rsp+4C0h+pszSource]; pv
0x180013de9  call    cs:__imp_CoTaskMemFree
0x180013def  mov     rax, [r14]
0x180013df2  mov     rcx, r14
0x180013df5  jmp     loc_180013C06
0x180013dfa  lea     rcx, [rsp+4C0h+pszOutBuf]; unsigned __int16 *
0x180013dff  call    ?ConfirmFile@@YAHPEAGH@Z; ConfirmFile(ushort *,int)
0x180013e04  cmp     eax, 3
0x180013e07  jnz     short loc_180013DCD
0x180013e09  mov     r15d, 80070002h
0x180013e0f  jmp     short loc_180013DE4
0x180013e11  mov     r8d, 104h
0x180013e17  lea     rdx, [rbp+3C0h+var_250]
0x180013e1e  lea     rcx, aSystemrootReso_2; "%SystemRoot%\\resources\\themes\\Aero\\"...
0x180013e25  call    cs:__imp_SHExpandEnvironmentStringsW
0x180013e2b  test    eax, eax
0x180013e2d  jz      loc_180013C76
0x180013e33  mov     rdx, r12; unsigned __int16 **
0x180013e36  lea     rcx, [rbp+3C0h+var_250]; unsigned __int16 *
0x180013e3d  call    ?HrSysAllocString@@YAJPEBGPEAPEAG@Z; HrSysAllocString(ushort const *,ushort * *)
0x180013e42  mov     esi, eax
0x180013e44  jmp     loc_180013C76
```
