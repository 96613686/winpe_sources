# CUsbHubSqm::GUIDComparer::operator()(_GUID const &,_GUID const &)

- ea: `0x1800051e0`
- end: `0x180005205`
- name: `??RGUIDComparer@CUsbHubSqm@@QEBA_NAEBU_GUID@@0@Z`
- size: `37`
- prototype: `bool __fastcall(__int64, const void *, const void *)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004ee4`
- `0x180004f68`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x1800051f3`
- `ntdll!RtlCompareMemory` at `0x1800051f3`

## pseudocode

```c
bool __fastcall CUsbHubSqm::GUIDComparer::operator()(__int64 a1, const void *a2, const void *a3)
{
  return RtlCompareMemory(a2, a3, 0x10u) != 16;
}

```

## disassembly

```asm
0x1800051e0  sub     rsp, 28h
0x1800051e4  mov     rax, r8
0x1800051e7  mov     rcx, rdx; Source1
0x1800051ea  mov     rdx, rax; Source2
0x1800051ed  mov     r8d, 10h; Length
0x1800051f3  call    cs:__imp_RtlCompareMemory
0x1800051f9  cmp     rax, 10h
0x1800051fd  setnz   al
0x180005200  add     rsp, 28h
0x180005204  retn
```
