# JobStore::GenerateTaskXmlFromCollections(JobMoniker &,Triggers::Trigulator &,Actions::ActionCollection &,wmi::AutoVectorPtr<ushort> &)

- ea: `0x18000bc60`
- end: `0x18000c920`
- name: `?GenerateTaskXmlFromCollections@JobStore@@QEAAJAEAVJobMoniker@@AEAVTrigulator@Triggers@@AEAVActionCollection@Actions@@AEAV?$AutoVectorPtr@G@wmi@@@Z`
- size: `3264`
- prototype: ``
- caller_count: `5`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800104c0`
- `0x18001d7ac`
- `0x180047ee0`
- `0x18004fc18`
- `0x18006fed4`

## callees

- `0x180004e20`
- `0x180006ac0`
- `0x18000a460`
- `0x18000a4ec`
- `0x18000a530`
- `0x18000b8c4`
- `0x18000bc60`
- `0x18000c9d0`
- `0x18000d830`
- `0x180011e40`
- `0x180036fb0`
- `0x180042604`
- `0x180054824`
- `0x18005a2bc`
- `0x180082a40`
- `0x180088010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000c374`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000c374`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c394`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c40e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c43e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c7e8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c394`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c40e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c43e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c7e8`
- `OLEAUT32!__imp_SysStringLen` at `0x18000c495`
- `OLEAUT32!__imp_SysStringLen` at `0x18000c495`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c62c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c62c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000bcc8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c459`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c4c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000bcc8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c459`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c4c3`
- `XmlLite!CreateXmlWriter` at `0x18000bd8f`
- `XmlLite!CreateXmlWriter` at `0x18000bd8f`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x18000bdfc`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x18000bdfc`

## string_xrefs

- `0x18000c1a6`: `xmlns`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall JobStore::GenerateTaskXmlFromCollections(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        Actions::ActionCollection *a4,
        LPVOID *a5)
{
  int v8; // r14d
  int v9; // eax
  IXmlWriterOutput *v10; // rax
  CBstrWriter *v11; // rax
  struct IErrorInfo *v12; // rdx
  __int64 v13; // r8
  CBstrWriter *v14; // r9
  UINT *v15; // r12
  IUnknown *v16; // rcx
  int v17; // ebx
  HRESULT v18; // ebx
  struct Schema *v19; // r8
  void *v20; // rcx
  void *v21; // rbx
  struct IErrorInfo *v22; // rdx
  struct IErrorInfo *v23; // rdx
  struct IErrorInfo *v24; // rdx
  struct IErrorInfo *v25; // rdx
  const struct SchemaEntry * near *v26; // r8
  struct IErrorInfo *v27; // rdx
  const struct SchemaEntry * near *v28; // r8
  struct IErrorInfo *v29; // rdx
  int v30; // ebx
  struct Schema *v31; // r8
  unsigned __int64 v32; // rdx
  _QWORD *v33; // rcx
  const struct SchemaEntry * near *v34; // r8
  int v35; // edi
  __int64 *v36; // rbx
  const unsigned __int64 *v38; // r9
  unsigned __int64 v39; // r9
  const unsigned __int64 *v40; // r9
  struct IErrorInfo *v41; // rdx
  int v42; // ebx
  struct IErrorInfo *v43; // rdx
  OLECHAR *v44; // rbx
  __int64 v45; // r12
  OLECHAR *v46; // rdi
  unsigned __int64 v47; // r10
  struct IUnknownVtbl *i; // r11
  unsigned __int64 AddRef; // rcx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdx
  unsigned __int64 v51; // r9
  OLECHAR *v52; // r8
  OLECHAR v53; // ax
  ULONG (__stdcall *v54)(IUnknown *); // rax
  volatile signed __int32 *v55; // rax
  volatile signed __int32 *v56; // rsi
  unsigned __int64 v57; // rdi
  SIZE_T v58; // rax
  unsigned int v59; // edx
  _WORD *v60; // rbx
  LPVOID *v61; // r14
  __int16 *v62; // rcx
  unsigned int v63; // r14d
  __int16 v64; // ax
  struct IErrorInfo *v65; // rdx
  IXmlWriterOutput *v66; // [rsp+30h] [rbp-D0h] BYREF
  IXmlWriterOutput *ppOutput; // [rsp+38h] [rbp-C8h] BYREF
  int v68; // [rsp+40h] [rbp-C0h] BYREF
  void *ppvObject; // [rsp+48h] [rbp-B8h] BYREF
  IXmlWriterOutput *v70; // [rsp+50h] [rbp-B0h]
  LPVOID *v71; // [rsp+58h] [rbp-A8h]
  struct IErrorInfo *v72; // [rsp+60h] [rbp-A0h] BYREF
  IUnknown *pOutputStream; // [rsp+68h] [rbp-98h] BYREF
  void *v74; // [rsp+70h] [rbp-90h]
  int v75; // [rsp+F8h] [rbp-8h]
  void **pExceptionObject; // [rsp+100h] [rbp+0h] BYREF
  char v77; // [rsp+108h] [rbp+8h]
  const unsigned __int16 *v78; // [rsp+110h] [rbp+10h]
  __int64 v79; // [rsp+118h] [rbp+18h]
  __int64 v80; // [rsp+120h] [rbp+20h]
  int v81; // [rsp+128h] [rbp+28h]
  __int64 v82; // [rsp+12Ch] [rbp+2Ch]

  v71 = a5;
  v8 = *(_DWORD *)(*(_QWORD *)(a2 + 32) + 96LL);
  v9 = v8;
  if ( !v8 )
    v9 = 65542;
  v68 = v9;
  v10 = (IXmlWriterOutput *)HeapAlloc(g_PrivateHeap, 0, 0x28u);
  if ( !v10 )
  {
    v77 = 0;
    v78 = &qword_1800A8718;
    v79 = 0;
    v80 = 0;
    v81 = 14;
    v82 = -1;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  ppOutput = v10;
  v11 = CBstrWriter::CBstrWriter((CBstrWriter *)v10);
  v14 = v11;
  v15 = 0;
  v70 = 0;
  v66 = 0;
  v16 = 0;
  if ( v11 )
  {
    ppOutput = 0;
    v17 = (**(__int64 (__fastcall ***)(CBstrWriter *, GUID *, IXmlWriterOutput **))v11)(
            v11,
            &GUID_0000000c_0000_0000_c000_000000000046,
            &ppOutput);
    if ( v17 < 0 )
    {
      ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(&v66);
      v15 = 0;
      v70 = 0;
      v66 = 0;
      v16 = 0;
    }
    else
    {
      v15 = (UINT *)ppOutput;
      v70 = ppOutput;
      v66 = ppOutput;
      v16 = ppOutput;
    }
    if ( v17 < 0 && v17 != -2147467262 )
      _com_raise_error(v17, v12);
  }
  LODWORD(v72) = v68;
  pOutputStream = v16;
  if ( v16 )
    ((void (__fastcall *)(IUnknown *, struct IErrorInfo *, __int64, CBstrWriter *))v16->lpVtbl->AddRef)(
      v16,
      v12,
      v13,
      v14);
  v74 = 0;
  v75 = 0;
  if ( !*((_QWORD *)a4 + 1) )
  {
    TaskXmlWriter::~TaskXmlWriter((TaskXmlWriter *)&v72);
    ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(&v66);
    return 2147549183LL;
  }
  ppvObject = 0;
  v18 = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  if ( v18 >= 0 )
  {
    v20 = ppvObject;
    v21 = v74;
    if ( v74 != ppvObject )
    {
      v74 = ppvObject;
      if ( ppvObject )
      {
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 8LL))(ppvObject);
        v20 = ppvObject;
      }
      if ( v21 )
      {
        (*(void (__fastcall **)(void *))(*(_QWORD *)v21 + 16LL))(v21);
        v20 = ppvObject;
      }
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)v20 + 16LL))(v20);
    ppOutput = 0;
    v18 = CreateXmlWriterOutputWithEncodingName(pOutputStream, 0, L"UTF-16", &ppOutput);
    if ( v18 >= 0 )
    {
      if ( !v74 )
        _com_raise_error(-2147467261, v22);
      v18 = (*(__int64 (__fastcall **)(void *, IXmlWriterOutput *))(*(_QWORD *)v74 + 24LL))(v74, ppOutput);
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
      if ( v18 < 0 )
        goto LABEL_55;
      if ( !v74 )
        _com_raise_error(-2147467261, v23);
      v18 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)v74 + 40LL))(v74, 1, 1);
      if ( v18 >= 0 )
      {
        if ( !v74 )
          _com_raise_error(-2147467261, v24);
        v18 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v74 + 208LL))(v74, 0);
        if ( v18 >= 0 )
        {
          if ( !v74 )
            _com_raise_error(-2147467261, v25);
          if ( (_DWORD)v72 == 65542 )
          {
LABEL_26:
            v26 = (&Schema::schemaEntries)[(unsigned __int16)v72] + 16;
          }
          else
          {
            switch ( (int)v72 )
            {
              case 65536:
              case 65537:
                v38 = 0;
                break;
              case 65538:
              case 65539:
              case 65540:
              case 65541:
                goto LABEL_26;
              default:
                goto LABEL_141;
            }
            while ( v38 < (&Schema::schemaEntriesCount)[(unsigned __int16)v72] )
            {
              v26 = &(&Schema::schemaEntries)[(unsigned __int16)v72][16 * (_QWORD)v38];
              if ( *(_DWORD *)v26 == 1 )
                goto LABEL_27;
              v38 = (const unsigned __int64 *)((char *)v38 + 1);
            }
LABEL_141:
            v26 = (const struct SchemaEntry * near *)&qword_1800A1560;
          }
LABEL_27:
          v18 = (*(__int64 (__fastcall **)(void *, const OLECHAR *, const struct SchemaEntry *, unsigned __int16 *const))(*(_QWORD *)v74 + 216LL))(
                  v74,
                  &ChannelPath,
                  v26[1],
                  Schema::namespaceUri);
          if ( v18 >= 0 )
          {
            if ( !v8 )
              goto LABEL_35;
            v18 = StringCchPrintfW(
                    (unsigned __int16 *)&pExceptionObject,
                    0x16u,
                    L"%d.%d",
                    (unsigned int)v72 >> 16,
                    (unsigned __int16)v72);
            if ( v18 >= 0 )
            {
              if ( !v74 )
                _com_raise_error(-2147467261, v27);
              if ( (_DWORD)v72 == 65542 )
              {
LABEL_32:
                v28 = (&Schema::schemaEntries)[(unsigned __int16)v72] + 32;
              }
              else
              {
                switch ( (int)v72 )
                {
                  case 65536:
                  case 65537:
                    v40 = 0;
                    break;
                  case 65538:
                  case 65539:
                  case 65540:
                  case 65541:
                    goto LABEL_32;
                  default:
                    goto LABEL_143;
                }
                while ( v40 < (&Schema::schemaEntriesCount)[(unsigned __int16)v72] )
                {
                  v28 = &(&Schema::schemaEntries)[(unsigned __int16)v72][16 * (_QWORD)v40];
                  if ( *(_DWORD *)v28 == 2 )
                    goto LABEL_33;
                  v40 = (const unsigned __int64 *)((char *)v40 + 1);
                }
LABEL_143:
                v28 = (const struct SchemaEntry * near *)&qword_1800A1560;
              }
LABEL_33:
              v18 = (*(__int64 (__fastcall **)(void *, const OLECHAR *, const struct SchemaEntry *, _QWORD, void ***))(*(_QWORD *)v74 + 56LL))(
                      v74,
                      &ChannelPath,
                      v28[1],
                      0,
                      &pExceptionObject);
              if ( v18 >= 0 )
              {
                if ( !v74 )
                  _com_raise_error(-2147467261, v29);
                v18 = (*(__int64 (__fastcall **)(void *, const OLECHAR *, const unsigned __int16 *, _QWORD, unsigned __int16 *const))(*(_QWORD *)v74 + 56LL))(
                        v74,
                        &ChannelPath,
                        L"xmlns",
                        0,
                        Schema::namespaceUri);
              }
            }
          }
        }
      }
    }
  }
  if ( v18 < 0 )
  {
LABEL_55:
    if ( v74 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v74 + 16LL))(v74);
    if ( pOutputStream )
      ((void (__fastcall *)(IUnknown *))pOutputStream->lpVtbl->Release)(pOutputStream);
    if ( v15 )
      (*(void (__fastcall **)(UINT *))(*(_QWORD *)v15 + 16LL))(v15);
    return (unsigned int)v18;
  }
LABEL_35:
  v30 = JobBucket::WriteRegistrationXml(*(JobBucket **)(a2 + 32), (struct TaskXmlWriter *)&v72, v19);
  if ( v30 < 0 )
    goto LABEL_145;
  v30 = JobBucket::WritePrincipalXml(*(JobBucket **)(a2 + 32), (struct TaskXmlWriter *)&v72, v31);
  if ( v30 < 0 )
    goto LABEL_145;
  v30 = JobBucket::WriteSettingsXml(*(JobBucket **)(a2 + 32), (struct TaskXmlWriter *)&v72, (struct Schema *)&v68);
  if ( v30 < 0 )
    goto LABEL_145;
  v33 = *(_QWORD **)(*(_QWORD *)(a2 + 32) + 168LL);
  if ( v33 )
  {
    if ( *v33 )
    {
      v30 = TaskXmlWriter::ElementCData(&v72, 96);
      if ( v30 < 0 )
        goto LABEL_145;
    }
  }
  if ( v75 )
  {
    ++v75;
  }
  else
  {
    v32 = (unsigned int)v72;
    if ( (_DWORD)v72 == 65542 )
    {
LABEL_43:
      v34 = (&Schema::schemaEntries)[(unsigned __int16)v72] + 192;
    }
    else
    {
      switch ( (int)v72 )
      {
        case 65536:
        case 65537:
          v39 = 0;
          v32 = (unsigned __int64)(&Schema::schemaEntriesCount)[(unsigned __int16)v72];
          break;
        case 65538:
        case 65539:
        case 65540:
        case 65541:
          goto LABEL_43;
        default:
          goto LABEL_147;
      }
      while ( v39 < v32 )
      {
        v34 = &(&Schema::schemaEntries)[(unsigned __int16)v72][16 * v39];
        if ( *(_DWORD *)v34 == 12 )
          goto LABEL_45;
        ++v39;
      }
LABEL_147:
      v34 = (const struct SchemaEntry * near *)&qword_1800A1560;
    }
    if ( *(_DWORD *)v34 )
    {
LABEL_45:
      if ( !v74 )
        _com_raise_error(-2147467261, (struct IErrorInfo *)v32);
      v35 = (*(__int64 (__fastcall **)(void *, const OLECHAR *, const struct SchemaEntry *, unsigned __int16 *const))(*(_QWORD *)v74 + 216LL))(
              v74,
              &ChannelPath,
              v34[1],
              Schema::namespaceUri);
      if ( v35 < 0 )
        goto LABEL_52;
    }
    else
    {
      v75 = 1;
    }
  }
  v36 = *(__int64 **)(a3 + 32);
  while ( 1 )
  {
    v36 = (__int64 *)*v36;
    if ( v36 == *(__int64 **)(a3 + 32) )
      break;
    v35 = (*(__int64 (__fastcall **)(__int64, struct IErrorInfo **))(*(_QWORD *)v36[2] + 40LL))(v36[2], &v72);
    if ( v35 < 0 )
      goto LABEL_52;
  }
  if ( v75 )
  {
    --v75;
  }
  else
  {
    if ( !v74 )
      _com_raise_error(-2147467261, (struct IErrorInfo *)v32);
    v35 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v74 + 120LL))(v74);
    if ( v35 < 0 )
    {
LABEL_52:
      TaskXmlWriter::~TaskXmlWriter((TaskXmlWriter *)&v72);
      ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(&v66);
      return (unsigned int)v35;
    }
  }
  v30 = Actions::ActionCollection::WriteXml(a4, (struct TaskXmlWriter *)&v72);
  if ( v30 < 0 )
  {
LABEL_145:
    TaskXmlWriter::~TaskXmlWriter((TaskXmlWriter *)&v72);
    ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(&v66);
    return (unsigned int)v30;
  }
  if ( !v74 )
    _com_raise_error(-2147467261, v65);
  v42 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v74 + 248LL))(v74);
  if ( v42 < 0 )
    goto LABEL_127;
  if ( v75 )
  {
    --v75;
  }
  else
  {
    if ( !v74 )
      _com_raise_error(-2147467261, v41);
    v42 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v74 + 120LL))(v74);
    if ( v42 < 0 )
      goto LABEL_127;
  }
  if ( !v74 )
    _com_raise_error(-2147467261, v41);
  v42 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v74 + 112LL))(v74);
  if ( v42 < 0 )
    goto LABEL_127;
  if ( !v74 )
    _com_raise_error(-2147467261, v43);
  v42 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v74 + 248LL))(v74);
  if ( v42 < 0 )
  {
LABEL_127:
    if ( v74 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v74 + 16LL))(v74);
    ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(&pOutputStream);
    if ( v15 )
      (*(void (__fastcall **)(UINT *))(*(_QWORD *)v15 + 16LL))(v15);
    return (unsigned int)v42;
  }
  v44 = SysAllocStringLen(0, v15[4]);
  v45 = 2147483646;
  if ( v44 )
  {
    SysFreeString(0);
    v46 = v44;
    v47 = (unsigned __int64)&v70[2].lpVtbl->QueryInterface + 1;
    for ( i = v70[3].lpVtbl; i; i = (struct IUnknownVtbl *)i->Release )
    {
      if ( !v47 )
        goto LABEL_97;
      if ( v47 > 0x7FFFFFFF || (AddRef = (unsigned __int64)i->AddRef, AddRef > 0x7FFFFFFE) )
      {
        *v46 = 0;
LABEL_97:
        SysFreeString(v44);
        v44 = 0;
        goto LABEL_100;
      }
      QueryInterface = i->QueryInterface;
      v51 = v47;
      v52 = v46;
      while ( AddRef )
      {
        v53 = *(_WORD *)QueryInterface;
        if ( !*(_WORD *)QueryInterface )
          break;
        QueryInterface = (HRESULT (__stdcall *)(IUnknown *, const IID *const, void **))((char *)QueryInterface + 2);
        *v52++ = v53;
        --AddRef;
        if ( !--v51 )
        {
          *(v52 - 1) = 0;
          goto LABEL_97;
        }
      }
      *v52 = 0;
      v54 = i->AddRef;
      v46 += (__int64)v54;
      v47 -= (unsigned __int64)v54;
    }
    SysFreeString(0);
  }
  else
  {
    SysFreeString(0);
    v44 = 0;
  }
LABEL_100:
  v55 = (volatile signed __int32 *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
  v56 = v55;
  if ( !v55 )
  {
    v77 = 0;
    v78 = &qword_1800A8718;
    v79 = 0;
    v80 = 0;
    v81 = 14;
    v82 = -1;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  *((_QWORD *)v55 + 1) = 0;
  *((_DWORD *)v55 + 4) = 1;
  *(_QWORD *)v55 = v44;
  ppOutput = (IXmlWriterOutput *)v55;
  if ( v44 )
  {
    v57 = SysStringLen(v44) + 1;
    v58 = 2 * v57;
    if ( !is_mul_ok(v57, 2u) )
      v58 = -1;
    v60 = HeapAlloc(g_PrivateHeap, 0, v58);
    if ( !v60 )
    {
      v77 = 0;
      v78 = &qword_1800A8718;
      v79 = 0;
      v80 = 0;
      v81 = 14;
      v82 = -1;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    v61 = v71;
    if ( *v71 )
      HeapFree(g_PrivateHeap, 0, *v71);
    *v61 = v60;
    if ( v57 )
    {
      if ( v57 > 0x7FFFFFFF )
      {
        v63 = -2147024809;
      }
      else
      {
        v62 = *(__int16 **)v56;
        v63 = 0;
        while ( v45 )
        {
          v64 = *v62;
          if ( !*v62 )
            break;
          ++v62;
          *v60++ = v64;
          --v45;
          if ( !--v57 )
          {
            --v60;
            v63 = -2147024774;
            break;
          }
        }
      }
      *v60 = 0;
    }
    else
    {
      v63 = -2147024809;
    }
    if ( _InterlockedExchangeAdd(v56 + 4, 0xFFFFFFFF) == 1 )
      _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v56, v59);
    if ( v74 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v74 + 16LL))(v74);
    if ( pOutputStream )
      ((void (__fastcall *)(IUnknown *))pOutputStream->lpVtbl->Release)(pOutputStream);
    if ( v70 )
      ((void (__fastcall *)(IXmlWriterOutput *))v70->lpVtbl->Release)(v70);
    return v63;
  }
  else
  {
    _bstr_t::~_bstr_t((_bstr_t *)&ppOutput);
    TaskXmlWriter::~TaskXmlWriter((TaskXmlWriter *)&v72);
    ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(&v66);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18000bc60  mov     [rsp-8+arg_0], rbx
0x18000bc65  push    rbp
0x18000bc66  push    rsi
0x18000bc67  push    rdi
0x18000bc68  push    r12
0x18000bc6a  push    r13
0x18000bc6c  push    r14
0x18000bc6e  push    r15
0x18000bc70  lea     rbp, [rsp-40h]
0x18000bc75  sub     rsp, 140h
0x18000bc7c  mov     rax, cs:__security_cookie
0x18000bc83  xor     rax, rsp
0x18000bc86  mov     [rbp+70h+var_38], rax
0x18000bc8a  mov     r15, r9
0x18000bc8d  mov     rsi, r8
0x18000bc90  mov     rdi, rdx
0x18000bc93  mov     rax, [rbp+70h+arg_20]
0x18000bc9a  mov     [rsp+170h+var_118], rax
0x18000bc9f  mov     rax, [rdx+20h]
0x18000bca3  mov     r14d, [rax+60h]
0x18000bca7  mov     eax, r14d
0x18000bcaa  mov     ecx, 10006h
0x18000bcaf  test    r14d, r14d
0x18000bcb2  cmovz   eax, ecx
0x18000bcb5  mov     [rsp+170h+var_130], eax
0x18000bcb9  xor     edx, edx; dwFlags
0x18000bcbb  mov     r8d, 28h ; '('; dwBytes
0x18000bcc1  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18000bcc8  call    cs:__imp_HeapAlloc
0x18000bccf  nop     dword ptr [rax+rax+00h]
0x18000bcd4  test    rax, rax
0x18000bcd7  jz      loc_18000C64A
0x18000bcdd  mov     [rsp+170h+ppOutput], rax
0x18000bce2  mov     rcx, rax; this
0x18000bce5  call    ??0CBstrWriter@@QEAA@XZ; CBstrWriter::CBstrWriter(void)
0x18000bcea  mov     r9, rax
0x18000bced  xor     r13d, r13d
0x18000bcf0  mov     r12d, r13d
0x18000bcf3  mov     [rsp+170h+var_120], r13
0x18000bcf8  mov     [rsp+170h+var_140], r13
0x18000bcfd  mov     ecx, r13d
0x18000bd00  test    rax, rax
0x18000bd03  jz      short loc_18000BD48
0x18000bd05  mov     [rsp+170h+ppOutput], r13
0x18000bd0a  mov     rcx, [rax]
0x18000bd0d  mov     rax, [rcx]
0x18000bd10  lea     r8, [rsp+170h+ppOutput]
0x18000bd15  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x18000bd1c  mov     rcx, r9
0x18000bd1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd24  mov     ebx, eax
0x18000bd26  test    eax, eax
0x18000bd28  js      loc_18000C68F
0x18000bd2e  mov     r12, [rsp+170h+ppOutput]
0x18000bd33  mov     [rsp+170h+var_120], r12
0x18000bd38  mov     [rsp+170h+var_140], r12
0x18000bd3d  mov     rcx, r12
0x18000bd40  test    ebx, ebx
0x18000bd42  js      loc_18000C6AE
0x18000bd48  mov     eax, [rsp+170h+var_130]
0x18000bd4c  mov     dword ptr [rsp+170h+var_110], eax
0x18000bd50  mov     [rsp+170h+pOutputStream], rcx
0x18000bd55  test    rcx, rcx
0x18000bd58  jz      short loc_18000BD67
0x18000bd5a  mov     rax, [rcx]
0x18000bd5d  mov     rax, [rax+8]
0x18000bd61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd66  nop
0x18000bd67  mov     [rsp+170h+var_100], r13
0x18000bd6c  mov     [rbp+70h+var_78], r13d
0x18000bd70  cmp     qword ptr [r15+8], 0
0x18000bd75  jz      loc_18000C6C2
0x18000bd7b  mov     [rsp+170h+ppvObject], r13
0x18000bd80  xor     r8d, r8d; pMalloc
0x18000bd83  lea     rdx, [rsp+170h+ppvObject]; ppvObject
0x18000bd88  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x18000bd8f  call    cs:__imp_CreateXmlWriter
0x18000bd96  nop     dword ptr [rax+rax+00h]
0x18000bd9b  mov     ebx, eax
0x18000bd9d  test    eax, eax
0x18000bd9f  js      loc_18000BFA5
0x18000bda5  mov     rcx, [rsp+170h+ppvObject]
0x18000bdaa  mov     rbx, [rsp+170h+var_100]
0x18000bdaf  cmp     rbx, rcx
0x18000bdb2  jz      short loc_18000BDD8
0x18000bdb4  mov     [rsp+170h+var_100], rcx
0x18000bdb9  test    rcx, rcx
0x18000bdbc  jz      short loc_18000BDCF
0x18000bdbe  mov     rax, [rcx]
0x18000bdc1  mov     rax, [rax+8]
0x18000bdc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdca  mov     rcx, [rsp+170h+ppvObject]
0x18000bdcf  test    rbx, rbx
0x18000bdd2  jnz     loc_18000C6E1
0x18000bdd8  mov     rax, [rcx]
0x18000bddb  mov     rax, [rax+10h]
0x18000bddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bde4  mov     [rsp+170h+ppOutput], r13
0x18000bde9  lea     r9, [rsp+170h+ppOutput]; ppOutput
0x18000bdee  lea     r8, pwszEncodingName; "UTF-16"
0x18000bdf5  xor     edx, edx; pMalloc
0x18000bdf7  mov     rcx, [rsp+170h+pOutputStream]; pOutputStream
0x18000bdfc  call    cs:__imp_CreateXmlWriterOutputWithEncodingName
0x18000be03  nop     dword ptr [rax+rax+00h]
0x18000be08  mov     ebx, eax
0x18000be0a  test    eax, eax
0x18000be0c  js      loc_18000BFA5
0x18000be12  mov     rcx, [rsp+170h+var_100]
0x18000be17  test    rcx, rcx
0x18000be1a  jz      loc_18000C6FA
0x18000be20  mov     rax, [rcx]
0x18000be23  mov     rdx, [rsp+170h+ppOutput]
0x18000be28  mov     rax, [rax+18h]
0x18000be2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be31  mov     ebx, eax
0x18000be33  mov     rcx, [rsp+170h+ppOutput]
0x18000be38  mov     rax, [rcx]
0x18000be3b  mov     rax, [rax+10h]
0x18000be3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be44  test    ebx, ebx
0x18000be46  js      loc_18000C13B
0x18000be4c  mov     rcx, [rsp+170h+var_100]
0x18000be51  test    rcx, rcx
0x18000be54  jz      loc_18000C705
0x18000be5a  mov     rax, [rcx]
0x18000be5d  mov     edx, 1
0x18000be62  mov     r8d, edx
0x18000be65  mov     rax, [rax+28h]
0x18000be69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be6e  mov     ebx, eax
0x18000be70  test    eax, eax
0x18000be72  js      loc_18000BFA5
0x18000be78  mov     rcx, [rsp+170h+var_100]
0x18000be7d  test    rcx, rcx
0x18000be80  jz      loc_18000C710
0x18000be86  mov     rax, [rcx]
0x18000be89  xor     edx, edx
0x18000be8b  mov     rax, [rax+0D0h]
0x18000be92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be97  mov     ebx, eax
0x18000be99  test    eax, eax
0x18000be9b  js      loc_18000BFA5
0x18000bea1  mov     r10, [rsp+170h+var_100]
0x18000bea6  test    r10, r10
0x18000bea9  jz      loc_18000C71B
0x18000beaf  mov     rax, [r10]
0x18000beb2  mov     r11, [rax+0D8h]
0x18000beb9  mov     edx, dword ptr [rsp+170h+var_110]
0x18000bebd  cmp     edx, 10006h
0x18000bec3  jnz     loc_18000C1C7
0x18000bec9  lea     r8, __ImageBase
0x18000bed0  movzx   ecx, dx; jumptable 000000018000C1EA cases 65538-65541
0x18000bed3  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r8+rcx*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x18000bedb  sub     r8, 0FFFFFFFFFFFFFF80h
0x18000bedf  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x18000bee6  mov     r8, [r8+8]
0x18000beea  lea     rdx, ChannelPath
0x18000bef1  mov     rcx, r10
0x18000bef4  mov     rax, r11
0x18000bef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000befc  mov     ebx, eax
0x18000befe  test    eax, eax
0x18000bf00  js      loc_18000BFA5
0x18000bf06  test    r14d, r14d
0x18000bf09  jz      loc_18000BFAD
0x18000bf0f  mov     r9d, dword ptr [rsp+170h+var_110]
0x18000bf14  movzx   eax, r9w
0x18000bf18  shr     r9d, 10h
0x18000bf1c  mov     dword ptr [rsp+170h+var_150], eax
0x18000bf20  lea     r8, aDD; "%d.%d"
0x18000bf27  mov     edx, 16h; unsigned __int64
0x18000bf2c  lea     rcx, [rbp+70h+pExceptionObject]; unsigned __int16 *
0x18000bf30  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000bf35  mov     ebx, eax
0x18000bf37  test    eax, eax
0x18000bf39  js      short loc_18000BFA5
0x18000bf3b  mov     r10, [rsp+170h+var_100]
0x18000bf40  test    r10, r10
0x18000bf43  jz      loc_18000C732
0x18000bf49  mov     rax, [r10]
0x18000bf4c  mov     r11, [rax+38h]
0x18000bf50  mov     edx, dword ptr [rsp+170h+var_110]
0x18000bf54  cmp     edx, 10006h
0x18000bf5a  jnz     loc_18000C28F
0x18000bf60  lea     r8, __ImageBase
0x18000bf67  movzx   ecx, dx; jumptable 000000018000C2B2 cases 65538-65541
0x18000bf6a  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r8+rcx*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x18000bf72  add     r8, 100h
0x18000bf79  lea     rax, [rbp+70h+pExceptionObject]
0x18000bf7d  mov     [rsp+170h+var_150], rax
0x18000bf82  xor     r9d, r9d
0x18000bf85  mov     r8, [r8+8]
0x18000bf89  lea     rdx, ChannelPath
0x18000bf90  mov     rcx, r10
0x18000bf93  mov     rax, r11
0x18000bf96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf9b  mov     ebx, eax
0x18000bf9d  test    eax, eax
0x18000bf9f  jns     loc_18000C186
0x18000bfa5  test    ebx, ebx
0x18000bfa7  js      loc_18000C13B
0x18000bfad  lea     rdx, [rsp+170h+var_110]; struct TaskXmlWriter *
0x18000bfb2  mov     rcx, [rdi+20h]; this
0x18000bfb6  call    ?WriteRegistrationXml@JobBucket@@QEBAJPEAVTaskXmlWriter@@PEAUSchema@@@Z; JobBucket::WriteRegistrationXml(TaskXmlWriter *,Schema *)
0x18000bfbb  mov     ebx, eax
0x18000bfbd  test    eax, eax
0x18000bfbf  js      loc_18000C754
0x18000bfc5  lea     rdx, [rsp+170h+var_110]; struct TaskXmlWriter *
0x18000bfca  mov     rcx, [rdi+20h]; this
0x18000bfce  call    ?WritePrincipalXml@JobBucket@@QEBAJPEAVTaskXmlWriter@@PEAUSchema@@@Z; JobBucket::WritePrincipalXml(TaskXmlWriter *,Schema *)
0x18000bfd3  mov     ebx, eax
0x18000bfd5  test    eax, eax
0x18000bfd7  js      loc_18000C754
0x18000bfdd  lea     r8, [rsp+170h+var_130]; struct Schema *
0x18000bfe2  lea     rdx, [rsp+170h+var_110]; struct TaskXmlWriter *
0x18000bfe7  mov     rcx, [rdi+20h]; this
0x18000bfeb  call    ?WriteSettingsXml@JobBucket@@QEBAJPEAVTaskXmlWriter@@PEAUSchema@@@Z; JobBucket::WriteSettingsXml(TaskXmlWriter *,Schema *)
0x18000bff0  mov     ebx, eax
0x18000bff2  test    eax, eax
0x18000bff4  js      loc_18000C754
0x18000bffa  mov     rax, [rdi+20h]
0x18000bffe  mov     rcx, [rax+0A8h]
0x18000c005  test    rcx, rcx
0x18000c008  jz      short loc_18000C02B
0x18000c00a  mov     r8, [rcx]
0x18000c00d  test    r8, r8
0x18000c010  jz      short loc_18000C02B
0x18000c012  mov     edx, 60h ; '`'
0x18000c017  lea     rcx, [rsp+170h+var_110]
0x18000c01c  call    ?ElementCData@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::ElementCData(TaskXmlNodeId,ushort const *)
0x18000c021  mov     ebx, eax
0x18000c023  test    eax, eax
0x18000c025  js      loc_18000C754
0x18000c02b  mov     eax, [rbp+70h+var_78]
0x18000c02e  test    eax, eax
0x18000c030  jnz     loc_18000C770
0x18000c036  mov     edx, dword ptr [rsp+170h+var_110]; struct IErrorInfo *
0x18000c03a  cmp     edx, 10006h
0x18000c040  jnz     loc_18000C22B
0x18000c046  lea     r8, __ImageBase
0x18000c04d  movzx   eax, dx; jumptable 000000018000C24E cases 65538-65541
0x18000c050  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r8+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x18000c058  add     r8, 600h
0x18000c05f  mov     eax, [r8]
0x18000c062  test    eax, eax
0x18000c064  jz      loc_18000C786
0x18000c06a  mov     rcx, [rsp+170h+var_100]
0x18000c06f  test    rcx, rcx
0x18000c072  jz      loc_18000C792
0x18000c078  mov     rax, [rcx]
0x18000c07b  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x18000c082  mov     r8, [r8+8]
0x18000c086  lea     rdx, ChannelPath
0x18000c08d  mov     rax, [rax+0D8h]
0x18000c094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c099  mov     edi, eax
0x18000c09b  test    eax, eax
0x18000c09d  js      short loc_18000C0DB
0x18000c09f  mov     rbx, [rsi+20h]
0x18000c0a3  mov     rbx, [rbx]
0x18000c0a6  cmp     rbx, [rsi+20h]
0x18000c0aa  jnz     short loc_18000C11A
0x18000c0ac  mov     eax, [rbp+70h+var_78]
0x18000c0af  test    eax, eax
0x18000c0b1  jnz     loc_18000C79D
0x18000c0b7  mov     rcx, [rsp+170h+var_100]
0x18000c0bc  test    rcx, rcx
0x18000c0bf  jz      loc_18000C7A7
0x18000c0c5  mov     rax, [rcx]
0x18000c0c8  mov     rax, [rax+78h]
0x18000c0cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0d1  mov     edi, eax
0x18000c0d3  test    eax, eax
0x18000c0d5  jns     loc_18000C5A6
0x18000c0db  lea     rcx, [rsp+170h+var_110]; this
0x18000c0e0  call    ??1TaskXmlWriter@@QEAA@XZ; TaskXmlWriter::~TaskXmlWriter(void)
0x18000c0e5  nop
0x18000c0e6  lea     rcx, [rsp+170h+var_140]
0x18000c0eb  call    ??1?$CComPtrBase@UIStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(void)
0x18000c0f0  mov     eax, edi
0x18000c0f2  mov     rcx, [rbp+70h+var_38]
0x18000c0f6  xor     rcx, rsp; StackCookie
0x18000c0f9  call    __security_check_cookie
0x18000c0fe  mov     rbx, [rsp+170h+arg_0]
0x18000c106  add     rsp, 140h
0x18000c10d  pop     r15
0x18000c10f  pop     r14
0x18000c111  pop     r13
0x18000c113  pop     r12
0x18000c115  pop     rdi
0x18000c116  pop     rsi
0x18000c117  pop     rbp
0x18000c118  retn
0x18000c11a  mov     rcx, [rbx+10h]
0x18000c11e  mov     rax, [rcx]
0x18000c121  lea     rdx, [rsp+170h+var_110]
0x18000c126  mov     rax, [rax+28h]
0x18000c12a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c12f  mov     edi, eax
0x18000c131  test    eax, eax
  ... truncated ...
```
