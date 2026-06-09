# SQLSetConnectAttrW

- ea: `0x38386d8d0`
- end: `0x38386f6c6`
- name: `SQLSetConnectAttrW`
- size: `7670`
- prototype: `SQLRETURN __stdcall(SQLHDBC hdbc, SQLINTEGER fAttribute, SQLPOINTER rgbValue, SQLINTEGER cbValue)`
- caller_count: `2`
- callee_count: `37`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x38389d300`
- `0x3838a3600`

## callees

- `0x3838424f0`
- `0x3838427d0`
- `0x3838434c0`
- `0x3838435e0`
- `0x383844d50`
- `0x383869d00`
- `0x38386a410`
- `0x38386c8f0`
- `0x38386ce60`
- `0x38386d3c0`
- `0x38386d810`
- `0x38386d8d0`
- `0x38387da60`
- `0x38388c250`
- `0x38389a4e0`
- `0x3838a3b00`
- `0x3838bae20`
- `0x38391ac40`
- `0x38391aed0`
- `0x38391af80`
- `0x3839393f0`
- `0x38393a170`
- `0x3839484a0`
- `0x38395bb00`
- `0x38395e1a0`
- `0x383961d60`
- `0x383961db0`
- `0x383962350`
- `0x383962810`
- `0x383962990`
- `0x3839629f0`
- `0x383962bc0`
- `0x3839630d0`
- `0x383967300`
- `0x383a9ee60`
- `0x383a9fcd0`
- `0x383adb7a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x38386df3a`
- `KERNEL32!GetLastError` at `0x38386df7c`
- `KERNEL32!GetLastError` at `0x38386dfba`
- `KERNEL32!GetLastError` at `0x38386dffa`
- `KERNEL32!GetLastError` at `0x38386eb2a`
- `KERNEL32!GetLastError` at `0x38386df3a`
- `KERNEL32!GetLastError` at `0x38386df7c`
- `KERNEL32!GetLastError` at `0x38386dfba`
- `KERNEL32!GetLastError` at `0x38386dffa`
- `KERNEL32!GetLastError` at `0x38386eb2a`
- `KERNEL32!FormatMessageW` at `0x38386eb83`
- `KERNEL32!FormatMessageW` at `0x38386eb83`

## string_xrefs

- `0x38386e71a`: ` SET TRANSACTION ISOLATION LEVEL READ COMMITTED `
- `0x38386e723`: ` SET TRANSACTION ISOLATION LEVEL READ UNCOMMITTED `
- `0x38386e711`: ` SET TRANSACTION ISOLATION LEVEL REPEATABLE READ `

## pseudocode

```c
SQLRETURN __stdcall SQLSetConnectAttrW(SQLHDBC hdbc, SQLINTEGER fAttribute, SQLPOINTER rgbValue, SQLINTEGER cbValue)
{
  __int64 v5; // rbx
  const CHAR *v6; // r12
  const unsigned __int16 *v8; // r13
  unsigned __int64 v9; // rsi
  SQLRETURN v10; // r15
  const unsigned __int16 *v11; // r8
  void *v12; // r9
  signed __int64 v13; // rdx
  bool v14; // zf
  _WORD *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int16 v18; // ax
  unsigned __int16 v19; // ax
  SQLINTEGER v20; // r11d
  char v21; // r11
  _QWORD *v23; // rdx
  _QWORD *v24; // rbx
  unsigned __int16 v25; // ax
  __int64 v26; // rbx
  __int64 v27; // rax
  struct tagSTMT *v28; // rcx
  __int64 v29; // rax
  __int64 v30; // r13
  struct tagDBC *v31; // rdx
  UINT v32; // esi
  int v33; // r13d
  __int16 v34; // bx
  unsigned int v35; // r13d
  int v36; // eax
  DWORD LastError; // eax
  unsigned __int16 v38; // dx
  int v39; // eax
  __int64 v40; // rdx
  __int64 v41; // rdx
  unsigned __int64 v42; // rax
  unsigned __int64 v43; // rbx
  int v44; // edx
  unsigned __int64 v45; // rax
  __int64 v46; // rcx
  _WORD *v47; // r9
  __int64 v48; // rdx
  _WORD *v49; // r8
  unsigned __int64 v50; // rsi
  __int16 v51; // ax
  int v52; // ecx
  __int64 v53; // rax
  __int16 v54; // cx
  __int64 v55; // rcx
  bool v56; // cf
  char *v57; // rbx
  unsigned __int64 v58; // rbx
  unsigned __int16 *v59; // rax
  unsigned __int16 *v60; // r12
  __int64 v61; // rax
  __int64 v62; // rbx
  __int16 v63; // ax
  __int64 v64; // rbx
  WCHAR *v65; // rcx
  WCHAR v66; // ax
  WCHAR v67; // ax
  __int64 v68; // rax
  __int64 v69; // rsi
  __int64 v70; // r11
  __int64 v71; // r13
  DWORD v72; // ebx
  struct tagDBC *v73; // rcx
  unsigned __int64 v74; // rax
  __int64 v75; // rbx
  __int64 v76; // r12
  WCHAR *v77; // rcx
  WCHAR v78; // ax
  unsigned __int64 v79; // rax
  __int64 v80; // rbx
  WCHAR *v81; // rcx
  WCHAR v82; // ax
  __int64 v83; // rax
  __int64 v84; // rbx
  __int64 v85; // rax
  __int64 v86; // rbx
  unsigned __int64 v87; // rax
  _WORD *v88; // rcx
  __int64 v89; // rdx
  unsigned __int64 v90; // rsi
  __int16 v91; // ax
  _WORD *v92; // rax
  __int16 v93; // cx
  SQLINTEGER v94; // eax
  unsigned int v95; // ebx
  int v96; // eax
  int v97; // eax
  int v98; // eax
  unsigned __int64 v99; // rax
  unsigned __int64 i; // r13
  __int64 v101; // rcx
  __int64 v102; // rax
  struct tagOBJBASE *v103; // rbx
  SQLRETURN v104; // r11
  int v105; // r14d
  __int64 v106; // rdx
  _WORD *v107; // rcx
  __int16 v108; // ax
  unsigned __int16 v109; // [rsp+40h] [rbp-C0h] BYREF
  SQLPOINTER rgbValuea; // [rsp+48h] [rbp-B8h] BYREF
  __int64 cbMultiByte; // [rsp+50h] [rbp-B0h]
  struct tagDBC *v112; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v113; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v114; // [rsp+68h] [rbp-98h]
  unsigned __int64 v115; // [rsp+70h] [rbp-90h] BYREF
  int v116; // [rsp+78h] [rbp-88h] BYREF
  __int64 v117; // [rsp+80h] [rbp-80h] BYREF
  int v118; // [rsp+88h] [rbp-78h] BYREF
  struct BATCHCTX *v119; // [rsp+90h] [rbp-70h] BYREF
  _WORD v120[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR WideCharStr[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR Buffer[512]; // [rsp+4C0h] [rbp+3C0h] BYREF
  unsigned __int16 v123[1024]; // [rsp+8C0h] [rbp+7C0h] BYREF

  v5 = (unsigned int)cbValue;
  v6 = (const CHAR *)rgbValue;
  v8 = 0;
  v9 = (unsigned __int64)rgbValue;
  rgbValuea = rgbValue;
  cbMultiByte = (unsigned int)cbValue;
  v10 = 0;
  v109 = -25337;
  memset(WideCharStr, 0, 522);
  v112 = 0;
  v115 = 0;
  v117 = -1;
  if ( (bidGblFlags & 4) != 0 )
  {
    if ( off_383B4A8B0[0] )
      bidScopeEnterW(&v117, off_383B4A8B0[0], *(unsigned int *)hdbc, hdbc);
    v9 = (unsigned __int64)rgbValuea;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)hdbc + 1000) + 32LL) + 8LL))(*((_QWORD *)hdbc + 1000) + 32LL);
  if ( (*((_BYTE *)hdbc + 24) & 0x10) == 0 )
    goto LABEL_3;
  if ( fAttribute != 37300 || v6 != (const CHAR *)1 )
  {
    if ( (*((_BYTE *)hdbc + 24) & 4) == 0 )
    {
      v23 = (_QWORD *)*((_QWORD *)hdbc + 1);
      if ( v23 )
      {
        do
        {
          v24 = (_QWORD *)*v23;
          ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
          v23 = v24;
        }
        while ( v24 );
        v5 = cbMultiByte;
      }
      *((_QWORD *)hdbc + 1) = 0;
      *((_QWORD *)hdbc + 2) = 0;
      *((_WORD *)hdbc + 12) = 0;
    }
LABEL_3:
    if ( fAttribute == 116 )
    {
      fAttribute = 1246;
    }
    else if ( fAttribute == 65000 )
    {
      fAttribute = 109;
    }
  }
  v13 = 0x383800000uLL;
  switch ( *((_DWORD *)hdbc + 2694) )
  {
    case 2:
    case 0xA:
      if ( fAttribute != 102 )
      {
        v25 = -25374;
        goto LABEL_467;
      }
LABEL_151:
      v10 = SetCommitModeOption((struct tagDBC *)hdbc, v9);
      if ( v10 == 2 )
      {
        *((_DWORD *)hdbc + 2694) &= ~0x80000000;
        goto LABEL_39;
      }
      *((_DWORD *)hdbc + 2694) = 0;
      *((_DWORD *)hdbc + 2689) = 0;
      if ( (v10 & 0xFFFE) == 0 )
        goto LABEL_531;
      goto LABEL_39;
    case 3:
      if ( fAttribute != 109 )
        goto LABEL_54;
LABEL_172:
      v10 = ChangeDatabase((struct tagDBC *)hdbc, (const unsigned __int16 *)v9);
      if ( v10 == 2 )
      {
        *((_DWORD *)hdbc + 2694) &= ~0x80000000;
        goto LABEL_39;
      }
      v9 = (unsigned __int64)hdbc + 2262;
      *((_DWORD *)hdbc + 2694) = 0;
      *((_DWORD *)hdbc + 2689) = 0;
      rgbValuea = (char *)hdbc + 2262;
LABEL_176:
      if ( (v10 & 0xFFFE) == 0 )
      {
        v47 = (_WORD *)*((_QWORD *)hdbc + 1015);
        if ( v47 || (v47 = SQLAllocateMemory((struct tagOBJBASE *)hdbc, 0x102u)) != 0 )
        {
          v48 = 129;
          v49 = v47;
          v50 = v9 - (_QWORD)v47;
          do
          {
            if ( v48 == -2147483517 )
              goto LABEL_184;
            v51 = *(_WORD *)((char *)v49 + v50);
            if ( !v51 )
              goto LABEL_184;
            *v49++ = v51;
            --v48;
          }
          while ( v48 );
          --v49;
LABEL_184:
          *v49 = 0;
          *((_QWORD *)hdbc + 1015) = v47;
          LOBYTE(v52) = 8;
          goto LABEL_535;
        }
        goto LABEL_34;
      }
      v53 = *((_QWORD *)hdbc + 1);
      v54 = *(_WORD *)(v53 + 8);
      if ( !v54 )
      {
        *(_WORD *)(v53 + 8) = -25337;
        goto LABEL_39;
      }
      if ( v54 != -25376 )
      {
        FreeErrors((struct tagOBJBASE *)hdbc);
        v109 = -25336;
        goto LABEL_35;
      }
      goto LABEL_39;
    case 8:
      if ( fAttribute == 1217 )
        goto LABEL_64;
      goto LABEL_54;
    case 9:
      if ( fAttribute != 101 )
        goto LABEL_54;
LABEL_56:
      v10 = IsDataBaseReadOnly((struct tagDBC *)hdbc, &v116);
      if ( v10 == 2 )
      {
        *((_DWORD *)hdbc + 2694) &= ~0x80000000;
        goto LABEL_39;
      }
      *((_DWORD *)hdbc + 2694) = 0;
      *((_DWORD *)hdbc + 2689) = 0;
      if ( v10 )
      {
        v10 = -1;
        if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
          bidTraceW(off_383B431E8[0], 1361929, off_383B49120[0], 1330);
        goto LABEL_39;
      }
      if ( !v116 )
        goto LABEL_531;
      goto LABEL_35;
    case 0xB:
      if ( fAttribute != 108 && fAttribute != 1227 )
        goto LABEL_54;
      fAttribute = 108;
LABEL_243:
      v61 = *((_QWORD *)hdbc + 1003) + 304LL;
      if ( *((_QWORD *)hdbc + 1003) != -304 )
      {
        v62 = *(_QWORD *)v61;
        (*(void (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)(*(_QWORD *)v61 + 32LL) + 8LL))(
          *(_QWORD *)v61 + 32LL,
          0x383800000uLL);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)(v62 + 32) + 24LL))(v62 + 32);
      }
      v10 = ExecImmediate(*((struct tagSTMT **)hdbc + 1003), v8, -3, *((_DWORD *)hdbc + 2250), 0);
      if ( v10 == 2 )
      {
        *((_DWORD *)hdbc + 2694) &= ~0x80000000;
        goto LABEL_39;
      }
      *((_DWORD *)hdbc + 2694) = 0;
      *((_DWORD *)hdbc + 2689) = 0;
      if ( v10 )
        XferErrors((struct tagOBJBASE *)hdbc, *((struct tagOBJBASE **)hdbc + 1003));
      SQLFreeStmt(*((SQLHSTMT *)hdbc + 1003), 0);
      v63 = -2;
LABEL_250:
      *((_WORD *)hdbc + 5056) &= v63;
      goto LABEL_531;
    case 0xC:
      if ( fAttribute != 1207 )
        goto LABEL_54;
LABEL_78:
      v10 = SQLEnlistTransaction((struct tagOBJBASE *)hdbc, (struct tagDBC *)v9, (unsigned __int16)v11, v12);
      if ( v10 == 2 )
      {
        *((_DWORD *)hdbc + 2694) &= ~0x80000000;
        goto LABEL_39;
      }
      *((_DWORD *)hdbc + 2694) = 0;
      LOBYTE(v52) = 25;
      *((_DWORD *)hdbc + 2689) = 0;
      goto LABEL_535;
    case 0xD:
      if ( fAttribute != 1208 )
        goto LABEL_54;
      if ( *((_DWORD *)hdbc + 2695) == 1 )
      {
        v31 = (struct tagDBC *)*((_QWORD *)hdbc + 1351);
        v112 = v31;
LABEL_313:
        v10 = SQLEnlistTransaction((struct tagOBJBASE *)hdbc, v31, (unsigned __int16)v11, v12);
        if ( v10 == 2 )
        {
          *((_DWORD *)hdbc + 2694) &= ~0x80000000;
          goto LABEL_39;
        }
        v73 = v112;
        *((_DWORD *)hdbc + 2694) = 0;
        *((_DWORD *)hdbc + 2689) = 0;
        if ( v73 )
        {
          (*(void (__fastcall **)(struct tagDBC *))(*(_QWORD *)v73 + 16LL))(v73);
          LOBYTE(v52) = 26;
          goto LABEL_535;
        }
      }
      else
      {
LABEL_318:
        v10 = SQLEnlistTransaction((struct tagOBJBASE *)hdbc, 0, (unsigned __int16)v11, v12);
        if ( v10 == 2 )
        {
          *((_DWORD *)hdbc + 2694) &= ~0x80000000;
          goto LABEL_39;
        }
        *((_DWORD *)hdbc + 2694) = 0;
        *((_DWORD *)hdbc + 2689) = 0;
      }
      LOBYTE(v52) = 26;
      goto LABEL_535;
    case 0xE:
      if ( fAttribute != 1246 )
      {
LABEL_54:
        v25 = -25374;
        goto LABEL_467;
      }
      if ( *((_DWORD *)hdbc + 2695) != 1 )
        goto LABEL_397;
LABEL_387:
      v83 = *((_QWORD *)hdbc + 1003) + 304LL;
      if ( *((_QWORD *)hdbc + 1003) != -304 )
      {
        v84 = *(_QWORD *)v83;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)v83 + 32LL) + 8LL))(*(_QWORD *)v83 + 32LL);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)(v84 + 32) + 24LL))(v84 + 32);
      }
      v10 = ExecTMRImmediate(*((struct tagSTMT **)hdbc + 1003), (struct TMRequest *)v120, *((_DWORD *)hdbc + 2250), 0);
      if ( v10 == 2 )
      {
        *((_DWORD *)hdbc + 2694) &= ~0x80000000;
        goto LABEL_39;
      }
      *((_DWORD *)hdbc + 2694) = 0;
      *((_DWORD *)hdbc + 2689) = 0;
      if ( v10 )
        XferErrors((struct tagOBJBASE *)hdbc, *((struct tagOBJBASE **)hdbc + 1003));
      SQLFreeStmt(*((SQLHSTMT *)hdbc + 1003), 0);
      goto LABEL_26;
    default:
      if ( fAttribute > 1226 )
      {
        if ( fAttribute == 1242 || fAttribute == 1247 || fAttribute == 37283 )
          goto LABEL_133;
        if ( fAttribute != 37284 )
        {
          v14 = fAttribute == 37286;
          goto LABEL_12;
        }
        if ( !v6 )
        {
LABEL_435:
          v94 = 1236;
          if ( fAttribute <= 37284 )
            v94 = 1234;
          fAttribute = v94;
LABEL_438:
          if ( *((_QWORD *)hdbc + 8) )
          {
LABEL_465:
            v25 = -25373;
LABEL_466:
            v9 = (unsigned __int64)rgbValuea;
            goto LABEL_467;
          }
          v95 = fAttribute - 1200;
          v96 = fAttribute - 1182;
          if ( (unsigned int)(fAttribute - 1200) > 0x24 )
            v96 = fAttribute - 1192;
          if ( *((_QWORD *)hdbc + v96 + 1007) )
          {
            v97 = fAttribute - 1182;
            if ( v95 > 0x24 )
              v97 = fAttribute - 1192;
            if ( *((_QWORD *)hdbc + v97 + 1007) )
              ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
            v98 = fAttribute - 1182;
            if ( v95 > 0x24 )
              v98 = fAttribute - 1192;
            *((_QWORD *)hdbc + v98 + 1007) = v6;
          }
          v9 = (unsigned __int64)rgbValuea;
          if ( rgbValuea )
          {
            v58 = -1;
            do
              ++v58;
            while ( *((_WORD *)rgbValuea + v58) );
            switch ( fAttribute )
            {
              case 1221:
              case 1229:
              case 1230:
                v99 = 260;
                goto LABEL_456;
              case 1225:
                v99 = 257;
                goto LABEL_456;
              case 1226:
                v99 = 128;
LABEL_456:
                if ( v58 <= v99 )
                  goto LABEL_220;
                v25 = -25371;
                break;
              case 1247:
                if ( (unsigned int)FIsValidApplicationIntentString((wchar_t *)rgbValuea) )
                  goto LABEL_220;
                *((_QWORD *)hdbc + 1121) &= ~0x80000000000000uLL;
                v109 = -25337;
                goto LABEL_35;
              default:
                goto LABEL_220;
            }
            goto LABEL_467;
          }
LABEL_531:
          if ( fAttribute < 1247 || fAttribute > 1248 )
          {
            if ( fAttribute < 1200 )
LABEL_536:
              v52 = fAttribute - 101;
            else
              v52 = fAttribute - 1182;
          }
          else
          {
            v52 = fAttribute - 1192;
          }
          goto LABEL_534;
        }
        if ( (_DWORD)v5 == -3 )
        {
          v5 = -1;
          do
            ++v5;
          while ( v6[v5] );
          cbMultiByte = v5;
        }
        v32 = 0;
        if ( (_DWORD)v5 )
          v32 = *((_DWORD *)hdbc + 2256);
        v33 = cbMultiByte;
        v34 = 0;
        if ( (_DWORD)cbMultiByte )
        {
          v35 = cbMultiByte;
          WideCharStr[260] = 0;
          v36 = FastMultiByteToWideChar(v32, v6, (unsigned int)cbMultiByte, WideCharStr, 260);
          cbMultiByte = v36;
          if ( v36 )
          {
            v33 = 2 * v36;
            v6 = 0;
            cbMultiByte = (unsigned int)(2 * v36);
            WideCharStr[v36] = 0;
          }
          else
          {
            if ( GetLastError() != 122 )
            {
              if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
                bidTraceW(off_383B43220, 1858569, off_383B49120[0], 1815);
              if ( GetLastError() == 87 )
              {
                if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
                  bidTraceW(off_383B43220, 1937417, off_383B49120[0], 1892);
                LastError = GetLastError();
                v38 = -25302;
              }
              else
              {
                if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
                  bidTraceW(off_383B43220, 1941513, off_383B49120[0], 1896);
                LastError = GetLastError();
                v38 = -25331;
              }
              PostSQLErrorEx((struct tagOBJBASE *)hdbc, v38, LastError, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
              v33 = cbMultiByte;
              if ( (bidGblFlags & 2) != 0 )
              {
                v6 = 0;
                v34 = _bidx_SNACOdbc_ErrCode(off_383B43220, 0x1DBC09u, -1);
              }
              else
              {
                v34 = -1;
                v6 = 0;
              }
LABEL_120:
              if ( (bidGblFlags & 2) != 0 )
              {
                if ( !v34 && (bidGblFlags & 0x40) == 0 )
                {
LABEL_130:
                  v42 = (unsigned __int64)v33 >> 1;
                  if ( v42 >= 261 )
                    _report_gsfailure(0);
                  WideCharStr[v42] = 0;
                  rgbValuea = WideCharStr;
                  goto LABEL_435;
                }
                v41 = 1704961;
                if ( v34 )
                  v41 = 1704993;
                bidTraceW(off_383B43220, v41, off_383B494E8[0], (unsigned int)v34);
              }
              if ( v34 == -1 )
              {
                v10 = -1;
                if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
                  bidTraceW(off_383B431E8[0], 1298441, off_383B49120[0], 1268);
                goto LABEL_39;
              }
              goto LABEL_130;
            }
            v39 = FastMultiByteToWideChar(v32, v6, v35, 0, 0);
            v34 = 1;
            v6 = 0;
            v33 = 2 * v39;
            cbMultiByte = (unsigned int)(2 * v39);
          }
        }
        else
        {
          v6 = 0;
          WideCharStr[0] = 0;
        }
        if ( (bidGblFlags & 2) != 0 && (v34 || (bidGblFlags & 0x40) != 0) )
        {
          v40 = 1930241;
          if ( v34 )
            v40 = 1930273;
          bidTraceW(off_383B43220, v40, off_383B494E8[0], (unsigned int)v34);
        }
        goto LABEL_120;
      }
      if ( fAttribute == 1226 )
        goto LABEL_133;
      if ( fAttribute > 1214 )
      {
        if ( fAttribute == 1216 )
          goto LABEL_133;
        v14 = fAttribute == 1221;
      }
      else
      {
        if ( fAttribute == 1214 || fAttribute == 106 || fAttribute == 109 )
          goto LABEL_133;
        v14 = fAttribute == 1212;
      }
LABEL_12:
      if ( !v14 )
      {
LABEL_13:
        v6 = 0;
        goto LABEL_14;
      }
LABEL_133:
      if ( !v6 || (_DWORD)v5 == -3 )
        goto LABEL_13;
      if ( (int)v5 < 0 )
      {
LABEL_219:
        v25 = -25371;
        goto LABEL_467;
      }
      if ( (int)v5 >= 522 )
        v5 = 520;
      cbMultiByte = v5;
      memcpy(WideCharStr, v6, (int)v5);
      v43 = (unsigned __int64)(int)v5 >> 1;
      if ( v43 >= 261 )
        _report_gsfailure(0);
      v9 = (unsigned __int64)WideCharStr;
      v6 = 0;
      rgbValuea = WideCharStr;
      WideCharStr[v43] = 0;
LABEL_14:
      if ( fAttribute <= 1200 )
      {
        if ( fAttribute != 1200 )
        {
          switch ( fAttribute )
          {
            case 'e':
              if ( !*((_QWORD *)hdbc + 8) )
                goto LABEL_525;
              v9 = (unsigned __int64)rgbValuea;
              if ( rgbValuea )
                goto LABEL_531;
              *((_DWORD *)hdbc + 2694) = -2147483639;
              *((_DWORD *)hdbc + 2689) = 0;
              goto LABEL_56;
            case 'f':
              if ( v9 != *((_QWORD *)hdbc + 1008) )
                goto LABEL_151;
              goto LABEL_531;
            case 'g':
            case 'q':
              v44 = -1;
              if ( v9 > 0xFFFE )
              {
                v9 = 65534;
                rgbValuea = (SQLPOINTER)65534;
                if ( (bidGblFlags & 2) != 0 )
                {
                  if ( off_383B49120[0] )
                    bidTraceW(off_383B431E8[0], 1392649, off_383B49120[0], 1360);
                  v9 = (unsigned __int64)rgbValuea;
                }
                PostSQLErrorEx((struct tagOBJBASE *)hdbc, 0x9E09u, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
                v10 = 1;
                v44 = -1;
              }
              if ( fAttribute != 113 )
              {
                if ( (_DWORD)v9 )
                  v44 = 1000 * v9;
                *((_DWORD *)hdbc + 2251) = v44;
                goto LABEL_531;
              }
              if ( (_DWORD)v9 )
                v44 = 1000 * v9;
              *((_DWORD *)hdbc + 2250) = v44;
              goto LABEL_536;
            case 'j':
              if ( !*((_QWORD *)hdbc + 8) )
              {
                v25 = -25356;
                goto LABEL_466;
              }
              v57 = (char *)hdbc + 8 * fAttribute;
              if ( *((_QWORD *)v57 + 906) )
              {
                ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
                *((_QWORD *)v57 + 906) = 0;
              }
              v9 = (unsigned __int64)rgbValuea;
              if ( !rgbValuea )
                goto LABEL_531;
              v58 = -1;
              do
                ++v58;
              while ( *((_WORD *)rgbValuea + v58) );
              if ( v58 > 0x104 )
                goto LABEL_219;
LABEL_220:
              v59 = (unsigned __int16 *)SQLAllocateMemory((struct tagOBJBASE *)hdbc, 2 * v58 + 2);
              v60 = v59;
              if ( !v59 )
                goto LABEL_35;
              StringCchCopyW(v59, v58 + 1, (const unsigned __int16 *)v9);
              v9 = (unsigned __int64)v60;
              goto LABEL_531;
            case 'k':
              goto LABEL_531;
            case 'l':
LABEL_223:
              if ( v9 != 1 && v9 != 2 && v9 != 4 && v9 != 8 && v9 != 32 )
              {
                v25 = -25358;
                goto LABEL_467;
              }
              if ( !*((_QWORD *)hdbc + 8) )
              {
LABEL_525:
                v9 = (unsigned __int64)rgbValuea;
                goto LABEL_531;
              }
              v9 = (unsigned __int64)rgbValuea;
              if ( (*((_BYTE *)hdbc + 10112) & 1) != 0 )
              {
                v25 = -25373;
                goto LABEL_467;
              }
              if ( rgbValuea == (SQLPOINTER)1 )
              {
                v8 = L" SET TRANSACTION ISOLATION LEVEL READ UNCOMMITTED ";
              }
              else if ( rgbValuea == (SQLPOINTER)2 )
              {
                v8 = L" SET TRANSACTION ISOLATION LEVEL READ COMMITTED ";
              }
              else if ( rgbValuea == (SQLPOINTER)4 )
              {
                v8 = L" SET TRANSACTION ISOLATION LEVEL REPEATABLE READ ";
              }
              else if ( rgbValuea == (SQLPOINTER)8 )
              {
                v8 = L" SET TRANSACTION ISOLATION LEVEL SERIALIZABLE ";
              }
              else if ( rgbValuea == (SQLPOINTER)32 )
              {
                v8 = L" SET TRANSACTION ISOLATION LEVEL SNAPSHOT ";
              }
              *((_DWORD *)hdbc + 2694) = -2147483637;
              *((_DWORD *)hdbc + 2689) = 0;
              goto LABEL_243;
            case 'm':
              if ( !v9 )
                goto LABEL_210;
              v45 = -1;
              do
                ++v45;
              while ( *(_WORD *)(v9 + 2 * v45) );
              if ( v45 > 0x80 )
                goto LABEL_210;
              if ( !*((_QWORD *)hdbc + 8) )
              {
                v9 = (unsigned __int64)rgbValuea;
                goto LABEL_176;
              }
              v46 = *((_QWORD *)hdbc + 1003);
              v109 = 0;
              if ( *(_QWORD *)(v46 + 1112) && (unsigned int)CheckBusy((struct tagSTMT *)v46, &v109) )
              {
                v25 = -25406;
                goto LABEL_466;
              }
              v9 = (unsigned __int64)rgbValuea;
              *((_DWORD *)hdbc + 2694) = -2147483645;
              *((_DWORD *)hdbc + 2689) = 0;
              goto LABEL_172;
            case 'p':
              v9 = (unsigned __int64)rgbValuea;
              if ( *((_QWORD *)hdbc + 8) )
              {
                v25 = -25373;
                goto LABEL_467;
              }
              if ( !rgbValuea )
                goto LABEL_531;
              v55 = 0x7FFF;
              v56 = (unsigned __int64)rgbValuea < 0x200;
              if ( (unsigned __int64)rgbValuea < 0x200 )
                goto LABEL_195;
              if ( (unsigned __int64)rgbValuea > 0x7FFF )
              {
                v56 = (unsigned __int64)rgbValuea < 0x200;
LABEL_195:
                if ( v56 )
                  v55 = 512;
                v9 = v55;
                rgbValuea = (SQLPOINTER)v55;
                if ( (bidGblFlags & 2) != 0 )
                {
                  if ( off_383B49120[0] )
                    bidTraceW(off_383B431E8[0], 1560585, off_383B49120[0], 1524);
                  v9 = (unsigned __int64)rgbValuea;
                }
                PostSQLErrorEx((struct tagOBJBASE *)hdbc, 0x9E06u, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
                v10 = 1;
              }
              goto LABEL_531;
            case 'u':
              if ( g_osviEx.dwMajorVersion <= 6 && (g_osviEx.dwMajorVersion != 6 || !g_osviEx.dwMinorVersion) )
                goto LABEL_205;
              if ( v9 == 1 )
              {
                if ( *((_QWORD *)hdbc + 1044) != 1 )
                  goto LABEL_531;
                v25 = -25355;
                goto LABEL_467;
              }
              if ( !v9 )
                goto LABEL_531;
LABEL_210:
              v109 = -25337;
              break;
            default:
              goto LABEL_33;
          }
          goto LABEL_35;
        }
LABEL_260:
        v9 = (unsigned __int64)rgbValuea;
        if ( *((_QWORD *)hdbc + 8) )
        {
          v25 = -25373;
          goto LABEL_467;
        }
LABEL_262:
        if ( v9 > 1 )
        {
          v109 = -25337;
          goto LABEL_35;
        }
        goto LABEL_531;
      }
      if ( fAttribute > 10001 )
      {
        if ( fAttribute < 37283 )
        {
LABEL_33:
          v19 = IsSetStmtOptionValid((struct tagDBC *)hdbc, 0, fAttribute, &rgbValuea, cbMultiByte);
          v9 = (unsigned __int64)rgbValuea;
          v109 = v19;
          if ( !v19 )
          {
LABEL_473:
            for ( i = 1; i <= *(_QWORD *)(*((_QWORD *)hdbc + 1004) + 8LL); ++i )
            {
              v101 = *((_QWORD *)hdbc + 1004);
              v102 = *(_QWORD *)(v101 + 24) * (i - 1);
              v103 = *(struct tagOBJBASE **)(v102 + v101 + 32);
              if ( v103 && v103 != *((struct tagOBJBASE **)hdbc + 1003) )
              {
                v104 = SQLSetStmtAttrW(*(SQLHSTMT *)(v102 + v101 + 32), fAttribute, (SQLPOINTER)v9, v20);
                if ( v104 )
                  XferErrors((struct tagOBJBASE *)hdbc, v103);
                if ( !v10 && v104 == 1 || (v10 & 0xFFFE) == 0 && v104 )
                  v10 = v104;
                if ( v10 == -1 )
                  break;
              }
              v20 = cbMultiByte;
            }
            if ( (unsigned int)(fAttribute - 10001) > 0xD )
            {
              if ( fAttribute < 1225 )
                v105 = fAttribute + 2;
              else
                v105 = fAttribute - 1181;
            }
            else
            {
              v105 = fAttribute - 9971;
            }
            if ( v105 >= 57 )
              v10 = -1;
            else
              *((_QWORD *)hdbc + v105 + 1064) = v9;
            if ( v109 && !v10 )
              v10 = 1;
            goto LABEL_39;
          }
LABEL_34:
          if ( v109 == 1 )
          {
LABEL_37:
            if ( v109 != 0x9E04 )
            {
LABEL_38:
              v10 = -1;
              if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
                bidTraceW(off_383B431E8[0], 2311177, off_383B49120[0], 2257);
              goto LABEL_39;
            }
            v20 = cbMultiByte;
            goto LABEL_473;
          }
LABEL_35:
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( off_383B49120[0] )
              bidTraceW(off_383B431E8[0], 2309129, off_383B49120[0], 2255);
            v9 = (unsigned __int64)rgbValuea;
          }
          PostSQLErrorEx((struct tagOBJBASE *)hdbc, v109, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
          goto LABEL_37;
        }
        if ( fAttribute > 37284 )
        {
          if ( fAttribute == 37285 )
          {
            v9 = (unsigned __int64)rgbValuea;
            if ( *((_QWORD *)hdbc + 8) )
            {
              v25 = -25373;
              goto LABEL_467;
            }
            if ( rgbValuea )
            {
              v92 = (_WORD *)*((_QWORD *)hdbc + 1060);
              if ( !v92 )
              {
                v92 = SQLAllocateMemory((struct tagOBJBASE *)hdbc, 6u);
                if ( !v92 )
                  goto LABEL_35;
              }
              *(_DWORD *)v92 = *(_DWORD *)rgbValuea;
              v93 = *(_WORD *)(v9 + 4);
              v9 = (unsigned __int64)v92;
              v92[2] = v93;
              v52 = 53;
            }
            else
            {
              if ( *((_QWORD *)hdbc + 1060) )
                ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
              v52 = 53;
            }
LABEL_534:
            *((_QWORD *)hdbc + v52 + 1007) = v9;
LABEL_535:
            *((_QWORD *)hdbc + 1121) |= 1LL << v52;
            goto LABEL_39;
          }
          if ( fAttribute != 37286 )
          {
            if ( fAttribute == 37287 )
            {
              if ( *((_QWORD *)hdbc + 8) )
              {
                *((_DWORD *)hdbc + 2256) = (_DWORD)rgbValuea;
                goto LABEL_39;
              }
              goto LABEL_465;
            }
            goto LABEL_33;
          }
        }
        goto LABEL_435;
      }
      if ( fAttribute == 10001 )
      {
LABEL_205:
        v25 = -25369;
LABEL_467:
        v109 = v25;
        goto LABEL_35;
      }
      switch ( fAttribute )
      {
        case 1202:
          if ( v9 <= 2 )
            goto LABEL_531;
          v109 = -25337;
          goto LABEL_35;
        case 1203:
        case 1210:
        case 1218:
        case 1222:
        case 1248:
          goto LABEL_260;
        case 1204:
          goto LABEL_262;
        case 1205:
        case 1206:
        case 1213:
          goto LABEL_531;
        case 1207:
          v9 = (unsigned __int64)rgbValuea;
          if ( !*((_QWORD *)hdbc + 8) )
          {
            v25 = -25356;
            goto LABEL_467;
          }
          *((_DWORD *)hdbc + 2694) = -2147483636;
          *((_DWORD *)hdbc + 2689) = 0;
          goto LABEL_78;
        case 1208:
          v9 = (unsigned __int64)rgbValuea;
          if ( !*((_QWORD *)hdbc + 8) )
          {
            v25 = -25356;
            goto LABEL_467;
          }
          if ( !rgbValuea )
          {
            *((_DWORD *)hdbc + 2694) = -2147483635;
            *((_DWORD *)hdbc + 2695) = 2;
            *((_DWORD *)hdbc + 2689) = 0;
            goto LABEL_318;
          }
          v118 = 0;
          if ( (unsigned int)StartXATransaction((char *)hdbc + 10080, &v112, &v118) )
          {
            v31 = v112;
            *((_DWORD *)hdbc + 2694) = -2147483635;
            *((_DWORD *)hdbc + 2689) = 0;
            *((_QWORD *)hdbc + 1351) = v31;
            *((_DWORD *)hdbc + 2695) = 1;
            goto LABEL_313;
          }
          v72 = GetLastError();
          if ( !v72 )
          {
            v25 = -25358;
            goto LABEL_467;
          }
          memset(Buffer, 0, sizeof(Buffer));
          FormatMessageW(0x1200u, 0, v72, 0, Buffer, 0x200u, 0);
          if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
            bidTraceW(off_383B431E8[0], 1747977, off_383B49120[0], 1707);
          PostTextErrorEx((struct tagOBJBASE *)hdbc, Buffer, L"25S12", 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF, 0, 1);
          goto LABEL_38;
        case 1211:
          if ( v9 == 1 )
          {
            if ( !g_fPerfStatLogEnabled && (unsigned __int16)InitStatistics((struct tagDBC *)hdbc, 0) )
            {
              v25 = -25130;
              goto LABEL_467;
            }
          }
          else
          {
            if ( v9 != 2 )
            {
              if ( g_fPerfStatLogEnabled )
                StopStatistics();
              goto LABEL_326;
            }
            if ( g_fPerfStatLogEnabled )
              StopStatistics();
          }
          goto LABEL_531;
        case 1212:
          if ( g_fPerfStatLogEnabled || !v9 )
            goto LABEL_326;
          v79 = -1;
          do
            ++v79;
          while ( *(_WORD *)(v9 + 2 * v79) );
          v80 = 261;
          if ( v79 >= 0x105 )
          {
            v109 = -25337;
            goto LABEL_35;
          }
          v76 = g_csSQLPerf;
          (*(void (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)(g_csSQLPerf + 32LL) + 8LL))(
            g_csSQLPerf + 32LL,
            0x383800000uLL);
          if ( g_fPerfStatLogEnabled )
            goto LABEL_348;
          v81 = &g_szPerfDataFile;
          while ( v80 != -2147483385 )
          {
            v82 = *(WCHAR *)((char *)v81 + v9 - (_QWORD)&g_szPerfDataFile);
            if ( !v82 )
              break;
            *v81++ = v82;
            if ( !--v80 )
            {
              --v81;
              break;
            }
          }
          *v81 = 0;
          goto LABEL_348;
        case 1214:
          if ( g_fLogSlowQuery || !v9 )
            goto LABEL_326;
          v74 = -1;
          do
            ++v74;
          while ( *(_WORD *)(v9 + 2 * v74) );
          v75 = 261;
          if ( v74 >= 0x105 )
          {
            v109 = -25337;
            goto LABEL_35;
          }
          v76 = g_csSQLPerf;
          (*(void (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)(g_csSQLPerf + 32LL) + 8LL))(
            g_csSQLPerf + 32LL,
            0x383800000uLL);
          if ( g_fLogSlowQuery )
            goto LABEL_348;
          v77 = &g_szPerfQueryFile;
          while ( v75 != -2147483385 )
          {
            v78 = *(WCHAR *)((char *)v77 + v9 - (_QWORD)&g_szPerfQueryFile);
            if ( !v78 )
              break;
            *v77++ = v78;
            if ( !--v75 )
            {
              --v77;
              break;
            }
          }
          *v77 = 0;
LABEL_348:
          (*(void (__fastcall **)(__int64))(*(_QWORD *)(v76 + 32) + 24LL))(v76 + 32);
          goto LABEL_531;
        case 1215:
          if ( v9 == 1 )
          {
            if ( !g_fLogSlowQuery && (unsigned __int16)InitQuery((struct tagDBC *)hdbc, 0) )
            {
              v25 = -25130;
              goto LABEL_467;
            }
            goto LABEL_531;
          }
          if ( v9 == 2 )
          {
            if ( g_fLogSlowQuery )
              StopQuery();
            goto LABEL_531;
          }
          if ( g_fLogSlowQuery )
          {
            StopQuery();
            v25 = -25130;
          }
          else
          {
LABEL_326:
            v25 = -25130;
          }
          goto LABEL_467;
        case 1216:
          if ( !g_fPerfStatLogEnabled )
            goto LABEL_326;
          if ( !(unsigned __int16)PrintStatistics((const OLECHAR *)v9, (void *)0x383800000LL, v11) )
            goto LABEL_531;
          v25 = -25130;
          goto LABEL_467;
        case 1217:
          if ( v9 > 1 )
          {
            v109 = -25337;
            goto LABEL_35;
          }
          if ( v9 == *((_QWORD *)hdbc + 1042) )
            goto LABEL_531;
          if ( !*((_QWORD *)hdbc + 8) )
            goto LABEL_525;
          v9 = (unsigned __int64)rgbValuea;
          v64 = 261;
          v65 = WideCharStr;
          if ( rgbValuea == (SQLPOINTER)1 )
          {
            v13 = (char *)L"set quoted_identifier on" - (char *)WideCharStr;
            while ( v64 != -2147483385 )
            {
              v66 = *(WCHAR *)((char *)v65 + v13);
              if ( !v66 )
                break;
              *v65++ = v66;
              if ( !--v64 )
                goto LABEL_277;
            }
          }
          else
          {
            v13 = (char *)L"set quoted_identifier off" - (char *)WideCharStr;
            while ( v64 != -2147483385 )
            {
              v67 = *(WCHAR *)((char *)v65 + v13);
              if ( !v67 )
                break;
              *v65++ = v67;
              if ( !--v64 )
              {
LABEL_277:
                --v65;
                break;
              }
            }
          }
          *v65 = 0;
          *((_DWORD *)hdbc + 2694) = -2147483640;
          *((_DWORD *)hdbc + 2689) = 0;
LABEL_64:
          v26 = 0;
          v27 = *((_QWORD *)hdbc + 1003) + 304LL;
          if ( *((_QWORD *)hdbc + 1003) != -304 )
          {
            v26 = *(_QWORD *)v27;
            (*(void (__fastcall **)(__int64, signed __int64))(*(_QWORD *)(*(_QWORD *)v27 + 32LL) + 8LL))(
              *(_QWORD *)v27 + 32LL,
              v13);
          }
          v28 = (struct tagSTMT *)*((_QWORD *)hdbc + 1003);
          v113 = 0;
          v114 = 0;
          if ( (int)GetBatchCtxFromStmt(v28, &v119, (struct CAutoBatchCtx_ODBC *)&v113) < 0 )
          {
            v10 = -1;
            if ( (bidGblFlags & 2) != 0 )
            {
              if ( off_383B49120[0] )
                bidTraceW(off_383B431E8[0], 1661961, off_383B49120[0], 1623);
              v9 = (unsigned __int64)rgbValuea;
            }
            v29 = v114;
            if ( v114 )
            {
              v30 = v113;
              v14 = (*(_DWORD *)(v113 + 1120))-- == 1;
              if ( v14 && !*(_QWORD *)(v29 + 96) )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v30 + 312) + 32LL) + 8LL))(*(_QWORD *)(v30 + 312) + 32LL);
                BATCHCTX::Release(*(BATCHCTX **)(v30 + 1112));
                *(_QWORD *)(v30 + 1112) = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v30 + 312) + 32LL) + 24LL))(*(_QWORD *)(v30 + 312) + 32LL);
              }
            }
            if ( v26 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)(v26 + 32) + 24LL))(v26 + 32);
            goto LABEL_35;
          }
          v10 = ExecImmediate(*((struct tagSTMT **)hdbc + 1003), WideCharStr, -3, *((_DWORD *)hdbc + 2250), 0);
          if ( v10 == 2 )
          {
            v68 = v114;
            *((_DWORD *)hdbc + 2694) &= ~0x80000000;
            if ( v68 )
            {
              v69 = v113;
              v14 = (*(_DWORD *)(v113 + 1120))-- == 1;
              if ( v14 && !*(_QWORD *)(v68 + 96) )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v69 + 312) + 32LL) + 8LL))(*(_QWORD *)(v69 + 312) + 32LL);
                BATCHCTX::Release(*(BATCHCTX **)(v69 + 1112));
                *(_QWORD *)(v69 + 1112) = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v69 + 312) + 32LL) + 24LL))(*(_QWORD *)(v69 + 312) + 32LL);
              }
            }
            if ( v26 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)(v26 + 32) + 24LL))(v26 + 32);
            break;
          }
          *((_DWORD *)hdbc + 2694) = 0;
          *((_DWORD *)hdbc + 2689) = 0;
          if ( v10 )
            XferErrors((struct tagOBJBASE *)hdbc, *((struct tagOBJBASE **)hdbc + 1003));
          SQLFreeStmt(*((SQLHSTMT *)hdbc + 1003), 0);
          v70 = v114;
          if ( v114 )
          {
            v71 = v113;
            v14 = (*(_DWORD *)(v113 + 1120))-- == 1;
            if ( v14 && !*(_QWORD *)(v70 + 96) )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v71 + 312) + 32LL) + 8LL))(*(_QWORD *)(v71 + 312) + 32LL);
              BATCHCTX::Release(*(BATCHCTX **)(v71 + 1112));
              *(_QWORD *)(v71 + 1112) = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v71 + 312) + 32LL) + 24LL))(*(_QWORD *)(v71 + 312) + 32LL);
            }
          }
          if ( v26 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)(v26 + 32) + 24LL))(v26 + 32);
          goto LABEL_531;
        case 1219:
          if ( v9 != 1 || *((_QWORD *)hdbc + 1023) != 1 )
            goto LABEL_260;
          v25 = -25355;
          goto LABEL_467;
        case 1220:
          if ( v9 == 1 )
          {
            *((_WORD *)hdbc + 5056) |= 2u;
            goto LABEL_531;
          }
          if ( v9 )
            goto LABEL_210;
          v63 = -3;
          goto LABEL_250;
        case 1221:
        case 1225:
        case 1226:
        case 1229:
        case 1230:
        case 1247:
          goto LABEL_438;
        case 1223:
          v9 = (unsigned __int64)rgbValuea;
          if ( *((_QWORD *)hdbc + 8) )
          {
            v25 = -25373;
            goto LABEL_467;
          }
          if ( (unsigned __int64)rgbValuea < 2 )
            goto LABEL_531;
          v25 = -25369;
          goto LABEL_467;
        case 1224:
        case 1228:
          v9 = (unsigned __int64)rgbValuea;
          if ( *((_QWORD *)hdbc + 8) )
          {
            v25 = -25373;
            goto LABEL_467;
          }
          if ( (unsigned __int64)rgbValuea < 2 )
            goto LABEL_531;
          v25 = -25369;
          goto LABEL_467;
        case 1227:
          fAttribute = 108;
          goto LABEL_223;
        case 1231:
        case 1232:
        case 1233:
          goto LABEL_205;
        case 1241:
          if ( v9 >= 2 )
          {
            v109 = -25337;
            goto LABEL_35;
          }
          *((_DWORD *)hdbc + 2529) = v9;
          break;
        case 1242:
          if ( v9 )
          {
            v87 = -1;
            do
              ++v87;
            while ( *(_WORD *)(v9 + 2 * v87) );
            if ( v87 > 0x80 )
            {
              v109 = -25371;
              goto LABEL_35;
            }
            v88 = (char *)hdbc + 10498;
            v89 = 129;
            v90 = v9 - ((_QWORD)hdbc + 10498);
            while ( v89 != -2147483517 )
            {
              v91 = *(_WORD *)((char *)v88 + v90);
              if ( !v91 )
                break;
              *v88++ = v91;
              if ( !--v89 )
              {
                *(v88 - 1) = 0;
                goto LABEL_39;
              }
            }
            *v88 = 0;
          }
          else
          {
            *((_WORD *)hdbc + 5249) = 0;
          }
          break;
        case 1243:
          if ( v9 >= 2 )
          {
            v109 = -25337;
            goto LABEL_35;
          }
          *((_DWORD *)hdbc + 2530) = v9;
          break;
        case 1245:
          if ( v9 >= 2 )
          {
            v109 = -25337;
            goto LABEL_35;
          }
          *((_DWORD *)hdbc + 2531) = v9;
          break;
        case 1246:
          if ( v9 != 1 )
          {
            v109 = -25337;
            goto LABEL_35;
          }
          if ( (*((_BYTE *)hdbc + 10148) & 8) == 0 )
            break;
          if ( !*((_QWORD *)hdbc + 8) || *(_BYTE *)(*((_QWORD *)hdbc + 8) + 1246LL) < 9u )
            goto LABEL_26;
          if ( !*((_QWORD *)hdbc + 8) || *(_BYTE *)(*((_QWORD *)hdbc + 8) + 1246LL) < 9u )
          {
            if ( (*((_WORD *)hdbc + 5056) & 1) == 0 )
              goto LABEL_26;
            goto LABEL_386;
          }
          if ( *((_QWORD *)hdbc + 8)
            && *(_QWORD *)(*((_QWORD *)hdbc + 8) + 368LL)
            && !*(_DWORD *)(*((_QWORD *)hdbc + 8) + 376LL) )
          {
LABEL_386:
            memset(v120, 0, 0x20Au);
            *((_DWORD *)hdbc + 2694) = -2147483634;
            v120[0] = 8;
            *((_DWORD *)hdbc + 2689) = 0;
            *((_DWORD *)hdbc + 2695) = 1;
            goto LABEL_387;
          }
LABEL_26:
          v15 = (char *)hdbc + 2262;
          v16 = 129;
          *(_DWORD *)(*((_QWORD *)hdbc + 8) + 340LL) = 1;
          *((_QWORD *)hdbc + 1124) = 0;
          *((_QWORD *)hdbc + 1123) = 0;
          v17 = 129;
          while ( v17 != -2147483517 )
          {
            v18 = v15[1689];
            if ( !v18 )
              break;
            *v15++ = v18;
            if ( !--v17 )
            {
              --v15;
              break;
            }
          }
          *v15 = 0;
          v107 = (char *)hdbc + 2004;
          while ( v16 != -2147483517 )
          {
            v108 = v107[1689];
            if ( !v108 )
              break;
            *v107++ = v108;
            if ( !--v16 )
            {
              --v107;
              break;
            }
          }
          *v107 = 0;
          *((_DWORD *)hdbc + 2253) = *(_DWORD *)((char *)hdbc + 5898);
          *((_BYTE *)hdbc + 9016) = *((_BYTE *)hdbc + 5902);
          *((_WORD *)hdbc + 5056) &= ~0x40u;
          if ( BuildServerSideConnectOptions(
                 (struct tagDBC *)hdbc,
                 v123,
                 (unsigned __int64)&v115,
                 (unsigned __int64 *)0xFFFFFFFFFFFFF72ALL) < 0 )
          {
            v10 = -1;
            if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
              bidTraceW(off_383B431E8[0], 2024457, off_383B49120[0], 1977);
          }
          else if ( v115 )
          {
            *((_DWORD *)hdbc + 2694) = -2147483634;
            *((_DWORD *)hdbc + 2695) = 2;
            *((_DWORD *)hdbc + 2689) = 0;
LABEL_397:
            v85 = *((_QWORD *)hdbc + 1003) + 304LL;
            if ( *((_QWORD *)hdbc + 1003) != -304 )
            {
              v86 = *(_QWORD *)v85;
              (*(void (__fastcall **)(__int64, signed __int64))(*(_QWORD *)(*(_QWORD *)v85 + 32LL) + 8LL))(
                *(_QWORD *)v85 + 32LL,
                v13);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)(v86 + 32) + 24LL))(v86 + 32);
            }
            v10 = ExecImmediate(*((struct tagSTMT **)hdbc + 1003), v123, v115, *((_DWORD *)hdbc + 2250), 0);
            if ( v10 == 2 )
            {
              *((_DWORD *)hdbc + 2694) &= ~0x80000000;
            }
            else
            {
              *((_DWORD *)hdbc + 2694) = 0;
              *((_DWORD *)hdbc + 2689) = 0;
              if ( v10 )
                XferErrors((struct tagOBJBASE *)hdbc, *((struct tagOBJBASE **)hdbc + 1003));
              SQLFreeStmt(*((SQLHSTMT *)hdbc + 1003), 0);
              *((_WORD *)hdbc + 5056) &= ~1u;
            }
          }
          break;
        default:
          goto LABEL_33;
      }
LABEL_39:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)hdbc + 1000) + 32LL) + 24LL))(*((_QWORD *)hdbc + 1000) + 32LL);
      v21 = bidGblFlags;
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( v10 || (v21 = bidGblFlags, (bidGblFlags & 0x40) != 0) )
        {
          v106 = 2364417;
          if ( v10 )
            v106 = 2364449;
          bidTraceW(off_383B431E8[0], v106, off_383B494E8[0], (unsigned int)v10);
          v21 = bidGblFlags;
        }
      }
      if ( v117 != -1 && (v21 & 4) != 0 && bidID != -1 )
        off_383B15058();
      return v10;
  }
}

```

## disassembly

```asm
0x38386d8d0  push    rbp
0x38386d8d2  push    rbx
0x38386d8d3  push    rsi
0x38386d8d4  push    rdi
0x38386d8d5  push    r12
0x38386d8d7  push    r13
0x38386d8d9  push    r14
0x38386d8db  push    r15
0x38386d8dd  lea     rbp, [rsp-0FD8h]
0x38386d8e5  mov     eax, 10D8h
0x38386d8ea  call    _alloca_probe
0x38386d8ef  sub     rsp, rax
0x38386d8f2  mov     rax, cs:__security_cookie
0x38386d8f9  xor     rax, rsp
0x38386d8fc  mov     [rbp+1010h+var_50], rax
0x38386d903  mov     rdi, rcx
0x38386d906  mov     ebx, r9d
0x38386d909  mov     r12, r8
0x38386d90c  mov     r14d, edx
0x38386d90f  xor     r13d, r13d
0x38386d912  mov     eax, 9D07h
0x38386d917  mov     rsi, r8
0x38386d91a  mov     [rsp+1110h+rgbValue], r8
0x38386d91f  lea     rcx, [rbp+1010h+var_E5E]; void *
0x38386d926  mov     r8d, 208h; Size
0x38386d92c  xor     edx, edx; Val
0x38386d92e  mov     [rsp+1110h+cbMultiByte], rbx
0x38386d933  movzx   r15d, r13w
0x38386d937  mov     [rsp+1110h+var_10D0], ax
0x38386d93c  mov     [rbp+1010h+WideCharStr], r13w
0x38386d944  call    memset
0x38386d949  xor     eax, eax
0x38386d94b  mov     [rsp+1110h+var_10B8], rax
0x38386d950  mov     [rsp+1110h+var_10A0], rax
0x38386d955  or      rax, 0FFFFFFFFFFFFFFFFh
0x38386d959  test    byte ptr cs:_bidGblFlags, 4
0x38386d960  mov     [rbp+1010h+var_1090], rax
0x38386d964  jnz     loc_38386DC05
0x38386d96a  mov     rcx, [rdi+1F40h]
0x38386d971  mov     rax, [rcx+20h]
0x38386d975  add     rcx, 20h ; ' '
0x38386d979  call    qword ptr [rax+8]
0x38386d97c  test    byte ptr [rdi+18h], 10h
0x38386d980  jnz     loc_38386DC3F
0x38386d986  cmp     r14d, 74h ; 't'
0x38386d98a  jnz     loc_38389D6BF
0x38386d990  mov     r14d, 4DEh
0x38386d996  mov     eax, [rdi+2A18h]
0x38386d99c  lea     rdx, cs:383800000h; void *
0x38386d9a3  add     eax, 0FFFFFFFEh; switch 13 cases
0x38386d9a6  cmp     eax, 0Ch
0x38386d9a9  jbe     loc_38386DCA5
0x38386d9af  cmp     r14d, 4CAh; jumptable 000000038386DCAF default case, cases 4-7
0x38386d9b6  jle     loc_38389D6D1
0x38386d9bc  mov     ecx, r14d
0x38386d9bf  sub     ecx, 4DAh
0x38386d9c5  jz      loc_38386E18B
0x38386d9cb  sub     ecx, 5
0x38386d9ce  jz      loc_38386E18B
0x38386d9d4  sub     ecx, 8CC4h
0x38386d9da  jz      loc_38386E18B
0x38386d9e0  dec     ecx
0x38386d9e2  jz      loc_38386DEAC
0x38386d9e8  cmp     ecx, 2
0x38386d9eb  jmp     short $+2
0x38386d9ed  jz      loc_38386E18B
0x38386d9f3  xor     r12d, r12d
0x38386d9f6  cmp     r14d, 4B0h
0x38386d9fd  jle     loc_38386DB03
0x38386da03  cmp     r14d, 2711h
0x38386da0a  jg      loc_38386F27D
0x38386da10  jz      loc_38386E5B2; jumptable 000000038386DA32 cases 1231-1233
0x38386da16  lea     eax, [r14-4B2h]; switch 47 cases
0x38386da1d  cmp     eax, 2Eh
0x38386da20  ja      def_38386DA32; jumptable 000000038386DA32 default case, cases 1209,1234-1240,1244
0x38386da26  cdqe
0x38386da28  mov     ecx, ds:(jpt_38386DA32 - 383800000h)[rdx+rax*4]
0x38386da2f  add     rcx, rdx
0x38386da32  jmp     rcx; switch jump
0x38386da34  cmp     rsi, 1; jumptable 000000038386DA32 case 1246
0x38386da38  jnz     loc_38386EF92
0x38386da3e  test    byte ptr [rdi+27A4h], 8
0x38386da45  jz      loc_38386DBB0
0x38386da4b  mov     rax, [rdi+40h]
0x38386da4f  test    rax, rax
0x38386da52  jz      short loc_38386DA99
0x38386da54  mov     rax, [rdi+40h]
0x38386da58  cmp     byte ptr [rax+4DEh], 9
0x38386da5f  jb      short loc_38386DA99
0x38386da61  mov     rax, [rdi+40h]
0x38386da65  test    rax, rax
0x38386da68  jz      loc_38386EFB9
0x38386da6e  mov     rax, [rdi+40h]
0x38386da72  cmp     byte ptr [rax+4DEh], 9
0x38386da79  jb      loc_38386EFB9
0x38386da7f  mov     rax, [rdi+40h]
0x38386da83  test    rax, rax
0x38386da86  jz      short loc_38386DA99
0x38386da88  mov     rax, [rdi+40h]
0x38386da8c  cmp     [rax+170h], r13
0x38386da93  jnz     loc_38386EFA1
0x38386da99  mov     r12d, 1
0x38386da9f  mov     rax, [rdi+40h]
0x38386daa3  lea     rcx, [rdi+8D6h]
0x38386daaa  mov     edx, 81h
0x38386daaf  mov     [rax+154h], r12d
0x38386dab6  xor     r12d, r12d
0x38386dab9  mov     r9, rdi
0x38386dabc  mov     [rdi+2320h], r12
0x38386dac3  mov     [rdi+2318h], r12
0x38386daca  mov     r8d, edx
0x38386dacd  sub     r9, rcx; unsigned __int64 *
0x38386dad0  lea     rax, [r8+7FFFFF7Dh]
0x38386dad7  test    rax, rax
0x38386dada  jz      loc_383870C5A
0x38386dae0  movzx   eax, word ptr [r9+rcx+1608h]
0x38386dae9  test    ax, ax
0x38386daec  jz      loc_383870C5A
0x38386daf2  mov     [rcx], ax
0x38386daf5  add     rcx, 2
0x38386daf9  dec     r8
0x38386dafc  jnz     short loc_38386DAD0
0x38386dafe  jmp     loc_38386EFB4
0x38386db03  jz      loc_38386E859; jumptable 000000038386DA32 cases 1203,1210,1218,1222,1248
0x38386db09  lea     eax, [r14-65h]; switch 17 cases
0x38386db0d  cmp     eax, 10h
0x38386db10  ja      short def_38386DA32; jumptable 000000038386DA32 default case, cases 1209,1234-1240,1244
0x38386db12  cdqe
0x38386db14  mov     ecx, ds:(jpt_38386DB1E - 383800000h)[rdx+rax*4]
0x38386db1b  add     rcx, rdx
0x38386db1e  jmp     rcx; switch jump
0x38386db20  mov     r11, [rsp+1110h+cbMultiByte]; jumptable 000000038386DA32 default case, cases 1209,1234-1240,1244
0x38386db25  lea     r9, [rsp+1110h+rgbValue]; void *
0x38386db2a  mov     r8d, r14d; int
0x38386db2d  xor     edx, edx; struct tagSTMT *
0x38386db2f  mov     rcx, rdi; struct tagDBC *
0x38386db32  mov     dword ptr [rsp+1110h+lpBuffer], r11d; int
0x38386db37  call    ?IsSetStmtOptionValid@@YAGPEAUtagDBC@@PEAUtagSTMT@@JPEAXJ@Z; IsSetStmtOptionValid(tagDBC *,tagSTMT *,long,void *,long)
0x38386db3c  mov     rsi, [rsp+1110h+rgbValue]
0x38386db41  mov     r12d, 0FFFEh
0x38386db47  mov     [rsp+1110h+var_10D0], ax
0x38386db4c  test    ax, ax
0x38386db4f  jz      loc_38386F546
0x38386db55  cmp     [rsp+1110h+var_10D0], 1
0x38386db5b  jz      loc_38386F4B7
0x38386db61  or      rbx, 0FFFFFFFFFFFFFFFFh
0x38386db65  test    byte ptr cs:_bidGblFlags, 2
0x38386db6c  jnz     loc_38386F50D
0x38386db72  movzx   edx, [rsp+1110h+var_10D0]; unsigned __int16
0x38386db77  mov     r9, rbx; unsigned __int64
0x38386db7a  xor     r8d, r8d; int
0x38386db7d  mov     rcx, rdi; struct tagOBJBASE *
0x38386db80  mov     dword ptr [rsp+1110h+lpBuffer], 0FFFFFFFFh; unsigned int
0x38386db88  call    ?PostSQLErrorEx@@YAFPEAUtagOBJBASE@@GJ_KK@Z; PostSQLErrorEx(tagOBJBASE *,ushort,long,unsigned __int64,ulong)
0x38386db8d  jmp     short $+2
0x38386db8f  mov     eax, 9E04h
0x38386db94  cmp     [rsp+1110h+var_10D0], ax
0x38386db99  jz      loc_38386F541
0x38386db9f  test    byte ptr cs:_bidGblFlags, 2
0x38386dba6  movzx   r15d, bx
0x38386dbaa  jnz     loc_38386F4C0
0x38386dbb0  mov     rcx, [rdi+1F40h]
0x38386dbb7  mov     rax, [rcx+20h]
0x38386dbbb  add     rcx, 20h ; ' '
0x38386dbbf  call    qword ptr [rax+18h]
0x38386dbc2  mov     r11d, cs:_bidGblFlags
0x38386dbc9  test    r11b, 2
0x38386dbcd  jnz     loc_38386F64B
0x38386dbd3  cmp     [rbp+1010h+var_1090], 0FFFFFFFFFFFFFFFFh
0x38386dbd8  jnz     loc_38386F696
0x38386dbde  movzx   eax, r15w
0x38386dbe2  mov     rcx, [rbp+1010h+var_50]
0x38386dbe9  xor     rcx, rsp; StackCookie
0x38386dbec  call    __security_check_cookie
0x38386dbf1  add     rsp, 10D8h
0x38386dbf8  pop     r15
0x38386dbfa  pop     r14
0x38386dbfc  pop     r13
0x38386dbfe  pop     r12
0x38386dc00  pop     rdi
0x38386dc01  pop     rsi
0x38386dc02  pop     rbx
0x38386dc03  pop     rbp
0x38386dc04  retn
0x38386dc05  mov     rax, cs:off_383B4A8B0; "<SQLSetConnectAttrW|API|ODBC|DRIVER> %u"...
0x38386dc0c  test    rax, rax
0x38386dc0f  jz      short loc_38386DC35
0x38386dc11  mov     r8d, [rdi]
0x38386dc14  mov     rdx, cs:off_383B4A8B0; "<SQLSetConnectAttrW|API|ODBC|DRIVER> %u"...
0x38386dc1b  mov     dword ptr [rsp+1110h+Arguments], ebx
0x38386dc1f  lea     rcx, [rbp+1010h+var_1090]
0x38386dc23  mov     r9, rdi
0x38386dc26  mov     qword ptr [rsp+1110h+nSize], rsi
0x38386dc2b  mov     dword ptr [rsp+1110h+lpBuffer], r14d
0x38386dc30  call    _bidScopeEnterW
0x38386dc35  mov     rsi, [rsp+1110h+rgbValue]
0x38386dc3a  jmp     loc_38386D96A
0x38386dc3f  cmp     r14d, 91B4h
0x38386dc46  jnz     short loc_38386DC52
0x38386dc48  cmp     r12, 1
0x38386dc4c  jz      loc_38386D996
0x38386dc52  test    byte ptr [rdi+18h], 4
0x38386dc56  jnz     loc_38386D986
0x38386dc5c  mov     rdx, [rdi+8]
0x38386dc60  test    rdx, rdx
0x38386dc63  jz      short loc_38386DC87
0x38386dc65  nop     word ptr [rax+rax]
0x38386dc6a  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x38386dc71  mov     rbx, [rdx]
0x38386dc74  mov     rax, [rcx]
0x38386dc77  call    qword ptr [rax+28h]
0x38386dc7a  mov     rdx, rbx
0x38386dc7d  test    rbx, rbx
0x38386dc80  jnz     short loc_38386DC6A
0x38386dc82  mov     rbx, [rsp+1110h+cbMultiByte]
0x38386dc87  xor     eax, eax
0x38386dc89  mov     [rdi+8], rax
0x38386dc8d  mov     [rdi+10h], rax
0x38386dc91  mov     [rdi+18h], ax
0x38386dc95  jmp     loc_38386D986
0x38386dc9a  mov     r14d, 6Dh ; 'm'
0x38386dca0  jmp     loc_38386D996
0x38386dca5  mov     ecx, ds:(jpt_38386DCAF - 383800000h)[rdx+rax*4]
0x38386dcac  add     rcx, rdx
0x38386dcaf  jmp     rcx; switch jump
0x38386dcb1  cmp     r14d, 6Dh ; 'm'; jumptable 000000038386DCAF case 3
0x38386dcb5  jz      loc_38386E3EC
0x38386dcbb  mov     eax, 9CE2h
0x38386dcc0  jmp     loc_38386F4FD
0x38386dcc5  cmp     r14d, 65h ; 'e'; jumptable 000000038386DCAF case 9
0x38386dcc9  jnz     short loc_38386DCBB
0x38386dccb  xor     r12d, r12d
0x38386dcce  lea     rdx, [rsp+1110h+var_1098]; int *
0x38386dcd3  mov     rcx, rdi; struct tagDBC *
0x38386dcd6  call    ?IsDataBaseReadOnly@@YAFPEAUtagDBC@@PEAH@Z; IsDataBaseReadOnly(tagDBC *,int *)
0x38386dcdb  movzx   r15d, ax
0x38386dcdf  cmp     ax, 2
0x38386dce3  jnz     loc_38386E239
0x38386dce9  and     dword ptr [rdi+2A18h], 7FFFFFFFh
0x38386dcf3  jmp     loc_38386DBB0
0x38386dcf8  cmp     r14d, 66h ; 'f'; jumptable 000000038386DCAF cases 2,10
0x38386dcfc  jz      loc_38386E2AE
0x38386dd02  mov     eax, 9CE2h
0x38386dd07  jmp     loc_38386F4FD
0x38386dd0c  cmp     r14d, 6Ch ; 'l'; jumptable 000000038386DCAF case 11
0x38386dd10  jz      short loc_38386DD1B
0x38386dd12  cmp     r14d, 4CBh
0x38386dd19  jnz     short loc_38386DCBB
0x38386dd1b  mov     r14d, 6Ch ; 'l'
0x38386dd21  xor     r12d, r12d
0x38386dd24  jmp     loc_38386E73B
0x38386dd29  cmp     r14d, 4C1h; jumptable 000000038386DCAF case 8
0x38386dd30  jnz     short loc_38386DCBB
0x38386dd32  xor     r12d, r12d
0x38386dd35  mov     rax, [rdi+1F58h]
0x38386dd3c  mov     rbx, r12
0x38386dd3f  add     rax, 130h
0x38386dd45  jz      short loc_38386DD55
0x38386dd47  mov     rbx, [rax]
0x38386dd4a  mov     rax, [rbx+20h]
0x38386dd4e  lea     rcx, [rbx+20h]
0x38386dd52  call    qword ptr [rax+8]
0x38386dd55  mov     rcx, [rdi+1F58h]; struct tagSTMT *
0x38386dd5c  lea     r8, [rsp+1110h+var_10B0]; struct CAutoBatchCtx_ODBC *
0x38386dd61  lea     rdx, [rbp+1010h+var_1080]; struct BATCHCTX **
0x38386dd65  mov     [rsp+1110h+var_10B0], r12
0x38386dd6a  mov     [rsp+1110h+var_10A8], r12
0x38386dd6f  call    ?GetBatchCtxFromStmt@@YAJPEAUtagSTMT@@PEAPEAVBATCHCTX@@PEAVCAutoBatchCtx_ODBC@@@Z; GetBatchCtxFromStmt(tagSTMT *,BATCHCTX * *,CAutoBatchCtx_ODBC *)
0x38386dd74  test    eax, eax
0x38386dd76  jns     loc_38386E936
0x38386dd7c  or      r15, 0FFFFFFFFFFFFFFFFh
0x38386dd80  test    byte ptr cs:_bidGblFlags, 2
0x38386dd87  jz      short loc_38386DDB8
0x38386dd89  mov     rcx, cs:off_383B431E8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x38386dd90  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x38386dd97  test    rax, rax
0x38386dd9a  jz      short loc_38386DDB3
0x38386dd9c  mov     r8, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x38386dda3  mov     r9d, 657h
0x38386dda9  mov     edx, 195C09h
0x38386ddae  call    _bidTraceW
0x38386ddb3  mov     rsi, [rsp+1110h+rgbValue]
0x38386ddb8  mov     rax, [rsp+1110h+var_10A8]
0x38386ddbd  test    rax, rax
0x38386ddc0  jz      short loc_38386DE0E
0x38386ddc2  mov     r13, [rsp+1110h+var_10B0]
0x38386ddc7  dec     dword ptr [r13+460h]
0x38386ddce  jnz     short loc_38386DE0E
0x38386ddd0  cmp     qword ptr [rax+60h], 0
0x38386ddd5  jnz     short loc_38386DE0E
0x38386ddd7  mov     rcx, [r13+138h]
0x38386ddde  mov     rax, [rcx+20h]
0x38386dde2  add     rcx, 20h ; ' '
0x38386dde6  call    qword ptr [rax+8]
0x38386dde9  mov     rcx, [r13+458h]; this
0x38386ddf0  call    ?Release@BATCHCTX@@QEAAKXZ; BATCHCTX::Release(void)
0x38386ddf5  mov     [r13+458h], r12
0x38386ddfc  mov     rcx, [r13+138h]
0x38386de03  mov     rax, [rcx+20h]
0x38386de07  add     rcx, 20h ; ' '
  ... truncated ...
```
