# WaitWakeRemoveIrp

- ea: `0x14000e320`
- end: `0x14000e356`
- name: `WaitWakeRemoveIrp`
- size: `54`
- prototype: `IO_CSQ_REMOVE_IRP`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000e320`

## pseudocode

```c
void __fastcall WaitWakeRemoveIrp(PIO_CSQ Csq, PIRP Irp)
{
  _LIST_ENTRY *p_ListEntry; // rdx
  _LIST_ENTRY *Flink; // rcx
  _LIST_ENTRY *Blink; // rax

  p_ListEntry = &Irp->Tail.Overlay.ListEntry;
  --*((_DWORD *)Csq[3].CsqInsertIrp + 102);
  Flink = p_ListEntry->Flink;
  if ( p_ListEntry->Flink->Blink != p_ListEntry || (Blink = p_ListEntry->Blink, Blink->Flink != p_ListEntry) )
    __fastfail(3u);
  Blink->Flink = Flink;
  Flink->Blink = Blink;
}

```

## disassembly

```asm
0x14000e320  mov     rax, [rcx+0C8h]
0x14000e327  add     rdx, 0A8h
0x14000e32e  dec     dword ptr [rax+198h]
0x14000e334  mov     rcx, [rdx]
0x14000e337  cmp     [rcx+8], rdx
0x14000e33b  jnz     short loc_14000E34F
0x14000e33d  mov     rax, [rdx+8]
0x14000e341  cmp     [rax], rdx
0x14000e344  jnz     short loc_14000E34F
0x14000e346  mov     [rax], rcx
0x14000e349  mov     [rcx+8], rax
0x14000e34d  retn
0x14000e34f  mov     ecx, 3
0x14000e354  int     29h; Win8: RtlFailFast(ecx)
```
