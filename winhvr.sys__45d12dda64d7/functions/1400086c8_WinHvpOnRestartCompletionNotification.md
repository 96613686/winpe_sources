# WinHvpOnRestartCompletionNotification

- ea: `0x1400086c8`
- end: `0x140008709`
- name: `WinHvpOnRestartCompletionNotification`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400011c0`

## callees

- `0x1400086c8`

## import_xrefs

- `ntoskrnl!KeInsertQueueDpc` at `0x1400086f7`
- `ntoskrnl!KeInsertQueueDpc` at `0x1400086f7`

## pseudocode

```c
char __fastcall WinHvpOnRestartCompletionNotification(__int64 a1)
{
  int v1; // eax
  volatile signed __int32 *v2; // rax

  v1 = *(_DWORD *)(a1 + 20);
  if ( !v1 )
  {
    v2 = &dword_14001621C;
LABEL_5:
    _InterlockedIncrement(v2);
    LOBYTE(v1) = KeInsertQueueDpc(&Dpc, 0, 0);
    return v1;
  }
  if ( v1 == 1 )
  {
    v2 = &dword_140016218;
    goto LABEL_5;
  }
  return v1;
}

```

## disassembly

```asm
0x1400086c8  sub     rsp, 28h
0x1400086cc  mov     eax, [rcx+14h]
0x1400086cf  test    eax, eax
0x1400086d1  jnz     short loc_1400086DC
0x1400086d3  lea     rax, dword_14001621C
0x1400086da  jmp     short loc_1400086E8
0x1400086dc  cmp     eax, 1
0x1400086df  jnz     short loc_140008703
0x1400086e1  lea     rax, dword_140016218
0x1400086e8  lock inc dword ptr [rax]
0x1400086eb  xor     r8d, r8d; SystemArgument2
0x1400086ee  lea     rcx, Dpc; Dpc
0x1400086f5  xor     edx, edx; SystemArgument1
0x1400086f7  call    cs:__imp_KeInsertQueueDpc
0x1400086fe  nop     dword ptr [rax+rax+00h]
0x140008703  add     rsp, 28h
0x140008707  retn
```
