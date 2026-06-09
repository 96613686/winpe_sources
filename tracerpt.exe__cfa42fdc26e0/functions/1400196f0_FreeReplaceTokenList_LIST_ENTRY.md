# FreeReplaceTokenList(_LIST_ENTRY *)

- ea: `0x1400196f0`
- end: `0x140019759`
- name: `?FreeReplaceTokenList@@YAXPEAU_LIST_ENTRY@@@Z`
- size: `105`
- prototype: `void __fastcall(struct _LIST_ENTRY *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140019960`
- `0x140019b70`

## callees

- `0x1400196f0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140019737`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140019737`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140019729`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140019729`

## pseudocode

```c
void __fastcall FreeReplaceTokenList(struct _LIST_ENTRY *a1)
{
  struct _LIST_ENTRY *Flink; // rdi
  struct _LIST_ENTRY *v3; // rax
  struct _LIST_ENTRY *Blink; // rcx
  struct _LIST_ENTRY *v5; // rbx
  HANDLE ProcessHeap; // rax

  Flink = a1->Flink;
  while ( a1 != Flink )
  {
    v3 = Flink->Flink;
    if ( Flink->Flink->Blink != Flink || (Blink = Flink->Blink, Blink->Flink != Flink) )
      __fastfail(3u);
    Blink->Flink = v3;
    v5 = Flink;
    Flink = v3;
    v3->Blink = Blink;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v5);
  }
}

```

## disassembly

```asm
0x1400196f0  mov     [rsp+arg_0], rbx
0x1400196f5  mov     [rsp+arg_8], rsi
0x1400196fa  push    rdi
0x1400196fb  sub     rsp, 20h
0x1400196ff  mov     rdi, [rcx]
0x140019702  mov     rsi, rcx
0x140019705  cmp     rcx, rdi
0x140019708  jz      short loc_140019742
0x14001970a  mov     rax, [rdi]
0x14001970d  cmp     [rax+8], rdi
0x140019711  jnz     short loc_140019752
0x140019713  mov     rcx, [rdi+8]
0x140019717  cmp     [rcx], rdi
0x14001971a  jnz     short loc_140019752
0x14001971c  mov     [rcx], rax
0x14001971f  mov     rbx, rdi
0x140019722  mov     rdi, rax
0x140019725  mov     [rax+8], rcx
0x140019729  call    cs:__imp_GetProcessHeap
0x14001972f  mov     r8, rbx; lpMem
0x140019732  xor     edx, edx; dwFlags
0x140019734  mov     rcx, rax; hHeap
0x140019737  call    cs:__imp_HeapFree
0x14001973d  cmp     rsi, rdi
0x140019740  jnz     short loc_14001970A
0x140019742  mov     rbx, [rsp+28h+arg_0]
0x140019747  mov     rsi, [rsp+28h+arg_8]
0x14001974c  add     rsp, 20h
0x140019750  pop     rdi
0x140019751  retn
0x140019752  mov     ecx, 3
0x140019757  int     29h; Win8: RtlFailFast(ecx)
```
