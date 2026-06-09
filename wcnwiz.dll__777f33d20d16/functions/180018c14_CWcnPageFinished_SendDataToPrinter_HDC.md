# CWcnPageFinished::SendDataToPrinter(HDC__ *)

- ea: `0x180018c14`
- end: `0x1800196b7`
- name: `?SendDataToPrinter@CWcnPageFinished@@QEAAJPEAUHDC__@@@Z`
- size: `2723`
- prototype: `int(CWcnPageFinished *__hidden this, HDC)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x180018584`

## callees

- `0x180001820`
- `0x180002294`
- `0x18000d630`
- `0x18000e0a0`
- `0x18000e19c`
- `0x18000e1dc`
- `0x180018c14`
- `0x18001974c`
- `0x18001b9a4`
- `0x18001f6b8`
- `0x18002de1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018e17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018e7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800193e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001942b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800194ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800194f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001956f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800195d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018e17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018e7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800193e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001942b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800194ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800194f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001956f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800195d3`
- `wlanapi!WlanUtf8SsidToDisplayName` at `0x180018f97`
- `wlanapi!WlanUtf8SsidToDisplayName` at `0x180018f97`
- `GDI32!StartPage` at `0x180018e72`
- `GDI32!StartPage` at `0x180018e72`
- `GDI32!EndDoc` at `0x1800195c9`
- `GDI32!EndDoc` at `0x1800195c9`
- `GDI32!GetDeviceCaps` at `0x180018d6b`
- `GDI32!GetDeviceCaps` at `0x180018d6b`
- `GDI32!GetTextMetricsW` at `0x180018ec1`
- `GDI32!GetTextMetricsW` at `0x180018ec1`
- `GDI32!TextOutW` at `0x1800191fd`
- `GDI32!TextOutW` at `0x1800192bf`
- `GDI32!TextOutW` at `0x180019377`
- `GDI32!TextOutW` at `0x1800191fd`
- `GDI32!TextOutW` at `0x1800192bf`
- `GDI32!TextOutW` at `0x180019377`
- `GDI32!StartDocW` at `0x180018e0d`
- `GDI32!StartDocW` at `0x180018e0d`
- `GDI32!EndPage` at `0x180019565`
- `GDI32!EndPage` at `0x180019565`
- `GDI32!DeleteObject` at `0x18001962e`
- `GDI32!DeleteObject` at `0x180019645`
- `GDI32!DeleteObject` at `0x18001962e`
- `GDI32!DeleteObject` at `0x180019645`
- `GDI32!SelectObject` at `0x1800191cd`
- `GDI32!SelectObject` at `0x180019222`
- `GDI32!SelectObject` at `0x1800191cd`
- `GDI32!SelectObject` at `0x180019222`
- `GDI32!GetTextExtentPoint32W` at `0x18001924e`
- `GDI32!GetTextExtentPoint32W` at `0x18001924e`

## pseudocode

```c
__int64 __fastcall CWcnPageFinished::SendDataToPrinter(CWcnPageFinished *this, HDC a2)
{
  const char *Indent; // rax
  __int64 v5; // r10
  HGDIOBJ v6; // r13
  int DeviceCaps; // r12d
  int v8; // eax
  signed int v9; // ebx
  _BYTE *v10; // r10
  signed int LastError; // eax
  unsigned int v12; // eax
  __int64 v13; // r10
  int v14; // edx
  signed int v15; // eax
  int Font; // eax
  int v17; // eax
  int v18; // eax
  unsigned int v19; // ecx
  __int64 v20; // rcx
  int v21; // edx
  int v22; // edx
  const char *v23; // rax
  __int64 v24; // r10
  __int64 v25; // rdx
  UINT v26; // ecx
  unsigned int v27; // eax
  __int64 v28; // r10
  int v29; // edx
  __int64 v30; // rcx
  UINT v31; // ecx
  int v32; // esi
  int i; // eax
  __int64 v34; // r12
  double tmHeight; // xmm6_8
  int v36; // eax
  int v37; // esi
  __int64 c; // rax
  double v39; // xmm6_8
  __int64 v40; // r8
  const WCHAR *v41; // r15
  int v42; // r13d
  __int64 v43; // rax
  int v44; // ebx
  __int64 v45; // rcx
  unsigned __int64 v46; // rdx
  int v47; // r12d
  __int64 v48; // rax
  int v49; // r11d
  signed int v50; // eax
  signed int v51; // eax
  __int64 v52; // rdx
  signed int v53; // eax
  signed int v54; // eax
  signed int v55; // eax
  unsigned int v56; // eax
  __int64 v57; // r10
  signed int v58; // eax
  unsigned int v59; // eax
  __int64 v60; // r10
  unsigned int v62; // [rsp+38h] [rbp-D0h]
  int v63; // [rsp+3Ch] [rbp-CCh]
  int v64; // [rsp+40h] [rbp-C8h]
  int v65; // [rsp+44h] [rbp-C4h]
  HGDIOBJ ho; // [rsp+48h] [rbp-C0h] BYREF
  int v67; // [rsp+50h] [rbp-B8h] BYREF
  int v68; // [rsp+54h] [rbp-B4h]
  HGDIOBJ h; // [rsp+58h] [rbp-B0h] BYREF
  struct tagSIZE psizl; // [rsp+60h] [rbp-A8h] BYREF
  UINT uID[2]; // [rsp+68h] [rbp-A0h]
  DOCINFOW v72; // [rsp+70h] [rbp-98h] BYREF
  __int64 v73; // [rsp+98h] [rbp-70h]
  const unsigned __int16 *v74; // [rsp+A0h] [rbp-68h]
  LPCWSTR lpString[2]; // [rsp+A8h] [rbp-60h]
  __int128 v76; // [rsp+B8h] [rbp-50h]
  struct tagTEXTMETRICW tm; // [rsp+C8h] [rbp-40h] BYREF
  WCHAR v78; // [rsp+108h] [rbp+0h] BYREF
  _BYTE v79[254]; // [rsp+10Ah] [rbp+2h] BYREF
  WCHAR v80; // [rsp+208h] [rbp+100h] BYREF
  _BYTE v81[254]; // [rsp+20Ah] [rbp+102h] BYREF
  __int16 v82; // [rsp+308h] [rbp+200h] BYREF
  _BYTE v83[334]; // [rsp+30Ah] [rbp+202h] BYREF
  WCHAR v84[328]; // [rsp+458h] [rbp+350h] BYREF
  WCHAR String[512]; // [rsp+6E8h] [rbp+5E0h] BYREF
  WCHAR Buffer[512]; // [rsp+AE8h] [rbp+9E0h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v5 + 16), 22, WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids, Indent);
  }
  v73 = 0;
  memset(&v72.lpszDocName, 0, 32);
  memset_0(Buffer, 0, sizeof(Buffer));
  memset_0(String, 0, sizeof(String));
  ho = 0;
  h = 0;
  v6 = 0;
  v82 = 0;
  memset_0(v83, 0, 0x140u);
  v67 = 161;
  v78 = 0;
  memset_0(v79, 0, sizeof(v79));
  v80 = 0;
  memset_0(v81, 0, sizeof(v81));
  uID[0] = 4369;
  uID[1] = 4380;
  v72.cbSize = 4381;
  *(&v72.cbSize + 1) = 4382;
  *(_OWORD *)lpString = 0;
  v76 = 0;
  memset(&tm, 0, sizeof(tm));
  DeviceCaps = GetDeviceCaps(a2, 8);
  if ( DeviceCaps <= 0 )
    DeviceCaps = 1;
  v62 = DeviceCaps;
  memset(&v72.lpszDocName, 0, 32);
  v73 = 0;
  LODWORD(v72.lpszDocName) = 40;
  v8 = WcnUxLoadString(0xF95u, 0x200u, Buffer);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return (unsigned int)v9;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_143;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids, (unsigned int)v8);
    goto LABEL_142;
  }
  LODWORD(v73) = 0;
  v72.lpszOutput = Buffer;
  *(_OWORD *)&v72.lpszDatatype = 0;
  if ( StartDocW(a2, (const DOCINFOW *)&v72.lpszDocName) <= 0 )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = (unsigned int)GetIndent(0);
        v14 = 24;
LABEL_16:
        WPP_SF_sd(*(_QWORD *)(v13 + 16), v14, (unsigned int)WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids, v12, v9);
LABEL_142:
        v10 = WPP_GLOBAL_Control;
        goto LABEL_143;
      }
      goto LABEL_143;
    }
    return (unsigned int)v9;
  }
  if ( StartPage(a2) > 0 )
  {
    if ( GetTextMetricsW(a2, &tm) )
    {
      Font = WcnSysCreateFont(tm.tmHeight, tm.tmAveCharWidth, 1u, tm.tmPitchAndFamily, 700, (HFONT *)&h);
      if ( Font < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids,
          (unsigned int)Font);
      }
      v17 = WcnSysCreateFont(tm.tmHeight, tm.tmAveCharWidth, 1u, tm.tmPitchAndFamily, 400, (HFONT *)&ho);
      if ( v17 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids,
          (unsigned int)v17);
      v6 = ho;
    }
    v18 = WlanUtf8SsidToDisplayName(*((_QWORD *)this + 24) + 752LL, 1, &v82, &v67);
    if ( v18 )
    {
      if ( v18 > 0 )
        v19 = (unsigned __int16)v18 | 0x80070000;
      else
        v19 = v18;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      {
LABEL_41:
        v20 = *((_QWORD *)this + 24);
        lpString[0] = (LPCWSTR)&v82;
        v21 = *(_DWORD *)(v20 + 880);
        lpString[1] = *(LPCWSTR *)(v20 + 232);
        v22 = v21 - 1;
        if ( v22 )
        {
          if ( v22 != 31 )
          {
            v9 = -2147024846;
            if ( v10 == (_BYTE *)&WPP_GLOBAL_Control || v10[25] < 2u )
              goto LABEL_138;
            v23 = GetIndent(0);
            v25 = 29;
            goto LABEL_46;
          }
          v26 = 4351;
        }
        else
        {
          v26 = 4353;
        }
        v9 = WcnUxLoadString(v26, 0x80u, &v78);
        if ( v9 >= 0 )
        {
          v30 = *((_QWORD *)this + 24);
          *(_QWORD *)&v76 = &v78;
          switch ( *(_DWORD *)(v30 + 884) )
          {
            case 1:
              v31 = 4354;
              break;
            case 4:
              v31 = 4356;
              break;
            case 8:
              v31 = 4357;
              break;
            default:
              v9 = -2147024846;
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                goto LABEL_138;
              v23 = GetIndent(0);
              v25 = 31;
LABEL_46:
              WPP_SF_s(*(_QWORD *)(v24 + 16), v25, WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids, v23);
LABEL_137:
              v10 = WPP_GLOBAL_Control;
              goto LABEL_138;
          }
          v9 = WcnUxLoadString(v31, 0x80u, &v80);
          if ( v9 >= 0 )
          {
            v32 = 25;
            *((_QWORD *)&v76 + 1) = &v80;
            for ( i = 0; ; i = v65 + 1 )
            {
              v65 = i;
              if ( i >= 4 )
                break;
              v34 = i;
              tmHeight = (double)tm.tmHeight;
              v36 = WcnUxLoadString(uID[i], 0x200u, String);
              v9 = v36;
              if ( v36 < 0 )
              {
                v10 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  goto LABEL_138;
                v52 = 33;
LABEL_110:
                WPP_SF_d(*((_QWORD *)v10 + 2), v52, WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids, (unsigned int)v36);
                goto LABEL_137;
              }
              v37 = v32 - (int)(tmHeight * -1.5);
              if ( h )
                SelectObject(a2, h);
              c = -1;
              do
                ++c;
              while ( String[c] );
              if ( !TextOutW(a2, v62 / 0xA, v37, String, c) )
              {
                v54 = GetLastError();
                v9 = v54;
                if ( v54 > 0 )
                  v9 = (unsigned __int16)v54 | 0x80070000;
                v10 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v27 = (unsigned int)GetIndent(0);
                  v29 = 34;
                  goto LABEL_136;
                }
                goto LABEL_138;
              }
              v39 = (double)tm.tmHeight;
              if ( v6 )
                SelectObject(a2, v6);
              psizl = 0;
              v40 = -1;
              v41 = lpString[v34];
              do
                ++v40;
              while ( v41[v40] );
              if ( !GetTextExtentPoint32W(a2, v41, v40, &psizl) )
              {
                v53 = GetLastError();
                v9 = v53;
                if ( v53 > 0 )
                  v9 = (unsigned __int16)v53 | 0x80070000;
                v10 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v27 = (unsigned int)GetIndent(0);
                  v29 = 35;
                  goto LABEL_136;
                }
                goto LABEL_138;
              }
              v42 = v62 >> 2;
              v32 = v37 - (int)(v39 * -1.5);
              if ( (int)v62 <= (int)((double)psizl.cx * 1.8 + (double)(v62 >> 2)) )
              {
                v44 = (int)(v62 - v42) / (int)((double)tm.tmAveCharWidth * 1.8);
                v68 = v44;
                memset_0(v84, 0, 0x282u);
                v45 = -1;
                do
                  ++v45;
                while ( v41[v45] );
                v63 = 0;
                v46 = 0;
                while ( 1 )
                {
                  v47 = v44;
                  v64 = v46;
                  if ( v44 >= (int)v45 )
                    v47 = v45;
                  v74 = &v41[(int)v46];
                  v36 = StringCchCopyNW(v84, v46, v74, v47);
                  v9 = v36;
                  if ( v36 < 0 )
                    break;
                  if ( !TextOutW(a2, v42, v32, v84, v47) )
                  {
                    v51 = GetLastError();
                    v9 = v51;
                    if ( v51 > 0 )
                      v9 = (unsigned __int16)v51 | 0x80070000;
                    v10 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      v27 = (unsigned int)GetIndent(0);
                      v29 = 38;
                      goto LABEL_136;
                    }
                    goto LABEL_138;
                  }
                  v48 = -1;
                  v49 = v47 + v63;
                  v45 = -1;
                  v63 += v47;
                  do
                    ++v45;
                  while ( v41[v45] );
                  LODWORD(v45) = v45 - v49;
                  do
                    ++v48;
                  while ( v74[v48] );
                  if ( (int)v45 <= 0 )
                    goto LABEL_83;
                  v44 = v68;
                  v46 = (unsigned int)(v48 - v45 + v64);
                  v32 += (int)((double)tm.tmHeight * 1.1);
                }
                v10 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v52 = 37;
                  goto LABEL_110;
                }
                goto LABEL_138;
              }
              v43 = -1;
              do
                ++v43;
              while ( v41[v43] );
              if ( !TextOutW(a2, v42, v32, v41, v43) )
              {
                v50 = GetLastError();
                v9 = v50;
                if ( v50 > 0 )
                  v9 = (unsigned __int16)v50 | 0x80070000;
                v10 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v27 = (unsigned int)GetIndent(0);
                  v29 = 36;
                  goto LABEL_136;
                }
                goto LABEL_138;
              }
LABEL_83:
              v6 = ho;
            }
            if ( EndPage(a2) <= 0 )
            {
              v55 = GetLastError();
              v9 = v55;
              if ( v55 > 0 )
                v9 = (unsigned __int16)v55 | 0x80070000;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v56 = (unsigned int)GetIndent(0);
                WPP_SF_sd(
                  *(_QWORD *)(v57 + 16),
                  39,
                  (unsigned int)WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids,
                  v56,
                  v9);
              }
            }
            if ( EndDoc(a2) > 0 )
              goto LABEL_137;
            v58 = GetLastError();
            v9 = v58;
            if ( v58 > 0 )
              v9 = (unsigned __int16)v58 | 0x80070000;
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v27 = (unsigned int)GetIndent(0);
              v29 = 40;
              goto LABEL_136;
            }
            goto LABEL_138;
          }
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
LABEL_138:
            if ( h )
            {
              DeleteObject(h);
              v10 = WPP_GLOBAL_Control;
            }
            if ( !ho )
              goto LABEL_143;
            DeleteObject(ho);
            goto LABEL_142;
          }
          v27 = (unsigned int)GetIndent(0);
          v29 = 32;
        }
        else
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_138;
          v27 = (unsigned int)GetIndent(0);
          v29 = 30;
        }
LABEL_136:
        WPP_SF_sd(*(_QWORD *)(v28 + 16), v29, (unsigned int)WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids, v27, v9);
        goto LABEL_137;
      }
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids,
        (unsigned int)v18,
        v19 | 0x80000000);
    }
    v10 = WPP_GLOBAL_Control;
    goto LABEL_41;
  }
  v15 = GetLastError();
  v9 = v15;
  if ( v15 > 0 )
    v9 = (unsigned __int16)v15 | 0x80070000;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = (unsigned int)GetIndent(0);
      v14 = 25;
      goto LABEL_16;
    }
LABEL_143:
    if ( v10 != (_BYTE *)&WPP_GLOBAL_Control && (v9 < 0 || v10[25] >= 6u) )
    {
      v59 = (unsigned int)GetIndent(-1);
      WPP_SF_sd(*(_QWORD *)(v60 + 16), 41, (unsigned int)WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids, v59, v9);
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180018c14  mov     rax, rsp
0x180018c17  mov     [rax+18h], rbx
0x180018c1b  push    rbp
0x180018c1c  push    rsi
0x180018c1d  push    rdi
0x180018c1e  push    r12
0x180018c20  push    r13
0x180018c22  push    r14
0x180018c24  push    r15
0x180018c26  lea     rbp, [rax-0E38h]
0x180018c2d  sub     rsp, 0F00h
0x180018c34  movaps  xmmword ptr [rax-48h], xmm6
0x180018c38  mov     rax, cs:__security_cookie
0x180018c3f  xor     rax, rsp
0x180018c42  mov     [rbp+0E30h+var_50], rax
0x180018c49  mov     r14, rdx
0x180018c4c  mov     rsi, rcx
0x180018c4f  mov     r10, cs:WPP_GLOBAL_Control
0x180018c56  lea     r15, WPP_GLOBAL_Control
0x180018c5d  cmp     r10, r15
0x180018c60  jz      short loc_180018C8B
0x180018c62  cmp     byte ptr [r10+19h], 6
0x180018c67  jb      short loc_180018C8B
0x180018c69  mov     ecx, 1; int
0x180018c6e  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180018c73  mov     rcx, [r10+10h]
0x180018c77  lea     r8, WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids
0x180018c7e  mov     edx, 16h
0x180018c83  mov     r9, rax
0x180018c86  call    WPP_SF_s
0x180018c8b  xorps   xmm0, xmm0
0x180018c8e  lea     rcx, [rbp+0E30h+Buffer]; void *
0x180018c95  xor     eax, eax
0x180018c97  mov     ebx, 400h
0x180018c9c  mov     r8d, ebx; Size
0x180018c9f  mov     [rbp+0E30h+var_EA0], rax
0x180018ca3  xor     edx, edx; Val
0x180018ca5  movups  xmmword ptr [rsp+0F30h+var_EC8.lpszDocName], xmm0
0x180018caa  movups  xmmword ptr [rbp+0E30h+var_EC8.lpszDatatype], xmm0
0x180018cae  call    memset_0
0x180018cb3  mov     r8d, ebx; Size
0x180018cb6  lea     rcx, [rbp+0E30h+String]; void *
0x180018cbd  xor     edx, edx; Val
0x180018cbf  call    memset_0
0x180018cc4  xor     edi, edi
0x180018cc6  lea     rcx, [rbp+0E30h+var_C2E]; void *
0x180018ccd  xor     edx, edx; Val
0x180018ccf  mov     [rsp+0F30h+ho], rdi
0x180018cd4  mov     r8d, 140h; Size
0x180018cda  mov     [rsp+0F30h+h], rdi
0x180018cdf  mov     r13d, edi
0x180018ce2  mov     [rbp+0E30h+var_C30], di
0x180018ce9  call    memset_0
0x180018cee  mov     ebx, 0FEh
0x180018cf3  mov     dword ptr [rsp+0F30h+var_EE8], 0A1h
0x180018cfb  mov     r8d, ebx; Size
0x180018cfe  mov     [rbp+0E30h+var_E30], di
0x180018d02  xor     edx, edx; Val
0x180018d04  lea     rcx, [rbp+0E30h+var_E2E]; void *
0x180018d08  call    memset_0
0x180018d0d  mov     r8d, ebx; Size
0x180018d10  mov     [rbp+0E30h+var_D30], di
0x180018d17  xor     edx, edx; Val
0x180018d19  lea     rcx, [rbp+0E30h+var_D2E]; void *
0x180018d20  call    memset_0
0x180018d25  xorps   xmm0, xmm0
0x180018d28  mov     [rsp+0F30h+uID], 1111h
0x180018d30  xorps   xmm1, xmm1
0x180018d33  mov     [rsp+0F30h+var_ECC], 111Ch
0x180018d3b  movups  xmmword ptr [rbp+0E30h+tm.tmOverhang], xmm0
0x180018d3f  lea     edx, [rdi+8]; index
0x180018d42  mov     [rsp+0F30h+var_EC8.cbSize], 111Dh
0x180018d4a  mov     rcx, r14; hdc
0x180018d4d  mov     dword ptr [rsp+0F30h+var_EC8+4], 111Eh
0x180018d55  movups  xmmword ptr [rbp+0E30h+tm.tmFirstChar], xmm0
0x180018d59  movdqu  xmmword ptr [rbp+0E30h+lpString], xmm0
0x180018d5e  movdqu  [rbp+0E30h+var_E80], xmm1
0x180018d63  movups  xmmword ptr [rbp+0E30h+tm.tmHeight], xmm0
0x180018d67  movups  xmmword ptr [rbp+0E30h+tm.tmExternalLeading], xmm0
0x180018d6b  call    cs:__imp_GetDeviceCaps
0x180018d71  xorps   xmm0, xmm0
0x180018d74  lea     r8, [rbp+0E30h+Buffer]; lpBuffer
0x180018d7b  mov     r12d, eax
0x180018d7e  test    eax, eax
0x180018d80  lea     eax, [rdi+1]
0x180018d83  mov     edx, 200h; cchBufferMax
0x180018d88  cmovle  r12d, eax
0x180018d8c  mov     ecx, 0F95h; uID
0x180018d91  xor     eax, eax
0x180018d93  mov     [rsp+0F30h+var_F00], r12d
0x180018d98  movups  xmmword ptr [rsp+0F30h+var_EC8.lpszDocName], xmm0
0x180018d9d  mov     [rbp+0E30h+var_EA0], rax
0x180018da1  movups  xmmword ptr [rbp+0E30h+var_EC8.lpszDatatype], xmm0
0x180018da5  mov     dword ptr [rsp+0F30h+var_EC8.lpszDocName], 28h ; '('
0x180018dad  call    ?WcnUxLoadString@@YAJIKPEAG@Z; WcnUxLoadString(uint,ulong,ushort *)
0x180018db2  mov     ebx, eax
0x180018db4  test    eax, eax
0x180018db6  jns     short loc_180018DEE
0x180018db8  mov     r10, cs:WPP_GLOBAL_Control
0x180018dbf  cmp     r10, r15
0x180018dc2  jz      loc_180019686
0x180018dc8  cmp     byte ptr [r10+19h], 2
0x180018dcd  jb      loc_180019652
0x180018dd3  mov     rcx, [r10+10h]
0x180018dd7  lea     edx, [rdi+17h]
0x180018dda  mov     r9d, eax
0x180018ddd  lea     r8, WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids
0x180018de4  call    WPP_SF_d
0x180018de9  jmp     loc_18001964B
0x180018dee  lea     rax, [rbp+0E30h+Buffer]
0x180018df5  mov     dword ptr [rbp+0E30h+var_EA0], edi
0x180018df8  xorps   xmm0, xmm0
0x180018dfb  mov     [rsp+0F30h+var_EC8.lpszOutput], rax
0x180018e00  lea     rdx, [rsp+0F30h+var_EC8.lpszDocName]; lpdi
0x180018e05  mov     rcx, r14; hdc
0x180018e08  movdqu  xmmword ptr [rbp+0E30h+var_EC8.lpszDatatype], xmm0
0x180018e0d  call    cs:__imp_StartDocW
0x180018e13  test    eax, eax
0x180018e15  jg      short loc_180018E6F
0x180018e17  call    cs:__imp_GetLastError
0x180018e1d  mov     ebx, eax
0x180018e1f  test    eax, eax
0x180018e21  jle     short loc_180018E2C
0x180018e23  movzx   ebx, ax
0x180018e26  or      ebx, 80070000h
0x180018e2c  mov     r10, cs:WPP_GLOBAL_Control
0x180018e33  cmp     r10, r15
0x180018e36  jz      loc_180019686
0x180018e3c  cmp     byte ptr [r10+19h], 2
0x180018e41  jb      loc_180019652
0x180018e47  xor     ecx, ecx; int
0x180018e49  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180018e4e  mov     edx, 18h
0x180018e53  mov     rcx, [r10+10h]
0x180018e57  lea     r8, WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids
0x180018e5e  mov     r9, rax
0x180018e61  mov     [rsp+0F30h+c], ebx
0x180018e65  call    WPP_SF_sd
0x180018e6a  jmp     loc_18001964B
0x180018e6f  mov     rcx, r14; hdc
0x180018e72  call    cs:__imp_StartPage
0x180018e78  test    eax, eax
0x180018e7a  jg      short loc_180018EBA
0x180018e7c  call    cs:__imp_GetLastError
0x180018e82  mov     ebx, eax
0x180018e84  test    eax, eax
0x180018e86  jle     short loc_180018E91
0x180018e88  movzx   ebx, ax
0x180018e8b  or      ebx, 80070000h
0x180018e91  mov     r10, cs:WPP_GLOBAL_Control
0x180018e98  cmp     r10, r15
0x180018e9b  jz      loc_180019686
0x180018ea1  cmp     byte ptr [r10+19h], 2
0x180018ea6  jb      loc_180019652
0x180018eac  xor     ecx, ecx; int
0x180018eae  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180018eb3  mov     edx, 19h
0x180018eb8  jmp     short loc_180018E53
0x180018eba  lea     rdx, [rbp+0E30h+tm]; lptm
0x180018ebe  mov     rcx, r14; hdc
0x180018ec1  call    cs:__imp_GetTextMetricsW
0x180018ec7  mov     ebx, 1
0x180018ecc  test    eax, eax
0x180018ece  jz      loc_180018F7B
0x180018ed4  mov     r9b, [rbp+0E30h+tm.tmPitchAndFamily]; unsigned __int8
0x180018ed8  lea     rax, [rsp+0F30h+h]
0x180018edd  mov     edx, [rbp+0E30h+tm.tmAveCharWidth]; cWidth
0x180018ee0  mov     r8b, bl; unsigned __int8
0x180018ee3  mov     ecx, [rbp+0E30h+tm.tmHeight]; cHeight
0x180018ee6  mov     [rsp+0F30h+var_F08], rax; HFONT *
0x180018eeb  mov     [rsp+0F30h+c], 2BCh; int
0x180018ef3  call    ?WcnSysCreateFont@@YAJJJEEJPEAPEAUHFONT__@@@Z; WcnSysCreateFont(long,long,uchar,uchar,long,HFONT__ * *)
0x180018ef8  test    eax, eax
0x180018efa  jns     short loc_180018F24
0x180018efc  mov     rcx, cs:WPP_GLOBAL_Control
0x180018f03  cmp     rcx, r15
0x180018f06  jz      short loc_180018F24
0x180018f08  cmp     byte ptr [rcx+19h], 3
0x180018f0c  jb      short loc_180018F24
0x180018f0e  mov     rcx, [rcx+10h]
0x180018f12  lea     edx, [rbx+19h]
0x180018f15  mov     r9d, eax
0x180018f18  lea     r8, WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids
0x180018f1f  call    WPP_SF_d
0x180018f24  mov     r9b, [rbp+0E30h+tm.tmPitchAndFamily]; unsigned __int8
0x180018f28  lea     rax, [rsp+0F30h+ho]
0x180018f2d  mov     edx, [rbp+0E30h+tm.tmAveCharWidth]; cWidth
0x180018f30  mov     r8b, bl; unsigned __int8
0x180018f33  mov     ecx, [rbp+0E30h+tm.tmHeight]; cHeight
0x180018f36  mov     [rsp+0F30h+var_F08], rax; HFONT *
0x180018f3b  mov     [rsp+0F30h+c], 190h; int
0x180018f43  call    ?WcnSysCreateFont@@YAJJJEEJPEAPEAUHFONT__@@@Z; WcnSysCreateFont(long,long,uchar,uchar,long,HFONT__ * *)
0x180018f48  test    eax, eax
0x180018f4a  jns     short loc_180018F76
0x180018f4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180018f53  cmp     rcx, r15
0x180018f56  jz      short loc_180018F76
0x180018f58  cmp     byte ptr [rcx+19h], 3
0x180018f5c  jb      short loc_180018F76
0x180018f5e  mov     rcx, [rcx+10h]
0x180018f62  lea     r8, WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids
0x180018f69  mov     edx, 1Bh
0x180018f6e  mov     r9d, eax
0x180018f71  call    WPP_SF_d
0x180018f76  mov     r13, [rsp+0F30h+ho]
0x180018f7b  mov     rcx, [rsi+0C0h]
0x180018f82  lea     r9, [rsp+0F30h+var_EE8]
0x180018f87  add     rcx, 2F0h
0x180018f8e  lea     r8, [rbp+0E30h+var_C30]
0x180018f95  mov     edx, ebx
0x180018f97  call    cs:__imp_WlanUtf8SsidToDisplayName
0x180018f9d  xor     r12d, r12d
0x180018fa0  mov     edi, 80070000h
0x180018fa5  test    eax, eax
0x180018fa7  jz      short loc_180018FE9
0x180018fa9  jg      short loc_180018FAF
0x180018fab  mov     ecx, eax
0x180018fad  jmp     short loc_180018FB4
0x180018faf  movzx   ecx, ax
0x180018fb2  or      ecx, edi
0x180018fb4  mov     r10, cs:WPP_GLOBAL_Control
0x180018fbb  cmp     r10, r15
0x180018fbe  jz      short loc_180018FF0
0x180018fc0  cmp     byte ptr [r10+19h], 3
0x180018fc5  jb      short loc_180018FF0
0x180018fc7  or      ecx, 80000000h
0x180018fcd  lea     r8, WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids
0x180018fd4  mov     [rsp+0F30h+c], ecx
0x180018fd8  mov     edx, 1Ch
0x180018fdd  mov     rcx, [r10+10h]
0x180018fe1  mov     r9d, eax
0x180018fe4  call    WPP_SF_Dd
0x180018fe9  mov     r10, cs:WPP_GLOBAL_Control
0x180018ff0  mov     rcx, [rsi+0C0h]
0x180018ff7  lea     rax, [rbp+0E30h+var_C30]
0x180018ffe  mov     [rbp+0E30h+lpString], rax
0x180019002  mov     edx, [rcx+370h]
0x180019008  mov     rax, [rcx+0E8h]
0x18001900f  mov     [rbp+0E30h+lpString+8], rax
0x180019013  sub     edx, 1
0x180019016  jz      short loc_180019061
0x180019018  cmp     edx, 1Fh
0x18001901b  jz      short loc_18001905A
0x18001901d  mov     ebx, 80070032h
0x180019022  cmp     r10, r15
0x180019025  jz      loc_180019621
0x18001902b  cmp     byte ptr [r10+19h], 2
0x180019030  jb      loc_180019621
0x180019036  xor     ecx, ecx; int
0x180019038  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001903d  mov     edx, 1Dh
0x180019042  mov     rcx, [r10+10h]
0x180019046  lea     r8, WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids
0x18001904d  mov     r9, rax
0x180019050  call    WPP_SF_s
0x180019055  jmp     loc_18001961A
0x18001905a  mov     ecx, 10FFh
0x18001905f  jmp     short loc_180019066
0x180019061  mov     ecx, 1101h; uID
0x180019066  lea     r8, [rbp+0E30h+var_E30]; lpBuffer
0x18001906a  mov     edx, 80h; cchBufferMax
0x18001906f  call    ?WcnUxLoadString@@YAJIKPEAG@Z; WcnUxLoadString(uint,ulong,ushort *)
0x180019074  mov     ebx, eax
0x180019076  test    eax, eax
0x180019078  jns     short loc_1800190A6
0x18001907a  mov     r10, cs:WPP_GLOBAL_Control
0x180019081  cmp     r10, r15
0x180019084  jz      loc_180019621
0x18001908a  cmp     byte ptr [r10+19h], 2
0x18001908f  jb      loc_180019621
0x180019095  xor     ecx, ecx; int
0x180019097  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001909c  mov     edx, 1Eh
0x1800190a1  jmp     loc_180019603
0x1800190a6  mov     rcx, [rsi+0C0h]
0x1800190ad  lea     rax, [rbp+0E30h+var_E30]
0x1800190b1  mov     qword ptr [rbp+0E30h+var_E80], rax
0x1800190b5  mov     edx, [rcx+374h]
0x1800190bb  sub     edx, 1
0x1800190be  jz      short loc_180019109
0x1800190c0  sub     edx, 3
0x1800190c3  jz      short loc_180019102
0x1800190c5  cmp     edx, 4
0x1800190c8  jz      short loc_1800190FB
0x1800190ca  mov     ebx, 80070032h
0x1800190cf  mov     r10, cs:WPP_GLOBAL_Control
0x1800190d6  cmp     r10, r15
0x1800190d9  jz      loc_180019621
0x1800190df  cmp     byte ptr [r10+19h], 2
0x1800190e4  jb      loc_180019621
0x1800190ea  xor     ecx, ecx; int
0x1800190ec  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800190f1  mov     edx, 1Fh
0x1800190f6  jmp     loc_180019042
0x1800190fb  mov     ecx, 1105h
0x180019100  jmp     short loc_18001910E
0x180019102  mov     ecx, 1104h
0x180019107  jmp     short loc_18001910E
0x180019109  mov     ecx, 1102h; uID
0x18001910e  lea     r8, [rbp+0E30h+var_D30]; lpBuffer
  ... truncated ...
```
