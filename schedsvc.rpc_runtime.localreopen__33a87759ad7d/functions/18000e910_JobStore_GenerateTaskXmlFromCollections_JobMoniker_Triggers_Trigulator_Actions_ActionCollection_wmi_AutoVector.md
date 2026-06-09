# JobStore::GenerateTaskXmlFromCollections(JobMoniker &,Triggers::Trigulator &,Actions::ActionCollection &,wmi::AutoVectorPtr<ushort> &)

- ea: `0x18000e910`
- end: `0x18000f574`
- name: `?GenerateTaskXmlFromCollections@JobStore@@QEAAJAEAVJobMoniker@@AEAVTrigulator@Triggers@@AEAVActionCollection@Actions@@AEAV?$AutoVectorPtr@G@wmi@@@Z`
- size: `3172`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000c3c0`
- `0x1800213f8`
- `0x180045df0`
- `0x18004d868`
- `0x18006c840`

## callees

- `0x180001f60`
- `0x180008010`
- `0x18000dc30`
- `0x18000e910`
- `0x18000fa4c`
- `0x18000fa70`
- `0x180010790`
- `0x1800123e0`
- `0x180015740`
- `0x180016abc`
- `0x18001b070`
- `0x180042f60`
- `0x180052118`
- `0x18005790c`
- `0x18007e6d0`
- `0x180084010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000f005`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000f005`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f01f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f08f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f0b6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f442`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f01f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f08f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f0b6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f442`
- `OLEAUT32!__imp_SysStringLen` at `0x18000f101`
- `OLEAUT32!__imp_SysStringLen` at `0x18000f101`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f28c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f28c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e978`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f0cb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f129`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e978`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f0cb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f129`
- `XmlLite!CreateXmlWriter` at `0x18000ea39`
- `XmlLite!CreateXmlWriter` at `0x18000ea39`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x18000eaa0`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x18000eaa0`

## string_xrefs

- `0x18000ee43`: `xmlns`

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
    v78 = &qword_1800A4718;
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
            v26 = (const struct SchemaEntry * near *)&qword_18009D560;
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
                v28 = (const struct SchemaEntry * near *)&qword_18009D560;
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
      v34 = (const struct SchemaEntry * near *)&qword_18009D560;
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
    v78 = &qword_1800A4718;
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
      v78 = &qword_1800A4718;
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
0x18000e910  mov     [rsp-8+arg_0], rbx
0x18000e915  push    rbp
0x18000e916  push    rsi
0x18000e917  push    rdi
0x18000e918  push    r12
0x18000e91a  push    r13
0x18000e91c  push    r14
0x18000e91e  push    r15
0x18000e920  lea     rbp, [rsp-40h]
0x18000e925  sub     rsp, 140h
0x18000e92c  mov     rax, cs:__security_cookie
0x18000e933  xor     rax, rsp
0x18000e936  mov     [rbp+70h+var_38], rax
0x18000e93a  mov     r15, r9
0x18000e93d  mov     rsi, r8
0x18000e940  mov     rdi, rdx
0x18000e943  mov     rax, [rbp+70h+arg_20]
0x18000e94a  mov     [rsp+170h+var_118], rax
0x18000e94f  mov     rax, [rdx+20h]
0x18000e953  mov     r14d, [rax+60h]
0x18000e957  mov     eax, r14d
0x18000e95a  mov     ecx, 10006h
0x18000e95f  test    r14d, r14d
0x18000e962  cmovz   eax, ecx
0x18000e965  mov     [rsp+170h+var_130], eax
0x18000e969  xor     edx, edx; dwFlags
0x18000e96b  mov     r8d, 28h ; '('; dwBytes
0x18000e971  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18000e978  call    cs:__imp_HeapAlloc
0x18000e97e  test    rax, rax
0x18000e981  jz      loc_18000F2A4
0x18000e987  mov     [rsp+170h+ppOutput], rax
0x18000e98c  mov     rcx, rax; this
0x18000e98f  call    ??0CBstrWriter@@QEAA@XZ; CBstrWriter::CBstrWriter(void)
0x18000e994  mov     r9, rax
0x18000e997  xor     r13d, r13d
0x18000e99a  mov     r12d, r13d
0x18000e99d  mov     [rsp+170h+var_120], r13
0x18000e9a2  mov     [rsp+170h+var_140], r13
0x18000e9a7  mov     ecx, r13d
0x18000e9aa  test    rax, rax
0x18000e9ad  jz      short loc_18000E9F2
0x18000e9af  mov     [rsp+170h+ppOutput], r13
0x18000e9b4  mov     rcx, [rax]
0x18000e9b7  mov     rax, [rcx]
0x18000e9ba  lea     r8, [rsp+170h+ppOutput]
0x18000e9bf  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x18000e9c6  mov     rcx, r9
0x18000e9c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9ce  mov     ebx, eax
0x18000e9d0  test    eax, eax
0x18000e9d2  js      loc_18000F2E9
0x18000e9d8  mov     r12, [rsp+170h+ppOutput]
0x18000e9dd  mov     [rsp+170h+var_120], r12
0x18000e9e2  mov     [rsp+170h+var_140], r12
0x18000e9e7  mov     rcx, r12
0x18000e9ea  test    ebx, ebx
0x18000e9ec  js      loc_18000F308
0x18000e9f2  mov     eax, [rsp+170h+var_130]
0x18000e9f6  mov     dword ptr [rsp+170h+var_110], eax
0x18000e9fa  mov     [rsp+170h+pOutputStream], rcx
0x18000e9ff  test    rcx, rcx
0x18000ea02  jz      short loc_18000EA11
0x18000ea04  mov     rax, [rcx]
0x18000ea07  mov     rax, [rax+8]
0x18000ea0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea10  nop
0x18000ea11  mov     [rsp+170h+var_100], r13
0x18000ea16  mov     [rbp+70h+var_78], r13d
0x18000ea1a  cmp     qword ptr [r15+8], 0
0x18000ea1f  jz      loc_18000F31C
0x18000ea25  mov     [rsp+170h+ppvObject], r13
0x18000ea2a  xor     r8d, r8d; pMalloc
0x18000ea2d  lea     rdx, [rsp+170h+ppvObject]; ppvObject
0x18000ea32  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x18000ea39  call    cs:__imp_CreateXmlWriter
0x18000ea3f  mov     ebx, eax
0x18000ea41  test    eax, eax
0x18000ea43  js      loc_18000EC43
0x18000ea49  mov     rcx, [rsp+170h+ppvObject]
0x18000ea4e  mov     rbx, [rsp+170h+var_100]
0x18000ea53  cmp     rbx, rcx
0x18000ea56  jz      short loc_18000EA7C
0x18000ea58  mov     [rsp+170h+var_100], rcx
0x18000ea5d  test    rcx, rcx
0x18000ea60  jz      short loc_18000EA73
0x18000ea62  mov     rax, [rcx]
0x18000ea65  mov     rax, [rax+8]
0x18000ea69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea6e  mov     rcx, [rsp+170h+ppvObject]
0x18000ea73  test    rbx, rbx
0x18000ea76  jnz     loc_18000F33B
0x18000ea7c  mov     rax, [rcx]
0x18000ea7f  mov     rax, [rax+10h]
0x18000ea83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea88  mov     [rsp+170h+ppOutput], r13
0x18000ea8d  lea     r9, [rsp+170h+ppOutput]; ppOutput
0x18000ea92  lea     r8, pwszEncodingName; "UTF-16"
0x18000ea99  xor     edx, edx; pMalloc
0x18000ea9b  mov     rcx, [rsp+170h+pOutputStream]; pOutputStream
0x18000eaa0  call    cs:__imp_CreateXmlWriterOutputWithEncodingName
0x18000eaa6  mov     ebx, eax
0x18000eaa8  test    eax, eax
0x18000eaaa  js      loc_18000EC43
0x18000eab0  mov     rcx, [rsp+170h+var_100]
0x18000eab5  test    rcx, rcx
0x18000eab8  jz      loc_18000F354
0x18000eabe  mov     rax, [rcx]
0x18000eac1  mov     rdx, [rsp+170h+ppOutput]
0x18000eac6  mov     rax, [rax+18h]
0x18000eaca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eacf  mov     ebx, eax
0x18000ead1  mov     rcx, [rsp+170h+ppOutput]
0x18000ead6  mov     rax, [rcx]
0x18000ead9  mov     rax, [rax+10h]
0x18000eadd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eae2  test    ebx, ebx
0x18000eae4  js      loc_18000EDD8
0x18000eaea  mov     rcx, [rsp+170h+var_100]
0x18000eaef  test    rcx, rcx
0x18000eaf2  jz      loc_18000F35F
0x18000eaf8  mov     rax, [rcx]
0x18000eafb  mov     edx, 1
0x18000eb00  mov     r8d, edx
0x18000eb03  mov     rax, [rax+28h]
0x18000eb07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb0c  mov     ebx, eax
0x18000eb0e  test    eax, eax
0x18000eb10  js      loc_18000EC43
0x18000eb16  mov     rcx, [rsp+170h+var_100]
0x18000eb1b  test    rcx, rcx
0x18000eb1e  jz      loc_18000F36A
0x18000eb24  mov     rax, [rcx]
0x18000eb27  xor     edx, edx
0x18000eb29  mov     rax, [rax+0D0h]
0x18000eb30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb35  mov     ebx, eax
0x18000eb37  test    eax, eax
0x18000eb39  js      loc_18000EC43
0x18000eb3f  mov     r10, [rsp+170h+var_100]
0x18000eb44  test    r10, r10
0x18000eb47  jz      loc_18000F375
0x18000eb4d  mov     rax, [r10]
0x18000eb50  mov     r11, [rax+0D8h]
0x18000eb57  mov     edx, dword ptr [rsp+170h+var_110]
0x18000eb5b  cmp     edx, 10006h
0x18000eb61  jnz     loc_18000EE64
0x18000eb67  lea     r8, __ImageBase
0x18000eb6e  movzx   ecx, dx; jumptable 000000018000EE87 cases 65538-65541
0x18000eb71  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r8+rcx*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x18000eb79  sub     r8, 0FFFFFFFFFFFFFF80h
0x18000eb7d  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x18000eb84  mov     r8, [r8+8]
0x18000eb88  lea     rdx, ChannelPath
0x18000eb8f  mov     rcx, r10
0x18000eb92  mov     rax, r11
0x18000eb95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb9a  mov     ebx, eax
0x18000eb9c  test    eax, eax
0x18000eb9e  js      loc_18000EC43
0x18000eba4  test    r14d, r14d
0x18000eba7  jz      loc_18000EC4B
0x18000ebad  mov     r9d, dword ptr [rsp+170h+var_110]
0x18000ebb2  movzx   eax, r9w
0x18000ebb6  shr     r9d, 10h
0x18000ebba  mov     dword ptr [rsp+170h+var_150], eax
0x18000ebbe  lea     r8, aDD; "%d.%d"
0x18000ebc5  mov     edx, 16h; unsigned __int64
0x18000ebca  lea     rcx, [rbp+70h+pExceptionObject]; unsigned __int16 *
0x18000ebce  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ebd3  mov     ebx, eax
0x18000ebd5  test    eax, eax
0x18000ebd7  js      short loc_18000EC43
0x18000ebd9  mov     r10, [rsp+170h+var_100]
0x18000ebde  test    r10, r10
0x18000ebe1  jz      loc_18000F38C
0x18000ebe7  mov     rax, [r10]
0x18000ebea  mov     r11, [rax+38h]
0x18000ebee  mov     edx, dword ptr [rsp+170h+var_110]
0x18000ebf2  cmp     edx, 10006h
0x18000ebf8  jnz     loc_18000EF24
0x18000ebfe  lea     r8, __ImageBase
0x18000ec05  movzx   ecx, dx; jumptable 000000018000EF47 cases 65538-65541
0x18000ec08  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r8+rcx*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x18000ec10  add     r8, 100h
0x18000ec17  lea     rax, [rbp+70h+pExceptionObject]
0x18000ec1b  mov     [rsp+170h+var_150], rax
0x18000ec20  xor     r9d, r9d
0x18000ec23  mov     r8, [r8+8]
0x18000ec27  lea     rdx, ChannelPath
0x18000ec2e  mov     rcx, r10
0x18000ec31  mov     rax, r11
0x18000ec34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec39  mov     ebx, eax
0x18000ec3b  test    eax, eax
0x18000ec3d  jns     loc_18000EE23
0x18000ec43  test    ebx, ebx
0x18000ec45  js      loc_18000EDD8
0x18000ec4b  lea     rdx, [rsp+170h+var_110]; struct TaskXmlWriter *
0x18000ec50  mov     rcx, [rdi+20h]; this
0x18000ec54  call    ?WriteRegistrationXml@JobBucket@@QEBAJPEAVTaskXmlWriter@@PEAUSchema@@@Z; JobBucket::WriteRegistrationXml(TaskXmlWriter *,Schema *)
0x18000ec59  mov     ebx, eax
0x18000ec5b  test    eax, eax
0x18000ec5d  js      loc_18000F3AE
0x18000ec63  lea     rdx, [rsp+170h+var_110]; struct TaskXmlWriter *
0x18000ec68  mov     rcx, [rdi+20h]; this
0x18000ec6c  call    ?WritePrincipalXml@JobBucket@@QEBAJPEAVTaskXmlWriter@@PEAUSchema@@@Z; JobBucket::WritePrincipalXml(TaskXmlWriter *,Schema *)
0x18000ec71  mov     ebx, eax
0x18000ec73  test    eax, eax
0x18000ec75  js      loc_18000F3AE
0x18000ec7b  lea     r8, [rsp+170h+var_130]; struct Schema *
0x18000ec80  lea     rdx, [rsp+170h+var_110]; struct TaskXmlWriter *
0x18000ec85  mov     rcx, [rdi+20h]; this
0x18000ec89  call    ?WriteSettingsXml@JobBucket@@QEBAJPEAVTaskXmlWriter@@PEAUSchema@@@Z; JobBucket::WriteSettingsXml(TaskXmlWriter *,Schema *)
0x18000ec8e  mov     ebx, eax
0x18000ec90  test    eax, eax
0x18000ec92  js      loc_18000F3AE
0x18000ec98  mov     rax, [rdi+20h]
0x18000ec9c  mov     rcx, [rax+0A8h]
0x18000eca3  test    rcx, rcx
0x18000eca6  jz      short loc_18000ECC9
0x18000eca8  mov     r8, [rcx]
0x18000ecab  test    r8, r8
0x18000ecae  jz      short loc_18000ECC9
0x18000ecb0  mov     edx, 60h ; '`'
0x18000ecb5  lea     rcx, [rsp+170h+var_110]
0x18000ecba  call    ?ElementCData@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::ElementCData(TaskXmlNodeId,ushort const *)
0x18000ecbf  mov     ebx, eax
0x18000ecc1  test    eax, eax
0x18000ecc3  js      loc_18000F3AE
0x18000ecc9  mov     eax, [rbp+70h+var_78]
0x18000eccc  test    eax, eax
0x18000ecce  jnz     loc_18000F3CA
0x18000ecd4  mov     edx, dword ptr [rsp+170h+var_110]; struct IErrorInfo *
0x18000ecd8  cmp     edx, 10006h
0x18000ecde  jnz     loc_18000EEC4
0x18000ece4  lea     r8, __ImageBase
0x18000eceb  movzx   eax, dx; jumptable 000000018000EEE7 cases 65538-65541
0x18000ecee  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r8+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x18000ecf6  add     r8, 600h
0x18000ecfd  mov     eax, [r8]
0x18000ed00  test    eax, eax
0x18000ed02  jz      loc_18000F3E0
0x18000ed08  mov     rcx, [rsp+170h+var_100]
0x18000ed0d  test    rcx, rcx
0x18000ed10  jz      loc_18000F3EC
0x18000ed16  mov     rax, [rcx]
0x18000ed19  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x18000ed20  mov     r8, [r8+8]
0x18000ed24  lea     rdx, ChannelPath
0x18000ed2b  mov     rax, [rax+0D8h]
0x18000ed32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed37  mov     edi, eax
0x18000ed39  test    eax, eax
0x18000ed3b  js      short loc_18000ED79
0x18000ed3d  mov     rbx, [rsi+20h]
0x18000ed41  mov     rbx, [rbx]
0x18000ed44  cmp     rbx, [rsi+20h]
0x18000ed48  jnz     short loc_18000EDB7
0x18000ed4a  mov     eax, [rbp+70h+var_78]
0x18000ed4d  test    eax, eax
0x18000ed4f  jnz     loc_18000F3F7
0x18000ed55  mov     rcx, [rsp+170h+var_100]
0x18000ed5a  test    rcx, rcx
0x18000ed5d  jz      loc_18000F401
0x18000ed63  mov     rax, [rcx]
0x18000ed66  mov     rax, [rax+78h]
0x18000ed6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed6f  mov     edi, eax
0x18000ed71  test    eax, eax
0x18000ed73  jns     loc_18000F206
0x18000ed79  lea     rcx, [rsp+170h+var_110]; this
0x18000ed7e  call    ??1TaskXmlWriter@@QEAA@XZ; TaskXmlWriter::~TaskXmlWriter(void)
0x18000ed83  nop
0x18000ed84  lea     rcx, [rsp+170h+var_140]
0x18000ed89  call    ??1?$CComPtrBase@UIStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(void)
0x18000ed8e  mov     eax, edi
0x18000ed90  mov     rcx, [rbp+70h+var_38]
0x18000ed94  xor     rcx, rsp; StackCookie
0x18000ed97  call    __security_check_cookie
0x18000ed9c  mov     rbx, [rsp+170h+arg_0]
0x18000eda4  add     rsp, 140h
0x18000edab  pop     r15
0x18000edad  pop     r14
0x18000edaf  pop     r13
0x18000edb1  pop     r12
0x18000edb3  pop     rdi
0x18000edb4  pop     rsi
0x18000edb5  pop     rbp
0x18000edb6  retn
0x18000edb7  mov     rcx, [rbx+10h]
0x18000edbb  mov     rax, [rcx]
0x18000edbe  lea     rdx, [rsp+170h+var_110]
0x18000edc3  mov     rax, [rax+28h]
0x18000edc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edcc  mov     edi, eax
0x18000edce  test    eax, eax
0x18000edd0  jns     loc_18000ED41
0x18000edd6  jmp     short loc_18000ED79
0x18000edd8  mov     rcx, [rsp+170h+var_100]
  ... truncated ...
```
