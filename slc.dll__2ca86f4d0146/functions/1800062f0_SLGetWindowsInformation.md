# SLGetWindowsInformation

- ea: `0x1800062f0`
- end: `0x180010cb2`
- name: `SLGetWindowsInformation`
- size: `43458`
- prototype: `HRESULT __stdcall(PCWSTR pwszValueName, SLDATATYPE *peDataType, UINT *pcbValue, PBYTE *ppbValue)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x180001090`
- `0x1800010c0`
- `0x180006240`
- `0x180006270`
- `0x180006290`
- `0x1800062c0`
- `0x1800062f0`
- `0x180010dc8`
- `0x18001f926`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006371`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006458`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006580`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800069cb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006eb6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006fdb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000701c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800070d9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000728e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007583`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007874`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800078e3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007937`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007992`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000843d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008aae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008b48`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008c74`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008f0d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009290`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000993e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009a49`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009aac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009b55`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009d79`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a38e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a79d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a811`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a876`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a8fb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b3cf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b532`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b775`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b98e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c1c7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c804`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c941`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c998`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ca39`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cc35`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cfa3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d3e2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d44e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d4bb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d521`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000df8d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e6fe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e83b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ecf6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f34e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f454`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f4a8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f54f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f733`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fa0a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fe12`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fe7d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fee5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ff4d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800108f1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006371`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006458`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006580`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800069cb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006eb6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006fdb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000701c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800070d9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000728e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007583`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007874`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800078e3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007937`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007992`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000843d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008aae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008b48`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008c74`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008f0d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009290`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000993e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009a49`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009aac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009b55`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009d79`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a38e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a79d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a811`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a876`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a8fb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b3cf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b532`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b775`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b98e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c1c7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c804`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c941`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c998`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ca39`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cc35`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cfa3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d3e2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d44e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d4bb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d521`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000df8d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e6fe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e83b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ecf6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f34e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f454`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f4a8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f54f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f733`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fa0a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fe12`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fe7d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fee5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ff4d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800108f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000635b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000644a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006570`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800069b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006e5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006ea4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006ed9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006f08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006f36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006f64`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006f85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006fc6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007008`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800070c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007130`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000715f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000718e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800071b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000727d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800073be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007572`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007862`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800078d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007925`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007981`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800079fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a57`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b1d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b4b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b79`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b9a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000842b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008546`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008577`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800085a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800085d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800085f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008615`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008633`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008663`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008691`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800086bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800086e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800086fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800089f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008a10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008a4c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008a6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008a9c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008b33`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008c65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008e37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008e5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008e75`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008e8e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008ef7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000927f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009354`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000992c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009961`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009990`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800099be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800099ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009a0d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009a34`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009a98`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b42`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009bc2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009bf1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c20`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c42`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009d68`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009d9c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009dcd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009dfc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009e2b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009e4d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009e6a`

## string_xrefs

- `0x180007622`: `ntdll.dll`
- `0x18000a4ff`: `ntdll.dll`
- `0x18000d13c`: `ntdll.dll`
- `0x18000fb84`: `ntdll.dll`

## pseudocode

```c
HRESULT __stdcall SLGetWindowsInformation(
        PCWSTR pwszValueName,
        SLDATATYPE *peDataType,
        UINT *pcbValue,
        PBYTE *ppbValue)
{
  HRESULT v5; // ebx
  HANDLE ProcessHeap; // rax
  _OWORD *v7; // r14
  int v8; // r12d
  int v9; // esi
  int v10; // r15d
  int v11; // edi
  UINT v12; // esi
  int v13; // r13d
  HANDLE v14; // rax
  _QWORD *v15; // rax
  unsigned int v16; // r10d
  void *v17; // r11
  unsigned int v18; // eax
  _DWORD *v19; // r14
  int v20; // r9d
  unsigned int v21; // ecx
  unsigned int v22; // eax
  unsigned int v23; // edx
  unsigned int v24; // eax
  unsigned int v25; // ecx
  __int64 v26; // rsi
  HANDLE v27; // rax
  _DWORD *v28; // rax
  void *v29; // r11
  void *v30; // r10
  int v31; // ecx
  _DWORD *v32; // rdx
  unsigned int v33; // eax
  unsigned __int64 v34; // rsi
  unsigned int v35; // eax
  unsigned int v36; // r10d
  _DWORD *v37; // rdx
  unsigned int i; // ecx
  unsigned int v39; // eax
  unsigned int j; // ecx
  unsigned int v41; // eax
  SIZE_T v42; // rax
  unsigned int v43; // r10d
  void *v44; // r11
  __int64 v45; // r8
  unsigned int v46; // r8d
  unsigned int v47; // ecx
  _DWORD *v48; // rdx
  unsigned int k; // ecx
  unsigned int v50; // eax
  void *v51; // rcx
  unsigned int v52; // r10d
  _DWORD *v53; // rdx
  unsigned int m; // r9d
  __int64 v55; // rax
  _DWORD *v56; // rax
  __int64 v57; // r9
  _DWORD *v58; // rdx
  void *v59; // rsi
  unsigned int v60; // ecx
  unsigned int v61; // eax
  unsigned int v62; // r9d
  HANDLE v63; // rax
  char *v64; // rcx
  void *v65; // rax
  unsigned int v66; // edx
  char *v67; // r9
  __int64 v68; // rdx
  unsigned __int8 v69; // al
  unsigned __int64 v70; // rcx
  int v71; // r8d
  int v72; // r14d
  _BYTE *v73; // rax
  void *v74; // rdi
  unsigned __int8 *v75; // r12
  unsigned int v76; // r9d
  int v77; // r13d
  int v78; // ecx
  int v79; // esi
  int v80; // r11d
  int v81; // esi
  int v82; // r11d
  int v83; // r10d
  int v84; // r8d
  int v85; // r10d
  int v86; // r9d
  int v87; // r8d
  unsigned int v88; // edx
  int v89; // ecx
  int v90; // edx
  int v91; // r8d
  int v92; // r9d
  int v93; // edx
  unsigned int v94; // r8d
  unsigned int v95; // r9d
  int v96; // edx
  int v97; // r8d
  int v98; // r9d
  int v99; // edx
  int v100; // r8d
  int v101; // r10d
  int v102; // edx
  int v103; // r9d
  unsigned int v104; // r8d
  int v105; // r10d
  int v106; // edx
  int v107; // r9d
  int v108; // r10d
  HANDLE v109; // rax
  HANDLE v110; // rax
  int v111; // esi
  void *v112; // rax
  HANDLE v113; // rax
  LPVOID v114; // rax
  HANDLE v115; // rax
  HANDLE v116; // rax
  HANDLE v117; // rax
  HANDLE v118; // rax
  _DWORD *v119; // rcx
  _QWORD *v120; // rsi
  HANDLE v121; // rax
  void *v122; // rax
  HANDLE v123; // rax
  _OWORD *v124; // rax
  HANDLE v125; // rax
  _QWORD *v126; // rax
  LPVOID v127; // rax
  HANDLE v128; // rax
  HANDLE v129; // rax
  HANDLE v130; // rax
  HANDLE v131; // rax
  unsigned int v132; // eax
  unsigned int v133; // edx
  unsigned int v134; // r8d
  unsigned int v135; // edx
  unsigned int v136; // eax
  unsigned int v137; // esi
  HANDLE v138; // rax
  _DWORD *v139; // rax
  const void **v140; // rsi
  _DWORD *v141; // rcx
  unsigned int *v142; // rdx
  _DWORD *v143; // rcx
  void *v144; // r11
  void *v145; // r8
  HANDLE v146; // rax
  _DWORD *v147; // rax
  int n; // r10d
  _DWORD *v149; // r9
  int v150; // ebx
  unsigned int v151; // edx
  unsigned int v152; // esi
  HANDLE v153; // rax
  void *v154; // rax
  void *v155; // r10
  void *v156; // rdx
  void *v157; // r9
  void *v158; // r11
  void *v159; // rcx
  signed int LastError; // eax
  NTSTATUS (__stdcall *NtQuerySystemInformation)(SYSTEM_INFORMATION_CLASS, PVOID, ULONG, PULONG); // rax
  int v162; // eax
  unsigned int v163; // edx
  void *v164; // rax
  size_t v165; // rsi
  char *v166; // rcx
  char *v167; // r11
  SIZE_T v168; // r8
  _DWORD *v169; // rcx
  unsigned int v170; // r11d
  unsigned __int64 v171; // r9
  unsigned int v172; // ecx
  unsigned int v173; // r9d
  unsigned int v174; // ecx
  HANDLE v175; // rax
  _QWORD *v176; // r14
  HANDLE v177; // rax
  void *v178; // rax
  int v179; // esi
  HANDLE v180; // rax
  void *v181; // rax
  size_t v182; // rax
  unsigned int v183; // esi
  HANDLE v184; // rax
  void *v185; // rax
  SIZE_T v186; // rax
  HANDLE v187; // rax
  HANDLE v188; // rax
  HANDLE v189; // rax
  HANDLE v190; // rax
  size_t *v191; // rcx
  HANDLE v192; // rax
  HANDLE v193; // rax
  HANDLE v194; // rax
  HANDLE v195; // rax
  unsigned __int8 v196; // al
  unsigned __int64 v197; // rdx
  int v198; // edi
  int v199; // r13d
  int v200; // eax
  unsigned __int8 *v201; // rbx
  int v202; // ecx
  unsigned int v203; // r10d
  __int64 v204; // r8
  unsigned int v205; // r9d
  int v206; // ecx
  unsigned int v207; // r11d
  _BYTE *v208; // rsi
  unsigned int v209; // edi
  char v210; // bl
  __int64 v211; // r9
  int v212; // r11d
  unsigned __int8 *v213; // rbx
  unsigned int v214; // r10d
  _BYTE *v215; // r13
  SIZE_T v216; // r12
  int v217; // r15d
  int v218; // eax
  int v219; // ecx
  int v220; // r14d
  int v221; // esi
  int v222; // r14d
  int v223; // edx
  int v224; // esi
  int v225; // r8d
  int v226; // r9d
  unsigned int v227; // edx
  int v228; // r8d
  int v229; // r9d
  unsigned int v230; // edx
  int v231; // r8d
  int v232; // r10d
  int v233; // r11d
  unsigned int v234; // r9d
  int v235; // r8d
  unsigned int v236; // r9d
  int v237; // r10d
  int v238; // r11d
  int v239; // edx
  int v240; // r8d
  int v241; // r9d
  int v242; // edx
  int v243; // r10d
  int v244; // r8d
  unsigned int v245; // edx
  unsigned int v246; // r8d
  unsigned __int64 ii; // rcx
  void *v248; // rcx
  void *v249; // rdx
  void *v250; // r9
  void *v251; // r11
  void *v252; // r10
  unsigned __int64 v253; // rsi
  void *v254; // rax
  _DWORD *v255; // rax
  __int64 v256; // rax
  void *v257; // rcx
  HANDLE v258; // rax
  HANDLE v259; // rax
  _QWORD *v260; // rax
  HANDLE v261; // rax
  HANDLE v262; // rax
  HANDLE v263; // rax
  HANDLE v264; // rax
  HANDLE v265; // rax
  HANDLE v266; // rax
  _QWORD *v267; // rax
  HANDLE v268; // rax
  HANDLE v269; // rax
  HANDLE v270; // rax
  HANDLE v271; // rax
  HANDLE v272; // rax
  int *v273; // rsi
  _DWORD *v274; // rax
  int kk; // r10d
  _DWORD *v276; // rcx
  size_t *v277; // r10
  _DWORD *v278; // rax
  unsigned int mm; // esi
  _DWORD *v280; // rcx
  unsigned int *v281; // rax
  unsigned int nn; // r10d
  unsigned int *v283; // rcx
  _DWORD *v284; // rax
  unsigned int i1; // r10d
  _DWORD *v286; // rcx
  _DWORD *v287; // r10
  _DWORD *v288; // rax
  unsigned int i2; // esi
  _DWORD *v290; // rcx
  int *v291; // r10
  HANDLE v292; // rax
  HANDLE v293; // rax
  HANDLE v294; // rax
  HANDLE v295; // rax
  void *v296; // rsi
  HANDLE v297; // rax
  _OWORD *v298; // rax
  void *v299; // r14
  HANDLE v300; // rax
  _QWORD *v301; // rax
  void *v302; // r9
  int v303; // ecx
  int v304; // eax
  int v305; // r10d
  int v306; // eax
  int v307; // r10d
  int v308; // eax
  int v309; // r10d
  unsigned int v310; // esi
  HANDLE v311; // rax
  LPVOID v312; // r9
  _DWORD *v313; // r9
  unsigned int v314; // r11d
  _DWORD *v315; // rax
  unsigned int v316; // eax
  unsigned int v317; // r10d
  unsigned int *v318; // r9
  HANDLE v319; // rax
  HANDLE v320; // rax
  HANDLE v321; // rax
  HANDLE v322; // rax
  HLOCAL v323; // rax
  HANDLE v324; // rax
  _OWORD *v325; // rax
  void *v326; // r14
  void *v327; // rsi
  __int64 v328; // rdx
  __int64 v329; // r9
  unsigned int *v330; // r9
  unsigned int v331; // r11d
  unsigned int v332; // eax
  unsigned int v333; // r10d
  unsigned int *v334; // r9
  __int64 v335; // rdx
  __int64 v336; // r9
  _DWORD *v337; // r9
  __int64 v338; // r11
  unsigned int *v339; // r10
  unsigned int v340; // r9d
  unsigned int i3; // r11d
  __int64 v342; // rdx
  __int64 v343; // r10
  int v344; // r11d
  _DWORD *v345; // r10
  _QWORD *v346; // rax
  size_t v347; // rcx
  __int64 v348; // rcx
  unsigned int v349; // r10d
  unsigned int v350; // r9d
  unsigned int v351; // r10d
  int v352; // esi
  unsigned int v353; // r9d
  unsigned int v354; // eax
  unsigned int v355; // esi
  HANDLE v356; // rax
  LPVOID v357; // rcx
  int v358; // esi
  void *v359; // rcx
  void *v360; // r9
  unsigned int v361; // r10d
  int v362; // r11d
  SIZE_T v363; // rcx
  HANDLE v364; // rax
  _BYTE *v365; // rsi
  unsigned __int64 v366; // rdx
  unsigned __int8 v367; // al
  unsigned __int64 v368; // rcx
  int v369; // r9d
  unsigned int v370; // r11d
  int v371; // ebx
  int v372; // r15d
  unsigned __int8 *v373; // rdi
  int v374; // r10d
  unsigned int v375; // r10d
  unsigned int v376; // r8d
  unsigned int v377; // ecx
  int v378; // r11d
  _BYTE *v379; // rbx
  char v380; // di
  int v381; // r8d
  int v382; // r13d
  SIZE_T v383; // r12
  unsigned __int8 *v384; // rdi
  _BYTE *v385; // r15
  int v386; // r14d
  int v387; // eax
  int v388; // ecx
  int v389; // esi
  int v390; // r11d
  int v391; // esi
  int v392; // r11d
  int v393; // r9d
  int v394; // r10d
  int v395; // r8d
  int v396; // r9d
  unsigned int v397; // edx
  int v398; // r8d
  int v399; // ecx
  int v400; // edx
  int v401; // r8d
  int v402; // r9d
  int v403; // edx
  unsigned int v404; // r8d
  unsigned int v405; // r9d
  int v406; // edx
  int v407; // r8d
  int v408; // r9d
  int v409; // edx
  int v410; // r8d
  int v411; // r10d
  int v412; // edx
  int v413; // r9d
  unsigned int v414; // r8d
  int v415; // eax
  int v416; // edx
  unsigned int v417; // ecx
  unsigned int v418; // r8d
  int v419; // r10d
  int v420; // edx
  HANDLE v421; // rax
  _DWORD *v422; // rax
  int v423; // esi
  void *v424; // rax
  HANDLE v425; // rax
  _QWORD *v426; // rax
  HANDLE v427; // rax
  HANDLE v428; // rax
  HANDLE v429; // rax
  HANDLE v430; // rax
  unsigned int *v431; // r10
  HANDLE v432; // rax
  void *v433; // rcx
  _DWORD *v434; // rsi
  HANDLE v435; // rax
  _OWORD *v436; // rax
  HANDLE v437; // rax
  _QWORD *v438; // rax
  _QWORD *v439; // rax
  HANDLE v440; // rax
  HANDLE v441; // rax
  HANDLE v442; // rax
  HANDLE v443; // rax
  __int64 v444; // rdx
  int v445; // esi
  __int64 v446; // r10
  __int64 v447; // rdx
  __int64 v448; // r10
  __int64 v449; // rdx
  void *v450; // r10
  unsigned int v451; // esi
  HANDLE v452; // rax
  void *v453; // rcx
  HANDLE v454; // rax
  _QWORD *v455; // rax
  HANDLE v456; // rax
  HANDLE v457; // rax
  HANDLE v458; // rax
  HANDLE v459; // rax
  HANDLE v460; // rax
  HANDLE v461; // rax
  _QWORD *v462; // rax
  HANDLE v463; // rax
  HANDLE v464; // rax
  HANDLE v465; // rax
  HANDLE v466; // rax
  HANDLE v467; // rax
  int v468; // eax
  _DWORD *v469; // r10
  unsigned int v470; // r11d
  int *v471; // rcx
  LPVOID v472; // rcx
  int v473; // r9d
  unsigned int v474; // r10d
  int v475; // r9d
  void *v476; // r9
  void *v477; // r11
  void *v478; // rcx
  void *v479; // r9
  const void **v480; // r10
  void *v481; // r11
  const void **v482; // r9
  LPVOID v483; // rcx
  unsigned int *v484; // r10
  LPVOID v485; // rcx
  unsigned int *v486; // r9
  void *v487; // rax
  HANDLE v488; // rax
  int v489; // eax
  __int64 v490; // rcx
  void *v491; // r9
  void *v492; // r10
  void *v493; // r11
  LPVOID v494; // rcx
  int i4; // edx
  unsigned int v496; // r9d
  LPVOID v497; // rcx
  unsigned int v498; // esi
  HANDLE v499; // rax
  void *v500; // r9
  unsigned int i5; // r9d
  unsigned int v502; // r10d
  int v503; // r9d
  unsigned int v504; // r11d
  unsigned int v505; // r10d
  signed int v506; // eax
  NTSTATUS (__stdcall *ProcAddress)(SYSTEM_INFORMATION_CLASS, PVOID, ULONG, PULONG); // rax
  int v508; // eax
  unsigned int v509; // r10d
  int v510; // esi
  unsigned int *v511; // rcx
  int v512; // r10d
  size_t v513; // r11
  unsigned int v514; // r11d
  int v515; // r10d
  int v516; // r10d
  SIZE_T v517; // r11
  unsigned int v518; // r11d
  int v519; // r10d
  int v520; // r10d
  unsigned int v521; // r11d
  int v522; // r10d
  int v523; // r11d
  SIZE_T v524; // rsi
  HANDLE v525; // rax
  _QWORD *v526; // rcx
  HANDLE v527; // rax
  void *v528; // rcx
  HANDLE v529; // rax
  void *v530; // rcx
  size_t v531; // rax
  unsigned int v532; // esi
  HANDLE v533; // rax
  void *v534; // rcx
  _QWORD *v535; // rax
  HANDLE v536; // rax
  HANDLE v537; // rax
  HANDLE v538; // rax
  HANDLE v539; // rax
  size_t *v540; // rdx
  HANDLE v541; // rax
  HANDLE v542; // rax
  HANDLE v543; // rax
  HANDLE v544; // rax
  unsigned __int64 v545; // rsi
  unsigned __int8 v546; // al
  int v547; // edi
  int v548; // eax
  int v549; // esi
  unsigned __int8 *v550; // rbx
  int v551; // ecx
  _BYTE *v552; // r11
  unsigned int v553; // edx
  __int64 v554; // r8
  unsigned int v555; // r9d
  unsigned int v556; // ecx
  int v557; // r10d
  unsigned int v558; // edi
  char v559; // bl
  __int64 v560; // r9
  int v561; // r11d
  SIZE_T v562; // r13
  unsigned __int8 *v563; // rbx
  _BYTE *v564; // r15
  int v565; // r12d
  int v566; // r10d
  int v567; // eax
  int v568; // ecx
  int v569; // r14d
  int v570; // esi
  int v571; // r14d
  int v572; // edx
  int v573; // esi
  int v574; // r8d
  int v575; // r9d
  unsigned int v576; // edx
  int v577; // r8d
  int v578; // r9d
  unsigned int v579; // edx
  int v580; // r8d
  int v581; // r10d
  int v582; // r11d
  unsigned int v583; // r9d
  int v584; // r8d
  unsigned int v585; // r9d
  int v586; // r10d
  int v587; // r11d
  int v588; // edx
  int v589; // r8d
  unsigned int v590; // r9d
  int v591; // edx
  int v592; // r10d
  int v593; // r8d
  unsigned int v594; // edx
  int v595; // r8d
  int v596; // r8d
  unsigned __int64 i6; // rcx
  int v598; // esi
  void *v599; // r9
  void *v600; // r10
  void *v601; // r11
  void *v602; // rdx
  int v603; // eax
  void *v604; // r10
  void *v605; // r11
  void *v606; // r9
  SIZE_T v607; // r10
  size_t v608; // r9
  unsigned int *v609; // r9
  SIZE_T v610; // r10
  __int64 v611; // rdx
  __int64 v612; // r9
  int v613; // eax
  size_t v614; // r8
  void *v615; // rcx
  HANDLE v616; // rax
  HANDLE v617; // rax
  _QWORD *v618; // rax
  int v619; // eax
  __int64 v620; // rcx
  int v621; // eax
  int v622; // r10d
  unsigned int v623; // r11d
  __int64 v624; // rdx
  unsigned int v625; // r9d
  int v626; // r10d
  int v627; // r10d
  int v628; // r10d
  unsigned int v629; // r11d
  unsigned int v630; // r9d
  int v631; // r10d
  int v632; // r10d
  unsigned int v633; // r11d
  unsigned int v634; // ecx
  int v635; // edx
  unsigned int v636; // esi
  HANDLE v637; // rax
  LPVOID v638; // r9
  _DWORD *v639; // r9
  unsigned int v640; // r11d
  _DWORD *v641; // rax
  unsigned int v642; // eax
  unsigned int v643; // r10d
  HANDLE v644; // rax
  HANDLE v645; // rax
  HANDLE v646; // rax
  HANDLE v647; // rax
  void *v648; // r13
  HANDLE v649; // rax
  _OWORD *v650; // rax
  void *v651; // r14
  _DWORD *v652; // rbx
  void *v653; // rsi
  HANDLE v654; // rax
  HANDLE v655; // rax
  HANDLE v656; // rax
  HANDLE v657; // rax
  unsigned int *v658; // r9
  __int64 v659; // rdx
  __int64 v660; // r9
  unsigned int *v661; // r9
  unsigned int v662; // r11d
  unsigned int v663; // eax
  unsigned int v664; // r10d
  unsigned int *v665; // r9
  __int64 v666; // rdx
  __int64 v667; // r9
  _DWORD *v668; // r9
  __int64 v669; // r11
  unsigned int *v670; // r10
  unsigned int v671; // r9d
  __int64 v672; // rdx
  unsigned int i7; // r11d
  __int64 v674; // rdx
  __int64 v675; // r10
  int v676; // r11d
  _DWORD *v677; // r10
  _QWORD *v678; // rax
  LPVOID v679; // rcx
  unsigned int v680; // r10d
  unsigned int v681; // eax
  unsigned int *v682; // r9
  __int64 v683; // rdx
  __int64 v684; // r9
  _DWORD *v685; // r9
  __int64 v686; // r11
  const void *v687; // rdx
  void *v688; // rcx
  unsigned int *v689; // r9
  unsigned int v690; // r10d
  unsigned int i8; // r11d
  __int64 v692; // rdx
  __int64 v693; // r9
  int v694; // r11d
  _DWORD *v695; // r9
  _DWORD *v696; // rax
  unsigned int *v697; // r9
  unsigned int v698; // r10d
  unsigned int i9; // r11d
  __int64 v700; // rdx
  __int64 v701; // r9
  int v702; // r11d
  _DWORD *v703; // r9
  _DWORD *v704; // rax
  __int64 v705; // rcx
  unsigned int v706; // r10d
  unsigned int v707; // r9d
  unsigned int v708; // r11d
  int v709; // ecx
  unsigned int v710; // r9d
  unsigned int v711; // eax
  unsigned int v712; // esi
  HANDLE v713; // rax
  _DWORD *v714; // r15
  int v715; // r9d
  SIZE_T v716; // rcx
  HANDLE v717; // rax
  unsigned __int8 *v718; // r15
  SIZE_T v719; // r10
  unsigned __int8 v720; // al
  SIZE_T v721; // rcx
  unsigned __int8 *v722; // r11
  unsigned int v723; // edx
  unsigned int v724; // r9d
  int v725; // edi
  int v726; // ebx
  int v727; // r8d
  unsigned int v728; // r8d
  unsigned int v729; // r9d
  unsigned int v730; // esi
  unsigned int v731; // ecx
  int v732; // r11d
  _BYTE *v733; // rdi
  char v734; // bl
  unsigned int v735; // r9d
  _BYTE *v736; // rdi
  SIZE_T v737; // r15
  int v738; // r12d
  int v739; // r14d
  int v740; // eax
  int v741; // esi
  int v742; // r11d
  int v743; // edx
  int v744; // r9d
  int v745; // r10d
  int v746; // r8d
  int v747; // r9d
  unsigned int v748; // edx
  int v749; // r8d
  int v750; // ecx
  int v751; // edx
  int v752; // r8d
  int v753; // r9d
  int v754; // edx
  unsigned int v755; // r8d
  unsigned int v756; // r9d
  int v757; // edx
  int v758; // r8d
  int v759; // r9d
  int v760; // edx
  int v761; // r8d
  int v762; // r9d
  int v763; // edx
  int v764; // r8d
  unsigned int v765; // r9d
  int v766; // edx
  HANDLE v767; // rax
  _DWORD *v768; // rax
  void *v769; // rsi
  int v770; // r15d
  void *v771; // rax
  HANDLE v772; // rax
  _QWORD *v773; // rax
  HANDLE v774; // rax
  HANDLE v775; // rax
  HANDLE v776; // rax
  HANDLE v777; // rax
  unsigned int *v778; // r9
  unsigned int v779; // esi
  HANDLE v780; // rax
  void *v781; // rax
  _DWORD *v782; // r15
  HANDLE v783; // rax
  _OWORD *v784; // rax
  HANDLE v785; // rax
  _QWORD *v786; // rax
  _QWORD *v787; // rax
  HANDLE v788; // rax
  HANDLE v789; // rax
  HANDLE v790; // rax
  HANDLE v791; // rax
  __int64 v792; // rdx
  int v793; // r15d
  __int64 v794; // r9
  __int64 v795; // rdx
  __int64 v796; // r9
  __int64 v797; // rdx
  void *v798; // r9
  unsigned int v799; // esi
  HANDLE v800; // rax
  void *v801; // rcx
  _DWORD *v802; // rsi
  void *v803; // r10
  int v804; // r11d
  void *v805; // rcx
  const void **v806; // r9
  void *v807; // r10
  int v808; // r11d
  LPVOID v809; // rcx
  unsigned int *v810; // r10
  LPVOID v811; // rcx
  unsigned int *v812; // r9
  void *v813; // rax
  HANDLE v814; // rax
  int v815; // eax
  unsigned int v816; // r11d
  __int64 v817; // rcx
  void *v818; // r9
  void *v819; // r10
  unsigned int *v820; // rcx
  unsigned int v821; // r11d
  int i10; // eax
  unsigned int v823; // r9d
  unsigned int v824; // esi
  SIZE_T v825; // rcx
  unsigned int v826; // esi
  HANDLE v827; // rax
  unsigned int i11; // r9d
  unsigned int v829; // r10d
  int v830; // r9d
  unsigned int v831; // r9d
  signed int v832; // eax
  NTSTATUS (__stdcall *v833)(SYSTEM_INFORMATION_CLASS, PVOID, ULONG, PULONG); // rax
  int v834; // eax
  unsigned int v835; // r9d
  int v836; // r15d
  unsigned int *v837; // rcx
  int v838; // r9d
  size_t v839; // r10
  unsigned int v840; // r10d
  int v841; // r9d
  int v842; // r9d
  SIZE_T v843; // r11
  unsigned int v844; // r11d
  int v845; // r9d
  int v846; // r9d
  unsigned int v847; // r10d
  int v848; // r9d
  int v849; // r10d
  int v850; // r11d
  SIZE_T v851; // r15
  HANDLE v852; // rax
  _QWORD *v853; // rcx
  void *v854; // rsi
  HANDLE v855; // rax
  void *v856; // rcx
  HANDLE v857; // rax
  void *v858; // rcx
  void *v859; // rax
  size_t v860; // rax
  unsigned int v861; // r15d
  HANDLE v862; // rax
  void *v863; // rcx
  _QWORD *v864; // rax
  HANDLE v865; // rax
  HANDLE v866; // rax
  HANDLE v867; // rax
  HANDLE v868; // rax
  size_t *v869; // rdx
  HANDLE v870; // rax
  HANDLE v871; // rax
  HANDLE v872; // rax
  HANDLE v873; // rax
  unsigned __int64 v874; // r15
  __int64 v875; // r8
  unsigned __int8 v876; // al
  int v877; // r10d
  unsigned int v878; // ebx
  int v879; // eax
  int v880; // r15d
  unsigned __int8 *v881; // rdi
  int v882; // r11d
  int v883; // r11d
  __int64 v884; // r9
  unsigned int v885; // r11d
  int v886; // ecx
  unsigned int v887; // edx
  _BYTE *v888; // rsi
  char v889; // di
  int v890; // r11d
  int v891; // r10d
  unsigned __int8 *v892; // rbx
  _BYTE *v893; // r15
  int v894; // r12d
  int v895; // r13d
  size_t v896; // rax
  int v897; // ecx
  int v898; // r14d
  int v899; // esi
  int v900; // r14d
  int v901; // esi
  int v902; // r8d
  int v903; // r9d
  unsigned int v904; // edx
  int v905; // r8d
  int v906; // r9d
  unsigned int v907; // edx
  unsigned int v908; // r8d
  int v909; // r10d
  int v910; // r11d
  unsigned int v911; // r9d
  int v912; // r8d
  unsigned int v913; // r9d
  int v914; // edx
  int v915; // r8d
  int v916; // r9d
  int v917; // edx
  int v918; // r8d
  int v919; // r9d
  int v920; // r10d
  int v921; // edx
  int v922; // r11d
  int v923; // ecx
  unsigned __int64 i12; // rcx
  void *v925; // rsi
  int v926; // r15d
  void *v927; // rcx
  void *v928; // r9
  void *v929; // r10
  void *v930; // r11
  void *v931; // rdx
  int v932; // eax
  void *v933; // r10
  void *v934; // r11
  void *v935; // r9
  SIZE_T v936; // r10
  size_t v937; // r9
  unsigned int *v938; // r9
  SIZE_T v939; // r10
  __int64 v940; // rdx
  __int64 v941; // r9
  int v942; // eax
  void *v943; // rax
  HANDLE v944; // rax
  size_t v945; // rsi
  LPVOID v946; // rax
  HANDLE v947; // rax
  _QWORD *v948; // rax
  HANDLE v949; // rax
  HANDLE v950; // rax
  HANDLE v951; // rax
  HANDLE v952; // rax
  HANDLE v953; // rax
  HANDLE v954; // rax
  _QWORD *v955; // rsi
  HANDLE v956; // rax
  HANDLE v957; // rax
  HANDLE v958; // rax
  HANDLE v959; // rax
  void *v960; // rsi
  HANDLE v961; // rax
  int v962; // eax
  void *v963; // rcx
  _DWORD *v964; // r9
  int v965; // r10d
  int *v966; // r15
  int i13; // r10d
  unsigned int v968; // r11d
  int v969; // r10d
  void *v970; // r9
  int v971; // r10d
  size_t *v972; // rdx
  size_t v973; // rax
  LPVOID v974; // rcx
  unsigned int v975; // r10d
  unsigned int v976; // r11d
  int v977; // r10d
  unsigned int *v978; // r9
  int v979; // r10d
  int *v980; // rdx
  int v981; // eax
  unsigned int *v982; // rcx
  int v983; // r11d
  unsigned int v984; // r10d
  __int64 v985; // rdx
  int v986; // r10d
  _DWORD *v987; // r9
  int v988; // r11d
  _DWORD *v989; // rcx
  unsigned int v990; // r10d
  int v991; // r10d
  void *v992; // r9
  int v993; // r10d
  _DWORD *v994; // rdx
  LPVOID v995; // rcx
  unsigned int v996; // r10d
  unsigned int v997; // r9d
  int v998; // r10d
  int v999; // r9d
  size_t v1000; // r11
  int *v1001; // rcx
  HANDLE v1002; // rax
  int v1003; // ecx
  int v1004; // eax
  int v1005; // r9d
  int v1006; // eax
  int v1007; // r9d
  int v1008; // eax
  int v1009; // r9d
  unsigned int v1010; // esi
  HANDLE v1011; // rax
  _DWORD *v1012; // rax
  _DWORD *v1013; // rsi
  unsigned int v1014; // r11d
  _DWORD *v1015; // rax
  unsigned int v1016; // esi
  unsigned int v1017; // eax
  unsigned int v1018; // r10d
  unsigned int *v1019; // r9
  __int64 v1020; // rdx
  __int64 v1021; // r9
  unsigned int *v1022; // r9
  unsigned int v1023; // r11d
  unsigned int v1024; // r10d
  unsigned int *v1025; // r9
  unsigned int i14; // r11d
  __int64 v1027; // rdx
  __int64 v1028; // r9
  int v1029; // r11d
  unsigned int *v1030; // r9
  unsigned int *v1031; // r10
  unsigned int v1032; // r9d
  unsigned int i15; // r11d
  __int64 v1034; // rdx
  __int64 v1035; // r10
  int v1036; // r11d
  _DWORD *v1037; // r10
  _QWORD *v1038; // rax
  size_t v1039; // rcx
  __int64 v1040; // rcx
  unsigned int v1041; // r11d
  unsigned int v1042; // r9d
  unsigned int v1043; // r11d
  int v1044; // ecx
  LPVOID v1045; // r9
  unsigned int v1046; // r10d
  unsigned int v1047; // eax
  unsigned int v1048; // esi
  HANDLE v1049; // rax
  char *v1050; // rax
  char *v1051; // rsi
  int v1052; // r9d
  int v1053; // r9d
  SIZE_T v1054; // rcx
  HANDLE v1055; // rax
  _DWORD *v1056; // rsi
  int v1057; // ecx
  SIZE_T v1058; // r11
  unsigned __int8 v1059; // al
  SIZE_T v1060; // r8
  unsigned __int8 *v1061; // r9
  unsigned int v1062; // r10d
  unsigned int v1063; // edi
  int v1064; // ebx
  int v1065; // esi
  int v1066; // r8d
  int v1067; // r8d
  unsigned int v1068; // r9d
  unsigned int v1069; // r8d
  unsigned int v1070; // ecx
  int v1071; // edx
  _BYTE *v1072; // rbx
  unsigned int v1073; // edi
  char v1074; // al
  unsigned int v1075; // r9d
  unsigned __int8 *v1076; // rdi
  SIZE_T v1077; // r14
  _BYTE *v1078; // r12
  int v1079; // r13d
  int v1080; // r15d
  int v1081; // eax
  int v1082; // ecx
  int v1083; // esi
  int v1084; // r11d
  int v1085; // esi
  int v1086; // r11d
  int v1087; // r8d
  int v1088; // r10d
  int v1089; // r8d
  int v1090; // r10d
  int v1091; // r9d
  int v1092; // r8d
  unsigned int v1093; // edx
  int v1094; // r9d
  int v1095; // ecx
  int v1096; // edx
  int v1097; // r8d
  int v1098; // r9d
  int v1099; // edx
  unsigned int v1100; // r8d
  unsigned int v1101; // r9d
  int v1102; // edx
  int v1103; // r8d
  int v1104; // r9d
  int v1105; // edx
  int v1106; // r8d
  int v1107; // r9d
  int v1108; // edx
  int v1109; // r8d
  unsigned int v1110; // r9d
  int v1111; // edx
  unsigned int v1112; // ecx
  int v1113; // r9d
  int v1114; // edx
  HANDLE v1115; // rax
  _DWORD *v1116; // rax
  const void **v1117; // rbx
  HANDLE v1118; // rax
  _QWORD *v1119; // rax
  HANDLE v1120; // rax
  HANDLE v1121; // rax
  HANDLE v1122; // rax
  HANDLE v1123; // rax
  unsigned int v1124; // ebx
  HANDLE v1125; // rax
  LPVOID v1126; // rax
  void *v1127; // rbx
  void *v1128; // rcx
  bool v1129; // zf
  int v1130; // eax
  HANDLE v1131; // rax
  _OWORD *v1132; // rcx
  _DWORD *v1133; // rax
  HANDLE v1134; // rax
  _QWORD *v1135; // rax
  _QWORD *v1136; // rbx
  HANDLE v1137; // rax
  HANDLE v1138; // rax
  HANDLE v1139; // rax
  HANDLE v1140; // rax
  void *v1141; // rcx
  int v1142; // eax
  __int64 v1143; // rdx
  __int64 v1144; // rdx
  __int64 v1145; // rdx
  unsigned int v1146; // ebx
  HANDLE v1147; // rax
  void *v1148; // rcx
  void *v1149; // rdi
  void *v1150; // r9
  void *v1151; // rcx
  void *v1152; // r9
  int v1153; // r10d
  LPVOID v1154; // rcx
  unsigned int *v1155; // r9
  LPVOID v1156; // rcx
  unsigned int *v1157; // r9
  int v1158; // eax
  HANDLE v1159; // rax
  unsigned int v1160; // r10d
  __int64 v1161; // rcx
  void *v1162; // r9
  unsigned int *v1163; // rcx
  int i16; // r11d
  unsigned int v1165; // r9d
  int v1166; // r11d
  unsigned int v1167; // ebx
  SIZE_T v1168; // rcx
  unsigned int v1169; // ebx
  HANDLE v1170; // rax
  unsigned int i17; // r9d
  unsigned int v1172; // r11d
  int v1173; // r9d
  int v1174; // r10d
  unsigned int v1175; // r9d
  bool v1176; // sf
  NTSTATUS (__stdcall *v1177)(SYSTEM_INFORMATION_CLASS, PVOID, ULONG, PULONG); // rax
  unsigned int v1178; // r9d
  SIZE_T v1179; // rbx
  int v1180; // ecx
  int v1181; // r9d
  int v1182; // r9d
  int v1183; // r9d
  SIZE_T v1184; // r11
  unsigned int v1185; // r11d
  int v1186; // r9d
  int v1187; // r9d
  unsigned int v1188; // r10d
  int v1189; // r9d
  int v1190; // r10d
  int v1191; // r11d
  HANDLE v1192; // rax
  _QWORD *v1193; // rcx
  void *v1194; // rbx
  HANDLE v1195; // rax
  void *v1196; // rax
  HANDLE v1197; // rax
  void *v1198; // rcx
  void *v1199; // rax
  SIZE_T v1200; // rax
  HANDLE v1201; // rax
  void *v1202; // rcx
  _QWORD *v1203; // rax
  HANDLE v1204; // rax
  HANDLE v1205; // rax
  HANDLE v1206; // rax
  HANDLE v1207; // rax
  size_t *v1208; // rdx
  unsigned int *v1209; // rax
  HANDLE v1210; // rax
  HANDLE v1211; // rax
  HANDLE v1212; // rax
  HANDLE v1213; // rax
  __int64 v1214; // rdx
  _BYTE *v1215; // r11
  unsigned __int8 v1216; // al
  unsigned __int8 *v1217; // r8
  unsigned int v1218; // r10d
  unsigned int v1219; // edi
  int v1220; // eax
  int v1221; // r11d
  int v1222; // r9d
  _BYTE *v1223; // rcx
  __int64 v1224; // r8
  unsigned int v1225; // r9d
  int v1226; // ebx
  unsigned int v1227; // edi
  char v1228; // r11
  __int64 v1229; // r9
  SIZE_T v1230; // rbx
  int v1231; // r15d
  SIZE_T v1232; // r14
  int v1233; // r11d
  _BYTE *v1234; // r12
  int v1235; // r13d
  int v1236; // r10d
  unsigned __int8 *v1237; // rax
  int v1238; // ecx
  int v1239; // esi
  int v1240; // ebx
  int v1241; // esi
  int v1242; // edx
  int v1243; // ebx
  int v1244; // r8d
  int v1245; // r9d
  unsigned int v1246; // edx
  int v1247; // r8d
  int v1248; // r9d
  unsigned int v1249; // edx
  int v1250; // r8d
  int v1251; // r10d
  int v1252; // r11d
  unsigned int v1253; // r9d
  int v1254; // edx
  int v1255; // r8d
  unsigned int v1256; // r9d
  int v1257; // edx
  int v1258; // r8d
  int v1259; // r9d
  int v1260; // edx
  unsigned int v1261; // r8d
  int v1262; // r9d
  int v1263; // edx
  int v1264; // r8d
  unsigned int v1265; // r9d
  int v1266; // r8d
  int v1267; // r9d
  SIZE_T i18; // rcx
  void *v1269; // rdi
  int v1270; // ecx
  void *v1271; // r9
  void *v1272; // r10
  int *v1273; // r11
  __int64 v1274; // rdx
  unsigned int *v1275; // rbx
  void *v1276; // r11
  void *v1277; // r9
  void *v1278; // r10
  SIZE_T v1279; // r9
  SIZE_T v1280; // r9
  __int64 v1281; // rdx
  void *v1282; // rax
  HANDLE v1283; // rax
  size_t v1284; // rdi
  int v1285; // eax
  void *v1286; // rbx
  HANDLE v1287; // rax
  _QWORD *v1288; // rbx
  HANDLE v1289; // rax
  HANDLE v1290; // rax
  HANDLE v1291; // rax
  HANDLE v1292; // rax
  void *v1293; // rbx
  HANDLE v1294; // rax
  HANDLE v1295; // rax
  _QWORD *v1296; // rbx
  void *v1297; // rsi
  HANDLE v1298; // rax
  void *v1299; // rsi
  HANDLE v1300; // rax
  void *v1301; // rsi
  HANDLE v1302; // rax
  HANDLE v1303; // rax
  HANDLE v1304; // rax
  unsigned int v1305; // r9d
  int *v1306; // rcx
  SIZE_T v1307; // rcx
  int i19; // r9d
  unsigned int v1309; // r10d
  int v1310; // r9d
  int v1311; // edi
  int v1312; // edi
  BYTE *v1313; // rcx
  SIZE_T v1315; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v1316; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID v1317; // [rsp+40h] [rbp-C0h]
  LPVOID v1318; // [rsp+48h] [rbp-B8h]
  void *v1319; // [rsp+50h] [rbp-B0h]
  int v1320; // [rsp+58h] [rbp-A8h]
  _BYTE Size[12]; // [rsp+5Ch] [rbp-A4h] BYREF
  LPVOID v1322; // [rsp+68h] [rbp-98h]
  unsigned int uBytes; // [rsp+70h] [rbp-90h]
  unsigned __int8 uBytes_4; // [rsp+74h] [rbp-8Ch]
  LPVOID v1325; // [rsp+78h] [rbp-88h]
  void *Src; // [rsp+80h] [rbp-80h]
  SIZE_T v1327; // [rsp+88h] [rbp-78h] BYREF
  LPVOID v1328; // [rsp+90h] [rbp-70h]
  LPVOID jj; // [rsp+98h] [rbp-68h]
  SIZE_T v1330; // [rsp+A0h] [rbp-60h] BYREF
  size_t v1331; // [rsp+A8h] [rbp-58h]
  void *v1332; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID v1333; // [rsp+B8h] [rbp-48h]
  SIZE_T v1334; // [rsp+C0h] [rbp-40h]
  LPVOID v1335; // [rsp+C8h] [rbp-38h] BYREF
  LPVOID v1336; // [rsp+D0h] [rbp-30h] BYREF
  SIZE_T dwBytes; // [rsp+D8h] [rbp-28h] BYREF
  SIZE_T v1338; // [rsp+E0h] [rbp-20h]
  int v1339; // [rsp+E8h] [rbp-18h]
  int v1340; // [rsp+ECh] [rbp-14h]
  SIZE_T v1341; // [rsp+F0h] [rbp-10h] BYREF
  LPVOID v1342; // [rsp+F8h] [rbp-8h]
  SIZE_T v1343; // [rsp+100h] [rbp+0h] BYREF
  size_t v1344[2]; // [rsp+108h] [rbp+8h] BYREF
  int v1345; // [rsp+118h] [rbp+18h] BYREF
  SIZE_T v1346; // [rsp+120h] [rbp+20h] BYREF
  void *v1347; // [rsp+128h] [rbp+28h] BYREF
  SIZE_T v1348; // [rsp+130h] [rbp+30h] BYREF
  LPVOID lpMem; // [rsp+138h] [rbp+38h]
  size_t v1350[2]; // [rsp+140h] [rbp+40h] BYREF
  size_t v1351[2]; // [rsp+150h] [rbp+50h] BYREF
  void *v1352; // [rsp+160h] [rbp+60h]
  void *v1353; // [rsp+168h] [rbp+68h] BYREF
  unsigned int v1354; // [rsp+170h] [rbp+70h] BYREF
  unsigned int v1355; // [rsp+174h] [rbp+74h] BYREF
  int v1356; // [rsp+178h] [rbp+78h]
  unsigned int v1357; // [rsp+17Ch] [rbp+7Ch] BYREF
  UINT v1358; // [rsp+180h] [rbp+80h]
  LPVOID v1359; // [rsp+188h] [rbp+88h] BYREF
  unsigned int v1360; // [rsp+190h] [rbp+90h] BYREF
  unsigned int v1361; // [rsp+194h] [rbp+94h] BYREF
  unsigned int v1362; // [rsp+198h] [rbp+98h] BYREF
  unsigned int v1363; // [rsp+1A0h] [rbp+A0h] BYREF
  int v1364; // [rsp+1A4h] [rbp+A4h]
  unsigned int v1365; // [rsp+1A8h] [rbp+A8h] BYREF
  unsigned int v1366; // [rsp+1ACh] [rbp+ACh] BYREF
  BYTE *v1367; // [rsp+1B0h] [rbp+B0h] BYREF
  HMODULE phModule; // [rsp+1C0h] [rbp+C0h] BYREF
  HMODULE hModule; // [rsp+1C8h] [rbp+C8h] BYREF
  HMODULE v1370; // [rsp+1D0h] [rbp+D0h] BYREF
  HMODULE v1371; // [rsp+1E0h] [rbp+E0h] BYREF
  PBYTE *v1372; // [rsp+1E8h] [rbp+E8h]
  __int128 v1373; // [rsp+1F0h] [rbp+F0h] BYREF
  __int128 v1374; // [rsp+200h] [rbp+100h]
  __int128 v1375; // [rsp+210h] [rbp+110h] BYREF
  __int128 v1376; // [rsp+220h] [rbp+120h]
  __int128 v1377; // [rsp+230h] [rbp+130h] BYREF
  __int128 v1378; // [rsp+240h] [rbp+140h]
  __int128 v1379; // [rsp+250h] [rbp+150h] BYREF
  __int128 v1380; // [rsp+260h] [rbp+160h]
  UINT *v1381; // [rsp+280h] [rbp+180h]
  SLDATATYPE *v1382; // [rsp+288h] [rbp+188h]

  v1381 = pcbValue;
  v1372 = ppbValue;
  v1382 = peDataType;
  v1343 = (SIZE_T)pwszValueName;
  v1367 = 0;
  if ( !pwszValueName || !pcbValue || !ppbValue )
  {
    v5 = -2147024809;
    goto LABEL_1716;
  }
  v1345 = 0;
  v1359 = 0;
  ProcessHeap = GetProcessHeap();
  Src = HeapAlloc(ProcessHeap, 8u, 0xA0u);
  v7 = Src;
  v8 = 4;
  if ( !Src )
  {
    v9 = -1073741801;
LABEL_7:
    v10 = v9;
LABEL_8:
    v11 = v1345;
    v12 = v1345;
    goto LABEL_9;
  }
  v13 = 0;
  v1340 = 0;
  *(_OWORD *)Src = xmmword_180024150;
  uBytes = 0;
  v7[1] = xmmword_180024160;
  v7[2] = xmmword_180024170;
  v7[3] = xmmword_180024180;
  v7[4] = xmmword_180024190;
  v7[5] = xmmword_1800241A0;
  v7[6] = xmmword_1800241B0;
  v7[7] = xmmword_1800241C0;
  v7[8] = xmmword_1800241D0;
  v7[9] = xmmword_1800241E0;
  v14 = GetProcessHeap();
  v15 = HeapAlloc(v14, 8u, 8u);
  v1339 = -805306345;
  v1319 = v15;
  v1356 = -1;
  v10 = -805306219;
  v1320 = -805306219;
  if ( !v15 )
  {
    v9 = -1073741801;
    v1319 = 0;
    LODWORD(v1327) = 0;
    LODWORD(v1328) = 0;
LABEL_439:
    v294 = GetProcessHeap();
    HeapFree(v294, 0, v7);
    goto LABEL_440;
  }
  *v15 = qword_180024090;
  v1330 = __rdtsc();
  dwBytes = 0;
  if ( (int)sub_180001090(pwszValueName, (unsigned __int64)HIDWORD(v1330) << 32, &dwBytes) < 0 )
  {
    v9 = -1073741762;
LABEL_438:
    LODWORD(v1328) = 0;
    LODWORD(v1327) = 0;
    goto LABEL_439;
  }
  if ( (unsigned int)(2 * dwBytes + 6) < 4 )
  {
    v9 = -1073741675;
    v1319 = v17;
    goto LABEL_438;
  }
  v18 = 2 * dwBytes + 202;
  v1336 = 0;
  v19 = 0;
  v20 = 0;
  v21 = v16;
  if ( v18 >= 0xC4 )
    v21 = 2 * dwBytes + 202;
  v9 = v18 < 0xC4 ? -805306219 : 0x10000000;
  if ( v18 < 0xC4 )
    goto LABEL_427;
  v22 = v21 + 8;
  v23 = v16;
  if ( v21 + 8 >= v21 )
    v23 = v21 + 8;
  v9 = v22 < v21 ? -805306219 : 0x10000000;
  if ( v22 < v21 )
    goto LABEL_427;
  v24 = v23 + 8;
  v25 = v16;
  if ( v23 + 8 >= v23 )
    v25 = v23 + 8;
  LODWORD(v1315) = v25;
  v9 = v24 < v23 ? -805306219 : 0x10000000;
  if ( v24 < v23 )
  {
LABEL_427:
    v1319 = v17;
LABEL_428:
    if ( v9 < 0 )
      goto LABEL_431;
    goto LABEL_429;
  }
  v26 = v25;
  v27 = GetProcessHeap();
  v28 = HeapAlloc(v27, 8u, (unsigned int)v26);
  v19 = v28;
  if ( !v28 )
  {
    v9 = -1073741801;
    v7 = Src;
    goto LABEL_438;
  }
  v29 = v1319;
  v30 = Src;
  if ( v28 + 1 < v28 )
    goto LABEL_53;
  if ( v28 + 2 > (_DWORD *)((char *)v28 + v26) )
  {
LABEL_37:
    v9 = -1073741789;
LABEL_54:
    v20 = 0;
    goto LABEL_428;
  }
  *v28 = 4;
  v31 = 0;
  v28[1] = 0;
  v32 = v28;
  v1319 = v29;
  Src = v30;
  while ( !v31 )
  {
    v33 = *v32 + 4;
    if ( v33 < 4 || (_DWORD *)((char *)v32 + v33) < v32 )
      goto LABEL_53;
    v32 = (_DWORD *)((char *)v32 + v33);
    v31 = 1;
  }
  if ( v32 + 1 < v32 )
    goto LABEL_53;
  v34 = (unsigned int)v1315;
  v1316 = (LPVOID)(unsigned int)v1315;
  if ( v32 + 41 > (_DWORD *)((char *)v19 + (unsigned int)v1315) )
    goto LABEL_37;
  *v32 = 160;
  if ( v30 )
  {
    memcpy(v32 + 1, v30, 0xA0u);
    v29 = v1319;
  }
  *(_DWORD *)&Size[4] = 2;
  if ( !v29 )
  {
    v9 = -1073741811;
    goto LABEL_54;
  }
  if ( v19 )
  {
    v37 = v19;
    for ( i = 0; i < 2; ++i )
    {
      v39 = *v37 + 4;
      if ( v39 < 4 || (_DWORD *)((char *)v37 + v39) < v37 )
        goto LABEL_53;
      v37 = (_DWORD *)((char *)v37 + v39);
    }
    if ( v37 + 1 >= v37 )
    {
      if ( v37 + 3 > (_DWORD *)((char *)v19 + v34) )
        goto LABEL_37;
      *v37 = 8;
      memcpy(v37 + 1, v29, 8u);
      v36 = *(_DWORD *)&Size[4] + 1;
      v32 = v19;
      for ( j = 0; j < v36; ++j )
      {
        v41 = *v32 + 4;
        if ( v41 < 4 || (_DWORD *)((char *)v32 + v41) < v32 )
          goto LABEL_53;
        v32 = (_DWORD *)((char *)v32 + v41);
      }
      if ( v32 + 1 >= v32 )
      {
        if ( v32 + 3 > (_DWORD *)((char *)v19 + v34) )
          goto LABEL_37;
        v42 = v1330;
        *v32 = 8;
        *(_QWORD *)(v32 + 1) = v42;
        goto LABEL_62;
      }
    }
LABEL_53:
    v9 = -1073741675;
    goto LABEL_54;
  }
  v35 = v34 + 12;
  if ( (int)v34 + 12 < (unsigned int)v34 )
    goto LABEL_53;
  v36 = 3;
  v34 = (unsigned int)(v34 + 24);
  v1316 = (LPVOID)v34;
  if ( (unsigned int)v34 < v35 )
    goto LABEL_53;
LABEL_62:
  dwBytes = 0;
  *(_DWORD *)&Size[4] = v36 + 1;
  if ( (int)sub_180001090(v1343, v32, &dwBytes) < 0 )
  {
    v9 = -1073741762;
    goto LABEL_431;
  }
  if ( dwBytes + 1 < dwBytes )
    goto LABEL_424;
  v45 = (unsigned int)(2 * (dwBytes + 1));
  if ( !(_DWORD)v45 )
  {
    v9 = -1073741811;
    goto LABEL_82;
  }
  if ( v19 )
  {
    v48 = v19;
    for ( k = 0; k < v43; ++k )
    {
      v50 = *v48 + 4;
      if ( v50 < 4 || (_DWORD *)((char *)v48 + v50) < v48 )
        goto LABEL_71;
      v48 = (_DWORD *)((char *)v48 + v50);
    }
    v1352 = v48 + 1;
    if ( v48 + 1 >= v48 )
    {
      if ( (char *)v48 + v45 + 4 <= (char *)v19 + (unsigned int)v34 )
      {
        v51 = v1352;
        v9 = 0;
        *v48 = v45;
        memcpy(v51, (const void *)v1343, (unsigned int)v45);
        v44 = v1319;
        v43 = *(_DWORD *)&Size[4] + 1;
      }
      else
      {
        v9 = -1073741789;
      }
      goto LABEL_82;
    }
    goto LABEL_71;
  }
  v46 = v45 + 4;
  if ( v46 < 4 )
  {
LABEL_71:
    v9 = -1073741675;
LABEL_82:
    v47 = (unsigned int)v1316;
    goto LABEL_83;
  }
  v47 = v34 + v46;
  if ( (unsigned int)v34 + v46 < (unsigned int)v34 )
  {
    v47 = -1;
    v9 = -1073741675;
  }
  else
  {
    ++v43;
    v9 = 0;
  }
LABEL_83:
  if ( v9 < 0 )
    goto LABEL_431;
  if ( !v19 )
  {
    if ( v47 + 8 >= v47 )
    {
      v52 = v43 + 1;
      LODWORD(v57) = v47 + 16;
      *(_DWORD *)Size = v47 + 16;
      if ( v47 + 16 >= v47 + 8 )
      {
        v59 = Src;
        goto LABEL_104;
      }
    }
LABEL_423:
    v9 = -1073741675;
    goto LABEL_54;
  }
  v53 = v19;
  for ( m = 0; m < v43; ++m )
  {
    v55 = (unsigned int)(*v53 + 4);
    if ( (unsigned int)v55 < 4 )
      goto LABEL_423;
    v56 = (_DWORD *)((char *)v53 + v55);
    if ( v56 < v53 )
      goto LABEL_423;
    v53 = v56;
  }
  if ( v53 + 1 < v53 )
    goto LABEL_423;
  if ( v53 + 2 > (_DWORD *)((char *)v19 + v47) )
    goto LABEL_37;
  v52 = v43 + 1;
  *(_QWORD *)v53 = 4;
  v1319 = v44;
  v57 = v47;
  v58 = v19;
  v59 = Src;
  v60 = 0;
  *(_DWORD *)Size = v57;
  while ( v60 < v52 )
  {
    v61 = *v58 + 4;
    if ( v61 < 4 || (_DWORD *)((char *)v58 + v61) < v58 )
      goto LABEL_423;
    v58 = (_DWORD *)((char *)v58 + v61);
    ++v60;
  }
  if ( v58 + 1 < v58 )
    goto LABEL_423;
  if ( v58 + 2 > (_DWORD *)((char *)v19 + v57) )
    goto LABEL_37;
  *v58 = 4;
  v58[1] = 0;
LABEL_104:
  *(_DWORD *)&Size[4] = v52 + 1;
  v1352 = (void *)__rdtsc();
  v62 = v57 + 8;
  if ( v62 < 8 || (v1342 = (LPVOID)((v62 + 7) & 0xFFFFFFF8), (unsigned int)v1342 < v62) )
  {
    v9 = -805306219;
    goto LABEL_431;
  }
  LODWORD(v1315) = 0;
  dwBytes = (v62 + 7) & 0xFFFFFFF8;
  v63 = GetProcessHeap();
  v1318 = HeapAlloc(v63, 8u, dwBytes);
  v64 = (char *)v1318;
  if ( v1318 )
  {
    v65 = v1319;
    Src = v59;
    *(_DWORD *)v1318 = *(_DWORD *)&Size[4];
    if ( v64 + 4 < v64 || (v66 = *(_DWORD *)Size, *((_DWORD *)v64 + 1) = *(_DWORD *)Size, v64 + 8 < v64 + 4) )
    {
      v1319 = v65;
      dwBytes = (SIZE_T)v64;
      v1318 = 0;
      LODWORD(v1342) = 0;
      v109 = GetProcessHeap();
      HeapFree(v109, 0, (LPVOID)dwBytes);
      v9 = -805306219;
      goto LABEL_362;
    }
    *(_QWORD *)&v64[dwBytes - 8] = v1352;
    memcpy(v64 + 8, v19, v66);
    dwBytes = (SIZE_T)v1318;
    jj = 0;
    v1317 = 0;
    v1325 = 0;
    v1322 = 0;
    v1333 = 0;
    v1328 = 0;
    if ( !(_DWORD)v1342
      || (v1341 = (unsigned int)v1342 + 8LL, lpMem = (LPVOID)sub_1800010C0(v1341), (v67 = (char *)lpMem) == 0) )
    {
      v9 = -805306367;
LABEL_339:
      v259 = GetProcessHeap();
      HeapFree(v259, 0, v1318);
LABEL_340:
      v260 = v1317;
      if ( v1317 )
      {
        v1331 = *((_QWORD *)v1317 + 1);
        if ( v1331 )
        {
          v261 = GetProcessHeap();
          HeapFree(v261, 0, (LPVOID)v1331);
          v260 = v1317;
          *((_QWORD *)v1317 + 1) = 0;
        }
        v1331 = v260[3];
        if ( v1331 )
        {
          v262 = GetProcessHeap();
          HeapFree(v262, 0, (LPVOID)v1331);
          v260 = v1317;
          *((_QWORD *)v1317 + 3) = 0;
        }
        v1331 = v260[5];
        if ( v1331 )
        {
          v263 = GetProcessHeap();
          HeapFree(v263, 0, (LPVOID)v1331);
          *((_QWORD *)v1317 + 5) = 0;
        }
        v264 = GetProcessHeap();
        HeapFree(v264, 0, v1317);
      }
      if ( v1325 )
      {
        v265 = GetProcessHeap();
        HeapFree(v265, 0, v1325);
      }
      if ( v1322 )
      {
        v266 = GetProcessHeap();
        HeapFree(v266, 0, v1322);
      }
      v267 = v1333;
      if ( v1333 )
      {
        v1331 = *((_QWORD *)v1333 + 1);
        if ( v1331 )
        {
          v268 = GetProcessHeap();
          HeapFree(v268, 0, (LPVOID)v1331);
          v267 = v1333;
          *((_QWORD *)v1333 + 1) = 0;
        }
        v1331 = v267[3];
        if ( v1331 )
        {
          v269 = GetProcessHeap();
          HeapFree(v269, 0, (LPVOID)v1331);
          v267 = v1333;
          *((_QWORD *)v1333 + 3) = 0;
        }
        v1331 = v267[5];
        if ( v1331 )
        {
          v270 = GetProcessHeap();
          HeapFree(v270, 0, (LPVOID)v1331);
          *((_QWORD *)v1333 + 5) = 0;
        }
        v271 = GetProcessHeap();
        HeapFree(v271, 0, v1333);
      }
      if ( v1328 )
      {
        v272 = GetProcessHeap();
        HeapFree(v272, 0, v1328);
      }
      goto LABEL_362;
    }
    v68 = (unsigned int)v1342;
    v69 = 0;
    v70 = 0;
    uBytes_4 = 0;
    if ( (_DWORD)v1342 )
    {
      do
      {
        v69 ^= *(_BYTE *)(v70 + dwBytes);
        ++v70;
      }
      while ( v70 < (unsigned int)v1342 );
      uBytes_4 = v69;
    }
    Src = v59;
    v1335 = v19;
    v1316 = (LPVOID)0xC81ECB17B1B54A58LL;
    v1352 = (void *)((unsigned __int64)(unsigned int)v1342 >> 3);
    if ( v1352 )
    {
      v71 = 0;
      v72 = HIWORD(v1316);
      v73 = lpMem;
      v74 = v1352;
      v75 = (unsigned __int8 *)v1318;
      dwBytes = 0;
      v76 = -1;
      v77 = WORD2(v1316);
      *(_DWORD *)Size = 0;
      LODWORD(v1334) = 0;
      do
      {
        v78 = *v75;
        v79 = v75[1];
        v80 = v75[4];
        v75 += 8;
        v81 = *(v75 - 5) | ((*(v75 - 6) | (((v78 << 8) | v79) << 8)) << 8);
        v82 = *(v75 - 1) | ((*(v75 - 2) | ((*(v75 - 3) | (v80 << 8)) << 8)) << 8);
        v83 = v71 ^ v81 ^ ((v76 ^ v82) - 19032);
        v84 = v83 ^ HIDWORD(v1316);
        v85 = v76 ^ v82 ^ (__ROR4__(v83 ^ HIDWORD(v1316), 7) + WORD1(v1316) * __ROR4__(v83, 15));
        v86 = v84 ^ (v77 * __ROR4__(v85 - 1313519016, 9) - __ROR4__(v85, 10));
        v87 = v85 ^ (__ROR4__(v86, 27) + v72 * __ROR4__(v86 ^ v77, 28));
        v88 = v86 ^ (HIDWORD(v1316) - (v87 ^ 0xB1B54A58));
        v89 = v88 ^ (19032 * (v77 ^ __ROR4__(v87 ^ (WORD1(v1316) * (v88 - 19032) - (v88 >> 6)), 15)));
        v90 = v87 ^ (WORD1(v1316) * (v88 - 19032) - (v88 >> 6)) ^ (v77 * (v72 + __ROR4__(~v89, 3)));
        v91 = v89 ^ (v90 - 19032 - HIDWORD(v1316));
        v92 = v90 ^ (WORD1(v1316) * (v91 ^ v72)) ^ __ROR4__(v91, 10);
        v93 = v91 ^ __ROR4__(v92, 3) ^ (v77 * __ROR4__(v92 ^ 0x4A58, 26));
        v94 = v92 ^ (19032 * (__ROR4__(v93, 15) - v72));
        v95 = v93
            ^ ((v94 ^ (v94 >> 14)) >> 1)
            ^ (19032 * (v94 ^ v72))
            ^ (19032 * (((unsigned __int64)(v94 - v77) >> 29) | (8 * (v94 - v77))));
        v96 = v94 ^ (WORD1(v1316) * (v95 - v77) - (v95 >> 13));
        v97 = v95 ^ __ROR4__(v96, 11) ^ (v77 * __ROR4__(-1313519016 - v96, 9));
        v98 = v96 ^ (v97 - v72 + 1313519016);
        v99 = v97 ^ (19032 * (WORD1(v1316) ^ v98) - __ROR4__(v98, 7));
        v100 = v98 ^ (WORD1(v1316) * __ROR4__(v99 ^ v72, 28) - __ROR4__(v99, 16));
        v101 = v99 ^ (__ROR4__(v100, 4) + v77 * __ROR4__(-1313519016 - v100, 10));
        v102 = v100 ^ __ROR4__(v101, 9) ^ (v72 * __ROR4__(v101 + 1313519016, 4));
        v103 = v101 ^ (19032 * __ROR4__(HIDWORD(v1316) ^ v102, 24) - __ROR4__(v102, 30));
        v104 = v102 ^ (WORD1(v1316) * __ROR4__(HIDWORD(v1316) - v103, 11) - __ROR4__(v103, 12));
        v105 = *(_DWORD *)Size;
        *(_DWORD *)Size = v81;
        v106 = v103 ^ (v104 >> 8) ^ (v77 * (WORD1(v1316) ^ v104));
        v107 = v1334 ^ HIDWORD(v1316);
        v108 = v106 ^ v105;
        v73[3] = v108;
        LODWORD(v1338) = v108;
        v76 = v106 ^ v104 ^ v107 ^ 0xB1B54A58;
        LODWORD(v1334) = v82;
        v73[7] = v76;
        v71 = v108;
        v73[2] = __ROR4__(v108, 8);
        v73[6] = __ROR4__(v76, 8);
        v73[1] = __ROR4__(v108, 16);
        v73[5] = __ROR4__(v76, 16);
        *v73 = __ROR4__(v108, 24);
        v73[4] = __ROR4__(v76, 24);
        v73 += 8;
        ++dwBytes;
      }
      while ( dwBytes < (unsigned __int64)v74 );
      v69 = uBytes_4;
      v13 = v1340;
      v10 = -805306219;
      v19 = v1335;
      v8 = 4;
      v59 = Src;
      v68 = (unsigned int)v1342;
      v67 = (char *)lpMem;
    }
    else
    {
      Src = v59;
    }
    *(_QWORD *)&v67[v68] = v69;
    v110 = GetProcessHeap();
    v1316 = HeapAlloc(v110, 8u, 0x30u);
    if ( v1316 )
    {
      Src = v59;
      v120 = v1316;
      *(_DWORD *)v1316 = v1341;
      v121 = GetProcessHeap();
      v122 = HeapAlloc(v121, 8u, (unsigned int)v1341);
      if ( v122 )
      {
        v120[1] = v122;
        memcpy(v122, lpMem, (unsigned int)v1341);
        *((_DWORD *)v120 + 4) = 160;
        v123 = GetProcessHeap();
        v124 = HeapAlloc(v123, 8u, 0xA0u);
        if ( v124 )
        {
          v120[3] = v124;
          *v124 = xmmword_1800240A0;
          v124[1] = xmmword_1800240B0;
          v124[2] = xmmword_1800240C0;
          v124[3] = xmmword_1800240D0;
          v124[4] = xmmword_1800240E0;
          v124[5] = xmmword_1800240F0;
          v124[6] = xmmword_180024100;
          v124[7] = xmmword_180024110;
          v124[8] = xmmword_180024120;
          v124[9] = xmmword_180024130;
          *((_DWORD *)v120 + 8) = 8;
          v125 = GetProcessHeap();
          v126 = HeapAlloc(v125, 8u, 8u);
          if ( v126 )
          {
            v120[5] = v126;
            *v126 = qword_180024140;
            jj = v120;
            v111 = 0;
            v112 = jj;
            jj = 0;
LABEL_124:
            v1317 = v112;
            v113 = GetProcessHeap();
            HeapFree(v113, 0, lpMem);
            v114 = jj;
            if ( jj )
            {
              v1352 = (void *)*((_QWORD *)jj + 1);
              if ( v1352 )
              {
                v115 = GetProcessHeap();
                HeapFree(v115, 0, v1352);
                v114 = jj;
                *((_QWORD *)jj + 1) = 0;
              }
              v1352 = (void *)*((_QWORD *)v114 + 3);
              if ( v1352 )
              {
                v116 = GetProcessHeap();
                HeapFree(v116, 0, v1352);
                v114 = jj;
                *((_QWORD *)jj + 3) = 0;
              }
              v1352 = (void *)*((_QWORD *)v114 + 5);
              if ( v1352 )
              {
                v117 = GetProcessHeap();
                HeapFree(v117, 0, v1352);
                *((_QWORD *)jj + 5) = 0;
              }
              v118 = GetProcessHeap();
              HeapFree(v118, 0, jj);
              v119 = v1317;
            }
            else
            {
              v119 = v1317;
            }
            v9 = v111 | 0x10000000;
            if ( v9 < 0 )
              goto LABEL_332;
            v132 = *v119 + 4;
            LODWORD(v1327) = 0;
            if ( v132 >= 4 )
            {
              v133 = v132 + 4;
              if ( v132 + 4 >= v132 )
              {
                v134 = v133 + v119[4];
                dwBytes = (SIZE_T)(v119 + 4);
                if ( v134 >= v133 )
                {
                  v135 = v134 + 4;
                  if ( v134 + 4 >= v134 )
                  {
                    v136 = v135 + v119[8];
                    *(_DWORD *)Size = v136;
                    if ( v136 >= v135 )
                    {
                      v137 = v136;
                      v138 = GetProcessHeap();
                      v139 = HeapAlloc(v138, 8u, v137);
                      v1316 = v139;
                      if ( !v139 )
                      {
                        v9 = -805306345;
LABEL_330:
                        v145 = v1318;
                        goto LABEL_335;
                      }
                      v140 = (const void **)v1317;
                      *v139 = *(_DWORD *)v1317;
                      v1352 = v139 + 1;
                      if ( v139 + 1 < v139 )
                      {
                        v1316 = v139;
                      }
                      else
                      {
                        memcpy(v139 + 1, v140[1], *(unsigned int *)v140);
                        v141 = (char *)v1352 + *(unsigned int *)v140;
                        if ( v141 >= v1352 )
                        {
                          v142 = (unsigned int *)dwBytes;
                          *v141 = *(_DWORD *)dwBytes;
                          v1352 = v141 + 1;
                          if ( v141 + 1 >= v141 )
                          {
                            memcpy(v141 + 1, v140[3], *v142);
                            v143 = (char *)v1352 + *(unsigned int *)dwBytes;
                            if ( v143 >= v1352 )
                            {
                              *v143 = *((_DWORD *)v140 + 8);
                              v1352 = v143 + 1;
                              if ( v143 + 1 >= v143 )
                              {
                                memcpy(v143 + 1, v140[5], *((unsigned int *)v140 + 8));
                                if ( (char *)v1352 + *((unsigned int *)v140 + 8) >= v1352 )
                                {
                                  v144 = v1316;
                                  v145 = v1318;
                                  v1325 = v1316;
                                  LODWORD(v1327) = *(_DWORD *)Size;
                                  if ( !v19 || *(_DWORD *)&Size[4] <= 1u )
                                  {
LABEL_173:
                                    v9 = -1073741811;
                                    goto LABEL_335;
                                  }
                                  v147 = v19;
                                  for ( n = 0; ; n = 1 )
                                  {
                                    LODWORD(v1334) = *v147;
                                    v149 = v147 + 1;
                                    if ( n )
                                      break;
                                    if ( v149 < v147 )
                                      goto LABEL_337;
                                    v147 = (_DWORD *)((char *)v149 + (unsigned int)v1334);
                                    if ( v147 < v149 )
                                      goto LABEL_337;
                                  }
                                  if ( v149 < v147 )
                                    goto LABEL_337;
                                  if ( *(_DWORD *)&Size[4] <= 2u )
                                    goto LABEL_173;
                                  v1341 = (SIZE_T)v19;
                                  for ( *(_DWORD *)Size = 0; ; ++*(_DWORD *)Size )
                                  {
                                    v1316 = Src;
                                    jj = v1319;
                                    v1342 = v19;
                                    v150 = *(_DWORD *)v1341;
                                    dwBytes = v1341 + 4;
                                    LODWORD(v1338) = v150;
                                    lpMem = v1318;
                                    *(_QWORD *)&Size[4] = v140;
                                    v1335 = v144;
                                    if ( *(_DWORD *)Size >= 2u )
                                      break;
                                    if ( dwBytes < v1341 )
                                      goto LABEL_337;
                                    v1341 = dwBytes + (unsigned int)v1338;
                                    if ( v1341 < dwBytes )
                                      goto LABEL_337;
                                  }
                                  if ( dwBytes < v1341
                                    || (unsigned int)v1334 >= 0xFFFFFFB8
                                    || (v151 = v1334 + 76, (int)v1334 + 76 < (unsigned int)(v1334 + 72))
                                    || (*(_DWORD *)Size = v151 + v1338, v151 + (unsigned int)v1338 < v151) )
                                  {
LABEL_337:
                                    v9 = -1073741675;
                                    goto LABEL_335;
                                  }
                                  if ( v151 + (unsigned int)v1338 > 0x400000 )
                                  {
                                    v9 = -2147418113;
                                    v1317 = *(LPVOID *)&Size[4];
                                    v1325 = v144;
                                    goto LABEL_334;
                                  }
                                  v152 = v151 + v1338;
                                  v153 = GetProcessHeap();
                                  v154 = HeapAlloc(v153, 8u, v152);
                                  v145 = lpMem;
                                  v155 = v154;
                                  v156 = jj;
                                  v1322 = v154;
                                  v1325 = v1335;
                                  v1317 = *(LPVOID *)&Size[4];
                                  v1318 = lpMem;
                                  v1319 = jj;
                                  if ( !v154 )
                                  {
                                    v9 = -805306345;
                                    Src = v1316;
                                    v1322 = 0;
                                    goto LABEL_335;
                                  }
                                  v157 = *(void **)&Size[4];
                                  v158 = v1335;
                                  v159 = v1316;
                                  Src = v1316;
                                  phModule = 0;
                                  v1373 = 0;
                                  v1374 = 0;
                                  if ( !v1335 )
                                  {
                                    v9 = -2147024809;
LABEL_195:
                                    v1322 = v155;
                                    v1325 = v158;
                                    v1317 = v157;
                                    v1319 = v156;
                                    Src = v159;
                                    goto LABEL_334;
                                  }
                                  *(_QWORD *)&v1373 = v1335;
                                  LODWORD(v1374) = v1327;
                                  *(_QWORD *)((char *)&v1374 + 4) = *(unsigned int *)Size;
                                  *((_QWORD *)&v1373 + 1) = v154;
                                  if ( GetModuleHandleExW(1u, L"ntdll.dll", &phModule)
                                    && (NtQuerySystemInformation = (NTSTATUS (__stdcall *)(SYSTEM_INFORMATION_CLASS, PVOID, ULONG, PULONG))GetProcAddress(phModule, "NtQuerySystemInformation")) != 0 )
                                  {
                                    v162 = ((__int64 (__fastcall *)(__int64, __int128 *))NtQuerySystemInformation)(
                                             134,
                                             &v1373);
                                    v9 = v162 | 0x10000000;
                                    if ( v162 >= 0 )
                                    {
                                      v163 = DWORD1(v1374);
                                      goto LABEL_203;
                                    }
                                  }
                                  else
                                  {
                                    LastError = GetLastError();
                                    v9 = LastError;
                                    if ( LastError > 0 )
                                      v9 = (unsigned __int16)LastError | 0x80070000;
                                    if ( v9 >= 0 )
                                    {
                                      v9 = -2147467259;
                                      goto LABEL_194;
                                    }
                                  }
                                  v163 = *(_DWORD *)Size;
                                  if ( v9 == -805306333 )
                                  {
                                    v9 = -2147024774;
LABEL_201:
                                    v145 = lpMem;
                                    v1325 = v1335;
                                    v1317 = *(LPVOID *)&Size[4];
                                    v1319 = jj;
                                    v164 = v1316;
                                    goto LABEL_333;
                                  }
                                  if ( v9 >= 0 )
                                  {
LABEL_203:
                                    if ( v163 < 4 )
                                    {
                                      v9 = -805306306;
                                      goto LABEL_201;
                                    }
                                    v165 = *(unsigned int *)v1322;
                                    v166 = (char *)v1322 + 4;
                                    dwBytes = (SIZE_T)v1322 + 4;
                                    if ( (char *)v1322 + 4 >= v1322 )
                                    {
                                      if ( v163 - 4 < (unsigned int)v165 )
                                      {
LABEL_207:
                                        v9 = -805306306;
                                        goto LABEL_201;
                                      }
                                      v167 = &v166[v165];
                                      v1331 = v165;
                                      v1341 = (SIZE_T)&v166[v165];
                                      if ( &v166[v165] >= v166 && (unsigned int)(v165 + 4) >= 4 )
                                      {
                                        if ( v163 - ((_DWORD)v165 + 4) < 4 )
                                          goto LABEL_207;
                                        v168 = *(unsigned int *)v167;
                                        v169 = v167 + 4;
                                        *(_DWORD *)Size = *(_DWORD *)v167;
                                        if ( v167 + 4 >= v167 )
                                        {
                                          v170 = v165 + 8;
                                          if ( (int)v165 + 8 >= (unsigned int)(v165 + 4) )
                                          {
                                            if ( v163 - v170 < (unsigned int)v168 )
                                              goto LABEL_207;
                                            v171 = (unsigned __int64)v169 + v168;
                                            v1348 = v168;
                                            v1352 = (char *)v169 + v168;
                                            if ( (_DWORD *)((char *)v169 + v168) >= v169 )
                                            {
                                              v172 = v170 + v168;
                                              if ( v170 + (unsigned int)v168 >= v170 )
                                              {
                                                if ( v163 - v172 < 4 )
                                                  goto LABEL_207;
                                                v1346 = v171 + 4;
                                                if ( v171 + 4 >= v171 )
                                                {
                                                  v173 = v172 + 4;
                                                  if ( v172 + 4 >= v172 )
                                                  {
                                                    v174 = *(_DWORD *)v1352;
                                                    LODWORD(v1334) = v174;
                                                    if ( v163 - v173 < v174 )
                                                      goto LABEL_207;
                                                    if ( v173 + v174 < v173 )
                                                    {
                                                      v9 = -805306219;
                                                      goto LABEL_330;
                                                    }
                                                    if ( v163 != v173 + v174
                                                      || (_DWORD)v165 + (_DWORD)v168 + v174 + 12LL != v163 )
                                                    {
                                                      goto LABEL_207;
                                                    }
                                                    v175 = GetProcessHeap();
                                                    v176 = HeapAlloc(v175, 8u, 0x30u);
                                                    v1338 = (SIZE_T)v176;
                                                    if ( !v176 )
                                                    {
                                                      v9 = -805306345;
                                                      v145 = lpMem;
                                                      v19 = v1342;
                                                      v1325 = v1335;
                                                      v1317 = *(LPVOID *)&Size[4];
                                                      v1319 = jj;
                                                      v164 = v1316;
                                                      goto LABEL_333;
                                                    }
                                                    v1327 = 0;
                                                    if ( dwBytes )
                                                    {
                                                      *(_DWORD *)v176 = v165;
                                                      v177 = GetProcessHeap();
                                                      v178 = HeapAlloc(v177, 8u, v165);
                                                      if ( !v178 )
                                                      {
LABEL_236:
                                                        v179 = -1073741801;
                                                        v19 = v1342;
                                                        v1325 = v1335;
                                                        v1317 = *(LPVOID *)&Size[4];
                                                        v1318 = lpMem;
                                                        v1319 = jj;
                                                        Src = v1316;
                                                        v186 = v1338;
                                                        v1335 = v1342;
                                                        v1331 = *(_QWORD *)(v1338 + 8);
                                                        if ( v1331 )
                                                        {
                                                          v187 = GetProcessHeap();
                                                          HeapFree(v187, 0, (LPVOID)v1331);
                                                          v186 = v1338;
                                                          *(_QWORD *)(v1338 + 8) = 0;
                                                        }
                                                        v1331 = *(_QWORD *)(v186 + 24);
                                                        if ( v1331 )
                                                        {
                                                          v188 = GetProcessHeap();
                                                          HeapFree(v188, 0, (LPVOID)v1331);
                                                          v186 = v1338;
                                                          *(_QWORD *)(v1338 + 24) = 0;
                                                        }
                                                        v1331 = *(_QWORD *)(v186 + 40);
                                                        if ( v1331 )
                                                        {
                                                          v189 = GetProcessHeap();
                                                          HeapFree(v189, 0, (LPVOID)v1331);
                                                          *(_QWORD *)(v1338 + 40) = 0;
                                                        }
                                                        v190 = GetProcessHeap();
                                                        HeapFree(v190, 0, (LPVOID)v1338);
                                                        v191 = (size_t *)v1327;
                                                        goto LABEL_246;
                                                      }
                                                      v176[1] = v178;
                                                      v179 = 0;
                                                      memcpy(v178, (const void *)dwBytes, v1331);
                                                    }
                                                    else
                                                    {
                                                      *(_DWORD *)v176 = 0;
                                                      v179 = 0;
                                                      v176[1] = 0;
                                                    }
                                                    if ( v1341 == -4 )
                                                    {
                                                      *((_DWORD *)v176 + 4) = 0;
                                                      v176[3] = 0;
                                                    }
                                                    else
                                                    {
                                                      *((_DWORD *)v176 + 4) = *(_DWORD *)Size;
                                                      v180 = GetProcessHeap();
                                                      v181 = HeapAlloc(v180, 8u, v1348);
                                                      if ( !v181 )
                                                      {
LABEL_235:
                                                        v1338 = (SIZE_T)v176;
                                                        goto LABEL_236;
                                                      }
                                                      v176[3] = v181;
                                                      v179 = 0;
                                                      memcpy(v181, (const void *)(v1341 + 4), v1348);
                                                    }
                                                    if ( v1346 )
                                                    {
                                                      v182 = (unsigned int)v1334;
                                                      *((_DWORD *)v176 + 8) = v1334;
                                                      v183 = v182;
                                                      v1331 = v182;
                                                      v184 = GetProcessHeap();
                                                      v185 = HeapAlloc(v184, 8u, v183);
                                                      if ( !v185 )
                                                        goto LABEL_235;
                                                      v176[5] = v185;
                                                      v179 = 0;
                                                      memcpy(v185, (const void *)v1346, v1331);
                                                    }
                                                    else
                                                    {
                                                      *((_DWORD *)v176 + 8) = 0;
                                                      v176[5] = 0;
                                                    }
                                                    v191 = v176;
                                                    v19 = v1342;
                                                    v1325 = v1335;
                                                    v1317 = *(LPVOID *)&Size[4];
                                                    v1318 = lpMem;
                                                    v1319 = jj;
                                                    Src = v1316;
                                                    v1327 = (SIZE_T)v191;
                                                    v1335 = v1342;
LABEL_246:
                                                    if ( v179 < 0 )
                                                    {
                                                      if ( v191 )
                                                      {
                                                        v1331 = v191[1];
                                                        if ( v1331 )
                                                        {
                                                          v192 = GetProcessHeap();
                                                          HeapFree(v192, 0, (LPVOID)v1331);
                                                          v191 = (size_t *)v1327;
                                                          *(_QWORD *)(v1327 + 8) = 0;
                                                        }
                                                        v1331 = v191[3];
                                                        if ( v1331 )
                                                        {
                                                          v193 = GetProcessHeap();
                                                          HeapFree(v193, 0, (LPVOID)v1331);
                                                          v191 = (size_t *)v1327;
                                                          *(_QWORD *)(v1327 + 24) = 0;
                                                        }
                                                        v1331 = v191[5];
                                                        if ( v1331 )
                                                        {
                                                          v194 = GetProcessHeap();
                                                          HeapFree(v194, 0, (LPVOID)v1331);
                                                          *(_QWORD *)(v1327 + 40) = 0;
                                                        }
                                                        v195 = GetProcessHeap();
                                                        HeapFree(v195, 0, (LPVOID)v1327);
                                                      }
                                                    }
                                                    else
                                                    {
                                                      v1333 = v191;
                                                    }
                                                    v9 = v179 | 0x10000000;
                                                    if ( v9 < 0 )
                                                      goto LABEL_330;
                                                    if ( !v1333
                                                      || (dwBytes = *((_QWORD *)v1333 + 1)) == 0
                                                      || !*(_DWORD *)v1333 )
                                                    {
                                                      v9 = -805306355;
                                                      goto LABEL_330;
                                                    }
                                                    jj = (LPVOID)(*(unsigned int *)v1333 - 8LL);
                                                    v1342 = (LPVOID)sub_1800010C0(jj);
                                                    if ( !v1342 )
                                                    {
LABEL_288:
                                                      v1328 = 0;
                                                      v9 = -805306367;
                                                      goto LABEL_330;
                                                    }
                                                    v196 = 0;
                                                    v1341 = dwBytes;
                                                    v197 = (unsigned __int64)jj;
                                                    uBytes_4 = 0;
                                                    v1316 = (LPVOID)0x7F1137FAB69605ELL;
                                                    v1346 = (unsigned __int8)jj & 7;
                                                    lpMem = v1342;
                                                    if ( ((unsigned __int8)jj & 7) != 0 )
                                                    {
                                                      LODWORD(v1328) = 0;
                                                      LODWORD(v1338) = 0;
                                                      *(_DWORD *)Size = 0;
                                                      v198 = 0;
                                                      v199 = 0;
                                                      v200 = 0;
                                                      v201 = (unsigned __int8 *)v1341;
                                                      do
                                                      {
                                                        v202 = *v201++;
                                                        *(_DWORD *)&Size[4] = v202;
                                                        *(_DWORD *)Size = 8 * v198;
                                                        if ( (unsigned int)v198 >= 4 )
                                                        {
                                                          *(_DWORD *)&Size[4] <<= 56 - Size[0];
                                                          v199 |= *(_DWORD *)&Size[4];
                                                        }
                                                        else
                                                        {
                                                          *(_DWORD *)&Size[4] <<= 24 - Size[0];
                                                          v200 |= *(_DWORD *)&Size[4];
                                                        }
                                                        ++v198;
                                                      }
                                                      while ( v198 < (int)v1346 );
                                                      LODWORD(v1338) = v200;
                                                      v196 = uBytes_4;
                                                      LODWORD(v1328) = v199;
                                                      v13 = v1340;
                                                      v1341 = (SIZE_T)v201;
                                                      v203 = v1346;
                                                      v197 = (unsigned __int64)jj;
                                                      v1335 = v19;
                                                      v204 = (unsigned int)v1338 ^ 0x92F65A5;
                                                      *(_DWORD *)Size = 0;
                                                      v205 = (unsigned int)v1328 ^ 0x699A899C;
                                                      v206 = v1338 ^ 0x92F65A5;
                                                      v207 = (unsigned int)v1328 ^ 0x699A899C;
                                                      if ( (_DWORD)v1346 )
                                                      {
                                                        v208 = lpMem;
                                                        v209 = *(_DWORD *)Size;
                                                        do
                                                        {
                                                          v1331 = (size_t)(v208 + 1);
                                                          if ( v209 >= 4 )
                                                          {
                                                            v207 = __ROR4__(v207, 24);
                                                            v210 = v207;
                                                          }
                                                          else
                                                          {
                                                            v206 = __ROR4__(v206, 24);
                                                            v210 = v206;
                                                          }
                                                          *v208 = v210;
                                                          ++v209;
                                                          v208 = (_BYTE *)v1331;
                                                        }
                                                        while ( (int)v209 < (int)v203 );
                                                        lpMem = (LPVOID)v1331;
                                                      }
                                                      if ( v203 <= 4 )
                                                      {
                                                        v211 = 0;
                                                        if ( v203 < 4 )
                                                          v204 = (unsigned int)v204 >> (8 * (4 - v203)) << (8 * (4 - v203));
                                                      }
                                                      else
                                                      {
                                                        v211 = v205 >> (8 * (8 - v203)) << (8 * (8 - v203));
                                                      }
                                                    }
                                                    else
                                                    {
                                                      v211 = 0;
                                                      LODWORD(v1338) = 0;
                                                      v204 = 0;
                                                      LODWORD(v1328) = -1;
                                                    }
                                                    if ( v197 >> 3 )
                                                    {
                                                      v212 = HIDWORD(v1316);
                                                      v213 = (unsigned __int8 *)v1341;
                                                      v214 = HIDWORD(v1316) ^ 0xAB69605E;
                                                      v215 = lpMem;
                                                      v216 = v197 >> 3;
                                                      v217 = (int)v1328;
                                                      *(_DWORD *)&Size[4] = WORD2(v1316);
                                                      LODWORD(v1327) = 24670;
                                                      v218 = v1338;
                                                      v1346 = 0;
                                                      *(_DWORD *)Size = HIDWORD(v1316) ^ 0xAB69605E;
                                                      do
                                                      {
                                                        v219 = *v213;
                                                        v220 = v213[1];
                                                        v221 = v213[4];
                                                        v213 += 8;
                                                        v222 = *(v213 - 5)
                                                             | ((*(v213 - 6) | (((v219 << 8) | v220) << 8)) << 8);
                                                        v223 = v204 ^ v222;
                                                        v224 = *(v213 - 1)
                                                             | ((*(v213 - 2) | ((*(v213 - 3) | (v221 << 8)) << 8)) << 8);
                                                        v225 = v204 ^ v222 ^ v214 ^ v211 ^ v224;
                                                        v226 = v223
                                                             ^ (__ROR4__(v225, 22)
                                                              + *(_DWORD *)&Size[4] * __ROR4__(v225 + 1419157410, 27));
                                                        v227 = v225
                                                             ^ (WORD1(v1316) * __ROR4__(v212 + v226, 9)
                                                              - __ROR4__(v226, 30));
                                                        v228 = v226
                                                             ^ (v1327 * (v227 - *(_DWORD *)&Size[4]) - (v227 >> 13));
                                                        v229 = v227
                                                             ^ (HIWORD(v1316) * __ROR4__(WORD1(v1316) ^ v228, 26)
                                                              - __ROR4__(v228, 30));
                                                        v230 = v228 ^ (v212 - (v229 ^ 0xAB69605E));
                                                        v231 = v229
                                                             ^ (WORD1(v1316) * (*(_DWORD *)&Size[4] ^ v230))
                                                             ^ __ROR4__(v230, 6);
                                                        v232 = v230
                                                             ^ (__ROR4__(v231, 30) + v1327 * __ROR4__(v212 + v231, 15));
                                                        v233 = v231
                                                             ^ (HIWORD(v1316) * __ROR4__(v232 + 1419157410, 14)
                                                              - __ROR4__(v232, 24));
                                                        v234 = v232
                                                             ^ __ROR4__(v233, 10)
                                                             ^ (*(_DWORD *)&Size[4] * __ROR4__(v233 ^ 0xAB69605E, 12));
                                                        v235 = v234
                                                             ^ (HIWORD(v1316)
                                                              * (v1327
                                                               + __ROR4__(
                                                                   ~(v233
                                                                   ^ (v234 >> 10)
                                                                   ^ (WORD1(v1316) * (v234 ^ HIWORD(v1316)))),
                                                                   5)));
                                                        v236 = v233
                                                             ^ (v234 >> 10)
                                                             ^ (WORD1(v1316) * (v234 ^ HIWORD(v1316)))
                                                             ^ (v235 - HIWORD(v1316))
                                                             ^ 0xAB69605E;
                                                        v237 = v235
                                                             ^ ((v236 >> 2)
                                                              + *(_DWORD *)&Size[4] * __ROR4__(v236 ^ HIWORD(v1316), 30));
                                                        v238 = v236
                                                             ^ (__ROR4__(v237, 25)
                                                              + WORD1(v1316) * __ROR4__(v237 - HIDWORD(v1316), 6));
                                                        v239 = v237
                                                             ^ (v1327 * (*(_DWORD *)&Size[4] ^ v238) + __ROR4__(v238, 9));
                                                        v240 = v238
                                                             ^ (__ROR4__(v239, 25)
                                                              + HIWORD(v1316) * __ROR4__(WORD1(v1316) ^ v239, 27));
                                                        v212 = HIDWORD(v1316);
                                                        v241 = *(_DWORD *)Size ^ v239 ^ v240;
                                                        v242 = v240
                                                             ^ (*(_DWORD *)&Size[4] * (__ROR4__(v241, 3) - WORD1(v1316)));
                                                        v243 = v241
                                                             ^ (v1327 * __ROR4__(v242 - HIDWORD(v1316), 1)
                                                              - __ROR4__(v242, 6));
                                                        v244 = v242
                                                             ^ (__ROR4__(v243, 18)
                                                              + HIWORD(v1316) * __ROR4__(v243 - 1419157410, 29));
                                                        v245 = v243
                                                             ^ (*(_DWORD *)&Size[4] * __ROR4__(v244 - 1419157410, 17)
                                                              - __ROR4__(v244, 14));
                                                        v214 = *(_DWORD *)Size;
                                                        v246 = v244 ^ (v245 >> 3) ^ (WORD1(v1316) * (v1327 ^ v245));
                                                        v211 = v217 ^ v246;
                                                        v217 = v224;
                                                        v204 = v218
                                                             ^ v245
                                                             ^ __ROR4__(v246, 30)
                                                             ^ ((_DWORD)v1327 * __ROR4__(HIDWORD(v1316) ^ v246, 28));
                                                        v218 = v222;
                                                        v215[3] = v204;
                                                        v215[7] = v211;
                                                        v215[2] = __ROR4__(v204, 8);
                                                        v215[6] = __ROR4__(v211, 8);
                                                        v215[1] = __ROR4__(v204, 16);
                                                        v215[5] = __ROR4__(v211, 16);
                                                        *v215 = __ROR4__(v204, 24);
                                                        v215[4] = __ROR4__(v211, 24);
                                                        v215 += 8;
                                                        ++v1346;
                                                      }
                                                      while ( v1346 < v216 );
                                                      v196 = uBytes_4;
                                                      v13 = v1340;
                                                      v10 = -805306219;
                                                      v19 = v1335;
                                                      v8 = 4;
                                                      v197 = (unsigned __int64)jj;
                                                    }
                                                    for ( ii = 0; ii < v197; ++ii )
                                                      v196 ^= *((_BYTE *)v1342 + ii);
                                                    if ( v196 != *(_QWORD *)(v197 + dwBytes) )
                                                    {
                                                      sub_180010DC8(v1342, v197, v204, v211);
                                                      goto LABEL_288;
                                                    }
                                                    v248 = Src;
                                                    v249 = v1319;
                                                    v145 = v1318;
                                                    v250 = v1317;
                                                    v251 = v1325;
                                                    v252 = v1322;
                                                    if ( (unsigned int)jj < 4 )
                                                    {
                                                      LODWORD(v253) = -1073741762;
                                                      v1328 = v1342;
LABEL_319:
                                                      v9 = v253 | 0x10000000;
                                                      goto LABEL_335;
                                                    }
                                                    v1328 = v1342;
                                                    v1335 = (char *)v1342 + 4;
                                                    if ( (char *)v1342 + 4 < v1342 )
                                                    {
                                                      LODWORD(v253) = -1073741675;
                                                      goto LABEL_319;
                                                    }
                                                    if ( (unsigned int)((_DWORD)jj - 4) < 4 )
                                                      goto LABEL_293;
                                                    if ( (char *)v1335 + 4 < (char *)v1342 + 4 )
                                                      goto LABEL_327;
                                                    LODWORD(v1334) = *((_DWORD *)v1342 + 1);
                                                    if ( (unsigned int)((_DWORD)jj - 8) < *((_DWORD *)v1342 + 1) )
                                                    {
LABEL_293:
                                                      v254 = v1342;
                                                      LODWORD(v253) = -1073741762;
LABEL_294:
                                                      v1328 = v254;
                                                      goto LABEL_319;
                                                    }
                                                    if ( *((_DWORD *)v1342 + 1) >= 0xFFFFFFF8 )
                                                    {
LABEL_327:
                                                      LODWORD(v253) = -1073741675;
                                                    }
                                                    else
                                                    {
                                                      v1341 = *((unsigned int *)v1342 + 1);
                                                      v1316 = (char *)v1342 + v1341 + 8;
                                                      if ( (char *)v1342 + (unsigned int)jj >= v1316 )
                                                      {
                                                        v253 = (unsigned __int64)v1335 + 4;
                                                        if ( (unsigned __int64)(unsigned int)jj
                                                           + (char *)v1342
                                                           - v1341
                                                           - ((_BYTE *)v1335
                                                            + 4) < 8 )
                                                        {
                                                          *(_DWORD *)Size = 0;
                                                          if ( v1335 != (LPVOID)-4LL )
                                                          {
                                                            if ( (unsigned __int64)v1316 < v253 )
                                                            {
                                                              LODWORD(v253) = -1073741675;
                                                            }
                                                            else
                                                            {
                                                              v1328 = v1342;
                                                              v255 = (char *)v1335 + 4;
                                                              for ( jj = (char *)v1335 + 4; ; jj = (LPVOID)v1331 )
                                                              {
                                                                LODWORD(v253) = 0;
                                                                if ( v255 >= v1316 )
                                                                  break;
                                                                if ( v255 + 1 < v255 )
                                                                  goto LABEL_311;
                                                                if ( v255 + 1 > v1316 )
                                                                  goto LABEL_313;
                                                                v256 = (unsigned int)(*v255 + 4);
                                                                if ( (unsigned int)v256 < 4
                                                                  || (v1331 = (size_t)jj + v256, (char *)jj + v256 < jj) )
                                                                {
LABEL_311:
                                                                  LODWORD(v253) = -1073741675;
                                                                  goto LABEL_319;
                                                                }
                                                                Src = v248;
                                                                v1319 = v249;
                                                                v1318 = v145;
                                                                v1317 = v250;
                                                                v1325 = v251;
                                                                v1322 = v252;
                                                                if ( v1331 > (unsigned __int64)v1316 )
                                                                {
                                                                  LODWORD(v253) = -1073741811;
                                                                  v1322 = v252;
                                                                  v1325 = v251;
                                                                  v1317 = v250;
                                                                  v1318 = v145;
                                                                  v1319 = v249;
                                                                  Src = v248;
                                                                  goto LABEL_319;
                                                                }
                                                                ++*(_DWORD *)Size;
                                                                v255 = (_DWORD *)v1331;
                                                              }
                                                              if ( v255 == v1316 )
                                                                goto LABEL_315;
LABEL_313:
                                                              LODWORD(v253) = -1073741811;
                                                            }
                                                            goto LABEL_319;
                                                          }
LABEL_315:
                                                          v257 = 0;
                                                          v1346 = 0;
                                                          LODWORD(v1338) = *(_DWORD *)v1342;
                                                          if ( (_DWORD)v1334 )
                                                          {
                                                            v258 = GetProcessHeap();
                                                            v1346 = (SIZE_T)HeapAlloc(v258, 8u, v1341);
                                                            v257 = (void *)v1346;
                                                            if ( !v1346 )
                                                            {
                                                              LODWORD(v253) = -1073741801;
LABEL_318:
                                                              v145 = v1318;
                                                              goto LABEL_319;
                                                            }
                                                            LODWORD(v253) = 0;
                                                          }
                                                          if ( v1335 != (LPVOID)-4LL )
                                                            memcpy(v257, (char *)v1335 + 4, v1341);
                                                          v1336 = (LPVOID)v1346;
                                                          LODWORD(v1315) = *(_DWORD *)Size;
                                                          if ( (_DWORD)v1338 != *(_DWORD *)Size )
                                                            LODWORD(v253) = -1073741762;
                                                          goto LABEL_318;
                                                        }
                                                      }
                                                      LODWORD(v253) = -1073741762;
                                                    }
                                                    v254 = v1328;
                                                    goto LABEL_294;
                                                  }
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                    v9 = -805306219;
LABEL_332:
                                    v164 = Src;
                                    v145 = v1318;
LABEL_333:
                                    Src = v164;
LABEL_334:
                                    v1318 = v145;
LABEL_335:
                                    if ( !v145 )
                                      goto LABEL_340;
                                    goto LABEL_339;
                                  }
LABEL_194:
                                  v159 = Src;
                                  v156 = v1319;
                                  v145 = v1318;
                                  v157 = v1317;
                                  v155 = v1322;
                                  v158 = v1325;
                                  goto LABEL_195;
                                }
                              }
                            }
                          }
                        }
                      }
                      v146 = GetProcessHeap();
                      HeapFree(v146, 0, v1316);
                    }
                  }
                }
              }
            }
            v9 = -805306219;
            v145 = v1318;
            goto LABEL_335;
          }
        }
        else
        {
          v1316 = v120;
        }
      }
      v111 = -1073741801;
      v127 = v1316;
      v1352 = (void *)*((_QWORD *)v1316 + 1);
      if ( v1352 )
      {
        v128 = GetProcessHeap();
        HeapFree(v128, 0, v1352);
        v127 = v1316;
        *((_QWORD *)v1316 + 1) = 0;
      }
      v1352 = (void *)*((_QWORD *)v127 + 3);
      if ( v1352 )
      {
        v129 = GetProcessHeap();
        HeapFree(v129, 0, v1352);
        v127 = v1316;
        *((_QWORD *)v1316 + 3) = 0;
      }
      v1352 = (void *)*((_QWORD *)v127 + 5);
      if ( v1352 )
      {
        v130 = GetProcessHeap();
        HeapFree(v130, 0, v1352);
        *((_QWORD *)v1316 + 5) = 0;
      }
      v131 = GetProcessHeap();
      HeapFree(v131, 0, v1316);
    }
    else
    {
      v111 = -1073741801;
    }
    v112 = v1317;
    goto LABEL_124;
  }
  v9 = -805306345;
LABEL_362:
  if ( v9 < 0 )
    goto LABEL_431;
  if ( !(_DWORD)v1315 )
    goto LABEL_364;
  if ( !v1336 )
  {
    v9 = -1073741811;
    goto LABEL_431;
  }
  if ( (char *)v1336 + 4 < v1336 )
  {
    v9 = -1073741675;
    goto LABEL_431;
  }
  v273 = 0;
  if ( *(_DWORD *)v1336 )
    v273 = (int *)((char *)v1336 + 4);
  if ( *(_DWORD *)v1336 != 4 )
  {
    v9 = -1073741789;
    goto LABEL_431;
  }
  v9 = *v273;
  if ( v9 == -805306333 )
  {
    v20 = -2147024774;
  }
  else
  {
    v20 = v9;
    if ( v9 != -2147024774 && v9 < 0 )
      goto LABEL_431;
  }
  if ( (_DWORD)v1315 != 6 )
  {
LABEL_364:
    v9 = -1073425151;
    goto LABEL_431;
  }
  v274 = v1336;
  for ( kk = 0; ; kk = 1 )
  {
    v276 = v274 + 1;
    if ( kk )
      break;
    if ( v276 < v274 )
      goto LABEL_424;
    v274 = (_DWORD *)((char *)v276 + (unsigned int)*v274);
    if ( v274 < v276 )
      goto LABEL_424;
  }
  if ( v276 < v274 )
    goto LABEL_424;
  v277 = 0;
  if ( *v274 )
    v277 = (size_t *)(v274 + 1);
  if ( *v274 != 8 )
    goto LABEL_417;
  v278 = v1336;
  v1331 = *v277;
  for ( mm = 0; ; ++mm )
  {
    v280 = v278 + 1;
    if ( mm >= 2 )
      break;
    if ( v280 < v278 )
      goto LABEL_424;
    v278 = (_DWORD *)((char *)v280 + (unsigned int)*v278);
    if ( v278 < v280 )
      goto LABEL_424;
  }
  if ( v280 < v278 )
    goto LABEL_424;
  if ( *v278 != 4 )
  {
LABEL_417:
    v9 = -1073741789;
    goto LABEL_431;
  }
  v281 = (unsigned int *)v1336;
  for ( nn = 0; ; ++nn )
  {
    v283 = v281 + 1;
    if ( nn >= 3 )
      break;
    if ( v283 < v281 )
      goto LABEL_420;
    v281 = (unsigned int *)((char *)v283 + *v281);
    if ( v281 < v283 )
      goto LABEL_420;
  }
  if ( v283 < v281 )
  {
LABEL_420:
    v9 = -1073741675;
    goto LABEL_428;
  }
  v284 = v1336;
  for ( i1 = 0; ; ++i1 )
  {
    v286 = v284 + 1;
    if ( i1 >= 4 )
      break;
    if ( v286 < v284 )
      goto LABEL_424;
    v284 = (_DWORD *)((char *)v286 + (unsigned int)*v284);
    if ( v284 < v286 )
      goto LABEL_424;
  }
  if ( v286 < v284 )
    goto LABEL_424;
  v287 = 0;
  if ( *v284 )
    v287 = v284 + 1;
  if ( *v284 != 4 )
    goto LABEL_417;
  v288 = v1336;
  LODWORD(v1315) = *v287;
  for ( i2 = 0; ; ++i2 )
  {
    v290 = v288 + 1;
    if ( i2 >= 5 )
      break;
    if ( v290 < v288 )
      goto LABEL_424;
    v288 = (_DWORD *)((char *)v290 + (unsigned int)*v288);
    if ( v288 < v290 )
      goto LABEL_424;
  }
  if ( v290 < v288 )
  {
LABEL_424:
    v9 = -1073741675;
    goto LABEL_431;
  }
  v291 = 0;
  if ( *v288 )
    v291 = v288 + 1;
  if ( *v288 != 4 )
    goto LABEL_417;
  if ( v1330 != v1331 )
    goto LABEL_364;
  v9 = 0;
  v13 = *v291;
  uBytes = v1315;
LABEL_429:
  if ( v20 )
    v9 = v20;
LABEL_431:
  if ( v19 )
  {
    v292 = GetProcessHeap();
    HeapFree(v292, 0, v19);
  }
  if ( v1336 )
  {
    v293 = GetProcessHeap();
    HeapFree(v293, 0, v1336);
  }
  v7 = Src;
  LODWORD(v1327) = v13;
  LODWORD(v1328) = uBytes;
  if ( Src )
    goto LABEL_439;
LABEL_440:
  if ( v1319 )
  {
    v295 = GetProcessHeap();
    HeapFree(v295, 0, v1319);
  }
  if ( v9 < 0 )
    goto LABEL_7;
  if ( !v13 )
    goto LABEL_475;
  v296 = 0;
  *(_OWORD *)v1350 = 0;
  v1336 = 0;
  v297 = GetProcessHeap();
  v298 = HeapAlloc(v297, 8u, 0xA0u);
  v299 = v298;
  if ( v298 )
  {
    *v298 = xmmword_180024150;
    v298[1] = xmmword_180024160;
    v298[2] = xmmword_180024170;
    v298[3] = xmmword_180024180;
    v298[4] = xmmword_180024190;
    v298[5] = xmmword_1800241A0;
    v298[6] = xmmword_1800241B0;
    v298[7] = xmmword_1800241C0;
    v298[8] = xmmword_1800241D0;
    v298[9] = xmmword_1800241E0;
    v300 = GetProcessHeap();
    v301 = HeapAlloc(v300, 8u, 8u);
    v1316 = v301;
    if ( !v301 )
    {
LABEL_456:
      v13 = v1327;
      uBytes = (unsigned int)v1328;
      goto LABEL_467;
    }
    *v301 = qword_180024090;
    v1331 = __rdtsc();
    *(_DWORD *)&Size[4] = 0;
    LODWORD(v1315) = 0;
    if ( (int)sub_180006270(4, 4, &v1315) < 0
      || (int)sub_180006270(0, (unsigned int)v1315, &Size[4]) < 0
      || (LODWORD(v1315) = v303, (int)sub_180006270(4, 160, &v1315) < 0)
      || (v304 = sub_180006270(*(unsigned int *)&Size[4], (unsigned int)v1315, &Size[4]), (v305 | v304) < 0)
      || (LODWORD(v1315) = 0, (int)sub_180006270(4, 8, &v1315) < 0)
      || (v306 = sub_180006270(*(unsigned int *)&Size[4], (unsigned int)v1315, &Size[4]), (v307 | v306) < 0)
      || (LODWORD(v1315) = 0, (int)sub_180006270(4, 8, &v1315) < 0)
      || (v308 = sub_180006270(*(unsigned int *)&Size[4], (unsigned int)v1315, &Size[4]), (v309 | v308) < 0) )
    {
      v296 = v302;
      v13 = v1327;
      uBytes = (unsigned int)v1328;
      goto LABEL_467;
    }
    HIDWORD(v1350[0]) = *(_DWORD *)&Size[4];
    v310 = *(_DWORD *)&Size[4];
    v311 = GetProcessHeap();
    v312 = HeapAlloc(v311, 8u, v310);
    if ( !v312 )
    {
      v296 = v1316;
      goto LABEL_456;
    }
    v1350[1] = (size_t)v312;
    v1352 = 0;
    LODWORD(v1350[0]) = 0;
    LODWORD(v1353) = 0;
    v296 = v1316;
    v13 = v1327;
    v1317 = v1316;
    v1330 = (SIZE_T)v312;
    uBytes = (unsigned int)v1328;
    if ( (int)sub_180006240(v312, 4, &v1353) < 0 || (unsigned __int64)(v313 + 2) > v1350[1] + HIDWORD(v1350[0]) )
      goto LABEL_467;
    v315 = v1353;
    *v313 = 4;
    *v315 = 4;
    v316 = 0;
    v317 = ++LODWORD(v1350[0]);
    v1352 = 0;
    LODWORD(v1353) = 0;
    if ( v299 )
    {
      if ( !v314 )
        goto LABEL_466;
    }
    else if ( v314 )
    {
      goto LABEL_467;
    }
    v318 = (unsigned int *)v1350[1];
    if ( v1350[1] )
    {
      v1330 = v1350[1];
      while ( 1 )
      {
        *(_DWORD *)Size = v316;
        if ( v316 >= v317 )
          break;
        v328 = *v318;
        LODWORD(v1315) = 0;
        if ( (int)sub_180006270(4, v328, &v1315) < 0 || (int)sub_180006240(v329, (unsigned int)v1315, &v1330) < 0 )
          goto LABEL_467;
        v318 = (unsigned int *)v1330;
        v316 = *(_DWORD *)Size + 1;
      }
      if ( (int)sub_180006240(v318, 4, &v1353) < 0 || (unsigned __int64)v330 + v331 + 4 > v1350[1] + HIDWORD(v1350[0]) )
        goto LABEL_467;
      *v330 = v331;
      if ( v299 )
        memcpy(v1353, v299, v331);
    }
    else
    {
      LODWORD(v1315) = 0;
      if ( (int)sub_180006270(4, v314, &v1315) < 0 )
        goto LABEL_467;
      if ( (int)sub_180006270(HIDWORD(v1350[0]), (unsigned int)v1315, (char *)v1350 + 4) < 0 )
        goto LABEL_466;
    }
    v332 = 0;
    v333 = ++LODWORD(v1350[0]);
    v1352 = 0;
    LODWORD(v1353) = 0;
    if ( !v296 )
      goto LABEL_467;
    v334 = (unsigned int *)v1350[1];
    if ( v1350[1] )
    {
      v1330 = v1350[1];
      while ( 1 )
      {
        *(_DWORD *)Size = v332;
        if ( v332 >= v333 )
          break;
        v335 = *v334;
        LODWORD(v1315) = 0;
        if ( (int)sub_180006270(4, v335, &v1315) < 0 || (int)sub_180006240(v336, (unsigned int)v1315, &v1330) < 0 )
          goto LABEL_467;
        v334 = (unsigned int *)v1330;
        v332 = *(_DWORD *)Size + 1;
      }
      if ( (int)sub_180006240(v334, 4, &v1353) < 0 || (unsigned __int64)v337 + v338 + 4 > v1350[1] + HIDWORD(v1350[0]) )
        goto LABEL_467;
      *v337 = v338;
      memcpy(v1353, v296, (unsigned int)v338);
    }
    else
    {
      LODWORD(v1315) = 0;
      if ( (int)sub_180006270(4, 8, &v1315) < 0 )
        goto LABEL_467;
      if ( (int)sub_180006270(HIDWORD(v1350[0]), (unsigned int)v1315, (char *)v1350 + 4) < 0 )
        goto LABEL_466;
    }
    v339 = (unsigned int *)v1350[1];
    v340 = ++LODWORD(v1350[0]);
    v1352 = 0;
    LODWORD(v1353) = 0;
    if ( v1350[1] )
    {
      v1330 = v1350[1];
      for ( i3 = 0; i3 < v340; i3 = v344 + 1 )
      {
        v342 = *v339;
        LODWORD(v1315) = 0;
        if ( (int)sub_180006270(4, v342, &v1315) < 0 || (int)sub_180006240(v343, (unsigned int)v1315, &v1330) < 0 )
          goto LABEL_467;
        v339 = (unsigned int *)v1330;
      }
      if ( (int)sub_180006240(v339, 4, &v1353) < 0 || (unsigned __int64)(v345 + 3) > v1350[1] + HIDWORD(v1350[0]) )
        goto LABEL_467;
      v346 = v1353;
      v347 = v1331;
      *v345 = 8;
      *v346 = v347;
    }
    else
    {
      LODWORD(v1315) = 0;
      if ( (int)sub_180006270(4, 8, &v1315) < 0 )
        goto LABEL_467;
      if ( (int)sub_180006270(HIDWORD(v1350[0]), (unsigned int)v1315, (char *)v1350 + 4) < 0 )
        goto LABEL_466;
    }
    ++LODWORD(v1350[0]);
    LODWORD(v1315) = 0;
    if ( (int)sub_180006270(4, 4, &v1315) < 0
      || (*(_DWORD *)Size = v1315, LODWORD(v1315) = 0, (int)sub_180006270(v348, v349, &v1315) < 0)
      || (int)sub_180006270(v350, (unsigned int)v1315, Size) < 0 )
    {
LABEL_466:
      v296 = v1317;
      goto LABEL_467;
    }
    LODWORD(v1328) = *(_DWORD *)Size;
    LODWORD(v1334) = 0;
    v1318 = 0;
    v1331 = __rdtsc();
    v1354 = v351;
    LODWORD(v1315) = 0;
    v352 = sub_180006270(v351, HIDWORD(v1350[0]), &v1354);
    if ( v352 < 0 )
    {
      jj = v299;
      v1340 = v13;
    }
    else
    {
      v354 = (v1354 + 7) & 0xFFFFFFF8;
      if ( v354 < v1354 )
        goto LABEL_466;
      v1354 = (v1354 + 7) & 0xFFFFFFF8;
      v355 = v354;
      v356 = GetProcessHeap();
      v1316 = HeapAlloc(v356, 8u, v355);
      v357 = v1316;
      if ( !v1316 )
      {
        v358 = -805306345;
        goto LABEL_610;
      }
      v1340 = v13;
      jj = v299;
      v1341 = (SIZE_T)v1316;
      *(_DWORD *)v1316 = v1350[0];
      v352 = sub_180006240(v357, 4, &v1341);
      if ( v352 < 0 )
      {
        v1316 = v359;
      }
      else
      {
        v363 = v1341;
        *(_DWORD *)v1341 = HIDWORD(v1350[0]);
        v352 = sub_180006240(v363, 4, &v1341);
        if ( v352 >= 0 )
        {
          *(_QWORD *)((char *)v1316 + v1354 - 8) = v1331;
          memcpy((void *)v1341, (const void *)v1350[1], HIDWORD(v1350[0]));
          v353 = v1354;
          v1318 = v1316;
          goto LABEL_525;
        }
      }
      v1340 = v13;
      uBytes = v361;
      jj = v299;
      v1317 = v360;
      LODWORD(v1328) = v362;
      v364 = GetProcessHeap();
      HeapFree(v364, 0, v1316);
      v353 = v1315;
    }
LABEL_525:
    v1322 = 0;
    v358 = v352 | 0x10000000;
    v1341 = 0;
    v1325 = 0;
    v1319 = 0;
    v1333 = 0;
    if ( v358 < 0 )
      goto LABEL_586;
    v365 = v1318;
    if ( !v1318 )
      goto LABEL_466;
    lpMem = (LPVOID)v353;
    if ( !v353 || (v1348 = v353 + 8LL, (dwBytes = sub_1800010C0(v1348)) == 0) )
    {
      v358 = -805306367;
      goto LABEL_587;
    }
    v366 = (unsigned __int64)lpMem;
    v367 = 0;
    v368 = 0;
    v1335 = 0;
    uBytes_4 = 0;
    if ( lpMem )
    {
      do
        v367 ^= v365[v368++];
      while ( v368 < (unsigned __int64)lpMem );
      uBytes_4 = v367;
    }
    Src = (void *)0xC81ECB17B1B54A58LL;
    v1316 = v365;
    v1342 = (LPVOID)dwBytes;
    v369 = (unsigned __int8)lpMem & 7;
    if ( ((unsigned __int8)lpMem & 7) != 0 )
    {
      v370 = 0;
      LODWORD(v1338) = 0;
      *(_DWORD *)&Size[4] = 0;
      v371 = 0;
      v372 = 0;
      v373 = v365;
      do
      {
        v374 = *v373++;
        LODWORD(v1315) = 8 * v370;
        if ( v370 >= 4 )
          v371 |= v374 << (56 - v1315);
        else
          v372 |= v374 << (24 - v1315);
        ++v370;
      }
      while ( (int)v370 < v369 );
      LODWORD(v1338) = v371;
      *(_DWORD *)&Size[4] = v372;
      v10 = -805306219;
      v1316 = v373;
      v366 = (unsigned __int64)lpMem;
      v1318 = v365;
      jj = v299;
      v1340 = v13;
      v375 = *(_DWORD *)&Size[4] ^ 0xB17A307A;
      *(_DWORD *)Size = 0;
      v376 = v371 ^ 0x42F6B18D;
      v377 = *(_DWORD *)&Size[4] ^ 0xB17A307A;
      v378 = v371 ^ 0x42F6B18D;
      if ( ((unsigned __int8)lpMem & 7) != 0 )
      {
        v379 = v1342;
        do
        {
          v1331 = (size_t)(v379 + 1);
          if ( *(_DWORD *)Size >= 4u )
          {
            v378 = __ROR4__(v378, 24);
            v380 = v378;
          }
          else
          {
            v377 = __ROR4__(v377, 24);
            v380 = v377;
          }
          *v379 = v380;
          ++*(_DWORD *)Size;
          v379 = (_BYTE *)v1331;
        }
        while ( *(int *)Size < v369 );
        v1342 = (LPVOID)v1331;
      }
      if ( (unsigned int)v369 <= 4 )
      {
        v381 = 0;
        if ( (unsigned int)v369 < 4 )
          v375 = v375 >> (8 * (4 - v369)) << (8 * (4 - v369));
      }
      else
      {
        v381 = v376 >> (8 * (8 - v369)) << (8 * (8 - v369));
      }
    }
    else
    {
      v375 = 0;
      v381 = -1;
      *(_DWORD *)&Size[4] = 0;
      LODWORD(v1338) = 0;
    }
    if ( v366 >> 3 )
    {
      v382 = WORD2(Src);
      v383 = v366 >> 3;
      v384 = (unsigned __int8 *)v1316;
      v385 = v1342;
      v386 = *(_DWORD *)&Size[4];
      *(_DWORD *)Size = 19032;
      LODWORD(v1327) = WORD1(Src);
      LODWORD(v1315) = HIWORD(Src);
      v387 = v1338;
      v1330 = 0;
      do
      {
        v388 = v384[1];
        v389 = *v384;
        v390 = v384[4];
        v384 += 8;
        v391 = *(v384 - 5) | ((*(v384 - 6) | ((v388 | (v389 << 8)) << 8)) << 8);
        v392 = *(v384 - 1) | ((*(v384 - 2) | ((*(v384 - 3) | (v390 << 8)) << 8)) << 8);
        v393 = v375 ^ v391 ^ HIDWORD(Src) ^ ((v381 ^ v392) - *(_DWORD *)Size);
        v394 = v381 ^ v392 ^ (__ROR4__(v393, 7) + WORD1(Src) * __ROR4__(v393 ^ HIDWORD(Src), 15));
        v395 = v393 ^ (v382 * __ROR4__(v394 - 1313519016, 9) - __ROR4__(v394, 10));
        v396 = v394 ^ (__ROR4__(v395, 27) + HIWORD(Src) * __ROR4__(v395 ^ v382, 28));
        v397 = v395 ^ (HIDWORD(Src) - (v396 ^ 0xB1B54A58));
        v398 = v396 ^ (WORD1(Src) * (v397 - *(_DWORD *)Size) - (v397 >> 6));
        v399 = v397 ^ (*(_DWORD *)Size * (v382 ^ __ROR4__(v398, 15)));
        v400 = v398 ^ (v382 * (HIWORD(Src) + __ROR4__(~v399, 3)));
        v401 = v399 ^ (v400 - HIDWORD(Src) - *(_DWORD *)Size);
        v402 = v400 ^ (v1327 * (v1315 ^ v401)) ^ __ROR4__(v401, 10);
        v403 = v401 ^ __ROR4__(v402, 3) ^ (v382 * __ROR4__(*(_DWORD *)Size ^ v402, 26));
        v404 = v402 ^ (*(_DWORD *)Size * (__ROR4__(v403, 15) - HIWORD(Src)));
        v405 = v403
             ^ (*(_DWORD *)Size * (v1315 ^ v404))
             ^ ((v404 ^ (v404 >> 14)) >> 1)
             ^ (*(_DWORD *)Size * ((8 * (v404 - v382)) | ((v404 - v382) >> 29)));
        v406 = v404 ^ (WORD1(Src) * (v405 - v382) - (v405 >> 13));
        v407 = v405 ^ __ROR4__(v406, 11) ^ (v382 * __ROR4__(-1313519016 - v406, 9));
        v408 = v406 ^ (v407 + 1313519016 - HIWORD(Src));
        v409 = v407 ^ (*(_DWORD *)Size * (v408 ^ WORD1(Src)) - __ROR4__(v408, 7));
        v410 = v408 ^ (WORD1(Src) * __ROR4__(HIWORD(Src) ^ v409, 28) - __ROR4__(v409, 16));
        v411 = v409 ^ (__ROR4__(v410, 4) + v382 * __ROR4__(-1313519016 - v410, 10));
        v412 = v410 ^ __ROR4__(v411, 9) ^ (HIWORD(Src) * __ROR4__(v411 + 1313519016, 4));
        v413 = v411 ^ (*(_DWORD *)Size * __ROR4__(v412 ^ HIDWORD(Src), 24) - __ROR4__(v412, 30));
        v414 = v412 ^ (WORD1(Src) * __ROR4__(HIDWORD(Src) - v413, 11) - __ROR4__(v413, 12));
        v415 = v414 ^ v387;
        v416 = v382 * (v414 ^ WORD1(Src));
        v417 = v414 >> 8;
        v418 = v415 ^ 0xB1B54A58;
        LODWORD(v1338) = v415;
        v419 = v386;
        v387 = v392;
        v386 = v391;
        v420 = v413 ^ v417 ^ v416;
        v375 = v420 ^ v419;
        v381 = HIDWORD(Src) ^ v420 ^ v418;
        v385[3] = v375;
        v385[7] = v381;
        v385[2] = __ROR4__(v375, 8);
        v385[6] = __ROR4__(v381, 8);
        v385[1] = __ROR4__(v375, 16);
        v385[5] = __ROR4__(v381, 16);
        *v385 = __ROR4__(v375, 24);
        v385[4] = __ROR4__(v381, 24);
        v385 += 8;
        ++v1330;
      }
      while ( v1330 < v383 );
      v367 = uBytes_4;
      v13 = v1340;
      v10 = -805306219;
      v299 = jj;
      v8 = 4;
      v365 = v1318;
      v366 = (unsigned __int64)lpMem;
    }
    *(_QWORD *)(dwBytes + v366) = v367;
    v421 = GetProcessHeap();
    v422 = HeapAlloc(v421, 8u, 0x30u);
    v1316 = v422;
    if ( v422 )
    {
      *v422 = v1348;
      v432 = GetProcessHeap();
      v433 = HeapAlloc(v432, 8u, (unsigned int)v1348);
      if ( v433 )
      {
        v1318 = v365;
        v434 = v1316;
        *((_QWORD *)v1316 + 1) = v433;
        memcpy(v433, (const void *)dwBytes, (unsigned int)v1348);
        v434[4] = 160;
        v435 = GetProcessHeap();
        v436 = HeapAlloc(v435, 8u, 0xA0u);
        if ( v436 )
        {
          *((_QWORD *)v434 + 3) = v436;
          *v436 = xmmword_1800240A0;
          v436[1] = xmmword_1800240B0;
          v436[2] = xmmword_1800240C0;
          v436[3] = xmmword_1800240D0;
          v436[4] = xmmword_1800240E0;
          v436[5] = xmmword_1800240F0;
          v436[6] = xmmword_180024100;
          v436[7] = xmmword_180024110;
          v436[8] = xmmword_180024120;
          v436[9] = xmmword_180024130;
          v434[8] = 8;
          v437 = GetProcessHeap();
          v438 = HeapAlloc(v437, 8u, 8u);
          if ( v438 )
          {
            *((_QWORD *)v434 + 5) = v438;
            *v438 = qword_180024140;
            v1335 = v434;
            v423 = 0;
            v424 = v1335;
            v1335 = 0;
LABEL_557:
            v1322 = v424;
            v425 = GetProcessHeap();
            HeapFree(v425, 0, (LPVOID)dwBytes);
            v426 = v1335;
            if ( v1335 )
            {
              v1331 = *((_QWORD *)v1335 + 1);
              if ( v1331 )
              {
                v427 = GetProcessHeap();
                HeapFree(v427, 0, (LPVOID)v1331);
                v426 = v1335;
                *((_QWORD *)v1335 + 1) = 0;
              }
              v1331 = v426[3];
              if ( v1331 )
              {
                v428 = GetProcessHeap();
                HeapFree(v428, 0, (LPVOID)v1331);
                v426 = v1335;
                *((_QWORD *)v1335 + 3) = 0;
              }
              v1331 = v426[5];
              if ( v1331 )
              {
                v429 = GetProcessHeap();
                HeapFree(v429, 0, (LPVOID)v1331);
                *((_QWORD *)v1335 + 5) = 0;
              }
              v430 = GetProcessHeap();
              HeapFree(v430, 0, v1335);
              v431 = (unsigned int *)v1322;
            }
            else
            {
              v431 = (unsigned int *)v1322;
            }
            v358 = v423 | 0x10000000;
            if ( v358 < 0 )
              goto LABEL_586;
            v444 = *v431;
            *(_QWORD *)Size = 0x400000000LL;
            v445 = sub_180006270(4, v444, &Size[4]);
            if ( v445 < 0 )
              goto LABEL_637;
            v445 = sub_180006270(*(unsigned int *)&Size[4], 4, &Size[4]);
            if ( v445 < 0
              || (v447 = *(unsigned int *)(v446 + 16),
                  v1330 = v446 + 16,
                  v445 = sub_180006270(*(unsigned int *)&Size[4], v447, &Size[4]),
                  v445 < 0)
              || (v445 = sub_180006270(*(unsigned int *)&Size[4], 4, &Size[4]), v445 < 0)
              || (v449 = *(unsigned int *)(v448 + 32),
                  v1346 = v448 + 32,
                  v445 = sub_180006270(*(unsigned int *)&Size[4], v449, &Size[4]),
                  v445 < 0) )
            {
LABEL_637:
              v358 = v445 | 0x10000000;
              if ( v358 >= 0 )
              {
                v1360 = 8;
                v489 = sub_180006270(8, (unsigned int)v1328, &v1360);
                v358 = v489 | 0x10000000;
                if ( v489 >= 0 )
                {
                  v490 = (v1360 + 7) & 0xFFFFFFF8;
                  if ( (unsigned int)v490 < v1360 )
                  {
                    v358 = -1073741675;
                    goto LABEL_586;
                  }
                  v1366 = (v1360 + 7) & 0xFFFFFFF8;
                  v358 = sub_180006270(v490, 8, &v1366);
                  if ( v358 >= 0 )
                  {
                    LODWORD(v1338) = 0;
                    v494 = (LPVOID)v1350[1];
                    v1340 = v13;
                    jj = v299;
                    v1317 = v491;
                    v1318 = v493;
                    v1322 = v492;
                    if ( !v1350[1] )
                      goto LABEL_651;
                    v1322 = v492;
                    v1318 = v493;
                    v1317 = v491;
                    jj = v299;
                    v1340 = v13;
                    if ( LODWORD(v1350[0]) <= 1 )
                      goto LABEL_651;
                    v1316 = (LPVOID)v1350[1];
                    for ( i4 = 0; ; i4 = v1315 + 1 )
                    {
                      LODWORD(v1315) = i4;
                      if ( i4 )
                        break;
                      v358 = sub_180006240(v494, 4, &v1316);
                      if ( v358 < 0 )
                        goto LABEL_586;
                      v358 = sub_180006240(v1316, v496, &v1316);
                      if ( v358 < 0 )
                        goto LABEL_586;
                      v494 = v1316;
                    }
                    v358 = sub_180006240(v494, 4, &v1316);
                    if ( v358 < 0 )
                      goto LABEL_586;
                    v497 = (LPVOID)v1350[1];
                    if ( !v1350[1] || LODWORD(v1350[0]) <= 2 )
                    {
LABEL_651:
                      v358 = -1073741811;
                      goto LABEL_586;
                    }
                    v1316 = (LPVOID)v1350[1];
                    for ( i5 = 0; i5 < 2; i5 = v503 + 1 )
                    {
                      v358 = sub_180006240(v497, 4, &v1316);
                      if ( v358 < 0 )
                        goto LABEL_586;
                      v358 = sub_180006240(v1316, v502, &v1316);
                      if ( v358 < 0 )
                        goto LABEL_586;
                      v497 = v1316;
                    }
                    v358 = sub_180006240(v497, 4, &v1316);
                    if ( v358 >= 0 )
                    {
                      *(_DWORD *)&Size[4] = 4;
                      LODWORD(v1338) = 0;
                      v358 = sub_180006270(4, v1366, &Size[4]);
                      if ( v358 >= 0 )
                      {
                        v358 = sub_180006270(*(unsigned int *)&Size[4], 4, &Size[4]);
                        if ( v358 >= 0 )
                        {
                          v358 = sub_180006270(*(unsigned int *)&Size[4], v504, &Size[4]);
                          if ( v358 >= 0 )
                          {
                            v358 = sub_180006270(*(unsigned int *)&Size[4], 4, &Size[4]);
                            if ( v358 >= 0 )
                            {
                              v358 = sub_180006270(*(unsigned int *)&Size[4], v505, &Size[4]);
                              if ( v358 >= 0 )
                              {
                                LODWORD(v1338) = *(_DWORD *)&Size[4];
                                if ( *(_DWORD *)&Size[4] > 0x400000u )
                                {
                                  v358 = -2147418113;
                                  goto LABEL_586;
                                }
                                v498 = *(_DWORD *)&Size[4];
                                v499 = GetProcessHeap();
                                v1325 = HeapAlloc(v499, 8u, v498);
                                v500 = v1325;
                                if ( !v1325 )
                                {
                                  v358 = -805306345;
                                  v1325 = 0;
                                  goto LABEL_586;
                                }
                                hModule = 0;
                                v1375 = 0;
                                v1376 = 0;
                                if ( !v1341 )
                                {
                                  v358 = -2147024809;
LABEL_679:
                                  v1325 = v500;
                                  goto LABEL_586;
                                }
                                *(_QWORD *)&v1375 = v1341;
                                *(_QWORD *)((char *)&v1376 + 4) = (unsigned int)v1338;
                                LODWORD(v1376) = *(_DWORD *)Size;
                                *((_QWORD *)&v1375 + 1) = v1325;
                                if ( GetModuleHandleExW(1u, L"ntdll.dll", &hModule)
                                  && (ProcAddress = (NTSTATUS (__stdcall *)(SYSTEM_INFORMATION_CLASS, PVOID, ULONG, PULONG))GetProcAddress(hModule, "NtQuerySystemInformation")) != 0 )
                                {
                                  v508 = ((__int64 (__fastcall *)(__int64, __int128 *))ProcAddress)(134, &v1375);
                                  v358 = v508 | 0x10000000;
                                  if ( v508 >= 0 )
                                  {
                                    v509 = DWORD1(v1376);
                                    goto LABEL_687;
                                  }
                                }
                                else
                                {
                                  v506 = GetLastError();
                                  v358 = v506;
                                  if ( v506 > 0 )
                                    v358 = (unsigned __int16)v506 | 0x80070000;
                                  if ( v358 >= 0 )
                                  {
                                    v358 = -2147467259;
                                    goto LABEL_678;
                                  }
                                }
                                if ( v358 == -805306333 )
                                {
                                  v358 = -2147024774;
                                  goto LABEL_586;
                                }
                                if ( v358 >= 0 )
                                {
                                  v509 = v1338;
LABEL_687:
                                  v500 = v1325;
                                  v1335 = v1325;
                                  LODWORD(v1327) = 0;
                                  if ( v509 < 4 )
                                  {
LABEL_688:
                                    v358 = -805306306;
                                    goto LABEL_679;
                                  }
                                  *(_DWORD *)Size = *(_DWORD *)v1325;
                                  v510 = sub_180006240(v1325, 4, &v1335);
                                  if ( v510 >= 0 )
                                  {
                                    v510 = sub_180006270(0, 4, &v1327);
                                    if ( v510 < 0 )
                                    {
LABEL_741:
                                      v1325 = v500;
                                      goto LABEL_742;
                                    }
                                    if ( v512 - (int)v1327 < (unsigned int)v513 )
                                      goto LABEL_688;
                                    v1330 = (SIZE_T)v1335;
                                    v1331 = v513;
                                    v510 = sub_180006240(v1335, (unsigned int)v513, &v1335);
                                    if ( v510 >= 0 )
                                    {
                                      v510 = sub_180006270((unsigned int)v1327, v514, &v1327);
                                      if ( v510 >= 0 )
                                      {
                                        if ( (unsigned int)(v515 - v1327) < 4 )
                                          goto LABEL_688;
                                        LODWORD(v1315) = *(_DWORD *)v1335;
                                        v510 = sub_180006240(v1335, 4, &v1335);
                                        if ( v510 >= 0 )
                                        {
                                          v510 = sub_180006270((unsigned int)v1327, 4, &v1327);
                                          if ( v510 >= 0 )
                                          {
                                            if ( v516 - (int)v1327 < (unsigned int)v517 )
                                              goto LABEL_688;
                                            dwBytes = (SIZE_T)v1335;
                                            v1346 = v517;
                                            v510 = sub_180006240(v1335, (unsigned int)v517, &v1335);
                                            if ( v510 >= 0 )
                                            {
                                              v510 = sub_180006270((unsigned int)v1327, v518, &v1327);
                                              if ( v510 >= 0 )
                                              {
                                                if ( (unsigned int)(v519 - v1327) < 4 )
                                                  goto LABEL_688;
                                                LODWORD(v1338) = *(_DWORD *)v1335;
                                                v510 = sub_180006240(v1335, 4, &v1335);
                                                if ( v510 >= 0 )
                                                {
                                                  v510 = sub_180006270((unsigned int)v1327, 4, &v1327);
                                                  if ( v510 >= 0 )
                                                  {
                                                    if ( v520 - (int)v1327 < v521 )
                                                      goto LABEL_688;
                                                    v510 = sub_180006270((unsigned int)v1327, v521, &v1327);
                                                    if ( v510 >= 0 )
                                                    {
                                                      if ( v522 != (_DWORD)v1327 )
                                                        goto LABEL_688;
                                                      v524 = *(unsigned int *)Size;
                                                      if ( (unsigned int)(v523 + *(_DWORD *)Size + v1315) + 12LL != v522 )
                                                        goto LABEL_688;
                                                      v525 = GetProcessHeap();
                                                      v1316 = HeapAlloc(v525, 8u, 0x30u);
                                                      v526 = v1316;
                                                      if ( !v1316 )
                                                      {
                                                        v1319 = 0;
                                                        goto LABEL_585;
                                                      }
                                                      v1340 = v13;
                                                      jj = v299;
                                                      v1342 = 0;
                                                      if ( v1330 )
                                                      {
                                                        *(_DWORD *)v1316 = v524;
                                                        v527 = GetProcessHeap();
                                                        v528 = HeapAlloc(v527, 8u, v524);
                                                        if ( !v528 )
                                                        {
LABEL_720:
                                                          v535 = v1316;
                                                          v510 = -1073741801;
                                                          v1331 = *((_QWORD *)v1316 + 1);
                                                          if ( v1331 )
                                                          {
                                                            v536 = GetProcessHeap();
                                                            HeapFree(v536, 0, (LPVOID)v1331);
                                                            v535 = v1316;
                                                            *((_QWORD *)v1316 + 1) = 0;
                                                          }
                                                          v1331 = v535[3];
                                                          if ( v1331 )
                                                          {
                                                            v537 = GetProcessHeap();
                                                            HeapFree(v537, 0, (LPVOID)v1331);
                                                            v535 = v1316;
                                                            *((_QWORD *)v1316 + 3) = 0;
                                                          }
                                                          v1331 = v535[5];
                                                          if ( v1331 )
                                                          {
                                                            v538 = GetProcessHeap();
                                                            HeapFree(v538, 0, (LPVOID)v1331);
                                                            *((_QWORD *)v1316 + 5) = 0;
                                                          }
                                                          v539 = GetProcessHeap();
                                                          HeapFree(v539, 0, v1316);
                                                          v540 = (size_t *)v1342;
                                                          goto LABEL_730;
                                                        }
                                                        *((_QWORD *)v1316 + 1) = v528;
                                                        v510 = 0;
                                                        memcpy(v528, (const void *)v1330, v1331);
                                                        v526 = v1316;
                                                      }
                                                      else
                                                      {
                                                        *(_DWORD *)v1316 = 0;
                                                        v510 = 0;
                                                        v526[1] = 0;
                                                      }
                                                      if ( dwBytes )
                                                      {
                                                        *((_DWORD *)v526 + 4) = v1315;
                                                        v529 = GetProcessHeap();
                                                        v530 = HeapAlloc(v529, 8u, v1346);
                                                        if ( !v530 )
                                                        {
LABEL_719:
                                                          v1340 = v13;
                                                          jj = v299;
                                                          goto LABEL_720;
                                                        }
                                                        *((_QWORD *)v1316 + 3) = v530;
                                                        v510 = 0;
                                                        memcpy(v530, (const void *)dwBytes, v1346);
                                                        v526 = v1316;
                                                      }
                                                      else
                                                      {
                                                        *((_DWORD *)v526 + 4) = 0;
                                                        v526[3] = 0;
                                                      }
                                                      if ( v1335 )
                                                      {
                                                        v531 = (unsigned int)v1338;
                                                        *((_DWORD *)v526 + 8) = v1338;
                                                        v532 = v531;
                                                        v1331 = v531;
                                                        v533 = GetProcessHeap();
                                                        v534 = HeapAlloc(v533, 8u, v532);
                                                        if ( !v534 )
                                                          goto LABEL_719;
                                                        *((_QWORD *)v1316 + 5) = v534;
                                                        v510 = 0;
                                                        memcpy(v534, v1335, v1331);
                                                        v526 = v1316;
                                                      }
                                                      else
                                                      {
                                                        *((_DWORD *)v526 + 8) = 0;
                                                        v526[5] = 0;
                                                      }
                                                      v540 = v526;
                                                      v1342 = v526;
                                                      jj = v299;
                                                      v1340 = v13;
LABEL_730:
                                                      if ( v510 < 0 )
                                                      {
                                                        v511 = 0;
                                                        v1319 = 0;
                                                        if ( v540 )
                                                        {
                                                          v1331 = v540[1];
                                                          if ( v1331 )
                                                          {
                                                            v541 = GetProcessHeap();
                                                            HeapFree(v541, 0, (LPVOID)v1331);
                                                            v540 = (size_t *)v1342;
                                                            *((_QWORD *)v1342 + 1) = 0;
                                                          }
                                                          v1331 = v540[3];
                                                          if ( v1331 )
                                                          {
                                                            v542 = GetProcessHeap();
                                                            HeapFree(v542, 0, (LPVOID)v1331);
                                                            v540 = (size_t *)v1342;
                                                            *((_QWORD *)v1342 + 3) = 0;
                                                          }
                                                          v1331 = v540[5];
                                                          if ( v1331 )
                                                          {
                                                            v543 = GetProcessHeap();
                                                            HeapFree(v543, 0, (LPVOID)v1331);
                                                            *((_QWORD *)v1342 + 5) = 0;
                                                          }
                                                          v544 = GetProcessHeap();
                                                          HeapFree(v544, 0, v1342);
                                                          v511 = 0;
                                                          v1319 = 0;
                                                        }
                                                      }
                                                      else
                                                      {
                                                        v511 = (unsigned int *)v540;
                                                        v1319 = v540;
                                                      }
LABEL_742:
                                                      v358 = v510 | 0x10000000;
                                                      if ( v358 < 0 )
                                                        goto LABEL_586;
                                                      if ( !v511 || (v1346 = *((_QWORD *)v511 + 1)) == 0 || !*v511 )
                                                      {
                                                        v358 = -805306355;
                                                        goto LABEL_586;
                                                      }
                                                      v545 = *v511 - 8LL;
                                                      v1335 = (LPVOID)v545;
                                                      v1333 = (LPVOID)sub_1800010C0(v545);
                                                      if ( !v1333 )
                                                        goto LABEL_774;
                                                      v546 = 0;
                                                      dwBytes = v1346;
                                                      uBytes_4 = 0;
                                                      v1316 = (LPVOID)0x7F1137FAB69605ELL;
                                                      v1330 = v545 & 7;
                                                      v1348 = (SIZE_T)v1333;
                                                      if ( (v545 & 7) != 0 )
                                                      {
                                                        LODWORD(v1338) = 0;
                                                        LODWORD(v1328) = 0;
                                                        LODWORD(v1315) = 0;
                                                        v547 = 0;
                                                        v548 = 0;
                                                        v549 = 0;
                                                        v550 = (unsigned __int8 *)dwBytes;
                                                        do
                                                        {
                                                          v551 = *v550++;
                                                          *(_DWORD *)&Size[4] = v551;
                                                          LODWORD(v1315) = 8 * v547;
                                                          if ( (unsigned int)v547 >= 4 )
                                                          {
                                                            *(_DWORD *)&Size[4] <<= 56 - v1315;
                                                            v548 |= *(_DWORD *)&Size[4];
                                                          }
                                                          else
                                                          {
                                                            *(_DWORD *)&Size[4] <<= 24 - v1315;
                                                            v549 |= *(_DWORD *)&Size[4];
                                                          }
                                                          ++v547;
                                                        }
                                                        while ( v547 < (int)v1330 );
                                                        LODWORD(v1328) = v549;
                                                        v545 = (unsigned __int64)v1335;
                                                        LODWORD(v1338) = v548;
                                                        v546 = uBytes_4;
                                                        dwBytes = (SIZE_T)v550;
                                                        v552 = (_BYTE *)v1348;
                                                        v553 = v1330;
                                                        jj = v299;
                                                        v1340 = v13;
                                                        v554 = (unsigned int)v1328 ^ 0x92F65A5;
                                                        LODWORD(v1315) = 0;
                                                        v555 = v1338 ^ 0x699A899C;
                                                        v556 = (unsigned int)v1328 ^ 0x92F65A5;
                                                        v557 = v1338 ^ 0x699A899C;
                                                        if ( (_DWORD)v1330 )
                                                        {
                                                          v558 = v1315;
                                                          do
                                                          {
                                                            v1331 = (size_t)(v552 + 1);
                                                            if ( v558 >= 4 )
                                                            {
                                                              v557 = __ROR4__(v557, 24);
                                                              v559 = v557;
                                                            }
                                                            else
                                                            {
                                                              v556 = __ROR4__(v556, 24);
                                                              v559 = v556;
                                                            }
                                                            *v552 = v559;
                                                            ++v558;
                                                            v552 = (_BYTE *)v1331;
                                                          }
                                                          while ( (int)v558 < (int)v553 );
                                                          v1348 = v1331;
                                                        }
                                                        if ( v553 <= 4 )
                                                        {
                                                          v560 = 0;
                                                          if ( v553 < 4 )
                                                            v554 = (unsigned int)v554 >> (8 * (4 - v553)) << (8 * (4 - v553));
                                                        }
                                                        else
                                                        {
                                                          v560 = v555 >> (8 * (8 - v553)) << (8 * (8 - v553));
                                                        }
                                                      }
                                                      else
                                                      {
                                                        v560 = 0;
                                                        LODWORD(v1328) = 0;
                                                        v554 = 0;
                                                        LODWORD(v1338) = -1;
                                                      }
                                                      if ( v545 >> 3 )
                                                      {
                                                        v561 = HIDWORD(v1316);
                                                        v562 = v545 >> 3;
                                                        v563 = (unsigned __int8 *)dwBytes;
                                                        v564 = (_BYTE *)v1348;
                                                        v565 = (int)v1328;
                                                        v566 = WORD2(v1316);
                                                        *(_DWORD *)&Size[4] = 24670;
                                                        v567 = v1338;
                                                        LODWORD(v1327) = WORD2(v1316);
                                                        v1330 = 0;
                                                        do
                                                        {
                                                          v568 = *v563;
                                                          v569 = v563[1];
                                                          v570 = v563[4];
                                                          v563 += 8;
                                                          v571 = *(v563 - 5)
                                                               | ((*(v563 - 6) | (((v568 << 8) | v569) << 8)) << 8);
                                                          v572 = v554 ^ v571;
                                                          v573 = *(v563 - 1)
                                                               | ((*(v563 - 2) | ((*(v563 - 3) | (v570 << 8)) << 8)) << 8);
                                                          v574 = v561 ^ v554 ^ v571 ^ v560 ^ v573 ^ 0xAB69605E;
                                                          v575 = v572
                                                               ^ (__ROR4__(v574, 22)
                                                                + v566 * __ROR4__(v574 + 1419157410, 27));
                                                          v576 = v574
                                                               ^ (WORD1(v1316) * __ROR4__(v561 + v575, 9)
                                                                - __ROR4__(v575, 30));
                                                          v577 = v575
                                                               ^ (*(_DWORD *)&Size[4] * (v576 - v566) - (v576 >> 13));
                                                          v578 = v576
                                                               ^ (HIWORD(v1316) * __ROR4__(v577 ^ WORD1(v1316), 26)
                                                                - __ROR4__(v577, 30));
                                                          v579 = v577 ^ (v561 - (v578 ^ 0xAB69605E));
                                                          v580 = v578
                                                               ^ (WORD1(v1316) * (v579 ^ v566))
                                                               ^ __ROR4__(v579, 6);
                                                          v581 = v579
                                                               ^ (__ROR4__(v580, 30)
                                                                + *(_DWORD *)&Size[4] * __ROR4__(v580 + v561, 15));
                                                          v582 = v580
                                                               ^ (HIWORD(v1316) * __ROR4__(v581 + 1419157410, 14)
                                                                - __ROR4__(v581, 24));
                                                          v583 = v581
                                                               ^ __ROR4__(v582, 10)
                                                               ^ (v1327 * __ROR4__(v582 ^ 0xAB69605E, 12));
                                                          v584 = v583
                                                               ^ (HIWORD(v1316)
                                                                * (*(_DWORD *)&Size[4]
                                                                 + __ROR4__(
                                                                     ~(v582
                                                                     ^ (v583 >> 10)
                                                                     ^ (WORD1(v1316) * (HIWORD(v1316) ^ v583))),
                                                                     5)));
                                                          v585 = v582
                                                               ^ (v583 >> 10)
                                                               ^ (WORD1(v1316) * (HIWORD(v1316) ^ v583))
                                                               ^ (v584 - HIWORD(v1316))
                                                               ^ 0xAB69605E;
                                                          v586 = v584
                                                               ^ ((v585 >> 2)
                                                                + v1327 * __ROR4__(HIWORD(v1316) ^ v585, 30));
                                                          v587 = v585
                                                               ^ (__ROR4__(v586, 25)
                                                                + WORD1(v1316) * __ROR4__(v586 - HIDWORD(v1316), 6));
                                                          v588 = v586
                                                               ^ (*(_DWORD *)&Size[4] * (v1327 ^ v587)
                                                                + __ROR4__(v587, 9));
                                                          v589 = v587
                                                               ^ (__ROR4__(v588, 25)
                                                                + HIWORD(v1316) * __ROR4__(WORD1(v1316) ^ v588, 27));
                                                          v561 = HIDWORD(v1316);
                                                          v590 = HIDWORD(v1316) ^ v588 ^ v589 ^ 0xAB69605E;
                                                          v591 = v589 ^ (v1327 * (__ROR4__(v590, 3) - WORD1(v1316)));
                                                          v592 = v590
                                                               ^ (*(_DWORD *)&Size[4]
                                                                * __ROR4__(v591 - HIDWORD(v1316), 1)
                                                                - __ROR4__(v591, 6));
                                                          v593 = v591
                                                               ^ (__ROR4__(v592, 18)
                                                                + HIWORD(v1316) * __ROR4__(v592 - 1419157410, 29));
                                                          v594 = v592
                                                               ^ (v1327 * __ROR4__(v593 - 1419157410, 17)
                                                                - __ROR4__(v593, 14));
                                                          v566 = v1327;
                                                          v595 = v593
                                                               ^ (v594 >> 3)
                                                               ^ (WORD1(v1316) * (*(_DWORD *)&Size[4] ^ v594));
                                                          v560 = v567 ^ (unsigned int)v595;
                                                          v567 = v573;
                                                          v596 = v565
                                                               ^ __ROR4__(v595, 30)
                                                               ^ (*(_DWORD *)&Size[4]
                                                                * __ROR4__(HIDWORD(v1316) ^ v595, 28));
                                                          v565 = v571;
                                                          v554 = v594 ^ v596;
                                                          v564[3] = v554;
                                                          v564[7] = v560;
                                                          v564[2] = __ROR4__(v554, 8);
                                                          v564[6] = __ROR4__(v560, 8);
                                                          v564[1] = __ROR4__(v554, 16);
                                                          v564[5] = __ROR4__(v560, 16);
                                                          *v564 = __ROR4__(v554, 24);
                                                          v564[4] = __ROR4__(v560, 24);
                                                          v564 += 8;
                                                          ++v1330;
                                                        }
                                                        while ( v1330 < v562 );
                                                        v546 = uBytes_4;
                                                        v13 = v1340;
                                                        v10 = -805306219;
                                                        v299 = jj;
                                                        v8 = 4;
                                                        v545 = (unsigned __int64)v1335;
                                                      }
                                                      for ( i6 = 0; i6 < v545; ++i6 )
                                                        v546 ^= *((_BYTE *)v1333 + i6);
                                                      if ( v546 != *(_QWORD *)(v545 + v1346) )
                                                      {
                                                        sub_180010DC8(v1333, v1333, v554, v560);
LABEL_774:
                                                        v1333 = 0;
                                                        v358 = -805306367;
                                                        goto LABEL_586;
                                                      }
                                                      *(_DWORD *)&Size[4] = 0;
                                                      v1316 = v1333;
                                                      if ( (unsigned int)v545 < 4 )
                                                        goto LABEL_776;
                                                      v598 = sub_180006240(v1333, 4, &v1316);
                                                      if ( v598 >= 0 )
                                                      {
                                                        v598 = sub_180006270(0, 4, &Size[4]);
                                                        if ( v598 >= 0 )
                                                        {
                                                          if ( (unsigned int)((_DWORD)v1335 - *(_DWORD *)&Size[4]) < 4 )
                                                            goto LABEL_780;
                                                          LODWORD(v1327) = *(_DWORD *)v1316;
                                                          v598 = sub_180006240(v1316, 4, &v1316);
                                                          if ( v598 < 0 )
                                                            goto LABEL_812;
                                                          v598 = sub_180006270(*(unsigned int *)&Size[4], 4, &Size[4]);
                                                          if ( v598 < 0 )
                                                            goto LABEL_812;
                                                          if ( (int)v1335 - *(_DWORD *)&Size[4] < (unsigned int)v1327 )
                                                          {
LABEL_780:
                                                            v602 = v1333;
                                                          }
                                                          else
                                                          {
                                                            v598 = sub_180006270(
                                                                     *(unsigned int *)&Size[4],
                                                                     (unsigned int)v1327,
                                                                     &Size[4]);
                                                            if ( v598 < 0 )
                                                              goto LABEL_812;
                                                            v602 = v1333;
                                                            v598 = (int)v1316;
                                                            if ( (char *)v1333 + (unsigned int)v1335 >= (char *)v1316 + (unsigned int)v1327
                                                              && (unsigned __int64)v1333
                                                               + (unsigned int)v1335
                                                               - (unsigned __int64)(unsigned int)v1327
                                                               - (_QWORD)v1316 < 8 )
                                                            {
                                                              LODWORD(v1338) = *(_DWORD *)v1333;
                                                              v1330 = 0;
                                                              v1346 = 0;
                                                              dwBytes = 0;
                                                              *(_DWORD *)Size = 0;
                                                              if ( v1316 )
                                                              {
                                                                v1331 = (size_t)v1316;
                                                                v603 = sub_180006240(v1316, (unsigned int)v1327, &v1330);
                                                                v1325 = v604;
                                                                v598 = v603;
                                                                v1322 = v605;
                                                                v1317 = v606;
                                                                if ( v603 >= 0 )
                                                                {
                                                                  v607 = v1330;
                                                                  v608 = v1331;
                                                                  while ( v608 < v607 )
                                                                  {
                                                                    v598 = sub_180006240(v608, 4, &v1346);
                                                                    if ( v598 < 0 )
                                                                      goto LABEL_800;
                                                                    if ( v1346 > v610 )
                                                                      goto LABEL_799;
                                                                    v611 = *v609;
                                                                    LODWORD(v1315) = 0;
                                                                    v598 = sub_180006270(4, v611, &v1315);
                                                                    if ( v598 < 0 )
                                                                      goto LABEL_813;
                                                                    v598 = sub_180006240(
                                                                             v612,
                                                                             (unsigned int)v1315,
                                                                             &dwBytes);
                                                                    if ( v598 < 0 )
                                                                      goto LABEL_800;
                                                                    v608 = dwBytes;
                                                                    if ( dwBytes > v607 )
                                                                      goto LABEL_799;
                                                                    ++*(_DWORD *)Size;
                                                                  }
                                                                  if ( v608 == v607 )
                                                                    goto LABEL_805;
LABEL_799:
                                                                  v598 = -1073741811;
                                                                  goto LABEL_813;
                                                                }
LABEL_800:
                                                                v613 = v1334;
                                                              }
                                                              else
                                                              {
                                                                v1325 = v600;
                                                                v1322 = v601;
                                                                v1317 = v599;
LABEL_805:
                                                                v614 = (unsigned int)v1327;
                                                                v615 = 0;
                                                                v1330 = 0;
                                                                if ( (_DWORD)v1327 )
                                                                {
                                                                  v616 = GetProcessHeap();
                                                                  v1330 = (SIZE_T)HeapAlloc(
                                                                                    v616,
                                                                                    8u,
                                                                                    (unsigned int)v1327);
                                                                  v615 = (void *)v1330;
                                                                  if ( !v1330 )
                                                                  {
                                                                    v598 = -1073741801;
                                                                    goto LABEL_813;
                                                                  }
                                                                  v614 = (unsigned int)v1327;
                                                                  v598 = 0;
                                                                }
                                                                if ( v1316 )
                                                                  memcpy(v615, v1316, v614);
                                                                v1336 = (LPVOID)v1330;
                                                                v613 = *(_DWORD *)Size;
                                                                LODWORD(v1334) = *(_DWORD *)Size;
                                                              }
                                                              if ( v598 < 0 || (_DWORD)v1338 == v613 )
                                                                goto LABEL_813;
LABEL_776:
                                                              v598 = -1073741762;
LABEL_813:
                                                              v358 = v598 | 0x10000000;
                                                              goto LABEL_586;
                                                            }
                                                          }
                                                          v598 = -1073741762;
                                                          v1333 = v602;
                                                        }
                                                      }
LABEL_812:
                                                      v1317 = v599;
                                                      v1322 = v601;
                                                      v1325 = v600;
                                                      goto LABEL_813;
                                                    }
                                                  }
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                  v511 = (unsigned int *)v1319;
                                  goto LABEL_741;
                                }
LABEL_678:
                                v500 = v1325;
                                goto LABEL_679;
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
LABEL_586:
              if ( !v1318 )
              {
LABEL_588:
                v455 = v1322;
                if ( v1322 )
                {
                  v1331 = *((_QWORD *)v1322 + 1);
                  if ( v1331 )
                  {
                    v456 = GetProcessHeap();
                    HeapFree(v456, 0, (LPVOID)v1331);
                    v455 = v1322;
                    *((_QWORD *)v1322 + 1) = 0;
                  }
                  v1331 = v455[3];
                  if ( v1331 )
                  {
                    v457 = GetProcessHeap();
                    HeapFree(v457, 0, (LPVOID)v1331);
                    v455 = v1322;
                    *((_QWORD *)v1322 + 3) = 0;
                  }
                  v1331 = v455[5];
                  if ( v1331 )
                  {
                    v458 = GetProcessHeap();
                    HeapFree(v458, 0, (LPVOID)v1331);
                    *((_QWORD *)v1322 + 5) = 0;
                  }
                  v459 = GetProcessHeap();
                  HeapFree(v459, 0, v1322);
                }
                if ( v1341 )
                {
                  v460 = GetProcessHeap();
                  HeapFree(v460, 0, (LPVOID)v1341);
                }
                if ( v1325 )
                {
                  v461 = GetProcessHeap();
                  HeapFree(v461, 0, v1325);
                }
                v462 = v1319;
                if ( v1319 )
                {
                  v1331 = *((_QWORD *)v1319 + 1);
                  if ( v1331 )
                  {
                    v463 = GetProcessHeap();
                    HeapFree(v463, 0, (LPVOID)v1331);
                    v462 = v1319;
                    *((_QWORD *)v1319 + 1) = 0;
                  }
                  v1331 = v462[3];
                  if ( v1331 )
                  {
                    v464 = GetProcessHeap();
                    HeapFree(v464, 0, (LPVOID)v1331);
                    v462 = v1319;
                    *((_QWORD *)v1319 + 3) = 0;
                  }
                  v1331 = v462[5];
                  if ( v1331 )
                  {
                    v465 = GetProcessHeap();
                    HeapFree(v465, 0, (LPVOID)v1331);
                    *((_QWORD *)v1319 + 5) = 0;
                  }
                  v466 = GetProcessHeap();
                  HeapFree(v466, 0, v1319);
                }
                if ( v1333 )
                {
                  v467 = GetProcessHeap();
                  HeapFree(v467, 0, v1333);
                }
LABEL_610:
                if ( v358 >= 0 && (_DWORD)v1334 && v1336 )
                {
                  v1330 = (SIZE_T)v1336;
                  v468 = sub_180006240(v1336, 4, &v1330);
                  v296 = v1317;
                  v1336 = v469;
                  if ( v468 >= 0 )
                  {
                    v471 = (int *)v1330;
                    if ( !*v469 )
                      v471 = 0;
                    if ( *v469 == 4 )
                    {
                      if ( *v471 < 0 )
                      {
                        v1336 = v469;
                      }
                      else if ( v470 <= 1 )
                      {
                        v1336 = v469;
                      }
                      else
                      {
                        v472 = v469;
                        v473 = 0;
                        v1316 = v469;
                        while ( !v473 )
                        {
                          if ( (int)sub_180006240(v472, 4, &v1316) < 0 || (int)sub_180006240(v1316, v474, &v1316) < 0 )
                            goto LABEL_467;
                          v472 = v1316;
                          v473 = v475 + 1;
                        }
                        sub_180006240(v472, 4, &v1316);
                      }
                    }
                  }
                  goto LABEL_467;
                }
                goto LABEL_466;
              }
LABEL_587:
              v454 = GetProcessHeap();
              HeapFree(v454, 0, v1318);
              goto LABEL_588;
            }
            v451 = *(_DWORD *)&Size[4];
            v1322 = v450;
            v452 = GetProcessHeap();
            jj = HeapAlloc(v452, 8u, v451);
            v453 = jj;
            if ( !jj )
            {
LABEL_585:
              v358 = -805306345;
              goto LABEL_586;
            }
            v476 = v1317;
            v477 = v1318;
            *(_DWORD *)jj = *(_DWORD *)v1322;
            v1317 = v476;
            v1318 = v477;
            v1316 = v453;
            v445 = sub_180006240(v453, 4, &v1316);
            if ( v445 < 0 )
            {
              v1322 = v480;
              v1318 = v481;
              v1317 = v479;
              jj = v478;
            }
            else
            {
              memcpy(v1316, v480[1], *(unsigned int *)v480);
              v445 = sub_180006240(v1316, *(unsigned int *)v1322, &v1316);
              if ( v445 < 0
                || (v483 = v1316, *(_DWORD *)v1316 = *(_DWORD *)v1330, v445 = sub_180006240(v483, 4, &v1316), v445 < 0) )
              {
                v1322 = v482;
              }
              else
              {
                memcpy(v1316, v482[3], *v484);
                v445 = sub_180006240(v1316, *(unsigned int *)v1330, &v1316);
                if ( v445 < 0 )
                {
                  v487 = v1322;
                }
                else
                {
                  v485 = v1316;
                  *(_DWORD *)v1316 = *(_DWORD *)v1346;
                  v445 = sub_180006240(v485, 4, &v1316);
                  v487 = v1322;
                  if ( v445 >= 0 )
                  {
                    memcpy(v1316, *((const void **)v1322 + 5), *v486);
                    v445 = sub_180006240(v1316, *(unsigned int *)v1346, &v1316);
                    if ( v445 >= 0 )
                    {
                      v1341 = (SIZE_T)jj;
                      *(_DWORD *)Size = *(_DWORD *)&Size[4];
                      goto LABEL_637;
                    }
                    goto LABEL_636;
                  }
                }
                v1322 = v487;
              }
            }
LABEL_636:
            v488 = GetProcessHeap();
            HeapFree(v488, 0, jj);
            goto LABEL_637;
          }
        }
        else
        {
          v1316 = v434;
        }
      }
      v423 = -1073741801;
      v439 = v1316;
      v1331 = *((_QWORD *)v1316 + 1);
      if ( v1331 )
      {
        v440 = GetProcessHeap();
        HeapFree(v440, 0, (LPVOID)v1331);
        v439 = v1316;
        *((_QWORD *)v1316 + 1) = 0;
      }
      v1331 = v439[3];
      if ( v1331 )
      {
        v441 = GetProcessHeap();
        HeapFree(v441, 0, (LPVOID)v1331);
        v439 = v1316;
        *((_QWORD *)v1316 + 3) = 0;
      }
      v1331 = v439[5];
      if ( v1331 )
      {
        v442 = GetProcessHeap();
        HeapFree(v442, 0, (LPVOID)v1331);
        *((_QWORD *)v1316 + 5) = 0;
      }
      v443 = GetProcessHeap();
      HeapFree(v443, 0, v1316);
    }
    else
    {
      v423 = -1073741801;
    }
    v424 = v1322;
    goto LABEL_557;
  }
LABEL_467:
  v1350[0] = 0;
  v1331 = v1350[1];
  if ( v1350[1] )
  {
    v319 = GetProcessHeap();
    HeapFree(v319, 0, (LPVOID)v1331);
    v1350[1] = 0;
  }
  if ( v1336 )
  {
    v320 = GetProcessHeap();
    HeapFree(v320, 0, v1336);
  }
  if ( v299 )
  {
    v321 = GetProcessHeap();
    HeapFree(v321, 0, v299);
  }
  if ( v296 )
  {
    v322 = GetProcessHeap();
    HeapFree(v322, 0, v296);
  }
LABEL_475:
  v323 = LocalAlloc(0x40u, uBytes);
  sub_180006290(&v1359, v323);
  v1352 = v1359;
  if ( !v1359 )
  {
    v10 = -2147024882;
    goto LABEL_8;
  }
  v1364 = 0;
  *(_OWORD *)v1344 = 0;
  v1358 = 0;
  v1336 = 0;
  v324 = GetProcessHeap();
  v325 = HeapAlloc(v324, 8u, 0xA0u);
  v326 = v325;
  if ( !v325 )
  {
    v10 = -1073741801;
    v327 = 0;
    v1320 = -1073741801;
    goto LABEL_850;
  }
  *v325 = xmmword_180024150;
  v325[1] = xmmword_180024160;
  v325[2] = xmmword_180024170;
  v325[3] = xmmword_180024180;
  v325[4] = xmmword_180024190;
  v325[5] = xmmword_1800241A0;
  v325[6] = xmmword_1800241B0;
  v325[7] = xmmword_1800241C0;
  v325[8] = xmmword_1800241D0;
  v325[9] = xmmword_1800241E0;
  v617 = GetProcessHeap();
  v618 = HeapAlloc(v617, 8u, 8u);
  v1318 = v618;
  v327 = v618;
  if ( !v618 )
  {
    v10 = -1073741801;
    v1320 = -1073741801;
    goto LABEL_850;
  }
  *v618 = qword_180024090;
  lpMem = (LPVOID)__rdtsc();
  LODWORD(v1315) = 0;
  v619 = sub_180006270(4, 4, &v1315);
  if ( v619 < 0 )
    goto LABEL_849;
  *(_DWORD *)Size = 0;
  v619 = sub_180006270(v620, 160, Size);
  if ( v619 < 0 )
    goto LABEL_849;
  *(_DWORD *)&Size[4] = 0;
  v621 = (int)v1315 + *(_DWORD *)Size < (unsigned int)v1315 ? -805306219 : 0x10000000;
  if ( (int)v1315 + *(_DWORD *)Size < (unsigned int)v1315 )
    goto LABEL_846;
  LODWORD(v1315) = 0;
  v619 = sub_180006270(4, 8, &v1315);
  if ( v619 < 0 )
    goto LABEL_849;
  v621 = v623 + (unsigned int)v1315 < v623 ? v622 + 0x10000000 : 0x10000000;
  if ( v623 + (unsigned int)v1315 < v623 )
    goto LABEL_846;
  LODWORD(v1315) = 0;
  v619 = sub_180006270(4, 8, &v1315);
  if ( v619 < 0 )
    goto LABEL_849;
  v621 = v625 + (unsigned int)v1315 < v625 ? v626 + 0x10000000 : 0x10000000;
  if ( v625 + (unsigned int)v1315 < v625 )
  {
LABEL_846:
    v1320 = v621;
    v10 = v621;
    goto LABEL_847;
  }
  v1330 = 0;
  if ( (int)sub_180001090(v1343, v624, &v1330) < 0 )
  {
    v10 = v627 - 87;
LABEL_1276:
    v1320 = v10;
    goto LABEL_850;
  }
  LODWORD(v1315) = 0;
  v619 = sub_180006270(4, (unsigned int)(2 * (v1330 + 1)), &v1315);
  if ( v619 < 0 )
  {
LABEL_849:
    v1320 = v619;
    v10 = v619;
    goto LABEL_850;
  }
  v621 = v629 + (unsigned int)v1315 < v629 ? v628 + 0x10000000 : 0x10000000;
  if ( v629 + (unsigned int)v1315 < v629 )
    goto LABEL_846;
  LODWORD(v1315) = 0;
  v619 = sub_180006270(4, 4, &v1315);
  if ( v619 < 0 )
    goto LABEL_849;
  v621 = v630 + (unsigned int)v1315 < v630 ? v631 + 0x10000000 : 0x10000000;
  if ( v630 + (unsigned int)v1315 < v630 )
    goto LABEL_846;
  LODWORD(v1315) = 0;
  v619 = sub_180006270(4, 4, &v1315);
  if ( v619 < 0 )
    goto LABEL_849;
  v634 = v633 + v1315;
  v635 = -1;
  if ( v633 + (unsigned int)v1315 >= v633 )
    v635 = v633 + v1315;
  v621 = v634 < v633 ? v632 + 0x10000000 : 0x10000000;
  if ( v634 < v633 )
    goto LABEL_846;
  HIDWORD(v1344[0]) = v635;
  v636 = v635;
  v637 = GetProcessHeap();
  v638 = HeapAlloc(v637, 8u, v636);
  if ( !v638 )
  {
    v10 = -1073741801;
LABEL_1262:
    v1320 = v10;
    goto LABEL_1263;
  }
  v1344[1] = (size_t)v638;
  v1331 = 0;
  LODWORD(v1344[0]) = 0;
  LODWORD(v1332) = 0;
  v327 = v1318;
  v1330 = (SIZE_T)v638;
  v621 = sub_180006240(v638, 4, &v1332);
  if ( v621 < 0 )
    goto LABEL_846;
  if ( (unsigned __int64)(v639 + 2) > v1344[1] + HIDWORD(v1344[0]) )
    goto LABEL_949;
  v641 = v1332;
  *v639 = 4;
  *v641 = 0;
  v642 = 0;
  v643 = ++LODWORD(v1344[0]);
  v1331 = 0;
  LODWORD(v1332) = 0;
  if ( v326 )
  {
    if ( !v640 )
      goto LABEL_845;
  }
  else if ( v640 )
  {
LABEL_845:
    v621 = -1073741811;
    goto LABEL_846;
  }
  v658 = (unsigned int *)v1344[1];
  if ( v1344[1] )
  {
    v1330 = v1344[1];
    while ( 1 )
    {
      *(_DWORD *)Size = v642;
      if ( v642 >= v643 )
        break;
      v659 = *v658;
      LODWORD(v1315) = 0;
      v621 = sub_180006270(4, v659, &v1315);
      if ( v621 < 0 )
        goto LABEL_846;
      v621 = sub_180006240(v660, (unsigned int)v1315, &v1330);
      if ( v621 < 0 )
        goto LABEL_846;
      v658 = (unsigned int *)v1330;
      v642 = *(_DWORD *)Size + 1;
    }
    v621 = sub_180006240(v658, 4, &v1332);
    if ( v621 < 0 )
      goto LABEL_846;
    if ( (unsigned __int64)v661 + v662 + 4 > v1344[1] + HIDWORD(v1344[0]) )
      goto LABEL_949;
    *v661 = v662;
    if ( v326 )
      memcpy(v1332, v326, v662);
  }
  else
  {
    LODWORD(v1315) = 0;
    v621 = sub_180006270(4, v640, &v1315);
    if ( v621 < 0 )
      goto LABEL_846;
    v621 = sub_180006270(HIDWORD(v1344[0]), (unsigned int)v1315, (char *)v1344 + 4);
    if ( v621 < 0 )
      goto LABEL_846;
  }
  v663 = 0;
  v664 = ++LODWORD(v1344[0]);
  v1331 = 0;
  LODWORD(v1332) = 0;
  if ( !v327 )
    goto LABEL_845;
  v665 = (unsigned int *)v1344[1];
  if ( v1344[1] )
  {
    v1330 = v1344[1];
    while ( 1 )
    {
      *(_DWORD *)Size = v663;
      if ( v663 >= v664 )
        break;
      v666 = *v665;
      LODWORD(v1315) = 0;
      v621 = sub_180006270(4, v666, &v1315);
      if ( v621 < 0 )
        goto LABEL_846;
      v621 = sub_180006240(v667, (unsigned int)v1315, &v1330);
      if ( v621 < 0 )
        goto LABEL_846;
      v665 = (unsigned int *)v1330;
      v663 = *(_DWORD *)Size + 1;
    }
    v621 = sub_180006240(v665, 4, &v1332);
    if ( v621 < 0 )
      goto LABEL_846;
    if ( (unsigned __int64)v668 + v669 + 4 > v1344[1] + HIDWORD(v1344[0]) )
      goto LABEL_949;
    *v668 = v669;
    memcpy(v1332, v327, (unsigned int)v669);
  }
  else
  {
    LODWORD(v1315) = 0;
    v621 = sub_180006270(4, 8, &v1315);
    if ( v621 < 0 )
      goto LABEL_846;
    v621 = sub_180006270(HIDWORD(v1344[0]), (unsigned int)v1315, (char *)v1344 + 4);
    if ( v621 < 0 )
      goto LABEL_846;
  }
  v670 = (unsigned int *)v1344[1];
  v671 = ++LODWORD(v1344[0]);
  v1331 = 0;
  LODWORD(v1332) = 0;
  if ( v1344[1] )
  {
    v1330 = v1344[1];
    for ( i7 = 0; i7 < v671; i7 = v676 + 1 )
    {
      v674 = *v670;
      LODWORD(v1315) = 0;
      v621 = sub_180006270(4, v674, &v1315);
      if ( v621 < 0 )
        goto LABEL_846;
      v621 = sub_180006240(v675, (unsigned int)v1315, &v1330);
      if ( v621 < 0 )
        goto LABEL_846;
      v670 = (unsigned int *)v1330;
    }
    v621 = sub_180006240(v670, 4, &v1332);
    if ( v621 < 0 )
      goto LABEL_846;
    if ( (unsigned __int64)(v677 + 3) > v1344[1] + HIDWORD(v1344[0]) )
      goto LABEL_949;
    v678 = v1332;
    v679 = lpMem;
    *v677 = 8;
    *v678 = v679;
  }
  else
  {
    LODWORD(v1315) = 0;
    v621 = sub_180006270(4, 8, &v1315);
    if ( v621 < 0 )
      goto LABEL_846;
    v621 = sub_180006270(HIDWORD(v1344[0]), (unsigned int)v1315, (char *)v1344 + 4);
    if ( v621 < 0 )
      goto LABEL_846;
  }
  ++LODWORD(v1344[0]);
  v1341 = 0;
  if ( (int)sub_180001090(v1343, v672, &v1341) < 0 )
  {
    v621 = -1073741762;
    goto LABEL_846;
  }
  v621 = sub_180006240(v1341, 1, &v1341);
  if ( v621 < 0 )
    goto LABEL_846;
  v681 = 0;
  v1331 = 0;
  LODWORD(v1332) = 0;
  if ( !(2 * (_DWORD)v1341) )
    goto LABEL_845;
  v682 = (unsigned int *)v1344[1];
  if ( v1344[1] )
  {
    v1330 = v1344[1];
    while ( 1 )
    {
      *(_DWORD *)Size = v681;
      if ( v681 >= v680 )
        break;
      v683 = *v682;
      LODWORD(v1315) = 0;
      v621 = sub_180006270(4, v683, &v1315);
      if ( v621 < 0 )
        goto LABEL_846;
      v621 = sub_180006240(v684, (unsigned int)v1315, &v1330);
      if ( v621 < 0 )
        goto LABEL_846;
      v682 = (unsigned int *)v1330;
      v681 = *(_DWORD *)Size + 1;
    }
    v621 = sub_180006240(v682, 4, &v1332);
    if ( v621 < 0 )
      goto LABEL_846;
    if ( (unsigned __int64)v685 + v686 + 4 > v1344[1] + HIDWORD(v1344[0]) )
      goto LABEL_949;
    v687 = (const void *)v1343;
    v688 = v1332;
    *v685 = v686;
    memcpy(v688, v687, (unsigned int)v686);
  }
  else
  {
    LODWORD(v1315) = 0;
    v621 = sub_180006270(4, (unsigned int)(2 * v1341), &v1315);
    if ( v621 < 0 )
      goto LABEL_846;
    v621 = sub_180006270(HIDWORD(v1344[0]), (unsigned int)v1315, (char *)v1344 + 4);
    if ( v621 < 0 )
      goto LABEL_846;
  }
  v689 = (unsigned int *)v1344[1];
  v690 = ++LODWORD(v1344[0]);
  v1331 = 0;
  LODWORD(v1332) = 0;
  if ( v1344[1] )
  {
    v1330 = v1344[1];
    for ( i8 = 0; i8 < v690; i8 = v694 + 1 )
    {
      v692 = *v689;
      LODWORD(v1315) = 0;
      v621 = sub_180006270(4, v692, &v1315);
      if ( v621 < 0 )
        goto LABEL_846;
      v621 = sub_180006240(v693, (unsigned int)v1315, &v1330);
      if ( v621 < 0 )
        goto LABEL_846;
      v689 = (unsigned int *)v1330;
    }
    v621 = sub_180006240(v689, 4, &v1332);
    if ( v621 < 0 )
      goto LABEL_846;
    if ( (unsigned __int64)(v695 + 2) > v1344[1] + HIDWORD(v1344[0]) )
      goto LABEL_949;
    v696 = v1332;
    *v695 = 4;
    *v696 = v13;
  }
  else
  {
    LODWORD(v1315) = 0;
    v621 = sub_180006270(4, 4, &v1315);
    if ( v621 < 0 )
      goto LABEL_846;
    v621 = sub_180006270(HIDWORD(v1344[0]), (unsigned int)v1315, (char *)v1344 + 4);
    if ( v621 < 0 )
      goto LABEL_846;
  }
  v697 = (unsigned int *)v1344[1];
  v698 = ++LODWORD(v1344[0]);
  v1331 = 0;
  LODWORD(v1332) = 0;
  if ( v1344[1] )
  {
    v1330 = v1344[1];
    for ( i9 = 0; i9 < v698; i9 = v702 + 1 )
    {
      v700 = *v697;
      LODWORD(v1315) = 0;
      v621 = sub_180006270(4, v700, &v1315);
      if ( v621 < 0 )
        goto LABEL_846;
      v621 = sub_180006240(v701, (unsigned int)v1315, &v1330);
      if ( v621 < 0 )
        goto LABEL_846;
      v697 = (unsigned int *)v1330;
    }
    v621 = sub_180006240(v697, 4, &v1332);
    if ( v621 < 0 )
      goto LABEL_846;
    if ( (unsigned __int64)(v703 + 2) <= v1344[1] + HIDWORD(v1344[0]) )
    {
      v704 = v1332;
      *v703 = 4;
      *v704 = uBytes;
      goto LABEL_951;
    }
LABEL_949:
    v621 = -1073741789;
    goto LABEL_846;
  }
  LODWORD(v1315) = 0;
  v621 = sub_180006270(4, 4, &v1315);
  if ( v621 < 0 )
    goto LABEL_846;
  v621 = sub_180006270(HIDWORD(v1344[0]), (unsigned int)v1315, (char *)v1344 + 4);
  if ( v621 < 0 )
    goto LABEL_846;
LABEL_951:
  ++LODWORD(v1344[0]);
  LODWORD(v1315) = 0;
  v621 = sub_180006270(4, 4, &v1315);
  if ( v621 < 0 )
    goto LABEL_846;
  LODWORD(v1327) = v1315;
  LODWORD(v1315) = 0;
  v621 = sub_180006270(v705, 8, &v1315);
  if ( v621 < 0 )
    goto LABEL_846;
  v621 = sub_180006270(v706, (unsigned int)v1315, &v1327);
  if ( v621 < 0 )
    goto LABEL_846;
  LODWORD(v1315) = 0;
  v621 = sub_180006270(4, 4, &v1315);
  if ( v621 < 0 )
    goto LABEL_846;
  v621 = sub_180006270((unsigned int)v1327, (unsigned int)v1315, &v1327);
  if ( v621 < 0 )
    goto LABEL_846;
  LODWORD(v1315) = 0;
  v621 = sub_180006270(4, v707, &v1315);
  if ( v621 < 0 )
    goto LABEL_846;
  v621 = sub_180006270((unsigned int)v1327, (unsigned int)v1315, &v1327);
  if ( v621 < 0 )
    goto LABEL_846;
  LODWORD(v1315) = 0;
  v621 = sub_180006270(4, 4, &v1315);
  if ( v621 < 0 )
    goto LABEL_846;
  v621 = sub_180006270((unsigned int)v1327, (unsigned int)v1315, &v1327);
  if ( v621 < 0 )
    goto LABEL_846;
  LODWORD(v1315) = 0;
  v621 = sub_180006270(4, 4, &v1315);
  if ( v621 < 0 )
    goto LABEL_846;
  v621 = sub_180006270((unsigned int)v1327, (unsigned int)v1315, &v1327);
  if ( v621 < 0 )
    goto LABEL_846;
  LODWORD(v1328) = v1327;
  *(_DWORD *)Size = 0;
  v1317 = 0;
  v1331 = __rdtsc();
  v1355 = v708;
  LODWORD(v1315) = 0;
  v709 = sub_180006270(v708, HIDWORD(v1344[0]), &v1355);
  if ( v709 < 0 )
  {
    v1318 = v327;
    jj = v326;
    v1340 = v13;
  }
  else
  {
    v711 = (v1355 + 7) & 0xFFFFFFF8;
    if ( v711 < v1355 )
    {
      v1318 = v327;
LABEL_1263:
      v327 = v1318;
      goto LABEL_850;
    }
    v1355 = (v1355 + 7) & 0xFFFFFFF8;
    v712 = v711;
    v713 = GetProcessHeap();
    v714 = HeapAlloc(v713, 8u, v712);
    if ( !v714 )
    {
      v10 = -805306345;
      v1320 = -805306345;
      goto LABEL_1259;
    }
    v327 = v1318;
    v1340 = v13;
    jj = v326;
    v1341 = (SIZE_T)v714;
    *v714 = v1344[0];
    LODWORD(v1334) = sub_180006240(v714, 4, &v1341);
    if ( (v1334 & 0x80000000) != 0LL
      || (v716 = v1341,
          *(_DWORD *)v1341 = HIDWORD(v1344[0]),
          LODWORD(v1334) = sub_180006240(v716, 4, &v1341),
          (v1334 & 0x80000000) != 0LL) )
    {
      v1340 = v13;
      jj = v326;
      v1318 = v327;
      LODWORD(v1328) = v715;
      v717 = GetProcessHeap();
      HeapFree(v717, 0, v714);
      v709 = v1334;
      v710 = v1315;
    }
    else
    {
      *(_QWORD *)((char *)v714 + v1355 - 8) = v1331;
      memcpy((void *)v1341, (const void *)v1344[1], HIDWORD(v1344[0]));
      v710 = v1355;
      v709 = v1334;
      v1317 = v714;
    }
  }
  v1322 = 0;
  v1341 = 0;
  v1319 = 0;
  v10 = v709 | 0x10000000;
  v1325 = 0;
  v1320 = v709 | 0x10000000;
  v1333 = 0;
  if ( v709 < 0 )
  {
    v802 = 0;
    goto LABEL_1234;
  }
  v718 = (unsigned __int8 *)v1317;
  if ( !v1317 )
  {
    v10 = -805306355;
    goto LABEL_1262;
  }
  v1346 = v710;
  if ( !v710 || (v1343 = v710 + 8LL, (v1348 = sub_1800010C0(v1343)) == 0) )
  {
    v802 = v1319;
    v10 = -805306367;
    v1320 = -805306367;
LABEL_1236:
    v947 = GetProcessHeap();
    HeapFree(v947, 0, v1317);
    goto LABEL_1237;
  }
  v719 = v1346;
  v720 = 0;
  v721 = 0;
  v1335 = 0;
  uBytes_4 = 0;
  if ( v1346 )
  {
    do
      v720 ^= v718[v721++];
    while ( v721 < v1346 );
    uBytes_4 = v720;
  }
  dwBytes = v1348;
  v722 = v718;
  Src = (void *)0xC81ECB17B1B54A58LL;
  v1316 = v718;
  v723 = v1346 & 7;
  if ( (v1346 & 7) != 0 )
  {
    v724 = 0;
    LODWORD(v1334) = 0;
    LODWORD(v1338) = 0;
    v725 = 0;
    v726 = 0;
    do
    {
      v727 = *v722++;
      LODWORD(v1315) = 8 * v724;
      if ( v724 >= 4 )
        v725 |= v727 << (56 - v1315);
      else
        v726 |= v727 << (24 - v1315);
      ++v724;
    }
    while ( (int)v724 < (int)v723 );
    LODWORD(v1338) = v726;
    LODWORD(v1334) = v725;
    v1316 = v722;
    v1317 = v718;
    v1318 = v327;
    jj = v326;
    v1340 = v13;
    v728 = v726 ^ 0xB17A307A;
    v729 = v725 ^ 0x42F6B18D;
    v730 = 0;
    v731 = v726 ^ 0xB17A307A;
    v732 = v725 ^ 0x42F6B18D;
    if ( (v1346 & 7) != 0 )
    {
      v733 = (_BYTE *)dwBytes;
      do
      {
        v1331 = (size_t)(v733 + 1);
        if ( v730 >= 4 )
        {
          v732 = __ROR4__(v732, 24);
          v734 = v732;
        }
        else
        {
          v731 = __ROR4__(v731, 24);
          v734 = v731;
        }
        *v733 = v734;
        ++v730;
        v733 = (_BYTE *)v1331;
      }
      while ( (int)v730 < (int)v723 );
      dwBytes = v1331;
    }
    if ( v723 <= 4 )
    {
      v735 = 0;
      if ( v723 < 4 )
        v728 = v728 >> (8 * (4 - v723)) << (8 * (4 - v723));
    }
    else
    {
      v735 = v729 >> (8 * (8 - v723)) << (8 * (8 - v723));
    }
    v722 = (unsigned __int8 *)v1316;
  }
  else
  {
    v728 = 0;
    v735 = -1;
    LODWORD(v1338) = 0;
    LODWORD(v1334) = 0;
  }
  if ( v719 >> 3 )
  {
    v736 = (_BYTE *)dwBytes;
    v737 = v719 >> 3;
    v738 = v1334;
    v739 = WORD2(Src);
    LODWORD(v1315) = 19032;
    LODWORD(v1327) = WORD1(Src);
    v740 = v1338;
    v1330 = 0;
    do
    {
      v741 = v722[3] | ((v722[2] | ((v722[1] | (*v722 << 8)) << 8)) << 8);
      v742 = *((unsigned __int8 *)v1316 + 7)
           | ((*((unsigned __int8 *)v1316 + 6) | ((*((unsigned __int8 *)v1316 + 5) | (v722[4] << 8)) << 8)) << 8);
      v1316 = (char *)v1316 + 8;
      v743 = v735 ^ v742;
      v744 = v728 ^ v741 ^ HIDWORD(Src) ^ ((v735 ^ v742) - 19032);
      v745 = v743 ^ (__ROR4__(v744, 7) + WORD1(Src) * __ROR4__(v744 ^ HIDWORD(Src), 15));
      v746 = v744 ^ (v739 * __ROR4__(v745 - 1313519016, 9) - __ROR4__(v745, 10));
      v747 = v745 ^ (__ROR4__(v746, 27) + HIWORD(Src) * __ROR4__(v746 ^ v739, 28));
      v748 = v746 ^ (HIDWORD(Src) - (v747 ^ 0xB1B54A58));
      v749 = v747 ^ (WORD1(Src) * (v748 - 19032) - (v748 >> 6));
      v750 = v748 ^ (19032 * (v739 ^ __ROR4__(v749, 15)));
      v751 = v749 ^ (v739 * (HIWORD(Src) + __ROR4__(~v750, 3)));
      v752 = v750 ^ (v751 - 19032 - HIDWORD(Src));
      v753 = v751 ^ (v1327 * (v752 ^ HIWORD(Src))) ^ __ROR4__(v752, 10);
      v754 = v752 ^ __ROR4__(v753, 3) ^ (v739 * __ROR4__(v753 ^ 0x4A58, 26));
      v755 = v753 ^ (19032 * (__ROR4__(v754, 15) - HIWORD(Src)));
      v756 = v754
           ^ ((v755 ^ (v755 >> 14)) >> 1)
           ^ (19032 * (v755 ^ HIWORD(Src)))
           ^ (19032 * ((8 * (v755 - v739)) | ((v755 - v739) >> 29)));
      v757 = v755 ^ (WORD1(Src) * (v756 - v739) - (v756 >> 13));
      v758 = v756 ^ __ROR4__(v757, 11) ^ (v739 * __ROR4__(-1313519016 - v757, 9));
      v759 = v757 ^ (v758 - HIWORD(Src) + 1313519016);
      v760 = v758 ^ (19032 * (v759 ^ WORD1(Src)) - __ROR4__(v759, 7));
      v761 = v759 ^ (WORD1(Src) * __ROR4__(v760 ^ HIWORD(Src), 28) - __ROR4__(v760, 16));
      v762 = v760 ^ (__ROR4__(v761, 4) + v739 * __ROR4__(-1313519016 - v761, 10));
      v763 = v761 ^ __ROR4__(v762, 9) ^ (HIWORD(Src) * __ROR4__(v762 + 1313519016, 4));
      v764 = v762 ^ (19032 * __ROR4__(v763 ^ HIDWORD(Src), 24) - __ROR4__(v763, 30));
      v765 = v763 ^ (WORD1(Src) * __ROR4__(HIDWORD(Src) - v764, 11) - __ROR4__(v764, 12));
      v766 = v764 ^ (v765 >> 8) ^ (v739 * (WORD1(Src) ^ v765));
      v728 = v740 ^ v766;
      v735 = v738 ^ v766 ^ HIDWORD(Src) ^ v765 ^ 0xB1B54A58;
      v736[3] = v740 ^ v766;
      LOBYTE(v750) = __ROR4__(v740 ^ v766, 8);
      v738 = v742;
      v722 = (unsigned __int8 *)v1316;
      v740 = v741;
      v736[7] = v735;
      v736[2] = v750;
      v736[6] = __ROR4__(v735, 8);
      v736[1] = __ROR4__(v728, 16);
      v736[5] = __ROR4__(v735, 16);
      *v736 = __ROR4__(v728, 24);
      v736[4] = __ROR4__(v735, 24);
      v736 += 8;
      ++v1330;
    }
    while ( v1330 < v737 );
    v720 = uBytes_4;
    v13 = v1340;
    v8 = 4;
    v326 = jj;
    v718 = (unsigned __int8 *)v1317;
    v719 = v1346;
  }
  *(_QWORD *)(v1348 + v719) = v720;
  v767 = GetProcessHeap();
  v768 = HeapAlloc(v767, 8u, 0x30u);
  v1316 = v768;
  if ( !v768 )
  {
    v769 = v1318;
    v770 = -1073741801;
LABEL_1002:
    v771 = v1322;
    goto LABEL_1003;
  }
  v779 = v1343;
  *v768 = v1343;
  v780 = GetProcessHeap();
  v781 = HeapAlloc(v780, 8u, v779);
  v769 = v1318;
  if ( !v781 )
    goto LABEL_1017;
  v1317 = v718;
  v782 = v1316;
  *((_QWORD *)v1316 + 1) = v781;
  memcpy(v781, (const void *)v1348, (unsigned int)v1343);
  v782[4] = 160;
  v783 = GetProcessHeap();
  v784 = HeapAlloc(v783, 8u, 0xA0u);
  if ( !v784 )
    goto LABEL_1017;
  *((_QWORD *)v782 + 3) = v784;
  *v784 = xmmword_1800240A0;
  v784[1] = xmmword_1800240B0;
  v784[2] = xmmword_1800240C0;
  v784[3] = xmmword_1800240D0;
  v784[4] = xmmword_1800240E0;
  v784[5] = xmmword_1800240F0;
  v784[6] = xmmword_180024100;
  v784[7] = xmmword_180024110;
  v784[8] = xmmword_180024120;
  v784[9] = xmmword_180024130;
  v782[8] = 8;
  v785 = GetProcessHeap();
  v786 = HeapAlloc(v785, 8u, 8u);
  if ( !v786 )
  {
LABEL_1017:
    v770 = -1073741801;
    v787 = v1316;
    v1318 = v769;
    v1331 = *((_QWORD *)v1316 + 1);
    if ( v1331 )
    {
      v788 = GetProcessHeap();
      HeapFree(v788, 0, (LPVOID)v1331);
      v787 = v1316;
      *((_QWORD *)v1316 + 1) = 0;
    }
    v1331 = v787[3];
    if ( v1331 )
    {
      v789 = GetProcessHeap();
      HeapFree(v789, 0, (LPVOID)v1331);
      v787 = v1316;
      *((_QWORD *)v1316 + 3) = 0;
    }
    v1331 = v787[5];
    if ( v1331 )
    {
      v790 = GetProcessHeap();
      HeapFree(v790, 0, (LPVOID)v1331);
      *((_QWORD *)v1316 + 5) = 0;
    }
    v791 = GetProcessHeap();
    HeapFree(v791, 0, v1316);
    goto LABEL_1002;
  }
  *((_QWORD *)v782 + 5) = v786;
  *v786 = qword_180024140;
  v1335 = v782;
  v770 = 0;
  v1318 = v769;
  v771 = v1335;
  v1335 = 0;
LABEL_1003:
  v1322 = v771;
  v772 = GetProcessHeap();
  HeapFree(v772, 0, (LPVOID)v1348);
  v773 = v1335;
  if ( v1335 )
  {
    v1331 = *((_QWORD *)v1335 + 1);
    if ( v1331 )
    {
      v774 = GetProcessHeap();
      HeapFree(v774, 0, (LPVOID)v1331);
      v773 = v1335;
      *((_QWORD *)v1335 + 1) = 0;
    }
    v1331 = v773[3];
    if ( v1331 )
    {
      v775 = GetProcessHeap();
      HeapFree(v775, 0, (LPVOID)v1331);
      v773 = v1335;
      *((_QWORD *)v1335 + 3) = 0;
    }
    v1331 = v773[5];
    if ( v1331 )
    {
      v776 = GetProcessHeap();
      HeapFree(v776, 0, (LPVOID)v1331);
      *((_QWORD *)v1335 + 5) = 0;
    }
    v777 = GetProcessHeap();
    HeapFree(v777, 0, v1335);
    v778 = (unsigned int *)v1322;
  }
  else
  {
    v778 = (unsigned int *)v1322;
  }
  v10 = v770 | 0x10000000;
  v1320 = v10;
  if ( v10 < 0 )
  {
    v946 = v1317;
    v1318 = v769;
    v802 = v1319;
    goto LABEL_1235;
  }
  v792 = *v778;
  LODWORD(v1338) = 0;
  LODWORD(v1327) = 4;
  v793 = sub_180006270(4, v792, &v1327);
  if ( v793 < 0 )
    goto LABEL_1050;
  v793 = sub_180006270((unsigned int)v1327, 4, &v1327);
  if ( v793 < 0
    || (v795 = *(unsigned int *)(v794 + 16),
        v1330 = v794 + 16,
        v793 = sub_180006270((unsigned int)v1327, v795, &v1327),
        v793 < 0)
    || (v793 = sub_180006270((unsigned int)v1327, 4, &v1327), v793 < 0)
    || (v797 = *(unsigned int *)(v796 + 32),
        v1346 = v796 + 32,
        v793 = sub_180006270((unsigned int)v1327, v797, &v1327),
        v793 < 0) )
  {
LABEL_1050:
    v1318 = v769;
    goto LABEL_1051;
  }
  v799 = v1327;
  v1322 = v798;
  v800 = GetProcessHeap();
  jj = HeapAlloc(v800, 8u, v799);
  v801 = jj;
  if ( jj )
  {
    v769 = v1318;
    v803 = v1317;
    v804 = (int)v1328;
    *(_DWORD *)jj = *(_DWORD *)v1322;
    v1318 = v769;
    LODWORD(v1328) = v804;
    v1317 = v803;
    v1316 = v801;
    v793 = sub_180006240(v801, 4, &v1316);
    if ( v793 < 0 )
    {
      v1317 = v807;
      LODWORD(v1328) = v808;
      jj = v805;
    }
    else
    {
      memcpy(v1316, v806[1], *(unsigned int *)v806);
      v793 = sub_180006240(v1316, *(unsigned int *)v1322, &v1316);
      if ( v793 >= 0 )
      {
        v809 = v1316;
        *(_DWORD *)v1316 = *(_DWORD *)v1330;
        v793 = sub_180006240(v809, 4, &v1316);
        if ( v793 >= 0 )
        {
          memcpy(v1316, v806[3], *v810);
          v793 = sub_180006240(v1316, *(unsigned int *)v1330, &v1316);
          if ( v793 < 0 )
          {
            v813 = v1322;
          }
          else
          {
            v811 = v1316;
            *(_DWORD *)v1316 = *(_DWORD *)v1346;
            v793 = sub_180006240(v811, 4, &v1316);
            v813 = v1322;
            if ( v793 >= 0 )
            {
              memcpy(v1316, *((const void **)v1322 + 5), *v812);
              v793 = sub_180006240(v1316, *(unsigned int *)v1346, &v1316);
              if ( v793 >= 0 )
              {
                v1341 = (SIZE_T)jj;
                LODWORD(v1338) = v1327;
LABEL_1051:
                v10 = v793 | 0x10000000;
                v1320 = v10;
                if ( v10 < 0 )
                  goto LABEL_1035;
                v1362 = 8;
                v815 = sub_180006270(8, (unsigned int)v1328, &v1362);
                v10 = v815 | 0x10000000;
                v1320 = v815 | 0x10000000;
                if ( v815 < 0 )
                  goto LABEL_1035;
                v817 = (v1362 + 7) & 0xFFFFFFF8;
                if ( (unsigned int)v817 < v1362 )
                {
                  v10 = -1073741675;
                  goto LABEL_1034;
                }
                v1363 = (v1362 + 7) & 0xFFFFFFF8;
                v1320 = sub_180006270(v817, v816, &v1363);
                v10 = v1320;
                if ( v1320 < 0 )
                  goto LABEL_1035;
                v820 = (unsigned int *)v1344[1];
                v821 = 0;
                v1340 = v13;
                jj = v326;
                v1318 = v769;
                v1317 = v819;
                v1322 = v818;
                LODWORD(v1334) = 0;
                if ( v1344[1] )
                {
                  v1322 = v818;
                  v1317 = v819;
                  v1318 = v769;
                  jj = v326;
                  v1340 = v13;
                  if ( LODWORD(v1344[0]) > 1 )
                  {
                    v1343 = v1344[1];
                    for ( i10 = 0; ; i10 = v1315 + 1 )
                    {
                      LODWORD(v1315) = i10;
                      if ( i10 )
                        break;
                      v1320 = sub_180006240(v820, 4, &v1343);
                      v10 = v1320;
                      if ( v1320 < 0 )
                        goto LABEL_1066;
                      v1320 = sub_180006240(v1343, v823, &v1343);
                      v10 = v1320;
                      if ( v1320 < 0 )
                        goto LABEL_1066;
                      v820 = (unsigned int *)v1343;
                    }
                    v824 = *v820;
                    v1320 = sub_180006240(v820, 4, &v1343);
                    v10 = v1320;
                    if ( v1320 < 0 )
                      goto LABEL_1066;
                    v825 = v1344[1];
                    if ( v1344[1] && LODWORD(v1344[0]) > 2 )
                    {
                      v1343 = v1344[1];
                      for ( i11 = 0; i11 < 2; i11 = v830 + 1 )
                      {
                        v1320 = sub_180006240(v825, 4, &v1343);
                        v10 = v1320;
                        if ( v1320 < 0 )
                          goto LABEL_1066;
                        v1320 = sub_180006240(v1343, v829, &v1343);
                        v10 = v1320;
                        if ( v1320 < 0 )
                          goto LABEL_1066;
                        v825 = v1343;
                      }
                      v1320 = sub_180006240(v825, 4, &v1343);
                      v10 = v1320;
                      if ( v1320 >= 0 )
                      {
                        LODWORD(v1334) = v821;
                        LODWORD(v1327) = 4;
                        v1320 = sub_180006270(4, v1363, &v1327);
                        v10 = v1320;
                        if ( v1320 < 0 )
                          goto LABEL_1082;
                        v1320 = sub_180006270((unsigned int)v1327, 4, &v1327);
                        v10 = v1320;
                        if ( v1320 < 0
                          || (v1320 = sub_180006270((unsigned int)v1327, v824, &v1327), v10 = v1320, v1320 < 0)
                          || (v1320 = sub_180006270((unsigned int)v1327, 4, &v1327), v10 = v1320, v1320 < 0)
                          || (v1320 = sub_180006270((unsigned int)v1327, v831, &v1327), v10 = v1320, v1320 < 0) )
                        {
LABEL_1082:
                          if ( v10 < 0 )
                            goto LABEL_1035;
                        }
                        else
                        {
                          v821 = v1327;
                          LODWORD(v1334) = v1327;
                        }
                        if ( v821 > 0x400000 )
                        {
                          v10 = -2147418113;
                          goto LABEL_1034;
                        }
LABEL_1067:
                        v826 = v821;
                        v827 = GetProcessHeap();
                        v1319 = HeapAlloc(v827, 8u, v826);
                        v802 = v1319;
                        if ( !v1319 )
                        {
                          v10 = -805306345;
                          v1320 = -805306345;
                          goto LABEL_1234;
                        }
                        v1370 = 0;
                        v1377 = 0;
                        v1378 = 0;
                        if ( !v1341 )
                        {
                          v10 = -2147024809;
LABEL_1097:
                          v1320 = v10;
                          goto LABEL_1234;
                        }
                        LODWORD(v1378) = v1338;
                        *(_QWORD *)&v1377 = v1341;
                        *(_QWORD *)((char *)&v1378 + 4) = (unsigned int)v1334;
                        *((_QWORD *)&v1377 + 1) = v1319;
                        if ( GetModuleHandleExW(1u, L"ntdll.dll", &v1370)
                          && (v833 = (NTSTATUS (__stdcall *)(SYSTEM_INFORMATION_CLASS, PVOID, ULONG, PULONG))GetProcAddress(v1370, "NtQuerySystemInformation")) != 0 )
                        {
                          v834 = ((__int64 (__fastcall *)(__int64, __int128 *))v833)(134, &v1377);
                          v10 = v834 | 0x10000000;
                          v1320 = v834 | 0x10000000;
                          if ( v834 >= 0 )
                          {
                            v835 = DWORD1(v1378);
                            goto LABEL_1100;
                          }
                        }
                        else
                        {
                          v832 = GetLastError();
                          v1320 = v832;
                          v10 = v832;
                          if ( v832 > 0 )
                          {
                            v10 = (unsigned __int16)v832 | 0x80070000;
                            v1320 = v10;
                          }
                          if ( v10 >= 0 )
                          {
                            v10 = -2147467259;
                            goto LABEL_1097;
                          }
                        }
                        if ( v10 == -805306333 )
                        {
                          v10 = -2147024774;
                          goto LABEL_1097;
                        }
                        if ( v10 < 0 )
                          goto LABEL_1234;
                        v835 = v1334;
LABEL_1100:
                        LODWORD(v1327) = 0;
                        v1335 = v802;
                        if ( v835 < 4 )
                        {
LABEL_1101:
                          v10 = -805306306;
                          goto LABEL_1097;
                        }
                        LODWORD(v1315) = *v802;
                        v836 = sub_180006240(v802, 4, &v1335);
                        if ( v836 >= 0 )
                        {
                          v836 = sub_180006270(0, 4, &v1327);
                          if ( v836 < 0 )
                          {
LABEL_1154:
                            v1319 = v802;
                            v854 = v1318;
                            goto LABEL_1155;
                          }
                          if ( v838 - (int)v1327 < (unsigned int)v839 )
                            goto LABEL_1101;
                          v1330 = (SIZE_T)v1335;
                          v1331 = v839;
                          v836 = sub_180006240(v1335, (unsigned int)v839, &v1335);
                          if ( v836 >= 0 )
                          {
                            v836 = sub_180006270((unsigned int)v1327, v840, &v1327);
                            if ( v836 >= 0 )
                            {
                              if ( (unsigned int)(v841 - v1327) < 4 )
                                goto LABEL_1101;
                              LODWORD(v1334) = *(_DWORD *)v1335;
                              v836 = sub_180006240(v1335, 4, &v1335);
                              if ( v836 >= 0 )
                              {
                                v836 = sub_180006270((unsigned int)v1327, 4, &v1327);
                                if ( v836 >= 0 )
                                {
                                  if ( v842 - (int)v1327 < (unsigned int)v843 )
                                    goto LABEL_1101;
                                  dwBytes = (SIZE_T)v1335;
                                  v1346 = v843;
                                  v836 = sub_180006240(v1335, (unsigned int)v843, &v1335);
                                  if ( v836 >= 0 )
                                  {
                                    v836 = sub_180006270((unsigned int)v1327, v844, &v1327);
                                    if ( v836 >= 0 )
                                    {
                                      if ( (unsigned int)(v845 - v1327) < 4 )
                                        goto LABEL_1101;
                                      LODWORD(v1338) = *(_DWORD *)v1335;
                                      v836 = sub_180006240(v1335, 4, &v1335);
                                      if ( v836 >= 0 )
                                      {
                                        v836 = sub_180006270((unsigned int)v1327, 4, &v1327);
                                        if ( v836 >= 0 )
                                        {
                                          if ( v846 - (int)v1327 < v847 )
                                            goto LABEL_1101;
                                          v836 = sub_180006270((unsigned int)v1327, v847, &v1327);
                                          if ( v836 >= 0 )
                                          {
                                            if ( v848 != (_DWORD)v1327 )
                                              goto LABEL_1101;
                                            v851 = (unsigned int)v1315;
                                            if ( (unsigned int)(v849 + v850 + v1315) + 12LL != v848 )
                                              goto LABEL_1101;
                                            v852 = GetProcessHeap();
                                            v1316 = HeapAlloc(v852, 8u, 0x30u);
                                            v853 = v1316;
                                            if ( !v1316 )
                                            {
                                              v1325 = 0;
                                              v10 = -805306345;
                                              goto LABEL_1097;
                                            }
                                            v854 = v1318;
                                            v1340 = v13;
                                            jj = v326;
                                            v1342 = 0;
                                            if ( v1330 )
                                            {
                                              *(_DWORD *)v1316 = v851;
                                              v855 = GetProcessHeap();
                                              v856 = HeapAlloc(v855, 8u, v851);
                                              if ( !v856 )
                                              {
LABEL_1133:
                                                v864 = v1316;
                                                v836 = -1073741801;
                                                v1331 = *((_QWORD *)v1316 + 1);
                                                if ( v1331 )
                                                {
                                                  v865 = GetProcessHeap();
                                                  HeapFree(v865, 0, (LPVOID)v1331);
                                                  v864 = v1316;
                                                  *((_QWORD *)v1316 + 1) = 0;
                                                }
                                                v1331 = v864[3];
                                                if ( v1331 )
                                                {
                                                  v866 = GetProcessHeap();
                                                  HeapFree(v866, 0, (LPVOID)v1331);
                                                  v864 = v1316;
                                                  *((_QWORD *)v1316 + 3) = 0;
                                                }
                                                v1331 = v864[5];
                                                if ( v1331 )
                                                {
                                                  v867 = GetProcessHeap();
                                                  HeapFree(v867, 0, (LPVOID)v1331);
                                                  *((_QWORD *)v1316 + 5) = 0;
                                                }
                                                v868 = GetProcessHeap();
                                                HeapFree(v868, 0, v1316);
                                                v869 = (size_t *)v1342;
                                                goto LABEL_1143;
                                              }
                                              *((_QWORD *)v1316 + 1) = v856;
                                              v836 = 0;
                                              memcpy(v856, (const void *)v1330, v1331);
                                              v853 = v1316;
                                            }
                                            else
                                            {
                                              *(_DWORD *)v1316 = 0;
                                              v836 = 0;
                                              v853[1] = 0;
                                            }
                                            if ( dwBytes )
                                            {
                                              *((_DWORD *)v853 + 4) = v1334;
                                              v857 = GetProcessHeap();
                                              v858 = HeapAlloc(v857, 8u, v1346);
                                              v859 = v1316;
                                              if ( !v858 )
                                              {
LABEL_1132:
                                                v1316 = v859;
                                                v1340 = v13;
                                                jj = v326;
                                                v1318 = v854;
                                                goto LABEL_1133;
                                              }
                                              *((_QWORD *)v1316 + 3) = v858;
                                              v836 = 0;
                                              memcpy(v858, (const void *)dwBytes, v1346);
                                              v853 = v1316;
                                            }
                                            else
                                            {
                                              *((_DWORD *)v853 + 4) = 0;
                                              v853[3] = 0;
                                            }
                                            if ( v1335 )
                                            {
                                              v860 = (unsigned int)v1338;
                                              *((_DWORD *)v853 + 8) = v1338;
                                              v861 = v860;
                                              v1331 = v860;
                                              v862 = GetProcessHeap();
                                              v863 = HeapAlloc(v862, 8u, v861);
                                              v859 = v1316;
                                              if ( !v863 )
                                                goto LABEL_1132;
                                              *((_QWORD *)v1316 + 5) = v863;
                                              v836 = 0;
                                              memcpy(v863, v1335, v1331);
                                              v853 = v1316;
                                            }
                                            else
                                            {
                                              *((_DWORD *)v853 + 8) = 0;
                                              v853[5] = 0;
                                            }
                                            v869 = v853;
                                            v1342 = v853;
                                            v1318 = v854;
                                            jj = v326;
                                            v1340 = v13;
LABEL_1143:
                                            if ( v836 < 0 )
                                            {
                                              v837 = 0;
                                              v1325 = 0;
                                              if ( v869 )
                                              {
                                                v1331 = v869[1];
                                                if ( v1331 )
                                                {
                                                  v870 = GetProcessHeap();
                                                  HeapFree(v870, 0, (LPVOID)v1331);
                                                  v869 = (size_t *)v1342;
                                                  *((_QWORD *)v1342 + 1) = 0;
                                                }
                                                v1331 = v869[3];
                                                if ( v1331 )
                                                {
                                                  v871 = GetProcessHeap();
                                                  HeapFree(v871, 0, (LPVOID)v1331);
                                                  v869 = (size_t *)v1342;
                                                  *((_QWORD *)v1342 + 3) = 0;
                                                }
                                                v1331 = v869[5];
                                                if ( v1331 )
                                                {
                                                  v872 = GetProcessHeap();
                                                  HeapFree(v872, 0, (LPVOID)v1331);
                                                  *((_QWORD *)v1342 + 5) = 0;
                                                }
                                                v873 = GetProcessHeap();
                                                HeapFree(v873, 0, v1342);
                                                v837 = 0;
                                                v1325 = 0;
                                              }
                                            }
                                            else
                                            {
                                              v837 = (unsigned int *)v869;
                                              v1325 = v869;
                                            }
LABEL_1155:
                                            v10 = v836 | 0x10000000;
                                            v1320 = v10;
                                            if ( v10 < 0 )
                                              goto LABEL_1035;
                                            if ( !v837 || (v1346 = *((_QWORD *)v837 + 1)) == 0 || !*v837 )
                                            {
                                              v10 = -805306355;
                                              goto LABEL_1034;
                                            }
                                            v874 = *v837 - 8LL;
                                            v1343 = v874;
                                            v1333 = (LPVOID)sub_1800010C0(v874);
                                            if ( !v1333 )
                                            {
LABEL_1187:
                                              v10 = -805306367;
                                              v1333 = 0;
                                              goto LABEL_1034;
                                            }
                                            v876 = 0;
                                            uBytes_4 = 0;
                                            v1316 = (LPVOID)0x7F1137FAB69605ELL;
                                            dwBytes = v1346;
                                            v1348 = (SIZE_T)v1333;
                                            v877 = v874 & 7;
                                            if ( (v874 & 7) != 0 )
                                            {
                                              LODWORD(v1334) = 0;
                                              LODWORD(v1338) = 0;
                                              v878 = 0;
                                              v879 = 0;
                                              v880 = 0;
                                              v881 = (unsigned __int8 *)dwBytes;
                                              do
                                              {
                                                v882 = *v881++;
                                                LODWORD(v1315) = 8 * v878;
                                                if ( v878 >= 4 )
                                                  v879 |= v882 << (56 - v1315);
                                                else
                                                  v880 |= v882 << (24 - v1315);
                                                ++v878;
                                              }
                                              while ( (int)v878 < v877 );
                                              LODWORD(v1338) = v880;
                                              v874 = v1343;
                                              LODWORD(v1334) = v879;
                                              v883 = v879;
                                              v876 = uBytes_4;
                                              dwBytes = (SIZE_T)v881;
                                              v1318 = v854;
                                              jj = v326;
                                              v1340 = v13;
                                              v884 = (unsigned int)v1338 ^ 0x92F65A5;
                                              v885 = v883 ^ 0x699A899C;
                                              v875 = 0;
                                              v886 = v1338 ^ 0x92F65A5;
                                              v887 = v885;
                                              if ( v877 )
                                              {
                                                v888 = (_BYTE *)v1348;
                                                do
                                                {
                                                  v1331 = (size_t)(v888 + 1);
                                                  if ( (unsigned int)v875 >= 4 )
                                                  {
                                                    v887 = __ROR4__(v887, 24);
                                                    v889 = v887;
                                                  }
                                                  else
                                                  {
                                                    v886 = __ROR4__(v886, 24);
                                                    v889 = v886;
                                                  }
                                                  *v888 = v889;
                                                  v875 = (unsigned int)(v875 + 1);
                                                  v888 = (_BYTE *)v1331;
                                                }
                                                while ( (int)v875 < v877 );
                                                v1348 = v1331;
                                              }
                                              if ( (unsigned int)v877 <= 4 )
                                              {
                                                v890 = 0;
                                                if ( (unsigned int)v877 < 4 )
                                                  v884 = (unsigned int)v884 >> (8 * (4 - v877)) << (8 * (4 - v877));
                                              }
                                              else
                                              {
                                                v890 = v885 >> (8 * (8 - v877)) << (8 * (8 - v877));
                                              }
                                            }
                                            else
                                            {
                                              v890 = 0;
                                              LODWORD(v1338) = 0;
                                              v884 = 0;
                                              LODWORD(v1334) = -1;
                                            }
                                            v1331 = v874 >> 3;
                                            if ( v874 >> 3 )
                                            {
                                              v891 = HIDWORD(v1316);
                                              v892 = (unsigned __int8 *)dwBytes;
                                              v893 = (_BYTE *)v1348;
                                              v894 = v1334;
                                              v895 = v1338;
                                              LODWORD(v1315) = HIDWORD(v1316) ^ 0xAB69605E;
                                              LODWORD(v1327) = 24670;
                                              v896 = v1331;
                                              v1330 = 0;
                                              LODWORD(v1328) = WORD2(v1316);
                                              do
                                              {
                                                v897 = v892[1];
                                                v898 = *v892;
                                                v899 = v892[4];
                                                v892 += 8;
                                                v900 = *(v892 - 5) | ((*(v892 - 6) | ((v897 | (v898 << 8)) << 8)) << 8);
                                                v901 = *(v892 - 1)
                                                     | ((*(v892 - 2) | ((*(v892 - 3) | (v899 << 8)) << 8)) << 8);
                                                v902 = v890 ^ v901 ^ v1315 ^ v884 ^ v900;
                                                v903 = v884
                                                     ^ v900
                                                     ^ (__ROR4__(v902, 22)
                                                      + (_DWORD)v1328 * __ROR4__(v902 + 1419157410, 27));
                                                v904 = v902
                                                     ^ (WORD1(v1316) * __ROR4__(v903 + v891, 9) - __ROR4__(v903, 30));
                                                v905 = v903 ^ (v1327 * (v904 - (_DWORD)v1328) - (v904 >> 13));
                                                v906 = v904
                                                     ^ (HIWORD(v1316) * __ROR4__(v905 ^ WORD1(v1316), 26)
                                                      - __ROR4__(v905, 30));
                                                v907 = v905 ^ (v891 - (v906 ^ 0xAB69605E));
                                                v908 = v906
                                                     ^ (WORD1(v1316) * (v907 ^ (unsigned int)v1328))
                                                     ^ __ROR4__(v907, 6);
                                                v909 = v907 ^ (__ROR4__(v908, 30) + v1327 * __ROR4__(v908 + v891, 15));
                                                v910 = v908
                                                     ^ (HIWORD(v1316) * __ROR4__(v909 + 1419157410, 14)
                                                      - __ROR4__(v909, 24));
                                                v911 = v909
                                                     ^ __ROR4__(v910, 10)
                                                     ^ ((_DWORD)v1328 * __ROR4__(v910 ^ 0xAB69605E, 12));
                                                v912 = v911
                                                     ^ (HIWORD(v1316)
                                                      * (v1327
                                                       + __ROR4__(
                                                           ~(v910
                                                           ^ (v911 >> 10)
                                                           ^ (WORD1(v1316) * (HIWORD(v1316) ^ v911))),
                                                           5)));
                                                v913 = v910
                                                     ^ (v911 >> 10)
                                                     ^ (WORD1(v1316) * (HIWORD(v1316) ^ v911))
                                                     ^ (v912 - HIWORD(v1316))
                                                     ^ 0xAB69605E;
                                                v914 = v912
                                                     ^ ((v913 >> 2) + (_DWORD)v1328 * __ROR4__(v913 ^ HIWORD(v1316), 30));
                                                v915 = v913
                                                     ^ (__ROR4__(v914, 25)
                                                      + WORD1(v1316) * __ROR4__(v914 - HIDWORD(v1316), 6));
                                                v916 = v914 ^ (v1327 * ((unsigned int)v1328 ^ v915) + __ROR4__(v915, 9));
                                                v917 = v915
                                                     ^ (__ROR4__(v916, 25)
                                                      + HIWORD(v1316) * __ROR4__(v916 ^ WORD1(v1316), 27));
                                                v918 = v916 ^ v917 ^ v1315;
                                                v919 = v917 ^ ((_DWORD)v1328 * (__ROR4__(v918, 3) - WORD1(v1316)));
                                                v920 = v918
                                                     ^ (v1327 * __ROR4__(v919 - HIDWORD(v1316), 1) - __ROR4__(v919, 6));
                                                v921 = v919
                                                     ^ (__ROR4__(v920, 18)
                                                      + HIWORD(v1316) * __ROR4__(v920 - 1419157410, 29));
                                                v875 = v920
                                                     ^ (unsigned int)((_DWORD)v1328 * __ROR4__(v921 - 1419157410, 17)
                                                                    - __ROR4__(v921, 14));
                                                v891 = HIDWORD(v1316);
                                                v922 = v921
                                                     ^ ((unsigned int)v875 >> 3)
                                                     ^ (WORD1(v1316) * (v875 ^ v1327));
                                                v923 = __ROR4__(v922, 30);
                                                v890 = v894 ^ v922;
                                                v894 = v901;
                                                v884 = v895
                                                     ^ (unsigned int)v875
                                                     ^ v923
                                                     ^ ((_DWORD)v1327
                                                      * __ROR4__(
                                                          HIDWORD(v1316)
                                                        ^ v921
                                                        ^ ((unsigned int)v875 >> 3)
                                                        ^ (WORD1(v1316) * (v875 ^ v1327)),
                                                          28));
                                                v895 = v900;
                                                v893[3] = v884;
                                                v893[7] = v890;
                                                v893[2] = __ROR4__(v884, 8);
                                                v893[6] = __ROR4__(v890, 8);
                                                v893[1] = __ROR4__(v884, 16);
                                                v893[5] = __ROR4__(v890, 16);
                                                *v893 = __ROR4__(v884, 24);
                                                v893[4] = __ROR4__(v890, 24);
                                                v893 += 8;
                                                ++v1330;
                                              }
                                              while ( v1330 < v896 );
                                              v876 = uBytes_4;
                                              v13 = v1340;
                                              v8 = 4;
                                              v326 = jj;
                                              v874 = v1343;
                                            }
                                            for ( i12 = 0; i12 < v874; ++i12 )
                                              v876 ^= *((_BYTE *)v1333 + i12);
                                            if ( v876 != *(_QWORD *)(v874 + v1346) )
                                            {
                                              sub_180010DC8(v1333, v1333, v875, v884);
                                              goto LABEL_1187;
                                            }
                                            v925 = v1319;
                                            LODWORD(v1327) = 0;
                                            v1316 = v1333;
                                            if ( (unsigned int)v874 < 4 )
                                              goto LABEL_1189;
                                            v926 = sub_180006240(v1333, 4, &v1316);
                                            if ( v926 >= 0 )
                                            {
                                              v926 = sub_180006270(0, 4, &v1327);
                                              if ( v926 < 0 )
                                                goto LABEL_1227;
                                              if ( (unsigned int)(v1343 - v1327) < 4 )
                                              {
LABEL_1193:
                                                v931 = v1333;
LABEL_1194:
                                                v926 = -1073741762;
                                                v1333 = v931;
LABEL_1229:
                                                v1318 = v928;
                                                v1317 = v930;
                                                v1322 = v929;
                                                v1319 = v925;
                                                goto LABEL_1230;
                                              }
                                              LODWORD(v1334) = *(_DWORD *)v1316;
                                              v926 = sub_180006240(v1316, 4, &v1316);
                                              if ( v926 < 0
                                                || (v926 = sub_180006270((unsigned int)v1327, 4, &v1327), v926 < 0) )
                                              {
LABEL_1227:
                                                v927 = v1333;
                                              }
                                              else
                                              {
                                                if ( (int)v1343 - (int)v1327 < (unsigned int)v1334 )
                                                  goto LABEL_1193;
                                                v926 = sub_180006270((unsigned int)v1327, (unsigned int)v1334, &v1327);
                                                if ( v926 >= 0 )
                                                {
                                                  v926 = (int)v1316;
                                                  v931 = v1333;
                                                  dwBytes = (unsigned int)v1334;
                                                  if ( (char *)v1333 + (unsigned int)v1343 >= (char *)v1316
                                                                                            + (unsigned int)v1334
                                                    && (unsigned __int64)v1333
                                                     + (unsigned int)v1343
                                                     - dwBytes
                                                     - (_QWORD)v1316 < 8 )
                                                  {
                                                    LODWORD(v1327) = *(_DWORD *)v1333;
                                                    v1330 = 0;
                                                    v1346 = 0;
                                                    v1348 = 0;
                                                    LODWORD(v1338) = 0;
                                                    if ( v1316 )
                                                    {
                                                      v1331 = (size_t)v1316;
                                                      v932 = sub_180006240(v1316, dwBytes, &v1330);
                                                      v1319 = v925;
                                                      v926 = v932;
                                                      v1322 = v933;
                                                      v1317 = v934;
                                                      v1318 = v935;
                                                      if ( v932 >= 0 )
                                                      {
                                                        v936 = v1330;
                                                        v937 = v1331;
                                                        while ( v937 < v936 )
                                                        {
                                                          v926 = sub_180006240(v937, 4, &v1346);
                                                          if ( v926 < 0 )
                                                            goto LABEL_1213;
                                                          if ( v1346 > v939 )
                                                            goto LABEL_1212;
                                                          v940 = *v938;
                                                          LODWORD(v1315) = 0;
                                                          v926 = sub_180006270(4, v940, &v1315);
                                                          if ( v926 < 0 )
                                                            goto LABEL_1230;
                                                          v926 = sub_180006240(v941, (unsigned int)v1315, &v1348);
                                                          if ( v926 < 0 )
                                                            goto LABEL_1213;
                                                          v937 = v1348;
                                                          if ( v1348 > v936 )
                                                            goto LABEL_1212;
                                                          LODWORD(v1338) = v1338 + 1;
                                                        }
                                                        if ( v937 == v936 )
                                                          goto LABEL_1218;
LABEL_1212:
                                                        v926 = -1073741811;
                                                        goto LABEL_1230;
                                                      }
LABEL_1213:
                                                      v942 = *(_DWORD *)Size;
                                                    }
                                                    else
                                                    {
                                                      v1319 = v925;
                                                      v1322 = v929;
                                                      v1317 = v930;
                                                      v1318 = v928;
LABEL_1218:
                                                      v943 = 0;
                                                      v1330 = 0;
                                                      if ( (_DWORD)v1334 )
                                                      {
                                                        v944 = GetProcessHeap();
                                                        v945 = dwBytes;
                                                        v943 = HeapAlloc(v944, 8u, dwBytes);
                                                        v1330 = (SIZE_T)v943;
                                                        if ( !v943 )
                                                        {
                                                          v926 = -1073741801;
                                                          goto LABEL_1230;
                                                        }
                                                        v926 = 0;
                                                      }
                                                      else
                                                      {
                                                        v945 = dwBytes;
                                                      }
                                                      if ( v1316 )
                                                        memcpy(v943, v1316, v945);
                                                      v1336 = (LPVOID)v1330;
                                                      v942 = v1338;
                                                      *(_DWORD *)Size = v1338;
                                                    }
                                                    if ( v926 < 0 || (_DWORD)v1327 == v942 )
                                                      goto LABEL_1230;
LABEL_1189:
                                                    v926 = -1073741762;
LABEL_1230:
                                                    v10 = v926 | 0x10000000;
                                                    goto LABEL_1034;
                                                  }
                                                  goto LABEL_1194;
                                                }
                                                v927 = v1333;
                                              }
                                            }
                                            v1333 = v927;
                                            goto LABEL_1229;
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                        v837 = (unsigned int *)v1325;
                        goto LABEL_1154;
                      }
LABEL_1066:
                      if ( v10 < 0 )
                        goto LABEL_1035;
                      goto LABEL_1067;
                    }
                  }
                }
                v10 = -1073741811;
                v1320 = -1073741811;
                goto LABEL_1066;
              }
LABEL_1049:
              v1318 = v769;
              v814 = GetProcessHeap();
              HeapFree(v814, 0, jj);
              goto LABEL_1051;
            }
          }
          v1322 = v813;
          goto LABEL_1049;
        }
      }
    }
    v1322 = v806;
    goto LABEL_1049;
  }
  v10 = -805306345;
LABEL_1034:
  v1320 = v10;
LABEL_1035:
  v802 = v1319;
LABEL_1234:
  v946 = v1317;
LABEL_1235:
  if ( v946 )
    goto LABEL_1236;
LABEL_1237:
  v948 = v1322;
  if ( v1322 )
  {
    v1331 = *((_QWORD *)v1322 + 1);
    if ( v1331 )
    {
      v949 = GetProcessHeap();
      HeapFree(v949, 0, (LPVOID)v1331);
      v948 = v1322;
      *((_QWORD *)v1322 + 1) = 0;
    }
    v1331 = v948[3];
    if ( v1331 )
    {
      v950 = GetProcessHeap();
      HeapFree(v950, 0, (LPVOID)v1331);
      v948 = v1322;
      *((_QWORD *)v1322 + 3) = 0;
    }
    v1331 = v948[5];
    if ( v1331 )
    {
      v951 = GetProcessHeap();
      HeapFree(v951, 0, (LPVOID)v1331);
      *((_QWORD *)v1322 + 5) = 0;
    }
    v952 = GetProcessHeap();
    HeapFree(v952, 0, v1322);
  }
  if ( v1341 )
  {
    v953 = GetProcessHeap();
    HeapFree(v953, 0, (LPVOID)v1341);
  }
  if ( v802 )
  {
    v954 = GetProcessHeap();
    HeapFree(v954, 0, v802);
  }
  v955 = v1325;
  if ( v1325 )
  {
    v1331 = *((_QWORD *)v1325 + 1);
    if ( v1331 )
    {
      v956 = GetProcessHeap();
      HeapFree(v956, 0, (LPVOID)v1331);
      v955[1] = 0;
    }
    v1331 = v955[3];
    if ( v1331 )
    {
      v957 = GetProcessHeap();
      HeapFree(v957, 0, (LPVOID)v1331);
      v955[3] = 0;
    }
    v1331 = v955[5];
    if ( v1331 )
    {
      v958 = GetProcessHeap();
      HeapFree(v958, 0, (LPVOID)v1331);
      v955[5] = 0;
    }
    v959 = GetProcessHeap();
    HeapFree(v959, 0, v955);
  }
  v960 = v1333;
  if ( v1333 )
  {
    v961 = GetProcessHeap();
    HeapFree(v961, 0, v960);
  }
LABEL_1259:
  if ( v10 < 0 )
    goto LABEL_1263;
  if ( !*(_DWORD *)Size )
  {
    v10 = -1073425151;
    goto LABEL_1262;
  }
  if ( !v1336 )
  {
    v327 = v1318;
    v10 = -1073741811;
    v1320 = -1073741811;
    goto LABEL_847;
  }
  v1330 = (SIZE_T)v1336;
  v962 = sub_180006240(v1336, 4, &v1330);
  v327 = v1318;
  v10 = v962;
  v1320 = v962;
  v1336 = v964;
  if ( v962 < 0 )
    goto LABEL_847;
  v966 = (int *)v1330;
  if ( !*v964 )
    v966 = 0;
  if ( *v964 != 4 )
    goto LABEL_1319;
  v10 = *v966;
  v1320 = v10;
  if ( v10 == -805306333 )
  {
    *(_DWORD *)&Size[4] = -2147024774;
    goto LABEL_1274;
  }
  *(_DWORD *)&Size[4] = v10;
  if ( v10 == -2147024774 || v10 >= 0 )
  {
LABEL_1274:
    v1336 = v964;
    if ( v965 != 6 )
      goto LABEL_1275;
    v1316 = v963;
    for ( i13 = 0; !i13; i13 = v969 + 1 )
    {
      v1320 = sub_180006240(v963, 4, &v1316);
      v10 = v1320;
      if ( v1320 < 0 )
        goto LABEL_847;
      v1320 = sub_180006240(v1316, v968, &v1316);
      v10 = v1320;
      if ( v1320 < 0 )
        goto LABEL_847;
      v963 = v1316;
    }
    v1320 = sub_180006240(v963, 4, &v1316);
    v10 = v1320;
    if ( v1320 < 0 )
      goto LABEL_847;
    v972 = (size_t *)v1316;
    if ( !v971 )
      v972 = 0;
    if ( v971 == 8 )
    {
      v1336 = v970;
      if ( !v970 )
        goto LABEL_1308;
      v973 = *v972;
      v974 = v970;
      v1316 = v970;
      v975 = 0;
      v1331 = v973;
      while ( v975 < 2 )
      {
        v1320 = sub_180006240(v974, 4, &v1316);
        v10 = v1320;
        if ( v1320 < 0 )
          goto LABEL_847;
        v1320 = sub_180006240(v1316, v976, &v1316);
        v10 = v1320;
        if ( v1320 < 0 )
          goto LABEL_847;
        v974 = v1316;
        v975 = v977 + 1;
      }
      v1320 = sub_180006240(v974, 4, &v1316);
      v10 = v1320;
      if ( v1320 < 0 )
        goto LABEL_847;
      v980 = (int *)v1316;
      if ( !v979 )
        v980 = 0;
      if ( v979 == 4 )
      {
        v1336 = v978;
        if ( !v978 )
        {
          v10 = -1073741811;
          v1320 = -1073741811;
          goto LABEL_847;
        }
        v981 = *v980;
        v982 = v978;
        v983 = *(_DWORD *)&Size[4];
        v984 = 0;
        v1343 = (SIZE_T)v978;
        *(_DWORD *)Size = v981;
        while ( 1 )
        {
          *(_DWORD *)&Size[4] = v983;
          if ( v984 >= 3 )
            break;
          if ( v982 + 1 < v982 )
          {
            v10 = -1073741675;
            goto LABEL_1320;
          }
          v985 = *v982;
          v1336 = v978;
          *(_DWORD *)&Size[4] = v983;
          v1343 = (SIZE_T)(v982 + 1);
          v1320 = sub_180006240(v982 + 1, v985, &v1343);
          v10 = v1320;
          if ( v1320 < 0 )
            goto LABEL_847;
          v982 = (unsigned int *)v1343;
          v984 = v986 + 1;
          v1336 = v978;
        }
        v1320 = sub_180006240(v982, 4, &v1343);
        v10 = v1320;
        if ( v1320 < 0 )
          goto LABEL_847;
        if ( !v988 )
        {
          v1330 = 0;
LABEL_1310:
          v989 = v987;
          v990 = 0;
          v1316 = v987;
          while ( v990 < 4 )
          {
            LODWORD(v1315) = *v989;
            v1320 = sub_180006240(v989, 4, &v1316);
            v10 = v1320;
            if ( v1320 < 0 )
              goto LABEL_847;
            v1320 = sub_180006240(v1316, (unsigned int)v1315, &v1316);
            v10 = v1320;
            if ( v1320 < 0 )
              goto LABEL_847;
            v989 = v1316;
            v990 = v991 + 1;
          }
          v1320 = sub_180006240(v989, 4, &v1316);
          v10 = v1320;
          if ( v1320 >= 0 )
          {
            v994 = v1316;
            if ( !v993 )
              v994 = 0;
            if ( v993 == 4 )
            {
              v1336 = v992;
              if ( !v992 )
              {
                v10 = -1073741811;
                goto LABEL_1276;
              }
              v995 = v992;
              LODWORD(v1315) = *v994;
              v996 = 0;
              v1316 = v992;
              while ( v996 < 5 )
              {
                v1320 = sub_180006240(v995, 4, &v1316);
                v10 = v1320;
                if ( v1320 < 0 )
                  goto LABEL_850;
                v1320 = sub_180006240(v1316, v997, &v1316);
                v10 = v1320;
                if ( v1320 < 0 )
                  goto LABEL_850;
                v995 = v1316;
                v996 = v998 + 1;
              }
              v1320 = sub_180006240(v995, 4, &v1316);
              v10 = v1320;
              if ( v1320 < 0 )
                goto LABEL_1276;
              v1001 = (int *)v1316;
              if ( !v999 )
                v1001 = 0;
              if ( v999 != 4 )
              {
                v10 = -1073741789;
                goto LABEL_1276;
              }
              if ( lpMem == (LPVOID)v1331 )
              {
                v13 = *v1001;
                v1364 = *(_DWORD *)Size;
                v1358 = v1315;
                if ( uBytes )
                {
                  if ( uBytes < (unsigned int)v1315 || uBytes < (unsigned int)v1000 )
                  {
                    v10 = -2147024774;
                    goto LABEL_1276;
                  }
                  memcpy(v1352, (const void *)v1330, v1000);
                }
                goto LABEL_848;
              }
LABEL_1275:
              v10 = -1073425151;
              goto LABEL_1276;
            }
            goto LABEL_1319;
          }
LABEL_847:
          if ( v10 < 0 )
            goto LABEL_850;
LABEL_848:
          v619 = *(_DWORD *)&Size[4];
          if ( !*(_DWORD *)&Size[4] )
            goto LABEL_850;
          goto LABEL_849;
        }
        if ( v987 )
        {
          v1330 = v1343;
          goto LABEL_1310;
        }
LABEL_1308:
        v10 = -1073741811;
LABEL_1320:
        v1320 = v10;
        goto LABEL_847;
      }
    }
LABEL_1319:
    v10 = -1073741789;
    goto LABEL_1320;
  }
LABEL_850:
  v1344[0] = 0;
  v1331 = v1344[1];
  if ( v1344[1] )
  {
    v644 = GetProcessHeap();
    HeapFree(v644, 0, (LPVOID)v1331);
    v1344[1] = 0;
  }
  if ( v1336 )
  {
    v645 = GetProcessHeap();
    HeapFree(v645, 0, v1336);
  }
  if ( v326 )
  {
    v646 = GetProcessHeap();
    HeapFree(v646, 0, v326);
  }
  if ( v327 )
  {
    v647 = GetProcessHeap();
    HeapFree(v647, 0, v327);
  }
  if ( v10 < 0 )
    goto LABEL_8;
  if ( v13 )
  {
    v648 = 0;
    v1325 = 0;
    *(_OWORD *)v1351 = 0;
    v649 = GetProcessHeap();
    v650 = HeapAlloc(v649, 8u, 0xA0u);
    v651 = v650;
    if ( !v650 )
      goto LABEL_861;
    *v650 = xmmword_180024150;
    v650[1] = xmmword_180024160;
    v650[2] = xmmword_180024170;
    v650[3] = xmmword_180024180;
    v650[4] = xmmword_180024190;
    v650[5] = xmmword_1800241A0;
    v650[6] = xmmword_1800241B0;
    v650[7] = xmmword_1800241C0;
    v650[8] = xmmword_1800241D0;
    v650[9] = xmmword_1800241E0;
    v1002 = GetProcessHeap();
    v1331 = (size_t)HeapAlloc(v1002, 8u, 8u);
    if ( !v1331 )
      goto LABEL_861;
    v648 = (void *)v1331;
    *(_QWORD *)v1331 = qword_180024090;
    v1331 = __rdtsc();
    *(_DWORD *)&Size[4] = 0;
    LODWORD(v1315) = 0;
    if ( (int)sub_180006270(4, 4, &v1315) < 0 )
      goto LABEL_861;
    if ( (int)sub_180006270(0, (unsigned int)v1315, &Size[4]) < 0 )
      goto LABEL_861;
    LODWORD(v1315) = v1003;
    if ( (int)sub_180006270(4, 160, &v1315) < 0 )
      goto LABEL_861;
    v1004 = sub_180006270(*(unsigned int *)&Size[4], (unsigned int)v1315, &Size[4]);
    if ( (v1005 | v1004) < 0 )
      goto LABEL_861;
    LODWORD(v1315) = 0;
    if ( (int)sub_180006270(4, 8, &v1315) < 0 )
      goto LABEL_861;
    v1006 = sub_180006270(*(unsigned int *)&Size[4], (unsigned int)v1315, &Size[4]);
    if ( (v1007 | v1006) < 0 )
      goto LABEL_861;
    LODWORD(v1315) = 0;
    if ( (int)sub_180006270(4, 8, &v1315) < 0 )
      goto LABEL_861;
    v1008 = sub_180006270(*(unsigned int *)&Size[4], (unsigned int)v1315, &Size[4]);
    if ( (v1009 | v1008) < 0 )
      goto LABEL_861;
    HIDWORD(v1351[0]) = *(_DWORD *)&Size[4];
    v1010 = *(_DWORD *)&Size[4];
    v1011 = GetProcessHeap();
    v1012 = HeapAlloc(v1011, 8u, v1010);
    v1013 = v1012;
    if ( !v1012 )
      goto LABEL_861;
    v1351[1] = (size_t)v1012;
    LODWORD(v1351[0]) = 0;
    v1346 = 0;
    LODWORD(v1347) = 0;
    v1330 = (SIZE_T)v1012;
    v1345 = 8;
    if ( (int)sub_180006240(v1012, 4, &v1347) < 0 || (unsigned __int64)(v1013 + 2) > v1351[1] + HIDWORD(v1351[0]) )
      goto LABEL_861;
    v1015 = v1347;
    *v1013 = 4;
    v1016 = v1345;
    *v1015 = 4;
    v1017 = 0;
    v1018 = ++LODWORD(v1351[0]);
    v1346 = 0;
    LODWORD(v1347) = 0;
    if ( v651 )
    {
      if ( !v1014 )
        goto LABEL_861;
    }
    else if ( v1014 )
    {
      goto LABEL_861;
    }
    v1019 = (unsigned int *)v1351[1];
    if ( v1351[1] )
    {
      v1330 = v1351[1];
      while ( 1 )
      {
        v1345 = v1017;
        if ( v1017 >= v1018 )
          break;
        v1020 = *v1019;
        LODWORD(v1315) = 0;
        if ( (int)sub_180006270(4, v1020, &v1315) < 0 || (int)sub_180006240(v1021, (unsigned int)v1315, &v1330) < 0 )
          goto LABEL_861;
        v1019 = (unsigned int *)v1330;
        v1017 = v1345 + 1;
      }
      if ( (int)sub_180006240(v1019, 4, &v1347) < 0
        || (unsigned __int64)v1022 + v1023 + 4 > v1351[1] + HIDWORD(v1351[0]) )
      {
        goto LABEL_861;
      }
      *v1022 = v1023;
      if ( v651 )
        memcpy(v1347, v651, v1023);
    }
    else
    {
      LODWORD(v1315) = 0;
      if ( (int)sub_180006270(4, v1014, &v1315) < 0
        || (int)sub_180006270(HIDWORD(v1351[0]), (unsigned int)v1315, (char *)v1351 + 4) < 0 )
      {
        goto LABEL_861;
      }
    }
    v1024 = ++LODWORD(v1351[0]);
    v1346 = 0;
    LODWORD(v1347) = 0;
    if ( !v1016 )
      goto LABEL_861;
    v1025 = (unsigned int *)v1351[1];
    if ( v1351[1] )
    {
      v1330 = v1351[1];
      for ( i14 = 0; i14 < v1024; i14 = v1029 + 1 )
      {
        v1027 = *v1025;
        LODWORD(v1315) = 0;
        if ( (int)sub_180006270(4, v1027, &v1315) < 0 || (int)sub_180006240(v1028, (unsigned int)v1315, &v1330) < 0 )
          goto LABEL_861;
        v1025 = (unsigned int *)v1330;
      }
      if ( (int)sub_180006240(v1025, 4, &v1347) < 0
        || (unsigned __int64)v1030 + v1016 + 4 > v1351[1] + HIDWORD(v1351[0]) )
      {
        goto LABEL_861;
      }
      *v1030 = v1016;
      memcpy(v1347, v648, v1016);
    }
    else
    {
      LODWORD(v1315) = 0;
      if ( (int)sub_180006270(4, v1016, &v1315) < 0
        || (int)sub_180006270(HIDWORD(v1351[0]), (unsigned int)v1315, (char *)v1351 + 4) < 0 )
      {
        goto LABEL_861;
      }
    }
    v1031 = (unsigned int *)v1351[1];
    v1032 = ++LODWORD(v1351[0]);
    v1346 = 0;
    LODWORD(v1347) = 0;
    if ( v1351[1] )
    {
      v1330 = v1351[1];
      for ( i15 = 0; i15 < v1032; i15 = v1036 + 1 )
      {
        v1034 = *v1031;
        LODWORD(v1315) = 0;
        if ( (int)sub_180006270(4, v1034, &v1315) < 0 || (int)sub_180006240(v1035, (unsigned int)v1315, &v1330) < 0 )
          goto LABEL_861;
        v1031 = (unsigned int *)v1330;
      }
      if ( (int)sub_180006240(v1031, 4, &v1347) < 0 || (unsigned __int64)(v1037 + 3) > v1351[1] + HIDWORD(v1351[0]) )
        goto LABEL_861;
      v1038 = v1347;
      v1039 = v1331;
      *v1037 = 8;
      *v1038 = v1039;
    }
    else
    {
      LODWORD(v1315) = 0;
      if ( (int)sub_180006270(4, 8, &v1315) < 0
        || (int)sub_180006270(HIDWORD(v1351[0]), (unsigned int)v1315, (char *)v1351 + 4) < 0 )
      {
        goto LABEL_861;
      }
    }
    ++LODWORD(v1351[0]);
    LODWORD(v1315) = 0;
    if ( (int)sub_180006270(4, 4, &v1315) < 0
      || (v1345 = v1315, LODWORD(v1315) = 0, (int)sub_180006270(v1040, v1041, &v1315) < 0)
      || (int)sub_180006270(v1042, (unsigned int)v1315, &v1345) < 0 )
    {
LABEL_861:
      v652 = v1325;
LABEL_862:
      v653 = (void *)v1351[1];
      v1351[0] = 0;
      if ( v1351[1] )
      {
        v654 = GetProcessHeap();
        HeapFree(v654, 0, v653);
        v1351[1] = 0;
      }
      if ( v652 )
      {
        v655 = GetProcessHeap();
        HeapFree(v655, 0, v652);
      }
      if ( v651 )
      {
        v656 = GetProcessHeap();
        HeapFree(v656, 0, v651);
      }
      if ( v648 )
      {
        v657 = GetProcessHeap();
        HeapFree(v657, 0, v648);
      }
      goto LABEL_870;
    }
    v1317 = 0;
    LODWORD(v1338) = 0;
    LODWORD(v1328) = v1345;
    v1331 = __rdtsc();
    v1357 = v1043;
    v1044 = sub_180006270(v1043, HIDWORD(v1351[0]), &v1357);
    if ( v1044 < 0 )
    {
      v1335 = v648;
      jj = v651;
    }
    else
    {
      v1047 = (v1357 + 7) & 0xFFFFFFF8;
      if ( v1047 < v1357 )
        goto LABEL_861;
      v1357 = (v1357 + 7) & 0xFFFFFFF8;
      v1048 = v1047;
      v1049 = GetProcessHeap();
      v1050 = (char *)HeapAlloc(v1049, 8u, v1048);
      v1051 = v1050;
      if ( !v1050 )
        goto LABEL_1683;
      v1052 = (int)v1328;
      v1341 = (SIZE_T)v1050;
      *(_DWORD *)v1050 = v1351[0];
      jj = v651;
      v1335 = v648;
      LODWORD(v1328) = v1052;
      *(_DWORD *)Size = sub_180006240(v1050, 4, &v1341);
      if ( *(int *)Size < 0
        || (v1054 = v1341,
            *(_DWORD *)v1341 = HIDWORD(v1351[0]),
            *(_DWORD *)Size = sub_180006240(v1054, 4, &v1341),
            *(int *)Size < 0) )
      {
        jj = v651;
        v1335 = v648;
        LODWORD(v1328) = v1053;
        v1055 = GetProcessHeap();
        HeapFree(v1055, 0, v1051);
        v1045 = v1317;
        v1044 = *(_DWORD *)Size;
        v1046 = (unsigned int)v1317;
      }
      else
      {
        *(_QWORD *)&v1051[v1357 - 8] = v1331;
        memcpy((void *)v1341, (const void *)v1351[1], HIDWORD(v1351[0]));
        v1046 = v1357;
        v1045 = v1051;
        v1044 = *(_DWORD *)Size;
        v1317 = v1051;
      }
    }
    v1322 = 0;
    v1319 = 0;
    v1056 = 0;
    v1359 = 0;
    v1057 = v1044 | 0x10000000;
    v1333 = 0;
    v1318 = 0;
    if ( v1057 < 0 )
    {
      v1149 = 0;
      goto LABEL_1658;
    }
    if ( !v1045 )
      goto LABEL_861;
    v1341 = v1046;
    if ( !v1046 || (v1343 = v1046 + 8LL, (v1348 = sub_1800010C0(v1343)) == 0) )
    {
      v1286 = v1317;
      v1149 = 0;
      v1339 = -805306367;
      goto LABEL_1660;
    }
    v1058 = v1341;
    v1059 = 0;
    v1060 = 0;
    v1316 = 0;
    uBytes_4 = 0;
    if ( v1341 )
    {
      do
        v1059 ^= *((_BYTE *)v1317 + v1060++);
      while ( v1060 < v1341 );
      uBytes_4 = v1059;
    }
    v1336 = (LPVOID)0xC81ECB17B1B54A58LL;
    v1330 = (SIZE_T)v1317;
    v1061 = (unsigned __int8 *)v1317;
    dwBytes = v1348;
    v1062 = v1341 & 7;
    if ( (v1341 & 7) != 0 )
    {
      *(_DWORD *)Size = 0;
      LODWORD(v1334) = 0;
      v1063 = 0;
      v1064 = 0;
      v1065 = 0;
      do
      {
        v1066 = *v1061++;
        LODWORD(v1315) = 8 * v1063;
        if ( v1063 >= 4 )
          v1064 |= v1066 << (56 - v1315);
        else
          v1065 |= v1066 << (24 - v1315);
        ++v1063;
      }
      while ( (int)v1063 < (int)v1062 );
      LODWORD(v1334) = v1065;
      v1067 = v1065;
      v1056 = v1333;
      *(_DWORD *)Size = v1064;
      v1330 = (SIZE_T)v1061;
      v1335 = v648;
      jj = v651;
      LODWORD(v1315) = 0;
      v1068 = v1064 ^ 0x42F6B18D;
      v1069 = v1067 ^ 0xB17A307A;
      v1070 = v1069;
      v1071 = v1064 ^ 0x42F6B18D;
      if ( (v1341 & 7) != 0 )
      {
        v1072 = (_BYTE *)dwBytes;
        v1073 = v1315;
        do
        {
          v1331 = (size_t)(v1072 + 1);
          if ( v1073 >= 4 )
          {
            v1071 = __ROR4__(v1071, 24);
            v1074 = v1071;
          }
          else
          {
            v1070 = __ROR4__(v1070, 24);
            v1074 = v1070;
          }
          *v1072 = v1074;
          ++v1073;
          v1072 = (_BYTE *)v1331;
        }
        while ( (int)v1073 < (int)v1062 );
        dwBytes = v1331;
        v1059 = uBytes_4;
      }
      if ( v1062 <= 4 )
      {
        v1075 = 0;
        if ( v1062 < 4 )
          v1069 = v1069 >> (8 * (4 - v1062)) << (8 * (4 - v1062));
      }
      else
      {
        v1075 = v1068 >> (8 * (8 - v1062)) << (8 * (8 - v1062));
      }
    }
    else
    {
      v1069 = 0;
      LODWORD(v1334) = 0;
      v1075 = -1;
      *(_DWORD *)Size = 0;
    }
    if ( v1058 >> 3 )
    {
      v1076 = (unsigned __int8 *)v1330;
      v1077 = v1058 >> 3;
      v1078 = (_BYTE *)dwBytes;
      v1079 = v1334;
      v1080 = WORD2(v1336);
      *(_DWORD *)&Size[4] = 19032;
      v1345 = WORD1(v1336);
      LODWORD(v1315) = HIWORD(v1336);
      v1081 = *(_DWORD *)Size;
      v1346 = 0;
      do
      {
        v1082 = v1076[1];
        v1083 = *v1076;
        v1084 = v1076[4];
        v1076 += 8;
        v1085 = *(v1076 - 5) | ((*(v1076 - 6) | ((v1082 | (v1083 << 8)) << 8)) << 8);
        v1086 = *(v1076 - 1) | ((*(v1076 - 2) | ((*(v1076 - 3) | (v1084 << 8)) << 8)) << 8);
        v1087 = v1069 ^ v1085 ^ ((v1075 ^ v1086) - *(_DWORD *)&Size[4]);
        v1088 = __ROR4__(v1087, 15);
        v1089 = HIDWORD(v1336) ^ v1087;
        v1090 = v1075 ^ v1086 ^ (__ROR4__(v1089, 7) + WORD1(v1336) * v1088);
        v1091 = v1089 ^ (v1080 * __ROR4__(v1090 - 1313519016, 9) - __ROR4__(v1090, 10));
        v1092 = v1090 ^ (__ROR4__(v1091, 27) + HIWORD(v1336) * __ROR4__(v1080 ^ v1091, 28));
        v1093 = v1091 ^ (HIDWORD(v1336) - (v1092 ^ 0xB1B54A58));
        v1094 = v1092 ^ (WORD1(v1336) * (v1093 - *(_DWORD *)&Size[4]) - (v1093 >> 6));
        v1095 = v1093 ^ (*(_DWORD *)&Size[4] * (v1080 ^ __ROR4__(v1094, 15)));
        v1096 = v1094 ^ (v1080 * (HIWORD(v1336) + __ROR4__(~v1095, 3)));
        v1097 = v1095 ^ (v1096 - HIDWORD(v1336) - *(_DWORD *)&Size[4]);
        v1098 = v1096 ^ (v1345 * (v1315 ^ v1097)) ^ __ROR4__(v1097, 10);
        v1099 = v1097 ^ __ROR4__(v1098, 3) ^ (v1080 * __ROR4__(*(_DWORD *)&Size[4] ^ v1098, 26));
        v1100 = v1098 ^ (*(_DWORD *)&Size[4] * (__ROR4__(v1099, 15) - HIWORD(v1336)));
        v1101 = v1099
              ^ (*(_DWORD *)&Size[4] * (v1315 ^ v1100))
              ^ ((v1100 ^ (v1100 >> 14)) >> 1)
              ^ (*(_DWORD *)&Size[4] * (((unsigned __int64)(v1100 - v1080) >> 29) | (8 * (v1100 - v1080))));
        v1102 = v1100 ^ (WORD1(v1336) * (v1101 - v1080) - (v1101 >> 13));
        v1103 = v1101 ^ __ROR4__(v1102, 11) ^ (v1080 * __ROR4__(-1313519016 - v1102, 9));
        v1104 = v1102 ^ (v1103 + 1313519016 - HIWORD(v1336));
        v1105 = v1103 ^ (*(_DWORD *)&Size[4] * (v1345 ^ v1104) - __ROR4__(v1104, 7));
        v1106 = v1104 ^ (WORD1(v1336) * __ROR4__(v1105 ^ HIWORD(v1336), 28) - __ROR4__(v1105, 16));
        v1107 = v1105 ^ (__ROR4__(v1106, 4) + v1080 * __ROR4__(-1313519016 - v1106, 10));
        v1108 = v1106 ^ __ROR4__(v1107, 9) ^ (HIWORD(v1336) * __ROR4__(v1107 + 1313519016, 4));
        v1109 = v1107 ^ (*(_DWORD *)&Size[4] * __ROR4__(v1108 ^ HIDWORD(v1336), 24) - __ROR4__(v1108, 30));
        v1110 = v1108 ^ (WORD1(v1336) * __ROR4__(HIDWORD(v1336) - v1109, 11) - __ROR4__(v1109, 12));
        v1111 = WORD1(v1336) ^ v1110;
        v1112 = v1110 >> 8;
        v1113 = v1081 ^ HIDWORD(v1336) ^ v1110;
        v1081 = v1086;
        v1114 = v1109 ^ v1112 ^ (v1080 * v1111);
        v1069 = v1114 ^ v1079;
        v1078[3] = v1114 ^ v1079;
        v1075 = v1114 ^ v1113 ^ 0xB1B54A58;
        v1078[7] = v1075;
        LOBYTE(v1112) = __ROR4__(v1114 ^ v1079, 8);
        v1079 = v1085;
        v1078[2] = v1112;
        v1078[6] = __ROR4__(v1075, 8);
        v1078[1] = __ROR4__(v1069, 16);
        v1078[5] = __ROR4__(v1075, 16);
        *v1078 = __ROR4__(v1069, 24);
        v1078[4] = __ROR4__(v1075, 24);
        v1078 += 8;
        ++v1346;
      }
      while ( v1346 < v1077 );
      v1059 = uBytes_4;
      v10 = v1320;
      v8 = 4;
      v651 = jj;
      v648 = v1335;
      v1056 = v1333;
      v1058 = v1341;
    }
    *(_QWORD *)(v1348 + v1058) = v1059;
    v1115 = GetProcessHeap();
    v1116 = HeapAlloc(v1115, 8u, 0x30u);
    jj = v1116;
    if ( !v1116 )
    {
      *(_DWORD *)&Size[4] = -1073741801;
LABEL_1436:
      v1117 = (const void **)v1322;
      goto LABEL_1437;
    }
    v1124 = v1343;
    *v1116 = v1343;
    v1125 = GetProcessHeap();
    v1126 = HeapAlloc(v1125, 8u, v1124);
    v1127 = v1317;
    v1128 = v1126;
    v1129 = v1126 == 0;
    v1130 = (int)v1328;
    if ( !v1129 )
    {
      *((_QWORD *)jj + 1) = v1128;
      memcpy(v1128, (const void *)v1348, (unsigned int)v1343);
      *((_DWORD *)jj + 4) = 160;
      v1131 = GetProcessHeap();
      v1132 = HeapAlloc(v1131, 8u, 0xA0u);
      v1133 = jj;
      if ( v1132 )
      {
        *((_QWORD *)jj + 3) = v1132;
        *v1132 = xmmword_1800240A0;
        v1132[1] = xmmword_1800240B0;
        v1132[2] = xmmword_1800240C0;
        v1132[3] = xmmword_1800240D0;
        v1132[4] = xmmword_1800240E0;
        v1132[5] = xmmword_1800240F0;
        v1132[6] = xmmword_180024100;
        v1132[7] = xmmword_180024110;
        v1132[8] = xmmword_180024120;
        v1132[9] = xmmword_180024130;
        v1133[8] = 8;
        v1134 = GetProcessHeap();
        v1135 = HeapAlloc(v1134, 8u, 8u);
        if ( v1135 )
        {
          v1141 = jj;
          *((_QWORD *)jj + 5) = v1135;
          *v1135 = qword_180024140;
          v1316 = v1141;
          *(_DWORD *)&Size[4] = 0;
          v1317 = v1127;
          goto LABEL_1459;
        }
        v1133 = jj;
      }
      jj = v1133;
      v1130 = (int)v1328;
    }
    LODWORD(v1328) = v1130;
    v1317 = v1127;
    v1136 = jj;
    *(_DWORD *)&Size[4] = -1073741801;
    v1331 = *((_QWORD *)jj + 1);
    if ( v1331 )
    {
      v1137 = GetProcessHeap();
      HeapFree(v1137, 0, (LPVOID)v1331);
      v1136[1] = 0;
    }
    v1331 = v1136[3];
    if ( v1331 )
    {
      v1138 = GetProcessHeap();
      HeapFree(v1138, 0, (LPVOID)v1331);
      v1136[3] = 0;
    }
    v1331 = v1136[5];
    if ( v1331 )
    {
      v1139 = GetProcessHeap();
      HeapFree(v1139, 0, (LPVOID)v1331);
      v1136[5] = 0;
    }
    v1140 = GetProcessHeap();
    HeapFree(v1140, 0, v1136);
    if ( *(int *)&Size[4] < 0 )
      goto LABEL_1436;
LABEL_1459:
    v1117 = (const void **)v1316;
    v1316 = 0;
LABEL_1437:
    v1322 = v1117;
    v1118 = GetProcessHeap();
    HeapFree(v1118, 0, (LPVOID)v1348);
    v1119 = v1316;
    if ( v1316 )
    {
      v1331 = *((_QWORD *)v1316 + 1);
      if ( v1331 )
      {
        v1120 = GetProcessHeap();
        HeapFree(v1120, 0, (LPVOID)v1331);
        v1119 = v1316;
        *((_QWORD *)v1316 + 1) = 0;
      }
      v1331 = v1119[3];
      if ( v1331 )
      {
        v1121 = GetProcessHeap();
        HeapFree(v1121, 0, (LPVOID)v1331);
        v1119 = v1316;
        *((_QWORD *)v1316 + 3) = 0;
      }
      v1331 = v1119[5];
      if ( v1331 )
      {
        v1122 = GetProcessHeap();
        HeapFree(v1122, 0, (LPVOID)v1331);
        *((_QWORD *)v1316 + 5) = 0;
      }
      v1123 = GetProcessHeap();
      HeapFree(v1123, 0, v1316);
    }
    else
    {
      v1322 = v1117;
    }
    v1142 = *(_DWORD *)&Size[4] | 0x10000000;
    if ( *(int *)&Size[4] < 0 )
      goto LABEL_1487;
    v1143 = *(unsigned int *)v1117;
    LODWORD(v1315) = 0;
    LODWORD(v1327) = 4;
    *(_DWORD *)&Size[4] = sub_180006270(4, v1143, &v1327);
    if ( *(int *)&Size[4] < 0 )
      goto LABEL_1482;
    *(_DWORD *)&Size[4] = sub_180006270((unsigned int)v1327, 4, &v1327);
    if ( *(int *)&Size[4] < 0 )
      goto LABEL_1482;
    v1144 = *((unsigned int *)v1117 + 4);
    v1330 = (SIZE_T)(v1117 + 2);
    *(_DWORD *)&Size[4] = sub_180006270((unsigned int)v1327, v1144, &v1327);
    if ( *(int *)&Size[4] < 0 )
      goto LABEL_1482;
    *(_DWORD *)&Size[4] = sub_180006270((unsigned int)v1327, 4, &v1327);
    if ( *(int *)&Size[4] < 0 )
      goto LABEL_1482;
    v1145 = *((unsigned int *)v1117 + 8);
    v1346 = (SIZE_T)(v1117 + 4);
    *(_DWORD *)&Size[4] = sub_180006270((unsigned int)v1327, v1145, &v1327);
    if ( *(int *)&Size[4] < 0 )
      goto LABEL_1482;
    v1322 = v1117;
    v1146 = v1327;
    v1147 = GetProcessHeap();
    jj = HeapAlloc(v1147, 8u, v1146);
    v1148 = jj;
    if ( !jj )
    {
      v1339 = -805306345;
LABEL_1469:
      v1149 = v1318;
      goto LABEL_1659;
    }
    v1117 = (const void **)v1322;
    v1150 = v1317;
    *(_DWORD *)jj = *(_DWORD *)v1322;
    v1317 = v1150;
    v1316 = v1148;
    *(_DWORD *)&Size[4] = sub_180006240(v1148, 4, &v1316);
    if ( *(int *)&Size[4] < 0 )
    {
      v1317 = v1152;
      LODWORD(v1328) = v1153;
      jj = v1151;
    }
    else
    {
      memcpy(v1316, v1117[1], *(unsigned int *)v1117);
      *(_DWORD *)&Size[4] = sub_180006240(v1316, *(unsigned int *)v1117, &v1316);
      if ( *(int *)&Size[4] >= 0 )
      {
        v1154 = v1316;
        *(_DWORD *)v1316 = *(_DWORD *)v1330;
        *(_DWORD *)&Size[4] = sub_180006240(v1154, 4, &v1316);
        if ( *(int *)&Size[4] >= 0 )
        {
          memcpy(v1316, v1117[3], *v1155);
          *(_DWORD *)&Size[4] = sub_180006240(v1316, *(unsigned int *)v1330, &v1316);
          if ( *(int *)&Size[4] >= 0 )
          {
            v1156 = v1316;
            *(_DWORD *)v1316 = *(_DWORD *)v1346;
            *(_DWORD *)&Size[4] = sub_180006240(v1156, 4, &v1316);
            if ( *(int *)&Size[4] >= 0 )
            {
              memcpy(v1316, v1117[5], *v1157);
              v1158 = sub_180006240(v1316, *(unsigned int *)v1346, &v1316);
              *(_DWORD *)&Size[4] = v1158;
              v1322 = v1117;
              if ( v1158 >= 0 )
              {
                v1359 = jj;
                LODWORD(v1315) = v1327;
LABEL_1483:
                v1142 = v1158 | 0x10000000;
                if ( v1142 < 0 )
                  goto LABEL_1487;
                v1361 = 8;
                v1142 = sub_180006270(8, (unsigned int)v1328, &v1361) | 0x10000000;
                if ( v1142 < 0 )
                  goto LABEL_1487;
                v1161 = (v1361 + 7) & 0xFFFFFFF8;
                if ( (unsigned int)v1161 < v1361 )
                {
                  v1142 = -1073741675;
LABEL_1487:
                  v1339 = v1142;
                  goto LABEL_1469;
                }
                v1365 = (v1361 + 7) & 0xFFFFFFF8;
                v1142 = sub_180006270(v1161, v1160, &v1365);
                if ( v1142 < 0 )
                  goto LABEL_1487;
                v1163 = (unsigned int *)v1351[1];
                jj = v651;
                v1335 = v648;
                v1317 = v1162;
                v1322 = v1117;
                *(_DWORD *)Size = 0;
                if ( !v1351[1] )
                  goto LABEL_1498;
                v1322 = v1117;
                v1317 = v1162;
                v1335 = v648;
                jj = v651;
                if ( LODWORD(v1351[0]) <= 1 )
                  goto LABEL_1498;
                v1343 = v1351[1];
                for ( i16 = 0; !i16; i16 = v1166 + 1 )
                {
                  v1142 = sub_180006240(v1163, 4, &v1343);
                  if ( v1142 < 0 )
                    goto LABEL_1487;
                  v1142 = sub_180006240(v1343, v1165, &v1343);
                  if ( v1142 < 0 )
                    goto LABEL_1487;
                  v1163 = (unsigned int *)v1343;
                }
                v1167 = *v1163;
                v1142 = sub_180006240(v1163, 4, &v1343);
                if ( v1142 < 0 )
                  goto LABEL_1487;
                v1168 = v1351[1];
                if ( !v1351[1] || LODWORD(v1351[0]) <= 2 )
                {
LABEL_1498:
                  v1142 = -1073741811;
                  goto LABEL_1487;
                }
                v1343 = v1351[1];
                for ( i17 = 0; i17 < 2; i17 = v1173 + 1 )
                {
                  v1142 = sub_180006240(v1168, 4, &v1343);
                  if ( v1142 < 0 )
                    goto LABEL_1487;
                  v1142 = sub_180006240(v1343, v1172, &v1343);
                  if ( v1142 < 0 )
                    goto LABEL_1487;
                  v1168 = v1343;
                }
                v1142 = sub_180006240(v1168, 4, &v1343);
                if ( v1142 < 0 )
                  goto LABEL_1487;
                *(_DWORD *)Size = v1174;
                *(_DWORD *)&Size[4] = 4;
                v1142 = sub_180006270(4, v1365, &Size[4]);
                if ( v1142 < 0 )
                  goto LABEL_1487;
                v1142 = sub_180006270(*(unsigned int *)&Size[4], 4, &Size[4]);
                if ( v1142 < 0 )
                  goto LABEL_1487;
                v1142 = sub_180006270(*(unsigned int *)&Size[4], v1167, &Size[4]);
                if ( v1142 < 0 )
                  goto LABEL_1487;
                v1142 = sub_180006270(*(unsigned int *)&Size[4], 4, &Size[4]);
                if ( v1142 < 0 )
                  goto LABEL_1487;
                v1142 = sub_180006270(*(unsigned int *)&Size[4], v1175, &Size[4]);
                if ( v1142 < 0 )
                  goto LABEL_1487;
                *(_DWORD *)Size = *(_DWORD *)&Size[4];
                if ( *(_DWORD *)&Size[4] > 0x400000u )
                {
                  v1142 = -2147418113;
                  goto LABEL_1487;
                }
                v1169 = *(_DWORD *)&Size[4];
                v1170 = GetProcessHeap();
                v1056 = HeapAlloc(v1170, 8u, v1169);
                if ( !v1056 )
                {
                  v1339 = -805306345;
                  v1149 = 0;
                  goto LABEL_1659;
                }
                v1371 = 0;
                v1379 = 0;
                v1380 = 0;
                if ( !v1359 )
                {
                  v1339 = -2147024809;
                  goto LABEL_1469;
                }
                LODWORD(v1380) = v1315;
                *(_QWORD *)&v1379 = v1359;
                *(_QWORD *)((char *)&v1380 + 4) = *(unsigned int *)Size;
                *((_QWORD *)&v1379 + 1) = v1056;
                if ( GetModuleHandleExW(1u, L"ntdll.dll", &v1371)
                  && (v1177 = (NTSTATUS (__stdcall *)(SYSTEM_INFORMATION_CLASS, PVOID, ULONG, PULONG))GetProcAddress(v1371, "NtQuerySystemInformation")) != 0 )
                {
                  v1142 = ((__int64 (__fastcall *)(__int64, __int128 *))v1177)(134, &v1379) | 0x10000000;
                  if ( v1142 >= 0 )
                  {
                    v1178 = DWORD1(v1380);
                    goto LABEL_1529;
                  }
                }
                else
                {
                  v1142 = GetLastError();
                  v1176 = v1142 < 0;
                  if ( v1142 > 0 )
                  {
                    v1142 = (unsigned __int16)v1142 | 0x80070000;
                    v1176 = v1142 < 0;
                  }
                  if ( !v1176 )
                  {
                    v1339 = -2147467259;
                    goto LABEL_1469;
                  }
                }
                if ( v1142 == -805306333 )
                {
                  v1339 = -2147024774;
                  goto LABEL_1469;
                }
                if ( v1142 < 0 )
                  goto LABEL_1487;
                v1178 = *(_DWORD *)Size;
LABEL_1529:
                *(_DWORD *)&Size[4] = 0;
                v1336 = v1056;
                if ( v1178 < 4 )
                {
LABEL_1530:
                  v1339 = -805306306;
                  goto LABEL_1469;
                }
                v1179 = (unsigned int)*v1056;
                LODWORD(v1315) = *v1056;
                v1180 = sub_180006240(v1056, 4, &v1336);
                if ( v1180 < 0 )
                  goto LABEL_1582;
                v1180 = sub_180006270(0, 4, &Size[4]);
                if ( v1180 < 0 )
                  goto LABEL_1582;
                if ( v1181 - *(_DWORD *)&Size[4] < (unsigned int)v1179 )
                  goto LABEL_1530;
                v1346 = (SIZE_T)v1336;
                v1330 = v1179;
                v1180 = sub_180006240(v1336, (unsigned int)v1179, &v1336);
                if ( v1180 < 0 )
                  goto LABEL_1582;
                v1180 = sub_180006270(*(unsigned int *)&Size[4], (unsigned int)v1179, &Size[4]);
                if ( v1180 < 0 )
                  goto LABEL_1582;
                if ( (unsigned int)(v1182 - *(_DWORD *)&Size[4]) < 4 )
                  goto LABEL_1530;
                v1345 = *(_DWORD *)v1336;
                v1180 = sub_180006240(v1336, 4, &v1336);
                if ( v1180 < 0 )
                  goto LABEL_1582;
                v1180 = sub_180006270(*(unsigned int *)&Size[4], 4, &Size[4]);
                if ( v1180 < 0 )
                  goto LABEL_1582;
                if ( v1183 - *(_DWORD *)&Size[4] < (unsigned int)v1184 )
                  goto LABEL_1530;
                v1348 = (SIZE_T)v1336;
                dwBytes = v1184;
                v1180 = sub_180006240(v1336, (unsigned int)v1184, &v1336);
                if ( v1180 < 0 )
                  goto LABEL_1582;
                v1180 = sub_180006270(*(unsigned int *)&Size[4], v1185, &Size[4]);
                if ( v1180 < 0 )
                  goto LABEL_1582;
                if ( (unsigned int)(v1186 - *(_DWORD *)&Size[4]) < 4 )
                  goto LABEL_1530;
                *(_DWORD *)Size = *(_DWORD *)v1336;
                v1180 = sub_180006240(v1336, 4, &v1336);
                if ( v1180 < 0 )
                  goto LABEL_1582;
                v1180 = sub_180006270(*(unsigned int *)&Size[4], 4, &Size[4]);
                if ( v1180 < 0 )
                  goto LABEL_1582;
                if ( v1187 - *(_DWORD *)&Size[4] < v1188 )
                  goto LABEL_1530;
                v1180 = sub_180006270(*(unsigned int *)&Size[4], v1188, &Size[4]);
                if ( v1180 < 0 )
                {
LABEL_1582:
                  v1194 = v1322;
                  v1209 = (unsigned int *)v1319;
                  v1333 = v1056;
                  goto LABEL_1583;
                }
                if ( v1189 != *(_DWORD *)&Size[4] || (unsigned int)(v1190 + v1191 + v1179) + 12LL != v1189 )
                  goto LABEL_1530;
                v1192 = GetProcessHeap();
                v1316 = HeapAlloc(v1192, 8u, 0x30u);
                v1193 = v1316;
                if ( !v1316 )
                {
                  v1339 = -805306345;
                  v1319 = 0;
                  v1149 = 0;
                  goto LABEL_1659;
                }
                v1194 = v1322;
                jj = v651;
                v1335 = v648;
                v1342 = 0;
                if ( v1346 )
                {
                  *(_DWORD *)v1316 = v1315;
                  v1195 = GetProcessHeap();
                  v1196 = HeapAlloc(v1195, 8u, v1330);
                  if ( !v1196 )
                  {
LABEL_1562:
                    v1203 = v1316;
                    *(_DWORD *)&Size[4] = -1073741801;
                    v1333 = v1056;
                    v1331 = *((_QWORD *)v1316 + 1);
                    if ( v1331 )
                    {
                      v1204 = GetProcessHeap();
                      HeapFree(v1204, 0, (LPVOID)v1331);
                      v1203 = v1316;
                      *((_QWORD *)v1316 + 1) = 0;
                    }
                    v1331 = v1203[3];
                    if ( v1331 )
                    {
                      v1205 = GetProcessHeap();
                      HeapFree(v1205, 0, (LPVOID)v1331);
                      v1203 = v1316;
                      *((_QWORD *)v1316 + 3) = 0;
                    }
                    v1331 = v1203[5];
                    if ( v1331 )
                    {
                      v1206 = GetProcessHeap();
                      HeapFree(v1206, 0, (LPVOID)v1331);
                      *((_QWORD *)v1316 + 5) = 0;
                    }
                    v1207 = GetProcessHeap();
                    HeapFree(v1207, 0, v1316);
                    v1208 = (size_t *)v1342;
                    goto LABEL_1572;
                  }
                  *((_QWORD *)v1316 + 1) = v1196;
                  *(_DWORD *)&Size[4] = 0;
                  memcpy(v1196, (const void *)v1346, v1330);
                  v1193 = v1316;
                }
                else
                {
                  *(_DWORD *)v1316 = 0;
                  *(_DWORD *)&Size[4] = 0;
                  v1193[1] = 0;
                }
                if ( v1348 )
                {
                  *((_DWORD *)v1193 + 4) = v1345;
                  v1197 = GetProcessHeap();
                  v1198 = HeapAlloc(v1197, 8u, dwBytes);
                  v1199 = v1316;
                  if ( !v1198 )
                  {
LABEL_1561:
                    v1316 = v1199;
                    jj = v651;
                    v1335 = v648;
                    v1322 = v1194;
                    goto LABEL_1562;
                  }
                  *((_QWORD *)v1316 + 3) = v1198;
                  *(_DWORD *)&Size[4] = 0;
                  memcpy(v1198, (const void *)v1348, dwBytes);
                  v1193 = v1316;
                }
                else
                {
                  *((_DWORD *)v1193 + 4) = 0;
                  v1193[3] = 0;
                }
                if ( v1336 )
                {
                  v1200 = *(unsigned int *)Size;
                  *((_DWORD *)v1193 + 8) = *(_DWORD *)Size;
                  v1330 = v1200;
                  v1201 = GetProcessHeap();
                  v1202 = HeapAlloc(v1201, 8u, v1330);
                  v1199 = v1316;
                  if ( !v1202 )
                    goto LABEL_1561;
                  *((_QWORD *)v1316 + 5) = v1202;
                  *(_DWORD *)&Size[4] = 0;
                  memcpy(v1202, v1336, v1330);
                  v1193 = v1316;
                }
                else
                {
                  *((_DWORD *)v1193 + 8) = 0;
                  v1193[5] = 0;
                }
                v1208 = v1193;
                v1342 = v1193;
                v1333 = v1056;
                v1322 = v1194;
                v1335 = v648;
                jj = v651;
LABEL_1572:
                v1180 = *(_DWORD *)&Size[4];
                if ( *(int *)&Size[4] < 0 )
                {
                  v1209 = 0;
                  v1319 = 0;
                  if ( v1208 )
                  {
                    v1331 = v1208[1];
                    if ( v1331 )
                    {
                      v1210 = GetProcessHeap();
                      HeapFree(v1210, 0, (LPVOID)v1331);
                      v1208 = (size_t *)v1342;
                      *((_QWORD *)v1342 + 1) = 0;
                    }
                    v1331 = v1208[3];
                    if ( v1331 )
                    {
                      v1211 = GetProcessHeap();
                      HeapFree(v1211, 0, (LPVOID)v1331);
                      v1208 = (size_t *)v1342;
                      *((_QWORD *)v1342 + 3) = 0;
                    }
                    v1331 = v1208[5];
                    if ( v1331 )
                    {
                      v1212 = GetProcessHeap();
                      HeapFree(v1212, 0, (LPVOID)v1331);
                      *((_QWORD *)v1342 + 5) = 0;
                    }
                    v1213 = GetProcessHeap();
                    HeapFree(v1213, 0, v1342);
                    v1180 = *(_DWORD *)&Size[4];
                    v1209 = 0;
                    v1319 = 0;
                  }
                }
                else
                {
                  v1209 = (unsigned int *)v1208;
                  v1319 = v1208;
                }
LABEL_1583:
                v1339 = v1180 | 0x10000000;
                if ( v1180 < 0 )
                  goto LABEL_1469;
                if ( !v1209 || (v1341 = *((_QWORD *)v1209 + 1)) == 0 || !*v1209 )
                {
                  v1339 = -805306355;
                  goto LABEL_1469;
                }
                dwBytes = *v1209 - 8LL;
                v1318 = (LPVOID)sub_1800010C0(dwBytes);
                v1215 = v1318;
                if ( !v1318 )
                  goto LABEL_1615;
                v1216 = 0;
                v1217 = (unsigned __int8 *)v1341;
                uBytes_4 = 0;
                v1316 = (LPVOID)0x7F1137FAB69605ELL;
                v1330 = v1341;
                v1346 = (SIZE_T)v1318;
                v1218 = dwBytes & 7;
                if ( (dwBytes & 7) != 0 )
                {
                  v1356 = 0;
                  *(_DWORD *)Size = 0;
                  LODWORD(v1315) = 0;
                  v1219 = 0;
                  v1220 = 0;
                  v1221 = 0;
                  do
                  {
                    v1222 = *v1217++;
                    LODWORD(v1315) = 8 * v1219;
                    if ( v1219 >= 4 )
                      v1221 |= v1222 << (56 - v1315);
                    else
                      v1220 |= v1222 << (24 - v1315);
                    ++v1219;
                  }
                  while ( (int)v1219 < (int)v1218 );
                  *(_DWORD *)Size = v1220;
                  v1216 = uBytes_4;
                  v1356 = v1221;
                  v1215 = v1318;
                  v1223 = v1318;
                  v1330 = (SIZE_T)v1217;
                  v1333 = v1056;
                  v1322 = v1194;
                  v1335 = v648;
                  jj = v651;
                  v1224 = *(_DWORD *)Size ^ 0x92F65A5u;
                  LODWORD(v1315) = 0;
                  v1225 = v1356 ^ 0x699A899C;
                  v1214 = v1224;
                  v1226 = v1356 ^ 0x699A899C;
                  if ( (dwBytes & 7) != 0 )
                  {
                    v1227 = v1315;
                    do
                    {
                      v1331 = (size_t)(v1223 + 1);
                      if ( v1227 >= 4 )
                      {
                        v1226 = __ROR4__(v1226, 24);
                        v1228 = v1226;
                      }
                      else
                      {
                        v1214 = (unsigned int)__ROR4__(v1214, 24);
                        v1228 = v1214;
                      }
                      *v1223 = v1228;
                      ++v1227;
                      v1223 = (_BYTE *)v1331;
                    }
                    while ( (int)v1227 < (int)v1218 );
                    v1346 = v1331;
                    v1215 = v1318;
                  }
                  if ( v1218 <= 4 )
                  {
                    v1229 = 0;
                    if ( v1218 < 4 )
                      v1224 = (unsigned int)v1224 >> (8 * (4 - v1218)) << (8 * (4 - v1218));
                  }
                  else
                  {
                    v1229 = v1225 >> (8 * (8 - v1218)) << (8 * (8 - v1218));
                  }
                }
                else
                {
                  v1229 = 0;
                  *(_DWORD *)Size = 0;
                  v1224 = 0;
                }
                v1230 = dwBytes;
                if ( dwBytes >> 3 )
                {
                  v1231 = HIDWORD(v1316);
                  v1232 = dwBytes >> 3;
                  v1233 = WORD1(v1316);
                  v1234 = (_BYTE *)v1346;
                  v1235 = *(_DWORD *)Size;
                  v1236 = WORD2(v1316);
                  *(_DWORD *)&Size[4] = 24670;
                  v1237 = (unsigned __int8 *)v1330;
                  LODWORD(v1315) = WORD2(v1316);
                  v1348 = 0;
                  do
                  {
                    v1238 = *v1237;
                    v1239 = v1237[1];
                    v1240 = v1237[4];
                    v1237 += 8;
                    v1241 = *(v1237 - 5) | ((*(v1237 - 6) | (((v1238 << 8) | v1239) << 8)) << 8);
                    v1242 = v1224 ^ v1241;
                    v1243 = *(v1237 - 1) | ((*(v1237 - 2) | ((*(v1237 - 3) | (v1240 << 8)) << 8)) << 8);
                    v1244 = v1231 ^ v1224 ^ v1241 ^ v1229 ^ v1243 ^ 0xAB69605E;
                    v1245 = v1242 ^ (__ROR4__(v1244, 22) + v1236 * __ROR4__(v1244 + 1419157410, 27));
                    v1246 = v1244 ^ (v1233 * __ROR4__(v1231 + v1245, 9) - __ROR4__(v1245, 30));
                    v1247 = v1245 ^ (*(_DWORD *)&Size[4] * (v1246 - v1236) - (v1246 >> 13));
                    v1248 = v1246 ^ (HIWORD(v1316) * __ROR4__(v1233 ^ v1247, 26) - __ROR4__(v1247, 30));
                    v1249 = v1247 ^ (v1231 - (v1248 ^ 0xAB69605E));
                    v1250 = v1248 ^ (v1233 * (v1236 ^ v1249)) ^ __ROR4__(v1249, 6);
                    v1251 = v1249 ^ (__ROR4__(v1250, 30) + *(_DWORD *)&Size[4] * __ROR4__(v1231 + v1250, 15));
                    v1252 = v1250 ^ (HIWORD(v1316) * __ROR4__(v1251 + 1419157410, 14) - __ROR4__(v1251, 24));
                    v1253 = v1251 ^ __ROR4__(v1252, 10) ^ (v1315 * __ROR4__(v1252 ^ 0xAB69605E, 12));
                    v1254 = v1252 ^ (v1253 >> 10) ^ (WORD1(v1316) * (HIWORD(v1316) ^ v1253));
                    v1233 = WORD1(v1316);
                    v1255 = v1253 ^ (HIWORD(v1316) * (*(_DWORD *)&Size[4] + __ROR4__(~v1254, 5)));
                    v1256 = v1254 ^ (v1255 - HIWORD(v1316)) ^ 0xAB69605E;
                    v1236 = v1315;
                    v1257 = v1255 ^ ((v1256 >> 2) + v1315 * __ROR4__(HIWORD(v1316) ^ v1256, 30));
                    v1258 = v1256 ^ (__ROR4__(v1257, 25) + WORD1(v1316) * __ROR4__(v1257 - v1231, 6));
                    v1259 = v1257 ^ (*(_DWORD *)&Size[4] * (v1315 ^ v1258) + __ROR4__(v1258, 9));
                    v1260 = v1258 ^ (__ROR4__(v1259, 25) + HIWORD(v1316) * __ROR4__(WORD1(v1316) ^ v1259, 27));
                    v1261 = v1259 ^ v1260 ^ v1231 ^ 0xAB69605E;
                    v1262 = v1260 ^ (v1315 * (__ROR4__(v1261, 3) - WORD1(v1316)));
                    v1263 = v1261 ^ (*(_DWORD *)&Size[4] * __ROR4__(v1262 - v1231, 1) - __ROR4__(v1262, 6));
                    v1264 = v1262 ^ (__ROR4__(v1263, 18) + HIWORD(v1316) * __ROR4__(v1263 - 1419157410, 29));
                    v1265 = v1263 ^ (v1315 * __ROR4__(v1264 - 1419157410, 17) - __ROR4__(v1264, 14));
                    v1214 = v1264 ^ (v1265 >> 3) ^ (WORD1(v1316) * (*(_DWORD *)&Size[4] ^ v1265));
                    v1266 = v1235 ^ __ROR4__(v1214, 30) ^ (*(_DWORD *)&Size[4] * __ROR4__(v1214 ^ v1231, 28));
                    v1235 = v1241;
                    v1224 = v1265 ^ v1266;
                    v1267 = v1356;
                    v1234[3] = v1224;
                    v1229 = (unsigned int)v1214 ^ v1267;
                    v1234[7] = v1229;
                    v1234[2] = __ROR4__(v1224, 8);
                    v1234[6] = __ROR4__(v1229, 8);
                    v1234[1] = __ROR4__(v1224, 16);
                    v1234[5] = __ROR4__(v1229, 16);
                    *v1234 = __ROR4__(v1224, 24);
                    v1234[4] = __ROR4__(v1229, 24);
                    v1234 += 8;
                    v1356 = v1243;
                    ++v1348;
                  }
                  while ( v1348 < v1232 );
                  v1216 = uBytes_4;
                  v8 = 4;
                  v10 = v1320;
                  v651 = jj;
                  v648 = v1335;
                  v1056 = v1333;
                  v1215 = v1318;
                  v1230 = dwBytes;
                }
                for ( i18 = 0; i18 < v1230; ++i18 )
                  v1216 ^= v1215[i18];
                if ( v1216 != *(_QWORD *)(v1230 + v1341) )
                {
                  sub_180010DC8(v1215, v1214, v1224, v1229);
LABEL_1615:
                  v1339 = -805306367;
                  v1149 = 0;
                  goto LABEL_1659;
                }
                v1269 = v1319;
                *(_DWORD *)&Size[4] = 0;
                v1316 = v1215;
                if ( (unsigned int)v1230 < 4 )
                {
LABEL_1617:
                  v1270 = -1073741762;
LABEL_1655:
                  v1149 = v1318;
                  v1057 = v1270 | 0x10000000;
LABEL_1658:
                  v1339 = v1057;
LABEL_1659:
                  v1286 = v1317;
                  if ( !v1317 )
                  {
LABEL_1661:
                    v1288 = v1322;
                    if ( v1322 )
                    {
                      v1331 = *((_QWORD *)v1322 + 1);
                      if ( v1331 )
                      {
                        v1289 = GetProcessHeap();
                        HeapFree(v1289, 0, (LPVOID)v1331);
                        v1288[1] = 0;
                      }
                      v1331 = v1288[3];
                      if ( v1331 )
                      {
                        v1290 = GetProcessHeap();
                        HeapFree(v1290, 0, (LPVOID)v1331);
                        v1288[3] = 0;
                      }
                      v1331 = v1288[5];
                      if ( v1331 )
                      {
                        v1291 = GetProcessHeap();
                        HeapFree(v1291, 0, (LPVOID)v1331);
                        v1288[5] = 0;
                      }
                      v1292 = GetProcessHeap();
                      HeapFree(v1292, 0, v1288);
                    }
                    v1293 = v1359;
                    if ( v1359 )
                    {
                      v1294 = GetProcessHeap();
                      HeapFree(v1294, 0, v1293);
                    }
                    if ( v1056 )
                    {
                      v1295 = GetProcessHeap();
                      HeapFree(v1295, 0, v1056);
                    }
                    v1296 = v1319;
                    if ( v1319 )
                    {
                      v1297 = (void *)*((_QWORD *)v1319 + 1);
                      if ( v1297 )
                      {
                        v1298 = GetProcessHeap();
                        HeapFree(v1298, 0, v1297);
                        v1296[1] = 0;
                      }
                      v1299 = (void *)v1296[3];
                      if ( v1299 )
                      {
                        v1300 = GetProcessHeap();
                        HeapFree(v1300, 0, v1299);
                        v1296[3] = 0;
                      }
                      v1301 = (void *)v1296[5];
                      if ( v1301 )
                      {
                        v1302 = GetProcessHeap();
                        HeapFree(v1302, 0, v1301);
                        v1296[5] = 0;
                      }
                      v1303 = GetProcessHeap();
                      HeapFree(v1303, 0, v1296);
                    }
                    if ( v1149 )
                    {
                      v1304 = GetProcessHeap();
                      HeapFree(v1304, 0, v1149);
                    }
LABEL_1683:
                    if ( v1339 >= 0 )
                    {
                      v652 = v1325;
                      if ( (_DWORD)v1338 )
                      {
                        if ( v1325 )
                        {
                          v1330 = (SIZE_T)v1325;
                          if ( (int)sub_180006240(v1325, 4, &v1330) >= 0 )
                          {
                            v1306 = (int *)v1330;
                            if ( !*v652 )
                              v1306 = 0;
                            if ( *v652 == 4 && *v1306 >= 0 && v1305 > 1 )
                            {
                              v1307 = (SIZE_T)v652;
                              v1343 = (SIZE_T)v652;
                              for ( i19 = 0; !i19; i19 = v1310 + 1 )
                              {
                                if ( (int)sub_180006240(v1307, 4, &v1343) < 0
                                  || (int)sub_180006240(v1343, v1309, &v1343) < 0 )
                                {
                                  goto LABEL_862;
                                }
                                v1307 = v1343;
                              }
                              sub_180006240(v1307, 4, &v1343);
                            }
                          }
                        }
                      }
                      goto LABEL_862;
                    }
                    goto LABEL_861;
                  }
LABEL_1660:
                  v1287 = GetProcessHeap();
                  HeapFree(v1287, 0, v1286);
                  goto LABEL_1661;
                }
                v1270 = sub_180006240(v1215, 4, &v1316);
                if ( v1270 >= 0 )
                {
                  v1270 = sub_180006270(0, 4, &Size[4]);
                  if ( v1270 >= 0 )
                  {
                    if ( (unsigned int)(v1230 - *(_DWORD *)&Size[4]) < 4 )
                      goto LABEL_1653;
                    *(_DWORD *)Size = *(_DWORD *)v1316;
                    v1270 = sub_180006240(v1316, 4, &v1316);
                    if ( v1270 < 0 )
                      goto LABEL_1654;
                    v1270 = sub_180006270(*(unsigned int *)&Size[4], 4, &Size[4]);
                    if ( v1270 < 0 )
                      goto LABEL_1654;
                    if ( (unsigned int)(v1230 - *(_DWORD *)&Size[4]) < *(_DWORD *)Size )
                      goto LABEL_1653;
                    v1270 = sub_180006270(*(unsigned int *)&Size[4], *(unsigned int *)Size, &Size[4]);
                    if ( v1270 >= 0 )
                    {
                      v1274 = (unsigned int)v1230;
                      v1275 = (unsigned int *)v1316;
                      dwBytes = *(unsigned int *)Size;
                      if ( (char *)v1273 + v1274 >= (char *)v1316 + *(unsigned int *)Size
                        && (unsigned __int64)v1273 + v1274 - *(unsigned int *)Size - (_QWORD)v1316 < 8 )
                      {
                        v1345 = *v1273;
                        v1330 = 0;
                        v1346 = 0;
                        v1348 = 0;
                        LODWORD(v1334) = 0;
                        if ( v1316 )
                        {
                          v1339 = sub_180006240(v1316, dwBytes, &v1330);
                          v1270 = v1339;
                          v1318 = v1276;
                          v1319 = v1269;
                          v1322 = v1277;
                          v1317 = v1278;
                          if ( v1339 < 0 )
                          {
LABEL_1649:
                            v1285 = v1338;
LABEL_1650:
                            if ( v1270 < 0 || v1345 == v1285 )
                              goto LABEL_1655;
                            goto LABEL_1617;
                          }
                          v1279 = v1330;
                          while ( (unsigned __int64)v1275 < v1279 )
                          {
                            v1270 = sub_180006240(v1275, 4, &v1346);
                            if ( v1270 < 0 )
                              goto LABEL_1649;
                            if ( v1346 > v1280 )
                              goto LABEL_1637;
                            v1281 = *v1275;
                            LODWORD(v1315) = 0;
                            v1270 = sub_180006270(4, v1281, &v1315);
                            if ( v1270 < 0 )
                              goto LABEL_1655;
                            v1339 = sub_180006240(v1275, (unsigned int)v1315, &v1348);
                            v1270 = v1339;
                            if ( v1339 < 0 )
                              goto LABEL_1649;
                            v1275 = (unsigned int *)v1348;
                            if ( v1348 > v1279 )
                              goto LABEL_1637;
                            LODWORD(v1334) = v1334 + 1;
                          }
                          if ( v1275 != (unsigned int *)v1279 )
                          {
LABEL_1637:
                            v1270 = -1073741811;
                            goto LABEL_1655;
                          }
                          v1275 = (unsigned int *)v1316;
                        }
                        else
                        {
                          v1270 = 0;
                          v1318 = v1273;
                          v1339 = 0;
                          v1319 = v1269;
                          v1322 = v1271;
                          v1317 = v1272;
                        }
                        v1282 = 0;
                        v1330 = 0;
                        if ( *(_DWORD *)Size )
                        {
                          v1283 = GetProcessHeap();
                          v1284 = dwBytes;
                          v1282 = HeapAlloc(v1283, 8u, dwBytes);
                          v1330 = (SIZE_T)v1282;
                          if ( !v1282 )
                          {
                            v1270 = -1073741801;
                            goto LABEL_1655;
                          }
                          v1270 = 0;
                          v1339 = 0;
                        }
                        else
                        {
                          v1284 = dwBytes;
                        }
                        if ( v1275 )
                        {
                          memcpy(v1282, v1275, v1284);
                          v1270 = v1339;
                        }
                        v1325 = (LPVOID)v1330;
                        v1285 = v1334;
                        LODWORD(v1338) = v1334;
                        goto LABEL_1650;
                      }
LABEL_1653:
                      v1270 = -1073741762;
                    }
                  }
                }
LABEL_1654:
                v1318 = v1273;
                v1317 = v1272;
                v1322 = v1271;
                v1319 = v1269;
                goto LABEL_1655;
              }
              goto LABEL_1481;
            }
          }
        }
      }
    }
    v1322 = v1117;
LABEL_1481:
    v1159 = GetProcessHeap();
    HeapFree(v1159, 0, jj);
LABEL_1482:
    v1158 = *(_DWORD *)&Size[4];
    goto LABEL_1483;
  }
LABEL_870:
  v12 = v1358;
  v11 = v1364;
  v1367 = (BYTE *)v1352;
  v1359 = 0;
LABEL_9:
  sub_1800062C0(&v1359);
  if ( v10 >= 0 )
  {
    v5 = 0;
    v1311 = v11 - 1;
    if ( v1311 )
    {
      v1312 = v1311 - 2;
      if ( v1312 )
      {
        if ( v1312 != 1 )
          v8 = 0;
      }
      else
      {
        v8 = 3;
      }
    }
    else
    {
      v8 = 1;
    }
    if ( v1382 )
      *v1382 = v8;
    *v1381 = v12;
    if ( v12 )
    {
      v1313 = v1367;
      v1367 = 0;
      *v1372 = v1313;
    }
    else
    {
      *v1372 = 0;
    }
  }
  else if ( v10 == -805306316 )
  {
    v5 = -1073418222;
  }
  else if ( v10 == -805306139 || v10 == -1073425151 )
  {
    v5 = -1073418201;
  }
  else
  {
    v5 = v10;
    if ( v10 == -805306306 )
      v5 = -1073418200;
  }
LABEL_1716:
  sub_1800062C0(&v1367);
  return v5;
}

```

## disassembly

```asm
0x1800062f0  push    rbp
0x1800062f2  push    rbx
0x1800062f3  push    rsi
0x1800062f4  push    rdi
0x1800062f5  push    r12
0x1800062f7  push    r13
0x1800062f9  push    r14
0x1800062fb  push    r15
0x1800062fd  lea     rbp, [rsp-218h]
0x180006305  sub     rsp, 318h
0x18000630c  mov     [rbp+250h+var_D0], r8
0x180006313  mov     rax, r9
0x180006316  mov     [rbp+250h+var_168], rax
0x18000631d  mov     rsi, rcx
0x180006320  mov     [rbp+250h+var_C8], rdx
0x180006327  mov     [rbp+250h+var_250], rcx
0x18000632b  mov     [rbp+250h+var_1A0], 0
0x180006336  test    rcx, rcx
0x180006339  jnz     short loc_180006345
0x18000633b  mov     ebx, 80070057h
0x180006340  jmp     loc_180010C90
0x180006345  test    r8, r8
0x180006348  jz      short loc_18000633B
0x18000634a  test    rax, rax
0x18000634d  jz      short loc_18000633B
0x18000634f  xor     eax, eax
0x180006351  mov     [rbp+250h+var_238], eax
0x180006354  mov     [rbp+250h+var_1C8], rax
0x18000635b  call    cs:GetProcessHeap
0x180006361  mov     ebx, 8
0x180006366  mov     r8d, 0A0h; dwBytes
0x18000636c  mov     rcx, rax; hHeap
0x18000636f  mov     edx, ebx; dwFlags
0x180006371  call    cs:HeapAlloc
0x180006377  mov     [rbp+250h+Src], rax
0x18000637b  mov     r14, rax
0x18000637e  lea     r12d, [rbx-4]
0x180006382  test    rax, rax
0x180006385  jnz     short loc_1800063C0
0x180006387  mov     esi, 0C0000017h
0x18000638c  mov     r15d, esi
0x18000638f  mov     edi, [rbp+250h+var_238]
0x180006392  mov     esi, edi
0x180006394  lea     rcx, [rbp+250h+var_1C8]
0x18000639b  call    sub_1800062C0
0x1800063a0  test    r15d, r15d
0x1800063a3  jns     loc_180010C33
0x1800063a9  cmp     r15d, 0D0000034h
0x1800063b0  jnz     loc_180010C06
0x1800063b6  mov     ebx, 0C004F012h
0x1800063bb  jmp     loc_180010C90
0x1800063c0  movups  xmm0, cs:xmmword_180024150
0x1800063c7  xor     r13d, r13d
0x1800063ca  xor     eax, eax
0x1800063cc  mov     [rbp+250h+var_264], r13d
0x1800063d0  movups  xmmword ptr [r14], xmm0
0x1800063d4  mov     dword ptr [rsp+350h+uBytes], eax
0x1800063d8  movups  xmm1, cs:xmmword_180024160
0x1800063df  movups  xmmword ptr [r14+10h], xmm1
0x1800063e4  movups  xmm0, cs:xmmword_180024170
0x1800063eb  movups  xmmword ptr [r14+20h], xmm0
0x1800063f0  movups  xmm1, cs:xmmword_180024180
0x1800063f7  movups  xmmword ptr [r14+30h], xmm1
0x1800063fc  movups  xmm0, cs:xmmword_180024190
0x180006403  movups  xmmword ptr [r14+40h], xmm0
0x180006408  movups  xmm1, cs:xmmword_1800241A0
0x18000640f  movups  xmmword ptr [r14+50h], xmm1
0x180006414  movups  xmm0, cs:xmmword_1800241B0
0x18000641b  movups  xmmword ptr [r14+60h], xmm0
0x180006420  movups  xmm1, cs:xmmword_1800241C0
0x180006427  movups  xmmword ptr [r14+70h], xmm1
0x18000642c  movups  xmm0, cs:xmmword_1800241D0
0x180006433  movups  xmmword ptr [r14+80h], xmm0
0x18000643b  movups  xmm1, cs:xmmword_1800241E0
0x180006442  movups  xmmword ptr [r14+90h], xmm1
0x18000644a  call    cs:GetProcessHeap
0x180006450  mov     r8, rbx; dwBytes
0x180006453  mov     edx, ebx; dwFlags
0x180006455  mov     rcx, rax; hHeap
0x180006458  call    cs:HeapAlloc
0x18000645e  or      r10d, 0FFFFFFFFh
0x180006462  mov     [rbp+250h+var_268], 0D0000017h
0x180006469  mov     r11, rax
0x18000646c  mov     [rsp+350h+var_300], rax
0x180006471  xor     eax, eax
0x180006473  mov     [rbp+250h+var_1D8], r10d
0x180006477  mov     r15d, 0D0000095h
0x18000647d  mov     rbx, 0C81ECB17B1B54A58h
0x180006487  mov     [rsp+350h+var_2F8], r15d
0x18000648c  mov     rdi, 7F1137FAB69605Eh
0x180006496  test    r11, r11
0x180006499  jnz     short loc_1800064B0
0x18000649b  mov     esi, 0C0000017h
0x1800064a0  mov     [rsp+350h+var_300], rax
0x1800064a5  mov     dword ptr [rbp+250h+var_2C8], eax
0x1800064a8  mov     dword ptr [rbp+250h+var_2C0], eax
0x1800064ab  jmp     loc_180008A4C
0x1800064b0  mov     rax, cs:qword_180024090
0x1800064b7  mov     [r11], rax
0x1800064ba  rdtsc
0x1800064bc  shl     rdx, 20h
0x1800064c0  or      rax, rdx
0x1800064c3  mov     [rbp+250h+var_2B0], rax
0x1800064c7  lea     r8, [rbp+250h+dwBytes]
0x1800064cb  mov     [rbp+250h+dwBytes], r13
0x1800064cf  mov     rcx, rsi
0x1800064d2  call    sub_180001090
0x1800064d7  test    eax, eax
0x1800064d9  jns     short loc_1800064E5
0x1800064db  mov     esi, 0C000003Eh
0x1800064e0  jmp     loc_180008A44
0x1800064e5  mov     rax, [rbp+250h+dwBytes]
0x1800064e9  lea     eax, ds:6[rax*2]
0x1800064f0  cmp     eax, r12d
0x1800064f3  jb      loc_180008A3A
0x1800064f9  add     eax, 0C4h
0x1800064fe  mov     [rbp+250h+var_280], r13
0x180006502  xor     r14d, r14d
0x180006505  xor     r9d, r9d
0x180006508  mov     edx, 0C4h
0x18000650d  mov     ecx, r10d
0x180006510  cmp     eax, edx
0x180006512  mov     r8d, 0C0000095h
0x180006518  cmovnb  ecx, eax
0x18000651b  sbb     esi, esi
0x18000651d  and     esi, r8d
0x180006520  add     esi, 10000000h
0x180006526  cmp     eax, edx
0x180006528  jb      loc_1800089D6
0x18000652e  lea     eax, [rcx+8]
0x180006531  mov     edx, r10d
0x180006534  cmp     eax, ecx
0x180006536  cmovnb  edx, eax
0x180006539  sbb     esi, esi
0x18000653b  and     esi, r8d
0x18000653e  add     esi, 10000000h
0x180006544  cmp     eax, ecx
0x180006546  jb      loc_1800089D6
0x18000654c  lea     eax, [rdx+8]
0x18000654f  mov     ecx, r10d
0x180006552  cmp     eax, edx
0x180006554  cmovnb  ecx, eax
0x180006557  sbb     esi, esi
0x180006559  and     esi, r8d
0x18000655c  mov     dword ptr [rsp+350h+var_320], ecx
0x180006560  add     esi, 10000000h
0x180006566  cmp     eax, edx
0x180006568  jb      loc_1800089D6
0x18000656e  mov     esi, ecx
0x180006570  call    cs:GetProcessHeap
0x180006576  mov     r8d, esi; dwBytes
0x180006579  lea     edx, [r14+8]; dwFlags
0x18000657d  mov     rcx, rax; hHeap
0x180006580  call    cs:HeapAlloc
0x180006586  mov     r14, rax
0x180006589  test    rax, rax
0x18000658c  jnz     short loc_1800065A6
0x18000658e  mov     rax, [rsp+350h+var_300]
0x180006593  mov     esi, 0C0000017h
0x180006598  mov     r14, [rbp+250h+Src]
0x18000659c  mov     [rsp+350h+var_300], rax
0x1800065a1  jmp     loc_180008A44
0x1800065a6  mov     r11, [rsp+350h+var_300]
0x1800065ab  lea     rdx, [rax+4]
0x1800065af  mov     r10, [rbp+250h+Src]
0x1800065b3  mov     [rsp+350h+var_300], r11
0x1800065b8  mov     [rbp+250h+Src], r10
0x1800065bc  cmp     rdx, r14
0x1800065bf  jb      loc_1800089C8
0x1800065c5  lea     rcx, [rax+rsi]
0x1800065c9  add     rax, 8
0x1800065cd  cmp     rax, rcx
0x1800065d0  ja      short loc_18000663E
0x1800065d2  mov     [r14], r12d
0x1800065d5  xor     ecx, ecx
0x1800065d7  mov     [rdx], r13d
0x1800065da  mov     rdx, r14
0x1800065dd  mov     [rsp+350h+var_300], r11
0x1800065e2  mov     [rbp+250h+Src], r10
0x1800065e6  cmp     ecx, 1
0x1800065e9  jnb     short loc_18000660F
0x1800065eb  mov     eax, [rdx]
0x1800065ed  add     eax, r12d
0x1800065f0  cmp     eax, r12d
0x1800065f3  jb      loc_18000671E
0x1800065f9  mov     r8d, eax
0x1800065fc  add     r8, rdx
0x1800065ff  cmp     r8, rdx
0x180006602  jb      loc_18000671E
0x180006608  mov     rdx, r8
0x18000660b  inc     ecx
0x18000660d  jmp     short loc_1800065E6
0x18000660f  lea     r9, [rdx+4]
0x180006613  cmp     r9, rdx
0x180006616  jb      loc_18000671E
0x18000661c  mov     esi, dword ptr [rsp+350h+var_320]
0x180006620  mov     r8d, 0A0h
0x180006626  mov     r8d, r8d; Size
0x180006629  mov     [rsp+350h+var_318], rsi
0x18000662e  lea     rcx, [r14+rsi]
0x180006632  lea     rax, [r8+4]
0x180006636  add     rax, rdx
0x180006639  cmp     rax, rcx
0x18000663c  jbe     short loc_180006648
0x18000663e  mov     esi, 0C0000023h
0x180006643  jmp     loc_180006723
0x180006648  mov     dword ptr [rdx], 0A0h
0x18000664e  test    r10, r10
0x180006651  jz      short loc_180006663
0x180006653  mov     rdx, r10; Src
0x180006656  mov     rcx, r9; void *
0x180006659  call    memcpy
0x18000665e  mov     r11, [rsp+350h+var_300]
0x180006663  mov     r10d, 2
0x180006669  mov     dword ptr [rsp+350h+Size+4], r10d
0x18000666e  test    r11, r11
0x180006671  jz      loc_1800089BE
0x180006677  test    r14, r14
0x18000667a  jnz     short loc_18000668F
0x18000667c  lea     eax, [rsi+0Ch]
0x18000667f  cmp     eax, esi
0x180006681  jb      loc_18000671E
0x180006687  inc     r10d
0x18000668a  jmp     loc_180006712
0x18000668f  mov     rdx, r14
0x180006692  xor     ecx, ecx
0x180006694  cmp     ecx, r10d
0x180006697  jnb     short loc_1800066B5
0x180006699  mov     eax, [rdx]
0x18000669b  add     eax, r12d
0x18000669e  cmp     eax, r12d
0x1800066a1  jb      short loc_18000671E
0x1800066a3  mov     r8d, eax
0x1800066a6  add     r8, rdx
0x1800066a9  cmp     r8, rdx
0x1800066ac  jb      short loc_18000671E
0x1800066ae  mov     rdx, r8
0x1800066b1  inc     ecx
0x1800066b3  jmp     short loc_180006694
0x1800066b5  lea     r9, [rdx+4]
0x1800066b9  cmp     r9, rdx
0x1800066bc  jb      short loc_18000671E
0x1800066be  mov     r8d, 8
0x1800066c4  lea     rcx, [r14+rsi]
0x1800066c8  mov     r8d, r8d; Size
0x1800066cb  lea     rax, [r8+4]
0x1800066cf  add     rax, rdx
0x1800066d2  cmp     rax, rcx
0x1800066d5  ja      loc_18000663E
0x1800066db  mov     dword ptr [rdx], 8
0x1800066e1  test    r11, r11
0x1800066e4  jz      short loc_1800066FB
0x1800066e6  mov     rdx, r11; Src
0x1800066e9  mov     rcx, r9; void *
0x1800066ec  call    memcpy
0x1800066f1  mov     r11, [rsp+350h+var_300]
0x1800066f6  mov     r10d, dword ptr [rsp+350h+Size+4]
0x1800066fb  mov     rax, [rbp+250h+Src]
0x1800066ff  inc     r10d
0x180006702  mov     [rsp+350h+var_300], r11
0x180006707  mov     [rbp+250h+Src], rax
0x18000670b  test    r14, r14
0x18000670e  jnz     short loc_18000672B
0x180006710  mov     eax, esi
0x180006712  lea     esi, [rax+0Ch]
0x180006715  mov     [rsp+350h+var_318], rsi
0x18000671a  cmp     esi, eax
0x18000671c  jnb     short loc_180006778
0x18000671e  mov     esi, 0C0000095h
0x180006723  mov     r9d, r13d
0x180006726  jmp     loc_1800089E3
0x18000672b  mov     rdx, r14
0x18000672e  xor     ecx, ecx
0x180006730  cmp     ecx, r10d
0x180006733  jnb     short loc_180006751
0x180006735  mov     eax, [rdx]
0x180006737  add     eax, r12d
0x18000673a  cmp     eax, r12d
0x18000673d  jb      short loc_18000671E
0x18000673f  mov     r8d, eax
0x180006742  add     r8, rdx
0x180006745  cmp     r8, rdx
0x180006748  jb      short loc_18000671E
0x18000674a  mov     rdx, r8
0x18000674d  inc     ecx
0x18000674f  jmp     short loc_180006730
0x180006751  lea     r8, [rdx+4]
0x180006755  cmp     r8, rdx
0x180006758  jb      short loc_18000671E
0x18000675a  lea     rcx, [r14+rsi]
0x18000675e  lea     rax, [rdx+0Ch]
0x180006762  cmp     rax, rcx
0x180006765  ja      loc_18000663E
0x18000676b  mov     rax, [rbp+250h+var_2B0]
0x18000676f  mov     dword ptr [rdx], 8
0x180006775  mov     [r8], rax
0x180006778  mov     rcx, [rbp+250h+var_250]
0x18000677c  lea     r8, [rbp+250h+dwBytes]
0x180006780  inc     r10d
0x180006783  mov     [rbp+250h+dwBytes], r13
  ... truncated ...
```
