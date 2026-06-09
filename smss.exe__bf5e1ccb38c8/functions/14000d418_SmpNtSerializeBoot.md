# SmpNtSerializeBoot

- ea: `0x14000d418`
- end: `0x14000d448`
- name: `SmpNtSerializeBoot`
- size: `48`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140006f30`
- `0x14000c638`
- `0x14000f120`

## callees

- `0x140008d10`
- `0x14000d450`

## import_xrefs

- `ntdll!NtSerializeBoot` at `0x14000d42a`
- `ntdll!NtSerializeBoot` at `0x14000d42a`

## pseudocode

```c
__int64 SmpNtSerializeBoot()
{
  unsigned int v0; // ebx

  SmpEventWrite(&SmssEvt_SerializeBoot_Start);
  v0 = NtSerializeBoot();
  SmpEventWriteULONG(&SmssEvt_SerializeBoot_Stop, v0);
  return v0;
}

```

## disassembly

```asm
0x14000d418  push    rbx
0x14000d41a  sub     rsp, 20h
0x14000d41e  lea     rcx, SmssEvt_SerializeBoot_Start; EventDescriptor
0x14000d425  call    SmpEventWrite
0x14000d42a  call    cs:__imp_NtSerializeBoot
0x14000d430  mov     edx, eax
0x14000d432  lea     rcx, SmssEvt_SerializeBoot_Stop; EventDescriptor
0x14000d439  mov     ebx, eax
0x14000d43b  call    SmpEventWriteULONG
0x14000d440  mov     eax, ebx
0x14000d442  add     rsp, 20h
0x14000d446  pop     rbx
0x14000d447  retn
```
