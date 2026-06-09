# TaskFolderImpl::Register(ushort *,long,tagVARIANT &,tagVARIANT &,_TASK_LOGON_TYPE,tagVARIANT &,IRegisteredTask * *,ITaskDefinition *,ushort const *)

- ea: `0x18000e4d0`
- end: `0x18000f36d`
- name: `?Register@TaskFolderImpl@@AEAAJPEAGJAEAUtagVARIANT@@1W4_TASK_LOGON_TYPE@@1PEAPEAUIRegisteredTask@@PEAUITaskDefinition@@PEBG@Z`
- size: `3741`
- prototype: `__int64 __fastcall(TaskFolderImpl *this, unsigned __int16 *, unsigned int, struct tagVARIANT *, struct tagVARIANT *pvarSrc, enum _TASK_LOGON_TYPE, struct tagVARIANT *pvargSrc, struct IRegisteredTask **, struct ITaskDefinition *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18000e410`
- `0x18000e470`

## callees

- `0x1800017f0`
- `0x180004fd0`
- `0x180007aa0`
- `0x18000d67c`
- `0x18000dd10`
- `0x18000e4d0`
- `0x18000f374`
- `0x18000fca0`
- `0x180010220`
- `0x18001edb0`
- `0x180033e34`
- `0x1800367c4`
- `0x180039524`
- `0x180054010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000f293`
- `msvcrt!wcsrchr` at `0x18000f293`
- `msvcrt!wcschr` at `0x18000e608`
- `msvcrt!wcschr` at `0x18000eac0`
- `msvcrt!wcschr` at `0x18000e608`
- `msvcrt!wcschr` at `0x18000eac0`
- `msvcrt!free` at `0x18000e7df`
- `msvcrt!free` at `0x18000e87b`
- `msvcrt!free` at `0x18000e915`
- `msvcrt!free` at `0x18000e9af`
- `msvcrt!free` at `0x18000ea52`
- `msvcrt!free` at `0x18000ed21`
- `msvcrt!free` at `0x18000edc8`
- `msvcrt!free` at `0x18000ee86`
- `msvcrt!free` at `0x18000f13e`
- `msvcrt!free` at `0x18000f2fe`
- `msvcrt!free` at `0x18000e7df`
- `msvcrt!free` at `0x18000e87b`
- `msvcrt!free` at `0x18000e915`
- `msvcrt!free` at `0x18000e9af`
- `msvcrt!free` at `0x18000ea52`
- `msvcrt!free` at `0x18000ed21`
- `msvcrt!free` at `0x18000edc8`
- `msvcrt!free` at `0x18000ee86`
- `msvcrt!free` at `0x18000f13e`
- `msvcrt!free` at `0x18000f2fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ec1a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ec1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ebea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ebea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e84a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e868`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e8e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e902`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e97e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e99c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ea19`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ea3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ece8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ed0a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ed97`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000edb5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ee4d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ee6f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f105`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f127`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f2d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f2f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e84a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e868`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e8e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e902`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e97e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e99c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ea19`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ea3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ece8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ed0a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ed97`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000edb5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ee4d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ee6f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f105`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f127`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f2d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f2f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e83c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e85a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e8d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e8f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e970`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e98e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ea0b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ea2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ecda`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ecfc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ed89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eda7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ee3f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ee61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f0f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f119`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f2c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f2e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e83c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e85a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e8d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e8f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e970`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e98e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ea0b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ea2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ecda`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ecfc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ed89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eda7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ee3f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ee61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f0f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f119`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f2c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f2e2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e62b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e752`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e7e9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e830`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e885`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e8ca`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e91f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e964`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e9b9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e9ff`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ea5c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eae2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ecce`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ed2b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ed7d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000edd2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ee33`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ee90`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f02b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f0eb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f148`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f2b8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f308`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e62b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e752`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e7e9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e830`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e885`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e8ca`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e91f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e964`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e9b9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e9ff`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ea5c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eae2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ecce`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ed2b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ed7d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000edd2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ee33`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ee90`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f02b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f0eb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f148`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f2b8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f308`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e71b`
- `OLEAUT32!__imp_SysStringLen` at `0x18000f08a`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e71b`
- `OLEAUT32!__imp_SysStringLen` at `0x18000f08a`
- `OLEAUT32!__imp_VariantClear` at `0x18000e685`
- `OLEAUT32!__imp_VariantClear` at `0x18000e6b5`
- `OLEAUT32!__imp_VariantClear` at `0x18000e6c4`
- `OLEAUT32!__imp_VariantClear` at `0x18000e6d3`
- `OLEAUT32!__imp_VariantClear` at `0x18000e7f5`
- `OLEAUT32!__imp_VariantClear` at `0x18000e804`
- `OLEAUT32!__imp_VariantClear` at `0x18000e813`
- `OLEAUT32!__imp_VariantClear` at `0x18000e891`
- `OLEAUT32!__imp_VariantClear` at `0x18000e8a0`
- `OLEAUT32!__imp_VariantClear` at `0x18000e8af`
- `OLEAUT32!__imp_VariantClear` at `0x18000e92b`
- `OLEAUT32!__imp_VariantClear` at `0x18000e93a`
- `OLEAUT32!__imp_VariantClear` at `0x18000e949`
- `OLEAUT32!__imp_VariantClear` at `0x18000e9c5`
- `OLEAUT32!__imp_VariantClear` at `0x18000e9d4`
- `OLEAUT32!__imp_VariantClear` at `0x18000e9e3`
- `OLEAUT32!__imp_VariantClear` at `0x18000ea68`
- `OLEAUT32!__imp_VariantClear` at `0x18000ea77`
- `OLEAUT32!__imp_VariantClear` at `0x18000ea86`
- `OLEAUT32!__imp_VariantClear` at `0x18000ed37`
- `OLEAUT32!__imp_VariantClear` at `0x18000ed46`
- `OLEAUT32!__imp_VariantClear` at `0x18000ed55`
- `OLEAUT32!__imp_VariantClear` at `0x18000edde`
- `OLEAUT32!__imp_VariantClear` at `0x18000eded`
- `OLEAUT32!__imp_VariantClear` at `0x18000edfc`
- `OLEAUT32!__imp_VariantClear` at `0x18000ee9c`
- `OLEAUT32!__imp_VariantClear` at `0x18000eeab`
- `OLEAUT32!__imp_VariantClear` at `0x18000eeba`
- `OLEAUT32!__imp_VariantClear` at `0x18000ef28`
- `OLEAUT32!__imp_VariantClear` at `0x18000ef58`
- `OLEAUT32!__imp_VariantClear` at `0x18000ef67`
- `OLEAUT32!__imp_VariantClear` at `0x18000ef76`
- `OLEAUT32!__imp_VariantClear` at `0x18000ef91`
- `OLEAUT32!__imp_VariantClear` at `0x18000efbe`
- `OLEAUT32!__imp_VariantClear` at `0x18000efcd`
- `OLEAUT32!__imp_VariantClear` at `0x18000efdc`
- `OLEAUT32!__imp_VariantClear` at `0x18000f037`
- `OLEAUT32!__imp_VariantClear` at `0x18000f046`
- `OLEAUT32!__imp_VariantClear` at `0x18000f055`
- `OLEAUT32!__imp_VariantClear` at `0x18000f154`
- `OLEAUT32!__imp_VariantClear` at `0x18000f163`
- `OLEAUT32!__imp_VariantClear` at `0x18000f172`
- `OLEAUT32!__imp_VariantClear` at `0x18000f314`
- `OLEAUT32!__imp_VariantClear` at `0x18000f323`
- `OLEAUT32!__imp_VariantClear` at `0x18000f332`
- `OLEAUT32!__imp_VariantClear` at `0x18000e685`
- `OLEAUT32!__imp_VariantClear` at `0x18000e6b5`
- `OLEAUT32!__imp_VariantClear` at `0x18000e6c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall TaskFolderImpl::Register(
        TaskFolderImpl *this,
        unsigned __int16 *a2,
        unsigned int a3,
        struct tagVARIANT *a4,
        struct tagVARIANT *pvarSrc,
        enum _TASK_LOGON_TYPE a6,
        struct tagVARIANT *pvargSrc,
        struct IRegisteredTask **a8,
        struct ITaskDefinition *a9,
        const unsigned __int16 *a10)
{
  HRESULT v13; // eax
  HRESULT v14; // eax
  HRESULT v15; // eax
  const unsigned __int16 *v16; // rdx
  VARTYPE vt; // ax
  VARTYPE v18; // ax
  VARTYPE v19; // ax
  OLECHAR *v20; // rdi
  __int64 v21; // rcx
  __int64 v22; // rbx
  OLECHAR *v23; // rax
  HRESULT v24; // edi
  int v25; // eax
  OLECHAR *v26; // rbx
  OLECHAR *v27; // rdx
  OLECHAR *v28; // rbx
  HRESULT v29; // eax
  unsigned __int16 *v30; // rbx
  _WORD *v31; // rcx
  unsigned __int16 *v32; // rdx
  HANDLE ProcessHeap; // rax
  HANDLE v35; // rax
  HANDLE v36; // rax
  HANDLE v37; // rax
  HANDLE v38; // rax
  HANDLE v39; // rax
  HANDLE v40; // rax
  HANDLE v41; // rax
  __int64 v42; // rbx
  OLECHAR *v43; // rax
  OLECHAR *v44; // rsi
  unsigned int v45; // ecx
  HRESULT (__stdcall *get_Settings)(ITaskDefinition *, ITaskSettings **); // rax
  int XmlText; // r14d
  const unsigned __int16 *v48; // r14
  const unsigned __int16 *bstrVal; // rcx
  int v50; // r14d
  void *v51; // rsi
  HANDLE v52; // rax
  unsigned __int16 *v53; // rsi
  HANDLE v54; // rax
  HANDLE v55; // rax
  HANDLE v56; // rax
  int NewObject; // r15d
  void *v58; // rsi
  HANDLE v59; // rax
  unsigned __int16 *v60; // rsi
  HANDLE v61; // rax
  void *v62; // rsi
  HANDLE v63; // rax
  unsigned __int16 *v64; // rsi
  HANDLE v65; // rax
  wchar_t *v66; // rax
  HANDLE v67; // rax
  HANDLE v68; // rax
  unsigned __int16 *v69; // [rsp+20h] [rbp-108h]
  unsigned int v70; // [rsp+30h] [rbp-F8h]
  LPVOID lpMem; // [rsp+58h] [rbp-D0h] BYREF
  unsigned __int16 *v72; // [rsp+60h] [rbp-C8h] BYREF
  BSTR pbstrResult; // [rsp+68h] [rbp-C0h] BYREF
  __int64 v74; // [rsp+70h] [rbp-B8h] BYREF
  VARIANTARG v75; // [rsp+78h] [rbp-B0h] BYREF
  VARIANTARG pvargDest; // [rsp+90h] [rbp-98h] BYREF
  VARIANTARG pvarg; // [rsp+A8h] [rbp-80h] BYREF
  BSTR bstrLeft; // [rsp+C0h] [rbp-68h] BYREF
  unsigned __int16 *v79; // [rsp+C8h] [rbp-60h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+D0h] [rbp-58h]
  __int128 v81; // [rsp+D8h] [rbp-50h] BYREF
  __int64 v82; // [rsp+E8h] [rbp-40h]
  OLECHAR *v83; // [rsp+F0h] [rbp-38h]
  struct ITaskDefinition *v84; // [rsp+F8h] [rbp-30h]

  pvarg.vt = 0;
  v13 = VariantCopy(&pvarg, pvargSrc);
  if ( v13 < 0 )
  {
    pvarg.vt = 10;
    pvarg.lVal = v13;
    ATL::PrivateAtlThrow(v13);
  }
  pvargDest.vt = 0;
  v14 = VariantCopy(&pvargDest, a4);
  if ( v14 < 0 )
  {
    pvargDest.vt = 10;
    pvargDest.lVal = v14;
    ATL::PrivateAtlThrow(v14);
  }
  v75.vt = 0;
  v15 = VariantCopy(&v75, pvarSrc);
  if ( v15 < 0 )
  {
    v75.vt = 10;
    v75.lVal = v15;
    ATL::PrivateAtlThrow(v15);
  }
  vt = pvargSrc->vt;
  if ( pvargSrc->vt >= 2u )
  {
    if ( vt == 10 )
    {
      if ( pvargSrc->lVal == -2147352572 )
        goto LABEL_5;
    }
    else if ( vt == 8 )
    {
      goto LABEL_5;
    }
    VariantClear(&pvarg);
    v24 = VariantChangeType(&pvarg, pvargSrc, 0, 8u);
    if ( v24 < 0 )
      goto LABEL_93;
  }
LABEL_5:
  v18 = a4->vt;
  if ( a4->vt < 2u )
    goto LABEL_6;
  if ( v18 == 10 )
  {
    if ( a4->lVal == -2147352572 )
      goto LABEL_6;
  }
  else if ( v18 == 8 )
  {
    goto LABEL_6;
  }
  VariantClear(&pvargDest);
  v24 = VariantChangeType(&pvargDest, a4, 0, 8u);
  if ( v24 < 0 )
    goto LABEL_93;
LABEL_6:
  v19 = pvarSrc->vt;
  if ( pvarSrc->vt < 2u )
    goto LABEL_7;
  if ( v19 == 10 )
  {
    if ( pvarSrc->lVal == -2147352572 )
      goto LABEL_7;
  }
  else if ( v19 == 8 )
  {
    goto LABEL_7;
  }
  VariantClear(&v75);
  v24 = VariantChangeType(&v75, pvarSrc, 0, 8u);
  if ( v24 < 0 )
  {
LABEL_93:
    VariantClear(&v75);
    VariantClear(&pvargDest);
    VariantClear(&pvarg);
    return (unsigned int)v24;
  }
LABEL_7:
  v81 = 0;
  v82 = 0;
  v20 = 0;
  bstrLeft = 0;
  if ( pvargDest.vt < 2u
    || pvargDest.vt == 10 && pvargDest.lVal == -2147352572
    || pvargDest.vt == 8 && (!pvargDest.llVal || !*pvargDest.bstrVal)
    || pvargDest.vt != 8 )
  {
    if ( v75.vt >= 2u && (v75.vt != 10 || v75.lVal != -2147352572) && !IsEmptyString(&v75) )
    {
      SysFreeString(0);
      VariantClear(&v75);
      VariantClear(&pvargDest);
      VariantClear(&pvarg);
      return 2147943004LL;
    }
    LODWORD(v82) = v82 | 1;
    v21 = *((_QWORD *)this + 13);
    if ( !*(_QWORD *)(v21 + 256)
      || wcschr(*(const wchar_t **)(v21 + 248), 0x40u)
      || wcschr(*(const wchar_t **)(*((_QWORD *)this + 13) + 248LL), 0x5Cu) )
    {
      v22 = *((_QWORD *)this + 13);
      if ( *(_QWORD *)(v22 + 248) )
      {
        SysFreeString(0);
        v23 = ATL::CComBSTR::Copy((ATL::CComBSTR *)(v22 + 248));
        v20 = v23;
        bstrLeft = v23;
        if ( *(_QWORD *)(v22 + 248) )
        {
          if ( !v23 )
            ATL::PrivateAtlThrow(-2147024882);
        }
      }
    }
    else
    {
      v42 = *((_QWORD *)this + 13);
      if ( *(_QWORD *)(v42 + 256) )
      {
        SysFreeString(0);
        v43 = ATL::CComBSTR::Copy((ATL::CComBSTR *)(v42 + 256));
        bstrLeft = v43;
        if ( *(_QWORD *)(v42 + 256) )
        {
          if ( !v43 )
            ATL::PrivateAtlThrow(-2147024882);
        }
      }
      v25 = ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrLeft, v16);
      if ( v25 < 0 )
        ATL::PrivateAtlThrow(v25);
      v26 = *(OLECHAR **)(*((_QWORD *)this + 13) + 248LL);
      if ( SysStringLen(v26) )
      {
        pbstrResult = 0;
        v27 = v26;
        v28 = bstrLeft;
        v29 = VarBstrCat(bstrLeft, v27, &pbstrResult);
        if ( v29 < 0 )
          ATL::PrivateAtlThrow(v29);
        SysFreeString(v28);
        v20 = pbstrResult;
        bstrLeft = pbstrResult;
      }
      else
      {
        v20 = bstrLeft;
      }
    }
    *(_QWORD *)&v81 = v20;
  }
  else
  {
    *(_QWORD *)&v81 = pvargDest.llVal;
    if ( v75.vt == 8 )
      *((_QWORD *)&v81 + 1) = v75.llVal;
    else
      *((_QWORD *)&v81 + 1) = 0;
  }
  v30 = 0;
  v79 = 0;
  if ( a2 && !*a2 )
    a2 = 0;
  v31 = (_WORD *)*((_QWORD *)this + 14);
  if ( *v31 && (*v31 != 92 || v31[1]) )
  {
    if ( !a2
      || (v30 = (unsigned __int16 *)operator new(0x20Au),
          v79 = v30,
          (int)tsched::SafePathAppend((tsched *)v30, v32, *((_QWORD *)this + 14), a2, v69) < 0) )
    {
      if ( v30 )
        free(v30);
      SysFreeString(v20);
      VariantClear(&v75);
      VariantClear(&pvargDest);
      VariantClear(&pvarg);
      return 2147942487LL;
    }
  }
  else if ( a2 )
  {
    v30 = tsched::PathCopy((tsched *)a2, v16);
    v79 = v30;
  }
  v72 = 0;
  lpMem = 0;
  v44 = 0;
  v83 = 0;
  if ( !a9 )
  {
    v48 = a10;
    goto LABEL_65;
  }
  LODWORD(v74) = 2;
  pbstrResult = 0;
  v45 = 0;
  if ( *((_DWORD *)this + 20) )
    v45 = *((_DWORD *)this + 21);
  get_Settings = a9->lpVtbl->get_Settings;
  if ( v45 < 0x10002 )
  {
    LODWORD(v74) = 1;
    XmlText = ((__int64 (__fastcall *)(struct ITaskDefinition *, BSTR *))get_Settings)(a9, &pbstrResult);
    if ( XmlText < 0 )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&pbstrResult);
      SysFreeString(0);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMem);
      lpMem = 0;
      v35 = GetProcessHeap();
      HeapFree(v35, 0, v72);
      v72 = 0;
      if ( !v30 )
        goto LABEL_76;
    }
    else
    {
      XmlText = (*(__int64 (__fastcall **)(BSTR, _QWORD))(*(_QWORD *)pbstrResult + 288LL))(
                  pbstrResult,
                  (unsigned int)v74);
      if ( XmlText >= 0 )
        goto LABEL_56;
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&pbstrResult);
      SysFreeString(0);
      v36 = GetProcessHeap();
      HeapFree(v36, 0, lpMem);
      lpMem = 0;
      v37 = GetProcessHeap();
      HeapFree(v37, 0, v72);
      v72 = 0;
      if ( !v30 )
        goto LABEL_76;
    }
LABEL_75:
    free(v30);
    goto LABEL_76;
  }
  XmlText = ((__int64 (__fastcall *)(struct ITaskDefinition *, BSTR *))get_Settings)(a9, &pbstrResult);
  if ( XmlText < 0 )
  {
    if ( pbstrResult )
      (*(void (__fastcall **)(BSTR, _QWORD))(*(_QWORD *)pbstrResult + 16LL))(pbstrResult, *(_QWORD *)pbstrResult);
    SysFreeString(0);
    v55 = GetProcessHeap();
    HeapFree(v55, 0, lpMem);
    lpMem = 0;
    v56 = GetProcessHeap();
    HeapFree(v56, 0, v72);
    v72 = 0;
    if ( !v30 )
      goto LABEL_76;
    goto LABEL_75;
  }
  XmlText = (*(__int64 (__fastcall **)(BSTR, __int64 *))(*(_QWORD *)pbstrResult + 280LL))(pbstrResult, &v74);
  if ( XmlText < 0 )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&pbstrResult);
    SysFreeString(0);
    v38 = GetProcessHeap();
    HeapFree(v38, 0, lpMem);
    lpMem = 0;
    v39 = GetProcessHeap();
    HeapFree(v39, 0, v72);
    v72 = 0;
    if ( !v30 )
      goto LABEL_76;
    goto LABEL_75;
  }
LABEL_56:
  if ( (int)v74 < 2 )
  {
    if ( v30 )
    {
      v66 = wcsrchr(v30, 0x5Cu);
      if ( v66 )
      {
        if ( v66 != v30 )
        {
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&pbstrResult);
          SysFreeString(0);
          v67 = GetProcessHeap();
          HeapFree(v67, 0, lpMem);
          lpMem = 0;
          v68 = GetProcessHeap();
          HeapFree(v68, 0, v72);
          v72 = 0;
          free(v30);
          SysFreeString(v20);
          VariantClear(&v75);
          VariantClear(&pvargDest);
          VariantClear(&pvarg);
          return 2147942561LL;
        }
      }
    }
  }
  lpCriticalSection = (LPCRITICAL_SECTION)&a9[3];
  if ( a9 != (struct ITaskDefinition *)-16LL )
    EnterCriticalSection((LPCRITICAL_SECTION)&a9[3]);
  v84 = a9 + 2;
  XmlText = TaskDefinitionImpl::GenerateXmlText((TaskDefinitionImpl *)a9, 0);
  if ( XmlText >= 0 )
  {
    v44 = ATL::CComBSTR::Copy((ATL::CComBSTR *)&a9[14]);
    v83 = v44;
    if ( !SysStringLen((BSTR)a9[14].lpVtbl) || v44 )
      XmlText = 0;
    else
      XmlText = -2147024882;
  }
  if ( a9 != (struct ITaskDefinition *)-16LL )
    LeaveCriticalSection(lpCriticalSection);
  if ( XmlText < 0 )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&pbstrResult);
    SysFreeString(v44);
    v40 = GetProcessHeap();
    HeapFree(v40, 0, lpMem);
    lpMem = 0;
    v41 = GetProcessHeap();
    HeapFree(v41, 0, v72);
    v72 = 0;
    if ( v30 )
      goto LABEL_75;
LABEL_76:
    SysFreeString(v20);
    VariantClear(&v75);
    VariantClear(&pvargDest);
    VariantClear(&pvarg);
    return (unsigned int)XmlText;
  }
  v48 = v44;
  if ( pbstrResult )
    (*(void (__fastcall **)(BSTR))(*(_QWORD *)pbstrResult + 16LL))(pbstrResult);
LABEL_65:
  bstrVal = 0;
  if ( pvarg.vt == 8 )
    bstrVal = pvarg.bstrVal;
  v50 = UniSession::RegisterTask(
          (TaskFolderImpl *)((char *)this + 80),
          v30,
          v48,
          a3,
          bstrVal,
          a6,
          v70,
          (const struct _TASK_USER_CRED *)&v81,
          (struct RpcString *)&v72,
          (struct RpcXmlErrorInfo *)&lpMem);
  if ( v50 < 0 )
  {
    SetOleErrorInfo(&GUID_8cfac062_a080_4c15_9a88_aa7c2af80dfc, (const struct _TASK_XML_ERROR_INFO *)lpMem);
    SysFreeString(v44);
    v62 = lpMem;
    v63 = GetProcessHeap();
    HeapFree(v63, 0, v62);
    lpMem = 0;
    v64 = v72;
    v65 = GetProcessHeap();
    HeapFree(v65, 0, v64);
    v72 = 0;
    if ( !v30 )
      goto LABEL_71;
    goto LABEL_70;
  }
  if ( !a8 )
  {
LABEL_69:
    SysFreeString(v44);
    v51 = lpMem;
    v52 = GetProcessHeap();
    HeapFree(v52, 0, v51);
    lpMem = 0;
    v53 = v72;
    v54 = GetProcessHeap();
    HeapFree(v54, 0, v53);
    v72 = 0;
    if ( !v30 )
    {
LABEL_71:
      SysFreeString(v20);
      VariantClear(&v75);
      VariantClear(&pvargDest);
      VariantClear(&pvarg);
      return (unsigned int)v50;
    }
LABEL_70:
    free(v30);
    goto LABEL_71;
  }
  if ( (a3 & 1) != 0 )
  {
    *a8 = 0;
    goto LABEL_69;
  }
  NewObject = RegisteredTaskImpl::CreateNewObject((TaskFolderImpl *)((char *)this + 80), v72, 0, a8);
  if ( NewObject >= 0 )
    goto LABEL_69;
  SysFreeString(v44);
  v58 = lpMem;
  v59 = GetProcessHeap();
  HeapFree(v59, 0, v58);
  lpMem = 0;
  v60 = v72;
  v61 = GetProcessHeap();
  HeapFree(v61, 0, v60);
  v72 = 0;
  if ( v30 )
    free(v30);
  SysFreeString(v20);
  VariantClear(&v75);
  VariantClear(&pvargDest);
  VariantClear(&pvarg);
  return (unsigned int)NewObject;
}

```

## disassembly

```asm
0x18000e4d0  mov     r11, rsp
0x18000e4d3  mov     [r11+8], rbx
0x18000e4d7  mov     [r11+10h], rsi
0x18000e4db  mov     [r11+18h], r8d
0x18000e4df  push    rdi
0x18000e4e0  push    r12
0x18000e4e2  push    r13
0x18000e4e4  push    r14
0x18000e4e6  push    r15
0x18000e4e8  sub     rsp, 100h
0x18000e4ef  mov     r14, r9
0x18000e4f2  mov     rsi, rdx
0x18000e4f5  mov     r13, rcx
0x18000e4f8  mov     r12, [rsp+128h+arg_40]
0x18000e500  mov     [rsp+128h+var_D8], 0
0x18000e508  xor     eax, eax
0x18000e50a  mov     [r11-80h], ax
0x18000e50f  mov     rdi, [rsp+128h+pvargSrc]
0x18000e517  mov     rdx, rdi; pvargSrc
0x18000e51a  lea     rcx, [r11-80h]; pvargDest
0x18000e51e  call    cs:__imp_VariantCopy
0x18000e524  test    eax, eax
0x18000e526  js      loc_18000EA94
0x18000e52c  xor     eax, eax
0x18000e52e  mov     word ptr [rsp+128h+pvargDest], ax
0x18000e536  mov     rdx, r14; pvargSrc
0x18000e539  lea     rcx, [rsp+128h+pvargDest]; pvargDest
0x18000e541  call    cs:__imp_VariantCopy
0x18000e547  test    eax, eax
0x18000e549  js      loc_18000F1D2
0x18000e54f  xor     eax, eax
0x18000e551  mov     word ptr [rsp+128h+var_B0], ax
0x18000e556  mov     r15, [rsp+128h+pvarSrc]
0x18000e55e  mov     rdx, r15; pvargSrc
0x18000e561  lea     rcx, [rsp+128h+var_B0]; pvargDest
0x18000e566  call    cs:__imp_VariantCopy
0x18000e56c  test    eax, eax
0x18000e56e  js      loc_18000F1EE
0x18000e574  movzx   eax, word ptr [rdi]
0x18000e577  mov     ebx, 8
0x18000e57c  cmp     ax, 2
0x18000e580  jnb     loc_18000E66A
0x18000e586  movzx   eax, word ptr [r14]
0x18000e58a  cmp     ax, 2
0x18000e58e  jnb     loc_18000EF0D
0x18000e594  movzx   eax, word ptr [r15]
0x18000e598  cmp     ax, 2
0x18000e59c  jnb     loc_18000EFFE
0x18000e5a2  xorps   xmm0, xmm0
0x18000e5a5  xor     eax, eax
0x18000e5a7  movups  [rsp+128h+var_50], xmm0
0x18000e5af  mov     [rsp+128h+var_40], rax
0x18000e5b7  xor     r15d, r15d
0x18000e5ba  mov     edi, r15d
0x18000e5bd  mov     [rsp+128h+bstrLeft], r15
0x18000e5c5  movzx   eax, word ptr [rsp+128h+pvargDest]
0x18000e5cd  cmp     ax, 2
0x18000e5d1  jnb     loc_18000EEC8
0x18000e5d7  movzx   eax, word ptr [rsp+128h+var_B0]
0x18000e5dc  cmp     ax, 2
0x18000e5e0  jnb     loc_18000F00D
0x18000e5e6  or      dword ptr [rsp+128h+var_40], 1
0x18000e5ee  mov     rcx, [r13+68h]
0x18000e5f2  cmp     qword ptr [rcx+100h], 0
0x18000e5fa  jz      short loc_18000E617
0x18000e5fc  mov     edx, 40h ; '@'; Ch
0x18000e601  mov     rcx, [rcx+0F8h]; Str
0x18000e608  call    cs:__imp_wcschr
0x18000e60e  test    rax, rax
0x18000e611  jz      loc_18000EAB0
0x18000e617  mov     rbx, [r13+68h]
0x18000e61b  cmp     qword ptr [rbx+0F8h], 0
0x18000e623  jz      loc_18000E765
0x18000e629  xor     ecx, ecx; bstrString
0x18000e62b  call    cs:__imp_SysFreeString
0x18000e631  lea     rcx, [rbx+0F8h]; this
0x18000e638  call    ?Copy@CComBSTR@ATL@@QEBAPEAGXZ; ATL::CComBSTR::Copy(void)
0x18000e63d  mov     rdi, rax
0x18000e640  mov     [rsp+128h+bstrLeft], rax
0x18000e648  cmp     qword ptr [rbx+0F8h], 0
0x18000e650  jz      loc_18000E765
0x18000e656  test    rax, rax
0x18000e659  jnz     loc_18000E765
0x18000e65f  mov     ecx, 8007000Eh; int
0x18000e664  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18000e66a  cmp     ax, 0Ah
0x18000e66e  jz      loc_18000F0C4
0x18000e674  cmp     bx, ax
0x18000e677  jz      loc_18000E586
0x18000e67d  lea     rcx, [rsp+128h+pvarg]; pvarg
0x18000e685  call    cs:__imp_VariantClear
0x18000e68b  mov     r9d, ebx; vt
0x18000e68e  xor     r8d, r8d; wFlags
0x18000e691  mov     rdx, rdi; pvarSrc
0x18000e694  lea     rcx, [rsp+128h+pvarg]; pvargDest
0x18000e69c  call    cs:__imp_VariantChangeType
0x18000e6a2  mov     edi, eax
0x18000e6a4  mov     [rsp+128h+var_D8], eax
0x18000e6a8  test    eax, eax
0x18000e6aa  jns     loc_18000E586
0x18000e6b0  lea     rcx, [rsp+128h+var_B0]; pvarg
0x18000e6b5  call    cs:__imp_VariantClear
0x18000e6bb  nop
0x18000e6bc  lea     rcx, [rsp+128h+pvargDest]; pvarg
0x18000e6c4  call    cs:__imp_VariantClear
0x18000e6ca  nop
0x18000e6cb  lea     rcx, [rsp+128h+pvarg]; pvarg
0x18000e6d3  call    cs:__imp_VariantClear
0x18000e6d9  mov     eax, edi
0x18000e6db  lea     r11, [rsp+128h+var_28]
0x18000e6e3  mov     rbx, [r11+30h]
0x18000e6e7  mov     rsi, [r11+38h]
0x18000e6eb  mov     rsp, r11
0x18000e6ee  pop     r15
0x18000e6f0  pop     r14
0x18000e6f2  pop     r13
0x18000e6f4  pop     r12
0x18000e6f6  pop     rdi
0x18000e6f7  retn
0x18000e6f8  lea     rcx, [rsp+128h+bstrLeft]; this
0x18000e700  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18000e705  test    eax, eax
0x18000e707  js      loc_18000F207
0x18000e70d  mov     rax, [r13+68h]
0x18000e711  mov     rbx, [rax+0F8h]
0x18000e718  mov     rcx, rbx; pbstr
0x18000e71b  call    cs:__imp_SysStringLen
0x18000e721  test    eax, eax
0x18000e723  jz      loc_18000F215
0x18000e729  mov     [rsp+128h+pbstrResult], r15
0x18000e72e  lea     r8, [rsp+128h+pbstrResult]; pbstrResult
0x18000e733  mov     rdx, rbx; bstrRight
0x18000e736  mov     rbx, [rsp+128h+bstrLeft]
0x18000e73e  mov     rcx, rbx; bstrLeft
0x18000e741  call    cs:__imp_VarBstrCat
0x18000e747  test    eax, eax
0x18000e749  js      loc_18000F20E
0x18000e74f  mov     rcx, rbx; bstrString
0x18000e752  call    cs:__imp_SysFreeString
0x18000e758  mov     rdi, [rsp+128h+pbstrResult]
0x18000e75d  mov     [rsp+128h+bstrLeft], rdi
0x18000e765  mov     qword ptr [rsp+128h+var_50], rdi
0x18000e76d  mov     rbx, r15
0x18000e770  mov     [rsp+128h+var_60], rbx
0x18000e778  test    rsi, rsi
0x18000e77b  jz      short loc_18000E784
0x18000e77d  cmp     [rsi], bx
0x18000e780  cmovz   rsi, r15
0x18000e784  mov     rcx, [r13+70h]
0x18000e788  movzx   eax, word ptr [rcx]
0x18000e78b  test    ax, ax
0x18000e78e  jz      loc_18000EB18
0x18000e794  cmp     ax, 5Ch ; '\'
0x18000e798  jz      loc_18000F222
0x18000e79e  test    rsi, rsi
0x18000e7a1  jz      short loc_18000E7CF
0x18000e7a3  mov     ecx, 20Ah; unsigned __int64
0x18000e7a8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e7ad  mov     rbx, rax
0x18000e7b0  mov     [rsp+128h+var_60], rax
0x18000e7b8  mov     r9, rsi; unsigned __int16 *
0x18000e7bb  mov     r8, [r13+70h]; unsigned int
0x18000e7bf  mov     rcx, rax; this
0x18000e7c2  call    ?SafePathAppend@tsched@@YAJPEAGKPEBG1@Z; tsched::SafePathAppend(ushort *,ulong,ushort const *,ushort const *)
0x18000e7c7  test    eax, eax
0x18000e7c9  jns     loc_18000EB30
0x18000e7cf  mov     [rsp+128h+var_D8], 80070057h
0x18000e7d7  test    rbx, rbx
0x18000e7da  jz      short loc_18000E7E6
0x18000e7dc  mov     rcx, rbx; Block
0x18000e7df  call    cs:__imp_free
0x18000e7e5  nop
0x18000e7e6  mov     rcx, rdi; bstrString
0x18000e7e9  call    cs:__imp_SysFreeString
0x18000e7ef  nop
0x18000e7f0  lea     rcx, [rsp+128h+var_B0]; pvarg
0x18000e7f5  call    cs:__imp_VariantClear
0x18000e7fb  nop
0x18000e7fc  lea     rcx, [rsp+128h+pvargDest]; pvarg
0x18000e804  call    cs:__imp_VariantClear
0x18000e80a  nop
0x18000e80b  lea     rcx, [rsp+128h+pvarg]; pvarg
0x18000e813  call    cs:__imp_VariantClear
0x18000e819  mov     eax, 80070057h
0x18000e81e  jmp     loc_18000E6DB
0x18000e823  lea     rcx, [rsp+128h+pbstrResult]
0x18000e828  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000e82d  nop
0x18000e82e  xor     ecx, ecx; bstrString
0x18000e830  call    cs:__imp_SysFreeString
0x18000e836  nop
0x18000e837  mov     rsi, [rsp+128h+lpMem]
0x18000e83c  call    cs:__imp_GetProcessHeap
0x18000e842  mov     r8, rsi; lpMem
0x18000e845  xor     edx, edx; dwFlags
0x18000e847  mov     rcx, rax; hHeap
0x18000e84a  call    cs:__imp_HeapFree
0x18000e850  mov     [rsp+128h+lpMem], r15
0x18000e855  mov     rsi, [rsp+128h+var_C8]
0x18000e85a  call    cs:__imp_GetProcessHeap
0x18000e860  mov     r8, rsi; lpMem
0x18000e863  xor     edx, edx; dwFlags
0x18000e865  mov     rcx, rax; hHeap
0x18000e868  call    cs:__imp_HeapFree
0x18000e86e  mov     [rsp+128h+var_C8], r15
0x18000e873  test    rbx, rbx
0x18000e876  jz      short loc_18000E882
0x18000e878  mov     rcx, rbx; Block
0x18000e87b  call    cs:__imp_free
0x18000e881  nop
0x18000e882  mov     rcx, rdi; bstrString
0x18000e885  call    cs:__imp_SysFreeString
0x18000e88b  nop
0x18000e88c  lea     rcx, [rsp+128h+var_B0]; pvarg
0x18000e891  call    cs:__imp_VariantClear
0x18000e897  nop
0x18000e898  lea     rcx, [rsp+128h+pvargDest]; pvarg
0x18000e8a0  call    cs:__imp_VariantClear
0x18000e8a6  nop
0x18000e8a7  lea     rcx, [rsp+128h+pvarg]; pvarg
0x18000e8af  call    cs:__imp_VariantClear
0x18000e8b5  mov     eax, r14d
0x18000e8b8  jmp     loc_18000E6DB
0x18000e8bd  lea     rcx, [rsp+128h+pbstrResult]
0x18000e8c2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000e8c7  nop
0x18000e8c8  xor     ecx, ecx; bstrString
0x18000e8ca  call    cs:__imp_SysFreeString
0x18000e8d0  nop
0x18000e8d1  mov     rsi, [rsp+128h+lpMem]
0x18000e8d6  call    cs:__imp_GetProcessHeap
0x18000e8dc  mov     r8, rsi; lpMem
0x18000e8df  xor     edx, edx; dwFlags
0x18000e8e1  mov     rcx, rax; hHeap
0x18000e8e4  call    cs:__imp_HeapFree
0x18000e8ea  mov     [rsp+128h+lpMem], r15
0x18000e8ef  mov     rsi, [rsp+128h+var_C8]
0x18000e8f4  call    cs:__imp_GetProcessHeap
0x18000e8fa  mov     r8, rsi; lpMem
0x18000e8fd  xor     edx, edx; dwFlags
0x18000e8ff  mov     rcx, rax; hHeap
0x18000e902  call    cs:__imp_HeapFree
0x18000e908  mov     [rsp+128h+var_C8], r15
0x18000e90d  test    rbx, rbx
0x18000e910  jz      short loc_18000E91C
0x18000e912  mov     rcx, rbx; Block
0x18000e915  call    cs:__imp_free
0x18000e91b  nop
0x18000e91c  mov     rcx, rdi; bstrString
0x18000e91f  call    cs:__imp_SysFreeString
0x18000e925  nop
0x18000e926  lea     rcx, [rsp+128h+var_B0]; pvarg
0x18000e92b  call    cs:__imp_VariantClear
0x18000e931  nop
0x18000e932  lea     rcx, [rsp+128h+pvargDest]; pvarg
0x18000e93a  call    cs:__imp_VariantClear
0x18000e940  nop
0x18000e941  lea     rcx, [rsp+128h+pvarg]; pvarg
0x18000e949  call    cs:__imp_VariantClear
0x18000e94f  mov     eax, r14d
0x18000e952  jmp     loc_18000E6DB
0x18000e957  lea     rcx, [rsp+128h+pbstrResult]
0x18000e95c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000e961  nop
0x18000e962  xor     ecx, ecx; bstrString
0x18000e964  call    cs:__imp_SysFreeString
0x18000e96a  nop
0x18000e96b  mov     rsi, [rsp+128h+lpMem]
0x18000e970  call    cs:__imp_GetProcessHeap
0x18000e976  mov     r8, rsi; lpMem
0x18000e979  xor     edx, edx; dwFlags
0x18000e97b  mov     rcx, rax; hHeap
0x18000e97e  call    cs:__imp_HeapFree
0x18000e984  mov     [rsp+128h+lpMem], r15
0x18000e989  mov     rsi, [rsp+128h+var_C8]
0x18000e98e  call    cs:__imp_GetProcessHeap
0x18000e994  mov     r8, rsi; lpMem
0x18000e997  xor     edx, edx; dwFlags
0x18000e999  mov     rcx, rax; hHeap
0x18000e99c  call    cs:__imp_HeapFree
0x18000e9a2  mov     [rsp+128h+var_C8], r15
0x18000e9a7  test    rbx, rbx
0x18000e9aa  jz      short loc_18000E9B6
0x18000e9ac  mov     rcx, rbx; Block
0x18000e9af  call    cs:__imp_free
0x18000e9b5  nop
0x18000e9b6  mov     rcx, rdi; bstrString
0x18000e9b9  call    cs:__imp_SysFreeString
0x18000e9bf  nop
0x18000e9c0  lea     rcx, [rsp+128h+var_B0]; pvarg
0x18000e9c5  call    cs:__imp_VariantClear
0x18000e9cb  nop
0x18000e9cc  lea     rcx, [rsp+128h+pvargDest]; pvarg
0x18000e9d4  call    cs:__imp_VariantClear
0x18000e9da  nop
0x18000e9db  lea     rcx, [rsp+128h+pvarg]; pvarg
0x18000e9e3  call    cs:__imp_VariantClear
0x18000e9e9  mov     eax, r14d
0x18000e9ec  jmp     loc_18000E6DB
0x18000e9f1  lea     rcx, [rsp+128h+pbstrResult]
  ... truncated ...
```
