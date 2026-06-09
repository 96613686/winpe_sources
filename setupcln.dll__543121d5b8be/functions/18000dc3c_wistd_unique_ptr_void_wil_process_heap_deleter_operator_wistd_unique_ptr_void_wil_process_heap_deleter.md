# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x18000dc3c`
- end: `0x18000dc68`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: `wil::details **__fastcall(wil::details **, wil::details **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180010560`
- `0x180011678`

## callees

- `0x18000dc3c`
- `0x18000e6bc`

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
0x18000dc3c  push    rbx
0x18000dc3e  sub     rsp, 20h
0x18000dc42  mov     rax, [rdx]
0x18000dc45  mov     rbx, rcx
0x18000dc48  mov     qword ptr [rdx], 0
0x18000dc4f  mov     rcx, [rcx]; this
0x18000dc52  mov     [rbx], rax
0x18000dc55  test    rcx, rcx
0x18000dc58  jz      short loc_18000DC5F
0x18000dc5a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000dc5f  mov     rax, rbx
0x18000dc62  add     rsp, 20h
0x18000dc66  pop     rbx
0x18000dc67  retn
```
