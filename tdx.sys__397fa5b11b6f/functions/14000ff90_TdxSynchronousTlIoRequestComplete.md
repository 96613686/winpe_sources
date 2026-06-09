# TdxSynchronousTlIoRequestComplete

- ea: `0x14000ff90`
- end: `0x14000ffb5`
- name: `TdxSynchronousTlIoRequestComplete`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000ffa3`
- `ntoskrnl!KeSetEvent` at `0x14000ffa3`

## pseudocode

```c
LONG __fastcall TdxSynchronousTlIoRequestComplete(__int64 a1, int a2, __int64 a3)
{
  *(_DWORD *)(a1 + 8) = a2;
  *(_QWORD *)(a1 + 16) = a3;
  return KeSetEvent(*(PRKEVENT *)a1, 0, 0);
}

```

## disassembly

```asm
0x14000ff90  sub     rsp, 28h
0x14000ff94  mov     [rcx+8], edx
0x14000ff97  xor     edx, edx; Increment
0x14000ff99  mov     [rcx+10h], r8
0x14000ff9d  xor     r8d, r8d; Wait
0x14000ffa0  mov     rcx, [rcx]; Event
0x14000ffa3  call    cs:__imp_KeSetEvent
0x14000ffaa  nop     dword ptr [rax+rax+00h]
0x14000ffaf  add     rsp, 28h
0x14000ffb3  retn
```
