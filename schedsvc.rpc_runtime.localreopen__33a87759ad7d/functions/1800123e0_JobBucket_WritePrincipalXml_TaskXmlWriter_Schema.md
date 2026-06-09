# JobBucket::WritePrincipalXml(TaskXmlWriter *,Schema *)

- ea: `0x1800123e0`
- end: `0x180013514`
- name: `?WritePrincipalXml@JobBucket@@QEBAJPEAVTaskXmlWriter@@PEAUSchema@@@Z`
- size: `4404`
- prototype: `__int64 __fastcall(JobBucket *__hidden this, struct TaskXmlWriter *, struct Schema *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000e910`

## callees

- `0x1800023c0`
- `0x18000dc30`
- `0x18000f630`
- `0x180012180`
- `0x1800123e0`
- `0x18001351c`
- `0x180016160`
- `0x180016df0`
- `0x18001b070`
- `0x18002d6c0`
- `0x18002eeec`
- `0x180030f80`
- `0x1800347e0`
- `0x18003ea10`
- `0x180043ac8`
- `0x180052118`
- `0x1800528f0`
- `0x1800680fc`
- `0x180084010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180012a5a`
- `OLEAUT32!__imp_SysAllocString` at `0x180012a5a`
- `OLEAUT32!__imp_SysStringLen` at `0x18001249e`
- `OLEAUT32!__imp_SysStringLen` at `0x18001261f`
- `OLEAUT32!__imp_SysStringLen` at `0x18001249e`
- `OLEAUT32!__imp_SysStringLen` at `0x18001261f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001265a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001265a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012a75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012a75`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001264c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001264c`

## string_xrefs

- `0x18001283d`: `InteractiveToken`
- `0x18001329f`: `InteractiveTokenOrPassword`

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
  __int64 v40; // rcx
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
  int v74; // edi
  BSTR v75; // rsi
  __int64 v76; // r14
  int v77; // eax
  int v78; // eax
  __int64 v79; // rcx
  int v80; // eax
  __int64 v81; // rcx
  int v82; // eax
  __int64 v83; // rcx
  int v84; // eax
  int v85; // edx
  const struct SchemaEntry * near *v86; // rdi
  int v87; // eax
  __int64 v88; // rax
  volatile signed __int32 *v89; // rax
  struct IErrorInfo *v90; // rdx
  unsigned __int64 v91; // r9
  const unsigned __int64 near *v92; // r10
  __int64 v93; // r11
  unsigned __int64 v94; // r10
  __int64 v95; // rax
  unsigned __int64 v96; // r9
  const unsigned __int64 near *v97; // r10
  __int64 v98; // r11
  unsigned __int64 v99; // r10
  __int64 v100; // rax
  unsigned __int64 v101; // r9
  const unsigned __int64 near *v102; // r10
  __int64 v103; // r11
  unsigned __int64 v104; // r9
  __int64 v105; // rax
  const unsigned __int64 near *v106; // r8
  unsigned __int64 v107; // r10
  __int64 v108; // rax
  unsigned __int64 v109; // r10
  __int64 v110; // rax
  unsigned __int64 v111; // r8
  __int64 v112; // rax
  const unsigned __int64 near *v113; // rdx
  __int64 *v114; // rax
  __int64 v115; // r8
  unsigned __int64 v116; // rsi
  __int64 v117; // rax
  __int64 v118; // r14
  int v119; // r12d
  __int64 *v120; // rdx
  __int64 v121; // r9
  __int64 v122; // rdi
  __int64 v123; // rsi
  unsigned int v124; // ebx
  LPWSTR StringSid; // [rsp+88h] [rbp+48h] BYREF
  struct Schema *v126; // [rsp+90h] [rbp+50h] BYREF
  volatile signed __int32 *v127; // [rsp+98h] [rbp+58h] BYREF

  v126 = a3;
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
          v91 = 0;
          v92 = (&Schema::schemaEntriesCount)[(unsigned __int16)v6];
          v93 = 8LL * (unsigned __int16)v6 + 558752;
          break;
        case 65538:
        case 65539:
        case 65540:
        case 65541:
          goto LABEL_3;
        default:
          goto LABEL_216;
      }
      while ( v91 < (unsigned __int64)v92 )
      {
        v7 = (struct IErrorInfo *)(*(_QWORD *)((char *)&_ImageBase + v93) + (v91 << 7));
        if ( LODWORD(v7->lpVtbl) == 97 )
          goto LABEL_5;
        ++v91;
      }
LABEL_216:
      v7 = (struct IErrorInfo *)&qword_18009D560;
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
            v96 = 0;
            v97 = (&Schema::schemaEntriesCount)[(unsigned __int16)v16];
            v98 = 8LL * (unsigned __int16)v16 + 558752;
            break;
          case 65538:
          case 65539:
          case 65540:
          case 65541:
            goto LABEL_15;
          default:
            goto LABEL_221;
        }
        while ( v96 < (unsigned __int64)v97 )
        {
          v17 = (struct IErrorInfo *)(*(_QWORD *)((char *)&_ImageBase + v98) + (v96 << 7));
          if ( LODWORD(v17->lpVtbl) == 98 )
            goto LABEL_17;
          ++v96;
        }
LABEL_221:
        v17 = (struct IErrorInfo *)&qword_18009D560;
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
                v104 = 0;
                v105 = (unsigned __int16)v21;
                v106 = (&Schema::schemaEntriesCount)[(unsigned __int16)v21];
                break;
              case 65538:
              case 65539:
              case 65540:
              case 65541:
                goto LABEL_20;
              default:
                goto LABEL_224;
            }
            while ( v104 < (unsigned __int64)v106 )
            {
              if ( *(_DWORD *)((v104 << 7) + *((_QWORD *)&_ImageBase + v105 + 69844)) == 99 )
                goto LABEL_22;
              ++v104;
            }
LABEL_224:
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
            v101 = 0;
            v102 = (&Schema::schemaEntriesCount)[(unsigned __int16)v28];
            v103 = 8LL * (unsigned __int16)v28 + 558752;
            break;
          case 65538:
          case 65539:
          case 65540:
          case 65541:
            goto LABEL_25;
          default:
            goto LABEL_226;
        }
        while ( v101 < (unsigned __int64)v102 )
        {
          v29 = (struct IErrorInfo *)(*(_QWORD *)((char *)&_ImageBase + v103) + (v101 << 7));
          if ( LODWORD(v29->lpVtbl) == 98 )
            goto LABEL_27;
          ++v101;
        }
LABEL_226:
        v29 = (struct IErrorInfo *)&qword_18009D560;
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
     || ((v114 = (__int64 *)*((_QWORD *)this + 10)) == 0 ? (v115 = 0) : (v115 = *v114),
         result = TaskXmlWriter::Element(a2, 112, v115),
         (int)result >= 0)) )
  {
    v34 = 0;
    v126 = 0;
    v35 = *((_QWORD *)this + 8);
    if ( !v35 )
    {
      v39 = -2147418113;
      goto LABEL_123;
    }
    StringSid = 0;
    if ( ConvertSidToStringSidW(*(PSID *)(v35 + 32), &StringSid) )
    {
      v75 = SysAllocString(StringSid);
      if ( v75 )
      {
        v89 = (volatile signed __int32 *)operator new(0x18u);
        v34 = v89;
        v127 = v89;
        if ( v89 )
        {
          *((_QWORD *)v89 + 1) = 0;
          *((_DWORD *)v89 + 4) = 1;
          *(_QWORD *)v89 = v75;
        }
        else
        {
          v34 = 0;
        }
        v127 = v34;
        if ( !v34 )
          _com_raise_error(-2147024882, v90);
        _InterlockedIncrement(v34 + 4);
        _bstr_t::~_bstr_t((_bstr_t *)&v126);
        v126 = (struct Schema *)v34;
        _bstr_t::~_bstr_t((_bstr_t *)&v127);
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
      goto LABEL_123;
    v40 = *(unsigned int *)(*((_QWORD *)this + 8) + 40LL);
    if ( (((_DWORD)v40 - 2) & 0xFFFFFFFC) != 0
      || (_DWORD)v40 == 3
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
        v44 = &qword_18009D560;
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
                v94 = 0;
                v95 = (unsigned __int16)v37;
                v37 = (struct IErrorInfo *)(&Schema::schemaEntriesCount)[(unsigned __int16)v37];
                break;
              case 65538:
              case 65539:
              case 65540:
              case 65541:
                goto LABEL_48;
              default:
                goto LABEL_245;
            }
            while ( v94 < (unsigned __int64)v37 )
            {
              v38 = (const struct SchemaEntry * near *)(*((_QWORD *)&_ImageBase + v95 + 69844) + (v94 << 7));
              if ( *(_DWORD *)v38 == 36 )
                goto LABEL_50;
              ++v94;
            }
LABEL_245:
            v38 = (const struct SchemaEntry * near *)&qword_18009D560;
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
            v44 = &qword_18009D560;
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
                  &qword_18009D560);
          v44 = &qword_18009D560;
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
        v44 = &qword_18009D560;
      }
    }
    else
    {
      if ( v34 )
        v76 = *(_QWORD *)v34;
      else
        v76 = 0;
      v77 = *((_DWORD *)a2 + 38);
      v44 = &qword_18009D560;
      if ( v77 )
      {
        *((_DWORD *)a2 + 38) = v77 + 1;
      }
      else
      {
        v37 = (struct IErrorInfo *)*(unsigned int *)a2;
        if ( (_DWORD)v37 == 65542 )
        {
LABEL_119:
          v38 = (&Schema::schemaEntries)[(unsigned __int16)v37] + 1776;
          v78 = *(_DWORD *)v38;
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
              goto LABEL_119;
            default:
              goto LABEL_238;
          }
          while ( v107 < (unsigned __int64)v37 )
          {
            v38 = (const struct SchemaEntry * near *)(*((_QWORD *)&_ImageBase + v108 + 69844) + (v107 << 7));
            if ( *(_DWORD *)v38 == 111 )
              goto LABEL_121;
            ++v107;
          }
LABEL_238:
          v38 = (const struct SchemaEntry * near *)&qword_18009D560;
          v78 = 0;
        }
        if ( v78 )
        {
LABEL_121:
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
            goto LABEL_123;
          if ( !v80 && v76 )
          {
            v81 = *((_QWORD *)a2 + 2);
            if ( !v81 )
              _com_raise_error(-2147467261, v37);
            v39 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v81 + 224LL))(v81, v76);
            if ( v39 < 0 )
              goto LABEL_123;
          }
          v44 = &qword_18009D560;
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
                &qword_18009D560);
        v44 = &qword_18009D560;
      }
      if ( v39 < 0 )
        goto LABEL_123;
      v41 = (int *)((char *)this + 16);
    }
    if ( (*v41 & 0x1000000) != 0 )
    {
      v48 = TaskXmlWriter::ElementRunLevel(a2, 101, 1);
      if ( v48 < 0 )
        goto LABEL_52;
      v44 = &qword_18009D560;
    }
    if ( (*v41 & 0x8000000) == 0 )
    {
LABEL_84:
      if ( (*v41 & 0x10000000) != 0 )
      {
        v39 = TaskXmlWriter::Element(a2, 133, L"Unrestricted");
        if ( v39 < 0 )
          goto LABEL_123;
        v44 = &qword_18009D560;
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
                    v109 = 0;
                    v110 = (unsigned __int16)v37;
                    v37 = (struct IErrorInfo *)(&Schema::schemaEntriesCount)[(unsigned __int16)v37];
                    break;
                  case 65538:
                  case 65539:
                  case 65540:
                  case 65541:
                    goto LABEL_90;
                  default:
                    goto LABEL_265;
                }
                while ( v109 < (unsigned __int64)v37 )
                {
                  v38 = (const struct SchemaEntry * near *)(*((_QWORD *)&_ImageBase + v110 + 69844) + (v109 << 7));
                  if ( *(_DWORD *)v38 == 145 )
                    goto LABEL_92;
                  ++v109;
                }
LABEL_265:
                v38 = (const struct SchemaEntry * near *)&qword_18009D560;
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
                  goto LABEL_102;
                if ( !v67 )
                {
                  v69 = *((_QWORD *)a2 + 2);
                  if ( !v69 )
                    _com_raise_error(-2147467261, v37);
                  v68 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v69 + 224LL))(v69, v63);
                  if ( v68 < 0 )
                    goto LABEL_102;
                }
                v44 = &qword_18009D560;
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
              v68 = (*(__int64 (__fastcall **)(__int64, struct IErrorInfo *, const struct SchemaEntry * near *, __int64 *))(*(_QWORD *)v71 + 120LL))(
                      v71,
                      v37,
                      v38,
                      &qword_18009D560);
              v44 = &qword_18009D560;
            }
            if ( v68 < 0 )
            {
LABEL_102:
              if ( v34 )
                _bstr_t::Data_t::Release((_bstr_t::Data_t *)v34);
              return (unsigned int)v68;
            }
          }
        }
        if ( (unsigned int)((__int64)(*((_QWORD *)this + 24) - *((_QWORD *)this + 23)) >> 3) )
        {
          v84 = *((_DWORD *)a2 + 38);
          if ( v84 )
          {
            *((_DWORD *)a2 + 38) = v84 + 1;
          }
          else
          {
            v85 = *(_DWORD *)a2;
            if ( *(_DWORD *)a2 == 65542 )
            {
LABEL_136:
              v86 = (&Schema::schemaEntries)[(unsigned __int16)v85] + 2336;
              v87 = *(_DWORD *)v86;
            }
            else
            {
              switch ( v85 )
              {
                case 65536:
                case 65537:
                  v111 = 0;
                  v112 = (unsigned __int16)v85;
                  v113 = (&Schema::schemaEntriesCount)[(unsigned __int16)v85];
                  break;
                case 65538:
                case 65539:
                case 65540:
                case 65541:
                  goto LABEL_136;
                default:
                  goto LABEL_272;
              }
              while ( v111 < (unsigned __int64)v113 )
              {
                v86 = (const struct SchemaEntry * near *)(*((_QWORD *)&_ImageBase + v112 + 69844) + (v111 << 7));
                if ( *(_DWORD *)v86 == 146 )
                  goto LABEL_138;
                ++v111;
              }
LABEL_272:
              v86 = (const struct SchemaEntry * near *)&qword_18009D560;
              v87 = 0;
            }
            if ( v87 )
            {
LABEL_138:
              v88 = _com_ptr_t<_com_IIID<IXmlWriter,&__s_GUID const _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030>>::operator->((char *)a2 + 16);
              v74 = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, const struct SchemaEntry *, unsigned __int16 *const))(*(_QWORD *)v88 + 216LL))(
                      v88,
                      &ChannelPath,
                      v86[1],
                      Schema::namespaceUri);
              if ( v74 < 0 )
              {
LABEL_109:
                _bstr_t::~_bstr_t((_bstr_t *)&v126);
                return (unsigned int)v74;
              }
            }
            else
            {
              *((_DWORD *)a2 + 38) = 1;
            }
          }
          v122 = 0;
          v123 = (__int64)(*((_QWORD *)this + 24) - *((_QWORD *)this + 23)) >> 3;
          while ( (unsigned int)v122 < (unsigned int)v123 )
          {
            v120 = *(__int64 **)(*((_QWORD *)this + 23) + 8 * v122);
            if ( v120 )
              v121 = *v120;
            else
              v121 = 0;
            v48 = JobBucket::WriteOptionalXmlElement(v40, a2, 147, v121);
            if ( v48 < 0 )
              goto LABEL_52;
            v122 = (unsigned int)(v122 + 1);
          }
          v74 = TaskXmlWriter::EndElement(a2);
          if ( v74 < 0 )
            goto LABEL_109;
        }
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
          v74 = (*(__int64 (__fastcall **)(__int64, struct IErrorInfo *, const struct SchemaEntry * near *, __int64 *))(*(_QWORD *)v73 + 120LL))(
                  v73,
                  v37,
                  v38,
                  v44);
          if ( v74 < 0 )
            goto LABEL_109;
        }
        v124 = TaskXmlWriter::EndElement(a2);
        _bstr_t::~_bstr_t((_bstr_t *)&v126);
        return v124;
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
              v99 = 0;
              v100 = (unsigned __int16)v50;
              v50 = (unsigned __int64)(&Schema::schemaEntriesCount)[(unsigned __int16)v50];
              break;
            case 65538:
            case 65539:
            case 65540:
            case 65541:
              goto LABEL_56;
            default:
              goto LABEL_258;
          }
          while ( v99 < v50 )
          {
            v51 = (const struct SchemaEntry * near *)(*((_QWORD *)&_ImageBase + v100 + 69844) + (v99 << 7));
            if ( *(_DWORD *)v51 == 134 )
              goto LABEL_58;
            ++v99;
          }
LABEL_258:
          v51 = (const struct SchemaEntry * near *)&qword_18009D560;
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
      v116 = 1;
      v117 = *((_QWORD *)this + 26);
      if ( v117 )
        v118 = *(_QWORD *)(v117 + 48);
      else
        v118 = 0;
      while ( v116 )
      {
        if ( (v118 & v116) != 0 )
        {
          StringSid = 0;
          if ( (unsigned int)User::GetPrivilegeName(v116, (const unsigned __int16 **)&StringSid) )
          {
            v119 = TaskXmlWriter::Element(a2, 135, StringSid);
            if ( v119 < 0 )
            {
              _bstr_t::~_bstr_t((_bstr_t *)&v126);
              return (unsigned int)v119;
            }
          }
        }
        v116 *= 2LL;
      }
      v39 = TaskXmlWriter::EndElement(a2);
      if ( v39 >= 0 )
      {
        v44 = &qword_18009D560;
        goto LABEL_86;
      }
LABEL_123:
      _bstr_t::~_bstr_t((_bstr_t *)&v126);
      return (unsigned int)v39;
    }
    v48 = TaskXmlWriter::ElementProcessTokenSidType(a2, 133, 0);
    if ( v48 >= 0 )
    {
      v44 = &qword_18009D560;
      goto LABEL_84;
    }
LABEL_52:
    _bstr_t::~_bstr_t((_bstr_t *)&v126);
    return (unsigned int)v48;
  }
  return result;
}

```

## disassembly

```asm
0x1800123e0  mov     [rsp-38h+arg_0], rbx
0x1800123e5  mov     [rsp-38h+arg_10], r8
0x1800123ea  push    rbp
0x1800123eb  push    rsi
0x1800123ec  push    rdi
0x1800123ed  push    r12
0x1800123ef  push    r13
0x1800123f1  push    r14
0x1800123f3  push    r15
0x1800123f5  mov     rbp, rsp
0x1800123f8  sub     rsp, 40h
0x1800123fc  mov     rbx, rdx
0x1800123ff  mov     r15, rcx
0x180012402  mov     eax, [rdx+98h]
0x180012408  lea     r13, __ImageBase
0x18001240f  mov     r8, cs:off_1800886D0
0x180012416  test    eax, eax
0x180012418  jnz     loc_1800130D4
0x18001241e  mov     edx, [rdx]
0x180012420  cmp     edx, 10006h
0x180012426  jnz     loc_180012CA6
0x18001242c  movzx   eax, dx; jumptable 0000000180012CC2 cases 65538-65541
0x18001242f  mov     rdx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r13+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180012437  add     rdx, 3080h; struct IErrorInfo *
0x18001243e  mov     eax, [rdx]
0x180012440  test    eax, eax
0x180012442  jz      loc_1800130EC
0x180012448  mov     rcx, [rbx+10h]
0x18001244c  test    rcx, rcx
0x18001244f  jz      loc_1800130FB
0x180012455  mov     rax, [rcx]
0x180012458  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x18001245f  mov     r8, [rdx+8]
0x180012463  lea     rdx, ChannelPath
0x18001246a  mov     rax, [rax+0D8h]
0x180012471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012476  test    eax, eax
0x180012478  js      loc_1800127DA
0x18001247e  mov     r8, cs:off_1800886D0
0x180012485  mov     rax, [r15+48h]
0x180012489  test    rax, rax
0x18001248c  jz      loc_18001259A
0x180012492  mov     rcx, [rax]; pbstr
0x180012495  test    rcx, rcx
0x180012498  jz      loc_180013106
0x18001249e  call    cs:__imp_SysStringLen
0x1800124a4  mov     r8, cs:off_1800886D0
0x1800124ab  test    eax, eax
0x1800124ad  jz      loc_18001259A
0x1800124b3  mov     rax, [r15+48h]
0x1800124b7  test    rax, rax
0x1800124ba  jz      loc_180012D04
0x1800124c0  mov     rsi, [rax]
0x1800124c3  mov     eax, [rbx+98h]
0x1800124c9  test    eax, eax
0x1800124cb  jnz     loc_18001310D
0x1800124d1  mov     edx, [rbx]
0x1800124d3  cmp     edx, 10006h
0x1800124d9  jnz     loc_180012D62
0x1800124df  movzx   eax, dx; jumptable 0000000180012D7E cases 65538-65541
0x1800124e2  mov     rdx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r13+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x1800124ea  add     rdx, 3100h; struct IErrorInfo *
0x1800124f1  mov     eax, [rdx]
0x1800124f3  test    eax, eax
0x1800124f5  jz      loc_18001312A
0x1800124fb  mov     rcx, [rbx+10h]
0x1800124ff  test    rcx, rcx
0x180012502  jz      loc_18001313E
0x180012508  mov     rax, [rcx]
0x18001250b  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x180012512  mov     r8, [rdx+8]
0x180012516  lea     rdx, ChannelPath
0x18001251d  mov     rax, [rax+0D8h]
0x180012524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012529  mov     edx, eax
0x18001252b  test    eax, eax
0x18001252d  js      loc_180012602
0x180012533  mov     r8d, [rbx]
0x180012536  cmp     r8d, 10006h
0x18001253d  jnz     loc_180012E91
0x180012543  movzx   eax, r8w; jumptable 0000000180012EAE cases 65538-65541
0x180012547  mov     rax, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r13+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x18001254f  mov     ecx, [rax+3180h]
0x180012555  test    ecx, ecx
0x180012557  jz      loc_180012602
0x18001255d  lea     rcx, [rbx+10h]
0x180012561  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlWriter@@$1?_GUID_7279fc88_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlWriter@@XZ; _com_ptr_t<_com_IIID<IXmlWriter,&__s_GUID const _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x180012566  mov     rdi, rax
0x180012569  mov     r11, [rax]
0x18001256c  mov     edx, 63h ; 'c'
0x180012571  mov     rcx, rbx
0x180012574  call    ?GetEntry@Schema@@AEBAAEBUSchemaEntry@@W4TaskXmlNodeId@@@Z; Schema::GetEntry(TaskXmlNodeId)
0x180012579  mov     [rsp+40h+var_20], rsi
0x18001257e  xor     r9d, r9d
0x180012581  mov     r8, [rax+8]
0x180012585  lea     rdx, ChannelPath
0x18001258c  mov     rcx, rdi
0x18001258f  mov     rax, [r11+38h]
0x180012593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012598  jmp     short loc_180012600
0x18001259a  mov     eax, [rbx+98h]
0x1800125a0  test    eax, eax
0x1800125a2  jnz     loc_180013157
0x1800125a8  mov     edx, [rbx]
0x1800125aa  cmp     edx, 10006h
0x1800125b0  jnz     loc_180012E3B
0x1800125b6  movzx   eax, dx; jumptable 0000000180012E57 cases 65538-65541
0x1800125b9  mov     rdx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r13+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x1800125c1  add     rdx, 3100h; struct IErrorInfo *
0x1800125c8  mov     eax, [rdx]
0x1800125ca  test    eax, eax
0x1800125cc  jz      loc_180013174
0x1800125d2  mov     rcx, [rbx+10h]
0x1800125d6  test    rcx, rcx
0x1800125d9  jz      loc_180013188
0x1800125df  mov     rax, [rcx]
0x1800125e2  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x1800125e9  mov     r8, [rdx+8]
0x1800125ed  lea     rdx, ChannelPath
0x1800125f4  mov     rax, [rax+0D8h]
0x1800125fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012600  mov     edx, eax
0x180012602  test    edx, edx
0x180012604  js      loc_180013193
0x18001260a  mov     rax, [r15+50h]
0x18001260e  test    rax, rax
0x180012611  jz      short loc_18001262D
0x180012613  mov     rcx, [rax]; pbstr
0x180012616  test    rcx, rcx
0x180012619  jz      loc_18001319A
0x18001261f  call    cs:__imp_SysStringLen
0x180012625  test    eax, eax
0x180012627  jnz     loc_180012FFC
0x18001262d  xor     edi, edi
0x18001262f  mov     [rbp+arg_10], rdi
0x180012633  mov     rcx, [r15+40h]
0x180012637  test    rcx, rcx
0x18001263a  jz      loc_1800131A1
0x180012640  mov     [rbp+StringSid], rdi
0x180012644  lea     rdx, [rbp+StringSid]; StringSid
0x180012648  mov     rcx, [rcx+20h]; Sid
0x18001264c  call    cs:__imp_ConvertSidToStringSidW
0x180012652  test    eax, eax
0x180012654  jnz     loc_180012A4E
0x18001265a  call    cs:__imp_GetLastError
0x180012660  mov     esi, eax
0x180012662  test    eax, eax
0x180012664  jle     short loc_18001266F
0x180012666  movzx   esi, ax
0x180012669  or      esi, 80070000h
0x18001266f  test    esi, esi
0x180012671  js      loc_180012B40
0x180012677  mov     rax, [r15+40h]
0x18001267b  mov     ecx, [rax+28h]
0x18001267e  lea     eax, [rcx-2]
0x180012681  test    eax, 0FFFFFFFCh
0x180012686  jnz     short loc_18001269E
0x180012688  cmp     ecx, 3
0x18001268b  jz      short loc_18001269E
0x18001268d  lea     rcx, [r15+40h]; this
0x180012691  call    ?IsLocalSystem@User@@QEBA_NXZ; User::IsLocalSystem(void)
0x180012696  test    al, al
0x180012698  jz      loc_1800131B2
0x18001269e  lea     rsi, [r15+10h]
0x1800126a2  test    dword ptr [rsi], 20000h
0x1800126a8  jz      loc_1800127F2
0x1800126ae  test    rdi, rdi
0x1800126b1  jz      loc_180012CFC
0x1800126b7  mov     r12, [rdi]
0x1800126ba  mov     eax, [rbx+98h]
0x1800126c0  mov     r9, cs:off_1800886D0
0x1800126c7  test    eax, eax
0x1800126c9  jnz     loc_180013244
0x1800126cf  mov     edx, [rbx]; struct IErrorInfo *
0x1800126d1  cmp     edx, 10006h
0x1800126d7  jnz     loc_180012D0B
0x1800126dd  movzx   eax, dx; jumptable 0000000180012D27 cases 65538-65541
0x1800126e0  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r13+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x1800126e8  add     r8, 1200h
0x1800126ef  mov     eax, [r8]
0x1800126f2  test    eax, eax
0x1800126f4  jz      loc_18001325C
0x1800126fa  mov     rcx, [rbx+10h]
0x1800126fe  test    rcx, rcx
0x180012701  jz      loc_18001326B
0x180012707  mov     rax, [rcx]
0x18001270a  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x180012711  mov     r8, [r8+8]
0x180012715  lea     rdx, ChannelPath
0x18001271c  mov     rax, [rax+0D8h]
0x180012723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012728  mov     r14d, eax
0x18001272b  test    eax, eax
0x18001272d  jns     loc_180012849
0x180012733  lea     rcx, [rbp+arg_10]; this
0x180012737  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001273c  mov     eax, r14d
0x18001273f  jmp     loc_1800127DA
0x180012744  cmp     qword ptr [rax+30h], 0
0x180012749  jz      loc_1800128EF
0x18001274f  mov     eax, [rbx+98h]
0x180012755  test    eax, eax
0x180012757  jnz     loc_180013308
0x18001275d  mov     edx, [rbx]; struct IErrorInfo *
0x18001275f  cmp     edx, 10006h
0x180012765  jnz     loc_180012DB8
0x18001276b  movzx   eax, dx; jumptable 0000000180012DD4 cases 65538-65541
0x18001276e  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r13+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180012776  add     r8, 4300h
0x18001277d  mov     eax, [r8]
0x180012780  test    eax, eax
0x180012782  jz      loc_180013320
0x180012788  mov     rcx, [rbx+10h]
0x18001278c  test    rcx, rcx
0x18001278f  jz      loc_18001332F
0x180012795  mov     rax, [rcx]
0x180012798  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x18001279f  mov     r8, [r8+8]
0x1800127a3  lea     rdx, ChannelPath
0x1800127aa  mov     rax, [rax+0D8h]
0x1800127b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127b6  mov     esi, eax
0x1800127b8  test    eax, eax
0x1800127ba  jns     loc_180013027
0x1800127c0  test    rdi, rdi
0x1800127c3  jz      short loc_1800127D8
0x1800127c5  mov     edx, 0FFFFFFFFh
0x1800127ca  lock xadd [rdi+10h], edx; unsigned int
0x1800127cf  cmp     edx, 1
0x1800127d2  jz      loc_180012A80
0x1800127d8  mov     eax, esi
0x1800127da  mov     rbx, [rsp+40h+arg_0]
0x1800127e2  add     rsp, 40h
0x1800127e6  pop     r15
0x1800127e8  pop     r14
0x1800127ea  pop     r13
0x1800127ec  pop     r12
0x1800127ee  pop     rdi
0x1800127ef  pop     rsi
0x1800127f0  pop     rbp
0x1800127f1  retn
0x1800127f2  test    rdi, rdi
0x1800127f5  jz      loc_180012F9B
0x1800127fb  mov     r8, [rdi]
0x1800127fe  mov     edx, 24h ; '$'
0x180012803  mov     rcx, rbx
0x180012806  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x18001280b  mov     r14d, eax
0x18001280e  test    eax, eax
0x180012810  js      loc_180012733
0x180012816  mov     eax, [rsi]
0x180012818  bt      eax, 12h
0x18001281c  jb      loc_180012C37
0x180012822  bt      eax, 0Eh
0x180012826  jb      loc_1800132AB
0x18001282c  bt      eax, 10h
0x180012830  jb      short loc_18001283D
0x180012832  test    eax, 80000h
0x180012837  jnz     loc_18001329F
0x18001283d  lea     r8, aInteractivetok; "InteractiveToken"
0x180012844  jmp     loc_180012C3E
0x180012849  jnz     short loc_18001287A
0x18001284b  test    r12, r12
0x18001284e  jz      short loc_18001287A
0x180012850  mov     rcx, [rbx+10h]
0x180012854  test    rcx, rcx
0x180012857  jz      loc_180013276
0x18001285d  mov     rax, [rcx]
0x180012860  mov     rdx, r12
0x180012863  mov     rax, [rax+0E0h]
0x18001286a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001286f  mov     r14d, eax
0x180012872  test    eax, eax
0x180012874  js      loc_180012733
0x18001287a  mov     r9, cs:off_1800886D0
0x180012881  mov     eax, [rbx+98h]
0x180012887  test    eax, eax
0x180012889  jnz     loc_180013281
0x18001288f  mov     rcx, [rbx+10h]
0x180012893  test    rcx, rcx
0x180012896  jz      loc_180013294
0x18001289c  mov     rax, [rcx]
0x18001289f  mov     rax, [rax+78h]
0x1800128a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128a8  mov     r14d, eax
0x1800128ab  mov     r9, cs:off_1800886D0
0x1800128b2  test    r14d, r14d
0x1800128b5  js      loc_180012733
0x1800128bb  test    dword ptr [rsi], 1000000h
0x1800128c1  jnz     loc_1800132B7
0x1800128c7  test    dword ptr [rsi], 8000000h
0x1800128cd  jnz     loc_1800132E1
0x1800128d3  test    dword ptr [rsi], 10000000h
0x1800128d9  jnz     loc_180012A96
0x1800128df  mov     rax, [r15+0D0h]
0x1800128e6  test    rax, rax
0x1800128e9  jnz     loc_180012744
0x1800128ef  mov     rax, [r15+0B0h]
0x1800128f6  test    rax, rax
0x1800128f9  jz      loc_1800129F3
  ... truncated ...
```
