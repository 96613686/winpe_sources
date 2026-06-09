# UdfKillCleanVolumeTimer

- ea: `0x14000b200`
- end: `0x14000b246`
- name: `UdfKillCleanVolumeTimer`
- size: `70`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140003148`
- `0x14002c008`

## callees

- `0x14000b200`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x14000b219`
- `ntoskrnl!KeCancelTimer` at `0x14000b219`
- `ntoskrnl!KeRemoveQueueDpc` at `0x14000b22c`
- `ntoskrnl!KeRemoveQueueDpc` at `0x14000b22c`

## pseudocode

```c
BOOLEAN __fastcall UdfKillCleanVolumeTimer(__int64 a1)
{
  BOOLEAN result; // al

  if ( (*(_DWORD *)(a1 + 48) & 0x400000) != 0 )
  {
    KeCancelTimer((PKTIMER)(a1 + 1920));
    result = KeRemoveQueueDpc((PRKDPC)(a1 + 1856));
  }
  *(_DWORD *)(a1 + 2128) &= ~4u;
  return result;
}

```

## disassembly

```asm
0x14000b200  push    rbx
0x14000b202  sub     rsp, 20h
0x14000b206  test    dword ptr [rcx+30h], 400000h
0x14000b20d  mov     rbx, rcx
0x14000b210  jz      short loc_14000B238
0x14000b212  add     rcx, 780h; PKTIMER
0x14000b219  call    cs:__imp_KeCancelTimer
0x14000b220  nop     dword ptr [rax+rax+00h]
0x14000b225  lea     rcx, [rbx+740h]; Dpc
0x14000b22c  call    cs:__imp_KeRemoveQueueDpc
0x14000b233  nop     dword ptr [rax+rax+00h]
0x14000b238  and     dword ptr [rbx+850h], 0FFFFFFFBh
0x14000b23f  add     rsp, 20h
0x14000b243  pop     rbx
0x14000b244  retn
```
