# CRepository::BuildClassHierarchy(IWmiDbSession *,IWmiDbHandle *,ushort const *,long,std::unique_ptr<CDynasty,std::default_delete<CDynasty>> &)

- ea: `0x18008af38`
- end: `0x18008b6c7`
- name: `?BuildClassHierarchy@CRepository@@SAJPEAUIWmiDbSession@@PEAUIWmiDbHandle@@PEBGJAEAV?$unique_ptr@VCDynasty@@U?$default_delete@VCDynasty@@@std@@@std@@@Z`
- size: `1935`
- prototype: `__int64 __usercall@<rax>(struct IWmiDbSession *@<rcx>, struct IWmiDbHandle *@<rdx>, unsigned __int16 *@<r8>, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18009c6e4`

## callees

- `0x18000ad74`
- `0x18000b140`
- `0x18000e950`
- `0x18000ebd0`
- `0x180019020`
- `0x18003cdb8`
- `0x18003cfe0`
- `0x180050314`
- `0x180056620`
- `0x18005d98c`
- `0x180065990`
- `0x18008af38`
- `0x18008d51c`
- `0x1800da010`

## import_xrefs

- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18008b111`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18008b111`
- `wbemcomn!??0CFlexQueue@@QEAA@H@Z` at `0x18008b1c0`
- `wbemcomn!??0CFlexQueue@@QEAA@H@Z` at `0x18008b1c0`
- `wbemcomn!??1CFlexQueue@@QEAA@XZ` at `0x18008b23e`
- `wbemcomn!??1CFlexQueue@@QEAA@XZ` at `0x18008b3e7`
- `wbemcomn!??1CFlexQueue@@QEAA@XZ` at `0x18008b23e`
- `wbemcomn!??1CFlexQueue@@QEAA@XZ` at `0x18008b3e7`
- `wbemcomn!?Enqueue@CFlexQueue@@QEAA_NPEAX@Z` at `0x18008b24e`
- `wbemcomn!?Enqueue@CFlexQueue@@QEAA_NPEAX@Z` at `0x18008b365`
- `wbemcomn!?Enqueue@CFlexQueue@@QEAA_NPEAX@Z` at `0x18008b24e`
- `wbemcomn!?Enqueue@CFlexQueue@@QEAA_NPEAX@Z` at `0x18008b365`
- `wbemcomn!?Dequeue@CFlexQueue@@QEAAPEAXXZ` at `0x18008b269`
- `wbemcomn!?Dequeue@CFlexQueue@@QEAAPEAXXZ` at `0x18008b269`
- `wbemcomn!??0WString2@@QEAA@PEBG@Z` at `0x18008afb9`
- `wbemcomn!??0WString2@@QEAA@PEBG@Z` at `0x18008afb9`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18008b660`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18008b660`
- `wbemcomn!??YWString2@@QEAAAEAV0@PEBG@Z` at `0x18008afc7`
- `wbemcomn!??YWString2@@QEAAAEAV0@PEBG@Z` at `0x18008afd8`
- `wbemcomn!??YWString2@@QEAAAEAV0@PEBG@Z` at `0x18008afc7`
- `wbemcomn!??YWString2@@QEAAAEAV0@PEBG@Z` at `0x18008afd8`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x18008b184`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x18008b184`
- `wbemcomn!??0CFlexArray@@QEAA@HH@Z` at `0x18008b0f5`
- `wbemcomn!??0CFlexArray@@QEAA@HH@Z` at `0x18008b0f5`
- `wbemcomn!??1CFlexArray@@QEAA@XZ` at `0x18008b3f2`
- `wbemcomn!??1CFlexArray@@QEAA@XZ` at `0x18008b637`
- `wbemcomn!??1CFlexArray@@QEAA@XZ` at `0x18008b646`
- `wbemcomn!??1CFlexArray@@QEAA@XZ` at `0x18008b3f2`
- `wbemcomn!??1CFlexArray@@QEAA@XZ` at `0x18008b637`
- `wbemcomn!??1CFlexArray@@QEAA@XZ` at `0x18008b646`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x18008b2d9`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x18008b2d9`
- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x18008b378`
- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x18008b378`
- `wbemcomn!GetMemLogObject` at `0x18008afed`
- `wbemcomn!GetMemLogObject` at `0x18008b076`
- `wbemcomn!GetMemLogObject` at `0x18008b1e9`
- `wbemcomn!GetMemLogObject` at `0x18008b40b`
- `wbemcomn!GetMemLogObject` at `0x18008b45e`
- `wbemcomn!GetMemLogObject` at `0x18008b4b5`
- `wbemcomn!GetMemLogObject` at `0x18008b4f7`
- `wbemcomn!GetMemLogObject` at `0x18008b54f`
- `wbemcomn!GetMemLogObject` at `0x18008b59d`
- `wbemcomn!GetMemLogObject` at `0x18008b5df`
- `wbemcomn!GetMemLogObject` at `0x18008b668`
- `wbemcomn!GetMemLogObject` at `0x18008afed`
- `wbemcomn!GetMemLogObject` at `0x18008b076`
- `wbemcomn!GetMemLogObject` at `0x18008b1e9`
- `wbemcomn!GetMemLogObject` at `0x18008b40b`
- `wbemcomn!GetMemLogObject` at `0x18008b45e`
- `wbemcomn!GetMemLogObject` at `0x18008b4b5`
- `wbemcomn!GetMemLogObject` at `0x18008b4f7`
- `wbemcomn!GetMemLogObject` at `0x18008b54f`
- `wbemcomn!GetMemLogObject` at `0x18008b59d`
- `wbemcomn!GetMemLogObject` at `0x18008b5df`
- `wbemcomn!GetMemLogObject` at `0x18008b668`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008affd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008b081`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008b1f9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008b41b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008b469`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008b4c5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008b502`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008b55f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008b5ad`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008b5ea`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008b678`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008affd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008b081`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008b1f9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008b41b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008b469`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008b4c5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008b502`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008b55f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008b5ad`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008b5ea`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008b678`
- `OLEAUT32!__imp_VariantInit` at `0x18008b11f`
- `OLEAUT32!__imp_VariantInit` at `0x18008b280`
- `OLEAUT32!__imp_VariantInit` at `0x18008b2e6`
- `OLEAUT32!__imp_VariantInit` at `0x18008b11f`
- `OLEAUT32!__imp_VariantInit` at `0x18008b280`
- `OLEAUT32!__imp_VariantInit` at `0x18008b2e6`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CRepository::BuildClassHierarchy(
        struct IWmiDbSession *a1,
        struct IWmiDbHandle *a2,
        unsigned __int16 *a3,
        char a4,
        void **a5)
{
  struct CSynchronousSink *v8; // rax
  struct IWbemObjectSink *v9; // rdi
  CMemoryLog *v10; // rax
  int v11; // ebx
  CMemoryLog *v12; // rax
  CFlexArray *v13; // r12
  struct IWbemClassObject *v14; // r14
  int v15; // edi
  struct IWbemClassObject *v16; // r15
  struct CDynasty *v17; // rax
  void **v18; // rbx
  CMemoryLog *v19; // rax
  CDynasty *v20; // rsi
  unsigned int v21; // edi
  struct IWbemClassObject *v22; // r14
  struct CDynasty *v23; // rax
  struct CDynasty *v24; // rbx
  CMemoryLog *v25; // rax
  CMemoryLog *v26; // rax
  CMemoryLog *v27; // rax
  CClientCnt *v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // r9
  CMemoryLog *v31; // rax
  CMemoryLog *v32; // rax
  CClientCnt *v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // r9
  CMemoryLog *v36; // rax
  CMemoryLog *v37; // rax
  CMemoryLog *MemLogObject; // rax
  struct IWbemObjectSink *v40; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v41[24]; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG v42; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp-88h] BYREF
  VARIANTARG v44; // [rsp+90h] [rbp-70h] BYREF
  _DWORD v45[24]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v46[14]; // [rsp+110h] [rbp+10h] BYREF
  struct CDynasty *v47; // [rsp+198h] [rbp+98h] BYREF

  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qqSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, (_DWORD)a3, (_DWORD)a1, (char)a2, (__int64)a3, a4);
  }
  if ( !a2 || !a3 )
  {
    MemLogObject = GetMemLogObject();
    v11 = -2147217400;
    CMemoryLog::Write(MemLogObject, -2147217400);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids, 2147749896LL);
    }
    return (unsigned int)v11;
  }
  WString2::WString2((WString2 *)v46, L"select * from meta_class where __this isa '");
  WString2::operator+=(v46, a3);
  WString2::operator+=(v46, L"'");
  v8 = CSynchronousSink::Create(0);
  v9 = (struct IWbemObjectSink *)v8;
  if ( !v8 )
  {
    v10 = GetMemLogObject();
    v11 = -2147217402;
    CMemoryLog::Write(v10, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids, 2147749894LL);
    }
    goto LABEL_85;
  }
  (*(void (__fastcall **)(struct CSynchronousSink *))(*(_QWORD *)v8 + 8LL))(v8);
  v40 = v9;
  v11 = CRepository::ExecQuery(a1, a2, v46[0], v9, 0);
  if ( v11 < 0 )
  {
    v12 = GetMemLogObject();
    CMemoryLog::Write(v12, v11);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        87,
        WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids,
        (unsigned int)v11);
    }
LABEL_17:
    CReleaseMe::release((CReleaseMe *)&v40);
    goto LABEL_85;
  }
  CSynchronousSink::Block((CSynchronousSink *)v9);
  CSynchronousSink::GetStatus((CSynchronousSink *)v9, (int *)&v47, 0, 0);
  v13 = (CFlexArray *)&v9[8];
  CFlexArray::CFlexArray((CFlexArray *)v45, 8, 100);
  v14 = 0;
  v15 = 0;
  if ( *(int *)v13 <= 0 )
  {
LABEL_84:
    CFlexArray::~CFlexArray((CFlexArray *)v45);
    CReleaseMe::release((CReleaseMe *)&v40);
    v11 = -2147217406;
    goto LABEL_85;
  }
  do
  {
    v16 = (struct IWbemClassObject *)CFlexArray::GetAt(v13, v15);
    VariantInit(&pvarg);
    v11 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))v16->lpVtbl->Get)(
            v16,
            L"__CLASS",
            0,
            &pvarg,
            0,
            0);
    if ( v11 < 0 )
    {
      v37 = GetMemLogObject();
      CMemoryLog::Write(v37, v11);
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_82;
      }
      v34 = 88;
      v35 = (unsigned int)v11;
LABEL_81:
      WPP_SF_d(*((_QWORD *)v33 + 2), v34, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids, v35);
      goto LABEL_82;
    }
    if ( pvarg.vt != 8 )
    {
      v36 = GetMemLogObject();
      v11 = -2147217393;
      CMemoryLog::Write(v36, -2147217393);
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_82;
      }
      v34 = 89;
      v35 = 2147749903LL;
      goto LABEL_81;
    }
    if ( !(unsigned int)wbem_wcsicmp(pvarg.bstrVal, a3) )
    {
      v14 = v16;
      goto LABEL_24;
    }
    if ( CFlexArray::Add((CFlexArray *)v45, v16) )
    {
      v32 = GetMemLogObject();
      v11 = -2147217402;
      CMemoryLog::Write(v32, -2147217402);
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v34 = 90;
        v35 = 2147749894LL;
        goto LABEL_81;
      }
LABEL_82:
      _variant_t::~_variant_t(&pvarg);
LABEL_83:
      CFlexArray::~CFlexArray((CFlexArray *)v45);
      goto LABEL_17;
    }
LABEL_24:
    _variant_t::~_variant_t(&pvarg);
    ++v15;
  }
  while ( v15 < *(_DWORD *)v13 );
  if ( !v14 )
    goto LABEL_84;
  CFlexQueue::CFlexQueue((CFlexQueue *)v41, 1);
  v17 = CDynasty::Create(v14);
  v18 = a5;
  std::unique_ptr<CDynasty>::reset(a5, v17);
  if ( !*v18 )
  {
    v19 = GetMemLogObject();
    v11 = -2147217402;
    CMemoryLog::Write(v19, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids, 2147749894LL);
    }
LABEL_31:
    CFlexQueue::~CFlexQueue((CFlexQueue *)v41);
    goto LABEL_83;
  }
  CFlexQueue::Enqueue((CFlexQueue *)v41, *v18);
  if ( v45[0] )
  {
    while ( 1 )
    {
      v20 = (CDynasty *)CFlexQueue::Dequeue((CFlexQueue *)v41);
      if ( !v20 )
        goto LABEL_44;
      VariantInit(&v42);
      v11 = (*(__int64 (__fastcall **)(_QWORD *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(**((_QWORD **)v20 + 1) + 32LL))(
              *((_QWORD **)v20 + 1),
              L"__CLASS",
              0,
              &v42,
              0,
              0);
      if ( v11 < 0 )
        break;
      if ( v42.vt != 8 )
      {
        v27 = GetMemLogObject();
        v11 = -2147217393;
        CMemoryLog::Write(v27, -2147217393);
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v29 = 93;
          v30 = 2147749903LL;
          goto LABEL_67;
        }
        goto LABEL_68;
      }
      v21 = 0;
      if ( v45[0] > 0 )
      {
        while ( 1 )
        {
          v22 = *(struct IWbemClassObject **)CFlexArray::operator[](v45, v21);
          VariantInit(&v44);
          v11 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))v22->lpVtbl->Get)(
                  v22,
                  L"__SUPERCLASS",
                  0,
                  &v44,
                  0,
                  0);
          if ( v11 < 0 )
            break;
          if ( v44.vt == 8 && !(unsigned int)wbem_wcsicmp(v44.bstrVal, v42.bstrVal) )
          {
            v23 = CDynasty::Create(v22);
            v24 = v23;
            v47 = v23;
            if ( !v23 )
            {
              v25 = GetMemLogObject();
              v11 = -2147217402;
              CMemoryLog::Write(v25, -2147217402);
              if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  95,
                  WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids,
                  2147749894LL);
              }
              goto LABEL_58;
            }
            CDynasty::AddChild(v20, v23);
            CFlexQueue::Enqueue((CFlexQueue *)v41, v24);
            v47 = 0;
            CFlexArray::RemoveAt((CFlexArray *)v45, v21--);
          }
          _variant_t::~_variant_t(&v44);
          if ( (int)++v21 >= v45[0] )
            goto LABEL_43;
        }
        v26 = GetMemLogObject();
        CMemoryLog::Write(v26, v11);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            94,
            WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids,
            (unsigned int)v11);
        }
LABEL_58:
        _variant_t::~_variant_t(&v44);
        goto LABEL_68;
      }
LABEL_43:
      _variant_t::~_variant_t(&v42);
      if ( !v45[0] )
        goto LABEL_44;
    }
    v31 = GetMemLogObject();
    CMemoryLog::Write(v31, v11);
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v29 = 92;
      v30 = (unsigned int)v11;
LABEL_67:
      WPP_SF_d(*((_QWORD *)v28 + 2), v29, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids, v30);
    }
LABEL_68:
    _variant_t::~_variant_t(&v42);
    goto LABEL_31;
  }
LABEL_44:
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids, 0);
  }
  CFlexQueue::~CFlexQueue((CFlexQueue *)v41);
  CFlexArray::~CFlexArray((CFlexArray *)v45);
  CReleaseMe::release((CReleaseMe *)&v40);
  v11 = 0;
LABEL_85:
  WString2::~WString2((WString2 *)v46);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18008af38  push    rbp
0x18008af3a  push    rbx
0x18008af3b  push    rsi
0x18008af3c  push    rdi
0x18008af3d  push    r12
0x18008af3f  push    r13
0x18008af41  push    r14
0x18008af43  push    r15
0x18008af45  lea     rbp, [rsp-48h]
0x18008af4a  sub     rsp, 148h
0x18008af51  mov     rsi, r8
0x18008af54  mov     rbx, rdx
0x18008af57  mov     r14, rcx
0x18008af5a  lea     r15, WPP_GLOBAL_Control
0x18008af61  mov     rcx, cs:WPP_GLOBAL_Control
0x18008af68  cmp     rcx, r15
0x18008af6b  jz      short loc_18008AF99
0x18008af6d  test    byte ptr [rcx+1Ch], 1
0x18008af71  jz      short loc_18008AF99
0x18008af73  cmp     byte ptr [rcx+19h], 5
0x18008af77  jb      short loc_18008AF99
0x18008af79  mov     edx, 54h ; 'T'
0x18008af7e  mov     [rsp+180h+var_150], r9d
0x18008af83  mov     [rsp+180h+var_158], r8
0x18008af88  mov     qword ptr [rsp+180h+var_160], rbx
0x18008af8d  mov     r9, r14
0x18008af90  mov     rcx, [rcx+10h]
0x18008af94  call    WPP_SF_qqSd
0x18008af99  xor     r13d, r13d
0x18008af9c  test    rbx, rbx
0x18008af9f  jz      loc_18008B668
0x18008afa5  test    rsi, rsi
0x18008afa8  jz      loc_18008B668
0x18008afae  lea     rdx, aSelectFromMeta_0; "select * from meta_class where __this i"...
0x18008afb5  lea     rcx, [rbp+80h+var_70]
0x18008afb9  call    cs:__imp_??0WString2@@QEAA@PEBG@Z; WString2::WString2(ushort const *)
0x18008afbf  nop
0x18008afc0  mov     rdx, rsi
0x18008afc3  lea     rcx, [rbp+80h+var_70]
0x18008afc7  call    cs:__imp_??YWString2@@QEAAAEAV0@PEBG@Z; WString2::operator+=(ushort const *)
0x18008afcd  lea     rdx, asc_1800EB884; "'"
0x18008afd4  lea     rcx, [rbp+80h+var_70]
0x18008afd8  call    cs:__imp_??YWString2@@QEAAAEAV0@PEBG@Z; WString2::operator+=(ushort const *)
0x18008afde  xor     ecx, ecx; struct IWbemObjectSinkEx *
0x18008afe0  call    ?Create@CSynchronousSink@@SAPEAV1@PEAUIWbemObjectSinkEx@@@Z; CSynchronousSink::Create(IWbemObjectSinkEx *)
0x18008afe5  mov     rdi, rax
0x18008afe8  test    rax, rax
0x18008afeb  jnz     short loc_18008B045
0x18008afed  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008aff3  mov     ebx, 80041006h
0x18008aff8  mov     edx, ebx
0x18008affa  mov     rcx, rax
0x18008affd  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008b003  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b00a  cmp     rcx, r15
0x18008b00d  jz      loc_18008B65C
0x18008b013  test    byte ptr [rcx+1Ch], 1
0x18008b017  jz      loc_18008B65C
0x18008b01d  cmp     byte ptr [rcx+19h], 2
0x18008b021  jb      loc_18008B65C
0x18008b027  lea     edx, [rdi+56h]
0x18008b02a  mov     r9d, 80041006h
0x18008b030  lea     r8, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids
0x18008b037  mov     rcx, [rcx+10h]
0x18008b03b  call    WPP_SF_d
0x18008b040  jmp     loc_18008B65C
0x18008b045  mov     rax, [rax]
0x18008b048  mov     rcx, rdi
0x18008b04b  mov     rax, [rax+8]
0x18008b04f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b054  mov     [rsp+180h+var_140], rdi
0x18008b059  mov     [rsp+180h+var_160], r13d; int
0x18008b05e  mov     r9, rdi; struct IWbemObjectSink *
0x18008b061  mov     r8, [rbp+80h+var_70]; unsigned __int16 *
0x18008b065  mov     rdx, rbx; struct IWmiDbHandle *
0x18008b068  mov     rcx, r14; struct IWmiDbSession *
0x18008b06b  call    ?ExecQuery@CRepository@@SAJPEAUIWmiDbSession@@PEAUIWmiDbHandle@@PEBGPEAUIWbemObjectSink@@J@Z; CRepository::ExecQuery(IWmiDbSession *,IWmiDbHandle *,ushort const *,IWbemObjectSink *,long)
0x18008b070  mov     ebx, eax
0x18008b072  test    eax, eax
0x18008b074  jns     short loc_18008B0C7
0x18008b076  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008b07c  mov     edx, ebx
0x18008b07e  mov     rcx, rax
0x18008b081  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008b087  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b08e  cmp     rcx, r15
0x18008b091  jz      short loc_18008B0B8
0x18008b093  test    byte ptr [rcx+1Ch], 1
0x18008b097  jz      short loc_18008B0B8
0x18008b099  cmp     byte ptr [rcx+19h], 2
0x18008b09d  jb      short loc_18008B0B8
0x18008b09f  mov     edx, 57h ; 'W'
0x18008b0a4  mov     r9d, ebx
0x18008b0a7  lea     r8, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids
0x18008b0ae  mov     rcx, [rcx+10h]
0x18008b0b2  call    WPP_SF_d
0x18008b0b7  nop
0x18008b0b8  lea     rcx, [rsp+180h+var_140]; this
0x18008b0bd  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x18008b0c2  jmp     loc_18008B65C
0x18008b0c7  mov     rcx, rdi; this
0x18008b0ca  call    ?Block@CSynchronousSink@@QEAAXXZ; CSynchronousSink::Block(void)
0x18008b0cf  xor     r9d, r9d; struct IWbemClassObject **
0x18008b0d2  xor     r8d, r8d; unsigned __int16 **
0x18008b0d5  lea     rdx, [rbp+80h+arg_8]; int *
0x18008b0dc  mov     rcx, rdi; this
0x18008b0df  call    ?GetStatus@CSynchronousSink@@QEAAXPEAJPEAPEAGPEAPEAUIWbemClassObject@@@Z; CSynchronousSink::GetStatus(long *,ushort * *,IWbemClassObject * *)
0x18008b0e4  lea     r12, [rdi+40h]
0x18008b0e8  mov     edx, 8
0x18008b0ed  lea     r8d, [rdx+5Ch]
0x18008b0f1  lea     rcx, [rbp+80h+var_D0]
0x18008b0f5  call    cs:__imp_??0CFlexArray@@QEAA@HH@Z; CFlexArray::CFlexArray(int,int)
0x18008b0fb  nop
0x18008b0fc  mov     r14, r13
0x18008b0ff  mov     edi, r13d
0x18008b102  cmp     [r12], r13d
0x18008b106  jle     loc_18008B642
0x18008b10c  mov     edx, edi
0x18008b10e  mov     rcx, r12
0x18008b111  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x18008b117  mov     r15, rax
0x18008b11a  lea     rcx, [rsp+180h+pvarg]; pvarg
0x18008b11f  call    cs:__imp_VariantInit
0x18008b125  nop
0x18008b126  mov     rcx, [r15]
0x18008b129  mov     rax, [rcx+20h]
0x18008b12d  mov     [rsp+180h+var_158], r13
0x18008b132  mov     qword ptr [rsp+180h+var_160], r13
0x18008b137  lea     r9, [rsp+180h+pvarg]
0x18008b13c  xor     r8d, r8d
0x18008b13f  lea     rdx, aClass_0; "__CLASS"
0x18008b146  mov     rcx, r15
0x18008b149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b14e  mov     ebx, eax
0x18008b150  test    eax, eax
0x18008b152  js      loc_18008B5DF
0x18008b158  mov     eax, 8
0x18008b15d  cmp     ax, word ptr [rsp+180h+pvarg]
0x18008b162  jnz     loc_18008B59D
0x18008b168  mov     rdx, rsi; unsigned __int16 *
0x18008b16b  mov     rcx, qword ptr [rbp+80h+pvarg+8]; unsigned __int16 *
0x18008b16f  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x18008b174  test    eax, eax
0x18008b176  jnz     short loc_18008B17D
0x18008b178  mov     r14, r15
0x18008b17b  jmp     short loc_18008B192
0x18008b17d  mov     rdx, r15
0x18008b180  lea     rcx, [rbp+80h+var_D0]
0x18008b184  call    cs:__imp_?Add@CFlexArray@@QEAAHPEAX@Z; CFlexArray::Add(void *)
0x18008b18a  test    eax, eax
0x18008b18c  jnz     loc_18008B54F
0x18008b192  lea     rcx, [rsp+180h+pvarg]; this
0x18008b197  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18008b19c  mov     r15d, 1
0x18008b1a2  add     edi, r15d
0x18008b1a5  cmp     edi, [r12]
0x18008b1a9  jl      loc_18008B10C
0x18008b1af  test    r14, r14
0x18008b1b2  jz      loc_18008B642
0x18008b1b8  mov     edx, r15d
0x18008b1bb  lea     rcx, [rsp+180h+var_138]
0x18008b1c0  call    cs:__imp_??0CFlexQueue@@QEAA@H@Z; CFlexQueue::CFlexQueue(int)
0x18008b1c6  nop
0x18008b1c7  mov     rcx, r14; struct IWbemClassObject *
0x18008b1ca  call    ?Create@CDynasty@@SAPEAV1@PEAUIWbemClassObject@@@Z; CDynasty::Create(IWbemClassObject *)
0x18008b1cf  mov     rdx, rax
0x18008b1d2  mov     rbx, [rbp+80h+arg_20]
0x18008b1d9  mov     rcx, rbx
0x18008b1dc  call    ?reset@?$unique_ptr@VCDynasty@@U?$default_delete@VCDynasty@@@std@@@std@@QEAAXPEAVCDynasty@@@Z; std::unique_ptr<CDynasty>::reset(CDynasty *)
0x18008b1e1  mov     rdx, [rbx]
0x18008b1e4  test    rdx, rdx
0x18008b1e7  jnz     short loc_18008B249
0x18008b1e9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008b1ef  mov     ebx, 80041006h
0x18008b1f4  mov     edx, ebx
0x18008b1f6  mov     rcx, rax
0x18008b1f9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008b1ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b206  lea     rax, WPP_GLOBAL_Control
0x18008b20d  cmp     rcx, rax
0x18008b210  jz      short loc_18008B239
0x18008b212  test    [rcx+1Ch], r15b
0x18008b216  jz      short loc_18008B239
0x18008b218  cmp     byte ptr [rcx+19h], 2
0x18008b21c  jb      short loc_18008B239
0x18008b21e  lea     edx, [r15+5Ah]
0x18008b222  mov     r9d, 80041006h
0x18008b228  lea     r8, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids
0x18008b22f  mov     rcx, [rcx+10h]
0x18008b233  call    WPP_SF_d
0x18008b238  nop
0x18008b239  lea     rcx, [rsp+180h+var_138]
0x18008b23e  call    cs:__imp_??1CFlexQueue@@QEAA@XZ; CFlexQueue::~CFlexQueue(void)
0x18008b244  jmp     loc_18008B633
0x18008b249  lea     rcx, [rsp+180h+var_138]
0x18008b24e  call    cs:__imp_?Enqueue@CFlexQueue@@QEAA_NPEAX@Z; CFlexQueue::Enqueue(void *)
0x18008b254  cmp     [rbp+80h+var_D0], r13d
0x18008b258  jz      loc_18008B3AA
0x18008b25e  mov     r12d, 8
0x18008b264  lea     rcx, [rsp+180h+var_138]
0x18008b269  call    cs:__imp_?Dequeue@CFlexQueue@@QEAAPEAXXZ; CFlexQueue::Dequeue(void)
0x18008b26f  mov     rsi, rax
0x18008b272  test    rax, rax
0x18008b275  jz      loc_18008B3AA
0x18008b27b  lea     rcx, [rsp+180h+var_120]; pvarg
0x18008b280  call    cs:__imp_VariantInit
0x18008b286  nop
0x18008b287  mov     rcx, [rsi+8]
0x18008b28b  mov     rdx, [rcx]
0x18008b28e  mov     rax, [rdx+20h]
0x18008b292  mov     [rsp+180h+var_158], r13
0x18008b297  mov     qword ptr [rsp+180h+var_160], r13
0x18008b29c  lea     r9, [rsp+180h+var_120]
0x18008b2a1  xor     r8d, r8d
0x18008b2a4  lea     rdx, aClass_0; "__CLASS"
0x18008b2ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b2b0  mov     ebx, eax
0x18008b2b2  test    eax, eax
0x18008b2b4  js      loc_18008B4F7
0x18008b2ba  cmp     r12w, word ptr [rsp+180h+var_120]
0x18008b2c0  jnz     loc_18008B4B5
0x18008b2c6  mov     edi, r13d
0x18008b2c9  cmp     [rbp+80h+var_D0], r13d
0x18008b2cd  jle     loc_18008B396
0x18008b2d3  mov     edx, edi
0x18008b2d5  lea     rcx, [rbp+80h+var_D0]
0x18008b2d9  call    cs:__imp_??ACFlexArray@@QEAAAEAPEAXH@Z; CFlexArray::operator[](int)
0x18008b2df  mov     r14, [rax]
0x18008b2e2  lea     rcx, [rbp+80h+var_F0]; pvarg
0x18008b2e6  call    cs:__imp_VariantInit
0x18008b2ec  nop
0x18008b2ed  mov     rax, [r14]
0x18008b2f0  mov     [rsp+180h+var_158], r13
0x18008b2f5  mov     qword ptr [rsp+180h+var_160], r13
0x18008b2fa  lea     r9, [rbp+80h+var_F0]
0x18008b2fe  xor     r8d, r8d
0x18008b301  lea     rdx, aSuperclass_0; "__SUPERCLASS"
0x18008b308  mov     rcx, r14
0x18008b30b  mov     rax, [rax+20h]
0x18008b30f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b314  mov     ebx, eax
0x18008b316  test    eax, eax
0x18008b318  js      loc_18008B45E
0x18008b31e  cmp     word ptr [rbp+80h+var_F0], r12w
0x18008b323  jnz     short loc_18008B381
0x18008b325  mov     rdx, qword ptr [rsp+180h+var_120+8]; unsigned __int16 *
0x18008b32a  mov     rcx, qword ptr [rbp+80h+var_F0+8]; unsigned __int16 *
0x18008b32e  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x18008b333  test    eax, eax
0x18008b335  jnz     short loc_18008B381
0x18008b337  mov     rcx, r14; struct IWbemClassObject *
0x18008b33a  call    ?Create@CDynasty@@SAPEAV1@PEAUIWbemClassObject@@@Z; CDynasty::Create(IWbemClassObject *)
0x18008b33f  mov     rbx, rax
0x18008b342  mov     [rbp+80h+arg_8], rax
0x18008b349  test    rax, rax
0x18008b34c  jz      loc_18008B40B
0x18008b352  mov     rdx, rax; struct CDynasty *
0x18008b355  mov     rcx, rsi; this
0x18008b358  call    ?AddChild@CDynasty@@QEAAXPEAV1@@Z; CDynasty::AddChild(CDynasty *)
0x18008b35d  mov     rdx, rbx
0x18008b360  lea     rcx, [rsp+180h+var_138]
0x18008b365  call    cs:__imp_?Enqueue@CFlexQueue@@QEAA_NPEAX@Z; CFlexQueue::Enqueue(void *)
0x18008b36b  mov     [rbp+80h+arg_8], r13
0x18008b372  mov     edx, edi
0x18008b374  lea     rcx, [rbp+80h+var_D0]
0x18008b378  call    cs:__imp_?RemoveAt@CFlexArray@@QEAAHH@Z; CFlexArray::RemoveAt(int)
0x18008b37e  sub     edi, r15d
0x18008b381  lea     rcx, [rbp+80h+var_F0]; this
0x18008b385  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18008b38a  add     edi, r15d
0x18008b38d  cmp     edi, [rbp+80h+var_D0]
0x18008b390  jl      loc_18008B2D3
0x18008b396  lea     rcx, [rsp+180h+var_120]; this
0x18008b39b  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18008b3a0  cmp     [rbp+80h+var_D0], r13d
0x18008b3a4  jnz     loc_18008B264
0x18008b3aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b3b1  lea     rax, WPP_GLOBAL_Control
0x18008b3b8  cmp     rcx, rax
0x18008b3bb  jz      short loc_18008B3E2
0x18008b3bd  test    [rcx+1Ch], r15b
0x18008b3c1  jz      short loc_18008B3E2
0x18008b3c3  cmp     byte ptr [rcx+19h], 2
0x18008b3c7  jb      short loc_18008B3E2
0x18008b3c9  mov     edx, 60h ; '`'
0x18008b3ce  xor     r9d, r9d
0x18008b3d1  lea     r8, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids
0x18008b3d8  mov     rcx, [rcx+10h]
0x18008b3dc  call    WPP_SF_d
0x18008b3e1  nop
0x18008b3e2  lea     rcx, [rsp+180h+var_138]
0x18008b3e7  call    cs:__imp_??1CFlexQueue@@QEAA@XZ; CFlexQueue::~CFlexQueue(void)
0x18008b3ed  nop
0x18008b3ee  lea     rcx, [rbp+80h+var_D0]
0x18008b3f2  call    cs:__imp_??1CFlexArray@@QEAA@XZ; CFlexArray::~CFlexArray(void)
0x18008b3f8  nop
0x18008b3f9  lea     rcx, [rsp+180h+var_140]; this
0x18008b3fe  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x18008b403  mov     ebx, r13d
0x18008b406  jmp     loc_18008B65C
  ... truncated ...
```
