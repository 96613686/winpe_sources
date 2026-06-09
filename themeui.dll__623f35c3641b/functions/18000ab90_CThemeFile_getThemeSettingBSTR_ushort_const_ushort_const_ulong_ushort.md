# CThemeFile::_getThemeSettingBSTR(ushort const *,ushort const *,ulong,ushort * *)

- ea: `0x18000ab90`
- end: `0x18000af0a`
- name: `?_getThemeSettingBSTR@CThemeFile@@AEAAJPEBG0KPEAPEAG@Z`
- size: `890`
- prototype: `__int64 __fastcall(CThemeFile *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int16 **)`
- caller_count: `6`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800090e0`
- `0x1800097b0`
- `0x180051b10`
- `0x180051fc0`
- `0x180052ff0`
- `0x180053020`

## callees

- `0x1800089c0`
- `0x18000ab10`
- `0x18000ab90`
- `0x18000d490`
- `0x18000dd60`
- `0x18000e780`
- `0x180015660`
- `0x1800358c0`
- `0x18003633c`
- `0x180052974`
- `0x180060fac`
- `0x18006d010`

## import_xrefs

- `SHLWAPI!PathIsRelativeW` at `0x18000ae88`
- `SHLWAPI!PathIsRelativeW` at `0x18000ae88`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x18000ae18`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x18000ae18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ad08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000aeda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ad08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000aeda`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ac29`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ac29`
- `OLEAUT32!__imp_SysAllocString` at `0x18000acec`
- `OLEAUT32!__imp_SysAllocString` at `0x18000acec`

## pseudocode

```c
__int64 __fastcall CThemeFile::_getThemeSettingBSTR(
        CThemeFile *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        char a4,
        unsigned __int16 **a5)
{
  OLECHAR *v5; // rdi
  const unsigned __int16 *v6; // r15
  __int64 *v9; // rsi
  HRESULT v10; // r15d
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  unsigned int v14; // ebx
  unsigned __int16 *v15; // rax
  PCWSTR v17; // r12
  _WORD *v18; // r12
  struct IUnknown *v19; // rdx
  __int64 v20; // rcx
  WCHAR *v21; // rax
  int v22; // r13d
  unsigned int v23; // r8d
  HRESULT v24; // eax
  unsigned int v25[2]; // [rsp+48h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-B0h] BYREF
  PCWSTR pszSource; // [rsp+60h] [rbp-A8h]
  OLECHAR *v29; // [rsp+68h] [rbp-A0h] BYREF
  WCHAR pszOutBuf[264]; // [rsp+78h] [rbp-90h] BYREF
  unsigned __int16 v31[264]; // [rsp+288h] [rbp+180h] BYREF

  v5 = 0;
  v6 = a2;
  pszSource = a3;
  *(_QWORD *)v25 = a2;
  *a5 = 0;
  v29 = 0;
  if ( !*((_QWORD *)this + 6) )
  {
    v10 = -2147467259;
    goto LABEL_13;
  }
  v9 = (__int64 *)*((_QWORD *)this + 7);
  if ( v9 )
  {
    v12 = *v9;
    if ( !*((_BYTE *)this + 64) )
    {
      (*(void (__fastcall **)(__int64 *))(v12 + 8))(v9);
      goto LABEL_19;
    }
    (*(void (__fastcall **)(__int64 *))(v12 + 96))(v9);
  }
  ppv = 0;
  v10 = CoCreateInstance(&CLSID_PrivateProfile, 0, 1u, &GUID_b57046bc_32e5_428a_9887_19f712b907bf, &ppv);
  if ( v10 < 0 )
    goto LABEL_13;
  v10 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64))(*(_QWORD *)ppv + 24LL))(
          ppv,
          *((_QWORD *)this + 6),
          0x400000);
  if ( v10 >= 0 )
  {
    v11 = *((_QWORD *)this + 7);
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v9 = (__int64 *)ppv;
    *((_QWORD *)this + 7) = ppv;
    (*(void (__fastcall **)(__int64 *))(*v9 + 8))(v9);
    v6 = *(const unsigned __int16 **)v25;
    *((_BYTE *)this + 64) = 0;
LABEL_19:
    v17 = pszSource;
    pv = 0;
    if ( (int)StringCchPrintfW(v31, 0x104u, L"%s.MUI", pszSource) >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64 *, const unsigned __int16 *, unsigned __int16 *, _QWORD, int, LPVOID *))(*v9 + 48))(
              v9,
              v6,
              v31,
              0,
              1,
              &pv);
      if ( v10 >= 0 )
        goto LABEL_23;
      v6 = *(const unsigned __int16 **)v25;
    }
    v10 = (*(__int64 (__fastcall **)(__int64 *, const unsigned __int16 *, PCWSTR, _QWORD, int, LPVOID *))(*v9 + 48))(
            v9,
            v6,
            v17,
            0,
            1,
            &pv);
    if ( v10 < 0 )
    {
LABEL_41:
      v13 = *v9;
      goto LABEL_12;
    }
LABEL_23:
    v18 = pv;
    pszSource = (PCWSTR)pv;
    memset_0(pszOutBuf, 0, 0x208u);
    if ( (a4 & 1) != 0 )
    {
      v18 = 0;
      v10 = SHLoadIndirectString(pszSource, pszOutBuf, 0x104u, 0);
      if ( v10 >= 0 )
      {
        v10 = ExpandResourceDir(pszOutBuf, (unsigned int)v19);
        if ( v10 >= 0 )
        {
          v10 = ExpandThemeTokens(*((const unsigned __int16 **)this + 6), pszOutBuf);
          v21 = pszOutBuf;
          if ( v10 < 0 )
            v21 = 0;
          v18 = v21;
        }
      }
      v22 = a4 & 2;
    }
    else
    {
      v22 = a4 & 2;
      if ( v22 )
        v10 = StringCchCopyW(pszOutBuf, 0x104u, (const unsigned __int16 *)pv);
    }
    if ( v10 < 0 )
      goto LABEL_40;
    if ( v22 && !PathIsRelativeW(pszOutBuf) )
    {
      v25[0] = 0;
      SHMapUrlToZoneEx(pszOutBuf, v19, v23, v25);
      if ( pszOutBuf[0] && v25[0] && !CFileSource::s_IsUncPathAllowedForThumbnailImage() )
      {
        *v18 = 0;
      }
      else if ( (unsigned int)ConfirmFile(pszOutBuf) == 3 )
      {
        v10 = -2147024894;
        goto LABEL_40;
      }
    }
    v24 = _AllocString<CTCoAllocPolicy>(v20, v19, v18, &v29);
    v5 = v29;
    v10 = v24;
LABEL_40:
    CoTaskMemFree(pv);
    goto LABEL_41;
  }
  v13 = *(_QWORD *)ppv;
LABEL_12:
  (*(void (**)(void))(v13 + 16))();
LABEL_13:
  if ( v10 < 0 )
    return (unsigned int)v10;
  v14 = 0;
  v15 = SysAllocString(v5);
  *a5 = v15;
  if ( v5 )
  {
    if ( !v15 )
      v14 = -2147024882;
  }
  CoTaskMemFree(v5);
  return v14;
}

```

## disassembly

```asm
0x18000ab90  mov     r11, rsp
0x18000ab93  push    rbp
0x18000ab94  push    rbx
0x18000ab95  push    rdi
0x18000ab96  push    r14
0x18000ab98  push    r15
0x18000ab9a  lea     rbp, [r11-3D8h]
0x18000aba1  sub     rsp, 4B0h
0x18000aba8  mov     rax, cs:__security_cookie
0x18000abaf  xor     rax, rsp
0x18000abb2  mov     [rbp+3D0h+var_40], rax
0x18000abb9  mov     r14, [rbp+3D0h+arg_20]
0x18000abc0  xor     edi, edi
0x18000abc2  mov     [r11-38h], r13
0x18000abc6  mov     r15, rdx
0x18000abc9  mov     r13d, r9d
0x18000abcc  mov     [rsp+4D0h+pszSource], r8
0x18000abd1  mov     qword ptr [rsp+4D0h+var_490], rdx
0x18000abd6  mov     rbx, rcx
0x18000abd9  mov     qword ptr [r14], 0
0x18000abe0  mov     [rsp+4D0h+var_470], rdi
0x18000abe5  cmp     [rcx+30h], rdi
0x18000abe9  jz      loc_18000ACAD
0x18000abef  mov     [r11+20h], rsi
0x18000abf3  mov     rsi, [rcx+38h]
0x18000abf7  mov     [r11-30h], r12
0x18000abfb  test    rsi, rsi
0x18000abfe  jnz     loc_18000AC8F
0x18000ac04  lea     rax, [rsp+4D0h+var_480]
0x18000ac09  mov     [rsp+4D0h+var_480], rdi
0x18000ac0e  lea     r9, _GUID_b57046bc_32e5_428a_9887_19f712b907bf; riid
0x18000ac15  mov     [rsp+4D0h+ppv], rax; ppv
0x18000ac1a  xor     edx, edx; pUnkOuter
0x18000ac1c  lea     rcx, CLSID_PrivateProfile; rclsid
0x18000ac23  mov     r8d, 1; dwClsContext
0x18000ac29  call    cs:__imp_CoCreateInstance
0x18000ac2f  mov     r15d, eax
0x18000ac32  test    eax, eax
0x18000ac34  js      loc_18000ACC6
0x18000ac3a  mov     rcx, [rsp+4D0h+var_480]
0x18000ac3f  mov     r8d, 400000h
0x18000ac45  mov     rdx, [rbx+30h]
0x18000ac49  mov     rax, [rcx]
0x18000ac4c  mov     rax, [rax+18h]
0x18000ac50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac55  mov     r15d, eax
0x18000ac58  test    eax, eax
0x18000ac5a  js      short loc_18000ACB5
0x18000ac5c  mov     rcx, [rbx+38h]
0x18000ac60  test    rcx, rcx
0x18000ac63  jnz     loc_18000AD2E
0x18000ac69  mov     rsi, [rsp+4D0h+var_480]
0x18000ac6e  mov     [rbx+38h], rsi
0x18000ac72  mov     rcx, rsi
0x18000ac75  mov     rax, [rsi]
0x18000ac78  mov     rax, [rax+8]
0x18000ac7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac81  mov     r15, qword ptr [rsp+4D0h+var_490]
0x18000ac86  mov     [rbx+40h], dil
0x18000ac8a  jmp     loc_18000AD48
0x18000ac8f  cmp     [rcx+40h], dil
0x18000ac93  mov     rcx, rsi
0x18000ac96  mov     rax, [rsi]
0x18000ac99  jz      loc_18000AD3F
0x18000ac9f  mov     rax, [rax+60h]
0x18000aca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aca8  jmp     loc_18000AC04
0x18000acad  mov     r15d, 80004005h
0x18000acb3  jmp     short loc_18000ACD6
0x18000acb5  mov     rcx, [rsp+4D0h+var_480]
0x18000acba  mov     rax, [rcx]
0x18000acbd  mov     rax, [rax+10h]
0x18000acc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acc6  mov     rsi, [rsp+4D0h+arg_18]
0x18000acce  mov     r12, [rsp+4A8h]
0x18000acd6  mov     r13, [rsp+4D0h+var_30]
0x18000acde  test    r15d, r15d
0x18000ace1  js      loc_18000AF02
0x18000ace7  mov     rcx, rdi; psz
0x18000acea  xor     ebx, ebx
0x18000acec  call    cs:__imp_SysAllocString
0x18000acf2  mov     [r14], rax
0x18000acf5  test    rdi, rdi
0x18000acf8  jz      short loc_18000AD05
0x18000acfa  test    rax, rax
0x18000acfd  mov     ecx, 8007000Eh
0x18000ad02  cmovz   ebx, ecx
0x18000ad05  mov     rcx, rdi; pv
0x18000ad08  call    cs:__imp_CoTaskMemFree
0x18000ad0e  mov     eax, ebx
0x18000ad10  mov     rcx, [rbp+3D0h+var_40]
0x18000ad17  xor     rcx, rsp; StackCookie
0x18000ad1a  call    __security_check_cookie
0x18000ad1f  add     rsp, 4B0h
0x18000ad26  pop     r15
0x18000ad28  pop     r14
0x18000ad2a  pop     rdi
0x18000ad2b  pop     rbx
0x18000ad2c  pop     rbp
0x18000ad2d  retn
0x18000ad2e  mov     rax, [rcx]
0x18000ad31  mov     rax, [rax+10h]
0x18000ad35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad3a  jmp     loc_18000AC69
0x18000ad3f  mov     rax, [rax+8]
0x18000ad43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad48  mov     r12, [rsp+4D0h+pszSource]
0x18000ad4d  lea     r8, aSMui; "%s.MUI"
0x18000ad54  mov     r9, r12
0x18000ad57  mov     [rsp+4D0h+pv], rdi
0x18000ad5c  mov     edx, 104h; unsigned __int64
0x18000ad61  lea     rcx, [rbp+3D0h+var_250]; unsigned __int16 *
0x18000ad68  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ad6d  test    eax, eax
0x18000ad6f  js      short loc_18000ADAB
0x18000ad71  mov     rax, [rsi]
0x18000ad74  lea     rcx, [rsp+4D0h+pv]
0x18000ad79  mov     [rsp+28h], rcx
0x18000ad7e  lea     r8, [rbp+3D0h+var_250]
0x18000ad85  xor     r9d, r9d
0x18000ad88  mov     dword ptr [rsp+4D0h+ppv], 1
0x18000ad90  mov     rdx, r15
0x18000ad93  mov     rcx, rsi
0x18000ad96  mov     rax, [rax+30h]
0x18000ad9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad9f  mov     r15d, eax
0x18000ada2  test    eax, eax
0x18000ada4  jns     short loc_18000ADE0
0x18000ada6  mov     r15, qword ptr [rsp+4D0h+var_490]
0x18000adab  mov     rax, [rsi]
0x18000adae  lea     rcx, [rsp+4D0h+pv]
0x18000adb3  mov     [rsp+28h], rcx
0x18000adb8  xor     r9d, r9d
0x18000adbb  mov     r8, r12
0x18000adbe  mov     dword ptr [rsp+4D0h+ppv], 1
0x18000adc6  mov     rdx, r15
0x18000adc9  mov     rcx, rsi
0x18000adcc  mov     rax, [rax+30h]
0x18000add0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000add5  mov     r15d, eax
0x18000add8  test    eax, eax
0x18000adda  js      loc_18000AEE0
0x18000ade0  mov     r12, [rsp+4D0h+pv]
0x18000ade5  lea     rcx, [rsp+4D0h+pszOutBuf]; void *
0x18000adea  xor     edx, edx; Val
0x18000adec  mov     [rsp+4D0h+pszSource], r12
0x18000adf1  mov     r8d, 208h; Size
0x18000adf7  call    memset_0
0x18000adfc  test    r13b, 1
0x18000ae00  jz      short loc_18000AE5C
0x18000ae02  mov     rcx, [rsp+4D0h+pszSource]; pszSource
0x18000ae07  lea     rdx, [rsp+4D0h+pszOutBuf]; pszOutBuf
0x18000ae0c  xor     r9d, r9d; ppvReserved
0x18000ae0f  mov     r8d, 104h; cchOutBuf
0x18000ae15  xor     r12d, r12d
0x18000ae18  call    cs:__imp_SHLoadIndirectString
0x18000ae1e  mov     r15d, eax
0x18000ae21  test    eax, eax
0x18000ae23  js      short loc_18000AE56
0x18000ae25  lea     rcx, [rsp+4D0h+pszOutBuf]; unsigned __int16 *
0x18000ae2a  call    ?ExpandResourceDir@@YAJPEAGK@Z; ExpandResourceDir(ushort *,ulong)
0x18000ae2f  mov     r15d, eax
0x18000ae32  test    eax, eax
0x18000ae34  js      short loc_18000AE56
0x18000ae36  mov     rcx, [rbx+30h]; unsigned __int16 *
0x18000ae3a  lea     rdx, [rsp+4D0h+pszOutBuf]; unsigned __int16 *
0x18000ae3f  call    ?ExpandThemeTokens@@YAJPEBGPEAGH@Z; ExpandThemeTokens(ushort const *,ushort *,int)
0x18000ae44  mov     r15d, eax
0x18000ae47  lea     rax, [rsp+4D0h+pszOutBuf]
0x18000ae4c  test    r15d, r15d
0x18000ae4f  cmovs   rax, r12
0x18000ae53  mov     r12, rax
0x18000ae56  and     r13d, 2
0x18000ae5a  jmp     short loc_18000AE79
0x18000ae5c  and     r13d, 2
0x18000ae60  jz      short loc_18000AE79
0x18000ae62  mov     r8, [rsp+4D0h+pv]; unsigned __int16 *
0x18000ae67  lea     rcx, [rsp+4D0h+pszOutBuf]; unsigned __int16 *
0x18000ae6c  mov     edx, 104h; unsigned __int64
0x18000ae71  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ae76  mov     r15d, eax
0x18000ae79  test    r15d, r15d
0x18000ae7c  js      short loc_18000AED5
0x18000ae7e  test    r13d, r13d
0x18000ae81  jz      short loc_18000AEC0
0x18000ae83  lea     rcx, [rsp+4D0h+pszOutBuf]; pszPath
0x18000ae88  call    cs:__imp_PathIsRelativeW
0x18000ae8e  test    eax, eax
0x18000ae90  jnz     short loc_18000AEC0
0x18000ae92  lea     r9, [rsp+4D0h+var_490]; unsigned int *
0x18000ae97  mov     [rsp+4D0h+var_490], edi
0x18000ae9b  lea     rcx, [rsp+4D0h+pszOutBuf]; unsigned __int16 *
0x18000aea0  call    ?SHMapUrlToZoneEx@@YAJPEBGPEAUIUnknown@@KPEAK@Z; SHMapUrlToZoneEx(ushort const *,IUnknown *,ulong,ulong *)
0x18000aea5  cmp     [rsp+4D0h+pszOutBuf], di
0x18000aeaa  jz      short loc_18000AEEB
0x18000aeac  cmp     [rsp+4D0h+var_490], edi
0x18000aeb0  jz      short loc_18000AEEB
0x18000aeb2  call    ?s_IsUncPathAllowedForThumbnailImage@CFileSource@@SAHXZ; CFileSource::s_IsUncPathAllowedForThumbnailImage(void)
0x18000aeb7  test    eax, eax
0x18000aeb9  jnz     short loc_18000AEEB
0x18000aebb  mov     [r12], ax
0x18000aec0  lea     r9, [rsp+4D0h+var_470]
0x18000aec5  mov     r8, r12
0x18000aec8  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18000aecd  mov     rdi, [rsp+4D0h+var_470]
0x18000aed2  mov     r15d, eax
0x18000aed5  mov     rcx, [rsp+4D0h+pv]; pv
0x18000aeda  call    cs:__imp_CoTaskMemFree
0x18000aee0  mov     rax, [rsi]
0x18000aee3  mov     rcx, rsi
0x18000aee6  jmp     loc_18000ACBD
0x18000aeeb  lea     rcx, [rsp+4D0h+pszOutBuf]; unsigned __int16 *
0x18000aef0  call    ?ConfirmFile@@YAHPEAGH@Z; ConfirmFile(ushort *,int)
0x18000aef5  cmp     eax, 3
0x18000aef8  jnz     short loc_18000AEC0
0x18000aefa  mov     r15d, 80070002h
0x18000af00  jmp     short loc_18000AED5
0x18000af02  mov     eax, r15d
0x18000af05  jmp     loc_18000AD10
```
