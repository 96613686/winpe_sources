# OutpEnqueuePollingDpc

- ea: `0x14000a1cc`
- end: `0x14000a1fe`
- name: `OutpEnqueuePollingDpc`
- size: `50`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140001780`
- `0x1400037e0`
- `0x140005250`
- `0x1400055d0`
- `0x140006700`

## callees

- `0x14000a1cc`

## import_xrefs

- `ntoskrnl!KeInsertQueueDpc` at `0x14000a1e1`
- `ntoskrnl!KeInsertQueueDpc` at `0x14000a1e1`

## pseudocode

```c
BOOLEAN __fastcall OutpEnqueuePollingDpc(__int64 a1)
{
  BOOLEAN result; // al

  result = KeInsertQueueDpc((PRKDPC)(a1 + 968), 0, 0);
  if ( result )
    ++*(_DWORD *)(a1 + 1032);
  return result;
}

```

## disassembly

```asm
0x14000a1cc  push    rbx
0x14000a1ce  sub     rsp, 20h
0x14000a1d2  mov     rbx, rcx
0x14000a1d5  xor     r8d, r8d; SystemArgument2
0x14000a1d8  add     rcx, 3C8h; Dpc
0x14000a1df  xor     edx, edx; SystemArgument1
0x14000a1e1  call    cs:__imp_KeInsertQueueDpc
0x14000a1e8  nop     dword ptr [rax+rax+00h]
0x14000a1ed  test    al, al
0x14000a1ef  jz      short loc_14000A1F7
0x14000a1f1  inc     dword ptr [rbx+408h]
0x14000a1f7  add     rsp, 20h
0x14000a1fb  pop     rbx
0x14000a1fc  retn
```
