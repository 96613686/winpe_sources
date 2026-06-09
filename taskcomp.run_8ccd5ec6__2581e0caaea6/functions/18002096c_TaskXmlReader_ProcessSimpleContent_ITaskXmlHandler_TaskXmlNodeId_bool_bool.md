# TaskXmlReader::ProcessSimpleContent(ITaskXmlHandler *,TaskXmlNodeId,bool,bool &)

- ea: `0x18002096c`
- end: `0x18002170a`
- name: `?ProcessSimpleContent@TaskXmlReader@@AEAAJPEAUITaskXmlHandler@@W4TaskXmlNodeId@@_NAEA_N@Z`
- size: `3486`
- prototype: ``
- caller_count: `2`
- callee_count: `37`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180003858`
- `0x1800207d4`

## callees

- `0x1800033d0`
- `0x180007988`
- `0x180007994`
- `0x18000a99c`
- `0x18000edd8`
- `0x18001d404`
- `0x18001da84`
- `0x18001daa8`
- `0x18001db08`
- `0x18001dda4`
- `0x18001de84`
- `0x18001dedc`
- `0x18001df2c`
- `0x18001e5e8`
- `0x18001ea5c`
- `0x18001ea88`
- `0x18001eb48`
- `0x18001ebf4`
- `0x18001ecb8`
- `0x18001ed88`
- `0x18001eff4`
- `0x18001f0fc`
- `0x18001f1a8`
- `0x18001f430`
- `0x18001f4c0`
- `0x18001f594`
- `0x18001f7b0`
- `0x18001f85c`
- `0x18001f938`
- `0x18001fcb0`
- `0x18002096c`
- `0x180021aec`
- `0x180021b4c`
- `0x180021bc8`
- `0x180021d40`
- `0x180021f58`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020c35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020c35`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180020bf4`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180020bf4`

## string_xrefs

- `0x180020f13`: `InteractiveToken`
- `0x180020f01`: `InteractiveTokenOrPassword`
- `0x180021176`: `LeastPrivilege`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TaskXmlReader::ProcessSimpleContent(__int64 a1, __int64 a2, unsigned int a3, char a4, _BYTE *a5)
{
  __int64 v7; // r13
  int v9; // ebx
  int v10; // eax
  int v11; // edi
  int v12; // eax
  __int64 Data1_low; // r8
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
  __int64 v26; // r8
  unsigned int *v27; // r15
  int v28; // eax
  __int64 v29; // rdx
  int v30; // eax
  __int64 v31; // r12
  const unsigned __int16 *v32; // r12
  unsigned int v33; // edi
  void *v34; // r11
  void *v35; // rcx
  void *v36; // rbx
  __int64 v37; // rdx
  int Logon; // eax
  unsigned int v39; // eax
  const unsigned __int16 *v40; // r8
  __int64 v41; // rdx
  int v42; // eax
  int v43; // ebx
  int v44; // ebx
  int v45; // ebx
  int v46; // ebx
  int v47; // ebx
  int v48; // eax
  int DayOfMonth; // eax
  __int64 v50; // rdx
  bool v51; // zf
  __int64 v52; // rcx
  int v53; // eax
  unsigned int *v54; // rbx
  int InstancePolicy; // eax
  int Week; // eax
  int RawValue; // edi
  unsigned int Data1; // eax
  int Value; // eax
  unsigned int v60; // eax
  int v61; // edi
  unsigned int i; // r9d
  int v63; // r10d
  unsigned int v64; // edx
  int HexString; // eax
  unsigned int v66; // r15d
  unsigned int v67; // r12d
  unsigned int v68; // r13d
  unsigned int v69; // r9d
  unsigned int v70; // r10d
  unsigned int v71; // r11d
  _BYTE *v72; // rbx
  __int64 v73; // r8
  int v74; // edi
  int v75; // edi
  unsigned int v76; // eax
  unsigned __int16 v78[2]; // [rsp+30h] [rbp-71h] BYREF
  unsigned __int16 v79; // [rsp+34h] [rbp-6Dh] BYREF
  unsigned __int16 v80[2]; // [rsp+38h] [rbp-69h] BYREF
  unsigned __int16 v81; // [rsp+3Ch] [rbp-65h] BYREF
  unsigned __int16 v82[2]; // [rsp+40h] [rbp-61h] BYREF
  unsigned __int16 v83[6]; // [rsp+44h] [rbp-5Dh] BYREF
  _BYTE v84[16]; // [rsp+50h] [rbp-51h] BYREF
  __int16 v85; // [rsp+60h] [rbp-41h]
  unsigned __int16 v86; // [rsp+62h] [rbp-3Fh]
  unsigned __int16 v87; // [rsp+64h] [rbp-3Dh]
  unsigned __int16 v88; // [rsp+66h] [rbp-3Bh]
  unsigned __int16 v89; // [rsp+68h] [rbp-39h]
  unsigned __int16 v90; // [rsp+6Ah] [rbp-37h]
  unsigned __int16 v91; // [rsp+6Ch] [rbp-35h]
  IID rclsid; // [rsp+70h] [rbp-31h] BYREF
  unsigned int *v93; // [rsp+80h] [rbp-21h]
  void *v94; // [rsp+88h] [rbp-19h]
  unsigned int v95; // [rsp+90h] [rbp-11h]
  __int64 v96; // [rsp+A0h] [rbp-1h] BYREF
  int v97; // [rsp+A8h] [rbp+7h]
  unsigned __int16 v98; // [rsp+ACh] [rbp+Bh]
  LPOLESTR lpsz; // [rsp+B0h] [rbp+Fh] BYREF
  void *Block; // [rsp+100h] [rbp+5Fh] BYREF
  __int64 v101; // [rsp+108h] [rbp+67h]

  v101 = a2;
  v7 = a2;
  ITaskXmlHandler::Data::Data((ITaskXmlHandler::Data *)v84);
  *(_BYTE *)(a1 + 1112) = 1;
  v9 = *(_DWORD *)(Schema::GetEntry(a1 + 1116, a3) + 28);
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
        v54 = (unsigned int *)(a1 + 64);
        if ( Value < 0 )
          v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)Value, a3, a1 + 64);
        v60 = (unsigned int)Block;
        *(_DWORD *)(a1 + 1116) = (_DWORD)Block;
        rclsid.Data1 = v60;
        goto LABEL_156;
      }
      v43 = v9 - 14;
      if ( v43 )
      {
        v44 = v43 - 1;
        if ( !v44 )
        {
          LOWORD(rclsid.Data1) = 0;
          Week = TaskXmlReader::LoadWeek((TaskXmlReader *)a1, (unsigned __int16 *)&rclsid);
          v11 = Week;
          if ( Week < 0 )
            v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)Week, a3, a1 + 64);
          v93 = (unsigned int *)(a1 + 64);
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_221;
          v50 = 70;
          v51 = LOWORD(rclsid.Data1) == 5;
          goto LABEL_148;
        }
        v45 = v44 - 1;
        if ( !v45 )
        {
          InstancePolicy = TaskXmlReader::LoadInstancePolicy((TaskXmlReader *)a1, (enum JobFlags::JobFlag *)&rclsid);
          v11 = InstancePolicy;
          if ( InstancePolicy < 0 )
            v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)InstancePolicy, a3, a1 + 64);
          v93 = (unsigned int *)(a1 + 64);
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_221;
          v14 = TaskXmlWriter::ElementMultipleInstancesPolicy(*(_QWORD *)(a1 + 16), rclsid.Data1);
          goto LABEL_104;
        }
        v46 = v45 - 1;
        if ( v46 )
        {
          v47 = v46 - 1;
          if ( v47 )
          {
            if ( v47 == 1 )
            {
              rclsid.Data1 = 0;
              v48 = TaskXmlReader::LoadSessionStateChange((TaskXmlReader *)a1, &rclsid.Data1);
              v11 = v48;
              if ( v48 < 0 )
                v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v48, a3, a1 + 64);
              v93 = (unsigned int *)(a1 + 64);
              if ( !*(_BYTE *)(a1 + 40) )
                goto LABEL_221;
              if ( LOWORD(rclsid.Data1) != 1 )
              {
                switch ( LOWORD(rclsid.Data1) )
                {
                  case 2u:
                    v40 = L"ConsoleDisconnect";
                    goto LABEL_143;
                  case 3u:
                    v40 = L"RemoteConnect";
                    goto LABEL_143;
                  case 4u:
                    v40 = L"RemoteDisconnect";
                    goto LABEL_143;
                  case 7u:
                    v40 = L"SessionLock";
                    goto LABEL_143;
                  case 8u:
                    v40 = L"SessionUnlock";
LABEL_143:
                    v41 = 38;
                    goto LABEL_119;
                }
              }
              v40 = L"ConsoleConnect";
              goto LABEL_143;
            }
LABEL_186:
            v29 = 2147750678LL;
            goto LABEL_71;
          }
          LOWORD(rclsid.Data1) = 0;
          DayOfMonth = TaskXmlReader::LoadDayOfMonth((TaskXmlReader *)a1, (unsigned __int16 *)&rclsid);
          v11 = DayOfMonth;
          if ( DayOfMonth < 0 )
            v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)DayOfMonth, a3, a1 + 64);
          v93 = (unsigned int *)(a1 + 64);
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_221;
          v50 = 68;
          v51 = LOWORD(rclsid.Data1) == 32;
LABEL_148:
          v52 = *(_QWORD *)(a1 + 16);
          if ( v51 )
          {
            v11 = TaskXmlWriter::Element(v52, v50, L"Last");
            if ( v11 >= 0 )
              goto LABEL_221;
          }
          else
          {
            v11 = TaskXmlWriter::ElementInt(v52, v50, LOWORD(rclsid.Data1));
          }
          if ( v11 < 0 )
            goto LABEL_255;
          goto LABEL_221;
        }
        v53 = TaskXmlReader::SkipElement((TaskXmlReader *)a1);
        v11 = v53;
        v54 = (unsigned int *)(a1 + 64);
        if ( v53 < 0 )
          v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v53, a3, a1 + 64);
LABEL_156:
        v93 = v54;
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
      v93 = (unsigned int *)(a1 + 64);
      if ( !*(_BYTE *)(a1 + 40) || (Data1 & 0x1000000) == 0 )
        goto LABEL_221;
      v40 = L"HighestAvailable";
      goto LABEL_118;
    }
    if ( v9 != 21 )
    {
      if ( v9 != 22 )
      {
        switch ( v9 )
        {
          case 23:
            v66 = 0;
            v67 = 0;
            v68 = 0;
            LODWORD(lpsz) = 0;
            v11 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
            if ( v11 >= 0 )
            {
              v96 = 0;
              v97 = 0;
              v98 = 0;
              if ( (int)TSParser::ParseTimePeriod(
                          *(const unsigned __int16 **)(a1 + 72),
                          *(unsigned int *)(a1 + 64),
                          (struct TSTimePeriod *)&v96) >= 0 )
              {
                v66 = (unsigned __int16)v96;
                v67 = WORD1(v96);
                v68 = WORD2(v96);
                LODWORD(lpsz) = v98;
                v11 = 0;
              }
              else
              {
                v11 = -2147216616;
              }
            }
            LOWORD(Block) = 0;
            v78[0] = 0;
            v80[0] = 0;
            v79 = 0;
            v81 = 0;
            v82[0] = 0;
            v83[0] = 0;
            if ( v11 < 0
              || (v11 = ULongToUShort(v66, (unsigned __int16 *)&Block), v11 < 0)
              || (v11 = ULongToUShort(v67, v78), v11 < 0)
              || (v11 = ULongToUShort(v68, &v79), v11 < 0)
              || (v11 = ULongToUShort(v69, v80), v11 < 0)
              || (v11 = ULongToUShort(v70, &v81), v11 < 0)
              || (v11 = ULongToUShort(v71, v82), v11 < 0)
              || (v11 = ULongToUShort((unsigned int)lpsz, v83), v11 < 0) )
            {
              v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v11, a3, a1 + 64);
            }
            else
            {
              v85 = (__int16)Block;
              v86 = v78[0];
              v87 = v79;
              v88 = v80[0];
              v89 = v81;
              v90 = v82[0];
              v91 = v83[0];
            }
            v93 = (unsigned int *)(a1 + 64);
            if ( *(_BYTE *)(a1 + 40) )
            {
              v11 = TaskXmlWriter::Element(*(_QWORD *)(a1 + 16), a3, *(_QWORD *)(a1 + 72));
              if ( v11 < 0 )
                goto LABEL_255;
            }
            v7 = v101;
            goto LABEL_221;
          case 24:
            goto LABEL_198;
          case 25:
            rclsid.Data1 = 0;
            v61 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
            if ( v61 < 0 )
            {
LABEL_194:
              v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v61, a3, a1 + 64);
              Data1_low = rclsid.Data1;
            }
            else
            {
              Data1_low = 0;
              rclsid.Data1 = 0;
              for ( i = 0; i < *(_DWORD *)(a1 + 64); ++i )
              {
                v63 = *(unsigned __int16 *)(*(_QWORD *)(a1 + 72) + 2LL * (int)i);
                if ( (unsigned __int16)(v63 - 48) <= 9u )
                {
                  v64 = Data1_low;
                  Data1_low = (unsigned int)(v63 + 2 * (Data1_low + 4 * (Data1_low - 6)));
                  rclsid.Data1 = Data1_low;
                  if ( (unsigned int)Data1_low >= v64 )
                    continue;
                }
                v61 = -2147216616;
                goto LABEL_194;
              }
              v11 = 0;
            }
            v93 = (unsigned int *)(a1 + 64);
            if ( *(_BYTE *)(a1 + 40) )
              goto LABEL_22;
            goto LABEL_221;
          case 26:
LABEL_198:
            HexString = TaskXmlReader::LoadHexString((TaskXmlReader *)a1);
            v11 = HexString;
            v27 = (unsigned int *)(a1 + 64);
            if ( HexString < 0 )
              v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)HexString, a3, a1 + 64);
            if ( v9 == 24 && *v27 != 16 )
              goto LABEL_76;
            v93 = (unsigned int *)(a1 + 64);
            if ( !*(_BYTE *)(a1 + 40) )
              goto LABEL_221;
            v14 = TaskXmlWriter::ElementHexString(*(_QWORD *)(a1 + 16), a3, v94, v95);
            goto LABEL_104;
        }
        goto LABEL_186;
      }
      *(_QWORD *)&rclsid.Data1 = 0;
      v74 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
      if ( v74 >= 0 )
      {
        if ( *(_DWORD *)(a1 + 64) )
        {
          Block = 0;
          if ( (unsigned int)User::LookupPrivilege(*(LPCWSTR *)(a1 + 72), (PLUID)&Block) )
          {
            *(_QWORD *)&rclsid.Data1 = 1LL << (char)Block;
            v11 = 0;
LABEL_233:
            v93 = (unsigned int *)(a1 + 64);
            if ( !*(_BYTE *)(a1 + 40) )
              goto LABEL_221;
            v19 = *(int **)(a1 + 72);
            v37 = 135;
            goto LABEL_103;
          }
        }
        v74 = -2147216616;
      }
      v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v74, a3, a1 + 64);
      goto LABEL_233;
    }
    rclsid.Data1 = 0;
    v75 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
    if ( v75 >= 0 )
    {
      if ( *(_DWORD *)(a1 + 64) )
      {
        if ( XmlParserTempString::IsEqualTo((XmlParserTempString *)(a1 + 64), L"None", 4u) )
        {
          v76 = 0x8000000;
LABEL_241:
          rclsid.Data1 = v76;
          v11 = 0;
LABEL_244:
          v93 = (unsigned int *)(a1 + 64);
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_221;
          if ( (v76 & 0x8000000) == 0 )
          {
            if ( (v76 & 0x10000000) == 0 )
              goto LABEL_221;
            v14 = TaskXmlWriter::ElementProcessTokenSidType(*(_QWORD *)(a1 + 16), a3, 1);
            goto LABEL_104;
          }
          v42 = TaskXmlWriter::ElementProcessTokenSidType(*(_QWORD *)(a1 + 16), a3, 0);
LABEL_247:
          v11 = v42;
          if ( v42 < 0 )
            goto LABEL_255;
          goto LABEL_248;
        }
        if ( XmlParserTempString::IsEqualTo((XmlParserTempString *)(a1 + 64), L"Unrestricted", 0xCu) )
        {
          v76 = 0x10000000;
          goto LABEL_241;
        }
      }
      v75 = -2147216616;
    }
    v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v75, a3, a1 + 64);
    v76 = rclsid.Data1;
    goto LABEL_244;
  }
  if ( v9 == 13 )
  {
    Logon = TaskXmlReader::LoadLogon((TaskXmlReader *)a1, (enum JobFlags::JobFlag *)&rclsid);
    v11 = Logon;
    if ( Logon < 0 )
      v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)Logon, a3, a1 + 64);
    v93 = (unsigned int *)(a1 + 64);
    if ( !*(_BYTE *)(a1 + 40) )
      goto LABEL_221;
    v39 = rclsid.Data1 & 0xFC000;
    if ( (rclsid.Data1 & 0xFC000) == 0x4000 )
    {
      v40 = L"S4U";
    }
    else
    {
      switch ( v39 )
      {
        case 0x10000u:
          v40 = L"InteractiveToken";
          break;
        case 0x40000u:
          v40 = L"Password";
          break;
        case 0x80000u:
          v40 = L"InteractiveTokenOrPassword";
          break;
        default:
          v11 = -2147024809;
          goto LABEL_255;
      }
    }
LABEL_118:
    v41 = a3;
LABEL_119:
    v42 = TaskXmlWriter::Element(*(_QWORD *)(a1 + 16), v41, v40);
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
          v23 = _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(a1 + 56);
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
        v93 = 0;
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
          XmlParserTempString::Clear((XmlParserTempString *)(a1 + 64));
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
            v93 = (unsigned int *)(a1 + 64);
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
      v93 = (unsigned int *)(a1 + 64);
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
      v11 = TaskXmlWriter::Element(*(_QWORD *)(a1 + 16), a3, lpsz);
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
    v93 = (unsigned int *)(a1 + 64);
    if ( !*(_BYTE *)(a1 + 40) )
      goto LABEL_221;
    LOBYTE(v26) = rclsid.Data1;
    v14 = TaskXmlWriter::ElementBool(*(_QWORD *)(a1 + 16), a3, v26);
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
            v93 = (unsigned int *)(a1 + 64);
LABEL_20:
            if ( *(_BYTE *)(a1 + 40) )
            {
              Data1_low = LOWORD(rclsid.Data1);
LABEL_22:
              v14 = TaskXmlWriter::ElementInt(*(_QWORD *)(a1 + 16), a3, Data1_low);
              goto LABEL_104;
            }
LABEL_221:
            v31 = a1 + 1116;
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
        if ( (int)TSParser::ParseDateTime(*(const unsigned __int16 **)(a1 + 72), *v15, (struct TSTime *)v84) < 0 )
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
        v93 = v15;
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
    v27 = (unsigned int *)(a1 + 64);
    XmlParserTempString::Clear((XmlParserTempString *)(a1 + 64));
    if ( !a4 )
    {
      v28 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)(a1 + 64));
      v11 = v28;
      if ( v28 < 0 )
      {
        v29 = (unsigned int)v28;
LABEL_71:
        v30 = TaskXmlReader::SetErrorInfo(a1, v29, a3);
LABEL_72:
        v11 = v30;
        goto LABEL_221;
      }
    }
    if ( (v9 != 2 && v9 != 7 || *v27) && (v9 != 6 || *v27) )
    {
      v93 = (unsigned int *)(a1 + 64);
      if ( !*(_BYTE *)(a1 + 40) )
        goto LABEL_221;
      if ( a3 != 6 && a3 != 8 && a3 != 10 && a3 != 11 && a3 != 112 && a3 != 115 && a3 != 121 && a3 - 129 >= 2 )
      {
        v31 = a1 + 1116;
        if ( *(_DWORD *)(Schema::GetEntry(a1 + 1116, a3) + 24) != 2 )
          v11 = TaskXmlWriter::Element(*(_QWORD *)(a1 + 16), a3, *(_QWORD *)(a1 + 72));
        if ( v11 < 0 )
          goto LABEL_255;
        goto LABEL_222;
      }
      v32 = *(const unsigned __int16 **)(a1 + 72);
      if ( v32 )
      {
        v33 = *v27;
        if ( *v27 )
        {
          Block = operator new[](saturated_mul(v33 + 1, 2u));
          v11 = StringCchCopyNW((unsigned __int16 *)Block, v33 + 1, v32, v33);
          if ( v11 < 0 )
          {
            v35 = v34;
LABEL_96:
            operator delete(v35);
            goto LABEL_255;
          }
          v11 = TaskXmlReader::LoadTranslatedString(&Block);
          if ( v11 < 0 )
          {
            v35 = Block;
            goto LABEL_96;
          }
          v36 = Block;
          v11 = TaskXmlWriter::Element(*(_QWORD *)(a1 + 16), a3, Block);
          v35 = v36;
          if ( v11 < 0 )
            goto LABEL_96;
          operator delete(v36);
          goto LABEL_248;
        }
      }
      v19 = &dword_18005260C;
LABEL_102:
      v37 = a3;
LABEL_103:
      v14 = TaskXmlWriter::Element(*(_QWORD *)(a1 + 16), v37, v19);
      goto LABEL_104;
    }
LABEL_76:
    v30 = TaskXmlReader::SetErrorInfo(a1, 2147750680LL, a3, v27);
    goto LABEL_72;
  }
  *(_BYTE *)(a1 + 1112) = 0;
LABEL_249:
  v31 = a1 + 1116;
LABEL_223:
  if ( v7 )
  {
    v72 = a5;
    v11 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _BYTE *, _BYTE))(*(_QWORD *)v7 + 8LL))(
            v7,
            v31,
            a3,
            v84,
            *a5);
    *v72 = 1;
    if ( v11 < 0 )
    {
      if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v7 + 24LL))(v7) )
        v73 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v7 + 24LL))(v7);
      else
        v73 = a3;
      v10 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v11, v73, a1 + 64);
      goto LABEL_254;
    }
  }
LABEL_255:
  operator delete(v94);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18002096c  mov     [rsp-8+arg_10], rbx
0x180020971  mov     [rsp-8+arg_8], rdx
0x180020976  push    rbp
0x180020977  push    rsi
0x180020978  push    rdi
0x180020979  push    r12
0x18002097b  push    r13
0x18002097d  push    r14
0x18002097f  push    r15
0x180020981  lea     rbp, [rsp-1Fh]
0x180020986  sub     rsp, 0C0h
0x18002098d  mov     r12b, r9b
0x180020990  mov     r14d, r8d
0x180020993  mov     r13, rdx
0x180020996  mov     rsi, rcx
0x180020999  lea     rcx, [rbp+4Fh+var_A0]; this
0x18002099d  call    ??0Data@ITaskXmlHandler@@QEAA@XZ; ITaskXmlHandler::Data::Data(void)
0x1800209a2  nop
0x1800209a3  mov     byte ptr [rsi+458h], 1
0x1800209aa  lea     r15, [rsi+45Ch]
0x1800209b1  mov     edx, r14d
0x1800209b4  mov     rcx, r15
0x1800209b7  call    ?GetEntry@Schema@@AEBAAEBUSchemaEntry@@W4TaskXmlNodeId@@@Z; Schema::GetEntry(TaskXmlNodeId)
0x1800209bc  mov     ebx, [rax+1Ch]
0x1800209bf  mov     ecx, ebx
0x1800209c1  xor     edx, edx
0x1800209c3  test    ebx, ebx
0x1800209c5  jz      short loc_1800209F5
0x1800209c7  sub     ecx, 1
0x1800209ca  jz      short loc_1800209F5
0x1800209cc  sub     ecx, 8
0x1800209cf  jz      short loc_1800209F5
0x1800209d1  sub     ecx, 2
0x1800209d4  jz      short loc_1800209F5
0x1800209d6  cmp     ecx, 0Fh
0x1800209d9  jz      short loc_1800209F5
0x1800209db  test    r12b, r12b
0x1800209de  jz      short loc_1800209F5
0x1800209e0  mov     r8d, r14d
0x1800209e3  mov     edx, 80041318h
0x1800209e8  mov     rcx, rsi
0x1800209eb  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJW4TaskXmlNodeId@@@Z; TaskXmlReader::SetErrorInfo(long,TaskXmlNodeId)
0x1800209f0  jmp     loc_1800216E1
0x1800209f5  cmp     ebx, 0Dh
0x1800209f8  jg      loc_180020F34
0x1800209fe  jz      loc_180020E9D
0x180020a04  xor     edi, edi
0x180020a06  cmp     ebx, 6
0x180020a09  jg      loc_180020B19
0x180020a0f  jz      loc_180020D05
0x180020a15  mov     ecx, ebx
0x180020a17  test    ebx, ebx
0x180020a19  jz      loc_180020B0E
0x180020a1f  sub     ecx, 1
0x180020a22  jz      loc_180020D05
0x180020a28  sub     ecx, 1
0x180020a2b  jz      loc_180020D05
0x180020a31  sub     ecx, 1
0x180020a34  jz      loc_180020ACF
0x180020a3a  sub     ecx, 1
0x180020a3d  jz      short loc_180020A9A
0x180020a3f  cmp     ecx, 1
0x180020a42  jnz     loc_18002125E
0x180020a48  xor     eax, eax
0x180020a4a  mov     word ptr [rbp+4Fh+rclsid.Data1], ax
0x180020a4e  lea     rdx, [rbp+4Fh+rclsid]; unsigned __int16 *
0x180020a52  mov     rcx, rsi; this
0x180020a55  call    ?LoadValue@TaskXmlReader@@AEAAJAEAG@Z; TaskXmlReader::LoadValue(ushort &)
0x180020a5a  mov     edi, eax
0x180020a5c  lea     rbx, [rsi+40h]
0x180020a60  test    eax, eax
0x180020a62  jns     short loc_180020A76
0x180020a64  mov     r9, rbx
0x180020a67  mov     r8d, r14d
0x180020a6a  mov     edx, eax
0x180020a6c  mov     rcx, rsi
0x180020a6f  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJW4TaskXmlNodeId@@AEAUXmlParserTempString@@@Z; TaskXmlReader::SetErrorInfo(long,TaskXmlNodeId,XmlParserTempString &)
0x180020a74  mov     edi, eax
0x180020a76  mov     [rbp+4Fh+var_70], rbx
0x180020a7a  cmp     byte ptr [rsi+28h], 0
0x180020a7e  jz      loc_1800214F4
0x180020a84  movzx   r8d, word ptr [rbp+4Fh+rclsid.Data1]
0x180020a89  mov     edx, r14d
0x180020a8c  mov     rcx, [rsi+10h]
0x180020a90  call    ?ElementInt@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@H@Z; TaskXmlWriter::ElementInt(TaskXmlNodeId,int)
0x180020a95  jmp     loc_180020E8E
0x180020a9a  lea     rbx, [rsi+40h]
0x180020a9e  mov     rdx, rbx; struct XmlParserTempString *
0x180020aa1  mov     rcx, rsi; this
0x180020aa4  call    ?LoadRawValue@TaskXmlReader@@AEAAJAEAUXmlParserTempString@@@Z; TaskXmlReader::LoadRawValue(XmlParserTempString &)
0x180020aa9  mov     edi, eax
0x180020aab  test    eax, eax
0x180020aad  js      short loc_180020AC7
0x180020aaf  mov     edx, [rbx]; unsigned __int64
0x180020ab1  lea     r8, [rbp+4Fh+var_A0]; struct TSTime *
0x180020ab5  mov     rcx, [rsi+48h]; unsigned __int16 *
0x180020ab9  call    ?ParseDateTime@TSParser@@SAJPEBG_KAEAVTSTime@@@Z; TSParser::ParseDateTime(ushort const *,unsigned __int64,TSTime &)
0x180020abe  test    eax, eax
0x180020ac0  jns     short loc_180020ACB
0x180020ac2  mov     edi, 80041318h
0x180020ac7  mov     edx, edi
0x180020ac9  jmp     short loc_180020AE7
0x180020acb  xor     edi, edi
0x180020acd  jmp     short loc_180020AF7
0x180020acf  lea     rdx, [rbp+4Fh+rclsid]; unsigned int *
0x180020ad3  mov     rcx, rsi; this
0x180020ad6  call    ?LoadTimespan@TaskXmlReader@@AEAAJAEAK@Z; TaskXmlReader::LoadTimespan(ulong &)
0x180020adb  lea     rbx, [rsi+40h]
0x180020adf  test    eax, eax
0x180020ae1  mov     edi, eax
0x180020ae3  jns     short loc_180020AF7
0x180020ae5  mov     edx, eax
0x180020ae7  mov     r9, rbx
0x180020aea  mov     r8d, r14d
0x180020aed  mov     rcx, rsi
0x180020af0  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJW4TaskXmlNodeId@@AEAUXmlParserTempString@@@Z; TaskXmlReader::SetErrorInfo(long,TaskXmlNodeId,XmlParserTempString &)
0x180020af5  mov     edi, eax
0x180020af7  mov     [rbp+4Fh+var_70], rbx
0x180020afb  cmp     byte ptr [rsi+28h], 0
0x180020aff  jz      loc_1800214F4
0x180020b05  mov     r8, [rbx+8]
0x180020b09  jmp     loc_180020E82
0x180020b0e  mov     [rsi+458h], dl
0x180020b14  jmp     loc_1800216A4
0x180020b19  mov     ecx, ebx
0x180020b1b  sub     ecx, 7
0x180020b1e  jz      loc_180020D05
0x180020b24  sub     ecx, 1
0x180020b27  jz      loc_180020CBA
0x180020b2d  sub     ecx, 1
0x180020b30  jz      loc_180020C46
0x180020b36  sub     ecx, 1
0x180020b39  jz      short loc_180020BAE
0x180020b3b  sub     ecx, 1
0x180020b3e  jz      short loc_180020B89
0x180020b40  cmp     ecx, 1
0x180020b43  jnz     loc_18002125E
0x180020b49  lea     rdx, [rbp+4Fh+rclsid]; unsigned __int16 *
0x180020b4d  mov     rcx, rsi; this
0x180020b50  call    ?LoadValue@TaskXmlReader@@AEAAJAEAG@Z; TaskXmlReader::LoadValue(ushort &)
0x180020b55  mov     edi, eax
0x180020b57  test    eax, eax
0x180020b59  jns     short loc_180020B5F
0x180020b5b  mov     edx, eax
0x180020b5d  jmp     short loc_180020B6B
0x180020b5f  cmp     word ptr [rbp+4Fh+rclsid.Data1], 0Ah
0x180020b64  jbe     short loc_180020B7C
0x180020b66  mov     edx, 80041318h
0x180020b6b  lea     r9, [rsi+40h]
0x180020b6f  mov     r8d, r14d
0x180020b72  mov     rcx, rsi
0x180020b75  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJW4TaskXmlNodeId@@AEAUXmlParserTempString@@@Z; TaskXmlReader::SetErrorInfo(long,TaskXmlNodeId,XmlParserTempString &)
0x180020b7a  mov     edi, eax
0x180020b7c  lea     rax, [rsi+40h]
0x180020b80  mov     [rbp+4Fh+var_70], rax
0x180020b84  jmp     loc_180020A7A
0x180020b89  lea     rbx, [rsi+40h]
0x180020b8d  mov     rcx, rbx; this
0x180020b90  call    ?Clear@XmlParserTempString@@QEAAXXZ; XmlParserTempString::Clear(void)
0x180020b95  test    r12b, r12b
0x180020b98  jnz     loc_180020AF7
0x180020b9e  mov     rdx, rbx; struct XmlParserTempString *
0x180020ba1  mov     rcx, rsi; this
0x180020ba4  call    ?LoadRawValue@TaskXmlReader@@AEAAJAEAUXmlParserTempString@@@Z; TaskXmlReader::LoadRawValue(XmlParserTempString &)
0x180020ba9  jmp     loc_180020ADF
0x180020bae  lea     rdx, [rbp+4Fh+rclsid]; struct _GUID *
0x180020bb2  mov     rcx, rsi; this
0x180020bb5  call    ?LoadValue@TaskXmlReader@@AEAAJAEAU_GUID@@@Z; TaskXmlReader::LoadValue(_GUID &)
0x180020bba  mov     edi, eax
0x180020bbc  lea     rbx, [rsi+40h]
0x180020bc0  test    eax, eax
0x180020bc2  jns     short loc_180020BD6
0x180020bc4  mov     r9, rbx
0x180020bc7  mov     r8d, r14d
0x180020bca  mov     edx, eax
0x180020bcc  mov     rcx, rsi
0x180020bcf  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJW4TaskXmlNodeId@@AEAUXmlParserTempString@@@Z; TaskXmlReader::SetErrorInfo(long,TaskXmlNodeId,XmlParserTempString &)
0x180020bd4  mov     edi, eax
0x180020bd6  mov     [rbp+4Fh+var_70], rbx
0x180020bda  cmp     byte ptr [rsi+28h], 0
0x180020bde  jz      loc_1800214F4
0x180020be4  mov     [rbp+4Fh+lpsz], 0
0x180020bec  lea     rdx, [rbp+4Fh+lpsz]; lplpsz
0x180020bf0  lea     rcx, [rbp+4Fh+rclsid]; rclsid
0x180020bf4  call    cs:__imp_StringFromCLSID
0x180020bfb  nop     dword ptr [rax+rax+00h]
0x180020c00  test    eax, eax
0x180020c02  jz      short loc_180020C17
0x180020c04  jle     loc_1800216E1
0x180020c0a  movzx   eax, ax
0x180020c0d  or      eax, 80070000h
0x180020c12  jmp     loc_1800216E1
0x180020c17  mov     r8, [rbp+4Fh+lpsz]
0x180020c1b  mov     edx, r14d
0x180020c1e  mov     rcx, [rsi+10h]
0x180020c22  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180020c27  mov     edi, eax
0x180020c29  test    eax, eax
0x180020c2b  js      loc_1800216E3
0x180020c31  mov     rcx, [rbp+4Fh+lpsz]; pv
0x180020c35  call    cs:__imp_CoTaskMemFree
0x180020c3c  nop     dword ptr [rax+rax+00h]
0x180020c41  jmp     loc_18002169D
0x180020c46  test    r12b, r12b
0x180020c49  jnz     short loc_180020CA0
0x180020c4b  mov     dword ptr [rbp+4Fh+Block], edx
0x180020c4e  lea     rcx, [rsi+38h]
0x180020c52  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlReader@@$1?_GUID_7279fc81_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlReader@@XZ; _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x180020c57  mov     r8, rax
0x180020c5a  mov     rcx, [rax]
0x180020c5d  mov     rax, [rcx+30h]
0x180020c61  lea     rdx, [rbp+4Fh+Block]
0x180020c65  mov     rcx, r8
0x180020c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c6d  mov     edi, eax
0x180020c6f  test    eax, eax
0x180020c71  jns     short loc_180020C82
0x180020c73  mov     edx, eax; int
0x180020c75  mov     rcx, rsi; this
0x180020c78  call    ?SetErrorInfoXmlLite@TaskXmlReader@@AEAAJJ@Z; TaskXmlReader::SetErrorInfoXmlLite(long)
0x180020c7d  jmp     loc_1800216E1
0x180020c82  jnz     short loc_180020C8A
0x180020c84  cmp     dword ptr [rbp+4Fh+Block], 0Fh
0x180020c88  jz      short loc_180020CA0
0x180020c8a  lea     r9, [rsi+40h]
0x180020c8e  mov     r8d, r14d
0x180020c91  mov     edx, 80041318h
0x180020c96  mov     rcx, rsi
0x180020c99  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJW4TaskXmlNodeId@@AEAUXmlParserTempString@@@Z; TaskXmlReader::SetErrorInfo(long,TaskXmlNodeId,XmlParserTempString &)
0x180020c9e  mov     edi, eax
0x180020ca0  mov     [rbp+4Fh+var_70], 0
0x180020ca8  cmp     byte ptr [rsi+28h], 0
0x180020cac  jz      loc_1800214F4
0x180020cb2  xor     r8d, r8d
0x180020cb5  jmp     loc_180020E82
0x180020cba  lea     rdx, [rbp+4Fh+rclsid]; bool *
0x180020cbe  mov     rcx, rsi; this
0x180020cc1  call    ?LoadValue@TaskXmlReader@@AEAAJAEA_N@Z; TaskXmlReader::LoadValue(bool &)
0x180020cc6  mov     edi, eax
0x180020cc8  lea     rbx, [rsi+40h]
0x180020ccc  test    eax, eax
0x180020cce  jns     short loc_180020CE2
0x180020cd0  mov     r9, rbx
0x180020cd3  mov     r8d, r14d
0x180020cd6  mov     edx, eax
0x180020cd8  mov     rcx, rsi
0x180020cdb  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJW4TaskXmlNodeId@@AEAUXmlParserTempString@@@Z; TaskXmlReader::SetErrorInfo(long,TaskXmlNodeId,XmlParserTempString &)
0x180020ce0  mov     edi, eax
0x180020ce2  mov     [rbp+4Fh+var_70], rbx
0x180020ce6  cmp     byte ptr [rsi+28h], 0
0x180020cea  jz      loc_1800214F4
0x180020cf0  mov     r8b, byte ptr [rbp+4Fh+rclsid.Data1]
0x180020cf4  mov     edx, r14d
0x180020cf7  mov     rcx, [rsi+10h]
0x180020cfb  call    ?ElementBool@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@_N@Z; TaskXmlWriter::ElementBool(TaskXmlNodeId,bool)
0x180020d00  jmp     loc_180020E8E
0x180020d05  lea     r15, [rsi+40h]
0x180020d09  mov     rcx, r15; this
0x180020d0c  call    ?Clear@XmlParserTempString@@QEAAXXZ; XmlParserTempString::Clear(void)
0x180020d11  test    r12b, r12b
0x180020d14  jnz     short loc_180020D3B
0x180020d16  mov     rdx, r15; struct XmlParserTempString *
0x180020d19  mov     rcx, rsi; this
0x180020d1c  call    ?LoadRawValue@TaskXmlReader@@AEAAJAEAUXmlParserTempString@@@Z; TaskXmlReader::LoadRawValue(XmlParserTempString &)
0x180020d21  mov     edi, eax
0x180020d23  test    eax, eax
0x180020d25  jns     short loc_180020D3B
0x180020d27  mov     edx, eax
0x180020d29  mov     r8d, r14d
0x180020d2c  mov     rcx, rsi
0x180020d2f  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJW4TaskXmlNodeId@@@Z; TaskXmlReader::SetErrorInfo(long,TaskXmlNodeId)
0x180020d34  mov     edi, eax
0x180020d36  jmp     loc_1800214F4
0x180020d3b  mov     edx, 2
0x180020d40  cmp     ebx, edx
0x180020d42  jz      short loc_180020D49
0x180020d44  cmp     ebx, 7
0x180020d47  jnz     short loc_180020D64
0x180020d49  cmp     dword ptr [r15], 0
0x180020d4d  jnz     short loc_180020D64
0x180020d4f  mov     r9, r15
0x180020d52  mov     r8d, r14d
0x180020d55  mov     edx, 80041318h
0x180020d5a  mov     rcx, rsi
0x180020d5d  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJW4TaskXmlNodeId@@AEAUXmlParserTempString@@@Z; TaskXmlReader::SetErrorInfo(long,TaskXmlNodeId,XmlParserTempString &)
0x180020d62  jmp     short loc_180020D34
0x180020d64  cmp     ebx, 6
0x180020d67  jnz     short loc_180020D6F
0x180020d69  cmp     dword ptr [r15], 0
0x180020d6d  jz      short loc_180020D4F
0x180020d6f  mov     [rbp+4Fh+var_70], r15
0x180020d73  cmp     byte ptr [rsi+28h], 0
0x180020d77  jz      loc_1800214F4
0x180020d7d  mov     ecx, r14d
0x180020d80  sub     ecx, 6
0x180020d83  jz      short loc_180020DE2
0x180020d85  sub     ecx, edx
0x180020d87  jz      short loc_180020DE2
0x180020d89  sub     ecx, edx
0x180020d8b  jz      short loc_180020DE2
  ... truncated ...
```
