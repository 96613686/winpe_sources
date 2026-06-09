# CInternalMerger::AddChildObjects(long,IWbemClassObject * *,bool,long *)

- ea: `0x180033764`
- end: `0x180034107`
- name: `?AddChildObjects@CInternalMerger@@IEAAJJPEAPEAUIWbemClassObject@@_NPEAJ@Z`
- size: `2467`
- prototype: `__int64 __fastcall(CInternalMerger *this, int, struct IWbemClassObject **, char, int *)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180031860`
- `0x1800c01a0`

## callees

- `0x18000b140`
- `0x18000b17c`
- `0x18000b46c`
- `0x180031228`
- `0x180031dc4`
- `0x1800320ec`
- `0x1800322a8`
- `0x180033764`
- `0x180034110`
- `0x1800343b0`
- `0x180034e20`
- `0x1800357e0`
- `0x18003594c`
- `0x18006f6d0`
- `0x1800da010`

## import_xrefs

- `msvcrt!wcschr` at `0x18003390c`
- `msvcrt!wcschr` at `0x18003390c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800337b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800337b1`
- `wbemcomn!?Empty@WString@@QEAAXXZ` at `0x180033f33`
- `wbemcomn!?Empty@WString@@QEAAXXZ` at `0x180033f85`
- `wbemcomn!?Empty@WString@@QEAAXXZ` at `0x180033f33`
- `wbemcomn!?Empty@WString@@QEAAXXZ` at `0x180033f85`
- `wbemcomn!?Empty@CWStringArray@@QEAAXXZ` at `0x180033cb2`
- `wbemcomn!?Empty@CWStringArray@@QEAAXXZ` at `0x180033cb2`
- `wbemcomn!?Enter@CCheckedInCritSec@@QEAAXXZ` at `0x180033cc0`
- `wbemcomn!?Enter@CCheckedInCritSec@@QEAAXXZ` at `0x180033cc0`
- `wbemcomn!??1WString@@QEAA@XZ` at `0x1800339e6`
- `wbemcomn!??1WString@@QEAA@XZ` at `0x1800340b7`
- `wbemcomn!??1WString@@QEAA@XZ` at `0x1800339e6`
- `wbemcomn!??1WString@@QEAA@XZ` at `0x1800340b7`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180033b74`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180033ec5`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180034014`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180033b74`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180033ec5`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180034014`
- `wbemcomn!??0WString@@QEAA@XZ` at `0x1800338dd`
- `wbemcomn!??0WString@@QEAA@XZ` at `0x1800338dd`
- `wbemcomn!??4WString@@QEAAAEAV0@PEBG@Z` at `0x180033924`
- `wbemcomn!??4WString@@QEAAAEAV0@PEBG@Z` at `0x180033924`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003392d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003392d`
- `wbemcomn!??0CWStringArray@@QEAA@HH@Z` at `0x18003385d`
- `wbemcomn!??0CWStringArray@@QEAA@HH@Z` at `0x18003385d`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180033d45`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180033d45`
- `wbemcomn!?Add@CWStringArray@@QEAAHPEBG@Z` at `0x180033b85`
- `wbemcomn!?Add@CWStringArray@@QEAAHPEBG@Z` at `0x180033b85`
- `wbemcomn!??0CCheckedInCritSec@@QEAA@PEAVCCritSec@@@Z` at `0x180033873`
- `wbemcomn!??0CCheckedInCritSec@@QEAA@PEAVCCritSec@@@Z` at `0x180033873`
- `wbemcomn!??1CCheckedInCritSec@@QEAA@XZ` at `0x180033d36`
- `wbemcomn!??1CCheckedInCritSec@@QEAA@XZ` at `0x180033d36`
- `wbemcomn!?Leave@CCheckedInCritSec@@QEAAXXZ` at `0x180033c00`
- `wbemcomn!?Leave@CCheckedInCritSec@@QEAAXXZ` at `0x180033cdd`
- `wbemcomn!?Leave@CCheckedInCritSec@@QEAAXXZ` at `0x180033c00`
- `wbemcomn!?Leave@CCheckedInCritSec@@QEAAXXZ` at `0x180033cdd`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x18003397f`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x180033a2b`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x18003397f`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x180033a2b`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800339a0`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180033a50`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800339a0`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180033a50`
- `wbemcomn!??0CFlexArray@@QEAA@HH@Z` at `0x180033835`
- `wbemcomn!??0CFlexArray@@QEAA@HH@Z` at `0x180033835`
- `wbemcomn!GetMemLogObject` at `0x1800339b8`
- `wbemcomn!GetMemLogObject` at `0x180033e6d`
- `wbemcomn!GetMemLogObject` at `0x180033e83`
- `wbemcomn!GetMemLogObject` at `0x180033eef`
- `wbemcomn!GetMemLogObject` at `0x180033f3e`
- `wbemcomn!GetMemLogObject` at `0x180033fd2`
- `wbemcomn!GetMemLogObject` at `0x180034065`
- `wbemcomn!GetMemLogObject` at `0x1800339b8`
- `wbemcomn!GetMemLogObject` at `0x180033e6d`
- `wbemcomn!GetMemLogObject` at `0x180033e83`
- `wbemcomn!GetMemLogObject` at `0x180033eef`
- `wbemcomn!GetMemLogObject` at `0x180033f3e`
- `wbemcomn!GetMemLogObject` at `0x180033fd2`
- `wbemcomn!GetMemLogObject` at `0x180034065`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800339c4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180033e78`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180033e8f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180033efb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180033f4a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180033fde`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180034071`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800339c4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180033e78`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180033e8f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180033efb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180033f4a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180033fde`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180034071`
- `FastProx!?AsymmetricMerge@CWbemInstance@@SAJPEAV1@0@Z` at `0x180033a0c`
- `FastProx!?AsymmetricMerge@CWbemInstance@@SAJPEAV1@0@Z` at `0x180033a0c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CInternalMerger::AddChildObjects(
        CInternalMerger *this,
        int a2,
        struct IWbemClassObject **a3,
        char a4,
        int *a5)
{
  CInternalMerger *v7; // r14
  int v8; // esi
  __int64 v9; // rbx
  DWORD TickCount; // eax
  __int64 i; // rbx
  int v12; // ebx
  struct IWbemClassObject *v13; // r15
  const wchar_t *v14; // rax
  wchar_t *v15; // rbx
  wchar_t *v16; // rax
  __int64 v17; // rbx
  CMemoryLog *v18; // rax
  int j; // eax
  int v20; // eax
  bool v21; // r15
  char *v22; // rcx
  int v23; // ecx
  __int64 v24; // rbx
  int v25; // eax
  int v26; // r8d
  int v27; // edx
  const unsigned __int16 *v28; // rax
  int v29; // ebx
  int v30; // r15d
  CMemoryLog *v32; // rax
  CMemoryLog *v33; // rax
  __int64 v34; // rax
  CMemoryLog *v35; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v37; // rax
  __int64 v38; // rax
  CMemoryLog *v39; // rax
  int v40; // [rsp+50h] [rbp-188h]
  int v41; // [rsp+54h] [rbp-184h]
  int v42; // [rsp+58h] [rbp-180h]
  int v43; // [rsp+60h] [rbp-178h]
  int v44; // [rsp+64h] [rbp-174h]
  int v45; // [rsp+68h] [rbp-170h]
  char v46[8]; // [rsp+70h] [rbp-168h] BYREF
  int v47; // [rsp+78h] [rbp-160h]
  int v48; // [rsp+7Ch] [rbp-15Ch]
  int v49; // [rsp+80h] [rbp-158h]
  int v50; // [rsp+84h] [rbp-154h]
  int v51; // [rsp+88h] [rbp-150h]
  int v52; // [rsp+8Ch] [rbp-14Ch]
  int v53; // [rsp+90h] [rbp-148h]
  _BYTE v54[16]; // [rsp+98h] [rbp-140h] BYREF
  CInternalMerger *v55; // [rsp+A8h] [rbp-130h] BYREF
  char v56; // [rsp+B0h] [rbp-128h]
  int v57; // [rsp+B4h] [rbp-124h]
  __int64 v58; // [rsp+B8h] [rbp-120h] BYREF
  __int64 v59; // [rsp+C0h] [rbp-118h]
  char v60[8]; // [rsp+C8h] [rbp-110h] BYREF
  char v61[16]; // [rsp+D0h] [rbp-108h] BYREF
  _BYTE v62[96]; // [rsp+E0h] [rbp-F8h] BYREF
  _BYTE v63[152]; // [rsp+140h] [rbp-98h] BYREF

  v7 = this;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_4bdb54f5bdc135277da4b5f2757d4675_Traceguids);
  }
  v8 = 0;
  v9 = *(_QWORD *)(*((_QWORD *)v7 + 7) + 24LL);
  TickCount = GetTickCount();
  *((_DWORD *)v7 + 38) = TickCount;
  *(_DWORD *)(v9 + 64) = TickCount;
  v55 = v7;
  v56 = 0;
  v57 = 0;
  if ( a4 )
  {
    for ( i = 0; (int)i < a2; i = (unsigned int)(i + 1) )
      v8 += ((__int64 (__fastcall *)(struct IWbemClassObject *))a3[i]->lpVtbl[3].PutMethod)(a3[i]);
    v8 = CInternalMerger::CScopedMemoryUsage::ReportMemoryUsage((CInternalMerger::CScopedMemoryUsage *)&v55, v8);
  }
  v42 = 0;
  v41 = 0;
  CFlexArray::CFlexArray((CFlexArray *)v62, 8, 100);
  v44 = 0;
  v40 = 0;
  v47 = 0;
  v12 = 0;
  CWStringArray::CWStringArray((CWStringArray *)v63, 0, 100);
  CCheckedInCritSec::CCheckedInCritSec((CCheckedInCritSec *)v54, (CInternalMerger *)((char *)v7 + 176));
  if ( v8 >= 0 )
  {
    if ( *((int *)v7 + 28) < 0 )
    {
      v8 = *((_DWORD *)v7 + 28);
    }
    else if ( *((_DWORD *)v7 + 21) )
    {
      v8 = -2147217386;
    }
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    for ( j = 0; ; ++j )
    {
      v43 = j;
      if ( v8 < 0 || j >= a2 )
        goto LABEL_103;
      if ( *((int *)v7 + 28) >= 0 )
        break;
      v8 = *((_DWORD *)v7 + 28);
LABEL_21:
      ;
    }
    v13 = a3[j];
    v45 = ((__int64 (__fastcall *)(struct IWbemClassObject *))v13->lpVtbl[3].PutMethod)(v13) + v12;
    v51 = v45;
    WString::WString((WString *)v46);
    v14 = (const wchar_t *)((__int64 (__fastcall *)(struct IWbemClassObject *, _QWORD))v13->lpVtbl[4].BeginMethodEnumeration)(
                             v13,
                             0);
    v15 = (wchar_t *)v14;
    if ( v14 )
    {
      v16 = wcschr(v14, 0x2Eu);
      if ( v16 )
      {
        WString::operator=(v46, v16 + 1);
      }
      else
      {
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, -1);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_4bdb54f5bdc135277da4b5f2757d4675_Traceguids, v15);
        }
        WString::Empty((WString *)v46);
      }
      CWin32DefaultArena::WbemMemFree(v15);
    }
    else
    {
      v35 = GetMemLogObject();
      CMemoryLog::Write(v35, -1);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_4bdb54f5bdc135277da4b5f2757d4675_Traceguids);
      }
      WString::Empty((WString *)v46);
    }
    std::_Tree<std::_Tmap_traits<WString,CInternalMergerRecord,WSiless,CKeyToInstRecordAlloc,0>>::find(
      (char *)v7 + 64,
      &v58,
      v46);
    v59 = *((_QWORD *)v7 + 8);
    v17 = v58;
    if ( v58 == v59 )
    {
      if ( *((_DWORD *)v7 + 20) )
      {
        if ( CFlexArray::Add((CFlexArray *)v62, v13)
          || (((void (__fastcall *)(struct IWbemClassObject *))v13->lpVtbl->AddRef)(v13),
              CFlexArray::Size((CFlexArray *)v62) - 1 < 0) )
        {
          v8 = -2147217402;
          v18 = GetMemLogObject();
          CMemoryLog::Write(v18, -1);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              27,
              WPP_4bdb54f5bdc135277da4b5f2757d4675_Traceguids,
              2147749894LL);
          }
          goto LABEL_20;
        }
        v49 = ++v44;
        goto LABEL_34;
      }
      v24 = std::map<WString,CInternalMergerRecord,WSiless,CKeyToInstRecordAlloc>::operator[]((char *)v7 + 64, v46);
      *(_QWORD *)v24 = v13;
      ((void (__fastcall *)(struct IWbemClassObject *))v13->lpVtbl->AddRef)(v13);
      *(_DWORD *)(v24 + 12) = 0;
      v25 = ((__int64 (__fastcall *)(struct IWbemClassObject *))v13->lpVtbl[3].PutMethod)(v13);
      *(_DWORD *)(v24 + 8) = v25;
      v26 = v42 + 1;
      v42 = v26;
      v53 = v26;
      v27 = v25 + v40;
      v40 = v27;
      v48 = v27;
      if ( !*((_DWORD *)v7 + 6) )
      {
        v28 = (const unsigned __int16 *)WString::operator unsigned short *(v46);
        if ( CWStringArray::Add((CWStringArray *)v63, v28) )
          v8 = -2147217402;
        goto LABEL_34;
      }
LABEL_57:
      v23 = v41;
LABEL_36:
      if ( v8 >= 0 )
      {
        if ( v45 >= 0 && (unsigned int)v45 >= *((_DWORD *)v7 + 42) )
        {
          v29 = a2 - 1;
          v30 = v43;
LABEL_42:
          *((_DWORD *)v7 + 54) += v27;
          CInternalMerger::AdjustThrottle(v7, v23, v26);
          CCheckedInCritSec::Leave((CCheckedInCritSec *)v54);
          v8 = CInternalMerger::IndicateArrayAndThrottle(v7, v40, v47, 1, 0, (__int64)a5);
          if ( v8 >= 0 && v30 < v29 )
          {
            v40 = 0;
            v48 = 0;
            v47 = 0;
            v50 = 0;
            v45 = 0;
            v51 = 0;
            v44 = 0;
            v49 = 0;
            v41 = 0;
            v52 = 0;
            v42 = 0;
            v53 = 0;
            CWStringArray::Empty((CWStringArray *)v63);
            CCheckedInCritSec::Enter((CCheckedInCritSec *)v54);
          }
          goto LABEL_20;
        }
        v29 = a2 - 1;
        v30 = v43;
        if ( v43 == a2 - 1 )
          goto LABEL_42;
      }
LABEL_20:
      WString::~WString((WString *)v46);
      v12 = v45;
      j = v43;
      goto LABEL_21;
    }
    if ( *(_DWORD *)(v58 + 52) )
    {
      v8 = CWbemInstance::AsymmetricMerge(*(struct CWbemInstance **)(v58 + 40), (struct CWbemInstance *)v13);
      if ( v8 < 0 )
      {
        v37 = GetMemLogObject();
        CMemoryLog::Write(v37, -1);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v38 = WString::operator unsigned short *(v46);
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_4bdb54f5bdc135277da4b5f2757d4675_Traceguids, v38);
        }
        goto LABEL_20;
      }
      if ( CFlexArray::Add((CFlexArray *)v62, v13)
        || (((void (__fastcall *)(struct IWbemClassObject *))v13->lpVtbl->AddRef)(v13),
            CFlexArray::Size((CFlexArray *)v62) - 1 < 0) )
      {
        v8 = -2147217402;
        v39 = GetMemLogObject();
        CMemoryLog::Write(v39, -1);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            30,
            WPP_4bdb54f5bdc135277da4b5f2757d4675_Traceguids,
            2147749894LL);
        }
        goto LABEL_20;
      }
      v20 = ((__int64 (__fastcall *)(struct IWbemClassObject *))v13->lpVtbl[3].PutMethod)(v13);
      v47 += v20;
      v50 = v47;
      v49 = ++v44;
      v40 -= *(_DWORD *)(v17 + 48);
      v48 = v40;
      v21 = 0;
      if ( *((_DWORD *)v7 + 20) )
        v21 = *((_QWORD *)v7 + 29) == v17;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v17 + 40) + 16LL))(*(_QWORD *)(v17 + 40));
      v22 = (char *)v7 + 64;
      if ( v21 )
        *((_QWORD *)v7 + 29) = *(_QWORD *)std::_Tree<std::_Tmap_traits<WString,CInternalMergerRecord,WSiless,CKeyToInstRecordAlloc,0>>::erase(
                                            v22,
                                            v60,
                                            v17);
      else
        std::_Tree<std::_Tmap_traits<WString,CInternalMergerRecord,WSiless,CKeyToInstRecordAlloc,0>>::erase(
          v22,
          v61,
          v17);
      v23 = v41 - 1;
      v41 = v23;
      v52 = v23;
      goto LABEL_35;
    }
    v33 = GetMemLogObject();
    CMemoryLog::Write(v33, -1);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        v27 = v40;
        v26 = v42;
        goto LABEL_57;
      }
      v34 = WString::operator unsigned short *(v46);
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_4bdb54f5bdc135277da4b5f2757d4675_Traceguids, v34);
    }
LABEL_34:
    v23 = v41;
LABEL_35:
    v27 = v40;
    v26 = v42;
    goto LABEL_36;
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &CX_MemoryException `RTTI Type Descriptor', 0) )
    {
      v8 = -2147217402;
      v7 = this;
      __eh34_try_continuation(0, &CX_MemoryException `RTTI Type Descriptor', &loc_1800340C2);
      goto LABEL_103;
    }
    if ( __eh34_catch_type(0, &CX_Exception `RTTI Type Descriptor', 0) )
    {
      _InterlockedIncrement(&ExceptionCounter::s_Count);
      v8 = -2147217398;
      v7 = this;
      __eh34_try_continuation(0, &CX_Exception `RTTI Type Descriptor', &loc_1800340C4);
    }
  }
LABEL_103:
  if ( *((int *)v7 + 28) < 0 )
    v8 = *((_DWORD *)v7 + 28);
  CCheckedInCritSec::Leave((CCheckedInCritSec *)v54);
  if ( v8 >= 0 )
  {
    if ( a4 )
    {
      if ( !*a5 )
      {
        _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(*((_QWORD *)v7 + 7) + 24LL) + 272LL));
        v8 = CWmiMerger::Throttle(*(CWmiMerger **)(*((_QWORD *)v7 + 7) + 24LL));
        _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(*((_QWORD *)v7 + 7) + 24LL) + 272LL));
        if ( v8 == -2147209215 || v8 == 266240 )
          v8 = 0;
      }
    }
  }
  if ( v8 == -2147209214 )
    v8 = -2147217358;
  if ( v8 < 0 )
  {
    CWmiMerger::Cancel(*(CWmiMerger **)(*((_QWORD *)v7 + 7) + 24LL), v8);
    v32 = GetMemLogObject();
    CMemoryLog::Write(v32, v8);
  }
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_4bdb54f5bdc135277da4b5f2757d4675_Traceguids, (unsigned int)v8);
  }
  CCheckedInCritSec::~CCheckedInCritSec((CCheckedInCritSec *)v54);
  CWStringArray::~CWStringArray((CWStringArray *)v63);
  CRefedPointerArray<IWbemClassObject>::~CRefedPointerArray<IWbemClassObject>(v62);
  CInternalMerger::CScopedMemoryUsage::Cleanup((CInternalMerger::CScopedMemoryUsage *)&v55);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180033764  mov     rax, rsp
0x180033767  mov     [rax+20h], r9b
0x18003376b  mov     [rax+18h], r8
0x18003376f  mov     [rax+10h], edx
0x180033772  mov     [rax+8], rcx
0x180033776  push    rbx
0x180033777  push    rsi
0x180033778  push    r12
0x18003377a  push    r13
0x18003377c  push    r14
0x18003377e  push    r15
0x180033780  sub     rsp, 1A8h
0x180033787  mov     r15b, r9b
0x18003378a  mov     r13d, edx
0x18003378d  mov     r14, rcx
0x180033790  lea     r12, WPP_GLOBAL_Control
0x180033797  mov     rcx, cs:WPP_GLOBAL_Control
0x18003379e  cmp     rcx, r12
0x1800337a1  jnz     loc_180033D8B
0x1800337a7  xor     esi, esi
0x1800337a9  mov     rax, [r14+38h]
0x1800337ad  mov     rbx, [rax+18h]
0x1800337b1  call    cs:__imp_GetTickCount
0x1800337b7  mov     [r14+98h], eax
0x1800337be  mov     [rbx+40h], eax
0x1800337c1  mov     [rsp+1D8h+var_130], r14
0x1800337c9  mov     [rsp+1D8h+var_128], sil
0x1800337d1  mov     [rsp+1D8h+var_124], esi
0x1800337d8  test    r15b, r15b
0x1800337db  jz      short loc_180033819
0x1800337dd  xor     ebx, ebx
0x1800337df  test    r13d, r13d
0x1800337e2  jle     short loc_180033808
0x1800337e4  mov     r15, [rsp+1D8h+arg_10]
0x1800337ec  mov     rcx, [r15+rbx*8]
0x1800337f0  mov     rax, [rcx]
0x1800337f3  mov     rax, [rax+328h]
0x1800337fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800337ff  add     esi, eax
0x180033801  inc     ebx
0x180033803  cmp     ebx, r13d
0x180033806  jl      short loc_1800337EC
0x180033808  mov     edx, esi; int
0x18003380a  lea     rcx, [rsp+1D8h+var_130]; this
0x180033812  call    ?ReportMemoryUsage@CScopedMemoryUsage@CInternalMerger@@QEAAJJ@Z; CInternalMerger::CScopedMemoryUsage::ReportMemoryUsage(long)
0x180033817  mov     esi, eax
0x180033819  xor     eax, eax
0x18003381b  mov     [rsp+1D8h+var_180], eax
0x18003381f  mov     [rsp+1D8h+var_184], eax
0x180033823  lea     r15d, [rax+64h]
0x180033827  mov     r8d, r15d
0x18003382a  lea     edx, [rax+8]
0x18003382d  lea     rcx, [rsp+1D8h+var_F8]
0x180033835  call    cs:__imp_??0CFlexArray@@QEAA@HH@Z; CFlexArray::CFlexArray(int,int)
0x18003383b  nop
0x18003383c  mov     [rsp+1D8h+var_174], 0
0x180033844  xor     eax, eax
0x180033846  mov     [rsp+1D8h+var_188], eax
0x18003384a  mov     [rsp+1D8h+var_160], eax
0x18003384e  xor     ebx, ebx
0x180033850  mov     r8d, r15d
0x180033853  xor     edx, edx
0x180033855  lea     rcx, [rsp+1D8h+var_98]
0x18003385d  call    cs:__imp_??0CWStringArray@@QEAA@HH@Z; CWStringArray::CWStringArray(int,int)
0x180033863  nop
0x180033864  lea     rdx, [r14+0B0h]
0x18003386b  lea     rcx, [rsp+1D8h+var_140]
0x180033873  call    cs:__imp_??0CCheckedInCritSec@@QEAA@PEAVCCritSec@@@Z; CCheckedInCritSec::CCheckedInCritSec(CCritSec *)
0x180033879  nop
0x18003387a  test    esi, esi
0x18003387c  jns     loc_180033DB9
0x180033882  xor     eax, eax
0x180033884  mov     r13b, 2
0x180033887  mov     [rsp+1D8h+var_178], eax
0x18003388b  test    esi, esi
0x18003388d  js      loc_180033CCB
0x180033893  cmp     eax, [rsp+1D8h+arg_8]
0x18003389a  jge     loc_180033CCB
0x1800338a0  cmp     dword ptr [r14+70h], 0
0x1800338a5  jl      loc_180033E51
0x1800338ab  cdqe
0x1800338ad  mov     rcx, [rsp+1D8h+arg_10]
0x1800338b5  mov     r15, [rcx+rax*8]
0x1800338b9  mov     rax, [r15]
0x1800338bc  mov     rcx, r15
0x1800338bf  mov     rax, [rax+328h]
0x1800338c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800338cb  add     ebx, eax
0x1800338cd  mov     [rsp+1D8h+var_170], ebx
0x1800338d1  mov     [rsp+1D8h+var_150], ebx
0x1800338d8  lea     rcx, [rsp+1D8h+var_168]
0x1800338dd  call    cs:__imp_??0WString@@QEAA@XZ; WString::WString(void)
0x1800338e3  nop
0x1800338e4  mov     rax, [r15]
0x1800338e7  xor     edx, edx
0x1800338e9  mov     rcx, r15
0x1800338ec  mov     rax, [rax+410h]
0x1800338f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800338f8  mov     rbx, rax
0x1800338fb  test    rax, rax
0x1800338fe  jz      loc_180033EEF
0x180033904  mov     edx, 2Eh ; '.'; Ch
0x180033909  mov     rcx, rax; Str
0x18003390c  call    cs:__imp_wcschr
0x180033912  test    rax, rax
0x180033915  jz      loc_180033F3E
0x18003391b  lea     rdx, [rax+2]
0x18003391f  lea     rcx, [rsp+1D8h+var_168]
0x180033924  call    cs:__imp_??4WString@@QEAAAEAV0@PEBG@Z; WString::operator=(ushort const *)
0x18003392a  mov     rcx, rbx
0x18003392d  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180033933  lea     r12, [r14+40h]
0x180033937  lea     r8, [rsp+1D8h+var_168]
0x18003393c  lea     rdx, [rsp+1D8h+var_120]
0x180033944  mov     rcx, r12
0x180033947  call    ?find@?$_Tree@V?$_Tmap_traits@VWString@@UCInternalMergerRecord@@VWSiless@@VCKeyToInstRecordAlloc@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVWString@@UCInternalMergerRecord@@@std@@@std@@@std@@@2@AEBVWString@@@Z; std::_Tree<std::_Tmap_traits<WString,CInternalMergerRecord,WSiless,CKeyToInstRecordAlloc,0>>::find(WString const &)
0x18003394c  mov     rax, [r12]
0x180033950  mov     [rsp+1D8h+var_118], rax
0x180033958  mov     rbx, [rsp+1D8h+var_120]
0x180033960  cmp     rbx, rax
0x180033963  jnz     loc_1800339FB
0x180033969  cmp     dword ptr [r14+50h], 0
0x18003396e  jz      loc_180033B03
0x180033974  mov     rdx, r15
0x180033977  lea     rcx, [rsp+1D8h+var_F8]
0x18003397f  call    cs:__imp_?Add@CFlexArray@@QEAAHPEAX@Z; CFlexArray::Add(void *)
0x180033985  test    eax, eax
0x180033987  jnz     short loc_1800339AF
0x180033989  mov     rax, [r15]
0x18003398c  mov     rcx, r15
0x18003398f  mov     rax, [rax+8]
0x180033993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033998  lea     rcx, [rsp+1D8h+var_F8]
0x1800339a0  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x1800339a6  cmp     eax, 1
0x1800339a9  jns     loc_180033DD2
0x1800339af  mov     esi, 80041006h
0x1800339b4  mov     [rsp+1D8h+var_17C], esi
0x1800339b8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800339be  or      edx, 0FFFFFFFFh
0x1800339c1  mov     rcx, rax
0x1800339c4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800339ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800339d1  lea     r12, WPP_GLOBAL_Control
0x1800339d8  cmp     rcx, r12
0x1800339db  jnz     loc_180033F90
0x1800339e1  lea     rcx, [rsp+1D8h+var_168]
0x1800339e6  call    cs:__imp_??1WString@@QEAA@XZ; WString::~WString(void)
0x1800339ec  mov     ebx, [rsp+1D8h+var_170]
0x1800339f0  mov     eax, [rsp+1D8h+var_178]
0x1800339f4  inc     eax
0x1800339f6  jmp     loc_180033887
0x1800339fb  cmp     dword ptr [rbx+34h], 0
0x1800339ff  jz      loc_180033E83
0x180033a05  mov     rdx, r15
0x180033a08  mov     rcx, [rbx+28h]
0x180033a0c  call    cs:__imp_?AsymmetricMerge@CWbemInstance@@SAJPEAV1@0@Z; CWbemInstance::AsymmetricMerge(CWbemInstance *,CWbemInstance *)
0x180033a12  mov     esi, eax
0x180033a14  mov     [rsp+1D8h+var_17C], eax
0x180033a18  test    eax, eax
0x180033a1a  js      loc_180033FD2
0x180033a20  mov     rdx, r15
0x180033a23  lea     rcx, [rsp+1D8h+var_F8]
0x180033a2b  call    cs:__imp_?Add@CFlexArray@@QEAAHPEAX@Z; CFlexArray::Add(void *)
0x180033a31  test    eax, eax
0x180033a33  jnz     loc_18003405C
0x180033a39  mov     rax, [r15]
0x180033a3c  mov     rcx, r15
0x180033a3f  mov     rax, [rax+8]
0x180033a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a48  lea     rcx, [rsp+1D8h+var_F8]
0x180033a50  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x180033a56  cmp     eax, 1
0x180033a59  js      loc_18003405C
0x180033a5f  mov     rax, [r15]
0x180033a62  mov     rcx, r15
0x180033a65  mov     rax, [rax+328h]
0x180033a6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a71  mov     ecx, [rsp+1D8h+var_160]
0x180033a75  add     ecx, eax
0x180033a77  mov     [rsp+1D8h+var_160], ecx
0x180033a7b  mov     [rsp+1D8h+var_154], ecx
0x180033a82  mov     eax, [rsp+1D8h+var_174]
0x180033a86  inc     eax
0x180033a88  mov     [rsp+1D8h+var_174], eax
0x180033a8c  mov     [rsp+1D8h+var_158], eax
0x180033a93  mov     eax, [rsp+1D8h+var_188]
0x180033a97  sub     eax, [rbx+30h]
0x180033a9a  mov     [rsp+1D8h+var_188], eax
0x180033a9e  mov     [rsp+1D8h+var_15C], eax
0x180033aa2  xor     r15b, r15b
0x180033aa5  cmp     dword ptr [r14+50h], 0
0x180033aaa  jnz     loc_18003403E
0x180033ab0  mov     rcx, [rbx+28h]
0x180033ab4  mov     rax, [rcx]
0x180033ab7  mov     rax, [rax+10h]
0x180033abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033ac0  mov     r8, rbx
0x180033ac3  mov     rcx, r12
0x180033ac6  test    r15b, r15b
0x180033ac9  jz      loc_180033E3F
0x180033acf  lea     rdx, [rsp+1D8h+var_110]
0x180033ad7  call    ?erase@?$_Tree@V?$_Tmap_traits@VWString@@UCInternalMergerRecord@@VWSiless@@VCKeyToInstRecordAlloc@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVWString@@UCInternalMergerRecord@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVWString@@UCInternalMergerRecord@@@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<WString,CInternalMergerRecord,WSiless,CKeyToInstRecordAlloc,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<WString const,CInternalMergerRecord>>>>)
0x180033adc  mov     rcx, [rax]
0x180033adf  mov     [r14+0E8h], rcx
0x180033ae6  mov     ecx, [rsp+1D8h+var_184]
0x180033aea  dec     ecx
0x180033aec  mov     [rsp+1D8h+var_184], ecx
0x180033af0  mov     [rsp+1D8h+var_14C], ecx
0x180033af7  lea     r12, WPP_GLOBAL_Control
0x180033afe  jmp     loc_180033B9E
0x180033b03  lea     rdx, [rsp+1D8h+var_168]
0x180033b08  mov     rcx, r12
0x180033b0b  call    ??A?$map@VWString@@UCInternalMergerRecord@@VWSiless@@VCKeyToInstRecordAlloc@@@std@@QEAAAEAUCInternalMergerRecord@@AEBVWString@@@Z; std::map<WString,CInternalMergerRecord,WSiless,CKeyToInstRecordAlloc>::operator[](WString const &)
0x180033b10  mov     rbx, rax
0x180033b13  mov     [rax], r15
0x180033b16  mov     rcx, [r15]
0x180033b19  mov     rax, [rcx+8]
0x180033b1d  mov     rcx, r15
0x180033b20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b25  mov     dword ptr [rbx+0Ch], 0
0x180033b2c  mov     rcx, [r15]
0x180033b2f  mov     rax, [rcx+328h]
0x180033b36  mov     rcx, r15
0x180033b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b3e  mov     [rbx+8], eax
0x180033b41  mov     r8d, [rsp+1D8h+var_180]
0x180033b46  inc     r8d
0x180033b49  mov     [rsp+1D8h+var_180], r8d
0x180033b4e  mov     [rsp+1D8h+var_148], r8d
0x180033b56  mov     edx, [rsp+1D8h+var_188]
0x180033b5a  add     edx, eax
0x180033b5c  mov     [rsp+1D8h+var_188], edx
0x180033b60  mov     [rsp+1D8h+var_15C], edx
0x180033b64  cmp     dword ptr [r14+18h], 0
0x180033b69  jnz     loc_180033D7B
0x180033b6f  lea     rcx, [rsp+1D8h+var_168]
0x180033b74  call    cs:__imp_??BWString@@QEAAPEAGXZ; WString::operator ushort *(void)
0x180033b7a  mov     rdx, rax
0x180033b7d  lea     rcx, [rsp+1D8h+var_98]
0x180033b85  call    cs:__imp_?Add@CWStringArray@@QEAAHPEBG@Z; CWStringArray::Add(ushort const *)
0x180033b8b  lea     r12, WPP_GLOBAL_Control
0x180033b92  test    eax, eax
0x180033b94  jnz     loc_180033FC4
0x180033b9a  mov     ecx, [rsp+1D8h+var_184]
0x180033b9e  mov     edx, [rsp+1D8h+var_188]
0x180033ba2  mov     r8d, [rsp+1D8h+var_180]; int
0x180033ba7  test    esi, esi
0x180033ba9  js      loc_1800339E1
0x180033baf  mov     eax, [rsp+1D8h+var_170]
0x180033bb3  test    eax, eax
0x180033bb5  js      short loc_180033BC0
0x180033bb7  cmp     eax, [r14+0A8h]
0x180033bbe  jnb     short loc_180033BD9
0x180033bc0  mov     ebx, [rsp+1D8h+arg_8]
0x180033bc7  dec     ebx
0x180033bc9  mov     r15d, [rsp+1D8h+var_178]
0x180033bce  cmp     r15d, ebx
0x180033bd1  jnz     loc_1800339E1
0x180033bd7  jmp     short loc_180033BE7
0x180033bd9  mov     ebx, [rsp+1D8h+arg_8]
0x180033be0  dec     ebx
0x180033be2  mov     r15d, [rsp+1D8h+var_178]
0x180033be7  add     [r14+0D8h], edx
0x180033bee  mov     edx, ecx; int
0x180033bf0  mov     rcx, r14; this
0x180033bf3  call    ?AdjustThrottle@CInternalMerger@@IEAAXJJ@Z; CInternalMerger::AdjustThrottle(long,long)
0x180033bf8  lea     rcx, [rsp+1D8h+var_140]
0x180033c00  call    cs:__imp_?Leave@CCheckedInCritSec@@QEAAXXZ; CCheckedInCritSec::Leave(void)
0x180033c06  mov     rax, [rsp+1D8h+arg_20]
0x180033c0e  mov     [rsp+1D8h+var_198], rax; __int64
0x180033c13  mov     [rsp+1D8h+var_1A0], 0; bool
0x180033c18  mov     [rsp+1D8h+var_1A8], 1; char
0x180033c1d  mov     eax, [rsp+1D8h+var_160]
0x180033c21  mov     [rsp+1D8h+var_1B0], eax; int
0x180033c25  mov     eax, [rsp+1D8h+var_188]
0x180033c29  mov     [rsp+1D8h+var_1B8], eax; int
0x180033c2d  lea     r9, [rsp+1D8h+var_98]
0x180033c35  lea     r8, [rsp+1D8h+var_F8]
0x180033c3d  mov     edx, [rsp+1D8h+var_174]
0x180033c41  mov     rcx, r14; this
0x180033c44  call    ?IndicateArrayAndThrottle@CInternalMerger@@IEAAJJPEAV?$CRefedPointerArray@UIWbemClassObject@@@@PEAVCWStringArray@@JJ_N2PEAJ@Z; CInternalMerger::IndicateArrayAndThrottle(long,CRefedPointerArray<IWbemClassObject> *,CWStringArray *,long,long,bool,bool,long *)
0x180033c49  mov     esi, eax
0x180033c4b  mov     [rsp+1D8h+var_17C], eax
0x180033c4f  test    eax, eax
0x180033c51  js      loc_1800339E1
0x180033c57  cmp     r15d, ebx
0x180033c5a  jge     loc_1800339E1
0x180033c60  xor     r15d, r15d
0x180033c63  mov     [rsp+1D8h+var_188], r15d
0x180033c68  mov     [rsp+1D8h+var_15C], r15d
0x180033c6d  mov     [rsp+1D8h+var_160], r15d
0x180033c72  mov     [rsp+1D8h+var_154], r15d
0x180033c7a  xor     eax, eax
0x180033c7c  mov     [rsp+1D8h+var_170], eax
0x180033c80  mov     [rsp+1D8h+var_150], eax
0x180033c87  xor     ebx, ebx
0x180033c89  mov     [rsp+1D8h+var_174], ebx
0x180033c8d  mov     [rsp+1D8h+var_158], ebx
0x180033c94  mov     [rsp+1D8h+var_184], eax
  ... truncated ...
```
