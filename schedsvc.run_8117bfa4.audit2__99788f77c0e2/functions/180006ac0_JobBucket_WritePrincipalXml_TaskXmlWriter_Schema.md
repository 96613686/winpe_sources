# JobBucket::WritePrincipalXml(TaskXmlWriter *,Schema *)

- ea: `0x180006ac0`
- end: `0x180007b3c`
- name: `?WritePrincipalXml@JobBucket@@QEBAJPEAVTaskXmlWriter@@PEAUSchema@@@Z`
- size: `4220`
- prototype: `__int64 __fastcall(JobBucket *__hidden this, struct TaskXmlWriter *, struct Schema *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000bc60`

## callees

- `0x180004818`
- `0x180006850`
- `0x180006ac0`
- `0x180007b44`
- `0x180009d60`
- `0x18000cb10`
- `0x18000d830`
- `0x180011e40`
- `0x1800258cc`
- `0x180027910`
- `0x18002fa10`
- `0x180030930`
- `0x180035e30`
- `0x1800373f0`
- `0x1800405e0`
- `0x180045a14`
- `0x180054824`
- `0x18005504c`
- `0x18006b434`
- `0x180088010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180007145`
- `OLEAUT32!__imp_SysAllocString` at `0x180007145`
- `OLEAUT32!__imp_SysStringLen` at `0x180006b7e`
- `OLEAUT32!__imp_SysStringLen` at `0x180006d05`
- `OLEAUT32!__imp_SysStringLen` at `0x180006b7e`
- `OLEAUT32!__imp_SysStringLen` at `0x180006d05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007166`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007166`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180006d38`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180006d38`

## string_xrefs

- `0x180006f36`: `InteractiveToken`
- `0x180007930`: `InteractiveTokenOrPassword`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall JobBucket::WritePrincipalXml(JobBucket *this, struct TaskXmlWriter *a2, struct Schema *a3)
{
  int v5; // eax
  int v6; // edx
  struct IErrorInfo *v7; // rdx
  int lpVtbl; // eax
  __int64 v9; // rcx
  __int64 result; // rax
  BSTR *v11; // rax
  UINT v12; // eax
  __int64 *v13; // rax
  __int64 v14; // rsi
  int v15; // eax
  int v16; // edx
  struct IErrorInfo *v17; // rdx
  int v18; // eax
  __int64 v19; // rcx
  int v20; // edx
  int v21; // r8d
  int v22; // ecx
  __int64 v23; // rdi
  __int64 Entry; // rax
  __int64 v25; // r11
  int v26; // eax
  int v27; // eax
  int v28; // edx
  struct IErrorInfo *v29; // rdx
  int v30; // eax
  __int64 v31; // rcx
  BSTR *v32; // rax
  UINT v33; // eax
  volatile signed __int32 *v34; // rdi
  __int64 v35; // rcx
  signed int LastError; // eax
  struct IErrorInfo *v37; // rdx
  const struct SchemaEntry * near *v38; // r8
  signed int v39; // esi
  int v40; // ecx
  int *v41; // rsi
  __int64 v42; // r12
  int v43; // eax
  __int64 *v44; // r9
  int v45; // eax
  __int64 v46; // rcx
  int v47; // eax
  int v48; // r14d
  int v49; // eax
  unsigned __int64 v50; // rdx
  const struct SchemaEntry * near *v51; // r8
  int v52; // eax
  __int64 v53; // rcx
  int v54; // esi
  __int64 v55; // r8
  int v56; // eax
  const unsigned __int16 *v57; // r8
  __int64 v58; // rcx
  int v59; // eax
  __int64 v60; // rcx
  __int64 v61; // rax
  __int64 *v62; // rax
  __int64 v63; // rsi
  int v64; // eax
  int v65; // eax
  __int64 v66; // rcx
  int v67; // eax
  int v68; // r14d
  __int64 v69; // rcx
  int v70; // eax
  __int64 v71; // rcx
  int v72; // eax
  __int64 v73; // rcx
  int started; // edi
  BSTR v75; // rsi
  __int64 v76; // r14
  int v77; // eax
  int v78; // eax
  __int64 v79; // rcx
  int v80; // eax
  __int64 v81; // rcx
  int v82; // eax
  __int64 v83; // rcx
  __int64 v84; // rcx
  __int64 v85; // rdi
  __int64 v86; // rsi
  volatile signed __int32 *v87; // rax
  struct IErrorInfo *v88; // rdx
  unsigned __int64 v89; // r9
  const unsigned __int64 near *v90; // r10
  __int64 v91; // r11
  unsigned __int64 v92; // r10
  __int64 v93; // rax
  unsigned __int64 v94; // r9
  const unsigned __int64 near *v95; // r10
  __int64 v96; // r11
  unsigned __int64 v97; // r10
  __int64 v98; // rax
  unsigned __int64 v99; // r9
  const unsigned __int64 near *v100; // r10
  __int64 v101; // r11
  unsigned __int64 v102; // r9
  __int64 v103; // rax
  const unsigned __int64 near *v104; // r8
  unsigned __int64 v105; // r10
  __int64 v106; // rax
  unsigned __int64 v107; // r10
  __int64 v108; // rax
  __int64 *v109; // rax
  __int64 v110; // r8
  unsigned __int64 v111; // rsi
  __int64 v112; // rax
  __int64 v113; // r14
  int v114; // r12d
  __int64 *v115; // rdx
  __int64 v116; // r9
  unsigned int v117; // ebx
  LPWSTR StringSid; // [rsp+88h] [rbp+48h] BYREF
  struct Schema *v119; // [rsp+90h] [rbp+50h] BYREF
  volatile signed __int32 *v120; // [rsp+98h] [rbp+58h] BYREF

  v119 = a3;
  v5 = *((_DWORD *)a2 + 38);
  if ( v5 )
  {
    *((_DWORD *)a2 + 38) = v5 + 1;
  }
  else
  {
    v6 = *(_DWORD *)a2;
    if ( v6 == 65542 )
    {
LABEL_3:
      v7 = (struct IErrorInfo *)((&Schema::schemaEntries)[(unsigned __int16)v6] + 1552);
      lpVtbl = (int)v7->lpVtbl;
    }
    else
    {
      switch ( v6 )
      {
        case 65536:
        case 65537:
          v89 = 0;
          v90 = (&Schema::schemaEntriesCount)[(unsigned __int16)v6];
          v91 = 8LL * (unsigned __int16)v6 + 575136;
          break;
        case 65538:
        case 65539:
        case 65540:
        case 65541:
          goto LABEL_3;
        default:
          goto LABEL_209;
      }
      while ( v89 < (unsigned __int64)v90 )
      {
        v7 = (struct IErrorInfo *)(*(_QWORD *)((char *)&_ImageBase + v91) + (v89 << 7));
        if ( LODWORD(v7->lpVtbl) == 97 )
          goto LABEL_5;
        ++v89;
      }
LABEL_209:
      v7 = (struct IErrorInfo *)&qword_1800A1560;
      lpVtbl = 0;
    }
    if ( lpVtbl )
    {
LABEL_5:
      v9 = *((_QWORD *)a2 + 2);
      if ( !v9 )
        _com_raise_error(-2147467261, v7);
      result = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, struct IErrorInfoVtbl *, unsigned __int16 *const))(*(_QWORD *)v9 + 216LL))(
                 v9,
                 &ChannelPath,
                 v7[1].lpVtbl,
                 Schema::namespaceUri);
      if ( (int)result < 0 )
        return result;
    }
    else
    {
      *((_DWORD *)a2 + 38) = 1;
    }
  }
  v11 = (BSTR *)*((_QWORD *)this + 9);
  if ( v11 && (!*v11 ? (v12 = 0) : (v12 = SysStringLen(*v11)), v12) )
  {
    v13 = (__int64 *)*((_QWORD *)this + 9);
    if ( v13 )
      v14 = *v13;
    else
      v14 = 0;
    v15 = *((_DWORD *)a2 + 38);
    if ( v15 )
    {
      *((_DWORD *)a2 + 38) = v15 + 1;
      v20 = 1;
    }
    else
    {
      v16 = *(_DWORD *)a2;
      if ( *(_DWORD *)a2 == 65542 )
      {
LABEL_15:
        v17 = (struct IErrorInfo *)((&Schema::schemaEntries)[(unsigned __int16)v16] + 1568);
        v18 = (int)v17->lpVtbl;
      }
      else
      {
        switch ( v16 )
        {
          case 65536:
          case 65537:
            v94 = 0;
            v95 = (&Schema::schemaEntriesCount)[(unsigned __int16)v16];
            v96 = 8LL * (unsigned __int16)v16 + 575136;
            break;
          case 65538:
          case 65539:
          case 65540:
          case 65541:
            goto LABEL_15;
          default:
            goto LABEL_214;
        }
        while ( v94 < (unsigned __int64)v95 )
        {
          v17 = (struct IErrorInfo *)(*(_QWORD *)((char *)&_ImageBase + v96) + (v94 << 7));
          if ( LODWORD(v17->lpVtbl) == 98 )
            goto LABEL_17;
          ++v94;
        }
LABEL_214:
        v17 = (struct IErrorInfo *)&qword_1800A1560;
        v18 = 0;
      }
      if ( v18 )
      {
LABEL_17:
        v19 = *((_QWORD *)a2 + 2);
        if ( !v19 )
          _com_raise_error(-2147467261, v17);
        v20 = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, struct IErrorInfoVtbl *, unsigned __int16 *const))(*(_QWORD *)v19 + 216LL))(
                v19,
                &ChannelPath,
                v17[1].lpVtbl,
                Schema::namespaceUri);
        if ( v20 >= 0 )
        {
          v21 = *(_DWORD *)a2;
          if ( *(_DWORD *)a2 == 65542 )
          {
LABEL_20:
            v22 = *((_DWORD *)(&Schema::schemaEntries)[(unsigned __int16)v21] + 3168);
          }
          else
          {
            switch ( v21 )
            {
              case 65536:
              case 65537:
                v102 = 0;
                v103 = (unsigned __int16)v21;
                v104 = (&Schema::schemaEntriesCount)[(unsigned __int16)v21];
                break;
              case 65538:
              case 65539:
              case 65540:
              case 65541:
                goto LABEL_20;
              default:
                goto LABEL_217;
            }
            while ( v102 < (unsigned __int64)v104 )
            {
              if ( *(_DWORD *)((v102 << 7) + *((_QWORD *)&_ImageBase + v103 + 71892)) == 99 )
                goto LABEL_22;
              ++v102;
            }
LABEL_217:
            v22 = 0;
          }
          if ( v22 )
          {
LABEL_22:
            v23 = _com_ptr_t<_com_IIID<IXmlWriter,&__s_GUID const _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030>>::operator->((char *)a2 + 16);
            Entry = Schema::GetEntry(a2, 99);
            v26 = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, _QWORD, _QWORD, __int64))(v25 + 56))(
                    v23,
                    &ChannelPath,
                    *(_QWORD *)(Entry + 8),
                    0,
                    v14);
LABEL_29:
            v20 = v26;
          }
        }
      }
      else
      {
        *((_DWORD *)a2 + 38) = 1;
        v20 = 1;
      }
    }
  }
  else
  {
    v27 = *((_DWORD *)a2 + 38);
    if ( v27 )
    {
      *((_DWORD *)a2 + 38) = v27 + 1;
      v20 = 1;
    }
    else
    {
      v28 = *(_DWORD *)a2;
      if ( *(_DWORD *)a2 == 65542 )
      {
LABEL_25:
        v29 = (struct IErrorInfo *)((&Schema::schemaEntries)[(unsigned __int16)v28] + 1568);
        v30 = (int)v29->lpVtbl;
      }
      else
      {
        switch ( v28 )
        {
          case 65536:
          case 65537:
            v99 = 0;
            v100 = (&Schema::schemaEntriesCount)[(unsigned __int16)v28];
            v101 = 8LL * (unsigned __int16)v28 + 575136;
            break;
          case 65538:
          case 65539:
          case 65540:
          case 65541:
            goto LABEL_25;
          default:
            goto LABEL_219;
        }
        while ( v99 < (unsigned __int64)v100 )
        {
          v29 = (struct IErrorInfo *)(*(_QWORD *)((char *)&_ImageBase + v101) + (v99 << 7));
          if ( LODWORD(v29->lpVtbl) == 98 )
            goto LABEL_27;
          ++v99;
        }
LABEL_219:
        v29 = (struct IErrorInfo *)&qword_1800A1560;
        v30 = 0;
      }
      if ( v30 )
      {
LABEL_27:
        v31 = *((_QWORD *)a2 + 2);
        if ( !v31 )
          _com_raise_error(-2147467261, v29);
        v26 = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, struct IErrorInfoVtbl *, unsigned __int16 *const))(*(_QWORD *)v31 + 216LL))(
                v31,
                &ChannelPath,
                v29[1].lpVtbl,
                Schema::namespaceUri);
        goto LABEL_29;
      }
      *((_DWORD *)a2 + 38) = 1;
      v20 = 1;
    }
  }
  if ( v20 < 0 )
    return (unsigned int)v20;
  v32 = (BSTR *)*((_QWORD *)this + 10);
  if ( !v32
    || (!*v32 ? (v33 = 0) : (v33 = SysStringLen(*v32)),
        !v33
     || ((v109 = (__int64 *)*((_QWORD *)this + 10)) == 0 ? (v110 = 0) : (v110 = *v109),
         result = TaskXmlWriter::Element(a2, 112, v110),
         (int)result >= 0)) )
  {
    v34 = 0;
    v119 = 0;
    v35 = *((_QWORD *)this + 8);
    if ( !v35 )
    {
      v39 = -2147418113;
      goto LABEL_122;
    }
    StringSid = 0;
    if ( ConvertSidToStringSidW(*(PSID *)(v35 + 32), &StringSid) )
    {
      v75 = SysAllocString(StringSid);
      if ( v75 )
      {
        v87 = (volatile signed __int32 *)operator new(0x18u);
        v34 = v87;
        v120 = v87;
        if ( v87 )
        {
          *((_QWORD *)v87 + 1) = 0;
          *((_DWORD *)v87 + 4) = 1;
          *(_QWORD *)v87 = v75;
        }
        else
        {
          v34 = 0;
        }
        v120 = v34;
        if ( !v34 )
          _com_raise_error(-2147024882, v88);
        _InterlockedIncrement(v34 + 4);
        _bstr_t::~_bstr_t((_bstr_t *)&v119);
        v119 = (struct Schema *)v34;
        _bstr_t::~_bstr_t((_bstr_t *)&v120);
        v39 = 0;
      }
      else
      {
        v39 = -2147024882;
      }
      LocalFree(StringSid);
    }
    else
    {
      LastError = GetLastError();
      v39 = LastError;
      if ( LastError > 0 )
        v39 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( v39 < 0 )
      goto LABEL_122;
    v40 = *(_DWORD *)(*((_QWORD *)this + 8) + 40LL);
    if ( ((v40 - 2) & 0xFFFFFFFC) != 0
      || v40 == 3
      || User::IsLocalSystem((JobBucket *)((char *)this + 64))
      || User::IsLocalService((JobBucket *)((char *)this + 64))
      || User::IsNetworkService((JobBucket *)((char *)this + 64))
      || User::IsServiceSid((JobBucket *)((char *)this + 64)) )
    {
      v41 = (int *)((char *)this + 16);
      if ( (*((_DWORD *)this + 4) & 0x20000) != 0 )
      {
        if ( v34 )
          v42 = *(_QWORD *)v34;
        else
          v42 = 0;
        v43 = *((_DWORD *)a2 + 38);
        v44 = &qword_1800A1560;
        if ( v43 )
        {
          *((_DWORD *)a2 + 38) = v43 + 1;
        }
        else
        {
          v37 = (struct IErrorInfo *)*(unsigned int *)a2;
          if ( (_DWORD)v37 == 65542 )
          {
LABEL_48:
            v38 = (&Schema::schemaEntries)[(unsigned __int16)v37] + 576;
            v45 = *(_DWORD *)v38;
          }
          else
          {
            switch ( (int)v37 )
            {
              case 65536:
              case 65537:
                v92 = 0;
                v93 = (unsigned __int16)v37;
                v37 = (struct IErrorInfo *)(&Schema::schemaEntriesCount)[(unsigned __int16)v37];
                break;
              case 65538:
              case 65539:
              case 65540:
              case 65541:
                goto LABEL_48;
              default:
                goto LABEL_238;
            }
            while ( v92 < (unsigned __int64)v37 )
            {
              v38 = (const struct SchemaEntry * near *)(*((_QWORD *)&_ImageBase + v93 + 71892) + (v92 << 7));
              if ( *(_DWORD *)v38 == 36 )
                goto LABEL_50;
              ++v92;
            }
LABEL_238:
            v38 = (const struct SchemaEntry * near *)&qword_1800A1560;
            v45 = 0;
          }
          if ( v45 )
          {
LABEL_50:
            v46 = *((_QWORD *)a2 + 2);
            if ( !v46 )
              _com_raise_error(-2147467261, v37);
            v47 = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, const struct SchemaEntry *, unsigned __int16 *const))(*(_QWORD *)v46 + 216LL))(
                    v46,
                    &ChannelPath,
                    v38[1],
                    Schema::namespaceUri);
            v48 = v47;
            if ( v47 < 0 )
              goto LABEL_52;
            if ( !v47 && v42 )
            {
              v58 = *((_QWORD *)a2 + 2);
              if ( !v58 )
                _com_raise_error(-2147467261, v37);
              v48 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v58 + 224LL))(v58, v42);
              if ( v48 < 0 )
                goto LABEL_52;
            }
            v44 = &qword_1800A1560;
          }
          else
          {
            *((_DWORD *)a2 + 38) = 1;
          }
        }
        v59 = *((_DWORD *)a2 + 38);
        if ( v59 )
        {
          *((_DWORD *)a2 + 38) = v59 - 1;
          v48 = 1;
        }
        else
        {
          v60 = *((_QWORD *)a2 + 2);
          if ( !v60 )
            _com_raise_error(-2147467261, v37);
          v48 = (*(__int64 (__fastcall **)(__int64, struct IErrorInfo *, const struct SchemaEntry * near *, __int64 *))(*(_QWORD *)v60 + 120LL))(
                  v60,
                  v37,
                  v38,
                  &qword_1800A1560);
          v44 = &qword_1800A1560;
        }
        if ( v48 < 0 )
          goto LABEL_52;
      }
      else
      {
        if ( v34 )
          v55 = *(_QWORD *)v34;
        else
          v55 = 0;
        v48 = TaskXmlWriter::Element(a2, 36, v55);
        if ( v48 < 0 )
          goto LABEL_52;
        v56 = *v41;
        if ( (*v41 & 0x40000) != 0 )
        {
          v57 = L"Password";
        }
        else if ( (v56 & 0x4000) != 0 )
        {
          v57 = L"S4U";
        }
        else
        {
          v57 = (v56 & 0x10000) == 0 && (v56 & 0x80000) != 0 ? L"InteractiveTokenOrPassword" : L"InteractiveToken";
        }
        v48 = TaskXmlWriter::Element(a2, 100, v57);
        if ( v48 < 0 )
          goto LABEL_52;
        v44 = &qword_1800A1560;
      }
    }
    else
    {
      if ( v34 )
        v76 = *(_QWORD *)v34;
      else
        v76 = 0;
      v77 = *((_DWORD *)a2 + 38);
      v44 = &qword_1800A1560;
      if ( v77 )
      {
        *((_DWORD *)a2 + 38) = v77 + 1;
      }
      else
      {
        v37 = (struct IErrorInfo *)*(unsigned int *)a2;
        if ( (_DWORD)v37 == 65542 )
        {
LABEL_118:
          v38 = (&Schema::schemaEntries)[(unsigned __int16)v37] + 1776;
          v78 = *(_DWORD *)v38;
        }
        else
        {
          switch ( (int)v37 )
          {
            case 65536:
            case 65537:
              v105 = 0;
              v106 = (unsigned __int16)v37;
              v37 = (struct IErrorInfo *)(&Schema::schemaEntriesCount)[(unsigned __int16)v37];
              break;
            case 65538:
            case 65539:
            case 65540:
            case 65541:
              goto LABEL_118;
            default:
              goto LABEL_231;
          }
          while ( v105 < (unsigned __int64)v37 )
          {
            v38 = (const struct SchemaEntry * near *)(*((_QWORD *)&_ImageBase + v106 + 71892) + (v105 << 7));
            if ( *(_DWORD *)v38 == 111 )
              goto LABEL_120;
            ++v105;
          }
LABEL_231:
          v38 = (const struct SchemaEntry * near *)&qword_1800A1560;
          v78 = 0;
        }
        if ( v78 )
        {
LABEL_120:
          v79 = *((_QWORD *)a2 + 2);
          if ( !v79 )
            _com_raise_error(-2147467261, v37);
          v80 = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, const struct SchemaEntry *, unsigned __int16 *const))(*(_QWORD *)v79 + 216LL))(
                  v79,
                  &ChannelPath,
                  v38[1],
                  Schema::namespaceUri);
          v39 = v80;
          if ( v80 < 0 )
            goto LABEL_122;
          if ( !v80 && v76 )
          {
            v81 = *((_QWORD *)a2 + 2);
            if ( !v81 )
              _com_raise_error(-2147467261, v37);
            v39 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v81 + 224LL))(v81, v76);
            if ( v39 < 0 )
              goto LABEL_122;
          }
          v44 = &qword_1800A1560;
        }
        else
        {
          *((_DWORD *)a2 + 38) = 1;
        }
      }
      v82 = *((_DWORD *)a2 + 38);
      if ( v82 )
      {
        *((_DWORD *)a2 + 38) = v82 - 1;
        v39 = 1;
      }
      else
      {
        v83 = *((_QWORD *)a2 + 2);
        if ( !v83 )
          _com_raise_error(-2147467261, v37);
        v39 = (*(__int64 (__fastcall **)(__int64, struct IErrorInfo *, const struct SchemaEntry * near *, __int64 *))(*(_QWORD *)v83 + 120LL))(
                v83,
                v37,
                v38,
                &qword_1800A1560);
        v44 = &qword_1800A1560;
      }
      if ( v39 < 0 )
        goto LABEL_122;
      v41 = (int *)((char *)this + 16);
    }
    if ( (*v41 & 0x1000000) != 0 )
    {
      v48 = TaskXmlWriter::ElementRunLevel(a2, 101, 1);
      if ( v48 < 0 )
        goto LABEL_52;
      v44 = &qword_1800A1560;
    }
    if ( (*v41 & 0x8000000) == 0 )
    {
LABEL_84:
      if ( (*v41 & 0x10000000) != 0 )
      {
        v39 = TaskXmlWriter::Element(a2, 133, L"Unrestricted");
        if ( v39 < 0 )
          goto LABEL_122;
        v44 = &qword_1800A1560;
      }
      v61 = *((_QWORD *)this + 26);
      if ( !v61 || !*(_QWORD *)(v61 + 48) )
      {
LABEL_86:
        v62 = (__int64 *)*((_QWORD *)this + 22);
        if ( v62 )
        {
          v63 = *v62;
          if ( *v62 )
          {
            v64 = *((_DWORD *)a2 + 38);
            if ( v64 )
            {
              *((_DWORD *)a2 + 38) = v64 + 1;
            }
            else
            {
              v37 = (struct IErrorInfo *)*(unsigned int *)a2;
              if ( (_DWORD)v37 == 65542 )
              {
LABEL_90:
                v38 = (&Schema::schemaEntries)[(unsigned __int16)v37] + 2320;
                v65 = *(_DWORD *)v38;
              }
              else
              {
                switch ( (int)v37 )
                {
                  case 65536:
                  case 65537:
                    v107 = 0;
                    v108 = (unsigned __int16)v37;
                    v37 = (struct IErrorInfo *)(&Schema::schemaEntriesCount)[(unsigned __int16)v37];
                    break;
                  case 65538:
                  case 65539:
                  case 65540:
                  case 65541:
                    goto LABEL_90;
                  default:
                    goto LABEL_258;
                }
                while ( v107 < (unsigned __int64)v37 )
                {
                  v38 = (const struct SchemaEntry * near *)(*((_QWORD *)&_ImageBase + v108 + 71892) + (v107 << 7));
                  if ( *(_DWORD *)v38 == 145 )
                    goto LABEL_92;
                  ++v107;
                }
LABEL_258:
                v38 = (const struct SchemaEntry * near *)&qword_1800A1560;
                v65 = 0;
              }
              if ( v65 )
              {
LABEL_92:
                v66 = *((_QWORD *)a2 + 2);
                if ( !v66 )
                  _com_raise_error(-2147467261, v37);
                v67 = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, const struct SchemaEntry *, unsigned __int16 *const))(*(_QWORD *)v66 + 216LL))(
                        v66,
                        &ChannelPath,
                        v38[1],
                        Schema::namespaceUri);
                v68 = v67;
                if ( v67 < 0 )
                  goto LABEL_101;
                if ( !v67 )
                {
                  v69 = *((_QWORD *)a2 + 2);
                  if ( !v69 )
                    _com_raise_error(-2147467261, v37);
                  v68 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v69 + 224LL))(v69, v63);
                  if ( v68 < 0 )
                    goto LABEL_101;
                }
              }
              else
              {
                *((_DWORD *)a2 + 38) = 1;
              }
            }
            v70 = *((_DWORD *)a2 + 38);
            if ( v70 )
            {
              *((_DWORD *)a2 + 38) = v70 - 1;
              v68 = 1;
            }
            else
            {
              v71 = *((_QWORD *)a2 + 2);
              if ( !v71 )
                _com_raise_error(-2147467261, v37);
              v68 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v71 + 120LL))(v71);
            }
            if ( v68 < 0 )
            {
LABEL_101:
              if ( v34 )
                _bstr_t::Data_t::Release((_bstr_t::Data_t *)v34);
              return (unsigned int)v68;
            }
          }
        }
        if ( !(unsigned int)((__int64)(*((_QWORD *)this + 24) - *((_QWORD *)this + 23)) >> 3) )
          goto LABEL_105;
        started = TaskXmlWriter::StartElement(a2, 146, v38, v44);
        if ( started >= 0 )
        {
          v85 = 0;
          v86 = (__int64)(*((_QWORD *)this + 24) - *((_QWORD *)this + 23)) >> 3;
          while ( (unsigned int)v85 < (unsigned int)v86 )
          {
            v115 = *(__int64 **)(*((_QWORD *)this + 23) + 8 * v85);
            if ( v115 )
              v116 = *v115;
            else
              v116 = 0;
            v48 = JobBucket::WriteOptionalXmlElement(v84, a2, 147, v116);
            if ( v48 < 0 )
              goto LABEL_52;
            v85 = (unsigned int)(v85 + 1);
          }
          started = TaskXmlWriter::EndElement(a2);
          if ( started >= 0 )
          {
LABEL_105:
            v72 = *((_DWORD *)a2 + 38);
            if ( v72 )
            {
              *((_DWORD *)a2 + 38) = v72 - 1;
            }
            else
            {
              v73 = *((_QWORD *)a2 + 2);
              if ( !v73 )
                _com_raise_error(-2147467261, v37);
              started = (*(__int64 (__fastcall **)(__int64, struct IErrorInfo *, const struct SchemaEntry * near *, __int64 *))(*(_QWORD *)v73 + 120LL))(
                          v73,
                          v37,
                          v38,
                          v44);
              if ( started < 0 )
                goto LABEL_108;
            }
            v117 = TaskXmlWriter::EndElement(a2);
            _bstr_t::~_bstr_t((_bstr_t *)&v119);
            return v117;
          }
        }
LABEL_108:
        _bstr_t::~_bstr_t((_bstr_t *)&v119);
        return (unsigned int)started;
      }
      v49 = *((_DWORD *)a2 + 38);
      if ( v49 )
      {
        *((_DWORD *)a2 + 38) = v49 + 1;
      }
      else
      {
        v50 = *(unsigned int *)a2;
        if ( (_DWORD)v50 == 65542 )
        {
LABEL_56:
          v51 = (&Schema::schemaEntries)[(unsigned __int16)v50] + 2144;
          v52 = *(_DWORD *)v51;
        }
        else
        {
          switch ( (int)v50 )
          {
            case 65536:
            case 65537:
              v97 = 0;
              v98 = (unsigned __int16)v50;
              v50 = (unsigned __int64)(&Schema::schemaEntriesCount)[(unsigned __int16)v50];
              break;
            case 65538:
            case 65539:
            case 65540:
            case 65541:
              goto LABEL_56;
            default:
              goto LABEL_251;
          }
          while ( v97 < v50 )
          {
            v51 = (const struct SchemaEntry * near *)(*((_QWORD *)&_ImageBase + v98 + 71892) + (v97 << 7));
            if ( *(_DWORD *)v51 == 134 )
              goto LABEL_58;
            ++v97;
          }
LABEL_251:
          v51 = (const struct SchemaEntry * near *)&qword_1800A1560;
          v52 = 0;
        }
        if ( v52 )
        {
LABEL_58:
          v53 = *((_QWORD *)a2 + 2);
          if ( !v53 )
            _com_raise_error(-2147467261, (struct IErrorInfo *)v50);
          v54 = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, const struct SchemaEntry *, unsigned __int16 *const))(*(_QWORD *)v53 + 216LL))(
                  v53,
                  &ChannelPath,
                  v51[1],
                  Schema::namespaceUri);
          if ( v54 < 0 )
          {
            if ( v34 && _InterlockedExchangeAdd(v34 + 4, 0xFFFFFFFF) == 1 )
              _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v34, 1u);
            return (unsigned int)v54;
          }
        }
        else
        {
          *((_DWORD *)a2 + 38) = 1;
        }
      }
      v111 = 1;
      v112 = *((_QWORD *)this + 26);
      if ( v112 )
        v113 = *(_QWORD *)(v112 + 48);
      else
        v113 = 0;
      while ( v111 )
      {
        if ( (v113 & v111) != 0 )
        {
          StringSid = 0;
          if ( (unsigned int)User::GetPrivilegeName(v111, (const unsigned __int16 **)&StringSid) )
          {
            v114 = TaskXmlWriter::Element(a2, 135, StringSid);
            if ( v114 < 0 )
            {
              _bstr_t::~_bstr_t((_bstr_t *)&v119);
              return (unsigned int)v114;
            }
          }
        }
        v111 *= 2LL;
      }
      v39 = TaskXmlWriter::EndElement(a2);
      if ( v39 >= 0 )
      {
        v44 = &qword_1800A1560;
        goto LABEL_86;
      }
LABEL_122:
      _bstr_t::~_bstr_t((_bstr_t *)&v119);
      return (unsigned int)v39;
    }
    v48 = TaskXmlWriter::ElementProcessTokenSidType(a2, 133, 0);
    if ( v48 >= 0 )
    {
      v44 = &qword_1800A1560;
      goto LABEL_84;
    }
LABEL_52:
    _bstr_t::~_bstr_t((_bstr_t *)&v119);
    return (unsigned int)v48;
  }
  return result;
}

```

## disassembly

```asm
0x180006ac0  mov     [rsp-38h+arg_0], rbx
0x180006ac5  mov     [rsp-38h+arg_10], r8
0x180006aca  push    rbp
0x180006acb  push    rsi
0x180006acc  push    rdi
0x180006acd  push    r12
0x180006acf  push    r13
0x180006ad1  push    r14
0x180006ad3  push    r15
0x180006ad5  mov     rbp, rsp
0x180006ad8  sub     rsp, 40h
0x180006adc  mov     rbx, rdx
0x180006adf  mov     r15, rcx
0x180006ae2  mov     eax, [rdx+98h]
0x180006ae8  lea     r13, __ImageBase
0x180006aef  mov     r8, cs:off_18008C6D0
0x180006af6  test    eax, eax
0x180006af8  jnz     loc_180007765
0x180006afe  mov     edx, [rdx]
0x180006b00  cmp     edx, 10006h
0x180006b06  jnz     loc_180007370
0x180006b0c  movzx   eax, dx; jumptable 000000018000738C cases 65538-65541
0x180006b0f  mov     rdx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r13+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180006b17  add     rdx, 3080h; struct IErrorInfo *
0x180006b1e  mov     eax, [rdx]
0x180006b20  test    eax, eax
0x180006b22  jz      loc_18000777D
0x180006b28  mov     rcx, [rbx+10h]
0x180006b2c  test    rcx, rcx
0x180006b2f  jz      loc_18000778C
0x180006b35  mov     rax, [rcx]
0x180006b38  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x180006b3f  mov     r8, [rdx+8]
0x180006b43  lea     rdx, ChannelPath
0x180006b4a  mov     rax, [rax+0D8h]
0x180006b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b56  test    eax, eax
0x180006b58  js      loc_180006ED2
0x180006b5e  mov     r8, cs:off_18008C6D0
0x180006b65  mov     rax, [r15+48h]
0x180006b69  test    rax, rax
0x180006b6c  jz      loc_180006C80
0x180006b72  mov     rcx, [rax]; pbstr
0x180006b75  test    rcx, rcx
0x180006b78  jz      loc_180007797
0x180006b7e  call    cs:__imp_SysStringLen
0x180006b85  nop     dword ptr [rax+rax+00h]
0x180006b8a  mov     r8, cs:off_18008C6D0
0x180006b91  test    eax, eax
0x180006b93  jz      loc_180006C80
0x180006b99  mov     rax, [r15+48h]
0x180006b9d  test    rax, rax
0x180006ba0  jz      loc_1800073D2
0x180006ba6  mov     rsi, [rax]
0x180006ba9  mov     eax, [rbx+98h]
0x180006baf  test    eax, eax
0x180006bb1  jnz     loc_18000779E
0x180006bb7  mov     edx, [rbx]
0x180006bb9  cmp     edx, 10006h
0x180006bbf  jnz     loc_180007434
0x180006bc5  movzx   eax, dx; jumptable 0000000180007450 cases 65538-65541
0x180006bc8  mov     rdx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r13+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180006bd0  add     rdx, 3100h; struct IErrorInfo *
0x180006bd7  mov     eax, [rdx]
0x180006bd9  test    eax, eax
0x180006bdb  jz      loc_1800077BB
0x180006be1  mov     rcx, [rbx+10h]
0x180006be5  test    rcx, rcx
0x180006be8  jz      loc_1800077CF
0x180006bee  mov     rax, [rcx]
0x180006bf1  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x180006bf8  mov     r8, [rdx+8]
0x180006bfc  lea     rdx, ChannelPath
0x180006c03  mov     rax, [rax+0D8h]
0x180006c0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c0f  mov     edx, eax
0x180006c11  test    eax, eax
0x180006c13  js      loc_180006CE8
0x180006c19  mov     r8d, [rbx]
0x180006c1c  cmp     r8d, 10006h
0x180006c23  jnz     loc_18000756F
0x180006c29  movzx   eax, r8w; jumptable 000000018000758C cases 65538-65541
0x180006c2d  mov     rax, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r13+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180006c35  mov     ecx, [rax+3180h]
0x180006c3b  test    ecx, ecx
0x180006c3d  jz      loc_180006CE8
0x180006c43  lea     rcx, [rbx+10h]
0x180006c47  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlWriter@@$1?_GUID_7279fc88_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlWriter@@XZ; _com_ptr_t<_com_IIID<IXmlWriter,&__s_GUID const _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x180006c4c  mov     rdi, rax
0x180006c4f  mov     r11, [rax]
0x180006c52  mov     edx, 63h ; 'c'
0x180006c57  mov     rcx, rbx
0x180006c5a  call    ?GetEntry@Schema@@AEBAAEBUSchemaEntry@@W4TaskXmlNodeId@@@Z; Schema::GetEntry(TaskXmlNodeId)
0x180006c5f  mov     [rsp+40h+var_20], rsi
0x180006c64  xor     r9d, r9d
0x180006c67  mov     r8, [rax+8]
0x180006c6b  lea     rdx, ChannelPath
0x180006c72  mov     rcx, rdi
0x180006c75  mov     rax, [r11+38h]
0x180006c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c7e  jmp     short loc_180006CE6
0x180006c80  mov     eax, [rbx+98h]
0x180006c86  test    eax, eax
0x180006c88  jnz     loc_1800077E8
0x180006c8e  mov     edx, [rbx]
0x180006c90  cmp     edx, 10006h
0x180006c96  jnz     loc_180007515
0x180006c9c  movzx   eax, dx; jumptable 0000000180007531 cases 65538-65541
0x180006c9f  mov     rdx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r13+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180006ca7  add     rdx, 3100h; struct IErrorInfo *
0x180006cae  mov     eax, [rdx]
0x180006cb0  test    eax, eax
0x180006cb2  jz      loc_180007805
0x180006cb8  mov     rcx, [rbx+10h]
0x180006cbc  test    rcx, rcx
0x180006cbf  jz      loc_180007819
0x180006cc5  mov     rax, [rcx]
0x180006cc8  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x180006ccf  mov     r8, [rdx+8]
0x180006cd3  lea     rdx, ChannelPath
0x180006cda  mov     rax, [rax+0D8h]
0x180006ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ce6  mov     edx, eax
0x180006ce8  test    edx, edx
0x180006cea  js      loc_180007824
0x180006cf0  mov     rax, [r15+50h]
0x180006cf4  test    rax, rax
0x180006cf7  jz      short loc_180006D19
0x180006cf9  mov     rcx, [rax]; pbstr
0x180006cfc  test    rcx, rcx
0x180006cff  jz      loc_18000782B
0x180006d05  call    cs:__imp_SysStringLen
0x180006d0c  nop     dword ptr [rax+rax+00h]
0x180006d11  test    eax, eax
0x180006d13  jnz     loc_18000768D
0x180006d19  xor     edi, edi
0x180006d1b  mov     [rbp+arg_10], rdi
0x180006d1f  mov     rcx, [r15+40h]
0x180006d23  test    rcx, rcx
0x180006d26  jz      loc_180007832
0x180006d2c  mov     [rbp+StringSid], rdi
0x180006d30  lea     rdx, [rbp+StringSid]; StringSid
0x180006d34  mov     rcx, [rcx+20h]; Sid
0x180006d38  call    cs:__imp_ConvertSidToStringSidW
0x180006d3f  nop     dword ptr [rax+rax+00h]
0x180006d44  test    eax, eax
0x180006d46  jnz     loc_180007139
0x180006d4c  call    cs:__imp_GetLastError
0x180006d53  nop     dword ptr [rax+rax+00h]
0x180006d58  mov     esi, eax
0x180006d5a  test    eax, eax
0x180006d5c  jle     short loc_180006D67
0x180006d5e  movzx   esi, ax
0x180006d61  or      esi, 80070000h
0x180006d67  test    esi, esi
0x180006d69  js      loc_180007237
0x180006d6f  mov     rax, [r15+40h]
0x180006d73  mov     ecx, [rax+28h]
0x180006d76  lea     eax, [rcx-2]
0x180006d79  test    eax, 0FFFFFFFCh
0x180006d7e  jnz     short loc_180006D96
0x180006d80  cmp     ecx, 3
0x180006d83  jz      short loc_180006D96
0x180006d85  lea     rcx, [r15+40h]; this
0x180006d89  call    ?IsLocalSystem@User@@QEBA_NXZ; User::IsLocalSystem(void)
0x180006d8e  test    al, al
0x180006d90  jz      loc_180007843
0x180006d96  lea     rsi, [r15+10h]
0x180006d9a  test    dword ptr [rsi], 20000h
0x180006da0  jz      loc_180006EEB
0x180006da6  test    rdi, rdi
0x180006da9  jz      loc_1800073CA
0x180006daf  mov     r12, [rdi]
0x180006db2  mov     eax, [rbx+98h]
0x180006db8  mov     r9, cs:off_18008C6D0
0x180006dbf  test    eax, eax
0x180006dc1  jnz     loc_1800078D5
0x180006dc7  mov     edx, [rbx]; struct IErrorInfo *
0x180006dc9  cmp     edx, 10006h
0x180006dcf  jnz     loc_1800073D9
0x180006dd5  movzx   eax, dx; jumptable 00000001800073F5 cases 65538-65541
0x180006dd8  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r13+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180006de0  add     r8, 1200h
0x180006de7  mov     eax, [r8]
0x180006dea  test    eax, eax
0x180006dec  jz      loc_1800078ED
0x180006df2  mov     rcx, [rbx+10h]
0x180006df6  test    rcx, rcx
0x180006df9  jz      loc_1800078FC
0x180006dff  mov     rax, [rcx]
0x180006e02  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x180006e09  mov     r8, [r8+8]
0x180006e0d  lea     rdx, ChannelPath
0x180006e14  mov     rax, [rax+0D8h]
0x180006e1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e20  mov     r14d, eax
0x180006e23  test    eax, eax
0x180006e25  jns     loc_180006F42
0x180006e2b  lea     rcx, [rbp+arg_10]; this
0x180006e2f  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180006e34  mov     eax, r14d
0x180006e37  jmp     loc_180006ED2
0x180006e3c  cmp     qword ptr [rax+30h], 0
0x180006e41  jz      loc_180006FE8
0x180006e47  mov     eax, [rbx+98h]
0x180006e4d  test    eax, eax
0x180006e4f  jnz     loc_180007999
0x180006e55  mov     edx, [rbx]; struct IErrorInfo *
0x180006e57  cmp     edx, 10006h
0x180006e5d  jnz     loc_18000748E
0x180006e63  movzx   eax, dx; jumptable 00000001800074AA cases 65538-65541
0x180006e66  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r13+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180006e6e  add     r8, 4300h
0x180006e75  mov     eax, [r8]
0x180006e78  test    eax, eax
0x180006e7a  jz      loc_1800079B1
0x180006e80  mov     rcx, [rbx+10h]
0x180006e84  test    rcx, rcx
0x180006e87  jz      loc_1800079C0
0x180006e8d  mov     rax, [rcx]
0x180006e90  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x180006e97  mov     r8, [r8+8]
0x180006e9b  lea     rdx, ChannelPath
0x180006ea2  mov     rax, [rax+0D8h]
0x180006ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006eae  mov     esi, eax
0x180006eb0  test    eax, eax
0x180006eb2  jns     loc_1800076B8
0x180006eb8  test    rdi, rdi
0x180006ebb  jz      short loc_180006ED0
0x180006ebd  mov     edx, 0FFFFFFFFh
0x180006ec2  lock xadd [rdi+10h], edx; unsigned int
0x180006ec7  cmp     edx, 1
0x180006eca  jz      loc_180007177
0x180006ed0  mov     eax, esi
0x180006ed2  mov     rbx, [rsp+40h+arg_0]
0x180006eda  add     rsp, 40h
0x180006ede  pop     r15
0x180006ee0  pop     r14
0x180006ee2  pop     r13
0x180006ee4  pop     r12
0x180006ee6  pop     rdi
0x180006ee7  pop     rsi
0x180006ee8  pop     rbp
0x180006ee9  retn
0x180006eeb  test    rdi, rdi
0x180006eee  jz      loc_180007685
0x180006ef4  mov     r8, [rdi]
0x180006ef7  mov     edx, 24h ; '$'
0x180006efc  mov     rcx, rbx
0x180006eff  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180006f04  mov     r14d, eax
0x180006f07  test    eax, eax
0x180006f09  js      loc_180006E2B
0x180006f0f  mov     eax, [rsi]
0x180006f11  bt      eax, 12h
0x180006f15  jb      loc_180007301
0x180006f1b  bt      eax, 0Eh
0x180006f1f  jb      loc_18000793C
0x180006f25  bt      eax, 10h
0x180006f29  jb      short loc_180006F36
0x180006f2b  test    eax, 80000h
0x180006f30  jnz     loc_180007930
0x180006f36  lea     r8, aInteractivetok; "InteractiveToken"
0x180006f3d  jmp     loc_180007308
0x180006f42  jnz     short loc_180006F73
0x180006f44  test    r12, r12
0x180006f47  jz      short loc_180006F73
0x180006f49  mov     rcx, [rbx+10h]
0x180006f4d  test    rcx, rcx
0x180006f50  jz      loc_180007907
0x180006f56  mov     rax, [rcx]
0x180006f59  mov     rdx, r12
0x180006f5c  mov     rax, [rax+0E0h]
0x180006f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f68  mov     r14d, eax
0x180006f6b  test    eax, eax
0x180006f6d  js      loc_180006E2B
0x180006f73  mov     r9, cs:off_18008C6D0
0x180006f7a  mov     eax, [rbx+98h]
0x180006f80  test    eax, eax
0x180006f82  jnz     loc_180007912
0x180006f88  mov     rcx, [rbx+10h]
0x180006f8c  test    rcx, rcx
0x180006f8f  jz      loc_180007925
0x180006f95  mov     rax, [rcx]
0x180006f98  mov     rax, [rax+78h]
0x180006f9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fa1  mov     r14d, eax
0x180006fa4  mov     r9, cs:off_18008C6D0
0x180006fab  test    r14d, r14d
0x180006fae  js      loc_180006E2B
0x180006fb4  test    dword ptr [rsi], 1000000h
0x180006fba  jnz     loc_180007948
0x180006fc0  test    dword ptr [rsi], 8000000h
0x180006fc6  jnz     loc_180007972
0x180006fcc  test    dword ptr [rsi], 10000000h
0x180006fd2  jnz     loc_18000718D
0x180006fd8  mov     rax, [r15+0D0h]
0x180006fdf  test    rax, rax
  ... truncated ...
```
