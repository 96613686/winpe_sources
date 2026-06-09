# PrintUserDataEx

- ea: `0x14001232c`
- end: `0x1400130c9`
- name: `PrintUserDataEx`
- size: `3485`
- prototype: `__int64 __fastcall(struct _iobuf *, char, unsigned __int8 *, __int64, char, __int64, __int64)`
- caller_count: `7`
- callee_count: `16`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140011c74`
- `0x1400281f0`
- `0x14002af78`
- `0x14002b158`
- `0x14002b2d4`
- `0x14002cd10`
- `0x14002d240`

## callees

- `0x140011d94`
- `0x140011ff8`
- `0x1400120f4`
- `0x140012158`
- `0x14001232c`
- `0x1400130d0`
- `0x140013a04`
- `0x140013b60`
- `0x140016360`
- `0x1400164c4`
- `0x14001e7a8`
- `0x140032488`
- `0x1400400be`
- `0x1400400d6`
- `0x140040130`
- `0x140041010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140013063`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140013096`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140013063`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140013096`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013055`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013088`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013055`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013088`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140012aad`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x14001300a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140012aad`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x14001300a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013014`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013014`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1400126e9`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1400126e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012779`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012779`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140012754`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140012754`
- `WS2_32!WSAAddressToStringW` at `0x140012ee8`
- `WS2_32!WSAAddressToStringW` at `0x140012ee8`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x140012e01`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x140012e01`

## pseudocode

```c
__int64 __fastcall PrintUserDataEx(
        struct _iobuf *a1,
        char a2,
        unsigned __int8 *a3,
        __int64 a4,
        char a5,
        __int64 a6,
        __int64 a7)
{
  size_t v7; // r10
  unsigned __int8 *v8; // rbx
  unsigned __int16 *v10; // r14
  CHAR *v11; // r15
  bool v12; // zf
  DWORD LastError; // r13d
  int v15; // r8d
  unsigned int v16; // esi
  unsigned __int16 v17; // cx
  unsigned int v18; // esi
  unsigned int v19; // esi
  unsigned int v20; // esi
  unsigned int v21; // esi
  unsigned int v22; // esi
  unsigned int v23; // ebx
  __int64 v24; // r8
  wchar_t *v25; // rdx
  struct _iobuf *v26; // rcx
  unsigned int v27; // ebx
  unsigned int v28; // ebx
  double v29; // xmm2_8
  sockaddr *p_saAddress; // r8
  wchar_t *v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rax
  FILETIME *p_FileTime; // rdx
  __int64 v35; // r14
  wchar_t *v36; // rcx
  size_t v37; // rsi
  unsigned __int8 v38; // dl
  __int16 v39; // bx
  _BYTE *v40; // rax
  CHAR v41; // cl
  __int64 cchWideChar; // rsi
  int v43; // edx
  unsigned __int8 v44; // r8
  size_t v45; // rsi
  int v46; // edx
  __int64 v47; // r8
  __int16 v48; // bx
  unsigned __int16 *v49; // rcx
  unsigned __int16 v50; // ax
  unsigned __int16 *v51; // rcx
  unsigned __int16 v52; // dx
  size_t v53; // rsi
  unsigned __int8 *v54; // rdx
  unsigned __int16 v55; // dx
  size_t v56; // rsi
  unsigned __int8 *v57; // rdx
  int v58; // edx
  unsigned __int8 *v59; // r8
  unsigned __int64 v60; // rdx
  __int64 (__fastcall *v61)(struct _SYSTEMTIME *, WCHAR *); // rax
  _WORD *v62; // rax
  __int64 v63; // rcx
  const wchar_t *v64; // rdx
  WCHAR *v65; // rax
  WCHAR *v66; // rcx
  struct _iobuf *v67; // rcx
  unsigned __int64 v68; // rsi
  INT v69; // eax
  __int64 v70; // r9
  __int64 v71; // r8
  __int64 v72; // rsi
  int v73; // edx
  HANDLE ProcessHeap; // rax
  HANDLE v75; // rax
  LPWSTR lpWideCharStr; // [rsp+20h] [rbp-E0h]
  DWORD dwAddressStringLength; // [rsp+54h] [rbp-ACh] BYREF
  FILETIME FileTime; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR v80; // [rsp+60h] [rbp-A0h] BYREF
  size_t Size; // [rsp+68h] [rbp-98h]
  LPCCH lpMultiByteStr; // [rsp+70h] [rbp-90h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+78h] [rbp-88h] BYREF
  sockaddr saAddress; // [rsp+90h] [rbp-70h] BYREF
  WCHAR szAddressString[256]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v86[1024]; // [rsp+390h] [rbp+290h] BYREF
  _BYTE v87[2048]; // [rsp+790h] [rbp+690h] BYREF

  v7 = (unsigned int)a4;
  v8 = a3;
  LOBYTE(a4) = a2;
  LODWORD(Size) = v7;
  v10 = 0;
  v80 = 0;
  v11 = 0;
  lpMultiByteStr = 0;
  v12 = (*(_BYTE *)a6 & 1) == 0;
  FileTime = 0;
  *(_QWORD *)&SystemTime.wYear = 0;
  if ( !v12 )
    return 50;
  if ( !a3 )
    return 13;
  LastError = 0;
  v15 = 64;
  if ( (a5 & 0x40) == 0 )
  {
    if ( (a5 & 0x20) != 0 )
    {
      v15 = 32;
    }
    else if ( *((_DWORD *)g_TraceContext + 2170) )
    {
      v15 = *((_DWORD *)g_TraceContext + 2170);
    }
  }
  v16 = *(unsigned __int16 *)(a6 + 8);
  v17 = *(_WORD *)(a6 + 10);
  dwAddressStringLength = v17;
  if ( v16 > 0x12C )
  {
    if ( v16 > 0x132 )
    {
      if ( v16 != 307 )
      {
        if ( v16 == 308 )
          goto LABEL_214;
        if ( v16 != 309 )
        {
          if ( v16 != 310 )
            return 50;
          if ( *(_DWORD *)v8 )
          {
            v12 = v15 == 64;
            v59 = v8 + 16;
            if ( !v12 )
              v59 = v8 + 8;
            PrintWBEMSid(a1, v16 - 309, v59, a4);
            return LastError;
          }
          v36 = (wchar_t *)L"0";
          goto LABEL_101;
        }
LABEL_82:
        v35 = 256;
        dwAddressStringLength = 256;
        if ( (_WORD)v16 == 309 )
        {
          LODWORD(v7) = *(_DWORD *)v8;
          v8 += 4;
        }
        else
        {
          if ( (_WORD)v16 != 25 )
          {
            if ( v17 == 24 )
              goto LABEL_197;
            goto LABEL_209;
          }
          LODWORD(v7) = *(unsigned __int16 *)v8;
          v8 += 2;
        }
        LODWORD(Size) = v7;
        if ( v17 == 24 )
        {
          if ( (_DWORD)v7 != 16 )
          {
LABEL_195:
            v60 = (unsigned int)v7;
LABEL_207:
            v67 = a1;
LABEL_208:
            PrintBinaryHex(v67, v60, v8, a4);
            return LastError;
          }
LABEL_197:
          SystemTime = *(struct _SYSTEMTIME *)v8;
          v61 = (__int64 (__fastcall *)(struct _SYSTEMTIME *, WCHAR *))DecodePointer(EtwpIpv6ToStringW);
          if ( XPorHigher && v61 )
          {
            v62 = (_WORD *)v61(&SystemTime, szAddressString);
            p_saAddress = (sockaddr *)szAddressString;
            *v62 = 0;
            goto LABEL_67;
          }
          v63 = 2147483646;
          v64 = L"Undecodable IP Address";
          v65 = szAddressString;
          do
          {
            if ( !v63 )
              break;
            if ( !*v64 )
              break;
            *v65++ = *v64++;
            --v63;
            --v35;
          }
          while ( v35 );
          LOBYTE(a4) = a2;
          v66 = v65 - 1;
          v60 = 16;
          if ( v35 )
            v66 = v65;
          *v66 = 0;
          goto LABEL_207;
        }
LABEL_209:
        if ( v17 == 25 && (unsigned int)v7 <= 0x80 )
        {
          memset_0(&saAddress, 0, 0x80u);
          v68 = (unsigned int)Size;
          memcpy_0(&saAddress, v8, (unsigned int)Size);
          v69 = WSAAddressToStringW(&saAddress, Size, 0, szAddressString, &dwAddressStringLength);
          v67 = a1;
          if ( v69 != -1 )
          {
            TracerptFWPrintf(a1, L"%ws", szAddressString, v70);
            return LastError;
          }
          LOBYTE(a4) = a2;
          v60 = v68;
          goto LABEL_208;
        }
        goto LABEL_195;
      }
      v56 = v7;
      LastError = SetString(&lpMultiByteStr, &SystemTime, v86, v7 + 1, 0);
      if ( LastError )
        goto LABEL_236;
      v11 = (CHAR *)lpMultiByteStr;
      if ( !lpMultiByteStr )
        return LastError;
      v57 = v8;
LABEL_224:
      memcpy_0(v11, v57, v56);
      v11[v56] = 0;
      if ( a7 )
      {
        v72 = 2 * v56 + 2;
        LastError = SetString(&v80, &FileTime, v87, v72, 1);
        if ( LastError )
          goto LABEL_235;
        v10 = v80;
        if ( !v80 )
          goto LABEL_237;
        if ( !MultiByteToWideChar(0, 0, v11, -1, v80, v72) )
          goto LABEL_228;
        if ( (unsigned __int8)PrintEventMap((int)a1, v73, a7, 0, v10) )
          goto LABEL_232;
      }
      v44 = 0;
      goto LABEL_231;
    }
    if ( v16 == 306 )
    {
      v53 = v7;
      LastError = SetString(&v80, &FileTime, v87, v7 + 2, 1);
      if ( LastError )
        goto LABEL_235;
      v10 = v80;
      if ( !v80 )
        return LastError;
      v54 = v8;
      goto LABEL_177;
    }
    if ( v16 != 301 )
    {
      if ( v16 == 302 )
        goto LABEL_162;
      if ( v16 != 303 )
      {
        if ( v16 != 304 )
        {
LABEL_118:
          v37 = v7;
          LastError = SetString(&lpMultiByteStr, &SystemTime, v86, v7 + 1, 0);
          if ( !LastError )
          {
            v11 = (CHAR *)lpMultiByteStr;
            if ( !lpMultiByteStr )
              return LastError;
            memcpy_0((void *)lpMultiByteStr, v8, v37);
            v39 = dwAddressStringLength;
            v11[v37] = 0;
            if ( v39 == 300 )
            {
              v40 = v11;
              if ( v11 )
              {
                v41 = *v11;
                v38 = LastError + 44;
                if ( *v11 )
                {
                  while ( v41 != (_BYTE)LastError + 9 && v41 != v38 )
                  {
                    if ( v41 == (_BYTE)LastError + 10 )
                    {
                      *v40 = v38;
                    }
                    else if ( v41 == (_BYTE)LastError + 13 )
                    {
                      break;
                    }
LABEL_129:
                    v41 = *++v40;
                    if ( !*v40 )
                      goto LABEL_134;
                  }
                  *v40 = 32;
                  goto LABEL_129;
                }
LABEL_134:
                while ( v11 < --v40 && (*v40 == 32 || *v40 == v38) )
                  *v40 = 0;
              }
            }
            if ( !a7 )
              goto LABEL_140;
            cchWideChar = 2 * v37 + 2;
            LastError = SetString(&v80, &FileTime, v87, cchWideChar, 1);
            if ( !LastError )
            {
              v10 = v80;
              if ( v80 )
              {
                if ( MultiByteToWideChar(0, 0, v11, -1, v80, cchWideChar) )
                {
                  if ( !(unsigned __int8)PrintEventMap((int)a1, v43, a7, 0, v10) )
                  {
LABEL_140:
                    v44 = v39 == 28;
LABEL_231:
                    PrintAnsiString(a1, v38, v44, v11);
                  }
LABEL_232:
                  if ( v10 && v10 != (unsigned __int16 *)v87 )
                  {
                    ProcessHeap = GetProcessHeap();
                    HeapFree(ProcessHeap, 0, v10);
                  }
                  goto LABEL_237;
                }
LABEL_228:
                LastError = GetLastError();
                goto LABEL_232;
              }
LABEL_237:
              if ( v11 && v11 != v86 )
              {
                v75 = GetProcessHeap();
                HeapFree(v75, 0, v11);
              }
              return LastError;
            }
LABEL_235:
            v10 = v80;
            goto LABEL_232;
          }
LABEL_236:
          v11 = (CHAR *)lpMultiByteStr;
          goto LABEL_237;
        }
        goto LABEL_141;
      }
    }
LABEL_168:
    if ( (_WORD)v16 == 303 )
      v55 = (*v8 << 8) + v8[1];
    else
      v55 = *(_WORD *)v8;
    v56 = v55;
    LastError = SetString(&lpMultiByteStr, &SystemTime, v86, v55 + 1LL, 0);
    if ( LastError )
      goto LABEL_236;
    v11 = (CHAR *)lpMultiByteStr;
    if ( !lpMultiByteStr )
      return LastError;
    v57 = v8 + 2;
    goto LABEL_224;
  }
  if ( v16 == 300 )
  {
LABEL_162:
    if ( (_WORD)v16 == 302 )
      v52 = (*v8 << 8) + v8[1];
    else
      v52 = *(_WORD *)v8;
    v53 = v52;
    LastError = SetString(&v80, &FileTime, v87, v52 + 2LL, 1);
    if ( LastError )
      goto LABEL_235;
    v10 = v80;
    if ( !v80 )
      return LastError;
    v54 = v8 + 2;
LABEL_177:
    memcpy_0(v10, v54, v53);
    v10[v53 >> 1] = 0;
    if ( a7 && (unsigned __int8)PrintEventMap((int)a1, v58, a7, 0, v10) )
      goto LABEL_232;
    v47 = 0;
    goto LABEL_180;
  }
  if ( v16 > 0xD )
  {
    if ( v16 <= 0x13 )
    {
      if ( v16 == 19 )
      {
        FileTime = 0;
        if ( ConvertSidToStringSidW(v8, (LPWSTR *)&FileTime) )
        {
          PrintWString(a1, 1, 0, *(unsigned __int16 **)&FileTime);
          LocalFree(*(HLOCAL *)&FileTime);
        }
        return LastError;
      }
      if ( v16 != 14 )
      {
        if ( v16 != 15 )
        {
          if ( v16 != 16 )
          {
            if ( v16 == 17 )
            {
              FileTime = *(FILETIME *)v8;
              SystemTime = 0;
              if ( !FileTimeToSystemTime(&FileTime, &SystemTime) || SystemTime.wMonth > 0xCu )
              {
                TracerptFWPrintf(a1, (wchar_t *)L"%u:%u", FileTime.dwLowDateTime, FileTime.dwHighDateTime);
                return LastError;
              }
              p_FileTime = &FileTime;
            }
            else
            {
              v32 = *(_QWORD *)v8;
              v33 = *(_QWORD *)v8 >> 16;
              SystemTime = *(struct _SYSTEMTIME *)v8;
              if ( (unsigned __int16)v33 > 0xCu )
              {
                TracerptFWPrintf(
                  a1,
                  (wchar_t *)L"%u:%u:%u:%u:%u:%u:%u:%u",
                  (unsigned __int16)v32,
                  SystemTime.wMonth,
                  SystemTime.wDayOfWeek,
                  SystemTime.wDay,
                  SystemTime.wHour,
                  SystemTime.wMinute,
                  SystemTime.wSecond,
                  SystemTime.wMilliseconds);
                return LastError;
              }
              p_FileTime = 0;
            }
            FormatDateTimeString(&SystemTime, (const union _LARGE_INTEGER *)p_FileTime, &saAddress.sa_family, a4, 1);
            p_saAddress = &saAddress;
            goto LABEL_67;
          }
LABEL_214:
          if ( v15 != 32 )
          {
            v71 = *(_QWORD *)v8;
            if ( a2 )
              TracerptFWPrintf(a1, L"0x%I64X", v71, a4);
            else
              TracerptFWPrintf(a1, L"%I64X", v71, a4);
            return LastError;
          }
          v24 = *(unsigned int *)v8;
          v25 = L"0x%X";
          if ( !(_BYTE)a4 )
            v25 = L"%X";
          goto LABEL_28;
        }
        SystemTime = *(struct _SYSTEMTIME *)v8;
        p_saAddress = (sockaddr *)CpdiGuidToString(&saAddress.sa_family, 0x80u, (struct _GUID *)&SystemTime);
LABEL_67:
        v31 = L"%ws";
        goto LABEL_57;
      }
      goto LABEL_81;
    }
    if ( v16 == 20 )
    {
      v17 = dwAddressStringLength;
      goto LABEL_93;
    }
    if ( v16 == 21 )
      goto LABEL_84;
    if ( v16 != 22 )
    {
      if ( v16 != 23 )
      {
        if ( v16 != 25 )
          return 50;
LABEL_81:
        v17 = dwAddressStringLength;
        goto LABEL_82;
      }
      goto LABEL_168;
    }
    goto LABEL_162;
  }
  if ( v16 == 13 )
  {
LABEL_93:
    if ( (_WORD)v16 == 20 )
    {
      v17 = 18;
      dwAddressStringLength = 18;
    }
    v28 = *(_DWORD *)v8;
    if ( a7 )
    {
      if ( (unsigned __int8)PrintEventMap((int)a1, 19, a7, v28, 0) )
        return LastError;
      v17 = dwAddressStringLength;
      LOBYTE(a4) = a2;
    }
    if ( (_WORD)v16 != 13 )
    {
      switch ( v17 )
      {
        case 0x17u:
          LODWORD(lpWideCharStr) = BYTE2(v28);
          TracerptFWPrintf(a1, (wchar_t *)L"%d.%d.%d.%d", (unsigned __int8)v28, BYTE1(v28), lpWideCharStr, HIBYTE(v28));
          return LastError;
        case 0x1Bu:
          v25 = L"%lu";
          v24 = dword_1400820F8 * v28;
          goto LABEL_28;
        case 0x12u:
        case 0x1Du:
          if ( (_BYTE)a4 )
            TracerptFWPrintf(a1, L"0x%X", v28, a4);
          else
            TracerptFWPrintf(a1, L"%X", v28, a4);
          return LastError;
      }
      goto LABEL_46;
    }
    v36 = (wchar_t *)L"false";
    if ( v28 )
      v36 = (wchar_t *)L"true";
LABEL_101:
    TracerptFPutws(v36, a1);
    return LastError;
  }
  if ( v16 > 7 )
  {
    if ( v16 != 8 )
    {
      if ( v16 != 9 )
      {
        if ( v16 != 10 )
        {
          if ( v16 == 11 )
            v29 = *(float *)v8;
          else
            v29 = *(double *)v8;
          TracerptFWPrintf(a1, (wchar_t *)L"%f", v29, a4);
          return LastError;
        }
LABEL_84:
        p_saAddress = *(sockaddr **)v8;
        *(_QWORD *)&SystemTime.wYear = 0;
        if ( (_WORD)v16 != 21 )
        {
          if ( (_WORD)dwAddressStringLength == 27 )
          {
            WmiTimeFromRawTime((unsigned __int64 *)&SystemTime.wYear, (unsigned __int64)p_saAddress);
            p_saAddress = *(sockaddr **)&SystemTime.wYear;
LABEL_87:
            v31 = (wchar_t *)L"%I64u";
            goto LABEL_57;
          }
          if ( (_WORD)dwAddressStringLength != 19 )
            goto LABEL_87;
        }
        v31 = L"0x%I64X";
        if ( !(_BYTE)a4 )
          v31 = L"%I64X";
        goto LABEL_57;
      }
      p_saAddress = *(sockaddr **)v8;
      v31 = (wchar_t *)L"%I64d";
LABEL_57:
      TracerptFWPrintf(a1, v31, p_saAddress, a4);
      return LastError;
    }
    v17 = dwAddressStringLength;
    goto LABEL_93;
  }
  if ( v16 == 7 )
  {
    v27 = *(_DWORD *)v8;
LABEL_36:
    if ( a7 && (unsigned __int8)PrintEventMap((int)a1, 19, a7, v27, 0) )
      return LastError;
    v24 = v27;
    v25 = L"%d";
    goto LABEL_28;
  }
  v18 = v16 - 1;
  if ( !v18 )
  {
LABEL_141:
    v45 = v7;
    LastError = SetString(&v80, &FileTime, v87, v7 + 2, 1);
    if ( LastError )
      goto LABEL_235;
    v10 = v80;
    if ( !v80 )
      return LastError;
    memcpy_0(v80, v8, v45);
    v48 = dwAddressStringLength;
    v10[v45 >> 1] = 0;
    if ( v48 == 300 )
    {
      v49 = v10;
      if ( v10 )
      {
        v50 = *v10;
        v46 = 44;
        v47 = (__int64)v10;
        if ( *v10 )
        {
          while ( v50 != 9 && v50 != 44 )
          {
            if ( v50 == 10 )
            {
              *v49 = 44;
            }
            else if ( v50 == 13 )
            {
              break;
            }
LABEL_152:
            v50 = *++v49;
            if ( !*v49 )
            {
              v48 = dwAddressStringLength;
              goto LABEL_154;
            }
          }
          *v49 = 32;
          goto LABEL_152;
        }
LABEL_154:
        v51 = v49 - 1;
        if ( v10 < v51 )
        {
          do
          {
            if ( *v51 != 32 && *v51 != 44 )
              break;
            *v51-- = 0;
          }
          while ( v10 < v51 );
          v48 = dwAddressStringLength;
        }
      }
    }
    if ( a7 && (unsigned __int8)PrintEventMap((int)a1, v46, a7, 0, v10) )
      goto LABEL_232;
    LOBYTE(v47) = v48 == 28;
LABEL_180:
    PrintWString(a1, 1, v47, v10);
    goto LABEL_232;
  }
  v19 = v18 - 1;
  if ( !v19 )
    goto LABEL_118;
  v20 = v19 - 1;
  if ( !v20 )
  {
    v27 = (char)*v8;
    goto LABEL_36;
  }
  v21 = v20 - 1;
  if ( !v21 )
  {
    v28 = *v8;
    if ( a7 )
    {
      if ( (unsigned __int8)PrintEventMap((int)a1, 19, a7, v28, 0) )
        return LastError;
      v17 = dwAddressStringLength;
      LOBYTE(a4) = a2;
    }
    if ( v17 == 16 )
    {
      v25 = L"0x%X";
      v24 = v28;
      if ( !(_BYTE)a4 )
        v25 = L"%X";
      goto LABEL_28;
    }
LABEL_46:
    v24 = v28;
LABEL_27:
    v25 = (wchar_t *)L"%u";
LABEL_28:
    v26 = a1;
LABEL_29:
    TracerptFWPrintf(v26, v25, v24, a4);
    return LastError;
  }
  v22 = v21 - 1;
  if ( !v22 )
  {
    v27 = *(__int16 *)v8;
    goto LABEL_36;
  }
  if ( v22 != 1 )
    return 50;
  v23 = *(unsigned __int16 *)v8;
  if ( !a7 )
  {
LABEL_25:
    if ( v17 != 22 )
    {
      v24 = v23;
      v12 = v17 == 17;
      v26 = a1;
      if ( !v12 )
      {
        TracerptFWPrintf(a1, (wchar_t *)L"%u", v23, a4);
        return LastError;
      }
      v25 = L"0x%X";
      if ( !(_BYTE)a4 )
        v25 = L"%X";
      goto LABEL_29;
    }
    v24 = (v23 >> 8) + ((unsigned __int8)v23 << 8);
    goto LABEL_27;
  }
  if ( !(unsigned __int8)PrintEventMap((int)a1, 19, a7, v23, 0) )
  {
    v17 = dwAddressStringLength;
    LOBYTE(a4) = a2;
    goto LABEL_25;
  }
  return LastError;
}

```

## disassembly

```asm
0x14001232c  mov     [rsp-8+arg_8], rbx
0x140012331  push    rbp
0x140012332  push    rsi
0x140012333  push    rdi
0x140012334  push    r12
0x140012336  push    r13
0x140012338  push    r14
0x14001233a  push    r15
0x14001233c  lea     rbp, [rsp-0EA0h]
0x140012344  sub     rsp, 0FA0h
0x14001234b  mov     rax, cs:__security_cookie
0x140012352  xor     rax, rsp
0x140012355  mov     [rbp+0ED0h+var_40], rax
0x14001235c  mov     r12, qword ptr [rbp+0ED0h+arg_30]
0x140012363  xor     r11d, r11d
0x140012366  mov     r10d, r9d
0x140012369  mov     rbx, r8
0x14001236c  mov     r9b, dl; unsigned int
0x14001236f  mov     [rsp+0FD0h+var_F80], dl
0x140012373  mov     rdx, [rbp+0ED0h+arg_28]
0x14001237a  mov     rdi, rcx
0x14001237d  mov     dword ptr [rsp+0FD0h+Size], r10d
0x140012382  mov     r14d, r11d
0x140012385  mov     [rsp+0FD0h+var_F70], r11
0x14001238a  mov     r15d, r11d
0x14001238d  mov     [rsp+0FD0h+lpMultiByteStr], r11
0x140012392  test    byte ptr [rdx], 1
0x140012395  mov     qword ptr [rsp+0FD0h+FileTime.dwLowDateTime], r11
0x14001239a  mov     qword ptr [rsp+0FD0h+SystemTime.wYear], r11
0x14001239f  jz      short loc_1400123AA
0x1400123a1  lea     eax, [r11+32h]
0x1400123a5  jmp     loc_14001309F
0x1400123aa  test    rbx, rbx
0x1400123ad  jnz     short loc_1400123B7
0x1400123af  lea     eax, [rbx+0Dh]
0x1400123b2  jmp     loc_14001309F
0x1400123b7  mov     eax, 20h ; ' '
0x1400123bc  mov     r13d, r11d
0x1400123bf  lea     r8d, [rax+20h]
0x1400123c3  test    [rbp+0ED0h+arg_20], r8b
0x1400123ca  jnz     short loc_1400123EC
0x1400123cc  test    [rbp+0ED0h+arg_20], al
0x1400123d2  jz      short loc_1400123D9
0x1400123d4  mov     r8d, eax
0x1400123d7  jmp     short loc_1400123EC
0x1400123d9  mov     rax, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x1400123e0  mov     ecx, [rax+21E8h]
0x1400123e6  test    ecx, ecx
0x1400123e8  cmovnz  r8d, ecx
0x1400123ec  movzx   esi, word ptr [rdx+8]
0x1400123f0  mov     eax, 0Dh
0x1400123f5  movzx   ecx, word ptr [rdx+0Ah]
0x1400123f9  mov     edx, 12Ch
0x1400123fe  mov     [rsp+0FD0h+dwAddressStringLength], ecx
0x140012402  cmp     esi, edx
0x140012404  ja      loc_140012951
0x14001240a  jz      loc_140012C02
0x140012410  lea     edx, [rax+6]; int
0x140012413  cmp     esi, eax
0x140012415  ja      loc_1400125FF
0x14001241b  jz      loc_140012845
0x140012421  cmp     esi, 7
0x140012424  ja      loc_140012589
0x14001242a  jz      loc_140012582
0x140012430  sub     esi, 1
0x140012433  jz      loc_140012AE7
0x140012439  sub     esi, 1
0x14001243c  jz      loc_140012996
0x140012442  sub     esi, 1
0x140012445  jz      loc_14001257A
0x14001244b  sub     esi, 1
0x14001244e  jz      loc_14001251D
0x140012454  sub     esi, 1
0x140012457  jz      loc_1400124EE
0x14001245d  cmp     esi, 1
0x140012460  jnz     loc_140012D7F
0x140012466  movzx   ebx, word ptr [rbx]
0x140012469  test    r12, r12
0x14001246c  jz      short loc_140012492
0x14001246e  mov     r9d, ebx; int
0x140012471  mov     [rsp+0FD0h+lpWideCharStr], r11; unsigned __int16 *
0x140012476  mov     r8, r12; int
0x140012479  mov     rcx, rdi; int
0x14001247c  call    PrintEventMap
0x140012481  test    al, al
0x140012483  jnz     loc_14001309C
0x140012489  mov     ecx, [rsp+0FD0h+dwAddressStringLength]
0x14001248d  mov     r9b, [rsp+0FD0h+var_F80]
0x140012492  mov     eax, 16h
0x140012497  cmp     ax, cx
0x14001249a  jnz     short loc_1400124BE
0x14001249c  movzx   r8d, bl
0x1400124a0  shl     r8d, 8
0x1400124a4  shr     ebx, 8
0x1400124a7  add     r8d, ebx
0x1400124aa  lea     rdx, aU; "%u"
0x1400124b1  mov     rcx, rdi; struct _iobuf *
0x1400124b4  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x1400124b9  jmp     loc_14001309C
0x1400124be  mov     eax, 11h
0x1400124c3  mov     r8d, ebx
0x1400124c6  cmp     ax, cx
0x1400124c9  mov     rcx, rdi
0x1400124cc  jnz     short loc_1400124E5
0x1400124ce  test    r9b, r9b
0x1400124d1  lea     rax, asc_140046194; "%X"
0x1400124d8  lea     rdx, a0xX; "0x%X"
0x1400124df  cmovz   rdx, rax
0x1400124e3  jmp     short loc_1400124B4
0x1400124e5  lea     rdx, aU; "%u"
0x1400124ec  jmp     short loc_1400124B4
0x1400124ee  movsx   ebx, word ptr [rbx]
0x1400124f1  test    r12, r12
0x1400124f4  jz      short loc_140012511
0x1400124f6  mov     r9d, ebx; int
0x1400124f9  mov     [rsp+0FD0h+lpWideCharStr], r11; unsigned __int16 *
0x1400124fe  mov     r8, r12; int
0x140012501  mov     rcx, rdi; int
0x140012504  call    PrintEventMap
0x140012509  test    al, al
0x14001250b  jnz     loc_14001309C
0x140012511  mov     r8d, ebx
0x140012514  lea     rdx, aD; "%d"
0x14001251b  jmp     short loc_1400124B1
0x14001251d  movzx   ebx, byte ptr [rbx]
0x140012520  test    r12, r12
0x140012523  jz      short loc_140012549
0x140012525  mov     r9d, ebx; int
0x140012528  mov     [rsp+0FD0h+lpWideCharStr], r11; unsigned __int16 *
0x14001252d  mov     r8, r12; int
0x140012530  mov     rcx, rdi; int
0x140012533  call    PrintEventMap
0x140012538  test    al, al
0x14001253a  jnz     loc_14001309C
0x140012540  mov     ecx, [rsp+0FD0h+dwAddressStringLength]
0x140012544  mov     r9b, [rsp+0FD0h+var_F80]
0x140012549  mov     r15d, 10h
0x14001254f  cmp     r15w, cx
0x140012553  jnz     short loc_140012572
0x140012555  test    r9b, r9b
0x140012558  lea     rax, asc_140046194; "%X"
0x14001255f  lea     rdx, a0xX; "0x%X"
0x140012566  mov     r8d, ebx
0x140012569  cmovz   rdx, rax
0x14001256d  jmp     loc_1400124B1
0x140012572  mov     r8d, ebx
0x140012575  jmp     loc_1400124AA
0x14001257a  movsx   ebx, byte ptr [rbx]
0x14001257d  jmp     loc_1400124F1
0x140012582  mov     ebx, [rbx]
0x140012584  jmp     loc_1400124F1
0x140012589  mov     ecx, esi
0x14001258b  sub     ecx, 8
0x14001258e  jz      loc_140012841
0x140012594  sub     ecx, 1
0x140012597  jz      short loc_1400125E8
0x140012599  sub     ecx, 1
0x14001259c  jz      loc_1400127E4
0x1400125a2  sub     ecx, 1
0x1400125a5  jz      short loc_1400125D7
0x1400125a7  cmp     ecx, 1
0x1400125aa  jnz     loc_140012D7F
0x1400125b0  mov     rax, [rbx]
0x1400125b3  mov     qword ptr [rsp+0FD0h+SystemTime.wYear], rax
0x1400125b8  movsd   xmm2, qword ptr [rsp+0FD0h+SystemTime.wYear]
0x1400125be  movq    r8, xmm2
0x1400125c3  lea     rdx, asc_140046214; "%f"
0x1400125ca  mov     rcx, rdi; struct _iobuf *
0x1400125cd  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x1400125d2  jmp     loc_14001309C
0x1400125d7  mov     eax, [rbx]
0x1400125d9  mov     dword ptr [rsp+0FD0h+Size], eax
0x1400125dd  movss   xmm2, dword ptr [rsp+0FD0h+Size]
0x1400125e3  cvtps2pd xmm2, xmm2
0x1400125e6  jmp     short loc_1400125BE
0x1400125e8  mov     r8, [rbx]
0x1400125eb  lea     rdx, aI64d; "%I64d"
0x1400125f2  mov     rcx, rdi; struct _iobuf *
0x1400125f5  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x1400125fa  jmp     loc_14001309C
0x1400125ff  cmp     esi, edx
0x140012601  ja      loc_140012784
0x140012607  jz      loc_140012747
0x14001260d  mov     ecx, esi
0x14001260f  sub     ecx, 0Eh
0x140012612  jz      loc_1400127B3
0x140012618  sub     ecx, 1
0x14001261b  jz      loc_140012723
0x140012621  sub     ecx, 1
0x140012624  jz      loc_140012F16
0x14001262a  sub     ecx, 1
0x14001262d  jz      loc_1400126CF
0x140012633  cmp     ecx, 1
0x140012636  jnz     loc_140012D7F
0x14001263c  movups  xmm0, xmmword ptr [rbx]
0x14001263f  movq    r8, xmm0
0x140012644  mov     rax, r8
0x140012647  shr     rax, 10h
0x14001264b  movups  xmmword ptr [rsp+0FD0h+SystemTime.wYear], xmm0
0x140012650  cmp     ax, 0Ch
0x140012654  ja      short loc_14001267B
0x140012656  xor     edx, edx; union _LARGE_INTEGER *
0x140012658  lea     r8, [rbp+0ED0h+saAddress]; unsigned __int16 *
0x14001265c  mov     byte ptr [rsp+0FD0h+lpWideCharStr], 1; bool
0x140012661  lea     rcx, [rsp+0FD0h+SystemTime]; lpSystemTime
0x140012666  call    ?FormatDateTimeString@@YAXPEBU_SYSTEMTIME@@PEBT_LARGE_INTEGER@@PEAGK_N@Z; FormatDateTimeString(_SYSTEMTIME const *,_LARGE_INTEGER const *,ushort *,ulong,bool)
0x14001266b  lea     r8, [rbp+0ED0h+saAddress]
0x14001266f  lea     rdx, aWs_2; "%ws"
0x140012676  jmp     loc_1400125F2
0x14001267b  movzx   ecx, [rbp+0ED0h+SystemTime.wSecond]
0x14001267f  movzx   edx, [rbp+0ED0h+SystemTime.wMinute]
0x140012683  movzx   eax, [rbp+0ED0h+SystemTime.wMilliseconds]
0x140012687  movzx   r10d, [rbp+0ED0h+SystemTime.wHour]
0x14001268c  movzx   r11d, [rsp+0FD0h+SystemTime.wDay]
0x140012692  movzx   ebx, [rsp+0FD0h+SystemTime.wDayOfWeek]
0x140012697  movzx   r9d, [rsp+0FD0h+SystemTime.wMonth]
0x14001269d  mov     [rsp+0FD0h+var_F88], eax
0x1400126a1  mov     [rsp+0FD0h+var_F90], ecx
0x1400126a5  mov     rcx, rdi; struct _iobuf *
0x1400126a8  mov     [rsp+0FD0h+var_F98], edx
0x1400126ac  lea     rdx, aUUUUUUUU; "%u:%u:%u:%u:%u:%u:%u:%u"
0x1400126b3  mov     [rsp+0FD0h+var_FA0], r10d
0x1400126b8  mov     [rsp+0FD0h+cchWideChar], r11d
0x1400126bd  movzx   r8d, r8w
0x1400126c1  mov     dword ptr [rsp+0FD0h+lpWideCharStr], ebx
0x1400126c5  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x1400126ca  jmp     loc_14001309C
0x1400126cf  mov     rax, [rbx]
0x1400126d2  lea     rdx, [rsp+0FD0h+SystemTime]; lpSystemTime
0x1400126d7  xorps   xmm0, xmm0
0x1400126da  mov     qword ptr [rsp+0FD0h+FileTime.dwLowDateTime], rax
0x1400126df  lea     rcx, [rsp+0FD0h+FileTime]; lpFileTime
0x1400126e4  movups  xmmword ptr [rsp+0FD0h+SystemTime.wYear], xmm0
0x1400126e9  call    cs:__imp_FileTimeToSystemTime
0x1400126ef  test    eax, eax
0x1400126f1  jz      short loc_140012705
0x1400126f3  cmp     [rsp+0FD0h+SystemTime.wMonth], 0Ch
0x1400126f9  ja      short loc_140012705
0x1400126fb  lea     rdx, [rsp+0FD0h+FileTime]
0x140012700  jmp     loc_140012658
0x140012705  mov     r9d, [rsp+0FD0h+FileTime.dwHighDateTime]
0x14001270a  lea     rdx, aUU; "%u:%u"
0x140012711  mov     r8d, [rsp+0FD0h+FileTime.dwLowDateTime]
0x140012716  mov     rcx, rdi; struct _iobuf *
0x140012719  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x14001271e  jmp     loc_14001309C
0x140012723  movups  xmm0, xmmword ptr [rbx]
0x140012726  lea     r8, [rsp+0FD0h+SystemTime]; struct _GUID *
0x14001272b  mov     edx, 80h; unsigned int
0x140012730  lea     rcx, [rbp+0ED0h+saAddress]; unsigned __int16 *
0x140012734  movdqu  xmmword ptr [rsp+0FD0h+SystemTime.wYear], xmm0
0x14001273a  call    ?CpdiGuidToString@@YAPEAGPEAGKPEAU_GUID@@@Z; CpdiGuidToString(ushort *,ulong,_GUID *)
0x14001273f  mov     r8, rax
0x140012742  jmp     loc_14001266F
0x140012747  lea     rdx, [rsp+0FD0h+FileTime]; StringSid
0x14001274c  mov     qword ptr [rsp+0FD0h+FileTime.dwLowDateTime], r11
0x140012751  mov     rcx, rbx; Sid
0x140012754  call    cs:__imp_ConvertSidToStringSidW
0x14001275a  test    eax, eax
0x14001275c  jz      loc_14001309C
0x140012762  mov     r9, qword ptr [rsp+0FD0h+FileTime.dwLowDateTime]; unsigned __int16 *
0x140012767  xor     r8d, r8d; unsigned __int8
0x14001276a  mov     dl, 1; unsigned __int8
0x14001276c  mov     rcx, rdi; struct _iobuf *
0x14001276f  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x140012774  mov     rcx, qword ptr [rsp+0FD0h+FileTime.dwLowDateTime]; hMem
0x140012779  call    cs:__imp_LocalFree
0x14001277f  jmp     loc_14001309C
0x140012784  mov     ecx, esi
0x140012786  mov     eax, 14h
0x14001278b  sub     ecx, eax
0x14001278d  jz      loc_1400128B4
0x140012793  sub     ecx, 1
0x140012796  jz      short loc_1400127E4
0x140012798  sub     ecx, 1
0x14001279b  jz      loc_140012C02
0x1400127a1  sub     ecx, 1
0x1400127a4  jz      loc_140012C6A
0x1400127aa  cmp     ecx, 2
0x1400127ad  jnz     loc_140012D7F
0x1400127b3  mov     ecx, [rsp+0FD0h+dwAddressStringLength]
0x1400127b7  mov     r14d, 100h
0x1400127bd  mov     edx, 19h
0x1400127c2  mov     [rsp+0FD0h+dwAddressStringLength], r14d
0x1400127c7  lea     eax, [r14+35h]
0x1400127cb  lea     r15d, [rdx-9]
0x1400127cf  cmp     ax, si
0x1400127d2  jnz     loc_140012DB6
0x1400127d8  mov     r10d, [rbx]
0x1400127db  add     rbx, 4
0x1400127df  jmp     loc_140012DC3
0x1400127e4  mov     r8, [rbx]
0x1400127e7  mov     eax, 15h
0x1400127ec  mov     qword ptr [rsp+0FD0h+SystemTime.wYear], r11
0x1400127f1  cmp     ax, si
0x1400127f4  jz      short loc_140012827
0x1400127f6  mov     ebx, [rsp+0FD0h+dwAddressStringLength]
0x1400127fa  mov     eax, 1Bh
0x1400127ff  cmp     ax, bx
0x140012802  jnz     short loc_140012822
  ... truncated ...
```
