# MapAndConvertPropsEx(ulong,ulong *,ulong *,ulong,JET_ENUMCOLUMN const *,uchar * *,ulong *)

- ea: `0x18000b9d0`
- end: `0x18000c608`
- name: `?MapAndConvertPropsEx@@YAJKPEAK0KPEBUJET_ENUMCOLUMN@@PEAPEAE0@Z`
- size: `3128`
- prototype: `__int64 __fastcall(unsigned int, unsigned int *, unsigned int *, unsigned int, const struct JET_ENUMCOLUMN *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b350`

## callees

- `0x1800068f0`
- `0x18000b9d0`
- `0x18000d9c0`
- `0x18000f530`
- `0x18006816c`
- `0x18006f180`
- `0x1800c5092`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000bb69`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000bcea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000be04`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000c08e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000bb69`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000bcea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000be04`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000c08e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000baaf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000bc14`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000baaf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000bc14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bd0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c12e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c455`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c51e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bd0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c12e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c455`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c51e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c04b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c04b`

## string_xrefs

- `0x18000bb3f`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000bb56`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000bb75`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000bcc0`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000bcd7`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000bcfd`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000bd83`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000c063`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000c0d3`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000c10f`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000c191`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000c219`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000c268`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000c30d`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000c37c`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000c3b4`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000c508`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000c552`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`

## pseudocode

```c
__int64 __fastcall MapAndConvertPropsEx(
        unsigned int a1,
        unsigned int *a2,
        unsigned int *a3,
        unsigned int a4,
        const struct JET_ENUMCOLUMN *a5,
        unsigned __int8 **a6,
        unsigned int *a7)
{
  unsigned int v7; // r15d
  const struct JET_ENUMCOLUMN *v8; // rbp
  unsigned int v9; // r12d
  unsigned __int64 v10; // r13
  unsigned __int64 v11; // rbx
  unsigned int v12; // r14d
  JET_ERR err; // eax
  JET_COLUMNID columnid; // edi
  __int64 v15; // rcx
  int *v16; // rbx
  __int64 v17; // rsi
  __int64 v18; // r9
  unsigned int HresultFromJetError; // ebx
  unsigned int v20; // r10d
  unsigned int v21; // r9d
  char *v22; // r11
  unsigned int v23; // r14d
  int v24; // ebx
  __int64 v25; // r15
  JET_COLUMNID v26; // r13d
  unsigned __int64 v27; // rcx
  _DWORD *v28; // rbx
  __int64 v29; // rbp
  unsigned __int64 v30; // rsi
  const struct PropIdAndColumnDetails *v31; // r14
  bool v32; // dl
  _DWORD *v33; // rax
  __int64 v34; // r9
  __int64 v35; // r9
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v39; // rax
  __int64 v40; // r9
  unsigned int *v41; // rcx
  __int64 v42; // r8
  unsigned int v43; // ecx
  int v44; // edx
  bool v45; // sf
  __int64 v46; // r12
  JET_ERR v47; // eax
  int v48; // r13d
  unsigned int v49; // esi
  char *v50; // r9
  unsigned int v51; // ebp
  __int64 v52; // r15
  __int64 v53; // rcx
  __int64 v54; // rax
  int *v55; // r14
  size_t v56; // r8
  __int64 v57; // rdx
  int v58; // eax
  __int64 v59; // rcx
  __int64 v60; // rbx
  __int64 v61; // rax
  char *v62; // rax
  char *v63; // rdi
  int v64; // ebx
  __int64 v65; // rcx
  JET_ERR v66; // eax
  __int64 v67; // r8
  __int64 v68; // rax
  __int64 v69; // rax
  BOOL v70; // edx
  __int16 v71; // ax
  __int64 v72; // rcx
  __int64 i; // rcx
  JET_ENUMCOLUMNVALUE *rgEnumColumnValue; // r9
  JET_ERR v75; // eax
  __int64 cEnumColumnValue; // rax
  unsigned int v77; // [rsp+30h] [rbp-D8h]
  int v78; // [rsp+34h] [rbp-D4h]
  int v79; // [rsp+38h] [rbp-D0h]
  char *v80; // [rsp+40h] [rbp-C8h]
  int v81; // [rsp+48h] [rbp-C0h]
  unsigned int v82; // [rsp+4Ch] [rbp-BCh]
  unsigned int v83; // [rsp+50h] [rbp-B8h]
  unsigned __int64 v85; // [rsp+58h] [rbp-B0h]
  char *v86; // [rsp+58h] [rbp-B0h]
  unsigned int v88; // [rsp+64h] [rbp-A4h]
  __int128 v89; // [rsp+78h] [rbp-90h] BYREF
  char *v90; // [rsp+88h] [rbp-80h]
  __int64 v91; // [rsp+90h] [rbp-78h]
  unsigned int *v92; // [rsp+98h] [rbp-70h]
  unsigned int *v93; // [rsp+A0h] [rbp-68h]
  unsigned __int8 **v94; // [rsp+A8h] [rbp-60h]
  __int64 v95; // [rsp+B0h] [rbp-58h]
  __int128 v96; // [rsp+B8h] [rbp-50h] BYREF

  v7 = a4;
  v8 = a5;
  v9 = a4;
  v92 = a3;
  v94 = a6;
  v93 = a2;
  *a6 = 0;
  *a7 = 0;
  if ( *a2 )
    v7 = *a2;
  v88 = v7;
  *(_QWORD *)&v89 = 0;
  v10 = 40LL * v7;
  if ( !is_mul_ok(0x28u, v7) )
  {
    Log_UnistoreHREvent_0(
      2147942934LL,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
      2206);
    return 2147942934LL;
  }
  v11 = 0;
  v12 = 0;
  v85 = 0;
  while ( v12 < v9 )
  {
    err = v8[v12].err;
    if ( !err || err == 1534 )
    {
      cEnumColumnValue = v8[v12].cEnumColumnValue;
      if ( (unsigned int)cEnumColumnValue > 1 )
      {
        if ( v11 + cEnumColumnValue < v11 )
        {
          v40 = 2214;
          goto LABEL_39;
        }
        v85 = v11 + cEnumColumnValue;
      }
    }
    columnid = v8[v12].columnid;
    AcquireSRWLockShared(&g_columnIdMapping);
    if ( !dword_18010D248 )
    {
      v18 = 252;
LABEL_16:
      HresultFromJetError = -2147418113;
      Log_UnistoreHREvent_0(
        2147549183LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
        v18);
      ReleaseSRWLockShared(&g_columnIdMapping);
      Log_UnistoreHREvent_0(
        2147549183LL,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
        2218);
      return HresultFromJetError;
    }
    v89 = 0;
    DWORD1(v89) = columnid;
    v16 = (int *)*((_QWORD *)&g_columnIdMapping + 3 * a1 + 271);
    v17 = (__int64)(*((_QWORD *)&g_columnIdMapping + 3 * a1 + 272) - (_QWORD)v16) >> 4;
    if ( v17 > 0 )
    {
      do
      {
        if ( CompareColumns(
               (const struct PropIdAndColumnDetails *)&v16[4 * ((unsigned __int64)v17 >> 1)],
               (const struct PropIdAndColumnDetails *)&v89) )
        {
          v16 += 4 * ((unsigned __int64)v17 >> 1) + 4;
          v17 += -1LL - ((unsigned __int64)v17 >> 1);
        }
        else
        {
          v17 = (unsigned __int64)v17 >> 1;
        }
      }
      while ( v17 > 0 );
      v8 = a5;
    }
    if ( v16 == *((int **)&g_columnIdMapping + 3 * a1 + 272) || v16[1] != columnid )
    {
      Log_AssertionEvent(
        v15,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
        270);
      v18 = 271;
      goto LABEL_16;
    }
    v64 = *v16;
    ReleaseSRWLockShared(&g_columnIdMapping);
    if ( (unsigned __int16)v64 == 31 || (unsigned __int16)v64 == 65 || (unsigned int)(unsigned __int16)v64 - 100 < 2 )
    {
      v66 = v8[v12].err;
      if ( !v66 || v66 == 1534 )
      {
        for ( i = 0; (unsigned int)i < v8[v12].cEnumColumnValue; i = (unsigned int)(i + 1) )
        {
          rgEnumColumnValue = v8[v12].rgEnumColumnValue;
          v75 = rgEnumColumnValue[i].err;
          if ( !v75 || v75 == 1534 )
          {
            if ( v10 + ((rgEnumColumnValue[i].cbData + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) < v10 )
            {
              v40 = 2233;
              goto LABEL_39;
            }
            v10 += (rgEnumColumnValue[i].cbData + 3LL) & 0xFFFFFFFFFFFFFFFCuLL;
          }
        }
        goto LABEL_91;
      }
      if ( v66 != 1536 )
        goto LABEL_91;
      if ( v10 + ((v8[v12].cEnumColumnValue + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) < v10 )
      {
        v40 = 2239;
        goto LABEL_39;
      }
      v11 = v85;
      v10 += (v8[v12].cEnumColumnValue + 3LL) & 0xFFFFFFFFFFFFFFFCuLL;
      v9 = a4;
      ++v12;
    }
    else
    {
LABEL_91:
      v11 = v85;
      ++v12;
      v9 = a4;
    }
  }
  *(_QWORD *)&v89 = 0;
  v39 = 24 * v11;
  if ( !is_mul_ok(0x18u, v11) )
  {
    v40 = 2246;
    goto LABEL_39;
  }
  *(_QWORD *)&v89 = v39 + v10;
  if ( v39 + v10 < v10 )
  {
    v40 = 2247;
LABEL_39:
    Log_UnistoreHREvent_0(
      2147942934LL,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
      v40);
    return 2147942934LL;
  }
  v62 = (char *)LocalAlloc(0x40u, v39 + v10);
  v63 = v62;
  if ( !v62 )
  {
    Log_UnistoreHREvent_0(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
      2251);
    return 2147942414LL;
  }
  v20 = 0;
  v21 = 0;
  v78 = 0;
  v82 = 0;
  v22 = &v62[40 * v7];
  v86 = v22;
  v80 = &v22[24 * v11];
  v79 = 0;
  v23 = 0;
  while ( 2 )
  {
    v83 = v23;
    if ( v23 < v7 )
    {
      v24 = 0;
      v25 = v20;
      v81 = 0;
      if ( v20 < v9 )
      {
        v26 = v8[v20].columnid;
        AcquireSRWLockShared(&g_columnIdMapping);
        if ( !dword_18010D248 )
        {
          v34 = 252;
LABEL_31:
          HresultFromJetError = -2147418113;
          Log_UnistoreHREvent_0(
            2147549183LL,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
            v34);
          ReleaseSRWLockShared(&g_columnIdMapping);
          v35 = 2268;
          goto LABEL_32;
        }
        v96 = 0;
        DWORD1(v96) = v26;
        v28 = (_DWORD *)*((_QWORD *)&g_columnIdMapping + 3 * a1 + 271);
        v29 = (__int64)(*((_QWORD *)&g_columnIdMapping + 3 * a1 + 272) - (_QWORD)v28) >> 4;
        if ( v29 > 0 )
        {
          do
          {
            v30 = (unsigned __int64)v29 >> 1;
            v31 = (const struct PropIdAndColumnDetails *)&v28[4 * ((unsigned __int64)v29 >> 1)];
            v32 = CompareColumns(v31, (const struct PropIdAndColumnDetails *)&v96);
            if ( v32 )
            {
              v27 = -1LL - v30;
              v29 += -1LL - v30;
            }
            else
            {
              v29 = (unsigned __int64)v29 >> 1;
            }
            v33 = (_DWORD *)((char *)v31 + 16);
            if ( !v32 )
              v33 = v28;
            v28 = v33;
          }
          while ( v29 > 0 );
          v23 = v83;
        }
        if ( v28 == *((_DWORD **)&g_columnIdMapping + 3 * a1 + 272) || v28[1] != v26 )
        {
          Log_AssertionEvent(
            v27,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
            270);
          v34 = 271;
          goto LABEL_31;
        }
        v24 = *v28;
        v81 = v24;
        ReleaseSRWLockShared(&g_columnIdMapping);
        v20 = v78;
        v21 = v82;
        v22 = v86;
        v8 = a5;
        v9 = a4;
      }
      if ( !v92 || (v43 = v92[v23], v43 == v24) )
      {
        if ( v20 >= v9 )
        {
          Log_UnistoreHREvent_0(
            2147942487LL,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
            2279);
          LocalFree(v63);
          return 2147942487LL;
        }
        v42 = 3 * v25;
        v44 = v8[v25].err;
        v91 = 3 * v25;
        if ( v44 != -1507 && v44 != -1517 && v44 != 1531 && v44 != 1004 )
        {
          if ( v44 != 1536 )
            goto LABEL_58;
          if ( v8[v25].cEnumColumnValue )
            goto LABEL_56;
          if ( v8[v25].rgEnumColumnValue )
          {
LABEL_58:
            v45 = v44 < 0;
            if ( v44 )
            {
LABEL_59:
              if ( v45 )
              {
                HresultFromJetError = MakeHresultFromJetError(v44);
                v35 = 2301;
                v36 = 0;
                v37 = HresultFromJetError;
                goto LABEL_33;
              }
              v46 = v21;
              if ( v92 )
                v46 = v23;
              v47 = v8[v20].err;
              if ( v47 && (v48 = 0, v49 = 1, v47 != 1534) || (v48 = 1, (v49 = v8[v20].cEnumColumnValue) != 0) )
              {
                *(_DWORD *)&v63[40 * v46] = v24;
                v50 = &v63[40 * v46];
                v90 = v50;
                if ( v49 <= 1 )
                  goto LABEL_65;
                v51 = 0;
                *((_QWORD *)v50 + 4) = v22;
                *((_WORD *)v50 + 3) = 2048;
                *((_DWORD *)v50 + 6) = v49;
                v86 = &v22[24 * v49];
LABEL_66:
                v52 = 0;
                v53 = (unsigned __int16)v24;
                v77 = (unsigned __int16)v24;
                v54 = 3LL * v20;
                v95 = v54;
                do
                {
                  v55 = (int *)*((_QWORD *)&a5->rgEnumColumnValue + v54);
                  v56 = *(&a5->cEnumColumnValue + 2 * v42);
                  v57 = 24 * v52;
                  if ( v48 )
                  {
                    v56 = (unsigned int)v55[(unsigned __int64)v57 / 4 + 2];
                    v55 = *(int **)&v55[(unsigned __int64)v57 / 4 + 4];
                  }
                  if ( v49 > 1 )
                    *(_DWORD *)(v57 + *((_QWORD *)v50 + 4)) = v24;
                  if ( (_DWORD)v53 == 102 )
                  {
LABEL_72:
                    if ( (_DWORD)v56 != 4 )
                      Log_AssertionEvent(
                        v53,
                        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
                        2390);
                    v58 = *v55;
                    v59 = 5 * v46;
                    if ( v49 > 1 )
LABEL_112:
                      *(_DWORD *)(*(_QWORD *)&v63[8 * v59 + 32] + 24 * v52 + 8) = v58;
                    else
LABEL_75:
                      *(_DWORD *)&v63[8 * v59 + 8] = v58;
                  }
                  else
                  {
                    switch ( (int)v53 )
                    {
                      case 2:
                        if ( (_DWORD)v56 != 2 )
                          Log_AssertionEvent(
                            v53,
                            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
                            2356);
                        v71 = *(_WORD *)v55;
                        v72 = 5 * v46;
                        if ( v49 <= 1 )
                          goto LABEL_133;
                        *(_WORD *)(*(_QWORD *)&v63[40 * v46 + 32] + 24 * v52 + 8) = v71;
                        break;
                      case 3:
                        if ( (_DWORD)v56 != 4 )
                          Log_AssertionEvent(
                            v53,
                            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
                            2367);
                        v58 = *v55;
                        v59 = 5 * v46;
                        if ( v49 > 1 )
                          goto LABEL_112;
                        goto LABEL_75;
                      case 4:
                      case 6:
                      case 7:
                      case 8:
                      case 9:
                      case 10:
                      case 12:
                      case 13:
                      case 14:
                      case 15:
                      case 16:
                      case 17:
                      case 20:
                      case 21:
                      case 22:
                      case 23:
                      case 24:
                      case 25:
                      case 26:
                      case 27:
                      case 28:
                      case 29:
                      case 30:
                      case 32:
                      case 33:
                      case 34:
                      case 35:
                      case 36:
                      case 37:
                      case 38:
                      case 39:
                      case 40:
                      case 41:
                      case 42:
                      case 43:
                      case 44:
                      case 45:
                      case 46:
                      case 47:
                      case 48:
                      case 49:
                      case 50:
                      case 51:
                      case 52:
                      case 53:
                      case 54:
                      case 55:
                      case 56:
                      case 57:
                      case 58:
                      case 59:
                      case 60:
                      case 61:
                      case 62:
                      case 63:
                      case 66:
                      case 67:
                      case 68:
                      case 69:
                      case 70:
                      case 71:
                      case 72:
                      case 73:
                      case 74:
                      case 75:
                      case 76:
                      case 77:
                      case 78:
                      case 79:
                      case 80:
                      case 81:
                      case 82:
                      case 83:
                      case 84:
                      case 85:
                      case 86:
                      case 87:
                      case 88:
                      case 89:
                      case 90:
                      case 91:
                      case 92:
                      case 93:
                      case 94:
                      case 95:
                      case 96:
                      case 97:
                      case 98:
                      case 99:
                      case 102:
                      case 103:
                      case 104:
                        break;
                      case 5:
                        if ( (_DWORD)v56 == 8 )
                          goto LABEL_103;
                        v67 = 2401;
                        goto LABEL_102;
                      case 11:
                        if ( (_DWORD)v56 != 1 )
                          Log_AssertionEvent(
                            v53,
                            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
                            2345);
                        v70 = *(_BYTE *)v55 != 0;
                        if ( v49 > 1 )
                          *(_DWORD *)(*(_QWORD *)&v63[40 * v46 + 32] + 24 * v52 + 8) = v70;
                        else
                          *(_DWORD *)&v63[40 * v46 + 8] = v70;
                        break;
                      case 18:
                        if ( (_DWORD)v56 != 2 )
                          Log_AssertionEvent(
                            v53,
                            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
                            2378);
                        v71 = *(_WORD *)v55;
                        v72 = 5 * v46;
                        if ( v49 > 1 )
                          *(_WORD *)(*(_QWORD *)&v63[40 * v46 + 32] + 24 * v52 + 8) = v71;
                        else
LABEL_133:
                          *(_WORD *)&v63[8 * v72 + 8] = v71;
                        break;
                      case 19:
                        goto LABEL_72;
                      case 31:
                        if ( v49 > 1 )
                          *(_QWORD *)(*(_QWORD *)&v63[40 * v46 + 32] + v57 + 8) = v80;
                        else
                          *(_QWORD *)&v63[40 * v46 + 8] = v80;
                        goto LABEL_84;
                      case 64:
                        if ( (_DWORD)v56 == 8 )
                          goto LABEL_103;
                        v67 = 2412;
                        goto LABEL_102;
                      case 65:
                      case 100:
                      case 101:
                        if ( v49 <= 1 )
                        {
                          *(_DWORD *)&v63[40 * v46 + 8] = v56;
                          *(_QWORD *)&v63[40 * v46 + 16] = v80;
                        }
                        else
                        {
                          *(_DWORD *)(v57 + *(_QWORD *)&v63[40 * v46 + 32] + 8) = v56;
                          *(_QWORD *)(v57 + *(_QWORD *)&v63[40 * v46 + 32] + 16) = v80;
                        }
LABEL_84:
                        v60 = (unsigned int)v56;
                        memcpy_0(v80, v55, v56);
                        v61 = v60 + 3;
                        v24 = v81;
                        v80 += v61 & 0xFFFFFFFFFFFFFFFCuLL;
                        break;
                      case 105:
                        if ( (_DWORD)v56 == 8 )
                          goto LABEL_103;
                        v67 = 2453;
LABEL_102:
                        Log_AssertionEvent(
                          v53,
                          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
                          v67);
LABEL_103:
                        v68 = *(_QWORD *)v55;
                        if ( v49 <= 1 )
                          *(_QWORD *)&v63[40 * v46 + 8] = v68;
                        else
                          *(_QWORD *)(*(_QWORD *)&v63[40 * v46 + 32] + 24 * v52 + 8) = v68;
                        break;
                      default:
                        goto LABEL_77;
                    }
                  }
                  v53 = v77;
LABEL_77:
                  v54 = v95;
                  ++v51;
                  v50 = v90;
                  ++v52;
                  v42 = v91;
                }
                while ( v51 < v49 );
                v20 = v78;
                v23 = v83;
              }
              else
              {
                Log_AssertionEvent(
                  3LL * v20,
                  "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
                  2314);
                v42 = v91;
                v20 = v78;
                v50 = &v63[40 * v46];
                v90 = v50;
                *(_DWORD *)v50 = v24;
LABEL_65:
                v51 = 0;
                if ( v49 )
                  goto LABEL_66;
              }
              v21 = v82 + 1;
              ++v20;
              ++v82;
              v78 = v20;
LABEL_80:
              v22 = v86;
              ++v23;
              v8 = a5;
              v7 = v88;
              v9 = a4;
              continue;
            }
            if ( v8[v20].cEnumColumnValue )
            {
LABEL_56:
              v45 = v44 < 0;
              goto LABEL_59;
            }
          }
        }
        v78 = ++v20;
        if ( v92 )
        {
          v65 = 5LL * v23;
          *(_DWORD *)&v63[8 * v65] = v92[v23];
          *(_WORD *)&v63[8 * v65 + 6] = 256;
        }
        else
        {
          v79 = 1;
        }
        goto LABEL_80;
      }
      v69 = 5LL * v23;
      *(_DWORD *)&v63[8 * v69] = v43;
      *(_WORD *)&v63[8 * v69 + 6] = 256;
      goto LABEL_80;
    }
    break;
  }
  v41 = v93;
  if ( !v92 )
    *v93 = v21;
  if ( v79 )
  {
    HresultFromJetError = USCopyPropValsEx(*v41, (_DWORD)v63, v42, (_DWORD)v94, (__int64)a7);
    if ( (HresultFromJetError & 0x80000000) == 0 )
    {
      LocalFree(v63);
      return 0;
    }
    v35 = 2476;
LABEL_32:
    v36 = 1;
    v37 = HresultFromJetError;
LABEL_33:
    Log_UnistoreHREvent_0(
      v37,
      v36,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
      v35);
    LocalFree(v63);
    return HresultFromJetError;
  }
  if ( (unsigned __int64)v89 > 0xFFFFFFFF )
  {
    *a7 = -1;
    Log_UnistoreHREvent_0(
      2147942934LL,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
      2480);
    LocalFree(v63);
    return 2147942934LL;
  }
  else
  {
    *a7 = v89;
    *v94 = (unsigned __int8 *)v63;
    return 0;
  }
}

```

## disassembly

```asm
0x18000b9d0  mov     r11, rsp
0x18000b9d3  push    rbp
0x18000b9d4  push    rsi
0x18000b9d5  push    r12
0x18000b9d7  push    r13
0x18000b9d9  push    r15
0x18000b9db  sub     rsp, 0E0h
0x18000b9e2  mov     rax, [rsp+108h+arg_30]
0x18000b9ea  mov     r15d, r9d
0x18000b9ed  mov     rbp, [rsp+108h+arg_20]
0x18000b9f5  mov     r12d, r9d
0x18000b9f8  mov     [rsp+108h+var_98], rax
0x18000b9fd  mov     [rsp+108h+var_A8], ecx
0x18000ba01  mov     rcx, [rsp+108h+arg_28]
0x18000ba09  mov     [rsp+108h+var_70], r8
0x18000ba11  xor     r8d, r8d
0x18000ba14  mov     [rsp+108h+var_60], rcx
0x18000ba1c  mov     [rsp+108h+var_68], rdx
0x18000ba24  mov     [rcx], r8
0x18000ba27  mov     ecx, 28h ; '('
0x18000ba2c  mov     [rax], r8d
0x18000ba2f  mov     eax, [rdx]
0x18000ba31  test    eax, eax
0x18000ba33  mov     [rsp+108h+var_B4], r9d
0x18000ba38  cmovnz  r15d, eax
0x18000ba3c  mov     [rsp+108h+var_A0], rbp
0x18000ba41  mov     eax, r15d
0x18000ba44  mul     rcx
0x18000ba47  mov     [rsp+108h+var_A4], r15d
0x18000ba4c  mov     qword ptr [rsp+108h+var_90], r8
0x18000ba51  mov     r13, rax
0x18000ba54  test    rdx, rdx
0x18000ba57  jnz     loc_18000C54C
0x18000ba5d  mov     [r11+8], rbx
0x18000ba61  lea     rsi, ?g_columnIdMapping@@3VColumnIdMappings@@A; ColumnIdMappings g_columnIdMapping
0x18000ba68  mov     [r11-30h], rdi
0x18000ba6c  mov     ebx, r8d
0x18000ba6f  mov     [r11-38h], r14
0x18000ba73  mov     r14d, r8d
0x18000ba76  mov     [rsp+108h+var_B0], rbx
0x18000ba7b  cmp     r14d, r12d
0x18000ba7e  jnb     loc_18000BD4E
0x18000ba84  mov     eax, r14d
0x18000ba87  lea     r12, [rax+rax*2]
0x18000ba8b  mov     eax, [rbp+r12*8+4]
0x18000ba90  test    eax, eax
0x18000ba92  jz      loc_18000C4AA
0x18000ba98  cmp     eax, 5FEh
0x18000ba9d  jz      loc_18000C4AA
0x18000baa3  mov     edi, [rbp+r12*8+0]
0x18000baa8  mov     rcx, rsi; SRWLock
0x18000baab  mov     [rsp+108h+var_D0], edi
0x18000baaf  call    cs:__imp_AcquireSRWLockShared
0x18000bab5  cmp     cs:dword_18010D248, 0
0x18000babc  jz      loc_18000C1CB
0x18000bac2  mov     eax, [rsp+108h+var_A8]
0x18000bac6  xorps   xmm0, xmm0
0x18000bac9  movups  [rsp+108h+var_90], xmm0
0x18000bace  mov     dword ptr [rsp+108h+var_90+4], edi
0x18000bad2  lea     r15, [rax+rax*2]
0x18000bad6  mov     rbx, [rsi+r15*8+878h]
0x18000bade  mov     rsi, [rsi+r15*8+880h]
0x18000bae6  sub     rsi, rbx
0x18000bae9  sar     rsi, 4
0x18000baed  test    rsi, rsi
0x18000baf0  jle     short loc_18000BB24
0x18000baf2  mov     rdi, rsi
0x18000baf5  lea     rdx, [rsp+108h+var_90]; struct PropIdAndColumnDetails *
0x18000bafa  shr     rdi, 1
0x18000bafd  mov     rbp, rdi
0x18000bb00  shl     rbp, 4
0x18000bb04  add     rbp, rbx
0x18000bb07  mov     rcx, rbp; struct PropIdAndColumnDetails *
0x18000bb0a  call    ?CompareColumns@@YA_NAEBUPropIdAndColumnDetails@@0@Z; CompareColumns(PropIdAndColumnDetails const &,PropIdAndColumnDetails const &)
0x18000bb0f  test    al, al
0x18000bb11  jnz     short loc_18000BB8D
0x18000bb13  mov     rsi, rdi
0x18000bb16  test    rsi, rsi
0x18000bb19  jg      short loc_18000BAF2
0x18000bb1b  mov     edi, [rsp+108h+var_D0]
0x18000bb1f  mov     rbp, [rsp+108h+var_A0]
0x18000bb24  lea     rsi, ?g_columnIdMapping@@3VColumnIdMappings@@A; ColumnIdMappings g_columnIdMapping
0x18000bb2b  cmp     rbx, [rsi+r15*8+880h]
0x18000bb33  jnz     loc_18000C080
0x18000bb39  mov     r8d, 10Eh
0x18000bb3f  lea     rdx, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000bb46  call    Log_AssertionEvent
0x18000bb4b  mov     r9d, 10Fh
0x18000bb51  mov     ebx, 8000FFFFh
0x18000bb56  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000bb5d  mov     ecx, ebx
0x18000bb5f  xor     edx, edx
0x18000bb61  call    Log_UnistoreHREvent_0
0x18000bb66  mov     rcx, rsi; SRWLock
0x18000bb69  call    cs:__imp_ReleaseSRWLockShared
0x18000bb6f  mov     r9d, 8AAh
0x18000bb75  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000bb7c  mov     edx, 1
0x18000bb81  mov     ecx, ebx
0x18000bb83  call    Log_UnistoreHREvent_0
0x18000bb88  jmp     loc_18000BD12
0x18000bb8d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000bb94  lea     rbx, [rbp+10h]
0x18000bb98  sub     rax, rdi
0x18000bb9b  add     rsi, rax
0x18000bb9e  jmp     loc_18000BB16
0x18000bba3  mov     r15d, [rsp+108h+var_A4]
0x18000bba8  xor     r10d, r10d
0x18000bbab  xor     r9d, r9d
0x18000bbae  mov     [rsp+108h+var_D4], r10d
0x18000bbb3  mov     [rsp+108h+var_BC], r9d
0x18000bbb8  lea     rax, [r15+r15*4]
0x18000bbbc  lea     r11, [rdi+rax*8]
0x18000bbc0  lea     rax, [rbx+rbx*2]
0x18000bbc4  mov     [rsp+108h+var_B0], r11
0x18000bbc9  lea     rax, [r11+rax*8]
0x18000bbcd  mov     [rsp+108h+var_C8], rax
0x18000bbd2  xor     eax, eax
0x18000bbd4  mov     [rsp+108h+var_D0], eax
0x18000bbd8  xor     r14d, r14d
0x18000bbdb  mov     [rsp+108h+var_B8], r14d
0x18000bbe0  mov     r13d, 100h
0x18000bbe6  cmp     r14d, r15d
0x18000bbe9  jnb     loc_18000BDA3
0x18000bbef  xor     ebx, ebx
0x18000bbf1  mov     r15d, r10d
0x18000bbf4  mov     [rsp+108h+var_C0], ebx
0x18000bbf8  cmp     r10d, r12d
0x18000bbfb  jnb     loc_18000BE29
0x18000bc01  lea     rax, [r15+r15*2]
0x18000bc05  mov     r13d, [rbp+rax*8+0]
0x18000bc0a  lea     rsi, ?g_columnIdMapping@@3VColumnIdMappings@@A; ColumnIdMappings g_columnIdMapping
0x18000bc11  mov     rcx, rsi; SRWLock
0x18000bc14  call    cs:__imp_AcquireSRWLockShared
0x18000bc1a  cmp     cs:dword_18010D248, ebx
0x18000bc20  jz      loc_18000C1C0
0x18000bc26  mov     eax, [rsp+108h+var_A8]
0x18000bc2a  xorps   xmm0, xmm0
0x18000bc2d  movups  [rsp+108h+var_50], xmm0
0x18000bc35  mov     dword ptr [rsp+108h+var_50+4], r13d
0x18000bc3d  lea     r12, [rax+rax*2]
0x18000bc41  mov     rbx, [rsi+r12*8+878h]
0x18000bc49  mov     rbp, [rsi+r12*8+880h]
0x18000bc51  sub     rbp, rbx
0x18000bc54  sar     rbp, 4
0x18000bc58  test    rbp, rbp
0x18000bc5b  jle     short loc_18000BCAC
0x18000bc5d  nop     dword ptr [rax]
0x18000bc60  mov     rsi, rbp
0x18000bc63  lea     rdx, [rsp+108h+var_50]; struct PropIdAndColumnDetails *
0x18000bc6b  shr     rsi, 1
0x18000bc6e  mov     r14, rsi
0x18000bc71  shl     r14, 4
0x18000bc75  add     r14, rbx
0x18000bc78  mov     rcx, r14; struct PropIdAndColumnDetails *
0x18000bc7b  call    ?CompareColumns@@YA_NAEBUPropIdAndColumnDetails@@0@Z; CompareColumns(PropIdAndColumnDetails const &,PropIdAndColumnDetails const &)
0x18000bc80  movzx   edx, al
0x18000bc83  test    al, al
0x18000bc85  jnz     loc_18000BD3C
0x18000bc8b  mov     rbp, rsi
0x18000bc8e  test    dl, dl
0x18000bc90  lea     rax, [r14+10h]
0x18000bc94  cmovz   rax, rbx
0x18000bc98  mov     rbx, rax
0x18000bc9b  test    rbp, rbp
0x18000bc9e  jg      short loc_18000BC60
0x18000bca0  mov     r14d, [rsp+108h+var_B8]
0x18000bca5  lea     rsi, ?g_columnIdMapping@@3VColumnIdMappings@@A; ColumnIdMappings g_columnIdMapping
0x18000bcac  cmp     rbx, [rsi+r12*8+880h]
0x18000bcb4  jnz     loc_18000BDF1
0x18000bcba  mov     r8d, 10Eh
0x18000bcc0  lea     rdx, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000bcc7  call    Log_AssertionEvent
0x18000bccc  mov     r9d, 10Fh
0x18000bcd2  mov     ebx, 8000FFFFh
0x18000bcd7  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000bcde  mov     ecx, ebx
0x18000bce0  xor     edx, edx
0x18000bce2  call    Log_UnistoreHREvent_0
0x18000bce7  mov     rcx, rsi; SRWLock
0x18000bcea  call    cs:__imp_ReleaseSRWLockShared
0x18000bcf0  mov     r9d, 8DCh
0x18000bcf6  mov     edx, 1
0x18000bcfb  mov     ecx, ebx
0x18000bcfd  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000bd04  call    Log_UnistoreHREvent_0
0x18000bd09  mov     rcx, rdi; hMem
0x18000bd0c  call    cs:__imp_LocalFree
0x18000bd12  mov     eax, ebx
0x18000bd14  mov     rdi, [rsp+108h+var_30]
0x18000bd1c  mov     rbx, [rsp+108h+arg_0]
0x18000bd24  mov     r14, [rsp+108h+var_38]
0x18000bd2c  add     rsp, 0E0h
0x18000bd33  pop     r15
0x18000bd35  pop     r13
0x18000bd37  pop     r12
0x18000bd39  pop     rsi
0x18000bd3a  pop     rbp
0x18000bd3b  retn
0x18000bd3c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000bd43  sub     rcx, rsi
0x18000bd46  add     rbp, rcx
0x18000bd49  jmp     loc_18000BC8E
0x18000bd4e  mov     ecx, 18h
0x18000bd53  mov     qword ptr [rsp+108h+var_90], 0
0x18000bd5c  mov     rax, rbx
0x18000bd5f  mul     rcx
0x18000bd62  test    rdx, rdx
0x18000bd65  jnz     loc_18000C541
0x18000bd6b  lea     rsi, [rax+r13]
0x18000bd6f  mov     qword ptr [rsp+108h+var_90], rsi
0x18000bd74  cmp     rsi, r13
0x18000bd77  jnb     loc_18000C043
0x18000bd7d  mov     r9d, 8C7h
0x18000bd83  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000bd8a  mov     edx, 1
0x18000bd8f  mov     ecx, 80070216h
0x18000bd94  call    Log_UnistoreHREvent_0
0x18000bd99  mov     eax, 80070216h
0x18000bd9e  jmp     loc_18000BD14
0x18000bda3  cmp     [rsp+108h+var_70], 0
0x18000bdac  mov     rcx, [rsp+108h+var_68]
0x18000bdb4  jz      loc_18000C52E
0x18000bdba  cmp     [rsp+108h+var_D0], 0
0x18000bdbf  mov     rax, [rsp+108h+var_98]
0x18000bdc4  jnz     loc_18000C431
0x18000bdca  mov     rsi, qword ptr [rsp+108h+var_90]
0x18000bdcf  mov     ecx, 0FFFFFFFFh
0x18000bdd4  cmp     rsi, rcx
0x18000bdd7  ja      loc_18000C10D
0x18000bddd  mov     [rax], esi
0x18000bddf  mov     rax, [rsp+108h+var_60]
0x18000bde7  mov     [rax], rdi
0x18000bdea  xor     eax, eax
0x18000bdec  jmp     loc_18000BD14
0x18000bdf1  cmp     [rbx+4], r13d
0x18000bdf5  jnz     loc_18000BCBA
0x18000bdfb  mov     ebx, [rbx]
0x18000bdfd  mov     rcx, rsi; SRWLock
0x18000be00  mov     [rsp+108h+var_C0], ebx
0x18000be04  call    cs:__imp_ReleaseSRWLockShared
0x18000be0a  mov     r10d, [rsp+108h+var_D4]
0x18000be0f  mov     r13d, 100h
0x18000be15  mov     r9d, [rsp+108h+var_BC]
0x18000be1a  mov     r11, [rsp+108h+var_B0]
0x18000be1f  mov     rbp, [rsp+108h+var_A0]
0x18000be24  mov     r12d, [rsp+108h+var_B4]
0x18000be29  mov     rsi, [rsp+108h+var_70]
0x18000be31  test    rsi, rsi
0x18000be34  jz      short loc_18000BE44
0x18000be36  mov     eax, r14d
0x18000be39  mov     ecx, [rsi+rax*4]
0x18000be3c  cmp     ecx, ebx
0x18000be3e  jnz     loc_18000C1D6
0x18000be44  cmp     r10d, r12d
0x18000be47  jnb     loc_18000C502
0x18000be4d  lea     r8, [r15+r15*2]
0x18000be51  mov     edx, [rbp+r8*8+4]
0x18000be56  mov     [rsp+108h+var_78], r8
0x18000be5e  cmp     edx, 0FFFFFA1Dh
0x18000be64  jz      loc_18000C0E4
0x18000be6a  cmp     edx, 0FFFFFA13h
0x18000be70  jz      loc_18000C0E4
0x18000be76  cmp     edx, 5FBh
0x18000be7c  jz      loc_18000C0E4
0x18000be82  cmp     edx, 3ECh
0x18000be88  jz      loc_18000C0E4
0x18000be8e  cmp     edx, 600h
0x18000be94  jnz     short loc_18000BEAE
0x18000be96  cmp     dword ptr [rbp+r8*8+8], 0
0x18000be9c  jz      short loc_18000BEA2
0x18000be9e  test    edx, edx
0x18000bea0  jmp     short loc_18000BEB6
0x18000bea2  cmp     qword ptr [rbp+r8*8+10h], 0
0x18000bea8  jz      loc_18000C0E4
0x18000beae  test    edx, edx
0x18000beb0  jz      loc_18000C33E
0x18000beb6  js      loc_18000C4EA
0x18000bebc  mov     eax, r10d
0x18000bebf  test    rsi, rsi
0x18000bec2  mov     r12d, r9d
0x18000bec5  cmovnz  r12d, r14d
0x18000bec9  lea     rcx, [rax+rax*2]
0x18000becd  mov     eax, [rbp+rcx*8+4]
0x18000bed1  test    eax, eax
0x18000bed3  jz      loc_18000C2EE
0x18000bed9  xor     r13d, r13d
0x18000bedc  mov     esi, 1
0x18000bee1  cmp     eax, 5FEh
0x18000bee6  jz      loc_18000C2EE
0x18000beec  lea     rcx, [r12+r12*4]
0x18000bef0  mov     [rdi+rcx*8], ebx
0x18000bef3  lea     r9, [rdi+rcx*8]
0x18000bef7  mov     [rsp+108h+var_80], r9
0x18000beff  cmp     esi, 1
0x18000bf02  ja      loc_18000C1E8
0x18000bf08  xor     ebp, ebp
0x18000bf0a  test    esi, esi
0x18000bf0c  jz      loc_18000BFAA
0x18000bf12  mov     eax, r10d
  ... truncated ...
```
