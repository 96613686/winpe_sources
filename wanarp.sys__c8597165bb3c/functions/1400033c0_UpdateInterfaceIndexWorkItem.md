# UpdateInterfaceIndexWorkItem

- ea: `0x1400033c0`
- end: `0x1400033ed`
- name: `UpdateInterfaceIndexWorkItem`
- size: `45`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140003344`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400033da`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400033da`

## pseudocode

```c
void __fastcall UpdateInterfaceIndexWorkItem(PVOID P)
{
  UpdateInterfaceIndexImpl(*((PVOID *)P + 4), *((_DWORD *)P + 10));
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x1400033c0  push    rbx
0x1400033c2  sub     rsp, 20h
0x1400033c6  mov     edx, [rcx+28h]; ifIndex
0x1400033c9  mov     rbx, rcx
0x1400033cc  mov     rcx, [rcx+20h]; Entry
0x1400033d0  call    UpdateInterfaceIndexImpl
0x1400033d5  xor     edx, edx; Tag
0x1400033d7  mov     rcx, rbx; P
0x1400033da  call    cs:__imp_ExFreePoolWithTag
0x1400033e1  nop     dword ptr [rax+rax+00h]
0x1400033e6  add     rsp, 20h
0x1400033ea  pop     rbx
0x1400033eb  retn
```
