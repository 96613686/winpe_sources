# TestDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x3839244b0`
- end: `0x3839253fd`
- name: `?TestDlgProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `3917`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `26`
- tags: `installer_update`

## callees

- `0x3838434c0`
- `0x3838435e0`
- `0x38386a2a0`
- `0x38386a450`
- `0x38386d140`
- `0x38386ff50`
- `0x383872620`
- `0x38387c938`
- `0x38389aa30`
- `0x38389d300`
- `0x3838a07e0`
- `0x3838a0b20`
- `0x3838a1ae0`
- `0x3838a3b00`
- `0x3838ba1d0`
- `0x3838ba240`
- `0x3838ba520`
- `0x38391aed0`
- `0x383920790`
- `0x3839244b0`
- `0x38395c2c0`
- `0x38395d490`
- `0x38395ee50`
- `0x383964030`
- `0x383a9ec90`
- `0x383adc1d0`

## import_xrefs

- `MSVCR100!_wtol` at `0x383924926`
- `MSVCR100!_wtol` at `0x383924926`
- `MSVCR100!_wcsicmp` at `0x3839248c7`
- `MSVCR100!_wcsicmp` at `0x3839249d7`
- `MSVCR100!_wcsicmp` at `0x383924aa3`
- `MSVCR100!_wcsicmp` at `0x383924b2f`
- `MSVCR100!_wcsicmp` at `0x383924c08`
- `MSVCR100!_wcsicmp` at `0x3839248c7`
- `MSVCR100!_wcsicmp` at `0x3839249d7`
- `MSVCR100!_wcsicmp` at `0x383924aa3`
- `MSVCR100!_wcsicmp` at `0x383924b2f`
- `MSVCR100!_wcsicmp` at `0x383924c08`
- `USER32!GetWindowLongPtrW` at `0x38392453d`
- `USER32!GetWindowLongPtrW` at `0x38392453d`
- `USER32!LoadStringW` at `0x383924608`
- `USER32!LoadStringW` at `0x3839246ba`
- `USER32!LoadStringW` at `0x38392495b`
- `USER32!LoadStringW` at `0x383924ac0`
- `USER32!LoadStringW` at `0x383924b4c`
- `USER32!LoadStringW` at `0x383924baf`
- `USER32!LoadStringW` at `0x383924f64`
- `USER32!LoadStringW` at `0x383924fb4`
- `USER32!LoadStringW` at `0x38392514b`
- `USER32!LoadStringW` at `0x383925225`
- `USER32!LoadStringW` at `0x383924608`
- `USER32!LoadStringW` at `0x3839246ba`
- `USER32!LoadStringW` at `0x38392495b`
- `USER32!LoadStringW` at `0x383924ac0`
- `USER32!LoadStringW` at `0x383924b4c`
- `USER32!LoadStringW` at `0x383924baf`
- `USER32!LoadStringW` at `0x383924f64`
- `USER32!LoadStringW` at `0x383924fb4`
- `USER32!LoadStringW` at `0x38392514b`
- `USER32!LoadStringW` at `0x383925225`
- `USER32!UpdateWindow` at `0x383925337`
- `USER32!UpdateWindow` at `0x383925337`
- `USER32!SetWindowTextW` at `0x383925319`
- `USER32!SetWindowTextW` at `0x383925319`
- `USER32!GetDlgItem` at `0x38392454e`
- `USER32!GetDlgItem` at `0x383924730`
- `USER32!GetDlgItem` at `0x383924746`
- `USER32!GetDlgItem` at `0x3839253c5`
- `USER32!GetDlgItem` at `0x38392454e`
- `USER32!GetDlgItem` at `0x383924730`
- `USER32!GetDlgItem` at `0x383924746`
- `USER32!GetDlgItem` at `0x3839253c5`
- `USER32!PostMessageW` at `0x3839252ec`
- `USER32!PostMessageW` at `0x3839253e4`
- `USER32!PostMessageW` at `0x3839252ec`
- `USER32!PostMessageW` at `0x3839253e4`
- `USER32!SetFocus` at `0x38392474f`
- `USER32!SetFocus` at `0x38392474f`
- `USER32!SetWindowLongPtrW` at `0x383924707`
- `USER32!SetWindowLongPtrW` at `0x3839253ad`
- `USER32!SetWindowLongPtrW` at `0x383924707`
- `USER32!SetWindowLongPtrW` at `0x3839253ad`
- `USER32!EnableWindow` at `0x38392473b`
- `USER32!EnableWindow` at `0x3839253d0`
- `USER32!EnableWindow` at `0x38392473b`
- `USER32!EnableWindow` at `0x3839253d0`
- `USER32!ShowWindow` at `0x3839253f0`
- `USER32!ShowWindow` at `0x3839253f0`
- `USER32!PostMessageA` at `0x38392532e`
- `USER32!PostMessageA` at `0x38392532e`
- `USER32!EndDialog` at `0x38392538e`
- `USER32!EndDialog` at `0x38392538e`

## string_xrefs

- `0x383924d4f`: `SQLServerDriver##TEMPDSN`
- `0x383924d5b`: `SQLServerDriver##TEMPDSN`
- `0x383924ff6`: `SQLServerDriver##TEMPDSN`

## pseudocode

```c
INT_PTR __fastcall TestDlgProc(HWND a1, int a2, __int64 a3, LONG_PTR a4)
{
  __int64 v4; // rbx
  HWND v6; // r12
  int v7; // edx
  int v8; // edx
  HWND WindowLongPtrW; // rdi
  unsigned int StringW; // eax
  _QWORD *v12; // rcx
  void *v13; // rbx
  unsigned int v14; // eax
  HWND v15; // rax
  HWND v16; // rax
  __int64 v17; // rax
  struct tagSTMT *v18; // rbx
  SQLRETURN v19; // r13
  SQLSMALLINT v20; // r13
  __int64 v21; // rdx
  WCHAR *v22; // rcx
  WCHAR v23; // ax
  unsigned int v24; // eax
  __int64 v25; // rax
  WCHAR *v26; // r8
  unsigned int FormattedMessage; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  UINT v30; // edx
  unsigned int v31; // eax
  __int64 v32; // rcx
  unsigned int v33; // eax
  LPARAM v34; // r9
  __int64 v35; // rax
  __int64 v36; // r8
  _WORD *v37; // rdx
  _WORD *v38; // rcx
  WPARAM v39; // r8
  SQLHENV v40; // r15
  SQLHENV v41; // rcx
  __int64 v42; // rax
  SQLSMALLINT v43; // r13
  unsigned int v44; // eax
  unsigned int v45; // eax
  __int64 v46; // r9
  unsigned int v47; // eax
  unsigned int v48; // eax
  HWND v49; // rbx
  HWND DlgItem; // rax
  unsigned __int16 *BufferLength; // [rsp+28h] [rbp-E0h]
  SQLLEN BufferLengtha; // [rsp+28h] [rbp-E0h]
  SQLSMALLINT pcbStringLength[2]; // [rsp+48h] [rbp-C0h] BYREF
  SQLSMALLINT pcchErrorMsg[2]; // [rsp+4Ch] [rbp-BCh] BYREF
  unsigned __int16 v55[2]; // [rsp+50h] [rbp-B8h] BYREF
  unsigned __int16 v56; // [rsp+54h] [rbp-B4h] BYREF
  struct HINSTANCE__ v57[2]; // [rsp+58h] [rbp-B0h] BYREF
  HWND v58; // [rsp+60h] [rbp-A8h]
  SQLHENV EnvironmentHandle; // [rsp+68h] [rbp-A0h] BYREF
  HWND hWnd; // [rsp+70h] [rbp-98h]
  LONG_PTR v61; // [rsp+78h] [rbp-90h]
  SQLWCHAR szSqlState[12]; // [rsp+80h] [rbp-88h] BYREF
  WCHAR Buffer[776]; // [rsp+98h] [rbp-70h] BYREF

  v4 = a3;
  v61 = a4;
  v6 = a1;
  v58 = a1;
  *(_QWORD *)szSqlState = a3;
  v7 = a2 - 272;
  if ( !v7 )
  {
    SetWindowLongPtrW(a1, -21, a4);
    CenterDialog(v6);
    DlgItem = GetDlgItem(v6, 1);
    EnableWindow(DlgItem, 0);
    PostMessageW(v6, 0x801u, 0, 0);
    ShowWindow(v6, 5);
    return 1;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    if ( (unsigned int)(unsigned __int16)a3 - 1 <= 1 )
    {
      EndDialog(a1, (_WORD)a3 == 1);
      return 1;
    }
    return 0;
  }
  if ( v8 != 1776 )
    return 0;
  memset(Buffer, 0, 1544);
  WindowLongPtrW = (HWND)GetWindowLongPtrW(a1, -21);
  hWnd = GetDlgItem(v6, 30700);
  if ( !*((_QWORD *)WindowLongPtrW + 15)
    && CreateExtBufferEx(
         (struct tagOBJBASE *)WindowLongPtrW,
         (struct ext_buffer **)WindowLongPtrW + 15,
         0xFA0u,
         0x200u,
         1) )
  {
    return 0;
  }
  if ( a4 )
  {
    if ( a4 != 1 )
    {
      if ( a4 != 2 )
      {
        if ( a4 == 3 )
        {
          if ( ((_BYTE)WindowLongPtrW[28] & 4) != 0 )
          {
            StringW = LoadStringW(g_hinstance_language, 0x9C6Au, Buffer, 772);
            WriteToExtBufferEx(
              (struct tagOBJBASE *)WindowLongPtrW,
              (struct ext_buffer **)WindowLongPtrW + 15,
              Buffer,
              2LL * StringW,
              1);
            WriteToExtBufferEx(
              (struct tagOBJBASE *)WindowLongPtrW,
              (struct ext_buffer **)WindowLongPtrW + 15,
              L"\r\n",
              4,
              1);
            SQLDisconnect(*((SQLHDBC *)WindowLongPtrW + 8));
            *((_WORD *)WindowLongPtrW + 56) &= ~4u;
          }
          v12 = (_QWORD *)*((_QWORD *)WindowLongPtrW + 8);
          if ( v12 )
          {
            v13 = (void *)v12[1002];
            SQLFreeConnect(v12);
            *((_QWORD *)WindowLongPtrW + 8) = 0;
            SQLFreeEnv(v13);
            v4 = *(_QWORD *)szSqlState;
          }
          WriteToExtBufferEx(
            (struct tagOBJBASE *)WindowLongPtrW,
            (struct ext_buffer **)WindowLongPtrW + 15,
            L"\r\n",
            4,
            1);
          v14 = LoadStringW(g_hinstance_language, (v4 == -1) + 40043, Buffer, 772);
          WriteToExtBufferEx(
            (struct tagOBJBASE *)WindowLongPtrW,
            (struct ext_buffer **)WindowLongPtrW + 15,
            Buffer,
            2LL * v14,
            1);
          *((_QWORD *)WindowLongPtrW + 8) = *((_QWORD *)WindowLongPtrW + 9);
          if ( CDlgATTRs::SetATTRValue(
                 (CDlgATTRs *)(WindowLongPtrW + 32),
                 2,
                 (const unsigned __int16 *)WindowLongPtrW + 117) >= 0 )
          {
            *((_WORD *)WindowLongPtrW + 56) ^= ((unsigned __int8)*((_WORD *)WindowLongPtrW + 56)
                                              ^ (unsigned __int8)(*((_WORD *)WindowLongPtrW + 56) >> 4))
                                             & 0x20;
            v15 = GetDlgItem(v6, 1);
            EnableWindow(v15, 1);
            v16 = GetDlgItem(v6, 1);
            SetFocus(v16);
          }
          else
          {
            SetWindowLongPtrW(v6, 0, -1);
          }
        }
        goto LABEL_114;
      }
      if ( v4 != -1 )
      {
        v17 = *((_QWORD *)WindowLongPtrW + 8);
        v18 = *(struct tagSTMT **)(v17 + 8024);
        v19 = ExecImmediate(
                v18,
                L"select name from sys.syscharsets where id = convert(tinyint, databasepropertyex ( db_name() , 'sqlcharset'))",
                -3,
                *(_DWORD *)(v17 + 9000),
                1);
        if ( (v19 & 0xFFFE) == 0 )
        {
          v19 = SQLFetch(v18);
          if ( !v19 )
            v19 = SQLGetData(v18, 1u, -8, Buffer, 1544, 0);
          Cancel(v18, 0);
        }
        if ( v19 == -1 )
        {
          v20 = 1;
          if ( !SQLGetDiagFieldW(3, v18, 1, 6, Buffer, 1540, pcbStringLength) )
          {
            do
            {
              WriteToExtBufferEx(
                (struct tagOBJBASE *)WindowLongPtrW,
                (struct ext_buffer **)WindowLongPtrW + 15,
                Buffer,
                pcbStringLength[0],
                1);
              WriteToExtBufferEx(
                (struct tagOBJBASE *)WindowLongPtrW,
                (struct ext_buffer **)WindowLongPtrW + 15,
                L"\r\n",
                4,
                1);
              ++v20;
            }
            while ( !SQLGetDiagFieldW(3, v18, v20, 6, Buffer, 1540, pcbStringLength) );
            v6 = v58;
          }
          v4 = -1;
        }
        else
        {
          if ( !_wcsicmp(Buffer, L"ISO_1") )
          {
            v21 = 772;
            v22 = Buffer;
            while ( v21 != -2147482874 )
            {
              v23 = *(WCHAR *)((char *)v22 + (char *)L"cp1252" - (char *)Buffer);
              if ( !v23 )
                break;
              *v22++ = v23;
              if ( !--v21 )
              {
                --v22;
                break;
              }
            }
            *v22 = 0;
          }
          if ( _wtol(&Buffer[2]) != *(_DWORD *)(*((_QWORD *)WindowLongPtrW + 8) + 10060LL)
            && (*(_BYTE *)(*((_QWORD *)WindowLongPtrW + 17) + 456LL) & 0x20) == 0 )
          {
            v24 = LoadStringW(g_hinstance_language, 0x9C72u, Buffer, 772);
            WriteToExtBufferEx(
              (struct tagOBJBASE *)WindowLongPtrW,
              (struct ext_buffer **)WindowLongPtrW + 15,
              Buffer,
              2LL * v24,
              1);
            WriteToExtBufferEx(
              (struct tagOBJBASE *)WindowLongPtrW,
              (struct ext_buffer **)WindowLongPtrW + 15,
              L"\r\n",
              4,
              1);
          }
          v4 = *(_QWORD *)szSqlState;
        }
        v25 = *((_QWORD *)WindowLongPtrW + 17);
        if ( (*(_BYTE *)(v25 + 312) & 1) != 0 && (*(_BYTE *)(v25 + 336) & 1) != 0 )
        {
          if ( _wcsicmp(
                 (const wchar_t *)(*(_QWORD *)(*((_QWORD *)WindowLongPtrW + 18) + 32LL) + *(_QWORD *)(v25 + 320)),
                 L"DBNETLIB") )
          {
            v26 = (WCHAR *)(*(_QWORD *)(*((_QWORD *)WindowLongPtrW + 18) + 32LL)
                          + *(_QWORD *)(*((_QWORD *)WindowLongPtrW + 17) + 320LL));
          }
          else
          {
            v26 = &::Buffer;
          }
          FormattedMessage = LoadFormattedMessage(
                               g_hinstance_language,
                               0x9C74u,
                               Buffer,
                               0x304u,
                               v26,
                               *(_QWORD *)(*((_QWORD *)WindowLongPtrW + 18) + 32LL)
                             + *(_QWORD *)(*((_QWORD *)WindowLongPtrW + 17) + 344LL));
          WriteToExtBufferEx(
            (struct tagOBJBASE *)WindowLongPtrW,
            (struct ext_buffer **)WindowLongPtrW + 15,
            Buffer,
            2LL * FormattedMessage,
            1);
          WriteToExtBufferEx(
            (struct tagOBJBASE *)WindowLongPtrW,
            (struct ext_buffer **)WindowLongPtrW + 15,
            L"\r\n",
            4,
            1);
        }
        if ( !*(_QWORD *)(*((_QWORD *)WindowLongPtrW + 8) + 8392LL)
          && !_wcsicmp(
                (const wchar_t *)(*(_QWORD *)(*((_QWORD *)WindowLongPtrW + 18) + 32LL)
                                + *(_QWORD *)(*((_QWORD *)WindowLongPtrW + 17) + 416LL)),
                L"Yes") )
        {
          v28 = LoadStringW(g_hinstance_language, 0x9C75u, Buffer, 772);
          WriteToExtBufferEx(
            (struct tagOBJBASE *)WindowLongPtrW,
            (struct ext_buffer **)WindowLongPtrW + 15,
            Buffer,
            2LL * v28,
            1);
          WriteToExtBufferEx(
            (struct tagOBJBASE *)WindowLongPtrW,
            (struct ext_buffer **)WindowLongPtrW + 15,
            L"\r\n",
            4,
            1);
        }
        if ( *(_QWORD *)(*((_QWORD *)WindowLongPtrW + 8) + 8384LL) )
        {
          if ( !_wcsicmp(
                  (const wchar_t *)(*(_QWORD *)(*((_QWORD *)WindowLongPtrW + 18) + 32LL)
                                  + *(_QWORD *)(*((_QWORD *)WindowLongPtrW + 17) + 368LL)),
                  L"No") )
          {
            v29 = LoadStringW(g_hinstance_language, 0x9C76u, Buffer, 772);
            WriteToExtBufferEx(
              (struct tagOBJBASE *)WindowLongPtrW,
              (struct ext_buffer **)WindowLongPtrW + 15,
              Buffer,
              2LL * v29,
              1);
            WriteToExtBufferEx(
              (struct tagOBJBASE *)WindowLongPtrW,
              (struct ext_buffer **)WindowLongPtrW + 15,
              L"\r\n",
              4,
              1);
          }
          v30 = 40056;
          if ( *(_QWORD *)(*((_QWORD *)WindowLongPtrW + 8) + 8424LL) )
            v30 = 40055;
          v31 = LoadStringW(g_hinstance_language, v30, Buffer, 772);
          WriteToExtBufferEx(
            (struct tagOBJBASE *)WindowLongPtrW,
            (struct ext_buffer **)WindowLongPtrW + 15,
            Buffer,
            2LL * v31,
            1);
          WriteToExtBufferEx(
            (struct tagOBJBASE *)WindowLongPtrW,
            (struct ext_buffer **)WindowLongPtrW + 15,
            L"\r\n",
            4,
            1);
        }
        v32 = *((_QWORD *)WindowLongPtrW + 8);
        if ( *(_QWORD *)(v32 + 8400) && _wcsicmp(*(const wchar_t **)(v32 + 8400), (const wchar_t *)(v32 + 4338)) )
        {
          v33 = LoadFormattedMessage(
                  g_hinstance_language,
                  0x9C79u,
                  Buffer,
                  0x304u,
                  *((_QWORD *)WindowLongPtrW + 8) + 4338LL);
          WriteToExtBufferEx(
            (struct tagOBJBASE *)WindowLongPtrW,
            (struct ext_buffer **)WindowLongPtrW + 15,
            Buffer,
            2LL * v33,
            1);
          WriteToExtBufferEx(
            (struct tagOBJBASE *)WindowLongPtrW,
            (struct ext_buffer **)WindowLongPtrW + 15,
            L"\r\n",
            4,
            1);
        }
      }
      v34 = 3;
      goto LABEL_112;
    }
    v35 = *((_QWORD *)WindowLongPtrW + 8);
    *((_QWORD *)WindowLongPtrW + 8) = 0;
    v36 = 641;
    *((_QWORD *)WindowLongPtrW + 9) = v35;
    v37 = (_WORD *)(*(_QWORD *)(*((_QWORD *)WindowLongPtrW + 18) + 32LL)
                  + *(_QWORD *)(*((_QWORD *)WindowLongPtrW + 17) + 56LL));
    v38 = (_WORD *)WindowLongPtrW + 117;
    while ( v36 != -2147483005 && *v37 )
    {
      *v38++ = *v37++;
      if ( !--v36 )
      {
        --v38;
        break;
      }
    }
    *v38 = 0;
    *((_WORD *)WindowLongPtrW + 56) ^= (*((_WORD *)WindowLongPtrW + 56)
                                      ^ (16 * *((_WORD *)WindowLongPtrW + 56)))
                                     & 0x200;
    if ( SQLAllocEnv(&EnvironmentHandle) )
    {
      v34 = 3;
      v39 = -1;
LABEL_113:
      PostMessageW(v6, 0x801u, v39, v34);
      goto LABEL_114;
    }
    v40 = EnvironmentHandle;
    v41 = EnvironmentHandle;
    *((_QWORD *)EnvironmentHandle + 8) = 3;
    if ( SQLAllocConnect(v41, (SQLHDBC *)WindowLongPtrW + 8) )
    {
      SQLFreeEnv(v40);
      v34 = 3;
      v39 = -1;
      goto LABEL_113;
    }
    SQLRemoveDSNFromIniW(L"SQLServerDriver##TEMPDSN");
    if ( CDlgATTRs::SetATTRValue((CDlgATTRs *)(WindowLongPtrW + 32), 2, L"SQLServerDriver##TEMPDSN") < 0 )
    {
      v34 = 3;
      v39 = -1;
      goto LABEL_113;
    }
    v42 = *((_QWORD *)WindowLongPtrW + 17);
    *((_WORD *)WindowLongPtrW + 56) |= 0x20u;
    *(_WORD *)(v42 + 264) &= ~4u;
    *(_WORD *)(*((_QWORD *)WindowLongPtrW + 17) + 288LL) &= ~4u;
    if ( (*(_BYTE *)(*((_QWORD *)WindowLongPtrW + 17) + 96LL) & 1) == 0
      && CDlgATTRs::SetATTRValue((CDlgATTRs *)(WindowLongPtrW + 32), 4, L"SQL Server Native Client 11.0") < 0 )
    {
      v34 = 3;
      v39 = -1;
      goto LABEL_113;
    }
    SaveDSNAttributes(WindowLongPtrW, (struct tagDLGSTRUCT *)1);
    *(_WORD *)(*((_QWORD *)WindowLongPtrW + 8) + 10112LL) &= ~2u;
    if ( (*(_BYTE *)(*((_QWORD *)WindowLongPtrW + 17) + 456LL) & 0x20) != 0 )
      *(_WORD *)(*((_QWORD *)WindowLongPtrW + 8) + 10112LL) |= 2u;
    SyncConnAttrWithKeyVal(*((struct tagDBC **)WindowLongPtrW + 8), (struct CDlgATTRs *)(WindowLongPtrW + 32));
    *(_QWORD *)(*((_QWORD *)WindowLongPtrW + 8) + 8072LL) = 15;
    *(_DWORD *)(*((_QWORD *)WindowLongPtrW + 8) + 9004LL) = 15000;
    if ( DoDlgConnection(v6, (struct tagDLGSTRUCT *)WindowLongPtrW, 7u) == -1 )
    {
      v43 = 1;
      if ( !SQLGetDiagRecW(2, *((SQLHANDLE *)WindowLongPtrW + 8), 1, szSqlState, 0, Buffer, 772, pcchErrorMsg) )
      {
        do
        {
          if ( szSqlState[0] != 48 || szSqlState[1] != 49 )
          {
            WriteToExtBufferEx(
              (struct tagOBJBASE *)WindowLongPtrW,
              (struct ext_buffer **)WindowLongPtrW + 15,
              Buffer,
              2LL * pcchErrorMsg[0],
              1);
            WriteToExtBufferEx(
              (struct tagOBJBASE *)WindowLongPtrW,
              (struct ext_buffer **)WindowLongPtrW + 15,
              L"\r\n",
              4,
              1);
          }
          ++v43;
        }
        while ( !SQLGetDiagRecW(2, *((SQLHANDLE *)WindowLongPtrW + 8), v43, szSqlState, 0, Buffer, 772, pcchErrorMsg) );
        v6 = v58;
      }
      v4 = -1;
    }
    else
    {
      v44 = LoadStringW(g_hinstance_language, 0x9C68u, Buffer, 772);
      WriteToExtBufferEx(
        (struct tagOBJBASE *)WindowLongPtrW,
        (struct ext_buffer **)WindowLongPtrW + 15,
        Buffer,
        2LL * v44,
        1);
      WriteToExtBufferEx((struct tagOBJBASE *)WindowLongPtrW, (struct ext_buffer **)WindowLongPtrW + 15, L"\r\n", 4, 1);
      v45 = LoadStringW(g_hinstance_language, 0x9C69u, Buffer, 772);
      WriteToExtBufferEx(
        (struct tagOBJBASE *)WindowLongPtrW,
        (struct ext_buffer **)WindowLongPtrW + 15,
        Buffer,
        2LL * v45,
        1);
      WriteToExtBufferEx((struct tagOBJBASE *)WindowLongPtrW, (struct ext_buffer **)WindowLongPtrW + 15, L"\r\n", 4, 1);
      v4 = *(_QWORD *)szSqlState;
    }
    SQLRemoveDSNFromIniW(L"SQLServerDriver##TEMPDSN");
    v34 = 2;
LABEL_112:
    v39 = v4;
    goto LABEL_113;
  }
  if ( ReadVersion(v57, &v56, v55, (unsigned __int16 *)&v57[1], BufferLength) )
    goto LABEL_95;
  LODWORD(BufferLengtha) = LOWORD(v57[0].unused);
  LoadFormattedMessage(g_hinstance_language, 0x9C62u, Buffer, 0x304u, BufferLengtha, v56, v55[0]);
  v46 = -1;
  do
    ++v46;
  while ( Buffer[v46] );
  if ( WriteToExtBufferEx(
         (struct tagOBJBASE *)WindowLongPtrW,
         (struct ext_buffer **)WindowLongPtrW + 15,
         Buffer,
         2 * v46,
         1) )
  {
    if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
      bidTraceW(off_383B431B8[0], 3835913, off_383B49120[0], 3746);
    goto LABEL_114;
  }
  if ( !WriteToExtBufferEx(
          (struct tagOBJBASE *)WindowLongPtrW,
          (struct ext_buffer **)WindowLongPtrW + 15,
          L"\r\n\r\n",
          8,
          1) )
  {
LABEL_95:
    v47 = LoadStringW(g_hinstance_language, 0x9C66u, Buffer, 772);
    if ( WriteToExtBufferEx(
           (struct tagOBJBASE *)WindowLongPtrW,
           (struct ext_buffer **)WindowLongPtrW + 15,
           Buffer,
           2LL * v47,
           1) )
    {
      if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
        bidTraceW(off_383B431B8[0], 3844105, off_383B49120[0], 3754);
    }
    else if ( WriteToExtBufferEx(
                (struct tagOBJBASE *)WindowLongPtrW,
                (struct ext_buffer **)WindowLongPtrW + 15,
                L"\r\n\r\n",
                8,
                1) )
    {
      if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
        bidTraceW(off_383B431B8[0], 3847177, off_383B49120[0], 3757);
    }
    else
    {
      v48 = LoadStringW(g_hinstance_language, 0x9C67u, Buffer, 772);
      if ( WriteToExtBufferEx(
             (struct tagOBJBASE *)WindowLongPtrW,
             (struct ext_buffer **)WindowLongPtrW + 15,
             Buffer,
             2LL * v48,
             1) )
      {
        if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
          bidTraceW(off_383B431B8[0], 3851273, off_383B49120[0], 3761);
      }
      else
      {
        if ( !WriteToExtBufferEx(
                (struct tagOBJBASE *)WindowLongPtrW,
                (struct ext_buffer **)WindowLongPtrW + 15,
                L"\r\n",
                4,
                1) )
        {
          v34 = 1;
          goto LABEL_112;
        }
        if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
          bidTraceW(off_383B431B8[0], 3854345, off_383B49120[0], 3764);
      }
    }
  }
  else if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
  {
    bidTraceW(off_383B431B8[0], 3838985, off_383B49120[0], 3749);
  }
LABEL_114:
  if ( WriteCharToExtBufferEx(
         (struct tagOBJBASE *)WindowLongPtrW,
         (struct ext_buffer **)WindowLongPtrW + 15,
         0,
         1u,
         (int)BufferLength) )
  {
    return 1;
  }
  v49 = hWnd;
  SetWindowTextW(hWnd, (LPCWSTR)(*((_QWORD *)WindowLongPtrW + 15) + 24LL));
  PostMessageA(v49, 0xB1u, 0xFFFFFFFFFFFFFFFFuLL, -1);
  UpdateWindow(v49);
  if ( v61 != 3 )
  {
    *(_QWORD *)(*((_QWORD *)WindowLongPtrW + 15) + 8LL) -= 2LL;
    return 1;
  }
  if ( *((_QWORD *)WindowLongPtrW + 15) )
    ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
  *((_QWORD *)WindowLongPtrW + 15) = 0;
  return 1;
}

```

## disassembly

```asm
0x3839244b0  mov     r11, rsp
0x3839244b3  push    rbp
0x3839244b4  push    rbx
0x3839244b5  push    rsi
0x3839244b6  push    r12
0x3839244b8  push    r15
0x3839244ba  lea     rbp, [r11-5E8h]
0x3839244c1  sub     rsp, 6C0h
0x3839244c8  mov     rax, cs:__security_cookie
0x3839244cf  xor     rax, rsp
0x3839244d2  mov     [rbp+5E0h+var_40], rax
0x3839244d9  mov     rbx, r8
0x3839244dc  mov     r15, r9
0x3839244df  mov     [rsp+6E0h+var_670], r9
0x3839244e4  mov     r12, rcx
0x3839244e7  mov     [rsp+6E0h+var_688], rcx
0x3839244ec  mov     qword ptr [rsp+6E0h+szSqlState], rbx
0x3839244f1  sub     edx, 110h
0x3839244f7  jz      loc_3839253A5
0x3839244fd  dec     edx
0x3839244ff  jz      loc_383925378
0x383924505  cmp     edx, 6F0h
0x38392450b  jnz     loc_38392539E
0x383924511  mov     [r11+10h], rdi
0x383924515  mov     [r11-30h], r13
0x383924519  lea     rcx, [rbp+5E0h+var_64E]; void *
0x38392451d  xor     r13d, r13d
0x383924520  xor     edx, edx; Val
0x383924522  mov     r8d, 606h; Size
0x383924528  mov     [rbp+5E0h+Buffer], r13w
0x38392452d  mov     [r11-38h], r14
0x383924531  call    memset
0x383924536  lea     edx, [r13-15h]; nIndex
0x38392453a  mov     rcx, r12; hWnd
0x38392453d  call    cs:__imp_GetWindowLongPtrW
0x383924543  mov     edx, 77ECh; nIDDlgItem
0x383924548  mov     rcx, r12; hDlg
0x38392454b  mov     rdi, rax
0x38392454e  call    cs:__imp_GetDlgItem
0x383924554  lea     esi, [r13+1]
0x383924558  mov     r9d, 200h; unsigned __int64
0x38392455e  mov     [rsp+6E0h+hWnd], rax
0x383924563  cmp     [rdi+78h], r13
0x383924567  jnz     short loc_3839245C2
0x383924569  lea     rdx, [rdi+78h]; struct ext_buffer **
0x38392456d  mov     r8d, 0FA0h; unsigned __int64
0x383924573  mov     rcx, rdi; struct tagOBJBASE *
0x383924576  mov     dword ptr [rsp+6E0h+BufferLength], esi; unsigned __int16 *
0x38392457a  call    ?CreateExtBufferEx@@YAFPEAUtagOBJBASE@@PEAPEAUext_buffer@@_K2H@Z; CreateExtBufferEx(tagOBJBASE *,ext_buffer * *,unsigned __int64,unsigned __int64,int)
0x38392457f  test    ax, ax
0x383924582  jz      short loc_3839245BC
0x383924584  xor     eax, eax
0x383924586  mov     r13, [rsp+6B8h]
0x38392458e  mov     rdi, [rsp+6E0h+arg_8]
0x383924596  mov     r14, [rsp+6E0h+var_30]
0x38392459e  mov     rcx, [rbp+5E0h+var_40]
0x3839245a5  xor     rcx, rsp; StackCookie
0x3839245a8  call    __security_check_cookie
0x3839245ad  add     rsp, 6C0h
0x3839245b4  pop     r15
0x3839245b6  pop     r12
0x3839245b8  pop     rsi
0x3839245b9  pop     rbx
0x3839245ba  pop     rbp
0x3839245bb  retn
0x3839245bc  mov     r9d, 200h
0x3839245c2  mov     rax, r15
0x3839245c5  test    r15, r15
0x3839245c8  jz      loc_38392500D
0x3839245ce  dec     rax
0x3839245d1  jz      loc_383924C7E
0x3839245d7  dec     rax
0x3839245da  jz      loc_38392475A
0x3839245e0  dec     rax
0x3839245e3  jnz     loc_3839252F2
0x3839245e9  test    byte ptr [rdi+70h], 4
0x3839245ed  mov     r15d, 304h
0x3839245f3  jz      short loc_383924659
0x3839245f5  mov     rcx, cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA; hInstance
0x3839245fc  lea     r8, [rbp+5E0h+Buffer]; lpBuffer
0x383924600  mov     r9d, r15d; cchBufferMax
0x383924603  mov     edx, 9C6Ah; uID
0x383924608  call    cs:__imp_LoadStringW
0x38392460e  lea     r8, [rbp+5E0h+Buffer]; void *
0x383924612  lea     rdx, [rdi+78h]; struct ext_buffer **
0x383924616  mov     r9d, eax
0x383924619  mov     rcx, rdi; struct tagOBJBASE *
0x38392461c  mov     dword ptr [rsp+6E0h+BufferLength], esi; int
0x383924620  add     r9, r9; __int64
0x383924623  call    ?WriteToExtBufferEx@@YAFPEAUtagOBJBASE@@PEAPEAUext_buffer@@PEBX_JH@Z; WriteToExtBufferEx(tagOBJBASE *,ext_buffer * *,void const *,__int64,int)
0x383924628  lea     r8, asc_383915954; "\r\n"
0x38392462f  lea     rdx, [rdi+78h]; struct ext_buffer **
0x383924633  mov     r9d, 4; __int64
0x383924639  mov     rcx, rdi; struct tagOBJBASE *
0x38392463c  mov     dword ptr [rsp+6E0h+BufferLength], esi; int
0x383924640  call    ?WriteToExtBufferEx@@YAFPEAUtagOBJBASE@@PEAPEAUext_buffer@@PEBX_JH@Z; WriteToExtBufferEx(tagOBJBASE *,ext_buffer * *,void const *,__int64,int)
0x383924645  mov     rcx, [rdi+40h]; ConnectionHandle
0x383924649  call    SQLDisconnect
0x38392464e  mov     r11d, 0FFFBh
0x383924654  and     [rdi+70h], r11w
0x383924659  mov     rcx, [rdi+40h]; ConnectionHandle
0x38392465d  test    rcx, rcx
0x383924660  jz      short loc_38392467F
0x383924662  mov     rbx, [rcx+1F50h]
0x383924669  call    SQLFreeConnect
0x38392466e  mov     rcx, rbx; EnvironmentHandle
0x383924671  mov     [rdi+40h], r13
0x383924675  call    SQLFreeEnv
0x38392467a  mov     rbx, qword ptr [rsp+6E0h+szSqlState]
0x38392467f  lea     r8, asc_383915954; "\r\n"
0x383924686  lea     rdx, [rdi+78h]; struct ext_buffer **
0x38392468a  mov     r9d, 4; __int64
0x383924690  mov     rcx, rdi; struct tagOBJBASE *
0x383924693  mov     dword ptr [rsp+6E0h+BufferLength], esi; int
0x383924697  call    ?WriteToExtBufferEx@@YAFPEAUtagOBJBASE@@PEAPEAUext_buffer@@PEBX_JH@Z; WriteToExtBufferEx(tagOBJBASE *,ext_buffer * *,void const *,__int64,int)
0x38392469c  mov     rcx, cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA; hInstance
0x3839246a3  mov     edx, r13d
0x3839246a6  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x3839246aa  lea     r8, [rbp+5E0h+Buffer]; lpBuffer
0x3839246ae  mov     r9d, r15d; cchBufferMax
0x3839246b1  setz    dl
0x3839246b4  add     edx, 9C6Bh; uID
0x3839246ba  call    cs:__imp_LoadStringW
0x3839246c0  lea     r8, [rbp+5E0h+Buffer]; void *
0x3839246c4  lea     rdx, [rdi+78h]; struct ext_buffer **
0x3839246c8  mov     r9d, eax
0x3839246cb  mov     rcx, rdi; struct tagOBJBASE *
0x3839246ce  mov     dword ptr [rsp+6E0h+BufferLength], esi; int
0x3839246d2  add     r9, r9; __int64
0x3839246d5  call    ?WriteToExtBufferEx@@YAFPEAUtagOBJBASE@@PEAPEAUext_buffer@@PEBX_JH@Z; WriteToExtBufferEx(tagOBJBASE *,ext_buffer * *,void const *,__int64,int)
0x3839246da  mov     r11, [rdi+48h]
0x3839246de  lea     rcx, [rdi+80h]; this
0x3839246e5  lea     r8, [rdi+0EAh]; unsigned __int16 *
0x3839246ec  mov     edx, 2; int
0x3839246f1  mov     [rdi+40h], r11
0x3839246f5  call    ?SetATTRValue@CDlgATTRs@@QEAAJHPEBG@Z; CDlgATTRs::SetATTRValue(int,ushort const *)
0x3839246fa  test    eax, eax
0x3839246fc  jns     short loc_383924712
0x3839246fe  or      r8, 0FFFFFFFFFFFFFFFFh; dwNewLong
0x383924702  xor     edx, edx; nIndex
0x383924704  mov     rcx, r12; hWnd
0x383924707  call    cs:__imp_SetWindowLongPtrW
0x38392470d  jmp     loc_3839252F2
0x383924712  movzx   eax, word ptr [rdi+70h]
0x383924716  mov     edx, esi; nIDDlgItem
0x383924718  movzx   ecx, ax
0x38392471b  shr     cx, 4
0x38392471f  xor     cx, ax
0x383924722  and     cx, 20h
0x383924726  xor     cx, ax
0x383924729  mov     [rdi+70h], cx
0x38392472d  mov     rcx, r12; hDlg
0x383924730  call    cs:__imp_GetDlgItem
0x383924736  mov     edx, esi; bEnable
0x383924738  mov     rcx, rax; hWnd
0x38392473b  call    cs:__imp_EnableWindow
0x383924741  mov     edx, esi; nIDDlgItem
0x383924743  mov     rcx, r12; hDlg
0x383924746  call    cs:__imp_GetDlgItem
0x38392474c  mov     rcx, rax; hWnd
0x38392474f  call    cs:__imp_SetFocus
0x383924755  jmp     loc_3839252F2
0x38392475a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x38392475e  jz      loc_383924C73
0x383924764  mov     rax, [rdi+40h]
0x383924768  lea     rdx, aSelectNameFrom_0; "select name from sys.syscharsets where "...
0x38392476f  mov     r8d, 0FFFFFFFDh; int
0x383924775  mov     rbx, [rax+1F58h]
0x38392477c  mov     r9d, [rax+2328h]; unsigned int
0x383924783  mov     dword ptr [rsp+6E0h+BufferLength], esi; int
0x383924787  mov     rcx, rbx; struct tagSTMT *
0x38392478a  call    ?ExecImmediate@@YAFPEAUtagSTMT@@PEBGJKH@Z; ExecImmediate(tagSTMT *,ushort const *,long,ulong,int)
0x38392478f  movzx   r13d, ax
0x383924793  mov     eax, 0FFFEh
0x383924798  test    ax, r13w
0x38392479c  jnz     short loc_3839247E3
0x38392479e  mov     rcx, rbx; StatementHandle
0x3839247a1  call    SQLFetch
0x3839247a6  movzx   r13d, ax
0x3839247aa  test    ax, ax
0x3839247ad  jnz     short loc_3839247D9
0x3839247af  lea     r9, [rbp+5E0h+Buffer]; TargetValue
0x3839247b3  mov     r8d, 0FFFFFFF8h; TargetType
0x3839247b9  mov     edx, esi; ColumnNumber
0x3839247bb  mov     rcx, rbx; StatementHandle
0x3839247be  mov     [rsp+6E0h+StrLen_or_IndPtr], 0; StrLen_or_IndPtr
0x3839247c7  mov     [rsp+6E0h+BufferLength], 608h; BufferLength
0x3839247d0  call    SQLGetData
0x3839247d5  movzx   r13d, ax
0x3839247d9  xor     edx, edx; int
0x3839247db  mov     rcx, rbx; struct tagSTMT *
0x3839247de  call    ?Cancel@@YAFPEAUtagSTMT@@H@Z; Cancel(tagSTMT *,int)
0x3839247e3  mov     r15d, 304h
0x3839247e9  cmp     r13w, 0FFFFh
0x3839247ee  jnz     loc_3839248BC
0x3839247f4  lea     rax, [rsp+6E0h+var_6A0]
0x3839247f9  mov     r9d, 6; fDiagField
0x3839247ff  mov     edx, 604h
0x383924804  mov     [rsp+6E0h+pcbStringLength], rax; pcbStringLength
0x383924809  mov     word ptr [rsp+6E0h+StrLen_or_IndPtr], dx; cbBufferLength
0x38392480e  lea     rax, [rbp+5E0h+Buffer]
0x383924812  lea     ecx, [r9-3]; fHandleType
0x383924816  mov     r8d, esi; iRecord
0x383924819  mov     rdx, rbx; handle
0x38392481c  mov     [rsp+6E0h+BufferLength], rax; rgbDiagInfo
0x383924821  movzx   r13d, si
0x383924825  call    SQLGetDiagFieldW
0x38392482a  test    ax, ax
0x38392482d  jnz     loc_3839248B3
0x383924833  mov     r12d, 604h
0x383924839  nop     dword ptr [rax+00000000h]
0x383924840  movsx   r9, [rsp+6E0h+var_6A0]; __int64
0x383924846  lea     r8, [rbp+5E0h+Buffer]; void *
0x38392484a  lea     rdx, [rdi+78h]; struct ext_buffer **
0x38392484e  mov     rcx, rdi; struct tagOBJBASE *
0x383924851  mov     dword ptr [rsp+6E0h+BufferLength], esi; int
0x383924855  call    ?WriteToExtBufferEx@@YAFPEAUtagOBJBASE@@PEAPEAUext_buffer@@PEBX_JH@Z; WriteToExtBufferEx(tagOBJBASE *,ext_buffer * *,void const *,__int64,int)
0x38392485a  lea     r8, asc_383915954; "\r\n"
0x383924861  lea     rdx, [rdi+78h]; struct ext_buffer **
0x383924865  mov     r9d, 4; __int64
0x38392486b  mov     rcx, rdi; struct tagOBJBASE *
0x38392486e  mov     dword ptr [rsp+6E0h+BufferLength], esi; int
0x383924872  call    ?WriteToExtBufferEx@@YAFPEAUtagOBJBASE@@PEAPEAUext_buffer@@PEBX_JH@Z; WriteToExtBufferEx(tagOBJBASE *,ext_buffer * *,void const *,__int64,int)
0x383924877  lea     rax, [rsp+6E0h+var_6A0]
0x38392487c  mov     ecx, 3; fHandleType
0x383924881  mov     [rsp+6E0h+pcbStringLength], rax; pcbStringLength
0x383924886  lea     rax, [rbp+5E0h+Buffer]
0x38392488a  inc     r13w
0x38392488e  lea     r9d, [rcx+3]; fDiagField
0x383924892  mov     rdx, rbx; handle
0x383924895  movzx   r8d, r13w; iRecord
0x383924899  mov     word ptr [rsp+6E0h+StrLen_or_IndPtr], r12w; cbBufferLength
0x38392489f  mov     [rsp+6E0h+BufferLength], rax; rgbDiagInfo
0x3839248a4  call    SQLGetDiagFieldW
0x3839248a9  test    ax, ax
0x3839248ac  jz      short loc_383924840
0x3839248ae  mov     r12, [rsp+6E0h+var_688]
0x3839248b3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x3839248b7  jmp     loc_38392499D
0x3839248bc  lea     rdx, aIso1_0; "ISO_1"
0x3839248c3  lea     rcx, [rbp+5E0h+Buffer]; String1
0x3839248c7  call    cs:__imp__wcsicmp
0x3839248cd  test    eax, eax
0x3839248cf  jnz     short loc_383924922
0x3839248d1  lea     r8, aCp1252; "cp1252"
0x3839248d8  lea     rax, [rbp+5E0h+Buffer]
0x3839248dc  mov     rdx, r15
0x3839248df  sub     r8, rax
0x3839248e2  lea     rcx, [rbp+5E0h+Buffer]
0x3839248e6  nop     word ptr [rax+rax+00000000h]
0x3839248f0  lea     rax, [rdx+7FFFFCFAh]
0x3839248f7  test    rax, rax
0x3839248fa  jz      short loc_383924914
0x3839248fc  movzx   eax, word ptr [r8+rcx]
0x383924901  test    ax, ax
0x383924904  jz      short loc_383924914
0x383924906  mov     [rcx], ax
0x383924909  add     rcx, 2
0x38392490d  dec     rdx
0x383924910  jnz     short loc_3839248F0
0x383924912  jmp     short loc_383924919
0x383924914  test    rdx, rdx
0x383924917  jnz     short loc_38392491D
0x383924919  sub     rcx, 2
0x38392491d  xor     eax, eax
0x38392491f  mov     [rcx], ax
0x383924922  lea     rcx, [rbp+5E0h+String]; String
0x383924926  call    cs:__imp__wtol
0x38392492c  mov     rcx, [rdi+40h]
0x383924930  cmp     eax, [rcx+274Ch]
0x383924936  jz      short loc_383924998
0x383924938  mov     rax, [rdi+88h]
0x38392493f  test    byte ptr [rax+1C8h], 20h
0x383924946  jnz     short loc_383924998
0x383924948  mov     rcx, cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA; hInstance
0x38392494f  lea     r8, [rbp+5E0h+Buffer]; lpBuffer
0x383924953  mov     r9d, r15d; cchBufferMax
0x383924956  mov     edx, 9C72h; uID
0x38392495b  call    cs:__imp_LoadStringW
0x383924961  lea     r8, [rbp+5E0h+Buffer]; void *
0x383924965  lea     rdx, [rdi+78h]; struct ext_buffer **
0x383924969  mov     r9d, eax
0x38392496c  mov     rcx, rdi; struct tagOBJBASE *
0x38392496f  mov     dword ptr [rsp+6E0h+BufferLength], esi; int
0x383924973  add     r9, r9; __int64
0x383924976  call    ?WriteToExtBufferEx@@YAFPEAUtagOBJBASE@@PEAPEAUext_buffer@@PEBX_JH@Z; WriteToExtBufferEx(tagOBJBASE *,ext_buffer * *,void const *,__int64,int)
0x38392497b  lea     r8, asc_383915954; "\r\n"
0x383924982  lea     rdx, [rdi+78h]; struct ext_buffer **
0x383924986  mov     r9d, 4; __int64
0x38392498c  mov     rcx, rdi; struct tagOBJBASE *
0x38392498f  mov     dword ptr [rsp+6E0h+BufferLength], esi; int
0x383924993  call    ?WriteToExtBufferEx@@YAFPEAUtagOBJBASE@@PEAPEAUext_buffer@@PEBX_JH@Z; WriteToExtBufferEx(tagOBJBASE *,ext_buffer * *,void const *,__int64,int)
0x383924998  mov     rbx, qword ptr [rsp+6E0h+szSqlState]
0x38392499d  mov     rax, [rdi+88h]
0x3839249a4  test    [rax+138h], sil
0x3839249ab  jz      loc_383924A75
0x3839249b1  test    [rax+150h], sil
0x3839249b8  jz      loc_383924A75
0x3839249be  mov     rdx, [rdi+90h]
0x3839249c5  mov     rcx, [rax+140h]
  ... truncated ...
```
