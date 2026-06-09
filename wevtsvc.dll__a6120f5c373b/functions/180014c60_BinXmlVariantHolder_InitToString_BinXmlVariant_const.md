# BinXmlVariantHolder::InitToString(BinXmlVariant const &)

- ea: `0x180014c60`
- end: `0x18001623c`
- name: `?InitToString@BinXmlVariantHolder@@QEAA_NAEBUBinXmlVariant@@@Z`
- size: `5596`
- prototype: `char __fastcall(HLOCAL *this, const FILETIME *)`
- caller_count: `5`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800137b8`
- `0x180013c70`
- `0x1800710fc`
- `0x1800aeaf8`
- `0x1800b0c4c`

## callees

- `0x180014c60`
- `0x180016250`
- `0x18001696c`
- `0x180016ef0`
- `0x18001c310`
- `0x180039520`
- `0x180053d20`
- `0x1800545b4`
- `0x180054a80`
- `0x1800762b8`
- `0x180092008`
- `0x180092dbc`
- `0x180092de8`
- `0x18009aee0`
- `0x18009bd4c`
- `0x1800d334c`
- `0x1800d3370`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015c8f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015e7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015c8f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015e7b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014dad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014dda`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014f67`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014fdc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014dad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014dda`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014f67`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014fdc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014d9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014dc9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014f59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014fce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015c81`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015e6d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014d9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014dc9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014f59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014fce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015c81`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015e6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c95`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014eb5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015020`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015e56`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014eb5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015020`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015e56`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180015c73`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180015c73`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180014e5e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180014e5e`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800150dd`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800150dd`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180015f7f`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180015f7f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180014e7d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180014e7d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall BinXmlVariantHolder::InitToString(HLOCAL *this, const FILETIME *a2)
{
  __int64 dwLowDateTime; // rdx
  DWORD AnsiStringArrayByteLength; // ebx
  unsigned int v6; // ecx
  unsigned __int64 v7; // rbx
  _BYTE *v8; // rdi
  char *v9; // r14
  _BYTE *v10; // rcx
  __int64 v11; // r14
  SIZE_T v12; // rbx
  HANDLE v13; // rax
  void *v14; // rax
  size_t v15; // rbx
  HANDLE v16; // rax
  _WORD *v17; // rax
  LPWSTR v19; // r14
  DWORD v20; // r14d
  _BYTE *v21; // r8
  DWORD v22; // r9d
  char *v23; // rdi
  _BYTE *v24; // rcx
  __int64 v25; // rdi
  SIZE_T v26; // rbx
  HANDLE v27; // rax
  __int64 v28; // rdi
  SIZE_T v29; // rbx
  HANDLE v30; // rax
  void *v31; // rax
  FILETIME v32; // rcx
  _BYTE *v33; // rdx
  char *v34; // rbx
  _BYTE *v35; // rcx
  __int64 v36; // rbx
  __int64 v37; // rbx
  unsigned int v38; // r9d
  unsigned int v39; // r8d
  __int64 v40; // r10
  unsigned int v41; // r10d
  __int64 v42; // r8
  __int64 v43; // rbx
  unsigned int v44; // r10d
  __int64 v45; // rbx
  unsigned int v46; // r10d
  __int64 v47; // rbx
  unsigned int v48; // r10d
  __int64 v49; // rbx
  unsigned int v50; // r10d
  __int64 v51; // r10
  _OWORD *v52; // rdx
  _BYTE *v53; // r9
  unsigned int v54; // r8d
  _BYTE *v55; // rcx
  _QWORD *v56; // rax
  unsigned __int64 v57; // r10
  unsigned int v58; // r8d
  unsigned int v59; // edx
  unsigned int v60; // r8d
  unsigned int v61; // edx
  unsigned int v62; // r8d
  unsigned int v63; // r9d
  _OWORD *v64; // rax
  _BYTE *v65; // r8
  unsigned int v66; // r9d
  _BYTE *v67; // rcx
  _QWORD *v68; // rax
  void *v69; // r10
  DWORD i; // r9d
  unsigned __int8 v71; // r8
  __int64 v72; // rcx
  int v73; // eax
  char *p_Src; // r10
  _BYTE *v75; // r9
  unsigned int v76; // r8d
  char *v77; // rdx
  _BYTE *v78; // rcx
  char *v79; // rbx
  __int64 v80; // r9
  _BYTE *v81; // rcx
  int v82; // eax
  __int64 v83; // rdx
  __int64 v84; // r9
  unsigned __int64 v85; // r11
  _BYTE *v86; // rcx
  _BYTE *v87; // rdx
  int dwLowDateTime_low; // eax
  __int64 v89; // rdx
  __int64 v90; // r9
  unsigned __int64 v91; // r11
  _BYTE *v92; // rdx
  __int64 v93; // r15
  void *lpWideCharStr; // rbx
  HANDLE v95; // rax
  DWORD LastError; // ebx
  HLOCAL v97; // rbx
  HANDLE ProcessHeap; // rax
  __int128 pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v100; // [rsp+40h] [rbp-C0h]
  int v101; // [rsp+48h] [rbp-B8h]
  int v102; // [rsp+4Ch] [rbp-B4h]
  int v103; // [rsp+50h] [rbp-B0h]
  const WCHAR *v104; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v105; // [rsp+68h] [rbp-98h]
  LPWSTR StringSid[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 Src; // [rsp+80h] [rbp-80h] BYREF
  __int128 v108; // [rsp+90h] [rbp-70h]
  __int128 v109; // [rsp+A0h] [rbp-60h]
  _BYTE v110[30]; // [rsp+B0h] [rbp-50h]
  _BYTE v111[4]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v112[16]; // [rsp+10Ch] [rbp+Ch] BYREF
  _BYTE v113[16]; // [rsp+11Ch] [rbp+1Ch] BYREF
  _BYTE v114[16]; // [rsp+12Ch] [rbp+2Ch] BYREF
  _BYTE v115[16]; // [rsp+13Ch] [rbp+3Ch] BYREF
  _BYTE v116[16]; // [rsp+14Ch] [rbp+4Ch] BYREF
  _BYTE v117[16]; // [rsp+15Ch] [rbp+5Ch] BYREF
  _BYTE v118[28]; // [rsp+16Ch] [rbp+6Ch] BYREF
  _BYTE v119[24]; // [rsp+188h] [rbp+88h] BYREF
  _BYTE v120[24]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE pSid[72]; // [rsp+1B8h] [rbp+B8h] BYREF

  switch ( *((_DWORD *)this + 3) )
  {
    case 1:
    case 2:
    case 0xE:
      v97 = *this;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v97);
      break;
    case 0xF:
    case 0x12:
      utl::_RefCountVtable<utl::_RefCountStored<PublisherManifestResource,utl::allocator<int>,0>,0>::_FreeRefCount(
        *this,
        16);
      break;
    case 0x13:
      LocalFree(*this);
      break;
    default:
      break;
  }
  *((_DWORD *)this + 3) = 0;
  dwLowDateTime = a2[1].dwLowDateTime;
  AnsiStringArrayByteLength = a2[1].dwLowDateTime;
  v6 = a2[1].dwHighDateTime & 0xFFFFFF7F;
  if ( (a2[1].dwHighDateTime & 0x80u) != 0 )
  {
    if ( v6 == 6 )
    {
LABEL_100:
      AnsiStringArrayByteLength = 2 * dwLowDateTime;
    }
    else if ( v6 == 2 )
    {
      AnsiStringArrayByteLength = GetAnsiStringArrayByteLength(a2);
    }
    else if ( v6 )
    {
      if ( v6 == 1 )
      {
        AnsiStringArrayByteLength = GetStringArrayByteLength(a2);
      }
      else
      {
        if ( v6 != 17 )
        {
          switch ( v6 )
          {
            case 3u:
            case 4u:
            case 0x10u:
              goto LABEL_101;
            case 5u:
              goto LABEL_100;
            case 7u:
            case 8u:
            case 0xBu:
            case 0xDu:
            case 0x14u:
              AnsiStringArrayByteLength = 4 * dwLowDateTime;
              goto LABEL_101;
            case 9u:
            case 0xAu:
            case 0xCu:
            case 0x15u:
              break;
            case 0xFu:
            case 0x12u:
              AnsiStringArrayByteLength *= 16;
              goto LABEL_101;
            case 0x13u:
              AnsiStringArrayByteLength = GetSidArrayByteLength(a2);
              goto LABEL_101;
            default:
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_ee379fc095b93d44bb4c0c8f5551b3ef_Traceguids, 13);
              }
              pExceptionObject = 0;
              v100 = 0;
              v101 = 13;
              v102 = -1;
              v103 = 430;
              throw (EvtException *)&pExceptionObject;
          }
        }
        AnsiStringArrayByteLength = 8 * dwLowDateTime;
      }
    }
    goto LABEL_101;
  }
  if ( v6 )
  {
    if ( v6 != 19 )
    {
      if ( v6 == 8 )
      {
        v21 = v118;
        v22 = a2->dwLowDateTime;
        do
        {
          *--v21 = v22 % 0xA + 48;
          v22 /= 0xAu;
        }
        while ( v22 );
        v23 = (char *)&Src + 2 * (v118 - v21);
        if ( v23 <= (char *)&Src || v23 > v112 )
        {
          v23 = v112;
        }
        else
        {
          v24 = 0;
          do
          {
            *((_WORD *)&Src + (_QWORD)v24) = (char)v21[(_QWORD)v24];
            ++v24;
          }
          while ( v24 != (_BYTE *)(v118 - v21) );
        }
        v25 = (v23 - (char *)&Src) >> 1;
        v26 = 2 * (v25 + 1);
        if ( !is_mul_ok(v25 + 1, 2u) )
          v26 = -1;
        v27 = GetProcessHeap();
        v14 = HeapAlloc(v27, 0, v26);
        if ( !v14 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_24825df847e73786693847dbb8940487_Traceguids, 14);
          }
          pExceptionObject = 0;
          v100 = 0;
          v101 = 14;
          v102 = -1;
          v103 = 17;
          throw (EvtException *)&pExceptionObject;
        }
        *((_DWORD *)this + 2) = v25;
        v15 = 2 * v25;
      }
      else
      {
        switch ( v6 )
        {
          case 1u:
            v104 = (const WCHAR *)*a2;
            v105 = dwLowDateTime;
            BinXmlVariantHolder::SetString(this, &v104);
            return 1;
          case 2u:
            if ( (_DWORD)dwLowDateTime )
            {
              lpWideCharStr = operator new(saturated_mul(dwLowDateTime + 1, 2u));
              if ( !MultiByteToWideChar(
                      0,
                      0,
                      *(LPCCH *)a2,
                      a2[1].dwLowDateTime,
                      (LPWSTR)lpWideCharStr,
                      a2[1].dwLowDateTime) )
              {
                v95 = GetProcessHeap();
                HeapFree(v95, 0, lpWideCharStr);
                LastError = GetLastError();
                if ( !LastError )
                  LastError = 1287;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    17,
                    WPP_ee379fc095b93d44bb4c0c8f5551b3ef_Traceguids,
                    LastError);
                }
                pExceptionObject = 0;
                v100 = 0;
                v101 = LastError;
                v102 = -1;
                v103 = 552;
                throw (EvtException *)&pExceptionObject;
              }
              *((_WORD *)lpWideCharStr + a2[1].dwLowDateTime) = 0;
              *((_DWORD *)this + 3) = 1;
              *this = lpWideCharStr;
              *((_DWORD *)this + 2) = a2[1].dwLowDateTime;
            }
            else
            {
              v104 = &pszFormat;
              v105 = 0;
              BinXmlVariantHolder::SetString(this, &v104);
            }
            return 1;
          case 3u:
            dwLowDateTime_low = SLOBYTE(a2->dwLowDateTime);
            if ( dwLowDateTime_low < 0 )
              LOWORD(Src) = 45;
            v89 = (unsigned int)-dwLowDateTime_low;
            if ( dwLowDateTime_low >= 0 )
              v89 = (unsigned int)dwLowDateTime_low;
            v90 = utl::_ToCharsConstWrite<unsigned int,char>(v113, v89);
            v86 = (_BYTE *)(v91 + 2LL * (_QWORD)&v113[-v90]);
            if ( (unsigned __int64)v86 <= v91 || v86 > v112 )
              goto LABEL_193;
            v92 = 0;
            do
            {
              *(_WORD *)(v91 + 2LL * (_QWORD)v92) = (char)v92[v90];
              ++v92;
            }
            while ( v92 != &v113[-v90] );
            goto LABEL_132;
          case 4u:
            v65 = v114;
            v66 = LOBYTE(a2->dwLowDateTime);
            do
            {
              *--v65 = v66 % 0xA + 48;
              v66 /= 0xAu;
            }
            while ( v66 );
            v34 = (char *)&Src + 2 * (v114 - v65);
            if ( v34 <= (char *)&Src || v34 > v112 )
              goto LABEL_180;
            v67 = 0;
            do
            {
              *((_WORD *)&Src + (_QWORD)v67) = (char)v65[(_QWORD)v67];
              ++v67;
            }
            while ( v67 != (_BYTE *)(v114 - v65) );
            goto LABEL_53;
          case 5u:
            v82 = SLOWORD(a2->dwLowDateTime);
            if ( v82 < 0 )
              LOWORD(Src) = 45;
            v83 = (unsigned int)-v82;
            if ( v82 >= 0 )
              v83 = (unsigned int)v82;
            v84 = utl::_ToCharsConstWrite<unsigned int,char>(v115, v83);
            v86 = (_BYTE *)(v85 + 2LL * (_QWORD)&v115[-v84]);
            if ( (unsigned __int64)v86 <= v85 || v86 > v112 )
            {
LABEL_193:
              v86 = v112;
            }
            else
            {
              v87 = 0;
              do
              {
                *(_WORD *)(v85 + 2LL * (_QWORD)v87) = (char)v87[v84];
                ++v87;
              }
              while ( v87 != &v115[-v84] );
            }
LABEL_132:
            StringSid[0] = (LPWSTR)&Src;
            StringSid[1] = (LPWSTR)((v86 - (_BYTE *)&Src) >> 1);
            BinXmlVariantHolder::SetString(this, StringSid);
            return 1;
          case 6u:
            v53 = v116;
            v54 = LOWORD(a2->dwLowDateTime);
            do
            {
              *--v53 = v54 % 0xA + 48;
              v54 /= 0xAu;
            }
            while ( v54 );
            v34 = (char *)&Src + 2 * (v116 - v53);
            if ( v34 <= (char *)&Src || v34 > v112 )
            {
LABEL_180:
              v34 = v112;
            }
            else
            {
              v55 = 0;
              do
              {
                *((_WORD *)&Src + (_QWORD)v55) = (char)v53[(_QWORD)v55];
                ++v55;
              }
              while ( v55 != (_BYTE *)(v116 - v53) );
            }
            goto LABEL_53;
          case 7u:
            v73 = a2->dwLowDateTime;
            if ( (a2->dwLowDateTime & 0x80000000) != 0 )
              LOWORD(Src) = 45;
            p_Src = (char *)&Src;
            if ( v73 < 0 )
              p_Src = (char *)&Src + 2;
            v75 = v117;
            v76 = -v73;
            if ( v73 >= 0 )
              v76 = v73;
            do
            {
              *--v75 = v76 % 0xA + 48;
              v76 /= 0xAu;
            }
            while ( v76 );
            v77 = &p_Src[2 * (v117 - v75)];
            if ( v77 <= p_Src || v77 > v112 )
              goto LABEL_182;
            v78 = 0;
            do
            {
              *(_WORD *)&p_Src[2 * (_QWORD)v78] = (char)v75[(_QWORD)v78];
              ++v78;
            }
            while ( v78 != (_BYTE *)(v117 - v75) );
            goto LABEL_115;
          case 9u:
            if ( *(_QWORD *)a2 < 0 )
            {
              LOWORD(Src) = 45;
              v79 = (char *)&Src + 2;
            }
            else
            {
              v79 = (char *)&Src;
            }
            v80 = utl::_ToCharsConstWrite<unsigned __int64,char>(v119);
            v77 = &v79[2 * (_QWORD)&v119[-v80]];
            if ( v77 <= v79 || v77 > v112 )
            {
LABEL_182:
              v77 = v112;
            }
            else
            {
              v81 = 0;
              do
              {
                *(_WORD *)&v79[2 * (_QWORD)v81] = (char)v81[v80];
                ++v81;
              }
              while ( v81 != &v119[-v80] );
            }
LABEL_115:
            StringSid[0] = (LPWSTR)&Src;
            StringSid[1] = (LPWSTR)((v77 - (char *)&Src) >> 1);
            BinXmlVariantHolder::SetString(this, StringSid);
            return 1;
          case 0xAu:
            v7 = (unsigned __int64)*a2;
            v8 = v120;
            if ( v7 >= 0x3B9ACA00 )
            {
              do
              {
                v57 = (unsigned __int64)((v7 * (unsigned __int128)0x112E0BE826D694B3uLL) >> 64) >> 26;
                v58 = v7 - 1000000000 * v57;
                v7 = v57;
                v59 = v58 / 0xA;
                *(v8 - 1) = v58 % 0xA + 48;
                v60 = v58 / 0xA / 0xA;
                *(v8 - 2) = v59 - 10 * v60 + 48;
                v61 = v60 / 0xA;
                *(v8 - 3) = v60 % 0xA + 48;
                v62 = v60 / 0xA / 0xA;
                *(v8 - 4) = v61 - 10 * v62 + 48;
                *(v8 - 5) = v62 % 0xA + 48;
                v63 = v62 / 0xA / 0xA;
                *(v8 - 6) = v62 / 0xA % 0xA + 48;
                *(v8 - 7) = v63 % 0xA + 48;
                *(v8 - 8) = v63 / 0xA % 0xA + 48;
                v8 -= 9;
                *v8 = v63 / 0xA / 0xA % 0xA + 48;
              }
              while ( v57 >= 0x3B9ACA00 );
            }
            do
            {
              *--v8 = (unsigned int)v7 % 0xA + 48;
              LODWORD(v7) = (unsigned int)v7 / 0xA;
            }
            while ( (_DWORD)v7 );
            v9 = (char *)&Src + 2 * (v120 - v8);
            if ( v9 <= (char *)&Src || v9 > v112 )
            {
              v9 = v112;
            }
            else
            {
              v10 = 0;
              do
              {
                *((_WORD *)&Src + (_QWORD)v10) = (char)v10[(_QWORD)v8];
                ++v10;
              }
              while ( v10 != (_BYTE *)(v120 - v8) );
            }
            v11 = (v9 - (char *)&Src) >> 1;
            v12 = 2 * (v11 + 1);
            if ( !is_mul_ok(v11 + 1, 2u) )
              v12 = -1;
            v13 = GetProcessHeap();
            v14 = HeapAlloc(v13, 0, v12);
            if ( !v14 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_24825df847e73786693847dbb8940487_Traceguids, 14);
              }
              pExceptionObject = 0;
              v100 = 0;
              v101 = 14;
              v102 = -1;
              v103 = 17;
              throw (EvtException *)&pExceptionObject;
            }
            *((_DWORD *)this + 2) = v11;
            v15 = 2 * v11;
            break;
          case 0xBu:
            v93 = -1;
            if ( snwprintf_s((wchar_t *const)&Src, 0x46u, 0xFFFFFFFFFFFFFFFFuLL, L"%.7g", a2->dwLowDateTime) == -1 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_ee379fc095b93d44bb4c0c8f5551b3ef_Traceguids, 13);
              }
              pExceptionObject = 0;
              v100 = 0;
              v101 = 13;
              v102 = -1;
              v103 = 504;
              throw (EvtException *)&pExceptionObject;
            }
            do
              ++v93;
            while ( *((_WORD *)&Src + v93) );
            goto LABEL_203;
          case 0xCu:
            v93 = -1;
            if ( snwprintf_s((wchar_t *const)&Src, 0x46u, 0xFFFFFFFFFFFFFFFFuLL, L"%.15g", *a2) == -1 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_ee379fc095b93d44bb4c0c8f5551b3ef_Traceguids, 13);
              }
              pExceptionObject = 0;
              v100 = 0;
              v101 = 13;
              v102 = -1;
              v103 = 514;
              throw (EvtException *)&pExceptionObject;
            }
            do
              ++v93;
            while ( *((_WORD *)&Src + v93) );
LABEL_203:
            StringSid[0] = (LPWSTR)&Src;
            StringSid[1] = (LPWSTR)v93;
            BinXmlVariantHolder::SetString(this, StringSid);
            return 1;
          case 0xDu:
            if ( a2->dwLowDateTime )
            {
              v56 = operator new(0xAu);
              *this = v56;
              *((_DWORD *)this + 3) = 1;
              *((_DWORD *)this + 2) = 4;
              *v56 = 0x65007500720074LL;
              *((_WORD *)*this + 4) = 0;
            }
            else
            {
              v68 = operator new(0xCu);
              *this = v68;
              *((_DWORD *)this + 3) = 1;
              *((_DWORD *)this + 2) = 5;
              *v68 = *(_QWORD *)L"false";
              *((_WORD *)v68 + 4) = aFalse[4];
              *((_WORD *)*this + 5) = 0;
            }
            return 1;
          case 0xEu:
            goto LABEL_101;
          case 0xFu:
            LOWORD(Src) = 123;
            ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))tlx::guid_to_string_lower<wchar_t>)((char *)&Src + 2, *a2, 0);
            *(_DWORD *)&v110[26] = 125;
            v64 = operator new(0x4Eu);
            *this = v64;
            *((_DWORD *)this + 3) = 1;
            *((_DWORD *)this + 2) = 38;
            *v64 = Src;
            v64[1] = v108;
            v64[2] = v109;
            v64[3] = *(_OWORD *)v110;
            *(_OWORD *)((char *)v64 + 60) = *(_OWORD *)&v110[12];
            *((_WORD *)*this + 38) = 0;
            return 1;
          case 0x10u:
            return 1;
          case 0x11u:
            *(_OWORD *)StringSid = 0;
            if ( FileTimeToSystemTime(a2, (LPSYSTEMTIME)StringSid) )
            {
              v38 = *(_QWORD *)a2 % 0x989680uLL;
            }
            else
            {
              *(_OWORD *)StringSid = 0;
              v38 = 0;
            }
            v39 = LOWORD(StringSid[0]);
            v40 = 4;
            do
            {
              --v40;
              *((_WORD *)&Src + v40) = v39 % 0xA + 48;
              v39 /= 0xAu;
            }
            while ( v40 );
            WORD4(Src) = 45;
            v41 = WORD1(StringSid[0]);
            v42 = 2;
            v43 = 2;
            do
            {
              *((_WORD *)&Src + --v43 + 5) = v41 % 0xA + 48;
              v41 /= 0xAu;
            }
            while ( v43 );
            HIWORD(Src) = 45;
            v44 = HIWORD(StringSid[0]);
            v45 = 2;
            do
            {
              --v45;
              *((_WORD *)&v108 + v45) = v44 % 0xA + 48;
              v44 /= 0xAu;
            }
            while ( v45 );
            WORD2(v108) = 84;
            v46 = LOWORD(StringSid[1]);
            v47 = 2;
            do
            {
              *((_WORD *)&v108 + --v47 + 3) = v46 % 0xA + 48;
              v46 /= 0xAu;
            }
            while ( v47 );
            WORD5(v108) = 58;
            v48 = WORD1(StringSid[1]);
            v49 = 2;
            do
            {
              *((_WORD *)&v108 + --v49 + 6) = v48 % 0xA + 48;
              v48 /= 0xAu;
            }
            while ( v49 );
            LOWORD(v109) = 58;
            v50 = WORD2(StringSid[1]);
            do
            {
              --v42;
              *(_WORD *)&v110[2 * v42 - 14] = v50 % 0xA + 48;
              v50 /= 0xAu;
            }
            while ( v42 );
            WORD3(v109) = 46;
            v51 = 7;
            do
            {
              --v51;
              *(_WORD *)&v110[2 * v51 - 8] = v38 % 0xA + 48;
              v38 /= 0xAu;
            }
            while ( v51 );
            *(_DWORD *)&v110[6] = 90;
            v52 = operator new(0x3Au);
            *this = v52;
            *((_DWORD *)this + 3) = 1;
            *((_DWORD *)this + 2) = 28;
            *v52 = Src;
            v52[1] = v108;
            v52[2] = v109;
            *((_QWORD *)v52 + 6) = *(_QWORD *)v110;
            *((_WORD *)*this + 28) = 0;
            return 1;
          case 0x12u:
            StringSid[0] = 0;
            SystemTimeToFileTime(*(const SYSTEMTIME **)a2, (LPFILETIME)StringSid);
            tlx::filetime_to_string<wchar_t>(&Src, StringSid);
            v104 = (const WCHAR *)&Src;
            v105 = 28;
            BinXmlVariantHolder::SetString(this, &v104);
            return 1;
          case 0x14u:
            LODWORD(Src) = 7864368;
            v36 = *(_QWORD *)utl::_ToCharsConstBase<utl::to_wchars_result,unsigned int,16,wchar_t>(
                               &v104,
                               (char *)&Src + 4,
                               v111,
                               a2->dwLowDateTime)
                - (_QWORD)&Src;
            goto LABEL_54;
          case 0x15u:
            LODWORD(Src) = 7864368;
            v32 = *a2;
            v33 = pSid;
            do
            {
              *--v33 = a0123456789abcd[v32.dwLowDateTime & 0xF];
              v32 = (FILETIME)(*(unsigned __int64 *)&v32 >> 4);
            }
            while ( v32 );
            v34 = (char *)&Src + 2 * (pSid - v33) + 4;
            if ( v34 <= (char *)&Src + 4 || v34 > v111 )
            {
              v34 = v111;
            }
            else
            {
              v35 = 0;
              do
              {
                *((_WORD *)&Src + (_QWORD)v35 + 2) = (char)v35[(_QWORD)v33];
                ++v35;
              }
              while ( v35 != (_BYTE *)(pSid - v33) );
            }
LABEL_53:
            v36 = v34 - (char *)&Src;
LABEL_54:
            v37 = v36 >> 1;
            v14 = operator new(saturated_mul(v37 + 1, 2u));
            *((_DWORD *)this + 2) = v37;
            v15 = 2 * v37;
            break;
          default:
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_ee379fc095b93d44bb4c0c8f5551b3ef_Traceguids, 13);
            }
            pExceptionObject = 0;
            v100 = 0;
            v101 = 13;
            v102 = -1;
            v103 = 627;
            throw (EvtException *)&pExceptionObject;
        }
      }
      *this = v14;
      *((_DWORD *)this + 3) = 1;
      memcpy_0(v14, &Src, v15);
      *(_WORD *)((char *)*this + v15) = 0;
      return 1;
    }
    if ( !*(_QWORD *)a2
      || (unsigned int)dwLowDateTime < 0xC
      || (unsigned int)dwLowDateTime > 0x44
      || (memcpy_0(pSid, *(const void **)a2, a2[1].dwLowDateTime), !IsValidSid(pSid)) )
    {
LABEL_101:
      *((_DWORD *)this + 2) = 2 * AnsiStringArrayByteLength;
      v69 = operator new(saturated_mul(2 * AnsiStringArrayByteLength + 1LL, 2u));
      *this = v69;
      for ( i = 0; i < AnsiStringArrayByteLength; ++i )
      {
        v71 = *(_BYTE *)(i + *(_QWORD *)a2);
        v72 = 2 * i;
        *((_WORD *)v69 + v72) = a0123456789abcd_0[(unsigned __int64)v71 >> 4];
        *((_WORD *)v69 + v72 + 1) = a0123456789abcd_0[v71 & 0xF];
      }
      *((_WORD *)v69 + *((unsigned int *)this + 2)) = 0;
      *((_DWORD *)this + 3) = 1;
      return 1;
    }
    StringSid[0] = 0;
    if ( !ConvertSidToStringSidW(pSid, StringSid) || (v19 = StringSid[0]) == 0 )
    {
      v20 = GetLastError();
      if ( v20 != 13 )
      {
        if ( !v20 )
          v20 = 1287;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_ee379fc095b93d44bb4c0c8f5551b3ef_Traceguids, v20);
        }
        pExceptionObject = 0;
        v100 = 0;
        v101 = v20;
        v102 = -1;
        v103 = 591;
        throw (EvtException *)&pExceptionObject;
      }
      if ( StringSid[0] )
        LocalFree(StringSid[0]);
      goto LABEL_101;
    }
    v28 = -1;
    do
      ++v28;
    while ( StringSid[0][v28] );
    v29 = 2 * (v28 + 1);
    if ( !is_mul_ok(v28 + 1, 2u) )
      v29 = -1;
    v30 = GetProcessHeap();
    v31 = HeapAlloc(v30, 0, v29);
    if ( !v31 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_24825df847e73786693847dbb8940487_Traceguids, 14);
      }
      pExceptionObject = 0;
      v100 = 0;
      v101 = 14;
      v102 = -1;
      v103 = 17;
      throw (EvtException *)&pExceptionObject;
    }
    *this = v31;
    *((_DWORD *)this + 3) = 1;
    *((_DWORD *)this + 2) = v28;
    memcpy_0(v31, v19, 2 * v28);
    *((_WORD *)*this + v28) = 0;
    if ( StringSid[0] )
      LocalFree(StringSid[0]);
  }
  else
  {
    v16 = GetProcessHeap();
    v17 = HeapAlloc(v16, 0, 2u);
    if ( !v17 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_24825df847e73786693847dbb8940487_Traceguids, 14);
      }
      pExceptionObject = 0;
      v100 = 0;
      v101 = 14;
      v102 = -1;
      v103 = 17;
      throw (EvtException *)&pExceptionObject;
    }
    *this = v17;
    *((_DWORD *)this + 3) = 1;
    *((_DWORD *)this + 2) = 0;
    *v17 = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180014c60  mov     [rsp-8+arg_10], rbx
0x180014c65  push    rbp
0x180014c66  push    rsi
0x180014c67  push    rdi
0x180014c68  push    r12
0x180014c6a  push    r13
0x180014c6c  push    r14
0x180014c6e  push    r15
0x180014c70  lea     rbp, [rsp-110h]
0x180014c78  sub     rsp, 210h
0x180014c7f  mov     rax, cs:__security_cookie
0x180014c86  xor     rax, rsp
0x180014c89  mov     [rbp+140h+var_40], rax
0x180014c90  mov     rdi, rdx
0x180014c93  mov     rsi, rcx
0x180014c96  mov     eax, [rcx+0Ch]
0x180014c99  dec     eax; switch 19 cases
0x180014c9b  lea     r13, __ImageBase
0x180014ca2  cmp     eax, 12h
0x180014ca5  jbe     loc_180015E46
0x180014cab  xor     r12d, r12d; jumptable 0000000180015E51 default case, cases 3-13,16,17
0x180014cae  mov     [rsi+0Ch], r12d
0x180014cb2  mov     edx, [rdi+8]
0x180014cb5  mov     ebx, edx
0x180014cb7  mov     eax, [rdi+0Ch]
0x180014cba  mov     ecx, eax
0x180014cbc  btr     ecx, 7
0x180014cc0  test    al, al
0x180014cc2  js      loc_18001565D
0x180014cc8  test    ecx, ecx
0x180014cca  jz      loc_180014DC9
0x180014cd0  cmp     ecx, 13h
0x180014cd3  jz      loc_180014E27
0x180014cd9  cmp     ecx, 8
0x180014cdc  jz      loc_180014EC0
0x180014ce2  dec     ecx; switch 21 cases
0x180014ce4  cmp     ecx, 14h
0x180014ce7  ja      def_180014CF8; jumptable 0000000180014CF8 default case, cases 8,19
0x180014ced  mov     eax, ds:(jpt_180014CF8 - 180000000h)[r13+rcx*4]
0x180014cf5  add     rax, r13
0x180014cf8  jmp     rax; switch jump
0x180014cfa  mov     rbx, [rdi]; jumptable 0000000180014CF8 case 10
0x180014cfd  lea     rdi, [rbp+140h+var_A0]
0x180014d04  mov     r11d, 0CCCCCCCDh
0x180014d0a  cmp     rbx, 3B9ACA00h
0x180014d11  jnb     loc_18001549C
0x180014d17  mov     eax, ebx
0x180014d19  imul    rax, r11
0x180014d1d  shr     rax, 23h
0x180014d21  mov     edx, eax
0x180014d23  dec     rdi
0x180014d26  shl     al, 2
0x180014d29  lea     ecx, [rax+rdx]
0x180014d2c  add     cl, cl
0x180014d2e  sub     bl, cl
0x180014d30  add     bl, 30h ; '0'
0x180014d33  mov     [rdi], bl
0x180014d35  mov     ebx, edx
0x180014d37  test    edx, edx
0x180014d39  jnz     short loc_180014D17
0x180014d3b  lea     rdx, [rbp+140h+var_A0]
0x180014d42  sub     rdx, rdi
0x180014d45  lea     r14, [rbp+140h+Src]
0x180014d49  lea     r14, [r14+rdx*2]
0x180014d4d  lea     rax, [rbp+140h+Src]
0x180014d51  cmp     r14, rax
0x180014d54  jbe     loc_180015D84
0x180014d5a  lea     rax, [rbp+140h+var_134]
0x180014d5e  cmp     r14, rax
0x180014d61  ja      loc_180015D84
0x180014d67  mov     rcx, r12
0x180014d6a  movsx   eax, byte ptr [rdi+rcx]
0x180014d6e  mov     word ptr [rbp+rcx*2+140h+Src], ax
0x180014d73  inc     rcx
0x180014d76  cmp     rcx, rdx
0x180014d79  jnz     short loc_180014D6A
0x180014d7b  lea     rax, [rbp+140h+Src]
0x180014d7f  sub     r14, rax
0x180014d82  sar     r14, 1
0x180014d85  lea     rcx, [r14+1]
0x180014d89  mov     eax, 2
0x180014d8e  mul     rcx
0x180014d91  mov     rbx, rax
0x180014d94  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180014d9b  cmovb   rbx, r15
0x180014d9f  call    cs:__imp_GetProcessHeap
0x180014da5  mov     rcx, rax; hHeap
0x180014da8  mov     r8, rbx; dwBytes
0x180014dab  xor     edx, edx; dwFlags
0x180014dad  call    cs:__imp_HeapAlloc
0x180014db3  test    rax, rax
0x180014db6  jz      loc_180015EA4
0x180014dbc  mov     [rsi+8], r14d
0x180014dc0  lea     rbx, [r14+r14]
0x180014dc4  jmp     loc_180014F7D
0x180014dc9  call    cs:__imp_GetProcessHeap
0x180014dcf  mov     rcx, rax; hHeap
0x180014dd2  xor     edx, edx; dwFlags
0x180014dd4  mov     r8d, 2; dwBytes
0x180014dda  call    cs:__imp_HeapAlloc
0x180014de0  test    rax, rax
0x180014de3  jz      loc_1800160DB
0x180014de9  mov     [rsi], rax
0x180014dec  mov     dword ptr [rsi+0Ch], 1
0x180014df3  mov     [rsi+8], r12d
0x180014df7  mov     [rax], r12w
0x180014dfb  mov     al, 1; jumptable 0000000180014CF8 case 16
0x180014dfd  mov     rcx, [rbp+140h+var_40]
0x180014e04  xor     rcx, rsp; StackCookie
0x180014e07  call    __security_check_cookie
0x180014e0c  mov     rbx, [rsp+240h+arg_10]
0x180014e14  add     rsp, 210h
0x180014e1b  pop     r15
0x180014e1d  pop     r14
0x180014e1f  pop     r13
0x180014e21  pop     r12
0x180014e23  pop     rdi
0x180014e24  pop     rsi
0x180014e25  pop     rbp
0x180014e26  retn
0x180014e27  mov     rax, [rdi]
0x180014e2a  test    rax, rax
0x180014e2d  jz      loc_18001576F; jumptable 0000000180014CF8 case 14
0x180014e33  cmp     edx, 0Ch
0x180014e36  jb      loc_18001576F; jumptable 0000000180014CF8 case 14
0x180014e3c  cmp     edx, 44h ; 'D'
0x180014e3f  ja      loc_18001576F; jumptable 0000000180014CF8 case 14
0x180014e45  mov     r8, rdx; Size
0x180014e48  mov     rdx, rax; Src
0x180014e4b  lea     rcx, [rbp+140h+pSid]; void *
0x180014e52  call    memcpy_0
0x180014e57  lea     rcx, [rbp+140h+pSid]; pSid
0x180014e5e  call    cs:__imp_IsValidSid
0x180014e64  test    eax, eax
0x180014e66  jz      loc_18001576F; jumptable 0000000180014CF8 case 14
0x180014e6c  mov     [rsp+240h+StringSid], r12
0x180014e71  lea     rdx, [rsp+240h+StringSid]; StringSid
0x180014e76  lea     rcx, [rbp+140h+pSid]; Sid
0x180014e7d  call    cs:__imp_ConvertSidToStringSidW
0x180014e83  test    eax, eax
0x180014e85  jz      short loc_180014E95
0x180014e87  mov     r14, [rsp+240h+StringSid]
0x180014e8c  test    r14, r14
0x180014e8f  jnz     loc_180014FA3
0x180014e95  call    cs:__imp_GetLastError
0x180014e9b  mov     r14d, eax
0x180014e9e  cmp     eax, 0Dh
0x180014ea1  jnz     loc_180015DCE
0x180014ea7  mov     rcx, [rsp+240h+StringSid]; hMem
0x180014eac  test    rcx, rcx
0x180014eaf  jz      loc_18001576F; jumptable 0000000180014CF8 case 14
0x180014eb5  call    cs:__imp_LocalFree
0x180014ebb  jmp     loc_18001576F; jumptable 0000000180014CF8 case 14
0x180014ec0  lea     r8, [rbp+140h+var_D4]
0x180014ec4  mov     r9d, [rdi]
0x180014ec7  mov     r11d, 0CCCCCCCDh
0x180014ecd  mov     edx, r9d
0x180014ed0  imul    rdx, r11
0x180014ed4  shr     rdx, 23h
0x180014ed8  dec     r8
0x180014edb  movzx   eax, dl
0x180014ede  shl     al, 2
0x180014ee1  lea     ecx, [rax+rdx]
0x180014ee4  add     cl, cl
0x180014ee6  sub     r9b, cl
0x180014ee9  add     r9b, 30h ; '0'
0x180014eed  mov     [r8], r9b
0x180014ef0  mov     r9d, edx
0x180014ef3  test    edx, edx
0x180014ef5  jnz     short loc_180014ECD
0x180014ef7  lea     rdx, [rbp+140h+var_D4]
0x180014efb  sub     rdx, r8
0x180014efe  lea     rdi, [rbp+140h+Src]
0x180014f02  lea     rdi, [rdi+rdx*2]
0x180014f06  lea     rax, [rbp+140h+Src]
0x180014f0a  cmp     rdi, rax
0x180014f0d  jbe     loc_18001591C
0x180014f13  lea     rax, [rbp+140h+var_134]
0x180014f17  cmp     rdi, rax
0x180014f1a  ja      loc_18001591C
0x180014f20  mov     rcx, r12
0x180014f23  movsx   eax, byte ptr [rcx+r8]
0x180014f28  mov     word ptr [rbp+rcx*2+140h+Src], ax
0x180014f2d  inc     rcx
0x180014f30  cmp     rcx, rdx
0x180014f33  jnz     short loc_180014F23
0x180014f35  lea     rax, [rbp+140h+Src]
0x180014f39  sub     rdi, rax
0x180014f3c  sar     rdi, 1
0x180014f3f  lea     rcx, [rdi+1]
0x180014f43  mov     eax, 2
0x180014f48  mul     rcx
0x180014f4b  mov     rbx, rax
0x180014f4e  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180014f55  cmovb   rbx, r15
0x180014f59  call    cs:__imp_GetProcessHeap
0x180014f5f  mov     rcx, rax; hHeap
0x180014f62  mov     r8, rbx; dwBytes
0x180014f65  xor     edx, edx; dwFlags
0x180014f67  call    cs:__imp_HeapAlloc
0x180014f6d  test    rax, rax
0x180014f70  jz      loc_180015FF7
0x180014f76  mov     [rsi+8], edi
0x180014f79  lea     rbx, [rdi+rdi]
0x180014f7d  mov     [rsi], rax
0x180014f80  mov     dword ptr [rsi+0Ch], 1
0x180014f87  mov     r8, rbx; Size
0x180014f8a  lea     rdx, [rbp+140h+Src]; Src
0x180014f8e  mov     rcx, rax; void *
0x180014f91  call    memcpy_0
0x180014f96  mov     rcx, [rsi]
0x180014f99  mov     [rbx+rcx], r12w
0x180014f9e  jmp     loc_180014DFB; jumptable 0000000180014CF8 case 16
0x180014fa3  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180014faa  mov     rdi, r15
0x180014fad  nop     dword ptr [rax]
0x180014fb0  inc     rdi
0x180014fb3  cmp     word ptr [r14+rdi*2], 0
0x180014fb9  jnz     short loc_180014FB0
0x180014fbb  lea     rcx, [rdi+1]
0x180014fbf  mov     eax, 2
0x180014fc4  mul     rcx
0x180014fc7  mov     rbx, rax
0x180014fca  cmovb   rbx, r15
0x180014fce  call    cs:__imp_GetProcessHeap
0x180014fd4  mov     rcx, rax; hHeap
0x180014fd7  mov     r8, rbx; dwBytes
0x180014fda  xor     edx, edx; dwFlags
0x180014fdc  call    cs:__imp_HeapAlloc
0x180014fe2  test    rax, rax
0x180014fe5  jz      loc_180016069
0x180014feb  mov     [rsi], rax
0x180014fee  mov     dword ptr [rsi+0Ch], 1
0x180014ff5  mov     [rsi+8], edi
0x180014ff8  lea     rbx, [rdi+rdi]
0x180014ffc  mov     r8, rbx; Size
0x180014fff  mov     rdx, r14; Src
0x180015002  mov     rcx, rax; void *
0x180015005  call    memcpy_0
0x18001500a  mov     rcx, [rsi]
0x18001500d  mov     [rbx+rcx], r12w
0x180015012  mov     rcx, [rsp+240h+StringSid]; hMem
0x180015017  test    rcx, rcx
0x18001501a  jz      loc_180014DFB; jumptable 0000000180014CF8 case 16
0x180015020  call    cs:__imp_LocalFree
0x180015026  jmp     loc_180014DFB; jumptable 0000000180014CF8 case 16
0x18001502b  mov     dword ptr [rbp+140h+Src], 780030h; jumptable 0000000180014CF8 case 21
0x180015032  mov     rcx, [rdi]
0x180015035  lea     rdx, [rbp+140h+pSid]
0x18001503c  dec     rdx
0x18001503f  mov     rax, rcx
0x180015042  and     eax, 0Fh
0x180015045  movzx   eax, byte ptr [rax+r13+0EC6F0h]
0x18001504e  mov     [rdx], al
0x180015050  shr     rcx, 4
0x180015054  test    rcx, rcx
0x180015057  jnz     short loc_18001503C
0x180015059  lea     r8, [rbp+140h+pSid]
0x180015060  sub     r8, rdx
0x180015063  lea     rbx, [rbp+140h+Src+4]
0x180015067  lea     rbx, [rbx+r8*2]
0x18001506b  lea     rax, [rbp+140h+Src+4]
0x18001506f  cmp     rbx, rax
0x180015072  jbe     loc_180015D8D
0x180015078  lea     rax, [rbp+140h+var_138]
0x18001507c  cmp     rbx, rax
0x18001507f  ja      loc_180015D8D
0x180015085  mov     rcx, r12
0x180015088  movsx   eax, byte ptr [rdx+rcx]
0x18001508c  mov     word ptr [rbp+rcx*2+140h+Src+4], ax
0x180015091  inc     rcx
0x180015094  cmp     rcx, r8
0x180015097  jnz     short loc_180015088
0x180015099  lea     rax, [rbp+140h+Src]
0x18001509d  sub     rbx, rax
0x1800150a0  sar     rbx, 1
0x1800150a3  lea     rcx, [rbx+1]
0x1800150a7  mov     eax, 2
0x1800150ac  mul     rcx
0x1800150af  mov     r15, 0FFFFFFFFFFFFFFFFh
0x1800150b6  cmovb   rax, r15
0x1800150ba  mov     rcx, rax; dwBytes
0x1800150bd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800150c2  mov     [rsi+8], ebx
0x1800150c5  add     rbx, rbx
0x1800150c8  jmp     loc_180014F7D
0x1800150cd  xorps   xmm0, xmm0; jumptable 0000000180014CF8 case 17
0x1800150d0  movups  xmmword ptr [rsp+240h+StringSid], xmm0
0x1800150d5  lea     rdx, [rsp+240h+StringSid]; lpSystemTime
0x1800150da  mov     rcx, rdi; lpFileTime
0x1800150dd  call    cs:__imp_FileTimeToSystemTime
0x1800150e3  test    eax, eax
0x1800150e5  jz      loc_180015DBD
0x1800150eb  mov     r9, [rdi]
0x1800150ee  mov     rax, 0D6BF94D5E57A42BDh
0x1800150f8  mul     r9
0x1800150fb  shr     rdx, 17h
0x1800150ff  imul    eax, edx, 989680h
0x180015105  sub     r9d, eax
0x180015108  movzx   r8d, word ptr [rsp+240h+StringSid]
  ... truncated ...
```
