# WriteCharDataText

- ea: `0x1800b7ea4`
- end: `0x1800b8be8`
- name: `WriteCharDataText`
- size: `3396`
- prototype: `__int64 __fastcall(WriteBuffer *this)`
- caller_count: `2`
- callee_count: `24`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010270`
- `0x1800949e4`

## callees

- `0x18000a2a0`
- `0x180014bd0`
- `0x180016a14`
- `0x180016ef0`
- `0x180017b60`
- `0x1800248c0`
- `0x18002de9c`
- `0x180046834`
- `0x180047fd8`
- `0x180053780`
- `0x180054380`
- `0x1800544bc`
- `0x180054a80`
- `0x18005687c`
- `0x180064520`
- `0x180065bfc`
- `0x180092008`
- `0x18009aee0`
- `0x18009bd4c`
- `0x1800b78f4`
- `0x1800b79e4`
- `0x1800b7ea4`
- `0x1800d334c`
- `0x1800d3370`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800b8347`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800b8347`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800b84c3`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800b8901`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800b84c3`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800b8901`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800b8362`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800b8362`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall WriteCharDataText(WriteBuffer *this, float *a2, __int64 a3, __int64 a4)
{
  WriteBuffer *v5; // rbx
  unsigned int v6; // edi
  unsigned __int64 v7; // rsi
  unsigned int v8; // edi
  unsigned int v9; // edi
  unsigned int v10; // edi
  __int64 v11; // r9
  __int64 v12; // rax
  __int64 v13; // r9
  wchar_t *v14; // r13
  __int64 v15; // r14
  unsigned int v16; // edi
  unsigned int v17; // edi
  unsigned int v18; // edi
  unsigned int v19; // edi
  unsigned int v20; // edi
  unsigned int v21; // edi
  unsigned int v22; // edi
  unsigned int v23; // edi
  int v24; // r8d
  unsigned int v25; // edi
  unsigned int v26; // edi
  unsigned int v27; // edi
  unsigned int v28; // edi
  LPWSTR *v29; // rax
  __int64 v30; // r14
  char *v31; // r8
  __int64 v32; // rdx
  char v33; // cl
  __int64 v34; // rax
  __int64 v35; // r9
  __int64 i; // rcx
  unsigned int v37; // edi
  struct _FILETIME v38; // rdx
  unsigned int v39; // r9d
  __int64 v40; // r9
  char *v41; // rcx
  __int64 v42; // rax
  wchar_t *p_Buffer; // rcx
  __int64 v44; // r8
  __int64 v45; // r9
  char *v46; // rcx
  __int64 v47; // rax
  __int64 v48; // rax
  struct _FILETIME *v49; // rdx
  __int64 v50; // r8
  unsigned int v51; // ebx
  unsigned int v52; // edx
  int v53; // [rsp+30h] [rbp-D0h]
  struct _FILETIME FileTime; // [rsp+38h] [rbp-C8h] BYREF
  __int128 pExceptionObject; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v56; // [rsp+50h] [rbp-B0h]
  int v57; // [rsp+58h] [rbp-A8h]
  int v58; // [rsp+5Ch] [rbp-A4h]
  int v59; // [rsp+60h] [rbp-A0h]
  struct _FILETIME v60; // [rsp+68h] [rbp-98h] BYREF
  WriteBuffer *v61; // [rsp+70h] [rbp-90h]
  __int64 v62; // [rsp+78h] [rbp-88h]
  unsigned int v63[2]; // [rsp+80h] [rbp-80h]
  __int64 v64; // [rsp+88h] [rbp-78h] BYREF
  char v65; // [rsp+90h] [rbp-70h] BYREF
  char v66; // [rsp+A0h] [rbp-60h] BYREF
  char v67; // [rsp+B0h] [rbp-50h] BYREF
  char v68; // [rsp+C0h] [rbp-40h] BYREF
  char v69[16]; // [rsp+D0h] [rbp-30h] BYREF
  char v70[16]; // [rsp+E0h] [rbp-20h] BYREF
  char v71; // [rsp+F0h] [rbp-10h] BYREF
  char v72; // [rsp+100h] [rbp+0h] BYREF
  char v73[16]; // [rsp+110h] [rbp+10h] BYREF
  SYSTEMTIME v74; // [rsp+120h] [rbp+20h] BYREF
  __int128 v75; // [rsp+130h] [rbp+30h] BYREF
  SYSTEMTIME SystemTime; // [rsp+140h] [rbp+40h] BYREF
  __int128 pSid; // [rsp+150h] [rbp+50h] BYREF
  __int64 v78; // [rsp+160h] [rbp+60h]
  int v79; // [rsp+168h] [rbp+68h]
  int v80; // [rsp+16Ch] [rbp+6Ch]
  int v81; // [rsp+170h] [rbp+70h]
  wchar_t Buffer; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v83[72]; // [rsp+1A2h] [rbp+A2h] BYREF
  __int16 v84; // [rsp+1EAh] [rbp+EAh]

  *(_QWORD *)&SystemTime.wYear = a4;
  v5 = this;
  v61 = this;
  v6 = *((_DWORD *)a2 + 3);
  v7 = 0;
  if ( (v6 & 0x80u) != 0 )
  {
    if ( !a4 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids, 13);
      }
      pSid = 0;
      v78 = 0;
      v79 = 13;
      v80 = -1;
      v81 = 363;
      throw (EvtException *)&pSid;
    }
    v34 = *((_QWORD *)this + 1);
    v35 = *((unsigned int *)this + 4);
    for ( i = v35 - 2; ; i -= 2 )
    {
      v62 = i;
      if ( i <= 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids, 13);
        }
        pSid = 0;
        v78 = 0;
        v79 = 13;
        v80 = -1;
        v81 = 384;
        throw (EvtException *)&pSid;
      }
      if ( *(_WORD *)(v34 + i) == 60 )
        break;
    }
    v37 = v6 & 0xFFFFFF7F;
    v38 = *(struct _FILETIME *)a2;
    FileTime = v38;
    *(_QWORD *)v63 = (unsigned int)(v35 - i);
    v39 = 0;
    v53 = 0;
    while ( 1 )
    {
      if ( v39 >= *((_DWORD *)a2 + 2) )
        return;
      if ( v37 > 0xB )
      {
        switch ( v37 )
        {
          case 0xCu:
            if ( snwprintf_s(&Buffer, 0x28u, 0xFFFFFFFFFFFFFFFFuLL, L"%.32g", *(_QWORD *)(*(_QWORD *)a2 + 8LL * v39)) == -1 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids, 13);
              }
              pSid = 0;
              v78 = 0;
              v79 = 13;
              v80 = -1;
              v81 = 462;
              throw (EvtException *)&pSid;
            }
            v44 = -1;
            do
              ++v44;
            while ( *(_WORD *)&v83[2 * v44 - 2] );
LABEL_167:
            p_Buffer = &Buffer;
LABEL_168:
            v39 = v53;
            goto LABEL_169;
          case 0xDu:
            v44 = 5LL - (*(_DWORD *)(*(_QWORD *)a2 + 4LL * v39) != 0);
            p_Buffer = L"true";
            if ( !*(_DWORD *)(*(_QWORD *)a2 + 4LL * v39) )
              p_Buffer = (wchar_t *)L"false";
LABEL_169:
            if ( !v44 )
              goto LABEL_172;
            goto LABEL_170;
          case 0xFu:
            v75 = *(_OWORD *)(*(_QWORD *)a2 + 16LL * v39);
            Buffer = 123;
            tlx::guid_to_string_lower<wchar_t>(v83, &v75, 0);
            v84 = v44 + 125;
            p_Buffer = &Buffer;
            LODWORD(v44) = v44 + 38;
            goto LABEL_170;
          case 0x10u:
            goto LABEL_172;
          case 0x11u:
            v64 = *(_QWORD *)(*(_QWORD *)a2 + 8LL * v39);
            v49 = (struct _FILETIME *)&v64;
LABEL_158:
            tlx::filetime_to_string<wchar_t>(&Buffer, v49);
            p_Buffer = &Buffer;
            LODWORD(v44) = 28;
LABEL_170:
            WriteBuffer::Write(v5, p_Buffer, 2 * v44);
            goto LABEL_171;
          case 0x12u:
            v74 = *(SYSTEMTIME *)(*(_QWORD *)a2 + 16LL * v39);
            v60 = 0;
            SystemTimeToFileTime(&v74, &v60);
            v49 = &v60;
            goto LABEL_158;
          case 0x14u:
            v42 = ToWcharsHex<unsigned int>(
                    &pExceptionObject,
                    &Buffer,
                    40,
                    *(unsigned int *)(*(_QWORD *)a2 + 4LL * v39));
            goto LABEL_121;
          case 0x15u:
            v42 = ToWcharsHex<unsigned __int64>(v73, &Buffer, 40, *(_QWORD *)(*(_QWORD *)a2 + 8LL * v39));
            goto LABEL_121;
        }
        if ( v37 != 35 )
        {
LABEL_182:
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids, 13);
          }
          pSid = 0;
          v78 = 0;
          v79 = 13;
          v80 = -1;
          v81 = 527;
          throw (EvtException *)&pSid;
        }
        v48 = -1;
        do
          ++v48;
        while ( *(_WORD *)(*(_QWORD *)&v38 + 2 * v48) );
      }
      else
      {
        if ( v37 == 11 )
        {
          if ( snwprintf_s(&Buffer, 0x28u, 0xFFFFFFFFFFFFFFFFuLL, L"%.16g", *(float *)(*(_QWORD *)a2 + 4LL * v39)) == -1 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids, 13);
            }
            pSid = 0;
            v78 = 0;
            v79 = 13;
            v80 = -1;
            v81 = 452;
            throw (EvtException *)&pSid;
          }
          v44 = -1;
          do
            ++v44;
          while ( *(_WORD *)&v83[2 * v44 - 2] );
          goto LABEL_167;
        }
        if ( v37 > 6 )
        {
          if ( v37 != 7 )
          {
            if ( v37 != 8 )
            {
              if ( v37 == 9 )
                v42 = ToWchars<__int64,10>(v70, &Buffer, 40, *(_QWORD *)(*(_QWORD *)a2 + 8LL * v39));
              else
                v42 = ToWchars<unsigned __int64,10>(v69, &Buffer, 40, *(_QWORD *)(*(_QWORD *)a2 + 8LL * v39));
LABEL_121:
              p_Buffer = *(wchar_t **)v42;
              v44 = *(_QWORD *)(v42 + 8);
              goto LABEL_168;
            }
            v45 = *(unsigned int *)(*(_QWORD *)a2 + 4LL * v39);
            v46 = &v71;
            goto LABEL_123;
          }
          v40 = *(unsigned int *)(*(_QWORD *)a2 + 4LL * v39);
          v41 = &v72;
LABEL_120:
          v42 = ToWchars<int,10>(v41, &Buffer, 40, v40);
          goto LABEL_121;
        }
        if ( v37 == 6 )
        {
          v45 = *(unsigned __int16 *)(*(_QWORD *)a2 + 2LL * v39);
          v46 = &v68;
          goto LABEL_123;
        }
        if ( v37 != 1 )
        {
          if ( v37 == 2 )
          {
            v47 = -1;
            do
              ++v47;
            while ( *(_BYTE *)(*(_QWORD *)&v38 + v47) );
            *(_QWORD *)&v75 = v47;
            WriteStringText_char_(v5);
            *(_QWORD *)&FileTime += (unsigned int)v75 + 1LL;
            goto LABEL_171;
          }
          if ( v37 != 3 )
          {
            if ( v37 != 4 )
            {
              if ( v37 != 5 )
                goto LABEL_182;
              v40 = (unsigned int)*(__int16 *)(*(_QWORD *)a2 + 2LL * v39);
              v41 = &v65;
              goto LABEL_120;
            }
            v45 = *(unsigned __int8 *)(v39 + *(_QWORD *)a2);
            v46 = &v66;
LABEL_123:
            v42 = ToWchars<unsigned int,10>(v46, &Buffer, 40, v45);
            goto LABEL_121;
          }
          v40 = (unsigned int)*(char *)(v39 + *(_QWORD *)a2);
          v41 = &v67;
          goto LABEL_120;
        }
        v48 = -1;
        do
          ++v48;
        while ( *(_WORD *)(*(_QWORD *)&v38 + 2 * v48) );
      }
      *(_QWORD *)&v75 = v48;
      WriteStringText_wchar_t_(v5);
      *(_QWORD *)&FileTime += 2LL * (unsigned int)v75 + 2;
LABEL_171:
      v39 = v53;
LABEL_172:
      v53 = ++v39;
      if ( v39 < *((_DWORD *)a2 + 2) )
      {
        WriteBuffer::Write(v5, L"</", 4u);
        v50 = -1;
        do
          ++v50;
        while ( *(_WORD *)(*(_QWORD *)&SystemTime.wYear + 2 * v50) );
        WriteBuffer::Write(v5, *(const void *const *)&SystemTime.wYear, 2 * v50);
        WriteBuffer::Write(v5, L">", 2u);
        v51 = *((_DWORD *)v5 + 4);
        WriteBuffer::Advance(v61, v63[0]);
        v52 = v51;
        v5 = v61;
        WriteBuffer::SetCurrentIndex(v61, v52);
        WriteBuffer::Write(v5, (const void *const)(*((_QWORD *)v5 + 1) + v62), v63[0]);
        v39 = v53;
      }
      v38 = FileTime;
    }
  }
  if ( v6 <= 0xB )
  {
    if ( v6 != 11 )
    {
      if ( v6 > 5 )
      {
        v16 = v6 - 6;
        if ( !v16 )
        {
          v11 = *(unsigned __int16 *)a2;
          goto LABEL_12;
        }
        v17 = v16 - 1;
        if ( v17 )
        {
          v18 = v17 - 1;
          if ( !v18 )
          {
            v11 = *(unsigned int *)a2;
            goto LABEL_12;
          }
          v19 = v18 - 1;
          if ( !v19 )
          {
            v12 = ToWchars<__int64,10>(&v74, &Buffer, 40, *(_QWORD *)a2);
            goto LABEL_15;
          }
          if ( v19 == 1 )
          {
            v12 = ToWchars<unsigned __int64,10>(&v74, &Buffer, 40, *(_QWORD *)a2);
            goto LABEL_15;
          }
LABEL_64:
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids, 13);
          }
          pExceptionObject = 0;
          v56 = 0;
          v57 = 13;
          v58 = -1;
          v59 = 351;
          throw (EvtException *)&pExceptionObject;
        }
        v13 = *(unsigned int *)a2;
LABEL_14:
        v12 = ToWchars<int,10>(&v74, &Buffer, 40, v13);
        goto LABEL_15;
      }
      if ( v6 == 5 )
      {
        v13 = (unsigned int)*(__int16 *)a2;
        goto LABEL_14;
      }
      if ( !v6 )
        return;
      v8 = v6 - 1;
      if ( v8 )
      {
        v9 = v8 - 1;
        if ( !v9 )
        {
          WriteStringText_char_(this);
          return;
        }
        v10 = v9 - 1;
        if ( v10 )
        {
          if ( v10 == 1 )
          {
            v11 = *(unsigned __int8 *)a2;
LABEL_12:
            v12 = ToWchars<unsigned int,10>(&v74, &Buffer, 40, v11);
LABEL_15:
            v14 = *(wchar_t **)v12;
            v15 = *(_QWORD *)(v12 + 8);
            goto LABEL_91;
          }
          goto LABEL_64;
        }
        v13 = (unsigned int)*(char *)a2;
        goto LABEL_14;
      }
LABEL_18:
      WriteStringText_wchar_t_(this);
      return;
    }
    v15 = -1;
    if ( snwprintf_s(&Buffer, 0x28u, 0xFFFFFFFFFFFFFFFFuLL, L"%.7g", *a2) == -1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids, 13);
      }
      pExceptionObject = 0;
      v56 = 0;
      v57 = 13;
      v58 = -1;
      v59 = 249;
      throw (EvtException *)&pExceptionObject;
    }
    do
      ++v15;
    while ( *(_WORD *)&v83[2 * v15 - 2] );
    goto LABEL_90;
  }
  if ( v6 > 0x11 )
  {
    v25 = v6 - 18;
    if ( v25 )
    {
      v26 = v25 - 1;
      if ( v26 )
      {
        v27 = v26 - 1;
        if ( !v27 )
        {
          v12 = ToWcharsHex<unsigned int>(&v74, &Buffer, 40, *(unsigned int *)a2);
          goto LABEL_15;
        }
        v28 = v27 - 1;
        if ( !v28 )
        {
          v12 = ToWcharsHex<unsigned __int64>(&v74, &Buffer, 40, *(_QWORD *)a2);
          goto LABEL_15;
        }
        if ( v28 != 14 )
          goto LABEL_64;
        goto LABEL_18;
      }
      if ( *((_DWORD *)a2 + 2) <= 0x44u )
      {
        memcpy_0(&pSid, *(const void **)a2, *((unsigned int *)a2 + 2));
        FileTime = 0;
        if ( IsValidSid(&pSid) )
        {
          v29 = (LPWSTR *)___replace___BY0A__WU__generic_delete___BY0A__WU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___utl__YAPEAPEA_WAEAV__unique_ptr___BY0A__WU__generic_delete___BY0A__WU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___0__Z(&FileTime);
          if ( ConvertSidToStringSidW(&pSid, v29) )
          {
            if ( FileTime )
            {
              v30 = -1;
              do
                ++v30;
              while ( *(_WORD *)(*(_QWORD *)&FileTime + 2 * v30) );
              WriteBuffer::Write(v5, *(const void *const *)&FileTime, 2 * v30);
              tlx::unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>(&FileTime);
              return;
            }
          }
        }
        tlx::unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>(&FileTime);
      }
      goto LABEL_80;
    }
    SystemTime = *(SYSTEMTIME *)*(_QWORD *)a2;
    FileTime = 0;
    SystemTimeToFileTime(&SystemTime, &FileTime);
    tlx::filetime_to_string<wchar_t>(&Buffer, &FileTime);
    v15 = 28;
LABEL_90:
    v14 = &Buffer;
    goto LABEL_91;
  }
  if ( v6 == 17 )
  {
    tlx::filetime_to_string<wchar_t>(&Buffer, a2);
    v14 = &Buffer;
    LODWORD(v15) = 28;
    goto LABEL_92;
  }
  v20 = v6 - 12;
  if ( !v20 )
  {
    v15 = -1;
    if ( snwprintf_s(&Buffer, 0x28u, 0xFFFFFFFFFFFFFFFFuLL, L"%.15g", *(_QWORD *)a2) == -1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids, 13);
      }
      pExceptionObject = 0;
      v56 = 0;
      v57 = 13;
      v58 = -1;
      v59 = 258;
      throw (EvtException *)&pExceptionObject;
    }
    do
      ++v15;
    while ( *(_WORD *)&v83[2 * v15 - 2] );
    goto LABEL_90;
  }
  v21 = v20 - 1;
  if ( v21 )
  {
    v22 = v21 - 1;
    if ( v22 )
    {
      v23 = v22 - 1;
      if ( v23 )
      {
        if ( v23 == 1 )
          return;
        goto LABEL_64;
      }
      SystemTime = *(SYSTEMTIME *)*(_QWORD *)a2;
      Buffer = 123;
      tlx::guid_to_string_lower<wchar_t>(v83, &SystemTime, 0);
      v84 = v24 + 125;
      v14 = &Buffer;
      LODWORD(v15) = v24 + 38;
LABEL_92:
      WriteBuffer::Write(v5, v14, 2 * v15);
      return;
    }
LABEL_80:
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&pExceptionObject);
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                             &pExceptionObject,
                             (unsigned int)(2 * *((_DWORD *)a2 + 2))) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids, 14);
      }
      pSid = 0;
      v78 = 0;
      v79 = 14;
      v80 = -1;
      v81 = 338;
      throw (EvtException *)&pSid;
    }
    v31 = *(char **)a2;
    if ( 2LL * *((unsigned int *)a2 + 2) )
    {
      do
      {
        v32 = pExceptionObject;
        v33 = *v31;
        *(_WORD *)(pExceptionObject + 2 * v7) = a0123456789abcd_0[(unsigned __int64)(unsigned __int8)*v31 >> 4];
        *(_WORD *)(v32 + 2 * v7 + 2) = a0123456789abcd_0[v33 & 0xF];
        v7 += 2LL;
        ++v31;
      }
      while ( v7 < 2 * (unsigned __int64)*((unsigned int *)a2 + 2) );
    }
    WriteBuffer::Write(
      v5,
      (const void *const)pExceptionObject,
      2 * ((__int64)(*((_QWORD *)&pExceptionObject + 1) - pExceptionObject) >> 1));
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&pExceptionObject);
    return;
  }
  v14 = L"true";
  if ( !*(_DWORD *)a2 )
    v14 = (wchar_t *)L"false";
  v15 = 5LL - (*(_DWORD *)a2 != 0);
LABEL_91:
  if ( v15 )
    goto LABEL_92;
}

```

## disassembly

```asm
0x1800b7ea4  push    rbp
0x1800b7ea6  push    rbx
0x1800b7ea7  push    rsi
0x1800b7ea8  push    rdi
0x1800b7ea9  push    r12
0x1800b7eab  push    r13
0x1800b7ead  push    r14
0x1800b7eaf  push    r15
0x1800b7eb1  lea     rbp, [rsp-108h]
0x1800b7eb9  sub     rsp, 208h
0x1800b7ec0  mov     rax, cs:__security_cookie
0x1800b7ec7  xor     rax, rsp
0x1800b7eca  mov     [rbp+140h+var_50], rax
0x1800b7ed1  mov     rax, r9
0x1800b7ed4  mov     qword ptr [rbp+140h+SystemTime.wYear], rax
0x1800b7ed8  mov     [rsp+240h+var_20C], r8b
0x1800b7edd  mov     r15, rdx
0x1800b7ee0  mov     rbx, rcx
0x1800b7ee3  mov     [rsp+240h+var_1D0], rcx
0x1800b7ee8  mov     edi, [rdx+0Ch]
0x1800b7eeb  xor     esi, esi
0x1800b7eed  test    dil, dil
0x1800b7ef0  js      loc_1800B8504
0x1800b7ef6  cmp     edi, 0Bh
0x1800b7ef9  ja      loc_1800B80E2
0x1800b7eff  jz      loc_1800B802F
0x1800b7f05  cmp     edi, 5
0x1800b7f08  ja      loc_1800B7FBF
0x1800b7f0e  jz      loc_1800B7FB9
0x1800b7f14  test    edi, edi
0x1800b7f16  jz      short loc_1800B7F85
0x1800b7f18  sub     edi, 1
0x1800b7f1b  jz      loc_1800B7FA8
0x1800b7f21  sub     edi, 1
0x1800b7f24  jz      short loc_1800B7F76
0x1800b7f26  sub     edi, 1
0x1800b7f29  jz      short loc_1800B7F50
0x1800b7f2b  cmp     edi, 1
0x1800b7f2e  jnz     loc_1800B8277
0x1800b7f34  movzx   r9d, byte ptr [rdx]
0x1800b7f38  mov     r8d, 28h ; '('
0x1800b7f3e  lea     rdx, [rbp+140h+Buffer]
0x1800b7f45  lea     rcx, [rbp+140h+var_120]
0x1800b7f49  call    ??$ToWchars@I$09@@YA?AV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@PEA_W_KI@Z; ToWchars<uint,10>(wchar_t *,unsigned __int64,uint)
0x1800b7f4e  jmp     short loc_1800B7F6A
0x1800b7f50  movsx   r9d, byte ptr [rdx]
0x1800b7f54  mov     r8d, 28h ; '('
0x1800b7f5a  lea     rdx, [rbp+140h+Buffer]
0x1800b7f61  lea     rcx, [rbp+140h+var_120]
0x1800b7f65  call    ??$ToWchars@H$09@@YA?AV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@PEA_W_KH@Z; ToWchars<int,10>(wchar_t *,unsigned __int64,int)
0x1800b7f6a  mov     r13, [rax]
0x1800b7f6d  mov     r14, [rax+8]
0x1800b7f71  jmp     loc_1800B84E7
0x1800b7f76  mov     r9b, r8b
0x1800b7f79  mov     r8d, [rdx+8]
0x1800b7f7d  mov     rdx, [rdx]
0x1800b7f80  call    WriteStringText_char_
0x1800b7f85  mov     rcx, [rbp+140h+var_50]
0x1800b7f8c  xor     rcx, rsp; StackCookie
0x1800b7f8f  call    __security_check_cookie
0x1800b7f94  add     rsp, 208h
0x1800b7f9b  pop     r15
0x1800b7f9d  pop     r14
0x1800b7f9f  pop     r13
0x1800b7fa1  pop     r12
0x1800b7fa3  pop     rdi
0x1800b7fa4  pop     rsi
0x1800b7fa5  pop     rbx
0x1800b7fa6  pop     rbp
0x1800b7fa7  retn
0x1800b7fa8  mov     r9b, r8b
0x1800b7fab  mov     r8d, [rdx+8]
0x1800b7faf  mov     rdx, [rdx]
0x1800b7fb2  call    WriteStringText_wchar_t_
0x1800b7fb7  jmp     short loc_1800B7F85
0x1800b7fb9  movsx   r9d, word ptr [rdx]
0x1800b7fbd  jmp     short loc_1800B7F54
0x1800b7fbf  sub     edi, 6
0x1800b7fc2  jz      short loc_1800B8026
0x1800b7fc4  sub     edi, 1
0x1800b7fc7  jz      short loc_1800B801E
0x1800b7fc9  sub     edi, 1
0x1800b7fcc  jz      short loc_1800B8016
0x1800b7fce  sub     edi, 1
0x1800b7fd1  jz      short loc_1800B7FF8
0x1800b7fd3  cmp     edi, 1
0x1800b7fd6  jnz     loc_1800B8277
0x1800b7fdc  mov     r9, [rdx]
0x1800b7fdf  lea     r8d, [rdi+27h]
0x1800b7fe3  lea     rdx, [rbp+140h+Buffer]
0x1800b7fea  lea     rcx, [rbp+140h+var_120]
0x1800b7fee  call    ??$ToWchars@_K$09@@YA?AV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@PEA_W_K1@Z; ToWchars<unsigned __int64,10>(wchar_t *,unsigned __int64,unsigned __int64)
0x1800b7ff3  jmp     loc_1800B7F6A
0x1800b7ff8  mov     r9, [rdx]
0x1800b7ffb  mov     r8d, 28h ; '('
0x1800b8001  lea     rdx, [rbp+140h+Buffer]
0x1800b8008  lea     rcx, [rbp+140h+var_120]
0x1800b800c  call    ??$ToWchars@_J$09@@YA?AV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@PEA_W_K_J@Z; ToWchars<__int64,10>(wchar_t *,unsigned __int64,__int64)
0x1800b8011  jmp     loc_1800B7F6A
0x1800b8016  mov     r9d, [rdx]
0x1800b8019  jmp     loc_1800B7F38
0x1800b801e  mov     r9d, [rdx]
0x1800b8021  jmp     loc_1800B7F54
0x1800b8026  movzx   r9d, word ptr [rdx]
0x1800b802a  jmp     loc_1800B7F38
0x1800b802f  movss   xmm0, dword ptr [rdx]
0x1800b8033  cvtps2pd xmm0, xmm0
0x1800b8036  movsd   [rsp+240h+var_220], xmm0
0x1800b803c  lea     r9, a7g; "%.7g"
0x1800b8043  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800b8047  mov     r8, r14; MaxCount
0x1800b804a  lea     edx, [r14+29h]; BufferCount
0x1800b804e  lea     rcx, [rbp+140h+Buffer]; Buffer
0x1800b8055  call    _snwprintf_s
0x1800b805a  cmp     eax, r14d
0x1800b805d  jnz     short loc_1800B80CC
0x1800b805f  lea     rax, WPP_GLOBAL_Control
0x1800b8066  lea     ebx, [r14+0Eh]
0x1800b806a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b8071  cmp     rcx, rax
0x1800b8074  jz      short loc_1800B8098
0x1800b8076  test    byte ptr [rcx+1Ch], 2
0x1800b807a  jz      short loc_1800B8098
0x1800b807c  cmp     byte ptr [rcx+19h], 2
0x1800b8080  jb      short loc_1800B8098
0x1800b8082  lea     edx, [rbx-3]
0x1800b8085  mov     r9d, ebx
0x1800b8088  lea     r8, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids
0x1800b808f  mov     rcx, [rcx+10h]
0x1800b8093  call    WPP_SF_d
0x1800b8098  xorps   xmm0, xmm0
0x1800b809b  movdqu  [rsp+240h+pExceptionObject], xmm0
0x1800b80a1  mov     [rsp+240h+var_1F0], rsi
0x1800b80a6  mov     [rsp+240h+var_1E8], ebx
0x1800b80aa  mov     [rsp+240h+var_1E4], 0FFFFFFFFh
0x1800b80b2  mov     [rsp+240h+var_1E0], 0F9h
0x1800b80ba  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800b80c1  lea     rcx, [rsp+240h+pExceptionObject]; pExceptionObject
0x1800b80c6  call    _CxxThrowException_0
0x1800b80cc  lea     rax, [rbp+140h+Buffer]
0x1800b80d3  inc     r14
0x1800b80d6  cmp     [rax+r14*2], si
0x1800b80db  jnz     short loc_1800B80D3
0x1800b80dd  jmp     loc_1800B84E0
0x1800b80e2  cmp     edi, 11h
0x1800b80e5  ja      loc_1800B8252
0x1800b80eb  jz      loc_1800B8234
0x1800b80f1  sub     edi, 0Ch
0x1800b80f4  jz      loc_1800B8184
0x1800b80fa  sub     edi, 1
0x1800b80fd  jz      short loc_1800B8160
0x1800b80ff  sub     edi, 1
0x1800b8102  jz      loc_1800B83AA
0x1800b8108  sub     edi, 1
0x1800b810b  jz      short loc_1800B811B
0x1800b810d  cmp     edi, 1
0x1800b8110  jz      loc_1800B7F85
0x1800b8116  jmp     loc_1800B8277
0x1800b811b  mov     rax, [rdx]
0x1800b811e  movups  xmm0, xmmword ptr [rax]
0x1800b8121  movdqu  xmmword ptr [rbp+140h+SystemTime.wYear], xmm0
0x1800b8126  mov     eax, 7Bh ; '{'
0x1800b812b  mov     [rbp+140h+Buffer], ax
0x1800b8132  xor     r8d, r8d
0x1800b8135  lea     rdx, [rbp+140h+SystemTime]
0x1800b8139  lea     rcx, [rbp+140h+var_9E]
0x1800b8140  call    ??$guid_to_string_lower@_W@tlx@@YAXPEA_WAEBU_GUID@@_N@Z; tlx::guid_to_string_lower<wchar_t>(wchar_t *,_GUID const &,bool)
0x1800b8145  lea     eax, [r8+7Dh]
0x1800b8149  mov     [rbp+140h+var_56], ax
0x1800b8150  lea     r13, [rbp+140h+Buffer]
0x1800b8157  lea     r14d, [r8+26h]
0x1800b815b  jmp     loc_1800B84F0
0x1800b8160  mov     eax, [rdx]
0x1800b8162  lea     rcx, aFalse; "false"
0x1800b8169  lea     r13, aTrue; "true"
0x1800b8170  test    eax, eax
0x1800b8172  cmovz   r13, rcx
0x1800b8176  neg     eax
0x1800b8178  sbb     r14, r14
0x1800b817b  add     r14, 5
0x1800b817f  jmp     loc_1800B84E7
0x1800b8184  movsd   xmm0, qword ptr [rdx]
0x1800b8188  movsd   [rsp+240h+var_220], xmm0
0x1800b818e  lea     r9, a15g; "%.15g"
0x1800b8195  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800b8199  mov     r8, r14; MaxCount
0x1800b819c  lea     edx, [r14+29h]; BufferCount
0x1800b81a0  lea     rcx, [rbp+140h+Buffer]; Buffer
0x1800b81a7  call    _snwprintf_s
0x1800b81ac  cmp     eax, r14d
0x1800b81af  jnz     short loc_1800B821E
0x1800b81b1  lea     rax, WPP_GLOBAL_Control
0x1800b81b8  lea     ebx, [r14+0Eh]
0x1800b81bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b81c3  cmp     rcx, rax
0x1800b81c6  jz      short loc_1800B81EA
0x1800b81c8  test    byte ptr [rcx+1Ch], 2
0x1800b81cc  jz      short loc_1800B81EA
0x1800b81ce  cmp     byte ptr [rcx+19h], 2
0x1800b81d2  jb      short loc_1800B81EA
0x1800b81d4  lea     edx, [rbx-2]
0x1800b81d7  mov     r9d, ebx
0x1800b81da  lea     r8, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids
0x1800b81e1  mov     rcx, [rcx+10h]
0x1800b81e5  call    WPP_SF_d
0x1800b81ea  xorps   xmm0, xmm0
0x1800b81ed  movdqu  [rsp+240h+pExceptionObject], xmm0
0x1800b81f3  mov     [rsp+240h+var_1F0], rsi
0x1800b81f8  mov     [rsp+240h+var_1E8], ebx
0x1800b81fc  mov     [rsp+240h+var_1E4], 0FFFFFFFFh
0x1800b8204  mov     [rsp+240h+var_1E0], 102h
0x1800b820c  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800b8213  lea     rcx, [rsp+240h+pExceptionObject]; pExceptionObject
0x1800b8218  call    _CxxThrowException_0
0x1800b821e  lea     rax, [rbp+140h+Buffer]
0x1800b8225  inc     r14
0x1800b8228  cmp     [rax+r14*2], si
0x1800b822d  jnz     short loc_1800B8225
0x1800b822f  jmp     loc_1800B84E0
0x1800b8234  lea     rcx, [rbp+140h+Buffer]
0x1800b823b  call    ??$filetime_to_string@_W@tlx@@YAXPEA_WAEBU_FILETIME@@_N@Z; tlx::filetime_to_string<wchar_t>(wchar_t *,_FILETIME const &,bool)
0x1800b8240  lea     r13, [rbp+140h+Buffer]
0x1800b8247  mov     r14d, 1Ch
0x1800b824d  jmp     loc_1800B84F0
0x1800b8252  sub     edi, 12h
0x1800b8255  jz      loc_1800B84AA
0x1800b825b  sub     edi, 1
0x1800b825e  jz      loc_1800B8328
0x1800b8264  sub     edi, 1
0x1800b8267  jz      loc_1800B830A
0x1800b826d  sub     edi, 1
0x1800b8270  jz      short loc_1800B82EC
0x1800b8272  cmp     edi, 0Eh
0x1800b8275  jz      short loc_1800B82E4
0x1800b8277  lea     rax, WPP_GLOBAL_Control
0x1800b827e  mov     ebx, 0Dh
0x1800b8283  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b828a  cmp     rcx, rax
0x1800b828d  jz      short loc_1800B82B0
0x1800b828f  test    byte ptr [rcx+1Ch], 2
0x1800b8293  jz      short loc_1800B82B0
0x1800b8295  cmp     byte ptr [rcx+19h], 2
0x1800b8299  jb      short loc_1800B82B0
0x1800b829b  mov     edx, ebx
0x1800b829d  mov     r9d, ebx
0x1800b82a0  lea     r8, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids
0x1800b82a7  mov     rcx, [rcx+10h]
0x1800b82ab  call    WPP_SF_d
0x1800b82b0  xorps   xmm0, xmm0
0x1800b82b3  movdqu  [rsp+240h+pExceptionObject], xmm0
0x1800b82b9  mov     [rsp+240h+var_1F0], rsi
0x1800b82be  mov     [rsp+240h+var_1E8], ebx
0x1800b82c2  mov     [rsp+240h+var_1E4], 0FFFFFFFFh
0x1800b82ca  mov     [rsp+240h+var_1E0], 15Fh
0x1800b82d2  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800b82d9  lea     rcx, [rsp+240h+pExceptionObject]; pExceptionObject
0x1800b82de  call    _CxxThrowException_0
0x1800b82e4  xor     r9d, r9d
0x1800b82e7  jmp     loc_1800B7FAB
0x1800b82ec  mov     r9, [rdx]
0x1800b82ef  mov     r8d, 28h ; '('
0x1800b82f5  lea     rdx, [rbp+140h+Buffer]
0x1800b82fc  lea     rcx, [rbp+140h+var_120]
0x1800b8300  call    ??$ToWcharsHex@_K@@YA?AV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@PEA_W_K1@Z; ToWcharsHex<unsigned __int64>(wchar_t *,unsigned __int64,unsigned __int64)
0x1800b8305  jmp     loc_1800B7F6A
0x1800b830a  mov     r9d, [rdx]
0x1800b830d  mov     r8d, 28h ; '('
0x1800b8313  lea     rdx, [rbp+140h+Buffer]
0x1800b831a  lea     rcx, [rbp+140h+var_120]
0x1800b831e  call    ??$ToWcharsHex@I@@YA?AV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@PEA_W_KI@Z; ToWcharsHex<uint>(wchar_t *,unsigned __int64,uint)
0x1800b8323  jmp     loc_1800B7F6A
0x1800b8328  cmp     dword ptr [rdx+8], 44h ; 'D'
0x1800b832c  ja      short loc_1800B83AA
0x1800b832e  mov     r8d, [rdx+8]; Size
0x1800b8332  mov     rdx, [rdx]; Src
0x1800b8335  lea     rcx, [rbp+140h+pSid]; void *
0x1800b8339  call    memcpy_0
0x1800b833e  mov     qword ptr [rsp+240h+FileTime.dwLowDateTime], rsi
0x1800b8343  lea     rcx, [rbp+140h+pSid]; pSid
0x1800b8347  call    cs:__imp_IsValidSid
0x1800b834d  test    eax, eax
0x1800b834f  jz      short loc_1800B83A0
0x1800b8351  lea     rcx, [rsp+240h+FileTime]
0x1800b8356  call    ??$replace@$$BY0A@_WU?$generic_delete@$$BY0A@_WU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@utl@@YAPEAPEA_WAEAV?$unique_ptr@$$BY0A@_WU?$generic_delete@$$BY0A@_WU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@0@@Z
0x1800b835b  mov     rdx, rax; StringSid
0x1800b835e  lea     rcx, [rbp+140h+pSid]; Sid
0x1800b8362  call    cs:__imp_ConvertSidToStringSidW
0x1800b8368  test    eax, eax
0x1800b836a  jz      short loc_1800B83A0
0x1800b836c  mov     rdx, qword ptr [rsp+240h+FileTime.dwLowDateTime]; void *
0x1800b8371  test    rdx, rdx
0x1800b8374  jz      short loc_1800B83A0
0x1800b8376  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800b837a  inc     r14
0x1800b837d  cmp     [rdx+r14*2], si
0x1800b8382  jnz     short loc_1800B837A
0x1800b8384  lea     r8d, [r14+r14]; unsigned int
0x1800b8388  mov     rcx, rbx; this
0x1800b838b  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x1800b8390  nop
  ... truncated ...
```
