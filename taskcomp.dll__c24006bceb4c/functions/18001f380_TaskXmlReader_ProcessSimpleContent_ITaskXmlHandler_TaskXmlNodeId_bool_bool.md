# TaskXmlReader::ProcessSimpleContent(ITaskXmlHandler *,TaskXmlNodeId,bool,bool &)

- ea: `0x18001f380`
- end: `0x180020111`
- name: `?ProcessSimpleContent@TaskXmlReader@@AEAAJPEAUITaskXmlHandler@@W4TaskXmlNodeId@@_NAEA_N@Z`
- size: `3473`
- prototype: ``
- caller_count: `2`
- callee_count: `37`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800036b4`
- `0x18001f1e8`

## callees

- `0x180003250`
- `0x1800074c8`
- `0x1800074d4`
- `0x18000a3c4`
- `0x18000e4d8`
- `0x18001bee0`
- `0x18001c534`
- `0x18001c558`
- `0x18001c5b8`
- `0x18001c854`
- `0x18001c930`
- `0x18001c984`
- `0x18001c9d4`
- `0x18001d06c`
- `0x18001d4c4`
- `0x18001d4ec`
- `0x18001d5a4`
- `0x18001d64c`
- `0x18001d710`
- `0x18001d7dc`
- `0x18001da48`
- `0x18001db50`
- `0x18001dbfc`
- `0x18001de60`
- `0x18001def0`
- `0x18001dfb8`
- `0x18001e1d4`
- `0x18001e27c`
- `0x18001e358`
- `0x18001e6cc`
- `0x18001f380`
- `0x1800204f0`
- `0x180020550`
- `0x1800205cc`
- `0x180020730`
- `0x18002093c`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f643`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f643`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001f608`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001f608`

## string_xrefs

- `0x18001f91b`: `InteractiveToken`
- `0x18001f909`: `InteractiveTokenOrPassword`
- `0x18001fb7e`: `LeastPrivilege`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TaskXmlReader::ProcessSimpleContent(__int64 a1, _BOOL8 a2, unsigned int a3, char a4, _BYTE *a5)
{
  __int64 v7; // r13
  int v9; // ebx
  int v10; // eax
  int v11; // edi
  int v12; // eax
  unsigned int Data1_low; // r8d
  int v14; // eax
  unsigned int *v15; // rbx
  int v16; // edi
  __int64 v17; // rdx
  int Timespan; // eax
  int *v19; // r8
  int v20; // eax
  __int64 v21; // rdx
  int v22; // eax
  __int64 v23; // rax
  int v24; // eax
  int v25; // eax
  unsigned int *v26; // r15
  int v27; // eax
  __int64 v28; // rdx
  int v29; // eax
  __int64 v30; // r12
  const unsigned __int16 *v31; // r12
  unsigned int v32; // edi
  void *v33; // r11
  void *v34; // rcx
  void *v35; // rbx
  __int64 v36; // rdx
  int Logon; // eax
  unsigned int v38; // eax
  const unsigned __int16 *v39; // r8
  __int64 v40; // rdx
  int v41; // eax
  int v42; // ebx
  int v43; // ebx
  int v44; // ebx
  int v45; // ebx
  int v46; // ebx
  int v47; // eax
  int DayOfMonth; // eax
  __int64 v49; // rdx
  bool v50; // zf
  __int64 v51; // rcx
  int v52; // eax
  unsigned int *v53; // rbx
  int InstancePolicy; // eax
  int Week; // eax
  int RawValue; // edi
  unsigned int Data1; // eax
  int Value; // eax
  unsigned int v59; // eax
  int v60; // edi
  unsigned int i; // r9d
  int v62; // r10d
  unsigned int v63; // edx
  int HexString; // eax
  unsigned int v65; // r15d
  unsigned int v66; // r12d
  unsigned int v67; // r13d
  unsigned int v68; // r9d
  unsigned int v69; // r10d
  unsigned int v70; // r11d
  _BYTE *v71; // rbx
  __int64 v72; // r8
  int v73; // edi
  int v74; // edi
  unsigned int v75; // eax
  unsigned __int16 v77[2]; // [rsp+30h] [rbp-71h] BYREF
  unsigned __int16 v78; // [rsp+34h] [rbp-6Dh] BYREF
  unsigned __int16 v79[2]; // [rsp+38h] [rbp-69h] BYREF
  unsigned __int16 v80; // [rsp+3Ch] [rbp-65h] BYREF
  unsigned __int16 v81[2]; // [rsp+40h] [rbp-61h] BYREF
  unsigned __int16 v82[6]; // [rsp+44h] [rbp-5Dh] BYREF
  _BYTE v83[16]; // [rsp+50h] [rbp-51h] BYREF
  __int16 v84; // [rsp+60h] [rbp-41h]
  unsigned __int16 v85; // [rsp+62h] [rbp-3Fh]
  unsigned __int16 v86; // [rsp+64h] [rbp-3Dh]
  unsigned __int16 v87; // [rsp+66h] [rbp-3Bh]
  unsigned __int16 v88; // [rsp+68h] [rbp-39h]
  unsigned __int16 v89; // [rsp+6Ah] [rbp-37h]
  unsigned __int16 v90; // [rsp+6Ch] [rbp-35h]
  IID rclsid; // [rsp+70h] [rbp-31h] BYREF
  unsigned int *v92; // [rsp+80h] [rbp-21h]
  void *v93; // [rsp+88h] [rbp-19h]
  unsigned int v94; // [rsp+90h] [rbp-11h]
  __int64 v95; // [rsp+A0h] [rbp-1h] BYREF
  int v96; // [rsp+A8h] [rbp+7h]
  unsigned __int16 v97; // [rsp+ACh] [rbp+Bh]
  LPOLESTR lpsz; // [rsp+B0h] [rbp+Fh] BYREF
  void *Block; // [rsp+100h] [rbp+5Fh] BYREF
  _BOOL8 v100; // [rsp+108h] [rbp+67h]

  v100 = a2;
  v7 = a2;
  ITaskXmlHandler::Data::Data((ITaskXmlHandler::Data *)v83, a2);
  *(_BYTE *)(a1 + 1112) = 1;
  v9 = *((_DWORD *)Schema::GetEntry((int *)(a1 + 1116), a3) + 7);
  if ( (unsigned int)v9 >= 2 && v9 != 9 && v9 != 11 && v9 != 26 && a4 )
  {
    v10 = TaskXmlReader::SetErrorInfo(a1, 2147750680LL, a3);
LABEL_254:
    v11 = v10;
    goto LABEL_255;
  }
  if ( v9 > 13 )
  {
    if ( v9 <= 20 )
    {
      if ( v9 == 20 )
      {
        LODWORD(Block) = 65542;
        Value = TaskXmlReader::LoadValue((TaskXmlReader *)a1, (enum Schema::Version *)&Block);
        v11 = Value;
        v53 = (unsigned int *)(a1 + 64);
        if ( Value < 0 )
          v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)Value, a3, a1 + 64);
        v59 = (unsigned int)Block;
        *(_DWORD *)(a1 + 1116) = (_DWORD)Block;
        rclsid.Data1 = v59;
        goto LABEL_156;
      }
      v42 = v9 - 14;
      if ( v42 )
      {
        v43 = v42 - 1;
        if ( !v43 )
        {
          LOWORD(rclsid.Data1) = 0;
          Week = TaskXmlReader::LoadWeek((TaskXmlReader *)a1, (unsigned __int16 *)&rclsid);
          v11 = Week;
          if ( Week < 0 )
            v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)Week, a3, a1 + 64);
          v92 = (unsigned int *)(a1 + 64);
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_221;
          v49 = 70;
          v50 = LOWORD(rclsid.Data1) == 5;
          goto LABEL_148;
        }
        v44 = v43 - 1;
        if ( !v44 )
        {
          InstancePolicy = TaskXmlReader::LoadInstancePolicy((TaskXmlReader *)a1, (enum JobFlags::JobFlag *)&rclsid);
          v11 = InstancePolicy;
          if ( InstancePolicy < 0 )
            v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)InstancePolicy, a3, a1 + 64);
          v92 = (unsigned int *)(a1 + 64);
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_221;
          v14 = TaskXmlWriter::ElementMultipleInstancesPolicy(*(_QWORD *)(a1 + 16), rclsid.Data1);
          goto LABEL_104;
        }
        v45 = v44 - 1;
        if ( v45 )
        {
          v46 = v45 - 1;
          if ( v46 )
          {
            if ( v46 == 1 )
            {
              rclsid.Data1 = 0;
              v47 = TaskXmlReader::LoadSessionStateChange((TaskXmlReader *)a1, &rclsid.Data1);
              v11 = v47;
              if ( v47 < 0 )
                v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v47, a3, a1 + 64);
              v92 = (unsigned int *)(a1 + 64);
              if ( !*(_BYTE *)(a1 + 40) )
                goto LABEL_221;
              if ( LOWORD(rclsid.Data1) != 1 )
              {
                switch ( LOWORD(rclsid.Data1) )
                {
                  case 2u:
                    v39 = L"ConsoleDisconnect";
                    goto LABEL_143;
                  case 3u:
                    v39 = L"RemoteConnect";
                    goto LABEL_143;
                  case 4u:
                    v39 = L"RemoteDisconnect";
                    goto LABEL_143;
                  case 7u:
                    v39 = L"SessionLock";
                    goto LABEL_143;
                  case 8u:
                    v39 = L"SessionUnlock";
LABEL_143:
                    v40 = 38;
                    goto LABEL_119;
                }
              }
              v39 = L"ConsoleConnect";
              goto LABEL_143;
            }
LABEL_186:
            v28 = 2147750678LL;
            goto LABEL_71;
          }
          LOWORD(rclsid.Data1) = 0;
          DayOfMonth = TaskXmlReader::LoadDayOfMonth((TaskXmlReader *)a1, (unsigned __int16 *)&rclsid);
          v11 = DayOfMonth;
          if ( DayOfMonth < 0 )
            v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)DayOfMonth, a3, a1 + 64);
          v92 = (unsigned int *)(a1 + 64);
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_221;
          v49 = 68;
          v50 = LOWORD(rclsid.Data1) == 32;
LABEL_148:
          v51 = *(_QWORD *)(a1 + 16);
          if ( v50 )
          {
            v11 = TaskXmlWriter::Element(v51, v49, (__int64)L"Last");
            if ( v11 >= 0 )
              goto LABEL_221;
          }
          else
          {
            v11 = TaskXmlWriter::ElementInt(v51, v49, LOWORD(rclsid.Data1));
          }
          if ( v11 < 0 )
            goto LABEL_255;
          goto LABEL_221;
        }
        v52 = TaskXmlReader::SkipElement((TaskXmlReader *)a1);
        v11 = v52;
        v53 = (unsigned int *)(a1 + 64);
        if ( v52 < 0 )
          v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v52, a3, a1 + 64);
LABEL_156:
        v92 = v53;
        goto LABEL_221;
      }
      rclsid.Data1 = 0;
      RawValue = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
      if ( RawValue >= 0 )
      {
        if ( *(_DWORD *)(a1 + 64) )
        {
          if ( XmlParserTempString::IsEqualTo((XmlParserTempString *)(a1 + 64), L"LeastPrivilege", 0xEu) )
          {
            Data1 = 0;
LABEL_171:
            rclsid.Data1 = Data1;
            v11 = 0;
            goto LABEL_174;
          }
          if ( XmlParserTempString::IsEqualTo((XmlParserTempString *)(a1 + 64), L"HighestAvailable", 0x10u) )
          {
            Data1 = 0x1000000;
            goto LABEL_171;
          }
        }
        RawValue = -2147216616;
      }
      v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)RawValue, a3, a1 + 64);
      Data1 = rclsid.Data1;
LABEL_174:
      v92 = (unsigned int *)(a1 + 64);
      if ( !*(_BYTE *)(a1 + 40) || (Data1 & 0x1000000) == 0 )
        goto LABEL_221;
      v39 = L"HighestAvailable";
      goto LABEL_118;
    }
    if ( v9 != 21 )
    {
      if ( v9 != 22 )
      {
        switch ( v9 )
        {
          case 23:
            v65 = 0;
            v66 = 0;
            v67 = 0;
            LODWORD(lpsz) = 0;
            v11 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
            if ( v11 >= 0 )
            {
              v95 = 0;
              v96 = 0;
              v97 = 0;
              if ( (int)TSParser::ParseTimePeriod(
                          *(const unsigned __int16 **)(a1 + 72),
                          *(unsigned int *)(a1 + 64),
                          (struct TSTimePeriod *)&v95) >= 0 )
              {
                v65 = (unsigned __int16)v95;
                v66 = WORD1(v95);
                v67 = WORD2(v95);
                LODWORD(lpsz) = v97;
                v11 = 0;
              }
              else
              {
                v11 = -2147216616;
              }
            }
            LOWORD(Block) = 0;
            v77[0] = 0;
            v79[0] = 0;
            v78 = 0;
            v80 = 0;
            v81[0] = 0;
            v82[0] = 0;
            if ( v11 < 0
              || (v11 = ULongToUShort(v65, (unsigned __int16 *)&Block), v11 < 0)
              || (v11 = ULongToUShort(v66, v77), v11 < 0)
              || (v11 = ULongToUShort(v67, &v78), v11 < 0)
              || (v11 = ULongToUShort(v68, v79), v11 < 0)
              || (v11 = ULongToUShort(v69, &v80), v11 < 0)
              || (v11 = ULongToUShort(v70, v81), v11 < 0)
              || (v11 = ULongToUShort((unsigned int)lpsz, v82), v11 < 0) )
            {
              v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v11, a3, a1 + 64);
            }
            else
            {
              v84 = (__int16)Block;
              v85 = v77[0];
              v86 = v78;
              v87 = v79[0];
              v88 = v80;
              v89 = v81[0];
              v90 = v82[0];
            }
            v92 = (unsigned int *)(a1 + 64);
            if ( *(_BYTE *)(a1 + 40) )
            {
              v11 = TaskXmlWriter::Element(*(_QWORD *)(a1 + 16), a3, *(_QWORD *)(a1 + 72));
              if ( v11 < 0 )
                goto LABEL_255;
            }
            v7 = v100;
            goto LABEL_221;
          case 24:
            goto LABEL_198;
          case 25:
            rclsid.Data1 = 0;
            v60 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
            if ( v60 < 0 )
            {
LABEL_194:
              v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v60, a3, a1 + 64);
              Data1_low = rclsid.Data1;
            }
            else
            {
              Data1_low = 0;
              rclsid.Data1 = 0;
              for ( i = 0; i < *(_DWORD *)(a1 + 64); ++i )
              {
                v62 = *(unsigned __int16 *)(*(_QWORD *)(a1 + 72) + 2LL * (int)i);
                if ( (unsigned __int16)(v62 - 48) <= 9u )
                {
                  v63 = Data1_low;
                  Data1_low = v62 + 2 * (Data1_low + 4 * (Data1_low - 6));
                  rclsid.Data1 = Data1_low;
                  if ( Data1_low >= v63 )
                    continue;
                }
                v60 = -2147216616;
                goto LABEL_194;
              }
              v11 = 0;
            }
            v92 = (unsigned int *)(a1 + 64);
            if ( *(_BYTE *)(a1 + 40) )
              goto LABEL_22;
            goto LABEL_221;
          case 26:
LABEL_198:
            HexString = TaskXmlReader::LoadHexString((TaskXmlReader *)a1);
            v11 = HexString;
            v26 = (unsigned int *)(a1 + 64);
            if ( HexString < 0 )
              v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)HexString, a3, a1 + 64);
            if ( v9 == 24 && *v26 != 16 )
              goto LABEL_76;
            v92 = (unsigned int *)(a1 + 64);
            if ( !*(_BYTE *)(a1 + 40) )
              goto LABEL_221;
            v14 = TaskXmlWriter::ElementHexString(*(_QWORD *)(a1 + 16), a3, (tsched *)v93, v94);
            goto LABEL_104;
        }
        goto LABEL_186;
      }
      *(_QWORD *)&rclsid.Data1 = 0;
      v73 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
      if ( v73 >= 0 )
      {
        if ( *(_DWORD *)(a1 + 64) )
        {
          Block = 0;
          if ( (unsigned int)User::LookupPrivilege(*(LPCWSTR *)(a1 + 72), (PLUID)&Block) )
          {
            *(_QWORD *)&rclsid.Data1 = 1LL << (char)Block;
            v11 = 0;
LABEL_233:
            v92 = (unsigned int *)(a1 + 64);
            if ( !*(_BYTE *)(a1 + 40) )
              goto LABEL_221;
            v19 = *(int **)(a1 + 72);
            v36 = 135;
            goto LABEL_103;
          }
        }
        v73 = -2147216616;
      }
      v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v73, a3, a1 + 64);
      goto LABEL_233;
    }
    rclsid.Data1 = 0;
    v74 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
    if ( v74 >= 0 )
    {
      if ( *(_DWORD *)(a1 + 64) )
      {
        if ( XmlParserTempString::IsEqualTo((XmlParserTempString *)(a1 + 64), L"None", 4u) )
        {
          v75 = 0x8000000;
LABEL_241:
          rclsid.Data1 = v75;
          v11 = 0;
LABEL_244:
          v92 = (unsigned int *)(a1 + 64);
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_221;
          if ( (v75 & 0x8000000) == 0 )
          {
            if ( (v75 & 0x10000000) == 0 )
              goto LABEL_221;
            v14 = TaskXmlWriter::ElementProcessTokenSidType(*(_QWORD *)(a1 + 16), a3, 1);
            goto LABEL_104;
          }
          v41 = TaskXmlWriter::ElementProcessTokenSidType(*(_QWORD *)(a1 + 16), a3, 0);
LABEL_247:
          v11 = v41;
          if ( v41 < 0 )
            goto LABEL_255;
          goto LABEL_248;
        }
        if ( XmlParserTempString::IsEqualTo((XmlParserTempString *)(a1 + 64), L"Unrestricted", 0xCu) )
        {
          v75 = 0x10000000;
          goto LABEL_241;
        }
      }
      v74 = -2147216616;
    }
    v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v74, a3, a1 + 64);
    v75 = rclsid.Data1;
    goto LABEL_244;
  }
  if ( v9 == 13 )
  {
    Logon = TaskXmlReader::LoadLogon((TaskXmlReader *)a1, (enum JobFlags::JobFlag *)&rclsid);
    v11 = Logon;
    if ( Logon < 0 )
      v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)Logon, a3, a1 + 64);
    v92 = (unsigned int *)(a1 + 64);
    if ( !*(_BYTE *)(a1 + 40) )
      goto LABEL_221;
    v38 = rclsid.Data1 & 0xFC000;
    if ( (rclsid.Data1 & 0xFC000) == 0x4000 )
    {
      v39 = L"S4U";
    }
    else
    {
      switch ( v38 )
      {
        case 0x10000u:
          v39 = L"InteractiveToken";
          break;
        case 0x40000u:
          v39 = L"Password";
          break;
        case 0x80000u:
          v39 = L"InteractiveTokenOrPassword";
          break;
        default:
          v11 = -2147024809;
          goto LABEL_255;
      }
    }
LABEL_118:
    v40 = a3;
LABEL_119:
    v41 = TaskXmlWriter::Element(*(_QWORD *)(a1 + 16), v40, (__int64)v39);
    goto LABEL_247;
  }
  v11 = 0;
  if ( v9 > 6 )
  {
    if ( v9 == 7 )
      goto LABEL_68;
    if ( v9 != 8 )
    {
      if ( v9 == 9 )
      {
        if ( !a4 )
        {
          LODWORD(Block) = 0;
          v23 = _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->((__int64 *)(a1 + 56));
          v24 = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v23 + 48LL))(v23, &Block);
          v11 = v24;
          if ( v24 < 0 )
          {
            v10 = TaskXmlReader::SetErrorInfoXmlLite((TaskXmlReader *)a1, v24);
            goto LABEL_254;
          }
          if ( v24 || (_DWORD)Block != 15 )
            v11 = TaskXmlReader::SetErrorInfo(a1, 2147750680LL, a3, a1 + 64);
        }
        v92 = 0;
        if ( !*(_BYTE *)(a1 + 40) )
          goto LABEL_221;
        v19 = 0;
        goto LABEL_102;
      }
      if ( v9 != 10 )
      {
        if ( v9 == 11 )
        {
          v15 = (unsigned int *)(a1 + 64);
          XmlParserTempString::Clear((BSTR *)(a1 + 64));
          if ( a4 )
            goto LABEL_32;
          Timespan = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
          goto LABEL_29;
        }
        v20 = TaskXmlReader::LoadValue((TaskXmlReader *)a1, (unsigned __int16 *)&rclsid);
        v11 = v20;
        if ( v20 >= 0 )
        {
          if ( LOWORD(rclsid.Data1) <= 0xAu )
          {
LABEL_45:
            v92 = (unsigned int *)(a1 + 64);
            goto LABEL_20;
          }
          v21 = 2147750680LL;
        }
        else
        {
          v21 = (unsigned int)v20;
        }
        v11 = TaskXmlReader::SetErrorInfo(a1, v21, a3, a1 + 64);
        goto LABEL_45;
      }
      v22 = TaskXmlReader::LoadValue((TaskXmlReader *)a1, &rclsid);
      v11 = v22;
      if ( v22 < 0 )
        v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v22, a3, a1 + 64);
      v92 = (unsigned int *)(a1 + 64);
      if ( !*(_BYTE *)(a1 + 40) )
        goto LABEL_221;
      lpsz = 0;
      v10 = StringFromCLSID(&rclsid, &lpsz);
      if ( v10 )
      {
        if ( v10 > 0 )
          v10 = (unsigned __int16)v10 | 0x80070000;
        goto LABEL_254;
      }
      v11 = TaskXmlWriter::Element(*(_QWORD *)(a1 + 16), a3, (__int64)lpsz);
      if ( v11 < 0 )
        goto LABEL_255;
      CoTaskMemFree(lpsz);
LABEL_248:
      *(_BYTE *)(a1 + 1112) = 0;
      goto LABEL_249;
    }
    v25 = TaskXmlReader::LoadValue((TaskXmlReader *)a1, (bool *)&rclsid);
    v11 = v25;
    if ( v25 < 0 )
      v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v25, a3, a1 + 64);
    v92 = (unsigned int *)(a1 + 64);
    if ( !*(_BYTE *)(a1 + 40) )
      goto LABEL_221;
    v14 = TaskXmlWriter::ElementBool(*(_QWORD *)(a1 + 16), a3, rclsid.Data1);
LABEL_104:
    v11 = v14;
    if ( v14 < 0 )
      goto LABEL_255;
    goto LABEL_221;
  }
  if ( v9 == 6 )
    goto LABEL_68;
  if ( v9 )
  {
    if ( v9 != 1 && v9 != 2 )
    {
      if ( v9 != 3 )
      {
        if ( v9 != 4 )
        {
          if ( v9 == 5 )
          {
            LOWORD(rclsid.Data1) = 0;
            v12 = TaskXmlReader::LoadValue((TaskXmlReader *)a1, (unsigned __int16 *)&rclsid);
            v11 = v12;
            if ( v12 < 0 )
              v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v12, a3, a1 + 64);
            v92 = (unsigned int *)(a1 + 64);
LABEL_20:
            if ( *(_BYTE *)(a1 + 40) )
            {
              Data1_low = LOWORD(rclsid.Data1);
LABEL_22:
              v14 = TaskXmlWriter::ElementInt(*(_QWORD *)(a1 + 16), a3, Data1_low);
              goto LABEL_104;
            }
LABEL_221:
            v30 = a1 + 1116;
LABEL_222:
            *(_BYTE *)(a1 + 1112) = 0;
            if ( v11 < 0 )
              goto LABEL_255;
            goto LABEL_223;
          }
          goto LABEL_186;
        }
        v15 = (unsigned int *)(a1 + 64);
        v16 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
        if ( v16 < 0 )
          goto LABEL_26;
        if ( (int)TSParser::ParseDateTime(*(const unsigned __int16 **)(a1 + 72), *v15, (struct TSTime *)v83) < 0 )
        {
          v16 = -2147216616;
LABEL_26:
          v17 = (unsigned int)v16;
LABEL_31:
          v11 = TaskXmlReader::SetErrorInfo(a1, v17, a3, v15);
          goto LABEL_32;
        }
        v11 = 0;
LABEL_32:
        v92 = v15;
        if ( !*(_BYTE *)(a1 + 40) )
          goto LABEL_221;
        v19 = (int *)*((_QWORD *)v15 + 1);
        goto LABEL_102;
      }
      Timespan = TaskXmlReader::LoadTimespan((TaskXmlReader *)a1, &rclsid.Data1);
      v15 = (unsigned int *)(a1 + 64);
LABEL_29:
      v11 = Timespan;
      if ( Timespan < 0 )
      {
        v17 = (unsigned int)Timespan;
        goto LABEL_31;
      }
      goto LABEL_32;
    }
LABEL_68:
    v26 = (unsigned int *)(a1 + 64);
    XmlParserTempString::Clear((BSTR *)(a1 + 64));
    if ( !a4 )
    {
      v27 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
      v11 = v27;
      if ( v27 < 0 )
      {
        v28 = (unsigned int)v27;
LABEL_71:
        v29 = TaskXmlReader::SetErrorInfo(a1, v28, a3);
LABEL_72:
        v11 = v29;
        goto LABEL_221;
      }
    }
    if ( (v9 != 2 && v9 != 7 || *v26) && (v9 != 6 || *v26) )
    {
      v92 = (unsigned int *)(a1 + 64);
      if ( !*(_BYTE *)(a1 + 40) )
        goto LABEL_221;
      if ( a3 != 6 && a3 != 8 && a3 != 10 && a3 != 11 && a3 != 112 && a3 != 115 && a3 != 121 && a3 - 129 >= 2 )
      {
        v30 = a1 + 1116;
        if ( *((_DWORD *)Schema::GetEntry((int *)(a1 + 1116), a3) + 6) != 2 )
          v11 = TaskXmlWriter::Element(*(_QWORD *)(a1 + 16), a3, *(_QWORD *)(a1 + 72));
        if ( v11 < 0 )
          goto LABEL_255;
        goto LABEL_222;
      }
      v31 = *(const unsigned __int16 **)(a1 + 72);
      if ( v31 )
      {
        v32 = *v26;
        if ( *v26 )
        {
          Block = operator new[](saturated_mul(v32 + 1, 2u));
          v11 = StringCchCopyNW((unsigned __int16 *)Block, v32 + 1, v31, v32);
          if ( v11 < 0 )
          {
            v34 = v33;
LABEL_96:
            operator delete(v34);
            goto LABEL_255;
          }
          v11 = TaskXmlReader::LoadTranslatedString(&Block);
          if ( v11 < 0 )
          {
            v34 = Block;
            goto LABEL_96;
          }
          v35 = Block;
          v11 = TaskXmlWriter::Element(*(_QWORD *)(a1 + 16), a3, (__int64)Block);
          v34 = v35;
          if ( v11 < 0 )
            goto LABEL_96;
          operator delete(v35);
          goto LABEL_248;
        }
      }
      v19 = &dword_1800505FC;
LABEL_102:
      v36 = a3;
LABEL_103:
      v14 = TaskXmlWriter::Element(*(_QWORD *)(a1 + 16), v36, (__int64)v19);
      goto LABEL_104;
    }
LABEL_76:
    v29 = TaskXmlReader::SetErrorInfo(a1, 2147750680LL, a3, v26);
    goto LABEL_72;
  }
  *(_BYTE *)(a1 + 1112) = 0;
LABEL_249:
  v30 = a1 + 1116;
LABEL_223:
  if ( v7 )
  {
    v71 = a5;
    v11 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _BYTE *, _BYTE))(*(_QWORD *)v7 + 8LL))(
            v7,
            v30,
            a3,
            v83,
            *a5);
    *v71 = 1;
    if ( v11 < 0 )
    {
      if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v7 + 24LL))(v7) )
        v72 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v7 + 24LL))(v7);
      else
        v72 = a3;
      v10 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v11, v72, a1 + 64);
      goto LABEL_254;
    }
  }
LABEL_255:
  operator delete(v93);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001f380  mov     [rsp-8+arg_10], rbx
0x18001f385  mov     [rsp-8+arg_8], rdx
0x18001f38a  push    rbp
0x18001f38b  push    rsi
0x18001f38c  push    rdi
0x18001f38d  push    r12
0x18001f38f  push    r13
0x18001f391  push    r14
0x18001f393  push    r15
0x18001f395  lea     rbp, [rsp-1Fh]
0x18001f39a  sub     rsp, 0C0h
0x18001f3a1  mov     r12b, r9b
0x18001f3a4  mov     r14d, r8d
0x18001f3a7  mov     r13, rdx
0x18001f3aa  mov     rsi, rcx
0x18001f3ad  lea     rcx, [rbp+4Fh+var_A0]; this
0x18001f3b1  call    ??0Data@ITaskXmlHandler@@QEAA@XZ; ITaskXmlHandler::Data::Data(void)
0x18001f3b6  nop
0x18001f3b7  mov     byte ptr [rsi+458h], 1
0x18001f3be  lea     r15, [rsi+45Ch]
0x18001f3c5  mov     edx, r14d
0x18001f3c8  mov     rcx, r15
0x18001f3cb  call    ?GetEntry@Schema@@AEBAAEBUSchemaEntry@@W4TaskXmlNodeId@@@Z; Schema::GetEntry(TaskXmlNodeId)
0x18001f3d0  mov     ebx, [rax+1Ch]
0x18001f3d3  mov     ecx, ebx
0x18001f3d5  xor     edx, edx
0x18001f3d7  test    ebx, ebx
0x18001f3d9  jz      short loc_18001F409
0x18001f3db  sub     ecx, 1
0x18001f3de  jz      short loc_18001F409
0x18001f3e0  sub     ecx, 8
0x18001f3e3  jz      short loc_18001F409
0x18001f3e5  sub     ecx, 2
0x18001f3e8  jz      short loc_18001F409
0x18001f3ea  cmp     ecx, 0Fh
0x18001f3ed  jz      short loc_18001F409
0x18001f3ef  test    r12b, r12b
0x18001f3f2  jz      short loc_18001F409
0x18001f3f4  mov     r8d, r14d
0x18001f3f7  mov     edx, 80041318h
0x18001f3fc  mov     rcx, rsi
0x18001f3ff  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJW4TaskXmlNodeId@@@Z; TaskXmlReader::SetErrorInfo(long,TaskXmlNodeId)
0x18001f404  jmp     loc_1800200E9
0x18001f409  cmp     ebx, 0Dh
0x18001f40c  jg      loc_18001F93C
0x18001f412  jz      loc_18001F8A5
0x18001f418  xor     edi, edi
0x18001f41a  cmp     ebx, 6
0x18001f41d  jg      loc_18001F52D
0x18001f423  jz      loc_18001F70D
0x18001f429  mov     ecx, ebx
0x18001f42b  test    ebx, ebx
0x18001f42d  jz      loc_18001F522
0x18001f433  sub     ecx, 1
0x18001f436  jz      loc_18001F70D
0x18001f43c  sub     ecx, 1
0x18001f43f  jz      loc_18001F70D
0x18001f445  sub     ecx, 1
0x18001f448  jz      loc_18001F4E3
0x18001f44e  sub     ecx, 1
0x18001f451  jz      short loc_18001F4AE
0x18001f453  cmp     ecx, 1
0x18001f456  jnz     loc_18001FC66
0x18001f45c  xor     eax, eax
0x18001f45e  mov     word ptr [rbp+4Fh+rclsid.Data1], ax
0x18001f462  lea     rdx, [rbp+4Fh+rclsid]; unsigned __int16 *
0x18001f466  mov     rcx, rsi; this
0x18001f469  call    ?LoadValue@TaskXmlReader@@AEAAJAEAG@Z; TaskXmlReader::LoadValue(ushort &)
0x18001f46e  mov     edi, eax
0x18001f470  lea     rbx, [rsi+40h]
0x18001f474  test    eax, eax
0x18001f476  jns     short loc_18001F48A
0x18001f478  mov     r9, rbx
0x18001f47b  mov     r8d, r14d
0x18001f47e  mov     edx, eax
0x18001f480  mov     rcx, rsi
0x18001f483  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJW4TaskXmlNodeId@@AEAUXmlParserTempString@@@Z; TaskXmlReader::SetErrorInfo(long,TaskXmlNodeId,XmlParserTempString &)
0x18001f488  mov     edi, eax
0x18001f48a  mov     [rbp+4Fh+var_70], rbx
0x18001f48e  cmp     byte ptr [rsi+28h], 0
0x18001f492  jz      loc_18001FEFC
0x18001f498  movzx   r8d, word ptr [rbp+4Fh+rclsid.Data1]
0x18001f49d  mov     edx, r14d
0x18001f4a0  mov     rcx, [rsi+10h]
0x18001f4a4  call    ?ElementInt@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@H@Z; TaskXmlWriter::ElementInt(TaskXmlNodeId,int)
0x18001f4a9  jmp     loc_18001F896
0x18001f4ae  lea     rbx, [rsi+40h]
0x18001f4b2  mov     rdx, rbx; struct XmlParserTempString *
0x18001f4b5  mov     rcx, rsi; this
0x18001f4b8  call    ?LoadRawValue@TaskXmlReader@@AEAAJAEAUXmlParserTempString@@@Z; TaskXmlReader::LoadRawValue(XmlParserTempString &)
0x18001f4bd  mov     edi, eax
0x18001f4bf  test    eax, eax
0x18001f4c1  js      short loc_18001F4DB
0x18001f4c3  mov     edx, [rbx]; unsigned __int64
0x18001f4c5  lea     r8, [rbp+4Fh+var_A0]; struct TSTime *
0x18001f4c9  mov     rcx, [rsi+48h]; unsigned __int16 *
0x18001f4cd  call    ?ParseDateTime@TSParser@@SAJPEBG_KAEAVTSTime@@@Z; TSParser::ParseDateTime(ushort const *,unsigned __int64,TSTime &)
0x18001f4d2  test    eax, eax
0x18001f4d4  jns     short loc_18001F4DF
0x18001f4d6  mov     edi, 80041318h
0x18001f4db  mov     edx, edi
0x18001f4dd  jmp     short loc_18001F4FB
0x18001f4df  xor     edi, edi
0x18001f4e1  jmp     short loc_18001F50B
0x18001f4e3  lea     rdx, [rbp+4Fh+rclsid]; unsigned int *
0x18001f4e7  mov     rcx, rsi; this
0x18001f4ea  call    ?LoadTimespan@TaskXmlReader@@AEAAJAEAK@Z; TaskXmlReader::LoadTimespan(ulong &)
0x18001f4ef  lea     rbx, [rsi+40h]
0x18001f4f3  test    eax, eax
0x18001f4f5  mov     edi, eax
0x18001f4f7  jns     short loc_18001F50B
0x18001f4f9  mov     edx, eax
0x18001f4fb  mov     r9, rbx
0x18001f4fe  mov     r8d, r14d
0x18001f501  mov     rcx, rsi
0x18001f504  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJW4TaskXmlNodeId@@AEAUXmlParserTempString@@@Z; TaskXmlReader::SetErrorInfo(long,TaskXmlNodeId,XmlParserTempString &)
0x18001f509  mov     edi, eax
0x18001f50b  mov     [rbp+4Fh+var_70], rbx
0x18001f50f  cmp     byte ptr [rsi+28h], 0
0x18001f513  jz      loc_18001FEFC
0x18001f519  mov     r8, [rbx+8]
0x18001f51d  jmp     loc_18001F88A
0x18001f522  mov     [rsi+458h], dl
0x18001f528  jmp     loc_1800200AC
0x18001f52d  mov     ecx, ebx
0x18001f52f  sub     ecx, 7
0x18001f532  jz      loc_18001F70D
0x18001f538  sub     ecx, 1
0x18001f53b  jz      loc_18001F6C2
0x18001f541  sub     ecx, 1
0x18001f544  jz      loc_18001F64E
0x18001f54a  sub     ecx, 1
0x18001f54d  jz      short loc_18001F5C2
0x18001f54f  sub     ecx, 1
0x18001f552  jz      short loc_18001F59D
0x18001f554  cmp     ecx, 1
0x18001f557  jnz     loc_18001FC66
0x18001f55d  lea     rdx, [rbp+4Fh+rclsid]; unsigned __int16 *
0x18001f561  mov     rcx, rsi; this
0x18001f564  call    ?LoadValue@TaskXmlReader@@AEAAJAEAG@Z; TaskXmlReader::LoadValue(ushort &)
0x18001f569  mov     edi, eax
0x18001f56b  test    eax, eax
0x18001f56d  jns     short loc_18001F573
0x18001f56f  mov     edx, eax
0x18001f571  jmp     short loc_18001F57F
0x18001f573  cmp     word ptr [rbp+4Fh+rclsid.Data1], 0Ah
0x18001f578  jbe     short loc_18001F590
0x18001f57a  mov     edx, 80041318h
0x18001f57f  lea     r9, [rsi+40h]
0x18001f583  mov     r8d, r14d
0x18001f586  mov     rcx, rsi
0x18001f589  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJW4TaskXmlNodeId@@AEAUXmlParserTempString@@@Z; TaskXmlReader::SetErrorInfo(long,TaskXmlNodeId,XmlParserTempString &)
0x18001f58e  mov     edi, eax
0x18001f590  lea     rax, [rsi+40h]
0x18001f594  mov     [rbp+4Fh+var_70], rax
0x18001f598  jmp     loc_18001F48E
0x18001f59d  lea     rbx, [rsi+40h]
0x18001f5a1  mov     rcx, rbx; this
0x18001f5a4  call    ?Clear@XmlParserTempString@@QEAAXXZ; XmlParserTempString::Clear(void)
0x18001f5a9  test    r12b, r12b
0x18001f5ac  jnz     loc_18001F50B
0x18001f5b2  mov     rdx, rbx; struct XmlParserTempString *
0x18001f5b5  mov     rcx, rsi; this
0x18001f5b8  call    ?LoadRawValue@TaskXmlReader@@AEAAJAEAUXmlParserTempString@@@Z; TaskXmlReader::LoadRawValue(XmlParserTempString &)
0x18001f5bd  jmp     loc_18001F4F3
0x18001f5c2  lea     rdx, [rbp+4Fh+rclsid]; struct _GUID *
0x18001f5c6  mov     rcx, rsi; this
0x18001f5c9  call    ?LoadValue@TaskXmlReader@@AEAAJAEAU_GUID@@@Z; TaskXmlReader::LoadValue(_GUID &)
0x18001f5ce  mov     edi, eax
0x18001f5d0  lea     rbx, [rsi+40h]
0x18001f5d4  test    eax, eax
0x18001f5d6  jns     short loc_18001F5EA
0x18001f5d8  mov     r9, rbx
0x18001f5db  mov     r8d, r14d
0x18001f5de  mov     edx, eax
0x18001f5e0  mov     rcx, rsi
0x18001f5e3  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJW4TaskXmlNodeId@@AEAUXmlParserTempString@@@Z; TaskXmlReader::SetErrorInfo(long,TaskXmlNodeId,XmlParserTempString &)
0x18001f5e8  mov     edi, eax
0x18001f5ea  mov     [rbp+4Fh+var_70], rbx
0x18001f5ee  cmp     byte ptr [rsi+28h], 0
0x18001f5f2  jz      loc_18001FEFC
0x18001f5f8  mov     [rbp+4Fh+lpsz], 0
0x18001f600  lea     rdx, [rbp+4Fh+lpsz]; lplpsz
0x18001f604  lea     rcx, [rbp+4Fh+rclsid]; rclsid
0x18001f608  call    cs:__imp_StringFromCLSID
0x18001f60e  test    eax, eax
0x18001f610  jz      short loc_18001F625
0x18001f612  jle     loc_1800200E9
0x18001f618  movzx   eax, ax
0x18001f61b  or      eax, 80070000h
0x18001f620  jmp     loc_1800200E9
0x18001f625  mov     r8, [rbp+4Fh+lpsz]
0x18001f629  mov     edx, r14d
0x18001f62c  mov     rcx, [rsi+10h]
0x18001f630  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x18001f635  mov     edi, eax
0x18001f637  test    eax, eax
0x18001f639  js      loc_1800200EB
0x18001f63f  mov     rcx, [rbp+4Fh+lpsz]; pv
0x18001f643  call    cs:__imp_CoTaskMemFree
0x18001f649  jmp     loc_1800200A5
0x18001f64e  test    r12b, r12b
0x18001f651  jnz     short loc_18001F6A8
0x18001f653  mov     dword ptr [rbp+4Fh+Block], edx
0x18001f656  lea     rcx, [rsi+38h]
0x18001f65a  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlReader@@$1?_GUID_7279fc81_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlReader@@XZ; _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x18001f65f  mov     r8, rax
0x18001f662  mov     rcx, [rax]
0x18001f665  mov     rax, [rcx+30h]
0x18001f669  lea     rdx, [rbp+4Fh+Block]
0x18001f66d  mov     rcx, r8
0x18001f670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f675  mov     edi, eax
0x18001f677  test    eax, eax
0x18001f679  jns     short loc_18001F68A
0x18001f67b  mov     edx, eax; int
0x18001f67d  mov     rcx, rsi; this
0x18001f680  call    ?SetErrorInfoXmlLite@TaskXmlReader@@AEAAJJ@Z; TaskXmlReader::SetErrorInfoXmlLite(long)
0x18001f685  jmp     loc_1800200E9
0x18001f68a  jnz     short loc_18001F692
0x18001f68c  cmp     dword ptr [rbp+4Fh+Block], 0Fh
0x18001f690  jz      short loc_18001F6A8
0x18001f692  lea     r9, [rsi+40h]
0x18001f696  mov     r8d, r14d
0x18001f699  mov     edx, 80041318h
0x18001f69e  mov     rcx, rsi
0x18001f6a1  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJW4TaskXmlNodeId@@AEAUXmlParserTempString@@@Z; TaskXmlReader::SetErrorInfo(long,TaskXmlNodeId,XmlParserTempString &)
0x18001f6a6  mov     edi, eax
0x18001f6a8  mov     [rbp+4Fh+var_70], 0
0x18001f6b0  cmp     byte ptr [rsi+28h], 0
0x18001f6b4  jz      loc_18001FEFC
0x18001f6ba  xor     r8d, r8d
0x18001f6bd  jmp     loc_18001F88A
0x18001f6c2  lea     rdx, [rbp+4Fh+rclsid]; bool *
0x18001f6c6  mov     rcx, rsi; this
0x18001f6c9  call    ?LoadValue@TaskXmlReader@@AEAAJAEA_N@Z; TaskXmlReader::LoadValue(bool &)
0x18001f6ce  mov     edi, eax
0x18001f6d0  lea     rbx, [rsi+40h]
0x18001f6d4  test    eax, eax
0x18001f6d6  jns     short loc_18001F6EA
0x18001f6d8  mov     r9, rbx
0x18001f6db  mov     r8d, r14d
0x18001f6de  mov     edx, eax
0x18001f6e0  mov     rcx, rsi
0x18001f6e3  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJW4TaskXmlNodeId@@AEAUXmlParserTempString@@@Z; TaskXmlReader::SetErrorInfo(long,TaskXmlNodeId,XmlParserTempString &)
0x18001f6e8  mov     edi, eax
0x18001f6ea  mov     [rbp+4Fh+var_70], rbx
0x18001f6ee  cmp     byte ptr [rsi+28h], 0
0x18001f6f2  jz      loc_18001FEFC
0x18001f6f8  mov     r8b, byte ptr [rbp+4Fh+rclsid.Data1]
0x18001f6fc  mov     edx, r14d
0x18001f6ff  mov     rcx, [rsi+10h]
0x18001f703  call    ?ElementBool@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@_N@Z; TaskXmlWriter::ElementBool(TaskXmlNodeId,bool)
0x18001f708  jmp     loc_18001F896
0x18001f70d  lea     r15, [rsi+40h]
0x18001f711  mov     rcx, r15; this
0x18001f714  call    ?Clear@XmlParserTempString@@QEAAXXZ; XmlParserTempString::Clear(void)
0x18001f719  test    r12b, r12b
0x18001f71c  jnz     short loc_18001F743
0x18001f71e  mov     rdx, r15; struct XmlParserTempString *
0x18001f721  mov     rcx, rsi; this
0x18001f724  call    ?LoadRawValue@TaskXmlReader@@AEAAJAEAUXmlParserTempString@@@Z; TaskXmlReader::LoadRawValue(XmlParserTempString &)
0x18001f729  mov     edi, eax
0x18001f72b  test    eax, eax
0x18001f72d  jns     short loc_18001F743
0x18001f72f  mov     edx, eax
0x18001f731  mov     r8d, r14d
0x18001f734  mov     rcx, rsi
0x18001f737  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJW4TaskXmlNodeId@@@Z; TaskXmlReader::SetErrorInfo(long,TaskXmlNodeId)
0x18001f73c  mov     edi, eax
0x18001f73e  jmp     loc_18001FEFC
0x18001f743  mov     edx, 2
0x18001f748  cmp     ebx, edx
0x18001f74a  jz      short loc_18001F751
0x18001f74c  cmp     ebx, 7
0x18001f74f  jnz     short loc_18001F76C
0x18001f751  cmp     dword ptr [r15], 0
0x18001f755  jnz     short loc_18001F76C
0x18001f757  mov     r9, r15
0x18001f75a  mov     r8d, r14d
0x18001f75d  mov     edx, 80041318h
0x18001f762  mov     rcx, rsi
0x18001f765  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJW4TaskXmlNodeId@@AEAUXmlParserTempString@@@Z; TaskXmlReader::SetErrorInfo(long,TaskXmlNodeId,XmlParserTempString &)
0x18001f76a  jmp     short loc_18001F73C
0x18001f76c  cmp     ebx, 6
0x18001f76f  jnz     short loc_18001F777
0x18001f771  cmp     dword ptr [r15], 0
0x18001f775  jz      short loc_18001F757
0x18001f777  mov     [rbp+4Fh+var_70], r15
0x18001f77b  cmp     byte ptr [rsi+28h], 0
0x18001f77f  jz      loc_18001FEFC
0x18001f785  mov     ecx, r14d
0x18001f788  sub     ecx, 6
0x18001f78b  jz      short loc_18001F7EA
0x18001f78d  sub     ecx, edx
0x18001f78f  jz      short loc_18001F7EA
0x18001f791  sub     ecx, edx
0x18001f793  jz      short loc_18001F7EA
0x18001f795  sub     ecx, 1
0x18001f798  jz      short loc_18001F7EA
  ... truncated ...
```
