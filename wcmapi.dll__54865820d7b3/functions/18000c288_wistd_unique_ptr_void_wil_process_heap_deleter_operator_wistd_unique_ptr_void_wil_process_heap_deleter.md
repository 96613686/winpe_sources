# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x18000c288`
- end: `0x18000c2b5`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `45`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bb08`
- `0x18000f3d8`

## callees

- `0x18000c288`
- `0x18000d0f0`

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
0x18000c288  push    rbx
0x18000c28a  sub     rsp, 20h
0x18000c28e  mov     rax, [rdx]
0x18000c291  mov     rbx, rcx
0x18000c294  mov     qword ptr [rdx], 0
0x18000c29b  mov     rcx, [rcx]; this
0x18000c29e  mov     [rbx], rax
0x18000c2a1  test    rcx, rcx
0x18000c2a4  jz      short loc_18000C2AB
0x18000c2a6  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000c2ab  mov     rax, rbx
0x18000c2ae  add     rsp, 20h
0x18000c2b2  pop     rbx
0x18000c2b3  retn
```
