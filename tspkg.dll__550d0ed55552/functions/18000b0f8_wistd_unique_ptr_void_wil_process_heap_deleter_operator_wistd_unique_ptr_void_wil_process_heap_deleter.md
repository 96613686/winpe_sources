# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x18000b0f8`
- end: `0x18000b124`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ad70`
- `0x18000b054`

## callees

- `0x18000b0f8`
- `0x18000deec`

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
0x18000b0f8  push    rbx
0x18000b0fa  sub     rsp, 20h
0x18000b0fe  mov     rax, [rdx]
0x18000b101  mov     rbx, rcx
0x18000b104  mov     qword ptr [rdx], 0
0x18000b10b  mov     rcx, [rcx]; this
0x18000b10e  mov     [rbx], rax
0x18000b111  test    rcx, rcx
0x18000b114  jz      short loc_18000B11B
0x18000b116  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000b11b  mov     rax, rbx
0x18000b11e  add     rsp, 20h
0x18000b122  pop     rbx
0x18000b123  retn
```
