# CIStreamMultipleResults::Read(void *,ulong,ulong *)

- ea: `0x383a8eaa0`
- end: `0x383a8ed5e`
- name: `?Read@CIStreamMultipleResults@@UEAAJPEAXKPEAK@Z`
- size: `702`
- prototype: `__int64 __fastcall(CIStreamMultipleResults *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3838427d0`
- `0x3838434c0`
- `0x383884bb0`
- `0x383893160`
- `0x38391aed0`
- `0x38391afe0`
- `0x383a8e110`
- `0x383a8e9a0`
- `0x383a8ea10`
- `0x383a8eaa0`
- `0x383a8f7d0`
- `0x383a8fd30`
- `0x383a909b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x383a8f374`
- `KERNEL32!GetLastError` at `0x383a8f374`
- `KERNEL32!MultiByteToWideChar` at `0x383a8f312`
- `KERNEL32!MultiByteToWideChar` at `0x383a8f36a`
- `KERNEL32!MultiByteToWideChar` at `0x383a8f312`
- `KERNEL32!MultiByteToWideChar` at `0x383a8f36a`
- `OLEAUT32!__imp_GetErrorInfo` at `0x383a8f40d`
- `OLEAUT32!__imp_GetErrorInfo` at `0x383a8f40d`
- `OLEAUT32!__imp_SetErrorInfo` at `0x383a8eaf2`
- `OLEAUT32!__imp_SetErrorInfo` at `0x383a8f437`
- `OLEAUT32!__imp_SetErrorInfo` at `0x383a8eaf2`
- `OLEAUT32!__imp_SetErrorInfo` at `0x383a8f437`

## string_xrefs

- `0x383a8ef4a`: `<?xml version="1.0" encoding="%s" ?>`
- `0x383a8ef0c`: `<?xml version="1.0" encoding="%S" ?>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CIStreamMultipleResults::Read(
        CIStreamMultipleResults *this,
        char *a2,
        unsigned int a3,
        unsigned int *a4)
{
  unsigned int StreamOverRowset; // edi
  unsigned int v9; // r15d
  _WORD *v10; // rax
  _WORD *v11; // r9
  _WORD *v12; // r8
  unsigned __int16 v13; // dx
  __int64 v14; // rdx
  _WORD *v15; // rcx
  __int16 v16; // ax
  int v17; // eax
  _WORD *v18; // rcx
  __int64 v19; // rax
  int v20; // eax
  int v21; // eax
  unsigned int v22; // eax
  int v23; // eax
  __int64 v24; // rcx
  int v25; // eax
  int v26; // eax
  char *v27; // rbx
  __int64 v28; // rax
  __int64 v29; // rax
  int v30; // eax
  unsigned __int64 v31; // rcx
  __int64 v32; // rdx
  _WORD *v33; // rbx
  __int64 v34; // r11
  _DWORD *v35; // rbx
  __int64 (__fastcall *v36)(char *, __int64, _QWORD, _QWORD *, char *, __int64 *); // r10
  __int64 v37; // rdx
  int v38; // eax
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // rbx
  unsigned int v42; // eax
  int v43; // eax
  __int64 *v44; // rcx
  bool v45; // zf
  __int64 v46; // rax
  signed int LastError; // eax
  unsigned int v48; // ecx
  IErrorInfo *v49; // rdx
  __int64 v50; // rcx
  CBinXMLConvert *v51; // rcx
  int v52; // eax
  CIStreamError *v53; // rax
  struct ISQLXMLHelper *v54; // r9
  CIStreamError *v55; // rax
  LPWSTR lpWideCharStr; // [rsp+20h] [rbp-E0h]
  int cbMultiByte; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD Size[3]; // [rsp+34h] [rbp-CCh] BYREF
  struct IRowset *v60; // [rsp+40h] [rbp-C0h] BYREF
  int v61; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v62; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v63[3]; // [rsp+58h] [rbp-A8h] BYREF
  CHAR MultiByteStr[1040]; // [rsp+70h] [rbp-90h] BYREF

  v63[1] = -2;
  StreamOverRowset = 0;
  v60 = 0;
  v9 = 0;
  SetErrorInfo(0, 0);
  if ( !a2 )
  {
    StreamOverRowset = -2147287031;
    if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
      bidTraceW(off_383B43498[0], 942121, off_383B49128[0], 2147680265LL);
    goto LABEL_191;
  }
  if ( !a3 )
    goto LABEL_191;
  while ( 2 )
  {
    if ( StreamOverRowset == 1 )
      goto LABEL_191;
    Size[0] = 0;
    switch ( *((_DWORD *)this + 16) )
    {
      case 0:
        v10 = (_WORD *)(*(__int64 (__fastcall **)(_QWORD, unsigned __int64, __int64, __int64))(**((_QWORD **)this + 5)
                                                                                             + 96LL))(
                         *((_QWORD *)this + 5),
                         0x383800000uLL,
                         12,
                         9);
        *((_QWORD *)this + 972) = v10;
        if ( !v10 )
          goto LABEL_23;
        v12 = v10;
        v13 = *v10;
        if ( !*v10 )
          goto LABEL_21;
        if ( (*((_BYTE *)(&g_apCharTables)[(unsigned __int64)v13 >> 8] + (unsigned __int8)v13) & 4) == 0 )
          goto LABEL_21;
        v11 = 0;
        if ( v13 == 58 || !v13 )
          goto LABEL_21;
        do
        {
          if ( (*((_BYTE *)(&g_apCharTables)[(unsigned __int64)v13 >> 8] + (unsigned __int8)v13) & 8) == 0 )
            break;
          if ( v13 == 58 )
          {
            if ( v11 )
              goto LABEL_19;
            v11 = v12;
          }
          v13 = *++v12;
        }
        while ( *v12 );
        if ( !v11 )
          goto LABEL_21;
LABEL_19:
        if ( (((char *)v12 - (char *)v11) & 0xFFFFFFFFFFFFFFFEuLL) == 2 )
          v12 = v11;
LABEL_21:
        if ( *v12 || v12 == v10 )
        {
          if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
          {
            LODWORD(lpWideCharStr) = 940;
            bidTraceW(off_383B43498[0], 962601, off_383B49128[0], 2147500037LL);
          }
          StreamOverRowset = -2147467259;
          InternalPostSQLXMLError(-2147467259, &IID_ICommand, 0x234u, v11, lpWideCharStr);
        }
        else
        {
LABEL_23:
          if ( (*(unsigned int (__fastcall **)(CIStreamMultipleResults *, __int64))(*(_QWORD *)this + 56LL))(this, 16) )
          {
            v14 = 255;
            v15 = (_WORD *)((char *)this + 96);
            while ( v14 != -2147483391 )
            {
              v16 = *(_WORD *)((char *)v15 + (char *)L"UCS-2" - ((char *)this + 96));
              if ( !v16 )
                break;
              *v15++ = v16;
              if ( !--v14 )
              {
                --v15;
                break;
              }
            }
            *v15 = 0;
          }
          v17 = CIStreamMultipleResults::SetEncoding(this, (const unsigned __int16 *)this + 48);
          StreamOverRowset = v17;
          if ( v17 >= 0 )
          {
            if ( (*(unsigned int (__fastcall **)(CIStreamMultipleResults *, __int64))(*(_QWORD *)this + 56LL))(this, 1)
              && (v18 = (_WORD *)*((_QWORD *)this + 972)) != 0
              && *v18 )
            {
              v19 = -1;
              do
                ++v19;
              while ( v18[v19] );
              *((_QWORD *)this + 974) = v19;
              v20 = *((_DWORD *)this + 1951);
              if ( v20 == 1200 || v20 == 12000 )
                *((_DWORD *)this + 16) = 2;
              else
                *((_DWORD *)this + 16) = 3;
            }
            else
            {
              *((_DWORD *)this + 16) = 6;
            }
            goto LABEL_41;
          }
          if ( (bidGblFlags & 2) != 0 )
            bidTraceHR(off_383B43498[0], 983049, (unsigned int)v17);
        }
        goto LABEL_191;
      case 2:
        if ( *((_QWORD *)this + 974) )
        {
          *((_DWORD *)this + 17) = 3;
        }
        else
        {
          if ( StreamOverRowset )
          {
            v23 = 10;
            if ( StreamOverRowset == 265929 )
              v23 = 12;
          }
          else
          {
            v23 = 6;
            if ( *((_QWORD *)this + 7) )
              v23 = 9;
          }
          *((_DWORD *)this + 17) = v23;
        }
        v24 = *((_QWORD *)this + 7);
        if ( v24
          && (*(unsigned int (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v24 + 56LL))(v24, 2, 12, 9)
          && !(*(unsigned int (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 7) + 56LL))(
                *((_QWORD *)this + 7),
                32) )
        {
          v25 = *((_DWORD *)this + 17);
          goto LABEL_119;
        }
        *((_DWORD *)this + 16) = 8;
        if ( *((_DWORD *)this + 1951) == 12000 )
        {
          *((_QWORD *)this + 11) = byte_383A8F740;
          *((_QWORD *)this + 10) = 4;
        }
        else
        {
          *((_QWORD *)this + 11) = &dword_383A8F744;
          *((_QWORD *)this + 10) = 2;
        }
        goto LABEL_167;
      case 3:
        *((_DWORD *)this + 16) = 8;
        *((_DWORD *)this + 17) = 4;
        v26 = *((_DWORD *)this + 1951);
        if ( v26 == 1200 || v26 == 12000 )
        {
          v27 = (char *)this + 606;
          if ( (int)StringCchPrintfW(
                      (unsigned __int16 *)this + 303,
                      0x401u,
                      L"<?xml version=\"1.0\" encoding=\"%s\" ?>",
                      (char *)this + 96) < 0 )
          {
            StreamOverRowset = -2147418113;
            if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
              bidTraceW(off_383B43498[0], 1140777, off_383B49128[0], 2147549183LL);
            goto LABEL_191;
          }
          v29 = -1;
          do
            ++v29;
          while ( *(_WORD *)&v27[2 * v29] );
          *((_QWORD *)this + 10) = 2 * v29;
          if ( *((_DWORD *)this + 1951) == 12000 )
            *((_DWORD *)this + 16) = 7;
        }
        else
        {
          v27 = (char *)this + 606;
          if ( (int)StringCchPrintfA(
                      (char *)this + 606,
                      0x401u,
                      "<?xml version=\"1.0\" encoding=\"%S\" ?>",
                      (const wchar_t *)this + 48) < 0 )
          {
            StreamOverRowset = -2147418113;
            if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
              bidTraceW(off_383B43498[0], 1156137, off_383B49128[0], 2147549183LL);
            goto LABEL_191;
          }
          v28 = -1;
          do
            ++v28;
          while ( v27[v28] );
          *((_QWORD *)this + 10) = v28;
        }
        *((_QWORD *)this + 11) = v27;
        goto LABEL_167;
      case 4:
        *((_DWORD *)this + 16) = 7;
        if ( StreamOverRowset )
        {
          v30 = 10;
          if ( StreamOverRowset == 265929 )
            v30 = 5;
        }
        else if ( *((_QWORD *)this + 7) )
        {
          v30 = 9;
        }
        else
        {
          v30 = (*((_QWORD *)this + 6) != 0) + 5;
        }
        *((_DWORD *)this + 17) = v30;
        v31 = *((_QWORD *)this + 974) + 3LL;
        if ( v31 <= 0x400 )
        {
          v33 = (_WORD *)((char *)this + 606);
        }
        else
        {
          v32 = 2 * v31;
          if ( !is_mul_ok(v31, 2u) )
            v32 = -1;
          v33 = (_WORD *)((__int64 (__fastcall *)(struct IMalloc *, __int64, __int64, __int64))g_pMO->lpVtbl[1].Free)(
                           g_pMO,
                           v32,
                           12,
                           9);
          *((_QWORD *)this + 973) = v33;
          if ( !v33 )
          {
            StreamOverRowset = -2147024882;
            if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
              bidTraceW(off_383B43498[0], 1186857, off_383B49128[0], 2147942414LL);
            goto LABEL_191;
          }
        }
        *((_QWORD *)this + 11) = v33;
        *v33 = 60;
        memcpy(v33 + 1, *((const void **)this + 972), 2LL * *((_QWORD *)this + 974));
        v34 = *((_QWORD *)this + 974);
        *((_QWORD *)this + 10) = 2 * v34 + 4;
        v33[v34 + 1] = 62;
        goto LABEL_167;
      case 5:
        *((_DWORD *)this + 16) = 7;
        *((_DWORD *)this + 17) = 12;
        if ( (unsigned __int64)(*((_QWORD *)this + 974) + 3LL) <= 0x400 )
          v35 = (_DWORD *)((char *)this + 606);
        else
          v35 = (_DWORD *)*((_QWORD *)this + 973);
        *((_QWORD *)this + 11) = v35;
        *v35 = 3080252;
        memcpy(v35 + 1, *((const void **)this + 972), 2LL * *((_QWORD *)this + 974));
        *((_WORD *)v35 + *((_QWORD *)this + 974) + 2) = 62;
        *((_QWORD *)this + 10) = 2LL * *((_QWORD *)this + 974) + 6;
        goto LABEL_167;
      case 6:
LABEL_41:
        if ( !*((_QWORD *)this + 6) )
        {
          v21 = 12;
          if ( *((_QWORD *)this + 974) )
            v21 = 4;
          *((_DWORD *)this + 16) = v21;
          goto LABEL_167;
        }
        while ( 1 )
        {
          v22 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, GUID *, _QWORD, struct IRowset **))(**((_QWORD **)this + 6) + 24LL))(
                  *((_QWORD *)this + 6),
                  0,
                  0,
                  &IID_IRowset,
                  0,
                  &v60);
          StreamOverRowset = v22;
          if ( v22 )
            break;
          if ( v60 )
          {
            StreamOverRowset = CreateStreamOverRowset(v60, (struct ISequentialStream **)this + 7);
            if ( v60 )
            {
              ((void (__fastcall *)(struct IRowset *))v60->lpVtbl->Release)(v60);
              v60 = 0;
            }
LABEL_54:
            if ( *((_DWORD *)this + 16) == 6 )
              *((_DWORD *)this + 16) = (StreamOverRowset != 0) + 9;
            goto LABEL_167;
          }
        }
        if ( v22 != 265929 )
        {
          if ( v22 == -2147217915 )
            *((_BYTE *)this + 7801) = 1;
          goto LABEL_54;
        }
        if ( *((_DWORD *)this + 16) == 6 )
        {
          StreamOverRowset = 0;
LABEL_117:
          v25 = 12;
          if ( *((_QWORD *)this + 974) )
            v25 = 5;
LABEL_119:
          *((_DWORD *)this + 16) = v25;
        }
        goto LABEL_167;
      case 7:
        v36 = (__int64 (__fastcall *)(char *, __int64, _QWORD, _QWORD *, char *, __int64 *))*((_QWORD *)this + 977);
        if ( !v36 )
          goto LABEL_110;
        v37 = *((unsigned int *)this + 1951);
        if ( (_DWORD)v37 == 1200 )
          goto LABEL_110;
        v63[0] = *((_QWORD *)this + 10) >> 1;
        v62 = 5120;
        v38 = v36((char *)this + 7808, v37, *((_QWORD *)this + 11), v63, (char *)this + 2656, &v62);
        if ( v38 < 0 )
        {
          StreamOverRowset = v38;
          goto LABEL_191;
        }
        *((_QWORD *)this + 10) = v62;
        *((_QWORD *)this + 11) = (char *)this + 2656;
LABEL_110:
        *((_DWORD *)this + 16) = 8;
LABEL_111:
        v39 = *((_QWORD *)this + 10);
        v40 = *((_QWORD *)this + 9);
        if ( a3 >= (unsigned __int64)(v39 - v40) )
          Size[0] = v39 - v40;
        else
          Size[0] = a3;
        v41 = Size[0];
        memcpy(&a2[v9], (const void *)(*((_QWORD *)this + 9) + *((_QWORD *)this + 11)), Size[0]);
        *((_QWORD *)this + 9) += v41;
        if ( *((_QWORD *)this + 9) == *((_QWORD *)this + 10) )
        {
          *((_DWORD *)this + 16) = *((_DWORD *)this + 17);
          *((_QWORD *)this + 10) = 0;
          *((_QWORD *)this + 9) = 0;
        }
LABEL_166:
        v9 += Size[0];
        a3 -= Size[0];
        goto LABEL_167;
      case 8:
        goto LABEL_111;
      case 9:
        if ( !*((_QWORD *)this + 6) )
          goto LABEL_117;
        if ( (*(unsigned int (__fastcall **)(_QWORD, __int64, __int64, __int64))(**((_QWORD **)this + 7) + 56LL))(
               *((_QWORD *)this + 7),
               4,
               12,
               9)
          && *((_DWORD *)this + 1951) == 1200
          || (*(unsigned int (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 7) + 56LL))(
               *((_QWORD *)this + 7),
               2)
          && !(*(unsigned int (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 7) + 56LL))(
                *((_QWORD *)this + 7),
                32) )
        {
          StreamOverRowset = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, _DWORD *))(**((_QWORD **)this + 7) + 24LL))(
                               *((_QWORD *)this + 7),
                               &a2[v9],
                               a3,
                               Size);
          goto LABEL_142;
        }
        cbMultiByte = 0;
        if ( (*(unsigned int (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 7) + 56LL))(
               *((_QWORD *)this + 7),
               2) )
        {
          v42 = CIStreamMultipleResults::ConvertBinaryXML(this, (unsigned int *)&cbMultiByte);
LABEL_138:
          v48 = cbMultiByte;
          StreamOverRowset = v42;
          goto LABEL_139;
        }
        v43 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 7) + 56LL))(*((_QWORD *)this + 7), 8);
        v44 = (__int64 *)*((_QWORD *)this + 7);
        v45 = v43 == 0;
        v46 = *v44;
        if ( v45 )
        {
          v42 = (*(__int64 (__fastcall **)(__int64 *, char *, __int64, int *))(v46 + 24))(
                  v44,
                  (char *)this + 606,
                  2050,
                  &cbMultiByte);
          goto LABEL_138;
        }
        StreamOverRowset = (*(__int64 (__fastcall **)(__int64 *, CHAR *, __int64, int *))(v46 + 24))(
                             v44,
                             MultiByteStr,
                             1024,
                             &cbMultiByte);
        if ( !StreamOverRowset )
        {
          if ( cbMultiByte )
          {
            if ( !MultiByteToWideChar(0, 0, MultiByteStr, cbMultiByte, (LPWSTR)this + 303, 1025) )
            {
              StreamOverRowset = (*(__int64 (__fastcall **)(_QWORD, CHAR *, _QWORD, int *))(**((_QWORD **)this + 7)
                                                                                          + 24LL))(
                                   *((_QWORD *)this + 7),
                                   &MultiByteStr[cbMultiByte - 1],
                                   StreamOverRowset + 1,
                                   &v61);
              if ( !StreamOverRowset
                && (!v61 || !MultiByteToWideChar(0, 0, MultiByteStr, v61 + cbMultiByte, (LPWSTR)this + 303, 1025)) )
              {
                LastError = GetLastError();
                StreamOverRowset = LastError;
                if ( LastError > 0 )
                  StreamOverRowset = (unsigned __int16)LastError | 0x80070000;
              }
            }
          }
        }
        v48 = 2 * cbMultiByte;
LABEL_139:
        if ( !StreamOverRowset )
        {
          if ( v48 )
          {
            *((_DWORD *)this + 16) = 7;
            *((_QWORD *)this + 11) = (char *)this + 606;
            *((_QWORD *)this + 10) = v48;
            *((_DWORD *)this + 17) = 9;
            goto LABEL_167;
          }
LABEL_160:
          StreamOverRowset = 0;
          goto LABEL_166;
        }
LABEL_142:
        if ( StreamOverRowset == -2147483638 || !StreamOverRowset )
          goto LABEL_160;
        v49 = 0;
        *(_QWORD *)&Size[1] = 0;
        if ( StreamOverRowset != 1 )
        {
          GetErrorInfo(0, (IErrorInfo **)&Size[1]);
          v49 = *(IErrorInfo **)&Size[1];
        }
        v50 = *((_QWORD *)this + 7);
        if ( v50 )
        {
          (*(void (__fastcall **)(__int64, IErrorInfo *))(*(_QWORD *)v50 + 16LL))(v50, v49);
          *((_QWORD *)this + 7) = 0;
          v49 = *(IErrorInfo **)&Size[1];
        }
        if ( v49 )
        {
          SetErrorInfo(0, v49);
          if ( *(_QWORD *)&Size[1] )
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&Size[1] + 16LL))(*(_QWORD *)&Size[1]);
        }
        v51 = (CBinXMLConvert *)*((_QWORD *)this + 982);
        if ( v51 )
        {
          CBinXMLConvert::`scalar deleting destructor'(v51, (unsigned int)v49);
          *((_QWORD *)this + 982) = 0;
        }
        if ( *((_BYTE *)this + 7801) )
        {
          v52 = 12;
          if ( *((_QWORD *)this + 974) )
            v52 = 5;
          *((_DWORD *)this + 16) = v52;
        }
        else if ( StreamOverRowset == 1 )
        {
          *((_DWORD *)this + 16) = 6;
          StreamOverRowset = 0;
        }
        else
        {
          *((_DWORD *)this + 16) = 10;
        }
        goto LABEL_166;
      case 0xA:
        v53 = (CIStreamError *)((__int64 (__fastcall *)(struct IMalloc *, __int64, __int64, __int64))g_pMO->lpVtbl[1].Release)(
                                 g_pMO,
                                 632,
                                 12,
                                 9);
        v63[0] = v53;
        if ( v53 )
          v55 = CIStreamError::CIStreamError(v53, StreamOverRowset, *((struct IErrorInfo **)this + 5), v54);
        else
          v55 = 0;
        *((_QWORD *)this + 7) = v55;
        if ( v55 )
        {
          *((_DWORD *)this + 16) = 9;
          StreamOverRowset = 0;
LABEL_167:
          if ( !a3 )
            goto LABEL_191;
          continue;
        }
        StreamOverRowset = -2147024882;
        if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
          bidTraceW(off_383B43498[0], 1437737, off_383B49128[0], 2147942414LL);
LABEL_191:
        if ( a4 )
          *a4 = v9;
        if ( StreamOverRowset == 1 )
          return v9 == 0;
        return StreamOverRowset;
      case 0xB:
        goto LABEL_190;
      case 0xC:
        StreamOverRowset = 1;
        if ( v9
          || !*((_BYTE *)this + 7800)
          || !(*(unsigned int (__fastcall **)(_QWORD, unsigned __int64, __int64, __int64))(**((_QWORD **)this + 5) + 40LL))(
                *((_QWORD *)this + 5),
                0x383800000uLL,
                12,
                9) )
        {
          goto LABEL_166;
        }
        *((_DWORD *)this + 16) = 11;
LABEL_190:
        StreamOverRowset = 265946;
        goto LABEL_191;
      default:
        goto LABEL_166;
    }
  }
}

```

## disassembly

```asm
0x383a8eaa0  push    rbp
0x383a8eaa2  push    rbx
0x383a8eaa3  push    rsi
0x383a8eaa4  push    rdi
0x383a8eaa5  push    r12
0x383a8eaa7  push    r13
0x383a8eaa9  push    r14
0x383a8eaab  push    r15
0x383a8eaad  lea     rbp, [rsp-398h]
0x383a8eab5  sub     rsp, 498h
0x383a8eabc  mov     [rsp+4D0h+var_470], 0FFFFFFFFFFFFFFFEh
0x383a8eac5  mov     rax, cs:__security_cookie
0x383a8eacc  xor     rax, rsp
0x383a8eacf  mov     [rbp+3D0h+var_50], rax
0x383a8ead6  mov     r12, r9
0x383a8ead9  mov     r14d, r8d
0x383a8eadc  mov     r13, rdx
0x383a8eadf  mov     rsi, rcx
0x383a8eae2  xor     ebx, ebx
0x383a8eae4  mov     edi, ebx
0x383a8eae6  mov     [rsp+4D0h+var_490], rbx
0x383a8eaeb  mov     r15d, ebx
0x383a8eaee  xor     edx, edx; perrinfo
0x383a8eaf0  xor     ecx, ecx; dwReserved
0x383a8eaf2  call    cs:__imp_SetErrorInfo
0x383a8eaf8  test    r13, r13
0x383a8eafb  jnz     short loc_383A8EB47
0x383a8eafd  mov     edi, 80030009h
0x383a8eb02  test    byte ptr cs:_bidGblFlags, 2
0x383a8eb09  jz      loc_383A8F6D2
0x383a8eb0f  mov     rcx, cs:off_383B43498; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a8eb16  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a8eb1d  test    rax, rax
0x383a8eb20  jz      loc_383A8F6D2
0x383a8eb26  mov     dword ptr [rsp+4D0h+lpWideCharStr], 398h
0x383a8eb2e  mov     r9d, edi
0x383a8eb31  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a8eb38  mov     edx, 0E6029h
0x383a8eb3d  call    _bidTraceW
0x383a8eb42  jmp     loc_383A8F6D2
0x383a8eb47  test    r14d, r14d
0x383a8eb4a  jz      loc_383A8F6D2
0x383a8eb50  mov     r8d, 0Ch
0x383a8eb56  lea     r10d, [r8-7]
0x383a8eb5a  lea     r9d, [r8-3]
0x383a8eb5e  mov     r11d, 4
0x383a8eb64  lea     rdx, cs:383800000h
0x383a8eb6b  cmp     edi, 1
0x383a8eb6e  jz      loc_383A8F6D2
0x383a8eb74  mov     dword ptr [rsp+4D0h+Size], ebx
0x383a8eb78  movsxd  rax, dword ptr [rsi+40h]
0x383a8eb7c  cmp     eax, 0Ch; switch 13 cases
0x383a8eb7f  ja      def_383A8EB8F; jumptable 0000000383A8EB8F default case, case 1
0x383a8eb85  mov     ecx, ds:(jpt_383A8EB8F - 383800000h)[rdx+rax*4]
0x383a8eb8c  add     rcx, rdx
0x383a8eb8f  jmp     rcx; switch jump
0x383a8eb91  mov     rcx, [rsi+28h]; jumptable 0000000383A8EB8F case 0
0x383a8eb95  mov     rax, [rcx]
0x383a8eb98  call    qword ptr [rax+60h]
0x383a8eb9b  mov     r11, rax
0x383a8eb9e  mov     [rsi+1E60h], rax
0x383a8eba5  test    rax, rax
0x383a8eba8  jz      loc_383A8EC50
0x383a8ebae  mov     r8, rax
0x383a8ebb1  movzx   edx, word ptr [rax]
0x383a8ebb4  test    dx, dx
0x383a8ebb7  jz      loc_383A8EC3C
0x383a8ebbd  movzx   ecx, dx
0x383a8ebc0  mov     eax, ecx
0x383a8ebc2  shr     rax, 8
0x383a8ebc6  movzx   ecx, cl
0x383a8ebc9  lea     r10, cs:383800000h
0x383a8ebd0  mov     rax, rva ?g_apCharTables@@3PAPEAEA[r10+rax*8]; uchar * near * g_apCharTables ...
0x383a8ebd8  test    byte ptr [rcx+rax], 4
0x383a8ebdc  jz      short loc_383A8EC3C
0x383a8ebde  mov     r9, rbx
0x383a8ebe1  cmp     dx, 3Ah ; ':'
0x383a8ebe5  jz      short loc_383A8EC3C
0x383a8ebe7  test    dx, dx
0x383a8ebea  jz      short loc_383A8EC3C
0x383a8ebec  nop     dword ptr [rax+00h]
0x383a8ebf0  movzx   ecx, dx
0x383a8ebf3  mov     eax, ecx
0x383a8ebf5  shr     rax, 8
0x383a8ebf9  movzx   ecx, cl
0x383a8ebfc  mov     rax, rva ?g_apCharTables@@3PAPEAEA[r10+rax*8]; uchar * near * g_apCharTables ...
0x383a8ec04  test    byte ptr [rcx+rax], 8
0x383a8ec08  jz      short loc_383A8EC25
0x383a8ec0a  cmp     dx, 3Ah ; ':'
0x383a8ec0e  jnz     short loc_383A8EC18
0x383a8ec10  test    r9, r9
0x383a8ec13  jnz     short loc_383A8EC2A
0x383a8ec15  mov     r9, r8
0x383a8ec18  add     r8, 2
0x383a8ec1c  movzx   edx, word ptr [r8]
0x383a8ec20  test    dx, dx
0x383a8ec23  jnz     short loc_383A8EBF0
0x383a8ec25  test    r9, r9
0x383a8ec28  jz      short loc_383A8EC3C
0x383a8ec2a  mov     rax, r8
0x383a8ec2d  sub     rax, r9
0x383a8ec30  and     rax, 0FFFFFFFFFFFFFFFEh
0x383a8ec34  cmp     rax, 2
0x383a8ec38  cmovz   r8, r9
0x383a8ec3c  cmp     word ptr [r8], 0
0x383a8ec41  jnz     loc_383A8F52B
0x383a8ec47  cmp     r8, r11
0x383a8ec4a  jz      loc_383A8F52B
0x383a8ec50  mov     rax, [rsi]
0x383a8ec53  mov     edx, 10h
0x383a8ec58  mov     rcx, rsi
0x383a8ec5b  call    qword ptr [rax+38h]
0x383a8ec5e  test    eax, eax
0x383a8ec60  jz      short loc_383A8ECB0
0x383a8ec62  mov     edx, 0FFh
0x383a8ec67  lea     rcx, [rsi+60h]
0x383a8ec6b  lea     r8, aUcs2; "UCS-2"
0x383a8ec72  sub     r8, rcx
0x383a8ec75  nop     word ptr [rax+rax+00000000h]
0x383a8ec80  lea     rax, [rdx+7FFFFEFFh]
0x383a8ec87  test    rax, rax
0x383a8ec8a  jz      short loc_383A8ECA4
0x383a8ec8c  movzx   eax, word ptr [r8+rcx]
0x383a8ec91  test    ax, ax
0x383a8ec94  jz      short loc_383A8ECA4
0x383a8ec96  mov     [rcx], ax
0x383a8ec99  add     rcx, 2
0x383a8ec9d  dec     rdx
0x383a8eca0  jnz     short loc_383A8EC80
0x383a8eca2  jmp     short loc_383A8ECA9
0x383a8eca4  test    rdx, rdx
0x383a8eca7  jnz     short loc_383A8ECAD
0x383a8eca9  sub     rcx, 2
0x383a8ecad  mov     [rcx], bx
0x383a8ecb0  lea     rdx, [rsi+60h]; unsigned __int16 *
0x383a8ecb4  mov     rcx, rsi; this
0x383a8ecb7  call    ?SetEncoding@CIStreamMultipleResults@@QEAAJPEBG@Z; CIStreamMultipleResults::SetEncoding(ushort const *)
0x383a8ecbc  mov     edi, eax
0x383a8ecbe  test    eax, eax
0x383a8ecc0  js      loc_383A8F584
0x383a8ecc6  mov     rax, [rsi]
0x383a8ecc9  mov     edx, 1
0x383a8ecce  mov     rcx, rsi
0x383a8ecd1  call    qword ptr [rax+38h]
0x383a8ecd4  test    eax, eax
0x383a8ecd6  jz      short loc_383A8ED27
0x383a8ecd8  mov     rcx, [rsi+1E60h]
0x383a8ecdf  test    rcx, rcx
0x383a8ece2  jz      short loc_383A8ED27
0x383a8ece4  cmp     word ptr [rcx], 0
0x383a8ece8  jz      short loc_383A8ED27
0x383a8ecea  or      rax, 0FFFFFFFFFFFFFFFFh
0x383a8ecee  xchg    ax, ax
0x383a8ecf0  inc     rax
0x383a8ecf3  cmp     word ptr [rcx+rax*2], 0
0x383a8ecf8  jnz     short loc_383A8ECF0
0x383a8ecfa  mov     [rsi+1E70h], rax
0x383a8ed01  mov     eax, [rsi+1E7Ch]
0x383a8ed07  cmp     eax, 4B0h
0x383a8ed0c  jz      short loc_383A8ED1E
0x383a8ed0e  cmp     eax, 2EE0h
0x383a8ed13  jz      short loc_383A8ED1E
0x383a8ed15  mov     dword ptr [rsi+40h], 3
0x383a8ed1c  jmp     short loc_383A8ED2E
0x383a8ed1e  mov     dword ptr [rsi+40h], 2
0x383a8ed25  jmp     short loc_383A8ED2E
0x383a8ed27  mov     dword ptr [rsi+40h], 6
0x383a8ed2e  mov     r8d, 0Ch
0x383a8ed34  lea     r9d, [r8-3]
0x383a8ed38  lea     r10d, [r8-7]
0x383a8ed3c  lea     r11d, [r8-8]
0x383a8ed40  cmp     qword ptr [rsi+30h], 0; jumptable 0000000383A8EB8F case 6
0x383a8ed45  jnz     short loc_383A8ED60
0x383a8ed47  mov     eax, r8d
0x383a8ed4a  cmp     qword ptr [rsi+1E70h], 0
0x383a8ed52  cmovnz  eax, r11d
0x383a8ed56  mov     [rsi+40h], eax
0x383a8ed59  jmp     loc_383A8F51B
0x383a8ed60  mov     rcx, [rsi+30h]
0x383a8ed64  mov     rax, [rcx]
0x383a8ed67  lea     rdx, [rsp+4D0h+var_490]
0x383a8ed6c  mov     qword ptr [rsp+4D0h+cchWideChar], rdx
0x383a8ed71  mov     [rsp+4D0h+lpWideCharStr], rbx
0x383a8ed76  lea     r9, IID_IRowset
0x383a8ed7d  xor     r8d, r8d
0x383a8ed80  xor     edx, edx
0x383a8ed82  call    qword ptr [rax+18h]
0x383a8ed85  mov     edi, eax
0x383a8ed87  test    eax, eax
0x383a8ed89  jnz     short loc_383A8EDB7
0x383a8ed8b  mov     rcx, [rsp+4D0h+var_490]; struct IRowset *
0x383a8ed90  test    rcx, rcx
0x383a8ed93  jz      short loc_383A8ED60
0x383a8ed95  lea     rdx, [rsi+38h]; struct ISequentialStream **
0x383a8ed99  call    ?CreateStreamOverRowset@@YAJPEAUIRowset@@PEAPEAUISequentialStream@@@Z; CreateStreamOverRowset(IRowset *,ISequentialStream * *)
0x383a8ed9e  mov     edi, eax
0x383a8eda0  mov     rcx, [rsp+4D0h+var_490]
0x383a8eda5  test    rcx, rcx
0x383a8eda8  jz      short loc_383A8EDEB
0x383a8edaa  mov     rax, [rcx]
0x383a8edad  call    qword ptr [rax+10h]
0x383a8edb0  mov     [rsp+4D0h+var_490], rbx
0x383a8edb5  jmp     short loc_383A8EDEB
0x383a8edb7  cmp     eax, 40EC9h
0x383a8edbc  jnz     short loc_383A8EDDD
0x383a8edbe  mov     r8d, 0Ch
0x383a8edc4  lea     r10d, [r8-7]
0x383a8edc8  lea     r9d, [r8-3]
0x383a8edcc  cmp     dword ptr [rsi+40h], 6
0x383a8edd0  jnz     loc_383A8F51B
0x383a8edd6  mov     edi, ebx
0x383a8edd8  jmp     loc_383A8F20A
0x383a8eddd  cmp     eax, 80040E05h
0x383a8ede2  jnz     short loc_383A8EDEB
0x383a8ede4  mov     byte ptr [rsi+1E79h], 1
0x383a8edeb  mov     r8d, 0Ch
0x383a8edf1  lea     r9d, [r8-3]
0x383a8edf5  lea     r10d, [r8-7]
0x383a8edf9  cmp     dword ptr [rsi+40h], 6
0x383a8edfd  jnz     loc_383A8F51B
0x383a8ee03  mov     eax, ebx
0x383a8ee05  test    edi, edi
0x383a8ee07  setnz   al
0x383a8ee0a  add     eax, r9d
0x383a8ee0d  mov     [rsi+40h], eax
0x383a8ee10  jmp     loc_383A8F51B
0x383a8ee15  cmp     qword ptr [rsi+1E70h], 0; jumptable 0000000383A8EB8F case 2
0x383a8ee1d  jz      short loc_383A8EE28
0x383a8ee1f  mov     dword ptr [rsi+44h], 3
0x383a8ee26  jmp     short loc_383A8EE4E
0x383a8ee28  test    edi, edi
0x383a8ee2a  jz      short loc_383A8EE3D
0x383a8ee2c  mov     eax, 0Ah
0x383a8ee31  cmp     edi, 40EC9h
0x383a8ee37  cmovz   eax, r8d
0x383a8ee3b  jmp     short loc_383A8EE4B
0x383a8ee3d  mov     eax, 6
0x383a8ee42  cmp     qword ptr [rsi+38h], 0
0x383a8ee47  cmovnz  eax, r9d
0x383a8ee4b  mov     [rsi+44h], eax
0x383a8ee4e  mov     rcx, [rsi+38h]
0x383a8ee52  test    rcx, rcx
0x383a8ee55  jz      short loc_383A8EEA3
0x383a8ee57  mov     rax, [rcx]
0x383a8ee5a  mov     edx, 2
0x383a8ee5f  call    qword ptr [rax+38h]
0x383a8ee62  test    eax, eax
0x383a8ee64  jz      short loc_383A8EE8F
0x383a8ee66  mov     rcx, [rsi+38h]
0x383a8ee6a  mov     rax, [rcx]
0x383a8ee6d  mov     edx, 20h ; ' '
0x383a8ee72  call    qword ptr [rax+38h]
0x383a8ee75  mov     r8d, 0Ch
0x383a8ee7b  lea     r9d, [r8-3]
0x383a8ee7f  lea     r10d, [r8-7]
0x383a8ee83  test    eax, eax
0x383a8ee85  jnz     short loc_383A8EE9D
0x383a8ee87  mov     eax, [rsi+44h]
0x383a8ee8a  jmp     loc_383A8F219
0x383a8ee8f  mov     r8d, 0Ch
0x383a8ee95  lea     r9d, [r8-3]
0x383a8ee99  lea     r10d, [r8-7]
0x383a8ee9d  mov     r11d, 4
0x383a8eea3  mov     dword ptr [rsi+40h], 8
0x383a8eeaa  cmp     dword ptr [rsi+1E7Ch], 2EE0h
0x383a8eeb4  jnz     short loc_383A8EECA
0x383a8eeb6  lea     rax, byte_383A8F740
0x383a8eebd  mov     [rsi+58h], rax
0x383a8eec1  mov     [rsi+50h], r11
0x383a8eec5  jmp     loc_383A8F51B
0x383a8eeca  lea     rax, dword_383A8F744
0x383a8eed1  mov     [rsi+58h], rax
0x383a8eed5  mov     qword ptr [rsi+50h], 2
0x383a8eedd  jmp     loc_383A8F51B
0x383a8eee2  mov     dword ptr [rsi+40h], 8; jumptable 0000000383A8EB8F case 3
0x383a8eee9  mov     [rsi+44h], r11d
0x383a8eeed  mov     eax, [rsi+1E7Ch]
0x383a8eef3  cmp     eax, 4B0h
0x383a8eef8  jz      short loc_383A8EF3F
0x383a8eefa  cmp     eax, 2EE0h
0x383a8eeff  jz      short loc_383A8EF3F
0x383a8ef01  lea     r9, [rsi+60h]
0x383a8ef05  lea     rbx, [rsi+25Eh]
0x383a8ef0c  lea     r8, aXmlVersion10En_0; "<?xml version=\"1.0\" encoding=\"%S\" ?"...
0x383a8ef13  mov     edx, 401h; unsigned __int64
0x383a8ef18  mov     rcx, rbx; char *
0x383a8ef1b  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x383a8ef20  test    eax, eax
0x383a8ef22  js      loc_383A8F5AA
0x383a8ef28  or      rax, 0FFFFFFFFFFFFFFFFh
0x383a8ef2c  nop     dword ptr [rax+00h]
0x383a8ef30  inc     rax
0x383a8ef33  cmp     byte ptr [rax+rbx], 0
0x383a8ef37  jnz     short loc_383A8EF30
0x383a8ef39  mov     [rsi+50h], rax
0x383a8ef3d  jmp     short loc_383A8EF94
0x383a8ef3f  lea     r9, [rsi+60h]
0x383a8ef43  lea     rbx, [rsi+25Eh]
0x383a8ef4a  lea     r8, aXmlVersion10En; "<?xml version=\"1.0\" encoding=\"%s\" ?"...
0x383a8ef51  mov     edx, 401h; unsigned __int64
  ... truncated ...
```
