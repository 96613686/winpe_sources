# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x180004174`
- end: `0x1800041a1`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `45`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003d00`
- `0x1800040d0`

## callees

- `0x180004174`
- `0x1800046f4`

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
0x180004174  push    rbx
0x180004176  sub     rsp, 20h
0x18000417a  mov     rax, [rdx]
0x18000417d  mov     rbx, rcx
0x180004180  mov     qword ptr [rdx], 0
0x180004187  mov     rcx, [rcx]; this
0x18000418a  mov     [rbx], rax
0x18000418d  test    rcx, rcx
0x180004190  jz      short loc_180004197
0x180004192  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180004197  mov     rax, rbx
0x18000419a  add     rsp, 20h
0x18000419e  pop     rbx
0x18000419f  retn
```
