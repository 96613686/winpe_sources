# TdxSynchronousTlCreateRequestComplete

- ea: `0x140010ac0`
- end: `0x140010ae9`
- name: `TdxSynchronousTlCreateRequestComplete`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140010ad7`
- `ntoskrnl!KeSetEvent` at `0x140010ad7`

## pseudocode

```c
LONG __fastcall TdxSynchronousTlCreateRequestComplete(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  *(_DWORD *)(a1 + 8) = a2;
  *(_QWORD *)(a1 + 16) = a3;
  *(_QWORD *)(a1 + 24) = a4;
  return KeSetEvent(*(PRKEVENT *)a1, 0, 0);
}

```

## disassembly

```asm
0x140010ac0  sub     rsp, 28h
0x140010ac4  mov     [rcx+8], edx
0x140010ac7  xor     edx, edx; Increment
0x140010ac9  mov     [rcx+10h], r8
0x140010acd  xor     r8d, r8d; Wait
0x140010ad0  mov     [rcx+18h], r9
0x140010ad4  mov     rcx, [rcx]; Event
0x140010ad7  call    cs:__imp_KeSetEvent
0x140010ade  nop     dword ptr [rax+rax+00h]
0x140010ae3  add     rsp, 28h
0x140010ae7  retn
```
