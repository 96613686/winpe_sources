# TdxSynchronousTlRequestComplete

- ea: `0x1400105e0`
- end: `0x140010601`
- name: `TdxSynchronousTlRequestComplete`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400105ef`
- `ntoskrnl!KeSetEvent` at `0x1400105ef`

## pseudocode

```c
LONG __fastcall TdxSynchronousTlRequestComplete(__int64 a1, int a2)
{
  *(_DWORD *)(a1 + 8) = a2;
  return KeSetEvent(*(PRKEVENT *)a1, 0, 0);
}

```

## disassembly

```asm
0x1400105e0  sub     rsp, 28h
0x1400105e4  mov     [rcx+8], edx
0x1400105e7  xor     r8d, r8d; Wait
0x1400105ea  mov     rcx, [rcx]; Event
0x1400105ed  xor     edx, edx; Increment
0x1400105ef  call    cs:__imp_KeSetEvent
0x1400105f6  nop     dword ptr [rax+rax+00h]
0x1400105fb  add     rsp, 28h
0x1400105ff  retn
```
