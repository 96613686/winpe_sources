# Free_SPP_COMPONENT_LOCATION(_SPP_COMPONENT_LOCATION *)

- ea: `0x1800346fc`
- end: `0x180034755`
- name: `?Free_SPP_COMPONENT_LOCATION@@YAXPEAU_SPP_COMPONENT_LOCATION@@@Z`
- size: `89`
- prototype: `void __fastcall(struct _SPP_COMPONENT_LOCATION *)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800024bc`
- `0x18001daa8`
- `0x18003475c`

## callees

- `0x1800346fc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003470c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003471d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003472f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034741`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003470c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003471d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003472f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034741`

## pseudocode

```c
void __fastcall Free_SPP_COMPONENT_LOCATION(LPVOID *a1)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx

  if ( a1 )
  {
    CoTaskMemFree(*a1);
    v2 = a1[1];
    *a1 = 0;
    CoTaskMemFree(v2);
    v3 = a1[2];
    a1[1] = 0;
    CoTaskMemFree(v3);
    v4 = a1[4];
    a1[2] = 0;
    CoTaskMemFree(v4);
    a1[4] = 0;
  }
}

```

## disassembly

```asm
0x1800346fc  test    rcx, rcx
0x1800346ff  jz      short locret_180034754
0x180034701  push    rbx
0x180034702  sub     rsp, 20h
0x180034706  mov     rbx, rcx
0x180034709  mov     rcx, [rcx]; pv
0x18003470c  call    cs:__imp_CoTaskMemFree
0x180034712  mov     rcx, [rbx+8]; pv
0x180034716  mov     qword ptr [rbx], 0
0x18003471d  call    cs:__imp_CoTaskMemFree
0x180034723  mov     rcx, [rbx+10h]; pv
0x180034727  mov     qword ptr [rbx+8], 0
0x18003472f  call    cs:__imp_CoTaskMemFree
0x180034735  mov     rcx, [rbx+20h]; pv
0x180034739  mov     qword ptr [rbx+10h], 0
0x180034741  call    cs:__imp_CoTaskMemFree
0x180034747  mov     qword ptr [rbx+20h], 0
0x18003474f  add     rsp, 20h
0x180034753  pop     rbx
0x180034754  retn
```
