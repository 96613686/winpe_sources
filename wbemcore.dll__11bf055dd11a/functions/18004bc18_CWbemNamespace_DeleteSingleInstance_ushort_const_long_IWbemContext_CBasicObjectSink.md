# CWbemNamespace::DeleteSingleInstance(ushort const *,long,IWbemContext *,CBasicObjectSink *)

- ea: `0x18004bc18`
- end: `0x18004d2f0`
- name: `?DeleteSingleInstance@CWbemNamespace@@QEAAJPEBGJPEAUIWbemContext@@PEAVCBasicObjectSink@@@Z`
- size: `5848`
- prototype: `__int64 __usercall@<rax>(CWbemNamespace *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, int@<r8d>, struct IWbemContext *@<r9>, struct CBasicObjectSink *)`
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18004d5a0`

## callees

- `0x18000b140`
- `0x18000b17c`
- `0x18000b46c`
- `0x18000e950`
- `0x18000e99c`
- `0x18000ebd0`
- `0x18000fa74`
- `0x180011700`
- `0x18001307c`
- `0x18001f6d0`
- `0x18002427c`
- `0x180027324`
- `0x180028c10`
- `0x18002ca8c`
- `0x18002fee4`
- `0x180036a9c`
- `0x1800370c0`
- `0x180039d40`
- `0x180039f68`
- `0x180039f98`
- `0x18003be20`
- `0x18003c000`
- `0x18003cfe0`
- `0x18003d010`
- `0x18003d050`
- `0x18004b6e4`
- `0x18004ba84`
- `0x18004bc18`
- `0x18004d2f8`
- `0x1800da010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ccd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004cd47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ccd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004cd47`
- `wbemcomn!IsAdmin` at `0x18004cd39`
- `wbemcomn!IsAdmin` at `0x18004cd39`
- `wbemcomn!?GetFirst_ms_XXX_Locale@CMUILocaleList@@QEAAJPEAPEAG@Z` at `0x18004c317`
- `wbemcomn!?GetFirst_ms_XXX_Locale@CMUILocaleList@@QEAAJPEAPEAG@Z` at `0x18004c317`
- `wbemcomn!?PublishRepDelete@CPublishWMIOperationEvent@@SAJKPEAGPEAUIWbemContext@@K0_KH@Z` at `0x18004c0ce`
- `wbemcomn!?PublishRepDelete@CPublishWMIOperationEvent@@SAJKPEAGPEAUIWbemContext@@K0_KH@Z` at `0x18004d1f9`
- `wbemcomn!?PublishRepDelete@CPublishWMIOperationEvent@@SAJKPEAGPEAUIWbemContext@@K0_KH@Z` at `0x18004c0ce`
- `wbemcomn!?PublishRepDelete@CPublishWMIOperationEvent@@SAJKPEAGPEAUIWbemContext@@K0_KH@Z` at `0x18004d1f9`
- `wbemcomn!?GetBool@CVar@@QEAAFXZ` at `0x18004c26a`
- `wbemcomn!?GetBool@CVar@@QEAAFXZ` at `0x18004c26a`
- `wbemcomn!??BCVar@@QEAAPEAGXZ` at `0x18004c351`
- `wbemcomn!??BCVar@@QEAAPEAGXZ` at `0x18004c351`
- `wbemcomn!?_Free@CMUILocale@@SAHPEAX@Z` at `0x18004c32b`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18004bde3`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18004c27d`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18004bde3`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18004c27d`
- `wbemcomn!?GetType@CVar@@QEAAHXZ` at `0x18004c257`
- `wbemcomn!?GetType@CVar@@QEAAHXZ` at `0x18004c2b5`
- `wbemcomn!?GetType@CVar@@QEAAHXZ` at `0x18004c257`
- `wbemcomn!?GetType@CVar@@QEAAHXZ` at `0x18004c2b5`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004c1dd`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004c464`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004c46f`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004c6c3`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004c6ce`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004c753`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004c791`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004c91a`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004c9b8`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004cbab`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004c1dd`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004c464`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004c46f`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004c6c3`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004c6ce`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004c753`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004c791`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004c91a`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004c9b8`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004cbab`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18004bfa0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18004d00f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18004bfa0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18004d00f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18004c19f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18004c8bb`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18004c8d9`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18004c19f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18004c8bb`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18004c8d9`
- `wbemcomn!??BWString2@@QEAAPEAGXZ` at `0x18004d1cf`
- `wbemcomn!??BWString2@@QEAAPEAGXZ` at `0x18004d20a`
- `wbemcomn!??BWString2@@QEAAPEAGXZ` at `0x18004d1cf`
- `wbemcomn!??BWString2@@QEAAPEAGXZ` at `0x18004d20a`
- `wbemcomn!??0WString2@@QEAA@XZ` at `0x18004bd56`
- `wbemcomn!??0WString2@@QEAA@XZ` at `0x18004bd56`
- `wbemcomn!??0WString2@@QEAA@PEBG@Z` at `0x18004d147`
- `wbemcomn!??0WString2@@QEAA@PEBG@Z` at `0x18004d147`
- `wbemcomn!??4WString2@@QEAAAEAV0@PEBG@Z` at `0x18004d2bf`
- `wbemcomn!??4WString2@@QEAAAEAV0@PEBG@Z` at `0x18004d2bf`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18004c206`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18004c4ac`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18004c62f`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18004c70b`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18004c7ce`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18004c943`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18004c9d9`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18004cb32`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18004d292`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18004d2b1`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18004c206`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18004c4ac`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18004c62f`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18004c70b`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18004c7ce`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18004c943`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18004c9d9`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18004cb32`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18004d292`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18004d2b1`
- `wbemcomn!??YWString2@@QEAAAEAV0@PEBG@Z` at `0x18004d159`
- `wbemcomn!??YWString2@@QEAAAEAV0@PEBG@Z` at `0x18004d16d`
- `wbemcomn!??YWString2@@QEAAAEAV0@PEBG@Z` at `0x18004d159`
- `wbemcomn!??YWString2@@QEAAAEAV0@PEBG@Z` at `0x18004d16d`
- `wbemcomn!GetMemLogObject` at `0x18004c52e`
- `wbemcomn!GetMemLogObject` at `0x18004c5fa`
- `wbemcomn!GetMemLogObject` at `0x18004c690`
- `wbemcomn!GetMemLogObject` at `0x18004c801`
- `wbemcomn!GetMemLogObject` at `0x18004c861`
- `wbemcomn!GetMemLogObject` at `0x18004cbb6`
- `wbemcomn!GetMemLogObject` at `0x18004cbf3`
- `wbemcomn!GetMemLogObject` at `0x18004cc8a`
- `wbemcomn!GetMemLogObject` at `0x18004cd52`
- `wbemcomn!GetMemLogObject` at `0x18004cdab`
- `wbemcomn!GetMemLogObject` at `0x18004c52e`
- `wbemcomn!GetMemLogObject` at `0x18004c5fa`
- `wbemcomn!GetMemLogObject` at `0x18004c690`
- `wbemcomn!GetMemLogObject` at `0x18004c801`
- `wbemcomn!GetMemLogObject` at `0x18004c861`
- `wbemcomn!GetMemLogObject` at `0x18004cbb6`
- `wbemcomn!GetMemLogObject` at `0x18004cbf3`
- `wbemcomn!GetMemLogObject` at `0x18004cc8a`
- `wbemcomn!GetMemLogObject` at `0x18004cd52`
- `wbemcomn!GetMemLogObject` at `0x18004cdab`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004c53c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004c608`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004c69c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004c80f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004c86d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004cbc1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004cbfe`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004cc97`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004cd5d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004cdb9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004c53c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004c608`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004c69c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004c80f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004c86d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004cbc1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004cbfe`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004cc97`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004cd5d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004cdb9`
- `wbemcomn!GetAccessToken` at `0x18004cc66`
- `wbemcomn!GetAccessToken` at `0x18004cc66`
- `OLEAUT32!__imp_SysAllocString` at `0x18004c3c8`
- `OLEAUT32!__imp_SysAllocString` at `0x18004c3c8`
- `OLEAUT32!__imp_SysFreeString` at `0x18004c424`
- `OLEAUT32!__imp_SysFreeString` at `0x18004c424`
- `OLEAUT32!__imp_VariantInit` at `0x18004c060`
- `OLEAUT32!__imp_VariantInit` at `0x18004d17a`
- `OLEAUT32!__imp_VariantInit` at `0x18004c060`
- `OLEAUT32!__imp_VariantInit` at `0x18004d17a`
- `OLEAUT32!__imp_VariantClear` at `0x18004c180`
- `OLEAUT32!__imp_VariantClear` at `0x18004c180`

## string_xrefs

- `0x18004bc75`: `DeleteInstance`
- `0x18004bd0a`: `__SystemSecurity`
- `0x18004be84`: `Delete (DeleteInstance)`
- `0x18004c2d9`: `Delete (DeleteInstance)`
- `0x18004c5b9`: `Delete (DeleteInstance)`
- `0x18004ccdc`: `Delete (DeleteInstance)`
- `0x18004d11f`: `Delete (DeleteInstance)`
- `0x18004ced7`: `SECURITY`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall CWbemNamespace::DeleteSingleInstance(
        CWbemNamespace *this,
        unsigned __int16 *a2,
        unsigned int a3,
        struct IWbemContext *a4,
        struct CBasicObjectSink *a5)
{
  struct IWbemContext *v5; // rsi
  unsigned int v6; // ebx
  int v9; // eax
  struct IWbemClassObject *v10; // r13
  const unsigned __int16 *v11; // r8
  int ObjectByPath; // eax
  struct IWbemClassObject *v13; // rsi
  struct CWbemObject *v14; // r14
  int v15; // ebx
  struct CNtSecurityDescriptor *v16; // rdx
  int v17; // eax
  __int64 v18; // rbx
  int v19; // eax
  int ObjectW; // eax
  void *v21; // r8
  _QWORD *v22; // r14
  int v23; // eax
  struct IWbemClassObject *v24; // rdi
  int IsLocalMachine; // eax
  int v26; // r15d
  CObjectSink *v27; // r14
  HRESULT v28; // eax
  struct IErrorInfo *v29; // rdx
  CObjectSink *v30; // rcx
  int First_ms_XXX_Locale; // ebx
  __int64 v33; // rdi
  __int64 (__fastcall *v34)(__int64, struct IWbemClassObject **, _QWORD, struct IWbemContext *, _QWORD, _QWORD, void *, _QWORD, __int64, GUID *, struct IWbemClassObject **); // rbx
  __int64 v35; // rax
  int v36; // ebx
  struct IWbemClassObject *v37; // rbx
  OLECHAR *v38; // rdi
  CObjectSink *v39; // r15
  CMemoryLog *v40; // rax
  CClientCnt *v41; // rcx
  __int64 v42; // rdx
  CObjectSink *v43; // rbx
  CMemoryLog *v44; // rax
  unsigned int v45; // r15d
  CObjectSink *v46; // rbx
  CMemoryLog *v47; // rax
  CClientCnt *v48; // rcx
  unsigned int v49; // ebx
  CMemoryLog *v50; // rax
  CMemoryLog *v51; // rax
  __int64 v52; // r9
  unsigned int v53; // edi
  int v54; // edx
  CMemoryLog *v55; // rax
  CMemoryLog *MemLogObject; // rax
  int AccessToken; // eax
  CMemoryLog *v58; // rax
  unsigned int v59; // edx
  int v60; // eax
  CMemoryLog *v61; // rax
  CMemoryLog *v62; // rax
  int v63; // edx
  struct IWbemClassObject *QueryInterface; // rdi
  int v65; // edx
  const unsigned __int16 *lpVtbl; // rbx
  int v67; // eax
  int v68; // edx
  int v69; // eax
  OLECHAR *v70; // r8
  int v71; // ebx
  unsigned __int64 v72; // rdi
  unsigned __int16 *v73; // rsi
  unsigned int v74; // r14d
  unsigned __int16 *v75; // rax
  const unsigned __int16 *v76; // rax
  int v77; // ebx
  int v78; // edx
  unsigned __int16 *v79; // [rsp+28h] [rbp-E0h]
  bool v80; // [rsp+30h] [rbp-D8h]
  bool v81; // [rsp+30h] [rbp-D8h]
  struct IWbemClassObject **v82; // [rsp+30h] [rbp-D8h]
  struct IWbemClassObject *v83; // [rsp+68h] [rbp-A0h] BYREF
  struct IWbemClassObject *v84; // [rsp+70h] [rbp-98h] BYREF
  __int64 v85; // [rsp+78h] [rbp-90h] BYREF
  char v86[8]; // [rsp+80h] [rbp-88h] BYREF
  CObjectSink *v87; // [rsp+88h] [rbp-80h]
  bool v88; // [rsp+90h] [rbp-78h] BYREF
  __int64 v89; // [rsp+98h] [rbp-70h] BYREF
  __int64 v90; // [rsp+A0h] [rbp-68h] BYREF
  void *v91; // [rsp+A8h] [rbp-60h] BYREF
  void **v92; // [rsp+B0h] [rbp-58h]
  HANDLE hObject; // [rsp+B8h] [rbp-50h] BYREF
  struct IWbemClassObject *v94; // [rsp+C0h] [rbp-48h] BYREF
  struct IWbemClassObject *v95[2]; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE v96[40]; // [rsp+D8h] [rbp-30h] BYREF
  void *v97; // [rsp+100h] [rbp-8h] BYREF
  _BYTE v98[32]; // [rsp+108h] [rbp+0h] BYREF
  __int64 v99; // [rsp+128h] [rbp+20h] BYREF
  struct IWbemClassObject *v100; // [rsp+130h] [rbp+28h] BYREF
  OLECHAR *v101; // [rsp+138h] [rbp+30h] BYREF
  struct IWbemClassObject *v102; // [rsp+140h] [rbp+38h] BYREF
  __int64 v103; // [rsp+148h] [rbp+40h] BYREF
  int v104; // [rsp+150h] [rbp+48h]
  __int64 v105; // [rsp+158h] [rbp+50h]
  __int128 v106; // [rsp+160h] [rbp+58h]
  int v107; // [rsp+170h] [rbp+68h]
  _BYTE v108[40]; // [rsp+178h] [rbp+70h] BYREF
  char v109[8]; // [rsp+1A0h] [rbp+98h] BYREF
  void (__fastcall *v110)(__int64); // [rsp+1A8h] [rbp+A0h]
  __int64 v111; // [rsp+1B0h] [rbp+A8h]
  VARIANTARG pvarg; // [rsp+1B8h] [rbp+B0h] BYREF
  VARIANTARG v113; // [rsp+1D0h] [rbp+C8h] BYREF
  _BYTE v114[40]; // [rsp+1E8h] [rbp+E0h] BYREF
  __int64 *v115; // [rsp+210h] [rbp+108h]
  struct IWbemClassObject *v116; // [rsp+218h] [rbp+110h]

  v5 = a4;
  v6 = a3;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 212, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, a2);
  }
  COperationError::COperationError((COperationError *)v86, a5, L"DeleteInstance", a2, 1);
  if ( v86[0] )
  {
    v95[0] = 0;
    v107 = 1;
    v104 = 0;
    v105 = 0;
    v103 = 0;
    v106 = 0;
    v9 = CObjectPathParser::Parse((CObjectPathParser *)&v103, a2, (struct ParsedObjectPath **)v95);
    v115 = &v103;
    v10 = v95[0];
    v116 = v95[0];
    if ( v9 || !(unsigned int)ParsedObjectPath::IsInstance((ParsedObjectPath *)v95[0]) )
    {
      v78 = -2147217350;
    }
    else
    {
      if ( (unsigned int)wbem_wcsicmp((const unsigned __int16 *)v10[3].lpVtbl, L"__CIMOMIdentification")
        && (unsigned int)wbem_wcsicmp((const unsigned __int16 *)v10[3].lpVtbl, L"__SystemSecurity")
        && (unsigned int)wbem_wcsicmp((const unsigned __int16 *)v10[3].lpVtbl, L"__ADAPStatus")
        && (unsigned int)wbem_wcsicmp((const unsigned __int16 *)v10[3].lpVtbl, L"__thisnamespace") )
      {
        WString2::WString2((WString2 *)v96);
        if ( (unsigned int)wbem_wcsicmp((const unsigned __int16 *)v10[3].lpVtbl, L"__NAMESPACE")
          && (unsigned int)CRepository::InheritsFrom(
                             *((struct IWmiDbSession **)this + 5),
                             *((struct IWmiDbHandle **)this + 8),
                             v11,
                             (const unsigned __int16 *)v10[3].lpVtbl) )
        {
          v95[0] = 0;
          v94 = 0;
          ObjectByPath = CWbemNamespace::Exec_GetObjectByPath(
                           this,
                           (const unsigned __int16 *)v10[3].lpVtbl,
                           0,
                           v5,
                           &v94,
                           v95);
          v13 = v95[0];
          v83 = v95[0];
          v14 = (struct CWbemObject *)v94;
          v84 = v94;
          if ( ObjectByPath == -2147217406 )
          {
            ObjectByPath = -2147217392;
          }
          else if ( ObjectByPath >= 0 )
          {
            CVar::CVar((CVar *)v98);
            if ( (*(int (__fastcall **)(struct CWbemObject *, const wchar_t *, _BYTE *, _QWORD))(*(_QWORD *)v14 + 976LL))(
                   v14,
                   L"Dynamic",
                   v98,
                   0) >= 0
              && CVar::GetType((CVar *)v98) == 11
              && CVar::GetBool((CVar *)v98) )
            {
              CVar::CVar((CVar *)v108);
              if ( (*(int (__fastcall **)(struct CWbemObject *, const wchar_t *, _BYTE *, _QWORD, _QWORD))(*(_QWORD *)v14 + 976LL))(
                     v14,
                     L"Provider",
                     v108,
                     0,
                     0) >= 0
                && CVar::GetType((CVar *)v108) == 8 )
              {
                if ( !CWbemNamespace::InnerAllowedWithSD(
                        this,
                        (CWbemNamespace *)((char *)this + 216),
                        0x10u,
                        L"Delete (DeleteInstance)",
                        a2,
                        v81,
                        1) )
                {
                  v54 = -2147217405;
                  goto LABEL_162;
                }
                v94 = 0;
                if ( *((_QWORD *)this + 31) )
                {
                  v91 = 0;
                  First_ms_XXX_Locale = CMUILocaleList::GetFirst_ms_XXX_Locale(
                                          (CWbemNamespace *)((char *)this + 176),
                                          (unsigned __int16 **)&v91);
                  if ( First_ms_XXX_Locale >= 0 )
                  {
                    MakeGuard<int (*)(void *),unsigned short *>(v109, CMUILocale::_Free, v91);
                    v33 = *((_QWORD *)this + 31);
                    v34 = *(__int64 (__fastcall **)(__int64, struct IWbemClassObject **, _QWORD, struct IWbemContext *, _QWORD, _QWORD, void *, _QWORD, __int64, GUID *, struct IWbemClassObject **))(*(_QWORD *)v33 + 40LL);
                    v35 = CVar::operator unsigned short *(v108);
                    *(_OWORD *)v95 = 0;
                    v36 = v34(v33, v95, 0, a4, 0, *((_QWORD *)this + 14), v91, 0, v35, &IID_IWbemServices, &v94);
                    if ( v36 >= 0 )
                    {
                      v37 = v94;
                      v95[0] = v94;
                      v38 = SysAllocString(a2);
                      v101 = v38;
                      v39 = v87;
                      ((void (__fastcall *)(struct IWbemClassObject *, OLECHAR *, _QWORD, struct IWbemContext *, CObjectSink *))v94->lpVtbl->GetPropertyOrigin)(
                        v94,
                        v38,
                        a3,
                        a4,
                        v87);
                      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          217,
                          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                          0);
                      }
                      if ( v38 )
                        SysFreeString(v38);
                      if ( v37 )
                        ((void (__fastcall *)(struct IWbemClassObject *))v37->lpVtbl->Release)(v37);
                      v95[0] = 0;
                      if ( !v109[0] )
                        v110(v111);
                      CVar::~CVar((CVar *)v108);
                      CVar::~CVar((CVar *)v98);
                      if ( v14 )
                        (*(void (__fastcall **)(struct CWbemObject *))(*(_QWORD *)v14 + 16LL))(v14);
                      v84 = 0;
                      if ( v13 )
                        ((void (__fastcall *)(struct IWbemClassObject *))v13->lpVtbl->Release)(v13);
                      v83 = 0;
                      WString2::~WString2((WString2 *)v96);
                      CObjectPathParser::Free((CObjectPathParser *)&v103, (struct ParsedObjectPath *)v10);
                      CObjectPathParser::Empty((CObjectPathParser *)&v103);
                      if ( !v39 )
                        return 0;
                      v30 = v39;
LABEL_52:
                      CObjectSink::Release(v30);
                      return 0;
                    }
                    MemLogObject = GetMemLogObject();
                    CMemoryLog::Write(MemLogObject, v36);
                    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        216,
                        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                        (unsigned int)v36);
                    }
                    v49 = COperationError::ErrorOccurred((COperationError *)v86, v36, 0);
                    ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>::~ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>((__int64)v109);
                    goto LABEL_164;
                  }
                  v55 = GetMemLogObject();
                  CMemoryLog::Write(v55, First_ms_XXX_Locale);
                  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      215,
                      WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                      (unsigned int)First_ms_XXX_Locale);
                  }
                  v54 = First_ms_XXX_Locale;
LABEL_162:
                  v49 = COperationError::ErrorOccurred((COperationError *)v86, v54, 0);
LABEL_164:
                  CVar::~CVar((CVar *)v108);
                  goto LABEL_141;
                }
                v45 = -2147217398;
                v46 = v87;
                if ( v87 )
                  COperationErrorSink::SetStatus(v87, 0, -2147217398, 0, 0);
                v51 = GetMemLogObject();
                CMemoryLog::Write(v51, -2147217398);
                v48 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_100;
                }
                v52 = 2147749898LL;
              }
              else
              {
                v45 = -2147217390;
                v46 = v87;
                if ( v87 )
                  COperationErrorSink::SetStatus(v87, 0, -2147217390, 0, 0);
                v47 = GetMemLogObject();
                CMemoryLog::Write(v47, -2147217390);
                v48 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_100;
                }
                v52 = 2147749906LL;
              }
              WPP_SF_d(*((_QWORD *)v48 + 2), 107, WPP_ffbbabd785873c07a1ea9257e814c720_Traceguids, v52);
LABEL_100:
              CVar::~CVar((CVar *)v108);
              CVar::~CVar((CVar *)v98);
              if ( v14 )
                (*(void (__fastcall **)(struct CWbemObject *))(*(_QWORD *)v14 + 16LL))(v14);
              v84 = 0;
              if ( v13 )
                ((void (__fastcall *)(struct IWbemClassObject *))v13->lpVtbl->Release)(v13);
              v83 = 0;
              WString2::~WString2((WString2 *)v96);
              CObjectPathParser::Free((CObjectPathParser *)&v103, (struct ParsedObjectPath *)v10);
              CObjectPathParser::Empty((CObjectPathParser *)&v103);
              if ( v46 )
                CObjectSink::Release(v46);
              return v45;
            }
            if ( (*(unsigned int (__fastcall **)(struct CWbemObject *, const wchar_t *))(*(_QWORD *)v14 + 144LL))(
                   v14,
                   L"__Provider")
              && (*(unsigned int (__fastcall **)(struct CWbemObject *, const wchar_t *))(*(_QWORD *)v14 + 144LL))(
                   v14,
                   L"__ProviderRegistration") )
            {
LABEL_16:
              v88 = 0;
              v15 = IsDerivedFromSystem(v14, &v88);
              if ( v15 < 0 )
              {
                v61 = GetMemLogObject();
                CMemoryLog::Write(v61, v15);
                if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    219,
                    WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                    (unsigned int)v15);
                }
                v49 = CBasicObjectSink::Return(a5, v15, 0);
                CVar::~CVar((CVar *)v98);
                if ( v14 )
                  (*(void (__fastcall **)(struct CWbemObject *))(*(_QWORD *)v14 + 16LL))(v14);
                v84 = 0;
                if ( v13 )
                  ((void (__fastcall *)(struct IWbemClassObject *))v13->lpVtbl->Release)(v13);
                v83 = 0;
                goto LABEL_115;
              }
              v16 = (CWbemNamespace *)((char *)this + 216);
              if ( v88 )
              {
                if ( CWbemNamespace::InnerAllowedWithSD(this, v16, 4u, L"Delete (DeleteInstance)", a2, v81, 1) )
                {
LABEL_19:
                  if ( v14 )
                    (*(void (__fastcall **)(struct CWbemObject *))(*(_QWORD *)v14 + 16LL))(v14);
                  v84 = 0;
                  v99 = 0;
                  v17 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 32) + 224LL))(
                          *((_QWORD *)this + 32),
                          &v99);
                  if ( v17 >= 0 )
                  {
                    v18 = v99;
                    v89 = v99;
                    v97 = 0;
                    v85 = 0;
                    v94 = (struct IWbemClassObject *)&v85;
                    v91 = 0;
                    v92 = &v97;
                    if ( !v99 )
                    {
                      v22 = (_QWORD *)((char *)this + 96);
                      v24 = 0;
                      v102 = 0;
                      goto LABEL_32;
                    }
                    v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**((_QWORD **)this + 32) + 184LL))(
                            *((_QWORD *)this + 32),
                            0,
                            &v85);
                    if ( v19 >= 0 )
                    {
                      ObjectW = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int16 *))(*(_QWORD *)v85 + 24LL))(
                                  v85,
                                  4,
                                  a2);
                      if ( ObjectW < 0 )
                      {
LABEL_128:
                        v53 = COperationError::ErrorOccurred((COperationError *)v86, ObjectW, 0);
                        CWin32DefaultArena::WbemMemFree(v97);
                        if ( v85 )
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
                        v85 = 0;
                        if ( v18 )
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
                        v89 = 0;
                        CVar::~CVar((CVar *)v98);
                        v84 = 0;
                        if ( v13 )
                          ((void (__fastcall *)(struct IWbemClassObject *))v13->lpVtbl->Release)(v13);
                        v83 = 0;
                        WString2::~WString2((WString2 *)v96);
                        CObjectPathParser::Free((CObjectPathParser *)&v103, (struct ParsedObjectPath *)v10);
                        CObjectPathParser::Empty((CObjectPathParser *)&v103);
                        if ( v87 )
                          CObjectSink::Release(v87);
                        return v53;
                      }
                      LODWORD(v90) = 0;
                      v19 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v85 + 168LL))(
                              v85,
                              &v90,
                              0);
                      if ( v19 >= 0 )
                      {
                        v21 = CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)(v90 + 1), 2u));
                        v97 = v21;
                        if ( !v21 )
                        {
                          v63 = -2147217402;
                          goto LABEL_137;
                        }
                        v19 = (*(__int64 (__fastcall **)(__int64, __int64 *, void *))(*(_QWORD *)v85 + 168LL))(
                                v85,
                                &v90,
                                v21);
                        if ( v19 >= 0 )
                        {
                          v22 = (_QWORD *)((char *)this + 96);
                          v23 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, struct IWbemContext *, __int64, _QWORD, void *))(*(_QWORD *)v99 + 40LL))(
                                  v99,
                                  2,
                                  a3,
                                  a4,
                                  v85,
                                  *((_QWORD *)this + 12),
                                  v97);
                          if ( v23 >= 0 )
                          {
                            v24 = 0;
                            v102 = 0;
                            if ( v23 != 262165 )
                            {
LABEL_32:
                              v95[0] = v24;
                              VariantInit(&pvarg);
                              if ( ((int (__fastcall *)(struct IWbemContext *, const wchar_t *, _QWORD, VARIANTARG *))a4->lpVtbl->GetValue)(
                                     a4,
                                     L"__GroupOperationId",
                                     0,
                                     &pvarg) >= 0 )
                              {
                                IsLocalMachine = CWbemNamespace::IsLocalMachine(*((wchar_t **)this + 35));
                                CPublishWMIOperationEvent::PublishRepDelete(
                                  pvarg.cyVal.Lo,
                                  a2,
                                  a4,
                                  *((_DWORD *)this + 76),
                                  *((unsigned __int16 **)this + 36),
                                  *((_QWORD *)this + 37),
                                  IsLocalMachine);
                              }
                              v26 = CRepository::DeleteByPath(
                                      *((struct IWmiDbSession **)this + 5),
                                      *((struct IWmiDbHandle **)this + 8),
                                      a2,
                                      0);
                              if ( v99 )
                                (*(void (__fastcall **)(__int64, __int64, _QWORD, struct IWbemContext *, __int64, _QWORD, void *, struct IWbemClassObject *))(*(_QWORD *)v99 + 48LL))(
                                  v99,
                                  2,
                                  (unsigned int)v26,
                                  a4,
                                  v85,
                                  *v22,
                                  v97,
                                  v102);
                              if ( v26 >= 0 )
                              {
                                v27 = v87;
                                if ( v87 )
                                  COperationErrorSink::SetStatus(v87, 0, 0, 0, 0);
                                if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                {
                                  WPP_SF_d(
                                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                                    107,
                                    WPP_ffbbabd785873c07a1ea9257e814c720_Traceguids,
                                    0);
                                }
                                v28 = VariantClear(&pvarg);
                                if ( v28 < 0 )
                                  _com_issue_error(v28, v29);
                                if ( v24 )
                                  ((void (__fastcall *)(struct IWbemClassObject *))v24->lpVtbl->Release)(v24);
                                v95[0] = 0;
                                CWin32DefaultArena::WbemMemFree(v97);
                                if ( v85 )
                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
                                v85 = 0;
                                if ( v18 )
                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
                                v89 = 0;
                                CVar::~CVar((CVar *)v98);
                                v84 = 0;
                                if ( v13 )
                                  ((void (__fastcall *)(struct IWbemClassObject *))v13->lpVtbl->Release)(v13);
                                v83 = 0;
                                WString2::~WString2((WString2 *)v96);
                                CObjectPathParser::Free((CObjectPathParser *)&v103, (struct ParsedObjectPath *)v10);
                                CObjectPathParser::Empty((CObjectPathParser *)&v103);
                                if ( !v27 )
                                  return 0;
                                v30 = v27;
                                goto LABEL_52;
                              }
                              v49 = COperationError::ErrorOccurred((COperationError *)v86, v26, 0);
                              _variant_t::~_variant_t(&pvarg);
                              CReleaseMe::release((CReleaseMe *)v95);
                              CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(&v91);
                              if ( v85 )
                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
                              v85 = 0;
                              goto LABEL_140;
                            }
                            ObjectW = CRepository::GetObjectW(
                                        *((struct IWmiDbSession **)this + 5),
                                        *((struct IWmiDbHandle **)this + 8),
                                        a2,
                                        0,
                                        &v102);
                            if ( ObjectW >= 0 )
                            {
                              v24 = v102;
                              goto LABEL_32;
                            }
                            goto LABEL_128;
                          }
                          v49 = COperationError::ErrorOccurred((COperationError *)v86, v23, 0);
                          CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(&v91);
                          if ( v85 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
                          v85 = 0;
LABEL_140:
                          CReleaseMe::release((CReleaseMe *)&v89);
LABEL_141:
                          CVar::~CVar((CVar *)v98);
                          CReleaseMe::release((CReleaseMe *)&v84);
LABEL_142:
                          CReleaseMe::release((CReleaseMe *)&v83);
LABEL_143:
                          WString2::~WString2((WString2 *)v96);
LABEL_144:
                          CObjectPathParser::Free((CObjectPathParser *)&v103, (struct ParsedObjectPath *)v10);
                          CObjectPathParser::Empty((CObjectPathParser *)&v103);
                          COperationError::~COperationError((COperationError *)v86);
                          return v49;
                        }
                      }
                    }
                    v63 = v19;
LABEL_137:
                    v49 = COperationError::ErrorOccurred((COperationError *)v86, v63, 0);
                    CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(&v91);
                    if ( v85 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
                    v85 = 0;
                    goto LABEL_140;
                  }
                  v49 = COperationError::ErrorOccurred((COperationError *)v86, v17, 0);
                  CVar::~CVar((CVar *)v98);
                  v84 = 0;
                  if ( v13 )
                    ((void (__fastcall *)(struct IWbemClassObject *))v13->lpVtbl->Release)(v13);
                  v83 = 0;
LABEL_115:
                  WString2::~WString2((WString2 *)v96);
                  CObjectPathParser::Free((CObjectPathParser *)&v103, (struct ParsedObjectPath *)v10);
                  CObjectPathParser::Empty((CObjectPathParser *)&v103);
                  if ( v87 )
                    CObjectSink::Release(v87);
                  return v49;
                }
                v62 = GetMemLogObject();
                CMemoryLog::Write(v62, -2147217405);
                v41 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_186;
                }
                v42 = 220;
              }
              else
              {
                if ( CWbemNamespace::InnerAllowedWithSD(this, v16, 8u, L"Delete (DeleteInstance)", a2, v81, 1) )
                  goto LABEL_19;
                v40 = GetMemLogObject();
                CMemoryLog::Write(v40, -2147217405);
                v41 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_186;
                }
                v42 = 221;
              }
              WPP_SF_d(*((_QWORD *)v41 + 2), v42, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749891LL);
LABEL_186:
              v60 = CBasicObjectSink::Return(a5, -2147217405, 0);
              goto LABEL_187;
            }
            hObject = 0;
            AccessToken = GetAccessToken(&hObject);
            if ( AccessToken >= 0 )
            {
              if ( IsAdmin(hObject) )
              {
                CloseHandle(hObject);
                goto LABEL_16;
              }
              CloseHandle(hObject);
              CWbemNamespace::CheckAllowedOnAlternateSD(this, v59, L"Delete (DeleteInstance)", a2, 0);
            }
            else
            {
              if ( AccessToken == -2147417833 || AccessToken == -2147217401 )
                goto LABEL_16;
              v58 = GetMemLogObject();
              CMemoryLog::Write(v58, -1);
              if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 218, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids);
              }
            }
            v60 = COperationError::ErrorOccurred((COperationError *)v86, -2147217405, 0);
LABEL_187:
            v49 = v60;
            goto LABEL_141;
          }
          COperationError::ErrorOccurred((COperationError *)v86, ObjectByPath, v95[0]);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 214, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 0);
          }
          CReleaseMe::release((CReleaseMe *)&v84);
          CReleaseMe::release((CReleaseMe *)&v83);
          WString2::~WString2((WString2 *)v96);
          v49 = 0;
          goto LABEL_144;
        }
        if ( !CWbemNamespace::InnerAllowedWithSD(
                this,
                (CWbemNamespace *)((char *)this + 216),
                4u,
                L"Delete (DeleteInstance)",
                a2,
                v80,
                1) )
        {
          v43 = v87;
          if ( v87 )
            COperationErrorSink::SetStatus(v87, 0, -2147217405, 0, 0);
          v44 = GetMemLogObject();
          CMemoryLog::Write(v44, -2147217405);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              107,
              WPP_ffbbabd785873c07a1ea9257e814c720_Traceguids,
              2147749891LL);
          }
          WString2::~WString2((WString2 *)v96);
          CObjectPathParser::Free((CObjectPathParser *)&v103, (struct ParsedObjectPath *)v10);
          CObjectPathParser::Empty((CObjectPathParser *)&v103);
          if ( v43 )
            CObjectSink::Release(v43);
          return 2147749891LL;
        }
        if ( LODWORD(v10[4].lpVtbl) != 1 )
          goto LABEL_207;
        QueryInterface = (struct IWbemClassObject *)v10[5].lpVtbl->QueryInterface;
        v94 = QueryInterface;
        if ( QueryInterface->lpVtbl )
        {
          if ( (unsigned int)wbem_wcsicmp((const unsigned __int16 *)QueryInterface->lpVtbl, L"name") )
            goto LABEL_207;
        }
        if ( LOWORD(QueryInterface[1].lpVtbl) != 8 )
          goto LABEL_207;
        if ( (unsigned int)wbem_wcsicmp(*((const unsigned __int16 **)this + 12), L"ROOT") )
          goto LABEL_216;
        lpVtbl = (const unsigned __int16 *)QueryInterface[2].lpVtbl;
        if ( lpVtbl )
        {
          if ( (unsigned int)wbem_wcsicmp((const unsigned __int16 *)QueryInterface[2].lpVtbl, L"SECURITY")
            && (unsigned int)wbem_wcsicmp(lpVtbl, L"DEFAULT") )
          {
            v6 = a3;
LABEL_216:
            v100 = 0;
            (*(void (__fastcall **)(_QWORD, struct IWbemClassObject **))(**((_QWORD **)this + 32) + 224LL))(
              *((_QWORD *)this + 32),
              &v100);
            v83 = v100;
            v101 = 0;
            v89 = 0;
            v91 = 0;
            v92 = (void **)&v101;
            if ( v100 )
            {
              v67 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**((_QWORD **)this + 32) + 184LL))(
                      *((_QWORD *)this + 32),
                      0,
                      &v89);
              if ( v67 < 0 )
              {
                v49 = COperationError::ErrorOccurred((COperationError *)v86, v67, 0);
LABEL_222:
                CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(&v91);
                goto LABEL_142;
              }
              v90 = v89;
              v69 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int16 *))(*(_QWORD *)v89 + 24LL))(
                      v89,
                      4,
                      a2);
              if ( v69 < 0 )
                goto LABEL_219;
              LODWORD(v84) = 0;
              v69 = (*(__int64 (__fastcall **)(__int64, struct IWbemClassObject **))(*(_QWORD *)v89 + 168LL))(v89, &v84);
              if ( v69 < 0 )
                goto LABEL_219;
              v70 = (OLECHAR *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)((_DWORD)v84 + 1), 2u));
              v101 = v70;
              if ( !v70 )
              {
                v68 = -2147217402;
                goto LABEL_220;
              }
              v69 = (*(__int64 (__fastcall **)(__int64, struct IWbemClassObject **, OLECHAR *))(*(_QWORD *)v89 + 168LL))(
                      v89,
                      &v84,
                      v70);
              if ( v69 < 0
                || (v82 = (struct IWbemClassObject **)*((_QWORD *)this + 12),
                    v69 = ((__int64 (__fastcall *)(struct IWbemClassObject *, __int64, _QWORD, struct IWbemContext *, __int64))v100->lpVtbl->Put)(
                            v100,
                            2,
                            v6,
                            v5,
                            v89),
                    v69 < 0) )
              {
LABEL_219:
                v68 = v69;
LABEL_220:
                v49 = COperationError::ErrorOccurred((COperationError *)v86, v68, 0);
LABEL_221:
                CReleaseMe::release((CReleaseMe *)&v90);
                goto LABEL_222;
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 8LL))(v89);
              CReleaseMe::release((CReleaseMe *)&v90);
            }
            v90 = v89;
            v95[0] = 0;
            v68 = CRepository::GetObjectW(
                    *((struct IWmiDbSession **)this + 5),
                    *((struct IWmiDbHandle **)this + 8),
                    a2,
                    0,
                    v95);
            if ( v68 < 0 )
              goto LABEL_220;
            hObject = v95[0];
            if ( !v68 )
            {
              if ( CWbemNamespace::InnerAllowedWithSD(
                     this,
                     (CWbemNamespace *)((char *)this + 216),
                     4u,
                     L"Delete (DeleteInstance)",
                     a2,
                     (bool)v82,
                     1) )
              {
                WString2::WString2((WString2 *)v114, L"__Namespace='");
                WString2::operator+=(v114, QueryInterface[2].lpVtbl);
                WString2::operator+=(v114, L"'");
                VariantInit(&v113);
                if ( ((int (__fastcall *)(struct IWbemContext *, const wchar_t *, _QWORD, VARIANTARG *))v5->lpVtbl->GetValue)(
                       v5,
                       L"__GroupOperationId",
                       0,
                       &v113) >= 0 )
                {
                  v71 = CWbemNamespace::IsLocalMachine(*((wchar_t **)this + 35));
                  v72 = *((_QWORD *)this + 37);
                  v73 = (unsigned __int16 *)*((_QWORD *)this + 36);
                  v74 = *((_DWORD *)this + 76);
                  v75 = (unsigned __int16 *)WString2::operator unsigned short *(v114);
                  v79 = v73;
                  v5 = a4;
                  CPublishWMIOperationEvent::PublishRepDelete(v113.cyVal.Lo, v75, a4, v74, v79, v72, v71);
                  QueryInterface = v94;
                }
                v76 = (const unsigned __int16 *)WString2::operator unsigned short *(v114);
                v77 = CRepository::DeleteByPath(
                        *((struct IWmiDbSession **)this + 5),
                        *((struct IWmiDbHandle **)this + 8),
                        v76,
                        0);
                if ( v100 )
                  ((void (__fastcall *)(struct IWbemClassObject *, __int64, _QWORD, struct IWbemContext *, __int64, _QWORD, OLECHAR *, struct IWbemClassObject *))v100->lpVtbl->Delete)(
                    v100,
                    2,
                    (unsigned int)v77,
                    v5,
                    v89,
                    *((_QWORD *)this + 12),
                    v101,
                    v95[0]);
                if ( v77 < 0 )
                {
                  v49 = COperationError::ErrorOccurred((COperationError *)v86, v77, 0);
                  _variant_t::~_variant_t(&v113);
                  WString2::~WString2((WString2 *)v114);
                  goto LABEL_234;
                }
                _variant_t::~_variant_t(&v113);
                WString2::~WString2((WString2 *)v114);
                WString2::operator=(v96, QueryInterface[2].lpVtbl);
                v68 = 0;
              }
              else
              {
                v68 = -2147217405;
              }
            }
            v49 = COperationError::ErrorOccurred((COperationError *)v86, v68, 0);
LABEL_234:
            CReleaseMe::release((CReleaseMe *)&hObject);
            goto LABEL_221;
          }
          v65 = -2147217405;
        }
        else
        {
LABEL_207:
          v65 = -2147217350;
        }
        v49 = COperationError::ErrorOccurred((COperationError *)v86, v65, 0);
        goto LABEL_143;
      }
      v78 = -2147217386;
    }
    v49 = COperationError::ErrorOccurred((COperationError *)v86, v78, 0);
    goto LABEL_144;
  }
  v50 = GetMemLogObject();
  CMemoryLog::Write(v50, -2147217402);
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 213, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749894LL);
  }
  if ( v87 )
    CObjectSink::Release(v87);
  return 2147749894LL;
}

```

## disassembly

```asm
0x18004bc18  mov     rax, rsp
0x18004bc1b  mov     [rax+8], rbx
0x18004bc1f  mov     [rax+20h], r9
0x18004bc23  mov     [rax+18h], r8d
0x18004bc27  push    rbp
0x18004bc28  push    rsi
0x18004bc29  push    rdi
0x18004bc2a  push    r12
0x18004bc2c  push    r13
0x18004bc2e  push    r14
0x18004bc30  push    r15
0x18004bc32  lea     rbp, [rax-168h]
0x18004bc39  sub     rsp, 230h
0x18004bc40  movaps  xmmword ptr [rax-48h], xmm6
0x18004bc44  mov     rsi, r9
0x18004bc47  mov     ebx, r8d
0x18004bc4a  mov     r12, rdx
0x18004bc4d  mov     r15, rcx
0x18004bc50  xor     edi, edi
0x18004bc52  lea     r13, WPP_GLOBAL_Control
0x18004bc59  lea     r14d, [rdi+1]
0x18004bc5d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bc64  cmp     rcx, r13
0x18004bc67  jnz     loc_18004C4DB
0x18004bc6d  mov     dword ptr [rsp+260h+var_240], r14d; int
0x18004bc72  mov     r9, r12; unsigned __int16 *
0x18004bc75  lea     r8, aDeleteinstance; "DeleteInstance"
0x18004bc7c  mov     rdx, [rbp+160h+arg_20]; struct CBasicObjectSink *
0x18004bc83  lea     rcx, [rsp+260h+var_1E8]; this
0x18004bc88  call    ??0COperationError@@QEAA@PEAVCBasicObjectSink@@PEBG1H@Z; COperationError::COperationError(CBasicObjectSink *,ushort const *,ushort const *,int)
0x18004bc8d  nop
0x18004bc8e  cmp     [rsp+260h+var_1E8], dil
0x18004bc93  jz      loc_18004C801
0x18004bc99  mov     [rbp+160h+var_1A0], rdi
0x18004bc9d  mov     [rbp+160h+var_F8], r14d
0x18004bca1  mov     [rbp+160h+var_118], edi
0x18004bca4  mov     [rbp+160h+var_110], rdi
0x18004bca8  mov     [rbp+160h+var_120], rdi
0x18004bcac  xorps   xmm0, xmm0
0x18004bcaf  movdqu  [rbp+160h+var_108], xmm0
0x18004bcb4  lea     r8, [rbp+160h+var_1A0]; struct ParsedObjectPath **
0x18004bcb8  mov     rdx, r12; unsigned __int16 *
0x18004bcbb  lea     rcx, [rbp+160h+var_120]; this
0x18004bcbf  call    ?Parse@CObjectPathParser@@QEAAHPEBGPEAPEAUParsedObjectPath@@@Z; CObjectPathParser::Parse(ushort const *,ParsedObjectPath * *)
0x18004bcc4  lea     rcx, [rbp+160h+var_120]
0x18004bcc8  mov     [rbp+160h+var_58], rcx
0x18004bccf  mov     r13, [rbp+160h+var_1A0]
0x18004bcd3  mov     [rbp+160h+var_50], r13
0x18004bcda  test    eax, eax
0x18004bcdc  jnz     loc_18004D2D6
0x18004bce2  mov     rcx, r13; this
0x18004bce5  call    ?IsInstance@ParsedObjectPath@@QEAAHXZ; ParsedObjectPath::IsInstance(void)
0x18004bcea  test    eax, eax
0x18004bcec  jz      loc_18004D2D6
0x18004bcf2  lea     rdx, aCimomidentific_0; "__CIMOMIdentification"
0x18004bcf9  mov     rcx, [r13+18h]; unsigned __int16 *
0x18004bcfd  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x18004bd02  test    eax, eax
0x18004bd04  jz      loc_18004D2CF
0x18004bd0a  lea     rdx, aSystemsecurity_0; "__SystemSecurity"
0x18004bd11  mov     rcx, [r13+18h]; unsigned __int16 *
0x18004bd15  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x18004bd1a  test    eax, eax
0x18004bd1c  jz      loc_18004D2CF
0x18004bd22  lea     rdx, aAdapstatus_0; "__ADAPStatus"
0x18004bd29  mov     rcx, [r13+18h]; unsigned __int16 *
0x18004bd2d  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x18004bd32  test    eax, eax
0x18004bd34  jz      loc_18004D2CF
0x18004bd3a  lea     rdx, aThisnamespace; "__thisnamespace"
0x18004bd41  mov     rcx, [r13+18h]; unsigned __int16 *
0x18004bd45  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x18004bd4a  test    eax, eax
0x18004bd4c  jz      loc_18004D2CF
0x18004bd52  lea     rcx, [rbp+160h+var_190]
0x18004bd56  call    cs:__imp_??0WString2@@QEAA@XZ; WString2::WString2(void)
0x18004bd5c  nop
0x18004bd5d  lea     rdx, aNamespace_1; "__NAMESPACE"
0x18004bd64  mov     rcx, [r13+18h]; unsigned __int16 *
0x18004bd68  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x18004bd6d  test    eax, eax
0x18004bd6f  jz      loc_18004C5A8
0x18004bd75  mov     r9, [r13+18h]; unsigned __int16 *
0x18004bd79  mov     rdx, [r15+40h]; struct IWmiDbHandle *
0x18004bd7d  mov     rcx, [r15+28h]; struct IWmiDbSession *
0x18004bd81  call    ?InheritsFrom@CRepository@@SAJPEAUIWmiDbSession@@PEAUIWmiDbHandle@@PEBG2@Z; CRepository::InheritsFrom(IWmiDbSession *,IWmiDbHandle *,ushort const *,ushort const *)
0x18004bd86  test    eax, eax
0x18004bd88  jz      loc_18004C5A8
0x18004bd8e  mov     [rbp+160h+var_1A0], rdi
0x18004bd92  mov     [rbp+160h+var_1A8], rdi
0x18004bd96  lea     rax, [rbp+160h+var_1A0]
0x18004bd9a  mov     [rsp+260h+var_238], rax; bool
0x18004bd9f  lea     rax, [rbp+160h+var_1A8]
0x18004bda3  mov     [rsp+260h+var_240], rax; struct IWbemClassObject **
0x18004bda8  mov     r9, rsi; struct IWbemContext *
0x18004bdab  xor     r8d, r8d; int
0x18004bdae  mov     rdx, [r13+18h]; unsigned __int16 *
0x18004bdb2  mov     rcx, r15; this
0x18004bdb5  call    ?Exec_GetObjectByPath@CWbemNamespace@@QEAAJPEBGJPEAUIWbemContext@@PEAPEAUIWbemClassObject@@2@Z; CWbemNamespace::Exec_GetObjectByPath(ushort const *,long,IWbemContext *,IWbemClassObject * *,IWbemClassObject * *)
0x18004bdba  mov     rsi, [rbp+160h+var_1A0]
0x18004bdbe  mov     [rsp+260h+var_200], rsi
0x18004bdc3  mov     r14, [rbp+160h+var_1A8]
0x18004bdc7  mov     [rsp+260h+var_1F8], r14
0x18004bdcc  cmp     eax, 80041002h
0x18004bdd1  jz      loc_18004CACC
0x18004bdd7  test    eax, eax
0x18004bdd9  js      loc_18004CAD1
0x18004bddf  lea     rcx, [rbp+160h+var_160]
0x18004bde3  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x18004bde9  nop
0x18004bdea  mov     rax, [r14]
0x18004bded  mov     [rsp+260h+var_240], rdi; bool
0x18004bdf2  xor     r9d, r9d
0x18004bdf5  lea     r8, [rbp+160h+var_160]
0x18004bdf9  lea     rdx, aDynamic_1; "Dynamic"
0x18004be00  mov     rcx, r14
0x18004be03  mov     rax, [rax+3D0h]
0x18004be0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be0f  test    eax, eax
0x18004be11  jns     loc_18004C253
0x18004be17  mov     rax, [r14]
0x18004be1a  lea     rdx, aProvider_1; "__Provider"
0x18004be21  mov     rcx, r14
0x18004be24  mov     rax, [rax+90h]
0x18004be2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be30  test    eax, eax
0x18004be32  jz      loc_18004CC5E
0x18004be38  mov     rax, [r14]
0x18004be3b  lea     rdx, aProviderregist; "__ProviderRegistration"
0x18004be42  mov     rcx, r14
0x18004be45  mov     rax, [rax+90h]
0x18004be4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be51  test    eax, eax
0x18004be53  jz      loc_18004CC5E
0x18004be59  mov     [rbp+160h+var_1D8], dil
0x18004be5d  lea     rdx, [rbp+160h+var_1D8]; bool *
0x18004be61  mov     rcx, r14; struct CWbemObject *
0x18004be64  call    ?IsDerivedFromSystem@@YAJAEAVCWbemObject@@PEA_N@Z; IsDerivedFromSystem(CWbemObject &,bool *)
0x18004be69  mov     ebx, eax
0x18004be6b  test    eax, eax
0x18004be6d  js      loc_18004CD52
0x18004be73  lea     rdx, [r15+0D8h]; struct CNtSecurityDescriptor *
0x18004be7a  mov     edi, 4
0x18004be7f  mov     [rsp+260h+var_230], 1; bool
0x18004be84  lea     r9, aDeleteDeletein; "Delete (DeleteInstance)"
0x18004be8b  mov     rcx, r15; this
0x18004be8e  mov     [rsp+260h+var_240], r12; unsigned __int16 *
0x18004be93  cmp     [rbp+160h+var_1D8], 0
0x18004be97  jz      loc_18004C51B
0x18004be9d  mov     r8d, edi; unsigned int
0x18004bea0  call    ?InnerAllowedWithSD@CWbemNamespace@@QEAA_NPEAVCNtSecurityDescriptor@@KPEBG1_N2@Z; CWbemNamespace::InnerAllowedWithSD(CNtSecurityDescriptor *,ulong,ushort const *,ushort const *,bool,bool)
0x18004bea5  test    al, al
0x18004bea7  jz      loc_18004CDAB
0x18004bead  test    r14, r14
0x18004beb0  jz      short loc_18004BEC1
0x18004beb2  mov     rax, [r14]
0x18004beb5  mov     rcx, r14
0x18004beb8  mov     rax, [rax+10h]
0x18004bebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bec1  xor     r14d, r14d
0x18004bec4  mov     [rsp+260h+var_1F8], r14
0x18004bec9  mov     [rbp+160h+var_140], r14
0x18004becd  mov     rcx, [r15+100h]
0x18004bed4  mov     rax, [rcx]
0x18004bed7  lea     rdx, [rbp+160h+var_140]
0x18004bedb  mov     rax, [rax+0E0h]
0x18004bee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bee7  test    eax, eax
0x18004bee9  js      loc_18004C73E
0x18004beef  mov     rbx, [rbp+160h+var_140]
0x18004bef3  mov     [rbp+160h+var_1D0], rbx
0x18004bef7  mov     [rbp+160h+var_168], r14
0x18004befb  mov     [rsp+260h+var_1F0], r14
0x18004bf00  lea     rax, [rsp+260h+var_1F0]
0x18004bf05  mov     [rbp+160h+var_1A8], rax
0x18004bf09  mov     [rbp+160h+var_1C0], r14
0x18004bf0d  lea     rax, [rbp+160h+var_168]
0x18004bf11  mov     [rbp+160h+var_1B8], rax
0x18004bf15  cmp     [rbp+160h+var_140], r14
0x18004bf19  jz      loc_18004C50C
0x18004bf1f  mov     rcx, [r15+100h]
0x18004bf26  mov     rax, [rcx]
0x18004bf29  lea     r8, [rsp+260h+var_1F0]
0x18004bf2e  xor     edx, edx
0x18004bf30  mov     rax, [rax+0B8h]
0x18004bf37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf3c  test    eax, eax
0x18004bf3e  js      loc_18004CDEF
0x18004bf44  mov     rcx, [rsp+260h+var_1F0]
0x18004bf49  mov     rax, [rcx]
0x18004bf4c  mov     r8, r12
0x18004bf4f  mov     edx, edi
0x18004bf51  mov     rax, [rax+18h]
0x18004bf55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf5a  xor     r8d, r8d; struct IWbemClassObject *
0x18004bf5d  test    eax, eax
0x18004bf5f  js      loc_18004C8A9
0x18004bf65  mov     dword ptr [rbp+160h+var_1C8], r14d
0x18004bf69  mov     rcx, [rsp+260h+var_1F0]
0x18004bf6e  mov     rax, [rcx]
0x18004bf71  lea     rdx, [rbp+160h+var_1C8]
0x18004bf75  mov     rax, [rax+0A8h]
0x18004bf7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf81  test    eax, eax
0x18004bf83  js      loc_18004CDEF
0x18004bf89  mov     ecx, dword ptr [rbp+160h+var_1C8]
0x18004bf8c  inc     ecx
0x18004bf8e  lea     eax, [r14+2]
0x18004bf92  mul     rcx
0x18004bf95  lea     rcx, [r14-1]
0x18004bf99  cmovb   rax, rcx
0x18004bf9d  mov     rcx, rax
0x18004bfa0  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18004bfa6  mov     r8, rax
0x18004bfa9  mov     [rbp+160h+var_168], rax
0x18004bfad  test    rax, rax
0x18004bfb0  jz      loc_18004CDF6
0x18004bfb6  mov     rcx, [rsp+260h+var_1F0]
0x18004bfbb  mov     rax, [rcx]
0x18004bfbe  lea     rdx, [rbp+160h+var_1C8]
0x18004bfc2  mov     rax, [rax+0A8h]
0x18004bfc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bfce  test    eax, eax
0x18004bfd0  js      loc_18004CDEF
0x18004bfd6  lea     r14, [r15+60h]
0x18004bfda  mov     rcx, [rbp+160h+var_140]
0x18004bfde  mov     rax, [rcx]
0x18004bfe1  mov     rdx, [rbp+160h+var_168]
0x18004bfe5  mov     qword ptr [rsp+260h+var_230], rdx
0x18004bfea  mov     rdx, [r14]
0x18004bfed  mov     [rsp+260h+var_238], rdx
0x18004bff2  mov     rdx, [rsp+260h+var_1F0]
0x18004bff7  mov     [rsp+260h+var_240], rdx
0x18004bffc  mov     r9, [rbp+160h+arg_18]
0x18004c003  mov     r8d, [rbp+160h+arg_10]
0x18004c00a  mov     edx, 2
0x18004c00f  mov     rax, [rax+28h]
0x18004c013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c018  test    eax, eax
0x18004c01a  js      loc_18004CA06
0x18004c020  xor     edi, edi
0x18004c022  mov     [rbp+160h+var_128], rdi
0x18004c026  cmp     eax, 40015h
0x18004c02b  jnz     short loc_18004C055
0x18004c02d  lea     rax, [rbp+160h+var_128]
0x18004c031  mov     [rsp+260h+var_240], rax; struct IWbemClassObject **
0x18004c036  xor     r9d, r9d; unsigned int
0x18004c039  mov     r8, r12; unsigned __int16 *
0x18004c03c  mov     rdx, [r15+40h]; struct IWmiDbHandle *
0x18004c040  mov     rcx, [r15+28h]; struct IWmiDbSession *
0x18004c044  call    ?GetObjectW@CRepository@@SAJPEAUIWmiDbSession@@PEAUIWmiDbHandle@@PEBGKPEAPEAUIWbemClassObject@@@Z; CRepository::GetObjectW(IWmiDbSession *,IWmiDbHandle *,ushort const *,ulong,IWbemClassObject * *)
0x18004c049  test    eax, eax
0x18004c04b  js      loc_18004C8C4
0x18004c051  mov     rdi, [rbp+160h+var_128]
0x18004c055  mov     [rbp+160h+var_1A0], rdi
0x18004c059  lea     rcx, [rbp+160h+pvarg]; pvarg
0x18004c060  call    cs:__imp_VariantInit
0x18004c066  nop
0x18004c067  mov     rcx, [rbp+160h+arg_18]
0x18004c06e  mov     rax, [rcx]
0x18004c071  lea     r9, [rbp+160h+pvarg]
0x18004c078  xor     r8d, r8d
0x18004c07b  lea     rdx, aGroupoperation; "__GroupOperationId"
0x18004c082  mov     rax, [rax+48h]
0x18004c086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c08b  test    eax, eax
0x18004c08d  js      short loc_18004C0D4
0x18004c08f  mov     rcx, [r15+118h]; String2
0x18004c096  call    ?IsLocalMachine@CWbemNamespace@@KAHPEBG@Z; CWbemNamespace::IsLocalMachine(ushort const *)
0x18004c09b  mov     dword ptr [rsp+260h+var_230], eax
0x18004c09f  mov     rax, [r15+128h]
0x18004c0a6  mov     [rsp+260h+var_238], rax
0x18004c0ab  mov     rax, [r15+120h]
0x18004c0b2  mov     [rsp+260h+var_240], rax
0x18004c0b7  mov     r9d, [r15+130h]
0x18004c0be  mov     r8, [rbp+160h+arg_18]
0x18004c0c5  mov     rdx, r12
0x18004c0c8  mov     ecx, dword ptr [rbp+160h+pvarg+8]
0x18004c0ce  call    cs:__imp_?PublishRepDelete@CPublishWMIOperationEvent@@SAJKPEAGPEAUIWbemContext@@K0_KH@Z; CPublishWMIOperationEvent::PublishRepDelete(ulong,ushort *,IWbemContext *,ulong,ushort *,unsigned __int64,int)
0x18004c0d4  xor     r9d, r9d; unsigned int
0x18004c0d7  mov     r8, r12; unsigned __int16 *
0x18004c0da  mov     rdx, [r15+40h]; struct IWmiDbHandle *
0x18004c0de  mov     rcx, [r15+28h]; struct IWmiDbSession *
0x18004c0e2  call    ?DeleteByPath@CRepository@@SAJPEAUIWmiDbSession@@PEAUIWmiDbHandle@@PEBGK@Z; CRepository::DeleteByPath(IWmiDbSession *,IWmiDbHandle *,ushort const *,ulong)
0x18004c0e7  mov     r15d, eax
0x18004c0ea  mov     rcx, [rbp+160h+var_140]
0x18004c0ee  xor     r12d, r12d
0x18004c0f1  test    rcx, rcx
0x18004c0f4  jz      short loc_18004C135
0x18004c0f6  mov     rdx, [rcx]
0x18004c0f9  mov     rax, [rdx+30h]
0x18004c0fd  mov     rdx, [rbp+160h+var_128]
0x18004c101  mov     [rsp+260h+var_228], rdx
0x18004c106  mov     rdx, [rbp+160h+var_168]
0x18004c10a  mov     qword ptr [rsp+260h+var_230], rdx
0x18004c10f  mov     rdx, [r14]
0x18004c112  mov     [rsp+260h+var_238], rdx
0x18004c117  mov     rdx, [rsp+260h+var_1F0]
0x18004c11c  mov     [rsp+260h+var_240], rdx
0x18004c121  mov     r9, [rbp+160h+arg_18]
  ... truncated ...
```
