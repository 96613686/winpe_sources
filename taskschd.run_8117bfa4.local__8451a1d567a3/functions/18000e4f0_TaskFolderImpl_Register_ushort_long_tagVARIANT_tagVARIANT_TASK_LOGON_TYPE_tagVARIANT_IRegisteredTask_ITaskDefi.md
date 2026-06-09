# TaskFolderImpl::Register(ushort *,long,tagVARIANT &,tagVARIANT &,_TASK_LOGON_TYPE,tagVARIANT &,IRegisteredTask * *,ITaskDefinition *,ushort const *)

- ea: `0x18000e4f0`
- end: `0x18000f693`
- name: `?Register@TaskFolderImpl@@AEAAJPEAGJAEAUtagVARIANT@@1W4_TASK_LOGON_TYPE@@1PEAPEAUIRegisteredTask@@PEAUITaskDefinition@@PEBG@Z`
- size: `4515`
- prototype: `int(TaskFolderImpl *__hidden this, unsigned __int16 *, int, struct tagVARIANT *, struct tagVARIANT *, enum _TASK_LOGON_TYPE, struct tagVARIANT *, struct IRegisteredTask **, struct ITaskDefinition *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18000e410`
- `0x18000e480`

## callees

- `0x180001880`
- `0x1800052c0`
- `0x180007e90`
- `0x18000dd3c`
- `0x18000e4f0`
- `0x18000f69c`
- `0x180010070`
- `0x1800108c0`
- `0x18001fe20`
- `0x180021f70`
- `0x18003698c`
- `0x18003977c`
- `0x18003c664`
- `0x180058010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000f577`
- `msvcrt!wcsrchr` at `0x18000f577`
- `msvcrt!wcschr` at `0x18000e639`
- `msvcrt!wcschr` at `0x18000ec43`
- `msvcrt!wcschr` at `0x18000e639`
- `msvcrt!wcschr` at `0x18000ec43`
- `msvcrt!free` at `0x18000e854`
- `msvcrt!free` at `0x18000e92c`
- `msvcrt!free` at `0x18000ea02`
- `msvcrt!free` at `0x18000ead8`
- `msvcrt!free` at `0x18000ebb7`
- `msvcrt!free` at `0x18000eeda`
- `msvcrt!free` at `0x18000efbd`
- `msvcrt!free` at `0x18000f0b7`
- `msvcrt!free` at `0x18000f405`
- `msvcrt!free` at `0x18000f606`
- `msvcrt!free` at `0x18000e854`
- `msvcrt!free` at `0x18000e92c`
- `msvcrt!free` at `0x18000ea02`
- `msvcrt!free` at `0x18000ead8`
- `msvcrt!free` at `0x18000ebb7`
- `msvcrt!free` at `0x18000eeda`
- `msvcrt!free` at `0x18000efbd`
- `msvcrt!free` at `0x18000f0b7`
- `msvcrt!free` at `0x18000f405`
- `msvcrt!free` at `0x18000f606`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000edaf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000edaf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ed79`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ed79`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e8e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e913`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e9bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e9e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ea95`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eabf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eb6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eb9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ee8f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eebd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ef7a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000efa4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f06c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f09a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f3ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f3e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f5c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f5f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e8e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e913`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e9bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e9e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ea95`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eabf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eb6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eb9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ee8f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eebd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ef7a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000efa4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f06c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f09a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f3ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f3e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f5c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f5f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e8d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e8ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e9ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e9d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ea81`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eaab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eb58`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eb86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ee7b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eea9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ef66`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ef90`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f058`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f086`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f3a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f3d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f5b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f5de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e8d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e8ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e9ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e9d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ea81`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eaab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eb58`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eb86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ee7b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eea9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ef66`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ef90`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f058`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f086`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f3a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f3d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f5b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f5de`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e662`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e7c0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e864`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e8c3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e93c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e999`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ea12`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ea6f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eae8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eb46`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ebc7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ec6b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ee69`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eeea`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ef54`
- `OLEAUT32!__imp_SysFreeString` at `0x18000efcd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f046`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f0c7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f2b6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f394`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f415`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f5a2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f616`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e662`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e7c0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e864`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e8c3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e93c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e999`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ea12`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ea6f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eae8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eb46`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ebc7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ec6b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ee69`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eeea`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ef54`
- `OLEAUT32!__imp_SysFreeString` at `0x18000efcd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f046`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f0c7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f2b6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f394`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f415`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f5a2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f616`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e77d`
- `OLEAUT32!__imp_SysStringLen` at `0x18000f32d`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e77d`
- `OLEAUT32!__imp_SysStringLen` at `0x18000f32d`
- `OLEAUT32!__imp_VariantClear` at `0x18000e6c2`
- `OLEAUT32!__imp_VariantClear` at `0x18000e6fe`
- `OLEAUT32!__imp_VariantClear` at `0x18000e713`
- `OLEAUT32!__imp_VariantClear` at `0x18000e728`
- `OLEAUT32!__imp_VariantClear` at `0x18000e876`
- `OLEAUT32!__imp_VariantClear` at `0x18000e88b`
- `OLEAUT32!__imp_VariantClear` at `0x18000e8a0`
- `OLEAUT32!__imp_VariantClear` at `0x18000e94e`
- `OLEAUT32!__imp_VariantClear` at `0x18000e963`
- `OLEAUT32!__imp_VariantClear` at `0x18000e978`
- `OLEAUT32!__imp_VariantClear` at `0x18000ea24`
- `OLEAUT32!__imp_VariantClear` at `0x18000ea39`
- `OLEAUT32!__imp_VariantClear` at `0x18000ea4e`
- `OLEAUT32!__imp_VariantClear` at `0x18000eafa`
- `OLEAUT32!__imp_VariantClear` at `0x18000eb0f`
- `OLEAUT32!__imp_VariantClear` at `0x18000eb24`
- `OLEAUT32!__imp_VariantClear` at `0x18000ebd9`
- `OLEAUT32!__imp_VariantClear` at `0x18000ebee`
- `OLEAUT32!__imp_VariantClear` at `0x18000ec03`
- `OLEAUT32!__imp_VariantClear` at `0x18000eefc`
- `OLEAUT32!__imp_VariantClear` at `0x18000ef11`
- `OLEAUT32!__imp_VariantClear` at `0x18000ef26`
- `OLEAUT32!__imp_VariantClear` at `0x18000efdf`
- `OLEAUT32!__imp_VariantClear` at `0x18000eff4`
- `OLEAUT32!__imp_VariantClear` at `0x18000f009`
- `OLEAUT32!__imp_VariantClear` at `0x18000f0d9`
- `OLEAUT32!__imp_VariantClear` at `0x18000f0ee`
- `OLEAUT32!__imp_VariantClear` at `0x18000f103`
- `OLEAUT32!__imp_VariantClear` at `0x18000f177`
- `OLEAUT32!__imp_VariantClear` at `0x18000f1b3`
- `OLEAUT32!__imp_VariantClear` at `0x18000f1c8`
- `OLEAUT32!__imp_VariantClear` at `0x18000f1dd`
- `OLEAUT32!__imp_VariantClear` at `0x18000f1fe`
- `OLEAUT32!__imp_VariantClear` at `0x18000f237`
- `OLEAUT32!__imp_VariantClear` at `0x18000f24c`
- `OLEAUT32!__imp_VariantClear` at `0x18000f261`
- `OLEAUT32!__imp_VariantClear` at `0x18000f2c8`
- `OLEAUT32!__imp_VariantClear` at `0x18000f2dd`
- `OLEAUT32!__imp_VariantClear` at `0x18000f2f2`
- `OLEAUT32!__imp_VariantClear` at `0x18000f427`
- `OLEAUT32!__imp_VariantClear` at `0x18000f43c`
- `OLEAUT32!__imp_VariantClear` at `0x18000f451`
- `OLEAUT32!__imp_VariantClear` at `0x18000f628`
- `OLEAUT32!__imp_VariantClear` at `0x18000f63d`
- `OLEAUT32!__imp_VariantClear` at `0x18000f652`
- `OLEAUT32!__imp_VariantClear` at `0x18000e6c2`
- `OLEAUT32!__imp_VariantClear` at `0x18000e6fe`
- `OLEAUT32!__imp_VariantClear` at `0x18000e713`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
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
      v25 = ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrLeft, v16, 1);
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
0x18000e4f0  mov     r11, rsp
0x18000e4f3  mov     [r11+8], rbx
0x18000e4f7  mov     [r11+10h], rsi
0x18000e4fb  mov     [r11+18h], r8d
0x18000e4ff  push    rdi
0x18000e500  push    r12
0x18000e502  push    r13
0x18000e504  push    r14
0x18000e506  push    r15
0x18000e508  sub     rsp, 100h
0x18000e50f  mov     rsi, r9
0x18000e512  mov     r14, rdx
0x18000e515  mov     r13, rcx
0x18000e518  mov     r12, [rsp+128h+arg_40]
0x18000e520  mov     [rsp+128h+var_D8], 0
0x18000e528  xor     eax, eax
0x18000e52a  mov     [r11-80h], ax
0x18000e52f  mov     rdi, [rsp+128h+pvargSrc]
0x18000e537  mov     rdx, rdi; pvargSrc
0x18000e53a  lea     rcx, [r11-80h]; pvargDest
0x18000e53e  call    cs:__imp_VariantCopy
0x18000e545  nop     dword ptr [rax+rax+00h]
0x18000e54a  test    eax, eax
0x18000e54c  js      loc_18000EC17
0x18000e552  xor     eax, eax
0x18000e554  mov     word ptr [rsp+128h+pvargDest], ax
0x18000e55c  mov     rdx, rsi; pvargSrc
0x18000e55f  lea     rcx, [rsp+128h+pvargDest]; pvargDest
0x18000e567  call    cs:__imp_VariantCopy
0x18000e56e  nop     dword ptr [rax+rax+00h]
0x18000e573  test    eax, eax
0x18000e575  js      loc_18000F4B6
0x18000e57b  xor     eax, eax
0x18000e57d  mov     word ptr [rsp+128h+var_B0], ax
0x18000e582  mov     r15, [rsp+128h+pvarSrc]
0x18000e58a  mov     rdx, r15; pvargSrc
0x18000e58d  lea     rcx, [rsp+128h+var_B0]; pvargDest
0x18000e592  call    cs:__imp_VariantCopy
0x18000e599  nop     dword ptr [rax+rax+00h]
0x18000e59e  test    eax, eax
0x18000e5a0  js      loc_18000F4D2
0x18000e5a6  movzx   eax, word ptr [rdi]
0x18000e5a9  mov     ebx, 8
0x18000e5ae  cmp     ax, 2
0x18000e5b2  jnb     loc_18000E6A7
0x18000e5b8  movzx   eax, word ptr [rsi]
0x18000e5bb  cmp     ax, 2
0x18000e5bf  jnb     loc_18000F15C
0x18000e5c5  movzx   eax, word ptr [r15]
0x18000e5c9  cmp     ax, 2
0x18000e5cd  jnb     loc_18000F289
0x18000e5d3  xorps   xmm0, xmm0
0x18000e5d6  xor     eax, eax
0x18000e5d8  movups  [rsp+128h+var_50], xmm0
0x18000e5e0  mov     [rsp+128h+var_40], rax
0x18000e5e8  xor     r15d, r15d
0x18000e5eb  mov     edi, r15d
0x18000e5ee  mov     [rsp+128h+bstrLeft], r15
0x18000e5f6  movzx   eax, word ptr [rsp+128h+pvargDest]
0x18000e5fe  cmp     ax, 2
0x18000e602  jnb     loc_18000F117
0x18000e608  movzx   eax, word ptr [rsp+128h+var_B0]
0x18000e60d  cmp     ax, 2
0x18000e611  jnb     loc_18000F298
0x18000e617  or      dword ptr [rsp+128h+var_40], 1
0x18000e61f  mov     rcx, [r13+68h]
0x18000e623  cmp     qword ptr [rcx+100h], 0
0x18000e62b  jz      short loc_18000E64E
0x18000e62d  mov     edx, 40h ; '@'; Ch
0x18000e632  mov     rcx, [rcx+0F8h]; Str
0x18000e639  call    cs:__imp_wcschr
0x18000e640  nop     dword ptr [rax+rax+00h]
0x18000e645  test    rax, rax
0x18000e648  jz      loc_18000EC33
0x18000e64e  mov     rbx, [r13+68h]
0x18000e652  cmp     qword ptr [rbx+0F8h], 0
0x18000e65a  jz      loc_18000E7D9
0x18000e660  xor     ecx, ecx; bstrString
0x18000e662  call    cs:__imp_SysFreeString
0x18000e669  nop     dword ptr [rax+rax+00h]
0x18000e66e  lea     rcx, [rbx+0F8h]; this
0x18000e675  call    ?Copy@CComBSTR@ATL@@QEBAPEAGXZ; ATL::CComBSTR::Copy(void)
0x18000e67a  mov     rdi, rax
0x18000e67d  mov     [rsp+128h+bstrLeft], rax
0x18000e685  cmp     qword ptr [rbx+0F8h], 0
0x18000e68d  jz      loc_18000E7D9
0x18000e693  test    rax, rax
0x18000e696  jnz     loc_18000E7D9
0x18000e69c  mov     ecx, 8007000Eh; int
0x18000e6a1  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18000e6a7  cmp     ax, 0Ah
0x18000e6ab  jz      loc_18000F36D
0x18000e6b1  cmp     bx, ax
0x18000e6b4  jz      loc_18000E5B8
0x18000e6ba  lea     rcx, [rsp+128h+pvarg]; pvarg
0x18000e6c2  call    cs:__imp_VariantClear
0x18000e6c9  nop     dword ptr [rax+rax+00h]
0x18000e6ce  mov     r9d, ebx; vt
0x18000e6d1  xor     r8d, r8d; wFlags
0x18000e6d4  mov     rdx, rdi; pvarSrc
0x18000e6d7  lea     rcx, [rsp+128h+pvarg]; pvargDest
0x18000e6df  call    cs:__imp_VariantChangeType
0x18000e6e6  nop     dword ptr [rax+rax+00h]
0x18000e6eb  mov     edi, eax
0x18000e6ed  mov     [rsp+128h+var_D8], eax
0x18000e6f1  test    eax, eax
0x18000e6f3  jns     loc_18000E5B8
0x18000e6f9  lea     rcx, [rsp+128h+var_B0]; pvarg
0x18000e6fe  call    cs:__imp_VariantClear
0x18000e705  nop     dword ptr [rax+rax+00h]
0x18000e70a  nop
0x18000e70b  lea     rcx, [rsp+128h+pvargDest]; pvarg
0x18000e713  call    cs:__imp_VariantClear
0x18000e71a  nop     dword ptr [rax+rax+00h]
0x18000e71f  nop
0x18000e720  lea     rcx, [rsp+128h+pvarg]; pvarg
0x18000e728  call    cs:__imp_VariantClear
0x18000e72f  nop     dword ptr [rax+rax+00h]
0x18000e734  mov     eax, edi
0x18000e736  lea     r11, [rsp+128h+var_28]
0x18000e73e  mov     rbx, [r11+30h]
0x18000e742  mov     rsi, [r11+38h]
0x18000e746  mov     rsp, r11
0x18000e749  pop     r15
0x18000e74b  pop     r14
0x18000e74d  pop     r13
0x18000e74f  pop     r12
0x18000e751  pop     rdi
0x18000e752  retn
0x18000e754  mov     r8d, 1; int
0x18000e75a  lea     rcx, [rsp+128h+bstrLeft]; this
0x18000e762  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18000e767  test    eax, eax
0x18000e769  js      loc_18000F4EB
0x18000e76f  mov     rax, [r13+68h]
0x18000e773  mov     rbx, [rax+0F8h]
0x18000e77a  mov     rcx, rbx; pbstr
0x18000e77d  call    cs:__imp_SysStringLen
0x18000e784  nop     dword ptr [rax+rax+00h]
0x18000e789  test    eax, eax
0x18000e78b  jz      loc_18000F4F9
0x18000e791  mov     [rsp+128h+pbstrResult], r15
0x18000e796  lea     r8, [rsp+128h+pbstrResult]; pbstrResult
0x18000e79b  mov     rdx, rbx; bstrRight
0x18000e79e  mov     rbx, [rsp+128h+bstrLeft]
0x18000e7a6  mov     rcx, rbx; bstrLeft
0x18000e7a9  call    cs:__imp_VarBstrCat
0x18000e7b0  nop     dword ptr [rax+rax+00h]
0x18000e7b5  test    eax, eax
0x18000e7b7  js      loc_18000F4F2
0x18000e7bd  mov     rcx, rbx; bstrString
0x18000e7c0  call    cs:__imp_SysFreeString
0x18000e7c7  nop     dword ptr [rax+rax+00h]
0x18000e7cc  mov     rdi, [rsp+128h+pbstrResult]
0x18000e7d1  mov     [rsp+128h+bstrLeft], rdi
0x18000e7d9  mov     qword ptr [rsp+128h+var_50], rdi
0x18000e7e1  mov     rbx, r15
0x18000e7e4  mov     [rsp+128h+var_60], rbx
0x18000e7ec  test    r14, r14
0x18000e7ef  jz      short loc_18000E7F9
0x18000e7f1  cmp     [r14], bx
0x18000e7f5  cmovz   r14, r15
0x18000e7f9  mov     rcx, [r13+70h]
0x18000e7fd  movzx   eax, word ptr [rcx]
0x18000e800  test    ax, ax
0x18000e803  jz      loc_18000ECA7
0x18000e809  cmp     ax, 5Ch ; '\'
0x18000e80d  jz      loc_18000F506
0x18000e813  test    r14, r14
0x18000e816  jz      short loc_18000E844
0x18000e818  mov     ecx, 20Ah; unsigned __int64
0x18000e81d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e822  mov     rbx, rax
0x18000e825  mov     [rsp+128h+var_60], rax
0x18000e82d  mov     r9, r14; unsigned __int16 *
0x18000e830  mov     r8, [r13+70h]; unsigned int
0x18000e834  mov     rcx, rax; this
0x18000e837  call    ?SafePathAppend@tsched@@YAJPEAGKPEBG1@Z; tsched::SafePathAppend(ushort *,ulong,ushort const *,ushort const *)
0x18000e83c  test    eax, eax
0x18000e83e  jns     loc_18000ECBF
0x18000e844  mov     [rsp+128h+var_D8], 80070057h
0x18000e84c  test    rbx, rbx
0x18000e84f  jz      short loc_18000E861
0x18000e851  mov     rcx, rbx; Block
0x18000e854  call    cs:__imp_free
0x18000e85b  nop     dword ptr [rax+rax+00h]
0x18000e860  nop
0x18000e861  mov     rcx, rdi; bstrString
0x18000e864  call    cs:__imp_SysFreeString
0x18000e86b  nop     dword ptr [rax+rax+00h]
0x18000e870  nop
0x18000e871  lea     rcx, [rsp+128h+var_B0]; pvarg
0x18000e876  call    cs:__imp_VariantClear
0x18000e87d  nop     dword ptr [rax+rax+00h]
0x18000e882  nop
0x18000e883  lea     rcx, [rsp+128h+pvargDest]; pvarg
0x18000e88b  call    cs:__imp_VariantClear
0x18000e892  nop     dword ptr [rax+rax+00h]
0x18000e897  nop
0x18000e898  lea     rcx, [rsp+128h+pvarg]; pvarg
0x18000e8a0  call    cs:__imp_VariantClear
0x18000e8a7  nop     dword ptr [rax+rax+00h]
0x18000e8ac  mov     eax, 80070057h
0x18000e8b1  jmp     loc_18000E736
0x18000e8b6  lea     rcx, [rsp+128h+pbstrResult]
0x18000e8bb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000e8c0  nop
0x18000e8c1  xor     ecx, ecx; bstrString
0x18000e8c3  call    cs:__imp_SysFreeString
0x18000e8ca  nop     dword ptr [rax+rax+00h]
0x18000e8cf  nop
0x18000e8d0  mov     rsi, [rsp+128h+lpMem]
0x18000e8d5  call    cs:__imp_GetProcessHeap
0x18000e8dc  nop     dword ptr [rax+rax+00h]
0x18000e8e1  mov     r8, rsi; lpMem
0x18000e8e4  xor     edx, edx; dwFlags
0x18000e8e6  mov     rcx, rax; hHeap
0x18000e8e9  call    cs:__imp_HeapFree
0x18000e8f0  nop     dword ptr [rax+rax+00h]
0x18000e8f5  mov     [rsp+128h+lpMem], r15
0x18000e8fa  mov     rsi, [rsp+128h+var_C8]
0x18000e8ff  call    cs:__imp_GetProcessHeap
0x18000e906  nop     dword ptr [rax+rax+00h]
0x18000e90b  mov     r8, rsi; lpMem
0x18000e90e  xor     edx, edx; dwFlags
0x18000e910  mov     rcx, rax; hHeap
0x18000e913  call    cs:__imp_HeapFree
0x18000e91a  nop     dword ptr [rax+rax+00h]
0x18000e91f  mov     [rsp+128h+var_C8], r15
0x18000e924  test    rbx, rbx
0x18000e927  jz      short loc_18000E939
0x18000e929  mov     rcx, rbx; Block
0x18000e92c  call    cs:__imp_free
0x18000e933  nop     dword ptr [rax+rax+00h]
0x18000e938  nop
0x18000e939  mov     rcx, rdi; bstrString
0x18000e93c  call    cs:__imp_SysFreeString
0x18000e943  nop     dword ptr [rax+rax+00h]
0x18000e948  nop
0x18000e949  lea     rcx, [rsp+128h+var_B0]; pvarg
0x18000e94e  call    cs:__imp_VariantClear
0x18000e955  nop     dword ptr [rax+rax+00h]
0x18000e95a  nop
0x18000e95b  lea     rcx, [rsp+128h+pvargDest]; pvarg
0x18000e963  call    cs:__imp_VariantClear
0x18000e96a  nop     dword ptr [rax+rax+00h]
0x18000e96f  nop
0x18000e970  lea     rcx, [rsp+128h+pvarg]; pvarg
0x18000e978  call    cs:__imp_VariantClear
0x18000e97f  nop     dword ptr [rax+rax+00h]
0x18000e984  mov     eax, r14d
0x18000e987  jmp     loc_18000E736
0x18000e98c  lea     rcx, [rsp+128h+pbstrResult]
0x18000e991  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000e996  nop
0x18000e997  xor     ecx, ecx; bstrString
0x18000e999  call    cs:__imp_SysFreeString
0x18000e9a0  nop     dword ptr [rax+rax+00h]
0x18000e9a5  nop
0x18000e9a6  mov     rsi, [rsp+128h+lpMem]
0x18000e9ab  call    cs:__imp_GetProcessHeap
0x18000e9b2  nop     dword ptr [rax+rax+00h]
0x18000e9b7  mov     r8, rsi; lpMem
0x18000e9ba  xor     edx, edx; dwFlags
0x18000e9bc  mov     rcx, rax; hHeap
0x18000e9bf  call    cs:__imp_HeapFree
0x18000e9c6  nop     dword ptr [rax+rax+00h]
0x18000e9cb  mov     [rsp+128h+lpMem], r15
0x18000e9d0  mov     rsi, [rsp+128h+var_C8]
0x18000e9d5  call    cs:__imp_GetProcessHeap
0x18000e9dc  nop     dword ptr [rax+rax+00h]
0x18000e9e1  mov     r8, rsi; lpMem
0x18000e9e4  xor     edx, edx; dwFlags
0x18000e9e6  mov     rcx, rax; hHeap
0x18000e9e9  call    cs:__imp_HeapFree
0x18000e9f0  nop     dword ptr [rax+rax+00h]
0x18000e9f5  mov     [rsp+128h+var_C8], r15
0x18000e9fa  test    rbx, rbx
0x18000e9fd  jz      short loc_18000EA0F
0x18000e9ff  mov     rcx, rbx; Block
0x18000ea02  call    cs:__imp_free
0x18000ea09  nop     dword ptr [rax+rax+00h]
0x18000ea0e  nop
0x18000ea0f  mov     rcx, rdi; bstrString
0x18000ea12  call    cs:__imp_SysFreeString
0x18000ea19  nop     dword ptr [rax+rax+00h]
0x18000ea1e  nop
0x18000ea1f  lea     rcx, [rsp+128h+var_B0]; pvarg
0x18000ea24  call    cs:__imp_VariantClear
0x18000ea2b  nop     dword ptr [rax+rax+00h]
0x18000ea30  nop
0x18000ea31  lea     rcx, [rsp+128h+pvargDest]; pvarg
0x18000ea39  call    cs:__imp_VariantClear
0x18000ea40  nop     dword ptr [rax+rax+00h]
0x18000ea45  nop
0x18000ea46  lea     rcx, [rsp+128h+pvarg]; pvarg
0x18000ea4e  call    cs:__imp_VariantClear
0x18000ea55  nop     dword ptr [rax+rax+00h]
0x18000ea5a  mov     eax, r14d
0x18000ea5d  jmp     loc_18000E736
  ... truncated ...
```
