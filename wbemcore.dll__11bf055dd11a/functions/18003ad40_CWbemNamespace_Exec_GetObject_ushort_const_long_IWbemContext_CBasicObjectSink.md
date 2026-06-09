# CWbemNamespace::Exec_GetObject(ushort const *,long,IWbemContext *,CBasicObjectSink *)

- ea: `0x18003ad40`
- end: `0x18003be16`
- name: `?Exec_GetObject@CWbemNamespace@@QEAAJPEBGJPEAUIWbemContext@@PEAVCBasicObjectSink@@@Z`
- size: `4310`
- prototype: `__int64 __usercall@<rax>(CWbemNamespace *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, int@<r8d>, struct IWbemContext *@<r9>, struct CBasicObjectSink *)`
- caller_count: `5`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e9a0`
- `0x180039d80`
- `0x18003d050`
- `0x18007258c`
- `0x18009ddcc`

## callees

- `0x18000b140`
- `0x18000b17c`
- `0x18000b1dc`
- `0x180010e80`
- `0x18001307c`
- `0x180013350`
- `0x180013710`
- `0x18002c9f0`
- `0x180036444`
- `0x180039d40`
- `0x180039f68`
- `0x180039f98`
- `0x18003ad40`
- `0x18003be20`
- `0x18003c000`
- `0x18003c2c0`
- `0x18003cd90`
- `0x18003cfe0`
- `0x18009ddcc`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18003b829`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18003b829`
- `wbemcomn!?GetLocales@CMUILocaleList@@QEAAPEBGXZ` at `0x18003b06a`
- `wbemcomn!?GetLocales@CMUILocaleList@@QEAAPEBGXZ` at `0x18003b06a`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003b04d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003b230`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003b619`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003b04d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003b230`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003b619`
- `wbemcomn!GetMemLogObject` at `0x18003ae8f`
- `wbemcomn!GetMemLogObject` at `0x18003af42`
- `wbemcomn!GetMemLogObject` at `0x18003b4b5`
- `wbemcomn!GetMemLogObject` at `0x18003b668`
- `wbemcomn!GetMemLogObject` at `0x18003b769`
- `wbemcomn!GetMemLogObject` at `0x18003b8c3`
- `wbemcomn!GetMemLogObject` at `0x18003b99a`
- `wbemcomn!GetMemLogObject` at `0x18003b9cc`
- `wbemcomn!GetMemLogObject` at `0x18003ba28`
- `wbemcomn!GetMemLogObject` at `0x18003ba88`
- `wbemcomn!GetMemLogObject` at `0x18003bb10`
- `wbemcomn!GetMemLogObject` at `0x18003bb8c`
- `wbemcomn!GetMemLogObject` at `0x18003bc96`
- `wbemcomn!GetMemLogObject` at `0x18003bd4f`
- `wbemcomn!GetMemLogObject` at `0x18003ae8f`
- `wbemcomn!GetMemLogObject` at `0x18003af42`
- `wbemcomn!GetMemLogObject` at `0x18003b4b5`
- `wbemcomn!GetMemLogObject` at `0x18003b668`
- `wbemcomn!GetMemLogObject` at `0x18003b769`
- `wbemcomn!GetMemLogObject` at `0x18003b8c3`
- `wbemcomn!GetMemLogObject` at `0x18003b99a`
- `wbemcomn!GetMemLogObject` at `0x18003b9cc`
- `wbemcomn!GetMemLogObject` at `0x18003ba28`
- `wbemcomn!GetMemLogObject` at `0x18003ba88`
- `wbemcomn!GetMemLogObject` at `0x18003bb10`
- `wbemcomn!GetMemLogObject` at `0x18003bb8c`
- `wbemcomn!GetMemLogObject` at `0x18003bc96`
- `wbemcomn!GetMemLogObject` at `0x18003bd4f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ae9d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003af50`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b4c3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b676`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b777`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b8d1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b9a5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b9da`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ba33`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ba96`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003bb1b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003bb9d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003bca4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003bd5a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ae9d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003af50`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b4c3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b676`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b777`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b8d1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b9a5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b9da`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ba33`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ba96`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003bb1b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003bb9d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003bca4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003bd5a`
- `FastProx!?InitEmpty@CWbemClass@@QEAAJHH@Z` at `0x18003b6b7`
- `FastProx!?InitEmpty@CWbemClass@@QEAAJHH@Z` at `0x18003b6b7`
- `FastProx!??0CWbemClass@@QEAA@XZ` at `0x18003b632`
- `FastProx!??0CWbemClass@@QEAA@XZ` at `0x18003b632`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CWbemNamespace::Exec_GetObject(
        const unsigned __int16 **this,
        unsigned __int16 *a2,
        int a3,
        struct IWbemContext *a4,
        struct CBasicObjectSink *a5)
{
  unsigned __int16 *v5; // rsi
  const unsigned __int16 **v6; // r13
  struct CBasicObjectSink *v7; // rbx
  volatile signed __int32 *v8; // r15
  unsigned __int16 *v9; // r9
  unsigned __int16 *v10; // rax
  int v11; // ebx
  struct IWbemPath *v12; // r14
  volatile signed __int32 *v13; // rbx
  CMemoryLog *v14; // rax
  volatile signed __int32 *v16; // rbx
  CMemoryLog *v17; // rax
  unsigned int v18; // ebx
  CReleaseMe *v19; // rcx
  CLocaleMergingSink *v20; // rdi
  const unsigned __int16 *Locales; // rax
  int DbPtr; // edi
  char v23; // al
  volatile signed __int32 *v24; // r12
  int Class; // eax
  BOOL (__stdcall *IsRelative)(IWbemPath *, LPWSTR, LPWSTR); // r12
  const unsigned __int16 *v27; // rbx
  unsigned __int16 *i; // rcx
  unsigned __int16 v29; // ax
  CBasicObjectSink *v30; // rax
  struct CBasicObjectSink *v31; // r13
  __int64 v32; // rcx
  CWbemNamespace *v33; // rax
  CClientCnt *v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rbx
  struct IWbemPath *v37; // rbx
  int v38; // ebx
  CMemoryLog *v39; // rax
  int Instance; // eax
  CWbemClass *v41; // rax
  CWbemClass *v42; // rdi
  CObjectSink *v43; // rbx
  CMemoryLog *v44; // rax
  int inited; // eax
  unsigned int v46; // ebx
  CObjectSink *v47; // rbx
  CMemoryLog *v48; // rax
  __int64 v49; // r13
  __int64 v50; // rax
  WCHAR *v51; // rcx
  unsigned __int16 near **v52; // rdx
  WCHAR v53; // r8
  int v54; // ecx
  unsigned __int16 near **v55; // rcx
  CObjectSink *v56; // rbx
  CMemoryLog *v57; // rax
  unsigned int v58; // edi
  CMemoryLog *v59; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v61; // rax
  CMemoryLog *v62; // rax
  CMemoryLog *v63; // rax
  CMemoryLog *v64; // rax
  int ObjectByFullPath; // eax
  struct IWbemPath *NewPath; // rax
  CMemoryLog *v67; // rax
  CMemoryLog *v68; // rax
  int v69; // [rsp+40h] [rbp-91h]
  volatile signed __int32 *v70; // [rsp+48h] [rbp-89h] BYREF
  __int64 v71; // [rsp+50h] [rbp-81h]
  char v72[8]; // [rsp+58h] [rbp-79h] BYREF
  CObjectSink *v73; // [rsp+60h] [rbp-71h]
  CWbemNamespace *v74; // [rsp+68h] [rbp-69h]
  struct IWbemPath *v75; // [rsp+70h] [rbp-61h] BYREF
  DWORD nSize[2]; // [rsp+78h] [rbp-59h] BYREF
  struct IWbemPath *v77; // [rsp+80h] [rbp-51h] BYREF
  CWbemClass *v78; // [rsp+88h] [rbp-49h] BYREF
  void *v79; // [rsp+90h] [rbp-41h] BYREF
  __int64 v80; // [rsp+98h] [rbp-39h] BYREF
  struct IWbemPath *v81; // [rsp+A0h] [rbp-31h]
  struct IWbemContext *v82; // [rsp+A8h] [rbp-29h]
  WCHAR Buffer[16]; // [rsp+B0h] [rbp-21h] BYREF

  v82 = a4;
  v69 = a3;
  v5 = a2;
  v6 = this;
  v74 = (CWbemNamespace *)this;
  v7 = a5;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 248, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, a2);
    a3 = v69;
  }
  v8 = 0;
  if ( v5 && *v5 && *v5 != 95 && (a3 & 0x20000) != 0 )
  {
    v20 = (CLocaleMergingSink *)CWin32DefaultArena::WbemMemAlloc(0xF0u);
    v79 = v20;
    if ( v20 )
    {
      Locales = CMUILocaleList::GetLocales((CMUILocaleList *)(v6 + 22));
      v8 = (volatile signed __int32 *)CLocaleMergingSink::CLocaleMergingSink(v20, a5, Locales);
    }
    else
    {
      v8 = 0;
    }
    if ( !v8 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2147217402);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          249,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          2147749894LL);
      }
      return CBasicObjectSink::Return(a5, -2147217402, 0);
    }
    DbPtr = CLocaleMergingSink::GetDbPtr((CLocaleMergingSink *)v8, v6[12]);
    if ( DbPtr < 0 )
    {
      v61 = GetMemLogObject();
      CMemoryLog::Write(v61, DbPtr);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          250,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          (unsigned int)DbPtr);
      }
      CLocaleMergingSink::`vector deleting destructor'((CLocaleMergingSink *)v8, 1u);
      return CBasicObjectSink::Return(a5, DbPtr, 0);
    }
    _InterlockedIncrement(v8 + 4);
    v7 = (struct CBasicObjectSink *)v8;
  }
  v70 = v8;
  v9 = v5;
  if ( !v5 )
    v9 = (unsigned __int16 *)&psz;
  COperationError::COperationError((COperationError *)v72, v7, L"GetObject", v9, 1);
  if ( v72[0] )
  {
    if ( !v5 || !*v5 )
    {
      v41 = (CWbemClass *)CWin32DefaultArena::WbemMemAlloc(0x360u);
      v42 = v41;
      v81 = (struct IWbemPath *)v41;
      if ( v41 )
      {
        CWbemClass::CWbemClass(v41);
        *(_QWORD *)v42 = &CWbemClass::`local vftable'{for `_IWmiObject'};
      }
      else
      {
        v42 = 0;
      }
      if ( !v42 )
      {
        v43 = v73;
        if ( v73 )
          COperationErrorSink::SetStatus(v73, 0, -2147217402, 0, 0);
        v44 = GetMemLogObject();
        CMemoryLog::Write(v44, -2147217402);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            107,
            WPP_ffbbabd785873c07a1ea9257e814c720_Traceguids,
            2147749894LL);
        }
        if ( v43 )
          CObjectSink::Release(v43);
        goto LABEL_22;
      }
      v78 = v42;
      inited = CWbemClass::InitEmpty(v42, 0, 1);
      if ( inited < 0 )
      {
        v46 = COperationError::ErrorOccurred((COperationError *)v72, inited, 0);
        (*(void (__fastcall **)(CWbemClass *))(*(_QWORD *)v42 + 16LL))(v42);
        v78 = 0;
        if ( v73 )
          CObjectSink::Release(v73);
        if ( v8 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 16LL))(v8);
        v70 = 0;
        return v46;
      }
      v79 = v42;
      (*(void (__fastcall **)(struct CBasicObjectSink *, __int64, void **))(*(_QWORD *)v7 + 24LL))(v7, 1, &v79);
      v18 = COperationError::ErrorOccurred((COperationError *)v72, 0, 0);
      v19 = (CReleaseMe *)&v78;
      goto LABEL_39;
    }
    v10 = v5;
    do
    {
      if ( v10 >= &v5[(unsigned int)g_PathLimit + 1] )
        break;
      ++v10;
    }
    while ( *v10 );
    if ( v10 - v5 > (unsigned __int64)(unsigned int)g_PathLimit )
    {
      v16 = (volatile signed __int32 *)v73;
      if ( v73 )
        COperationErrorSink::SetStatus(v73, 0, -2147217300, 0, 0);
      v17 = GetMemLogObject();
      CMemoryLog::Write(v17, -2147217300);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          107,
          WPP_ffbbabd785873c07a1ea9257e814c720_Traceguids,
          2147749996LL);
      }
      if ( v16 && _InterlockedExchangeAdd(v16 + 4, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v16 + 80LL))(v16, 1);
      if ( v8 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 16LL))(v8);
      v70 = 0;
      return 2147749996LL;
    }
    if ( !g_pPathFac )
      goto LABEL_15;
    v77 = 0;
    v11 = ((__int64 (__fastcall *)(struct IClassFactory *, _QWORD, GUID *, struct IWbemPath **))g_pPathFac->lpVtbl->CreateInstance)(
            g_pPathFac,
            0,
            &IID_IWbemPath,
            &v77);
    if ( v11 < 0 )
    {
      v63 = GetMemLogObject();
      CMemoryLog::Write(v63, -1);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          109,
          WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
          (unsigned int)v11);
      }
      goto LABEL_15;
    }
    v12 = v77;
    if ( !v77 )
    {
LABEL_15:
      v13 = (volatile signed __int32 *)v73;
      if ( v73 )
        COperationErrorSink::SetStatus(v73, 0, -2147217402, 0, 0);
      v14 = GetMemLogObject();
      CMemoryLog::Write(v14, -2147217402);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          107,
          WPP_ffbbabd785873c07a1ea9257e814c720_Traceguids,
          2147749894LL);
      }
      if ( v13 && _InterlockedExchangeAdd(v13 + 4, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v13 + 80LL))(v13, 1);
LABEL_22:
      if ( v8 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 16LL))(v8);
LABEL_24:
      v70 = 0;
      return 2147749894LL;
    }
    v75 = v77;
    if ( ((int (__fastcall *)(struct IWbemPath *, __int64, unsigned __int16 *))v77->lpVtbl->SetText)(v77, 4, v5) < 0 )
    {
      v47 = v73;
      if ( v73 )
        COperationErrorSink::SetStatus(v73, 0, -2147217350, 0, 0);
      v48 = GetMemLogObject();
      CMemoryLog::Write(v48, -2147217350);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          107,
          WPP_ffbbabd785873c07a1ea9257e814c720_Traceguids,
          2147749946LL);
      }
      ((void (__fastcall *)(struct IWbemPath *))v12->lpVtbl->Release)(v12);
      v75 = 0;
      if ( v47 )
        CObjectSink::Release(v47);
      if ( !v8 )
        goto LABEL_134;
    }
    else
    {
      v80 = 0;
      if ( ((int (__fastcall *)(struct IWbemPath *, _QWORD, __int64 *))v12->lpVtbl->GetInfo)(v12, 0, &v80) < 0
        || (v80 & 0xC) == 0 )
      {
        v18 = COperationError::ErrorOccurred((COperationError *)v72, -2147217350, 0);
        v19 = (CReleaseMe *)&v75;
LABEL_39:
        CReleaseMe::release(v19);
        goto LABEL_40;
      }
      IsRelative = v12->lpVtbl->IsRelative;
      v27 = v6[12];
      if ( ConfigMgr::g_FirstCallToGetMachineName )
      {
        v49 = 16;
        nSize[0] = 16;
        GetComputerNameExW(ComputerNameNetBIOS, Buffer, nSize);
        ConfigMgr::g_FirstCallToGetMachineName = 0;
        v50 = 2147483646;
        v51 = Buffer;
        v52 = &ConfigMgr::g_ThisMachineName;
        do
        {
          if ( !v50 )
            break;
          v53 = *v51;
          if ( !*v51 )
            break;
          ++v51;
          *(_WORD *)v52 = v53;
          v52 = (unsigned __int16 near **)((char *)v52 + 2);
          --v50;
          --v49;
        }
        while ( v49 );
        v54 = -2147024774;
        if ( v49 )
          v54 = 0;
        LODWORD(v71) = v54;
        v55 = (unsigned __int16 near **)((char *)v52 - 2);
        if ( v49 )
          v55 = v52;
        *(_WORD *)v55 = 0;
        if ( !v49 )
        {
          v64 = GetMemLogObject();
          CMemoryLog::Write(v64, v71);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              52,
              WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
              (unsigned int)v71);
          }
        }
        v6 = (const unsigned __int16 **)v74;
      }
      if ( !((unsigned int (__fastcall *)(struct IWbemPath *, unsigned __int16 near **, const unsigned __int16 *))IsRelative)(
              v12,
              &ConfigMgr::g_ThisMachineName,
              v27) )
      {
        ObjectByFullPath = CWbemNamespace::GetObjectByFullPath((CWbemNamespace *)v6, v5, v12, v69, v82, v73);
        v18 = COperationError::ErrorOccurred((COperationError *)v72, ObjectByFullPath, 0);
        v19 = (CReleaseMe *)&v75;
        goto LABEL_39;
      }
      for ( i = v5; ; ++i )
      {
        v29 = *i;
        if ( !*i || v29 == 61 )
        {
          v23 = v80;
          goto LABEL_53;
        }
        if ( v29 == 58 )
          break;
      }
      v23 = v80;
      if ( (v80 & 0x20000) != 0 )
      {
        v5 = i + 1;
LABEL_53:
        if ( (v23 & 8) == 0 )
        {
          v24 = (volatile signed __int32 *)v73;
          Class = CWbemNamespace::Exec_GetClass((CWbemNamespace *)v6, v5, v69, v82, v73);
          v18 = Class;
          if ( Class < 0 )
          {
            if ( v24 )
              COperationErrorSink::SetStatus((COperationErrorSink *)v24, 0, Class, 0, 0);
            v58 = -2147217406;
            if ( v18 != -2147217406 )
            {
              v59 = GetMemLogObject();
              CMemoryLog::Write(v59, v18);
              if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, WPP_ffbbabd785873c07a1ea9257e814c720_Traceguids, v18);
              }
              v58 = v18;
            }
            ((void (__fastcall *)(struct IWbemPath *))v12->lpVtbl->Release)(v12);
            v75 = 0;
            if ( v24 )
              CObjectSink::Release((CObjectSink *)v24);
            if ( v8 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 16LL))(v8);
            v70 = 0;
            return v58;
          }
          goto LABEL_55;
        }
        v30 = (CBasicObjectSink *)CWin32DefaultArena::WbemMemAlloc(0x38u);
        v31 = v30;
        v79 = v30;
        v24 = (volatile signed __int32 *)v73;
        if ( v30 )
        {
          CBasicObjectSink::CBasicObjectSink(v30);
          *(_QWORD *)v32 = &CObjectSink::`vftable'{for `IWbemObjectSinkEx'};
          *(_QWORD *)(v32 + 8) = &CInternalMerger::COwnSink::`vftable'{for `CDestination'};
          *(_DWORD *)(v32 + 16) = 0;
          *(_QWORD *)v32 = &CForwardingSink::`vftable'{for `IWbemObjectSinkEx'};
          *(_QWORD *)(v32 + 8) = &CInternalMerger::COwnSink::`vftable'{for `CDestination'};
          *((_QWORD *)v31 + 3) = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 88LL))(v24);
          *((_QWORD *)v31 + 4) = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 96LL))(v24);
          *((_QWORD *)v31 + 5) = v24;
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v31 + 3) + 8LL))(*((_QWORD *)v31 + 3));
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v31 + 4) + 8LL))(*((_QWORD *)v31 + 4));
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v31 + 5) + 8LL))(*((_QWORD *)v31 + 5));
          *(_QWORD *)v31 = &CFinalizingSink::`vftable'{for `IWbemObjectSinkEx'};
          *((_QWORD *)v31 + 1) = &CInternalMerger::COwnSink::`vftable'{for `CDestination'};
          v33 = v74;
          *((_QWORD *)v31 + 6) = v74;
          _InterlockedIncrement((volatile signed __int32 *)v33 + 6);
        }
        else
        {
          v31 = 0;
        }
        if ( !v31 )
        {
          if ( v24 )
            COperationErrorSink::SetStatus((COperationErrorSink *)v24, 0, -2147217402, 0, 0);
          v39 = GetMemLogObject();
          CMemoryLog::Write(v39, -2147217402);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              107,
              WPP_ffbbabd785873c07a1ea9257e814c720_Traceguids,
              2147749894LL);
          }
          ((void (__fastcall *)(struct IWbemPath *))v12->lpVtbl->Release)(v12);
          v75 = 0;
          if ( v24 )
            CObjectSink::Release((CObjectSink *)v24);
          if ( v8 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 16LL))(v8);
          goto LABEL_24;
        }
        (*(void (__fastcall **)(struct CBasicObjectSink *))(*(_QWORD *)v31 + 8LL))(v31);
        v78 = v31;
        v34 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 253, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v5);
          v34 = WPP_GLOBAL_Control;
        }
        if ( v69 < 0 )
          goto LABEL_100;
        *(_QWORD *)nSize = 0;
        v35 = *((_QWORD *)v74 + 8);
        v71 = v35;
        v36 = *((_QWORD *)v74 + 5);
        if ( v34 != (CClientCnt *)&WPP_GLOBAL_Control && (*((_BYTE *)v34 + 28) & 1) != 0 && *((_BYTE *)v34 + 25) >= 5u )
          WPP_SF_qqS(
            *((_QWORD *)v34 + 2),
            46,
            (unsigned int)WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids,
            v36,
            v35,
            (__int64)v5);
        v77 = 0;
        if ( (**(int (__fastcall ***)(__int64, GUID *, struct IWbemPath **))v36)(v36, &IID_IWmiDbSessionEx, &v77) < 0 )
        {
          NewPath = ConfigMgr::GetNewPath();
          v81 = NewPath;
          if ( !NewPath )
          {
            v67 = GetMemLogObject();
            CMemoryLog::Write(v67, -2147217402);
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                47,
                WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids,
                2147749894LL);
            }
            goto LABEL_100;
          }
          v79 = NewPath;
          ((void (__fastcall *)(struct IWbemPath *, __int64, unsigned __int16 *))NewPath->lpVtbl->SetText)(
            NewPath,
            4,
            v5);
          v38 = (*(__int64 (__fastcall **)(__int64, __int64, struct IWbemPath *, _QWORD, GUID *, DWORD *))(*(_QWORD *)v36 + 32LL))(
                  v36,
                  v71,
                  v81,
                  (unsigned int)v69,
                  &IID_IWbemClassObject,
                  nSize);
          CReleaseMe::release((CReleaseMe *)&v79);
        }
        else
        {
          v37 = v77;
          v81 = v77;
          LODWORD(v71) = ((__int64 (__fastcall *)(struct IWbemPath *, __int64, unsigned __int16 *, _QWORD, GUID *, DWORD *))v77->lpVtbl->RemoveAllNamespaces)(
                           v77,
                           v71,
                           v5,
                           (unsigned int)v69,
                           &IID_IWbemClassObject,
                           nSize);
          if ( v37 )
            ((void (__fastcall *)(struct IWbemPath *))v37->lpVtbl->Release)(v37);
          v81 = 0;
          v38 = v71;
        }
        if ( v38 != -2147217406 )
        {
          if ( v38 < 0 )
          {
            v68 = GetMemLogObject();
            CMemoryLog::Write(v68, v38);
          }
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              48,
              WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids,
              (unsigned int)v38);
          }
          if ( v38 >= 0 )
          {
            (**((void (__fastcall ***)(__int64, _QWORD))v31 + 1))((__int64)v31 + 8, *(_QWORD *)nSize);
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)nSize + 16LL))(*(_QWORD *)nSize);
            (*(void (__fastcall **)(struct CBasicObjectSink *, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v31 + 32LL))(
              v31,
              0,
              0,
              0,
              0);
            v18 = 0;
LABEL_90:
            (*(void (__fastcall **)(struct CBasicObjectSink *))(*(_QWORD *)v31 + 16LL))(v31);
            v78 = 0;
LABEL_55:
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 252, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v18);
            }
            ((void (__fastcall *)(struct IWbemPath *))v12->lpVtbl->Release)(v12);
            v75 = 0;
            if ( v24 && _InterlockedExchangeAdd(v24 + 4, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v24 + 80LL))(v24, 1);
LABEL_60:
            if ( v8 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 16LL))(v8);
            v70 = 0;
            return v18;
          }
        }
LABEL_100:
        Instance = CWbemNamespace::DynAux_GetInstance(v74, v5, v69, v82, v31);
        v18 = Instance;
        if ( Instance < 0 )
        {
          v18 = COperationError::ErrorOccurred((COperationError *)v72, Instance, 0);
          (*(void (__fastcall **)(struct CBasicObjectSink *))(*(_QWORD *)v31 + 16LL))(v31);
          v78 = 0;
          ((void (__fastcall *)(struct IWbemPath *))v12->lpVtbl->Release)(v12);
          v75 = 0;
          if ( v24 )
            CObjectSink::Release((CObjectSink *)v24);
          goto LABEL_60;
        }
        goto LABEL_90;
      }
      v56 = v73;
      if ( v73 )
        COperationErrorSink::SetStatus(v73, 0, -2147217350, 0, 0);
      v57 = GetMemLogObject();
      CMemoryLog::Write(v57, -2147217350);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          107,
          WPP_ffbbabd785873c07a1ea9257e814c720_Traceguids,
          2147749946LL);
      }
      ((void (__fastcall *)(struct IWbemPath *))v12->lpVtbl->Release)(v12);
      v75 = 0;
      if ( v56 )
        CObjectSink::Release(v56);
      if ( !v8 )
      {
LABEL_134:
        v70 = 0;
        return 2147749946LL;
      }
    }
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 16LL))(v8);
    goto LABEL_134;
  }
  v62 = GetMemLogObject();
  CMemoryLog::Write(v62, -2147217402);
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 251, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749894LL);
  }
  v18 = CBasicObjectSink::Return(v7, -2147217402, 0);
LABEL_40:
  COperationError::~COperationError((COperationError *)v72);
  CReleaseMe::release((CReleaseMe *)&v70);
  return v18;
}

```

## disassembly

```asm
0x18003ad40  push    rbp
0x18003ad42  push    rbx
0x18003ad43  push    rsi
0x18003ad44  push    rdi
0x18003ad45  push    r12
0x18003ad47  push    r13
0x18003ad49  push    r14
0x18003ad4b  push    r15
0x18003ad4d  lea     rbp, [rsp-17h]
0x18003ad52  sub     rsp, 0E8h
0x18003ad59  mov     rax, cs:__security_cookie
0x18003ad60  xor     rax, rsp
0x18003ad63  mov     [rbp+4Fh+var_50], rax
0x18003ad67  mov     [rbp+4Fh+var_78], r9
0x18003ad6b  mov     [rsp+120h+var_E0], r8d
0x18003ad70  mov     rsi, rdx
0x18003ad73  mov     r13, rcx
0x18003ad76  mov     [rbp+4Fh+var_B8], rcx
0x18003ad7a  mov     rbx, [rbp+4Fh+arg_20]
0x18003ad7e  lea     r14, WPP_GLOBAL_Control
0x18003ad85  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ad8c  cmp     rcx, r14
0x18003ad8f  jnz     loc_18003B0AD
0x18003ad95  xor     r12d, r12d
0x18003ad98  mov     r15d, r12d
0x18003ad9b  test    rsi, rsi
0x18003ad9e  jnz     loc_18003B027
0x18003ada4  mov     [rsp+120h+var_D8], r15
0x18003ada9  lea     rax, psz
0x18003adb0  mov     r9, rsi
0x18003adb3  test    rsi, rsi
0x18003adb6  cmovz   r9, rax; unsigned __int16 *
0x18003adba  mov     dword ptr [rsp+120h+var_100], 1; int
0x18003adc2  lea     r8, aGetobject; "GetObject"
0x18003adc9  mov     rdx, rbx; struct CBasicObjectSink *
0x18003adcc  lea     rcx, [rbp+4Fh+var_C8]; this
0x18003add0  call    ??0COperationError@@QEAA@PEAVCBasicObjectSink@@PEBG1H@Z; COperationError::COperationError(CBasicObjectSink *,ushort const *,ushort const *,int)
0x18003add5  nop
0x18003add6  cmp     [rbp+4Fh+var_C8], 0
0x18003adda  jz      loc_18003BA88
0x18003ade0  test    rsi, rsi
0x18003ade3  jz      loc_18003B614
0x18003ade9  cmp     word ptr [rsi], 0
0x18003aded  jz      loc_18003B614
0x18003adf3  mov     rax, rsi
0x18003adf6  mov     edx, cs:?g_PathLimit@@3KA; ulong g_PathLimit
0x18003adfc  lea     rcx, [rdx+1]
0x18003ae00  lea     rcx, [rsi+rcx*2]
0x18003ae04  cmp     rax, rcx
0x18003ae07  jnb     short loc_18003AE13
0x18003ae09  add     rax, 2
0x18003ae0d  cmp     word ptr [rax], 0
0x18003ae11  jnz     short loc_18003AE04
0x18003ae13  sub     rax, rsi
0x18003ae16  sar     rax, 1
0x18003ae19  cmp     rax, rdx
0x18003ae1c  ja      loc_18003AF21
0x18003ae22  mov     edi, 0FFFFFFFFh
0x18003ae27  mov     rcx, cs:?g_pPathFac@@3PEAUIClassFactory@@EA; IClassFactory * g_pPathFac
0x18003ae2e  test    rcx, rcx
0x18003ae31  jz      short loc_18003AE6E
0x18003ae33  mov     [rbp+4Fh+var_A0], r12
0x18003ae37  mov     rax, [rcx]
0x18003ae3a  lea     r9, [rbp+4Fh+var_A0]
0x18003ae3e  lea     r8, IID_IWbemPath
0x18003ae45  xor     edx, edx
0x18003ae47  mov     rax, [rax+18h]
0x18003ae4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ae50  mov     ebx, eax
0x18003ae52  test    eax, eax
0x18003ae54  js      loc_18003BB10
0x18003ae5a  mov     r14, [rbp+4Fh+var_A0]
0x18003ae5e  test    r14, r14
0x18003ae61  jnz     loc_18003AFA7
0x18003ae67  lea     r14, WPP_GLOBAL_Control
0x18003ae6e  mov     rbx, [rbp+4Fh+var_C0]
0x18003ae72  test    rbx, rbx
0x18003ae75  jz      short loc_18003AE8F
0x18003ae77  mov     [rsp+120h+var_100], r12; struct IWbemClassObject *
0x18003ae7c  xor     r9d, r9d; unsigned __int16 *
0x18003ae7f  xor     edx, edx; int
0x18003ae81  mov     r8d, 80041006h; int
0x18003ae87  mov     rcx, rbx; this
0x18003ae8a  call    ?SetStatus@COperationErrorSink@@UEAAJJJPEAGPEAUIWbemClassObject@@@Z; COperationErrorSink::SetStatus(long,long,ushort *,IWbemClassObject *)
0x18003ae8f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003ae95  mov     edx, 80041006h
0x18003ae9a  mov     rcx, rax
0x18003ae9d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003aea3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003aeaa  cmp     rcx, r14
0x18003aead  jz      short loc_18003AEB9
0x18003aeaf  test    byte ptr [rcx+1Ch], 1
0x18003aeb3  jnz     loc_18003BD8C
0x18003aeb9  test    rbx, rbx
0x18003aebc  jz      short loc_18003AEC8
0x18003aebe  lock xadd [rbx+10h], edi
0x18003aec3  cmp     edi, 1
0x18003aec6  jz      short loc_18003AF06
0x18003aec8  test    r15, r15
0x18003aecb  jz      short loc_18003AEDC
0x18003aecd  mov     rax, [r15]
0x18003aed0  mov     rcx, r15
0x18003aed3  mov     rax, [rax+10h]
0x18003aed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aedc  mov     [rsp+120h+var_D8], r12
0x18003aee1  mov     eax, 80041006h
0x18003aee6  mov     rcx, [rbp+4Fh+var_50]
0x18003aeea  xor     rcx, rsp; StackCookie
0x18003aeed  call    __security_check_cookie
0x18003aef2  add     rsp, 0E8h
0x18003aef9  pop     r15
0x18003aefb  pop     r14
0x18003aefd  pop     r13
0x18003aeff  pop     r12
0x18003af01  pop     rdi
0x18003af02  pop     rsi
0x18003af03  pop     rbx
0x18003af04  pop     rbp
0x18003af05  retn
0x18003af06  test    rbx, rbx
0x18003af09  jz      short loc_18003AEC8
0x18003af0b  mov     rax, [rbx]
0x18003af0e  mov     edx, 1
0x18003af13  mov     rcx, rbx
0x18003af16  mov     rax, [rax+50h]
0x18003af1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003af1f  jmp     short loc_18003AEC8
0x18003af21  mov     rbx, [rbp+4Fh+var_C0]
0x18003af25  test    rbx, rbx
0x18003af28  jz      short loc_18003AF42
0x18003af2a  mov     [rsp+120h+var_100], r12; struct IWbemClassObject *
0x18003af2f  xor     r9d, r9d; unsigned __int16 *
0x18003af32  xor     edx, edx; int
0x18003af34  mov     r8d, 8004106Ch; int
0x18003af3a  mov     rcx, rbx; this
0x18003af3d  call    ?SetStatus@COperationErrorSink@@UEAAJJJPEAGPEAUIWbemClassObject@@@Z; COperationErrorSink::SetStatus(long,long,ushort *,IWbemClassObject *)
0x18003af42  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003af48  mov     edx, 8004106Ch
0x18003af4d  mov     rcx, rax
0x18003af50  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003af56  mov     rcx, cs:WPP_GLOBAL_Control
0x18003af5d  cmp     rcx, r14
0x18003af60  jz      short loc_18003AF6C
0x18003af62  test    byte ptr [rcx+1Ch], 1
0x18003af66  jnz     loc_18003BAE6
0x18003af6c  test    rbx, rbx
0x18003af6f  jz      short loc_18003AF84
0x18003af71  mov     edi, 0FFFFFFFFh
0x18003af76  lock xadd [rbx+10h], edi
0x18003af7b  cmp     edi, 1
0x18003af7e  jz      loc_18003B1E6
0x18003af84  test    r15, r15
0x18003af87  jz      short loc_18003AF98
0x18003af89  mov     rcx, [r15]
0x18003af8c  mov     rax, [rcx+10h]
0x18003af90  mov     rcx, r15
0x18003af93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003af98  mov     [rsp+120h+var_D8], r12
0x18003af9d  mov     eax, 8004106Ch
0x18003afa2  jmp     loc_18003AEE6
0x18003afa7  mov     [rbp+4Fh+var_B0], r14
0x18003afab  mov     rax, [r14]
0x18003afae  mov     r8, rsi
0x18003afb1  mov     edx, 4
0x18003afb6  mov     rcx, r14
0x18003afb9  mov     rax, [rax+18h]
0x18003afbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003afc2  test    eax, eax
0x18003afc4  js      loc_18003B748
0x18003afca  mov     [rbp+4Fh+var_88], r12
0x18003afce  mov     rax, [r14]
0x18003afd1  lea     r8, [rbp+4Fh+var_88]
0x18003afd5  xor     edx, edx
0x18003afd7  mov     rcx, r14
0x18003afda  mov     rax, [rax+28h]
0x18003afde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003afe3  test    eax, eax
0x18003afe5  js      short loc_18003AFF1
0x18003afe7  test    byte ptr [rbp+4Fh+var_88], 0Ch
0x18003afeb  jnz     loc_18003B183
0x18003aff1  xor     r8d, r8d; struct IWbemClassObject *
0x18003aff4  mov     edx, 8004103Ah; int
0x18003aff9  lea     rcx, [rbp+4Fh+var_C8]; this
0x18003affd  call    ?ErrorOccurred@COperationError@@QEAAJJPEAUIWbemClassObject@@@Z; COperationError::ErrorOccurred(long,IWbemClassObject *)
0x18003b002  mov     ebx, eax
0x18003b004  lea     rcx, [rbp+4Fh+var_B0]; this
0x18003b008  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x18003b00d  nop
0x18003b00e  lea     rcx, [rbp+4Fh+var_C8]; this
0x18003b012  call    ??1COperationError@@QEAA@XZ; COperationError::~COperationError(void)
0x18003b017  nop
0x18003b018  lea     rcx, [rsp+120h+var_D8]; this
0x18003b01d  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x18003b022  jmp     loc_18003B17C
0x18003b027  movzx   eax, word ptr [rsi]
0x18003b02a  test    ax, ax
0x18003b02d  jz      loc_18003ADA4
0x18003b033  cmp     ax, 5Fh ; '_'
0x18003b037  jz      loc_18003ADA4
0x18003b03d  bt      r8d, 11h
0x18003b042  jnb     loc_18003ADA4
0x18003b048  mov     ecx, 0F0h
0x18003b04d  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003b053  mov     rdi, rax
0x18003b056  mov     [rbp+4Fh+var_90], rax
0x18003b05a  test    rax, rax
0x18003b05d  jz      loc_18003B7DE
0x18003b063  lea     rcx, [r13+0B0h]
0x18003b06a  call    cs:__imp_?GetLocales@CMUILocaleList@@QEAAPEBGXZ; CMUILocaleList::GetLocales(void)
0x18003b070  mov     r8, rax; unsigned __int16 *
0x18003b073  mov     rdx, rbx; struct CBasicObjectSink *
0x18003b076  mov     rcx, rdi; this
0x18003b079  call    ??0CLocaleMergingSink@@QEAA@PEAVCBasicObjectSink@@PEBG@Z; CLocaleMergingSink::CLocaleMergingSink(CBasicObjectSink *,ushort const *)
0x18003b07e  mov     r15, rax
0x18003b081  test    r15, r15
0x18003b084  jz      loc_18003B9CC
0x18003b08a  mov     rdx, [r13+60h]; unsigned __int16 *
0x18003b08e  mov     rcx, r15; this
0x18003b091  call    ?GetDbPtr@CLocaleMergingSink@@QEAAJPEBG@Z; CLocaleMergingSink::GetDbPtr(ushort const *)
0x18003b096  mov     edi, eax
0x18003b098  test    eax, eax
0x18003b09a  js      loc_18003BA28
0x18003b0a0  lock inc dword ptr [r15+10h]
0x18003b0a5  mov     rbx, r15
0x18003b0a8  jmp     loc_18003ADA4
0x18003b0ad  test    byte ptr [rcx+1Ch], 1
0x18003b0b1  jz      loc_18003AD95
0x18003b0b7  cmp     byte ptr [rcx+19h], 5
0x18003b0bb  jb      loc_18003AD95
0x18003b0c1  mov     edx, 0F8h
0x18003b0c6  mov     r9, rsi
0x18003b0c9  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18003b0d0  mov     rcx, [rcx+10h]
0x18003b0d4  call    WPP_SF_S
0x18003b0d9  mov     r8d, [rsp+120h+var_E0]
0x18003b0de  jmp     loc_18003AD95
0x18003b0e3  mov     rax, [rbp+4Fh+var_88]
0x18003b0e7  test    al, 8
0x18003b0e9  jnz     loc_18003B22B
0x18003b0ef  mov     r12, [rbp+4Fh+var_C0]
0x18003b0f3  mov     [rsp+120h+var_100], r12; struct CBasicObjectSink *
0x18003b0f8  mov     r9, [rbp+4Fh+var_78]; struct IWbemContext *
0x18003b0fc  mov     r8d, [rsp+120h+var_E0]; int
0x18003b101  mov     rdx, rsi; psz
0x18003b104  mov     rcx, r13; this
0x18003b107  call    ?Exec_GetClass@CWbemNamespace@@QEAAJPEBGJPEAUIWbemContext@@PEAVCBasicObjectSink@@@Z; CWbemNamespace::Exec_GetClass(ushort const *,long,IWbemContext *,CBasicObjectSink *)
0x18003b10c  mov     ebx, eax
0x18003b10e  test    eax, eax
0x18003b110  js      loc_18003B92A
0x18003b116  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b11d  lea     rax, WPP_GLOBAL_Control
0x18003b124  cmp     rcx, rax
0x18003b127  jz      short loc_18003B133
0x18003b129  test    byte ptr [rcx+1Ch], 1
0x18003b12d  jnz     loc_18003B5ED
0x18003b133  mov     rax, [r14]
0x18003b136  mov     rcx, r14
0x18003b139  mov     rax, [rax+10h]
0x18003b13d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b142  mov     [rbp+4Fh+var_B0], 0
0x18003b14a  test    r12, r12
0x18003b14d  jz      short loc_18003B15F
0x18003b14f  lock xadd [r12+10h], edi
0x18003b156  cmp     edi, 1
0x18003b159  jz      loc_18003B208
0x18003b15f  test    r15, r15
0x18003b162  jz      short loc_18003B173
0x18003b164  mov     rax, [r15]
0x18003b167  mov     rcx, r15
0x18003b16a  mov     rax, [rax+10h]
0x18003b16e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b173  mov     [rsp+120h+var_D8], 0
0x18003b17c  mov     eax, ebx
0x18003b17e  jmp     loc_18003AEE6
0x18003b183  mov     rax, [r14]
0x18003b186  mov     r12, [rax+0C8h]
0x18003b18d  mov     rbx, [r13+60h]
0x18003b191  cmp     cs:?g_FirstCallToGetMachineName@ConfigMgr@@2HA, 0; int ConfigMgr::g_FirstCallToGetMachineName
0x18003b198  jnz     loc_18003B815
0x18003b19e  mov     r8, rbx
0x18003b1a1  lea     rdx, ?g_ThisMachineName@ConfigMgr@@0PAGA; ushort near * ConfigMgr::g_ThisMachineName
0x18003b1a8  mov     rcx, r14
0x18003b1ab  mov     rax, r12
0x18003b1ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b1b3  test    eax, eax
0x18003b1b5  jz      loc_18003BBEB
0x18003b1bb  mov     rcx, rsi
0x18003b1be  xchg    ax, ax
0x18003b1c0  movzx   eax, word ptr [rcx]
0x18003b1c3  test    ax, ax
0x18003b1c6  jz      loc_18003B0E3
0x18003b1cc  cmp     ax, 3Dh ; '='
0x18003b1d0  jz      loc_18003B0E3
0x18003b1d6  cmp     ax, 3Ah ; ':'
0x18003b1da  jz      loc_18003B5A0
0x18003b1e0  add     rcx, 2
0x18003b1e4  jmp     short loc_18003B1C0
0x18003b1e6  test    rbx, rbx
0x18003b1e9  jz      loc_18003AF84
0x18003b1ef  mov     rax, [rbx]
  ... truncated ...
```
