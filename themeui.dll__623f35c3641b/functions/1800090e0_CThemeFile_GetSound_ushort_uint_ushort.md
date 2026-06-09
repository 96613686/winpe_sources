# CThemeFile::GetSound(ushort *,uint,ushort * *)

- ea: `0x1800090e0`
- end: `0x180009603`
- name: `?GetSound@CThemeFile@@UEAAJPEAGIPEAPEAG@Z`
- size: `1315`
- prototype: `__int64 __fastcall(CThemeFile *__hidden this, unsigned __int16 *, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800089c0`
- `0x1800090e0`
- `0x18000a9a0`
- `0x18000ab10`
- `0x18000ab90`
- `0x18000d490`
- `0x18000dd60`
- `0x18000e780`
- `0x180015660`
- `0x180030f64`
- `0x1800358c0`
- `0x18003633c`
- `0x180052974`
- `0x180060fac`
- `0x18006d010`

## import_xrefs

- `SHLWAPI!PathIsRelativeW` at `0x1800094fe`
- `SHLWAPI!PathIsRelativeW` at `0x1800094fe`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x1800094c6`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x1800094c6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800095ba`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800095ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000937c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009554`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000937c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009554`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800091c3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000930c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800091c3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000930c`
- `OLEAUT32!__imp_SysAllocString` at `0x180009255`
- `OLEAUT32!__imp_SysAllocString` at `0x18000935f`
- `OLEAUT32!__imp_SysAllocString` at `0x180009255`
- `OLEAUT32!__imp_SysAllocString` at `0x18000935f`
- `OLEAUT32!__imp_SysFreeString` at `0x180009243`
- `OLEAUT32!__imp_SysFreeString` at `0x1800093ec`
- `OLEAUT32!__imp_SysFreeString` at `0x180009243`
- `OLEAUT32!__imp_SysFreeString` at `0x1800093ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CThemeFile::GetSound(CThemeFile *this, unsigned __int16 *a2, DWORD a3, unsigned __int16 **a4)
{
  unsigned __int16 *v5; // r13
  int v7; // ebx
  unsigned int v8; // edi
  int ThemeSettingBSTR; // r14d
  bool v10; // sf
  unsigned __int16 *v11; // rbx
  OLECHAR *v12; // r13
  int CachedProfile; // r14d
  unsigned __int16 *v14; // rax
  int ValueW; // edx
  bool v17; // sf
  OLECHAR *v18; // rax
  int v19; // eax
  unsigned __int16 *v20; // r14
  HRESULT v21; // r14d
  unsigned int v22; // edx
  struct IUnknown *v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  unsigned int v26; // edx
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD uID; // [rsp+44h] [rbp-BCh] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-B8h] BYREF
  PCWSTR pszSource; // [rsp+50h] [rbp-B0h] BYREF
  struct ICachedPrivateProfile *v31; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v32; // [rsp+60h] [rbp-A0h]
  OLECHAR *v33; // [rsp+68h] [rbp-98h] BYREF
  WCHAR pszOutBuf[264]; // [rsp+70h] [rbp-90h] BYREF
  OLECHAR psz[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR SubKey[264]; // [rsp+490h] [rbp+390h] BYREF

  uID = a3;
  v5 = a2;
  v32 = a2;
  *a4 = 0;
  v7 = 0;
  if ( !*((_WORD *)this + 402) )
  {
    bstrString = 0;
    v7 = (*(__int64 (__fastcall **)(CThemeFile *, BSTR *))(*(_QWORD *)this + 320LL))(this, &bstrString);
    SysFreeString(bstrString);
    if ( v7 < 0 )
      return (unsigned int)v7;
  }
  if ( *((_BYTE *)this + 1324) )
    return (unsigned int)v7;
  v8 = -2147024882;
  if ( !*((_BYTE *)this + 1846) )
  {
    v11 = 0;
    bstrString = 0;
    v12 = 0;
    v33 = 0;
    v31 = 0;
    CachedProfile = CThemeFile::_GetCachedProfile((CThemeFile *)((char *)this - 16), 1, &v31);
    if ( CachedProfile < 0 )
      goto LABEL_9;
    pszSource = 0;
    v19 = StringCchPrintfW(SubKey, 0x104u, L"%s.MUI", L"DefaultValue");
    v20 = v32;
    if ( v19 < 0
      || (*(int (__fastcall **)(struct ICachedPrivateProfile *, unsigned __int16 *, WCHAR *, _QWORD, int, PCWSTR *))(*(_QWORD *)v31 + 48LL))(
           v31,
           v32,
           SubKey,
           0,
           1,
           &pszSource) < 0 )
    {
      v21 = (*(__int64 (__fastcall **)(struct ICachedPrivateProfile *, unsigned __int16 *, const OLECHAR *, _QWORD, int, PCWSTR *))(*(_QWORD *)v31 + 48LL))(
              v31,
              v20,
              L"DefaultValue",
              0,
              1,
              &pszSource);
      if ( v21 < 0 )
      {
LABEL_27:
        (*(void (__fastcall **)(struct ICachedPrivateProfile *))(*(_QWORD *)v31 + 16LL))(v31);
        if ( v21 < 0 )
          goto LABEL_51;
        CachedProfile = 0;
        v18 = SysAllocString(v12);
        v11 = v18;
        bstrString = v18;
        if ( v12 && !v18 )
          CachedProfile = -2147024882;
        CoTaskMemFree(v12);
LABEL_9:
        if ( CachedProfile >= 0 )
        {
          v5 = v32;
          goto LABEL_11;
        }
LABEL_51:
        v5 = v32;
        ThemeSettingBSTR = StringCchPrintfW(SubKey, 0x104u, L"%s\\.Current", v32);
        if ( ThemeSettingBSTR < 0
          || (ThemeSettingBSTR = CThemeFile::_getThemeSettingBSTR(
                                   (CThemeFile *)((char *)this - 16),
                                   SubKey,
                                   L"DefaultValue",
                                   3,
                                   &bstrString),
              v11 = bstrString,
              ThemeSettingBSTR < 0) )
        {
          psz[0] = 0;
          goto LABEL_12;
        }
LABEL_11:
        ThemeSettingBSTR = StringCchCopyW(psz, 0x104u, v11);
LABEL_12:
        SysFreeString(v11);
        goto LABEL_13;
      }
    }
    memset_0(pszOutBuf, 0, 0x208u);
    v21 = SHLoadIndirectString(pszSource, pszOutBuf, 0x104u, 0);
    if ( v21 >= 0 )
    {
      v21 = ExpandResourceDir(pszOutBuf, v22);
      if ( v21 >= 0 )
      {
        v21 = ExpandThemeTokens(*((const unsigned __int16 **)this + 4), pszOutBuf);
        if ( v21 >= 0 )
        {
          if ( !PathIsRelativeW(pszOutBuf) )
          {
            pcbData = 0;
            SHMapUrlToZoneEx(pszOutBuf, v23, v25, &pcbData);
            if ( pszOutBuf[0] && pcbData && !CFileSource::s_IsUncPathAllowedForThumbnailImage() )
            {
              pszOutBuf[0] = 0;
            }
            else if ( (unsigned int)ConfirmFile(pszOutBuf) == 3 )
            {
              v21 = -2147024894;
              goto LABEL_48;
            }
          }
          v21 = _AllocString<CTCoAllocPolicy>(v24, v23, pszOutBuf, &v33);
          v12 = v33;
        }
      }
    }
LABEL_48:
    CoTaskMemFree((LPVOID)pszSource);
    goto LABEL_27;
  }
  ThemeSettingBSTR = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", v5, (char *)this + 1326);
  if ( ThemeSettingBSTR >= 0 )
  {
    pcbData = 520;
    ThemeSettingBSTR = RegGetValueW(HKEY_CURRENT_USER, SubKey, 0, 2u, 0, psz, &pcbData);
    if ( ThemeSettingBSTR )
    {
      psz[0] = 0;
      v10 = ThemeSettingBSTR < 0;
      if ( ThemeSettingBSTR <= 0 )
        goto LABEL_14;
      ThemeSettingBSTR = (unsigned __int16)ThemeSettingBSTR | 0x80070000;
    }
  }
LABEL_13:
  v10 = ThemeSettingBSTR < 0;
LABEL_14:
  if ( v10 )
  {
    if ( !uID )
      return 0;
    if ( uID == -1 )
    {
      ValueW = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", v5, L".Default");
      if ( ValueW >= 0 )
      {
        uID = 520;
        ValueW = RegGetValueW(HKEY_CURRENT_USER, SubKey, 0, 2u, 0, psz, &uID);
        if ( ValueW )
        {
          psz[0] = 0;
          v17 = ValueW < 0;
          if ( ValueW <= 0 )
          {
LABEL_23:
            if ( !v17 )
              goto LABEL_15;
            return 0;
          }
          ValueW = (unsigned __int16)ValueW | 0x80070000;
        }
      }
    }
    else
    {
      if ( !LoadStringW(g_hinst, uID, psz, 260) && (int)ResultFromKnownLastError() < 0
        || (int)ExpandResourceDir(psz, v26) < 0 )
      {
        return 0;
      }
      ValueW = ExpandThemeTokens(*((const unsigned __int16 **)this + 4), psz);
    }
    v17 = ValueW < 0;
    goto LABEL_23;
  }
LABEL_15:
  v14 = SysAllocString(psz);
  *a4 = v14;
  if ( v14 )
    return 0;
  return v8;
}

```

## disassembly

```asm
0x1800090e0  push    rbp
0x1800090e2  push    rbx
0x1800090e3  push    rsi
0x1800090e4  push    rdi
0x1800090e5  push    r12
0x1800090e7  push    r13
0x1800090e9  push    r14
0x1800090eb  push    r15
0x1800090ed  lea     rbp, [rsp-5B8h]
0x1800090f5  sub     rsp, 6B8h
0x1800090fc  mov     rax, cs:__security_cookie
0x180009103  xor     rax, rsp
0x180009106  mov     [rbp+5F0h+var_50], rax
0x18000910d  mov     r12, r9
0x180009110  mov     [rsp+6F0h+uID], r8d
0x180009115  mov     r13, rdx
0x180009118  mov     [rsp+6F0h+var_690], rdx
0x18000911d  mov     rsi, rcx
0x180009120  xor     eax, eax
0x180009122  mov     [r9], rax
0x180009125  mov     ebx, eax
0x180009127  cmp     [rcx+324h], ax
0x18000912e  jz      loc_1800093CC
0x180009134  cmp     byte ptr [rsi+52Ch], 0
0x18000913b  jnz     loc_1800095FC
0x180009141  mov     edi, 8007000Eh
0x180009146  cmp     byte ptr [rsi+736h], 0
0x18000914d  jz      loc_1800091EB
0x180009153  lea     rax, [rsi+52Eh]
0x18000915a  mov     [rsp+6F0h+pdwType], rax
0x18000915f  mov     r9, r13
0x180009162  lea     r8, aSS; "%s\\%s"
0x180009169  mov     edx, 104h; unsigned __int64
0x18000916e  lea     rcx, [rbp+5F0h+SubKey]; unsigned __int16 *
0x180009175  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000917a  mov     r14d, eax
0x18000917d  test    eax, eax
0x18000917f  js      loc_180009249
0x180009185  mov     [rsp+6F0h+var_6B0], 208h
0x18000918d  lea     rax, [rsp+6F0h+var_6B0]
0x180009192  mov     [rsp+6F0h+pcbData], rax; pcbData
0x180009197  lea     rax, [rbp+5F0h+psz]
0x18000919e  mov     [rsp+6F0h+pvData], rax; pvData
0x1800091a3  mov     [rsp+6F0h+pdwType], 0; pdwType
0x1800091ac  mov     r9d, 2; dwFlags
0x1800091b2  xor     r8d, r8d; lpValue
0x1800091b5  lea     rdx, [rbp+5F0h+SubKey]; lpSubKey
0x1800091bc  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1800091c3  call    cs:__imp_RegGetValueW
0x1800091c9  mov     r14d, eax
0x1800091cc  test    eax, eax
0x1800091ce  jz      short loc_180009249
0x1800091d0  xor     eax, eax
0x1800091d2  mov     [rbp+5F0h+psz], ax
0x1800091d9  test    r14d, r14d
0x1800091dc  jle     short loc_18000924C
0x1800091de  movzx   r14d, r14w
0x1800091e2  or      r14d, 80070000h
0x1800091e9  jmp     short loc_180009249
0x1800091eb  mov     rbx, rax
0x1800091ee  mov     [rsp+6F0h+bstrString], rax
0x1800091f3  mov     r13, rax
0x1800091f6  mov     [rsp+6F0h+var_688], rax
0x1800091fb  mov     [rsp+6F0h+var_698], rax
0x180009200  lea     r8, [rsp+6F0h+var_698]; struct ICachedPrivateProfile **
0x180009205  mov     dl, 1; bool
0x180009207  lea     rcx, [rsi-10h]; this
0x18000920b  call    ?_GetCachedProfile@CThemeFile@@AEAAJ_NPEAPEAUICachedPrivateProfile@@@Z; CThemeFile::_GetCachedProfile(bool,ICachedPrivateProfile * *)
0x180009210  mov     r14d, eax
0x180009213  test    eax, eax
0x180009215  jns     loc_180009401
0x18000921b  test    r14d, r14d
0x18000921e  js      loc_180009576
0x180009224  mov     r13, [rsp+6F0h+var_690]
0x180009229  mov     r8, rbx; unsigned __int16 *
0x18000922c  mov     edx, 104h; unsigned __int64
0x180009231  lea     rcx, [rbp+5F0h+psz]; unsigned __int16 *
0x180009238  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000923d  mov     r14d, eax
0x180009240  mov     rcx, rbx; bstrString
0x180009243  call    cs:__imp_SysFreeString
0x180009249  test    r14d, r14d
0x18000924c  js      short loc_18000928C
0x18000924e  lea     rcx, [rbp+5F0h+psz]; psz
0x180009255  call    cs:__imp_SysAllocString
0x18000925b  mov     [r12], rax
0x18000925f  xor     ecx, ecx
0x180009261  test    rax, rax
0x180009264  cmovnz  edi, ecx
0x180009267  mov     eax, edi
0x180009269  mov     rcx, [rbp+5F0h+var_50]
0x180009270  xor     rcx, rsp; StackCookie
0x180009273  call    __security_check_cookie
0x180009278  add     rsp, 6B8h
0x18000927f  pop     r15
0x180009281  pop     r14
0x180009283  pop     r13
0x180009285  pop     r12
0x180009287  pop     rdi
0x180009288  pop     rsi
0x180009289  pop     rbx
0x18000928a  pop     rbp
0x18000928b  retn
0x18000928c  mov     edx, [rsp+6F0h+uID]; uID
0x180009290  test    edx, edx
0x180009292  jz      loc_180009320
0x180009298  cmp     edx, 0FFFFFFFFh
0x18000929b  jnz     loc_1800095A6
0x1800092a1  lea     rax, aDefault; ".Default"
0x1800092a8  mov     [rsp+6F0h+pdwType], rax
0x1800092ad  mov     r9, r13
0x1800092b0  lea     r8, aSS; "%s\\%s"
0x1800092b7  mov     edx, 104h; unsigned __int64
0x1800092bc  lea     rcx, [rbp+5F0h+SubKey]; unsigned __int16 *
0x1800092c3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800092c8  mov     edx, eax
0x1800092ca  test    eax, eax
0x1800092cc  js      short loc_180009318
0x1800092ce  mov     [rsp+6F0h+uID], 208h
0x1800092d6  lea     rax, [rsp+6F0h+uID]
0x1800092db  mov     [rsp+6F0h+pcbData], rax; pcbData
0x1800092e0  lea     rax, [rbp+5F0h+psz]
0x1800092e7  mov     [rsp+6F0h+pvData], rax; pvData
0x1800092ec  mov     [rsp+6F0h+pdwType], 0; pdwType
0x1800092f5  mov     r9d, 2; dwFlags
0x1800092fb  xor     r8d, r8d; lpValue
0x1800092fe  lea     rdx, [rbp+5F0h+SubKey]; lpSubKey
0x180009305  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18000930c  call    cs:__imp_RegGetValueW
0x180009312  mov     edx, eax
0x180009314  test    eax, eax
0x180009316  jnz     short loc_180009327
0x180009318  test    edx, edx
0x18000931a  jns     loc_18000924E
0x180009320  xor     eax, eax
0x180009322  jmp     loc_180009269
0x180009327  xor     eax, eax
0x180009329  mov     [rbp+5F0h+psz], ax
0x180009330  test    edx, edx
0x180009332  jle     short loc_18000931A
0x180009334  movzx   edx, dx
0x180009337  or      edx, 80070000h
0x18000933d  jmp     short loc_180009318
0x18000933f  mov     rcx, [rsp+6F0h+var_698]
0x180009344  mov     rax, [rcx]
0x180009347  mov     rax, [rax+10h]
0x18000934b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009350  test    r14d, r14d
0x180009353  js      loc_180009576
0x180009359  xor     r14d, r14d
0x18000935c  mov     rcx, r13; psz
0x18000935f  call    cs:__imp_SysAllocString
0x180009365  mov     rbx, rax
0x180009368  mov     [rsp+6F0h+bstrString], rax
0x18000936d  test    r13, r13
0x180009370  jz      short loc_180009379
0x180009372  test    rax, rax
0x180009375  cmovz   r14d, edi
0x180009379  mov     rcx, r13; pv
0x18000937c  call    cs:__imp_CoTaskMemFree
0x180009382  jmp     loc_18000921B
0x180009387  lea     rax, [rsp+6F0h+bstrString]
0x18000938c  mov     [rsp+6F0h+pdwType], rax; unsigned __int16 **
0x180009391  mov     r9d, 3; unsigned int
0x180009397  lea     r8, aDefaultvalue; "DefaultValue"
0x18000939e  lea     rdx, [rbp+5F0h+SubKey]; unsigned __int16 *
0x1800093a5  lea     rcx, [rsi-10h]; this
0x1800093a9  call    ?_getThemeSettingBSTR@CThemeFile@@AEAAJPEBG0KPEAPEAG@Z; CThemeFile::_getThemeSettingBSTR(ushort const *,ushort const *,ulong,ushort * *)
0x1800093ae  mov     r14d, eax
0x1800093b1  mov     rbx, [rsp+6F0h+bstrString]
0x1800093b6  test    eax, eax
0x1800093b8  jns     loc_180009229
0x1800093be  xor     eax, eax
0x1800093c0  mov     [rbp+5F0h+psz], ax
0x1800093c7  jmp     loc_180009240
0x1800093cc  mov     [rsp+6F0h+bstrString], rax
0x1800093d1  mov     rax, [rcx]
0x1800093d4  lea     rdx, [rsp+6F0h+bstrString]
0x1800093d9  mov     rax, [rax+140h]
0x1800093e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093e5  mov     ebx, eax
0x1800093e7  mov     rcx, [rsp+6F0h+bstrString]; bstrString
0x1800093ec  call    cs:__imp_SysFreeString
0x1800093f2  test    ebx, ebx
0x1800093f4  js      loc_1800095FC
0x1800093fa  xor     eax, eax
0x1800093fc  jmp     loc_180009134
0x180009401  mov     [rsp+6F0h+pszSource], 0
0x18000940a  lea     r9, aDefaultvalue; "DefaultValue"
0x180009411  lea     r8, aSMui; "%s.MUI"
0x180009418  mov     edx, 104h; unsigned __int64
0x18000941d  lea     rcx, [rbp+5F0h+SubKey]; unsigned __int16 *
0x180009424  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009429  mov     r14, [rsp+6F0h+var_690]
0x18000942e  test    eax, eax
0x180009430  js      short loc_180009466
0x180009432  mov     rcx, [rsp+6F0h+var_698]
0x180009437  mov     rax, [rcx]
0x18000943a  lea     rdx, [rsp+6F0h+pszSource]
0x18000943f  mov     [rsp+6F0h+pvData], rdx
0x180009444  mov     dword ptr [rsp+6F0h+pdwType], 1
0x18000944c  xor     r9d, r9d
0x18000944f  lea     r8, [rbp+5F0h+SubKey]
0x180009456  mov     rdx, r14
0x180009459  mov     rax, [rax+30h]
0x18000945d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009462  test    eax, eax
0x180009464  jns     short loc_1800094A1
0x180009466  mov     rcx, [rsp+6F0h+var_698]
0x18000946b  mov     rax, [rcx]
0x18000946e  lea     rdx, [rsp+6F0h+pszSource]
0x180009473  mov     [rsp+6F0h+pvData], rdx
0x180009478  mov     dword ptr [rsp+6F0h+pdwType], 1
0x180009480  xor     r9d, r9d
0x180009483  lea     r8, aDefaultvalue; "DefaultValue"
0x18000948a  mov     rdx, r14
0x18000948d  mov     rax, [rax+30h]
0x180009491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009496  mov     r14d, eax
0x180009499  test    eax, eax
0x18000949b  js      loc_18000933F
0x1800094a1  xor     edx, edx; Val
0x1800094a3  mov     r8d, 208h; Size
0x1800094a9  lea     rcx, [rsp+6F0h+pszOutBuf]; void *
0x1800094ae  call    memset_0
0x1800094b3  xor     r9d, r9d; ppvReserved
0x1800094b6  mov     r8d, 104h; cchOutBuf
0x1800094bc  lea     rdx, [rsp+6F0h+pszOutBuf]; pszOutBuf
0x1800094c1  mov     rcx, [rsp+6F0h+pszSource]; pszSource
0x1800094c6  call    cs:__imp_SHLoadIndirectString
0x1800094cc  mov     r14d, eax
0x1800094cf  test    eax, eax
0x1800094d1  js      short loc_18000954F
0x1800094d3  lea     rcx, [rsp+6F0h+pszOutBuf]; unsigned __int16 *
0x1800094d8  call    ?ExpandResourceDir@@YAJPEAGK@Z; ExpandResourceDir(ushort *,ulong)
0x1800094dd  mov     r14d, eax
0x1800094e0  test    eax, eax
0x1800094e2  js      short loc_18000954F
0x1800094e4  lea     rdx, [rsp+6F0h+pszOutBuf]; unsigned __int16 *
0x1800094e9  mov     rcx, [rsi+20h]; unsigned __int16 *
0x1800094ed  call    ?ExpandThemeTokens@@YAJPEBGPEAGH@Z; ExpandThemeTokens(ushort const *,ushort *,int)
0x1800094f2  mov     r14d, eax
0x1800094f5  test    eax, eax
0x1800094f7  js      short loc_18000954F
0x1800094f9  lea     rcx, [rsp+6F0h+pszOutBuf]; pszPath
0x1800094fe  call    cs:__imp_PathIsRelativeW
0x180009504  test    eax, eax
0x180009506  jnz     short loc_180009538
0x180009508  mov     [rsp+6F0h+var_6B0], eax
0x18000950c  lea     r9, [rsp+6F0h+var_6B0]; unsigned int *
0x180009511  lea     rcx, [rsp+6F0h+pszOutBuf]; unsigned __int16 *
0x180009516  call    ?SHMapUrlToZoneEx@@YAJPEBGPEAUIUnknown@@KPEAK@Z; SHMapUrlToZoneEx(ushort const *,IUnknown *,ulong,ulong *)
0x18000951b  cmp     [rsp+6F0h+pszOutBuf], 0
0x180009521  jz      short loc_18000955F
0x180009523  cmp     [rsp+6F0h+var_6B0], 0
0x180009528  jz      short loc_18000955F
0x18000952a  call    ?s_IsUncPathAllowedForThumbnailImage@CFileSource@@SAHXZ; CFileSource::s_IsUncPathAllowedForThumbnailImage(void)
0x18000952f  test    eax, eax
0x180009531  jnz     short loc_18000955F
0x180009533  mov     [rsp+6F0h+pszOutBuf], ax
0x180009538  lea     r9, [rsp+6F0h+var_688]
0x18000953d  lea     r8, [rsp+6F0h+pszOutBuf]
0x180009542  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180009547  mov     r14d, eax
0x18000954a  mov     r13, [rsp+6F0h+var_688]
0x18000954f  mov     rcx, [rsp+6F0h+pszSource]; pv
0x180009554  call    cs:__imp_CoTaskMemFree
0x18000955a  jmp     loc_18000933F
0x18000955f  lea     rcx, [rsp+6F0h+pszOutBuf]; unsigned __int16 *
0x180009564  call    ?ConfirmFile@@YAHPEAGH@Z; ConfirmFile(ushort *,int)
0x180009569  cmp     eax, 3
0x18000956c  jnz     short loc_180009538
0x18000956e  mov     r14d, 80070002h
0x180009574  jmp     short loc_18000954F
0x180009576  mov     r13, [rsp+6F0h+var_690]
0x18000957b  mov     r9, r13
0x18000957e  lea     r8, aSCurrent; "%s\\.Current"
0x180009585  mov     edx, 104h; unsigned __int64
0x18000958a  lea     rcx, [rbp+5F0h+SubKey]; unsigned __int16 *
0x180009591  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009596  mov     r14d, eax
0x180009599  test    eax, eax
0x18000959b  js      loc_1800093BE
0x1800095a1  jmp     loc_180009387
0x1800095a6  mov     r9d, 104h; cchBufferMax
0x1800095ac  lea     r8, [rbp+5F0h+psz]; lpBuffer
0x1800095b3  mov     rcx, cs:g_hinst; hInstance
0x1800095ba  call    cs:__imp_LoadStringW
0x1800095c0  test    eax, eax
0x1800095c2  jnz     short loc_1800095D1
0x1800095c4  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800095c9  test    eax, eax
0x1800095cb  js      loc_180009320
0x1800095d1  lea     rcx, [rbp+5F0h+psz]; unsigned __int16 *
0x1800095d8  call    ?ExpandResourceDir@@YAJPEAGK@Z; ExpandResourceDir(ushort *,ulong)
0x1800095dd  test    eax, eax
0x1800095df  js      loc_180009320
0x1800095e5  lea     rdx, [rbp+5F0h+psz]; unsigned __int16 *
0x1800095ec  mov     rcx, [rsi+20h]; unsigned __int16 *
0x1800095f0  call    ?ExpandThemeTokens@@YAJPEBGPEAGH@Z; ExpandThemeTokens(ushort const *,ushort *,int)
  ... truncated ...
```
