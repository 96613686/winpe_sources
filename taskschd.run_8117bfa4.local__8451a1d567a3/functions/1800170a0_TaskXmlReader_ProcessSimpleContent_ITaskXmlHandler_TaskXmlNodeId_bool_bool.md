# TaskXmlReader::ProcessSimpleContent(ITaskXmlHandler *,TaskXmlNodeId,bool,bool &)

- ea: `0x1800170a0`
- end: `0x180018931`
- name: `?ProcessSimpleContent@TaskXmlReader@@AEAAJPEAUITaskXmlHandler@@W4TaskXmlNodeId@@_NAEA_N@Z`
- size: `6289`
- prototype: ``
- caller_count: `2`
- callee_count: `40`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180019730`
- `0x180019b50`

## callees

- `0x180002554`
- `0x180003a30`
- `0x180003ea0`
- `0x180007e90`
- `0x180011d0c`
- `0x180016900`
- `0x180016930`
- `0x1800169e0`
- `0x1800170a0`
- `0x180018940`
- `0x180019228`
- `0x18001aec0`
- `0x18001af18`
- `0x18001b340`
- `0x18001d650`
- `0x180022c60`
- `0x180024300`
- `0x18002a6f0`
- `0x180033250`
- `0x180033438`
- `0x180035620`
- `0x1800370e8`
- `0x1800372f0`
- `0x180037c2c`
- `0x18003b514`
- `0x18003b74c`
- `0x18003bf68`
- `0x18003c990`
- `0x18003d034`
- `0x18004ee30`
- `0x18004ee90`
- `0x18004eee0`
- `0x18004f180`
- `0x18004f1fc`
- `0x18004f280`
- `0x18004f55c`
- `0x18004f638`
- `0x180052617`
- `0x180052640`
- `0x180058010`

## import_xrefs

- `msvcrt!free` at `0x180017261`
- `msvcrt!free` at `0x180017af5`
- `msvcrt!free` at `0x18001827d`
- `msvcrt!free` at `0x1800182cf`
- `msvcrt!free` at `0x1800182e5`
- `msvcrt!free` at `0x180018306`
- `msvcrt!free` at `0x180018323`
- `msvcrt!free` at `0x180017261`
- `msvcrt!free` at `0x180017af5`
- `msvcrt!free` at `0x18001827d`
- `msvcrt!free` at `0x1800182cf`
- `msvcrt!free` at `0x1800182e5`
- `msvcrt!free` at `0x180018306`
- `msvcrt!free` at `0x180018323`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800170ee`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800170ee`
- `OLEAUT32!__imp_SysFreeString` at `0x1800186b9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800186b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800178c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800178c7`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180017d55`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180018481`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180017d55`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180018481`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180017891`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180017891`

## string_xrefs

- `0x180017964`: `LeastPrivilege`
- `0x18001824f`: `InteractiveToken`
- `0x180017e14`: `InteractiveTokenOrPassword`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TaskXmlReader::ProcessSimpleContent(__int64 a1, __int64 a2, int a3, char a4, _BYTE *a5)
{
  __int64 v6; // r14
  int v9; // r8d
  __int64 *v10; // rdx
  int v11; // ecx
  signed int v12; // ebx
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
  int v64; // r15d
  __int64 v65; // rdx
  __int64 v66; // rax
  int *v67; // rdi
  int v68; // r15d
  __int64 Data1; // r8
  HRESULT v70; // ebx
  HRESULT v71; // eax
  unsigned int *v72; // r12
  int v73; // eax
  unsigned int v74; // r11d
  __int64 v75; // rax
  const unsigned __int16 *v76; // r8
  unsigned int v77; // r9d
  int v78; // eax
  const unsigned __int64 *v79; // r9
  int v80; // edx
  unsigned __int64 v81; // r8
  const unsigned __int64 near *v82; // r9
  __int64 v83; // r10
  unsigned int *v84; // rdi
  int v85; // eax
  bool v86; // sf
  void *v87; // rbx
  __int64 v88; // r10
  unsigned int v89; // r9d
  __int64 i; // rdx
  __int16 v91; // cx
  char v92; // cl
  unsigned __int64 v93; // r8
  int v94; // eax
  int v95; // eax
  __int64 v96; // rdx
  const unsigned __int16 *v97; // r8
  unsigned int v98; // r9d
  int v99; // r15d
  int v100; // eax
  const OLECHAR *NullTerminated; // rax
  __int64 Entry; // rax
  int v103; // eax
  int v104; // ecx
  int v105; // ecx
  const unsigned __int16 *v106; // r8
  unsigned int v107; // r9d
  __int64 v108; // rax
  int v109; // eax
  int v110; // eax
  const unsigned __int64 near *v111; // r9
  __int64 v112; // r10
  unsigned __int64 v113; // r9
  const unsigned __int64 near *v114; // r10
  __int64 v115; // r11
  int DayOfMonth; // eax
  __int64 v117; // rcx
  int v118; // eax
  __int64 v119; // rax
  int v120; // eax
  unsigned __int16 *v121; // rax
  int ProcessTokenSidType; // eax
  int Privilege; // eax
  int Week; // eax
  __int64 v125; // rcx
  int v126; // eax
  const unsigned __int16 *v127; // r12
  unsigned int v128; // r15d
  OLECHAR *v129; // rbx
  int v130; // edi
  LPOLESTR v131; // rdi
  __int64 v132; // r11
  int v133; // [rsp+20h] [rbp-E0h]
  LPOLESTR lpsz; // [rsp+30h] [rbp-D0h] BYREF
  int v135; // [rsp+38h] [rbp-C8h]
  unsigned __int16 v136; // [rsp+3Ch] [rbp-C4h]
  char v137; // [rsp+40h] [rbp-C0h]
  _BYTE v138[8]; // [rsp+50h] [rbp-B0h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-A8h] BYREF
  LPOLESTR v140; // [rsp+60h] [rbp-A0h]
  int v141; // [rsp+68h] [rbp-98h]
  unsigned __int16 v142; // [rsp+6Ch] [rbp-94h]
  IID rclsid; // [rsp+70h] [rbp-90h] BYREF
  unsigned int *v144; // [rsp+80h] [rbp-80h]
  void *Block; // [rsp+88h] [rbp-78h]
  unsigned int v146; // [rsp+90h] [rbp-70h]
  _BYTE *v147; // [rsp+A0h] [rbp-60h]
  OLECHAR sz[40]; // [rsp+B0h] [rbp-50h] BYREF

  v137 = a4;
  v6 = a3;
  v147 = a5;
  v138[0] = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v140 = 0;
  v141 = 0;
  v142 = 0;
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
        v79 = 0;
        break;
      case 65538:
      case 65539:
      case 65540:
      case 65541:
        goto LABEL_2;
      default:
        goto LABEL_191;
    }
    while ( v79 < (&Schema::schemaEntriesCount)[(unsigned __int16)v9] )
    {
      v10 = (__int64 *)(*((_QWORD *)&_ImageBase + (unsigned __int16)v9 + 48103) + ((_QWORD)v79 << 7));
      if ( *(_DWORD *)v10 == (_DWORD)v6 )
        goto LABEL_3;
      v79 = (const unsigned __int64 *)((char *)v79 + 1);
    }
LABEL_191:
    v10 = &qword_180072DF0;
  }
LABEL_3:
  v11 = *((_DWORD *)v10 + 7);
  if ( v11 == 26 || !v11 || (v104 = v11 - 1) == 0 || (v105 = v104 - 8) == 0 || v105 == 2 || !a4 )
  {
    v12 = 0;
    if ( v9 == 65542 )
    {
LABEL_5:
      v13 = (__int64 *)&(&Schema::schemaEntries)[(unsigned __int16)v9][16 * v6];
    }
    else
    {
      v80 = *(_DWORD *)(a1 + 1116);
      switch ( v9 )
      {
        case 65536:
        case 65537:
          v81 = 0;
          v82 = (&Schema::schemaEntriesCount)[(unsigned __int16)v80];
          v83 = 8LL * (unsigned __int16)v80 + 384824;
          break;
        case 65538:
        case 65539:
        case 65540:
        case 65541:
          goto LABEL_5;
        default:
          goto LABEL_192;
      }
      while ( v81 < (unsigned __int64)v82 )
      {
        v13 = (__int64 *)(*(_QWORD *)((char *)&_ImageBase + v83) + (v81 << 7));
        if ( *(_DWORD *)v13 == (_DWORD)v6 )
          goto LABEL_6;
        ++v81;
      }
LABEL_192:
      v13 = &qword_180072DF0;
    }
LABEL_6:
    v14 = *((_DWORD *)v13 + 7);
    if ( v14 == 7 )
    {
LABEL_13:
      if ( (*(_BYTE *)(a1 + 1106) & 1) != 0 )
        SysFreeString(*(BSTR *)(a1 + 72));
      *(_DWORD *)(a1 + 64) = 0;
      *(_QWORD *)(a1 + 72) = 0;
      *(_BYTE *)(a1 + 1106) &= 0xFCu;
      *(_WORD *)(a1 + 80) = 0;
      if ( v137
        || (RawValue = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64)),
            v12 = RawValue,
            RawValue >= 0) )
      {
        if ( v14 != 2 && v14 != 7 || *(_DWORD *)(a1 + 64) )
        {
          if ( v14 == 6 && !*(_DWORD *)(a1 + 64) )
          {
            if ( (_DWORD)v6 )
            {
              Entry = Schema::GetEntry(a1 + 1116, (unsigned int)v6);
              v97 = *(const unsigned __int16 **)(Entry + 8);
              v98 = *(_DWORD *)(Entry + 16);
            }
            else
            {
              v97 = 0;
              v98 = 0;
            }
            v12 = TaskXmlReader::SetErrorInfo(
                    (TaskXmlReader *)a1,
                    -2147216616,
                    v97,
                    v98,
                    *(const unsigned __int16 **)(a1 + 72),
                    0);
          }
          else
          {
            v20 = (unsigned int *)(a1 + 64);
            v144 = (unsigned int *)(a1 + 64);
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
                  v127 = *(const unsigned __int16 **)(a1 + 72);
                  if ( !v127 || (v128 = *v20) == 0 )
                  {
                    v12 = TaskXmlWriter::Element(*(_QWORD *)(a1 + 16), (unsigned int)v6, &Src);
                    if ( v12 >= 0 )
                      break;
                    goto LABEL_29;
                  }
                  v129 = (OLECHAR *)operator new(saturated_mul(v128 + 1, 2u));
                  lpsz = v129;
                  v130 = StringCchCopyNW(v129, v128 + 1, v127, v128);
                  if ( v130 < 0 )
                  {
                    if ( v129 )
                      free(v129);
                    if ( Block )
                      free(Block);
                    return (unsigned int)v130;
                  }
                  v12 = TaskXmlReader::LoadTranslatedString(&lpsz);
                  if ( v12 < 0 )
                  {
                    if ( lpsz )
                      free(lpsz);
                    goto LABEL_29;
                  }
                  v131 = lpsz;
                  v12 = TaskXmlWriter::Element(*(_QWORD *)(a1 + 16), (unsigned int)v6, lpsz);
                  if ( v12 < 0 )
                  {
                    if ( v131 )
                      free(v131);
                    goto LABEL_29;
                  }
                  if ( v131 )
                    free(v131);
                  break;
                default:
                  if ( *(_DWORD *)(Schema::GetEntry(a1 + 1116, (unsigned int)v6) + 24) == 2 )
                    goto LABEL_322;
                  v12 = TaskXmlWriter::Element(*(_QWORD *)(a1 + 16), (unsigned int)v6, *(_QWORD *)(v132 + 8));
                  v32 = v12 < 0;
                  goto LABEL_282;
              }
LABEL_263:
              *(_BYTE *)(a1 + 1112) = 0;
              goto LABEL_25;
            }
          }
          goto LABEL_21;
        }
        v30 = TaskXmlReader::SetErrorInfo(a1, 2147750680LL, (unsigned int)v6, a1 + 64);
      }
      else
      {
        v47 = (unsigned int)v6;
        v48 = (unsigned int)RawValue;
LABEL_73:
        v30 = TaskXmlReader::SetErrorInfo(a1, v48, v47);
      }
      goto LABEL_162;
    }
    if ( v14 == 20 )
    {
      LODWORD(lpsz) = 65542;
      Value = TaskXmlReader::LoadValue((TaskXmlReader *)a1, (enum Schema::Version *)&lpsz);
      v12 = Value;
      if ( Value < 0 )
        v12 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)Value, (unsigned int)v6, a1 + 64);
      v26 = (unsigned int)lpsz;
      *(_DWORD *)(a1 + 1116) = (_DWORD)lpsz;
      rclsid.Data1 = v26;
      v144 = (unsigned int *)(a1 + 64);
      goto LABEL_21;
    }
    if ( v14 != 8 )
    {
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
          v135 = 0;
          v136 = 0;
          if ( (int)TSParser::ParseTimePeriod(
                      *(const unsigned __int16 **)(a1 + 72),
                      *(unsigned int *)(a1 + 64),
                      (struct TSTimePeriod *)&lpsz) < 0
            || WORD1(lpsz) + 12 * (unsigned __int16)lpsz )
          {
            goto LABEL_53;
          }
          if ( (unsigned __int64)(v136
                                + 60
                                * (HIWORD(v135) + 60 * ((unsigned __int16)v135 + 24 * (HIWORD(lpsz) + 7 * WORD2(lpsz))))) <= 0xFFFFFFFF )
          {
            rclsid.Data1 = v136
                         + 60 * (HIWORD(v135) + 60 * ((unsigned __int16)v135 + 24 * (HIWORD(lpsz) + 7 * WORD2(lpsz))));
            v12 = 0;
          }
          else
          {
            rclsid.Data1 = -1;
LABEL_53:
            v33 = -2147216616;
LABEL_54:
            if ( (_DWORD)v6 )
            {
              v66 = Schema::GetEntry(a1 + 1116, (unsigned int)v6);
              v34 = *(const unsigned __int16 **)(v66 + 8);
              v35 = *(_DWORD *)(v66 + 16);
            }
            else
            {
              v34 = 0;
              v35 = 0;
            }
            v12 = TaskXmlReader::SetErrorInfo(
                    (TaskXmlReader *)a1,
                    v33,
                    v34,
                    v35,
                    *(const unsigned __int16 **)(a1 + 72),
                    *(_DWORD *)(a1 + 64));
          }
          v144 = (unsigned int *)(a1 + 64);
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_21;
          v36 = *(int **)(a1 + 16);
          v37 = v36[38];
          if ( v37 )
          {
            v36[38] = v37 + 1;
LABEL_68:
            v12 = 1;
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
                v113 = 0;
                v114 = (&Schema::schemaEntriesCount)[(unsigned __int16)v38];
                v115 = 8LL * (unsigned __int16)v38 + 384824;
                break;
              case 65538:
              case 65539:
              case 65540:
              case 65541:
                goto LABEL_60;
              default:
                goto LABEL_250;
            }
            while ( v113 < (unsigned __int64)v114 )
            {
              v39 = (struct IErrorInfo *)(*(_QWORD *)((char *)&_ImageBase + v115) + (v113 << 7));
              lpVtbl = (int)v39->lpVtbl;
              if ( LODWORD(v39->lpVtbl) == (_DWORD)v6 )
                goto LABEL_62;
              ++v113;
            }
LABEL_250:
            v39 = (struct IErrorInfo *)&qword_180072DF0;
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
            v12 = v43;
            if ( v43 < 0 )
              goto LABEL_22;
            if ( !v43 )
            {
              if ( v42 )
              {
                v44 = _com_ptr_t<_com_IIID<IXmlWriter,&__s_GUID const _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030>>::operator->(v36 + 4);
                v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v44 + 224LL))(v44, v42);
                if ( v12 < 0 )
                  goto LABEL_22;
              }
            }
            goto LABEL_68;
          }
          v12 = 1;
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
          if ( (int)TSParser::ParseDateTime(*(const unsigned __int16 **)(a1 + 72), *v15, (struct TSTime *)v138) < 0 )
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
            v12 = TaskXmlReader::SetErrorInfo(
                    (TaskXmlReader *)a1,
                    v16,
                    v18,
                    v19,
                    *(const unsigned __int16 **)(a1 + 72),
                    *v15);
          }
          v144 = (unsigned int *)(a1 + 64);
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_21;
          v36 = *(int **)(a1 + 16);
          v53 = v36[38];
          if ( v53 )
          {
            v36[38] = v53 + 1;
LABEL_93:
            v12 = 1;
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
                v111 = (&Schema::schemaEntriesCount)[(unsigned __int16)v54];
                v112 = 8LL * (unsigned __int16)v54 + 384824;
                break;
              case 65538:
              case 65539:
              case 65540:
              case 65541:
                goto LABEL_84;
              default:
                goto LABEL_247;
            }
            while ( v52 < (struct IErrorInfo *)v111 )
            {
              v55 = (__int64 *)(*(_QWORD *)((char *)&_ImageBase + v112) + ((_QWORD)v52 << 7));
              v56 = *(_DWORD *)v55;
              if ( *(_DWORD *)v55 == (_DWORD)v6 )
                goto LABEL_86;
              v52 = (struct IErrorInfo *)((char *)v52 + 1);
            }
LABEL_247:
            v55 = &qword_180072DF0;
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
            v12 = v59;
            if ( v59 < 0 )
              goto LABEL_22;
            if ( !v59 && v58 )
            {
              v61 = *((_QWORD *)v36 + 2);
              if ( !v61 )
                _com_raise_error(-2147467261, v60);
              v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v61 + 224LL))(v61, v58);
              if ( v12 < 0 )
                goto LABEL_22;
            }
            goto LABEL_93;
          }
          v12 = 1;
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
            v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v63 + 120LL))(v63);
          }
LABEL_139:
          if ( v12 < 0 )
            goto LABEL_22;
          goto LABEL_263;
        case 5:
          LOWORD(rclsid.Data1) = 0;
          v95 = TaskXmlReader::LoadValue((TaskXmlReader *)a1, (unsigned __int16 *)&rclsid);
          v12 = v95;
          if ( v95 >= 0 )
            goto LABEL_165;
          v96 = (unsigned int)v95;
          goto LABEL_300;
        case 9:
          if ( a4 )
            goto LABEL_170;
          LODWORD(lpsz) = 0;
          v119 = _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(a1 + 56);
          v120 = (*(__int64 (__fastcall **)(__int64, LPOLESTR *))(*(_QWORD *)v119 + 48LL))(v119, &lpsz);
          v12 = v120;
          if ( v120 >= 0 )
          {
            if ( v120 || (_DWORD)lpsz != 15 )
              v12 = TaskXmlReader::SetErrorInfo(a1, 2147750680LL, (unsigned int)v6, a1 + 64);
LABEL_170:
            v144 = 0;
            if ( *(_BYTE *)(a1 + 40) )
            {
              v31 = TaskXmlWriter::Element(*(_QWORD *)(a1 + 16), (unsigned int)v6, 0);
              goto LABEL_47;
            }
            goto LABEL_21;
          }
          v12 = TaskXmlReader::SetErrorInfoXmlLite((TaskXmlReader *)a1, v120);
          v21 = Block;
          if ( !Block )
            return (unsigned int)v12;
          goto LABEL_23;
        case 10:
          v70 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
          if ( v70 < 0
            || (NullTerminated = XmlParserTempString::GetNullTerminated((XmlParserTempString *)(a1 + 64)),
                v70 = CLSIDFromString(NullTerminated, &rclsid),
                v70 < 0)
            && (*XmlParserTempString::GetNullTerminated((XmlParserTempString *)(a1 + 64)) == 123
             || (v121 = XmlParserTempString::GetNullTerminated((XmlParserTempString *)(a1 + 64)),
                 v70 = StringCchPrintfW(sz, 0x28u, L"{%s}", v121),
                 v70 < 0)
             || (v70 = CLSIDFromString(sz, &rclsid), v70 < 0)) )
          {
            v12 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v70, (unsigned int)v6, a1 + 64);
          }
          else
          {
            v12 = 0;
          }
          v144 = (unsigned int *)(a1 + 64);
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_21;
          lpsz = 0;
          v71 = StringFromCLSID(&rclsid, &lpsz);
          v12 = v71;
          if ( v71 )
          {
            if ( v71 > 0 )
              v12 = (unsigned __int16)v71 | 0x80070000;
            goto LABEL_29;
          }
          v12 = TaskXmlWriter::Element(*(_QWORD *)(a1 + 16), (unsigned int)v6, lpsz);
          if ( v12 < 0 )
            goto LABEL_29;
          CoTaskMemFree(lpsz);
          *(_BYTE *)(a1 + 1112) = 0;
          goto LABEL_25;
        case 11:
          v84 = (unsigned int *)(a1 + 64);
          XmlParserTempString::~XmlParserTempString((XmlParserTempString *)(a1 + 64));
          if ( !a4 )
          {
            v110 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
            v12 = v110;
            if ( v110 < 0 )
              v12 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v110, (unsigned int)v6, a1 + 64);
          }
          goto LABEL_133;
        case 12:
          v94 = TaskXmlReader::LoadValue((TaskXmlReader *)a1, (unsigned __int16 *)&rclsid);
          v12 = v94;
          if ( v94 < 0 )
          {
            v96 = (unsigned int)v94;
          }
          else
          {
            if ( LOWORD(rclsid.Data1) <= 0xAu )
              goto LABEL_165;
            v96 = 2147750680LL;
          }
LABEL_300:
          v12 = TaskXmlReader::SetErrorInfo(a1, v96, (unsigned int)v6, a1 + 64);
LABEL_165:
          v144 = (unsigned int *)(a1 + 64);
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_21;
          v85 = TaskXmlWriter::ElementInt(*(_QWORD *)(a1 + 16), (unsigned int)v6, LOWORD(rclsid.Data1));
LABEL_135:
          v12 = v85;
          v86 = v85 < 0;
          goto LABEL_136;
        case 13:
          v67 = (int *)(a1 + 64);
          v68 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
          if ( v68 < 0 )
            goto LABEL_103;
          v103 = *v67;
          if ( !*v67 )
            goto LABEL_302;
          rclsid.Data1 = 0;
          if ( v103 == 3 )
          {
            if ( !wcsncmp_0(*(const wchar_t **)(a1 + 72), L"S4U", 3u) )
            {
              Data1 = 0x4000;
              goto LABEL_262;
            }
          }
          else if ( v103 == 8 )
          {
            if ( !wcsncmp_0(*(const wchar_t **)(a1 + 72), L"Password", 8u) )
            {
              Data1 = 0x40000;
              goto LABEL_262;
            }
          }
          else if ( v103 == 16 && !wcsncmp_0(*(const wchar_t **)(a1 + 72), L"InteractiveToken", 0x10u) )
          {
            Data1 = 0x10000;
            goto LABEL_262;
          }
          if ( XmlParserTempString::IsEqualTo((XmlParserTempString *)(a1 + 64), L"InteractiveTokenOrPassword", 0x1Au) )
          {
            Data1 = 0x80000;
LABEL_262:
            rclsid.Data1 = Data1;
            v12 = 0;
            goto LABEL_104;
          }
LABEL_302:
          v68 = -2147216616;
LABEL_103:
          v12 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v68, (unsigned int)v6, a1 + 64);
          Data1 = rclsid.Data1;
LABEL_104:
          v144 = (unsigned int *)(a1 + 64);
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_21;
          v31 = TaskXmlWriter::ElementLogonType(*(_QWORD *)(a1 + 16), (unsigned int)v6, Data1);
          goto LABEL_47;
        case 14:
          rclsid.Data1 = 0;
          v49 = (int *)(a1 + 64);
          v50 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
          if ( v50 < 0 )
            goto LABEL_75;
          v78 = *v49;
          if ( !*v49 )
            goto LABEL_121;
          if ( v78 == 14 )
          {
            if ( wcsncmp_0(*(const wchar_t **)(a1 + 72), L"LeastPrivilege", 0xEu) )
              goto LABEL_121;
            v51 = 0;
          }
          else
          {
            if ( v78 != 16 || wcsncmp_0(*(const wchar_t **)(a1 + 72), L"HighestAvailable", 0x10u) )
            {
LABEL_121:
              v50 = -2147216616;
LABEL_75:
              v12 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v50, (unsigned int)v6, a1 + 64);
              v51 = rclsid.Data1;
LABEL_76:
              v144 = (unsigned int *)(a1 + 64);
              if ( *(_BYTE *)(a1 + 40) && (v51 & 0x1000000) != 0 )
              {
                v31 = TaskXmlWriter::ElementRunLevel(*(_QWORD *)(a1 + 16), (unsigned int)v6, 1);
                goto LABEL_47;
              }
              goto LABEL_21;
            }
            v51 = 0x1000000;
          }
          rclsid.Data1 = v51;
          v12 = 0;
          goto LABEL_76;
        case 15:
          LOWORD(rclsid.Data1) = 0;
          Week = TaskXmlReader::LoadWeek((TaskXmlReader *)a1, (unsigned __int16 *)&rclsid);
          v12 = Week;
          if ( Week < 0 )
            v12 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)Week, (unsigned int)v6, a1 + 64);
          v144 = (unsigned int *)(a1 + 64);
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_21;
          v125 = *(_QWORD *)(a1 + 16);
          if ( LOWORD(rclsid.Data1) == 5 )
          {
            v12 = TaskXmlWriter::Element(v125, 70, L"Last");
            if ( v12 >= 0 )
              goto LABEL_21;
          }
          else
          {
            v12 = TaskXmlWriter::ElementInt(v125, 70, LOWORD(rclsid.Data1));
          }
LABEL_322:
          v32 = v12 < 0;
          goto LABEL_282;
        case 16:
          rclsid.Data1 = 0;
          v64 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
          if ( v64 < 0 )
            goto LABEL_97;
          v100 = *(_DWORD *)(a1 + 64);
          if ( v100 == 8 )
          {
            if ( !wcsncmp_0(*(const wchar_t **)(a1 + 72), L"Parallel", 8u) )
            {
              v65 = 1024;
              rclsid.Data1 = 1024;
              v12 = 0;
              goto LABEL_98;
            }
          }
          else if ( v100 == 5 )
          {
            if ( !wcsncmp_0(*(const wchar_t **)(a1 + 72), L"Queue", 5u) )
            {
              v65 = 4096;
              goto LABEL_218;
            }
          }
          else if ( v100 == 9 && !wcsncmp_0(*(const wchar_t **)(a1 + 72), L"IgnoreNew", 9u) )
          {
            v65 = 0x2000;
            rclsid.Data1 = 0x2000;
            v12 = 0;
            goto LABEL_98;
          }
          if ( XmlParserTempString::IsEqualTo((XmlParserTempString *)(a1 + 64), L"StopExisting", 0xCu) )
          {
            v65 = 2048;
LABEL_218:
            rclsid.Data1 = v65;
            v12 = 0;
            goto LABEL_98;
          }
          v64 = -2147216616;
LABEL_97:
          v12 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v64, (unsigned int)v6, a1 + 64);
          v65 = rclsid.Data1;
LABEL_98:
          v144 = (unsigned int *)(a1 + 64);
          if ( *(_BYTE *)(a1 + 40) )
          {
            v31 = TaskXmlWriter::ElementMultipleInstancesPolicy(*(_QWORD *)(a1 + 16), v65);
            goto LABEL_47;
          }
          goto LABEL_21;
        case 17:
          v126 = TaskXmlReader::SkipElement((TaskXmlReader *)a1);
          v12 = v126;
          if ( v126 < 0 )
            v12 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v126, (unsigned int)v6, a1 + 64);
          v144 = (unsigned int *)(a1 + 64);
          goto LABEL_21;
        case 18:
          LOWORD(rclsid.Data1) = 0;
          DayOfMonth = TaskXmlReader::LoadDayOfMonth((TaskXmlReader *)a1, (unsigned __int16 *)&rclsid);
          v12 = DayOfMonth;
          if ( DayOfMonth < 0 )
            v12 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)DayOfMonth, (unsigned int)v6, a1 + 64);
          v144 = (unsigned int *)(a1 + 64);
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_21;
          v117 = *(_QWORD *)(a1 + 16);
          if ( LOWORD(rclsid.Data1) == 32 )
          {
            v12 = TaskXmlWriter::Element(v117, 68, L"Last");
            if ( v12 >= 0 )
              goto LABEL_21;
          }
          else
          {
            v12 = TaskXmlWriter::ElementInt(v117, 68, LOWORD(rclsid.Data1));
          }
          v86 = v12 < 0;
LABEL_136:
          if ( !v86 )
            goto LABEL_21;
          goto LABEL_22;
        case 19:
          rclsid.Data1 = 0;
          v118 = TaskXmlReader::LoadSessionStateChange((TaskXmlReader *)a1, &rclsid.Data1);
          v12 = v118;
          if ( v118 < 0 )
            v12 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v118, (unsigned int)v6, a1 + 64);
          v144 = (unsigned int *)(a1 + 64);
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_21;
          v85 = TaskXmlWriter::ElementSessionStateChange(*(TaskXmlWriter **)(a1 + 16), LOWORD(rclsid.Data1));
          goto LABEL_135;
        case 21:
          ProcessTokenSidType = TaskXmlReader::LoadProcessTokenSidType(
                                  (TaskXmlReader *)a1,
                                  (enum JobFlags::JobFlag *)&rclsid);
          v12 = ProcessTokenSidType;
          if ( ProcessTokenSidType < 0 )
            v12 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)ProcessTokenSidType, (unsigned int)v6, a1 + 64);
          v144 = (unsigned int *)(a1 + 64);
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
          v12 = Privilege;
          if ( Privilege < 0 )
            v12 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)Privilege, (unsigned int)v6, a1 + 64);
          v144 = (unsigned int *)(a1 + 64);
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_21;
          v31 = TaskXmlWriter::Element(*(_QWORD *)(a1 + 16), 135, *(_QWORD *)(a1 + 72));
          goto LABEL_47;
        case 23:
          v84 = (unsigned int *)(a1 + 64);
          v99 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
          if ( v99 < 0 )
            goto LABEL_176;
          lpsz = 0;
          v135 = 0;
          v136 = 0;
          if ( (int)TSParser::ParseTimePeriod(*(const unsigned __int16 **)(a1 + 72), *v84, (struct TSTimePeriod *)&lpsz) < 0 )
          {
            v99 = -2147216616;
LABEL_176:
            v12 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v99, (unsigned int)v6, a1 + 64);
          }
          else
          {
            v12 = 0;
            v140 = lpsz;
            v141 = v135;
            v142 = v136;
          }
LABEL_133:
          v144 = v84;
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_21;
          v85 = TaskXmlWriter::Element(*(_QWORD *)(a1 + 16), (unsigned int)v6, *((_QWORD *)v84 + 1));
          goto LABEL_135;
        case 24:
        case 26:
          Block = 0;
          v146 = 0;
          v72 = (unsigned int *)(a1 + 64);
          v73 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
          if ( v73 < 0 )
            goto LABEL_113;
          if ( !*v72 )
            goto LABEL_235;
          if ( !*(_QWORD *)(a1 + 72) )
            goto LABEL_194;
          v146 = (*v72 & 1) + (*v72 >> 1);
          v87 = operator new(v146);
          if ( Block )
            free(Block);
          Block = v87;
          if ( v87 )
          {
            v88 = *(_QWORD *)(a1 + 72);
            if ( v88 )
            {
              v89 = *v72;
              if ( *v72 )
              {
                if ( v146 >= (*v72 & 1) + (*v72 >> 1) )
                {
                  for ( i = 0; (unsigned int)i < v89; i = (unsigned int)(i + 1) )
                  {
                    v91 = *(_WORD *)(v88 + 2 * i);
                    if ( (unsigned __int16)(v91 - 48) > 9u )
                    {
                      if ( (unsigned __int16)(v91 - 97) <= 5u )
                      {
                        v92 = v91 - 87;
                      }
                      else
                      {
                        if ( (unsigned __int16)(v91 - 65) > 5u )
                          goto LABEL_194;
                        v92 = v91 - 55;
                      }
                    }
                    else
                    {
                      v92 = v91 - 48;
                    }
                    v93 = (unsigned __int64)(unsigned int)i >> 1;
                    if ( (i & 1) != 0 )
                      *((_BYTE *)v87 + v93) |= v92;
                    else
                      *((_BYTE *)v87 + v93) = 16 * v92;
                  }
                  v146 = (v89 & 1) + (v89 >> 1);
LABEL_235:
                  v12 = 0;
LABEL_114:
                  if ( v14 != 24 || (v74 = *v72, *v72 == 16) )
                  {
                    v144 = (unsigned int *)(a1 + 64);
                    if ( *(_BYTE *)(a1 + 40) )
                    {
                      v31 = TaskXmlWriter::ElementHexString(*(_QWORD *)(a1 + 16), (unsigned int)v6, Block, v146);
                      goto LABEL_47;
                    }
                    goto LABEL_21;
                  }
                  if ( (_DWORD)v6 )
                  {
                    v75 = Schema::GetEntry(a1 + 1116, (unsigned int)v6);
                    v76 = *(const unsigned __int16 **)(v75 + 8);
                    v77 = *(_DWORD *)(v75 + 16);
                  }
                  else
                  {
                    v76 = 0;
                    v77 = 0;
                  }
                  v30 = TaskXmlReader::SetErrorInfo(
                          (TaskXmlReader *)a1,
                          -2147216616,
                          v76,
                          v77,
                          *(const unsigned __int16 **)(a1 + 72),
                          v74);
LABEL_162:
                  v12 = v30;
                  goto LABEL_21;
                }
              }
            }
LABEL_194:
            v73 = -2147216616;
          }
          else
          {
            v146 = 0;
            v73 = -2147024882;
          }
LABEL_113:
          v12 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v73, (unsigned int)v6, a1 + 64);
          goto LABEL_114;
        case 25:
          rclsid.Data1 = 0;
          v109 = TaskXmlReader::LoadValue((TaskXmlReader *)a1, &rclsid.Data1);
          v12 = v109;
          if ( v109 < 0 )
            v12 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v109, (unsigned int)v6, a1 + 64);
          v144 = (unsigned int *)(a1 + 64);
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_21;
          v85 = TaskXmlWriter::ElementInt(*(_QWORD *)(a1 + 16), (unsigned int)v6, rclsid.Data1);
          goto LABEL_135;
        default:
          v47 = (unsigned int)v6;
          v48 = 2147750678LL;
          goto LABEL_73;
      }
    }
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
            v12 = 0;
            goto LABEL_45;
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
            v12 = 0;
LABEL_45:
            v144 = (unsigned int *)(a1 + 64);
            if ( *(_BYTE *)(a1 + 40) )
            {
              v31 = TaskXmlWriter::ElementBool(*(_QWORD *)(a1 + 16), (unsigned int)v6, Data1_low);
LABEL_47:
              v12 = v31;
              v32 = v31 < 0;
LABEL_282:
              if ( v32 )
                goto LABEL_29;
            }
LABEL_21:
            *(_BYTE *)(a1 + 1112) = 0;
            if ( v12 < 0 )
              goto LABEL_22;
LABEL_25:
            if ( !a2 )
              goto LABEL_22;
            v23 = v147;
            LOBYTE(v133) = *v147;
            v12 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _BYTE *, int))(*(_QWORD *)a2 + 8LL))(
                    a2,
                    a1 + 1116,
                    (unsigned int)v6,
                    v138,
                    v133);
            *v23 = 1;
            if ( v12 >= 0 )
              goto LABEL_22;
            if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a2 + 24LL))(a2) )
            {
              v24 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 24LL))(a2);
              v12 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v12, v24, a1 + 64);
            }
            else
            {
              v12 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v12, (unsigned int)v6, a1 + 64);
            }
LABEL_29:
            v21 = Block;
            if ( !Block )
              return (unsigned int)v12;
            goto LABEL_23;
          }
          break;
      }
      v27 = -2147216616;
    }
    v12 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v27, (unsigned int)v6, a1 + 64);
    Data1_low = LOBYTE(rclsid.Data1);
    goto LABEL_45;
  }
  if ( (_DWORD)v6 )
  {
    v108 = Schema::GetEntry(a1 + 1116, (unsigned int)v6);
    v106 = *(const unsigned __int16 **)(v108 + 8);
    v107 = *(_DWORD *)(v108 + 16);
  }
  else
  {
    v106 = 0;
    v107 = 0;
  }
  v12 = TaskXmlReader::SetErrorInfo((TaskXmlReader *)a1, -2147216616, v106, v107, 0, 0);
LABEL_22:
  v21 = Block;
  if ( Block )
LABEL_23:
    free(v21);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800170a0  mov     [rsp-8+arg_18], rbx
0x1800170a5  push    rbp
0x1800170a6  push    rsi
0x1800170a7  push    rdi
0x1800170a8  push    r12
0x1800170aa  push    r13
0x1800170ac  push    r14
0x1800170ae  push    r15
0x1800170b0  lea     rbp, [rsp-10h]
0x1800170b5  sub     rsp, 110h
0x1800170bc  mov     rax, cs:__security_cookie
0x1800170c3  xor     rax, rsp
0x1800170c6  mov     [rbp+40h+var_40], rax
0x1800170ca  movzx   r15d, r9b
0x1800170ce  mov     [rsp+140h+var_100], r9b
0x1800170d3  movsxd  r14, r8d
0x1800170d6  mov     r13, rdx
0x1800170d9  mov     rsi, rcx
0x1800170dc  mov     rax, [rbp+40h+arg_20]
0x1800170e0  mov     [rbp+40h+var_A0], rax
0x1800170e4  mov     [rsp+140h+var_F0], 0
0x1800170e9  lea     rcx, [rsp+140h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800170ee  call    cs:__imp_GetSystemTimeAsFileTime
0x1800170f5  nop     dword ptr [rax+rax+00h]
0x1800170fa  xor     r12d, r12d
0x1800170fd  mov     [rsp+140h+var_E0], r12
0x180017102  mov     [rsp+140h+var_D8], r12d
0x180017107  mov     [rsp+140h+var_D4], r12w
0x18001710d  mov     [rbp+40h+Block], r12
0x180017111  mov     byte ptr [rsi+458h], 1
0x180017118  mov     r8d, [rsi+45Ch]
0x18001711f  lea     rdi, __ImageBase
0x180017126  cmp     r8d, 10006h
0x18001712d  jnz     loc_180017987
0x180017133  movzx   eax, r8w; jumptable 00000001800179A3 cases 65538-65541
0x180017137  mov     rdx, r14
0x18001713a  shl     rdx, 7
0x18001713e  add     rdx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[rdi+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180017146  mov     ecx, [rdx+1Ch]
0x180017149  cmp     ecx, 1Ah
0x18001714c  jnz     loc_180017E36
0x180017152  mov     ebx, r12d
0x180017155  cmp     r8d, 10006h
0x18001715c  jnz     loc_1800179E2
0x180017162  movzx   eax, r8w; jumptable 0000000180017A01 cases 65538-65541
0x180017166  mov     rdx, r14
0x180017169  shl     rdx, 7
0x18001716d  add     rdx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[rdi+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180017175  movsxd  rdi, dword ptr [rdx+1Ch]
0x180017179  cmp     edi, 7
0x18001717c  jz      short loc_1800171EF; jumptable 00000001800171AA cases 1,2,6
0x18001717e  cmp     edi, 14h
0x180017181  jz      loc_18001731C
0x180017187  cmp     edi, 8
0x18001718a  jz      loc_180017356
0x180017190  cmp     edi, 1Ah; switch 27 cases
0x180017193  ja      def_1800171AA; jumptable 00000001800171AA default case, cases 7,8,20
0x180017199  lea     rdx, __ImageBase
0x1800171a0  mov     ecx, ds:(jpt_1800171AA - 180000000h)[rdx+rdi*4]
0x1800171a7  add     rcx, rdx
0x1800171aa  jmp     rcx; switch jump
0x1800171b0  lea     r12, [rsi+40h]; jumptable 00000001800171AA case 4
0x1800171b4  mov     rdx, r12; struct XmlParserTempString *
0x1800171b7  mov     rcx, rsi; this
0x1800171ba  call    ?LoadRawValue@TaskXmlReader@@AEAAJAEAUXmlParserTempString@@@Z; TaskXmlReader::LoadRawValue(XmlParserTempString &)
0x1800171bf  mov     r15d, eax
0x1800171c2  test    eax, eax
0x1800171c4  jns     loc_180017B78
0x1800171ca  test    r14d, r14d
0x1800171cd  jz      loc_18001765B
0x1800171d3  mov     edx, r14d
0x1800171d6  lea     rcx, [rsi+45Ch]
0x1800171dd  call    ?GetEntry@Schema@@AEBAAEBUSchemaEntry@@W4TaskXmlNodeId@@@Z; Schema::GetEntry(TaskXmlNodeId)
0x1800171e2  mov     r8, [rax+8]
0x1800171e6  mov     r9d, [rax+10h]
0x1800171ea  jmp     loc_180017661
0x1800171ef  test    byte ptr [rsi+452h], 1; jumptable 00000001800171AA cases 1,2,6
0x1800171f6  jnz     loc_1800186B5
0x1800171fc  mov     [rsi+40h], ebx
0x1800171ff  mov     [rsi+48h], rbx
0x180017203  and     byte ptr [rsi+452h], 0FCh
0x18001720a  xor     eax, eax
0x18001720c  mov     [rsi+50h], ax
0x180017210  cmp     [rsp+140h+var_100], al
0x180017214  jz      loc_1800175CE
0x18001721a  cmp     edi, 2
0x18001721d  jz      loc_180017395
0x180017223  cmp     edi, 7
0x180017226  jz      loc_180017395
0x18001722c  cmp     edi, 6
0x18001722f  jnz     short loc_18001723B
0x180017231  cmp     dword ptr [rsi+40h], 0
0x180017235  jz      loc_180017C5A
0x18001723b  lea     r11, [rsi+40h]
0x18001723f  mov     [rbp+40h+var_C0], r11
0x180017243  cmp     byte ptr [rsi+28h], 0
0x180017247  jnz     loc_1800186CA
0x18001724d  mov     byte ptr [rsi+458h], 0
0x180017254  test    ebx, ebx
0x180017256  jns     short loc_180017297
0x180017258  mov     rcx, [rbp+40h+Block]; Block
0x18001725c  test    rcx, rcx
0x18001725f  jz      short loc_18001726D
0x180017261  call    cs:__imp_free
0x180017268  nop     dword ptr [rax+rax+00h]
0x18001726d  mov     eax, ebx
0x18001726f  mov     rcx, [rbp+40h+var_40]
0x180017273  xor     rcx, rsp; StackCookie
0x180017276  call    __security_check_cookie
0x18001727b  mov     rbx, [rsp+140h+arg_18]
0x180017283  add     rsp, 110h
0x18001728a  pop     r15
0x18001728c  pop     r14
0x18001728e  pop     r13
0x180017290  pop     r12
0x180017292  pop     rdi
0x180017293  pop     rsi
0x180017294  pop     rbp
0x180017295  retn
0x180017297  test    r13, r13
0x18001729a  jz      short loc_180017258
0x18001729c  lea     rdx, [rsi+45Ch]
0x1800172a3  mov     rax, [r13+0]
0x1800172a7  mov     rdi, [rbp+40h+var_A0]
0x1800172ab  movzx   ecx, byte ptr [rdi]
0x1800172ae  mov     byte ptr [rsp+140h+var_120], cl
0x1800172b2  lea     r9, [rsp+140h+var_F0]
0x1800172b7  mov     r8d, r14d
0x1800172ba  mov     rcx, r13
0x1800172bd  mov     rax, [rax+8]
0x1800172c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172c6  mov     ebx, eax
0x1800172c8  mov     byte ptr [rdi], 1
0x1800172cb  test    eax, eax
0x1800172cd  jns     short loc_180017258
0x1800172cf  mov     rax, [r13+0]
0x1800172d3  mov     rcx, r13
0x1800172d6  mov     rax, [rax+18h]
0x1800172da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172df  test    eax, eax
0x1800172e1  jz      loc_1800187C7
0x1800172e7  mov     rax, [r13+0]
0x1800172eb  mov     rcx, r13
0x1800172ee  mov     rax, [rax+18h]
0x1800172f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172f7  mov     r8d, eax
0x1800172fa  lea     r9, [rsi+40h]
0x1800172fe  mov     edx, ebx
0x180017300  mov     rcx, rsi
0x180017303  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJW4TaskXmlNodeId@@AEAUXmlParserTempString@@@Z; TaskXmlReader::SetErrorInfo(long,TaskXmlNodeId,XmlParserTempString &)
0x180017308  mov     ebx, eax
0x18001730a  mov     rcx, [rbp+40h+Block]
0x18001730e  test    rcx, rcx
0x180017311  jz      loc_18001726D
0x180017317  jmp     loc_180017261
0x18001731c  mov     dword ptr [rsp+140h+lpsz], 10006h
0x180017324  lea     rdx, [rsp+140h+lpsz]; enum Schema::Version *
0x180017329  mov     rcx, rsi; this
0x18001732c  call    ?LoadValue@TaskXmlReader@@AEAAJAEAW4Version@Schema@@@Z; TaskXmlReader::LoadValue(Schema::Version &)
0x180017331  mov     ebx, eax
0x180017333  test    eax, eax
0x180017335  js      loc_18001869D
0x18001733b  mov     eax, dword ptr [rsp+140h+lpsz]
0x18001733f  mov     [rsi+45Ch], eax
0x180017345  mov     [rsp+140h+rclsid.Data1], eax
0x180017349  lea     rax, [rsi+40h]
0x18001734d  mov     [rbp+40h+var_C0], rax
0x180017351  jmp     loc_18001724D
0x180017356  lea     rdx, [rsi+40h]; struct XmlParserTempString *
0x18001735a  mov     rcx, rsi; this
0x18001735d  call    ?LoadRawValue@TaskXmlReader@@AEAAJAEAUXmlParserTempString@@@Z; TaskXmlReader::LoadRawValue(XmlParserTempString &)
0x180017362  mov     r15d, eax
0x180017365  test    eax, eax
0x180017367  js      short loc_1800173E2
0x180017369  mov     eax, [rsi+40h]
0x18001736c  cmp     eax, 5
0x18001736f  jnz     short loc_1800173B8
0x180017371  mov     r8d, eax; MaxCount
0x180017374  lea     rdx, aFalse; "false"
0x18001737b  mov     rcx, [rsi+48h]; String1
0x18001737f  call    wcsncmp_0
0x180017384  test    eax, eax
0x180017386  jnz     short loc_1800173DC
0x180017388  xor     r8b, r8b
0x18001738b  mov     byte ptr [rsp+140h+rclsid.Data1], r8b
0x180017390  mov     ebx, r12d
0x180017393  jmp     short loc_1800173FC
0x180017395  cmp     dword ptr [rsi+40h], 0
0x180017399  jnz     loc_18001722C
0x18001739f  lea     r9, [rsi+40h]
0x1800173a3  mov     r8d, r14d
0x1800173a6  mov     edx, 80041318h
0x1800173ab  mov     rcx, rsi
0x1800173ae  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJW4TaskXmlNodeId@@AEAUXmlParserTempString@@@Z; TaskXmlReader::SetErrorInfo(long,TaskXmlNodeId,XmlParserTempString &)
0x1800173b3  jmp     loc_180017BBC
0x1800173b8  cmp     eax, 4
0x1800173bb  jnz     loc_1800181BD
0x1800173c1  mov     r8d, eax; MaxCount
0x1800173c4  lea     rdx, aTrue; "true"
0x1800173cb  mov     rcx, [rsi+48h]; String1
0x1800173cf  call    wcsncmp_0
0x1800173d4  test    eax, eax
0x1800173d6  jz      loc_180018189
0x1800173dc  mov     r15d, 80041318h
0x1800173e2  lea     r9, [rsi+40h]
0x1800173e6  mov     r8d, r14d
0x1800173e9  mov     edx, r15d
0x1800173ec  mov     rcx, rsi
0x1800173ef  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJW4TaskXmlNodeId@@AEAUXmlParserTempString@@@Z; TaskXmlReader::SetErrorInfo(long,TaskXmlNodeId,XmlParserTempString &)
0x1800173f4  mov     ebx, eax
0x1800173f6  movzx   r8d, byte ptr [rsp+140h+rclsid.Data1]
0x1800173fc  lea     rax, [rsi+40h]
0x180017400  mov     [rbp+40h+var_C0], rax
0x180017404  cmp     byte ptr [rsi+28h], 0
0x180017408  jz      loc_18001724D
0x18001740e  mov     edx, r14d
0x180017411  mov     rcx, [rsi+10h]
0x180017415  call    ?ElementBool@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@_N@Z; TaskXmlWriter::ElementBool(TaskXmlNodeId,bool)
0x18001741a  mov     ebx, eax
0x18001741c  test    eax, eax
0x18001741e  jmp     loc_18001837A
0x180017423  lea     rdx, [rsi+40h]; jumptable 00000001800171AA case 3
0x180017427  mov     rcx, rsi; this
0x18001742a  call    ?LoadRawValue@TaskXmlReader@@AEAAJAEAUXmlParserTempString@@@Z; TaskXmlReader::LoadRawValue(XmlParserTempString &)
0x18001742f  mov     r15d, eax
0x180017432  test    eax, eax
0x180017434  js      loc_1800174BC
0x18001743a  mov     [rsp+140h+lpsz], r12
0x18001743f  mov     [rsp+140h+var_108], r12d
0x180017444  mov     [rsp+140h+var_104], r12w
0x18001744a  mov     edx, [rsi+40h]; unsigned __int64
0x18001744d  lea     r8, [rsp+140h+lpsz]; struct TSTimePeriod *
0x180017452  mov     rcx, [rsi+48h]; unsigned __int16 *
0x180017456  call    ?ParseTimePeriod@TSParser@@SAJPEBG_KAEAVTSTimePeriod@@@Z; TSParser::ParseTimePeriod(ushort const *,unsigned __int64,TSTimePeriod &)
0x18001745b  test    eax, eax
0x18001745d  js      short loc_1800174B6
0x18001745f  movzx   eax, word ptr [rsp+140h+lpsz]
0x180017464  lea     ecx, [rax+rax*2]
0x180017467  movzx   eax, word ptr [rsp+140h+lpsz+2]
0x18001746c  lea     ecx, [rax+rcx*4]
0x18001746f  test    ecx, ecx
0x180017471  jnz     short loc_1800174B6
0x180017473  movzx   eax, word ptr [rsp+140h+lpsz+4]
0x180017478  imul    ecx, eax, 7
0x18001747b  movzx   eax, word ptr [rsp+140h+lpsz+6]
0x180017480  add     ecx, eax
0x180017482  lea     ecx, [rcx+rcx*2]
0x180017485  movzx   eax, word ptr [rsp+140h+var_108]
0x18001748a  lea     ecx, [rax+rcx*8]
0x18001748d  imul    edx, ecx, 3Ch ; '<'
0x180017490  movzx   eax, word ptr [rsp+140h+var_108+2]
0x180017495  add     edx, eax
0x180017497  imul    edx, 3Ch ; '<'
0x18001749a  movzx   eax, [rsp+140h+var_104]
0x18001749f  add     edx, eax
0x1800174a1  movsxd  rax, edx
0x1800174a4  mov     ecx, 0FFFFFFFFh
0x1800174a9  cmp     rax, rcx
0x1800174ac  jbe     loc_1800177EA
0x1800174b2  mov     [rsp+140h+rclsid.Data1], ecx
0x1800174b6  mov     r15d, 80041318h
0x1800174bc  test    r14d, r14d
0x1800174bf  jnz     loc_1800177CE
0x1800174c5  mov     r8, r12; unsigned __int16 *
0x1800174c8  mov     r9d, r12d; unsigned int
0x1800174cb  mov     eax, [rsi+40h]
0x1800174ce  mov     [rsp+140h+var_118], eax; unsigned int
0x1800174d2  mov     rax, [rsi+48h]
0x1800174d6  mov     [rsp+140h+var_120], rax; unsigned __int16 *
0x1800174db  mov     edx, r15d; int
0x1800174de  mov     rcx, rsi; this
0x1800174e1  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJPEBGK0K@Z; TaskXmlReader::SetErrorInfo(long,ushort const *,ulong,ushort const *,ulong)
0x1800174e6  mov     ebx, eax
0x1800174e8  lea     r8, [rsi+40h]
0x1800174ec  mov     [rbp+40h+var_C0], r8
0x1800174f0  cmp     byte ptr [rsi+28h], 0
0x1800174f4  jz      loc_18001724D
0x1800174fa  mov     rdi, [rsi+10h]
0x1800174fe  mov     eax, [rdi+98h]
0x180017504  test    eax, eax
0x180017506  jnz     loc_180018385
0x18001750c  mov     edx, [rdi]
0x18001750e  cmp     edx, 10006h
0x180017514  jnz     loc_180017FB5
0x18001751a  lea     r15, __ImageBase
0x180017521  movzx   eax, dx; jumptable 0000000180017FD8 cases 65538-65541
0x180017524  mov     rcx, r14
0x180017527  shl     rcx, 7
0x18001752b  mov     rdx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r15+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180017533  add     rdx, rcx; struct IErrorInfo *
0x180017536  mov     eax, [rdx]
0x180017538  test    eax, eax
0x18001753a  jz      loc_1800181AD
0x180017540  mov     rcx, [rdi+10h]
0x180017544  test    rcx, rcx
0x180017547  jz      loc_180018392
0x18001754d  mov     r12, [r8+8]
0x180017551  mov     rax, [rcx]
0x180017554  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x18001755b  mov     r8, [rdx+8]
  ... truncated ...
```
