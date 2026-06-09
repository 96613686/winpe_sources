# CWbemNamespace::GetObjectByFullPath(ushort const *,IWbemPath *,long,IWbemContext *,CBasicObjectSink *)

- ea: `0x18009ddcc`
- end: `0x18009e7ab`
- name: `?GetObjectByFullPath@CWbemNamespace@@QEAAJPEBGPEAUIWbemPath@@JPEAUIWbemContext@@PEAVCBasicObjectSink@@@Z`
- size: `2527`
- prototype: `__int64 __fastcall(CWbemNamespace *__hidden this, const unsigned __int16 *, struct IWbemPath *, int, struct IWbemContext *, struct CBasicObjectSink *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003ad40`

## callees

- `0x18000b140`
- `0x18000b17c`
- `0x18001307c`
- `0x18001f6d0`
- `0x180023250`
- `0x180027920`
- `0x18002a998`
- `0x18002dd24`
- `0x18002fe54`
- `0x180036db0`
- `0x180036df4`
- `0x18003ad40`
- `0x18005fc7c`
- `0x180065cd0`
- `0x18008a658`
- `0x18009ddcc`
- `0x1800da010`

## import_xrefs

- `msvcrt!malloc` at `0x18009e43d`
- `msvcrt!malloc` at `0x18009e43d`
- `msvcrt!free` at `0x18009e4d1`
- `msvcrt!free` at `0x18009e4d1`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18009e47b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18009e47b`
- `wbemcomn!?GetLocales@CMUILocaleList@@QEAAPEBGXZ` at `0x18009e692`
- `wbemcomn!?GetLocales@CMUILocaleList@@QEAAPEBGXZ` at `0x18009e692`
- `wbemcomn!??0CInsertionString@@QEAA@PEBG@Z` at `0x18009e5cb`
- `wbemcomn!??0CInsertionString@@QEAA@PEBG@Z` at `0x18009e5cb`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18009dece`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18009e021`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18009dece`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18009e021`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18009e2e5`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18009e785`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18009e78f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18009e2e5`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18009e785`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18009e78f`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18009e4ee`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18009e505`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18009e51b`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18009e530`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18009e545`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18009e55a`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18009e56f`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18009e58a`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18009e5a5`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18009e4ee`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18009e505`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18009e51b`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18009e530`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18009e545`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18009e55a`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18009e56f`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18009e58a`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18009e5a5`
- `wbemcomn!?Report@CEventLog@@QEAAHGAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z` at `0x18009e61b`
- `wbemcomn!?Report@CEventLog@@QEAAHGAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z` at `0x18009e61b`
- `wbemcomn!GetMemLogObject` at `0x18009de65`
- `wbemcomn!GetMemLogObject` at `0x18009dee0`
- `wbemcomn!GetMemLogObject` at `0x18009df59`
- `wbemcomn!GetMemLogObject` at `0x18009dfc0`
- `wbemcomn!GetMemLogObject` at `0x18009e033`
- `wbemcomn!GetMemLogObject` at `0x18009e0b7`
- `wbemcomn!GetMemLogObject` at `0x18009e15c`
- `wbemcomn!GetMemLogObject` at `0x18009e1c5`
- `wbemcomn!GetMemLogObject` at `0x18009e298`
- `wbemcomn!GetMemLogObject` at `0x18009e309`
- `wbemcomn!GetMemLogObject` at `0x18009e3b6`
- `wbemcomn!GetMemLogObject` at `0x18009e485`
- `wbemcomn!GetMemLogObject` at `0x18009e63a`
- `wbemcomn!GetMemLogObject` at `0x18009e6d8`
- `wbemcomn!GetMemLogObject` at `0x18009e71f`
- `wbemcomn!GetMemLogObject` at `0x18009de65`
- `wbemcomn!GetMemLogObject` at `0x18009dee0`
- `wbemcomn!GetMemLogObject` at `0x18009df59`
- `wbemcomn!GetMemLogObject` at `0x18009dfc0`
- `wbemcomn!GetMemLogObject` at `0x18009e033`
- `wbemcomn!GetMemLogObject` at `0x18009e0b7`
- `wbemcomn!GetMemLogObject` at `0x18009e15c`
- `wbemcomn!GetMemLogObject` at `0x18009e1c5`
- `wbemcomn!GetMemLogObject` at `0x18009e298`
- `wbemcomn!GetMemLogObject` at `0x18009e309`
- `wbemcomn!GetMemLogObject` at `0x18009e3b6`
- `wbemcomn!GetMemLogObject` at `0x18009e485`
- `wbemcomn!GetMemLogObject` at `0x18009e63a`
- `wbemcomn!GetMemLogObject` at `0x18009e6d8`
- `wbemcomn!GetMemLogObject` at `0x18009e71f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009de70`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009def0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009df64`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009dfcb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009e043`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009e0c2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009e16c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009e1d5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009e2a4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009e315`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009e3c2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009e491`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009e64a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009e6e4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009e72f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009de70`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009def0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009df64`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009dfcb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009e043`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009e0c2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009e16c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009e1d5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009e2a4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009e315`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009e3c2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009e491`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009e64a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009e6e4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009e72f`

## string_xrefs

- `0x18009e369`: `Read (GetObject)`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CWbemNamespace::GetObjectByFullPath(
        CWbemNamespace *this,
        const unsigned __int16 *a2,
        struct IWbemPath *a3,
        int a4,
        struct IWbemContext *a5,
        struct CBasicObjectSink *a6)
{
  int v8; // ebx
  CMemoryLog *MemLogObject; // rax
  CClientCnt *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  void *v13; // rax
  void *v14; // r12
  CMemoryLog *v15; // rax
  CMemoryLog *v16; // rax
  CClientCnt *v17; // rcx
  __int64 v18; // rdx
  CMemoryLog *v19; // rax
  __int64 v20; // r9
  void *v21; // rax
  void *v22; // rsi
  CMemoryLog *v23; // rax
  CMemoryLog *v24; // rax
  CClientCnt *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // r9
  BOOL (__stdcall *IsLocal)(IWbemPath *, LPCWSTR); // rbx
  unsigned __int16 *MachineName; // rax
  CMemoryLog *v30; // rax
  int v31; // ebx
  CClientCnt *v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // r9
  int v35; // r13d
  struct CWbemNamespace *Instance; // rbx
  CMemoryLog *v37; // rax
  int v38; // r13d
  unsigned int v39; // r9d
  unsigned int v40; // eax
  unsigned int v41; // edx
  int Object; // r14d
  CMemoryLog *v43; // rax
  CClientCnt *v44; // rcx
  __int64 v45; // rdx
  CMemoryLog *v46; // rax
  unsigned int UserAccess; // r14d
  int v48; // r14d
  CMemoryLog *v49; // rax
  int v50; // edx
  const unsigned __int16 *v51; // rcx
  int v52; // esi
  CHAR *lpMultiByteStr; // rax
  CHAR *v54; // rbx
  CMemoryLog *v55; // rax
  CInsertionString *v56; // r13
  CInsertionString *v57; // r12
  CInsertionString *v58; // r15
  CInsertionString *v59; // r14
  CInsertionString *v60; // rsi
  CInsertionString *v61; // rdi
  CInsertionString *v62; // rbx
  CInsertionString *v63; // rax
  CMemoryLog *v64; // rax
  unsigned __int16 *Locales; // rax
  CMemoryLog *v66; // rax
  CMemoryLog *v67; // rax
  bool cbMultiByte; // [rsp+30h] [rbp-D8h]
  int v70; // [rsp+60h] [rbp-A8h]
  __int64 v71; // [rsp+78h] [rbp-90h] BYREF
  unsigned __int64 v72; // [rsp+80h] [rbp-88h] BYREF
  __int64 v73; // [rsp+88h] [rbp-80h] BYREF
  CInsertionString *v74; // [rsp+90h] [rbp-78h]
  struct CEventLog *v75; // [rsp+98h] [rbp-70h]
  struct CWbemNamespace *v76; // [rsp+A0h] [rbp-68h]
  void *v77; // [rsp+A8h] [rbp-60h]
  void *v78; // [rsp+B0h] [rbp-58h]
  void *v79; // [rsp+B8h] [rbp-50h]
  void *v80; // [rsp+C0h] [rbp-48h]
  _BYTE *v81; // [rsp+C8h] [rbp-40h]
  _BYTE *v82; // [rsp+D0h] [rbp-38h]
  _BYTE *v83; // [rsp+D8h] [rbp-30h]
  _BYTE *v84; // [rsp+E0h] [rbp-28h]
  _BYTE *v85; // [rsp+E8h] [rbp-20h]
  _BYTE *v86; // [rsp+F0h] [rbp-18h]
  _BYTE *v87; // [rsp+F8h] [rbp-10h]
  _BYTE *v88; // [rsp+100h] [rbp-8h]
  _BYTE *v89; // [rsp+108h] [rbp+0h]
  _BYTE *v90; // [rsp+110h] [rbp+8h]
  _BYTE v91[16]; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v92[16]; // [rsp+128h] [rbp+20h] BYREF
  _BYTE v93[16]; // [rsp+138h] [rbp+30h] BYREF
  _BYTE v94[16]; // [rsp+148h] [rbp+40h] BYREF
  _BYTE v95[16]; // [rsp+158h] [rbp+50h] BYREF
  _BYTE v96[16]; // [rsp+168h] [rbp+60h] BYREF
  _BYTE v97[16]; // [rsp+178h] [rbp+70h] BYREF
  _BYTE v98[16]; // [rsp+188h] [rbp+80h] BYREF
  _BYTE v99[16]; // [rsp+198h] [rbp+90h] BYREF
  _BYTE v100[80]; // [rsp+1A8h] [rbp+A0h] BYREF
  unsigned int v103; // [rsp+218h] [rbp+110h] BYREF
  int v104; // [rsp+220h] [rbp+118h]

  v104 = a4;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 227, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, a2);
  }
  v103 = 0;
  v8 = ((__int64 (__fastcall *)(struct IWbemPath *, __int64, unsigned int *, _QWORD))a3->lpVtbl->GetText)(
         a3,
         16,
         &v103,
         0);
  if ( v8 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v8);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = 228;
      v12 = (unsigned int)v8;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v12);
      return (unsigned int)v8;
    }
    return (unsigned int)v8;
  }
  v13 = CWin32DefaultArena::WbemMemAlloc(saturated_mul(v103, 2u));
  v14 = v13;
  v78 = v13;
  if ( v13 )
  {
    v79 = v13;
    v8 = ((__int64 (__fastcall *)(struct IWbemPath *, __int64, unsigned int *, void *))a3->lpVtbl->GetText)(
           a3,
           16,
           &v103,
           v13);
    if ( v8 < 0 )
    {
      v16 = GetMemLogObject();
      CMemoryLog::Write(v16, v8);
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_108;
      }
      v18 = 230;
      goto LABEL_26;
    }
    LODWORD(v71) = 0;
    v8 = ((__int64 (__fastcall *)(struct IWbemPath *, __int64, __int64 *, _QWORD))a3->lpVtbl->GetText)(a3, 2, &v71, 0);
    if ( v8 < 0 )
    {
      v19 = GetMemLogObject();
      CMemoryLog::Write(v19, v8);
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_108;
      }
      v18 = 231;
LABEL_26:
      v20 = (unsigned int)v8;
LABEL_32:
      WPP_SF_d(*((_QWORD *)v17 + 2), v18, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v20);
LABEL_108:
      CWin32DefaultArena::WbemMemFree(v14);
      return (unsigned int)v8;
    }
    v21 = CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)v71, 2u));
    v22 = v21;
    v77 = v21;
    if ( !v21 )
    {
      v23 = GetMemLogObject();
      v8 = -2147217402;
      CMemoryLog::Write(v23, -2147217402);
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_108;
      }
      v18 = 232;
      v20 = 2147749894LL;
      goto LABEL_32;
    }
    v80 = v21;
    v8 = ((__int64 (__fastcall *)(struct IWbemPath *, __int64, __int64 *, void *))a3->lpVtbl->GetText)(a3, 2, &v71, v21);
    if ( v8 < 0 )
    {
      v24 = GetMemLogObject();
      CMemoryLog::Write(v24, v8);
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_107;
      }
      v26 = 233;
      v27 = (unsigned int)v8;
      goto LABEL_38;
    }
    IsLocal = a3->lpVtbl->IsLocal;
    MachineName = ConfigMgr::GetMachineName();
    if ( !((unsigned int (__fastcall *)(struct IWbemPath *, unsigned __int16 *))IsLocal)(a3, MachineName) )
    {
      v67 = GetMemLogObject();
      v31 = -2147217396;
      CMemoryLog::Write(v67, -2147217396);
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_105;
      }
      v33 = 242;
      v34 = 2147749900LL;
      goto LABEL_104;
    }
    v73 = 0;
    if ( ((int (__fastcall *)(struct IWbemPath *, _QWORD, __int64 *))a3->lpVtbl->GetInfo)(a3, 0, &v73) >= 0
      && (v73 & 0x20000) == 0 )
    {
      v30 = GetMemLogObject();
      v31 = -2147217350;
      CMemoryLog::Write(v30, -2147217350);
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_105;
      }
      v33 = 234;
      v34 = 2147749946LL;
LABEL_104:
      WPP_SF_d(*((_QWORD *)v32 + 2), v33, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v34);
LABEL_105:
      v50 = v31;
LABEL_106:
      v8 = CBasicObjectSink::Return(a6, v50, 0);
      goto LABEL_107;
    }
    v35 = *((_DWORD *)this + 27);
    Instance = CWbemNamespace::CreateInstance();
    v76 = Instance;
    if ( !Instance )
    {
      v37 = GetMemLogObject();
      v8 = -2147217402;
      CMemoryLog::Write(v37, -2147217402);
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_107;
      }
      v26 = 235;
      v27 = 2147749894LL;
      goto LABEL_38;
    }
    v38 = v35 & 4;
    if ( v38 )
    {
      v39 = *((_DWORD *)this + 27);
      v40 = *((_DWORD *)this + 26);
    }
    else
    {
      v39 = 0;
      v40 = 0;
    }
    Object = CWbemNamespace::Initialize(
               Instance,
               (unsigned __int16 *)v14,
               *((unsigned __int16 **)this + 14),
               v39,
               v40,
               *((_DWORD *)this + 32),
               0,
               *((const unsigned __int16 **)this + 35),
               *((const unsigned __int16 **)this + 36),
               *((_DWORD *)this + 76),
               *((_QWORD *)this + 37),
               v70,
               0,
               0);
    if ( Object >= 0 )
    {
      Object = *((_DWORD *)Instance + 8);
      if ( Object )
      {
        CWbemNamespace::Release(Instance);
        if ( Object < 0 )
        {
          v46 = GetMemLogObject();
          CMemoryLog::Write(v46, Object);
        }
        v44 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_60;
        }
        v45 = 237;
      }
      else
      {
        if ( !v38 )
        {
          UserAccess = CWbemNamespace::GetUserAccess(Instance);
          CWbemNamespace::InnerAllowedWithSD(
            Instance,
            (struct CWbemNamespace *)((char *)Instance + 216),
            1u,
            L"Read (GetObject)",
            a2,
            cbMultiByte,
            1);
          if ( (UserAccess & 1) == 0 || *((_BYTE *)Instance + 328) && !EncryptedCaller() )
          {
            v51 = (const unsigned __int16 *)*((_QWORD *)this + 12);
            if ( v51 )
            {
              v72 = 0;
              if ( (int)StringCchLengthW(v51, 0x10000u, &v72) >= 0 )
              {
                v52 = v72;
                lpMultiByteStr = (CHAR *)malloc(v72 + 1);
                v54 = lpMultiByteStr;
                if ( lpMultiByteStr )
                {
                  if ( WideCharToMultiByte(0, 0x400u, *((LPCWCH *)this + 12), v52, lpMultiByteStr, v52 + 1, 0, 0) )
                  {
                    v55 = GetMemLogObject();
                    CMemoryLog::Write(v55, -1);
                    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      WPP_SF_s(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        238,
                        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                        v54);
                    }
                  }
                  free(v54);
                }
              }
              v75 = g_pEventLog;
              v81 = v91;
              v72 = (unsigned __int64)CInsertionString::CInsertionString((CInsertionString *)v91);
              v82 = v92;
              v74 = CInsertionString::CInsertionString((CInsertionString *)v92);
              v83 = v93;
              v56 = CInsertionString::CInsertionString((CInsertionString *)v93);
              v84 = v94;
              v57 = CInsertionString::CInsertionString((CInsertionString *)v94);
              v85 = v95;
              v58 = CInsertionString::CInsertionString((CInsertionString *)v95);
              v86 = v96;
              v59 = CInsertionString::CInsertionString((CInsertionString *)v96);
              v87 = v97;
              v60 = CInsertionString::CInsertionString((CInsertionString *)v97);
              v88 = v98;
              v61 = CInsertionString::CInsertionString((CInsertionString *)v98);
              v89 = v99;
              v62 = CInsertionString::CInsertionString((CInsertionString *)v99);
              v90 = v100;
              v63 = CInsertionString::CInsertionString(
                      (CInsertionString *)v100,
                      *((const unsigned __int16 **)this + 12));
              CEventLog::Report(
                v75,
                4,
                WBEM_MC_WBEM_REQUIRES_ENCRYPTION_DENIED,
                v63,
                v62,
                v61,
                v60,
                v59,
                v58,
                v57,
                v56,
                v74,
                v72);
              Instance = v76;
              v22 = v77;
              v14 = v78;
            }
            CWbemNamespace::`scalar deleting destructor'(Instance, v41);
            v64 = GetMemLogObject();
            v8 = -2147217405;
            CMemoryLog::Write(v64, -2147217405);
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_107;
            }
            v26 = 239;
            v27 = 2147749891LL;
LABEL_38:
            WPP_SF_d(*((_QWORD *)v25 + 2), v26, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v27);
LABEL_107:
            CWin32DefaultArena::WbemMemFree(v22);
            goto LABEL_108;
          }
          *((_DWORD *)Instance + 26) = UserAccess;
        }
        v48 = *((_DWORD *)Instance + 8);
        if ( v48 )
        {
          CWbemNamespace::`scalar deleting destructor'(Instance, v41);
          if ( v48 < 0 )
          {
            v49 = GetMemLogObject();
            CMemoryLog::Write(v49, v48);
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                240,
                WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                (unsigned int)v48);
            }
          }
          v50 = v48;
          goto LABEL_106;
        }
        Locales = (unsigned __int16 *)CMUILocaleList::GetLocales((CWbemNamespace *)((char *)this + 176));
        CWbemNamespace::_SetLocale(Instance, Locales);
        Object = CWbemNamespace::Exec_GetObject(Instance, (const unsigned __int16 *)v22, v104, a5, a6);
        CWbemNamespace::Release(Instance);
        if ( Object < 0 )
        {
          v66 = GetMemLogObject();
          CMemoryLog::Write(v66, Object);
        }
        v44 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_60:
          CWin32DefaultArena::WbemMemFree(v22);
          v8 = Object;
          goto LABEL_108;
        }
        v45 = 241;
      }
    }
    else
    {
      CWbemNamespace::Release(Instance);
      v43 = GetMemLogObject();
      CMemoryLog::Write(v43, Object);
      v44 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_60;
      }
      v45 = 236;
    }
    WPP_SF_d(*((_QWORD *)v44 + 2), v45, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, (unsigned int)Object);
    goto LABEL_60;
  }
  v15 = GetMemLogObject();
  v8 = -2147217402;
  CMemoryLog::Write(v15, -2147217402);
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v11 = 229;
    v12 = 2147749894LL;
    goto LABEL_10;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18009ddcc  mov     rax, rsp
0x18009ddcf  mov     [rax+20h], r9d
0x18009ddd3  mov     [rax+10h], rdx
0x18009ddd7  mov     [rax+8], rcx
0x18009dddb  push    rbp
0x18009dddc  push    rbx
0x18009dddd  push    rsi
0x18009ddde  push    rdi
0x18009dddf  push    r12
0x18009dde1  push    r13
0x18009dde3  push    r14
0x18009dde5  push    r15
0x18009dde7  lea     rbp, [rax-0F8h]
0x18009ddee  sub     rsp, 1B8h
0x18009ddf5  mov     r14, r8
0x18009ddf8  mov     rax, rdx
0x18009ddfb  mov     r15, rcx
0x18009ddfe  lea     rdi, WPP_GLOBAL_Control
0x18009de05  lea     rsi, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18009de0c  mov     rcx, cs:WPP_GLOBAL_Control
0x18009de13  cmp     rcx, rdi
0x18009de16  jz      short loc_18009DE38
0x18009de18  test    byte ptr [rcx+1Ch], 1
0x18009de1c  jz      short loc_18009DE38
0x18009de1e  cmp     byte ptr [rcx+19h], 5
0x18009de22  jb      short loc_18009DE38
0x18009de24  mov     edx, 0E3h
0x18009de29  mov     r9, rax
0x18009de2c  mov     r8, rsi
0x18009de2f  mov     rcx, [rcx+10h]
0x18009de33  call    WPP_SF_S
0x18009de38  xor     r13d, r13d
0x18009de3b  mov     [rbp+0F0h+arg_10], r13d
0x18009de42  mov     rax, [r14]
0x18009de45  xor     r9d, r9d
0x18009de48  lea     r8, [rbp+0F0h+arg_10]
0x18009de4f  lea     edx, [r13+10h]
0x18009de53  mov     rcx, r14
0x18009de56  mov     rax, [rax+20h]
0x18009de5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009de5f  mov     ebx, eax
0x18009de61  test    eax, eax
0x18009de63  jns     short loc_18009DEB3
0x18009de65  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009de6b  mov     edx, ebx
0x18009de6d  mov     rcx, rax
0x18009de70  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009de76  mov     rcx, cs:WPP_GLOBAL_Control
0x18009de7d  cmp     rcx, rdi
0x18009de80  jz      loc_18009E795
0x18009de86  test    byte ptr [rcx+1Ch], 1
0x18009de8a  jz      loc_18009E795
0x18009de90  cmp     byte ptr [rcx+19h], 2
0x18009de94  jb      loc_18009E795
0x18009de9a  mov     edx, 0E4h
0x18009de9f  mov     r9d, ebx
0x18009dea2  mov     r8, rsi
0x18009dea5  mov     rcx, [rcx+10h]
0x18009dea9  call    WPP_SF_d
0x18009deae  jmp     loc_18009E795
0x18009deb3  mov     ecx, [rbp+0F0h+arg_10]
0x18009deb9  mov     edi, 2
0x18009debe  mov     eax, edi
0x18009dec0  mul     rcx
0x18009dec3  lea     rcx, [rdi-3]
0x18009dec7  cmovb   rax, rcx
0x18009decb  mov     rcx, rax
0x18009dece  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18009ded4  mov     r12, rax
0x18009ded7  mov     [rbp+0F0h+var_148], rax
0x18009dedb  test    rax, rax
0x18009dede  jnz     short loc_18009DF31
0x18009dee0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009dee6  mov     ebx, 80041006h
0x18009deeb  mov     edx, ebx
0x18009deed  mov     rcx, rax
0x18009def0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009def6  mov     rcx, cs:WPP_GLOBAL_Control
0x18009defd  lea     rax, WPP_GLOBAL_Control
0x18009df04  cmp     rcx, rax
0x18009df07  jz      loc_18009E795
0x18009df0d  test    byte ptr [rcx+1Ch], 1
0x18009df11  jz      loc_18009E795
0x18009df17  cmp     [rcx+19h], dil
0x18009df1b  jb      loc_18009E795
0x18009df21  mov     edx, 0E5h
0x18009df26  mov     r9d, 80041006h
0x18009df2c  jmp     loc_18009DEA2
0x18009df31  mov     [rbp+0F0h+var_140], r12
0x18009df35  mov     rax, [r14]
0x18009df38  mov     r9, r12
0x18009df3b  lea     r8, [rbp+0F0h+arg_10]
0x18009df42  mov     edx, 10h
0x18009df47  mov     rcx, r14
0x18009df4a  mov     rax, [rax+20h]
0x18009df4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009df53  mov     ebx, eax
0x18009df55  test    eax, eax
0x18009df57  jns     short loc_18009DF9C
0x18009df59  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009df5f  mov     edx, ebx
0x18009df61  mov     rcx, rax
0x18009df64  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009df6a  mov     rcx, cs:WPP_GLOBAL_Control
0x18009df71  lea     rax, WPP_GLOBAL_Control
0x18009df78  cmp     rcx, rax
0x18009df7b  jz      loc_18009E78C
0x18009df81  test    byte ptr [rcx+1Ch], 1
0x18009df85  jz      loc_18009E78C
0x18009df8b  cmp     [rcx+19h], dil
0x18009df8f  jb      loc_18009E78C
0x18009df95  mov     edx, 0E6h
0x18009df9a  jmp     short loc_18009E001
0x18009df9c  mov     dword ptr [rsp+1F0h+var_180], r13d
0x18009dfa1  mov     rax, [r14]
0x18009dfa4  xor     r9d, r9d
0x18009dfa7  lea     r8, [rsp+1F0h+var_180]
0x18009dfac  mov     edx, edi
0x18009dfae  mov     rcx, r14
0x18009dfb1  mov     rax, [rax+20h]
0x18009dfb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009dfba  mov     ebx, eax
0x18009dfbc  test    eax, eax
0x18009dfbe  jns     short loc_18009E009
0x18009dfc0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009dfc6  mov     edx, ebx
0x18009dfc8  mov     rcx, rax
0x18009dfcb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009dfd1  mov     rcx, cs:WPP_GLOBAL_Control
0x18009dfd8  lea     rax, WPP_GLOBAL_Control
0x18009dfdf  cmp     rcx, rax
0x18009dfe2  jz      loc_18009E78C
0x18009dfe8  test    byte ptr [rcx+1Ch], 1
0x18009dfec  jz      loc_18009E78C
0x18009dff2  cmp     [rcx+19h], dil
0x18009dff6  jb      loc_18009E78C
0x18009dffc  mov     edx, 0E7h
0x18009e001  mov     r9d, ebx
0x18009e004  mov     r8, rsi
0x18009e007  jmp     short loc_18009E086
0x18009e009  mov     ecx, dword ptr [rsp+1F0h+var_180]
0x18009e00d  mov     rax, rdi
0x18009e010  mul     rcx
0x18009e013  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18009e01a  cmovb   rax, rcx
0x18009e01e  mov     rcx, rax
0x18009e021  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18009e027  mov     rsi, rax
0x18009e02a  mov     [rbp+0F0h+var_150], rax
0x18009e02e  test    rax, rax
0x18009e031  jnz     short loc_18009E094
0x18009e033  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009e039  mov     ebx, 80041006h
0x18009e03e  mov     edx, ebx
0x18009e040  mov     rcx, rax
0x18009e043  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009e049  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e050  lea     rax, WPP_GLOBAL_Control
0x18009e057  cmp     rcx, rax
0x18009e05a  jz      loc_18009E78C
0x18009e060  test    byte ptr [rcx+1Ch], 1
0x18009e064  jz      loc_18009E78C
0x18009e06a  cmp     [rcx+19h], dil
0x18009e06e  jb      loc_18009E78C
0x18009e074  mov     edx, 0E8h
0x18009e079  mov     r9d, 80041006h
0x18009e07f  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18009e086  mov     rcx, [rcx+10h]
0x18009e08a  call    WPP_SF_d
0x18009e08f  jmp     loc_18009E78C
0x18009e094  mov     [rbp+0F0h+var_138], rsi
0x18009e098  mov     rax, [r14]
0x18009e09b  mov     r9, rsi
0x18009e09e  lea     r8, [rsp+1F0h+var_180]
0x18009e0a3  mov     edx, edi
0x18009e0a5  mov     rcx, r14
0x18009e0a8  mov     rax, [rax+20h]
0x18009e0ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e0b1  mov     ebx, eax
0x18009e0b3  test    eax, eax
0x18009e0b5  jns     short loc_18009E110
0x18009e0b7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009e0bd  mov     edx, ebx
0x18009e0bf  mov     rcx, rax
0x18009e0c2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009e0c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e0cf  lea     rax, WPP_GLOBAL_Control
0x18009e0d6  cmp     rcx, rax
0x18009e0d9  jz      loc_18009E782
0x18009e0df  test    byte ptr [rcx+1Ch], 1
0x18009e0e3  jz      loc_18009E782
0x18009e0e9  cmp     [rcx+19h], dil
0x18009e0ed  jb      loc_18009E782
0x18009e0f3  mov     edx, 0E9h
0x18009e0f8  mov     r9d, ebx
0x18009e0fb  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18009e102  mov     rcx, [rcx+10h]
0x18009e106  call    WPP_SF_d
0x18009e10b  jmp     loc_18009E782
0x18009e110  mov     rax, [r14]
0x18009e113  mov     rbx, [rax+0D8h]
0x18009e11a  call    ?GetMachineName@ConfigMgr@@SAPEAGXZ; ConfigMgr::GetMachineName(void)
0x18009e11f  mov     rdx, rax
0x18009e122  mov     rcx, r14
0x18009e125  mov     rax, rbx
0x18009e128  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e12d  test    eax, eax
0x18009e12f  jz      loc_18009E71F
0x18009e135  mov     [rbp+0F0h+var_170], r13
0x18009e139  mov     rax, [r14]
0x18009e13c  lea     r8, [rbp+0F0h+var_170]
0x18009e140  xor     edx, edx
0x18009e142  mov     rcx, r14
0x18009e145  mov     rax, [rax+28h]
0x18009e149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e14e  test    eax, eax
0x18009e150  js      short loc_18009E1AD
0x18009e152  test    [rbp+0F0h+var_170], 20000h
0x18009e15a  jnz     short loc_18009E1AD
0x18009e15c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009e162  mov     ebx, 8004103Ah
0x18009e167  mov     edx, ebx
0x18009e169  mov     rcx, rax
0x18009e16c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009e172  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e179  lea     rax, WPP_GLOBAL_Control
0x18009e180  cmp     rcx, rax
0x18009e183  jz      loc_18009E76F
0x18009e189  test    byte ptr [rcx+1Ch], 1
0x18009e18d  jz      loc_18009E76F
0x18009e193  cmp     [rcx+19h], dil
0x18009e197  jb      loc_18009E76F
0x18009e19d  mov     edx, 0EAh
0x18009e1a2  mov     r9d, 8004103Ah
0x18009e1a8  jmp     loc_18009E75F
0x18009e1ad  mov     r13d, [r15+6Ch]
0x18009e1b1  call    ?CreateInstance@CWbemNamespace@@SAPEAV1@XZ; CWbemNamespace::CreateInstance(void)
0x18009e1b6  mov     rbx, rax
0x18009e1b9  mov     [rbp+0F0h+var_158], rax
0x18009e1bd  xor     r14d, r14d
0x18009e1c0  test    rax, rax
0x18009e1c3  jnz     short loc_18009E216
0x18009e1c5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009e1cb  mov     ebx, 80041006h
0x18009e1d0  mov     edx, ebx
0x18009e1d2  mov     rcx, rax
0x18009e1d5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009e1db  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e1e2  lea     rax, WPP_GLOBAL_Control
0x18009e1e9  cmp     rcx, rax
0x18009e1ec  jz      loc_18009E782
0x18009e1f2  test    byte ptr [rcx+1Ch], 1
0x18009e1f6  jz      loc_18009E782
0x18009e1fc  cmp     [rcx+19h], dil
0x18009e200  jb      loc_18009E782
0x18009e206  mov     edx, 0EBh
0x18009e20b  mov     r9d, 80041006h
0x18009e211  jmp     loc_18009E0FB
0x18009e216  and     r13d, 4
0x18009e21a  mov     rcx, [r15+128h]
0x18009e221  mov     edx, [r15+130h]
0x18009e228  mov     r8, [r15+120h]
0x18009e22f  mov     r10, [r15+118h]
0x18009e236  mov     r11d, [r15+80h]
0x18009e23d  jz      short loc_18009E249
0x18009e23f  mov     r9d, [r15+6Ch]
0x18009e243  mov     eax, [r15+68h]
0x18009e247  jmp     short loc_18009E24F
0x18009e249  mov     r9d, r14d; unsigned int
0x18009e24c  mov     eax, r14d
0x18009e24f  mov     [rsp+1F0h+var_188], r14d; unsigned int
0x18009e254  mov     [rsp+1F0h+var_190], r14; struct IWmiDbSession *
0x18009e259  mov     [rsp+1F0h+var_1A0], rcx; unsigned __int64
0x18009e25e  mov     [rsp+1F0h+var_1A8], edx; unsigned int
0x18009e262  mov     [rsp+1F0h+var_1B0], r8; unsigned __int16 *
0x18009e267  mov     [rsp+1F0h+lpUsedDefaultChar], r10; unsigned __int16 *
0x18009e26c  mov     dword ptr [rsp+1F0h+lpDefaultChar], r14d; int
0x18009e271  mov     [rsp+1F0h+cbMultiByte], r11d; bool
0x18009e276  mov     dword ptr [rsp+1F0h+lpMultiByteStr], eax; unsigned int
0x18009e27a  mov     r8, [r15+70h]; unsigned __int16 *
0x18009e27e  mov     rdx, r12; unsigned __int16 *
0x18009e281  mov     rcx, rbx; this
0x18009e284  call    ?Initialize@CWbemNamespace@@QEAAJPEAG0KKHHPEBG1K_KHPEAUIWmiDbSession@@K@Z; CWbemNamespace::Initialize(ushort *,ushort *,ulong,ulong,int,int,ushort const *,ushort const *,ulong,unsigned __int64,int,IWmiDbSession *,ulong)
0x18009e289  mov     r14d, eax
0x18009e28c  test    eax, eax
0x18009e28e  jns     short loc_18009E2F3
0x18009e290  mov     rcx, rbx; this
0x18009e293  call    ?Release@CWbemNamespace@@UEAAKXZ; CWbemNamespace::Release(void)
0x18009e298  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009e29e  mov     edx, r14d
0x18009e2a1  mov     rcx, rax
0x18009e2a4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009e2aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e2b1  lea     rax, WPP_GLOBAL_Control
0x18009e2b8  cmp     rcx, rax
0x18009e2bb  jz      short loc_18009E2E2
0x18009e2bd  test    byte ptr [rcx+1Ch], 1
0x18009e2c1  jz      short loc_18009E2E2
0x18009e2c3  cmp     [rcx+19h], dil
0x18009e2c7  jb      short loc_18009E2E2
  ... truncated ...
```
