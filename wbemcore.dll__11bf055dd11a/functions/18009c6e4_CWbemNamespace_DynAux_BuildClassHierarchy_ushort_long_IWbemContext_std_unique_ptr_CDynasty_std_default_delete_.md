# CWbemNamespace::DynAux_BuildClassHierarchy(ushort *,long,IWbemContext *,std::unique_ptr<CDynasty,std::default_delete<CDynasty>> &,IWbemClassObject * *)

- ea: `0x18009c6e4`
- end: `0x18009d046`
- name: `?DynAux_BuildClassHierarchy@CWbemNamespace@@QEAAJPEAGJPEAUIWbemContext@@AEAV?$unique_ptr@VCDynasty@@U?$default_delete@VCDynasty@@@std@@@std@@PEAPEAUIWbemClassObject@@@Z`
- size: `2402`
- prototype: `__int64 __usercall@<rax>(CWbemNamespace *this@<rcx>, unsigned __int16 *@<rdx>, int@<r8d>, __int64, struct IWbemClassObject **)`
- caller_count: `2`
- callee_count: `27`
- tags: `broker_com_uri`

## callers

- `0x180036444`
- `0x18003d3b0`

## callees

- `0x18000b140`
- `0x18000b17c`
- `0x18000b274`
- `0x18000b46c`
- `0x18000e9ac`
- `0x18000ea50`
- `0x18000ebd0`
- `0x18000ecf8`
- `0x18000faac`
- `0x1800121d0`
- `0x18003cdb8`
- `0x18003cfe0`
- `0x18003d050`
- `0x180050314`
- `0x180056620`
- `0x180057bdc`
- `0x18005d98c`
- `0x18005e85c`
- `0x180065990`
- `0x18008af38`
- `0x18008d51c`
- `0x18009c350`
- `0x18009c6e4`
- `0x1800a1a40`
- `0x1800a1b60`
- `0x1800a1b78`
- `0x1800da010`

## import_xrefs

- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18009cd86`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18009cd86`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18009ceed`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18009ceed`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18009cc9b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18009cd46`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18009cf97`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18009cfe7`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18009cc9b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18009cd46`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18009cf97`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18009cfe7`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18009cc32`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18009cc32`
- `wbemcomn!GetMemLogObject` at `0x18009c76d`
- `wbemcomn!GetMemLogObject` at `0x18009c808`
- `wbemcomn!GetMemLogObject` at `0x18009c873`
- `wbemcomn!GetMemLogObject` at `0x18009c96a`
- `wbemcomn!GetMemLogObject` at `0x18009c9e4`
- `wbemcomn!GetMemLogObject` at `0x18009ca5e`
- `wbemcomn!GetMemLogObject` at `0x18009caa3`
- `wbemcomn!GetMemLogObject` at `0x18009cb39`
- `wbemcomn!GetMemLogObject` at `0x18009cb95`
- `wbemcomn!GetMemLogObject` at `0x18009cc4d`
- `wbemcomn!GetMemLogObject` at `0x18009ccd7`
- `wbemcomn!GetMemLogObject` at `0x18009ce2e`
- `wbemcomn!GetMemLogObject` at `0x18009ce92`
- `wbemcomn!GetMemLogObject` at `0x18009cf4a`
- `wbemcomn!GetMemLogObject` at `0x18009c76d`
- `wbemcomn!GetMemLogObject` at `0x18009c808`
- `wbemcomn!GetMemLogObject` at `0x18009c873`
- `wbemcomn!GetMemLogObject` at `0x18009c96a`
- `wbemcomn!GetMemLogObject` at `0x18009c9e4`
- `wbemcomn!GetMemLogObject` at `0x18009ca5e`
- `wbemcomn!GetMemLogObject` at `0x18009caa3`
- `wbemcomn!GetMemLogObject` at `0x18009cb39`
- `wbemcomn!GetMemLogObject` at `0x18009cb95`
- `wbemcomn!GetMemLogObject` at `0x18009cc4d`
- `wbemcomn!GetMemLogObject` at `0x18009ccd7`
- `wbemcomn!GetMemLogObject` at `0x18009ce2e`
- `wbemcomn!GetMemLogObject` at `0x18009ce92`
- `wbemcomn!GetMemLogObject` at `0x18009cf4a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009c77b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009c813`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009c87e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009c975`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009c9f2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009ca6a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009cab5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009cb44`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009cba0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009cc5b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009cce3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009ce3a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009ce9e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009cf55`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009c77b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009c813`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009c87e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009c975`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009c9f2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009ca6a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009cab5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009cb44`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009cba0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009cc5b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009cce3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009ce3a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009ce9e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009cf55`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CWbemNamespace::DynAux_BuildClassHierarchy(
        struct IWmiDbSession **this,
        unsigned __int16 *a2,
        int a3,
        struct IWbemContext *a4,
        CDynasty **a5,
        struct IWbemClassObject **a6)
{
  struct CSynchronousSink *v9; // rax
  struct CBasicObjectSink *v10; // r15
  CMemoryLog *v11; // rax
  int ClassEnum; // ebx
  CMemoryLog *MemLogObject; // rax
  CClientCnt *v14; // rcx
  __int64 v15; // rdx
  CMemoryLog *v16; // rax
  int ObjectByPath; // eax
  unsigned int v18; // edx
  int v19; // r15d
  CMemoryLog *v20; // rax
  unsigned int v21; // edx
  CClientCnt *v22; // rcx
  __int64 v23; // rdx
  CDynasty *v24; // rcx
  struct CDynasty *v25; // rax
  CMemoryLog *v26; // rax
  unsigned int v27; // edx
  CMemoryLog *v28; // rax
  CMemoryLog *v29; // rax
  CMemoryLog *v30; // rax
  CMemoryLog *v31; // rax
  CFlexArray *v32; // r12
  int i; // r15d
  struct IWbemClassObject *v34; // rax
  struct CDynasty *v35; // rax
  unsigned int v36; // edx
  CMemoryLog *v37; // rax
  unsigned int v38; // edx
  CDynasty *v39; // rcx
  CMemoryLog *v40; // rax
  void *v41; // r13
  struct CDynasty **j; // rbx
  struct CDynasty *v43; // r15
  unsigned __int16 *v44; // r12
  __int64 v45; // r15
  __int64 v46; // rax
  bool v47; // sf
  CMemoryLog *v48; // rax
  CMemoryLog *v49; // rax
  CDynasty *v50; // rdx
  CMemoryLog *v51; // rax
  CMemoryLog *v53; // rax
  CMemoryLog *v54; // rax
  CDynasty *v55; // [rsp+30h] [rbp-A8h] BYREF
  struct CDynasty *v56; // [rsp+38h] [rbp-A0h] BYREF
  struct IWbemClassObject *v57; // [rsp+40h] [rbp-98h] BYREF
  __int64 v58[2]; // [rsp+48h] [rbp-90h] BYREF
  __int128 v59; // [rsp+58h] [rbp-80h] BYREF
  __int64 v60; // [rsp+68h] [rbp-70h]
  struct CBasicObjectSink *v61; // [rsp+70h] [rbp-68h] BYREF
  unsigned __int16 *v62; // [rsp+78h] [rbp-60h] BYREF
  __int64 v63; // [rsp+80h] [rbp-58h] BYREF
  int v64; // [rsp+88h] [rbp-50h] BYREF
  unsigned __int16 *v65; // [rsp+90h] [rbp-48h]

  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 396, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, a2);
  }
  *a6 = 0;
  v9 = CSynchronousSink::Create(0);
  v10 = v9;
  if ( v9 )
  {
    (*(void (__fastcall **)(struct CSynchronousSink *))(*(_QWORD *)v9 + 8LL))(v9);
    v61 = v10;
    ClassEnum = CWbemNamespace::Exec_CreateClassEnum((CWbemNamespace *)this, a2, a3 | 0x80000000, a4, v10);
    LODWORD(v57) = ClassEnum;
    if ( ClassEnum < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, ClassEnum);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_118;
      }
      v15 = 398;
      goto LABEL_20;
    }
    CSynchronousSink::Block(v10);
    CSynchronousSink::GetStatus(v10, (int *)&v57, 0, a6);
    ClassEnum = (int)v57;
    if ( (int)v57 < 0 )
    {
      v16 = GetMemLogObject();
      CMemoryLog::Write(v16, ClassEnum);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_118;
      }
      v15 = 399;
LABEL_20:
      WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, (unsigned int)ClassEnum);
      goto LABEL_118;
    }
    v55 = 0;
    ClassEnum = CRepository::BuildClassHierarchy(this[5], this[7], a2, (__int64)&v55);
    if ( ClassEnum == -2147217406 )
    {
      v57 = 0;
      ObjectByPath = CWbemNamespace::Exec_GetObjectByPath((CWbemNamespace *)this, a2, a3, a4, &v57, a6);
      ClassEnum = ObjectByPath;
      if ( ObjectByPath < 0 )
      {
        v19 = -2147217406;
        if ( ObjectByPath == -2147217406 )
        {
LABEL_24:
          if ( v55 )
            CDynasty::`scalar deleting destructor'(v55, v18);
          ClassEnum = v19;
          goto LABEL_118;
        }
        v20 = GetMemLogObject();
        CMemoryLog::Write(v20, ClassEnum);
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_32;
        }
        v23 = 400;
LABEL_31:
        WPP_SF_d(*((_QWORD *)v22 + 2), v23, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, (unsigned int)ClassEnum);
        goto LABEL_32;
      }
      v56 = (struct CDynasty *)v57;
      v25 = CDynasty::Create(v57);
      std::unique_ptr<CDynasty>::reset(&v55, v25);
      if ( !v55 )
      {
        v26 = GetMemLogObject();
        CMemoryLog::Write(v26, -2147217402);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            401,
            WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            2147749894LL);
        }
        CReleaseMe::release((CReleaseMe *)&v56);
        if ( v55 )
          CDynasty::`scalar deleting destructor'(v55, v27);
        ClassEnum = -2147217402;
        goto LABEL_118;
      }
      if ( !*((_QWORD *)v55 + 1) )
      {
        v28 = GetMemLogObject();
        CMemoryLog::Write(v28, -1);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 402, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, a2);
        }
        v29 = GetMemLogObject();
        v19 = -2147217404;
        CMemoryLog::Write(v29, -2147217404);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            403,
            WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            2147749892LL);
        }
        CReleaseMe::release((CReleaseMe *)&v56);
        goto LABEL_24;
      }
      CReleaseMe::release((CReleaseMe *)&v56);
    }
    else if ( ClassEnum < 0 )
    {
      v31 = GetMemLogObject();
      CMemoryLog::Write(v31, ClassEnum);
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_32;
      }
      v23 = 404;
      goto LABEL_31;
    }
    v58[0] = 0;
    v58[1] = 0;
    v58[0] = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<unsigned short * const,CDynasty *>,wbem_allocator<CDynasty *>>>::_Buyheadnode();
    ClassEnum = AddAllMembers((const unsigned __int16 **)v55, v58);
    if ( ClassEnum >= 0 )
    {
      v32 = (struct CBasicObjectSink *)((char *)v10 + 64);
      v59 = 0;
      v60 = 0;
      try
      {
        if ( *(_DWORD *)v32 )
        {
          if ( (unsigned __int64)*(int *)v32 > 0x1FFFFFFFFFFFFFFFLL )
            std::vector<CDynasty *,wbem_allocator<CDynasty *>>::_Xlen();
          std::vector<CDynasty *,wbem_allocator<CDynasty *>>::_Reallocate(&v59);
        }
      }
      catch ( CX_MemoryException )
      {
        v54 = GetMemLogObject();
        CMemoryLog::Write(v54, -2147217402);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            406,
            WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            2147749894LL);
        }
        if ( (_QWORD)v59 )
        {
          CWin32DefaultArena::WbemMemFree((void *)v59);
          v59 = 0;
          v60 = 0;
        }
        std::_Tree<std::_Tmap_traits<unsigned short *,CDynasty *,wcsiless,wbem_allocator<CDynasty *>,0>>::~_Tree<std::_Tmap_traits<unsigned short *,CDynasty *,wcsiless,wbem_allocator<CDynasty *>,0>>(v58);
        v39 = v55;
        if ( v55 )
        {
LABEL_122:
          if ( v39 )
            CDynasty::`scalar deleting destructor'(v39, v38);
        }
        CReleaseMe::release((CReleaseMe *)&v61);
        return 2147749894LL;
      }
      for ( i = 0; i < *(_DWORD *)v32; ++i )
      {
        v34 = (struct IWbemClassObject *)CFlexArray::GetAt(v32, i);
        v35 = CDynasty::Create(v34);
        v56 = v35;
        if ( !v35 )
        {
          v37 = GetMemLogObject();
          CMemoryLog::Write(v37, -2147217402);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              407,
              WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
              2147749894LL);
          }
          if ( (_QWORD)v59 )
          {
            CWin32DefaultArena::WbemMemFree((void *)v59);
            v59 = 0;
            v60 = 0;
          }
LABEL_76:
          std::_Tree<std::_Tmap_traits<unsigned short *,CDynasty *,wcsiless,wbem_allocator<CDynasty *>,0>>::~_Tree<std::_Tmap_traits<unsigned short *,CDynasty *,wcsiless,wbem_allocator<CDynasty *>,0>>(v58);
          v39 = v55;
          goto LABEL_122;
        }
        if ( *((_QWORD *)v35 + 1) )
        {
          try
          {
            *(_QWORD *)std::map<unsigned short *,CDynasty *,wcsiless,wbem_allocator<CDynasty *>>::operator[](v58, v35) = v35;
            std::vector<CDynasty *,wbem_allocator<CDynasty *>>::push_back(&v59, &v56);
          }
          catch ( CX_MemoryException )
          {
            v53 = GetMemLogObject();
            CMemoryLog::Write(v53, -2147217402);
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                409,
                WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                2147749894LL);
            }
            if ( (_QWORD)v59 )
            {
              CWin32DefaultArena::WbemMemFree((void *)v59);
              v59 = 0;
              v60 = 0;
            }
            goto LABEL_76;
          }
        }
        else
        {
          CDynasty::`scalar deleting destructor'(v35, v36);
          v40 = GetMemLogObject();
          CMemoryLog::Write(v40, -1);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 408, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids);
          }
        }
      }
      v41 = (void *)v59;
      for ( j = (struct CDynasty **)v59; j != *((struct CDynasty ***)&v59 + 1); ++j )
      {
        v56 = *j;
        v43 = v56;
        CVar::CVar((CVar *)&v64);
        if ( (*(int (__fastcall **)(_QWORD, int *))(**((_QWORD **)v43 + 1) + 1112LL))(*((_QWORD *)v43 + 1), &v64) < 0
          || v64 == 1 )
        {
          v49 = GetMemLogObject();
          CMemoryLog::Write(v49, -1);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_SS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              410,
              (unsigned int)WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
              *(_QWORD *)v43,
              (__int64)a2);
          }
        }
        else
        {
          v44 = v65;
          v62 = v65;
          std::_Tree<std::_Tmap_traits<unsigned short *,CDynasty *,wcsiless,wbem_allocator<CDynasty *>,0>>::lower_bound(
            v58,
            &v63,
            &v62);
          v45 = v63;
          v46 = v58[0];
          if ( v63 == v58[0]
            || (v47 = (int)wbem_wcsicmp(v44, *(const unsigned __int16 **)(v63 + 32)) < 0, v46 = v58[0], v47) )
          {
            v45 = v46;
          }
          if ( v45 == v46 )
          {
            if ( (unsigned int)wbem_wcsicmp(*(const unsigned __int16 **)v56, a2) )
            {
              v48 = GetMemLogObject();
              CMemoryLog::Write(v48, -1);
              if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 411, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v65);
              }
            }
          }
          else
          {
            CDynasty::AddChild(*(CDynasty **)(v45 + 40), v56);
          }
        }
        CVar::~CVar((CVar *)&v64);
      }
      if ( a5 != &v55 )
      {
        v50 = v55;
        v55 = 0;
        std::unique_ptr<CDynasty>::reset(a5, v50);
      }
      ClassEnum = CWbemNamespace::DynAux_BuildChainUp((CWbemNamespace *)this, a4);
      if ( ClassEnum < 0 )
      {
        v51 = GetMemLogObject();
        CMemoryLog::Write(v51, ClassEnum);
      }
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          412,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          (unsigned int)ClassEnum);
      }
      if ( v41 )
      {
        CWin32DefaultArena::WbemMemFree(v41);
        v59 = 0;
        v60 = 0;
      }
      std::_Tree<std::_Tmap_traits<unsigned short *,CDynasty *,wcsiless,wbem_allocator<CDynasty *>,0>>::~_Tree<std::_Tmap_traits<unsigned short *,CDynasty *,wcsiless,wbem_allocator<CDynasty *>,0>>(v58);
      v24 = v55;
      if ( !v55 )
      {
LABEL_118:
        CReleaseMe::release((CReleaseMe *)&v61);
        return (unsigned int)ClassEnum;
      }
LABEL_116:
      if ( v24 )
        CDynasty::`scalar deleting destructor'(v24, v21);
      goto LABEL_118;
    }
    v30 = GetMemLogObject();
    CMemoryLog::Write(v30, ClassEnum);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        405,
        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
        (unsigned int)ClassEnum);
    }
    std::_Tree<std::_Tmap_traits<unsigned short *,CDynasty *,wcsiless,wbem_allocator<CDynasty *>,0>>::~_Tree<std::_Tmap_traits<unsigned short *,CDynasty *,wcsiless,wbem_allocator<CDynasty *>,0>>(v58);
LABEL_32:
    v24 = v55;
    goto LABEL_116;
  }
  v11 = GetMemLogObject();
  CMemoryLog::Write(v11, -2147217402);
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 397, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749894LL);
  }
  return 2147749894LL;
}

```

## disassembly

```asm
0x18009c6e4  mov     [rsp+arg_18], r9
0x18009c6e9  mov     [rsp+arg_8], rdx
0x18009c6ee  mov     [rsp+arg_0], rcx
0x18009c6f3  push    rbx
0x18009c6f4  push    r12
0x18009c6f6  push    r13
0x18009c6f8  push    r14
0x18009c6fa  push    r15
0x18009c6fc  sub     rsp, 0B0h
0x18009c703  mov     r12d, r8d
0x18009c706  mov     r13, rdx
0x18009c709  mov     rbx, rcx
0x18009c70c  lea     rax, WPP_GLOBAL_Control
0x18009c713  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c71a  cmp     rcx, rax
0x18009c71d  jz      short loc_18009C748
0x18009c71f  test    byte ptr [rcx+1Ch], 1
0x18009c723  jz      short loc_18009C748
0x18009c725  cmp     byte ptr [rcx+19h], 5
0x18009c729  jb      short loc_18009C748
0x18009c72b  mov     edx, 18Ch
0x18009c730  mov     r9, r13
0x18009c733  lea     r14, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18009c73a  mov     r8, r14
0x18009c73d  mov     rcx, [rcx+10h]
0x18009c741  call    WPP_SF_S
0x18009c746  jmp     short loc_18009C74F
0x18009c748  lea     r14, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18009c74f  mov     rax, [rsp+0D8h+arg_28]
0x18009c757  mov     qword ptr [rax], 0
0x18009c75e  xor     ecx, ecx; struct IWbemObjectSinkEx *
0x18009c760  call    ?Create@CSynchronousSink@@SAPEAV1@PEAUIWbemObjectSinkEx@@@Z; CSynchronousSink::Create(IWbemObjectSinkEx *)
0x18009c765  mov     r15, rax
0x18009c768  test    rax, rax
0x18009c76b  jnz     short loc_18009C7C8
0x18009c76d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009c773  mov     edx, 80041006h
0x18009c778  mov     rcx, rax
0x18009c77b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009c781  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c788  lea     r13, WPP_GLOBAL_Control
0x18009c78f  cmp     rcx, r13
0x18009c792  jz      loc_18009D029
0x18009c798  test    byte ptr [rcx+1Ch], 1
0x18009c79c  jz      loc_18009D029
0x18009c7a2  cmp     byte ptr [rcx+19h], 2
0x18009c7a6  jb      loc_18009D029
0x18009c7ac  mov     edx, 18Dh
0x18009c7b1  mov     r9d, 80041006h
0x18009c7b7  mov     r8, r14
0x18009c7ba  mov     rcx, [rcx+10h]
0x18009c7be  call    WPP_SF_d
0x18009c7c3  jmp     loc_18009D029
0x18009c7c8  mov     rax, [rax]
0x18009c7cb  mov     rcx, r15
0x18009c7ce  mov     rax, [rax+8]
0x18009c7d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c7d7  mov     [rsp+0D8h+var_68], r15
0x18009c7dc  mov     r8d, r12d
0x18009c7df  or      r8d, 80000000h; int
0x18009c7e6  mov     [rsp+0D8h+var_B8], r15; struct CBasicObjectSink *
0x18009c7eb  mov     r9, [rsp+0D8h+arg_18]; struct IWbemContext *
0x18009c7f3  mov     rdx, r13; unsigned __int16 *
0x18009c7f6  mov     rcx, rbx; this
0x18009c7f9  call    ?Exec_CreateClassEnum@CWbemNamespace@@QEAAJPEAGJPEAUIWbemContext@@PEAVCBasicObjectSink@@@Z; CWbemNamespace::Exec_CreateClassEnum(ushort *,long,IWbemContext *,CBasicObjectSink *)
0x18009c7fe  mov     ebx, eax
0x18009c800  mov     dword ptr [rsp+0D8h+var_98], eax
0x18009c804  test    eax, eax
0x18009c806  jns     short loc_18009C84B
0x18009c808  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009c80e  mov     edx, ebx
0x18009c810  mov     rcx, rax
0x18009c813  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009c819  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c820  lea     r13, WPP_GLOBAL_Control
0x18009c827  cmp     rcx, r13
0x18009c82a  jz      loc_18009CFCF
0x18009c830  test    byte ptr [rcx+1Ch], 1
0x18009c834  jz      loc_18009CFCF
0x18009c83a  cmp     byte ptr [rcx+19h], 2
0x18009c83e  jb      loc_18009CFCF
0x18009c844  mov     edx, 18Eh
0x18009c849  jmp     short loc_18009C8B4
0x18009c84b  mov     rcx, r15; this
0x18009c84e  call    ?Block@CSynchronousSink@@QEAAXXZ; CSynchronousSink::Block(void)
0x18009c853  mov     r9, [rsp+0D8h+arg_28]; struct IWbemClassObject **
0x18009c85b  xor     r8d, r8d; unsigned __int16 **
0x18009c85e  lea     rdx, [rsp+0D8h+var_98]; int *
0x18009c863  mov     rcx, r15; this
0x18009c866  call    ?GetStatus@CSynchronousSink@@QEAAXPEAJPEAPEAGPEAPEAUIWbemClassObject@@@Z; CSynchronousSink::GetStatus(long *,ushort * *,IWbemClassObject * *)
0x18009c86b  mov     ebx, dword ptr [rsp+0D8h+var_98]
0x18009c86f  test    ebx, ebx
0x18009c871  jns     short loc_18009C8C8
0x18009c873  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009c879  mov     edx, ebx
0x18009c87b  mov     rcx, rax
0x18009c87e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009c884  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c88b  lea     r13, WPP_GLOBAL_Control
0x18009c892  cmp     rcx, r13
0x18009c895  jz      loc_18009CFCF
0x18009c89b  test    byte ptr [rcx+1Ch], 1
0x18009c89f  jz      loc_18009CFCF
0x18009c8a5  cmp     byte ptr [rcx+19h], 2
0x18009c8a9  jb      loc_18009CFCF
0x18009c8af  mov     edx, 18Fh
0x18009c8b4  mov     r9d, ebx
0x18009c8b7  mov     r8, r14
0x18009c8ba  mov     rcx, [rcx+10h]
0x18009c8be  call    WPP_SF_d
0x18009c8c3  jmp     loc_18009CFCF
0x18009c8c8  mov     [rsp+0D8h+var_A8], 0
0x18009c8d1  mov     r9d, r12d
0x18009c8d4  and     r9d, 1
0x18009c8d8  lea     rax, [rsp+0D8h+var_A8]
0x18009c8dd  mov     [rsp+0D8h+var_B8], rax; __int64
0x18009c8e2  mov     r8, r13; unsigned __int16 *
0x18009c8e5  mov     rax, [rsp+0D8h+arg_0]
0x18009c8ed  mov     rdx, [rax+38h]; struct IWmiDbHandle *
0x18009c8f1  mov     rcx, [rax+28h]; struct IWmiDbSession *
0x18009c8f5  call    ?BuildClassHierarchy@CRepository@@SAJPEAUIWmiDbSession@@PEAUIWmiDbHandle@@PEBGJAEAV?$unique_ptr@VCDynasty@@U?$default_delete@VCDynasty@@@std@@@std@@@Z; CRepository::BuildClassHierarchy(IWmiDbSession *,IWmiDbHandle *,ushort const *,long,std::unique_ptr<CDynasty> &)
0x18009c8fa  mov     ebx, eax
0x18009c8fc  cmp     eax, 80041002h
0x18009c901  jnz     loc_18009CB8D
0x18009c907  mov     [rsp+0D8h+var_98], 0
0x18009c910  mov     rax, [rsp+0D8h+arg_28]
0x18009c918  mov     [rsp+0D8h+var_B0], rax; struct IWbemClassObject **
0x18009c91d  lea     rax, [rsp+0D8h+var_98]
0x18009c922  mov     [rsp+0D8h+var_B8], rax; struct IWbemClassObject **
0x18009c927  mov     r9, [rsp+0D8h+arg_18]; struct IWbemContext *
0x18009c92f  mov     r8d, r12d; int
0x18009c932  mov     rdx, r13; unsigned __int16 *
0x18009c935  mov     rcx, [rsp+0D8h+arg_0]; this
0x18009c93d  call    ?Exec_GetObjectByPath@CWbemNamespace@@QEAAJPEBGJPEAUIWbemContext@@PEAPEAUIWbemClassObject@@2@Z; CWbemNamespace::Exec_GetObjectByPath(ushort const *,long,IWbemContext *,IWbemClassObject * *,IWbemClassObject * *)
0x18009c942  mov     ebx, eax
0x18009c944  test    eax, eax
0x18009c946  jns     short loc_18009C9B9
0x18009c948  mov     r15d, 80041002h
0x18009c94e  cmp     eax, r15d
0x18009c951  jnz     short loc_18009C96A
0x18009c953  mov     rcx, [rsp+0D8h+var_A8]; this
0x18009c958  test    rcx, rcx
0x18009c95b  jz      short loc_18009C962
0x18009c95d  call    ??_GCDynasty@@QEAAPEAXI@Z; CDynasty::`scalar deleting destructor'(uint)
0x18009c962  mov     ebx, r15d
0x18009c965  jmp     loc_18009CFCF
0x18009c96a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009c970  mov     edx, ebx
0x18009c972  mov     rcx, rax
0x18009c975  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009c97b  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c982  lea     r13, WPP_GLOBAL_Control
0x18009c989  cmp     rcx, r13
0x18009c98c  jz      short loc_18009C9AF
0x18009c98e  test    byte ptr [rcx+1Ch], 1
0x18009c992  jz      short loc_18009C9AF
0x18009c994  cmp     byte ptr [rcx+19h], 2
0x18009c998  jb      short loc_18009C9AF
0x18009c99a  mov     edx, 190h
0x18009c99f  mov     r9d, ebx
0x18009c9a2  mov     r8, r14
0x18009c9a5  mov     rcx, [rcx+10h]
0x18009c9a9  call    WPP_SF_d
0x18009c9ae  nop
0x18009c9af  mov     rcx, [rsp+0D8h+var_A8]
0x18009c9b4  jmp     loc_18009CFC4
0x18009c9b9  mov     rax, [rsp+0D8h+var_98]
0x18009c9be  mov     [rsp+0D8h+var_A0], rax
0x18009c9c3  mov     rcx, [rsp+0D8h+var_98]; struct IWbemClassObject *
0x18009c9c8  call    ?Create@CDynasty@@SAPEAV1@PEAUIWbemClassObject@@@Z; CDynasty::Create(IWbemClassObject *)
0x18009c9cd  mov     rdx, rax
0x18009c9d0  lea     rcx, [rsp+0D8h+var_A8]
0x18009c9d5  call    ?reset@?$unique_ptr@VCDynasty@@U?$default_delete@VCDynasty@@@std@@@std@@QEAAXPEAVCDynasty@@@Z; std::unique_ptr<CDynasty>::reset(CDynasty *)
0x18009c9da  mov     rax, [rsp+0D8h+var_A8]
0x18009c9df  test    rax, rax
0x18009c9e2  jnz     short loc_18009CA53
0x18009c9e4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009c9ea  mov     edx, 80041006h
0x18009c9ef  mov     rcx, rax
0x18009c9f2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009c9f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c9ff  lea     r13, WPP_GLOBAL_Control
0x18009ca06  cmp     rcx, r13
0x18009ca09  jz      short loc_18009CA2F
0x18009ca0b  test    byte ptr [rcx+1Ch], 1
0x18009ca0f  jz      short loc_18009CA2F
0x18009ca11  cmp     byte ptr [rcx+19h], 2
0x18009ca15  jb      short loc_18009CA2F
0x18009ca17  mov     edx, 191h
0x18009ca1c  mov     r9d, 80041006h
0x18009ca22  mov     r8, r14
0x18009ca25  mov     rcx, [rcx+10h]
0x18009ca29  call    WPP_SF_d
0x18009ca2e  nop
0x18009ca2f  lea     rcx, [rsp+0D8h+var_A0]; this
0x18009ca34  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x18009ca39  nop
0x18009ca3a  mov     rcx, [rsp+0D8h+var_A8]; this
0x18009ca3f  test    rcx, rcx
0x18009ca42  jz      short loc_18009CA49
0x18009ca44  call    ??_GCDynasty@@QEAAPEAXI@Z; CDynasty::`scalar deleting destructor'(uint)
0x18009ca49  mov     ebx, 80041006h
0x18009ca4e  jmp     loc_18009CFCF
0x18009ca53  cmp     qword ptr [rax+8], 0
0x18009ca58  jnz     loc_18009CAFA
0x18009ca5e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009ca64  or      edx, 0FFFFFFFFh
0x18009ca67  mov     rcx, rax
0x18009ca6a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009ca70  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ca77  lea     rbx, WPP_GLOBAL_Control
0x18009ca7e  cmp     rcx, rbx
0x18009ca81  jz      short loc_18009CAA3
0x18009ca83  test    byte ptr [rcx+1Ch], 1
0x18009ca87  jz      short loc_18009CAA3
0x18009ca89  cmp     byte ptr [rcx+19h], 2
0x18009ca8d  jb      short loc_18009CAA3
0x18009ca8f  mov     edx, 192h
0x18009ca94  mov     r9, r13
0x18009ca97  mov     r8, r14
0x18009ca9a  mov     rcx, [rcx+10h]
0x18009ca9e  call    WPP_SF_S
0x18009caa3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009caa9  mov     r15d, 80041004h
0x18009caaf  mov     edx, r15d
0x18009cab2  mov     rcx, rax
0x18009cab5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009cabb  mov     rcx, cs:WPP_GLOBAL_Control
0x18009cac2  cmp     rcx, rbx
0x18009cac5  jz      short loc_18009CAEB
0x18009cac7  test    byte ptr [rcx+1Ch], 1
0x18009cacb  jz      short loc_18009CAEB
0x18009cacd  cmp     byte ptr [rcx+19h], 2
0x18009cad1  jb      short loc_18009CAEB
0x18009cad3  mov     edx, 193h
0x18009cad8  mov     r9d, 80041004h
0x18009cade  mov     r8, r14
0x18009cae1  mov     rcx, [rcx+10h]
0x18009cae5  call    WPP_SF_d
0x18009caea  nop
0x18009caeb  lea     rcx, [rsp+0D8h+var_A0]; this
0x18009caf0  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x18009caf5  jmp     loc_18009C953
0x18009cafa  lea     rcx, [rsp+0D8h+var_A0]; this
0x18009caff  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x18009cb04  mov     [rsp+0D8h+var_90], 0
0x18009cb0d  mov     [rsp+0D8h+var_88], 0
0x18009cb16  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@QEAGPEAVCDynasty@@@std@@V?$wbem_allocator@PEAVCDynasty@@@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEAGPEAVCDynasty@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<ushort * const,CDynasty *>,wbem_allocator<CDynasty *>>>::_Buyheadnode(void)
0x18009cb1b  mov     [rsp+0D8h+var_90], rax
0x18009cb20  lea     rdx, [rsp+0D8h+var_90]
0x18009cb25  mov     rcx, [rsp+0D8h+var_A8]
0x18009cb2a  call    ?AddAllMembers@@YAJPEAVCDynasty@@AEAV?$map@PEAGPEAVCDynasty@@Vwcsiless@@V?$wbem_allocator@PEAVCDynasty@@@@@std@@@Z; AddAllMembers(CDynasty *,std::map<ushort *,CDynasty *,wcsiless,wbem_allocator<CDynasty *>> &)
0x18009cb2f  mov     ebx, eax
0x18009cb31  test    eax, eax
0x18009cb33  jns     loc_18009CBDB
0x18009cb39  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009cb3f  mov     edx, ebx
0x18009cb41  mov     rcx, rax
0x18009cb44  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009cb4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18009cb51  lea     r13, WPP_GLOBAL_Control
0x18009cb58  cmp     rcx, r13
0x18009cb5b  jz      short loc_18009CB7E
0x18009cb5d  test    byte ptr [rcx+1Ch], 1
0x18009cb61  jz      short loc_18009CB7E
0x18009cb63  cmp     byte ptr [rcx+19h], 2
0x18009cb67  jb      short loc_18009CB7E
0x18009cb69  mov     edx, 195h
0x18009cb6e  mov     r9d, ebx
0x18009cb71  mov     r8, r14
0x18009cb74  mov     rcx, [rcx+10h]
0x18009cb78  call    WPP_SF_d
0x18009cb7d  nop
0x18009cb7e  lea     rcx, [rsp+0D8h+var_90]
0x18009cb83  call    ??1?$_Tree@V?$_Tmap_traits@PEAGPEAVCDynasty@@Vwcsiless@@V?$wbem_allocator@PEAVCDynasty@@@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ushort *,CDynasty *,wcsiless,wbem_allocator<CDynasty *>,0>>::~_Tree<std::_Tmap_traits<ushort *,CDynasty *,wcsiless,wbem_allocator<CDynasty *>,0>>(void)
0x18009cb88  jmp     loc_18009C9AF
0x18009cb8d  test    ebx, ebx
0x18009cb8f  jns     loc_18009CB04
0x18009cb95  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009cb9b  mov     edx, ebx
0x18009cb9d  mov     rcx, rax
0x18009cba0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009cba6  mov     rcx, cs:WPP_GLOBAL_Control
0x18009cbad  lea     r13, WPP_GLOBAL_Control
0x18009cbb4  cmp     rcx, r13
0x18009cbb7  jz      loc_18009C9AF
0x18009cbbd  test    byte ptr [rcx+1Ch], 1
0x18009cbc1  jz      loc_18009C9AF
0x18009cbc7  cmp     byte ptr [rcx+19h], 2
0x18009cbcb  jb      loc_18009C9AF
0x18009cbd1  mov     edx, 194h
0x18009cbd6  jmp     loc_18009C99F
0x18009cbdb  lea     r12, [r15+40h]
0x18009cbdf  xorps   xmm0, xmm0
0x18009cbe2  movdqu  [rsp+0D8h+var_80], xmm0
0x18009cbe8  mov     [rsp+0D8h+var_70], 0
0x18009cbf1  movsxd  rdx, dword ptr [r12]
0x18009cbf5  test    rdx, rdx
0x18009cbf8  jz      short loc_18009CC18
0x18009cbfa  mov     rax, 1FFFFFFFFFFFFFFFh
  ... truncated ...
```
