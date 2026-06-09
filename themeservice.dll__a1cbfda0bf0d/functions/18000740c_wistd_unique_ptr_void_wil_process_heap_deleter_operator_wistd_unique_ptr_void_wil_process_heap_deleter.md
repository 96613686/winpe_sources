# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x18000740c`
- end: `0x180007438`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: `wil::details **__fastcall(wil::details **, wil::details **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007094`
- `0x180007368`

## callees

- `0x18000740c`
- `0x180008afc`

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
0x18000740c  push    rbx
0x18000740e  sub     rsp, 20h
0x180007412  mov     rax, [rdx]
0x180007415  mov     rbx, rcx
0x180007418  mov     qword ptr [rdx], 0
0x18000741f  mov     rcx, [rcx]; this
0x180007422  mov     [rbx], rax
0x180007425  test    rcx, rcx
0x180007428  jz      short loc_18000742F
0x18000742a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000742f  mov     rax, rbx
0x180007432  add     rsp, 20h
0x180007436  pop     rbx
0x180007437  retn
```
