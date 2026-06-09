# Free_SPP_ENVIRONMENT_PROP(_SPP_ENVIRONMENT_PROP *)

- ea: `0x180034804`
- end: `0x180034839`
- name: `?Free_SPP_ENVIRONMENT_PROP@@YAXPEAU_SPP_ENVIRONMENT_PROP@@@Z`
- size: `53`
- prototype: `void __fastcall(struct _SPP_ENVIRONMENT_PROP *)`
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002584`
- `0x180008ed0`
- `0x180018f10`
- `0x1800192a8`
- `0x180034840`
- `0x1800349d0`

## callees

- `0x180034804`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034814`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034825`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034814`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034825`

## pseudocode

```c
void __fastcall Free_SPP_ENVIRONMENT_PROP(LPVOID *a1)
{
  void *v2; // rcx

  if ( a1 )
  {
    CoTaskMemFree(*a1);
    v2 = a1[1];
    *a1 = 0;
    CoTaskMemFree(v2);
    a1[1] = 0;
  }
}

```

## disassembly

```asm
0x180034804  test    rcx, rcx
0x180034807  jz      short locret_180034838
0x180034809  push    rbx
0x18003480a  sub     rsp, 20h
0x18003480e  mov     rbx, rcx
0x180034811  mov     rcx, [rcx]; pv
0x180034814  call    cs:__imp_CoTaskMemFree
0x18003481a  mov     rcx, [rbx+8]; pv
0x18003481e  mov     qword ptr [rbx], 0
0x180034825  call    cs:__imp_CoTaskMemFree
0x18003482b  mov     qword ptr [rbx+8], 0
0x180034833  add     rsp, 20h
0x180034837  pop     rbx
0x180034838  retn
```
