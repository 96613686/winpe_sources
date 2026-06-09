# RfspThreadPoolNodeWakeIdleWorker

- ea: `0x140004960`
- end: `0x14000499a`
- name: `RfspThreadPoolNodeWakeIdleWorker`
- size: `58`
- prototype: ``
- caller_count: `40`
- callee_count: `1`
- tags: ``

## callers

- `0x1400041a0`
- `0x140004560`
- `0x140004814`
- `0x1400049a0`
- `0x1400055b0`
- `0x140006218`
- `0x140006580`
- `0x140006ad0`
- `0x140007ff8`
- `0x140008410`
- `0x140008c40`
- `0x14000ae60`
- `0x14000ca00`
- `0x14000cdf0`
- `0x14000e140`
- `0x14000e340`
- `0x14000e5f0`
- `0x14000f060`
- `0x140012790`
- `0x1400128b0`
- `0x1400136b0`
- `0x140013810`
- `0x1400167f0`
- `0x140017730`
- `0x140019168`
- `0x14001a250`
- `0x14001b3fc`
- `0x14001f050`
- `0x14001fa5c`
- `0x14002038c`
- `0x140022820`
- `0x1400228c0`
- `0x14002b7f8`
- `0x14002bff0`
- `0x14002c360`
- `0x14002c6d0`
- `0x1400312f0`
- `0x140032f70`
- `0x140034590`
- `0x1400736d0`

## callees

- `0x140004960`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000498c`
- `ntoskrnl!KeSetEvent` at `0x14000498c`
- `ntoskrnl!KeReadStateEvent` at `0x14000496d`
- `ntoskrnl!KeReadStateEvent` at `0x14000496d`

## pseudocode

```c
LONG __fastcall RfspThreadPoolNodeWakeIdleWorker(struct _KEVENT *a1)
{
  struct _KEVENT *v1; // rbx
  LONG result; // eax

  v1 = a1 + 3;
  result = KeReadStateEvent(a1 + 3);
  if ( !result )
    return KeSetEvent(v1, 0, 0);
  return result;
}

```

## disassembly

```asm
0x140004960  push    rbx
0x140004962  sub     rsp, 20h
0x140004966  lea     rbx, [rcx+48h]
0x14000496a  mov     rcx, rbx; Event
0x14000496d  call    cs:__imp_KeReadStateEvent
0x140004974  nop     dword ptr [rax+rax+00h]
0x140004979  test    eax, eax
0x14000497b  jz      short loc_140004984
0x14000497d  add     rsp, 20h
0x140004981  pop     rbx
0x140004982  retn
0x140004984  xor     r8d, r8d; Wait
0x140004987  xor     edx, edx; Increment
0x140004989  mov     rcx, rbx; Event
0x14000498c  call    cs:__imp_KeSetEvent
0x140004993  nop     dword ptr [rax+rax+00h]
0x140004998  jmp     short loc_14000497D
```
