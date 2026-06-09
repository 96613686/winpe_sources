# TaskDefinitionImpl::WriteJobSettingsXml(TaskXmlWriter &)

- ea: `0x180002c10`
- end: `0x180003838`
- name: `?WriteJobSettingsXml@TaskDefinitionImpl@@AEAAJAEAVTaskXmlWriter@@@Z`
- size: `3112`
- prototype: `int(TaskDefinitionImpl *__hidden this, struct TaskXmlWriter *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180004fd0`

## callees

- `0x1800017f0`
- `0x180001b00`
- `0x180001cb8`
- `0x18000247c`
- `0x180002c10`
- `0x180003840`
- `0x1800039f0`
- `0x180003c90`
- `0x180003d1c`
- `0x1800136e0`
- `0x1800157e4`
- `0x180038404`
- `0x180039e34`
- `0x180054010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180003180`
- `OLEAUT32!__imp_SysFreeString` at `0x180003213`
- `OLEAUT32!__imp_SysFreeString` at `0x18000340a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800034dd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000361c`
- `OLEAUT32!__imp_SysFreeString` at `0x180003798`
- `OLEAUT32!__imp_SysFreeString` at `0x1800037d2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800037ed`
- `OLEAUT32!__imp_SysFreeString` at `0x180003180`
- `OLEAUT32!__imp_SysFreeString` at `0x180003213`
- `OLEAUT32!__imp_SysFreeString` at `0x18000340a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800034dd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000361c`
- `OLEAUT32!__imp_SysFreeString` at `0x180003798`
- `OLEAUT32!__imp_SysFreeString` at `0x1800037d2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800037ed`
- `OLEAUT32!__imp_SysStringLen` at `0x1800033dd`
- `OLEAUT32!__imp_SysStringLen` at `0x180003499`
- `OLEAUT32!__imp_SysStringLen` at `0x18000376b`
- `OLEAUT32!__imp_SysStringLen` at `0x1800033dd`
- `OLEAUT32!__imp_SysStringLen` at `0x180003499`
- `OLEAUT32!__imp_SysStringLen` at `0x18000376b`

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
          v47 = 8LL * (unsigned __int16)v6 + 368464;
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
      v7 = (const struct SchemaEntry * near *)&qword_18006EE10;
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
            v49 = 8LL * (unsigned __int16)v13 + 368464;
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
        v14 = (const struct SchemaEntry * near *)&qword_18006EE10;
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
0x180002c10  push    rbp
0x180002c12  push    rbx
0x180002c13  push    rsi
0x180002c14  push    rdi
0x180002c15  push    r12
0x180002c17  push    r14
0x180002c19  push    r15
0x180002c1b  mov     rbp, rsp
0x180002c1e  sub     rsp, 50h
0x180002c22  mov     rdi, rdx
0x180002c25  mov     rsi, rcx
0x180002c28  mov     rbx, [rcx+50h]
0x180002c2c  mov     [rbp+var_10], rbx
0x180002c30  test    rbx, rbx
0x180002c33  jz      short loc_180002C45
0x180002c35  mov     rax, [rbx]
0x180002c38  mov     rcx, rbx
0x180002c3b  mov     rax, [rax+8]
0x180002c3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c44  nop
0x180002c45  cmp     qword ptr [rsi+50h], 0
0x180002c4a  jz      loc_18000321A
0x180002c50  mov     eax, [rdi+98h]
0x180002c56  lea     r14, __ImageBase
0x180002c5d  xor     r12d, r12d
0x180002c60  test    eax, eax
0x180002c62  jnz     loc_1800036B0
0x180002c68  mov     r8d, [rdi]
0x180002c6b  cmp     r8d, 10006h
0x180002c72  jnz     loc_180003530
0x180002c78  movzx   eax, r8w; jumptable 000000018000354D cases 65538-65541
0x180002c7c  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r14+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180002c84  add     r8, 2380h
0x180002c8b  mov     eax, [r8]
0x180002c8e  test    eax, eax
0x180002c90  jz      loc_18000365C
0x180002c96  mov     rcx, [rdi+10h]
0x180002c9a  test    rcx, rcx
0x180002c9d  jz      loc_1800036BD
0x180002ca3  mov     rax, [rcx]
0x180002ca6  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x180002cad  mov     r8, [r8+8]
0x180002cb1  lea     rdx, Src
0x180002cb8  mov     rax, [rax+0D8h]
0x180002cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cc4  mov     esi, eax
0x180002cc6  test    eax, eax
0x180002cc8  js      loc_180003678
0x180002cce  mov     [rbp+arg_18], r12d
0x180002cd2  mov     rax, [rbx]
0x180002cd5  lea     rdx, [rbp+arg_18]
0x180002cd9  mov     rcx, rbx
0x180002cdc  mov     rax, [rax+68h]
0x180002ce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ce5  mov     esi, eax
0x180002ce7  test    eax, eax
0x180002ce9  js      loc_180003187
0x180002cef  mov     ecx, [rbp+arg_18]
0x180002cf2  cmp     ecx, 1
0x180002cf5  jnz     loc_1800035E3
0x180002cfb  mov     eax, [rdi+98h]
0x180002d01  test    eax, eax
0x180002d03  jnz     loc_180003701
0x180002d09  mov     r8d, [rdi]
0x180002d0c  cmp     r8d, 10006h
0x180002d13  jnz     loc_180003589
0x180002d19  movzx   eax, r8w; jumptable 00000001800035A6 cases 65538-65541
0x180002d1d  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r14+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180002d25  add     r8, 2480h
0x180002d2c  mov     eax, [r8]
0x180002d2f  test    eax, eax
0x180002d31  jz      loc_1800033A3
0x180002d37  mov     rcx, [rdi+10h]
0x180002d3b  test    rcx, rcx
0x180002d3e  jz      loc_18000370E
0x180002d44  mov     rax, [rcx]
0x180002d47  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x180002d4e  mov     r8, [r8+8]
0x180002d52  lea     rdx, Src
0x180002d59  mov     rax, [rax+0D8h]
0x180002d60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d65  mov     esi, eax
0x180002d67  test    eax, eax
0x180002d69  jns     loc_180003240
0x180002d6f  test    esi, esi
0x180002d71  js      loc_18000327A
0x180002d77  mov     [rbp+arg_0], r12w
0x180002d7c  mov     rax, [rbx]
0x180002d7f  lea     rdx, [rbp+arg_0]
0x180002d83  mov     rcx, rbx
0x180002d86  mov     rax, [rax+88h]
0x180002d8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d92  mov     esi, eax
0x180002d94  test    eax, eax
0x180002d96  js      loc_180003187
0x180002d9c  cmp     [rbp+arg_0], r12w
0x180002da1  setnz   al
0x180002da4  lea     r15, aFalse; "false"
0x180002dab  lea     rsi, aTrue; "true"
0x180002db2  mov     r8, rsi
0x180002db5  test    al, al
0x180002db7  cmovz   r8, r15
0x180002dbb  mov     edx, 4Ah ; 'J'
0x180002dc0  mov     rcx, rdi
0x180002dc3  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180002dc8  mov     r14d, eax
0x180002dcb  test    eax, eax
0x180002dcd  js      loc_180003723
0x180002dd3  mov     rax, [rbx]
0x180002dd6  lea     rdx, [rbp+arg_0]
0x180002dda  mov     rcx, rbx
0x180002ddd  mov     rax, [rax+78h]
0x180002de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002de6  mov     r14d, eax
0x180002de9  test    eax, eax
0x180002deb  js      loc_180003723
0x180002df1  cmp     [rbp+arg_0], r12w
0x180002df6  setnz   al
0x180002df9  mov     r8, rsi
0x180002dfc  test    al, al
0x180002dfe  cmovz   r8, r15
0x180002e02  mov     edx, 4Bh ; 'K'
0x180002e07  mov     rcx, rdi
0x180002e0a  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180002e0f  mov     r14d, eax
0x180002e12  test    eax, eax
0x180002e14  js      loc_180003723
0x180002e1a  mov     rax, [rbx]
0x180002e1d  lea     rdx, [rbp+arg_0]
0x180002e21  mov     rcx, rbx
0x180002e24  mov     rax, [rax+98h]
0x180002e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e30  mov     r14d, eax
0x180002e33  test    eax, eax
0x180002e35  js      loc_180003723
0x180002e3b  cmp     [rbp+arg_0], r12w
0x180002e40  setnz   al
0x180002e43  mov     r8, rsi
0x180002e46  test    al, al
0x180002e48  cmovz   r8, r15
0x180002e4c  mov     edx, 4Ch ; 'L'
0x180002e51  mov     rcx, rdi
0x180002e54  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180002e59  mov     r14d, eax
0x180002e5c  test    eax, eax
0x180002e5e  js      loc_180003723
0x180002e64  mov     rax, [rbx]
0x180002e67  lea     rdx, [rbp+arg_0]
0x180002e6b  mov     rcx, rbx
0x180002e6e  mov     rax, [rax+0A8h]
0x180002e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e7a  mov     r14d, eax
0x180002e7d  test    eax, eax
0x180002e7f  js      loc_180003723
0x180002e85  cmp     [rbp+arg_0], r12w
0x180002e8a  setnz   al
0x180002e8d  mov     r8, rsi
0x180002e90  test    al, al
0x180002e92  cmovz   r8, r15
0x180002e96  mov     edx, 4Dh ; 'M'
0x180002e9b  mov     rcx, rdi
0x180002e9e  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180002ea3  mov     r14d, eax
0x180002ea6  test    eax, eax
0x180002ea8  js      loc_180003723
0x180002eae  mov     rax, [rbx]
0x180002eb1  lea     rdx, [rbp+arg_0]
0x180002eb5  mov     rcx, rbx
0x180002eb8  mov     rax, [rax+0C8h]
0x180002ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ec4  mov     r14d, eax
0x180002ec7  test    eax, eax
0x180002ec9  js      loc_180003723
0x180002ecf  cmp     [rbp+arg_0], r12w
0x180002ed4  setnz   al
0x180002ed7  mov     r8, rsi
0x180002eda  test    al, al
0x180002edc  cmovz   r8, r15
0x180002ee0  mov     edx, 4Eh ; 'N'
0x180002ee5  mov     rcx, rdi
0x180002ee8  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180002eed  mov     r14d, eax
0x180002ef0  test    eax, eax
0x180002ef2  js      loc_180003723
0x180002ef8  cmp     [rbp+arg_0], r12w
0x180002efd  jnz     loc_1800032A0
0x180002f03  mov     [rbp+var_18], rbx
0x180002f07  mov     rax, [rbx]
0x180002f0a  mov     rcx, rbx
0x180002f0d  mov     rax, [rax+8]
0x180002f11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f16  nop
0x180002f17  lea     rdx, [rbp+var_18]
0x180002f1b  mov     rcx, rdi
0x180002f1e  call    ?WriteIdleSettings@@YAJAEAVTaskXmlWriter@@VJobSettingsPtr@@@Z; WriteIdleSettings(TaskXmlWriter &,JobSettingsPtr)
0x180002f23  mov     r14d, eax
0x180002f26  test    eax, eax
0x180002f28  js      loc_180003723
0x180002f2e  mov     rax, [rbx]
0x180002f31  lea     rdx, [rbp+arg_0]
0x180002f35  mov     rcx, rbx
0x180002f38  mov     rax, [rax+38h]
0x180002f3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f41  mov     r14d, eax
0x180002f44  test    eax, eax
0x180002f46  js      loc_180003723
0x180002f4c  cmp     [rbp+arg_0], 0
0x180002f51  setnz   al
0x180002f54  mov     r8, rsi
0x180002f57  test    al, al
0x180002f59  cmovz   r8, r15
0x180002f5d  mov     edx, 48h ; 'H'
0x180002f62  mov     rcx, rdi
0x180002f65  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180002f6a  mov     r14d, eax
0x180002f6d  test    eax, eax
0x180002f6f  js      loc_180003723
0x180002f75  mov     rax, [rbx]
0x180002f78  lea     rdx, [rbp+arg_0]
0x180002f7c  mov     rcx, rbx
0x180002f7f  mov     rax, [rax+0E8h]
0x180002f86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f8b  mov     r14d, eax
0x180002f8e  test    eax, eax
0x180002f90  js      loc_180003723
0x180002f96  cmp     [rbp+arg_0], 0
0x180002f9b  setnz   al
0x180002f9e  mov     r8, rsi
0x180002fa1  test    al, al
0x180002fa3  cmovz   r8, r15
0x180002fa7  mov     edx, 13h
0x180002fac  mov     rcx, rdi
0x180002faf  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180002fb4  mov     r14d, eax
0x180002fb7  test    eax, eax
0x180002fb9  js      loc_180003723
0x180002fbf  mov     rax, [rbx]
0x180002fc2  lea     rdx, [rbp+arg_0]
0x180002fc6  mov     rcx, rbx
0x180002fc9  mov     rax, [rax+128h]
0x180002fd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fd5  mov     r14d, eax
0x180002fd8  test    eax, eax
0x180002fda  js      loc_180003723
0x180002fe0  cmp     [rbp+arg_0], 0
0x180002fe5  setnz   al
0x180002fe8  mov     r8, rsi
0x180002feb  test    al, al
0x180002fed  cmovz   r8, r15
0x180002ff1  mov     edx, 51h ; 'Q'
0x180002ff6  mov     rcx, rdi
0x180002ff9  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180002ffe  mov     r14d, eax
0x180003001  test    eax, eax
0x180003003  js      loc_180003723
0x180003009  mov     rax, [rbx]
0x18000300c  lea     rdx, [rbp+arg_0]
0x180003010  mov     rcx, rbx
0x180003013  mov     rax, [rax+148h]
0x18000301a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000301f  mov     r14d, eax
0x180003022  test    eax, eax
0x180003024  js      loc_180003723
0x18000302a  cmp     [rbp+arg_0], 0
0x18000302f  setnz   al
0x180003032  mov     r8, rsi
0x180003035  test    al, al
0x180003037  cmovz   r8, r15
0x18000303b  mov     edx, 54h ; 'T'
0x180003040  mov     rcx, rdi
0x180003043  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180003048  mov     r14d, eax
0x18000304b  test    eax, eax
0x18000304d  js      loc_180003723
0x180003053  mov     [rbp+arg_10], r12d
0x180003057  mov     rax, [rbx]
0x18000305a  lea     rdx, [rbp+arg_10]
0x18000305e  mov     rcx, rbx
0x180003061  mov     rax, [rax+118h]
0x180003068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000306d  mov     r14d, eax
0x180003070  test    eax, eax
0x180003072  js      loc_180003723
0x180003078  mov     eax, [rbp+arg_10]
0x18000307b  cmp     eax, 3
0x18000307e  jge     loc_1800032D0
0x180003084  cmp     eax, 4
0x180003087  jge     loc_180003419
0x18000308d  mov     rax, [rbx]
0x180003090  lea     rdx, [rbp+arg_0]
0x180003094  mov     rcx, rbx
0x180003097  mov     rax, [rax+158h]
0x18000309e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030a3  mov     r14d, eax
0x1800030a6  test    eax, eax
0x1800030a8  js      loc_180003723
0x1800030ae  cmp     [rbp+arg_0], 0
0x1800030b3  setnz   al
0x1800030b6  test    al, al
0x1800030b8  cmovz   rsi, r15
  ... truncated ...
```
