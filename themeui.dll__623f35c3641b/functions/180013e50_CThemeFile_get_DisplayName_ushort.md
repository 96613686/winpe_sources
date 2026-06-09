# CThemeFile::get_DisplayName(ushort * *)

- ea: `0x180013e50`
- end: `0x180014137`
- name: `?get_DisplayName@CThemeFile@@UEAAJPEAPEAG@Z`
- size: `743`
- prototype: `int(CThemeFile *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800089c0`
- `0x18000d490`
- `0x18000dd60`
- `0x180013e50`
- `0x180015190`
- `0x180015660`
- `0x1800358c0`
- `0x18003633c`
- `0x18006d010`

## import_xrefs

- `SHCORE!SHUnicodeToUnicode` at `0x18001410d`
- `SHCORE!SHUnicodeToUnicode` at `0x18001410d`
- `SHLWAPI!PathFindFileNameW` at `0x1800140f4`
- `SHLWAPI!PathFindFileNameW` at `0x1800140f4`
- `SHLWAPI!PathRemoveExtensionW` at `0x180014118`
- `SHLWAPI!PathRemoveExtensionW` at `0x180014118`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x18001408f`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x18001408f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013f94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800140da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013f94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800140da`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013ec1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013ec1`
- `OLEAUT32!__imp_SysAllocString` at `0x180013f78`
- `OLEAUT32!__imp_SysAllocString` at `0x180013f78`

## pseudocode

```c
__int64 __fastcall CThemeFile::get_DisplayName(CThemeFile *this, unsigned __int16 **a2)
{
  OLECHAR *v2; // rdi
  __int64 *v5; // r14
  HRESULT v6; // ebp
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rax
  unsigned int v10; // ebx
  unsigned __int16 *v11; // rax
  unsigned int v13; // edx
  __int64 v14; // rdx
  __int64 v15; // rcx
  HRESULT v16; // eax
  const WCHAR *v17; // rcx
  const WCHAR *FileNameW; // rax
  PCWSTR pszSource; // [rsp+40h] [rbp-478h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-470h] BYREF
  OLECHAR *v21; // [rsp+50h] [rbp-468h] BYREF
  WCHAR pszOutBuf[264]; // [rsp+60h] [rbp-458h] BYREF
  unsigned __int16 v23[264]; // [rsp+270h] [rbp-248h] BYREF

  v2 = 0;
  v21 = 0;
  if ( !*((_QWORD *)this + 4) )
  {
    v6 = -2147467259;
    goto LABEL_13;
  }
  v5 = (__int64 *)*((_QWORD *)this + 5);
  if ( v5 )
  {
    v8 = *v5;
    if ( !*((_BYTE *)this + 48) )
    {
      (*(void (__fastcall **)(__int64 *))(v8 + 8))(v5);
LABEL_20:
      pszSource = 0;
      if ( (int)StringCchPrintfW(v23, 0x104u, L"%s.MUI", L"DisplayName") >= 0
        && (*(int (__fastcall **)(__int64 *, const unsigned __int16 *, unsigned __int16 *, _QWORD, int, PCWSTR *))(*v5 + 48))(
             v5,
             L"Theme",
             v23,
             0,
             1,
             &pszSource) >= 0
        || (v6 = (*(__int64 (__fastcall **)(__int64 *, const unsigned __int16 *, const WCHAR *, _QWORD, int, PCWSTR *))(*v5 + 48))(
                   v5,
                   L"Theme",
                   L"DisplayName",
                   0,
                   1,
                   &pszSource),
            v6 >= 0) )
      {
        memset_0(pszOutBuf, 0, 0x208u);
        v6 = SHLoadIndirectString(pszSource, pszOutBuf, 0x104u, 0);
        if ( v6 >= 0 )
        {
          v6 = ExpandResourceDir(pszOutBuf, v13);
          if ( v6 >= 0 )
          {
            v6 = ExpandThemeTokens(*((const unsigned __int16 **)this + 4), pszOutBuf);
            if ( v6 >= 0 )
            {
              v16 = _AllocString<CTCoAllocPolicy>(v15, v14, pszOutBuf, &v21);
              v2 = v21;
              v6 = v16;
            }
          }
        }
        CoTaskMemFree((LPVOID)pszSource);
      }
      v9 = *v5;
      goto LABEL_12;
    }
    (*(void (__fastcall **)(__int64 *))(v8 + 96))(v5);
  }
  ppv = 0;
  v6 = CoCreateInstance(&CLSID_PrivateProfile, 0, 1u, &GUID_b57046bc_32e5_428a_9887_19f712b907bf, &ppv);
  if ( v6 < 0 )
    goto LABEL_13;
  v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64))(*(_QWORD *)ppv + 24LL))(
         ppv,
         *((_QWORD *)this + 4),
         0x400000);
  if ( v6 >= 0 )
  {
    v7 = *((_QWORD *)this + 5);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    v5 = (__int64 *)ppv;
    *((_QWORD *)this + 5) = ppv;
    (*(void (__fastcall **)(__int64 *))(*v5 + 8))(v5);
    *((_BYTE *)this + 48) = 0;
    goto LABEL_20;
  }
  v9 = *(_QWORD *)ppv;
LABEL_12:
  (*(void (**)(void))(v9 + 16))();
LABEL_13:
  if ( v6 < 0 )
  {
    v17 = (const WCHAR *)*((_QWORD *)this + 4);
    if ( v17 && (FileNameW = PathFindFileNameW(v17)) != 0 )
    {
      SHUnicodeToUnicode(FileNameW, pszOutBuf, 260);
      PathRemoveExtensionW(pszOutBuf);
      return HrSysAllocString(pszOutBuf, a2);
    }
    else
    {
      return (unsigned int)v6;
    }
  }
  else
  {
    v10 = 0;
    if ( a2 )
    {
      v11 = SysAllocString(v2);
      *a2 = v11;
      if ( v2 )
      {
        if ( !v11 )
          v10 = -2147024882;
      }
    }
    CoTaskMemFree(v2);
    return v10;
  }
}

```

## disassembly

```asm
0x180013e50  mov     r11, rsp
0x180013e53  push    rbx
0x180013e54  push    rbp
0x180013e55  push    rsi
0x180013e56  push    rdi
0x180013e57  sub     rsp, 498h
0x180013e5e  mov     rax, cs:__security_cookie
0x180013e65  xor     rax, rsp
0x180013e68  mov     [rsp+4B8h+var_38], rax
0x180013e70  xor     edi, edi
0x180013e72  mov     rsi, rdx
0x180013e75  mov     rbx, rcx
0x180013e78  mov     [rsp+4B8h+var_468], rdi
0x180013e7d  cmp     [rcx+20h], rdi
0x180013e81  jz      loc_180013F3E
0x180013e87  mov     [r11+18h], r14
0x180013e8b  mov     r14, [rcx+28h]
0x180013e8f  mov     [r11-28h], r15
0x180013e93  test    r14, r14
0x180013e96  jnz     loc_180013F20
0x180013e9c  lea     rax, [rsp+4B8h+var_470]
0x180013ea1  mov     [rsp+4B8h+var_470], rdi
0x180013ea6  lea     r9, _GUID_b57046bc_32e5_428a_9887_19f712b907bf; riid
0x180013ead  mov     [rsp+4B8h+ppv], rax; ppv
0x180013eb2  xor     edx, edx; pUnkOuter
0x180013eb4  lea     rcx, CLSID_PrivateProfile; rclsid
0x180013ebb  mov     r8d, 1; dwClsContext
0x180013ec1  call    cs:__imp_CoCreateInstance
0x180013ec7  mov     ebp, eax
0x180013ec9  test    eax, eax
0x180013ecb  js      loc_180013F56
0x180013ed1  mov     rcx, [rsp+4B8h+var_470]
0x180013ed6  mov     r8d, 400000h
0x180013edc  mov     rdx, [rbx+20h]
0x180013ee0  mov     rax, [rcx]
0x180013ee3  mov     rax, [rax+18h]
0x180013ee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013eec  mov     ebp, eax
0x180013eee  test    eax, eax
0x180013ef0  js      short loc_180013F45
0x180013ef2  mov     rcx, [rbx+28h]
0x180013ef6  test    rcx, rcx
0x180013ef9  jnz     loc_180013FB8
0x180013eff  mov     r14, [rsp+4B8h+var_470]
0x180013f04  mov     [rbx+28h], r14
0x180013f08  mov     rcx, r14
0x180013f0b  mov     rax, [r14]
0x180013f0e  mov     rax, [rax+8]
0x180013f12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f17  mov     [rbx+30h], dil
0x180013f1b  jmp     loc_180013FD2
0x180013f20  cmp     [rcx+30h], dil
0x180013f24  mov     rcx, r14
0x180013f27  mov     rax, [r14]
0x180013f2a  jz      loc_180013FC9
0x180013f30  mov     rax, [rax+60h]
0x180013f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f39  jmp     loc_180013E9C
0x180013f3e  mov     ebp, 80004005h
0x180013f43  jmp     short loc_180013F66
0x180013f45  mov     rcx, [rsp+4B8h+var_470]
0x180013f4a  mov     rax, [rcx]
0x180013f4d  mov     rax, [rax+10h]
0x180013f51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f56  mov     r14, [rsp+4B8h+arg_10]
0x180013f5e  mov     r15, [rsp+4B8h+var_28]
0x180013f66  test    ebp, ebp
0x180013f68  js      loc_1800140EB
0x180013f6e  xor     ebx, ebx
0x180013f70  test    rsi, rsi
0x180013f73  jz      short loc_180013F91
0x180013f75  mov     rcx, rdi; psz
0x180013f78  call    cs:__imp_SysAllocString
0x180013f7e  mov     [rsi], rax
0x180013f81  test    rdi, rdi
0x180013f84  jz      short loc_180013F91
0x180013f86  test    rax, rax
0x180013f89  mov     ecx, 8007000Eh
0x180013f8e  cmovz   ebx, ecx
0x180013f91  mov     rcx, rdi; pv
0x180013f94  call    cs:__imp_CoTaskMemFree
0x180013f9a  mov     eax, ebx
0x180013f9c  mov     rcx, [rsp+4B8h+var_38]
0x180013fa4  xor     rcx, rsp; StackCookie
0x180013fa7  call    __security_check_cookie
0x180013fac  add     rsp, 498h
0x180013fb3  pop     rdi
0x180013fb4  pop     rsi
0x180013fb5  pop     rbp
0x180013fb6  pop     rbx
0x180013fb7  retn
0x180013fb8  mov     rax, [rcx]
0x180013fbb  mov     rax, [rax+10h]
0x180013fbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fc4  jmp     loc_180013EFF
0x180013fc9  mov     rax, [rax+8]
0x180013fcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fd2  lea     r9, pszPropertyName; "DisplayName"
0x180013fd9  mov     [rsp+4B8h+pszSource], rdi
0x180013fde  lea     r8, aSMui; "%s.MUI"
0x180013fe5  mov     edx, 104h; unsigned __int64
0x180013fea  lea     rcx, [rsp+4B8h+var_248]; unsigned __int16 *
0x180013ff2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013ff7  test    eax, eax
0x180013ff9  js      short loc_180014032
0x180013ffb  mov     rax, [r14]
0x180013ffe  lea     rcx, [rsp+4B8h+pszSource]
0x180014003  mov     [rsp+4B8h+var_490], rcx
0x180014008  lea     r8, [rsp+4B8h+var_248]
0x180014010  xor     r9d, r9d
0x180014013  mov     dword ptr [rsp+4B8h+ppv], 1
0x18001401b  lea     rdx, aTheme_1; "Theme"
0x180014022  mov     rcx, r14
0x180014025  mov     rax, [rax+30h]
0x180014029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001402e  test    eax, eax
0x180014030  jns     short loc_18001406A
0x180014032  mov     rax, [r14]
0x180014035  lea     rcx, [rsp+4B8h+pszSource]
0x18001403a  mov     [rsp+4B8h+var_490], rcx
0x18001403f  lea     r8, pszPropertyName; "DisplayName"
0x180014046  xor     r9d, r9d
0x180014049  mov     dword ptr [rsp+4B8h+ppv], 1
0x180014051  lea     rdx, aTheme_1; "Theme"
0x180014058  mov     rcx, r14
0x18001405b  mov     rax, [rax+30h]
0x18001405f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014064  mov     ebp, eax
0x180014066  test    eax, eax
0x180014068  js      short loc_1800140E0
0x18001406a  xor     edx, edx; Val
0x18001406c  lea     rcx, [rsp+4B8h+pszOutBuf]; void *
0x180014071  mov     r8d, 208h; Size
0x180014077  call    memset_0
0x18001407c  mov     rcx, [rsp+4B8h+pszSource]; pszSource
0x180014081  lea     rdx, [rsp+4B8h+pszOutBuf]; pszOutBuf
0x180014086  xor     r9d, r9d; ppvReserved
0x180014089  mov     r8d, 104h; cchOutBuf
0x18001408f  call    cs:__imp_SHLoadIndirectString
0x180014095  mov     ebp, eax
0x180014097  test    eax, eax
0x180014099  js      short loc_1800140D5
0x18001409b  lea     rcx, [rsp+4B8h+pszOutBuf]; unsigned __int16 *
0x1800140a0  call    ?ExpandResourceDir@@YAJPEAGK@Z; ExpandResourceDir(ushort *,ulong)
0x1800140a5  mov     ebp, eax
0x1800140a7  test    eax, eax
0x1800140a9  js      short loc_1800140D5
0x1800140ab  mov     rcx, [rbx+20h]; unsigned __int16 *
0x1800140af  lea     rdx, [rsp+4B8h+pszOutBuf]; unsigned __int16 *
0x1800140b4  call    ?ExpandThemeTokens@@YAJPEBGPEAGH@Z; ExpandThemeTokens(ushort const *,ushort *,int)
0x1800140b9  mov     ebp, eax
0x1800140bb  test    eax, eax
0x1800140bd  js      short loc_1800140D5
0x1800140bf  lea     r9, [rsp+4B8h+var_468]
0x1800140c4  lea     r8, [rsp+4B8h+pszOutBuf]
0x1800140c9  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800140ce  mov     rdi, [rsp+4B8h+var_468]
0x1800140d3  mov     ebp, eax
0x1800140d5  mov     rcx, [rsp+4B8h+pszSource]; pv
0x1800140da  call    cs:__imp_CoTaskMemFree
0x1800140e0  mov     rax, [r14]
0x1800140e3  mov     rcx, r14
0x1800140e6  jmp     loc_180013F4D
0x1800140eb  mov     rcx, [rbx+20h]; pszPath
0x1800140ef  test    rcx, rcx
0x1800140f2  jz      short loc_180014130
0x1800140f4  call    cs:__imp_PathFindFileNameW
0x1800140fa  test    rax, rax
0x1800140fd  jz      short loc_180014130
0x1800140ff  mov     r8d, 104h; cwchBuf
0x180014105  lea     rdx, [rsp+4B8h+pszOutBuf]; pwzDst
0x18001410a  mov     rcx, rax; pwzSrc
0x18001410d  call    cs:__imp_SHUnicodeToUnicode
0x180014113  lea     rcx, [rsp+4B8h+pszOutBuf]; pszPath
0x180014118  call    cs:__imp_PathRemoveExtensionW
0x18001411e  mov     rdx, rsi; unsigned __int16 **
0x180014121  lea     rcx, [rsp+4B8h+pszOutBuf]; unsigned __int16 *
0x180014126  call    ?HrSysAllocString@@YAJPEBGPEAPEAG@Z; HrSysAllocString(ushort const *,ushort * *)
0x18001412b  jmp     loc_180013F9C
0x180014130  mov     eax, ebp
0x180014132  jmp     loc_180013F9C
```
