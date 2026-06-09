# UniSession::GenerateXmlLegacy(ITask *,ATL::CComBSTR &)

- ea: `0x180048cb0`
- end: `0x180049aa8`
- name: `?GenerateXmlLegacy@UniSession@@CAJPEAUITask@@AEAVCComBSTR@ATL@@@Z`
- size: `3576`
- prototype: `static int(struct ITask *, struct ATL::CComBSTR *)`
- caller_count: `3`
- callee_count: `28`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180005e20`
- `0x18001e890`
- `0x18001fda0`

## callees

- `0x1800017f0`
- `0x18000247c`
- `0x180003840`
- `0x180003c90`
- `0x180003d1c`
- `0x180004c00`
- `0x1800055f8`
- `0x180007aa0`
- `0x180009a78`
- `0x1800136e0`
- `0x180013820`
- `0x18002cc10`
- `0x180030b54`
- `0x1800333d4`
- `0x180033e58`
- `0x1800366f8`
- `0x180039500`
- `0x180039e34`
- `0x18003b51c`
- `0x180048928`
- `0x180048cb0`
- `0x18004afd0`
- `0x18004b058`
- `0x18004b430`
- `0x18004b494`
- `0x18004b4f8`
- `0x18004e950`
- `0x180054010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18004997d`
- `msvcrt!_wcsicmp` at `0x18004997d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048e10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048e49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048ea4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049705`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049737`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049813`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800498dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049935`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800499fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049a0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049a1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049a42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049a53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049a64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048e10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048e49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048ea4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049705`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049737`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049813`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800498dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049935`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800499fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049a0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049a1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049a42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049a53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049a64`

## string_xrefs

- `0x1800497d1`: `InteractiveToken`
- `0x180049875`: `InteractiveTokenOrPassword`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall UniSession::GenerateXmlLegacy(struct ITask *a1, struct ATL::CComBSTR *a2)
{
  CBstrWriter *v4; // rax
  CBstrWriter *v5; // rbx
  int started; // ebx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  unsigned __int16 i; // di
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r8
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  __int64 v19; // r8
  __int64 v20; // r8
  __int64 v21; // r8
  __int64 v22; // r8
  __int64 v23; // r8
  __int64 v24; // r8
  __int64 v25; // r8
  __int64 v26; // r8
  __int64 v27; // r8
  unsigned __int64 v28; // rdi
  void *v29; // rcx
  unsigned __int16 *v30; // rbx
  unsigned __int16 *v31; // r15
  unsigned __int16 j; // r14
  int v33; // r14d
  int v34; // eax
  __int64 v35; // rdx
  const wchar_t *v36; // r8
  wchar_t *v37; // r8
  unsigned __int64 v38; // rcx
  CBstrWriter *v39; // rax
  unsigned __int16 *Copy; // rax
  CBstrWriter *v41; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v43[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v44; // [rsp+54h] [rbp-ACh] BYREF
  LPVOID v45; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v46; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v47; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *String2; // [rsp+70h] [rbp-90h] BYREF
  CBstrWriter *v49; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v50[160]; // [rsp+80h] [rbp-80h] BYREF
  __int128 pExceptionObject; // [rsp+120h] [rbp+20h] BYREF
  __int128 v52; // [rsp+130h] [rbp+30h]
  unsigned int v53[4]; // [rsp+140h] [rbp+40h]
  int v54; // [rsp+150h] [rbp+50h]

  v4 = (CBstrWriter *)operator new(0x28u);
  v49 = v4;
  if ( v4 )
    v5 = CBstrWriter::CBstrWriter(v4);
  else
    v5 = 0;
  v41 = v5;
  if ( !v5 )
  {
    BYTE8(pExceptionObject) = 0;
    *(_QWORD *)&v52 = &qword_180077320;
    *((_QWORD *)&v52 + 1) = 0;
    *(_QWORD *)v53 = 0;
    v53[2] = 14;
    v53[3] = -1;
    v54 = -1;
    *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  (*(void (__fastcall **)(CBstrWriter *))(*(_QWORD *)v5 + 8LL))(v5);
  LODWORD(pv) = 65537;
  _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::_com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>(
    &v49,
    &v41);
  TaskXmlWriter::TaskXmlWriter(v50, &v49, &pv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v49);
  started = TaskXmlWriter::StartDocument(v50, 65537);
  if ( started < 0 )
    goto LABEL_8;
  started = TaskXmlWriter::StartElement(v50, 3);
  if ( started < 0 )
    goto LABEL_8;
  pv = 0;
  started = ((__int64 (__fastcall *)(struct ITask *, LPVOID *))a1->lpVtbl->GetCreator)(a1, &pv);
  if ( started < 0 )
    goto LABEL_11;
  v9 = pv;
  if ( pv && *(_WORD *)pv )
  {
    started = TaskXmlWriter::Element(v50, 8, pv);
    if ( started < 0 )
      goto LABEL_11;
    v9 = pv;
  }
  if ( v9 )
    CoTaskMemFree(v9);
  pv = 0;
  started = ((__int64 (__fastcall *)(struct ITask *, LPVOID *))a1->lpVtbl->GetComment)(a1, &pv);
  if ( started < 0 )
    goto LABEL_11;
  v10 = pv;
  if ( pv && *(_WORD *)pv )
  {
    started = TaskXmlWriter::Element(v50, 10, pv);
    if ( started < 0 )
      goto LABEL_11;
    v10 = pv;
  }
  if ( v10 )
    CoTaskMemFree(v10);
  started = TaskXmlWriter::EndElement(v50);
  if ( started < 0 )
    goto LABEL_8;
  started = TaskXmlWriter::StartElement(v50, 12);
  if ( started < 0 )
    goto LABEL_8;
  v46 = 0;
  started = ((__int64 (__fastcall *)(struct ITask *, unsigned __int16 *))a1->lpVtbl->GetTriggerCount)(a1, &v46);
  if ( started < 0 )
    goto LABEL_8;
  for ( i = 0; i < v46; ++i )
  {
    pExceptionObject = 0;
    v52 = 0;
    *(_OWORD *)v53 = 0;
    pv = 0;
    started = ((__int64 (__fastcall *)(struct ITask *, _QWORD, LPVOID *))a1->lpVtbl->GetTrigger)(a1, i, &pv);
    if ( started < 0
      || (started = (*(__int64 (__fastcall **)(LPVOID, __int128 *))(*(_QWORD *)pv + 32LL))(pv, &pExceptionObject),
          started < 0) )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&pv);
      goto LABEL_8;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&pv);
    if ( v53[0] )
    {
      switch ( v53[0] )
      {
        case 1u:
        case 2u:
        case 3u:
        case 4u:
          v12 = 39;
          break;
        case 5u:
          v12 = 24;
          break;
        case 6u:
          v12 = 21;
          break;
        case 7u:
          v12 = 35;
          break;
        default:
          goto LABEL_49;
      }
    }
    else
    {
      v12 = 25;
    }
    started = TaskXmlWriter::StartElement(v50, v12);
    if ( started < 0 )
      goto LABEL_8;
LABEL_49:
    v13 = HIDWORD(v52) >> 2;
    LOBYTE(v13) = (BYTE12(v52) & 4) == 0;
    started = TaskXmlWriter::ElementBool(v50, 19, v13);
    if ( started < 0 )
      goto LABEL_8;
    if ( DWORD2(v52) )
    {
      started = TaskXmlWriter::StartElement(v50, 13);
      if ( started < 0 )
        goto LABEL_8;
      started = TaskXmlWriter::ElementDuration(v50, 14);
      if ( started < 0 )
        goto LABEL_8;
      started = TaskXmlWriter::ElementDuration(v50, 15);
      if ( started < 0 )
        goto LABEL_8;
      v14 = HIDWORD(v52) >> 1;
      LOBYTE(v14) = (BYTE12(v52) & 2) != 0;
      started = TaskXmlWriter::ElementBool(v50, 16, v14);
      if ( started < 0 )
        goto LABEL_8;
      v15 = TaskXmlWriter::EndElement(v50);
    }
    else
    {
      if ( !DWORD1(v52) || (BYTE12(v52) & 2) == 0 )
        goto LABEL_60;
      v15 = TaskXmlWriter::ElementDuration(v50, 20);
    }
    started = v15;
    if ( v15 < 0 )
      goto LABEL_8;
LABEL_60:
    if ( (BYTE12(v52) & 1) != 0 )
    {
      started = TaskXmlWriter::ElementDateTime(
                  v50,
                  18,
                  WORD5(pExceptionObject),
                  WORD6(pExceptionObject),
                  HIWORD(pExceptionObject),
                  23,
                  59,
                  59,
                  v41);
      if ( started < 0 )
        goto LABEL_8;
    }
    if ( v53[0] )
    {
      if ( v53[0] != 1 && v53[0] != 2 && v53[0] != 3 && v53[0] != 4 )
      {
        if ( v53[0] != 5 && v53[0] - 6 > 1 )
          continue;
        goto LABEL_91;
      }
      started = TaskXmlWriter::ElementDateTime(
                  v50,
                  17,
                  WORD2(pExceptionObject),
                  WORD3(pExceptionObject),
                  WORD4(pExceptionObject),
                  (unsigned __int16)v52,
                  WORD1(v52),
                  0,
                  v41);
      if ( started < 0 )
        goto LABEL_8;
      if ( v53[0] == 1 )
      {
        started = TaskXmlWriter::StartElement(v50, 40);
        if ( started < 0 )
          goto LABEL_8;
        v17 = TaskXmlWriter::ElementInt(v50, 41, LOWORD(v53[1]));
      }
      else if ( v53[0] == 2 )
      {
        started = TaskXmlWriter::StartElement(v50, 42);
        if ( started < 0 )
          goto LABEL_8;
        started = TaskXmlWriter::ElementInt(v50, 43, LOWORD(v53[1]));
        if ( started < 0 )
          goto LABEL_8;
        v17 = TaskXmlWriter::SectionDaysOfWeek((TaskXmlWriter *)v50, HIWORD(v53[1]));
      }
      else
      {
        if ( v53[0] == 3 )
        {
          started = TaskXmlWriter::StartElement(v50, 52);
          if ( started < 0 )
            goto LABEL_8;
          v16 = TaskXmlWriter::SectionDaysOfMonth((TaskXmlWriter *)v50, v53[1]);
        }
        else
        {
          if ( v53[0] != 4 )
            goto LABEL_91;
          started = TaskXmlWriter::StartElement(v50, 54);
          if ( started < 0 )
            goto LABEL_8;
          started = TaskXmlWriter::SectionWeeks((TaskXmlWriter *)v50, 1 << (LOBYTE(v53[1]) - 1));
          if ( started < 0 )
            goto LABEL_8;
          v16 = TaskXmlWriter::SectionDaysOfWeek((TaskXmlWriter *)v50, HIWORD(v53[1]));
        }
        started = v16;
        if ( v16 < 0 )
          goto LABEL_8;
        v17 = TaskXmlWriter::SectionMonths((TaskXmlWriter *)v50, LOWORD(v53[2]));
      }
      started = v17;
      if ( v17 < 0 )
        goto LABEL_8;
      v18 = TaskXmlWriter::EndElement(v50);
    }
    else
    {
      v18 = TaskXmlWriter::ElementDateTime(
              v50,
              17,
              WORD2(pExceptionObject),
              WORD3(pExceptionObject),
              WORD4(pExceptionObject),
              (unsigned __int16)v52,
              WORD1(v52),
              0,
              v41);
    }
    started = v18;
    if ( v18 < 0 )
      goto LABEL_8;
LABEL_91:
    started = TaskXmlWriter::EndElement(v50);
    if ( started < 0 )
      goto LABEL_8;
  }
  started = TaskXmlWriter::EndElement(v50);
  if ( started < 0 )
    goto LABEL_8;
  v44 = 0;
  started = ((__int64 (__fastcall *)(struct ITask *, unsigned int *))a1->lpVtbl->GetFlags)(a1, &v44);
  if ( started < 0 )
    goto LABEL_8;
  started = TaskXmlWriter::StartElement(v50, 71);
  if ( started < 0 )
    goto LABEL_8;
  v19 = v44 >> 2;
  LOBYTE(v19) = (v44 & 4) == 0;
  started = TaskXmlWriter::ElementBool(v50, 19, v19);
  if ( started < 0 )
    goto LABEL_8;
  if ( (v44 & 2) != 0 )
  {
    started = TaskXmlWriter::ElementDuration(v50, 82);
    if ( started < 0 )
      goto LABEL_8;
  }
  LODWORD(pv) = 0;
  started = ((__int64 (__fastcall *)(struct ITask *, LPVOID *))a1->lpVtbl->GetMaxRunTime)(a1, &pv);
  if ( started < 0 )
    goto LABEL_8;
  if ( (unsigned int)((_DWORD)pv - 1) <= 0xFFFFFFFD )
  {
    started = TaskXmlWriter::ElementDuration(v50, 20);
    if ( started < 0 )
      goto LABEL_8;
  }
  v20 = v44 >> 9;
  LOBYTE(v20) = (v44 & 0x200) != 0;
  started = TaskXmlWriter::ElementBool(v50, 81, v20);
  if ( started < 0 )
    goto LABEL_8;
  v21 = v44 >> 12;
  LOBYTE(v21) = (v44 & 0x1000) != 0;
  started = TaskXmlWriter::ElementBool(v50, 79, v21);
  if ( started < 0 )
    goto LABEL_8;
  v22 = v44 >> 6;
  LOBYTE(v22) = (v44 & 0x40) != 0;
  started = TaskXmlWriter::ElementBool(v50, 74, v22);
  if ( started < 0 )
    goto LABEL_8;
  v23 = v44 >> 7;
  LOBYTE(v23) = (v44 & 0x80) != 0;
  started = TaskXmlWriter::ElementBool(v50, 75, v23);
  if ( started < 0 )
    goto LABEL_8;
  v24 = v44 >> 4;
  LOBYTE(v24) = (v44 & 0x10) != 0;
  started = TaskXmlWriter::ElementBool(v50, 84, v24);
  if ( started < 0 )
    goto LABEL_8;
  LODWORD(pv) = 0x4000;
  started = ((__int64 (__fastcall *)(struct ITask *, LPVOID *))a1->lpVtbl->GetPriority)(a1, &pv);
  if ( started < 0 )
    goto LABEL_8;
  v25 = 7;
  switch ( (_DWORD)pv )
  {
    case 0x20:
      v25 = 5;
      break;
    case 0x40:
      v25 = 9;
      break;
    case 0x80:
      v25 = 1;
      break;
    case 0x100:
      v25 = 0;
      break;
    case 0x8000:
      v25 = 3;
      break;
  }
  started = TaskXmlWriter::ElementInt(v50, 83, v25);
  if ( started < 0 )
    goto LABEL_8;
  v43[0] = 0;
  LOWORD(pv) = 0;
  started = ((__int64 (__fastcall *)(struct ITask *, _WORD *, LPVOID *))a1->lpVtbl->GetIdleWait)(a1, v43, &pv);
  if ( started < 0 )
    goto LABEL_8;
  started = TaskXmlWriter::StartElement(v50, 85);
  if ( started < 0 )
    goto LABEL_8;
  started = TaskXmlWriter::ElementDuration(v50, 86);
  if ( started < 0 )
    goto LABEL_8;
  started = TaskXmlWriter::ElementDuration(v50, 87);
  if ( started < 0 )
    goto LABEL_8;
  v26 = v44 >> 5;
  LOBYTE(v26) = (v44 & 0x20) != 0;
  started = TaskXmlWriter::ElementBool(v50, 88, v26);
  if ( started < 0 )
    goto LABEL_8;
  v27 = v44 >> 11;
  LOBYTE(v27) = (v44 & 0x800) != 0;
  started = TaskXmlWriter::ElementBool(v50, 89, v27);
  if ( started < 0 )
    goto LABEL_8;
  started = TaskXmlWriter::EndElement(v50);
  if ( started < 0 )
    goto LABEL_8;
  started = TaskXmlWriter::EndElement(v50);
  if ( started < 0 )
    goto LABEL_8;
  pv = 0;
  v43[0] = 0;
  started = ((__int64 (__fastcall *)(struct ITask *, _WORD *, LPVOID *))a1->lpVtbl->GetWorkItemData)(a1, v43, &pv);
  if ( started < 0 )
    goto LABEL_11;
  v28 = -1;
  v29 = pv;
  if ( v43[0] && pv )
  {
    v30 = (unsigned __int16 *)operator new(saturated_mul(2 * (unsigned int)v43[0] + 1, 2u));
    v49 = (CBstrWriter *)v30;
    v31 = v30;
    for ( j = 0; j < v43[0]; ++j )
    {
      StringCchPrintfW(v31, 3u, L"%02x", *((unsigned __int8 *)pv + j));
      v31 += 2;
    }
    v33 = TaskXmlWriter::Element(v50, 96, v30);
    if ( v33 < 0 )
    {
      operator delete(v30);
      if ( pv )
        CoTaskMemFree(pv);
      TaskXmlWriter::~TaskXmlWriter((TaskXmlWriter *)v50);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
      return (unsigned int)v33;
    }
    operator delete(v30);
    v29 = pv;
  }
  if ( v29 )
    CoTaskMemFree(v29);
  pv = 0;
  v34 = ((__int64 (__fastcall *)(struct ITask *, LPVOID *))a1->lpVtbl->GetAccountInformation)(a1, &pv);
  started = v34;
  if ( v34 != -2147216625 )
  {
    if ( v34 < 0 )
      goto LABEL_11;
    started = TaskXmlWriter::StartElement(v50, 97);
    if ( started < 0 )
      goto LABEL_11;
    started = TaskXmlWriter::StartElement(v50, 98);
    if ( started < 0 )
      goto LABEL_11;
    v35 = 36;
    if ( !*(_WORD *)pv )
    {
      v36 = L"System";
      goto LABEL_149;
    }
    started = TaskXmlWriter::Element(v50, 36, pv);
    if ( started < 0 )
      goto LABEL_11;
    v35 = 100;
    v36 = (v44 & 0x2000) != 0 ? L"InteractiveToken" : L"InteractiveTokenOrPassword";
LABEL_149:
    started = TaskXmlWriter::Element(v50, v35, v36);
    if ( started < 0
      || (started = TaskXmlWriter::EndElement(v50), started < 0)
      || (started = TaskXmlWriter::EndElement(v50), started < 0) )
    {
LABEL_11:
      v8 = pv;
      goto LABEL_12;
    }
  }
  if ( pv )
    CoTaskMemFree(pv);
  started = TaskXmlWriter::StartElement(v50, 102);
  if ( started < 0 )
    goto LABEL_8;
  started = TaskXmlWriter::StartElement(v50, 103);
  if ( started < 0 )
    goto LABEL_8;
  v45 = 0;
  started = ((__int64 (__fastcall *)(struct ITask *, LPVOID *))a1->lpVtbl->GetApplicationName)(a1, &v45);
  if ( started < 0 )
    goto LABEL_157;
  if ( v45 )
  {
    if ( *(_WORD *)v45 )
    {
      started = TaskXmlWriter::Element(v50, 104, v45);
      if ( started < 0 )
        goto LABEL_157;
    }
  }
  v47 = 0;
  started = ((__int64 (__fastcall *)(struct ITask *, LPVOID *))a1->lpVtbl->GetParameters)(a1, &v47);
  if ( started < 0 )
    goto LABEL_164;
  if ( v47 )
  {
    if ( *(_WORD *)v47 )
    {
      started = TaskXmlWriter::Element(v50, 105, v47);
      if ( started < 0 )
        goto LABEL_164;
    }
  }
  String2 = 0;
  started = ((__int64 (__fastcall *)(struct ITask *, wchar_t **))a1->lpVtbl->GetWorkingDirectory)(a1, &String2);
  if ( started < 0 )
  {
LABEL_170:
    if ( String2 )
      CoTaskMemFree(String2);
LABEL_164:
    if ( v47 )
      CoTaskMemFree(v47);
LABEL_157:
    v8 = v45;
LABEL_12:
    if ( v8 )
      CoTaskMemFree(v8);
LABEL_8:
    TaskXmlWriter::~TaskXmlWriter((TaskXmlWriter *)v50);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
    return (unsigned int)started;
  }
  v37 = String2;
  if ( String2 && *String2 && v45 )
  {
    v38 = -1;
    do
      ++v38;
    while ( *((_WORD *)v45 + v38) );
    do
      ++v28;
    while ( String2[v28] );
    if ( v38 < v28 )
      goto LABEL_181;
    if ( _wcsicmp((const wchar_t *)v45 + v38 - v28, String2) )
    {
      v37 = String2;
LABEL_181:
      started = TaskXmlWriter::Element(v50, 106, v37);
      if ( started < 0 )
        goto LABEL_170;
    }
  }
  started = TaskXmlWriter::EndElement(v50);
  if ( started < 0 )
    goto LABEL_170;
  started = TaskXmlWriter::EndElement(v50);
  if ( started < 0 )
    goto LABEL_170;
  started = TaskXmlWriter::EndDocument((TaskXmlWriter *)v50);
  if ( started < 0 )
    goto LABEL_170;
  v39 = (CBstrWriter *)ATL::CComPtrBase<IStream>::operator*(&v41);
  Copy = CBstrWriter::GetCopy(v39);
  if ( !Copy )
  {
    if ( String2 )
      CoTaskMemFree(String2);
    if ( v47 )
      CoTaskMemFree(v47);
    if ( v45 )
      CoTaskMemFree(v45);
    started = -2147024882;
    goto LABEL_8;
  }
  ATL::CComBSTR::Attach(a2, Copy);
  if ( String2 )
    CoTaskMemFree(String2);
  if ( v47 )
    CoTaskMemFree(v47);
  if ( v45 )
    CoTaskMemFree(v45);
  TaskXmlWriter::~TaskXmlWriter((TaskXmlWriter *)v50);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
  return 0;
}

```

## disassembly

```asm
0x180048cb0  mov     [rsp-8+arg_10], rbx
0x180048cb5  push    rbp
0x180048cb6  push    rsi
0x180048cb7  push    rdi
0x180048cb8  push    r12
0x180048cba  push    r13
0x180048cbc  push    r14
0x180048cbe  push    r15
0x180048cc0  lea     rbp, [rsp-60h]
0x180048cc5  sub     rsp, 160h
0x180048ccc  mov     rax, cs:__security_cookie
0x180048cd3  xor     rax, rsp
0x180048cd6  mov     [rbp+90h+var_38], rax
0x180048cda  mov     r12, rdx
0x180048cdd  mov     rsi, rcx
0x180048ce0  mov     ecx, 28h ; '('; unsigned __int64
0x180048ce5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180048cea  mov     [rsp+190h+var_118], rax
0x180048cef  xor     r13d, r13d
0x180048cf2  test    rax, rax
0x180048cf5  jz      short loc_180048D04
0x180048cf7  mov     rcx, rax; this
0x180048cfa  call    ??0CBstrWriter@@QEAA@XZ; CBstrWriter::CBstrWriter(void)
0x180048cff  mov     rbx, rax
0x180048d02  jmp     short loc_180048D07
0x180048d04  mov     rbx, r13
0x180048d07  mov     [rsp+190h+var_150], rbx
0x180048d0c  test    rbx, rbx
0x180048d0f  jz      short loc_180048D21
0x180048d11  mov     rax, [rbx]
0x180048d14  mov     rcx, rbx
0x180048d17  mov     rax, [rax+8]
0x180048d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048d20  nop
0x180048d21  test    rbx, rbx
0x180048d24  jnz     short loc_180048D6E
0x180048d26  mov     byte ptr [rbp+90h+pExceptionObject+8], r13b
0x180048d2a  lea     rax, qword_180077320
0x180048d31  mov     qword ptr [rbp+90h+var_60], rax
0x180048d35  mov     qword ptr [rbp+90h+var_60+8], r13
0x180048d39  mov     qword ptr [rbp+90h+var_50], r13
0x180048d3d  mov     [rbp+90h+var_50+8], 0Eh
0x180048d44  mov     [rbp+90h+var_50+0Ch], 0FFFFFFFFh
0x180048d4b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180048d4f  mov     [rbp+90h+var_40], edi
0x180048d52  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180048d59  mov     qword ptr [rbp+90h+pExceptionObject], rax
0x180048d5d  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180048d64  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x180048d68  call    _CxxThrowException_0
0x180048d6e  mov     ebx, 10001h
0x180048d73  mov     dword ptr [rsp+190h+pv], ebx
0x180048d77  lea     rdx, [rsp+190h+var_150]
0x180048d7c  lea     rcx, [rsp+190h+var_118]
0x180048d81  call    ??$?0V?$CComPtr@UIStream@@@ATL@@@?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@AEBV?$CComPtr@UIStream@@@ATL@@@Z; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::_com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>(ATL::CComPtr<IStream> const &)
0x180048d86  lea     r8, [rsp+190h+pv]
0x180048d8b  lea     rdx, [rsp+190h+var_118]
0x180048d90  lea     rcx, [rbp+90h+var_110]
0x180048d94  call    ??0TaskXmlWriter@@QEAA@AEBV?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEBUSchema@@@Z; TaskXmlWriter::TaskXmlWriter(_com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>> const &,Schema const &)
0x180048d99  nop
0x180048d9a  lea     rcx, [rsp+190h+var_118]
0x180048d9f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180048da4  mov     edx, ebx
0x180048da6  lea     rcx, [rbp+90h+var_110]
0x180048daa  call    ?StartDocument@TaskXmlWriter@@QEAAJW4Version@Schema@@@Z; TaskXmlWriter::StartDocument(Schema::Version)
0x180048daf  mov     ebx, eax
0x180048db1  test    eax, eax
0x180048db3  jns     short loc_180048DD0
0x180048db5  lea     rcx, [rbp+90h+var_110]; this
0x180048db9  call    ??1TaskXmlWriter@@QEAA@XZ; TaskXmlWriter::~TaskXmlWriter(void)
0x180048dbe  nop
0x180048dbf  lea     rcx, [rsp+190h+var_150]
0x180048dc4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180048dc9  mov     eax, ebx
0x180048dcb  jmp     loc_180049A81
0x180048dd0  mov     edx, 3
0x180048dd5  lea     rcx, [rbp+90h+var_110]
0x180048dd9  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x180048dde  mov     ebx, eax
0x180048de0  test    eax, eax
0x180048de2  js      short loc_180048DB5
0x180048de4  mov     [rsp+190h+pv], r13
0x180048de9  mov     rax, [rsi]
0x180048dec  lea     rdx, [rsp+190h+pv]
0x180048df1  mov     rcx, rsi
0x180048df4  mov     rax, [rax+0A8h]
0x180048dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048e00  mov     ebx, eax
0x180048e02  test    eax, eax
0x180048e04  jns     short loc_180048E18
0x180048e06  mov     rcx, [rsp+190h+pv]; pv
0x180048e0b  test    rcx, rcx
0x180048e0e  jz      short loc_180048DB5
0x180048e10  call    cs:__imp_CoTaskMemFree
0x180048e16  jmp     short loc_180048DB5
0x180048e18  mov     rcx, [rsp+190h+pv]
0x180048e1d  test    rcx, rcx
0x180048e20  jz      short loc_180048E44
0x180048e22  cmp     [rcx], r13w
0x180048e26  jz      short loc_180048E44
0x180048e28  mov     r8, rcx
0x180048e2b  mov     edx, 8
0x180048e30  lea     rcx, [rbp+90h+var_110]
0x180048e34  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180048e39  mov     ebx, eax
0x180048e3b  test    eax, eax
0x180048e3d  js      short loc_180048E06
0x180048e3f  mov     rcx, [rsp+190h+pv]; pv
0x180048e44  test    rcx, rcx
0x180048e47  jz      short loc_180048E4F
0x180048e49  call    cs:__imp_CoTaskMemFree
0x180048e4f  mov     [rsp+190h+pv], r13
0x180048e54  mov     rax, [rsi]
0x180048e57  lea     rdx, [rsp+190h+pv]
0x180048e5c  mov     rcx, rsi
0x180048e5f  mov     rax, [rax+98h]
0x180048e66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048e6b  mov     ebx, eax
0x180048e6d  test    eax, eax
0x180048e6f  jns     short loc_180048E73
0x180048e71  jmp     short loc_180048E06
0x180048e73  mov     rcx, [rsp+190h+pv]
0x180048e78  test    rcx, rcx
0x180048e7b  jz      short loc_180048E9F
0x180048e7d  cmp     [rcx], r13w
0x180048e81  jz      short loc_180048E9F
0x180048e83  mov     r8, rcx
0x180048e86  mov     edx, 0Ah
0x180048e8b  lea     rcx, [rbp+90h+var_110]
0x180048e8f  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180048e94  mov     ebx, eax
0x180048e96  test    eax, eax
0x180048e98  js      short loc_180048E71
0x180048e9a  mov     rcx, [rsp+190h+pv]; pv
0x180048e9f  test    rcx, rcx
0x180048ea2  jz      short loc_180048EAA
0x180048ea4  call    cs:__imp_CoTaskMemFree
0x180048eaa  lea     rcx, [rbp+90h+var_110]
0x180048eae  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x180048eb3  mov     ebx, eax
0x180048eb5  test    eax, eax
0x180048eb7  js      loc_180048DB5
0x180048ebd  mov     edx, 0Ch
0x180048ec2  lea     rcx, [rbp+90h+var_110]
0x180048ec6  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x180048ecb  mov     ebx, eax
0x180048ecd  test    eax, eax
0x180048ecf  js      loc_180048DB5
0x180048ed5  mov     [rsp+190h+var_130], r13w
0x180048edb  mov     rax, [rsi]
0x180048ede  lea     rdx, [rsp+190h+var_130]
0x180048ee3  mov     rcx, rsi
0x180048ee6  mov     rax, [rax+28h]
0x180048eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048eef  mov     ebx, eax
0x180048ef1  test    eax, eax
0x180048ef3  js      loc_180048DB5
0x180048ef9  mov     edi, r13d
0x180048efc  mov     r14d, 1
0x180048f02  lea     r15d, [r14+3Ah]
0x180048f06  cmp     di, [rsp+190h+var_130]
0x180048f0b  jnb     loc_1800492F2
0x180048f11  xorps   xmm0, xmm0
0x180048f14  movups  [rbp+90h+pExceptionObject], xmm0
0x180048f18  movups  [rbp+90h+var_60], xmm0
0x180048f1c  movups  xmmword ptr [rbp+90h+var_50], xmm0
0x180048f20  mov     [rsp+190h+pv], r13
0x180048f25  mov     rax, [rsi]
0x180048f28  lea     r8, [rsp+190h+pv]
0x180048f2d  movzx   edx, di
0x180048f30  mov     rcx, rsi
0x180048f33  mov     rax, [rax+30h]
0x180048f37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048f3c  mov     ebx, eax
0x180048f3e  test    eax, eax
0x180048f40  js      loc_1800492E3
0x180048f46  mov     rcx, [rsp+190h+pv]
0x180048f4b  mov     rax, [rcx]
0x180048f4e  lea     rdx, [rbp+90h+pExceptionObject]
0x180048f52  mov     rax, [rax+20h]
0x180048f56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048f5b  mov     ebx, eax
0x180048f5d  lea     rcx, [rsp+190h+pv]
0x180048f62  test    eax, eax
0x180048f64  js      loc_1800492E8
0x180048f6a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180048f6f  mov     ecx, [rbp+90h+var_50]
0x180048f72  test    ecx, ecx
0x180048f74  jz      short loc_180048FB3
0x180048f76  sub     ecx, 1
0x180048f79  jz      short loc_180048FAC
0x180048f7b  sub     ecx, 1
0x180048f7e  jz      short loc_180048FAC
0x180048f80  sub     ecx, 1
0x180048f83  jz      short loc_180048FAC
0x180048f85  sub     ecx, 1
0x180048f88  jz      short loc_180048FAC
0x180048f8a  sub     ecx, 1
0x180048f8d  jz      short loc_180048FA5
0x180048f8f  sub     ecx, 1
0x180048f92  jz      short loc_180048F9E
0x180048f94  cmp     ecx, 1
0x180048f97  jnz     short loc_180048FCB
0x180048f99  lea     edx, [rcx+22h]
0x180048f9c  jmp     short loc_180048FB8
0x180048f9e  mov     edx, 15h
0x180048fa3  jmp     short loc_180048FB8
0x180048fa5  mov     edx, 18h
0x180048faa  jmp     short loc_180048FB8
0x180048fac  mov     edx, 27h ; '''
0x180048fb1  jmp     short loc_180048FB8
0x180048fb3  mov     edx, 19h
0x180048fb8  lea     rcx, [rbp+90h+var_110]
0x180048fbc  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x180048fc1  mov     ebx, eax
0x180048fc3  test    eax, eax
0x180048fc5  js      loc_180048DB5
0x180048fcb  mov     r8d, dword ptr [rbp+90h+var_60+0Ch]
0x180048fcf  shr     r8d, 2
0x180048fd3  not     r8b
0x180048fd6  and     r8b, r14b
0x180048fd9  mov     edx, 13h
0x180048fde  lea     rcx, [rbp+90h+var_110]
0x180048fe2  call    ?ElementBool@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@_N@Z; TaskXmlWriter::ElementBool(TaskXmlNodeId,bool)
0x180048fe7  mov     ebx, eax
0x180048fe9  test    eax, eax
0x180048feb  js      loc_180048DB5
0x180048ff1  cmp     dword ptr [rbp+90h+var_60+8], r13d
0x180048ff5  jz      short loc_180049076
0x180048ff7  mov     edx, 0Dh
0x180048ffc  lea     rcx, [rbp+90h+var_110]
0x180049000  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x180049005  mov     ebx, eax
0x180049007  test    eax, eax
0x180049009  js      loc_180048DB5
0x18004900f  imul    r8d, dword ptr [rbp+90h+var_60+8], 3Ch ; '<'
0x180049014  mov     edx, 0Eh
0x180049019  lea     rcx, [rbp+90h+var_110]
0x18004901d  call    ?ElementDuration@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@K@Z; TaskXmlWriter::ElementDuration(TaskXmlNodeId,ulong)
0x180049022  mov     ebx, eax
0x180049024  test    eax, eax
0x180049026  js      loc_180048DB5
0x18004902c  imul    r8d, dword ptr [rbp+90h+var_60+4], 3Ch ; '<'
0x180049031  mov     edx, 0Fh
0x180049036  lea     rcx, [rbp+90h+var_110]
0x18004903a  call    ?ElementDuration@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@K@Z; TaskXmlWriter::ElementDuration(TaskXmlNodeId,ulong)
0x18004903f  mov     ebx, eax
0x180049041  test    eax, eax
0x180049043  js      loc_180048DB5
0x180049049  mov     r8d, dword ptr [rbp+90h+var_60+0Ch]
0x18004904d  shr     r8d, 1
0x180049050  and     r8b, r14b
0x180049053  mov     edx, 10h
0x180049058  lea     rcx, [rbp+90h+var_110]
0x18004905c  call    ?ElementBool@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@_N@Z; TaskXmlWriter::ElementBool(TaskXmlNodeId,bool)
0x180049061  mov     ebx, eax
0x180049063  test    eax, eax
0x180049065  js      loc_180048DB5
0x18004906b  lea     rcx, [rbp+90h+var_110]
0x18004906f  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x180049074  jmp     short loc_180049095
0x180049076  mov     eax, dword ptr [rbp+90h+var_60+4]
0x180049079  test    eax, eax
0x18004907b  jz      short loc_18004909F
0x18004907d  test    byte ptr [rbp+90h+var_60+0Ch], 2
0x180049081  jz      short loc_18004909F
0x180049083  imul    r8d, eax, 3Ch ; '<'
0x180049087  mov     edx, 14h
0x18004908c  lea     rcx, [rbp+90h+var_110]
0x180049090  call    ?ElementDuration@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@K@Z; TaskXmlWriter::ElementDuration(TaskXmlNodeId,ulong)
0x180049095  test    eax, eax
0x180049097  mov     ebx, eax
0x180049099  js      loc_180048DB5
0x18004909f  test    byte ptr [rbp+90h+var_60+0Ch], r14b
0x1800490a3  jz      short loc_1800490E1
0x1800490a5  movzx   eax, word ptr [rbp+90h+pExceptionObject+0Eh]
0x1800490a9  movzx   r9d, word ptr [rbp+90h+pExceptionObject+0Ch]
0x1800490ae  movzx   r8d, word ptr [rbp+90h+pExceptionObject+0Ah]
0x1800490b3  mov     [rsp+190h+var_158], r15d
0x1800490b8  mov     [rsp+190h+var_160], r15d
0x1800490bd  mov     [rsp+190h+var_168], 17h
0x1800490c5  mov     [rsp+190h+var_170], eax
0x1800490c9  mov     edx, 12h
0x1800490ce  lea     rcx, [rbp+90h+var_110]
0x1800490d2  call    ?ElementDateTime@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@HHHHHH@Z; TaskXmlWriter::ElementDateTime(TaskXmlNodeId,int,int,int,int,int,int)
0x1800490d7  mov     ebx, eax
0x1800490d9  test    eax, eax
0x1800490db  js      loc_180048DB5
0x1800490e1  mov     ecx, [rbp+90h+var_50]
0x1800490e4  test    ecx, ecx
0x1800490e6  jz      loc_180049288
0x1800490ec  sub     ecx, 1
0x1800490ef  jz      short loc_180049120
0x1800490f1  sub     ecx, 1
0x1800490f4  jz      short loc_180049120
0x1800490f6  sub     ecx, 1
0x1800490f9  jz      short loc_180049120
0x1800490fb  sub     ecx, 1
0x1800490fe  jz      short loc_180049120
0x180049100  sub     ecx, 1
  ... truncated ...
```
