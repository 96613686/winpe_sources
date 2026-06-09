# SaveDSNAttributes(HWND__ *,tagDLGSTRUCT *,int)

- ea: `0x38395d490`
- end: `0x38395df05`
- name: `?SaveDSNAttributes@@YAKPEAUHWND__@@PEAUtagDLGSTRUCT@@H@Z`
- size: `2677`
- prototype: `unsigned int __fastcall(HWND, struct tagDLGSTRUCT *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x3839244b0`
- `0x38395cdc0`

## callees

- `0x3838434c0`
- `0x38387c938`
- `0x383893160`
- `0x3838a1e3c`
- `0x38395d490`
- `0x383a981cc`
- `0x383adbfd0`
- `0x383adc100`
- `0x383adc1d0`
- `0x383adc220`

## import_xrefs

- `MSVCR100!_wcsicmp` at `0x38395dd51`
- `MSVCR100!_wcsicmp` at `0x38395ddb8`
- `MSVCR100!_wcsicmp` at `0x38395dd51`
- `MSVCR100!_wcsicmp` at `0x38395ddb8`
- `ADVAPI32!RegOpenKeyExW` at `0x38395deaf`
- `ADVAPI32!RegOpenKeyExW` at `0x38395deaf`
- `ADVAPI32!RegDeleteValueW` at `0x38395dec1`
- `ADVAPI32!RegDeleteValueW` at `0x38395dec1`
- `ADVAPI32!RegDeleteKeyW` at `0x38395de94`
- `ADVAPI32!RegDeleteKeyW` at `0x38395de94`
- `ADVAPI32!RegCloseKey` at `0x38395decc`
- `ADVAPI32!RegCloseKey` at `0x38395decc`

## string_xrefs

- `0x38395dcd1`: `TranslationDLL`

## pseudocode

```c
__int64 __fastcall SaveDSNAttributes(HWND a1, struct tagDLGSTRUCT *a2)
{
  __int64 v2; // rbp
  HWND v3; // rbx
  int v4; // r15d
  __int64 v5; // r8
  __int64 v7; // r9
  const WCHAR *v8; // rsi
  const WCHAR *v10; // rdi
  __int64 v11; // r8
  const WCHAR *v12; // r8
  __int64 v13; // r8
  const WCHAR *v14; // r8
  __int64 v15; // r8
  const WCHAR *v16; // r8
  __int64 v17; // r8
  const WCHAR *v18; // r8
  __int64 v19; // r8
  const WCHAR *v20; // r8
  __int64 v21; // r8
  const WCHAR *v22; // r8
  __int64 v23; // r8
  const WCHAR *v24; // r8
  __int64 v25; // r8
  const WCHAR *v26; // r8
  __int64 v27; // r8
  const WCHAR *v28; // r8
  __int64 v29; // r8
  const WCHAR *v30; // r8
  __int64 v31; // r8
  const WCHAR *v32; // r8
  __int64 v33; // r8
  const WCHAR *v34; // r8
  __int64 v35; // r8
  const WCHAR *v36; // r8
  __int64 v37; // r8
  const WCHAR *v38; // r8
  __int64 v39; // r8
  const WCHAR *v40; // r8
  __int64 v41; // r8
  const WCHAR *v42; // r8
  __int64 v43; // r8
  const WCHAR *v44; // r8
  __int64 v45; // r8
  const WCHAR *v46; // r8
  __int64 v47; // r8
  const WCHAR *v48; // r8
  __int64 v49; // r8
  const WCHAR *v50; // r8
  __int64 v51; // r8
  const WCHAR *v52; // r8
  __int64 v53; // r8
  const WCHAR *v54; // r8
  __int64 v55; // r8
  const WCHAR *v56; // r8
  __int64 v57; // rcx
  __int64 v58; // rax
  __int64 v59; // rcx
  const unsigned __int16 *v60; // r8
  const WCHAR *v61; // rbx
  DWORD pfErrorCode[2]; // [rsp+30h] [rbp-458h] BYREF
  BYTE Data[2]; // [rsp+40h] [rbp-448h] BYREF

  v2 = *((_QWORD *)a1 + 7);
  v3 = a1 + 32;
  v4 = (int)a2;
  v5 = *((_QWORD *)a1 + 17);
  v7 = *(_QWORD *)(*((_QWORD *)a1 + 18) + 32LL);
  v8 = (const WCHAR *)(v7 + *(_QWORD *)(v5 + 56));
  if ( ((_BYTE)a1[28] & 0x20) != 0
    && (!*(_WORD *)(v7 + *(_QWORD *)(v5 + 128))
     || !*(_WORD *)(v7 + *(_QWORD *)(v5 + 344)) && (*(_BYTE *)(v5 + 336) & 0x20) == 0
     || !*(_WORD *)(v7 + *(_QWORD *)(v5 + 320)) && (*(_BYTE *)(v5 + 312) & 0x20) == 0) )
  {
    return 4;
  }
  v10 = 0;
  if ( !SQLWriteDSNToIniW((LPCWSTR)(v7 + *(_QWORD *)(v5 + 56)), L"SQL Server Native Client 11.0") )
  {
    pfErrorCode[0] = 0;
    SQLInstallerErrorW(1u, pfErrorCode, 0, 0, 0);
    return pfErrorCode[0];
  }
  if ( ((v2 || (*(_BYTE *)(*((_QWORD *)v3 + 1) + 72LL) & 1) != 0)
     && ((v11 = *((_QWORD *)v3 + 1), (*(_BYTE *)(v11 + 72) & 0x20) == 0)
       ? (v12 = (const WCHAR *)(*(_QWORD *)(*((_QWORD *)v3 + 2) + 32LL) + *(_QWORD *)(v11 + 80)))
       : (v12 = 0),
         SQLWritePrivateProfileStringW(v8, L"Description", v12, L"ODBC.INI"),
         v2)
     || (*(_BYTE *)(*((_QWORD *)v3 + 1) + 120LL) & 1) != 0)
    && ((v13 = *((_QWORD *)v3 + 1), (*(_BYTE *)(v13 + 120) & 0x20) == 0)
      ? (v14 = (const WCHAR *)(*(_QWORD *)(*((_QWORD *)v3 + 2) + 32LL) + *(_QWORD *)(v13 + 128)))
      : (v14 = 0),
        SQLWritePrivateProfileStringW(v8, L"Server", v14, L"ODBC.INI"),
        v2)
    || (*(_BYTE *)(*((_QWORD *)v3 + 1) + 600LL) & 1) != 0 )
  {
    v15 = *((_QWORD *)v3 + 1);
    v16 = (*(_BYTE *)(v15 + 600) & 0x20) != 0
        ? 0LL
        : (const WCHAR *)(*(_QWORD *)(*((_QWORD *)v3 + 2) + 32LL) + *(_QWORD *)(v15 + 608));
    SQLWritePrivateProfileStringW(v8, L"Regional", v16, L"ODBC.INI");
    if ( v2 )
      goto LABEL_173;
  }
  if ( (*(_BYTE *)(*((_QWORD *)v3 + 1) + 624LL) & 1) != 0 )
  {
LABEL_173:
    v17 = *((_QWORD *)v3 + 1);
    v18 = (*(_BYTE *)(v17 + 624) & 0x20) != 0
        ? 0LL
        : (const WCHAR *)(*(_QWORD *)(*((_QWORD *)v3 + 2) + 32LL) + *(_QWORD *)(v17 + 632));
    SQLWritePrivateProfileStringW(v8, L"QuotedId", v18, L"ODBC.INI");
    if ( v2 )
      goto LABEL_172;
  }
  if ( (*(_BYTE *)(*((_QWORD *)v3 + 1) + 648LL) & 1) != 0 )
  {
LABEL_172:
    v19 = *((_QWORD *)v3 + 1);
    v20 = (*(_BYTE *)(v19 + 648) & 0x20) != 0
        ? 0LL
        : (const WCHAR *)(*(_QWORD *)(*((_QWORD *)v3 + 2) + 32LL) + *(_QWORD *)(v19 + 656));
    SQLWritePrivateProfileStringW(v8, L"AnsiNPW", v20, L"ODBC.INI");
    if ( v2 )
      goto LABEL_171;
  }
  if ( (*(_BYTE *)(*((_QWORD *)v3 + 1) + 264LL) & 1) != 0 )
  {
LABEL_171:
    v21 = *((_QWORD *)v3 + 1);
    v22 = (*(_BYTE *)(v21 + 264) & 0x20) != 0
        ? 0LL
        : (const WCHAR *)(*(_QWORD *)(*((_QWORD *)v3 + 2) + 32LL) + *(_QWORD *)(v21 + 272));
    SQLWritePrivateProfileStringW(v8, L"Database", v22, L"ODBC.INI");
    if ( v2 )
      goto LABEL_170;
  }
  if ( (*(_BYTE *)(*((_QWORD *)v3 + 1) + 288LL) & 1) != 0 )
  {
LABEL_170:
    v23 = *((_QWORD *)v3 + 1);
    v24 = (*(_BYTE *)(v23 + 288) & 0x20) != 0
        ? 0LL
        : (const WCHAR *)(*(_QWORD *)(*((_QWORD *)v3 + 2) + 32LL) + *(_QWORD *)(v23 + 296));
    SQLWritePrivateProfileStringW(v8, L"Language", v24, L"ODBC.INI");
    if ( v2 )
      goto LABEL_169;
  }
  if ( (*(_BYTE *)(*((_QWORD *)v3 + 1) + 672LL) & 1) != 0 )
  {
LABEL_169:
    v25 = *((_QWORD *)v3 + 1);
    v26 = (*(_BYTE *)(v25 + 672) & 0x20) != 0
        ? 0LL
        : (const WCHAR *)(*(_QWORD *)(*((_QWORD *)v3 + 2) + 32LL) + *(_QWORD *)(v25 + 680));
    SQLWritePrivateProfileStringW(v8, L"AttachDBFileName", v26, L"ODBC.INI");
    if ( v2 )
      goto LABEL_168;
  }
  if ( (*(_BYTE *)(*((_QWORD *)v3 + 1) + 360LL) & 1) != 0 )
  {
LABEL_168:
    v27 = *((_QWORD *)v3 + 1);
    v28 = (*(_BYTE *)(v27 + 360) & 0x20) != 0
        ? 0LL
        : (const WCHAR *)(*(_QWORD *)(*((_QWORD *)v3 + 2) + 32LL) + *(_QWORD *)(v27 + 368));
    SQLWritePrivateProfileStringW(v8, L"Encrypt", v28, L"ODBC.INI");
    if ( v2 )
      goto LABEL_167;
  }
  if ( (*(_BYTE *)(*((_QWORD *)v3 + 1) + 384LL) & 1) != 0 )
  {
LABEL_167:
    v29 = *((_QWORD *)v3 + 1);
    v30 = (*(_BYTE *)(v29 + 384) & 0x20) != 0
        ? 0LL
        : (const WCHAR *)(*(_QWORD *)(*((_QWORD *)v3 + 2) + 32LL) + *(_QWORD *)(v29 + 392));
    SQLWritePrivateProfileStringW(v8, L"TrustServerCertificate", v30, L"ODBC.INI");
    if ( v2 )
      goto LABEL_166;
  }
  if ( (*(_BYTE *)(*((_QWORD *)v3 + 1) + 408LL) & 1) != 0 )
  {
LABEL_166:
    v31 = *((_QWORD *)v3 + 1);
    v32 = (*(_BYTE *)(v31 + 408) & 0x20) != 0
        ? 0LL
        : (const WCHAR *)(*(_QWORD *)(*((_QWORD *)v3 + 2) + 32LL) + *(_QWORD *)(v31 + 416));
    SQLWritePrivateProfileStringW(v8, L"MARS_Connection", v32, L"ODBC.INI");
    if ( v2 )
      goto LABEL_165;
  }
  if ( (*(_BYTE *)(*((_QWORD *)v3 + 1) + 432LL) & 1) != 0 )
  {
LABEL_165:
    v33 = *((_QWORD *)v3 + 1);
    v34 = (*(_BYTE *)(v33 + 432) & 0x20) != 0
        ? 0LL
        : (const WCHAR *)(*(_QWORD *)(*((_QWORD *)v3 + 2) + 32LL) + *(_QWORD *)(v33 + 440));
    SQLWritePrivateProfileStringW(v8, L"Failover_Partner", v34, L"ODBC.INI");
    if ( v2 )
      goto LABEL_164;
  }
  if ( (*(_BYTE *)(*((_QWORD *)v3 + 1) + 696LL) & 1) != 0 )
  {
LABEL_164:
    v35 = *((_QWORD *)v3 + 1);
    v36 = (*(_BYTE *)(v35 + 696) & 0x20) != 0
        ? 0LL
        : (const WCHAR *)(*(_QWORD *)(*((_QWORD *)v3 + 2) + 32LL) + *(_QWORD *)(v35 + 704));
    SQLWritePrivateProfileStringW(v8, L"ServerSPN", v36, L"ODBC.INI");
    if ( v2 )
      goto LABEL_163;
  }
  if ( (*(_BYTE *)(*((_QWORD *)v3 + 1) + 720LL) & 1) != 0 )
  {
LABEL_163:
    v37 = *((_QWORD *)v3 + 1);
    v38 = (*(_BYTE *)(v37 + 720) & 0x20) != 0
        ? 0LL
        : (const WCHAR *)(*(_QWORD *)(*((_QWORD *)v3 + 2) + 32LL) + *(_QWORD *)(v37 + 728));
    SQLWritePrivateProfileStringW(v8, L"FailoverPartnerSPN", v38, L"ODBC.INI");
    if ( v2 )
      goto LABEL_162;
  }
  if ( (*(_BYTE *)(*((_QWORD *)v3 + 1) + 744LL) & 1) != 0 )
  {
LABEL_162:
    v39 = *((_QWORD *)v3 + 1);
    v40 = (*(_BYTE *)(v39 + 744) & 0x20) != 0
        ? 0LL
        : (const WCHAR *)(*(_QWORD *)(*((_QWORD *)v3 + 2) + 32LL) + *(_QWORD *)(v39 + 752));
    SQLWritePrivateProfileStringW(v8, L"ApplicationIntent", v40, L"ODBC.INI");
    if ( v2 )
      goto LABEL_161;
  }
  if ( (*(_BYTE *)(*((_QWORD *)v3 + 1) + 768LL) & 1) != 0 )
  {
LABEL_161:
    v41 = *((_QWORD *)v3 + 1);
    v42 = (*(_BYTE *)(v41 + 768) & 0x20) != 0
        ? 0LL
        : (const WCHAR *)(*(_QWORD *)(*((_QWORD *)v3 + 2) + 32LL) + *(_QWORD *)(v41 + 776));
    SQLWritePrivateProfileStringW(v8, L"MultiSubnetFailover", v42, L"ODBC.INI");
    if ( v2 )
      goto LABEL_160;
  }
  if ( (*(_BYTE *)(*((_QWORD *)v3 + 1) + 144LL) & 1) != 0 )
  {
LABEL_160:
    v43 = *((_QWORD *)v3 + 1);
    v44 = (*(_BYTE *)(v43 + 144) & 0x20) != 0
        ? 0LL
        : (const WCHAR *)(*(_QWORD *)(*((_QWORD *)v3 + 2) + 32LL) + *(_QWORD *)(v43 + 152));
    SQLWritePrivateProfileStringW(v8, L"LastUser", v44, L"ODBC.INI");
    if ( v2 )
      goto LABEL_159;
  }
  if ( (*(_BYTE *)(*((_QWORD *)v3 + 1) + 504LL) & 1) != 0 )
  {
LABEL_159:
    v45 = *((_QWORD *)v3 + 1);
    v46 = (*(_BYTE *)(v45 + 504) & 0x20) != 0
        ? 0LL
        : (const WCHAR *)(*(_QWORD *)(*((_QWORD *)v3 + 2) + 32LL) + *(_QWORD *)(v45 + 512));
    SQLWritePrivateProfileStringW(v8, L"QueryLogFile", v46, L"ODBC.INI");
    if ( v2 )
      goto LABEL_158;
  }
  if ( (*(_BYTE *)(*((_QWORD *)v3 + 1) + 576LL) & 1) != 0 )
  {
LABEL_158:
    v47 = *((_QWORD *)v3 + 1);
    v48 = (*(_BYTE *)(v47 + 576) & 0x20) != 0
        ? 0LL
        : (const WCHAR *)(*(_QWORD *)(*((_QWORD *)v3 + 2) + 32LL) + *(_QWORD *)(v47 + 584));
    SQLWritePrivateProfileStringW(v8, L"StatsLogFile", v48, L"ODBC.INI");
    if ( v2 )
      goto LABEL_157;
  }
  if ( (*(_BYTE *)(*((_QWORD *)v3 + 1) + 480LL) & 1) != 0 )
  {
LABEL_157:
    v49 = *((_QWORD *)v3 + 1);
    v50 = (*(_BYTE *)(v49 + 480) & 0x20) != 0
        ? 0LL
        : (const WCHAR *)(*(_QWORD *)(*((_QWORD *)v3 + 2) + 32LL) + *(_QWORD *)(v49 + 488));
    SQLWritePrivateProfileStringW(v8, L"QueryLog_On", v50, L"ODBC.INI");
    if ( v2 )
      goto LABEL_156;
  }
  if ( (*(_BYTE *)(*((_QWORD *)v3 + 1) + 552LL) & 1) != 0 )
  {
LABEL_156:
    v51 = *((_QWORD *)v3 + 1);
    v52 = (*(_BYTE *)(v51 + 552) & 0x20) != 0
        ? 0LL
        : (const WCHAR *)(*(_QWORD *)(*((_QWORD *)v3 + 2) + 32LL) + *(_QWORD *)(v51 + 560));
    SQLWritePrivateProfileStringW(v8, L"StatsLog_On", v52, L"ODBC.INI");
    if ( v2 )
      goto LABEL_155;
  }
  if ( (*(_BYTE *)(*((_QWORD *)v3 + 1) + 528LL) & 1) != 0 )
  {
LABEL_155:
    v53 = *((_QWORD *)v3 + 1);
    v54 = (*(_BYTE *)(v53 + 528) & 0x20) != 0
        ? 0LL
        : (const WCHAR *)(*(_QWORD *)(*((_QWORD *)v3 + 2) + 32LL) + *(_QWORD *)(v53 + 536));
    SQLWritePrivateProfileStringW(v8, L"QueryLogTime", v54, L"ODBC.INI");
    if ( v2 )
      goto LABEL_154;
  }
  if ( (*(_BYTE *)(*((_QWORD *)v3 + 1) + 192LL) & 1) != 0 )
  {
LABEL_154:
    v55 = *((_QWORD *)v3 + 1);
    v56 = (*(_BYTE *)(v55 + 192) & 0x20) != 0
        ? 0LL
        : (const WCHAR *)(*(_QWORD *)(*((_QWORD *)v3 + 2) + 32LL) + *(_QWORD *)(v55 + 200));
    SQLWritePrivateProfileStringW(v8, L"Trusted_Connection", v56, L"ODBC.INI");
    if ( v2 )
      goto LABEL_127;
  }
  if ( (*(_BYTE *)(*((_QWORD *)v3 + 1) + 456LL) & 1) != 0 )
  {
LABEL_127:
    v57 = *((_QWORD *)v3 + 1);
    if ( (*(_BYTE *)(v57 + 456) & 0x20) == 0 )
      v10 = (const WCHAR *)(*(_QWORD *)(*((_QWORD *)v3 + 2) + 32LL) + *(_QWORD *)(v57 + 464));
    SQLWritePrivateProfileStringW(v8, L"AutoTranslate", v10, L"ODBC.INI");
  }
  SQLWritePrivateProfileStringW(v8, L"FastConnectOption", 0, L"ODBC.INI");
  SQLWritePrivateProfileStringW(v8, L"Network", 0, L"ODBC.INI");
  SQLWritePrivateProfileStringW(v8, L"Address", 0, L"ODBC.INI");
  SQLWritePrivateProfileStringW(v8, L"TranslationName", 0, L"ODBC.INI");
  SQLWritePrivateProfileStringW(v8, L"TranslationOption", 0, L"ODBC.INI");
  SQLWritePrivateProfileStringW(v8, L"TranslationDLL", 0, L"ODBC.INI");
  SQLWritePrivateProfileStringW(v8, L"OemToAnsi", 0, L"ODBC.INI");
  SQLWritePrivateProfileStringW(v8, L"UseProcForPrepare", 0, L"ODBC.INI");
  SQLWritePrivateProfileStringW(v8, L"Fallback", 0, L"ODBC.INI");
  if ( !v4
    && (*(_BYTE *)(*((_QWORD *)v3 + 1) + 48LL) & 1) != 0
    && *((_WORD *)a1 + 84)
    && _wcsicmp((const wchar_t *)a1 + 84, v8) )
  {
    SQLRemoveDSNFromIniW((LPCWSTR)a1 + 84);
  }
  if ( *((_QWORD *)a1 + 7)
    || (v58 = *((_QWORD *)v3 + 1), (*(_BYTE *)(v58 + 312) & 1) != 0)
    || (*(_BYTE *)(v58 + 336) & 1) != 0 )
  {
    v59 = *((_QWORD *)v3 + 1);
    if ( (*(_BYTE *)(v59 + 312) & 0x20) != 0 && (*(_BYTE *)(v59 + 336) & 0x20) != 0
      || !_wcsicmp((const wchar_t *)(*(_QWORD *)(*((_QWORD *)v3 + 2) + 32LL) + *(_QWORD *)(v59 + 128)), L"(local)") )
    {
      v61 = (const WCHAR *)(*(_QWORD *)(*((_QWORD *)v3 + 2) + 32LL) + *(_QWORD *)(*((_QWORD *)v3 + 1) + 128LL));
      if ( v61 )
      {
        if ( !RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\MSSQLServer\\Client\\ConnectTo",
                0,
                0x2001Fu,
                (PHKEY)pfErrorCode) )
        {
          RegDeleteValueW(*(HKEY *)pfErrorCode, v61);
          RegCloseKey(*(HKEY *)pfErrorCode);
        }
      }
      else
      {
        RegDeleteKeyW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\MSSQLServer\\Client\\ConnectTo");
      }
    }
    else
    {
      if ( (*(_BYTE *)(*((_QWORD *)v3 + 1) + 312LL) & 0x20) != 0
        && CDlgATTRs::SetATTRValue((CDlgATTRs *)v3, 13, L"DBNETLIB") < 0
        || (*(_BYTE *)(*((_QWORD *)v3 + 1) + 336LL) & 0x20) != 0
        && (int)CDlgATTRs::CopyATTRValue((CDlgATTRs *)v3, 14, 5) < 0 )
      {
        return 21;
      }
      StringCchPrintfW(
        (unsigned __int16 *)Data,
        0x20Au,
        L"%s,%s",
        *(_QWORD *)(*((_QWORD *)v3 + 2) + 32LL) + *(_QWORD *)(*((_QWORD *)v3 + 1) + 320LL),
        *(_QWORD *)(*((_QWORD *)v3 + 2) + 32LL) + *(_QWORD *)(*((_QWORD *)v3 + 1) + 344LL));
      DrvWriteProfileString(
        (LPCWSTR)(*(_QWORD *)(*((_QWORD *)v3 + 2) + 32LL) + *(_QWORD *)(*((_QWORD *)v3 + 1) + 128LL)),
        Data,
        v60);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x38395d490  mov     [rsp+arg_10], rbx
0x38395d495  mov     [rsp+arg_18], rbp
0x38395d49a  push    rsi
0x38395d49b  push    r14
0x38395d49d  push    r15
0x38395d49f  sub     rsp, 470h
0x38395d4a6  mov     rax, cs:__security_cookie
0x38395d4ad  xor     rax, rsp
0x38395d4b0  mov     [rsp+488h+var_28], rax
0x38395d4b8  mov     rbp, [rcx+38h]
0x38395d4bc  lea     rbx, [rcx+80h]
0x38395d4c3  mov     r15d, edx
0x38395d4c6  mov     r8, [rbx+8]
0x38395d4ca  mov     rax, [rbx+10h]
0x38395d4ce  mov     r14, rcx
0x38395d4d1  mov     r9, [rax+20h]
0x38395d4d5  mov     rsi, [r8+38h]
0x38395d4d9  add     rsi, r9
0x38395d4dc  test    byte ptr [rcx+70h], 20h
0x38395d4e0  jz      short loc_38395D52D
0x38395d4e2  mov     rax, [r8+80h]
0x38395d4e9  cmp     word ptr [r9+rax], 0
0x38395d4ef  jz      short loc_38395D523
0x38395d4f1  mov     rax, [r8+158h]
0x38395d4f8  cmp     word ptr [r9+rax], 0
0x38395d4fe  jnz     short loc_38395D50A
0x38395d500  test    byte ptr [r8+150h], 20h
0x38395d508  jz      short loc_38395D523
0x38395d50a  mov     rax, [r8+140h]
0x38395d511  cmp     word ptr [r9+rax], 0
0x38395d517  jnz     short loc_38395D52D
0x38395d519  test    byte ptr [r8+138h], 20h
0x38395d521  jnz     short loc_38395D52D
0x38395d523  mov     eax, 4
0x38395d528  jmp     loc_38395DEDC
0x38395d52d  lea     rdx, szDriver; "SQL Server Native Client 11.0"
0x38395d534  mov     rcx, rsi; lpszDSN
0x38395d537  mov     [rsp+488h+arg_8], rdi
0x38395d53f  call    SQLWriteDSNToIniW
0x38395d544  xor     edi, edi
0x38395d546  test    eax, eax
0x38395d548  jnz     short loc_38395D56F
0x38395d54a  lea     ecx, [rdi+1]; iError
0x38395d54d  lea     rdx, [rsp+488h+pfErrorCode]; pfErrorCode
0x38395d552  xor     r9d, r9d; cchErrorMsgMax
0x38395d555  xor     r8d, r8d; lpszErrorMsg
0x38395d558  mov     [rsp+488h+pfErrorCode], edi
0x38395d55c  mov     [rsp+488h+pcchErrorMsg], rdi; pcchErrorMsg
0x38395d561  call    SQLInstallerErrorW
0x38395d566  mov     eax, [rsp+488h+pfErrorCode]
0x38395d56a  jmp     loc_38395DED4
0x38395d56f  test    rbp, rbp
0x38395d572  jnz     short loc_38395D57E
0x38395d574  mov     rax, [rbx+8]
0x38395d578  test    byte ptr [rax+48h], 1
0x38395d57c  jz      short loc_38395D5B5
0x38395d57e  mov     r8, [rbx+8]
0x38395d582  test    byte ptr [r8+48h], 20h
0x38395d587  jz      short loc_38395D58E
0x38395d589  mov     r8, rdi
0x38395d58c  jmp     short loc_38395D59A
0x38395d58e  mov     rax, [rbx+10h]
0x38395d592  mov     r8, [r8+50h]
0x38395d596  add     r8, [rax+20h]; lpszString
0x38395d59a  lea     r9, szFilename; "ODBC.INI"
0x38395d5a1  lea     rdx, aDescription; "Description"
0x38395d5a8  mov     rcx, rsi; lpszSection
0x38395d5ab  call    SQLWritePrivateProfileStringW
0x38395d5b0  test    rbp, rbp
0x38395d5b3  jnz     short loc_38395D5BF
0x38395d5b5  mov     rax, [rbx+8]
0x38395d5b9  test    byte ptr [rax+78h], 1
0x38395d5bd  jz      short loc_38395D5F9
0x38395d5bf  mov     r8, [rbx+8]
0x38395d5c3  test    byte ptr [r8+78h], 20h
0x38395d5c8  jz      short loc_38395D5CF
0x38395d5ca  mov     r8, rdi
0x38395d5cd  jmp     short loc_38395D5DE
0x38395d5cf  mov     rax, [rbx+10h]
0x38395d5d3  mov     r8, [r8+80h]
0x38395d5da  add     r8, [rax+20h]; lpszString
0x38395d5de  lea     r9, szFilename; "ODBC.INI"
0x38395d5e5  lea     rdx, aServer; "Server"
0x38395d5ec  mov     rcx, rsi; lpszSection
0x38395d5ef  call    SQLWritePrivateProfileStringW
0x38395d5f4  test    rbp, rbp
0x38395d5f7  jnz     short loc_38395D606
0x38395d5f9  mov     rax, [rbx+8]
0x38395d5fd  test    byte ptr [rax+258h], 1
0x38395d604  jz      short loc_38395D643
0x38395d606  mov     r8, [rbx+8]
0x38395d60a  test    byte ptr [r8+258h], 20h
0x38395d612  jz      short loc_38395D619
0x38395d614  mov     r8, rdi
0x38395d617  jmp     short loc_38395D628
0x38395d619  mov     rax, [rbx+10h]
0x38395d61d  mov     r8, [r8+260h]
0x38395d624  add     r8, [rax+20h]; lpszString
0x38395d628  lea     r9, szFilename; "ODBC.INI"
0x38395d62f  lea     rdx, aRegional; "Regional"
0x38395d636  mov     rcx, rsi; lpszSection
0x38395d639  call    SQLWritePrivateProfileStringW
0x38395d63e  test    rbp, rbp
0x38395d641  jnz     short loc_38395D650
0x38395d643  mov     rax, [rbx+8]
0x38395d647  test    byte ptr [rax+270h], 1
0x38395d64e  jz      short loc_38395D68D
0x38395d650  mov     r8, [rbx+8]
0x38395d654  test    byte ptr [r8+270h], 20h
0x38395d65c  jz      short loc_38395D663
0x38395d65e  mov     r8, rdi
0x38395d661  jmp     short loc_38395D672
0x38395d663  mov     rax, [rbx+10h]
0x38395d667  mov     r8, [r8+278h]
0x38395d66e  add     r8, [rax+20h]; lpszString
0x38395d672  lea     r9, szFilename; "ODBC.INI"
0x38395d679  lea     rdx, aQuotedid; "QuotedId"
0x38395d680  mov     rcx, rsi; lpszSection
0x38395d683  call    SQLWritePrivateProfileStringW
0x38395d688  test    rbp, rbp
0x38395d68b  jnz     short loc_38395D69A
0x38395d68d  mov     rax, [rbx+8]
0x38395d691  test    byte ptr [rax+288h], 1
0x38395d698  jz      short loc_38395D6D7
0x38395d69a  mov     r8, [rbx+8]
0x38395d69e  test    byte ptr [r8+288h], 20h
0x38395d6a6  jz      short loc_38395D6AD
0x38395d6a8  mov     r8, rdi
0x38395d6ab  jmp     short loc_38395D6BC
0x38395d6ad  mov     rax, [rbx+10h]
0x38395d6b1  mov     r8, [r8+290h]
0x38395d6b8  add     r8, [rax+20h]; lpszString
0x38395d6bc  lea     r9, szFilename; "ODBC.INI"
0x38395d6c3  lea     rdx, aAnsinpw; "AnsiNPW"
0x38395d6ca  mov     rcx, rsi; lpszSection
0x38395d6cd  call    SQLWritePrivateProfileStringW
0x38395d6d2  test    rbp, rbp
0x38395d6d5  jnz     short loc_38395D6E4
0x38395d6d7  mov     rax, [rbx+8]
0x38395d6db  test    byte ptr [rax+108h], 1
0x38395d6e2  jz      short loc_38395D721
0x38395d6e4  mov     r8, [rbx+8]
0x38395d6e8  test    byte ptr [r8+108h], 20h
0x38395d6f0  jz      short loc_38395D6F7
0x38395d6f2  mov     r8, rdi
0x38395d6f5  jmp     short loc_38395D706
0x38395d6f7  mov     rax, [rbx+10h]
0x38395d6fb  mov     r8, [r8+110h]
0x38395d702  add     r8, [rax+20h]; lpszString
0x38395d706  lea     r9, szFilename; "ODBC.INI"
0x38395d70d  lea     rdx, aDatabase; "Database"
0x38395d714  mov     rcx, rsi; lpszSection
0x38395d717  call    SQLWritePrivateProfileStringW
0x38395d71c  test    rbp, rbp
0x38395d71f  jnz     short loc_38395D72E
0x38395d721  mov     rax, [rbx+8]
0x38395d725  test    byte ptr [rax+120h], 1
0x38395d72c  jz      short loc_38395D76B
0x38395d72e  mov     r8, [rbx+8]
0x38395d732  test    byte ptr [r8+120h], 20h
0x38395d73a  jz      short loc_38395D741
0x38395d73c  mov     r8, rdi
0x38395d73f  jmp     short loc_38395D750
0x38395d741  mov     rax, [rbx+10h]
0x38395d745  mov     r8, [r8+128h]
0x38395d74c  add     r8, [rax+20h]; lpszString
0x38395d750  lea     r9, szFilename; "ODBC.INI"
0x38395d757  lea     rdx, aLanguage; "Language"
0x38395d75e  mov     rcx, rsi; lpszSection
0x38395d761  call    SQLWritePrivateProfileStringW
0x38395d766  test    rbp, rbp
0x38395d769  jnz     short loc_38395D778
0x38395d76b  mov     rax, [rbx+8]
0x38395d76f  test    byte ptr [rax+2A0h], 1
0x38395d776  jz      short loc_38395D7B5
0x38395d778  mov     r8, [rbx+8]
0x38395d77c  test    byte ptr [r8+2A0h], 20h
0x38395d784  jz      short loc_38395D78B
0x38395d786  mov     r8, rdi
0x38395d789  jmp     short loc_38395D79A
0x38395d78b  mov     rax, [rbx+10h]
0x38395d78f  mov     r8, [r8+2A8h]
0x38395d796  add     r8, [rax+20h]; lpszString
0x38395d79a  lea     r9, szFilename; "ODBC.INI"
0x38395d7a1  lea     rdx, aAttachdbfilena; "AttachDBFileName"
0x38395d7a8  mov     rcx, rsi; lpszSection
0x38395d7ab  call    SQLWritePrivateProfileStringW
0x38395d7b0  test    rbp, rbp
0x38395d7b3  jnz     short loc_38395D7C2
0x38395d7b5  mov     rax, [rbx+8]
0x38395d7b9  test    byte ptr [rax+168h], 1
0x38395d7c0  jz      short loc_38395D7FF
0x38395d7c2  mov     r8, [rbx+8]
0x38395d7c6  test    byte ptr [r8+168h], 20h
0x38395d7ce  jz      short loc_38395D7D5
0x38395d7d0  mov     r8, rdi
0x38395d7d3  jmp     short loc_38395D7E4
0x38395d7d5  mov     rax, [rbx+10h]
0x38395d7d9  mov     r8, [r8+170h]
0x38395d7e0  add     r8, [rax+20h]; lpszString
0x38395d7e4  lea     r9, szFilename; "ODBC.INI"
0x38395d7eb  lea     rdx, aEncrypt_0; "Encrypt"
0x38395d7f2  mov     rcx, rsi; lpszSection
0x38395d7f5  call    SQLWritePrivateProfileStringW
0x38395d7fa  test    rbp, rbp
0x38395d7fd  jnz     short loc_38395D80C
0x38395d7ff  mov     rax, [rbx+8]
0x38395d803  test    byte ptr [rax+180h], 1
0x38395d80a  jz      short loc_38395D849
0x38395d80c  mov     r8, [rbx+8]
0x38395d810  test    byte ptr [r8+180h], 20h
0x38395d818  jz      short loc_38395D81F
0x38395d81a  mov     r8, rdi
0x38395d81d  jmp     short loc_38395D82E
0x38395d81f  mov     rax, [rbx+10h]
0x38395d823  mov     r8, [r8+188h]
0x38395d82a  add     r8, [rax+20h]; lpszString
0x38395d82e  lea     r9, szFilename; "ODBC.INI"
0x38395d835  lea     rdx, aTrustservercer; "TrustServerCertificate"
0x38395d83c  mov     rcx, rsi; lpszSection
0x38395d83f  call    SQLWritePrivateProfileStringW
0x38395d844  test    rbp, rbp
0x38395d847  jnz     short loc_38395D856
0x38395d849  mov     rax, [rbx+8]
0x38395d84d  test    byte ptr [rax+198h], 1
0x38395d854  jz      short loc_38395D893
0x38395d856  mov     r8, [rbx+8]
0x38395d85a  test    byte ptr [r8+198h], 20h
0x38395d862  jz      short loc_38395D869
0x38395d864  mov     r8, rdi
0x38395d867  jmp     short loc_38395D878
0x38395d869  mov     rax, [rbx+10h]
0x38395d86d  mov     r8, [r8+1A0h]
0x38395d874  add     r8, [rax+20h]; lpszString
0x38395d878  lea     r9, szFilename; "ODBC.INI"
0x38395d87f  lea     rdx, aMarsConnection; "MARS_Connection"
0x38395d886  mov     rcx, rsi; lpszSection
0x38395d889  call    SQLWritePrivateProfileStringW
0x38395d88e  test    rbp, rbp
0x38395d891  jnz     short loc_38395D8A0
0x38395d893  mov     rax, [rbx+8]
0x38395d897  test    byte ptr [rax+1B0h], 1
0x38395d89e  jz      short loc_38395D8DD
0x38395d8a0  mov     r8, [rbx+8]
0x38395d8a4  test    byte ptr [r8+1B0h], 20h
0x38395d8ac  jz      short loc_38395D8B3
0x38395d8ae  mov     r8, rdi
0x38395d8b1  jmp     short loc_38395D8C2
0x38395d8b3  mov     rax, [rbx+10h]
0x38395d8b7  mov     r8, [r8+1B8h]
0x38395d8be  add     r8, [rax+20h]; lpszString
0x38395d8c2  lea     r9, szFilename; "ODBC.INI"
0x38395d8c9  lea     rdx, aFailoverPartne; "Failover_Partner"
0x38395d8d0  mov     rcx, rsi; lpszSection
0x38395d8d3  call    SQLWritePrivateProfileStringW
0x38395d8d8  test    rbp, rbp
0x38395d8db  jnz     short loc_38395D8EA
0x38395d8dd  mov     rax, [rbx+8]
0x38395d8e1  test    byte ptr [rax+2B8h], 1
0x38395d8e8  jz      short loc_38395D927
0x38395d8ea  mov     r8, [rbx+8]
0x38395d8ee  test    byte ptr [r8+2B8h], 20h
0x38395d8f6  jz      short loc_38395D8FD
0x38395d8f8  mov     r8, rdi
0x38395d8fb  jmp     short loc_38395D90C
0x38395d8fd  mov     rax, [rbx+10h]
0x38395d901  mov     r8, [r8+2C0h]
0x38395d908  add     r8, [rax+20h]; lpszString
0x38395d90c  lea     r9, szFilename; "ODBC.INI"
0x38395d913  lea     rdx, aServerspn; "ServerSPN"
0x38395d91a  mov     rcx, rsi; lpszSection
0x38395d91d  call    SQLWritePrivateProfileStringW
0x38395d922  test    rbp, rbp
0x38395d925  jnz     short loc_38395D934
0x38395d927  mov     rax, [rbx+8]
0x38395d92b  test    byte ptr [rax+2D0h], 1
0x38395d932  jz      short loc_38395D971
0x38395d934  mov     r8, [rbx+8]
0x38395d938  test    byte ptr [r8+2D0h], 20h
0x38395d940  jz      short loc_38395D947
0x38395d942  mov     r8, rdi
0x38395d945  jmp     short loc_38395D956
0x38395d947  mov     rax, [rbx+10h]
0x38395d94b  mov     r8, [r8+2D8h]
0x38395d952  add     r8, [rax+20h]; lpszString
0x38395d956  lea     r9, szFilename; "ODBC.INI"
0x38395d95d  lea     rdx, aFailoverpartne; "FailoverPartnerSPN"
0x38395d964  mov     rcx, rsi; lpszSection
0x38395d967  call    SQLWritePrivateProfileStringW
0x38395d96c  test    rbp, rbp
0x38395d96f  jnz     short loc_38395D97E
0x38395d971  mov     rax, [rbx+8]
0x38395d975  test    byte ptr [rax+2E8h], 1
0x38395d97c  jz      short loc_38395D9BB
0x38395d97e  mov     r8, [rbx+8]
0x38395d982  test    byte ptr [r8+2E8h], 20h
0x38395d98a  jz      short loc_38395D991
0x38395d98c  mov     r8, rdi
0x38395d98f  jmp     short loc_38395D9A0
0x38395d991  mov     rax, [rbx+10h]
  ... truncated ...
```
