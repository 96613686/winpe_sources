# Free_SPP_BAD_COMPONENT_INFO(_SPP_COMPONENT_ERROR_INFO *)

- ea: `0x180008d3c`
- end: `0x180008d83`
- name: `?Free_SPP_BAD_COMPONENT_INFO@@YAXPEAU_SPP_COMPONENT_ERROR_INFO@@@Z`
- size: `71`
- prototype: `void __fastcall(struct _SPP_COMPONENT_ERROR_INFO *)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002458`
- `0x180008d8c`
- `0x1800102e4`

## callees

- `0x180008d3c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008d4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008d5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008d6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008d4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008d5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008d6f`

## pseudocode

```c
void __fastcall Free_SPP_BAD_COMPONENT_INFO(LPVOID *a1)
{
  void *v2; // rcx
  void *v3; // rcx

  if ( a1 )
  {
    CoTaskMemFree(a1[4]);
    v2 = *a1;
    a1[4] = 0;
    CoTaskMemFree(v2);
    v3 = a1[1];
    *a1 = 0;
    CoTaskMemFree(v3);
    a1[1] = 0;
  }
}

```

## disassembly

```asm
0x180008d3c  test    rcx, rcx
0x180008d3f  jz      short locret_180008D82
0x180008d41  push    rbx
0x180008d42  sub     rsp, 20h
0x180008d46  mov     rbx, rcx
0x180008d49  mov     rcx, [rcx+20h]; pv
0x180008d4d  call    cs:__imp_CoTaskMemFree
0x180008d53  mov     rcx, [rbx]; pv
0x180008d56  mov     qword ptr [rbx+20h], 0
0x180008d5e  call    cs:__imp_CoTaskMemFree
0x180008d64  mov     rcx, [rbx+8]; pv
0x180008d68  mov     qword ptr [rbx], 0
0x180008d6f  call    cs:__imp_CoTaskMemFree
0x180008d75  mov     qword ptr [rbx+8], 0
0x180008d7d  add     rsp, 20h
0x180008d81  pop     rbx
0x180008d82  retn
```
