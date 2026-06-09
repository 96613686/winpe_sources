# UniSession::GenerateXmlLegacy(ITask *,ATL::CComBSTR &)

- ea: `0x18004c7d8`
- end: `0x18004d62f`
- name: `?GenerateXmlLegacy@UniSession@@CAJPEAUITask@@AEAVCComBSTR@ATL@@@Z`
- size: `3671`
- prototype: `static int(struct ITask *, struct ATL::CComBSTR *)`
- caller_count: `3`
- callee_count: `28`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800060d0`
- `0x18001f8c0`
- `0x180020e40`

## callees

- `0x180001880`
- `0x180002554`
- `0x180003a30`
- `0x180003ea0`
- `0x180003f30`
- `0x180004ee0`
- `0x180005924`
- `0x180007e90`
- `0x18000a460`
- `0x1800145c0`
- `0x18002eee0`
- `0x180033528`
- `0x180034628`
- `0x1800361b0`
- `0x180036bd8`
- `0x18003966c`
- `0x18003c640`
- `0x18003d034`
- `0x18003e88c`
- `0x18004c438`
- `0x18004c7d8`
- `0x18004ebb4`
- `0x18004ec3c`
- `0x18004f018`
- `0x18004f080`
- `0x18004f0e8`
- `0x180052640`
- `0x180058010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18004d4d5`
- `msvcrt!_wcsicmp` at `0x18004d4d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c938`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c977`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c9d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d23f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d277`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d359`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d429`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d487`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d55c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d573`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d58a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d5b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d5cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d5e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c938`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c977`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c9d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d23f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d277`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d359`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d429`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d487`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d55c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d573`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d58a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d5b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d5cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d5e4`

## string_xrefs

- `0x18004d317`: `InteractiveToken`
- `0x18004d3c1`: `InteractiveTokenOrPassword`

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
    *(_QWORD *)&v52 = &qword_18007B2F0;
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
0x18004c7d8  mov     [rsp-8+arg_10], rbx
0x18004c7dd  push    rbp
0x18004c7de  push    rsi
0x18004c7df  push    rdi
0x18004c7e0  push    r12
0x18004c7e2  push    r13
0x18004c7e4  push    r14
0x18004c7e6  push    r15
0x18004c7e8  lea     rbp, [rsp-60h]
0x18004c7ed  sub     rsp, 160h
0x18004c7f4  mov     rax, cs:__security_cookie
0x18004c7fb  xor     rax, rsp
0x18004c7fe  mov     [rbp+90h+var_38], rax
0x18004c802  mov     r12, rdx
0x18004c805  mov     rsi, rcx
0x18004c808  mov     ecx, 28h ; '('; unsigned __int64
0x18004c80d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004c812  mov     [rsp+190h+var_118], rax
0x18004c817  xor     r13d, r13d
0x18004c81a  test    rax, rax
0x18004c81d  jz      short loc_18004C82C
0x18004c81f  mov     rcx, rax; this
0x18004c822  call    ??0CBstrWriter@@QEAA@XZ; CBstrWriter::CBstrWriter(void)
0x18004c827  mov     rbx, rax
0x18004c82a  jmp     short loc_18004C82F
0x18004c82c  mov     rbx, r13
0x18004c82f  mov     [rsp+190h+var_150], rbx
0x18004c834  test    rbx, rbx
0x18004c837  jz      short loc_18004C849
0x18004c839  mov     rax, [rbx]
0x18004c83c  mov     rcx, rbx
0x18004c83f  mov     rax, [rax+8]
0x18004c843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c848  nop
0x18004c849  test    rbx, rbx
0x18004c84c  jnz     short loc_18004C896
0x18004c84e  mov     byte ptr [rbp+90h+pExceptionObject+8], r13b
0x18004c852  lea     rax, qword_18007B2F0
0x18004c859  mov     qword ptr [rbp+90h+var_60], rax
0x18004c85d  mov     qword ptr [rbp+90h+var_60+8], r13
0x18004c861  mov     qword ptr [rbp+90h+var_50], r13
0x18004c865  mov     [rbp+90h+var_50+8], 0Eh
0x18004c86c  mov     [rbp+90h+var_50+0Ch], 0FFFFFFFFh
0x18004c873  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004c877  mov     [rbp+90h+var_40], edi
0x18004c87a  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18004c881  mov     qword ptr [rbp+90h+pExceptionObject], rax
0x18004c885  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18004c88c  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x18004c890  call    _CxxThrowException_0
0x18004c896  mov     ebx, 10001h
0x18004c89b  mov     dword ptr [rsp+190h+pv], ebx
0x18004c89f  lea     rdx, [rsp+190h+var_150]
0x18004c8a4  lea     rcx, [rsp+190h+var_118]
0x18004c8a9  call    ??$?0V?$CComPtr@UIStream@@@ATL@@@?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@AEBV?$CComPtr@UIStream@@@ATL@@@Z; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::_com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>(ATL::CComPtr<IStream> const &)
0x18004c8ae  lea     r8, [rsp+190h+pv]
0x18004c8b3  lea     rdx, [rsp+190h+var_118]
0x18004c8b8  lea     rcx, [rbp+90h+var_110]
0x18004c8bc  call    ??0TaskXmlWriter@@QEAA@AEBV?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEBUSchema@@@Z; TaskXmlWriter::TaskXmlWriter(_com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>> const &,Schema const &)
0x18004c8c1  nop
0x18004c8c2  lea     rcx, [rsp+190h+var_118]
0x18004c8c7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004c8cc  mov     edx, ebx
0x18004c8ce  lea     rcx, [rbp+90h+var_110]
0x18004c8d2  call    ?StartDocument@TaskXmlWriter@@QEAAJW4Version@Schema@@@Z; TaskXmlWriter::StartDocument(Schema::Version)
0x18004c8d7  mov     ebx, eax
0x18004c8d9  test    eax, eax
0x18004c8db  jns     short loc_18004C8F8
0x18004c8dd  lea     rcx, [rbp+90h+var_110]; this
0x18004c8e1  call    ??1TaskXmlWriter@@QEAA@XZ; TaskXmlWriter::~TaskXmlWriter(void)
0x18004c8e6  nop
0x18004c8e7  lea     rcx, [rsp+190h+var_150]
0x18004c8ec  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004c8f1  mov     eax, ebx
0x18004c8f3  jmp     loc_18004D607
0x18004c8f8  mov     edx, 3
0x18004c8fd  lea     rcx, [rbp+90h+var_110]
0x18004c901  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x18004c906  mov     ebx, eax
0x18004c908  test    eax, eax
0x18004c90a  js      short loc_18004C8DD
0x18004c90c  mov     [rsp+190h+pv], r13
0x18004c911  mov     rax, [rsi]
0x18004c914  lea     rdx, [rsp+190h+pv]
0x18004c919  mov     rcx, rsi
0x18004c91c  mov     rax, [rax+0A8h]
0x18004c923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c928  mov     ebx, eax
0x18004c92a  test    eax, eax
0x18004c92c  jns     short loc_18004C946
0x18004c92e  mov     rcx, [rsp+190h+pv]; pv
0x18004c933  test    rcx, rcx
0x18004c936  jz      short loc_18004C8DD
0x18004c938  call    cs:__imp_CoTaskMemFree
0x18004c93f  nop     dword ptr [rax+rax+00h]
0x18004c944  jmp     short loc_18004C8DD
0x18004c946  mov     rcx, [rsp+190h+pv]
0x18004c94b  test    rcx, rcx
0x18004c94e  jz      short loc_18004C972
0x18004c950  cmp     [rcx], r13w
0x18004c954  jz      short loc_18004C972
0x18004c956  mov     r8, rcx
0x18004c959  mov     edx, 8
0x18004c95e  lea     rcx, [rbp+90h+var_110]
0x18004c962  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x18004c967  mov     ebx, eax
0x18004c969  test    eax, eax
0x18004c96b  js      short loc_18004C92E
0x18004c96d  mov     rcx, [rsp+190h+pv]; pv
0x18004c972  test    rcx, rcx
0x18004c975  jz      short loc_18004C983
0x18004c977  call    cs:__imp_CoTaskMemFree
0x18004c97e  nop     dword ptr [rax+rax+00h]
0x18004c983  mov     [rsp+190h+pv], r13
0x18004c988  mov     rax, [rsi]
0x18004c98b  lea     rdx, [rsp+190h+pv]
0x18004c990  mov     rcx, rsi
0x18004c993  mov     rax, [rax+98h]
0x18004c99a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c99f  mov     ebx, eax
0x18004c9a1  test    eax, eax
0x18004c9a3  jns     short loc_18004C9A7
0x18004c9a5  jmp     short loc_18004C92E
0x18004c9a7  mov     rcx, [rsp+190h+pv]
0x18004c9ac  test    rcx, rcx
0x18004c9af  jz      short loc_18004C9D3
0x18004c9b1  cmp     [rcx], r13w
0x18004c9b5  jz      short loc_18004C9D3
0x18004c9b7  mov     r8, rcx
0x18004c9ba  mov     edx, 0Ah
0x18004c9bf  lea     rcx, [rbp+90h+var_110]
0x18004c9c3  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x18004c9c8  mov     ebx, eax
0x18004c9ca  test    eax, eax
0x18004c9cc  js      short loc_18004C9A5
0x18004c9ce  mov     rcx, [rsp+190h+pv]; pv
0x18004c9d3  test    rcx, rcx
0x18004c9d6  jz      short loc_18004C9E4
0x18004c9d8  call    cs:__imp_CoTaskMemFree
0x18004c9df  nop     dword ptr [rax+rax+00h]
0x18004c9e4  lea     rcx, [rbp+90h+var_110]
0x18004c9e8  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x18004c9ed  mov     ebx, eax
0x18004c9ef  test    eax, eax
0x18004c9f1  js      loc_18004C8DD
0x18004c9f7  mov     edx, 0Ch
0x18004c9fc  lea     rcx, [rbp+90h+var_110]
0x18004ca00  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x18004ca05  mov     ebx, eax
0x18004ca07  test    eax, eax
0x18004ca09  js      loc_18004C8DD
0x18004ca0f  mov     [rsp+190h+var_130], r13w
0x18004ca15  mov     rax, [rsi]
0x18004ca18  lea     rdx, [rsp+190h+var_130]
0x18004ca1d  mov     rcx, rsi
0x18004ca20  mov     rax, [rax+28h]
0x18004ca24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca29  mov     ebx, eax
0x18004ca2b  test    eax, eax
0x18004ca2d  js      loc_18004C8DD
0x18004ca33  mov     edi, r13d
0x18004ca36  mov     r14d, 1
0x18004ca3c  lea     r15d, [r14+3Ah]
0x18004ca40  cmp     di, [rsp+190h+var_130]
0x18004ca45  jnb     loc_18004CE2C
0x18004ca4b  xorps   xmm0, xmm0
0x18004ca4e  movups  [rbp+90h+pExceptionObject], xmm0
0x18004ca52  movups  [rbp+90h+var_60], xmm0
0x18004ca56  movups  xmmword ptr [rbp+90h+var_50], xmm0
0x18004ca5a  mov     [rsp+190h+pv], r13
0x18004ca5f  mov     rax, [rsi]
0x18004ca62  lea     r8, [rsp+190h+pv]
0x18004ca67  movzx   edx, di
0x18004ca6a  mov     rcx, rsi
0x18004ca6d  mov     rax, [rax+30h]
0x18004ca71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca76  mov     ebx, eax
0x18004ca78  test    eax, eax
0x18004ca7a  js      loc_18004CE1D
0x18004ca80  mov     rcx, [rsp+190h+pv]
0x18004ca85  mov     rax, [rcx]
0x18004ca88  lea     rdx, [rbp+90h+pExceptionObject]
0x18004ca8c  mov     rax, [rax+20h]
0x18004ca90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca95  mov     ebx, eax
0x18004ca97  lea     rcx, [rsp+190h+pv]
0x18004ca9c  test    eax, eax
0x18004ca9e  js      loc_18004CE22
0x18004caa4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004caa9  mov     ecx, [rbp+90h+var_50]
0x18004caac  test    ecx, ecx
0x18004caae  jz      short loc_18004CAED
0x18004cab0  sub     ecx, 1
0x18004cab3  jz      short loc_18004CAE6
0x18004cab5  sub     ecx, 1
0x18004cab8  jz      short loc_18004CAE6
0x18004caba  sub     ecx, 1
0x18004cabd  jz      short loc_18004CAE6
0x18004cabf  sub     ecx, 1
0x18004cac2  jz      short loc_18004CAE6
0x18004cac4  sub     ecx, 1
0x18004cac7  jz      short loc_18004CADF
0x18004cac9  sub     ecx, 1
0x18004cacc  jz      short loc_18004CAD8
0x18004cace  cmp     ecx, 1
0x18004cad1  jnz     short loc_18004CB05
0x18004cad3  lea     edx, [rcx+22h]
0x18004cad6  jmp     short loc_18004CAF2
0x18004cad8  mov     edx, 15h
0x18004cadd  jmp     short loc_18004CAF2
0x18004cadf  mov     edx, 18h
0x18004cae4  jmp     short loc_18004CAF2
0x18004cae6  mov     edx, 27h ; '''
0x18004caeb  jmp     short loc_18004CAF2
0x18004caed  mov     edx, 19h
0x18004caf2  lea     rcx, [rbp+90h+var_110]
0x18004caf6  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x18004cafb  mov     ebx, eax
0x18004cafd  test    eax, eax
0x18004caff  js      loc_18004C8DD
0x18004cb05  mov     r8d, dword ptr [rbp+90h+var_60+0Ch]
0x18004cb09  shr     r8d, 2
0x18004cb0d  not     r8b
0x18004cb10  and     r8b, r14b
0x18004cb13  mov     edx, 13h
0x18004cb18  lea     rcx, [rbp+90h+var_110]
0x18004cb1c  call    ?ElementBool@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@_N@Z; TaskXmlWriter::ElementBool(TaskXmlNodeId,bool)
0x18004cb21  mov     ebx, eax
0x18004cb23  test    eax, eax
0x18004cb25  js      loc_18004C8DD
0x18004cb2b  cmp     dword ptr [rbp+90h+var_60+8], r13d
0x18004cb2f  jz      short loc_18004CBB0
0x18004cb31  mov     edx, 0Dh
0x18004cb36  lea     rcx, [rbp+90h+var_110]
0x18004cb3a  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x18004cb3f  mov     ebx, eax
0x18004cb41  test    eax, eax
0x18004cb43  js      loc_18004C8DD
0x18004cb49  imul    r8d, dword ptr [rbp+90h+var_60+8], 3Ch ; '<'
0x18004cb4e  mov     edx, 0Eh
0x18004cb53  lea     rcx, [rbp+90h+var_110]
0x18004cb57  call    ?ElementDuration@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@K@Z; TaskXmlWriter::ElementDuration(TaskXmlNodeId,ulong)
0x18004cb5c  mov     ebx, eax
0x18004cb5e  test    eax, eax
0x18004cb60  js      loc_18004C8DD
0x18004cb66  imul    r8d, dword ptr [rbp+90h+var_60+4], 3Ch ; '<'
0x18004cb6b  mov     edx, 0Fh
0x18004cb70  lea     rcx, [rbp+90h+var_110]
0x18004cb74  call    ?ElementDuration@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@K@Z; TaskXmlWriter::ElementDuration(TaskXmlNodeId,ulong)
0x18004cb79  mov     ebx, eax
0x18004cb7b  test    eax, eax
0x18004cb7d  js      loc_18004C8DD
0x18004cb83  mov     r8d, dword ptr [rbp+90h+var_60+0Ch]
0x18004cb87  shr     r8d, 1
0x18004cb8a  and     r8b, r14b
0x18004cb8d  mov     edx, 10h
0x18004cb92  lea     rcx, [rbp+90h+var_110]
0x18004cb96  call    ?ElementBool@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@_N@Z; TaskXmlWriter::ElementBool(TaskXmlNodeId,bool)
0x18004cb9b  mov     ebx, eax
0x18004cb9d  test    eax, eax
0x18004cb9f  js      loc_18004C8DD
0x18004cba5  lea     rcx, [rbp+90h+var_110]
0x18004cba9  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x18004cbae  jmp     short loc_18004CBCF
0x18004cbb0  mov     eax, dword ptr [rbp+90h+var_60+4]
0x18004cbb3  test    eax, eax
0x18004cbb5  jz      short loc_18004CBD9
0x18004cbb7  test    byte ptr [rbp+90h+var_60+0Ch], 2
0x18004cbbb  jz      short loc_18004CBD9
0x18004cbbd  imul    r8d, eax, 3Ch ; '<'
0x18004cbc1  mov     edx, 14h
0x18004cbc6  lea     rcx, [rbp+90h+var_110]
0x18004cbca  call    ?ElementDuration@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@K@Z; TaskXmlWriter::ElementDuration(TaskXmlNodeId,ulong)
0x18004cbcf  test    eax, eax
0x18004cbd1  mov     ebx, eax
0x18004cbd3  js      loc_18004C8DD
0x18004cbd9  test    byte ptr [rbp+90h+var_60+0Ch], r14b
0x18004cbdd  jz      short loc_18004CC1B
0x18004cbdf  movzx   eax, word ptr [rbp+90h+pExceptionObject+0Eh]
0x18004cbe3  movzx   r9d, word ptr [rbp+90h+pExceptionObject+0Ch]
0x18004cbe8  movzx   r8d, word ptr [rbp+90h+pExceptionObject+0Ah]
0x18004cbed  mov     [rsp+190h+var_158], r15d
0x18004cbf2  mov     [rsp+190h+var_160], r15d
0x18004cbf7  mov     [rsp+190h+var_168], 17h
0x18004cbff  mov     [rsp+190h+var_170], eax
0x18004cc03  mov     edx, 12h
0x18004cc08  lea     rcx, [rbp+90h+var_110]
0x18004cc0c  call    ?ElementDateTime@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@HHHHHH@Z; TaskXmlWriter::ElementDateTime(TaskXmlNodeId,int,int,int,int,int,int)
0x18004cc11  mov     ebx, eax
0x18004cc13  test    eax, eax
0x18004cc15  js      loc_18004C8DD
0x18004cc1b  mov     ecx, [rbp+90h+var_50]
0x18004cc1e  test    ecx, ecx
0x18004cc20  jz      loc_18004CDC2
0x18004cc26  sub     ecx, 1
0x18004cc29  jz      short loc_18004CC5A
0x18004cc2b  sub     ecx, 1
0x18004cc2e  jz      short loc_18004CC5A
0x18004cc30  sub     ecx, 1
0x18004cc33  jz      short loc_18004CC5A
  ... truncated ...
```
