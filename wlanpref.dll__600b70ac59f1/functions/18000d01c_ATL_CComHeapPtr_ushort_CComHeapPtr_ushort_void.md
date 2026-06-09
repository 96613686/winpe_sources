# ATL::CComHeapPtr<ushort>::~CComHeapPtr<ushort>(void)

- ea: `0x18000d01c`
- end: `0x18000d03b`
- name: `??1?$CComHeapPtr@G@ATL@@QEAA@XZ`
- size: `31`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002e177`
- `0x18002e229`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d028`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d028`

## pseudocode

```c
void __fastcall ATL::CComHeapPtr<unsigned short>::~CComHeapPtr<unsigned short>(LPVOID *a1)
{
  CoTaskMemFree(*a1);
  *a1 = 0;
}

```

## disassembly

```asm
0x18000d01c  push    rbx
0x18000d01e  sub     rsp, 20h
0x18000d022  mov     rbx, rcx
0x18000d025  mov     rcx, [rcx]; pv
0x18000d028  call    cs:__imp_CoTaskMemFree
0x18000d02e  mov     qword ptr [rbx], 0
0x18000d035  add     rsp, 20h
0x18000d039  pop     rbx
0x18000d03a  retn
```
