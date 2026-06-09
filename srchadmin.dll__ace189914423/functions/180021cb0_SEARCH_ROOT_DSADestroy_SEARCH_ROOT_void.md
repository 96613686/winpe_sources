# SEARCH_ROOT::DSADestroy(SEARCH_ROOT *,void *)

- ea: `0x180021cb0`
- end: `0x180021cc8`
- name: `?DSADestroy@SEARCH_ROOT@@SAHPEAU1@PEAX@Z`
- size: `24`
- prototype: `int __stdcall(void *p, void *pData)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021cb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021cb8`

## pseudocode

```c
__int64 __fastcall SEARCH_ROOT::DSADestroy(LPVOID *p, void *pData)
{
  CoTaskMemFree(p[1]);
  return 1;
}

```

## disassembly

```asm
0x180021cb0  sub     rsp, 28h
0x180021cb4  mov     rcx, [rcx+8]; pv
0x180021cb8  call    cs:__imp_CoTaskMemFree
0x180021cbe  mov     eax, 1
0x180021cc3  add     rsp, 28h
0x180021cc7  retn
```
