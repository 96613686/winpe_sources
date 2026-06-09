# TaskDefinitionImpl::WriteJobSettingsXml(TaskXmlWriter &)

- ea: `0x180002db0`
- end: `0x180003a28`
- name: `?WriteJobSettingsXml@TaskDefinitionImpl@@AEAAJAEAVTaskXmlWriter@@@Z`
- size: `3192`
- prototype: `int(TaskDefinitionImpl *__hidden this, struct TaskXmlWriter *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800052c0`

## callees

- `0x180001880`
- `0x180001b70`
- `0x180001d4c`
- `0x180002554`
- `0x180002db0`
- `0x180003a30`
- `0x180003be8`
- `0x180003ea0`
- `0x180003f30`
- `0x1800145c0`
- `0x180016900`
- `0x18003b74c`
- `0x18003d034`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180003320`
- `OLEAUT32!__imp_SysFreeString` at `0x1800033ba`
- `OLEAUT32!__imp_SysFreeString` at `0x1800035bf`
- `OLEAUT32!__imp_SysFreeString` at `0x18000369e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800037ec`
- `OLEAUT32!__imp_SysFreeString` at `0x180003976`
- `OLEAUT32!__imp_SysFreeString` at `0x1800039b6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800039d7`
- `OLEAUT32!__imp_SysFreeString` at `0x180003320`
- `OLEAUT32!__imp_SysFreeString` at `0x1800033ba`
- `OLEAUT32!__imp_SysFreeString` at `0x1800035bf`
- `OLEAUT32!__imp_SysFreeString` at `0x18000369e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800037ec`
- `OLEAUT32!__imp_SysFreeString` at `0x180003976`
- `OLEAUT32!__imp_SysFreeString` at `0x1800039b6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800039d7`
- `OLEAUT32!__imp_SysStringLen` at `0x18000358c`
- `OLEAUT32!__imp_SysStringLen` at `0x180003654`
- `OLEAUT32!__imp_SysStringLen` at `0x180003943`
- `OLEAUT32!__imp_SysStringLen` at `0x18000358c`
- `OLEAUT32!__imp_SysStringLen` at `0x180003654`
- `OLEAUT32!__imp_SysStringLen` at `0x180003943`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall TaskDefinitionImpl::WriteJobSettingsXml(TaskDefinitionImpl *this, struct IErrorInfo *a2)
{
  struct IErrorInfo *v2; // rdi
  struct ITaskSettings3 *v4; // rbx
  int lpVtbl; // eax
  int v6; // r8d
  const struct SchemaEntry * near *v7; // r8
  struct IErrorInfoVtbl *v8; // rcx
  int v9; // esi
  struct IErrorInfo *v10; // rdx
  int started; // esi
  int v12; // eax
  int v13; // r8d
  const struct SchemaEntry * near *v14; // r8
  struct IErrorInfoVtbl *v15; // rcx
  int v16; // eax
  int v17; // esi
  const wchar_t *v18; // rsi
  const wchar_t *v19; // r8
  int v20; // r14d
  const wchar_t *v21; // r8
  const wchar_t *v22; // r8
  const wchar_t *v23; // r8
  const wchar_t *v24; // r8
  const wchar_t *v25; // r8
  const wchar_t *v26; // r8
  const wchar_t *v27; // r8
  const wchar_t *v28; // r8
  int v29; // eax
  struct IErrorInfo *v31; // rdx
  OLECHAR *v32; // rcx
  int v33; // eax
  struct IErrorInfoVtbl *v34; // rcx
  int v35; // edi
  __int64 v36; // rax
  const wchar_t *v37; // r8
  const wchar_t *v38; // r8
  int v39; // eax
  __int64 v40; // rax
  int v41; // eax
  int v42; // esi
  TaskDefinitionImpl *v43; // rcx
  int v44; // r14d
  __int64 v45; // r8
  const unsigned __int64 near *v46; // r9
  __int64 v47; // r10
  const unsigned __int64 near *v48; // r9
  __int64 v49; // r10
  unsigned int v50; // [rsp+30h] [rbp-20h] BYREF
  struct ITaskSettings3 *v51; // [rsp+38h] [rbp-18h] BYREF
  struct ITaskSettings3 *v52; // [rsp+40h] [rbp-10h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-8h] BYREF
  __int16 v54; // [rsp+90h] [rbp+40h] BYREF
  int v55; // [rsp+A0h] [rbp+50h] BYREF
  int v56; // [rsp+A8h] [rbp+58h] BYREF

  v2 = a2;
  v4 = (struct ITaskSettings3 *)*((_QWORD *)this + 10);
  v52 = v4;
  if ( v4 )
    ((void (__fastcall *)(struct ITaskSettings3 *))v4->lpVtbl->AddRef)(v4);
  if ( !*((_QWORD *)this + 10) )
  {
LABEL_81:
    if ( v4 )
      ((void (__fastcall *)(struct ITaskSettings3 *))v4->lpVtbl->Release)(v4);
    return 0;
  }
  lpVtbl = (int)v2[19].lpVtbl;
  if ( lpVtbl )
  {
    LODWORD(v2[19].lpVtbl) = lpVtbl + 1;
  }
  else
  {
    v6 = (int)v2->lpVtbl;
    if ( LODWORD(v2->lpVtbl) == 65542 )
    {
LABEL_6:
      v7 = (&Schema::schemaEntries)[(unsigned __int16)v6] + 1136;
    }
    else
    {
      switch ( v6 )
      {
        case 65536:
        case 65537:
          a2 = 0;
          v46 = (&Schema::schemaEntriesCount)[(unsigned __int16)v6];
          v47 = 8LL * (unsigned __int16)v6 + 384824;
          break;
        case 65538:
        case 65539:
        case 65540:
        case 65541:
          goto LABEL_6;
        default:
          goto LABEL_140;
      }
      while ( a2 < (struct IErrorInfo *)v46 )
      {
        v7 = (const struct SchemaEntry * near *)(*(_QWORD *)((char *)&_ImageBase + v47) + ((_QWORD)a2 << 7));
        if ( *(_DWORD *)v7 == 71 )
          goto LABEL_8;
        a2 = (struct IErrorInfo *)((char *)a2 + 1);
      }
LABEL_140:
      v7 = (const struct SchemaEntry * near *)&qword_180072DF0;
    }
    if ( *(_DWORD *)v7 )
    {
LABEL_8:
      v8 = v2[2].lpVtbl;
      if ( !v8 )
        _com_raise_error(-2147467261, a2);
      v9 = (*((__int64 (__fastcall **)(struct IErrorInfoVtbl *, const unsigned __int16 *, const struct SchemaEntry *, wchar_t *const))v8->QueryInterface
            + 27))(
             v8,
             &Src,
             v7[1],
             Schema::namespaceUri);
      if ( v9 < 0 )
      {
        if ( v4 )
          ((void (__fastcall *)(struct ITaskSettings3 *))v4->lpVtbl->Release)(v4);
        return (unsigned int)v9;
      }
    }
    else
    {
      LODWORD(v2[19].lpVtbl) = 1;
    }
  }
  v56 = 0;
  started = ((__int64 (__fastcall *)(struct ITaskSettings3 *, int *))v4->lpVtbl->get_MultipleInstances)(v4, &v56);
  if ( started < 0 )
    goto LABEL_72;
  if ( v56 == 1 )
  {
    v12 = (int)v2[19].lpVtbl;
    if ( v12 )
    {
      LODWORD(v2[19].lpVtbl) = v12 + 1;
    }
    else
    {
      v13 = (int)v2->lpVtbl;
      if ( LODWORD(v2->lpVtbl) == 65542 )
      {
LABEL_14:
        v14 = (&Schema::schemaEntries)[(unsigned __int16)v13] + 1168;
      }
      else
      {
        switch ( v13 )
        {
          case 65536:
          case 65537:
            v10 = 0;
            v48 = (&Schema::schemaEntriesCount)[(unsigned __int16)v13];
            v49 = 8LL * (unsigned __int16)v13 + 384824;
            break;
          case 65538:
          case 65539:
          case 65540:
          case 65541:
            goto LABEL_14;
          default:
            goto LABEL_141;
        }
        while ( v10 < (struct IErrorInfo *)v48 )
        {
          v14 = (const struct SchemaEntry * near *)(*(_QWORD *)((char *)&_ImageBase + v49) + ((_QWORD)v10 << 7));
          if ( *(_DWORD *)v14 == 73 )
            goto LABEL_16;
          v10 = (struct IErrorInfo *)((char *)v10 + 1);
        }
LABEL_141:
        v14 = (const struct SchemaEntry * near *)&qword_180072DF0;
      }
      if ( *(_DWORD *)v14 )
      {
LABEL_16:
        v15 = v2[2].lpVtbl;
        if ( !v15 )
          _com_raise_error(-2147467261, v10);
        v16 = (*((__int64 (__fastcall **)(struct IErrorInfoVtbl *, const unsigned __int16 *, const struct SchemaEntry *, wchar_t *const))v15->QueryInterface
               + 27))(
                v15,
                &Src,
                v14[1],
                Schema::namespaceUri);
        v17 = v16;
        if ( v16 < 0 )
          goto LABEL_18;
        if ( !v16 )
        {
          v36 = _com_ptr_t<_com_IIID<IXmlWriter,&__s_GUID const _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030>>::operator->(&v2[2]);
          v17 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v36 + 224LL))(v36, L"Queue");
          if ( v17 < 0 )
            goto LABEL_18;
        }
      }
      else
      {
        LODWORD(v2[19].lpVtbl) = 1;
      }
    }
    v39 = (int)v2[19].lpVtbl;
    if ( v39 )
    {
      LODWORD(v2[19].lpVtbl) = v39 - 1;
      v17 = 1;
      goto LABEL_18;
    }
    v40 = _com_ptr_t<_com_IIID<IXmlWriter,&__s_GUID const _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030>>::operator->(&v2[2]);
    v41 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v40 + 120LL))(v40);
  }
  else if ( v56 )
  {
    if ( v56 == 2 )
    {
      v41 = TaskXmlWriter::Element(v2, 73, L"IgnoreNew");
    }
    else
    {
      if ( v56 != 3 )
      {
        v17 = TaskXmlWriter::Element(v2, 73, L"IgnoreNew");
        goto LABEL_18;
      }
      v41 = TaskXmlWriter::Element(v2, 73, L"StopExisting");
    }
  }
  else
  {
    v41 = TaskXmlWriter::Element(v2, 73, L"Parallel");
  }
  v17 = v41;
LABEL_18:
  if ( v17 >= 0 )
  {
    v54 = 0;
    started = ((__int64 (__fastcall *)(struct ITaskSettings3 *, __int16 *))v4->lpVtbl->get_DisallowStartIfOnBatteries)(
                v4,
                &v54);
    if ( started >= 0 )
    {
      v18 = L"true";
      v19 = L"true";
      if ( !v54 )
        v19 = L"false";
      v20 = TaskXmlWriter::Element(v2, 74, v19);
      if ( v20 < 0 )
        goto LABEL_156;
      v20 = ((__int64 (__fastcall *)(struct ITaskSettings3 *, __int16 *))v4->lpVtbl->get_StopIfGoingOnBatteries)(
              v4,
              &v54);
      if ( v20 < 0 )
        goto LABEL_156;
      v21 = L"true";
      if ( !v54 )
        v21 = L"false";
      v20 = TaskXmlWriter::Element(v2, 75, v21);
      if ( v20 < 0 )
        goto LABEL_156;
      v20 = ((__int64 (__fastcall *)(struct ITaskSettings3 *, __int16 *))v4->lpVtbl->get_AllowHardTerminate)(v4, &v54);
      if ( v20 < 0 )
        goto LABEL_156;
      v22 = L"true";
      if ( !v54 )
        v22 = L"false";
      v20 = TaskXmlWriter::Element(v2, 76, v22);
      if ( v20 < 0 )
        goto LABEL_156;
      v20 = ((__int64 (__fastcall *)(struct ITaskSettings3 *, __int16 *))v4->lpVtbl->get_StartWhenAvailable)(v4, &v54);
      if ( v20 < 0 )
        goto LABEL_156;
      v23 = L"true";
      if ( !v54 )
        v23 = L"false";
      v20 = TaskXmlWriter::Element(v2, 77, v23);
      if ( v20 < 0 )
        goto LABEL_156;
      v20 = ((__int64 (__fastcall *)(struct ITaskSettings3 *, __int16 *))v4->lpVtbl->get_RunOnlyIfNetworkAvailable)(
              v4,
              &v54);
      if ( v20 < 0 )
        goto LABEL_156;
      v24 = L"true";
      if ( !v54 )
        v24 = L"false";
      v20 = TaskXmlWriter::Element(v2, 78, v24);
      if ( v20 < 0 )
        goto LABEL_156;
      if ( v54 )
      {
        v51 = v4;
        ((void (__fastcall *)(struct ITaskSettings3 *))v4->lpVtbl->AddRef)(v4);
        v20 = WriteNetworkSettings(v2, &v51);
        if ( v20 < 0 )
          goto LABEL_156;
      }
      v51 = v4;
      ((void (__fastcall *)(struct ITaskSettings3 *))v4->lpVtbl->AddRef)(v4);
      v20 = WriteIdleSettings(v2, &v51);
      if ( v20 < 0 )
        goto LABEL_156;
      v20 = ((__int64 (__fastcall *)(struct ITaskSettings3 *, __int16 *))v4->lpVtbl->get_AllowDemandStart)(v4, &v54);
      if ( v20 < 0 )
        goto LABEL_156;
      v25 = L"true";
      if ( !v54 )
        v25 = L"false";
      v20 = TaskXmlWriter::Element(v2, 72, v25);
      if ( v20 < 0 )
        goto LABEL_156;
      v20 = ((__int64 (__fastcall *)(struct ITaskSettings3 *, __int16 *))v4->lpVtbl->get_Enabled)(v4, &v54);
      if ( v20 < 0 )
        goto LABEL_156;
      v26 = L"true";
      if ( !v54 )
        v26 = L"false";
      v20 = TaskXmlWriter::Element(v2, 19, v26);
      if ( v20 < 0 )
        goto LABEL_156;
      v20 = ((__int64 (__fastcall *)(struct ITaskSettings3 *, __int16 *))v4->lpVtbl->get_Hidden)(v4, &v54);
      if ( v20 < 0 )
        goto LABEL_156;
      v27 = L"true";
      if ( !v54 )
        v27 = L"false";
      v20 = TaskXmlWriter::Element(v2, 81, v27);
      if ( v20 < 0 )
        goto LABEL_156;
      v20 = ((__int64 (__fastcall *)(struct ITaskSettings3 *, __int16 *))v4->lpVtbl->get_RunOnlyIfIdle)(v4, &v54);
      if ( v20 < 0 )
        goto LABEL_156;
      v28 = L"true";
      if ( !v54 )
        v28 = L"false";
      v20 = TaskXmlWriter::Element(v2, 84, v28);
      if ( v20 < 0 )
        goto LABEL_156;
      v55 = 0;
      v20 = ((__int64 (__fastcall *)(struct ITaskSettings3 *, int *))v4->lpVtbl->get_Compatibility)(v4, &v55);
      if ( v20 < 0 )
        goto LABEL_156;
      v29 = v55;
      if ( v55 >= 3 )
      {
        v51 = 0;
        if ( ((__int64 (__fastcall *)(struct ITaskSettings3 *, GUID *, struct ITaskSettings3 **))v4->lpVtbl->QueryInterface)(
               v4,
               &GUID_2c05c3f0_6eed_4c05_a15f_ed7d7a98a369,
               &v51) >= 0 )
        {
          v20 = ((__int64 (__fastcall *)(struct ITaskSettings3 *, __int16 *))v51->lpVtbl->get_AllowDemandStart)(
                  v51,
                  &v54);
          if ( v20 < 0 )
            goto LABEL_155;
          v37 = L"true";
          if ( !v54 )
            v37 = L"false";
          v20 = TaskXmlWriter::Element(v2, 132, v37);
          if ( v20 < 0 )
            goto LABEL_155;
          v20 = ((__int64 (__fastcall *)(struct ITaskSettings3 *, __int16 *))v51->lpVtbl->get_RestartInterval)(
                  v51,
                  &v54);
          if ( v20 < 0 )
            goto LABEL_155;
          v38 = L"true";
          if ( !v54 )
            v38 = L"false";
          v20 = TaskXmlWriter::Element(v2, 131, v38);
          if ( v20 < 0 )
          {
LABEL_155:
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v51);
            goto LABEL_156;
          }
        }
        if ( v51 )
          ((void (__fastcall *)(struct ITaskSettings3 *))v51->lpVtbl->Release)(v51);
        v29 = v55;
      }
      if ( v29 >= 4 )
      {
        v51 = 0;
        if ( ((__int64 (__fastcall *)(struct ITaskSettings3 *, GUID *, struct ITaskSettings3 **))v4->lpVtbl->QueryInterface)(
               v4,
               &GUID_0ad9d0d7_0c7f_4ebb_9a5f_d1c648dca528,
               &v51) >= 0 )
        {
          v44 = TaskDefinitionImpl::WriteMaintenanceSettings(v43, (struct TaskXmlWriter *)v2, v51);
          if ( v44 < 0
            || (v44 = ((__int64 (__fastcall *)(struct ITaskSettings3 *, __int16 *))v51->lpVtbl->get_Volatile)(v51, &v54),
                v44 < 0)
            || v54 && (LOBYTE(v45) = 1, v44 = TaskXmlWriter::ElementBool(v2, 140, v45), v44 < 0) )
          {
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v51);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v52);
            return (unsigned int)v44;
          }
        }
        if ( v51 )
          ((void (__fastcall *)(struct ITaskSettings3 *))v51->lpVtbl->Release)(v51);
      }
      v20 = ((__int64 (__fastcall *)(struct ITaskSettings3 *, __int16 *))v4->lpVtbl->get_WakeToRun)(v4, &v54);
      if ( v20 >= 0 )
      {
        if ( !v54 )
          v18 = L"false";
        started = TaskXmlWriter::Element(v2, 79, v18);
        if ( started < 0 )
          goto LABEL_72;
        bstrString = 0;
        started = ((__int64 (__fastcall *)(struct ITaskSettings3 *, BSTR *))v4->lpVtbl->get_ExecutionTimeLimit)(
                    v4,
                    &bstrString);
        if ( started < 0 )
          goto LABEL_71;
        if ( bstrString && SysStringLen(bstrString) )
        {
          v42 = TaskXmlWriter::Element(v2, 20, bstrString);
          if ( v42 < 0 )
          {
            SysFreeString(bstrString);
            ((void (__fastcall *)(struct ITaskSettings3 *))v4->lpVtbl->Release)(v4);
            return (unsigned int)v42;
          }
          SysFreeString(bstrString);
          bstrString = 0;
        }
        started = ((__int64 (__fastcall *)(struct ITaskSettings3 *, BSTR *))v4->lpVtbl->get_DeleteExpiredTaskAfter)(
                    v4,
                    &bstrString);
        if ( started < 0 )
          goto LABEL_71;
        if ( bstrString && SysStringLen(bstrString) )
        {
          started = TaskXmlWriter::Element(v2, 82, bstrString);
          if ( started < 0 )
          {
LABEL_71:
            SysFreeString(bstrString);
            goto LABEL_72;
          }
          SysFreeString(bstrString);
          bstrString = 0;
        }
        v50 = 7;
        started = ((__int64 (__fastcall *)(struct ITaskSettings3 *, unsigned int *))v4->lpVtbl->get_Priority)(v4, &v50);
        if ( started >= 0 )
        {
          if ( v50 > 0xA )
          {
            SysFreeString(bstrString);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v52);
            return 2147942487LL;
          }
          started = StringCchPrintfW((unsigned __int16 *)&v2[3], 0x40u, L"%d");
          if ( started >= 0 )
          {
            started = TaskXmlWriter::Element(v2, 83, &v2[3]);
            if ( started >= 0 )
            {
              started = ((__int64 (__fastcall *)(struct ITaskSettings3 *, BSTR *))v4->lpVtbl->get_RestartInterval)(
                          v4,
                          &bstrString);
              if ( started >= 0 )
              {
                v32 = bstrString;
                if ( !bstrString )
                {
LABEL_76:
                  v33 = (int)v2[19].lpVtbl;
                  if ( v33 )
                  {
                    LODWORD(v2[19].lpVtbl) = v33 - 1;
                  }
                  else
                  {
                    v34 = v2[2].lpVtbl;
                    if ( !v34 )
                      _com_raise_error(-2147467261, v31);
                    v35 = (*((__int64 (__fastcall **)(struct IErrorInfoVtbl *))v34->QueryInterface + 15))(v34);
                    if ( v35 < 0 )
                    {
                      SysFreeString(bstrString);
                      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v52);
                      return (unsigned int)v35;
                    }
                    v32 = bstrString;
                  }
                  SysFreeString(v32);
                  goto LABEL_81;
                }
                if ( !SysStringLen(bstrString) )
                  goto LABEL_124;
                started = TaskXmlWriter::StartElement(v2, 93);
                if ( started >= 0 )
                {
                  started = TaskXmlWriter::Element(v2, 94, bstrString);
                  if ( started >= 0 )
                  {
                    SysFreeString(bstrString);
                    bstrString = 0;
                    LODWORD(v51) = 0;
                    started = ((__int64 (__fastcall *)(struct ITaskSettings3 *, struct ITaskSettings3 **))v4->lpVtbl->get_RestartCount)(
                                v4,
                                &v51);
                    if ( started >= 0 )
                    {
                      if ( (int)v51 <= 0
                        || (started = TaskXmlWriter::ElementInt(v2, 95, (unsigned int)v51), started >= 0) )
                      {
                        started = TaskXmlWriter::EndElement(v2);
                        if ( started >= 0 )
                        {
LABEL_124:
                          v32 = bstrString;
                          goto LABEL_76;
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
        goto LABEL_71;
      }
LABEL_156:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v52);
      return (unsigned int)v20;
    }
LABEL_72:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v52);
    return (unsigned int)started;
  }
  if ( v4 )
    ((void (__fastcall *)(struct ITaskSettings3 *))v4->lpVtbl->Release)(v4);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180002db0  push    rbp
0x180002db2  push    rbx
0x180002db3  push    rsi
0x180002db4  push    rdi
0x180002db5  push    r12
0x180002db7  push    r14
0x180002db9  push    r15
0x180002dbb  mov     rbp, rsp
0x180002dbe  sub     rsp, 50h
0x180002dc2  mov     rdi, rdx
0x180002dc5  mov     rsi, rcx
0x180002dc8  mov     rbx, [rcx+50h]
0x180002dcc  mov     [rbp+var_10], rbx
0x180002dd0  test    rbx, rbx
0x180002dd3  jz      short loc_180002DE5
0x180002dd5  mov     rax, [rbx]
0x180002dd8  mov     rcx, rbx
0x180002ddb  mov     rax, [rax+8]
0x180002ddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002de4  nop
0x180002de5  cmp     qword ptr [rsi+50h], 0
0x180002dea  jz      loc_1800033C7
0x180002df0  mov     eax, [rdi+98h]
0x180002df6  lea     r14, __ImageBase
0x180002dfd  xor     r12d, r12d
0x180002e00  test    eax, eax
0x180002e02  jnz     loc_180003888
0x180002e08  mov     r8d, [rdi]
0x180002e0b  cmp     r8d, 10006h
0x180002e12  jnz     loc_1800036F7
0x180002e18  movzx   eax, r8w; jumptable 0000000180003714 cases 65538-65541
0x180002e1c  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r14+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180002e24  add     r8, 2380h
0x180002e2b  mov     eax, [r8]
0x180002e2e  test    eax, eax
0x180002e30  jz      loc_180003833
0x180002e36  mov     rcx, [rdi+10h]
0x180002e3a  test    rcx, rcx
0x180002e3d  jz      loc_180003895
0x180002e43  mov     rax, [rcx]
0x180002e46  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x180002e4d  mov     r8, [r8+8]
0x180002e51  lea     rdx, Src
0x180002e58  mov     rax, [rax+0D8h]
0x180002e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e64  mov     esi, eax
0x180002e66  test    eax, eax
0x180002e68  js      loc_18000384F
0x180002e6e  mov     [rbp+arg_18], r12d
0x180002e72  mov     rax, [rbx]
0x180002e75  lea     rdx, [rbp+arg_18]
0x180002e79  mov     rcx, rbx
0x180002e7c  mov     rax, [rax+68h]
0x180002e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e85  mov     esi, eax
0x180002e87  test    eax, eax
0x180002e89  js      loc_18000332D
0x180002e8f  mov     ecx, [rbp+arg_18]
0x180002e92  cmp     ecx, 1
0x180002e95  jnz     loc_1800037B3
0x180002e9b  mov     eax, [rdi+98h]
0x180002ea1  test    eax, eax
0x180002ea3  jnz     loc_1800038D9
0x180002ea9  mov     r8d, [rdi]
0x180002eac  cmp     r8d, 10006h
0x180002eb3  jnz     loc_180003754
0x180002eb9  movzx   eax, r8w; jumptable 0000000180003771 cases 65538-65541
0x180002ebd  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r14+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180002ec5  add     r8, 2480h
0x180002ecc  mov     eax, [r8]
0x180002ecf  test    eax, eax
0x180002ed1  jz      loc_180003552
0x180002ed7  mov     rcx, [rdi+10h]
0x180002edb  test    rcx, rcx
0x180002ede  jz      loc_1800038E6
0x180002ee4  mov     rax, [rcx]
0x180002ee7  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x180002eee  mov     r8, [r8+8]
0x180002ef2  lea     rdx, Src
0x180002ef9  mov     rax, [rax+0D8h]
0x180002f00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f05  mov     esi, eax
0x180002f07  test    eax, eax
0x180002f09  jns     loc_1800033EE
0x180002f0f  test    esi, esi
0x180002f11  js      loc_180003428
0x180002f17  mov     [rbp+arg_0], r12w
0x180002f1c  mov     rax, [rbx]
0x180002f1f  lea     rdx, [rbp+arg_0]
0x180002f23  mov     rcx, rbx
0x180002f26  mov     rax, [rax+88h]
0x180002f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f32  mov     esi, eax
0x180002f34  test    eax, eax
0x180002f36  js      loc_18000332D
0x180002f3c  cmp     [rbp+arg_0], r12w
0x180002f41  setnz   al
0x180002f44  lea     r15, aFalse; "false"
0x180002f4b  lea     rsi, aTrue; "true"
0x180002f52  mov     r8, rsi
0x180002f55  test    al, al
0x180002f57  cmovz   r8, r15
0x180002f5b  mov     edx, 4Ah ; 'J'
0x180002f60  mov     rcx, rdi
0x180002f63  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180002f68  mov     r14d, eax
0x180002f6b  test    eax, eax
0x180002f6d  js      loc_1800038FB
0x180002f73  mov     rax, [rbx]
0x180002f76  lea     rdx, [rbp+arg_0]
0x180002f7a  mov     rcx, rbx
0x180002f7d  mov     rax, [rax+78h]
0x180002f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f86  mov     r14d, eax
0x180002f89  test    eax, eax
0x180002f8b  js      loc_1800038FB
0x180002f91  cmp     [rbp+arg_0], r12w
0x180002f96  setnz   al
0x180002f99  mov     r8, rsi
0x180002f9c  test    al, al
0x180002f9e  cmovz   r8, r15
0x180002fa2  mov     edx, 4Bh ; 'K'
0x180002fa7  mov     rcx, rdi
0x180002faa  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180002faf  mov     r14d, eax
0x180002fb2  test    eax, eax
0x180002fb4  js      loc_1800038FB
0x180002fba  mov     rax, [rbx]
0x180002fbd  lea     rdx, [rbp+arg_0]
0x180002fc1  mov     rcx, rbx
0x180002fc4  mov     rax, [rax+98h]
0x180002fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fd0  mov     r14d, eax
0x180002fd3  test    eax, eax
0x180002fd5  js      loc_1800038FB
0x180002fdb  cmp     [rbp+arg_0], r12w
0x180002fe0  setnz   al
0x180002fe3  mov     r8, rsi
0x180002fe6  test    al, al
0x180002fe8  cmovz   r8, r15
0x180002fec  mov     edx, 4Ch ; 'L'
0x180002ff1  mov     rcx, rdi
0x180002ff4  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180002ff9  mov     r14d, eax
0x180002ffc  test    eax, eax
0x180002ffe  js      loc_1800038FB
0x180003004  mov     rax, [rbx]
0x180003007  lea     rdx, [rbp+arg_0]
0x18000300b  mov     rcx, rbx
0x18000300e  mov     rax, [rax+0A8h]
0x180003015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000301a  mov     r14d, eax
0x18000301d  test    eax, eax
0x18000301f  js      loc_1800038FB
0x180003025  cmp     [rbp+arg_0], r12w
0x18000302a  setnz   al
0x18000302d  mov     r8, rsi
0x180003030  test    al, al
0x180003032  cmovz   r8, r15
0x180003036  mov     edx, 4Dh ; 'M'
0x18000303b  mov     rcx, rdi
0x18000303e  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180003043  mov     r14d, eax
0x180003046  test    eax, eax
0x180003048  js      loc_1800038FB
0x18000304e  mov     rax, [rbx]
0x180003051  lea     rdx, [rbp+arg_0]
0x180003055  mov     rcx, rbx
0x180003058  mov     rax, [rax+0C8h]
0x18000305f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003064  mov     r14d, eax
0x180003067  test    eax, eax
0x180003069  js      loc_1800038FB
0x18000306f  cmp     [rbp+arg_0], r12w
0x180003074  setnz   al
0x180003077  mov     r8, rsi
0x18000307a  test    al, al
0x18000307c  cmovz   r8, r15
0x180003080  mov     edx, 4Eh ; 'N'
0x180003085  mov     rcx, rdi
0x180003088  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x18000308d  mov     r14d, eax
0x180003090  test    eax, eax
0x180003092  js      loc_1800038FB
0x180003098  cmp     [rbp+arg_0], r12w
0x18000309d  jnz     loc_18000344F
0x1800030a3  mov     [rbp+var_18], rbx
0x1800030a7  mov     rax, [rbx]
0x1800030aa  mov     rcx, rbx
0x1800030ad  mov     rax, [rax+8]
0x1800030b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030b6  nop
0x1800030b7  lea     rdx, [rbp+var_18]
0x1800030bb  mov     rcx, rdi
0x1800030be  call    ?WriteIdleSettings@@YAJAEAVTaskXmlWriter@@VJobSettingsPtr@@@Z; WriteIdleSettings(TaskXmlWriter &,JobSettingsPtr)
0x1800030c3  mov     r14d, eax
0x1800030c6  test    eax, eax
0x1800030c8  js      loc_1800038FB
0x1800030ce  mov     rax, [rbx]
0x1800030d1  lea     rdx, [rbp+arg_0]
0x1800030d5  mov     rcx, rbx
0x1800030d8  mov     rax, [rax+38h]
0x1800030dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030e1  mov     r14d, eax
0x1800030e4  test    eax, eax
0x1800030e6  js      loc_1800038FB
0x1800030ec  cmp     [rbp+arg_0], 0
0x1800030f1  setnz   al
0x1800030f4  mov     r8, rsi
0x1800030f7  test    al, al
0x1800030f9  cmovz   r8, r15
0x1800030fd  mov     edx, 48h ; 'H'
0x180003102  mov     rcx, rdi
0x180003105  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x18000310a  mov     r14d, eax
0x18000310d  test    eax, eax
0x18000310f  js      loc_1800038FB
0x180003115  mov     rax, [rbx]
0x180003118  lea     rdx, [rbp+arg_0]
0x18000311c  mov     rcx, rbx
0x18000311f  mov     rax, [rax+0E8h]
0x180003126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000312b  mov     r14d, eax
0x18000312e  test    eax, eax
0x180003130  js      loc_1800038FB
0x180003136  cmp     [rbp+arg_0], 0
0x18000313b  setnz   al
0x18000313e  mov     r8, rsi
0x180003141  test    al, al
0x180003143  cmovz   r8, r15
0x180003147  mov     edx, 13h
0x18000314c  mov     rcx, rdi
0x18000314f  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180003154  mov     r14d, eax
0x180003157  test    eax, eax
0x180003159  js      loc_1800038FB
0x18000315f  mov     rax, [rbx]
0x180003162  lea     rdx, [rbp+arg_0]
0x180003166  mov     rcx, rbx
0x180003169  mov     rax, [rax+128h]
0x180003170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003175  mov     r14d, eax
0x180003178  test    eax, eax
0x18000317a  js      loc_1800038FB
0x180003180  cmp     [rbp+arg_0], 0
0x180003185  setnz   al
0x180003188  mov     r8, rsi
0x18000318b  test    al, al
0x18000318d  cmovz   r8, r15
0x180003191  mov     edx, 51h ; 'Q'
0x180003196  mov     rcx, rdi
0x180003199  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x18000319e  mov     r14d, eax
0x1800031a1  test    eax, eax
0x1800031a3  js      loc_1800038FB
0x1800031a9  mov     rax, [rbx]
0x1800031ac  lea     rdx, [rbp+arg_0]
0x1800031b0  mov     rcx, rbx
0x1800031b3  mov     rax, [rax+148h]
0x1800031ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031bf  mov     r14d, eax
0x1800031c2  test    eax, eax
0x1800031c4  js      loc_1800038FB
0x1800031ca  cmp     [rbp+arg_0], 0
0x1800031cf  setnz   al
0x1800031d2  mov     r8, rsi
0x1800031d5  test    al, al
0x1800031d7  cmovz   r8, r15
0x1800031db  mov     edx, 54h ; 'T'
0x1800031e0  mov     rcx, rdi
0x1800031e3  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x1800031e8  mov     r14d, eax
0x1800031eb  test    eax, eax
0x1800031ed  js      loc_1800038FB
0x1800031f3  mov     [rbp+arg_10], r12d
0x1800031f7  mov     rax, [rbx]
0x1800031fa  lea     rdx, [rbp+arg_10]
0x1800031fe  mov     rcx, rbx
0x180003201  mov     rax, [rax+118h]
0x180003208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000320d  mov     r14d, eax
0x180003210  test    eax, eax
0x180003212  js      loc_1800038FB
0x180003218  mov     eax, [rbp+arg_10]
0x18000321b  cmp     eax, 3
0x18000321e  jge     loc_18000347F
0x180003224  cmp     eax, 4
0x180003227  jge     loc_1800035D4
0x18000322d  mov     rax, [rbx]
0x180003230  lea     rdx, [rbp+arg_0]
0x180003234  mov     rcx, rbx
0x180003237  mov     rax, [rax+158h]
0x18000323e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003243  mov     r14d, eax
0x180003246  test    eax, eax
0x180003248  js      loc_1800038FB
0x18000324e  cmp     [rbp+arg_0], 0
0x180003253  setnz   al
0x180003256  test    al, al
0x180003258  cmovz   rsi, r15
  ... truncated ...
```
