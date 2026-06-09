# RpcServer::EnumFolder(ushort const *,bool,ulong,ulong *,ulong,ulong *,ushort * * *)

- ea: `0x180027990`
- end: `0x18002b1fb`
- name: `?EnumFolder@RpcServer@@QEAAJPEBG_NKPEAKK2PEAPEAPEAG@Z`
- size: `14443`
- prototype: `__int64 __fastcall(RpcServer *__hidden this, const unsigned __int16 *, bool, unsigned int, unsigned int *, unsigned int, unsigned int *, unsigned __int16 ***)`
- caller_count: `2`
- callee_count: `32`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800267c0`
- `0x180026820`

## callees

- `0x18000bb10`
- `0x18000cb10`
- `0x18000cc40`
- `0x18000d830`
- `0x18000fda4`
- `0x18000ff40`
- `0x180010390`
- `0x180011e40`
- `0x1800138d8`
- `0x180015030`
- `0x18001d130`
- `0x18001ea40`
- `0x18001f060`
- `0x18001fe10`
- `0x180024730`
- `0x180027910`
- `0x180027990`
- `0x18002b210`
- `0x18002db40`
- `0x18002f814`
- `0x180034cc0`
- `0x180037490`
- `0x180043ffc`
- `0x180054824`
- `0x180054bd8`
- `0x18005a2bc`
- `0x18005a2d6`
- `0x180069f84`
- `0x18006a08c`
- `0x1800829fa`
- `0x180082a40`
- `0x180088010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180027cc8`
- `OLEAUT32!__imp_SysAllocString` at `0x180027d4e`
- `OLEAUT32!__imp_SysAllocString` at `0x1800280df`
- `OLEAUT32!__imp_SysAllocString` at `0x180028160`
- `OLEAUT32!__imp_SysAllocString` at `0x180028592`
- `OLEAUT32!__imp_SysAllocString` at `0x18002860e`
- `OLEAUT32!__imp_SysAllocString` at `0x18002870f`
- `OLEAUT32!__imp_SysAllocString` at `0x18002887f`
- `OLEAUT32!__imp_SysAllocString` at `0x180028be0`
- `OLEAUT32!__imp_SysAllocString` at `0x1800293e9`
- `OLEAUT32!__imp_SysAllocString` at `0x180029498`
- `OLEAUT32!__imp_SysAllocString` at `0x180029745`
- `OLEAUT32!__imp_SysAllocString` at `0x180029ae6`
- `OLEAUT32!__imp_SysAllocString` at `0x180029cb1`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a1b7`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a6eb`
- `OLEAUT32!__imp_SysAllocString` at `0x180027cc8`
- `OLEAUT32!__imp_SysAllocString` at `0x180027d4e`
- `OLEAUT32!__imp_SysAllocString` at `0x1800280df`
- `OLEAUT32!__imp_SysAllocString` at `0x180028160`
- `OLEAUT32!__imp_SysAllocString` at `0x180028592`
- `OLEAUT32!__imp_SysAllocString` at `0x18002860e`
- `OLEAUT32!__imp_SysAllocString` at `0x18002870f`
- `OLEAUT32!__imp_SysAllocString` at `0x18002887f`
- `OLEAUT32!__imp_SysAllocString` at `0x180028be0`
- `OLEAUT32!__imp_SysAllocString` at `0x1800293e9`
- `OLEAUT32!__imp_SysAllocString` at `0x180029498`
- `OLEAUT32!__imp_SysAllocString` at `0x180029745`
- `OLEAUT32!__imp_SysAllocString` at `0x180029ae6`
- `OLEAUT32!__imp_SysAllocString` at `0x180029cb1`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a1b7`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a6eb`
- `OLEAUT32!__imp_SysFreeString` at `0x180029356`
- `OLEAUT32!__imp_SysFreeString` at `0x180029356`
- `OLEAUT32!__imp_SysStringLen` at `0x180027da9`
- `OLEAUT32!__imp_SysStringLen` at `0x180027dc4`
- `OLEAUT32!__imp_SysStringLen` at `0x1800281c3`
- `OLEAUT32!__imp_SysStringLen` at `0x1800281db`
- `OLEAUT32!__imp_SysStringLen` at `0x18002876a`
- `OLEAUT32!__imp_SysStringLen` at `0x180028785`
- `OLEAUT32!__imp_SysStringLen` at `0x1800288e2`
- `OLEAUT32!__imp_SysStringLen` at `0x1800288fa`
- `OLEAUT32!__imp_SysStringLen` at `0x1800297aa`
- `OLEAUT32!__imp_SysStringLen` at `0x1800297c9`
- `OLEAUT32!__imp_SysStringLen` at `0x180029b4f`
- `OLEAUT32!__imp_SysStringLen` at `0x180029b6e`
- `OLEAUT32!__imp_SysStringLen` at `0x18002a5c2`
- `OLEAUT32!__imp_SysStringLen` at `0x18002a5dd`
- `OLEAUT32!__imp_SysStringLen` at `0x18002a653`
- `OLEAUT32!__imp_SysStringLen` at `0x18002a66e`
- `OLEAUT32!__imp_SysStringLen` at `0x180027da9`
- `OLEAUT32!__imp_SysStringLen` at `0x180027dc4`
- `OLEAUT32!__imp_SysStringLen` at `0x1800281c3`
- `OLEAUT32!__imp_SysStringLen` at `0x1800281db`
- `OLEAUT32!__imp_SysStringLen` at `0x18002876a`
- `OLEAUT32!__imp_SysStringLen` at `0x180028785`
- `OLEAUT32!__imp_SysStringLen` at `0x1800288e2`
- `OLEAUT32!__imp_SysStringLen` at `0x1800288fa`
- `OLEAUT32!__imp_SysStringLen` at `0x1800297aa`
- `OLEAUT32!__imp_SysStringLen` at `0x1800297c9`
- `OLEAUT32!__imp_SysStringLen` at `0x180029b4f`
- `OLEAUT32!__imp_SysStringLen` at `0x180029b6e`
- `OLEAUT32!__imp_SysStringLen` at `0x18002a5c2`
- `OLEAUT32!__imp_SysStringLen` at `0x18002a5dd`
- `OLEAUT32!__imp_SysStringLen` at `0x18002a653`
- `OLEAUT32!__imp_SysStringLen` at `0x18002a66e`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180027dfe`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18002821b`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180028653`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800287bf`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18002893a`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800294e3`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180029a0f`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18002a27b`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180027dfe`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18002821b`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180028653`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800287bf`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18002893a`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800294e3`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180029a0f`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18002a27b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a76f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a76f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800291fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029325`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029d63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a042`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800291fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029325`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029d63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a042`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180027c5c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180027c5c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800291e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002930a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180029d48`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002a027`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002a12d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800291e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002930a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180029d48`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002a027`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002a12d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180028a8f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180028a8f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027ea6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800282c1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800289c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028acc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029591`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027ea6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800282c1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800289c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028acc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029591`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027f79`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027fde`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028398`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800283fd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028b0f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002924c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002965a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800296c0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027f79`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027fde`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028398`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800283fd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028b0f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002924c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002965a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800296c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027ee7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027f34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028038`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028304`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028354`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028454`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028b51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028b73`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800295d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002961a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002982b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a3c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a4fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b044`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027ee7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027f34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028038`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028304`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028354`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028454`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028b51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028b73`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800295d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002961a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002982b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a3c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a4fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b044`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800292bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002937e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800292bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002937e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027c99`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027d1c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027d7a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800280ac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002812d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002818c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002851d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180028563`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800285df`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800286e0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002873b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002884f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800288ab`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180028bb2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180028ca9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180029469`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180029712`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180029771`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180029ab8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180029b12`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027c99`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027d1c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027d7a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800280ac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002812d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002818c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002851d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180028563`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800285df`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800286e0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002873b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002884f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800288ab`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180028bb2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180028ca9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180029469`

## string_xrefs

- `0x18002a1b0`: `NT TASK`
- `0x18002a6e4`: `NT TASK\`
- `0x180027cc1`: `TaskCache\Tree`
- `0x1800280d8`: `TaskCache\Tree`
- `0x180029491`: `TaskCache\Tree`
- `0x180028607`: `TaskCache\Tree\`

## pseudocode

```c
// Hidden C++ exception states: #wind=57
__int64 __fastcall RpcServer::EnumFolder(
        RpcServer *this,
        const unsigned __int16 *a2,
        bool a3,
        int a4,
        unsigned int *a5,
        unsigned int a6,
        unsigned int *a7,
        unsigned __int16 ***a8)
{
  unsigned __int16 v10; // r9
  int i; // ecx
  int v12; // edx
  bool v13; // zf
  unsigned int v14; // r8d
  __int64 v16; // rdx
  const OLECHAR *v17; // r8
  __int64 v18; // rax
  OLECHAR *v19; // rcx
  OLECHAR v20; // r9
  __int64 v21; // rcx
  OLECHAR *v22; // rax
  __int64 v23; // r9
  __int64 v24; // rax
  __int64 v25; // rdx
  _WORD *v26; // r9
  __int16 v27; // cx
  _WORD *v28; // rcx
  RPC_STATUS v29; // eax
  EventManager *v30; // rcx
  RPC_STATUS v31; // ebx
  HANDLE CurrentThread; // rax
  RTL_SRWLOCK *v33; // r14
  JobStore *v34; // r13
  HLOCAL v35; // r15
  HKEY v36; // rdi
  HKEY v37; // rax
  HKEY v38; // rbx
  BSTR v39; // rax
  struct IErrorInfo *v40; // rdx
  OLECHAR *v41; // rax
  HKEY v42; // rax
  HKEY v43; // rsi
  UINT v44; // r13d
  BSTR v45; // rax
  struct IErrorInfo *v46; // rdx
  JobStore *v47; // rax
  struct IErrorInfo *v48; // rdx
  JobStore *v49; // r15
  UINT v50; // eax
  UINT v51; // r12d
  struct IErrorInfo *v52; // rdx
  BSTR v53; // rcx
  const WCHAR *v54; // rdx
  LSTATUS v55; // eax
  unsigned int v56; // edx
  signed int v57; // esi
  HKEY v58; // rcx
  LSTATUS v59; // eax
  BYTE *v60; // rbx
  LSTATUS v61; // eax
  void *v62; // r15
  JobStore *v63; // r13
  BYTE *v64; // r12
  HKEY v65; // rdi
  HKEY v66; // rax
  HKEY v67; // rbx
  BSTR v68; // rax
  struct IErrorInfo *v69; // rdx
  OLECHAR *v70; // rax
  HKEY v71; // rax
  volatile signed __int32 *v72; // rsi
  BSTR v73; // rax
  struct IErrorInfo *v74; // rdx
  JobStore *v75; // rax
  struct IErrorInfo *v76; // rdx
  JobStore *v77; // r15
  UINT v78; // eax
  OLECHAR *v79; // rcx
  DWORD v80; // ecx
  struct IErrorInfo *v81; // rdx
  BSTR v82; // rcx
  const WCHAR *v83; // rdx
  LSTATUS v84; // eax
  unsigned int v85; // edx
  signed int v86; // esi
  HKEY v87; // rcx
  LSTATUS v88; // eax
  BYTE *v89; // rbx
  LSTATUS v90; // eax
  FolderEnumerator *v91; // rax
  FolderEnumerator *v92; // rdi
  HKEY v93; // rax
  BSTR *v94; // rbx
  BSTR v95; // rax
  struct IErrorInfo *v96; // rdx
  HKEY *v97; // r12
  JobStore *v98; // r13
  const OLECHAR *v99; // rdi
  OLECHAR *v100; // rax
  OLECHAR *v101; // rbx
  BSTR v102; // rax
  struct IErrorInfo *v103; // rdx
  OLECHAR *v104; // rdi
  struct IErrorInfo *v105; // rdx
  BSTR v106; // rcx
  HKEY v107; // rax
  HKEY v108; // rsi
  UINT v109; // r13d
  BSTR v110; // rax
  struct IErrorInfo *v111; // rdx
  JobStore *v112; // rax
  struct IErrorInfo *v113; // rdx
  UINT v114; // eax
  UINT v115; // r12d
  struct IErrorInfo *v116; // rdx
  BSTR v117; // rcx
  HKEY v118; // rax
  volatile signed __int32 *v119; // rsi
  BSTR v120; // rax
  struct IErrorInfo *v121; // rdx
  JobStore *v122; // rax
  struct IErrorInfo *v123; // rdx
  UINT v124; // eax
  OLECHAR *v125; // rcx
  DWORD v126; // ecx
  struct IErrorInfo *v127; // rdx
  BSTR v128; // rcx
  const WCHAR *v129; // rdx
  LSTATUS v130; // eax
  unsigned int v131; // edx
  signed int v132; // ebx
  FolderEnumerator *v133; // r13
  unsigned int v134; // edi
  DWORD v135; // ebx
  LSTATUS v136; // eax
  LSTATUS v137; // eax
  bool v138; // zf
  __int64 v139; // rbx
  BSTR *v140; // rax
  BSTR *v141; // rbx
  BSTR v142; // rax
  struct IErrorInfo *v143; // rdx
  OLECHAR *v144; // r10
  __int64 v145; // rcx
  OLECHAR *v146; // rdx
  __int64 v147; // r9
  OLECHAR *v148; // r8
  OLECHAR v149; // ax
  unsigned int v150; // r12d
  unsigned __int64 v151; // rax
  __int64 v152; // r15
  HKEY *v153; // rax
  HKEY *v154; // rsi
  HKEY v155; // r15
  DWORD v156; // edi
  bool Next; // al
  OLECHAR *v158; // r15
  __int64 v159; // rcx
  OLECHAR *v160; // rdx
  __int64 v161; // r9
  OLECHAR *v162; // r8
  OLECHAR v163; // ax
  OLECHAR v164; // r8
  __int64 v165; // rcx
  OLECHAR *v166; // rax
  __int64 v167; // rcx
  OLECHAR *v168; // rax
  __int64 v169; // r9
  __int64 v170; // rcx
  const OLECHAR *v171; // r8
  __int64 v172; // rdx
  OLECHAR *v173; // rax
  OLECHAR v174; // r9
  OLECHAR *v175; // rcx
  __int64 v176; // rcx
  OLECHAR *v177; // rax
  __int64 v178; // r8
  __int64 v179; // rcx
  __int64 v180; // rdx
  OLECHAR *v181; // rax
  OLECHAR v182; // r8
  OLECHAR *v183; // rcx
  JobStore *v184; // rsi
  int v185; // ebx
  OLECHAR v186; // r8
  OLECHAR *v187; // r11
  __int64 v188; // rcx
  OLECHAR *v189; // rax
  __int64 v190; // rcx
  OLECHAR *v191; // rax
  __int64 v192; // r10
  __int64 v193; // r8
  const OLECHAR *v194; // r9
  __int64 v195; // rdx
  OLECHAR *v196; // rax
  OLECHAR v197; // cx
  OLECHAR *v198; // rcx
  __int64 v199; // rcx
  OLECHAR *v200; // rax
  __int64 v201; // r9
  __int64 v202; // r8
  __int64 v203; // rdx
  OLECHAR *v204; // rax
  OLECHAR v205; // cx
  OLECHAR *v206; // rcx
  int v207; // ebx
  int v208; // r8d
  unsigned __int16 **v209; // rcx
  BOOL v210; // ebx
  FolderEnumerator *v211; // rdi
  void *v212; // rcx
  const OLECHAR *v213; // r15
  BSTR *v214; // rax
  struct IErrorInfo *v215; // rdx
  BSTR *v216; // rsi
  BSTR v217; // rax
  JobStore *v218; // r12
  HKEY v219; // rdi
  HKEY v220; // rax
  HKEY v221; // rbx
  BSTR v222; // rax
  struct IErrorInfo *v223; // rdx
  OLECHAR *v224; // r13
  struct IErrorInfo *v225; // rdx
  BSTR v226; // rcx
  const WCHAR *v227; // rdx
  LSTATUS v228; // eax
  unsigned int v229; // edx
  signed int v230; // r12d
  BYTE *v231; // r13
  HKEY v232; // rcx
  LSTATUS v233; // eax
  BYTE *v234; // rbx
  LSTATUS v235; // eax
  HKEY v236; // rax
  HKEY v237; // r12
  BSTR v238; // rax
  struct IErrorInfo *v239; // rdx
  HKEY v240; // rax
  unsigned __int64 v241; // rdx
  UINT v242; // eax
  unsigned int v243; // eax
  HANDLE v244; // rbx
  HKEY v245; // r11
  __int64 v246; // rcx
  HKEY v247; // rdx
  OLECHAR *v248; // rbx
  OLECHAR *v249; // r8
  __int64 v250; // r9
  OLECHAR v251; // ax
  __int64 v252; // r10
  OLECHAR *v253; // rcx
  char *v254; // r11
  DWORD v255; // edi
  unsigned __int64 v256; // r15
  __int64 v257; // r8
  unsigned __int64 v258; // rdx
  unsigned __int64 v259; // rcx
  unsigned __int64 v260; // rcx
  BSTR v261; // rcx
  struct IErrorInfo *v262; // rdx
  BSTR *v263; // rax
  BSTR *v264; // r12
  BSTR v265; // rax
  struct IErrorInfo *v266; // rdx
  _QWORD *v267; // rax
  HKEY v268; // r13
  unsigned __int64 v269; // rdx
  UINT v270; // eax
  unsigned int v271; // eax
  JobBucket *v272; // rax
  JobBucket *v273; // rax
  JobBucket *v274; // rbx
  void (__fastcall ***v275)(_QWORD, __int64); // rcx
  BSTR *v276; // rax
  BSTR *v277; // rbx
  BSTR *v278; // rax
  struct IErrorInfo *v279; // rdx
  BSTR *v280; // rbx
  BSTR v281; // rax
  BSTR v282; // rax
  struct IErrorInfo *v283; // rdx
  __int64 v284; // rdx
  const OLECHAR *v285; // r9
  __int64 v286; // r10
  OLECHAR *p_psz; // rax
  OLECHAR v288; // cx
  struct IErrorInfo *v289; // rdx
  BSTR v290; // rcx
  __int16 *v291; // rcx
  __int16 v292; // ax
  HKEY v293; // rbx
  __int64 v294; // rdx
  __int64 v295; // r8
  __int64 v296; // rdi
  __int64 v297; // rdi
  BSTR *v298; // rax
  struct IErrorInfo *v299; // rdx
  BSTR *v300; // rdi
  UINT v301; // r13d
  UINT v302; // eax
  UINT v303; // r12d
  JobStore *v304; // rax
  struct IErrorInfo *v305; // rdx
  UINT v306; // r15d
  UINT v307; // eax
  UINT v308; // r12d
  BSTR *v309; // rax
  BSTR v310; // rax
  struct IErrorInfo *v311; // rdx
  signed int LastError; // eax
  signed int v313; // ebx
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  const struct _GUID *lpcbData; // [rsp+28h] [rbp-D8h]
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  BYTE Data[4]; // [rsp+44h] [rbp-BCh] BYREF
  bool v318; // [rsp+48h] [rbp-B8h]
  DWORD cbData; // [rsp+4Ch] [rbp-B4h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD PrivilegeSetLength; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cchName; // [rsp+5Ch] [rbp-A4h] BYREF
  HKEY v323; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v324; // [rsp+68h] [rbp-98h] BYREF
  HKEY v325; // [rsp+70h] [rbp-90h]
  unsigned int v326; // [rsp+78h] [rbp-88h]
  void *TokenHandle; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR *v328; // [rsp+88h] [rbp-78h] BYREF
  HKEY *v329; // [rsp+90h] [rbp-70h]
  FolderEnumerator *v330; // [rsp+98h] [rbp-68h]
  JobStore *v331; // [rsp+A0h] [rbp-60h]
  int v332; // [rsp+A8h] [rbp-58h]
  JobStore *v333; // [rsp+B0h] [rbp-50h]
  HANDLE ClientToken; // [rsp+B8h] [rbp-48h]
  _QWORD *v335; // [rsp+C0h] [rbp-40h]
  HLOCAL hMem; // [rsp+C8h] [rbp-38h] BYREF
  DWORD v337; // [rsp+D0h] [rbp-30h]
  _BYTE v338[48]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v339; // [rsp+108h] [rbp+8h]
  unsigned __int16 ***v340; // [rsp+110h] [rbp+10h]
  unsigned int *v341; // [rsp+118h] [rbp+18h]
  unsigned int *v342; // [rsp+120h] [rbp+20h]
  BYTE *v343; // [rsp+128h] [rbp+28h] BYREF
  DWORD v344; // [rsp+130h] [rbp+30h]
  RTL_SRWLOCK *v345; // [rsp+138h] [rbp+38h]
  _QWORD *v346; // [rsp+140h] [rbp+40h]
  FolderEnumerator *v347; // [rsp+148h] [rbp+48h]
  HKEY *v348; // [rsp+150h] [rbp+50h]
  __int64 v349; // [rsp+158h] [rbp+58h]
  BSTR *v350; // [rsp+160h] [rbp+60h]
  BSTR *v351; // [rsp+168h] [rbp+68h]
  BSTR *v352; // [rsp+170h] [rbp+70h]
  __int128 pExceptionObject; // [rsp+178h] [rbp+78h] BYREF
  const unsigned __int16 *v354; // [rsp+188h] [rbp+88h] BYREF
  __int16 *v355; // [rsp+190h] [rbp+90h]
  __int64 v356; // [rsp+198h] [rbp+98h] BYREF
  int v357; // [rsp+1A0h] [rbp+A0h]
  __int64 v358; // [rsp+1A4h] [rbp+A4h]
  struct _GENERIC_MAPPING pSecurityDescriptor; // [rsp+1B0h] [rbp+B0h] BYREF
  struct _PRIVILEGE_SET RequiredPrivileges; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE PrivilegeSet[24]; // [rsp+1D8h] [rbp+D8h] BYREF
  __int16 *v362; // [rsp+1F0h] [rbp+F0h]
  _QWORD v363[3]; // [rsp+1F8h] [rbp+F8h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+210h] [rbp+110h] BYREF
  struct _GUID v365; // [rsp+220h] [rbp+120h] BYREF
  OLECHAR v366; // [rsp+230h] [rbp+130h] BYREF
  OLECHAR v367[263]; // [rsp+232h] [rbp+132h] BYREF
  OLECHAR psz; // [rsp+440h] [rbp+340h] BYREF
  _BYTE v369[526]; // [rsp+442h] [rbp+342h] BYREF
  WCHAR Name[264]; // [rsp+650h] [rbp+550h] BYREF

  v332 = a4;
  v318 = a3;
  v342 = a5;
  v326 = a6;
  v341 = a7;
  v340 = a8;
  if ( !a7 )
    return 2147942487LL;
  if ( !a8 )
    return 2147942487LL;
  if ( !a5 )
    return 2147942487LL;
  *a7 = 0;
  *a8 = 0;
  if ( (a4 & 0xFFFFFFFE) != 0 )
    return 2147942487LL;
  memset_0(&psz, 0, 0x20Au);
  if ( !a2 || !*a2 )
  {
    v284 = 2147483646;
    v285 = L"\\";
    v286 = 261;
    p_psz = &psz;
    v14 = 0;
    do
    {
      if ( !v284 )
        goto LABEL_46;
      v288 = *v285;
      if ( !*v285 )
        goto LABEL_46;
      ++v285;
      *p_psz++ = v288;
      --v284;
      --v286;
    }
    while ( v286 );
    --p_psz;
    v14 = -2147024774;
LABEL_46:
    *p_psz = 0;
    if ( (v14 & 0x80000000) != 0 )
      return v14;
    goto LABEL_47;
  }
  if ( *a2 != 92 )
  {
    v16 = 2147483646;
    v17 = L"\\";
    v18 = 261;
    v19 = &psz;
    while ( v16 )
    {
      v20 = *v17;
      if ( !*v17 )
        break;
      ++v17;
      *v19++ = v20;
      --v16;
      if ( !--v18 )
        return (unsigned int)-2147024774;
    }
    *v19 = 0;
  }
  v10 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= 261 )
      return (unsigned int)-2147024773;
    v12 = a2[i];
    if ( !(_WORD)v12 )
      break;
    if ( v12 == 92 )
    {
      v13 = v10 == 92;
LABEL_13:
      if ( v13 )
        return (unsigned int)-2147024773;
      goto LABEL_14;
    }
    if ( v12 == 32 )
    {
      if ( v10 == 92 )
        return (unsigned int)-2147024773;
      v13 = v10 == 0;
      goto LABEL_13;
    }
    if ( v12 != 46 )
    {
      if ( v12 == 47 )
        return (unsigned int)-2147024773;
      v13 = v12 == 58;
      goto LABEL_13;
    }
    if ( v10 == 46 || v10 == 92 && a2[i + 1] == 92 )
      return (unsigned int)-2147024773;
LABEL_14:
    v10 = a2[i];
  }
  if ( v10 == 92 && i > 1 )
    return (unsigned int)-2147024773;
  v21 = 261;
  v22 = &psz;
  do
  {
    if ( !*v22 )
      break;
    ++v22;
    --v21;
  }
  while ( v21 );
  v14 = -2147024809;
  if ( v21 )
    v14 = 0;
  v23 = 261 - v21;
  if ( !v21 )
    return v14;
  v24 = 2147483646;
  v25 = v21;
  v13 = v23 == 261;
  v26 = &v369[2 * v23 - 2];
  if ( !v13 )
  {
    do
    {
      if ( !v24 )
        break;
      v27 = *a2;
      if ( !*a2 )
        break;
      ++a2;
      *v26++ = v27;
      --v24;
      --v25;
    }
    while ( v25 );
  }
  v14 = -2147024774;
  if ( v25 )
    v14 = 0;
  v28 = v26 - 1;
  if ( v25 )
    v28 = v26;
  *v28 = 0;
  if ( !v25 )
    return v14;
LABEL_47:
  TokenHandle = 0;
  v29 = RpcImpersonateClient(0);
  v31 = v29;
  if ( v29 )
  {
    EventManager::EvtReport(v30, &IMPERSONATION_FAILURE, L"EnumFolder", v29, phkResult, lpcbData);
    BYTE8(pExceptionObject) = 0;
    *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
    v354 = &qword_1800A8718;
    v355 = 0;
    v356 = 0;
    v357 = v31;
    v358 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    RpcRevertToSelf();
  }
  else
  {
    LastError = GetLastError();
    v313 = LastError;
    if ( LastError > 0 )
      v313 = (unsigned __int16)LastError | 0x80070000;
    RpcRevertToSelf();
    if ( v313 < 0 )
    {
      wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&TokenHandle);
      return (unsigned int)v313;
    }
  }
  v33 = (RTL_SRWLOCK *)((char *)this + 16);
  v345 = v33;
  AcquireSRWLockShared(v33);
  v34 = JobStore::m_pCommonStore;
  v333 = JobStore::m_pCommonStore;
  v35 = 0;
  hMem = 0;
  v337 = 0;
  v36 = 0;
  ClientToken = 0;
  hKey = 0;
  v37 = (HKEY)HeapAlloc(g_PrivateHeap, 0, 0x18u);
  v38 = v37;
  if ( !v37 )
  {
    BYTE8(pExceptionObject) = 0;
    v354 = &qword_1800A8718;
    v355 = 0;
    v356 = 0;
    v357 = 14;
    v358 = -1;
    *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  v325 = v37;
  *((_QWORD *)v37 + 1) = 0;
  *((_DWORD *)v37 + 4) = 1;
  v39 = SysAllocString(L"TaskCache\\Tree");
  *(_QWORD *)v38 = v39;
  if ( !v39 )
    _com_raise_error(-2147024882, v40);
  v329 = (HKEY *)v38;
  if ( psz == 92 )
    v41 = (OLECHAR *)v369;
  else
    v41 = &psz;
  v328 = v41;
  if ( *v41 )
  {
    v42 = (HKEY)HeapAlloc(g_PrivateHeap, 0, 0x18u);
    v43 = v42;
    if ( !v42 )
    {
      BYTE8(pExceptionObject) = 0;
      v354 = &qword_1800A8718;
      v355 = 0;
      v356 = 0;
      v357 = 14;
      v358 = -1;
      *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    v325 = v42;
    v44 = 0;
    *((_QWORD *)v42 + 1) = 0;
    *((_DWORD *)v42 + 4) = 1;
    v45 = SysAllocString(L"\\");
    *(_QWORD *)v43 = v45;
    if ( !v45 )
      _com_raise_error(-2147024882, v46);
    v325 = v43;
    v47 = (JobStore *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
    v49 = v47;
    if ( !v47 )
    {
      BYTE8(pExceptionObject) = 0;
      v354 = &qword_1800A8718;
      v355 = 0;
      v356 = 0;
      v357 = 14;
      v358 = -1;
      *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    v331 = v47;
    *((_QWORD *)v47 + 1) = 0;
    *((_DWORD *)v47 + 4) = 1;
    if ( *(_QWORD *)v38 )
      v44 = SysStringLen(*(BSTR *)v38);
    if ( *(_QWORD *)v43 )
      v50 = SysStringLen(*(BSTR *)v43);
    else
      v50 = 0;
    *(_DWORD *)Data = v50;
    v51 = v50 + v44;
    if ( v50 + v44 < v44 || (v48 = (struct IErrorInfo *)(2LL * v51), (unsigned __int64)v48 > 0xFFFFFFFF) )
      _com_raise_error(-2147024882, v48);
    v106 = SysAllocStringByteLen(0, (UINT)v48);
    *(_QWORD *)v49 = v106;
    if ( v106 )
    {
      if ( *(_QWORD *)v38 )
        memcpy_0(v106, *(const void **)v38, 2LL * (v44 + 1));
      v105 = *(struct IErrorInfo **)v43;
      if ( *(_QWORD *)v43 )
        memcpy_0((void *)(*(_QWORD *)v49 + 2LL * v44), v105, 2LL * (unsigned int)(*(_DWORD *)Data + 1));
    }
    else if ( v51 )
    {
      _com_raise_error(-2147024882, v105);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v38 + 4, 0xFFFFFFFF) == 1 )
      _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v38, (unsigned int)v105);
    v329 = (HKEY *)v49;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v43 + 4, 0xFFFFFFFF) == 1 )
      _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v43, (unsigned int)v105);
    v107 = (HKEY)HeapAlloc(g_PrivateHeap, 0, 0x18u);
    v108 = v107;
    if ( !v107 )
    {
      BYTE8(pExceptionObject) = 0;
      v354 = &qword_1800A8718;
      v355 = 0;
      v356 = 0;
      v357 = 14;
      v358 = -1;
      *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    v325 = v107;
    v109 = 0;
    *((_QWORD *)v107 + 1) = 0;
    *((_DWORD *)v107 + 4) = 1;
    v110 = SysAllocString(v328);
    *(_QWORD *)v108 = v110;
    if ( !v110 )
      _com_raise_error(-2147024882, v111);
    v325 = v108;
    v112 = (JobStore *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
    v38 = (HKEY)v112;
    if ( !v112 )
    {
      BYTE8(pExceptionObject) = 0;
      v354 = &qword_1800A8718;
      v355 = 0;
      v356 = 0;
      v357 = 14;
      v358 = -1;
      *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    v331 = v112;
    *((_QWORD *)v112 + 1) = 0;
    *((_DWORD *)v112 + 4) = 1;
    if ( *(_QWORD *)v49 )
      v109 = SysStringLen(*(BSTR *)v49);
    if ( *(_QWORD *)v108 )
      v114 = SysStringLen(*(BSTR *)v108);
    else
      v114 = 0;
    *(_DWORD *)Data = v114;
    v115 = v114 + v109;
    if ( v114 + v109 < v109 || (v113 = (struct IErrorInfo *)(2LL * v115), (unsigned __int64)v113 > 0xFFFFFFFF) )
      _com_raise_error(-2147024882, v113);
    v53 = SysAllocStringByteLen(0, (UINT)v113);
    *(_QWORD *)v38 = v53;
    if ( v53 )
    {
      if ( *(_QWORD *)v49 )
        memcpy_0(v53, *(const void **)v49, 2LL * (v109 + 1));
      v52 = *(struct IErrorInfo **)v108;
      if ( *(_QWORD *)v108 )
        memcpy_0((void *)(*(_QWORD *)v38 + 2LL * v109), v52, 2LL * (unsigned int)(*(_DWORD *)Data + 1));
    }
    else if ( v115 )
    {
      _com_raise_error(-2147024882, v52);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v49 + 4, 0xFFFFFFFF) == 1 )
      _bstr_t::Data_t::`scalar deleting destructor'(v49, (unsigned int)v52);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v108 + 4, 0xFFFFFFFF) == 1 )
      _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v108, (unsigned int)v52);
    v34 = v333;
    v35 = hMem;
  }
  if ( v38 )
    v54 = *(const WCHAR **)v38;
  else
    v54 = 0;
  v55 = RegOpenKeyExW(*((HKEY *)v34 + 2), v54, 0, 0xF003Fu, &hKey);
  v57 = v55;
  if ( !v55 )
  {
    v36 = hKey;
    v58 = 0;
    hKey = 0;
    if ( v38 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v38 + 4, 0xFFFFFFFF) == 1 )
        _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v38, v56);
      v58 = hKey;
    }
    if ( v58 )
    {
      RegCloseKey(v58);
      hKey = 0;
    }
LABEL_93:
    Type = 3;
    cbData = 0;
    v323 = 0;
    v59 = RegQueryValueExW(v36, L"SD", 0, &Type, 0, &cbData);
    v57 = v59;
    if ( v59 )
    {
      if ( v59 > 0 )
        v57 = (unsigned __int16)v59 | 0x80070000;
    }
    else
    {
      if ( Type != 3 )
        goto LABEL_674;
      v60 = (BYTE *)LocalAlloc(0, cbData);
      v323 = (HKEY)v60;
      if ( !v60 )
      {
        tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v323);
        goto LABEL_102;
      }
      v61 = RegQueryValueExW(v36, L"SD", 0, &Type, v60, &cbData);
      v57 = v61;
      if ( !v61 )
      {
        if ( Type != 3 )
        {
          LocalFree(v60);
          v57 = -2147023537;
          goto LABEL_103;
        }
        if ( cbData )
        {
          v35 = v60;
          hMem = v60;
          v337 = cbData;
LABEL_102:
          v57 = 0;
          goto LABEL_103;
        }
LABEL_674:
        tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v323);
        v57 = -2147023537;
        goto LABEL_103;
      }
      if ( v61 > 0 )
        v57 = (unsigned __int16)v61 | 0x80070000;
      LocalFree(v60);
    }
    if ( v57 < 0 )
      goto LABEL_103;
    goto LABEL_102;
  }
  if ( v55 > 0 )
    v57 = (unsigned __int16)v55 | 0x80070000;
  if ( v38 && _InterlockedExchangeAdd((volatile signed __int32 *)v38 + 4, 0xFFFFFFFF) == 1 )
    _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v38, v56);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v57 >= 0 )
    goto LABEL_93;
LABEL_103:
  if ( v36 )
    RegCloseKey(v36);
  if ( v57 < 0 )
  {
    tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&hMem);
    ReleaseSRWLockShared(v33);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return (unsigned int)v57;
  }
  v365 = 0;
  if ( JobStore::RegGetTreeInfo(v34, &psz, &v365, 0) >= 0 )
  {
    if ( v35 )
      LocalFree(v35);
    ReleaseSRWLockShared(v33);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return 2147942403LL;
  }
  v62 = TokenHandle;
  v324 = (HKEY)TokenHandle;
  v63 = JobStore::m_pCommonStore;
  v64 = 0;
  v343 = 0;
  v344 = 0;
  v65 = 0;
  ClientToken = 0;
  hKey = 0;
  v66 = (HKEY)HeapAlloc(g_PrivateHeap, 0, 0x18u);
  v67 = v66;
  if ( !v66 )
  {
    BYTE8(pExceptionObject) = 0;
    v354 = &qword_1800A8718;
    v355 = 0;
    v356 = 0;
    v357 = 14;
    v358 = -1;
    *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  v325 = v66;
  *((_QWORD *)v66 + 1) = 0;
  *((_DWORD *)v66 + 4) = 1;
  v68 = SysAllocString(L"TaskCache\\Tree");
  *(_QWORD *)v67 = v68;
  if ( !v68 )
    _com_raise_error(-2147024882, v69);
  v329 = (HKEY *)v67;
  if ( psz == 92 )
    v70 = (OLECHAR *)v369;
  else
    v70 = &psz;
  v328 = v70;
  if ( *v70 )
  {
    v71 = (HKEY)HeapAlloc(g_PrivateHeap, 0, 0x18u);
    v72 = (volatile signed __int32 *)v71;
    if ( !v71 )
    {
      BYTE8(pExceptionObject) = 0;
      v354 = &qword_1800A8718;
      v355 = 0;
      v356 = 0;
      v357 = 14;
      v358 = -1;
      *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    v325 = v71;
    *((_QWORD *)v71 + 1) = 0;
    *((_DWORD *)v71 + 4) = 1;
    v73 = SysAllocString(L"\\");
    *(_QWORD *)v72 = v73;
    if ( !v73 )
      _com_raise_error(-2147024882, v74);
    v325 = (HKEY)v72;
    v75 = (JobStore *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
    v77 = v75;
    if ( !v75 )
    {
      BYTE8(pExceptionObject) = 0;
      v354 = &qword_1800A8718;
      v355 = 0;
      v356 = 0;
      v357 = 14;
      v358 = -1;
      *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    v331 = v75;
    *((_QWORD *)v75 + 1) = 0;
    *((_DWORD *)v75 + 4) = 1;
    if ( *(_QWORD *)v67 )
      v78 = SysStringLen(*(BSTR *)v67);
    else
      v78 = 0;
    Type = v78;
    v79 = *(OLECHAR **)v72;
    if ( *(_QWORD *)v72 )
    {
      LODWORD(v79) = SysStringLen(v79);
      v78 = Type;
    }
    *(_DWORD *)Data = (_DWORD)v79;
    v80 = v78 + (_DWORD)v79;
    cchName = v80;
    if ( v80 < v78 || (v76 = (struct IErrorInfo *)(2LL * v80), (unsigned __int64)v76 > 0xFFFFFFFF) )
      _com_raise_error(-2147024882, v76);
    v117 = SysAllocStringByteLen(0, (UINT)v76);
    *(_QWORD *)v77 = v117;
    if ( v117 )
    {
      if ( *(_QWORD *)v67 )
        memcpy_0(v117, *(const void **)v67, 2LL * (Type + 1));
      v116 = *(struct IErrorInfo **)v72;
      if ( *(_QWORD *)v72 )
        memcpy_0((void *)(*(_QWORD *)v77 + 2LL * Type), v116, 2LL * (unsigned int)(*(_DWORD *)Data + 1));
    }
    else if ( cchName )
    {
      _com_raise_error(-2147024882, v116);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v67 + 4, 0xFFFFFFFF) == 1 )
      _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v67, (unsigned int)v116);
    v329 = (HKEY *)v77;
    if ( _InterlockedExchangeAdd(v72 + 4, 0xFFFFFFFF) == 1 )
      _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v72, (unsigned int)v116);
    v118 = (HKEY)HeapAlloc(g_PrivateHeap, 0, 0x18u);
    v119 = (volatile signed __int32 *)v118;
    if ( !v118 )
    {
      BYTE8(pExceptionObject) = 0;
      v354 = &qword_1800A8718;
      v355 = 0;
      v356 = 0;
      v357 = 14;
      v358 = -1;
      *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    v325 = v118;
    *((_QWORD *)v118 + 1) = 0;
    *((_DWORD *)v118 + 4) = 1;
    v120 = SysAllocString(v328);
    *(_QWORD *)v119 = v120;
    if ( !v120 )
      _com_raise_error(-2147024882, v121);
    v325 = (HKEY)v119;
    v122 = (JobStore *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
    v67 = (HKEY)v122;
    if ( !v122 )
    {
      BYTE8(pExceptionObject) = 0;
      v354 = &qword_1800A8718;
      v355 = 0;
      v356 = 0;
      v357 = 14;
      v358 = -1;
      *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    v331 = v122;
    *((_QWORD *)v122 + 1) = 0;
    *((_DWORD *)v122 + 4) = 1;
    if ( *(_QWORD *)v77 )
      v124 = SysStringLen(*(BSTR *)v77);
    else
      v124 = 0;
    Type = v124;
    v125 = *(OLECHAR **)v119;
    if ( *(_QWORD *)v119 )
    {
      LODWORD(v125) = SysStringLen(v125);
      v124 = Type;
    }
    *(_DWORD *)Data = (_DWORD)v125;
    v126 = v124 + (_DWORD)v125;
    cchName = v126;
    if ( v126 < v124 || (v123 = (struct IErrorInfo *)(2LL * v126), (unsigned __int64)v123 > 0xFFFFFFFF) )
      _com_raise_error(-2147024882, v123);
    v82 = SysAllocStringByteLen(0, (UINT)v123);
    *(_QWORD *)v67 = v82;
    if ( v82 )
    {
      if ( *(_QWORD *)v77 )
        memcpy_0(v82, *(const void **)v77, 2LL * (Type + 1));
      v81 = *(struct IErrorInfo **)v119;
      if ( *(_QWORD *)v119 )
        memcpy_0((void *)(*(_QWORD *)v67 + 2LL * Type), v81, 2LL * (unsigned int)(*(_DWORD *)Data + 1));
    }
    else if ( cchName )
    {
      _com_raise_error(-2147024882, v81);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v77 + 4, 0xFFFFFFFF) == 1 )
      _bstr_t::Data_t::`scalar deleting destructor'(v77, (unsigned int)v81);
    if ( _InterlockedExchangeAdd(v119 + 4, 0xFFFFFFFF) == 1 )
      _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v119, (unsigned int)v81);
    v62 = v324;
  }
  if ( v67 )
    v83 = *(const WCHAR **)v67;
  else
    v83 = 0;
  v84 = RegOpenKeyExW(*((HKEY *)v63 + 2), v83, 0, 0xF003Fu, &hKey);
  v86 = v84;
  if ( !v84 )
  {
    v65 = hKey;
    v87 = 0;
    hKey = 0;
    if ( v67 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v67 + 4, 0xFFFFFFFF) == 1 )
        _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v67, v85);
      v87 = hKey;
    }
    if ( v87 )
    {
      RegCloseKey(v87);
      hKey = 0;
    }
LABEL_150:
    Type = 3;
    cbData = 0;
    v323 = 0;
    v88 = RegQueryValueExW(v65, L"SD", 0, &Type, 0, &cbData);
    v86 = v88;
    if ( v88 )
    {
      if ( v88 > 0 )
        v86 = (unsigned __int16)v88 | 0x80070000;
    }
    else
    {
      if ( Type != 3 )
        goto LABEL_686;
      v89 = (BYTE *)LocalAlloc(0, cbData);
      v323 = (HKEY)v89;
      if ( !v89 )
      {
        tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v323);
        goto LABEL_159;
      }
      v90 = RegQueryValueExW(v65, L"SD", 0, &Type, v89, &cbData);
      v86 = v90;
      if ( !v90 )
      {
        if ( Type != 3 )
        {
          LocalFree(v89);
          v86 = -2147023537;
          goto LABEL_160;
        }
        if ( cbData )
        {
          v64 = v89;
          v343 = v89;
          v344 = cbData;
LABEL_159:
          v86 = 0;
          goto LABEL_160;
        }
LABEL_686:
        tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v323);
        v86 = -2147023537;
        goto LABEL_160;
      }
      if ( v90 > 0 )
        v86 = (unsigned __int16)v90 | 0x80070000;
      LocalFree(v89);
    }
    if ( v86 < 0 )
      goto LABEL_160;
    goto LABEL_159;
  }
  if ( v84 > 0 )
    v86 = (unsigned __int16)v84 | 0x80070000;
  if ( v67 && _InterlockedExchangeAdd((volatile signed __int32 *)v67 + 4, 0xFFFFFFFF) == 1 )
    _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v67, v85);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v86 >= 0 )
    goto LABEL_150;
LABEL_160:
  if ( v65 )
    RegCloseKey(v65);
  if ( v86 < 0 )
  {
    if ( v64 )
      LocalFree(v64);
    goto LABEL_560;
  }
  Type = 0;
  memset(&RequiredPrivileges, 0, sizeof(RequiredPrivileges));
  if ( !v62 )
    goto LABEL_559;
  if ( !v64 )
    goto LABEL_559;
  RequiredPrivileges.Control = 1;
  RequiredPrivileges.PrivilegeCount = 1;
  RequiredPrivileges.Privilege[0].Attributes = 2;
  RequiredPrivileges.Privilege[0].Luid = (LUID)17LL;
  if ( !PrivilegeCheck(v62, &RequiredPrivileges, (LPBOOL)&Type) )
    goto LABEL_559;
  if ( Type
    || (*(_QWORD *)&pSecurityDescriptor.GenericRead = 0x12011600120089LL,
        pSecurityDescriptor.GenericExecute = 1179808,
        pSecurityDescriptor.GenericAll = 2032127,
        cchName = 20,
        memset(&RequiredPrivileges, 0, sizeof(RequiredPrivileges)),
        *(_DWORD *)Data = 0,
        AccessCheck(v64, v62, 1u, &pSecurityDescriptor, &RequiredPrivileges, &cchName, (LPDWORD)Data, (LPBOOL)&Type))
    && Type
    && (Data[0] & 1) != 0 )
  {
    LocalFree(v64);
  }
  else
  {
LABEL_559:
    tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v343);
LABEL_560:
    if ( (int)TaskAccessCheck(TokenHandle, &psz, 2u) < 0 )
    {
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&hMem);
      ReleaseSRWLockShared(v33);
      wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&TokenHandle);
      return 2147942403LL;
    }
  }
  v91 = (FolderEnumerator *)HeapAlloc(g_PrivateHeap, 0, 0x30u);
  v92 = v91;
  v330 = v91;
  if ( !v91 )
  {
    wmi::OutOfMemoryException::OutOfMemoryException((wmi::OutOfMemoryException *)v338);
    throw (wmi::OutOfMemoryException *)v338;
  }
  ClientToken = v91;
  *(_QWORD *)v91 = &wmi::RefBase::`vftable';
  *((_DWORD *)v91 + 2) = 0;
  *(_QWORD *)v91 = &FolderEnumerator::`vftable';
  v93 = (HKEY)HeapAlloc(g_PrivateHeap, 0, 0x18u);
  v94 = (BSTR *)v93;
  if ( !v93 )
  {
    wmi::OutOfMemoryException::OutOfMemoryException((wmi::OutOfMemoryException *)v338);
    throw (wmi::OutOfMemoryException *)v338;
  }
  v325 = v93;
  *((_QWORD *)v93 + 1) = 0;
  *((_DWORD *)v93 + 4) = 1;
  v95 = SysAllocString(&psz);
  *v94 = v95;
  if ( !v95 )
    _com_raise_error(-2147024882, v96);
  *((_QWORD *)v92 + 2) = v94;
  v97 = (HKEY *)((char *)v92 + 24);
  v329 = (HKEY *)((char *)v92 + 24);
  *((_QWORD *)v92 + 3) = 0;
  *((_BYTE *)v92 + 32) = v318;
  *((_QWORD *)v92 + 5) = 0;
  v98 = JobStore::m_pCommonStore;
  v99 = *v94;
  v100 = (OLECHAR *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
  v101 = v100;
  if ( !v100 )
  {
    wmi::OutOfMemoryException::OutOfMemoryException((wmi::OutOfMemoryException *)v338);
    throw (wmi::OutOfMemoryException *)v338;
  }
  v325 = (HKEY)v100;
  *((_QWORD *)v100 + 1) = 0;
  *((_DWORD *)v100 + 4) = 1;
  v102 = SysAllocString(L"TaskCache\\Tree\\");
  *(_QWORD *)v101 = v102;
  if ( !v102 )
    _com_raise_error(-2147024882, v103);
  v328 = v101;
  if ( !v99 )
  {
    v104 = v101;
    goto LABEL_225;
  }
  v213 = v99 + 1;
  if ( *v99 != 92 )
    v213 = v99;
  v214 = (BSTR *)operator new(0x18u);
  v216 = v214;
  v325 = (HKEY)v214;
  if ( v214 )
  {
    v214[1] = 0;
    *((_DWORD *)v214 + 4) = 1;
    v217 = SysAllocString(v213);
    *v216 = v217;
    if ( !v217 && v213 )
      _com_raise_error(-2147024882, v215);
  }
  else
  {
    v216 = 0;
  }
  v325 = (HKEY)v216;
  if ( !v216 )
    _com_raise_error(-2147024882, v215);
  v304 = (JobStore *)operator new(0x18u);
  v104 = (OLECHAR *)v304;
  v331 = v304;
  if ( v304 )
  {
    *((_QWORD *)v304 + 1) = 0;
    *((_DWORD *)v304 + 4) = 1;
    if ( *(_QWORD *)v101 )
      v306 = SysStringLen(*(BSTR *)v101);
    else
      v306 = 0;
    if ( *v216 )
      v307 = SysStringLen(*v216);
    else
      v307 = 0;
    *(_DWORD *)Data = v307;
    v308 = v307 + v306;
    if ( v307 + v306 < v306 || (v305 = (struct IErrorInfo *)(2LL * v308), (unsigned __int64)v305 > 0xFFFFFFFF) )
      _com_raise_error(-2147024882, v305);
    v128 = SysAllocStringByteLen(0, (UINT)v305);
    *(_QWORD *)v104 = v128;
    if ( v128 )
    {
      if ( *(_QWORD *)v101 )
        memcpy_0(v128, *(const void **)v101, 2LL * (v306 + 1));
      if ( *v216 )
        memcpy_0((void *)(*(_QWORD *)v104 + 2LL * v306), *v216, 2LL * (unsigned int)(*(_DWORD *)Data + 1));
    }
    else if ( v308 )
    {
      _com_raise_error(-2147024882, v127);
    }
    v97 = v329;
  }
  else
  {
    v104 = 0;
  }
  _bstr_t::Data_t::Release((_bstr_t::Data_t *)v101);
  v101 = v104;
  v328 = v104;
  _bstr_t::Data_t::Release((_bstr_t::Data_t *)v216);
  if ( v104 )
LABEL_225:
    v129 = *(const WCHAR **)v101;
  else
    v129 = 0;
  v130 = RegOpenKeyExW(*((HKEY *)v98 + 2), v129, 0, 0x20019u, v97);
  v132 = v130;
  if ( v130 )
  {
    if ( v130 > 0 )
      v132 = (unsigned __int16)v130 | 0x80070000;
    _bstr_t::~_bstr_t((_bstr_t *)&v328);
    if ( v132 < 0 )
    {
      BYTE8(pExceptionObject) = 0;
      *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
      v354 = &qword_1800A8718;
      v355 = 0;
      v356 = 0;
      v357 = v132;
      v358 = -1;
      throw (wmi::GenericException *)&pExceptionObject;
    }
  }
  else if ( v104 && _InterlockedExchangeAdd((volatile signed __int32 *)v104 + 4, 0xFFFFFFFF) == 1 )
  {
    _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v104, v131);
  }
  v133 = v330;
  *((_DWORD *)v330 + 9) = -1;
  v347 = v133;
  _InterlockedIncrement((volatile signed __int32 *)v133 + 2);
  v366 = 0;
  memset_0(v367, 0, 0x208u);
  v134 = *v342;
  if ( !*v342 )
    goto LABEL_258;
  while ( 2 )
  {
    v135 = *((_DWORD *)v133 + 9) + 1;
    while ( 2 )
    {
      hKey = 0;
      cbData = 0;
      Type = 0;
      *(_DWORD *)Data = 0;
      cchName = 261;
      v136 = RegEnumKeyExW(*v97, v135, Name, &cchName, 0, 0, 0, 0);
      if ( v136 == 259 )
      {
        if ( hKey )
          RegCloseKey(hKey);
        *v341 = 0;
        *v340 = 0;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v133 + 2, 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(FolderEnumerator *, __int64))v133)(v133, 1);
        if ( hMem )
          LocalFree(hMem);
        ReleaseSRWLockShared(v33);
        if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(TokenHandle);
        return 1;
      }
      if ( v136 )
      {
        BYTE8(pExceptionObject) = 0;
        *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
        v354 = &qword_1800A8718;
        v355 = 0;
        v356 = 0;
        v357 = v136;
        v358 = -1;
        throw (wmi::GenericException *)&pExceptionObject;
      }
      v137 = RegOpenKeyExW(*v97, Name, 0, 0x20019u, &hKey);
      if ( v137 )
      {
        BYTE8(pExceptionObject) = 0;
        *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
        v354 = &qword_1800A8718;
        v355 = 0;
        v356 = 0;
        v357 = v137;
        v358 = -1;
        throw (wmi::GenericException *)&pExceptionObject;
      }
      cbData = 1;
      Type = 0;
      if ( RegQueryValueExW(hKey, L"Id", 0, &cbData, 0, &Type) == 2 )
      {
        v138 = *((_BYTE *)v133 + 32) == 0;
      }
      else
      {
        if ( cbData != 1 )
        {
          BYTE8(pExceptionObject) = 0;
          *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
          v354 = &qword_1800A8718;
          v355 = 0;
          v356 = 0;
          v357 = 1359;
          v358 = -1;
          throw (wmi::GenericException *)&pExceptionObject;
        }
        if ( Type > 0x50 )
        {
          BYTE8(pExceptionObject) = 0;
          *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
          v354 = &qword_1800A8718;
          v355 = 0;
          v356 = 0;
          v357 = 1359;
          v358 = -1;
          throw (wmi::GenericException *)&pExceptionObject;
        }
        if ( *((_BYTE *)v133 + 32) )
          goto LABEL_239;
        cbData = 4;
        Type = 4;
        if ( RegQueryValueExW(hKey, L"Index", 0, &cbData, Data, &Type) )
        {
          BYTE8(pExceptionObject) = 0;
          *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
          v354 = &qword_1800A8718;
          v355 = 0;
          v356 = 0;
          v357 = 1359;
          v358 = -1;
          throw (wmi::GenericException *)&pExceptionObject;
        }
        if ( cbData != 4 )
        {
          BYTE8(pExceptionObject) = 0;
          *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
          v354 = &qword_1800A8718;
          v355 = 0;
          v356 = 0;
          v357 = 1359;
          v358 = -1;
          throw (wmi::GenericException *)&pExceptionObject;
        }
        if ( Type != 4 )
        {
          BYTE8(pExceptionObject) = 0;
          *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
          v354 = &qword_1800A8718;
          v355 = 0;
          v356 = 0;
          v357 = 1359;
          v358 = -1;
          throw (wmi::GenericException *)&pExceptionObject;
        }
        v138 = *(_DWORD *)Data == 0;
      }
      if ( v138 )
      {
LABEL_239:
        ++v135;
        if ( hKey )
          RegCloseKey(hKey);
        continue;
      }
      break;
    }
    if ( hKey )
      RegCloseKey(hKey);
    *((_DWORD *)v133 + 9) = v135;
    v139 = *((_QWORD *)v133 + 5);
    if ( v139 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v139 + 16), 0xFFFFFFFF) == 1 )
      {
        if ( *(_QWORD *)v139 )
        {
          SysFreeString(*(BSTR *)v139);
          *(_QWORD *)v139 = 0;
        }
        v212 = *(void **)(v139 + 8);
        if ( v212 )
        {
          operator delete(v212);
          *(_QWORD *)(v139 + 8) = 0;
        }
        HeapFree(g_PrivateHeap, 0, (LPVOID)v139);
      }
      *((_QWORD *)v133 + 5) = 0;
    }
    v140 = (BSTR *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
    v141 = v140;
    if ( !v140 )
    {
      wmi::OutOfMemoryException::OutOfMemoryException((wmi::OutOfMemoryException *)v338);
      throw (wmi::OutOfMemoryException *)v338;
    }
    ClientToken = v140;
    v140[1] = 0;
    *((_DWORD *)v140 + 4) = 1;
    v142 = SysAllocString(Name);
    *v141 = v142;
    if ( !v142 )
      _com_raise_error(-2147024882, v143);
    *((_QWORD *)v133 + 5) = v141;
    v144 = *v141;
    if ( &v366 == *v141 )
      goto LABEL_257;
    if ( psz )
    {
      v145 = 2147483646;
      v146 = &psz;
      v147 = 261;
      v148 = &v366;
      while ( v145 )
      {
        v149 = *v146;
        if ( !*v146 )
          break;
        ++v146;
        *v148++ = v149;
        --v145;
        if ( !--v147 )
        {
          *(v148 - 1) = 0;
          goto LABEL_257;
        }
      }
      *v148 = 0;
    }
    if ( !v144 )
      goto LABEL_307;
    v164 = *v144;
    if ( !*v144 )
      goto LABEL_307;
    v165 = 261;
    v166 = &v366;
    do
    {
      if ( !*v166 )
        break;
      ++v166;
      --v165;
    }
    while ( v165 );
    if ( !v165 )
      goto LABEL_257;
    if ( *(_WORD *)&v365.Data4[2 * (261 - v165) + 6] != 92 )
    {
      if ( v164 == 92 )
        goto LABEL_296;
      v167 = 261;
      v168 = &v366;
      do
      {
        if ( !*v168 )
          break;
        ++v168;
        --v167;
      }
      while ( v167 );
      v169 = 261 - v167;
      if ( v167 )
      {
        v170 = 2147483646;
        v171 = L"\\";
        v172 = 261 - v169;
        v173 = &v367[v169 - 1];
        if ( v169 != 261 )
        {
          do
          {
            if ( !v170 )
              break;
            v174 = *v171;
            if ( !*v171 )
              break;
            ++v171;
            *v173++ = v174;
            --v170;
            --v172;
          }
          while ( v172 );
        }
        v175 = v173 - 1;
        if ( v172 )
          v175 = v173;
        *v175 = 0;
        if ( v172 )
          goto LABEL_296;
      }
      goto LABEL_257;
    }
    if ( v164 == 92 )
      ++v144;
LABEL_296:
    v176 = 261;
    v177 = &v366;
    do
    {
      if ( !*v177 )
        break;
      ++v177;
      --v176;
    }
    while ( v176 );
    v178 = 261 - v176;
    if ( v176 )
    {
      v179 = 2147483646;
      v180 = 261 - v178;
      v181 = &v367[v178 - 1];
      if ( v178 != 261 )
      {
        do
        {
          if ( !v179 )
            break;
          v182 = *v144;
          if ( !*v144 )
            break;
          ++v144;
          *v181++ = v182;
          --v179;
          --v180;
        }
        while ( v180 );
      }
      v183 = v181 - 1;
      if ( v180 )
        v183 = v181;
      *v183 = 0;
      if ( v180 )
      {
LABEL_307:
        *(_OWORD *)&RequiredPrivileges.PrivilegeCount = 0;
        v184 = v333;
        if ( JobStore::RegGetTreeInfo(v333, &v366, (struct _GUID *)&RequiredPrivileges, 0) >= 0 )
        {
          if ( (int)TaskAccessCheck(TokenHandle, &v366, 1u) < 0 )
            goto LABEL_257;
          v185 = 1;
        }
        else
        {
          v185 = 0;
          if ( (int)TaskAccessCheck(TokenHandle, &v366, 1u) < 0 && (int)TaskAccessCheck(TokenHandle, &v366, 2u) < 0 )
            goto LABEL_257;
        }
        if ( (v332 & 1) == 0 && v185 )
        {
          JobMoniker::JobMoniker((JobMoniker *)&pExceptionObject, &v366, (const struct _GUID *)&RequiredPrivileges);
          v323 = 0;
          if ( (int)JobStore::RegOpenTaskKey(v184, (struct JobMoniker *)&pExceptionObject, &v323, 0x20019u) >= 0 )
          {
            Triggers::Trigulator::Trigulator((Triggers::Trigulator *)PrivilegeSet);
            if ( (int)Triggers::Trigulator::StreamIn((Triggers::Trigulator *)PrivilegeSet, v323, 2u, 0) >= 0
              && (int)Triggers::Trigulator::GetBucket(
                        (Triggers::Trigulator *)PrivilegeSet,
                        (struct JobMoniker *)&pExceptionObject) >= 0
              && (*(_DWORD *)(v356 + 16) & 0x800000) != 0 )
            {
              Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)PrivilegeSet);
              wmi::AutoRegKey::Close((wmi::AutoRegKey *)&v323);
              JobMoniker::~JobMoniker((JobMoniker *)&pExceptionObject);
              goto LABEL_257;
            }
            Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)PrivilegeSet);
          }
          wmi::AutoRegKey::Close((wmi::AutoRegKey *)&v323);
          JobMoniker::~JobMoniker((JobMoniker *)&pExceptionObject);
        }
        --v134;
      }
    }
LABEL_257:
    if ( v134 )
      continue;
    break;
  }
LABEL_258:
  v150 = v326;
  if ( v326 - 1 > 0x1FF )
  {
    v150 = 512;
    v326 = 512;
  }
  v151 = 528LL * v150;
  if ( v151 > 0x10000 )
    LODWORD(v151) = 0x10000;
  v152 = (unsigned int)v151;
  v153 = (HKEY *)HeapAlloc(g_PrivateHeap, 0, (unsigned int)v151);
  v329 = v153;
  if ( !v153 )
  {
    wmi::OutOfMemoryException::OutOfMemoryException((wmi::OutOfMemoryException *)v338);
    throw (wmi::OutOfMemoryException *)v338;
  }
  v154 = v153;
  v348 = v153;
  v328 = (OLECHAR *)&v153[v150];
  v155 = (HKEY)((v152 - 8 * (unsigned __int64)v150) >> 1);
  v318 = 0;
  v156 = 0;
  cbData = 0;
  hKey = v155;
  while ( 2 )
  {
    while ( 2 )
    {
      if ( v156 >= v150 || !v155 )
        goto LABEL_360;
      Next = FolderEnumerator::FindNext(v133);
      v318 = Next;
      if ( !Next )
        goto LABEL_361;
      v158 = (OLECHAR *)*((_QWORD *)v133 + 5);
      if ( v158 )
      {
        v158 = *(OLECHAR **)v158;
        if ( &v366 == v158 )
          goto LABEL_275;
      }
      if ( psz )
      {
        v159 = 2147483646;
        v160 = &psz;
        v161 = 261;
        v162 = &v366;
        while ( v159 )
        {
          v163 = *v160;
          if ( !*v160 )
            break;
          ++v160;
          *v162++ = v163;
          --v159;
          if ( !--v161 )
          {
            *(v162 - 1) = 0;
            goto LABEL_275;
          }
        }
        *v162 = 0;
      }
      if ( v158 )
      {
        v186 = *v158;
        if ( *v158 )
        {
          v187 = v158;
          v188 = 261;
          v189 = &v366;
          do
          {
            if ( !*v189 )
              break;
            ++v189;
            --v188;
          }
          while ( v188 );
          if ( !v188 )
            goto LABEL_275;
          if ( *(_WORD *)&v365.Data4[2 * (261 - v188) + 6] != 92 )
          {
            if ( v186 == 92 )
              goto LABEL_331;
            v190 = 261;
            v191 = &v366;
            do
            {
              if ( !*v191 )
                break;
              ++v191;
              --v190;
            }
            while ( v190 );
            v192 = 261 - v190;
            if ( v190 )
            {
              v193 = 2147483646;
              v194 = L"\\";
              v195 = v190;
              v196 = &v367[v192 - 1];
              if ( v192 != 261 )
              {
                do
                {
                  if ( !v193 )
                    break;
                  v197 = *v194;
                  if ( !*v194 )
                    break;
                  ++v194;
                  *v196++ = v197;
                  --v193;
                  --v195;
                }
                while ( v195 );
              }
              v198 = v196 - 1;
              if ( v195 )
                v198 = v196;
              *v198 = 0;
              if ( v195 )
                goto LABEL_331;
            }
            goto LABEL_275;
          }
          if ( v186 == 92 )
            v187 = v158 + 1;
LABEL_331:
          v199 = 261;
          v200 = &v366;
          do
          {
            if ( !*v200 )
              break;
            ++v200;
            --v199;
          }
          while ( v199 );
          v201 = 261 - v199;
          if ( !v199 )
            goto LABEL_275;
          v202 = 2147483646;
          v203 = v199;
          v204 = &v367[v201 - 1];
          if ( v201 != 261 )
          {
            do
            {
              if ( !v202 )
                break;
              v205 = *v187;
              if ( !*v187 )
                break;
              ++v187;
              *v204++ = v205;
              --v202;
              --v203;
            }
            while ( v203 );
          }
          v206 = v204 - 1;
          if ( v203 )
            v206 = v204;
          *v206 = 0;
          if ( !v203 )
          {
LABEL_275:
            v155 = hKey;
            continue;
          }
        }
      }
      break;
    }
    *(_OWORD *)&RequiredPrivileges.PrivilegeCount = 0;
    if ( JobStore::RegGetTreeInfo(v333, &v366, (struct _GUID *)&RequiredPrivileges, 0) < 0 )
    {
      v207 = 0;
      if ( (int)TaskAccessCheck(TokenHandle, &v366, 1u) >= 0 || (int)TaskAccessCheck(TokenHandle, &v366, 2u) >= 0 )
        goto LABEL_453;
      goto LABEL_275;
    }
    ClientToken = TokenHandle;
    v218 = JobStore::m_pCommonStore;
    v331 = JobStore::m_pCommonStore;
    *(_QWORD *)&pSecurityDescriptor.GenericRead = 0;
    pSecurityDescriptor.GenericExecute = 0;
    v219 = 0;
    v349 = 0;
    v323 = 0;
    v220 = (HKEY)HeapAlloc(g_PrivateHeap, 0, 0x18u);
    v221 = v220;
    if ( !v220 )
    {
      wmi::OutOfMemoryException::OutOfMemoryException((wmi::OutOfMemoryException *)v338);
      throw (wmi::OutOfMemoryException *)v338;
    }
    v325 = v220;
    *((_QWORD *)v220 + 1) = 0;
    *((_DWORD *)v220 + 4) = 1;
    v222 = SysAllocString(L"TaskCache\\Tree");
    *(_QWORD *)v221 = v222;
    if ( !v222 )
      _com_raise_error(-2147024882, v223);
    v325 = v221;
    if ( v366 == 92 )
      v224 = v367;
    else
      v224 = &v366;
    if ( *v224 )
    {
      v236 = (HKEY)HeapAlloc(g_PrivateHeap, 0, 0x18u);
      v237 = v236;
      if ( !v236 )
      {
        wmi::OutOfMemoryException::OutOfMemoryException((wmi::OutOfMemoryException *)v338);
        throw (wmi::OutOfMemoryException *)v338;
      }
      v324 = v236;
      *((_QWORD *)v236 + 1) = 0;
      *((_DWORD *)v236 + 4) = 1;
      v238 = SysAllocString(L"\\");
      *(_QWORD *)v237 = v238;
      if ( !v238 )
        _com_raise_error(-2147024882, v239);
      v346 = v237;
      v240 = (HKEY)HeapAlloc(g_PrivateHeap, 0, 0x18u);
      v324 = v240;
      if ( !v240 )
      {
        wmi::OutOfMemoryException::OutOfMemoryException((wmi::OutOfMemoryException *)v338);
        throw (wmi::OutOfMemoryException *)v338;
      }
      v335 = v240;
      *((_QWORD *)v240 + 1) = 0;
      *((_DWORD *)v240 + 4) = 1;
      if ( *(_QWORD *)v221 )
        v241 = SysStringLen(*(BSTR *)v221);
      else
        v241 = 0;
      Type = v241;
      if ( *(_QWORD *)v237 )
      {
        v242 = SysStringLen(*(BSTR *)v237);
        v241 = Type;
      }
      else
      {
        v242 = 0;
      }
      *(_DWORD *)Data = v242;
      v243 = v241 + v242;
      if ( v243 < (unsigned int)v241 || (v241 = 2LL * v243, v241 > 0xFFFFFFFF) )
        _com_raise_error(-2147024882, (struct IErrorInfo *)v241);
      v261 = SysAllocStringByteLen(0, v241);
      v262 = (struct IErrorInfo *)v324;
      *(_QWORD *)v324 = v261;
      if ( v261 )
      {
        if ( *(_QWORD *)v221 )
        {
          memcpy_0(v261, *(const void **)v221, 2LL * (Type + 1));
          v262 = (struct IErrorInfo *)v324;
        }
        if ( *(_QWORD *)v237 )
          memcpy_0((char *)v262->lpVtbl + 2 * Type, *(const void **)v237, 2LL * (unsigned int)(*(_DWORD *)Data + 1));
      }
      else if ( Type + *(_DWORD *)Data )
      {
        _com_raise_error(-2147024882, v262);
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v221 + 4, 0xFFFFFFFF) == 1 )
        _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v221, (unsigned int)v262);
      v325 = v324;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v237 + 4, 0xFFFFFFFF) == 1 )
        _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v237, (unsigned int)v262);
      v263 = (BSTR *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
      v264 = v263;
      if ( !v263 )
      {
        wmi::OutOfMemoryException::OutOfMemoryException((wmi::OutOfMemoryException *)v338);
        throw (wmi::OutOfMemoryException *)v338;
      }
      v335 = v263;
      v263[1] = 0;
      *((_DWORD *)v263 + 4) = 1;
      v265 = SysAllocString(v224);
      *v264 = v265;
      if ( !v265 )
        _com_raise_error(-2147024882, v266);
      v335 = v264;
      v267 = HeapAlloc(g_PrivateHeap, 0, 0x18u);
      v221 = (HKEY)v267;
      if ( !v267 )
      {
        wmi::OutOfMemoryException::OutOfMemoryException((wmi::OutOfMemoryException *)v338);
        throw (wmi::OutOfMemoryException *)v338;
      }
      v346 = v267;
      v267[1] = 0;
      *((_DWORD *)v267 + 4) = 1;
      v268 = v324;
      if ( *(_QWORD *)v324 )
        v269 = SysStringLen(*(BSTR *)v324);
      else
        v269 = 0;
      Type = v269;
      if ( *v264 )
      {
        v270 = SysStringLen(*v264);
        v269 = Type;
      }
      else
      {
        v270 = 0;
      }
      *(_DWORD *)Data = v270;
      v271 = v269 + v270;
      if ( v271 < (unsigned int)v269 || (v269 = 2LL * v271, v269 > 0xFFFFFFFF) )
        _com_raise_error(-2147024882, (struct IErrorInfo *)v269);
      v226 = SysAllocStringByteLen(0, v269);
      *(_QWORD *)v221 = v226;
      if ( v226 )
      {
        if ( *(_QWORD *)v268 )
          memcpy_0(v226, *(const void **)v268, 2LL * (Type + 1));
        v225 = (struct IErrorInfo *)*v264;
        if ( *v264 )
          memcpy_0((void *)(*(_QWORD *)v221 + 2LL * Type), v225, 2LL * (unsigned int)(*(_DWORD *)Data + 1));
      }
      else if ( Type + *(_DWORD *)Data )
      {
        _com_raise_error(-2147024882, v225);
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v268 + 4, 0xFFFFFFFF) == 1 )
        _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v268, (unsigned int)v225);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v264 + 4, 0xFFFFFFFF) == 1 )
        _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v264, (unsigned int)v225);
      v218 = v331;
    }
    if ( v221 )
      v227 = *(const WCHAR **)v221;
    else
      v227 = 0;
    v228 = RegOpenKeyExW(*((HKEY *)v218 + 2), v227, 0, 0xF003Fu, &v323);
    v230 = v228;
    if ( v228 )
    {
      if ( v228 > 0 )
        v230 = (unsigned __int16)v228 | 0x80070000;
      if ( v221 && _InterlockedExchangeAdd((volatile signed __int32 *)v221 + 4, 0xFFFFFFFF) == 1 )
        _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v221, v229);
      if ( v323 )
        RegCloseKey(v323);
      if ( v230 < 0 )
      {
        v231 = *(BYTE **)&pSecurityDescriptor.GenericRead;
        goto LABEL_442;
      }
    }
    else
    {
      v219 = v323;
      v232 = 0;
      v323 = 0;
      if ( v221 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v221 + 4, 0xFFFFFFFF) == 1 )
          _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v221, v229);
        v232 = v323;
      }
      if ( v232 )
        RegCloseKey(v232);
    }
    Type = 3;
    *(_DWORD *)Data = 0;
    v324 = 0;
    v233 = RegQueryValueExW(v219, L"SD", 0, &Type, 0, (LPDWORD)Data);
    v230 = v233;
    if ( v233 )
    {
      if ( v233 > 0 )
        v230 = (unsigned __int16)v233 | 0x80070000;
      goto LABEL_439;
    }
    if ( Type != 3 )
      goto LABEL_719;
    v234 = (BYTE *)LocalAlloc(0, *(unsigned int *)Data);
    v324 = (HKEY)v234;
    if ( !v234 )
    {
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v324);
      v231 = *(BYTE **)&pSecurityDescriptor.GenericRead;
LABEL_441:
      v230 = 0;
      goto LABEL_442;
    }
    v235 = RegQueryValueExW(v219, L"SD", 0, &Type, v234, (LPDWORD)Data);
    v230 = v235;
    if ( v235 )
    {
      if ( v235 > 0 )
        v230 = (unsigned __int16)v235 | 0x80070000;
      LocalFree(v234);
LABEL_439:
      if ( v230 < 0 )
        goto LABEL_721;
      v231 = *(BYTE **)&pSecurityDescriptor.GenericRead;
      goto LABEL_441;
    }
    if ( Type == 3 )
    {
      if ( *(_DWORD *)Data )
      {
        v231 = v234;
        *(_QWORD *)&pSecurityDescriptor.GenericRead = v234;
        pSecurityDescriptor.GenericExecute = *(_DWORD *)Data;
        goto LABEL_441;
      }
LABEL_719:
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v324);
    }
    else
    {
      LocalFree(v234);
    }
    v230 = -2147023537;
LABEL_721:
    v231 = *(BYTE **)&pSecurityDescriptor.GenericRead;
LABEL_442:
    if ( v219 )
      RegCloseKey(v219);
    if ( v230 < 0 )
    {
      v156 = cbData;
      v155 = hKey;
      v150 = v326;
      if ( v231 )
      {
        LocalFree(v231);
        *(_QWORD *)&pSecurityDescriptor.GenericRead = 0;
      }
      goto LABEL_447;
    }
    *(_DWORD *)Data = 0;
    memset(PrivilegeSet, 0, 20);
    v244 = ClientToken;
    if ( !ClientToken )
      goto LABEL_549;
    if ( !v231 )
      goto LABEL_549;
    *(_QWORD *)PrivilegeSet = 0x100000001LL;
    *(_DWORD *)&PrivilegeSet[16] = 2;
    *(_QWORD *)&PrivilegeSet[8] = 17;
    if ( !PrivilegeCheck(ClientToken, (PPRIVILEGE_SET)PrivilegeSet, (LPBOOL)Data)
      || !*(_DWORD *)Data
      && ((GenericMapping.GenericRead = 1179785,
           GenericMapping.GenericWrite = 1179926,
           GenericMapping.GenericExecute = 1179808,
           GenericMapping.GenericAll = 2032127,
           PrivilegeSetLength = 20,
           memset(PrivilegeSet, 0, 20),
           cchName = 0,
           !AccessCheck(
              v231,
              v244,
              1u,
              &GenericMapping,
              (PPRIVILEGE_SET)PrivilegeSet,
              &PrivilegeSetLength,
              &cchName,
              (LPBOOL)Data))
       || !*(_DWORD *)Data
       || (cchName & 1) == 0) )
    {
LABEL_549:
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&pSecurityDescriptor);
      v156 = cbData;
      v155 = hKey;
LABEL_474:
      v150 = v326;
LABEL_447:
      v133 = v330;
      continue;
    }
    break;
  }
  v207 = 1;
  LocalFree(v231);
  *(_QWORD *)&pSecurityDescriptor.GenericRead = 0;
LABEL_453:
  if ( (v332 & 1) == 0 && v207 )
  {
    *(_QWORD *)&PrivilegeSet[16] = 0;
    v363[0] = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_qS_guid_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        v208,
        (unsigned int)PrivilegeSet,
        (__int64)&v366,
        (__int64)&RequiredPrivileges);
    }
    v272 = (JobBucket *)operator new(0xD8u);
    v335 = v272;
    if ( v272 )
    {
      v273 = JobBucket::JobBucket(v272);
      v274 = v273;
      if ( v273 )
        _InterlockedIncrement((volatile signed __int32 *)v273 + 2);
    }
    else
    {
      v274 = 0;
    }
    v275 = (void (__fastcall ***)(_QWORD, __int64))v363[0];
    if ( v363[0] && _InterlockedExchangeAdd((volatile signed __int32 *)(v363[0] + 8LL), 0xFFFFFFFF) == 1 )
      (**v275)(v275, 1);
    v363[0] = v274;
    if ( v366 == 92 || v366 == 47 )
    {
      _bstr_t::~_bstr_t((_bstr_t *)&PrivilegeSet[16]);
      v276 = (BSTR *)operator new(0x18u);
      v277 = v276;
      v351 = v276;
      if ( v276 )
      {
        v276[1] = 0;
        *((_DWORD *)v276 + 4) = 1;
        v282 = SysAllocString(L"NT TASK");
        *v277 = v282;
        if ( !v282 )
          _com_raise_error(-2147024882, v283);
      }
    }
    else
    {
      _bstr_t::~_bstr_t((_bstr_t *)&PrivilegeSet[16]);
      v309 = (BSTR *)operator new(0x18u);
      v277 = v309;
      v350 = v309;
      if ( v309 )
      {
        v309[1] = 0;
        *((_DWORD *)v309 + 4) = 1;
        v310 = SysAllocString(L"NT TASK\\");
        *v277 = v310;
        if ( !v310 )
          _com_raise_error(-2147024882, v311);
      }
    }
    *(_QWORD *)&PrivilegeSet[16] = v277;
    v278 = (BSTR *)operator new(0x18u);
    v280 = v278;
    v352 = v278;
    if ( v278 )
    {
      v278[1] = 0;
      *((_DWORD *)v278 + 4) = 1;
      v281 = SysAllocString(&v366);
      *v280 = v281;
      if ( !v281 )
        _com_raise_error(-2147024882, v279);
    }
    else
    {
      v280 = 0;
    }
    v335 = v280;
    if ( !v280 )
      _com_raise_error(-2147024882, v279);
    v298 = (BSTR *)operator new(0x18u);
    v300 = v298;
    v343 = (BYTE *)v298;
    if ( v298 )
    {
      v298[1] = 0;
      *((_DWORD *)v298 + 4) = 1;
      if ( *(_QWORD *)&PrivilegeSet[16] && **(_QWORD **)&PrivilegeSet[16] )
        v301 = SysStringLen(**(BSTR **)&PrivilegeSet[16]);
      else
        v301 = 0;
      if ( *v280 )
        v302 = SysStringLen(*v280);
      else
        v302 = 0;
      *(_DWORD *)Data = v302;
      v303 = v302 + v301;
      if ( v302 + v301 < v301 || (v299 = (struct IErrorInfo *)(2LL * v303), (unsigned __int64)v299 > 0xFFFFFFFF) )
        _com_raise_error(-2147024882, v299);
      v290 = SysAllocStringByteLen(0, (UINT)v299);
      *v300 = v290;
      if ( v290 )
      {
        if ( *(_QWORD *)&PrivilegeSet[16] && **(_QWORD **)&PrivilegeSet[16] )
          memcpy_0(v290, **(const void ***)&PrivilegeSet[16], 2LL * (v301 + 1));
        if ( *v280 )
          memcpy_0(&(*v300)[v301], *v280, 2LL * (unsigned int)(*(_DWORD *)Data + 1));
      }
      else if ( v303 )
      {
        _com_raise_error(-2147024882, v289);
      }
    }
    else
    {
      v300 = 0;
    }
    _bstr_t::~_bstr_t((_bstr_t *)&PrivilegeSet[16]);
    *(_QWORD *)&PrivilegeSet[16] = v300;
    _bstr_t::Data_t::Release((_bstr_t::Data_t *)v280);
    v291 = *(__int16 **)&PrivilegeSet[16];
    if ( *(_QWORD *)&PrivilegeSet[16] )
      v291 = **(__int16 ***)&PrivilegeSet[16];
    v292 = *v291;
    if ( !*v291 )
    {
LABEL_597:
      *(_OWORD *)PrivilegeSet = *(_OWORD *)&RequiredPrivileges.PrivilegeCount;
      *(_DWORD *)(v363[0] + 60LL) = 0;
      v324 = 0;
      if ( (int)JobStore::RegOpenTaskKey(v333, (struct JobMoniker *)PrivilegeSet, &v324, 0x20019u) < 0 )
      {
        v293 = v324;
      }
      else
      {
        Triggers::Trigulator::Trigulator((Triggers::Trigulator *)v338);
        v293 = v324;
        if ( (int)Triggers::Trigulator::StreamIn((Triggers::Trigulator *)v338, v324, 2u, 0) >= 0 )
        {
          v296 = v339;
          if ( v339 )
          {
            v354 = 0;
            v356 = 0;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_qqq(*((_QWORD *)WPP_GLOBAL_Control + 2), v294, v295, &pExceptionObject, PrivilegeSet, v339);
            }
            if ( v296 )
              _InterlockedIncrement((volatile signed __int32 *)(v296 + 8));
            wmi::AutoRef<JobBucket>::Release(&v356);
            v356 = v296;
            _bstr_t::operator=(&v354, &PrivilegeSet[16]);
            v355 = v362;
            pExceptionObject = *(_OWORD *)PrivilegeSet;
            if ( v354 )
              _InterlockedIncrement((volatile signed __int32 *)v354 + 4);
            _bstr_t::~_bstr_t((_bstr_t *)&PrivilegeSet[16]);
            *(_QWORD *)&PrivilegeSet[16] = v354;
            v362 = v355;
            *(_OWORD *)PrivilegeSet = pExceptionObject;
            v297 = v356;
            if ( v356 )
              _InterlockedIncrement((volatile signed __int32 *)(v356 + 8));
            wmi::AutoRef<JobBucket>::Release(v363);
            v363[0] = v297;
            JobMoniker::~JobMoniker((JobMoniker *)&pExceptionObject);
            if ( (*(_DWORD *)(v363[0] + 16LL) & 0x800000) != 0 )
            {
              Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)v338);
              if ( v293 )
                RegCloseKey(v293);
              wmi::AutoRef<JobBucket>::Release(v363);
              _bstr_t::~_bstr_t((_bstr_t *)&PrivilegeSet[16]);
              v156 = cbData;
              v155 = hKey;
              goto LABEL_474;
            }
          }
        }
        Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)v338);
      }
      if ( v293 )
        RegCloseKey(v293);
      wmi::AutoRef<JobBucket>::Release(v363);
      _bstr_t::~_bstr_t((_bstr_t *)&PrivilegeSet[16]);
      goto LABEL_455;
    }
    while ( 1 )
    {
      if ( v292 == 47 )
      {
        *v291 = 92;
      }
      else if ( v292 != 92 )
      {
        ++v291;
        goto LABEL_595;
      }
      v362 = ++v291;
LABEL_595:
      v292 = *v291;
      if ( !*v291 )
      {
        v33 = v345;
        goto LABEL_597;
      }
    }
  }
LABEL_455:
  v245 = hKey;
  if ( (unsigned __int64)hKey <= 0x7FFFFFFF )
  {
    v246 = 2147483646;
    v247 = hKey;
    v248 = v328;
    v249 = v328;
    v250 = 0;
    do
    {
      if ( !v246 )
        break;
      v251 = *v158;
      if ( !*v158 )
        break;
      ++v158;
      *v249++ = v251;
      --v246;
      ++v250;
      v247 = (HKEY)((char *)v247 - 1);
    }
    while ( v247 );
    v252 = v250 - 1;
    if ( v247 )
      v252 = v250;
    v253 = v249 - 1;
    if ( v247 )
      v253 = v249;
    *v253 = 0;
    if ( !v247 )
      goto LABEL_359;
    v254 = (char *)v245 - v252;
    v255 = cbData;
    v329[cbData] = (HKEY)v248;
    v156 = v255 + 1;
    cbData = v156;
    v256 = (unsigned __int64)(v254 - 1);
    if ( !v254 )
      v256 = 0;
    v257 = (__int64)&v248[v252 + 1];
    if ( !v254 )
      v257 = (__int64)&v248[v252];
    v258 = ((((v257 - (__int64)v248) >> 1) + 3 + (((((v257 - (__int64)v248) >> 1) + 3) >> 63) & 3))
          & 0xFFFFFFFFFFFFFFFCuLL)
         - ((v257 - (__int64)v248) >> 1);
    v259 = v256;
    if ( v258 < v256 )
      v259 = ((((v257 - (__int64)v248) >> 1) + 3 + (((((v257 - (__int64)v248) >> 1) + 3) >> 63) & 3))
            & 0xFFFFFFFFFFFFFFFCuLL)
           - ((v257 - (__int64)v248) >> 1);
    v328 = (OLECHAR *)(v257 + 2 * v259);
    v260 = v256;
    v155 = (HKEY)(v256 - v258);
    if ( v258 >= v260 )
      v155 = 0;
    hKey = v155;
    goto LABEL_474;
  }
  *v328 = 0;
LABEL_359:
  v156 = cbData;
LABEL_360:
  Next = v318;
LABEL_361:
  if ( v156 )
  {
    v154 = 0;
    v209 = (unsigned __int16 **)v329;
  }
  else
  {
    v209 = 0;
  }
  *v340 = v209;
  *v341 = v156;
  *v342 += v156;
  v210 = Next;
  if ( v154 )
    HeapFree(g_PrivateHeap, 0, v154);
  v211 = v330;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v330 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(FolderEnumerator *, __int64))v211)(v211, 1);
  if ( hMem )
    LocalFree(hMem);
  ReleaseSRWLockShared(v33);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return v210;
}

```

## disassembly

```asm
0x180027990  push    rbp
0x180027992  push    rbx
0x180027993  push    rsi
0x180027994  push    rdi
0x180027995  push    r12
0x180027997  push    r13
0x180027999  push    r14
0x18002799b  push    r15
0x18002799d  lea     rbp, [rsp-778h]
0x1800279a5  sub     rsp, 878h
0x1800279ac  mov     rax, cs:__security_cookie
0x1800279b3  xor     rax, rsp
0x1800279b6  mov     [rbp+7B0h+var_50], rax
0x1800279bd  mov     [rbp+7B0h+var_808], r9d
0x1800279c1  mov     [rsp+8B0h+var_868], r8b
0x1800279c6  mov     rbx, rdx
0x1800279c9  mov     r14, rcx
0x1800279cc  mov     rax, [rbp+7B0h+arg_20]
0x1800279d3  mov     [rbp+7B0h+var_790], rax
0x1800279d7  mov     ecx, [rbp+7B0h+arg_28]
0x1800279dd  mov     [rsp+8B0h+var_838], ecx
0x1800279e1  mov     rdx, [rbp+7B0h+arg_30]
0x1800279e8  mov     [rbp+7B0h+var_798], rdx
0x1800279ec  mov     rcx, [rbp+7B0h+arg_38]
0x1800279f3  mov     [rbp+7B0h+var_7A0], rcx
0x1800279f7  test    rdx, rdx
0x1800279fa  jz      loc_18002B1F1
0x180027a00  test    rcx, rcx
0x180027a03  jz      loc_18002B1F1
0x180027a09  test    rax, rax
0x180027a0c  jz      loc_18002B1F1
0x180027a12  xor     esi, esi
0x180027a14  mov     [rdx], esi
0x180027a16  mov     [rcx], rsi
0x180027a19  test    r9d, 0FFFFFFFEh
0x180027a20  jnz     loc_18002B1F1
0x180027a26  xor     edx, edx; Val
0x180027a28  mov     r8d, 20Ah; Size
0x180027a2e  lea     rcx, [rbp+7B0h+psz]; void *
0x180027a35  call    memset_0
0x180027a3a  test    rbx, rbx
0x180027a3d  jz      loc_18002A1EC
0x180027a43  movzx   eax, word ptr [rbx]
0x180027a46  test    ax, ax
0x180027a49  jz      loc_18002A1EC
0x180027a4f  cmp     ax, 5Ch ; '\'
0x180027a53  jnz     loc_180027AE5
0x180027a59  mov     r9d, esi
0x180027a5c  mov     ecx, esi
0x180027a5e  xchg    ax, ax
0x180027a60  cmp     ecx, 105h
0x180027a66  jge     short loc_180027A8F
0x180027a68  movsxd  r10, ecx
0x180027a6b  movzx   edx, word ptr [rbx+r10*2]
0x180027a70  test    dx, dx
0x180027a73  jz      loc_180027B3C
0x180027a79  mov     r8d, edx
0x180027a7c  cmp     edx, 5Ch ; '\'
0x180027a7f  jnz     short loc_180027ABC
0x180027a81  cmp     r9w, dx
0x180027a85  jz      short loc_180027A8F
0x180027a87  movzx   r9d, dx
0x180027a8b  inc     ecx
0x180027a8d  jmp     short loc_180027A60
0x180027a8f  mov     r8d, 8007007Bh
0x180027a95  mov     eax, r8d
0x180027a98  mov     rcx, [rbp+7B0h+var_50]
0x180027a9f  xor     rcx, rsp; StackCookie
0x180027aa2  call    __security_check_cookie
0x180027aa7  add     rsp, 878h
0x180027aae  pop     r15
0x180027ab0  pop     r14
0x180027ab2  pop     r13
0x180027ab4  pop     r12
0x180027ab6  pop     rdi
0x180027ab7  pop     rsi
0x180027ab8  pop     rbx
0x180027ab9  pop     rbp
0x180027aba  retn
0x180027abc  sub     r8d, 20h ; ' '
0x180027ac0  jnz     short loc_180027ACF
0x180027ac2  cmp     r9w, 5Ch ; '\'
0x180027ac7  jz      short loc_180027A8F
0x180027ac9  test    r9w, r9w
0x180027acd  jmp     short loc_180027A85
0x180027acf  sub     r8d, 0Eh
0x180027ad3  jz      loc_18002A7C2
0x180027ad9  sub     r8d, 1
0x180027add  jz      short loc_180027A8F
0x180027adf  cmp     r8d, 0Bh
0x180027ae3  jmp     short loc_180027A85
0x180027ae5  mov     edx, 7FFFFFFEh
0x180027aea  lea     r8, asc_1800A7EC0; "\\"
0x180027af1  mov     eax, 105h
0x180027af6  lea     rcx, [rbp+7B0h+psz]
0x180027afd  nop     dword ptr [rax]
0x180027b00  test    rdx, rdx
0x180027b03  jz      short loc_180027B34
0x180027b05  movzx   r9d, word ptr [r8]
0x180027b09  test    r9w, r9w
0x180027b0d  jz      short loc_180027B2F
0x180027b0f  add     r8, 2
0x180027b13  mov     [rcx], r9w
0x180027b17  add     rcx, 2
0x180027b1b  dec     rdx
0x180027b1e  sub     rax, 1
0x180027b22  jnz     short loc_180027B00
0x180027b24  mov     r8d, 8007007Ah
0x180027b2a  jmp     loc_180027A95
0x180027b2f  test    rax, rax
0x180027b32  jz      short loc_180027B24
0x180027b34  mov     [rcx], si
0x180027b37  jmp     loc_180027A59
0x180027b3c  cmp     r9w, 5Ch ; '\'
0x180027b41  jz      loc_18002A7E9
0x180027b47  mov     ecx, 105h
0x180027b4c  lea     rax, [rbp+7B0h+psz]
0x180027b53  cmp     [rax], si
0x180027b56  jz      short loc_180027B62
0x180027b58  add     rax, 2
0x180027b5c  sub     rcx, 1
0x180027b60  jnz     short loc_180027B53
0x180027b62  mov     r8d, 80070057h
0x180027b68  test    rcx, rcx
0x180027b6b  cmovnz  r8d, esi
0x180027b6f  mov     r9d, 105h
0x180027b75  sub     r9, rcx
0x180027b78  test    rcx, rcx
0x180027b7b  cmovz   r9, rsi
0x180027b7f  jz      loc_180027A95
0x180027b85  mov     eax, 7FFFFFFEh
0x180027b8a  mov     edx, 105h
0x180027b8f  sub     rdx, r9
0x180027b92  lea     r9, [rbp+r9*2+7B0h+psz]
0x180027b9a  jz      short loc_180027BC2
0x180027b9c  nop     dword ptr [rax+00h]
0x180027ba0  test    rax, rax
0x180027ba3  jz      short loc_180027BC2
0x180027ba5  movzx   ecx, word ptr [rbx]
0x180027ba8  test    cx, cx
0x180027bab  jz      short loc_180027BC2
0x180027bad  add     rbx, 2
0x180027bb1  mov     [r9], cx
0x180027bb5  add     r9, 2
0x180027bb9  dec     rax
0x180027bbc  sub     rdx, 1
0x180027bc0  jnz     short loc_180027BA0
0x180027bc2  mov     r8d, 8007007Ah
0x180027bc8  test    rdx, rdx
0x180027bcb  cmovnz  r8d, esi
0x180027bcf  lea     rcx, [r9-2]
0x180027bd3  cmovnz  rcx, r9
0x180027bd7  mov     [rcx], si
0x180027bda  jz      loc_180027A95
0x180027be0  jmp     short loc_180027BF7
0x180027be2  test    r10, r10
0x180027be5  jz      loc_18002A23A
0x180027beb  mov     [rax], si
0x180027bee  test    r8d, r8d
0x180027bf1  js      loc_180027A95
0x180027bf7  mov     [rbp+7B0h+TokenHandle], rsi
0x180027bfb  xor     ecx, ecx; BindingHandle
0x180027bfd  call    cs:__imp_RpcImpersonateClient
0x180027c04  nop     dword ptr [rax+rax+00h]
0x180027c09  mov     ebx, eax
0x180027c0b  test    eax, eax
0x180027c0d  jnz     loc_18002A7F7
0x180027c13  call    cs:__imp_GetCurrentThread
0x180027c1a  nop     dword ptr [rax+rax+00h]
0x180027c1f  mov     rcx, rax; ThreadHandle
0x180027c22  lea     r9, [rbp+7B0h+TokenHandle]; TokenHandle
0x180027c26  mov     edx, 8; DesiredAccess
0x180027c2b  mov     r8d, 1; OpenAsSelf
0x180027c31  call    cs:__imp_OpenThreadToken
0x180027c38  nop     dword ptr [rax+rax+00h]
0x180027c3d  test    eax, eax
0x180027c3f  jz      loc_18002A76F
0x180027c45  call    cs:__imp_RpcRevertToSelf
0x180027c4c  nop     dword ptr [rax+rax+00h]
0x180027c51  add     r14, 10h
0x180027c55  mov     [rbp+7B0h+var_778], r14
0x180027c59  mov     rcx, r14; SRWLock
0x180027c5c  call    cs:__imp_AcquireSRWLockShared
0x180027c63  nop     dword ptr [rax+rax+00h]
0x180027c68  nop
0x180027c69  mov     r13, cs:?m_pCommonStore@JobStore@@0PEAV1@EA; JobStore * JobStore::m_pCommonStore
0x180027c70  mov     [rbp+7B0h+var_800], r13
0x180027c74  mov     r15, rsi
0x180027c77  mov     [rbp+7B0h+hMem], rsi
0x180027c7b  mov     [rbp+7B0h+var_7E0], esi
0x180027c7e  mov     rdi, rsi
0x180027c81  mov     [rbp+7B0h+ClientToken], rsi
0x180027c85  mov     [rsp+8B0h+hKey], rsi
0x180027c8a  xor     edx, edx; dwFlags
0x180027c8c  mov     r8d, 18h; dwBytes
0x180027c92  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180027c99  call    cs:__imp_HeapAlloc
0x180027ca0  nop     dword ptr [rax+rax+00h]
0x180027ca5  mov     rbx, rax
0x180027ca8  test    rax, rax
0x180027cab  jz      loc_18002A85D
0x180027cb1  mov     [rsp+8B0h+var_840], rax
0x180027cb6  mov     [rax+8], rsi
0x180027cba  mov     dword ptr [rax+10h], 1
0x180027cc1  lea     rcx, psz; "TaskCache\\Tree"
0x180027cc8  call    cs:__imp_SysAllocString
0x180027ccf  nop     dword ptr [rax+rax+00h]
0x180027cd4  mov     [rbx], rax
0x180027cd7  test    rax, rax
0x180027cda  jz      loc_18002863B
0x180027ce0  mov     [rbp+7B0h+var_820], rbx
0x180027ce4  cmp     [rbp+7B0h+psz], 5Ch ; '\'
0x180027cec  jnz     loc_18002A16E
0x180027cf2  lea     rax, [rbp+7B0h+var_46E]
0x180027cf9  mov     [rbp+7B0h+var_828], rax
0x180027cfd  mov     r12d, 0FFFFFFFFh
0x180027d03  cmp     word ptr [rax], 0
0x180027d07  jz      loc_180027E83
0x180027d0d  xor     edx, edx; dwFlags
0x180027d0f  mov     r8d, 18h; dwBytes
0x180027d15  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180027d1c  call    cs:__imp_HeapAlloc
0x180027d23  nop     dword ptr [rax+rax+00h]
0x180027d28  mov     rsi, rax
0x180027d2b  test    rax, rax
0x180027d2e  jz      loc_18002A8B1
0x180027d34  mov     [rsp+8B0h+var_840], rax
0x180027d39  xor     r13d, r13d
0x180027d3c  mov     [rax+8], r13
0x180027d40  mov     dword ptr [rax+10h], 1
0x180027d47  lea     rcx, asc_1800A7EC0; "\\"
0x180027d4e  call    cs:__imp_SysAllocString
0x180027d55  nop     dword ptr [rax+rax+00h]
0x180027d5a  mov     [rsi], rax
0x180027d5d  test    rax, rax
0x180027d60  jz      loc_180029DAB
0x180027d66  mov     [rsp+8B0h+var_840], rsi
0x180027d6b  xor     edx, edx; dwFlags
0x180027d6d  mov     r8d, 18h; dwBytes
0x180027d73  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180027d7a  call    cs:__imp_HeapAlloc
0x180027d81  nop     dword ptr [rax+rax+00h]
0x180027d86  mov     r15, rax
0x180027d89  test    rax, rax
0x180027d8c  jz      loc_18002A907
0x180027d92  mov     [rbp+7B0h+var_810], rax
0x180027d96  mov     [rax+8], r13
0x180027d9a  mov     dword ptr [rax+10h], 1
0x180027da1  mov     rcx, [rbx]; pbstr
0x180027da4  test    rcx, rcx
0x180027da7  jz      short loc_180027DB8
0x180027da9  call    cs:__imp_SysStringLen
0x180027db0  nop     dword ptr [rax+rax+00h]
0x180027db5  mov     r13d, eax
0x180027db8  mov     rcx, [rsi]; pbstr
0x180027dbb  test    rcx, rcx
0x180027dbe  jz      loc_18002A95B
0x180027dc4  call    cs:__imp_SysStringLen
0x180027dcb  nop     dword ptr [rax+rax+00h]
0x180027dd0  mov     dword ptr [rsp+8B0h+Data], eax
0x180027dd4  lea     r12d, [rax+r13]
0x180027dd8  cmp     r12d, r13d
0x180027ddb  jb      short loc_180027DF1
0x180027ddd  mov     edx, r12d
0x180027de0  add     rdx, rdx; struct IErrorInfo *
0x180027de3  mov     eax, 0FFFFFFFFh
0x180027de8  cmp     rdx, rax
0x180027deb  jbe     loc_180028651
0x180027df1  mov     ecx, 8007000Eh; int
0x180027df6  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180027dfc  xor     ecx, ecx; psz
0x180027dfe  call    cs:__imp_SysAllocStringByteLen
0x180027e05  nop     dword ptr [rax+rax+00h]
0x180027e0a  mov     rcx, rax; void *
0x180027e0d  mov     [rbx], rax
0x180027e10  test    rax, rax
0x180027e13  jz      loc_180029E3B
0x180027e19  mov     rdx, [r15]; Src
0x180027e1c  test    rdx, rdx
0x180027e1f  jz      short loc_180027E2D
0x180027e21  lea     r8d, [r13+1]
0x180027e25  add     r8, r8; Size
0x180027e28  call    memcpy_0
0x180027e2d  mov     rdx, [rsi]; Src
0x180027e30  test    rdx, rdx
0x180027e33  jz      short loc_180027E50
0x180027e35  mov     r8d, dword ptr [rsp+8B0h+Data]
0x180027e3a  inc     r8d
0x180027e3d  add     r8, r8; Size
0x180027e40  mov     ecx, r13d
0x180027e43  mov     rax, [rbx]
0x180027e46  lea     rcx, [rax+rcx*2]; void *
0x180027e4a  call    memcpy_0
0x180027e4f  nop
0x180027e50  mov     r12d, 0FFFFFFFFh
0x180027e56  mov     eax, r12d
0x180027e59  lock xadd [r15+10h], eax
0x180027e5f  cmp     eax, 1
0x180027e62  jz      loc_180029FAA
0x180027e68  mov     eax, r12d
  ... truncated ...
```
