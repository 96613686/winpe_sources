# CQueryEngine::ExecSchemaQuery(CWbemNamespace *,ushort *,QL_LEVEL_1_RPN_EXPRESSION *,IWbemContext *,CBasicObjectSink *)

- ea: `0x18007258c`
- end: `0x180073144`
- name: `?ExecSchemaQuery@CQueryEngine@@CAJPEAVCWbemNamespace@@PEAGPEAUQL_LEVEL_1_RPN_EXPRESSION@@PEAUIWbemContext@@PEAVCBasicObjectSink@@@Z`
- size: `3000`
- prototype: `__int64 __usercall@<rax>(struct CWbemNamespace *this@<rcx>, unsigned __int16 *@<rdx>, struct QL_LEVEL_1_RPN_EXPRESSION *@<r8>, struct IWbemContext *@<r9>, struct CBasicObjectSink *)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18003d3b0`

## callees

- `0x18000b140`
- `0x18000b46c`
- `0x18000ebd0`
- `0x180011ca4`
- `0x1800121d0`
- `0x18001307c`
- `0x180013c50`
- `0x180035740`
- `0x180037af4`
- `0x180039d40`
- `0x18003ad40`
- `0x18003cf20`
- `0x18003cfe0`
- `0x18003d050`
- `0x180065278`
- `0x18007258c`
- `0x1800da010`

## import_xrefs

- `wbemcomn!?GetNumElements@CPropertyName@@QEBAJXZ` at `0x180072c9d`
- `wbemcomn!?GetNumElements@CPropertyName@@QEBAJXZ` at `0x180072caf`
- `wbemcomn!?GetNumElements@CPropertyName@@QEBAJXZ` at `0x180072c9d`
- `wbemcomn!?GetNumElements@CPropertyName@@QEBAJXZ` at `0x180072caf`
- `wbemcomn!?GetStringAt@CPropertyName@@QEBAPEBGJ@Z` at `0x180072638`
- `wbemcomn!?GetStringAt@CPropertyName@@QEBAPEBGJ@Z` at `0x180072af2`
- `wbemcomn!?GetStringAt@CPropertyName@@QEBAPEBGJ@Z` at `0x180072cc3`
- `wbemcomn!?GetStringAt@CPropertyName@@QEBAPEBGJ@Z` at `0x180072638`
- `wbemcomn!?GetStringAt@CPropertyName@@QEBAPEBGJ@Z` at `0x180072af2`
- `wbemcomn!?GetStringAt@CPropertyName@@QEBAPEBGJ@Z` at `0x180072cc3`
- `wbemcomn!?IsNull@CVar@@QEAAHXZ` at `0x1800729a6`
- `wbemcomn!?IsNull@CVar@@QEAAHXZ` at `0x1800729a6`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18007292d`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18007292d`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x1800729b4`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x1800729b4`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800729dd`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180072a1e`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800729dd`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180072a1e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180072b2d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180072e5f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180072f66`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180072ff0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180072b2d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180072e5f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180072f66`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180072ff0`
- `wbemcomn!GetMemLogObject` at `0x180072646`
- `wbemcomn!GetMemLogObject` at `0x180072759`
- `wbemcomn!GetMemLogObject` at `0x18007281a`
- `wbemcomn!GetMemLogObject` at `0x1800728cc`
- `wbemcomn!GetMemLogObject` at `0x18007294e`
- `wbemcomn!GetMemLogObject` at `0x180072a4c`
- `wbemcomn!GetMemLogObject` at `0x180072a97`
- `wbemcomn!GetMemLogObject` at `0x180072b5b`
- `wbemcomn!GetMemLogObject` at `0x180072c0e`
- `wbemcomn!GetMemLogObject` at `0x180072e0f`
- `wbemcomn!GetMemLogObject` at `0x180072e8f`
- `wbemcomn!GetMemLogObject` at `0x180072f96`
- `wbemcomn!GetMemLogObject` at `0x18007301c`
- `wbemcomn!GetMemLogObject` at `0x180072646`
- `wbemcomn!GetMemLogObject` at `0x180072759`
- `wbemcomn!GetMemLogObject` at `0x18007281a`
- `wbemcomn!GetMemLogObject` at `0x1800728cc`
- `wbemcomn!GetMemLogObject` at `0x18007294e`
- `wbemcomn!GetMemLogObject` at `0x180072a4c`
- `wbemcomn!GetMemLogObject` at `0x180072a97`
- `wbemcomn!GetMemLogObject` at `0x180072b5b`
- `wbemcomn!GetMemLogObject` at `0x180072c0e`
- `wbemcomn!GetMemLogObject` at `0x180072e0f`
- `wbemcomn!GetMemLogObject` at `0x180072e8f`
- `wbemcomn!GetMemLogObject` at `0x180072f96`
- `wbemcomn!GetMemLogObject` at `0x18007301c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180072656`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180072769`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007282a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800728d7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007295e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180072a5c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180072aa7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180072b6b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180072c1e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180072e1f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180072e9f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180072fa6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007302c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180072656`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180072769`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007282a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800728d7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007295e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180072a5c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180072aa7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180072b6b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180072c1e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180072e1f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180072e9f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180072fa6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007302c`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CQueryEngine::ExecSchemaQuery(
        struct CWbemNamespace *this,
        struct IWbemClassObject *a2,
        struct QL_LEVEL_1_RPN_EXPRESSION *a3,
        struct IWbemContext *a4,
        struct CBasicObjectSink *a5)
{
  __int64 v8; // r13
  int v9; // r8d
  unsigned __int16 *v10; // rdx
  __int64 v12; // rcx
  const unsigned __int16 *StringAt; // rax
  const unsigned __int16 *v14; // rdi
  CMemoryLog *MemLogObject; // rax
  int v16; // ebx
  CClientCnt *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r9
  int v20; // edx
  CBasicObjectSink *v21; // rcx
  __int64 v22; // rbx
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rcx
  bool v26; // zf
  CMemoryLog *v27; // rax
  CMemoryLog *v28; // rax
  __int16 v29; // ax
  unsigned __int16 *v30; // r15
  int ObjectByPath; // eax
  struct IWbemClassObject *v32; // rdi
  int v33; // ebx
  CMemoryLog *v34; // rax
  unsigned int v35; // ebx
  CMemoryLog *v36; // rax
  int v37; // edx
  const unsigned __int16 *LPWSTR; // rax
  struct IWbemClassObject **v39; // rcx
  struct CBasicObjectSink *v40; // rbx
  CMemoryLog *v41; // rax
  CMemoryLog *v42; // rax
  const unsigned __int16 *v43; // rax
  __int64 v44; // rax
  struct IWbemClassObject *v45; // rax
  CCombiningSink *v46; // rbx
  CMemoryLog *v47; // rax
  CMemoryLog *v48; // rax
  __int64 v49; // r12
  int i; // eax
  __int64 v51; // rbx
  const unsigned __int16 *v52; // rax
  const unsigned __int16 *v53; // rdi
  const unsigned __int16 *v54; // rcx
  const unsigned __int16 *v55; // rdx
  __int64 v56; // rax
  CMemoryLog *v57; // rax
  struct IWbemClassObject *v58; // rax
  CBasicObjectSink *v59; // rdi
  CQlFilteringSink *v60; // rbx
  CMemoryLog *v61; // rax
  unsigned __int16 *v62; // rdx
  __int64 v63; // r15
  CCombiningSink *v64; // rax
  struct CBasicObjectSink *v65; // rbx
  CMemoryLog *v66; // rax
  CClientCnt *v67; // rcx
  __int64 v68; // rdx
  CCombiningSink *v69; // rax
  CMemoryLog *v70; // rax
  int v71; // [rsp+20h] [rbp-60h]
  int v72; // [rsp+30h] [rbp-50h]
  __int64 v73; // [rsp+38h] [rbp-48h]
  __int64 v74; // [rsp+40h] [rbp-40h]
  _QWORD v75[6]; // [rsp+48h] [rbp-38h] BYREF
  int v76; // [rsp+78h] [rbp-8h]
  int v77; // [rsp+7Ch] [rbp-4h]
  struct IWbemClassObject *v78; // [rsp+C8h] [rbp+48h] BYREF
  struct IWbemClassObject *v79; // [rsp+D0h] [rbp+50h] BYREF

  v78 = a2;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids);
  }
  v8 = 0;
  if ( !*((_DWORD *)a3 + 2) )
  {
    v9 = 0;
    v10 = 0;
LABEL_7:
    CWbemNamespace::Exec_CreateClassEnum(this, v10, v9, a4, a5);
    return 0;
  }
  if ( *((_DWORD *)a3 + 2) == 1 )
  {
    v12 = *((_QWORD *)a3 + 2);
    if ( *(_DWORD *)(v12 + 40) == 1 )
    {
      StringAt = CPropertyName::GetStringAt((CPropertyName *)(v12 + 8), 0);
      v14 = StringAt;
      if ( !StringAt )
      {
        MemLogObject = GetMemLogObject();
        v16 = -2147217385;
        CMemoryLog::Write(MemLogObject, -2147217385);
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_18;
        }
        v18 = 109;
LABEL_16:
        v19 = 2147749911LL;
        goto LABEL_17;
      }
      v22 = *((_QWORD *)a3 + 2);
      if ( !(unsigned int)wbem_wcsicmp(StringAt, L"__CLASS") )
      {
        if ( *(_WORD *)(v22 + 48) == 8 )
        {
          v23 = *(_QWORD *)(v22 + 56);
          v24 = -1;
          v25 = -1;
          do
            ++v25;
          while ( *(_WORD *)(v23 + 2 * v25) );
          if ( v25 )
          {
            CForwardingSink::CForwardingSink((CForwardingSink *)v75, a5, 1);
            v75[0] = &CErrorChangingSink::`vftable'{for `IWbemObjectSinkEx'};
            v75[1] = &CInternalMerger::COwnSink::`vftable'{for `CDestination'};
            v76 = -2147217406;
            v77 = 0;
            CWbemNamespace::Exec_GetObject(
              (const unsigned __int16 **)this,
              *(unsigned __int16 **)(v22 + 56),
              0,
              a4,
              (struct CBasicObjectSink *)v75);
            goto LABEL_27;
          }
          do
            ++v24;
          while ( *(_WORD *)(v23 + 2 * v24) );
          v26 = v24 == 0;
        }
        else
        {
          v26 = *(_WORD *)(v22 + 48) == 1;
        }
        if ( v26 )
        {
          v20 = 0;
          goto LABEL_19;
        }
        v27 = GetMemLogObject();
        v16 = -2147217385;
        CMemoryLog::Write(v27, -2147217385);
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_18;
        }
        v18 = 110;
        goto LABEL_16;
      }
      if ( (unsigned int)wbem_wcsicmp(v14, L"__SUPERCLASS") )
      {
        if ( (unsigned int)wbem_wcsicmp(v14, L"__DYNASTY") )
        {
          v42 = GetMemLogObject();
          v16 = -2147217385;
          CMemoryLog::Write(v42, -2147217385);
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_18;
          }
          v18 = 115;
        }
        else
        {
          v29 = *(_WORD *)(v22 + 48);
          if ( v29 == 8 )
          {
            v30 = *(unsigned __int16 **)(v22 + 56);
            v78 = 0;
            ObjectByPath = CWbemNamespace::Exec_GetObjectByPath(this, v30, 0, a4, &v78, 0);
            v32 = v78;
            v79 = v78;
            if ( ObjectByPath >= 0 )
            {
              CVar::CVar((CVar *)v75);
              if ( ((int (__fastcall *)(struct IWbemClassObject *, _QWORD *))v32->lpVtbl[5].GetQualifierSet)(v32, v75) >= 0 )
              {
                if ( !CVar::IsNull((CVar *)v75) )
                {
                  LPWSTR = CVar::GetLPWSTR((CVar *)v75);
                  if ( !(unsigned int)wbem_wcsicmp(LPWSTR, v30) )
                  {
                    v40 = a5;
                    (**((void (__fastcall ***)(char *, struct IWbemClassObject *))a5 + 1))((char *)a5 + 8, v32);
                    CWbemNamespace::Exec_CreateClassEnum(this, v30, 0, a4, v40);
                    CVar::~CVar((CVar *)v75);
                    CReleaseMe::release((CReleaseMe *)&v79);
                    return 0;
                  }
                }
                v37 = 0;
              }
              else
              {
                v36 = GetMemLogObject();
                CMemoryLog::Write(v36, -2147217407);
                if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    113,
                    WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids,
                    2147749889LL);
                }
                v37 = -2147217407;
              }
              v35 = CBasicObjectSink::Return(a5, v37, 0);
              CVar::~CVar((CVar *)v75);
            }
            else
            {
              v33 = 0;
              if ( ObjectByPath != -2147217406 )
                v33 = ObjectByPath;
              if ( v33 < 0 )
              {
                v34 = GetMemLogObject();
                CMemoryLog::Write(v34, v33);
                if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    112,
                    WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids,
                    (unsigned int)v33);
                }
              }
              v35 = CBasicObjectSink::Return(a5, v33, 0);
            }
            v39 = &v79;
LABEL_185:
            CReleaseMe::release((CReleaseMe *)v39);
            return v35;
          }
          if ( v29 == 1 )
          {
            CBasicObjectSink::Return(a5, 0, 0);
            return 0;
          }
          v41 = GetMemLogObject();
          v16 = -2147217385;
          CMemoryLog::Write(v41, -2147217385);
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_18;
          }
          v18 = 114;
        }
        goto LABEL_16;
      }
      if ( *(_WORD *)(v22 + 48) != 8 )
      {
        if ( *(_WORD *)(v22 + 48) == 1 )
        {
          v9 = 1;
          v10 = (unsigned __int16 *)&psz;
          goto LABEL_7;
        }
        v28 = GetMemLogObject();
        v16 = -2147217385;
        CMemoryLog::Write(v28, -2147217385);
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_18;
        }
        v18 = 111;
        goto LABEL_16;
      }
      CErrorChangingSink::CErrorChangingSink((CErrorChangingSink *)v75, a5, -2147217392, 0);
      CWbemNamespace::Exec_CreateClassEnum(
        this,
        *(unsigned __int16 **)(v22 + 56),
        1,
        a4,
        (struct CBasicObjectSink *)v75);
LABEL_27:
      CForwardingSink::~CForwardingSink((CForwardingSink *)v75);
      return 0;
    }
    if ( *(_DWORD *)(v12 + 40) == 9 )
    {
      v43 = CPropertyName::GetStringAt((CPropertyName *)(v12 + 8), 0);
      if ( !(unsigned int)wbem_wcsicmp(v43, L"__THIS") )
      {
        v44 = *((_QWORD *)a3 + 2);
        if ( *(_WORD *)(v44 + 48) == 8 && *(_QWORD *)(v44 + 56) )
        {
          v45 = (struct IWbemClassObject *)CWin32DefaultArena::WbemMemAlloc(0x70u);
          v78 = v45;
          if ( v45 )
            v46 = CCombiningSink::CCombiningSink((CCombiningSink *)v45, a5, 0x80041002);
          else
            v46 = 0;
          if ( v46 )
          {
            (*(void (__fastcall **)(CCombiningSink *))(*(_QWORD *)v46 + 8LL))(v46);
            v78 = (struct IWbemClassObject *)v46;
            CWbemNamespace::Exec_GetObject(
              (const unsigned __int16 **)this,
              *(unsigned __int16 **)(*((_QWORD *)a3 + 2) + 56LL),
              0,
              a4,
              v46);
            CWbemNamespace::Exec_CreateClassEnum(this, *(unsigned __int16 **)(*((_QWORD *)a3 + 2) + 56LL), 0, a4, v46);
            (*(void (__fastcall **)(CCombiningSink *))(*(_QWORD *)v46 + 16LL))(v46);
            v78 = 0;
            return 0;
          }
          v47 = GetMemLogObject();
          v16 = -2147217402;
          CMemoryLog::Write(v47, -2147217402);
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_18;
          }
          v18 = 117;
          v19 = 2147749894LL;
        }
        else
        {
          v48 = GetMemLogObject();
          v16 = -2147217385;
          CMemoryLog::Write(v48, -2147217385);
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_18;
          }
          v18 = 116;
          v19 = 2147749911LL;
        }
LABEL_17:
        WPP_SF_d(*((_QWORD *)v17 + 2), v18, WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids, v19);
        goto LABEL_18;
      }
    }
  }
  LODWORD(v78) = 0;
  LODWORD(v79) = CQueryEngine::IsConjunctiveQuery(a3);
  v74 = 0;
  v49 = 0;
  v73 = 0;
  for ( i = 0; ; i = v72 + 1 )
  {
    v72 = i;
    if ( i == *((_DWORD *)a3 + 2) )
      break;
    v51 = *((_QWORD *)a3 + 2) + ((__int64)i << 7);
    if ( (int)CPropertyName::GetNumElements((CPropertyName *)(v51 + 8)) > 1 )
      goto LABEL_135;
    if ( CPropertyName::GetNumElements((CPropertyName *)(v51 + 8)) != 1 )
      continue;
    v52 = CPropertyName::GetStringAt((CPropertyName *)(v51 + 8), 0);
    v53 = v52;
    if ( !v52 )
      goto LABEL_135;
    v54 = v52;
    if ( *(_DWORD *)(v51 + 40) == 9 )
    {
      v55 = L"__THIS";
    }
    else
    {
      if ( !(unsigned int)wbem_wcsicmp(v52, L"__CLASS") || !(unsigned int)wbem_wcsicmp(v53, L"__SUPERCLASS") )
        goto LABEL_107;
      v55 = L"__DYNASTY";
      v54 = v53;
    }
    if ( (unsigned int)wbem_wcsicmp(v54, v55) )
      goto LABEL_135;
LABEL_107:
    if ( !(_DWORD)v79 )
      continue;
    if ( (unsigned int)wbem_wcsicmp(v53, L"__THIS") )
    {
      if ( (unsigned int)wbem_wcsicmp(v53, L"__CLASS") )
      {
        if ( (unsigned int)wbem_wcsicmp(v53, L"__SUPERCLASS") )
        {
          if ( *(_WORD *)(v51 + 48) != 8 )
          {
LABEL_127:
            LODWORD(v78) = 1;
            continue;
          }
          if ( *(_DWORD *)(v51 + 40) != 1 )
          {
LABEL_129:
            LODWORD(v79) = 0;
            continue;
          }
          v56 = v73;
          if ( !v73 )
            v56 = v51;
          v73 = v56;
        }
        else
        {
          if ( *(_WORD *)(v51 + 48) != 8 && *(_WORD *)(v51 + 48) != 1 )
          {
LABEL_115:
            LODWORD(v78) = 1;
            continue;
          }
          if ( *(_DWORD *)(v51 + 40) != 1 )
            goto LABEL_129;
          if ( !v8 )
            v8 = v51;
        }
      }
      else
      {
        if ( *(_WORD *)(v51 + 48) != 8 && *(_WORD *)(v51 + 48) != 1 )
          goto LABEL_115;
        if ( *(_DWORD *)(v51 + 40) == 1 )
        {
          if ( !v49 )
            v49 = v51;
        }
        else
        {
          LODWORD(v79) = 0;
        }
      }
    }
    else
    {
      if ( *(_WORD *)(v51 + 48) != 8 )
        goto LABEL_127;
      if ( !v74 )
        v74 = v51;
    }
  }
  if ( (_DWORD)v78 != 1 )
  {
    v58 = (struct IWbemClassObject *)CWin32DefaultArena::WbemMemAlloc(0x48u);
    v78 = v58;
    v59 = a5;
    if ( v58 )
      v60 = CQlFilteringSink::CQlFilteringSink((CQlFilteringSink *)v58, a5, a3, this, v71);
    else
      v60 = 0;
    if ( !v60 )
    {
      v61 = GetMemLogObject();
      CMemoryLog::Write(v61, -2147217402);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          119,
          WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids,
          2147749894LL);
      }
      v20 = -2147217402;
      v21 = v59;
      return CBasicObjectSink::Return(v21, v20, 0);
    }
    _InterlockedAdd((volatile signed __int32 *)v60 + 4, 1u);
    v78 = (struct IWbemClassObject *)v60;
    if ( !(_DWORD)v79 )
      goto LABEL_177;
    if ( v49 )
    {
      if ( *(_WORD *)(v49 + 48) == 1 )
        CBasicObjectSink::Return(v60, 0, 0);
      else
        CWbemNamespace::Exec_GetObject((const unsigned __int16 **)this, *(unsigned __int16 **)(v49 + 56), 0, a4, v60);
      goto LABEL_179;
    }
    if ( v8 )
    {
      if ( *(_WORD *)(v8 + 48) != 1 )
      {
        v62 = *(unsigned __int16 **)(v8 + 56);
LABEL_178:
        CWbemNamespace::Exec_CreateClassEnum(this, v62, 0, a4, v60);
LABEL_179:
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids, 0);
        }
        v35 = 0;
        goto LABEL_184;
      }
LABEL_177:
      v62 = 0;
      goto LABEL_178;
    }
    v63 = v73;
    if ( v73 )
    {
      v64 = (CCombiningSink *)CWin32DefaultArena::WbemMemAlloc(0x70u);
      v79 = (struct IWbemClassObject *)v64;
      if ( v64 )
        v65 = CCombiningSink::CCombiningSink(v64, v60, 0x80041002);
      else
        v65 = 0;
      if ( !v65 )
      {
        v66 = GetMemLogObject();
        CMemoryLog::Write(v66, -2147217402);
        v67 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_175;
        }
        v68 = 120;
LABEL_174:
        WPP_SF_d(*((_QWORD *)v67 + 2), v68, WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids, 2147749894LL);
LABEL_175:
        v35 = CBasicObjectSink::Return(v59, -2147217402, 0);
LABEL_184:
        v39 = &v78;
        goto LABEL_185;
      }
    }
    else
    {
      v63 = v74;
      if ( !v74 )
        goto LABEL_177;
      v69 = (CCombiningSink *)CWin32DefaultArena::WbemMemAlloc(0x70u);
      v79 = (struct IWbemClassObject *)v69;
      if ( v69 )
        v65 = CCombiningSink::CCombiningSink(v69, v60, 0x80041002);
      else
        v65 = 0;
      if ( !v65 )
      {
        v70 = GetMemLogObject();
        CMemoryLog::Write(v70, -2147217402);
        v67 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_175;
        }
        v68 = 121;
        goto LABEL_174;
      }
    }
    CReleaseMe::release((CReleaseMe *)&v78);
    (*(void (__fastcall **)(struct CBasicObjectSink *))(*(_QWORD *)v65 + 8LL))(v65);
    CWbemNamespace::Exec_GetObject((const unsigned __int16 **)this, *(unsigned __int16 **)(v63 + 56), 0, a4, v65);
    CWbemNamespace::Exec_CreateClassEnum(this, *(unsigned __int16 **)(v63 + 56), 0, a4, v65);
    CObjectSink::Release(v65);
    goto LABEL_179;
  }
LABEL_135:
  v57 = GetMemLogObject();
  v16 = -2147217385;
  CMemoryLog::Write(v57, -2147217385);
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v18 = 118;
    goto LABEL_16;
  }
LABEL_18:
  v20 = v16;
LABEL_19:
  v21 = a5;
  return CBasicObjectSink::Return(v21, v20, 0);
}

```

## disassembly

```asm
0x18007258c  mov     [rsp-38h+arg_0], rbx
0x180072591  mov     [rsp-38h+arg_8], rdx
0x180072596  push    rbp
0x180072597  push    rsi
0x180072598  push    rdi
0x180072599  push    r12
0x18007259b  push    r13
0x18007259d  push    r14
0x18007259f  push    r15
0x1800725a1  mov     rbp, rsp
0x1800725a4  sub     rsp, 80h
0x1800725ab  mov     r14, r9
0x1800725ae  mov     r15, r8
0x1800725b1  mov     rsi, rcx
0x1800725b4  lea     rax, WPP_GLOBAL_Control
0x1800725bb  lea     rdi, WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids
0x1800725c2  mov     r12d, 1
0x1800725c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800725cf  cmp     rcx, rax
0x1800725d2  jz      short loc_1800725F1
0x1800725d4  test    [rcx+1Ch], r12b
0x1800725d8  jz      short loc_1800725F1
0x1800725da  cmp     byte ptr [rcx+19h], 5
0x1800725de  jb      short loc_1800725F1
0x1800725e0  lea     edx, [r12+6Bh]
0x1800725e5  mov     r8, rdi
0x1800725e8  mov     rcx, [rcx+10h]
0x1800725ec  call    WPP_SF_
0x1800725f1  xor     r13d, r13d
0x1800725f4  cmp     [r15+8], r13d
0x1800725f8  jnz     short loc_18007261A
0x1800725fa  xor     r8d, r8d; int
0x1800725fd  xor     edx, edx; unsigned __int16 *
0x1800725ff  mov     rax, [rbp+arg_20]
0x180072603  mov     [rsp+80h+var_60], rax; struct CBasicObjectSink *
0x180072608  mov     r9, r14; struct IWbemContext *
0x18007260b  mov     rcx, rsi; this
0x18007260e  call    ?Exec_CreateClassEnum@CWbemNamespace@@QEAAJPEAGJPEAUIWbemContext@@PEAVCBasicObjectSink@@@Z; CWbemNamespace::Exec_CreateClassEnum(ushort *,long,IWbemContext *,CBasicObjectSink *)
0x180072613  xor     eax, eax
0x180072615  jmp     loc_180073129
0x18007261a  cmp     [r15+8], r12d
0x18007261e  jnz     loc_180072C62
0x180072624  mov     rcx, [r15+10h]
0x180072628  cmp     [rcx+28h], r12d
0x18007262c  jnz     loc_180072AE2
0x180072632  add     rcx, 8
0x180072636  xor     edx, edx
0x180072638  call    cs:__imp_?GetStringAt@CPropertyName@@QEBAPEBGJ@Z; CPropertyName::GetStringAt(long)
0x18007263e  mov     rdi, rax
0x180072641  test    rax, rax
0x180072644  jnz     short loc_1800726A7
0x180072646  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007264c  mov     ebx, 80041017h
0x180072651  mov     edx, ebx
0x180072653  mov     rcx, rax
0x180072656  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007265c  mov     rcx, cs:WPP_GLOBAL_Control
0x180072663  lea     rax, WPP_GLOBAL_Control
0x18007266a  cmp     rcx, rax
0x18007266d  jz      short loc_180072694
0x18007266f  test    [rcx+1Ch], r12b
0x180072673  jz      short loc_180072694
0x180072675  cmp     byte ptr [rcx+19h], 2
0x180072679  jb      short loc_180072694
0x18007267b  lea     edx, [rdi+6Dh]
0x18007267e  mov     r9d, 80041017h
0x180072684  lea     r8, WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids
0x18007268b  mov     rcx, [rcx+10h]
0x18007268f  call    WPP_SF_d
0x180072694  xor     r8d, r8d; struct IWbemClassObject *
0x180072697  mov     edx, ebx; int
0x180072699  mov     rcx, [rbp+arg_20]; this
0x18007269d  call    ?Return@CBasicObjectSink@@QEAAJJPEAUIWbemClassObject@@@Z; CBasicObjectSink::Return(long,IWbemClassObject *)
0x1800726a2  jmp     loc_180073129
0x1800726a7  mov     rbx, [r15+10h]
0x1800726ab  lea     rdx, aClass_0; "__CLASS"
0x1800726b2  mov     rcx, rdi; unsigned __int16 *
0x1800726b5  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x1800726ba  test    eax, eax
0x1800726bc  jnz     loc_1800727AE
0x1800726c2  cmp     word ptr [rbx+30h], 8
0x1800726c7  jnz     loc_180072752
0x1800726cd  mov     rdx, [rbx+38h]
0x1800726d1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800726d5  mov     rcx, rax
0x1800726d8  inc     rcx
0x1800726db  cmp     [rdx+rcx*2], r13w
0x1800726e0  jnz     short loc_1800726D8
0x1800726e2  test    rcx, rcx
0x1800726e5  jz      short loc_180072743
0x1800726e7  mov     r8d, r12d; int
0x1800726ea  mov     rdx, [rbp+arg_20]; struct CBasicObjectSink *
0x1800726ee  lea     rcx, [rbp+var_38]; this
0x1800726f2  call    ??0CForwardingSink@@QEAA@PEAVCBasicObjectSink@@J@Z; CForwardingSink::CForwardingSink(CBasicObjectSink *,long)
0x1800726f7  nop
0x1800726f8  lea     rax, ??_7CErrorChangingSink@@6BIWbemObjectSinkEx@@@; const CErrorChangingSink::`vftable'{for `IWbemObjectSinkEx'}
0x1800726ff  mov     [rbp+var_38], rax
0x180072703  lea     rax, ??_7COwnSink@CInternalMerger@@6BCDestination@@@; const CInternalMerger::COwnSink::`vftable'{for `CDestination'}
0x18007270a  mov     [rbp+var_30], rax
0x18007270e  mov     [rbp+var_8], 80041002h
0x180072715  mov     [rbp+var_4], r13d
0x180072719  lea     rax, [rbp+var_38]
0x18007271d  mov     [rsp+80h+var_60], rax; struct CBasicObjectSink *
0x180072722  mov     r9, r14; struct IWbemContext *
0x180072725  xor     r8d, r8d; int
0x180072728  mov     rdx, [rbx+38h]; unsigned __int16 *
0x18007272c  mov     rcx, rsi; this
0x18007272f  call    ?Exec_GetObject@CWbemNamespace@@QEAAJPEBGJPEAUIWbemContext@@PEAVCBasicObjectSink@@@Z; CWbemNamespace::Exec_GetObject(ushort const *,long,IWbemContext *,CBasicObjectSink *)
0x180072734  nop
0x180072735  lea     rcx, [rbp+var_38]; this
0x180072739  call    ??1CForwardingSink@@UEAA@XZ; CForwardingSink::~CForwardingSink(void)
0x18007273e  jmp     loc_180072613
0x180072743  inc     rax
0x180072746  cmp     [rdx+rax*2], r13w
0x18007274b  jnz     short loc_180072743
0x18007274d  test    rax, rax
0x180072750  jmp     short loc_180072757
0x180072752  cmp     [rbx+30h], r12w
0x180072757  jz      short loc_1800727A4
0x180072759  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007275f  mov     ebx, 80041017h
0x180072764  mov     edx, ebx
0x180072766  mov     rcx, rax
0x180072769  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007276f  mov     rcx, cs:WPP_GLOBAL_Control
0x180072776  lea     rax, WPP_GLOBAL_Control
0x18007277d  cmp     rcx, rax
0x180072780  jz      loc_180072694
0x180072786  test    [rcx+1Ch], r12b
0x18007278a  jz      loc_180072694
0x180072790  cmp     byte ptr [rcx+19h], 2
0x180072794  jb      loc_180072694
0x18007279a  mov     edx, 6Eh ; 'n'
0x18007279f  jmp     loc_18007267E
0x1800727a4  xor     r8d, r8d
0x1800727a7  xor     edx, edx
0x1800727a9  jmp     loc_180072699
0x1800727ae  lea     rdx, aSuperclass_0; "__SUPERCLASS"
0x1800727b5  mov     rcx, rdi; unsigned __int16 *
0x1800727b8  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x1800727bd  test    eax, eax
0x1800727bf  jnz     loc_180072865
0x1800727c5  cmp     word ptr [rbx+30h], 8
0x1800727ca  jnz     short loc_180072804
0x1800727cc  xor     r9d, r9d; int
0x1800727cf  mov     r8d, 80041010h; int
0x1800727d5  mov     rdx, [rbp+arg_20]; struct CBasicObjectSink *
0x1800727d9  lea     rcx, [rbp+var_38]; this
0x1800727dd  call    ??0CErrorChangingSink@@QEAA@PEAVCBasicObjectSink@@JJ@Z; CErrorChangingSink::CErrorChangingSink(CBasicObjectSink *,long,long)
0x1800727e2  nop
0x1800727e3  lea     rax, [rbp+var_38]
0x1800727e7  mov     [rsp+80h+var_60], rax; struct CBasicObjectSink *
0x1800727ec  mov     r9, r14; struct IWbemContext *
0x1800727ef  mov     r8d, r12d; int
0x1800727f2  mov     rdx, [rbx+38h]; unsigned __int16 *
0x1800727f6  mov     rcx, rsi; this
0x1800727f9  call    ?Exec_CreateClassEnum@CWbemNamespace@@QEAAJPEAGJPEAUIWbemContext@@PEAVCBasicObjectSink@@@Z; CWbemNamespace::Exec_CreateClassEnum(ushort *,long,IWbemContext *,CBasicObjectSink *)
0x1800727fe  nop
0x1800727ff  jmp     loc_180072735
0x180072804  cmp     [rbx+30h], r12w
0x180072809  jnz     short loc_18007281A
0x18007280b  mov     r8d, r12d
0x18007280e  lea     rdx, psz
0x180072815  jmp     loc_1800725FF
0x18007281a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180072820  mov     ebx, 80041017h
0x180072825  mov     edx, ebx
0x180072827  mov     rcx, rax
0x18007282a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180072830  mov     rcx, cs:WPP_GLOBAL_Control
0x180072837  lea     rax, WPP_GLOBAL_Control
0x18007283e  cmp     rcx, rax
0x180072841  jz      loc_180072694
0x180072847  test    [rcx+1Ch], r12b
0x18007284b  jz      loc_180072694
0x180072851  cmp     byte ptr [rcx+19h], 2
0x180072855  jb      loc_180072694
0x18007285b  mov     edx, 6Fh ; 'o'
0x180072860  jmp     loc_18007267E
0x180072865  lea     rdx, aDynasty; "__DYNASTY"
0x18007286c  mov     rcx, rdi; unsigned __int16 *
0x18007286f  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x180072874  test    eax, eax
0x180072876  jnz     loc_180072A97
0x18007287c  movzx   eax, word ptr [rbx+30h]
0x180072880  cmp     ax, 8
0x180072884  jnz     loc_180072A33
0x18007288a  mov     r15, [rbx+38h]
0x18007288e  mov     [rbp+arg_8], r13
0x180072892  mov     [rsp+80h+var_58], r13; struct IWbemClassObject **
0x180072897  lea     rax, [rbp+arg_8]
0x18007289b  mov     [rsp+80h+var_60], rax; struct IWbemClassObject **
0x1800728a0  mov     r9, r14; struct IWbemContext *
0x1800728a3  xor     r8d, r8d; int
0x1800728a6  mov     rdx, r15; unsigned __int16 *
0x1800728a9  mov     rcx, rsi; this
0x1800728ac  call    ?Exec_GetObjectByPath@CWbemNamespace@@QEAAJPEBGJPEAUIWbemContext@@PEAPEAUIWbemClassObject@@2@Z; CWbemNamespace::Exec_GetObjectByPath(ushort const *,long,IWbemContext *,IWbemClassObject * *,IWbemClassObject * *)
0x1800728b1  mov     rdi, [rbp+arg_8]
0x1800728b5  mov     [rbp+arg_10], rdi
0x1800728b9  test    eax, eax
0x1800728bb  jns     short loc_180072929
0x1800728bd  mov     ebx, r13d
0x1800728c0  cmp     eax, 80041002h
0x1800728c5  cmovnz  ebx, eax
0x1800728c8  test    ebx, ebx
0x1800728ca  jns     short loc_180072914
0x1800728cc  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800728d2  mov     edx, ebx
0x1800728d4  mov     rcx, rax
0x1800728d7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800728dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800728e4  lea     rax, WPP_GLOBAL_Control
0x1800728eb  cmp     rcx, rax
0x1800728ee  jz      short loc_180072914
0x1800728f0  test    [rcx+1Ch], r12b
0x1800728f4  jz      short loc_180072914
0x1800728f6  cmp     byte ptr [rcx+19h], 2
0x1800728fa  jb      short loc_180072914
0x1800728fc  mov     edx, 70h ; 'p'
0x180072901  mov     r9d, ebx
0x180072904  lea     r8, WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids
0x18007290b  mov     rcx, [rcx+10h]
0x18007290f  call    WPP_SF_d
0x180072914  xor     r8d, r8d; struct IWbemClassObject *
0x180072917  mov     edx, ebx; int
0x180072919  mov     rcx, [rbp+arg_20]; this
0x18007291d  call    ?Return@CBasicObjectSink@@QEAAJJPEAUIWbemClassObject@@@Z; CBasicObjectSink::Return(long,IWbemClassObject *)
0x180072922  mov     ebx, eax
0x180072924  jmp     loc_1800729E4
0x180072929  lea     rcx, [rbp+var_38]
0x18007292d  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x180072933  nop
0x180072934  mov     rax, [rdi]
0x180072937  lea     rdx, [rbp+var_38]
0x18007293b  mov     rcx, rdi
0x18007293e  mov     rax, [rax+450h]
0x180072945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007294a  test    eax, eax
0x18007294c  jns     short loc_1800729A2
0x18007294e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180072954  mov     ebx, 80041001h
0x180072959  mov     edx, ebx
0x18007295b  mov     rcx, rax
0x18007295e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180072964  mov     rcx, cs:WPP_GLOBAL_Control
0x18007296b  lea     rax, WPP_GLOBAL_Control
0x180072972  cmp     rcx, rax
0x180072975  jz      short loc_18007299E
0x180072977  test    [rcx+1Ch], r12b
0x18007297b  jz      short loc_18007299E
0x18007297d  cmp     byte ptr [rcx+19h], 2
0x180072981  jb      short loc_18007299E
0x180072983  mov     edx, 71h ; 'q'
0x180072988  mov     r9d, 80041001h
0x18007298e  lea     r8, WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids
0x180072995  mov     rcx, [rcx+10h]
0x180072999  call    WPP_SF_d
0x18007299e  mov     edx, ebx
0x1800729a0  jmp     short loc_1800729CB
0x1800729a2  lea     rcx, [rbp+var_38]
0x1800729a6  call    cs:__imp_?IsNull@CVar@@QEAAHXZ; CVar::IsNull(void)
0x1800729ac  test    eax, eax
0x1800729ae  jnz     short loc_1800729C9
0x1800729b0  lea     rcx, [rbp+var_38]
0x1800729b4  call    cs:__imp_?GetLPWSTR@CVar@@QEAAPEAGXZ; CVar::GetLPWSTR(void)
0x1800729ba  mov     rcx, rax; unsigned __int16 *
0x1800729bd  mov     rdx, r15; unsigned __int16 *
0x1800729c0  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x1800729c5  test    eax, eax
0x1800729c7  jz      short loc_1800729ED
0x1800729c9  xor     edx, edx; int
0x1800729cb  xor     r8d, r8d; struct IWbemClassObject *
0x1800729ce  mov     rcx, [rbp+arg_20]; this
0x1800729d2  call    ?Return@CBasicObjectSink@@QEAAJJPEAUIWbemClassObject@@@Z; CBasicObjectSink::Return(long,IWbemClassObject *)
0x1800729d7  mov     ebx, eax
0x1800729d9  lea     rcx, [rbp+var_38]
0x1800729dd  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800729e3  nop
0x1800729e4  lea     rcx, [rbp+arg_10]
0x1800729e8  jmp     loc_180073122
0x1800729ed  mov     rbx, [rbp+arg_20]
0x1800729f1  lea     rcx, [rbx+8]
0x1800729f5  mov     rax, [rcx]
0x1800729f8  mov     rdx, rdi
0x1800729fb  mov     rax, [rax]
0x1800729fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072a03  mov     [rsp+80h+var_60], rbx; struct CBasicObjectSink *
0x180072a08  mov     r9, r14; struct IWbemContext *
0x180072a0b  xor     r8d, r8d; int
0x180072a0e  mov     rdx, r15; unsigned __int16 *
0x180072a11  mov     rcx, rsi; this
0x180072a14  call    ?Exec_CreateClassEnum@CWbemNamespace@@QEAAJPEAGJPEAUIWbemContext@@PEAVCBasicObjectSink@@@Z; CWbemNamespace::Exec_CreateClassEnum(ushort *,long,IWbemContext *,CBasicObjectSink *)
0x180072a19  nop
0x180072a1a  lea     rcx, [rbp+var_38]
0x180072a1e  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180072a24  nop
0x180072a25  lea     rcx, [rbp+arg_10]; this
0x180072a29  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x180072a2e  jmp     loc_180072613
0x180072a33  cmp     ax, r12w
  ... truncated ...
```
