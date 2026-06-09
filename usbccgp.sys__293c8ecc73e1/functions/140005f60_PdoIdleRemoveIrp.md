# PdoIdleRemoveIrp

- ea: `0x140005f60`
- end: `0x140005fbe`
- name: `PdoIdleRemoveIrp`
- size: `94`
- prototype: `IO_CSQ_REMOVE_IRP`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140005f60`
- `0x140006430`

## pseudocode

```c
void __fastcall PdoIdleRemoveIrp(char *Csq, PIRP Irp)
{
  _LIST_ENTRY *p_ListEntry; // rdx
  _LIST_ENTRY *Flink; // r8
  _LIST_ENTRY *Blink; // rax
  char *v5; // rbx
  void (__fastcall *v6)(_IO_CSQ *, _IRP *); // rcx

  p_ListEntry = &Irp->Tail.Overlay.ListEntry;
  Flink = p_ListEntry->Flink;
  if ( p_ListEntry->Flink->Blink != p_ListEntry || (Blink = p_ListEntry->Blink, Blink->Flink != p_ListEntry) )
    __fastfail(3u);
  v5 = Csq - 120;
  v6 = (void (__fastcall *)(_IO_CSQ *, _IRP *))*((_QWORD *)Csq + 14);
  Blink->Flink = Flink;
  Flink->Blink = Blink;
  SetPdoIdle((__int64)v6, (__int64)v5, 3, 0, 0);
  *((_QWORD *)v5 + 36) = 0;
}

```

## disassembly

```asm
0x140005f60  push    rbx
0x140005f62  sub     rsp, 30h
0x140005f66  add     rdx, 0A8h
0x140005f6d  mov     r8, [rdx]
0x140005f70  cmp     [r8+8], rdx
0x140005f74  jnz     short loc_140005FB7
0x140005f76  mov     rax, [rdx+8]
0x140005f7a  cmp     [rax], rdx
0x140005f7d  jnz     short loc_140005FB7
0x140005f7f  lea     rbx, [rcx-78h]
0x140005f83  mov     [rsp+38h+var_18], 0
0x140005f88  mov     rcx, [rbx+0E8h]
0x140005f8f  xor     r9d, r9d
0x140005f92  mov     [rax], r8
0x140005f95  mov     rdx, rbx
0x140005f98  mov     [r8+8], rax
0x140005f9c  lea     r8d, [r9+3]
0x140005fa0  call    SetPdoIdle
0x140005fa5  mov     qword ptr [rbx+120h], 0
0x140005fb0  add     rsp, 30h
0x140005fb4  pop     rbx
0x140005fb5  retn
0x140005fb7  mov     ecx, 3
0x140005fbc  int     29h; Win8: RtlFailFast(ecx)
```
