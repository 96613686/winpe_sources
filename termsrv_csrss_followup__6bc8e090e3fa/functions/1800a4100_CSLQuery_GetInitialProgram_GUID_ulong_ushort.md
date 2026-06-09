# CSLQuery::GetInitialProgram(_GUID,ulong,ushort *)

- ea: `0x1800a4100`
- end: `0x1800af142`
- name: `?GetInitialProgram@CSLQuery@@SAJU_GUID@@KPEAG@Z`
- size: `45122`
- prototype: `__int64 __fastcall(struct _GUID *__struct_ptr, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180031950`

## callees

- `0x18000256c`
- `0x180005314`
- `0x180005ce0`
- `0x180005e04`
- `0x180012d10`
- `0x180015044`
- `0x18001637c`
- `0x180016558`
- `0x180026068`
- `0x1800269e0`
- `0x180026a10`
- `0x180026ad8`
- `0x180029574`
- `0x180029dc0`
- `0x180033f44`
- `0x18003444c`
- `0x1800a4100`
- `0x1800ca374`
- `0x1800caedc`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800a5804`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800a824b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800ab43b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800add95`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800a5804`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800a824b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800ab43b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800add95`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a5874`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a829a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ab48d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800addd8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a5874`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a829a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ab48d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800addd8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a44dc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a45cd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a46fe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a4b5a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a4c0f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5053`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a51ba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5207`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a52c5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a54a4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a574c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5a1f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5a90`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5aee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5b57`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5e29`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a6571`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a6c0b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a6cad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a6d03`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a7022`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a754b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a76b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a7702`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a77c1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a79fc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a80b1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a84dd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a855f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a85d5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a866b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a92b6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a9485`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a9536`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a9756`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a9959`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a99f8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aa1b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aa818`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aa99b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aa9f8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aaaa5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aacd9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ab275`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ab6f2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ab769`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ab7d7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ab84a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ac316`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ac89d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ace49`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ad4bf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ad502`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ad567`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ad61b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ad936`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800adbfb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ae013`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ae085`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ae0f7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ae169`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aebec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a44dc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a45cd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a46fe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a4b5a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a4c0f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5053`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a51ba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5207`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a52c5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a54a4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a574c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5a1f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5a90`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5aee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5b57`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5e29`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a6571`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a6c0b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a6cad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a6d03`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a7022`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a754b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a76b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a7702`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a77c1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a79fc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a80b1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a84dd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a855f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a85d5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a866b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a92b6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a9485`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a9536`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a9756`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a9959`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a99f8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aa1b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aa818`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aa99b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aa9f8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aaaa5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aacd9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ab275`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ab6f2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ab769`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ab7d7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ab84a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ac316`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ac89d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ace49`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ad4bf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ad502`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ad567`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ad61b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ad936`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800adbfb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ae013`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ae085`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ae0f7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ae169`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aebec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a44c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a45b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a46e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a4b43`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a4bfa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a4feb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a503b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a507b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a50b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a50f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a512d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a515b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a519f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a51ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a52ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a5319`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a5353`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a538d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a53ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a548d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a55c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a5735`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a5a07`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a5a79`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a5ad6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a5b40`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a5bc2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a5bfc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a5c36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a5c63`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a5d17`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a5d51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a5d8b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a5db8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a5e14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a6558`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a6630`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a666d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a66a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a66e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a6711`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a673a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a6762`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a679d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a67d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a6811`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a683e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a6866`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a6b25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a6b4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a6b9b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a6bc0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a6bf1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a6c96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a6ce9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a700a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a70fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a7533`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a7574`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a75af`

## string_xrefs

- `0x1800a57d8`: `ntdll.dll`
- `0x1800a821e`: `ntdll.dll`
- `0x1800ab41d`: `ntdll.dll`
- `0x1800add77`: `ntdll.dll`
- `0x1800a4177`: `TerminalServices-RemoteConnectionManager-`

## pseudocode

```c
__int64 __fastcall CSLQuery::GetInitialProgram(struct _GUID *a1, __int64 a2, unsigned __int16 *a3)
{
  int v3; // r15d
  wchar_t *v4; // r13
  unsigned __int16 *v5; // rdi
  unsigned __int64 v6; // r11
  int v7; // r8d
  int v8; // r9d
  unsigned __int64 v9; // r11
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
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
  SIZE_T m; // rax
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
  SIZE_T v345; // r9
  unsigned __int8 v346; // al
  unsigned __int64 v347; // rdx
  void *v348; // rsi
  _BYTE *v349; // r14
  unsigned __int8 *v350; // r12
  int v351; // r15d
  SIZE_T v352; // rdi
  int v353; // r9d
  int v354; // r8d
  unsigned int v355; // eax
  int v356; // ecx
  int v357; // esi
  int v358; // r11d
  int v359; // esi
  int v360; // r11d
  int v361; // r8d
  int v362; // r10d
  int v363; // r8d
  int v364; // r10d
  int v365; // r9d
  int v366; // r8d
  unsigned int v367; // edx
  int v368; // r9d
  int v369; // ecx
  int v370; // edx
  int v371; // r8d
  int v372; // r9d
  int v373; // edx
  unsigned int v374; // r8d
  unsigned int v375; // r9d
  int v376; // edx
  int v377; // r8d
  int v378; // r9d
  int v379; // edx
  int v380; // r8d
  int v381; // r10d
  int v382; // edx
  int v383; // r9d
  unsigned int v384; // r8d
  int v385; // edx
  int v386; // r10d
  HANDLE v387; // rax
  int v388; // esi
  void *v389; // rax
  HANDLE v390; // rax
  _QWORD *v391; // rax
  HANDLE v392; // rax
  HANDLE v393; // rax
  HANDLE v394; // rax
  HANDLE v395; // rax
  unsigned int *v396; // r11
  SIZE_T v397; // rsi
  HANDLE v398; // rax
  void *v399; // rax
  HANDLE v400; // rax
  _OWORD *v401; // rax
  HANDLE v402; // rax
  _QWORD *v403; // rax
  SIZE_T v404; // rax
  HANDLE v405; // rax
  HANDLE v406; // rax
  HANDLE v407; // rax
  HANDLE v408; // rax
  __int64 v409; // rdx
  int v410; // esi
  unsigned int v411; // r9d
  __int64 v412; // r11
  __int64 v413; // rdx
  unsigned int v414; // r9d
  __int64 v415; // r11
  __int64 v416; // rdx
  void *v417; // r11
  unsigned int v418; // esi
  HANDLE v419; // rax
  LPVOID v420; // rcx
  HANDLE v421; // rax
  _QWORD *v422; // rax
  HANDLE v423; // rax
  HANDLE v424; // rax
  HANDLE v425; // rax
  HANDLE v426; // rax
  HANDLE v427; // rax
  HANDLE v428; // rax
  _QWORD *v429; // rax
  HANDLE v430; // rax
  HANDLE v431; // rax
  HANDLE v432; // rax
  HANDLE v433; // rax
  HANDLE v434; // rax
  int v435; // eax
  unsigned int v436; // r9d
  _DWORD *v437; // r10
  __int64 v438; // r11
  int *v439; // rcx
  unsigned int v440; // eax
  SIZE_T v441; // rcx
  unsigned int v442; // r10d
  int v443; // r9d
  void *v444; // r9
  void *v445; // r10
  void *v446; // rcx
  void *v447; // r9
  void *v448; // r10
  const void **v449; // r11
  const void **v450; // r9
  SIZE_T v451; // rcx
  unsigned int *v452; // r10
  SIZE_T v453; // rcx
  unsigned int *v454; // r9
  void *v455; // rax
  HANDLE v456; // rax
  int v457; // eax
  __int64 v458; // rcx
  void *v459; // r9
  void *v460; // r10
  void *v461; // r11
  SIZE_T v462; // rcx
  __int64 v463; // r10
  unsigned int v464; // r9d
  unsigned int v465; // esi
  HANDLE v466; // rax
  void *v467; // r9
  SIZE_T v468; // rcx
  unsigned int v469; // r10d
  int v470; // r9d
  unsigned int v471; // ecx
  unsigned int v472; // r11d
  int v473; // r9d
  unsigned int v474; // r10d
  signed int v475; // eax
  FARPROC v476; // rax
  int v477; // eax
  unsigned int v478; // r10d
  int v479; // esi
  unsigned int *v480; // rcx
  int v481; // r10d
  size_t v482; // r11
  unsigned int v483; // r11d
  int v484; // r10d
  int v485; // r10d
  size_t v486; // r11
  unsigned int v487; // r11d
  int v488; // r10d
  int v489; // r10d
  unsigned int v490; // r11d
  int v491; // r10d
  int v492; // r11d
  SIZE_T v493; // rsi
  HANDLE v494; // rax
  SIZE_T v495; // rcx
  HANDLE v496; // rax
  void *v497; // rcx
  HANDLE v498; // rax
  void *v499; // rcx
  size_t v500; // rax
  unsigned int v501; // esi
  HANDLE v502; // rax
  void *v503; // rcx
  SIZE_T v504; // rax
  HANDLE v505; // rax
  HANDLE v506; // rax
  HANDLE v507; // rax
  HANDLE v508; // rax
  size_t *v509; // rdx
  HANDLE v510; // rax
  HANDLE v511; // rax
  HANDLE v512; // rax
  HANDLE v513; // rax
  unsigned __int64 v514; // rsi
  unsigned __int8 v515; // al
  int v516; // edi
  int v517; // eax
  int v518; // esi
  unsigned __int8 *v519; // rbx
  int v520; // ecx
  _BYTE *v521; // r11
  unsigned int v522; // edx
  unsigned int v523; // r8d
  unsigned int v524; // r9d
  int v525; // ecx
  int v526; // r10d
  unsigned int v527; // edi
  char v528; // bl
  int v529; // r9d
  int v530; // r11d
  SIZE_T v531; // r12
  unsigned __int8 *v532; // rbx
  int v533; // r15d
  int v534; // r10d
  int v535; // r13d
  _BYTE *v536; // rax
  int v537; // ecx
  int v538; // r14d
  int v539; // esi
  int v540; // r14d
  int v541; // edx
  int v542; // esi
  int v543; // r8d
  int v544; // r9d
  unsigned int v545; // edx
  int v546; // r8d
  int v547; // r9d
  unsigned int v548; // edx
  int v549; // r8d
  int v550; // r10d
  int v551; // r11d
  unsigned int v552; // r9d
  int v553; // r8d
  unsigned int v554; // r9d
  int v555; // r10d
  int v556; // r11d
  int v557; // edx
  int v558; // r8d
  int v559; // r9d
  int v560; // edx
  int v561; // r10d
  int v562; // r8d
  unsigned int v563; // edx
  int v564; // r9d
  int v565; // r8d
  int v566; // ecx
  unsigned __int64 k; // rcx
  int v568; // esi
  void *v569; // r9
  void *v570; // r10
  void *v571; // r11
  void *v572; // rdx
  int v573; // eax
  void *v574; // rcx
  void *v575; // r10
  void *v576; // r11
  void *v577; // r9
  unsigned int *v578; // rcx
  __int64 v579; // rdx
  _BYTE *v580; // r9
  _DWORD *v581; // r12
  void *v582; // r13
  void *v583; // r9
  void *v584; // r10
  void *v585; // r11
  void *v586; // rax
  int v587; // eax
  unsigned int v588; // edx
  void *v589; // rcx
  HANDLE v590; // rax
  HANDLE v591; // rax
  void *v592; // r13
  HANDLE v593; // rax
  HANDLE v594; // rax
  HANDLE v595; // rax
  HLOCAL v596; // rax
  HANDLE v597; // rax
  _OWORD *v598; // rax
  void *v599; // r13
  void *v600; // r14
  HANDLE v601; // rax
  _QWORD *v602; // rax
  int v603; // eax
  int v604; // ecx
  unsigned int v605; // r11d
  unsigned int v606; // r11d
  unsigned int v607; // r11d
  size_t v608; // rdx
  unsigned int v609; // r11d
  unsigned int v610; // r11d
  unsigned int v611; // r11d
  unsigned int v612; // esi
  HANDLE v613; // rax
  _DWORD *v614; // rsi
  int v615; // eax
  int v616; // r9d
  unsigned int v617; // r11d
  _DWORD *v618; // rax
  unsigned int v619; // esi
  int v620; // r10d
  void *v621; // rsi
  HANDLE v622; // rax
  void *v623; // rsi
  HANDLE v624; // rax
  HANDLE v625; // rax
  HANDLE v626; // rax
  void *v627; // r12
  _DWORD *v628; // r13
  HANDLE v629; // rax
  _OWORD *v630; // rax
  void *v631; // r14
  HANDLE v632; // rax
  _QWORD *v633; // rax
  _QWORD *v634; // r13
  unsigned int *v635; // r9
  __int64 v636; // rdx
  __int64 v637; // r9
  unsigned int v638; // r10d
  unsigned int *v639; // r9
  unsigned int v640; // r11d
  int v641; // r10d
  unsigned int *v642; // r9
  __int64 v643; // rdx
  __int64 v644; // r9
  unsigned int v645; // r10d
  int v646; // r11d
  unsigned int *v647; // r9
  unsigned int *v648; // r10
  int v649; // r9d
  size_t v650; // rdx
  __int64 v651; // rdx
  __int64 v652; // r10
  unsigned int v653; // r9d
  int v654; // r11d
  _DWORD *v655; // r10
  _QWORD *v656; // rax
  SIZE_T v657; // rcx
  int v658; // r11d
  unsigned int *v659; // r9
  int v660; // esi
  __int64 v661; // rdx
  __int64 v662; // r9
  unsigned int v663; // r11d
  _DWORD *v664; // r9
  __int64 v665; // r10
  STRSAFE_PCNZWCH v666; // rdx
  void *v667; // rcx
  unsigned int *v668; // r9
  int v669; // r10d
  __int64 v670; // rdx
  __int64 v671; // r9
  unsigned int v672; // r10d
  int v673; // r11d
  _DWORD *v674; // r9
  _DWORD *v675; // rax
  unsigned int *v676; // r9
  int v677; // r10d
  __int64 v678; // rdx
  __int64 v679; // r9
  unsigned int v680; // r10d
  int v681; // r11d
  _DWORD *v682; // r9
  _DWORD *v683; // rax
  __int64 v684; // rcx
  unsigned int v685; // r10d
  unsigned int v686; // r9d
  int v687; // eax
  unsigned int v688; // r9d
  unsigned int v689; // eax
  unsigned int v690; // esi
  HANDLE v691; // rax
  _DWORD *v692; // rsi
  int v693; // r9d
  unsigned int v694; // r10d
  LPVOID v695; // rcx
  HANDLE v696; // rax
  _DWORD *v697; // rsi
  unsigned __int8 *v698; // r15
  SIZE_T v699; // r10
  unsigned __int8 v700; // al
  SIZE_T v701; // rcx
  unsigned __int8 *v702; // r11
  int v703; // edx
  unsigned int v704; // r9d
  int v705; // edi
  int v706; // ebx
  int v707; // r8d
  unsigned int v708; // r9d
  unsigned int v709; // r8d
  unsigned int v710; // ecx
  int v711; // r11d
  _BYTE *v712; // rdi
  char v713; // bl
  unsigned int v714; // r9d
  _BYTE *v715; // rdi
  size_t v716; // r15
  int v717; // r14d
  int v718; // r13d
  int v719; // eax
  int v720; // esi
  int v721; // r11d
  int v722; // edx
  int v723; // r9d
  int v724; // r10d
  int v725; // r8d
  int v726; // r9d
  unsigned int v727; // edx
  int v728; // r8d
  int v729; // ecx
  int v730; // edx
  int v731; // r8d
  int v732; // r9d
  int v733; // edx
  unsigned int v734; // r8d
  unsigned int v735; // r9d
  int v736; // edx
  int v737; // r8d
  int v738; // r9d
  int v739; // edx
  int v740; // r8d
  int v741; // r9d
  int v742; // edx
  int v743; // r8d
  unsigned int v744; // r9d
  int v745; // edx
  unsigned int v746; // ecx
  int v747; // r9d
  int v748; // edx
  HANDLE v749; // rax
  _DWORD *v750; // rax
  int v751; // r15d
  void *v752; // rax
  HANDLE v753; // rax
  SIZE_T v754; // rax
  HANDLE v755; // rax
  HANDLE v756; // rax
  HANDLE v757; // rax
  HANDLE v758; // rax
  HANDLE v759; // rax
  void *v760; // rcx
  _DWORD *v761; // r15
  HANDLE v762; // rax
  _OWORD *v763; // rax
  HANDLE v764; // rax
  _QWORD *v765; // rax
  _QWORD *v766; // rax
  HANDLE v767; // rax
  HANDLE v768; // rax
  HANDLE v769; // rax
  HANDLE v770; // rax
  const void **v771; // rsi
  unsigned int v772; // r9d
  int v773; // r15d
  __int64 v774; // rdx
  unsigned int v775; // r9d
  __int64 v776; // rdx
  unsigned int v777; // esi
  HANDLE v778; // rax
  LPVOID v779; // rcx
  LPVOID v780; // rax
  HANDLE v781; // rax
  _QWORD *v782; // rax
  HANDLE v783; // rax
  HANDLE v784; // rax
  HANDLE v785; // rax
  HANDLE v786; // rax
  HANDLE v787; // rax
  HANDLE v788; // rax
  _QWORD *v789; // rsi
  HANDLE v790; // rax
  HANDLE v791; // rax
  HANDLE v792; // rax
  HANDLE v793; // rax
  void *v794; // rsi
  HANDLE v795; // rax
  void *v796; // r9
  void *v797; // rcx
  void *v798; // r9
  int v799; // r10d
  SIZE_T v800; // rcx
  unsigned int *v801; // r9
  SIZE_T v802; // rcx
  unsigned int *v803; // r9
  int v804; // eax
  HANDLE v805; // rax
  int v806; // eax
  __int64 v807; // rcx
  void *v808; // r9
  SIZE_T v809; // rcx
  unsigned int v810; // r10d
  unsigned int v811; // r9d
  int v812; // r11d
  unsigned int v813; // esi
  SIZE_T v814; // rcx
  unsigned int v815; // esi
  HANDLE v816; // rax
  unsigned int v817; // r11d
  int v818; // r9d
  unsigned int v819; // r11d
  unsigned int v820; // r11d
  unsigned int v821; // r11d
  unsigned int v822; // r9d
  signed int v823; // eax
  FARPROC v824; // rax
  int v825; // eax
  unsigned int v826; // r9d
  unsigned int v827; // r11d
  int v828; // r15d
  unsigned int *v829; // rcx
  int v830; // r9d
  _BYTE *v831; // r10
  unsigned int v832; // r10d
  int v833; // r9d
  __int64 v834; // r11
  unsigned int v835; // r10d
  int v836; // r9d
  SIZE_T v837; // r11
  unsigned int v838; // r11d
  int v839; // r9d
  unsigned int v840; // r10d
  int v841; // r9d
  unsigned int v842; // r10d
  int v843; // r9d
  int v844; // r10d
  int v845; // r11d
  SIZE_T v846; // r15
  HANDLE v847; // rax
  SIZE_T v848; // rcx
  HANDLE v849; // rax
  void *v850; // rcx
  HANDLE v851; // rax
  void *v852; // rcx
  SIZE_T v853; // rax
  unsigned __int64 v854; // rax
  unsigned int v855; // r15d
  HANDLE v856; // rax
  void *v857; // rcx
  SIZE_T v858; // rax
  HANDLE v859; // rax
  HANDLE v860; // rax
  HANDLE v861; // rax
  HANDLE v862; // rax
  unsigned int *v863; // rdx
  HANDLE v864; // rax
  HANDLE v865; // rax
  HANDLE v866; // rax
  HANDLE v867; // rax
  unsigned __int64 v868; // r15
  unsigned __int8 v869; // al
  unsigned int v870; // r9d
  unsigned int v871; // r11d
  int v872; // edi
  int v873; // eax
  unsigned __int8 *v874; // rbx
  int v875; // r10d
  unsigned int v876; // r8d
  unsigned int v877; // r10d
  unsigned int v878; // r11d
  int v879; // ecx
  int v880; // edx
  _BYTE *v881; // rdi
  char v882; // bl
  int v883; // r10d
  size_t v884; // rcx
  int v885; // r11d
  unsigned __int8 *v886; // rbx
  int v887; // r9d
  _BYTE *v888; // r15
  int v889; // r13d
  int v890; // r12d
  size_t v891; // rax
  int v892; // ecx
  int v893; // r14d
  int v894; // esi
  int v895; // r14d
  int v896; // edx
  int v897; // esi
  int v898; // r8d
  int v899; // r9d
  unsigned int v900; // edx
  int v901; // r8d
  int v902; // r9d
  unsigned int v903; // edx
  int v904; // r8d
  int v905; // r10d
  int v906; // r11d
  unsigned int v907; // r9d
  int v908; // r8d
  unsigned int v909; // r9d
  int v910; // r10d
  int v911; // r11d
  int v912; // edx
  int v913; // r8d
  int v914; // r9d
  int v915; // edx
  int v916; // r10d
  int v917; // r8d
  unsigned int v918; // edx
  int v919; // r8d
  unsigned __int64 j; // rcx
  int v921; // r15d
  void *v922; // rcx
  void *v923; // r9
  void *v924; // r10
  void *v925; // r11
  void *v926; // rdx
  void *v927; // rcx
  void *v928; // r11
  void *v929; // r9
  void *v930; // r10
  unsigned int *v931; // rcx
  __int64 v932; // rdx
  void *v933; // r12
  _DWORD *v934; // r13
  void *v935; // rsi
  void *v936; // r9
  void *v937; // r10
  void *v938; // r11
  void *v939; // rax
  unsigned int v940; // edx
  void *v941; // rcx
  HANDLE v942; // rax
  int v943; // eax
  void *v944; // rcx
  _DWORD *v945; // r9
  int v946; // r10d
  int v947; // r11d
  int *v948; // r15
  int v949; // esi
  unsigned int v950; // r11d
  int v951; // r10d
  void *v952; // r9
  int v953; // r10d
  void **v954; // rdx
  _BYTE *v955; // rax
  SIZE_T v956; // rcx
  unsigned int v957; // r11d
  int v958; // r10d
  void *v959; // r9
  int v960; // r10d
  __int64 v961; // r11
  void *v962; // rcx
  __int64 v963; // rsi
  unsigned int v964; // r11d
  int v965; // r10d
  unsigned int *v966; // r9
  int v967; // r11d
  unsigned int *v968; // rcx
  unsigned int v969; // esi
  int v970; // r10d
  void *v971; // r9
  int v972; // r10d
  unsigned int *v973; // rdx
  void *v974; // rcx
  unsigned int v975; // esi
  unsigned int v976; // r9d
  int v977; // r10d
  int v978; // r9d
  size_t v979; // r11
  int *v980; // rcx
  _DWORD *v981; // rcx
  int v982; // eax
  int v983; // r9d
  int v984; // eax
  int v985; // r9d
  int v986; // eax
  int v987; // r9d
  unsigned int v988; // esi
  HANDLE v989; // rax
  _DWORD *v990; // rsi
  void *v991; // rsi
  HANDLE v992; // rax
  HANDLE v993; // rax
  HANDLE v994; // rax
  HANDLE v995; // rax
  _DWORD *v996; // r9
  unsigned int v997; // r11d
  _DWORD *v998; // rax
  unsigned int v999; // esi
  int v1000; // r10d
  unsigned int *v1001; // r9
  int v1002; // r13d
  __int64 v1003; // rdx
  __int64 v1004; // r9
  unsigned int v1005; // r10d
  unsigned int *v1006; // r9
  unsigned int v1007; // r11d
  int v1008; // r10d
  unsigned int *v1009; // r9
  __int64 v1010; // rdx
  __int64 v1011; // r9
  unsigned int v1012; // r10d
  int v1013; // r11d
  unsigned int *v1014; // r9
  unsigned int *v1015; // r10
  int v1016; // r9d
  __int64 v1017; // rdx
  __int64 v1018; // r10
  unsigned int v1019; // r9d
  int v1020; // r11d
  _DWORD *v1021; // r10
  _QWORD *v1022; // rax
  LPVOID v1023; // rcx
  __int64 v1024; // rcx
  unsigned int v1025; // r9d
  int v1026; // r13d
  int v1027; // ecx
  unsigned int v1028; // r10d
  unsigned int v1029; // eax
  unsigned int v1030; // esi
  HANDLE v1031; // rax
  char *v1032; // rax
  char *v1033; // rsi
  unsigned int v1034; // r9d
  LPVOID v1035; // rcx
  HANDLE v1036; // rax
  unsigned int *v1037; // rsi
  _DWORD *v1038; // r13
  int v1039; // ecx
  SIZE_T v1040; // r11
  unsigned __int8 v1041; // al
  SIZE_T v1042; // r8
  unsigned __int8 *v1043; // r9
  unsigned int v1044; // r10d
  unsigned int v1045; // edi
  int v1046; // ebx
  int v1047; // esi
  int v1048; // r8d
  int v1049; // r8d
  unsigned int v1050; // r8d
  unsigned int v1051; // r9d
  unsigned int v1052; // ecx
  int v1053; // edx
  _BYTE *v1054; // rbx
  unsigned int v1055; // edi
  char v1056; // r13
  int v1057; // r9d
  unsigned __int8 *v1058; // rdi
  size_t v1059; // r14
  _BYTE *v1060; // r13
  int v1061; // r12d
  int v1062; // eax
  unsigned int v1063; // r15d
  int v1064; // ecx
  int v1065; // esi
  int v1066; // r11d
  int v1067; // esi
  int v1068; // r11d
  int v1069; // r8d
  int v1070; // r10d
  int v1071; // r8d
  int v1072; // r10d
  int v1073; // r9d
  int v1074; // r8d
  unsigned int v1075; // edx
  int v1076; // r9d
  int v1077; // ecx
  int v1078; // edx
  int v1079; // r8d
  int v1080; // r9d
  int v1081; // edx
  unsigned int v1082; // r8d
  unsigned int v1083; // r9d
  int v1084; // edx
  int v1085; // r8d
  int v1086; // r9d
  int v1087; // edx
  int v1088; // r8d
  int v1089; // r9d
  int v1090; // edx
  int v1091; // r8d
  unsigned int v1092; // r9d
  int v1093; // edx
  unsigned int v1094; // ecx
  int v1095; // r9d
  int v1096; // edx
  HANDLE v1097; // rax
  _DWORD *v1098; // rax
  void *v1099; // rbx
  unsigned int v1100; // ebx
  HANDLE v1101; // rax
  void *v1102; // rax
  HANDLE v1103; // rax
  _OWORD *v1104; // rcx
  SIZE_T v1105; // rax
  HANDLE v1106; // rax
  _QWORD *v1107; // rax
  SIZE_T v1108; // rax
  HANDLE v1109; // rax
  HANDLE v1110; // rax
  HANDLE v1111; // rax
  HANDLE v1112; // rax
  void *v1113; // rcx
  HANDLE v1114; // rax
  _QWORD *v1115; // rax
  HANDLE v1116; // rax
  HANDLE v1117; // rax
  HANDLE v1118; // rax
  HANDLE v1119; // rax
  __int64 v1120; // rdx
  unsigned int v1121; // r9d
  __int64 v1122; // rdx
  unsigned int v1123; // r9d
  __int64 v1124; // rdx
  unsigned int v1125; // ebx
  HANDLE v1126; // rax
  _DWORD *v1127; // rax
  void *v1128; // rdi
  void *v1129; // rcx
  int v1130; // r9d
  SIZE_T v1131; // rcx
  unsigned int *v1132; // r9
  SIZE_T v1133; // rcx
  unsigned int *v1134; // r9
  int v1135; // eax
  HANDLE v1136; // rax
  int LastError; // eax
  int v1138; // eax
  int v1139; // r9d
  __int64 v1140; // rcx
  SIZE_T v1141; // rcx
  unsigned int v1142; // r11d
  int v1143; // r10d
  unsigned int v1144; // ebx
  SIZE_T v1145; // rcx
  unsigned int v1146; // ebx
  HANDLE v1147; // rax
  unsigned int v1148; // r11d
  int v1149; // r10d
  int v1150; // r9d
  unsigned int v1151; // r11d
  unsigned int v1152; // r11d
  unsigned int v1153; // r11d
  unsigned int v1154; // r10d
  bool v1155; // sf
  FARPROC ProcAddress; // rax
  unsigned int v1157; // r9d
  SIZE_T v1158; // rbx
  int v1159; // ecx
  unsigned int v1160; // r10d
  int v1161; // r9d
  int v1162; // r9d
  __int64 v1163; // r10
  unsigned int v1164; // r10d
  int v1165; // r9d
  SIZE_T v1166; // r11
  unsigned int v1167; // r11d
  int v1168; // r9d
  unsigned int v1169; // r10d
  int v1170; // r9d
  unsigned int v1171; // r10d
  int v1172; // r9d
  int v1173; // r10d
  int v1174; // r11d
  HANDLE v1175; // rax
  _QWORD *v1176; // rax
  SIZE_T v1177; // rcx
  HANDLE v1178; // rax
  void *v1179; // rcx
  _QWORD *v1180; // rax
  HANDLE v1181; // rax
  void *v1182; // rcx
  SIZE_T v1183; // rax
  HANDLE v1184; // rax
  void *v1185; // rcx
  _BYTE *v1186; // rcx
  HANDLE v1187; // rax
  HANDLE v1188; // rax
  HANDLE v1189; // rax
  HANDLE v1190; // rax
  unsigned int *v1191; // rdx
  unsigned int *v1192; // rax
  HANDLE v1193; // rax
  HANDLE v1194; // rax
  HANDLE v1195; // rax
  HANDLE v1196; // rax
  _BYTE *v1197; // r10
  size_t v1198; // r11
  unsigned __int8 v1199; // al
  unsigned __int8 *v1200; // r9
  int v1201; // edi
  int v1202; // r11d
  unsigned int v1203; // eax
  int v1204; // ecx
  _BYTE *v1205; // rcx
  unsigned int v1206; // edx
  unsigned int v1207; // r8d
  unsigned int v1208; // r9d
  int v1209; // ebx
  unsigned int v1210; // eax
  int v1211; // edi
  char v1212; // r10
  int v1213; // r9d
  int v1214; // r15d
  SIZE_T v1215; // r14
  int v1216; // r10d
  _BYTE *v1217; // r13
  int v1218; // r12d
  int v1219; // r11d
  unsigned __int8 *v1220; // rax
  int v1221; // ecx
  int v1222; // esi
  int v1223; // ebx
  int v1224; // esi
  int v1225; // edx
  int v1226; // ebx
  unsigned int v1227; // r8d
  int v1228; // r9d
  unsigned int v1229; // edx
  int v1230; // r8d
  int v1231; // r9d
  unsigned int v1232; // edx
  int v1233; // r8d
  int v1234; // r10d
  int v1235; // r11d
  unsigned int v1236; // r9d
  int v1237; // r8d
  unsigned int v1238; // r9d
  int v1239; // r10d
  int v1240; // r11d
  int v1241; // edx
  int v1242; // r8d
  unsigned int v1243; // r9d
  int v1244; // edx
  int v1245; // r10d
  int v1246; // r8d
  unsigned int v1247; // edx
  int v1248; // ecx
  size_t i; // rcx
  void *v1250; // r9
  void *v1251; // rdi
  int v1252; // ecx
  unsigned int *v1253; // r10
  int v1254; // r11d
  __int64 v1255; // rbx
  int v1256; // r11d
  unsigned int v1257; // r11d
  __int64 v1258; // r8
  unsigned int *v1259; // r11
  void *v1260; // r10
  LPVOID v1261; // rax
  unsigned int *v1262; // rbx
  __int64 v1263; // rdx
  unsigned int v1264; // edx
  void *v1265; // rcx
  HANDLE v1266; // rax
  int v1267; // eax
  HANDLE v1268; // rax
  void *v1269; // rbx
  HANDLE v1270; // rax
  void *v1271; // rbx
  HANDLE v1272; // rax
  void *v1273; // rbx
  HANDLE v1274; // rax
  HANDLE v1275; // rax
  void *v1276; // rbx
  HANDLE v1277; // rax
  HANDLE v1278; // rax
  _QWORD *v1279; // rbx
  void *v1280; // rsi
  HANDLE v1281; // rax
  void *v1282; // rsi
  HANDLE v1283; // rax
  void *v1284; // rsi
  HANDLE v1285; // rax
  HANDLE v1286; // rax
  HANDLE v1287; // rax
  unsigned int v1288; // r9d
  __int64 v1289; // r11
  int *v1290; // rcx
  SIZE_T v1291; // rcx
  unsigned int v1292; // r10d
  int v1293; // r9d
  int v1294; // ecx
  int v1295; // r8d
  int v1296; // r9d
  SIZE_T v1298; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v1299; // [rsp+58h] [rbp-A8h]
  SIZE_T v1300; // [rsp+60h] [rbp-A0h] BYREF
  void *Src; // [rsp+68h] [rbp-98h]
  int v1302; // [rsp+70h] [rbp-90h]
  LPVOID v1303; // [rsp+78h] [rbp-88h] BYREF
  LPVOID v1304; // [rsp+80h] [rbp-80h]
  unsigned int uBytes; // [rsp+88h] [rbp-78h]
  unsigned __int8 uBytes_4; // [rsp+8Ch] [rbp-74h]
  size_t Size; // [rsp+90h] [rbp-70h] BYREF
  LPVOID v1308; // [rsp+98h] [rbp-68h]
  SIZE_T v1309; // [rsp+A0h] [rbp-60h] BYREF
  SIZE_T v1310; // [rsp+A8h] [rbp-58h] BYREF
  SIZE_T v1311; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID v1312; // [rsp+B8h] [rbp-48h] BYREF
  SIZE_T v1313; // [rsp+C0h] [rbp-40h] BYREF
  LPVOID v1314; // [rsp+C8h] [rbp-38h]
  size_t pcchLength; // [rsp+D0h] [rbp-30h] BYREF
  size_t v1316; // [rsp+D8h] [rbp-28h]
  int v1317; // [rsp+E0h] [rbp-20h]
  void *v1318; // [rsp+E8h] [rbp-18h]
  void *v1319; // [rsp+F0h] [rbp-10h] BYREF
  LPVOID v1320; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE *v1321; // [rsp+100h] [rbp+0h]
  void *v1322; // [rsp+108h] [rbp+8h] BYREF
  SIZE_T v1323; // [rsp+110h] [rbp+10h]
  LPVOID lpMem; // [rsp+118h] [rbp+18h] BYREF
  SIZE_T v1325; // [rsp+120h] [rbp+20h]
  int v1326; // [rsp+128h] [rbp+28h]
  SIZE_T v1327; // [rsp+130h] [rbp+30h] BYREF
  LPVOID v1328; // [rsp+138h] [rbp+38h]
  size_t v1329; // [rsp+140h] [rbp+40h] BYREF
  size_t v1330[2]; // [rsp+148h] [rbp+48h] BYREF
  SIZE_T dwBytes; // [rsp+158h] [rbp+58h]
  unsigned int v1332; // [rsp+160h] [rbp+60h] BYREF
  SIZE_T v1333; // [rsp+168h] [rbp+68h] BYREF
  void *v1334; // [rsp+170h] [rbp+70h] BYREF
  size_t v1335[2]; // [rsp+178h] [rbp+78h] BYREF
  void *v1336; // [rsp+188h] [rbp+88h] BYREF
  unsigned int v1337; // [rsp+190h] [rbp+90h] BYREF
  unsigned int v1338; // [rsp+194h] [rbp+94h] BYREF
  STRSAFE_PCNZWCH psz; // [rsp+198h] [rbp+98h]
  unsigned int v1340; // [rsp+1A0h] [rbp+A0h]
  unsigned int v1341; // [rsp+1A4h] [rbp+A4h] BYREF
  unsigned int v1342; // [rsp+1A8h] [rbp+A8h] BYREF
  unsigned int v1343; // [rsp+1ACh] [rbp+ACh]
  unsigned int v1344; // [rsp+1B0h] [rbp+B0h] BYREF
  RPC_WSTR StringUuid; // [rsp+1B8h] [rbp+B8h] BYREF
  unsigned int v1346; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned int v1347; // [rsp+1C4h] [rbp+C4h] BYREF
  unsigned int v1348; // [rsp+1C8h] [rbp+C8h] BYREF
  size_t v1349; // [rsp+1D0h] [rbp+D0h] BYREF
  int v1350; // [rsp+1D8h] [rbp+D8h] BYREF
  int v1351; // [rsp+1DCh] [rbp+DCh] BYREF
  int v1352[4]; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned int v1353; // [rsp+1F0h] [rbp+F0h] BYREF
  int v1354; // [rsp+1F4h] [rbp+F4h] BYREF
  int v1355; // [rsp+1F8h] [rbp+F8h] BYREF
  int v1356; // [rsp+200h] [rbp+100h] BYREF
  HMODULE phModule; // [rsp+208h] [rbp+108h] BYREF
  HMODULE v1358; // [rsp+210h] [rbp+110h] BYREF
  HMODULE hModule; // [rsp+218h] [rbp+118h] BYREF
  HMODULE v1360; // [rsp+220h] [rbp+120h] BYREF
  __int128 v1361; // [rsp+230h] [rbp+130h] BYREF
  __int128 v1362; // [rsp+240h] [rbp+140h]
  __int128 v1363; // [rsp+250h] [rbp+150h] BYREF
  __int128 v1364; // [rsp+260h] [rbp+160h]
  __int128 v1365; // [rsp+270h] [rbp+170h] BYREF
  __int128 v1366; // [rsp+280h] [rbp+180h]
  __int128 v1367; // [rsp+290h] [rbp+190h] BYREF
  __int128 v1368; // [rsp+2A0h] [rbp+1A0h]
  const char *v1369; // [rsp+2B0h] [rbp+1B0h] BYREF
  RPC_WSTR v1370; // [rsp+2B8h] [rbp+1B8h] BYREF
  const char *v1371; // [rsp+2C0h] [rbp+1C0h] BYREF
  const char *v1372; // [rsp+2C8h] [rbp+1C8h] BYREF
  const unsigned __int16 *v1373; // [rsp+2D0h] [rbp+1D0h] BYREF
  const char *v1374; // [rsp+2D8h] [rbp+1D8h] BYREF
  const char *v1375; // [rsp+2E0h] [rbp+1E0h] BYREF
  const char *v1376; // [rsp+2E8h] [rbp+1E8h] BYREF
  const char *v1377; // [rsp+2F0h] [rbp+1F0h] BYREF
  const char *v1378; // [rsp+2F8h] [rbp+1F8h] BYREF
  const char *v1379; // [rsp+300h] [rbp+200h] BYREF
  const char *v1380; // [rsp+310h] [rbp+210h] BYREF
  const char *v1381; // [rsp+318h] [rbp+218h] BYREF
  const char *v1382; // [rsp+320h] [rbp+220h] BYREF
  unsigned __int16 *v1383; // [rsp+328h] [rbp+228h]
  const char *v1384; // [rsp+330h] [rbp+230h] BYREF
  const unsigned __int16 *v1385; // [rsp+340h] [rbp+240h] BYREF
  const char *v1386; // [rsp+348h] [rbp+248h] BYREF
  const char *v1387; // [rsp+350h] [rbp+250h] BYREF

  v1383 = a3;
  StringUuid = 0;
  v3 = -2147024809;
  lpMem = 0;
  pcchLength = 0;
  v1336 = 0;
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
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        v1385 = L"TerminalServices-RemoteConnectionManager-";
        v1386 = "GetInitialProgram";
        v1350 = v3;
        v1387 = "CSLQuery::GetInitialProgram - StringCchLength";
        v1369 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          dword_18012E170,
          (unsigned int)word_18011A50A,
          v7,
          v8,
          (__int64)&v1369,
          (__int64)&v1387,
          (__int64)&v1350,
          (__int64)&v1386,
          (__int64)&v1385);
      }
      goto LABEL_1661;
    }
    v3 = StringCchLengthW(StringUuid, v6, &pcchLength);
    if ( v3 < 0 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        v1370 = StringUuid;
        v1371 = "GetInitialProgram";
        v1372 = "CSLQuery::GetInitialProgram - StringCchLength";
        v1378 = "Warning HResult failed";
        v1351 = v3;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v10,
          (unsigned int)byte_18011A879,
          v11,
          v12,
          (__int64)&v1378,
          (__int64)&v1372,
          (__int64)&v1351,
          (__int64)&v1371,
          (__int64)&v1370);
      }
      goto LABEL_1661;
    }
    v3 = StringCchLengthW(L"-InitialProgram", v9, (unsigned __int64 *)&v1336);
    if ( v3 < 0 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        v1373 = L"-InitialProgram";
        v1374 = "GetInitialProgram";
        v1352[0] = v3;
        v1375 = "CSLQuery::GetInitialProgram - StringCchLength";
        v1376 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v13,
          (unsigned int)byte_180119FB1,
          v14,
          v15,
          (__int64)&v1376,
          (__int64)&v1375,
          (__int64)v1352,
          (__int64)&v1374,
          (__int64)&v1373);
      }
      goto LABEL_1661;
    }
    v16 = (unsigned __int64)lpMem + (_QWORD)v1336 + pcchLength + 3;
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
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        v1356 = v3;
        v1377 = "GetInitialProgram";
        v1384 = "CSLQuery::GetInitialProgram - StringCchPrintf";
        v1379 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (unsigned int)&dword_18012E170,
          (unsigned int)&word_18011A1CE,
          0,
          0,
          (__int64)&v1379,
          (__int64)&v1384,
          (__int64)&v1356,
          (__int64)&v1377);
      }
      goto LABEL_1661;
    }
    v1349 = 0;
    v1343 = 0;
    v1336 = 0;
    ProcessHeap = GetProcessHeap();
    v19 = HeapAlloc(ProcessHeap, 8u, 0xA0u);
    if ( !v19 )
    {
      v20 = -1073741801;
LABEL_21:
      v3 = v20;
LABEL_22:
      v21 = v1343;
LABEL_23:
      SP<unsigned char,SP_HLOCAL<unsigned char>>::Reset(&v1336);
      if ( v3 >= 0 )
      {
        if ( v21 )
        {
          v5 = (unsigned __int16 *)v1349;
          v1349 = 0;
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
      SP<unsigned char,SP_HLOCAL<unsigned char>>::Reset(&v1349);
      if ( v3 >= 0 )
      {
        if ( v21 + 1 <= 0x100 )
        {
          v3 = StringCchCopyW(v1383, 0x100u, v5);
        }
        else
        {
          v3 = -2147024774;
          if ( (unsigned int)dword_18012E170 > 3 && (unsigned __int8)tlgKeywordOn(&dword_18012E170, 0, 2147942522LL) )
          {
            v1355 = v1296;
            v1380 = "GetInitialProgram";
            v1353 = v21;
            v1381 = "CSLQuery::GetInitialProgram - BufferSize";
            v1382 = "Warning HResult failed";
            v1354 = v1295;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v1294,
              (unsigned int)byte_18011A993,
              v1295,
              v1296,
              (__int64)&v1382,
              (__int64)&v1381,
              (__int64)&v1354,
              (__int64)&v1380,
              (__int64)&v1353,
              (__int64)&v1355);
          }
        }
      }
      v4 = (wchar_t *)psz;
      goto LABEL_1661;
    }
    v22 = 0;
    uBytes = 0;
    *v19 = `WarbirdUmGetDecryptionCipher'::`2'::DecryptionCipher;
    v1326 = 0;
    v19[1] = xmmword_18012E5A0;
    v19[2] = xmmword_18012E5B0;
    v19[3] = xmmword_18012E5C0;
    v19[4] = xmmword_18012E5D0;
    v19[5] = xmmword_18012E5E0;
    v19[6] = xmmword_18012E5F0;
    v19[7] = xmmword_18012E600;
    v19[8] = xmmword_18012E610;
    v19[9] = xmmword_18012E620;
    v23 = GetProcessHeap();
    v24 = HeapAlloc(v23, 8u, 8u);
    v1332 = -1;
    Src = v24;
    v3 = -805306219;
    v1328 = (LPVOID)196;
    v1302 = -805306219;
    v1317 = -805306345;
    if ( !v24 )
    {
      v20 = -1073741801;
      v25 = 0;
LABEL_446:
      LODWORD(v1310) = 0;
      LODWORD(v1313) = 0;
      goto LABEL_447;
    }
    *v24 = `WarbirdUmGetDecryptionKey'::`2'::nDecryptionKey;
    v1327 = __rdtsc();
    pcchLength = 0;
    if ( StringCchLengthW(v4, (unsigned __int64)HIDWORD(v1327) << 32, &pcchLength) < 0 )
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
    v1320 = 0;
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
    LODWORD(v1298) = v34;
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
      v305 = v1320;
      if ( v1320 )
      {
        v306 = GetProcessHeap();
        HeapFree(v306, 0, v305);
      }
      v25 = Src;
      LODWORD(v1313) = uBytes;
      LODWORD(v1310) = v22;
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
        *v310 = `WarbirdUmGetDecryptionCipher'::`2'::DecryptionCipher;
        v310[1] = xmmword_18012E5A0;
        v310[2] = xmmword_18012E5B0;
        v310[3] = xmmword_18012E5C0;
        v310[4] = xmmword_18012E5D0;
        v310[5] = xmmword_18012E5E0;
        v310[6] = xmmword_18012E5F0;
        v310[7] = xmmword_18012E600;
        v310[8] = xmmword_18012E610;
        v310[9] = xmmword_18012E620;
        v312 = GetProcessHeap();
        v313 = HeapAlloc(v312, 8u, 8u);
        v314 = v313;
        if ( !v313 )
        {
          v22 = v1310;
          uBytes = v1313;
LABEL_777:
          v594 = GetProcessHeap();
          HeapFree(v594, 0, v311);
LABEL_778:
          if ( v314 )
          {
            v595 = GetProcessHeap();
            HeapFree(v595, 0, v314);
          }
LABEL_780:
          v596 = LocalAlloc(0x40u, uBytes);
          SP<unsigned char,SP_HLOCAL<unsigned char>>::operator=(&v1336, v596);
          v1316 = (size_t)v1336;
          if ( !v1336 )
          {
            v3 = -2147024882;
            goto LABEL_22;
          }
          v1340 = 0;
          *(_OWORD *)v1330 = 0;
          v1320 = 0;
          v597 = GetProcessHeap();
          v598 = HeapAlloc(v597, 8u, 0xA0u);
          v599 = v598;
          if ( !v598 )
          {
            v3 = -1073741801;
            v600 = 0;
            v1302 = -1073741801;
            goto LABEL_813;
          }
          *v598 = `WarbirdUmGetDecryptionCipher'::`2'::DecryptionCipher;
          v598[1] = xmmword_18012E5A0;
          v598[2] = xmmword_18012E5B0;
          v598[3] = xmmword_18012E5C0;
          v598[4] = xmmword_18012E5D0;
          v598[5] = xmmword_18012E5E0;
          v598[6] = xmmword_18012E5F0;
          v598[7] = xmmword_18012E600;
          v598[8] = xmmword_18012E610;
          v598[9] = xmmword_18012E620;
          v601 = GetProcessHeap();
          v602 = HeapAlloc(v601, 8u, 8u);
          v600 = v602;
          if ( !v602 )
          {
            v3 = -1073741801;
            v1302 = -1073741801;
            goto LABEL_813;
          }
          *v602 = `WarbirdUmGetDecryptionKey'::`2'::nDecryptionKey;
          v1333 = __rdtsc();
          LODWORD(v1309) = 0;
          LODWORD(v1298) = 0;
          v603 = RtlUIntAdd(4, 4, &v1298);
          if ( v603 < 0 )
            goto LABEL_812;
          v603 = RtlUIntAdd(0, (unsigned int)v1298, &v1309) | 0x10000000;
          if ( v603 < 0 )
            goto LABEL_812;
          LODWORD(v1298) = v604;
          v603 = RtlUIntAdd(v605, 160, &v1298);
          if ( v603 < 0 )
            goto LABEL_812;
          v603 = RtlUIntAdd((unsigned int)v1309, (unsigned int)v1298, &v1309) | 0x10000000;
          if ( v603 < 0 )
            goto LABEL_812;
          LODWORD(v1298) = 0;
          v603 = RtlUIntAdd(v606, v606 + 4, &v1298);
          if ( v603 < 0 )
            goto LABEL_812;
          v603 = RtlUIntAdd((unsigned int)v1309, (unsigned int)v1298, &v1309) | 0x10000000;
          if ( v603 < 0 )
            goto LABEL_812;
          LODWORD(v1298) = 0;
          v603 = RtlUIntAdd(v607, v607 + 4, &v1298);
          if ( v603 < 0 )
            goto LABEL_812;
          v603 = RtlUIntAdd((unsigned int)v1309, (unsigned int)v1298, &v1309) | 0x10000000;
          if ( v603 < 0 )
            goto LABEL_812;
          v1329 = 0;
          if ( StringCchLengthW(psz, v608, &v1329) < 0 )
          {
            v3 = -1073741762;
LABEL_1014:
            v1302 = v3;
            goto LABEL_813;
          }
          LODWORD(v1298) = 0;
          v603 = RtlUIntAdd(v609, (unsigned int)(2 * (v1329 + 1)), &v1298);
          if ( v603 < 0
            || (v603 = RtlUIntAdd((unsigned int)v1309, (unsigned int)v1298, &v1309) | 0x10000000, v603 < 0)
            || (LODWORD(v1298) = 0, v603 = RtlUIntAdd(v610, v610, &v1298), v603 < 0)
            || (v603 = RtlUIntAdd((unsigned int)v1309, (unsigned int)v1298, &v1309) | 0x10000000, v603 < 0)
            || (LODWORD(v1298) = 0, v603 = RtlUIntAdd(v611, v611, &v1298), v603 < 0)
            || (v603 = RtlUIntAdd((unsigned int)v1309, (unsigned int)v1298, &v1309) | 0x10000000, v603 < 0) )
          {
LABEL_812:
            v3 = v603;
            v1302 = v603;
            goto LABEL_813;
          }
          HIDWORD(v1330[0]) = v1309;
          v612 = v1309;
          v613 = GetProcessHeap();
          v614 = HeapAlloc(v613, 8u, v612);
          if ( !v614 )
          {
            v3 = -1073741801;
            goto LABEL_1014;
          }
          v1330[1] = (size_t)v614;
          v1321 = 0;
          LODWORD(v1313) = 0;
          LODWORD(v1330[0]) = 0;
          LODWORD(v1322) = 0;
          pcchLength = (size_t)v614;
          LODWORD(Size) = 8;
          v615 = RtlULongLongAdd(v614, 4, &v1322);
          if ( v615 < 0 )
            goto LABEL_809;
          if ( (unsigned __int64)(v614 + 2) > v1330[1] + HIDWORD(v1330[0]) )
            goto LABEL_805;
          v618 = v1322;
          *v614 = 4;
          v619 = Size;
          *v618 = v616;
          v620 = ++LODWORD(v1330[0]);
          v1321 = 0;
          LODWORD(v1322) = 0;
          if ( v599 )
          {
            if ( !v617 )
              goto LABEL_808;
          }
          else if ( v617 )
          {
LABEL_808:
            v615 = -1073741811;
            goto LABEL_809;
          }
          v635 = (unsigned int *)v1330[1];
          if ( v1330[1] )
          {
            pcchLength = v1330[1];
            LODWORD(Size) = 0;
            if ( v620 )
            {
              do
              {
                v636 = *v635;
                LODWORD(v1298) = 0;
                v615 = RtlUIntAdd(4, v636, &v1298);
                if ( v615 < 0 )
                  goto LABEL_809;
                v615 = RtlULongLongAdd(v637, (unsigned int)v1298, &pcchLength);
                if ( v615 < 0 )
                  goto LABEL_809;
                v635 = (unsigned int *)pcchLength;
                LODWORD(Size) = Size + 1;
              }
              while ( (unsigned int)Size < v638 );
            }
            v615 = RtlULongLongAdd(v635, 4, &v1322);
            if ( v615 < 0 )
              goto LABEL_809;
            if ( (unsigned __int64)v639 + v640 + 4 > v1330[1] + HIDWORD(v1330[0]) )
              goto LABEL_805;
            *v639 = v640;
            if ( v599 )
              memcpy_0(v1322, v599, v640);
          }
          else
          {
            LODWORD(v1298) = 0;
            v615 = RtlUIntAdd(4, v617, &v1298);
            if ( v615 < 0 )
              goto LABEL_809;
            v615 = RtlUIntAdd(HIDWORD(v1330[0]), (unsigned int)v1298, (char *)v1330 + 4);
            if ( v615 < 0 )
              goto LABEL_809;
          }
          v641 = ++LODWORD(v1330[0]);
          v1321 = 0;
          LODWORD(v1322) = 0;
          if ( v600 )
          {
            if ( !v619 )
              goto LABEL_808;
          }
          else if ( v619 )
          {
            goto LABEL_808;
          }
          v642 = (unsigned int *)v1330[1];
          if ( v1330[1] )
          {
            pcchLength = v1330[1];
            if ( v641 )
            {
              do
              {
                v643 = *v642;
                LODWORD(v1298) = 0;
                v615 = RtlUIntAdd(4, v643, &v1298);
                if ( v615 < 0 )
                  goto LABEL_809;
                v615 = RtlULongLongAdd(v644, (unsigned int)v1298, &pcchLength);
                if ( v615 < 0 )
                  goto LABEL_809;
                v642 = (unsigned int *)pcchLength;
              }
              while ( v646 + 1 < v645 );
            }
            v615 = RtlULongLongAdd(v642, 4, &v1322);
            if ( v615 < 0 )
              goto LABEL_809;
            if ( (unsigned __int64)v647 + v619 + 4 > v1330[1] + HIDWORD(v1330[0]) )
              goto LABEL_805;
            *v647 = v619;
            if ( v600 )
              memcpy_0(v1322, v600, v619);
          }
          else
          {
            LODWORD(v1298) = 0;
            v615 = RtlUIntAdd(4, v619, &v1298);
            if ( v615 < 0 )
              goto LABEL_809;
            v615 = RtlUIntAdd(HIDWORD(v1330[0]), (unsigned int)v1298, (char *)v1330 + 4);
            if ( v615 < 0 )
              goto LABEL_809;
          }
          v648 = (unsigned int *)v1330[1];
          v649 = ++LODWORD(v1330[0]);
          v1321 = 0;
          LODWORD(v1322) = 0;
          if ( v1330[1] )
          {
            pcchLength = v1330[1];
            if ( v649 )
            {
              do
              {
                v651 = *v648;
                LODWORD(v1298) = 0;
                v615 = RtlUIntAdd(4, v651, &v1298);
                if ( v615 < 0 )
                  goto LABEL_809;
                v615 = RtlULongLongAdd(v652, (unsigned int)v1298, &pcchLength);
                if ( v615 < 0 )
                  goto LABEL_809;
                v648 = (unsigned int *)pcchLength;
              }
              while ( v654 + 1 < v653 );
            }
            v615 = RtlULongLongAdd(v648, 4, &v1322);
            if ( v615 < 0 )
              goto LABEL_809;
            if ( (unsigned __int64)(v655 + 3) > v1330[1] + HIDWORD(v1330[0]) )
              goto LABEL_805;
            v656 = v1322;
            v657 = v1333;
            *v655 = 8;
            *v656 = v657;
          }
          else
          {
            LODWORD(v1298) = 0;
            v615 = RtlUIntAdd(4, 8, &v1298);
            if ( v615 < 0 )
              goto LABEL_809;
            v615 = RtlUIntAdd(HIDWORD(v1330[0]), (unsigned int)v1298, (char *)v1330 + 4);
            if ( v615 < 0 )
              goto LABEL_809;
          }
          ++LODWORD(v1330[0]);
          lpMem = 0;
          if ( StringCchLengthW(psz, v650, (size_t *)&lpMem) < 0 )
          {
            v615 = -1073741762;
            goto LABEL_809;
          }
          v615 = RtlULongLongAdd(lpMem, 1, &lpMem);
          if ( v615 < 0 )
            goto LABEL_809;
          v1321 = 0;
          LODWORD(v1322) = 0;
          if ( !(2 * (_DWORD)lpMem) )
            goto LABEL_808;
          v659 = (unsigned int *)v1330[1];
          if ( v1330[1] )
          {
            v660 = 0;
            pcchLength = v1330[1];
            if ( v658 )
            {
              do
              {
                v661 = *v659;
                LODWORD(v1298) = 0;
                v615 = RtlUIntAdd(4, v661, &v1298);
                if ( v615 < 0 )
                  goto LABEL_809;
                v615 = RtlULongLongAdd(v662, (unsigned int)v1298, &pcchLength);
                if ( v615 < 0 )
                  goto LABEL_809;
                v659 = (unsigned int *)pcchLength;
              }
              while ( ++v660 < v663 );
            }
            v615 = RtlULongLongAdd(v659, 4, &v1322);
            if ( v615 < 0 )
              goto LABEL_809;
            if ( (unsigned __int64)v664 + v665 + 4 > v1330[1] + HIDWORD(v1330[0]) )
              goto LABEL_805;
            v666 = psz;
            v667 = v1322;
            *v664 = v665;
            memcpy_0(v667, v666, (unsigned int)v665);
          }
          else
          {
            LODWORD(v1298) = 0;
            v615 = RtlUIntAdd(4, (unsigned int)(2 * (_DWORD)lpMem), &v1298);
            if ( v615 < 0 )
              goto LABEL_809;
            v615 = RtlUIntAdd(HIDWORD(v1330[0]), (unsigned int)v1298, (char *)v1330 + 4);
            if ( v615 < 0 )
              goto LABEL_809;
          }
          v668 = (unsigned int *)v1330[1];
          v669 = ++LODWORD(v1330[0]);
          v1321 = 0;
          LODWORD(v1322) = 0;
          if ( v1330[1] )
          {
            pcchLength = v1330[1];
            if ( v669 )
            {
              do
              {
                v670 = *v668;
                LODWORD(v1298) = 0;
                v615 = RtlUIntAdd(4, v670, &v1298);
                if ( v615 < 0 )
                  goto LABEL_809;
                v615 = RtlULongLongAdd(v671, (unsigned int)v1298, &pcchLength);
                if ( v615 < 0 )
                  goto LABEL_809;
                v668 = (unsigned int *)pcchLength;
              }
              while ( v673 + 1 < v672 );
            }
            v615 = RtlULongLongAdd(v668, 4, &v1322);
            if ( v615 < 0 )
              goto LABEL_809;
            if ( (unsigned __int64)(v674 + 2) > v1330[1] + HIDWORD(v1330[0]) )
              goto LABEL_805;
            v675 = v1322;
            *v674 = 4;
            *v675 = v22;
          }
          else
          {
            LODWORD(v1298) = 0;
            v615 = RtlUIntAdd(4, 4, &v1298);
            if ( v615 < 0 )
              goto LABEL_809;
            v615 = RtlUIntAdd(HIDWORD(v1330[0]), (unsigned int)v1298, (char *)v1330 + 4);
            if ( v615 < 0 )
              goto LABEL_809;
          }
          v676 = (unsigned int *)v1330[1];
          v677 = ++LODWORD(v1330[0]);
          v1321 = 0;
          LODWORD(v1322) = 0;
          if ( !v1330[1] )
          {
            LODWORD(v1298) = 0;
            v615 = RtlUIntAdd(4, 4, &v1298);
            if ( v615 < 0 )
              goto LABEL_809;
            v615 = RtlUIntAdd(HIDWORD(v1330[0]), (unsigned int)v1298, (char *)v1330 + 4);
            if ( v615 < 0 )
              goto LABEL_809;
LABEL_903:
            ++LODWORD(v1330[0]);
            LODWORD(v1298) = 0;
            v615 = RtlUIntAdd(4, 4, &v1298);
            if ( v615 < 0 )
              goto LABEL_809;
            LODWORD(v1310) = v1298;
            LODWORD(v1298) = 0;
            v615 = RtlUIntAdd(v684, 8, &v1298);
            if ( v615 < 0 )
              goto LABEL_809;
            v615 = RtlUIntAdd(v685, (unsigned int)v1298, &v1310);
            if ( v615 < 0 )
              goto LABEL_809;
            LODWORD(v1298) = 0;
            v615 = RtlUIntAdd(4, 4, &v1298);
            if ( v615 < 0 )
              goto LABEL_809;
            v615 = RtlUIntAdd((unsigned int)v1310, (unsigned int)v1298, &v1310);
            if ( v615 < 0 )
              goto LABEL_809;
            LODWORD(v1298) = 0;
            v615 = RtlUIntAdd(4, v686, &v1298);
            if ( v615 < 0 )
              goto LABEL_809;
            v615 = RtlUIntAdd((unsigned int)v1310, (unsigned int)v1298, &v1310);
            if ( v615 < 0 )
              goto LABEL_809;
            LODWORD(v1298) = 0;
            v615 = RtlUIntAdd(4, 4, &v1298);
            if ( v615 < 0 )
              goto LABEL_809;
            v615 = RtlUIntAdd((unsigned int)v1310, (unsigned int)v1298, &v1310);
            if ( v615 < 0 )
              goto LABEL_809;
            LODWORD(v1298) = 0;
            v615 = RtlUIntAdd(4, 4, &v1298);
            if ( v615 < 0 )
              goto LABEL_809;
            v615 = RtlUIntAdd((unsigned int)v1310, (unsigned int)v1298, &v1310);
            if ( v615 < 0 )
              goto LABEL_809;
            LODWORD(v1309) = v1310;
            LODWORD(Size) = 0;
            v1299 = 0;
            v1321 = (_BYTE *)__rdtsc();
            v1337 = 8;
            LODWORD(v1298) = 0;
            v687 = RtlUIntAdd(8, HIDWORD(v1330[0]), &v1337);
            if ( v687 < 0 )
            {
              v1318 = v600;
              v1312 = v599;
              v1326 = v22;
            }
            else
            {
              v689 = (v1337 + 7) & 0xFFFFFFF8;
              if ( v689 < v1337 )
                goto LABEL_813;
              v1337 = (v1337 + 7) & 0xFFFFFFF8;
              v690 = v689;
              v691 = GetProcessHeap();
              v692 = HeapAlloc(v691, 8u, v690);
              if ( !v692 )
              {
                v3 = -805306345;
                v1302 = -805306345;
                goto LABEL_1011;
              }
              v1326 = v22;
              v1312 = v599;
              v1318 = v600;
              lpMem = v692;
              *v692 = v1330[0];
              LODWORD(v1325) = RtlULongLongAdd(v692, 4, &lpMem);
              if ( (v1325 & 0x80000000) != 0LL
                || (v695 = lpMem,
                    *(_DWORD *)lpMem = HIDWORD(v1330[0]),
                    LODWORD(v1325) = RtlULongLongAdd(v695, v694, &lpMem),
                    (v1325 & 0x80000000) != 0LL) )
              {
                v1326 = v22;
                v1312 = v599;
                v1318 = v600;
                LODWORD(v1309) = v693;
                v696 = GetProcessHeap();
                HeapFree(v696, 0, v692);
                v687 = v1325;
                v688 = v1298;
              }
              else
              {
                *(_QWORD *)((char *)v692 + v1337 - 8) = v1321;
                memcpy_0(lpMem, (const void *)v1330[1], HIDWORD(v1330[0]));
                v688 = v1337;
                v687 = v1325;
                v1299 = v692;
              }
            }
            v1304 = 0;
            v1308 = 0;
            v697 = 0;
            dwBytes = 0;
            v1303 = 0;
            v3 = v687 | 0x10000000;
            v1314 = 0;
            v1302 = v687 | 0x10000000;
            if ( v687 < 0 )
              goto LABEL_986;
            v698 = (unsigned __int8 *)v1299;
            if ( !v1299 )
            {
              v3 = -805306355;
              goto LABEL_1014;
            }
            v1327 = v688;
            if ( !v688 || (lpMem = (LPVOID)(v688 + 8LL), (v1311 = (SIZE_T)MemoryAlloc((unsigned __int64)lpMem)) == 0) )
            {
              v3 = -805306367;
              v1302 = -805306367;
              goto LABEL_988;
            }
            v699 = v1327;
            v700 = 0;
            v701 = 0;
            v1300 = 0;
            uBytes_4 = 0;
            if ( v1327 )
            {
              do
                v700 ^= v698[v701++];
              while ( v701 < v1327 );
              uBytes_4 = v700;
            }
            pcchLength = v1311;
            v702 = v698;
            Src = (void *)0xC81ECB17B1B54A58LL;
            v1319 = v698;
            v703 = v1327 & 7;
            if ( (v1327 & 7) != 0 )
            {
              v704 = 0;
              LODWORD(v1325) = 0;
              LODWORD(v1323) = 0;
              v705 = 0;
              v706 = 0;
              do
              {
                v707 = *v702++;
                LODWORD(v1298) = 8 * v704;
                if ( v704 >= 4 )
                  v705 |= v707 << (56 - v1298);
                else
                  v706 |= v707 << (24 - v1298);
                ++v704;
              }
              while ( (int)v704 < v703 );
              LODWORD(v1323) = v706;
              LODWORD(v1325) = v705;
              v1319 = v702;
              v1299 = v698;
              v1318 = v600;
              v1312 = v599;
              v1326 = v22;
              LODWORD(v1310) = 0;
              v708 = v705 ^ 0x42F6B18D;
              v709 = v706 ^ 0xB17A307A;
              v710 = v706 ^ 0xB17A307A;
              v711 = v705 ^ 0x42F6B18D;
              if ( (v1327 & 7) != 0 )
              {
                v712 = (_BYTE *)pcchLength;
                do
                {
                  v1321 = v712 + 1;
                  if ( (unsigned int)v1310 >= 4 )
                  {
                    v711 = __ROR4__(v711, 24);
                    v713 = v711;
                  }
                  else
                  {
                    v710 = __ROR4__(v710, 24);
                    v713 = v710;
                  }
                  *v712 = v713;
                  LODWORD(v1310) = v1310 + 1;
                  v712 = v1321;
                }
                while ( (int)v1310 < v703 );
                pcchLength = (size_t)v1321;
              }
              if ( (unsigned int)v703 <= 4 )
              {
                v714 = 0;
                if ( (unsigned int)v703 < 4 )
                  v709 = v709 >> (8 * (4 - v703)) << (8 * (4 - v703));
              }
              else
              {
                v714 = v708 >> (8 * (8 - v703)) << (8 * (8 - v703));
              }
              v702 = (unsigned __int8 *)v1319;
            }
            else
            {
              v709 = 0;
              LODWORD(v1323) = 0;
              v714 = -1;
              LODWORD(v1325) = 0;
            }
            if ( v699 >> 3 )
            {
              v715 = (_BYTE *)pcchLength;
              v716 = v699 >> 3;
              v717 = v1323;
              v718 = WORD2(Src);
              LODWORD(v1298) = 19032;
              LODWORD(v1310) = WORD1(Src);
              v719 = v1325;
              v1329 = 0;
              do
              {
                v720 = v702[3] | ((v702[2] | (((*v702 << 8) | v702[1]) << 8)) << 8);
                v721 = *((unsigned __int8 *)v1319 + 7)
                     | ((*((unsigned __int8 *)v1319 + 6) | ((*((unsigned __int8 *)v1319 + 5) | (v702[4] << 8)) << 8)) << 8);
                v1319 = (char *)v1319 + 8;
                v722 = v714 ^ v721;
                v723 = v709 ^ v720 ^ HIDWORD(Src) ^ ((v714 ^ v721) - 19032);
                v724 = v722 ^ (__ROR4__(v723, 7) + WORD1(Src) * __ROR4__(v723 ^ HIDWORD(Src), 15));
                v725 = v723 ^ (v718 * __ROR4__(v724 - 1313519016, 9) - __ROR4__(v724, 10));
                v726 = v724 ^ (__ROR4__(v725, 27) + HIWORD(Src) * __ROR4__(v718 ^ v725, 28));
                v727 = v725 ^ (HIDWORD(Src) - (v726 ^ 0xB1B54A58));
                v728 = v726 ^ (WORD1(Src) * (v727 - 19032) - (v727 >> 6));
                v729 = v727 ^ (19032 * (v718 ^ __ROR4__(v728, 15)));
                v730 = v728 ^ (v718 * (HIWORD(Src) + __ROR4__(~v729, 3)));
                v731 = v729 ^ (v730 - 19032 - HIDWORD(Src));
                v732 = v730 ^ (v1310 * (v731 ^ HIWORD(Src))) ^ __ROR4__(v731, 10);
                v733 = v731 ^ __ROR4__(v732, 3) ^ (v718 * __ROR4__(v732 ^ 0x4A58, 26));
                v734 = v732 ^ (19032 * (__ROR4__(v733, 15) - HIWORD(Src)));
                v735 = v733
                     ^ ((v734 ^ (v734 >> 14)) >> 1)
                     ^ (19032 * (v734 ^ HIWORD(Src)))
                     ^ (19032 * ((8 * (v734 - v718)) | ((v734 - v718) >> 29)));
                v736 = v734 ^ (WORD1(Src) * (v735 - v718) - (v735 >> 13));
                v737 = v735 ^ __ROR4__(v736, 11) ^ (v718 * __ROR4__(-1313519016 - v736, 9));
                v738 = v736 ^ (v737 - HIWORD(Src) + 1313519016);
                v739 = v737 ^ (19032 * (v738 ^ WORD1(Src)) - __ROR4__(v738, 7));
                v740 = v738 ^ (WORD1(Src) * __ROR4__(v739 ^ HIWORD(Src), 28) - __ROR4__(v739, 16));
                v741 = v739 ^ (__ROR4__(v740, 4) + v718 * __ROR4__(-1313519016 - v740, 10));
                v742 = v740 ^ __ROR4__(v741, 9) ^ (HIWORD(Src) * __ROR4__(v741 + 1313519016, 4));
                v743 = v741 ^ (19032 * __ROR4__(v742 ^ HIDWORD(Src), 24) - __ROR4__(v742, 30));
                v744 = v742 ^ (WORD1(Src) * __ROR4__(HIDWORD(Src) - v743, 11) - __ROR4__(v743, 12));
                v745 = v744 ^ WORD1(Src);
                v746 = v744 >> 8;
                v747 = v719 ^ HIDWORD(Src) ^ v744;
                v719 = v721;
                v702 = (unsigned __int8 *)v1319;
                v748 = v743 ^ v746 ^ (v718 * v745);
                v709 = v748 ^ v717;
                v715[3] = v748 ^ v717;
                v714 = v748 ^ v747 ^ 0xB1B54A58;
                v715[7] = v714;
                LOBYTE(v746) = __ROR4__(v748 ^ v717, 8);
                v717 = v720;
                v715[2] = v746;
                v715[6] = __ROR4__(v714, 8);
                v715[1] = __ROR4__(v709, 16);
                v715[5] = __ROR4__(v714, 16);
                *v715 = __ROR4__(v709, 24);
                v715[4] = __ROR4__(v714, 24);
                v715 += 8;
                ++v1329;
              }
              while ( v1329 < v716 );
              v700 = uBytes_4;
              v22 = v1326;
              v599 = v1312;
              v600 = v1318;
              v697 = v1303;
              v698 = (unsigned __int8 *)v1299;
              v699 = v1327;
            }
            *(_QWORD *)(v1311 + v699) = v700;
            v749 = GetProcessHeap();
            v750 = HeapAlloc(v749, 8u, 0x30u);
            v1328 = v750;
            if ( v750 )
            {
              *v750 = (_DWORD)lpMem;
              v759 = GetProcessHeap();
              v760 = HeapAlloc(v759, 8u, (unsigned int)lpMem);
              if ( v760 )
              {
                v1299 = v698;
                v761 = v1328;
                *((_QWORD *)v1328 + 1) = v760;
                memcpy_0(v760, (const void *)v1311, (unsigned int)lpMem);
                v761[4] = 160;
                v762 = GetProcessHeap();
                v763 = HeapAlloc(v762, 8u, 0xA0u);
                if ( v763 )
                {
                  *((_QWORD *)v761 + 3) = v763;
                  *v763 = `WarbirdUmGetEncryptionCipher'::`2'::EncryptionCipher;
                  v763[1] = xmmword_18012E4F0;
                  v763[2] = xmmword_18012E500;
                  v763[3] = xmmword_18012E510;
                  v763[4] = xmmword_18012E520;
                  v763[5] = xmmword_18012E530;
                  v763[6] = xmmword_18012E540;
                  v763[7] = xmmword_18012E550;
                  v763[8] = xmmword_18012E560;
                  v763[9] = xmmword_18012E570;
                  v761[8] = 8;
                  v764 = GetProcessHeap();
                  v765 = HeapAlloc(v764, 8u, 8u);
                  if ( v765 )
                  {
                    *((_QWORD *)v761 + 5) = v765;
                    *v765 = `WarbirdUmGetEncryptionKey'::`2'::nEncryptionKey;
                    v1300 = (SIZE_T)v761;
                    v751 = 0;
                    v752 = (void *)v1300;
                    v1300 = 0;
LABEL_954:
                    v1304 = v752;
                    v753 = GetProcessHeap();
                    HeapFree(v753, 0, (LPVOID)v1311);
                    v754 = v1300;
                    if ( v1300 )
                    {
                      v1321 = *(_BYTE **)(v1300 + 8);
                      if ( v1321 )
                      {
                        v755 = GetProcessHeap();
                        HeapFree(v755, 0, v1321);
                        v754 = v1300;
                        *(_QWORD *)(v1300 + 8) = 0;
                      }
                      v1321 = *(_BYTE **)(v754 + 24);
                      if ( v1321 )
                      {
                        v756 = GetProcessHeap();
                        HeapFree(v756, 0, v1321);
                        v754 = v1300;
                        *(_QWORD *)(v1300 + 24) = 0;
                      }
                      v1321 = *(_BYTE **)(v754 + 40);
                      if ( v1321 )
                      {
                        v757 = GetProcessHeap();
                        HeapFree(v757, 0, v1321);
                        *(_QWORD *)(v1300 + 40) = 0;
                      }
                      v758 = GetProcessHeap();
                      HeapFree(v758, 0, (LPVOID)v1300);
                    }
                    v3 = v751 | 0x10000000;
                    v1302 = v3;
                    if ( v3 < 0 )
                    {
                      v780 = v1299;
LABEL_987:
                      if ( !v780 )
                      {
LABEL_989:
                        v782 = v1304;
                        if ( v1304 )
                        {
                          v1321 = (_BYTE *)*((_QWORD *)v1304 + 1);
                          if ( v1321 )
                          {
                            v783 = GetProcessHeap();
                            HeapFree(v783, 0, v1321);
                            v782 = v1304;
                            *((_QWORD *)v1304 + 1) = 0;
                          }
                          v1321 = (_BYTE *)v782[3];
                          if ( v1321 )
                          {
                            v784 = GetProcessHeap();
                            HeapFree(v784, 0, v1321);
                            v782 = v1304;
                            *((_QWORD *)v1304 + 3) = 0;
                          }
                          v1321 = (_BYTE *)v782[5];
                          if ( v1321 )
                          {
                            v785 = GetProcessHeap();
                            HeapFree(v785, 0, v1321);
                            *((_QWORD *)v1304 + 5) = 0;
                          }
                          v786 = GetProcessHeap();
                          HeapFree(v786, 0, v1304);
                        }
                        if ( dwBytes )
                        {
                          v787 = GetProcessHeap();
                          HeapFree(v787, 0, (LPVOID)dwBytes);
                        }
                        if ( v697 )
                        {
                          v788 = GetProcessHeap();
                          HeapFree(v788, 0, v697);
                        }
                        v789 = v1308;
                        if ( v1308 )
                        {
                          v1321 = (_BYTE *)*((_QWORD *)v1308 + 1);
                          if ( v1321 )
                          {
                            v790 = GetProcessHeap();
                            HeapFree(v790, 0, v1321);
                            v789[1] = 0;
                          }
                          v1321 = (_BYTE *)v789[3];
                          if ( v1321 )
                          {
                            v791 = GetProcessHeap();
                            HeapFree(v791, 0, v1321);
                            v789[3] = 0;
                          }
                          v1321 = (_BYTE *)v789[5];
                          if ( v1321 )
                          {
                            v792 = GetProcessHeap();
                            HeapFree(v792, 0, v1321);
                            v789[5] = 0;
                          }
                          v793 = GetProcessHeap();
                          HeapFree(v793, 0, v789);
                        }
                        v794 = v1314;
                        if ( v1314 )
                        {
                          v795 = GetProcessHeap();
                          HeapFree(v795, 0, v794);
                        }
LABEL_1011:
                        if ( v3 < 0 )
                          goto LABEL_813;
                        if ( !(_DWORD)Size )
                          goto LABEL_1013;
                        if ( v1320 )
                        {
                          v1329 = (size_t)v1320;
                          v1302 = RtlULongLongAdd(v1320, 4, &v1329);
                          v3 = v1302;
                          v1320 = v945;
                          if ( v1302 < 0 )
                            goto LABEL_810;
                          v948 = (int *)v1329;
                          if ( !*v945 )
                            v948 = 0;
                          if ( *v945 == v947 )
                          {
                            v3 = *v948;
                            v1302 = v3;
                            if ( v3 == -805306333 )
                            {
                              v949 = -2147024774;
                              LODWORD(v1313) = -2147024774;
                            }
                            else
                            {
                              LODWORD(v1313) = v3;
                              v949 = v3;
                              if ( v3 != -2147024774 && v3 < 0 )
                                goto LABEL_813;
                            }
                            v1320 = v945;
                            if ( v946 != 6 )
                            {
LABEL_1013:
                              v3 = -1073425151;
                              goto LABEL_1014;
                            }
                            v1319 = v944;
                            while ( 1 )
                            {
                              v1302 = RtlULongLongAdd(v944, 4, &v1319);
                              v3 = v1302;
                              if ( v1302 < 0 )
                                break;
                              v1302 = RtlULongLongAdd(v1319, v950, &v1319);
                              v3 = v1302;
                              if ( v1302 < 0 )
                                break;
                              v944 = v1319;
                              if ( v951 != -1 )
                              {
                                v1302 = RtlULongLongAdd(v1319, 4, &v1319);
                                v3 = v1302;
                                if ( v1302 < 0 )
                                  break;
                                v954 = (void **)v1319;
                                if ( !v953 )
                                  v954 = 0;
                                if ( v953 != 8 )
                                  goto LABEL_1250;
                                v1320 = v952;
                                if ( !v952 )
                                {
LABEL_1253:
                                  v3 = -1073741811;
                                  goto LABEL_1014;
                                }
                                v955 = *v954;
                                v956 = (SIZE_T)v952;
                                v1311 = (SIZE_T)v952;
                                v1321 = v955;
                                LODWORD(v1313) = v949;
                                while ( 1 )
                                {
                                  v1302 = RtlULongLongAdd(v956, 4, &v1311);
                                  v3 = v1302;
                                  if ( v1302 < 0 )
                                    goto LABEL_813;
                                  v1302 = RtlULongLongAdd(v1311, v957, &v1311);
                                  v3 = v1302;
                                  if ( v1302 < 0 )
                                    goto LABEL_813;
                                  v956 = v1311;
                                  if ( (unsigned int)(v958 + 1) >= 2 )
                                  {
                                    v1302 = RtlULongLongAdd(v1311, 4, &v1311);
                                    v3 = v1302;
                                    if ( v1302 < 0 )
                                      goto LABEL_813;
                                    if ( v960 != (_DWORD)v961 )
                                    {
LABEL_1262:
                                      v3 = -1073741789;
                                      goto LABEL_1014;
                                    }
                                    v1320 = v959;
                                    if ( !v959 )
                                      goto LABEL_1233;
                                    v962 = v959;
                                    LODWORD(v1313) = v949;
                                    v1319 = v959;
                                    v963 = v961;
                                    while ( 1 )
                                    {
                                      v1302 = RtlULongLongAdd(v962, v963, &v1319);
                                      v3 = v1302;
                                      if ( v1302 < 0 )
                                        goto LABEL_810;
                                      v1302 = RtlULongLongAdd(v1319, v964, &v1319);
                                      v3 = v1302;
                                      if ( v1302 < 0 )
                                        goto LABEL_810;
                                      v962 = v1319;
                                      if ( (unsigned int)(v965 + 1) >= 3 )
                                      {
                                        v1302 = RtlULongLongAdd(v1319, v963, &v1319);
                                        v3 = v1302;
                                        if ( v1302 >= 0 )
                                        {
                                          if ( v967 )
                                            v1329 = (size_t)v1319;
                                          else
                                            v1329 = 0;
                                          v968 = v966;
                                          v1319 = v966;
                                          while ( 1 )
                                          {
                                            v969 = *v968;
                                            v1302 = RtlULongLongAdd(v968, 4, &v1319);
                                            v3 = v1302;
                                            if ( v1302 < 0 )
                                              break;
                                            v1302 = RtlULongLongAdd(v1319, v969, &v1319);
                                            v3 = v1302;
                                            if ( v1302 < 0 )
                                              break;
                                            v968 = (unsigned int *)v1319;
                                            if ( (unsigned int)(v970 + 1) >= 4 )
                                            {
                                              v1302 = RtlULongLongAdd(v1319, 4, &v1319);
                                              v3 = v1302;
                                              if ( v1302 < 0 )
                                                goto LABEL_810;
                                              v973 = (unsigned int *)v1319;
                                              if ( !v972 )
                                                v973 = 0;
                                              if ( v972 != 4 )
                                                goto LABEL_1250;
                                              v1320 = v971;
                                              if ( !v971 )
                                                goto LABEL_1253;
                                              v974 = v971;
                                              v975 = *v973;
                                              v1319 = v971;
                                              while ( 1 )
                                              {
                                                v1302 = RtlULongLongAdd(v974, 4, &v1319);
                                                v3 = v1302;
                                                if ( v1302 < 0 )
                                                  goto LABEL_813;
                                                v1302 = RtlULongLongAdd(v1319, v976, &v1319);
                                                v3 = v1302;
                                                if ( v1302 < 0 )
                                                  goto LABEL_813;
                                                v974 = v1319;
                                                if ( (unsigned int)(v977 + 1) >= 5 )
                                                {
                                                  v1302 = RtlULongLongAdd(v1319, 4, &v1319);
                                                  v3 = v1302;
                                                  if ( v1302 < 0 )
                                                    goto LABEL_1014;
                                                  v980 = (int *)v1319;
                                                  if ( !v978 )
                                                    v980 = 0;
                                                  if ( v978 != 4 )
                                                    goto LABEL_1262;
                                                  if ( (_BYTE *)v1333 != v1321 )
                                                    goto LABEL_1013;
                                                  v22 = *v980;
                                                  v1340 = v975;
                                                  if ( uBytes )
                                                  {
                                                    if ( uBytes < v975 || uBytes < (unsigned int)v979 )
                                                    {
                                                      v3 = -2147024774;
                                                      goto LABEL_1014;
                                                    }
                                                    memcpy_0((void *)v1316, (const void *)v1329, v979);
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
                            v603 = v1313;
                            if ( (_DWORD)v1313 )
                              goto LABEL_812;
LABEL_813:
                            v621 = (void *)v1330[1];
                            v1330[0] = 0;
                            if ( v1330[1] )
                            {
                              v622 = GetProcessHeap();
                              HeapFree(v622, 0, v621);
                              v1330[1] = 0;
                            }
                            v623 = v1320;
                            if ( v1320 )
                            {
                              v624 = GetProcessHeap();
                              HeapFree(v624, 0, v623);
                            }
                            if ( v599 )
                            {
                              v625 = GetProcessHeap();
                              HeapFree(v625, 0, v599);
                            }
                            if ( v600 )
                            {
                              v626 = GetProcessHeap();
                              HeapFree(v626, 0, v600);
                            }
                            if ( v3 < 0 )
                              goto LABEL_22;
                            if ( !v22 )
                            {
LABEL_1289:
                              v21 = v1340;
                              v1349 = v1316;
                              v1336 = 0;
                              goto LABEL_23;
                            }
                            v627 = 0;
                            v628 = 0;
                            v1308 = 0;
                            *(_OWORD *)v1335 = 0;
                            v629 = GetProcessHeap();
                            v630 = HeapAlloc(v629, 8u, 0xA0u);
                            v631 = v630;
                            if ( !v630 )
                            {
LABEL_1281:
                              v991 = (void *)v1335[1];
                              v1335[0] = 0;
                              if ( v1335[1] )
                              {
                                v992 = GetProcessHeap();
                                HeapFree(v992, 0, v991);
                                v1335[1] = 0;
                              }
                              if ( v628 )
                              {
                                v993 = GetProcessHeap();
                                HeapFree(v993, 0, v628);
                              }
                              if ( v631 )
                              {
                                v994 = GetProcessHeap();
                                HeapFree(v994, 0, v631);
                              }
                              if ( v627 )
                              {
                                v995 = GetProcessHeap();
                                HeapFree(v995, 0, v627);
                              }
                              goto LABEL_1289;
                            }
                            *v630 = `WarbirdUmGetDecryptionCipher'::`2'::DecryptionCipher;
                            v630[1] = xmmword_18012E5A0;
                            v630[2] = xmmword_18012E5B0;
                            v630[3] = xmmword_18012E5C0;
                            v630[4] = xmmword_18012E5D0;
                            v630[5] = xmmword_18012E5E0;
                            v630[6] = xmmword_18012E5F0;
                            v630[7] = xmmword_18012E600;
                            v630[8] = xmmword_18012E610;
                            v630[9] = xmmword_18012E620;
                            v632 = GetProcessHeap();
                            v633 = HeapAlloc(v632, 8u, 8u);
                            v634 = v633;
                            if ( !v633 )
                            {
                              v628 = 0;
                              goto LABEL_1281;
                            }
                            *v633 = `WarbirdUmGetDecryptionKey'::`2'::nDecryptionKey;
                            v1321 = (_BYTE *)__rdtsc();
                            LODWORD(v1298) = 0;
                            LODWORD(v1313) = 0;
                            if ( (int)RtlUIntAdd(4, 4, &v1298) < 0 )
                              goto LABEL_1279;
                            if ( (int)RtlUIntAdd(0, (unsigned int)v1298, &v1313) < 0 )
                            {
                              v627 = v634;
                              v628 = v981;
                              goto LABEL_1281;
                            }
                            LODWORD(v1298) = (_DWORD)v981;
                            if ( (int)RtlUIntAdd(4, 160, &v1298) < 0 )
                              goto LABEL_1279;
                            v982 = RtlUIntAdd((unsigned int)v1313, (unsigned int)v1298, &v1313);
                            if ( (v983 | v982) < 0 )
                              goto LABEL_1279;
                            LODWORD(v1298) = 0;
                            if ( (int)RtlUIntAdd(4, 8, &v1298) < 0
                              || (v984 = RtlUIntAdd((unsigned int)v1313, (unsigned int)v1298, &v1313), (v985 | v984) < 0)
                              || (LODWORD(v1298) = 0, (int)RtlUIntAdd(4, 8, &v1298) < 0)
                              || (v986 = RtlUIntAdd((unsigned int)v1313, (unsigned int)v1298, &v1313), (v987 | v986) < 0)
                              || (HIDWORD(v1335[0]) = v1313,
                                  v988 = v1313,
                                  v989 = GetProcessHeap(),
                                  (v990 = HeapAlloc(v989, 8u, v988)) == 0) )
                            {
LABEL_1279:
                              v627 = v634;
                              goto LABEL_1280;
                            }
                            v1335[1] = (size_t)v990;
                            v1333 = 0;
                            LODWORD(v1335[0]) = 0;
                            LODWORD(v1334) = 0;
                            v627 = v634;
                            pcchLength = (size_t)v990;
                            LODWORD(Size) = 8;
                            if ( (int)RtlULongLongAdd(v990, 4, &v1334) < 0
                              || (unsigned __int64)(v990 + 2) > v1335[1] + HIDWORD(v1335[0]) )
                            {
LABEL_1340:
                              v628 = v996;
                              goto LABEL_1281;
                            }
                            v998 = v1334;
                            *v990 = 4;
                            v999 = Size;
                            *v998 = 4;
                            v1000 = ++LODWORD(v1335[0]);
                            v1333 = 0;
                            LODWORD(v1334) = 0;
                            if ( v631 )
                            {
                              if ( !v997 )
                                goto LABEL_1280;
                            }
                            else if ( v997 )
                            {
LABEL_1294:
                              v628 = 0;
                              goto LABEL_1281;
                            }
                            v1001 = (unsigned int *)v1335[1];
                            if ( v1335[1] )
                            {
                              v1002 = 0;
                              pcchLength = v1335[1];
                              if ( v1000 )
                              {
                                do
                                {
                                  v1003 = *v1001;
                                  LODWORD(v1298) = 0;
                                  if ( (int)RtlUIntAdd(4, v1003, &v1298) < 0
                                    || (int)RtlULongLongAdd(v1004, (unsigned int)v1298, &pcchLength) < 0 )
                                  {
                                    goto LABEL_1280;
                                  }
                                  v1001 = (unsigned int *)pcchLength;
                                }
                                while ( ++v1002 < v1005 );
                              }
                              if ( (int)RtlULongLongAdd(v1001, 4, &v1334) < 0
                                || (unsigned __int64)v1006 + v1007 + 4 > v1335[1] + HIDWORD(v1335[0]) )
                              {
                                goto LABEL_1280;
                              }
                              *v1006 = v1007;
                              if ( v631 )
                                memcpy_0(v1334, v631, v1007);
                            }
                            else
                            {
                              LODWORD(v1298) = 0;
                              if ( (int)RtlUIntAdd(4, v997, &v1298) < 0
                                || (int)RtlUIntAdd(HIDWORD(v1335[0]), (unsigned int)v1298, (char *)v1335 + 4) < 0 )
                              {
                                goto LABEL_1280;
                              }
                            }
                            v1008 = ++LODWORD(v1335[0]);
                            v1333 = 0;
                            LODWORD(v1334) = 0;
                            if ( v627 )
                            {
                              if ( !v999 )
                                goto LABEL_1280;
                            }
                            else if ( v999 )
                            {
                              goto LABEL_1294;
                            }
                            v1009 = (unsigned int *)v1335[1];
                            if ( v1335[1] )
                            {
                              pcchLength = v1335[1];
                              if ( v1008 )
                              {
                                do
                                {
                                  v1010 = *v1009;
                                  LODWORD(v1298) = 0;
                                  if ( (int)RtlUIntAdd(4, v1010, &v1298) < 0
                                    || (int)RtlULongLongAdd(v1011, (unsigned int)v1298, &pcchLength) < 0 )
                                  {
                                    goto LABEL_1280;
                                  }
                                  v1009 = (unsigned int *)pcchLength;
                                }
                                while ( v1013 + 1 < v1012 );
                              }
                              if ( (int)RtlULongLongAdd(v1009, 4, &v1334) < 0
                                || (unsigned __int64)v1014 + v999 + 4 > v1335[1] + HIDWORD(v1335[0]) )
                              {
                                goto LABEL_1280;
                              }
                              *v1014 = v999;
                              if ( v627 )
                                memcpy_0(v1334, v627, v999);
                            }
                            else
                            {
                              LODWORD(v1298) = 0;
                              if ( (int)RtlUIntAdd(4, v999, &v1298) < 0
                                || (int)RtlUIntAdd(HIDWORD(v1335[0]), (unsigned int)v1298, (char *)v1335 + 4) < 0 )
                              {
                                goto LABEL_1280;
                              }
                            }
                            v1015 = (unsigned int *)v1335[1];
                            v1016 = ++LODWORD(v1335[0]);
                            v1333 = 0;
                            LODWORD(v1334) = 0;
                            if ( !v1335[1] )
                            {
                              LODWORD(v1298) = 0;
                              if ( (int)RtlUIntAdd(4, 8, &v1298) < 0
                                || (int)RtlUIntAdd(HIDWORD(v1335[0]), (unsigned int)v1298, (char *)v1335 + 4) < 0 )
                              {
                                goto LABEL_1280;
                              }
LABEL_1335:
                              ++LODWORD(v1335[0]);
                              LODWORD(v1298) = 0;
                              if ( (int)RtlUIntAdd(4, 4, &v1298) < 0 )
                                goto LABEL_1280;
                              LODWORD(Size) = v1298;
                              LODWORD(v1298) = 0;
                              if ( (int)RtlUIntAdd(v1024, 8, &v1298) < 0
                                || (int)RtlUIntAdd(v1025, (unsigned int)v1298, &Size) < 0 )
                              {
                                goto LABEL_1280;
                              }
                              v1026 = Size;
                              v1299 = 0;
                              LODWORD(v1323) = 0;
                              LODWORD(v1309) = Size;
                              v1321 = (_BYTE *)__rdtsc();
                              v1338 = 8;
                              v1027 = RtlUIntAdd(8, HIDWORD(v1335[0]), &v1338);
                              if ( v1027 < 0 )
                              {
                                v1318 = v627;
                                v1312 = v631;
                              }
                              else
                              {
                                v1029 = (v1338 + 7) & 0xFFFFFFF8;
                                if ( v1029 < v1338 )
                                  goto LABEL_1340;
                                v1338 = (v1338 + 7) & 0xFFFFFFF8;
                                v1030 = v1029;
                                v1031 = GetProcessHeap();
                                v1032 = (char *)HeapAlloc(v1031, 8u, v1030);
                                v1033 = v1032;
                                if ( !v1032 )
                                {
LABEL_1628:
                                  if ( v1317 >= 0 )
                                  {
                                    v628 = v1308;
                                    if ( (_DWORD)v1323 )
                                    {
                                      if ( v1308 )
                                      {
                                        v1333 = (SIZE_T)v1308;
                                        if ( (int)RtlULongLongAdd(v1308, 4, &v1333) >= 0 )
                                        {
                                          v1290 = (int *)v1333;
                                          if ( !*v628 )
                                            v1290 = 0;
                                          if ( *v628 == (_DWORD)v1289 && *v1290 >= 0 && v1288 > 1 )
                                          {
                                            v1291 = (SIZE_T)v628;
                                            v1311 = (SIZE_T)v628;
                                            while ( (int)RtlULongLongAdd(v1291, v1289, &v1311) >= 0
                                                 && (int)RtlULongLongAdd(v1311, v1292, &v1311) >= 0 )
                                            {
                                              v1291 = v1311;
                                              if ( v1293 != -1 )
                                              {
                                                RtlULongLongAdd(v1311, v1289, &v1311);
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
                                lpMem = v1032;
                                v1312 = v631;
                                v1318 = v627;
                                LODWORD(v1309) = v1026;
                                *(_DWORD *)v1032 = v1335[0];
                                LODWORD(Size) = RtlULongLongAdd(v1032, 4, &lpMem);
                                if ( (Size & 0x80000000) != 0LL
                                  || (v1035 = lpMem,
                                      *(_DWORD *)lpMem = HIDWORD(v1335[0]),
                                      LODWORD(Size) = RtlULongLongAdd(v1035, v1034, &lpMem),
                                      (Size & 0x80000000) != 0LL) )
                                {
                                  v1312 = v631;
                                  v1318 = v627;
                                  LODWORD(v1309) = v1026;
                                  v1036 = GetProcessHeap();
                                  HeapFree(v1036, 0, v1033);
                                  v996 = v1299;
                                  v1027 = Size;
                                  v1028 = (unsigned int)v1299;
                                }
                                else
                                {
                                  *(_QWORD *)&v1033[v1338 - 8] = v1321;
                                  memcpy_0(lpMem, (const void *)v1335[1], HIDWORD(v1335[0]));
                                  v1028 = v1338;
                                  v996 = v1033;
                                  v1027 = Size;
                                  v1299 = v1033;
                                }
                              }
                              v1037 = 0;
                              Src = 0;
                              v1038 = 0;
                              v1319 = 0;
                              v1039 = v1027 | 0x10000000;
                              v1320 = 0;
                              v1303 = 0;
                              v1304 = 0;
                              if ( v1039 < 0 )
                              {
                                v1317 = v1039;
                                v1128 = 0;
                                goto LABEL_1603;
                              }
                              if ( !v996 )
                                goto LABEL_1280;
                              v1327 = v1028;
                              if ( !v1028
                                || (lpMem = (LPVOID)(v1028 + 8LL), (v1336 = MemoryAlloc((unsigned __int64)lpMem)) == 0) )
                              {
                                v1099 = v1299;
                                v1128 = 0;
                                v1317 = -805306367;
                                goto LABEL_1605;
                              }
                              v1040 = v1327;
                              v1041 = 0;
                              v1042 = 0;
                              v1328 = 0;
                              uBytes_4 = 0;
                              if ( v1327 )
                              {
                                do
                                  v1041 ^= *((_BYTE *)v1299 + v1042++);
                                while ( v1042 < v1327 );
                                uBytes_4 = v1041;
                              }
                              v1314 = (LPVOID)0xC81ECB17B1B54A58LL;
                              v1333 = (SIZE_T)v1299;
                              v1043 = (unsigned __int8 *)v1299;
                              pcchLength = (size_t)v1336;
                              v1044 = v1327 & 7;
                              if ( (v1327 & 7) != 0 )
                              {
                                LODWORD(Size) = 0;
                                LODWORD(v1325) = 0;
                                v1045 = 0;
                                v1046 = 0;
                                v1047 = 0;
                                do
                                {
                                  v1048 = *v1043++;
                                  LODWORD(v1298) = 8 * v1045;
                                  if ( v1045 >= 4 )
                                    v1046 |= v1048 << (56 - v1298);
                                  else
                                    v1047 |= v1048 << (24 - v1298);
                                  ++v1045;
                                }
                                while ( (int)v1045 < (int)v1044 );
                                LODWORD(v1325) = v1047;
                                v1049 = v1047;
                                v1037 = 0;
                                LODWORD(Size) = v1046;
                                v1333 = (SIZE_T)v1043;
                                v1318 = v627;
                                v1312 = v631;
                                v1050 = v1049 ^ 0xB17A307A;
                                v1051 = v1046 ^ 0x42F6B18D;
                                v1052 = v1050;
                                v1053 = v1046 ^ 0x42F6B18D;
                                if ( (v1327 & 7) != 0 )
                                {
                                  v1054 = (_BYTE *)pcchLength;
                                  v1055 = 0;
                                  do
                                  {
                                    v1321 = v1054 + 1;
                                    if ( v1055 >= 4 )
                                    {
                                      v1053 = __ROR4__(v1053, 24);
                                      v1056 = v1053;
                                    }
                                    else
                                    {
                                      v1052 = __ROR4__(v1052, 24);
                                      v1056 = v1052;
                                    }
                                    *v1054 = v1056;
                                    ++v1055;
                                    v1054 = v1321;
                                  }
                                  while ( (int)v1055 < (int)v1044 );
                                  pcchLength = (size_t)v1321;
                                  v1038 = v1320;
                                }
                                if ( v1044 <= 4 )
                                {
                                  v1057 = 0;
                                  if ( v1044 < 4 )
                                    v1050 = v1050 >> (8 * (4 - v1044)) << (8 * (4 - v1044));
                                }
                                else
                                {
                                  v1057 = v1051 >> (8 * (8 - v1044)) << (8 * (8 - v1044));
                                }
                              }
                              else
                              {
                                v1050 = 0;
                                LODWORD(v1325) = 0;
                                v1057 = -1;
                                LODWORD(Size) = 0;
                              }
                              if ( v1040 >> 3 )
                              {
                                v1058 = (unsigned __int8 *)v1333;
                                v1059 = v1040 >> 3;
                                v1060 = (_BYTE *)pcchLength;
                                v1061 = v1325;
                                LODWORD(v1310) = 19032;
                                v1317 = WORD1(v1314);
                                uBytes = WORD2(v1314);
                                LODWORD(v1313) = HIWORD(v1314);
                                LODWORD(v1298) = HIDWORD(v1314) ^ 0xB1B54A58;
                                v1062 = Size;
                                v1063 = HIDWORD(v1314) ^ 0xB1B54A58;
                                v1329 = 0;
                                do
                                {
                                  v1064 = *v1058;
                                  v1065 = v1058[1];
                                  v1066 = v1058[4];
                                  v1058 += 8;
                                  v1067 = *(v1058 - 5) | ((*(v1058 - 6) | (((v1064 << 8) | v1065) << 8)) << 8);
                                  v1068 = *(v1058 - 1) | ((*(v1058 - 2) | ((*(v1058 - 3) | (v1066 << 8)) << 8)) << 8);
                                  v1069 = v1050 ^ v1067 ^ ((v1057 ^ v1068) - v1310);
                                  v1070 = __ROR4__(v1069, 15);
                                  v1071 = HIDWORD(v1314) ^ v1069;
                                  v1072 = v1057 ^ v1068 ^ (__ROR4__(v1071, 7) + WORD1(v1314) * v1070);
                                  v1073 = v1071 ^ (WORD2(v1314) * __ROR4__(v1072 - 1313519016, 9) - __ROR4__(v1072, 10));
                                  v1074 = v1072
                                        ^ (__ROR4__(v1073, 27) + HIWORD(v1314) * __ROR4__(WORD2(v1314) ^ v1073, 28));
                                  v1075 = v1073 ^ (HIDWORD(v1314) - (v1074 ^ 0xB1B54A58));
                                  v1076 = v1074 ^ (WORD1(v1314) * (v1075 - v1310) - (v1075 >> 6));
                                  v1077 = v1075 ^ (v1310 * (WORD2(v1314) ^ __ROR4__(v1076, 15)));
                                  v1078 = v1076 ^ (WORD2(v1314) * (v1313 + __ROR4__(~v1077, 3)));
                                  v1079 = v1077 ^ (v1078 - HIDWORD(v1314) - v1310);
                                  v1080 = v1078 ^ (v1317 * (v1313 ^ v1079)) ^ __ROR4__(v1079, 10);
                                  v1081 = v1079 ^ __ROR4__(v1080, 3) ^ (WORD2(v1314) * __ROR4__(v1310 ^ v1080, 26));
                                  v1082 = v1080 ^ (v1310 * (__ROR4__(v1081, 15) - HIWORD(v1314)));
                                  v1083 = v1081
                                        ^ (v1310 * (v1313 ^ v1082))
                                        ^ ((v1082 ^ (v1082 >> 14)) >> 1)
                                        ^ (v1310 * (((v1082 - uBytes) >> 29) | (8 * (v1082 - WORD2(v1314)))));
                                  v1084 = v1082 ^ (WORD1(v1314) * (v1083 - WORD2(v1314)) - (v1083 >> 13));
                                  v1085 = v1083
                                        ^ __ROR4__(v1084, 11)
                                        ^ (WORD2(v1314) * __ROR4__(-1313519016 - v1084, 9));
                                  v1086 = v1084 ^ (v1085 - HIWORD(v1314) + 1313519016);
                                  v1087 = v1085 ^ (v1310 * (v1086 ^ WORD1(v1314)) - __ROR4__(v1086, 7));
                                  v1088 = v1086
                                        ^ (WORD1(v1314) * __ROR4__(v1087 ^ HIWORD(v1314), 28) - __ROR4__(v1087, 16));
                                  v1089 = v1087
                                        ^ (__ROR4__(v1088, 4) + WORD2(v1314) * __ROR4__(-1313519016 - v1088, 10));
                                  v1090 = v1088 ^ __ROR4__(v1089, 9) ^ (HIWORD(v1314) * __ROR4__(v1089 + 1313519016, 4));
                                  v1091 = v1089 ^ (v1310 * __ROR4__(v1090 ^ HIDWORD(v1314), 24) - __ROR4__(v1090, 30));
                                  v1092 = v1090
                                        ^ (WORD1(v1314) * __ROR4__(HIDWORD(v1314) - v1091, 11) - __ROR4__(v1091, 12));
                                  v1093 = WORD2(v1314) * (v1092 ^ WORD1(v1314));
                                  v1094 = v1092 >> 8;
                                  v1095 = v1063 ^ v1062 ^ v1092;
                                  v1062 = v1068;
                                  v1096 = v1091 ^ v1094 ^ v1093;
                                  v1050 = v1096 ^ v1061;
                                  v1057 = v1096 ^ v1095;
                                  v1060[3] = v1096 ^ v1061;
                                  LOBYTE(v1094) = __ROR4__(v1096 ^ v1061, 8);
                                  v1061 = v1067;
                                  v1060[7] = v1057;
                                  v1060[2] = v1094;
                                  v1060[6] = __ROR4__(v1057, 8);
                                  v1060[1] = __ROR4__(v1050, 16);
                                  v1060[5] = __ROR4__(v1057, 16);
                                  *v1060 = __ROR4__(v1050, 24);
                                  v1060[4] = __ROR4__(v1057, 24);
                                  v1060 += 8;
                                  ++v1329;
                                }
                                while ( v1329 < v1059 );
                                v1038 = v1320;
                                v1041 = uBytes_4;
                                v1037 = (unsigned int *)v1320;
                                v3 = v1302;
                                v631 = v1312;
                                v627 = v1318;
                                v1040 = v1327;
                              }
                              *(_QWORD *)((char *)v1336 + v1040) = v1041;
                              v1097 = GetProcessHeap();
                              v1098 = HeapAlloc(v1097, 8u, 0x30u);
                              v1300 = (SIZE_T)v1098;
                              if ( !v1098 )
                              {
                                v1099 = v1299;
                                LODWORD(v1313) = -1073741801;
                                goto LABEL_1393;
                              }
                              v1100 = (unsigned int)lpMem;
                              *v1098 = (_DWORD)lpMem;
                              v1101 = GetProcessHeap();
                              v1102 = HeapAlloc(v1101, 8u, v1100);
                              v1099 = v1299;
                              if ( v1102 )
                              {
                                *(_QWORD *)(v1300 + 8) = v1102;
                                memcpy_0(v1102, v1336, (unsigned int)lpMem);
                                *(_DWORD *)(v1300 + 16) = 160;
                                v1103 = GetProcessHeap();
                                v1104 = HeapAlloc(v1103, 8u, 0xA0u);
                                v1105 = v1300;
                                if ( v1104 )
                                {
                                  *(_QWORD *)(v1300 + 24) = v1104;
                                  *v1104 = `WarbirdUmGetEncryptionCipher'::`2'::EncryptionCipher;
                                  v1104[1] = xmmword_18012E4F0;
                                  v1104[2] = xmmword_18012E500;
                                  v1104[3] = xmmword_18012E510;
                                  v1104[4] = xmmword_18012E520;
                                  v1104[5] = xmmword_18012E530;
                                  v1104[6] = xmmword_18012E540;
                                  v1104[7] = xmmword_18012E550;
                                  v1104[8] = xmmword_18012E560;
                                  v1104[9] = xmmword_18012E570;
                                  *(_DWORD *)(v1105 + 32) = 8;
                                  v1106 = GetProcessHeap();
                                  v1107 = HeapAlloc(v1106, 8u, 8u);
                                  if ( v1107 )
                                  {
                                    v1113 = (void *)v1300;
                                    *(_QWORD *)(v1300 + 40) = v1107;
                                    *v1107 = `WarbirdUmGetEncryptionKey'::`2'::nEncryptionKey;
                                    v1328 = v1113;
                                    LODWORD(v1313) = 0;
                                    v1299 = v1099;
                                    goto LABEL_1392;
                                  }
                                  v1105 = v1300;
                                }
                                v1300 = v1105;
                              }
                              v1108 = v1300;
                              LODWORD(v1313) = -1073741801;
                              v1299 = v1099;
                              v1321 = *(_BYTE **)(v1300 + 8);
                              if ( v1321 )
                              {
                                v1109 = GetProcessHeap();
                                HeapFree(v1109, 0, v1321);
                                v1108 = v1300;
                                *(_QWORD *)(v1300 + 8) = 0;
                              }
                              v1321 = *(_BYTE **)(v1108 + 24);
                              if ( v1321 )
                              {
                                v1110 = GetProcessHeap();
                                HeapFree(v1110, 0, v1321);
                                v1108 = v1300;
                                *(_QWORD *)(v1300 + 24) = 0;
                              }
                              v1321 = *(_BYTE **)(v1108 + 40);
                              if ( v1321 )
                              {
                                v1111 = GetProcessHeap();
                                HeapFree(v1111, 0, v1321);
                                *(_QWORD *)(v1300 + 40) = 0;
                              }
                              v1112 = GetProcessHeap();
                              HeapFree(v1112, 0, (LPVOID)v1300);
                              if ( (v1313 & 0x80000000) != 0LL )
                              {
LABEL_1393:
                                v1114 = GetProcessHeap();
                                HeapFree(v1114, 0, v1336);
                                v1115 = v1328;
                                if ( v1328 )
                                {
                                  v1321 = (_BYTE *)*((_QWORD *)v1328 + 1);
                                  if ( v1321 )
                                  {
                                    v1116 = GetProcessHeap();
                                    HeapFree(v1116, 0, v1321);
                                    v1115 = v1328;
                                    *((_QWORD *)v1328 + 1) = 0;
                                  }
                                  v1321 = (_BYTE *)v1115[3];
                                  if ( v1321 )
                                  {
                                    v1117 = GetProcessHeap();
                                    HeapFree(v1117, 0, v1321);
                                    v1115 = v1328;
                                    *((_QWORD *)v1328 + 3) = 0;
                                  }
                                  v1321 = (_BYTE *)v1115[5];
                                  if ( v1321 )
                                  {
                                    v1118 = GetProcessHeap();
                                    HeapFree(v1118, 0, v1321);
                                    *((_QWORD *)v1328 + 5) = 0;
                                  }
                                  v1119 = GetProcessHeap();
                                  HeapFree(v1119, 0, v1328);
                                }
                                if ( (v1313 & 0x80000000) != 0LL )
                                {
                                  v1299 = v1099;
                                  v1317 = v1313 | 0x10000000;
                                  goto LABEL_1409;
                                }
                                v1120 = *v1037;
                                LODWORD(v1298) = 0;
                                LODWORD(v1310) = 4;
                                v1317 = RtlUIntAdd(4, v1120, &v1310);
                                if ( v1317 < 0 )
                                  goto LABEL_1421;
                                v1317 = RtlUIntAdd((unsigned int)v1310, v1121, &v1310);
                                if ( v1317 < 0
                                  || (v1122 = v1037[4],
                                      v1333 = (SIZE_T)(v1037 + 4),
                                      v1317 = RtlUIntAdd((unsigned int)v1310, v1122, &v1310),
                                      v1317 < 0)
                                  || (v1317 = RtlUIntAdd((unsigned int)v1310, v1123, &v1310), v1317 < 0)
                                  || (v1124 = v1037[8],
                                      v1329 = (size_t)(v1037 + 8),
                                      v1317 = RtlUIntAdd((unsigned int)v1310, v1124, &v1310),
                                      v1317 < 0) )
                                {
LABEL_1421:
                                  v1299 = v1099;
                                }
                                else
                                {
                                  v1125 = v1310;
                                  v1126 = GetProcessHeap();
                                  v1127 = HeapAlloc(v1126, 8u, v1125);
                                  v1099 = v1299;
                                  v1312 = v1127;
                                  if ( !v1127 )
                                  {
                                    v1317 = -805306345;
LABEL_1409:
                                    v1128 = v1304;
                                    goto LABEL_1604;
                                  }
                                  *v1127 = *v1037;
                                  v1299 = v1099;
                                  v1300 = (SIZE_T)v1127;
                                  v1317 = RtlULongLongAdd(v1127, 4, &v1300);
                                  if ( v1317 < 0 )
                                  {
                                    LODWORD(v1309) = v1130;
                                    v1312 = v1129;
                                  }
                                  else
                                  {
                                    memcpy_0((void *)v1300, *((const void **)v1037 + 1), *v1037);
                                    v1317 = RtlULongLongAdd(v1300, *v1037, &v1300);
                                    if ( v1317 >= 0 )
                                    {
                                      v1131 = v1300;
                                      *(_DWORD *)v1300 = *(_DWORD *)v1333;
                                      v1317 = RtlULongLongAdd(v1131, 4, &v1300);
                                      if ( v1317 >= 0 )
                                      {
                                        memcpy_0((void *)v1300, *((const void **)v1037 + 3), *v1132);
                                        v1317 = RtlULongLongAdd(v1300, *(unsigned int *)v1333, &v1300);
                                        if ( v1317 >= 0 )
                                        {
                                          v1133 = v1300;
                                          *(_DWORD *)v1300 = *(_DWORD *)v1329;
                                          v1317 = RtlULongLongAdd(v1133, 4, &v1300);
                                          if ( v1317 >= 0 )
                                          {
                                            memcpy_0((void *)v1300, *((const void **)v1037 + 5), *v1134);
                                            v1135 = RtlULongLongAdd(v1300, *(unsigned int *)v1329, &v1300);
                                            v1317 = v1135;
                                            if ( v1135 >= 0 )
                                            {
                                              v1319 = v1312;
                                              LODWORD(v1298) = v1310;
LABEL_1423:
                                              LastError = v1135 | 0x10000000;
                                              if ( LastError < 0 )
                                                goto LABEL_1427;
                                              v1344 = 8;
                                              v1138 = RtlUIntAdd(8, (unsigned int)v1309, &v1344);
                                              LastError = v1139 | v1138;
                                              if ( LastError < 0 )
                                                goto LABEL_1427;
                                              v1140 = (v1344 + 7) & 0xFFFFFFF8;
                                              if ( (unsigned int)v1140 < v1344 )
                                              {
                                                LastError = -1073741675;
LABEL_1427:
                                                v1317 = LastError;
LABEL_1465:
                                                v1128 = v1304;
LABEL_1603:
                                                v1099 = v1299;
LABEL_1604:
                                                if ( !v1099 )
                                                {
LABEL_1606:
                                                  if ( v1037 )
                                                  {
                                                    v1269 = (void *)*((_QWORD *)v1037 + 1);
                                                    if ( v1269 )
                                                    {
                                                      v1270 = GetProcessHeap();
                                                      HeapFree(v1270, 0, v1269);
                                                      *((_QWORD *)v1037 + 1) = 0;
                                                    }
                                                    v1271 = (void *)*((_QWORD *)v1037 + 3);
                                                    if ( v1271 )
                                                    {
                                                      v1272 = GetProcessHeap();
                                                      HeapFree(v1272, 0, v1271);
                                                      *((_QWORD *)v1037 + 3) = 0;
                                                    }
                                                    v1273 = (void *)*((_QWORD *)v1037 + 5);
                                                    if ( v1273 )
                                                    {
                                                      v1274 = GetProcessHeap();
                                                      HeapFree(v1274, 0, v1273);
                                                      *((_QWORD *)v1037 + 5) = 0;
                                                    }
                                                    v1275 = GetProcessHeap();
                                                    HeapFree(v1275, 0, v1037);
                                                  }
                                                  v1276 = v1319;
                                                  if ( v1319 )
                                                  {
                                                    v1277 = GetProcessHeap();
                                                    HeapFree(v1277, 0, v1276);
                                                  }
                                                  if ( v1038 )
                                                  {
                                                    v1278 = GetProcessHeap();
                                                    HeapFree(v1278, 0, v1038);
                                                  }
                                                  v1279 = v1303;
                                                  if ( v1303 )
                                                  {
                                                    v1280 = (void *)*((_QWORD *)v1303 + 1);
                                                    if ( v1280 )
                                                    {
                                                      v1281 = GetProcessHeap();
                                                      HeapFree(v1281, 0, v1280);
                                                      v1279[1] = 0;
                                                    }
                                                    v1282 = (void *)v1279[3];
                                                    if ( v1282 )
                                                    {
                                                      v1283 = GetProcessHeap();
                                                      HeapFree(v1283, 0, v1282);
                                                      v1279[3] = 0;
                                                    }
                                                    v1284 = (void *)v1279[5];
                                                    if ( v1284 )
                                                    {
                                                      v1285 = GetProcessHeap();
                                                      HeapFree(v1285, 0, v1284);
                                                      v1279[5] = 0;
                                                    }
                                                    v1286 = GetProcessHeap();
                                                    HeapFree(v1286, 0, v1279);
                                                  }
                                                  if ( v1128 )
                                                  {
                                                    v1287 = GetProcessHeap();
                                                    HeapFree(v1287, 0, v1128);
                                                  }
                                                  goto LABEL_1628;
                                                }
LABEL_1605:
                                                v1268 = GetProcessHeap();
                                                HeapFree(v1268, 0, v1099);
                                                goto LABEL_1606;
                                              }
                                              v1346 = (v1344 + 7) & 0xFFFFFFF8;
                                              LastError = RtlUIntAdd(v1140, 8, &v1346);
                                              if ( LastError < 0 )
                                                goto LABEL_1427;
                                              v1141 = v1335[1];
                                              v1312 = v631;
                                              v1318 = v627;
                                              v1299 = v1099;
                                              Src = v1037;
                                              LODWORD(Size) = 0;
                                              if ( !v1335[1] )
                                                goto LABEL_1437;
                                              Src = v1037;
                                              v1299 = v1099;
                                              v1318 = v627;
                                              v1312 = v631;
                                              if ( LODWORD(v1335[0]) <= 1 )
                                                goto LABEL_1437;
                                              v1311 = v1335[1];
                                              do
                                              {
                                                LastError = RtlULongLongAdd(v1141, 4, &v1311);
                                                if ( LastError < 0 )
                                                  goto LABEL_1427;
                                                LastError = RtlULongLongAdd(v1311, v1142, &v1311);
                                                if ( LastError < 0 )
                                                  goto LABEL_1427;
                                                v1141 = v1311;
                                              }
                                              while ( v1143 == -1 );
                                              v1144 = *(_DWORD *)v1311;
                                              LastError = RtlULongLongAdd(v1311, 4, &v1311);
                                              if ( LastError < 0 )
                                                goto LABEL_1427;
                                              v1145 = v1335[1];
                                              if ( !v1335[1] || LODWORD(v1335[0]) <= 2 )
                                              {
LABEL_1437:
                                                LastError = -1073741811;
                                                goto LABEL_1427;
                                              }
                                              v1311 = v1335[1];
                                              do
                                              {
                                                LastError = RtlULongLongAdd(v1145, 4, &v1311);
                                                if ( LastError < 0 )
                                                  goto LABEL_1427;
                                                LastError = RtlULongLongAdd(v1311, v1148, &v1311);
                                                if ( LastError < 0 )
                                                  goto LABEL_1427;
                                                v1145 = v1311;
                                              }
                                              while ( (unsigned int)(v1149 + 1) < 2 );
                                              LastError = RtlULongLongAdd(v1311, 4, &v1311);
                                              if ( LastError < 0 )
                                                goto LABEL_1427;
                                              LODWORD(Size) = v1150;
                                              LODWORD(v1310) = v1151;
                                              LastError = RtlUIntAdd(v1151, v1346, &v1310);
                                              if ( LastError < 0 )
                                                goto LABEL_1427;
                                              LastError = RtlUIntAdd((unsigned int)v1310, v1152, &v1310);
                                              if ( LastError < 0 )
                                                goto LABEL_1427;
                                              LastError = RtlUIntAdd((unsigned int)v1310, v1144, &v1310);
                                              if ( LastError < 0 )
                                                goto LABEL_1427;
                                              LastError = RtlUIntAdd((unsigned int)v1310, v1153, &v1310);
                                              if ( LastError < 0 )
                                                goto LABEL_1427;
                                              LastError = RtlUIntAdd((unsigned int)v1310, v1154, &v1310);
                                              if ( LastError < 0 )
                                                goto LABEL_1427;
                                              LODWORD(Size) = v1310;
                                              if ( (unsigned int)v1310 > 0x400000 )
                                              {
                                                LastError = -2147418113;
                                                goto LABEL_1427;
                                              }
                                              v1146 = v1310;
                                              v1147 = GetProcessHeap();
                                              v1038 = HeapAlloc(v1147, 8u, v1146);
                                              if ( !v1038 )
                                              {
                                                v1317 = -805306345;
                                                v1128 = 0;
                                                goto LABEL_1603;
                                              }
                                              v1358 = 0;
                                              v1361 = 0;
                                              v1362 = 0;
                                              if ( !v1319 )
                                              {
                                                v1317 = -2147024809;
                                                goto LABEL_1465;
                                              }
                                              LODWORD(v1362) = v1298;
                                              *(_QWORD *)&v1361 = v1319;
                                              *(_QWORD *)((char *)&v1362 + 4) = (unsigned int)Size;
                                              *((_QWORD *)&v1361 + 1) = v1038;
                                              if ( GetModuleHandleExW(1u, L"ntdll.dll", &v1358)
                                                && (ProcAddress = GetProcAddress(v1358, "NtQuerySystemInformation")) != 0 )
                                              {
                                                LastError = ((__int64 (__fastcall *)(__int64, __int128 *))ProcAddress)(
                                                              134,
                                                              &v1361)
                                                          | 0x10000000;
                                                if ( LastError >= 0 )
                                                {
                                                  v1157 = DWORD1(v1362);
                                                  goto LABEL_1468;
                                                }
                                              }
                                              else
                                              {
                                                LastError = GetLastError();
                                                v1155 = LastError < 0;
                                                if ( LastError > 0 )
                                                {
                                                  LastError = (unsigned __int16)LastError | 0x80070000;
                                                  v1155 = LastError < 0;
                                                }
                                                if ( !v1155 )
                                                {
                                                  v1317 = -2147467259;
                                                  goto LABEL_1465;
                                                }
                                              }
                                              if ( LastError == -805306333 )
                                              {
                                                v1317 = -2147024774;
                                                goto LABEL_1465;
                                              }
                                              if ( LastError < 0 )
                                                goto LABEL_1427;
                                              v1157 = Size;
LABEL_1468:
                                              LODWORD(v1309) = 0;
                                              v1320 = v1038;
                                              if ( v1157 < 4 )
                                              {
LABEL_1469:
                                                v1317 = -805306306;
                                                goto LABEL_1465;
                                              }
                                              v1158 = (unsigned int)*v1038;
                                              LODWORD(v1298) = *v1038;
                                              v1159 = RtlULongLongAdd(v1038, 4, &v1320);
                                              if ( v1159 < 0 )
                                                goto LABEL_1521;
                                              v1159 = RtlUIntAdd(0, v1160, &v1309);
                                              if ( v1159 < 0 )
                                                goto LABEL_1521;
                                              if ( v1161 - (int)v1309 < (unsigned int)v1158 )
                                                goto LABEL_1469;
                                              v1329 = (size_t)v1320;
                                              v1333 = v1158;
                                              v1159 = RtlULongLongAdd(v1320, (unsigned int)v1158, &v1320);
                                              if ( v1159 < 0 )
                                                goto LABEL_1521;
                                              v1159 = RtlUIntAdd((unsigned int)v1309, (unsigned int)v1158, &v1309);
                                              if ( v1159 < 0 )
                                                goto LABEL_1521;
                                              if ( v1162 - (int)v1309 < (unsigned int)v1163 )
                                                goto LABEL_1469;
                                              LODWORD(Size) = *(_DWORD *)v1320;
                                              v1159 = RtlULongLongAdd(v1320, v1163, &v1320);
                                              if ( v1159 < 0 )
                                                goto LABEL_1521;
                                              v1159 = RtlUIntAdd((unsigned int)v1309, v1164, &v1309);
                                              if ( v1159 < 0 )
                                                goto LABEL_1521;
                                              if ( v1165 - (int)v1309 < (unsigned int)v1166 )
                                                goto LABEL_1469;
                                              pcchLength = (size_t)v1320;
                                              v1327 = v1166;
                                              v1159 = RtlULongLongAdd(v1320, (unsigned int)v1166, &v1320);
                                              if ( v1159 < 0 )
                                                goto LABEL_1521;
                                              v1159 = RtlUIntAdd((unsigned int)v1309, v1167, &v1309);
                                              if ( v1159 < 0 )
                                                goto LABEL_1521;
                                              if ( v1168 - (int)v1309 < v1169 )
                                                goto LABEL_1469;
                                              LODWORD(v1325) = *(_DWORD *)v1320;
                                              v1159 = RtlULongLongAdd(v1320, 4, &v1320);
                                              if ( v1159 < 0 )
                                                goto LABEL_1521;
                                              v1159 = RtlUIntAdd((unsigned int)v1309, 4, &v1309);
                                              if ( v1159 < 0 )
                                                goto LABEL_1521;
                                              if ( v1170 - (int)v1309 < v1171 )
                                                goto LABEL_1469;
                                              v1159 = RtlUIntAdd((unsigned int)v1309, v1171, &v1309);
                                              if ( v1159 < 0 )
                                              {
LABEL_1521:
                                                v1099 = v1299;
                                                v1192 = (unsigned int *)v1303;
                                                v1320 = v1038;
                                                goto LABEL_1522;
                                              }
                                              if ( v1172 != (_DWORD)v1309
                                                || (unsigned int)(v1158 + v1173 + v1174) + 12LL != v1172 )
                                              {
                                                goto LABEL_1469;
                                              }
                                              v1175 = GetProcessHeap();
                                              v1176 = HeapAlloc(v1175, 8u, 0x30u);
                                              v1099 = v1299;
                                              v1177 = (SIZE_T)v1176;
                                              v1300 = (SIZE_T)v1176;
                                              if ( !v1176 )
                                              {
                                                v1317 = -805306345;
                                                v1303 = 0;
                                                v1128 = 0;
                                                goto LABEL_1604;
                                              }
                                              v1312 = v631;
                                              v1318 = v627;
                                              Src = v1037;
                                              v1311 = 0;
                                              if ( v1329 )
                                              {
                                                *(_DWORD *)v1176 = v1298;
                                                v1178 = GetProcessHeap();
                                                v1179 = HeapAlloc(v1178, 8u, v1333);
                                                v1180 = (_QWORD *)v1300;
                                                if ( !v1179 )
                                                {
LABEL_1501:
                                                  v1186 = (_BYTE *)v1180[1];
                                                  LODWORD(v1313) = -1073741801;
                                                  v1320 = v1038;
                                                  v1321 = v1186;
                                                  if ( v1186 )
                                                  {
                                                    v1187 = GetProcessHeap();
                                                    HeapFree(v1187, 0, v1321);
                                                    v1180 = (_QWORD *)v1300;
                                                    *(_QWORD *)(v1300 + 8) = 0;
                                                  }
                                                  v1321 = (_BYTE *)v1180[3];
                                                  if ( v1321 )
                                                  {
                                                    v1188 = GetProcessHeap();
                                                    HeapFree(v1188, 0, v1321);
                                                    v1180 = (_QWORD *)v1300;
                                                    *(_QWORD *)(v1300 + 24) = 0;
                                                  }
                                                  v1321 = (_BYTE *)v1180[5];
                                                  if ( v1321 )
                                                  {
                                                    v1189 = GetProcessHeap();
                                                    HeapFree(v1189, 0, v1321);
                                                    *(_QWORD *)(v1300 + 40) = 0;
                                                  }
                                                  v1190 = GetProcessHeap();
                                                  HeapFree(v1190, 0, (LPVOID)v1300);
                                                  v1191 = (unsigned int *)v1311;
                                                  goto LABEL_1511;
                                                }
                                                *(_QWORD *)(v1300 + 8) = v1179;
                                                LODWORD(v1313) = 0;
                                                memcpy_0(v1179, (const void *)v1329, v1333);
                                                v1177 = v1300;
                                              }
                                              else
                                              {
                                                *(_DWORD *)v1176 = 0;
                                                v1176[1] = 0;
                                                LODWORD(v1313) = 0;
                                              }
                                              if ( pcchLength )
                                              {
                                                *(_DWORD *)(v1177 + 16) = Size;
                                                v1181 = GetProcessHeap();
                                                v1182 = HeapAlloc(v1181, 8u, v1327);
                                                v1180 = (_QWORD *)v1300;
                                                if ( !v1182 )
                                                {
LABEL_1500:
                                                  v1312 = v631;
                                                  v1318 = v627;
                                                  v1299 = v1099;
                                                  Src = v1037;
                                                  v1300 = (SIZE_T)v1180;
                                                  goto LABEL_1501;
                                                }
                                                *(_QWORD *)(v1300 + 24) = v1182;
                                                LODWORD(v1313) = 0;
                                                memcpy_0(v1182, (const void *)pcchLength, v1327);
                                                v1177 = v1300;
                                              }
                                              else
                                              {
                                                *(_DWORD *)(v1177 + 16) = 0;
                                                *(_QWORD *)(v1177 + 24) = 0;
                                              }
                                              if ( v1320 )
                                              {
                                                v1183 = (unsigned int)v1325;
                                                *(_DWORD *)(v1177 + 32) = v1325;
                                                v1333 = v1183;
                                                v1184 = GetProcessHeap();
                                                v1185 = HeapAlloc(v1184, 8u, v1333);
                                                v1180 = (_QWORD *)v1300;
                                                if ( !v1185 )
                                                  goto LABEL_1500;
                                                *(_QWORD *)(v1300 + 40) = v1185;
                                                LODWORD(v1313) = 0;
                                                memcpy_0(v1185, v1320, v1333);
                                                v1177 = v1300;
                                              }
                                              else
                                              {
                                                *(_DWORD *)(v1177 + 32) = 0;
                                                *(_QWORD *)(v1177 + 40) = 0;
                                              }
                                              v1191 = (unsigned int *)v1177;
                                              v1311 = v1177;
                                              v1320 = v1038;
                                              Src = v1037;
                                              v1299 = v1099;
                                              v1318 = v627;
                                              v1312 = v631;
LABEL_1511:
                                              v1159 = v1313;
                                              if ( (v1313 & 0x80000000) != 0LL )
                                              {
                                                v1192 = 0;
                                                v1303 = 0;
                                                if ( v1191 )
                                                {
                                                  v1321 = (_BYTE *)*((_QWORD *)v1191 + 1);
                                                  if ( v1321 )
                                                  {
                                                    v1193 = GetProcessHeap();
                                                    HeapFree(v1193, 0, v1321);
                                                    v1191 = (unsigned int *)v1311;
                                                    *(_QWORD *)(v1311 + 8) = 0;
                                                  }
                                                  v1321 = (_BYTE *)*((_QWORD *)v1191 + 3);
                                                  if ( v1321 )
                                                  {
                                                    v1194 = GetProcessHeap();
                                                    HeapFree(v1194, 0, v1321);
                                                    v1191 = (unsigned int *)v1311;
                                                    *(_QWORD *)(v1311 + 24) = 0;
                                                  }
                                                  v1321 = (_BYTE *)*((_QWORD *)v1191 + 5);
                                                  if ( v1321 )
                                                  {
                                                    v1195 = GetProcessHeap();
                                                    HeapFree(v1195, 0, v1321);
                                                    *(_QWORD *)(v1311 + 40) = 0;
                                                  }
                                                  v1196 = GetProcessHeap();
                                                  HeapFree(v1196, 0, (LPVOID)v1311);
                                                  v1159 = v1313;
                                                  v1192 = 0;
                                                  v1303 = 0;
                                                }
                                              }
                                              else
                                              {
                                                v1192 = v1191;
                                                v1303 = v1191;
                                              }
LABEL_1522:
                                              v1317 = v1159 | 0x10000000;
                                              if ( v1159 < 0 )
                                                goto LABEL_1465;
                                              if ( !v1192 || (v1336 = (void *)*((_QWORD *)v1192 + 1)) == 0 || !*v1192 )
                                              {
                                                v1317 = -805306355;
                                                goto LABEL_1465;
                                              }
                                              pcchLength = *v1192 - 8LL;
                                              v1304 = MemoryAlloc(pcchLength);
                                              v1197 = v1304;
                                              if ( !v1304 )
                                              {
LABEL_1554:
                                                v1317 = -805306367;
                                                v1128 = 0;
                                                goto LABEL_1603;
                                              }
                                              v1198 = pcchLength;
                                              v1199 = 0;
                                              v1200 = (unsigned __int8 *)v1336;
                                              uBytes_4 = 0;
                                              v1333 = pcchLength & 7;
                                              v1300 = 0x7F1137FAB69605ELL;
                                              v1329 = (size_t)v1336;
                                              v1327 = (SIZE_T)v1304;
                                              if ( (pcchLength & 7) != 0 )
                                              {
                                                v1332 = 0;
                                                LODWORD(Size) = 0;
                                                LODWORD(v1298) = 0;
                                                v1201 = 0;
                                                v1202 = 0;
                                                v1203 = 0;
                                                do
                                                {
                                                  v1204 = *v1200++;
                                                  LODWORD(v1313) = v1204;
                                                  LODWORD(v1298) = 8 * v1201;
                                                  if ( (unsigned int)v1201 >= 4 )
                                                  {
                                                    LODWORD(v1313) = (_DWORD)v1313 << (56 - v1298);
                                                    v1203 |= v1313;
                                                  }
                                                  else
                                                  {
                                                    LODWORD(v1313) = (_DWORD)v1313 << (24 - v1298);
                                                    v1202 |= v1313;
                                                  }
                                                  ++v1201;
                                                }
                                                while ( v1201 < (int)v1333 );
                                                LODWORD(Size) = v1202;
                                                v1205 = v1304;
                                                v1198 = pcchLength;
                                                v1332 = v1203;
                                                v1199 = uBytes_4;
                                                v1206 = v1333;
                                                v1329 = (size_t)v1200;
                                                v1320 = v1038;
                                                Src = v1037;
                                                v1299 = v1099;
                                                v1318 = v627;
                                                v1312 = v631;
                                                v1207 = Size ^ 0x92F65A5;
                                                v1208 = v1332 ^ 0x699A899C;
                                                LODWORD(v1298) = 0;
                                                v1209 = Size ^ 0x92F65A5;
                                                if ( (_DWORD)v1333 )
                                                {
                                                  v1210 = v1298;
                                                  v1211 = v1332 ^ 0x699A899C;
                                                  do
                                                  {
                                                    v1321 = v1205 + 1;
                                                    if ( v1210 >= 4 )
                                                    {
                                                      v1211 = __ROR4__(v1211, 24);
                                                      v1212 = v1211;
                                                    }
                                                    else
                                                    {
                                                      v1209 = __ROR4__(v1209, 24);
                                                      v1212 = v1209;
                                                    }
                                                    *v1205 = v1212;
                                                    ++v1210;
                                                    v1205 = v1321;
                                                  }
                                                  while ( (int)v1210 < (int)v1206 );
                                                  v1199 = uBytes_4;
                                                  v1327 = (SIZE_T)v1321;
                                                  v1197 = v1304;
                                                }
                                                if ( v1206 <= 4 )
                                                {
                                                  v1213 = 0;
                                                  if ( v1206 < 4 )
                                                    v1207 = v1207 >> (8 * (4 - v1206)) << (8 * (4 - v1206));
                                                }
                                                else
                                                {
                                                  v1213 = v1208 >> (8 * (8 - v1206)) << (8 * (8 - v1206));
                                                }
                                              }
                                              else
                                              {
                                                v1213 = 0;
                                                LODWORD(Size) = 0;
                                                v1207 = 0;
                                              }
                                              if ( v1198 >> 3 )
                                              {
                                                v1214 = HIDWORD(v1300);
                                                v1215 = v1198 >> 3;
                                                v1216 = WORD1(v1300);
                                                v1217 = (_BYTE *)v1327;
                                                v1218 = Size;
                                                v1219 = WORD2(v1300);
                                                LODWORD(v1313) = 24670;
                                                v1220 = (unsigned __int8 *)v1329;
                                                LODWORD(v1325) = WORD2(v1300);
                                                v1333 = 0;
                                                do
                                                {
                                                  v1221 = v1220[1];
                                                  v1222 = *v1220;
                                                  v1223 = v1220[4];
                                                  v1220 += 8;
                                                  v1224 = *(v1220 - 5)
                                                        | ((*(v1220 - 6) | ((v1221 | (v1222 << 8)) << 8)) << 8);
                                                  v1225 = v1207 ^ v1224;
                                                  v1226 = *(v1220 - 1)
                                                        | ((*(v1220 - 2) | ((*(v1220 - 3) | (v1223 << 8)) << 8)) << 8);
                                                  v1227 = v1213 ^ v1226 ^ v1214 ^ v1207 ^ v1224 ^ 0xAB69605E;
                                                  v1228 = v1225
                                                        ^ (__ROR4__(v1227, 22) + v1219
                                                                               * __ROR4__(v1227 + 1419157410, 27));
                                                  v1229 = v1227
                                                        ^ (v1216 * __ROR4__(v1228 + v1214, 9) - __ROR4__(v1228, 30));
                                                  v1230 = v1228 ^ (v1313 * (v1229 - v1219) - (v1229 >> 13));
                                                  v1231 = v1229
                                                        ^ (HIWORD(v1300) * __ROR4__(v1230 ^ v1216, 26)
                                                         - __ROR4__(v1230, 30));
                                                  v1232 = v1230 ^ (v1214 - (v1231 ^ 0xAB69605E));
                                                  v1233 = v1231 ^ (v1216 * (v1232 ^ v1219)) ^ __ROR4__(v1232, 6);
                                                  v1234 = v1232
                                                        ^ (__ROR4__(v1233, 30) + v1313 * __ROR4__(v1233 + v1214, 15));
                                                  v1235 = v1233
                                                        ^ (HIWORD(v1300) * __ROR4__(v1234 + 1419157410, 14)
                                                         - __ROR4__(v1234, 24));
                                                  v1236 = v1234
                                                        ^ __ROR4__(v1235, 10)
                                                        ^ (v1325 * __ROR4__(v1235 ^ 0xAB69605E, 12));
                                                  v1237 = v1236
                                                        ^ (HIWORD(v1300)
                                                         * (v1313
                                                          + __ROR4__(
                                                              ~(v1235
                                                              ^ (v1236 >> 10)
                                                              ^ (WORD1(v1300) * (v1236 ^ HIWORD(v1300)))),
                                                              5)));
                                                  v1238 = v1235
                                                        ^ (v1236 >> 10)
                                                        ^ (WORD1(v1300) * (v1236 ^ HIWORD(v1300)))
                                                        ^ (v1237 - HIWORD(v1300))
                                                        ^ 0xAB69605E;
                                                  v1239 = v1237
                                                        ^ ((v1238 >> 2) + v1325 * __ROR4__(HIWORD(v1300) ^ v1238, 30));
                                                  v1240 = v1238
                                                        ^ (__ROR4__(v1239, 25)
                                                         + WORD1(v1300) * __ROR4__(v1239 - v1214, 6));
                                                  v1241 = v1239 ^ (v1313 * (v1240 ^ v1325) + __ROR4__(v1240, 9));
                                                  v1242 = v1240
                                                        ^ (__ROR4__(v1241, 25)
                                                         + HIWORD(v1300) * __ROR4__(v1241 ^ WORD1(v1300), 27));
                                                  v1219 = v1325;
                                                  v1243 = v1214 ^ v1241 ^ v1242 ^ 0xAB69605E;
                                                  v1244 = v1242 ^ (v1325 * (__ROR4__(v1243, 3) - WORD1(v1300)));
                                                  v1245 = v1243
                                                        ^ (v1313 * __ROR4__(v1244 - v1214, 1) - __ROR4__(v1244, 6));
                                                  v1246 = v1244
                                                        ^ (__ROR4__(v1245, 18)
                                                         + HIWORD(v1300) * __ROR4__(v1245 - 1419157410, 29));
                                                  v1247 = v1245
                                                        ^ (v1325 * __ROR4__(v1246 - 1419157410, 17) - __ROR4__(v1246, 14));
                                                  v1216 = WORD1(v1300);
                                                  v1248 = v1246 ^ (v1247 >> 3) ^ (WORD1(v1300) * (v1247 ^ v1313));
                                                  v1213 = v1332 ^ v1248;
                                                  v1332 = v1226;
                                                  v1207 = v1218
                                                        ^ v1247
                                                        ^ __ROR4__(v1248, 30)
                                                        ^ (v1313 * __ROR4__(v1214 ^ v1248, 28));
                                                  v1218 = v1224;
                                                  v1217[3] = v1207;
                                                  v1217[7] = v1213;
                                                  v1217[2] = __ROR4__(v1207, 8);
                                                  v1217[6] = __ROR4__(v1213, 8);
                                                  v1217[1] = __ROR4__(v1207, 16);
                                                  v1217[5] = __ROR4__(v1213, 16);
                                                  *v1217 = __ROR4__(v1207, 24);
                                                  v1217[4] = __ROR4__(v1213, 24);
                                                  v1217 += 8;
                                                  ++v1333;
                                                }
                                                while ( v1333 < v1215 );
                                                v1199 = uBytes_4;
                                                v3 = v1302;
                                                v631 = v1312;
                                                v627 = v1318;
                                                v1038 = v1320;
                                                v1037 = (unsigned int *)Src;
                                                v1197 = v1304;
                                                v1198 = pcchLength;
                                              }
                                              for ( i = 0; i < v1198; ++i )
                                                v1199 ^= v1197[i];
                                              if ( v1199 != *(_QWORD *)((char *)v1336 + v1198) )
                                              {
                                                MemoryFree(v1197);
                                                goto LABEL_1554;
                                              }
                                              v1250 = v1299;
                                              v1251 = v1303;
                                              v1332 = 0;
                                              v1311 = (SIZE_T)v1197;
                                              if ( (unsigned int)v1198 < 4 )
                                              {
                                                v1128 = v1304;
                                                v1252 = -1073741762;
LABEL_1598:
                                                v1099 = v1250;
                                                goto LABEL_1599;
                                              }
                                              v1252 = RtlULongLongAdd(v1197, 4, &v1311);
                                              if ( v1252 >= 0 )
                                              {
                                                v1252 = RtlUIntAdd(0, 4, &v1332);
                                                if ( v1252 >= 0 )
                                                {
                                                  if ( v1254 - v1332 < 4 )
                                                    goto LABEL_1596;
                                                  v1255 = *(unsigned int *)v1311;
                                                  LODWORD(Size) = *(_DWORD *)v1311;
                                                  v1252 = RtlULongLongAdd(v1311, 4, &v1311);
                                                  if ( v1252 < 0 )
                                                    goto LABEL_1597;
                                                  v1252 = RtlUIntAdd(v1332, 4, &v1332);
                                                  if ( v1252 < 0 )
                                                    goto LABEL_1597;
                                                  if ( v1256 - v1332 < (unsigned int)v1255 )
                                                    goto LABEL_1596;
                                                  v1252 = RtlUIntAdd(v1332, (unsigned int)v1255, &v1332);
                                                  if ( v1252 >= 0 )
                                                  {
                                                    v1258 = v1257;
                                                    v1259 = (unsigned int *)v1311;
                                                    if ( (unsigned __int64)v1253 + v1258 >= v1255 + v1311
                                                      && (unsigned __int64)v1253 + v1258 - v1311 - v1255 < 8 )
                                                    {
                                                      v1332 = *v1253;
                                                      lpMem = 0;
                                                      v1333 = 0;
                                                      v1329 = 0;
                                                      LODWORD(v1325) = 0;
                                                      if ( v1311 )
                                                      {
                                                        v1317 = RtlULongLongAdd(v1311, (unsigned int)v1255, &lpMem);
                                                        v1252 = v1317;
                                                        v1303 = v1251;
                                                        v1299 = v1250;
                                                        if ( v1317 < 0 )
                                                        {
                                                          v1099 = v1250;
                                                          v1128 = v1260;
LABEL_1592:
                                                          v1267 = v1323;
LABEL_1593:
                                                          if ( v1252 >= 0 && v1332 != v1267 )
                                                            v1252 = -1073741762;
                                                          goto LABEL_1599;
                                                        }
                                                        v1261 = lpMem;
                                                        v1262 = v1259;
                                                        v1328 = v1259;
                                                        if ( v1259 < lpMem )
                                                        {
                                                          v1304 = v1260;
                                                          while ( 1 )
                                                          {
                                                            v1252 = RtlULongLongAdd(v1262, 4, &v1333);
                                                            if ( v1252 < 0 )
                                                              break;
                                                            if ( v1333 > (unsigned __int64)lpMem )
                                                            {
                                                              v1252 = -1073741811;
LABEL_1581:
                                                              v1099 = v1299;
                                                              v1128 = v1304;
                                                              goto LABEL_1599;
                                                            }
                                                            v1263 = *v1262;
                                                            LODWORD(v1298) = 0;
                                                            v1252 = RtlUIntAdd(4, v1263, &v1298);
                                                            if ( v1252 < 0 )
                                                              goto LABEL_1581;
                                                            v1321 = v631;
                                                            v1327 = (SIZE_T)v1251;
                                                            v1252 = RtlULongLongAdd(v1262, (unsigned int)v1298, &v1329);
                                                            v1303 = v1251;
                                                            v1317 = v1252;
                                                            v631 = v1321;
                                                            v1128 = v1260;
                                                            v1099 = v1250;
                                                            if ( v1252 < 0 )
                                                              goto LABEL_1592;
                                                            v1262 = (unsigned int *)v1329;
                                                            v1261 = lpMem;
                                                            v1328 = (LPVOID)v1329;
                                                            if ( v1329 > (unsigned __int64)lpMem )
                                                            {
                                                              v1252 = -1073741811;
                                                              v1303 = (LPVOID)v1327;
                                                              goto LABEL_1598;
                                                            }
                                                            LODWORD(v1325) = v1325 + 1;
                                                            v1251 = (void *)v1327;
                                                            v1304 = v1260;
                                                            v1303 = (LPVOID)v1327;
                                                            v1299 = v1250;
                                                            if ( v1329 >= (unsigned __int64)lpMem )
                                                            {
                                                              v1303 = (LPVOID)v1327;
                                                              goto LABEL_1577;
                                                            }
                                                          }
                                                          v1099 = v1299;
                                                          v1128 = v1304;
                                                          goto LABEL_1592;
                                                        }
LABEL_1577:
                                                        v1128 = v1260;
                                                        v1099 = v1250;
                                                        if ( v1328 != v1261 )
                                                        {
                                                          v1252 = -1073741811;
LABEL_1599:
                                                          v1317 = v1252 | 0x10000000;
                                                          goto LABEL_1604;
                                                        }
                                                      }
                                                      else
                                                      {
                                                        v1303 = v1251;
                                                        v1099 = v1250;
                                                        v1128 = v1253;
                                                        v1317 = 0;
                                                        v1299 = v1250;
                                                      }
                                                      v1264 = Size;
                                                      v1265 = 0;
                                                      v1333 = 0;
                                                      if ( (_DWORD)Size )
                                                      {
                                                        v1266 = GetProcessHeap();
                                                        v1333 = (SIZE_T)HeapAlloc(v1266, 8u, (unsigned int)Size);
                                                        v1265 = (void *)v1333;
                                                        if ( !v1333 )
                                                        {
                                                          v1252 = -1073741801;
                                                          goto LABEL_1599;
                                                        }
                                                        v1259 = (unsigned int *)v1311;
                                                        v1264 = Size;
                                                        v1317 = 0;
                                                      }
                                                      if ( v1259 )
                                                        memcpy_0(v1265, v1259, v1264);
                                                      v1252 = v1317;
                                                      v1308 = (LPVOID)v1333;
                                                      v1267 = v1325;
                                                      LODWORD(v1323) = v1325;
                                                      goto LABEL_1593;
                                                    }
LABEL_1596:
                                                    v1252 = -1073741762;
                                                  }
                                                }
                                              }
LABEL_1597:
                                              v1303 = v1251;
                                              v1128 = v1253;
                                              v1299 = v1250;
                                              goto LABEL_1598;
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                  v1299 = v1099;
                                  v1136 = GetProcessHeap();
                                  HeapFree(v1136, 0, v1312);
                                }
                                v1135 = v1317;
                                goto LABEL_1423;
                              }
LABEL_1392:
                              v1037 = (unsigned int *)v1328;
                              v1328 = 0;
                              goto LABEL_1393;
                            }
                            pcchLength = v1335[1];
                            if ( v1016 )
                            {
                              do
                              {
                                v1017 = *v1015;
                                LODWORD(v1298) = 0;
                                if ( (int)RtlUIntAdd(4, v1017, &v1298) < 0
                                  || (int)RtlULongLongAdd(v1018, (unsigned int)v1298, &pcchLength) < 0 )
                                {
                                  goto LABEL_1280;
                                }
                                v1015 = (unsigned int *)pcchLength;
                              }
                              while ( v1020 + 1 < v1019 );
                            }
                            if ( (int)RtlULongLongAdd(v1015, 4, &v1334) >= 0
                              && (unsigned __int64)(v1021 + 3) <= v1335[1] + HIDWORD(v1335[0]) )
                            {
                              v1022 = v1334;
                              v1023 = v1321;
                              *v1021 = 8;
                              *v1022 = v1023;
                              goto LABEL_1335;
                            }
LABEL_1280:
                            v628 = v1308;
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
                        v1302 = v3;
                        goto LABEL_810;
                      }
LABEL_988:
                      v781 = GetProcessHeap();
                      HeapFree(v781, 0, v1299);
                      goto LABEL_989;
                    }
                    v771 = (const void **)v1304;
                    LODWORD(v1298) = 0;
                    LODWORD(v1310) = 4;
                    v773 = RtlUIntAdd(4, *(unsigned int *)v1304, &v1310);
                    if ( v773 < 0 )
                      goto LABEL_1027;
                    v773 = RtlUIntAdd((unsigned int)v1310, v772, &v1310);
                    if ( v773 < 0
                      || (v774 = *((unsigned int *)v771 + 4),
                          v1329 = (size_t)(v771 + 2),
                          v773 = RtlUIntAdd((unsigned int)v1310, v774, &v1310),
                          v773 < 0)
                      || (v773 = RtlUIntAdd((unsigned int)v1310, v775, &v1310), v773 < 0)
                      || (v776 = *((unsigned int *)v771 + 8),
                          v1327 = (SIZE_T)(v771 + 4),
                          v773 = RtlUIntAdd((unsigned int)v1310, v776, &v1310),
                          v773 < 0) )
                    {
LABEL_1027:
                      v3 = v773 | 0x10000000;
                      v1302 = v3;
                      if ( v3 < 0 )
                        goto LABEL_985;
                      v1342 = 8;
                      v806 = RtlUIntAdd(8, (unsigned int)v1309, &v1342);
                      v3 = v806 | 0x10000000;
                      v1302 = v806 | 0x10000000;
                      if ( v806 < 0 )
                        goto LABEL_985;
                      v807 = (v1342 + 7) & 0xFFFFFFF8;
                      if ( (unsigned int)v807 < v1342 )
                      {
                        v3 = -1073741675;
                        goto LABEL_984;
                      }
                      v1347 = (v1342 + 7) & 0xFFFFFFF8;
                      v1302 = RtlUIntAdd(v807, 8, &v1347);
                      v3 = v1302;
                      if ( v1302 < 0 )
                        goto LABEL_985;
                      v809 = v1330[1];
                      v810 = 0;
                      v1326 = v22;
                      v1312 = v599;
                      v1318 = v600;
                      v1299 = v808;
                      v1304 = v771;
                      LODWORD(v1325) = 0;
                      if ( !v1330[1] )
                        goto LABEL_1040;
                      v1304 = v771;
                      v1299 = v808;
                      v1318 = v600;
                      v1312 = v599;
                      v1326 = v22;
                      if ( LODWORD(v1330[0]) > 1 )
                      {
                        v1311 = v1330[1];
                        while ( 1 )
                        {
                          v1302 = RtlULongLongAdd(v809, 4, &v1311);
                          v3 = v1302;
                          if ( v1302 < 0 )
                            break;
                          v1302 = RtlULongLongAdd(v1311, v811, &v1311);
                          v3 = v1302;
                          if ( v1302 < 0 )
                            break;
                          v809 = v1311;
                          if ( v812 != -1 )
                          {
                            v813 = *(_DWORD *)v1311;
                            v1302 = RtlULongLongAdd(v1311, 4, &v1311);
                            v3 = v1302;
                            if ( v1302 < 0 )
                              break;
                            v814 = v1330[1];
                            if ( v1330[1] && LODWORD(v1330[0]) > 2 )
                            {
                              v1311 = v1330[1];
                              while ( 1 )
                              {
                                v1302 = RtlULongLongAdd(v814, 4, &v1311);
                                v3 = v1302;
                                if ( v1302 < 0 )
                                  goto LABEL_1041;
                                v1302 = RtlULongLongAdd(v1311, v817, &v1311);
                                v3 = v1302;
                                if ( v1302 < 0 )
                                  goto LABEL_1041;
                                v814 = v1311;
                                if ( (unsigned int)(v818 + 1) >= 2 )
                                {
                                  v1302 = RtlULongLongAdd(v1311, 4, &v1311);
                                  v3 = v1302;
                                  if ( v1302 < 0 )
                                    goto LABEL_1041;
                                  LODWORD(v1325) = v810;
                                  LODWORD(v1310) = v819;
                                  v1302 = RtlUIntAdd(v819, v1347, &v1310);
                                  v3 = v1302;
                                  if ( v1302 < 0 )
                                    goto LABEL_1056;
                                  v1302 = RtlUIntAdd((unsigned int)v1310, v820, &v1310);
                                  v3 = v1302;
                                  if ( v1302 < 0
                                    || (v1302 = RtlUIntAdd((unsigned int)v1310, v813, &v1310), v3 = v1302, v1302 < 0)
                                    || (v1302 = RtlUIntAdd((unsigned int)v1310, v821, &v1310), v3 = v1302, v1302 < 0)
                                    || (v1302 = RtlUIntAdd((unsigned int)v1310, v822, &v1310), v3 = v1302, v1302 < 0) )
                                  {
LABEL_1056:
                                    if ( v3 < 0 )
                                      goto LABEL_985;
                                  }
                                  else
                                  {
                                    v810 = v1310;
                                    LODWORD(v1325) = v1310;
                                  }
                                  if ( v810 > 0x400000 )
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
                        v1302 = -1073741811;
                      }
LABEL_1041:
                      if ( v3 < 0 )
                        goto LABEL_985;
LABEL_1042:
                      v815 = v810;
                      v816 = GetProcessHeap();
                      v697 = HeapAlloc(v816, 8u, v815);
                      if ( !v697 )
                      {
                        v3 = -805306345;
                        v1302 = -805306345;
                        goto LABEL_986;
                      }
                      v1360 = 0;
                      v1367 = 0;
                      v1368 = 0;
                      if ( !dwBytes )
                      {
                        v3 = -2147024809;
LABEL_1071:
                        v1302 = v3;
                        goto LABEL_986;
                      }
                      LODWORD(v1368) = v1298;
                      *(_QWORD *)&v1367 = dwBytes;
                      *(_QWORD *)((char *)&v1368 + 4) = (unsigned int)v1325;
                      *((_QWORD *)&v1367 + 1) = v697;
                      if ( GetModuleHandleExW(1u, L"ntdll.dll", &v1360)
                        && (v824 = GetProcAddress(v1360, "NtQuerySystemInformation")) != 0 )
                      {
                        v825 = ((__int64 (__fastcall *)(__int64, __int128 *))v824)(134, &v1367);
                        v3 = v825 | 0x10000000;
                        v1302 = v825 | 0x10000000;
                        if ( v825 >= 0 )
                        {
                          v826 = DWORD1(v1368);
                          goto LABEL_1074;
                        }
                      }
                      else
                      {
                        v823 = GetLastError();
                        v1302 = v823;
                        v3 = v823;
                        if ( v823 > 0 )
                        {
                          v3 = (unsigned __int16)v823 | 0x80070000;
                          v1302 = v3;
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
                      v826 = v1325;
LABEL_1074:
                      LODWORD(v1309) = 0;
                      v1303 = v697;
                      if ( v826 < 4 )
                      {
LABEL_1075:
                        v3 = -805306306;
                        goto LABEL_1071;
                      }
                      LODWORD(v1298) = *v697;
                      v828 = RtlULongLongAdd(v697, 4, &v1303);
                      if ( v828 >= 0 )
                      {
                        v828 = RtlUIntAdd(0, v827, &v1309);
                        if ( v828 < 0 )
                        {
LABEL_1128:
                          v1303 = v697;
                          goto LABEL_1129;
                        }
                        if ( v830 - (int)v1309 < (unsigned int)v831 )
                          goto LABEL_1075;
                        v1329 = (size_t)v1303;
                        v1321 = v831;
                        v828 = RtlULongLongAdd(v1303, (unsigned int)v831, &v1303);
                        if ( v828 >= 0 )
                        {
                          v828 = RtlUIntAdd((unsigned int)v1309, v832, &v1309);
                          if ( v828 >= 0 )
                          {
                            if ( v833 - (int)v1309 < (unsigned int)v834 )
                              goto LABEL_1075;
                            LODWORD(v1325) = *(_DWORD *)v1303;
                            v828 = RtlULongLongAdd(v1303, v834, &v1303);
                            if ( v828 >= 0 )
                            {
                              v828 = RtlUIntAdd((unsigned int)v1309, v835, &v1309);
                              if ( v828 >= 0 )
                              {
                                if ( v836 - (int)v1309 < (unsigned int)v837 )
                                  goto LABEL_1075;
                                pcchLength = (size_t)v1303;
                                v1327 = v837;
                                v828 = RtlULongLongAdd(v1303, (unsigned int)v837, &v1303);
                                if ( v828 >= 0 )
                                {
                                  v828 = RtlUIntAdd((unsigned int)v1309, v838, &v1309);
                                  if ( v828 >= 0 )
                                  {
                                    if ( v839 - (int)v1309 < v840 )
                                      goto LABEL_1075;
                                    LODWORD(v1323) = *(_DWORD *)v1303;
                                    v828 = RtlULongLongAdd(v1303, 4, &v1303);
                                    if ( v828 >= 0 )
                                    {
                                      v828 = RtlUIntAdd((unsigned int)v1309, 4, &v1309);
                                      if ( v828 >= 0 )
                                      {
                                        if ( v841 - (int)v1309 < v842 )
                                          goto LABEL_1075;
                                        v828 = RtlUIntAdd((unsigned int)v1309, v842, &v1309);
                                        if ( v828 >= 0 )
                                        {
                                          if ( v843 != (_DWORD)v1309 )
                                            goto LABEL_1075;
                                          v846 = (unsigned int)v1298;
                                          if ( (unsigned int)(v1298 + v844 + v845) + 12LL != v843 )
                                            goto LABEL_1075;
                                          v847 = GetProcessHeap();
                                          v848 = (SIZE_T)HeapAlloc(v847, 8u, 0x30u);
                                          v1300 = v848;
                                          v780 = v1299;
                                          if ( !v848 )
                                          {
                                            v3 = -805306345;
                                            v1308 = 0;
                                            v1302 = -805306345;
                                            goto LABEL_987;
                                          }
                                          v1326 = v22;
                                          v1312 = v599;
                                          v1318 = v600;
                                          v1311 = 0;
                                          if ( v1329 )
                                          {
                                            *(_DWORD *)v848 = v846;
                                            v849 = GetProcessHeap();
                                            v850 = HeapAlloc(v849, 8u, v846);
                                            if ( !v850 )
                                            {
LABEL_1107:
                                              v858 = v1300;
                                              v828 = -1073741801;
                                              v1303 = v697;
                                              v1321 = *(_BYTE **)(v1300 + 8);
                                              if ( v1321 )
                                              {
                                                v859 = GetProcessHeap();
                                                HeapFree(v859, 0, v1321);
                                                v858 = v1300;
                                                *(_QWORD *)(v1300 + 8) = 0;
                                              }
                                              v1321 = *(_BYTE **)(v858 + 24);
                                              if ( v1321 )
                                              {
                                                v860 = GetProcessHeap();
                                                HeapFree(v860, 0, v1321);
                                                v858 = v1300;
                                                *(_QWORD *)(v1300 + 24) = 0;
                                              }
                                              v1321 = *(_BYTE **)(v858 + 40);
                                              if ( v1321 )
                                              {
                                                v861 = GetProcessHeap();
                                                HeapFree(v861, 0, v1321);
                                                *(_QWORD *)(v1300 + 40) = 0;
                                              }
                                              v862 = GetProcessHeap();
                                              HeapFree(v862, 0, (LPVOID)v1300);
                                              v863 = (unsigned int *)v1311;
                                              goto LABEL_1117;
                                            }
                                            *(_QWORD *)(v1300 + 8) = v850;
                                            v828 = 0;
                                            memcpy_0(v850, (const void *)v1329, (size_t)v1321);
                                            v848 = v1300;
                                          }
                                          else
                                          {
                                            *(_DWORD *)v848 = 0;
                                            v828 = 0;
                                            *(_QWORD *)(v848 + 8) = 0;
                                          }
                                          if ( pcchLength )
                                          {
                                            *(_DWORD *)(v848 + 16) = v1325;
                                            v851 = GetProcessHeap();
                                            v852 = HeapAlloc(v851, 8u, v1327);
                                            v853 = v1300;
                                            if ( !v852 )
                                            {
LABEL_1106:
                                              v1300 = v853;
                                              v1326 = v22;
                                              v1312 = v599;
                                              v1318 = v600;
                                              goto LABEL_1107;
                                            }
                                            *(_QWORD *)(v1300 + 24) = v852;
                                            v828 = 0;
                                            memcpy_0(v852, (const void *)pcchLength, v1327);
                                            v848 = v1300;
                                          }
                                          else
                                          {
                                            *(_DWORD *)(v848 + 16) = 0;
                                            *(_QWORD *)(v848 + 24) = 0;
                                          }
                                          if ( v1303 )
                                          {
                                            v854 = (unsigned int)v1323;
                                            *(_DWORD *)(v848 + 32) = v1323;
                                            v855 = v854;
                                            v1321 = (_BYTE *)v854;
                                            v856 = GetProcessHeap();
                                            v857 = HeapAlloc(v856, 8u, v855);
                                            v853 = v1300;
                                            if ( !v857 )
                                              goto LABEL_1106;
                                            *(_QWORD *)(v1300 + 40) = v857;
                                            v828 = 0;
                                            memcpy_0(v857, v1303, (size_t)v1321);
                                            v848 = v1300;
                                          }
                                          else
                                          {
                                            *(_DWORD *)(v848 + 32) = 0;
                                            *(_QWORD *)(v848 + 40) = 0;
                                          }
                                          v863 = (unsigned int *)v848;
                                          v1311 = v848;
                                          v1303 = v697;
                                          v1318 = v600;
                                          v1312 = v599;
                                          v1326 = v22;
LABEL_1117:
                                          if ( v828 < 0 )
                                          {
                                            v829 = 0;
                                            v1308 = 0;
                                            if ( v863 )
                                            {
                                              v1321 = (_BYTE *)*((_QWORD *)v863 + 1);
                                              if ( v1321 )
                                              {
                                                v864 = GetProcessHeap();
                                                HeapFree(v864, 0, v1321);
                                                v863 = (unsigned int *)v1311;
                                                *(_QWORD *)(v1311 + 8) = 0;
                                              }
                                              v1321 = (_BYTE *)*((_QWORD *)v863 + 3);
                                              if ( v1321 )
                                              {
                                                v865 = GetProcessHeap();
                                                HeapFree(v865, 0, v1321);
                                                v863 = (unsigned int *)v1311;
                                                *(_QWORD *)(v1311 + 24) = 0;
                                              }
                                              v1321 = (_BYTE *)*((_QWORD *)v863 + 5);
                                              if ( v1321 )
                                              {
                                                v866 = GetProcessHeap();
                                                HeapFree(v866, 0, v1321);
                                                *(_QWORD *)(v1311 + 40) = 0;
                                              }
                                              v867 = GetProcessHeap();
                                              HeapFree(v867, 0, (LPVOID)v1311);
                                              v829 = 0;
                                              v1308 = 0;
                                            }
                                          }
                                          else
                                          {
                                            v829 = v863;
                                            v1308 = v863;
                                          }
LABEL_1129:
                                          v3 = v828 | 0x10000000;
                                          v1302 = v3;
                                          if ( v3 < 0 )
                                            goto LABEL_986;
                                          if ( !v829 || (v1327 = *((_QWORD *)v829 + 1)) == 0 || !*v829 )
                                          {
                                            v3 = -805306355;
                                            goto LABEL_1071;
                                          }
                                          v868 = *v829 - 8LL;
                                          lpMem = (LPVOID)v868;
                                          v1314 = MemoryAlloc(v868);
                                          if ( !v1314 )
                                          {
LABEL_1161:
                                            v3 = -805306367;
                                            v1314 = 0;
                                            goto LABEL_1071;
                                          }
                                          v869 = 0;
                                          uBytes_4 = 0;
                                          v1300 = 0x7F1137FAB69605ELL;
                                          pcchLength = v1327;
                                          v1311 = (SIZE_T)v1314;
                                          v870 = v868 & 7;
                                          if ( (v868 & 7) != 0 )
                                          {
                                            v871 = 0;
                                            LODWORD(v1325) = 0;
                                            LODWORD(v1323) = 0;
                                            v872 = 0;
                                            v873 = 0;
                                            v874 = (unsigned __int8 *)pcchLength;
                                            do
                                            {
                                              v875 = *v874++;
                                              LODWORD(v1298) = 8 * v871;
                                              if ( v871 >= 4 )
                                                v872 |= v875 << (56 - v1298);
                                              else
                                                v873 |= v875 << (24 - v1298);
                                              ++v871;
                                            }
                                            while ( (int)v871 < (int)v870 );
                                            LODWORD(v1323) = v873;
                                            v869 = uBytes_4;
                                            LODWORD(v1325) = v872;
                                            pcchLength = (size_t)v874;
                                            v1303 = v697;
                                            v1318 = v600;
                                            v1312 = v599;
                                            v1326 = v22;
                                            v876 = v1323 ^ 0x92F65A5;
                                            v877 = v872 ^ 0x699A899C;
                                            v878 = 0;
                                            v879 = v1323 ^ 0x92F65A5;
                                            v880 = v872 ^ 0x699A899C;
                                            if ( (v868 & 7) != 0 )
                                            {
                                              v881 = (_BYTE *)v1311;
                                              do
                                              {
                                                v1321 = v881 + 1;
                                                if ( v878 >= 4 )
                                                {
                                                  v880 = __ROR4__(v880, 24);
                                                  v882 = v880;
                                                }
                                                else
                                                {
                                                  v879 = __ROR4__(v879, 24);
                                                  v882 = v879;
                                                }
                                                *v881 = v882;
                                                ++v878;
                                                v881 = v1321;
                                              }
                                              while ( (int)v878 < (int)v870 );
                                              v1311 = (SIZE_T)v1321;
                                            }
                                            if ( v870 <= 4 )
                                            {
                                              v883 = 0;
                                              if ( v870 < 4 )
                                                v876 = v876 >> (8 * (4 - v870)) << (8 * (4 - v870));
                                            }
                                            else
                                            {
                                              v883 = v877 >> (8 * (8 - v870)) << (8 * (8 - v870));
                                            }
                                          }
                                          else
                                          {
                                            v883 = 0;
                                            LODWORD(v1323) = 0;
                                            v876 = 0;
                                            LODWORD(v1325) = -1;
                                          }
                                          v884 = v868 >> 3;
                                          if ( v868 >> 3 )
                                          {
                                            v885 = HIDWORD(v1300);
                                            v886 = (unsigned __int8 *)pcchLength;
                                            v887 = HIDWORD(v1300) ^ 0xAB69605E;
                                            v888 = (_BYTE *)v1311;
                                            v889 = v1325;
                                            v890 = v1323;
                                            LODWORD(v1310) = WORD2(v1300);
                                            LODWORD(v1309) = 24670;
                                            v891 = v884;
                                            v1329 = 0;
                                            LODWORD(v1298) = HIDWORD(v1300) ^ 0xAB69605E;
                                            do
                                            {
                                              v892 = v886[1];
                                              v893 = *v886;
                                              v894 = v886[4];
                                              v886 += 8;
                                              v895 = *(v886 - 5) | ((*(v886 - 6) | ((v892 | (v893 << 8)) << 8)) << 8);
                                              v896 = v876 ^ v895;
                                              v897 = *(v886 - 1)
                                                   | ((*(v886 - 2) | ((*(v886 - 3) | (v894 << 8)) << 8)) << 8);
                                              v898 = v883 ^ v897 ^ v876 ^ v895 ^ v887;
                                              v899 = v896
                                                   ^ (__ROR4__(v898, 22) + v1310 * __ROR4__(v898 + 1419157410, 27));
                                              v900 = v898
                                                   ^ (WORD1(v1300) * __ROR4__(v885 + v899, 9) - __ROR4__(v899, 30));
                                              v901 = v899 ^ (v1309 * (v900 - v1310) - (v900 >> 13));
                                              v902 = v900
                                                   ^ (HIWORD(v1300) * __ROR4__(v901 ^ WORD1(v1300), 26)
                                                    - __ROR4__(v901, 30));
                                              v903 = v901 ^ (v885 - (v902 ^ 0xAB69605E));
                                              v904 = v902 ^ (WORD1(v1300) * (v903 ^ v1310)) ^ __ROR4__(v903, 6);
                                              v905 = v903 ^ (__ROR4__(v904, 30) + v1309 * __ROR4__(v904 + v885, 15));
                                              v906 = v904
                                                   ^ (HIWORD(v1300) * __ROR4__(v905 + 1419157410, 14)
                                                    - __ROR4__(v905, 24));
                                              v907 = v905
                                                   ^ __ROR4__(v906, 10)
                                                   ^ (v1310 * __ROR4__(v906 ^ 0xAB69605E, 12));
                                              v908 = v907
                                                   ^ (HIWORD(v1300)
                                                    * (v1309
                                                     + __ROR4__(
                                                         ~(v906 ^ (v907 >> 10) ^ (WORD1(v1300) * (v907 ^ HIWORD(v1300)))),
                                                         5)));
                                              v909 = v906
                                                   ^ (v907 >> 10)
                                                   ^ (WORD1(v1300) * (v907 ^ HIWORD(v1300)))
                                                   ^ (v908 - HIWORD(v1300))
                                                   ^ 0xAB69605E;
                                              v910 = v908 ^ ((v909 >> 2) + v1310 * __ROR4__(v909 ^ HIWORD(v1300), 30));
                                              v911 = v909
                                                   ^ (__ROR4__(v910, 25)
                                                    + WORD1(v1300) * __ROR4__(v910 - HIDWORD(v1300), 6));
                                              v912 = v910 ^ (v1309 * (v911 ^ v1310) + __ROR4__(v911, 9));
                                              v913 = v911
                                                   ^ (__ROR4__(v912, 25)
                                                    + HIWORD(v1300) * __ROR4__(v912 ^ WORD1(v1300), 27));
                                              v885 = HIDWORD(v1300);
                                              v914 = v1298 ^ v912 ^ v913;
                                              v915 = v913 ^ (v1310 * (__ROR4__(v914, 3) - WORD1(v1300)));
                                              v916 = v914
                                                   ^ (v1309 * __ROR4__(v915 - HIDWORD(v1300), 1) - __ROR4__(v915, 6));
                                              v887 = v1298;
                                              v917 = v915
                                                   ^ (__ROR4__(v916, 18)
                                                    + HIWORD(v1300) * __ROR4__(v916 - 1419157410, 29));
                                              v918 = v916
                                                   ^ (v1310 * __ROR4__(v917 - 1419157410, 17) - __ROR4__(v917, 14));
                                              v919 = v917 ^ (v918 >> 3) ^ (WORD1(v1300) * (v1309 ^ v918));
                                              v883 = v889 ^ v919;
                                              v889 = v897;
                                              v876 = v890
                                                   ^ v918
                                                   ^ __ROR4__(v919, 30)
                                                   ^ (v1309 * __ROR4__(HIDWORD(v1300) ^ v919, 28));
                                              v890 = v895;
                                              v888[3] = v876;
                                              v888[7] = v883;
                                              v888[2] = __ROR4__(v876, 8);
                                              v888[6] = __ROR4__(v883, 8);
                                              v888[1] = __ROR4__(v876, 16);
                                              v888[5] = __ROR4__(v883, 16);
                                              *v888 = __ROR4__(v876, 24);
                                              v888[4] = __ROR4__(v883, 24);
                                              v888 += 8;
                                              ++v1329;
                                            }
                                            while ( v1329 < v891 );
                                            v869 = uBytes_4;
                                            v22 = v1326;
                                            v599 = v1312;
                                            v600 = v1318;
                                            v697 = v1303;
                                            v868 = (unsigned __int64)lpMem;
                                          }
                                          for ( j = 0; j < v868; ++j )
                                            v869 ^= *((_BYTE *)v1314 + j);
                                          if ( v869 != *(_QWORD *)(v868 + v1327) )
                                          {
                                            MemoryFree(v1314);
                                            goto LABEL_1161;
                                          }
                                          LODWORD(v1310) = 0;
                                          v1311 = (SIZE_T)v1314;
                                          if ( (unsigned int)v868 < 4 )
                                          {
LABEL_1163:
                                            v921 = -1073741762;
LABEL_1176:
                                            v3 = v921 | 0x10000000;
                                            goto LABEL_1071;
                                          }
                                          v921 = RtlULongLongAdd(v1314, 4, &v1311);
                                          if ( v921 < 0 )
                                            goto LABEL_1174;
                                          v921 = RtlUIntAdd(0, 4, &v1310);
                                          if ( v921 < 0 )
                                            goto LABEL_1173;
                                          if ( (unsigned int)((_DWORD)lpMem - v1310) < 4 )
                                          {
                                            v926 = v1314;
LABEL_1168:
                                            v921 = -1073741762;
                                            v1314 = v926;
LABEL_1175:
                                            v1299 = v924;
                                            v1304 = v923;
                                            v1308 = v925;
                                            goto LABEL_1176;
                                          }
                                          LODWORD(v1325) = *(_DWORD *)v1311;
                                          v921 = RtlULongLongAdd(v1311, 4, &v1311);
                                          if ( v921 < 0 || (v921 = RtlUIntAdd((unsigned int)v1310, 4, &v1310), v921 < 0) )
                                          {
LABEL_1173:
                                            v922 = v1314;
LABEL_1174:
                                            v1314 = v922;
                                            goto LABEL_1175;
                                          }
                                          if ( (int)lpMem - (int)v1310 < (unsigned int)v1325 )
                                          {
                                            v921 = -1073741762;
                                            goto LABEL_1173;
                                          }
                                          v921 = RtlUIntAdd((unsigned int)v1310, (unsigned int)v1325, &v1310);
                                          if ( v921 < 0 )
                                            goto LABEL_1173;
                                          v926 = v1314;
                                          if ( (unsigned __int64)v1314 + (unsigned int)lpMem < (unsigned int)v1325
                                                                                             + v1311
                                            || (unsigned __int64)v1314
                                             + (unsigned int)lpMem
                                             - (unsigned int)v1325
                                             - v1311 >= 8 )
                                          {
                                            goto LABEL_1168;
                                          }
                                          LODWORD(v1309) = *(_DWORD *)v1314;
                                          v1319 = 0;
                                          v1329 = 0;
                                          v1327 = 0;
                                          LODWORD(v1323) = 0;
                                          if ( v1311 )
                                          {
                                            v921 = RtlULongLongAdd(v1311, (unsigned int)v1325, &v1319);
                                            v1308 = v928;
                                            v1304 = v929;
                                            v1299 = v930;
                                            if ( v921 < 0 )
                                            {
LABEL_1201:
                                              v943 = Size;
LABEL_1202:
                                              if ( v921 < 0 || (_DWORD)v1309 == v943 )
                                                goto LABEL_1176;
                                              goto LABEL_1163;
                                            }
                                            lpMem = v927;
                                            if ( v927 < v1319 )
                                            {
                                              while ( 1 )
                                              {
                                                v921 = RtlULongLongAdd(v927, 4, &v1329);
                                                if ( v921 < 0 )
                                                  goto LABEL_1201;
                                                if ( v1329 > (unsigned __int64)v1319 )
                                                  goto LABEL_1192;
                                                v932 = *v931;
                                                LODWORD(v1298) = 0;
                                                v921 = RtlUIntAdd(4, v932, &v1298);
                                                if ( v921 < 0 )
                                                  goto LABEL_1176;
                                                LODWORD(v1310) = v22;
                                                v933 = v599;
                                                v934 = v697;
                                                v935 = v1314;
                                                v1312 = v1314;
                                                v921 = RtlULongLongAdd(lpMem, (unsigned int)v1298, &v1327);
                                                v1314 = v935;
                                                v697 = v934;
                                                v1308 = v938;
                                                v599 = v933;
                                                v1304 = v936;
                                                v22 = v1310;
                                                v1299 = v937;
                                                if ( v921 < 0 )
                                                  goto LABEL_1201;
                                                v927 = (void *)v1327;
                                                v939 = v1319;
                                                lpMem = (LPVOID)v1327;
                                                v1308 = v938;
                                                v1304 = v936;
                                                v1299 = v937;
                                                v1314 = v1312;
                                                if ( v1327 > (unsigned __int64)v1319 )
                                                  goto LABEL_1192;
                                                LODWORD(v1323) = v1323 + 1;
                                                if ( v1327 >= (unsigned __int64)v1319 )
                                                {
                                                  v1314 = v1312;
                                                  v1308 = v938;
                                                  v1304 = v936;
                                                  v1299 = v937;
                                                  goto LABEL_1191;
                                                }
                                              }
                                            }
                                            v939 = v1319;
LABEL_1191:
                                            if ( v927 != v939 )
                                            {
LABEL_1192:
                                              v921 = -1073741811;
                                              goto LABEL_1176;
                                            }
                                          }
                                          else
                                          {
                                            v921 = 0;
                                            v1308 = v925;
                                            v1304 = v923;
                                            v1299 = v924;
                                          }
                                          v940 = v1325;
                                          v941 = 0;
                                          v1329 = 0;
                                          if ( (_DWORD)v1325 )
                                          {
                                            v942 = GetProcessHeap();
                                            v1329 = (size_t)HeapAlloc(v942, 8u, (unsigned int)v1325);
                                            v941 = (void *)v1329;
                                            if ( !v1329 )
                                            {
                                              v921 = -1073741801;
                                              goto LABEL_1176;
                                            }
                                            v940 = v1325;
                                            v921 = 0;
                                          }
                                          if ( v1311 )
                                            memcpy_0(v941, (const void *)v1311, v940);
                                          v1320 = (LPVOID)v1329;
                                          v943 = v1323;
                                          LODWORD(Size) = v1323;
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
                      v829 = (unsigned int *)v1308;
                      goto LABEL_1128;
                    }
                    v1304 = v771;
                    v777 = v1310;
                    v778 = GetProcessHeap();
                    v1312 = HeapAlloc(v778, 8u, v777);
                    v779 = v1312;
                    if ( !v1312 )
                    {
                      v3 = -805306345;
LABEL_984:
                      v1302 = v3;
LABEL_985:
                      v697 = v1303;
LABEL_986:
                      v780 = v1299;
                      goto LABEL_987;
                    }
                    v771 = (const void **)v1304;
                    v796 = v1299;
                    *(_DWORD *)v1312 = *(_DWORD *)v1304;
                    v1299 = v796;
                    v1300 = (SIZE_T)v779;
                    v773 = RtlULongLongAdd(v779, 4, &v1300);
                    if ( v773 < 0 )
                    {
                      v1299 = v798;
                      LODWORD(v1309) = v799;
                      v1312 = v797;
                    }
                    else
                    {
                      memcpy_0((void *)v1300, v771[1], *(unsigned int *)v771);
                      v773 = RtlULongLongAdd(v1300, *(unsigned int *)v771, &v1300);
                      if ( v773 >= 0 )
                      {
                        v800 = v1300;
                        *(_DWORD *)v1300 = *(_DWORD *)v1329;
                        v773 = RtlULongLongAdd(v800, 4, &v1300);
                        if ( v773 >= 0 )
                        {
                          memcpy_0((void *)v1300, v771[3], *v801);
                          v773 = RtlULongLongAdd(v1300, *(unsigned int *)v1329, &v1300);
                          if ( v773 >= 0 )
                          {
                            v802 = v1300;
                            *(_DWORD *)v1300 = *(_DWORD *)v1327;
                            v773 = RtlULongLongAdd(v802, 4, &v1300);
                            if ( v773 >= 0 )
                            {
                              memcpy_0((void *)v1300, v771[5], *v803);
                              v804 = RtlULongLongAdd(v1300, *(unsigned int *)v1327, &v1300);
                              v1304 = v771;
                              v773 = v804;
                              if ( v804 >= 0 )
                              {
                                dwBytes = (SIZE_T)v1312;
                                LODWORD(v1298) = v1310;
                                goto LABEL_1027;
                              }
LABEL_1026:
                              v805 = GetProcessHeap();
                              HeapFree(v805, 0, v1312);
                              goto LABEL_1027;
                            }
                          }
                        }
                      }
                    }
                    v1304 = v771;
                    goto LABEL_1026;
                  }
                }
              }
              v751 = -1073741801;
              v766 = v1328;
              v1321 = (_BYTE *)*((_QWORD *)v1328 + 1);
              if ( v1321 )
              {
                v767 = GetProcessHeap();
                HeapFree(v767, 0, v1321);
                v766 = v1328;
                *((_QWORD *)v1328 + 1) = 0;
              }
              v1321 = (_BYTE *)v766[3];
              if ( v1321 )
              {
                v768 = GetProcessHeap();
                HeapFree(v768, 0, v1321);
                v766 = v1328;
                *((_QWORD *)v1328 + 3) = 0;
              }
              v1321 = (_BYTE *)v766[5];
              if ( v1321 )
              {
                v769 = GetProcessHeap();
                HeapFree(v769, 0, v1321);
                *((_QWORD *)v1328 + 5) = 0;
              }
              v770 = GetProcessHeap();
              HeapFree(v770, 0, v1328);
            }
            else
            {
              v751 = -1073741801;
            }
            v752 = v1304;
            goto LABEL_954;
          }
          pcchLength = v1330[1];
          if ( v677 )
          {
            do
            {
              v678 = *v676;
              LODWORD(v1298) = 0;
              v615 = RtlUIntAdd(4, v678, &v1298);
              if ( v615 < 0 )
                goto LABEL_809;
              v615 = RtlULongLongAdd(v679, (unsigned int)v1298, &pcchLength);
              if ( v615 < 0 )
                goto LABEL_809;
              v676 = (unsigned int *)pcchLength;
            }
            while ( v681 + 1 < v680 );
          }
          v615 = RtlULongLongAdd(v676, 4, &v1322);
          if ( v615 >= 0 )
          {
            if ( (unsigned __int64)(v682 + 2) <= v1330[1] + HIDWORD(v1330[0]) )
            {
              v683 = v1322;
              *v682 = 4;
              *v683 = uBytes;
              goto LABEL_903;
            }
LABEL_805:
            v615 = -1073741789;
          }
LABEL_809:
          v1302 = v615;
          v3 = v615;
          goto LABEL_810;
        }
        *v313 = `WarbirdUmGetDecryptionKey'::`2'::nDecryptionKey;
        v1316 = __rdtsc();
        v315 = GetProcessHeap();
        v316 = HeapAlloc(v315, 8u, 0xC4u);
        v22 = v1310;
        uBytes = v1313;
        if ( !v316 )
          goto LABEL_777;
        dwBytes = 0;
        v1321 = 0;
        LODWORD(v1322) = 0;
        if ( (int)RtlULongLongAdd(v316, 4, &v1322) >= 0 )
        {
          if ( v316 + 2 > v316 + 49 )
            goto LABEL_773;
          v318 = v1322;
          *v316 = 4;
          uBytes = v317;
          *v318 = 4;
          v1321 = 0;
          LODWORD(v1322) = 0;
          v319 = v316;
          LODWORD(v1298) = 8;
          for ( lpMem = v316; ; v319 = lpMem )
          {
            if ( *v319 >= 0xFFFFFFFC )
              goto LABEL_770;
            if ( (int)RtlULongLongAdd(v319, (unsigned int)(*v319 + 4), &lpMem) < 0 )
              goto LABEL_773;
            if ( v320 != -1 )
              break;
          }
          if ( (int)RtlULongLongAdd(lpMem, 4, &v1322) >= 0 && v321 + 41 <= v316 + 49 )
          {
            *v321 = 160;
            if ( v311 )
            {
              memcpy_0(v1322, v311, 0xA0u);
              v317 = uBytes;
              v322 = v1298;
            }
            uBytes = v317;
            v1303 = v314;
            v1321 = 0;
            LODWORD(v1313) = 2;
            LODWORD(v1322) = 0;
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
            LODWORD(v1298) = 0;
            do
            {
              if ( *v323 >= 0xFFFFFFFC )
                goto LABEL_770;
              if ( (int)RtlULongLongAdd(v323, (unsigned int)(*v323 + 4), &lpMem) < 0 )
                goto LABEL_773;
              v323 = lpMem;
              LODWORD(v1298) = v1298 + 1;
            }
            while ( (unsigned int)v1298 < v324 );
            if ( (int)RtlULongLongAdd(lpMem, 4, &v1322) >= 0
              && (char *)v325 + v327 + 4 <= (char *)v316 + (unsigned int)v1328 )
            {
              *v325 = v327;
              if ( v314 )
              {
                memcpy_0(v1322, v314, v327);
                v326 = v1313;
              }
              v1321 = 0;
              LODWORD(v1322) = 0;
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
              if ( (int)RtlULongLongAdd(v328, 4, &v1322) >= 0
                && v331 + 3 <= (_DWORD *)((char *)v316 + (unsigned int)v1328) )
              {
                v333 = v1322;
                v334 = v1316;
                *v331 = 8;
                *v333 = v334;
                LODWORD(v1313) = v332 + 1;
                v1316 = __rdtsc();
                if ( (unsigned int)v1328 >= 0xFFFFFFF8 )
                  goto LABEL_770;
                v1319 = (void *)(((_DWORD)v1328 + 15) & 0xFFFFFFF8);
                if ( (unsigned int)v1319 < (int)v1328 + 8 )
                  goto LABEL_770;
                LODWORD(v1325) = 0;
                v1327 = ((_DWORD)v1328 + 15) & 0xFFFFFFF8;
                v335 = GetProcessHeap();
                Src = HeapAlloc(v335, 8u, v1327);
                v336 = Src;
                if ( !Src )
                {
                  v337 = -805306345;
                  goto LABEL_560;
                }
                *(_DWORD *)Src = v1313;
                v1303 = v314;
                v1299 = 0;
                lpMem = 0;
                v1308 = 0;
                v1304 = 0;
                v1314 = 0;
                v1311 = (SIZE_T)v336;
                v338 = RtlULongLongAdd(v336, 4, &v1311);
                if ( v338 < 0
                  || (v341 = v1311, *(_DWORD *)v1311 = (_DWORD)v1328, v338 = RtlULongLongAdd(v341, 4, &v1311), v338 < 0) )
                {
                  v1327 = v339;
                  uBytes = v340;
                  Src = 0;
                  LODWORD(v1319) = 0;
                  v343 = GetProcessHeap();
                  HeapFree(v343, 0, (LPVOID)v1327);
                }
                else
                {
                  *(_QWORD *)(v339 + v1327 - 8) = v1316;
                  memcpy_0((void *)v1311, v316, v342);
                }
                v337 = v338 | 0x10000000;
                if ( v337 < 0 )
                  goto LABEL_536;
                if ( !Src )
                  goto LABEL_769;
                v344 = (unsigned int)v1319;
                if ( !(_DWORD)v1319
                  || (v1311 = (unsigned int)v1319 + 8LL, v1309 = (SIZE_T)MemoryAlloc(v1311), (v345 = v1309) == 0) )
                {
                  v337 = -805306367;
                  goto LABEL_537;
                }
                v346 = 0;
                uBytes_4 = 0;
                v347 = 0;
                v1312 = 0;
                if ( v344 )
                {
                  do
                    v346 ^= *((_BYTE *)Src + v347++);
                  while ( v347 < v344 );
                  uBytes_4 = v346;
                }
                v348 = v1303;
                v1326 = v22;
                v1328 = v311;
                v1320 = v316;
                v1318 = (void *)0xC81ECB17B1B54A58LL;
                v1316 = (unsigned __int64)(unsigned int)v1319 >> 3;
                if ( v1316 )
                {
                  v349 = (_BYTE *)v1309;
                  v350 = (unsigned __int8 *)Src;
                  v351 = WORD2(v1318);
                  v352 = v1316;
                  v353 = -1;
                  LODWORD(v1310) = WORD1(v1318);
                  v354 = 0;
                  v355 = HIDWORD(v1318) ^ 0xB1B54A58;
                  v1327 = 0;
                  LODWORD(v1298) = 0;
                  LODWORD(Size) = 0;
                  do
                  {
                    v356 = v350[1];
                    v357 = *v350;
                    v358 = v350[4];
                    v350 += 8;
                    v359 = *(v350 - 5) | ((*(v350 - 6) | ((v356 | (v357 << 8)) << 8)) << 8);
                    v360 = *(v350 - 1) | ((*(v350 - 2) | ((*(v350 - 3) | (v358 << 8)) << 8)) << 8);
                    v361 = v354 ^ v359 ^ ((v353 ^ v360) - 19032);
                    v362 = __ROR4__(v361, 15);
                    v363 = HIDWORD(v1318) ^ v361;
                    v364 = v353 ^ v360 ^ (__ROR4__(v363, 7) + WORD1(v1318) * v362);
                    v365 = v363 ^ (v351 * __ROR4__(v364 - 1313519016, 9) - __ROR4__(v364, 10));
                    v366 = v364 ^ (__ROR4__(v365, 27) + HIWORD(v1318) * __ROR4__(v365 ^ v351, 28));
                    v367 = v365 ^ (HIDWORD(v1318) - (v366 ^ 0xB1B54A58));
                    v368 = v366 ^ (WORD1(v1318) * (v367 - 19032) - (v367 >> 6));
                    v369 = v367 ^ (19032 * (v351 ^ __ROR4__(v368, 15)));
                    v370 = v368 ^ (v351 * (HIWORD(v1318) + __ROR4__(~v369, 3)));
                    v371 = v369 ^ (v370 - 19032 - HIDWORD(v1318));
                    v372 = v370 ^ (v1310 * (HIWORD(v1318) ^ v371)) ^ __ROR4__(v371, 10);
                    v373 = v371 ^ __ROR4__(v372, 3) ^ (v351 * __ROR4__(v372 ^ 0x4A58, 26));
                    v374 = v372 ^ (19032 * (__ROR4__(v373, 15) - HIWORD(v1318)));
                    v375 = v373
                         ^ (19032 * (HIWORD(v1318) ^ v374))
                         ^ ((v374 ^ (v374 >> 14)) >> 1)
                         ^ (19032 * ((8 * (v374 - v351)) | ((v374 - v351) >> 29)));
                    v376 = v374 ^ (WORD1(v1318) * (v375 - v351) - (v375 >> 13));
                    v377 = v375 ^ __ROR4__(v376, 11) ^ (v351 * __ROR4__(-1313519016 - v376, 9));
                    v378 = v376 ^ (v377 + 1313519016 - HIWORD(v1318));
                    v379 = v377 ^ (19032 * (v378 ^ WORD1(v1318)) - __ROR4__(v378, 7));
                    v380 = v378 ^ (WORD1(v1318) * __ROR4__(HIWORD(v1318) ^ v379, 28) - __ROR4__(v379, 16));
                    v381 = v379 ^ (__ROR4__(v380, 4) + v351 * __ROR4__(-1313519016 - v380, 10));
                    v382 = v380 ^ __ROR4__(v381, 9) ^ (HIWORD(v1318) * __ROR4__(v381 + 1313519016, 4));
                    v383 = v381 ^ (19032 * __ROR4__(HIDWORD(v1318) ^ v382, 24) - __ROR4__(v382, 30));
                    v384 = v382 ^ (WORD1(v1318) * __ROR4__(HIDWORD(v1318) - v383, 11) - __ROR4__(v383, 12));
                    v385 = v383 ^ (v384 >> 8) ^ (v351 * (v384 ^ WORD1(v1318)));
                    v386 = v1298 ^ v385;
                    LOBYTE(v369) = __ROR4__(v1298 ^ v385, 8);
                    v353 = v384 ^ Size ^ v385 ^ v355;
                    v349[3] = v1298 ^ v385;
                    v354 = v386;
                    v349[7] = v353;
                    v349[2] = v369;
                    v349[6] = __ROR4__(v353, 8);
                    v349[1] = __ROR4__(v386, 16);
                    v349[5] = __ROR4__(v353, 16);
                    *v349 = __ROR4__(v386, 24);
                    v349[4] = __ROR4__(v353, 24);
                    v349 += 8;
                    LODWORD(v1323) = v386;
                    LODWORD(v1298) = v359;
                    LODWORD(Size) = v360;
                    ++v1327;
                  }
                  while ( v1327 < v352 );
                  v346 = uBytes_4;
                  v3 = v1302;
                  v22 = v1326;
                  v316 = v1320;
                  v311 = v1328;
                  v348 = v1303;
                  v345 = v1309;
                }
                *(_QWORD *)(v345 + (unsigned int)v1319) = v346;
                v387 = GetProcessHeap();
                v1300 = (SIZE_T)HeapAlloc(v387, 8u, 0x30u);
                if ( v1300 )
                {
                  v1303 = v348;
                  v397 = v1300;
                  *(_DWORD *)v1300 = v1311;
                  v398 = GetProcessHeap();
                  v399 = HeapAlloc(v398, 8u, (unsigned int)v1311);
                  if ( v399 )
                  {
                    *(_QWORD *)(v397 + 8) = v399;
                    memcpy_0(v399, (const void *)v1309, (unsigned int)v1311);
                    *(_DWORD *)(v397 + 16) = 160;
                    v400 = GetProcessHeap();
                    v401 = HeapAlloc(v400, 8u, 0xA0u);
                    if ( v401 )
                    {
                      *(_QWORD *)(v397 + 24) = v401;
                      *v401 = `WarbirdUmGetEncryptionCipher'::`2'::EncryptionCipher;
                      v401[1] = xmmword_18012E4F0;
                      v401[2] = xmmword_18012E500;
                      v401[3] = xmmword_18012E510;
                      v401[4] = xmmword_18012E520;
                      v401[5] = xmmword_18012E530;
                      v401[6] = xmmword_18012E540;
                      v401[7] = xmmword_18012E550;
                      v401[8] = xmmword_18012E560;
                      v401[9] = xmmword_18012E570;
                      *(_DWORD *)(v397 + 32) = 8;
                      v402 = GetProcessHeap();
                      v403 = HeapAlloc(v402, 8u, 8u);
                      if ( v403 )
                      {
                        *(_QWORD *)(v397 + 40) = v403;
                        *v403 = `WarbirdUmGetEncryptionKey'::`2'::nEncryptionKey;
                        v1312 = (LPVOID)v397;
                        v388 = 0;
                        v389 = v1312;
                        v1312 = 0;
LABEL_507:
                        v1299 = v389;
                        v390 = GetProcessHeap();
                        HeapFree(v390, 0, (LPVOID)v1309);
                        v391 = v1312;
                        if ( v1312 )
                        {
                          v1316 = *((_QWORD *)v1312 + 1);
                          if ( v1316 )
                          {
                            v392 = GetProcessHeap();
                            HeapFree(v392, 0, (LPVOID)v1316);
                            v391 = v1312;
                            *((_QWORD *)v1312 + 1) = 0;
                          }
                          v1316 = v391[3];
                          if ( v1316 )
                          {
                            v393 = GetProcessHeap();
                            HeapFree(v393, 0, (LPVOID)v1316);
                            v391 = v1312;
                            *((_QWORD *)v1312 + 3) = 0;
                          }
                          v1316 = v391[5];
                          if ( v1316 )
                          {
                            v394 = GetProcessHeap();
                            HeapFree(v394, 0, (LPVOID)v1316);
                            *((_QWORD *)v1312 + 5) = 0;
                          }
                          v395 = GetProcessHeap();
                          HeapFree(v395, 0, v1312);
                          v396 = (unsigned int *)v1299;
                        }
                        else
                        {
                          v396 = (unsigned int *)v1299;
                        }
                        v337 = v388 | 0x10000000;
                        if ( v337 < 0 )
                          goto LABEL_536;
                        v409 = *v396;
                        LODWORD(Size) = 0;
                        LODWORD(v1310) = 4;
                        v410 = RtlUIntAdd(4, v409, &v1310);
                        if ( v410 < 0 )
                          goto LABEL_587;
                        v410 = RtlUIntAdd((unsigned int)v1310, v411, &v1310);
                        if ( v410 < 0 )
                          goto LABEL_587;
                        v413 = *(unsigned int *)(v412 + 16);
                        v1327 = v412 + 16;
                        v410 = RtlUIntAdd((unsigned int)v1310, v413, &v1310);
                        if ( v410 < 0 )
                          goto LABEL_587;
                        v410 = RtlUIntAdd((unsigned int)v1310, v414, &v1310);
                        if ( v410 < 0 )
                          goto LABEL_587;
                        v416 = *(unsigned int *)(v415 + 32);
                        pcchLength = v415 + 32;
                        v410 = RtlUIntAdd((unsigned int)v1310, v416, &v1310);
                        if ( v410 < 0 )
                          goto LABEL_587;
                        v418 = v1310;
                        v1299 = v417;
                        v419 = GetProcessHeap();
                        v1312 = HeapAlloc(v419, 8u, v418);
                        v420 = v1312;
                        if ( !v1312 )
                        {
LABEL_535:
                          v337 = -805306345;
                          goto LABEL_536;
                        }
                        v444 = v1303;
                        v445 = Src;
                        *(_DWORD *)v1312 = *(_DWORD *)v1299;
                        v1303 = v444;
                        Src = v445;
                        v1300 = (SIZE_T)v420;
                        v410 = RtlULongLongAdd(v420, 4, &v1300);
                        if ( v410 < 0 )
                        {
                          v1299 = v449;
                          Src = v448;
                          v1303 = v447;
                          v1312 = v446;
                          goto LABEL_586;
                        }
                        memcpy_0((void *)v1300, v449[1], *(unsigned int *)v449);
                        v410 = RtlULongLongAdd(v1300, *(unsigned int *)v1299, &v1300);
                        if ( v410 < 0
                          || (v451 = v1300,
                              *(_DWORD *)v1300 = *(_DWORD *)v1327,
                              v410 = RtlULongLongAdd(v451, 4, &v1300),
                              v410 < 0) )
                        {
                          v1299 = v450;
                          goto LABEL_586;
                        }
                        memcpy_0((void *)v1300, v450[3], *v452);
                        v410 = RtlULongLongAdd(v1300, *(unsigned int *)v1327, &v1300);
                        if ( v410 < 0 )
                        {
                          v455 = v1299;
                        }
                        else
                        {
                          v453 = v1300;
                          *(_DWORD *)v1300 = *(_DWORD *)pcchLength;
                          v410 = RtlULongLongAdd(v453, 4, &v1300);
                          v455 = v1299;
                          if ( v410 >= 0 )
                          {
                            memcpy_0((void *)v1300, *((const void **)v1299 + 5), *v454);
                            v410 = RtlULongLongAdd(v1300, *(unsigned int *)pcchLength, &v1300);
                            if ( v410 >= 0 )
                            {
                              lpMem = v1312;
                              LODWORD(Size) = v1310;
                              goto LABEL_587;
                            }
LABEL_586:
                            v456 = GetProcessHeap();
                            HeapFree(v456, 0, v1312);
LABEL_587:
                            v337 = v410 | 0x10000000;
                            if ( v337 >= 0 )
                            {
                              v1341 = 8;
                              v457 = RtlUIntAdd(8, 20, &v1341);
                              v337 = v457 | 0x10000000;
                              if ( v457 >= 0 )
                              {
                                v458 = (v1341 + 7) & 0xFFFFFFF8;
                                if ( (unsigned int)v458 < v1341 )
                                {
                                  v337 = -1073741675;
                                  goto LABEL_536;
                                }
                                v1348 = (v1341 + 7) & 0xFFFFFFF8;
                                v337 = RtlUIntAdd(v458, 8, &v1348);
                                if ( v337 >= 0 )
                                {
                                  v1326 = v22;
                                  v1328 = v311;
                                  v1303 = v459;
                                  Src = v460;
                                  v1299 = v461;
                                  LODWORD(v1323) = 0;
                                  v1320 = v316;
                                  if ( !v316 )
                                    goto LABEL_600;
                                  v1299 = v461;
                                  Src = v460;
                                  v1303 = v459;
                                  v1328 = v311;
                                  v1326 = v22;
                                  if ( (unsigned int)v1313 <= 1 )
                                    goto LABEL_600;
                                  v462 = (SIZE_T)v316;
                                  LODWORD(v1298) = 0;
                                  v1311 = (SIZE_T)v316;
                                  v463 = 4;
                                  do
                                  {
                                    v337 = RtlULongLongAdd(v462, v463, &v1311);
                                    if ( v337 < 0 )
                                      goto LABEL_536;
                                    v337 = RtlULongLongAdd(v1311, v464, &v1311);
                                    if ( v337 < 0 )
                                      goto LABEL_536;
                                    v462 = v1311;
                                    LODWORD(v1298) = v1298 + 1;
                                  }
                                  while ( !(_DWORD)v1298 );
                                  v337 = RtlULongLongAdd(v1311, v463, &v1311);
                                  if ( v337 >= 0 )
                                  {
                                    if ( (unsigned int)v1313 <= 2 )
                                    {
LABEL_600:
                                      v337 = -1073741811;
                                      goto LABEL_536;
                                    }
                                    v468 = (SIZE_T)v316;
                                    v1311 = (SIZE_T)v316;
                                    do
                                    {
                                      v337 = RtlULongLongAdd(v468, 4, &v1311);
                                      if ( v337 < 0 )
                                        goto LABEL_536;
                                      v337 = RtlULongLongAdd(v1311, v469, &v1311);
                                      if ( v337 < 0 )
                                        goto LABEL_536;
                                      v468 = v1311;
                                    }
                                    while ( (unsigned int)(v470 + 1) < 2 );
                                    v337 = RtlULongLongAdd(v1311, 4, &v1311);
                                    if ( v337 >= 0 )
                                    {
                                      LODWORD(v1310) = 4;
                                      LODWORD(v1323) = 0;
                                      v337 = RtlUIntAdd(4, v1348, &v1310);
                                      if ( v337 >= 0 )
                                      {
                                        v337 = RtlUIntAdd((unsigned int)v1310, v471, &v1310);
                                        if ( v337 >= 0 )
                                        {
                                          v337 = RtlUIntAdd((unsigned int)v1310, v472, &v1310);
                                          if ( v337 >= 0 )
                                          {
                                            v337 = RtlUIntAdd((unsigned int)v1310, (unsigned int)(v473 + 4), &v1310);
                                            if ( v337 >= 0 )
                                            {
                                              v337 = RtlUIntAdd((unsigned int)v1310, v474, &v1310);
                                              if ( v337 >= 0 )
                                              {
                                                LODWORD(v1323) = v1310;
                                                if ( (unsigned int)v1310 > 0x400000 )
                                                {
                                                  v337 = -2147418113;
                                                  goto LABEL_536;
                                                }
                                                v465 = v1310;
                                                v466 = GetProcessHeap();
                                                v1308 = HeapAlloc(v466, 8u, v465);
                                                v467 = v1308;
                                                if ( !v1308 )
                                                {
                                                  v337 = -805306345;
                                                  v1308 = 0;
                                                  goto LABEL_536;
                                                }
                                                hModule = 0;
                                                v1365 = 0;
                                                v1366 = 0;
                                                if ( !lpMem )
                                                {
                                                  v337 = -2147024809;
LABEL_626:
                                                  v1308 = v467;
                                                  goto LABEL_536;
                                                }
                                                *(_QWORD *)((char *)&v1366 + 4) = (unsigned int)v1323;
                                                *(_QWORD *)&v1365 = lpMem;
                                                LODWORD(v1366) = Size;
                                                *((_QWORD *)&v1365 + 1) = v1308;
                                                if ( GetModuleHandleExW(1u, L"ntdll.dll", &hModule)
                                                  && (v476 = GetProcAddress(hModule, "NtQuerySystemInformation")) != 0 )
                                                {
                                                  v477 = ((__int64 (__fastcall *)(__int64, __int128 *))v476)(
                                                           134,
                                                           &v1365);
                                                  v337 = v477 | 0x10000000;
                                                  if ( v477 >= 0 )
                                                  {
                                                    v478 = DWORD1(v1366);
                                                    goto LABEL_634;
                                                  }
                                                }
                                                else
                                                {
                                                  v475 = GetLastError();
                                                  v337 = v475;
                                                  if ( v475 > 0 )
                                                    v337 = (unsigned __int16)v475 | 0x80070000;
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
                                                  v478 = v1323;
LABEL_634:
                                                  v467 = v1308;
                                                  v1312 = v1308;
                                                  LODWORD(v1309) = 0;
                                                  if ( v478 < 4 )
                                                  {
LABEL_635:
                                                    v337 = -805306306;
                                                    goto LABEL_626;
                                                  }
                                                  LODWORD(Size) = *(_DWORD *)v1308;
                                                  v479 = RtlULongLongAdd(v1308, 4, &v1312);
                                                  if ( v479 >= 0 )
                                                  {
                                                    v479 = RtlUIntAdd(0, 4, &v1309);
                                                    if ( v479 < 0 )
                                                    {
LABEL_688:
                                                      v1308 = v467;
                                                      goto LABEL_689;
                                                    }
                                                    if ( v481 - (int)v1309 < (unsigned int)v482 )
                                                      goto LABEL_635;
                                                    v1327 = (SIZE_T)v1312;
                                                    v1316 = v482;
                                                    v479 = RtlULongLongAdd(v1312, (unsigned int)v482, &v1312);
                                                    if ( v479 >= 0 )
                                                    {
                                                      v479 = RtlUIntAdd((unsigned int)v1309, v483, &v1309);
                                                      if ( v479 >= 0 )
                                                      {
                                                        if ( (unsigned int)(v484 - v1309) < 4 )
                                                          goto LABEL_635;
                                                        LODWORD(v1298) = *(_DWORD *)v1312;
                                                        v479 = RtlULongLongAdd(v1312, 4, &v1312);
                                                        if ( v479 >= 0 )
                                                        {
                                                          v479 = RtlUIntAdd((unsigned int)v1309, 4, &v1309);
                                                          if ( v479 >= 0 )
                                                          {
                                                            if ( v485 - (int)v1309 < (unsigned int)v486 )
                                                              goto LABEL_635;
                                                            v1319 = v1312;
                                                            pcchLength = v486;
                                                            v479 = RtlULongLongAdd(v1312, (unsigned int)v486, &v1312);
                                                            if ( v479 >= 0 )
                                                            {
                                                              v479 = RtlUIntAdd((unsigned int)v1309, v487, &v1309);
                                                              if ( v479 >= 0 )
                                                              {
                                                                if ( (unsigned int)(v488 - v1309) < 4 )
                                                                  goto LABEL_635;
                                                                LODWORD(v1323) = *(_DWORD *)v1312;
                                                                v479 = RtlULongLongAdd(v1312, 4, &v1312);
                                                                if ( v479 >= 0 )
                                                                {
                                                                  v479 = RtlUIntAdd((unsigned int)v1309, 4, &v1309);
                                                                  if ( v479 >= 0 )
                                                                  {
                                                                    if ( v489 - (int)v1309 < v490 )
                                                                      goto LABEL_635;
                                                                    v479 = RtlUIntAdd((unsigned int)v1309, v490, &v1309);
                                                                    if ( v479 >= 0 )
                                                                    {
                                                                      if ( v491 != (_DWORD)v1309 )
                                                                        goto LABEL_635;
                                                                      v493 = (unsigned int)Size;
                                                                      if ( (unsigned int)(Size + v492 + v1298) + 12LL != v491 )
                                                                        goto LABEL_635;
                                                                      v494 = GetProcessHeap();
                                                                      v1300 = (SIZE_T)HeapAlloc(v494, 8u, 0x30u);
                                                                      v495 = v1300;
                                                                      if ( !v1300 )
                                                                      {
                                                                        v1304 = 0;
                                                                        goto LABEL_535;
                                                                      }
                                                                      v1326 = v22;
                                                                      v1328 = v311;
                                                                      v1320 = v316;
                                                                      v1311 = 0;
                                                                      if ( v1327 )
                                                                      {
                                                                        *(_DWORD *)v1300 = v493;
                                                                        v496 = GetProcessHeap();
                                                                        v497 = HeapAlloc(v496, 8u, v493);
                                                                        if ( !v497 )
                                                                        {
LABEL_667:
                                                                          v504 = v1300;
                                                                          v479 = -1073741801;
                                                                          v1316 = *(_QWORD *)(v1300 + 8);
                                                                          if ( v1316 )
                                                                          {
                                                                            v505 = GetProcessHeap();
                                                                            HeapFree(v505, 0, (LPVOID)v1316);
                                                                            v504 = v1300;
                                                                            *(_QWORD *)(v1300 + 8) = 0;
                                                                          }
                                                                          v1316 = *(_QWORD *)(v504 + 24);
                                                                          if ( v1316 )
                                                                          {
                                                                            v506 = GetProcessHeap();
                                                                            HeapFree(v506, 0, (LPVOID)v1316);
                                                                            v504 = v1300;
                                                                            *(_QWORD *)(v1300 + 24) = 0;
                                                                          }
                                                                          v1316 = *(_QWORD *)(v504 + 40);
                                                                          if ( v1316 )
                                                                          {
                                                                            v507 = GetProcessHeap();
                                                                            HeapFree(v507, 0, (LPVOID)v1316);
                                                                            *(_QWORD *)(v1300 + 40) = 0;
                                                                          }
                                                                          v508 = GetProcessHeap();
                                                                          HeapFree(v508, 0, (LPVOID)v1300);
                                                                          v509 = (size_t *)v1311;
                                                                          goto LABEL_677;
                                                                        }
                                                                        *(_QWORD *)(v1300 + 8) = v497;
                                                                        v479 = 0;
                                                                        memcpy_0(v497, (const void *)v1327, v1316);
                                                                        v495 = v1300;
                                                                      }
                                                                      else
                                                                      {
                                                                        *(_DWORD *)v1300 = 0;
                                                                        v479 = 0;
                                                                        *(_QWORD *)(v495 + 8) = 0;
                                                                      }
                                                                      if ( v1319 )
                                                                      {
                                                                        *(_DWORD *)(v495 + 16) = v1298;
                                                                        v498 = GetProcessHeap();
                                                                        v499 = HeapAlloc(v498, 8u, pcchLength);
                                                                        if ( !v499 )
                                                                        {
LABEL_666:
                                                                          v1326 = v22;
                                                                          v1328 = v311;
                                                                          v1320 = v316;
                                                                          goto LABEL_667;
                                                                        }
                                                                        *(_QWORD *)(v1300 + 24) = v499;
                                                                        v479 = 0;
                                                                        memcpy_0(v499, v1319, pcchLength);
                                                                        v495 = v1300;
                                                                      }
                                                                      else
                                                                      {
                                                                        *(_DWORD *)(v495 + 16) = 0;
                                                                        *(_QWORD *)(v495 + 24) = 0;
                                                                      }
                                                                      if ( v1312 )
                                                                      {
                                                                        v500 = (unsigned int)v1323;
                                                                        *(_DWORD *)(v495 + 32) = v1323;
                                                                        v501 = v500;
                                                                        v1316 = v500;
                                                                        v502 = GetProcessHeap();
                                                                        v503 = HeapAlloc(v502, 8u, v501);
                                                                        if ( !v503 )
                                                                          goto LABEL_666;
                                                                        *(_QWORD *)(v1300 + 40) = v503;
                                                                        v479 = 0;
                                                                        memcpy_0(v503, v1312, v1316);
                                                                        v495 = v1300;
                                                                      }
                                                                      else
                                                                      {
                                                                        *(_DWORD *)(v495 + 32) = 0;
                                                                        *(_QWORD *)(v495 + 40) = 0;
                                                                      }
                                                                      v509 = (size_t *)v495;
                                                                      v1311 = v495;
                                                                      v1320 = v316;
                                                                      v1328 = v311;
                                                                      v1326 = v22;
LABEL_677:
                                                                      if ( v479 < 0 )
                                                                      {
                                                                        v480 = 0;
                                                                        v1304 = 0;
                                                                        if ( v509 )
                                                                        {
                                                                          v1316 = v509[1];
                                                                          if ( v1316 )
                                                                          {
                                                                            v510 = GetProcessHeap();
                                                                            HeapFree(v510, 0, (LPVOID)v1316);
                                                                            v509 = (size_t *)v1311;
                                                                            *(_QWORD *)(v1311 + 8) = 0;
                                                                          }
                                                                          v1316 = v509[3];
                                                                          if ( v1316 )
                                                                          {
                                                                            v511 = GetProcessHeap();
                                                                            HeapFree(v511, 0, (LPVOID)v1316);
                                                                            v509 = (size_t *)v1311;
                                                                            *(_QWORD *)(v1311 + 24) = 0;
                                                                          }
                                                                          v1316 = v509[5];
                                                                          if ( v1316 )
                                                                          {
                                                                            v512 = GetProcessHeap();
                                                                            HeapFree(v512, 0, (LPVOID)v1316);
                                                                            *(_QWORD *)(v1311 + 40) = 0;
                                                                          }
                                                                          v513 = GetProcessHeap();
                                                                          HeapFree(v513, 0, (LPVOID)v1311);
                                                                          v480 = 0;
                                                                          v1304 = 0;
                                                                        }
                                                                      }
                                                                      else
                                                                      {
                                                                        v480 = (unsigned int *)v509;
                                                                        v1304 = v509;
                                                                      }
LABEL_689:
                                                                      v337 = v479 | 0x10000000;
                                                                      if ( v337 < 0 )
                                                                        goto LABEL_536;
                                                                      if ( !v480
                                                                        || (pcchLength = *((_QWORD *)v480 + 1)) == 0
                                                                        || !*v480 )
                                                                      {
                                                                        v337 = -805306355;
                                                                        goto LABEL_536;
                                                                      }
                                                                      v514 = *v480 - 8LL;
                                                                      v1319 = (void *)v514;
                                                                      v1314 = MemoryAlloc(v514);
                                                                      if ( !v1314 )
                                                                        goto LABEL_721;
                                                                      v515 = 0;
                                                                      v1311 = pcchLength;
                                                                      uBytes_4 = 0;
                                                                      v1300 = 0x7F1137FAB69605ELL;
                                                                      v1327 = v514 & 7;
                                                                      v1312 = v1314;
                                                                      if ( (v514 & 7) != 0 )
                                                                      {
                                                                        LODWORD(v1323) = 0;
                                                                        LODWORD(v1309) = 0;
                                                                        LODWORD(v1298) = 0;
                                                                        v516 = 0;
                                                                        v517 = 0;
                                                                        v518 = 0;
                                                                        v519 = (unsigned __int8 *)v1311;
                                                                        do
                                                                        {
                                                                          v520 = *v519++;
                                                                          LODWORD(v1313) = v520;
                                                                          LODWORD(v1298) = 8 * v516;
                                                                          if ( (unsigned int)v516 >= 4 )
                                                                          {
                                                                            LODWORD(v1313) = (_DWORD)v1313 << (56 - v1298);
                                                                            v517 |= v1313;
                                                                          }
                                                                          else
                                                                          {
                                                                            LODWORD(v1313) = (_DWORD)v1313 << (24 - v1298);
                                                                            v518 |= v1313;
                                                                          }
                                                                          ++v516;
                                                                        }
                                                                        while ( v516 < (int)v1327 );
                                                                        LODWORD(v1323) = v517;
                                                                        v515 = uBytes_4;
                                                                        LODWORD(v1309) = v518;
                                                                        v514 = (unsigned __int64)v1319;
                                                                        v1311 = (SIZE_T)v519;
                                                                        v521 = v1312;
                                                                        v522 = v1327;
                                                                        v1320 = v316;
                                                                        v1328 = v311;
                                                                        v1326 = v22;
                                                                        v523 = v1309 ^ 0x92F65A5;
                                                                        LODWORD(v1298) = 0;
                                                                        v524 = v1323 ^ 0x699A899C;
                                                                        v525 = v1309 ^ 0x92F65A5;
                                                                        v526 = v1323 ^ 0x699A899C;
                                                                        if ( (_DWORD)v1327 )
                                                                        {
                                                                          v527 = v1298;
                                                                          do
                                                                          {
                                                                            v1316 = (size_t)(v521 + 1);
                                                                            if ( v527 >= 4 )
                                                                            {
                                                                              v526 = __ROR4__(v526, 24);
                                                                              v528 = v526;
                                                                            }
                                                                            else
                                                                            {
                                                                              v525 = __ROR4__(v525, 24);
                                                                              v528 = v525;
                                                                            }
                                                                            *v521 = v528;
                                                                            ++v527;
                                                                            v521 = (_BYTE *)v1316;
                                                                          }
                                                                          while ( (int)v527 < (int)v522 );
                                                                          v1312 = (LPVOID)v1316;
                                                                        }
                                                                        if ( v522 <= 4 )
                                                                        {
                                                                          v529 = 0;
                                                                          if ( v522 < 4 )
                                                                            v523 = v523 >> (8 * (4 - v522)) << (8 * (4 - v522));
                                                                        }
                                                                        else
                                                                        {
                                                                          v529 = v524 >> (8 * (8 - v522)) << (8 * (8 - v522));
                                                                        }
                                                                      }
                                                                      else
                                                                      {
                                                                        v529 = 0;
                                                                        LODWORD(v1309) = 0;
                                                                        v523 = 0;
                                                                        LODWORD(v1323) = -1;
                                                                      }
                                                                      if ( v514 >> 3 )
                                                                      {
                                                                        v530 = HIDWORD(v1300);
                                                                        v531 = v514 >> 3;
                                                                        v532 = (unsigned __int8 *)v1311;
                                                                        v533 = v1323;
                                                                        v534 = HIDWORD(v1300) ^ 0xAB69605E;
                                                                        v535 = v1309;
                                                                        LODWORD(v1313) = WORD2(v1300);
                                                                        LODWORD(v1310) = 24670;
                                                                        v536 = v1312;
                                                                        v1327 = 0;
                                                                        LODWORD(v1298) = HIDWORD(v1300) ^ 0xAB69605E;
                                                                        do
                                                                        {
                                                                          v537 = v532[1];
                                                                          v538 = *v532;
                                                                          v539 = v532[4];
                                                                          v532 += 8;
                                                                          v540 = *(v532 - 5)
                                                                               | ((*(v532 - 6)
                                                                                 | ((v537 | (v538 << 8)) << 8)) << 8);
                                                                          v541 = v523 ^ v540;
                                                                          v542 = *(v532 - 1)
                                                                               | ((*(v532 - 2)
                                                                                 | ((*(v532 - 3) | (v539 << 8)) << 8)) << 8);
                                                                          v543 = v529 ^ v542 ^ v523 ^ v540 ^ v534;
                                                                          v544 = v541
                                                                               ^ (__ROR4__(v543, 22)
                                                                                + v1313
                                                                                * __ROR4__(v543 + 1419157410, 27));
                                                                          v545 = v543
                                                                               ^ (WORD1(v1300)
                                                                                * __ROR4__(v530 + v544, 9)
                                                                                - __ROR4__(v544, 30));
                                                                          v546 = v544
                                                                               ^ (v1310 * (v545 - v1313) - (v545 >> 13));
                                                                          v547 = v545
                                                                               ^ (HIWORD(v1300)
                                                                                * __ROR4__(v546 ^ WORD1(v1300), 26)
                                                                                - __ROR4__(v546, 30));
                                                                          v548 = v546 ^ (v530 - (v547 ^ 0xAB69605E));
                                                                          v549 = v547
                                                                               ^ (WORD1(v1300) * (v1313 ^ v548))
                                                                               ^ __ROR4__(v548, 6);
                                                                          v550 = v548
                                                                               ^ (__ROR4__(v549, 30)
                                                                                + v1310 * __ROR4__(v530 + v549, 15));
                                                                          v551 = v549
                                                                               ^ (HIWORD(v1300)
                                                                                * __ROR4__(v550 + 1419157410, 14)
                                                                                - __ROR4__(v550, 24));
                                                                          v552 = v550
                                                                               ^ __ROR4__(v551, 10)
                                                                               ^ (v1313 * __ROR4__(
                                                                                            v551 ^ 0xAB69605E,
                                                                                            12));
                                                                          v553 = v552
                                                                               ^ (HIWORD(v1300)
                                                                                * (v1310
                                                                                 + __ROR4__(
                                                                                     ~(v551
                                                                                     ^ (v552 >> 10)
                                                                                     ^ (WORD1(v1300)
                                                                                      * (v552 ^ HIWORD(v1300)))),
                                                                                     5)));
                                                                          v554 = v551
                                                                               ^ (v552 >> 10)
                                                                               ^ (WORD1(v1300) * (v552 ^ HIWORD(v1300)))
                                                                               ^ (v553 - HIWORD(v1300))
                                                                               ^ 0xAB69605E;
                                                                          v555 = v553
                                                                               ^ ((v554 >> 2)
                                                                                + v1313
                                                                                * __ROR4__(v554 ^ HIWORD(v1300), 30));
                                                                          v556 = v554
                                                                               ^ (__ROR4__(v555, 25)
                                                                                + WORD1(v1300)
                                                                                * __ROR4__(v555 - HIDWORD(v1300), 6));
                                                                          v557 = v555
                                                                               ^ (v1310 * (v1313 ^ v556)
                                                                                + __ROR4__(v556, 9));
                                                                          v558 = v556
                                                                               ^ (__ROR4__(v557, 25)
                                                                                + HIWORD(v1300)
                                                                                * __ROR4__(WORD1(v1300) ^ v557, 27));
                                                                          v530 = HIDWORD(v1300);
                                                                          v559 = v1298 ^ v557 ^ v558;
                                                                          v560 = v558
                                                                               ^ (v1313
                                                                                * (__ROR4__(v559, 3) - WORD1(v1300)));
                                                                          v561 = v559
                                                                               ^ (v1310
                                                                                * __ROR4__(v560 - HIDWORD(v1300), 1)
                                                                                - __ROR4__(v560, 6));
                                                                          v562 = v560
                                                                               ^ (__ROR4__(v561, 18)
                                                                                + HIWORD(v1300)
                                                                                * __ROR4__(v561 - 1419157410, 29));
                                                                          v563 = v561
                                                                               ^ (v1313
                                                                                * __ROR4__(v562 - 1419157410, 17)
                                                                                - __ROR4__(v562, 14));
                                                                          v534 = v1298;
                                                                          v564 = v562
                                                                               ^ (v563 >> 3)
                                                                               ^ (WORD1(v1300) * (v1310 ^ v563));
                                                                          v565 = v564 ^ HIDWORD(v1300);
                                                                          v566 = __ROR4__(v564, 30);
                                                                          v529 = v533 ^ v564;
                                                                          v533 = v542;
                                                                          v523 = v535
                                                                               ^ v563
                                                                               ^ v566
                                                                               ^ (v1310 * __ROR4__(v565, 28));
                                                                          v535 = v540;
                                                                          v536[3] = v523;
                                                                          v536[7] = v529;
                                                                          v536[2] = __ROR4__(v523, 8);
                                                                          v536[6] = __ROR4__(v529, 8);
                                                                          v536[1] = __ROR4__(v523, 16);
                                                                          v536[5] = __ROR4__(v529, 16);
                                                                          *v536 = __ROR4__(v523, 24);
                                                                          v536[4] = __ROR4__(v529, 24);
                                                                          v536 += 8;
                                                                          ++v1327;
                                                                        }
                                                                        while ( v1327 < v531 );
                                                                        v515 = uBytes_4;
                                                                        v3 = v1302;
                                                                        v22 = v1326;
                                                                        v316 = v1320;
                                                                        v311 = v1328;
                                                                        v514 = (unsigned __int64)v1319;
                                                                      }
                                                                      for ( k = 0; k < v514; ++k )
                                                                        v515 ^= *((_BYTE *)v1314 + k);
                                                                      if ( v515 != *(_QWORD *)(v514 + pcchLength) )
                                                                      {
                                                                        MemoryFree(v1314);
LABEL_721:
                                                                        v1314 = 0;
                                                                        v337 = -805306367;
                                                                        goto LABEL_536;
                                                                      }
                                                                      LODWORD(v1313) = 0;
                                                                      v1311 = (SIZE_T)v1314;
                                                                      if ( (unsigned int)v514 < 4 )
                                                                      {
LABEL_723:
                                                                        v568 = -1073741762;
LABEL_762:
                                                                        v337 = v568 | 0x10000000;
                                                                        goto LABEL_536;
                                                                      }
                                                                      v568 = RtlULongLongAdd(v1314, 4, &v1311);
                                                                      if ( v568 >= 0 )
                                                                      {
                                                                        v568 = RtlUIntAdd(0, 4, &v1313);
                                                                        if ( v568 >= 0 )
                                                                        {
                                                                          if ( (unsigned int)((_DWORD)v1319 - v1313) < 4 )
                                                                            goto LABEL_727;
                                                                          LODWORD(v1323) = *(_DWORD *)v1311;
                                                                          v568 = RtlULongLongAdd(v1311, 4, &v1311);
                                                                          if ( v568 < 0 )
                                                                            goto LABEL_761;
                                                                          v568 = RtlUIntAdd(
                                                                                   (unsigned int)v1313,
                                                                                   4,
                                                                                   &v1313);
                                                                          if ( v568 < 0 )
                                                                            goto LABEL_761;
                                                                          if ( (int)v1319 - (int)v1313 < (unsigned int)v1323 )
                                                                          {
LABEL_727:
                                                                            v572 = v1314;
                                                                          }
                                                                          else
                                                                          {
                                                                            v568 = RtlUIntAdd(
                                                                                     (unsigned int)v1313,
                                                                                     (unsigned int)v1323,
                                                                                     &v1313);
                                                                            if ( v568 < 0 )
                                                                              goto LABEL_761;
                                                                            v572 = v1314;
                                                                            if ( (unsigned __int64)v1314
                                                                               + (unsigned int)v1319 >= (unsigned int)v1323 + v1311
                                                                              && (unsigned __int64)v1314
                                                                               + (unsigned int)v1319
                                                                               - (unsigned int)v1323
                                                                               - v1311 < 8 )
                                                                            {
                                                                              LODWORD(v1309) = *(_DWORD *)v1314;
                                                                              v1319 = 0;
                                                                              v1327 = 0;
                                                                              v1329 = 0;
                                                                              LODWORD(Size) = 0;
                                                                              if ( v1311 )
                                                                              {
                                                                                v573 = RtlULongLongAdd(
                                                                                         v1311,
                                                                                         (unsigned int)v1323,
                                                                                         &v1319);
                                                                                v1308 = v575;
                                                                                v568 = v573;
                                                                                Src = v576;
                                                                                v1303 = v577;
                                                                                if ( v573 < 0 )
                                                                                {
LABEL_749:
                                                                                  v587 = v1325;
LABEL_750:
                                                                                  if ( v568 < 0 || (_DWORD)v1309 == v587 )
                                                                                    goto LABEL_762;
                                                                                  goto LABEL_723;
                                                                                }
                                                                                v1312 = v574;
                                                                                if ( v574 < v1319 )
                                                                                {
                                                                                  while ( 1 )
                                                                                  {
                                                                                    v568 = RtlULongLongAdd(
                                                                                             v574,
                                                                                             4,
                                                                                             &v1327);
                                                                                    if ( v568 < 0 )
                                                                                      goto LABEL_749;
                                                                                    if ( v1327 > (unsigned __int64)v1319 )
                                                                                      goto LABEL_748;
                                                                                    v579 = *v578;
                                                                                    LODWORD(v1298) = 0;
                                                                                    v568 = RtlUIntAdd(4, v579, &v1298);
                                                                                    if ( v568 < 0 )
                                                                                      goto LABEL_762;
                                                                                    LODWORD(v1313) = uBytes;
                                                                                    v1300 = (SIZE_T)v1304;
                                                                                    LODWORD(v1310) = v22;
                                                                                    v581 = v316;
                                                                                    v582 = v1299;
                                                                                    v1328 = v1314;
                                                                                    pcchLength = (size_t)v311;
                                                                                    v1321 = v580;
                                                                                    v1318 = v1299;
                                                                                    v568 = RtlULongLongAdd(
                                                                                             v1312,
                                                                                             (unsigned int)v1298,
                                                                                             &v1329);
                                                                                    v1314 = v1328;
                                                                                    v1299 = v582;
                                                                                    v316 = v581;
                                                                                    v1304 = (LPVOID)v1300;
                                                                                    v22 = v1310;
                                                                                    v1308 = v584;
                                                                                    Src = v585;
                                                                                    v1303 = v583;
                                                                                    uBytes = v1313;
                                                                                    if ( v568 < 0 )
                                                                                      goto LABEL_749;
                                                                                    v574 = (void *)v1329;
                                                                                    v586 = v1319;
                                                                                    v1312 = (LPVOID)v1329;
                                                                                    v1308 = v584;
                                                                                    Src = v585;
                                                                                    v1303 = v583;
                                                                                    uBytes = v1313;
                                                                                    if ( v1329 > (unsigned __int64)v1319 )
                                                                                    {
                                                                                      v568 = -1073741811;
                                                                                      v1314 = v1328;
                                                                                      v1304 = (LPVOID)v1300;
                                                                                      v1299 = v1318;
                                                                                      goto LABEL_762;
                                                                                    }
                                                                                    LODWORD(Size) = Size + 1;
                                                                                    v1314 = v1328;
                                                                                    v1304 = (LPVOID)v1300;
                                                                                    v1299 = v1318;
                                                                                    v311 = (void *)pcchLength;
                                                                                    if ( v1329 >= (unsigned __int64)v1319 )
                                                                                    {
                                                                                      v1314 = v1328;
                                                                                      v1304 = (LPVOID)v1300;
                                                                                      v1299 = v1318;
                                                                                      v1303 = v1321;
                                                                                      v1308 = v584;
                                                                                      Src = v585;
                                                                                      uBytes = v1313;
                                                                                      goto LABEL_747;
                                                                                    }
                                                                                  }
                                                                                }
                                                                                v586 = v1319;
                                                                                v574 = v1312;
LABEL_747:
                                                                                if ( v574 != v586 )
                                                                                {
LABEL_748:
                                                                                  v568 = -1073741811;
                                                                                  goto LABEL_762;
                                                                                }
                                                                              }
                                                                              else
                                                                              {
                                                                                v568 = 0;
                                                                                v1308 = v570;
                                                                                Src = v571;
                                                                                v1303 = v569;
                                                                              }
                                                                              v588 = v1323;
                                                                              v589 = 0;
                                                                              v1329 = 0;
                                                                              if ( (_DWORD)v1323 )
                                                                              {
                                                                                v590 = GetProcessHeap();
                                                                                v1329 = (size_t)HeapAlloc(
                                                                                                  v590,
                                                                                                  8u,
                                                                                                  (unsigned int)v1323);
                                                                                v589 = (void *)v1329;
                                                                                if ( !v1329 )
                                                                                {
                                                                                  v568 = -1073741801;
                                                                                  goto LABEL_762;
                                                                                }
                                                                                v588 = v1323;
                                                                                v568 = 0;
                                                                              }
                                                                              if ( v1311 )
                                                                                memcpy_0(
                                                                                  v589,
                                                                                  (const void *)v1311,
                                                                                  v588);
                                                                              dwBytes = v1329;
                                                                              v587 = Size;
                                                                              LODWORD(v1325) = Size;
                                                                              goto LABEL_750;
                                                                            }
                                                                          }
                                                                          v568 = -1073741762;
                                                                          v1314 = v572;
                                                                        }
                                                                      }
LABEL_761:
                                                                      v1303 = v569;
                                                                      Src = v571;
                                                                      v1308 = v570;
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
                                                  v480 = (unsigned int *)v1304;
                                                  goto LABEL_688;
                                                }
LABEL_625:
                                                v467 = v1308;
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
                              v422 = v1299;
                              if ( v1299 )
                              {
                                v1321 = (_BYTE *)*((_QWORD *)v1299 + 1);
                                if ( v1321 )
                                {
                                  v423 = GetProcessHeap();
                                  HeapFree(v423, 0, v1321);
                                  v422 = v1299;
                                  *((_QWORD *)v1299 + 1) = 0;
                                }
                                v1321 = (_BYTE *)v422[3];
                                if ( v1321 )
                                {
                                  v424 = GetProcessHeap();
                                  HeapFree(v424, 0, v1321);
                                  v422 = v1299;
                                  *((_QWORD *)v1299 + 3) = 0;
                                }
                                v1321 = (_BYTE *)v422[5];
                                if ( v1321 )
                                {
                                  v425 = GetProcessHeap();
                                  HeapFree(v425, 0, v1321);
                                  *((_QWORD *)v1299 + 5) = 0;
                                }
                                v426 = GetProcessHeap();
                                HeapFree(v426, 0, v1299);
                              }
                              if ( lpMem )
                              {
                                v427 = GetProcessHeap();
                                HeapFree(v427, 0, lpMem);
                              }
                              if ( v1308 )
                              {
                                v428 = GetProcessHeap();
                                HeapFree(v428, 0, v1308);
                              }
                              v429 = v1304;
                              if ( v1304 )
                              {
                                v1321 = (_BYTE *)*((_QWORD *)v1304 + 1);
                                if ( v1321 )
                                {
                                  v430 = GetProcessHeap();
                                  HeapFree(v430, 0, v1321);
                                  v429 = v1304;
                                  *((_QWORD *)v1304 + 1) = 0;
                                }
                                v1321 = (_BYTE *)v429[3];
                                if ( v1321 )
                                {
                                  v431 = GetProcessHeap();
                                  HeapFree(v431, 0, v1321);
                                  v429 = v1304;
                                  *((_QWORD *)v1304 + 3) = 0;
                                }
                                v1321 = (_BYTE *)v429[5];
                                if ( v1321 )
                                {
                                  v432 = GetProcessHeap();
                                  HeapFree(v432, 0, v1321);
                                  *((_QWORD *)v1304 + 5) = 0;
                                }
                                v433 = GetProcessHeap();
                                HeapFree(v433, 0, v1304);
                              }
                              if ( v1314 )
                              {
                                v434 = GetProcessHeap();
                                HeapFree(v434, 0, v1314);
                              }
LABEL_560:
                              if ( v337 >= 0 && (_DWORD)v1325 && dwBytes )
                              {
                                v1329 = dwBytes;
                                v435 = RtlULongLongAdd(dwBytes, 4, &v1329);
                                v314 = v1303;
                                dwBytes = (SIZE_T)v437;
                                if ( v435 < 0 )
                                {
                                  v440 = uBytes;
                                }
                                else
                                {
                                  v439 = (int *)v1329;
                                  if ( !*v437 )
                                    v439 = 0;
                                  v440 = uBytes;
                                  if ( *v437 != (_DWORD)v438 )
                                    goto LABEL_770;
                                  if ( *v439 < 0 )
                                  {
                                    dwBytes = (SIZE_T)v437;
                                    goto LABEL_770;
                                  }
                                  if ( v436 > 1 )
                                  {
                                    v441 = (SIZE_T)v437;
                                    v1311 = (SIZE_T)v437;
                                    while ( (int)RtlULongLongAdd(v441, v438, &v1311) >= 0
                                         && (int)RtlULongLongAdd(v1311, v442, &v1311) >= 0 )
                                    {
                                      v441 = v1311;
                                      if ( v443 != -1 )
                                      {
                                        RtlULongLongAdd(v1311, v438, &v1311);
                                        goto LABEL_770;
                                      }
                                    }
                                    goto LABEL_770;
                                  }
                                  dwBytes = (SIZE_T)v437;
                                }
                                uBytes = v440;
                                goto LABEL_770;
                              }
LABEL_769:
                              v314 = v1303;
                              goto LABEL_770;
                            }
LABEL_537:
                            v421 = GetProcessHeap();
                            HeapFree(v421, 0, Src);
                            goto LABEL_538;
                          }
                        }
                        v1299 = v455;
                        goto LABEL_586;
                      }
                    }
                    else
                    {
                      v1300 = v397;
                    }
                  }
                  v388 = -1073741801;
                  v404 = v1300;
                  v1316 = *(_QWORD *)(v1300 + 8);
                  if ( v1316 )
                  {
                    v405 = GetProcessHeap();
                    HeapFree(v405, 0, (LPVOID)v1316);
                    v404 = v1300;
                    *(_QWORD *)(v1300 + 8) = 0;
                  }
                  v1316 = *(_QWORD *)(v404 + 24);
                  if ( v1316 )
                  {
                    v406 = GetProcessHeap();
                    HeapFree(v406, 0, (LPVOID)v1316);
                    v404 = v1300;
                    *(_QWORD *)(v1300 + 24) = 0;
                  }
                  v1316 = *(_QWORD *)(v404 + 40);
                  if ( v1316 )
                  {
                    v407 = GetProcessHeap();
                    HeapFree(v407, 0, (LPVOID)v1316);
                    *(_QWORD *)(v1300 + 40) = 0;
                  }
                  v408 = GetProcessHeap();
                  HeapFree(v408, 0, (LPVOID)v1300);
                }
                else
                {
                  v388 = -1073741801;
                }
                v389 = v1299;
                goto LABEL_507;
              }
            }
LABEL_773:
            v591 = GetProcessHeap();
            HeapFree(v591, 0, v316);
LABEL_774:
            v592 = (void *)dwBytes;
            if ( dwBytes )
            {
              v593 = GetProcessHeap();
              HeapFree(v593, 0, v592);
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
    v1316 = (unsigned int)v1298;
    if ( v40 + 41 > (_DWORD *)&v28[(unsigned int)v1298] )
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
    v45 = v1316;
    if ( !Src )
    {
      v20 = -1073741811;
      goto LABEL_432;
    }
    if ( v28 )
    {
      v46 = 0;
      LODWORD(Size) = v1316;
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
      v1316 = (size_t)(v48 + 1);
      if ( v48 + 1 < v48 )
        goto LABEL_431;
      if ( v48 + 3 > (_DWORD *)&v28[v45] )
        goto LABEL_63;
      *v48 = 8;
      memcpy_0((void *)v1316, v44, 8u);
      v49 = 0;
      LODWORD(v1310) = Size;
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
      v51 = v1327;
      *(_DWORD *)v43 = 8;
      *(_QWORD *)(v43 + 4) = v51;
    }
    else
    {
      if ( (int)v1316 + 12 < (unsigned int)v1316 )
        goto LABEL_431;
      LODWORD(v1310) = v1316 + 24;
      if ( (int)v1316 + 24 < (unsigned int)(v1316 + 12) )
        goto LABEL_431;
    }
    pcchLength = 0;
    LODWORD(v1309) = 4;
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
      v55 = v1310;
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
      if ( (char *)v57 + v53 + 4 > &v28[(unsigned int)v1310] )
      {
        v20 = -1073741789;
        goto LABEL_94;
      }
      *v57 = v53;
      v20 = 0;
      memcpy_0(v57 + 1, psz, (unsigned int)v53);
      v52 = Src;
      v59 = v1309 + 1;
      v55 = v1310;
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
        LODWORD(v1309) = v60 + 1;
        v1316 = __rdtsc();
        v68 = ii + 8;
        if ( v68 < 8 || (v69 = (v68 + 7) & 0xFFFFFFF8, v1311 = v69, (unsigned int)v69 < v68) )
        {
          v20 = -805306219;
          goto LABEL_438;
        }
        LODWORD(v1298) = 0;
        v1333 = (unsigned int)v69;
        v70 = GetProcessHeap();
        v71 = HeapAlloc(v70, 8u, (v68 + 7) & 0xFFFFFFF8);
        v1299 = v71;
        if ( !v71 )
        {
          v20 = -805306345;
          goto LABEL_372;
        }
        v72 = Src;
        *v71 = v1309;
        if ( v71 + 1 < v71 || (v73 = Size, v71[1] = Size, v71 + 2 < v71 + 1) )
        {
          pcchLength = (size_t)v71;
          v1299 = 0;
          LODWORD(v1311) = 0;
          v115 = GetProcessHeap();
          HeapFree(v115, 0, (LPVOID)pcchLength);
          v20 = -805306219;
          goto LABEL_372;
        }
        *(_QWORD *)((char *)v71 + v1333 - 8) = v1316;
        memcpy_0(v71 + 2, v28, v73);
        pcchLength = (size_t)v1299;
        v1300 = 0;
        v1303 = 0;
        v1308 = 0;
        v1304 = 0;
        v1314 = 0;
        v1310 = 0;
        if ( !(_DWORD)v1311
          || (dwBytes = (unsigned int)v1311 + 8LL,
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
        while ( v77 < (unsigned int)v1311 );
        uBytes_4 = v76;
        v1312 = v19;
        Src = v72;
        v1319 = v28;
        v1318 = (void *)0xC81ECB17B1B54A58LL;
        v1316 = (unsigned __int64)(unsigned int)v1311 >> 3;
        if ( v1316 )
        {
          v78 = WORD1(v1318);
          v79 = 0;
          v80 = WORD2(v1318);
          v81 = lpMem;
          v82 = v1316;
          v83 = -1;
          LODWORD(v1323) = HIDWORD(v1318) ^ 0xB1B54A58;
          pcchLength = 0;
          v84 = (unsigned __int8 *)v1299;
          LODWORD(Size) = 0;
          LODWORD(v1325) = 0;
          v85 = HIDWORD(v1318) ^ 0xB1B54A58;
          LODWORD(v1313) = WORD1(v1318);
          do
          {
            v86 = v84[1];
            v87 = *v84;
            v88 = v84[4];
            v84 += 8;
            v89 = *(v84 - 5) | ((*(v84 - 6) | ((v86 | (v87 << 8)) << 8)) << 8);
            v90 = *(v84 - 1) | ((*(v84 - 2) | ((*(v84 - 3) | (v88 << 8)) << 8)) << 8);
            v91 = v83 ^ v90;
            v92 = v79 ^ v89 ^ HIDWORD(v1318) ^ ((v83 ^ v90) - 19032);
            v93 = v91 ^ (__ROR4__(v92, 7) + v78 * __ROR4__(v92 ^ HIDWORD(v1318), 15));
            v94 = v92 ^ (v80 * __ROR4__(v93 - 1313519016, 9) - __ROR4__(v93, 10));
            v95 = v93 ^ (__ROR4__(v94, 27) + HIWORD(v1318) * __ROR4__(v80 ^ v94, 28));
            v96 = v94 ^ (HIDWORD(v1318) - (v95 ^ 0xB1B54A58));
            v97 = v95 ^ (WORD1(v1318) * (v96 - 19032) - (v96 >> 6));
            v98 = v96 ^ (19032 * (v80 ^ __ROR4__(v97, 15)));
            v99 = v97 ^ (v80 * (HIWORD(v1318) + __ROR4__(~v98, 3)));
            v100 = v98 ^ (v99 - HIDWORD(v1318) - 19032);
            v101 = v99 ^ (v1313 * (HIWORD(v1318) ^ v100)) ^ __ROR4__(v100, 10);
            v102 = v100 ^ __ROR4__(v101, 3) ^ (v80 * __ROR4__(v101 ^ 0x4A58, 26));
            v103 = v101 ^ (19032 * (__ROR4__(v102, 15) - HIWORD(v1318)));
            v104 = v102
                 ^ (19032 * (HIWORD(v1318) ^ v103))
                 ^ ((v103 ^ (v103 >> 14)) >> 1)
                 ^ (19032 * (((unsigned __int64)(v103 - v80) >> 29) | (8 * (v103 - v80))));
            v105 = v103 ^ (WORD1(v1318) * (v104 - v80) - (v104 >> 13));
            v106 = v104 ^ __ROR4__(v105, 11) ^ (v80 * __ROR4__(-1313519016 - v105, 9));
            v107 = v105 ^ (v106 - HIWORD(v1318) + 1313519016);
            v108 = v106 ^ (19032 * (v107 ^ WORD1(v1318)) - __ROR4__(v107, 7));
            v109 = v107 ^ (WORD1(v1318) * __ROR4__(HIWORD(v1318) ^ v108, 28) - __ROR4__(v108, 16));
            v110 = v108 ^ (__ROR4__(v109, 4) + v80 * __ROR4__(-1313519016 - v109, 10));
            v111 = v109 ^ __ROR4__(v110, 9) ^ (HIWORD(v1318) * __ROR4__(v110 + 1313519016, 4));
            v112 = v110 ^ (19032 * __ROR4__(v111 ^ HIDWORD(v1318), 24) - __ROR4__(v111, 30));
            v113 = v111 ^ (WORD1(v1318) * __ROR4__(HIDWORD(v1318) - v112, 11) - __ROR4__(v112, 12));
            v114 = v112 ^ (v113 >> 8) ^ (v80 * (v113 ^ WORD1(v1318)));
            v79 = Size ^ v114;
            LOBYTE(v98) = __ROR4__(Size ^ v114, 8);
            v83 = v113 ^ v1325 ^ v114 ^ v85;
            v78 = WORD1(v1318);
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
            LODWORD(v1325) = v90;
            ++pcchLength;
          }
          while ( pcchLength < v82 );
          v76 = uBytes_4;
          v3 = v1302;
          v22 = v1326;
          v28 = (char *)v1319;
          v19 = v1312;
          v72 = Src;
          v75 = (char *)lpMem;
        }
        else
        {
          Src = v72;
        }
        *(_QWORD *)&v75[(unsigned int)v1311] = v76;
        v116 = GetProcessHeap();
        v1312 = HeapAlloc(v116, 8u, 0x30u);
        if ( v1312 )
        {
          Src = v72;
          v126 = v1312;
          *(_DWORD *)v1312 = dwBytes;
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
              *v130 = `WarbirdUmGetEncryptionCipher'::`2'::EncryptionCipher;
              v130[1] = xmmword_18012E4F0;
              v130[2] = xmmword_18012E500;
              v130[3] = xmmword_18012E510;
              v130[4] = xmmword_18012E520;
              v130[5] = xmmword_18012E530;
              v130[6] = xmmword_18012E540;
              v130[7] = xmmword_18012E550;
              v130[8] = xmmword_18012E560;
              v130[9] = xmmword_18012E570;
              *((_DWORD *)v126 + 8) = 8;
              v131 = GetProcessHeap();
              v132 = HeapAlloc(v131, 8u, 8u);
              if ( v132 )
              {
                v126[5] = v132;
                *v132 = `WarbirdUmGetEncryptionKey'::`2'::nEncryptionKey;
                v1300 = (SIZE_T)v126;
                v117 = 0;
                v118 = (void *)v1300;
                v1300 = 0;
LABEL_135:
                v1303 = v118;
                v119 = GetProcessHeap();
                HeapFree(v119, 0, lpMem);
                v120 = v1300;
                if ( v1300 )
                {
                  v1316 = *(_QWORD *)(v1300 + 8);
                  if ( v1316 )
                  {
                    v121 = GetProcessHeap();
                    HeapFree(v121, 0, (LPVOID)v1316);
                    v120 = v1300;
                    *(_QWORD *)(v1300 + 8) = 0;
                  }
                  v1316 = *(_QWORD *)(v120 + 24);
                  if ( v1316 )
                  {
                    v122 = GetProcessHeap();
                    HeapFree(v122, 0, (LPVOID)v1316);
                    v120 = v1300;
                    *(_QWORD *)(v1300 + 24) = 0;
                  }
                  v1316 = *(_QWORD *)(v120 + 40);
                  if ( v1316 )
                  {
                    v123 = GetProcessHeap();
                    HeapFree(v123, 0, (LPVOID)v1316);
                    *(_QWORD *)(v1300 + 40) = 0;
                  }
                  v124 = GetProcessHeap();
                  HeapFree(v124, 0, (LPVOID)v1300);
                  v125 = v1303;
                }
                else
                {
                  v125 = v1303;
                }
                v20 = v117 | 0x10000000;
                if ( v20 < 0 )
                  goto LABEL_342;
                v138 = *v125 + 4;
                LODWORD(v1325) = 0;
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
                          v1300 = (SIZE_T)v145;
                          if ( !v145 )
                          {
                            v20 = -805306345;
LABEL_340:
                            v151 = v1299;
                            goto LABEL_345;
                          }
                          v146 = (const void **)v1303;
                          *v145 = *(_DWORD *)v1303;
                          v1316 = (size_t)(v145 + 1);
                          if ( v145 + 1 < v145 )
                          {
                            v1300 = (SIZE_T)v145;
                          }
                          else
                          {
                            memcpy_0(v145 + 1, v146[1], *(unsigned int *)v146);
                            v147 = (_DWORD *)(v1316 + *(unsigned int *)v146);
                            if ( (unsigned __int64)v147 >= v1316 )
                            {
                              v148 = (unsigned int *)pcchLength;
                              *v147 = *(_DWORD *)pcchLength;
                              v1316 = (size_t)(v147 + 1);
                              if ( v147 + 1 >= v147 )
                              {
                                memcpy_0(v147 + 1, v146[3], *v148);
                                v149 = (_DWORD *)(v1316 + *(unsigned int *)pcchLength);
                                if ( (unsigned __int64)v149 >= v1316 )
                                {
                                  *v149 = *((_DWORD *)v146 + 8);
                                  v1316 = (size_t)(v149 + 1);
                                  if ( v149 + 1 >= v149 )
                                  {
                                    memcpy_0(v149 + 1, v146[5], *((unsigned int *)v146 + 8));
                                    if ( v1316 + *((unsigned int *)v146 + 8) >= v1316 )
                                    {
                                      v150 = v1300;
                                      v151 = v1299;
                                      v1308 = (LPVOID)v1300;
                                      LODWORD(v1325) = Size;
                                      if ( !v28 || (unsigned int)v1309 <= 1 )
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
                                      if ( (unsigned int)v1309 <= 2 )
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
                                        v1316 = (size_t)v155;
                                        if ( v155 < v156 )
                                          goto LABEL_347;
                                        LODWORD(Size) = Size + 1;
                                        v157 = (void *)v150;
                                        v1300 = (SIZE_T)v19;
                                        v1312 = Src;
                                        v1313 = (SIZE_T)v28;
                                        v1323 = (SIZE_T)v1299;
                                        v1318 = v146;
                                        v1309 = v150;
                                      }
                                      while ( (unsigned int)Size < 2 );
                                      if ( (unsigned __int64)(v155 + 1) < v1316
                                        || *v153 >= 0xFFFFFFB8
                                        || (v158 = *v153 + 76, v158 < *v153 + 72)
                                        || (v159 = v158 + *(_DWORD *)v1316, LODWORD(Size) = v159, v159 < v158) )
                                      {
LABEL_347:
                                        v20 = -1073741675;
                                        goto LABEL_345;
                                      }
                                      if ( v159 > 0x400000 )
                                      {
                                        v1308 = v157;
                                        v20 = -2147418113;
                                        v1303 = v1318;
                                        goto LABEL_344;
                                      }
                                      v160 = v159;
                                      v161 = GetProcessHeap();
                                      v162 = HeapAlloc(v161, 8u, v160);
                                      v163 = v1318;
                                      v151 = (void *)v1323;
                                      v164 = v162;
                                      v165 = v1312;
                                      v1304 = v162;
                                      v1308 = (LPVOID)v1309;
                                      v1303 = v1318;
                                      v1299 = (LPVOID)v1323;
                                      Src = v1312;
                                      if ( !v162 )
                                      {
                                        v20 = -805306345;
                                        v1304 = 0;
                                        goto LABEL_345;
                                      }
                                      v166 = (void *)v1309;
                                      phModule = 0;
                                      v1363 = 0;
                                      v1364 = 0;
                                      if ( !v1309 )
                                      {
                                        v20 = -2147024809;
LABEL_204:
                                        v1304 = v164;
                                        v1308 = v166;
                                        v1303 = v163;
                                        Src = v165;
                                        goto LABEL_344;
                                      }
                                      *(_QWORD *)&v1363 = v1309;
                                      LODWORD(v1364) = v1325;
                                      *(_QWORD *)((char *)&v1364 + 4) = (unsigned int)Size;
                                      *((_QWORD *)&v1363 + 1) = v162;
                                      if ( GetModuleHandleExW(1u, L"ntdll.dll", &phModule)
                                        && (v168 = GetProcAddress(phModule, "NtQuerySystemInformation")) != 0 )
                                      {
                                        v169 = ((__int64 (__fastcall *)(__int64, __int128 *))v168)(134, &v1363);
                                        v20 = v169 | 0x10000000;
                                        if ( v169 >= 0 )
                                        {
                                          v170 = DWORD1(v1364);
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
                                        v151 = (void *)v1323;
                                        v1308 = (LPVOID)v1309;
                                        v1303 = v1318;
                                        v171 = v1312;
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
                                        v172 = *(unsigned int *)v1304;
                                        v173 = (char *)v1304 + 4;
                                        v1333 = (SIZE_T)v1304 + 4;
                                        if ( (char *)v1304 + 4 >= v1304 )
                                        {
                                          if ( v170 - 4 < (unsigned int)v172 )
                                          {
LABEL_216:
                                            v20 = -805306306;
                                            goto LABEL_210;
                                          }
                                          v174 = &v173[v172];
                                          v1329 = v172;
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
                                                v1316 = (size_t)v176 + v175;
                                                if ( (_DWORD *)((char *)v176 + v175) >= v176 )
                                                {
                                                  v179 = v177 + v175;
                                                  if ( v177 + (unsigned int)v175 >= v177 )
                                                  {
                                                    if ( v170 - v179 < 4 )
                                                      goto LABEL_216;
                                                    v1319 = (void *)(v178 + 4);
                                                    if ( v178 + 4 >= v178 )
                                                    {
                                                      v180 = v179 + 4;
                                                      if ( v179 + 4 >= v179 )
                                                      {
                                                        v181 = *(_DWORD *)v1316;
                                                        LODWORD(v1325) = v181;
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
                                                          v151 = (void *)v1323;
                                                          v20 = -805306345;
                                                          v19 = (_OWORD *)v1300;
                                                          v1308 = (LPVOID)v1309;
                                                          v1303 = v1318;
                                                          v171 = v1312;
                                                          goto LABEL_343;
                                                        }
                                                        v184 = (const void *)v1333;
                                                        v1311 = 0;
                                                        if ( v1333 )
                                                        {
                                                          *(_DWORD *)v183 = v172;
                                                          v185 = GetProcessHeap();
                                                          v186 = HeapAlloc(v185, 8u, v172);
                                                          if ( !v186 )
                                                          {
LABEL_245:
                                                            v187 = -1073741801;
                                                            v28 = (char *)v1313;
                                                            v19 = (_OWORD *)v1300;
                                                            v1308 = (LPVOID)v1309;
                                                            v1303 = v1318;
                                                            v1299 = (LPVOID)v1323;
                                                            Src = v1312;
                                                            v196 = dwBytes;
                                                            v1319 = (void *)v1313;
                                                            v1312 = (LPVOID)v1300;
                                                            v1316 = *(_QWORD *)(dwBytes + 8);
                                                            if ( v1316 )
                                                            {
                                                              v197 = GetProcessHeap();
                                                              HeapFree(v197, 0, (LPVOID)v1316);
                                                              v196 = dwBytes;
                                                              *(_QWORD *)(dwBytes + 8) = 0;
                                                            }
                                                            v1316 = *(_QWORD *)(v196 + 24);
                                                            if ( v1316 )
                                                            {
                                                              v198 = GetProcessHeap();
                                                              HeapFree(v198, 0, (LPVOID)v1316);
                                                              v196 = dwBytes;
                                                              *(_QWORD *)(dwBytes + 24) = 0;
                                                            }
                                                            v1316 = *(_QWORD *)(v196 + 40);
                                                            if ( v1316 )
                                                            {
                                                              v199 = GetProcessHeap();
                                                              HeapFree(v199, 0, (LPVOID)v1316);
                                                              *(_QWORD *)(dwBytes + 40) = 0;
                                                            }
                                                            v200 = GetProcessHeap();
                                                            HeapFree(v200, 0, (LPVOID)dwBytes);
                                                            v201 = (size_t *)v1311;
                                                            goto LABEL_255;
                                                          }
                                                          v183[1] = v186;
                                                          v187 = 0;
                                                          memcpy_0(v186, v184, v1329);
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
                                                        v191 = v1319;
                                                        if ( v1319 )
                                                        {
                                                          v192 = (unsigned int)v1325;
                                                          *((_DWORD *)v183 + 8) = v1325;
                                                          v193 = v192;
                                                          v1316 = v192;
                                                          v194 = GetProcessHeap();
                                                          v195 = HeapAlloc(v194, 8u, v193);
                                                          if ( !v195 )
                                                            goto LABEL_244;
                                                          v183[5] = v195;
                                                          v187 = 0;
                                                          memcpy_0(v195, v191, v1316);
                                                        }
                                                        else
                                                        {
                                                          *((_DWORD *)v183 + 8) = 0;
                                                          v183[5] = 0;
                                                        }
                                                        v201 = v183;
                                                        v28 = (char *)v1313;
                                                        v19 = (_OWORD *)v1300;
                                                        v1308 = (LPVOID)v1309;
                                                        v1303 = v1318;
                                                        v1299 = (LPVOID)v1323;
                                                        Src = v1312;
                                                        v1311 = (SIZE_T)v201;
                                                        v1319 = (void *)v1313;
                                                        v1312 = (LPVOID)v1300;
LABEL_255:
                                                        if ( v187 < 0 )
                                                        {
                                                          if ( v201 )
                                                          {
                                                            v1316 = v201[1];
                                                            if ( v1316 )
                                                            {
                                                              v202 = GetProcessHeap();
                                                              HeapFree(v202, 0, (LPVOID)v1316);
                                                              v201 = (size_t *)v1311;
                                                              *(_QWORD *)(v1311 + 8) = 0;
                                                            }
                                                            v1316 = v201[3];
                                                            if ( v1316 )
                                                            {
                                                              v203 = GetProcessHeap();
                                                              HeapFree(v203, 0, (LPVOID)v1316);
                                                              v201 = (size_t *)v1311;
                                                              *(_QWORD *)(v1311 + 24) = 0;
                                                            }
                                                            v1316 = v201[5];
                                                            if ( v1316 )
                                                            {
                                                              v204 = GetProcessHeap();
                                                              HeapFree(v204, 0, (LPVOID)v1316);
                                                              *(_QWORD *)(v1311 + 40) = 0;
                                                            }
                                                            v205 = GetProcessHeap();
                                                            HeapFree(v205, 0, (LPVOID)v1311);
                                                          }
                                                        }
                                                        else
                                                        {
                                                          v1314 = v201;
                                                        }
                                                        v20 = v187 | 0x10000000;
                                                        if ( v20 < 0 )
                                                          goto LABEL_340;
                                                        if ( !v1314
                                                          || (v1325 = *((_QWORD *)v1314 + 1)) == 0
                                                          || !*(_DWORD *)v1314 )
                                                        {
                                                          v20 = -805306355;
                                                          goto LABEL_340;
                                                        }
                                                        dwBytes = *(unsigned int *)v1314 - 8LL;
                                                        v206 = GetProcessHeap();
                                                        v207 = HeapAlloc(v206, 0, dwBytes);
                                                        v1311 = (SIZE_T)v207;
                                                        if ( !v207 )
                                                        {
LABEL_297:
                                                          v1310 = 0;
                                                          v20 = -805306367;
                                                          goto LABEL_340;
                                                        }
                                                        v208 = dwBytes;
                                                        v209 = 0;
                                                        uBytes_4 = 0;
                                                        v1300 = 0x7F1137FAB69605ELL;
                                                        lpMem = (LPVOID)v1325;
                                                        v1318 = v207;
                                                        v210 = dwBytes & 7;
                                                        if ( (dwBytes & 7) != 0 )
                                                        {
                                                          LODWORD(v1309) = 0;
                                                          LODWORD(v1323) = 0;
                                                          LODWORD(Size) = 0;
                                                          v211 = 0;
                                                          v212 = (unsigned __int8 *)v1325;
                                                          v213 = 0;
                                                          v214 = 0;
                                                          do
                                                          {
                                                            v215 = *v212++;
                                                            LODWORD(v1313) = v215;
                                                            LODWORD(Size) = 8 * v211;
                                                            if ( v211 >= 4 )
                                                            {
                                                              LODWORD(v1313) = (_DWORD)v1313 << (56 - Size);
                                                              v213 |= v1313;
                                                            }
                                                            else
                                                            {
                                                              LODWORD(v1313) = (_DWORD)v1313 << (24 - Size);
                                                              v214 |= v1313;
                                                            }
                                                            ++v211;
                                                          }
                                                          while ( (int)v211 < (int)v210 );
                                                          LODWORD(v1323) = v214;
                                                          v209 = uBytes_4;
                                                          LODWORD(v1309) = v213;
                                                          v22 = v1326;
                                                          lpMem = v212;
                                                          v208 = dwBytes;
                                                          v1319 = v28;
                                                          v1312 = v19;
                                                          LODWORD(Size) = 0;
                                                          v216 = v1309 ^ 0x699A899C;
                                                          v217 = v1323 ^ 0x92F65A5;
                                                          v218 = v1323 ^ 0x92F65A5;
                                                          v219 = v1309 ^ 0x699A899C;
                                                          if ( (dwBytes & 7) != 0 )
                                                          {
                                                            v220 = v1318;
                                                            v221 = Size;
                                                            do
                                                            {
                                                              v1316 = (size_t)(v220 + 1);
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
                                                              v220 = (_BYTE *)v1316;
                                                            }
                                                            while ( (int)v221 < (int)v210 );
                                                            v1318 = (void *)v1316;
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
                                                          LODWORD(v1323) = 0;
                                                          v217 = 0;
                                                          LODWORD(v1309) = -1;
                                                        }
                                                        v1316 = v208 >> 3;
                                                        if ( v208 >> 3 )
                                                        {
                                                          v224 = HIDWORD(v1300);
                                                          v225 = (unsigned __int8 *)lpMem;
                                                          v226 = v1318;
                                                          v227 = v1309;
                                                          v228 = v1323;
                                                          v229 = v1316;
                                                          LODWORD(Size) = HIDWORD(v1300) ^ 0xAB69605E;
                                                          LODWORD(v1310) = WORD2(v1300);
                                                          LODWORD(v1313) = 24670;
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
                                                            v235 = Size ^ v223 ^ v234 ^ v217 ^ v233;
                                                            v236 = v217
                                                                 ^ v233
                                                                 ^ (__ROR4__(v235, 22)
                                                                  + v1310 * __ROR4__(v235 + 1419157410, 27));
                                                            v237 = v235
                                                                 ^ (WORD1(v1300) * __ROR4__(v236 + v224, 9)
                                                                  - __ROR4__(v236, 30));
                                                            v238 = v236 ^ (v1313 * (v237 - v1310) - (v237 >> 13));
                                                            v239 = v237
                                                                 ^ (HIWORD(v1300) * __ROR4__(v238 ^ WORD1(v1300), 26)
                                                                  - __ROR4__(v238, 30));
                                                            v240 = v238 ^ (v224 - (v239 ^ 0xAB69605E));
                                                            v241 = v239
                                                                 ^ (WORD1(v1300) * (v240 ^ v1310))
                                                                 ^ __ROR4__(v240, 6);
                                                            v242 = v240
                                                                 ^ (__ROR4__(v241, 30)
                                                                  + v1313 * __ROR4__(v241 + v224, 15));
                                                            v243 = v241
                                                                 ^ (HIWORD(v1300) * __ROR4__(v242 + 1419157410, 14)
                                                                  - __ROR4__(v242, 24));
                                                            v244 = v242
                                                                 ^ __ROR4__(v243, 10)
                                                                 ^ (v1310 * __ROR4__(v243 ^ 0xAB69605E, 12));
                                                            v245 = v244
                                                                 ^ (HIWORD(v1300)
                                                                  * (v1313
                                                                   + __ROR4__(
                                                                       ~(v243
                                                                       ^ (v244 >> 10)
                                                                       ^ (WORD1(v1300) * (v244 ^ HIWORD(v1300)))),
                                                                       5)));
                                                            v246 = v243
                                                                 ^ (v244 >> 10)
                                                                 ^ (WORD1(v1300) * (v244 ^ HIWORD(v1300)))
                                                                 ^ (v245 - HIWORD(v1300))
                                                                 ^ 0xAB69605E;
                                                            v247 = v245
                                                                 ^ ((v246 >> 2)
                                                                  + v1310 * __ROR4__(HIWORD(v1300) ^ v246, 30));
                                                            v248 = v246
                                                                 ^ (__ROR4__(v247, 25)
                                                                  + WORD1(v1300) * __ROR4__(v247 - HIDWORD(v1300), 6));
                                                            v249 = v247 ^ (v1313 * (v248 ^ v1310) + __ROR4__(v248, 9));
                                                            v250 = v248
                                                                 ^ (__ROR4__(v249, 25)
                                                                  + HIWORD(v1300) * __ROR4__(WORD1(v1300) ^ v249, 27));
                                                            v224 = HIDWORD(v1300);
                                                            v251 = Size ^ v249 ^ v250;
                                                            v252 = v250 ^ (v1310 * (__ROR4__(v251, 3) - WORD1(v1300)));
                                                            v253 = v251
                                                                 ^ (v1313 * __ROR4__(v252 - HIDWORD(v1300), 1)
                                                                  - __ROR4__(v252, 6));
                                                            v254 = v252
                                                                 ^ (__ROR4__(v253, 18)
                                                                  + HIWORD(v1300) * __ROR4__(v253 - 1419157410, 29));
                                                            v255 = v253
                                                                 ^ (v1310 * __ROR4__(v254 - 1419157410, 17)
                                                                  - __ROR4__(v254, 14));
                                                            v256 = v254 ^ (v255 >> 3) ^ (WORD1(v1300) * (v255 ^ v1313));
                                                            v257 = __ROR4__(v256, 30);
                                                            v223 = v227 ^ v256;
                                                            v227 = v234;
                                                            v217 = v228
                                                                 ^ v255
                                                                 ^ v257
                                                                 ^ (v1313
                                                                  * __ROR4__(
                                                                      HIDWORD(v1300)
                                                                    ^ v254
                                                                    ^ (v255 >> 3)
                                                                    ^ (WORD1(v1300) * (v255 ^ v1313)),
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
                                                          v3 = v1302;
                                                          v22 = v1326;
                                                          v28 = (char *)v1319;
                                                          v19 = v1312;
                                                          v208 = dwBytes;
                                                        }
                                                        v258 = (_DWORD *)v1311;
                                                        for ( m = 0; m < v208; ++m )
                                                          v209 ^= *(_BYTE *)(v1311 + m);
                                                        if ( v209 != *(_QWORD *)(v208 + v1325) )
                                                        {
                                                          MemoryFree((void *)v1311);
                                                          goto LABEL_297;
                                                        }
                                                        v151 = v1299;
                                                        if ( (unsigned int)dwBytes < 4 )
                                                        {
                                                          v260 = v1311;
                                                          v261 = -1073741762;
LABEL_300:
                                                          v1310 = v260;
LABEL_330:
                                                          v20 = v261 | 0x10000000;
                                                          goto LABEL_345;
                                                        }
                                                        v1310 = v1311;
                                                        v1316 = v1311 + 4;
                                                        if ( v1311 + 4 < v1311 )
                                                          goto LABEL_338;
                                                        if ( (unsigned int)(dwBytes - 4) < 4 )
                                                        {
LABEL_303:
                                                          v262 = v1311;
                                                          v261 = -1073741762;
LABEL_304:
                                                          v1310 = v262;
                                                          goto LABEL_330;
                                                        }
                                                        v1319 = (void *)(v1311 + 8);
                                                        if ( v1311 + 8 < v1316 )
                                                          goto LABEL_338;
                                                        if ( (unsigned int)(dwBytes - 8) < *(_DWORD *)(v1311 + 4) )
                                                          goto LABEL_303;
                                                        if ( *(_DWORD *)(v1311 + 4) >= 0xFFFFFFF8 )
                                                        {
LABEL_338:
                                                          v261 = -1073741675;
                                                        }
                                                        else
                                                        {
                                                          v1300 = *(unsigned int *)(v1311 + 4);
                                                          v1311 = (SIZE_T)v1319 + v1300;
                                                          v1316 = (unsigned int)dwBytes;
                                                          if ( (char *)v258 + (unsigned int)dwBytes >= (char *)v1319 + v1300
                                                            && v1316 + (char *)v258 - v1300 - (_BYTE *)v1319 < 8 )
                                                          {
                                                            LODWORD(Size) = 0;
                                                            if ( v1319 )
                                                            {
                                                              if ( v1311 < (unsigned __int64)v1319 )
                                                              {
                                                                v260 = v1310;
                                                                v261 = -1073741675;
                                                                goto LABEL_300;
                                                              }
                                                              v263 = v1319;
                                                              if ( v1311 > (unsigned __int64)v1319 )
                                                              {
                                                                while ( v263 + 1 >= v263 )
                                                                {
                                                                  if ( (unsigned __int64)(v263 + 1) > v1311 )
                                                                    goto LABEL_323;
                                                                  v264 = *v263 + 4;
                                                                  if ( *v263 >= 0xFFFFFFFC )
                                                                    break;
                                                                  v265 = (SIZE_T)v263 + v264;
                                                                  if ( v265 < (unsigned __int64)v263 )
                                                                    break;
                                                                  if ( v265 > v1311 )
                                                                    goto LABEL_323;
                                                                  LODWORD(Size) = Size + 1;
                                                                  v263 = (_DWORD *)((char *)v263 + v264);
                                                                  if ( v265 >= v1311 )
                                                                    goto LABEL_322;
                                                                }
                                                                v261 = -1073741675;
                                                                goto LABEL_330;
                                                              }
                                                              v1310 = (SIZE_T)v258;
LABEL_322:
                                                              if ( v263 != (_DWORD *)v1311 )
                                                              {
LABEL_323:
                                                                v261 = -1073741811;
                                                                goto LABEL_330;
                                                              }
                                                            }
                                                            else
                                                            {
                                                              v1310 = (SIZE_T)v258;
                                                            }
                                                            v266 = v258[1] == 0;
                                                            LODWORD(v1325) = *v258;
                                                            if ( v266 )
                                                            {
                                                              v268 = 0;
                                                            }
                                                            else
                                                            {
                                                              v267 = GetProcessHeap();
                                                              v268 = HeapAlloc(v267, 8u, v1300);
                                                              if ( !v268 )
                                                              {
                                                                v261 = -1073741801;
LABEL_329:
                                                                v151 = v1299;
                                                                goto LABEL_330;
                                                              }
                                                            }
                                                            v261 = 0;
                                                            v1320 = v268;
                                                            if ( v1319 )
                                                              memcpy_0(v268, v1319, v1300);
                                                            LODWORD(v1298) = Size;
                                                            if ( (_DWORD)v1325 != (_DWORD)Size )
                                                              v261 = -1073741762;
                                                            goto LABEL_329;
                                                          }
                                                          v261 = -1073741762;
                                                        }
                                                        v262 = v1310;
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
                                        v151 = v1299;
LABEL_343:
                                        Src = v171;
LABEL_344:
                                        v1299 = v151;
LABEL_345:
                                        if ( !v151 )
                                        {
LABEL_350:
                                          v270 = v1303;
                                          if ( v1303 )
                                          {
                                            v1316 = *((_QWORD *)v1303 + 1);
                                            if ( v1316 )
                                            {
                                              v271 = GetProcessHeap();
                                              HeapFree(v271, 0, (LPVOID)v1316);
                                              v270 = v1303;
                                              *((_QWORD *)v1303 + 1) = 0;
                                            }
                                            v1316 = v270[3];
                                            if ( v1316 )
                                            {
                                              v272 = GetProcessHeap();
                                              HeapFree(v272, 0, (LPVOID)v1316);
                                              v270 = v1303;
                                              *((_QWORD *)v1303 + 3) = 0;
                                            }
                                            v1316 = v270[5];
                                            if ( v1316 )
                                            {
                                              v273 = GetProcessHeap();
                                              HeapFree(v273, 0, (LPVOID)v1316);
                                              *((_QWORD *)v1303 + 5) = 0;
                                            }
                                            v274 = GetProcessHeap();
                                            HeapFree(v274, 0, v1303);
                                          }
                                          if ( v1308 )
                                          {
                                            v275 = GetProcessHeap();
                                            HeapFree(v275, 0, v1308);
                                          }
                                          if ( v1304 )
                                          {
                                            v276 = GetProcessHeap();
                                            HeapFree(v276, 0, v1304);
                                          }
                                          v277 = v1314;
                                          if ( v1314 )
                                          {
                                            v1316 = *((_QWORD *)v1314 + 1);
                                            if ( v1316 )
                                            {
                                              v278 = GetProcessHeap();
                                              HeapFree(v278, 0, (LPVOID)v1316);
                                              v277 = v1314;
                                              *((_QWORD *)v1314 + 1) = 0;
                                            }
                                            v1316 = v277[3];
                                            if ( v1316 )
                                            {
                                              v279 = GetProcessHeap();
                                              HeapFree(v279, 0, (LPVOID)v1316);
                                              v277 = v1314;
                                              *((_QWORD *)v1314 + 3) = 0;
                                            }
                                            v1316 = v277[5];
                                            if ( v1316 )
                                            {
                                              v280 = GetProcessHeap();
                                              HeapFree(v280, 0, (LPVOID)v1316);
                                              *((_QWORD *)v1314 + 5) = 0;
                                            }
                                            v281 = GetProcessHeap();
                                            HeapFree(v281, 0, v1314);
                                          }
                                          if ( v1310 )
                                          {
                                            v282 = GetProcessHeap();
                                            HeapFree(v282, 0, (LPVOID)v1310);
                                          }
LABEL_372:
                                          if ( v20 < 0 )
                                            goto LABEL_438;
                                          if ( !(_DWORD)v1298 )
                                            goto LABEL_374;
                                          if ( !v1320 )
                                          {
                                            v20 = -1073741811;
                                            goto LABEL_438;
                                          }
                                          if ( (char *)v1320 + 4 < v1320 )
                                          {
                                            v20 = -1073741675;
                                            goto LABEL_438;
                                          }
                                          v283 = 0;
                                          if ( *(_DWORD *)v1320 )
                                            v283 = (int *)((char *)v1320 + 4);
                                          if ( *(_DWORD *)v1320 != 4 )
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
                                          if ( (_DWORD)v1298 != 6 )
                                          {
LABEL_374:
                                            v20 = -1073425151;
                                            goto LABEL_438;
                                          }
                                          v284 = v1320;
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
                                              v289 = v1320;
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
                                                    v292 = (unsigned int *)v1320;
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
                                                    v295 = v1320;
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
                                                          v300 = v1320;
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
                                                              if ( v1327 != v288 )
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
                                        HeapFree(v269, 0, v1299);
                                        goto LABEL_350;
                                      }
LABEL_203:
                                      v165 = Src;
                                      v151 = v1299;
                                      v163 = v1303;
                                      v164 = v1304;
                                      v166 = v1308;
                                      goto LABEL_204;
                                    }
                                  }
                                }
                              }
                            }
                          }
                          v152 = GetProcessHeap();
                          HeapFree(v152, 0, (LPVOID)v1300);
                        }
                      }
                    }
                  }
                }
                v20 = -805306219;
                v151 = v1299;
                goto LABEL_345;
              }
            }
            else
            {
              v1312 = v126;
            }
          }
          v117 = -1073741801;
          v133 = v1312;
          v1316 = *((_QWORD *)v1312 + 1);
          if ( v1316 )
          {
            v134 = GetProcessHeap();
            HeapFree(v134, 0, (LPVOID)v1316);
            v133 = v1312;
            *((_QWORD *)v1312 + 1) = 0;
          }
          v1316 = v133[3];
          if ( v1316 )
          {
            v135 = GetProcessHeap();
            HeapFree(v135, 0, (LPVOID)v1316);
            v133 = v1312;
            *((_QWORD *)v1312 + 3) = 0;
          }
          v1316 = v133[5];
          if ( v1316 )
          {
            v136 = GetProcessHeap();
            HeapFree(v136, 0, (LPVOID)v1316);
            *((_QWORD *)v1312 + 5) = 0;
          }
          v137 = GetProcessHeap();
          HeapFree(v137, 0, v1312);
        }
        else
        {
          v117 = -1073741801;
        }
        v118 = v1303;
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
    v55 = v1310;
    if ( v54 >= 4 )
    {
      if ( v54 + (unsigned int)v1310 >= (unsigned int)v1310 )
      {
        v55 = v54 + v1310;
        LODWORD(v1309) = 5;
        v20 = 0;
LABEL_95:
        v59 = v1309;
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
0x1800a4100  mov     [rsp-8+arg_8], rbx
0x1800a4105  push    rbp
0x1800a4106  push    rsi
0x1800a4107  push    rdi
0x1800a4108  push    r12
0x1800a410a  push    r13
0x1800a410c  push    r14
0x1800a410e  push    r15
0x1800a4110  lea     rbp, [rsp-2D0h]
0x1800a4118  sub     rsp, 3D0h
0x1800a411f  xor     eax, eax
0x1800a4121  mov     [rbp+300h+var_D8], r8
0x1800a4128  mov     [rbp+300h+StringUuid], rax
0x1800a412f  mov     r15d, 80070057h
0x1800a4135  mov     [rbp+300h+lpMem], rax
0x1800a4139  mov     [rbp+300h+pcchLength], rax
0x1800a413d  mov     [rbp+300h+var_278], rax
0x1800a4144  test    r8, r8
0x1800a4147  jz      loc_1800AF123
0x1800a414d  lea     rdx, [rbp+300h+StringUuid]; StringUuid
0x1800a4154  mov     [r8], ax
0x1800a4158  mov     r13d, eax
0x1800a415b  mov     edi, eax
0x1800a415d  call    cs:__imp_UuidToStringW
0x1800a4164  nop     dword ptr [rax+rax+00h]
0x1800a4169  test    eax, eax
0x1800a416b  jnz     loc_1800AF0E5
0x1800a4171  mov     r11d, 7FFFFFFFh
0x1800a4177  lea     r14, aTerminalservic_5; "TerminalServices-RemoteConnectionManage"...
0x1800a417e  mov     edx, r11d; unsigned __int64
0x1800a4181  lea     r8, [rbp+300h+lpMem]; unsigned __int64 *
0x1800a4185  mov     rcx, r14; unsigned __int16 *
0x1800a4188  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800a418d  mov     r15d, eax
0x1800a4190  test    eax, eax
0x1800a4192  jns     loc_1800A4231
0x1800a4198  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a419d  mov     ecx, cs:dword_18012E170
0x1800a41a3  cmp     ecx, 3
0x1800a41a6  jbe     loc_1800AF0E5
0x1800a41ac  lea     rax, aGetinitialprog; "GetInitialProgram"
0x1800a41b3  mov     [rbp+300h+var_C0], r14
0x1800a41ba  mov     [rbp+300h+var_B8], rax
0x1800a41c1  lea     rdx, word_18011A50A
0x1800a41c8  lea     rax, aCslqueryGetini_1; "CSLQuery::GetInitialProgram - StringCch"...
0x1800a41cf  mov     [rbp+300h+var_228], r15d
0x1800a41d6  mov     [rbp+300h+var_B0], rax
0x1800a41dd  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800a41e4  mov     [rbp+300h+var_150], rax
0x1800a41eb  lea     rax, [rbp+300h+var_C0]
0x1800a41f2  mov     [rsp+400h+var_3C0], rax
0x1800a41f7  lea     rax, [rbp+300h+var_B8]
0x1800a41fe  mov     [rsp+400h+var_3C8], rax
0x1800a4203  lea     rax, [rbp+300h+var_228]
0x1800a420a  mov     [rsp+400h+var_3D0], rax
0x1800a420f  lea     rax, [rbp+300h+var_B0]
0x1800a4216  mov     [rsp+400h+var_3D8], rax
0x1800a421b  lea     rax, [rbp+300h+var_150]
0x1800a4222  mov     [rsp+400h+var_3E0], rax
0x1800a4227  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800a422c  jmp     loc_1800AF0E5
0x1800a4231  mov     rcx, [rbp+300h+StringUuid]; unsigned __int16 *
0x1800a4238  lea     r8, [rbp+300h+pcchLength]; unsigned __int64 *
0x1800a423c  mov     rdx, r11; unsigned __int64
0x1800a423f  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800a4244  mov     r15d, eax
0x1800a4247  test    eax, eax
0x1800a4249  jns     loc_1800A42E5
0x1800a424f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a4254  mov     eax, cs:dword_18012E170
0x1800a425a  cmp     eax, 3
0x1800a425d  jbe     loc_1800AF0E5
0x1800a4263  mov     rax, [rbp+300h+StringUuid]
0x1800a426a  lea     rdx, byte_18011A879
0x1800a4271  mov     [rbp+300h+var_148], rax
0x1800a4278  lea     rax, aGetinitialprog; "GetInitialProgram"
0x1800a427f  mov     [rbp+300h+var_140], rax
0x1800a4286  lea     rax, aCslqueryGetini_1; "CSLQuery::GetInitialProgram - StringCch"...
0x1800a428d  mov     [rbp+300h+var_138], rax
0x1800a4294  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800a429b  mov     [rbp+300h+var_108], rax
0x1800a42a2  lea     rax, [rbp+300h+var_148]
0x1800a42a9  mov     [rsp+400h+var_3C0], rax
0x1800a42ae  lea     rax, [rbp+300h+var_140]
0x1800a42b5  mov     [rsp+400h+var_3C8], rax
0x1800a42ba  lea     rax, [rbp+300h+var_224]
0x1800a42c1  mov     [rsp+400h+var_3D0], rax
0x1800a42c6  lea     rax, [rbp+300h+var_138]
0x1800a42cd  mov     [rsp+400h+var_3D8], rax
0x1800a42d2  lea     rax, [rbp+300h+var_108]
0x1800a42d9  mov     [rbp+300h+var_224], r15d
0x1800a42e0  jmp     loc_1800A4222
0x1800a42e5  lea     rsi, aInitialprogram; "-InitialProgram"
0x1800a42ec  mov     rdx, r11; unsigned __int64
0x1800a42ef  mov     rcx, rsi; unsigned __int16 *
0x1800a42f2  lea     r8, [rbp+300h+var_278]; unsigned __int64 *
0x1800a42f9  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800a42fe  mov     r15d, eax
0x1800a4301  test    eax, eax
0x1800a4303  jns     loc_1800A4398
0x1800a4309  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a430e  mov     eax, cs:dword_18012E170
0x1800a4314  cmp     eax, 3
0x1800a4317  jbe     loc_1800AF0E5
0x1800a431d  lea     rax, aGetinitialprog; "GetInitialProgram"
0x1800a4324  mov     [rbp+300h+var_130], rsi
0x1800a432b  mov     [rbp+300h+var_128], rax
0x1800a4332  lea     rdx, byte_180119FB1
0x1800a4339  lea     rax, aCslqueryGetini_1; "CSLQuery::GetInitialProgram - StringCch"...
0x1800a4340  mov     [rbp+300h+var_220], r15d
0x1800a4347  mov     [rbp+300h+var_120], rax
0x1800a434e  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800a4355  mov     [rbp+300h+var_118], rax
0x1800a435c  lea     rax, [rbp+300h+var_130]
0x1800a4363  mov     [rsp+400h+var_3C0], rax
0x1800a4368  lea     rax, [rbp+300h+var_128]
0x1800a436f  mov     [rsp+400h+var_3C8], rax
0x1800a4374  lea     rax, [rbp+300h+var_220]
0x1800a437b  mov     [rsp+400h+var_3D0], rax
0x1800a4380  lea     rax, [rbp+300h+var_120]
0x1800a4387  mov     [rsp+400h+var_3D8], rax
0x1800a438c  lea     rax, [rbp+300h+var_118]
0x1800a4393  jmp     loc_1800A4222
0x1800a4398  mov     rdx, [rbp+300h+var_278]
0x1800a439f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800a43a6  add     rdx, [rbp+300h+pcchLength]
0x1800a43aa  mov     eax, 2
0x1800a43af  mov     rbx, [rbp+300h+lpMem]
0x1800a43b3  add     rbx, 3
0x1800a43b7  add     rbx, rdx
0x1800a43ba  mul     rbx
0x1800a43bd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a43c4  cmovb   rax, rcx
0x1800a43c8  mov     rcx, rax; unsigned __int64
0x1800a43cb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800a43d0  mov     [rbp+300h+psz], rax
0x1800a43d7  mov     r13, rax
0x1800a43da  test    rax, rax
0x1800a43dd  jnz     short loc_1800A43EA
0x1800a43df  mov     r15d, 8007000Eh
0x1800a43e5  jmp     loc_1800AF0E5
0x1800a43ea  mov     rax, [rbp+300h+StringUuid]
0x1800a43f1  lea     r8, aWsWsWs; "%ws%ws%ws"
0x1800a43f8  mov     [rsp+400h+var_3D8], rsi
0x1800a43fd  mov     r9, r14
0x1800a4400  mov     rdx, rbx; unsigned __int64
0x1800a4403  mov     [rsp+400h+var_3E0], rax
0x1800a4408  mov     rcx, r13; unsigned __int16 *
0x1800a440b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a4410  mov     r15d, eax
0x1800a4413  xor     eax, eax
0x1800a4415  test    r15d, r15d
0x1800a4418  jns     loc_1800A44AC
0x1800a441e  mov     eax, cs:dword_18012E170
0x1800a4424  cmp     eax, 3
0x1800a4427  jbe     loc_1800AF0E5
0x1800a442d  lea     rax, aGetinitialprog; "GetInitialProgram"
0x1800a4434  mov     [rbp+300h+var_200], r15d
0x1800a443b  mov     [rbp+300h+var_110], rax
0x1800a4442  lea     rdx, word_18011A1CE
0x1800a4449  lea     rax, aCslqueryGetini_0; "CSLQuery::GetInitialProgram - StringCch"...
0x1800a4450  xor     r9d, r9d
0x1800a4453  mov     [rbp+300h+var_D0], rax
0x1800a445a  lea     rcx, dword_18012E170
0x1800a4461  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800a4468  xor     r8d, r8d
0x1800a446b  mov     [rbp+300h+var_100], rax
0x1800a4472  lea     rax, [rbp+300h+var_110]
0x1800a4479  mov     [rsp+400h+var_3C8], rax
0x1800a447e  lea     rax, [rbp+300h+var_200]
0x1800a4485  mov     [rsp+400h+var_3D0], rax
0x1800a448a  lea     rax, [rbp+300h+var_D0]
0x1800a4491  mov     [rsp+400h+var_3D8], rax
0x1800a4496  lea     rax, [rbp+300h+var_100]
0x1800a449d  mov     [rsp+400h+var_3E0], rax
0x1800a44a2  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800a44a7  jmp     loc_1800AF0E5
0x1800a44ac  mov     [rbp+300h+var_230], rax
0x1800a44b3  mov     [rbp+300h+var_254], eax
0x1800a44b9  mov     [rbp+300h+var_278], rax
0x1800a44c0  call    cs:__imp_GetProcessHeap
0x1800a44c7  nop     dword ptr [rax+rax+00h]
0x1800a44cc  mov     ebx, 8
0x1800a44d1  mov     r8d, 0A0h; dwBytes
0x1800a44d7  mov     rcx, rax; hHeap
0x1800a44da  mov     edx, ebx; dwFlags
0x1800a44dc  call    cs:__imp_HeapAlloc
0x1800a44e3  nop     dword ptr [rax+rax+00h]
0x1800a44e8  mov     r14, rax
0x1800a44eb  test    rax, rax
0x1800a44ee  jnz     short loc_1800A4530
0x1800a44f0  mov     esi, 0C0000017h
0x1800a44f5  mov     r15d, esi
0x1800a44f8  mov     ebx, [rbp+300h+var_254]
0x1800a44fe  lea     rcx, [rbp+300h+var_278]
0x1800a4505  call    ?Reset@?$SP@EV?$SP_HLOCAL@E@@@@QEAAXXZ; SP<uchar,SP_HLOCAL<uchar>>::Reset(void)
0x1800a450a  test    r15d, r15d
0x1800a450d  jns     loc_1800AEFC3
0x1800a4513  xor     ebx, ebx
0x1800a4515  cmp     r15d, 0D0000034h
0x1800a451c  jnz     loc_1800AEF91
0x1800a4522  mov     r15d, 0C004F012h
0x1800a4528  mov     rdi, rbx
0x1800a452b  jmp     loc_1800AEFE0
0x1800a4530  movups  xmm0, cs:?DecryptionCipher@?1??WarbirdUmGetDecryptionCipher@@9@4PAEA; uchar near * `WarbirdUmGetDecryptionCipher'::`2'::DecryptionCipher
0x1800a4537  xor     eax, eax
0x1800a4539  xor     r12d, r12d
0x1800a453c  mov     dword ptr [rbp+300h+uBytes], eax
0x1800a453f  movups  xmmword ptr [r14], xmm0
0x1800a4543  mov     [rbp+300h+var_2D8], r12d
0x1800a4547  movups  xmm1, cs:xmmword_18012E5A0
0x1800a454e  movups  xmmword ptr [r14+10h], xmm1
0x1800a4553  movups  xmm0, cs:xmmword_18012E5B0
0x1800a455a  movups  xmmword ptr [r14+20h], xmm0
0x1800a455f  movups  xmm1, cs:xmmword_18012E5C0
0x1800a4566  movups  xmmword ptr [r14+30h], xmm1
0x1800a456b  movups  xmm0, cs:xmmword_18012E5D0
0x1800a4572  movups  xmmword ptr [r14+40h], xmm0
0x1800a4577  movups  xmm1, cs:xmmword_18012E5E0
0x1800a457e  movups  xmmword ptr [r14+50h], xmm1
0x1800a4583  movups  xmm0, cs:xmmword_18012E5F0
0x1800a458a  movups  xmmword ptr [r14+60h], xmm0
0x1800a458f  movups  xmm1, cs:xmmword_18012E600
0x1800a4596  movups  xmmword ptr [r14+70h], xmm1
0x1800a459b  movups  xmm0, cs:xmmword_18012E610
0x1800a45a2  movups  xmmword ptr [r14+80h], xmm0
0x1800a45aa  movups  xmm1, cs:xmmword_18012E620
0x1800a45b1  movups  xmmword ptr [r14+90h], xmm1
0x1800a45b9  call    cs:__imp_GetProcessHeap
0x1800a45c0  nop     dword ptr [rax+rax+00h]
0x1800a45c5  mov     r8, rbx; dwBytes
0x1800a45c8  mov     edx, ebx; dwFlags
0x1800a45ca  mov     rcx, rax; hHeap
0x1800a45cd  call    cs:__imp_HeapAlloc
0x1800a45d4  nop     dword ptr [rax+rax+00h]
0x1800a45d9  mov     esi, 0C4h
0x1800a45de  mov     [rbp+300h+var_2A0], 0FFFFFFFFh
0x1800a45e5  mov     [rsp+400h+Src], rax
0x1800a45ea  mov     r15d, 0D0000095h
0x1800a45f0  mov     [rbp+300h+var_2C8], rsi
0x1800a45f4  mov     r11, rax
0x1800a45f7  mov     [rsp+400h+var_390], r15d
0x1800a45fc  mov     rbx, 0C81ECB17B1B54A58h
0x1800a4606  mov     [rbp+300h+var_320], 0D0000017h
0x1800a460d  mov     rdi, 7F1137FAB69605Eh
0x1800a4617  test    rax, rax
0x1800a461a  jnz     short loc_1800A4629
0x1800a461c  mov     esi, 0C0000017h
0x1800a4621  xor     r13d, r13d
0x1800a4624  jmp     loc_1800A6B93
0x1800a4629  mov     rax, cs:?nDecryptionKey@?1??WarbirdUmGetDecryptionKey@@9@4_KA; unsigned __int64 `WarbirdUmGetDecryptionKey'::`2'::nDecryptionKey
0x1800a4630  mov     [r11], rax
0x1800a4633  rdtsc
0x1800a4635  shl     rdx, 20h; cchMax
0x1800a4639  or      rax, rdx
0x1800a463c  mov     [rbp+300h+var_2D0], rax
0x1800a4640  lea     r8, [rbp+300h+pcchLength]; pcchLength
0x1800a4644  mov     [rbp+300h+pcchLength], r12
0x1800a4648  mov     rcx, r13; psz
0x1800a464b  call    StringCchLengthW
0x1800a4650  test    eax, eax
0x1800a4652  jns     short loc_1800A465E
0x1800a4654  mov     esi, 0C000003Eh
0x1800a4659  jmp     loc_1800A6B8E
0x1800a465e  mov     rax, [rbp+300h+pcchLength]
0x1800a4662  lea     eax, ds:6[rax*2]
0x1800a4669  cmp     eax, 4
0x1800a466c  jb      loc_1800A6B84
0x1800a4672  add     eax, esi
0x1800a4674  mov     [rbp+300h+var_308], r12
0x1800a4678  or      r10d, 0FFFFFFFFh
0x1800a467c  xor     r13d, r13d
0x1800a467f  xor     r9d, r9d
0x1800a4682  mov     ecx, r10d
0x1800a4685  cmp     eax, esi
0x1800a4687  mov     r8d, 0C0000095h
0x1800a468d  cmovnb  ecx, eax
0x1800a4690  sbb     esi, esi
0x1800a4692  and     esi, r8d
0x1800a4695  add     esi, 10000000h
0x1800a469b  cmp     eax, 0C4h
0x1800a46a0  jb      loc_1800A6B10
0x1800a46a6  lea     eax, [rcx+8]
0x1800a46a9  mov     edx, r10d
0x1800a46ac  cmp     eax, ecx
0x1800a46ae  cmovnb  edx, eax
0x1800a46b1  sbb     esi, esi
0x1800a46b3  and     esi, r8d
0x1800a46b6  add     esi, 10000000h
0x1800a46bc  cmp     eax, ecx
0x1800a46be  jb      loc_1800A6B10
0x1800a46c4  lea     eax, [rdx+8]
0x1800a46c7  mov     ecx, r10d
0x1800a46ca  cmp     eax, edx
0x1800a46cc  cmovnb  ecx, eax
0x1800a46cf  sbb     esi, esi
0x1800a46d1  and     esi, r8d
0x1800a46d4  mov     dword ptr [rsp+400h+var_3B0], ecx
0x1800a46d8  add     esi, 10000000h
0x1800a46de  cmp     eax, edx
  ... truncated ...
```
