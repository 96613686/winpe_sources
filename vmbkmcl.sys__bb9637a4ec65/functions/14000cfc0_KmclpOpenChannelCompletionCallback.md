# KmclpOpenChannelCompletionCallback

- ea: `0x14000cfc0`
- end: `0x14000cfde`
- name: `KmclpOpenChannelCompletionCallback`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000cfcc`
- `ntoskrnl!KeSetEvent` at `0x14000cfcc`

## pseudocode

```c
LONG __fastcall KmclpOpenChannelCompletionCallback(struct _KEVENT *a1, LONG a2)
{
  a1[1].Header.LockNV = a2;
  return KeSetEvent(a1, 0, 0);
}

```

## disassembly

```asm
0x14000cfc0  sub     rsp, 28h
0x14000cfc4  mov     [rcx+18h], edx
0x14000cfc7  xor     r8d, r8d; Wait
0x14000cfca  xor     edx, edx; Increment
0x14000cfcc  call    cs:__imp_KeSetEvent
0x14000cfd3  nop     dword ptr [rax+rax+00h]
0x14000cfd8  add     rsp, 28h
0x14000cfdc  retn
```
