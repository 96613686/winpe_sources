# myDeleteTimerQueueTimer(void *,void *,void *)

- ea: `0x18002a940`
- end: `0x18002a975`
- name: `?myDeleteTimerQueueTimer@@YAXPEAX00@Z`
- size: `53`
- prototype: `void __fastcall(void *, struct _RTL_CRITICAL_SECTION *, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180009a80`
- `0x180029bbc`

## callees

- `0x18002a980`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a969`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002a955`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002a955`

## pseudocode

```c
void __fastcall myDeleteTimerQueueTimer(void *a1, struct _RTL_CRITICAL_SECTION *a2, void *a3)
{
  myStopTimerQueueTimer(a1, a2, (void *)0xFFFFFFFFFFFFFFFFLL);
  DeleteCriticalSection(a2);
  LocalFree(a2);
}

```

## disassembly

```asm
0x18002a940  push    rbx
0x18002a942  sub     rsp, 20h
0x18002a946  or      r8, 0FFFFFFFFFFFFFFFFh; void *
0x18002a94a  mov     rbx, rdx
0x18002a94d  call    ?myStopTimerQueueTimer@@YAJPEAX00@Z; myStopTimerQueueTimer(void *,void *,void *)
0x18002a952  mov     rcx, rbx; lpCriticalSection
0x18002a955  call    cs:__imp_DeleteCriticalSection
0x18002a95c  nop     dword ptr [rax+rax+00h]
0x18002a961  mov     rcx, rbx
0x18002a964  add     rsp, 20h
0x18002a968  pop     rbx
0x18002a969  jmp     cs:__imp_LocalFree
```
