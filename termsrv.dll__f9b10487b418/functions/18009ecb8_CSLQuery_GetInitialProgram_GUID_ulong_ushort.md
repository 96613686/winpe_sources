# CSLQuery::GetInitialProgram(_GUID,ulong,ushort *)

- ea: `0x18009ecb8`
- end: `0x1800a931f`
- name: `?GetInitialProgram@CSLQuery@@SAJU_GUID@@KPEAG@Z`
- size: `42599`
- prototype: `__int64 __fastcall(struct _GUID *__struct_ptr, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002fd60`

## callees

- `0x180002544`
- `0x1800052d0`
- `0x180005c88`
- `0x180005dac`
- `0x1800127b0`
- `0x180014a2c`
- `0x1800159d8`
- `0x180015ab0`
- `0x180024d08`
- `0x1800255f8`
- `0x180025624`
- `0x1800256dc`
- `0x180028070`
- `0x1800287b4`
- `0x1800321d4`
- `0x1800326dc`
- `0x18009ecb8`
- `0x1800c4290`
- `0x1800c4e0c`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800a02ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800a29ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800a5923`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800a80bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800a02ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800a29ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800a5923`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800a80bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a030f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a2a2d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a5969`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a80f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a030f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a2a2d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a5969`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a80f4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009f088`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009f16d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009f292`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009f6e2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009f78b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009fbb7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009fcd6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009fd17`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009fdc9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009ff6c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a01fc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a04ae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a0513`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a0565`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a05c2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a0828`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a0f64`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a1532`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a15c8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a1612`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a1925`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a1a48`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a1e38`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a1f5a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a1f9b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a204e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a224d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a285a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a2c64`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a2cda`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a2d44`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a2dce`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a39ae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a3b3b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a3be0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a3df4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a3fbb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a404e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a47ff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a4e4a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a4f85`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a4fd6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5077`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a526f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5763`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5bc2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5c2d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5c8f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5cf6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a6756`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a6cd1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a7241`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a78a1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a78d8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a7931`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a79d9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a7c7c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a7f29`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a8323`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a8389`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a83ef`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a8455`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a8e6c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009f088`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009f16d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009f292`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009f6e2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009f78b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009fbb7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009fcd6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009fd17`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009fdc9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009ff6c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a01fc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a04ae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a0513`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a0565`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a05c2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a0828`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a0f64`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a1532`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a15c8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a1612`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a1925`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a1a48`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a1e38`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a1f5a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a1f9b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a204e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a224d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a285a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a2c64`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a2cda`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a2d44`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a2dce`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a39ae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a3b3b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a3be0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a3df4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a3fbb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a404e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a47ff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a4e4a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a4f85`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a4fd6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5077`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a526f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5763`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5bc2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5c2d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5c8f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5cf6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a6756`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a6cd1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a7241`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a78a1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a78d8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a7931`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a79d9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a7c7c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a7f29`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a8323`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a8389`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a83ef`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a8455`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a8e6c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009f072`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009f15f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009f282`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009f6d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009f77c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009fb61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009fba5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009fbd9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009fc09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009fc38`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009fc67`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009fc89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009fcc1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009fd03`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009fdb6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009fe17`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009fe45`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009fe73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009fe94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009ff5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a0086`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a01eb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a049c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a0502`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a0553`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a05b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a0627`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a0655`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a0683`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a06a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a074c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a077a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a07a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a07c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a0819`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a0f51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a101d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a104e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a107d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a10ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a10ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a10eb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a1107`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a1136`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a1164`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a1192`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a11b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a11cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a1482`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a149f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a14e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a14f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a151e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a15b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a15fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a1913`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a19f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a1a39`

## string_xrefs

- `0x1800a027f`: `ntdll.dll`
- `0x1800a29bd`: `ntdll.dll`
- `0x1800a5905`: `ntdll.dll`
- `0x1800a809f`: `ntdll.dll`
- `0x18009ed29`: `TerminalServices-RemoteConnectionManager-`

## pseudocode

```c
__int64 __fastcall CSLQuery::GetInitialProgram(struct _GUID *a1, __int64 a2, unsigned __int16 *a3)
{
  int v3; // r15d
  wchar_t *v4; // r13
  unsigned __int16 *v5; // rdi
  unsigned __int64 v6; // r11
  __int64 v7; // r8
  __int64 v8; // r9
  unsigned __int64 v9; // r11
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  unsigned __int64 v16; // rbx
  unsigned __int64 v17; // rax
  HANDLE ProcessHeap; // rax
  _OWORD *v19; // r14
  int v20; // esi
  unsigned int v21; // ebx
  int v22; // r12d
  HANDLE v23; // rax
  _QWORD *v24; // rax
  void *v25; // r13
  void *v26; // r11
  unsigned int v27; // eax
  char *v28; // r13
  int v29; // r9d
  unsigned int v30; // ecx
  unsigned int v31; // eax
  unsigned int v32; // edx
  unsigned int v33; // eax
  unsigned int v34; // ecx
  __int64 v35; // rsi
  HANDLE v36; // rax
  char *v37; // rax
  void *v38; // r11
  int v39; // ecx
  _DWORD *v40; // rdx
  unsigned int v41; // eax
  unsigned __int64 v42; // r8
  size_t v43; // rdx
  void *v44; // r11
  int v45; // r9d
  unsigned int v46; // ecx
  _DWORD *v47; // rdx
  _DWORD *v48; // rax
  unsigned int v49; // r9d
  unsigned int v50; // eax
  SIZE_T v51; // rax
  void *v52; // r11
  __int64 v53; // r8
  unsigned int v54; // r8d
  unsigned int v55; // eax
  unsigned int v56; // ecx
  _DWORD *v57; // rdx
  unsigned int v58; // eax
  unsigned int v59; // edx
  unsigned int v60; // edx
  unsigned int v61; // ecx
  unsigned int v62; // r9d
  _DWORD *v63; // r10
  unsigned int ii; // esi
  unsigned int v65; // ecx
  _DWORD *v66; // r10
  unsigned int v67; // eax
  unsigned int v68; // esi
  SIZE_T v69; // rax
  HANDLE v70; // rax
  _DWORD *v71; // rax
  void *v72; // rsi
  unsigned int v73; // edx
  HANDLE v74; // rax
  char *v75; // rdx
  unsigned __int8 v76; // al
  unsigned __int64 v77; // r8
  int v78; // r8d
  int v79; // r10d
  int v80; // eax
  _BYTE *v81; // r13
  size_t v82; // rdi
  int v83; // r9d
  unsigned __int8 *v84; // r14
  unsigned int v85; // r12d
  int v86; // ecx
  int v87; // esi
  int v88; // r11d
  int v89; // esi
  int v90; // r11d
  int v91; // edx
  int v92; // r9d
  int v93; // r10d
  int v94; // r8d
  int v95; // r9d
  unsigned int v96; // edx
  int v97; // r8d
  int v98; // ecx
  int v99; // edx
  int v100; // r8d
  int v101; // r9d
  int v102; // edx
  unsigned int v103; // r8d
  unsigned int v104; // r9d
  int v105; // edx
  int v106; // r8d
  int v107; // r9d
  int v108; // edx
  int v109; // r8d
  int v110; // r10d
  int v111; // edx
  int v112; // r9d
  unsigned int v113; // r8d
  int v114; // edx
  HANDLE v115; // rax
  HANDLE v116; // rax
  int v117; // esi
  void *v118; // rax
  HANDLE v119; // rax
  SIZE_T v120; // rax
  HANDLE v121; // rax
  HANDLE v122; // rax
  HANDLE v123; // rax
  HANDLE v124; // rax
  _DWORD *v125; // rcx
  _QWORD *v126; // rsi
  HANDLE v127; // rax
  void *v128; // rax
  HANDLE v129; // rax
  _OWORD *v130; // rax
  HANDLE v131; // rax
  _QWORD *v132; // rax
  _QWORD *v133; // rax
  HANDLE v134; // rax
  HANDLE v135; // rax
  HANDLE v136; // rax
  HANDLE v137; // rax
  unsigned int v138; // eax
  unsigned int v139; // edx
  unsigned int v140; // r8d
  unsigned int v141; // edx
  unsigned int v142; // eax
  unsigned int v143; // esi
  HANDLE v144; // rax
  _DWORD *v145; // rax
  const void **v146; // rsi
  _DWORD *v147; // rcx
  unsigned int *v148; // rdx
  _DWORD *v149; // rcx
  SIZE_T v150; // r10
  void *v151; // rdx
  HANDLE v152; // rax
  _DWORD *v153; // r9
  _DWORD *v154; // r11
  unsigned int *v155; // rax
  unsigned int *v156; // r8
  void *v157; // r8
  unsigned int v158; // r10d
  unsigned int v159; // eax
  unsigned int v160; // esi
  HANDLE v161; // rax
  void *v162; // rax
  void *v163; // r8
  void *v164; // r9
  void *v165; // rcx
  void *v166; // r10
  signed int v167; // eax
  FARPROC v168; // rax
  int v169; // eax
  unsigned int v170; // edx
  void *v171; // rax
  size_t v172; // rsi
  char *v173; // rcx
  char *v174; // r11
  size_t v175; // r8
  _DWORD *v176; // rcx
  unsigned int v177; // r11d
  unsigned __int64 v178; // r10
  unsigned int v179; // ecx
  unsigned int v180; // r10d
  unsigned int v181; // ecx
  HANDLE v182; // rax
  _QWORD *v183; // r14
  const void *v184; // r13
  HANDLE v185; // rax
  void *v186; // rax
  int v187; // esi
  char *v188; // r13
  HANDLE v189; // rax
  void *v190; // rax
  void *v191; // r13
  size_t v192; // rax
  unsigned int v193; // esi
  HANDLE v194; // rax
  void *v195; // rax
  SIZE_T v196; // rax
  HANDLE v197; // rax
  HANDLE v198; // rax
  HANDLE v199; // rax
  HANDLE v200; // rax
  size_t *v201; // rcx
  HANDLE v202; // rax
  HANDLE v203; // rax
  HANDLE v204; // rax
  HANDLE v205; // rax
  HANDLE v206; // rax
  LPVOID v207; // rax
  SIZE_T v208; // r8
  unsigned __int8 v209; // dl
  unsigned int v210; // r11d
  unsigned int v211; // edi
  unsigned __int8 *v212; // rbx
  int v213; // r12d
  int v214; // edx
  int v215; // ecx
  unsigned int v216; // r10d
  unsigned int v217; // r9d
  int v218; // eax
  int v219; // ecx
  _BYTE *v220; // rsi
  unsigned int v221; // edi
  char v222; // bl
  int v223; // r10d
  int v224; // r11d
  unsigned __int8 *v225; // rbx
  _BYTE *v226; // r12
  int v227; // edx
  int v228; // r15d
  size_t v229; // r13
  int v230; // eax
  int v231; // r14d
  int v232; // esi
  int v233; // r14d
  int v234; // esi
  int v235; // r8d
  int v236; // r9d
  unsigned int v237; // ecx
  int v238; // r8d
  int v239; // r9d
  unsigned int v240; // ecx
  int v241; // r8d
  int v242; // r10d
  int v243; // r11d
  unsigned int v244; // r9d
  int v245; // r8d
  unsigned int v246; // r9d
  int v247; // r10d
  int v248; // r11d
  int v249; // ecx
  int v250; // r8d
  int v251; // r9d
  int v252; // ecx
  int v253; // r10d
  int v254; // r8d
  unsigned int v255; // ecx
  int v256; // r10d
  int v257; // eax
  _DWORD *v258; // rsi
  unsigned __int64 m; // rax
  SIZE_T v260; // rax
  int v261; // esi
  SIZE_T v262; // rax
  _DWORD *v263; // rcx
  unsigned int v264; // eax
  SIZE_T v265; // r9
  bool v266; // zf
  HANDLE v267; // rax
  void *v268; // rax
  HANDLE v269; // rax
  _QWORD *v270; // rax
  HANDLE v271; // rax
  HANDLE v272; // rax
  HANDLE v273; // rax
  HANDLE v274; // rax
  HANDLE v275; // rax
  HANDLE v276; // rax
  _QWORD *v277; // rax
  HANDLE v278; // rax
  HANDLE v279; // rax
  HANDLE v280; // rax
  HANDLE v281; // rax
  HANDLE v282; // rax
  int *v283; // rsi
  _DWORD *v284; // rax
  int v285; // r8d
  _DWORD *v286; // rdx
  __int64 *v287; // r8
  __int64 v288; // rsi
  _DWORD *v289; // rdx
  int v290; // r10d
  _DWORD *v291; // r8
  unsigned int *v292; // rdx
  unsigned int n; // r10d
  unsigned int *v294; // r8
  _DWORD *v295; // rax
  int v296; // r8d
  _DWORD *v297; // rdx
  unsigned int *v298; // rdx
  unsigned int v299; // r10d
  _DWORD *v300; // rax
  int v301; // r8d
  _DWORD *v302; // rdx
  int *v303; // rdx
  HANDLE v304; // rax
  void *v305; // r13
  HANDLE v306; // rax
  HANDLE v307; // rax
  HANDLE v308; // rax
  HANDLE v309; // rax
  _OWORD *v310; // rax
  void *v311; // r14
  HANDLE v312; // rax
  _QWORD *v313; // rax
  void *v314; // rsi
  HANDLE v315; // rax
  _DWORD *v316; // r13
  unsigned int v317; // r9d
  _DWORD *v318; // rax
  _DWORD *v319; // rcx
  int v320; // r10d
  _DWORD *v321; // r10
  int v322; // r11d
  _DWORD *v323; // r9
  unsigned int v324; // r10d
  unsigned int *v325; // r9
  int v326; // r10d
  unsigned int v327; // r11d
  _DWORD *v328; // r9
  unsigned int v329; // r10d
  int v330; // r11d
  _DWORD *v331; // r9
  int v332; // r10d
  _QWORD *v333; // rax
  size_t v334; // rcx
  HANDLE v335; // rax
  void *v336; // r9
  int v337; // esi
  int v338; // esi
  SIZE_T v339; // r9
  unsigned int v340; // r10d
  SIZE_T v341; // rcx
  unsigned int v342; // r11d
  HANDLE v343; // rax
  unsigned __int64 v344; // rsi
  HANDLE v345; // rax
  SIZE_T v346; // r9
  unsigned __int8 v347; // al
  unsigned __int64 v348; // rdx
  void *v349; // rsi
  _BYTE *v350; // r14
  unsigned __int8 *v351; // r12
  int v352; // r15d
  SIZE_T v353; // rdi
  int v354; // r9d
  int v355; // r8d
  unsigned int v356; // eax
  int v357; // ecx
  int v358; // esi
  int v359; // r11d
  int v360; // esi
  int v361; // r11d
  int v362; // r8d
  int v363; // r10d
  int v364; // r8d
  int v365; // r10d
  int v366; // r9d
  int v367; // r8d
  unsigned int v368; // edx
  int v369; // r9d
  int v370; // ecx
  int v371; // edx
  int v372; // r8d
  int v373; // r9d
  int v374; // edx
  unsigned int v375; // r8d
  unsigned int v376; // r9d
  int v377; // edx
  int v378; // r8d
  int v379; // r9d
  int v380; // edx
  int v381; // r8d
  int v382; // r9d
  int v383; // r10d
  int v384; // r8d
  unsigned int v385; // edx
  int v386; // r8d
  int v387; // r9d
  HANDLE v388; // rax
  int v389; // esi
  void *v390; // rax
  HANDLE v391; // rax
  _QWORD *v392; // rax
  HANDLE v393; // rax
  HANDLE v394; // rax
  HANDLE v395; // rax
  HANDLE v396; // rax
  unsigned int *v397; // r11
  SIZE_T v398; // rsi
  HANDLE v399; // rax
  void *v400; // rax
  HANDLE v401; // rax
  _OWORD *v402; // rax
  HANDLE v403; // rax
  _QWORD *v404; // rax
  SIZE_T v405; // rax
  HANDLE v406; // rax
  HANDLE v407; // rax
  HANDLE v408; // rax
  HANDLE v409; // rax
  __int64 v410; // rdx
  int v411; // esi
  unsigned int v412; // r9d
  __int64 v413; // r11
  __int64 v414; // rdx
  unsigned int v415; // r9d
  __int64 v416; // r11
  __int64 v417; // rdx
  void *v418; // r11
  unsigned int v419; // esi
  HANDLE v420; // rax
  LPVOID v421; // rcx
  HANDLE v422; // rax
  _QWORD *v423; // rax
  HANDLE v424; // rax
  HANDLE v425; // rax
  HANDLE v426; // rax
  HANDLE v427; // rax
  HANDLE v428; // rax
  HANDLE v429; // rax
  _QWORD *v430; // rax
  HANDLE v431; // rax
  HANDLE v432; // rax
  HANDLE v433; // rax
  HANDLE v434; // rax
  HANDLE v435; // rax
  int v436; // eax
  unsigned int v437; // r9d
  _DWORD *v438; // r10
  __int64 v439; // r11
  int *v440; // rcx
  unsigned int v441; // eax
  SIZE_T v442; // rcx
  unsigned int v443; // r10d
  int v444; // r9d
  void *v445; // r9
  void *v446; // r10
  void *v447; // rcx
  void *v448; // r9
  void *v449; // r10
  const void **v450; // r11
  const void **v451; // r9
  SIZE_T v452; // rcx
  unsigned int *v453; // r10
  SIZE_T v454; // rcx
  unsigned int *v455; // r9
  void *v456; // rax
  HANDLE v457; // rax
  int v458; // eax
  __int64 v459; // rcx
  void *v460; // r9
  void *v461; // r10
  void *v462; // r11
  SIZE_T v463; // rcx
  __int64 v464; // r10
  unsigned int v465; // r9d
  unsigned int v466; // esi
  HANDLE v467; // rax
  void *v468; // r9
  SIZE_T v469; // rcx
  unsigned int v470; // r10d
  int v471; // r9d
  unsigned int v472; // ecx
  unsigned int v473; // r11d
  int v474; // r9d
  unsigned int v475; // r10d
  signed int v476; // eax
  FARPROC v477; // rax
  int v478; // eax
  unsigned int v479; // r10d
  int v480; // esi
  unsigned int *v481; // rcx
  int v482; // r10d
  size_t v483; // r11
  unsigned int v484; // r11d
  int v485; // r10d
  int v486; // r10d
  size_t v487; // r11
  unsigned int v488; // r11d
  int v489; // r10d
  int v490; // r10d
  unsigned int v491; // r11d
  int v492; // r10d
  int v493; // r11d
  SIZE_T v494; // rsi
  HANDLE v495; // rax
  SIZE_T v496; // rcx
  HANDLE v497; // rax
  void *v498; // rcx
  HANDLE v499; // rax
  void *v500; // rcx
  size_t v501; // rax
  unsigned int v502; // esi
  HANDLE v503; // rax
  void *v504; // rcx
  SIZE_T v505; // rax
  HANDLE v506; // rax
  HANDLE v507; // rax
  HANDLE v508; // rax
  HANDLE v509; // rax
  size_t *v510; // rdx
  HANDLE v511; // rax
  HANDLE v512; // rax
  HANDLE v513; // rax
  HANDLE v514; // rax
  unsigned __int64 v515; // rsi
  unsigned __int8 v516; // al
  int v517; // edi
  int v518; // eax
  int v519; // esi
  unsigned __int8 *v520; // rbx
  int v521; // ecx
  _BYTE *v522; // r11
  unsigned int v523; // edx
  unsigned int v524; // r8d
  unsigned int v525; // r9d
  int v526; // ecx
  int v527; // r10d
  unsigned int v528; // edi
  char v529; // bl
  int v530; // r9d
  int v531; // r11d
  SIZE_T v532; // r12
  unsigned __int8 *v533; // rbx
  int v534; // r15d
  int v535; // r10d
  int v536; // r13d
  _BYTE *v537; // rax
  int v538; // ecx
  int v539; // r14d
  int v540; // esi
  int v541; // r14d
  int v542; // edx
  int v543; // esi
  int v544; // r8d
  int v545; // r9d
  unsigned int v546; // edx
  int v547; // r8d
  int v548; // r9d
  unsigned int v549; // edx
  int v550; // r8d
  int v551; // r10d
  int v552; // r11d
  unsigned int v553; // r9d
  int v554; // r8d
  unsigned int v555; // r9d
  int v556; // r10d
  int v557; // r11d
  int v558; // edx
  int v559; // r8d
  int v560; // r9d
  int v561; // edx
  int v562; // r10d
  int v563; // r8d
  unsigned int v564; // edx
  int v565; // r8d
  unsigned __int64 k; // rcx
  int v567; // esi
  void *v568; // r9
  void *v569; // r10
  void *v570; // r11
  void *v571; // rdx
  int v572; // eax
  void *v573; // rcx
  void *v574; // r10
  void *v575; // r11
  void *v576; // r9
  unsigned int *v577; // rcx
  __int64 v578; // rdx
  _BYTE *v579; // r9
  _DWORD *v580; // r12
  void *v581; // r13
  void *v582; // r9
  void *v583; // r10
  void *v584; // r11
  void *v585; // rax
  int v586; // eax
  unsigned int v587; // edx
  void *v588; // rcx
  HANDLE v589; // rax
  HANDLE v590; // rax
  void *v591; // r13
  HANDLE v592; // rax
  HANDLE v593; // rax
  HANDLE v594; // rax
  HLOCAL v595; // rax
  HANDLE v596; // rax
  _OWORD *v597; // rax
  void *v598; // r13
  void *v599; // r14
  HANDLE v600; // rax
  _QWORD *v601; // rax
  int v602; // eax
  int v603; // ecx
  unsigned int v604; // r11d
  unsigned int v605; // r11d
  unsigned int v606; // r11d
  size_t v607; // rdx
  unsigned int v608; // r11d
  unsigned int v609; // r11d
  unsigned int v610; // r11d
  unsigned int v611; // esi
  HANDLE v612; // rax
  _DWORD *v613; // rsi
  int v614; // eax
  int v615; // r9d
  unsigned int v616; // r11d
  _DWORD *v617; // rax
  unsigned int v618; // esi
  int v619; // r10d
  void *v620; // rsi
  HANDLE v621; // rax
  void *v622; // rsi
  HANDLE v623; // rax
  HANDLE v624; // rax
  HANDLE v625; // rax
  void *v626; // r12
  _DWORD *v627; // r13
  HANDLE v628; // rax
  _OWORD *v629; // rax
  void *v630; // r14
  HANDLE v631; // rax
  _QWORD *v632; // rax
  _QWORD *v633; // r13
  unsigned int *v634; // r9
  __int64 v635; // rdx
  __int64 v636; // r9
  unsigned int v637; // r10d
  unsigned int *v638; // r9
  unsigned int v639; // r11d
  int v640; // r10d
  unsigned int *v641; // r9
  __int64 v642; // rdx
  __int64 v643; // r9
  unsigned int v644; // r10d
  int v645; // r11d
  unsigned int *v646; // r9
  unsigned int *v647; // r10
  int v648; // r9d
  size_t v649; // rdx
  __int64 v650; // rdx
  __int64 v651; // r10
  unsigned int v652; // r9d
  int v653; // r11d
  _DWORD *v654; // r10
  _QWORD *v655; // rax
  SIZE_T v656; // rcx
  int v657; // r11d
  unsigned int *v658; // r9
  int v659; // esi
  __int64 v660; // rdx
  __int64 v661; // r9
  unsigned int v662; // r11d
  _DWORD *v663; // r9
  __int64 v664; // r10
  STRSAFE_PCNZWCH v665; // rdx
  void *v666; // rcx
  unsigned int *v667; // r9
  int v668; // r10d
  __int64 v669; // rdx
  __int64 v670; // r9
  unsigned int v671; // r10d
  int v672; // r11d
  _DWORD *v673; // r9
  _DWORD *v674; // rax
  unsigned int *v675; // r9
  int v676; // r10d
  __int64 v677; // rdx
  __int64 v678; // r9
  unsigned int v679; // r10d
  int v680; // r11d
  _DWORD *v681; // r9
  _DWORD *v682; // rax
  __int64 v683; // rcx
  unsigned int v684; // r10d
  unsigned int v685; // r9d
  int v686; // eax
  unsigned int v687; // r9d
  unsigned int v688; // eax
  unsigned int v689; // esi
  HANDLE v690; // rax
  _DWORD *v691; // rsi
  int v692; // r9d
  unsigned int v693; // r10d
  LPVOID v694; // rcx
  HANDLE v695; // rax
  _DWORD *v696; // rsi
  unsigned __int8 *v697; // r15
  SIZE_T v698; // r10
  unsigned __int8 v699; // al
  SIZE_T v700; // rcx
  unsigned __int8 *v701; // r11
  int v702; // edx
  unsigned int v703; // r9d
  int v704; // edi
  int v705; // ebx
  int v706; // r8d
  unsigned int v707; // r9d
  unsigned int v708; // r8d
  unsigned int v709; // ecx
  int v710; // r11d
  _BYTE *v711; // rdi
  char v712; // bl
  unsigned int v713; // r9d
  _BYTE *v714; // rdi
  size_t v715; // r15
  int v716; // r14d
  int v717; // r13d
  int v718; // eax
  int v719; // esi
  int v720; // r11d
  int v721; // edx
  int v722; // r9d
  int v723; // r10d
  int v724; // r8d
  int v725; // r9d
  unsigned int v726; // edx
  int v727; // r8d
  int v728; // ecx
  int v729; // edx
  int v730; // r8d
  int v731; // r9d
  int v732; // edx
  unsigned int v733; // r8d
  unsigned int v734; // r9d
  int v735; // edx
  int v736; // r8d
  int v737; // r9d
  int v738; // edx
  int v739; // r8d
  int v740; // r9d
  int v741; // edx
  int v742; // r8d
  unsigned int v743; // r9d
  int v744; // edx
  unsigned int v745; // ecx
  int v746; // r9d
  int v747; // edx
  HANDLE v748; // rax
  _DWORD *v749; // rax
  int v750; // r15d
  void *v751; // rax
  HANDLE v752; // rax
  SIZE_T v753; // rax
  HANDLE v754; // rax
  HANDLE v755; // rax
  HANDLE v756; // rax
  HANDLE v757; // rax
  HANDLE v758; // rax
  void *v759; // rcx
  _DWORD *v760; // r15
  HANDLE v761; // rax
  _OWORD *v762; // rax
  HANDLE v763; // rax
  _QWORD *v764; // rax
  _QWORD *v765; // rax
  HANDLE v766; // rax
  HANDLE v767; // rax
  HANDLE v768; // rax
  HANDLE v769; // rax
  const void **v770; // rsi
  unsigned int v771; // r9d
  int v772; // r15d
  __int64 v773; // rdx
  unsigned int v774; // r9d
  __int64 v775; // rdx
  unsigned int v776; // esi
  HANDLE v777; // rax
  LPVOID v778; // rcx
  LPVOID v779; // rax
  HANDLE v780; // rax
  _QWORD *v781; // rax
  HANDLE v782; // rax
  HANDLE v783; // rax
  HANDLE v784; // rax
  HANDLE v785; // rax
  HANDLE v786; // rax
  HANDLE v787; // rax
  _QWORD *v788; // rsi
  HANDLE v789; // rax
  HANDLE v790; // rax
  HANDLE v791; // rax
  HANDLE v792; // rax
  void *v793; // rsi
  HANDLE v794; // rax
  void *v795; // r9
  void *v796; // rcx
  void *v797; // r9
  int v798; // r10d
  SIZE_T v799; // rcx
  unsigned int *v800; // r9
  SIZE_T v801; // rcx
  unsigned int *v802; // r9
  int v803; // eax
  HANDLE v804; // rax
  int v805; // eax
  __int64 v806; // rcx
  void *v807; // r9
  SIZE_T v808; // rcx
  unsigned int v809; // r10d
  unsigned int v810; // r9d
  int v811; // r11d
  unsigned int v812; // esi
  SIZE_T v813; // rcx
  unsigned int v814; // esi
  HANDLE v815; // rax
  unsigned int v816; // r11d
  int v817; // r9d
  unsigned int v818; // r11d
  unsigned int v819; // r11d
  unsigned int v820; // r11d
  unsigned int v821; // r9d
  signed int v822; // eax
  FARPROC v823; // rax
  int v824; // eax
  unsigned int v825; // r9d
  unsigned int v826; // r11d
  int v827; // r15d
  unsigned int *v828; // rcx
  int v829; // r9d
  _BYTE *v830; // r10
  unsigned int v831; // r10d
  int v832; // r9d
  __int64 v833; // r11
  unsigned int v834; // r10d
  int v835; // r9d
  SIZE_T v836; // r11
  unsigned int v837; // r11d
  int v838; // r9d
  unsigned int v839; // r10d
  int v840; // r9d
  unsigned int v841; // r10d
  int v842; // r9d
  int v843; // r10d
  int v844; // r11d
  SIZE_T v845; // r15
  HANDLE v846; // rax
  SIZE_T v847; // rcx
  HANDLE v848; // rax
  void *v849; // rcx
  HANDLE v850; // rax
  void *v851; // rcx
  SIZE_T v852; // rax
  unsigned __int64 v853; // rax
  unsigned int v854; // r15d
  HANDLE v855; // rax
  void *v856; // rcx
  SIZE_T v857; // rax
  HANDLE v858; // rax
  HANDLE v859; // rax
  HANDLE v860; // rax
  HANDLE v861; // rax
  unsigned int *v862; // rdx
  HANDLE v863; // rax
  HANDLE v864; // rax
  HANDLE v865; // rax
  HANDLE v866; // rax
  unsigned __int64 v867; // r15
  unsigned __int8 v868; // al
  unsigned int v869; // r9d
  unsigned int v870; // r11d
  int v871; // edi
  int v872; // eax
  unsigned __int8 *v873; // rbx
  int v874; // r10d
  unsigned int v875; // r8d
  unsigned int v876; // r10d
  unsigned int v877; // r11d
  int v878; // ecx
  int v879; // edx
  _BYTE *v880; // rdi
  char v881; // bl
  int v882; // r10d
  size_t v883; // rcx
  int v884; // r11d
  unsigned __int8 *v885; // rbx
  int v886; // r9d
  _BYTE *v887; // r15
  int v888; // r13d
  int v889; // r12d
  size_t v890; // rax
  int v891; // ecx
  int v892; // r14d
  int v893; // esi
  int v894; // r14d
  int v895; // edx
  int v896; // esi
  int v897; // r8d
  int v898; // r9d
  unsigned int v899; // edx
  int v900; // r8d
  int v901; // r9d
  unsigned int v902; // edx
  int v903; // r8d
  int v904; // r10d
  int v905; // r11d
  unsigned int v906; // r9d
  int v907; // r8d
  unsigned int v908; // r9d
  int v909; // r10d
  int v910; // r11d
  int v911; // edx
  int v912; // r8d
  int v913; // r9d
  int v914; // edx
  int v915; // r10d
  int v916; // r8d
  unsigned int v917; // edx
  int v918; // r8d
  unsigned __int64 j; // rcx
  int v920; // r15d
  void *v921; // rcx
  void *v922; // r9
  void *v923; // r10
  void *v924; // r11
  void *v925; // rdx
  void *v926; // rcx
  void *v927; // r11
  void *v928; // r9
  void *v929; // r10
  unsigned int *v930; // rcx
  __int64 v931; // rdx
  void *v932; // r12
  _DWORD *v933; // r13
  void *v934; // rsi
  void *v935; // r9
  void *v936; // r10
  void *v937; // r11
  void *v938; // rax
  unsigned int v939; // edx
  void *v940; // rcx
  HANDLE v941; // rax
  int v942; // eax
  void *v943; // rcx
  _DWORD *v944; // r9
  int v945; // r10d
  int v946; // r11d
  int *v947; // r15
  int v948; // esi
  unsigned int v949; // r11d
  int v950; // r10d
  void *v951; // r9
  int v952; // r10d
  void **v953; // rdx
  _BYTE *v954; // rax
  SIZE_T v955; // rcx
  unsigned int v956; // r11d
  int v957; // r10d
  void *v958; // r9
  int v959; // r10d
  __int64 v960; // r11
  void *v961; // rcx
  __int64 v962; // rsi
  unsigned int v963; // r11d
  int v964; // r10d
  unsigned int *v965; // r9
  int v966; // r11d
  unsigned int *v967; // rcx
  unsigned int v968; // esi
  int v969; // r10d
  void *v970; // r9
  int v971; // r10d
  unsigned int *v972; // rdx
  void *v973; // rcx
  unsigned int v974; // esi
  unsigned int v975; // r9d
  int v976; // r10d
  int v977; // r9d
  size_t v978; // r11
  int *v979; // rcx
  _DWORD *v980; // rcx
  int v981; // eax
  int v982; // r9d
  int v983; // eax
  int v984; // r9d
  int v985; // eax
  int v986; // r9d
  unsigned int v987; // esi
  HANDLE v988; // rax
  _DWORD *v989; // rsi
  void *v990; // rsi
  HANDLE v991; // rax
  HANDLE v992; // rax
  HANDLE v993; // rax
  HANDLE v994; // rax
  _DWORD *v995; // r9
  unsigned int v996; // r11d
  _DWORD *v997; // rax
  unsigned int v998; // esi
  int v999; // r10d
  unsigned int *v1000; // r9
  int v1001; // r13d
  __int64 v1002; // rdx
  __int64 v1003; // r9
  unsigned int v1004; // r10d
  unsigned int *v1005; // r9
  unsigned int v1006; // r11d
  int v1007; // r10d
  unsigned int *v1008; // r9
  __int64 v1009; // rdx
  __int64 v1010; // r9
  unsigned int v1011; // r10d
  int v1012; // r11d
  unsigned int *v1013; // r9
  unsigned int *v1014; // r10
  int v1015; // r9d
  __int64 v1016; // rdx
  __int64 v1017; // r10
  unsigned int v1018; // r9d
  int v1019; // r11d
  _DWORD *v1020; // r10
  _QWORD *v1021; // rax
  LPVOID v1022; // rcx
  __int64 v1023; // rcx
  unsigned int v1024; // r9d
  int v1025; // r13d
  int v1026; // ecx
  unsigned int v1027; // r10d
  unsigned int v1028; // eax
  unsigned int v1029; // esi
  HANDLE v1030; // rax
  char *v1031; // rax
  char *v1032; // rsi
  unsigned int v1033; // r9d
  LPVOID v1034; // rcx
  HANDLE v1035; // rax
  unsigned int *v1036; // rsi
  _DWORD *v1037; // r13
  int v1038; // ecx
  SIZE_T v1039; // r11
  unsigned __int8 v1040; // al
  SIZE_T v1041; // r8
  unsigned __int8 *v1042; // r9
  unsigned int v1043; // r10d
  unsigned int v1044; // edi
  int v1045; // ebx
  int v1046; // esi
  int v1047; // r8d
  int v1048; // r8d
  unsigned int v1049; // r8d
  unsigned int v1050; // r9d
  unsigned int v1051; // ecx
  int v1052; // edx
  _BYTE *v1053; // rbx
  unsigned int v1054; // edi
  char v1055; // r13
  int v1056; // r9d
  unsigned __int8 *v1057; // rdi
  size_t v1058; // r14
  _BYTE *v1059; // r13
  int v1060; // r12d
  int v1061; // eax
  unsigned int v1062; // r15d
  int v1063; // ecx
  int v1064; // esi
  int v1065; // r11d
  int v1066; // esi
  int v1067; // r11d
  int v1068; // r8d
  int v1069; // r10d
  int v1070; // r8d
  int v1071; // r10d
  int v1072; // r9d
  int v1073; // r8d
  unsigned int v1074; // edx
  int v1075; // r9d
  int v1076; // ecx
  int v1077; // edx
  int v1078; // r8d
  int v1079; // r9d
  int v1080; // edx
  unsigned int v1081; // r8d
  unsigned int v1082; // r9d
  int v1083; // edx
  int v1084; // r8d
  int v1085; // r9d
  int v1086; // edx
  int v1087; // r8d
  int v1088; // r9d
  int v1089; // edx
  int v1090; // r8d
  unsigned int v1091; // r9d
  int v1092; // edx
  unsigned int v1093; // ecx
  int v1094; // r9d
  int v1095; // edx
  HANDLE v1096; // rax
  _DWORD *v1097; // rax
  void *v1098; // rbx
  unsigned int v1099; // ebx
  HANDLE v1100; // rax
  void *v1101; // rax
  HANDLE v1102; // rax
  _OWORD *v1103; // rcx
  SIZE_T v1104; // rax
  HANDLE v1105; // rax
  _QWORD *v1106; // rax
  SIZE_T v1107; // rax
  HANDLE v1108; // rax
  HANDLE v1109; // rax
  HANDLE v1110; // rax
  HANDLE v1111; // rax
  void *v1112; // rcx
  HANDLE v1113; // rax
  _QWORD *v1114; // rax
  HANDLE v1115; // rax
  HANDLE v1116; // rax
  HANDLE v1117; // rax
  HANDLE v1118; // rax
  __int64 v1119; // rdx
  unsigned int v1120; // r9d
  __int64 v1121; // rdx
  unsigned int v1122; // r9d
  __int64 v1123; // rdx
  unsigned int v1124; // ebx
  HANDLE v1125; // rax
  _DWORD *v1126; // rax
  void *v1127; // rdi
  void *v1128; // rcx
  int v1129; // r9d
  SIZE_T v1130; // rcx
  unsigned int *v1131; // r9
  SIZE_T v1132; // rcx
  unsigned int *v1133; // r9
  int v1134; // eax
  HANDLE v1135; // rax
  int LastError; // eax
  int v1137; // eax
  int v1138; // r9d
  __int64 v1139; // rcx
  SIZE_T v1140; // rcx
  unsigned int v1141; // r11d
  int v1142; // r10d
  unsigned int v1143; // ebx
  SIZE_T v1144; // rcx
  unsigned int v1145; // ebx
  HANDLE v1146; // rax
  unsigned int v1147; // r11d
  int v1148; // r10d
  int v1149; // r9d
  unsigned int v1150; // r11d
  unsigned int v1151; // r11d
  unsigned int v1152; // r11d
  unsigned int v1153; // r10d
  bool v1154; // sf
  FARPROC ProcAddress; // rax
  unsigned int v1156; // r9d
  SIZE_T v1157; // rbx
  int v1158; // ecx
  unsigned int v1159; // r10d
  int v1160; // r9d
  int v1161; // r9d
  __int64 v1162; // r10
  unsigned int v1163; // r10d
  int v1164; // r9d
  SIZE_T v1165; // r11
  unsigned int v1166; // r11d
  int v1167; // r9d
  unsigned int v1168; // r10d
  int v1169; // r9d
  unsigned int v1170; // r10d
  int v1171; // r9d
  int v1172; // r10d
  int v1173; // r11d
  HANDLE v1174; // rax
  _QWORD *v1175; // rax
  SIZE_T v1176; // rcx
  HANDLE v1177; // rax
  void *v1178; // rcx
  _QWORD *v1179; // rax
  HANDLE v1180; // rax
  void *v1181; // rcx
  SIZE_T v1182; // rax
  HANDLE v1183; // rax
  void *v1184; // rcx
  _BYTE *v1185; // rcx
  HANDLE v1186; // rax
  HANDLE v1187; // rax
  HANDLE v1188; // rax
  HANDLE v1189; // rax
  unsigned int *v1190; // rdx
  unsigned int *v1191; // rax
  HANDLE v1192; // rax
  HANDLE v1193; // rax
  HANDLE v1194; // rax
  HANDLE v1195; // rax
  _BYTE *v1196; // r10
  size_t v1197; // r11
  unsigned __int8 v1198; // al
  unsigned __int8 *v1199; // r9
  int v1200; // edi
  int v1201; // r11d
  unsigned int v1202; // eax
  int v1203; // ecx
  _BYTE *v1204; // rcx
  unsigned int v1205; // edx
  unsigned int v1206; // r8d
  unsigned int v1207; // r9d
  int v1208; // ebx
  unsigned int v1209; // eax
  int v1210; // edi
  char v1211; // r10
  int v1212; // r9d
  int v1213; // r15d
  SIZE_T v1214; // r14
  int v1215; // r10d
  _BYTE *v1216; // r13
  int v1217; // r12d
  int v1218; // r11d
  unsigned __int8 *v1219; // rax
  int v1220; // ecx
  int v1221; // esi
  int v1222; // ebx
  int v1223; // esi
  int v1224; // edx
  int v1225; // ebx
  unsigned int v1226; // r8d
  int v1227; // r9d
  unsigned int v1228; // edx
  int v1229; // r8d
  int v1230; // r9d
  unsigned int v1231; // edx
  int v1232; // r8d
  int v1233; // r10d
  int v1234; // r11d
  unsigned int v1235; // r9d
  int v1236; // r8d
  unsigned int v1237; // r9d
  int v1238; // r10d
  int v1239; // r11d
  int v1240; // edx
  int v1241; // r8d
  unsigned int v1242; // r9d
  int v1243; // edx
  int v1244; // r10d
  int v1245; // r8d
  unsigned int v1246; // edx
  int v1247; // ecx
  size_t i; // rcx
  void *v1249; // r9
  void *v1250; // rdi
  int v1251; // ecx
  unsigned int *v1252; // r10
  int v1253; // r11d
  __int64 v1254; // rbx
  int v1255; // r11d
  unsigned int v1256; // r11d
  __int64 v1257; // r8
  unsigned int *v1258; // r11
  void *v1259; // r10
  LPVOID v1260; // rax
  unsigned int *v1261; // rbx
  __int64 v1262; // rdx
  unsigned int v1263; // edx
  void *v1264; // rcx
  HANDLE v1265; // rax
  int v1266; // eax
  HANDLE v1267; // rax
  void *v1268; // rbx
  HANDLE v1269; // rax
  void *v1270; // rbx
  HANDLE v1271; // rax
  void *v1272; // rbx
  HANDLE v1273; // rax
  HANDLE v1274; // rax
  void *v1275; // rbx
  HANDLE v1276; // rax
  HANDLE v1277; // rax
  _QWORD *v1278; // rbx
  void *v1279; // rsi
  HANDLE v1280; // rax
  void *v1281; // rsi
  HANDLE v1282; // rax
  void *v1283; // rsi
  HANDLE v1284; // rax
  HANDLE v1285; // rax
  HANDLE v1286; // rax
  unsigned int v1287; // r9d
  __int64 v1288; // r11
  int *v1289; // rcx
  SIZE_T v1290; // rcx
  unsigned int v1291; // r10d
  int v1292; // r9d
  __int64 v1293; // rcx
  __int64 v1294; // r8
  __int64 v1295; // r9
  SIZE_T v1297; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v1298; // [rsp+58h] [rbp-A8h]
  SIZE_T v1299; // [rsp+60h] [rbp-A0h] BYREF
  void *Src; // [rsp+68h] [rbp-98h]
  int v1301; // [rsp+70h] [rbp-90h]
  LPVOID v1302; // [rsp+78h] [rbp-88h] BYREF
  LPVOID v1303; // [rsp+80h] [rbp-80h]
  unsigned int uBytes; // [rsp+88h] [rbp-78h]
  unsigned __int8 uBytes_4; // [rsp+8Ch] [rbp-74h]
  size_t Size; // [rsp+90h] [rbp-70h] BYREF
  LPVOID v1307; // [rsp+98h] [rbp-68h]
  SIZE_T v1308; // [rsp+A0h] [rbp-60h] BYREF
  SIZE_T v1309; // [rsp+A8h] [rbp-58h] BYREF
  SIZE_T v1310; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID v1311; // [rsp+B8h] [rbp-48h] BYREF
  SIZE_T v1312; // [rsp+C0h] [rbp-40h] BYREF
  LPVOID v1313; // [rsp+C8h] [rbp-38h]
  size_t pcchLength; // [rsp+D0h] [rbp-30h] BYREF
  size_t v1315; // [rsp+D8h] [rbp-28h]
  int v1316; // [rsp+E0h] [rbp-20h]
  void *v1317; // [rsp+E8h] [rbp-18h]
  void *v1318; // [rsp+F0h] [rbp-10h] BYREF
  LPVOID v1319; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE *v1320; // [rsp+100h] [rbp+0h]
  void *v1321; // [rsp+108h] [rbp+8h] BYREF
  SIZE_T v1322; // [rsp+110h] [rbp+10h]
  LPVOID lpMem; // [rsp+118h] [rbp+18h] BYREF
  SIZE_T v1324; // [rsp+120h] [rbp+20h]
  int v1325; // [rsp+128h] [rbp+28h]
  SIZE_T v1326; // [rsp+130h] [rbp+30h] BYREF
  LPVOID v1327; // [rsp+138h] [rbp+38h]
  size_t v1328; // [rsp+140h] [rbp+40h] BYREF
  size_t v1329[2]; // [rsp+148h] [rbp+48h] BYREF
  SIZE_T dwBytes; // [rsp+158h] [rbp+58h]
  unsigned int v1331; // [rsp+160h] [rbp+60h] BYREF
  SIZE_T v1332; // [rsp+168h] [rbp+68h] BYREF
  void *v1333; // [rsp+170h] [rbp+70h] BYREF
  size_t v1334[2]; // [rsp+178h] [rbp+78h] BYREF
  void *v1335; // [rsp+188h] [rbp+88h] BYREF
  unsigned int v1336; // [rsp+190h] [rbp+90h] BYREF
  unsigned int v1337; // [rsp+194h] [rbp+94h] BYREF
  STRSAFE_PCNZWCH psz; // [rsp+198h] [rbp+98h]
  unsigned int v1339; // [rsp+1A0h] [rbp+A0h]
  unsigned int v1340; // [rsp+1A4h] [rbp+A4h] BYREF
  unsigned int v1341; // [rsp+1A8h] [rbp+A8h] BYREF
  unsigned int v1342; // [rsp+1ACh] [rbp+ACh]
  unsigned int v1343; // [rsp+1B0h] [rbp+B0h] BYREF
  RPC_WSTR StringUuid; // [rsp+1B8h] [rbp+B8h] BYREF
  unsigned int v1345; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned int v1346; // [rsp+1C4h] [rbp+C4h] BYREF
  unsigned int v1347; // [rsp+1C8h] [rbp+C8h] BYREF
  size_t v1348; // [rsp+1D0h] [rbp+D0h] BYREF
  int v1349; // [rsp+1D8h] [rbp+D8h] BYREF
  int v1350; // [rsp+1DCh] [rbp+DCh] BYREF
  int v1351[4]; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned int v1352; // [rsp+1F0h] [rbp+F0h] BYREF
  int v1353; // [rsp+1F4h] [rbp+F4h] BYREF
  int v1354; // [rsp+1F8h] [rbp+F8h] BYREF
  int v1355; // [rsp+200h] [rbp+100h] BYREF
  HMODULE phModule; // [rsp+208h] [rbp+108h] BYREF
  HMODULE v1357; // [rsp+210h] [rbp+110h] BYREF
  HMODULE hModule; // [rsp+218h] [rbp+118h] BYREF
  HMODULE v1359; // [rsp+220h] [rbp+120h] BYREF
  __int128 v1360; // [rsp+230h] [rbp+130h] BYREF
  __int128 v1361; // [rsp+240h] [rbp+140h]
  __int128 v1362; // [rsp+250h] [rbp+150h] BYREF
  __int128 v1363; // [rsp+260h] [rbp+160h]
  __int128 v1364; // [rsp+270h] [rbp+170h] BYREF
  __int128 v1365; // [rsp+280h] [rbp+180h]
  __int128 v1366; // [rsp+290h] [rbp+190h] BYREF
  __int128 v1367; // [rsp+2A0h] [rbp+1A0h]
  const char *v1368; // [rsp+2B0h] [rbp+1B0h] BYREF
  const unsigned __int16 *v1369; // [rsp+2B8h] [rbp+1B8h] BYREF
  const char *v1370; // [rsp+2C0h] [rbp+1C0h] BYREF
  const char *v1371; // [rsp+2C8h] [rbp+1C8h] BYREF
  const unsigned __int16 *v1372; // [rsp+2D0h] [rbp+1D0h] BYREF
  const char *v1373; // [rsp+2D8h] [rbp+1D8h] BYREF
  const char *v1374; // [rsp+2E0h] [rbp+1E0h] BYREF
  const char *v1375; // [rsp+2E8h] [rbp+1E8h] BYREF
  const char *v1376; // [rsp+2F0h] [rbp+1F0h] BYREF
  const char *v1377; // [rsp+2F8h] [rbp+1F8h] BYREF
  const char *v1378; // [rsp+300h] [rbp+200h] BYREF
  const char *v1379; // [rsp+310h] [rbp+210h] BYREF
  const char *v1380; // [rsp+318h] [rbp+218h] BYREF
  const char *v1381; // [rsp+320h] [rbp+220h] BYREF
  unsigned __int16 *v1382; // [rsp+328h] [rbp+228h]
  const char *v1383; // [rsp+330h] [rbp+230h] BYREF
  const unsigned __int16 *v1384; // [rsp+340h] [rbp+240h] BYREF
  const char *v1385; // [rsp+348h] [rbp+248h] BYREF
  const char *v1386; // [rsp+350h] [rbp+250h] BYREF

  v1382 = a3;
  StringUuid = 0;
  v3 = -2147024809;
  lpMem = 0;
  pcchLength = 0;
  v1335 = 0;
  if ( !a3 )
    return (unsigned int)v3;
  *a3 = 0;
  v4 = 0;
  v5 = 0;
  if ( !UuidToStringW(a1, &StringUuid) )
  {
    v3 = StringCchLengthW(L"TerminalServices-RemoteConnectionManager-", 0x7FFFFFFFu, (unsigned __int64 *)&lpMem);
    if ( v3 < 0 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v1384 = L"TerminalServices-RemoteConnectionManager-";
        v1385 = "GetInitialProgram";
        v1349 = v3;
        v1386 = "CSLQuery::GetInitialProgram - StringCchLength";
        v1368 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          (unsigned int)dword_180128170,
          (__int64)word_18011448A,
          v7,
          v8,
          (const unsigned __int16 **)&v1368,
          (const unsigned __int16 **)&v1386,
          (__int64)&v1349,
          (const unsigned __int16 **)&v1385,
          &v1384);
      }
      goto LABEL_1661;
    }
    v3 = StringCchLengthW(StringUuid, v6, &pcchLength);
    if ( v3 < 0 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v1369 = StringUuid;
        v1370 = "GetInitialProgram";
        v1371 = "CSLQuery::GetInitialProgram - StringCchLength";
        v1377 = "Warning HResult failed";
        v1350 = v3;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v10,
          (__int64)qword_1801147D8,
          v11,
          v12,
          (const unsigned __int16 **)&v1377,
          (const unsigned __int16 **)&v1371,
          (__int64)&v1350,
          (const unsigned __int16 **)&v1370,
          &v1369);
      }
      goto LABEL_1661;
    }
    v3 = StringCchLengthW(L"-InitialProgram", v9, (unsigned __int64 *)&v1335);
    if ( v3 < 0 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v1372 = L"-InitialProgram";
        v1373 = "GetInitialProgram";
        v1351[0] = v3;
        v1374 = "CSLQuery::GetInitialProgram - StringCchLength";
        v1375 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v13,
          (__int64)byte_180113F31,
          v14,
          v15,
          (const unsigned __int16 **)&v1375,
          (const unsigned __int16 **)&v1374,
          (__int64)v1351,
          (const unsigned __int16 **)&v1373,
          &v1372);
      }
      goto LABEL_1661;
    }
    v16 = (unsigned __int64)lpMem + (_QWORD)v1335 + pcchLength + 3;
    v17 = 2 * v16;
    if ( !is_mul_ok(v16, 2u) )
      v17 = -1;
    psz = (STRSAFE_PCNZWCH)operator new(v17, (const struct std::nothrow_t *)std::nothrow);
    v4 = (wchar_t *)psz;
    if ( !psz )
    {
      v3 = -2147024882;
      goto LABEL_1661;
    }
    v3 = StringCchPrintfW(
           (unsigned __int16 *)psz,
           v16,
           L"%ws%ws%ws",
           L"TerminalServices-RemoteConnectionManager-",
           StringUuid,
           L"-InitialProgram");
    if ( v3 < 0 )
    {
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v1355 = v3;
        v1376 = "GetInitialProgram";
        v1383 = "CSLQuery::GetInitialProgram - StringCchPrintf";
        v1378 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (__int64)&dword_180128170,
          (__int64)&word_18011414E,
          0,
          0,
          (const unsigned __int16 **)&v1378,
          (const unsigned __int16 **)&v1383,
          (__int64)&v1355,
          (const unsigned __int16 **)&v1376);
      }
      goto LABEL_1661;
    }
    v1348 = 0;
    v1342 = 0;
    v1335 = 0;
    ProcessHeap = GetProcessHeap();
    v19 = HeapAlloc(ProcessHeap, 8u, 0xA0u);
    if ( !v19 )
    {
      v20 = -1073741801;
LABEL_21:
      v3 = v20;
LABEL_22:
      v21 = v1342;
LABEL_23:
      SP<unsigned char,SP_HLOCAL<unsigned char>>::Reset(&v1335);
      if ( v3 >= 0 )
      {
        if ( v21 )
        {
          v5 = (unsigned __int16 *)v1348;
          v1348 = 0;
        }
        else
        {
          v5 = 0;
        }
        v3 = 0;
      }
      else
      {
        v21 = 0;
        switch ( v3 )
        {
          case -805306316:
            v3 = -1073418222;
            break;
          case -805306139:
          case -1073425151:
            v3 = -1073418201;
            break;
          case -805306306:
            v3 = -1073418200;
            break;
        }
        v5 = 0;
      }
      SP<unsigned char,SP_HLOCAL<unsigned char>>::Reset(&v1348);
      if ( v3 >= 0 )
      {
        if ( v21 + 1 <= 0x100 )
        {
          v3 = StringCchCopyW(v1382, 0x100u, v5);
        }
        else
        {
          v3 = -2147024774;
          if ( (unsigned int)dword_180128170 > 3 && (unsigned __int8)tlgKeywordOn(&dword_180128170, 0) )
          {
            v1354 = v1295;
            v1379 = "GetInitialProgram";
            v1352 = v21;
            v1380 = "CSLQuery::GetInitialProgram - BufferSize";
            v1381 = "Warning HResult failed";
            v1353 = v1294;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v1293,
              (__int64)byte_180114913,
              v1294,
              v1295,
              (const unsigned __int16 **)&v1381,
              (const unsigned __int16 **)&v1380,
              (__int64)&v1353,
              (const unsigned __int16 **)&v1379,
              (__int64)&v1352,
              (__int64)&v1354);
          }
        }
      }
      v4 = (wchar_t *)psz;
      goto LABEL_1661;
    }
    v22 = 0;
    uBytes = 0;
    *v19 = xmmword_180128590;
    v1325 = 0;
    v19[1] = xmmword_1801285A0;
    v19[2] = xmmword_1801285B0;
    v19[3] = xmmword_1801285C0;
    v19[4] = xmmword_1801285D0;
    v19[5] = xmmword_1801285E0;
    v19[6] = xmmword_1801285F0;
    v19[7] = xmmword_180128600;
    v19[8] = xmmword_180128610;
    v19[9] = xmmword_180128620;
    v23 = GetProcessHeap();
    v24 = HeapAlloc(v23, 8u, 8u);
    v1331 = -1;
    Src = v24;
    v3 = -805306219;
    v1327 = (LPVOID)196;
    v1301 = -805306219;
    v1316 = -805306345;
    if ( !v24 )
    {
      v20 = -1073741801;
      v25 = 0;
LABEL_446:
      LODWORD(v1309) = 0;
      LODWORD(v1312) = 0;
      goto LABEL_447;
    }
    *v24 = qword_1801284D0;
    v1326 = __rdtsc();
    pcchLength = 0;
    if ( StringCchLengthW(v4, (unsigned __int64)HIDWORD(v1326) << 32, &pcchLength) < 0 )
    {
      v20 = -1073741762;
LABEL_445:
      v25 = Src;
      goto LABEL_446;
    }
    if ( (unsigned int)(2 * pcchLength + 6) < 4 )
    {
      v20 = -1073741675;
      Src = v26;
      goto LABEL_445;
    }
    v27 = 2 * pcchLength + 202;
    v1319 = 0;
    v28 = 0;
    v29 = 0;
    v30 = -1;
    if ( v27 >= 0xC4 )
      v30 = 2 * pcchLength + 202;
    v20 = v27 < 0xC4 ? -805306219 : 0x10000000;
    if ( v27 < 0xC4 )
      goto LABEL_434;
    v31 = v30 + 8;
    v32 = -1;
    if ( v30 + 8 >= v30 )
      v32 = v30 + 8;
    v20 = v31 < v30 ? -805306219 : 0x10000000;
    if ( v31 < v30 )
      goto LABEL_434;
    v33 = v32 + 8;
    v34 = -1;
    if ( v32 + 8 >= v32 )
      v34 = v32 + 8;
    LODWORD(v1297) = v34;
    v20 = v33 < v32 ? -805306219 : 0x10000000;
    if ( v33 < v32 )
    {
LABEL_434:
      Src = v26;
LABEL_435:
      if ( v20 >= 0 )
      {
LABEL_436:
        if ( v29 )
          v20 = v29;
      }
LABEL_438:
      if ( v28 )
      {
        v304 = GetProcessHeap();
        HeapFree(v304, 0, v28);
      }
      v305 = v1319;
      if ( v1319 )
      {
        v306 = GetProcessHeap();
        HeapFree(v306, 0, v305);
      }
      v25 = Src;
      LODWORD(v1312) = uBytes;
      LODWORD(v1309) = v22;
      if ( !v19 )
      {
LABEL_448:
        if ( v25 )
        {
          v308 = GetProcessHeap();
          HeapFree(v308, 0, v25);
        }
        if ( v20 < 0 )
          goto LABEL_21;
        if ( !v22 )
          goto LABEL_780;
        v309 = GetProcessHeap();
        v310 = HeapAlloc(v309, 8u, 0xA0u);
        v311 = v310;
        if ( !v310 )
          goto LABEL_780;
        *v310 = xmmword_180128590;
        v310[1] = xmmword_1801285A0;
        v310[2] = xmmword_1801285B0;
        v310[3] = xmmword_1801285C0;
        v310[4] = xmmword_1801285D0;
        v310[5] = xmmword_1801285E0;
        v310[6] = xmmword_1801285F0;
        v310[7] = xmmword_180128600;
        v310[8] = xmmword_180128610;
        v310[9] = xmmword_180128620;
        v312 = GetProcessHeap();
        v313 = HeapAlloc(v312, 8u, 8u);
        v314 = v313;
        if ( !v313 )
        {
          v22 = v1309;
          uBytes = v1312;
LABEL_777:
          v593 = GetProcessHeap();
          HeapFree(v593, 0, v311);
LABEL_778:
          if ( v314 )
          {
            v594 = GetProcessHeap();
            HeapFree(v594, 0, v314);
          }
LABEL_780:
          v595 = LocalAlloc(0x40u, uBytes);
          SP<unsigned char,SP_HLOCAL<unsigned char>>::operator=(&v1335, v595);
          v1315 = (size_t)v1335;
          if ( !v1335 )
          {
            v3 = -2147024882;
            goto LABEL_22;
          }
          v1339 = 0;
          *(_OWORD *)v1329 = 0;
          v1319 = 0;
          v596 = GetProcessHeap();
          v597 = HeapAlloc(v596, 8u, 0xA0u);
          v598 = v597;
          if ( !v597 )
          {
            v3 = -1073741801;
            v599 = 0;
            v1301 = -1073741801;
            goto LABEL_813;
          }
          *v597 = xmmword_180128590;
          v597[1] = xmmword_1801285A0;
          v597[2] = xmmword_1801285B0;
          v597[3] = xmmword_1801285C0;
          v597[4] = xmmword_1801285D0;
          v597[5] = xmmword_1801285E0;
          v597[6] = xmmword_1801285F0;
          v597[7] = xmmword_180128600;
          v597[8] = xmmword_180128610;
          v597[9] = xmmword_180128620;
          v600 = GetProcessHeap();
          v601 = HeapAlloc(v600, 8u, 8u);
          v599 = v601;
          if ( !v601 )
          {
            v3 = -1073741801;
            v1301 = -1073741801;
            goto LABEL_813;
          }
          *v601 = qword_1801284D0;
          v1332 = __rdtsc();
          LODWORD(v1308) = 0;
          LODWORD(v1297) = 0;
          v602 = RtlUIntAdd(4, 4, &v1297);
          if ( v602 < 0 )
            goto LABEL_812;
          v602 = RtlUIntAdd(0, (unsigned int)v1297, &v1308) | 0x10000000;
          if ( v602 < 0 )
            goto LABEL_812;
          LODWORD(v1297) = v603;
          v602 = RtlUIntAdd(v604, 160, &v1297);
          if ( v602 < 0 )
            goto LABEL_812;
          v602 = RtlUIntAdd((unsigned int)v1308, (unsigned int)v1297, &v1308) | 0x10000000;
          if ( v602 < 0 )
            goto LABEL_812;
          LODWORD(v1297) = 0;
          v602 = RtlUIntAdd(v605, v605 + 4, &v1297);
          if ( v602 < 0 )
            goto LABEL_812;
          v602 = RtlUIntAdd((unsigned int)v1308, (unsigned int)v1297, &v1308) | 0x10000000;
          if ( v602 < 0 )
            goto LABEL_812;
          LODWORD(v1297) = 0;
          v602 = RtlUIntAdd(v606, v606 + 4, &v1297);
          if ( v602 < 0 )
            goto LABEL_812;
          v602 = RtlUIntAdd((unsigned int)v1308, (unsigned int)v1297, &v1308) | 0x10000000;
          if ( v602 < 0 )
            goto LABEL_812;
          v1328 = 0;
          if ( StringCchLengthW(psz, v607, &v1328) < 0 )
          {
            v3 = -1073741762;
LABEL_1014:
            v1301 = v3;
            goto LABEL_813;
          }
          LODWORD(v1297) = 0;
          v602 = RtlUIntAdd(v608, (unsigned int)(2 * (v1328 + 1)), &v1297);
          if ( v602 < 0
            || (v602 = RtlUIntAdd((unsigned int)v1308, (unsigned int)v1297, &v1308) | 0x10000000, v602 < 0)
            || (LODWORD(v1297) = 0, v602 = RtlUIntAdd(v609, v609, &v1297), v602 < 0)
            || (v602 = RtlUIntAdd((unsigned int)v1308, (unsigned int)v1297, &v1308) | 0x10000000, v602 < 0)
            || (LODWORD(v1297) = 0, v602 = RtlUIntAdd(v610, v610, &v1297), v602 < 0)
            || (v602 = RtlUIntAdd((unsigned int)v1308, (unsigned int)v1297, &v1308) | 0x10000000, v602 < 0) )
          {
LABEL_812:
            v3 = v602;
            v1301 = v602;
            goto LABEL_813;
          }
          HIDWORD(v1329[0]) = v1308;
          v611 = v1308;
          v612 = GetProcessHeap();
          v613 = HeapAlloc(v612, 8u, v611);
          if ( !v613 )
          {
            v3 = -1073741801;
            goto LABEL_1014;
          }
          v1329[1] = (size_t)v613;
          v1320 = 0;
          LODWORD(v1312) = 0;
          LODWORD(v1329[0]) = 0;
          LODWORD(v1321) = 0;
          pcchLength = (size_t)v613;
          LODWORD(Size) = 8;
          v614 = RtlULongLongAdd(v613, 4, &v1321);
          if ( v614 < 0 )
            goto LABEL_809;
          if ( (unsigned __int64)(v613 + 2) > v1329[1] + HIDWORD(v1329[0]) )
            goto LABEL_805;
          v617 = v1321;
          *v613 = 4;
          v618 = Size;
          *v617 = v615;
          v619 = ++LODWORD(v1329[0]);
          v1320 = 0;
          LODWORD(v1321) = 0;
          if ( v598 )
          {
            if ( !v616 )
              goto LABEL_808;
          }
          else if ( v616 )
          {
LABEL_808:
            v614 = -1073741811;
            goto LABEL_809;
          }
          v634 = (unsigned int *)v1329[1];
          if ( v1329[1] )
          {
            pcchLength = v1329[1];
            LODWORD(Size) = 0;
            if ( v619 )
            {
              do
              {
                v635 = *v634;
                LODWORD(v1297) = 0;
                v614 = RtlUIntAdd(4, v635, &v1297);
                if ( v614 < 0 )
                  goto LABEL_809;
                v614 = RtlULongLongAdd(v636, (unsigned int)v1297, &pcchLength);
                if ( v614 < 0 )
                  goto LABEL_809;
                v634 = (unsigned int *)pcchLength;
                LODWORD(Size) = Size + 1;
              }
              while ( (unsigned int)Size < v637 );
            }
            v614 = RtlULongLongAdd(v634, 4, &v1321);
            if ( v614 < 0 )
              goto LABEL_809;
            if ( (unsigned __int64)v638 + v639 + 4 > v1329[1] + HIDWORD(v1329[0]) )
              goto LABEL_805;
            *v638 = v639;
            if ( v598 )
              memcpy_0(v1321, v598, v639);
          }
          else
          {
            LODWORD(v1297) = 0;
            v614 = RtlUIntAdd(4, v616, &v1297);
            if ( v614 < 0 )
              goto LABEL_809;
            v614 = RtlUIntAdd(HIDWORD(v1329[0]), (unsigned int)v1297, (char *)v1329 + 4);
            if ( v614 < 0 )
              goto LABEL_809;
          }
          v640 = ++LODWORD(v1329[0]);
          v1320 = 0;
          LODWORD(v1321) = 0;
          if ( v599 )
          {
            if ( !v618 )
              goto LABEL_808;
          }
          else if ( v618 )
          {
            goto LABEL_808;
          }
          v641 = (unsigned int *)v1329[1];
          if ( v1329[1] )
          {
            pcchLength = v1329[1];
            if ( v640 )
            {
              do
              {
                v642 = *v641;
                LODWORD(v1297) = 0;
                v614 = RtlUIntAdd(4, v642, &v1297);
                if ( v614 < 0 )
                  goto LABEL_809;
                v614 = RtlULongLongAdd(v643, (unsigned int)v1297, &pcchLength);
                if ( v614 < 0 )
                  goto LABEL_809;
                v641 = (unsigned int *)pcchLength;
              }
              while ( v645 + 1 < v644 );
            }
            v614 = RtlULongLongAdd(v641, 4, &v1321);
            if ( v614 < 0 )
              goto LABEL_809;
            if ( (unsigned __int64)v646 + v618 + 4 > v1329[1] + HIDWORD(v1329[0]) )
              goto LABEL_805;
            *v646 = v618;
            if ( v599 )
              memcpy_0(v1321, v599, v618);
          }
          else
          {
            LODWORD(v1297) = 0;
            v614 = RtlUIntAdd(4, v618, &v1297);
            if ( v614 < 0 )
              goto LABEL_809;
            v614 = RtlUIntAdd(HIDWORD(v1329[0]), (unsigned int)v1297, (char *)v1329 + 4);
            if ( v614 < 0 )
              goto LABEL_809;
          }
          v647 = (unsigned int *)v1329[1];
          v648 = ++LODWORD(v1329[0]);
          v1320 = 0;
          LODWORD(v1321) = 0;
          if ( v1329[1] )
          {
            pcchLength = v1329[1];
            if ( v648 )
            {
              do
              {
                v650 = *v647;
                LODWORD(v1297) = 0;
                v614 = RtlUIntAdd(4, v650, &v1297);
                if ( v614 < 0 )
                  goto LABEL_809;
                v614 = RtlULongLongAdd(v651, (unsigned int)v1297, &pcchLength);
                if ( v614 < 0 )
                  goto LABEL_809;
                v647 = (unsigned int *)pcchLength;
              }
              while ( v653 + 1 < v652 );
            }
            v614 = RtlULongLongAdd(v647, 4, &v1321);
            if ( v614 < 0 )
              goto LABEL_809;
            if ( (unsigned __int64)(v654 + 3) > v1329[1] + HIDWORD(v1329[0]) )
              goto LABEL_805;
            v655 = v1321;
            v656 = v1332;
            *v654 = 8;
            *v655 = v656;
          }
          else
          {
            LODWORD(v1297) = 0;
            v614 = RtlUIntAdd(4, 8, &v1297);
            if ( v614 < 0 )
              goto LABEL_809;
            v614 = RtlUIntAdd(HIDWORD(v1329[0]), (unsigned int)v1297, (char *)v1329 + 4);
            if ( v614 < 0 )
              goto LABEL_809;
          }
          ++LODWORD(v1329[0]);
          lpMem = 0;
          if ( StringCchLengthW(psz, v649, (size_t *)&lpMem) < 0 )
          {
            v614 = -1073741762;
            goto LABEL_809;
          }
          v614 = RtlULongLongAdd(lpMem, 1, &lpMem);
          if ( v614 < 0 )
            goto LABEL_809;
          v1320 = 0;
          LODWORD(v1321) = 0;
          if ( !(2 * (_DWORD)lpMem) )
            goto LABEL_808;
          v658 = (unsigned int *)v1329[1];
          if ( v1329[1] )
          {
            v659 = 0;
            pcchLength = v1329[1];
            if ( v657 )
            {
              do
              {
                v660 = *v658;
                LODWORD(v1297) = 0;
                v614 = RtlUIntAdd(4, v660, &v1297);
                if ( v614 < 0 )
                  goto LABEL_809;
                v614 = RtlULongLongAdd(v661, (unsigned int)v1297, &pcchLength);
                if ( v614 < 0 )
                  goto LABEL_809;
                v658 = (unsigned int *)pcchLength;
              }
              while ( ++v659 < v662 );
            }
            v614 = RtlULongLongAdd(v658, 4, &v1321);
            if ( v614 < 0 )
              goto LABEL_809;
            if ( (unsigned __int64)v663 + v664 + 4 > v1329[1] + HIDWORD(v1329[0]) )
              goto LABEL_805;
            v665 = psz;
            v666 = v1321;
            *v663 = v664;
            memcpy_0(v666, v665, (unsigned int)v664);
          }
          else
          {
            LODWORD(v1297) = 0;
            v614 = RtlUIntAdd(4, (unsigned int)(2 * (_DWORD)lpMem), &v1297);
            if ( v614 < 0 )
              goto LABEL_809;
            v614 = RtlUIntAdd(HIDWORD(v1329[0]), (unsigned int)v1297, (char *)v1329 + 4);
            if ( v614 < 0 )
              goto LABEL_809;
          }
          v667 = (unsigned int *)v1329[1];
          v668 = ++LODWORD(v1329[0]);
          v1320 = 0;
          LODWORD(v1321) = 0;
          if ( v1329[1] )
          {
            pcchLength = v1329[1];
            if ( v668 )
            {
              do
              {
                v669 = *v667;
                LODWORD(v1297) = 0;
                v614 = RtlUIntAdd(4, v669, &v1297);
                if ( v614 < 0 )
                  goto LABEL_809;
                v614 = RtlULongLongAdd(v670, (unsigned int)v1297, &pcchLength);
                if ( v614 < 0 )
                  goto LABEL_809;
                v667 = (unsigned int *)pcchLength;
              }
              while ( v672 + 1 < v671 );
            }
            v614 = RtlULongLongAdd(v667, 4, &v1321);
            if ( v614 < 0 )
              goto LABEL_809;
            if ( (unsigned __int64)(v673 + 2) > v1329[1] + HIDWORD(v1329[0]) )
              goto LABEL_805;
            v674 = v1321;
            *v673 = 4;
            *v674 = v22;
          }
          else
          {
            LODWORD(v1297) = 0;
            v614 = RtlUIntAdd(4, 4, &v1297);
            if ( v614 < 0 )
              goto LABEL_809;
            v614 = RtlUIntAdd(HIDWORD(v1329[0]), (unsigned int)v1297, (char *)v1329 + 4);
            if ( v614 < 0 )
              goto LABEL_809;
          }
          v675 = (unsigned int *)v1329[1];
          v676 = ++LODWORD(v1329[0]);
          v1320 = 0;
          LODWORD(v1321) = 0;
          if ( !v1329[1] )
          {
            LODWORD(v1297) = 0;
            v614 = RtlUIntAdd(4, 4, &v1297);
            if ( v614 < 0 )
              goto LABEL_809;
            v614 = RtlUIntAdd(HIDWORD(v1329[0]), (unsigned int)v1297, (char *)v1329 + 4);
            if ( v614 < 0 )
              goto LABEL_809;
LABEL_903:
            ++LODWORD(v1329[0]);
            LODWORD(v1297) = 0;
            v614 = RtlUIntAdd(4, 4, &v1297);
            if ( v614 < 0 )
              goto LABEL_809;
            LODWORD(v1309) = v1297;
            LODWORD(v1297) = 0;
            v614 = RtlUIntAdd(v683, 8, &v1297);
            if ( v614 < 0 )
              goto LABEL_809;
            v614 = RtlUIntAdd(v684, (unsigned int)v1297, &v1309);
            if ( v614 < 0 )
              goto LABEL_809;
            LODWORD(v1297) = 0;
            v614 = RtlUIntAdd(4, 4, &v1297);
            if ( v614 < 0 )
              goto LABEL_809;
            v614 = RtlUIntAdd((unsigned int)v1309, (unsigned int)v1297, &v1309);
            if ( v614 < 0 )
              goto LABEL_809;
            LODWORD(v1297) = 0;
            v614 = RtlUIntAdd(4, v685, &v1297);
            if ( v614 < 0 )
              goto LABEL_809;
            v614 = RtlUIntAdd((unsigned int)v1309, (unsigned int)v1297, &v1309);
            if ( v614 < 0 )
              goto LABEL_809;
            LODWORD(v1297) = 0;
            v614 = RtlUIntAdd(4, 4, &v1297);
            if ( v614 < 0 )
              goto LABEL_809;
            v614 = RtlUIntAdd((unsigned int)v1309, (unsigned int)v1297, &v1309);
            if ( v614 < 0 )
              goto LABEL_809;
            LODWORD(v1297) = 0;
            v614 = RtlUIntAdd(4, 4, &v1297);
            if ( v614 < 0 )
              goto LABEL_809;
            v614 = RtlUIntAdd((unsigned int)v1309, (unsigned int)v1297, &v1309);
            if ( v614 < 0 )
              goto LABEL_809;
            LODWORD(v1308) = v1309;
            LODWORD(Size) = 0;
            v1298 = 0;
            v1320 = (_BYTE *)__rdtsc();
            v1336 = 8;
            LODWORD(v1297) = 0;
            v686 = RtlUIntAdd(8, HIDWORD(v1329[0]), &v1336);
            if ( v686 < 0 )
            {
              v1317 = v599;
              v1311 = v598;
              v1325 = v22;
            }
            else
            {
              v688 = (v1336 + 7) & 0xFFFFFFF8;
              if ( v688 < v1336 )
                goto LABEL_813;
              v1336 = (v1336 + 7) & 0xFFFFFFF8;
              v689 = v688;
              v690 = GetProcessHeap();
              v691 = HeapAlloc(v690, 8u, v689);
              if ( !v691 )
              {
                v3 = -805306345;
                v1301 = -805306345;
                goto LABEL_1011;
              }
              v1325 = v22;
              v1311 = v598;
              v1317 = v599;
              lpMem = v691;
              *v691 = v1329[0];
              LODWORD(v1324) = RtlULongLongAdd(v691, 4, &lpMem);
              if ( (v1324 & 0x80000000) != 0LL
                || (v694 = lpMem,
                    *(_DWORD *)lpMem = HIDWORD(v1329[0]),
                    LODWORD(v1324) = RtlULongLongAdd(v694, v693, &lpMem),
                    (v1324 & 0x80000000) != 0LL) )
              {
                v1325 = v22;
                v1311 = v598;
                v1317 = v599;
                LODWORD(v1308) = v692;
                v695 = GetProcessHeap();
                HeapFree(v695, 0, v691);
                v686 = v1324;
                v687 = v1297;
              }
              else
              {
                *(_QWORD *)((char *)v691 + v1336 - 8) = v1320;
                memcpy_0(lpMem, (const void *)v1329[1], HIDWORD(v1329[0]));
                v687 = v1336;
                v686 = v1324;
                v1298 = v691;
              }
            }
            v1303 = 0;
            v1307 = 0;
            v696 = 0;
            dwBytes = 0;
            v1302 = 0;
            v3 = v686 | 0x10000000;
            v1313 = 0;
            v1301 = v686 | 0x10000000;
            if ( v686 < 0 )
              goto LABEL_986;
            v697 = (unsigned __int8 *)v1298;
            if ( !v1298 )
            {
              v3 = -805306355;
              goto LABEL_1014;
            }
            v1326 = v687;
            if ( !v687 || (lpMem = (LPVOID)(v687 + 8LL), (v1310 = (SIZE_T)MemoryAlloc((unsigned __int64)lpMem)) == 0) )
            {
              v3 = -805306367;
              v1301 = -805306367;
              goto LABEL_988;
            }
            v698 = v1326;
            v699 = 0;
            v700 = 0;
            v1299 = 0;
            uBytes_4 = 0;
            if ( v1326 )
            {
              do
                v699 ^= v697[v700++];
              while ( v700 < v1326 );
              uBytes_4 = v699;
            }
            pcchLength = v1310;
            v701 = v697;
            Src = (void *)0xC81ECB17B1B54A58LL;
            v1318 = v697;
            v702 = v1326 & 7;
            if ( (v1326 & 7) != 0 )
            {
              v703 = 0;
              LODWORD(v1324) = 0;
              LODWORD(v1322) = 0;
              v704 = 0;
              v705 = 0;
              do
              {
                v706 = *v701++;
                LODWORD(v1297) = 8 * v703;
                if ( v703 >= 4 )
                  v704 |= v706 << (56 - v1297);
                else
                  v705 |= v706 << (24 - v1297);
                ++v703;
              }
              while ( (int)v703 < v702 );
              LODWORD(v1322) = v705;
              LODWORD(v1324) = v704;
              v1318 = v701;
              v1298 = v697;
              v1317 = v599;
              v1311 = v598;
              v1325 = v22;
              LODWORD(v1309) = 0;
              v707 = v704 ^ 0x42F6B18D;
              v708 = v705 ^ 0xB17A307A;
              v709 = v705 ^ 0xB17A307A;
              v710 = v704 ^ 0x42F6B18D;
              if ( (v1326 & 7) != 0 )
              {
                v711 = (_BYTE *)pcchLength;
                do
                {
                  v1320 = v711 + 1;
                  if ( (unsigned int)v1309 >= 4 )
                  {
                    v710 = __ROR4__(v710, 24);
                    v712 = v710;
                  }
                  else
                  {
                    v709 = __ROR4__(v709, 24);
                    v712 = v709;
                  }
                  *v711 = v712;
                  LODWORD(v1309) = v1309 + 1;
                  v711 = v1320;
                }
                while ( (int)v1309 < v702 );
                pcchLength = (size_t)v1320;
              }
              if ( (unsigned int)v702 <= 4 )
              {
                v713 = 0;
                if ( (unsigned int)v702 < 4 )
                  v708 = v708 >> (8 * (4 - v702)) << (8 * (4 - v702));
              }
              else
              {
                v713 = v707 >> (8 * (8 - v702)) << (8 * (8 - v702));
              }
              v701 = (unsigned __int8 *)v1318;
            }
            else
            {
              v708 = 0;
              LODWORD(v1322) = 0;
              v713 = -1;
              LODWORD(v1324) = 0;
            }
            if ( v698 >> 3 )
            {
              v714 = (_BYTE *)pcchLength;
              v715 = v698 >> 3;
              v716 = v1322;
              v717 = WORD2(Src);
              LODWORD(v1297) = 19032;
              LODWORD(v1309) = WORD1(Src);
              v718 = v1324;
              v1328 = 0;
              do
              {
                v719 = v701[3] | ((v701[2] | ((v701[1] | (*v701 << 8)) << 8)) << 8);
                v720 = *((unsigned __int8 *)v1318 + 7)
                     | ((*((unsigned __int8 *)v1318 + 6) | ((*((unsigned __int8 *)v1318 + 5) | (v701[4] << 8)) << 8)) << 8);
                v1318 = (char *)v1318 + 8;
                v721 = v713 ^ v720;
                v722 = v708 ^ v719 ^ HIDWORD(Src) ^ ((v713 ^ v720) - 19032);
                v723 = v721 ^ (__ROR4__(v722, 7) + WORD1(Src) * __ROR4__(v722 ^ HIDWORD(Src), 15));
                v724 = v722 ^ (v717 * __ROR4__(v723 - 1313519016, 9) - __ROR4__(v723, 10));
                v725 = v723 ^ (__ROR4__(v724, 27) + HIWORD(Src) * __ROR4__(v717 ^ v724, 28));
                v726 = v724 ^ (HIDWORD(Src) - (v725 ^ 0xB1B54A58));
                v727 = v725 ^ (WORD1(Src) * (v726 - 19032) - (v726 >> 6));
                v728 = v726 ^ (19032 * (v717 ^ __ROR4__(v727, 15)));
                v729 = v727 ^ (v717 * (HIWORD(Src) + __ROR4__(~v728, 3)));
                v730 = v728 ^ (v729 - 19032 - HIDWORD(Src));
                v731 = v729 ^ (v1309 * (v730 ^ HIWORD(Src))) ^ __ROR4__(v730, 10);
                v732 = v730 ^ __ROR4__(v731, 3) ^ (v717 * __ROR4__(v731 ^ 0x4A58, 26));
                v733 = v731 ^ (19032 * (__ROR4__(v732, 15) - HIWORD(Src)));
                v734 = v732
                     ^ ((v733 ^ (v733 >> 14)) >> 1)
                     ^ (19032 * (v733 ^ HIWORD(Src)))
                     ^ (19032 * ((8 * (v733 - v717)) | ((v733 - v717) >> 29)));
                v735 = v733 ^ (WORD1(Src) * (v734 - v717) - (v734 >> 13));
                v736 = v734 ^ __ROR4__(v735, 11) ^ (v717 * __ROR4__(-1313519016 - v735, 9));
                v737 = v735 ^ (v736 - HIWORD(Src) + 1313519016);
                v738 = v736 ^ (19032 * (v737 ^ WORD1(Src)) - __ROR4__(v737, 7));
                v739 = v737 ^ (WORD1(Src) * __ROR4__(v738 ^ HIWORD(Src), 28) - __ROR4__(v738, 16));
                v740 = v738 ^ (__ROR4__(v739, 4) + v717 * __ROR4__(-1313519016 - v739, 10));
                v741 = v739 ^ __ROR4__(v740, 9) ^ (HIWORD(Src) * __ROR4__(v740 + 1313519016, 4));
                v742 = v740 ^ (19032 * __ROR4__(v741 ^ HIDWORD(Src), 24) - __ROR4__(v741, 30));
                v743 = v741 ^ (WORD1(Src) * __ROR4__(HIDWORD(Src) - v742, 11) - __ROR4__(v742, 12));
                v744 = v743 ^ WORD1(Src);
                v745 = v743 >> 8;
                v746 = v718 ^ HIDWORD(Src) ^ v743;
                v718 = v720;
                v701 = (unsigned __int8 *)v1318;
                v747 = v742 ^ v745 ^ (v717 * v744);
                v708 = v747 ^ v716;
                v714[3] = v747 ^ v716;
                v713 = v747 ^ v746 ^ 0xB1B54A58;
                v714[7] = v713;
                LOBYTE(v745) = __ROR4__(v747 ^ v716, 8);
                v716 = v719;
                v714[2] = v745;
                v714[6] = __ROR4__(v713, 8);
                v714[1] = __ROR4__(v708, 16);
                v714[5] = __ROR4__(v713, 16);
                *v714 = __ROR4__(v708, 24);
                v714[4] = __ROR4__(v713, 24);
                v714 += 8;
                ++v1328;
              }
              while ( v1328 < v715 );
              v699 = uBytes_4;
              v22 = v1325;
              v598 = v1311;
              v599 = v1317;
              v696 = v1302;
              v697 = (unsigned __int8 *)v1298;
              v698 = v1326;
            }
            *(_QWORD *)(v1310 + v698) = v699;
            v748 = GetProcessHeap();
            v749 = HeapAlloc(v748, 8u, 0x30u);
            v1327 = v749;
            if ( v749 )
            {
              *v749 = (_DWORD)lpMem;
              v758 = GetProcessHeap();
              v759 = HeapAlloc(v758, 8u, (unsigned int)lpMem);
              if ( v759 )
              {
                v1298 = v697;
                v760 = v1327;
                *((_QWORD *)v1327 + 1) = v759;
                memcpy_0(v759, (const void *)v1310, (unsigned int)lpMem);
                v760[4] = 160;
                v761 = GetProcessHeap();
                v762 = HeapAlloc(v761, 8u, 0xA0u);
                if ( v762 )
                {
                  *((_QWORD *)v760 + 3) = v762;
                  *v762 = xmmword_1801284E0;
                  v762[1] = xmmword_1801284F0;
                  v762[2] = xmmword_180128500;
                  v762[3] = xmmword_180128510;
                  v762[4] = xmmword_180128520;
                  v762[5] = xmmword_180128530;
                  v762[6] = xmmword_180128540;
                  v762[7] = xmmword_180128550;
                  v762[8] = xmmword_180128560;
                  v762[9] = xmmword_180128570;
                  v760[8] = 8;
                  v763 = GetProcessHeap();
                  v764 = HeapAlloc(v763, 8u, 8u);
                  if ( v764 )
                  {
                    *((_QWORD *)v760 + 5) = v764;
                    *v764 = qword_180128580;
                    v1299 = (SIZE_T)v760;
                    v750 = 0;
                    v751 = (void *)v1299;
                    v1299 = 0;
LABEL_954:
                    v1303 = v751;
                    v752 = GetProcessHeap();
                    HeapFree(v752, 0, (LPVOID)v1310);
                    v753 = v1299;
                    if ( v1299 )
                    {
                      v1320 = *(_BYTE **)(v1299 + 8);
                      if ( v1320 )
                      {
                        v754 = GetProcessHeap();
                        HeapFree(v754, 0, v1320);
                        v753 = v1299;
                        *(_QWORD *)(v1299 + 8) = 0;
                      }
                      v1320 = *(_BYTE **)(v753 + 24);
                      if ( v1320 )
                      {
                        v755 = GetProcessHeap();
                        HeapFree(v755, 0, v1320);
                        v753 = v1299;
                        *(_QWORD *)(v1299 + 24) = 0;
                      }
                      v1320 = *(_BYTE **)(v753 + 40);
                      if ( v1320 )
                      {
                        v756 = GetProcessHeap();
                        HeapFree(v756, 0, v1320);
                        *(_QWORD *)(v1299 + 40) = 0;
                      }
                      v757 = GetProcessHeap();
                      HeapFree(v757, 0, (LPVOID)v1299);
                    }
                    v3 = v750 | 0x10000000;
                    v1301 = v3;
                    if ( v3 < 0 )
                    {
                      v779 = v1298;
LABEL_987:
                      if ( !v779 )
                      {
LABEL_989:
                        v781 = v1303;
                        if ( v1303 )
                        {
                          v1320 = (_BYTE *)*((_QWORD *)v1303 + 1);
                          if ( v1320 )
                          {
                            v782 = GetProcessHeap();
                            HeapFree(v782, 0, v1320);
                            v781 = v1303;
                            *((_QWORD *)v1303 + 1) = 0;
                          }
                          v1320 = (_BYTE *)v781[3];
                          if ( v1320 )
                          {
                            v783 = GetProcessHeap();
                            HeapFree(v783, 0, v1320);
                            v781 = v1303;
                            *((_QWORD *)v1303 + 3) = 0;
                          }
                          v1320 = (_BYTE *)v781[5];
                          if ( v1320 )
                          {
                            v784 = GetProcessHeap();
                            HeapFree(v784, 0, v1320);
                            *((_QWORD *)v1303 + 5) = 0;
                          }
                          v785 = GetProcessHeap();
                          HeapFree(v785, 0, v1303);
                        }
                        if ( dwBytes )
                        {
                          v786 = GetProcessHeap();
                          HeapFree(v786, 0, (LPVOID)dwBytes);
                        }
                        if ( v696 )
                        {
                          v787 = GetProcessHeap();
                          HeapFree(v787, 0, v696);
                        }
                        v788 = v1307;
                        if ( v1307 )
                        {
                          v1320 = (_BYTE *)*((_QWORD *)v1307 + 1);
                          if ( v1320 )
                          {
                            v789 = GetProcessHeap();
                            HeapFree(v789, 0, v1320);
                            v788[1] = 0;
                          }
                          v1320 = (_BYTE *)v788[3];
                          if ( v1320 )
                          {
                            v790 = GetProcessHeap();
                            HeapFree(v790, 0, v1320);
                            v788[3] = 0;
                          }
                          v1320 = (_BYTE *)v788[5];
                          if ( v1320 )
                          {
                            v791 = GetProcessHeap();
                            HeapFree(v791, 0, v1320);
                            v788[5] = 0;
                          }
                          v792 = GetProcessHeap();
                          HeapFree(v792, 0, v788);
                        }
                        v793 = v1313;
                        if ( v1313 )
                        {
                          v794 = GetProcessHeap();
                          HeapFree(v794, 0, v793);
                        }
LABEL_1011:
                        if ( v3 < 0 )
                          goto LABEL_813;
                        if ( !(_DWORD)Size )
                          goto LABEL_1013;
                        if ( v1319 )
                        {
                          v1328 = (size_t)v1319;
                          v1301 = RtlULongLongAdd(v1319, 4, &v1328);
                          v3 = v1301;
                          v1319 = v944;
                          if ( v1301 < 0 )
                            goto LABEL_810;
                          v947 = (int *)v1328;
                          if ( !*v944 )
                            v947 = 0;
                          if ( *v944 == v946 )
                          {
                            v3 = *v947;
                            v1301 = v3;
                            if ( v3 == -805306333 )
                            {
                              v948 = -2147024774;
                              LODWORD(v1312) = -2147024774;
                            }
                            else
                            {
                              LODWORD(v1312) = v3;
                              v948 = v3;
                              if ( v3 != -2147024774 && v3 < 0 )
                                goto LABEL_813;
                            }
                            v1319 = v944;
                            if ( v945 != 6 )
                            {
LABEL_1013:
                              v3 = -1073425151;
                              goto LABEL_1014;
                            }
                            v1318 = v943;
                            while ( 1 )
                            {
                              v1301 = RtlULongLongAdd(v943, 4, &v1318);
                              v3 = v1301;
                              if ( v1301 < 0 )
                                break;
                              v1301 = RtlULongLongAdd(v1318, v949, &v1318);
                              v3 = v1301;
                              if ( v1301 < 0 )
                                break;
                              v943 = v1318;
                              if ( v950 != -1 )
                              {
                                v1301 = RtlULongLongAdd(v1318, 4, &v1318);
                                v3 = v1301;
                                if ( v1301 < 0 )
                                  break;
                                v953 = (void **)v1318;
                                if ( !v952 )
                                  v953 = 0;
                                if ( v952 != 8 )
                                  goto LABEL_1250;
                                v1319 = v951;
                                if ( !v951 )
                                {
LABEL_1253:
                                  v3 = -1073741811;
                                  goto LABEL_1014;
                                }
                                v954 = *v953;
                                v955 = (SIZE_T)v951;
                                v1310 = (SIZE_T)v951;
                                v1320 = v954;
                                LODWORD(v1312) = v948;
                                while ( 1 )
                                {
                                  v1301 = RtlULongLongAdd(v955, 4, &v1310);
                                  v3 = v1301;
                                  if ( v1301 < 0 )
                                    goto LABEL_813;
                                  v1301 = RtlULongLongAdd(v1310, v956, &v1310);
                                  v3 = v1301;
                                  if ( v1301 < 0 )
                                    goto LABEL_813;
                                  v955 = v1310;
                                  if ( (unsigned int)(v957 + 1) >= 2 )
                                  {
                                    v1301 = RtlULongLongAdd(v1310, 4, &v1310);
                                    v3 = v1301;
                                    if ( v1301 < 0 )
                                      goto LABEL_813;
                                    if ( v959 != (_DWORD)v960 )
                                    {
LABEL_1262:
                                      v3 = -1073741789;
                                      goto LABEL_1014;
                                    }
                                    v1319 = v958;
                                    if ( !v958 )
                                      goto LABEL_1233;
                                    v961 = v958;
                                    LODWORD(v1312) = v948;
                                    v1318 = v958;
                                    v962 = v960;
                                    while ( 1 )
                                    {
                                      v1301 = RtlULongLongAdd(v961, v962, &v1318);
                                      v3 = v1301;
                                      if ( v1301 < 0 )
                                        goto LABEL_810;
                                      v1301 = RtlULongLongAdd(v1318, v963, &v1318);
                                      v3 = v1301;
                                      if ( v1301 < 0 )
                                        goto LABEL_810;
                                      v961 = v1318;
                                      if ( (unsigned int)(v964 + 1) >= 3 )
                                      {
                                        v1301 = RtlULongLongAdd(v1318, v962, &v1318);
                                        v3 = v1301;
                                        if ( v1301 >= 0 )
                                        {
                                          if ( v966 )
                                            v1328 = (size_t)v1318;
                                          else
                                            v1328 = 0;
                                          v967 = v965;
                                          v1318 = v965;
                                          while ( 1 )
                                          {
                                            v968 = *v967;
                                            v1301 = RtlULongLongAdd(v967, 4, &v1318);
                                            v3 = v1301;
                                            if ( v1301 < 0 )
                                              break;
                                            v1301 = RtlULongLongAdd(v1318, v968, &v1318);
                                            v3 = v1301;
                                            if ( v1301 < 0 )
                                              break;
                                            v967 = (unsigned int *)v1318;
                                            if ( (unsigned int)(v969 + 1) >= 4 )
                                            {
                                              v1301 = RtlULongLongAdd(v1318, 4, &v1318);
                                              v3 = v1301;
                                              if ( v1301 < 0 )
                                                goto LABEL_810;
                                              v972 = (unsigned int *)v1318;
                                              if ( !v971 )
                                                v972 = 0;
                                              if ( v971 != 4 )
                                                goto LABEL_1250;
                                              v1319 = v970;
                                              if ( !v970 )
                                                goto LABEL_1253;
                                              v973 = v970;
                                              v974 = *v972;
                                              v1318 = v970;
                                              while ( 1 )
                                              {
                                                v1301 = RtlULongLongAdd(v973, 4, &v1318);
                                                v3 = v1301;
                                                if ( v1301 < 0 )
                                                  goto LABEL_813;
                                                v1301 = RtlULongLongAdd(v1318, v975, &v1318);
                                                v3 = v1301;
                                                if ( v1301 < 0 )
                                                  goto LABEL_813;
                                                v973 = v1318;
                                                if ( (unsigned int)(v976 + 1) >= 5 )
                                                {
                                                  v1301 = RtlULongLongAdd(v1318, 4, &v1318);
                                                  v3 = v1301;
                                                  if ( v1301 < 0 )
                                                    goto LABEL_1014;
                                                  v979 = (int *)v1318;
                                                  if ( !v977 )
                                                    v979 = 0;
                                                  if ( v977 != 4 )
                                                    goto LABEL_1262;
                                                  if ( (_BYTE *)v1332 != v1320 )
                                                    goto LABEL_1013;
                                                  v22 = *v979;
                                                  v1339 = v974;
                                                  if ( uBytes )
                                                  {
                                                    if ( uBytes < v974 || uBytes < (unsigned int)v978 )
                                                    {
                                                      v3 = -2147024774;
                                                      goto LABEL_1014;
                                                    }
                                                    memcpy_0((void *)v1315, (const void *)v1328, v978);
                                                  }
                                                  goto LABEL_811;
                                                }
                                              }
                                            }
                                          }
                                        }
                                        goto LABEL_810;
                                      }
                                    }
                                  }
                                }
                              }
                            }
LABEL_810:
                            if ( v3 < 0 )
                              goto LABEL_813;
LABEL_811:
                            v602 = v1312;
                            if ( (_DWORD)v1312 )
                              goto LABEL_812;
LABEL_813:
                            v620 = (void *)v1329[1];
                            v1329[0] = 0;
                            if ( v1329[1] )
                            {
                              v621 = GetProcessHeap();
                              HeapFree(v621, 0, v620);
                              v1329[1] = 0;
                            }
                            v622 = v1319;
                            if ( v1319 )
                            {
                              v623 = GetProcessHeap();
                              HeapFree(v623, 0, v622);
                            }
                            if ( v598 )
                            {
                              v624 = GetProcessHeap();
                              HeapFree(v624, 0, v598);
                            }
                            if ( v599 )
                            {
                              v625 = GetProcessHeap();
                              HeapFree(v625, 0, v599);
                            }
                            if ( v3 < 0 )
                              goto LABEL_22;
                            if ( !v22 )
                            {
LABEL_1289:
                              v21 = v1339;
                              v1348 = v1315;
                              v1335 = 0;
                              goto LABEL_23;
                            }
                            v626 = 0;
                            v627 = 0;
                            v1307 = 0;
                            *(_OWORD *)v1334 = 0;
                            v628 = GetProcessHeap();
                            v629 = HeapAlloc(v628, 8u, 0xA0u);
                            v630 = v629;
                            if ( !v629 )
                            {
LABEL_1281:
                              v990 = (void *)v1334[1];
                              v1334[0] = 0;
                              if ( v1334[1] )
                              {
                                v991 = GetProcessHeap();
                                HeapFree(v991, 0, v990);
                                v1334[1] = 0;
                              }
                              if ( v627 )
                              {
                                v992 = GetProcessHeap();
                                HeapFree(v992, 0, v627);
                              }
                              if ( v630 )
                              {
                                v993 = GetProcessHeap();
                                HeapFree(v993, 0, v630);
                              }
                              if ( v626 )
                              {
                                v994 = GetProcessHeap();
                                HeapFree(v994, 0, v626);
                              }
                              goto LABEL_1289;
                            }
                            *v629 = xmmword_180128590;
                            v629[1] = xmmword_1801285A0;
                            v629[2] = xmmword_1801285B0;
                            v629[3] = xmmword_1801285C0;
                            v629[4] = xmmword_1801285D0;
                            v629[5] = xmmword_1801285E0;
                            v629[6] = xmmword_1801285F0;
                            v629[7] = xmmword_180128600;
                            v629[8] = xmmword_180128610;
                            v629[9] = xmmword_180128620;
                            v631 = GetProcessHeap();
                            v632 = HeapAlloc(v631, 8u, 8u);
                            v633 = v632;
                            if ( !v632 )
                            {
                              v627 = 0;
                              goto LABEL_1281;
                            }
                            *v632 = qword_1801284D0;
                            v1320 = (_BYTE *)__rdtsc();
                            LODWORD(v1297) = 0;
                            LODWORD(v1312) = 0;
                            if ( (int)RtlUIntAdd(4, 4, &v1297) < 0 )
                              goto LABEL_1279;
                            if ( (int)RtlUIntAdd(0, (unsigned int)v1297, &v1312) < 0 )
                            {
                              v626 = v633;
                              v627 = v980;
                              goto LABEL_1281;
                            }
                            LODWORD(v1297) = (_DWORD)v980;
                            if ( (int)RtlUIntAdd(4, 160, &v1297) < 0 )
                              goto LABEL_1279;
                            v981 = RtlUIntAdd((unsigned int)v1312, (unsigned int)v1297, &v1312);
                            if ( (v982 | v981) < 0 )
                              goto LABEL_1279;
                            LODWORD(v1297) = 0;
                            if ( (int)RtlUIntAdd(4, 8, &v1297) < 0
                              || (v983 = RtlUIntAdd((unsigned int)v1312, (unsigned int)v1297, &v1312), (v984 | v983) < 0)
                              || (LODWORD(v1297) = 0, (int)RtlUIntAdd(4, 8, &v1297) < 0)
                              || (v985 = RtlUIntAdd((unsigned int)v1312, (unsigned int)v1297, &v1312), (v986 | v985) < 0)
                              || (HIDWORD(v1334[0]) = v1312,
                                  v987 = v1312,
                                  v988 = GetProcessHeap(),
                                  (v989 = HeapAlloc(v988, 8u, v987)) == 0) )
                            {
LABEL_1279:
                              v626 = v633;
                              goto LABEL_1280;
                            }
                            v1334[1] = (size_t)v989;
                            v1332 = 0;
                            LODWORD(v1334[0]) = 0;
                            LODWORD(v1333) = 0;
                            v626 = v633;
                            pcchLength = (size_t)v989;
                            LODWORD(Size) = 8;
                            if ( (int)RtlULongLongAdd(v989, 4, &v1333) < 0
                              || (unsigned __int64)(v989 + 2) > v1334[1] + HIDWORD(v1334[0]) )
                            {
LABEL_1340:
                              v627 = v995;
                              goto LABEL_1281;
                            }
                            v997 = v1333;
                            *v989 = 4;
                            v998 = Size;
                            *v997 = 4;
                            v999 = ++LODWORD(v1334[0]);
                            v1332 = 0;
                            LODWORD(v1333) = 0;
                            if ( v630 )
                            {
                              if ( !v996 )
                                goto LABEL_1280;
                            }
                            else if ( v996 )
                            {
LABEL_1294:
                              v627 = 0;
                              goto LABEL_1281;
                            }
                            v1000 = (unsigned int *)v1334[1];
                            if ( v1334[1] )
                            {
                              v1001 = 0;
                              pcchLength = v1334[1];
                              if ( v999 )
                              {
                                do
                                {
                                  v1002 = *v1000;
                                  LODWORD(v1297) = 0;
                                  if ( (int)RtlUIntAdd(4, v1002, &v1297) < 0
                                    || (int)RtlULongLongAdd(v1003, (unsigned int)v1297, &pcchLength) < 0 )
                                  {
                                    goto LABEL_1280;
                                  }
                                  v1000 = (unsigned int *)pcchLength;
                                }
                                while ( ++v1001 < v1004 );
                              }
                              if ( (int)RtlULongLongAdd(v1000, 4, &v1333) < 0
                                || (unsigned __int64)v1005 + v1006 + 4 > v1334[1] + HIDWORD(v1334[0]) )
                              {
                                goto LABEL_1280;
                              }
                              *v1005 = v1006;
                              if ( v630 )
                                memcpy_0(v1333, v630, v1006);
                            }
                            else
                            {
                              LODWORD(v1297) = 0;
                              if ( (int)RtlUIntAdd(4, v996, &v1297) < 0
                                || (int)RtlUIntAdd(HIDWORD(v1334[0]), (unsigned int)v1297, (char *)v1334 + 4) < 0 )
                              {
                                goto LABEL_1280;
                              }
                            }
                            v1007 = ++LODWORD(v1334[0]);
                            v1332 = 0;
                            LODWORD(v1333) = 0;
                            if ( v626 )
                            {
                              if ( !v998 )
                                goto LABEL_1280;
                            }
                            else if ( v998 )
                            {
                              goto LABEL_1294;
                            }
                            v1008 = (unsigned int *)v1334[1];
                            if ( v1334[1] )
                            {
                              pcchLength = v1334[1];
                              if ( v1007 )
                              {
                                do
                                {
                                  v1009 = *v1008;
                                  LODWORD(v1297) = 0;
                                  if ( (int)RtlUIntAdd(4, v1009, &v1297) < 0
                                    || (int)RtlULongLongAdd(v1010, (unsigned int)v1297, &pcchLength) < 0 )
                                  {
                                    goto LABEL_1280;
                                  }
                                  v1008 = (unsigned int *)pcchLength;
                                }
                                while ( v1012 + 1 < v1011 );
                              }
                              if ( (int)RtlULongLongAdd(v1008, 4, &v1333) < 0
                                || (unsigned __int64)v1013 + v998 + 4 > v1334[1] + HIDWORD(v1334[0]) )
                              {
                                goto LABEL_1280;
                              }
                              *v1013 = v998;
                              if ( v626 )
                                memcpy_0(v1333, v626, v998);
                            }
                            else
                            {
                              LODWORD(v1297) = 0;
                              if ( (int)RtlUIntAdd(4, v998, &v1297) < 0
                                || (int)RtlUIntAdd(HIDWORD(v1334[0]), (unsigned int)v1297, (char *)v1334 + 4) < 0 )
                              {
                                goto LABEL_1280;
                              }
                            }
                            v1014 = (unsigned int *)v1334[1];
                            v1015 = ++LODWORD(v1334[0]);
                            v1332 = 0;
                            LODWORD(v1333) = 0;
                            if ( !v1334[1] )
                            {
                              LODWORD(v1297) = 0;
                              if ( (int)RtlUIntAdd(4, 8, &v1297) < 0
                                || (int)RtlUIntAdd(HIDWORD(v1334[0]), (unsigned int)v1297, (char *)v1334 + 4) < 0 )
                              {
                                goto LABEL_1280;
                              }
LABEL_1335:
                              ++LODWORD(v1334[0]);
                              LODWORD(v1297) = 0;
                              if ( (int)RtlUIntAdd(4, 4, &v1297) < 0 )
                                goto LABEL_1280;
                              LODWORD(Size) = v1297;
                              LODWORD(v1297) = 0;
                              if ( (int)RtlUIntAdd(v1023, 8, &v1297) < 0
                                || (int)RtlUIntAdd(v1024, (unsigned int)v1297, &Size) < 0 )
                              {
                                goto LABEL_1280;
                              }
                              v1025 = Size;
                              v1298 = 0;
                              LODWORD(v1322) = 0;
                              LODWORD(v1308) = Size;
                              v1320 = (_BYTE *)__rdtsc();
                              v1337 = 8;
                              v1026 = RtlUIntAdd(8, HIDWORD(v1334[0]), &v1337);
                              if ( v1026 < 0 )
                              {
                                v1317 = v626;
                                v1311 = v630;
                              }
                              else
                              {
                                v1028 = (v1337 + 7) & 0xFFFFFFF8;
                                if ( v1028 < v1337 )
                                  goto LABEL_1340;
                                v1337 = (v1337 + 7) & 0xFFFFFFF8;
                                v1029 = v1028;
                                v1030 = GetProcessHeap();
                                v1031 = (char *)HeapAlloc(v1030, 8u, v1029);
                                v1032 = v1031;
                                if ( !v1031 )
                                {
LABEL_1628:
                                  if ( v1316 >= 0 )
                                  {
                                    v627 = v1307;
                                    if ( (_DWORD)v1322 )
                                    {
                                      if ( v1307 )
                                      {
                                        v1332 = (SIZE_T)v1307;
                                        if ( (int)RtlULongLongAdd(v1307, 4, &v1332) >= 0 )
                                        {
                                          v1289 = (int *)v1332;
                                          if ( !*v627 )
                                            v1289 = 0;
                                          if ( *v627 == (_DWORD)v1288 && *v1289 >= 0 && v1287 > 1 )
                                          {
                                            v1290 = (SIZE_T)v627;
                                            v1310 = (SIZE_T)v627;
                                            while ( (int)RtlULongLongAdd(v1290, v1288, &v1310) >= 0
                                                 && (int)RtlULongLongAdd(v1310, v1291, &v1310) >= 0 )
                                            {
                                              v1290 = v1310;
                                              if ( v1292 != -1 )
                                              {
                                                RtlULongLongAdd(v1310, v1288, &v1310);
                                                goto LABEL_1281;
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                    goto LABEL_1281;
                                  }
                                  goto LABEL_1280;
                                }
                                lpMem = v1031;
                                v1311 = v630;
                                v1317 = v626;
                                LODWORD(v1308) = v1025;
                                *(_DWORD *)v1031 = v1334[0];
                                LODWORD(Size) = RtlULongLongAdd(v1031, 4, &lpMem);
                                if ( (Size & 0x80000000) != 0LL
                                  || (v1034 = lpMem,
                                      *(_DWORD *)lpMem = HIDWORD(v1334[0]),
                                      LODWORD(Size) = RtlULongLongAdd(v1034, v1033, &lpMem),
                                      (Size & 0x80000000) != 0LL) )
                                {
                                  v1311 = v630;
                                  v1317 = v626;
                                  LODWORD(v1308) = v1025;
                                  v1035 = GetProcessHeap();
                                  HeapFree(v1035, 0, v1032);
                                  v995 = v1298;
                                  v1026 = Size;
                                  v1027 = (unsigned int)v1298;
                                }
                                else
                                {
                                  *(_QWORD *)&v1032[v1337 - 8] = v1320;
                                  memcpy_0(lpMem, (const void *)v1334[1], HIDWORD(v1334[0]));
                                  v1027 = v1337;
                                  v995 = v1032;
                                  v1026 = Size;
                                  v1298 = v1032;
                                }
                              }
                              v1036 = 0;
                              Src = 0;
                              v1037 = 0;
                              v1318 = 0;
                              v1038 = v1026 | 0x10000000;
                              v1319 = 0;
                              v1302 = 0;
                              v1303 = 0;
                              if ( v1038 < 0 )
                              {
                                v1316 = v1038;
                                v1127 = 0;
                                goto LABEL_1603;
                              }
                              if ( !v995 )
                                goto LABEL_1280;
                              v1326 = v1027;
                              if ( !v1027
                                || (lpMem = (LPVOID)(v1027 + 8LL), (v1335 = MemoryAlloc((unsigned __int64)lpMem)) == 0) )
                              {
                                v1098 = v1298;
                                v1127 = 0;
                                v1316 = -805306367;
                                goto LABEL_1605;
                              }
                              v1039 = v1326;
                              v1040 = 0;
                              v1041 = 0;
                              v1327 = 0;
                              uBytes_4 = 0;
                              if ( v1326 )
                              {
                                do
                                  v1040 ^= *((_BYTE *)v1298 + v1041++);
                                while ( v1041 < v1326 );
                                uBytes_4 = v1040;
                              }
                              v1313 = (LPVOID)0xC81ECB17B1B54A58LL;
                              v1332 = (SIZE_T)v1298;
                              v1042 = (unsigned __int8 *)v1298;
                              pcchLength = (size_t)v1335;
                              v1043 = v1326 & 7;
                              if ( (v1326 & 7) != 0 )
                              {
                                LODWORD(Size) = 0;
                                LODWORD(v1324) = 0;
                                v1044 = 0;
                                v1045 = 0;
                                v1046 = 0;
                                do
                                {
                                  v1047 = *v1042++;
                                  LODWORD(v1297) = 8 * v1044;
                                  if ( v1044 >= 4 )
                                    v1045 |= v1047 << (56 - v1297);
                                  else
                                    v1046 |= v1047 << (24 - v1297);
                                  ++v1044;
                                }
                                while ( (int)v1044 < (int)v1043 );
                                LODWORD(v1324) = v1046;
                                v1048 = v1046;
                                v1036 = 0;
                                LODWORD(Size) = v1045;
                                v1332 = (SIZE_T)v1042;
                                v1317 = v626;
                                v1311 = v630;
                                v1049 = v1048 ^ 0xB17A307A;
                                v1050 = v1045 ^ 0x42F6B18D;
                                v1051 = v1049;
                                v1052 = v1045 ^ 0x42F6B18D;
                                if ( (v1326 & 7) != 0 )
                                {
                                  v1053 = (_BYTE *)pcchLength;
                                  v1054 = 0;
                                  do
                                  {
                                    v1320 = v1053 + 1;
                                    if ( v1054 >= 4 )
                                    {
                                      v1052 = __ROR4__(v1052, 24);
                                      v1055 = v1052;
                                    }
                                    else
                                    {
                                      v1051 = __ROR4__(v1051, 24);
                                      v1055 = v1051;
                                    }
                                    *v1053 = v1055;
                                    ++v1054;
                                    v1053 = v1320;
                                  }
                                  while ( (int)v1054 < (int)v1043 );
                                  pcchLength = (size_t)v1320;
                                  v1037 = v1319;
                                }
                                if ( v1043 <= 4 )
                                {
                                  v1056 = 0;
                                  if ( v1043 < 4 )
                                    v1049 = v1049 >> (8 * (4 - v1043)) << (8 * (4 - v1043));
                                }
                                else
                                {
                                  v1056 = v1050 >> (8 * (8 - v1043)) << (8 * (8 - v1043));
                                }
                              }
                              else
                              {
                                v1049 = 0;
                                LODWORD(v1324) = 0;
                                v1056 = -1;
                                LODWORD(Size) = 0;
                              }
                              if ( v1039 >> 3 )
                              {
                                v1057 = (unsigned __int8 *)v1332;
                                v1058 = v1039 >> 3;
                                v1059 = (_BYTE *)pcchLength;
                                v1060 = v1324;
                                LODWORD(v1309) = 19032;
                                v1316 = WORD1(v1313);
                                uBytes = WORD2(v1313);
                                LODWORD(v1297) = HIWORD(v1313);
                                LODWORD(v1312) = HIDWORD(v1313) ^ 0xB1B54A58;
                                v1061 = Size;
                                v1062 = HIDWORD(v1313) ^ 0xB1B54A58;
                                v1328 = 0;
                                do
                                {
                                  v1063 = *v1057;
                                  v1064 = v1057[1];
                                  v1065 = v1057[4];
                                  v1057 += 8;
                                  v1066 = *(v1057 - 5) | ((*(v1057 - 6) | (((v1063 << 8) | v1064) << 8)) << 8);
                                  v1067 = *(v1057 - 1) | ((*(v1057 - 2) | ((*(v1057 - 3) | (v1065 << 8)) << 8)) << 8);
                                  v1068 = v1049 ^ v1066 ^ ((v1056 ^ v1067) - v1309);
                                  v1069 = __ROR4__(v1068, 15);
                                  v1070 = HIDWORD(v1313) ^ v1068;
                                  v1071 = v1056 ^ v1067 ^ (__ROR4__(v1070, 7) + WORD1(v1313) * v1069);
                                  v1072 = v1070 ^ (WORD2(v1313) * __ROR4__(v1071 - 1313519016, 9) - __ROR4__(v1071, 10));
                                  v1073 = v1071
                                        ^ (__ROR4__(v1072, 27) + HIWORD(v1313) * __ROR4__(WORD2(v1313) ^ v1072, 28));
                                  v1074 = v1072 ^ (HIDWORD(v1313) - (v1073 ^ 0xB1B54A58));
                                  v1075 = v1073 ^ (WORD1(v1313) * (v1074 - v1309) - (v1074 >> 6));
                                  v1076 = v1074 ^ (v1309 * (WORD2(v1313) ^ __ROR4__(v1075, 15)));
                                  v1077 = v1075 ^ (WORD2(v1313) * (v1297 + __ROR4__(~v1076, 3)));
                                  v1078 = v1076 ^ (v1077 - HIDWORD(v1313) - v1309);
                                  v1079 = v1077 ^ (v1316 * (v1297 ^ v1078)) ^ __ROR4__(v1078, 10);
                                  v1080 = v1078 ^ __ROR4__(v1079, 3) ^ (WORD2(v1313) * __ROR4__(v1079 ^ v1309, 26));
                                  v1081 = v1079 ^ (v1309 * (__ROR4__(v1080, 15) - HIWORD(v1313)));
                                  v1082 = v1080
                                        ^ ((v1081 ^ (v1081 >> 14)) >> 1)
                                        ^ (v1309 * (v1081 ^ HIWORD(v1313)))
                                        ^ (v1309 * (((v1081 - uBytes) >> 29) | (8 * (v1081 - WORD2(v1313)))));
                                  v1083 = v1081 ^ (WORD1(v1313) * (v1082 - WORD2(v1313)) - (v1082 >> 13));
                                  v1084 = v1082
                                        ^ __ROR4__(v1083, 11)
                                        ^ (WORD2(v1313) * __ROR4__(-1313519016 - v1083, 9));
                                  v1085 = v1083 ^ (v1084 - HIWORD(v1313) + 1313519016);
                                  v1086 = v1084 ^ (v1309 * (v1085 ^ WORD1(v1313)) - __ROR4__(v1085, 7));
                                  v1087 = v1085
                                        ^ (WORD1(v1313) * __ROR4__(v1086 ^ HIWORD(v1313), 28) - __ROR4__(v1086, 16));
                                  v1088 = v1086
                                        ^ (__ROR4__(v1087, 4) + WORD2(v1313) * __ROR4__(-1313519016 - v1087, 10));
                                  v1089 = v1087 ^ __ROR4__(v1088, 9) ^ (HIWORD(v1313) * __ROR4__(v1088 + 1313519016, 4));
                                  v1090 = v1088 ^ (v1309 * __ROR4__(v1089 ^ HIDWORD(v1313), 24) - __ROR4__(v1089, 30));
                                  v1091 = v1089
                                        ^ (WORD1(v1313) * __ROR4__(HIDWORD(v1313) - v1090, 11) - __ROR4__(v1090, 12));
                                  v1092 = WORD2(v1313) * (v1091 ^ WORD1(v1313));
                                  v1093 = v1091 >> 8;
                                  v1094 = v1062 ^ v1061 ^ v1091;
                                  v1061 = v1067;
                                  v1095 = v1090 ^ v1093 ^ v1092;
                                  v1049 = v1095 ^ v1060;
                                  v1056 = v1095 ^ v1094;
                                  v1059[3] = v1095 ^ v1060;
                                  LOBYTE(v1093) = __ROR4__(v1095 ^ v1060, 8);
                                  v1060 = v1066;
                                  v1059[7] = v1056;
                                  v1059[2] = v1093;
                                  v1059[6] = __ROR4__(v1056, 8);
                                  v1059[1] = __ROR4__(v1049, 16);
                                  v1059[5] = __ROR4__(v1056, 16);
                                  *v1059 = __ROR4__(v1049, 24);
                                  v1059[4] = __ROR4__(v1056, 24);
                                  v1059 += 8;
                                  ++v1328;
                                }
                                while ( v1328 < v1058 );
                                v1037 = v1319;
                                v1040 = uBytes_4;
                                v1036 = (unsigned int *)v1319;
                                v3 = v1301;
                                v630 = v1311;
                                v626 = v1317;
                                v1039 = v1326;
                              }
                              *(_QWORD *)((char *)v1335 + v1039) = v1040;
                              v1096 = GetProcessHeap();
                              v1097 = HeapAlloc(v1096, 8u, 0x30u);
                              v1299 = (SIZE_T)v1097;
                              if ( !v1097 )
                              {
                                v1098 = v1298;
                                LODWORD(v1312) = -1073741801;
                                goto LABEL_1393;
                              }
                              v1099 = (unsigned int)lpMem;
                              *v1097 = (_DWORD)lpMem;
                              v1100 = GetProcessHeap();
                              v1101 = HeapAlloc(v1100, 8u, v1099);
                              v1098 = v1298;
                              if ( v1101 )
                              {
                                *(_QWORD *)(v1299 + 8) = v1101;
                                memcpy_0(v1101, v1335, (unsigned int)lpMem);
                                *(_DWORD *)(v1299 + 16) = 160;
                                v1102 = GetProcessHeap();
                                v1103 = HeapAlloc(v1102, 8u, 0xA0u);
                                v1104 = v1299;
                                if ( v1103 )
                                {
                                  *(_QWORD *)(v1299 + 24) = v1103;
                                  *v1103 = xmmword_1801284E0;
                                  v1103[1] = xmmword_1801284F0;
                                  v1103[2] = xmmword_180128500;
                                  v1103[3] = xmmword_180128510;
                                  v1103[4] = xmmword_180128520;
                                  v1103[5] = xmmword_180128530;
                                  v1103[6] = xmmword_180128540;
                                  v1103[7] = xmmword_180128550;
                                  v1103[8] = xmmword_180128560;
                                  v1103[9] = xmmword_180128570;
                                  *(_DWORD *)(v1104 + 32) = 8;
                                  v1105 = GetProcessHeap();
                                  v1106 = HeapAlloc(v1105, 8u, 8u);
                                  if ( v1106 )
                                  {
                                    v1112 = (void *)v1299;
                                    *(_QWORD *)(v1299 + 40) = v1106;
                                    *v1106 = qword_180128580;
                                    v1327 = v1112;
                                    LODWORD(v1312) = 0;
                                    v1298 = v1098;
                                    goto LABEL_1392;
                                  }
                                  v1104 = v1299;
                                }
                                v1299 = v1104;
                              }
                              v1107 = v1299;
                              LODWORD(v1312) = -1073741801;
                              v1298 = v1098;
                              v1320 = *(_BYTE **)(v1299 + 8);
                              if ( v1320 )
                              {
                                v1108 = GetProcessHeap();
                                HeapFree(v1108, 0, v1320);
                                v1107 = v1299;
                                *(_QWORD *)(v1299 + 8) = 0;
                              }
                              v1320 = *(_BYTE **)(v1107 + 24);
                              if ( v1320 )
                              {
                                v1109 = GetProcessHeap();
                                HeapFree(v1109, 0, v1320);
                                v1107 = v1299;
                                *(_QWORD *)(v1299 + 24) = 0;
                              }
                              v1320 = *(_BYTE **)(v1107 + 40);
                              if ( v1320 )
                              {
                                v1110 = GetProcessHeap();
                                HeapFree(v1110, 0, v1320);
                                *(_QWORD *)(v1299 + 40) = 0;
                              }
                              v1111 = GetProcessHeap();
                              HeapFree(v1111, 0, (LPVOID)v1299);
                              if ( (v1312 & 0x80000000) != 0LL )
                              {
LABEL_1393:
                                v1113 = GetProcessHeap();
                                HeapFree(v1113, 0, v1335);
                                v1114 = v1327;
                                if ( v1327 )
                                {
                                  v1320 = (_BYTE *)*((_QWORD *)v1327 + 1);
                                  if ( v1320 )
                                  {
                                    v1115 = GetProcessHeap();
                                    HeapFree(v1115, 0, v1320);
                                    v1114 = v1327;
                                    *((_QWORD *)v1327 + 1) = 0;
                                  }
                                  v1320 = (_BYTE *)v1114[3];
                                  if ( v1320 )
                                  {
                                    v1116 = GetProcessHeap();
                                    HeapFree(v1116, 0, v1320);
                                    v1114 = v1327;
                                    *((_QWORD *)v1327 + 3) = 0;
                                  }
                                  v1320 = (_BYTE *)v1114[5];
                                  if ( v1320 )
                                  {
                                    v1117 = GetProcessHeap();
                                    HeapFree(v1117, 0, v1320);
                                    *((_QWORD *)v1327 + 5) = 0;
                                  }
                                  v1118 = GetProcessHeap();
                                  HeapFree(v1118, 0, v1327);
                                }
                                if ( (v1312 & 0x80000000) != 0LL )
                                {
                                  v1298 = v1098;
                                  v1316 = v1312 | 0x10000000;
                                  goto LABEL_1409;
                                }
                                v1119 = *v1036;
                                LODWORD(v1297) = 0;
                                LODWORD(v1309) = 4;
                                v1316 = RtlUIntAdd(4, v1119, &v1309);
                                if ( v1316 < 0 )
                                  goto LABEL_1421;
                                v1316 = RtlUIntAdd((unsigned int)v1309, v1120, &v1309);
                                if ( v1316 < 0
                                  || (v1121 = v1036[4],
                                      v1332 = (SIZE_T)(v1036 + 4),
                                      v1316 = RtlUIntAdd((unsigned int)v1309, v1121, &v1309),
                                      v1316 < 0)
                                  || (v1316 = RtlUIntAdd((unsigned int)v1309, v1122, &v1309), v1316 < 0)
                                  || (v1123 = v1036[8],
                                      v1328 = (size_t)(v1036 + 8),
                                      v1316 = RtlUIntAdd((unsigned int)v1309, v1123, &v1309),
                                      v1316 < 0) )
                                {
LABEL_1421:
                                  v1298 = v1098;
                                }
                                else
                                {
                                  v1124 = v1309;
                                  v1125 = GetProcessHeap();
                                  v1126 = HeapAlloc(v1125, 8u, v1124);
                                  v1098 = v1298;
                                  v1311 = v1126;
                                  if ( !v1126 )
                                  {
                                    v1316 = -805306345;
LABEL_1409:
                                    v1127 = v1303;
                                    goto LABEL_1604;
                                  }
                                  *v1126 = *v1036;
                                  v1298 = v1098;
                                  v1299 = (SIZE_T)v1126;
                                  v1316 = RtlULongLongAdd(v1126, 4, &v1299);
                                  if ( v1316 < 0 )
                                  {
                                    LODWORD(v1308) = v1129;
                                    v1311 = v1128;
                                  }
                                  else
                                  {
                                    memcpy_0((void *)v1299, *((const void **)v1036 + 1), *v1036);
                                    v1316 = RtlULongLongAdd(v1299, *v1036, &v1299);
                                    if ( v1316 >= 0 )
                                    {
                                      v1130 = v1299;
                                      *(_DWORD *)v1299 = *(_DWORD *)v1332;
                                      v1316 = RtlULongLongAdd(v1130, 4, &v1299);
                                      if ( v1316 >= 0 )
                                      {
                                        memcpy_0((void *)v1299, *((const void **)v1036 + 3), *v1131);
                                        v1316 = RtlULongLongAdd(v1299, *(unsigned int *)v1332, &v1299);
                                        if ( v1316 >= 0 )
                                        {
                                          v1132 = v1299;
                                          *(_DWORD *)v1299 = *(_DWORD *)v1328;
                                          v1316 = RtlULongLongAdd(v1132, 4, &v1299);
                                          if ( v1316 >= 0 )
                                          {
                                            memcpy_0((void *)v1299, *((const void **)v1036 + 5), *v1133);
                                            v1134 = RtlULongLongAdd(v1299, *(unsigned int *)v1328, &v1299);
                                            v1316 = v1134;
                                            if ( v1134 >= 0 )
                                            {
                                              v1318 = v1311;
                                              LODWORD(v1297) = v1309;
LABEL_1423:
                                              LastError = v1134 | 0x10000000;
                                              if ( LastError < 0 )
                                                goto LABEL_1427;
                                              v1343 = 8;
                                              v1137 = RtlUIntAdd(8, (unsigned int)v1308, &v1343);
                                              LastError = v1138 | v1137;
                                              if ( LastError < 0 )
                                                goto LABEL_1427;
                                              v1139 = (v1343 + 7) & 0xFFFFFFF8;
                                              if ( (unsigned int)v1139 < v1343 )
                                              {
                                                LastError = -1073741675;
LABEL_1427:
                                                v1316 = LastError;
LABEL_1465:
                                                v1127 = v1303;
LABEL_1603:
                                                v1098 = v1298;
LABEL_1604:
                                                if ( !v1098 )
                                                {
LABEL_1606:
                                                  if ( v1036 )
                                                  {
                                                    v1268 = (void *)*((_QWORD *)v1036 + 1);
                                                    if ( v1268 )
                                                    {
                                                      v1269 = GetProcessHeap();
                                                      HeapFree(v1269, 0, v1268);
                                                      *((_QWORD *)v1036 + 1) = 0;
                                                    }
                                                    v1270 = (void *)*((_QWORD *)v1036 + 3);
                                                    if ( v1270 )
                                                    {
                                                      v1271 = GetProcessHeap();
                                                      HeapFree(v1271, 0, v1270);
                                                      *((_QWORD *)v1036 + 3) = 0;
                                                    }
                                                    v1272 = (void *)*((_QWORD *)v1036 + 5);
                                                    if ( v1272 )
                                                    {
                                                      v1273 = GetProcessHeap();
                                                      HeapFree(v1273, 0, v1272);
                                                      *((_QWORD *)v1036 + 5) = 0;
                                                    }
                                                    v1274 = GetProcessHeap();
                                                    HeapFree(v1274, 0, v1036);
                                                  }
                                                  v1275 = v1318;
                                                  if ( v1318 )
                                                  {
                                                    v1276 = GetProcessHeap();
                                                    HeapFree(v1276, 0, v1275);
                                                  }
                                                  if ( v1037 )
                                                  {
                                                    v1277 = GetProcessHeap();
                                                    HeapFree(v1277, 0, v1037);
                                                  }
                                                  v1278 = v1302;
                                                  if ( v1302 )
                                                  {
                                                    v1279 = (void *)*((_QWORD *)v1302 + 1);
                                                    if ( v1279 )
                                                    {
                                                      v1280 = GetProcessHeap();
                                                      HeapFree(v1280, 0, v1279);
                                                      v1278[1] = 0;
                                                    }
                                                    v1281 = (void *)v1278[3];
                                                    if ( v1281 )
                                                    {
                                                      v1282 = GetProcessHeap();
                                                      HeapFree(v1282, 0, v1281);
                                                      v1278[3] = 0;
                                                    }
                                                    v1283 = (void *)v1278[5];
                                                    if ( v1283 )
                                                    {
                                                      v1284 = GetProcessHeap();
                                                      HeapFree(v1284, 0, v1283);
                                                      v1278[5] = 0;
                                                    }
                                                    v1285 = GetProcessHeap();
                                                    HeapFree(v1285, 0, v1278);
                                                  }
                                                  if ( v1127 )
                                                  {
                                                    v1286 = GetProcessHeap();
                                                    HeapFree(v1286, 0, v1127);
                                                  }
                                                  goto LABEL_1628;
                                                }
LABEL_1605:
                                                v1267 = GetProcessHeap();
                                                HeapFree(v1267, 0, v1098);
                                                goto LABEL_1606;
                                              }
                                              v1345 = (v1343 + 7) & 0xFFFFFFF8;
                                              LastError = RtlUIntAdd(v1139, 8, &v1345);
                                              if ( LastError < 0 )
                                                goto LABEL_1427;
                                              v1140 = v1334[1];
                                              v1311 = v630;
                                              v1317 = v626;
                                              v1298 = v1098;
                                              Src = v1036;
                                              LODWORD(Size) = 0;
                                              if ( !v1334[1] )
                                                goto LABEL_1437;
                                              Src = v1036;
                                              v1298 = v1098;
                                              v1317 = v626;
                                              v1311 = v630;
                                              if ( LODWORD(v1334[0]) <= 1 )
                                                goto LABEL_1437;
                                              v1310 = v1334[1];
                                              do
                                              {
                                                LastError = RtlULongLongAdd(v1140, 4, &v1310);
                                                if ( LastError < 0 )
                                                  goto LABEL_1427;
                                                LastError = RtlULongLongAdd(v1310, v1141, &v1310);
                                                if ( LastError < 0 )
                                                  goto LABEL_1427;
                                                v1140 = v1310;
                                              }
                                              while ( v1142 == -1 );
                                              v1143 = *(_DWORD *)v1310;
                                              LastError = RtlULongLongAdd(v1310, 4, &v1310);
                                              if ( LastError < 0 )
                                                goto LABEL_1427;
                                              v1144 = v1334[1];
                                              if ( !v1334[1] || LODWORD(v1334[0]) <= 2 )
                                              {
LABEL_1437:
                                                LastError = -1073741811;
                                                goto LABEL_1427;
                                              }
                                              v1310 = v1334[1];
                                              do
                                              {
                                                LastError = RtlULongLongAdd(v1144, 4, &v1310);
                                                if ( LastError < 0 )
                                                  goto LABEL_1427;
                                                LastError = RtlULongLongAdd(v1310, v1147, &v1310);
                                                if ( LastError < 0 )
                                                  goto LABEL_1427;
                                                v1144 = v1310;
                                              }
                                              while ( (unsigned int)(v1148 + 1) < 2 );
                                              LastError = RtlULongLongAdd(v1310, 4, &v1310);
                                              if ( LastError < 0 )
                                                goto LABEL_1427;
                                              LODWORD(Size) = v1149;
                                              LODWORD(v1309) = v1150;
                                              LastError = RtlUIntAdd(v1150, v1345, &v1309);
                                              if ( LastError < 0 )
                                                goto LABEL_1427;
                                              LastError = RtlUIntAdd((unsigned int)v1309, v1151, &v1309);
                                              if ( LastError < 0 )
                                                goto LABEL_1427;
                                              LastError = RtlUIntAdd((unsigned int)v1309, v1143, &v1309);
                                              if ( LastError < 0 )
                                                goto LABEL_1427;
                                              LastError = RtlUIntAdd((unsigned int)v1309, v1152, &v1309);
                                              if ( LastError < 0 )
                                                goto LABEL_1427;
                                              LastError = RtlUIntAdd((unsigned int)v1309, v1153, &v1309);
                                              if ( LastError < 0 )
                                                goto LABEL_1427;
                                              LODWORD(Size) = v1309;
                                              if ( (unsigned int)v1309 > 0x400000 )
                                              {
                                                LastError = -2147418113;
                                                goto LABEL_1427;
                                              }
                                              v1145 = v1309;
                                              v1146 = GetProcessHeap();
                                              v1037 = HeapAlloc(v1146, 8u, v1145);
                                              if ( !v1037 )
                                              {
                                                v1316 = -805306345;
                                                v1127 = 0;
                                                goto LABEL_1603;
                                              }
                                              v1357 = 0;
                                              v1360 = 0;
                                              v1361 = 0;
                                              if ( !v1318 )
                                              {
                                                v1316 = -2147024809;
                                                goto LABEL_1465;
                                              }
                                              LODWORD(v1361) = v1297;
                                              *(_QWORD *)&v1360 = v1318;
                                              *(_QWORD *)((char *)&v1361 + 4) = (unsigned int)Size;
                                              *((_QWORD *)&v1360 + 1) = v1037;
                                              if ( GetModuleHandleExW(1u, L"ntdll.dll", &v1357)
                                                && (ProcAddress = GetProcAddress(v1357, "NtQuerySystemInformation")) != 0 )
                                              {
                                                LastError = ((__int64 (__fastcall *)(__int64, __int128 *))ProcAddress)(
                                                              134,
                                                              &v1360)
                                                          | 0x10000000;
                                                if ( LastError >= 0 )
                                                {
                                                  v1156 = DWORD1(v1361);
                                                  goto LABEL_1468;
                                                }
                                              }
                                              else
                                              {
                                                LastError = GetLastError();
                                                v1154 = LastError < 0;
                                                if ( LastError > 0 )
                                                {
                                                  LastError = (unsigned __int16)LastError | 0x80070000;
                                                  v1154 = LastError < 0;
                                                }
                                                if ( !v1154 )
                                                {
                                                  v1316 = -2147467259;
                                                  goto LABEL_1465;
                                                }
                                              }
                                              if ( LastError == -805306333 )
                                              {
                                                v1316 = -2147024774;
                                                goto LABEL_1465;
                                              }
                                              if ( LastError < 0 )
                                                goto LABEL_1427;
                                              v1156 = Size;
LABEL_1468:
                                              LODWORD(v1308) = 0;
                                              v1319 = v1037;
                                              if ( v1156 < 4 )
                                              {
LABEL_1469:
                                                v1316 = -805306306;
                                                goto LABEL_1465;
                                              }
                                              v1157 = (unsigned int)*v1037;
                                              LODWORD(v1297) = *v1037;
                                              v1158 = RtlULongLongAdd(v1037, 4, &v1319);
                                              if ( v1158 < 0 )
                                                goto LABEL_1521;
                                              v1158 = RtlUIntAdd(0, v1159, &v1308);
                                              if ( v1158 < 0 )
                                                goto LABEL_1521;
                                              if ( v1160 - (int)v1308 < (unsigned int)v1157 )
                                                goto LABEL_1469;
                                              v1328 = (size_t)v1319;
                                              v1332 = v1157;
                                              v1158 = RtlULongLongAdd(v1319, (unsigned int)v1157, &v1319);
                                              if ( v1158 < 0 )
                                                goto LABEL_1521;
                                              v1158 = RtlUIntAdd((unsigned int)v1308, (unsigned int)v1157, &v1308);
                                              if ( v1158 < 0 )
                                                goto LABEL_1521;
                                              if ( v1161 - (int)v1308 < (unsigned int)v1162 )
                                                goto LABEL_1469;
                                              LODWORD(Size) = *(_DWORD *)v1319;
                                              v1158 = RtlULongLongAdd(v1319, v1162, &v1319);
                                              if ( v1158 < 0 )
                                                goto LABEL_1521;
                                              v1158 = RtlUIntAdd((unsigned int)v1308, v1163, &v1308);
                                              if ( v1158 < 0 )
                                                goto LABEL_1521;
                                              if ( v1164 - (int)v1308 < (unsigned int)v1165 )
                                                goto LABEL_1469;
                                              pcchLength = (size_t)v1319;
                                              v1326 = v1165;
                                              v1158 = RtlULongLongAdd(v1319, (unsigned int)v1165, &v1319);
                                              if ( v1158 < 0 )
                                                goto LABEL_1521;
                                              v1158 = RtlUIntAdd((unsigned int)v1308, v1166, &v1308);
                                              if ( v1158 < 0 )
                                                goto LABEL_1521;
                                              if ( v1167 - (int)v1308 < v1168 )
                                                goto LABEL_1469;
                                              LODWORD(v1324) = *(_DWORD *)v1319;
                                              v1158 = RtlULongLongAdd(v1319, 4, &v1319);
                                              if ( v1158 < 0 )
                                                goto LABEL_1521;
                                              v1158 = RtlUIntAdd((unsigned int)v1308, 4, &v1308);
                                              if ( v1158 < 0 )
                                                goto LABEL_1521;
                                              if ( v1169 - (int)v1308 < v1170 )
                                                goto LABEL_1469;
                                              v1158 = RtlUIntAdd((unsigned int)v1308, v1170, &v1308);
                                              if ( v1158 < 0 )
                                              {
LABEL_1521:
                                                v1098 = v1298;
                                                v1191 = (unsigned int *)v1302;
                                                v1319 = v1037;
                                                goto LABEL_1522;
                                              }
                                              if ( v1171 != (_DWORD)v1308
                                                || (unsigned int)(v1157 + v1172 + v1173) + 12LL != v1171 )
                                              {
                                                goto LABEL_1469;
                                              }
                                              v1174 = GetProcessHeap();
                                              v1175 = HeapAlloc(v1174, 8u, 0x30u);
                                              v1098 = v1298;
                                              v1176 = (SIZE_T)v1175;
                                              v1299 = (SIZE_T)v1175;
                                              if ( !v1175 )
                                              {
                                                v1316 = -805306345;
                                                v1302 = 0;
                                                v1127 = 0;
                                                goto LABEL_1604;
                                              }
                                              v1311 = v630;
                                              v1317 = v626;
                                              Src = v1036;
                                              v1310 = 0;
                                              if ( v1328 )
                                              {
                                                *(_DWORD *)v1175 = v1297;
                                                v1177 = GetProcessHeap();
                                                v1178 = HeapAlloc(v1177, 8u, v1332);
                                                v1179 = (_QWORD *)v1299;
                                                if ( !v1178 )
                                                {
LABEL_1501:
                                                  v1185 = (_BYTE *)v1179[1];
                                                  LODWORD(v1312) = -1073741801;
                                                  v1319 = v1037;
                                                  v1320 = v1185;
                                                  if ( v1185 )
                                                  {
                                                    v1186 = GetProcessHeap();
                                                    HeapFree(v1186, 0, v1320);
                                                    v1179 = (_QWORD *)v1299;
                                                    *(_QWORD *)(v1299 + 8) = 0;
                                                  }
                                                  v1320 = (_BYTE *)v1179[3];
                                                  if ( v1320 )
                                                  {
                                                    v1187 = GetProcessHeap();
                                                    HeapFree(v1187, 0, v1320);
                                                    v1179 = (_QWORD *)v1299;
                                                    *(_QWORD *)(v1299 + 24) = 0;
                                                  }
                                                  v1320 = (_BYTE *)v1179[5];
                                                  if ( v1320 )
                                                  {
                                                    v1188 = GetProcessHeap();
                                                    HeapFree(v1188, 0, v1320);
                                                    *(_QWORD *)(v1299 + 40) = 0;
                                                  }
                                                  v1189 = GetProcessHeap();
                                                  HeapFree(v1189, 0, (LPVOID)v1299);
                                                  v1190 = (unsigned int *)v1310;
                                                  goto LABEL_1511;
                                                }
                                                *(_QWORD *)(v1299 + 8) = v1178;
                                                LODWORD(v1312) = 0;
                                                memcpy_0(v1178, (const void *)v1328, v1332);
                                                v1176 = v1299;
                                              }
                                              else
                                              {
                                                *(_DWORD *)v1175 = 0;
                                                v1175[1] = 0;
                                                LODWORD(v1312) = 0;
                                              }
                                              if ( pcchLength )
                                              {
                                                *(_DWORD *)(v1176 + 16) = Size;
                                                v1180 = GetProcessHeap();
                                                v1181 = HeapAlloc(v1180, 8u, v1326);
                                                v1179 = (_QWORD *)v1299;
                                                if ( !v1181 )
                                                {
LABEL_1500:
                                                  v1311 = v630;
                                                  v1317 = v626;
                                                  v1298 = v1098;
                                                  Src = v1036;
                                                  v1299 = (SIZE_T)v1179;
                                                  goto LABEL_1501;
                                                }
                                                *(_QWORD *)(v1299 + 24) = v1181;
                                                LODWORD(v1312) = 0;
                                                memcpy_0(v1181, (const void *)pcchLength, v1326);
                                                v1176 = v1299;
                                              }
                                              else
                                              {
                                                *(_DWORD *)(v1176 + 16) = 0;
                                                *(_QWORD *)(v1176 + 24) = 0;
                                              }
                                              if ( v1319 )
                                              {
                                                v1182 = (unsigned int)v1324;
                                                *(_DWORD *)(v1176 + 32) = v1324;
                                                v1332 = v1182;
                                                v1183 = GetProcessHeap();
                                                v1184 = HeapAlloc(v1183, 8u, v1332);
                                                v1179 = (_QWORD *)v1299;
                                                if ( !v1184 )
                                                  goto LABEL_1500;
                                                *(_QWORD *)(v1299 + 40) = v1184;
                                                LODWORD(v1312) = 0;
                                                memcpy_0(v1184, v1319, v1332);
                                                v1176 = v1299;
                                              }
                                              else
                                              {
                                                *(_DWORD *)(v1176 + 32) = 0;
                                                *(_QWORD *)(v1176 + 40) = 0;
                                              }
                                              v1190 = (unsigned int *)v1176;
                                              v1310 = v1176;
                                              v1319 = v1037;
                                              Src = v1036;
                                              v1298 = v1098;
                                              v1317 = v626;
                                              v1311 = v630;
LABEL_1511:
                                              v1158 = v1312;
                                              if ( (v1312 & 0x80000000) != 0LL )
                                              {
                                                v1191 = 0;
                                                v1302 = 0;
                                                if ( v1190 )
                                                {
                                                  v1320 = (_BYTE *)*((_QWORD *)v1190 + 1);
                                                  if ( v1320 )
                                                  {
                                                    v1192 = GetProcessHeap();
                                                    HeapFree(v1192, 0, v1320);
                                                    v1190 = (unsigned int *)v1310;
                                                    *(_QWORD *)(v1310 + 8) = 0;
                                                  }
                                                  v1320 = (_BYTE *)*((_QWORD *)v1190 + 3);
                                                  if ( v1320 )
                                                  {
                                                    v1193 = GetProcessHeap();
                                                    HeapFree(v1193, 0, v1320);
                                                    v1190 = (unsigned int *)v1310;
                                                    *(_QWORD *)(v1310 + 24) = 0;
                                                  }
                                                  v1320 = (_BYTE *)*((_QWORD *)v1190 + 5);
                                                  if ( v1320 )
                                                  {
                                                    v1194 = GetProcessHeap();
                                                    HeapFree(v1194, 0, v1320);
                                                    *(_QWORD *)(v1310 + 40) = 0;
                                                  }
                                                  v1195 = GetProcessHeap();
                                                  HeapFree(v1195, 0, (LPVOID)v1310);
                                                  v1158 = v1312;
                                                  v1191 = 0;
                                                  v1302 = 0;
                                                }
                                              }
                                              else
                                              {
                                                v1191 = v1190;
                                                v1302 = v1190;
                                              }
LABEL_1522:
                                              v1316 = v1158 | 0x10000000;
                                              if ( v1158 < 0 )
                                                goto LABEL_1465;
                                              if ( !v1191 || (v1335 = (void *)*((_QWORD *)v1191 + 1)) == 0 || !*v1191 )
                                              {
                                                v1316 = -805306355;
                                                goto LABEL_1465;
                                              }
                                              pcchLength = *v1191 - 8LL;
                                              v1303 = MemoryAlloc(pcchLength);
                                              v1196 = v1303;
                                              if ( !v1303 )
                                              {
LABEL_1554:
                                                v1316 = -805306367;
                                                v1127 = 0;
                                                goto LABEL_1603;
                                              }
                                              v1197 = pcchLength;
                                              v1198 = 0;
                                              v1199 = (unsigned __int8 *)v1335;
                                              uBytes_4 = 0;
                                              v1332 = pcchLength & 7;
                                              v1299 = 0x7F1137FAB69605ELL;
                                              v1328 = (size_t)v1335;
                                              v1326 = (SIZE_T)v1303;
                                              if ( (pcchLength & 7) != 0 )
                                              {
                                                v1331 = 0;
                                                LODWORD(Size) = 0;
                                                LODWORD(v1297) = 0;
                                                v1200 = 0;
                                                v1201 = 0;
                                                v1202 = 0;
                                                do
                                                {
                                                  v1203 = *v1199++;
                                                  LODWORD(v1312) = v1203;
                                                  LODWORD(v1297) = 8 * v1200;
                                                  if ( (unsigned int)v1200 >= 4 )
                                                  {
                                                    LODWORD(v1312) = (_DWORD)v1312 << (56 - v1297);
                                                    v1202 |= v1312;
                                                  }
                                                  else
                                                  {
                                                    LODWORD(v1312) = (_DWORD)v1312 << (24 - v1297);
                                                    v1201 |= v1312;
                                                  }
                                                  ++v1200;
                                                }
                                                while ( v1200 < (int)v1332 );
                                                LODWORD(Size) = v1201;
                                                v1204 = v1303;
                                                v1197 = pcchLength;
                                                v1331 = v1202;
                                                v1198 = uBytes_4;
                                                v1205 = v1332;
                                                v1328 = (size_t)v1199;
                                                v1319 = v1037;
                                                Src = v1036;
                                                v1298 = v1098;
                                                v1317 = v626;
                                                v1311 = v630;
                                                v1206 = Size ^ 0x92F65A5;
                                                v1207 = v1331 ^ 0x699A899C;
                                                LODWORD(v1297) = 0;
                                                v1208 = Size ^ 0x92F65A5;
                                                if ( (_DWORD)v1332 )
                                                {
                                                  v1209 = v1297;
                                                  v1210 = v1331 ^ 0x699A899C;
                                                  do
                                                  {
                                                    v1320 = v1204 + 1;
                                                    if ( v1209 >= 4 )
                                                    {
                                                      v1210 = __ROR4__(v1210, 24);
                                                      v1211 = v1210;
                                                    }
                                                    else
                                                    {
                                                      v1208 = __ROR4__(v1208, 24);
                                                      v1211 = v1208;
                                                    }
                                                    *v1204 = v1211;
                                                    ++v1209;
                                                    v1204 = v1320;
                                                  }
                                                  while ( (int)v1209 < (int)v1205 );
                                                  v1198 = uBytes_4;
                                                  v1326 = (SIZE_T)v1320;
                                                  v1196 = v1303;
                                                }
                                                if ( v1205 <= 4 )
                                                {
                                                  v1212 = 0;
                                                  if ( v1205 < 4 )
                                                    v1206 = v1206 >> (8 * (4 - v1205)) << (8 * (4 - v1205));
                                                }
                                                else
                                                {
                                                  v1212 = v1207 >> (8 * (8 - v1205)) << (8 * (8 - v1205));
                                                }
                                              }
                                              else
                                              {
                                                v1212 = 0;
                                                LODWORD(Size) = 0;
                                                v1206 = 0;
                                              }
                                              if ( v1197 >> 3 )
                                              {
                                                v1213 = HIDWORD(v1299);
                                                v1214 = v1197 >> 3;
                                                v1215 = WORD1(v1299);
                                                v1216 = (_BYTE *)v1326;
                                                v1217 = Size;
                                                v1218 = WORD2(v1299);
                                                LODWORD(v1312) = 24670;
                                                v1219 = (unsigned __int8 *)v1328;
                                                LODWORD(v1324) = WORD2(v1299);
                                                v1332 = 0;
                                                do
                                                {
                                                  v1220 = v1219[1];
                                                  v1221 = *v1219;
                                                  v1222 = v1219[4];
                                                  v1219 += 8;
                                                  v1223 = *(v1219 - 5)
                                                        | ((*(v1219 - 6) | ((v1220 | (v1221 << 8)) << 8)) << 8);
                                                  v1224 = v1206 ^ v1223;
                                                  v1225 = *(v1219 - 1)
                                                        | ((*(v1219 - 2) | ((*(v1219 - 3) | (v1222 << 8)) << 8)) << 8);
                                                  v1226 = v1212 ^ v1225 ^ v1213 ^ v1206 ^ v1223 ^ 0xAB69605E;
                                                  v1227 = v1224
                                                        ^ (__ROR4__(v1226, 22) + v1218
                                                                               * __ROR4__(v1226 + 1419157410, 27));
                                                  v1228 = v1226
                                                        ^ (v1215 * __ROR4__(v1227 + v1213, 9) - __ROR4__(v1227, 30));
                                                  v1229 = v1227 ^ (v1312 * (v1228 - v1218) - (v1228 >> 13));
                                                  v1230 = v1228
                                                        ^ (HIWORD(v1299) * __ROR4__(v1229 ^ v1215, 26)
                                                         - __ROR4__(v1229, 30));
                                                  v1231 = v1229 ^ (v1213 - (v1230 ^ 0xAB69605E));
                                                  v1232 = v1230 ^ (v1215 * (v1231 ^ v1218)) ^ __ROR4__(v1231, 6);
                                                  v1233 = v1231
                                                        ^ (__ROR4__(v1232, 30) + v1312 * __ROR4__(v1232 + v1213, 15));
                                                  v1234 = v1232
                                                        ^ (HIWORD(v1299) * __ROR4__(v1233 + 1419157410, 14)
                                                         - __ROR4__(v1233, 24));
                                                  v1235 = v1233
                                                        ^ __ROR4__(v1234, 10)
                                                        ^ (v1324 * __ROR4__(v1234 ^ 0xAB69605E, 12));
                                                  v1236 = v1235
                                                        ^ (HIWORD(v1299)
                                                         * (v1312
                                                          + __ROR4__(
                                                              ~(v1234
                                                              ^ (v1235 >> 10)
                                                              ^ (WORD1(v1299) * (v1235 ^ HIWORD(v1299)))),
                                                              5)));
                                                  v1237 = v1234
                                                        ^ (v1235 >> 10)
                                                        ^ (WORD1(v1299) * (v1235 ^ HIWORD(v1299)))
                                                        ^ (v1236 - HIWORD(v1299))
                                                        ^ 0xAB69605E;
                                                  v1238 = v1236
                                                        ^ ((v1237 >> 2) + v1324 * __ROR4__(HIWORD(v1299) ^ v1237, 30));
                                                  v1239 = v1237
                                                        ^ (__ROR4__(v1238, 25)
                                                         + WORD1(v1299) * __ROR4__(v1238 - v1213, 6));
                                                  v1240 = v1238 ^ (v1312 * (v1239 ^ v1324) + __ROR4__(v1239, 9));
                                                  v1241 = v1239
                                                        ^ (__ROR4__(v1240, 25)
                                                         + HIWORD(v1299) * __ROR4__(v1240 ^ WORD1(v1299), 27));
                                                  v1218 = v1324;
                                                  v1242 = v1213 ^ v1240 ^ v1241 ^ 0xAB69605E;
                                                  v1243 = v1241 ^ (v1324 * (__ROR4__(v1242, 3) - WORD1(v1299)));
                                                  v1244 = v1242
                                                        ^ (v1312 * __ROR4__(v1243 - v1213, 1) - __ROR4__(v1243, 6));
                                                  v1245 = v1243
                                                        ^ (__ROR4__(v1244, 18)
                                                         + HIWORD(v1299) * __ROR4__(v1244 - 1419157410, 29));
                                                  v1246 = v1244
                                                        ^ (v1324 * __ROR4__(v1245 - 1419157410, 17) - __ROR4__(v1245, 14));
                                                  v1215 = WORD1(v1299);
                                                  v1247 = v1245 ^ (v1246 >> 3) ^ (WORD1(v1299) * (v1246 ^ v1312));
                                                  v1212 = v1331 ^ v1247;
                                                  v1331 = v1225;
                                                  v1206 = v1217
                                                        ^ v1246
                                                        ^ __ROR4__(v1247, 30)
                                                        ^ (v1312 * __ROR4__(v1213 ^ v1247, 28));
                                                  v1217 = v1223;
                                                  v1216[3] = v1206;
                                                  v1216[7] = v1212;
                                                  v1216[2] = __ROR4__(v1206, 8);
                                                  v1216[6] = __ROR4__(v1212, 8);
                                                  v1216[1] = __ROR4__(v1206, 16);
                                                  v1216[5] = __ROR4__(v1212, 16);
                                                  *v1216 = __ROR4__(v1206, 24);
                                                  v1216[4] = __ROR4__(v1212, 24);
                                                  v1216 += 8;
                                                  ++v1332;
                                                }
                                                while ( v1332 < v1214 );
                                                v1198 = uBytes_4;
                                                v3 = v1301;
                                                v630 = v1311;
                                                v626 = v1317;
                                                v1037 = v1319;
                                                v1036 = (unsigned int *)Src;
                                                v1196 = v1303;
                                                v1197 = pcchLength;
                                              }
                                              for ( i = 0; i < v1197; ++i )
                                                v1198 ^= v1196[i];
                                              if ( v1198 != *(_QWORD *)((char *)v1335 + v1197) )
                                              {
                                                MemoryFree(v1196);
                                                goto LABEL_1554;
                                              }
                                              v1249 = v1298;
                                              v1250 = v1302;
                                              v1331 = 0;
                                              v1310 = (SIZE_T)v1196;
                                              if ( (unsigned int)v1197 < 4 )
                                              {
                                                v1127 = v1303;
                                                v1251 = -1073741762;
LABEL_1598:
                                                v1098 = v1249;
                                                goto LABEL_1599;
                                              }
                                              v1251 = RtlULongLongAdd(v1196, 4, &v1310);
                                              if ( v1251 >= 0 )
                                              {
                                                v1251 = RtlUIntAdd(0, 4, &v1331);
                                                if ( v1251 >= 0 )
                                                {
                                                  if ( v1253 - v1331 < 4 )
                                                    goto LABEL_1596;
                                                  v1254 = *(unsigned int *)v1310;
                                                  LODWORD(Size) = *(_DWORD *)v1310;
                                                  v1251 = RtlULongLongAdd(v1310, 4, &v1310);
                                                  if ( v1251 < 0 )
                                                    goto LABEL_1597;
                                                  v1251 = RtlUIntAdd(v1331, 4, &v1331);
                                                  if ( v1251 < 0 )
                                                    goto LABEL_1597;
                                                  if ( v1255 - v1331 < (unsigned int)v1254 )
                                                    goto LABEL_1596;
                                                  v1251 = RtlUIntAdd(v1331, (unsigned int)v1254, &v1331);
                                                  if ( v1251 >= 0 )
                                                  {
                                                    v1257 = v1256;
                                                    v1258 = (unsigned int *)v1310;
                                                    if ( (unsigned __int64)v1252 + v1257 >= v1254 + v1310
                                                      && (unsigned __int64)v1252 + v1257 - v1310 - v1254 < 8 )
                                                    {
                                                      v1331 = *v1252;
                                                      lpMem = 0;
                                                      v1332 = 0;
                                                      v1328 = 0;
                                                      LODWORD(v1324) = 0;
                                                      if ( v1310 )
                                                      {
                                                        v1316 = RtlULongLongAdd(v1310, (unsigned int)v1254, &lpMem);
                                                        v1251 = v1316;
                                                        v1302 = v1250;
                                                        v1298 = v1249;
                                                        if ( v1316 < 0 )
                                                        {
                                                          v1098 = v1249;
                                                          v1127 = v1259;
LABEL_1592:
                                                          v1266 = v1322;
LABEL_1593:
                                                          if ( v1251 >= 0 && v1331 != v1266 )
                                                            v1251 = -1073741762;
                                                          goto LABEL_1599;
                                                        }
                                                        v1260 = lpMem;
                                                        v1261 = v1258;
                                                        v1327 = v1258;
                                                        if ( v1258 < lpMem )
                                                        {
                                                          v1303 = v1259;
                                                          while ( 1 )
                                                          {
                                                            v1251 = RtlULongLongAdd(v1261, 4, &v1332);
                                                            if ( v1251 < 0 )
                                                              break;
                                                            if ( v1332 > (unsigned __int64)lpMem )
                                                            {
                                                              v1251 = -1073741811;
LABEL_1581:
                                                              v1098 = v1298;
                                                              v1127 = v1303;
                                                              goto LABEL_1599;
                                                            }
                                                            v1262 = *v1261;
                                                            LODWORD(v1297) = 0;
                                                            v1251 = RtlUIntAdd(4, v1262, &v1297);
                                                            if ( v1251 < 0 )
                                                              goto LABEL_1581;
                                                            v1320 = v630;
                                                            v1326 = (SIZE_T)v1250;
                                                            v1251 = RtlULongLongAdd(v1261, (unsigned int)v1297, &v1328);
                                                            v1302 = v1250;
                                                            v1316 = v1251;
                                                            v630 = v1320;
                                                            v1127 = v1259;
                                                            v1098 = v1249;
                                                            if ( v1251 < 0 )
                                                              goto LABEL_1592;
                                                            v1261 = (unsigned int *)v1328;
                                                            v1260 = lpMem;
                                                            v1327 = (LPVOID)v1328;
                                                            if ( v1328 > (unsigned __int64)lpMem )
                                                            {
                                                              v1251 = -1073741811;
                                                              v1302 = (LPVOID)v1326;
                                                              goto LABEL_1598;
                                                            }
                                                            LODWORD(v1324) = v1324 + 1;
                                                            v1250 = (void *)v1326;
                                                            v1303 = v1259;
                                                            v1302 = (LPVOID)v1326;
                                                            v1298 = v1249;
                                                            if ( v1328 >= (unsigned __int64)lpMem )
                                                            {
                                                              v1302 = (LPVOID)v1326;
                                                              goto LABEL_1577;
                                                            }
                                                          }
                                                          v1098 = v1298;
                                                          v1127 = v1303;
                                                          goto LABEL_1592;
                                                        }
LABEL_1577:
                                                        v1127 = v1259;
                                                        v1098 = v1249;
                                                        if ( v1327 != v1260 )
                                                        {
                                                          v1251 = -1073741811;
LABEL_1599:
                                                          v1316 = v1251 | 0x10000000;
                                                          goto LABEL_1604;
                                                        }
                                                      }
                                                      else
                                                      {
                                                        v1302 = v1250;
                                                        v1098 = v1249;
                                                        v1127 = v1252;
                                                        v1316 = 0;
                                                        v1298 = v1249;
                                                      }
                                                      v1263 = Size;
                                                      v1264 = 0;
                                                      v1332 = 0;
                                                      if ( (_DWORD)Size )
                                                      {
                                                        v1265 = GetProcessHeap();
                                                        v1332 = (SIZE_T)HeapAlloc(v1265, 8u, (unsigned int)Size);
                                                        v1264 = (void *)v1332;
                                                        if ( !v1332 )
                                                        {
                                                          v1251 = -1073741801;
                                                          goto LABEL_1599;
                                                        }
                                                        v1258 = (unsigned int *)v1310;
                                                        v1263 = Size;
                                                        v1316 = 0;
                                                      }
                                                      if ( v1258 )
                                                        memcpy_0(v1264, v1258, v1263);
                                                      v1251 = v1316;
                                                      v1307 = (LPVOID)v1332;
                                                      v1266 = v1324;
                                                      LODWORD(v1322) = v1324;
                                                      goto LABEL_1593;
                                                    }
LABEL_1596:
                                                    v1251 = -1073741762;
                                                  }
                                                }
                                              }
LABEL_1597:
                                              v1302 = v1250;
                                              v1127 = v1252;
                                              v1298 = v1249;
                                              goto LABEL_1598;
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                  v1298 = v1098;
                                  v1135 = GetProcessHeap();
                                  HeapFree(v1135, 0, v1311);
                                }
                                v1134 = v1316;
                                goto LABEL_1423;
                              }
LABEL_1392:
                              v1036 = (unsigned int *)v1327;
                              v1327 = 0;
                              goto LABEL_1393;
                            }
                            pcchLength = v1334[1];
                            if ( v1015 )
                            {
                              do
                              {
                                v1016 = *v1014;
                                LODWORD(v1297) = 0;
                                if ( (int)RtlUIntAdd(4, v1016, &v1297) < 0
                                  || (int)RtlULongLongAdd(v1017, (unsigned int)v1297, &pcchLength) < 0 )
                                {
                                  goto LABEL_1280;
                                }
                                v1014 = (unsigned int *)pcchLength;
                              }
                              while ( v1019 + 1 < v1018 );
                            }
                            if ( (int)RtlULongLongAdd(v1014, 4, &v1333) >= 0
                              && (unsigned __int64)(v1020 + 3) <= v1334[1] + HIDWORD(v1334[0]) )
                            {
                              v1021 = v1333;
                              v1022 = v1320;
                              *v1020 = 8;
                              *v1021 = v1022;
                              goto LABEL_1335;
                            }
LABEL_1280:
                            v627 = v1307;
                            goto LABEL_1281;
                          }
LABEL_1250:
                          v3 = -1073741789;
                        }
                        else
                        {
LABEL_1233:
                          v3 = -1073741811;
                        }
                        v1301 = v3;
                        goto LABEL_810;
                      }
LABEL_988:
                      v780 = GetProcessHeap();
                      HeapFree(v780, 0, v1298);
                      goto LABEL_989;
                    }
                    v770 = (const void **)v1303;
                    LODWORD(v1297) = 0;
                    LODWORD(v1309) = 4;
                    v772 = RtlUIntAdd(4, *(unsigned int *)v1303, &v1309);
                    if ( v772 < 0 )
                      goto LABEL_1027;
                    v772 = RtlUIntAdd((unsigned int)v1309, v771, &v1309);
                    if ( v772 < 0
                      || (v773 = *((unsigned int *)v770 + 4),
                          v1328 = (size_t)(v770 + 2),
                          v772 = RtlUIntAdd((unsigned int)v1309, v773, &v1309),
                          v772 < 0)
                      || (v772 = RtlUIntAdd((unsigned int)v1309, v774, &v1309), v772 < 0)
                      || (v775 = *((unsigned int *)v770 + 8),
                          v1326 = (SIZE_T)(v770 + 4),
                          v772 = RtlUIntAdd((unsigned int)v1309, v775, &v1309),
                          v772 < 0) )
                    {
LABEL_1027:
                      v3 = v772 | 0x10000000;
                      v1301 = v3;
                      if ( v3 < 0 )
                        goto LABEL_985;
                      v1341 = 8;
                      v805 = RtlUIntAdd(8, (unsigned int)v1308, &v1341);
                      v3 = v805 | 0x10000000;
                      v1301 = v805 | 0x10000000;
                      if ( v805 < 0 )
                        goto LABEL_985;
                      v806 = (v1341 + 7) & 0xFFFFFFF8;
                      if ( (unsigned int)v806 < v1341 )
                      {
                        v3 = -1073741675;
                        goto LABEL_984;
                      }
                      v1346 = (v1341 + 7) & 0xFFFFFFF8;
                      v1301 = RtlUIntAdd(v806, 8, &v1346);
                      v3 = v1301;
                      if ( v1301 < 0 )
                        goto LABEL_985;
                      v808 = v1329[1];
                      v809 = 0;
                      v1325 = v22;
                      v1311 = v598;
                      v1317 = v599;
                      v1298 = v807;
                      v1303 = v770;
                      LODWORD(v1324) = 0;
                      if ( !v1329[1] )
                        goto LABEL_1040;
                      v1303 = v770;
                      v1298 = v807;
                      v1317 = v599;
                      v1311 = v598;
                      v1325 = v22;
                      if ( LODWORD(v1329[0]) > 1 )
                      {
                        v1310 = v1329[1];
                        while ( 1 )
                        {
                          v1301 = RtlULongLongAdd(v808, 4, &v1310);
                          v3 = v1301;
                          if ( v1301 < 0 )
                            break;
                          v1301 = RtlULongLongAdd(v1310, v810, &v1310);
                          v3 = v1301;
                          if ( v1301 < 0 )
                            break;
                          v808 = v1310;
                          if ( v811 != -1 )
                          {
                            v812 = *(_DWORD *)v1310;
                            v1301 = RtlULongLongAdd(v1310, 4, &v1310);
                            v3 = v1301;
                            if ( v1301 < 0 )
                              break;
                            v813 = v1329[1];
                            if ( v1329[1] && LODWORD(v1329[0]) > 2 )
                            {
                              v1310 = v1329[1];
                              while ( 1 )
                              {
                                v1301 = RtlULongLongAdd(v813, 4, &v1310);
                                v3 = v1301;
                                if ( v1301 < 0 )
                                  goto LABEL_1041;
                                v1301 = RtlULongLongAdd(v1310, v816, &v1310);
                                v3 = v1301;
                                if ( v1301 < 0 )
                                  goto LABEL_1041;
                                v813 = v1310;
                                if ( (unsigned int)(v817 + 1) >= 2 )
                                {
                                  v1301 = RtlULongLongAdd(v1310, 4, &v1310);
                                  v3 = v1301;
                                  if ( v1301 < 0 )
                                    goto LABEL_1041;
                                  LODWORD(v1324) = v809;
                                  LODWORD(v1309) = v818;
                                  v1301 = RtlUIntAdd(v818, v1346, &v1309);
                                  v3 = v1301;
                                  if ( v1301 < 0 )
                                    goto LABEL_1056;
                                  v1301 = RtlUIntAdd((unsigned int)v1309, v819, &v1309);
                                  v3 = v1301;
                                  if ( v1301 < 0
                                    || (v1301 = RtlUIntAdd((unsigned int)v1309, v812, &v1309), v3 = v1301, v1301 < 0)
                                    || (v1301 = RtlUIntAdd((unsigned int)v1309, v820, &v1309), v3 = v1301, v1301 < 0)
                                    || (v1301 = RtlUIntAdd((unsigned int)v1309, v821, &v1309), v3 = v1301, v1301 < 0) )
                                  {
LABEL_1056:
                                    if ( v3 < 0 )
                                      goto LABEL_985;
                                  }
                                  else
                                  {
                                    v809 = v1309;
                                    LODWORD(v1324) = v1309;
                                  }
                                  if ( v809 > 0x400000 )
                                  {
                                    v3 = -2147418113;
                                    goto LABEL_984;
                                  }
                                  goto LABEL_1042;
                                }
                              }
                            }
                            goto LABEL_1040;
                          }
                        }
                      }
                      else
                      {
LABEL_1040:
                        v3 = -1073741811;
                        v1301 = -1073741811;
                      }
LABEL_1041:
                      if ( v3 < 0 )
                        goto LABEL_985;
LABEL_1042:
                      v814 = v809;
                      v815 = GetProcessHeap();
                      v696 = HeapAlloc(v815, 8u, v814);
                      if ( !v696 )
                      {
                        v3 = -805306345;
                        v1301 = -805306345;
                        goto LABEL_986;
                      }
                      v1359 = 0;
                      v1366 = 0;
                      v1367 = 0;
                      if ( !dwBytes )
                      {
                        v3 = -2147024809;
LABEL_1071:
                        v1301 = v3;
                        goto LABEL_986;
                      }
                      LODWORD(v1367) = v1297;
                      *(_QWORD *)&v1366 = dwBytes;
                      *(_QWORD *)((char *)&v1367 + 4) = (unsigned int)v1324;
                      *((_QWORD *)&v1366 + 1) = v696;
                      if ( GetModuleHandleExW(1u, L"ntdll.dll", &v1359)
                        && (v823 = GetProcAddress(v1359, "NtQuerySystemInformation")) != 0 )
                      {
                        v824 = ((__int64 (__fastcall *)(__int64, __int128 *))v823)(134, &v1366);
                        v3 = v824 | 0x10000000;
                        v1301 = v824 | 0x10000000;
                        if ( v824 >= 0 )
                        {
                          v825 = DWORD1(v1367);
                          goto LABEL_1074;
                        }
                      }
                      else
                      {
                        v822 = GetLastError();
                        v1301 = v822;
                        v3 = v822;
                        if ( v822 > 0 )
                        {
                          v3 = (unsigned __int16)v822 | 0x80070000;
                          v1301 = v3;
                        }
                        if ( v3 >= 0 )
                        {
                          v3 = -2147467259;
                          goto LABEL_1071;
                        }
                      }
                      if ( v3 == -805306333 )
                      {
                        v3 = -2147024774;
                        goto LABEL_1071;
                      }
                      if ( v3 < 0 )
                        goto LABEL_986;
                      v825 = v1324;
LABEL_1074:
                      LODWORD(v1308) = 0;
                      v1302 = v696;
                      if ( v825 < 4 )
                      {
LABEL_1075:
                        v3 = -805306306;
                        goto LABEL_1071;
                      }
                      LODWORD(v1297) = *v696;
                      v827 = RtlULongLongAdd(v696, 4, &v1302);
                      if ( v827 >= 0 )
                      {
                        v827 = RtlUIntAdd(0, v826, &v1308);
                        if ( v827 < 0 )
                        {
LABEL_1128:
                          v1302 = v696;
                          goto LABEL_1129;
                        }
                        if ( v829 - (int)v1308 < (unsigned int)v830 )
                          goto LABEL_1075;
                        v1328 = (size_t)v1302;
                        v1320 = v830;
                        v827 = RtlULongLongAdd(v1302, (unsigned int)v830, &v1302);
                        if ( v827 >= 0 )
                        {
                          v827 = RtlUIntAdd((unsigned int)v1308, v831, &v1308);
                          if ( v827 >= 0 )
                          {
                            if ( v832 - (int)v1308 < (unsigned int)v833 )
                              goto LABEL_1075;
                            LODWORD(v1324) = *(_DWORD *)v1302;
                            v827 = RtlULongLongAdd(v1302, v833, &v1302);
                            if ( v827 >= 0 )
                            {
                              v827 = RtlUIntAdd((unsigned int)v1308, v834, &v1308);
                              if ( v827 >= 0 )
                              {
                                if ( v835 - (int)v1308 < (unsigned int)v836 )
                                  goto LABEL_1075;
                                pcchLength = (size_t)v1302;
                                v1326 = v836;
                                v827 = RtlULongLongAdd(v1302, (unsigned int)v836, &v1302);
                                if ( v827 >= 0 )
                                {
                                  v827 = RtlUIntAdd((unsigned int)v1308, v837, &v1308);
                                  if ( v827 >= 0 )
                                  {
                                    if ( v838 - (int)v1308 < v839 )
                                      goto LABEL_1075;
                                    LODWORD(v1322) = *(_DWORD *)v1302;
                                    v827 = RtlULongLongAdd(v1302, 4, &v1302);
                                    if ( v827 >= 0 )
                                    {
                                      v827 = RtlUIntAdd((unsigned int)v1308, 4, &v1308);
                                      if ( v827 >= 0 )
                                      {
                                        if ( v840 - (int)v1308 < v841 )
                                          goto LABEL_1075;
                                        v827 = RtlUIntAdd((unsigned int)v1308, v841, &v1308);
                                        if ( v827 >= 0 )
                                        {
                                          if ( v842 != (_DWORD)v1308 )
                                            goto LABEL_1075;
                                          v845 = (unsigned int)v1297;
                                          if ( (unsigned int)(v1297 + v843 + v844) + 12LL != v842 )
                                            goto LABEL_1075;
                                          v846 = GetProcessHeap();
                                          v847 = (SIZE_T)HeapAlloc(v846, 8u, 0x30u);
                                          v1299 = v847;
                                          v779 = v1298;
                                          if ( !v847 )
                                          {
                                            v3 = -805306345;
                                            v1307 = 0;
                                            v1301 = -805306345;
                                            goto LABEL_987;
                                          }
                                          v1325 = v22;
                                          v1311 = v598;
                                          v1317 = v599;
                                          v1310 = 0;
                                          if ( v1328 )
                                          {
                                            *(_DWORD *)v847 = v845;
                                            v848 = GetProcessHeap();
                                            v849 = HeapAlloc(v848, 8u, v845);
                                            if ( !v849 )
                                            {
LABEL_1107:
                                              v857 = v1299;
                                              v827 = -1073741801;
                                              v1302 = v696;
                                              v1320 = *(_BYTE **)(v1299 + 8);
                                              if ( v1320 )
                                              {
                                                v858 = GetProcessHeap();
                                                HeapFree(v858, 0, v1320);
                                                v857 = v1299;
                                                *(_QWORD *)(v1299 + 8) = 0;
                                              }
                                              v1320 = *(_BYTE **)(v857 + 24);
                                              if ( v1320 )
                                              {
                                                v859 = GetProcessHeap();
                                                HeapFree(v859, 0, v1320);
                                                v857 = v1299;
                                                *(_QWORD *)(v1299 + 24) = 0;
                                              }
                                              v1320 = *(_BYTE **)(v857 + 40);
                                              if ( v1320 )
                                              {
                                                v860 = GetProcessHeap();
                                                HeapFree(v860, 0, v1320);
                                                *(_QWORD *)(v1299 + 40) = 0;
                                              }
                                              v861 = GetProcessHeap();
                                              HeapFree(v861, 0, (LPVOID)v1299);
                                              v862 = (unsigned int *)v1310;
                                              goto LABEL_1117;
                                            }
                                            *(_QWORD *)(v1299 + 8) = v849;
                                            v827 = 0;
                                            memcpy_0(v849, (const void *)v1328, (size_t)v1320);
                                            v847 = v1299;
                                          }
                                          else
                                          {
                                            *(_DWORD *)v847 = 0;
                                            v827 = 0;
                                            *(_QWORD *)(v847 + 8) = 0;
                                          }
                                          if ( pcchLength )
                                          {
                                            *(_DWORD *)(v847 + 16) = v1324;
                                            v850 = GetProcessHeap();
                                            v851 = HeapAlloc(v850, 8u, v1326);
                                            v852 = v1299;
                                            if ( !v851 )
                                            {
LABEL_1106:
                                              v1299 = v852;
                                              v1325 = v22;
                                              v1311 = v598;
                                              v1317 = v599;
                                              goto LABEL_1107;
                                            }
                                            *(_QWORD *)(v1299 + 24) = v851;
                                            v827 = 0;
                                            memcpy_0(v851, (const void *)pcchLength, v1326);
                                            v847 = v1299;
                                          }
                                          else
                                          {
                                            *(_DWORD *)(v847 + 16) = 0;
                                            *(_QWORD *)(v847 + 24) = 0;
                                          }
                                          if ( v1302 )
                                          {
                                            v853 = (unsigned int)v1322;
                                            *(_DWORD *)(v847 + 32) = v1322;
                                            v854 = v853;
                                            v1320 = (_BYTE *)v853;
                                            v855 = GetProcessHeap();
                                            v856 = HeapAlloc(v855, 8u, v854);
                                            v852 = v1299;
                                            if ( !v856 )
                                              goto LABEL_1106;
                                            *(_QWORD *)(v1299 + 40) = v856;
                                            v827 = 0;
                                            memcpy_0(v856, v1302, (size_t)v1320);
                                            v847 = v1299;
                                          }
                                          else
                                          {
                                            *(_DWORD *)(v847 + 32) = 0;
                                            *(_QWORD *)(v847 + 40) = 0;
                                          }
                                          v862 = (unsigned int *)v847;
                                          v1310 = v847;
                                          v1302 = v696;
                                          v1317 = v599;
                                          v1311 = v598;
                                          v1325 = v22;
LABEL_1117:
                                          if ( v827 < 0 )
                                          {
                                            v828 = 0;
                                            v1307 = 0;
                                            if ( v862 )
                                            {
                                              v1320 = (_BYTE *)*((_QWORD *)v862 + 1);
                                              if ( v1320 )
                                              {
                                                v863 = GetProcessHeap();
                                                HeapFree(v863, 0, v1320);
                                                v862 = (unsigned int *)v1310;
                                                *(_QWORD *)(v1310 + 8) = 0;
                                              }
                                              v1320 = (_BYTE *)*((_QWORD *)v862 + 3);
                                              if ( v1320 )
                                              {
                                                v864 = GetProcessHeap();
                                                HeapFree(v864, 0, v1320);
                                                v862 = (unsigned int *)v1310;
                                                *(_QWORD *)(v1310 + 24) = 0;
                                              }
                                              v1320 = (_BYTE *)*((_QWORD *)v862 + 5);
                                              if ( v1320 )
                                              {
                                                v865 = GetProcessHeap();
                                                HeapFree(v865, 0, v1320);
                                                *(_QWORD *)(v1310 + 40) = 0;
                                              }
                                              v866 = GetProcessHeap();
                                              HeapFree(v866, 0, (LPVOID)v1310);
                                              v828 = 0;
                                              v1307 = 0;
                                            }
                                          }
                                          else
                                          {
                                            v828 = v862;
                                            v1307 = v862;
                                          }
LABEL_1129:
                                          v3 = v827 | 0x10000000;
                                          v1301 = v3;
                                          if ( v3 < 0 )
                                            goto LABEL_986;
                                          if ( !v828 || (v1326 = *((_QWORD *)v828 + 1)) == 0 || !*v828 )
                                          {
                                            v3 = -805306355;
                                            goto LABEL_1071;
                                          }
                                          v867 = *v828 - 8LL;
                                          lpMem = (LPVOID)v867;
                                          v1313 = MemoryAlloc(v867);
                                          if ( !v1313 )
                                          {
LABEL_1161:
                                            v3 = -805306367;
                                            v1313 = 0;
                                            goto LABEL_1071;
                                          }
                                          v868 = 0;
                                          uBytes_4 = 0;
                                          v1299 = 0x7F1137FAB69605ELL;
                                          pcchLength = v1326;
                                          v1310 = (SIZE_T)v1313;
                                          v869 = v867 & 7;
                                          if ( (v867 & 7) != 0 )
                                          {
                                            v870 = 0;
                                            LODWORD(v1324) = 0;
                                            LODWORD(v1322) = 0;
                                            v871 = 0;
                                            v872 = 0;
                                            v873 = (unsigned __int8 *)pcchLength;
                                            do
                                            {
                                              v874 = *v873++;
                                              LODWORD(v1297) = 8 * v870;
                                              if ( v870 >= 4 )
                                                v871 |= v874 << (56 - v1297);
                                              else
                                                v872 |= v874 << (24 - v1297);
                                              ++v870;
                                            }
                                            while ( (int)v870 < (int)v869 );
                                            LODWORD(v1322) = v872;
                                            v868 = uBytes_4;
                                            LODWORD(v1324) = v871;
                                            pcchLength = (size_t)v873;
                                            v1302 = v696;
                                            v1317 = v599;
                                            v1311 = v598;
                                            v1325 = v22;
                                            v875 = v1322 ^ 0x92F65A5;
                                            v876 = v871 ^ 0x699A899C;
                                            v877 = 0;
                                            v878 = v1322 ^ 0x92F65A5;
                                            v879 = v871 ^ 0x699A899C;
                                            if ( (v867 & 7) != 0 )
                                            {
                                              v880 = (_BYTE *)v1310;
                                              do
                                              {
                                                v1320 = v880 + 1;
                                                if ( v877 >= 4 )
                                                {
                                                  v879 = __ROR4__(v879, 24);
                                                  v881 = v879;
                                                }
                                                else
                                                {
                                                  v878 = __ROR4__(v878, 24);
                                                  v881 = v878;
                                                }
                                                *v880 = v881;
                                                ++v877;
                                                v880 = v1320;
                                              }
                                              while ( (int)v877 < (int)v869 );
                                              v1310 = (SIZE_T)v1320;
                                            }
                                            if ( v869 <= 4 )
                                            {
                                              v882 = 0;
                                              if ( v869 < 4 )
                                                v875 = v875 >> (8 * (4 - v869)) << (8 * (4 - v869));
                                            }
                                            else
                                            {
                                              v882 = v876 >> (8 * (8 - v869)) << (8 * (8 - v869));
                                            }
                                          }
                                          else
                                          {
                                            v882 = 0;
                                            LODWORD(v1322) = 0;
                                            v875 = 0;
                                            LODWORD(v1324) = -1;
                                          }
                                          v883 = v867 >> 3;
                                          if ( v867 >> 3 )
                                          {
                                            v884 = HIDWORD(v1299);
                                            v885 = (unsigned __int8 *)pcchLength;
                                            v886 = HIDWORD(v1299) ^ 0xAB69605E;
                                            v887 = (_BYTE *)v1310;
                                            v888 = v1324;
                                            v889 = v1322;
                                            LODWORD(v1309) = WORD2(v1299);
                                            LODWORD(v1308) = 24670;
                                            v890 = v883;
                                            v1328 = 0;
                                            LODWORD(v1297) = HIDWORD(v1299) ^ 0xAB69605E;
                                            do
                                            {
                                              v891 = v885[1];
                                              v892 = *v885;
                                              v893 = v885[4];
                                              v885 += 8;
                                              v894 = *(v885 - 5) | ((*(v885 - 6) | ((v891 | (v892 << 8)) << 8)) << 8);
                                              v895 = v875 ^ v894;
                                              v896 = *(v885 - 1)
                                                   | ((*(v885 - 2) | ((*(v885 - 3) | (v893 << 8)) << 8)) << 8);
                                              v897 = v882 ^ v896 ^ v875 ^ v894 ^ v886;
                                              v898 = v895
                                                   ^ (__ROR4__(v897, 22) + v1309 * __ROR4__(v897 + 1419157410, 27));
                                              v899 = v897
                                                   ^ (WORD1(v1299) * __ROR4__(v898 + v884, 9) - __ROR4__(v898, 30));
                                              v900 = v898 ^ (v1308 * (v899 - v1309) - (v899 >> 13));
                                              v901 = v899
                                                   ^ (HIWORD(v1299) * __ROR4__(v900 ^ WORD1(v1299), 26)
                                                    - __ROR4__(v900, 30));
                                              v902 = v900 ^ (v884 - (v901 ^ 0xAB69605E));
                                              v903 = v901 ^ (WORD1(v1299) * (v902 ^ v1309)) ^ __ROR4__(v902, 6);
                                              v904 = v902 ^ (__ROR4__(v903, 30) + v1308 * __ROR4__(v903 + v884, 15));
                                              v905 = v903
                                                   ^ (HIWORD(v1299) * __ROR4__(v904 + 1419157410, 14)
                                                    - __ROR4__(v904, 24));
                                              v906 = v904
                                                   ^ __ROR4__(v905, 10)
                                                   ^ (v1309 * __ROR4__(v905 ^ 0xAB69605E, 12));
                                              v907 = v906
                                                   ^ (HIWORD(v1299)
                                                    * (v1308
                                                     + __ROR4__(
                                                         ~(v905 ^ (v906 >> 10) ^ (WORD1(v1299) * (v906 ^ HIWORD(v1299)))),
                                                         5)));
                                              v908 = v905
                                                   ^ (v906 >> 10)
                                                   ^ (WORD1(v1299) * (v906 ^ HIWORD(v1299)))
                                                   ^ (v907 - HIWORD(v1299))
                                                   ^ 0xAB69605E;
                                              v909 = v907 ^ ((v908 >> 2) + v1309 * __ROR4__(v908 ^ HIWORD(v1299), 30));
                                              v910 = v908
                                                   ^ (__ROR4__(v909, 25)
                                                    + WORD1(v1299) * __ROR4__(v909 - HIDWORD(v1299), 6));
                                              v911 = v909 ^ (v1308 * (v910 ^ v1309) + __ROR4__(v910, 9));
                                              v912 = v910
                                                   ^ (__ROR4__(v911, 25)
                                                    + HIWORD(v1299) * __ROR4__(v911 ^ WORD1(v1299), 27));
                                              v884 = HIDWORD(v1299);
                                              v913 = v1297 ^ v911 ^ v912;
                                              v914 = v912 ^ (v1309 * (__ROR4__(v913, 3) - WORD1(v1299)));
                                              v915 = v913
                                                   ^ (v1308 * __ROR4__(v914 - HIDWORD(v1299), 1) - __ROR4__(v914, 6));
                                              v886 = v1297;
                                              v916 = v914
                                                   ^ (__ROR4__(v915, 18)
                                                    + HIWORD(v1299) * __ROR4__(v915 - 1419157410, 29));
                                              v917 = v915
                                                   ^ (v1309 * __ROR4__(v916 - 1419157410, 17) - __ROR4__(v916, 14));
                                              v918 = v916 ^ (v917 >> 3) ^ (WORD1(v1299) * (v1308 ^ v917));
                                              v882 = v888 ^ v918;
                                              v888 = v896;
                                              v875 = v889
                                                   ^ v917
                                                   ^ __ROR4__(v918, 30)
                                                   ^ (v1308 * __ROR4__(HIDWORD(v1299) ^ v918, 28));
                                              v889 = v894;
                                              v887[3] = v875;
                                              v887[7] = v882;
                                              v887[2] = __ROR4__(v875, 8);
                                              v887[6] = __ROR4__(v882, 8);
                                              v887[1] = __ROR4__(v875, 16);
                                              v887[5] = __ROR4__(v882, 16);
                                              *v887 = __ROR4__(v875, 24);
                                              v887[4] = __ROR4__(v882, 24);
                                              v887 += 8;
                                              ++v1328;
                                            }
                                            while ( v1328 < v890 );
                                            v868 = uBytes_4;
                                            v22 = v1325;
                                            v598 = v1311;
                                            v599 = v1317;
                                            v696 = v1302;
                                            v867 = (unsigned __int64)lpMem;
                                          }
                                          for ( j = 0; j < v867; ++j )
                                            v868 ^= *((_BYTE *)v1313 + j);
                                          if ( v868 != *(_QWORD *)(v867 + v1326) )
                                          {
                                            MemoryFree(v1313);
                                            goto LABEL_1161;
                                          }
                                          LODWORD(v1309) = 0;
                                          v1310 = (SIZE_T)v1313;
                                          if ( (unsigned int)v867 < 4 )
                                          {
LABEL_1163:
                                            v920 = -1073741762;
LABEL_1176:
                                            v3 = v920 | 0x10000000;
                                            goto LABEL_1071;
                                          }
                                          v920 = RtlULongLongAdd(v1313, 4, &v1310);
                                          if ( v920 < 0 )
                                            goto LABEL_1174;
                                          v920 = RtlUIntAdd(0, 4, &v1309);
                                          if ( v920 < 0 )
                                            goto LABEL_1173;
                                          if ( (unsigned int)((_DWORD)lpMem - v1309) < 4 )
                                          {
                                            v925 = v1313;
LABEL_1168:
                                            v920 = -1073741762;
                                            v1313 = v925;
LABEL_1175:
                                            v1298 = v923;
                                            v1303 = v922;
                                            v1307 = v924;
                                            goto LABEL_1176;
                                          }
                                          LODWORD(v1324) = *(_DWORD *)v1310;
                                          v920 = RtlULongLongAdd(v1310, 4, &v1310);
                                          if ( v920 < 0 || (v920 = RtlUIntAdd((unsigned int)v1309, 4, &v1309), v920 < 0) )
                                          {
LABEL_1173:
                                            v921 = v1313;
LABEL_1174:
                                            v1313 = v921;
                                            goto LABEL_1175;
                                          }
                                          if ( (int)lpMem - (int)v1309 < (unsigned int)v1324 )
                                          {
                                            v920 = -1073741762;
                                            goto LABEL_1173;
                                          }
                                          v920 = RtlUIntAdd((unsigned int)v1309, (unsigned int)v1324, &v1309);
                                          if ( v920 < 0 )
                                            goto LABEL_1173;
                                          v925 = v1313;
                                          if ( (unsigned __int64)v1313 + (unsigned int)lpMem < (unsigned int)v1324
                                                                                             + v1310
                                            || (unsigned __int64)v1313
                                             + (unsigned int)lpMem
                                             - (unsigned int)v1324
                                             - v1310 >= 8 )
                                          {
                                            goto LABEL_1168;
                                          }
                                          LODWORD(v1308) = *(_DWORD *)v1313;
                                          v1318 = 0;
                                          v1328 = 0;
                                          v1326 = 0;
                                          LODWORD(v1322) = 0;
                                          if ( v1310 )
                                          {
                                            v920 = RtlULongLongAdd(v1310, (unsigned int)v1324, &v1318);
                                            v1307 = v927;
                                            v1303 = v928;
                                            v1298 = v929;
                                            if ( v920 < 0 )
                                            {
LABEL_1201:
                                              v942 = Size;
LABEL_1202:
                                              if ( v920 < 0 || (_DWORD)v1308 == v942 )
                                                goto LABEL_1176;
                                              goto LABEL_1163;
                                            }
                                            lpMem = v926;
                                            if ( v926 < v1318 )
                                            {
                                              while ( 1 )
                                              {
                                                v920 = RtlULongLongAdd(v926, 4, &v1328);
                                                if ( v920 < 0 )
                                                  goto LABEL_1201;
                                                if ( v1328 > (unsigned __int64)v1318 )
                                                  goto LABEL_1192;
                                                v931 = *v930;
                                                LODWORD(v1297) = 0;
                                                v920 = RtlUIntAdd(4, v931, &v1297);
                                                if ( v920 < 0 )
                                                  goto LABEL_1176;
                                                LODWORD(v1309) = v22;
                                                v932 = v598;
                                                v933 = v696;
                                                v934 = v1313;
                                                v1311 = v1313;
                                                v920 = RtlULongLongAdd(lpMem, (unsigned int)v1297, &v1326);
                                                v1313 = v934;
                                                v696 = v933;
                                                v1307 = v937;
                                                v598 = v932;
                                                v1303 = v935;
                                                v22 = v1309;
                                                v1298 = v936;
                                                if ( v920 < 0 )
                                                  goto LABEL_1201;
                                                v926 = (void *)v1326;
                                                v938 = v1318;
                                                lpMem = (LPVOID)v1326;
                                                v1307 = v937;
                                                v1303 = v935;
                                                v1298 = v936;
                                                v1313 = v1311;
                                                if ( v1326 > (unsigned __int64)v1318 )
                                                  goto LABEL_1192;
                                                LODWORD(v1322) = v1322 + 1;
                                                if ( v1326 >= (unsigned __int64)v1318 )
                                                {
                                                  v1313 = v1311;
                                                  v1307 = v937;
                                                  v1303 = v935;
                                                  v1298 = v936;
                                                  goto LABEL_1191;
                                                }
                                              }
                                            }
                                            v938 = v1318;
LABEL_1191:
                                            if ( v926 != v938 )
                                            {
LABEL_1192:
                                              v920 = -1073741811;
                                              goto LABEL_1176;
                                            }
                                          }
                                          else
                                          {
                                            v920 = 0;
                                            v1307 = v924;
                                            v1303 = v922;
                                            v1298 = v923;
                                          }
                                          v939 = v1324;
                                          v940 = 0;
                                          v1328 = 0;
                                          if ( (_DWORD)v1324 )
                                          {
                                            v941 = GetProcessHeap();
                                            v1328 = (size_t)HeapAlloc(v941, 8u, (unsigned int)v1324);
                                            v940 = (void *)v1328;
                                            if ( !v1328 )
                                            {
                                              v920 = -1073741801;
                                              goto LABEL_1176;
                                            }
                                            v939 = v1324;
                                            v920 = 0;
                                          }
                                          if ( v1310 )
                                            memcpy_0(v940, (const void *)v1310, v939);
                                          v1319 = (LPVOID)v1328;
                                          v942 = v1322;
                                          LODWORD(Size) = v1322;
                                          goto LABEL_1202;
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
                      v828 = (unsigned int *)v1307;
                      goto LABEL_1128;
                    }
                    v1303 = v770;
                    v776 = v1309;
                    v777 = GetProcessHeap();
                    v1311 = HeapAlloc(v777, 8u, v776);
                    v778 = v1311;
                    if ( !v1311 )
                    {
                      v3 = -805306345;
LABEL_984:
                      v1301 = v3;
LABEL_985:
                      v696 = v1302;
LABEL_986:
                      v779 = v1298;
                      goto LABEL_987;
                    }
                    v770 = (const void **)v1303;
                    v795 = v1298;
                    *(_DWORD *)v1311 = *(_DWORD *)v1303;
                    v1298 = v795;
                    v1299 = (SIZE_T)v778;
                    v772 = RtlULongLongAdd(v778, 4, &v1299);
                    if ( v772 < 0 )
                    {
                      v1298 = v797;
                      LODWORD(v1308) = v798;
                      v1311 = v796;
                    }
                    else
                    {
                      memcpy_0((void *)v1299, v770[1], *(unsigned int *)v770);
                      v772 = RtlULongLongAdd(v1299, *(unsigned int *)v770, &v1299);
                      if ( v772 >= 0 )
                      {
                        v799 = v1299;
                        *(_DWORD *)v1299 = *(_DWORD *)v1328;
                        v772 = RtlULongLongAdd(v799, 4, &v1299);
                        if ( v772 >= 0 )
                        {
                          memcpy_0((void *)v1299, v770[3], *v800);
                          v772 = RtlULongLongAdd(v1299, *(unsigned int *)v1328, &v1299);
                          if ( v772 >= 0 )
                          {
                            v801 = v1299;
                            *(_DWORD *)v1299 = *(_DWORD *)v1326;
                            v772 = RtlULongLongAdd(v801, 4, &v1299);
                            if ( v772 >= 0 )
                            {
                              memcpy_0((void *)v1299, v770[5], *v802);
                              v803 = RtlULongLongAdd(v1299, *(unsigned int *)v1326, &v1299);
                              v1303 = v770;
                              v772 = v803;
                              if ( v803 >= 0 )
                              {
                                dwBytes = (SIZE_T)v1311;
                                LODWORD(v1297) = v1309;
                                goto LABEL_1027;
                              }
LABEL_1026:
                              v804 = GetProcessHeap();
                              HeapFree(v804, 0, v1311);
                              goto LABEL_1027;
                            }
                          }
                        }
                      }
                    }
                    v1303 = v770;
                    goto LABEL_1026;
                  }
                }
              }
              v750 = -1073741801;
              v765 = v1327;
              v1320 = (_BYTE *)*((_QWORD *)v1327 + 1);
              if ( v1320 )
              {
                v766 = GetProcessHeap();
                HeapFree(v766, 0, v1320);
                v765 = v1327;
                *((_QWORD *)v1327 + 1) = 0;
              }
              v1320 = (_BYTE *)v765[3];
              if ( v1320 )
              {
                v767 = GetProcessHeap();
                HeapFree(v767, 0, v1320);
                v765 = v1327;
                *((_QWORD *)v1327 + 3) = 0;
              }
              v1320 = (_BYTE *)v765[5];
              if ( v1320 )
              {
                v768 = GetProcessHeap();
                HeapFree(v768, 0, v1320);
                *((_QWORD *)v1327 + 5) = 0;
              }
              v769 = GetProcessHeap();
              HeapFree(v769, 0, v1327);
            }
            else
            {
              v750 = -1073741801;
            }
            v751 = v1303;
            goto LABEL_954;
          }
          pcchLength = v1329[1];
          if ( v676 )
          {
            do
            {
              v677 = *v675;
              LODWORD(v1297) = 0;
              v614 = RtlUIntAdd(4, v677, &v1297);
              if ( v614 < 0 )
                goto LABEL_809;
              v614 = RtlULongLongAdd(v678, (unsigned int)v1297, &pcchLength);
              if ( v614 < 0 )
                goto LABEL_809;
              v675 = (unsigned int *)pcchLength;
            }
            while ( v680 + 1 < v679 );
          }
          v614 = RtlULongLongAdd(v675, 4, &v1321);
          if ( v614 >= 0 )
          {
            if ( (unsigned __int64)(v681 + 2) <= v1329[1] + HIDWORD(v1329[0]) )
            {
              v682 = v1321;
              *v681 = 4;
              *v682 = uBytes;
              goto LABEL_903;
            }
LABEL_805:
            v614 = -1073741789;
          }
LABEL_809:
          v1301 = v614;
          v3 = v614;
          goto LABEL_810;
        }
        *v313 = qword_1801284D0;
        v1315 = __rdtsc();
        v315 = GetProcessHeap();
        v316 = HeapAlloc(v315, 8u, 0xC4u);
        v22 = v1309;
        uBytes = v1312;
        if ( !v316 )
          goto LABEL_777;
        dwBytes = 0;
        v1320 = 0;
        LODWORD(v1321) = 0;
        if ( (int)RtlULongLongAdd(v316, 4, &v1321) >= 0 )
        {
          if ( v316 + 2 > v316 + 49 )
            goto LABEL_773;
          v318 = v1321;
          *v316 = 4;
          uBytes = v317;
          *v318 = 4;
          v1320 = 0;
          LODWORD(v1321) = 0;
          v319 = v316;
          LODWORD(v1297) = 8;
          for ( lpMem = v316; ; v319 = lpMem )
          {
            if ( *v319 >= 0xFFFFFFFC )
              goto LABEL_770;
            if ( (int)RtlULongLongAdd(v319, (unsigned int)(*v319 + 4), &lpMem) < 0 )
              goto LABEL_773;
            if ( v320 != -1 )
              break;
          }
          if ( (int)RtlULongLongAdd(lpMem, 4, &v1321) >= 0 && v321 + 41 <= v316 + 49 )
          {
            *v321 = 160;
            if ( v311 )
            {
              memcpy_0(v1321, v311, 0xA0u);
              v317 = uBytes;
              v322 = v1297;
            }
            uBytes = v317;
            v1302 = v314;
            v1320 = 0;
            LODWORD(v1312) = 2;
            LODWORD(v1321) = 0;
            if ( v314 )
            {
              if ( !v322 )
                goto LABEL_770;
            }
            else if ( v322 )
            {
              goto LABEL_770;
            }
            lpMem = v316;
            v323 = v316;
            LODWORD(v1297) = 0;
            do
            {
              if ( *v323 >= 0xFFFFFFFC )
                goto LABEL_770;
              if ( (int)RtlULongLongAdd(v323, (unsigned int)(*v323 + 4), &lpMem) < 0 )
                goto LABEL_773;
              v323 = lpMem;
              LODWORD(v1297) = v1297 + 1;
            }
            while ( (unsigned int)v1297 < v324 );
            if ( (int)RtlULongLongAdd(lpMem, 4, &v1321) >= 0
              && (char *)v325 + v327 + 4 <= (char *)v316 + (unsigned int)v1327 )
            {
              *v325 = v327;
              if ( v314 )
              {
                memcpy_0(v1321, v314, v327);
                v326 = v1312;
              }
              v1320 = 0;
              LODWORD(v1321) = 0;
              lpMem = v316;
              v328 = v316;
              if ( v326 != -1 )
              {
                while ( *v328 < 0xFFFFFFFC )
                {
                  if ( (int)RtlULongLongAdd(v328, (unsigned int)(*v328 + 4), &lpMem) < 0 )
                    goto LABEL_773;
                  v328 = lpMem;
                  if ( v330 + 1 >= v329 )
                    goto LABEL_483;
                }
LABEL_770:
                if ( !v316 )
                  goto LABEL_774;
                goto LABEL_773;
              }
LABEL_483:
              if ( (int)RtlULongLongAdd(v328, 4, &v1321) >= 0
                && v331 + 3 <= (_DWORD *)((char *)v316 + (unsigned int)v1327) )
              {
                v333 = v1321;
                v334 = v1315;
                *v331 = 8;
                *v333 = v334;
                LODWORD(v1312) = v332 + 1;
                v1315 = __rdtsc();
                if ( (unsigned int)v1327 >= 0xFFFFFFF8 )
                  goto LABEL_770;
                v1318 = (void *)(((_DWORD)v1327 + 15) & 0xFFFFFFF8);
                if ( (unsigned int)v1318 < (int)v1327 + 8 )
                  goto LABEL_770;
                LODWORD(v1324) = 0;
                v1326 = ((_DWORD)v1327 + 15) & 0xFFFFFFF8;
                v335 = GetProcessHeap();
                Src = HeapAlloc(v335, 8u, v1326);
                v336 = Src;
                if ( !Src )
                {
                  v337 = -805306345;
                  goto LABEL_560;
                }
                *(_DWORD *)Src = v1312;
                v1302 = v314;
                v1298 = 0;
                lpMem = 0;
                v1307 = 0;
                v1303 = 0;
                v1313 = 0;
                v1310 = (SIZE_T)v336;
                v338 = RtlULongLongAdd(v336, 4, &v1310);
                if ( v338 < 0
                  || (v341 = v1310, *(_DWORD *)v1310 = (_DWORD)v1327, v338 = RtlULongLongAdd(v341, 4, &v1310), v338 < 0) )
                {
                  v1326 = v339;
                  uBytes = v340;
                  Src = 0;
                  LODWORD(v1318) = 0;
                  v343 = GetProcessHeap();
                  HeapFree(v343, 0, (LPVOID)v1326);
                }
                else
                {
                  *(_QWORD *)(v339 + v1326 - 8) = v1315;
                  memcpy_0((void *)v1310, v316, v342);
                }
                v337 = v338 | 0x10000000;
                if ( v337 < 0 )
                  goto LABEL_536;
                if ( !Src )
                  goto LABEL_769;
                v344 = (unsigned int)v1318;
                if ( !(_DWORD)v1318
                  || (v1310 = (unsigned int)v1318 + 8LL,
                      v345 = GetProcessHeap(),
                      v1308 = (SIZE_T)HeapAlloc(v345, 0, v344 + 8),
                      (v346 = v1308) == 0) )
                {
                  v337 = -805306367;
                  goto LABEL_537;
                }
                v347 = 0;
                uBytes_4 = 0;
                v348 = 0;
                v1311 = 0;
                if ( v344 )
                {
                  do
                    v347 ^= *((_BYTE *)Src + v348++);
                  while ( v348 < v344 );
                  uBytes_4 = v347;
                }
                v349 = v1302;
                v1325 = v22;
                v1327 = v311;
                v1319 = v316;
                v1317 = (void *)0xC81ECB17B1B54A58LL;
                v1315 = (unsigned __int64)(unsigned int)v1318 >> 3;
                if ( v1315 )
                {
                  v350 = (_BYTE *)v1308;
                  v351 = (unsigned __int8 *)Src;
                  v352 = WORD2(v1317);
                  v353 = v1315;
                  v354 = -1;
                  LODWORD(v1309) = WORD1(v1317);
                  v355 = 0;
                  v356 = HIDWORD(v1317) ^ 0xB1B54A58;
                  v1326 = 0;
                  LODWORD(v1297) = 0;
                  LODWORD(Size) = 0;
                  do
                  {
                    v357 = v351[1];
                    v358 = *v351;
                    v359 = v351[4];
                    v351 += 8;
                    v360 = *(v351 - 5) | ((*(v351 - 6) | ((v357 | (v358 << 8)) << 8)) << 8);
                    v361 = *(v351 - 1) | ((*(v351 - 2) | ((*(v351 - 3) | (v359 << 8)) << 8)) << 8);
                    v362 = v355 ^ v360 ^ ((v354 ^ v361) - 19032);
                    v363 = __ROR4__(v362, 15);
                    v364 = HIDWORD(v1317) ^ v362;
                    v365 = v354 ^ v361 ^ (__ROR4__(v364, 7) + WORD1(v1317) * v363);
                    v366 = v364 ^ (v352 * __ROR4__(v365 - 1313519016, 9) - __ROR4__(v365, 10));
                    v367 = v365 ^ (__ROR4__(v366, 27) + HIWORD(v1317) * __ROR4__(v366 ^ v352, 28));
                    v368 = v366 ^ (HIDWORD(v1317) - (v367 ^ 0xB1B54A58));
                    v369 = v367 ^ (WORD1(v1317) * (v368 - 19032) - (v368 >> 6));
                    v370 = v368 ^ (19032 * (v352 ^ __ROR4__(v369, 15)));
                    v371 = v369 ^ (v352 * (HIWORD(v1317) + __ROR4__(~v370, 3)));
                    v372 = v370 ^ (v371 - 19032 - HIDWORD(v1317));
                    v373 = v371 ^ (v1309 * (HIWORD(v1317) ^ v372)) ^ __ROR4__(v372, 10);
                    v374 = v372 ^ __ROR4__(v373, 3) ^ (v352 * __ROR4__(v373 ^ 0x4A58, 26));
                    v375 = v373 ^ (19032 * (__ROR4__(v374, 15) - HIWORD(v1317)));
                    v376 = v374
                         ^ ((v375 ^ (v375 >> 14)) >> 1)
                         ^ (19032 * (HIWORD(v1317) ^ v375))
                         ^ (19032 * ((8 * (v375 - v352)) | ((v375 - v352) >> 29)));
                    v377 = v375 ^ (WORD1(v1317) * (v376 - v352) - (v376 >> 13));
                    v378 = v376 ^ __ROR4__(v377, 11) ^ (v352 * __ROR4__(-1313519016 - v377, 9));
                    v379 = v377 ^ (v378 + 1313519016 - HIWORD(v1317));
                    v380 = v378 ^ (19032 * (v379 ^ WORD1(v1317)) - __ROR4__(v379, 7));
                    v381 = v379 ^ (WORD1(v1317) * __ROR4__(HIWORD(v1317) ^ v380, 28) - __ROR4__(v380, 16));
                    v382 = v380 ^ (__ROR4__(v381, 4) + v352 * __ROR4__(-1313519016 - v381, 10));
                    v383 = v381 ^ __ROR4__(v382, 9) ^ (HIWORD(v1317) * __ROR4__(v382 + 1313519016, 4));
                    v384 = v382 ^ (19032 * __ROR4__(HIDWORD(v1317) ^ v383, 24) - __ROR4__(v383, 30));
                    v385 = v383 ^ (WORD1(v1317) * __ROR4__(HIDWORD(v1317) - v384, 11) - __ROR4__(v384, 12));
                    v386 = v384 ^ (v385 >> 8) ^ (v352 * (v385 ^ WORD1(v1317)));
                    v387 = v356 ^ v386;
                    v355 = v1297 ^ v386;
                    v354 = v385 ^ Size ^ v387;
                    v350[3] = v355;
                    v350[7] = v354;
                    v350[2] = __ROR4__(v355, 8);
                    v350[6] = __ROR4__(v354, 8);
                    v350[1] = __ROR4__(v355, 16);
                    v350[5] = __ROR4__(v354, 16);
                    *v350 = __ROR4__(v355, 24);
                    v350[4] = __ROR4__(v354, 24);
                    v350 += 8;
                    LODWORD(v1297) = v360;
                    LODWORD(Size) = v361;
                    ++v1326;
                  }
                  while ( v1326 < v353 );
                  v347 = uBytes_4;
                  v3 = v1301;
                  v22 = v1325;
                  v316 = v1319;
                  v311 = v1327;
                  v349 = v1302;
                  v346 = v1308;
                }
                *(_QWORD *)(v346 + (unsigned int)v1318) = v347;
                v388 = GetProcessHeap();
                v1299 = (SIZE_T)HeapAlloc(v388, 8u, 0x30u);
                if ( v1299 )
                {
                  v1302 = v349;
                  v398 = v1299;
                  *(_DWORD *)v1299 = v1310;
                  v399 = GetProcessHeap();
                  v400 = HeapAlloc(v399, 8u, (unsigned int)v1310);
                  if ( v400 )
                  {
                    *(_QWORD *)(v398 + 8) = v400;
                    memcpy_0(v400, (const void *)v1308, (unsigned int)v1310);
                    *(_DWORD *)(v398 + 16) = 160;
                    v401 = GetProcessHeap();
                    v402 = HeapAlloc(v401, 8u, 0xA0u);
                    if ( v402 )
                    {
                      *(_QWORD *)(v398 + 24) = v402;
                      *v402 = xmmword_1801284E0;
                      v402[1] = xmmword_1801284F0;
                      v402[2] = xmmword_180128500;
                      v402[3] = xmmword_180128510;
                      v402[4] = xmmword_180128520;
                      v402[5] = xmmword_180128530;
                      v402[6] = xmmword_180128540;
                      v402[7] = xmmword_180128550;
                      v402[8] = xmmword_180128560;
                      v402[9] = xmmword_180128570;
                      *(_DWORD *)(v398 + 32) = 8;
                      v403 = GetProcessHeap();
                      v404 = HeapAlloc(v403, 8u, 8u);
                      if ( v404 )
                      {
                        *(_QWORD *)(v398 + 40) = v404;
                        *v404 = qword_180128580;
                        v1311 = (LPVOID)v398;
                        v389 = 0;
                        v390 = v1311;
                        v1311 = 0;
LABEL_507:
                        v1298 = v390;
                        v391 = GetProcessHeap();
                        HeapFree(v391, 0, (LPVOID)v1308);
                        v392 = v1311;
                        if ( v1311 )
                        {
                          v1315 = *((_QWORD *)v1311 + 1);
                          if ( v1315 )
                          {
                            v393 = GetProcessHeap();
                            HeapFree(v393, 0, (LPVOID)v1315);
                            v392 = v1311;
                            *((_QWORD *)v1311 + 1) = 0;
                          }
                          v1315 = v392[3];
                          if ( v1315 )
                          {
                            v394 = GetProcessHeap();
                            HeapFree(v394, 0, (LPVOID)v1315);
                            v392 = v1311;
                            *((_QWORD *)v1311 + 3) = 0;
                          }
                          v1315 = v392[5];
                          if ( v1315 )
                          {
                            v395 = GetProcessHeap();
                            HeapFree(v395, 0, (LPVOID)v1315);
                            *((_QWORD *)v1311 + 5) = 0;
                          }
                          v396 = GetProcessHeap();
                          HeapFree(v396, 0, v1311);
                          v397 = (unsigned int *)v1298;
                        }
                        else
                        {
                          v397 = (unsigned int *)v1298;
                        }
                        v337 = v389 | 0x10000000;
                        if ( v337 < 0 )
                          goto LABEL_536;
                        v410 = *v397;
                        LODWORD(Size) = 0;
                        LODWORD(v1309) = 4;
                        v411 = RtlUIntAdd(4, v410, &v1309);
                        if ( v411 < 0 )
                          goto LABEL_587;
                        v411 = RtlUIntAdd((unsigned int)v1309, v412, &v1309);
                        if ( v411 < 0 )
                          goto LABEL_587;
                        v414 = *(unsigned int *)(v413 + 16);
                        v1326 = v413 + 16;
                        v411 = RtlUIntAdd((unsigned int)v1309, v414, &v1309);
                        if ( v411 < 0 )
                          goto LABEL_587;
                        v411 = RtlUIntAdd((unsigned int)v1309, v415, &v1309);
                        if ( v411 < 0 )
                          goto LABEL_587;
                        v417 = *(unsigned int *)(v416 + 32);
                        pcchLength = v416 + 32;
                        v411 = RtlUIntAdd((unsigned int)v1309, v417, &v1309);
                        if ( v411 < 0 )
                          goto LABEL_587;
                        v419 = v1309;
                        v1298 = v418;
                        v420 = GetProcessHeap();
                        v1311 = HeapAlloc(v420, 8u, v419);
                        v421 = v1311;
                        if ( !v1311 )
                        {
LABEL_535:
                          v337 = -805306345;
                          goto LABEL_536;
                        }
                        v445 = v1302;
                        v446 = Src;
                        *(_DWORD *)v1311 = *(_DWORD *)v1298;
                        v1302 = v445;
                        Src = v446;
                        v1299 = (SIZE_T)v421;
                        v411 = RtlULongLongAdd(v421, 4, &v1299);
                        if ( v411 < 0 )
                        {
                          v1298 = v450;
                          Src = v449;
                          v1302 = v448;
                          v1311 = v447;
                          goto LABEL_586;
                        }
                        memcpy_0((void *)v1299, v450[1], *(unsigned int *)v450);
                        v411 = RtlULongLongAdd(v1299, *(unsigned int *)v1298, &v1299);
                        if ( v411 < 0
                          || (v452 = v1299,
                              *(_DWORD *)v1299 = *(_DWORD *)v1326,
                              v411 = RtlULongLongAdd(v452, 4, &v1299),
                              v411 < 0) )
                        {
                          v1298 = v451;
                          goto LABEL_586;
                        }
                        memcpy_0((void *)v1299, v451[3], *v453);
                        v411 = RtlULongLongAdd(v1299, *(unsigned int *)v1326, &v1299);
                        if ( v411 < 0 )
                        {
                          v456 = v1298;
                        }
                        else
                        {
                          v454 = v1299;
                          *(_DWORD *)v1299 = *(_DWORD *)pcchLength;
                          v411 = RtlULongLongAdd(v454, 4, &v1299);
                          v456 = v1298;
                          if ( v411 >= 0 )
                          {
                            memcpy_0((void *)v1299, *((const void **)v1298 + 5), *v455);
                            v411 = RtlULongLongAdd(v1299, *(unsigned int *)pcchLength, &v1299);
                            if ( v411 >= 0 )
                            {
                              lpMem = v1311;
                              LODWORD(Size) = v1309;
                              goto LABEL_587;
                            }
LABEL_586:
                            v457 = GetProcessHeap();
                            HeapFree(v457, 0, v1311);
LABEL_587:
                            v337 = v411 | 0x10000000;
                            if ( v337 >= 0 )
                            {
                              v1340 = 8;
                              v458 = RtlUIntAdd(8, 20, &v1340);
                              v337 = v458 | 0x10000000;
                              if ( v458 >= 0 )
                              {
                                v459 = (v1340 + 7) & 0xFFFFFFF8;
                                if ( (unsigned int)v459 < v1340 )
                                {
                                  v337 = -1073741675;
                                  goto LABEL_536;
                                }
                                v1347 = (v1340 + 7) & 0xFFFFFFF8;
                                v337 = RtlUIntAdd(v459, 8, &v1347);
                                if ( v337 >= 0 )
                                {
                                  v1325 = v22;
                                  v1327 = v311;
                                  v1302 = v460;
                                  Src = v461;
                                  v1298 = v462;
                                  LODWORD(v1322) = 0;
                                  v1319 = v316;
                                  if ( !v316 )
                                    goto LABEL_600;
                                  v1298 = v462;
                                  Src = v461;
                                  v1302 = v460;
                                  v1327 = v311;
                                  v1325 = v22;
                                  if ( (unsigned int)v1312 <= 1 )
                                    goto LABEL_600;
                                  v463 = (SIZE_T)v316;
                                  LODWORD(v1297) = 0;
                                  v1310 = (SIZE_T)v316;
                                  v464 = 4;
                                  do
                                  {
                                    v337 = RtlULongLongAdd(v463, v464, &v1310);
                                    if ( v337 < 0 )
                                      goto LABEL_536;
                                    v337 = RtlULongLongAdd(v1310, v465, &v1310);
                                    if ( v337 < 0 )
                                      goto LABEL_536;
                                    v463 = v1310;
                                    LODWORD(v1297) = v1297 + 1;
                                  }
                                  while ( !(_DWORD)v1297 );
                                  v337 = RtlULongLongAdd(v1310, v464, &v1310);
                                  if ( v337 >= 0 )
                                  {
                                    if ( (unsigned int)v1312 <= 2 )
                                    {
LABEL_600:
                                      v337 = -1073741811;
                                      goto LABEL_536;
                                    }
                                    v469 = (SIZE_T)v316;
                                    v1310 = (SIZE_T)v316;
                                    do
                                    {
                                      v337 = RtlULongLongAdd(v469, 4, &v1310);
                                      if ( v337 < 0 )
                                        goto LABEL_536;
                                      v337 = RtlULongLongAdd(v1310, v470, &v1310);
                                      if ( v337 < 0 )
                                        goto LABEL_536;
                                      v469 = v1310;
                                    }
                                    while ( (unsigned int)(v471 + 1) < 2 );
                                    v337 = RtlULongLongAdd(v1310, 4, &v1310);
                                    if ( v337 >= 0 )
                                    {
                                      LODWORD(v1309) = 4;
                                      LODWORD(v1322) = 0;
                                      v337 = RtlUIntAdd(4, v1347, &v1309);
                                      if ( v337 >= 0 )
                                      {
                                        v337 = RtlUIntAdd((unsigned int)v1309, v472, &v1309);
                                        if ( v337 >= 0 )
                                        {
                                          v337 = RtlUIntAdd((unsigned int)v1309, v473, &v1309);
                                          if ( v337 >= 0 )
                                          {
                                            v337 = RtlUIntAdd((unsigned int)v1309, (unsigned int)(v474 + 4), &v1309);
                                            if ( v337 >= 0 )
                                            {
                                              v337 = RtlUIntAdd((unsigned int)v1309, v475, &v1309);
                                              if ( v337 >= 0 )
                                              {
                                                LODWORD(v1322) = v1309;
                                                if ( (unsigned int)v1309 > 0x400000 )
                                                {
                                                  v337 = -2147418113;
                                                  goto LABEL_536;
                                                }
                                                v466 = v1309;
                                                v467 = GetProcessHeap();
                                                v1307 = HeapAlloc(v467, 8u, v466);
                                                v468 = v1307;
                                                if ( !v1307 )
                                                {
                                                  v337 = -805306345;
                                                  v1307 = 0;
                                                  goto LABEL_536;
                                                }
                                                hModule = 0;
                                                v1364 = 0;
                                                v1365 = 0;
                                                if ( !lpMem )
                                                {
                                                  v337 = -2147024809;
LABEL_626:
                                                  v1307 = v468;
                                                  goto LABEL_536;
                                                }
                                                *(_QWORD *)((char *)&v1365 + 4) = (unsigned int)v1322;
                                                *(_QWORD *)&v1364 = lpMem;
                                                LODWORD(v1365) = Size;
                                                *((_QWORD *)&v1364 + 1) = v1307;
                                                if ( GetModuleHandleExW(1u, L"ntdll.dll", &hModule)
                                                  && (v477 = GetProcAddress(hModule, "NtQuerySystemInformation")) != 0 )
                                                {
                                                  v478 = ((__int64 (__fastcall *)(__int64, __int128 *))v477)(
                                                           134,
                                                           &v1364);
                                                  v337 = v478 | 0x10000000;
                                                  if ( v478 >= 0 )
                                                  {
                                                    v479 = DWORD1(v1365);
                                                    goto LABEL_634;
                                                  }
                                                }
                                                else
                                                {
                                                  v476 = GetLastError();
                                                  v337 = v476;
                                                  if ( v476 > 0 )
                                                    v337 = (unsigned __int16)v476 | 0x80070000;
                                                  if ( v337 >= 0 )
                                                  {
                                                    v337 = -2147467259;
                                                    goto LABEL_625;
                                                  }
                                                }
                                                if ( v337 == -805306333 )
                                                {
                                                  v337 = -2147024774;
                                                  goto LABEL_536;
                                                }
                                                if ( v337 >= 0 )
                                                {
                                                  v479 = v1322;
LABEL_634:
                                                  v468 = v1307;
                                                  v1311 = v1307;
                                                  LODWORD(v1308) = 0;
                                                  if ( v479 < 4 )
                                                  {
LABEL_635:
                                                    v337 = -805306306;
                                                    goto LABEL_626;
                                                  }
                                                  LODWORD(Size) = *(_DWORD *)v1307;
                                                  v480 = RtlULongLongAdd(v1307, 4, &v1311);
                                                  if ( v480 >= 0 )
                                                  {
                                                    v480 = RtlUIntAdd(0, 4, &v1308);
                                                    if ( v480 < 0 )
                                                    {
LABEL_688:
                                                      v1307 = v468;
                                                      goto LABEL_689;
                                                    }
                                                    if ( v482 - (int)v1308 < (unsigned int)v483 )
                                                      goto LABEL_635;
                                                    v1326 = (SIZE_T)v1311;
                                                    v1315 = v483;
                                                    v480 = RtlULongLongAdd(v1311, (unsigned int)v483, &v1311);
                                                    if ( v480 >= 0 )
                                                    {
                                                      v480 = RtlUIntAdd((unsigned int)v1308, v484, &v1308);
                                                      if ( v480 >= 0 )
                                                      {
                                                        if ( (unsigned int)(v485 - v1308) < 4 )
                                                          goto LABEL_635;
                                                        LODWORD(v1297) = *(_DWORD *)v1311;
                                                        v480 = RtlULongLongAdd(v1311, 4, &v1311);
                                                        if ( v480 >= 0 )
                                                        {
                                                          v480 = RtlUIntAdd((unsigned int)v1308, 4, &v1308);
                                                          if ( v480 >= 0 )
                                                          {
                                                            if ( v486 - (int)v1308 < (unsigned int)v487 )
                                                              goto LABEL_635;
                                                            v1318 = v1311;
                                                            pcchLength = v487;
                                                            v480 = RtlULongLongAdd(v1311, (unsigned int)v487, &v1311);
                                                            if ( v480 >= 0 )
                                                            {
                                                              v480 = RtlUIntAdd((unsigned int)v1308, v488, &v1308);
                                                              if ( v480 >= 0 )
                                                              {
                                                                if ( (unsigned int)(v489 - v1308) < 4 )
                                                                  goto LABEL_635;
                                                                LODWORD(v1322) = *(_DWORD *)v1311;
                                                                v480 = RtlULongLongAdd(v1311, 4, &v1311);
                                                                if ( v480 >= 0 )
                                                                {
                                                                  v480 = RtlUIntAdd((unsigned int)v1308, 4, &v1308);
                                                                  if ( v480 >= 0 )
                                                                  {
                                                                    if ( v490 - (int)v1308 < v491 )
                                                                      goto LABEL_635;
                                                                    v480 = RtlUIntAdd((unsigned int)v1308, v491, &v1308);
                                                                    if ( v480 >= 0 )
                                                                    {
                                                                      if ( v492 != (_DWORD)v1308 )
                                                                        goto LABEL_635;
                                                                      v494 = (unsigned int)Size;
                                                                      if ( (unsigned int)(Size + v493 + v1297) + 12LL != v492 )
                                                                        goto LABEL_635;
                                                                      v495 = GetProcessHeap();
                                                                      v1299 = (SIZE_T)HeapAlloc(v495, 8u, 0x30u);
                                                                      v496 = v1299;
                                                                      if ( !v1299 )
                                                                      {
                                                                        v1303 = 0;
                                                                        goto LABEL_535;
                                                                      }
                                                                      v1325 = v22;
                                                                      v1327 = v311;
                                                                      v1319 = v316;
                                                                      v1310 = 0;
                                                                      if ( v1326 )
                                                                      {
                                                                        *(_DWORD *)v1299 = v494;
                                                                        v497 = GetProcessHeap();
                                                                        v498 = HeapAlloc(v497, 8u, v494);
                                                                        if ( !v498 )
                                                                        {
LABEL_667:
                                                                          v505 = v1299;
                                                                          v480 = -1073741801;
                                                                          v1315 = *(_QWORD *)(v1299 + 8);
                                                                          if ( v1315 )
                                                                          {
                                                                            v506 = GetProcessHeap();
                                                                            HeapFree(v506, 0, (LPVOID)v1315);
                                                                            v505 = v1299;
                                                                            *(_QWORD *)(v1299 + 8) = 0;
                                                                          }
                                                                          v1315 = *(_QWORD *)(v505 + 24);
                                                                          if ( v1315 )
                                                                          {
                                                                            v507 = GetProcessHeap();
                                                                            HeapFree(v507, 0, (LPVOID)v1315);
                                                                            v505 = v1299;
                                                                            *(_QWORD *)(v1299 + 24) = 0;
                                                                          }
                                                                          v1315 = *(_QWORD *)(v505 + 40);
                                                                          if ( v1315 )
                                                                          {
                                                                            v508 = GetProcessHeap();
                                                                            HeapFree(v508, 0, (LPVOID)v1315);
                                                                            *(_QWORD *)(v1299 + 40) = 0;
                                                                          }
                                                                          v509 = GetProcessHeap();
                                                                          HeapFree(v509, 0, (LPVOID)v1299);
                                                                          v510 = (size_t *)v1310;
                                                                          goto LABEL_677;
                                                                        }
                                                                        *(_QWORD *)(v1299 + 8) = v498;
                                                                        v480 = 0;
                                                                        memcpy_0(v498, (const void *)v1326, v1315);
                                                                        v496 = v1299;
                                                                      }
                                                                      else
                                                                      {
                                                                        *(_DWORD *)v1299 = 0;
                                                                        v480 = 0;
                                                                        *(_QWORD *)(v496 + 8) = 0;
                                                                      }
                                                                      if ( v1318 )
                                                                      {
                                                                        *(_DWORD *)(v496 + 16) = v1297;
                                                                        v499 = GetProcessHeap();
                                                                        v500 = HeapAlloc(v499, 8u, pcchLength);
                                                                        if ( !v500 )
                                                                        {
LABEL_666:
                                                                          v1325 = v22;
                                                                          v1327 = v311;
                                                                          v1319 = v316;
                                                                          goto LABEL_667;
                                                                        }
                                                                        *(_QWORD *)(v1299 + 24) = v500;
                                                                        v480 = 0;
                                                                        memcpy_0(v500, v1318, pcchLength);
                                                                        v496 = v1299;
                                                                      }
                                                                      else
                                                                      {
                                                                        *(_DWORD *)(v496 + 16) = 0;
                                                                        *(_QWORD *)(v496 + 24) = 0;
                                                                      }
                                                                      if ( v1311 )
                                                                      {
                                                                        v501 = (unsigned int)v1322;
                                                                        *(_DWORD *)(v496 + 32) = v1322;
                                                                        v502 = v501;
                                                                        v1315 = v501;
                                                                        v503 = GetProcessHeap();
                                                                        v504 = HeapAlloc(v503, 8u, v502);
                                                                        if ( !v504 )
                                                                          goto LABEL_666;
                                                                        *(_QWORD *)(v1299 + 40) = v504;
                                                                        v480 = 0;
                                                                        memcpy_0(v504, v1311, v1315);
                                                                        v496 = v1299;
                                                                      }
                                                                      else
                                                                      {
                                                                        *(_DWORD *)(v496 + 32) = 0;
                                                                        *(_QWORD *)(v496 + 40) = 0;
                                                                      }
                                                                      v510 = (size_t *)v496;
                                                                      v1310 = v496;
                                                                      v1319 = v316;
                                                                      v1327 = v311;
                                                                      v1325 = v22;
LABEL_677:
                                                                      if ( v480 < 0 )
                                                                      {
                                                                        v481 = 0;
                                                                        v1303 = 0;
                                                                        if ( v510 )
                                                                        {
                                                                          v1315 = v510[1];
                                                                          if ( v1315 )
                                                                          {
                                                                            v511 = GetProcessHeap();
                                                                            HeapFree(v511, 0, (LPVOID)v1315);
                                                                            v510 = (size_t *)v1310;
                                                                            *(_QWORD *)(v1310 + 8) = 0;
                                                                          }
                                                                          v1315 = v510[3];
                                                                          if ( v1315 )
                                                                          {
                                                                            v512 = GetProcessHeap();
                                                                            HeapFree(v512, 0, (LPVOID)v1315);
                                                                            v510 = (size_t *)v1310;
                                                                            *(_QWORD *)(v1310 + 24) = 0;
                                                                          }
                                                                          v1315 = v510[5];
                                                                          if ( v1315 )
                                                                          {
                                                                            v513 = GetProcessHeap();
                                                                            HeapFree(v513, 0, (LPVOID)v1315);
                                                                            *(_QWORD *)(v1310 + 40) = 0;
                                                                          }
                                                                          v514 = GetProcessHeap();
                                                                          HeapFree(v514, 0, (LPVOID)v1310);
                                                                          v481 = 0;
                                                                          v1303 = 0;
                                                                        }
                                                                      }
                                                                      else
                                                                      {
                                                                        v481 = (unsigned int *)v510;
                                                                        v1303 = v510;
                                                                      }
LABEL_689:
                                                                      v337 = v480 | 0x10000000;
                                                                      if ( v337 < 0 )
                                                                        goto LABEL_536;
                                                                      if ( !v481
                                                                        || (pcchLength = *((_QWORD *)v481 + 1)) == 0
                                                                        || !*v481 )
                                                                      {
                                                                        v337 = -805306355;
                                                                        goto LABEL_536;
                                                                      }
                                                                      v515 = *v481 - 8LL;
                                                                      v1318 = (void *)v515;
                                                                      v1313 = MemoryAlloc(v515);
                                                                      if ( !v1313 )
                                                                        goto LABEL_721;
                                                                      v516 = 0;
                                                                      v1310 = pcchLength;
                                                                      uBytes_4 = 0;
                                                                      v1299 = 0x7F1137FAB69605ELL;
                                                                      v1326 = v515 & 7;
                                                                      v1311 = v1313;
                                                                      if ( (v515 & 7) != 0 )
                                                                      {
                                                                        LODWORD(v1322) = 0;
                                                                        LODWORD(v1308) = 0;
                                                                        LODWORD(v1297) = 0;
                                                                        v517 = 0;
                                                                        v518 = 0;
                                                                        v519 = 0;
                                                                        v520 = (unsigned __int8 *)v1310;
                                                                        do
                                                                        {
                                                                          v521 = *v520++;
                                                                          LODWORD(v1312) = v521;
                                                                          LODWORD(v1297) = 8 * v517;
                                                                          if ( (unsigned int)v517 >= 4 )
                                                                          {
                                                                            LODWORD(v1312) = (_DWORD)v1312 << (56 - v1297);
                                                                            v518 |= v1312;
                                                                          }
                                                                          else
                                                                          {
                                                                            LODWORD(v1312) = (_DWORD)v1312 << (24 - v1297);
                                                                            v519 |= v1312;
                                                                          }
                                                                          ++v517;
                                                                        }
                                                                        while ( v517 < (int)v1326 );
                                                                        LODWORD(v1322) = v518;
                                                                        v516 = uBytes_4;
                                                                        LODWORD(v1308) = v519;
                                                                        v515 = (unsigned __int64)v1318;
                                                                        v1310 = (SIZE_T)v520;
                                                                        v522 = v1311;
                                                                        v523 = v1326;
                                                                        v1319 = v316;
                                                                        v1327 = v311;
                                                                        v1325 = v22;
                                                                        v524 = v1308 ^ 0x92F65A5;
                                                                        LODWORD(v1297) = 0;
                                                                        v525 = v1322 ^ 0x699A899C;
                                                                        v526 = v1308 ^ 0x92F65A5;
                                                                        v527 = v1322 ^ 0x699A899C;
                                                                        if ( (_DWORD)v1326 )
                                                                        {
                                                                          v528 = v1297;
                                                                          do
                                                                          {
                                                                            v1315 = (size_t)(v522 + 1);
                                                                            if ( v528 >= 4 )
                                                                            {
                                                                              v527 = __ROR4__(v527, 24);
                                                                              v529 = v527;
                                                                            }
                                                                            else
                                                                            {
                                                                              v526 = __ROR4__(v526, 24);
                                                                              v529 = v526;
                                                                            }
                                                                            *v522 = v529;
                                                                            ++v528;
                                                                            v522 = (_BYTE *)v1315;
                                                                          }
                                                                          while ( (int)v528 < (int)v523 );
                                                                          v1311 = (LPVOID)v1315;
                                                                        }
                                                                        if ( v523 <= 4 )
                                                                        {
                                                                          v530 = 0;
                                                                          if ( v523 < 4 )
                                                                            v524 = v524 >> (8 * (4 - v523)) << (8 * (4 - v523));
                                                                        }
                                                                        else
                                                                        {
                                                                          v530 = v525 >> (8 * (8 - v523)) << (8 * (8 - v523));
                                                                        }
                                                                      }
                                                                      else
                                                                      {
                                                                        v530 = 0;
                                                                        LODWORD(v1308) = 0;
                                                                        v524 = 0;
                                                                        LODWORD(v1322) = -1;
                                                                      }
                                                                      if ( v515 >> 3 )
                                                                      {
                                                                        v531 = HIDWORD(v1299);
                                                                        v532 = v515 >> 3;
                                                                        v533 = (unsigned __int8 *)v1310;
                                                                        v534 = v1322;
                                                                        v535 = HIDWORD(v1299) ^ 0xAB69605E;
                                                                        v536 = v1308;
                                                                        LODWORD(v1312) = WORD2(v1299);
                                                                        LODWORD(v1309) = 24670;
                                                                        v537 = v1311;
                                                                        v1326 = 0;
                                                                        LODWORD(v1297) = HIDWORD(v1299) ^ 0xAB69605E;
                                                                        do
                                                                        {
                                                                          v538 = v533[1];
                                                                          v539 = *v533;
                                                                          v540 = v533[4];
                                                                          v533 += 8;
                                                                          v541 = *(v533 - 5)
                                                                               | ((*(v533 - 6)
                                                                                 | ((v538 | (v539 << 8)) << 8)) << 8);
                                                                          v542 = v524 ^ v541;
                                                                          v543 = *(v533 - 1)
                                                                               | ((*(v533 - 2)
                                                                                 | ((*(v533 - 3) | (v540 << 8)) << 8)) << 8);
                                                                          v544 = v530 ^ v543 ^ v524 ^ v541 ^ v535;
                                                                          v545 = v542
                                                                               ^ (__ROR4__(v544, 22)
                                                                                + v1312
                                                                                * __ROR4__(v544 + 1419157410, 27));
                                                                          v546 = v544
                                                                               ^ (WORD1(v1299)
                                                                                * __ROR4__(v531 + v545, 9)
                                                                                - __ROR4__(v545, 30));
                                                                          v547 = v545
                                                                               ^ (v1309 * (v546 - v1312) - (v546 >> 13));
                                                                          v548 = v546
                                                                               ^ (HIWORD(v1299)
                                                                                * __ROR4__(WORD1(v1299) ^ v547, 26)
                                                                                - __ROR4__(v547, 30));
                                                                          v549 = v547 ^ (v531 - (v548 ^ 0xAB69605E));
                                                                          v550 = v548
                                                                               ^ (WORD1(v1299) * (v1312 ^ v549))
                                                                               ^ __ROR4__(v549, 6);
                                                                          v551 = v549
                                                                               ^ (__ROR4__(v550, 30)
                                                                                + v1309 * __ROR4__(v531 + v550, 15));
                                                                          v552 = v550
                                                                               ^ (HIWORD(v1299)
                                                                                * __ROR4__(v551 + 1419157410, 14)
                                                                                - __ROR4__(v551, 24));
                                                                          v553 = v551
                                                                               ^ __ROR4__(v552, 10)
                                                                               ^ (v1312 * __ROR4__(
                                                                                            v552 ^ 0xAB69605E,
                                                                                            12));
                                                                          v554 = v553
                                                                               ^ (HIWORD(v1299)
                                                                                * (v1309
                                                                                 + __ROR4__(
                                                                                     ~(v552
                                                                                     ^ (v553 >> 10)
                                                                                     ^ (WORD1(v1299)
                                                                                      * (v553 ^ HIWORD(v1299)))),
                                                                                     5)));
                                                                          v555 = v552
                                                                               ^ (v553 >> 10)
                                                                               ^ (WORD1(v1299) * (v553 ^ HIWORD(v1299)))
                                                                               ^ (v554 - HIWORD(v1299))
                                                                               ^ 0xAB69605E;
                                                                          v556 = v554
                                                                               ^ ((v555 >> 2)
                                                                                + v1312
                                                                                * __ROR4__(HIWORD(v1299) ^ v555, 30));
                                                                          v557 = v555
                                                                               ^ (__ROR4__(v556, 25)
                                                                                + WORD1(v1299)
                                                                                * __ROR4__(v556 - HIDWORD(v1299), 6));
                                                                          v558 = v556
                                                                               ^ (v1309 * (v1312 ^ v557)
                                                                                + __ROR4__(v557, 9));
                                                                          v559 = v557
                                                                               ^ (__ROR4__(v558, 25)
                                                                                + HIWORD(v1299)
                                                                                * __ROR4__(WORD1(v1299) ^ v558, 27));
                                                                          v531 = HIDWORD(v1299);
                                                                          v560 = v1297 ^ v558 ^ v559;
                                                                          v561 = v559
                                                                               ^ (v1312
                                                                                * (__ROR4__(v560, 3) - WORD1(v1299)));
                                                                          v562 = v560
                                                                               ^ (v1309
                                                                                * __ROR4__(v561 - HIDWORD(v1299), 1)
                                                                                - __ROR4__(v561, 6));
                                                                          v563 = v561
                                                                               ^ (__ROR4__(v562, 18)
                                                                                + HIWORD(v1299)
                                                                                * __ROR4__(v562 - 1419157410, 29));
                                                                          v564 = v562
                                                                               ^ (v1312
                                                                                * __ROR4__(v563 - 1419157410, 17)
                                                                                - __ROR4__(v563, 14));
                                                                          v535 = v1297;
                                                                          v565 = v563
                                                                               ^ (v564 >> 3)
                                                                               ^ (WORD1(v1299) * (v1309 ^ v564));
                                                                          v530 = v534 ^ v565;
                                                                          v534 = v543;
                                                                          v524 = v536
                                                                               ^ v564
                                                                               ^ __ROR4__(v565, 30)
                                                                               ^ (v1309
                                                                                * __ROR4__(HIDWORD(v1299) ^ v565, 28));
                                                                          v536 = v541;
                                                                          v537[3] = v524;
                                                                          v537[7] = v530;
                                                                          v537[2] = __ROR4__(v524, 8);
                                                                          v537[6] = __ROR4__(v530, 8);
                                                                          v537[1] = __ROR4__(v524, 16);
                                                                          v537[5] = __ROR4__(v530, 16);
                                                                          *v537 = __ROR4__(v524, 24);
                                                                          v537[4] = __ROR4__(v530, 24);
                                                                          v537 += 8;
                                                                          ++v1326;
                                                                        }
                                                                        while ( v1326 < v532 );
                                                                        v516 = uBytes_4;
                                                                        v3 = v1301;
                                                                        v22 = v1325;
                                                                        v316 = v1319;
                                                                        v311 = v1327;
                                                                        v515 = (unsigned __int64)v1318;
                                                                      }
                                                                      for ( k = 0; k < v515; ++k )
                                                                        v516 ^= *((_BYTE *)v1313 + k);
                                                                      if ( v516 != *(_QWORD *)(v515 + pcchLength) )
                                                                      {
                                                                        MemoryFree(v1313);
LABEL_721:
                                                                        v1313 = 0;
                                                                        v337 = -805306367;
                                                                        goto LABEL_536;
                                                                      }
                                                                      LODWORD(v1312) = 0;
                                                                      v1310 = (SIZE_T)v1313;
                                                                      if ( (unsigned int)v515 < 4 )
                                                                      {
LABEL_723:
                                                                        v567 = -1073741762;
LABEL_762:
                                                                        v337 = v567 | 0x10000000;
                                                                        goto LABEL_536;
                                                                      }
                                                                      v567 = RtlULongLongAdd(v1313, 4, &v1310);
                                                                      if ( v567 >= 0 )
                                                                      {
                                                                        v567 = RtlUIntAdd(0, 4, &v1312);
                                                                        if ( v567 >= 0 )
                                                                        {
                                                                          if ( (unsigned int)((_DWORD)v1318 - v1312) < 4 )
                                                                            goto LABEL_727;
                                                                          LODWORD(v1322) = *(_DWORD *)v1310;
                                                                          v567 = RtlULongLongAdd(v1310, 4, &v1310);
                                                                          if ( v567 < 0 )
                                                                            goto LABEL_761;
                                                                          v567 = RtlUIntAdd(
                                                                                   (unsigned int)v1312,
                                                                                   4,
                                                                                   &v1312);
                                                                          if ( v567 < 0 )
                                                                            goto LABEL_761;
                                                                          if ( (int)v1318 - (int)v1312 < (unsigned int)v1322 )
                                                                          {
LABEL_727:
                                                                            v571 = v1313;
                                                                          }
                                                                          else
                                                                          {
                                                                            v567 = RtlUIntAdd(
                                                                                     (unsigned int)v1312,
                                                                                     (unsigned int)v1322,
                                                                                     &v1312);
                                                                            if ( v567 < 0 )
                                                                              goto LABEL_761;
                                                                            v571 = v1313;
                                                                            if ( (unsigned __int64)v1313
                                                                               + (unsigned int)v1318 >= (unsigned int)v1322 + v1310
                                                                              && (unsigned __int64)v1313
                                                                               + (unsigned int)v1318
                                                                               - (unsigned int)v1322
                                                                               - v1310 < 8 )
                                                                            {
                                                                              LODWORD(v1308) = *(_DWORD *)v1313;
                                                                              v1318 = 0;
                                                                              v1326 = 0;
                                                                              v1328 = 0;
                                                                              LODWORD(Size) = 0;
                                                                              if ( v1310 )
                                                                              {
                                                                                v572 = RtlULongLongAdd(
                                                                                         v1310,
                                                                                         (unsigned int)v1322,
                                                                                         &v1318);
                                                                                v1307 = v574;
                                                                                v567 = v572;
                                                                                Src = v575;
                                                                                v1302 = v576;
                                                                                if ( v572 < 0 )
                                                                                {
LABEL_749:
                                                                                  v586 = v1324;
LABEL_750:
                                                                                  if ( v567 < 0 || (_DWORD)v1308 == v586 )
                                                                                    goto LABEL_762;
                                                                                  goto LABEL_723;
                                                                                }
                                                                                v1311 = v573;
                                                                                if ( v573 < v1318 )
                                                                                {
                                                                                  while ( 1 )
                                                                                  {
                                                                                    v567 = RtlULongLongAdd(
                                                                                             v573,
                                                                                             4,
                                                                                             &v1326);
                                                                                    if ( v567 < 0 )
                                                                                      goto LABEL_749;
                                                                                    if ( v1326 > (unsigned __int64)v1318 )
                                                                                      goto LABEL_748;
                                                                                    v578 = *v577;
                                                                                    LODWORD(v1297) = 0;
                                                                                    v567 = RtlUIntAdd(4, v578, &v1297);
                                                                                    if ( v567 < 0 )
                                                                                      goto LABEL_762;
                                                                                    LODWORD(v1312) = uBytes;
                                                                                    v1299 = (SIZE_T)v1303;
                                                                                    LODWORD(v1309) = v22;
                                                                                    v580 = v316;
                                                                                    v581 = v1298;
                                                                                    v1327 = v1313;
                                                                                    pcchLength = (size_t)v311;
                                                                                    v1320 = v579;
                                                                                    v1317 = v1298;
                                                                                    v567 = RtlULongLongAdd(
                                                                                             v1311,
                                                                                             (unsigned int)v1297,
                                                                                             &v1328);
                                                                                    v1313 = v1327;
                                                                                    v1298 = v581;
                                                                                    v316 = v580;
                                                                                    v1303 = (LPVOID)v1299;
                                                                                    v22 = v1309;
                                                                                    v1307 = v583;
                                                                                    Src = v584;
                                                                                    v1302 = v582;
                                                                                    uBytes = v1312;
                                                                                    if ( v567 < 0 )
                                                                                      goto LABEL_749;
                                                                                    v573 = (void *)v1328;
                                                                                    v585 = v1318;
                                                                                    v1311 = (LPVOID)v1328;
                                                                                    v1307 = v583;
                                                                                    Src = v584;
                                                                                    v1302 = v582;
                                                                                    uBytes = v1312;
                                                                                    if ( v1328 > (unsigned __int64)v1318 )
                                                                                    {
                                                                                      v567 = -1073741811;
                                                                                      v1313 = v1327;
                                                                                      v1303 = (LPVOID)v1299;
                                                                                      v1298 = v1317;
                                                                                      goto LABEL_762;
                                                                                    }
                                                                                    LODWORD(Size) = Size + 1;
                                                                                    v1313 = v1327;
                                                                                    v1303 = (LPVOID)v1299;
                                                                                    v1298 = v1317;
                                                                                    v311 = (void *)pcchLength;
                                                                                    if ( v1328 >= (unsigned __int64)v1318 )
                                                                                    {
                                                                                      v1313 = v1327;
                                                                                      v1303 = (LPVOID)v1299;
                                                                                      v1298 = v1317;
                                                                                      v1302 = v1320;
                                                                                      v1307 = v583;
                                                                                      Src = v584;
                                                                                      uBytes = v1312;
                                                                                      goto LABEL_747;
                                                                                    }
                                                                                  }
                                                                                }
                                                                                v585 = v1318;
                                                                                v573 = v1311;
LABEL_747:
                                                                                if ( v573 != v585 )
                                                                                {
LABEL_748:
                                                                                  v567 = -1073741811;
                                                                                  goto LABEL_762;
                                                                                }
                                                                              }
                                                                              else
                                                                              {
                                                                                v567 = 0;
                                                                                v1307 = v569;
                                                                                Src = v570;
                                                                                v1302 = v568;
                                                                              }
                                                                              v587 = v1322;
                                                                              v588 = 0;
                                                                              v1328 = 0;
                                                                              if ( (_DWORD)v1322 )
                                                                              {
                                                                                v589 = GetProcessHeap();
                                                                                v1328 = (size_t)HeapAlloc(
                                                                                                  v589,
                                                                                                  8u,
                                                                                                  (unsigned int)v1322);
                                                                                v588 = (void *)v1328;
                                                                                if ( !v1328 )
                                                                                {
                                                                                  v567 = -1073741801;
                                                                                  goto LABEL_762;
                                                                                }
                                                                                v587 = v1322;
                                                                                v567 = 0;
                                                                              }
                                                                              if ( v1310 )
                                                                                memcpy_0(
                                                                                  v588,
                                                                                  (const void *)v1310,
                                                                                  v587);
                                                                              dwBytes = v1328;
                                                                              v586 = Size;
                                                                              LODWORD(v1324) = Size;
                                                                              goto LABEL_750;
                                                                            }
                                                                          }
                                                                          v567 = -1073741762;
                                                                          v1313 = v571;
                                                                        }
                                                                      }
LABEL_761:
                                                                      v1302 = v568;
                                                                      Src = v570;
                                                                      v1307 = v569;
                                                                      goto LABEL_762;
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
                                                  v481 = (unsigned int *)v1303;
                                                  goto LABEL_688;
                                                }
LABEL_625:
                                                v468 = v1307;
                                                goto LABEL_626;
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
LABEL_536:
                            if ( !Src )
                            {
LABEL_538:
                              v423 = v1298;
                              if ( v1298 )
                              {
                                v1320 = (_BYTE *)*((_QWORD *)v1298 + 1);
                                if ( v1320 )
                                {
                                  v424 = GetProcessHeap();
                                  HeapFree(v424, 0, v1320);
                                  v423 = v1298;
                                  *((_QWORD *)v1298 + 1) = 0;
                                }
                                v1320 = (_BYTE *)v423[3];
                                if ( v1320 )
                                {
                                  v425 = GetProcessHeap();
                                  HeapFree(v425, 0, v1320);
                                  v423 = v1298;
                                  *((_QWORD *)v1298 + 3) = 0;
                                }
                                v1320 = (_BYTE *)v423[5];
                                if ( v1320 )
                                {
                                  v426 = GetProcessHeap();
                                  HeapFree(v426, 0, v1320);
                                  *((_QWORD *)v1298 + 5) = 0;
                                }
                                v427 = GetProcessHeap();
                                HeapFree(v427, 0, v1298);
                              }
                              if ( lpMem )
                              {
                                v428 = GetProcessHeap();
                                HeapFree(v428, 0, lpMem);
                              }
                              if ( v1307 )
                              {
                                v429 = GetProcessHeap();
                                HeapFree(v429, 0, v1307);
                              }
                              v430 = v1303;
                              if ( v1303 )
                              {
                                v1320 = (_BYTE *)*((_QWORD *)v1303 + 1);
                                if ( v1320 )
                                {
                                  v431 = GetProcessHeap();
                                  HeapFree(v431, 0, v1320);
                                  v430 = v1303;
                                  *((_QWORD *)v1303 + 1) = 0;
                                }
                                v1320 = (_BYTE *)v430[3];
                                if ( v1320 )
                                {
                                  v432 = GetProcessHeap();
                                  HeapFree(v432, 0, v1320);
                                  v430 = v1303;
                                  *((_QWORD *)v1303 + 3) = 0;
                                }
                                v1320 = (_BYTE *)v430[5];
                                if ( v1320 )
                                {
                                  v433 = GetProcessHeap();
                                  HeapFree(v433, 0, v1320);
                                  *((_QWORD *)v1303 + 5) = 0;
                                }
                                v434 = GetProcessHeap();
                                HeapFree(v434, 0, v1303);
                              }
                              if ( v1313 )
                              {
                                v435 = GetProcessHeap();
                                HeapFree(v435, 0, v1313);
                              }
LABEL_560:
                              if ( v337 >= 0 && (_DWORD)v1324 && dwBytes )
                              {
                                v1328 = dwBytes;
                                v436 = RtlULongLongAdd(dwBytes, 4, &v1328);
                                v314 = v1302;
                                dwBytes = (SIZE_T)v438;
                                if ( v436 < 0 )
                                {
                                  v441 = uBytes;
                                }
                                else
                                {
                                  v440 = (int *)v1328;
                                  if ( !*v438 )
                                    v440 = 0;
                                  v441 = uBytes;
                                  if ( *v438 != (_DWORD)v439 )
                                    goto LABEL_770;
                                  if ( *v440 < 0 )
                                  {
                                    dwBytes = (SIZE_T)v438;
                                    goto LABEL_770;
                                  }
                                  if ( v437 > 1 )
                                  {
                                    v442 = (SIZE_T)v438;
                                    v1310 = (SIZE_T)v438;
                                    while ( (int)RtlULongLongAdd(v442, v439, &v1310) >= 0
                                         && (int)RtlULongLongAdd(v1310, v443, &v1310) >= 0 )
                                    {
                                      v442 = v1310;
                                      if ( v444 != -1 )
                                      {
                                        RtlULongLongAdd(v1310, v439, &v1310);
                                        goto LABEL_770;
                                      }
                                    }
                                    goto LABEL_770;
                                  }
                                  dwBytes = (SIZE_T)v438;
                                }
                                uBytes = v441;
                                goto LABEL_770;
                              }
LABEL_769:
                              v314 = v1302;
                              goto LABEL_770;
                            }
LABEL_537:
                            v422 = GetProcessHeap();
                            HeapFree(v422, 0, Src);
                            goto LABEL_538;
                          }
                        }
                        v1298 = v456;
                        goto LABEL_586;
                      }
                    }
                    else
                    {
                      v1299 = v398;
                    }
                  }
                  v389 = -1073741801;
                  v405 = v1299;
                  v1315 = *(_QWORD *)(v1299 + 8);
                  if ( v1315 )
                  {
                    v406 = GetProcessHeap();
                    HeapFree(v406, 0, (LPVOID)v1315);
                    v405 = v1299;
                    *(_QWORD *)(v1299 + 8) = 0;
                  }
                  v1315 = *(_QWORD *)(v405 + 24);
                  if ( v1315 )
                  {
                    v407 = GetProcessHeap();
                    HeapFree(v407, 0, (LPVOID)v1315);
                    v405 = v1299;
                    *(_QWORD *)(v1299 + 24) = 0;
                  }
                  v1315 = *(_QWORD *)(v405 + 40);
                  if ( v1315 )
                  {
                    v408 = GetProcessHeap();
                    HeapFree(v408, 0, (LPVOID)v1315);
                    *(_QWORD *)(v1299 + 40) = 0;
                  }
                  v409 = GetProcessHeap();
                  HeapFree(v409, 0, (LPVOID)v1299);
                }
                else
                {
                  v389 = -1073741801;
                }
                v390 = v1298;
                goto LABEL_507;
              }
            }
LABEL_773:
            v590 = GetProcessHeap();
            HeapFree(v590, 0, v316);
LABEL_774:
            v591 = (void *)dwBytes;
            if ( dwBytes )
            {
              v592 = GetProcessHeap();
              HeapFree(v592, 0, v591);
            }
            if ( !v311 )
              goto LABEL_778;
            goto LABEL_777;
          }
        }
        uBytes = v317;
        goto LABEL_773;
      }
LABEL_447:
      v307 = GetProcessHeap();
      HeapFree(v307, 0, v19);
      goto LABEL_448;
    }
    v35 = v34;
    v36 = GetProcessHeap();
    v37 = (char *)HeapAlloc(v36, 8u, (unsigned int)v35);
    v28 = v37;
    if ( !v37 )
    {
      v25 = Src;
      v20 = -1073741801;
      goto LABEL_446;
    }
    v38 = Src;
    if ( v37 + 4 < v37 )
    {
      v20 = -1073741675;
      goto LABEL_52;
    }
    if ( v37 + 8 > &v37[v35] )
      goto LABEL_63;
    *(_DWORD *)v37 = 4;
    v39 = 0;
    *((_DWORD *)v37 + 1) = 0;
    v40 = v37;
    Src = v38;
    do
    {
      v41 = *v40 + 4;
      if ( *v40 >= 0xFFFFFFFC )
        goto LABEL_431;
      v42 = (unsigned __int64)v40 + v41;
      if ( v42 < (unsigned __int64)v40 )
        goto LABEL_431;
      ++v39;
      v40 = (_DWORD *)((char *)v40 + v41);
    }
    while ( !v39 );
    if ( v42 + 4 < v42 )
    {
      Src = v38;
LABEL_431:
      v20 = -1073741675;
      goto LABEL_432;
    }
    v1315 = (unsigned int)v1297;
    if ( v40 + 41 > (_DWORD *)&v28[(unsigned int)v1297] )
    {
      v20 = -1073741789;
LABEL_52:
      Src = v38;
LABEL_432:
      v29 = 0;
      goto LABEL_435;
    }
    *v40 = 160;
    memcpy_0((void *)(v42 + 4), v19, 0xA0u);
    v44 = Src;
    v45 = v1315;
    if ( !Src )
    {
      v20 = -1073741811;
      goto LABEL_432;
    }
    if ( v28 )
    {
      v46 = 0;
      LODWORD(Size) = v1315;
      v47 = v28;
      do
      {
        if ( *v47 >= 0xFFFFFFFC )
          goto LABEL_431;
        v48 = (_DWORD *)((char *)v47 + (unsigned int)(*v47 + 4));
        if ( v48 < v47 )
          goto LABEL_431;
        ++v46;
        v47 = (_DWORD *)((char *)v47 + (unsigned int)(*v47 + 4));
      }
      while ( v46 < 2 );
      v1315 = (size_t)(v48 + 1);
      if ( v48 + 1 < v48 )
        goto LABEL_431;
      if ( v48 + 3 > (_DWORD *)&v28[v45] )
        goto LABEL_63;
      *v48 = 8;
      memcpy_0((void *)v1315, v44, 8u);
      v49 = 0;
      LODWORD(v1309) = Size;
      v43 = (size_t)v28;
      do
      {
        v50 = *(_DWORD *)v43 + 4;
        if ( *(_DWORD *)v43 >= 0xFFFFFFFC || v43 + v50 < v43 )
          goto LABEL_431;
        ++v49;
        v43 += v50;
      }
      while ( v49 < 3 );
      if ( v43 + 4 < v43 )
        goto LABEL_431;
      if ( v43 + 12 > (unsigned __int64)&v28[(unsigned int)Size] )
        goto LABEL_63;
      v51 = v1326;
      *(_DWORD *)v43 = 8;
      *(_QWORD *)(v43 + 4) = v51;
    }
    else
    {
      if ( (int)v1315 + 12 < (unsigned int)v1315 )
        goto LABEL_431;
      LODWORD(v1309) = v1315 + 24;
      if ( (int)v1315 + 24 < (unsigned int)(v1315 + 12) )
        goto LABEL_431;
    }
    pcchLength = 0;
    LODWORD(v1308) = 4;
    if ( StringCchLengthW(psz, v43, &pcchLength) < 0 )
    {
      v20 = -1073741762;
      goto LABEL_438;
    }
    if ( pcchLength + 1 < pcchLength )
      goto LABEL_428;
    v53 = (unsigned int)(2 * (pcchLength + 1));
    if ( !(_DWORD)v53 )
    {
      v20 = -1073741811;
LABEL_94:
      v55 = v1309;
      goto LABEL_95;
    }
    if ( v28 )
    {
      v56 = 0;
      v57 = v28;
      do
      {
        v58 = *v57 + 4;
        if ( *v57 >= 0xFFFFFFFC || (_DWORD *)((char *)v57 + v58) < v57 )
          goto LABEL_91;
        ++v56;
        v57 = (_DWORD *)((char *)v57 + v58);
      }
      while ( v56 < 4 );
      if ( v57 + 1 < v57 )
      {
LABEL_91:
        v20 = -1073741675;
        goto LABEL_94;
      }
      if ( (char *)v57 + v53 + 4 > &v28[(unsigned int)v1309] )
      {
        v20 = -1073741789;
        goto LABEL_94;
      }
      *v57 = v53;
      v20 = 0;
      memcpy_0(v57 + 1, psz, (unsigned int)v53);
      v52 = Src;
      v59 = v1308 + 1;
      v55 = v1309;
LABEL_96:
      if ( v20 < 0 )
        goto LABEL_438;
      if ( !v28 )
      {
        if ( v55 + 8 < v55 )
          goto LABEL_108;
        v60 = v59 + 1;
        ii = v55 + 16;
        LODWORD(Size) = v55 + 16;
        if ( v55 + 16 < v55 + 8 )
          goto LABEL_108;
LABEL_116:
        LODWORD(v1308) = v60 + 1;
        v1315 = __rdtsc();
        v68 = ii + 8;
        if ( v68 < 8 || (v69 = (v68 + 7) & 0xFFFFFFF8, v1310 = v69, (unsigned int)v69 < v68) )
        {
          v20 = -805306219;
          goto LABEL_438;
        }
        LODWORD(v1297) = 0;
        v1332 = (unsigned int)v69;
        v70 = GetProcessHeap();
        v71 = HeapAlloc(v70, 8u, (v68 + 7) & 0xFFFFFFF8);
        v1298 = v71;
        if ( !v71 )
        {
          v20 = -805306345;
          goto LABEL_372;
        }
        v72 = Src;
        *v71 = v1308;
        if ( v71 + 1 < v71 || (v73 = Size, v71[1] = Size, v71 + 2 < v71 + 1) )
        {
          pcchLength = (size_t)v71;
          v1298 = 0;
          LODWORD(v1310) = 0;
          v115 = GetProcessHeap();
          HeapFree(v115, 0, (LPVOID)pcchLength);
          v20 = -805306219;
          goto LABEL_372;
        }
        *(_QWORD *)((char *)v71 + v1332 - 8) = v1315;
        memcpy_0(v71 + 2, v28, v73);
        pcchLength = (size_t)v1298;
        v1299 = 0;
        v1302 = 0;
        v1307 = 0;
        v1303 = 0;
        v1313 = 0;
        v1309 = 0;
        if ( !(_DWORD)v1310
          || (dwBytes = (unsigned int)v1310 + 8LL,
              v74 = GetProcessHeap(),
              lpMem = HeapAlloc(v74, 0, dwBytes),
              (v75 = (char *)lpMem) == 0) )
        {
          v20 = -805306367;
          goto LABEL_349;
        }
        v76 = 0;
        v77 = 0;
        uBytes_4 = 0;
        do
          v76 ^= *(_BYTE *)(pcchLength + v77++);
        while ( v77 < (unsigned int)v1310 );
        uBytes_4 = v76;
        v1311 = v19;
        Src = v72;
        v1318 = v28;
        v1317 = (void *)0xC81ECB17B1B54A58LL;
        v1315 = (unsigned __int64)(unsigned int)v1310 >> 3;
        if ( v1315 )
        {
          v78 = WORD1(v1317);
          v79 = 0;
          v80 = WORD2(v1317);
          v81 = lpMem;
          v82 = v1315;
          v83 = -1;
          LODWORD(v1322) = HIDWORD(v1317) ^ 0xB1B54A58;
          pcchLength = 0;
          v84 = (unsigned __int8 *)v1298;
          LODWORD(Size) = 0;
          LODWORD(v1324) = 0;
          v85 = HIDWORD(v1317) ^ 0xB1B54A58;
          LODWORD(v1312) = WORD1(v1317);
          do
          {
            v86 = v84[1];
            v87 = *v84;
            v88 = v84[4];
            v84 += 8;
            v89 = *(v84 - 5) | ((*(v84 - 6) | ((v86 | (v87 << 8)) << 8)) << 8);
            v90 = *(v84 - 1) | ((*(v84 - 2) | ((*(v84 - 3) | (v88 << 8)) << 8)) << 8);
            v91 = v83 ^ v90;
            v92 = v79 ^ v89 ^ HIDWORD(v1317) ^ ((v83 ^ v90) - 19032);
            v93 = v91 ^ (__ROR4__(v92, 7) + v78 * __ROR4__(v92 ^ HIDWORD(v1317), 15));
            v94 = v92 ^ (v80 * __ROR4__(v93 - 1313519016, 9) - __ROR4__(v93, 10));
            v95 = v93 ^ (__ROR4__(v94, 27) + HIWORD(v1317) * __ROR4__(v80 ^ v94, 28));
            v96 = v94 ^ (HIDWORD(v1317) - (v95 ^ 0xB1B54A58));
            v97 = v95 ^ (WORD1(v1317) * (v96 - 19032) - (v96 >> 6));
            v98 = v96 ^ (19032 * (v80 ^ __ROR4__(v97, 15)));
            v99 = v97 ^ (v80 * (HIWORD(v1317) + __ROR4__(~v98, 3)));
            v100 = v98 ^ (v99 - HIDWORD(v1317) - 19032);
            v101 = v99 ^ (v1312 * (HIWORD(v1317) ^ v100)) ^ __ROR4__(v100, 10);
            v102 = v100 ^ __ROR4__(v101, 3) ^ (v80 * __ROR4__(v101 ^ 0x4A58, 26));
            v103 = v101 ^ (19032 * (__ROR4__(v102, 15) - HIWORD(v1317)));
            v104 = v102
                 ^ (19032 * (HIWORD(v1317) ^ v103))
                 ^ ((v103 ^ (v103 >> 14)) >> 1)
                 ^ (19032 * (((unsigned __int64)(v103 - v80) >> 29) | (8 * (v103 - v80))));
            v105 = v103 ^ (WORD1(v1317) * (v104 - v80) - (v104 >> 13));
            v106 = v104 ^ __ROR4__(v105, 11) ^ (v80 * __ROR4__(-1313519016 - v105, 9));
            v107 = v105 ^ (v106 - HIWORD(v1317) + 1313519016);
            v108 = v106 ^ (19032 * (v107 ^ WORD1(v1317)) - __ROR4__(v107, 7));
            v109 = v107 ^ (WORD1(v1317) * __ROR4__(HIWORD(v1317) ^ v108, 28) - __ROR4__(v108, 16));
            v110 = v108 ^ (__ROR4__(v109, 4) + v80 * __ROR4__(-1313519016 - v109, 10));
            v111 = v109 ^ __ROR4__(v110, 9) ^ (HIWORD(v1317) * __ROR4__(v110 + 1313519016, 4));
            v112 = v110 ^ (19032 * __ROR4__(v111 ^ HIDWORD(v1317), 24) - __ROR4__(v111, 30));
            v113 = v111 ^ (WORD1(v1317) * __ROR4__(HIDWORD(v1317) - v112, 11) - __ROR4__(v112, 12));
            v114 = v112 ^ (v113 >> 8) ^ (v80 * (v113 ^ WORD1(v1317)));
            v79 = Size ^ v114;
            LOBYTE(v98) = __ROR4__(Size ^ v114, 8);
            v83 = v113 ^ v1324 ^ v114 ^ v85;
            v78 = WORD1(v1317);
            v81[3] = Size ^ v114;
            v81[7] = v83;
            v81[2] = v98;
            v81[6] = __ROR4__(v83, 8);
            v81[1] = __ROR4__(v79, 16);
            v81[5] = __ROR4__(v83, 16);
            *v81 = __ROR4__(v79, 24);
            v81[4] = __ROR4__(v83, 24);
            v81 += 8;
            LODWORD(Size) = v89;
            LODWORD(v1324) = v90;
            ++pcchLength;
          }
          while ( pcchLength < v82 );
          v76 = uBytes_4;
          v3 = v1301;
          v22 = v1325;
          v28 = (char *)v1318;
          v19 = v1311;
          v72 = Src;
          v75 = (char *)lpMem;
        }
        else
        {
          Src = v72;
        }
        *(_QWORD *)&v75[(unsigned int)v1310] = v76;
        v116 = GetProcessHeap();
        v1311 = HeapAlloc(v116, 8u, 0x30u);
        if ( v1311 )
        {
          Src = v72;
          v126 = v1311;
          *(_DWORD *)v1311 = dwBytes;
          v127 = GetProcessHeap();
          v128 = HeapAlloc(v127, 8u, (unsigned int)dwBytes);
          if ( v128 )
          {
            v126[1] = v128;
            memcpy_0(v128, lpMem, (unsigned int)dwBytes);
            *((_DWORD *)v126 + 4) = 160;
            v129 = GetProcessHeap();
            v130 = HeapAlloc(v129, 8u, 0xA0u);
            if ( v130 )
            {
              v126[3] = v130;
              *v130 = xmmword_1801284E0;
              v130[1] = xmmword_1801284F0;
              v130[2] = xmmword_180128500;
              v130[3] = xmmword_180128510;
              v130[4] = xmmword_180128520;
              v130[5] = xmmword_180128530;
              v130[6] = xmmword_180128540;
              v130[7] = xmmword_180128550;
              v130[8] = xmmword_180128560;
              v130[9] = xmmword_180128570;
              *((_DWORD *)v126 + 8) = 8;
              v131 = GetProcessHeap();
              v132 = HeapAlloc(v131, 8u, 8u);
              if ( v132 )
              {
                v126[5] = v132;
                *v132 = qword_180128580;
                v1299 = (SIZE_T)v126;
                v117 = 0;
                v118 = (void *)v1299;
                v1299 = 0;
LABEL_135:
                v1302 = v118;
                v119 = GetProcessHeap();
                HeapFree(v119, 0, lpMem);
                v120 = v1299;
                if ( v1299 )
                {
                  v1315 = *(_QWORD *)(v1299 + 8);
                  if ( v1315 )
                  {
                    v121 = GetProcessHeap();
                    HeapFree(v121, 0, (LPVOID)v1315);
                    v120 = v1299;
                    *(_QWORD *)(v1299 + 8) = 0;
                  }
                  v1315 = *(_QWORD *)(v120 + 24);
                  if ( v1315 )
                  {
                    v122 = GetProcessHeap();
                    HeapFree(v122, 0, (LPVOID)v1315);
                    v120 = v1299;
                    *(_QWORD *)(v1299 + 24) = 0;
                  }
                  v1315 = *(_QWORD *)(v120 + 40);
                  if ( v1315 )
                  {
                    v123 = GetProcessHeap();
                    HeapFree(v123, 0, (LPVOID)v1315);
                    *(_QWORD *)(v1299 + 40) = 0;
                  }
                  v124 = GetProcessHeap();
                  HeapFree(v124, 0, (LPVOID)v1299);
                  v125 = v1302;
                }
                else
                {
                  v125 = v1302;
                }
                v20 = v117 | 0x10000000;
                if ( v20 < 0 )
                  goto LABEL_342;
                v138 = *v125 + 4;
                LODWORD(v1324) = 0;
                if ( v138 >= 4 )
                {
                  v139 = v138 + 4;
                  if ( v138 + 4 >= v138 )
                  {
                    v140 = v139 + v125[4];
                    pcchLength = (size_t)(v125 + 4);
                    if ( v140 >= v139 )
                    {
                      v141 = v140 + 4;
                      if ( v140 + 4 >= v140 )
                      {
                        v142 = v141 + v125[8];
                        LODWORD(Size) = v142;
                        if ( v142 >= v141 )
                        {
                          v143 = v142;
                          v144 = GetProcessHeap();
                          v145 = HeapAlloc(v144, 8u, v143);
                          v1299 = (SIZE_T)v145;
                          if ( !v145 )
                          {
                            v20 = -805306345;
LABEL_340:
                            v151 = v1298;
                            goto LABEL_345;
                          }
                          v146 = (const void **)v1302;
                          *v145 = *(_DWORD *)v1302;
                          v1315 = (size_t)(v145 + 1);
                          if ( v145 + 1 < v145 )
                          {
                            v1299 = (SIZE_T)v145;
                          }
                          else
                          {
                            memcpy_0(v145 + 1, v146[1], *(unsigned int *)v146);
                            v147 = (_DWORD *)(v1315 + *(unsigned int *)v146);
                            if ( (unsigned __int64)v147 >= v1315 )
                            {
                              v148 = (unsigned int *)pcchLength;
                              *v147 = *(_DWORD *)pcchLength;
                              v1315 = (size_t)(v147 + 1);
                              if ( v147 + 1 >= v147 )
                              {
                                memcpy_0(v147 + 1, v146[3], *v148);
                                v149 = (_DWORD *)(v1315 + *(unsigned int *)pcchLength);
                                if ( (unsigned __int64)v149 >= v1315 )
                                {
                                  *v149 = *((_DWORD *)v146 + 8);
                                  v1315 = (size_t)(v149 + 1);
                                  if ( v149 + 1 >= v149 )
                                  {
                                    memcpy_0(v149 + 1, v146[5], *((unsigned int *)v146 + 8));
                                    if ( v1315 + *((unsigned int *)v146 + 8) >= v1315 )
                                    {
                                      v150 = v1299;
                                      v151 = v1298;
                                      v1307 = (LPVOID)v1299;
                                      LODWORD(v1324) = Size;
                                      if ( !v28 || (unsigned int)v1308 <= 1 )
                                        goto LABEL_183;
                                      v153 = v28;
                                      LODWORD(Size) = 0;
                                      do
                                      {
                                        v154 = v153 + 1;
                                        if ( v153 + 1 < v153 )
                                          goto LABEL_347;
                                        v153 = (_DWORD *)((char *)v154 + (unsigned int)*v153);
                                        if ( v153 < v154 )
                                          goto LABEL_347;
                                        LODWORD(Size) = Size + 1;
                                      }
                                      while ( !(_DWORD)Size );
                                      if ( v153 + 1 < v153 )
                                        goto LABEL_347;
                                      if ( (unsigned int)v1308 <= 2 )
                                      {
LABEL_183:
                                        v20 = -1073741811;
                                        goto LABEL_345;
                                      }
                                      v155 = (unsigned int *)v28;
                                      LODWORD(Size) = 0;
                                      do
                                      {
                                        v156 = v155 + 1;
                                        if ( v155 + 1 < v155 )
                                          goto LABEL_347;
                                        v155 = (unsigned int *)((char *)v156 + *v155);
                                        v1315 = (size_t)v155;
                                        if ( v155 < v156 )
                                          goto LABEL_347;
                                        LODWORD(Size) = Size + 1;
                                        v157 = (void *)v150;
                                        v1299 = (SIZE_T)v19;
                                        v1311 = Src;
                                        v1312 = (SIZE_T)v28;
                                        v1322 = (SIZE_T)v1298;
                                        v1317 = v146;
                                        v1308 = v150;
                                      }
                                      while ( (unsigned int)Size < 2 );
                                      if ( (unsigned __int64)(v155 + 1) < v1315
                                        || *v153 >= 0xFFFFFFB8
                                        || (v158 = *v153 + 76, v158 < *v153 + 72)
                                        || (v159 = v158 + *(_DWORD *)v1315, LODWORD(Size) = v159, v159 < v158) )
                                      {
LABEL_347:
                                        v20 = -1073741675;
                                        goto LABEL_345;
                                      }
                                      if ( v159 > 0x400000 )
                                      {
                                        v1307 = v157;
                                        v20 = -2147418113;
                                        v1302 = v1317;
                                        goto LABEL_344;
                                      }
                                      v160 = v159;
                                      v161 = GetProcessHeap();
                                      v162 = HeapAlloc(v161, 8u, v160);
                                      v163 = v1317;
                                      v151 = (void *)v1322;
                                      v164 = v162;
                                      v165 = v1311;
                                      v1303 = v162;
                                      v1307 = (LPVOID)v1308;
                                      v1302 = v1317;
                                      v1298 = (LPVOID)v1322;
                                      Src = v1311;
                                      if ( !v162 )
                                      {
                                        v20 = -805306345;
                                        v1303 = 0;
                                        goto LABEL_345;
                                      }
                                      v166 = (void *)v1308;
                                      phModule = 0;
                                      v1362 = 0;
                                      v1363 = 0;
                                      if ( !v1308 )
                                      {
                                        v20 = -2147024809;
LABEL_204:
                                        v1303 = v164;
                                        v1307 = v166;
                                        v1302 = v163;
                                        Src = v165;
                                        goto LABEL_344;
                                      }
                                      *(_QWORD *)&v1362 = v1308;
                                      LODWORD(v1363) = v1324;
                                      *(_QWORD *)((char *)&v1363 + 4) = (unsigned int)Size;
                                      *((_QWORD *)&v1362 + 1) = v162;
                                      if ( GetModuleHandleExW(1u, L"ntdll.dll", &phModule)
                                        && (v168 = GetProcAddress(phModule, "NtQuerySystemInformation")) != 0 )
                                      {
                                        v169 = ((__int64 (__fastcall *)(__int64, __int128 *))v168)(134, &v1362);
                                        v20 = v169 | 0x10000000;
                                        if ( v169 >= 0 )
                                        {
                                          v170 = DWORD1(v1363);
                                          goto LABEL_212;
                                        }
                                      }
                                      else
                                      {
                                        v167 = GetLastError();
                                        v20 = v167;
                                        if ( v167 > 0 )
                                          v20 = (unsigned __int16)v167 | 0x80070000;
                                        if ( v20 >= 0 )
                                        {
                                          v20 = -2147467259;
                                          goto LABEL_203;
                                        }
                                      }
                                      v170 = Size;
                                      if ( v20 == -805306333 )
                                      {
                                        v20 = -2147024774;
LABEL_210:
                                        v151 = (void *)v1322;
                                        v1307 = (LPVOID)v1308;
                                        v1302 = v1317;
                                        v171 = v1311;
                                        goto LABEL_343;
                                      }
                                      if ( v20 >= 0 )
                                      {
LABEL_212:
                                        if ( v170 < 4 )
                                        {
                                          v20 = -805306306;
                                          goto LABEL_210;
                                        }
                                        v172 = *(unsigned int *)v1303;
                                        v173 = (char *)v1303 + 4;
                                        v1332 = (SIZE_T)v1303 + 4;
                                        if ( (char *)v1303 + 4 >= v1303 )
                                        {
                                          if ( v170 - 4 < (unsigned int)v172 )
                                          {
LABEL_216:
                                            v20 = -805306306;
                                            goto LABEL_210;
                                          }
                                          v174 = &v173[v172];
                                          v1328 = v172;
                                          lpMem = &v173[v172];
                                          if ( &v173[v172] >= v173 && (unsigned int)v172 < 0xFFFFFFFC )
                                          {
                                            if ( v170 - ((_DWORD)v172 + 4) < 4 )
                                              goto LABEL_216;
                                            v175 = *(unsigned int *)v174;
                                            v176 = v174 + 4;
                                            LODWORD(Size) = *(_DWORD *)v174;
                                            if ( v174 + 4 >= v174 )
                                            {
                                              v177 = v172 + 8;
                                              if ( (int)v172 + 8 >= (unsigned int)(v172 + 4) )
                                              {
                                                if ( v170 - v177 < (unsigned int)v175 )
                                                  goto LABEL_216;
                                                v178 = (unsigned __int64)v176 + v175;
                                                pcchLength = v175;
                                                v1315 = (size_t)v176 + v175;
                                                if ( (_DWORD *)((char *)v176 + v175) >= v176 )
                                                {
                                                  v179 = v177 + v175;
                                                  if ( v177 + (unsigned int)v175 >= v177 )
                                                  {
                                                    if ( v170 - v179 < 4 )
                                                      goto LABEL_216;
                                                    v1318 = (void *)(v178 + 4);
                                                    if ( v178 + 4 >= v178 )
                                                    {
                                                      v180 = v179 + 4;
                                                      if ( v179 + 4 >= v179 )
                                                      {
                                                        v181 = *(_DWORD *)v1315;
                                                        LODWORD(v1324) = v181;
                                                        if ( v170 - v180 < v181 )
                                                          goto LABEL_216;
                                                        if ( v180 + v181 < v180 )
                                                        {
                                                          v20 = v3;
                                                          goto LABEL_340;
                                                        }
                                                        if ( v170 != v180 + v181
                                                          || (unsigned int)v175 + (_DWORD)v172 + v181 + 12LL != v170 )
                                                        {
                                                          goto LABEL_216;
                                                        }
                                                        v182 = GetProcessHeap();
                                                        v183 = HeapAlloc(v182, 8u, 0x30u);
                                                        dwBytes = (SIZE_T)v183;
                                                        if ( !v183 )
                                                        {
                                                          v151 = (void *)v1322;
                                                          v20 = -805306345;
                                                          v19 = (_OWORD *)v1299;
                                                          v1307 = (LPVOID)v1308;
                                                          v1302 = v1317;
                                                          v171 = v1311;
                                                          goto LABEL_343;
                                                        }
                                                        v184 = (const void *)v1332;
                                                        v1310 = 0;
                                                        if ( v1332 )
                                                        {
                                                          *(_DWORD *)v183 = v172;
                                                          v185 = GetProcessHeap();
                                                          v186 = HeapAlloc(v185, 8u, v172);
                                                          if ( !v186 )
                                                          {
LABEL_245:
                                                            v187 = -1073741801;
                                                            v28 = (char *)v1312;
                                                            v19 = (_OWORD *)v1299;
                                                            v1307 = (LPVOID)v1308;
                                                            v1302 = v1317;
                                                            v1298 = (LPVOID)v1322;
                                                            Src = v1311;
                                                            v196 = dwBytes;
                                                            v1318 = (void *)v1312;
                                                            v1311 = (LPVOID)v1299;
                                                            v1315 = *(_QWORD *)(dwBytes + 8);
                                                            if ( v1315 )
                                                            {
                                                              v197 = GetProcessHeap();
                                                              HeapFree(v197, 0, (LPVOID)v1315);
                                                              v196 = dwBytes;
                                                              *(_QWORD *)(dwBytes + 8) = 0;
                                                            }
                                                            v1315 = *(_QWORD *)(v196 + 24);
                                                            if ( v1315 )
                                                            {
                                                              v198 = GetProcessHeap();
                                                              HeapFree(v198, 0, (LPVOID)v1315);
                                                              v196 = dwBytes;
                                                              *(_QWORD *)(dwBytes + 24) = 0;
                                                            }
                                                            v1315 = *(_QWORD *)(v196 + 40);
                                                            if ( v1315 )
                                                            {
                                                              v199 = GetProcessHeap();
                                                              HeapFree(v199, 0, (LPVOID)v1315);
                                                              *(_QWORD *)(dwBytes + 40) = 0;
                                                            }
                                                            v200 = GetProcessHeap();
                                                            HeapFree(v200, 0, (LPVOID)dwBytes);
                                                            v201 = (size_t *)v1310;
                                                            goto LABEL_255;
                                                          }
                                                          v183[1] = v186;
                                                          v187 = 0;
                                                          memcpy_0(v186, v184, v1328);
                                                        }
                                                        else
                                                        {
                                                          *(_DWORD *)v183 = 0;
                                                          v187 = 0;
                                                          v183[1] = 0;
                                                        }
                                                        v188 = (char *)lpMem + 4;
                                                        if ( lpMem == (LPVOID)-4LL )
                                                        {
                                                          *((_DWORD *)v183 + 4) = 0;
                                                          v183[3] = 0;
                                                        }
                                                        else
                                                        {
                                                          *((_DWORD *)v183 + 4) = Size;
                                                          v189 = GetProcessHeap();
                                                          v190 = HeapAlloc(v189, 8u, pcchLength);
                                                          if ( !v190 )
                                                          {
LABEL_244:
                                                            dwBytes = (SIZE_T)v183;
                                                            goto LABEL_245;
                                                          }
                                                          v183[3] = v190;
                                                          v187 = 0;
                                                          memcpy_0(v190, v188, pcchLength);
                                                        }
                                                        v191 = v1318;
                                                        if ( v1318 )
                                                        {
                                                          v192 = (unsigned int)v1324;
                                                          *((_DWORD *)v183 + 8) = v1324;
                                                          v193 = v192;
                                                          v1315 = v192;
                                                          v194 = GetProcessHeap();
                                                          v195 = HeapAlloc(v194, 8u, v193);
                                                          if ( !v195 )
                                                            goto LABEL_244;
                                                          v183[5] = v195;
                                                          v187 = 0;
                                                          memcpy_0(v195, v191, v1315);
                                                        }
                                                        else
                                                        {
                                                          *((_DWORD *)v183 + 8) = 0;
                                                          v183[5] = 0;
                                                        }
                                                        v201 = v183;
                                                        v28 = (char *)v1312;
                                                        v19 = (_OWORD *)v1299;
                                                        v1307 = (LPVOID)v1308;
                                                        v1302 = v1317;
                                                        v1298 = (LPVOID)v1322;
                                                        Src = v1311;
                                                        v1310 = (SIZE_T)v201;
                                                        v1318 = (void *)v1312;
                                                        v1311 = (LPVOID)v1299;
LABEL_255:
                                                        if ( v187 < 0 )
                                                        {
                                                          if ( v201 )
                                                          {
                                                            v1315 = v201[1];
                                                            if ( v1315 )
                                                            {
                                                              v202 = GetProcessHeap();
                                                              HeapFree(v202, 0, (LPVOID)v1315);
                                                              v201 = (size_t *)v1310;
                                                              *(_QWORD *)(v1310 + 8) = 0;
                                                            }
                                                            v1315 = v201[3];
                                                            if ( v1315 )
                                                            {
                                                              v203 = GetProcessHeap();
                                                              HeapFree(v203, 0, (LPVOID)v1315);
                                                              v201 = (size_t *)v1310;
                                                              *(_QWORD *)(v1310 + 24) = 0;
                                                            }
                                                            v1315 = v201[5];
                                                            if ( v1315 )
                                                            {
                                                              v204 = GetProcessHeap();
                                                              HeapFree(v204, 0, (LPVOID)v1315);
                                                              *(_QWORD *)(v1310 + 40) = 0;
                                                            }
                                                            v205 = GetProcessHeap();
                                                            HeapFree(v205, 0, (LPVOID)v1310);
                                                          }
                                                        }
                                                        else
                                                        {
                                                          v1313 = v201;
                                                        }
                                                        v20 = v187 | 0x10000000;
                                                        if ( v20 < 0 )
                                                          goto LABEL_340;
                                                        if ( !v1313
                                                          || (v1324 = *((_QWORD *)v1313 + 1)) == 0
                                                          || !*(_DWORD *)v1313 )
                                                        {
                                                          v20 = -805306355;
                                                          goto LABEL_340;
                                                        }
                                                        dwBytes = *(unsigned int *)v1313 - 8LL;
                                                        v206 = GetProcessHeap();
                                                        v207 = HeapAlloc(v206, 0, dwBytes);
                                                        v1310 = (SIZE_T)v207;
                                                        if ( !v207 )
                                                        {
LABEL_297:
                                                          v1309 = 0;
                                                          v20 = -805306367;
                                                          goto LABEL_340;
                                                        }
                                                        v208 = dwBytes;
                                                        v209 = 0;
                                                        uBytes_4 = 0;
                                                        v1299 = 0x7F1137FAB69605ELL;
                                                        lpMem = (LPVOID)v1324;
                                                        v1317 = v207;
                                                        v210 = dwBytes & 7;
                                                        if ( (dwBytes & 7) != 0 )
                                                        {
                                                          LODWORD(v1308) = 0;
                                                          LODWORD(v1322) = 0;
                                                          LODWORD(Size) = 0;
                                                          v211 = 0;
                                                          v212 = (unsigned __int8 *)v1324;
                                                          v213 = 0;
                                                          v214 = 0;
                                                          do
                                                          {
                                                            v215 = *v212++;
                                                            LODWORD(v1312) = v215;
                                                            LODWORD(Size) = 8 * v211;
                                                            if ( v211 >= 4 )
                                                            {
                                                              LODWORD(v1312) = (_DWORD)v1312 << (56 - Size);
                                                              v213 |= v1312;
                                                            }
                                                            else
                                                            {
                                                              LODWORD(v1312) = (_DWORD)v1312 << (24 - Size);
                                                              v214 |= v1312;
                                                            }
                                                            ++v211;
                                                          }
                                                          while ( (int)v211 < (int)v210 );
                                                          LODWORD(v1322) = v214;
                                                          v209 = uBytes_4;
                                                          LODWORD(v1308) = v213;
                                                          v22 = v1325;
                                                          lpMem = v212;
                                                          v208 = dwBytes;
                                                          v1318 = v28;
                                                          v1311 = v19;
                                                          LODWORD(Size) = 0;
                                                          v216 = v1308 ^ 0x699A899C;
                                                          v217 = v1322 ^ 0x92F65A5;
                                                          v218 = v1322 ^ 0x92F65A5;
                                                          v219 = v1308 ^ 0x699A899C;
                                                          if ( (dwBytes & 7) != 0 )
                                                          {
                                                            v220 = v1317;
                                                            v221 = Size;
                                                            do
                                                            {
                                                              v1315 = (size_t)(v220 + 1);
                                                              if ( v221 >= 4 )
                                                              {
                                                                v219 = __ROR4__(v219, 24);
                                                                v222 = v219;
                                                              }
                                                              else
                                                              {
                                                                v218 = __ROR4__(v218, 24);
                                                                v222 = v218;
                                                              }
                                                              *v220 = v222;
                                                              ++v221;
                                                              v220 = (_BYTE *)v1315;
                                                            }
                                                            while ( (int)v221 < (int)v210 );
                                                            v1317 = (void *)v1315;
                                                          }
                                                          if ( v210 <= 4 )
                                                          {
                                                            v223 = 0;
                                                            if ( v210 < 4 )
                                                              v217 = v217 >> (8 * (4 - v210)) << (8 * (4 - v210));
                                                          }
                                                          else
                                                          {
                                                            v223 = v216 >> (8 * (8 - v210)) << (8 * (8 - v210));
                                                          }
                                                        }
                                                        else
                                                        {
                                                          v223 = 0;
                                                          LODWORD(v1322) = 0;
                                                          v217 = 0;
                                                          LODWORD(v1308) = -1;
                                                        }
                                                        v1315 = v208 >> 3;
                                                        if ( v208 >> 3 )
                                                        {
                                                          v224 = HIDWORD(v1299);
                                                          v225 = (unsigned __int8 *)lpMem;
                                                          v226 = v1317;
                                                          v227 = v1308;
                                                          v228 = v1322;
                                                          v229 = v1315;
                                                          LODWORD(Size) = HIDWORD(v1299) ^ 0xAB69605E;
                                                          LODWORD(v1309) = WORD2(v1299);
                                                          LODWORD(v1312) = 24670;
                                                          pcchLength = 0;
                                                          do
                                                          {
                                                            v230 = v225[1];
                                                            v231 = *v225;
                                                            v232 = v225[4];
                                                            v225 += 8;
                                                            v233 = *(v225 - 5)
                                                                 | ((*(v225 - 6) | ((v230 | (v231 << 8)) << 8)) << 8);
                                                            v234 = *(v225 - 1)
                                                                 | ((*(v225 - 2) | ((*(v225 - 3) | (v232 << 8)) << 8)) << 8);
                                                            v235 = v217 ^ v233 ^ Size ^ v223 ^ v234;
                                                            v236 = v217
                                                                 ^ v233
                                                                 ^ (__ROR4__(v235, 22)
                                                                  + v1309 * __ROR4__(v235 + 1419157410, 27));
                                                            v237 = v235
                                                                 ^ (WORD1(v1299) * __ROR4__(v236 + v224, 9)
                                                                  - __ROR4__(v236, 30));
                                                            v238 = v236 ^ (v1312 * (v237 - v1309) - (v237 >> 13));
                                                            v239 = v237
                                                                 ^ (HIWORD(v1299) * __ROR4__(v238 ^ WORD1(v1299), 26)
                                                                  - __ROR4__(v238, 30));
                                                            v240 = v238 ^ (v224 - (v239 ^ 0xAB69605E));
                                                            v241 = v239
                                                                 ^ (WORD1(v1299) * (v240 ^ v1309))
                                                                 ^ __ROR4__(v240, 6);
                                                            v242 = v240
                                                                 ^ (__ROR4__(v241, 30)
                                                                  + v1312 * __ROR4__(v241 + v224, 15));
                                                            v243 = v241
                                                                 ^ (HIWORD(v1299) * __ROR4__(v242 + 1419157410, 14)
                                                                  - __ROR4__(v242, 24));
                                                            v244 = v242
                                                                 ^ __ROR4__(v243, 10)
                                                                 ^ (v1309 * __ROR4__(v243 ^ 0xAB69605E, 12));
                                                            v245 = v244
                                                                 ^ (HIWORD(v1299)
                                                                  * (v1312
                                                                   + __ROR4__(
                                                                       ~(v243
                                                                       ^ (v244 >> 10)
                                                                       ^ (WORD1(v1299) * (v244 ^ HIWORD(v1299)))),
                                                                       5)));
                                                            v246 = v243
                                                                 ^ (v244 >> 10)
                                                                 ^ (WORD1(v1299) * (v244 ^ HIWORD(v1299)))
                                                                 ^ (v245 - HIWORD(v1299))
                                                                 ^ 0xAB69605E;
                                                            v247 = v245
                                                                 ^ ((v246 >> 2)
                                                                  + v1309 * __ROR4__(HIWORD(v1299) ^ v246, 30));
                                                            v248 = v246
                                                                 ^ (__ROR4__(v247, 25)
                                                                  + WORD1(v1299) * __ROR4__(v247 - HIDWORD(v1299), 6));
                                                            v249 = v247 ^ (v1312 * (v248 ^ v1309) + __ROR4__(v248, 9));
                                                            v250 = v248
                                                                 ^ (__ROR4__(v249, 25)
                                                                  + HIWORD(v1299) * __ROR4__(WORD1(v1299) ^ v249, 27));
                                                            v224 = HIDWORD(v1299);
                                                            v251 = Size ^ v249 ^ v250;
                                                            v252 = v250 ^ (v1309 * (__ROR4__(v251, 3) - WORD1(v1299)));
                                                            v253 = v251
                                                                 ^ (v1312 * __ROR4__(v252 - HIDWORD(v1299), 1)
                                                                  - __ROR4__(v252, 6));
                                                            v254 = v252
                                                                 ^ (__ROR4__(v253, 18)
                                                                  + HIWORD(v1299) * __ROR4__(v253 - 1419157410, 29));
                                                            v255 = v253
                                                                 ^ (v1309 * __ROR4__(v254 - 1419157410, 17)
                                                                  - __ROR4__(v254, 14));
                                                            v256 = v254 ^ (v255 >> 3) ^ (WORD1(v1299) * (v255 ^ v1312));
                                                            v257 = __ROR4__(v256, 30);
                                                            v223 = v227 ^ v256;
                                                            v227 = v234;
                                                            v217 = v228
                                                                 ^ v255
                                                                 ^ v257
                                                                 ^ (v1312
                                                                  * __ROR4__(
                                                                      HIDWORD(v1299)
                                                                    ^ v254
                                                                    ^ (v255 >> 3)
                                                                    ^ (WORD1(v1299) * (v255 ^ v1312)),
                                                                      28));
                                                            v228 = v233;
                                                            v226[3] = v217;
                                                            v226[7] = v223;
                                                            v226[2] = __ROR4__(v217, 8);
                                                            v226[6] = __ROR4__(v223, 8);
                                                            v226[1] = __ROR4__(v217, 16);
                                                            v226[5] = __ROR4__(v223, 16);
                                                            *v226 = __ROR4__(v217, 24);
                                                            v226[4] = __ROR4__(v223, 24);
                                                            v226 += 8;
                                                            ++pcchLength;
                                                          }
                                                          while ( pcchLength < v229 );
                                                          v209 = uBytes_4;
                                                          v3 = v1301;
                                                          v22 = v1325;
                                                          v28 = (char *)v1318;
                                                          v19 = v1311;
                                                          v208 = dwBytes;
                                                        }
                                                        v258 = (_DWORD *)v1310;
                                                        for ( m = 0; m < v208; ++m )
                                                          v209 ^= *(_BYTE *)(m + v1310);
                                                        if ( v209 != *(_QWORD *)(v208 + v1324) )
                                                        {
                                                          MemoryFree((void *)v1310);
                                                          goto LABEL_297;
                                                        }
                                                        v151 = v1298;
                                                        if ( (unsigned int)dwBytes < 4 )
                                                        {
                                                          v260 = v1310;
                                                          v261 = -1073741762;
LABEL_300:
                                                          v1309 = v260;
LABEL_330:
                                                          v20 = v261 | 0x10000000;
                                                          goto LABEL_345;
                                                        }
                                                        v1309 = v1310;
                                                        v1315 = v1310 + 4;
                                                        if ( v1310 + 4 < v1310 )
                                                          goto LABEL_338;
                                                        if ( (unsigned int)(dwBytes - 4) < 4 )
                                                        {
LABEL_303:
                                                          v262 = v1310;
                                                          v261 = -1073741762;
LABEL_304:
                                                          v1309 = v262;
                                                          goto LABEL_330;
                                                        }
                                                        v1318 = (void *)(v1310 + 8);
                                                        if ( v1310 + 8 < v1315 )
                                                          goto LABEL_338;
                                                        if ( (unsigned int)(dwBytes - 8) < *(_DWORD *)(v1310 + 4) )
                                                          goto LABEL_303;
                                                        if ( *(_DWORD *)(v1310 + 4) >= 0xFFFFFFF8 )
                                                        {
LABEL_338:
                                                          v261 = -1073741675;
                                                        }
                                                        else
                                                        {
                                                          v1299 = *(unsigned int *)(v1310 + 4);
                                                          v1310 = (SIZE_T)v1318 + v1299;
                                                          v1315 = (unsigned int)dwBytes;
                                                          if ( (char *)v258 + (unsigned int)dwBytes >= (char *)v1318 + v1299
                                                            && v1315 + (char *)v258 - v1299 - (_BYTE *)v1318 < 8 )
                                                          {
                                                            LODWORD(Size) = 0;
                                                            if ( v1318 )
                                                            {
                                                              if ( v1310 < (unsigned __int64)v1318 )
                                                              {
                                                                v260 = v1309;
                                                                v261 = -1073741675;
                                                                goto LABEL_300;
                                                              }
                                                              v263 = v1318;
                                                              if ( v1310 > (unsigned __int64)v1318 )
                                                              {
                                                                while ( v263 + 1 >= v263 )
                                                                {
                                                                  if ( (unsigned __int64)(v263 + 1) > v1310 )
                                                                    goto LABEL_323;
                                                                  v264 = *v263 + 4;
                                                                  if ( *v263 >= 0xFFFFFFFC )
                                                                    break;
                                                                  v265 = (SIZE_T)v263 + v264;
                                                                  if ( v265 < (unsigned __int64)v263 )
                                                                    break;
                                                                  if ( v265 > v1310 )
                                                                    goto LABEL_323;
                                                                  LODWORD(Size) = Size + 1;
                                                                  v263 = (_DWORD *)((char *)v263 + v264);
                                                                  if ( v265 >= v1310 )
                                                                    goto LABEL_322;
                                                                }
                                                                v261 = -1073741675;
                                                                goto LABEL_330;
                                                              }
                                                              v1309 = (SIZE_T)v258;
LABEL_322:
                                                              if ( v263 != (_DWORD *)v1310 )
                                                              {
LABEL_323:
                                                                v261 = -1073741811;
                                                                goto LABEL_330;
                                                              }
                                                            }
                                                            else
                                                            {
                                                              v1309 = (SIZE_T)v258;
                                                            }
                                                            v266 = v258[1] == 0;
                                                            LODWORD(v1324) = *v258;
                                                            if ( v266 )
                                                            {
                                                              v268 = 0;
                                                            }
                                                            else
                                                            {
                                                              v267 = GetProcessHeap();
                                                              v268 = HeapAlloc(v267, 8u, v1299);
                                                              if ( !v268 )
                                                              {
                                                                v261 = -1073741801;
LABEL_329:
                                                                v151 = v1298;
                                                                goto LABEL_330;
                                                              }
                                                            }
                                                            v261 = 0;
                                                            v1319 = v268;
                                                            if ( v1318 )
                                                              memcpy_0(v268, v1318, v1299);
                                                            LODWORD(v1297) = Size;
                                                            if ( (_DWORD)v1324 != (_DWORD)Size )
                                                              v261 = -1073741762;
                                                            goto LABEL_329;
                                                          }
                                                          v261 = -1073741762;
                                                        }
                                                        v262 = v1309;
                                                        goto LABEL_304;
                                                      }
                                                    }
                                                  }
                                                }
                                              }
                                            }
                                          }
                                        }
                                        v20 = v3;
LABEL_342:
                                        v171 = Src;
                                        v151 = v1298;
LABEL_343:
                                        Src = v171;
LABEL_344:
                                        v1298 = v151;
LABEL_345:
                                        if ( !v151 )
                                        {
LABEL_350:
                                          v270 = v1302;
                                          if ( v1302 )
                                          {
                                            v1315 = *((_QWORD *)v1302 + 1);
                                            if ( v1315 )
                                            {
                                              v271 = GetProcessHeap();
                                              HeapFree(v271, 0, (LPVOID)v1315);
                                              v270 = v1302;
                                              *((_QWORD *)v1302 + 1) = 0;
                                            }
                                            v1315 = v270[3];
                                            if ( v1315 )
                                            {
                                              v272 = GetProcessHeap();
                                              HeapFree(v272, 0, (LPVOID)v1315);
                                              v270 = v1302;
                                              *((_QWORD *)v1302 + 3) = 0;
                                            }
                                            v1315 = v270[5];
                                            if ( v1315 )
                                            {
                                              v273 = GetProcessHeap();
                                              HeapFree(v273, 0, (LPVOID)v1315);
                                              *((_QWORD *)v1302 + 5) = 0;
                                            }
                                            v274 = GetProcessHeap();
                                            HeapFree(v274, 0, v1302);
                                          }
                                          if ( v1307 )
                                          {
                                            v275 = GetProcessHeap();
                                            HeapFree(v275, 0, v1307);
                                          }
                                          if ( v1303 )
                                          {
                                            v276 = GetProcessHeap();
                                            HeapFree(v276, 0, v1303);
                                          }
                                          v277 = v1313;
                                          if ( v1313 )
                                          {
                                            v1315 = *((_QWORD *)v1313 + 1);
                                            if ( v1315 )
                                            {
                                              v278 = GetProcessHeap();
                                              HeapFree(v278, 0, (LPVOID)v1315);
                                              v277 = v1313;
                                              *((_QWORD *)v1313 + 1) = 0;
                                            }
                                            v1315 = v277[3];
                                            if ( v1315 )
                                            {
                                              v279 = GetProcessHeap();
                                              HeapFree(v279, 0, (LPVOID)v1315);
                                              v277 = v1313;
                                              *((_QWORD *)v1313 + 3) = 0;
                                            }
                                            v1315 = v277[5];
                                            if ( v1315 )
                                            {
                                              v280 = GetProcessHeap();
                                              HeapFree(v280, 0, (LPVOID)v1315);
                                              *((_QWORD *)v1313 + 5) = 0;
                                            }
                                            v281 = GetProcessHeap();
                                            HeapFree(v281, 0, v1313);
                                          }
                                          if ( v1309 )
                                          {
                                            v282 = GetProcessHeap();
                                            HeapFree(v282, 0, (LPVOID)v1309);
                                          }
LABEL_372:
                                          if ( v20 < 0 )
                                            goto LABEL_438;
                                          if ( !(_DWORD)v1297 )
                                            goto LABEL_374;
                                          if ( !v1319 )
                                          {
                                            v20 = -1073741811;
                                            goto LABEL_438;
                                          }
                                          if ( (char *)v1319 + 4 < v1319 )
                                          {
                                            v20 = -1073741675;
                                            goto LABEL_438;
                                          }
                                          v283 = 0;
                                          if ( *(_DWORD *)v1319 )
                                            v283 = (int *)((char *)v1319 + 4);
                                          if ( *(_DWORD *)v1319 != 4 )
                                          {
                                            v20 = -1073741789;
                                            goto LABEL_438;
                                          }
                                          v20 = *v283;
                                          if ( v20 == -805306333 )
                                          {
                                            v29 = -2147024774;
                                          }
                                          else
                                          {
                                            v29 = v20;
                                            if ( v20 != -2147024774 && v20 < 0 )
                                              goto LABEL_438;
                                          }
                                          if ( (_DWORD)v1297 != 6 )
                                          {
LABEL_374:
                                            v20 = -1073425151;
                                            goto LABEL_438;
                                          }
                                          v284 = v1319;
                                          v285 = 0;
                                          while ( 1 )
                                          {
                                            v286 = v284 + 1;
                                            if ( v284 + 1 < v284 )
                                              break;
                                            v284 = (_DWORD *)((char *)v286 + (unsigned int)*v284);
                                            if ( v284 < v286 )
                                              break;
                                            if ( ++v285 )
                                            {
                                              if ( v284 + 1 < v284 )
                                                break;
                                              v287 = 0;
                                              if ( *v284 )
                                                v287 = (__int64 *)(v284 + 1);
                                              if ( *v284 != 8 )
                                              {
LABEL_422:
                                                v20 = -1073741789;
                                                goto LABEL_438;
                                              }
                                              v288 = *v287;
                                              v289 = v1319;
                                              v290 = 0;
                                              while ( 1 )
                                              {
                                                v291 = v289 + 1;
                                                if ( v289 + 1 < v289 )
                                                  goto LABEL_428;
                                                v289 = (_DWORD *)((char *)v291 + (unsigned int)*v289);
                                                if ( v289 < v291 )
                                                  goto LABEL_428;
                                                if ( (unsigned int)++v290 >= 2 )
                                                {
                                                  if ( v289 + 1 < v289 )
                                                    goto LABEL_428;
                                                  if ( *v289 == 4 )
                                                  {
                                                    v292 = (unsigned int *)v1319;
                                                    for ( n = 0; n < 3; ++n )
                                                    {
                                                      v294 = v292 + 1;
                                                      if ( v292 + 1 < v292 )
                                                        goto LABEL_425;
                                                      v292 = (unsigned int *)((char *)v294 + *v292);
                                                      if ( v292 < v294 )
                                                        goto LABEL_425;
                                                    }
                                                    if ( v292 + 1 < v292 )
                                                    {
LABEL_425:
                                                      v20 = -1073741675;
                                                      goto LABEL_435;
                                                    }
                                                    v295 = v1319;
                                                    v296 = 0;
                                                    while ( 1 )
                                                    {
                                                      v297 = v295 + 1;
                                                      if ( v295 + 1 < v295 )
                                                        goto LABEL_428;
                                                      v295 = (_DWORD *)((char *)v297 + (unsigned int)*v295);
                                                      if ( v295 < v297 )
                                                        goto LABEL_428;
                                                      if ( (unsigned int)++v296 >= 4 )
                                                      {
                                                        if ( v295 + 1 < v295 )
                                                          goto LABEL_428;
                                                        v298 = 0;
                                                        if ( *v295 )
                                                          v298 = v295 + 1;
                                                        if ( *v295 == 4 )
                                                        {
                                                          v299 = *v298;
                                                          v300 = v1319;
                                                          v301 = 0;
                                                          while ( 1 )
                                                          {
                                                            v302 = v300 + 1;
                                                            if ( v300 + 1 < v300 )
                                                              goto LABEL_428;
                                                            v300 = (_DWORD *)((char *)v302 + (unsigned int)*v300);
                                                            if ( v300 < v302 )
                                                              goto LABEL_428;
                                                            if ( (unsigned int)++v301 >= 5 )
                                                            {
                                                              if ( v300 + 1 < v300 )
                                                                goto LABEL_428;
                                                              v303 = 0;
                                                              if ( *v300 )
                                                                v303 = v300 + 1;
                                                              if ( *v300 != 4 )
                                                                goto LABEL_422;
                                                              if ( v1326 != v288 )
                                                                goto LABEL_374;
                                                              v22 = *v303;
                                                              v20 = 0;
                                                              uBytes = v299;
                                                              goto LABEL_436;
                                                            }
                                                          }
                                                        }
                                                        goto LABEL_422;
                                                      }
                                                    }
                                                  }
                                                  goto LABEL_422;
                                                }
                                              }
                                            }
                                          }
LABEL_428:
                                          v20 = -1073741675;
                                          goto LABEL_438;
                                        }
LABEL_349:
                                        v269 = GetProcessHeap();
                                        HeapFree(v269, 0, v1298);
                                        goto LABEL_350;
                                      }
LABEL_203:
                                      v165 = Src;
                                      v151 = v1298;
                                      v163 = v1302;
                                      v164 = v1303;
                                      v166 = v1307;
                                      goto LABEL_204;
                                    }
                                  }
                                }
                              }
                            }
                          }
                          v152 = GetProcessHeap();
                          HeapFree(v152, 0, (LPVOID)v1299);
                        }
                      }
                    }
                  }
                }
                v20 = -805306219;
                v151 = v1298;
                goto LABEL_345;
              }
            }
            else
            {
              v1311 = v126;
            }
          }
          v117 = -1073741801;
          v133 = v1311;
          v1315 = *((_QWORD *)v1311 + 1);
          if ( v1315 )
          {
            v134 = GetProcessHeap();
            HeapFree(v134, 0, (LPVOID)v1315);
            v133 = v1311;
            *((_QWORD *)v1311 + 1) = 0;
          }
          v1315 = v133[3];
          if ( v1315 )
          {
            v135 = GetProcessHeap();
            HeapFree(v135, 0, (LPVOID)v1315);
            v133 = v1311;
            *((_QWORD *)v1311 + 3) = 0;
          }
          v1315 = v133[5];
          if ( v1315 )
          {
            v136 = GetProcessHeap();
            HeapFree(v136, 0, (LPVOID)v1315);
            *((_QWORD *)v1311 + 5) = 0;
          }
          v137 = GetProcessHeap();
          HeapFree(v137, 0, v1311);
        }
        else
        {
          v117 = -1073741801;
        }
        v118 = v1302;
        goto LABEL_135;
      }
      v61 = 0;
      v62 = v55;
      v63 = v28;
      if ( v59 )
      {
        while ( *v63 < 0xFFFFFFFC && (_DWORD *)((char *)v63 + (unsigned int)(*v63 + 4)) >= v63 )
        {
          ++v61;
          v63 = (_DWORD *)((char *)v63 + (unsigned int)(*v63 + 4));
          if ( v61 >= v59 )
            goto LABEL_104;
        }
        goto LABEL_108;
      }
LABEL_104:
      if ( v63 + 1 < v63 )
        goto LABEL_108;
      if ( v63 + 2 > (_DWORD *)&v28[v55] )
        goto LABEL_63;
      v60 = v59 + 1;
      *v63 = 4;
      Src = v52;
      v63[1] = 0;
      v65 = 0;
      Src = v52;
      LODWORD(Size) = v55;
      v66 = v28;
      for ( ii = v55; v65 < v60; v66 = (_DWORD *)((char *)v66 + v67) )
      {
        v67 = *v66 + 4;
        if ( *v66 >= 0xFFFFFFFC || (_DWORD *)((char *)v66 + v67) < v66 )
          goto LABEL_108;
        ++v65;
      }
      if ( v66 + 1 < v66 )
      {
LABEL_108:
        v20 = -1073741675;
        goto LABEL_432;
      }
      if ( v66 + 2 <= (_DWORD *)&v28[v62] )
      {
        *v66 = 4;
        v66[1] = 0;
        goto LABEL_116;
      }
LABEL_63:
      v20 = -1073741789;
      goto LABEL_432;
    }
    v54 = v53 + 4;
    v55 = v1309;
    if ( v54 >= 4 )
    {
      if ( v54 + (unsigned int)v1309 >= (unsigned int)v1309 )
      {
        v55 = v54 + v1309;
        LODWORD(v1308) = 5;
        v20 = 0;
LABEL_95:
        v59 = v1308;
        goto LABEL_96;
      }
      v55 = -1;
    }
    v20 = -1073741675;
    goto LABEL_95;
  }
LABEL_1661:
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  if ( v4 )
    operator delete(v4);
  if ( v5 )
    LocalFree(v5);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18009ecb8  mov     [rsp-8+arg_8], rbx
0x18009ecbd  push    rbp
0x18009ecbe  push    rsi
0x18009ecbf  push    rdi
0x18009ecc0  push    r12
0x18009ecc2  push    r13
0x18009ecc4  push    r14
0x18009ecc6  push    r15
0x18009ecc8  lea     rbp, [rsp-2D0h]
0x18009ecd0  sub     rsp, 3D0h
0x18009ecd7  xor     eax, eax
0x18009ecd9  mov     [rbp+300h+var_D8], r8
0x18009ece0  mov     [rbp+300h+StringUuid], rax
0x18009ece7  mov     r15d, 80070057h
0x18009eced  mov     [rbp+300h+lpMem], rax
0x18009ecf1  mov     [rbp+300h+pcchLength], rax
0x18009ecf5  mov     [rbp+300h+var_278], rax
0x18009ecfc  test    r8, r8
0x18009ecff  jz      loc_1800A9301
0x18009ed05  lea     rdx, [rbp+300h+StringUuid]; StringUuid
0x18009ed0c  mov     [r8], ax
0x18009ed10  mov     r13d, eax
0x18009ed13  mov     edi, eax
0x18009ed15  call    cs:__imp_UuidToStringW
0x18009ed1b  test    eax, eax
0x18009ed1d  jnz     loc_1800A92CF
0x18009ed23  mov     r11d, 7FFFFFFFh
0x18009ed29  lea     r14, aTerminalservic_5; "TerminalServices-RemoteConnectionManage"...
0x18009ed30  mov     edx, r11d; unsigned __int64
0x18009ed33  lea     r8, [rbp+300h+lpMem]; unsigned __int64 *
0x18009ed37  mov     rcx, r14; unsigned __int16 *
0x18009ed3a  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18009ed3f  mov     r15d, eax
0x18009ed42  test    eax, eax
0x18009ed44  jns     loc_18009EDE3
0x18009ed4a  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "SUCCEEDED(hr)")
0x18009ed4f  mov     ecx, cs:dword_180128170
0x18009ed55  cmp     ecx, 3
0x18009ed58  jbe     loc_1800A92CF
0x18009ed5e  lea     rax, aGetinitialprog; "GetInitialProgram"
0x18009ed65  mov     [rbp+300h+var_C0], r14
0x18009ed6c  mov     [rbp+300h+var_B8], rax
0x18009ed73  lea     rdx, word_18011448A
0x18009ed7a  lea     rax, aCslqueryGetini_1; "CSLQuery::GetInitialProgram - StringCch"...
0x18009ed81  mov     [rbp+300h+var_228], r15d
0x18009ed88  mov     [rbp+300h+var_B0], rax
0x18009ed8f  lea     rax, aWarningHresult; "Warning HResult failed"
0x18009ed96  mov     [rbp+300h+var_150], rax
0x18009ed9d  lea     rax, [rbp+300h+var_C0]
0x18009eda4  mov     [rsp+400h+var_3C0], rax
0x18009eda9  lea     rax, [rbp+300h+var_B8]
0x18009edb0  mov     [rsp+400h+var_3C8], rax
0x18009edb5  lea     rax, [rbp+300h+var_228]
0x18009edbc  mov     [rsp+400h+var_3D0], rax
0x18009edc1  lea     rax, [rbp+300h+var_B0]
0x18009edc8  mov     [rsp+400h+var_3D8], rax
0x18009edcd  lea     rax, [rbp+300h+var_150]
0x18009edd4  mov     [rsp+400h+var_3E0], rax
0x18009edd9  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18009edde  jmp     loc_1800A92CF
0x18009ede3  mov     rcx, [rbp+300h+StringUuid]; unsigned __int16 *
0x18009edea  lea     r8, [rbp+300h+pcchLength]; unsigned __int64 *
0x18009edee  mov     rdx, r11; unsigned __int64
0x18009edf1  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18009edf6  mov     r15d, eax
0x18009edf9  test    eax, eax
0x18009edfb  jns     loc_18009EE97
0x18009ee01  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "SUCCEEDED(hr)")
0x18009ee06  mov     eax, cs:dword_180128170
0x18009ee0c  cmp     eax, 3
0x18009ee0f  jbe     loc_1800A92CF
0x18009ee15  mov     rax, [rbp+300h+StringUuid]
0x18009ee1c  lea     rdx, qword_1801147D8
0x18009ee23  mov     [rbp+300h+var_148], rax
0x18009ee2a  lea     rax, aGetinitialprog; "GetInitialProgram"
0x18009ee31  mov     [rbp+300h+var_140], rax
0x18009ee38  lea     rax, aCslqueryGetini_1; "CSLQuery::GetInitialProgram - StringCch"...
0x18009ee3f  mov     [rbp+300h+var_138], rax
0x18009ee46  lea     rax, aWarningHresult; "Warning HResult failed"
0x18009ee4d  mov     [rbp+300h+var_108], rax
0x18009ee54  lea     rax, [rbp+300h+var_148]
0x18009ee5b  mov     [rsp+400h+var_3C0], rax
0x18009ee60  lea     rax, [rbp+300h+var_140]
0x18009ee67  mov     [rsp+400h+var_3C8], rax
0x18009ee6c  lea     rax, [rbp+300h+var_224]
0x18009ee73  mov     [rsp+400h+var_3D0], rax
0x18009ee78  lea     rax, [rbp+300h+var_138]
0x18009ee7f  mov     [rsp+400h+var_3D8], rax
0x18009ee84  lea     rax, [rbp+300h+var_108]
0x18009ee8b  mov     [rbp+300h+var_224], r15d
0x18009ee92  jmp     loc_18009EDD4
0x18009ee97  lea     rsi, aInitialprogram; "-InitialProgram"
0x18009ee9e  mov     rdx, r11; unsigned __int64
0x18009eea1  mov     rcx, rsi; unsigned __int16 *
0x18009eea4  lea     r8, [rbp+300h+var_278]; unsigned __int64 *
0x18009eeab  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18009eeb0  mov     r15d, eax
0x18009eeb3  test    eax, eax
0x18009eeb5  jns     loc_18009EF4A
0x18009eebb  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "SUCCEEDED(hr)")
0x18009eec0  mov     eax, cs:dword_180128170
0x18009eec6  cmp     eax, 3
0x18009eec9  jbe     loc_1800A92CF
0x18009eecf  lea     rax, aGetinitialprog; "GetInitialProgram"
0x18009eed6  mov     [rbp+300h+var_130], rsi
0x18009eedd  mov     [rbp+300h+var_128], rax
0x18009eee4  lea     rdx, byte_180113F31
0x18009eeeb  lea     rax, aCslqueryGetini_1; "CSLQuery::GetInitialProgram - StringCch"...
0x18009eef2  mov     [rbp+300h+var_220], r15d
0x18009eef9  mov     [rbp+300h+var_120], rax
0x18009ef00  lea     rax, aWarningHresult; "Warning HResult failed"
0x18009ef07  mov     [rbp+300h+var_118], rax
0x18009ef0e  lea     rax, [rbp+300h+var_130]
0x18009ef15  mov     [rsp+400h+var_3C0], rax
0x18009ef1a  lea     rax, [rbp+300h+var_128]
0x18009ef21  mov     [rsp+400h+var_3C8], rax
0x18009ef26  lea     rax, [rbp+300h+var_220]
0x18009ef2d  mov     [rsp+400h+var_3D0], rax
0x18009ef32  lea     rax, [rbp+300h+var_120]
0x18009ef39  mov     [rsp+400h+var_3D8], rax
0x18009ef3e  lea     rax, [rbp+300h+var_118]
0x18009ef45  jmp     loc_18009EDD4
0x18009ef4a  mov     rdx, [rbp+300h+var_278]
0x18009ef51  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18009ef58  add     rdx, [rbp+300h+pcchLength]
0x18009ef5c  mov     eax, 2
0x18009ef61  mov     rbx, [rbp+300h+lpMem]
0x18009ef65  add     rbx, 3
0x18009ef69  add     rbx, rdx
0x18009ef6c  mul     rbx
0x18009ef6f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009ef76  cmovb   rax, rcx
0x18009ef7a  mov     rcx, rax; unsigned __int64
0x18009ef7d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18009ef82  mov     [rbp+300h+psz], rax
0x18009ef89  mov     r13, rax
0x18009ef8c  test    rax, rax
0x18009ef8f  jnz     short loc_18009EF9C
0x18009ef91  mov     r15d, 8007000Eh
0x18009ef97  jmp     loc_1800A92CF
0x18009ef9c  mov     rax, [rbp+300h+StringUuid]
0x18009efa3  lea     r8, aWsWsWs; "%ws%ws%ws"
0x18009efaa  mov     [rsp+400h+var_3D8], rsi
0x18009efaf  mov     r9, r14
0x18009efb2  mov     rdx, rbx; unsigned __int64
0x18009efb5  mov     [rsp+400h+var_3E0], rax
0x18009efba  mov     rcx, r13; unsigned __int16 *
0x18009efbd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009efc2  mov     r15d, eax
0x18009efc5  xor     eax, eax
0x18009efc7  test    r15d, r15d
0x18009efca  jns     loc_18009F05E
0x18009efd0  mov     eax, cs:dword_180128170
0x18009efd6  cmp     eax, 3
0x18009efd9  jbe     loc_1800A92CF
0x18009efdf  lea     rax, aGetinitialprog; "GetInitialProgram"
0x18009efe6  mov     [rbp+300h+var_200], r15d
0x18009efed  mov     [rbp+300h+var_110], rax
0x18009eff4  lea     rdx, word_18011414E
0x18009effb  lea     rax, aCslqueryGetini_0; "CSLQuery::GetInitialProgram - StringCch"...
0x18009f002  xor     r9d, r9d
0x18009f005  mov     [rbp+300h+var_D0], rax
0x18009f00c  lea     rcx, dword_180128170
0x18009f013  lea     rax, aWarningHresult; "Warning HResult failed"
0x18009f01a  xor     r8d, r8d
0x18009f01d  mov     [rbp+300h+var_100], rax
0x18009f024  lea     rax, [rbp+300h+var_110]
0x18009f02b  mov     [rsp+400h+var_3C8], rax
0x18009f030  lea     rax, [rbp+300h+var_200]
0x18009f037  mov     [rsp+400h+var_3D0], rax
0x18009f03c  lea     rax, [rbp+300h+var_D0]
0x18009f043  mov     [rsp+400h+var_3D8], rax
0x18009f048  lea     rax, [rbp+300h+var_100]
0x18009f04f  mov     [rsp+400h+var_3E0], rax
0x18009f054  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18009f059  jmp     loc_1800A92CF
0x18009f05e  mov     [rbp+300h+var_230], rax
0x18009f065  mov     [rbp+300h+var_254], eax
0x18009f06b  mov     [rbp+300h+var_278], rax
0x18009f072  call    cs:__imp_GetProcessHeap
0x18009f078  mov     ebx, 8
0x18009f07d  mov     r8d, 0A0h; dwBytes
0x18009f083  mov     rcx, rax; hHeap
0x18009f086  mov     edx, ebx; dwFlags
0x18009f088  call    cs:__imp_HeapAlloc
0x18009f08e  mov     r14, rax
0x18009f091  test    rax, rax
0x18009f094  jnz     short loc_18009F0D6
0x18009f096  mov     esi, 0C0000017h
0x18009f09b  mov     r15d, esi
0x18009f09e  mov     ebx, [rbp+300h+var_254]
0x18009f0a4  lea     rcx, [rbp+300h+var_278]
0x18009f0ab  call    ?Reset@?$SP@EV?$SP_HLOCAL@E@@@@QEAAXXZ; SP<uchar,SP_HLOCAL<uchar>>::Reset(void)
0x18009f0b0  test    r15d, r15d
0x18009f0b3  jns     loc_1800A91AD
0x18009f0b9  xor     ebx, ebx
0x18009f0bb  cmp     r15d, 0D0000034h
0x18009f0c2  jnz     loc_1800A917B
0x18009f0c8  mov     r15d, 0C004F012h
0x18009f0ce  mov     rdi, rbx
0x18009f0d1  jmp     loc_1800A91CA
0x18009f0d6  movups  xmm0, cs:xmmword_180128590
0x18009f0dd  xor     eax, eax
0x18009f0df  xor     r12d, r12d
0x18009f0e2  mov     dword ptr [rbp+300h+uBytes], eax
0x18009f0e5  movups  xmmword ptr [r14], xmm0
0x18009f0e9  mov     [rbp+300h+var_2D8], r12d
0x18009f0ed  movups  xmm1, cs:xmmword_1801285A0
0x18009f0f4  movups  xmmword ptr [r14+10h], xmm1
0x18009f0f9  movups  xmm0, cs:xmmword_1801285B0
0x18009f100  movups  xmmword ptr [r14+20h], xmm0
0x18009f105  movups  xmm1, cs:xmmword_1801285C0
0x18009f10c  movups  xmmword ptr [r14+30h], xmm1
0x18009f111  movups  xmm0, cs:xmmword_1801285D0
0x18009f118  movups  xmmword ptr [r14+40h], xmm0
0x18009f11d  movups  xmm1, cs:xmmword_1801285E0
0x18009f124  movups  xmmword ptr [r14+50h], xmm1
0x18009f129  movups  xmm0, cs:xmmword_1801285F0
0x18009f130  movups  xmmword ptr [r14+60h], xmm0
0x18009f135  movups  xmm1, cs:xmmword_180128600
0x18009f13c  movups  xmmword ptr [r14+70h], xmm1
0x18009f141  movups  xmm0, cs:xmmword_180128610
0x18009f148  movups  xmmword ptr [r14+80h], xmm0
0x18009f150  movups  xmm1, cs:xmmword_180128620
0x18009f157  movups  xmmword ptr [r14+90h], xmm1
0x18009f15f  call    cs:__imp_GetProcessHeap
0x18009f165  mov     r8, rbx; dwBytes
0x18009f168  mov     edx, ebx; dwFlags
0x18009f16a  mov     rcx, rax; hHeap
0x18009f16d  call    cs:__imp_HeapAlloc
0x18009f173  mov     esi, 0C4h
0x18009f178  mov     [rbp+300h+var_2A0], 0FFFFFFFFh
0x18009f17f  mov     [rsp+400h+Src], rax
0x18009f184  mov     r15d, 0D0000095h
0x18009f18a  mov     [rbp+300h+var_2C8], rsi
0x18009f18e  mov     r11, rax
0x18009f191  mov     [rsp+400h+var_390], r15d
0x18009f196  mov     rbx, 0C81ECB17B1B54A58h
0x18009f1a0  mov     [rbp+300h+var_320], 0D0000017h
0x18009f1a7  mov     rdi, 7F1137FAB69605Eh
0x18009f1b1  test    rax, rax
0x18009f1b4  jnz     short loc_18009F1C3
0x18009f1b6  mov     esi, 0C0000017h
0x18009f1bb  xor     r13d, r13d
0x18009f1be  jmp     loc_1800A14D8
0x18009f1c3  mov     rax, cs:qword_1801284D0
0x18009f1ca  mov     [r11], rax
0x18009f1cd  rdtsc
0x18009f1cf  shl     rdx, 20h; cchMax
0x18009f1d3  or      rax, rdx
0x18009f1d6  mov     [rbp+300h+var_2D0], rax
0x18009f1da  lea     r8, [rbp+300h+pcchLength]; pcchLength
0x18009f1de  mov     [rbp+300h+pcchLength], r12
0x18009f1e2  mov     rcx, r13; psz
0x18009f1e5  call    StringCchLengthW
0x18009f1ea  test    eax, eax
0x18009f1ec  jns     short loc_18009F1F8
0x18009f1ee  mov     esi, 0C000003Eh
0x18009f1f3  jmp     loc_1800A14D3
0x18009f1f8  mov     rax, [rbp+300h+pcchLength]
0x18009f1fc  lea     eax, ds:6[rax*2]
0x18009f203  cmp     eax, 4
0x18009f206  jb      loc_1800A14C9
0x18009f20c  add     eax, esi
0x18009f20e  mov     [rbp+300h+var_308], r12
0x18009f212  or      r10d, 0FFFFFFFFh
0x18009f216  xor     r13d, r13d
0x18009f219  xor     r9d, r9d
0x18009f21c  mov     ecx, r10d
0x18009f21f  cmp     eax, esi
0x18009f221  mov     r8d, 0C0000095h
0x18009f227  cmovnb  ecx, eax
0x18009f22a  sbb     esi, esi
0x18009f22c  and     esi, r8d
0x18009f22f  add     esi, 10000000h
0x18009f235  cmp     eax, 0C4h
0x18009f23a  jb      loc_1800A146D
0x18009f240  lea     eax, [rcx+8]
0x18009f243  mov     edx, r10d
0x18009f246  cmp     eax, ecx
0x18009f248  cmovnb  edx, eax
0x18009f24b  sbb     esi, esi
0x18009f24d  and     esi, r8d
0x18009f250  add     esi, 10000000h
0x18009f256  cmp     eax, ecx
0x18009f258  jb      loc_1800A146D
0x18009f25e  lea     eax, [rdx+8]
0x18009f261  mov     ecx, r10d
0x18009f264  cmp     eax, edx
0x18009f266  cmovnb  ecx, eax
0x18009f269  sbb     esi, esi
0x18009f26b  and     esi, r8d
0x18009f26e  mov     dword ptr [rsp+400h+var_3B0], ecx
0x18009f272  add     esi, 10000000h
0x18009f278  cmp     eax, edx
0x18009f27a  jb      loc_1800A146D
0x18009f280  mov     esi, ecx
0x18009f282  call    cs:__imp_GetProcessHeap
0x18009f288  mov     r8d, esi; dwBytes
0x18009f28b  lea     edx, [r13+8]; dwFlags
  ... truncated ...
```
