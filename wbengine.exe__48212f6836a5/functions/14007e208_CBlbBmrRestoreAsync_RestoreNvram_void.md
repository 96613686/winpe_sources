# CBlbBmrRestoreAsync::RestoreNvram(void)

- ea: `0x14007e208`
- end: `0x14007e855`
- name: `?RestoreNvram@CBlbBmrRestoreAsync@@AEAAJXZ`
- size: `1613`
- prototype: `__int64 __fastcall(CBlbBmrRestoreAsync *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14007d630`

## callees

- `0x140006948`
- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014200`
- `0x140014260`
- `0x140014384`
- `0x140028500`
- `0x14006a01c`
- `0x14006a044`
- `0x14007e208`
- `0x140088ba4`
- `0x140094cb8`
- `0x140094f38`
- `0x140134d20`

## import_xrefs

- `KERNEL32!CopyFileW` at `0x14007e4ba`
- `KERNEL32!CopyFileW` at `0x14007e4ba`
- `KERNEL32!DeleteFileW` at `0x14007e70b`
- `KERNEL32!DeleteFileW` at `0x14007e70b`
- `KERNEL32!RaiseException` at `0x14007e7dd`
- `KERNEL32!RaiseException` at `0x14007e7dd`
- `KERNEL32!GetLastError` at `0x14007e4c4`
- `KERNEL32!GetLastError` at `0x14007e4c4`
- `msvcrt!_wcsnicmp` at `0x14007e335`
- `msvcrt!_wcsnicmp` at `0x14007e335`
- `ntdll!RtlInitUnicodeString` at `0x14007e59e`
- `ntdll!RtlInitUnicodeString` at `0x14007e59e`
- `ole32!CoTaskMemFree` at `0x14007e77d`
- `ole32!CoTaskMemFree` at `0x14007e77d`
- `OLEAUT32!__imp_SysFreeString` at `0x14007e430`
- `OLEAUT32!__imp_SysFreeString` at `0x14007e52c`
- `OLEAUT32!__imp_SysFreeString` at `0x14007e558`
- `OLEAUT32!__imp_SysFreeString` at `0x14007e813`
- `OLEAUT32!__imp_SysFreeString` at `0x14007e81c`
- `OLEAUT32!__imp_SysFreeString` at `0x14007e825`
- `OLEAUT32!__imp_SysFreeString` at `0x14007e430`
- `OLEAUT32!__imp_SysFreeString` at `0x14007e52c`
- `OLEAUT32!__imp_SysFreeString` at `0x14007e558`
- `OLEAUT32!__imp_SysFreeString` at `0x14007e813`
- `OLEAUT32!__imp_SysFreeString` at `0x14007e81c`
- `OLEAUT32!__imp_SysFreeString` at `0x14007e825`
- `OLEAUT32!__imp_SysStringLen` at `0x14007e3c7`
- `OLEAUT32!__imp_SysStringLen` at `0x14007e40d`
- `OLEAUT32!__imp_SysStringLen` at `0x14007e535`
- `OLEAUT32!__imp_SysStringLen` at `0x14007e57e`
- `OLEAUT32!__imp_SysStringLen` at `0x14007e3c7`
- `OLEAUT32!__imp_SysStringLen` at `0x14007e40d`
- `OLEAUT32!__imp_SysStringLen` at `0x14007e535`
- `OLEAUT32!__imp_SysStringLen` at `0x14007e57e`
- `OLEAUT32!__imp_VarBstrCat` at `0x14007e424`
- `OLEAUT32!__imp_VarBstrCat` at `0x14007e54c`
- `OLEAUT32!__imp_VarBstrCat` at `0x14007e424`
- `OLEAUT32!__imp_VarBstrCat` at `0x14007e54c`
- `RPCRT4!UuidToStringW` at `0x14007e450`
- `RPCRT4!UuidToStringW` at `0x14007e450`
- `RPCRT4!UuidCreate` at `0x14007e442`
- `RPCRT4!UuidCreate` at `0x14007e442`
- `RPCRT4!RpcStringFreeW` at `0x14007e764`
- `RPCRT4!RpcStringFreeW` at `0x14007e764`
- `bcd!BcdSetSystemStoreDevice` at `0x14007e5a8`
- `bcd!BcdSetSystemStoreDevice` at `0x14007e5a8`
- `bcd!BcdImportStoreWithFlags` at `0x14007e69a`
- `bcd!BcdImportStoreWithFlags` at `0x14007e69a`

## string_xrefs

- `0x14007e302`: `base\stor\blb\engine\service\bmr.cpp`
- `0x14007e391`: `base\stor\blb\engine\service\bmr.cpp`
- `0x14007e3e4`: `base\stor\blb\engine\service\bmr.cpp`
- `0x14007e2f6`: `pVolCtxt->m_wszRestoreTargetPath`
- `0x14007e646`: `SeSystemEnvironmentPrivilege`

## pseudocode

```c
__int64 __fastcall CBlbBmrRestoreAsync::RestoreNvram(CBlbBmrRestoreAsync *this)
{
  WCHAR *v2; // rbx
  OLECHAR *v3; // rdi
  __int64 v4; // r15
  __int64 v5; // r14
  __int64 v6; // rsi
  wchar_t *v7; // r14
  signed int v8; // esi
  PVOID *v9; // rcx
  UINT v10; // eax
  signed int LastError; // eax
  int v12; // eax
  int v13; // edx
  signed int v14; // eax
  _QWORD *v15; // rcx
  int Buffer; // r9d
  int v17; // edx
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  int v20; // eax
  signed int v21; // r15d
  wchar_t *String2; // [rsp+30h] [rbp-49h] BYREF
  unsigned __int16 v24; // [rsp+38h] [rbp-41h] BYREF
  LPCWSTR lpNewFileName; // [rsp+40h] [rbp-39h] BYREF
  RPC_WSTR StringUuid; // [rsp+48h] [rbp-31h] BYREF
  BSTR pbstr; // [rsp+50h] [rbp-29h] BYREF
  PCWSTR SourceString; // [rsp+58h] [rbp-21h] BYREF
  __int128 v29; // [rsp+60h] [rbp-19h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-9h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+80h] [rbp+7h] BYREF
  UUID Uuid; // [rsp+90h] [rbp+17h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids);
  }
  NewState = 0;
  v29 = 0;
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&String2, &String1);
  v2 = 0;
  v3 = 0;
  lpNewFileName = 0;
  v29 = 0;
  pbstr = 0;
  v4 = 0;
  SourceString = 0;
  StringUuid = 0;
  Uuid = GUID_NULL;
  DestinationString = 0;
  while ( (unsigned int)v4 < *((_DWORD *)this + 83) )
  {
    v5 = *((_QWORD *)this + 33);
    v6 = 192 * v4;
    if ( (*(_BYTE *)(192 * v4 + v5 + 76) & 1) != 0 && *(_DWORD *)(v6 + v5 + 20) == 9 )
    {
      if ( !*(_QWORD *)(v6 + v5 + 112) )
        BlbAssert("base\\stor\\blb\\engine\\service\\bmr.cpp", 0x38Au, "pVolCtxt->m_wszRestoreTargetPath");
      ATL::CComBSTR::Append((ATL::CComBSTR *)&String2, *(const unsigned __int16 **)(v6 + v5 + 112));
      break;
    }
    v4 = (unsigned int)(v4 + 1);
  }
  v7 = String2;
  if ( _wcsnicmp(L"\\\\?\\", String2, 4u) )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids, v7);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    v8 = -2147024809;
    goto LABEL_75;
  }
  v7[1] = 63;
  if ( (_DWORD)v4 == *((_DWORD *)this + 83) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids);
    }
    BlbAssert("base\\stor\\blb\\engine\\service\\bmr.cpp", 0x39Fu, "FALSE");
    v8 = -2147418113;
    goto LABEL_20;
  }
  v8 = BlbutilRemoveTrailingBackslash(v7, (unsigned __int16 **)&SourceString);
  if ( v8 < 0 )
    goto LABEL_29;
  v10 = SysStringLen(v7);
  if ( v10 )
  {
    if ( v7[v10 - 1] != 92 )
    {
      v24 = 92;
      ATL::CComBSTR::Append((ATL::CComBSTR *)&String2, &v24, 1);
    }
  }
  else
  {
    BlbAssert("base\\stor\\blb\\engine\\service\\bmr.cpp", 0x3ABu, "length > 0");
  }
  ATL::CComBSTR::Append((ATL::CComBSTR *)&String2, L"EFI\\Microsoft\\Boot\\BCD");
  v7 = String2;
  if ( SysStringLen(String2) )
  {
    String2 = 0;
    if ( VarBstrCat(0, v7, &String2) >= 0 )
    {
      SysFreeString(0);
      v2 = String2;
      lpNewFileName = String2;
    }
  }
  UuidCreate(&Uuid);
  if ( UuidToStringW(&Uuid, &StringUuid) )
  {
    v8 = -2147418113;
LABEL_29:
    v9 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_75;
  }
  ATL::CComBSTR::Append((ATL::CComBSTR *)&lpNewFileName, StringUuid);
  v2 = (WCHAR *)lpNewFileName;
  if ( CopyFileW(v7, lpNewFileName, 1) )
  {
    SysFreeString(0);
    if ( SysStringLen(v7) )
    {
      lpNewFileName = 0;
      if ( VarBstrCat(0, v7, (LPBSTR)&lpNewFileName) >= 0 )
      {
        SysFreeString(0);
        pbstr = (BSTR)lpNewFileName;
      }
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&pbstr, StringUuid);
    v3 = pbstr;
    *((_QWORD *)&v29 + 1) = pbstr;
    LOWORD(v29) = 2 * SysStringLen(pbstr);
    WORD1(v29) = 2 * (v29 + 1);
    RtlInitUnicodeString(&DestinationString, SourceString);
    v12 = BcdSetSystemStoreDevice(&DestinationString);
    if ( v12 )
    {
      if ( v12 != -2143748093 )
      {
        v14 = HRESULTFromNTSTATUS(v12);
        v8 = v14;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_69;
        }
        Buffer = (int)DestinationString.Buffer;
        v17 = 67;
        goto LABEL_68;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids);
      }
    }
    v8 = BlbutilSetPrivilege(L"SeSystemEnvironmentPrivilege", v13, &NewState);
    if ( v8 < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_69;
      }
      v19 = 68;
      goto LABEL_57;
    }
    v20 = BcdImportStoreWithFlags(&v29, 1);
    if ( !v20 )
      goto LABEL_69;
    if ( v20 == -2143748095 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      {
        goto LABEL_69;
      }
      v19 = 69;
LABEL_57:
      WPP_SF_(v18[2], v19, &WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids);
LABEL_69:
      DeleteFileW(v2);
      goto LABEL_20;
    }
    v14 = HRESULTFromNTSTATUS(v20);
    v8 = v14;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_69;
    }
    Buffer = DWORD2(v29);
    v17 = 70;
LABEL_68:
    WPP_SF_Sd(v15[2], v17, (unsigned int)&WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids, Buffer, v14);
    goto LABEL_69;
  }
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError > 0 )
    v8 = (unsigned __int16)LastError | 0x80070000;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_SSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      65,
      (unsigned int)&WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids,
      (_DWORD)v7,
      (__int64)v2,
      v8);
LABEL_20:
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_75:
  if ( StringUuid )
  {
    RpcStringFreeW(&StringUuid);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( SourceString )
  {
    CoTaskMemFree((LPVOID)SourceString);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( NewState.PrivilegeCount )
  {
    v21 = BlbutilRevertPrivilege(&NewState);
    if ( v21 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids);
      }
      RaiseException(v21, 1u, 0, 0);
    }
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 && *((_BYTE *)v9 + 25) >= 4u )
    WPP_SF_(v9[2], 72, &WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids);
  SysFreeString(v3);
  SysFreeString(v2);
  SysFreeString(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14007e208  mov     [rsp-8+arg_8], rbx
0x14007e20d  mov     [rsp-8+arg_10], rsi
0x14007e212  push    rbp
0x14007e213  push    rdi
0x14007e214  push    r13
0x14007e216  push    r14
0x14007e218  push    r15
0x14007e21a  lea     rbp, [rsp-37h]
0x14007e21f  sub     rsp, 0B0h
0x14007e226  mov     rax, cs:__security_cookie
0x14007e22d  xor     rax, rsp
0x14007e230  mov     [rbp+57h+var_30], rax
0x14007e234  mov     r13, rcx
0x14007e237  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e23e  lea     rax, WPP_GLOBAL_Control
0x14007e245  mov     esi, 1
0x14007e24a  cmp     rcx, rax
0x14007e24d  jz      short loc_14007E26E
0x14007e24f  test    [rcx+1Ch], sil
0x14007e253  jz      short loc_14007E26E
0x14007e255  cmp     byte ptr [rcx+19h], 4
0x14007e259  jb      short loc_14007E26E
0x14007e25b  mov     rcx, [rcx+10h]
0x14007e25f  lea     edx, [rsi+3Dh]
0x14007e262  lea     r8, WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids
0x14007e269  call    WPP_SF_
0x14007e26e  xorps   xmm0, xmm0
0x14007e271  lea     rdx, String1; unsigned __int16 *
0x14007e278  xorps   xmm1, xmm1
0x14007e27b  lea     rcx, [rbp+57h+String2]; this
0x14007e27f  movups  xmmword ptr [rbp+57h+NewState.PrivilegeCount], xmm0
0x14007e283  movups  [rbp+57h+var_70], xmm1
0x14007e287  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x14007e28c  xor     ebx, ebx
0x14007e28e  xorps   xmm0, xmm0
0x14007e291  xor     edi, edi
0x14007e293  mov     [rbp+57h+lpNewFileName], rbx
0x14007e297  movups  [rbp+57h+var_70], xmm0
0x14007e29b  mov     [rbp+57h+pbstr], rdi
0x14007e29f  xor     r15d, r15d
0x14007e2a2  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14007e2a9  mov     [rbp+57h+SourceString], rbx
0x14007e2ad  xorps   xmm1, xmm1
0x14007e2b0  mov     [rbp+57h+StringUuid], rbx
0x14007e2b4  movdqu  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x14007e2b9  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x14007e2bd  cmp     r15d, [r13+14Ch]
0x14007e2c4  jnb     short loc_14007E321
0x14007e2c6  mov     r14, [r13+108h]
0x14007e2cd  lea     rsi, [r15+r15*2]
0x14007e2d1  shl     rsi, 6
0x14007e2d5  test    byte ptr [rsi+r14+4Ch], 1
0x14007e2db  jz      short loc_14007E2E5
0x14007e2dd  cmp     dword ptr [rsi+r14+14h], 9
0x14007e2e3  jz      short loc_14007E2EF
0x14007e2e5  mov     esi, 1
0x14007e2ea  add     r15d, esi
0x14007e2ed  jmp     short loc_14007E2BD
0x14007e2ef  cmp     [rsi+r14+70h], rbx
0x14007e2f4  jnz     short loc_14007E30E
0x14007e2f6  lea     r8, aPvolctxtMWszre; "pVolCtxt->m_wszRestoreTargetPath"
0x14007e2fd  mov     edx, 38Ah; unsigned int
0x14007e302  lea     rcx, aBaseStorBlbEng_10; "base\\stor\\blb\\engine\\service\\bmr.c"...
0x14007e309  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14007e30e  mov     rdx, [rsi+r14+70h]; unsigned __int16 *
0x14007e313  lea     rcx, [rbp+57h+String2]; this
0x14007e317  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x14007e31c  mov     esi, 1
0x14007e321  mov     r14, [rbp+57h+String2]
0x14007e325  lea     rcx, asc_1401417A8; "\\\\?\\"
0x14007e32c  mov     rdx, r14; String2
0x14007e32f  mov     r8d, 4; MaxCount
0x14007e335  call    cs:__imp__wcsnicmp
0x14007e33b  test    eax, eax
0x14007e33d  jnz     loc_14007E716
0x14007e343  mov     word ptr [r14+2], 3Fh ; '?'
0x14007e34a  cmp     r15d, [r13+14Ch]
0x14007e351  jnz     short loc_14007E3AE
0x14007e353  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e35a  lea     r13, WPP_GLOBAL_Control
0x14007e361  cmp     rcx, r13
0x14007e364  jz      short loc_14007E385
0x14007e366  test    [rcx+1Ch], sil
0x14007e36a  jz      short loc_14007E385
0x14007e36c  cmp     byte ptr [rcx+19h], 2
0x14007e370  jb      short loc_14007E385
0x14007e372  mov     rcx, [rcx+10h]
0x14007e376  lea     edx, [rax+40h]
0x14007e379  lea     r8, WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids
0x14007e380  call    WPP_SF_
0x14007e385  lea     r8, aFalse_1; "FALSE"
0x14007e38c  mov     edx, 39Fh; unsigned int
0x14007e391  lea     rcx, aBaseStorBlbEng_10; "base\\stor\\blb\\engine\\service\\bmr.c"...
0x14007e398  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14007e39d  mov     esi, 8000FFFFh
0x14007e3a2  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e3a9  jmp     loc_14007E759
0x14007e3ae  lea     rdx, [rbp+57h+SourceString]; unsigned __int16 **
0x14007e3b2  mov     rcx, r14; unsigned __int16 *
0x14007e3b5  call    ?BlbutilRemoveTrailingBackslash@@YAJPEBGPEAPEAG@Z; BlbutilRemoveTrailingBackslash(ushort const *,ushort * *)
0x14007e3ba  mov     esi, eax
0x14007e3bc  test    eax, eax
0x14007e3be  js      loc_14007E45F
0x14007e3c4  mov     rcx, r14; pbstr
0x14007e3c7  call    cs:__imp_SysStringLen
0x14007e3cd  mov     eax, eax
0x14007e3cf  test    rax, rax
0x14007e3d2  jnz     loc_14007E472
0x14007e3d8  lea     r8, aLength0; "length > 0"
0x14007e3df  mov     edx, 3ABh; unsigned int
0x14007e3e4  lea     rcx, aBaseStorBlbEng_10; "base\\stor\\blb\\engine\\service\\bmr.c"...
0x14007e3eb  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14007e3f0  mov     r15d, 1
0x14007e3f6  lea     rdx, aEfiMicrosoftBo; "EFI\\Microsoft\\Boot\\BCD"
0x14007e3fd  lea     rcx, [rbp+57h+String2]; this
0x14007e401  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x14007e406  mov     r14, [rbp+57h+String2]
0x14007e40a  mov     rcx, r14; pbstr
0x14007e40d  call    cs:__imp_SysStringLen
0x14007e413  test    eax, eax
0x14007e415  jz      short loc_14007E43E
0x14007e417  lea     r8, [rbp+57h+String2]; pbstrResult
0x14007e41b  mov     [rbp+57h+String2], rbx
0x14007e41f  mov     rdx, r14; bstrRight
0x14007e422  xor     ecx, ecx; bstrLeft
0x14007e424  call    cs:__imp_VarBstrCat
0x14007e42a  test    eax, eax
0x14007e42c  js      short loc_14007E43E
0x14007e42e  xor     ecx, ecx; bstrString
0x14007e430  call    cs:__imp_SysFreeString
0x14007e436  mov     rbx, [rbp+57h+String2]
0x14007e43a  mov     [rbp+57h+lpNewFileName], rbx
0x14007e43e  lea     rcx, [rbp+57h+Uuid]; Uuid
0x14007e442  call    cs:__imp_UuidCreate
0x14007e448  lea     rdx, [rbp+57h+StringUuid]; StringUuid
0x14007e44c  lea     rcx, [rbp+57h+Uuid]; Uuid
0x14007e450  call    cs:__imp_UuidToStringW
0x14007e456  test    eax, eax
0x14007e458  jz      short loc_14007E4A0
0x14007e45a  mov     esi, 8000FFFFh
0x14007e45f  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e466  lea     r13, WPP_GLOBAL_Control
0x14007e46d  jmp     loc_14007E759
0x14007e472  mov     ecx, 5Ch ; '\'
0x14007e477  cmp     [r14+rax*2-2], cx
0x14007e47d  jz      loc_14007E3F0
0x14007e483  lea     r15d, [rcx-5Bh]
0x14007e487  mov     [rbp+57h+var_98], cx
0x14007e48b  mov     r8d, r15d; int
0x14007e48e  lea     rdx, [rbp+57h+var_98]; unsigned __int16 *
0x14007e492  lea     rcx, [rbp+57h+String2]; this
0x14007e496  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x14007e49b  jmp     loc_14007E3F6
0x14007e4a0  mov     rdx, [rbp+57h+StringUuid]; unsigned __int16 *
0x14007e4a4  lea     rcx, [rbp+57h+lpNewFileName]; this
0x14007e4a8  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x14007e4ad  mov     rbx, [rbp+57h+lpNewFileName]
0x14007e4b1  mov     r8d, r15d; bFailIfExists
0x14007e4b4  mov     rdx, rbx; lpNewFileName
0x14007e4b7  mov     rcx, r14; lpExistingFileName
0x14007e4ba  call    cs:__imp_CopyFileW
0x14007e4c0  test    eax, eax
0x14007e4c2  jnz     short loc_14007E52A
0x14007e4c4  call    cs:__imp_GetLastError
0x14007e4ca  mov     esi, eax
0x14007e4cc  test    eax, eax
0x14007e4ce  jle     short loc_14007E4D9
0x14007e4d0  movzx   esi, ax
0x14007e4d3  or      esi, 80070000h
0x14007e4d9  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e4e0  lea     r13, WPP_GLOBAL_Control
0x14007e4e7  cmp     rcx, r13
0x14007e4ea  jz      loc_14007E759
0x14007e4f0  test    [rcx+1Ch], r15b
0x14007e4f4  jz      loc_14007E759
0x14007e4fa  cmp     byte ptr [rcx+19h], 2
0x14007e4fe  jb      loc_14007E759
0x14007e504  mov     rcx, [rcx+10h]
0x14007e508  lea     r8, WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids
0x14007e50f  mov     edx, 41h ; 'A'
0x14007e514  mov     [rsp+0D0h+var_A8], esi
0x14007e518  mov     r9, r14
0x14007e51b  mov     [rsp+0D0h+var_B0], rbx
0x14007e520  call    WPP_SF_SSD
0x14007e525  jmp     loc_14007E3A2
0x14007e52a  xor     ecx, ecx; bstrString
0x14007e52c  call    cs:__imp_SysFreeString
0x14007e532  mov     rcx, r14; pbstr
0x14007e535  call    cs:__imp_SysStringLen
0x14007e53b  test    eax, eax
0x14007e53d  jz      short loc_14007E566
0x14007e53f  lea     r8, [rbp+57h+lpNewFileName]; pbstrResult
0x14007e543  mov     [rbp+57h+lpNewFileName], rdi
0x14007e547  mov     rdx, r14; bstrRight
0x14007e54a  xor     ecx, ecx; bstrLeft
0x14007e54c  call    cs:__imp_VarBstrCat
0x14007e552  test    eax, eax
0x14007e554  js      short loc_14007E566
0x14007e556  xor     ecx, ecx; bstrString
0x14007e558  call    cs:__imp_SysFreeString
0x14007e55e  mov     rax, [rbp+57h+lpNewFileName]
0x14007e562  mov     [rbp+57h+pbstr], rax
0x14007e566  mov     rdx, [rbp+57h+StringUuid]; unsigned __int16 *
0x14007e56a  lea     rcx, [rbp+57h+pbstr]; this
0x14007e56e  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x14007e573  mov     rdi, [rbp+57h+pbstr]
0x14007e577  mov     rcx, rdi; pbstr
0x14007e57a  mov     qword ptr [rbp+57h+var_70+8], rdi
0x14007e57e  call    cs:__imp_SysStringLen
0x14007e584  mov     rdx, [rbp+57h+SourceString]; SourceString
0x14007e588  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14007e58c  add     ax, ax
0x14007e58f  mov     word ptr [rbp+57h+var_70], ax
0x14007e593  add     ax, r15w
0x14007e597  add     ax, ax
0x14007e59a  mov     word ptr [rbp+57h+var_70+2], ax
0x14007e59e  call    cs:__imp_RtlInitUnicodeString
0x14007e5a4  lea     rcx, [rbp+57h+DestinationString]
0x14007e5a8  call    cs:__imp_BcdSetSystemStoreDevice
0x14007e5ae  test    eax, eax
0x14007e5b0  jz      loc_14007E63B
0x14007e5b6  cmp     eax, 80390003h
0x14007e5bb  jnz     short loc_14007E5F9
0x14007e5bd  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e5c4  lea     r13, WPP_GLOBAL_Control
0x14007e5cb  cmp     rcx, r13
0x14007e5ce  jz      short loc_14007E642
0x14007e5d0  test    [rcx+1Ch], r15b
0x14007e5d4  jz      short loc_14007E642
0x14007e5d6  cmp     byte ptr [rcx+19h], 3
0x14007e5da  jb      short loc_14007E642
0x14007e5dc  mov     rcx, [rcx+10h]
0x14007e5e0  lea     r8, WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids
0x14007e5e7  mov     edx, 42h ; 'B'
0x14007e5ec  mov     r9d, 80390003h
0x14007e5f2  call    WPP_SF_d
0x14007e5f7  jmp     short loc_14007E642
0x14007e5f9  mov     ecx, eax; int
0x14007e5fb  call    ?HRESULTFromNTSTATUS@@YAJJ@Z; HRESULTFromNTSTATUS(long)
0x14007e600  mov     esi, eax
0x14007e602  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e609  lea     r13, WPP_GLOBAL_Control
0x14007e610  cmp     rcx, r13
0x14007e613  jz      loc_14007E708
0x14007e619  test    [rcx+1Ch], r15b
0x14007e61d  jz      loc_14007E708
0x14007e623  cmp     byte ptr [rcx+19h], 2
0x14007e627  jb      loc_14007E708
0x14007e62d  mov     r9, [rbp+57h+DestinationString.Buffer]
0x14007e631  mov     edx, 43h ; 'C'
0x14007e636  jmp     loc_14007E6F4
0x14007e63b  lea     r13, WPP_GLOBAL_Control
0x14007e642  lea     r8, [rbp+57h+NewState]; struct _TOKEN_PRIVILEGES *
0x14007e646  lea     rcx, aSesystemenviro; "SeSystemEnvironmentPrivilege"
0x14007e64d  call    ?BlbutilSetPrivilege@@YAJPEBGHPEAU_TOKEN_PRIVILEGES@@@Z; BlbutilSetPrivilege(ushort const *,int,_TOKEN_PRIVILEGES *)
0x14007e652  mov     esi, eax
0x14007e654  test    eax, eax
0x14007e656  jns     short loc_14007E693
0x14007e658  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e65f  cmp     rcx, r13
0x14007e662  jz      loc_14007E708
0x14007e668  test    [rcx+1Ch], r15b
0x14007e66c  jz      loc_14007E708
0x14007e672  cmp     byte ptr [rcx+19h], 2
0x14007e676  jb      loc_14007E708
0x14007e67c  mov     edx, 44h ; 'D'
0x14007e681  mov     rcx, [rcx+10h]
0x14007e685  lea     r8, WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids
0x14007e68c  call    WPP_SF_
0x14007e691  jmp     short loc_14007E708
0x14007e693  mov     edx, r15d
0x14007e696  lea     rcx, [rbp+57h+var_70]
0x14007e69a  call    cs:__imp_BcdImportStoreWithFlags
0x14007e6a0  test    eax, eax
0x14007e6a2  jz      short loc_14007E708
0x14007e6a4  cmp     eax, 80390001h
0x14007e6a9  jnz     short loc_14007E6CA
0x14007e6ab  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e6b2  cmp     rcx, r13
0x14007e6b5  jz      short loc_14007E708
0x14007e6b7  test    [rcx+1Ch], r15b
0x14007e6bb  jz      short loc_14007E708
0x14007e6bd  cmp     byte ptr [rcx+19h], 3
0x14007e6c1  jb      short loc_14007E708
0x14007e6c3  mov     edx, 45h ; 'E'
0x14007e6c8  jmp     short loc_14007E681
0x14007e6ca  mov     ecx, eax; int
0x14007e6cc  call    ?HRESULTFromNTSTATUS@@YAJJ@Z; HRESULTFromNTSTATUS(long)
0x14007e6d1  mov     esi, eax
0x14007e6d3  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e6da  cmp     rcx, r13
0x14007e6dd  jz      short loc_14007E708
0x14007e6df  test    [rcx+1Ch], r15b
0x14007e6e3  jz      short loc_14007E708
0x14007e6e5  cmp     byte ptr [rcx+19h], 2
0x14007e6e9  jb      short loc_14007E708
0x14007e6eb  mov     r9, qword ptr [rbp+57h+var_70+8]
0x14007e6ef  mov     edx, 46h ; 'F'
0x14007e6f4  mov     rcx, [rcx+10h]
0x14007e6f8  lea     r8, WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids
  ... truncated ...
```
