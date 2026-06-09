# CStringBlobT<ulong>::Clear(void)

- ea: `0x180078cd4`
- end: `0x180078d3e`
- name: `?Clear@?$CStringBlobT@K@@QEAAXXZ`
- size: `106`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800756e8`
- `0x18007c6ec`
- `0x18007e1d8`

## callees

- `0x180002aac`
- `0x180078cd4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078ce5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078ce5`

## pseudocode

```c
bool __fastcall CStringBlobT<unsigned long>::Clear(__int64 a1)
{
  void *v2; // rcx
  void *v3; // rdx
  void *v4; // rdx
  bool result; // al

  v2 = *(void **)a1;
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *(_QWORD *)a1 = 0;
  }
  v3 = *(void **)(a1 + 16);
  *(_DWORD *)(a1 + 8) = 0;
  CWinHeap::Free((CWinHeap *)&g_heap, v3);
  v4 = *(void **)(a1 + 32);
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  result = CWinHeap::Free((CWinHeap *)&g_heap, v4);
  *(_QWORD *)(a1 + 32) = 0;
  *(_DWORD *)(a1 + 40) = 0;
  return result;
}

```

## disassembly

```asm
0x180078cd4  push    rbx
0x180078cd6  sub     rsp, 20h
0x180078cda  mov     rbx, rcx
0x180078cdd  mov     rcx, [rcx]; pv
0x180078ce0  test    rcx, rcx
0x180078ce3  jz      short loc_180078CF2
0x180078ce5  call    cs:__imp_CoTaskMemFree
0x180078ceb  mov     qword ptr [rbx], 0
0x180078cf2  mov     rdx, [rbx+10h]; void *
0x180078cf6  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x180078cfd  mov     dword ptr [rbx+8], 0
0x180078d04  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x180078d09  mov     rdx, [rbx+20h]; void *
0x180078d0d  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x180078d14  mov     qword ptr [rbx+10h], 0
0x180078d1c  mov     qword ptr [rbx+18h], 0
0x180078d24  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x180078d29  mov     qword ptr [rbx+20h], 0
0x180078d31  mov     dword ptr [rbx+28h], 0
0x180078d38  add     rsp, 20h
0x180078d3c  pop     rbx
0x180078d3d  retn
```
