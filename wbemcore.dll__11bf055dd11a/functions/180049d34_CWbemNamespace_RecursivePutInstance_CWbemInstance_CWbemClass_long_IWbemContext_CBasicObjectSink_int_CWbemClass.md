# CWbemNamespace::RecursivePutInstance(CWbemInstance *,CWbemClass *,long,IWbemContext *,CBasicObjectSink *,int,CWbemClass *)

- ea: `0x180049d34`
- end: `0x18004b6dd`
- name: `?RecursivePutInstance@CWbemNamespace@@QEAAJPEAVCWbemInstance@@PEAVCWbemClass@@JPEAUIWbemContext@@PEAVCBasicObjectSink@@H1@Z`
- size: `6569`
- prototype: `__int64 __fastcall(CWbemNamespace *this, struct CWbemInstance *, struct CWbemClass *, unsigned int, struct IWbemContext *, struct CBasicObjectSink *, int, struct CWbemClass *)`
- caller_count: `2`
- callee_count: `32`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180048a50`
- `0x18006f80c`

## callees

- `0x18000a86c`
- `0x18000b140`
- `0x18000b46c`
- `0x18000e950`
- `0x18000e99c`
- `0x18000ebd0`
- `0x18000fa74`
- `0x180011700`
- `0x18001307c`
- `0x18001f6d0`
- `0x180020358`
- `0x18002f578`
- `0x18003cfe0`
- `0x180049d34`
- `0x18004b6e4`
- `0x18004b88c`
- `0x18004b934`
- `0x18004ba3c`
- `0x18004ba84`
- `0x18005cc60`
- `0x1800604d0`
- `0x18006f80c`
- `0x1800733a4`
- `0x18007bbcc`
- `0x18007ebf4`
- `0x18007f408`
- `0x1800820a0`
- `0x1800827d0`
- `0x18009b428`
- `0x1800a02dc`
- `0x1800bee64`
- `0x1800da010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b0a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b4a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b6d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b0a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b4a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b6d1`
- `wbemcomn!??0CNtSecurityDescriptor@@QEAA@PEAX@Z` at `0x18004b4b2`
- `wbemcomn!??0CNtSecurityDescriptor@@QEAA@PEAX@Z` at `0x18004b4b2`
- `wbemcomn!??1CNtSecurityDescriptor@@QEAA@XZ` at `0x18004b655`
- `wbemcomn!??1CNtSecurityDescriptor@@QEAA@XZ` at `0x18004b6c3`
- `wbemcomn!??1CNtSecurityDescriptor@@QEAA@XZ` at `0x18004b655`
- `wbemcomn!??1CNtSecurityDescriptor@@QEAA@XZ` at `0x18004b6c3`
- `wbemcomn!?PublishRepUpdate@CPublishWMIOperationEvent@@SAJKPEAGKPEAUIWbemContext@@K0_KH@Z` at `0x18004a18b`
- `wbemcomn!?PublishRepUpdate@CPublishWMIOperationEvent@@SAJKPEAGKPEAUIWbemContext@@K0_KH@Z` at `0x18004a935`
- `wbemcomn!?PublishRepUpdate@CPublishWMIOperationEvent@@SAJKPEAGKPEAUIWbemContext@@K0_KH@Z` at `0x18004b5d0`
- `wbemcomn!?PublishRepUpdate@CPublishWMIOperationEvent@@SAJKPEAGKPEAUIWbemContext@@K0_KH@Z` at `0x18004a18b`
- `wbemcomn!?PublishRepUpdate@CPublishWMIOperationEvent@@SAJKPEAGKPEAUIWbemContext@@K0_KH@Z` at `0x18004a935`
- `wbemcomn!?PublishRepUpdate@CPublishWMIOperationEvent@@SAJKPEAGKPEAUIWbemContext@@K0_KH@Z` at `0x18004b5d0`
- `wbemcomn!?IsNull@CVar@@QEAAHXZ` at `0x18004a89c`
- `wbemcomn!?IsNull@CVar@@QEAAHXZ` at `0x18004a89c`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180049f06`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18004a866`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180049f06`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18004a866`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180049f31`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180049f99`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x18004a8ae`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180049f31`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180049f99`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x18004a8ae`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004a2d2`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004a397`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004a65c`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004a765`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004a8dd`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004b1ee`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004b695`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004a2d2`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004a397`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004a65c`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004a765`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004a8dd`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004b1ee`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004b695`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18004a284`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18004a5ca`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18004a284`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18004a5ca`
- `wbemcomn!GetMemLogObject` at `0x18004a5d9`
- `wbemcomn!GetMemLogObject` at `0x18004a808`
- `wbemcomn!GetMemLogObject` at `0x18004a97c`
- `wbemcomn!GetMemLogObject` at `0x18004a9ea`
- `wbemcomn!GetMemLogObject` at `0x18004aa7c`
- `wbemcomn!GetMemLogObject` at `0x18004aad5`
- `wbemcomn!GetMemLogObject` at `0x18004ab24`
- `wbemcomn!GetMemLogObject` at `0x18004ab9a`
- `wbemcomn!GetMemLogObject` at `0x18004abdd`
- `wbemcomn!GetMemLogObject` at `0x18004ac5c`
- `wbemcomn!GetMemLogObject` at `0x18004acad`
- `wbemcomn!GetMemLogObject` at `0x18004ad0b`
- `wbemcomn!GetMemLogObject` at `0x18004ad42`
- `wbemcomn!GetMemLogObject` at `0x18004ad83`
- `wbemcomn!GetMemLogObject` at `0x18004ae03`
- `wbemcomn!GetMemLogObject` at `0x18004ae5f`
- `wbemcomn!GetMemLogObject` at `0x18004aea0`
- `wbemcomn!GetMemLogObject` at `0x18004aee6`
- `wbemcomn!GetMemLogObject` at `0x18004af3e`
- `wbemcomn!GetMemLogObject` at `0x18004afa0`
- `wbemcomn!GetMemLogObject` at `0x18004aff2`
- `wbemcomn!GetMemLogObject` at `0x18004b049`
- `wbemcomn!GetMemLogObject` at `0x18004b0b3`
- `wbemcomn!GetMemLogObject` at `0x18004b0f9`
- `wbemcomn!GetMemLogObject` at `0x18004b15d`
- `wbemcomn!GetMemLogObject` at `0x18004b1f9`
- `wbemcomn!GetMemLogObject` at `0x18004b233`
- `wbemcomn!GetMemLogObject` at `0x18004b2b5`
- `wbemcomn!GetMemLogObject` at `0x18004b313`
- `wbemcomn!GetMemLogObject` at `0x18004b399`
- `wbemcomn!GetMemLogObject` at `0x18004b3ff`
- `wbemcomn!GetMemLogObject` at `0x18004b446`
- `wbemcomn!GetMemLogObject` at `0x18004b4c6`
- `wbemcomn!GetMemLogObject` at `0x18004b5eb`
- `wbemcomn!GetMemLogObject` at `0x18004a5d9`
- `wbemcomn!GetMemLogObject` at `0x18004a808`
- `wbemcomn!GetMemLogObject` at `0x18004a97c`
- `wbemcomn!GetMemLogObject` at `0x18004a9ea`
- `wbemcomn!GetMemLogObject` at `0x18004aa7c`
- `wbemcomn!GetMemLogObject` at `0x18004aad5`
- `wbemcomn!GetMemLogObject` at `0x18004ab24`
- `wbemcomn!GetMemLogObject` at `0x18004ab9a`
- `wbemcomn!GetMemLogObject` at `0x18004abdd`
- `wbemcomn!GetMemLogObject` at `0x18004ac5c`
- `wbemcomn!GetMemLogObject` at `0x18004acad`
- `wbemcomn!GetMemLogObject` at `0x18004ad0b`
- `wbemcomn!GetMemLogObject` at `0x18004ad42`
- `wbemcomn!GetMemLogObject` at `0x18004ad83`
- `wbemcomn!GetMemLogObject` at `0x18004ae03`
- `wbemcomn!GetMemLogObject` at `0x18004ae5f`
- `wbemcomn!GetMemLogObject` at `0x18004aea0`
- `wbemcomn!GetMemLogObject` at `0x18004aee6`
- `wbemcomn!GetMemLogObject` at `0x18004af3e`
- `wbemcomn!GetMemLogObject` at `0x18004afa0`
- `wbemcomn!GetMemLogObject` at `0x18004aff2`
- `wbemcomn!GetMemLogObject` at `0x18004b049`
- `wbemcomn!GetMemLogObject` at `0x18004b0b3`
- `wbemcomn!GetMemLogObject` at `0x18004b0f9`
- `wbemcomn!GetMemLogObject` at `0x18004b15d`
- `wbemcomn!GetMemLogObject` at `0x18004b1f9`
- `wbemcomn!GetMemLogObject` at `0x18004b233`
- `wbemcomn!GetMemLogObject` at `0x18004b2b5`
- `wbemcomn!GetMemLogObject` at `0x18004b313`
- `wbemcomn!GetMemLogObject` at `0x18004b399`
- `wbemcomn!GetMemLogObject` at `0x18004b3ff`
- `wbemcomn!GetMemLogObject` at `0x18004b446`
- `wbemcomn!GetMemLogObject` at `0x18004b4c6`
- `wbemcomn!GetMemLogObject` at `0x18004b5eb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004a5e5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004a813`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004a987`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004a9f6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004aa8c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004aae0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004ab2f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004aba6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004abe8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004ac67`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004acbd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004ad1b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004ad4d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004ad93`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004ae0e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004ae6a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004aeab`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004aef4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004af49`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004afab`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b002`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b054`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b0be`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b109`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b16c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b209`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b242`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b2c5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b31f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b3ac`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b410`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b452`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b4d6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b5f7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004a5e5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004a813`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004a987`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004a9f6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004aa8c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004aae0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004ab2f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004aba6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004abe8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004ac67`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004acbd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004ad1b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004ad4d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004ad93`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004ae0e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004ae6a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004aeab`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004aef4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004af49`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004afab`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b002`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b054`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b0be`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b109`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b16c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b209`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b242`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b2c5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b31f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b3ac`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b410`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b452`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b4d6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b5f7`
- `FastProx!?IsDynamic@CWbemClass@@QEAAHXZ` at `0x180049dd9`
- `FastProx!?IsDynamic@CWbemClass@@QEAAHXZ` at `0x180049e4f`
- `FastProx!?IsDynamic@CWbemClass@@QEAAHXZ` at `0x18004a42a`
- `FastProx!?IsDynamic@CWbemClass@@QEAAHXZ` at `0x18004a44c`
- `FastProx!?IsDynamic@CWbemClass@@QEAAHXZ` at `0x180049dd9`
- `FastProx!?IsDynamic@CWbemClass@@QEAAHXZ` at `0x180049e4f`
- `FastProx!?IsDynamic@CWbemClass@@QEAAHXZ` at `0x18004a42a`
- `FastProx!?IsDynamic@CWbemClass@@QEAAHXZ` at `0x18004a44c`
- `FastProx!?IsAbstract@CWbemClass@@QEAAHXZ` at `0x180049d96`
- `FastProx!?IsAbstract@CWbemClass@@QEAAHXZ` at `0x18004a43b`
- `FastProx!?IsAbstract@CWbemClass@@QEAAHXZ` at `0x180049d96`
- `FastProx!?IsAbstract@CWbemClass@@QEAAHXZ` at `0x18004a43b`
- `FastProx!?IsAmendment@CWbemClass@@QEAAHXZ` at `0x180049da7`
- `FastProx!?IsAmendment@CWbemClass@@QEAAHXZ` at `0x180049da7`
- `FastProx!?PlugKeyHoles@CWbemInstance@@QEAAJXZ` at `0x180049e62`
- `FastProx!?PlugKeyHoles@CWbemInstance@@QEAAJXZ` at `0x180049e62`

## string_xrefs

- `0x180049ffb`: `__RELPATH`
- `0x180049ea0`: `Write (PutInstance)`
- `0x18004b29b`: `Update (Namespace)`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CWbemNamespace::RecursivePutInstance(
        CWbemNamespace *this,
        struct CWbemInstance *a2,
        struct CWbemClass *a3,
        unsigned int a4,
        struct IWbemContext *a5,
        struct CBasicObjectSink *a6,
        int a7,
        struct CWbemClass *a8)
{
  unsigned int v8; // r13d
  unsigned int v12; // ebx
  int v13; // r14d
  int v14; // ebx
  struct IWbemClassObject *v15; // rbx
  __int64 v16; // rdx
  int v17; // esi
  struct CNtSecurityDescriptor *v18; // rdx
  int v19; // edi
  __int64 v20; // rdi
  CWbemNamespace *v21; // rcx
  CWbemNamespace *v22; // rcx
  int updated; // esi
  int NamespaceSecurityFromQualifier; // esi
  HLOCAL v25; // r14
  const unsigned __int16 *LPWSTR; // rax
  const unsigned __int16 *v27; // r8
  int ObjectW; // esi
  struct IWbemClassObject *v29; // rsi
  char v30; // dl
  const struct _GUID *v31; // r8
  int IsLocalMachine; // eax
  unsigned __int16 *bstrVal; // rdx
  unsigned int v34; // eax
  int Namespace; // r13d
  HRESULT v36; // eax
  OLECHAR *v37; // rsi
  OLECHAR *v38; // r15
  unsigned int v39; // esi
  unsigned int v41; // r15d
  HRESULT v42; // eax
  unsigned int v43; // edi
  int v44; // esi
  int v45; // eax
  const struct _GUID *v46; // r8
  unsigned int v47; // eax
  CMemoryLog *v48; // rax
  unsigned int v49; // esi
  HRESULT v50; // eax
  unsigned int v51; // eax
  HRESULT v52; // eax
  int IsPutRequiredForClass; // esi
  CMemoryLog *v54; // rax
  const unsigned __int16 *v55; // rax
  int v56; // eax
  unsigned __int16 *v57; // rdx
  const unsigned __int16 *v58; // r8
  int v59; // eax
  CMemoryLog *v60; // rax
  CClientCnt *v61; // rcx
  __int64 v62; // rdx
  int v63; // edx
  CMemoryLog *v64; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v66; // rax
  CMemoryLog *v67; // rax
  int v68; // edx
  CMemoryLog *v69; // rax
  int v70; // edx
  CMemoryLog *v71; // rax
  CClientCnt *v72; // rcx
  __int64 v73; // rdx
  CMemoryLog *v74; // rax
  CMemoryLog *v75; // rax
  CClientCnt *v76; // rcx
  __int64 v77; // rdx
  CMemoryLog *v78; // rax
  CMemoryLog *v79; // rax
  CMemoryLog *v80; // rax
  int v81; // edx
  CMemoryLog *v82; // rax
  CMemoryLog *v83; // rax
  CMemoryLog *v84; // rax
  CMemoryLog *v85; // rax
  CMemoryLog *v86; // rax
  CMemoryLog *v87; // rax
  CMemoryLog *v88; // rax
  CMemoryLog *v89; // rax
  CMemoryLog *v90; // rax
  CMemoryLog *v91; // rax
  CMemoryLog *v92; // rax
  unsigned int v93; // ebx
  CClientCnt *v94; // rcx
  __int64 v95; // rdx
  __int64 v96; // r9
  CMemoryLog *v97; // rax
  CMemoryLog *v98; // rax
  const unsigned __int16 *v99; // rax
  CMemoryLog *v100; // rax
  int v101; // r13d
  CMemoryLog *v102; // rax
  int v103; // edx
  CMemoryLog *v104; // rax
  CMemoryLog *v105; // rax
  CMemoryLog *v106; // rax
  CMemoryLog *v107; // rax
  const struct _GUID *v108; // r8
  int v109; // eax
  unsigned __int16 *v110; // rdx
  CMemoryLog *v111; // rax
  bool v112; // [rsp+28h] [rbp-D8h]
  bool v113; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v114; // [rsp+58h] [rbp-A8h] BYREF
  struct IWbemClassObject *v115; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL v116; // [rsp+68h] [rbp-98h] BYREF
  struct IWbemClassObject *v117; // [rsp+70h] [rbp-90h] BYREF
  int v118; // [rsp+78h] [rbp-88h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp-80h] BYREF
  int v120; // [rsp+98h] [rbp-68h] BYREF
  CWbemNamespace *v121; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v122[8]; // [rsp+A8h] [rbp-58h] BYREF
  void (__fastcall *v123)(_QWORD); // [rsp+B0h] [rbp-50h]
  _QWORD *v124; // [rsp+B8h] [rbp-48h]
  _BYTE v125[32]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v126; // [rsp+E0h] [rbp-20h] BYREF
  HLOCAL hMem; // [rsp+E8h] [rbp-18h] BYREF
  struct IWbemClassObject *v128; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v129[8]; // [rsp+F8h] [rbp-8h] BYREF
  void (__fastcall *v130)(_QWORD); // [rsp+100h] [rbp+0h]
  _QWORD *v131; // [rsp+108h] [rbp+8h]
  const unsigned __int16 *v132[2]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 *v133; // [rsp+120h] [rbp+20h] BYREF
  struct IWbemClassObject *v134; // [rsp+128h] [rbp+28h] BYREF
  VARIANTARG v135; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v136[40]; // [rsp+148h] [rbp+48h] BYREF
  VARIANTARG v137; // [rsp+170h] [rbp+70h] BYREF
  VARIANTARG v138; // [rsp+188h] [rbp+88h] BYREF
  int v140; // [rsp+208h] [rbp+108h]
  int v141; // [rsp+208h] [rbp+108h]

  v8 = a4;
  v12 = 1;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, a2, a3);
  }
  v120 = 0;
  if ( (v8 & 0x20000000) != 0 )
  {
    MemLogObject = GetMemLogObject();
    v43 = -2147217400;
    CMemoryLog::Write(MemLogObject, -2147217400);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 140, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749896LL);
    }
    return v43;
  }
  if ( CWbemClass::IsAbstract(a3)
    || CWbemClass::IsAmendment(a3)
    || !(*(unsigned int (__fastcall **)(struct CWbemClass *))(*(_QWORD *)a3 + 1032LL))(a3) )
  {
    return v12;
  }
  v13 = 1;
  v118 = 1;
  if ( CWbemClass::IsDynamic(a3) )
  {
    v12 = CWbemNamespace::RecursivePutParentClassesDynamicClass(this, a2, a3, v8, a5, a6, &v118);
    if ( (v12 & 0x80000000) != 0 )
    {
      v66 = GetMemLogObject();
      CMemoryLog::Write(v66, v12);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 141, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v12);
      }
      return v12;
    }
    v13 = v118;
  }
  v115 = 0;
  v14 = CWbemInstance::ConvertToClass(a2, a3, (struct CWbemInstance **)&v115);
  if ( v14 < 0 )
  {
    v67 = GetMemLogObject();
    CMemoryLog::Write(v67, v14);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        142,
        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
        (unsigned int)v14);
    }
    v68 = v14;
    return CBasicObjectSink::Return(a6, v68, 0);
  }
  v15 = v115;
  if ( !v115 )
  {
    v69 = GetMemLogObject();
    CMemoryLog::Write(v69, -1);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids);
    }
    v68 = -2147217398;
    return CBasicObjectSink::Return(a6, v68, 0);
  }
  v134 = v115;
  v133 = (unsigned __int16 *)((__int64 (__fastcall *)(struct IWbemClassObject *, _QWORD))v115->lpVtbl[4].BeginMethodEnumeration)(
                               v115,
                               0);
  MakeGuard<void (*)(unsigned short *),RefHolder<unsigned short *>>(v122, v16, &v133);
  if ( CWbemClass::IsDynamic(a3) )
  {
    if ( !a7 && (v8 & 1) != 0 )
    {
      IsPutRequiredForClass = CWbemNamespace::IsPutRequiredForClass(a3, a2, a5, v13);
      if ( IsPutRequiredForClass < 0 )
      {
        v54 = GetMemLogObject();
        CMemoryLog::Write(v54, IsPutRequiredForClass);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            144,
            WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            (unsigned int)IsPutRequiredForClass);
        }
        v51 = CBasicObjectSink::Return(a6, IsPutRequiredForClass, 0);
        goto LABEL_108;
      }
      if ( IsPutRequiredForClass == 1 )
      {
        v70 = 0;
LABEL_185:
        v12 = CBasicObjectSink::Return(a6, v70, 0);
        goto LABEL_325;
      }
    }
    v51 = CWbemNamespace::PutInstanceDynamicClass(this, (struct CWbemInstance *)v115, a3, v8, a5, a6, &a7, v133);
LABEL_108:
    v43 = v51;
    if ( !v122[0] )
      v123(*v124);
    if ( v15 )
      ((void (__fastcall *)(struct IWbemClassObject *))v15->lpVtbl->Release)(v15);
    goto LABEL_70;
  }
  v17 = CWbemInstance::PlugKeyHoles((CWbemInstance *)v115);
  if ( v17 < 0 )
  {
    v71 = GetMemLogObject();
    CMemoryLog::Write(v71, v17);
    v72 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_183;
    }
    v73 = 145;
    goto LABEL_182;
  }
  v113 = 0;
  v17 = IsDerivedFromSystem((struct CWbemObject *)v115, &v113);
  if ( v17 < 0 )
  {
    v74 = GetMemLogObject();
    CMemoryLog::Write(v74, v17);
    v72 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_183;
    }
    v73 = 146;
LABEL_182:
    WPP_SF_d(*((_QWORD *)v72 + 2), v73, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, (unsigned int)v17);
LABEL_183:
    v70 = v17;
    goto LABEL_185;
  }
  v18 = (CWbemNamespace *)((char *)this + 216);
  if ( v113 )
  {
    if ( !CWbemNamespace::InnerAllowedWithSD(this, v18, 4u, L"Write (PutInstance)", v133, v112, 1)
      && ((int)CWbemNamespace::CheckSecurityCenterException(this, (struct CWbemInstance *)v115, &v120) < 0 || !v120) )
    {
      v75 = GetMemLogObject();
      CMemoryLog::Write(v75, -2147217405);
      v76 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_197;
      }
      v77 = 147;
LABEL_196:
      WPP_SF_d(*((_QWORD *)v76 + 2), v77, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749891LL);
LABEL_197:
      v70 = -2147217405;
      goto LABEL_185;
    }
  }
  else if ( !CWbemNamespace::InnerAllowedWithSD(this, v18, 8u, L"Write (PutInstance)", v133, v112, 1) )
  {
    if ( !a8 || !CWbemClass::IsDynamic(a8) || CWbemClass::IsAbstract(a3) || CWbemClass::IsDynamic(a3) )
    {
      v78 = GetMemLogObject();
      CMemoryLog::Write(v78, -2147217405);
      v76 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_197;
      }
      v77 = 148;
      goto LABEL_196;
    }
    v12 = 1;
LABEL_325:
    ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>::~ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>(v122);
    CReleaseMe::release((CReleaseMe *)&v134);
    return v12;
  }
  v126 = 0;
  v19 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 32) + 224LL))(*((_QWORD *)this + 32), &v126);
  if ( v19 < 0 )
  {
    v79 = GetMemLogObject();
    CMemoryLog::Write(v79, v19);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        149,
        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
        (unsigned int)v19);
    }
    v70 = v19;
    goto LABEL_185;
  }
  v20 = v126;
  v114 = v126;
  CVar::CVar((CVar *)v125);
  if ( ((int (__fastcall *)(struct IWbemClassObject *, _BYTE *))v115->lpVtbl[5].Release)(v115, v125) < 0 )
  {
    v80 = GetMemLogObject();
    CMemoryLog::Write(v80, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 150, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749894LL);
    }
    v81 = -2147217402;
    goto LABEL_212;
  }
  v132[0] = CVar::GetLPWSTR((CVar *)v125);
  if ( !(unsigned int)wbem_wcsicmp(v132[0], L"__NAMESPACE") )
  {
    v121 = (CWbemNamespace *)((char *)this + 40);
LABEL_19:
    updated = CWbemNamespace::MUILocaleUpdateNSInstance(v21, (struct CWbemInstance *)v115);
    if ( updated < 0 )
    {
      v82 = GetMemLogObject();
      CMemoryLog::Write(v82, updated);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          151,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          (unsigned int)updated);
      }
      v49 = CBasicObjectSink::Return(a6, updated, 0);
      goto LABEL_98;
    }
    hMem = 0;
    NamespaceSecurityFromQualifier = CWbemNamespace::GetNamespaceSecurityFromQualifier(
                                       v22,
                                       (struct CWbemInstance *)v115,
                                       &hMem);
    if ( NamespaceSecurityFromQualifier >= 0 )
    {
      v113 = 1;
      v25 = hMem;
      goto LABEL_24;
    }
    v83 = GetMemLogObject();
    CMemoryLog::Write(v83, NamespaceSecurityFromQualifier);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        152,
        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
        (unsigned int)NamespaceSecurityFromQualifier);
    }
    v81 = NamespaceSecurityFromQualifier;
LABEL_212:
    v12 = CBasicObjectSink::Return(a6, v81, 0);
LABEL_324:
    CVar::~CVar((CVar *)v125);
    CReleaseMe::release((CReleaseMe *)&v114);
    goto LABEL_325;
  }
  LPWSTR = CVar::GetLPWSTR((CVar *)v125);
  v121 = (CWbemNamespace *)((char *)this + 40);
  if ( !(unsigned int)CRepository::InheritsFrom(
                        *((struct IWmiDbSession **)this + 5),
                        *((struct IWmiDbHandle **)this + 7),
                        v27,
                        LPWSTR) )
  {
    v121 = (CWbemNamespace *)((char *)this + 40);
    goto LABEL_19;
  }
  v113 = 0;
  v25 = 0;
  hMem = 0;
LABEL_24:
  v116 = v25;
  VariantInit(&pvarg);
  ObjectW = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD))v115->lpVtbl->Get)(
              v115,
              L"__RELPATH",
              0,
              &pvarg,
              0);
  if ( ObjectW < 0 )
  {
    v84 = GetMemLogObject();
    CMemoryLog::Write(v84, ObjectW);
    v61 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_145;
    }
    v62 = 153;
    goto LABEL_144;
  }
  if ( pvarg.vt != 8 )
  {
    v85 = GetMemLogObject();
    CMemoryLog::Write(v85, -2147217398);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 154, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749898LL);
    }
    v63 = -2147217398;
    goto LABEL_152;
  }
  v128 = 0;
  ObjectW = CRepository::GetObjectW(
              *(struct IWmiDbSession **)v121,
              *((struct IWmiDbHandle **)this + 8),
              pvarg.bstrVal,
              0,
              &v128);
  if ( ObjectW >= 0 )
  {
    v29 = v128;
    v117 = v128;
    if ( (v8 & 3) == 2 )
    {
      v91 = GetMemLogObject();
      CMemoryLog::Write(v91, -2147217383);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          163,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          2147749913LL);
      }
      v12 = CBasicObjectSink::Return(a6, -2147217383, 0);
      goto LABEL_322;
    }
    v121 = 0;
    MakeGuard<void (*)(CWbemNamespace *),RefHolder<CWbemNamespace *>>(v129, 0, &v121);
    if ( v113 == v30 )
    {
LABEL_29:
      if ( (v8 & 0x20000) != 0 )
      {
        v101 = CWbemNamespace::SplitLocalized(this, (struct CWbemObject *)v115, (struct CWbemObject *)v128);
        if ( v101 < 0 )
        {
          v102 = GetMemLogObject();
          CMemoryLog::Write(v102, v101);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              168,
              WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
              (unsigned int)v101);
          }
          v103 = v101;
LABEL_290:
          v12 = CBasicObjectSink::Return(a6, v103, 0);
          goto LABEL_321;
        }
        v8 = a4;
      }
      v140 = CWbemNamespace::DecorateObject(this, v115);
      if ( v140 < 0 )
      {
        v104 = GetMemLogObject();
        CMemoryLog::Write(v104, v140);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            169,
            WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            (unsigned int)v140);
        }
        v41 = CBasicObjectSink::Return(a6, v140, 0);
LABEL_57:
        if ( !v129[0] )
          v130(*v131);
        if ( v29 )
          ((void (__fastcall *)(struct IWbemClassObject *))v29->lpVtbl->Release)(v29);
        v117 = 0;
        VariantClear(&pvarg);
        if ( v25 )
          LocalFree(v25);
        CVar::~CVar((CVar *)v125);
        if ( v20 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        v114 = 0;
        if ( !v122[0] )
          v123(*v124);
        if ( v15 )
          ((void (__fastcall *)(struct IWbemClassObject *))v15->lpVtbl->Release)(v15);
        v43 = v41;
LABEL_70:
        v134 = 0;
        return v43;
      }
      if ( !v126
        || (v141 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, struct IWbemContext *, _QWORD, _QWORD, const unsigned __int16 *, struct IWbemClassObject *))(*(_QWORD *)v126 + 24LL))(
                     v126,
                     1,
                     v8,
                     a5,
                     0,
                     *((_QWORD *)this + 12),
                     v132[0],
                     v115),
            v141 >= 0) )
      {
        VariantInit(&v135);
        if ( ((int (__fastcall *)(struct IWbemContext *, const wchar_t *, _QWORD, VARIANTARG *))a5->lpVtbl->GetValue)(
               a5,
               L"__GroupOperationId",
               0,
               &v135) >= 0 )
        {
          IsLocalMachine = CWbemNamespace::IsLocalMachine(*((wchar_t **)this + 35));
          bstrVal = 0;
          if ( pvarg.vt == 8 )
            bstrVal = pvarg.bstrVal;
          CPublishWMIOperationEvent::PublishRepUpdate(
            v135.cyVal.Lo,
            bstrVal,
            v8,
            a5,
            *((_DWORD *)this + 76),
            *((unsigned __int16 **)this + 36),
            *((_QWORD *)this + 37),
            IsLocalMachine);
        }
        v34 = CRepository::PutObject(
                *((struct IWmiDbSession **)this + 5),
                *((struct IWmiDbHandle **)this + 8),
                v31,
                v115,
                v8);
        Namespace = v34;
        if ( v126 )
          (*(void (__fastcall **)(__int64, __int64, _QWORD, struct IWbemContext *, _QWORD, _QWORD, const unsigned __int16 *, struct IWbemClassObject *, struct IWbemClassObject *))(*(_QWORD *)v126 + 32LL))(
            v126,
            1,
            v34,
            a5,
            0,
            *((_QWORD *)this + 12),
            v132[0],
            v115,
            v128);
        if ( Namespace >= 0 )
        {
          if ( !hMem )
          {
LABEL_41:
            v36 = VariantClear(&v135);
            if ( v36 < 0 )
              _com_issue_error(v36);
            if ( !v129[0] )
              v130(*v131);
            if ( v29 )
              ((void (__fastcall *)(struct IWbemClassObject *))v29->lpVtbl->Release)(v29);
            v117 = 0;
            goto LABEL_47;
          }
          CNtSecurityDescriptor::CNtSecurityDescriptor((CNtSecurityDescriptor *)v132, hMem);
          if ( (unsigned int)SetDefaultGroup((struct CNtSecurityDescriptor *)v132) )
          {
            Namespace = CWbemNamespace::CommonValidateAndSetSD(v121, (struct CNtSecurityDescriptor *)v132, 1);
            if ( Namespace >= 0 )
            {
              CNtSecurityDescriptor::~CNtSecurityDescriptor((CNtSecurityDescriptor *)v132);
              goto LABEL_41;
            }
            VariantInit(&v138);
            if ( ((int (__fastcall *)(struct IWbemContext *, const wchar_t *, _QWORD, VARIANTARG *))a5->lpVtbl->GetValue)(
                   a5,
                   L"__GroupOperationId",
                   0,
                   &v138) >= 0 )
            {
              v109 = CWbemNamespace::IsLocalMachine(*((wchar_t **)this + 35));
              v110 = 0;
              if ( pvarg.vt == 8 )
                v110 = pvarg.bstrVal;
              CPublishWMIOperationEvent::PublishRepUpdate(
                v138.cyVal.Lo,
                v110,
                0x4001u,
                a5,
                *((_DWORD *)this + 76),
                *((unsigned __int16 **)this + 36),
                *((_QWORD *)this + 37),
                v109);
            }
            CRepository::PutObject(
              *((struct IWmiDbSession **)this + 5),
              *((struct IWmiDbHandle **)this + 8),
              v108,
              v128,
              0x4001u);
            v111 = GetMemLogObject();
            CMemoryLog::Write(v111, Namespace);
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                173,
                WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                (unsigned int)Namespace);
            }
            v12 = CBasicObjectSink::Return(a6, Namespace, 0);
            _variant_t::~_variant_t((_variant_t *)&v138);
          }
          else
          {
            v107 = GetMemLogObject();
            v12 = -2147217407;
            CMemoryLog::Write(v107, -2147217407);
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                172,
                WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                2147749889LL);
            }
          }
          CNtSecurityDescriptor::~CNtSecurityDescriptor((CNtSecurityDescriptor *)v132);
          _variant_t::~_variant_t((_variant_t *)&v135);
          goto LABEL_321;
        }
        v106 = GetMemLogObject();
        CMemoryLog::Write(v106, Namespace);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            171,
            WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            (unsigned int)Namespace);
        }
        v41 = CBasicObjectSink::Return(a6, Namespace, 0);
        v42 = VariantClear(&v135);
        if ( v42 < 0 )
          _com_issue_error(v42);
        goto LABEL_57;
      }
      v105 = GetMemLogObject();
      CMemoryLog::Write(v105, v141);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          170,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          (unsigned int)v141);
      }
      v103 = v141;
      goto LABEL_290;
    }
    CVar::CVar((CVar *)v136);
    v118 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _BYTE *))v115->lpVtbl[3].CompareTo)(
             v115,
             L"Name",
             v136);
    if ( v118 < 0 )
    {
      v92 = GetMemLogObject();
      v93 = v118;
      CMemoryLog::Write(v92, v118);
      v94 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_266;
      }
      v95 = 164;
    }
    else
    {
      if ( CVar::IsNull((CVar *)v136) )
      {
        v97 = GetMemLogObject();
        v93 = -2147217394;
        CMemoryLog::Write(v97, -2147217394);
        v94 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_266;
        }
        v95 = 165;
        v96 = 2147749902LL;
        goto LABEL_265;
      }
      v55 = CVar::GetLPWSTR((CVar *)v136);
      v118 = CWbemNamespace::BuildChildNamespace(this, v55, &v121);
      if ( v118 >= 0 )
      {
        if ( v120 )
          goto LABEL_131;
        v99 = 0;
        if ( pvarg.vt == 8 )
          v99 = pvarg.bstrVal;
        if ( CWbemNamespace::InnerAllowedWithSD(
               v121,
               (CWbemNamespace *)((char *)v121 + 216),
               4u,
               L"Update (Namespace)",
               v99,
               0,
               1) )
        {
LABEL_131:
          CVar::~CVar((CVar *)v136);
          goto LABEL_29;
        }
        v100 = GetMemLogObject();
        v12 = -2147217405;
        CMemoryLog::Write(v100, -2147217405);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            167,
            WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            2147749891LL);
        }
LABEL_267:
        CVar::~CVar((CVar *)v136);
LABEL_321:
        ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>::~ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>(v129);
LABEL_322:
        CReleaseMe::release((CReleaseMe *)&v117);
        goto LABEL_323;
      }
      v98 = GetMemLogObject();
      v93 = v118;
      CMemoryLog::Write(v98, v118);
      v94 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_266:
        v12 = CBasicObjectSink::Return(a6, v93, 0);
        goto LABEL_267;
      }
      v95 = 166;
    }
    v96 = v93;
LABEL_265:
    WPP_SF_d(*((_QWORD *)v94 + 2), v95, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v96);
    goto LABEL_266;
  }
  if ( ObjectW != -2147217406 )
  {
    v86 = GetMemLogObject();
    CMemoryLog::Write(v86, ObjectW);
    v61 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_145;
    }
    v62 = 155;
    goto LABEL_144;
  }
  if ( (v8 & 0x20000) != 0 )
  {
    ObjectW = CWbemNamespace::SplitLocalized(this, (struct CWbemObject *)v115, 0);
    if ( ObjectW < 0 )
    {
      v87 = GetMemLogObject();
      CMemoryLog::Write(v87, ObjectW);
      v61 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_145;
      }
      v62 = 156;
      goto LABEL_144;
    }
  }
  if ( (v8 & 3) == 1 )
  {
    if ( a7 )
    {
      v88 = GetMemLogObject();
      CMemoryLog::Write(v88, -2147217406);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          157,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          2147749890LL);
      }
      v63 = -2147217406;
      goto LABEL_152;
    }
    goto LABEL_114;
  }
  if ( (v8 & 1) == 0 && !a7 )
  {
LABEL_114:
    VariantClear(&pvarg);
    CFreeMe<void>::~CFreeMe<void>(&v116);
    CVar::~CVar((CVar *)v125);
    CReleaseMe::release((CReleaseMe *)&v114);
    v12 = 1;
    goto LABEL_325;
  }
  if ( !v113 )
  {
    v44 = CWbemNamespace::DecorateObject(this, v115);
    if ( v44 < 0 )
    {
      v89 = GetMemLogObject();
      CMemoryLog::Write(v89, v44);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          159,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          (unsigned int)v44);
      }
      v49 = CBasicObjectSink::Return(a6, v44, 0);
    }
    else
    {
      v117 = 0;
      if ( v126 )
      {
        v45 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, struct IWbemContext *, _QWORD, _QWORD, const unsigned __int16 *, struct IWbemClassObject *))(*(_QWORD *)v126 + 24LL))(
                v126,
                1,
                v8,
                a5,
                0,
                *((_QWORD *)this + 12),
                v132[0],
                v115);
        ObjectW = v45;
        if ( v45 < 0 )
        {
          v90 = GetMemLogObject();
          CMemoryLog::Write(v90, ObjectW);
          v61 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_145;
          }
          v62 = 160;
          goto LABEL_144;
        }
        if ( v45 == 262162 )
        {
          v58 = 0;
          if ( pvarg.vt == 8 )
            v58 = pvarg.bstrVal;
          v59 = CRepository::GetObjectW(
                  *((struct IWmiDbSession **)this + 5),
                  *((struct IWmiDbHandle **)this + 7),
                  v58,
                  0,
                  &v117);
          ObjectW = 0;
          if ( v59 != -2147217406 )
            ObjectW = v59;
          if ( ObjectW < 0 )
          {
            v60 = GetMemLogObject();
            CMemoryLog::Write(v60, ObjectW);
            v61 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_145;
            }
            v62 = 161;
LABEL_144:
            WPP_SF_d(*((_QWORD *)v61 + 2), v62, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, (unsigned int)ObjectW);
LABEL_145:
            v63 = ObjectW;
LABEL_152:
            v12 = CBasicObjectSink::Return(a6, v63, 0);
LABEL_323:
            VariantClear(&pvarg);
            CFreeMe<void>::~CFreeMe<void>(&v116);
            goto LABEL_324;
          }
        }
      }
      VariantInit(&v137);
      if ( ((int (__fastcall *)(struct IWbemContext *, const wchar_t *, _QWORD, VARIANTARG *))a5->lpVtbl->GetValue)(
             a5,
             L"__GroupOperationId",
             0,
             &v137) >= 0 )
      {
        v56 = CWbemNamespace::IsLocalMachine(*((wchar_t **)this + 35));
        v57 = 0;
        if ( pvarg.vt == 8 )
          v57 = pvarg.bstrVal;
        CPublishWMIOperationEvent::PublishRepUpdate(
          v137.cyVal.Lo,
          v57,
          v8,
          a5,
          *((_DWORD *)this + 76),
          *((unsigned __int16 **)this + 36),
          *((_QWORD *)this + 37),
          v56);
      }
      v47 = CRepository::PutObject(
              *((struct IWmiDbSession **)this + 5),
              *((struct IWmiDbHandle **)this + 8),
              v46,
              v115,
              v8);
      Namespace = v47;
      if ( v126 )
        (*(void (__fastcall **)(__int64, __int64, _QWORD, struct IWbemContext *, _QWORD, _QWORD, const unsigned __int16 *, struct IWbemClassObject *, struct IWbemClassObject *))(*(_QWORD *)v126 + 32LL))(
          v126,
          1,
          v47,
          a5,
          0,
          *((_QWORD *)this + 12),
          v132[0],
          v115,
          v117);
      CWin32DefaultArena::WbemMemFree(v117);
      if ( Namespace >= 0 )
      {
        v52 = VariantClear(&v137);
        if ( v52 < 0 )
          _com_issue_error(v52);
        goto LABEL_47;
      }
      v48 = GetMemLogObject();
      CMemoryLog::Write(v48, Namespace);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          162,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          (unsigned int)Namespace);
      }
      v49 = CBasicObjectSink::Return(a6, Namespace, 0);
      v50 = VariantClear(&v137);
      if ( v50 < 0 )
        _com_issue_error(v50);
    }
    VariantClear(&pvarg);
    if ( v25 )
      LocalFree(v25);
LABEL_98:
    CVar::~CVar((CVar *)v125);
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v114 = 0;
    if ( !v122[0] )
      v123(*v124);
    if ( v15 )
      ((void (__fastcall *)(struct IWbemClassObject *))v15->lpVtbl->Release)(v15);
    v43 = v49;
    goto LABEL_70;
  }
  Namespace = CWbemNamespace::CreateNamespace(this, (struct CWbemInstance *)v115, hMem, a5, v120);
  if ( Namespace < 0 )
  {
    v64 = GetMemLogObject();
    CMemoryLog::Write(v64, Namespace);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        158,
        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
        (unsigned int)Namespace);
    }
    v63 = Namespace;
    goto LABEL_152;
  }
LABEL_47:
  v37 = (OLECHAR *)((__int64 (__fastcall *)(struct IWbemClassObject *, _QWORD))v115->lpVtbl[4].BeginMethodEnumeration)(
                     v115,
                     0);
  v38 = SysAllocString(v37);
  CWin32DefaultArena::WbemMemFree(v37);
  v39 = (*(__int64 (__fastcall **)(struct CBasicObjectSink *, _QWORD, _QWORD, OLECHAR *, _QWORD))(*(_QWORD *)a6 + 32LL))(
          a6,
          0,
          (unsigned int)Namespace,
          v38,
          0);
  SysFreeString(v38);
  VariantClear(&pvarg);
  if ( v25 )
    LocalFree(v25);
  CVar::~CVar((CVar *)v125);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  v114 = 0;
  if ( !v122[0] )
    v123(*v124);
  if ( v15 )
    ((void (__fastcall *)(struct IWbemClassObject *))v15->lpVtbl->Release)(v15);
  v134 = 0;
  return v39;
}

```

## disassembly

```asm
0x180049d34  mov     [rsp-8+arg_18], r9d
0x180049d39  push    rbp
0x180049d3a  push    rbx
0x180049d3b  push    rsi
0x180049d3c  push    rdi
0x180049d3d  push    r12
0x180049d3f  push    r13
0x180049d41  push    r14
0x180049d43  push    r15
0x180049d45  lea     rbp, [rsp-0A8h]
0x180049d4d  sub     rsp, 1A8h
0x180049d54  mov     r13d, r9d
0x180049d57  mov     rdi, r8
0x180049d5a  mov     rsi, rdx
0x180049d5d  mov     r15, rcx
0x180049d60  lea     r14, WPP_GLOBAL_Control
0x180049d67  mov     ebx, 1
0x180049d6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180049d73  cmp     rcx, r14
0x180049d76  jz      short loc_180049D81
0x180049d78  test    [rcx+1Ch], bl
0x180049d7b  jnz     loc_18004AA50
0x180049d81  mov     [rbp+0E0h+var_148], 0
0x180049d88  bt      r13d, 1Dh
0x180049d8d  jb      loc_18004AA7C
0x180049d93  mov     rcx, rdi
0x180049d96  call    cs:__imp_?IsAbstract@CWbemClass@@QEAAHXZ; CWbemClass::IsAbstract(void)
0x180049d9c  test    eax, eax
0x180049d9e  jnz     loc_18004AB1D
0x180049da4  mov     rcx, rdi
0x180049da7  call    cs:__imp_?IsAmendment@CWbemClass@@QEAAHXZ; CWbemClass::IsAmendment(void)
0x180049dad  test    eax, eax
0x180049daf  jnz     loc_18004AB1D
0x180049db5  mov     rax, [rdi]
0x180049db8  mov     rcx, rdi
0x180049dbb  mov     rax, [rax+408h]
0x180049dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049dc7  test    eax, eax
0x180049dc9  jz      loc_18004AB1D
0x180049dcf  mov     r14d, ebx
0x180049dd2  mov     [rsp+1E0h+var_168], ebx
0x180049dd6  mov     rcx, rdi
0x180049dd9  call    cs:__imp_?IsDynamic@CWbemClass@@QEAAHXZ; CWbemClass::IsDynamic(void)
0x180049ddf  mov     r12, [rbp+0E0h+arg_28]
0x180049de6  test    eax, eax
0x180049de8  jnz     loc_18004A785
0x180049dee  mov     [rsp+1E0h+var_180], 0
0x180049df7  lea     r8, [rsp+1E0h+var_180]
0x180049dfc  mov     rdx, rdi
0x180049dff  mov     rcx, rsi
0x180049e02  call    cs:__imp_?ConvertToClass@CWbemInstance@@QEAAJPEAVCWbemClass@@PEAPEAV1@@Z; CWbemInstance::ConvertToClass(CWbemClass *,CWbemInstance * *)
0x180049e08  mov     ebx, eax
0x180049e0a  test    eax, eax
0x180049e0c  js      loc_18004AB24
0x180049e12  mov     rbx, [rsp+1E0h+var_180]
0x180049e17  test    rbx, rbx
0x180049e1a  jz      loc_18004AB9A
0x180049e20  mov     [rbp+0E0h+var_B8], rbx
0x180049e24  mov     rcx, [rsp+1E0h+var_180]
0x180049e29  mov     rax, [rcx]
0x180049e2c  xor     edx, edx
0x180049e2e  mov     rax, [rax+410h]
0x180049e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049e3a  mov     [rbp+0E0h+var_C0], rax
0x180049e3e  lea     r8, [rbp+0E0h+var_C0]
0x180049e42  lea     rcx, [rbp+0E0h+var_138]
0x180049e46  call    ??$MakeGuard@P6AXPEAG@ZV?$RefHolder@PEAG@@@@YA?AV?$ScopeGuardImpl1@P6AXPEAG@ZV?$RefHolder@PEAG@@@@P6AXPEAG@ZV?$RefHolder@PEAG@@@Z; MakeGuard<void (*)(ushort *),RefHolder<ushort *>>(void (*)(ushort *),RefHolder<ushort *>)
0x180049e4b  nop
0x180049e4c  mov     rcx, rdi
0x180049e4f  call    cs:__imp_?IsDynamic@CWbemClass@@QEAAHXZ; CWbemClass::IsDynamic(void)
0x180049e55  test    eax, eax
0x180049e57  jnz     loc_18004A6BA
0x180049e5d  mov     rcx, [rsp+1E0h+var_180]
0x180049e62  call    cs:__imp_?PlugKeyHoles@CWbemInstance@@QEAAJXZ; CWbemInstance::PlugKeyHoles(void)
0x180049e68  mov     esi, eax
0x180049e6a  test    eax, eax
0x180049e6c  js      loc_18004ABDD
0x180049e72  mov     [rsp+1E0h+var_190], 0
0x180049e77  lea     rdx, [rsp+1E0h+var_190]; bool *
0x180049e7c  mov     rcx, [rsp+1E0h+var_180]; struct CWbemObject *
0x180049e81  call    ?IsDerivedFromSystem@@YAJAEAVCWbemObject@@PEA_N@Z; IsDerivedFromSystem(CWbemObject &,bool *)
0x180049e86  mov     esi, eax
0x180049e88  test    eax, eax
0x180049e8a  js      loc_18004AC5C
0x180049e90  lea     rdx, [r15+0D8h]; struct CNtSecurityDescriptor *
0x180049e97  mov     rax, [rbp+0E0h+var_C0]
0x180049e9b  mov     byte ptr [rsp+1E0h+var_1B0], 1; bool
0x180049ea0  lea     r9, aWritePutinstan; "Write (PutInstance)"
0x180049ea7  mov     rcx, r15; this
0x180049eaa  mov     [rsp+1E0h+var_1C0], rax; unsigned __int16 *
0x180049eaf  cmp     [rsp+1E0h+var_190], 0
0x180049eb4  jz      loc_18004A407
0x180049eba  mov     r8d, 4; unsigned int
0x180049ec0  call    ?InnerAllowedWithSD@CWbemNamespace@@QEAA_NPEAVCNtSecurityDescriptor@@KPEBG1_N2@Z; CWbemNamespace::InnerAllowedWithSD(CNtSecurityDescriptor *,ulong,ushort const *,ushort const *,bool,bool)
0x180049ec5  test    al, al
0x180049ec7  jz      loc_18004AC8E
0x180049ecd  mov     [rbp+0E0h+var_100], 0
0x180049ed5  mov     rcx, [r15+100h]
0x180049edc  mov     rax, [rcx]
0x180049edf  lea     rdx, [rbp+0E0h+var_100]
0x180049ee3  mov     rax, [rax+0E0h]
0x180049eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049eef  mov     edi, eax
0x180049ef1  test    eax, eax
0x180049ef3  js      loc_18004AD42
0x180049ef9  mov     rdi, [rbp+0E0h+var_100]
0x180049efd  mov     [rsp+1E0h+var_188], rdi
0x180049f02  lea     rcx, [rbp+0E0h+var_120]
0x180049f06  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x180049f0c  nop
0x180049f0d  mov     rcx, [rsp+1E0h+var_180]
0x180049f12  mov     rax, [rcx]
0x180049f15  lea     rdx, [rbp+0E0h+var_120]
0x180049f19  mov     rax, [rax+448h]
0x180049f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049f25  test    eax, eax
0x180049f27  js      loc_18004AD83
0x180049f2d  lea     rcx, [rbp+0E0h+var_120]
0x180049f31  call    cs:__imp_?GetLPWSTR@CVar@@QEAAPEAGXZ; CVar::GetLPWSTR(void)
0x180049f37  mov     [rbp+0E0h+var_D0], rax
0x180049f3b  lea     rdx, aNamespace_1; "__NAMESPACE"
0x180049f42  mov     rcx, rax; unsigned __int16 *
0x180049f45  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x180049f4a  test    eax, eax
0x180049f4c  jnz     short loc_180049F95
0x180049f4e  lea     rax, [r15+28h]
0x180049f52  mov     [rbp+0E0h+var_140], rax
0x180049f56  mov     rdx, [rsp+1E0h+var_180]; struct CWbemInstance *
0x180049f5b  call    ?MUILocaleUpdateNSInstance@CWbemNamespace@@IEAAJPEAVCWbemInstance@@@Z; CWbemNamespace::MUILocaleUpdateNSInstance(CWbemInstance *)
0x180049f60  mov     esi, eax
0x180049f62  test    eax, eax
0x180049f64  js      loc_18004AE03
0x180049f6a  mov     [rbp+0E0h+hMem], 0
0x180049f72  lea     r8, [rbp+0E0h+hMem]; void **
0x180049f76  mov     rdx, [rsp+1E0h+var_180]; struct CWbemInstance *
0x180049f7b  call    ?GetNamespaceSecurityFromQualifier@CWbemNamespace@@IEAAJPEAVCWbemInstance@@PEAPEAX@Z; CWbemNamespace::GetNamespaceSecurityFromQualifier(CWbemInstance *,void * *)
0x180049f80  mov     esi, eax
0x180049f82  test    eax, eax
0x180049f84  js      loc_18004AE5F
0x180049f8a  mov     [rsp+1E0h+var_190], 1
0x180049f8f  mov     r14, [rbp+0E0h+hMem]
0x180049f93  jmp     short loc_180049FCA
0x180049f95  lea     rcx, [rbp+0E0h+var_120]
0x180049f99  call    cs:__imp_?GetLPWSTR@CVar@@QEAAPEAGXZ; CVar::GetLPWSTR(void)
0x180049f9f  lea     r14, [r15+28h]
0x180049fa3  mov     [rbp+0E0h+var_140], r14
0x180049fa7  mov     r9, rax; unsigned __int16 *
0x180049faa  mov     rdx, [r15+38h]; struct IWmiDbHandle *
0x180049fae  mov     rcx, [r14]; struct IWmiDbSession *
0x180049fb1  call    ?InheritsFrom@CRepository@@SAJPEAUIWmiDbSession@@PEAUIWmiDbHandle@@PEBG2@Z; CRepository::InheritsFrom(IWmiDbSession *,IWmiDbHandle *,ushort const *,ushort const *)
0x180049fb6  test    eax, eax
0x180049fb8  jz      loc_18004A736
0x180049fbe  mov     [rsp+1E0h+var_190], 0
0x180049fc3  xor     r14d, r14d
0x180049fc6  mov     [rbp+0E0h+hMem], r14
0x180049fca  mov     [rsp+1E0h+var_178], r14
0x180049fcf  lea     rcx, [rbp+0E0h+pvarg]; pvarg
0x180049fd3  call    cs:__imp_VariantInit
0x180049fd9  nop
0x180049fda  mov     rcx, [rsp+1E0h+var_180]
0x180049fdf  mov     rax, [rcx]
0x180049fe2  mov     [rsp+1E0h+var_1B8], 0; bool
0x180049feb  mov     [rsp+1E0h+var_1C0], 0
0x180049ff4  lea     r9, [rbp+0E0h+pvarg]
0x180049ff8  xor     r8d, r8d
0x180049ffb  lea     rdx, aRelpath_0; "__RELPATH"
0x18004a002  mov     rax, [rax+20h]
0x18004a006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a00b  mov     esi, eax
0x18004a00d  test    eax, eax
0x18004a00f  js      loc_18004AEA0
0x18004a015  mov     eax, 8
0x18004a01a  cmp     word ptr [rbp+0E0h+pvarg], ax
0x18004a01e  jnz     loc_18004AEE6
0x18004a024  mov     [rbp+0E0h+var_F0], 0
0x18004a02c  lea     rax, [rbp+0E0h+var_F0]
0x18004a030  mov     [rsp+1E0h+var_1C0], rax; struct IWbemClassObject **
0x18004a035  xor     r9d, r9d; unsigned int
0x18004a038  mov     r8, qword ptr [rbp+0E0h+pvarg+8]; unsigned __int16 *
0x18004a03c  mov     rdx, [r15+40h]; struct IWmiDbHandle *
0x18004a040  mov     rcx, [rbp+0E0h+var_140]
0x18004a044  mov     rcx, [rcx]; struct IWmiDbSession *
0x18004a047  call    ?GetObjectW@CRepository@@SAJPEAUIWmiDbSession@@PEAUIWmiDbHandle@@PEBGKPEAPEAUIWbemClassObject@@@Z; CRepository::GetObjectW(IWmiDbSession *,IWmiDbHandle *,ushort const *,ulong,IWbemClassObject * *)
0x18004a04c  mov     esi, eax
0x18004a04e  xor     edx, edx
0x18004a050  test    eax, eax
0x18004a052  js      loc_18004A462
0x18004a058  mov     rsi, [rbp+0E0h+var_F0]
0x18004a05c  mov     [rsp+1E0h+var_170], rsi
0x18004a061  mov     eax, r13d
0x18004a064  and     al, 3
0x18004a066  cmp     al, 2
0x18004a068  jz      loc_18004B0F9
0x18004a06e  mov     [rbp+0E0h+var_140], rdx
0x18004a072  lea     r8, [rbp+0E0h+var_140]
0x18004a076  lea     rcx, [rbp+0E0h+var_E8]
0x18004a07a  call    ??$MakeGuard@P6AXPEAVCWbemNamespace@@@ZV?$RefHolder@PEAVCWbemNamespace@@@@@@YA?AV?$ScopeGuardImpl1@P6AXPEAVCWbemNamespace@@@ZV?$RefHolder@PEAVCWbemNamespace@@@@@@P6AXPEAVCWbemNamespace@@@ZV?$RefHolder@PEAVCWbemNamespace@@@@@Z; MakeGuard<void (*)(CWbemNamespace *),RefHolder<CWbemNamespace *>>(void (*)(CWbemNamespace *),RefHolder<CWbemNamespace *>)
0x18004a07f  nop
0x18004a080  cmp     [rsp+1E0h+var_190], dl
0x18004a084  jnz     loc_18004A862
0x18004a08a  bt      r13d, 11h
0x18004a08f  jb      loc_18004B2FB
0x18004a095  mov     rdx, [rsp+1E0h+var_180]; struct IWbemClassObject *
0x18004a09a  mov     rcx, r15; this
0x18004a09d  call    ?DecorateObject@CWbemNamespace@@QEAAJPEAUIWbemClassObject@@@Z; CWbemNamespace::DecorateObject(IWbemClassObject *)
0x18004a0a2  mov     [rbp+0E0h+arg_18], eax
0x18004a0a8  test    eax, eax
0x18004a0aa  js      loc_18004B399
0x18004a0b0  mov     rcx, [rbp+0E0h+var_100]
0x18004a0b4  test    rcx, rcx
0x18004a0b7  jz      short loc_18004A10A
0x18004a0b9  mov     rax, [rcx]
0x18004a0bc  mov     r10, [rax+18h]
0x18004a0c0  mov     rax, [rsp+1E0h+var_180]
0x18004a0c5  mov     [rsp+1E0h+var_1A8], rax
0x18004a0ca  mov     rax, [rbp+0E0h+var_D0]
0x18004a0ce  mov     [rsp+1E0h+var_1B0], rax
0x18004a0d3  mov     rax, [r15+60h]
0x18004a0d7  mov     [rsp+1E0h+var_1B8], rax
0x18004a0dc  mov     [rsp+1E0h+var_1C0], 0
0x18004a0e5  mov     r9, [rbp+0E0h+arg_20]
0x18004a0ec  mov     r8d, r13d
0x18004a0ef  mov     edx, 1
0x18004a0f4  mov     rax, r10
0x18004a0f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a0fc  mov     [rbp+0E0h+arg_18], eax
0x18004a102  test    eax, eax
0x18004a104  js      loc_18004B3FF
0x18004a10a  lea     rcx, [rbp+0E0h+var_B0]; pvarg
0x18004a10e  call    cs:__imp_VariantInit
0x18004a114  nop
0x18004a115  mov     rcx, [rbp+0E0h+arg_20]
0x18004a11c  mov     rax, [rcx]
0x18004a11f  lea     r9, [rbp+0E0h+var_B0]
0x18004a123  xor     r8d, r8d
0x18004a126  lea     rdx, aGroupoperation; "__GroupOperationId"
0x18004a12d  mov     rax, [rax+48h]
0x18004a131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a136  test    eax, eax
0x18004a138  js      short loc_18004A191
0x18004a13a  mov     rcx, [r15+118h]; String2
0x18004a141  call    ?IsLocalMachine@CWbemNamespace@@KAHPEBG@Z; CWbemNamespace::IsLocalMachine(ushort const *)
0x18004a146  mov     rcx, [r15+128h]
0x18004a14d  mov     r8, [r15+120h]
0x18004a154  mov     r9d, [r15+130h]
0x18004a15b  xor     edx, edx
0x18004a15d  lea     r10d, [rdx+8]
0x18004a161  cmp     word ptr [rbp+0E0h+pvarg], r10w
0x18004a166  cmovz   rdx, qword ptr [rbp+0E0h+pvarg+8]
0x18004a16b  mov     dword ptr [rsp+1E0h+var_1A8], eax
0x18004a16f  mov     [rsp+1E0h+var_1B0], rcx
0x18004a174  mov     [rsp+1E0h+var_1B8], r8
0x18004a179  mov     dword ptr [rsp+1E0h+var_1C0], r9d
0x18004a17e  mov     r9, [rbp+0E0h+arg_20]
0x18004a185  mov     r8d, r13d
0x18004a188  mov     ecx, dword ptr [rbp+0E0h+var_B0+8]
0x18004a18b  call    cs:__imp_?PublishRepUpdate@CPublishWMIOperationEvent@@SAJKPEAGKPEAUIWbemContext@@K0_KH@Z; CPublishWMIOperationEvent::PublishRepUpdate(ulong,ushort *,ulong,IWbemContext *,ulong,ushort *,unsigned __int64,int)
0x18004a191  mov     dword ptr [rsp+1E0h+var_1C0], r13d; unsigned int
0x18004a196  mov     r9, [rsp+1E0h+var_180]; void *
0x18004a19b  mov     rdx, [r15+40h]; struct IWmiDbHandle *
0x18004a19f  mov     rcx, [r15+28h]; struct IWmiDbSession *
0x18004a1a3  call    ?PutObject@CRepository@@SAJPEAUIWmiDbSession@@PEAUIWmiDbHandle@@AEBU_GUID@@PEAXK@Z; CRepository::PutObject(IWmiDbSession *,IWmiDbHandle *,_GUID const &,void *,ulong)
0x18004a1a8  mov     r13d, eax
0x18004a1ab  mov     rcx, [rbp+0E0h+var_100]
0x18004a1af  test    rcx, rcx
0x18004a1b2  jz      short loc_18004A200
0x18004a1b4  mov     rax, [rcx]
0x18004a1b7  mov     r10, [rax+20h]
0x18004a1bb  mov     rax, [rbp+0E0h+var_F0]
0x18004a1bf  mov     [rsp+1E0h+var_1A0], rax
0x18004a1c4  mov     rax, [rsp+1E0h+var_180]
0x18004a1c9  mov     [rsp+1E0h+var_1A8], rax
0x18004a1ce  mov     rax, [rbp+0E0h+var_D0]
0x18004a1d2  mov     [rsp+1E0h+var_1B0], rax
0x18004a1d7  mov     rax, [r15+60h]
0x18004a1db  mov     [rsp+1E0h+var_1B8], rax
0x18004a1e0  mov     [rsp+1E0h+var_1C0], 0
0x18004a1e9  mov     r9, [rbp+0E0h+arg_20]
0x18004a1f0  mov     r8d, r13d
0x18004a1f3  mov     edx, 1
0x18004a1f8  mov     rax, r10
0x18004a1fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a200  test    r13d, r13d
0x18004a203  js      loc_18004B446
0x18004a209  mov     rdx, [rbp+0E0h+hMem]
0x18004a20d  test    rdx, rdx
0x18004a210  jnz     loc_18004B4AE
0x18004a216  lea     rcx, [rbp+0E0h+var_B0]; pvarg
0x18004a21a  call    cs:__imp_VariantClear
0x18004a220  test    eax, eax
0x18004a222  js      loc_18004A6B2
0x18004a228  cmp     [rbp+0E0h+var_E8], 0
0x18004a22c  jnz     short loc_18004A23F
0x18004a22e  mov     rcx, [rbp+0E0h+var_D8]
0x18004a232  mov     rcx, [rcx]
0x18004a235  mov     rax, [rbp+0E0h+var_E0]
0x18004a239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a23e  nop
0x18004a23f  test    rsi, rsi
0x18004a242  jz      short loc_18004A253
  ... truncated ...
```
