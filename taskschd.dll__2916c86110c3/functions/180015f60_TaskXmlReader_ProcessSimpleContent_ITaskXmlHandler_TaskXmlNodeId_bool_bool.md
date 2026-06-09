# TaskXmlReader::ProcessSimpleContent(ITaskXmlHandler *,TaskXmlNodeId,bool,bool &)

- ea: `0x180015f60`
- end: `0x180017859`
- name: `?ProcessSimpleContent@TaskXmlReader@@AEAAJPEAUITaskXmlHandler@@W4TaskXmlNodeId@@_NAEA_N@Z`
- size: `6393`
- prototype: ``
- caller_count: `2`
- callee_count: `39`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800185f0`
- `0x180018a00`

## callees

- `0x18000247c`
- `0x180003840`
- `0x180003c90`
- `0x180007aa0`
- `0x1800113ec`
- `0x1800157e4`
- `0x180015810`
- `0x1800158b0`
- `0x180015f60`
- `0x180017860`
- `0x1800180f0`
- `0x180019d10`
- `0x180019d68`
- `0x18001a170`
- `0x18001c4b0`
- `0x180021240`
- `0x1800226d0`
- `0x180028a80`
- `0x1800308e4`
- `0x180032908`
- `0x180034310`
- `0x180034644`
- `0x180034d98`
- `0x180038404`
- `0x18003843c`
- `0x180038e58`
- `0x180039734`
- `0x180039e34`
- `0x18004b24c`
- `0x18004b2ac`
- `0x18004b2fc`
- `0x18004b588`
- `0x18004b600`
- `0x18004b684`
- `0x18004b93c`
- `0x18004ba18`
- `0x18004e91b`
- `0x18004e950`
- `0x180054010`

## import_xrefs

- `msvcrt!free` at `0x180016117`
- `msvcrt!free` at `0x180016995`
- `msvcrt!free` at `0x1800171de`
- `msvcrt!free` at `0x18001722a`
- `msvcrt!free` at `0x18001723a`
- `msvcrt!free` at `0x180017255`
- `msvcrt!free` at `0x18001726c`
- `msvcrt!free` at `0x180016117`
- `msvcrt!free` at `0x180016995`
- `msvcrt!free` at `0x1800171de`
- `msvcrt!free` at `0x18001722a`
- `msvcrt!free` at `0x18001723a`
- `msvcrt!free` at `0x180017255`
- `msvcrt!free` at `0x18001726c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180015fae`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180015fae`
- `OLEAUT32!__imp_SysFreeString` at `0x1800175e9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800175e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001676e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001676e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180016c38`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800173c4`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180016c38`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800173c4`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001673e`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001673e`

## string_xrefs

- `0x180016805`: `LeastPrivilege`
- `0x1800171b0`: `InteractiveToken`
- `0x180016cf1`: `InteractiveTokenOrPassword`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TaskXmlReader::ProcessSimpleContent(__int64 a1, __int64 a2, int a3, char a4, _BYTE *a5)
{
  __int64 v6; // r14
  int v9; // r8d
  __int64 *v10; // rdx
  int v11; // ecx
  int TranslatedString; // ebx
  __int64 *v13; // rdx
  int v14; // edi
  unsigned int *v15; // r12
  int v16; // r15d
  __int64 v17; // rax
  const unsigned __int16 *v18; // r8
  unsigned int v19; // r9d
  unsigned int *v20; // r11
  void *v21; // rcx
  _BYTE *v23; // rdi
  unsigned int v24; // eax
  int Value; // eax
  unsigned int v26; // eax
  int v27; // r15d
  int v28; // eax
  __int64 Data1_low; // r8
  int v30; // eax
  int v31; // eax
  bool v32; // sf
  int v33; // r15d
  const unsigned __int16 *v34; // r8
  unsigned int v35; // r9d
  int *v36; // rdi
  int v37; // eax
  int v38; // edx
  struct IErrorInfo *v39; // rdx
  int lpVtbl; // eax
  __int64 v41; // rcx
  __int64 v42; // r12
  int v43; // eax
  __int64 v44; // rax
  int v45; // eax
  int RawValue; // eax
  __int64 v47; // r8
  __int64 v48; // rdx
  int *v49; // rdi
  int v50; // r15d
  unsigned int v51; // eax
  struct IErrorInfo *v52; // rdx
  int v53; // eax
  int v54; // r8d
  __int64 *v55; // r8
  int v56; // eax
  __int64 v57; // rcx
  __int64 v58; // r15
  int v59; // eax
  struct IErrorInfo *v60; // rdx
  __int64 v61; // rcx
  int v62; // eax
  __int64 v63; // rax
  int *v64; // rdi
  int v65; // r15d
  __int64 v66; // rdx
  __int64 v67; // rax
  int *v68; // rdi
  int v69; // r15d
  __int64 v70; // r8
  HRESULT v71; // ebx
  HRESULT v72; // eax
  unsigned int *v73; // r12
  int v74; // eax
  unsigned int v75; // r11d
  __int64 v76; // rax
  const unsigned __int16 *v77; // r8
  unsigned int v78; // r9d
  int v79; // eax
  const unsigned __int64 *v80; // r9
  int v81; // edx
  unsigned __int64 v82; // r8
  const unsigned __int64 near *v83; // r9
  __int64 v84; // r10
  unsigned int *v85; // rdi
  int v86; // eax
  bool v87; // sf
  void *v88; // rbx
  __int64 v89; // r10
  unsigned int v90; // r9d
  __int64 i; // rdx
  __int16 v92; // cx
  char v93; // cl
  unsigned __int64 v94; // r8
  unsigned int *v95; // rdi
  int v96; // r15d
  __int64 v97; // rdx
  unsigned __int16 Data1; // r8
  unsigned int v99; // r9d
  const unsigned __int16 *v100; // r8
  unsigned int v101; // r9d
  int v102; // r15d
  unsigned int v103; // r9d
  int v104; // eax
  const OLECHAR *NullTerminated; // rax
  __int64 v106; // rax
  int v107; // eax
  int v108; // ecx
  int v109; // ecx
  const unsigned __int16 *v110; // r8
  unsigned int v111; // r9d
  __int64 Entry; // rax
  int v113; // eax
  int v114; // eax
  const unsigned __int64 near *v115; // r9
  __int64 v116; // r10
  unsigned __int64 v117; // r9
  const unsigned __int64 near *v118; // r10
  __int64 v119; // r11
  __int16 v120; // r10
  unsigned __int16 v121; // dx
  __int16 v122; // r10
  unsigned __int16 v123; // dx
  int DayOfMonth; // eax
  __int64 v125; // rcx
  int v126; // eax
  __int64 v127; // rax
  int v128; // eax
  unsigned __int16 *v129; // rax
  int ProcessTokenSidType; // eax
  int Privilege; // eax
  int Week; // eax
  __int64 v133; // rcx
  int v134; // eax
  const unsigned __int16 *v135; // r12
  unsigned int v136; // r15d
  OLECHAR *v137; // rbx
  int v138; // edi
  LPOLESTR v139; // rdi
  __int64 v140; // r11
  int v141; // [rsp+20h] [rbp-E0h]
  LPOLESTR lpsz; // [rsp+30h] [rbp-D0h] BYREF
  int v143; // [rsp+38h] [rbp-C8h]
  unsigned __int16 v144; // [rsp+3Ch] [rbp-C4h]
  char v145; // [rsp+40h] [rbp-C0h]
  _BYTE v146[8]; // [rsp+50h] [rbp-B0h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-A8h] BYREF
  LPOLESTR v148; // [rsp+60h] [rbp-A0h]
  int v149; // [rsp+68h] [rbp-98h]
  unsigned __int16 v150; // [rsp+6Ch] [rbp-94h]
  IID rclsid; // [rsp+70h] [rbp-90h] BYREF
  unsigned int *v152; // [rsp+80h] [rbp-80h]
  void *Block; // [rsp+88h] [rbp-78h]
  unsigned int v154; // [rsp+90h] [rbp-70h]
  _BYTE *v155; // [rsp+A0h] [rbp-60h]
  OLECHAR sz[40]; // [rsp+B0h] [rbp-50h] BYREF

  v145 = a4;
  v6 = a3;
  v155 = a5;
  v146[0] = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v148 = 0;
  v149 = 0;
  v150 = 0;
  Block = 0;
  *(_BYTE *)(a1 + 1112) = 1;
  v9 = *(_DWORD *)(a1 + 1116);
  if ( v9 == 65542 )
  {
LABEL_2:
    v10 = (__int64 *)&(&Schema::schemaEntries)[(unsigned __int16)v9][16 * v6];
  }
  else
  {
    switch ( v9 )
    {
      case 65536:
      case 65537:
        v80 = 0;
        break;
      case 65538:
      case 65539:
      case 65540:
      case 65541:
        goto LABEL_2;
      default:
        goto LABEL_197;
    }
    while ( v80 < (&Schema::schemaEntriesCount)[(unsigned __int16)v9] )
    {
      v10 = (__int64 *)(*((_QWORD *)&_ImageBase + (unsigned __int16)v9 + 46058) + ((_QWORD)v80 << 7));
      if ( *(_DWORD *)v10 == (_DWORD)v6 )
        goto LABEL_3;
      v80 = (const unsigned __int64 *)((char *)v80 + 1);
    }
LABEL_197:
    v10 = &qword_18006EE10;
  }
LABEL_3:
  v11 = *((_DWORD *)v10 + 7);
  if ( v11 != 26 )
  {
    if ( v11 )
    {
      v108 = v11 - 1;
      if ( v108 )
      {
        v109 = v108 - 8;
        if ( v109 )
        {
          if ( v109 != 2 && a4 )
          {
            if ( (_DWORD)v6 )
            {
              Entry = Schema::GetEntry(a1 + 1116, (unsigned int)v6);
              v110 = *(const unsigned __int16 **)(Entry + 8);
              v111 = *(_DWORD *)(Entry + 16);
            }
            else
            {
              v110 = 0;
              v111 = 0;
            }
            TranslatedString = TaskXmlReader::SetErrorInfo((TaskXmlReader *)a1, -2147216616, v110, v111, 0, 0);
            goto LABEL_22;
          }
        }
      }
    }
  }
  TranslatedString = 0;
  if ( v9 == 65542 )
  {
LABEL_5:
    v13 = (__int64 *)&(&Schema::schemaEntries)[(unsigned __int16)v9][16 * v6];
  }
  else
  {
    v81 = *(_DWORD *)(a1 + 1116);
    switch ( v9 )
    {
      case 65536:
      case 65537:
        v82 = 0;
        v83 = (&Schema::schemaEntriesCount)[(unsigned __int16)v81];
        v84 = 8LL * (unsigned __int16)v81 + 368464;
        break;
      case 65538:
      case 65539:
      case 65540:
      case 65541:
        goto LABEL_5;
      default:
        goto LABEL_198;
    }
    while ( v82 < (unsigned __int64)v83 )
    {
      v13 = (__int64 *)(*(_QWORD *)((char *)&_ImageBase + v84) + (v82 << 7));
      if ( *(_DWORD *)v13 == (_DWORD)v6 )
        goto LABEL_6;
      ++v82;
    }
LABEL_198:
    v13 = &qword_18006EE10;
  }
LABEL_6:
  v14 = *((_DWORD *)v13 + 7);
  switch ( v14 )
  {
    case 7:
LABEL_13:
      if ( (*(_BYTE *)(a1 + 1106) & 1) != 0 )
        SysFreeString(*(BSTR *)(a1 + 72));
      *(_DWORD *)(a1 + 64) = 0;
      *(_QWORD *)(a1 + 72) = 0;
      *(_BYTE *)(a1 + 1106) &= 0xFCu;
      *(_WORD *)(a1 + 80) = 0;
      if ( !v145 )
      {
        RawValue = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
        TranslatedString = RawValue;
        if ( RawValue < 0 )
        {
          v47 = (unsigned int)v6;
          v48 = (unsigned int)RawValue;
LABEL_73:
          v30 = TaskXmlReader::SetErrorInfo(a1, v48, v47);
          goto LABEL_162;
        }
      }
      if ( (v14 == 2 || v14 == 7) && !*(_DWORD *)(a1 + 64) )
      {
        v30 = TaskXmlReader::SetErrorInfo(a1, 2147750680LL, (unsigned int)v6, a1 + 64);
        goto LABEL_162;
      }
      if ( v14 == 6 && !*(_DWORD *)(a1 + 64) )
      {
        if ( (_DWORD)v6 )
        {
          v106 = Schema::GetEntry(a1 + 1116, (unsigned int)v6);
          v100 = *(const unsigned __int16 **)(v106 + 8);
          v101 = *(_DWORD *)(v106 + 16);
        }
        else
        {
          v100 = 0;
          v101 = 0;
        }
        TranslatedString = TaskXmlReader::SetErrorInfo(
                             (TaskXmlReader *)a1,
                             -2147216616,
                             v100,
                             v101,
                             *(const unsigned __int16 **)(a1 + 72),
                             0);
      }
      else
      {
        v20 = (unsigned int *)(a1 + 64);
        v152 = (unsigned int *)(a1 + 64);
        if ( *(_BYTE *)(a1 + 40) )
        {
          switch ( (int)v6 )
          {
            case 6:
            case 8:
            case 10:
            case 11:
            case 112:
            case 115:
            case 121:
            case 129:
            case 130:
              v135 = *(const unsigned __int16 **)(a1 + 72);
              if ( !v135 || (v136 = *v20) == 0 )
              {
                TranslatedString = TaskXmlWriter::Element(*(_QWORD *)(a1 + 16), (unsigned int)v6, &Src);
                if ( TranslatedString >= 0 )
                  break;
                goto LABEL_29;
              }
              v137 = (OLECHAR *)operator new(saturated_mul(v136 + 1, 2u));
              lpsz = v137;
              v138 = StringCchCopyNW(v137, v136 + 1, v135, v136);
              if ( v138 < 0 )
              {
                if ( v137 )
                  free(v137);
                if ( Block )
                  free(Block);
                return (unsigned int)v138;
              }
              TranslatedString = TaskXmlReader::LoadTranslatedString((const wchar_t **)&lpsz);
              if ( TranslatedString < 0 )
              {
                if ( lpsz )
                  free(lpsz);
                goto LABEL_29;
              }
              v139 = lpsz;
              TranslatedString = TaskXmlWriter::Element(*(_QWORD *)(a1 + 16), (unsigned int)v6, lpsz);
              if ( TranslatedString < 0 )
              {
                if ( v139 )
                  free(v139);
                goto LABEL_29;
              }
              if ( v139 )
                free(v139);
              break;
            default:
              if ( *(_DWORD *)(Schema::GetEntry(a1 + 1116, (unsigned int)v6) + 24) == 2 )
                goto LABEL_333;
              TranslatedString = TaskXmlWriter::Element(*(_QWORD *)(a1 + 16), (unsigned int)v6, *(_QWORD *)(v140 + 8));
              v32 = TranslatedString < 0;
              goto LABEL_294;
          }
LABEL_275:
          *(_BYTE *)(a1 + 1112) = 0;
          goto LABEL_25;
        }
      }
LABEL_21:
      *(_BYTE *)(a1 + 1112) = 0;
      if ( TranslatedString < 0 )
        goto LABEL_22;
LABEL_25:
      if ( !a2 )
        goto LABEL_22;
      v23 = v155;
      LOBYTE(v141) = *v155;
      TranslatedString = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _BYTE *, int))(*(_QWORD *)a2 + 8LL))(
                           a2,
                           a1 + 1116,
                           (unsigned int)v6,
                           v146,
                           v141);
      *v23 = 1;
      if ( TranslatedString >= 0 )
        goto LABEL_22;
      if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a2 + 24LL))(a2) )
      {
        v24 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 24LL))(a2);
        TranslatedString = TaskXmlReader::SetErrorInfo(a1, (unsigned int)TranslatedString, v24, a1 + 64);
      }
      else
      {
        TranslatedString = TaskXmlReader::SetErrorInfo(a1, (unsigned int)TranslatedString, (unsigned int)v6, a1 + 64);
      }
LABEL_29:
      v21 = Block;
      if ( !Block )
        return (unsigned int)TranslatedString;
      goto LABEL_23;
    case 20:
      LODWORD(lpsz) = 65542;
      Value = TaskXmlReader::LoadValue((TaskXmlReader *)a1, (enum Schema::Version *)&lpsz);
      TranslatedString = Value;
      if ( Value < 0 )
        TranslatedString = TaskXmlReader::SetErrorInfo(a1, (unsigned int)Value, (unsigned int)v6, a1 + 64);
      v26 = (unsigned int)lpsz;
      *(_DWORD *)(a1 + 1116) = (_DWORD)lpsz;
      rclsid.Data1 = v26;
      v152 = (unsigned int *)(a1 + 64);
      goto LABEL_21;
    case 8:
      v27 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
      if ( v27 >= 0 )
      {
        v28 = *(_DWORD *)(a1 + 64);
        switch ( v28 )
        {
          case 5:
            if ( !wcsncmp_0(*(const wchar_t **)(a1 + 72), L"false", 5u) )
            {
LABEL_37:
              LOBYTE(Data1_low) = 0;
LABEL_38:
              LOBYTE(rclsid.Data1) = Data1_low;
              TranslatedString = 0;
LABEL_45:
              v152 = (unsigned int *)(a1 + 64);
              if ( !*(_BYTE *)(a1 + 40) )
                goto LABEL_21;
              v31 = TaskXmlWriter::ElementBool(*(_QWORD *)(a1 + 16), (unsigned int)v6, Data1_low);
              goto LABEL_47;
            }
            break;
          case 4:
            if ( !wcsncmp_0(*(const wchar_t **)(a1 + 72), L"true", 4u) )
            {
              LOBYTE(Data1_low) = 1;
              goto LABEL_38;
            }
            break;
          case 1:
            if ( !wcsncmp_0(*(const wchar_t **)(a1 + 72), L"0", 1u) )
              goto LABEL_37;
            if ( !wcsncmp_0(*(const wchar_t **)(a1 + 72), L"1", 1u) )
            {
              Data1_low = 1;
              LOBYTE(rclsid.Data1) = 1;
              TranslatedString = 0;
              goto LABEL_45;
            }
            break;
        }
        v27 = -2147216616;
      }
      TranslatedString = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v27, (unsigned int)v6, a1 + 64);
      Data1_low = LOBYTE(rclsid.Data1);
      goto LABEL_45;
  }
  switch ( v14 )
  {
    case 0:
      *(_BYTE *)(a1 + 1112) = 0;
      goto LABEL_25;
    case 1:
    case 2:
    case 6:
      goto LABEL_13;
    case 3:
      v33 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
      if ( v33 < 0 )
        goto LABEL_54;
      lpsz = 0;
      v143 = 0;
      v144 = 0;
      if ( (int)TSParser::ParseTimePeriod(
                  *(const unsigned __int16 **)(a1 + 72),
                  *(unsigned int *)(a1 + 64),
                  (struct TSTimePeriod *)&lpsz) < 0
        || WORD1(lpsz) + 12 * (unsigned __int16)lpsz )
      {
        goto LABEL_53;
      }
      if ( (unsigned __int64)(v144
                            + 60
                            * (HIWORD(v143) + 60 * ((unsigned __int16)v143 + 24 * (HIWORD(lpsz) + 7 * WORD2(lpsz))))) <= 0xFFFFFFFF )
      {
        rclsid.Data1 = v144
                     + 60 * (HIWORD(v143) + 60 * ((unsigned __int16)v143 + 24 * (HIWORD(lpsz) + 7 * WORD2(lpsz))));
        TranslatedString = 0;
      }
      else
      {
        rclsid.Data1 = -1;
LABEL_53:
        v33 = -2147216616;
LABEL_54:
        if ( (_DWORD)v6 )
        {
          v67 = Schema::GetEntry(a1 + 1116, (unsigned int)v6);
          v34 = *(const unsigned __int16 **)(v67 + 8);
          v35 = *(_DWORD *)(v67 + 16);
        }
        else
        {
          v34 = 0;
          v35 = 0;
        }
        TranslatedString = TaskXmlReader::SetErrorInfo(
                             (TaskXmlReader *)a1,
                             v33,
                             v34,
                             v35,
                             *(const unsigned __int16 **)(a1 + 72),
                             *(_DWORD *)(a1 + 64));
      }
      v152 = (unsigned int *)(a1 + 64);
      if ( !*(_BYTE *)(a1 + 40) )
        goto LABEL_21;
      v36 = *(int **)(a1 + 16);
      v37 = v36[38];
      if ( v37 )
      {
        v36[38] = v37 + 1;
LABEL_68:
        TranslatedString = 1;
        goto LABEL_69;
      }
      v38 = *v36;
      if ( *v36 == 65542 )
      {
LABEL_60:
        v39 = (struct IErrorInfo *)&(&Schema::schemaEntries)[(unsigned __int16)v38][16 * v6];
      }
      else
      {
        switch ( v38 )
        {
          case 65536:
          case 65537:
            v117 = 0;
            v118 = (&Schema::schemaEntriesCount)[(unsigned __int16)v38];
            v119 = 8LL * (unsigned __int16)v38 + 368464;
            break;
          case 65538:
          case 65539:
          case 65540:
          case 65541:
            goto LABEL_60;
          default:
            goto LABEL_262;
        }
        while ( v117 < (unsigned __int64)v118 )
        {
          v39 = (struct IErrorInfo *)(*(_QWORD *)((char *)&_ImageBase + v119) + (v117 << 7));
          lpVtbl = (int)v39->lpVtbl;
          if ( LODWORD(v39->lpVtbl) == (_DWORD)v6 )
            goto LABEL_62;
          ++v117;
        }
LABEL_262:
        v39 = (struct IErrorInfo *)&qword_18006EE10;
      }
      lpVtbl = (int)v39->lpVtbl;
LABEL_62:
      if ( lpVtbl )
      {
        v41 = *((_QWORD *)v36 + 2);
        if ( !v41 )
          _com_raise_error(-2147467261, v39);
        v42 = *(_QWORD *)(a1 + 72);
        v43 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, struct IErrorInfoVtbl *, wchar_t *const))(*(_QWORD *)v41 + 216LL))(
                v41,
                &Src,
                v39[1].lpVtbl,
                Schema::namespaceUri);
        TranslatedString = v43;
        if ( v43 < 0 )
          goto LABEL_22;
        if ( !v43 )
        {
          if ( v42 )
          {
            v44 = _com_ptr_t<_com_IIID<IXmlWriter,&__s_GUID const _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030>>::operator->(v36 + 4);
            TranslatedString = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v44 + 224LL))(v44, v42);
            if ( TranslatedString < 0 )
              goto LABEL_22;
          }
        }
        goto LABEL_68;
      }
      TranslatedString = 1;
      v36[38] = 1;
LABEL_69:
      v45 = v36[38];
      if ( !v45 )
        goto LABEL_95;
      v36[38] = v45 - 1;
      goto LABEL_139;
    case 4:
      v15 = (unsigned int *)(a1 + 64);
      v16 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
      if ( v16 < 0 )
        goto LABEL_11;
      if ( (int)TSParser::ParseDateTime(*(const unsigned __int16 **)(a1 + 72), *v15, (struct TSTime *)v146) < 0 )
      {
        v16 = -2147216616;
LABEL_11:
        if ( (_DWORD)v6 )
        {
          v17 = Schema::GetEntry(a1 + 1116, (unsigned int)v6);
          v18 = *(const unsigned __int16 **)(v17 + 8);
          v19 = *(_DWORD *)(v17 + 16);
        }
        else
        {
          v18 = 0;
          v19 = 0;
        }
        TranslatedString = TaskXmlReader::SetErrorInfo(
                             (TaskXmlReader *)a1,
                             v16,
                             v18,
                             v19,
                             *(const unsigned __int16 **)(a1 + 72),
                             *v15);
      }
      v152 = (unsigned int *)(a1 + 64);
      if ( !*(_BYTE *)(a1 + 40) )
        goto LABEL_21;
      v36 = *(int **)(a1 + 16);
      v53 = v36[38];
      if ( v53 )
      {
        v36[38] = v53 + 1;
LABEL_93:
        TranslatedString = 1;
        goto LABEL_94;
      }
      v54 = *v36;
      if ( *v36 == 65542 )
      {
LABEL_84:
        v55 = (__int64 *)&(&Schema::schemaEntries)[(unsigned __int16)v54][16 * v6];
      }
      else
      {
        switch ( v54 )
        {
          case 65536:
          case 65537:
            v52 = 0;
            v115 = (&Schema::schemaEntriesCount)[(unsigned __int16)v54];
            v116 = 8LL * (unsigned __int16)v54 + 368464;
            break;
          case 65538:
          case 65539:
          case 65540:
          case 65541:
            goto LABEL_84;
          default:
            goto LABEL_259;
        }
        while ( v52 < (struct IErrorInfo *)v115 )
        {
          v55 = (__int64 *)(*(_QWORD *)((char *)&_ImageBase + v116) + ((_QWORD)v52 << 7));
          v56 = *(_DWORD *)v55;
          if ( *(_DWORD *)v55 == (_DWORD)v6 )
            goto LABEL_86;
          v52 = (struct IErrorInfo *)((char *)v52 + 1);
        }
LABEL_259:
        v55 = &qword_18006EE10;
      }
      v56 = *(_DWORD *)v55;
LABEL_86:
      if ( v56 )
      {
        v57 = *((_QWORD *)v36 + 2);
        if ( !v57 )
          _com_raise_error(-2147467261, v52);
        v58 = *(_QWORD *)(a1 + 72);
        v59 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64, wchar_t *const))(*(_QWORD *)v57 + 216LL))(
                v57,
                &Src,
                v55[1],
                Schema::namespaceUri);
        TranslatedString = v59;
        if ( v59 < 0 )
          goto LABEL_22;
        if ( !v59 && v58 )
        {
          v61 = *((_QWORD *)v36 + 2);
          if ( !v61 )
            _com_raise_error(-2147467261, v60);
          TranslatedString = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v61 + 224LL))(v61, v58);
          if ( TranslatedString < 0 )
            goto LABEL_22;
        }
        goto LABEL_93;
      }
      TranslatedString = 1;
      v36[38] = 1;
LABEL_94:
      v62 = v36[38];
      if ( v62 )
      {
        v36[38] = v62 - 1;
      }
      else
      {
LABEL_95:
        v63 = _com_ptr_t<_com_IIID<IXmlWriter,&__s_GUID const _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030>>::operator->(v36 + 4);
        TranslatedString = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v63 + 120LL))(v63);
      }
LABEL_139:
      if ( TranslatedString < 0 )
        goto LABEL_22;
      goto LABEL_275;
    case 5:
      LOWORD(rclsid.Data1) = 0;
      v95 = (unsigned int *)(a1 + 64);
      v96 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
      if ( v96 < 0 )
        goto LABEL_164;
      Data1 = 0;
      LOWORD(rclsid.Data1) = 0;
      v103 = 0;
      while ( 2 )
      {
        if ( v103 >= *v95 )
        {
          TranslatedString = 0;
          goto LABEL_169;
        }
        v122 = *(_WORD *)(*(_QWORD *)(a1 + 72) + 2LL * (int)v103);
        if ( (unsigned __int16)(v122 - 48) <= 9u )
        {
          v123 = Data1;
          Data1 = v122 + 10 * Data1 - 48;
          LOWORD(rclsid.Data1) = Data1;
          if ( Data1 >= v123 )
          {
            ++v103;
            continue;
          }
        }
        goto LABEL_244;
      }
    case 9:
      if ( a4 )
        goto LABEL_172;
      LODWORD(lpsz) = 0;
      v127 = _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(a1 + 56);
      v128 = (*(__int64 (__fastcall **)(__int64, LPOLESTR *))(*(_QWORD *)v127 + 48LL))(v127, &lpsz);
      TranslatedString = v128;
      if ( v128 >= 0 )
      {
        if ( v128 || (_DWORD)lpsz != 15 )
          TranslatedString = TaskXmlReader::SetErrorInfo(a1, 2147750680LL, (unsigned int)v6, a1 + 64);
LABEL_172:
        v152 = 0;
        if ( *(_BYTE *)(a1 + 40) )
        {
          v31 = TaskXmlWriter::Element(*(_QWORD *)(a1 + 16), (unsigned int)v6, 0);
          goto LABEL_47;
        }
        goto LABEL_21;
      }
      TranslatedString = TaskXmlReader::SetErrorInfoXmlLite((TaskXmlReader *)a1, v128);
      v21 = Block;
      if ( !Block )
        return (unsigned int)TranslatedString;
      goto LABEL_23;
    case 10:
      v71 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
      if ( v71 < 0
        || (NullTerminated = XmlParserTempString::GetNullTerminated((XmlParserTempString *)(a1 + 64)),
            v71 = CLSIDFromString(NullTerminated, &rclsid),
            v71 < 0)
        && (*XmlParserTempString::GetNullTerminated((XmlParserTempString *)(a1 + 64)) == 123
         || (v129 = XmlParserTempString::GetNullTerminated((XmlParserTempString *)(a1 + 64)),
             v71 = StringCchPrintfW(sz, 0x28u, L"{%s}", v129),
             v71 < 0)
         || (v71 = CLSIDFromString(sz, &rclsid), v71 < 0)) )
      {
        TranslatedString = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v71, (unsigned int)v6, a1 + 64);
      }
      else
      {
        TranslatedString = 0;
      }
      v152 = (unsigned int *)(a1 + 64);
      if ( !*(_BYTE *)(a1 + 40) )
        goto LABEL_21;
      lpsz = 0;
      v72 = StringFromCLSID(&rclsid, &lpsz);
      TranslatedString = v72;
      if ( v72 )
      {
        if ( v72 > 0 )
          TranslatedString = (unsigned __int16)v72 | 0x80070000;
        goto LABEL_29;
      }
      TranslatedString = TaskXmlWriter::Element(*(_QWORD *)(a1 + 16), (unsigned int)v6, lpsz);
      if ( TranslatedString < 0 )
        goto LABEL_29;
      CoTaskMemFree(lpsz);
      *(_BYTE *)(a1 + 1112) = 0;
      goto LABEL_25;
    case 11:
      v85 = (unsigned int *)(a1 + 64);
      XmlParserTempString::~XmlParserTempString((XmlParserTempString *)(a1 + 64));
      if ( !a4 )
      {
        v114 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
        TranslatedString = v114;
        if ( v114 < 0 )
          TranslatedString = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v114, (unsigned int)v6, a1 + 64);
      }
      goto LABEL_133;
    case 12:
      v95 = (unsigned int *)(a1 + 64);
      v96 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
      if ( v96 < 0 )
        goto LABEL_164;
      Data1 = 0;
      LOWORD(rclsid.Data1) = 0;
      v99 = 0;
      while ( 2 )
      {
        if ( v99 < *v95 )
        {
          v120 = *(_WORD *)(*(_QWORD *)(a1 + 72) + 2LL * (int)v99);
          if ( (unsigned __int16)(v120 - 48) <= 9u )
          {
            v121 = Data1;
            Data1 = v120 + 10 * Data1 - 48;
            LOWORD(rclsid.Data1) = Data1;
            if ( Data1 >= v121 )
            {
              ++v99;
              continue;
            }
          }
LABEL_244:
          v96 = -2147216616;
LABEL_164:
          v97 = (unsigned int)v96;
          goto LABEL_165;
        }
        break;
      }
      TranslatedString = 0;
      if ( Data1 > 0xAu )
      {
        v97 = 2147750680LL;
LABEL_165:
        TranslatedString = TaskXmlReader::SetErrorInfo(a1, v97, (unsigned int)v6, v95);
        Data1 = rclsid.Data1;
      }
LABEL_169:
      v152 = v95;
      if ( !*(_BYTE *)(a1 + 40) )
        goto LABEL_21;
      v86 = TaskXmlWriter::ElementInt(*(_QWORD *)(a1 + 16), (unsigned int)v6, Data1);
LABEL_135:
      TranslatedString = v86;
      v87 = v86 < 0;
LABEL_136:
      if ( !v87 )
        goto LABEL_21;
LABEL_22:
      v21 = Block;
      if ( Block )
LABEL_23:
        free(v21);
      return (unsigned int)TranslatedString;
    case 13:
      v68 = (int *)(a1 + 64);
      v69 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
      if ( v69 < 0 )
        goto LABEL_103;
      v107 = *v68;
      if ( !*v68 )
        goto LABEL_313;
      rclsid.Data1 = 0;
      if ( v107 == 3 )
      {
        if ( !wcsncmp_0(*(const wchar_t **)(a1 + 72), L"S4U", 3u) )
        {
          v70 = 0x4000;
          goto LABEL_274;
        }
      }
      else if ( v107 == 8 )
      {
        if ( !wcsncmp_0(*(const wchar_t **)(a1 + 72), L"Password", 8u) )
        {
          v70 = 0x40000;
          goto LABEL_274;
        }
      }
      else if ( v107 == 16 && !wcsncmp_0(*(const wchar_t **)(a1 + 72), L"InteractiveToken", 0x10u) )
      {
        v70 = 0x10000;
        goto LABEL_274;
      }
      if ( XmlParserTempString::IsEqualTo((XmlParserTempString *)(a1 + 64), L"InteractiveTokenOrPassword", 0x1Au) )
      {
        v70 = 0x80000;
LABEL_274:
        rclsid.Data1 = v70;
        TranslatedString = 0;
        goto LABEL_104;
      }
LABEL_313:
      v69 = -2147216616;
LABEL_103:
      TranslatedString = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v69, (unsigned int)v6, a1 + 64);
      v70 = rclsid.Data1;
LABEL_104:
      v152 = (unsigned int *)(a1 + 64);
      if ( !*(_BYTE *)(a1 + 40) )
        goto LABEL_21;
      v31 = TaskXmlWriter::ElementLogonType(*(_QWORD *)(a1 + 16), (unsigned int)v6, v70);
      goto LABEL_47;
    case 14:
      rclsid.Data1 = 0;
      v49 = (int *)(a1 + 64);
      v50 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
      if ( v50 < 0 )
        goto LABEL_75;
      v79 = *v49;
      if ( !*v49 )
        goto LABEL_121;
      if ( v79 == 14 )
      {
        if ( wcsncmp_0(*(const wchar_t **)(a1 + 72), L"LeastPrivilege", 0xEu) )
        {
LABEL_121:
          v50 = -2147216616;
LABEL_75:
          TranslatedString = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v50, (unsigned int)v6, a1 + 64);
          v51 = rclsid.Data1;
LABEL_76:
          v152 = (unsigned int *)(a1 + 64);
          if ( !*(_BYTE *)(a1 + 40) || (v51 & 0x1000000) == 0 )
            goto LABEL_21;
          v31 = TaskXmlWriter::ElementRunLevel(*(_QWORD *)(a1 + 16), (unsigned int)v6, 1);
LABEL_47:
          TranslatedString = v31;
          v32 = v31 < 0;
LABEL_294:
          if ( v32 )
            goto LABEL_29;
          goto LABEL_21;
        }
        v51 = 0;
      }
      else
      {
        if ( v79 != 16 || wcsncmp_0(*(const wchar_t **)(a1 + 72), L"HighestAvailable", 0x10u) )
          goto LABEL_121;
        v51 = 0x1000000;
      }
      rclsid.Data1 = v51;
      TranslatedString = 0;
      goto LABEL_76;
    case 15:
      LOWORD(rclsid.Data1) = 0;
      Week = TaskXmlReader::LoadWeek((TaskXmlReader *)a1, (unsigned __int16 *)&rclsid);
      TranslatedString = Week;
      if ( Week < 0 )
        TranslatedString = TaskXmlReader::SetErrorInfo(a1, (unsigned int)Week, (unsigned int)v6, a1 + 64);
      v152 = (unsigned int *)(a1 + 64);
      if ( !*(_BYTE *)(a1 + 40) )
        goto LABEL_21;
      v133 = *(_QWORD *)(a1 + 16);
      if ( LOWORD(rclsid.Data1) == 5 )
      {
        TranslatedString = TaskXmlWriter::Element(v133, 70, L"Last");
        if ( TranslatedString >= 0 )
          goto LABEL_21;
      }
      else
      {
        TranslatedString = TaskXmlWriter::ElementInt(v133, 70, LOWORD(rclsid.Data1));
      }
LABEL_333:
      v32 = TranslatedString < 0;
      goto LABEL_294;
    case 16:
      rclsid.Data1 = 0;
      v64 = (int *)(a1 + 64);
      v65 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
      if ( v65 < 0 )
        goto LABEL_97;
      v104 = *v64;
      if ( *v64 == 8 )
      {
        if ( !wcsncmp_0(*(const wchar_t **)(a1 + 72), L"Parallel", 8u) )
        {
          v66 = 1024;
          rclsid.Data1 = 1024;
          TranslatedString = 0;
          goto LABEL_98;
        }
      }
      else if ( v104 == 5 )
      {
        if ( !wcsncmp_0(*(const wchar_t **)(a1 + 72), L"Queue", 5u) )
        {
          v66 = 4096;
          goto LABEL_224;
        }
      }
      else if ( v104 == 9 && !wcsncmp_0(*(const wchar_t **)(a1 + 72), L"IgnoreNew", 9u) )
      {
        v66 = 0x2000;
        rclsid.Data1 = 0x2000;
        TranslatedString = 0;
        goto LABEL_98;
      }
      if ( XmlParserTempString::IsEqualTo((XmlParserTempString *)(a1 + 64), L"StopExisting", 0xCu) )
      {
        v66 = 2048;
LABEL_224:
        rclsid.Data1 = v66;
        TranslatedString = 0;
        goto LABEL_98;
      }
      v65 = -2147216616;
LABEL_97:
      TranslatedString = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v65, (unsigned int)v6, a1 + 64);
      v66 = rclsid.Data1;
LABEL_98:
      v152 = (unsigned int *)(a1 + 64);
      if ( !*(_BYTE *)(a1 + 40) )
        goto LABEL_21;
      v31 = TaskXmlWriter::ElementMultipleInstancesPolicy(*(_QWORD *)(a1 + 16), v66);
      goto LABEL_47;
    case 17:
      v134 = TaskXmlReader::SkipElement((TaskXmlReader *)a1);
      TranslatedString = v134;
      if ( v134 < 0 )
        TranslatedString = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v134, (unsigned int)v6, a1 + 64);
      v152 = (unsigned int *)(a1 + 64);
      goto LABEL_21;
    case 18:
      LOWORD(rclsid.Data1) = 0;
      DayOfMonth = TaskXmlReader::LoadDayOfMonth((TaskXmlReader *)a1, (unsigned __int16 *)&rclsid);
      TranslatedString = DayOfMonth;
      if ( DayOfMonth < 0 )
        TranslatedString = TaskXmlReader::SetErrorInfo(a1, (unsigned int)DayOfMonth, (unsigned int)v6, a1 + 64);
      v152 = (unsigned int *)(a1 + 64);
      if ( !*(_BYTE *)(a1 + 40) )
        goto LABEL_21;
      v125 = *(_QWORD *)(a1 + 16);
      if ( LOWORD(rclsid.Data1) == 32 )
      {
        TranslatedString = TaskXmlWriter::Element(v125, 68, L"Last");
        if ( TranslatedString >= 0 )
          goto LABEL_21;
      }
      else
      {
        TranslatedString = TaskXmlWriter::ElementInt(v125, 68, LOWORD(rclsid.Data1));
      }
      v87 = TranslatedString < 0;
      goto LABEL_136;
    case 19:
      rclsid.Data1 = 0;
      v126 = TaskXmlReader::LoadSessionStateChange((TaskXmlReader *)a1, &rclsid.Data1);
      TranslatedString = v126;
      if ( v126 < 0 )
        TranslatedString = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v126, (unsigned int)v6, a1 + 64);
      v152 = (unsigned int *)(a1 + 64);
      if ( !*(_BYTE *)(a1 + 40) )
        goto LABEL_21;
      v86 = TaskXmlWriter::ElementSessionStateChange(*(TaskXmlWriter **)(a1 + 16), LOWORD(rclsid.Data1));
      goto LABEL_135;
    case 21:
      ProcessTokenSidType = TaskXmlReader::LoadProcessTokenSidType(
                              (TaskXmlReader *)a1,
                              (enum JobFlags::JobFlag *)&rclsid);
      TranslatedString = ProcessTokenSidType;
      if ( ProcessTokenSidType < 0 )
        TranslatedString = TaskXmlReader::SetErrorInfo(a1, (unsigned int)ProcessTokenSidType, (unsigned int)v6, a1 + 64);
      v152 = (unsigned int *)(a1 + 64);
      if ( !*(_BYTE *)(a1 + 40) )
        goto LABEL_21;
      if ( (rclsid.Data1 & 0x8000000) != 0 )
      {
        v31 = TaskXmlWriter::ElementProcessTokenSidType(*(_QWORD *)(a1 + 16), (unsigned int)v6, 0);
        goto LABEL_47;
      }
      if ( (rclsid.Data1 & 0x10000000) == 0 )
        goto LABEL_21;
      v31 = TaskXmlWriter::ElementProcessTokenSidType(*(_QWORD *)(a1 + 16), (unsigned int)v6, 1);
      goto LABEL_47;
    case 22:
      Privilege = TaskXmlReader::LoadPrivilege((TaskXmlReader *)a1, (unsigned __int64 *)&rclsid.Data1);
      TranslatedString = Privilege;
      if ( Privilege < 0 )
        TranslatedString = TaskXmlReader::SetErrorInfo(a1, (unsigned int)Privilege, (unsigned int)v6, a1 + 64);
      v152 = (unsigned int *)(a1 + 64);
      if ( !*(_BYTE *)(a1 + 40) )
        goto LABEL_21;
      v31 = TaskXmlWriter::Element(*(_QWORD *)(a1 + 16), 135, *(_QWORD *)(a1 + 72));
      goto LABEL_47;
    case 23:
      v85 = (unsigned int *)(a1 + 64);
      v102 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
      if ( v102 < 0 )
        goto LABEL_178;
      lpsz = 0;
      v143 = 0;
      v144 = 0;
      if ( (int)TSParser::ParseTimePeriod(*(const unsigned __int16 **)(a1 + 72), *v85, (struct TSTimePeriod *)&lpsz) < 0 )
      {
        v102 = -2147216616;
LABEL_178:
        TranslatedString = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v102, (unsigned int)v6, a1 + 64);
      }
      else
      {
        TranslatedString = 0;
        v148 = lpsz;
        v149 = v143;
        v150 = v144;
      }
LABEL_133:
      v152 = v85;
      if ( !*(_BYTE *)(a1 + 40) )
        goto LABEL_21;
      v86 = TaskXmlWriter::Element(*(_QWORD *)(a1 + 16), (unsigned int)v6, *((_QWORD *)v85 + 1));
      goto LABEL_135;
    case 24:
    case 26:
      Block = 0;
      v154 = 0;
      v73 = (unsigned int *)(a1 + 64);
      v74 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
      if ( v74 < 0 )
        goto LABEL_113;
      if ( !*v73 )
        goto LABEL_241;
      if ( !*(_QWORD *)(a1 + 72) )
        goto LABEL_200;
      v154 = (*v73 & 1) + (*v73 >> 1);
      v88 = operator new(v154);
      if ( Block )
        free(Block);
      Block = v88;
      if ( v88 )
      {
        v89 = *(_QWORD *)(a1 + 72);
        if ( v89 )
        {
          v90 = *v73;
          if ( *v73 )
          {
            if ( v154 >= (*v73 & 1) + (*v73 >> 1) )
            {
              for ( i = 0; (unsigned int)i < v90; i = (unsigned int)(i + 1) )
              {
                v92 = *(_WORD *)(v89 + 2 * i);
                if ( (unsigned __int16)(v92 - 48) > 9u )
                {
                  if ( (unsigned __int16)(v92 - 97) <= 5u )
                  {
                    v93 = v92 - 87;
                  }
                  else
                  {
                    if ( (unsigned __int16)(v92 - 65) > 5u )
                      goto LABEL_200;
                    v93 = v92 - 55;
                  }
                }
                else
                {
                  v93 = v92 - 48;
                }
                v94 = (unsigned __int64)(unsigned int)i >> 1;
                if ( (i & 1) != 0 )
                  *((_BYTE *)v88 + v94) |= v93;
                else
                  *((_BYTE *)v88 + v94) = 16 * v93;
              }
              v154 = (v90 & 1) + (v90 >> 1);
LABEL_241:
              TranslatedString = 0;
LABEL_114:
              if ( v14 != 24 || (v75 = *v73, *v73 == 16) )
              {
                v152 = (unsigned int *)(a1 + 64);
                if ( !*(_BYTE *)(a1 + 40) )
                  goto LABEL_21;
                v31 = TaskXmlWriter::ElementHexString(*(_QWORD *)(a1 + 16), (unsigned int)v6, Block, v154);
                goto LABEL_47;
              }
              if ( (_DWORD)v6 )
              {
                v76 = Schema::GetEntry(a1 + 1116, (unsigned int)v6);
                v77 = *(const unsigned __int16 **)(v76 + 8);
                v78 = *(_DWORD *)(v76 + 16);
              }
              else
              {
                v77 = 0;
                v78 = 0;
              }
              v30 = TaskXmlReader::SetErrorInfo(
                      (TaskXmlReader *)a1,
                      -2147216616,
                      v77,
                      v78,
                      *(const unsigned __int16 **)(a1 + 72),
                      v75);
LABEL_162:
              TranslatedString = v30;
              goto LABEL_21;
            }
          }
        }
LABEL_200:
        v74 = -2147216616;
      }
      else
      {
        v154 = 0;
        v74 = -2147024882;
      }
LABEL_113:
      TranslatedString = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v74, (unsigned int)v6, a1 + 64);
      goto LABEL_114;
    case 25:
      rclsid.Data1 = 0;
      v113 = TaskXmlReader::LoadValue((TaskXmlReader *)a1, &rclsid.Data1);
      TranslatedString = v113;
      if ( v113 < 0 )
        TranslatedString = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v113, (unsigned int)v6, a1 + 64);
      v152 = (unsigned int *)(a1 + 64);
      if ( !*(_BYTE *)(a1 + 40) )
        goto LABEL_21;
      v86 = TaskXmlWriter::ElementInt(*(_QWORD *)(a1 + 16), (unsigned int)v6, rclsid.Data1);
      goto LABEL_135;
    default:
      v47 = (unsigned int)v6;
      v48 = 2147750678LL;
      goto LABEL_73;
  }
}

```

## disassembly

```asm
0x180015f60  mov     [rsp-8+arg_18], rbx
0x180015f65  push    rbp
0x180015f66  push    rsi
0x180015f67  push    rdi
0x180015f68  push    r12
0x180015f6a  push    r13
0x180015f6c  push    r14
0x180015f6e  push    r15
0x180015f70  lea     rbp, [rsp-10h]
0x180015f75  sub     rsp, 110h
0x180015f7c  mov     rax, cs:__security_cookie
0x180015f83  xor     rax, rsp
0x180015f86  mov     [rbp+40h+var_40], rax
0x180015f8a  movzx   r15d, r9b
0x180015f8e  mov     [rsp+140h+var_100], r9b
0x180015f93  movsxd  r14, r8d
0x180015f96  mov     r13, rdx
0x180015f99  mov     rsi, rcx
0x180015f9c  mov     rax, [rbp+40h+arg_20]
0x180015fa0  mov     [rbp+40h+var_A0], rax
0x180015fa4  mov     [rsp+140h+var_F0], 0
0x180015fa9  lea     rcx, [rsp+140h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180015fae  call    cs:__imp_GetSystemTimeAsFileTime
0x180015fb4  xor     r12d, r12d
0x180015fb7  mov     [rsp+140h+var_E0], r12
0x180015fbc  mov     [rsp+140h+var_D8], r12d
0x180015fc1  mov     [rsp+140h+var_D4], r12w
0x180015fc7  mov     [rbp+40h+Block], r12
0x180015fcb  mov     byte ptr [rsi+458h], 1
0x180015fd2  mov     r8d, [rsi+45Ch]
0x180015fd9  lea     rdi, __ImageBase
0x180015fe0  cmp     r8d, 10006h
0x180015fe7  jnz     loc_180016828
0x180015fed  movzx   eax, r8w; jumptable 0000000180016844 cases 65538-65541
0x180015ff1  mov     rdx, r14
0x180015ff4  shl     rdx, 7
0x180015ff8  add     rdx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[rdi+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180016000  mov     ecx, [rdx+1Ch]
0x180016003  cmp     ecx, 1Ah
0x180016006  jnz     loc_180016D13
0x18001600c  mov     ebx, r12d
0x18001600f  cmp     r8d, 10006h
0x180016016  jnz     loc_180016882
0x18001601c  movzx   eax, r8w; jumptable 00000001800168A1 cases 65538-65541
0x180016020  mov     rdx, r14
0x180016023  shl     rdx, 7
0x180016027  add     rdx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[rdi+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x18001602f  movsxd  rdi, dword ptr [rdx+1Ch]
0x180016033  cmp     edi, 7
0x180016036  jz      short loc_1800160A5; jumptable 0000000180016064 cases 1,2,6
0x180016038  cmp     edi, 14h
0x18001603b  jz      loc_1800161CB
0x180016041  cmp     edi, 8
0x180016044  jz      loc_180016205
0x18001604a  cmp     edi, 1Ah; switch 27 cases
0x18001604d  ja      def_180016064; jumptable 0000000180016064 default case, cases 7,8,20
0x180016053  lea     rdx, __ImageBase
0x18001605a  mov     ecx, ds:(jpt_180016064 - 180000000h)[rdx+rdi*4]
0x180016061  add     rcx, rdx
0x180016064  jmp     rcx; switch jump
0x180016066  lea     r12, [rsi+40h]; jumptable 0000000180016064 case 4
0x18001606a  mov     rdx, r12; struct XmlParserTempString *
0x18001606d  mov     rcx, rsi; this
0x180016070  call    ?LoadRawValue@TaskXmlReader@@AEAAJAEAUXmlParserTempString@@@Z; TaskXmlReader::LoadRawValue(XmlParserTempString &)
0x180016075  mov     r15d, eax
0x180016078  test    eax, eax
0x18001607a  jns     loc_180016A15
0x180016080  test    r14d, r14d
0x180016083  jz      loc_18001650A
0x180016089  mov     edx, r14d
0x18001608c  lea     rcx, [rsi+45Ch]
0x180016093  call    ?GetEntry@Schema@@AEBAAEBUSchemaEntry@@W4TaskXmlNodeId@@@Z; Schema::GetEntry(TaskXmlNodeId)
0x180016098  mov     r8, [rax+8]
0x18001609c  mov     r9d, [rax+10h]
0x1800160a0  jmp     loc_180016510
0x1800160a5  test    byte ptr [rsi+452h], 1; jumptable 0000000180016064 cases 1,2,6
0x1800160ac  jnz     loc_1800175E5
0x1800160b2  mov     [rsi+40h], ebx
0x1800160b5  mov     [rsi+48h], rbx
0x1800160b9  and     byte ptr [rsi+452h], 0FCh
0x1800160c0  xor     eax, eax
0x1800160c2  mov     [rsi+50h], ax
0x1800160c6  cmp     [rsp+140h+var_100], al
0x1800160ca  jz      loc_18001647D
0x1800160d0  cmp     edi, 2
0x1800160d3  jz      loc_180016244
0x1800160d9  cmp     edi, 7
0x1800160dc  jz      loc_180016244
0x1800160e2  cmp     edi, 6
0x1800160e5  jnz     short loc_1800160F1
0x1800160e7  cmp     dword ptr [rsi+40h], 0
0x1800160eb  jz      loc_180016B02
0x1800160f1  lea     r11, [rsi+40h]
0x1800160f5  mov     [rbp+40h+var_C0], r11
0x1800160f9  cmp     byte ptr [rsi+28h], 0
0x1800160fd  jnz     loc_1800175F4
0x180016103  mov     byte ptr [rsi+458h], 0
0x18001610a  test    ebx, ebx
0x18001610c  jns     short loc_180016146
0x18001610e  mov     rcx, [rbp+40h+Block]; Block
0x180016112  test    rcx, rcx
0x180016115  jz      short loc_18001611D
0x180016117  call    cs:__imp_free
0x18001611d  mov     eax, ebx
0x18001611f  mov     rcx, [rbp+40h+var_40]
0x180016123  xor     rcx, rsp; StackCookie
0x180016126  call    __security_check_cookie
0x18001612b  mov     rbx, [rsp+140h+arg_18]
0x180016133  add     rsp, 110h
0x18001613a  pop     r15
0x18001613c  pop     r14
0x18001613e  pop     r13
0x180016140  pop     r12
0x180016142  pop     rdi
0x180016143  pop     rsi
0x180016144  pop     rbp
0x180016145  retn
0x180016146  test    r13, r13
0x180016149  jz      short loc_18001610E
0x18001614b  lea     rdx, [rsi+45Ch]
0x180016152  mov     rax, [r13+0]
0x180016156  mov     rdi, [rbp+40h+var_A0]
0x18001615a  movzx   ecx, byte ptr [rdi]
0x18001615d  mov     byte ptr [rsp+140h+var_120], cl
0x180016161  lea     r9, [rsp+140h+var_F0]
0x180016166  mov     r8d, r14d
0x180016169  mov     rcx, r13
0x18001616c  mov     rax, [rax+8]
0x180016170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016175  mov     ebx, eax
0x180016177  mov     byte ptr [rdi], 1
0x18001617a  test    eax, eax
0x18001617c  jns     short loc_18001610E
0x18001617e  mov     rax, [r13+0]
0x180016182  mov     rcx, r13
0x180016185  mov     rax, [rax+18h]
0x180016189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001618e  test    eax, eax
0x180016190  jz      loc_1800176ED
0x180016196  mov     rax, [r13+0]
0x18001619a  mov     rcx, r13
0x18001619d  mov     rax, [rax+18h]
0x1800161a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161a6  mov     r8d, eax
0x1800161a9  lea     r9, [rsi+40h]
0x1800161ad  mov     edx, ebx
0x1800161af  mov     rcx, rsi
0x1800161b2  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJW4TaskXmlNodeId@@AEAUXmlParserTempString@@@Z; TaskXmlReader::SetErrorInfo(long,TaskXmlNodeId,XmlParserTempString &)
0x1800161b7  mov     ebx, eax
0x1800161b9  mov     rcx, [rbp+40h+Block]
0x1800161bd  test    rcx, rcx
0x1800161c0  jz      loc_18001611D
0x1800161c6  jmp     loc_180016117
0x1800161cb  mov     dword ptr [rsp+140h+lpsz], 10006h
0x1800161d3  lea     rdx, [rsp+140h+lpsz]; enum Schema::Version *
0x1800161d8  mov     rcx, rsi; this
0x1800161db  call    ?LoadValue@TaskXmlReader@@AEAAJAEAW4Version@Schema@@@Z; TaskXmlReader::LoadValue(Schema::Version &)
0x1800161e0  mov     ebx, eax
0x1800161e2  test    eax, eax
0x1800161e4  js      loc_1800175CD
0x1800161ea  mov     eax, dword ptr [rsp+140h+lpsz]
0x1800161ee  mov     [rsi+45Ch], eax
0x1800161f4  mov     [rsp+140h+rclsid.Data1], eax
0x1800161f8  lea     rax, [rsi+40h]
0x1800161fc  mov     [rbp+40h+var_C0], rax
0x180016200  jmp     loc_180016103
0x180016205  lea     rdx, [rsi+40h]; struct XmlParserTempString *
0x180016209  mov     rcx, rsi; this
0x18001620c  call    ?LoadRawValue@TaskXmlReader@@AEAAJAEAUXmlParserTempString@@@Z; TaskXmlReader::LoadRawValue(XmlParserTempString &)
0x180016211  mov     r15d, eax
0x180016214  test    eax, eax
0x180016216  js      short loc_180016291
0x180016218  mov     eax, [rsi+40h]
0x18001621b  cmp     eax, 5
0x18001621e  jnz     short loc_180016267
0x180016220  mov     r8d, eax; MaxCount
0x180016223  lea     rdx, aFalse; "false"
0x18001622a  mov     rcx, [rsi+48h]; String1
0x18001622e  call    wcsncmp_0
0x180016233  test    eax, eax
0x180016235  jnz     short loc_18001628B
0x180016237  xor     r8b, r8b
0x18001623a  mov     byte ptr [rsp+140h+rclsid.Data1], r8b
0x18001623f  mov     ebx, r12d
0x180016242  jmp     short loc_1800162AB
0x180016244  cmp     dword ptr [rsi+40h], 0
0x180016248  jnz     loc_1800160E2
0x18001624e  lea     r9, [rsi+40h]
0x180016252  mov     r8d, r14d
0x180016255  mov     edx, 80041318h
0x18001625a  mov     rcx, rsi
0x18001625d  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJW4TaskXmlNodeId@@AEAUXmlParserTempString@@@Z; TaskXmlReader::SetErrorInfo(long,TaskXmlNodeId,XmlParserTempString &)
0x180016262  jmp     loc_180016A59
0x180016267  cmp     eax, 4
0x18001626a  jnz     loc_18001711E
0x180016270  mov     r8d, eax; MaxCount
0x180016273  lea     rdx, aTrue; "true"
0x18001627a  mov     rcx, [rsi+48h]; String1
0x18001627e  call    wcsncmp_0
0x180016283  test    eax, eax
0x180016285  jz      loc_1800170EA
0x18001628b  mov     r15d, 80041318h
0x180016291  lea     r9, [rsi+40h]
0x180016295  mov     r8d, r14d
0x180016298  mov     edx, r15d
0x18001629b  mov     rcx, rsi
0x18001629e  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJW4TaskXmlNodeId@@AEAUXmlParserTempString@@@Z; TaskXmlReader::SetErrorInfo(long,TaskXmlNodeId,XmlParserTempString &)
0x1800162a3  mov     ebx, eax
0x1800162a5  movzx   r8d, byte ptr [rsp+140h+rclsid.Data1]
0x1800162ab  lea     rax, [rsi+40h]
0x1800162af  mov     [rbp+40h+var_C0], rax
0x1800162b3  cmp     byte ptr [rsi+28h], 0
0x1800162b7  jz      loc_180016103
0x1800162bd  mov     edx, r14d
0x1800162c0  mov     rcx, [rsi+10h]
0x1800162c4  call    ?ElementBool@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@_N@Z; TaskXmlWriter::ElementBool(TaskXmlNodeId,bool)
0x1800162c9  mov     ebx, eax
0x1800162cb  test    eax, eax
0x1800162cd  jmp     loc_1800172BD
0x1800162d2  lea     rdx, [rsi+40h]; jumptable 0000000180016064 case 3
0x1800162d6  mov     rcx, rsi; this
0x1800162d9  call    ?LoadRawValue@TaskXmlReader@@AEAAJAEAUXmlParserTempString@@@Z; TaskXmlReader::LoadRawValue(XmlParserTempString &)
0x1800162de  mov     r15d, eax
0x1800162e1  test    eax, eax
0x1800162e3  js      loc_18001636B
0x1800162e9  mov     [rsp+140h+lpsz], r12
0x1800162ee  mov     [rsp+140h+var_108], r12d
0x1800162f3  mov     [rsp+140h+var_104], r12w
0x1800162f9  mov     edx, [rsi+40h]; unsigned __int64
0x1800162fc  lea     r8, [rsp+140h+lpsz]; struct TSTimePeriod *
0x180016301  mov     rcx, [rsi+48h]; unsigned __int16 *
0x180016305  call    ?ParseTimePeriod@TSParser@@SAJPEBG_KAEAVTSTimePeriod@@@Z; TSParser::ParseTimePeriod(ushort const *,unsigned __int64,TSTimePeriod &)
0x18001630a  test    eax, eax
0x18001630c  js      short loc_180016365
0x18001630e  movzx   eax, word ptr [rsp+140h+lpsz]
0x180016313  lea     ecx, [rax+rax*2]
0x180016316  movzx   eax, word ptr [rsp+140h+lpsz+2]
0x18001631b  lea     ecx, [rax+rcx*4]
0x18001631e  test    ecx, ecx
0x180016320  jnz     short loc_180016365
0x180016322  movzx   eax, word ptr [rsp+140h+lpsz+4]
0x180016327  imul    ecx, eax, 7
0x18001632a  movzx   eax, word ptr [rsp+140h+lpsz+6]
0x18001632f  add     ecx, eax
0x180016331  lea     ecx, [rcx+rcx*2]
0x180016334  movzx   eax, word ptr [rsp+140h+var_108]
0x180016339  lea     ecx, [rax+rcx*8]
0x18001633c  imul    edx, ecx, 3Ch ; '<'
0x18001633f  movzx   eax, word ptr [rsp+140h+var_108+2]
0x180016344  add     edx, eax
0x180016346  imul    edx, 3Ch ; '<'
0x180016349  movzx   eax, [rsp+140h+var_104]
0x18001634e  add     edx, eax
0x180016350  movsxd  rax, edx
0x180016353  mov     ecx, 0FFFFFFFFh
0x180016358  cmp     rax, rcx
0x18001635b  jbe     loc_180016697
0x180016361  mov     [rsp+140h+rclsid.Data1], ecx
0x180016365  mov     r15d, 80041318h
0x18001636b  test    r14d, r14d
0x18001636e  jnz     loc_18001667B
0x180016374  mov     r8, r12; unsigned __int16 *
0x180016377  mov     r9d, r12d; unsigned int
0x18001637a  mov     eax, [rsi+40h]
0x18001637d  mov     [rsp+140h+var_118], eax; unsigned int
0x180016381  mov     rax, [rsi+48h]
0x180016385  mov     [rsp+140h+var_120], rax; unsigned __int16 *
0x18001638a  mov     edx, r15d; int
0x18001638d  mov     rcx, rsi; this
0x180016390  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJPEBGK0K@Z; TaskXmlReader::SetErrorInfo(long,ushort const *,ulong,ushort const *,ulong)
0x180016395  mov     ebx, eax
0x180016397  lea     r8, [rsi+40h]
0x18001639b  mov     [rbp+40h+var_C0], r8
0x18001639f  cmp     byte ptr [rsi+28h], 0
0x1800163a3  jz      loc_180016103
0x1800163a9  mov     rdi, [rsi+10h]
0x1800163ad  mov     eax, [rdi+98h]
0x1800163b3  test    eax, eax
0x1800163b5  jnz     loc_1800172C8
0x1800163bb  mov     edx, [rdi]
0x1800163bd  cmp     edx, 10006h
0x1800163c3  jnz     loc_180016E87
0x1800163c9  lea     r15, __ImageBase
0x1800163d0  movzx   eax, dx; jumptable 0000000180016EAA cases 65538-65541
0x1800163d3  mov     rcx, r14
0x1800163d6  shl     rcx, 7
0x1800163da  mov     rdx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r15+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x1800163e2  add     rdx, rcx; struct IErrorInfo *
0x1800163e5  mov     eax, [rdx]
0x1800163e7  test    eax, eax
0x1800163e9  jz      loc_18001710E
0x1800163ef  mov     rcx, [rdi+10h]
0x1800163f3  test    rcx, rcx
0x1800163f6  jz      loc_1800172D5
0x1800163fc  mov     r12, [r8+8]
0x180016400  mov     rax, [rcx]
0x180016403  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x18001640a  mov     r8, [rdx+8]
0x18001640e  lea     rdx, Src
0x180016415  mov     rax, [rax+0D8h]
  ... truncated ...
```
