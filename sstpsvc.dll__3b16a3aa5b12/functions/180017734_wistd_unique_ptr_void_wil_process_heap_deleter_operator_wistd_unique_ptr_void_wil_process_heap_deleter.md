# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x180017734`
- end: `0x180017760`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180019c6c`
- `0x18001aad8`

## callees

- `0x180017734`
- `0x18001804c`

## pseudocode

```c
wil::details **__fastcall wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(
        wil::details **a1,
        wil::details **a2)
{
  wil::details *v2; // rax
  wil::details *v4; // rcx

  v2 = *a2;
  *a2 = 0;
  v4 = *a1;
  *a1 = v2;
  if ( v4 )
    wil::details::FreeProcessHeap(v4, a2);
  return a1;
}

```

## disassembly

```asm
0x180017734  push    rbx
0x180017736  sub     rsp, 20h
0x18001773a  mov     rax, [rdx]
0x18001773d  mov     rbx, rcx
0x180017740  mov     qword ptr [rdx], 0
0x180017747  mov     rcx, [rcx]; this
0x18001774a  mov     [rbx], rax
0x18001774d  test    rcx, rcx
0x180017750  jz      short loc_180017757
0x180017752  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180017757  mov     rax, rbx
0x18001775a  add     rsp, 20h
0x18001775e  pop     rbx
0x18001775f  retn
```
