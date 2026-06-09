# IumCrashReport(_IUM_DUMP_REPORT_INFO *,wchar_t *)

- ea: `0x180020e70`
- end: `0x180021b81`
- name: `?IumCrashReport@@YAKPEAU_IUM_DUMP_REPORT_INFO@@PEA_W@Z`
- size: `3345`
- prototype: `unsigned int __fastcall(struct _IUM_DUMP_REPORT_INFO *, wchar_t *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x1800029d0`
- `0x1800035e8`
- `0x180006134`
- `0x18000e318`
- `0x18000e630`
- `0x180011ef8`
- `0x180020e70`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020f05`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020f69`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020fcb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002102d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002108f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800210e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020f05`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020f69`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020fcb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002102d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002108f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800210e7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002114a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002114a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180020ee4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180020ee4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020f15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020f77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020fd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002103b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002109e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800210f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021b04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020f15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020f77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020fd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002103b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002109e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800210f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021b04`

## string_xrefs

- `0x180020edd`: `wer.dll`
- `0x180020fc1`: `WerReportCreate`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall IumCrashReport(const WCHAR *a1, wchar_t *a2)
{
  HMODULE Library; // rax
  HMODULE v4; // r15
  signed int LastError; // eax
  __int128 v6; // rdi
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  FARPROC v9; // rbx
  signed int v10; // eax
  FARPROC v11; // r14
  signed int v12; // eax
  FARPROC v13; // r13
  signed int v14; // eax
  signed int v15; // eax
  signed int v16; // eax
  unsigned __int16 *v17; // rsi
  __int64 v18; // rdx
  __int64 v19; // r10
  unsigned __int16 *v20; // rbx
  __int64 v21; // rax
  unsigned __int16 *v22; // rcx
  __int64 v23; // rdx
  char *v24; // r8
  unsigned __int16 v25; // r9
  char *v26; // rcx
  _QWORD *v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r9
  __int64 v30; // rax
  unsigned __int16 *v31; // rcx
  unsigned __int64 v32; // rax
  unsigned __int64 v33; // rax
  wchar_t *v34; // rcx
  __int64 v35; // r8
  wchar_t *v36; // rdx
  wchar_t v37; // r9
  wchar_t *v38; // rcx
  __int64 v39; // rax
  wchar_t *v40; // rcx
  __int64 v41; // rdx
  wchar_t *v42; // r8
  wchar_t v43; // r9
  wchar_t *v44; // rcx
  const wchar_t *v45; // rax
  __int64 v46; // rdx
  wchar_t *v47; // r8
  wchar_t v48; // cx
  wchar_t *v49; // rcx
  int v50; // eax
  unsigned __int16 v51; // dx
  int v52; // r8d
  unsigned __int16 v53; // r9
  int v54; // ecx
  unsigned __int16 *v55; // rbx
  int v56; // eax
  unsigned __int16 v57; // r12
  int v58; // r14d
  unsigned __int16 v59; // r15
  unsigned __int16 *v60; // r9
  __int64 v61; // rax
  unsigned __int16 *v62; // rcx
  __int64 v63; // rdx
  unsigned __int64 v64; // rax
  _QWORD *v65; // rcx
  __int64 v66; // rdx
  __int64 v67; // r9
  int v68; // eax
  const WCHAR *v69; // rbx
  const wchar_t *v70; // rdx
  int v71; // eax
  signed int v72; // eax
  __int64 v74; // [rsp+20h] [rbp-E0h]
  __int64 v75; // [rsp+28h] [rbp-D8h]
  __int64 v76; // [rsp+30h] [rbp-D0h]
  HMODULE v77; // [rsp+40h] [rbp-C0h]
  __int64 v78; // [rsp+48h] [rbp-B8h] BYREF
  void (*v79)(void); // [rsp+50h] [rbp-B0h]
  __int64 v80; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v81; // [rsp+60h] [rbp-A0h] BYREF
  const WCHAR *v82; // [rsp+68h] [rbp-98h]
  wchar_t *v83; // [rsp+70h] [rbp-90h]
  FARPROC ProcAddress; // [rsp+78h] [rbp-88h]
  FARPROC v85; // [rsp+80h] [rbp-80h]
  FARPROC v86; // [rsp+88h] [rbp-78h]
  __int128 v87; // [rsp+90h] [rbp-70h]
  __int128 v88; // [rsp+A0h] [rbp-60h]
  __int128 v89; // [rsp+B0h] [rbp-50h]
  int v90; // [rsp+C0h] [rbp-40h]
  _DWORD v91[100]; // [rsp+D0h] [rbp-30h] BYREF
  char v92; // [rsp+260h] [rbp+160h] BYREF
  char v93; // [rsp+360h] [rbp+260h] BYREF
  char v94; // [rsp+568h] [rbp+468h] BYREF
  wchar_t v95[64]; // [rsp+970h] [rbp+870h] BYREF
  wchar_t v96[264]; // [rsp+9F0h] [rbp+8F0h] BYREF

  v83 = a2;
  v82 = a1;
  v87 = 0;
  v88 = 0;
  v89 = 0;
  v90 = 0;
  memset_0(v91, 0, 0x8A0u);
  v81 = 0;
  Library = LoadLibraryExW(L"wer.dll", 0, 0);
  v4 = Library;
  v77 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "WerReportAddFile");
    if ( !ProcAddress )
    {
      LastError = GetLastError();
      LODWORD(v6) = LastError;
      if ( LastError > 0 )
        LODWORD(v6) = (unsigned __int16)LastError | 0x80070000;
      if ( (int)v6 >= 0 )
        LODWORD(v6) = -2147467259;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_51;
      v8 = 123;
LABEL_50:
      WPP_SF_d(v7[2], v8, &WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids, (unsigned int)v6);
LABEL_51:
      FreeLibrary(v4);
      return (unsigned int)v6;
    }
    v9 = GetProcAddress(v4, "WerReportCloseHandle");
    if ( !v9 )
    {
      v10 = GetLastError();
      LODWORD(v6) = v10;
      if ( v10 > 0 )
        LODWORD(v6) = (unsigned __int16)v10 | 0x80070000;
      if ( (int)v6 >= 0 )
        LODWORD(v6) = -2147467259;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_51;
      v8 = 124;
      goto LABEL_50;
    }
    v11 = GetProcAddress(v4, "WerReportCreate");
    if ( !v11 )
    {
      v12 = GetLastError();
      LODWORD(v6) = v12;
      if ( v12 > 0 )
        LODWORD(v6) = (unsigned __int16)v12 | 0x80070000;
      if ( (int)v6 >= 0 )
        LODWORD(v6) = -2147467259;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_51;
      v8 = 125;
      goto LABEL_50;
    }
    v13 = GetProcAddress(v4, "WerReportSetParameter");
    if ( !v13 )
    {
      v14 = GetLastError();
      LODWORD(v6) = v14;
      if ( v14 > 0 )
        LODWORD(v6) = (unsigned __int16)v14 | 0x80070000;
      if ( (int)v6 >= 0 )
        LODWORD(v6) = -2147467259;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_51;
      v8 = 126;
      goto LABEL_50;
    }
    v85 = GetProcAddress(v4, "WerReportSubmit");
    if ( !v85 )
    {
      v15 = GetLastError();
      LODWORD(v6) = v15;
      if ( v15 > 0 )
        LODWORD(v6) = (unsigned __int16)v15 | 0x80070000;
      if ( (int)v6 >= 0 )
        LODWORD(v6) = -2147467259;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_51;
      v8 = 127;
      goto LABEL_50;
    }
    v86 = GetProcAddress(v4, "WerpGetStoreLocation");
    if ( !v86 )
    {
      v16 = GetLastError();
      LODWORD(v6) = v16;
      if ( v16 > 0 )
        LODWORD(v6) = (unsigned __int16)v16 | 0x80070000;
      if ( (int)v6 >= 0 )
        LODWORD(v6) = -2147467259;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_51;
      v8 = 128;
      goto LABEL_50;
    }
    v79 = (void (*)(void))v9;
    v80 = 0;
    v17 = (unsigned __int16 *)(a1 + 12);
    v18 = 0x200000000801LL;
    v19 = 2147483646;
    if ( a1 == (const WCHAR *)-24LL )
    {
      v20 = 0;
    }
    else
    {
      v30 = -1;
      do
        ++v30;
      while ( v17[v30] );
      v31 = &v17[v30];
      while ( 1 )
      {
        v20 = v31;
        if ( v31 <= v17 )
          break;
        v32 = *--v31;
        LOWORD(v32) = v32 - 47;
        if ( (unsigned __int16)v32 <= 0x2Du )
        {
          if ( _bittest64(&v18, v32) )
            break;
        }
      }
      if ( v20 )
      {
        v33 = ((char *)v20 - (char *)a1 - 24) >> 1;
        if ( v33 <= 0x7FFFFFFE )
        {
          v34 = (wchar_t *)(a1 + 12);
          v35 = 260;
          v36 = v96;
          do
          {
            if ( !v33 )
              break;
            v37 = *v34;
            if ( !*v34 )
              break;
            ++v34;
            *v36++ = v37;
            --v33;
            --v35;
          }
          while ( v35 );
          v38 = v36 - 1;
          if ( v35 )
            v38 = v36;
          *v38 = 0;
LABEL_55:
          v91[0] = 2208;
          v21 = 2147483646;
          v22 = v20;
          v23 = 128;
          v24 = &v92;
          do
          {
            if ( !v21 )
              break;
            v25 = *v22;
            if ( !*v22 )
              break;
            ++v22;
            *(_WORD *)v24 = v25;
            v24 += 2;
            --v21;
            --v23;
          }
          while ( v23 );
          LODWORD(v6) = v23 == 0 ? 0x8007007A : 0;
          v26 = v24 - 2;
          if ( v23 )
            v26 = v24;
          *(_WORD *)v26 = 0;
          if ( !v23 )
          {
            v27 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v28 = 129;
LABEL_65:
              v29 = (unsigned int)v6;
LABEL_66:
              WPP_SF_d(v27[2], v28, &WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids, v29);
              goto LABEL_201;
            }
            goto LABEL_201;
          }
          v39 = 2147483646;
          v40 = v96;
          v41 = 260;
          v42 = (wchar_t *)&v93;
          do
          {
            if ( !v39 )
              break;
            v43 = *v40;
            if ( !*v40 )
              break;
            ++v40;
            *v42++ = v43;
            --v39;
            --v41;
          }
          while ( v41 );
          LODWORD(v6) = v41 == 0 ? 0x8007007A : 0;
          v44 = v42 - 1;
          if ( v41 )
            v44 = v42;
          *v44 = 0;
          if ( !v41 )
          {
            v27 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v28 = 130;
              goto LABEL_65;
            }
LABEL_201:
            if ( v80 )
              v79();
            goto LABEL_51;
          }
          v45 = L"This is a crash in a IUM trustlet process. Please send it to the application owner.";
          v46 = 512;
          v47 = (wchar_t *)&v94;
          do
          {
            if ( !v19 )
              break;
            v48 = *v45;
            if ( !*v45 )
              break;
            ++v45;
            *v47++ = v48;
            --v19;
            --v46;
          }
          while ( v46 );
          LODWORD(v6) = v46 == 0 ? 0x8007007A : 0;
          v49 = v47 - 1;
          if ( v46 )
            v49 = v47;
          *v49 = 0;
          if ( !v46 )
          {
            v27 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v28 = 131;
              goto LABEL_65;
            }
            goto LABEL_201;
          }
          v80 = 0;
          LODWORD(v6) = ((__int64 (__fastcall *)(const wchar_t *, _QWORD, _DWORD *, __int64 *))v11)(
                          L"IUMTrustletCrash",
                          0,
                          v91,
                          &v80);
          if ( (int)v6 < 0 )
            goto LABEL_201;
          v50 = ((__int64 (__fastcall *)(__int64, _QWORD, const wchar_t *, unsigned __int16 *))v13)(
                  v80,
                  0,
                  L"Application name",
                  v20);
          LODWORD(v6) = v50;
          if ( v50 < 0 )
          {
            v27 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_201;
            v28 = 132;
            goto LABEL_107;
          }
          v78 = 0;
          if ( (int)UtilGetFileInfo(a1 + 12) < 0 )
          {
            v53 = 0;
            LOWORD(v54) = 0;
            v51 = WORD1(v78);
            LOWORD(v52) = v78;
          }
          else
          {
            v51 = WORD4(v87);
            v52 = HIWORD(DWORD2(v87));
            v53 = WORD6(v87);
            v54 = HIWORD(HIDWORD(v87));
            WORD2(v78) = HIWORD(v87);
          }
          v50 = StringCchPrintfW(v95, 0x40u, L"%u.%u.%u.%u", (unsigned __int16)v52, v51, (unsigned __int16)v54, v53);
          v6 = (unsigned int)v50;
          if ( v50 < 0 )
          {
            v27 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_201;
            v28 = 133;
            goto LABEL_107;
          }
          v50 = ((__int64 (__fastcall *)(__int64, __int64, const wchar_t *, wchar_t *))v13)(
                  v80,
                  1,
                  L"Application version",
                  v95);
          LODWORD(v6) = v50;
          if ( v50 < 0 )
          {
            v27 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_201;
            v28 = 134;
            goto LABEL_107;
          }
          v50 = StringCchPrintfW(v95, 0x40u, L"%08x", *((unsigned int *)a1 + 2));
          LODWORD(v6) = v50;
          if ( v50 < 0 )
          {
            v27 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_201;
            v28 = 135;
            goto LABEL_107;
          }
          v50 = ((__int64 (__fastcall *)(__int64, __int64, const wchar_t *, wchar_t *))v13)(
                  v80,
                  2,
                  L"Application timestamp",
                  v95);
          LODWORD(v6) = v50;
          if ( v50 < 0 )
          {
            v27 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_201;
            v28 = 136;
LABEL_107:
            v29 = (unsigned int)v50;
            goto LABEL_66;
          }
          v78 = 0;
          v55 = (unsigned __int16 *)(a1 + 272);
          if ( a1[272] )
          {
            if ( (int)UtilGetFileInfo(a1 + 272) < 0 )
            {
              v57 = HIWORD(v78);
              LOWORD(v58) = WORD2(v78);
              v59 = WORD1(v78);
              WORD4(v6) = v78;
            }
            else
            {
              v59 = WORD4(v87);
              DWORD2(v6) = HIWORD(DWORD2(v87));
              v57 = WORD6(v87);
              v58 = HIWORD(HIDWORD(v87));
            }
            if ( v55 )
            {
              v61 = -1;
              do
                ++v61;
              while ( v55[v61] );
              v62 = &v55[v61];
              if ( v62 <= v55 )
              {
LABEL_141:
                v60 = v62;
              }
              else
              {
                v63 = 0x200000000801LL;
                while ( 1 )
                {
                  v60 = v62--;
                  v64 = *v62;
                  LOWORD(v64) = v64 - 47;
                  if ( (unsigned __int16)v64 <= 0x2Du )
                  {
                    if ( _bittest64(&v63, v64) )
                      break;
                  }
                  if ( v62 <= v55 )
                    goto LABEL_141;
                }
              }
            }
            else
            {
              v60 = 0;
            }
            v56 = ((__int64 (__fastcall *)(__int64, __int64, const wchar_t *, unsigned __int16 *))v13)(
                    v80,
                    3,
                    L"Module name",
                    v60);
          }
          else
          {
            v56 = ((__int64 (__fastcall *)(__int64, __int64, const wchar_t *, const wchar_t *))v13)(
                    v80,
                    3,
                    L"Module name",
                    L"UNKNOWN");
            v57 = HIWORD(v78);
            LOWORD(v58) = WORD2(v78);
            v59 = WORD1(v78);
            WORD4(v6) = v78;
          }
          LODWORD(v6) = v56;
          if ( v56 >= 0 )
          {
            LODWORD(v76) = v57;
            LODWORD(v75) = (unsigned __int16)v58;
            LODWORD(v74) = v59;
            v68 = StringCchPrintfW(v95, 0x40u, L"%u.%u.%u.%u", WORD4(v6), v74, v75, v76);
            LODWORD(v6) = v68;
            if ( v68 >= 0 )
            {
              v68 = ((__int64 (__fastcall *)(__int64, __int64, const wchar_t *, wchar_t *))v13)(
                      v80,
                      4,
                      L"Module version",
                      v95);
              LODWORD(v6) = v68;
              if ( v68 >= 0 )
              {
                v69 = v82;
                v68 = StringCchPrintfW(v95, 0x40u, L"%08x", *((unsigned int *)v82 + 3));
                LODWORD(v6) = v68;
                if ( v68 >= 0 )
                {
                  v68 = ((__int64 (__fastcall *)(__int64, __int64, const wchar_t *, wchar_t *))v13)(
                          v80,
                          5,
                          L"Module timestamp",
                          v95);
                  LODWORD(v6) = v68;
                  if ( v68 >= 0 )
                  {
                    v68 = StringCchPrintfW(v95, 0x40u, L"%08x", *((unsigned int *)v69 + 4));
                    LODWORD(v6) = v68;
                    if ( v68 >= 0 )
                    {
                      v68 = ((__int64 (__fastcall *)(__int64, __int64, const wchar_t *, wchar_t *))v13)(
                              v80,
                              6,
                              L"Exception code",
                              v95);
                      LODWORD(v6) = v68;
                      if ( v68 >= 0 )
                      {
                        v68 = StringCchPrintfW(v95, 0x40u, L"%016I64x", *(_QWORD *)v69);
                        LODWORD(v6) = v68;
                        if ( v68 >= 0 )
                        {
                          v68 = ((__int64 (__fastcall *)(__int64, __int64, const wchar_t *, wchar_t *))v13)(
                                  v80,
                                  7,
                                  L"Exception offset",
                                  v95);
                          LODWORD(v6) = v68;
                          if ( v68 >= 0 )
                          {
                            v68 = ((__int64 (__fastcall *)(__int64, wchar_t *, __int64))ProcAddress)(v80, v83, 2);
                            LODWORD(v6) = v68;
                            if ( v68 >= 0 )
                            {
                              v68 = ((__int64 (__fastcall *)(__int64, __int64, __int64, unsigned int *))v85)(
                                      v80,
                                      1,
                                      4,
                                      &v81);
                              LODWORD(v6) = v68;
                              if ( v68 >= 0 )
                              {
                                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                                {
                                  WPP_SF_d(
                                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                                    148,
                                    &WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids,
                                    v81);
                                }
                                if ( v81 == 1 )
                                {
                                  LODWORD(v78) = 260;
                                  v96[0] = 0;
                                  if ( !((unsigned int (__fastcall *)(__int64, wchar_t *, __int64 *))v86)(
                                          v80,
                                          v96,
                                          &v78) )
                                  {
                                    if ( v96[0] )
                                    {
                                      v71 = UtilFlushFiles(v96, v70);
                                      if ( v71 < 0
                                        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                                      {
                                        WPP_SF_d(
                                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                                          149,
                                          &WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids,
                                          (unsigned int)v71);
                                      }
                                    }
                                  }
                                }
                                LODWORD(v6) = 0;
                                goto LABEL_200;
                              }
                              v65 = WPP_GLOBAL_Control;
                              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                              {
LABEL_200:
                                v4 = v77;
                                goto LABEL_201;
                              }
                              v66 = 147;
                            }
                            else
                            {
                              v65 = WPP_GLOBAL_Control;
                              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                              {
                                goto LABEL_200;
                              }
                              v66 = 146;
                            }
                          }
                          else
                          {
                            v65 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                            {
                              goto LABEL_200;
                            }
                            v66 = 145;
                          }
                        }
                        else
                        {
                          v65 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                          {
                            goto LABEL_200;
                          }
                          v66 = 144;
                        }
                      }
                      else
                      {
                        v65 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                          goto LABEL_200;
                        v66 = 143;
                      }
                    }
                    else
                    {
                      v65 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                        goto LABEL_200;
                      v66 = 142;
                    }
                  }
                  else
                  {
                    v65 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                      goto LABEL_200;
                    v66 = 141;
                  }
                }
                else
                {
                  v65 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                    goto LABEL_200;
                  v66 = 140;
                }
              }
              else
              {
                v65 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                  goto LABEL_200;
                v66 = 139;
              }
            }
            else
            {
              v65 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                goto LABEL_200;
              v66 = 138;
            }
            v67 = (unsigned int)v68;
          }
          else
          {
            v65 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_200;
            v66 = 137;
            v67 = (unsigned int)v56;
          }
          WPP_SF_d(v65[2], v66, &WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids, v67);
          goto LABEL_200;
        }
      }
    }
    v96[0] = 0;
    goto LABEL_55;
  }
  v72 = GetLastError();
  LODWORD(v6) = v72;
  if ( v72 > 0 )
    LODWORD(v6) = (unsigned __int16)v72 | 0x80070000;
  if ( (int)v6 >= 0 )
    LODWORD(v6) = -2147467259;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      122,
      &WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids,
      (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180020e70  mov     [rsp-8+arg_10], rbx
0x180020e75  push    rbp
0x180020e76  push    rsi
0x180020e77  push    rdi
0x180020e78  push    r12
0x180020e7a  push    r13
0x180020e7c  push    r14
0x180020e7e  push    r15
0x180020e80  lea     rbp, [rsp-0B10h]
0x180020e88  sub     rsp, 0C10h
0x180020e8f  mov     rax, cs:__security_cookie
0x180020e96  xor     rax, rsp
0x180020e99  mov     [rbp+0B40h+var_40], rax
0x180020ea0  mov     [rsp+0C40h+var_BD0], rdx
0x180020ea5  mov     r12, rcx
0x180020ea8  mov     [rsp+0C40h+var_BD8], rcx
0x180020ead  xorps   xmm0, xmm0
0x180020eb0  xor     eax, eax
0x180020eb2  movups  [rbp+0B40h+var_BB0], xmm0
0x180020eb6  movups  [rbp+0B40h+var_BA0], xmm0
0x180020eba  movups  [rbp+0B40h+var_B90], xmm0
0x180020ebe  mov     [rbp+0B40h+var_B80], eax
0x180020ec1  xor     edx, edx; Val
0x180020ec3  mov     r8d, 8A0h; Size
0x180020ec9  lea     rcx, [rbp+0B40h+var_B70]; void *
0x180020ecd  call    memset_0
0x180020ed2  xor     edi, edi
0x180020ed4  mov     [rsp+0C40h+var_BE0], edi
0x180020ed8  xor     r8d, r8d; dwFlags
0x180020edb  xor     edx, edx; hFile
0x180020edd  lea     rcx, aWerDll_0; "wer.dll"
0x180020ee4  call    cs:__imp_LoadLibraryExW
0x180020eea  mov     r15, rax
0x180020eed  mov     [rsp+0C40h+var_C00], rax
0x180020ef2  test    rax, rax
0x180020ef5  jz      loc_180021B04
0x180020efb  lea     rdx, aWerreportaddfi; "WerReportAddFile"
0x180020f02  mov     rcx, rax; hModule
0x180020f05  call    cs:__imp_GetProcAddress
0x180020f0b  mov     [rsp+0C40h+var_BC8], rax
0x180020f10  test    rax, rax
0x180020f13  jnz     short loc_180020F5F
0x180020f15  call    cs:__imp_GetLastError
0x180020f1b  mov     edi, eax
0x180020f1d  test    eax, eax
0x180020f1f  jle     short loc_180020F2A
0x180020f21  movzx   edi, ax
0x180020f24  or      edi, 80070000h
0x180020f2a  mov     eax, 80004005h
0x180020f2f  test    edi, edi
0x180020f31  cmovns  edi, eax
0x180020f34  lea     rbx, WPP_GLOBAL_Control
0x180020f3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f42  cmp     rcx, rbx
0x180020f45  jz      loc_180021147
0x180020f4b  test    byte ptr [rcx+1Ch], 1
0x180020f4f  jz      loc_180021147
0x180020f55  mov     edx, 7Bh ; '{'
0x180020f5a  jmp     loc_180021133
0x180020f5f  lea     rdx, aWerreportclose; "WerReportCloseHandle"
0x180020f66  mov     rcx, r15; hModule
0x180020f69  call    cs:__imp_GetProcAddress
0x180020f6f  mov     rbx, rax
0x180020f72  test    rax, rax
0x180020f75  jnz     short loc_180020FC1
0x180020f77  call    cs:__imp_GetLastError
0x180020f7d  mov     edi, eax
0x180020f7f  test    eax, eax
0x180020f81  jle     short loc_180020F8C
0x180020f83  movzx   edi, ax
0x180020f86  or      edi, 80070000h
0x180020f8c  mov     eax, 80004005h
0x180020f91  test    edi, edi
0x180020f93  cmovns  edi, eax
0x180020f96  lea     rbx, WPP_GLOBAL_Control
0x180020f9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180020fa4  cmp     rcx, rbx
0x180020fa7  jz      loc_180021147
0x180020fad  test    byte ptr [rcx+1Ch], 1
0x180020fb1  jz      loc_180021147
0x180020fb7  mov     edx, 7Ch ; '|'
0x180020fbc  jmp     loc_180021133
0x180020fc1  lea     rdx, aWerreportcreat; "WerReportCreate"
0x180020fc8  mov     rcx, r15; hModule
0x180020fcb  call    cs:__imp_GetProcAddress
0x180020fd1  mov     r14, rax
0x180020fd4  test    rax, rax
0x180020fd7  jnz     short loc_180021023
0x180020fd9  call    cs:__imp_GetLastError
0x180020fdf  mov     edi, eax
0x180020fe1  test    eax, eax
0x180020fe3  jle     short loc_180020FEE
0x180020fe5  movzx   edi, ax
0x180020fe8  or      edi, 80070000h
0x180020fee  mov     eax, 80004005h
0x180020ff3  test    edi, edi
0x180020ff5  cmovns  edi, eax
0x180020ff8  lea     rbx, WPP_GLOBAL_Control
0x180020fff  mov     rcx, cs:WPP_GLOBAL_Control
0x180021006  cmp     rcx, rbx
0x180021009  jz      loc_180021147
0x18002100f  test    byte ptr [rcx+1Ch], 1
0x180021013  jz      loc_180021147
0x180021019  mov     edx, 7Dh ; '}'
0x18002101e  jmp     loc_180021133
0x180021023  lea     rdx, aWerreportsetpa; "WerReportSetParameter"
0x18002102a  mov     rcx, r15; hModule
0x18002102d  call    cs:__imp_GetProcAddress
0x180021033  mov     r13, rax
0x180021036  test    rax, rax
0x180021039  jnz     short loc_180021085
0x18002103b  call    cs:__imp_GetLastError
0x180021041  mov     edi, eax
0x180021043  test    eax, eax
0x180021045  jle     short loc_180021050
0x180021047  movzx   edi, ax
0x18002104a  or      edi, 80070000h
0x180021050  mov     eax, 80004005h
0x180021055  test    edi, edi
0x180021057  cmovns  edi, eax
0x18002105a  lea     rbx, WPP_GLOBAL_Control
0x180021061  mov     rcx, cs:WPP_GLOBAL_Control
0x180021068  cmp     rcx, rbx
0x18002106b  jz      loc_180021147
0x180021071  test    byte ptr [rcx+1Ch], 1
0x180021075  jz      loc_180021147
0x18002107b  mov     edx, 7Eh ; '~'
0x180021080  jmp     loc_180021133
0x180021085  lea     rdx, aWerreportsubmi; "WerReportSubmit"
0x18002108c  mov     rcx, r15; hModule
0x18002108f  call    cs:__imp_GetProcAddress
0x180021095  mov     [rbp+0B40h+var_BC0], rax
0x180021099  test    rax, rax
0x18002109c  jnz     short loc_1800210DD
0x18002109e  call    cs:__imp_GetLastError
0x1800210a4  mov     edi, eax
0x1800210a6  test    eax, eax
0x1800210a8  jle     short loc_1800210B3
0x1800210aa  movzx   edi, ax
0x1800210ad  or      edi, 80070000h
0x1800210b3  mov     eax, 80004005h
0x1800210b8  test    edi, edi
0x1800210ba  cmovns  edi, eax
0x1800210bd  lea     rbx, WPP_GLOBAL_Control
0x1800210c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800210cb  cmp     rcx, rbx
0x1800210ce  jz      short loc_180021147
0x1800210d0  test    byte ptr [rcx+1Ch], 1
0x1800210d4  jz      short loc_180021147
0x1800210d6  mov     edx, 7Fh
0x1800210db  jmp     short loc_180021133
0x1800210dd  lea     rdx, aWerpgetstorelo; "WerpGetStoreLocation"
0x1800210e4  mov     rcx, r15; hModule
0x1800210e7  call    cs:__imp_GetProcAddress
0x1800210ed  mov     [rbp+0B40h+var_BB8], rax
0x1800210f1  test    rax, rax
0x1800210f4  jnz     short loc_180021155
0x1800210f6  call    cs:__imp_GetLastError
0x1800210fc  mov     edi, eax
0x1800210fe  test    eax, eax
0x180021100  jle     short loc_18002110B
0x180021102  movzx   edi, ax
0x180021105  or      edi, 80070000h
0x18002110b  mov     eax, 80004005h
0x180021110  test    edi, edi
0x180021112  cmovns  edi, eax
0x180021115  lea     rbx, WPP_GLOBAL_Control
0x18002111c  mov     rcx, cs:WPP_GLOBAL_Control
0x180021123  cmp     rcx, rbx
0x180021126  jz      short loc_180021147
0x180021128  test    byte ptr [rcx+1Ch], 1
0x18002112c  jz      short loc_180021147
0x18002112e  mov     edx, 80h
0x180021133  mov     r9d, edi
0x180021136  lea     r8, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids
0x18002113d  mov     rcx, [rcx+10h]
0x180021141  call    WPP_SF_d
0x180021146  nop
0x180021147  mov     rcx, r15; hLibModule
0x18002114a  call    cs:__imp_FreeLibrary
0x180021150  jmp     loc_180021B55
0x180021155  mov     [rsp+0C40h+var_BF0], rbx
0x18002115a  mov     [rsp+0C40h+var_BE8], rdi
0x18002115f  lea     rsi, [r12+18h]
0x180021164  mov     rdx, 200000000801h
0x18002116e  mov     r10d, 7FFFFFFEh
0x180021174  test    rsi, rsi
0x180021177  jnz     loc_18002122B
0x18002117d  mov     rbx, rdi
0x180021180  mov     [rbp+0B40h+var_250], di
0x180021187  mov     [rbp+0B40h+var_B70], 8A0h
0x18002118e  mov     rax, r10
0x180021191  mov     rcx, rbx
0x180021194  mov     edx, 80h
0x180021199  lea     r8, [rbp+0B40h+var_9E0]
0x1800211a0  test    rax, rax
0x1800211a3  jz      short loc_1800211C4
0x1800211a5  movzx   r9d, word ptr [rcx]
0x1800211a9  test    r9w, r9w
0x1800211ad  jz      short loc_1800211C4
0x1800211af  add     rcx, 2
0x1800211b3  mov     [r8], r9w
0x1800211b7  add     r8, 2
0x1800211bb  dec     rax
0x1800211be  sub     rdx, 1
0x1800211c2  jnz     short loc_1800211A0
0x1800211c4  mov     rax, rdx
0x1800211c7  neg     rax
0x1800211ca  sbb     edi, edi
0x1800211cc  not     edi
0x1800211ce  mov     r11d, 8007007Ah
0x1800211d4  and     edi, r11d
0x1800211d7  lea     rcx, [r8-2]
0x1800211db  xor     eax, eax
0x1800211dd  test    rdx, rdx
0x1800211e0  cmovnz  rcx, r8
0x1800211e4  mov     [rcx], ax
0x1800211e7  jnz     loc_1800212C3
0x1800211ed  lea     rbx, WPP_GLOBAL_Control
0x1800211f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800211fb  cmp     rcx, rbx
0x1800211fe  jz      loc_180021AEA
0x180021204  test    byte ptr [rcx+1Ch], 1
0x180021208  jz      loc_180021AEA
0x18002120e  mov     edx, 81h
0x180021213  mov     r9d, edi
0x180021216  lea     r8, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids
0x18002121d  mov     rcx, [rcx+10h]
0x180021221  call    WPP_SF_d
0x180021226  jmp     loc_180021AEA
0x18002122b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002122f  inc     rax
0x180021232  cmp     [rsi+rax*2], di
0x180021236  jnz     short loc_18002122F
0x180021238  lea     rcx, [rsi+rax*2]
0x18002123c  jmp     short loc_180021255
0x18002123e  sub     rcx, 2
0x180021242  movzx   eax, word ptr [rcx]
0x180021245  sub     ax, 2Fh ; '/'
0x180021249  cmp     ax, 2Dh ; '-'
0x18002124d  ja      short loc_180021255
0x18002124f  bt      rdx, rax
0x180021253  jb      short loc_18002125D
0x180021255  mov     rbx, rcx
0x180021258  cmp     rcx, rsi
0x18002125b  ja      short loc_18002123E
0x18002125d  test    rbx, rbx
0x180021260  jz      loc_180021180
0x180021266  mov     rax, rbx
0x180021269  sub     rax, r12
0x18002126c  sub     rax, 18h
0x180021270  sar     rax, 1
0x180021273  cmp     rax, r10
0x180021276  ja      loc_180021180
0x18002127c  mov     rcx, rsi
0x18002127f  mov     r8d, 104h
0x180021285  lea     rdx, [rbp+0B40h+var_250]
0x18002128c  test    rax, rax
0x18002128f  jz      short loc_1800212B0
0x180021291  movzx   r9d, word ptr [rcx]
0x180021295  test    r9w, r9w
0x180021299  jz      short loc_1800212B0
0x18002129b  add     rcx, 2
0x18002129f  mov     [rdx], r9w
0x1800212a3  add     rdx, 2
0x1800212a7  dec     rax
0x1800212aa  sub     r8, 1
0x1800212ae  jnz     short loc_18002128C
0x1800212b0  lea     rcx, [rdx-2]
0x1800212b4  test    r8, r8
0x1800212b7  cmovnz  rcx, rdx
0x1800212bb  mov     [rcx], di
0x1800212be  jmp     loc_180021187
0x1800212c3  mov     rax, r10
0x1800212c6  lea     rcx, [rbp+0B40h+var_250]
0x1800212cd  mov     edx, 104h
0x1800212d2  lea     r8, [rbp+0B40h+var_8E0]
0x1800212d9  test    rax, rax
0x1800212dc  jz      short loc_1800212FD
0x1800212de  movzx   r9d, word ptr [rcx]
0x1800212e2  test    r9w, r9w
0x1800212e6  jz      short loc_1800212FD
0x1800212e8  add     rcx, 2
0x1800212ec  mov     [r8], r9w
0x1800212f0  add     r8, 2
0x1800212f4  dec     rax
0x1800212f7  sub     rdx, 1
0x1800212fb  jnz     short loc_1800212D9
0x1800212fd  mov     rax, rdx
0x180021300  neg     rax
0x180021303  sbb     edi, edi
0x180021305  not     edi
0x180021307  and     edi, r11d
0x18002130a  lea     rcx, [r8-2]
0x18002130e  xor     eax, eax
0x180021310  test    rdx, rdx
0x180021313  cmovnz  rcx, r8
0x180021317  mov     [rcx], ax
0x18002131a  jnz     short loc_180021347
0x18002131c  lea     rbx, WPP_GLOBAL_Control
  ... truncated ...
```
