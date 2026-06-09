# PROCESSED_SEARCH_ROOT::DSADestroy(PROCESSED_SEARCH_ROOT *,void *)

- ea: `0x180021c80`
- end: `0x180021ca8`
- name: `?DSADestroy@PROCESSED_SEARCH_ROOT@@SAHPEAU1@PEAX@Z`
- size: `40`
- prototype: `int __stdcall(void *p, void *pData)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021cd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021c8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021c97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021c8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021c97`

## pseudocode

```c
__int64 __fastcall PROCESSED_SEARCH_ROOT::DSADestroy(LPVOID *p, void *pData)
{
  CoTaskMemFree(p[1]);
  CoTaskMemFree(p[2]);
  return 1;
}

```

## disassembly

```asm
0x180021c80  push    rbx
0x180021c82  sub     rsp, 20h
0x180021c86  mov     rbx, rcx
0x180021c89  mov     rcx, [rcx+8]; pv
0x180021c8d  call    cs:__imp_CoTaskMemFree
0x180021c93  mov     rcx, [rbx+10h]; pv
0x180021c97  call    cs:__imp_CoTaskMemFree
0x180021c9d  mov     eax, 1
0x180021ca2  add     rsp, 20h
0x180021ca6  pop     rbx
0x180021ca7  retn
```
