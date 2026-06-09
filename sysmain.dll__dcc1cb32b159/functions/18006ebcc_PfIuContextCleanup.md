# PfIuContextCleanup

- ea: `0x18006ebcc`
- end: `0x18006ed16`
- name: `PfIuContextCleanup`
- size: `330`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18006a020`

## callees

- `0x18003cbe4`
- `0x180065530`
- `0x1800686d0`
- `0x18006ebcc`
- `0x18006ed1c`
- `0x1800923f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006ec4e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006ec4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ec14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ec14`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18006ec0b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18006ec0b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006ecf3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006ecf3`

## string_xrefs

- `0x18006ec23`: `PfIuBatteryPaths`

## pseudocode

```c
__int64 __fastcall PfIuContextCleanup(__int64 a1)
{
  void *v2; // rbx
  __int64 result; // rax
  unsigned __int64 v4; // [rsp+40h] [rbp+8h] BYREF

  if ( *(_QWORD *)(a1 + 64) )
  {
    PfIuCheckAndMergeHistories();
    if ( 5604LL * (**(_DWORD **)(a1 + 64) & 1) + *(_QWORD *)(a1 + 64) + 8LL )
      PfIuHistorySave();
    v2 = *(void **)(a1 + 56);
    UnmapViewOfFile(*(LPCVOID *)(a1 + 64));
    CloseHandle(v2);
  }
  if ( *(_DWORD *)(a1 + 88) )
    RegSetValueExW(
      *(HKEY *)(*(_QWORD *)&PfSvcGlobals + 1432LL),
      L"PfIuBatteryPaths",
      0,
      7u,
      *(const BYTE **)(a1 + 80),
      *(_DWORD *)(a1 + 92));
  PfsMultiStringContextCleanup(a1 + 72);
  v4 = 0x7FFFFFFFFFFFFFFFLL;
  PfsActionItemQueueEx((LPCRITICAL_SECTION)(*(_QWORD *)&PfSvcGlobals + 1720LL), 0x33u, &v4, 0);
  v4 = 0x7FFFFFFFFFFFFFFFLL;
  PfsActionItemQueueEx((LPCRITICAL_SECTION)(*(_QWORD *)&PfSvcGlobals + 1720LL), 0x34u, &v4, 0);
  v4 = 0x7FFFFFFFFFFFFFFFLL;
  PfsActionItemQueueEx((LPCRITICAL_SECTION)(*(_QWORD *)&PfSvcGlobals + 1720LL), 0x35u, &v4, 0);
  if ( *(_QWORD *)(a1 + 104) )
  {
    PfIuAggregatedPredictionStatsLog(a1);
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, *(LPVOID *)(a1 + 104));
  }
  result = *(_QWORD *)&PfSvcGlobals;
  *(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 3712LL) = 0;
  return result;
}

```

## disassembly

```asm
0x18006ebcc  mov     [rsp+arg_8], rbx
0x18006ebd1  push    rdi
0x18006ebd2  sub     rsp, 30h
0x18006ebd6  cmp     qword ptr [rcx+40h], 0
0x18006ebdb  mov     rdi, rcx
0x18006ebde  jz      short loc_18006EC1A
0x18006ebe0  call    PfIuCheckAndMergeHistories
0x18006ebe5  mov     rdx, [rdi+40h]
0x18006ebe9  mov     eax, [rdx]
0x18006ebeb  lea     rcx, [rdx+8]
0x18006ebef  and     eax, 1
0x18006ebf2  imul    rax, 15E4h
0x18006ebf9  add     rcx, rax
0x18006ebfc  jz      short loc_18006EC03
0x18006ebfe  call    PfIuHistorySave
0x18006ec03  mov     rcx, [rdi+40h]; lpBaseAddress
0x18006ec07  mov     rbx, [rdi+38h]
0x18006ec0b  call    cs:__imp_UnmapViewOfFile
0x18006ec11  mov     rcx, rbx; hObject
0x18006ec14  call    cs:__imp_CloseHandle
0x18006ec1a  cmp     dword ptr [rdi+58h], 0
0x18006ec1e  jz      short loc_18006EC54
0x18006ec20  mov     eax, [rdi+5Ch]
0x18006ec23  lea     rdx, aPfiubatterypat; "PfIuBatteryPaths"
0x18006ec2a  mov     rcx, cs:PfSvcGlobals
0x18006ec31  mov     r9d, 7; dwType
0x18006ec37  mov     [rsp+38h+cbData], eax; cbData
0x18006ec3b  xor     r8d, r8d; Reserved
0x18006ec3e  mov     rax, [rdi+50h]
0x18006ec42  mov     [rsp+38h+lpData], rax; lpData
0x18006ec47  mov     rcx, [rcx+598h]; hKey
0x18006ec4e  call    cs:__imp_RegSetValueExW
0x18006ec54  lea     rcx, [rdi+48h]
0x18006ec58  call    PfsMultiStringContextCleanup
0x18006ec5d  mov     rcx, cs:PfSvcGlobals
0x18006ec64  lea     r8, [rsp+38h+arg_0]
0x18006ec69  xor     r9d, r9d
0x18006ec6c  mov     rbx, 7FFFFFFFFFFFFFFFh
0x18006ec76  add     rcx, 6B8h; lpCriticalSection
0x18006ec7d  mov     [rsp+38h+arg_0], rbx
0x18006ec82  lea     edx, [r9+33h]
0x18006ec86  call    PfsActionItemQueueEx
0x18006ec8b  mov     rcx, cs:PfSvcGlobals
0x18006ec92  lea     r8, [rsp+38h+arg_0]
0x18006ec97  xor     r9d, r9d
0x18006ec9a  mov     [rsp+38h+arg_0], rbx
0x18006ec9f  add     rcx, 6B8h; lpCriticalSection
0x18006eca6  lea     edx, [r9+34h]
0x18006ecaa  call    PfsActionItemQueueEx
0x18006ecaf  mov     rcx, cs:PfSvcGlobals
0x18006ecb6  lea     r8, [rsp+38h+arg_0]
0x18006ecbb  xor     r9d, r9d
0x18006ecbe  mov     [rsp+38h+arg_0], rbx
0x18006ecc3  add     rcx, 6B8h; lpCriticalSection
0x18006ecca  lea     edx, [r9+35h]
0x18006ecce  call    PfsActionItemQueueEx
0x18006ecd3  cmp     qword ptr [rdi+68h], 0
0x18006ecd8  jz      short loc_18006ECF9
0x18006ecda  mov     rcx, rdi
0x18006ecdd  call    PfIuAggregatedPredictionStatsLog
0x18006ece2  mov     rcx, cs:PfSvcGlobals
0x18006ece9  xor     edx, edx; dwFlags
0x18006eceb  mov     r8, [rdi+68h]; lpMem
0x18006ecef  mov     rcx, [rcx+58h]; hHeap
0x18006ecf3  call    cs:__imp_HeapFree
0x18006ecf9  mov     rax, cs:PfSvcGlobals
0x18006ed00  mov     rbx, [rsp+38h+arg_8]
0x18006ed05  mov     qword ptr [rax+0E80h], 0
0x18006ed10  add     rsp, 30h
0x18006ed14  pop     rdi
0x18006ed15  retn
```
