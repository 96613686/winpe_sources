# WanpClearPacketFilterComplete

- ea: `0x140003020`
- end: `0x140003057`
- name: `WanpClearPacketFilterComplete`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140002bb0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140003045`
- `ntoskrnl!KeSetEvent` at `0x140003045`

## pseudocode

```c
LONG __fastcall WanpClearPacketFilterComplete(__int64 a1)
{
  struct _KEVENT *v1; // rax

  v1 = (struct _KEVENT *)qword_140009AD0;
  if ( a1 != 212578788 )
    v1 = &stru_140009BF0;
  return KeSetEvent(v1, 0, 0);
}

```

## disassembly

```asm
0x140003020  sub     rsp, 28h
0x140003024  cmp     rcx, 0CABB1E4h
0x14000302b  lea     rdx, stru_140009BF0
0x140003032  lea     rax, qword_140009AD0
0x140003039  cmovnz  rax, rdx
0x14000303d  xor     r8d, r8d; Wait
0x140003040  mov     rcx, rax; Event
0x140003043  xor     edx, edx; Increment
0x140003045  call    cs:__imp_KeSetEvent
0x14000304c  nop     dword ptr [rax+rax+00h]
0x140003051  add     rsp, 28h
0x140003055  retn
```
